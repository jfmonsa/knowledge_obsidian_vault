# SOLID
+ The Foundation of Robust Software
+ by Robert C. Martin

## Single Responsability Principle (SRP)
a class or module should have one, and only one, reason to change. This promotes focused, cohesive units of code.

### Concerns
+ A class can have multiple methods, as long as they collectively serve a single responsibility
### Problems when SRP violation
+ **Tight Coupling**: functionalities are intertwined, making changes to one aspect likely to ripple through the entire service
+ **Reduced Testability**: Writing comprehensive unit tests for this monolith becomes incredibly complicated. You’d need to mock or set up the database, cache, mailer, etc., even for simple authentication logic tests.
+ **Poor Maintainability:** Understanding this super-service requires keeping a vast array of concerns in your head at once.
## Open/Closed Principle (OCP)
Software should be open for extension but closed for modification. This means your code can be easily extended with new functionalities without having to rewrite existing logic
+ SRP plays a crucial role here, as loosely coupled, well-defined services become easier to extend.

## Liskov Substitution Principle (LSP)
Subtypes should be substitutable for their base types without altering the program’s correctness. SRP helps ensure that your services have clear responsibilities, making it more likely that subclasses can safely inherit their behavior.

## Interface Segregation Principle (ISP)
Clients shouldn’t be forced to depend on methods they don’t use. SRP aligns well with ISP, as it encourages focused services with well-defined interfaces. Clients only interact with the functionalities they need.


## Dependency Inversion Principle (DIP)
High-level modules should not depend on low-level modules. Both should depend on abstractions (interfaces). SRP promotes loosely coupled services, making it easier to implement abstractions and adhere to DIP.
## Resources
+ https://medium.com/@muhammadhaggy/solid-in-nest-js-deep-dive-into-single-responsibility-principle-6f2e3d936088 SOLID in NEST JS: Deep Dive into Single Responsibility Principle