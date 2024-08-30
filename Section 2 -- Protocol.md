# Protocol

Protocols ensure the security of platform transmissions, and in a peer-to-peer
network like Turms, they are essential.

We're not reinventing the wheel, and the **Signal protocol**
([SignalApp/libsignal](https://github.com/signalapp/libsignal)) is perfectly
suited to our requirements. This means that the following elements must be
implemented in the software:

1. **X3DH** (Extended Triple Diffie-Hellman): used to exchange keys securely.
