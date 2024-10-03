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