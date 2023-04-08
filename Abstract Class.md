---
date updated: 2021-11-20 12:21
sr-due: 2021-12-06
sr-interval: 11
sr-ease: 263
---

Topic: #oop #java_programming
Tags: #review #pn_2_1
Links: [[Class  Visibility]] [[Class]]
Date Created: 23-10-21

---

# Abstract Class

## Abstract Class in few words

```java
abstract-keyword class-keyword class-name {
	...
}
```

```java
abstract class AnAbstractClass {
	...
}
```

## Abstract Class in details

[[Abstract Class|Abstract Classes]] are another tool in the tool box to achieve [[Abstraction]].

It can have:

- [[Abstract Method]]
- Concrete [[Method]]

**Like** [[Interfaces in Java]] they cannot be [[Instantiation|instantiated]].
**Contrary** to [[Interfaces in Java]] they can contain [[Field|fields]], therefore can **describe change of state** and be used [[Constructor]] to be used for [[Subclass]].
**Contrary** to [[Interfaces in Java]] they cannot be [[Inheritance|inherrited]] multiple times meaning this is wrong

```java
class E extends A,B,C,D { // this is impossible
	...
}
```

**Like** [[Interfaces in Java]] a [[Class]] that [[Inheritance|inherits]] from an [[Abstract Class]] must redefine [[Abstract Method]] in order to be a concrete [[Class]] and therefore be [[Instantiation|instantiable]].
An [[Abstract Class]] doesn't need to have [[Abstract Method]].

### In Practice

If `abstract` is used then the [[Class]] cannot be [[Instantiation|instantiated]] but [[Subclass|Sub-Classes]] can be [[Instantiation|instantiated]].

```java
jshell> abstract public class Fruit {
   ...>     public Fruit() {}}
|  modified class Fruit

jshell> Fruit banana = new Fruit();
|  Error:
|  Fruit is abstract; cannot be instantiated
|  Fruit banana = new Fruit();
|                 ^---------^

jshell> public class Banana extends Fruit {
   ...> }
|  created class Banana

jshell> Banana bigBanana = new Banana();
bigBanana ==> Banana@27bc2616

jshell> 
```

## References

- [[Class#References]]
