---
---

# HIGH PERFORMANCE COMPUTING

## 1 - GÉNÉRALITÉS


## 2 - PARALLÉLISME

- Quel est l'intérêt d'utiliser plus d'unités de calcul pour améliorer les performances de son code ?
	- Car cela n'implique aucune charge de travail supplémentaire.
- Mais quel est le problème de l'augmentation des performances par les unités de calcul ?
	- On ne peut pas le faire indéfinimment.
- Donc si augmenter les performances de son code par les unités de calcul n'est pas la solution, quelle est t'elle ?
	- Le parallélisme
- Qu'est-ce que le parallélisme ?
	- C'est l'action d'exécuter plusieurs tâches en même temps au lieu de les accomplir séquentiellement.
	- Le but final étant d'accélérer la réalisation de ces tâches.
- Qu'est-ce que le problème de balance de charge ?
	- Si les étapes d'un code ne prennent pas le même temps, on attendra donc sur le processus ayant l’étape la plus longue.
- Qu'est-ce que le speedup ?
	- Le speedup (accélération) est une mesure de l'efficacité d'un système de calcul parallèle par rapport à un système séquentiel (ou une version séquentielle d'un algorithme). 
- Quel est l'utilité du speedup ?
	- Le speedup est souvent utilisé pour évaluer la performance d'un algorithme parallèle ou d'un système de calcul parallèle.
- Comment calculer le speedup en latence ?
	- Le speedup est calculé en comparant le temps d'exécution d'un algorithme séquentiel (T₁) avec le temps d'exécution de la version parallèle de l'algorithme (Tₚ) sur P processeurs. La formule du speedup (S) est la suivante :
		- S = T₁ / Tₚ
		- où :
			- T₁ est le temps d'exécution de l'algorithme séquentiel (ou la version séquentielle de l'algorithme)
			- Tₚ est le temps d'exécution de l'algorithme parallèle sur P processeurs
			- S est le speedup
- Quel valeur de speedup serait idéal ?
	- Lorsque S est égal à P, cela signifie que l'algorithme parallèle est P fois plus rapide que l'algorithme séquentiel.
- Qu'est-ce que l'architecture d'un système distribué ?
	- C'est une architecture composée de processeurs interconnectés
- Qu'est-ce qu'un ordinateur parallèle ?
	- C'est une machine composée de processeurs fortement couplés
- Qu'est-ce que la taxonomie de Flynn ?
	- C'est une manière de classer les architectures d'ordinateur
	- Les classes sont basées sur le flux de données et du flux d’instructions :
		- SISD - Single Instruction Single Data : unique flux d’instructions, unique flux de données
		- SIMD - Single Instruction Multiple Data : unique flux d’instructions, multiples flux de données
		- MISD - Multiple Instruction Single Data : multiples flux d’instructions, unique flux de données
		- MIMD - Multiple Instruction Multiple Data : multiples flux d’instructions, multiples flux de données
		
- Qu'est-ce que SISD - Single Instruction Single Data ?
	- Une architecture qui a 
		- unique flux d’instructions, 
		- unique flux de données
		- ![[Pasted image 20230415153532.png]]
- Qu'est-ce que SIMD - Single Instruction Multiple Data ?
	- C'est une architecture qui a 
		- unique flux d’instructions, 
		- multiples flux de données
		- ![[Pasted image 20230415153630.png]]
- Qu'est-ce que MISD - Multiple Instruction Single Data ?
	- C'est une architecture qui a
		- multiples flux d’instructions,
		- unique flux de données
		- ![[Pasted image 20230415153740.png]]
- Qu'est-ce que MIMD - Multiple Instruction Multiple Data ?
	- C'est une architecture qui a
		- multiples flux d’instructions,
		- multiples flux de données
		- ![[Pasted image 20230415153837.png]]
- Qu'est-ce que l'architecture MIMD à mémoire partagée ?
	- Une architecture MIMD où 
		- processeurs synchronisés
		- gestion des conflits d'accès par l'OS
		- programmation conventionnelle
		- ![[Pasted image 20230415154838.png]]
- Qu'est-ce que l'architecture MIMD à mémoire distribuée ?
	- Une architecture MIMD où
		- processeurs non-synchronisés
		- communication par échange de message
		- gestion des échanges de données par le programmeur
		- extensibilité du système par ajout de modules processeur-mémoire
		- ![[Pasted image 20230415154952.png]]
- Quels sont les types de parallélisme ?
	- Le parallélisme de données ou *data parallelism*
	- Le parallélisme de contrôle ou *task parallelism*
- Qu'est-ce que le parallélisme de données ?
	- C'est un type de parallélisme où l'on distribue les données sur différentes unités de calcul
	- Les données sont traitées en parallèle
	- La même opération ou tâche est appliquée sur les données sur chaque unité de calcul
- Quel est l'utilité du parallélisme de données ?
	- Le parallélisme de données s'applique bien aux applications scientifiques où l'on travaille avec des structures de données régulières (tableaux/vecteurs ou matrices)
- Qu'est-ce que le parallélisme de contrôle ?
	- Les unités de calcul exécutent différentes tâches
	- Les tâches sont exécutées de manière concurrent sur les différentes unités de calcul
- Quel est le problème avec Julia et le multithreading ?
	- Julia utilise la librairie BLAS en backend pour les opérations d’algèbre linéaire (comme la multiplication de matrice en exemple). BLAS offre une version parallélisée en mémoire partagée des opérations. 
	- Le problème est que par défaut, Julia utilise tous les threads disponibles sur la machine pour effectuer les calculs. Cela peut être pratique (gain de temps sur les opérations d’algèbre linéaire), mais dans le cas d’une utilisation sur un cluster, cela peut être dangereux (risque d’oversubscribing, création de plus de flux d’exécutions que d’unités de calcul.)


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

- Qu'est-ce que la mémoire distribuée ?
	- Chaque unité de calcul a un espace mémoire privé
	- Programmation en multi-processus. Échange explicite de messages
- Qu'est-ce que la memoire partagée ?
	- Toutes les unités de calcul ont accès à la même mémoire.
	- Programmation possible en multi-processus ou multi-threads (accès à un espace mémoire commun)
- Quel est l'avantage du multi-threads ?
	- Il n'y a pas d'échange explicite de messages (plus "simple")
- Quel est le désavantage du multi-threads ?
	- Toutes les problématique liées à la programmation concurrente.

```julia
using .Threads
using MPI

function mean(A)
    sum = 0.0

    for i in eachindex(A)
        sum += i
    end

    return sum
end

function mean_threads(A)
    sum = 0.0

    @threads for i in eachindex(A)
        sum += i
        # @show threadid()
    end

    return sum
end

function mean_threads_good(A)
    sums = zeros(nthreads()) # [0,0,0,0]

    @threads for i in eachindex(A)
        sums[threadid()] += i
        # @show threadid()
    end

    return sum(sums)
end

# julia -t 8 live_code.jl
function main_simple_threads()
   data = fill(5, 100000000)
    @show data

    @time @show mean(data)
    @time @show mean_threads(data)
    @time @show mean_threads_good(data) 
end
```

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

- Qu'est-ce qu'un cluster ?
	- Un cluster est un ensemble de serveurs ou d'ordinateurs interconnectés travaillant ensemble pour former un système unifié. Les clusters sont utilisés pour améliorer la performance, la disponibilité et la fiabilité des systèmes informatiques en répartissant les charges de travail et les ressources entre plusieurs machines. Ils sont couramment utilisés dans les environnements de calcul haute performance (HPC), les centres de données et pour les applications critiques nécessitant une tolérance aux pannes.

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

- Qu'est-ce qu'une barrière de synchronisation ?
	- Une barrière de synchronisation est un mécanisme de synchronisation utilisé en programmation parallèle et concurrente.
	- Elle permet de garantir que tous les processus ou threads atteignent un certain point dans le code avant de continuer leur exécution. Lorsqu'un processus ou thread atteint la barrière, il se bloque jusqu'à ce que tous les autres processus ou threads atteignent également la barrière. Une fois que tous les processus ou threads sont arrivés à la barrière, ils sont libérés et peuvent continuer leur exécution.
	-  ![[Pasted image 20230413200153.png]]
- Quel est l'utilité d'une barrière de synchronisation ?
	- De synchroniser tous les processus du communicateur
	- Les barrières de synchronisation sont utiles pour coordonner le travail entre les processus ou threads, en particulier dans les situations où certains processus dépendent des résultats d'autres processus. Elles permettent de garantir que toutes les opérations précédentes sont terminées et que les données sont cohérentes avant de poursuivre.
- Comment ça fonctionne ?

```julia
using MPI

MPI.Init()

comm = MPI.COMM_WORLD
rank = MPI.Comm_rank(comm)
size = MPI.Comm_size(comm)

# Faites quelque chose ici...

MPI.Barrier(comm) # Barrière de synchronisation

# Continuez à faire quelque chose ici après que tous les processus aient atteint la barrière

MPI.Finalize()
```

### DIFFUSION (BROADCAST)

- Qu'est-ce qu'une diffusion (broadcast) ?
	- La diffusion (broadcast) est un mécanisme de communication dans les systèmes parallèles et distribués, tel que MPI (Message Passing Interface), où une donnée ou un message est envoyé par un processus (appelé processus racine) à tous les autres processus participant à la communication.
	- Cela permet de partager des informations ou des données à l'échelle de l'ensemble des processus sans qu'ils aient à s'envoyer explicitement des messages individuels.
	- ![[Pasted image 20230413200648.png]]
- Quel est l'utilité de la diffusion ?
	- La diffusion est particulièrement utile pour distribuer des paramètres, des configurations ou des données initiales à tous les processus dans un système parallèle ou distribué. Par exemple, lors du démarrage d'un calcul parallèle, il est courant de diffuser les paramètres de configuration à partir du processus racine vers tous les autres processus.
- Comment ça fonctionne ?

```julia
using MPI

MPI.Init()

comm = MPI.COMM_WORLD
rank = MPI.Comm_rank(comm)
size = MPI.Comm_size(comm)

root = 0 # Processus racine
data = zeros(1) # Tableau pour stocker la donnée diffusée

if rank == root
    data[1] = 42.0 # La donnée à diffuser
end

# Diffuser la donnée à partir du processus racine vers tous les autres processus
MPI.Bcast!(data, root, comm)

@show data[1] # Affiche la donnée diffusée sur tous les processus

MPI.Finalize()

```

### DISPERSION (SCATTER)

- Qu'est-ce qu'une dispersion (scatter) ?
	- La dispersion (scatter) est un mécanisme de communication dans les systèmes parallèles et distribués, comme MPI (Message Passing Interface), où un processus racine distribue différentes parties d'un tableau de données à différents processus de manière équilibrée. 
	- Cela permet de diviser le travail entre les processus en leur attribuant des parties distinctes des données initiales.
- Quel est l'utilité de la dispersion ?
	- La dispersion est souvent utilisée au début d'un calcul parallèle pour distribuer les données d'entrée entre les processus.
	- Chaque processus travaille ensuite sur sa partie des données et, à la fin du calcul, les résultats sont généralement rassemblés (gather) pour former le résultat final.
- Comment ça fonctionne ?

```julia
using MPI

MPI.Init()

comm = MPI.COMM_WORLD
rank = MPI.Comm_rank(comm)
size = MPI.Comm_size(comm)

root = 0 # Processus racine
num_elems = 10 # Nombre total d'éléments à distribuer

sendbuf = nothing
if rank == root
    sendbuf = MPI.UBuffer(collect(1:num_elems), num_elems ÷ size) # Tableau de données à disperser
end

recvbuf = zeros(num_elems ÷ size) # Tableau pour stocker les données reçues

# Disperser les données à partir du processus racine vers tous les autres processus
MPI.Scatter!(sendbuf, recvbuf, comm)

@show recvbuf # Affiche la partie des données reçues sur chaque processus

MPI.Finalize()

```

#### MPI.UBUFFER

- Qu'est-ce que `MPI.UBuffer` ?
	- `MPI.UBuffer` est une fonction de la bibliothèque MPI.jl en Julia qui crée un tampon de type uniforme (UBuffer) à partir des données fournies. Ce tampon est utilisé pour faciliter la communication entre les processus dans les opérations collectives, telles que la dispersion (scatter), le rassemblement (gather), la diffusion (broadcast), etc.
- Comment ça fonctionne ?
	- Voici les deux arguments que la fonction prend en entrée :
	1.  `data`: Il s'agit des données que vous souhaitez inclure dans le tampon. Cela peut être un tableau ou un autre type de données supporté par MPI.jl.
	2.  `count`: C'est le nombre d'éléments du tampon que chaque processus doit recevoir lors de l'utilisation du tampon dans les opérations collectives. Dans le cas d'une dispersion (scatter) ou d'un rassemblement (gather), cela représente généralement le nombre d'éléments que chaque processus recevra ou enverra.

### RÉUNION (GATHER)

- Qu'est-ce que la réunion ?
	- La réunion (gather) est une opération de communication collective dans laquelle chaque processus envoie un élément ou un ensemble d'éléments à un processus racine. Le processus racine rassemble les données de tous les autres processus et les stocke dans un ordre déterminé. Gather est souvent utilisé pour collecter les résultats de calculs effectués par différents processus.
	- ![[Pasted image 20230413201800.png]]


### RÉUNION SUR TOUS (ALL GATHER)

- Qu'est-ce que la réunion sur tous ?
	- La réunion sur tous (allgather) est similaire à la réunion (gather), mais au lieu de rassembler les données uniquement sur le processus racine, chaque processus reçoit une copie de toutes les données rassemblées. Cela signifie que chaque processus a accès aux données de tous les autres processus à la fin de l'opération allgather.
	- ![[Pasted image 20230413201813.png]]
	
### RÉDUCTION (REDUCE)

- Qu'est-ce que la réduction ?
	- La réduction (reduce) est une opération de communication collective où chaque processus envoie un élément ou un ensemble d'éléments à un processus racine. Contrairement à gather, où les données sont simplement rassemblées, dans reduce, une opération spécifiée (telle que l'addition, la multiplication, le minimum, le maximum, etc.) est appliquée aux données envoyées par les processus. Le processus racine reçoit le résultat de l'opération de réduction appliquée aux données de tous les processus.
	- ![[Pasted image 20230413201928.png]]

### EXEMPLE GATHER, ALL GATHER, REDUCE

```julia
using MPI

MPI.Init()

comm = MPI.COMM_WORLD
rank = MPI.Comm_rank(comm)
size = MPI.Comm_size(comm)

root = 0
send_data = rank

# Gather
gather_result = zeros(Int, size)
MPI.Gather!(send_data, gather_result, root, comm)

# Allgather
allgather_result = zeros(Int, size)
MPI.Allgather!(send_data, allgather_result, comm)

# Reduce
reduce_result = Ref{Int}(0)
MPI.Reduce(send_data, reduce_result, MPI.SUM, root, comm)

if rank == root
    println("Gather result: ", gather_result)
    println("Allgather result: ", allgather_result)
    println("Reduce result (sum): ", reduce_result[])
end

MPI.Finalize()

```

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
