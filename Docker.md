---
---

# Docker

Les distributions Linux, OS, et applications dépendent de librairies bien précises. Si les versions ne sont pas bonnes, rien ne fonctionnera.

Les containers sont un moyen de mettre du scotch autour des applications.

Docker est un framework qui permet de déployer des applications.

Docker est une application client serveur.

Une image c'est un système de fichier racine. Contenant tout ce qui est nécessaire pour exécuter une application.

```bash
docker images
```

This command will list the local images, not the public one.

```shell
docker pull debian:buster
```

This command will download the image of debian and the child of this image buster. This will then be stored locally.

A container is the instanciation of an image.

Images uses local library from the system. Meaning they will be smaller.

The docker daemon could be executed locally or remotely. It's executed in `root`, it's dangerous as if the daemon is corrupted, then the whole system is corrupted.
`podman` is not running in `root`.
There is a `docker` rootless, but it's experimental.
`systemd` is a container, it can manage, create container.

## References
