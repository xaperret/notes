---
date updated: 2021-11-03 17:29
---

Topic: #kotlin #oop
Tags: #review #pn_2_1
Links: [[Kotlin]] [[Class in Kotlin]] [[Constructor]]
Date Created: 03-11-21

---

# Constructor in Kotlin

## Constructor in Kotlin in few words

## Constructor in Kotlin in details

There is a **primary** [[Constructor in Kotlin|constructor]] and the possibility for a **secondary**.
The `constructor` [[Keyword]] can be **omitted** altogether if the **primary** has no [[Visibility Modifiers]] or [[Annotations]].

We can have _initialization code_ inside a block `init` in the [[Class]]

```kotlin
...
init {
	// do stuff
}
...
```

To initialize properties simply

```kotlin
class Person constructor(firstName: String) { 
	val firstname = firstName.uppercase()/*...*/ }
```

To initialize and declare them inside the [[Constructor in Kotlin]] simply

```kotlin
class Person(val firstName: String, val lastName: String, var age: Int)
```

And to have default values

```kotlin
class Person(val firstName: String, val lastName: String, var isEmployed: Boolean = true)
```

For [[Properties in Kotlin]] one should add commas at the end to improve the [[Constructor in Kotlin|constructor]] job.

```kotlin
class Person {
	val firstName: String,
	val lastName: String,
	val age: Int,
}
```

```kotlin
class Fruit(var a: String)
```

### Secondary constructors

```kotlin
class Person(val pets: MutableList<Pet> = mutableListOf()) 

class Pet {
	constructor(owner: Person) {
		owner.pets.add(this) // adds this pet to the list of its owner's pets 
	}
}
```

## References

- <https://kotlinlang.org/docs/classes.html>
