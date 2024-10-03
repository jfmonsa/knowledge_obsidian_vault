
# MVC

+ 3 capas express, como ya lo vengo trabajando
+ http layer: controller + route; BL layer: services y data access layer: models, entities o repositories
# Hexagonal
+ **Infraestructura**: BD connection, axios calls
+ **Aplicación**: Casos de uso
+ **Domain**: Modelos o entidades

![[Pasted image 20240929172057.png]]

Combinandolo un poco con las arquitecturas clean
+ Regla de dependencias

---
Terminología extra:
+ puerto = repositorie
+ service functions = adapters
## Resources
+ https://www.youtube.com/watch?v=bdnpXzgj1oY&list=TLPQMjkwOTIwMjQIVCpNRnssjQ&index=1&pp=gAQBiAQB Clean Architecture and Hexagonal
# DDD - Domain Driven Design

# Clean Architectures

+ Separan el dominio (BL) de la infraestructura
+ Pasamos de estar acoplados a ser independientes del framework, de la libreria, de la ui
+ Mejor escalabilidad
![[Pasted image 20240929173919.png]]
![[Pasted image 20240929174027.png]]

## Resources
+ https://youtu.be/1OLSE6tX71Y?si=j0Z5GfdJeA3VN-cG - Understand Clean Architecture in 7 Minutes

