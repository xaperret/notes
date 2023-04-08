---
date updated: 2021-11-09 15:09
---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Java]]
Date Created: 09-11-21

---

# Inner Class or Nested Class in Java

## Inner Class or Nested Class in Java in few words

```java
class OuterClass {
    ...
    static class StaticNestedClass {
        ...
    }
    class InnerClass {
        ...
    }
}
```

## Inner Class or Nested Class in Java in details

We design any [[Class]] that is inside the declaration of a [[Type]] or [[Class]] as an [[Inner Class]] or [[Nested Class]]

> An [[Object]] of a [[Nested Class]] always contains a reference to an [[Object]] of the enclosing class, called the enclosing object.

For **non-static [[Nested Class]]**, this means that if we were to create a [[Class]] called _==Car==_ and give it a [[Nested Class]] or [[Inner Class]], then the [[Inner Object]] after being instantiated would keep a **reference** to its _parent [[Class]] ==Car==_  or as Peter Sestoft says the [[Enclosing Object]].

```java
class Car {
	class Wheel {
		public void getEnclosingObject() {
			System.out.println("We can get the Enclosing Object with" + Car.this);
		}
	}
}
```

This is **NOT** true for [[Static Class]] ! A [[Static Class]], because it cannot be instantiated and therefore be an [[Object]] doesn't have a **reference** to an [[Enclosing Object]].
It **can** however, refer to **static member** of the [[Enclosing Class]].

### Iterator

```java
class A {
	public 	Iterator<Integer
}
```
### Implementing an interface that is an Enclosing Class

```java
public interface State {
    static class InitialState implements State {
      public boolean isRunning() { return false; }
      public State nextState() { return new SecondState(); }
    }
    static class SecondState implements State {
      public boolean isRunning() { return true; }
      public State nextState() { return new InitialState(); }
    }
    default boolean isRunning() { return true; }
    public static State initial() { return new InitialState(); }
    State nextState();
}
```

Therefore

```java
State.initial().nextState().isRunning();
State.initial().nextState().nextState().isRunning();
```

### Scope

```java
interface Status {
    default boolean isOn() { // has an implicit public visibility
        return false;
    };

    default boolean isOff() {// has an implicit public visibility
        return false;
    }

    default String getErrorMessage() {// has an implicit public visibility
        throw new UnsupportedOperationException("bad");
    };

    static Erro makeError(String message) {// has an implicit public visibility
        return new Erro();
    }

    static Status process() {// has an implicit public visibility
        int chance = new Random().nextInt(3);
        if (chance == 0) {
            return new On();
        } else {
            return chance == 1 ? new Off() : new Err("Oups");
        }
    }

    class On implements Status {
		// because class On is a nested class of the interface
		// and it implements Status
		// it cannot have no scope-keyword as it would imply private 
        boolean isOn() { // does not compile
            return true;
        }
		public boolean isOff() { // good
			return false;
		}

    }

    class Off implements Status {

    }

    class Erro implements Status {

    }
}

```
## References

- <https://cavat.website/poo/docs/particular-types/>
- <https://cavat.website/poo/docs/particular-types/inner-class/>
- [[@sestoftJavaPrecisely2016]] p. 32
