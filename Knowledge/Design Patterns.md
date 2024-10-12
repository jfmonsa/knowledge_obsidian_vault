# Premature Optimization
> I truly do believe that premature optimization is the root of all evils - Donald Knuth

Tradeoff triangle:
![[Pasted image 20241005140332.png]]

+ **Velocity**: How fast a new feature is added
	+ If you go only for velocity, you will created a lot of techical debt (eg.:not following SOLID)
+ **Adaptability**: How well the system can change to new , reusable, extensible components
+ **Peformance**
	+ Macro performance: At design level
	+ Micro performance: at a module or function
---
+ where to focus depends on the stage of your project
+ For performance issues:
	+ Measure
	+ Try something ,analysis of: 
		+ ==data structures==
		+ Profiling
		+ Think about how your code works under the hood
		+ think about memory: allocating memory

## Resources
+ https://youtu.be/tKbV6BpH-C8?si=AU9Nqp8TskevQpaI  - Premature Optimization
# DRY
# Guard Clauses
+ Early return
# Switch case with object literal
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
# Singletone
# Factory Method Pattern
+ Creational Pattern -> allow us create objects
+ Provides an interface for creating objects in a superclass but allow subclasses to alter the type of objects that will be created
+ the subclasses are the ones that actually define how those objects are instaciated

```java
VehicleFactory carFactory = new CarFactory();
VehicleFactory truckFactory = new TruckFactory();
VehicleFactory bikeFactory = new BikeFactory();

Vehicle myCar = carFactory.createVehicle();
Vehicle myTruck = truckFactory.createVehicle();
Vehicle myBike = bikeFactory.createVehicle();

myCar.getType(); // "Car"
myTruck.getType(); // "Truck"
myBike.getType(); // "Bike"
```

+ https://youtu.be/phTXrJqRgnI?si=l7-k1eKoL68ZQ425 - Neetcode Factory Method Design Pattern 
# Dependency Injection
+ It Means: Giving an object its instance variables
+ **Dependencies:** Are objects which specific class depends on

## Real Life Example:

If you have a computer: its CPU, HDD, Memory, and Graphics cards are its dependencies

![[Pasted image 20240830171738.png]]

## Constructor Injection
+ We pass the objects in the constructor
+ Allow us to give each computer instance different components
```java
class Computer(
	private val processor: Processor,
	private val ram: RAM,
	private val hardDrive: HardDrive,
	private val graphicsCard: GraphicsCard
){
// implementation
}
```

## Use Cases
1. To create transactions, passing db object as a dependency injection