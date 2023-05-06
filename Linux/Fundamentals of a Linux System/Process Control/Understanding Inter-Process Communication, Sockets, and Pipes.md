# Understanding Inter-Process Communication, Sockets, and Pipes
## Understanding Sockets
An essential component in the Linux OS communication between processes (IPC) is the socket. A socket is a data communications endpoint for exchanging data. Using sockets provides an alternative to using local network communication.

SOCK_STREAM (like TCP) is used if it needs to be reliable.

SOCK_DGRAM (like UDP) is used for unordered and reliable transmission of datagrams.

Processes use the filesystem to work with sockets. A socket is created as a file system inode which allows two processes to communicate using the same socket.

In networking, sockets can be compared to TC Pand UDP and the same principle is used.

## Benefits of Using Sockets
Unix domain sockets provide an easy to use interface for applications, working similar as network sockets but without the need to implement any networking.

This makes the application faster as no networking is involved, so there is less work to do.

Some applications accept remote connecitons through network sockets and local connections through Unix domain sockets.

Sockets can be listed using `lsof -U`