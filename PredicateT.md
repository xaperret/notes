---
date updated: 2021-11-10 10:06
---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Functional Interface in Java]]
Date Created: 10-11-21

---

# PredicateT

## PredicateT in few words

## PredicateT in details

[[PredicateT]] is a [[Functional Interface in Java]] that `T -> boolean` and has a [[Signature]] `boolean test(T t)`.

```java
Stream<Person> originStream = ...
List<Person> people = originStream.filter( p -> p.isWorking() )
                                  .collect(Collectors.toList());
List<Person> people = originStream.filter( Person::isWorking )
                                  .collect(Collectors.toList());
```

## References

- <https://cavat.website/poo/docs/particular-types/anonymous/#exemples-de-functiontr-et-suppliert-et-predicatet-avec-des-streams>
