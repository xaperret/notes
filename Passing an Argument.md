---
date updated: '2021-10-12T17:33:06+02:00'

---

Topic: #java_programming
Tags: #review #pn_1_9
Links: [[Java]]
Date Created: 10-10-21

---

# Passing an Argument

## Passing an Argument in few words

## Passing an Argument in details

There are two ways that [[Argument]] are given to a [[Method]], they depend on what we are passing to the [[Method]].

### Passing an Argument by value

When we have [[Primitive Type in Java]], arguments are given by **value,** not by [[Reference]]. The **value** is therefore copied.
This means we can modify the [[Passing an Argument]] without fear of the original being changed.

### Argument by reference

When we are dealing with [[Reference Type in Java]], arguments are passed by **reference**, this time when we modify something the **original** is modified, **unless** the [[Object]] is [[Immutable]].
Of course, if the [[Object]] is [[Mutable]], then we can modify it as wished.

To solve this problem, we can either use `Collections` or `copyOf`.

```java
// Collections.unmodifiableCollection retourne une vue immubable sans réaliser de copie 
giveMeYourList( Collections.unmodifiableCollection(dontTouchPlease) );

// copie de la liste
giveMeYourList( List.copyOf(dontTouchPlease) );
giveMeYourList( new ArrayList<>(dontTouchPlease) );
```

```ad-warning
Adding `final` will not make the [[Object]] [[Immutable]], it will make the [[Reference Type|Reference]] [[Immutable]] which means the [[Object]] itself can still be modified !


```

### Arbitrary number of arguments

We can pass sometime an arbitrary number of arguments.

```java
public void explosions(Type... explosion) {
	for(Type exp: explosion) {
		...; // something
	}
}
```

## References

- <https://cavat.website/poo/docs/classes-and-objects/parameters-comparison/>

### Parent References
