---
date updated: 2021-11-02 17:09
---

Topic: #kotlin
Tags: #review #pn_2_1
Links: [[Kotlin]]
Date Created: 02-11-21

---

# Control Structures in Kotlin

## Control Structures in Kotlin in few words

## Control Structures in Kotlin in details

### if-else

We have _normal_ if-else blocks like so

```kotlin
if (condition) {
	// block of code
} else {
	// block of code
}
```

Or something similar to [[Ternary]]

```kotlin
val type = if (age < 18) "child" else "adult"
println("${name} is a ${type}")
```

### when

```kotlin
when (value) {
	"bim" -> stuff
	"boum" -> stuf
	else -> stu
}
```

Pattern Matching

```kotlin
when(value) {
	age >= 18 -> st
	height == 1 -> s
}
```

Assigning values using when

```kotlin
val canDrive = when(value) {
		in 15..18 -> true
		in 18..80 -> true
		else -> false
}
```

### for-loop

for-loop using ranges

```kotlin
for (i in 1..5) {
	...
}
```

for-loop going through collections

```kotlin
for (item in collection) {
	...
}
```

## References

- [[ISC_L511 - Développement mobile]]
- <https://kotlinlang.org/docs/coding-conventions.html#control-flow-statements>
