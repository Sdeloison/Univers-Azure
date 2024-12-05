# Azure Sentinel, ou le SIEM selon Microsoft

## **Introduction :**

Dans le monde de l'information, de la data et des clients, la notion de sécurité n'a jamais été aussi présente.

Il en va de même pour le monde de l'application, les modes de consommation et l'hybridation des usages entrainent une nécessité de renforcer la sécurité.

Je n'aborderais pas les aspects à proprement parlé de la sécurité, mais je vais vous présenter Azure Sentinel qui offre une approche multi-faces : 4 piliers de références - Intégration multipolaire – Évolutif

Commençons par présenter rapidement les 4 piliers de références. Ces derniers sont constitués par:

-   Collecte : ce que j'appellerais ISR
-   Détection ou la lever du brouillard de guerre
-   Investigation : l'aspect NCIS de l'outil
-   Réponse **:** Toute action visant à bloquer, canaliser, éradiquer le problème via un ensemble d'actions automatisées, et d'avoir un suivi.

## Collecte ou le monde de L'ISR selon Microsoft

Le premier pilier d’Azure Sentinel est la collecte des informations.

Pour cela Sentinel s'appuiera sur un peu plus de 200 connecteurs (actuellement car ce nombre pourrait évoluer dans le futur). Ces connecteurs couvrent essentiellement les solution Microsoft, tel qu’Azure AD, M365… Pour les autres environnements, Azure Sentinel fournit un ensemble de connecteurs Builtin compatibles avec un grand nombre de solution Non-Microsoft.

-> Ce pilier fera l’objet d'une prochaine publication.

## Détection

La collecte est une phase importante mais la détection d'un incident de sécurité quel qu'il soit est primordial. Sur base des différents connecteurs et des data remontées, Azure Sentinel entreprend de faire du Deep Détection afin de trouver toutes les anomalies de "comportement".

Cette détection passera par l'utilisation d’Azure Monitor Workbook, associé à Azure Analyses, afin de réaliser un tri dans le Bruit des data analysées.

Cet aspect est important car cela va conditionner les actions correctrices et ainsi permettre de réduire les faux positifs.

## Investigation ou quand Sentinel se prend pour le NCIS/FBI

Collecter et analyser c'est bien. Mais ne faudrait-il pas investiguer sur le ou les incidents pour comprendre et corriger les failles ?

Pour cela, Azure Sentinel offre un outil des plus sympa : une visualisation sous forme graphique des incidents et une visualisation de l'ensemble des composants et de ceux impactés par l'incident de sécurité.

On parle ici de "Deep (très à la mode ce terme) Investigation" qui va permette de remonter le cheminement de l’incident, des impacts et d'identifier les failles. Cela revient à faire du "hunting" sur les raisons de l’incident.

À l'issue de cette action de « hunting » : Azure Sentinel, au travers du 4ème et dernier pilier, d'agir de manier autonome (après que l’administrateur ait définitit des règles appropriées) pour bloquer, voir solutionner l’incident, mais également de pouvoir avertir les personnes concernées par cet incident.

Complément d’informations : De par sa faculté d'analyse, de track et de résolution, Azure Sentinel sera un bon auxiliaire pour pouvoir se mettre en conformité avec la GDPR/RGPD mais ne remplacera pas une vraie politique de gestion des données.

## Réponse :

Azure Sentinel, comme indiqué précédemment, sera capable au travers de différents mécanismes d'agir pour circonscrire l'incident de trois manières :

-   de manière soit manuel
-   de manière semi-automatique
-   de manière complètement autonome, qui est la plus intéressante

Non, Azure Sentinel n'est pas un terminator. Cependant, l'utilisation de l'AI et de solution de Deep Learning permettra d'envisager le futur de vos infrastructures multi-domaines, multi-usages et multi-utilisateurs de manière plus sereine.

**Next step :** le prochain papier couvrira la mise en place d'Azure Sentinel et plus si affinité.

> Merci de votre lecture, pour ce premier (certes court) papier.

