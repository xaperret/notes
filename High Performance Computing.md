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
