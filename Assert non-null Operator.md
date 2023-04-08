---
date updated: 2021-11-02 15:46
---

Topic: #kotlin
Tags: #review #pn_2_1
Links: [[Type nullable]]
Date Created: 02-11-21

---

# Assert non-null Operator

## Assert non-null Operator in few words

## Assert non-null Operator in details

The [[Assert non-null Operator]] or `!!` Operator converts any value to a `non-null` type and **throws an exception** if the value is `null`.

```kotlin
fun main() {
    val b: String? = null
	val l = b!!.length // this will throw a NullPointerException since b is null !
    println(l)
}
```

## References

- <https://kotlinlang.org/docs/null-safety.html#safe-casts>
