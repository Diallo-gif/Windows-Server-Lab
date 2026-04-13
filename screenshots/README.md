#  Screenshots
Ce dossier contiendra les captures d’écran du projet :

## Domaine ALPHA (principal)

### Installation Active Directory
![Installation AD](./1.png)

Installation du rôle AD DS et préparation du serveur pour la promotion en contrôleur de domaine.

### Connexion au domaine
![Login domaine](./2.png)
Connexion réussie avec un compte du domaine alpha.local.

### Dashboard serveur
![Dashboard](./3.png)
Vérification des rôles AD DS et DNS actifs sur le serveur.

##  Domaine BETA (second contrôleur de domaine)
Le domaine BETA simule une filiale dans une infrastructure multi-domaines.
### Connexion au domaine
![Login BETA](./beta-login.png)

Connexion réussie avec un compte du domaine beta.local.

### Dashboard serveur
![Dashboard BETA](./beta-dashboard.png)

Vérification des rôles AD DS et DNS actifs sur le serveur BETA.

### Intégration d’un client au domaine
Objectif :  
Intégrer une machine Windows 10 (CLIENT-01) au domaine Active Directory alpha.local.

Étapes réalisées :  
- Configuration réseau du client  
- Connexion au domaine alpha.local  
- Authentification avec un compte administrateur  
- Redémarrage de la machine  

Résultat :  
La machine CLIENT-01 est désormais membre du domaine et peut communiquer avec le contrôleur de domaine.

Preuves :
Les screenshots suivantes montrent la réussite de l’intégration du client au domaine ainsi que la communication avec le contrôleur de domaine.
Preuves :

Les captures d’écran ci-dessous montrent la réussite de l’intégration du client au domaine ainsi que la communication avec le contrôleur de domaine.

![Join Domain](./Client-1(dans-le-domaine).png)
### Installation et configuration Du DNS
![vue-de-zone](vue-de-zone.png)
![pointeur-PTR](pointeur-PTR.png)
![console-nslookup](console-nslookup.png)

#### Installation du rôle DHCP

![Scope DHCP](Etendue.png)

![DHCP Pool](adresse.png)

![Test DHCP](console.png)
### Active Directory de l'organisation
![unité-d'organisation](unité-d'organisation.png)


