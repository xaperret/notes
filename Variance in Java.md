---
date created: Monday, December 20th 2021, 3:00:52 pm
date modified: Saturday, January 22nd 2022, 10:03:27 am
---

- Topic:
- Tags: #review #pn_2_1
- Links: [[Java]]
- Date Created: 20-12-21

---

# Variance in Java

## Variance in Java in Few Words

Let's recall what [[Subtyping Polymorphism]] is. First, [[Polymorphism]] is a way to have different behavior using different types. [[Subtyping Polymorphism]] allows us to still use a method, class, or anything that requires a type by using its [[Subtype]].

```java
Object o = new MySuperCoolObject();
```

What that means is if A **inherits** from B, then **A is a B**, therefore we can **substitute** B for A, the reverse is true, e.g.:

```java
Class A {
	...
}
Class B extends A {
	...
}
```

To do

```java
public static void expectA(A o) {
	...
}
A a = new A();
B b = new B();

expectA(a); // this works
expectA(b); // this works too
```

[[Variance]] is a way for us to do [[Subtyping Polymorphism]]  in more complex situations.

```ad-tip

If the following is true
~~~java
class A { ... }
class B extends A { ... }
~~~

then A can reference B.

```

![[Pasted image 20211220184437.png]]

## Variance in Java in Details

There are different types of [[Variance]]:

- [[Covariance]], allows us to substitute a [[Type]] by its [[Subtype]]
- [[Contravariance]], allows us to substitute a [[Type]] by its [[Superclass]]
- [[Invariance]], forbid any substitution

And to do [[Variance]] might be different from type to type

- [[Generics in Java#Generics and Variance]]

### Static Arrays and Variance

[[Static Array]] are [[Covariance|covariant]]

```java
String[] strs = new String[10];
Object[] objs = strs;
objs[0] = 12; // Runtime => (ArrayStoreException)
String s = strs[0]; 
```

## References

- https://cavat.website/poo/docs/variance/
- https://cavat.website/poo/docs/variance/definition/
