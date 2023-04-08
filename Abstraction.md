---
date updated: 2021-10-27 11:43

---

Topic: #oop #java_programming
Tags: #review #pn_2_1
Links: [[Java]] [[Object-Oriented Programming]]
Date Created: 17-10-21

---

# Abstraction

## Abstraction in few words

## Abstraction in details

> A good architecture allows major decisions to be deferred
> (Robert C. Martin, Clean Code)

In Java, stuff like [[Interfaces in Java]] are very good at providing a higher level of [[Abstraction]].

A good example of the usefulness of [[Abstraction]] in [[Object-Oriented Programming]] is the [[Collections in Java]] and [[Generics]] `List`

```java
List<Integer> is = new ArrayList<>();
// List is an interface
// ArrayList is a class
```

In the [[Class]] hierarchy it sits
![[Pasted image 20211017122503.png]]

So this means we can create a [[Method]] that expects an [[Object]] `List` of a certain [[Type]] and we could give it both `ArrayList` and `LinkedList` without problems !

### Interface vs Class

Prefer [[Inheritance]] of [[Interfaces in Java]] over [[Class]].

## References

- <https://cavat.website/poo/docs/polymorphism/abstraction/>
