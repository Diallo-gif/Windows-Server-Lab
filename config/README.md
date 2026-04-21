#  Configuration du Lab

## Configuration réseau

- Réseau utilisé : Host-only (VirtualBox)
- Plage IP : 192.168.56.0/24

Serveur-01 (DC-ALPHA) :
- IP : 192.168.56.50
- DNS : 192.168.56.50

Serveur-02 (DC-BETA) :
-IP : 192.168.56.60
-DNS : 192.168.56.60

CLIENT-01 :
- IP : DHCP 
- DNS : 192.168.56.50

---
##  Domaine
- Domaine principal : alpha.local
- Contrôleur principal : Serveur-01 (DC-ALPHA)
- Second contrôleur : Serveur-02 (DC-BETA)
  
Objectif :

Mettre en place une infrastructure Active Directory fonctionnelle,
incluant la communication entre deux domaines via une relation d’approbation (trust).

- Permettre l’authentification entre les domaines alpha.local et beta.local
- Assurer la résolution DNS entre les deux environnements
- Mettre en place une gestion sécurisée des accès basée sur les groupes

##  Utilisateurs et groupes

Création d’une structure basée sur les bonnes pratiques Active Directory :

- Organisation des utilisateurs dans des OU (IT, RH, Direction…)
- Création de groupes de sécurité :
  - GG_Alpha_Users
  - GG_Beta_Share_Access

Principe appliqué :
 Les permissions sont attribuées aux groupes et non directement aux utilisateurs.

Exemple :
- Utilisateur : user_alpha
- Groupe : GG_Alpha_Users
- Affectation via appartenance au groupe

---

##  GPO

Mise en place de stratégies de groupe pour renforcer la sécurité :

- Restriction d’accès au panneau de configuration
- Application d’une configuration centralisée

Objectif :
 Standardiser et sécuriser l’environnement utilisateur

---

##  DHCP / DNS

Configuration des services réseau :

- Attribution d’adresses IP via DHCP
- Configuration des serveurs DNS pour la résolution des noms

Tests réalisés :
- Vérification de la connectivité réseau
- Test de résolution DNS avec `nslookup`

Résultat :
 Communication fonctionnelle entre les machines et les domaines

---
## VPN (Accès à distance)

### Configuration
- Mise en place du rôle Accès à distance (RRAS)
- Activation du service VPN et NAT
- Configuration de l’interface WAN (accès Internet)
- Création d’un pool d’adresses IP pour les clients VPN

### Authentification
- Utilisation des comptes Active Directory
- Autorisation d’accès VPN configurée sur les utilisateurs

### Tests réalisés
- Connexion d’un client distant au serveur VPN
- Vérification de l’adresse IP attribuée (ipconfig)
- Accès au domaine interne depuis le client VPN

### Résultat
- Connexion sécurisée établie entre le client et le réseau interne
- Accès aux ressources selon les permissions Active Directory

### Contexte
- Simulation d’un environnement de télétravail sécurisé
