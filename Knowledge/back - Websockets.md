# Websockets
+ standard that describes a way for clients and servers to exchange messages in realtime
+ provides bi-directional communication between server and client with the usage of a single long-lasting [TCP connection](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)
+ Layer 7 (OSI)
+ not protected by same-origin policy
+ The websocket server **consume events** for the client that is usign the websocket server
	+ Client **send** messages
	+ server needs to listen to those events (**Subscribe to events**)
+ Es un protocolo que esta por encima de http
## Concepts
+ **WebSocket** - is a protocol that depends on TCP protocol (like HTTP)
+ **ws** - a node package to emulate the WebSocket support for browsers but for node and usually used as a server (though it can do both)
+ **Socket.IO** - is a library (built on top of WebSocket protocol), (must be used both on client and server). ==Recommended==
---
Other:
+ **Socket** - is an endpoint (in a socket communication)
+ **Webhook** - is an HTTP-based callback function which allows one way, server to server communication (not related to WebSockets and not concerned in this tutorial series)

## Socket IO
+ You need to use it in browser and server
+ You have to set CORS since its a custom protocol built on top of WebSockets protocol
---
+ Rooms and namespaces are created on the server side

![[Pasted image 20241009083042.png]]

### Rooms
![[Pasted image 20241009081437.png]]
+ is an arbitrary channel that sockets can `join` and `leave`. It can be used to broadcast events to a subset of clients
+ By default socket.io joins you to a room with your `socket.id`
+ It's quite useful using rooms instead you implementing your own mechanism e.g. throught HashMaps
+ When a socket disconnects the socket leave all rooms in the server automatically 
### namespaces
![[Pasted image 20241009081723.png]]
+ A Namespace is a communication channel that allows you to split the logic of your application over a single shared connection (also called "multiplexing")
+ Possible use-cases
	+ you want to create a special namespace that only authorized users have access to, so the logic related to those users is separated from the rest of the application
	+ your application has multiple tenants so you want to dynamically create one namespace per tenant
## Resources
+ https://socket.io/docs/v3/emit-cheatsheet/
+ https://socket.io/docs/v3/rooms/