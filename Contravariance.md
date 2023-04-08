---
date created: Monday, December 20th 2021, 3:29:46 pm
date modified: Monday, December 20th 2021, 6:48:07 pm
---

- Topic: #java_programming
- Tags: #review #pn_2_1
- Links: [[Variance]] [[Variance in Java]]
- Date Created: 20-12-21

---

# Contra-variance

## Contra-variance in Few Words

Is a way to substitute a type by its [[Superclass]] or super-type.

To make something **contra-variance**, one must use the syntax `<? extends supertype>`, like so :

```java
boolean addAll(Collection<? super E> c) { ... } // this allows us to have covariance
```

So something like

```java
List<Integer> ints List.of(1,2,3);
List<Number> arguments = ints; // doesnt compile
```

Can be put into something that compiles like

```java
List<Integer> ints List.of(1,2,3);
List<? extends Number> arguments = ints; // ok

List<Number> numbers = new ArrayList<>();
numbers.addAll(arguments); // this now works !
```

![[Pasted image 20211220184804.png]]

## Contra-variance in Details

## References

- https://cavat.website/poo/docs/variance/
