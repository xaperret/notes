---
date updated: "2021-10-10T12:20:15+02:00"
---

Topic: #java_programming
Tags: #review #pn_1_9
Links:
Date Created: 10-10-21

---

# Explicit Conversion

## Explicit Conversion in few words

## Explicit Conversion in details

```java
short s1 = 32767;  // Ok, 32767 est la valeur max d'un short
short s2 = 32768;  // Erreur, 32768 hors ens. défin. short
short s3 = (short)32768;   // Conversion explicite
                           // Un cycle s’effectue lors
                           // d’un dépassement
                           // ici s3 vaut -32768
```

## References

### Parent References
