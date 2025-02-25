#index
# Concepts
## Coupling

When components are tightly coupled, they have a strong dependency on each other, meaning that changes to one component may have a ripple effect on other components. This can make the system difficult to maintain, test, and extend.

> ==**Coupling** vs. **Cohesion**==
# Software Design Principles

Basic:
+ KISS: Keep It Simple Stupid Principle
+ YANGI: You ain't gonna need it Principle. never implements things before you need them.
+ [[DPP - Abstraction Principles - DRY, WET, AHA]]
+ [[DPP - SOLID]]
+ [[DPP - Inversion of Control (IoC)]], same as Dependency Inversion Principle of Solid

# Software Design Patterns (GoF)

+ general concept for solving a particular problem
+ High level description of a solution
+ a toolkit of **tried and tested solutions**

![[Pasted image 20241104211111.png]]

---
## -  [[DPP - Error and Exception - Handling]]

## - [[DPP - Dependency Injection Pattern]]
---
## Creational Design Patterns
Object Creation Mechanism
### - [[DPP- Factory Pattern]]
### - [[DPP - Singletone]]
### - Builder

## Structural Design Patterns
how to assemble objects and classes into larger structures
### - [[DPP - Data Transfer Object (DTO)]]
### - [[DPP - DAO (Data Access Object)]]
### - [[DPP - Repistory Pattern]]
### - Facade
### - Decorator

## Behavioral Design Patterns
concerned with algorithms and the assignment of responsibilities between objects.
### - [[DPP - Value Object (VO)]]
### - Strategy Pattern
### - Observable
### - Template
### - Specification Pattern
# Other Patterns
## [[DPP - BFF (Backend For Frontend)]]
# Mix Code Good Practices (Idioms)
+ Basic and low-level patterns
### Guard Clauses
+ Early return
### (Object Lookup) - Switch case with object literal

### - [[DPP - Clean Code]]
Summary of Clean Code Book
# Programming Techniques
### Reflection
+ **reflective programming** or **reflection** is the ability of a [process](https://en.wikipedia.org/wiki/Process_(computing) "Process (computing)") to examine, [introspect](https://en.wikipedia.org/wiki/Introspection_(computer_science) "Introspection (computer science)"), and modify its own structure and behavior. (process because we are talking about at runtime)
+ This includes de ability to discover information about types, methods, properties and other elements of code while the program is excecuting
+ Use to implement testing frameworks, mocks