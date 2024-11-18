Web communication method that use http requests to perform CRUD operations on resources and its base on stateless communication between client and server usign standard http methods like: GET, POST, PUT and DELETE

+ **API**: Application Programming Interface
+ **REST**: Representational State Transfer, Estilo de arquitectura de software
+ client / server model thought HTTP 
+ That means that they follow the Representational State Transfer guide
+ Coined in Roy Fielding's 2000 PhD dissertion
+ organizes API entities or resources into unique (URIs)

# HTTP
+ Internet protocol
+ define the mechanism through clients and servers can share resources

![[Pasted image 20240912143633.png]]
## Parts of HTTP Request / Response

### Headers
+ Metadata of the request
+ Define media type
+ Define http verb
### Body, params, query
+ Contains custom payload of data
## HTTP verbs / methods
+ GET
+ POST
+ PATCH
+ DELETE
Other:
+ PUT
+ HEAD
## Media Type
+ Formato especifico que tiene una representación de un recurso
+ Mecanismo a través del cual se comunican clientes y servidores sobre como entender la representación de un recurso

# Recurso
+ Cualquier cosa que tiene un URI asignado
+ Puede ser: un archivo, una impresora, un dispositivo

# Representación
+ Es una fotografía del estado de un recurso

# API REST restrictions
+ Clientes (consumidores) están desacoplados del servidor (proveedor) permitiendo su evolución independiente
+ toda información dentro de la solicitud debe ser cacheable
+ solo se emplea HTTP
## Stateless
+ An important part of that architecture is that it is stateless, which means that the two parts (client and server) doesn't have to store any information about each other and every request / response cicle is independent from each communication
+ API no tiene estado, cualquier requerimiento de conservación de estado deber ser gestionado por el cliente y enviado al proveedor


# Versioning API Rest
+ Problemas aparecen tras desplegar la primera versión
+ Es muy común romper la compatibilidad con los clientes
+ El cambio es inevitable
+ Tenemos que pensar y diseñar nuestras Web API para que se puedan adaptar al cambio con el paso del tiempo
![[Pasted image 20240814220812.png]]
![[Pasted image 20240814220943.png]]

