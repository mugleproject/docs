# Build and Run Automation

To get an automated build of mugle and run the server, pull changes from Github, compile and restart, then run mugle as a service. Tested on both Ubuntu 16.04 and Fedora 28.

## Build and run manually the first time

Follow the instructions in the [build docs](../../getting-started/build.md) to build a binary or download the mugle [release binary](https://github.com/mugleproject/mugle/releases). You should end up with a `.mugle` directory in your home folder.

## Set up mugle as a service

Disable the TUI before setting up mugle as a service by updating the following line in `~/.mugle/main/mugle-server.toml` to `false`:

```toml
run_tui = false
```

Then create a service file for mugle:

```bash
sudo nano /etc/systemd/system/mugle.service
```

Paste the following content into the file. Ensure you update it with
your own user, group, working directory, and path where you placed the
mugle binary.

```
[Unit]
Description=mugle node
After=network.target

[Service]
WorkingDirectory=/home/alice/.mugle/
User=alice
Group=alice
PrivateDevices=yes
Type=simple
ExecReload=/bin/kill -HUP $MAINPID
KillMode=mixed
KillSignal=SIGTERM
TimeoutStopSec=60
ExecStart=/home/alice/mugleproject/mugle/target/release/mugle
Restart=on-failure
RestartSec=30

[Install]
WantedBy=multi-user.target
Alias=mugle.service
```

Tell systemd to reload (you need to do that every time you edit this file):

```bash
systemctl daemon-reload
```

Now try to start the node:

```bash
sudo systemctl start mugle
```

And check to see if it's running:

```bash
ps aux | grep mugle
```

That should give you two lines of output like this:

```bash
alice   19175  0.4  0.6 188040 54208 ?        Ssl  17:45   0:07 /home/alice/mugleproject/mugle/target/release/mugle
alice   27481  0.0  0.0  12944  1028 pts/0    S+   18:11   0:00 grep --color=auto mugle
```

!!! note "SELinux"

    If you use SELinux in Enforcing mode, the first time you are going to run mugle via systemd is going to fail with permission errors. You can grab a profile of those permission errors using `audit2allow`, create a SELinux policy module for mugle, and add that module in SELinux's policies.

    ```sh
    # capture mugle AVC denials in a file
    (sudo audit2allow -w -a | ausearch -c mugle) > denials.log
    # create a policy module out of the captured denials
    # avoid piping audit2allow to itself due to https://bugs.centos.org/view.php?id=14220
    cat denials.log | audit2allow -M mugle
    # set the module in SELinux's policies
    sudo semodule -i mugle.pp
    ```

    There is an additional thread in mugle named `peer_connect` that also gets denied certain access so it's more likely that you will need to repeat the above process for it as well.

## Create an update script

Copy this text into a `nightly-update.sh` script in the same directory as the above:

```sh
#!/bin/sh

cd /home/alice/mugleproject/mugle
git pull
git checkout master
git fetch --tags
latestTag=$(git describe --tags `git rev-list --tags --max-count=1`)
git checkout $latestTag
cargo build --release
sudo systemctl restart mugle
```

If you want to be pedantic and build from scratch every time, you can also insert `cargo clean` before `cargo build --release`.

## Set up a cron job

You can set up cron jobs for you the current user by executing:

```
crontab -e
```

This will open an editor and let you edit the cron file of the current user. Paste this onto the bottom of the file:

```
0 2 * * * /home/alice/mimblewimble/nightly-update.sh 1> /home/alice/mimblewimble/nightly-update.log 2> /home/alice/mimblewimble/nightly-update.log
```

The above puts either success or fail debug output into a file in your main directory. Alternatively, if mail is enabled on your host, you can also have the results emailed to you:

```
0 2 * * * /home/alice/mimblewimble/nightly-update.sh 2>&1 | mail -s "mugle update FAIL" you@yourdomain.com
```

This runs the script from the previous step at 2 am UTC. Please adjust this time with some randomness so your node does not restart at the same time as everyone else.

## Check that it worked

Later, after your chosen time of day has passed, you can check that all is working as expected. If you run `ps aux | grep mugle`, you should get one output line that is something like:

```
alice   13065  0.5  1.0 206492 85232 ?        Ssl  02:00   5:30 /home/alice/mugleproject/mugle/target/release/mugle
```

That means the server is running. Now also check that the latest version was built by running:

```
ls -l ~/mugleproject/mugle/target/release/mugle
```

That should make it all set to compile and restart every night. Enjoy!
