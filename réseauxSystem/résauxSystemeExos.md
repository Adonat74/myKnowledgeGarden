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
    - 


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

- ### Problème avec l'ajout d'une carte réseau supplémentaire :**
   Ajouter une carte réseau au serveur complique la configuration, coûte de l'argent, et n'est pas pratique si on veut connecter plus d'appareils à l'avenir.

- ### Quel équipement choisir pour l'interconnexion :**
   Il vaut mieux ajouter un **switch**. Cela permet de connecter plusieurs appareils facilement, sans configuration complexe, et c'est évolutif pour le futur.