---
date updated: 2021-10-26 11:23
---

Topic: #oop #java_programming
Tags: #review #pn_2_1
Links: [[Polymorphism]]
Date Created: 12-10-21

---

# Subtyping Polymorphism

## Subtyping Polymorphism in few words

## Subtyping Polymorphism in details

A form of [[Polymorphism]] is [[Subtyping Polymorphism|subtyping]]. The way [[Polymorphism]] is achieved here is by using [[Subtype]] or [[Subclass]] to **substitute** a [[Superclass]].
It is therefore intimately linked to [[Inheritance]]. Another way to achieve [[Subtyping Polymorphism]] is to use [[Interfaces in Java]].

If [[Class]] `B` inherits from `A`, it is a [[Subtype]].
Therefore, if we have a [[Reference]] which wants [[Type]] `A` we can **substitute ** `B` for `A`.

Let's recall [[Class Object]] and try this in an example

```java
Object o = new Object();
o.toString(); // ==>"java.lang.Object@27fa135a"

o = new Counter.withValue(42); // since o is the super class for
// counter and subtyping polymorphism is a thing
// it works !
o.toString(); // ==> Counter(0042)

o = List.of(1,2,3);
o.toString(); // ==> [1,2,3]
```

```ad-important

`o`, [[Reference Type]] will stay the same, it is still an [[Class Object]] even after assigning it to our `Counter` [[Object]].

```

`o` will **NOT** have access to the [[Method]] of the [[Object]] it references, but it will have access to the list of **[[Method|methods]]** contained in the [[Superclass]].
Therefore, if we are going to use one of those [[Method|methods]] the [[Compiler]] will first look into the [[Superclass]] [[Method|methods]] list. Then it will call the right [[Method]] of the [[Subtype]].
This means it will call either the [[Method]] of the [[Superclass]] or the [[Override|overridden]] [[Method]] found in the [[Subclass]].
If we have a [[Method]] that accepts `int` in the [[Subtype]] but the [[Superclass]] only accepts `short` it will be impossible to use this [[Method]].

![[Pasted image 20211012192305.png]]

This means in our case we have access to the

- `toString()`
- `hashCode`
- `equals`

```java
public class Food {
	private String color;
	private int length;
	private int width;
	private int weight;

	public void eat(short w) {
		if(weight - w >= 0) {
			this.weight -= w;
		}
	}
}

public class Fruit extends {
	...

	@override // redefinition => same signature, different behaviour
	public void eat(short w) {
		if(weight - w >= 0) {
			this.weight -= w;
			System.out.println("amazin")		}
	}

	@overload // over load => changing type / adding type
	public void eat(int w) {
		if(weight - w >= 0) {
			this.weight -= w;
		}
	}
}
```

## References

- <https://cavat.website/poo/docs/classes-and-objects/object/#signification-de-lh%c3%a9ritage>
