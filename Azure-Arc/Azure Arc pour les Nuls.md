# Blog 2 : Azure Arc – Le Retour aux Sources


#  Intro:

Humblement j’ai revu mes Target à la baisse, en effet lors de mes 1 er test d’utilisation d’Azure Arc Jumpbox ; je me suis rendue compte que je ne maitrise pas toutes les briques . 😕

J’ai donc décidé de reprendre les bases et de déployé une solution Azure Arc mais de manière maitrisés. 😋

Il y aura à la suite de ce Blog 2 le retour , plusieurs autres sur les déploiements des composant de la familles Azure Arc.

Pour arrive à ce résultats , je me suis inspire des blogs de mes 2 mentors sur cet Techno :

Celui de Stanislas Quastana ( en FR) et celui de Thomas Maurer (en Uk) ; je les remercies pour leur travailles et l’inspiration qu’ils m’ont apportés.

## Planning :

Ce post sera découpé en 3 parties :

 - Step 1 : Rappel de ce qu’est Azure Arc.
 - Step 2 : Les prérequis et leur mise en place.   
 - Step 3 : Le deployment d’ Azure Arc Enabled Server

## Step 1: Mais qu’ est-ce donc qu’ Azure Arc ?

All your files and folders are presented as a tree in the file explorer. You can switch from one to another by clicking a file in the tree.

## Rename a file

Azure Arc est un service Microsoft Azure , accessible via le portail et managé depuis ce dernier.
*Image insert*

La fonction d’Azure Arc est de manage , et suivre un ensemble de composant tel que :

-   Les service Azure type VM et SQL
-   Les autres Cloud : AWS, ou GCP.
-   Mais aussi des composant 100% on-Premise : type VMWare , ou Hyper-V.

On parle donc ici de **Solution de management Hybride** .

Les principaux composant qu’ Azure Arc manage sont les suivant :

1.  Instancier et gérer des services Azure managés (PaaS) hors de Azure :
2.  Azure Arc enabled data services
3.  Azure Arc enabled application services
4.  Azure Arc enabled Machine Learning
5.  Etendre les outils de gestion et de sécurité d’Azure pour des systèmes hors d’Azure:
6.  Azure Arc enabled servers
7.  Azure Arc enabled Kubernetes
8.  Azure Arc enabled Azure Stack HCI
9.  Azure Arc enabled VMware vSphere
10.  Azure Arc enabled SCVMM

Je me fais force de vous faire un article pour chaque un de ces éléments, et en fonction de mes moyens.
*Image insert*


## Step 2 : Les prérequis et leur mise en place.

REM : les prérequis cites ci-dessous sont pour la partie Azure Arc Enabled.

Lors de la planification de votre déploiement, pensez aux points ci-dessous :

-   Vos machines doivent exécuter un système d’exploitation pris en charge pour l’agent Connected Machine.
-   Vos machines doivent disposer d’une connectivité à partir de votre réseau local ou d’un autre environnement cloud aux ressources Azure, directement ou via un serveur proxy.
-   Pour installer et configurer l’agent Azure Connected Machine, vous devez disposer d’un compte doté de privilèges élevés (c’est-à-dire, administrateur ou racine) sur les machines.
-   Pour intégrer des machines, vous devez avoir le rôle **Intégration Azured’ Connected Machine**.
-   Pour lire, modifier et supprimer une machine, vous devez avoir le rôle **Administrateur de ressources Azure Connected Machine**.

Et bien évidement une Azure Suscription 😉

### Environnements pris en charge:

Les serveurs avec Azure Arc prennent en charge l’installation de l’agent Connected Machine sur des serveurs physiques et des machines virtuelles hébergées en dehors d’Azure. Cela comprend la prise en charge des machines virtuelles s’exécutant sur des plateformes comme :

-   VMware (y compris Azure VMware Solution)
-   Azure Stack HCI
-   Autres environments cloud

REM : Vous ne devez pas installer Azure Arc sur des machines virtuelles hébergées dans Azure, Azure Stack Hub ou Azure Stack Edge, car elles disposent déjà de fonctionnalités similaires.

*Insert Image*

### Systèmes d’exploitation pris en charge
Azure Arc prend en charge les systèmes d’exploitation Windows et Linux suivants. Seules les architectures x86-64 (64 bits) sont prises en charge. Azure Arc ne s’exécute pas sur des architectures x86 (32 bits) ou ARM.

-   Windows Server 2008 R2 SP1, 2012 R2, 2016, 2019 et 2022
    
    -   Les expériences Desktop et Server Core sont toutes deux prises en charge
    
    -   Les éditions Azure sont prises en charge sur Azure Stack HCI
-   Windows 10, 11
-   Windows IoT Entreprise
-   Azure Stack HCI
-   Ubuntu 16.04, 18.04, 20.04 et 22.04 LTS
-   Debian 10 et 11
-   CentOS Linux 7 et 8
-   Rocky Linux 8
-   SUSE Linux Enterprise Server (SLES) 12 et 15
-   Red Hat Enterprise Linux (RHEL) 7, 8 et 9
-   Amazon Linux 2
-   Oracle Linux 7 et 8

Cf Microsoft Documentation :

[Connected Machine agent prerequisites – Azure Arc | Microsoft Learn](https://learn.microsoft.com/en-us/azure/azure-arc/servers/prerequisites#supported-environments)

### Configuration logicielle requise:

Systèmes d’exploitation Windows :

-   NET Framework 4.6 ou version ultérieure.[](https://learn.microsoft.com/fr-fr/dotnet/framework/install/guide-for-developers)
-   Windows PowerShell version 4.0 ou ultérieure

Systems exploitation Linux :

-   systemd
-   wget (pour télécharger le script d’installation)
-   openssl
-   Gnupg

Cf Microsoft Documentation :

[Connected Machine agent prerequisites – Azure Arc | Microsoft Learn](https://learn.microsoft.com/en-us/azure/azure-arc/servers/prerequisites#supported-environments)

### Authorizations requises

Vous aurez besoin des rôles intégrés Azure suivants pour différents aspects de la gestion des machines connectées :

-   Pour intégrer des machines, vous devez disposer du rôle **Azure Connected Machine Onboarding** **ou** **Contributor** pour le RG dans lequel vous gérez les serveurs.
-   Pour lire, modifier et supprimer une machine, vous devez être membre du **Azure Connected Machine Resource Administrator** pour le RG.
-   Pour sélectionner un RG dans la liste déroulante lors de l’utilisation de la méthode **Générer un script** , vous avez également besoin du **rôle** **Reader**  pour ce groupe de ressources .

### Azure ressource providers

Pour utiliser des serveurs Azure Arc, les Azure ressources providers suivants doivent être inscrits dans votre abonnement :

-   **Microsoft.HybridCompute**
-   **Microsoft.GuestConfiguration**
-   **Microsoft.HybridConnectivity**
-   **Microsoft.AzureArcData** (si vous envisagez d’activer Les serveurs SQL)

*Insert Image*
##  Step 3 : Deployment Azure Arc enabled server
REM: les autres aspects des déploiement d’Azure Arc , serons traite dans mes autres articles.

### Scenario :

Il s’agit ici de déployer les agents Azure Arc sur une Server Hyper-V , ou plus précisément sur les VM hébergés sur ce dernier.

Il y aura 3 VM :

-Windows Server 2019

-Windows 10

-Linux CentOs

### Déroulement Step-By-Step :

Step 1 : Se connecte au portail Azure

Step 2 : sélectionner Azure Arc

Step 3 : Select : “ Add your infra for Free “

Step 4: Select “Add in your Server part”

Step 5 : select “Add Single Server” -> Creation du script pour l’installation sur le Target.

Step 6 : remplir les éléments demande – cf l’image

Step 7 déployer le script sur le Target ( Linux, Windows..)

Step 8 : vérification de l’ajout dans Azure Arc.

#### Déroulement Step-By-Step en Images:

Step 1: Ouvrir le portail Azure

Step 2 : sélectionner Azure Arc

Step 3 : Select : “ Add your infra for Free “

![](https://universazure.fr/wp-content/uploads/2023/03/image-7.png?w=975)

Step 4: Select “Add in your Server part”

![](https://universazure.fr/wp-content/uploads/2023/03/image-8.png?w=975)

Step 5 : select “Add Single Server” -Generate Script.

![](https://universazure.fr/wp-content/uploads/2023/03/image-9.png?w=535)

Step 6 : remplir les éléments demande

![](https://universazure.fr/wp-content/uploads/2023/03/image-10.png?w=676)

Step 6-1

![](https://universazure.fr/wp-content/uploads/2023/03/image-11.png?w=675)

Step 6 -2

![](https://universazure.fr/wp-content/uploads/2023/03/image-12.png?w=568)

Step 6 -3

![](https://universazure.fr/wp-content/uploads/2023/03/image-13.png?w=570)

Step 6 -4

![](https://universazure.fr/wp-content/uploads/2023/03/image-14.png?w=859)

Step 7 déployer le script sur le Target ( Linux, Windows..)

Step 8 : vérification de l’ajout dans Azure Arc

![](https://universazure.fr/wp-content/uploads/2023/03/image-15.png?w=975)

Et voila nous venons de faire un Onboarding de server dans Azure Arc.

Je vous présenterais dans mon Blog Suivant les aspects que Azure Arc permet de faire sur les éléments déployer : Azure Policies, …..

A Bientôt pour continuer la découverte de l’Univers Azure Arc !!

