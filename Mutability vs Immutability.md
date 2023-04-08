---
date updated: '2021-10-02T11:49:39+02:00'

---

Topic: #oop
Tags: #review #pn_1_6
Links: [[Object-Oriented Programming in Practice]] [[Object-Oriented Programming]]
Date Created: 02-10-21

---

# Mutability vs Immutability

## 📋 Mutability vs Immutability

## 🗂️ Mutability vs Immutability

### The problem of mutability

Sometimes, when you badly design something, you can step in some **undesirable** [[State]].
The best example is the class `Date` in Java, which allows you to modify the object itself. Indeed, you can delete or modify dates.
This is a **dumb implementation**, for multiple reason. First, dates don't change, so to be able to say February 3rd doesn't exist will create bad consequences.
Second, every modification will result in **undesirable** [[State]] which we said that we **NEVER WANT TO BE IN**[^1].

A good library here uses [[Object]] that are **immutable**, if you change the date, a new object will be created, so only the **reference** will change.
Good examples of library that are immutable in [[Java]] :

- `LocalDate`
- `String`
  - Object instantiation by using [[Implicit Conversion]] thanks to [[autoboxing]]
  ```java
  String s = "bim bam boum"; // => this is autoboxing
  ```

### String

Therefore, when we want to concatenate two string we can do

```java
String s1 = "bim"; // autoboxing
String s2 = "bam"; // autoboxing 
String str = ""; // ... you get it now

str = s1 + s2; // the object at line 3 is still in the heap
// but str does not reference it, a new object combining s1 and s2 has been inst.
// the old object will be garbage collected since it is not referenced by any
// thing in the stack
```

![[Pasted image 20211002114934.png]]

## 🗄️ References

- [Mutability & Immutability](https://web.mit.edu/6.005/www/fa15/classes/09-immutability/)
- [[Object-Oriented Programming#References]]
- <https://cavat.website/poo/docs/poo-basics/poo-by-use/>

[^1]: [[Object Paradigm#Changement d'état]]
