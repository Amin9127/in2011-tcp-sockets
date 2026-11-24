# IN2011 Computer Networks: TCP Sockets

Implementation of a client-server architecture using standard Java TCP sockets for the IN2011 Computer Networks lab coursework.

## Overview

The project demonstrates network communication over stream sockets between a client (`TCPClient`) and server (`TCPServer`):
- **Port**: `4567` (default)
- **Host**: `127.0.0.1` (localhost loopback)
- **Transport**: TCP stream sockets (`java.net.Socket`, `java.net.ServerSocket`)
- **I/O**: Character streams using `BufferedReader` and `OutputStreamWriter` with explicit flushing

## Running

1. Compile both source files:
```bash
javac TCPServer.java TCPClient.java
```

2. Start the server:
```bash
java TCPServer
```

3. In a separate terminal, run the client:
```bash
java TCPClient
```

## Protocol Flow

1. Server opens `ServerSocket(4567)` and listens for incoming connections.
2. Client creates `Socket("127.0.0.1", 4567)` to initiate handshake.
3. Client sends `"Hello Server!\n"` and flushes the writer.
4. Server reads the request, prints it, and responds with `"Nice to meet you\n"`.
5. Client prints server response and closes connection.
