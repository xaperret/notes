---
date updated: 2021-11-01 12:28
---

Topic: #java_programming #oop
Tags: #review #pn_1_9
Links: [[Java]] [[Object-Oriented Programming]]
Date Created: 11-10-21

---

# Inheritance

## Inheritance in few words

```java
class A {}
class B extends A {}
```

[[Class]] `B` is a [[Class]] `A`. It is a _specialized_

## Inheritance in details

[[Inheritance]] is a way of giving to another [[Class]] which we call [[Subclass]]the functionalities of one [[Method]] which we call [[Superclass]].
In other words, the [[Subclass]] (or [[Subclass|Childclass]]) **inherits** from a [[Superclass]] or [[Superclass|parent class]].
The elements that **inherited** are the [[Member|members]] that are not `private`[^1].
It is what allows us to do **code reuse** and [[Polymorphism]].

There are two ways of doing [[Inheritance]][^2]
- By **behavior**, using [[Interfaces in Java]]
- By **structure**, using [[Class to Class Inheritance]]

Let's take an example

```java
class A {}
class B extends A {}
class C extends A {}
class E extends A {} 
class Z {
	public void f(B b) { System.out.println("B"); }
	public void f(C c) { System.out.println("C"); }
	public void f(E e) { System.out.println("E"); }
}
```

Let's look specifically at [[Class]] `A` and `B`.

- [[Class]] `B` **inherits** from `A`
- Since `B` can't [[Override]] `A`'s [[Method]] in a way that would hide them, they are as **exposed** as in `A`.
- Our [[Subclass]] `B` can expose **more functionalities**, therefore **specializes** itself.

````ad-question

What is wrong and what is correct here ?

```java
Z z = new Z();
z.f(new A());
z.f(new B());
z.f(new C());
z.f(new D());
z.f("COUCOU");
````

````ad-info
title: Answers
collapse: closed

```java
Z z = new Z(); // ok
z.f(new A()); // pas ok
z.f(new B()); // ok
z.f(new C()); // ok
z.f(new D()); // pas ok
z.f("COUCOU"); // pas ok
````

### Class `Object`

The [[Class Object]] is the _biggest_ [[Superclass]] there is in [[Java]].

![[Pasted image 20211012180148.png]]

## References

- [[Subclass]]
- <https://cavat.website/poo/docs/classes-and-objects/object/>
- [[@blochEffectiveJava2017]] p. 87

### Parent References

- [[Java#References]]
- [[Object-Oriented Programming#References]]

[^1]: [[Visibility]]

[^2]: https://cavat.website/poo/docs/polymorphism/extensibility/#conclusion
