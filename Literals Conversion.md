---
date updated: 2021-10-27 10:19

---

Topic: #java_programming #type_conversion
Tags: #review #pn_2_1
Links: [[Type Conversion]]
Date Created: 08-10-21

---

# Literals Conversion

## Literals Conversion in few words

## Literals Conversion in details

### Integer Type

A [[Integer Type]] [[Literal in Java]] is **by default** of type `int`.

````ad-note
collapse: closed
This below works, because this is part of the domain of short, which also an Integer Type.
```java
short s = 10; // this work !
````

Any [[Affectation]] where the value does not match the domain of the type will be **denied**.

```java
int i = 12; // 12 is a literal that belongs to the domain
byte b1 = 127; // 127 is a literal that belongs to the domain
byte wrong = 128; // does not belong, will not work

int i = 12.0; // 12.0 is a real number so it does not work
```

Sometimes you have to [[Postfix]] a [[Literal in Java]]

```java
long wrongtoo = 3000000000; // does not work because this is not an int
long right = 3000000000L; // we use a long literal !
```

### Real Type

There are no such rules with [[Real Type]], but it is important to note that a [[Real]] [[Literal in Java]] will be by default of type [[Double]]

## References

- <https://cavat.website/poo/docs/syntaxe/base/#quelques-r%c3%a8gles-de-conversions-importantes-sur-les-entiers>
