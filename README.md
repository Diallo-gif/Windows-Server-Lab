## Technologies utilisées

- Windows Server 2019
- Active Directory Domain Services (AD DS)
- DNS (Domain Name System)
- DHCP (Dynamic Host Configuration Protocol)
- GPO (Group Policy Objects)
- VirtualBox (environnement de virtualisation)
- Windows 10 (poste client)
---
## Architecture

Infrastructure simulant un environnement PME avec deux domaines Windows Server :

- 1 serveur principal :
  - Nom : SERVER-01
  - Domaine : alpha.local
  - Rôles : AD DS, DNS, DHCP

- 1 second serveur :
  - Nom : SERVER-02
  - Domaine : beta.local
  - Rôle : contrôleur de domaine secondaire pour la mise en place d’une relation d’approbation

- 1 poste client :
  - Nom : CLIENT-01
  - Intégré au domaine : alpha.local

- Réseau interne :
  - Plage IP principale : 192.168.56.0/24
  - Attribution automatique des adresses IP via DHCP

- Relation d’approbation :
  - Mise en place d’un trust entre `alpha.local` et `beta.local`

Objectif : reproduire une architecture Windows Server réaliste avec gestion de domaine, services réseau et communication inter-domaines.

---
## Fonctionnalités mises en place

- Déploiement de deux contrôleurs de domaine
- Création des domaines "alpha.local" et "beta.local"
- Mise en place d’une relation d’approbation entre les deux domaines
- Création et gestion des utilisateurs et groupes
- Organisation des ressources via les OU (Unités d’Organisation)
- Configuration du serveur DNS pour la résolution de noms
- Mise en place du serveur DHCP pour l’attribution automatique des IP
- Application de stratégies de groupe (GPO)
- Gestion des permissions NTFS et des groupes
- Simulation d’incidents réseau et système (DHCP, DNS, accès)

---

## Statut

Projet en cours d’amélioration continue :

- Ajout de nouveaux scénarios d’incidents
- Amélioration de la documentation
- Ajout de cas pratiques pour simuler des situations réelles
