---
date created: Monday, December 20th 2021, 3:27:48 pm
date modified: Sunday, January 16th 2022, 4:59:18 pm
tags: [review, pn_2_1]
---

- Topic:
- Tags: #review #pn_2_1
- Links: 
	- [[Variance]]
	- [[Variance in Java]]
- Date Created: 20-12-21

---

# COVARIANCE

## COVARIANCE IN FEW WORDS

Is a way to substitute a type by its [[Subtype]].

To make something **covariant**, one must use the syntax `<? extends supertype>`, like so :

```java
boolean addAll(Collection<? extends E> c) { ... } // this allows us to have covariance
```

This means that something like this :

```java
List<Integer> ints = List.of(1,2,3);
List<Number> arguments = ints; // does not work
```

That doesn't work, because Integer is a **subtype** of Number **but** [[Generics in Java]] are [[Invariance|invariant]], meaning we **must** give it a **Number** if it wants a **Number**.

Fortunately for us, we know [[Covariance]], which means we can do

```java
boolean addAll(Collection<? extends E> c) { ... }
```

Which makes the method **variant**, meaning this become possible

```java
List<Number> numbers = new ArrayList<>();
numbers.addAll(arguments);
```

![[Pasted image 20211220184721.png]]

## COVARIANCE IN DETAILS

## REFERENCES

- https://cavat.website/poo/docs/variance/
