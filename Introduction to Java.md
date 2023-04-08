---
date updated: '2021-10-08T10:38:52+02:00'

---

Topic: #oop #java_programming
Tags: #review #pn_1_9
Links: [[Java]]
Date Created: 05-10-21

---

# Introduction to Java

## Introduction to Java in few words

## Introduction to Java in details

Java is very portable, because its code is interpreted by a [[Virtual Machine]], the [[Java Virtual Machine]]. To  alleviate the performance issue usually caused by code interpretation Java is using [[Just-In-Time Compilation]], which transform Java [[Bytecode]] into [[Machine Code]] _during_ **execution**, so that the code is not **interpreted** but rather **executed**.

The [[Java Virtual Machine]] is a [[Virtual Machine]] that allows a computer to compute Java [[Bytecode]].
The fact that it can execute Java [[Bytecode]] means it is possible to execute programs written in other language under the condition that they _generate_ Java [[Bytecode]].

We mentioned earlier [[Just-In-Time Compilation]], there is another **performance enhancer**, indeed Java is capable of [[Ahead-of-Time Compilation]], which compiles [[Bytecode]] into [[Machine Code]] _before_ **execution**, with their latest [[Compiler]] with `jaotc`.

Java uses a [[Garbage Collector]] for memory management. This means that there is no manual management of memory, since unneeded data on the [[Stack]]/[[Heap]] is automatically disposed.

Java is statically typed.

```java
public class HelloWorld {
 public static void main(String[] args) {

  System.out.println("Hi Guys!");

 }
}
```

Java is an [[Imperative language]] and [[Object-Oriented Programming]] language which is evolving towards a [[Declarative language]] style

## References

- <https://cavat.website/poo/docs/bases/intro-java/>
- <https://en.wikipedia.org/wiki/Java_virtual_machine>

### Parent References

- [[Java#References]]
