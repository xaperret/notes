---
---

# RÉSEAU VIRTUEL

## INTRODUCTION

- Quelle est l'ambition de la virtualisation des réseaux ?
	- Pouvoir exécuter une application distribuée composée de routeurs/commutateurs/proxies/liens de la même manière que vous le feriez sur un réseau physique
- Quels sont les avantages de la virtualisation réseau ?
	- Les équipements deviennent instanciables/jetables par programmation logicielle
	- Le cycle de vie des équipements est aussi long qu'un service
	- Les propriétés qui sont généralement statiques ou inhérentes au matériel physique sont configurables chaque fois
	- L'équipement devient une fonction du réseau, ce qui signifie qu'il perd ses propriétés matérielles/statiques

## LAYER OSI

- ![[Pasted image 20230407180131.png]]

### LAYER 1 DEVICES

- Analog modem
- Hub

### LAYER 2 DEVICES

### SWITCH

- Qu'est-ce qu'un switch ?
	- Un switch (commutateur) est un dispositif de réseau utilisé pour connecter plusieurs appareils, tels que des ordinateurs, des serveurs, des imprimantes et d'autres équipements de réseau, au sein d'un réseau local (LAN). Il fonctionne principalement au niveau 2 (couche de liaison de données) du modèle OSI (Open Systems Interconnection) et facilite la communication entre les appareils connectés en transmettant des paquets de données.
- Quel est l'utilité d'un switch ? 
	- L'utilité d'un switch est multiple :
	1.  Connectivité : Il permet de relier plusieurs appareils entre eux, facilitant ainsi la communication et le partage de ressources au sein d'un réseau local.
	2.  Gestion du trafic : Le switch examine les paquets de données qui lui parviennent et les dirige vers l'appareil de destination approprié. Contrairement à un hub, qui envoie les paquets à tous les appareils connectés, un switch transmet les paquets uniquement à l'appareil concerné, ce qui réduit la congestion du réseau et améliore les performances.
	3.  Gestion des collisions : Un switch attribue une bande passante dédiée à chaque connexion, ce qui réduit les risques de collision de paquets de données et améliore la fiabilité et la vitesse du réseau.
	4.  Sécurité : Les switchs gèrent les communications entre les appareils connectés, ce qui peut contribuer à améliorer la sécurité du réseau en empêchant les accès non autorisés et en limitant la diffusion des paquets à des destinations spécifiques.
	5.  Évolutivité : Les switchs sont généralement modulaires, ce qui permet d'ajouter ou de retirer des appareils du réseau sans perturber les autres connexions. Ils peuvent être utilisés pour créer de petits réseaux domestiques ou pour étendre des réseaux d'entreprise complexes.

### LAYER 3 DEVICES

### MULTILAYER SWITCH

- Qu’est-ce qu’un multilayer switch ?
	- Multi-layer switching combines layer 2, 3 and 4 switching technologies and provides high-speed scalability with low latency. Multi-layer switching can move traffic at [wire speed](https://en.wikipedia.org/wiki/Wire_speed "Wire speed") and also provide layer 3 routing.

## DOMAINE DE COLLISION

- Qu’est-ce qu’un domaine de collision ?
	- Segment du réseau lequel les transmissions de données/les signaux peuvent entrer en collision physique entre elles, par exemple sur un point d’accès Wifi pour anciennement, sur un Hub Ethernet.
- Les hôtes qui accédent au même domaine de collision sont en compétition pour accéder au média de communication.

## DOMAINE DE BROADCAST

- Qu’est-ce qu’un domaine de broadcast ?
	- Un domaine de broadcast est une division logique d’un réseau dans lequel tous les hôtes du réseaux peuvent envoyer à tout les autres hôtes en envoyant un message broadcast au niveau de la couche 2, typiquement par du flooding.

## SWITCH ET LES DOMAINES DE BROADCAST ET DE COLLISION

- Qu’est-ce qu’il permet de faire (en lien avec les domaines de collision) ?
	- Un switch segmente les domaines de collision de manière transparente et automatique
- Comment un switch segmente les domaines de collision ?
	- Une interconnexion de switches Ethernet constitue un domaine de broadcast, mais chaque port du switch constitue un domaine de collision séparé.

### FONCTIONNEMENT D’UN SWITCH ETHERNET

- Où s’installe un switch ?
	- Sur un Lan
- Comment crée t’on l’inter-connection entre les hôtes ?
	- Elle se fait simplement en branchant les équipements
- L’inter-connection entre les hôtes ne perturbe pas le réseau existant
- En combien de parties est divisé le domaine de collision ?
	- En autant de domaines qu’il y a de ports sur le switch
- De quel principe dépendent certains protocoles conçus pour un BUS (topologie physique) ?
	- Du broadcast
- Quels sont les protocoles conçus pour un BUS nécessitent un broadcast ?
	- ARP et DHCP
- Hub
	- ![[Pasted image 20230407133031.png]]
- Switch
	- ![[Pasted image 20230407133109.png]]
- Le switch doit détecter et résoudre les boucles de manière transparente.
- Comment un switch réussi à détecter et résoudre les boucles de manière transparente ?
	- Il construit un arbre de recouvrement (STP, RSTP)
- Un switch écoute sur toutes les adresses MAC, on dit que ses ports sont en mode ?
	- Promiscuous
- Les hôtes n’ont pas ce même fonctionnement ils filtrent de manière positive sur :
	- Adresse Ethernet
	- Adresse Multicast des groupes qu’ils ont rejoint
	- Le broadcast

### EUI - 48

- Qu’est-ce que EUI-48
	- EUI-48 (Extended Unique Identifier - 48 bits) est un identifiant unique de 48 bits utilisé pour identifier de manière unique les interfaces réseau au niveau de la couche de liaison de données (couche 2) du modèle OSI. EUI-48 est principalement utilisé pour les adresses MAC (Media Access Control) dans les réseaux Ethernet et Wi-Fi.

L'adresse EUI-48 est composée de deux parties :

1.  OUI (Organizationally Unique Identifier) : Les 24 premiers bits de l'adresse EUI-48 sont appelés OUI. L'OUI est attribué par l'IEEE (Institute of Electrical and Electronics Engineers) à chaque fabricant de matériel réseau, garantissant ainsi que chaque OUI est unique. Les fabricants sont responsables de l'attribution d'adresses EUI-48 uniques à leurs produits en utilisant leur OUI comme préfixe.
    
2.  Extension d'identifiant : Les 24 bits restants de l'adresse EUI-48 sont appelés extension d'identifiant. Cette partie de l'adresse est gérée par le fabricant de matériel réseau et est attribuée de manière unique pour chaque interface réseau produite.
    

En combinant ces deux parties, l'EUI-48 assure que chaque adresse MAC est unique à l'échelle mondiale, évitant ainsi les conflits d'adresse dans les réseaux. Toutefois, il est important de noter qu'il existe des exceptions à l'unicité des adresses EUI-48, telles que les adresses MAC locales administrées, qui sont générées et gérées localement et ne garantissent pas l'unicité à l'échelle mondiale.

### COMMUNICATION ENTRE LES DOMAINES DE COLLISION

- Quels sont les différentes manière de communication entre domaines de collision ?
	- Approche naïve
	- Approche learning switch
- Comment fonctionne l’approche naïve ?
	- Le switch copie toutes les trames sur tous les ports sauf celui d’entrée.
- Comment appel t’on le fonctionnement de l’approche naïve ?
	- Le flooding
- Quels sont les désavantages de l’approche naïve ?
	- Elle n’est pas efficace pour les communications qui ont lieu dans le domaine de collision, car on copie du traffic non nécessaire.
	- Elle se trouve équivalente fonctionnellement à un HUB, mais pas physiquement, car elles n’ont pas les mêmes domaine de collisions
- Comment fonction l’approche du learning switch ?
	- On filtre le traffic ou bien on le copie selon la destination, à l’aide d’une table d’association MAC:Numéro de port
- Comment fonctionne le système de table d’association du learning switch ?
	- Chaque entrée de la table est associée à un timer (ageing timer) qui permet d’assurer le changement de port d’une adresse MAC
- Comment fonctionne le système d’apprentissage ?
	- Lorsqu’une trame arrive sur un port, le switch note la source Ethernet et le numéro de port, ou bien met à jour le timer dans la table.
	- Le switch ne forwarde pas les trames dont la destination est pour lui-même (destination locale)
- Quels sont les différents états d’un learning switch ?
	- Learning
	- Flooding
	- Filtering
	- Forwarding
	- Ageing
- Qu’est-ce que l’état Learning d’un learning switch ?
	- Le switch note les adresses sources des trames qui traverse le switch, sur quel port.
- Qu’est-ce que l’état flooding d’un learning switch ?
	- Si une adresse n’est pas connue, le switch copie la trame sur touts les ports, sauf celui d’entrée.
- Qu’est-ce que l’état forwarding d’un learning switch ?
	- Si une adresse est connue dans la table, le switch envoie la trame sur le port indiqué dans cette table
- Qu’est-ce que l’état ageing d’un learning switch ?
	- Chaque adresse mac associée à un numéro de port a une durée de vie associée à un timer, lorsque ce timer arrive à échéance, l’entrée de la table est supprimée.
- Quels sont les adresses de destination spéciales ?
	- Broadcast
	- Multicast
	- Certaines adresses sont réservées pour la communication locale au lien et ne sont pas copiées 

### SWITCH LOGICIELS

#### SWITCH LINUX

- Qu’est-ce qu’un switch linux ?
	- C’est un programme qui tourne dans le noyau, ce n’est donc pas un programme utilisateur mais du code kernel (raisons de performances)
- Qu’est-ce que l’utilité d’un switch linux ?
	- Virtualisation de machines. On les utilisent pour la gestion du réseau des machines virtuelles.
- Comment configure t’on un switch linux ?
	- Avec `iproute2`, les commandes `ip` et `bridge`

## AUTRES APPAREILS RÉSEAUX

### PONT

- Qu'est-ce qu'un pont ?
	- Un bridge (pont) est un dispositif matériel ou logiciel qui permet de relier et de filtrer le trafic entre deux ou plusieurs réseaux locaux (LAN) au niveau de la couche 2 (couche de liaison de données) du modèle OSI (Open Systems Interconnection). Les bridges agissent principalement sur les trames Ethernet et utilisent les adresses MAC (Media Access Control) pour déterminer si une trame doit être transmise à un autre segment du réseau ou non.

Le principal objectif d'un bridge est d'étendre ou de segmenter des réseaux locaux en créant des domaines de collision et de diffusion distincts, tout en permettant la communication entre ces domaines. Cela améliore les performances du réseau en réduisant la congestion et en minimisant les collisions de paquets.

Les bridges fonctionnent en :

1.  Apprenant et maintenant une table d'adresses MAC pour chaque segment de réseau connecté.
2.  Filtrant les trames en fonction de leur adresse MAC de destination et en ne transmettant les trames qu'aux segments de réseau appropriés.
3.  Transmettant les trames de diffusion (broadcast) et de multidiffusion (multicast) à tous les segments de réseau connectés.
4.  Appliquant des règles de filtrage et de gestion du trafic pour améliorer les performances et la sécurité du réseau.

Dans certains cas, les bridges peuvent également être utilisés pour connecter des réseaux utilisant des protocoles de couche 2 différents, tels que Ethernet et Token Ring, bien que cela soit moins courant dans les réseaux modernes. Les bridges sont souvent utilisés dans les réseaux d'entreprise et les centres de données pour gérer et étendre les réseaux locaux.

### ROUTER

- Qu’est-ce qu’un router ?
	- Un routeur est un dispositif matériel ou logiciel utilisé pour connecter et transmettre des paquets de données entre différents réseaux informatiques. Son principal objectif est d'assurer la communication et le transfert d'informations entre des réseaux distincts, généralement sur le protocole Internet (IP).

Les routeurs opèrent principalement sur la couche 3 (couche réseau) du modèle OSI (Open Systems Interconnection), où ils analysent les paquets de données pour déterminer leur destination et choisir le meilleur chemin pour les acheminer. Ils utilisent des tables de routage et des protocoles de routage pour déterminer le chemin optimal vers la destination souhaitée.

Les routeurs jouent un rôle essentiel dans l'infrastructure des réseaux, notamment en permettant :

1.  La connexion de réseaux locaux (LAN) à des réseaux étendus (WAN) ou à Internet.
2.  La segmentation et la gestion du trafic entre différents sous-réseaux pour améliorer les performances et la sécurité.
3.  L'acheminement des paquets de données vers leur destination en suivant les règles de routage définies.
4.  La prise en charge de protocoles de routage dynamiques pour s'adapter aux changements de topologie et de charge du réseau.

### OVERLAY/TUNNEL

- Qu'est-ce qu'un overlay ?
	- Un réseau overlay est une couche de réseau virtuel construite au-dessus d'un autre réseau, généralement pour fournir des fonctionnalités ou des services supplémentaires.
- Quel est l'utilité des réseaux overlay ?
	- Les réseaux overlay sont souvent utilisés pour créer des réseaux privés virtuels (VPN), des réseaux de diffusion de contenu (CDN), ou pour virtualiser les réseaux dans des environnements de cloud computing.
- Comment fonctionne les réseaux overlay ?
	- Les réseaux overlay utilisent généralement des protocoles de tunneling pour encapsuler les paquets de données et les acheminer à travers le réseau sous-jacent.
- Qu'est-ce qu'un tunnel ?

### DES PROTOCOLES QUI PEUVENT ÊTRE UTILE À COMPRENDRE

Ces protocoles de routage sont utilisés pour maintenir et échanger des informations de routage entre les routeurs d'un réseau IP, ce qui permet de déterminer les meilleurs chemins vers les destinations et de s'adapter aux changements de topologie de réseau.

- Qu'est-ce que l'OSPF ?
	- OSPF est un protocole de routage dynamique utilisé pour échanger des informations de routage entre les routeurs d'un réseau IP. Il s'agit d'un protocole de routage à état de lien qui permet aux routeurs de calculer les chemins les plus courts vers toutes les destinations du réseau en utilisant l'algorithme de Dijkstra. OSPF est un protocole de routage interne (IGP), ce qui signifie qu'il est conçu pour être utilisé à l'intérieur d'un seul système autonome.
- Qu'est-ce que l'EIGRP ?
	- EIGRP est un protocole de routage dynamique développé par Cisco. Il s'agit également d'un protocole de routage interne qui utilise un algorithme de routage à vecteur de distance pour déterminer les meilleurs chemins vers les destinations du réseau. EIGRP est capable de converger rapidement et de s'adapter aux changements de topologie de réseau, tout en minimisant la consommation de ressources réseau.
- Qu'est-ce que le RIP ?
	- RIP est un protocole de routage dynamique simple et ancien qui utilise un algorithme de vecteur de distance pour échanger des informations de routage entre les routeurs d'un réseau IP. RIP a été l'un des premiers protocoles de routage IP, mais il est maintenant considéré comme obsolète en raison de ses limitations, telles que sa lente convergence et sa limitation à 15 sauts (hops) entre les routeurs.
- Qu'est-ce que le BGP ?
	- BGP est un protocole de routage externe (EGP) utilisé pour échanger des informations de routage entre les systèmes autonomes (AS) sur Internet. BGP est conçu pour être très évolutif et gérer des milliers de routes, et il est donc utilisé par les fournisseurs de services Internet (ISP) et les grands réseaux d'entreprise pour maintenir la connectivité entre les systèmes autonomes. BGP utilise un algorithme de routage à vecteur de chemin et prend en compte de nombreux attributs pour sélectionner les meilleurs chemins vers les destinations du réseau.

## ADRESSAGE IP

## ROUTAGE

- Qu’est-ce que le routage ?
	- Le routage, dans le contexte des réseaux informatiques, est le processus de sélection des chemins dans un réseau pour envoyer des paquets de données d'un dispositif à un autre. Les routeurs sont les dispositifs de réseau responsables de la gestion du routage. Leur principal objectif est de déterminer le meilleur chemin pour acheminer les paquets de données entre les différents réseaux et sous-réseaux, en fonction de divers paramètres tels que la distance, la vitesse, la charge du réseau et la disponibilité des routes.

Le routage se fait généralement en deux étapes :

1.  Création de la table de routage : La table de routage est une base de données stockée dans le routeur qui contient des informations sur les chemins possibles pour atteindre différentes destinations du réseau. Les routeurs obtiennent ces informations à partir de protocoles de routage (comme RIP, OSPF, EIGRP ou BGP), de la configuration manuelle ou de mécanismes de découverte automatique de réseau. La table de routage inclut des informations telles que l'adresse IP de destination, l'adresse IP de la passerelle (le prochain saut) et la métrique (un indicateur de la qualité ou de la performance du chemin).
    
2.  Prise de décision de routage : Lorsqu'un paquet de données arrive au routeur, celui-ci consulte la table de routage pour déterminer le meilleur chemin pour acheminer le paquet vers sa destination finale. Le routeur sélectionne généralement le chemin avec la métrique la plus faible ou la plus favorable. Une fois le chemin sélectionné, le routeur modifie le paquet, met à jour les informations d'en-tête (telles que l'adresse de la passerelle) et l'envoie au prochain saut sur le chemin sélectionné.
    

Il existe deux types principaux de routage :

1.  Routage statique : Le routage statique est configuré manuellement par l'administrateur réseau. Les chemins et les passerelles pour atteindre différentes destinations sont définis explicitement, et les routeurs n'apprennent pas automatiquement les chemins disponibles. Le routage statique convient aux petits réseaux où les chemins et la topologie du réseau changent rarement.
    
2.  Routage dynamique : Le routage dynamique utilise des protocoles de routage pour permettre aux routeurs d'échanger des informations sur les chemins disponibles et les changements de topologie du réseau. Les routeurs mettent à jour automatiquement leur table de routage en fonction des informations reçues, ce qui permet une adaptation rapide aux changements de réseau. Le routage dynamique est plus adapté aux réseaux plus grands et plus complexes, où la topologie est susceptible de changer fréquemment.

- Qu’est-ce que le policy routing ?
	- Le policy routing, ou routage basé sur les politiques, est une méthode de routage avancée qui permet de déterminer le chemin des paquets de données dans un réseau en fonction de critères spécifiques définis par l'administrateur réseau, plutôt que de se baser uniquement sur l'adresse de destination, comme dans le routage traditionnel.

Dans le policy routing, les paquets de données peuvent être acheminés en fonction de divers attributs, tels que l'adresse source, le type de service, le protocole, le port, la charge du réseau ou d'autres informations spécifiques au paquet. Cela permet aux administrateurs réseau de mettre en œuvre des stratégies de contrôle plus granulaires pour optimiser la performance du réseau, assurer la qualité de service (QoS), mettre en place des mécanismes de sécurité ou satisfaire à des exigences réglementaires.

Le policy routing est généralement mis en œuvre à l'aide de règles de routage qui définissent les critères de correspondance des paquets et les actions à effectuer sur ces paquets. Par exemple, une règle de policy routing peut stipuler que tous les paquets provenant d'une adresse IP spécifique doivent être acheminés via une passerelle spécifique, indépendamment de la destination. Les routeurs prennent en compte ces règles lorsqu'ils prennent des décisions de routage.

Le policy routing peut être utilisé pour répondre à divers besoins, tels que :

1.  Équilibrage de charge : Le policy routing peut aider à répartir le trafic sur plusieurs liens ou passerelles pour optimiser l'utilisation des ressources et éviter la congestion.
    
2.  Qualité de service : Les paquets associés à des applications sensibles au délai, comme la VoIP ou la vidéoconférence, peuvent être acheminés via des chemins à faible latence ou à haute priorité pour garantir une expérience utilisateur satisfaisante.
    
3.  Sécurité : Les paquets de données peuvent être acheminés en fonction de leur source, de leur destination ou de leur contenu, pour renforcer la sécurité du réseau et contrôler l'accès aux ressources.
    
4.  Conformité réglementaire : Le policy routing peut être utilisé pour s'assurer que certains types de trafic, comme les communications financières ou médicales, sont acheminés conformément aux exigences légales ou réglementaires.


### NAT

- Qu’est-ce que le NAT ?
	- Le NAT (Network Address Translation) est une technique utilisée dans les réseaux informatiques pour permettre à plusieurs dispositifs ayant des adresses IP privées de partager une ou plusieurs adresses IP publiques pour accéder à Internet ou à d'autres réseaux externes. Le NAT est souvent mis en œuvre dans les routeurs et les pare-feu pour gérer le trafic entre les réseaux privés et les réseaux publics.

Le NAT fonctionne en modifiant les adresses IP et les numéros de port des paquets IP lorsqu'ils traversent le routeur ou le pare-feu. Il existe plusieurs types de NAT, dont les plus courants sont :

1.  NAT statique : Dans ce cas, une adresse IP privée est associée à une adresse IP publique spécifique. Chaque fois qu'un dispositif du réseau privé communique avec l'extérieur, son adresse IP privée est remplacée par l'adresse IP publique associée.
    
2.  NAT dynamique : Contrairement au NAT statique, le NAT dynamique attribue les adresses IP publiques disponibles de manière temporaire aux dispositifs du réseau privé lorsqu'ils ont besoin de communiquer avec l'extérieur. L'adresse IP publique est ensuite libérée et remise dans le pool d'adresses IP publiques une fois la communication terminée.
    
3.  PAT (Port Address Translation) ou NAPT (Network Address Port Translation) : Ce type de NAT, souvent appelé "NAT overload" ou simplement "masquerade", permet à plusieurs dispositifs du réseau privé de partager une seule adresse IP publique. Le routeur ou le pare-feu effectue la traduction d'adresse en modifiant à la fois l'adresse IP et le numéro de port pour distinguer les communications de chaque dispositif.
    

Le NAT présente plusieurs avantages, tels que :

1.  Économie d'adresses IP : Le NAT permet de réduire le besoin en adresses IP publiques, ce qui est important étant donné la pénurie d'adresses IPv4.
    
2.  Sécurité : En masquant les adresses IP privées des dispositifs internes, le NAT ajoute une couche de sécurité en rendant plus difficile pour les attaquants de cibler directement ces dispositifs.
    
3.  Flexibilité : Le NAT permet aux réseaux privés d'utiliser n'importe quelle plage d'adresses IP sans se soucier de la compatibilité avec les réseaux externes.
    

Cependant, le NAT peut également présenter des inconvénients, tels que la complexité de la configuration, la dégradation des performances dues à la traduction d'adresse et la difficulté à mettre en œuvre certaines applications et services qui nécessitent des communications directes entre les dispositifs.
- nftables

### MASQUERADE

- Qu’est-ce que la masquerade ?
	- C’est une technique utilisée pour masquer l'identité des adresses IP privées derrière une seule adresse IP publique, généralement celle d'un routeur ou d'un pare-feu. Cette technique est souvent utilisée dans les réseaux domestiques et les réseaux d'entreprise où les adresses IP privées ne peuvent pas être routées directement sur Internet. La masquerade est une forme de traduction d'adresse réseau (Network Address Translation, ou NAT).
- À quoi sert la masquerade ?
	- La masquerade permet aux hôtes du réseau privé d'accéder à Internet en utilisant l'adresse IP publique du routeur ou du pare-feu, tout en conservant leurs adresses IP privées.
- Comment fonctionne la masquerade ?
	- Lorsqu'un hôte du réseau privé envoie une requête sur Internet, le routeur ou le pare-feu remplace l'adresse IP privée de l'hôte par son adresse IP publique avant de transmettre la requête. Les réponses aux requêtes sont ensuite envoyées à l'adresse IP publique du routeur ou du pare-feu, qui inverse le processus de masquerade et transmet les réponses à l'adresse IP privée appropriée.
- Comment mettre en place la masquerade sur Linux ?
	- À l’aide la commande `iptables`
- Quels sont les avantages de la masquerade ?
	1.  Économie d'adresses IP : Comme plusieurs hôtes peuvent partager une seule adresse IP publique, la masquerade permet d'économiser des adresses IP publiques, qui sont une ressource limitée.
	2.  Sécurité : La masquerade ajoute une couche de sécurité en masquant les adresses IP privées des hôtes du réseau. Les attaquants ne peuvent pas cibler directement les hôtes internes en se basant uniquement sur leurs adresses IP.
	3.  Flexibilité : La masquerade permet à un réseau d'utiliser n'importe quelle plage d'adresses IP privées sans se soucier de la compatibilité avec les adresses IP publiques.

## CONFIGURATION DES PÉRIPHÉRIQUES VIRTUELS

### VETH

- Qu'est-ce qu'un VETH ?
	- Un veth (Virtual Ethernet) est un type d'interface réseau virtuelle dans les environnements Linux. Il fonctionne comme un câble Ethernet virtuel, permettant de connecter deux espaces de noms réseau (namespaces) ou d'autres dispositifs réseau virtuels entre eux. Les paires veth fonctionnent en tandem : les paquets envoyés sur une interface de la paire sont reçus par l'autre interface. Les veth sont généralement utilisés dans les conteneurs, les machines virtuelles et les environnements de réseau complexes.
- Pour créer un lien veth et le configurer avec iproute2 (outil "ip" dans Linux), suivez les étapes ci-dessous :
1.  Créez une paire veth avec les noms veth1 et veth2 :
```bash
sudo ip link add veth1 type veth peer name veth2
```
2.  Attribuez des adresses IP aux interfaces veth :
```bash
sudo ip addr add 192.168.1.1/24 dev veth1 sudo ip addr add 192.168.1.2/24 dev veth2
```
3.  Activez les interfaces veth :
```bash
sudo ip link set veth1 up sudo ip link set veth2 up
```

Maintenant, les deux interfaces veth sont configurées et peuvent être utilisées pour transmettre des paquets entre elles. Vous pouvez ajouter des routes via "ip route" si nécessaire, par exemple :

```bash
sudo ip route add 192.168.2.0/24 via 192.168.1.2 dev veth1
```

Cela ajoutera une route pour atteindre le réseau 192.168.2.0/24 via l'interface veth1 et l'adresse IP 192.168.1.2.

Pour créer des liens virtuels supplémentaires, répétez simplement les étapes ci-dessus en utilisant des noms et des adresses IP différents pour les interfaces veth.

Il est important de noter que les interfaces veth ne sont pas limitées à la connexion de deux espaces de noms réseau locaux. Vous pouvez également les utiliser pour connecter des espaces de noms réseau à des bridges Linux, des dispositifs Open vSwitch et d'autres dispositifs de réseau virtuels.

### BRIDGE

- Qu'est-ce qu'un bridge
	- Un bridge (pont) est un dispositif réseau qui permet d'interconnecter plusieurs segments de réseau au niveau de la couche 2 (couche de liaison de données) du modèle OSI. Dans le contexte des réseaux Linux, un bridge est souvent utilisé pour connecter des interfaces réseau virtuelles, telles que les interfaces veth, tap ou les interfaces d'autres machines virtuelles ou conteneurs, pour créer un réseau virtuel partagé. Les bridges fonctionnent de manière similaire aux commutateurs réseau, en apprenant les adresses MAC et en acheminant les paquets entre les ports connectés.

Voici comment créer un bridge et le configurer avec iproute2 (outil "ip" dans Linux) :

1.  Installez le paquet "bridge-utils" si nécessaire (cette étape peut varier selon la distribution Linux) :

```bash
sudo apt-get install bridge-utils
```

2.  Créez un bridge nommé "br0" :

```bash
sudo ip link add name br0 type bridge
```

3.  Attribuez une adresse IP au bridge :

```bash
sudo ip addr add 192.168.1.1/24 dev br0
```


4.  Activez le bridge :

```bash
sudo ip link set br0 up
```

Maintenant, le bridge est configuré et peut être utilisé pour connecter des interfaces réseau virtuelles. Pour ajouter des interfaces veth, tap ou autres au bridge, utilisez la commande suivante :

```bash
sudo ip link set veth1 master br0
```

Cela ajoutera l'interface "veth1" au bridge "br0". Répétez cette étape pour toutes les interfaces que vous souhaitez ajouter au bridge.

Notez que la configuration des routes avec "ip route" est généralement utilisée pour la couche 3 (couche réseau) du modèle OSI et ne s'applique pas directement aux bridges. Cependant, si vous souhaitez ajouter des routes pour atteindre d'autres réseaux via le bridge, vous pouvez le faire en utilisant l'adresse IP du bridge comme passerelle :

```bash
sudo ip route add 192.168.2.0/24 via 192.168.1.1 dev br0
```

Cela ajoutera une route pour atteindre le réseau 192.168.2.0/24 via l'interface "br0" et l'adresse IP 192.168.1.1.

Pour créer des liens virtuels supplémentaires, il vous suffit de créer et d'ajouter d'autres interfaces réseau virtuelles (telles que veth, tap, etc.) au bridge en suivant les étapes ci-dessus.

## NAMESPACE RÉSEAUX LINUX

- Quel est l’utilité des namespaces Linux ?
	- L’isolation. En effet chaque processus “croit” avoir toutes les ressources pour lui et n’a pas accès aux ressources des processus dans un autre namespace.
- Quels sont les propriétés des namespaces Linux ?
	- Ils n’engendrent quasiment pas d’overhead de virtualisation. Ils sont ainsi à la base des conteneurs (docker).
	- Ils sont assignable individuellement à un groupe de processus.
	- Ils sont anonymes dans le kernel Linux
- Quel est la signification des termes suivants ?
	- `mnt` : points de montage de systèmes de fichiers
	- `pid` : ensemble d’identifiants de processus
	- `net` : pile réseau
	- `ipc` : des ressources de communication inter-processus
	- `uts` : unix time sharing
	- `user` ensemble d’identifiants utilisateurs
	- `time` fuseau horaire des processus
- Qu’est-ce qu’un namespace réseau ?
	- C’est une instance supplémentaire de toute la pile réseau de l’hôte avec
		- ses propres routes
		- son propre firewall
		- ses propres interfaces réseaux
		- ses propres entrées relative au réseau dans `/proc` et `/sys`
- Comment nommer un namespace `net` avec les commandes utilisateur
	- `ip netns add/set`
	- Ajout de ns1 : `ip netns add ns1`
	- Suppression de ns1 `ip netns del ns1`
	- Lister les namespace existant `ip netns list`
	- Trouver le namespace d'un processus `ip netns identify <pid>`
	- Déplacer le namespace d'une interface réseau `ip link set <iface> netns ns1`
	- Exécuter un processus dans un namespace réseau `ip netns exec ns1 bash`
	- Déplacer une interface dans le namespace par défaut (pid 1) `ip link set <iface> netns 1`
- Comment est représenter un namespace réseaux linux ?
	- Par la `struct net` du noyau Linux

Les namespaces Linux sont une fonctionnalité du noyau Linux qui permet d'isoler et de virtualiser les ressources système pour un processus ou un groupe de processus. Dans le contexte des réseaux, les namespaces réseau (netns) permettent de créer des environnements réseau isolés, chacun avec ses propres interfaces, routes et règles de pare-feu.

Voici comment utiliser les namespaces réseau avec l'outil "ip" d'iproute2 :

1.  Créez un nouveau namespace réseau :

```bash
sudo ip netns add netns1
```

Cela crée un namespace réseau appelé "netns1".

2.  Pour exécuter des commandes spécifiques au namespace, utilisez la syntaxe suivante :

```bash
sudo ip netns exec netns1 <commande>
```

Par exemple, pour afficher les interfaces réseau dans "netns1" :

`sudo ip netns exec netns1 ip link`

3.  Créez une paire d'interfaces veth :

`sudo ip link add veth1 type veth peer name veth2`

Cela crée deux interfaces, "veth1" et "veth2", reliées l'une à l'autre.

4.  Ajoutez une extrémité de la paire d'interfaces veth (par exemple, "veth1") au namespace :

`sudo ip link set veth1 netns netns1`

5.  Configurez les interfaces dans le namespace et dans l'espace global. Par exemple, attribuez des adresses IP et activez-les :

```bash
sudo ip addr add 10.0.0.1/24 dev veth2 
sudo ip link set veth2 up 
sudo ip netns exec netns1 ip addr add 10.0.0.2/24 dev veth1 
sudo ip netns exec netns1 ip link set veth1 up 
sudo ip netns exec netns1 ip link set lo up
```

6.  Configurez les routes si nécessaire. Par exemple, pour définir l'interface "veth1" comme passerelle par défaut dans le namespace "netns1" :

`sudo ip netns exec netns1 ip route add default via 10.0.0.1 dev veth1`

Maintenant, vous avez un namespace réseau avec sa propre interface, des adresses IP et des routes. Vous pouvez exécuter des applications ou des commandes spécifiques à ce namespace pour tester la connectivité, comme "ping" :

`sudo ip netns exec netns1 ping 10.0.0.1`

Pour supprimer un namespace, utilisez la commande suivante :

`sudo ip netns del netns1`

Cela supprimera le namespace "netns1" et toutes les ressources qui lui sont associées.

## INTERFACES RÉSEAUX VIRTUELLES

### INTERFACE DE TYPE VETH
- Qu'est-ce que `veth` ?
	- `veth` est une paire d'interface virtuelle ethernet connectées
	- ![[Pasted image 20230407152948.png]]
- `veth0` et `veth0` (dans le namespace `ns1`) une paire d'interface, on envoi des paquets depuis `veth0` qu'est ce qu'il se passe ?
	- Ils sont envoyés sur `veth0` dans le namespace `ns1`
- Il faut monter les deux côtés de la paire
	- `ip link set up veth0`
	- `ip netns exec <namespace> ip link set up veth0`
- Comment les bridgées ?
	- Avec une interface de type bridge `ip link set <iface> master br0`


## ANSIBLE

### INTRODUCTION

- Qu'est-ce qu'ansible ?
	- C'est un langage d'automatisation qui permet de décrire l'infrastructure IT d'une application à l'aide d'un **Ansible Playbook**.
	- C'est un moteur d'automatisation qui permet de lancer des **Ansible Playbook**
- Qu'est-ce qu'ansible tower ?
	- Ansible Tower est une framework pour controller, sécuriser et gérer l'automatisation Ansible à l'aide d'une interface graphique et API REST.
- Qu'est-ce qu'un `play` ?
	- Un `play` est une séquence de tâches à exécuter sur un groupe d'hôtes dans le cadre d'un processus d'automatisation Ansible.
	- ![[Pasted image 20230409114824.png]]
- Qu'est-ce qu'un `playbook` ?
	- Un `playbook` est un fichier texte écrit en YAML qui contient une ou plusieurs séquences de tâches (**plays**) à exécuter sur des groupes d'hôtes cibles.
	- ![[Pasted image 20230407171738.png]]
- Quels sont les caractéristiques d'Ansible
	- Simplicité
	- Puissance
	- Sans agent
- Qu'est-ce que la caractéristique de simplicité d'Ansible ? Car il a
	- Langage lisible
	- Pas de compétence spéciale requise
	- Tâche exécuté séquentiellement
	- **Productif rapidement**
- Qu'est-ce que la caractéristique de puissance d'Ansible ? Car il permet
	- Déploiement d'application
	- Gestion de la configuration
	- Workflow orchestration
	- **Organisation du cycle de vie de l'application**
- Qu'est-ce que la caractéristique Sans agent d'Ansible ?
	- Utilise OpenSSH & WinRM
	- Pas d'agent exploitable ou à mettre à jour
	- **Plus efficient et plus sécurisé**

 > [!summary] 
> - Un playbook c'est plusieurs plays

### OPÉRATION SIMPLE ET CONCEPT GÉNÉRAUX

- Comment Ansible fonctionne ?
- Qu'est-ce que l'idempotence ?
	- Une opération est dite idempotente si, lorsqu'elle est effectuée plusieurs fois avec les mêmes paramètres, elle produit le même résultat que si elle n'avait été effectuée qu'une seule fois.
	- En d'autres termes, une opération idempotente peut être répétée plusieurs fois sans changer l'état du système après la première exécution. Cette propriété est particulièrement importante pour assurer la stabilité et la prévisibilité des systèmes informatiques, car elle permet de gérer les erreurs et les défaillances sans provoquer d'effets secondaires indésirables.
- On dit que les playbooks et les modules Ansible sont ?
	- Idempotents
- Qu'est-ce que cela signifie de dire que les playbooks et les modules Ansible sont idempotents ?
	- Les playbooks et les modules Ansible sont idempotents, ce qui signifie qu'ils ne vont pas réappliquer un changement de configuration si celui-ci a déjà été effectué sur les nœuds gérés. Cette idempotence assure que les playbooks ne modifient pas l'état du système de manière inattendue lorsqu'ils sont exécutés plusieurs fois.
- Qu'est-ce qu'un module Ansible ?
	- Un module est constitué de morceaux de code transféré sur le système cible et exécuté pour satisfaire la tâche déclaré. 
- Qu'est-ce que les `Run Commands` ?
	- Ce sont des modules qui permettent d'exécuter des commandes sur le système cible
		- `command`
		- `shell`
		- `script`
		- `raw`
- Qu'est-ce qu'un module ?
	- Un outil préconçu pour effectuer une action spécifique, comme installer un package, copier un fichier, redémarrer un service, ou exécuter une commande. Les tâches peuvent également avoir des paramètres qui personnalisent leur comportement.
- Qu'est-ce que le module `command` ?
	- C'est un module qui permet d'exécuter des commandes sur le système hôte.
- Qu'est-ce que le module `shell` ?
	- C'est un module qui permet d'exécuter les commandes à travers un shell comme `/bin/sh`, on peut donc utiliser des pipes.
- Qu'est-ce que le module `script` ?
	- C'est un module qui permet de lancer un script local sur un noeud distant après l'avoir transféré.
- Qu'est-ce que le module `raw` ?
	- C'est un module qui exécute une commande sans utiliser le module de sous-système Ansible. Sur des systèmes qui n'ont pas python ce module peut être très utile.
- Qu'est-ce qu'un `Inventory` ?
	- Un `Inventory` est une collection d'hôtes (noeuds) avec des données associés auxquels Ansible peut se connecter et gérer.
- Hosts (nodes)
- Groups
- Inventory-specific data (variables)
- Static or dynamic sources
	- ![[Pasted image 20230407154907.png]]
	- ![[Pasted image 20230407154915.png]]
- Qu'est-ce qu'une commande `ad-hoc` ?
	- Une commande `ad-hoc` est une commande pour une seule tâche Ansible qui doit être exécuter rapidement, mais que l'on ne veut pas garder pour plus tard.
	- ![[Pasted image 20230407155042.png]]
- Qu'est-ce qu'un `fact` ?
	- Un `fact` est multitude d'informations qui sont dérivés de l'examination d'un système hôte qui sont stockés comme variable pour être utiliser plus tard dans un `play`.
	- ![[Pasted image 20230407155210.png]]

#### VARIABLE

- Qu'est-ce qu'une variable ?
	- Une variable est un moyen de stocker des informations dynamiques ou statiques qui peuvent être utilisées dans un playbook, une tâche, un modèle, un rôle ou un fichier d'inventaire.
- Quels sont les différents types de variables ?
	- Variable d'inventaire
	- Variable de playbook
	- Variable de rôles
	- Variable de l'utilisateur
- Qu'est-ce qu'une variable d'inventaire ?
	- Ces variables sont définies dans les fichiers d'inventaire pour les hôtes ou les groupes d'hôtes. Elles sont utilisées pour définir des informations spécifiques à un hôte ou à un groupe, comme les adresses IP, les mots de passe, etc.
- Qu'est-ce qu'une variable de playbook ?
	- Les variables peuvent être définies directement dans un playbook, soit en tant que variable individuelle ou dans un fichier externe à l'aide du module `include_vars`.
	- Elles peuvent être définies au niveau du play et sont accessibles à toutes les tâches du play.

```yaml
 - name: Apply tasks with custom variables
  hosts: target_hosts
  vars:
    package_name: nginx
    config_file_path: /etc/nginx/nginx.conf

```

- Qu'est-ce qu'une variable de rôle ?
	- Variables de rôle : Les variables spécifiques à un rôle sont définies dans le dossier `defaults` ou `vars` d'un rôle. Elles sont utilisées pour personnaliser le comportement d'un rôle en fonction des besoins de chaque hôte ou groupe d'hôtes.
- Qu'est-ce qu'une variable de tâche ?
	- Les variables peuvent être définies au niveau d'une tâche et sont généralement utilisées pour stocker les résultats d'une tâche ou les données spécifiques à la tâche en cours.
- Qu'est-ce qu'une variable d'utilisateur ?
	- Les variables peuvent être définies par l'utilisateur lors de l'exécution d'un playbook en utilisant l'option `-e` ou `--extra-vars` sur la ligne de commande.

#### TÂCHE

- Qu'est-ce qu'une `task` (tâche) ?
	- Une tâche (task en anglais) est une unité de travail élémentaire qui réalise une action spécifique sur un hôte ou un groupe d'hôtes à l'aide d'un module.
	- ![[Pasted image 20230407160631.png]]
- Qu'est-ce qu'une `handler task` ?
	- Une handler task (tâche gestionnaire en français) est une tâche spéciale qui est déclenchée en réponse à une notification d'une autre tâche.
	 - Elles ne s'exécutent que si elles sont notifiées par une autre tâche, et elles ne sont exécutées qu'une seule fois, même si elles sont notifiées plusieurs fois.
	- ![[Pasted image 20230407160758.png]]
- Qu'est-ce qu'un `host selector` ?
	- Le Host Selector est utilisé pour déterminer sur quels hôtes d'un inventaire une séquence de tâches (un play) doit être exécutée.
	- Dans un playbook Ansible, le sélecteur d'hôtes est défini par l'attribut `hosts`.

```yaml
- name: Apply tasks to web servers
  hosts: web_servers
```

- Qu'est que `privilege escalation` ? 
	- Dans Ansible, l'élévation de privilèges est utilisée pour exécuter des tâches avec des droits d'administration élevés, comme root sur les systèmes Unix/Linux ou Administrateur sur les systèmes Windows.

```yaml
- name: Apply tasks with elevated privileges
  hosts: target_hosts
  become: yes
```

#### L'ORDRE D'EXÉCUTION DES TÂCHES

- Ansible exécute le playbook dans l'ordre suivant :
	1. **pre_tasks**.
	2. handlers **déclenché** par **pre_tasks**.
	3. Les rôles importé statiquement qui sont listés dans la section **roles**.
	4. Les tâches listées dans la section des tâches.
	5. les *handlers* déclenchées par les **rôles** et **tâches**.
	6. **post_tasks**
	7. les *handlers* déclenchées par **post_tasks**
	- ![[Pasted image 20230409190034.png]]
- 
	
### OPÉRATIONS AVANCÉES

#### TEMPLATES

- Qu'est-ce qu'une template ?
	- Les templates sont des fichiers texte qui utilisent la syntaxe du moteur de templating Jinja2 pour gérer les variables et les structures de contrôle.
- Quel est l'utilité d'une template ?
	- Ils sont utiles pour générer des fichiers de configuration dynamiques en fonction des variables définies dans un playbook ou pour un hôte particulier (`conditional logic`).
- Comment utiliser une template 
	- Les templates peuvent être utilisés avec le module `template` d'Ansible pour déployer des fichiers de configuration personnalisés sur les hôtes cibles. Par exemple

```yaml
- name: Deploy a dynamic configuration file
  ansible.builtin.template:
    src: myconfig.j2
    dest: /etc/myapp/myconfig.conf
```

#### LOOPS

- Qu'est-ce qu'une boucle ?
	- Les boucles sont utilisées pour exécuter une tâche plusieurs fois avec différentes valeurs.

```yaml
- name: Install multiple packages
  ansible.builtin.package:
    name: "{{ item }}"
    state: present
  loop:
    - package1
    - package2
    - package3
```

#### CONDITIONALS

- Qu'est-ce qu'un conditionnel ?
	- Les conditionnels permettent d'exécuter ou de sauter des tâches en fonction de certaines conditions. 
	- Les conditions peuvent être basées sur des variables, des faits sur les hôtes, des valeurs renvoyées par d'autres tâches, etc.
 - Quel est l'utilité des conditionnels ?
	 - Les conditionnels sont utiles pour adapter le comportement d'un playbook en fonction de différents scénarios.

```yaml
- name: Execute a task if a package is installed
  ansible.builtin.shell: /usr/bin/some-command
  when: "'my_package' in ansible_facts.packages"
```

#### TAGS

- Qu'est-ce qu'un tag ?
	- Les tags sont des étiquettes qui peuvent être appliquées aux tâches ou aux plays pour les organiser et les filtrer.
- Quel est l'utilité d'un tag ?
	- Les tags peuvent être utilisés pour exécuter uniquement certaines parties d'un playbook en fonction des tags spécifiés lors de l'exécution d'Ansible.

```yaml
- name: Configure a service
  ansible.builtin.template:
    src: service.conf.j2
    dest: /etc/service.conf
  tags:
    - configuration

- name: Deploy a service
  ansible.builtin.copy:
    src: service_binary
    dest: /usr/bin/service
  tags:
    - deployment

```

#### BLOCKS

- Qu'est-ce qu'un block ? 
	- Les blocks sont des groupes de tâches qui peuvent être regroupées pour appliquer certaines fonctionnalités à l'ensemble du groupe
 - Quel est l'utilité d'un block ?
	 - Les blocks peuvent être utilisés pour définir des attributs communs à toutes les tâches du bloc, comme les conditionnels, les élévations de privilèges ou les tags.

```yaml
- name: Example of using blocks in a playbook
  hosts: all
  tasks:
    - name: Configure and deploy application
      block:
        - name: Install required packages
          ansible.builtin.package:
            name: "{{ item }}"
            state: present
          loop:
            - package1
            - package2

        - name: Deploy configuration file
          ansible.builtin.template:
            src: app_config.j2
            dest: /etc/app/config.conf

        - name: Start application service
          ansible.builtin.service:
            name: app_service
            state: started
      become: yes
      tags:
        - deployment

      rescue:
        - name: Log error and send notification
          ansible.builtin.debug:
            msg: "An error occurred during application deployment"

      always:
        - name: Clean up temporary files
          ansible.builtin.file:
            path: /tmp/deployment
            state: absent

```

#### ROLES

- Qu'est-ce qu'un role ?
	- Les rôles (roles) sont une façon d'organiser les tâches, les variables, les fichiers et autres éléments liés à la configuration d'Ansible de manière modulaire et réutilisable
	- ![[Pasted image 20230407174747.png]]
- Quel est l'utilité des rôles ?
	- Les rôles permettent de simplifier et de structurer les playbooks en séparant la logique des différentes parties d'un système.

#### ANSIBLE GALAXY

- Qu'est-ce qu'Ansible Galaxy ?
	- Ansible Galaxy est un hub centralisé et une plateforme de partage pour les rôles Ansible créés par la communauté.
- Quel est l'utilité d'Ansible Galaxy ?
	- Il permet aux utilisateurs de trouver, réutiliser et partager des rôles Ansible pour faciliter la gestion de la configuration et le déploiement d'applications et de services.


## WIREGUARD

### INTRODUCTION

- Qu'est-ce que WireGuard ?
	- WireGuard est un protocole de réseau privé virtuel (VPN) ou "secure network tunnel" open-source conçu pour offrir une connexion sécurisée et cryptée entre les dispositifs sur un réseau.
- Qu'est-ce qu'un "secure network tunnel" ?
	- Un tunnel de réseau sécurisé (secure network tunnel) est une méthode de communication sécurisée qui permet à deux dispositifs ou réseaux distants de transférer des données de manière sécurisée et chiffrée à travers un réseau non sécurisé, généralement Internet.
	- https://www.ibm.com/docs/en/cloud-paks/cloud-pak-watson-aiops/3.3.1?topic=connections-secure-tunnel
	- https://www.cloudflare.com/learning/network-layer/what-is-tunneling/
	- https://en.wikipedia.org/wiki/Tunneling_protocol
- Comment fonctionne (grossièrement) un "secure network tunnel" ?
	- Le tunnel de réseau sécurisé crée un canal de communication privé en encapsulant et en chiffrant les données à l'intérieur d'un protocole de transport standard, de sorte que les données ne peuvent être interceptées ou décodées par des tiers non autorisés.
- Quel est l'utilité d'un "secure network tunnel" ?
	- Les tunnels de réseau sécurisés sont souvent utilisés pour mettre en place des réseaux privés virtuels (VPN) qui permettent aux utilisateurs et aux organisations de sécuriser leurs communications sur des réseaux publics ou non sécurisés.
- Quels sont les trois protocoles VPN les plus courant ?
	- IPsec
	- OpenVPN
	- WireGuard
- L'interface de tunnel virtuel (virtual tunnel interface) se base sur quels principes ?
	- Une association entre une clé public et l'adresse IP de la source du tunnel.
	- Un "single round trip key exchange" basé sur NoiseIK.
	- Gestion transparente à l'utilisateur des créations de sessions en utilisant un mécanisme de machine d'état temporisateur ("timer state machine").
- Dans quel couche OSI WireGuard opère-t'il ?
	- La couche 3.

### CRYPOTKEY ROUTING

- Qu'est-ce que le *Cryptokey Routing* ?
	- Le *Cryptokey Routing* est un concept utilisé par WireGuard pour établir et maintenir des connexions sécurisées entre les pairs dans un réseau VPN.
	- Au lieu d'utiliser des configurations complexes basées sur des adresses IP ou des noms de domaine, **WireGuard associe directement les clés publiques aux adresses IP autorisées pour simplifier la gestion et le routage des connexions VPN**
	- ![[Pasted image 20230408171030.png]]
- Quels sont les étapes lié au "Cryptokey Routing" 
	- Génération des clés
	- Configuration des pairs
	- Établissement de la connexion
		- IP autorisé ?
		- Si oui, quel clé publique ?
	- Routage des paquets
- En quoi consiste l'étape de générations des clés ?
	- Chaque pair (client ou serveur) génère une paire de clés (clé privée et clé publique). La clé privée est conservée secrète par chaque pair, tandis que la clé publique est partagée entre les pairs pour établir une connexion sécurisée.
- En quoi consiste la configuration des pairs ?
	- Les pairs sont configurés en ajoutant des sections `[Peer]` dans leurs fichiers de configuration respectifs. Chaque section `[Peer]` contient la clé publique de l'autre pair et une liste d'adresses IP autorisées pour ce pair. L'adresse IP autorisée peut être une adresse IP unique ou un bloc CIDR, et elle détermine à quelle adresse IP le pair peut envoyer des paquets via le tunnel VPN.
- En quoi consiste l'établissement de la connexion ?
	- Lorsqu'un pair envoie un paquet à travers le tunnel VPN, WireGuard pour vérifié d'abord si l'adresse IP de destination est autorisée pour la clé publique du pair destinataire.
	- Si l'adresse IP est autorisée, WireGuard utilise la clé publique pour chiffrer le paquet avant de l'envoyer au pair destinataire.
- En quoi consiste le routage des paquets ?
	- Lorsque le pair destinataire reçoit le paquet chiffré, il utilise sa clé privée pour déchiffrer le paquet. Ensuite, il vérifie si l'adresse IP source du paquet est autorisée pour la clé publique de l'expéditeur. Si l'adresse IP source est autorisée, le paquet est accepté et traité. Sinon, le paquet est rejeté.
- Maintenant, que nous savons toutes ces choses, qu'est-ce que possède une interface ?
	- Une clé privée
	- Un port UDP sur lequel elle écoute
	- Une liste de pairs autorisés
- Un pair est identifié par 
	- sa clé publique
	- et est autorisé ensuite par son adresse ip.
- Que se passe t'il si WireGuard reçoit un paquet chiffré ?
	- Le paquet va être
		- déchiffré
		- authentifié
	- Il sera ensuite accepté seulement si l'IP source se trouve dans la table et correspond à la clé publique utilisé pour déchiffré le paquet.
	
### LA DISTRIBUTION DES CLÉS

- Quels sont les étapes liés aux clés ?
	- Génération des clés
	- Configuration des pairs
	- Établissement de la connexion
	- Échange de clés
	- Chiffrement des données
- Comment s'exécute l'étape de génération des clés ?
	- Chaque pair (dispositif) génère une paire de clés, composée d'une clé privée et d'une clé publique.
	- La clé privée est secrète et doit rester sur le dispositif qui l'a générée, tandis que la clé publique peut être partagée avec d'autres dispositifs.
- Comment s'exécute l'étape de configuration des pairs ?
	- Chaque pair doit être configuré avec la clé publique de l'autre pair et sa propre clé privée. 
	- Dans la configuration de WireGuard, cela se fait en ajoutant des sections `[Peer]` pour chaque pair, avec les clés publiques et les adresses IP de chaque pair.
- Comment s'exécute l'étape d'établissement de la connexion ?
	- Lorsqu'un pair tente d'établir une connexion avec un autre pair, il envoie un message d'initiation chiffré avec la clé publique de ce pair.
	- Le message d'initiation contient également la clé publique de l'expéditeur, de sorte que le destinataire puisse authentifier l'expéditeur et établir la connexion.
- Comment s'exécute l'étape d'échange de clés ?
	- Une fois la connexion établie, les pairs utilisent le protocole de WireGuard pour échanger leurs clés publiques et établir une connexion sécurisée.
	- WireGuard utilise le protocole Noise, qui est un protocole cryptographique de nouvelle génération, pour gérer l'échange de clés et la création de sessions chiffrées.
- Comment s'exécute l'étape de chiffrements des données ?
	- Une fois l'échange de clés terminé, les pairs utilisent leurs clés privées et les clés publiques de l'autre pair pour chiffrer et déchiffrer les données transmises entre eux. WireGuard utilise des algorithmes de chiffrement modernes et sécurisés, tels que ChaCha20 pour le chiffrement des données et Poly1305 pour l'authentification des messages.

### ENDPOINTS & ROAMING

- Qu'est-ce qu'un endpoint ?
	- L'endpoint dans WireGuard fait référence à l'adresse IP publique et au port d'un pair auquel un autre pair doit envoyer des paquets chiffrés.
- À quel moment l'endpoint est nécessaire (POV : Client) ?
	- Lorsqu'un client (ou un pair) se connecte à un serveur (ou à un autre pair) via WireGuard, il doit connaître l'endpoint du serveur pour pouvoir envoyer des paquets chiffrés à ce serveur.
- À quel moment l'endpoint est nécessaire (POV : Serveur) ?
	- De même, le serveur doit également connaître l'endpoint du client pour envoyer des paquets chiffrés en retour.
- Où est défini l'endpoint ?
	- L'endpoint est défini dans la configuration de chaque pair et est essentiel pour établir la connexion.
- Qu'est-ce que le roaming ?
	- Le roaming est une fonctionnalité de WireGuard qui permet aux pairs de maintenir une connexion sécurisée, même lorsqu'ils changent d'adresse IP ou de réseau. Cela est particulièrement utile pour les clients mobiles, qui peuvent passer d'un réseau Wi-Fi à un réseau mobile ou changer d'adresse IP en raison de l'attribution dynamique des adresses par DHCP.
- Comment fonctionne le roaming dans WireGuard ?
	1. Échange de clés publiques et configuration des endpoints
		- Chaque pair WireGuard possède une clé publique et une clé privée. Lors de la configuration de la connexion, les pairs échangent leurs clés publiques et définissent les endpoints (adresse IP publique et port) de l'autre pair. Les informations d'endpoint sont stockées dans la configuration de chaque pair.
	2.  Routage des paquets chiffrés via les endpoints
		- Lorsqu'un client envoie des paquets chiffrés à un serveur, il utilise l'endpoint du serveur pour acheminer les paquets. De même, le serveur utilise l'endpoint du client pour renvoyer des paquets chiffrés.
	3.  Changement d'adresse IP et impact sur l'endpoint
		- Si un client change d'adresse IP ou de réseau, par exemple en passant d'un réseau Wi-Fi à un réseau mobile, son endpoint (adresse IP publique et port) change également. Cependant, étant donné que le serveur n'est pas informé de ce changement, il continuera d'envoyer des paquets à l'ancien endpoint du client.
	4.  Mise à jour automatique de l'endpoint du client par le serveur
		- Lorsque le client envoie un paquet chiffré valide au serveur à partir de sa nouvelle adresse IP, le serveur reconnaît la clé publique du client et met à jour l'endpoint du client dans sa configuration avec la nouvelle adresse IP et le nouveau port. Le serveur n'a pas besoin de renégocier la clé ou de réauthentifier le client, car la clé publique du client est toujours valide.
	5.  Maintien de la connexion VPN sans interruption
		- Le serveur commence à envoyer des paquets chiffrés à la nouvelle adresse IP du client, ce qui permet de maintenir la connexion sans interruption.
- Comment WireGuard gère-t-il le roaming lorsqu'un pair se déplace entre différents réseaux ou change d'adresse IP externe?
	- WireGuard se base sur l'adresse IP externe source du paquet chiffré pour identifier le pair distant, ce qui permet aux pairs de se déplacer librement entre différentes adresses IP externes sans avoir à renégocier ou rétablir la connexion VPN.
- Qu'est-ce qui identifie de manière unique un pair dans WireGuard?
	- Une clé publique identifie de manière unique un pair dans WireGuard.
- Qu'est-ce qui permet le roaming dans WireGuard?
	- Le roaming est possible car WireGuard utilise l'adresse IP externe source du paquet chiffré pour identifier le pair distant, plutôt que de compter sur une configuration d'adresse IP statique.
- Comment le roaming dans WireGuard est-il similaire à Mosh?
	- Mosh est un autre protocole qui permet la mobilité des connexions, en particulier pour les sessions SSH sur les réseaux instables ou en cas de changement d'adresse IP. WireGuard et Mosh permettent tous deux la mobilité des connexions sans interruption.
- Quel est l'avantage du roaming dans WireGuard pour les utilisateurs du réseau VPN?
	- Le roaming dans WireGuard permet une expérience de mobilité transparente pour les utilisateurs du réseau VPN, car ils peuvent se déplacer entre différents réseaux ou changer d'adresse IP externe sans perdre leur connexion VPN.
- Les éléments internes et externes impliqués dans le roaming WireGuard sont les suivants :
	- Internes
		- Clés publiques et privées
		- Les configurations d'endpoint stockées par chaque pair
		- Le processus de mise à jour automatique de l'endpoint lorsqu'un paquet chiffré valide est reçu d'une nouvelle adresse IP
	- Externes
		- Les réseaux et les adresses IP que les clients utilisent pour se connecter, qui peuvent changer en raison de facteurs tels que le passage entre les réseaux Wi-Fi et mobiles ou l'attribution dynamique des adresses IP par DHCP.
- Qu'est-ce qu'une IP adresse externe ?
	- Un *endpoint*
	- En effet, chaque membre de la table de routage peut éventuellement pré-spécifié une adresse connue externe et un port UDP.
- Comment WireGuard gère-t-il les adresses IP externes les plus récentes et les ports UDP pour les pairs lors du roaming ?
	- WireGuard met à jour les informations d'endpoint pour refléter les changements d'adresse IP externe et de port UDP lorsqu'un pair se déplace entre différents réseaux.
- Pourquoi le roaming de WireGuard réduit-il la nécessité pour les dispositifs NAT de maintenir des sessions ouvertes ?
	- WireGuard gère le roaming en mettant à jour les endpoints en fonction de l'adresse IP source externe. Cela permet aux communications entre les pairs de ne pas être interrompues lorsqu'ils changent d'adresse IP, réduisant ainsi la nécessité pour les dispositifs NAT de maintenir des sessions ouvertes.
- Quel est le rôle des dispositifs de traduction d'adresse réseau (NAT) dans un contexte de roaming ?
	- Dans un contexte de roaming, le NAT doit généralement garder les sessions ouvertes pour que les communications entre les pairs ne soient pas interrompues lorsqu'ils changent d'adresse IP. Cependant, avec WireGuard, cette exigence est réduite grâce à sa gestion du roaming.
- Comment WireGuard gère-t-il les fichiers de configuration pour les interfaces côté serveur et client ?
	- Chaque interface WireGuard a son propre fichier de configuration. WireGuard ne distingue pas les rôles "client" et "serveur", chaque nœud est considéré comme un "pair".
- Quelle est la différence entre le champ "Endpoint" et le champ "AllowedIPs" pour la section [Peer] dans un fichier de configuration WireGuard ?
	- Le champ "Endpoint" indique l'adresse IP réelle et le port du pair distant, tandis que le champ "AllowedIPs" spécifie les adresses IP que l'hôte local doit acheminer vers le pair distant via le tunnel WireGuard.
- Comment fonctionne le routage de paquets entrants et sortants dans le tunnel WireGuard avec l'adresse IP virtuelle spécifiée dans la section [Interface] du fichier de configuration ?
	- L'adresse IP virtuelle spécifiée dans la section [Interface] affecte le routage des paquets entrants et sortants du tunnel WireGuard. Cette adresse IP ne doit pas être une adresse IP réelle routable en dehors du VPN.
- Quel est l'impact de la spécification d'un masque de réseau pour le paramètre "Address" dans un fichier de configuration WireGuard ?
	- La spécification d'un masque de réseau pour le paramètre "Address" affecte les décisions de routage prises par l'hôte local concernant le trafic à envoyer dans le tunnel. Cela peut être redondant ou contradictoire avec le paramètre "AllowedIPs". Il est généralement préférable d'omettre le masque de réseau dans le paramètre "Address" et d'utiliser uniquement les paramètres "AllowedIPs" pour chaque pair pour contrôler le routage.
- Quelle est l'utilité du champ "Endpoint" dans le fichier de configuration WireGuard ?
	- Le champ "Endpoint" est nécessaire pour indiquer à l'hôte local comment se connecter au pair distant afin d'établir un tunnel WireGuard. Il n'est nécessaire de définir un "Endpoint" que d'un côté du tunnel WireGuard, mais il peut être défini des deux côtés si les deux pairs ont une adresse IP statique.
- Comment fonctionne le paramètre "PersistentKeepalive" dans un fichier de configuration WireGuard ?
	- Le paramètre "PersistentKeepalive" indique à un pair de se connecter activement à l'autre pair toutes les N secondes, où N est la valeur spécifiée. Cela permet d'établir et de maintenir un tunnel WireGuard, même si l'un des pairs possède une adresse IP publique dynamique.

> [!summary]
> -   Endpoint : adresse IP publique et port d'un pair pour l'envoi de paquets chiffrés
> -   Endpoint nécessaire pour les clients et serveurs pour établir la connexion
> -   Endpoint défini dans la configuration de chaque pair
> -   Roaming : maintient d'une connexion sécurisée lors de changement d'adresse IP ou de réseau
> -   Roaming dans WireGuard : échange de clés, routage via endpoints, mise à jour automatique d'endpoint
> -   WireGuard identifie les pairs par clé publique et adresse IP source externe pour gérer le roaming
> -   Roaming similaire à Mosh : mobilité des connexions sans interruption
> -   Avantage du roaming : expérience transparente pour les utilisateurs de VPN
> -   Éléments internes et externes du roaming : clés, configurations d'endpoint, mise à jour automatique, réseaux et adresses IP
> -   WireGuard met à jour les endpoints lors du roaming, réduisant la nécessité de sessions NAT ouvertes
> -   WireGuard utilise des fichiers de configuration pour chaque interface sans distinction entre client et serveur
> -   Différence entre Endpoint et AllowedIPs : adresse IP réelle et port vs adresses IP à acheminer via le tunnel
> -   Routage de paquets entrants et sortants avec l'adresse IP virtuelle spécifiée dans [Interface]
> -   Impact du masque de réseau pour "Address" : affecte les décisions de routage, préférable d'utiliser AllowedIPs
> -   Utilité du champ "Endpoint" : indiquer comment se connecter au pair distant
> -   Paramètre "PersistentKeepalive" : connexion active toutes les N secondes pour établir et maintenir un tunnel

#### EXEMPLE DU ROAMING

Alice utilise son smartphone pour se connecter à un serveur VPN WireGuard. Son smartphone a une clé privée `smartphone_private_key` et une clé publique `smartphone_public_key`. Le serveur VPN a une clé privée `server_private_key` et une clé publique `server_public_key`.

Au départ, le smartphone d'Alice utilise une connexion Wi-Fi de son domicile et a une adresse IP publique `192.0.2.10` fournie par son réseau Wi-Fi.

1.  Alice et le serveur VPN échangent leurs clés publiques et configurent leurs endpoints respectifs (adresse IP publique et port). Le serveur VPN a une adresse IP publique fixe `203.0.113.5` et écoute sur le port `51820`.

Configuration WireGuard sur le smartphone d'Alice:

```ini
[Interface]
PrivateKey = smartphone_private_key
Address = 10.200.200.2/24

[Peer]
PublicKey = server_public_key
AllowedIPs = 0.0.0.0/0
Endpoint = 203.0.113.5:51820
```

Configuration WireGuard sur le serveur VPN:

```ini
[Interface] 
PrivateKey = server_private_key 
Address = 10.200.200.1/24  

[Peer]
PublicKey = smartphone_public_key 
AllowedIPs = 10.200.200.2/32
Endpoint = 192.0.2.10:12345
```

2.  Alice envoie des paquets chiffrés au serveur VPN en utilisant l'endpoint du serveur `203.0.113.5:51820`. 
   Le serveur VPN répond en envoyant des paquets chiffrés à l'endpoint d'Alice `192.0.2.10:12345`.
3.  Alice quitte son domicile et se déplace vers un café, où elle se connecte à un nouveau réseau Wi-Fi. 
   Son smartphone obtient une nouvelle adresse IP publique `198.51.100.20` du réseau Wi-Fi du café.
4.  Le smartphone d'Alice continue d'envoyer des paquets chiffrés au serveur VPN. 
   Cependant, maintenant, ces paquets proviennent de la nouvelle adresse IP publique `198.51.100.20`.
5.  Le serveur VPN reçoit un paquet chiffré valide provenant de la nouvelle adresse IP d'Alice (`198.51.100.20`) et reconnaît la clé publique d'Alice. 
   Le serveur met alors à jour l'endpoint d'Alice dans sa configuration avec la nouvelle adresse IP `198.51.100.20` et le nouveau port (par exemple, `23456`).

Configuration WireGuard mise à jour sur le serveur VPN:

```ini
[Interface]
PrivateKey = server_private_key
Address = 10.200.200.1/24

[Peer]
PublicKey = smartphone_public_key 
AllowedIPs = 10.200.200.2/32 
Endpoint = 198.51.100.20:23456
```

6.  Le serveur VPN commence à envoyer des paquets chiffrés à la nouvelle adresse IP d'Alice `198.51.100.20`, maintenant la connexion VPN sans interruption.

Dans ce scénario, le roaming de WireGuard permet à Alice de passer d'un réseau Wi-Fi à un autre sans interrompre

![[Pasted image 20230408212433.png]]

```mermaidjs
sequenceDiagram
    participant Alice as Alice (smartphone)
    participant HomeWiFi as Home Wi-Fi
    participant VPN as VPN Server
    participant CafeWiFi as Café Wi-Fi

    Alice->>HomeWiFi: Connect to Home Wi-Fi
    HomeWiFi->>Alice: Assign IP 192.0.2.10
    Alice->>VPN: Exchange public keys and configure endpoints
    Alice->>VPN: Send encrypted packets (source IP: 192.0.2.10)
    VPN->>Alice: Send encrypted packets (source IP: 203.0.113.5)
    Alice->>CafeWiFi: Connect to Café Wi-Fi
    CafeWiFi->>Alice: Assign IP 198.51.100.20
    Alice->>VPN: Send encrypted packets (source IP: 198.51.100.20)
    VPN->>Alice: Update Alice's endpoint to 198.51.100.20
    VPN->>Alice: Send encrypted packets (source IP: 203.0.113.5)
```

### SEND/RECEIVE FLOW

- ![[Pasted image 20230408215527.png]]
- Quels sont les flux pour recevoir et envoyer un paquet sur l'interface wg0 en utilisant "Configuration 1" dans la conception de roaming de la section 2.1 avec la table de routage cryptokey de la section 2?
	- Lorsqu'un paquet est généré localement (ou transmis) et prêt à être envoyé sur l'interface de sortie wg0 :
		1.  Le paquet en clair atteint l'interface WireGuard, wg0.
		2.  L'adresse IP de destination du paquet, 192.168.87.21, correspond au pair TrMv...WXX0.
		3.  La clé de chiffrement symétrique d'envoi et le compteur de nonce de la session sécurisée associée au pair TrMv...WXX0 sont utilisés pour chiffrer le paquet en clair avec ChaCha20Poly1305.
		4.  Un en-tête contenant divers champs est ajouté au paquet chiffré.
		5.  Cet en-tête et le paquet chiffré sont envoyés sous forme de paquet UDP à l'endpoint Internet UDP/IP associé au pair TrMv...WXX0.
	- En résumé
		1. Atteindre l'interface WireGuard avec un paquet en clair
		2.  Correspondance de l'adresse IP de destination avec un pair
		3.  Chiffrement du paquet en clair à l'aide de ChaCha20Poly1305
		4.  Ajout d'un en-tête aux paquets chiffrés
		5.  Envoi du paquet chiffré via UDP à l'endpoint associé
- Que se passe-t-il lorsqu'un paquet UDP/IP atteint le port UDP 41414 de l'hôte, qui est le port d'écoute UDP de l'interface wg0?
	- Lorsqu'un paquet UDP/IP contenant un en-tête particulier et une charge utile chiffrée est reçu sur le bon port :
		1.  Un paquet UDP/IP contenant un en-tête et une charge utile chiffrée est reçu sur le bon port (dans ce cas, le port 41414).
		2.  WireGuard détermine qu'il est associé à la session sécurisée du pair TrMv...WXX0, vérifie la validité du compteur de messages et tente de l'authentifier et de le déchiffrer.
		3.  Le paquet est authentifié correctement, l'adresse IP source du paquet UDP/IP externe est utilisée pour mettre à jour l'endpoint pour le pair TrMv...WXX0.
		4.  Une fois le paquet déchiffré, l'interface a un paquet en clair qui est vérifié pour correspondre à la table de routage cryptokey.
		5.  Si le paquet en clair n'a pas été supprimé, il est inséré dans la file d'attente de réception de l'interface wg0.
	- En résumé
		1. Réception d'un paquet UDP/IP chiffré sur le bon port
		2.  Authentification et déchiffrement du paquet avec WireGuard
		3.  Mise à jour de l'endpoint pour le pair suite à l'authentification
		4.  Vérification de la correspondance avec la table de routage cryptokey
		5.  Insertion du paquet en clair dans la file d'attente de réception
-  Comment la liste des IP autorisées est-elle utilisée pour les paquets entrants et sortants?
	- La liste des IP autorisées est utilisée pour vérifier l'adresse source des paquets entrants et pour choisir un pair en fonction de l'adresse de destination.
	- Lors de l'envoi d'un paquet, la liste est consultée en fonction de l'adresse IP de destination ; lors de la réception d'un paquet, cette même liste est consultée pour déterminer si l'adresse IP source est autorisée.
	- Cela permet d'appliquer un mappage un à un des adresses IP d'envoi et de réception, garantissant que si un paquet est reçu d'un pair particulier, les réponses à cette IP iront au même pair.

### LA COMPÉTITION

- Qu'est-ce que le protocole IPsec ? (Internet Protocol Security) : 
	- Un ensemble de protocoles de sécurité qui fonctionne au niveau de la couche réseau (Couche 2) pour sécuriser les communications sur les réseaux IP.
- Qu'est-ce que le protocole OpenVPN ?
	- Un protocole VPN open-source largement utilisé qui fonctionne au niveau de la couche application (Couche 7) pour sécuriser les communications sur les réseaux TCP/IP.
- Quel est l'avantage de WireGuard par rapport à IPsec ?
	- WireGuard n'utilise pas deux couches différentes pour l'échange de clé et le transport de données comme le fait IPsec. Ainsi cela diminue la **complexité** de l'implémentation.
	- En effet, après une simple configuration d'une interface virtuel en lui assignant une clé privée et les clés publiques des pairs, le tunnel fonctionne !
- Quel est le problème de WireGuard par rapport à IPsec ?
	- Académiquement c'est pas une bonne manière d'abstraire les choses (mauvaise utilisation des couches). 
	- Cependant, ces problèmes sont rectifiés à l'aide de techniques ingénierique (lol) et cryptographique.
- Quel est le désavantage d'OpenVPN par rapport à WireGuard ?
	- Du fait qu'il est implémenté dans la couche applicative (user space), il n'est pas très performant, puisque les packets sont copiés plusieurs fois entre l'espace kernel et utilisateur.
	- Il faut aussi un daemon de "longue vie".
	- Il n'est pas stateless du point de vue de l'administrateur.
	- Il utilise un protocole complexe et lourd : TLS.

### LAYER 3 VPNS

- Qu'est-ce qu'un layer 3 VPN ?
	- Layer 3 VPN, ou VPRN (réseau privé routé virtuel), utilise la VRF de couche 3 (VPN / routage et transfert virtuels) pour segmenter les tables de routage pour chaque client utilisant le service. Le client se connecte au routeur du fournisseur de services et les deux échangent des routes, qui sont placées dans une table de routage spécifique au client. Le protocole BGP multiprotocole (MP-BGP) est requis dans le cloud pour utiliser le service, ce qui augmente la complexité de la conception et de la mise en œuvre. Les VPN L3 ne sont généralement pas déployés sur les réseaux d’utilité en raison de leur complexité; cependant, un VPN L3 pourrait être utilisé pour router le trafic entre les sites d’entreprise ou de centre de données.

### RÉFÉRENCES

- https://www.youtube.com/watch?v=kxj8GMvnASE