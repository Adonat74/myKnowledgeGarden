# Docker


- ### Définition: 

> Docker est un outil qui peut empaqueter une application et ses dépendances dans un conteneur isolé, qui pourra être exécuté sur n'importe quel serveur


## avantages :

- > Un grand avantage de Docker est la possibilité de modéliser chaque conteneur sous la forme d'une image que l'on peut stocker localement ou sur le Docker Hub, endroit public où de nombreuses images sont publiées et mises à jour régulièrement.

- > Un conteneur est moins figé qu'une machine virtuelle en matière de taille de disque et de ressources allouées.

- > Utiliser Docker pour créer et gérer des conteneurs peut simplifier la mise en œuvre de systèmes distribués en permettant à de multiples applications, tâches de fond et autres processus de s'exécuter de façon autonome sur une seule machine physique ou à travers un éventail de machines isolées. 


## installations :

https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository


## Docker commands:

|Commande|Ce qu'elle fait|
|-|-|
|docker ps|Liste les conteneurs qui sont actifs|
|docker run {nom image}|lance la conteneurisation d'une image|
|docker start {container id}|démarre un conteneur arrêté|
|docker stop {container id}|arrête un conteneur lancé|
|docker logs {container id}|permet d'afficher les logs d'un conteneur|
|sudo systemctl stop docker |Arrêt de docker|
|||
|||

## Docker options:

|option|à quoi elle sert|
|-|-|
|-p 8080:80|bind le port de l'image dans docker avec le port précisé dans la commande sur la machine hote|
|-d ou --detache|lance un conteneur sans les logs|
|||
|||
|||