---
theme: css/main.css
date created: Thursday, September 22nd 2022, 10:19:14 am
date modified: Thursday, October 13th 2022, 11:55:13 am
---

# Purpose of Machine Learning

- Make computers smart so that they are able to do more and more task

---

# Natural Language

There are more and more "virtual agents", that necessitate to be able to understand customers.

---

# Why Machine Learning

- Understand the human DNA, this way one day it could be possible to find which gene is responsible for a disease.
- Find threats (terrorism, crimes, …)
- Travel, e.g., Expedia a travel agency.

---

# Data Gab

- The amount of data is growing much more than the amount of IT staff growth, which means there is the need for **automatic data analysis**

---

# Data Mining

- Recent field where vocabulary is not fixed

---

# Meeting between multiple field

- Machine learning is the result of multiple fields : Statistics, Data Mining, Data bases, Computing, Data Analysis, Learning, Computer Vision, IA, …

---

# Applications

- Predict how a game will be done, e.g., NBA, Tennis
- Chess, Go, etc…
- Weather.
- Elections.
- Health.
- Product recommendation
- Spam detection
- CAPTCHA

---

# Chocolate and life expectancy

- The way data is interpreted matters a lot, as if there are data missing data will be misinterpreted

---

# Base Components for Data Mining

---

# Neural Network

---

## Perceptron

A perceptron is the basic unit of a neural network.

A perceptron is as a single unit something that takes a number of inputs, and by some processing on these inputs produces one single **binary** output.

---

## Perceptron : Neural Network

Network is composed by
- input layer
- output layer
- intermediary layers, or hidden layers

---

## Perceptron : Everything is a function of something

Each neuron in a hidden layer is the result or function of every single neuron in the last layer.

Therefore, each neuron of the output layer that give an output are result (or function of…) of the neurons' input layer.

---

## Perceptron : Inputs

Each perceptron will have in its input this

$$y = \beta_{0}+\sum{\beta_{i}x_{i}} $$
where
- $\beta_{0}$ is the initial input
- $\beta_{i}$ are the weights for each input
- $x_i$ are the input

---

## Perceptron : Process

The simplest way to reduce these input would be a threshold, so simply the function of the perceptron to reduce its input would be 

$$\phi_{sigma}(u)
\begin{cases}
 \text{1}\\
 \text{0}\\
 \end{cases}
$$


1. Qu'est-ce que l'on peut trouver dans un arbre de décision ?
2.  Qu'est-ce que l'on peut trouver dans un perceptron ?
3. Par quoi se traduit l'apprentissage d'un perceptron ?
4. Qu'est-ce qui se trouve dans un réseau convolutionnel ?
5. C'est quoi pour les réseaux convolutionnels ?
6. Qu'est-ce que c'est une fonction d'activation ?
7. Qu'est-ce qu'une SVN ? 
8. Quel est la marge d'une SVN ?
9. Comment on passe d'une branche à une autre ?
10. Comment fonctionne le + proche voisin ?
	1. Pour un point à tester
	2. On calcule la distance entre lui et tout les points du dataset d'entraînement
	3. On trie les distances en croissant
	4. On garde k distance
	5. La classe majeur dans 4 = La classe du point
11. Comment fonctionne le k-means ?
	1. On crée k clusters
	2. On prend des centroides au bols
	3. On met les points dans les clusters les plus proche
	4. On recalcule les centroides
	5. On recommence à l'étape 3 sauf si 4 n'a pas donnée de nouveaux centroides.