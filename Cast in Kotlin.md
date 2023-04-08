---
date updated: 2021-11-03 20:50
---

Topic: #kotlin
Tags: #review #pn_2_1
Links: [[Kotlin]]
Date Created: 03-11-21

---

# Cast in Kotlin

## Cast in Kotlin in few words

## Cast in Kotlin in details

### Smart cast

```kotlin
if(vehicle is Car) {
	vehicle.carMethod()
}
```

### Unsafe cast

```kotlin
var jeep: Car = vehicle as Car
```

### Safe cast

Safe cast is a way to not have a `ClassCastException` if the [[Object]] is not of the target type.

```kotlin
val aInt: Int? = a as? Int
```

## References

- [[ISC_L511 - Développement mobile]]
