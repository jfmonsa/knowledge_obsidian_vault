
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