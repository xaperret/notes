---
date updated: 2021-11-11 10:12
sr-due: 2022-03-14
sr-interval: 110
sr-ease: 232
---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Type]]
Date Created: 08-10-21

---

# Literal

## Literal in few words

```java
int i = 10; // 10 is an Integer literal
```

```
Literal:  
 IntegerLiteral  
 FloatingPointLiteral  
 BooleanLiteral  
 CharacterLiteral  
 StringLiteral  
 NullLiteral
```

## Literal in details

A literal is a **value explicitly given** found in the code, it is **the source code representation**, e.g. `int i = 10` is an [[Integer Type]] [[Literal in Java]].

### Integer Literals

An `integer literal` can be expressed in [[Decimal]](base 10), [[Hexadecimal]](base 16), or [[Binary]](base 2).

```java
IntegerLiteral:  // anything that is an integer 10, 1, 0, 100,
 DecimalIntegerLiteral  
 HexIntegerLiteral  
 OctalIntegerLiteral  
 BinaryIntegerLiteral   
  
  // these literal requires suffixes !
DecimalIntegerLiteral:  
 DecimalNumeral IntegerTypeSuffixopt  
  
HexIntegerLiteral:  // 0x
 HexNumeral IntegerTypeSuffixopt  
  
OctalIntegerLiteral:  // 0 followed by [0-7]*
 OctalNumeral IntegerTypeSuffixopt  
  
BinaryIntegerLiteral:  // 0b
 BinaryNumeral IntegerTypeSuffixopt  
  
IntegerTypeSuffix: one of  
 `l` `L`
```

### Floating-Point Literals

## References

- <https://cavat.website/poo/docs/syntaxe/base/#quelques-r%c3%a8gles-de-conversions-importantes-sur-les-entiers>
- <https://docs.oracle.com/javase/specs/jls/se7/html/jls-3.html#jls-3.10>
