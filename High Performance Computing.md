---
---

# HIGH PERFORMANCE COMPUTING

## 1 - GÉNÉRALITÉS

## 2 - PARALLÉLISME

## 3 - JULIA

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

### INTRODUCTION AUX PRIMITIVES POINT À POINT ET COLLECTIVES

- Qu'est-ce qu'une primitive de communication point à point ?
	- Les primitives de communication point à point sont des opérations de communication dans un environnement de calcul parallèle où les messages sont échangés directement entre deux processus distincts.
	- Exemple
		- `MPI.Send`
		- `MPI.Recv`
		- `MPI.Sendrecv`
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
