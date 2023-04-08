---
date updated: 2021-10-30 14:26
tags:
  - '#java_programming'
  - '#oop'
  - '#review'
  - '#pn_2_1'
---

Topic: #java_programming #oop
Tags: #review #pn_2_1
Links: [[Object]]
Date Created: 30-10-21

---

# Inner Object

## Inner Object in few words

## Inner Object in details

An [[Inner Object]] is an instantiation of a non-static [[Member]] of a [[Class]].

```java
TLC oo = new TLC();
TLC.NMC io1 = oo.new NMC();
TLC.NMC io2 = oo.new NMC();
TLC.SMC sio = new TLC.SMC();
```

![[Pasted image 20211030142409.png]]

## References

- [[@sestoftJavaPrecisely2016]] p. 35
