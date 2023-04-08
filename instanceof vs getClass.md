---
date updated: '2021-10-14T21:11:30+02:00'

---

Topic: #java_programming
Tags: #review #pn_2
Links: [[Java]]
Date Created: 12-10-21

---

# instanceof vs getClass

## instanceof vs getClass in few words

## instanceof vs getClass in details

### `instanceof`

[[Static Method]] that returns `true` if an [[Reference]] is:

- `not-null`
- Can be converted into **known** [[Type]]
- Is in the hierarchy

Either return false or a compile error depending on the _severity_

                Object  
              /      \  \
        Number       A  String
       /     \       |
    Double  Integer  C

```java
Number n = 3;
n instanceof Object // => true
n instanceof Number // => true
n instanceof Double // => false
n instanceof String // => Compile-time error
n instanceof A // => Compile-time error
```

### `getClass`

[[Method]] that returns the [[Class]] referenced as `java.lang.Class<T>`, **not** the [[Reference]] !
Therefore, this is the [[Method]] that should be used to redefine `equals`[^1]

```java
Object o = 10;
Integer i = 20;
Class A { ... }

o.getClass().equals(Integer.class); // true, the object in mem is integer
o.getClass() == i.getClass(); // still true

o.getClass().isInstance(i); // true
o.getClass().equals(A.class); // false integer is not equal to A


```

```ad-important
It's a dynamic solution, meaning there are no checks done at `Compile-time` !

```

## References

- <https://cavat.website/poo/docs/classes-and-objects/object/#instanceof-vs-getclass>

[^1]: [[Class Object#Redefine equals]]
