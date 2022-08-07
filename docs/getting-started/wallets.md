# Mugle Wallets

[![Mugle++](images/mugleplusplus.png){ align=left width=60 }](https://mugleplusplus.github.io/){:target="_blank"}

## &emsp;Mugle++

</br>

GUI wallet and node written in C++ &emsp;~Windows,~ ~Linux,~ ~macOS~

??? abstract "How to: send/receive"
    === "Download"

        Download at [mugleplusplus.github.io](https://mugleplusplus.github.io/){:target="_blank"}

        [Troubleshooting](https://davidtavarez.github.io/2020/troubleshooting-mugleplusplus/)

    === "Receive"

        * Copy your address (`mugle1...`) and provide it to the other party.

        ![mugle++ receive step1](images/mugleplusplus-receive.png){ width=400 loading="lazy" }

        That's it. If both your wallets can communicate via Tor, the transaction is then completed automatically.

        *But if there's no Tor communication, next steps are:*

        * The sender will provide you a Slatepack message. Paste it into the Slatepack box and click Receive.

        ![mugle++ receive step2](images/mugleplusplus-receive2.png){ width=400 loading="lazy" }

        * Copy the Slatepack message your wallet generates.

        ![mugle++ slatepack](images/mugleplusplus-slatepack.png){ width=400 loading="lazy" }

        * Provide it to the sender.

        Done! The sender will finalize the transaction and post it to the network.

    === "Send"

        * Click send.

        ![mugle++ receive step3](images/mugleplusplus-send.png){ width=400 loading="lazy" }

        * Choose the amount of mugles.

        ![mugle++ receive step4](images/mugleplusplus-send2.png){ width=400 loading="lazy" }

        * Enter the receiver's address and send.

        ![mugle++ receive step4](images/mugleplusplus-send3.png){ width=400 loading="lazy" }

        That's it. If both your wallets can communicate via Tor, the transaction is then completed automatically.

        *But if there's no Tor communication, next steps are:*

        * Copy the Slatepack message your wallet generates and provide it to the receiver (however you want).

        ![mugle++ receive step4](images/mugleplusplus-slatepack.png){ width=400 loading="lazy" }

        * You should get a Slatepack message back from the receiver. Paste it into the Slatepack box and click Finalize.

        ![mugle++ receive step4](images/mugleplusplus-send4.png){ width=400 loading="lazy" }

        Done! Your wallet will now finalize the transaction and post it to the network.

---

[![Niffler](images/niffler.png){ align=left width=60 }](https://github.com/muglefans/Niffler){:target="_blank"}

## &emsp;Niffler

</br>
GUI wallet and node using the Rust implementation as back-end &emsp;~Windows,~ ~Linux,~ ~macOS~

??? abstract "How to: send/receive"
    === "Download"

        Download at [github.com/muglefans/niffler/releases](https://github.com/muglefans/niffler/releases){:target="_blank"}

        (by clicking on one of the listed download links)

    === "Receive"

        * Click on Receive, then Slatepack address.

        ![niffler receive step1](images/niffler-receive.png){ width=400 loading="lazy" }

        * Copy your address (`mugle1...`) and provide it to the other party.

        That's it. If both your wallets can communicate via Tor, the transaction is then completed automatically.

        * But if there's no Tor communication, next steps are:*

        * The sender will provide you a Slatepack message. Click again on Receive, then on Create response slatepack. Paste it into the Slatepack box and click Create response slatepack.

        ![niffler receive step1](images/niffler-receive2.png){ width=400 loading="lazy" }

        * Copy the new Slatepack message your wallet generates.

        ![niffler receive step1](images/niffler-slatepack.png){ width=400 loading="lazy" }

        * Provide it to the sender.

        Done! The sender will then finalize the transaction and post it to the network.


    === "Send"

        * Click on Send, then Create slatepack.

        ![niffler send step1](images/niffler-send.png){ width=400 loading="lazy" }

        * Enter the address and amount, then Create slatepack.

        ![niffler send step2](images/niffler-send2.png){ width=400 loading="lazy" }

        * Copy the Slatepack message your wallet generates and provide it to the receiver (however you want).

        ![niffler send step3](images/niffler-slatepack.png){ width=400 loading="lazy" }

        * You should get a Slatepack message back from the receiver. </br> Click on Send, then on Finalize.

        ![niffler send step4](images/niffler-send4.png){ width=400 loading="lazy" }

        * Paste the Slatepack message into the box and confirm.

        Done! Your wallet will now finalize the transaction and post it to the network.

---

[![Ironbelly](images/ironbelly.png){ align=left width=55 }](https://ironbelly.app){:target="_blank"}

## &emsp;Ironbelly

</br>
Mobile wallet &emsp;~iOS,~ ~Android~

??? abstract "How to: send/receive"
    === "Download"

        Download at [https://ironbelly.app](https://ironbelly.app/){:target="_blank"}

    === "Receive"

        Soon

    === "Send"

        Soon

---

</br>

# Related Services

[![muglenode.live](images/muglenode-live.png){ align=left width=90 }](https://muglenode.live/){:target="_blank"}

## &emsp;Muglenode.live

</br>
Public MUGLE API and sync service

---
