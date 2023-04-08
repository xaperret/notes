---
date updated: '2021-10-16T19:10:07+02:00'

---

Topic: #java_programming
Tags: #review #pn_2
Links: [[Java]]
Date Created: 16-10-21

---

# Syntax

## Syntax in few words

## Syntax in details

### Special values

`Nan, Infinity, -Infinity`


### Le type booléen

- true, false
- pas de conversion implicite

### Compatibilité et équivalence de types primitifs

- Types sont **non équivalents** => espace mémoire diffère
- Types sont comparables ~> compatibles => conversion implicite si **il n'y a pas de perte de magnitude (~~précision~~)**.
- magnitude => taille e.g => un float dans un double
- précision

```java
byte -> short -> int -> long -> float -> double
char -> int -> long -> float -> double
```

- note: short est signé donc char ne peut être mis dedans

#### Perte de précision sans perte de magnitude

```java
// autre exemple
int origin = 123456789;
float target = origin; 
$1 ==> 1.23456794E9
```

### Récap

- [[Type adjustment]]

### Conversion explicites (cast)

```java
short s1 = 32767;  // Ok, 32767 est la valeur max d'un short
short s2 = 32768;  // Erreur, 32768 hors ens. défin. short
short s3 = (short)32768;
```

### Inférence des types

L'inférence des types est le fait de dynamiquement donner un type à un littéral.

```java
var i = 3; // inféré en int
var d = 33.2; // inféré en double
var s = "Coucou"; // inféré en String
```

### Déclaration de constantes

- variable change pas ? => constante
- mot clé final.

```java
final double PI = 3.141592;
final var userId = 1;
final var result = weightInKg / (heightInCm*heightInCm);
```

## References

### Direct References

- <https://cavat.website/poo/docs/syntaxe/>

### Parent References
