---
date updated: '2021-10-07T16:20:29+02:00'
publish: false

---

Topic: #system #system_programming
Tags: #review #literature_note_v1_1
Links: [[@0 Start here]]
Author:
Date Created: 23-09-21

---

# Programmation système

## Introduction à la programmation système

[[API]] => interface mettant visible des fonctionnalités
Un [[Disk]] est géré par un [[File System]] => block de 512 octets
Le [[Kernel]] se charge de vérifier que tel [[Process]] a le droit d'accéder à tel espace. Il gère les périphériques donc.

## Historique

- encodage
- système d'exploitation réecrit en C
- langage C => UNIX, afin de réécrir le système d'exploitation dans un langage de plus haut niveau
- code => utilisé un compilateur qui n'est pas de l'assembleur => portabilité
- AT&T => licensie le code source à qui le demande
  - achat d'UNIX => achat du code source
- une [[Distribution]] c'est un ensemble d'élément (logiciel) autour d'un système d'exploitation => 1er => berkley-software distribution (1982)
- 1983 => vague de privatisation
  - AT&T peut vendre le produit sans le code source
  - entreprise => développe leur propre UNIX
    - HPUX
    - SunOS
    - Irix
    - Xenix
  - => problème il y a séparation des os => programme qui compile sur une os et pas une autre
- créationde norme => STANDARD POSIX (1988)
  - signaux
  - processus
  - accès aux fichiers
  - ligne de commande
  - ...
- privatisation => mouvement gratuit => GNU IS NOT UNIX 1983
  - clone de UNIX, libre et gratuit
  - crée d'abord un éditeur de texte => emacs, puis ls
- premier système graphique pour Unix => X window system 1984
  - client-serveur
    - => interface graphique déporté (fichier distance)
      - le window manager est un serveur, ce qui permet de faire tourner l'application localement ou à distance
  - fonctionne à travers le réseau
- 1991 => linus torvalds => crée un nouveau kernel auxquel GNU s'ajoutera
- Distribution
  - version du noyau
  - version des librairies standards
  - système d'installation
  - système de démarage
  - catalogue d'applications par défaut
  - moyen d'installer les application/mise à jour
  - documentation, support commercial, communauté, etc..

## BASH (BOURNE-AGAIN SHELL)

- peu de ressource
- script
- rapidité de certaines commandes
- opérations complexes

### Permissions - effets

| Fichier |                                                |
| ------- | ---------------------------------------------- |
| Read    | Lire le contenu du fichier                     |
| Write   | Modifier le contenu du fichier (Warning => rm) |
| eXecute | Executer le fichier                            |

| Répertoire |                                                                |
| ---------- | -------------------------------------------------------------- |
| Read       | Lister les noms des fichiers inclus (mais pas les métadonnées) |
| Write      | Créer, renommer ou supprimer les fichiers dans le répertoire   |
| eXecute    | Exécuter le fichier                                            |

![[Pasted image 20210930131854.png]]

![[Pasted image 20210930144157.png]]

## TERMINAL & PSEUDO-TERMINAL

- shell => programme en cours d'execution => affiche les résultats sur un terminal
- terminal => moyen pour afficher le shell

## Flux de sortie

- Un [[Process]] => a une [[Standard Output]] et [[Standard Input]]
- défaut => terminal
- echo => écrire dans la sortie standard

## Flux d'erreur

- redirigé par défaut sur le terminal
- `2>` pour le rediriger, toutes les sorties et entrée ont des numéros
  - entrée standard 0
  - sortie 1
  - erreur 2
- lorsque l'on utilise `>` et `>>` le noyau redirige le flux vers la ressource demandé, ainsi la sortie se fait pas directement sur le hardware

## Système de fichier

A way to organize data on a disk
A disk is just a series of block
We need a way to organize block

| Name | Description                                                                |
| ---- | -------------------------------------------------------------------------- |
| NTFS | Windows                                                                    |
| ext4 | GNU/Linux                                                                  |
| NFS  | [[Network]] file system                                                    |
| IPFS | Interplanetary file system - distributed and decentralized [[File System]] |

### Arborescence

Tout fichier est monté dans une même arborescence.
Windows => disk
Linux => root => tout est monté dans la racine
![[Pasted image 20211007134103.png]]

Sur Linux
![[Pasted image 20211007134235.png]]

## Processus

- Code en langage machine => ram
- Descripteur de fichier => entier faisant référence à un fichier (STIN, STDOUT, STDERR)
- Permissions
- Etat => consommation des ressources, valeur du pointeur d'instructions
- Coeur de proc => 1 processus à la fois => multitâche séquentielle
- ps pour lancer les processus

## JOBS

job -> processus lancé par un shell
lancé en arrière plan avec un &

processus -> variable d'environnement => export => vairable d'environnement du processus

## Questions

- Lorsque l'on fait une redirection, l'on prend un des **data stream** et on le redirige vers une autre entrée.
  - [[Standard Input]]
  - [[Standard Error]]
  - [[Standard Output]]

## References

- [[ISC-332 - Programmation système]]
