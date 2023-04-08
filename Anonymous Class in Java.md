---
date updated: 2021-11-09 16:23
---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Java]]
Date Created: 09-11-21

---

# Anonymous Class in Java

## Anonymous Class in Java in few words

```java
// Anonymous Classes general declaration
Class variableName = new Class(actual-list) // where actual-list is an optional list of arguments
{	class-body	}

// Anonymous Interface general declaration
new I()
{	class-body	}
```

## Anonymous Class in Java in details

An [[Anonymous Class in Java]] is a special kind of [[Nested Class]].
This is the reason why it must be **declared inside** a [[Method]], [[Constructor]] or [[Initializer]].
An [[Anonymous Class in Java|Anonymous Class]] can only be instantiated once.
An [[Anonymous Class in Java]] can't declared its own [[Constructor]].

For example, we have this interface:

```java
public interface Hello {
  void greetings();
}
```

Then we can implement our **Anonymous Class** like so

```java
Hello h = new Hello() {
  public void greetings() { System.out.println("Hi guys!"); }
};
h.greetings(); // show Hi guys!

// or inside the enclosing class 
new Hello() { 
  public void greetings() { System.out.println("Hi!"); } 
}.greetings(); // show Hi!
```

### Java 8 : Lambdas

See [[Functional Interface in Java]]

## References

- <https://cavat.website/poo/docs/particular-types/anonymous/>
- [[@sestoftJavaPrecisely2016]] p. 32
