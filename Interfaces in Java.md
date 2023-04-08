---
date created: Sunday, January 16th 2022, 3:56:28 pm
date modified: Sunday, January 16th 2022, 3:57:28 pm
---
- Topic: [#java_programming](https://publish.obsidian.md/#java_programming) [#oop](https://publish.obsidian.md/#oop)  
- Tags: [#review](https://publish.obsidian.md/#review) [#pn_2_1](https://publish.obsidian.md/#pn_2_1)  
- Links: [List](https://notes.xavierperret.dev/List) [Extensibility](https://notes.xavierperret.dev/Extensibility)  
- Date Created: 17-10-21

---

# Interface

## Interface in Few Words

```java
interface Status {
    boolean isOn(); // here is an abstract method

    boolean isOff(); // no need for public keybword

    boolean err(); // or abstract (reserved for abstract class/method)
    
    // here is below a static factory
    static Status process() { // no need for public, default or abstract
        int chance = new Random().nextInt(3);
        if (chance == 0) {
            return new On();
        } else {
            return chance == 1 ? new Off() : new Err("Oups");
        }
    }
}
```

In a way it's a more restricting way to do [Inheritance](https://notes.xavierperret.dev/Inheritance), but for the better, since we can impose stuff on children.

## Interface in Details

An [Interfaces in Java](https://notes.xavierperret.dev/Interfaces+in+Java) or **Protocol** is a **contract** that a [Class](https://notes.xavierperret.dev/Class) is forced to respect.  

This **contract** specifies the **functionality** ([Method](https://notes.xavierperret.dev/Method)), the **behavior** and the **structure** that must be respected.

```ad-warning

Usually the **structure** is set by the [[Field|fields]] but in this case, an [[Interface]] can't contain a state !
Indeed, an [[Interface]] cannot have [[Field|fields]] or [[Constructor|constructors]]

```

The _cool_ thing about [Interfaces in Java](https://notes.xavierperret.dev/Interfaces+in+Java) is that it allows the [Type](https://notes.xavierperret.dev/Type) to be **dynamic**.

An [Interfaces in Java](https://notes.xavierperret.dev/Interfaces+in+Java) can contain

-   [Abstract Method](https://notes.xavierperret.dev/Abstract+Method), meaning a [Method](https://notes.xavierperret.dev/Method) that is not yet implemented
-   Concrete [Method](https://notes.xavierperret.dev/Method) with the `default` [Keyword](https://notes.xavierperret.dev/Keyword)
-   [Static Method](https://notes.xavierperret.dev/Static+Method)
-   [Constant](https://notes.xavierperret.dev/Constant)

The [Keyword](https://notes.xavierperret.dev/Keyword) `public` is useless for [Member](https://notes.xavierperret.dev/Member) of an [Interfaces in Java](https://notes.xavierperret.dev/Interfaces+in+Java) as it is considered [Implicit](https://notes.xavierperret.dev/Implicit).

### The Power of Concrete Methods an Abstract Methods

Implementing a [Method](https://notes.xavierperret.dev/Method) in an [Interface](https://notes.xavierperret.dev/Interfaces+in+Java) is possible since Java 8, thanks to `default`. It is an incredibly powerful tool to fight against **code duplication**.  

Now with this tool it is possible to make it work with [Abstract Method](https://notes.xavierperret.dev/Abstract+Method), expanding the amount of stuff that can be done

```java
public interface RoomDatabase {
  void insert(Room room);
  List<Room> rooms();
  default boolean exists(String id) {
    /*                 +---- Calling an abstract method allows us to not know the implementation and to have more flexibility, meaning if someone creates a different implementation of this method, our concrete method calling an abstract method will still work !!!
                       v                                   */
    for(Room r: this.rooms()){
      if( r.id().equals(id) ) {
        return true;
      }
    }
    return false;
  }
    .....
```

#### Temporary Usage

With such flexibility, we could imagine using this to make [Test](https://notes.xavierperret.dev/Test) before setting up a [Database](https://notes.xavierperret.dev/Database).

### Using Interfaces

When a [Class](https://notes.xavierperret.dev/Class) **uses** an [Interfaces in Java](https://notes.xavierperret.dev/Interfaces+in+Java) it `implements` the [Interfaces in Java](https://notes.xavierperret.dev/Interfaces+in+Java), which means it **respects** the **contract**.  

It is a form of [Inheritance](https://notes.xavierperret.dev/Inheritance).  

So for example, if we have the following [Interfaces in Java](https://notes.xavierperret.dev/Interfaces+in+Java)

```java
interface Resource {
    // abstract method
    String info(); // no need for public keyword => implicit
}
```

Then a [Class](https://notes.xavierperret.dev/Class) who wants to use this [Interface](https://notes.xavierperret.dev/Interfaces+in+Java) needs to

```java
class Room implements Resource {  
    ...
}
```

**AND**

```java
    public String info() { // (RE)DEFINE THE METHOD
        return String.format(
          "room id: %s with capacity: %d", 
          this.id, 
          this.capacity);
    }
}
```

It's also possible to `implements` multiple [Interfaces](https://notes.xavierperret.dev/Interfaces+in+Java) like so

```java
class A implements B, C, D {
...
    }
```

An [Interface](https://notes.xavierperret.dev/Interfaces+in+Java) can also inherits from other [Interfaces](https://notes.xavierperret.dev/Interfaces+in+Java).

```java
interface A extends B, C, D {
...
    }
```

```ad-important

A [[Class]] must implement every [[Abstraction]] in order to become a concrete [[Class]] and therefore be able to be instantiated.

```

### Default Methods

Default [Method](https://notes.xavierperret.dev/Method) are a way to give an implementation to [Method](https://notes.xavierperret.dev/Method), so that some [Method](https://notes.xavierperret.dev/Method) don't have to be implemented in [Class](https://notes.xavierperret.dev/Class) that are bound to the [Interface](https://notes.xavierperret.dev/Interfaces+in+Java).

### Exercises

```java
// MyContrat.java
public interface MyContract {
  
  void myAction();
  
  default void myActionWithLog() { 
    log("Starting...");
    myAction();
    log("Ending...");
  } 

  private void log(String msg) { 
    System.out.println("- " + msg); 
  }
}

// FunnyImpl.java
public class FunnyImpl implements MyContract {
  public void myAction() {
    System.out.println("This is a funny action");
  }
}

// BadImpl.java
public class BadImpl implements MyContract {
  public void myAction() {
    System.out.println("This is a bad action");
  }
}
```

So what does this do

```java
MyContract c = new FunnyImpl();
c.myActionWithLog();

c = new BadImpl();
c.myActionWithLog();
```

```ad-important
collapse: closed

~~~shell
- Starting...
This is a funny action
- Ending....
- Starting...
This is a bad action
- Ending....
~~~

```

```java

public interface Runnable {
  void run();
}

public class Test {
  ...
  void execute() { ... }
}

public class TestAdapter implements Runnable {
    private Test t;

    public run() {
        this.t.execute();
    }

    public TestAdapter(Test t) {
        this.t - t;
    }
}

// App.java
public class App {
   public static void runThat(Runnable r) { 
     System.out.println("Run that: ");
     r.run(); 
     /* do something else */
   }
   public static void runThis(Runnable r) { 
     System.out.println("Run this: ");
     r.run(); 
     /* do something else */
   }
   
   public static void main(String[] args){
      Test t = new Test();
      runThis( t ); // NE COMPILE PAS, Test n'est pas un Runnable
      runThat( t ); // NE COMPILE PAS, Test n'est pas un Runnable
   }
}
```

### See Also

-   [Subtyping Polymorphism](https://notes.xavierperret.dev/Subtyping+Polymorphism)

## References

-   [https://cavat.website/poo/docs/poo-basics/poo-by-use/#le-cas-de-list](https://cavat.website/poo/docs/poo-basics/poo-by-use/#le-cas-de-list)
-   [https://cavat.website/poo/docs/polymorphism/extensibility/#version-poo-en-java](https://cavat.website/poo/docs/polymorphism/extensibility/#version-poo-en-java)
-   [https://cavat.website/poo/docs/polymorphism/interface/#possibilit%c3%a9s](https://cavat.website/poo/docs/polymorphism/interface/#possibilit%c3%a9s)

[Java](https://notes.xavierperret.dev/Java)

[Generics in Java](https://notes.xavierperret.dev/Generics+in+Java)

[Object-Oriented Programming](https://notes.xavierperret.dev/Object-Oriented+Programming)

[List](https://notes.xavierperret.dev/List)

[Inheritance](https://notes.xavierperret.dev/Inheritance)

[Subtyping Polymorphism](https://notes.xavierperret.dev/Subtyping+Polymorphism)

[Abstraction](https://notes.xavierperret.dev/Abstraction)

[Components of a Class](https://notes.xavierperret.dev/Components+of+a+Class)

[Abstract Class](https://notes.xavierperret.dev/Abstract+Class)

[Reference Type in Java](https://notes.xavierperret.dev/Reference+Type+in+Java)

[Functional Interface in Java](https://notes.xavierperret.dev/Functional+Interface+in+Java)

[Natural Ordering in Java](https://notes.xavierperret.dev/Natural+Ordering+in+Java)

[Interface](https://notes.xavierperret.dev/Interface)

[Iterable and Iterator](https://notes.xavierperret.dev/Iterable+and+Iterator)
