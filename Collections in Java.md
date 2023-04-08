---
date updated: 2021-11-13 14:37
---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Java]] [[Control Structures]]
Date Created: 10-10-21

---

# Collection

## Collection in few words

## Collection in details

`java.util` has a set of tools for manipulation or creation of [[Collections in Java|Collections]] called **Java Collections Framework**

![[Pasted image 20211112185438.png]][^1]

There are three categories of [[Class]]

- [[Set|Sets]], which are [[Collections in Java|collections]] that contains **unique** items
  - `HashSet` uses a [[Hashing Table]], which means the [[Method]] `hashCode` **must** be redefined.
  - `SortedSet` provides a [[Total Order|total ordering]] on its elements, which means the elements are ordered according to their [[Natural Ordering in Java]]. Because of that property, [[Object]] must be **`Comparable`**

- [[Queues]]
  - In [[Queues]] operations such as **Insertion**, **Extraction** and **Inspection** can be made on elements. These structure can use [[LIFO]] or [[FIFO]] or [[Priority Queue]].

- [[List]]
  - Sequence of object where user has control on the place where the element is inserted.

To navigates through list, one must implement [[Iterable and Iterator]].

### The behavior of a data structure that implements `Collection`

Is defined by the [[Interface]] as

```java
public interface Collection<E> extends Iterable<E> {
  boolean add(E e);
  boolean remove(Object o);
  boolean isEmpty();
  boolean contains(Object o);
  void clear();
  int size();
  boolean removeAll(Collection<?> c);
  default boolean removeIf(Predicate<? super E> filter);
  default Stream<E> stream();
}
```

We still have the freedom on how to choose how to **insert** and **retrieve** elements, and this makes sense since [[Data Structures]] tend to have different ways of doing these things.

### Abstract Classes

The advantage of [[Abstract Class]] is of course the possibility to hold [[State]], which is not possible with [[Interface]].

![[Pasted image 20211113120810.png]][^2]

For example, if we were to create a `List`-like structure, we could use `AbstractList` and to get the included `Iterator` working, we only have to override:

- Immutable List: `size()` and `get(int)`
- Mutable List: previous [[Method]] plus `set(int, E)` and `remove(int)`

```ad-warning

There are methods that are not abstract, meaning the `default` keyword is used, but their implementation is empty. Meaning calling them will create an exception.
`remove` and `set` are examples of such methods.

```

## References

- <https://cavat.website/poo/docs/collections/collections/>
- <https://docs.oracle.com/javase/8/docs/technotes/guides/collections/overview.html>
- <https://docs.oracle.com/javase/8/docs/api/java/util/SortedSet.html>

[^1]: https://cavat.website/poo/docs/collections/collections/

[^2]: https://cavat.website/poo/docs/collections/collections/#classes-abstraites-offertes-par-le-java-collections-framework
