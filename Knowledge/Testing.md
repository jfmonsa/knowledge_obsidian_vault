# Testing con Jest (Nestjs)

+ Prevenir bugs en producción
+ test unitarios y de Integración, de controladores y servicios en una API REST

## Piramide de los tests

+ Diferentes niveles o capas de testing
+ **Test unitarios**: la unidad testeada puede ser una función, una clase o un modulo, independientes unos de otros, para una entrada el test unitario comprueba el resultado. No contactan con el mundo exterior.
+ **Test de Integración**: Comprobamos la integración de los controladores con los servicios, la integración de nuestro sistema con algo de la infraesctructura (db, archivos etc...) pueden hacer llamadas a servicios externos
+ **Tests e2e (pruebas funcionales)** simulan condiciones reales. Se ejecutarían en un navegador (o similar) y cubren todos los sistemas funcionando juntos (frontend y backend). simulan a un usuario (escribiendo, haciendo clics, etc.)

![[Pasted image 20240908103402.png]]

## Herramientas de Testing
+ Jest - Test unitarios backend: objetos de domino, controladores y servicios
+ Supertest - para test de integración en backend y frontend. Permite hacer las pruebas de llamadas HTTP
+ Cypress: para pruebas e2e que simulen las acciones de los usuarios

## Resources
+ https://ualmtorres.github.io/SeminarioTesting/ - Seminario de Testing (muy bueno)