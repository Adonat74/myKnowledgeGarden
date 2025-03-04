# réseaux systèmes exercices.

## exo 1


- ### Pour vous, qu’est ce qu’un réseau ?

    plusieurs entitées qui communiquent entre elle grâce à des canaux.

- ### Quel est le lien entre la notion de réseau et Internet?

    Internet est un réseau mondial

- ### Quelle est la différence entre Internet et le Web ? Ou a-t-il été inventé ?

    - Le web est un service qui permet au entitées de naviguer et d'accéder à des informations sur internet

    - Il à été inventé au cern

- ### Quels sont les différents types de réseaux informatiques ? Pour chaque type de réseau, donner un exemple concret.

    - PAN : USB
    - LAN : Ethernet
    - MAN : Wireless Metropolitan Area Network (WMAN)
    - WAN : IP/MPLS (Multiprotocol Label Switching )
    - GAN : Internet
    - VPN : NordVPN



- ### Quels sont les principaux équipements physiques d’un réseau LAN?

    - Ordinateurs
    - Cable Ethernet
    - router
    - switch


- ### Qu’est ce que la commande ping ? A quoi sert-elle ?

    cette ligne de commande permet de vérifier la disponibilité d’un autre ordinateur dans un réseau local associé ou dans un réseau public 
    et de mesurer la latence.

- ### Pour chaque commande lancée, faites défiler 5 lignes et faites CTRL+C. Lisez les statistiques de la commande et expliquez ce qu’il s’est passé.

    - Toute ont envoyés des packets à l'adresse IP
    - 2 sur 3 ont reçus des packets en retour
    - Il y a eu un calcul de perte de packets et de la rapiditée


## exo 3

### 1. Identification des machines et des types de machines

- **PC** : Il s’agit d’un ordinateur personnel qui sera utilisé par M. Silvermoon pour accéder aux fichiers et aux ressources stockées sur le serveur.
- **Serveur de stockage** : C'est un serveur dédié au stockage de données. Il pourrait s’agir d’un serveur physique ou virtuel qui gère les fichiers et les documents importants pour l'entreprise.

### 2. Choix du support de communication

Étant donné que les machines ne sont pas éloignées, vous pouvez choisir parmi les options suivantes :

- **Câble cuivre (Ethernet)** : C'est la solution la plus courante pour des connexions locales. Il est rapide et suffisant pour une petite distance.
- **Fibre optique** : Plus rapide et adapté pour des distances plus longues, mais dans ce cas précis, elle est probablement surdimensionnée.
- **Sans-fil (Wi-Fi)** : Pratique mais moins stable que le câble pour des connexions à courte distance dans des environnements contrôlés.

### 3. Identification des machines au sein du réseau

Les machines sur un réseau sont identifiées par des adresses uniques. Les deux principales sont :

- **Adresse MAC (Media Access Control)** : C'est une adresse physique unique attribuée à chaque interface réseau par le fabricant. Elle est utilisée au niveau de la couche 2 (Data Link Layer) du modèle OSI pour l'identification des appareils sur le réseau local.
- **Adresse IP (Internet Protocol)** : C'est une adresse logique utilisée pour l'identification et la communication entre les appareils sur un réseau. Elle fonctionne au niveau de la couche 3 (Network Layer) du modèle OSI.

### 4. Interfaces réseau

Une **interface réseau** est un composant matériel ou logiciel permettant à un ordinateur ou un autre périphérique de se connecter à un réseau. Les interfaces peuvent être physiques (comme une carte réseau Ethernet) ou virtuelles (comme une interface Wi-Fi ou une interface VPN).

### 5. Adresse MAC et Adresse IP

- **Adresse MAC** : Cette adresse est généralement fixe et assignée par le constructeur de la carte réseau. Par exemple, une adresse MAC pourrait ressembler à `00:1A:2B:3C:4D:5E`.
- **Adresse IP** : Elle est assignée de manière dynamique via DHCP ou manuellement (statique). Dans votre cas, les adresses IP sont :
  - PC : `1.1.1.1`
  - Serveur de stockage : `1.1.1.2`

### 6. Configuration des adresses IP

Pour configurer une adresse IP manuellement sur un PC et un serveur, suivez ces étapes typiques :

- **Sur Windows** :
  1. Allez dans les paramètres réseau.
  2. Accédez aux propriétés de la connexion Ethernet ou Wi-Fi.
  3. Modifiez les paramètres IP pour définir une adresse IP statique (e.g., `1.1.1.1` pour le PC).

- **Sur Linux** :
  1. Modifiez les fichiers de configuration réseau ou utilisez des outils comme `ifconfig` ou `ip`.
  2. Configurez l’adresse IP statique (e.g., `1.1.1.1` pour le PC).

### 7. Test de la configuration et de la communication

- **Ping** : Utilisez la commande `ping` pour vérifier la connectivité entre le PC et le serveur.
  - Sur le PC, ouvrez l’invite de commande et tapez : `ping 1.1.1.2`
  - Vous devriez recevoir des réponses si la connexion est correcte.

- **Traceroute** : Utilisez `tracert` (sur Windows) ou `traceroute` (sur Linux) pour voir le chemin suivi par les paquets.

### 8. Mise en place du réseau sur Cisco Packet Tracer

1. **Ajouter les dispositifs** : Placez un PC et un serveur de stockage sur la zone de travail.
2. **Connecter les dispositifs** : Utilisez un câble Ethernet pour relier le PC au serveur.
3. **Configurer les adresses IP** :
   - Sélectionnez le PC, accédez aux paramètres IP, et configurez l’adresse `1.1.1.1`.
   - Faites de même pour le serveur avec l’adresse `1.1.1.2`.
4. **Tester la connexion** :
   - Utilisez l'outil de simulation pour vérifier la communication entre les deux machines.
   - Passez en mode temps réel pour effectuer des tests de ping et valider la connectivité.

### Résumé des Étapes sur Cisco Packet Tracer

1. **Placer les dispositifs** : PC et serveur.
2. **Connecter avec un câble Ethernet**.
3. **Configurer les adresses IP** :
   - PC : `1.1.1.1`
   - Serveur : `1.1.1.2`
4. **Tester la connexion** en utilisant les outils de simulation et de temps réel pour confirmer que les deux machines peuvent se communiquer efficacement.

## exo 4

- ### Problème avec l'ajout d'une carte réseau supplémentaire :
   Ajouter une carte réseau au serveur complique la configuration, coûte de l'argent, et n'est pas pratique si on veut connecter plus d'appareils à l'avenir.

- ### Quel équipement choisir pour l'interconnexion :
   Il vaut mieux ajouter un **switch**. Cela permet de connecter plusieurs appareils facilement, sans configuration complexe, et c'est évolutif pour le futur.


## exo 5

> Soit l’adresse réseau suivante : 192.168.1.0

- ### Quel est son masque ?

L'adresse 192.168.1.0 a un masque de sous-réseau de /24, donc le masque est 255.255.255.0.

- ### Combien d’adresses IP peut-on attribuer dans ce réseau. Attention, il y a un piège : faite une recherche sur l’adresse IP de broadcast

Dans ce réseau, il y a 256 adresses possibles, mais on ne peut en utiliser que 254 parce que 192.168.1.0 est l'adresse réseau et 192.168.1.255 est l'adresse de broadcast.

> Soit les adresses ip suivantes : 192.168.1.1/24 et 192.168.24.3/24

- ### Quel est son masque ?

255.255.255.0

- ### Combien d’adresses IP peut-on attribuer dans ce réseau. Attention, il y a un piège : faite une recherche sur l’adresse IP de broadcast

Pour les adresses 192.168.1.1/24 et 192.168.24.3/24, elles ne sont pas sur le même réseau. L'adresse réseau de 192.168.1.1 est 192.168.1.0 et celle de 192.168.24.3 est 192.168.24.0. Donc, deux réseaux différents !


![alt text](./images/Capture%20d’écran%20du%202024-09-10%2016-48-49.png)


- ## exo 6 

### Modèle OSI et ses 7 couches :

1. **Couche 1 : Physique (Physical)**  
   - **Description** : Transmet les bits bruts (0 et 1) sur un support physique (câbles, ondes, etc.).
   - **Élément associé** : Câbles Ethernet, fibres optiques.

2. **Couche 2 : Liaison de données (Data Link)**  
   - **Description** : Assure le transfert de données entre deux dispositifs sur le même réseau, et gère la détection des erreurs de transmission.
   - **Élément associé** : Adresse MAC, commutateurs (switches).

3. **Couche 3 : Réseau (Network)**  
   - **Description** : Gère le routage des paquets à travers différents réseaux.
   - **Élément associé** : Adresse IP, routeurs.

4. **Couche 4 : Transport (Transport)**  
   - **Description** : Assure la transmission fiable des données entre deux hôtes, avec gestion des erreurs et contrôle de flux.
   - **Élément associé** : TCP, UDP.

5. **Couche 5 : Session (Session)**  
   - **Description** : Gère les sessions de communication (établir, maintenir et terminer la connexion).
   - **Élément associé** : API sockets.

6. **Couche 6 : Présentation (Presentation)**  
   - **Description** : Formate et chiffre les données pour qu'elles soient interprétables par la couche application.
   - **Élément associé** : SSL/TLS (cryptage), formats de fichiers (JPEG, MP3).

7. **Couche 7 : Application**  
   - **Description** : Interface avec l'utilisateur et les applications, permettant l'échange de données avec le réseau.
   - **Élément associé** : HTTP, FTP, applications web.

### Pourquoi le modèle OSI est important ?

- **Structure claire** : Il divise la communication réseau en couches distinctes, facilitant la compréhension.
- **Interopérabilité** : Permet à des équipements et logiciels de différents fabricants de fonctionner ensemble.
- **Débogage** : Aide à identifier où se situe un problème dans le réseau (couche physique, transport, etc.).




### Qu’est-ce que TCP et IP ?

- **TCP (Transmission Control Protocol)** : Protocole qui garantit une transmission fiable des données entre deux machines.
- **IP (Internet Protocol)** : Protocole qui gère l'adressage et le routage des paquets de données à travers les réseaux.

### Les couches du modèle TCP/IP :

1. **Accès réseau** : Combine les couches Physique et Liaison de données (OSI), gère la transmission des données sur un support physique.
2. **Internet** : Équivalent à la couche Réseau (OSI), responsable du routage via les adresses IP.
3. **Transport** : Assure la communication fiable (TCP) ou rapide (UDP) entre les hôtes.
4. **Application** : Regroupe Application, Présentation, et Session (OSI), gère les interactions utilisateur et les données.

### Lien avec le modèle OSI :

- Accès réseau (TCP/IP) ⇔ Physique + Liaison (OSI)
- Internet (TCP/IP) ⇔ Réseau (OSI)
- Transport (TCP/IP) ⇔ Transport (OSI)
- Application (TCP/IP) ⇔ Application + Présentation + Session (OSI)

### Importance :

Le modèle TCP/IP est la base d'Internet, plus simple et plus pratique que le modèle OSI.


![alt text](./images/Capture%20d’écran%20du%202024-09-11%2010-25-18.png)




# Sercvices DNS

## exo 1

Voici l'ordre des actions lorsque **PC10** envoie un ping à **PC11**, en supposant que **PC10** ne connaît pas l'adresse IP de **PC11** :

1. **Requête DNS de PC10** :  
   PC10 ne connaît que le nom de PC11. Il envoie donc une **requête DNS** au serveur DNS pour obtenir l'adresse IP de PC11.

2. **Réponse DNS du serveur DNS** :  
   Le serveur DNS répond à PC10 en lui donnant l'adresse IP de PC11.

3. **PC10 lance la commande Ping vers PC11** :  
   Maintenant que PC10 connaît l'adresse IP de PC11, il commence à envoyer des **paquets ICMP** (Ping) à l'adresse IP de PC11.

4. **PC11 reçoit les paquets ICMP et répond** :  
   PC11 reçoit les paquets ICMP de PC10 et envoie des **réponses ICMP** à PC10 pour confirmer la communication.

5. **PC10 reçoit les réponses ICMP de PC11** :  
   PC10 reçoit la confirmation des réponses ICMP de PC11, ce qui termine le processus de Ping.




## exo 2


### Noms de domaine et sous-domaines

Un **nom de domaine** est une adresse web (ex. : `example.com`) qui rend l'accès aux ressources plus facile qu'en utilisant une adresse IP. Un **sous-domaine** est une extension du domaine principal, séparant différentes parties d'un site (ex. : `blog.example.com`).

---

### Types d'enregistrements DNS

1. **A** : Lie un nom de domaine à une IP **IPv4**.
2. **AAAA** : Lie un nom de domaine à une IP **IPv6**.
3. **CNAME** : Redirige un domaine vers un autre domaine.
4. **MX** : Indique les serveurs de messagerie du domaine.
5. **NS** : Spécifie les serveurs DNS pour le domaine.
6. **PTR** : Associe une adresse IP à un nom de domaine (DNS inversé).
7. **TXT** : Stocke des informations textuelles, souvent pour la vérification.
8. **SRV** : Définit des services spécifiques (ex. : SIP).

Les enregistrements DNS dirigent le trafic Internet et gèrent les services comme les emails.



# Protocole HTTP

## exo 1

### Qu'est-ce qu'une API et une API REST ?

Une **API (Application Programming Interface)** est un ensemble de règles et d'outils qui permet à des logiciels de communiquer entre eux. Une **API REST** (Representational State Transfer) est un type d'API qui suit les principes REST, où les données sont accessibles via des requêtes HTTP à des **endpoints** (points d'accès), souvent en JSON ou XML.

### Qu'est-ce que le protocole HTTP ?

Le **protocole HTTP (Hypertext Transfer Protocol)** est un protocole utilisé pour échanger des informations sur le web. Il permet aux navigateurs et serveurs web de communiquer pour afficher des pages, envoyer des données, etc.

### Méthodes disponibles avec le protocole HTTP :

1. **GET** : Récupère des données d'un serveur (lecture).
2. **POST** : Envoie des données au serveur (création).
3. **PUT** : Remplace entièrement une ressource sur le serveur (mise à jour).
4. **PATCH** : Modifie partiellement une ressource.
5. **DELETE** : Supprime une ressource.
6. **HEAD** : Similaire à GET, mais sans le corps de la réponse (métadonnées seulement).
7. **OPTIONS** : Décrit les options de communication pour une ressource.

### Différence entre HTTP et HTTPS :

- **HTTP (Hypertext Transfer Protocol)** : Transfère des données sans chiffrement.
- **HTTPS (Hypertext Transfer Protocol Secure)** : Utilise SSL/TLS pour **chiffrer** les données, garantissant la confidentialité et la sécurité des échanges.

### Qu'est-ce qu'un Bearer Token ?

Un **Bearer Token** est un jeton d'authentification utilisé dans les requêtes HTTP, souvent dans le cadre de **l'authentification via OAuth**. Il est inclus dans l'en-tête de la requête (`Authorization: Bearer <token>`) et permet d'accéder à des ressources protégées sans avoir à fournir des identifiants à chaque requête.



## liens fin de l'éxercice sur les requettes http :

https://checkboxolympics.com/

https://theuselessweb.com/



# exos SSH

## Quels sont les protocoles qui ont été remplacés par SSH ?

Le protocole SSH a été conçu avec l'objectif de remplacer les différents protocoles non chiffrés comme rlogin, telnet, rcp et rsh.


## Quelles sont les différents modes d’utilisation de SSH (notamment au niveau de la sécurité)?

- Accès distant sécurisé :

Mot de passe : Simple mais vulnérable aux attaques par force brute.

Clés SSH : Méthode plus sécurisée via une paire de clés publique/privée.

- Transfert sécurisé de fichiers :

SCP (Secure Copy) et SFTP (SSH File Transfer Protocol) pour transférer des fichiers en toute sécurité.

- Tunneling sécurisé :

Permet de chiffrer le trafic réseau d'autres applications via SSH.

- Port forwarding :

Forwarding local et distant pour sécuriser l'accès à des services internes à un réseau.


## Comment est établie une connection SSH entre un client et un serveur avec la méthode la plus sécurisé (faites un schéma)

![alt text](./images/sshConnectionSchema.jpg)




## php-fpm nginx

### PHP-FPM et NGINX: Utilité et Interaction

#### **NGINX**
- **Serveur Web**: Sert les fichiers statiques (HTML, CSS, JS).
- **Reverse Proxy**: Transmet les requêtes à des serveurs backend comme PHP-FPM pour le traitement des scripts PHP.
- **Load Balancer**: Répartit la charge entre plusieurs serveurs.

#### **PHP-FPM**
- **Exécution PHP**: Traite les fichiers PHP et génère des réponses dynamiques.
- **Gestion des Processus**: Optimise la gestion des ressources PHP avec plusieurs pools de processus.

### Schéma de l'Interaction

```
Utilisateur
    |
    | Requête HTTP (GET /)
    |
   NGINX
    |
    | Fichier Statique ? 
    |-- Oui --> Renvoie le fichier statique
    |
    |-- Non --> Passe à PHP-FPM
    |
 PHP-FPM
    |
    | Exécute le Script PHP
    |
    | Génère la Réponse HTML
    |
   NGINX
    |
    | Renvoie la Réponse à l'Utilisateur
    |
Utilisateur
```

### Résumé
1. **Utilisateur** demande la page d'accueil.
2. **NGINX** vérifie et transmet la requête à **PHP-FPM** si nécessaire.
3. **PHP-FPM** exécute le script PHP et renvoie la réponse à **NGINX**.
4. **NGINX** renvoie la réponse finale à l'utilisateur.

## Limite de l'utilisation de de la méthode pour déployer le sites

Voici un résumé des problématiques liées à la gestion de diverses technologies (Node.js, Python, Go, Java) pour TechFlow :

### 1. **Gestion des Dépendances et Environnements**
- **Problème** : Chaque technologie a ses propres dépendances et versions, ce qui complique l'isolation et la gestion des versions.
- **Solution** : Utiliser des conteneurs Docker pour isoler les environnements.

### 2. **Déploiement Multi-Technologies**
- **Problème** : Les processus de déploiement varient selon les technologies, et la gestion des ressources devient complexe.
- **Solution** : Adopter Kubernetes pour orchestrer les conteneurs de différentes technologies.

### 3. **CI/CD**
- **Problème** : Les pipelines CI/CD doivent gérer des étapes spécifiques pour chaque technologie, augmentant la complexité.
- **Solution** : Créer des pipelines modulaires adaptés à chaque technologie avec des outils CI flexibles.

### 4. **Sécurité et Mises à Jour**
- **Problème** : Chaque technologie a des vulnérabilités spécifiques à surveiller et des pratiques de sécurité différentes.
- **Solution** : Utiliser des outils de sécurité adaptés à chaque langage et maintenir une politique de mise à jour régulière.

### 5. **Compatibilité et Intégration**
- **Problème** : Les différentes applications doivent interagir, ce qui nécessite des standards de communication.
- **Solution** : Utiliser des protocoles d'échange standardisés comme REST ou gRPC.

### 6. **Formation et Compétences**
- **Problème** : Former des développeurs sur plusieurs technologies peut être coûteux et ralentir la productivité.
- **Solution** : Spécialiser les équipes tout en favorisant la collaboration entre elles.

### 7. **Standardisation des Pratiques**
- **Problème** : Maintenir des standards cohérents à travers différentes technologies peut être difficile.
- **Solution** : Établir des pratiques de développement communes mais flexibles pour chaque technologie.

En résumé, la clé est de standardiser autant que possible tout en utilisant des outils modernes pour gérer la diversité technologique.



## Docker

### Différence entre une image Docker et un conteneur

- **Image Docker** : Fichier statique avec tout le nécessaire pour exécuter une application. Immobile et immuable.
- **Conteneur** : Instance en cours d'exécution d'une image, modifiable et temporaire.

### Que fait Docker si l’image demandée n’est pas locale ?

Docker télécharge l’image depuis un registre (comme Docker Hub) et l’installe localement avant de créer le conteneur.