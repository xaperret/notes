---
date updated: 2021-11-02 18:44
---

Topic: #kotlin
Tags: #review #pn_2_1
Links: [[Kotlin]]
Date Created: 02-11-21

---

# Function in Kotlin

## Function in Kotlin in few words

## Function in Kotlin in details

A [[Function in Kotlin]] is simply declared with the [[Keyword]] `fun`

```kotlin
fun aFunction() {
	println("A very fun function !")
}
```

The [[Return]] [[Type]] of a function can be **explicit** or **inferred**

```kotlin
fun product(a: Int, b: Int): Int {
	return a * b
}
// or inferred
fun product(a: Int, b: Int) = a * b
```

Default value can be given to arguments

```kotlin
fun product(a: Int = 1, b: Int = 1) = a * b
```

## References

- [[ISC_L511 - Développement mobile]]
- <https://kotlinlang.org/docs/basic-syntax.html#functions>
