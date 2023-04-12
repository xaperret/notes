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

## 9 - PRIMITIVES COLLECTIVES

## 10 - JULIA CUDA

## 11 - CONVOLUTION CUDA JULIA


## 12 - EXERCICES DE RÉVISION

### THÉORIQUE

#### 01 - PRODUIT SCALAIRE EN MPI

- Qu'est-ce que le produit scalaire ?
	- Le produit scalaire, également appelé produit intérieur ou dot product en anglais, est une opération algébrique qui prend deux vecteurs de même taille et retourne un scalaire (un nombre réel). Le produit scalaire est utilisé dans divers domaines tels que l'algèbre linéaire, la géométrie analytique, la mécanique et le traitement du signal.
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
