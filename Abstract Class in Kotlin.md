---
date updated: 2021-11-03 19:30
---

Topic: #kotlin
Tags: #review #pn_2_1
Links: [[Kotlin]] [[Abstract Class]]
Date Created: 03-11-21

---

# Abstract Class in Kotlin

## Abstract Class in Kotlin in few words

## Abstract Class in Kotlin in details

```kotlin
abstract  class Explosion(val size: Int) {
	abstract fun detonation()
}

class TNT : Explosion(100) {
	override fun detonation() {
		println("boum")
	}
}
```

## References

- [[ISC_L511 - Développement mobile]]
