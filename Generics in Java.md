---
date created: Thursday, December 2nd 2021, 6:04:12 pm
date modified: Sunday, January 16th 2022, 5:54:44 pm
---

- Topic: #java_programming
- Tags: #review #pn_2_1
- Links: [[Java]] [[Generics]]
- Date Created: 02-12-21

---

# Generics in Java

## Generics in Java in Few Words

In other language than Java, it is also known as **Parameterized Type**.

It is a way to write a [[Class]] in a way that leaves some types unspecified.

This effectively allows us to upgrade the syntax of a given [[Class]] in a way that allow us to keep the _same_ inner logic but make it work for **any single type or set of types**.

[[Generics]] are a type of **polymorphism**: [[Parametric Polymorphism]].

A good example of a **Generic** is the `List<E>` class in Java, which can accept different types.

```Java
List<Integer> integerList = new ArrayList<>();
List<Double> integerList = new ArrayList<>();
```

`E` is a [[Parametric Type]]

A generic type must always be instantiated with parameters. These parameters type must be a [[Class]] or the [[Class]] equivalent to the [[Primitive Type in Java|primitive data type]].

Once the **parameters** have been given the once [[Generics]] types become **concrete**.

You can't use [[Primitive Type in Java]] to instantiate any [[Generics|generics]].

In Java, a [[Class]] or [[Interfaces in Java]] whose declaration has one or more _type parameters_ is a **generic** [[Class]] or [[Interfaces in Java]].

We say that a **generic** [[Class]] is a parameterized type. It's **raw** type is _itself_, e.g. :

- [[List]], `List<String>` the **raw** type is list, it is a parameterized type representing a [[List|list(java)]] of [[String in Java|string]].

## Generics in Java in Details

- [[Generics in Java and Variance]]

### How to Set the Domain for Parameters

A boundary is declared with `extends`.

```java
public final class Box<T extends Number> { 
  ... 
}

...
Box<Integer> bi = ... // ok, Integer hérite de Number
Box<Double> bd = ... // ok, Double hérite de Number
Box<String> bs = ... // erreur de compilation, String n'est pas un Number
```

Multiple boundaries

```java
public static <T extends Number & String> ...
```

### Parameters Naming Conventions

- `E` - Element
- `K` - Key
- `N` - Number
- `T` - Type
- `V` - Value
- `S`, `U`, `V`, …

### Generics in Practice

#### Generic Class

```java
import java.util.Objects;

public final class Box<T> {

  private T value;

  public Box(T value) { this.value = value; }

  public T get() { return this.value; }

  public void set(T newValue) { this.value = newValue; }

  @Override
  public String toString() { return "[" + this.value.toString() + "]"; }

  @Override
  public boolean equals(Object o) {
    if (this == o) {
      return true;
    }
    if (o == null || o.getClass() != this.getClass()) {
      return false;
    }
    Box<?> other = (Box<?>)o;
    return this.value.equals(other.value);
  }
A
  @Override
  public int hashCode() {
    return Objects.hash(this.value);
  }
}
```

#### Generic Method

```java
public <R> Box<R> map(Function<T, R> f) {
  return new Box<R>(f.apply(this.t));
}
```

#### Generic Static Method

```java
class Util {
  public static <T> boolean areEquals(Box<T> b1, Box<T> b2) { 
    return b1.equals(b2); // we use areEquals to make sure both types are the same !
  }
}
```

#### Generic Static Factory

```java
public static <T> Element<T> makeHeadElement() {
        Element<T> el = new Element<T>(0);
        return el;
    }
```

#### Generic Equals Method

The [[equals method in Java]] should never raise an exception therefore we cannot use `Box<T>` below because by doing so it will allow Java to have a situation where a `Box<Integer> a = Box<String>` which is something that will **throw an exception**.

```java
@Override
    public boolean equals(Object obj) {
        if (this == obj)
            return true;
        if (obj == null)
            return false;
        if (getClass() != obj.getClass())
            return false;
        Box<?> other = (Box<?>) obj; // important to write this so that it doesn't use raw types
        if (contentOfBox == null) {
            if (other.contentOfBox != null)
                return false;
        } else if (!contentOfBox.equals(other.contentOfBox))
            return false;
        return true;
    }
```

## References

- https://cavat.website/poo/docs/generics/generic-types/#mise-en-oeuvre-dune-box
- <https://cavat.website/poo/docs/poo-basics/poo-by-use/#le-cas-de-list>
- <https://en.wikipedia.org/wiki/Generics_in_Java>
- <https://docs.oracle.com/javase/tutorial/java/generics/types.html>
- Gamma, Helm, Johnson, Vlissides, Design Patterns : Elements of Reusable Object-Oriented Software, 1995.
- Learning Java, 5th Edition By Marc Loy, Patrick Niemeyer, Daniel Leuck
- Effective Java, 3rd Edition By Joshua Bloch
