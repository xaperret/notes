---
date updated: 2021-11-02 15:50
---

Topic: #kotlin
Tags: #review #pn_2_1
Links: [[Type in Kotlin]] [[The Billion Dollar Mistake]]
Date Created: 02-11-21

---

# Type nullable

## Type nullable in few words

## Type nullable in details

As mentioned in [[Type in Kotlin]], [[Kotlin]] aggressively fights against `null`.
There are multiple ways to insure the [[Compiler]] is happy with our handling of **possible** `null` [[Type]].

### Explicitly Checks for `null`

We can **explicitly check for `null` in [[If-Statement]]**, since the [[Compiler]] will check if we use them to treat safely `null` types.

### Using Operators to check for `null`

There are also three operators made for that purpose

- [[Safe Calls]]
- [[Elvis Operator]]
- [[Assert non-null Operator]]

## References

- [[ISC_L511 - Développement mobile]]
- <https://kotlinlang.org/docs/null-safety.html#nullable-types-and-non-null-types>
