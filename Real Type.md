---
date updated: "2021-10-09T10:46:18+02:00"
---

Topic: #java_programming
Tags: #review #pn_1_9
Links: [[Java]]
Date Created: 09-10-21

---

# Real Type

## Real Type in few words

## Real Type in details

| Type     | Byte |
| -------- | ---- |
| `float`  | 4    |
| `double` | 8    |

A [[Real]] [[Literal in Java]] is of type `double`. Therefore, the compiler will not give **implicitly** it the `float` type.
Indeed, to have a [[Real]] [[Literal in Java]] as a type `float`, you need to [[Postfix]] it with `f` or `F` like so `float b = 2.0f;` which is a bit _stupid_ considering you can do `float c = 2;` without problems.

There are no [[Numeric Promotion]] like with [[Integer Type]].

```java
float a = 10;
float b = 5.0f;
float c = 2000000000.0F;
double d = 2e3;  // this is possible ! 2*10^3=2000

return (a + b) * c; // will not return a double or an integer
```

There are special values `Nan`, `Infinity` and `-Infinity`

```bash
jshell> 0.0 / 0.0
$1 ==> NaN

jshell> 3 / 0.0
$2 ==> Infinity

jshell> -3 / 0.0
$3 ==> -Infinity
```

**Precision** is not very good with these types, which is why it's better for _money_ to work either with [[Integer Type]] and work with pennies or use `BigDecimal` which uses [[Arbitrary-precision Arithmetic]]

## References

- <https://cavat.website/poo/docs/syntaxe/base/#les-types-r%c3%a9els>

### Parent References

- [[Java]]
