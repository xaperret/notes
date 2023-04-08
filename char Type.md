---
date updated: "2021-10-09T11:02:46+02:00"
---

Topic: #java_programming
Tags: #review #pn_1_9
Links: [[Java]]
Date Created: 09-10-21

---

# char Type

## char Type in few words

## char Type in details

`char` needs **2 bytes** to store one `char`, using [[Unicode]] .
It is an unsigned Integer and respect [[Numeric Promotion]].
The [[Object]] [[Type]] [[String in Java]] can instantiate a character string.

```java
char c1; // empty char == ''
char c2 = 'c'; // c for correct way to declare a char

char c3 = "w"; // w for wrong way to declare a char
```

As we can see

```java
jshell> char c3 = "w";
|  Error:
|  incompatible types: java.lang.String cannot be converted to char
|  char c3 = "w";
|            ^-^

jshell>
```

- objet type `String` permet d'instancier une chaîne de caractère

## References

- <https://cavat.website/poo/docs/syntaxe/base/#le-type-caract%c3%a8re>

### Parent References

- [[Java#References]]
