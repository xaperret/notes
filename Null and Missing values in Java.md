---
date modified: Monday, December 13th 2021, 1:18:23 pm
date created: Friday, November 19th 2021, 2:01:17 pm
date modified: Monday, December 13th 2021, 1:18:23 pm
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 13-11-21

---
# Null and Missing Values in Java

## Null and Missing Values in Java in Few Words

## Null and Missing Values in Java in Details

### Bad Practices

In general using `null` is fine unless it is not properly hidden by [[Abstraction]].

If for some reason a box return `null` then it is bad.

#### Arbitrary Values

#### `null` Values

It becomes very hard to find what is the cause of `NullPointerException`.

#### Exceptions

Better but might crash the program.

### Better Way

#### Empty Collection or Object

Title

Using `Optional<T>` we can write code in a better way, cause it makes the app fail at compilation.

```java
public Optional<User> get(int id) { ... }
```

```java
Optional<User> maybeUser = get(42);
if( maybeUser.isPresent() ) {
  User user = maybeUser.get();
  System.out.println( user.email() );
}
```

```java
private Map<Integer, User> maps = ...;

public Optional<User> get(int id) { 
  User u = users.get(id);
  if (u == null) {
    return Optional.empty();
  }
  return Optional.of(u);
}
```

## References

- <https://cavat.website/poo/docs/inconsistencies/optional/>
