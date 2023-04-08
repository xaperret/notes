---
date updated: 2021-11-10 10:03
tags:
  - '#java_programming'
  - '#interface'
  - '#review'
  - '#pn_2_1'
---

Topic: #java_programming #interface
Tags: #review #pn_2_1
Links: [[Functional Interface in Java]]
Date Created: 10-11-21

---

# FunctionTR

## FunctionTR in few words

## FunctionTR in details

[[FunctionTR]] is a type of [[Functional Interface in Java]] that takes a **type** (`T -> R`), apply an operation on it and returns something.
Its [[Signature]] is `R apply(T t)`.

`Stream` are lazy, meaning they are evaluated only when **used**. `Stream` are a good way to manipulate [[Collections in Java]].

```java
Stream<Integer> xs = List.of(1,2,3).stream();

List<String> zs = xs.map( (Integer i) -> i.toString() )
                    .collect(Collectors.toList());
List<String> zs = xs.map( i -> i.toString() )
                    .collect(Collectors.toList());
```

## References

- <https://cavat.website/poo/docs/particular-types/anonymous/#exemples-de-functiontr-et-suppliert-et-predicatet-avec-des-streams>
