#  Documentation du projet

## Phase 1 — Installation Active Directory

###  Objectif

Ce projet a pour objectif de simuler une infrastructure d’entreprise
en déployant un environnement Active Directory sous Windows Server,
incluant plusieurs contrôleurs de domaine.

L’objectif est de comprendre les mécanismes essentiels :

- Authentification centralisée
- Résolution DNS
- Gestion des machines et des utilisateurs
- Réplication entre contrôleurs de domaine

---

###  Étapes réalisées
1. Installation de Windows Server
2. Configuration du réseau (IP statique)
3. Installation du rôle Active Directory (AD DS)
4. Promotion en contrôleur de domaine (alpha.local)
5. Mise en place d’un second contrôleur de domaine
6. Intégration d’une machine cliente au domaine

---
### Résultat
Le domaine Active Directory est opérationnel et prêt à accueillir des machines clientes.
- Intégration d'une machine cleinte au domaine réussie

###  Ce que j’ai appris
- Le rôle du contrôleur de domaine
- L’importance du DNS dans Active Directory
- La configuration réseau avant installation

---
##  Problème rencontré
-
 Impossible de ping entre le client et le serveur  
 Cause : Firewall activé sur le serveur  
---
##  Solutions
Solution : Désactivation temporaire pour test réseau

### Phase 2 — Configuration du serveur DNS
## Objectif
Mettre en place un serveur DNS afin de permettre la résolution des noms dans le domaine Active Directory.

Le DNS est un composant essentiel d’Active Directory, car il permet de traduire les noms de domaine en adresses IP et de localiser les services du domaine

 ## Configuration réalisée
Installation du rôle DNS sur le contrôleur de domaine
Création de la zone de recherche directe : alpha.local
Création automatique de la zone _msdcs.alpha.local
Mise en place d’une zone de recherche inversée
Ajout d’un enregistrement PTR pour associer une adresse IP à un nom de machine
## Problème rencontré:
Le serveur DNS était mal configuré, empêchant la résolution du nom de domaine malgré une connectivité réseau fonctionnelle.
## solution trouvée:
Correction de la configuration DNS en pointant la machine vers l’adresse IP du contrôleur de domaine (192.168.56.50).

## Phase 3 — Installation et configuration du serveur DHCP
### Objectif
Mettre en place un serveur DHCP afin d’attribuer automatiquement des adresses IP aux machines du réseau interne.

---
### Étapes réalisées

1. Installation du rôle DHCP
   - Ajout du rôle via le Gestionnaire de serveur

2. Configuration du serveur DHCP
   - Autorisation du serveur dans Active Directory

3. Création d’un scope DHCP
   - Plage d’adresses : 192.168.56.100 – 192.168.56.200
   - Masque de sous-réseau : 255.255.255.0

4. Configuration des options DHCP
   - Passerelle par défaut : 192.168.56.50
   - Serveur DNS : 192.168.56.50
   - Nom de domaine : alpha.local

5. Test côté client
   - Renouvellement de l’adresse IP (`ipconfig /renew`)
   - Vérification de l’attribution d’une IP correcte
   - Test de connectivité avec le serveur (ping)
---
### Résultat
Après avoir fait: ipconfig /release et ipconfig /renew on a:
les machines clientes obtiennent automatiquement une adresse IP valide et peuvent communiquer avec le serveur ainsi qu’avec le domaine Active Directory.

### Organisation Active Directory
## Configuration réalisée
Création d’Unités d’Organisation (OU) pour structurer l’entreprise :
OU UTILISATEURS
IT
RH
COMPTABILITES
DIRECTION
OU GROUPES
OU ORDINATEURS
OU SERVEURS
