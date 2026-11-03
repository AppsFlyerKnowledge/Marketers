---
title: LTV vs. Activité
metadata:
  keywords:
    - dashboard
    - activity
    - Advertisers
    - ltv
    - life time value
    - lifetime value
    - lifetime
    - Agencies
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
  created_at: '2017-11-07T12:42:27Z'
  edited_at: '2021-06-14T23:16:06Z'
  id: 115005600889
  locale: fr
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/fr/articles/115005600889
---
> **En bref :** les données dans AppsFlyer sont soit la valeur à vie (LTV), soit l'activité. Les données LTV sont liées aux installations qui se produisent pendant la période spécifiée. Les données d'activité correspondent à tous les événements qui se produisent pendant la plage de dates spécifiée.

## LTV vs. Activité

Il existe deux méthodes d'analyse des données d'événement utilisateur.  Les données d'évènement concernent toute action exécutée par des utilisateurs après l'installation, comme des achats in-app, des inscriptions et des réussites de niveaux. Dans AppsFlyer, les données d'événements peuvent être regroupées par date d'acquisition, par l'utilisateur ou par date chronologique de l'événement.

* Les données regroupées selon la date d'acquisition de l'utilisateur sont appelées Durée de vie (LTV).
* Les données regroupées chronologiquement sont appelées données d'activité.

Il est important de comprendre ce qu'elles signifient et où les trouver. Notez que les installations ne sont ni des données d'activité ni des données LTV.

#### **Données d'activité**

* Il s'agit d'évènements réalisés par les utilisateurs actifs de l'app au cours d'une période spécifique.
* Les données d'activité affichent une répartition précise des évènements chronologiques. Elles sont utiles pour mesurer la performance globale des sources médias sur des périodes spécifiques.
* Par exemple, vous pouvez utiliser les données d'activité pour voir le nombre d'évènements d'achat fournis par tous les utilisateurs du mois de janvier.
* Utilisez les données d'activité pour comparer le comportement des utilisateurs du mois en cours par rapport au mois précédent.

#### **Données LTV**

* Les données LTV sont des évènements réalisés tout au long de la valeur vie d'un utilisateur qui a installé l'app au cours d'une période spécifique.
* Les évènements réalisés par les utilisateurs qui ont installé l'app avant la période donnée ne sont pas affichés dans les données LTV, même si l'évènement s'est produit dans la période donnée.
* Par exemple, utilisez les données LTV pour voir le ROI jusqu'à présent des utilisateurs qui ont installé votre app au cours du mois de janvier.

Les **données LTV** permettent de définir la **qualité des utilisateurs** à partir de différentes sources média. L'optimisation d'une campagne dépend des données LTV.

Les deux méthodes sont utiles aux annonceurs, mais à des fins différentes. C'est pourquoi les deux sont disponibles.

* Quelles données pouvez-vous utiliser pour comparer les sources média ?
* Quelles pages et quels rapports pouvez-vous comparer sur AppsFlyer ?
* Comment comparer les données LTV et les données d'activité ?

### L'analogie du train

**Activité** : imaginez que vous regardez un train qui passe. Lorsque le train avance, vous voyez uniquement les actions effectuées par les passagers du train au moment où ils passent devant vous. Il s'agit des données d'activité.

<Image alt="activity_data.jpg" src="https://files.readme.io/70a37d5dc16f0817d137f9011be9af5360bd7c4d2469a8abf9430fe69b2671c3-360002436957.jpg" width="400px" />

**LTV** : imaginez maintenant que vous montez à bord d'un train en tant qu'observateur. Le train est divisé en plusieurs wagons.

* Vous montez à bord d'un wagon avec d'autres passagers à la gare de départ. Ceci est l'installation.
* Pendant le voyage, vous pouvez observer toutes les actions effectuées par les passagers dans le wagon. Vous pouvez observer les actions de tous les passagers de la voiture jusqu'à ce qu'un passager descende du train, c'est une désinstallation.
* Vous ne pouvez pas voir ce que font les passagers dans les autres wagons du train car ils sont montés avant ou après vous. Il s'agit de la LTV.

<Image alt="ltv_data.jpg" src="https://files.readme.io/78925644f263b6d5ea5630a09e0b2155d153ce2c4b3060be5c8d7cb9ba0ce4e6-360002436977.jpg" width="400px" />

## Tableaux de bord AppsFlyer—LTV ou activité ?

Les tableaux de bord permettent aux marketeurs d'optimiser leur trafic non organique. La plupart des tableaux de bord et rapports de la plateforme sont basés sur les données LTV, car les marketers mesurent généralement les performances sur la base de la LTV.

Découvrons quelles données sont des données LTV et lesquelles sont des données d'activité.

<Accordion title="Vue d'ensemble du tableau de bord">

* La vue d'ensemble du tableau de bord indique la LTV.
* Métriques disponibles : points de contact, installations, taux de conversion et revenus LTV
* Graphiques : tendances d'acquisition des utilisateurs, installations, utilisateurs fidèles LTV et revenus LTV

[![](https://files.readme.io/5e9d7025c7d8b3ca11270cabd348cba3ffa166df674548803b84efb4b11ab6ab-115014844503.png)](https://files.readme.io/5e9d7025c7d8b3ca11270cabd348cba3ffa166df674548803b84efb4b11ab6ab-115014844503.png)

Le bas de page de la vue d'ensemble du tableau de bord contient encore plus de données d'évènement, qui sont également des données LTV.

Dans le tableau **Rapport de performances agrégées**, les colonnes suivantes sont toutes des évènements liés aux données LTV :

* Sessions
* Utilisateurs fidèles (nombre et taux)
* Revenu
* ROI
* ARPU
* Désinstallations (nombre et taux)
* Toutes les colonnes d'évènements in-app

[![](https://files.readme.io/508f2388e5671fe00181a050a7a7cce1064e3a68470fea1b91b89647c76a9e2d-115014673026.png)](https://files.readme.io/508f2388e5671fe00181a050a7a7cce1064e3a68470fea1b91b89647c76a9e2d-115014673026.png)

Le widget **Meilleurs évènements** contient également des données LTV.

</Accordion>

<Accordion title="Tableau de bord des événements">

Toutes les données de cette page, accessibles à partir du widget **Meilleurs évènements** ou du lien **Évènements** dans la barre de gauche, sont des données d’évènements LTV. Pour une explication plus détaillée de la page d'évènements, cliquez ici.

[![](https://files.readme.io/5d144a104c8bb0bdd287e916534f619fc2f8ad76f895803f61b69dc36a581fd2-115014673046.png)](https://files.readme.io/5d144a104c8bb0bdd287e916534f619fc2f8ad76f895803f61b69dc36a581fd2-115014673046.png)

</Accordion>

<Accordion title="Tableau de bord de retargeting">

Le <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide#retargeting-dashboard">tableau de bord de retargeting</Anchor> fonctionne conjointement avec la vue d'ensemble du tableau de bord. Les données d'évènement affichées sont des **données LTV** et se rapportent aux réattributions et réengagements survenant au cours de la période.

</Accordion>

<Accordion title="Rapports de rétention et de cohorte">

Même si vous sélectionnez un seul jour de données de rétention, vous pouvez récupérer plusieurs jours ou semaines de données de sessions pertinentes uniquement pour les installations de ce jour, ce qui est un excellent KPI pour la qualité utilisateur. LTV classique. Cliquez sur les liens pour obtenir une description plus détaillée du rapport de rétention et du <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard">rapport de cohorte</Anchor>.

[![](https://files.readme.io/e72add1e5b77439f0ba744cbf739846e4de8a03f3923dfd9b256c50b526402ae-115014673066.png)](https://files.readme.io/e72add1e5b77439f0ba744cbf739846e4de8a03f3923dfd9b256c50b526402ae-115014673066.png)

Le rapport de cohorte est similaire au rapport de rétention, mais comporte plus que les métriques de sessions. Ces métriques, tels que le revenu, les sessions et les évènements in-app, sont des données LTV.

[![CohortForLTV_us-en.jpg](https://support.appsflyer.com/hc/article_attachments/360008407377/CohortForLTV_us-en.jpg)](https://support.appsflyer.com/hc/article_attachments/360008407377/CohortForLTV_us-en.jpg)

</Accordion>

<Accordion title="Tableau de bord d'activité">

Les données d'évènement du Tableau de <Anchor target="_blank" href="/marketers/fr/docs/activity-dashboard">bord d'activité</Anchor> sont basées sur les sessions et les revenus et sont **la base de l'activité**. Elles sont relatives chronologiquement à tous les utilisateurs d'app actifs durant une période donnée.

[![Activity_us-en.jpg](https://support.appsflyer.com/hc/article_attachments/360008510978/Activity_us-en.jpg)](https://support.appsflyer.com/hc/article_attachments/360008510978/Activity_us-en.jpg)

</Accordion>

<Accordion title="Rapports téléchargeables">

* <Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview">**Rapports de performance**</Anchor> : comme pour le tableau Rapport de performance agrégé de la Vue d'ensemble du tableau de bord, ces rapports de performance sont des données LTV.
* **<Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">Rapports de données brutes</Anchor> :** Les rapports de données brutes sont la principale source de données d'activité. Ces rapports de type installations, événements in-app, postbacks et désinstallations sont définis et séquencés par date d'activité.

#### Rapports de retargeting

Les rapports de retargeting, y compris les rapports sur les performances et les données brutes, sont similaires aux rapports UA et sont disponibles. Dans le cas des rapports de données brutes, les éléments suivants sont disponibles :

* événements in-app de retargeting
* Conversions (réattributions, réengagements)

#### Rapports sur la prévention de la fraude

Le rapport sur les évènements in-app rejetés correspond à des données d'**activité**.

</Accordion>

<Accordion title="Widgets du tableau de bord personnalisé">

Conjointement avec la page de présentation du tableau de bord, toutes les données d'évènements de la page <Anchor target="_blank" href="/marketers/fr/docs/custom-dashboards">Tableau de bord personnalisé</Anchor> sont des **données LTV**.

[![](https://files.readme.io/c9ee8de9a03e8ed64ec305b6de3ab235f7b1ca6a996478837d4c4d323ed911dc-115014844623.png)](https://files.readme.io/c9ee8de9a03e8ed64ec305b6de3ab235f7b1ca6a996478837d4c4d323ed911dc-115014844623.png)

</Accordion>

<Accordion title="Tableau croisé dynamique et API principale">

Le <Anchor target="_blank" href="/marketers/fr/docs/pivot-table-user-metrics">tableau croisé dynamique AppsFlyer</Anchor> repose sur l'<Anchor target="_blank" href="/marketers/fr/docs/master-api-user-acquisition-metrics-via-api">API principale</Anchor>, qui peut fournir les données provenant de 3 groupes différents : LTV, activité et rétention. Lorsque vous créez une nouvelle URL d'API principale ou une nouvelle vue de tableau croisé dynamique, vous choisissez les KPI d'événement que vous souhaitez associer à la LTV, à l'activité ou aux deux.

</Accordion>

<Accordion title="Tableau de bord Protect360">

Protect360 offre un tableau de bord pour les installations, et un pour les événements in-app.

Les données du tableau de bord des installations donnent des éléments basés sur la LTV à propos des installations frauduleuses, bloquées en temps réel et identifiées post attribution. Vous pouvez approfondir encore l'examen des événements frauduleux à l'aide des options de filtrage et de regroupement.

Les données du tableau de bord des événements in-app (CPA) donnent des informations basées sur l'activité concernant les événements in-app frauduleux, bloqués en temps réel et identifiés post attribution.  Vous pouvez approfondir encore l'examen des cas frauduleux à l'aide des options de filtrage et de regroupement.

</Accordion>

## Résumé des sources de données

Le tableau suivant récapitule quels types de données d'évènements sont disponibles sur les différents rapports et pages du tableau de bord d'AppsFlyer.

| Source | LTV | ACTIVITÉ |
| --- | --- | --- |
| Vue d'ensemble du tableau de bord | Y | N |
| Tableau de bord des événements | Y | N |
| Tableau de bord de retargeting | Y | N |
| Rapport de rétention | Y | N |
| Rapport de cohorte | Y | N |
| Tableau de bord d'activité | N | Y |
| Rapports de performances | Y | N |
| Rapports de données brutes | N | Y |
| Rapports de retargeting | Y | Y |
| Rapports sur la prévention de la fraude | N | Y |
| API push | N | Y |
| API principale — KPI de performance de campagne | Y | Y |
| Tableau Pivot | Y | Y |
| Installations Protect360 | Y | N |
| Évènement in-app Protect360 | N | Y |

### Utiliser le tableau concernant les sources de données

Si vous souhaitez comparer des données provenant de différentes sections de la plate-forme, assurez-vous d'utiliser des rapports qui sont soit en LTV, soit basés sur l'activité

## Comparer les sources de données

### Comparer les données d'AppsFlyer aux sources de données externes

**La grande majorité des sources de données**, notamment les **données d'activité d'affichage** de Google et d'Apple, ne sont pas des données LTV.

Par conséquent, **pour comparer les données des sources externes à celles d'AppsFlyer, vous utiliserez généralement les données d'activité d'AppsFlyer,** disponibles dans les rapports de données brutes.

Notez que Facebook offre des données LTV partielles, limitées à 28 jours après l'installation.

### Comparer les données LTV et d'activité sur le tableau de bord d'AppsFlyer

Il existe deux différences entre les données LTV et les données d'activité si l'on prend la même période. Les différences sont les suivantes :

* Les données d'activité incluent les évènements des **installations survenus avant** la période.
* Les données LTV incluent les **évènements survenus après** la période.

Pour pouvoir comparer correctement les deux types de données, nous devons neutraliser ces différences. Cela peut être fait en récupérant les données LTV des données d'activité ou inversement.

> 📘 **Remarque**
>
> Il est possible que des différences mineures existent encore entre des sources similaires en raison des différences de délai de génération des rapports.

### Récupérer des données LTV à partir des données brutes d'activité

1. Allez sur la page **Données d'exportation**
2. Choisissez le **jour en cours comme dernier jour** de la période (différence B résolue)
3. Téléchargez le rapport de données brutes des évènements in-app.
4. Utilisez la colonne **Temps d'installation** pour filtrer les installations avant le premier jour de la période (différence A résolue)

> 📘 **Remarque**
>
> Tandis que les données d'activité restent constantes dans le temps, les données LTV changent lorsque les utilisateurs existants exécutent de nouveaux évènements in-app. Les données LTV que vous voyez aujourd'hui peuvent être différentes demain pour la même période.

### Récupérer des données d'activité à partir des données LTV

Pour comparer la page de présentation basée sur les données LTV à une source externe, qui est basée sur les données d'activité, vous devez éliminer les deux différences.

Cela n'est possible qu'en :

1. **Sélectionnant des sources qui ont commencé à envoyer des installations au cours de la période spécifiée sur AppsFlyer** (différence 1 résolue).  
    Cela garantit que les données d'activité n'incluent pas les évènements exécutés au cours de la période appartenant aux installations antérieures à la période.
2. **Définissant le jour en cours comme dernier jour de la période** (différence 2 résolue).  
    Cela garantit que les données LTV n'incluent pas les évènements exécutés après la période appartenant aux installations survenues au cours de la période.

## Conclusion

Lorsque vous comparez deux sources de données, qu'elles se trouvent toutes les deux dans AppsFlyer ou qu'une seule s'y trouve, assurez-vous de comparez les données d'activité aux données d'activité et les données LTV aux données LTV.