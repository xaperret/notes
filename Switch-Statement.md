---
date created: 2021-11-07 18:22
date updated: 2021-11-07 18:23
---

---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Control Structures]]
Date Created: 07-11-21

---

# Switch-Statement

## Switch-Statement in few words

## Switch-Statement in details

```java
switch (expression) {
	case const1:
		...
		break;
	default:
		...
		break;
}

switch (i) {
	case 1:
		bim;
		break;
	default:
		boum;
		break;
}
```

`switch` can be used as an [[expression]], by opposition to [[instruction]]. This means that we can use `switch` to return _stuff_ and that also means we can use it as a way to [[Definition|defined]] variables, e.g.:

```java
String hello = switch(number) {
	case 1 -> "un";
	case 2 -> "deux";
	case 3 -> "trois";
	default -> "...";
}
```

We can use `yield` as a way to return something and not have to use `break`.

```java
int i = 2;
String hello = switch (i) {
  case 1:
    yield "Un";
  case 2:
    yield "Deux";
  case 3:
    yield "Trois";
  default: {
    /* les blocs sont possibles */
    yield "...";
  }
}
```

## References
