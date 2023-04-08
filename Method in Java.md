---
date updated: 2021-11-25 10:44
---

Topic:
Tags: #review #pn_2_1
Links:
Date Created: 25-11-21

---

# Method in Java

## Method in Java in few words

## Method in Java in details

Method is something that brings functionality. In [[Object-Oriented Programming]] it can either be attached to an [[Object]], in which case it is an _[[Object]] [[Method]]_ or to a _[[Type]]/[[Class]][^1]_, in which case it is a [[Static Method]].

```java
public class Car {
	private int fuelLevel;
	private String carColor;
	
	public boolean isReservoirEmpty() {
		return fuelLevel == 0;
	}
	
	public static Car makeCarWithColor(String color) {
		if(color.equals("")) {
			throw ...
		}
	
		return new Car(color);
	}
	
	private Car(String carColor) {
		this.fuelLevel = 0;
		this.carColor = carColor;
	}
}
```

In this example, we can

```java
Car redCar = Car.makeCarWithColor("red"); // use of static method
if(redCar.isReservoirEmpty) { // use of a field method
	System.out.println("Damn we can't drive, we don't have fuel:(");
} else {
	System.out.println("Let's go for a drive");
}
```

## References

- <https://cavat.website/poo/docs/poo-basics/poo-intro/>
