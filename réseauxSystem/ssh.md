# comment se connecter à une autre machine

https://doc.ubuntu-fr.org/ssh


- ## principe de la connexion ssh :

### 1. **Le principe des clés publiques et privées :**
En cryptographie, on utilise deux clés :
- Une **clé publique** : qui peut être partagée avec tout le monde.
- Une **clé privée** : qui doit rester secrète.

Le principe clé est :
- **Ce qui est chiffré avec la clé publique ne peut être déchiffré qu'avec la clé privée**.
- Et inversement, ce qui est chiffré avec la clé privée peut être vérifié ou déchiffré avec la clé publique (utilisé pour les signatures numériques).

### 2. **Comment ça marche ?**
Imaginons une boîte :
- La **clé publique** permet de verrouiller (chiffrer) la boîte.
- Seule la **clé privée** correspondante peut déverrouiller (déchiffrer) la boîte.

Donc, si quelqu'un veut vous envoyer un message secret :
- Il utilise votre **clé publique** pour le chiffrer.
- Seule votre **clé privée** peut déchiffrer ce message.


### 4. **Utilisation dans SSH :**
Lors d'une connexion SSH, la clé publique est stockée sur le serveur, et la clé privée reste sur votre ordinateur. Le serveur envoie un message chiffré avec votre clé publique, que seul votre ordinateur (avec la clé privée) peut déchiffrer. Cela garantit une connexion sécurisée.

En bref :
- **Clé publique** : pour chiffrer, peut être partagée.
- **Clé privée** : pour déchiffrer, doit rester secrète.

![alt text](../images/ssh.jpg)

## configurer un serveur

https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-fr


## installer le certificat ssl sur le site et le serveur: 

https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04-fr


## Principe clés privée/publique et Clés SSH

Oui, il existe un lien direct entre les clés SSH et le concept des clés publiques et privées. Voici un résumé du rapport :

### 1. **Qu'est-ce qu'une clé SSH ?**
Une clé SSH (Secure Shell) est un outil utilisé pour l'authentification dans les connexions SSH, qui permettent un accès sécurisé à des systèmes distants. Les clés SSH sont basées sur la cryptographie asymétrique.

### 2. **Cryptographie asymétrique et clés publiques/privées**
La cryptographie asymétrique repose sur une paire de clés :
- **Clé privée** : elle reste secrète, stockée en toute sécurité par l'utilisateur.
- **Clé publique** : elle peut être partagée librement avec d'autres, comme un serveur auquel on souhaite se connecter.

Ces deux clés sont mathématiquement liées. Une clé publique peut être utilisée pour vérifier une signature générée avec la clé privée ou pour chiffrer un message que seule la clé privée pourra déchiffrer.

### 3. **Clés SSH et le système de clés publiques/privées**
Les clés SSH utilisent exactement ce principe de clés publiques et privées :
- **Clé privée SSH** : elle est stockée sur votre machine locale, généralement dans `~/.ssh/id_rsa` (ou un autre fichier en fonction de l'algorithme utilisé, comme `id_ecdsa` ou `id_ed25519`).
- **Clé publique SSH** : elle est dérivée de la clé privée et stockée dans un fichier comme `~/.ssh/id_rsa.pub`. Elle est copiée sur le serveur distant dans un fichier tel que `~/.ssh/authorized_keys`.

### 4. **Fonctionnement de l'authentification SSH**
Voici comment l'authentification se déroule :
1. Lorsque vous tentez de vous connecter à un serveur via SSH, votre client utilise votre clé privée pour signer un message.
2. Le serveur, qui a déjà votre clé publique, vérifie cette signature.
3. Si la signature correspond à la clé publique, le serveur accorde l'accès.

### 5. **Avantages de ce système**
- **Sécurité renforcée** : Votre clé privée n'est jamais partagée, ce qui minimise le risque d'interception.
- **Commodité** : Une fois configurée, elle élimine le besoin de mots de passe pour chaque connexion.

### Conclusion
Les clés SSH sont un exemple concret de l'utilisation du système de clés publiques et privées dans le domaine de la sécurité informatique. Elles exploitent cette technologie pour offrir une méthode d'authentification robuste et sécurisée.