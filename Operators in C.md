---
date modified: Tuesday, November 30th 2021, 11:52:21 am
date created: Tuesday, November 30th 2021, 10:29:56 am
---

- Topic: #c_programming
- Tags: #review #pn_2_2
- Links: [[C]]
- Date Created: 30-11-21

---

# Operators in C

## Operators in C in Few Words

| Type           | Operators                 | ?                       | Example                                            |
| -------------- | ------------------------- | ----------------------- | -------------------------------------------------- |
| Affectation    | `=`                       | Var affectation         | `int i = 5;`                                       |
| Arithmetic     | `+`                       | Addition                | `i = i+1; // i = 6`                                |
|                | `-`                       | Subtraction             | `i = i-4; // i = 2`                                |
|                | `*`                       | Multiplication          | `i = i*10; // i = 20`                              |
|                | `/`                       | Division                | `i = i/5; // i = 4`                                |
|                | `%`                       | Modulo                  | `i = i % 2; // i = 0`                              |
| Comparator     | `<`, `>`                  | Greater/lesser          | `10 > 5`, `5 < 10 // true`                         |
|                | `<=`, `>=`                | Greater/lesser or equal | `10 >= 10`, `10 >= 5 // true`                      |
|                | `!=`, `==`                | Not equal, equal        | `10  != 5`, ` 10 == 10 // true  `                  |
| Logical        | `&&`                      | And                     | `(10 > 5) && (5 < 10) // true`                     |
|                | <code>&#124;&#124;</code> | Or                      | <code>(10 >= 10) &#124; (1 >= 5) // true</code>    |
|                | `!`                       | Is not, opposite        | <code>(10 >= 100) &#124; !(1 >= 5) // true</code>  |
| Binary         | `&`                       | And                     | `0b1001 & 0b1111 == 0b1001`                        |
|                | <code>&#124;</code>       | Or                      | <code>0b1001 &#124;0b1111 == 0b1111</code>         |
|                | `^`                       | XOR                     | `0b1001 ^ 0b1111 == 0b0110`                        |
|                | `~`                       |                         | <code>~(0b1001 &#124;0b1111) == 0b0000</code>      |
|                | `>>`                      | Right shift             | <code>(0b1001 &#124;0b1111) >> 1 == 0b0111</code>  |
|                | `<<`                      | Left shift              | <code>(0b1001 &#124;0b1111) << 1 == 0b11110</code> |
| (In/De)crement | `++`, `--`                |                         |                                                    |
|                | `i++`, `i--`              | Return i then do in/de. |                                                    |
|                | `++i`, `--i`              | Do in/de then return i  |                                                    |

## Operators in C in Details

Any of these operators can be combined with the **Affectation Operator** (except himself, of course).

```c
int a = 0;
// this
a = a + 10;
// can be expressed as
a += 10;

a = a - 5;
a -= 5;

a = a * 10;
a *= 10;

a = a << 2;
a <<= 2;
```

## References

- [[ISC-332 - Programmation système]]
