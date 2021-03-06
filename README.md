BM-Go
=====
An implementation of the Bitmessage protocol, server and client using Go
programming language from Google.

The entire implementation is divided into 4 packages.

bitmessage
----------
The main library which provides the implementation of the protocol. It does not
interact with OS/network in any way. It is designed to be serial. Only v3 of the
protocol is supported.

middleware
----------
Designed to connect to the required network (clearnet/I2P/Tor) and manage the
SQLite file on disk, including the user's identities. Also responsible for
implementing the task queues and calling bitmessage package for doing its tasks.

daemon
------
The Bitmessage daemon designed as a thin wrapper over the middleware to manage
and configure everything through the commandline.

gui
---
The GUI meant for use by the average user, which connects the bitmessage and
middleware packages through a user friendly interface.
