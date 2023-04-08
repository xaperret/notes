---
date updated: '2021-10-08T10:46:33+02:00'

date created: Sunday, January 16th 2022, 4:01:06 pm
date modified: Tuesday, July 5th 2022, 5:28:53 pm
---

Topic: #java_programming #computer_science
Tags: #review #pn_1_9
Links: [[Java]]
Date Created: 05-10-21

---

# Imperative vs Declarative Style in Java

## Imperative vs Declarative Style in Java in few words

Java is at its heart a [[Imperative Language]][^1] The trend is for Java to evolve into [[Declarative language|declarative style]].

## Imperative vs Declarative Style in Java in details

### Imperative Style

**How** is more important than **what**.

```ad-example
~~~java
// Algo : sommer les nombres positifs d'une liste
int i = 0 ;
int resultat = 0;
while (i < liste.size()) {
  int valeur = liste[i];
  if (valeur >= 0) {
    resultat += valeur;
  }
  i += 1;
}
~~~
```

### Declarative Style

**What** is more important than **how**.

```java
int resultat = liste.filter( (valeur) -> valeur >= 0 ).sum();
```

### Example

Imperative is **how** : "I see that table located under the Gone Fishin’ sign is empty. My husband and I are going to walk over there and sit down."
Declarative is **what** : "Table for two, please."

### Programming Languages

- Imperative : [[C]], [[C++]], [[Java]]
- Declarative : [[SQL]], [[HTML]]
- Both (possibly) : [[JavaScript]], [[CSharp]], [[Python]]

## References

- <https://cavat.website/poo/>
- <ui.dev/c/react>

### Parent References

- [[Java#References]]

[^1]: [[Imperative Programming]]
