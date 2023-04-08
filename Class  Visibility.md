---
date modified: Sunday, April 10th 2022, 9:11:00 pm

date created: Sunday, January 16th 2022, 4:01:06 pm
date modified: Sunday, April 10th 2022, 9:11:00 pm
---

Topic: #oop #java_programming
Tags: #review #pn_2_1
Links: [[Class]]
Date Created: 23-10-21

---

# Class Visibility

## Class Visibility in few words

Each of these members have a [[Visibility]] that we have to indicate. No matter the [[Class]] [[Visibility]] if the [[Keyword|keyword]] `final` is used, then it's **impossible** to declare [[Subclass]] of this [[Class]].

```java
jshell> final public class Fruit {
   ...>     
   ...> }
|  created class Fruit

jshell> public class Banana extends Fruit {
   ...> }
|  Error:
|  cannot inherit from final Fruit
|  public class Banana extends Fruit {
|                              ^---^

jshell> 
```

Also, [[Abstract Class]] cannot be instantiated but their children can !

## Class Visibility in details

## References

- [[Class#References]]
