---
---

# LVM

## LOGICAL VOLUME MANAGER

- Qu'est-ce qu'un Logical Volume Manager ?
	- Le Logical Volume Manager (LVM) est un **système de gestion de stockage** pour Linux qui permet de gérer et d'organiser des espaces de stockage sur des disques durs ou d'autres dispositifs de stockage.
	- LVM facilite la gestion des partitions et des volumes, en offrant **une abstraction des dispositifs de stockage physiques** et en permettant aux utilisateurs de **créer et de modifier des volumes logiques** sans se soucier des détails spécifiques du matériel
 - Quels sont les avantages de LVM ?
	 1.  **Redimensionnement dynamique des volumes**: LVM permet de redimensionner les volumes logiques à la volée, sans avoir besoin de redémarrer le système ou de démonter les systèmes de fichiers.
	2.  **Gestion des snapshots**: LVM permet de créer des instantanés (snapshots) des volumes logiques, ce qui facilite la sauvegarde et la récupération des données.
	3.  **Allocation de l'espace disque à la demande**: LVM permet d'allouer de l'espace disque aux volumes logiques au fur et à mesure de leurs besoins, ce qui évite le gaspillage d'espace disque et facilite la gestion du stockage.
	4.  **Gestion des volumes répartis sur plusieurs disques**: LVM permet de créer des volumes logiques qui s'étendent sur plusieurs disques ou dispositifs de stockage, offrant ainsi une flexibilité accrue pour la gestion du stockage.

> [!summary]
> - Virtualization de stockage
> - Couche d'abstraction pour le stockage
> - Utilise le device mapper de Linux

## LINUX MULTIPLE DEVICE (MD)

- Qu'est-ce que le Linux Multiple Device (MD)  kernel driver ?
	- Le Linux Multiple Device (MD) kernel driver, également connu sous le nom de "mdadm" ou "software RAID", est un composant du noyau Linux qui permet de **créer et de gérer des ensembles RAID** (Redundant Array of Independent Disks) en utilisant **des dispositifs de stockage** (généralement des disques durs, dispositif physique) directement connectés à la machine.
	- Le MD kernel driver est une solution logicielle pour **la mise en place de RAID**, contrairement aux solutions matérielles basées sur des contrôleurs RAID dédiés.

> [!summary]
> - Gérer des volumes logiques à l'aide de dispositif physique
> - RAID logicielle

## LINUX DEVICE MAPPER (DM)

- Qu'est-ce que le Linux device mapper (DM) kernel driver ?
	- Le Linux Device Mapper (DM) kernel driver est un composant du noyau Linux qui fournit une **infrastructure générique pour la création et la gestion de dispositifs de mappage**. 
	- Le Device Mapper permet de transformer et de mapper des **blocs de stockage** entre des dispositifs sources et des dispositifs cibles. 
	- Cette fonctionnalité est utilisée pour mettre en œuvre diverses fonctionnalités de gestion du stockage, telles que le RAID logiciel, les volumes logiques (LVM), les instantanés de volume et le cryptage de disque.
- Concrètement qu'est-ce que le Linux device mapper (DM) permet de réaliser ?
	- Le Device Mapper permet de créer des **dispositifs de mappage** qui sont des **dispositifs virtuels de blocs** basés sur des dispositifs de **blocs physiques ou d'autres dispositifs de mappage**.
	- Ces dispositifs virtuels peuvent être utilisés pour combiner, diviser, redimensionner, chiffrer ou manipuler de toute autre manière les dispositifs de blocs sous-jacents.
	- Exemples :
		1.  LVM (Logical Volume Manager) : Il permet de créer des volumes logiques flexibles qui peuvent être redimensionnés, déplacés ou combinés selon les besoins. Les volumes logiques reposent sur des groupes de volumes qui, à leur tour, reposent sur des dispositifs de stockage physiques.
		2.  dm-crypt : Il s'agit d'un sous-système de Device Mapper qui fournit des fonctionnalités de cryptage de disque transparentes. dm-crypt est généralement utilisé avec LUKS (Linux Unified Key Setup) pour gérer le cryptage de disque.
		3.  dm-raid : Il prend en charge la création et la gestion de RAID logiciel en utilisant Device Mapper au lieu de MD (Multiple Devices) kernel driver.
		4.  dm-thin : Il permet la création de dispositifs de provisionnement mince (thin provisioning) pour une utilisation plus efficace de l'espace disque.

> [!summary]
> - Mapper les blocks physiques sur des higher-level virtual block devices
> - C'est un driver qui virtualize les block devices
> - LVM, disk encryption, file system snapshots, etc.

## LOGICAL VOLUME MANAGER (LVM2)

- Qu'est-ce que le Logical Volume Manager (LVM2) ?
	- Le Logical Volume Manager (LVM) est un outil de gestion du stockage sous Linux qui facilite l'allocation et la gestion flexibles de l'espace disque sur des disques durs physiques.
 
 > [!summary]
> - Cela utilise DM pour fournir une gestion générique des volumes depuis l'espace utilisateur

## LVM2 ADVANTAGES

- Quel est l'avantage du LVM2 ?
	1.  Gestion flexible du stockage
	2.  Instantanés (Snapshots (copy-on-write))
	3.  Striping et mirroring
	4.  Migration de données
	5.  Provisionnement fin (Thin Provisioning) : Cette fonctionnalité permet de créer des volumes logiques qui utilisent l'espace disque de manière plus efficace en n'allouant l'espace disque qu'au fur et à mesure de son utilisation.
	6. Couche d'abstraction qui cache les détails d'implémentation
- Qu'est-ce que l'on veut dire par Gestion flexible du stockage pour LVM2 ?
	- LVM2 permet de créer, redimensionner, déplacer et supprimer facilement des volumes logiques, ce qui facilite l'adaptation de l'espace disque aux besoins changeants.
- Qu'est-ce que l'on veut dire par Instantanés (Snapshots) pour LVM2  ?
	- LVM2 prend en charge la création d'instantanés de volumes logiques, qui sont des copies de l'état d'un volume logique à un moment donné. Les instantanés sont utiles pour les sauvegardes et les tests, car ils permettent de revenir à un état antérieur du système en cas de problème.
- Qu'est-ce que l'on veut dire par Striping et mirroring pour LVM2 ?
	- LVM2 permet d'améliorer les performances et la redondance du stockage en répartissant les données sur plusieurs disques (striping) et en copiant les données sur plusieurs disques pour la redondance (mirroring).
- Qu'est-ce que l'on veut dire par Migration de données pour LVM2 ?
	- LVM2 facilite la migration des données entre différents disques ou systèmes de stockage sans interruption de service.
- Qu'est-ce que l'on veut dire par Provisionnement fin (Thin Provisioning) pour LVM2 ?
	- Cette fonctionnalité permet de créer des volumes logiques qui utilisent l'espace disque de manière plus efficace en n'allouant l'espace disque qu'au fur et à mesure de son utilisation.
	- Cela permet de crée des systèmes de fichiers plus grand que l'espace disque actuellement disponible
- Quel est le bénéfice pour LVM de " Couche d'abstraction qui cache les détails d'implémentation" ?
	- L'espace de stockage peut être modifié de manière transparente aux applications
	- Agrégation transparente de multiples dispositifs physiques possible
	- Les dispositifs physiques peuvent être changer (hot-swapping)

> [!summary]
> -   Gestion flexible du stockage pour l'adaptation aux besoins changeants
> -   Instantanés (Snapshots) pour les sauvegardes et tests
> -   Amélioration des performances et redondance avec striping et mirroring
> -   Migration de données sans interruption de service
> -   Thin Provisioning pour une utilisation efficace de l'espace disque
> -   Couche d'abstraction pour la transparence des applications et l'agrégation de dispositifs physiques

## LVM2 USAGE

- Pourquoi utilise t'on des LVM ?
	- Car LVM offre une gestion de stockage plus souple, efficace et performante, facilitant la maintenance et l'évolutivité des systèmes Linux. 
	- Et ces avantages sont nécessaire lorsque l'on doit gérer des quantités de données massives dans les data centers.

## TYPES OF LVM2

 - Qu'est-ce que Clustered LVM (CLVM) ?
	 - Clustered LVM (CLVM) est une extension du Logical Volume Manager (LVM) qui permet la gestion de volumes logiques dans un environnement de cluster. CLVM offre les mêmes fonctionnalités que LVM, mais ajoute la capacité de partager et gérer des volumes logiques sur plusieurs nœuds de cluster simultanément.
	 - Dans un cluster, plusieurs serveurs (nœuds) travaillent ensemble pour fournir une haute disponibilité, une meilleure répartition de la charge et une évolutivité. CLVM est particulièrement utile pour les environnements où les données doivent être accessibles et partagées entre plusieurs nœuds, comme dans les cas de serveurs de fichiers, de bases de données ou de machines virtuelles.
 - Qu'est-ce que High-Availability LVM (HA-LVM)
	 - High-Availability LVM (HA-LVM) est une configuration de LVM qui est utilisée en conjonction avec un logiciel de gestion de cluster pour fournir une disponibilité élevée des volumes logiques dans un environnement de cluster.
	 - HA-LVM améliore la disponibilité des données en permettant la détection automatique des défaillances et la récupération des services de stockage sur un autre nœud du cluster en cas de défaillance d'un nœud.
 - Qu'est-ce que le Mirroring ?
	 - Le mirroring (ou mise en miroir) est une technique de redondance de données qui consiste à copier les données d'un disque ou d'une partition sur un autre disque ou une autre partition, en temps réel ou presque.
	 - Cette méthode de réplication des données est utilisée pour assurer la continuité de l'accès aux données et la protection contre la perte de données en cas de défaillance matérielle, comme la panne d'un disque dur.

## LVM2 LAYERS

 - Qu'est-ce qu'un physical volume (LVM terminology) ?
	 - Dans la terminologie LVM (Logical Volume Manager) sous Linux, un Physical Volume (PV) est un disque ou une partition de disque qui est utilisé comme bloc de base pour créer des volumes logiques.
	 - Les Physical Volumes sont généralement des disques durs, des partitions de disque, des périphériques de stockage externes ou d'autres dispositifs de stockage reconnus par le système d'exploitation.
 - Qu'est-ce que le volume group (LVM terminology) ?
	 - Dans la terminologie LVM (Logical Volume Manager) sous Linux, un Volume Group (VG) est un regroupement de plusieurs Physical Volumes (PV). 
	 - Le Volume Group permet d'agréger l'espace de stockage provenant de plusieurs Physical Volumes en une seule entité logique, facilitant ainsi la gestion et l'allocation de l'espace de stockage.
 - Qu'est-ce qu'un logical volume (LVM terminology) ?
	 - Dans la terminologie LVM (Logical Volume Manager) sous Linux, un Logical Volume (LV) est une unité de stockage logique créée à partir de l'espace disponible dans un Volume Group (VG).
	 - Les Logical Volumes sont les éléments sur lesquels vous créez des systèmes de fichiers et les montez dans l'arborescence du système de fichiers de votre système d'exploitation.
	 - Un Logical Volume est un périphérique de blocs exposé, qui est plus ou moins équivalent à une partition de disque.
	 - Il peut être étendu, réparti en bandes (striped), dupliqué (mirrored) ou être un instantané (snapshot), offrant ainsi une flexibilité et des options avancées pour la gestion de l'espace disque.
 - Quels sont les trois couches du modèle LVM ?
	 1.  Physical Volume (PV)
	 2.  Volume Group (VG)
	 3.  Logical Volume (LV)
	 - ![[Pasted image 20230424171530.png]]
	 - ![[Pasted image 20230424171547.png]]
 
> [!summary]
> - Physical Volume (PV) : Il s'agit de la couche de base qui représente les disques physiques ou les partitions sur lesquels LVM opère. Un Physical Volume est un périphérique de stockage (un disque dur, une partition, ou un autre périphérique de stockage) qui est configuré pour être utilisé par LVM.
> - Volume Group (VG) : Cette couche intermédiaire regroupe un ou plusieurs Physical Volumes en une seule entité logique. Un Volume Group agit comme un pool de stockage à partir duquel on peut allouer de l'espace pour créer des Logical Volumes. Un VG peut être étendu ou réduit en ajoutant ou en supprimant des PVs.
> - Logical Volume (LV) : C'est la couche supérieure qui représente les unités de stockage virtuelles créées à partir de l'espace disponible dans un Volume Group. Les Logical Volumes sont les éléments sur lesquels vous créez des systèmes de fichiers et les montez dans la structure du système de fichiers de votre système d'exploitation. Les LVs peuvent être redimensionnés, déplacés, et configurés avec différentes options telles que le striping, le mirroring et les snapshots.

## OTHER TERMINOLOGIES

 - Qu'est-ce que l'unité de base d'allocation de LVM ?
	- L'unité de base d'allocation de LVM (Logical Volume Manager) est appelée "Physical Extent"  (PE) ou Logical extents (LE), représentée par deux nombres : (décalage, longueur).
 - Qu'est-ce qu'un extent ?
	 - Un Physical Extent est un bloc d'espace disque de taille fixe contigüe sur un Physical Volume (PV). Lors de la création d'un Volume Group (VG), tous les PVs inclus sont divisés en Physical Extents de même taille.
 - Quels sont les deux types d'extents ?
	 1.  Physical Extents (PE) : Ce sont les unités de base d'allocation sur un Physical Volume (PV). Chaque Physical Extent est mappé sur un Logical Extent dans un Logical Volume.
	 2.  Logical Extents (LE) : Ce sont les unités de base d'allocation sur un Logical Volume (LV). Les Logical Extents sont mappés sur des Physical Extents dans un ou plusieurs Physical Volumes.
 - Les volumes physique sont divisés en ?
	 - Les volumes physiques (Physical Volumes, PV) dans LVM sont divisés en unités d'allocation appelées Physical Extents (PE).
 - Les volume groups sont des ensemble de ?
	 - Les Volume Groups (VG) dans LVM sont des ensembles de volumes physiques (Physical Volumes, PV).
 - Les volumes logiques sont des ensemble de ?
	 - Les volumes logiques (Logical Volumes, LV) sont des ensembles d'extents logiques qui proviennent d'un Volume Group (VG).
 - Les PE et LE ont la même taille
 - Comment est réalisé le mappage de logical extent à physical extent ?
	 - Le mappage de logical extents (LE) à physical extents (PE) est réalisé par le Logical Volume Manager (LVM). 
	 - LVM maintient une table de mappage qui relie les extents logiques aux extents physiques sur les disques.
	 - ![[Pasted image 20230424171839.png]]

## LVM SNAPSHOTS

- Qu'est-ce qu'un instantané (snapshot) ?
	- Un instantané sauvegarde atomiquement l'état d'un volume logique. 
	- L'instantané est effectué au niveau de la couche de blocs, ce qui le rend indépendant du système de fichiers.
- Quel technique utilise un snapshot LVM ? 
	- Il utilise la technique de copie à l'écriture (COW) et nécessite un nouveau volume logique pour sauvegarder les "changements". 
 - Quel contrainte de taille pour un snapshot LVM ?
	- La taille de ce nouveau volume doit être suffisante pour stocker les changements (10% de la taille du volume logique original est souvent recommandé). 
- Comment fonctionnent les instantanés (snapshots) ?
	- Soit A le volume original et S le volume instantané de A.
	- S stocke les "changements" après la prise de l'instantané. 
	- Les changements ne sont pas les nouvelles données, mais les données de A avant S. Lorsqu'on accède à S (via le montage), on voit le contenu original de A, c'est-à-dire avant que S ne soit pris. 
	- Lorsqu'on accède à A, on voit son contenu actuel. 
	- L'état atomique de A avant S peut alors être sauvegardé. 
	- Le contenu d'un instantané peut être fusionné pour restaurer l'état avant l'instantané, mais cela nécessite de démonter le volume original (A) avant d'appliquer la fusion.
 - Quels sont les cas d'utilisation des instantanés (snapshots) ?
	-   Sauvegarde atomique d'un volume logique sans mettre le volume hors ligne : 
		- mise à niveau du système (susceptible de réussir), 
		- création d'un instantané avant la mise à niveau, 
		- suppression de l'instantané si tout se passe bien, et réversion (fusion) de l'instantané en cas d'échec de la mise à niveau.
	- Changements temporaires à jeter : 
		- créer un instantané du système, 
		- monter l'instantané (par exemple dans /snap), 
		- laisser l'utilisateur utiliser /snap, 
		- puis supprimer l'instantané lorsque l'utilisateur a terminé.
  
# CONTAINERS

- Qu'est-ce que l'Operating System Virtualization ou conteneurisation ?
	- La virtualisation du système d'exploitation, également appelée conteneurisation, est une méthode de virtualisation dans laquelle plusieurs instances isolées (appelées conteneurs) sont exécutées sur un seul hôte, partageant le même noyau du système d'exploitation.
 - Dans la Conteneurisation chaque conteneur dispose de ?
	- Chaque conteneur dispose de son propre espace de processus, de réseau, d'utilisateur et de système de fichiers, ce qui lui permet d'exécuter des applications et des services dans un environnement isolé. 
- Pourquoi dis-t'on que la conteneurisation fournie de l'isolation ?
	- On dit que la conteneurisation fournit de l'isolation car elle permet d'exécuter des applications et des services dans des environnements isolés, appelés conteneurs.
	- Chaque conteneur dispose de sa propre instance des processus, du réseau, des utilisateurs et du système de fichiers. 
	- Cette séparation permet aux conteneurs de fonctionner indépendamment les uns des autres, réduisant ainsi les conflits et les problèmes de compatibilité entre les différentes applications ou services.
 - Quel est la différence entre la virtualization de OS et la virtualization de plateforme ?
	 - Les conteneurs partagent le même kernel mais ont des différentes librairies, utilities, root filesystem, view of process tree, networking, etc...
	 - Les machines virtuelles ont des OS invités différents
	 - ![[Pasted image 20230424192443.png]]
- Quel est l'avantage des conteneurs par rapport aux vms ?
	- Moins d'overhead, mais moins d'isolation.
- Qu'est-ce qu'un conteneur ?
	- A conteneur is a set of processes that are isolated from the host system and other conteneurs

## CONTAINERS AND KERNEL

- Que fournie le Kernel pour limiter l'impact des activités d'un conteneur sur les autres conteneurs ?
	- Le noyau Linux fournit plusieurs mécanismes pour limiter l'impact des activités d'un conteneur sur les autres conteneurs et pour assurer l'isolation et la sécurité entre eux. C'est-à-dire, du resource-management.
 - Quel technologie sont offertes par le noyau Linux pour permettre l'isolation et dont les conteneurs font usage ?
	1.  **Namespaces** 
	2.  **Cgroups (Control Groups)**
	3.  **Capabilities** 
	4.  **Seccomp** 
- Qu'est-ce que Namespaces ?
	- Les namespaces permettent d'isoler les ressources système entre les conteneurs, en leur donnant l'illusion de disposer de leurs propres ressources, telles que les processus, les utilisateurs, les interfaces réseau, les systèmes de fichiers et les groupes de contrôle. 
	- Chaque conteneur dispose de ses propres namespaces, ce qui l'isole des autres conteneurs et empêche les accès non autorisés ou les conflits.
- Qu'est-ce que Control groups (Cgroups) ?
	- Les cgroups permettent de gérer et de contrôler l'utilisation des ressources système, telles que le CPU, la mémoire, le réseau et les entrées/sorties disque, par les conteneurs.
	- Ils offrent la possibilité de limiter la quantité de ressources qu'un conteneur peut utiliser, d'assurer la répartition équitable des ressources entre les conteneurs et d'éviter qu'un conteneur monopolise les ressources au détriment des autres.
	- Exemple
		- CPU time, memory, network bandwidth, I/O bandwidth
- Qu'est-ce que Capabilities ?
	- Les capacités sont un mécanisme de sécurité qui permet de restreindre les privilèges accordés aux processus s'exécutant dans un conteneur. 
	- Elles permettent de décomposer les privilèges root en sous-ensembles plus granulaires, ce qui permet de limiter les actions qu'un processus peut effectuer et d'empêcher les abus de privilèges.
- Qu'est-ce que seccomp ?
	- Seccomp (secure computing mode) est un mécanisme de sécurité qui permet de limiter les appels système autorisés pour un processus s'exécutant dans un conteneur. 
	- En filtrant les appels système, Seccomp empêche les processus malveillants ou défectueux d'exploiter des vulnérabilités du noyau et de compromettre d'autres conteneurs ou le système hôte.

## CONTAINERS AND THEIR RIVALS
 
- Quels sont les bénéfices de la conteneurisation ?
	1.  **Isolation** : Les conteneurs fournissent une isolation entre les applications et les dépendances, ce qui facilite la gestion des applications et réduit les conflits ou les problèmes de compatibilité entre les différentes parties d'un système.
	2.  **Portabilité** : Les conteneurs permettent de créer des applications qui peuvent être facilement déployées sur différents environnements sans modification. Cela facilite le transfert des applications entre les environnements de développement, de test et de production, et garantit un fonctionnement cohérent sur différentes plateformes.
	3.  **Légèreté** : Les conteneurs sont plus légers que les machines virtuelles traditionnelles, car ils partagent le même noyau et n'ont pas besoin d'un système d'exploitation complet pour chaque instance. Cela permet d'économiser de l'espace disque et d'améliorer les performances en réduisant la consommation de ressources système.
	4.  **Densité** : Grâce à leur faible consommation de ressources et à leur légèreté, les conteneurs permettent d'exécuter un plus grand nombre d'applications sur une seule machine physique, ce qui augmente la densité et l'utilisation des ressources.
	5.  **Scalabilité** : Les conteneurs facilitent le redimensionnement des applications en ajoutant ou en supprimant rapidement des instances pour répondre à la demande. Cela permet d'améliorer la performance et la disponibilité des applications tout en réduisant les coûts.
	6.  **Déploiement rapide** : Les conteneurs permettent de déployer rapidement des applications et des services, ce qui accélère le processus de développement, de test et de mise en production.
	7.  **Versioning et gestion des dépendances** : Les conteneurs permettent de gérer efficacement les versions des applications et leurs dépendances, en garantissant que chaque instance dispose de la bonne version des logiciels et des bibliothèques requises.
	8.  **Intégration et automatisation** : Les conteneurs sont compatibles avec divers outils et plateformes d'intégration et de déploiement continu (CI/CD), ce qui facilite l'automatisation des processus de développement, de test et de déploiement.
	- Les plus importants sont : Isolation, portabilité et productivité (performance)
- Pourquoi utilisé les conteneurs par rapport aux machines virtuelles ?
	1.  **Légèreté** : Les conteneurs sont généralement plus légers que les machines virtuelles, car ils partagent le même noyau du système d'exploitation hôte et n'ont pas besoin d'un système d'exploitation complet pour chaque instance. Cela permet d'économiser de l'espace disque et de réduire la consommation de ressources système, ce qui se traduit par une meilleure utilisation des ressources et des performances accrues.
	2.  **Démarrage rapide** : Les conteneurs peuvent être lancés en quelques secondes, tandis que les machines virtuelles peuvent prendre des minutes pour démarrer. Cette rapidité de démarrage facilite le déploiement, la mise à l'échelle et la reprise après sinistre des applications.
	3.  **Portabilité** : Les conteneurs encapsulent les applications et leurs dépendances, ce qui facilite leur déploiement sur différents environnements sans modification. Les machines virtuelles peuvent également être portables, mais elles sont généralement plus lourdes et plus sensibles aux variations de l'environnement sous-jacent.
	4.  **Densité** : Grâce à leur légèreté, les conteneurs permettent d'exécuter un plus grand nombre d'applications sur une seule machine physique que les machines virtuelles. Cela augmente la densité et l'utilisation des ressources, ce qui se traduit par une réduction des coûts d'infrastructure.
	5.  **Scalabilité et orchestration** : Les conteneurs facilitent la mise à l'échelle horizontale des applications en ajoutant ou en supprimant rapidement des instances pour répondre à la demande. Les technologies d'orchestration de conteneurs, comme Kubernetes, facilitent la gestion de ces environnements à grande échelle, tandis que les machines virtuelles peuvent être plus difficiles à gérer et à mettre à l'échelle.
	6.  **Isolation des processus** : Bien que les machines virtuelles offrent une isolation complète au niveau du système d'exploitation, les conteneurs offrent une isolation suffisante pour la plupart des applications tout en étant plus légers et plus rapides. Les conteneurs isolent les processus et les ressources au niveau du noyau du système d'exploitation sans nécessiter de virtualisation complète du matériel.
- Quels sont les limitations des conteneurs ?
	1.  **Isolation moins stricte** : Les conteneurs offrent une isolation des processus et des ressources au niveau du noyau du système d'exploitation, mais cette isolation est généralement moins stricte que celle des machines virtuelles. Cela signifie que les conteneurs peuvent être plus vulnérables aux problèmes de sécurité, en particulier si un conteneur malveillant parvient à compromettre le noyau du système d'exploitation hôte.
	2.  **Compatibilité du système d'exploitation** : Les conteneurs partagent le même noyau que le système d'exploitation hôte, ce qui signifie qu'ils ne peuvent pas exécuter des applications qui nécessitent un système d'exploitation différent ou une version de noyau spécifique. Les machines virtuelles, en revanche, peuvent exécuter n'importe quel système d'exploitation compatible avec le matériel sous-jacent.
	3. **Limitation d'architecture du noyau** : Les conteneurs ne peuvent exécuter que des applications compilées pour l'architecture du noyau de l'hôte. Par exemple, il n'est pas possible d'exécuter un conteneur armhf (ARM) sur un système amd64 (x86-64).
	4. **Dépendance du noyau hôte** : Les conteneurs sont limités aux fonctionnalités du noyau de l'hôte sur lequel ils sont exécutés.
	5. **Fiabilité** : En cas de crash, notamment au niveau du noyau, l'impact est plus important sur les conteneurs que sur les machines virtuelles, car ils partagent le même noyau avec le système d'exploitation hôte.

# DOCKER OVERVIEW

- Quels sont les objectifs de docker ?
	- Docker vise à améliorer 
		- la reproductibilité
		- la portabilité, 
		- la scalabilité 
		- la sécurité
		- l'isolation des applications
- Qu'est-ce que Docker ?
	-   Docker est une plateforme open-source qui :
	    - Automatise le déploiement d'applications
	    - Utilise des conteneurs pour empaqueter et isoler les applications et leurs dépendances
	    - Facilite la portabilité des applications entre différents environnements
	    - Simplifie la gestion et la maintenance des infrastructures informatiques
	    - Encourage la collaboration et le partage d'applications au sein de la communauté de développement
- Quels sont les composants de Docker ?
	- **Docker Engine**
	- **Docker Images**
	- **Docker Containers**
	- **Docker Registries**
	- Dockerfile : Fichier texte contenant les instructions pour construire une image Docker
	- Docker Compose : Outil pour définir et gérer des applications multi-conteneurs avec des fichiers de configuration YAML
	- Docker Hub : Répertoire en ligne de Docker qui permet de partager et de télécharger des images Docker
	- Docker Swarm : Système de gestion et d'orchestration de clusters pour les services Docker
- Docker engine ?
	- Moteur de Docker qui gère la création, l'exécution et la gestion des conteneurs
	- Application client-server
- Docker Images ?
	- Images contenant les applications et leurs dépendances, utilisées pour créer des conteneurs
- Docker Containers ?
	- Instances exécutables des images, qui encapsulent les applications et leur environnement
 - Docker Registries ?
	 - Un registre Docker est un service en ligne qui permet de stocker et de distribuer des images Docker. Il facilite le partage, la distribution et la collaboration autour des images Docker entre les développeurs et les équipes.
	 - Docker Hub est un exemple de registre Docker public, mais il est également possible de créer des registres Docker privés pour stocker et partager des images au sein d'une organisation ou d'un projet spécifique.
-  Docker est livré avec :
	-   un client en ligne de commande (docker) et
	-   une API RESTful pour interagir avec dockerd
- Les clients Docker communiquent avec ?
	- le serveur Docker (daemon dockerd) qui effectue tout le travail
-   Chaque conteneur est instancié à partir
	- d'une image
-   Lorsque l'on ajoute des modifications à une image (A) et que l'on commit (B) on dit que A est le ? de B
	- Le parent de B, car il existe une hiérarchie des images
	- Les images ont une relation parent ↔ enfant
- Les images sont aux conteneurs ce que les classes sont aux
	-   instances en POO (Programmation Orientée Objet) 
- Une image comprend :
	- Un système de fichiers racine complet et isolé (par exemple, système de fichiers minimal fourni par une distribution Ubuntu)
	- Le programme par défaut à exécuter lorsqu'un conteneur est créé à partir d'une image
	- Informations réseau (par exemple, les ports à exposer)
- Comment appelle-t'on le programme par défaut à exécuter lorsqu'un conteneur est créé à partir d'une image ?
	- Le point d'entrée
- Le démon Docker dispose d'un registre interne d'images téléchargées
	- il les met en cache (sur l'hôte) pour éviter de les télécharger à nouveau
-   Un conteneur est
    -   une instance d'une image, similaire à un processus est une instance d'un programme
-   Images
    -   = aspect de construction de Docker → immuable (statique)
-   Conteneurs
    -   = aspect d'exécution de Docker → mutable (dynamique)
-   Docker daemon
    -   Docker daemon = programme dockerd
    - ![[Pasted image 20230424203212.png]]
-   Les conteneurs sont exécutés par
    -   le démon Docker, et non le client Docker
-   Exemple le plus simple
    -   `docker run debian echo "Hello world"`
-   Pour créer un conteneur et lancer un shell bash à l'intérieur :
    -   `docker run -it debian /bin/bash`
-   Exécuter le programme d'un conteneur avec des identifiants d'utilisateur et de groupe spécifiques peut être fait avec l'argument :
    -   `-u uid : gid`
-   Liste tous les conteneurs en cours d'exécution
    -   `docker ps`
    -   `docker ps -a`
-   Pour réexécuter le processus (point d'entrée) d'un conteneur arrêté, ou pour démarrer un conteneur créé via docker create, utilisez :
    -   `docker start`
-   Peut être utile pour démarrer d'autres processus dans un conteneur (par exemple, bash pour explorer ou modifier le système de fichiers) :
    -   `docker exec <args exec> <conteneur> <cmd> <args cmd>`
-   Le paramètre -d de docker run crée un conteneur s'exécutant en arrière-plan (c'est-à-dire détaché)
-   Pour afficher les journaux stdout et stderr pour un conteneur donné :
    -   `docker logs <conteneur>`
-   Un conteneur peut également être arrêté depuis la ligne de commande de l'hôte :
    -   `docker stop`
-   Pour envoyer un signal à un conteneur :
    -   `docker kill`
-   Pour afficher des informations détaillées sur un conteneur et son processus, exécutez :
    -   `docker inspect`
-   Pour supprimer un conteneur arrêté :
    -   `docker rm`
-   Pour supprimer tous les conteneurs sur l'hôte :
    -   `docker rm -f $(docker ps -aq)`

# DOCKER DATA STORAGE

## IMAGE DOCKER

- Qu'est-ce que les images Docker ?
	- Les images Docker sont des systèmes de fichiers racine (rootfs) pour les conteneurs.
	- Les images Docker sont des modèles immuables utilisés pour créer des conteneurs. Chaque conteneur est instancié à partir d'une image qui inclut le système de fichiers, l'application et ses dépendances.
	- Les images Docker sont organisées de manière hiérarchique, avec des relations parents-enfants entre elles. Une image peut être basée sur une autre image, héritant ainsi de ses couches et de son contenu.
- Une image contient :
	- Un système de fichiers complet et isolé (par exemple, le système de fichiers minimal fourni par une distribution Ubuntu).
	- Le programme par défaut à exécuter lorsqu'un conteneur est créé à partir de l'image (également appelé point d'entrée).
	- Des informations réseau (par exemple, quels ports doivent être exposés).
- Que signifie cette phrase "Les images Docker sont des systèmes de fichiers racine (rootfs) pour les conteneurs." ?
	- Cette phrase signifie que les images Docker fournissent le système de fichiers de base (également appelé système de fichiers racine ou rootfs) qui est utilisé pour créer des conteneurs. 
	- Le système de fichiers racine est la partie principale du système de fichiers qui contient tous les fichiers, dossiers et dépendances nécessaires pour exécuter une application ou un service à l'intérieur d'un conteneur.
- Qu'est-ce que signifie l'utilisation de rootfs des Image pour les containers ?
	- Ils n'ont pas besoin d'un noyau + modules : les conteneurs partagent le noyau de l'hôte
	- Ils n'ont pas besoin d'outils ou de scripts d'initialisation
	- Ils doivent être minimaux : inclure uniquement une application et ses dépendances
- Quelles sont les caractéristiques d'une image ?
	-   immuable (en lecture seule)
	-   portable
	-   partageable
	-   stockable
	-   mise à jour possible
- Comment les images sont-elles composées ?
	-   Les images sont constituées de couches
 - Que signifie dire que les images sont constituées de couches ?
	-   Elles sont composées de différentes couches empilées qui peuvent être réutilisées par d'autres images et partagées par les conteneurs
	-   Chaque image étend une image parente (sa première couche)
	- ![[Pasted image 20230425162703.png]]

## LAYERS OF AN IMAGE

-   Comment les couches sont-elles créées ?
    -   Les couches sont créées à partir d'instructions Dockerfile : `RUN, COPY, ADD`
-   Qu'est-ce qu'une couche ?
    -   Une couche est une collection de fichiers et de répertoires
-   Quelles sont les caractéristiques d'une couche ?
    -   immuable
    -   représente un delta des changements par rapport à la couche précédente
    -   est associée et référencée par un hachage généré à partir du contenu de la couche
-   Que se passe-t-il lorsque vous téléchargez une image ?
    -   Chaque couche est téléchargée séparément
- Que se passe-t-il lorsqu'un conteneur est créé ?
	-   une nouvelle couche modifiable est ajoutée au-dessus de l'image
	- ![[Pasted image 20230425163349.png]]
-   Cette couche supérieure est :
    -   appelée la couche conteneur
    -   initialement vide
-   Où sont écrites toutes les modifications effectuées dans un conteneur en cours d'exécution ?
    -   elles sont écrites dans la couche modifiable
-   Que partagent plusieurs conteneurs exécutant la même image ?
    -   Les mêmes couches sous-jacentes immuables
	- ![[Pasted image 20230425163519.png]]
 -   Quelle est la différence entre une image et un conteneur ?
    -   la couche modifiable en haut !
-   Que se passe-t-il lorsqu'un conteneur est supprimé ?
    -   Seule sa couche modifiable est supprimée, mais l'image immuable sous-jacente reste !
-   Comment fonctionne l'héritage d'images ?
    -   De nouvelles images peuvent être créées à partir d'images existantes
-   Qu'est-ce qu'une image de base ?
    -   Les images peuvent également être créées à partir de zéro (à partir d'une archive)
-   Comment inspecter les couches d'une image ?
    -   `docker inspect`
    -   `docker inspect --format "{{json .RootFS.Layers}}" mongo :6`
-   Les pilotes de stockage Docker, dont le défaut est overlay2, utilisent :
    -   Le système de fichiers overlay de Linux
-   Qu'est-ce que le système de fichiers Overlay ?
    -   Il combine des arbres de répertoires supérieurs et inférieurs et présente une vue unifiée
	- ![[Pasted image 20230425164305.png]]
-   Quelle couche est modifiable ?
    -   la couche supérieure
-   Quel fichier/dossier est visible en cas de conflit ?
    -   fichier : uniquement les fichiers dans le répertoire supérieur
    -   dossier : union entre les deux dossiers
- Comment créer un système de fichiers overlay ?
	- `mount -t overlay overlay -o lowerdir =/ low1 :/ low2 :/ low3 , upperdir =/ upper , workdir =/ work / merged`
		- In this example the dir order is 
		- `/ upper / low1 / low2 / low3`, meaning upper is writeable and lowN are the image layers
-   Rootfs indique ?
    -   Répertoire fusionné
-   Quel est le problème avec le système de fichiers overlay ?
    -   La lecture et l'écriture dans la couche modifiable du conteneur sont plus lentes que sur le système de fichiers natif !
-   Que faut-il utiliser pour écrire beaucoup de données ?
    -   Utilisez les volumes Docker pour les charges de travail en écriture intensive plutôt que la couche modifiable du conteneur
-   Pourquoi utiliser des volumes pour écrire beaucoup de données ?
    -   Les volumes écrivent directement sur le système de fichiers de l'hôte → de meilleures performances que l'écriture sur la couche modifiable !
-   Committer des changements
    -   Docker commit permet de valider l'état actuel d'un conteneur dans un fichier image
-   Qu'est-ce que l'état actuel d'un conteneur ?
    -   toutes les couches + couche modifiable supérieure
-   À quoi sert Docker commit ?
    -   utile lors de la modification d'un conteneur à la main et souhaitant rendre ces modifications permanentes
-   Quelle est une meilleure solution à Docker commit ?
    -   Il est préférable d'utiliser les Dockerfiles, mais le commit est utile pour les tests et la préparation
-   Partage de données
    -   Les fichiers créés à l'intérieur d'un conteneur sont stockés sur une couche modifiable du conteneur : les données ne sont pas persistantes lorsque le conteneur est supprimé, il peut être difficile de sortir les données du conteneur
-   Comment partager des données entre plusieurs conteneurs ?
    -   montage de liaison (bind mount)
    -   montage de volume (volume mount)
-   Montage de liaison (bind mount)
    -   Le conteneur peut lire et écrire des fichiers en dehors de la couche modifiable du conteneur
    -   Un fichier ou un répertoire de la machine hôte est monté dans un conteneur
    -   Le fichier ou répertoire est référencé par son chemin absolu complet sur la machine hôte
    -   Efficace, mais repose sur la structure de répertoires du système de fichiers de la machine hôte (point de montage)
-   Montage de volume (volume mount)
    -   Le conteneur peut lire et écrire des fichiers en dehors de la couche modifiable du conteneur
    -   Un volume (local, mais éventuellement distant) est monté dans un conteneur
    -   Mécanisme préféré pour la persistance des données générées par et utilisées par les conteneurs Docker
    -   Le volume est référencé par son nom sur la machine hôte
    -   Les volumes sont entièrement gérés par Docker
-   Volumes vs écriture sur la couche modifiable du conteneur
    -   Les volumes sont souvent un meilleur choix que de persister les données dans la couche modifiable d'un conteneur :
        -   Meilleures performances en lecture-écriture
        -   Ne pas augmenter la taille du conteneur
        -   Le contenu existe en dehors du cycle de vie du conteneur !
-   Transfert de données vers/depuis un volume
    -   Comment copier les données de :
        -   Le système de fichiers local vers un volume ?
        -   Un volume vers le système de fichiers local ?
            -   Copier le contenu du répertoire courant dans le système de fichiers local vers le volume monté dans /shared dans le conteneur : `docker cp . my_conteneur :/ shared /`
            -   Copier le contenu du volume (monté dans /shared dans le conteneur) vers le répertoire courant dans le système de fichiers local : `docker cp my_conteneur :/ shared / .`

# DOCKERFILES

- What is a dockerfile ?
	- A Dockerfile is a text file containing instructions on how to build an image
- Why a Dockerfile?
	- When existing images don’t satisfy our needs
	- To customize an existing image to our needs
- To build an image
	- `docker build`
- To run & create a contenuueur
	- `docker run`
- Dockerfile
	1. Define base image (FROM) 
	2. Set environment variables (ENV) 
	3. Add instructions, e.g. packages to install, etc. (RUN) 
	4. Add files (COPY or ADD) 
	5. Define default command (CMD or ENTRYPOINT)
	6. Indicates ports the contenueur listens to for connections (EXPOSE)

```dockerfile
FROM alpine:3.16
ENV EDITOR=vi
RUN apk update
RUN apk add git
COPY hosts /etc/ 
WORKDIR /home 
CMD git
```

- COPY vs ADD both copy files from a specific location into a Docker image
	- COPY can only copy a local file or directory from the host into the image
	- ADD similar to COPY but more powerful: 
		- can extract a tar archive into the image
		- can specify an URL instead of a local file or directory
- ENTRYPOINT also specify which command to execute when the image is instantiated
- By opposition to CMD, ENTRYPOINT cannot be overriden when starting the contenuueur!
- What is the purpose of ENTRYPOINT since CMD already exists?
	- CMD contents is added to ENTRYPOINT as argument
	- ENTRYPOINT + CMD = a way of specifying default, but overridable arguments

```dockerfile
ENTRYPOINT ["git"]
CMD [" --help "]
```

- The docker build command builds an image from a Dockerfile and a build context
- The build is run by the Docker daemon dockerd (on the host), not the client!
- Docker builds the image myimage:mytag based on the content of a file named Dockerfile in the current directory
	- `docker build . -t myimage : mytag`
- Build context = set of files at a specified PATH or URL • PATH includes any subdirectories • URL includes a git repository and its submodules
- • During build, the client sends the entire context recursively to the Docker daemon!
- Use .dockerignore to specify which files to not sent to the daemon (similar to .gitignore)
- why layers matter
	- • Every RUN, COPY and ADD line creates a new layer
	- each layer represents a delta of the changes from previous layer • what is present in a layer can never be removed!
- docker export
	- exports a contenueur’s filesystem into a tar archive (to stdout) • archive contains the filesystem only
	- docker import
- docker save
	- saves an image’s filesystem into a tar archive (to stdout) • archive contains the various layers’ contents (filesystem) and image meta-data (e.g. entry-point, etc.)
	- docker load
- What's the problem with building an image from a local root filesystem ?
	- The image will likely change over time
- What's the solution to the fact an image will likely change over time ?
	- `docker export alpine :3.16 > alpine_3 .16. tar`

```dockerfile
FROM scratch
ADD alpine_3.16.tar /
CMD sh
```

- What if you want to build a conteneur with a specific program that must be generated from source?
	- multi-stage builds!
- Best practices
	- One conteneur should only solve one problem! • Create Dockerfiles that define stateless images • any state should be kept outside of the container (volumes) • Minimize the image size by removing unecessary files, for instance with Debian-like distributions: apt - get clean && rm -rf / var /lib/ apt/ lists / var / cache / apt • Minimize number of layers (= minimize number of steps) • Use .dockerignore to avoid sending all context files/dirs to the Docker daemon

# VIRTUALISATION - DOCKER BASICS

## EXERCICE 1

### PRENDRE L'IMAGE

```shell
docker search hepia

NAME                    DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
hepia/docker_ex01                                                       0
hepia/hepia-pandoc      convert markdown to pdf with custom template…   0
hepia/docker_ex03                                                       0
hepia/docker_ex02                                                       0
hepia/docker_ex04                                                       0
hepia/ubuntu-java       Ubuntu 19.04 with openjdk and other tools ar…   0
hepia/docker_ex05                                                       0
hepia/hbvar-openms      Open-source software for mass spectrometry a…   0
peiryd/hepia                                                            0
hepiall00001/leonidas   ubuntu                                          0
```

- Cette commande recherche et liste tous les conteneurs disponibles sur Docker Hub qui contiennent le mot-clé "hepia" dans leur nom ou leur description. La liste des conteneurs correspondants est affichée avec leurs noms, descriptions, étoiles, balises "Official" et "Automated".

```shell
docker pull hepia/docker_ex01

Using default tag: latest
latest: Pulling from hepia/docker_ex01
6c40cc604d8e: Pull complete
26532eea736d: Pull complete
Digest: sha256:522c719726dcedf03aecac97aff51dc2bf5f6ab03e8f396fd5a3fb028a4a0769
Status: Downloaded newer image for hepia/docker_ex01:latest
docker.io/hepia/docker_ex01:latest
```

- Cette commande télécharge l'image du conteneur "hepia/docker_ex01" depuis Docker Hub sur votre machine locale. Si aucune balise n'est spécifiée (par exemple, `:latest`), Docker utilisera la balise "latest" par défaut.

### LANCER DES COMMANDES 

```shell
docker run hepia/docker_ex01 pwd
/
```

- Cette commande exécute un conteneur basé sur l'image "hepia/docker_ex01" et lance la commande `pwd` (print working directory) à l'intérieur de ce conteneur. Dans ce cas, la commande `pwd` affiche le répertoire de travail actuel à l'intérieur du conteneur, qui est "/". Cette commande ne lance pas de shell interactif dans le conteneur, mais exécute simplement la commande spécifiée et affiche la sortie.

```shell
docker run hepia/docker_ex01 ls
bin
dev
etc
flag
home
lib
media
mnt
opt
proc
root
run
sbin
srv
sys
tmp
usr
var
```

```shell
ls -ah
.
..
.dockerenv
bin
dev
etc
flag
home
lib
media
mnt
opt
proc
root
run
sbin
srv
sys
tmp
usr
var

ls -ahl
total 68
drwxr-xr-x    1 root     root        4.0K Apr 25 09:51 .
drwxr-xr-x    1 root     root        4.0K Apr 25 09:51 ..
-rwxr-xr-x    1 root     root           0 Apr 25 09:51 .dockerenv
drwxr-xr-x    2 root     root        4.0K Jan 30  2019 bin
drwxr-xr-x    5 root     root         340 Apr 25 09:51 dev
drwxr-xr-x    1 root     root        4.0K Apr 25 09:51 etc
-rw-r--r--    1 root     root          39 Feb  8  2019 flag
drwxr-xr-x    2 root     root        4.0K Jan 30  2019 home
drwxr-xr-x    5 root     root        4.0K Jan 30  2019 lib
drwxr-xr-x    5 root     root        4.0K Jan 30  2019 media
drwxr-xr-x    2 root     root        4.0K Jan 30  2019 mnt
drwxr-xr-x    2 root     root        4.0K Jan 30  2019 opt
dr-xr-xr-x  396 root     root           0 Apr 25 09:51 proc
drwx------    2 root     root        4.0K Jan 30  2019 root
drwxr-xr-x    2 root     root        4.0K Jan 30  2019 run
drwxr-xr-x    2 root     root        4.0K Jan 30  2019 sbin
drwxr-xr-x    2 root     root        4.0K Jan 30  2019 srv
dr-xr-xr-x   11 root     root           0 Apr 25 09:51 sys
drwxrwxrwt    2 root     root        4.0K Jan 30  2019 tmp
drwxr-xr-x    7 root     root        4.0K Jan 30  2019 usr
drwxr-xr-x   11 root     root        4.0K Jan 30  2019 var
```

```shell
docker run hepia/docker_ex01 cat .dockerenv
docker run hepia/docker_ex01 cat flag
Well done !!! you've finished exercice
➜  school
```

### QUESTIONS

#### SUITE AUX DEUX OPÉRATIONS CI-DESSUS, COMBIEN DE CONTAINERS ONT ÉTÉ CRÉÉS ET QUELS SONT LEURS NOMS ET IDS ?

- Comment affiché la liste des conteneurs ?
	- La commande nécessaire pour cette étape est `docker ps -a`

```shell
➜  school docker ps -a | grep ex01
2bc803f65779   hepia/docker_ex01                                                                                   "ls -ahl"                2 minutes ago    Exited (0) 2 minutes ago              optimistic_bell
51a14747ac05   hepia/docker_ex01                                                                                   "cat flag"               2 minutes ago    Exited (0) 2 minutes ago              hardcore_grothendieck
0b1f34a9df67   hepia/docker_ex01                                                                                   "cat .dockerenv"         4 minutes ago    Exited (0) 4 minutes ago              bold_gould
f7ebac069ad6   hepia/docker_ex01                                                                                   "cat .dockerenv"         6 minutes ago    Exited (0) 6 minutes ago              naughty_wing
b852220154cb   hepia/docker_ex01                                                                                   "ls -ah"                 6 minutes ago    Exited (0) 6 minutes ago              angry_ptolemy
2caaaa58bdf0   hepia/docker_ex01                                                                                   "ls home"                6 minutes ago    Exited (0) 6 minutes ago              loving_meninsky
a7e3a18117a0   hepia/docker_ex01                                                                                   "ls"                     8 minutes ago    Exited (0) 8 minutes ago              charming_vaughan
804127024dce   hepia/docker_ex01                                                                                   "pwd"                    12 minutes ago   Exited (0) 12 minutes ago             great_lovelace
```

- Il y a eu autant de containers crée que nous avons lancé la commande.

#### QUEL EST L’ÉTAT DES CONTAINERS ?

- Les conteneurs sont à l'état "exited", car ils ont terminé l'exécution des commandes spécifiées (ls et cat) et se sont arrêtés. 
- Vous pouvez vérifier l'état des conteneurs avec la commande `docker ps -a`.
- L'état des container est arrêté puisque les containers ne restent ouvert que le temps du processus qui est appelé, ici `ls`

#### QUEL EST L’ID DE L’IMAGE UTILISÉE PAR LES CONTAINERS QUE VOUS VENEZ D’EXÉCUTER ?

- Il existe plusieurs manière de récupérer l'ID de l'image utilisée par les containers, soit
	- Cette suite de commande :
		- `docker inspect <container>`
		- `docker inspect <image> hepia/docker_ex01`
	- Soit cette commande
		- `docker image ls hepia/docker_ex01`
- Le résultat est le suivant : `"sha256:cae01e578..."`

#### EST-CE QUE L’ID DE L’IMAGE SERA IDENTIQUE CHEZ VOS CAMARADES DE CLASSE ?

- Oui, si ils ont la même version d'image, puisque c'est un sha256.

#### EST-CE QUE LES NOMS ET IDS DES CONTAINERS SERONT IDENTIQUES CHEZ VOS CAMARADES ?

- Non, les noms et les ID des conteneurs seront différents pour chaque utilisateur et chaque instance de conteneur, car Docker génère des noms et des ID uniques pour chaque conteneur créé.

## EXERCICE 2

### EXÉCUTEZ LE CONTAINER HEPIA/DOCKER_EX03 AVEC UN SHELL (SH) EN MODE INTERACTIF. CRÉEZ ENSUITE LE FICHIER FANTASIO DANS LE RÉPERTOIRE /EX03/ AVEC LA COMMANDE TOUCH. 

- Tout d'abord pour lancer le terminal en interactif on fait la commande suivante :
	- `docker run -it <image> <shell>`
 - Ce qui nous donne :

```shell
➜  school docker run -it hepia/docker_ex03 /bin/sh
/ # ls
bin    etc    flag   lib    mnt    proc   run    srv    tmp    var
dev    ex03   home   media  opt    root   sbin   sys    usr
/ # touch ex03/fantasio
/ 
```

#### QUE SE PASSE-T-IL QUAND VOUS QUITTEZ LE SHELL AVEC CTRL+D ?

- Quand vous quittez le shell avec ctrl+d, le conteneur s'arrête, car le processus principal (le shell) se termine.

```shell
➜  school docker ps -a | grep ex03
f4ed42c7fa1d   hepia/docker_ex03
  "/bin/sh"                2 minutes ago    Exited (0) 14 seconds ago              busy_galois
➜  school
```

### EXÉCUTEZ UN NOUVEAU CONTAINER BASÉ SUR LA MÊME IMAGE QUE PRÉCÉDEMMENT ET NOMMEZ-LE ZORGLUB

- Pour renommer un container il faut faire `docker rename <container name or id> <new name>`

```shell
➜  ~ docker ps
CONTAINER ID   IMAGE               COMMAND     CREATED              STATUS              PORTS     NAMES
8d43cceae149   hepia/docker_ex03   "/bin/sh"   About a minute ago   Up About a minute             agitated_hugle
➜  ~ docker rename 8d43cceae149 zorglub
➜  ~ docker ps
CONTAINER ID   IMAGE               COMMAND     CREATED         STATUS         PORTS     NAMES
8d43cceae149   hepia/docker_ex03   "/bin/sh"   2 minutes ago   Up 2 minutes             zorglub
➜  ~
```

#### EST-CE QUE LE FICHIER /EX03/FANTASIO EXISTE OU PAS ? POURQUOI ?

- Le fichier /ex03/fantasio n'existe pas dans le conteneur zorglub, car vous avez créé un nouveau conteneur basé sur la même image, et l'image ne contient pas le fichier. 
- Les modifications apportées aux conteneurs précédents ne sont pas conservées dans l'image.

#### DANS LE CONTAINER ZORGLUB, EXÉCUTEZ À NOUVEAU TOUCH /EX03/FANTASIO, PUIS PRESSEZ LA COMBINAISON DE TOUCHES CTRL+P CTRL+Q

- La combinaison de touches ctrl+p ctrl+q permet de détacher le terminal du conteneur sans arrêter le conteneur.

```shell
➜  school docker ps -a | grep ex03
650a121ba89d   hepia/docker_ex03
  "/bin/sh"                2 minutes ago   Up 2 minutes                         optimistic_panini
f4ed42c7fa1d   hepia/docker_ex03
  "/bin/sh"                2 hours ago     Exited (0) 2 hours ago               busy_galois
➜  school
```

#### QUEL EST L’ÉTAT (STOPPÉ, EN EXÉCUTION, ETC.) DU CONTAINER ZORGLUB ?

- Après avoir utilisé ctrl+p ctrl+q, le conteneur zorglub reste en exécution. Vous pouvez le vérifier avec la commande `docker ps`.

#### QUEL EST DONC LE RÔLE DE LA COMBINAISON DE TOUCHES CTRL+P CTRL+Q ?

- La combinaison de touches ctrl+p ctrl+q permet de détacher le terminal du conteneur sans arrêter le conteneur.

### ATTACHEZ-VOUS (DOCKER ATTACH) ALORS AU CONTAINER ZORGLUB

#### EST-CE QUE LE FICHIER /EX03/FANTASIO EXISTE ENCORE ?

- Oui, le fichier /ex03/fantasio existe toujours, car vous vous êtes simplement reconnecté au même conteneur qui était en cours d'exécution.
- 

```shell
➜  school docker attach 650a121ba89d
/ # ls
bin    etc    flag   lib    mnt    proc   run    srv    tmp    var
dev    ex03   home   media  opt    root   sbin   sys    usr
/ # ls ex03/
fantasio
/ #
```

### DANS UN NOUVEAU TERMINAL, ATTACHEZ-VOUS À NOUVEAU AU CONTAINER ZORGLUB. PLACEZ CÔTE À CÔTE LES DEUX TERMINAUX DANS LESQUELS VOUS ÊTES ATTACHÉ AU CONTAINER ZORGLUB ET TAPEZ DES CARACTÈRES AU CLAVIER

#### QU’OBSERVEZ-VOUS ET QUE POUVEZ-VOUS DONC EN DÉDUIRE ?

- Lorsque vous tapez des caractères dans l'un des terminaux attachés, vous verrez les mêmes caractères apparaître dans l'autre terminal. Cela montre que les deux terminaux sont connectés au même conteneur et partagent le même environnement.

### EXÉCUTEZ LA COMMANDE DOCKER EXEC -IT ZORGLUB SH
#### EST-CE QUE LE FICHIER /EX03/FANTASIO EXISTE TOUJOURS ?

- Oui, le fichier /ex03/fantasio existe toujours, car `docker exec` exécute simplement une nouvelle commande (dans ce cas, un nouveau shell) dans le conteneur en cours d'exécution sans modifier l'état du conteneur.

#### COMBIEN DE SHELLS SONT EN COURS D’EXECUTION (AIDE: PS) ?

- Il y en a deux qui sont ouvert !

```shell
/ # ps
PID   USER     TIME  COMMAND
    1 root      0:00 /bin/sh
   16 root      0:00 sh
   23 root      0:00 ps
/ #
```

```shell
/ # ps aux | grep -i 'sh' | grep -v grep | wc -l
2
/ #
```

#### QUELLE EST LA DIFFÉRENCE ENTRE LES COMMANDES ATTACH ET EXEC ?

- La commande `attach` permet de se connecter à un conteneur en cours d'exécution et d'interagir avec son processus principal (généralement un shell). stdin et stdout sont redirigés.
- La commande `exec` permet d'exécuter une nouvelle commande ou un nouveau processus dans un conteneur en cours d'exécution sans interférer avec le processus principal.

### TERMINEZ LE SHELL (P.EX. AVEC CTRL+D) DANS LEQUEL VOUS AVIEZ EXÉCUTÉ DOCKER EXEC ... AUPARAVANT
#### EST-CE QUE LE CONTAINER ZORGLUB EST TOUJOURS EN EXÉCUTION ?

- Oui, le conteneur zorglub est toujours en exécution, car la fin d'un shell lancé avec `docker exec` n'affecte pas le processus principal du conteneur.

```shell
➜  ~ docker ps
CONTAINER ID   IMAGE               COMMAND     CREATED         STATUS         PORTS     NAMES
8d43cceae149   hepia/docker_ex03   "/bin/sh"   9 minutes ago   Up 9 minutes             zorglub
➜  ~
```

### EXÉCUTEZ UN NOUVEAU SHELL DANS LE CONTAINER AVEC LA COMMANDE DOCKER EXEC -IT ZORGLUB SH, PUIS ALLEZ DANS LE TERMINAL OÙ VOUS AVIEZ AVIEZ RÉALISÉ LE DOCKER ATTACH PLUS HAUT. TERMINEZ ALORS CE SHELL AVEC CTRL+D. 

#### EST-CE QUE LE CONTAINER ZORGLUB EST TOUJOURS EN EXÉCUTION ?  QUE POUVEZ-VOUS EN CONCLURE ? 

- Non, lorsque vous terminez le shell principal (celui avec `docker attach`), cela entraîne également la fermeture du conteneur. Cela est dû au fait que le processus principal du conteneur (dans ce cas, le shell) a été terminé, et lorsque le processus principal se termine, le conteneur s'arrête également.
- Dans ce cas, lorsque vous terminez le shell avec `ctrl+d` après avoir réalisé le `docker attach`, le conteneur zorglub s'arrêtera, et les autres shells ouverts avec `docker exec` seront également fermés. Vous pouvez vérifier l'état du conteneur en utilisant la commande `docker ps -a` et constater qu'il est arrêté.

```shell
➜  ~ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
➜  ~
```

### DÉMARREZ LE CONTAINER ZORGLUB AVEC LA COMMANDE START -AI (ATTACH + INTERACTIVE)

#### LE FICHIER /EX03/FANTASIO EXISTE-T-IL TOUJOURS ?

- Le fichier /ex03/fantasio devrait toujours exister, car il a été créé dans un conteneur précédent qui a été démarré avec la commande `start -ai`. Les modifications apportées aux conteneurs sont persistantes tant que le conteneur n'est pas supprimé.

```shell
➜  ~ docker start -ai zorglub
/ # ls ex03/
fantasio
/ #
```

- `docker start -ai`
	- attach
	- interactive

## EXERCICE 3

### EXÉCUTEZ UN CONTAINER BASÉ SUR L’IMAGE ALPINE 3.17 EN SPÉCIFIANT DE LE DÉTRUIRE UNE FOIS TERMINÉ. VÉRIFIEZ QUE VOUS UTILISEZ LA BONNE DISTRIBUTION EN INSPECTANT LE CONTENU DU FICHIER /ETC/OS-RELEASE

```shell
➜  ~ docker pull alpine:3.17
3.17: Pulling from library/alpine
f56be85fc22e: Pull complete
Digest: sha256:124c7d2707904eea7431fffe91522a01e5a861a624ee31d03372cc1d138a3126
Status: Downloaded newer image for alpine:3.17
docker.io/library/alpine:3.17
➜  ~
```

```shell
➜  ~ docker run -it --rm alpine:3.17 /bin/sh
/ # ls /etc/os-release
/etc/os-release
/ # cat /etc/os-release
NAME="Alpine Linux"
ID=alpine
VERSION_ID=3.17.3
PRETTY_NAME="Alpine Linux v3.17"
HOME_URL="https://alpinelinux.org/"
BUG_REPORT_URL="https://gitlab.alpinelinux.org/alpine/aports/-/issues"
/ #
```

- Pour spécifier de le détruire on fait :
	- `--rm`

### DANS CE CONTAINER, EXÉCUTEZ LA COMMANDE TOP. INSPECTEZ ENSUITE LE PROCESSUS TOP À L’INTÉRIEUR DU CONTAINER ET SUR LA MACHINE HÔTE (VIA PS AUX)

```shell
Mem: 6728512K used, 9518596K free, 5536K shrd, 509312K buff, 3878076K cached
CPU:   0% usr   0% sys   0% nic 100% idle   0% io   0% irq   0% sirq
Load average: 0.00 0.00 0.00 1/1095 9
  PID  PPID USER     STAT   VSZ %VSZ CPU %CPU COMMAND
    1     0 root     S     1692   0%  18   0% /bin/sh
    9     1 root     R     1620   0%   0   0% top
```

```shell
➜  school ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.0   2324  1712 ?        Sl   11:24   0:00 /init
root         4  0.0  0.0   2376    68 ?        Sl   11:24   0:02 plan9 --control-socket 5 --log-level 4 --server-
root       131  0.0  0.0   2328   112 ?        Ss   11:24   0:00 /init
root       132  0.0  0.0   2344   116 ?        S    11:24   0:00 /init
root       133  0.0  0.1 733348 29232 pts/0    Ssl+ 11:24   0:00 /mnt/wsl/docker-desktop/docker-desktop-user-dist
root       152  0.0  0.0   2344   116 ?        S    11:24   0:00 /init
xavierp    153  0.0  0.2 769848 46024 pts/1    Ssl+ 11:24   0:00 docker serve --address unix:///home/xavierp/.doc
root       188  0.0  0.0   2328   112 ?        Ss   11:31   0:00 /init
root       189  0.0  0.0   2344   116 ?        R    11:31   0:00 /init
xavierp    190  0.0  0.0  12896  9024 pts/2    Ss   11:31   0:02 -zsh
root      2428  0.0  0.0   2340   112 ?        Ss   14:06   0:00 /init
root      2429  0.0  0.0   2340   120 ?        S    14:06   0:00 /init
xavierp   2430  0.1  0.0  12708  8864 pts/3    Ss   14:06   0:01 -zsh
xavierp   4050  0.0  0.2 769848 43624 pts/3    Sl+  14:27   0:00 docker run -it alpine:3.17 /bin/sh
xavierp   4067  0.0  0.2 1496316 42232 pts/3   Sl+  14:27   0:00 /mnt/wsl/docker-desktop/cli-tools/usr/bin/com.do
xavierp   4083  0.0  0.0   7480  3092 pts/2    R+   14:28   0:00 ps aux
➜  school
```

#### SELON VOTRE OBSERVATION, EST-CE QU’UN PROCESSUS APPARTENANT À ROOT DANS LE CONTAINER APPARTIENT ÉGALEMENT À ROOT EN DEHORS DU CONTAINER ?

- Oui, un processus appartenant à root dans le conteneur appartient également à root en dehors du conteneur.
- Cependant, il est important de noter que Docker utilise un mappage d'ID utilisateur pour isoler les UID à l'intérieur du conteneur.

### POUR RAPPEL, ROOT POSSÈDE LE USER ID (UID) 0
#### POURQUOI EST-IL DANGEREUX QU’UN PROCESSUS UID 0 DANS LE CONTAINER SOIT ÉGALEMENT UID 0 SUR LA MACHINE HÔTE ?

- C'est dangereux car si un processus avec UID 0 dans le conteneur est compromis, l'attaquant peut potentiellement prendre le contrôle de la machine hôte. L'isolation entre les conteneurs et la machine hôte est essentielle pour maintenir la sécurité.

#### QUELLE DIFFÉRENCE REMARQUEZ VOUS LORSQUE VOUS EXÉCUTEZ LA COMMANDE PS AUX DANS LE CONTAINER ET SUR LA MACHINE HÔTE ? A VOTRE AVIS, QUELLE EST LA RAISON DE CETTE DIFFÉRENCE ?

- Dans le conteneur, `ps aux` affichera uniquement les processus en cours d'exécution à l'intérieur du conteneur, alors que sur la machine hôte, il affichera tous les processus en cours d'exécution sur la machine hôte, y compris ceux des conteneurs.
- La différence est due à l'isolation des processus fournie par Docker. Les conteneurs sont isolés du système hôte et ne peuvent voir que leurs propres processus.

### À L’INTÉRIEUR DU CONTAINER, TERMINEZ TOP (TOUCHE Q), PUIS INSTALLEZ ET EXÉCUTEZ LE PROGRAMME ASCIIQUARIUM. POUR INFO, ALPINE UTILISE LE PACKAGE MANAGER APK. LES ÉQUIVALENTS ALPINE DE APTGET UPDATE ET APT-GET INSTALL SONT APK UPDATE ET APK ADD. VOUS POUVEZ LISTER TOUS LES PAQUETS DISPONIBLES AVEC APK LIST
#### QUEL EST LE PID DE CE PROCESSUS DANS LE CONTAINER ? QUEL EST LE PID DE CE MÊME PROCESSUS SUR LA MACHINE HÔTE ET POURQUOI EST-IL DIFFÉRENT À VOTRE AVIS ?

- Le PID dans le conteneur est différent du PID sur la machine hôte. Docker utilise des espaces de noms (namespaces) pour isoler les processus entre le conteneur et l'hôte, ce qui entraîne des PIDs différents.

### VOUS ALLEZ MAINTENANT INVESTIGUER EMPIRIQUEMENT LE COMPORTEMENT DES CONTAINERS
#### QUEL EST LE PROCESSUS PORTANT LE NUMÉRO DE PID 1 DANS LE CONTAINER ?

- Dans le conteneur, le processus avec le PID 1 est généralement le processus principal du conteneur (par exemple, le shell ou le processus d'entrée).

```shell
/ # ps aux
PID   USER     TIME  COMMAND
    1 root      0:00 /bin/sh
   24 root      0:00 ps aux
/ #
```

#### QUEL EST LE PROCESSUS PORTANT LE MÊME NUMÉRO DE PID SUR LA MACHINE HÔTE ? 

- Sur la machine hôte, le processus avec le PID 1 est généralement le système d'initialisation (par exemple, systemd).

```shell
➜  school ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.0   2324  1712 ?        Sl   11:24   0:00 /init
```

#### POUR GÉNÉRALISER, QUEL EST LE PROCESSUS PORTANT LE PID 1 DANS LE CONTAINER (CÀD QUEL QUE SOIT LE CONTAINER EXÉCUTÉ) ? VOUS POUVEZ LE DÉDUIRE EMPIRIQUEMENT EN EXÉCUTANT D’AUTRES CONTAINERS AVEC DES PROGRAMMES DIFFÉRENTS

- Le processus portant le PID 1 dans un conteneur est généralement le processus principal ou d'entrée du conteneur, qui dépend de l'image et de la configuration du conteneur.

### COMPARER LE RÉSULTAT DE LA COMMANDE UNAME -RV DANS LE CONTAINER ET SUR LA MACHINE HÔTE

#### QUE REMARQUEZ-VOUS ET QUE POUVEZ-VOUS EN CONCLURE ? 

- Normalement les résultats doivent être les mêmes, car le conteneur utilise le noyau de la machine hôte.

- Hôte

```shell
➜  school uname -rv
5.15.90.1-microsoft-standard-WSL2 #1 SMP Fri Jan 27 02:56:13 UTC 2023
➜  school
```

- Container

```shell
/ # uname -rv
5.15.90.1-microsoft-standard-WSL2 #1 SMP Fri Jan 27 02:56:13 UTC 2023
/ #
```

### SIMILAIREMENT À CI-DESSUS, COMPAREZ LE CONTENU DU RÉPERTOIRE /DEV/

#### QUE REMARQUEZ-VOUS ?  A VOTRE AVIS QUELLE EST LA RAISON DE CETTE DIFFÉRENCE ?

- Le contenu du répertoire /dev/ peut différer entre le conteneur et la machine hôte, car Docker crée un environnement isolé pour chaque conteneur.

- Machine hôte

```shell
➜  school ls /dev/
autofs           hvc0          loop2   ptp0   ram5    sg1     tty12  tty24  tty36  tty48  tty6     vcs
block            hvc1          loop3   pts    ram6    sg2     tty13  tty25  tty37  tty49  tty60    vcs1
bsg              hvc2          loop4   ram0   ram7    sg3     tty14  tty26  tty38  tty5   tty61    vcsa
btrfs-control    hvc3          loop5   ram1   ram8    sg4     tty15  tty27  tty39  tty50  tty62    vcsa1
bus              hvc4          loop6   ram10  ram9    shm     tty16  tty28  tty4   tty51  tty63    vcsu
console          hvc5          loop7   ram11  random  stderr  tty17  tty29  tty40  tty52  tty7     vcsu1
cpu_dma_latency  hvc6          mapper  ram12  rtc0    stdin   tty18  tty3   tty41  tty53  tty8     vfio
cuse             hvc7          mem     ram13  sda     stdout  tty19  tty30  tty42  tty54  tty9     vhost-net
dri              kmsg          net     ram14  sdb     tty     tty2   tty31  tty43  tty55  ttyS0    vport0p0
dxg              kvm           null    ram15  sdc     tty0    tty20  tty32  tty44  tty56  ttyS1    vport0p1
fd               loop-control  nvram   ram2   sdd     tty1    tty21  tty33  tty45  tty57  ttyS2    vsock
full             loop0         ppp     ram3   sde     tty10   tty22  tty34  tty46  tty58  ttyS3    zero
fuse             loop1         ptmx    ram4   sg0     tty11   tty23  tty35  tty47  tty59  urandom
➜  school
```

- Container

```shell
/ # ls /dev/
console  fd       mqueue   ptmx     random   stderr   stdout   urandom
core     full     null     pts      shm      stdin    tty      zero
/ #
```

#### EST-IL POSSIBLE DE DONNER À UN CONTAINER ACCÈS À UN OU PLUSIEURS PÉRIPHÉRIQUES DE LA MACHINE HÔTE ? COMMENT ? TROUVER UN MOYEN PERMETTANT DE VÉRIFIER VOTRE MÉTHODE

- Oui, il est possible de donner à un conteneur accès à un ou plusieurs périphériques de la machine hôte en utilisant l'option `--device` lors de la création du conteneur. `docker run --device=/dev/sda:/dev/sda`
- Par exemple, pour donner accès à un périphérique USB :

```shell
docker run -it --device=/dev/ttyUSB0 ubuntu
```

- Vous pouvez vérifier si le périphérique est accessible dans le conteneur en utilisant des commandes spécifiques au périphérique ou en vérifiant le contenu du répertoire `/dev/`.

### EXÉCUTEZ LA COMMANDE MOUNT SUR LA MACHINE HÔTE ET DANS LE CONTAINER

- Les montages et les systèmes de fichiers peuvent différer entre le conteneur et la machine hôte en raison de l'isolation des conteneurs.

#### QUELLES DIFFÉRENCES REMARQUEZ VOUS, NOTAMMENT EN CE QUI CONCERNE LE SYSTÈME DE FICHIERS RACINE ?

- Le système de fichiers racine du conteneur sera différent de celui de la machine hôte. 
- Les conteneurs ont leur propre système de fichiers racine isolé, construit à partir de l'image du conteneur.
- Le système de fichier racine est un overlay sur le contenueur et sur l'hôte.

#### RETROUVEZ-VOUS L’ENTRÉE DÉFINISSANT LE SYSTÈME DE FICHIERS RACINE DU CONTAINER SUR LA MACHINE HÔTE ? QUE POUVEZ-VOUS DONC CONCLURE DU SYSTÈME DE FICHIERS RACINE DU CONTAINER ?

- L'entrée définissant le système de fichiers racine du conteneur peut ne pas être visible sur la machine hôte.
- Les conteneurs ont leur propre système de fichiers racine qui est isolé de la machine hôte et construit à partir de l'image du conteneur. 
- Cette isolation assure la sécurité et la portabilité des conteneurs.

# VIRTUALISATION - DOCKER STORAGE

## EXERCICE 1

### CONFIGURATION

```shell
➜  school cd v
➜  v mkdir lower
➜  v mkdir upper
➜  v mkdir merged
➜  v mkdir workdir
➜  v
```

1.  `lowerdir`: C'est le répertoire utilisé comme couche inférieure (lower layer) dans overlayfs. Il est généralement en lecture seule et contient les fichiers et les répertoires de base (par exemple, l'image Docker).
2.  `upperdir`: C'est le répertoire utilisé comme couche supérieure (upper layer) dans overlayfs. Il est en lecture/écriture et stocke les modifications apportées aux fichiers et répertoires pendant l'exécution du conteneur (par exemple, la couche de conteneur en lecture/écriture).
3.  `workdir`: C'est un répertoire de travail utilisé par overlayfs pour gérer les opérations internes, telles que le mécanisme de copy-on-write. Ce répertoire doit être sur le même système de fichiers que `upperdir`.
4.  `merged`: C'est le répertoire où la vue unifiée des couches inférieure et supérieure est montée. Les fichiers et répertoires de ce répertoire représentent la combinaison des deux couches, et c'est ce que voit et utilise un conteneur Docker. (le root en soit)

```shell
➜  v sudo mount -t overlay overlay -o lowerdir=lower,upperdir=upper,workdir=workdir merged
[sudo] password for xavierp:
➜  v
```

#### QUELLE EST L'ANALOGIE ENTRE LE SCÉNARIO QUE VOUS AVEZ RÉALISÉ ICI ET LES CONTAINERS DOCKER (IMAGE ET COUCHE CONTAINER) ?

- L'analogie entre ce scénario et les contenueurs Docker est que la couche basse (lower) correspond à l'image Docker en lecture seule, et la couche haute (upper) correspond à la couche de conteneur en lecture/écriture qui stocke les modifications apportées pendant l'exécution du conteneur.
- La vue unifiée (merged) représente la combinaison des deux couches, tout comme l'environnement de fichiers d'un conteneur Docker.

#### QUE SE PASSE-T-IL RÉELLEMENT LORSQU'UN FICHIER DE LA VUE UNIFIÉE (MERGED) EST AJOUTÉ ?

- Lorsqu'un fichier est ajouté à la vue unifiée (merged), il est en réalité créé dans la couche haute (upper), car c'est la couche en lecture/écriture.
- La couche basse (lower) reste inchangée, car elle est en lecture seule.

#### QUE SE PASSE-T-IL RÉELLEMENT LORSQU'UN FICHIER DE LA VUE UNIFIÉE (MERGED) ET EXISTANT DANS LA COUCHE BASSE, EST MODIFIÉ ?

- Lorsqu'un fichier existant dans la couche basse (lower) est modifié dans la vue unifiée (merged), le fichier modifié est créé dans la couche haute (upper), préservant ainsi l'original dans la couche basse.
	- Ce mécanisme est appelé "copy-on-write".
- La vue unifiée (merged) affiche la version modifiée du fichier.

#### QUE SE PASSE-T-IL RÉELLEMENT LORSQU'UN FICHIER DE LA VUE UNIFIÉE (MERGED) ET EXISTANT DANS LA COUCHE BASSE, EST SUPPRIMÉ ?

- Lorsqu'un fichier existant dans la couche basse (lower) est supprimé dans la vue unifiée (merged), un "whiteout" est créé dans la couche haute (upper) pour indiquer que le fichier a été supprimé.
- Le fichier original dans la couche basse reste inchangé, mais il est masqué par le whiteout dans la vue unifiée (merged).
- Pour afficher les attributs d'un fichier avec un whiteout, vous pouvez utiliser `ls -l`.
- Pour en savoir plus sur les whiteouts et la commande `mknod`, consultez la documentation du système de fichiers overlayfs et les pages de manuel Linux.

## EXERCICE 2

### MAINTENANT, ON S’INTÉRESSE À MIEUX COMPRENDRE COMMENT LES COUCHES D’UNE IMAGE/CONTAINER SONT GÉRÉES PAR DOCKER. 

Exécutez un contenueur Fedora:26, puis dans celui-ci : 

- ajoutez un fichier à la racine
- supprimez un fichier, par exemple /etc/issue
- modifiez un fichier, par exemple en ajoutant une ligne à /etc/passwd

```shell
➜  school docker run -it --rm fedora:26 /bin/sh
sh-4.4#
sh-4.4# touch patate.txt
sh-4.4# rm /etc/issue
sh-4.4# echo pouf >> /etc/passwd
sh-4.4# cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
sync:x:5:0:sync:/sbin:/bin/sync
shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown
halt:x:7:0:halt:/sbin:/sbin/halt
mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
operator:x:11:0:operator:/root:/sbin/nologin
games:x:12:100:games:/usr/games:/sbin/nologin
ftp:x:14:50:FTP User:/var/ftp:/sbin/nologin
nobody:x:99:99:Nobody:/:/sbin/nologin
systemd-coredump:x:999:998:systemd Core Dumper:/:/sbin/nologin
systemd-timesync:x:998:997:systemd Time Synchronization:/:/sbin/nologin
systemd-network:x:192:192:systemd Network Management:/:/sbin/nologin
systemd-resolve:x:193:193:systemd Resolver:/:/sbin/nologin
dbus:x:81:81:System message bus:/:/sbin/nologin
tss:x:59:59:Account used by the trousers package to sandbox the tcsd daemon:/dev/null:/sbin/nologin
pouf
sh-4.4#
```

### UTILISEZ DOCKER INSPECT POUR INSPECTER LE CONTENU DU CONTAINER EN EXÉCUTION CI-DESSUS

#### COMBIEN DE COUCHES BASSES (LOWER LAYERS) CONTIENT CE CONTAINER ET QUELLES SONT LEURS CHEMINS ABSOLUS DANS LE SYSTÈME DE FICHIERS SUR LA MACHINE HÔTE ?

- Le nombre de couches basses (lower layers) dépend de l'image Docker utilisée et des couches qui la composent. Pour trouver leurs chemins absolus, utilisez la commande `docker inspect` et recherchez la valeur de "LowerDir" dans la section "GraphDriver" de la sortie JSON.

```
➜  v docker ps
CONTAINER ID   IMAGE       COMMAND     CREATED          STATUS          PORTS     NAMES
a742187698a6   fedora:26   "/bin/sh"   53 seconds ago   Up 53 seconds             determined_moser
➜  v docker inspect a742187698a6

...
"GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/78acf48bc6744b02d651d0609027524541bda5bd219f086e691db7799d6ac2f1-init/diff:/var/lib/docker/overlay2/30175f2c9c4d4c6764a2b8076ff7f8ec88e5578bb049db731c9691cadbde5672/diff",
                "MergedDir": "/var/lib/docker/overlay2/78acf48bc6744b02d651d0609027524541bda5bd219f086e691db7799d6ac2f1/merged",
                "UpperDir": "/var/lib/docker/overlay2/78acf48bc6744b02d651d0609027524541bda5bd219f086e691db7799d6ac2f1/diff",
                "WorkDir": "/var/lib/docker/overlay2/78acf48bc6744b02d651d0609027524541bda5bd219f086e691db7799d6ac2f1/work"
            },
            "Name": "overlay2"
        },
...
```

#### QUEL EST LE CHEMIN ABSOLU DE LA COUCHE CONTAINER WRITABLE (UPPER) ?

- Le chemin absolu de la couche conteneur writable (upper layer) est donné par la valeur de "UpperDir" dans la section "GraphDriver" de la sortie JSON de la commande `docker inspect`.

#### EN INSPECTANT LE SYSTÈME DE FICHIERS SUR LA MACHINE HÔTE, LISTEZ LE CONTENU COMPLET DE LA COUCHE CONTAINER WRITABLE (INFO: TREE EST TRÈS PRATIQUE POUR VISUALISER LES ARBORESCENCES)

- Utilisez la commande `tree` pour afficher le contenu complet de la couche conteneur writable en exécutant :

`tree /chemin/vers/UpperDir`

- Nous pouvons voir que la couche upper contient les modifications que nous avons fait après l'instanciation du conteneur.

#### SUR LA MACHINE HÔTE, QUEL EST LE CHEMIN ABSOLU DU RÉPERTOIRE CORRESPONDANT AU ROOTFS DU CONTAINER ?

- Le chemin absolu du répertoire correspondant au rootfs du conteneur est donné par la valeur de "MergedDir" dans la section "GraphDriver" de la sortie JSON de la commande `docker inspect`.

### SUR LA MACHINE HÔTE, DÉPLACEZ-VOUS DANS LE RÉPERTOIRE CORRESPONDANT AU ROOTFS DU CONTAINER. A L’INTÉRIEUR DE CELUI-CI, CRÉEZ LE FICHIER HELLO_FROM_THE_OUTSIDE

#### SUITE À L’OPÉRATION CI-DESSUS, QU’OBSERVEZ-VOUS DANS LE CONTAINER LORSQUE VOUS LISTEZ LE CONTENU DU RÉPERTOIRE RACINE ?

- Après avoir créé le fichier `Hello_from_the_outside` dans le répertoire rootfs du conteneur sur la machine hôte, vous devriez voir ce fichier lorsque vous listez le contenu du répertoire racine dans le conteneur.

### PRÉCÉDEMMENT, VOUS AVEZ UTILISÉ LA COMMANDE DOCKER INSPECT POUR DÉTERMINER LES DIFFÉRENTES COUCHES (OVERLAYFS) DU CONTAINER

#### EST-CE QU’IL EST POSSIBLE DE SIMPLEMENT UTILISER LA COMMANDE MOUNT SUR LE SERVEUR POUR OBTENIR LES MÊMES INFORMATIONS ? JUSTIFIEZ VOTRE DÉMARCHE

- Oui, il est possible d'utiliser la commande `mount` pour obtenir des informations sur le système de fichiers overlay utilisé par le conteneur. Cependant, les informations peuvent être formatées différemment et il peut être nécessaire d'analyser la sortie pour extraire les informations pertinentes.
- Pour ce faire, exécutez la commande suivante : `mount | grep overlay`

```
sh-4.4# mount | grep overlay
overlay on / type overlay (rw,relatime,lowerdir=/var/lib/docker/overlay2/l/J6J2YXETF3MGXBZEPZP3FRDOEP:/var/lib/docker/overlay2/l/STISIXXHST3EF244SLJI7RRGOL,upperdir=/var/lib/docker/overlay2/78acf48bc6744b02d651d0609027524541bda5bd219f086e691db7799d6ac2f1/diff,workdir=/var/lib/docker/overlay2/78acf48bc6744b02d651d0609027524541bda5bd219f086e691db7799d6ac2f1/work)
sh-4.4#
```

## EXERCICE 3

### DANS CET EXERCICE ON DÉSIRE MODIFIER UN CONTAINER ET RENDRE CES MODIFICATIONS PERSISTANTES, EN LES COMMITTANT DANS UNE NOUVELLE IMAGE

#### QUELLE EST LA VERSION LA PLUS RÉCENTE QUE VOUS AVEZ TROUVÉE ?

Déterminez l’image Debian la plus récente (en terme de numéro de version), puis téléchargez là. 

```
➜  school docker pull debian
➜  school docker run debian cat /etc/os-release
PRETTY_NAME="Debian GNU/Linux 11 (bullseye)"
NAME="Debian GNU/Linux"
VERSION_ID="11"
VERSION="11 (bullseye)"
VERSION_CODENAME=bullseye
ID=debian
HOME_URL="https://www.debian.org/"
SUPPORT_URL="https://www.debian.org/support"
BUG_REPORT_URL="https://bugs.debian.org/"
```

### DÉMARREZ ALORS UN CONTAINER NOMMÉ MYDEBIAN INSTANCIÉ DEPUIS L’IMAGE QUE VOUS VENEZ DE TÉLÉCHARGER. 

Dans ce conteneur : 

- Supprimez les répertoires /opt et /mnt et la commande /usr/bin/uniq 2 / 3
- Avec dd, créez le fichier /home/random de 8500 bytes à partir de /dev/urandom
- Ajouter la ligne ci-dessous à la fin du fichier /etc/motd: `Tagada tsoin tsoin`

Une fois ces opérations réalisées, sortez du conteneur. 

```
➜  school docker run -it --name mydebian debian
root@ddc940dda346:/# rm -rf /opt /mnt /usr/bin/uniq
root@ddc940dda346:/# dd if=/dev/urandom of=/home/random bs=1 count=8500
8500+0 records in
8500+0 records out
8500 bytes (8.5 kB, 8.3 KiB) copied, 0.00941865 s, 902 kB/s
root@ddc940dda346:/# echo "Tagada tsoin tsoin" >> /etc/motd
root@ddc940dda346:/# exit
```

### A L’AIDE DE DOCKER DIFF, AFFICHEZ LES DIFFÉRENCES ENTRE VOTRE CONTAINER MYDEBIAN ET L’IMAGE UTILISÉE POUR SON INSTANTATION

#### QUELLE EST LA SIGNIFICATION DE LA LETTRE SITUÉE DANS LA PREMIÈRE COLONNE DES RÉSULTATS DE DOCKER DIFF ?

```shell
➜  school docker diff mydebian
C /etc
C /etc/motd
C /home
A /home/random
C /root
A /root/.bash_history
C /usr
C /usr/bin
D /usr/bin/uniq
D /mnt
D /opt
➜  school
```

-   A : Ajout (Added)
-   D : Suppression (Deleted)
-   C : Modification (Changed)

### A L’AIDE DE LA COMMANDE DOCKER COMMIT, COMMITTEZ ALORS CES CHANGEMENT EN CRÉEANT LA NOUVELLE IMAGE DEBIAN:NEW. DÉTRUISEZ ALORS LE CONTAINER DEBIAN PRÉCÉDENT ÉTANT DONNÉ QU’IL N’EST PLUS UTILE, PUIS INSPECTEZ L’HISTORIQUE DE L’IMAGE DEBIAN:NEW QUE VOUS VENEZ DE CRÉER

```shell
docker commit mydebian debian:new
```

```
➜  school docker commit mydebian debian:new
sha256:d87ccf9df1683e04fc12de730ccebc28bfd1fce573b373277dcd38f863dcc2d5
➜  school
```

#### COMBIEN DE COUCHES ONT ÉTÉ AJOUTÉES À L’IMAGE SUITE À VOS MODIFICATIONS APPORTÉES AU CONTAINER CI-DESSUS ?

- 1

```
➜  school docker history debian:new
IMAGE          CREATED         CREATED BY                                      SIZE      COMMENT
d87ccf9df168   2 minutes ago   bash                                            8.93kB
ca1a8403096e   13 days ago     /bin/sh -c #(nop)  CMD ["bash"]                 0B
<missing>      13 days ago     /bin/sh -c #(nop) ADD file:f2d012660f882f319…   124MB
```

#### QUELLE EST LA TAILLE DE CES/CETTE NOUVELLE(S) COUCHE(S) ? 

- `8.93kB`

### ENFIN, INSTANCIEZ UN NOUVEAU CONTAINER À PARTIR DE VOTRE NOUVELLE IMAGE DEBIAN:NEW ET VÉRIFIEZ QUE CE NOUVEAU CONTAINER CONTIENT BIEN LES CHANGEMENTS EFFECTUÉS PRÉCÉDEMMENT

## EXERCICE 4

### ON DÉSIRE ENFIN SE FAMILIARISER AVEC L’UTILISATION DE VOLUMES ET BIND MOUNTS. SUR VOTRE MACHINE CLIENT, CRÉEZ LE VOLUME PICS, PUIS MONTEZ LE DANS LE RÉPERTOIRE /VOL/PICS D’UN CONTAINER UBUNTU:22.04 CRÉÉ POUR L’OCCASION

#### DANS LE CONTAINER, QUEL EST LE CONTENU DU VOLUME PICS ?

```
➜  school docker volume create pics
pics
➜  school docker run -it --name my_ubuntu_container -v pics:/vol/pics ubuntu:22.04
Unable to find image 'ubuntu:22.04' locally
22.04: Pulling from library/ubuntu
2ab09b027e7f: Pull complete
Digest: sha256:67211c14fa74f070d27cc59d69a7fa9aeff8e28ea118ef3babc295a0428a6d21
Status: Downloaded newer image for ubuntu:22.04
root@de1db3d20cb7:/#
```

```
➜  ~ docker cp images/ my_ubuntu_container:/vol/pics
➜  ~
```

```
root@de1db3d20cb7:/# ls vol/pics/images/
c.jpg
root@de1db3d20cb7:/#
```

### DEPUIS LA MACHINE CLIENTE, COPIEZ UN RÉPERTOIRE CONTENANT UNE SÉRIE D’IMAGES DANS LE VOLUME PICS ET VÉRIFIEZ QUE VOUS POUVEZ ACCÉDER À CES IMAGES DANS VOTRE CONTAINER

Réalisez maintenant l’opération inverse: copiez le contenu du volume pics dans le répertoire courant de votre machine locale.

#### EST-CE QUE LES OPÉRATIONS CI-DESSUS SUR LE VOLUME PICS FONCTIONNERONT CORRECTEMENT SI LE DAEMON DOCKERD S’EXÉCUTE SUR UNE MACHINE DIFFÉRENTE DU CLIENT DOCKER ? JUSTIFIEZ

- 7.  Les opérations ci-dessus sur le volume `pics` fonctionneront correctement si le daemon `dockerd` s'exécute sur une machine différente du client Docker. Les volumes Docker sont gérés par le daemon Docker et peuvent être partagés entre plusieurs conteneurs, même sur des hôtes distants.

```
➜  ~ docker cp my_ubuntu_container:/vol/pics otherimages
➜  ~ ls otherimages/pics/images/c.jpg
otherimages/pics/images/c.jpg
➜  ~
```

### RÉALISEZ MAINTENANT LES MÊME OPÉRATION QUE CI-DESSUS, MAIS PLUTÔT QUE D’UTILISER UN VOLUME, UTILISEZ UN BIND MOUNT

#### EST-CE QUE DANS LE CAS D’UN BIND MOUNT, LES OPÉRATIONS CI-DESSUS FONCTIONNERONT CORRECTEMENT SI LE DAEMON DOCKERD S’EXÉCUTE SUR UNE MACHINE DIFFÉRENTE DU CLIENT DOCKER ? JUSTIFIEZ

- Dans le cas d'un bind mount, les opérations ci-dessus pourraient ne pas fonctionner correctement si le daemon `dockerd` s'exécute sur une machine différente du client Docker. Les bind mounts dépendent du système de fichiers local de l'hôte où le daemon Docker s'exécute. Si le daemon Docker est sur une machine différente, le chemin vers le répertoire local sur le client ne sera pas accessible par le daemon Docker sur la machine distante. Pour partager des fichiers entre un client Docker et un daemon Docker distant, vous devrez utiliser une méthode de partage de fichiers compatible avec les deux machines, comme NFS ou SMB, ou utiliser des volumes Docker.

# VIRTUALISATION - DOCKERFILES

## EXERCICE 1

### A) DÉCRIVEZ CE QUE RÉALISE CE CONTAINER EN EXPLIQUANT CHAQUE LIGNE DU DOCKERFILE

```dockerfile
FROM alpine:latest

LABEL maintainer="Yoda"

ADD files.tar.gz /dir_tar

RUN mkdir /dir_add

COPY file0* /dir_add/

CMD ["ls", "-al", "/dir_tar", "/dir_add"]
```

Ce Dockerfile crée une image de conteneur basée sur l'image officielle d'Alpine Linux (la version la plus récente). Voici une explication de chaque ligne du Dockerfile :

1.  `FROM alpine:latest` : Cette ligne indique que l'image de base pour ce Dockerfile est `alpine:latest`, qui est la dernière version de l'image officielle d'Alpine Linux.
2.  `LABEL maintainer="Yoda"` : Cette ligne ajoute une étiquette (label) à l'image avec le champ `maintainer` et la valeur "Yoda". Les étiquettes sont utilisées pour ajouter des métadonnées aux images.
3.  `ADD files.tar.gz /dir_tar` : Cette ligne décompresse l'archive `files.tar.gz` et ajoute son contenu dans le répertoire `/dir_tar` à l'intérieur de l'image.
4.  `RUN mkdir /dir_add` : Cette ligne crée un nouveau répertoire appelé `/dir_add` à l'intérieur de l'image.
5.  `COPY file0* /dir_add/` : Cette ligne copie tous les fichiers dont le nom commence par `file0` dans le répertoire `/dir_add` de l'image.
6.  `CMD ["ls", "-al", "/dir_tar", "/dir_add"]` : Cette ligne définit la commande par défaut à exécuter lorsque le conteneur est lancé. Dans ce cas, la commande est `ls -al /dir_tar /dir_add`, qui affiche les détails des fichiers et des répertoires dans `/dir_tar` et `/dir_add`.

### B) POURQUOI LE FICHIER FILE04 N’EST PAS PRÉSENT DANS LE RÉPERTOIRE /DIR_ADD DU CONTAINER (INDICE: INSPECTEZ LES FICHIERS DANS EX01) ?

Il est dans le `.dockerignore`.

### C) EN OBSERVANT LA SORTIE DU CONTAINER, QUE REMARQUEZ-VOUS AU NIVEAU DES ATTRIBUTS DES FICHIERS AJOUTÉS ? D’OÙ VIENT CETTE DIFFÉRENCE ?

En observant la sortie du conteneur, vous pouvez remarquer que les attributs des fichiers diffèrent entre les répertoires `/dir_add` et `/dir_tar`. Les fichiers ajoutés à `/dir_add` ont été copiés avec l'instruction `COPY` du Dockerfile et sont donc créés avec l'utilisateur `root` et le groupe `root`. Les permissions sont définies sur `-rw-r--r--` pour ces fichiers.

En revanche, les fichiers ajoutés à `/dir_tar` ont été extraits de l'archive `files.tar.gz` avec l'instruction `ADD`. Ces fichiers conservent les attributs originaux de l'archive, qui comprennent l'utilisateur `1000` et le groupe `1000`. Les permissions sont `-rw-rw-r--` pour ces fichiers.

La différence provient donc de la manière dont les fichiers ont été ajoutés au conteneur. L'instruction `COPY` copie les fichiers en utilisant l'utilisateur et le groupe courants dans l'image (dans ce cas, `root`), tandis que l'instruction `ADD` extrait les fichiers de l'archive en conservant leurs attributs d'origine.

```shell
➜  ex01 git:(master) id
uid=1000(xavierp) gid=1000(xavierp) groups=1000(xavierp),4(adm),20(dialout),24(cdrom),25(floppy),27(sudo),29(audio),30(dip),44(video),46(plugdev),116(netdev),1001(docker)
```

```shell
➜  ex01 git:(master) docker run -it --rm exercice1
/dir_add:
total 32
drwxr-xr-x    1 root     root          4096 Apr 27 08:18 .
drwxr-xr-x    1 root     root          4096 Apr 27 08:23 ..
-rw-r--r--    1 root     root            36 Apr 24 13:08 file01
-rw-r--r--    1 root     root          2796 Apr 24 13:08 file02
-rw-r--r--    1 root     root         13990 Apr 24 13:08 file03

/dir_tar:
total 108
drwxr-xr-x    2 root     root          4096 Apr 27 08:18 .
drwxr-xr-x    1 root     root          4096 Apr 27 08:23 ..
-rw-rw-r--    1 1000     1000            36 Apr 20 20:07 file01
-rw-rw-r--    1 1000     1000          2796 Apr 20 20:07 file02
-rw-rw-r--    1 1000     1000         13990 Apr 20 20:09 file03
-rw-rw-r--    1 1000     1000         75133 Apr 20 20:08 file04
```

### D) INSPECTEZ L’HISTORIQUE (NON-TRONQUÉE) DE L’IMAGE QUE VOUS AVEZ CRÉÉE ET DÉCRIVEZ CHAQUE LAYER (COUCHE) DE L’IMAGE

```shell
➜  ex01 git:(master) docker history --no-trunc exercice1
IMAGE         CREATED          CREATED BY
          SIZE      COMMENT
sha256:   12 minutes ago   CMD ["ls" "-al" "/dir_tar" "/dir_add"]                                                              0B        buildkit.dockerfile.v0
<missing> 12 minutes ago   COPY file0* /dir_add/ # buildkit                                                                    16.8kB    buildkit.dockerfile.v0
<missing> 12 minutes ago   RUN /bin/sh -c mkdir /dir_add # buildkit                                                            0B        buildkit.dockerfile.v0
<missing> 12 minutes ago   ADD files.tar.gz /dir_tar # buildkit                                                                92kB      buildkit.dockerfile.v0
<missing> 12 minutes ago   LABEL maintainer=Yoda                                                                               0B        buildkit.dockerfile.v0
```

Voici la description de chaque couche (layer) de l'image que vous avez créée en utilisant `docker history --no-trunc exercice1` :

1.  `CMD ["ls" "-al" "/dir_tar" "/dir_add"]`: Cette couche définit la commande par défaut à exécuter lorsque le conteneur est démarré. Ici, la commande `ls -al` est utilisée pour afficher le contenu des répertoires `/dir_tar` et `/dir_add`.
2.  `COPY file0* /dir_add/`: Cette couche copie les fichiers commençant par `file0` du contexte de construction (répertoire local) vers le répertoire `/dir_add` du conteneur.
3.  `RUN /bin/sh -c mkdir /dir_add`: Cette couche crée un nouveau répertoire nommé `/dir_add` dans le conteneur en utilisant la commande `mkdir`.
4.  `ADD files.tar.gz /dir_tar`: Cette couche ajoute le fichier `files.tar.gz` au répertoire `/dir_tar` du conteneur et décompresse automatiquement l'archive tar.gz.
5.  `LABEL maintainer=Yoda`: Cette couche ajoute une étiquette (label) à l'image avec la clé "maintainer" et la valeur "Yoda".
6.  `/bin/sh -c #(nop) CMD ["/bin/sh"]`: Cette couche est celle de l'image de base `alpine:latest` et définit la commande par défaut à exécuter dans le conteneur comme `/bin/sh`. Les couches précédentes ont modifié cette commande par défaut avec la couche `CMD ["ls" "-al" "/dir_tar" "/dir_add"]`.

Chaque couche représente une instruction du Dockerfile, et elles sont empilées pour former l'image complète. Les couches sont immuables et peuvent être partagées entre différentes images et conteneurs pour économiser de l'espace disque et du temps de construction.

### E) RE-CRÉEZ L’IMAGE EN TANT QU’UTILISATEUR ROOT. EST-CE QUE CELA CHANGE QUELQUE CHOSE ? JUSTIFIEZ

```dockerfile
FROM alpine:latest
USER root
LABEL maintainer="Yoda"
ADD files.tar.gz /dir_tar
RUN mkdir /dir_add
COPY file0* /dir_add/
CMD ["ls", "-al", "/dir_tar", "/dir_add"]
```

```shell
➜  ex01 git:(master) ✗ docker run -it --rm exercice1:0.2
/dir_add:
total 32
drwxr-xr-x    1 root     root          4096 Apr 27 08:42 .
drwxr-xr-x    1 root     root          4096 Apr 27 08:43 ..
-rw-r--r--    1 root     root            36 Apr 20 20:07 file01
-rw-r--r--    1 root     root          2796 Apr 20 20:07 file02
-rw-r--r--    1 root     root         13990 Apr 20 20:09 file03

/dir_tar:
total 108
drwxr-xr-x    2 root     root          4096 Apr 27 08:18 .
drwxr-xr-x    1 root     root          4096 Apr 27 08:43 ..
-rw-rw-r--    1 1000     1000            36 Apr 20 20:07 file01
-rw-rw-r--    1 1000     1000          2796 Apr 20 20:07 file02
-rw-rw-r--    1 1000     1000         13990 Apr 20 20:09 file03
-rw-rw-r--    1 1000     1000         75133 Apr 20 20:08 file04
➜  ex01 git:(master) ✗
```

Dans ce contexte, puisque vous travaillez déjà avec l'image `alpine:latest`, qui exécute les commandes en tant qu'utilisateur root par défaut, vous n'avez pas besoin d'ajouter l'instruction `USER root` dans le Dockerfile. Les instructions du Dockerfile que vous avez partagées précédemment sont déjà exécutées en tant qu'utilisateur root.

Cependant, si vous utilisiez une image de base qui définissait un autre utilisateur par défaut, vous devriez ajouter l'instruction `USER root` dans le Dockerfile pour exécuter les commandes en tant qu'utilisateur root.

Dans votre cas actuel, puisque vous travaillez déjà avec l'utilisateur root par défaut, reconstruire l'image ne devrait pas changer le comportement de l'image.

## EXERCICE 2

On désire créer un container Docker permettant de convertir (non-récursivement) les images du répertoire courant dans tout autre format d’image. Pour information, la commande mogrify -format png \*.jpg permet de convertir au format PNG tous les fichiers (du répertoire courant) se terminant par l’extension jpg. A savoir que l’outil mogrify est disponible dans le package imagemagick.

Votre solution doit respecter les points suivants :

- On doit pouvoir spécifier, au moment de l’instantiation du container, en quel format les images doivent être converties, de même que les images à convertir. 
	- Par exemple, passer 1 / 3 l’argument a*.jpg" doit convertir tous les fichiers du répertoire courant commençant par a et se terminant par .jpg.
- Les fichiers générés par le container doivent appartenir à l’utilisateur ayant exécuté le container et non à root (indice : slide 26 du cours “08-Docker_overview.pdf” et aussi commande id)
- Au cas où aucun argument n’est spécifié, on désire qu’un texte d’aide soit affiché, indiquant la syntaxe à utiliser.
- On veut que le Dockerfile se base sur une image de distribution Linux spécifique à une version donnée (donc pas latest), ceci afin de rendre le comportement du container plus stable. Le choix de la distribution est par contre libre.
- On désire une image aussi petite que possible.
- Afin d’éviter une accumulation inutile de containers, on désire que le container soit supprimé une fois son exécution terminée.

```dockerfile
FROM alpine:3.14
LABEL maintainer="Xavier Perret"

RUN apk update && \
  apk add --no-cache imagemagick && \
  mkdir /images && \
  chmod 777 /images

COPY ./images /images

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]
```

```shell
#!/bin/sh

if [ $# -eq 0 ]; then
  echo "Usage: docker run --rm -v \$(pwd):/images IMAGE_NAME [pattern] [format]"
  echo "Example: docker run --rm -v \$(pwd):/images IMAGE_NAME a*.jpg png"
  exit 1
fi

PATTERN=$1
FORMAT=$2

echo "Mogrifying images with pattern $PATTERN to format $FORMAT"

cd images/
mogrify -format $FORMAT $PATTERN
ls -l
```

```shell
docker build -t image-converter .

docker run --rm -u $(id -u):$(id -g) image-converter "a*.jpg" "png"
```

## EXERCICE 3

### PARTIE 1

```dockerfile
FROM golang:1.17
RUN go install github.com/alfg/asciicat@latest

ADD /images .

ENTRYPOINT [ "asciicat" ]
```

```shell
➜  ex03 git:(master) ✗ docker run --rm -v $(pwd):/images -w /images asciicat -i images/cat.jpg -w 400
```

- L'option `-v $(pwd):/images` dans la commande `docker run` sert à monter un volume dans le container Docker.

- Dans ce cas, `$(pwd)` représente le chemin du répertoire courant sur la machine hôte, et `/images` est le point de montage dans le container. Lorsque vous utilisez cette option, le répertoire courant de la machine hôte est monté dans le container sous `/images`. Ainsi, tous les fichiers présents dans le répertoire courant de la machine hôte seront accessibles par le container sous `/images`. Cela permet au container de lire et éventuellement de modifier les fichiers du répertoire courant sans avoir à les copier dans l'image Docker elle-même.


#### A) QUELLE EST LA TAILLE DE L’IMAGE GÉNÉRÉE ?

```shell
➜  part1 git:(master) docker inspect asciicat1
        "Size": 945673463,
```

```shell
➜  part1 git:(master) docker history asciicat1
IMAGE          CREATED          CREATED BY                                      SIZE      COMMENT
620f6a01e36d   13 minutes ago   ENTRYPOINT ["asciicat"]                         0B        buildkit.dockerfile.v0
<missing>      13 minutes ago   RUN /bin/sh -c go install github.com/alfg/as…   4.07MB    buildkit.dockerfile.v0
<missing>      8 months ago     /bin/sh -c #(nop) WORKDIR /go                   0B
<missing>      8 months ago     /bin/sh -c mkdir -p "$GOPATH/src" "$GOPATH/b…   0B
<missing>      8 months ago     /bin/sh -c #(nop)  ENV PATH=/go/bin:/usr/loc…   0B
<missing>      8 months ago     /bin/sh -c #(nop)  ENV GOPATH=/go               0B
<missing>      8 months ago     /bin/sh -c set -eux;  arch="$(dpkg --print-a…   408MB
<missing>      8 months ago     /bin/sh -c #(nop)  ENV GOLANG_VERSION=1.17.13   0B
<missing>      9 months ago     /bin/sh -c #(nop)  ENV PATH=/usr/local/go/bi…   0B
<missing>      9 months ago     /bin/sh -c set -eux;  apt-get update;  apt-g…   228MB
<missing>      9 months ago     /bin/sh -c apt-get update && apt-get install…   152MB
<missing>      9 months ago     /bin/sh -c set -ex;  if ! command -v gpg > /…   19MB
<missing>      9 months ago     /bin/sh -c set -eux;  apt-get update;  apt-g…   10.7MB
<missing>      9 months ago     /bin/sh -c #(nop)  CMD ["bash"]                 0B
<missing>      9 months ago     /bin/sh -c #(nop) ADD file:3451708ab45bc1bcf…   124MB
➜  part1 git:(master)
```

- La taille ajouté est de 4.07 MB
- La taille entière est de 900 MB

#### B) QUELLE EST LA LIGNE DE COMMANDE À EXÉCUTER POUR AFFICHER L’IMAGE CAT.PNG (SE TROUVANT DANS LE RÉPERTOIRE COURANT) EN ASCII ART SUR UNE LARGEUR DE 40 CARACTÈRES ?

```shell
➜  part1 git:(master) ✗ docker run --rm asciicat1 -i cat.jpg -w 40
```

### PARTIE 2

```dockerfile
FROM golang:1.17 AS builder

RUN go install github.com/alfg/asciicat@latest

FROM alpine:latest

COPY --from=builder /go/bin/asciicat /usr/local/bin/asciicat

ENTRYPOINT [ "asciicat" ]
```

### PARTIE 3

1.  Tout d'abord, exportez le système de fichiers d'une image Alpine existante. Pour ce faire, créez un container à partir de l'image Alpine, puis exportez le système de fichiers dans un fichier TAR.

```shell
docker create --name my-alpine-container alpine:3.14
docker export my-alpine-container > my-alpine.tar
```

2.  Créez un Dockerfile pour construire l'image asciicat en utilisant le fichier TAR exporté.

```dockerfile
FROM scratch
ADD alpine_3.17.tar /

RUN apk add --no-cache git go && \
  go install github.com/alfg/asciicat@latest

COPY images/ .
ENV PATH="${PATH}:/root/go/bin/"

ENTRYPOINT [ "asciicat" ]
```

```shell
➜  part3 git:(master) ✗ docker build -t asciicat3 .
[+] Building 0.1s (7/7) FINISHED
 => [internal] load build definition from Dockerfile                                                          0.0s
 => => transferring dockerfile: 237B                                                                          0.0s
 => [internal] load .dockerignore                                                                             0.0s
 => => transferring context: 2B                                                                               0.0s
 => [internal] load build context                                                                             0.0s
 => => transferring context: 100B                                                                             0.0s
 => CACHED [1/3] ADD alpine_3.17.tar /                                                                        0.0s
 => CACHED [2/3] RUN apk add --no-cache git go &&   go install github.com/alfg/asciicat@latest                0.0s
 => CACHED [3/3] COPY images/ .                                                                               0.0s
 => exporting to image                                                                                        0.0s
 => => exporting layers                                                                                       0.0s
 => => writing image sha256:e00af82997dcff613ade59bd7d4ca7f2ca0a487f24345f5885bd1151da7491ff                  0.0s
 => => naming to docker.io/library/asciicat3
 ```

```shell
➜  part3 git:(master) ✗ docker run --rm asciicat3 -i cat.jpg -w 40
ooooooio*********ooooooo+++++o*ooooooooo
****ooioo**%%%%%%%**o++++++++iiii++ooo**
%%%*o*iooo%%*%%%******o*ooooo+++++++++oo
oo*ooo;+o+ooooooooooo*****oooooo++++++++
++++ii;ii++++++iiiiiiiiiiiiiii++++++++++
;;;;;;:;;;;;;;iiiiiii;:;iiiiiiiiiii;;;;:
,,,,:,,;;:::::::::::::::;;;;::;:::::::'`
,,,,,,.,,,,,,,,,,.,,,...,,,,..,,,,,,,.``
,,,,....,,,,,,,,,,,,,,........,....,,```
'''''`''''''''''''''''`'````````````````
```````````````````````   ``````````````
````````````````````````''.''```````````
``````````````````'',,,.'```````````````
``````````'``''',...'```````````````````

➜  part3 git:(master) ✗
```