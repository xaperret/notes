---
date modified: Thursday, December 16th 2021, 3:12:30 pm
date created: Thursday, November 25th 2021, 9:52:56 am
date modified: Thursday, December 16th 2021, 3:12:30 pm
---

- Topic: #c_programming
- Tags: #review #pn_2_1
- Links: [[Type in C]]
- Date Created: 25-11-21

---

# Integer Type in C

## Integer Type in C in Few Words

| Signed | Keyword                                                            | **Minimal** Size[^1] | ???                             |
| ------ | ------------------------------------------------------------------ | -------------------- | ------------------------------- |
| Yes    | `short`<br>`short int`<br>`signed short`<br>`signed short int`[^2] | 2                    | -32767 to 32767                 |
| Yes    | `int`<br>`signed int`<br>`signed`                                  | 2                    | -32767 to 32767                 |
| Yes    | `long`<br>`long int`<br>`signed long`<br>`signed long int`[^3]     | 4                    | -2,147,483,648 to 2,147,483,647 |
| Yes    | `char`                                                             | 1                    |                                 |
| No     | `unsigned int`<br>`unsigned`                                       | 2                    | 0 to 65535                      |
| No     | `long`<br>`long int`<br>`signed long`<br>`signed long int`[^4]     | 4                    | -2,147,483,648 to 2,147,483,647 |
| No     | `unsigned long`<br>`unsigned long int`[^5]                         | 4                    | 0 to 4,294,967,295              |
| No     | `unsigned char`                                                    | 1                    |                                 |

```ad-important

ANSI Standards don't really impose specific size constraints but some types must have the length, e.g 
- `long int` and `unsigned long int`
- `short int` and `int` can have the same size
- `int` can be of 2 bytes

```

## Integer Type in C in Details

## References

- [[ISC-332 - Programmation système]]
- [[@delannoyGuideCompletLangage2020]] p. 28
- <https://www.tutorialspoint.com/cprogramming/c_data_types.htm>





[^1]: Size can be different depending on the system implementation, indeed int can be as small as 2 bytes !
[^2]: its `signed/unsigned short/long int`
