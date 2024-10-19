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