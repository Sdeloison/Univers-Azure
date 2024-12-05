# Blog Article 3:Azure Arc et Azure Policy


Dans ce nouvelle opus , LOL 😋, je vais vous parle de l’interaction entre Azure Arc , et les Azure Policy.

Cet article seras composer de 4 parties :

1.  Rappel sur Azure Policy
2.  Azure Policy with Azure Arc - Sample : Monitoring et Compliancy
3.  Demo Step-By-Step
4.  Conclusion

## Part 1 :Azure Policy : Mais qu’est-ce donc ? Et à quoi cela sert ?

**Déf :**

Azure Policy est un outil permettant de standardise et normalise les ressources Azure pour permettre de déployé de manière global un ensemble de règles pour permettre un gestion rationnel .

Par exemple : Les tags, déploiement de Defender…..

Donc pour avoir un Azure aux normes , et compliance avec un ensemble de règles, et de gouvernances, il faut faire appel à Super « Azure Policy » 😉.

Cf cette URL :

[Overview of Azure Policy - Azure Policy | Microsoft Learn](https://learn.microsoft.com/en-us/azure/governance/policy/overview)

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture1.png?w=398)

Figure 1 - Azure Arc & Azure Policy

Extrait de : Buchanan, S., Joyner, J. (2022). Azure Management Insights. In: Azure Arc-Enabled Kubernetes and Servers. Apress, Berkeley, CA

## Part 2: Azure Arc : Déployer les Azure Policy sur des machines non Azure

Dans cette partie , je vais vous montre les options permettant de déployé des Azure Policy , pour manager les machines non Azure ( Hyper-V , local, VMware).

Ici j’utiliserais mon Server Hyper-V pour mes captures et ma démo ( cf part 3).

Pour faire cela, je vais déployer un Azure Policy pour monitore les machine, et remonte leur données.

### a/ les prérequis – Choisir les Azure Policy :

Azure Policy comprend plusieurs définitions prédéfinies en rapport avec Azure Monitor. Pour obtenir la liste complète des stratégies intégrées de la catégorie **Monitoring.**

Pour déployer cette solution , il est nécessaire :

De d’abord définir l’Azure Policy a déployé, et donc de bien avoir en vue le résultat recherché.(cf ex)

-   Active les options de Azure Log Monitoring sur les VM => **_Enable Azure Monitoring for VM_**.

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture2.png?w=791)

Figure 2 - Azure Policy sample

### b/ Azure Policy : les détails – Activations et mise en œuvres

-   Via le portail Azure , après avoir sélectionné la Policy , il est nécessaire de l’assigne :

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture3.png?w=516)

Figure 3 - Azure Policy Assign

-   Entrée l’ensemble des informations demande, et déployé la Policy :

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture4.png?w=541)

Figure 4- Azure Policy suite

### C/ Déploiement en l’image :

-   Ouvrir le portail azure : Sélectionner , ou rechercher après : « Policy »

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture5.png?w=611)

Figure 5 - Azure Policy search & found

-   Click sur Assignments

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture6.png?w=233)

Figure 6 - Azure Policy Assign selection

-   Puis Click sur Assign Policy

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture7.png?w=450)

Figure 7 - Azure Policy Action

-   Saisir les informations dans les différentes zones :

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture8.png?w=592)

Zone 1 : entrée le Scope choisie

Zone 2 : choisir la Policy à déployer et , donner un nom à votre Assign

Zone 3 : click Next

-   Zone 1 : choisir la suscription et le Ressource Group d’assignation

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture9-2.png?w=469)

Figure 8 - Azure Policy Scope – Zone 1

Zone 2 : Recherche les définitions , et choisir celle qui vous intéresse

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture10-1.png?w=600)

Figure 9 - Azure Policy Zone 2 Policy Definition

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture11-1.png?w=372)

-   Dans la zone Advanced , vérifier , et click sur Next

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture12-2.png?w=626)

Figure 10 - Azure Policy - Advanced Option

-   Entre , si nécessaire les paramètres

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture13-1.png?w=615)

Figure 11 - Azure Policy - Parameters

-   selectionner la case : Create a Managed Identity

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture14-1.png?w=509)

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture15-1.png?w=508)

Figure 12 - Azure Policy - Managed Identity

-   Saisir un message , si nécessaire pour indiquer la Non-Compliance

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture16.png?w=608)

Figure 13 - Azure Policy Message

-   Review

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture17.png?w=551)

Figure 14 - Azure Policy Review

On click sur create.

### d/ Azure Policy Result :

-   Sur le Portail , il est possible de voir le résultat de des Policy déployer

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture18.png?w=594)

Figure 15 - Azure Policy - Portail

-   Présentation de notre Policy avant remédiation

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture19.png?w=598)

Figure 16 - Azure Policy Ma Policy

### d/ Remediation:

-   Creation d’ une Remediation Task pour une Azure Policy for Azure Arc :

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture20.png?w=511)

Figure 17 - Azure Policy -Remediation Task

-   Sélectionner les éléments pour la remédiation , et click sur Remediate

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture21-1.png?w=943)

Figure 18- Azure Policy - Remediation

-   Etat de la creation

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture22.png?w=350)

Figure 19 - Azure Policy Remediation creation

Résultat de la task de remédiation :

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2023/10/picture23.png?w=604)

Figure 20 - Azure Policy After Remediation

# Conclusion:

L’association Azure Policy avec Azure

