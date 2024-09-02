# exercices

## 7 - tableau serveur web / navigateur web

- Laravel:

|Serveur web|Navigateur web|
|-|-|
|Stocker les données de l'application|Afficher les pages web|
|Router les requêtes HTTP||
|Effectuer le rendu des pages web||
|Exécuter le code métier de l’application||

- Vue:

|Serveur web|Navigateur web|
|-|-|
|Stocker les données de l’application|Afficher les pages web|
|Router les requêtes HTTP|Effectuer le rendu des pages web|
||Exécuter le code métier de l’application|


- Mettre en place la sanitarisation  des urls.
- Mettre en place la validation des inputs.
- Utilisation d'une Api sécurisée.
- limiter les permissions de l'API.


## Liste des enpoints de l'API.


|Route|Méthode|Descritpion|
|-|-|-|
|http://127.0.0.1:8000/api/register|POST|Permet de créer un compte|
|http://127.0.0.1:8000/api/login|POST|Permet de se connecter|
|http://127.0.0.1:8000/api/me|GET|Permet de récupérer ses infos|
|http://127.0.0.1:8000/api/product|GET|Permet d récupérer tous les produits|
|http://127.0.0.1:8000/api/product/2|GET|Permet de récupérer un produit spécifique|
|http://127.0.0.1:8000/api/product/categorie/2|GET|Permet de trier les produit parcatégorie|
|http://127.0.0.1:8000/api/product/add|POST|Permet de créer un produit|
|http://127.0.0.1:8000/api/product/update/3|PATCH|Permet de modifier un produit|
|http://127.0.0.1:8000/api/product/delete/4|DELETE|Permet de supprimer un produit|
|http://127.0.0.1:8000/api/order|GET|Permet de récupérer toute les commandes|
|http://127.0.0.1:8000/api/order/56|GET|Permet de récupérer une commande|
|http://127.0.0.1:8000/api/getOrders/4|GET|Permet de récupérer l'utilisateur d'une commande|
|http://127.0.0.1:8000/api/getProducts/4|GET|Permet de récupérer les produits d'une commande|
|http://127.0.0.1:8000/api/getCustomProducts/9|GET|Permet de récupérer les produits custom d'un commande|
|http://127.0.0.1:8000/api/order|POST|Permet de créer une commande|
|http://127.0.0.1:8000/api/order/65|PUT|Permet de modifier une commande|
|http://127.0.0.1:8000/api/order/4|DELETE|Permet de supprimer une commande|
|http://127.0.0.1:8000/api/customproducts|GET|Permet de récupérer touts le produits custom|
|http://127.0.0.1:8000/api/customproduct/1|GET|Permet de récupérer un produit custom|
|http://127.0.0.1:8000/api/customproduct|POST|crée un produit custom|
|http://127.0.0.1:8000/api/customproduct/3|PUT|Permet de modifier un produit custom|
|http://127.0.0.1:8000/api/customproduct/3|DELETE|Permet de supprimer un produit custom|
|http://127.0.0.1:8000/categories|GET|Permet de récupérer toute les catégories|
|http://127.0.0.1:8000/category/2|GET|Permet de récupérer une catégorie|
|http://127.0.0.1:8000/api/category|POST|Permet de créer une catégorie|
|http://127.0.0.1:8000/api/category/3|PUT|Permet de modifier une catégorie|
|http://127.0.0.1:8000/api/category/4|DELETE|Permet de supprimer une catégorie|