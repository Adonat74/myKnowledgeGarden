# Commandes "avancées"

## GENERAL

|command|result|
|-|-|
|grep |permet de chercher dans des fichiers->https://www.linuxtricks.fr/wiki/grep-afficher-les-lignes-correspondant-a-un-motif-donne |
|find|permet de chercher fichiers ou/et des répertoires->https://www.ionos.fr/digitalguide/serveur/configuration/commande-find-sous-linux|
|git cherry-pick [nom commit]|Cherry-pick permet, lorsqu'on se trouve sur une branche, de sélectionner un commit spécifique d'une autre branche (peu importe son ordre dans l'historique) et de l'appliquer à la branche actuelle, sans avoir besoin de fusionner toute la branche d'origine.|
|scp|Permet de copier un fichier ou dossier depuis un serveur distant directement sur sa machine doc : https://linux.die.net/man/1/scp|
|mysqldump|Permet d'exporter une ou plusieur db et/ou d'exclure des tables doc : https://mysqldump.guru|
|zip <option> <fichier.zip> <folder> |Grâce au package zip on peut compresser des fichiers/dossier au format .zip|
|docker exec -it --user=root |permet de rentre dans le shell du conteneur en étant en root permet de faire pleins d'actions genre touch|



## DRUSH commands

|command|result|
|-|-|
|drush config:export/import|permet d'exporter et d'importer des configs drupal (on peut préciser les chemins)|
|drush wt or watchdog:tail|permet de log les messages drush/drupal en permanence|


