# Overview

Turms is a French communications software. It can be used centrally, using the
network provided by Gravitalia, or decentrally, hosting its own instance.

Turms is based on
[WebRTC](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API), a
real-time communication technology available on browsers and mobiles. Turms
implements its own discovery server, enabling peer discovery on a decentralized
network. It also acts as a storage-and-transmission server. The discovery server
does not prevent communication with peers outside the server, and does not
change the principle of end-to-end encrypted peer-to-peer communication.

Turms integrates various services that work together, even if they come from
external networks:

- [**discovery**](https://github.com/TurmsApp/discovery): peer discovery
  service. As a peer manager, it enables public discovery (a list of all peers)
  or private discovery (you need to enter the entire identifier), which it
  distributes via an HTTP API. As a storage-and-transmission server, it
  temporarily stores, in encrypted form, messages that could not be delivered
  to the peer using Postgres.

- [**turn**](https://github.com/TurmsApp/turn): high-performance and secure
  relay server (TURN), thanks to Rust. Any TURN server -- even those provided
  for free by Cloudflare -- will do. However, Turms Turn integrates its own
  authentication features, such as JWT management. This prevents unwanted use
  when the server is public.

- [**sync**](https://github.com/TurmsApp/sync): Software not yet ready.
  This software will enable keys to be transferred securely between different
  devices. It will be directly integrated into desktop and mobile applications,
  enabling keys and messages already created/sent to be exchanged with just a
  few clicks. It is also intended to be a self-hosting service for storing keys
  in the cloud.

Gravitalia provides these services free of charge. A Gravitalia account gives
you free, secure access to Turms. However, it may be preferable to self-host
services for greater confidentiality. Turms lets you do away with the rest of
the centralization (discovery server and relay server), giving you the option
of self-hosting them. Messages are always sent without an intermediary server;
peer-to-peer. The only exceptions are: if the peer is not connected, if you
(or the peer) are using a firewall.

Because of these key services and principles, this makes it one of the most
secure messaging services, beyond Telegram and Signal.
