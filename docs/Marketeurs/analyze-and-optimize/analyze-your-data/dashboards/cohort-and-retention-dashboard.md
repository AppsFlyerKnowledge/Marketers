---
title: Tableau de bord des cohortes
metadata:
  keywords:
    - Cohort
    - Cohort Report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2015-12-24T10:20:01Z'
  edited_at: '2023-12-04T14:40:39Z'
  id: 207040496
  locale: fr
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/fr/articles/207040496
---
> **En bref :** le tableau de bord des cohortes regroupe les utilisateurs d'app selon la date d'acquisition. Vous pouvez effectuer une analyse des performances tout au long du cycle de vie utilisateur. Utilisez le tableau de bord pour comprendre comment les différences entre les campagnes agissent sur leurs métriques.

**Revenus par nombre de jours post installation, classé par source média**

![Full_cohort2_us-en.png](https://files.readme.io/b60e18dcd68ca4b1831c56b69ad667931ca52610a456f8612f44d4fac51150f6-14583921567377.png)

<div id="cohort-and-retention-dashboard" />

## Tableau de bord des cohortes

Pour utiliser la cohorte, sélectionnez des utilisateurs dans une ou plusieurs apps et segmentez-les par date de conversion. Les métriques de cohorte telles que le revenu, le ROI ou les taux de conversion d'événements sont disponibles. La cohorte peut être répartie en dimensions de type campagne ou source média afin de comparer certains éléments. Vous faites ainsi le jour sur des modèles ou changements de performances durant les cycles de vie d'utilisateurs ou de campagnes. Voir <Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">Cas d'utilisation des cohortes</Anchor>.

> 👍 **Astuce**
>
> Vous voulez en savoir plus sur les rapports de cohorte ? Suivez cette <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7804/play/18625/your-users-journey-with-retention-and-cohort-reports">formation éclaire</Anchor> sur le portail d'apprentissage AppsFlyer.

<div id="cohort-principles" />

<Accordion title="Principes de la cohorte">

[![OV.png](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)

* **Type de cohorte**
  * **Unifié** :
    * Les performances combinées des campagnes d'acquisition d'utilisateurs et de retargeting (coût et revenus inclus)
    * Si un événement est attribué aux deux types de conversion, seul l'événement de retargeting est inclus. Autrement dit, le rapport est généré en utilisant la source média de la dernière touche réelle. Si vous avez l'habitude des données brutes, cela signifie que les événements sont attribués à <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor>.
  * **Acquisition d'utilisateur :** données de performance des installations (hors réinstallations sauf si elles sont spécifiquement activées).
  * **Retargeting :** données de performance des réattributions ou réengagements
* **Type de tendance**
  * **Performances de la valeur vie utilisateur :** les utilisateurs sont classés par **heure** de conversion. Vous pouvez ainsi comparer les performances de l'utilisateur après conversion, à dater du jour de conversion, que l'on nomme «jour de cohorte 0». La cohorte ne tient pas compte de l'heure de l'événement mais uniquement du jour où il se produit. Cette tendance est souvent utilisée pour évaluer les performances de l'utilisateur en rapport à une source média.
    * Pour la granularité horaire, le nombre maximum d'heures est de 72.
    * Pour la granularité journalière, le nombre maximum de jours est de 180.
    * Pour la granularité hebdomadaire, le nombre maximal de semaines est de 156.
    * Pour la granularité mensuelle, le nombre maximum de mois est de 36.

* * **KPI par jour d'attribution :** les utilisateurs sont regroupés par **heure** de conversion. Vous pouvez ainsi évaluer les performances de la campagne au fil du temps et accéder aux KPI de campagne selon l'heure de conversion.
* **Métriques liées aux coûts :** Dans la cohorte, les données de coût apparaissent uniquement s'il y a une attribution associée (installation, réengagement ou réattribution). En d'autres termes, si une campagne induit un coût basé sur les clics et les impressions, mais qu'elle n'a aucune attribution, alors le coût ne sera pas inclus dans les rapports de cohorte. Ce principe s'applique à tous les niveaux de la hiérarchie publicitaire.
* **Options de granularité**

| Type de granularité | Période autorisée | Remarques |
| --- | --- | --- |
| Jours | Sélectionner 1-60 jours |  |
| Heures | Sélectionnez 1 à 72 heures sur les 72 heures précédentes | Métriques liées au coût non disponibles |
| Semaines | Jusqu'à 26 semaines |  |
| mois | Jusqu'à 12 mois |  |

</Accordion>

<div id="example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend" />

<Accordion title="Exemple : évolution des performances de la valeur vie utilisateur comparée à celle du KPI par jour d'attribution">

Dans cet exemple, les mêmes données brutes sont utilisées pour générer les deux types de tendance de cohorte. Le tableau de données brutes contient les événements d'attribution liés à différents utilisateurs A, B, C et D. Les utilisateurs suivent une publicité, installent l'app et effectuent un ou plusieurs achats après conversion. Le jour 0 de la cohorte correspond au jour de l'installation.

[![CohortExample_en-us.jpg](https://files.readme.io/7542605e2bb3972dc90fb12c9d6a328ff52ec65f0694a79752380d548e72e286-32127949500817.jpg)](https://files.readme.io/7542605e2bb3972dc90fb12c9d6a328ff52ec65f0694a79752380d548e72e286-32127949500817.jpg)

</Accordion>

<div id="metrics-available" />

<Accordion title="Mesures disponibles">

<table><thead><tr><th> </th><th> </th><th colspan="6">Fonctions</th></tr><tr><th rowspan="2">Toujours / Optionnel </th><th rowspan="2"><p>Métrique</p></th><th>Décompte</th><th>cvr (taux de conversion)</th><th>Taux</th><th>Total</th><th>Utilisateurs uniques</th><th>eCPA</th></tr><tr><th>Nombre</th><th>Pourcentage</th><th>Pourcentage</th><th>Nombre</th><th>Nombre</th><th>Nombre</th></tr></thead><tbody><tr><td>Toujours</td><td>Utilisateurs (4)</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td><td><span>-</span></td><td><span>-</span></td></tr><tr><td>Toujours</td><td>Coût (3)</td><td><span>-</span></td><td><span>-</span></td><td>-</td><td><span>✓</span></td><td>-</td><td><span>-</span></td></tr><tr><td>Toujours</td><td>eCPI moyen</td><td><span>-</span></td><td><span>-</span></td><td><span>✓</span></td><td><span>-</span></td><td><span>-</span></td><td><span>-</span></td></tr><tr><td>OPTIONNELLE</td><td><code>"event_name"</code></td><td> </td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td> <span>✓</span><span><span>(5)</span></span> </td></tr><tr><td>OPTIONNELLE</td><td>Revenu</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td><span>-</span></td></tr><tr><td>OPTIONNELLE</td><td>ROAS (3)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td></tr><tr><td>OPTIONNELLE</td><td>ROI (3)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td></tr><tr><td>OPTIONNELLE</td><td>Sessions (2)</td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td><td> <span>✓</span><span>(1)</span> </td><td><span><span>-</span></span></td></tr><tr><td>OPTIONNELLE</td><td>Désinstallations (3)</td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td></tr></tbody><tfoot><tr><td colspan="8"><p>(1) Les sessions uniques reviennent lorsque aggregation_type=on_day<br/>(2) Les sessions de retargeting (réengagement et réattribution) sont disponibles pour les sessions qui ont lieu à compter du 13 juillet 2020. Ce qui signifie que les sessions qui se sont produites avant le 12 juillet 2020 ne s'affichent pas.<br/>(3) Non disponible dans les cas suivants :</p><ul><li>Le type de vue est unifié</li><li>La granularité se compte en heures. Calcul quotidien d'après l'heure UTC.</li></ul><p>(4) La métrique <em>Utilisateurs</em> comptabilise le nombre d'attributions (installations, réengagements, réattributions) survenues durant la période sélectionnée.   </p><p>(5) Coût effectif par action (eCPA) : Coût / Nombre cumulé d'utilisateurs uniques effectuant l'événement.</p></td></tr></tfoot></table>

</Accordion>

<div id="using-cohort" />

## Utiliser la cohorte

<div id="setting-up-an-analysis" />

<Accordion title="Configurer une analyse">

1. Allez dans **Tableau de bord** > **Cohorte**.  
   Le tableau de bord des cohortes s'ouvre. La granularité et la période de conversion s'affichent.  
   ![mceclip0__1_.png](https://files.readme.io/4113fd619422979d6a26004a55c009ebc48eef59d10ddc7c3e5becd2a758e6d4-32127949494417.png)
2. Sélectionnez la granularité.
3. Définissez la période d'attribution (acquisition d'utilisateur ou engagement de retargeting). Les données relatives aux dates les plus récentes peuvent générer des [données partielles](/docs/cohort-and-retention-dashboard#partial-data), indiquées par des tirets dans les graphiques et les tableaux.
4. Cliquez sur **Modifier la cohorte**.La fenêtre de configuration de cohorte s'ouvre.  

   <Image alt="CohortSetup.jpg" src="https://files.readme.io/f09cc190770d16a2ddf60e1f210f458114ac43d4c19fc5507fb50b0d1d2f5c77-32127949495825.jpg" width="365px" />
5. Renseignez les paramètres suivants :
   * **Type de cohorte :**
     * **Acquisition d'utilisateur.**
     * **Retargeting**
     * **Unifiée :** inclut les événements in-app d'attribution d'utilisateur ainsi que de conversions de retargeting. **Remarque** : les événements de retargeting prévalent sur les événements d'acquisition d'utilisateur, ce qui signifie que le rapport contient les événements où <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor>.
   * Sélectionnez un type de tendance :
     * **Performances de la valeur vie utilisateur.**
     * **KPI par jour d'attribution**.
   * **Utilisateurs des applications**: sélectionnez 1 ou plusieurs ou **tous** (soit les 100 premières applications de votre compte). **Remarque** : les agences ne peuvent sélectionner qu'une seule application.
   * **Classement par** :  sélectionnez une ou plusieurs [dimensions](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) (par défaut : *source média*).
   * **Taille minimum de la cohorte** : spécifiez la taille minimale de la cohorte. Cela évitera d'encombrer votre rapport avec des (petites) cohortes inutiles. (Par défaut = 1)
   * Champs optionnels :
     * **Filtré par** : sélectionnez une ou plusieurs [dimensions](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) à appliquer comme filtre. Il n'existe pas de filtre par défaut.
6. Cliquez sur **Appliquer les modifications**.  
   Le rapport s'affiche.
7. Pour terminer la mise en place de la cohorte, effectuez l'une des opérations de type tendance suivantes.
8. [Facultatif] [Gestion des rapports de cohorte sauvegardés](/docs/cohort-and-retention-dashboard#using-my-reports-save-and-select-reports).

</Accordion>

<div id="trend-type-user-lifetime-performance" />

<Accordion title="Type de tendance—Performances de la valeur vie utilisateur">

Les utilisateurs sont classés en cohorte selon le nombre de **jours** qui suit la conversion. Le jour de conversion correspond au «jour de post-conversion 0». Le jour suivant est le «jour de post-conversion 1», et ainsi de suite.

* Pour la granularité journalière, le nombre maximum de jours est de 180.
* Pour la granularité hebdomadaire, le nombre maximal de semaines est de 156.
* Pour la granularité mensuelle, le nombre maximum de mois est de 36.

![DaysPost.jpg](https://files.readme.io/dbeb30f800b198ea0ce2c7b69f2d3652f54384630dab9e8e77a7960a3d9471fb-360005455377.jpg)

* **Sélectionnez une métrique, une fonction et cochez «par utilisateur»**— **Remarque :** toutes les combinaisons de métrique, fonction et «par utilisateur» ne sont pas possibles.
  * Métriques : Revenus, <Anchor target="_blank" href="/marketers/fr/docs/measure-sessions">Sessions</Anchor>, Désinstallations, ROI, Événement in-app, ROAS.
  * Fonctions : la métrique est calculée à l'aide de fonctions. La liste des fonctions varie en fonction de la métrique.
    * **Total** : le revenu total pour une journée de cohorte.
    * **Décompte** : nombre d'événements. Par exemple, le nombre de sessions, le nombre d'événements de revenu, le nombre de désinstallations, etc.
    * **Utilisateurs uniques** : le nombre total d'utilisateurs qui ont exécuté un même événement. Par exemple, si un utilisateur ouvre une application 10 fois au cours d'un jour donné, le résultat sera 1.
    * **Conversion in-app** : taux de conversion de l'installation / retargeting vers un événement in-app. Le nombre d’utilisateurs uniques qui ont exécuté un certain événement in-app pour **la toute première** **fois**, divisé par le nombre d’utilisateurs uniques dans la cohorte. Exemple : une cohorte contient 100 utilisateurs (uniques). Parmi eux, 20 exécutent un événement in-app donné pour la première fois. Le taux de conversion in-app est alors de 20/100 = 20%.
  * **Par utilisateur** : lorsque cette option est activée, le total ou le décompte est divisé par le nombre d'utilisateurs de l'app.
* **Durée d'affichage** : le nombre de jours de cohorte post conversion à afficher. Le jour 0 correspond au jour de la conversion, le jour 1 le lendemain de la conversion, et ainsi de suite. Remarque : la durée d'affichage sera tronquée si le résultat correspond à une date future.
* **Tableau** ou **Graphique :**
  * Les graphiques affichent les 5 ou 10 meilleurs du classement selon le nombre d'utilisateurs d'app de la cohorte. Le résultat ne tient pas compte de la dimension affichée.
  * Les tableaux contiennent jusqu'à 50 lignes. Les utilisateurs, le coût et l'eCPI moyen (coût effectif par installation) sont systématiquement affichés, quelle que soit la métrique sélectionnée.
* ***Jour J*** ou ***Cumulé*** :
  * «Jour J» signifie que la valeur de la métrique se réfère à ce jour uniquement.
  * Ce jour ne fournit pas de métriques liées aux coûts.
  * Cumulé correspond à l'addition de l'ensemble des valeurs de la métrique. Important ! Dans le cas d'une métrique d'utilisateurs uniques, on parle du nombre d'utilisateurs uniques qui ont réalisé un certain événement et ce jusqu'à un jour de cohorte donné. Il ne s'agit pas de la somme des utilisateurs uniques sur les jours précédents.

</Accordion>

<div id="trend-type-kpi-by-attribution-time" />

<Accordion title="Type de tendance—KPI par jour d'attribution">

Les utilisateurs sont regroupés en cohortes par **heure d'attribution.**

![KPIdays.jpg](https://files.readme.io/dfac4a4f84aad39d6526cdb416e8a2ec6c9e95dd6a2ca06e3c7fd10d31b76272-360005458837.jpg)

* **Sélectionnez une métrique, une fonction, les jours de KPI et cochez «par utilisateur»**— **Remarque :** Toutes les combinaisons de métrique, fonction et «par utilisateur» ne sont pas possibles.
  * Métriques : Revenus, Sessions (non disponibles en affichage unifié), Désinstallations, ROI, événement in-app, ROAS.
  * Fonctions : la métrique est calculée à l'aide de fonctions. La liste des fonctions varie en fonction de la métrique.
    * **Total** : le revenu total pour une journée de cohorte.
    * **Décompte**
    * **Utilisateurs uniques** : le nombre total d'utilisateurs qui ont exécuté un même événement. Par exemple, si un utilisateur ouvre une application 10 fois au cours d'un jour donné, le résultat sera 1.
    * **Conversion in-app** : taux de conversion de l'installation / retargeting vers un événement in-app. Le nombre d’utilisateurs uniques qui ont exécuté un certain événement in-app pour **la toute première** **fois**, divisé par le nombre d’utilisateurs uniques dans la cohorte. Exemple : une cohorte contient 100 utilisateurs (uniques). Parmi eux, 20 exécutent un événement in-app donné pour la première fois. Le taux de conversion in-app est alors de 20/100 = 20%.
  * **Jours de KPI :** choisissez entre le jour 0, le jour 3, le jour 7, etc. Le jour 0 correspond toujours au jour de conversion. Le jour 3 signifie correspond au jour de conversion plus les trois jours suivants, soit un total de quatre jours. La même chose s'applique pour les jours d'après. La valeur du KPI est totalisée sur la période sélectionnée.
  * **Par utilisateur** : lorsque cette option est activée, le total ou le décompte est divisé par le nombre d'utilisateurs de l'app.
  * **Tableaux** ou **Graphiques** : les graphiques affichent les 5/10 meilleurs du classement selon le nombre d'utilisateurs d'app de la cohorte. Le résultat ne tient pas compte de la dimension affichée dans le graphique. Les tableaux contiennent jusqu'à 50 lignes.
  * **Jour J :** la valeur renvoie au jour de cohorte spécifié. Par exemple, si l'on prend le jour 7, la valeur correspond au jour post-conversion 7.
  * **Cumulé** : l'addition de tous les jours indiqués dans Jours. Par exemple, si l'on prend le Jour 7, le résultat correspond au cumul du jour de conversion et des 7 jours suivants. Attention ! Dans le contexte des utilisateurs uniques, cela signifie le nombre cumulé d'utilisateurs uniques.

</Accordion>

<div id="list-of-dimensions-for-grouping-and-filtering" />

<Accordion title="Liste des dimensions pour regrouper et filtrer">

| Dimension | Commentaires | Regrouper | Filtrer |
| --- | --- | --- | --- |
| <span id="ad"></span>Publicité |  | ✓ | ✓ |
| <span id="ad-id"></span>Identifiant de publicité |  | ✓ | ✓ |
| <span id="adset"></span>Ensemble de publicités |  | ✓ | ✓ |
| <span id="adset-id"></span>Identifiant de l'ensemble de publicités |  | ✓ | ✓ |
| <span id="agency"></span>Agence |  | ✓ | ✓ |
| <span id="apps"></span>Applications | Particulièrement utile lorsque le rapport contient plusieurs apps | ✓ | **X** |
| <span id="attributed-touchtype"></span>Type de touch attribué | Valeurs : click, impression ou NA (organique) | ✓ | ✓ |
| <span id="campaign"></span>Campagne |  | ✓ | ✓ |
| <span id="campaign-id"></span>Identifiant de la campagne |  | ✓ | ✓ |
| <span id="channel"></span>Canal |  | ✓ | ✓ |
| <span id="conversion-type"></span>Types de conversion | Dépendance au type de cohorte :<ul><li>**Acquisition d'utilisateur** : installations</li><li>**Retargeting** : réengagement, réattribution</li></ul> | ✓ | ✓ |
| <span id="country-geo"></span>Pays (géo) | Basé sur l'adresse IP de l'utilisateur | ✓ | ✓ |
| <span id="time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year"></span>Heure. Dans le cas de :<ul><li>La granularité quotidienne est la date</li><li>La granularité horaire correspond à l'heure de la journée.</li><li>La granularité hebdomadaire correspond à la semaine de l'année.</li><li>La granularité mensuelle correspond au mois de l'année.</li></ul> | Dépendance au type de cohorte :<ul><li>**Acquisition d'utilisateurs et unifié** : l'heure où l'app a été lancée pour la première fois.</li><li>**Retargeting** : l'heure où l'app a été lancée pour la première fois après réengagement.</li></ul> | ✓ | **X** |
| <span id="install-app-store"></span>App store d'installation | Pertinent pour les apps mettant en œuvre l'<Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution">attribution multi-stores</Anchor> d'Android.Contactez votre CSM pour activer cette dimension. | ✓ | ✓ |
| <span id="keywords"></span>Mots-clés | Recherche de mots-clés fournis par les partenaires intégrés | ✓ | ✓ |
| <span id="media-source"></span>Source média |  | ✓ | ✓ |
| <span id="revenue-type"></span>Type de revenu | Ordinaire, monétisation publicitaire | **x** | ✓ |
| <span id="site-id"></span>ID site |  | ✓ | ✓ |
| <span id="sub-param-1"></span>Sous-paramètre 1 |  | ✓ | ✓ |

</Accordion>

<div id="using-my-reports-save-and-select-reports" />

<Accordion title="Utilisation de Mes rapports - Enregistrer et sélectionner les rapports">

* «Mes rapports« vous permet d'enregistrer les paramètres en cours du tableau de bord pour une utilisation ultérieure.
* Sélectionnez un rapport sauvegardé pour afficher les données de cohortes disponibles les plus récentes.
* Vous pouvez sauvegarder un ou plusieurs rapports.
* Vous êtes la seule personne à pouvoir accéder à Mes rapports.

| Contient | Description |
| --- | --- |
| Mes rapports | ![MyReports.png](https://files.readme.io/8f49c0e6dee55427bf3a64149ac48f67547967b8cd24aa8de3e34b760708f992-32127933340305.png)<br /><br />Sélectionnez un rapport pour afficher les données disponibles les plus récentes. |
| Enregistrer les modifications | Sauvegardez le rapport. Remarque : le rapport qui est sélectionné est écrasé et remplacé. |
| Autres méthodes (![Elipse.png](https://files.readme.io/14b74dc6e733867bd16b6a3594f5f0856d7437462b2e0cf7c12adf11cfa295b3-32127949499409.png)) | <ul><li>**Enregistrer comme nouveau**<ul><li>Sauvegardez le rapport en utilisant un autre nom de rapport</li><li>[Facultatif] Faire de ce rapport le rapport par défaut</li></ul></li><li>**Renommer** : changer le nom du rapport</li><li>**Définir par défaut** : faire du rapport le rapport par défaut. Lorsque vous ouvrez Cohorte, c'est le rapport qui s'affiche automatiquement</li><li>**Supprimer**: supprimer le rapport</li></ul> |

</Accordion>

<div id="partial-data" />

<Accordion title="Données partielles">

Utilisez la commande **Cohorte en temps réel** pour sélectionner le mode d'affichage des données :

* [Par défaut] En **temps réel :**
  * Données d'attribution mises à jour en permanence et en temps réel, y compris les revenus.
  * La date de coût est mise à jour 6 fois par jour en moyenne, toutes les quatre heures.
  * Les données partielles (indiquées par des tirets dans les rapports et les graphiques) sont incluses
* **Quotidiennement :** les données sont mises à jour quotidiennement et sont disponibles quelques minutes après minuit. Les données concernant les jours incomplets ne s'affichent pas.

Que sont les données partielles ?

Pour un certain jour dans la plage de données de conversion, si le nombre de jours écoulés depuis la date de conversion est inférieur au nombre de jours de la cohorte, ces jours de cohorte contiendront des données partielles. Cela signifie que les données partielles sont produites les jours où le jour de cohorte est supérieur à la date du jour-la date de conversion.

</Accordion>

<div id="export-the-cohort-to-a-csv-file" />

<Accordion title="Exporter la cohorte au format CSV">

* Les rapports de cohorte peuvent être exportés dans un fichier CSV.
* Les fichiers CSV sont limités à 100 000 lignes.
* La fonction d'exportation en CSV est réservée aux rapports de **performance de la valeur vie utilisateur**.
* Les noms de colonne qui ont le suffixe[partial reviennent au même que les tirets affichés dans les graphiques et les tableaux de l'interface utilisateur.](/docs/cohort-and-retention-dashboard#partial-data)

**Pour exporter les rapports de cohorte au format CSV :**

* En haut à droite de la fenêtre Rapports de cohorte, cliquez sur <Image alt="Download.png" src="https://files.readme.io/50af9c6cde00dada58a1bb89a9eb3e566f316c0e7336af68f4ce403584047a5b-32127933341969.png" width="21px" />(exportation).  
   Le fichier CSV de rapport de cohorte est téléchargé.

</Accordion>

<div id="additional-information" />

## Informations

<div id="cohort-for-agencies" />

<Accordion title="la cohorte pour les agences">

* L'annonceur doit donner l'autorisation à l'agence pour qu'elle utilise la cohorte
  * Pour accorder l'autorisation à une agence, l'annonceur doit :
    * Allez dans **Configuration** > **Intégrations actives**.
    * Sélectionner l'agence.
    * Rendez-vous dans l'onglet Permissions, activez l'option**Autoriser l'accès à vos rapports de rétention et de cohorte.**
* L'accès des agences se limite aux données du trafic généré par l'agence. Elles ne peuvent pas consulter les données du trafic organique ou non organique provenant d'ailleurs.

</Accordion>

<div id="use-cases" />

<Accordion title="CAS D'UTILISATION">

<div id="revenue-sum-by-geo" />

#### Total des revenus par pays

**Tableau : revenu par utilisateur cumulé**

[![CohortGraph.png](https://files.readme.io/1142844a9312498e4fc229502cbdf86d46bd61007d62837d38ba1b66fb2e00aa-360003206697.png)](https://files.readme.io/1142844a9312498e4fc229502cbdf86d46bd61007d62837d38ba1b66fb2e00aa-360003206697.png)

**Tableau : revenu par jour**

[![CohortTable.png](https://files.readme.io/9181e589fc99e48e360fe9361b15fd59ec498b9fa99c31b43e6832aac25376da-360003206717.png)](https://files.readme.io/9181e589fc99e48e360fe9361b15fd59ec498b9fa99c31b43e6832aac25376da-360003206717.png)

<div id="in-app-event-conversion" />

#### Conversion d'évènement in-app

Un annonceur définit un événement in-app avec af\_purchase. Le graphique de cohorte indique le pourcentage d'utilisateurs d'app dans la cohorte qui ont effectué un achat sur mobile. Par exemple, on constate que le jour 10 près de 30% (11,11%+9.71%+7,47%) des utilisateurs de la cohorte ont fait un achat sur leur mobile

[.![Cohort-inapp](https://files.readme.io/e365c6b930d765d97155b1fd4384a608cb7eb0339b2b61e4598ee2d5d17d3249-32127949502481.png)](https://files.readme.io/e365c6b930d765d97155b1fd4384a608cb7eb0339b2b61e4598ee2d5d17d3249-32127949502481.png)

</Accordion>

<div id="faq" />

<Accordion title="FAQ">

| Question | Réponse |
| --- | --- |
| <span id="can-i-view-apple-search-ads-keyword-cost-and-roi"></span>Puis-je accéder au <Anchor target="_blank" href="/marketers/fr/docs/apple-ads-integration-setup#analyze-keyword-cost">coût de mot-clé et au ROI</Anchor> des Apple Search Ads ? | Oui, c'est possible.  <br />Apple Search Ads nous fournit quotidiennement le coût de chaque mot clé, regroupé par campagne \ adset \ publicité. **Remarque :** la répartition par géo / pays n'est pas disponible. |
| <span id="for-a-given-media-source-why-does-the-same-campaign-name-display-more-than-once"></span>Pourquoi est-ce que le même nom de campagne s'affiche plusieurs fois pour une source média donnée ? | <ul><li>Si vous utilisez le même nom de campagne pour des campagnes qui ont des identifiants différents, alors le nom s'affiche plus d'une fois.</li><li>Nous vous conseillons d'attribuer un nom spécifique à chaque ID de campagne</li><li>Lorsque vous changer un nom de campagne, les données s'alignent sur le dernier nom utilisé.</li></ul> |
| <span id="can-i-view-organic-users"></span>Est-il possible d'afficher les utilisateurs organiques ? | Les utilisateurs organiques, sont inclus dans les rapports de cohorte par défaut.<br /><br />**Pour limiter le rapport de la cohorte aux utilisateurs organiques exclusivement :**<ol><li>Dans le **Tableau de bord des cohortes**, cliquez sur le bouton **Modifier la cohorte**.</li><li>Dans la fenêtre de configuration de la cohorte, sélectionnez **Filtrer par** > **Source média** est **Organique** :</li></ol>[![cohort_setup_filtered_by_media_source_is_organic.png](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)<ol><li>Cliquez sur **Appliquer les modifications**.</li></ol> |
| <span id="can-i-see-data-from-deleted-installs"></span>Est-il possible de consulter les données des installations supprimées ? | Les installations supprimées, comme les installations des SRN qui ont été supprimées à cause des politiques de conservation des données, ou les installations supprimées en vertu du RGPD, ne sont pas visibles dans le tableau de bord de cohorte.<br /><br />Pour plus d'informations, veuillez cliquer <Anchor target="_blank" href="/marketers/fr/docs/user-level-data-retention#périodes-de-conservation-des-données-des-partenaires">ici</Anchor>. |
| <span id="can-i-compare-data-for-daily-view-to-data-in-weekly-or-monthly-views"></span>Peut-on comparer les données quotidiennes aux données hebdomadaires ou mensuelles ? | Il n'est pas facile de comparer les données d'une granularité quotidienne à une granularité hebdomadaire ou mensuelle, car les LTV des cohortes ne s'alignent pas. <br /><br />Lors de l'affichage des cohortes en granularité quotidienne, le **Jour 0** affiche les données pour le jour de l'installation. Le jour 1 correspond au lendemain de l'installation, le jour 2 correspond au surlendemain de l'installation, etc. <br /><br />Pour les cohortes en granularité hebdomadaire, les données s'affichent pour toutes les installations effectuées sur l'ensemble de la **Semaine 0**. La semaine 1 correspond à la semaine suivant l'installation, la semaine 2 à 15 jours après l'installation, etc. <br /><br />Pour les cohortes en granularité mensuelle, les données s'affichent pour toutes les installations effectuées sur l'ensemble du **Mois 0**. Le mois 1 correspond au mois suivant l'installation, le mois 2 à 2 mois après l'installation, etc. <br /><br />Les calendriers LTV ne sont donc pas alignés. Exemple avec les données du 9 au 15 janvier : si vous utilisez la granularité quotidienne, **Jour 0** contient des données pour le premier jour sur toutes les installations **effectuées du 9 au 15 janvier,** et **Jour 6** contient les données pour les 6 premiers jours après installation sur les installations effectuées entre le **9 et le 15 janvier**. De plus, avec la **granularité hebdomadaire**, **Semaine 0** contient les données pour toutes les installations sur **toute la période** **allant du 9 au 15 janvier**. Ainsi, pour les installations du **9 janvier**, les données sont les suivantes : **Jour 6**. Mais pour les installations du **15 janvier**, elles sont les mêmes qu'au **Jour 0**. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Remarques |
| --- | --- |
| Accès du réseau publicitaire à Cohort | Non disponible |
| Autorisations de l'agence | Disponible :<ul><li>Limité à une seule app.</li><li>Les comptes hybrides ne peuvent pas accéder à la cohorte.</li><li>Nécessite une autorisation d'accès pour chaque app.</li><li>La sélection de plusieurs apps n'est pas possible.</li><li>L'accès aux données organiques n'est pas possible.</li></ul> |
| Transparence de l'agence | Disponible depuis le 10 janvier 2021 |
| Fuseau horaire spécifique à l'app | <ul><li>Disponible</li><li>Exception : dans tous les cas suivants, AppsFlyer ignore le fuseau horaire spécifique à l'app et utilise le fuseau horaire par défaut (UTC +0)<ul><li>Le rapport de cohorte contient les données provenant de plusieurs apps, et les apps ont des fuseaux horaires différents.</li><li>Les apps ont toutes le même fuseau horaire, et le fuseau horaire d'au moins l'une d'entre elles a changé sur la période du rapport de cohorte. Pour déterminer la période du rapport :<ul><li>Date de démarrage : le premier jour de la plage de dates de conversion</li><li>Date de fin : elle est calculée en additionnant le nombre de jours de la durée d'affichage et le dernier jour de la plage de dates de conversion. Ex. Dernier jour = 1er janvier 2019. Durée du rapport : 30 jours. Date de fin : 31 janvier 2019.</li></ul></li><li>Les données hebdomadaires et mensuelles sont affichées selon le fuseau horaire UTC.</li></ul></li></ul> |
| Devise spécifique à l'app | <ul><li>Disponible</li><li>Restriction :  toutes les apps doivent utiliser la même devise.Dans le cas contraire, l'USD est utilisé.</li></ul> |
| Limites | <ul><li>Fichiers CSV téléchargeables :<ul><li>10 000 lignes maximum</li><li>N'est pas disponible pour les tendances de KPI parjour d'attribution.</li></ul></li><li>Graphiques : affichent les 5 ou 10 meilleurs résultats classés par nombre d'utilisateurs dans la cohorte.</li><li>Tableaux : affichent les 50 premières lignes classées par le nombre d'utilisateurs dans la cohorte.</li><li>Réinstallations : si les événements postérieurs à la réinstallation sont considérés comme événements organiques non attribués, ils ne sont pas inclus dans la cohorte. Si ils sont attribués à la première installation, ils sont inclus. <Anchor target="_blank" href="/marketers/fr/docs/measure-reinstalls#les-événements-in-app-et-leur-système-dattribution">En savoir plus</Anchor></li><li>Coût : AppsFlyer ne rapporte pas les données de coût pour les mots-clés qui contiennent des lettres majuscules dans le rapport de cohorte ou l'API de cohorte.</li><li>Limite de 10 exportations CSV par minute, 100 maxi par jour (par utilisateur).</li><li>Limite de 20 requêtes de données par minute, 500 maxi par jour (par utilisateur). Tout changement de période, de groupe, de KPI, ou autre, est considéré comme une nouvelle requête.</li></ul> |
| Données organiques | Inclus |
| Données non organiques | Inclus |
| Actualisation des données | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#eod">temps réel</Anchor></li><li>Exceptions :<ul><li>Cohortes quotidiennes :<ul><li>Le nombre de coûts, revenus publicitaires et désinstallations est mis à jour quotidiennement.</li><li>Les désinstallations sont calculées une fois par jour d'après l'heure UTC.</li></ul></li><li>Cohortes hebdomadaires et mensuelles :<ul><li>Les données en temps réel ne sont pas disponibles.Les données ne s'afficheront qu'une fois complétées (c'est-à-dire à la fin de la semaine ou du mois).<br />Toutefois, les données pour lesquelles une partie des données d'installation est complétée s'afficheront, comme dans le cas où certaines données sont complétées (heure post-installation) et d'autres n'ont pas encore commencé.</li></ul></li></ul></li></ul> |
| Données historiques | <ul><li>Cohorte quotidienne : 2 ans</li><li>Cohortes hebdomadaires/mensuelles : 3 ans</li></ul> |
| Géo/pays | <ul><li>Disponible</li><li>Lorsque la zone géo est inconnue (N/A), les données des revenus publicitaires ne s'affichent pas lors du regroupement par zone géo.</li></ul> |
| Nombre de sessions | Le nombre de sessions au jour 0 dans la vue Retargeting peut être inférieur au nombre d'utilisateurs.<br />Plusieurs raisons peuvent l'expliquer. Les plus courantes sont les suivantes :<ul><li>La session de réengagement a déjà été attribuée avant que le réengagement ne soit enregistré. Dans ce cas, elle ne sera pas attribuée à la session de retargeting.</li><li>Le filtrage selon différents paramètres comme **Durée minimum entre les sessions**. Dans ce cas, le réengagement est enregistré. Cependant, les sessions sont filtrées mais ne sont pas enregistrées.</li></ul> |
| Retargeting et données unifiées | Les données mensuelles sur les sessions ne sont disponibles qu'à compter du 1er septembre 2021. |
| Revenus publicitaires | <ul><li>Non disponibles lors de l'affichage des cohortes avec une granularité horaire.</li><li>Les données de revenus publicitaires peuvent afficher des différences entre le tableau général et le tableau de cohorte. Cela se produit lorsque les réseaux déclarent les revenus en UTC et que les applications ont un fuseau horaire différent.</li><li>Pour les événements af\_ad\_revenue, la mesure des utilisateurs uniques n'est pas disponible lorsque le type d'agrégation est :<ul><li>«Cumulatif».</li><li>«Le jour même», pour les dates comprises entre le 5 octobre 2022 et le 16 février 2023.</li></ul></li></ul> |
| Granularité hebdomadaire et mensuelle | <ul><li>Les granularités hebdomadaire et mensuelle ne sont disponibles que dans le tableau de bord de cohorte.</li><li>**Utilisateurs uniques** et **Taux de conversion** ne sont pas disponibles si les données incluent des installations qui ont eu lieu avant novembre 2022.</li><li>Les métriques liées aux coûts ne sont pas disponibles lors du regroupement par semaine ou par mois. Elle incluent :</li></ul><ul><li>Coût</li><li>eCPI</li><li>ROI</li><li>ROAS</li></ul><ul><li>Les données historiques ne sont disponibles qu'à partir de 2021.</li></ul> |
| Période de la cohorte | <ul><li>La période de conversion est désignée par 0 (heure 0, jour 0, semaine 0 ou mois 0). La période qui suit la conversion est appelée 1 (heure 1, jour 1, semaine 1 ou mois 1), et ainsi de suite.</li><li>Dans AppsFlyer, une période de cohorte ne prend pas en compte l'heure de l'installation. Les heures de la cohorte sont arrondies et les jours, semaines et mois de la cohorte sont basés sur le jour, la semaine ou le mois du calendrier. Cela peut entraîner des divergences lorsque l'on compare les données de cohorte d'AppsFlyer aux données de cohorte d'autres réseaux, où toutes les périodes de cohorte sont déterminées par l'heure précise de l'installation (une heure correspond à 60 minutes après l'heure de l'installation, un jour correspond à la période de 24 heures après l'heure de l'installation, etc.)</li></ul> |

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview#cohort-flavors">Différences entre les versions de cohorte</Anchor>

<div data-zendesk-anchors="cohort-dashboard=tableau-de-bord-des-cohortes 01H7WE9R0CX9C2MQHNK1MB15AM=tableau-de-bord-des-cohortes 01H7WE9R0DSQ4E0WTXPTF43S08=astuce 01H7WE9R0D15RA4F3ZN6Y1Q30N=cohort-principles 01H7WE9R0DJA1ZNDR265WEWVKH=example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend 01H7WE9R0DTNKK17Y0XXZQRXD0=metrics-available using-cohort=utiliser-la-cohorte 01H7WE9R0DZDRBYYCM3ACSHXMS=utiliser-la-cohorte 01H7WE9R0DRV7CENP28NB0TNDK=setting-up-an-analysis trend-type%E2%80%94user-lifetime-performance=trend-type-user-lifetime-performance 01H7WE9R0D76VN0K95BF3ZBTH6=trend-type-user-lifetime-performance trend-type%E2%80%94kpi-by-attribution-time=trend-type-kpi-by-attribution-time 01H7WE9R0DN3ZPVTDGJ72QWEV0=trend-type-kpi-by-attribution-time 01H7WE9R0DSFAXSK2C1BBSJJCC=list-of-dimensions-for-grouping-and-filtering time-in-the-case-of%0A%0Adaily-granularity-is-the-date%0Ahourly-granularity-is-the-hour-of-the-day%0Aweekly-granularity-is-the-week-of-the-year%0Amonthly-granularity-is-the-month-of-the-year=time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year using-my-reports%E2%80%94save-and-select-reports=using-my-reports-save-and-select-reports 01H7WE9R0ERMN0ZNN1RDBD7SYA=using-my-reports-save-and-select-reports 01H7WE9R0E6BPEKRQKAMZVD12Y=partial-data 01H7WE9R0EMP5YPK4RSF06PP3B=export-the-cohort-to-a-csv-file information=informations 01H7WE9R0ETQW8WCRW8Q2NSNFF=informations 01H7WE9R0E8JHK7J4RZB50TAHE=cohort-for-agencies 01H7WE9R0E153RM1BE5BWZ7XEE=use-cases revenue-sum-by-country=total-des-revenus-par-pays 01H7WE9R0FNZC0QWNDNCR1CKH2=total-des-revenus-par-pays inapp-event-conversion=conversion-d%C3%A9v%C3%A8nement-in-app 01H7WE9R0FC8BV8F2STR6P9J3M=conversion-d%C3%A9v%C3%A8nement-in-app 01H7WE9R0FYH0CMQ3E6KMT5EKH=faq 01H7WE9R0F4GZ3WA21N1YF4AAG=traits-and-limitations h_01HE0CSHCJRXXG8WXRBHCWN7AC=%C3%A0-consulter-%C3%A9galement" />
