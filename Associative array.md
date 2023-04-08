---
date updated: 2021-10-27 10:51

---

Topic: #oop #java_programming
Tags: #review #pn_2
Links: [[Abstraction]] [[Java]]
Date Created: 18-10-21

---

# Associative array

## Associative array in few words

## Associative array in details

An [[Associative array]], **Map**, **Symbol table** or **Dictionary** is an [[Abstraction|abstract]] data type that **links** one piece of **data** with **key(s)**

![[Pasted image 20211018150847.png]]

A key _k_ is unique in the key [[Domain]]. There can't be two keys with the same value.
Although a [[key]] $k_1$ can have multiple values $v_i$

### Maps in Java

In Java, we declare a Map like so `Map<TypeOfKey, TypeOfValue> varName = ...;` which translates to

```java
Map<String, Integer> contacts = ...;

Map<String, Integer> contacts = new HashMap<>();
// ou
Map<String, Integer> contacts = new TreeMap<>();
```

There are several methods that can be used such as

#### `HashMap<K, V>`

`HashMap` uses an [[Hash Tables]]. Its key must redefine [[Method]] `hashCode()` and `equals()`[^1]

#### `TreeMap<K, V>`

### Exercise
We would like to parse a file and count the number of occurrences of each word.

With an [[Associative array]] ?
```java
Map<String, Integer> wordFreq = new HashMap<>();
```

Knowing a word, how to iterate it ?
```java
wordFreq.put(key, map.get(key)+1);
```

## References

- <https://cavat.website/poo/docs/polymorphism/abstraction/#etude-de-cas--les-tableaux-associatifs>
- <https://en.wikipedia.org/wiki/Associative_array>

[^1]: [[Class Object]]
