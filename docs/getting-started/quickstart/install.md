# Install

The *Quickstart* series will guide you in your first steps of installing a Mugle node, creating a wallet, and making a transaction.

!!! tip "GUI Wallet"
    To use Mugle with a graphical user interface, see [wallets](../wallets.md).

We begin by downloading the precompiled binaries.

* `mugle` - mugle node.
* `mugle-wallet` - command-line wallet.

First, choose your operating system:

* [Linux](#linux)
* [macOS](#macos)
* [Windows](#windows)

---

## Linux

Go to [mugle.org/download](https://mugle.org/download) and download the tgz files of mugle and mugle-wallet by clicking on their name titles. Or alternatively, type in the terminal:

```bash
wget https://github.com/mugleproject/mugle/releases/latest/download/mugle-$VERSION-linux-amd64.tar.gz
wget https://github.com/mugleproject/mugle-wallet/releases/latest/download/mugle-wallet-$VERSION-linux-amd64.tar.gz
```

*In every command replace `$VERSION` with the appropriate version for each binary, e.g. `v4.0.2`*

To verify the release, calculate the `sha256sum` of the binaries and compare the result against their respective SHA256 HASH on the website (or in [releases](https://github.com/mugleproject/mugle/releases)).

```bash
sha256sum mugle-wallet-$VERSION-linux-amd64.tar.gz
sha256sum mugle-$VERSION-linux-amd64.tar.gz
```

Next, navigate to the directory where the files were downloaded and extract the binaries:

```bash
sudo tar -C /usr/local/bin -xzf mugle-$VERSION-linux-amd64.tar.gz --strip-components=1
sudo tar -C /usr/local/bin -xzf mugle-wallet-$VERSION-linux-amd64.tar.gz --strip-components=1
```

??? note "libncursesw error &#8628;"
    If you have the following error when you start mugle:

    ```bash
    mugle: error while loading shared libraries: libncursesw.so.5: cannot open shared object file: No such file or directory
    ```

    Then install `libncursesw5`:

    ```bash
    sudo apt install libncursesw5
    ```

And you're done!

### Snap Store

You can also install everything as [Snap package](https://snapcraft.io/mugle), however, note that you can't verify its content.

To install, type:

```bash
snap install mugle
```

When installed with Snap, mugle-wallet is accessible using the `mugle.wallet` command instead of `mugle-wallet`.

---

## macOS


The easiest way to install mugle and mugle-wallet on macOS is with [homebrew](https://brew.sh).

If you do not have homebrew installed, open the "Terminal.app" and paste the following line:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

This will install homebrew on your computer.

Once it's finished, you can simply install the binaries:

```bash
brew install mugle mugle-wallet
```

---

## Windows

Go to [mugle.org/download](https://mugle.org/download) and download the zip files of mugle and mugle-wallet by clicking on their name titles.

We recommend that you create a directory called `Mugle` in `C:\Users\%USER%\AppData\Local`. The parent directory is where most user windows apps are installed, but if you want to put them somewhere else, that'll work too.

In this directory, extract both binaries `mugle.exe` and `mugle-wallet.exe`. Then, add them to your path by typing in the terminal:

```text
set PATH=%PATH%;C:\Users\%USER%\AppData\Local\Mugle
```

*Remember to replace %USER%*

That's it, you're done!
