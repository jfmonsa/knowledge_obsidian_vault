# Testing con Jest (Nestjs)

+ Prevenir bugs en producción

## Piramide de los tests
+ Diferentes capas
![[Pasted image 20240908103402.png]]
### Unit Tests
+ Test small pieces of your app
la unidad testeada puede ser una función, una clase o un modulo, independientes unos de otros, para una entrada el test unitario comprueba el resultado. No contactan con el mundo exterior.
### Integration Tests
Comprobamos la integración de los controladores con los servicios, la integración de nuestro sistema con algo de la infraesctructura (db, archivos etc...) pueden hacer llamadas a servicios externos
### Tests e2e (pruebas funcionales)
+ test whole functionalities or use-cases
simulan condiciones reales. Se ejecutarían en un navegador (o similar) y cubren todos los sistemas funcionando juntos (frontend y backend). simulan a un usuario (escribiendo, haciendo clics, etc.)

## Herramientas de Testing
+ **Jest** - Test unitarios backend: objetos de domino, controladores y servicios
+ **Supertest** - para test de integración en backend y frontend. Permite hacer las pruebas de llamadas HTTP
+ **Cypress**: para pruebas e2e que simulen las acciones de los usuarios

ej:
```js
import {sum} from "./math.js"

test("properly adds two numbers",
	 () => {
		 //this is run when you run tests
		 expect(sum(1,2)).toBe(3)
	 }
	)
```


## Resources
+ https://ualmtorres.github.io/SeminarioTesting/ - Seminario de Testing (muy bueno)