# Collecte ou le monde de L'ISR selon Microsoft

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/pexels-photo-414812.jpeg?w=1024)

La base de tout SIEM est la collecte d’information ; Azure Sentinel n'échappe pas à cette règle.

#### Les connecteurs

La collecte se fait via des connecteurs, et permet un certain niveau de configuration.

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/image.png?w=780)

Liste des connecteurs

Il existe un jeu de couleurs qui permet très rapidement de voir l'état du connecteur :

-   Gris : qui indique un connecteur non activé, mais disponible
-   Vert : qui indique que le dis connecteur est actif
-   Mauve : qui indique qu'il n'est pas encore disponible

-   **Remarque** : Microsoft a aussi introduit des connecteurs en Preview. Il est donc déconseillé de les utiliser, sauf pour un test 😉.

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/019/10/image-1.png?w=807)

Connecteur Inactif

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/image-2.png?w=845)

Connecteur Actif

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/image-3.png?w=821)

Connecteur à venir

Il existe une approche des plus intéressantes dans le cadre d'un déploiement en mode Hybrid (d'un point de vue solution on premise/Azure) :

L’utilisation d’Azure Sentinel pour monitorer et donc collecter les datas venant d'une part de vos Datacenter on premise et d’autre part de vos déploiements dans le cloud (Microsoft ou autres).

-   **Exemple :** Il sera possible de collecter les Data venant de vos firewall, comme F5 par exemple ou de solution palo-alto , pour n'en citer que 2.

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/image-4.png?w=796)

Connecteur Non-Microsoft - F5

Je lève ici un point important, directement influencé par les informations ci-dessus. Comme beaucoup de service cloud, Azure Sentinel a un coût. Dès lors, il sera bien nécessaire de définir ses besoin et une estimation de la volumétrie du nombre d'incident car le prix pourrait très rapidement être relativement important.

Nous reparlerons de ce point ultérieurement.  

#### Les Workbook

Avoir une source de donnée, c'est bien. Mais pouvoir visualiser sur un Dashboard les dites données cela serait mieux. Azure Sentinel fournit un outil adapté : le Workbook, avec un ensemble de templates pour démarrer rapidement.

-   **Exemple :** sur la figure ci-dessous on trouvera un Workbook pour AWS :

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/image-5.png?w=1024)

Workbook pour AWS Network Activites

Ces templates sont associés au connecteur de base présent avec Sentinel. Dans le détail, le portal affiche les Workbooks Templates et se décompose en 4 zones majeures : une frame qui annonce le nombre de Workbook sauvés (utilisés), le nombre de template disponible et les updates;mais aussi une zone pour vos Workbooks et une zonz template ( que je place dans la meme frame) .

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/image-6.png?w=1024)

Frame des WorkBooks

Concernant l’affichage, on y retrouve une zone de listing avec l'ensemble des Templates mais également un listing de vos Workbook en sélectionnant « My Workbook ». Vous y retrouverez une zone avec un court descriptif du Workbook, ainsi que la liste des prérequis pour pouvoir l'utiliser.

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/image-7.png?w=531)

WorkBooks Sample

Il suffira donc de faire une sauvegarde du template qui vous intéresse et de le mettre dans un emplacement lié aux Datacenter d'Azure.

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/image-8.png?w=1024)

Selection de la sauvegarde de votre workbooks

Résultat :

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/image-9.png?w=1024)

Résultat du workbooks

Mais cela ne s'arrête pas là. Si vous le souhaitez, il est possible d'éditer ce template et de le personnaliser comme bon vous semble.

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/image-11.png?w=1024)

Edition

![](https://github.com/Sdeloison/Univers-Azure/blob/main/assets/2019/10/image-12.png?w=612)

List des ressources disponibles pour la customization

Voila pour ce début , je reviendrais pour compléter ces information et présenter plus d'options et surtout comment déployer Azure Sentinel de manières détaillée : un Step-By-Step

