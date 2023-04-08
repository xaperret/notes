---
date updated: 2021-10-27 10:24
tags:
  - '#java_programming'
  - '#type_conversion'
  - '#review'
  - '#pn_2_1'

---

Topic: #java_programming #type_conversion
Tags: #review #pn_2_1
Links: [[Literals Conversion]]
Date Created: 10-10-21

---

# Implicit Conversion

## Implicit Conversion in few words

- **mixed [[Type]]** (`short a = b`, where b is `byte` => `short`)
- [[Integer Type]] and [[Real Type]] (`int` + `float` => `float` + `float` => `float`)

## Implicit Conversion in details

There is the possibility for [[Implicit Conversion]] between types as long as there no loss of [[magnitude]], loss of [[precision]] is completely **acceptable**.
From this rule we can derive this hierarchy

```java
byte -> short -> int -> long -> float -> double
char -> int -> long -> float -> double
```

### Exercises

Indicate which lines don't compile

```java
short s = 10;
byte b = s;
int i = s;
long l = s;
```

````ad-info
title: Answers
collapse: closed

```java
short s = 10; // yes
byte b = s; // s is bigger that b so magnitude loss => no
int i = s; // i is bigger that s so no loss => yes
long l = s; // same => yes
````

```java
short s = 10;
s = s + s;
s = s * 2;
```

````ad-info
title: Answers
collapse: closed

```java
short s = 10; // yes
s = s + s; // + transform into int so int -> short = loss => no
s = s * 2; // same idea => no
````

```java
short s = Short.MAX_VALUE // 32767
int i = s++;
```

````ad-info
title: Answers
collapse: closed

```java
short s = Short.MAX_VALUE // 32767
int i = s++; // ++ => post-fix => return then ++
````

```java

void g(int n, float x) {...};
void h(short s) {...};

int i;
byte b;
float f;
double d;

g(i, f);
```

````ad-info
title: Answers
collapse: closed

```java
void g(int n, float x) {...};
void h(short s) {...};

int i;
byte b;
float f;
double d;

g(i, f); // i => ok, x => ok => YES
g(b+1, f); // b+1 => int => ok, f => ok => YES
g(b, f); // b => ok, f => ok => YES
g(i, d); // i => ok, d => pas ok => NO
g(i, i); // i => ok, i => ok => YES
g(i, 2*f); // i => ok, 2*f => ok => YES
g(i, 2.0*f); // i => ok, 2.0 => double => loss => NO
h(b); // YES
h(b+1); // NO
h(5+5); // NO
h(5.0); // NO
````

## References

- <https://cavat.website/poo>
