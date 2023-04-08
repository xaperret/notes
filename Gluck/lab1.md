---
date created: Sunday, March 26th 2023, 6:17:15 pm
date modified: Sunday, March 26th 2023, 7:24:41 pm
cards-deck: labo1
---

# 1. CAHIER DE LABORATOIRE DE VIRTUALISATION DES SYSTÈMES : LABO 1

- Merci à Denis et Gustavo

# 2. INTRODUCTION À VIRTUALBOX

## 2.1. HYPERVISEUR VIRTUALBOX

VirtualBox est:: un hyperviseur open source qui permet de créer et de gérer des machines virtuelles sur un système d’exploitation hôte.

VirtualBox est utilisé pour:: créer un environnement isolé et sécurisé dans lequel les utilisateurs peuvent exécuter différents systèmes d’exploitation et applications sans affecter le système hôte.


L’hyperviseur VirtualBox utilise la ==virtualisation matérielle== pour créer une ==couche d’abstraction== entre le matériel physique et les machines virtuelles.

Il utilise également une architecture ==client-serveur== pour permettre ==la gestion à distance des machines virtuelles==.

VirtualBox prend en charge une variété de systèmes d’exploitation invités, tels que Windows, Linux, Mac OS X et Solaris, ainsi que des fonctionnalités avancées telles que la virtualisation par accélération matérielle, la prise en charge de l’USB 2.0 et 3.0, et la possibilité de créer des snapshots pour sauvegarder et restaurer l’état des machines virtuelles.

# 3. MACHINE VIRTUELLE INITIALE

## 3.1. VDI

Lors de la création d’une nouvelle machine virtuelle (VM), le fichier .vdi est un ==fichier de disque dur virtuel== utilisé par VirtualBox pour ==stocker le système d’exploitation, les données== et les ==applications de la machine virtuelle==.

^1679850830064

Le fichier .vdi est créé lorsque:: l’utilisateur configure la machine virtuelle et spécifie la taille et le format du disque dur virtuel.

^1679850830072

Ce fichier .vdi est ensuite utilisé par VirtualBox pour:: émuler un disque dur physique à l’intérieur de la machine virtuelle.

^1679850830080

Le fichier .vdi contient:: tous les fichiers nécessaires au fonctionnement de la machine virtuelle, tels que le système d’exploitation invité, les fichiers de configuration et les données stockées dans le disque dur virtuel.

^1679850830089

Le fichier .vdi peut être copié, déplacé ou sauvegardé comme tout autre fichier.

## 3.2. LORS DE LA CRÉATION D’UN DISQUE DE STOCKAGE VIRTUEL, QUELLE EST LA DIFFÉRENCE ENTRE UN DISQUE ALLOUÉ DYNAMIQUEMENT ET UN DISQUE DE TAILLE FIXE ?

La différence principale entre un disque alloué dynamiquement et un disque de taille fixe réside dans:: la manière dont ils allouent et utilisent l'espace disque.

^1679850830100

Le disque alloué dynamiquement:: s'agrandit progressivement à mesure que la machine virtuelle est utilisée et n'occupe que l'espace physique nécessaire.

^1679850830110

Ainsi, le fichier de disque dur virtuel s'étend:: dynamiquement pour accueillir les nouvelles données, ce qui permet de conserver de l'espace disque physique.

^1679850830119

En revanche, un disque de taille fixe:: pré-alloue l'espace disque lors de la création de la machine virtuelle, réservant et dédiant cet espace à cette machine, même s'il n'est pas utilisé immédiatement.

^1679850830127

## 3.3. LEQUEL DEVRAIT OFFRIR LES MEILLEURES PERFORMANCES ET POURQUOI ?

En termes de performances, le disque de taille fixe est:: généralement meilleur que le disque alloué dynamiquement.

^1679850830136

La raison principale (que statique > dynamique) est:: que VirtualBox n'a pas besoin de demander régulièrement de l'espace supplémentaire au système d'exploitation et la fragmentation du disque est réduite, bien qu'elle reste inévitable.

^1679850830144

Cependant, le choix entre le stockage alloué de manière dynamique et le stockage fixe dépend des besoins spécifiques de chaque utilisateur. Le stockage dynamique est:: plus flexible et permet d'économiser de l'espace disque.

^1679850830152

## 3.4. QUELLES DIFFÉRENCES REMARQUEZ-VOUS ENTRE LE MATÉRIEL (HARDWARE) DÉTECTÉ PAR L’OS GUEST ET L’OS DE LA MACHINE HÔTE (HOST) ?

### 3.4.1. `LSCPU`

Les informations sur le processeur sont:: les mêmes sur la machine hôte et sur la machine virtuelle.

La seule chose qui change est:: le nombre de coeur disponible (ici 4 puisque nous avons choisit 4 coeurs pour la machine virtuelle).

### 3.4.2. `FREE -H`

Ici, on peut voir que le montant de mémoire libre disponible:: diffère entre la machine hôte et la machine virtuelle. La machine virtuelle en a 3, la machine hôte en a 31.

### 3.4.3. `LSBLK`

### 3.4.4. QUE RÉALISE CHAQUE COMMANDE SYSTÈME QUI VOUS A ÉTÉ INDIQUÉE CI-DESSUS ?

  

- `lscpu` :: affiche les informations sur le processeur

- `free -h` :: affiche la mémoire libre

- `lspci` :: affiche les périphériques PCI

- `lsblk` :: affiche les périphériques de stockage

- `df -h` :: affiche les informations sur les systèmes de fichiers

  

### 3.4.5. POUR DÉTERMINER SI UN PÉRIPHÉRIQUE EST PARAVIRTUALISÉ, ÉMULÉ OU EN MODE PASSTHROUGH, VOUS POUVEZ SUIVRE LES ÉTAPES CI-DESSOUS :

#### CONFIGURATION DU SYSTÈME DE VIRTUALISATION

Configuration du système de virtualisation : Vérifiez les paramètres de la machine virtuelle dans le logiciel de virtualisation que vous utilisez (par exemple, VirtualBox, VMware, KVM, etc.).

Paravirtualisé :: Pour les périphériques paravirtualisés, vous verrez généralement un modèle ou un contrôleur spécifique (comme VirtIO pour le stockage et le réseau dans VirtualBox et KVM).

^1679850830161

Émulé :: Les périphériques émulés apparaissent généralement comme des modèles de matériel standard ou courant (par exemple, Intel E1000 pour les cartes réseau).

^1679850830170

Passthrough :: Pour les périphériques en mode passthrough, vous verrez généralement une option pour passer directement le matériel physique à la machine virtuelle, comme "PCI Passthrough" ou "USB Passthrough".

^1679850830179

#### PILOTES

Pilotes dans l'OS invité (guest) : Vérifiez les pilotes installés pour les périphériques concernés dans l'OS invité.

Paravirtualisé :: Les pilotes paravirtualisés ont généralement des noms spécifiques liés à la paravirtualisation (comme "virtio-pci" pour le stockage et "virtio_net" pour le réseau).

^1679850830188

Émulé :: Les pilotes pour les périphériques émulés apparaissent généralement comme des pilotes standard pour le matériel émulé (par exemple, "e1000" pour les cartes réseau Intel E1000).

^1679850830197

Passthrough :: Pour les périphériques en mode passthrough, les pilotes installés dans l'OS invité seront les mêmes que ceux utilisés sur le matériel physique.

^1679850830210

### 3.4.6. PARMIS LES PÉRIPHÉRIQUES LISTÉS AVEC LSPCI LESQUELS SONT DE TYPE ÉMULÉ, PARAVIRTUALISÉ ET PASSTHROUGH SELON VOUS ?

D'après la sortie de lspci -k, voici une description des périphériques et de leur type (émulé, paravirtualisé ou passthrough) :

1. Émulés:
- Contrôleur IDE (00:01.1) : Utilise le pilote ata_piix. C'est un contrôleur émulé Intel PIIX4.
- Contrôleur VGA (00:02.0) : Utilise le pilote vmwgfx. C'est une carte graphique VMware SVGA II émulée.
- Contrôleur Ethernet (00:03.0) : Utilise le pilote e1000. C'est une carte réseau émulée Intel PRO/1000 MT Desktop.
- Contrôleur audio (00:05.0) : Utilise le pilote snd_intel8x0. C'est un contrôleur audio AC'97 émulé.
- Contrôleur USB (00:06.0) : Utilise le pilote ohci-pci. C'est un contrôleur USB émulé Apple KeyLargo/Intrepid.
- Contrôleur SATA (00:0d.0) : Utilise le pilote ahci. C'est un contrôleur SATA émulé Intel ICH8M/ICH8M-E.

2. Paravirtualisés:

- Périphérique système (00:04.0) : Utilise le pilote vboxguest. Il s'agit des services invités ==VirtualBox paravirtualisés==.
^1679850830219

3. Passthrough:

- Aucun périphérique n'est configuré en mode passthrough dans cette sortie. Les périphériques en mode passthrough apparaîtraient généralement comme:: des périphériques matériels spécifiques, et non des périphériques émulés ou paravirtualisés.
^1679850830227

La classification ci-dessus est basée sur les pilotes utilisés et les modèles de matériel rapportés par la commande lspci -k. Les périphériques émulés utilisent des ==pilotes et des modèles de matériel standard==, tandis que les périphériques paravirtualisés utilisent ==des pilotes spécifiques liés à la paravirtualisation==. Aucun périphérique en mode passthrough n'est présent dans la sortie fournie.

^1679850830235

#### 3.4.6.1. POUR SAVOIR SI UN PÉRIPHÉRIQUE EST PARAVIRTUALISÉ, DE MANIÈRE GÉNÉRALE ON PEUT VÉRIFIER LES ÉLÉMENTS SUIVANTS

1. Documentation du périphérique :: Consultez la documentation du périphérique ou du système de virtualisation pour savoir si le périphérique prend en charge la paravirtualisation.
^1679850830246

2. Configuration du système de virtualisation :: Vérifiez la configuration de la machine virtuelle (VM) pour voir si le périphérique utilise un modèle spécifique à la paravirtualisation. Par exemple, dans VirtualBox, vous pouvez vérifier la configuration des périphériques de stockage, audio et réseau pour voir s'ils utilisent un modèle paravirtualisé, comme VirtIO pour le stockage ou le réseau.
^1679850830255

3. Pilotes dans l'OS invité (guest) :: Dans le système d'exploitation invité, vérifiez si les pilotes installés pour le périphérique sont spécifiques à la paravirtualisation. Ces pilotes sont généralement fournis par le système de virtualisation et optimisés pour fonctionner dans un environnement virtualisé.
^1679850830263

4. Performance du périphérique :: Les périphériques paravirtualisés ont généralement de meilleures performances que les périphériques émulés. Si vous constatez que le périphérique fonctionne avec des performances proches de celles d'un matériel natif, cela peut être un indicateur que le périphérique est paravirtualisé.
^1679850830271

  

## 3.5. DANS LES PARAMÈTRES DE VOTRE VM, PARMIS LES PÉRIPHÉRIQUES SUPPORTÉS :

  

```bash

xavier@xavier-VirtualBox:~/Desktop$ lspci -k

00:00.0 Host bridge: Intel Corporation 440FX - 82441FX PMC [Natoma] (rev 02)

00:01.0 ISA bridge: Intel Corporation 82371SB PIIX3 ISA [Natoma/Triton II]

00:01.1 IDE interface: Intel Corporation 82371AB/EB/MB PIIX4 IDE (rev 01)

Kernel driver in use: ata_piix

Kernel modules: pata_acpi

00:02.0 VGA compatible controller: VMware SVGA II Adapter

Subsystem: VMware SVGA II Adapter

Kernel driver in use: vmwgfx

Kernel modules: vmwgfx

00:03.0 Ethernet controller: Intel Corporation 82540EM Gigabit Ethernet Controller (rev 02)

Subsystem: Intel Corporation PRO/1000 MT Desktop Adapter

Kernel driver in use: e1000

Kernel modules: e1000

00:04.0 System peripheral: InnoTek Systemberatung GmbH VirtualBox Guest Service

Kernel driver in use: vboxguest

Kernel modules: vboxguest

00:05.0 Multimedia audio controller: Intel Corporation 82801AA AC'97 Audio Controller (rev 01)

Subsystem: Dell 82801AA AC'97 Audio Controller

Kernel driver in use: snd_intel8x0

Kernel modules: snd_intel8x0

00:06.0 USB controller: Apple Inc. KeyLargo/Intrepid USB

Kernel driver in use: ohci-pci

00:07.0 Bridge: Intel Corporation 82371AB/EB/MB PIIX4 ACPI (rev 08)

Kernel driver in use: piix4_smbus

Kernel modules: i2c_piix4

00:0d.0 SATA controller: Intel Corporation 82801HM/HEM (ICH8M/ICH8M-E) SATA Controller [AHCI mode] (rev 02)

Kernel driver in use: ahci

Kernel modules: ahci

```

  

### 3.5.1. QUELS PÉRIPHÉRIQUES DE STOCKAGE SONT PARAVIRTUALISÉS ?

Aucun des contrôleurs de stockage (IDE et SATA) n'est paravirtualisé dans cette configuration. Les contrôleurs de stockage paravirtualisés utiliseraient généralement le pilote ::VirtIO (virtio_blk ou virtio_scsi) ou un pilote similaire spécifique à la paravirtualisation.

^1679850830280

### 3.5.2. QUELS PÉRIPHÉRIQUES AUDIO SONT PARAVIRTUALISÉS ?

Le contrôleur audio AC'97 (00:05.0) est émulé et non paravirtualisé. Un périphérique audio paravirtualisé utiliserait généralement le pilote :: snd_virtio ou un pilote similaire spécifique à la paravirtualisation.

^1679850830291

### 3.5.3. QUELS PÉRIPHÉRIQUES RÉSEAU SONT PARAVIRTUALISÉS ?

La carte réseau Intel PRO/1000 MT Desktop (00:03.0) est émulée et non paravirtualisée. Un périphérique réseau paravirtualisé utiliserait généralement le pilote :: virtio_net ou un pilote similaire spécifique à la paravirtualisation.

^1679850830300

## 3.6. AU NIVEAU DE LA STRUCTURE SUR DISQUE D’UNE VM :

### 3.6.1. OÙ SE TROUVENT LES FICHIERS LIÉS À VOTRE VM ? ENUMÉREZ CHAQUE FICHIER ET DÉCRIVEZ PRÉCISÉMENT LE RÔLE DE CHACUN DE CES FICHIERS.

Fichier .vbox :: Il s'agit du fichier de configuration de la machine virtuelle, qui contient les paramètres de la VM, tels que la quantité de mémoire allouée, les périphériques de stockage et les interfaces réseau. Le fichier .vbox est un fichier XML lisible par l'homme et est spécifique à chaque VM.

^1679850830310

Fichier .vbox-prev :: Il s'agit d'une sauvegarde du fichier .vbox précédent. En cas de problème avec le fichier .vbox actuel, vous pouvez restaurer les paramètres de la VM à partir de ce fichier.

^1679850830321

Fichiers .vdi (Virtual Disk Image) :: Ce sont les fichiers d'image disque qui contiennent le système d'exploitation et les données de la machine virtuelle. Chaque disque dur virtuel utilisé par la VM est représenté par un fichier .vdi distinct. La taille de ces fichiers dépend du disque virtuel et de la façon dont il est configuré (taille fixe ou allouée dynamiquement).

^1679850830330

Fichiers .vmdk (Virtual Machine Disk) :: Ce sont des fichiers d'image disque alternatifs utilisés par certaines VM. Bien que .vdi soit le format natif pour VirtualBox, il prend également en charge d'autres formats de disque, tels que .vmdk, qui est le format de disque natif pour VMware.

^1679850830339

Fichiers .sav (Saved State) :: Ces fichiers contiennent l'état de la machine virtuelle lorsqu'elle est mise en pause ou sauvegardée. Ils permettent de restaurer la VM à l'état exact où elle se trouvait lorsque l'état a été enregistré.

^1679850830348

Fichiers .log et .log.X (Log Files) :: Ce sont des fichiers journaux qui contiennent des informations sur l'exécution de la machine virtuelle et des erreurs éventuelles. Les fichiers .log sont utiles pour le dépannage en cas de problèmes avec la VM. Les fichiers .log.X sont des anciens fichiers journaux archivés.

^1679850830356

Ces fichiers sont les principaux fichiers liés à une VM dans VirtualBox. Vous pouvez également trouver d'autres fichiers temporaires ou de sauvegarde, tels que des snapshots ou des fichiers de vidage, selon la configuration de votre VM.

# 4. GUEST ADDITIONS

Les Guest Additions sont :: un ensemble de pilotes et de logiciels qui permettent une meilleure intégration entre l’hôte et l’invité dans une machine virtuelle.

^1679850830364

Ils sont conçus pour :: améliorer les performances et la convivialité de la machine virtuelle, ainsi que pour fournir des fonctionnalités supplémentaires qui ne sont pas disponibles par défaut dans l’invité.

^1679850830372

Les Guest Additions comprennent :: des pilotes de périphériques tels que le pilote de carte graphique, le pilote réseau et le pilote audio, qui permettent une communication plus rapide et plus efficace entre l’hôte et l’invité.

^1679850830381

Ils incluent également des outils :: tels que le partage de fichiers et le glisser-déposer entre l’hôte et l’invité, ce qui permet de transférer facilement des fichiers et des données entre les deux systèmes.

^1679850830394

## 4.1. MODULES HÔTE

Les commandes lsmod puis modinfo sont utiles dans cette partie.

### 4.1.1. VBOXDRV

Vboxdrv est :: un module de noyau Linux qui permet à VirtualBox d’accéder aux fonctionnalités matérielles de l’hôte.

^1679850830403

Il permet également de :: créer des interfaces de communication entre le système hôte et les machines virtuelles.

^1679850830415

### 4.1.2. VBOXNETADP

vboxnetadp est :: un module de pilote réseau utilisé par VirtualBox pour permettre aux machines virtuelles d’accéder aux réseaux externes.

^1679850830426

Il crée :: une interface réseau virtuelle sur l’hôte et permet à VirtualBox de communiquer avec cette interface pour transmettre des données réseau entre l’hôte et les machines virtuelles.

^1679850830436

En d’autres termes, vboxnetadp est responsable de la communication entre les machines virtuelles et le réseau externe auquel l’hôte est connecté.

### 4.1.3. VBOXNETFLT

Vboxnetflt est :: un pilote de filtre de réseau pour VirtualBox qui permet de filtrer les paquets de données en transit entre les machines virtuelles et les hôtes.

^1679850830444

Le rôle de ce pilote est :: d’assurer une communication sécurisée entre les machines virtuelles et le réseau extérieur, en permettant notamment la configuration de règles de filtrage pour les différents types de paquets de données.

^1679850830452

Ce pilote est installé lors de:: l’installation de VirtualBox et est utilisé automatiquement lorsque vous créez des machines virtuelles avec des cartes réseau virtuelles.

^1679850830463

## 4.2. MODULE GUEST

### 4.2.1. VBOXGUEST

Le module vboxguest est:: un module de noyau qui est installé dans le système d’exploitation invité (guest) lorsqu’une machine virtuelle est créée avec VirtualBox.

^1679850830473

Ce module a pour rôle de ::fournir un certain nombre de fonctionnalités et de services spécifiques pour le système d’exploitation invité.

^1679850830482

Plus précisément, le module vboxguest permet ::une communication efficace et sûre entre le système d’exploitation hôte (host) et le système d’exploitation invité.

^1679850830494

Il fournit également des pilotes de ::périphériques pour les disques virtuels, les cartes réseau virtuelles et d’autres périphériques émulés dans la machine virtuelle.

^1679850830504

Le module vboxguest assure également ::une synchronisation des horloges entre le système d’exploitation hôte et le système d’exploitation invité pour assurer la cohérence des horloges entre les deux systèmes.

^1679850830514

Enfin, le module vboxguest permet de fournir:: une interface de communication entre les outils VirtualBox et le système d’exploitation invité pour effectuer des opérations telles que la capture d’écran, le partage de fichiers et l’intégration du presse-papiers entre l’hôte et l’invité.

^1679850830523

## 4.3. QUE SE PASSE-T-IL LORSQUE VOUS MAXIMISEZ OU CHANGEZ LA TAILLE DE LA FENÊTRE DE VOTRE VM ?

Cela:: ne change pas la résolution, il y a un fond noir autour de l'image de la vm.

^1679850830533

## 4.4. QU’EN PENSEZ-VOUS EN TERME D’USABILITÉ ?

Cela:: n'est pas du tout pratique.

^1679850830542

## 4.5. EST-IL POSSIBLE DE CHANGER LA RÉSOLUTION DE L’AFFICHAGE DEPUIS L’INTERFACE DE VIRTUALBOX (VIEW → VIRTUAL SCREEN) ? COMMENT EST-IL ALORS POSSIBLE DE CHANGER LA RÉSOLUTION ?

Non,:: il faut le faire depuis l'image du guest.

^1679850830550

## 4.6. OBSERVEZ LES MODULES CHARGÉS DANS LE NOYAU DE VOTRE MACHINE HÔTE (HOST) AVEC LA COMMANDE LSMOD.

### 4.7. QUELS SONT LES MODULES APPARTENANT À VIRTUALBOX ET QUEL EST LE RÔLE DE CHACUN D’ENTRE-EUX ?

Dans la sortie de lsmod, voici les modules liés à VirtualBox :

1. vboxnetadp :: Ce module est responsable de la création et de la gestion des adaptateurs réseau hôte (Host-Only) pour VirtualBox. Les adaptateurs réseau hôte permettent la communication entre la machine hôte et les machines virtuelles sans avoir besoin d'accéder au réseau externe.
^1679850830559
2. vboxnetflt :: Ce module est responsable de la fonctionnalité de filtrage du trafic réseau pour les adaptateurs de type "NAT" et "Bridged" dans VirtualBox. Il permet d'intercepter et de traiter le trafic réseau entre la machine hôte et les machines virtuelles, améliorant ainsi la performance et la sécurité du réseau.
^1679850830568
3. vboxdrv :: Il s'agit du module de base de VirtualBox qui fournit les fonctions de virtualisation nécessaires pour exécuter des machines virtuelles. Il interagit avec le matériel et le système d'exploitation de la machine hôte pour fournir une plate-forme de virtualisation stable et performante.
^1679850830578

```bash

➜ ~ lsmod | grep box

vboxnetadp 28672 0

vboxnetflt 32768 0

vboxdrv 643072 3 vboxnetadp,vboxnetflt

processor_thermal_mbox 16384 2 processor_thermal_rfim,processor_thermal_device

➜ ~

```

## 4.8. OBSERVEZ MAINTENANT LES MODULES CHARGÉS DANS VOTRE OS GUEST.

### 4.9. TROUVEZ-VOUS UN OU DES MODULES LIÉS À VIRTUALBOX ? SI OUI, LEQUEL OU LESQUELS ET QUEL EST LEUR RÔLE SELON VOUS ?

Dans la sortie de lsmod, voici les modules liés à VirtualBox :

1. vboxvideo:: Ce module est un pilote vidéo pour VirtualBox qui prend en charge l'accélération graphique 2D et 3D des machines virtuelles. Il s'interface avec le système graphique de l'hôte pour fournir une meilleure expérience utilisateur et des performances graphiques améliorées.
^1679850830588
2. vboxguest:: Ce module est un pilote pour les fonctionnalités Guest Additions de VirtualBox, qui permettent une meilleure intégration entre la machine hôte et les machines virtuelles. Les fonctionnalités incluent le partage de fichiers, le glisser-déposer, le redimensionnement automatique de la fenêtre de la machine virtuelle et la synchronisation du presse-papiers.
^1679850830598

Ces deux modules sont chargés dans le noyau de la machine hôte pour améliorer les performances et la compatibilité des machines virtuelles sous VirtualBox.

Tout à fait logique puisque j'ai déjà ajouté les `Guest Additions`.

## 4.10. SUITE À L’INSTALLATION DES GUEST ADDITIONS, REBOOTEZ VOTRE OS GUEST ET OBSERVEZ À NOUVEAU LES MODULES CHARGÉS DANS VOTRE OS GUEST.

### 4.11. VOYEZ-VOUS UN OU DES MODULES NOYAU SUPPLÉMENTAIRES LIÉS À VIRTUALBOX ? SI OUI, LEQUEL OU LESQUELS ET QUEL EST LEUR RÔLE SELON VOUS ?

On verra l'ajout et l'activation des deux modules précédents.

Notamment, le module vboxvideo a été ajouté et il dépend des modules suivants : drm_ttm_helper, ttm et drm_kms_helper. Vboxvideo est le module vidéo qui permet de modifier la résolution de manière dynamique à partir de l'onglet "View" dans VirtualBox.

## 4.12. ESSAYEZ À NOUVEAU DE MAXIMISER OU CHANGER LA TAILLE DE LA FENÊTRE DE VOTRE VM. QU’OBSERVEZ-VOUS PAR RAPPORT À LA MÊME MANIPULATION PRÉCÉDENT L’INSTALLATION DES GUEST ADDITIONS DANS VOTRE OS GUEST ?

La résolution de la vm:: s'adapte à la taille de la fenêtre de l'hôte.

^1679850830607

## 4.13. EST-IL MAINTENANT POSSIBLE DE CHANGER LA RÉSOLUTION DE L’AFFICHAGE DEPUIS L’INTERFACE DE VIRTUALBOX (VIEW → VIRTUAL SCREEN) ?

Oui, grâce au nouveau pilote.

## 4.14. SELON VOS OBSERVATIONS EMPIRIQUES ET VOTRE COMPRÉHENSION THÉORIQUE, QUE CONSTITUENT LES GUESTADDITIONS EXACTEMENT ?

voir définition dans le point 4.

# 5. RÉPERTOIRE PARTAGÉ

## 5.1. VBOXSF

Le module vboxsf est utilisé pour ::fournir un accès partagé entre le système hôte et le système invité.

^1679850830618

Ce module permet à la machine virtuelle de ::monter les dossiers partagés avec l’hôte et de les utiliser comme n’importe quel autre dossier sur le système invité.

^1679850830627

## 5.2. VOYEZ-VOUS UN NOUVEAU MODULE NOYAU LIÉ À VIRTUALBOX DANS VOTRE OS GUEST ? SI OUI, LEQUEL ET QUEL EST SON RÔLE ?

On peut voir un nouveau module noyau lié à VirtualBox dans votre système d'exploitation invité (guest OS) :: vboxsf.

^1679850830635

Le module vboxsf est le module du système de fichiers partagés de VirtualBox (Shared Folders). Il est responsable de la gestion et du montage des dossiers partagés entre la machine hôte et la machine virtuelle. Ce module permet aux machines virtuelles d'accéder aux fichiers et répertoires de la machine hôte, facilitant ainsi le transfert de données et le partage de ressources entre les deux systèmes.

```bash

xavier@xavier-VirtualBox:~/Desktop$ lsmod | grep vbox

vboxsf 36864 1

vboxvideo 28672 0

drm_vram_helper 24576 1 vboxvideo

drm_ttm_helper 16384 2 drm_vram_helper,vboxvideo

vboxguest 45056 6 vboxsf

drm_kms_helper 311296 3 vmwgfx,drm_vram_helper,vboxvideo

drm 622592 9 vmwgfx,drm_kms_helper,drm_vram_helper,vboxvideo,drm_ttm_helper,ttm

xavier@xavier-VirtualBox:~/Desktop$

```

  

## 5.3. QUEL EST LE TYPE DU SYSTÈME DE FICHIERS UTILISÉ PAR LE RÉPERTOIRE PARTAGÉ ET COMMENT L’AVEZ-VOUS DÉTERMINÉ ?

Le système de fichiers utilisé par le répertoire partagé est:: vboxsf.

^1679850830645

Vous pouvez le déterminer en examinant la sortie de la commande:: `df -T`.

Dans la sortie, vous pouvez voir la colonne "Type" qui indique:: le type de système de fichiers pour chaque montage. Le répertoire partagé /sharedFolder est monté avec le type de système de fichiers vboxsf.

^1679850830654

Le système de fichiers vboxsf est:: spécifique à VirtualBox.

^1679850830663

Le système de fichier vboxsf est utilisé pour:: gérer les dossiers partagés entre la machine hôte et les machines virtuelles.

^1679850830672

Il permet:: un accès transparent aux fichiers de la machine hôte depuis la machine virtuelle.

^1679850830681

Il facilite ::le transfert de données et le partage de ressources entre les deux systèmes.

^1679850830689

```bash

xavier@xavier-VirtualBox:~/Desktop$ df -T

Filesystem Type 1K-blocks Used Available Use% Mounted on

tmpfs tmpfs 307440 1148 306292 1% /run

/dev/sda3 ext4 30267332 12637348 16067156 45% /

tmpfs tmpfs 1537188 0 1537188 0% /dev/shm

tmpfs tmpfs 5120 4 5116 1% /run/lock

/dev/sda2 vfat 524252 6216 518036 2% /boot/efi

Downloads vboxsf 950994596 242828376 708166220 26% /sharedFolder

tmpfs tmpfs 307436 60 307376 1% /run/user/1000

xavier@xavier-VirtualBox:~/Desktop$

```

# 6. CLONE ET SNAPSHOTS

## 6.1. FULL CLONE

Un full clone dans VirtualBox est:: une copie complète d’une machine virtuelle existante.

^1679850830707

Créant ainsi:: une nouvelle machine virtuelle indépendante avec sa propre configuration et son propre stockage.

^1679850830722

Cela signifie que le clone aura une copie:: exacte du disque dur virtuel, de la mémoire et de tous les fichiers de configuration de la machine virtuelle.

^1679850830734

Le fonctionnement d’un full clone se déroule en plusieurs étapes :

- Tout d’abord, VirtualBox crée ==un nouveau disque dur virtuel== pour la machine virtuelle clonée, qui est initialement vide.
^1679850830746

- Ensuite, VirtualBox copie ==tous les fichiers de configuration de la machine virtuelle originale vers la nouvelle machine virtuelle==, en modifiant les paramètres pour qu’ils correspondent à la nouvelle machine virtuelle.
^1679850830754

- Une fois que les fichiers de configuration ont été copiés, VirtualBox copie ==le disque dur virtuel de la machine virtuelle originale vers le nouveau disque dur virtuel de la machine virtuelle clonée==.
^1679850830762

- Enfin, VirtualBox ==ajuste les identifiants uniques de la nouvelle machine virtuelle pour s’assurer qu’elle est entièrement indépendante de la machine virtuelle originale==.
^1679850830770

## 6.2. LINKED CLONE

Un linked clone, ou clone lié en français, est:: une copie d’une machine virtuelle qui partage le même disque dur virtuel que la machine virtuelle originale, appelée machine parent.

^1679850830780

Le disque dur virtuel du clone est:: un instantané du disque dur virtuel de la machine parent, et tout changement effectué dans le disque dur virtuel du clone est stocké dans des fichiers supplémentaires appelés différences.

^1679850830788

Concrètement, lorsqu’un linked clone est créé, VirtualBox crée ::un nouveau disque dur virtuel pour le clone qui ne contient que des liens vers le disque dur virtuel de la machine parent.

^1679850830797

Ainsi, le clone ne stocke que ::les différences par rapport à la machine parent, ce qui permet de gagner de l’espace de stockage.

^1679850830805

Par exemple, si la machine parent utilise 20 Go d’espace disque, un clone lié ne prendrait que quelques centaines de mégaoctets d’espace supplémentaire pour stocker les différences.

Lorsque le clone est exécuté, VirtualBox utilise le disque dur virtuel de la machine parent comme base, puis applique les différences stockées dans le disque dur virtuel du clone. Cela signifie que toutes les modifications apportées à la machine parent après la création du clone seront:: visibles dans le clone.

^1679850830814

## 6.3. QUELS FORMATS D’IMAGES SONT PROPOSÉS SUR LE SITE OSBOXES.ORG ? QUE CONTIENNENT CES DIFFÉRENTS FORMATS D’IMAGES, ET QUELLES SONT LEURS DIFFÉRENCES ?

Sur le site osboxes.org, deux formats d'images sont proposés:

VDI (Virtual Disk Image):: Il s'agit du format d'image disque utilisé par VirtualBox, développé par Oracle.

^1679850830825

Les fichiers VDI contiennent:: une image disque d'un système d'exploitation invité et sont utilisés pour stocker les données de la machine virtuelle.

^1679850830834

Le format VDI est ::portable et peut être utilisé par d'autres logiciels de virtualisation, y compris VMware.

^1679850830843

VMDK (Virtual Machine Disk File):: Il s'agit du format d'image disque propriétaire de VMware.

^1679850830852

Les fichiers VMDK contiennent ::également une image disque d'un système d'exploitation invité et sont utilisés pour stocker les données de la machine virtuelle.

^1679850830859

Bien que VMDK soit principalement utilisé par VMware, d'autres logiciels de virtualisation, comme VirtualBox, peuvent également lire ce format.

Les différences entre ces formats résident principalement dans:: leur compatibilité et leur utilisation avec différents logiciels de virtualisation. VDI est spécifiquement conçu pour VirtualBox, tandis que VMDK est conçu pour les produits VMware. Cependant, les deux formats peuvent être utilisés par plusieurs logiciels de virtualisation, ce qui les rend interchangeables dans une certaine mesure.

^1679850830868

Il existe un troisième format, VHD (Virtual Hard Disk), développé par Microsoft. Ce format est utilisé par les produits de virtualisation Microsoft, tels que Hyper-V, Virtual PC et Virtual Server. VHD est également compatible avec d'autres logiciels de virtualisation, y compris VirtualBox et VMware.

## 6.4. ASSUREZ-VOUS QUE VM2 EST EN COURS D’EXÉCUTION. POUVEZ-VOUS LA CLONER ?

=>::Non.

^1679850830877

## 6.5. SUITE À VOS OBSERVATIONS, EXPLIQUEZ QUEL EST LE FONCTIONNEMENT D’UN FULL CLONE ? CONFIRMEZ VOTRE EXPLICATION EN LISANT LE MANUEL DE VIRTUALBOX

Le fonctionnement d'un full clone consiste à:: créer une copie complète et indépendante d'une machine virtuelle.

^1679850830886

Lors de la création d'un full clone, toutes les images de disque dépendantes sont ::copiées dans le nouveau dossier de la machine virtuelle. Ainsi, le full clone peut fonctionner entièrement sans la machine virtuelle source.

^1679850830896

Cela signifie que le full clone :: ne partage aucune donnée avec la machine virtuelle d'origine, ce qui permet de le déplacer, le copier ou le modifier sans affecter la machine d'origine.

^1679850830905

## 6.6. SUITE À VOS OBSERVATIONS, EXPLIQUEZ QUEL EST LE FONCTIONNEMENT D’UN LINKED CLONE ? CONFIRMEZ VOTRE EXPLICATION EN LISANT LE MANUEL DE VIRTUALBOX.

Le fonctionnement d'un linked clone consiste à :: créer une copie dépendante d'une machine virtuelle existante.

^1679850830923

Contrairement à un full clone, un linked clone:: ne copie pas l'intégralité des images de disque de la machine virtuelle source. Au lieu de cela, il crée de nouvelles images de disque différentielles qui reposent sur les images de disque de la machine source.

^1679850830938

Lorsque vous sélectionnez l'état actuel de la machine virtuelle source comme point de clonage, Oracle VM VirtualBox crée:: un nouveau snapshot. Ce snapshot capture l'état actuel de la machine virtuelle source, et les modifications apportées au linked clone sont enregistrées dans les images de disque différentielles.

^1679850830946

Cela permet de réduire l'espace disque nécessaire pour stocker le linked clone, car il partage une partie de ses données avec la machine virtuelle source.

Toutefois, il est important de noter qu'un linked clone dépend de la machine virtuelle source et de ses images de disque. Si la machine source est supprimée ou modifiée, cela peut affecter le fonctionnement du linked clone.

## 6.7. QUELLES SONT LES TAILLES RESPECTIVES DES DISQUES DE VM2, VM2CLONE1 ET VM2CLONE2 ?

Les tailles respectives des disques de VM2, VM2Clone1 et VM2Clone2 sont les suivantes:

- VM2 : 2,4 Go
- VM2Clone1 (==Full Clone==) : 2,4 Go
^1679850830954
- VM2Clone2 (==Linked Clone==) : 3,3 Mo
^1679850830962

VM2Clone1, étant un ==full clone==, a la même taille que VM2 car il ==s'agit d'une copie complète et indépendante== de la machine virtuelle source. En revanche, VM2Clone2, étant un ==linked clone==, a une taille nettement inférieure car ==il partage une partie de ses données avec la machine virtuelle source et ne stocke que les modifications spécifiques au linked clone dans des images de disque différentielles==.

^1679850830970

