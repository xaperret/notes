---
date updated: '2021-10-12T18:20:19+02:00'

---

Topic: #oop #java_programming
Tags: #review #pn_2
Links: [[Java]] [[Subclass]] [[Inheritance]]
Date Created: 12-10-21

---

# Override

## Override in few words

## Override in details

Redefinition is the action of modifying the **behavior** of an already [[Definition|defined]] [[Method]] by [[Override|overriding]] its original **behavior**.

### Override in practice

Let's start by defining our [[Class|classes]].

```java
public class food {
	visibility void methodFood () {...}
}

public class fruit extends food {
	visibility void methodFruit () {...}
}

public class banana extends fruit {
	visibility void methodBanana() {...}
}
```

A method belonging to a [[Class]] can be overridden in [[Subclass|Subclasses]], but it must check a few conditions:

- Be **at least** as **accessible**[^1] as the overridden method, e.g. if `methodFruit()` is `public` it **couldn't** be **overridden** with a [[Visibility]] of `private`.
- Have the same [[Signature]] as the **overridden** [[Method]]
- Return the same [[Type]] or a [[Subtype]] of the **overridden** [[Method]]'s return.
- No **throws-clause** or no more than the **overridden** [[Method]].

To override the behavior of a [[Method]] it's strongly advised to add `@Override` before it.

## References

### Direct References

- [[@sestoftJavaPrecisely2016]] p. 24
- <https://cavat.website/poo/docs/classes-and-objects/object/#lh%c3%a9ritage>

### Parent References

[^1]: [[Visibility]]
