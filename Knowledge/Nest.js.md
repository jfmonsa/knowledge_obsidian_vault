# Intro
+ Nest provides a level of abstraction above these common Node.js frameworks (Express/Fastify). But also exposes their APIS directly to the developer
+ Nest provides an out-of-the-box application architecture, heavily inspired by Angular Architecture (MVC)

## Create a Project
Use nest CLI
```bash
$ npm i -g @nestjs/cli
$ nest new project-name
```

# Architecture
+ Principios SOLID
+ Heavily tied to Dependency Injection Pattern

![[Pasted image 20240907081845.png]]

## 1. Modules
+ Is the heart of an API entity, connects controller, service and models of an API REST entity
+ Primero se debe crear el modulo antes de crear servicios o controladores, etc.
+ are used to organize related code into cohesive units
+ a way to encapsulate related components, controllers, and services within a single module

```
nest g mo users
```

+ The root module is the starting point Nest uses to build the application graph - the internal data structure Nest uses to resolve module and provider relationships and dependencies

### @Module() decorator
+ **providers** -> the providers that will be instantiated by the Nest injector and that may be shared at least across this module (services)
+ controllers
+ **imports** -> the list of imported modules that export the providers which are required in this module
+ **exports** -> the subset of `providers` that are provided by this module and should be available in other modules which import this module.
### Shared Modules
+ Every module is automatically a **shared module**. Once created it can be reused by any module
+ In order to shared a service with put it in export array of a module
### Dynamic Modules
### Resources
+ Intro to Modules
+ https://medium.com/@briankworld/creating-a-shared-module-in-nestjs-benefits-and-use-cases-6292a1dcd200 - Shared modules
## 2. Controllers
+ Controllers are responsible for handling incoming **requests** and returning **responses** to the client.
+ In order to create a basic controller, we use ==classes and decorators==. Decorators associate classes with required metadata and enable Nest to create a routing map

### Routing
+ Use `@Controller('cats')` to specify a route prefix
+  The route path for a handler is determined by concatenating the (optional) prefix declared for the controller, and any path specified in the method's decorator

```typescript

import { Controller, Get } from '@nestjs/common';

@Controller('cats')
export class CatsController {
  @Get()
  findAll(): string {
    return 'This action returns all cats';
  }
}
```

> [!HINT]
> To create a controller `$ nest g controller [name]`

### Request Object
+ use `@Req()`decorator but in most cases we can use dedicated decorators such as:
	+ `@Body()`, `@Query()`, `@Params`, `@Headers`
+ you can use `@types/express`

## 3. Services
+ usamos DTOs y class validator para validar datos

> `nest g s [name]`

Si queremos crear servicios anidados en una carpeta
> `nest g s users/services/users --flat`
+ Uses `@Injectable` Decorator

### DTO: Data Transfer Object
+ Una clase intermediaria entre los datos de la request y las entidades del backend

## 4. Providers and Dependency Injection
+ Many of the basic Nest classes may be treated as a provider – services, repositories, factories, helpers, and so on
+ The main idea of a provider is that it can be **injected** as a dependency
+ Controllers should handle HTTP requests and delegate more complex tasks to **providers**.
+ Providers are plain JavaScript classes that are declared as `providers` in a [module](https://docs.nestjs.com/modules).

## 5. Basic Setup of a project
+ configure .env
+ configure api versioning3
+ swagger documentation
+ interceptor to format api responses
	+ https://youtu.be/NhBblxY9zzo?si=Kz3mghxQ72LWczTR
	+ https://blog.stackademic.com/crafting-a-uniform-response-structure-in-nestjs-a-guide-to-mastering-interceptors-706820b5aa0b

## 6. Pipes
Transformar la data recibida en requests, para asegurar un tipo, valor o instancia de un objeto

## 7. Interceptors
### Before Interceptor
Interceptan la solicitud (request) y la pueden transformar completamente
+ Cache
+ Logs

### After Interceptor
Intercepta la respuesta que emitirá el controlador y la puede transformar completamente basado en las necesidades.
+ Alamcenar cache de la response
+ formatear la response

## 8. Guards
+ Permitir o prevenir acceso a una ruta

## 9. Exception filter
+ Maneja los errores de código en mensajes de https://youtu.be/KfvCXO3zPCk?si=ntVdEcpSFV_SlJlarespuesta http
# Recursos
+ https://youtube.com/playlist?list=PLergODdA95kfcSoXqZZ-IDImO6YaQLYlG&si=fOTcjd_e1d1sdUPB - Playlist super recomendada
+ https://youtube.com/playlist?list=PL2cV4xVnwFlmhwJwbUOchUZMJEEh_9wAQ&si=OAPcGrID0iQma_vy - Lista de reproduccion de nest
+ https://www.youtube.com/watch?v=wsqcg5ZtUMM - Curso de nest Fatz

# Websockets
+ standard that describes a way for clients and servers to exchange messages in realtime
+ The websocket server **consume events** for the client that is usign the websocket server
	+ Client **send** messages
	+ server needs to listen to those events (**Subscribe to events**)
+ Es un protocolo que esta por encima de http
## WS libraries for Javascript
+ **WebSocket** - built in to browsers (no library needed)
+ **ws** - a node package to emulate the WebSocket support for browsers but for node and usually used as a server (though it can do both)
+ **Socket.io** - a custom protocol/library on top of WebSockets for browsers and node (must be used both on client and server). also it allows you to emulate web sockets with http pooling

## Resources
1. https://hrugvedprashantchavan.medium.com/nestjs-a-guide-to-websocket-implementation-655593fc73ab
2. https://devtalles.com/files/nest-cheatsheet.pdf - Cheat sheet muy util

# Ciclo de vida nestjs
![[Pasted image 20240913094441.png]]