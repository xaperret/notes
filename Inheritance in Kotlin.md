---
date updated: 2021-11-03 17:33
---

Topic:
Tags: #review #pn_2_1
Links:
Date Created: 03-11-21

---

# Inheritance in Kotlin

## Inheritance in Kotlin in few words

## Inheritance in Kotlin in details

Add [[Keyword]] `open` to a [[Class in Kotlin]] for it to be **inherited**.

```kotlin
open class Person(val firstName: String, val lastName: String) {
	...
}

class Patient(val id: Int) : Person()
```

## References

- [[ISC_L511 - Développement mobile]]
