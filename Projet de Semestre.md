---
tags: [important]
---
# PROJET DE SEMESTRE

- Méthode de systématisation pour tester les différents textes
	- Plus d'exemples d'apprentissage
	- Quels sont les problèmes ?
		- Date se chevauchent ?
		- Mauvaise date ?
		- Date pas laycan ?
		- Rien trouvé ?
	- Méthode de calcul d'évaluer à quel point les résultats sont bien
		- Score
			- Pour évaluer les méthodes
	- Utiliser des modèles statistiques :
		- Matrice de confusion
- Autres éléments que l'on pourrait identifier
- Pour tout le texte essayer avec des modèles de langues
	- Transformer en annotation
	- Cherche les parties qui correspondent à un laycan
	- Sous-entraîner un modèle existant
	- Entraîner un modèle de texte
- *Option* : Comparer le projet par rapport aux autres prestataires

Les objectifs du laycans :

1. Test
	1. Format dynamique : JSON, CSV, ...
		1. Enlever le nom
		2. Identifiant : hash de l'input
		3. Date ISO
		4. Date plus riche `onw` ?
			1. Intervalle strict, fermé ou ouvert
			2. floue
			3. juste une date
		5. **Reconnu en tant que cargo+laycan** #important
	2. Calculer des scores en fonction des métriques sélectionné
	3. Prédicteur existant -> former une input
2. Explorer d'autres méthodes de parsing
	1. Pour les laycan
	2. Pour le texte en soit
		1. NLP => Spacy.io

## TECHNOLOGIES

- Spacy.io

## SPACY.IO

- Quoi reconnaître ?
- Inside–outside–beginning (tagging) : IOB2

## SCORE

- Main
	- Tout juste ou pas
	- Qu'est-ce qui a bien été détecté
	- Combien on est faux lorsque l'on est faux
	- Oui Laycan, Non Laycan
		- Implique de savoir quel ligne où se trouve le laycan
- ?
	- Score fournie par le backend
	- Un modèle - Un ensemble d'apprentissage - Autre chose ?
	- Développer un classifieur, une méthode de test
	- Automatiquement sur tout le dataset
	- Plus de dataset
- Quel est l'erreur quand c'est pas détecté
- Trop tôt ou trop tard => position du laycan
	- tot
	- tard
	- ???
- Tableau des erreurs => type d'erreur
- Qualité du résultat
- Diagnostique
- Méthode de comparaison de méthodes
	- Score en fonction du paramètre
	- Graphique en colonne