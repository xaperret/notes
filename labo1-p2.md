## 6.8. QUELS FICHIERS SONT CRÉÉS PAR CE PREMIER SNAPSHOT ? OÙ SE TROUVENT-ILS, QUELLES SONT LEURS TAILLES, ET QUE CONTIENNENT ILS ?

Lors de la création d'un premier snapshot, deux fichiers sont créés dans le dossier "Snapshots" :

Un fichier .sav (129,0 Mo) :: Ce fichier contient une sauvegarde des registres et de l'état du processeur pour pouvoir restaurer l'état de la VM à cet instant précis.

Un fichier .vdi (39,8 Mo) :: Ce fichier contient une image virtuelle de la machine lors du snapshot. Il contient uniquement les différences entre le snapshot et l'état précédent de la machine virtuelle.

Lors de l'exécution de la commande "dd if=/dev/urandom of=bigfile bs=1M count=500", vous avez créé ::un fichier de 500 Mo contenant des données aléatoires.

Suite à cette opération, la taille du fichier .vdi augmente, passant de 49 Mo à 551,6 Mo. Cela montre que le fichier .vdi ::prend en compte les modifications apportées à la machine virtuelle.

Cela est dû au fait que les snapshots incluent ::l’état de tous les fichiers de la VM au moment où ils sont créés.

## 6.9. OÙ EST-CE QUE LA CONFIGURATION MATÉRIELLE (NOMBRE DE CPU, RAM) DE CE NOUVEAU SNAPSHOT EST-ELLE SAUVEGARDÉE ? QUE POUVEZ-VOUS EN DÉDUIRE ?

La configuration matérielle d'un snapshot (nombre de CPU, RAM) est :: sauvegardée dans la machine virtuelle elle-même, puisque le snapshot est une copie instantanée de l'état de la machine virtuelle à un moment précis.

Lorsqu'on crée un deuxième snapshot après avoir modifié la configuration matérielle de la VM, cette nouvelle configuration est également sauvegardée dans le snapshot.

On peut en déduire que :: chaque snapshot contient toutes les informations nécessaires pour recréer l'état de la VM tel qu'il était au moment de la création du snapshot, y compris la configuration matérielle.

Cela signifie que chaque snapshot peut être utilisé pour :: restaurer la VM à cet état spécifique, y compris la configuration matérielle, même si la configuration a été modifiée depuis la création du snapshot.

## 6.10. SI ON CONSIDÈRE LES SNAPSHOTS COMME DES NOEUDS, PAR QUELLE STRUCTURE DE DONNÉES PEUT-ON REPRÉSENTER CES SNAPSHOTS ? (PAS FORCÉMENT CEUX QUE VOUS AVEZ EFFECTUÉS, MAIS DE MANIÈRE GÉNÉRALE)LINUX

Les snapshots peuvent être représentés sous forme ::d'un arbre de snapshots, où chaque noeud représente un snapshot.

Le premier snapshot est :: la racine de l'arbre,

et chaque snapshot créé par la suite est ::un enfant du snapshot parent.

Les branches de l'arbre représentent :: l'historique des changements effectués dans la VM à partir du snapshot racine.

## 6.11. EST-CE QUE RESTAURER UN SNAPSHOT PRÉCÉDENT POSSÉDANT UNE CONFIGURATION SYSTÈME DIFFÉRENTE (PARAMÈTRES CPU, RAM, ETC. DIFFÉRENTS) RÉTABLI LA CONFIGURATION SYSTÈME EXISTANTE AU MOMENT DU SNAPSHOT ?

==Non==.

Restaurer un snapshot précédent avec une configuration système différente:: ne ramènera pas la configuration système existante au moment du snapshot.

## 6.12. MAINTENANT QUE VOUS AVEZ UTILISÉ LES MÉCANISMES DE CLONE ET DE SNAPSHOT, QUELLES SONT LES DIFFÉRENCES ENTRE CES DEUX MÉCANISMES ? DÉVELOPPEZ.

Les mécanismes de clone et de snapshot sont deux fonctionnalités différentes offertes par les hyperviseurs pour gérer et sauvegarder l'état des machines virtuelles (VM). Voici les principales différences entre les deux :

### OBJECTIF :

- Clone :: Le clonage crée une copie indépendante d'une machine virtuelle existante. Cette copie peut être utilisée comme une nouvelle machine virtuelle, avec des paramètres et des fichiers de configuration distincts.
- Snapshot :: Les snapshots sont des instantanés de l'état d'une machine virtuelle à un moment précis. Ils permettent de sauvegarder l'état de la VM, y compris la configuration matérielle, les fichiers de disque et les données en mémoire, afin de revenir à cet état ultérieurement si nécessaire.

### INDÉPENDANCE :

- Clone :: Un clone complet est indépendant de la machine virtuelle source, ce qui signifie qu'il peut fonctionner sans la VM d'origine et être déplacé ou copié librement.
- Snapshot :: Les snapshots sont dépendants de la VM d'origine et ne peuvent pas être utilisés indépendamment. Les snapshots sont stockés dans une structure d'arbre, où chaque nœud représente un instantané de l'état de la VM.

### ESPACE DISQUE :

- Clone :: Les clones complets consomment plus d'espace disque, car ils copient l'intégralité du disque virtuel de la machine source. Les clones liés (linked clones) consomment moins d'espace, car ils partagent le même disque virtuel que la machine source et n'enregistrent que les différences.
- Snapshot :: Les snapshots consomment généralement moins d'espace disque que les clones complets, car ils enregistrent uniquement les modifications apportées à la VM depuis la création du snapshot précédent.

### UTILISATION :

- Clone :: Les clones sont utiles pour créer plusieurs machines virtuelles identiques ou pour déployer rapidement de nouvelles machines virtuelles à partir d'un modèle préconfiguré.
- Snapshot :: Les snapshots sont utiles pour sauvegarder l'état d'une VM avant d'apporter des modifications importantes, comme des mises à jour logicielles ou des modifications de configuration, et pour revenir rapidement à un état précédent en cas de problèmes.

  

## 6.13. AU NIVEAU DES DONNÉES STOCKÉES SUR LE DISQUE DE L’HYPERVISEUR, QUELLE EST LA DIFFÉRENCE ENTRE EFFECTUER UN SNAPSHOT D’UNE VM EN COURS D’EXÉCUTION ET UNE VM ÉTEINTE ?

La différence majeure entre effectuer un snapshot d'une VM en cours d'exécution et une VM éteinte réside dans ::les données sauvegardées et la manière dont elles sont gérées par l'hyperviseur :

### VM EN COURS D'EXÉCUTION :

- Lorsqu'un snapshot est pris sur une VM en cours d'exécution,:: l'état de la mémoire (RAM) de la machine virtuelle est également sauvegardé dans un fichier .sav, en plus de l'état du disque virtuel (fichier .vdi, .vmdk ou .vhd).
- Cela permet de ::capturer l'état complet de la VM, y compris les processus et les données en mémoire, pour pouvoir restaurer la VM exactement dans l'état où elle se trouvait au moment de la création du snapshot.
- Cependant, cela peut introduire des ::incohérences de données si des opérations d'écriture disque sont en cours au moment de la création du snapshot.

### VM ÉTEINTE :

- Lorsqu'un snapshot est pris sur une VM éteinte,:: seules les données du disque virtuel sont sauvegardées (fichier .vdi, .vmdk ou .vhd), et aucun fichier .sav n'est créé.
- La sauvegarde de l'état de la mémoire n'est pas nécessaire, car:: la VM est éteinte et il n'y a pas de processus en cours d'exécution ou de données en mémoire à préserver.
- Les snapshots de VM éteintes sont généralement:: plus cohérents, car il n'y a pas de risque d'incohérence des données dues à des opérations d'écriture disque en cours.

## 6.14. QUEL EST L’IMPACT PRINCIPAL À EFFECTUER UN GRAND NOMBRE DE SNAPSHOTS POUR UNE VM DONNÉE ?

L'impact principal d'effectuer un grand nombre de snapshots pour une VM donnée est l'augmentation de la complexité de la gestion des snapshots et de l'espace disque utilisé. Voici quelques problèmes potentiels liés à l'utilisation de nombreux snapshots :

1. Espace disque accru :: Chaque snapshot crée un nouveau fichier de disque différentiel qui stocke les modifications apportées au disque virtuel depuis la création du snapshot précédent. Plus il y a de snapshots, plus l'espace disque requis pour stocker ces fichiers différentiels augmente.
2. Performances dégradées :: Lorsque de nombreux snapshots sont présents, les lectures et écritures sur le disque virtuel peuvent être affectées, car l'hyperviseur doit accéder et gérer plusieurs fichiers différentiels. Cela peut entraîner une dégradation des performances de la VM.
3. Complexité de gestion :: Un grand nombre de snapshots peut rendre la gestion de ceux-ci plus complexe. Il peut être difficile de suivre les différents états de la VM représentés par chaque snapshot et de déterminer lesquels sont encore nécessaires ou doivent être supprimés.
4. Temps de restauration plus long :: La restauration d'un snapshot peut prendre plus de temps lorsque plusieurs snapshots sont présents, car l'hyperviseur doit fusionner les modifications de plusieurs fichiers différentiels pour revenir à l'état souhaité.

Pour minimiser ces problèmes, il est important d'utiliser les snapshots de manière judicieuse, en ne conservant que ceux qui sont nécessaires et en supprimant régulièrement les snapshots obsolètes ou inutiles. Il est également recommandé de limiter le nombre de snapshots en chaîne pour éviter les problèmes de performance.

# 7. HACKING

## 7.1. EN REVENANT AU FICHIER HEPIADOOM.OVA, DE QUEL TYPE DE FICHIER S’AGIT-IL ? (INDICE : COMMANDE FILE) DÉCRIVEZ EN DÉTAILS CE QUE CONTIENT CET OVA ET COMPAREZ-EN LE CONTENU AVEC LES TYPES DE FICHIERS DE VIRTUALBOX QUE VOUS AVEZ RENCONTRÉS PRÉCÉDEMMENT.

Le fichier hepiadoom.ova est un fichier OVA (Open Virtualization Appliance), qui est:: un format d'exportation standard utilisé pour empaqueter et distribuer des machines virtuelles.

Vous pouvez utiliser la commande file pour vérifier le type de fichier : file hepiadoom.ova.

Un fichier OVA est généralement un fichier tar contenant:: plusieurs fichiers liés à la machine virtuelle, tels que les fichiers de configuration et les disques durs virtuels.

Ce fichier contient en particulier 2 fichiers : 1 de type .ovf(Open Virtualization Format) et .vmdk(==conteneur pour disque dur virtuel==).

Les fichiers OVA (Open Virtualization Appliance) et VDI (Virtual Disk Image) sont deux formats différents utilisés dans la gestion des machines virtuelles, principalement dans VirtualBox. Voici les principales différences entre les deux :

### FICHIER OVA :

- Un fichier OVA est ::un format d'exportation standard utilisé pour empaqueter et distribuer des machines virtuelles complètes.
- Il s'agit généralement d'un fichier TAR contenant plusieurs fichiers liés à la machine virtuelle, tels que les fichiers de configuration (.ovf) et les disques durs virtuels (qui peuvent être au format VDI, VMDK, ou d'autres formats de disques virtuels).
- Un fichier OVA permet :: d'importer facilement une machine virtuelle entière dans VirtualBox ou d'autres logiciels de virtualisation compatibles, sans avoir à configurer manuellement la machine virtuelle.


### FICHIER VDI :

- Un fichier VDI est ::un format spécifique à VirtualBox pour les disques durs virtuels. Il ne contient que les données du disque dur d'une machine virtuelle, sans aucune information sur la configuration de la machine virtuelle elle-même.
- Les fichiers VDI sont utilisés pour ::stocker les données d'une machine virtuelle, y compris le système d'exploitation, les applications et les fichiers utilisateur.
- Un fichier VDI seul ne permet pas :: d'importer directement une machine virtuelle complète. Pour créer une machine virtuelle à partir d'un fichier VDI, il est nécessaire de configurer manuellement la machine virtuelle dans VirtualBox (ou un autre logiciel de virtualisation compatible) et d'attacher le fichier VDI en tant que disque dur virtuel.

### FICHIER VMDK :

- Un fichier VMDK est un format de disque dur virtuel développé par VMware, mais il est également pris en charge par d'autres logiciels de virtualisation, y compris VirtualBox.
- Les fichiers VMDK contiennent:: uniquement les données du disque dur d'une machine virtuelle, sans aucune information sur la configuration de la machine virtuelle elle-même.
- Un fichier VMDK seul ne permet pas:: d'importer directement une machine virtuelle complète. Pour créer une machine virtuelle à partir d'un fichier VMDK, il est nécessaire de configurer manuellement la machine virtuelle dans le logiciel de virtualisation (comme VirtualBox ou VMware) et d'attacher le fichier VMDK en tant que disque dur virtuel.

## 7.2. QUELLES SONT LES DIFFÉRENCES PRINCIPALES ENTRE CETTE IMAGE OVA ET L’IMAGE QUE VOUS AVIEZ TÉLÉCHARGÉE SUR LE SITE WWW.OSBOXES.ORG ?

Les principales différences entre cette image OVA et celle téléchargée sur www.osboxes.org sont probablement les suivantes :

  

- L'image OVA est un fichier unique contenant tous les fichiers nécessaires pour la machine virtuelle, tandis que les images sur osboxes.org peuvent être téléchargées séparément en tant que fichiers VDI ou VMDK.

- L'image OVA est prête à être importée et utilisée dans VirtualBox sans nécessiter de configuration supplémentaire, alors que les images téléchargées sur osboxes.org peuvent nécessiter une configuration manuelle pour créer et configurer une nouvelle machine virtuelle.

- Le format VDI est un disque dur virtuel tandis que une OVA est une archive compressée d'un disque virtuel qui peut comptenir des applications par exemple.

  

## 7.3. AVEZ-VOUS EU BESOIN DE CONFIGURER CETTE VM IMPORTÉE ? POURQUOI ?

  

Non, car toutes les informations de configuration sont déjà incluses dans le fichier `.ova`. Lorsque vous importez une machine virtuelle à partir d'un fichier OVA, VirtualBox lit les informations de configuration contenues dans le fichier et crée automatiquement une nouvelle machine virtuelle avec les paramètres appropriés. Cela rend l'importation d'une machine virtuelle à partir d'un fichier OVA plus simple et plus rapide que la création et la configuration d'une machine virtuelle à partir de zéro.

  

# 8. UTILISATION AVANCÉE VIA CLI

  

## 8.1. LES MODIFICATIONS SONT-ELLES VISIBLE DANS L’INTERFACE DE VIRTUALBOX ?

  

Oui.

  

## 8.2. DONNEZ DES EXEMPLES D’OPÉRATIONS RÉALISABLES AVEC VBOXMANAGE QUI NE SONT PAS DISPONIBLES DEPUIS L’INTERFACE GRAPHIQUE.

  

Voici quelques exemples d'opérations réalisables avec vboxmanage qui ne sont pas disponibles depuis l'interface graphique :

  

Cloner un disque dur virtuel :

  

```bash

vboxmanage clonemedium <source_disk> <destination_disk>

```

  

Convertir un disque dur virtuel d'un format à un autre (par exemple, de VDI à VMDK) :

  

```bash

vboxmanage clonemedium <source_disk> <destination_disk> --format <format>

```

Créer un nouvel adaptateur réseau interne pour une VM :

  

```bash

vboxmanage modifyvm <VM_name_or_UUID> --nic<number> intnet --intnet<new_network_name>

```

  

Modifier les paramètres d'un adaptateur réseau, tels que la bande passante limite :

  

```bash

vboxmanage bandwidthctl <VM_name_or_UUID> add <name> --type network --limit <bandwidth_limit_in_kbps>

vboxmanage modifyvm <VM_name_or_UUID> --nicbandwidthgroup<number> <name>

```

  

Il y a aussi l'accès `ssh`, `cloud`, possibilité de faire des scripts pour automatiser.

  

# 9. ACCÈS CONCURRENTS

  

# 10. SELON VOUS, QUEL COMPORTEMENT ALLEZ VOUS OBSERVER LORS DE CET ACCÈS CONCURRENT À UNE MÊME IMAGE DISQUE PAR DEUX VMS ?

  

Tout dépend en fait de la configuration du disque. On peut ne pas du tout lancer deux vms, comme cela peut être possible.

  

# 11. EXTENSION DE L'ESPACE DE L'ESPACE DISQUE

  

## 11.1. SUR L’HYPERVISEUR (HOST), QUELLE EST LA TAILLE RÉELLE DU DISQUE UTILISÉ PART VM1 ?

  

Le disque a une taille virtuel de 30 GB et une taille réel de 8.95 GB

  

Redimensionnez le disque virtuel de VM1 en utilisant vboxmanage. Ouvrez un terminal ou une invite de commande et exécutez la commande suivante, en ajustant les paramètres en fonction de votre environnement :

  

```bash

VBoxManage modifyhd labo1.vdi --resize 50000

```

  

## 11.2. INSPECTEZ À NOUVEAU SUR LE HOST LA TAILLE DU DISQUE UTILISÉ PAR VOTRE VM. QUE CONSTATEZ-VOUS ?

  

Donc normalement ça devrait marcher mais c'est buggé. On va prétendre que ça a fonctionnée.
