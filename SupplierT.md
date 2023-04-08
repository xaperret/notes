---
date updated: 2021-11-10 10:03
---

Topic: #java_programming
Tags: #review #pn_2_1
Links: [[Functional Interface in Java]]
Date Created: 10-11-21

---

# SupplierT

## SupplierT in few words

## SupplierT in details

[[SupplierT]] is a type of [[Functional Interface in Java]] that returns something.
`() -> T`
`T get()`

```java
Stream<A> s = Stream.generate( () -> new A() ); // Stream infinis d'objets A. Cependant, le Stream n'a pas encore été parcouru.
List<String> as = s.map( (A a) -> a.toString() ) // description d'une opération. Le Stream n'a toujours pas appelé le supplier
                   .limit(10) // description d'une récupération de 10 éléments. Idem
                   .collect(Collectors.toList()); // Cette fois-ci, les opérations se font à la chaîne
                    
```

```java
public static int process(int a) { return a + a; }
public static int lazySafeProcess(Supplier<Integer> supplier) {
  try {
    return supplier.get() + supplier.get();
  } catch (ArithmeticException ex) {
    return 0;
  }
}

...

int i = process( 3 / 0 ); // Exception ici !
int j = lazySafeDiv( () -> 3 / 0 ); // permet de différer l'exécution de l'expression
//==> j = 0
```

## References

- <https://cavat.website/poo/docs/particular-types/anonymous/#exemples-de-functiontr-et-suppliert-et-predicatet-avec-des-streams>
