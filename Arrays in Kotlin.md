---
date updated: 2021-11-02 20:24
date created: Friday, November 19th 2021, 2:00:25 pm
date modified: Tuesday, November 2nd 2021, 8:26:16 pm
---

Topic: #kotlin

Tags: #review #pn_2_1

Links: [[Type in Kotlin]]

Date Created: 02-11-21

---

# Arrays in Kotlin

## Arrays in Kotlin in Few Words

## Arrays in Kotlin in Details

[[Arrays in Kotlin]] are **invariant**, this means that the [[Type]] cannot be changed.

If we want to have dynamic array [[Type|types]] then we should use a [[Generics]], more precisely [[Generics in Kotlin#Type Projections|Type Projections]].

### Build an Array

With a [[Constructor]]

```kotlin
val tab = Array<Type>(size) { values}
```

With a [[Factory]][^1]

```kotlin
val tab = arrayOf(val1, val2,  ...)
```

### Access An Item

```kotlin
tab.get(indexOfDesiredItem)
tab[indexOfDesiredItem]
```

#### Primitive Type Arrays

## References

[^1]: note that this link might talk about factory from another language which might not be the same in Kotlin
