---
date updated: 2021-11-09 11:24
sr-due: 2021-12-02
sr-interval: 23
sr-ease: 262
tags:
  - '#oop'
  - '#java_programming'
  - '#review'
  - '#pn_1_9'
---

Topic: #oop #java_programming
Tags: #review #pn_1_9
Links: [[Java]] [[Object-Oriented Programming]]
Date Created: 12-10-21

---

# Constructor

## Constructor in few words

```java
scope ClassName(listOfArgs) throw-clause {
	Constructor-body
}
```

## Constructor in details

A [[Constructor]] has the same name as the [[Class]] it _works_ for.
The [[Constructor]] is inside the **block** `{...}` of the [[Class]] as it is one of the [[Class]] [[Member]].
The **purpose** of a [[Constructor]] is to [[Instantiation|instantiate]] a new [[Object]], by eventually giving _values_ to the [[Field]] and doing the necessary operation required by the programmer.

```java
public class Counter {
    private int counter;
    public Counter() {
        this.counter = 0; // initiating Field counter to 0
    }
```

It's possible to **throw an [[Exception]]** inside the constructor to **prevent** a **wrongful instantiation**, but it is advised to use a [[Factory]] instead.

```ad-caution

A [[Constructor]] cannot be `abstract`, `final`, `static` and it has no return type.

```

A [[Constructor]] can be [[Overload|overloaded]] and therefore can call its overridden version with `this(listOfArgs)`, but it **can't call itself**.

## References

- <https://cavat.website/poo/docs/classes-and-objects/class-creation/#constructeurs>
- [[@sestoftJavaPrecisely2016]] p. 30-32,
- [[@blochEffectiveJava2017]] p. 5
