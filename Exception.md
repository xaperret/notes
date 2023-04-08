---
date updated: '2021-10-10T23:09:42+02:00'

---

Topic: #java_programming
Tags: #review #pn_1_9
Links: [[Java]]
Date Created: 10-10-21

---

# Exception

## Exception in few words

## Exception in details

### Throw an Exception

```java
public static int countPeople() {
  if( !isDatabaseConnected() ) {
    throw new RuntimeException("Inaccessible database");
  }

  ...

}
```

### Treat an Exception

```java
try {
  int i = scanner.nextInt(); /* l'utilisateur ne rentre pas forcément en entier
                                ==> exception InputMismatchException est retournée */
  System.out.println(i);
} catch (InputMismatchException e) { // traitée ici
  System.err.println(e.toString());  // affichage de l'erreur sur stderr
} finally { // finally = "dans tous les cas..."
  scanner.close(); // ... il est nécessaire de fermer le scanner
}
```

## References

- <https://cavat.website/poo/docs/poo-basics/poo-complements/#exceptions-notions-de-base>

### Parent References

- [[Java#References]]
