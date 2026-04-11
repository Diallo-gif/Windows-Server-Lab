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
###  Problèmes rencontrés
 Impossible de ping entre le client et le serveur  
 Cause : Firewall activé sur le serveur  


---
###  Solutions
Solution : Désactivation temporaire pour test réseau
