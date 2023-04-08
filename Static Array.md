---
date updated: '2021-10-10T22:54:45+02:00'

---

Topic: #java_programming
Tags: #review #pn_1_9
Links: [[Java]]
Date Created: 10-10-21

---

# Static Array

## Static Array in few words

## Static Array in details

[[Static Array]] aren't that interesting to use in [[Java]] since you can't add to them, only modify what is in the list.

```java
var test1 = Arrays.asList("bim", "bam", "boum");
var test2 = List.of("boum", "bam", "bim");
type[] test3 = {"boum", "bim", "bam"};
type[] test4 = new type[SIZE_OF_STATIC_ARRAY];

/**
** test1.add won't work
** test1.get(i), if i is > limit, then ArrayIndexOutOfBoundsExc.
** test3[0] => to get the first element
** test3[0] = "something else"; => to change it
*/
```

```java
float[] fs = new float[4]  // fs = {0.0, 0.0, 0.0, 0.0}
String[] fs2 = new String[4] // fs2 = {null, null, null, null]
```

```java
double[][] matrix = new double[2][3]; // deux lignes, trois colonnes
```

```java
double[][] matrix2 = matrix; // /!\ matrix et matrix2 pointent 
                             // sur la même instance
double[][] matrix3 = matrix.clone() // copie le tableau
```

## References

- <https://cavat.website/poo/docs/poo-basics/poo-by-use/#les-tableaux-statiques>

### Parent References

- [[Java#References]]
