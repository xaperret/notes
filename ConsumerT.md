---
date updated: 2021-11-10 09:51
---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Functional Interface in Java]]
Date Created: 10-11-21

---

# `Consumer<T>`

## `Consumer<T>` in few words

## `Consumer<T>` in details

[[ConsumerT]] is something that given data with a **Type** does on action on it and returns `void` (`T -> ()`)
Therefore its [[Signature]] is `void accept(T t)`

An example of that is `forEach`, which takes something and does on action and then returns `void`

```java
List<Integer> is = ...
is.forEach( (Integer i) -> System.out.println(i) );
is.forEach( i -> System.out.println(i) );
is.forEach( System.out::println );
```

```java
class DeviceManager {
  List<Resource> resources = ...
  ...
  void apply(Consumer<Resource> consumer) {
    for(Resource r: this.resources) {
      consumer.accept(r);
    }
  }
  ...
}
```

```java
myResourcesManager.apply( resource -> System.out.println(resource.info()) );
myResourcesManager.apply( resource -> database.save(resource) );
```

## References

- <https://cavat.website/poo/docs/particular-types/anonymous/#exemple-dun-consumert>
