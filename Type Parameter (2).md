---
date created: Friday, November 19th 2021, 2:00:04 pm
date modified: Thursday, December 2nd 2021, 6:14:11 pm
---

- Topic: #java_programming 
- Tags: #review #pn_2_1
- Links: [[Collections in Java]] [[Generics in Java]]
- Date Created: 02-12-21

---

# Type Parameter

## Type Parameter in Few Words

A **type parameter** or **parametric type** allows us to express the type we want to use in a _dynamic_ way. They are written as single, uppercase letters, also named **type variable**.

```java
/**
 * Generic version of the Box class.
 * @param <T> the type of the value being boxed
 */
public class Box<T> {
    // T stands for "Type"
    private T t;

    public void set(T t) { this.t = t; }
    public T get() { return t; }
}
```

## Type Parameter in Details

## References

- <https://docs.oracle.com/javase/tutorial/java/generics/types.html>
