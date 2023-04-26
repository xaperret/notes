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
	2.  Instantanés (Snapshots)
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

## LVM2 USAGE

- Pourquoi utilise t'on des LVM ?
	- Car la virtualisation d'espace de stockage massif est mandatoire dans les data centers afin de réduire le system downtime et augmenter la flexibilité
 - Qu'est-ce que Clustered LVM (CLVM)
 - Qu'est-ce que High-Availability LVM (HA-LVM)
 - Qu'est-ce que le Mirroring ?
 - Qu'est-ce qu'un physical volume (LVM terminology) ?
	 - Physical storage, typically hard disk, partition, or something that looks like a disk, e.g. software RAID device
 - Qu'est-ce que le volume group (LVM terminology) ?
	 - A pool of physical volumes presented as one administrative unit
 - Qu'est-ce qu'un logical volume (LVM terminology) ?
	 - An exposed block device (~ equivalent of a disk partition)
	 - May be spanned, striped, mirrored, or a snapshot
 - Quels sont les trois couches du modèle LVM ?
	 - ![[Pasted image 20230424171530.png]]
	 - ![[Pasted image 20230424171547.png]]
 - Qu'est-ce que l'unité de base d'allocation de LVM ?
	 - Extent
 - Qu'est-ce qu'un extent ?
	 - An extent is a contiguous area of storage, represented by 2 numbers: (offset, length)
 - Quels sont les deux types d'extents ?
	 - physical extents (PE)
	 - logical extents (LE)
 - physical volumes are divided into PE
 - volume groups are sets of PE
 - logical volumes are sets of LE
 - PE and LE have the same size
 - PE size displayed in vgdisplay
 - Comment est réalisé le mappage de logical extent à physical extent ?
	 - ![[Pasted image 20230424171839.png]]
- LVM features
	- Les volumes groups resizable online by absorbing new PVs or ejecting existing ones
	- Logical Volume resizable online
	- Logical Volume movable between PVs
	- VGs can be split or merged as long as no LVs span the split • Useful when migrating whole LVs to or from offline storage
	- Atomic snapshots (copy-on-write)
	- Thinly-provisioned LVs (over-commit physical storage)
	- Supports RAID 0, 1, 4, 5, 6, 10
	- High availability (shared-storage cluster with shared PVs between hosts)
- Snapshots
	- A snapshots atomically saves the state of a logical volume • Snapshot performed at the block layer level → filesystem independent • Use Copy-On-Write (COW) • requires a new LV to save “changes” • up to the user to choose the new volume size • size must be enough to store the changes (10% of original’s LV is often recommended) • Allows to create atomic backups • a task impossible to perform on a filesystem that doesn’t support native shapshots, such as ext4
- Snapshots behavior
	- Let A be the original volume and S the snapshot volume of A • S stores the “changes” after the snapshot was performed • changes are not the new data, but A’s data before S • When accessing S (via mount), we see A’s original content, i.e. before S was taken • When accessing A, we see its current content • The atomic state of A prior to S can then be backup’ed • A snapshot’s content can be merged back to restore the state pre-snapshot • however: requires to umount the original volume (A) before applying the merge
- Snapshots use-cases
	- Atomic backup of a logical volume without taking the volume offline • System upgrade (likely to succeed) • snapshot before the upgrade • if everything goes well → remove the snapshot • if upgrade fails → revert (merge) the snapshot • Discardable changes for temporary use • create a snapshot of the system • mount the snapshot (say in /snap) • let user use /snap • when user is finished → discard the snapshot

# CONTAINERS

- Qu'est-ce que l'operating system virtualization ou containerization ?
	- C'est une technologie qui permet au kernel de créer et gérer des instances multiples d'espaces utilisateurs, appelées containers.
- Pourquoi dis-t'on que la containerization fournie de l'isolation ?
	- Car les processus dans un containers voient seulement le contenu du container et les devices qui lui sont assignés.
- Que fournie le Kernel pour limiter l'impact des activités d'un container sur les autres containers ?
	- Il fournie du resource-management.
 - Quel est la différence entre la virtualization de OS et la virtualization de plateforme ?
	 - Les containers partagent le même kernel mais ont des différentes librairies, utilities, root filesystem, view of process tree, networking, etc...
	 - Les machines virtuelles ont des OS invités différents
	 - ![[Pasted image 20230424192443.png]]
- Quel est l'avantage des containers par rapport aux vms ?
	- Moins d'overhead, mais moins d'isolation.
- Qu'est-ce qu'un container ?
	- A container is a set of processes that are isolated from the host system and other containers
- De quel technologies les containers font usage ?
	- Capabilities, provide security
	- Namespaces, provide isolation
	- Control groups, provide limits on resources
	- Seccomp, provide security
- Qu'est-ce que Capabilities ?
	- Capabilities divide superuser’s privileges into small pieces
	- Processes and files can each have capabilities • process capabilities: defines what privileged operations a process can do • file capabilities: what capabilities a process gets when executing the file
- Qu'est-ce que Namespaces ?
	- Namespaces are used to provide isolation
- Qu'est-ce que Control groups (Cgroups) ?
	- Cgroups are used to control resources among groups of processes
	- CPU time, memory, network bandwidth, I/O bandwidth
	- provide fine-grained control over allocating, prioritizing, denying, managing, and monitoring system resources • organized hierarchically (like processes) and child cgroups inherit some of their parents’ attributes
- Cgroups can be: • monitored • denied access to resources • reconfigured dynamically (i.e. at run-time)
- Qu'est-ce que seccomp ?
	- Seccomp is used to restrict the system calls a process makes
- Pourquoi utilisé les containers ?
	- Lightweight, fast, disposable. . . virtual environments
	- Can be used as “light” virtual machines, but with less isolation
	- Can be used to build, ship, deploy, and run applications
- Quels sont les bénéfices de la containerization ?
	- Isolation (security) • Provide a complete isolated OS environment • Allow packaging and isolation of applications with their entire runtime environment
	- Portability • Container packaged with all its dependencies
	- Productivity • Performance: lightweight environment • Consolidation: maximize resource utilization • Continuous integration: development, test, deployment
- Containers vs virtual machines
	- Containers are lightweight compared to traditional VMs → more containers can be run per host than traditional VMs • Unlike containers, VMs require emulation layers → consume more resources and add overhead • Containers share resources with the underlying host machine, with user space and process isolations • Starting a container is much faster2 than starting a VM
- Qeuls sont les limtiations des containers Containers use same kernel as host → imposes strong limitations: ?
	- Limited to running applications compiled for the host’s kernel architecture • Limitation from an hardware (CPU) point of view: can’t run an armhf (ARM) container on top of an amd64 (x86-64) system • Can’t run a Windows container on a Linux system • Limited to the host’s kernel (and its features) • Reliability: higher impact of a crash, especially in kernel area

# LXC

- What is LXC?
	- LXC = Linux Containers • low-level Linux container runtime
- How does it work ?\
	- Run multiple isolated Linux systems on a single host
- Provide ?
	- • Provide OS level virtualization (not an hypervisor!) • provide virtual OS with own CPU, memory, I/O and filesystem
	- Provide a user space API
- Containers share the same kernel as the host kernel!
- What does it use for isolation ?
	- Use kernel-based isolation mechanisms (capabilities, namespaces, cgroups, seccomp)
- How to create different OS containers ?
	- LXC uses templates to create different OS containers
- What are templates ?
	- • Templates = scripts to bootstrap specific OS

# DOCKER OVERVIEW

- What are docker's goals ?
	- Package/ship applications independently of the underlying operating system
	- Make applications deployment reproducible
	- Increase applications’ security
- What Docker provides
	- Isolation
	- Simplicity
	- Lightweight
	- Workflow
	- Community
- What is Docker ?
	- Docker = open-source engine that automates the deployment of applications into containers
	- Platform for developers/sysadmins to develop, ship, and run applications, based on containers
- What does it also do
	- Simplifies and standardizes the creation and management of containers
	- Provides a RESTful API to perform queries and actions
- Docker components
	- Docker Engine (docker client + server)
	- Images
	- Registries
	- Containers
- What is docker engine ?
	- Docker is a client-server application
- • Docker ships with
	- a command line client (docker) and 
	- a RESTful API to interact with dockerd
- Docker clients talk to the docker server (dockerd daemon) which does all the work
- Images
	- Every container is instantiated from an image → encloses a program within the image’s filesystem
	- Hierarchy of images: images have a parent ↔ children relationship
- Images are to containers what classes are to
	- instances in OOP (Object Oriented Programming)
- An image includes: 
	- a full-fledged, isolated root filesystem (e.g. minimal filesystem provided by an Ubuntu distribution)
	- the default program to execute when a container is created from an image
		- this program is also called the entry-point
	- network info (e.g. which ports should be exposed)
- Registries
	- Docker stores images that users build in registries
- • Two types of registries, 
	- public and
	- private
- The docker daemon has an internal registry of downloaded images • it caches them (on the host) to avoid downloading them again
- Image names follow a precise format: `<repository>[:<tag>]` where `<repository> ::= [ /] < base name >]`
- To list images available in the internal registry, execute:
	- `docker images`
 - Image can be manually downloaded via:
	 - `docker pull <image name>
	 - `docker pull <image id>`
 - Containers
	 - Docker helps build and deploy containers inside of which one can package applications and services
 - Containers are launched from
	 - images and contain one or more running processes
 - A container terminates when 
	 - its entry-point process terminates, regardless of the number of other processes still running in the container
 - A container is 
	 - an instance of an image, similar to a process is an instance of a program
 - Images 
	 - = building aspect of docker → immutable (static)
 - Containers 
	 - = running aspect of docker → mutable (dynamic)
 - Docker daemon
	 - Docker daemon = dockerd program
	 - ![[Pasted image 20230424203212.png]]
 - Containers are ran by 
	 - the docker daemon, not the docker client
 - Simplest example
	 - `docker run debian echo " Hello world "`
 - To create a container and launch a bash shell inside it:
	 - `docker run -it debian /bin / bash`
 - Running a container’s program with specific user and group IDs can be done with the argument:
	 - `-u uid : gid`
 - lists all running containers
	 - `docker ps`
	 - `docker ps -a`
 - To re-execute the process (entry point) of a stopped container, or to start a container created via docker create, use:
	 - `docker start`
 - Might be useful to start other processes within a container (e.g. bash to explore or alter the filesystem):
	 - `docker exec <exec args> <container> <cmd> <cmd args>`
- The -d parameter of docker run creates a container running in the background (i.e. detached)
- To output stdout and stderr logs for a given container
	- `docker logs <container>`
- A container can also be stopped from the host’s command line:
	- `docker stop`
- To send a signal to a container
	- `docker kill`
- To show detailed information about a container and its process, execute
	- `docker inspect`
- To remove a stopped container:
	- `docker rm`
- To remove all containers on the host:
	- `docker rm -f $( docker ps -aq)`

## REFERENCES

# DOCKER DATA STORAGE

- Docker images
	- Docker images are root filesystems (rootfs) for containers
- What does it mean ?
	- they do not need a kernel + modules: containers share the host kernel
	- they do not need initialization tools or scripts
	- they should be minimal: only include an application and its dependencies
- What are the characteristics of an image ?
	- immutable (read-only)
	- portable
	- sharable
	- storable
	- updatable
- How are Image composed ?
	- Images are layered
- What does it mean to say that images are layered ?
	- They are made of different stacked layers that can be reused by other images and shared by containers
	- Every image extends a parent image (its first layer)
	- ![[Pasted image 20230425162703.png]]
- How are layers made ?
	- Layers are created from Dockerfile instructions: `RUN, COPY, ADD`
- What is a layer ?
	- A layer is a collection of files and directories
- What are the characteristics of a layer ?
	- immutable
	- represents a delta of the changes from the previous layer
	- is associated and referenced by a hash generated from the layer’s content
- What happens when you download an image ?
	- Each layer is downloaded separately
- What happens when a container is created ?
	- a new writable layer is added on top of the image
	- ![[Pasted image 20230425163349.png]]
- This top layer is:
	- called the container layer
	- initially empty
- Where are all changes made in a running container ?
	- are written to the writable layer
- What do multiple containers running the same image share ?
	- The same immutable underlying layers
	- ![[Pasted image 20230425163519.png]]
- What is the difference between an image and a container ?
	- the top writable layer!
- What happens when a container is deleted ?
	- Only its writable layer is deleted but the underlying immutable image remains!
- How does Image inheritance work ?
	- New images can be created from existing images
- What is a base image ?
	- • Images can also be created from scratch (from an archive)
- How to inspect an image's layers ?
	- `docker inspect`
	- `docker inspect --format "{{json .RootFS.Layers}}" mongo :6`
- Docker storage drivers, which the default is overlay2 is using :
	- Linux’s overlay filesystem\
- What is the Overlay filesystem ?
	- It combines upper and lower directory trees and presents a unified view
	- ![[Pasted image 20230425164305.png]]
- Which layer is writeable ?
	- upper one
- What file/folder is visible when conflict ?
	- file : only files in upper directory
	- folder : union between both folders
- How to create an overlay filesystem ?
	- `mount -t overlay overlay -o lowerdir =/ low1 :/ low2 :/ low3 , upperdir =/ upper , workdir =/ work / merged`
		- In this example the dir order is 
		- `/ upper / low1 / low2 / low3`, meaning upper is writeable and lowN are the image layers
- Rootfs indicates ?
	- Merged directory
- What is the issue with overlay filesystem ?
	- Reading and writing in container’s writable layer is slower than on native filesystem!
- What to use to write lots of data ?
	- Use Docker volumes for write-heavy workloads instead of the container’s writable layer
- Why use volumes to write a lot of data ?
	- Volumes write directly to the host filesystem → better performances than writing to the writable layer!
- Committing changes
	- docker commit commits the current state of a container into an image file
- What's the current state of a container ?
	- all layers + top writable layer
- What's the use of docker commit ?
	- useful when modifying a container by hand and wanting to make these changes permanent
- What is a better solution to docker commit ?
	- Better to use dockerfiles, but commit useful for testing and preparing
- Data sharing
	- Files created inside a container are stored on a writable container layer: • data not persistent when container is deleted • can be difficult to get the data out of the container
- How to share data between multiple containers?
	- bind mount
	- volume mount
- Bind mount
	- • Container can read-write files outside the container’s writable layer
	- • A file or directory on the host machine is mounted into a container
	- • The file or directory is referenced by its full absolute path on the host machine
	- • Efficient, but rely on the host machine’s filesystem having a specific directory structure available (mount point)
- Volume mount
	- • Container can read-write files outside the container’s writable layer
	- • A volume (local, but possibly remote) is mounted into a container
	- Preferred mechanism for persisting data generated by and used by Docker containers
	- • The volume is referenced by its name on the host machine
	- • Volumes are fully managed by Docker
- Volumes vs bind mounts
	- Benefits of volumes over bind mounts:
		- • Volumes manageable via Docker CLI or Docker API • Work on both Linux and Windows containers • Can be stored on remote hosts (e.g. Cloud), supports encrypted contents, etc. • New volumes can have their contents pre-populated by a container
- Volumes vs writing to the container writable layer
	- Volumes are often a better choice than persisting data in a container’s writable layer: 
		- • Better read-write performance • Does not increase the container’s size • Contents exist outside the container’s lifecycle!
- Transfering data to/from a volume
	- How to copy data from: • the local filesystem to a volume? • a volume to the local filesystem?
		- Copy content of the current dir in the local filesystem to the volume mounted in /shared in the container: docker cp . my_container :/ shared /
		- Copy volume’s content (mounted in /shared in the container) to the current directory in the local filesystem: docker cp my_container :/ shared / .

# DOCKERFILES

- What is a dockerfile ?
	- A Dockerfile is a text file containing instructions on how to build an image
- Why a Dockerfile?
	- When existing images don’t satisfy our needs
	- To customize an existing image to our needs
- To build an image
	- `docker build`
- To run & create a container
	- `docker run`
- Dockerfile
	1. Define base image (FROM) 
	2. Set environment variables (ENV) 
	3. Add instructions, e.g. packages to install, etc. (RUN) 
	4. Add files (COPY or ADD) 
	5. Define default command (CMD or ENTRYPOINT)
	6. Indicates ports the container listens to for connections (EXPOSE)

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
- By opposition to CMD, ENTRYPOINT cannot be overriden when starting the container!
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
	- exports a container’s filesystem into a tar archive (to stdout) • archive contains the filesystem only
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

- What if you want to build a container with a specific program that must be generated from source?
	- multi-stage builds!
- Best practices
	- One container should only solve one problem! • Create Dockerfiles that define stateless images • any state should be kept outside of the container (volumes) • Minimize the image size by removing unecessary files, for instance with Debian-like distributions: apt - get clean && rm -rf / var /lib/ apt/ lists / var / cache / apt • Minimize number of layers (= minimize number of steps) • Use .dockerignore to avoid sending all context files/dirs to the Docker daemon

# DOCKER BASIC NETWORKING

- What are the main Docker network drivers ?
	- None
	- Host
	- Bridge
	- (Overlay)
- What is the None network driver ?
	- The none network driver ensure no network interface is available to the container (except for the local loopback interface)
	- Example : `docker run -it --rm --network none ubuntu:22.04`
- What is the Host network driver ?
	- Remove network isolation between container and host
	- All network interfaces from the host are available in the container
	- Example : `docker run -it --rm --network host ubuntu:22.04`
- What is the Bridge network driver ?
	- Allow containers connected to the same bridge network to communicate, while providing isolation from containers which are not connected to it
	- One can create user-defined custom bridge networks
- What is the Default bridge network ?
	- • When Docker daemon is started, a default network is created automatically • Named bridge and exposed via the docker0 interface • Newly-started containers connect to the bridge network unless otherwise specified • Containers conntected to the bridge network can reach each others by ip • The bridge network is legacy and is not recommended for production use • Instead, it’s recommended to create user-defined custom networksA
	- ![[Pasted image 20230426114334.png]]
- User-defined networks
	- Containers connected to the same user-defined network:
		- can reach each other by name or ip • effectively expose all ports to each other
- User-defined networks provide name resolution between containers connected to the same network
- For a port to be accessible to containers or non-Docker hosts on different networks, it must be published with -p
- ![[Pasted image 20230426114524.png]]
- User-defined network vs default bridge network (1/2)
	- User-defined networks provide: • better flexibility and interoperability between containerized applications • name resolution between containers connected to the same network • The bridge network does not provide name resolution between containers!
	- • Containers can be attached/detached from user-defined networks on the fly • to remove a container from the bridge network → must be stopped and recreated with different options • Each user-defined network creates a configurable bridge • configuring the bridge network happens outside of Docker itself, and requires a restart of Docker
# VIRTUALIZATION TECHNOLOGIES AND FRAMEWORKS

- Unikernel
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

- Comment affiché la liste des containers ?
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
- Le système de fichier racine est un overlay sur le container et sur l'hôte.

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

- L'analogie entre ce scénario et les containers Docker est que la couche basse (lower) correspond à l'image Docker en lecture seule, et la couche haute (upper) correspond à la couche de conteneur en lecture/écriture qui stocke les modifications apportées pendant l'exécution du conteneur.
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

Exécutez un container Fedora:26, puis dans celui-ci : 

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

- Le chemin absolu de la couche container writable (upper layer) est donné par la valeur de "UpperDir" dans la section "GraphDriver" de la sortie JSON de la commande `docker inspect`.

#### EN INSPECTANT LE SYSTÈME DE FICHIERS SUR LA MACHINE HÔTE, LISTEZ LE CONTENU COMPLET DE LA COUCHE CONTAINER WRITABLE (INFO: TREE EST TRÈS PRATIQUE POUR VISUALISER LES ARBORESCENCES)

- Utilisez la commande `tree` pour afficher le contenu complet de la couche container writable en exécutant :

`tree /chemin/vers/UpperDir`

- Nous pouvons voir que la couche upper contient les modifications que nous avons fait après l'instanciation du container.

#### SUR LA MACHINE HÔTE, QUEL EST LE CHEMIN ABSOLU DU RÉPERTOIRE CORRESPONDANT AU ROOTFS DU CONTAINER ?

- Le chemin absolu du répertoire correspondant au rootfs du container est donné par la valeur de "MergedDir" dans la section "GraphDriver" de la sortie JSON de la commande `docker inspect`.

### SUR LA MACHINE HÔTE, DÉPLACEZ-VOUS DANS LE RÉPERTOIRE CORRESPONDANT AU ROOTFS DU CONTAINER. A L’INTÉRIEUR DE CELUI-CI, CRÉEZ LE FICHIER HELLO_FROM_THE_OUTSIDE

#### SUITE À L’OPÉRATION CI-DESSUS, QU’OBSERVEZ-VOUS DANS LE CONTAINER LORSQUE VOUS LISTEZ LE CONTENU DU RÉPERTOIRE RACINE ?

- Après avoir créé le fichier `Hello_from_the_outside` dans le répertoire rootfs du container sur la machine hôte, vous devriez voir ce fichier lorsque vous listez le contenu du répertoire racine dans le container.

### PRÉCÉDEMMENT, VOUS AVEZ UTILISÉ LA COMMANDE DOCKER INSPECT POUR DÉTERMINER LES DIFFÉRENTES COUCHES (OVERLAYFS) DU CONTAINER

#### EST-CE QU’IL EST POSSIBLE DE SIMPLEMENT UTILISER LA COMMANDE MOUNT SUR LE SERVEUR POUR OBTENIR LES MÊMES INFORMATIONS ? JUSTIFIEZ VOTRE DÉMARCHE

- Oui, il est possible d'utiliser la commande `mount` pour obtenir des informations sur le système de fichiers overlay utilisé par le container. Cependant, les informations peuvent être formatées différemment et il peut être nécessaire d'analyser la sortie pour extraire les informations pertinentes.
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

Dans ce container : 

- Supprimez les répertoires /opt et /mnt et la commande /usr/bin/uniq 2 / 3
- Avec dd, créez le fichier /home/random de 8500 bytes à partir de /dev/urandom
- Ajouter la ligne ci-dessous à la fin du fichier /etc/motd: `Tagada tsoin tsoin`

Une fois ces opérations réalisées, sortez du container. 

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