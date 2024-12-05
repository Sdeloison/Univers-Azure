# Azure Arc pour les Nuls (Ou plutôt Pour moi 😉):

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/12/arc.png?w=987)

Azure Arc

## Introduction:

Cette rubrique va contenir un ensemble de présentation pour accompagner la découverte et la mise en œuvre d’Azure Arc.

## Planning des post:

Part 1: Introduction à Azure Arc – Ce Post

Part 2: la mise en place d Azure Arc – Les 4 blocks ( donc 4 post 😁)

Part 3 : les options d’Azure Arc -

Part 4 : Les usage - Les scenarios et pour qui ? – exemple de scenario possible ( PME…)

Part 5 : La sécurité et Azure Arc – Un spécial Sécu

part 6: Et Après? – A suivre !

## Part 1 : Introduction à Azure Arc :

Cette partie sera découper en 3 volets :

-   Qu’est-ce que Azure Arc
-   A quoi sert-il ? On parleras des 4 poles d'utilisations
-   Les licences

### Qu’est-ce que Azure Arc?

Azure Arc est une solution Microsoft permettant de gère et d’étendre les service Azure n’importe ou.

Azure Arc va nous aider à déployer ,construire des applications en mode Hybrid ( Onpremise) , Multicloud( Support AWS… ) , et en mode Natif ( Azure ).

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2022/11/image.png?w=975)

Figure 1 Azure Arc

Azure Arc n’est pas un produit, mais plutôt une famille de produit permettant une très grande diversité d’approche et de solutions.

On pourrais classe Azure ARC en 4 grandes block , en fonction des rôles de chacun .

-   Azure Arc for Developers
-   Azure Arc for Cloud Solutions Architects
-   Azure Arc for IT Pros
-   Azure Arc for Security Engineers

Ces grands rôles étant représenté par un ensemble de sous-catégories propres à chacun :

-   Azure Arc Enabled Server
-   Azure Arc Enabled SQL Server
-   Azure Arc Enabled Kubernetes
-   Azure Arc Enabled Azure Stack HCI
-   Azure Arc Enabled VMware VSphere
-   Azure Arc Enabled Data services
-   Azure Arc Enabled application services
-   Azure Arc Enabled Machine Learning

Les 5 premiers étant la pour étendre les Management Tools d’Azure , sur des systèmes Non-Azure

Les 3 autres permettant d’instancier et de gérer des services Azure managés – Type PaaS , hors d’Azure.

Ici , je vais me contenter de vous présenter les 4 grands block, et cela afin de ne pas faire un post imbuvable 😉.

## Les 4 blocks:

Cette courte, enfin cela reste relatif, partie présentera les point important de l’apport d’Azure Arc pour ces Master Rôles.

### Azure Arc for Developers:

Azure Arc et Azure control plane permettent aux développeurs de déployer leur applications en mode Hybrid, et où , multicloud ; leur permettant de gère l’infrastructure et le déployant des service Azure n’importe où, en s’appuyant sur le service Azure Control Plane.

Les développeurs pourront utiliser les services Azure dont ils sont familier, comme les WebApps , Azure SQL , et exécuter leur applications à l’extérieur d’Azure.

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2022/11/image-1.png?w=713)

Figure 2 Azure Arc for Devs

Azure Arc offre des points important pour un développeur :

-   Utilisation d’ Azure Portal pour une vue centralise
-   Manage Access
-   Enable your custom deployment locations
-   Run cloud-native apps on Azure PaaS anywhere
-   Azure Arc enabled Data Services
-   CI/CD workflow utilsant GitOps – Azure Arc enabled Kubernetes
-   Access au Kubernetes Cluster depuis n’importe où
-   Deployer et utilizer Azure Kubernetes Services (AKS) on-premises sur Azure Stack HCI
-   Execute Azure Machine Learning de n’importe où
-   Utiliser Azure Managed Identities on-prem ou d’autre cloud providers
-   Monitoring

Et bien plus.

### Azure Arc for IT Pros

De la même manière Azure Arc va , pour les It Pro , permettre de simplifié la gouvernance et la gestion via une seule platform des mondes Hybrid ( Onpremise-Cloud) et Multicloud.

Azure Arc permet aux IT Professional (IT Pros) de géré l’ensemble des environnements , avec une seule interface, et cela en utilisant Azure Resource Manager.

Il est donc possible maintenant de géré les Serveurs, les Kubernetes clusters, les Databases comme si ils étaient sur Azure.

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2022/11/image-2.png?w=784)

Figure 3 Azure Arc Monitoring sample for It Pros

Point d’intérêt pour les IT Pros :

-   Utilisation d’ Azure Portal comme point central de gestion
-   Organization et Inventory
-   Azure Resource Graph
-   Manage Access
-   Update Management
-   Monitoring
-   Log collection et analytics
-   Change Tracking et Inventory
-   Certificate Management
-   Security
-   Running Scripts sur les servers
-   Gestion du compliance state
-   Gestion de notre Azure Stack HCI

### Azure Arc for Cloud Solutions Architects:

Azure Arc et Azure Control plane service , permettent au Cloud Solution Architect de définir, et construire des Architecture Hybrid et Multicloud.

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2022/11/image-3.png?w=674)

Figure 4 Azure Arc for Cloud Solution Architect

Point d’intérêt pour les Cloud Solution Architect :

-   Utilisation d’ Azure Portal comme point central de gestion
-   Organization et Inventory
-   Azure Resource Graph
-   Manage Access
-   custom deployment locations
-   Exécute les cloud-native apps base sur les Azure PaaS n’importe où
-   Azure Arc enabled Data Services
-   CI/CD workflow utilisant GitOps – Azure Arc enabled Kubernetes
-   Deploy et execute Azure Kubernetes Services (AKS) on-premises sur Azure Stack HCI
-   Utilise Azure Managed Identities on-prem ou d’autre cloud providers
-   Execution de Machine Learning n’importe où
-   Update Management
-   Monitoring
-   Log collection et analytics
-   Change Tracking et Inventory
-   Certificate Management
-   Security
-   Execution des Scripts
-   Gestion des compliance state
-   Gestion de notre Azure Stack HCI

L’ensemble de ces points permettant un plus grand choix d’Architecture possible.

### Azure Arc for Security Engineers:

The last but not the least

Azure Arc , et Azure control plane , vont permettent au Security Engineers de contrôle, maitriser le Cloud Goverance , mais aussi rendre plus sur les environnements Hybride et multiclouds en configurant, contrôlant les aspects Sécurité , Compliance , et cela quel que soit le model Hybrid, Natif ou Multicloud.

En cela Azure Arc permet de simplifier les vues de ces différents composant pour une plus grande efficacités.

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2022/11/image-4.png?w=776)

Figure 5 Azure Arc sample view for Security Engineers

-   Utilisation d’ Azure Portal comme point central de gestion
-   Organization et Inventory
-   Azure Resource Graph
-   Manage Access
-   Update Management
-   Monitoring
-   Log collection et analytics
-   Change Tracking et Inventory
-   Certificate Management
-   Security
-   Compliance State

## Conclusion:

Azure Arc est un outil complet , et qui permettras de manager beaucoup de composant multi environnement .

En cela je vous présenterais les 4 block de manières individuel , mais surtout sur mon retour d’expérience de leur mise en place , je sens que je vais suer. 😉😁
