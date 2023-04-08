---
date updated: 2021-11-21 18:09
---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Collections in Java]] [[Interfaces in Java]]
Date Created: 21-11-21

---

# Iterable and Iterator

## Iterable and Iterator in few words

## Iterable and Iterator in details

The interface `Iterable` is implemented by `Collection`, that means that these data structures can be _parsed_ without care for the specific implementation of the data structure.
An `Iterable` will return an iterator `Iterator`, which navigates through a collection.

```java
public interface Iterable<T> {
    default void forEach(Consumer<? super T> action);
    Iterator<T> iterator();
    default Spliterator<T> spliterator();
}
```

#### Iterator

```java
public interface Iterator<E> {
    default void forEachRemaining(Consumer<? super E> action);
    boolean hasNext();
    E next();
    default void remove(); // by default this makes it impossible to remove an element from the Collection
}
```

An `Iterator` is a mutable [[Object]] that navigates a collection without modifying its state.
It points to the current item and can navigate to the next one with `next`.

Here's an example of how to implement an `Iterator` inside a [[Class]] by using [[Anonymous Class in Java]].

```java
class ArrayListInt implements ListInt, Iterable<Integer> {
  int[] arrayList;
  int lastElement; // lastElement points to the next insert position

  public Iterator<Integer> iterator() {
    Iterator<Integer> it = new Iterator<Integer>() {
      int count = 0;

      @Override
      public boolean hasNext() {
        return count < ArrayListInt.this.size(); // not this.size(); !!
      };

      @Override
      public Integer next() {
        if (hasNext()) { // it's good practice to use this
          return ArrayListInt.this.get(count++); // not this.get(index);!!
        } else {
          throw new NoSuchElementException("No more");
        }
      };
    };
  }
	
...
```

## References
