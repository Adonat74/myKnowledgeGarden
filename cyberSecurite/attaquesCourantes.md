# Les attaques informatiques les plus courantes

## Attaque par Déni de Service Distribué (DDoS)

> Une attaque par Déni de Service Distribué (DDoS) vise à rendre un service en ligne indisponible en submergeant le site avec un trafic massif provenant de multiples sources.

### Prévenir

- Utiliser des pare-feux d'application (WAF) : Filtrer et surveiller le trafic HTTP pour bloquer les attaques.
- Configurer des systèmes de détection et de prévention des intrusions (IDS/IPS) : Détecter et bloquer les trafics malveillants.
- Mettre en place des services de protection DDoS : Utiliser des services comme Cloudflare ou Akamai pour absorber les trafics excessifs.
- Plan de redondance : Avoir plusieurs serveurs en divers endroits géographiques pour distribuer la charge.
- Limiter le taux de trafic : Mettre en œuvre des techniques de limitation de débit pour limiter le nombre de requêtes qu'un utilisateur peut faire sur une période donnée.


### Réagir

- Identifier la source : Utiliser des outils de surveillance réseau pour identifier la source des attaques.
- Rediriger le trafic : Utiliser des services de redirection de trafic pour dévier les attaques vers des systèmes d'absorption.
- Communiquer avec votre fournisseur de services Internet (ISP) : Travailler avec votre ISP pour filtrer les attaques en amont.
- Surveiller les systèmes : Continuer à surveiller les systèmes pour des schémas d'attaques récurrentes.



## Attaque de l'Homme du Milieu (MitM)

> Une attaque de l'Homme du Milieu (MitM) consiste à intercepter et éventuellement altérer les communications entre deux parties sans qu'elles en soient conscientes.

### Prévenir

- Utiliser des connexions chiffrées : Toujours utiliser HTTPS, TLS et SSL pour sécuriser les communications.
- Authentification mutuelle : Utiliser des certificats pour authentifier les deux parties de la communication.
- Réseaux privés virtuels (VPN) : Utiliser des VPN pour sécuriser les connexions réseau.
- Configurer les pare-feux et les IDS/IPS : Pour détecter et bloquer les tentatives d'interception.


### Réagir

- Interrompre la connexion : Déconnecter immédiatement les connexions suspectes.
- Analyser les journaux : Examiner les journaux de réseau pour identifier l'origine de l'attaque.
- Mettre à jour les certificats : Révoquer les certificats compromis et en émettre de nouveaux.
- Informer les utilisateurs : Communiquer rapidement avec les utilisateurs concernés pour qu'ils changent leurs identifiants et mots de passe.


## Injection SQL

> Une injection SQL est une attaque qui permet à un attaquant d'exécuter des requêtes SQL arbitraires sur une base de données en exploitant des vulnérabilités dans les entrées utilisateur.

### Prévenir

- Validation des entrées : Valider et filtrer toutes les entrées utilisateur pour éviter les caractères dangereux.
- Utiliser des requêtes préparées : Utiliser des requêtes paramétrées pour empêcher l'injection de code SQL.
- Mettre à jour les logiciels : Garder le SGBD et les applications à jour avec les derniers correctifs de sécurité.
- Limiter les privilèges des comptes de base de données : Utiliser des comptes de base de données avec les moindres privilèges nécessaires.


### Réagir

- Isoler la base de données : Si une attaque est détectée, isoler la base de données pour limiter les dégâts.
- Analyser les logs : Examiner les journaux pour comprendre l'étendue de l'attaque et identifier les failles exploitées.
- Corriger les vulnérabilités : Appliquer les correctifs nécessaires et renforcer les mesures de prévention.
- Informer les parties concernées : Notifier les utilisateurs et les parties prenantes si leurs données ont été compromises.

## Cross-Site Scripting (XSS)

> Le Cross-Site Scripting (XSS) est une attaque qui permet à un attaquant d'injecter du code malveillant dans une page web vue par d'autres utilisateurs, souvent via des entrées utilisateur non sécurisées.

### Prévenir

- Échapper les entrées et sorties : Échapper correctement toutes les données fournies par l'utilisateur avant de les afficher.
- Utiliser des Content Security Policies (CSP) : Mettre en place des CSP pour limiter les sources de contenu et réduire les risques XSS.
- Validation des entrées : Valider et nettoyer toutes les entrées utilisateur pour éviter l'injection de code malveillant.
- Mises à jour régulières : Garder les bibliothèques et frameworks à jour avec les derniers correctifs de sécurité.


### Réagir

- Identifier et corriger les vulnérabilités : Trouver et corriger les points faibles dans le code source.
- Nettoyer le site affecté : Éliminer tout code malveillant injecté dans le site.
- Notifier les utilisateurs : Informer les utilisateurs potentiellement affectés par l'attaque.
- Audit de sécurité : Effectuer un audit complet pour s'assurer que toutes les failles XSS sont corrigées.