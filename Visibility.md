---
date updated: 2021-10-24 15:21

---

Topic: #oop #java_programming
Tags: #review #pn_2_1
Links: [[Java]]
Date Created: 11-10-21

---

# Visibility

## Visibility in few words

## Visibility in details

We can add to any property a keyword to set its [[Visibility]] or [[Scoping]], with a [[Scope]] of `public` a [[Field]] can be accessible outside its [[Class]] or [[Object]].
By opposition to `private` who makes the property only available to its own [[Class]].

```java
public class Fruit {
	private String color;
	
	public static boolean isSameColor(Fruit f) {
		... // access f.color
	}
}

Fruit f1 = new Fruit("red");
Fruit f2 = new Fruit("white");
f1.isSameColor(f2); // is possible since they are the same class

```

| modifier                | Class | Sub-Class | Package | Outside |
| ----------------------- | ----- | --------- | ------- | ------- |
| private[^1]             | Yes   | No        | No      | No      |
| protected               | Yes   | Yes       | No      | No      |
| not mentioned (package) | Yes   | Yes       | Yes     | No      |
| public                  | Yes   | No        | No      | No      |

```ad-tip

Private should be the default scope ! Indeed one of the [[Object-Oriented Programming Principles]] is all about hiding the implementation, i.e. [[Encapsulation]] !

```

## References

- <https://cavat.website/poo/docs/classes-and-objects/class-creation/>
- <https://cavat.website/poo/tech/syntaxe/interm/>
- [[@nobackObjectDesignStyle2020]] p.5

[^1]: This also means that two object of the same [[Class]] can access each other `private` [[Member]]
