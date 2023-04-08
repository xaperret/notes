---
date updated: 2021-11-03 19:42
---

Topic: #kotlin
Tags: #review #pn_2_1
Links: [[Kotlin]]
Date Created: 03-11-21

---

# Interface in Kotlin

## Interface in Kotlin in few words

## Interface in Kotlin in details

```kotlin
interface Fuel {
	val prop: Int, // this is a property, this is fine, this is not storing a state
	
	fun foo()
	
	fun fillGasTank() {
		println("default behavior")
	}
}
```

```kotlin
class Child: Fuel {
	override fun foo() {
		// stuff
	}
}
```

Possible to inherits from multiple [[Interface in Kotlin|Interface]]

Possible to have [[Interface in Kotlin|Interface]] inheritance with another [[Interface in Kotlin|Interface]].

## References

- [[ISC_L511 - Développement mobile]]
