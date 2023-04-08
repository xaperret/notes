---
date created: Monday, December 20th 2021, 3:30:37 pm
date modified: Monday, December 20th 2021, 3:32:48 pm
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 20-12-21

---

# Invariance

## Invariance in Few Words

[[Generics in Java]] are invariant, meaning that the parameter cannot change. This means if we have a [[Generics]] type like an `ArrayList`, it can **substitute** a `List` but the parameter type must stay the same.

```java
List<Number> nums = new ArrayList<Number>(); // YEAH :)
List<String> s = new ArrayList<Number>(); // this will not work at all :(
```

## Invariance in Details

## References

- https://cavat.website/poo/docs/variance/
