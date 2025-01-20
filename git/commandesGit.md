# GIT


- ## Enlever un repo git créé par accident

    Il suffit d'enlever le dossier " .git " du dossier en question.


- ## Les commandes git

    | commande | A quoi elle sert |
    | - | - |
    | git log  | Afficher la liste des commits du repo |
    | git add [nom de fichier] | Ajoute un instantané du fichier, en préparation pour le suivi de version |
    | git commit -m "message descriptif" | Enregistre des instantanés de fichiers de façon permanente dans l'historique des versions |
    | git pull | Récupère tout l'historique du dépôt nommé et incorpore les modifications |
    | git push origin [branche] | Envoie tous les commits de la branche locale vers GitHub |
    | git push -u origin [branche] | Envoie tous les commits de la branche locale vers GitHub |
    | git status | Permet de voir sur quelle branche on se trouve |
    | git checkout <commit-id> | Permet de revenir à un commit passé |
    | git checkout [branche-name] | Permet de changer de branche et rde revenir à la version actuelle si l'on étais sur un ancien commit |
    | git checkout -b "nom-branche" | Créé une branche et bascule directement dessus |
    | git tag [version ex : 1.1.0] | permet de créer des tags, sortes de versions |
    | git push --tags | Push le tag sur le repo GitHub |
    | git diff | Permet de voir quelles lignes ont été modifié avant et après le dernier commit |
    | git reset HEAD <file> | Permet de retirer un fichier de la "staging area" |
    | git branch  | Permet de lister les branches |
    | git branch "nom_branche" | Permet de créer une nouvelle branche <branche> |
    | git branch -m "nom_branche" | Renomme la branche courante en <branche> |
    | git branch -d "nom_branche" | Permet de supprimer une branche |
    




    > git add : Il faut utiliser "git add -A" pour ajouter tous les fichiers et lors du push mettre à jour les fichier meme pour supprier qui ne sont plus dans le repo local.


- ## Messages de commit

    liste des emojis supportés dans les messages de commits et en markdown : https://gist.github.com/rxaviers/7360908
    

- ## Staging area

    C'est une sorte de mémoire vive qui permet rapidement de sauvegarder son code sans le versionner, si l'on git add plusieur fois sans commit, le code est remplacé et on ne peut plus revenir à une version précédente.


