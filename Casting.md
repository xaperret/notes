---
date updated: '2021-10-16T19:22:08+02:00'

---

Topic: #java_programming
Tags: #review #pn_2
Links: [[Java]]
Date Created: 16-10-21

---

# Casting

## Casting in few words

## Casting in details

Before Java 16, to cast an [[Object]] we needed to do this

```java
String s = (String)o;
```

But ! `instanceof` can allow us to not make mistake when casting, by verifying if the type we wanted to Cast was compatible with the other.

```java
public static void test(Object o) {
    if (o instanceof String) {
        String s = (String)o; // cast
        /* do something with s */
    } else if (o instanceof Counter) {
        Counter counter = (Counter)o; // cast
        /* do something with counter */
    } 
}
```

With **Java 16**, we don't have to the [[Casting]] is automatic, thanks to [[pattern matching]].

## References

### Direct References

- <https://cavat.website/poo/docs/classes-and-objects/object/#casting>

### Parent References
