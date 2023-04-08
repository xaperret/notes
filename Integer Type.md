---
date updated: 2021-11-09 11:29
sr-due: 2021-12-03
sr-interval: 24
sr-ease: 254
---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Java]] [[Primitive Type in Java]]
Date Created: 08-10-21

---

# Integer Type in Java

## Integer Type in Java in few words

| Type    | Byte |
| ------- | ---- |
| `byte`  | 1    |
| `short` | 2    |
| `int`   | 4    |
| `long`  | 8    |

## Integer Type in Java in details

[[Integer Type]] is a subtype of [[Primitive Type in Java|Primitive Type]].
The [[Integer Type]] and its subtypes are **signed numbers**.
They are using [[Two's complement representation]] and have **exact precision** within their **constraint [[Domain]]**.
Meaning,

- Integer Literal must respect the domain constraint $x \in [min value, max value]$
- Integer Operations must respect the constraint $Integer MIN VALUE < OPERATION(x_n) < Integer MAX VALUE$ is respected, then there is no loss of precision.

```java
int a = 10;
int b = 20;
int c = a + b;

if(10 + 20 == c) {
	System.out.println("Happy !");
}

float a = 10.00001f;
float b = 20.001f;
float c = 20.00101f;

if (10.001f + 20.00001f == c) {
	...// this might not be true because of the way
	// real types are represented in memory
}
```

The arithmetic is modular, meaning if there is an [[Overflow]] this will cause a _loop_

```java
jshell> int j = 2147483647 + 1 // 2147483647 est la valeur max d'un int
j ==> -2147483648 // débordement !
```

To not have a problem, one should use the library `Math` which **throws** an [[Exception]] if there is an [[Overflow]].

```java
jshell> Math.addExact(2147483647, 1) // fonction utilitaire
|  Exception java.lang.ArithmeticException: integer overflow
|        at Math.addExact (Math.java:825)
|        at (#1:1)
```

```ad-important

Beware of pre and post iteration operators !
~~~java
jshell> int a = Integer.MAX_VALUE;
a ==> 2147483647

jshell> a = a++;
a ==> 2147483647

jshell> a = ++a;
a ==> -2147483648
~~~

```

## References

- <https://cavat.website/poo/docs/syntaxe/base/>
- [[@sestoftJavaPrecisely2016]] p. 5
