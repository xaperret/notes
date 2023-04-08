---
date updated: 2021-11-02 18:42
---

Topic: #kotlin
Tags: #review #pn_2_1
Links: [[Kotlin]] [[Property]]
Date Created: 02-11-21

---

# Property

## Property in few words

## Property in details

[[Properties in Kotlin]] [[Class in Kotlin|classes]] like [[Variable in Kotlin|variables]] can be [[Mutable]] `var` or [[Immutable]] `val`.

```kotlin
class Address { 
	var name: String = "Holmes, Sherlock" 
	var street: String = "Baker" 
	var city: String = "London" 
	var state: String? = null 
	var zip: String = "123456" 
}
```

To call a [[Property]] we just refer it by its name

```kotlin
val test  = Address()
test.name = "test"
test.street = "test street"
...
```

## References

- <https://kotlinlang.org/docs/properties.html>
