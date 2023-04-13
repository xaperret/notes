---
---

# HIGH PERFORMANCE COMPUTING

## 1 - GÉNÉRALITÉS

## 2 - PARALLÉLISME

## 3 - JULIA
### SHORTCUTS
- [Généralités](#généralités)
- [Bases](#bases)
- [Julia et ses délires avec les caractères spéciaux](#wtf-is-happening-with-symbols)
- [Variables](#variables)
- [Types](#types)
- [Opérateurs](#opérateurs)
- [Boucles](#boucles)
- [Conditions](#conditions)
- [Fonctions](#fonctions)
- [Références](#références)
- [Slides ignorées](#slides-ignorées)

### GÉNÉRALITÉS
Julia est un langage de programmation haut niveau. Il possède plus de 4000 packages (https://julialang.org/packages/). Les points forts de ce langage sont:
- La rapidité (comparable au C)
- Il est haut niveau
- Il est adapté au calcul parallèle.
- Sa polyvalence
### BASES
Lancer julia:
```sh
julia
```
Executer un script:
```sh
julia script.jl
```
### WTF IS HAPPENING WITH SYMBOLS
En julia, il faut savoir que des caractères spéciaux `unicode` peuvent être utilisés avec le préfixe `\`. Certains d'entre eux peuvent avoir une signification particulière et donc influencer votre code.

Exemples non exaustifs:

| signe | code     | signification  |
|-------|----------|----------------|
|   α   |\alpha    |simple symbole  |
|   ÷   |\div      |division entière|
|   ©   |\copyright|simple symbole  |
|   ... |...       |...				|

Voici la liste exaustive: https://docs.julialang.org/en/v1/manual/unicode-input/

### VARIABLES
Déclarer une variable:
```julia
var1 = 42
α = 10 # \alpha = 10
name = "Jean-Marc Michel"
```
Forcer le type d'une expression (assertion):
```julia
forced = (10+10)::Int
```
Conversions de type:
```julia
converted = Float64(10+10)
```

### TYPES
La racine de tous les types en Julia est `Any`.

Pour connaitre le type d'une variable:
```julia
typeof(x)
```

Pour connaitre le sous-type et le super-type d'un type donné:
```julia
supertype(Number)
subtypes(Number)
```

#### NOMBRES
Il existe une hiérarchie des types, faisant que, par exemple, `Int8` sois un sous type de `Integer`.

Voici un diagramme plus précis de la hiérarchie des types numériques: 
![Hierarchie des types](https://upload.wikimedia.org/wikipedia/commons/thumb/4/40/Type-hierarchy-for-julia-numbers.png/1200px-Type-hierarchy-for-julia-numbers.png)

#### CARACTÈRES ET CHAINES DE CARACTÈRES
Déclaration:
```julia
c = `a`
s1 = "Je suis une chaine de caracteres"
```

Interpoler des valeurs dans une chaine de caractères:
```julia
a = 3
b = 8
nom = "Jean-Marc Michel"
println("Bonjour $nom, $a + $b = $(a+b)")
```

Concaténer des chaines:
```julia
string("Bonjour ", "les amis")
string("Nous sommes le ", 12, " janvier")
s1 = "Bonjour "
s2 = "les amis"
s1*s2
"$s1$s2"
```

### OPÉRATEURS
Voici des opérations mathématiques de base:
```julia
3 + 5 # Addition
9 - 8 # Soustraction
8 * 9 # Produit
7 / 9 # Division
7 ÷ 9 # Division entière (obtenu avec \div)
7 % 9 # Modulo
8 ^ 9 # Puissance
```

Voici les différentes égalités possibles:
```julia
3 == 3				# Retourne true
3.0 ≈ 3.00000001	# Retourne true  (\approx)
3.0 ≈ 3.00001		# Retourne false (\approx)
```

Opérateurs bit-à-bit:
```julia
~2         # => -3 # bitwise not
3 & 5      # => 1  # bitwise and
2 | 4      # => 6  # bitwise or
xor(2, 4)  # => 6  # bitwise xor
2 >>> 1    # => 1  # logical shift right
2 >> 1     # => 1  # arithmetic shift right
2 << 1     # => 4  # logical/arithmetic shift left
```

Opérateurs booléens:
```julia
!true   # => false
!false  # => true
1 == 1  # => true
2 == 1  # => false
1 != 1  # => false
2 != 1  # => true
1 < 10  # => true
1 > 10  # => false
2 <= 2  # => true
2 >= 2  # => true
# Les comparaisons peuvent être chainées
1 < 2 < 3  # => true
2 < 3 < 2  # => false
```

### BOUCLES
[TODO]
### CONDITIONS
[TODO]
### FONCTIONS
Syntaxe de base:
```julia
function add(x, y)
    println("x is $x and y is $y")
    x + y # la dernière expression est le return
end
```

Sytaxe compacte:
```julia
add(x, y) = x + y
```

Fonctions internes:
```julia
function create_adder(x)
    function adder(y)
        x + y
    end
    adder
end
```

Appel de fonction: 
```julia 
add(10, 12)
```

### STRUCTURES DE DONNÉES
#### DICTIONNAIRES
Création d'un dictionnaire
```julia
a = Dict("A"=>1, "B"=>2)
a = Dict([("A", 1), ("B", 2)])
```
Ajout et modification d'un élément 
```julia
a["C"] = 17
a["C"] = 2
```
Retirer un élément
```julia
pop!(a, "A") # "!" est une convention Julia indiquant qu'un paramètre est modifié
```

#### TUPLES

```julia
```
```julia
```
```julia
```

#### TABLAUX

```julia
```
```julia
```
```julia
```

### RÉFÉRENCES
- https://juliaacademy.com/
- Documentation https://docs.julialang.org/
- Julia 1.0 Programming Complete Reference Guide
https://www.packtpub.com/product/julia-1-0-programming-complete-reference-guide/9781838822248
- https://en.wikibooks.org/wiki/Introducing_Julia
- https://enccs.github.io/Julia-for-HPC/

### SLIDES IGNORÉES
Cette section répertorie les slides des présentations `03.01-julia.pdf` et `03.02-julia.pdf` qui furent ignorées par question de concision ou par flemme:
- `03.01-julia.pdf`:  8 -  
- `03.02-julia.pdf`:  


## 4 - THREADS EN JULIA

### MPI VS THREAD

- Quel est la différence entre .Thread et MPI ?
	- `Threads` et `MPI` sont deux approches différentes pour la programmation parallèle et la répartition des calculs sur plusieurs unités de traitement.
	- Threads (multithreading) : Le multithreading en Julia est basé sur les threads natifs de l'ordinateur. Julia utilise un modèle de parallélisme à mémoire partagée, ce qui signifie que tous les threads ont accès à la même mémoire. Les threads sont utiles pour exploiter la parallélisation sur un seul nœud ou une seule machine avec plusieurs cœurs de processeur. 
	- MPI (Message Passing Interface) : MPI est une approche basée sur le passage de messages entre des processus distincts. Contrairement au multithreading, MPI utilise un modèle de parallélisme à mémoire distribuée, où chaque processus a sa propre mémoire et communique avec les autres processus en échangeant des messages. MPI est généralement utilisé pour la programmation parallèle sur des clusters de calcul ou des supercalculateurs avec plusieurs nœuds.

#### THREAD

```julia
using Base.Threads

nthreads = nthreads()
@threads for i = 1:10
    println("I'm thread ", threadid(), " and I'm working on iteration ", i)
end
```

#### MPI

```julia
using MPI

MPI.Init()

comm = MPI.COMM_WORLD
rank = MPI.Comm_rank(comm)
size = MPI.Comm_size(comm)

println("Hello world, I am process ", rank, " of ", size)

MPI.Finalize()
```

## 5 - CLUSTER SLURM

## 6 - GAIN LIMITATION PERF

## 7 - RÉSEAUX

## 8 - SÉMANTIQUE PTP 

- Comment envoyer des informations d’un processus à l’autre à l’aide de MPI ?
	- `MPI.send()`
- Comment recevoir des informations d’un autre processus à l’aide de MPI ?
	- `MPI.recv()`
- Envoi non-bloquant
	- `MPI.Isend()` ou `MPI.isend()
- Réception non-bloquante
	- `MPI.Irecv!()`
- Pour chaque opération de communication, MPI considère deux éléments :
	- La complétion locale
	- La complétion globale
- Qu’est-ce que la complétion locale ?
	- C’est le moment où le bloc de mémoire peut être modifié sans perturber la communication
- Qu’est-ce que la complétion globale ?
	- C’est le moment où tous les processus impliqués dans la communication ont atteint la complétion locale.
- Quand est-ce que la complétion locale est atteinte pour l’expéditeur lors de l’utilisation d’un `MPI_Bsend` (buffered send) ?
	- Elle est atteinte lorsque l’expéditeur a finit de copié le message à envoyer dans le buffer
	- Dans cette exemple ce moment coïncide avec la complétion globale.
- Qu’est-ce qu’une fonction non-bloquante ?
	- Une fonction est non-bloquante si elle n’attend pas la complétion locale avant de permettre au programme de poursuivre
- Qu’est-ce qu’une fonction bloquante ?
	- Une fonction est bloquante si et seulement si elle attend la complétion locale avant de se terminer et de permettre au programme de poursuivre
- Qu’est-ce qu’une fonction synchronisée ?
	- Une fonction est synchronisée si elle attend la complétion globale avant de se terminer
- Qu’est-ce que `MPI.Send()` ?
	- C’est une fonction bloquante, possiblement synchronisée permettant d’envoyer des données.
	- `MPI.Ssend()` est
		- bloquant et synchronisé
	- `MPI.Bsend()`
		- bloquant mais non synchronisé

## 9 - PRIMITIVES COLLECTIVES

### INTRODUCTION AUX PRIMITIVES POINT À POINT ET COLLECTIVES

- Qu'est-ce qu'une primitive de communication point à point ?
	- Les primitives de communication point à point sont des opérations de communication dans un environnement de calcul parallèle où les messages sont échangés directement entre deux processus distincts.
	- Exemple
		- `MPI.send`
		- `MPI.recv`
		- `MPI.sendrecv`
- À quoi servent les primitives de communications ?
	- Les primitives de communication point à point permettent aux processus de s'envoyer des messages (ou des données) directement les uns aux autres, sans impliquer d'autres processus dans la communication.
- Dans le contexte du passage de messages, comme avec MPI, ces opérations sont souvent bloquantes ou non bloquantes :
	- Opérations bloquantes
		- L'opération bloquante attend que la communication soit terminée avant de permettre au processus de poursuivre. 
		- Par exemple, lors de l'envoi d'un message, l'opération d'envoi bloquante attend que le message soit envoyé avant de continuer. De même, lors de la réception d'un message, l'opération de réception bloquante attend qu'un message soit reçu avant de continuer.
	- Opérations non bloquantes
		- L'opération non bloquante permet au processus de poursuivre sans attendre que la communication soit terminée. Dans ce cas, le programme doit utiliser des opérations de synchronisation séparées pour s'assurer que la communication est terminée avant d'accéder aux données envoyées ou reçues.
- Qu'est-ce qu'une primitive de communication collective ?
	- Ce sont des opérations de communications tout comme les primitives de communication. Contrairement aux communications point à point, où les messages sont échangés entre deux processus spécifiques, les communications collectives impliquent plusieurs processus qui participent simultanément à l'échange de messages ou à la synchronisation.
	- Exemple
		- `MPI.Barrier`
		- `MPI.Bcast`
		- `MPI.Scatter`
		- `MPI.Gather`
		- `MPI.Allgather`
		- `MPI.Allreduce`
- Quels sont les différentes primitives de communications collective ?
	- Barrière de synchronisation
	- Diffusion
	- Dispersion
	- Réunion
	- Réunion sur tous
	- Réduction

### LES COMMUNICATEURS

- Qu'est-ce qu'un communicateur ?
	- Un communicateur est un groupe de processus
- Chaque processus a un identifiant unique dans un communicateur
- Quel est le communicateur de MPI ?
	- `MPI.COMM_WORLD`, c'est lui qui englobe tous les processus
- Comment peut-on organiser les communicateurs ?
	- En sous groupe.
	- Par exemple
		- ![[Pasted image 20230412154425.png]]
		- Ici on a le communicateur globale `MPI.COMM_WORLD` est en vert
		- Et on divise le communicateur globale en sous communicateurs !

### BARRIÈRE DE SYNCHRONISATION

### DIFFUSION (BROADCAST)

### DISPERSION (SCATTER)

#### MPI.UBUFFER

### RÉUNION (GATHER)

### RÉUNION SUR TOUS (ALL GATHER)

### RÉDUCTION (REDUCE)

## 10 - JULIA CUDA

## 11 - CONVOLUTION CUDA JULIA

## 12 - EXERCICES DE RÉVISION

### THÉORIQUE

#### 01 - PRODUIT SCALAIRE EN MPI

- Qu'est-ce que le produit scalaire ?
	- Le produit scalaire, également appelé produit intérieur ou dot product en anglais, est une opération algébrique qui prend deux vecteurs de même taille et retourne **un scalaire (un nombre réel)**. 
- Comment défini t'on mathématiquement le produit scalaire ?
	- $$ A · B = Σ (A_i * B_i) \text{ pour i allant de 1 à n} $$
- Comment définir le nœud racine (celui de rang 0) initialise les vecteurs a et b ?
- Tout d'abord créons une fonction qui génère un vecteur de taille `n x m` dont les valeurs sont aléatoire

```julia
function GenerateVector(dimN::Int64, dimM::Int64, min::Int64=0, max::Int64=100)
  random_matrix = min .+ (max - min) .* rand(dimN, dimM)
  return random_matrix
end

function GenerateVectorInt(dimN::Int64, dimM::Int64, min::Int64=0, max::Int64=100)
  v = GenerateVector(dimN, dimM, min, max)
  return Int.(floor.(v))
end
```   

- Ensuite, on veut maintenant que notre code supporte les threads

## REFERENCES
