---
date updated: '2021-10-10T22:42:02+02:00'

---

Topic: #oop #java_programming 
Tags: #review #pn_1_9
Links: [[Object-Oriented Programming]]
Date Created: 10-10-21

---

# Object-Oriented Programming in Practice

## Object-Oriented Programming in Practice in few words

## Object-Oriented Programming in Practice in details

![[Pasted image 20210926220836.png]]

As we can see, the [[Stack]] contains [[Reference]] and the [[Heap]] the [[Object]].

![[Pasted image 20210926221244.png]]

Functionalities are brought by [[Method]], these methods can be linked to an [[Object]] or a **type** or [[Class]] or independent thanks to [[Static Method]].

```java
Date d = new Date(1981, 4, 1); // btw dont use Date use LocalDate cause Date is mutable which is stupid, yeah lets allow users to delete dates, it totally happens in real life 
d.before(new Date(1981, 4, 2)); // ==> true
```

The [[Method]] `before()` is linked to an [[Object]].

Let's see another example:

```java
jshell> LocalDate bad = LocalDate.of(1981, 2, 29); // Voyons voyons
|  Exception java.time.DateTimeException: Invalid 
|        date 'February 29' as '1981' is not a leap year
|        at LocalDate.create (LocalDate.java:458)
|        at LocalDate.of (LocalDate.java:272)  
```

The [[Method]] `of` is a [[Static Method]] which is **not** linked to an [[Object]].

When designing a [[Class]] it is important to beware of the risk of **Mutability** (see [[Mutability vs Immutability]]).

## References

- [[Object-Oriented Programming#References]]
- <https://cavat.website/poo/docs/poo-basics/poo-by-use/>

### Parent References
