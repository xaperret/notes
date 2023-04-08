---
date created: Sunday, January 16th 2022, 5:54:31 pm
date modified: Sunday, January 16th 2022, 7:31:17 pm
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 16-01-22

---

# Generics in Java and Variance

## Generics in Java and Variance in Few Words

Generics are invariant, meaning the parameter can't change.

```java
List<Number> numbers = new ArrayList<Number>(); // work
List<Number> numbers = new ArrayList<Integer>(); // doesn't work
```

We can authorize [[Variance in Java]] by **explicitly** declaring it when referencing. Let's say we have a [[Method in Java]] that takes a bunch of stuff and prints them

```java
public Class A<E> {
	...
	void printThemAll(Collection<E> c);
	...
}
```

This method right now could only print elements that are made of E. Now if we allow this method to be [[Covariance]], it could take [[Subtype]] of E.

```java
public Class A<E> {
	...
	void printThemAll(Collection<? extends E> c); // Covariant
	void printThemAll(Collection<? super E> c); // Contravariant
	...
}
```

### Generics, Covariance and Contravariance

```java
public Class G<T> {

}

public Class G<T2> {

}
```

- [[Covariance|Covariant]], if `G<T2>` is a [[Subtype]] of `G<T>`
	- `List<? extends Number> banana = List.of(1, 2, 3);` means *I want a type that is a Number, that is a Sub type of Number, meaning Integer extends Number*
- [[Contravariance|Contravariant]], if `G<T>` is a [[Subtype]] of `G<T2>`
	- `List<? super Banane> bananas = fruits;` means *I want a Type who is a Super type of Banana, meaning Banana extends ?*. This also means we can accept or **consume** Fruit because it is the super type and Banana who is the subtype but it will still **produce** only **bananas**!
- [[Invariance|Invariant]], if none are true


| Covariant | Contravariant |
| --------- | ------------- |
|       ![[Pasted image 20220116175934.png]]    |        ![[Pasted image 20220116175949.png]]       |

## Generics in Java and Variance in Details

## References

- https://cavat.website/poo/docs/variance/definition/#covariance-et-contravariance-avec-les-types-g%c3%a9n%c3%a9riques
