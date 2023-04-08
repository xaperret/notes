---
date created: Friday, April 29th 2022, 4:59:24 pm
date modified: Friday, April 29th 2022, 6:26:48 pm
---

# Modélisation UML

---

## Qu'est-ce qu'UML

L'UML est un **langage de modélisation graphique** qui permet de créer des **représentations de systèmes**.

Il a été conçu spécifiquement pour le **développement logiciel de conception orientée-objet**.

---

## À quoi sert UML

L'objectif d'UML c'est donc de permettre aux ingénieurs d'avoir des **outils** pour :
- **Analyser, concevoir et implémenter** des systèmes logiciels
- Modéliser la [[Business Logic]]

---

## Qu'est-ce qu'un modèle UML

Un [[model|modèle]] c'est une abstraction des détails d'un [[System|système]] **existant** ou **inexistant**.

Cela signifie que le [[model|modèle]] est soit une représentation de ce qui **est** dans le cas où le [[System|système]] existe déjà.
Ce qui devra être **construit** si le [[System|système]] n'existe pas.

---

```ad-note

### Comment sont construits les modèles UML ?

Avec trois catégories d'éléments qui décrivent des possibilités:
- Classificateurs : décrivent un ensemble d'objets
- Évènements : décrivent un ensemble d'actions 
- Comportements : décrivent un ensemble d'exécutions
```

---

## Types de diagramme UML

- [[Structure Diagram|Diagramme Structuraux]] qui définissent le système décrit par la place des éléments dans le domaine.
- [[Behaviour Diagram|Diagramme Comportementaux]]

---

```ad-note
### Tous les diagrammes d'UML 2.5.1

![[Pasted image 20220429153112.png]]

```

---

## À quoi ressemble un diagramme UML ?

![[Pasted image 20220429152932.png]]
- Exemple ici: [[Package Diagram]]

---

## À quoi ressemble un diagramme UML ?

![[Pasted image 20220429151356.png]]

- `<heading>` (optionnel) : le titre du diagramme
- `<contents area>` : le contenu du diagramme, qui vont définir le type de diagramme
- cadre (optionnel)

---

```ad-attention

Si le cadre n'est pas mis, il ne faut pas mettre de titre.
```

---

## Étude de cas : Bancomat

```ad-important

Après avoir effectué [[Ingenierie des besoins - Presentation]], on a la liste des services que le systèmes doit offrir.

```

---

## Étude de cas : Bancomat

---

## Diagramme des cas d'utilisation

---

## Cas d'utilisation

Un [[Use Case|cas d'utilisation]] représente un ensemble d'actions qui sont réalisés par le système et qui produisent un résultat observable intéressant pour un acteur en particulier.

Ce résultat intéressant permet de remplir un ou plusieurs **besoins** du cahier des charges de l'utilisateur.

---

Diagramme cas d'utilisation

Un [[Use Cases Diagram|diagramme des cas d'utilisation]] permet donc de décrire un ou plusieurs services offerts par le système.

todo add picture here

Dans ce cadre, une autre manière de voir un cas d'utilisation est de le voir comme une classe, l'objet ou instance étant un scénario.

---

## Étude de cas : Bancomat - Diagramme de cas d'utilisation

---

### Scénario

Un scénario peut être décrit textuellement(non spécifié par UML) ou graphiquement par un [[Sequence Diagram]].

---

### Diagramme de séquence
