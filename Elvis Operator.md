---
date updated: 2021-11-02 15:45
---

Topic: #kotlin
Tags: #review #pn_2_1
Links: [[Type nullable]]
Date Created: 02-11-21

---

# Elvis Operator

## Elvis Operator in few words

## Elvis Operator in details

The [[Elvis Operator]] is an operator that is similar to a [[Ternary]] expression but for the purpose of `nullable` [[Reference]].

```kotlin
val l: Int = if (b != null) b.length else -1
// becomes
val l = b?.length ?: -1 // if b is null then -1 is attributed to l
// it is also possible to return 
val l = b?.length ?: throw IllegalArgumentException("djfsajflkdsaj")  // if b is null then throw error
val l = b?.length ?: return null // if b is null then return something
```

## References

- <https://kotlinlang.org/docs/null-safety.html#safe-casts>
