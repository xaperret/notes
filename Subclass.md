---
date updated: '2021-10-12T14:36:59+02:00'

---

Topic: #oop  #java_programming
Tags: #review #pn_2
Links: [[Class]] [[Inheritance]]
Date Created: 12-10-21

---

# Subclass

## Subclass in few words

## Subclass in details

A [[Class]] `banana` might [[Declaration|declared]] a [[Subclass]] of [[Class]] `fruit` by what is called an _extends-clause_.

```java
class banana extends fruit {...}
```

The [[Subclass]] inherits of all [[Method|methods]] and [[Field|fields]] event `private` ones, although they are not accessible within [[Class]] `banana`. This is possible thanks to [[Inheritance]].

[[Class]] `fruit`is called **the immediate [[Superclass]]** of [[Class]] `banana`. A [[Class]] can only have **one**.

### Constructor in Subclass

A [[Constructor]] in a [[Subclass]] might want to call the [[Superclass]]' [[Constructor]], if it does, it should be the first things done before doing anything else.

```java
super(...); // or o.super(...); if `fruit was an inner class`
```

By **default**, if `super` is not called, it will call the **default [[Constructor]]** of `fruit`.

So `super` can be used to call another [[Constructor]] of `fruit`.

## References

### Direct References

- [[@sestoftJavaPrecisely2016]] p. 24

### Parent References
