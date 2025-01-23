# Docker


- ### Définition: 

> Docker est un outil qui peut empaqueter une application et ses dépendances dans un conteneur isolé, qui pourra être exécuté sur n'importe quel serveur


## avantages :

- > Un grand avantage de Docker est la possibilité de modéliser chaque conteneur sous la forme d'une image que l'on peut stocker localement ou sur le Docker Hub, endroit public où de nombreuses images sont publiées et mises à jour régulièrement.

- > Un conteneur est moins figé qu'une machine virtuelle en matière de taille de disque et de ressources allouées.

- > Utiliser Docker pour créer et gérer des conteneurs peut simplifier la mise en œuvre de systèmes distribués en permettant à de multiples applications, tâches de fond et autres processus de s'exécuter de façon autonome sur une seule machine physique ou à travers un éventail de machines isolées. 


## installations :

https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository

for ubuntu

https://www.youtube.com/watch?v=geNvWXac2Mg


## Docker commands:

|Commande|Ce qu'elle fait|
|-|-|
|docker ps|Liste les conteneurs qui sont actifs|
|docker run {nom image}|lance la conteneurisation d'une image|
|docker start {container id}|démarre un conteneur arrêté|
|docker stop {container id}|arrête un conteneur lancé|
|docker logs {container id}|permet d'afficher les logs d'un conteneur|
|sudo systemctl stop docker |Arrêt de docker|
|docker container prune|delete all stopped containers|
|exec -it|permet d'éxécuter une commande dans le conteneur|
|docker volume ls|liste les volumes|
|docker ps -q|Lists the IDs of all running containers.|
|docker stop $(docker ps -q)|permet de stopper tous les conteneurs en route|
|docker rm -f $(docker ps -aq)|permet de stopper et de supprimer tous les conteneurs|

## Docker options:

|option|à quoi elle sert|
|-|-|
|-p 8080:80|bind le port de l'image dans docker avec le port précisé dans la commande sur la machine hote|
|-d ou --detache|lance un conteneur sans les logs|
|--rm|permet de spécifier de supprimer le conteneur lorsqu'il sera arrêté|
|-v|permet de déclarer un volume persistant|
|||

- ## mariadb volume container run:

```
sudo docker exec -it silly_gagarin mariadb -uroot -p
```

|sudo docker|exec -it |silly_gagarin| mariadb -uroot -p|
|-|-|-|-|
|Commande docker de base|permet d'éxécuter une commande dans le conteneur|le nom du conteneur|la commande à éxécuter dans le conteneur|

> permet d'ouvrir et de se connecter à mariadb


- ## mariadb connection line example:

```
sudo docker run -v backup-volume:/var/lib/mysql -d -p 3307:80 --env MARIADB_ROOT_PASSWORD=root mariadb:latest  
```

|-v |backup-volume|:/var/lib/mysql|
|-|-|-|
|tag permettant de signaler un volume|nom du volume|répertoire sur la machine qui contient le volume|

> permet de lancer un conteneur en utilisant un volume pour faire persister des données.