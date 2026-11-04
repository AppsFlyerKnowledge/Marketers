---
title: Tableau de bord Protect360
metadata:
  keywords:
    - dashboard
    - Advertisers
    - Protect360
    - protect 360
    - '360'
    - P360
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-08-11T09:58:07Z'
  edited_at: '2024-10-23T11:41:51Z'
  id: 360011793077
  locale: fr
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/fr/articles/360011793077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** Le tableau de bord Protect360 contient les informations relatives au trafic frauduleux et aux installations bloquées suite aux règles de validation.

[![p360_dashboard_main.png](https://support.appsflyer.com/hc/article_attachments/5218491552273)](https://support.appsflyer.com/hc/article_attachments/5218491552273)

<div id="about-protect360-dashboard" />

## À propos du tableau de bord Protect360

Le tableau de bord Protect360 :

* Affiche des données agrégées concernant la fraude au niveau du compte.
* Propose deux types d’affichage :
  * Les installations (CPI)
  * Les événements in-app (CPA)
* Sépare les fraudes en différentes catégories, ce qui inclut :
  * Les fausses installations et installations détournées
  * La fraude bloquée en temps réel et la fraude repérée après l’attribution.
  * La fraude à l'UA par et les campagnes de retargeting
* Permet de détailler les événements frauduleux avec les options de filtrage et de regroupement.

Pour consulter le tableau de bord Protect360, dans AppsFlyer, rendez-vous dans **Tableau de bord** > **Protect360.** 

<div id="filters-and-groupings" />

<Accordion title="Filtres et regroupements">

**Fenêtre Filtre et regroupements**

[![p360_filters_2.png](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)

Ces options de filtres et de regroupement sont disponibles :

* Filtres de base :
  * Nom de l'app
  * Type de la source : Non-organique et/ou organique
  * Source média
  * Géo
  * Période (<Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#protect360-dashboard">cf le guide sur les fuseaux horaires</Anchor>)
  * Type d'attribution : Installations, réattributions et/ou ré-engagements
  * [Événements payables](/docs/protect360-dashboard#payable-events) (disponible dans le tableau de bord des événements in-app)
* Filtres étendus - cliquez sur la flèche bleue, à droite du sélecteur de date :
  * Agences
  * Campagnes
  * Canaux
* Options de regroupement - vous pouvez choisir différentes dimensions pour regrouper les données de la fraude et obtenir des informations précises :
  * **Application :** compare le montant total de la fraude entre chacune de vos apps.
  * **Source média** (par défaut) : compare les fraudes identifiées pour chacune des sources média utilisées par vos apps.
  * Source Media / Campagne compare les fraudes identifiées dans l’ensemble de vos campagnes entre toutes les sources média utilisées par vos apps.
  * **Source média + ID du site** : compare la fraude pour tous les éditeurs (ID de site) entre toutes les sources média utilisées par vos apps.
  * **Source média + ID du site + Campagne** : compare la fraude identifiée chez tous les éditeurs (ID de site) entre toutes les sources média utilisées par vos apps, et affiche les noms de campagne concernées.
  * **Source média + Géo** (disponible dans le tableau de bord des événements in-app) : compare la fraude identifiée dans chacune des sources média utilisées par vos apps, et indique le pays concerné
  * **Source média + Type d'attribution**: compare la fraude identifiée entre chacune de vos sources média, pour le type d'attribution sélectionné (installations, réattributions et/ou ré-engagements)
  * **Geo**: compare la fraude identifiée entre chacun des pays

</Accordion>

<div id="installs-dashboard" />

## Tableau de bord des installations

Le tableau de bord des installations affiche les données de LTV, c'est-à-dire les données des installations, réattributions et ré-engagements qui ont eu lieu pendant la période que vous avez définie.

Les fonctionnalités du tableau de bord sont détaillées dans les sections suivantes.

<div id="installs-headline-metrics" />

<Accordion title="Installations — métriques principales">

Les métriques principales vous permettent d’afficher :

* L’estimation des économies
* Le nombre total d'installations frauduleuses
* Le nombre d'événements frauduleux (in-app)
* Les anomalies

Pour chaque KPI, il existe un pourcentage. Cette valeur indique l'évolution du KPI sur une durée identique mais au cours de la période précédente. Exemple : comparaison entre la semaine en cours et la semaine précédente, ou entre un même nombre de jours sur deux périodes adjacentes : si on observe une augmentation de X % des économies estimées, cela signifie que la période identique précédente a eu - X %d'installations, de réattributions et de ré-engagements frauduleux.

**Estimation des économies**

[![](https://support.appsflyer.com/hc/article_attachments/4403139246993)](https://support.appsflyer.com/hc/article_attachments/4403139246993)

Métriques des économies estimées :

* Affiche la valeur de la fraude bloquée en temps réel ou en post-attribution, qui représente ce que vous devrez régler aux réseaux publicitaires.
* Utilise la formule : Économies estimées = nombre d'installations bloquées X eCPI moyen de l'app.
* Ne fonctionne pas pour le trafic organique.

Pour plus de détails sur le mode de calcul de cette valeur, lisez cette <Anchor target="_blank" href="/marketers/fr/docs/protect360-anti-fraud-guide#faq">FAQ</Anchor>.

**Attributions frauduleuses identifiées**

[![](https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png)](https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png)

Le total des fraudes identifiées indique les montants suivants :

* Les installations, réattributions et ré-engagements frauduleux bloqués en temps réel, quel que soit la raison du blocage.
* Installations, réattributions et ré-engagements identifiés comme frauduleux après l'attribution.

**Événements in-app bloqués**

[![](https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png)](https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png)

Les métriques des événements in-app bloqués affichent le nombre d'événements in-app bloqués par AppsFlyer. Les évènements peuvent avoir été bloqués parce qu'ils appartiennent à des installations bloquées, ou parce qu'ils sont marqués comme événements suspects après l’attribution.

</Accordion>

<div id="installs-charts" />

<Accordion title="Installations— diagrammes">

<div id="identified-fraud-trend-chart" />

#### Tableau des tendance de la fraude identifiée

Le tableau des tendances de la fraude identifiée indique le nombre quotidien d'installations, de réattributions et de ré-engagements frauduleux, réparti par l’une de ces catégories :

* **Type de détection** : installations bloquées en temps réel et installations identifiées comme frauduleuses après l’attribution.
* **Type d'attribution** : Installations, réattributions et ré-engagements.
* **Type de source :** Non-organique et organique

Les résultats s'affichent sous la forme d'un graphique ou d'un diagramme en bâton.

<div id="hijacked-installs-attribution-correction-chart" />

#### Diagramme de correction de l'attribution des installations détournées

Le diagramme des corrections d'attribution des installations détournées affiche les sources média qui ont tenté de s'attribuer des installations, réattributions ou ré-engagements, ainsi que les dernières sources valides engagées.

Vous pouvez :

* Filtrer par attributions détournées identifiées en temps réel, post-attribution ou par attributions identifiées via une règle de validation.
* Définir quelle attribution de source valide est corrigée, ou depuis quelle attribution de source détournée la correction est faite.
* Afficher le diagramme sous forme de tableau et télécharger les données au format CSV.

**Remarque :**

* Seuls les annonceurs peuvent accéder à ce tableau. Les agences et les ad networks n'y ont pas accès.
* Lorsque les détournements sont bloqués en temps réel, les attributions correctes s'affichent dans les tableaux de bord et dans les rapports AppsFlyer (pas seulement dans Protect360). Lorsque les détournements sont identifiés en post-attribution, les attributions correctes s'affichent uniquement dans les données brutes Protect360.
* Ce tableau peut afficher la correction **vers l**'organique, mais pas **depuis l**'organique.

<div id="identified-fraud-chart" />

#### Diagramme des fraudes identifiées

Le tableau des fraudes identifiées affiche les types de fraude rencontrés, sous forme de pourcentage. Le classement des différentes fraudes peut se faire par :

* Motif du blocage
* <Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports#niveau-installationcauses-de-blocage-des-installations-frauduleuses">Sous-motif du blocage</Anchor>
* Source média
* Campagne
* Géo
* App

</Accordion>

<div id="installs-table" />

<Accordion title="Installations—tableau">

<div id="identified-fraud-breakdown" />

#### Répartition des fraudes identifiées

Le tableau de **répartition des fraudes identifiées** affiche les données suivantes :

* Fraude bloquée en temps réel
* Fraude identifiée et marquée comme fraude après l’attribution
* Autres indices d’une fraude par source média

Le tableau présente un aperçu global, cf image suivante.

[![p360_main_table.png](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)

Structure du tableau dynamique :

* Vous permet de cliquer sur le bouton de configuration du tableau pour ajouter ou supprimer des colonnes au tableau.  
  Si vous apportez des modifications au tableau, veillez ensuite à bien cliquer sur **Enregistrer**.
* Correspond à un utilisateur, chaque utilisateur du compte ayant accès à Protect360 peut donc personnaliser la structure de son tableau. Voir [les différentes options du tableau](/docs/protect360-dashboard#options-supplémentaires-du-tableau).

[![edit_table.jpg](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)

<div id="content-of-the-identified-fraud-breakdown-table" />

#### Contenu du tableau de répartition des fraudes identifiées

| Colonne du tableau | Description |
| --- | --- |
| Regroupements | <ul><li>[Par default] Le tableau et le tableau de bord sont regroupés par source média.</li><li>Lorsque vous sélectionnez une source média spécifique, le regroupement se fait automatiquement par source média et par ID de site.</li><li>Les regroupements facultatifs incluent Campagne, GEO, Canal, Agence, Agence + Source Média, qui peuvent être combinés.</li><li>Si vous sélectionnez un regroupement dont les dimensions s’appliquent uniquement au trafic non organique, le tableau indiquera N/A pour les sources média organiques.</li></ul> |
| **Attributions** | **Répartition principale des installations bloquées et des installations frauduleuses post-attribution.** |
| Total (A) | <ul><li>Nombre total d'installations = installations normales (non frauduleuses) + installations bloquées</li><li>Les installations normales sont disponibles par source média (non organique) dans le tableau de bord général.</li></ul> |
| Bloqué (B) | <ul><li>Nombre total d'installations bloquées.</li><li>[Par défaut] Le tableau est trié par ordre décroissant en fonction de ce KPI.</li></ul> |
| % bloqué (B/A) | Installations bloquées / nombre total d'installations |
| Post-attribution (C) | Installations identifiées frauduleuses en post-attribution. |
| % en post-attribution (C/A) | Installations post-attribution / nombre total d'installations |
| Nombre total d'installations frauduleuses (D) | Installations frauduleuses, bloquées en temps réel ou identifiées comme frauduleuses en post-attribution. |
| % d'installations frauduleuses (D/A) | Installations frauduleuses / Nombre total d'installations |
| **Répartition de la fraude par type d'attribution** | **Les types d'attribution des installations frauduleuses, classées en fonction des installations, réattributions et ré-engagements.** |
| Installations | La fraude provient d'une campagne UA |
| Ré-attributions | La fraude provient d'une campagne de retargeting qui a généré une installation. |
| Ré-engagements | La fraude provient d'une campagne de retargeting qui a généré un ré-engagement. |
| **Faux** | **Les installations ou réattributions frauduleuses qui imitent une véritable activité de l'utilisateur, classées par blocage en temps réel et post-attribution.** |
| Blocage en temps réel | Fausses installations bloquées en temps réel. |
| Fraude post-attribution | Fausses installations identifiées comme fraude en post-attribution. |
| **Détourné** | **Derniers clics frauduleux ayant usurpé une activité réelle d'utilisateur - divisés par les blocages en temps réel et en post-attribution.** |
| Blocage en temps réel | Installations détournées bloquées en temps réel |
| Fraude post-attribution | Installations détournées identifiées comme fraude en post-attribution |
| **Règles de validation** | **Installations répondant aux conditions des règles de validation.** |
| Installations bloquées | Les installations bloquées par les règles de validation. |
| Attribution bloquée | Modifications d'attribution des installations dues aux règles de validation. |
| **Répartition des blocages des fausses installations** | **Répartition des fausses installations frauduleuses bloquées et en post-attribution, généralement produites par algorithme.** |
| Liste des ID de site bloqués | Installations bloquées car Protect360 a classé le SiteID dans la liste des sites bloqués. |
| Liste de blocage des ID de site post-attribution | Installations marquées comme frauduleuses car Protect360 a classé le SiteID dans liste de blocage. |
| Bots bloqués | Tentatives d'installations effectuées par des bots qui ont été bloquées. |
| Bots en post-attribution | Installations marquées comme frauduleuses car identifiées comme activité de bots en post-attribution |
| Anomalies comportementales bloquées | Installations bloquées en raison d'aberrations comportementales, c'est à dire de sessions ou performances d'événements in-app anormales pour un utilisateur. |
| Anomalies comportementales en post-attribution | Installations marquées comme frauduleuses en raison d'anomalies comportementales en post-attribution. |
| Validation des installations bloquées | Nombre total d'installations bloquées en raison du refus de validation du store. |
| **Répartition des installations détournées bloquées** | **Répartition des derniers clics frauduleux visant à voler l'attribution de véritables installations aux applications utilisateur** |
| Détournement d'installations bloquées | Détournement d'installations bloquées de la source. |
| Détournement d'installations en post-attribution | Détournement d'installations marquées comme frauduleuses en post-attribution. |
| Anomalies CTIT bloquées | Installations bloquées en raison d'anomalies CTIT. |
| Anomalies CTIT en post-attribution | Anomalies CTIT marquées comme frauduleuses en post-attribution. |
| Click flooding bloqué | Installations bloquées en raison de click flooding ( fraude visant à envoyer de grands volumes de clics dans l'espoir de fournir au hasard les derniers clics avant une installation ) |
| Click flooding en post-attribution | Installations de click flooding marquées comme frauduleuses en post-attribution. |
| **Clics** | **Clics à partir de la source**<br /><br />Remarque : Tous les types d'attribution doivent être sélectionnés dans la barre des filtres pour que les données de clics s'affichent dans le tableau (dans le cas contraire, elles afficheront N/A). Pensez à sélectionner les filtres en conséquence. |
| Total (E) | Nombre total de clics légitimes et frauduleux reçus de la source |
| Bloqué | Clics bloqués pour cause de fraude (clics plafonnés inclus) |
| Plafonnement | Clics bloqués en raison du dépassement du plafond |
| **Impressions** | **Impressions à partir de la source**<br /><br />**Remarque** : Tous les types d'attribution doivent être sélectionnés dans la barre des filtres pour que les données d'impressions s'affichent dans le tableau (dans le cas contraire, elles afficheront N/A). Pensez à sélectionner les filtres en conséquence. |
| Total | Nombre total d'impressions légitimes et frauduleuses reçues à partir de la source |
| Bloqué | Impressions bloquées pour cause de fraude (clics plafonnés inclus) |
| Plafonnement | Impressions bloquées en raison du dépassement du plafonnement |
| **Évènements in-app** | **Événements in-app à partir de la source**<br /><br />**Remarque :** inclut les événements in-app provenant d'une installation, mais pas ceux issus d'une réattribution ou d'un ré-engagement. |
| Total (G) | Nombre total des événements in-app |
| Bloqué (H) | Événements in-app bloqués |
| % (H/G) | Évènements in-app bloqués / nombre total d'évènements in-app |
| **Indicateurs de ferme d'appareils** | **Signalent une activité liée à une ferme d'appareils, utilisant la fraude par réinitialisation des appareils ou la fraude par LAT.**<br /><br />**Remarque :** inclut les installations et les réattributions, mais pas les ré-engagements. |
| Installations (I) | Installations avec un nouvel ID d'appareil inconnu d'AppsFlyer. |
| % d'installations (I/A) | Nouvelles installations d'appareil / nombre total d'installations |
| % d'utilisateurs fidèles | KPI global qui indique si les utilisateurs de la source sont réels ou factices. |
| **Indicateurs de click flooding** | **Signalent une fraude via click flooding en fonction de taux de conversion ou d'installations anormaux, ou d'un CTIT suspect.** |
| Taux de conversion (%) | Un faible pourcentage comparé au taux de conversion général de l'application indique une fraude de type click flooding<br /><br />**Remarque** : tous les types d'attribution doivent être sélectionnés dans la barre de filtre pour que les données du taux de conversion s'affichent dans le tableau (dans le cas contraire, elles apparaîtront sous la forme N/A). Pensez à sélectionner les filtres en conséquence. |
| % assistances | Un pourcentage élevé comparé aux autres sources média (dans le widget Assistances de la page de présentation) indique une fraude de type click flooding. |
| CTIT > Plus de 60 minutes | Installations, réattributions et ré-engagements lorsque le temps entre le clic et le premier lancement de l'app dépasse 60 minutes. Le calcul n'inclut que les installations dont le CTIT est inférieur à 25 heures (il ne prend donc pas en compte toutes les installations). En général, près de 30 % des premiers lancements d'applications ont lieu plus de 60 minutes après le téléchargement. |
| CTIT > Plus de 5 heures | Installations, réattributions et ré-engagements lorsque le temps entre le clic et le premier lancement de l'app est supérieur à 5 heures. Le calcul n'inclut que les installations dont le CTIT est inférieur à 25 heures (il ne prend donc pas en compte toutes les installations). En général, près de 20 % des premiers lancements d'applications ont lieu plus 5 heures après le téléchargement. |

<div id="additional-table-options" />

#### Options supplémentaires du tableau

* Cliquez sur **Exporter CSV** pour télécharger le tableau sur votre ordinateur au format CSV
* Cliquez sur l'icône *engrenage* pour :
  * Changer l'ordre des colonnes du tableau
  * Ajouter ou supprimer les colonnes décrites ci-dessus
  * Ajouter ou supprimer n'importe lequel des **événements in-app récemment bloqués** dans votre application. Pour chaque événement in-app ajouté, les colonnes suivantes s'affichent :

| Colonne du tableau | Description |
| --- | --- |
| Compteur d'évènements (total) | Nombre d'occurrences bloquées de l'évènement spécifique |
| Utilisateurs uniques | Nombre d'utilisateurs uniques pour lesquels l'évènement spécifique est bloqué |

Notez qu’un taux inhabituel pour l'un de ces KPI n'indiquent pas nécessairement une fraude, en effet de nombreux évènements sont bloqués en raison d'installations frauduleuses post-attribution.

Les données des événements in-app affichées dans le tableau de bord CPI se basent sur la LTV, elles englobent donc tous les événements in-app associés aux installations qui ont lieu durant la période définie.

</Accordion>

<div id="in-app-events-dashboard" />

## Tableau de bord des événements in-app

Le tableau de bord des événements in-app affiche les données basées sur l'activité, c'est-à-dire les données des événements in-app qui ont eu lieu pendant la période que vous avez définie, ainsi que les événements d'installations qui se sont produites avant cette même période.

Les fonctionnalités du tableau de bord sont détaillées dans les sections suivantes.

<div id="inapp-events-headline-metrics" />

<Accordion title="Événements in-app — Métriques principales">

[![](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)

Les métriques principales vous permettent d’afficher :

* Estimation des économies
  * Disponible uniquement si l'option [**Événements payables**](/docs/protect360-dashboard#payable-events) est activée.
  * Dépend des événements payables que vous avez configurés.
* Nombre total d'EIA frauduleux identifiés

</Accordion>

<div id="inapp-events-charts" />

<Accordion title="Événements in-app — Diagrammes">

<div id="fraud-trend-over-time-chart" />

#### **Diagramme des tendances en termes de fraude au fil du temps**

Le diagramme d'évolution de la fraude au fil du temps affiche le nombre d'événements pour chaque jour, répartis comme suit :

* **Temps réel** : blocage en temps réel des événements in-app frauduleux
* Post-attribution Événements frauduleux identifiés après l'attribution
* **Non-frauduleux**

<div id="top-iae-fraud-by-media-source-chart" />

#### **Diagramme des principaux EIA frauduleux par source média**

Les principaux événements in-app frauduleux par source média incluent :

* Les 5 sources média avec le plus grand nombre d'événements in-app frauduleux, classées par ordre décroissant.
* Un graphique pour chaque source média, avec le pourcentage des types d'événements in-app suivants par rapport au nombre total d'événements in-app :
  * **Temps réel** : blocage en temps réel des événements in-app frauduleux
  * Post-attribution Événements frauduleux identifiés après l'attribution
  * **Non-frauduleux**

</Accordion>

<div id="inapp-events-table" />

<Accordion title="Évènements in-app — Tableau">

Le tableau de **Répartition des événements in-app frauduleux** indique les éléments suivants :

* Fraude bloquée en temps réel
* Fraude identifiée et marquée comme fraude après l’attribution
* Autres indices d’une fraude par source média

Le tableau présente un aperçu global, cf image suivante.

[![EIA_fraud_table.jpg](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)

Structure du tableau dynamique :

* Vous permet de cliquer sur le bouton de configuration du tableau pour ajouter ou supprimer des colonnes au tableau.  
  Si vous apportez des modifications au tableau, veillez ensuite à bien cliquer sur **Enregistrer**.
* Correspond à un utilisateur, chaque utilisateur du compte ayant accès à Protect360 peut donc personnaliser la structure de son tableau. Voir [les différentes options du tableau](/docs/protect360-dashboard#installs-table).

[![EIA_table_structure.jpg](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)

<div id="content-of-the-in-app-event-fraud-breakdown-table" />

#### Contenu du tableau de répartition des événements in-app frauduleux

| Colonne du tableau | Description |
| --- | --- |
| Regroupements | <ul><li>[Par default] Le tableau et le tableau de bord sont regroupés par source média.</li><li>Lorsque vous sélectionnez une source média spécifique, le regroupement se fait automatiquement par source média et par ID de site.</li><li>Les regroupements facultatifs incluent Campagne, GEO, Canal, Agence, Agence + Source Média, qui peuvent être combinés.</li></ul> |
| **Événements in-app** | **Répartition principale des EIA bloqués et EIA frauduleux post-attribution.** |
| Total des EIA (A) | <ul><li>EIA total = EIA normaux (non frauduleux) + EIA bloqués + EIA identifiés comme frauduleux post-attribution.</li><li>Les EIA normaux sont affichés par source média (non organique) dans le tableau de bord général.</li></ul> |
| Total des EIA frauduleux (B) | <ul><li>Nombre total d'EIA bloqués + EIA identifiés comme frauduleux post-attribution.</li><li>[Par défaut] Le tableau est trié par ordre décroissant selon ce KPI.</li></ul> |
| Événements frauduleux % (B/A) | EIA frauduleux / EIA total |
| **Blocage en temps réel des faux EIA** | Blocage en temps réel des EIA frauduleux |
| Faux EIA | Faux EIA identifiés comme frauduleux et bloqués en temps réel. |
| Fausses installations | L'installation originale a été identifiée comme étant frauduleuse et bloquée en temps réel. |
| Fausses installations post-attribution | L'installation originale a été identifiée comme fraude post-attribution, et avant l'EIA. |
| **Sauvé d'un détournement en temps réel** | **Les EIA dont l'installation originale a été détournée par une source frauduleuse, mais que AppsFlyer a bien attribués à la dernière source non frauduleuse.** |
| Corrigé en organique | Les installations détournées, dont la dernière source non frauduleuse est organique. |
| Corrigé en source non organique | Les installations détournées dont la dernière source non frauduleuse était une source média non organique. |
| **EIA en post-attribution frauduleux** | **Les événements in-app identifiés comme fraude en post-attribution.** |
| Fausses installations | L'EIA a eu lieu avant que l'installation ne soit identifiée comme une fraude post-attribution. |
| Installations détournées | L'EIA a eu lieu avant que l'installation ne soit identifiée comme détournée, et ne peut être correctement attribué post-attribution. |
| **Règles de validation** | **Les EIA sont bloqués car ils répondent aux conditions des règles de validation.** |
| Installations bloquées | Les EIA des installations bloquées par les règles de validation. |
| EIA bloqué | Les EIA bloqués par les règles de validation. |
| Corrigé en organique | Les installations détournées, dont la dernière source non frauduleuse est organique. |
| Corrigé en source non organique | Les installations détournées dont la dernière source non frauduleuse était une source média non organique. |

<div id="additional-table-options-1" />

#### Options supplémentaires du tableau

* Cliquez sur **Exporter CSV** pour télécharger le tableau sur votre ordinateur au format CSV
* Cliquez sur l'icône *engrenage* pour :
  * Changer l'ordre des colonnes du tableau
  * Ajouter ou supprimer les colonnes décrites ci-dessus

Le nombre d'évènements affiché est basé sur l'activité et non sur la LTV. Il s'agit donc du nombre exact de blocages d'évènement au cours de la période définie.

</Accordion>

<div id="payable-events" />

<Accordion title="Événements payables">

Les événements payables sont des EIA qui ont un coût. Une fois activé et configuré, le tableau de bord des activités in-app affiche uniquement les données des événements payables.

Pour activer les événements payables dans le tableau de bord des activités in-app :

* Dans la section Filtrer par du tableau de bord des activités in-app, activez l'option Événements payables.  

  [![](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)

Pour configurer les événements payables :

1. Dans le tableau de bord des activités in-app, cliquez sur **Configurer les événements à payer**.  

   [![](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)

   La fenêtre contextuelle de Configuration des événements payables s'affiche.

   [![](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)
2. [Facultatif] Si vous configurez un nouvel événement payable, cliquez sur **Ajouter nouveau**.
3. En fonction des EIA payables que vous souhaitez afficher dans le tableau de bord, sélectionnez dans les menus déroulants les options suivantes :
   * Applications
   * Événements in-app
   * Sources média
   * Campagnes
4. Entrez le CPA de l'EIA.
5. Cliquez sur **Enregistrer**.
6. Cliquez sur **Fermer.**

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Retargeting | <ul><li>Le tableau de bord des installations (CPI) peut afficher les types de touch attribués regroupés par installations, réattributions et ré-engagements.</li><li>Le tableau de bord des événements in-app (CPA) affiche les événements frauduleux provenant des installations AU, mais pas celles provenant du retargeting. **Remarque** : Les événements frauduleux de réattribution identifiés en temps réel se retrouvent dans les rapports de données brutes.</li></ul> |
| Données historiques | Les données sont accessibles dès le début de l'abonnement Protect360. |
| Actualisation des données | Mise à jour quotidienne.<ul><li>Installations (CPI) à 16:00 UTC</li><li>Événements in-app (CPA) à 21:00 UTC</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/protect360-anti-fraud-guide">Présentation de Protect360</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports">Rapports de données brutes</Anchor>

<div data-zendesk-anchors="about-protect360-dashboard=%C3%A0-propos-du-tableau-de-bord-protect360 01H8H9GQ17C4PBHCAMXE879BX7=%C3%A0-propos-du-tableau-de-bord-protect360 01H8H9GQ173SQ8P29C4DETJRTD=filters-and-groupings installs-dashboard=tableau-de-bord-des-installations 01H8H9GQ173H3QH1Y5KZ26XMCW=tableau-de-bord-des-installations installs%E2%80%94headline-metrics=installs-headline-metrics 01H8H9GQ17FJKWE3M2YSZFTQCS=installs-headline-metrics installs%E2%80%94charts=installs-charts 01H8H9GQ18VHMK7FFV3RY409VB=installs-charts identified-fraud-trend-chart=tableau-des-tendance-de-la-fraude-identifi%C3%A9e 01H8H9GQ18JDSZ2H8BKZVWGBPV=tableau-des-tendance-de-la-fraude-identifi%C3%A9e hijacked-installs-attribution-correction-chart=diagramme-de-correction-de-lattribution-des-installations-d%C3%A9tourn%C3%A9es 01H8H9GQ18VXBPQRN55WHM3GG0=diagramme-de-correction-de-lattribution-des-installations-d%C3%A9tourn%C3%A9es identified-fraud-chart=diagramme-des-fraudes-identifi%C3%A9es 01H8H9GQ18FW87TXQZCYERHNDE=diagramme-des-fraudes-identifi%C3%A9es installs%E2%80%94table=installs-table 01H8H9GQ18FYXJA7TXQ4RNQGX2=installs-table identified-fraud-breakdown=r%C3%A9partition-des-fraudes-identifi%C3%A9es 01H8H9GQ18540JJ8X833E6WF44=r%C3%A9partition-des-fraudes-identifi%C3%A9es content-of-the-identified-fraud-breakdown-table=contenu-du-tableau-de-r%C3%A9partition-des-fraudes-identifi%C3%A9es 01H8H9GQ18DMPD7YTPTN2XJMSH=contenu-du-tableau-de-r%C3%A9partition-des-fraudes-identifi%C3%A9es additional-table-options=options-suppl%C3%A9mentaires-du-tableau 01H8H9GQ18PZ8ABG3D51M7J91R=options-suppl%C3%A9mentaires-du-tableau inapp-events-dashboard=tableau-de-bord-des-%C3%A9v%C3%A9nements-in-app 01H8H9GQ19CQZV00XA62MGVJ86=tableau-de-bord-des-%C3%A9v%C3%A9nements-in-app inapp-events%E2%80%94headline-metrics=inapp-events-headline-metrics 01H8H9GQ19B95MDK2WEHVNEFS5=inapp-events-headline-metrics inapp-events%E2%80%94charts=inapp-events-charts 01H8H9GQ19XEJ0HNY2Y8BMX7A5=inapp-events-charts fraud-trend-over-time-chart=diagramme-des-tendances-en-termes-de-fraude-au-fil-du-temps 01H8H9GQ1969AB4KK4ENP8AVQJ=diagramme-des-tendances-en-termes-de-fraude-au-fil-du-temps top-iae-fraud-by-media-source-chart=diagramme-des-principaux-eia-frauduleux-par-source-m%C3%A9dia 01H8H9GQ19Z078PK1HR7VEZHXG=diagramme-des-principaux-eia-frauduleux-par-source-m%C3%A9dia inapp-events%E2%80%94table=inapp-events-table 01H8H9GQ19PTNWGJV6YDWR7SH6=inapp-events-table content-of-the-inapp-event-fraud-breakdown-table=contenu-du-tableau-de-r%C3%A9partition-des-%C3%A9v%C3%A9nements-in-app-frauduleux 01H8H9GQ19773CS8TGS2QXBRG5=contenu-du-tableau-de-r%C3%A9partition-des-%C3%A9v%C3%A9nements-in-app-frauduleux additional-table-options::44e54bfa=options-suppl%C3%A9mentaires-du-tableau-1 01H8H9GQ192WA6XFNW7CKGBQ03=options-suppl%C3%A9mentaires-du-tableau-1 01H8H9GQ1AVAVQ31ZZA1K024RF=payable-events 01H8H9GQ1BJX0K01NX8VCC0690=traits-and-limitations h_01HE7S2JKX3VMRCF6913S4MCAR=articles-connexes" />
