---
date updated: 2021-11-02 17:51
---

Topic: #kotlin
Tags: #review #pn_2_1
Links: [[Kotlin]]
Date Created: 02-11-21

---

# Variable in Kotlin

## Variable in Kotlin in few words

## Variable in Kotlin in details

We can have [[Constant]][^1]

```kotlin
val a: Int = 0 // this can't be modified
val b = 2 // this can't be modified
```

Also if for some reason you can't or don't want to assign a [[Constant]] you can **defer** the assignment !

```kotlin
val c: Int
c = 3 // THE ASSIGNEMENT CAN BE DEFERRED WTF
```

Normal variables can be declared either with the [[Type]] explicitly declared or inferred.

```kotlin
var x = 5
var y: Int = 5
```

## References

- <https://kotlinlang.org/docs/basic-syntax.html#variables>

[^1]: or `read-only` local variables, how kotlin doc calls them (i don't get it)
