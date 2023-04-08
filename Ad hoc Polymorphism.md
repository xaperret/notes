---
date updated: '2021-10-16T21:17:14+02:00'

---

Topic:  #java_programming
Tags: #review #pn_2
Links: [[Polymorphism]]
Date Created: 16-10-21

---

# Ad hoc Polymorphism

## Ad hoc Polymorphism in few words

## Ad hoc Polymorphism in details

Or [[Overload]] (NOT [[Override]]). [[Method]] of the same [[Class]] can have the same **name** if they have **different [[Argument|arguments]]** in **number** or **type**

```ad-warning

A different return type DOES NOT allow overload

```

```java
class Test {
  void test(int i) { System.out.println("int: " + i); }
  void test(short s) { System.out.println("short: " + s); }
  void test(Schtroumpf s) { System.out.println("Je suis un schtroumpf: " + s.schtroumpf()); }
}
```

## References

### Direct References

- <https://cavat.website/poo/docs/classes-and-objects/surcharge/>

### Parent References
