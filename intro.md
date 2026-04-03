## What are APIs ?

- API stands for: Application Programming Interfaces, provide a manner in which they communicate to each other.

- It abstracts the complexity of the software Application.

- They define methods and data formats of an application should use in order to perform task. (CRUD)

## HTTP in API design

- HTTP is the fundamental piece of of an API design.

- HTTP is curcial for API design as it provides the structure of request and response should be constructed and handled.

- A solid Understanding of HTTP principles allows for more robust, efficient and secure API design.

## HTTP Versions

- HTTP Versions specify how data should be packaged and transported, as well as how web servers and browsers should responed to commands.

- From HTTP/1.0, the initial version of HTTP to HTTP/2 and the latest version HTTP/3, each version brings in improvements in speed, data transmission capabilities, and security.

## HTTP: 1.0 VS 2.0 VS 3.0

### Introduction

- Networks typically consider the OSI models. These model contemplate different layers like network, transport and application layer.

- Each network layer has particular protocols that implement a myriad(countless) functionalities. Eg: IP at the network layer, TCP and UDP at transport layer and HTTP at application layer.

- These protocols evolve, thus being updated and extended over a peroid of time. So, it's a natural that these protocols have mulitple Versions.

### Application Layer Protocols

- It's the 7th layer of OSI models and 4th layer of TCP/IP model. In pratice the application layer is the closest layer to the user.

- There are three principles architectures employed to build application-layer systems:
  1. client-server: The main characteristic of the client-server architectures is to have a mulitple client requesting and receiving services from the centralized server.

  2. peer-to-peer: The peer-to-peer architectures is to have a mulitple independent computers connected in the network that collaborate to excute an operation.

  3. Hybrid: An architectures that employs both server and peers to execute operations.

- Application protocols assums the other layers tackle the communication with the correct destination computer connected to the network.

- Example of some application layer protocols: HTTP, FTP, POP, DNS etc.

### HTTP

- HTTP is an application protocol (7th layer of OSI model and 4th layer of TCP/IP model) employed to create distrubted hypermedia systems.

- HTTP relies on TCP/IP to work. IT means the HTTP is a connection based protocols.

- HTTP has been used on the internet since '90s'. The first release of HTTP (0.g) was much limited. This version only enable client to request information from a server using a single operation. GET

- The first HTTP release only supported transmitting ASCII data. However, in the following releases this support expanded to other data types.

### HTTP V-1.0

The first version of HTTP only allowed getting information from a server. However it became insufficient as the internet evolved and new functionalities arose.

In this context, version 1.0 of HTTP was released 1996 about five years after version 0.g:

Version 1.0 of HTTP brings several new utilities. Let’s see some of them:

1. Header: only the method and the resource name composed an HTTP 0.9 request. HTTP 1.0, in turn, introduced the HTTP header, thus allowing the transmission of metadata that made the protocol flexible and extensible

2. Versioning: the HTTP requests explicitly informs the employed version, appending it in the request line

3. Status code: HTTP responses now contain a status code, thus enabling the receiver to check the request processing status (successful or failed)

4. Content-type: thanks to the HTTP header, in specific to the Content-Type field, HTTP can transmit other documents types than a plain HTML file

5. New methods: besides GET, HTTP 1.0 provides two new methods (POST and HEAD)

- In summary, HTTP Version 1.0 is more robust than 0.g.

### HTTP V-1.1

This version(V-1.1) release only after one year of the previous release V-1.0

Version 1.1 of HTTP brings several new utilities.

1. Host Header: The host header is specially important to route messages through proxy servers, allowing to distinguish domains that point to the same IP.

2. Persistent Connections: In HTTP 1.0 each request/response pair requires opening a new connection. In HTTP 1.1, it's possible to execute several requests using a single connection.

3. Continue Status: To avoid servers refusing unprocessing requests. Now client can first send only the request headers and check if they recieve a continue status code (100)

4. New Methods: PUT, DELETE, PATCH, CONNECT, TRACE and OPTIONS are added.

- In additional to the highlighted enhancements, such as compression and decompression, multi-language support, and byte-range transfers.

### HTTP V-2.0

This version was released in 2015.

This version implement several features to improve connection and data exchange. These are:

1. Request multiplexing:
   - HTTP V-1.1 is a sequential protocol. So, we can send a single request at a time.

   - HTTP V-2.0 allows a mulitple request at a same time with single connection.

2. Request prioritization:
   - In this version, we can set a numeric prioritization in a batch of requests.

   - Thus, we can be explicit in which order we expect the response, such as getting a css file before js file.

3. Automatic compressing:
   - In the previous versions, we have to explicitly require a compression in request/response.

   - However, in this version executes a GZip compression automatically.

4. Connection reset:
   - A functionality allows closing a connection between a server and a client for some reasons, thus immediately opening a new one.

5. Server-Push:
   - To avoid a server receiving lots of requests. HTTP V-2.0 introduced a server-push functionality.

   - The server tries to predic the resources that will be requested soon. So, the server proactively pushes these resources to the client cache.

- In Summary:
  - We can see HTTP 2.0 as a patch of enhancements to solve the problems and limitations of previous version.

### HTTP V-3.0

- The first draft of this version was released in 2020.

- The main difference between the current and previous versions is the transport layer.

- we have TCP connections with or not TLS (HTTPS and HTTP). HTTP 3.0, in turn, is designed over QUIC (Quick UDP Internet Connections).

- QUIC, in short, is a transport layer protocol with native multiplexing and built-in encryption.

- HTTP 3.0 is that it always creates encrypted connections.
