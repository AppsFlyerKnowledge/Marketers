---
title: Présentation des rapports agrégés et analytiques
metadata:
  keywords:
    - Agencies
    - Ad Networks
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
    - Ad Networks
  created_at: '2020-02-04T09:38:14Z'
  edited_at: '2023-10-27T11:13:07Z'
  id: 360005437257
  locale: fr
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/fr/articles/360005437257
---
> **En bref :** description et différences entre les rapports d'attribution agrégés et analytiques, les outils et les API disponibles.

<div id="aggregated-and-analytics-performance-reporting-overview" />

## Rapports de performance agrégés et analytiques—outils et rapports

Les outils d'agrégation et d'analyse proposés sur la plateforme permettent aux annonceurs de mesurer différentes métriques pour évaluer les performances de leurs apps, campagnes et utilisateurs.

Les outils varient dans la manière dont ils présentent et traitent les données. Par exemple, le tableau de bord Général fournit les mesures lifetime des campagnes (LTV), tandis que Cohorte permet d'analyser l'engagement des utilisateurs au fil du temps.

Les outils détaillés dans cet article concernent les données qui peuvent être exportées depuis la plate-forme. Utilisez le tableau de comparaison suivant pour découvrir leur fonction principale et les différences entre chacun.

<div id="toolapi-comparison" />

<Accordion title="Différences entre les méthodes de reporting">

Le tableau suivant décrit les méthodes de reporting et tableaux de bord permettant d'obtenir des données agrégées.

**[Téléchargez le tableau au format CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSICicxcvD0996RT59fTLDJvdGUKxqPqr47f5SMD8BmsbZtrWIoxRxJEo7tAXTBBmnIbiH097VtK6L9/pub?output=xlsx) pour voir les champs contenant les caractéristiques et limitations afin de vous aider à comparer les différentes méthodes de reporting.**

Les champs des caractéristiques du fichier CSV que vous téléchargez sont les suivants :

* <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support">Actualisation des données</Anchor> : période de temps entre le moment où l'événement se produit et la mise à disposition des données via reporting.
* <Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV/activité</Anchor>: définit si les données sont de type LTV ou activité.
* <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">Retargeting</Anchor>: définir si les données de retargeting (réengagement et réattribution) sont affichées ou non.
* <Anchor target="_blank" href="/marketers/fr/docs/measure-reinstalls#attributed-to-the-first-install">Attribution des événements de réinstallation à la première installation</Anchor>: définit si les événements survenus après une réinstallation peuvent être attribués à l'installation initiale.
* <Anchor target="_blank" href="/partners/fr/docs/about-agency-accounts#transparence-de-lagence">Transparence de l'agence</Anchor> : définit si les marketeurs peuvent connaître l'identité de la source média d'origine pour le trafic provenant d'une agence
* <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles">Fuseau horaire</Anchor> : définit le fuseau horaire (UTC ou sélectionné par l'app) utilisé pour afficher les données.
* <Anchor target="_blank" href="/marketers/fr/docs/measure-reinstalls#unattributed-organic-inapps">Événements non attribués</Anchor>: définit si les événements non attribués après une réinstallation sont affichés ou non.
* <Anchor target="_blank" href="/marketers/fr/docs/campaign-name-changes?">Changement de nom de campagne</Anchor> : définit la possibilité de modifier le nom des campagnes sans créer de doublons.

| Méthode de reporting | Description |
| --- | --- |
| Vue d'ensemble du tableau de bord | Durée-vie (LTV) des utilisateurs qui installent, se réengagent ou sont réattribués durant la période sélectionnée. |
| <Anchor target="_blank" href="/marketers/fr/docs/master-api-user-acquisition-metrics-via-api">API principale</Anchor>  <br />(Fonctionnalité Premium) | Sélection de LTV, activité, rétention, cohorte et des KPI de performance des campagnes Protect360 via API, au format CSV ou JSON. |
| <Anchor target="_blank" href="/marketers/fr/docs/pull-api-aggregate-data">API Pull - rapports agrégés</Anchor> | Durée-vie (LTV) des utilisateurs qui installent, se réengagent ou sont réattribués au format CSV. Les données UA et de retargeting sont distinctes ; il n'existe pas d'option pour les réunir. |
| <Anchor target="_blank" href="/marketers/fr/docs/aggregated-data-export-page">Page d'exportation des données - rapports agrégés</Anchor> | Durée-vie (LTV) des utilisateurs qui installent, se réengagent ou sont réattribués au format CSV. Les données UA et de retargeting sont distinctes ; il n'existe pas d'option pour les réunir. |
| <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Présentation de SKAN</Anchor> | Métriques rapportées via postbacks iOS SKAN, et points de données supplémentaires durant les fenêtres de mesure initiales de l'utilisateur. |
| <Anchor target="_blank" href="/marketers/fr/docs/skan-aggregated-performance-report-api">API de données agrégées API SKAN</Anchor> | Métriques rapportées via postbacks iOS SKAN, et points de données supplémentaires durant les fenêtres de mesure initiales de l'utilisateur. |
| <Anchor target="_blank" href="/marketers/fr/docs/protect360-dashboard">Tableau de bord Protect360</Anchor> | Mesures et informations relatives au trafic frauduleux.  <br />Données basées sur la LTV pour les installations, et données basées sur l'activité pour les événements in-app. |
| <Anchor target="_blank" href="/marketers/fr/docs/activity-dashboard">Tableau de bord d'activité</Anchor> | Activité de l'application, engagement et mesures in-app sur la période sélectionnée. |
| Tableau de bord des événements | Mesure des performances des événements in-app sur l'ensemble des sources média, sur la base des données LTV des utilisateurs qui ont installé l'app au cours de la période sélectionnée. |
| Tableau de bord de rétention | Mesures de l'engagement de l'utilisateur unique (session) pour chaque jour qui suit l'installation. |
| <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard">Tableau de bord des cohortes</Anchor> | Diverses mesures de l'utilisateur pour chaque jour qui suit l'installation. |
| <Anchor target="_blank" href="/marketers/fr/docs/cohort-api">API de Cohorte</Anchor>  <br />(Fonctionnalité Premium) | Diverses mesures de l'utilisateur pour chaque jour qui suit l'installation. |
| <Anchor target="_blank" href="/marketers/fr/docs/cohort-analytics-via-data-locker">Cohort Data Locker</Anchor>  <br />(Fonctionnalité Premium) | Diverses mesures de l'utilisateur pour chaque jour qui suit l'installation. |
| <Anchor target="_blank" href="/marketers/fr/docs/custom-dashboards">Tableau de bord personnalisé</Anchor> | Tableau de bord personnalisé avec mesures d'acquisition d'utilisateurs LTV. |
| <Anchor target="_blank" href="/marketers/fr/docs/pivot-table-user-metrics">Rapports croisés</Anchor>  <br />(Fonctionnalité Premium) | Sélection de LTV, activité, rétention et KPI de performance de campagne Protect360, dans le tableau de bord ou via CSV. |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports">ETL des coûts</Anchor> | Données sur les coûts des campagnes avec la plus haute granularité disponible, par source de média. |
| Rapports de consommation | L'ensemble de toutes les fonctionnalités basées sur la consommation de AppsFlyer qui impactent les contrats pendant les cycles de facturation. |

</Accordion>

<div id="cohort-flavors" />

<Accordion title="Versions de cohorte">

Différentes *versions* de cohorte sont disponibles : <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard">tableau de bord de cohorte</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/cohort-api">API de cohorte</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/cohort-analytics-via-data-locker">analyse de cohorte via Data Locker.</Anchor> Le tableau ci-dessous indique les propriétés de chacune.

| Caractéristiques | Analyse des cohortes dans Data Locker | Tableau de bord des cohortes | API de cohorte |
| --- | --- | --- | --- |
| App unique ou multiple | Multiple Les données sont regroupées par app dans un fichier unique, ou réparties dans des fichiers correspondant à chaque application. | Multiple Performances réunies ou regroupées par options d'application. | Unique |
| Regroupements | Hiérarchie complète des campagnes et noms des événements. Environ 20 groupes | 4 groupes | 7 groupes |
| Métriques disponibles | Toutes les métriques | 1 métrique sélectionnable et 4 métriques fixes par vue | 1 métrique sélectionnable et 4 métriques fixes par appel |
| Jours après l'attribution disponibles (jours de cohorte) | 365 | 180 | 180 |
| Limites de l'exportation des données | L'ensemble des données est disponible | Téléchargement manuel et paramètres | Taux et taille de réponse limités |
| Demande personnalisable | Non | Oui | Oui |

</Accordion>

<div id="user-journey-reports" />

### Rapports de parcours utilisateur

* Les rapports détaillés sont disponibles depuis la page Données d'exportation ou bien à l'aide de l'API Pull agrégée.
* Ils sont en <Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Durée lifetime (LTV)</Anchor> , la plage de dates du reporting découle donc de la date d'attribution, soit :
  * Date d'installation pour les rapports AU et Protect360
  * Date de réattribution ou de réengagement dans le cas de rapports de retargeting
* La première date de rapport disponible correspond au jour de la première installation de l'app.

<div id="ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users" />

<Accordion title="Rapports de données agrégées LTV AU contenant des utilisateurs organiques et non-organiques">

<table><tbody><tr><th>Nom du rapport</th><th>Regroupés par</th></tr><tr><td>Partenaires (sources média)</td><td>Agence, source média, campagne</td></tr><tr><td>Partenaires par date</td><td>Date, agence, source média, campagne</td></tr><tr><td>Activité quotidienne</td><td>Date, agence, source média, campagne</td></tr><tr><td>Géo</td><td>Pays, agence, source média, campagne</td></tr><tr><td>Géo par date</td><td>Date, pays, agence, source média, campagne</td></tr><tr><td>KPI d'attribution post vue</td><td><p><a href="./pull-api-aggregate-data" target="_blank">Les rapports VTA sont disponibles via API Pull</a></p></td></tr><tr><td colspan="2"> <strong>Remarque</strong> : si Meta Ads est la <em>source média</em> sélectionnée, des colonnes supplémentaires sont alors incluses ( ID de publicité, nom de publicité, ID d'ensemble de publicités, nom d'ensemble de publicités)</td></tr></tbody></table>

Les champs de date dans les fichiers CSV sont au format aaaa-mm-jj. Lorsque vous ouvrez un fichier CSV dans Excel, les champs de date sont formatés en fonction des paramètres de date et d'heure de votre ordinateur. Assurez-vous de sélectionner le format de date approprié dans <Anchor target="_blank" href="https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows">Excel</Anchor>.

<div id="examples-of-aggregate-reports" />

#### Exemples de rapports agrégés

[Exemples de rapports dans une feuille de calcul](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmzRons779Dk5QWVoPsOF8E7yJLwNPB1IF87shZr6rcMJLjszlSNIbAMVcdeQLysr8Bc4QAby5QB4u/pub?output=xlsx)

<div id="fields-in-ua-aggregate-reports" />

#### Champs présents dans les rapports agrégés AU

<table><thead><tr><th rowspan="2">Champ</th><th rowspan="2">Description</th><th colspan="5"><p><strong>Nom du rapport</strong></p></th></tr><tr><th><p><strong>Partenaire (source média)</strong></p></th><th><p><strong>Partenaire par date</strong></p></th><th><p><strong>Quotidien</strong></p></th><th><p><strong>Géo</strong></p></th><th><p><strong>Géo par date</strong></p></th></tr></thead><tbody><tr><td><p>Pays</p></td><td>Pays d'installation</td><td> </td><td> </td><td> </td><td><p>✓</p></td><td> ✓</td></tr><tr><td><p>Date</p></td><td><p>Date d'attribution</p></td><td> </td><td><p>✓</p></td><td> </td><td> </td><td><p>✓</p></td></tr><tr><td><p>Agence/PMD (af_prt)</p></td><td><p>Nom de l'agence / du partenaire</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Source média (PID)</p></td><td><p>Source média qui draine l'utilisateur (pid = source média)</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Campagne</p></td><td><p>Nom de la campagne</p><p>(c = nom de la campagne)</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Identifiant de la campagne</p></td><td><p>Identifiant de la campagne Meta</p></td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td></tr><tr><td><p>Identifiant de publicité</p></td><td><p>ID du groupe Meta ad ou ID publicitaire</p></td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td></tr><tr><td><p>Nom de publicité</p></td><td><p>Groupe Meta Ad</p></td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td></tr><tr><td><p>Identifiant de l'ensemble de publicités</p></td><td><p>ID d'adset Meta</p></td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td></tr><tr><td><p>Nom d'adset</p></td><td><p>Nom de l'adset Meta</p></td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td><td>Meta ads uniquement</td></tr><tr><td><p>ARPU</p></td><td><p>Revenu moyen par utilisateur</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td>✓</td><td><p>✓</p></td></tr><tr><td><p>eCPI moyen</p></td><td><p>eCPI moyen</p></td><td> </td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>Clics</p></td><td><p>Nombre de clics</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>de l'installation à la première commande</p></td><td><p>Nombre d'installations / nombre de clics</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>CTR</p></td><td><p>Taux post clic</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td></tr><tr><td><p>`{your event name}(utilisateurs uniques)</p></td><td><p>Nombre d'utilisateurs uniques qui ont effectué l'événement</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>{your event name} (compteur d'événements)</p></td><td><p>Compteur d'évènements</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>{your event name}` (ventes en XXX)</p></td><td><p>Ventes d'événements en XXX lorsque XXX est la devise définie pour l'app</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Impressions</p></td><td><p>Nombre d'impressions</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>d'installations</p></td><td><p>nombre d’installations</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>utilisateurs fidèles</p></td><td><p>(par défaut) Utilisateur qui ouvre l'app plus de trois fois</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Utilisateurs fidèles / Installations</p></td><td><p>Taux d'utilisateurs fidèles</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>ROI</p></td><td><p>Retour sur investissement</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>Sessions</p></td><td><ul><li>Nombre d'ouvertures d'app non organiques</li><li>Les sessions organiques et non organiques sont disponibles dans l'analyse de cohorte</li></ul></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td><p>Coût total</p></td><td><p>-</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td> </td><td> </td></tr><tr><td><p>Revenu total</p></td><td><p>Total des revenus générés par la source média et la campagne</p></td><td><p>✓</p></td><td><p>✓</p></td><td> </td><td><p>✓</p></td><td><p>✓</p></td></tr><tr><td colspan="7"><p><strong>Remarque :</strong> Les colonnes indiquant "Meta ads uniquement" sont incluses lorsque les Meta ads sont sélectionnées comme source média unique.</p></td></tr></tbody></table>

</Accordion>

<div id="retargeting" />

<Accordion title="Re-Targeting">

* Les rapports de retargeting recensent les utilisateurs qui ont interagi avec une <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide#retargeting-reports-and-raw-data">campagne de retargeting</Anchor>, puis qui ont effectué une action de réengagement ou de réattribution.
* Dans les rapports de retargeting, il n'existe pas de distinction entre les utilisateurs organiques et non organiques.
* Pour obtenir des rapports de retargeting via API Pull, ajoutez le paramètre *&reattr=true* aux URI des rapports de performance.

<div id="aggregate-ltv-retargeting-reports" />

#### Rapports de retargeting LTV agrégés

| Nom du rapport | Regroupés par |
| --- | --- |
| Partenaires (sources média) | Agence, source média, campagne |
| Partenaires par date | Date, agence, source média, campagne |
| Activité par date | Date, agence, source média, campagne |
| Pays | Pays, agence, source média, campagne |
| Pays par date | Date, pays, agence, source média, campagne |

<div id="aggregate-ltv-retargeting-reports-1" />

#### Rapports de retargeting LTV agrégés

| Champ | Description | Partenaires | Quotidien | Partenaires par date | Géo par date | Géo |
| --- | --- | --- | --- | --- | --- | --- |
| Date | Date de la conversion | - | - | ✓ | ✓ | - |
| Pays |  | - | ✓ |  | ✓ | ✓ |
| Agence/PMD (af\_prt) | Nom de l'agence / du partenaire | ✓ | ✓ | ✓ | ✓ | ✓ |
| Source média (PID) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Campagne (c) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Clics |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversions |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Types de conversion | Réattribution ou réengagement | ✓ | ✓ | ✓ | ✓ | ✓ |
| de l'installation à la première commande | Conversions / clics | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sessions |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| utilisateurs fidèles |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Utilisateurs fidèles / Installations |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Coût total |  | - | - | - | - | - |
| eCPI moyen |  | - | - | - | - | - |
| Revenu total |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| ROI |  | - | - | - | - | - |
| ARPU |  | ✓ | ✓ | ✓ | - | ✓ |

</Accordion>

<div id="feature-reports" />

## Rapports de fonctionnalités

<div id="skadnetwork" />

<Accordion title="SKAdNetwork">

<Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#reporting-options">Rapport agrégé SKAdNetwork</Anchor>

</Accordion>

<div id="protect360-blocked-fraud" />

<Accordion title="Fraudes bloquées Protect360">

![](https://theme.zdassets.com/theme_assets/245528/ffbbc473bb0e74b9fb636ed735f69e9af6a25a18.png)

* Les rapports agrégés de fraude bloquée donnent des infos détaillées sur les événements bloqués par <Anchor target="_blank" href="/marketers/fr/docs/protect360-anti-fraud-guide">Protect360</Anchor>.
* Les rapports sont disponibles via API Pull. Ces rapports ne sont pas disponibles via la page des données d'exportation.
* La plage de dates se rapporte à la date d'installation.

<div id="aggregate-protect360-reports-available-via-pull-api" />

#### Les rapports agrégés de Protect360 disponibles via API Pull

| Nom du rapport |
| --- |
| Partenaires (sources média) |
| Partenaires par date |
| Géo |
| Géo par date |
| Rapport de campagne du partenaire |

**Exception :** le motif de blocage **bots** est invoqué même dans le cas où il devrait être **version d'app** ou bien **id utilisateur du client manquant**.

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/configuring-meta-campaign-management-partners">Configuration des partenaires pour la gestion des campagnes Meta</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">Vue d'ensemble du reporting des données brutes</Anchor>

<div data-zendesk-anchors="aggregated-and-analytics-performance-reporting%E2%80%94tools-and-reports=rapports-de-performance-agr%C3%A9g%C3%A9s-et-analytiquesoutils-et-rapports 01EWA9VQ2HH93525BMK6WN0P6S=rapports-de-performance-agr%C3%A9g%C3%A9s-et-analytiquesoutils-et-rapports 01ED4D7W8B53Q81G7PXQH8ADE2=toolapi-comparison h_01HDNYFR9KBX2KP75K1FAZC2Q7=cohort-flavors user-journey-reports=rapports-de-parcours-utilisateur 01ED4D7W8CVAQ9V2GCEX1G6KD7=rapports-de-parcours-utilisateur h_01HDNYFR9KBMWAFXDNNJN8VA2X=ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users examples-of-aggregate-reports=exemples-de-rapports-agr%C3%A9g%C3%A9s 01ED4D7W8C3ZNBYR3CMHJF3QSE=exemples-de-rapports-agr%C3%A9g%C3%A9s fields-in-ua-aggregate-reports=champs-pr%C3%A9sents-dans-les-rapports-agr%C3%A9g%C3%A9s-au h_01HDNYFR9KTQ7ZF35C7E7M7AF1=champs-pr%C3%A9sents-dans-les-rapports-agr%C3%A9g%C3%A9s-au 01ED4D7W8FCW3QTV08MWWA8FDT=retargeting aggregate-ltv-retargeting-reports=rapports-de-retargeting-ltv-agr%C3%A9g%C3%A9s h_01HDNYFR9MSJWCP3JA4M1WXN1H=rapports-de-retargeting-ltv-agr%C3%A9g%C3%A9s aggregate-ltv-retargeting-reports::b2093953=rapports-de-retargeting-ltv-agr%C3%A9g%C3%A9s-1 h_01HDNYFR9MSK9VQQ0Q889Z55TN=rapports-de-retargeting-ltv-agr%C3%A9g%C3%A9s-1 feature-reports=rapports-de-fonctionnalit%C3%A9s h_01HDNYFR9MYXVZ5BA9FDZ6D82M=rapports-de-fonctionnalit%C3%A9s 01ED4D7W8CBH7Q8D31VX5313WP=skadnetwork protect360%E2%80%94blocked-fraud=protect360-blocked-fraud h_01HDNYFR9MJNKGR7XFCACVP6KT=protect360-blocked-fraud aggregate-protect360-reports-available-via-pull-api=les-rapports-agr%C3%A9g%C3%A9s-de-protect360-disponibles-via-api-pull h_01HDNYFR9MSZ9K8F283J0WBHCZ=les-rapports-agr%C3%A9g%C3%A9s-de-protect360-disponibles-via-api-pull h_01HDNYYJXVY9XHX87K06NXYQNS=%C3%A0-consulter-%C3%A9galement" />
