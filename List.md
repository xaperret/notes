---
date updated: '2021-10-10T22:48:50+02:00'

---

Topic: #java_programming
Tags: #review #pn_1_9
Links: [[Java]]
Date Created: 10-10-21

---

# List

## List in few words

## List in details

List is an **ordered collection**, similar to [[Array in Java]] but **manipulable** contrary to [[Static Array]]. **List** are [[Generics]].
This is **NOT** a [[Class]], this **type** is an [[Interfaces in Java]]. This means that to use a variable, we need to actually instantiate an **implementation** of **List**.

```java
// instantiation of List
List<Integer> listOfInteger = new ArrayList<>(); // using ArrayList - the type is infered here
List<Integer> listOfInteger = new ArrayList<Integer>(); // also works but less pretty right ?!
```

`ArrayList` is a class that **implements** the `List` interface and it is also a [[Generics]] ! So, by the definition in [[Generics]] we should instantiate its _type parameter_ but no need with Java 7.0 (Compiler does it for us thanks to => _generic type inference_).

```java
List<Integer> integer;
List<Date> dates;
List<Bim> incredible;
```

- Giving the type by inputting the _type parameter_ is called **instantiating the type** or **invoking the type**.

### The [[Generics]] in List

If we take a look at the Javadoc for `List` here is how it looks like :

```java
    public class List< E > {
       ...
       public void add( E element ) { ... }
       public E get( int i ) { ... }
    }
```

- `E` is a [[Type Parameter]]

## References

- <https://cavat.website/poo/docs/poo-basics/poo-by-use/#le-cas-de-list>
- Learning Java, 5th Edition By Marc Loy, Patrick Niemeyer, Daniel Leuck

### Parent References

- [[Java#References]]
