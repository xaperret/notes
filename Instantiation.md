---
date updated: 2021-10-30 14:30
---

Topic: #java_programming
Tags: #review #pn_1_9
Links: [[Java]] [[Object-Oriented Programming]]
Date Created: 12-10-21

---

# Instantiation

## Instantiation in few words

```java
Integer i = new Integer(); // instantiating an object of the type/class Integer
```

## Instantiation in details

`Object o = new Object;`

- Default values are given to non-static [[Field]] based on [[Type]]
- [[Constructor]] is called
- _Explicit_ & _implicit_ [[Superclass]] [[Constructor]] is called => until `Object` is reached
- non-static [[Field]] and **blocks** are executed from top to bottom
- [[Constructor]] **body** is executed

## References

### Parent References
