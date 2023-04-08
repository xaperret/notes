---
date updated: 2021-10-31 19:08
---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Java]]
Date Created: 16-10-21

---

# Enum

## Enum in few words

```java
enum-modifiers enum t implements-clause { 
	enum-value-list; 
	field-declarations;
	constructor-declarations;
	method-declarations;
	class-declarations;
	interface-declarations;
	initializer-blocks;
}
```

## Enum in details

An [[Enum]] [[Type]] is a [[Reference Type in Java]], that has a specialized form of [[Class]] declaration that begins with a list of value declaration that represents the [[Enum]].

```java
public enum Day {
	// enum-value list
    Monday(0), Tuesday(1), Wednesday(2),
	Thursday(3), Friday(4), Saturday(5), Sunday(6); // value declaration
}

// typesafe
void print(Day d) {...}

print(0); // meaning this does not work
print(Day.monday); // but this does

if (Day.Monday == "bim" || Day.Monday == null) {...} // neither works
```

This is a [[Typesafe]] way to have fixed [[Constant]] predefined values.

Keywords `abstract` and `final` cannot be used for the enum-modifier
An [[Enum]] [[Type]] cannot [[Inheritance|inherit]].
A nested [[Enum]] [[Type]] is implicitly [[Static]].

## References

- <https://cavat.website/poo/docs/classes-and-objects/enum/>
- [[@sestoftJavaPrecisely2016]] p. 83
