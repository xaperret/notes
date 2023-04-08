---
date updated: '2021-10-11T16:20:33+02:00'

---

Topic: #java_programming
Tags: #review #pn_1_9
Links:
Date Created: 08-10-21

---

# Numeric Promotion

## Numeric Promotion in few words

Automatically transforms the [[Type]] of any [Operand] in any expression has an arithmetic [[Operators in Java]].

- Arithmetic [[Operators in Java]] (`byte` + `short` => `int` + `int` => `int`)

## Numeric Promotion in details

[[Numeric Promotion]] is an **automatic conversion** that happens on [[Integer Type]] or [[Real Type]] [[Operand]] which transforms any [[Operand]] [[Integer Type]] or [[Real Type]] (e.g.: `short`, `byte`)into a bigger [[Type]] to **accommodate** the desired operation.
It's a form of [[Implicit Conversion]] (please look at [[Implicit Conversion#Exercises]] for more example).

This **bigger [[Type]]** could depend on the situation.

There are cases where there are **different** [[Type]].

```java
short a = 10;
byte b = 15;
short c = a + b; // numeric promotion => byte + short = short
```

There are cases where there are [[Integer Type]] and [[Real Type]]

```java
short a = 10;
float b = 10.0;
float c = a + b; // numeric promotion => short + float = float
```

There are cases where there is an **arithmetic [[Operators in Java]]** and if there are [[Integer Type]] they will be converted to `int`

```java
short s1 = 10;
short s2 = 20;
short s3 = s1 + s2; // not ok, + => converted to int !
```

[[Numeric Promotion]] does work when invoking functions.

```java
public class NumericPromotion {

    public static void patate(int banane) {

    }
	
	public static void shortPatate(short banane) {

    }
    public static void main(String[] args) {
        short banane = 10;
        NumericPromotion.patate(banane); // no problem
        NumericPromotion.shortPatate(banane + 10); // problem !
    }
```

But, it does not work the other way around !

```java
void test(short s) { ... }

short s = 42; // ok for declaration int -> short
test(s); // ok
test(42); // not ok for calling a function != int -/-> short
            
```

If you understand the value of `n` and `p` here, you have understood [[Numeric Promotion]]

```java
byte b = Byte.MAX_VALUE;
int n = b + 1;

int i = Integer.MAX_VALUE;
long p = i + 1;
```

````ad-warning

Weird stuff with [[Real Type]]
```java
float f1 = 10.0;  // 10.0 is a real literal meaning double => CANT COMPILE
float f2 = 10.0f; // POST-FIX !!  :D
float f3 = f2 + f2;  // no numeric promotion
````

## References

- <https://cavat.website/poo/docs/syntaxe/base/> "Numeric Promotion is not a thing in Real Types, it's type adjustment"
- <https://docs.oracle.com/javase/specs/jls/se7/html/jls-5.html#jls-5.6>

### Parent References
