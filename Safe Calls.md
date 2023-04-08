---
date updated: 2021-11-02 15:43
---

Topic: #kotlin
Tags: #review #pn_2_1
Links: [[Type nullable]]
Date Created: 02-11-21

---

# Safe Calls

## Safe Calls in few words

## Safe Calls in details

The [[Safe Call Operator]] is an operator that is used when we want to access a [[Properties in Kotlin]] on a `nullable` [[Variable]]

```kotlin
val a = "banana"
val b: String? = null
println(b?.length)
println(a?.length)
```

## References

- <https://kotlinlang.org/docs/null-safety.html>
