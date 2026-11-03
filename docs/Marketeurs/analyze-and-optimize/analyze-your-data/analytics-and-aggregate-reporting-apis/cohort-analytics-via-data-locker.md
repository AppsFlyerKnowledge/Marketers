---
title: Analyse des cohortes via Data Locker
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2021-10-14T08:46:00Z'
  edited_at: '2024-08-07T11:22:19Z'
  id: 4408945472529
  locale: fr
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/fr/articles/4408945472529
---
> **En bref :** L'analyse des cohortes dans Data Locker contient des données agrégées de tous les éléments de la hiérarchie publicitaire. Les rapports contiennent des données sur les utilisateurs qui ont effectué des attributions au cours des 365 jours précédents. Ce rapport est accessible aux annonceurs qui disposent de données brutes ou de l'API Cohort, ou des deux, dans le cadre de leur abonnement. Cela signifie qu'aucun abonnement Data Locker n'est requis pour ce rapport.

## Analyse des cohortes dans Data Locker

Dans certains cas, les données brutes d'attribution dans AppsFlyer sont <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">limitées</Anchor> en raison des politiques de partage des données des sources média ou de vos <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">politiques de protection de la vie privée.</Anchor> La restriction inclut tous les champs liés à l'attribution, tels que la campagne et l'adset. Les rapports de cohorte vous fournissent des données agrégées qui peuvent être utilisées comme alternative aux données brutes.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ8q_4xv83wHkl4fs6jndEffRu-RHsPobBRfxDG-bUNXb0pOnvJH4QT0nXKdWvi3JPtVUBegTFbxIEe/pub?output=xlsx">Télécharger un exemple de rapport</Anchor>

<div id="enable-data-locker" />

<Accordion title="Activer Data Locker">

Le rapport est disponible pour Data Locker, l'API Cohort et les abonnés aux données brutes. Pour activer le rapport dans <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">Data Locker,</Anchor> effectuez l'une des procédures suivantes.

| Obtenez-vous actuellement des données via Data Locker ? | Marche à suivre |
| --- | --- |
| Oui | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Pour ajouter les rapports de cohorte à Data Locker :<ol><li>Dans AppsFlyer, dans le menu latéral, sélectionnez **Rapport > Data Locker**.</li><li>Sélectionnez tous les rapports dans la section **Analyse des cohortes**.</li><li>Cliquez sur **Enregistrer la configuration**.<br />Les rapports seront disponibles le lendemain à 10:00 UTC.</li></ol> |
| Non | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**Pour configurer Data Locker** :<ol><li>Achevez la toute première configuration Data Locker (<Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers#set-up-data-locker">annonceur</Anchor> \| <Anchor target="_blank" href="/partners/fr/docs/data-locker-for-partners">partenaire</Anchor>).</li><li>Ajoutez les rapports de cohorte à Data Locker :<ol><li>Dans AppsFlyer, dans le menu latéral, sélectionnez **Rapport > Data Locker**.</li><li>Sélectionnez tous les rapports dans la section **Analyse des cohortes**.</li><li>Cliquez sur **Enregistrer la configuration**.<br />Les rapports seront disponibles le lendemain à 10:00 UTC.</li></ol></li></ol> |

</Accordion>

Vous pouvez charger les données dans vos systèmes de BI et les utiliser dans le cadre de vos processus de performance et d’optimisation des campagnes ;

**Métriques disponibles**

Les métriques disponibles sont les revenus, les utilisateurs uniques qui effectuent un événement et le nombre d’occurrences d’événements. Pour calculer des indicateurs liés aux coûts tels que le ROI (retour sur investissement) et le ROAS (retour sur les dépenses publicitaires), vous avez besoin à la fois de données liés aux revenus et aux coûts. Les mesures de revenus sont dans la partie Cohorte. Les mesures de coûts sont fournies par <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports">l’ETL des coûts ROI360</Anchor>.

<div id="facts" />

<Accordion title="Faits relatifs à l'analyse des cohortes">

| Rapports disponibles | Les rapports suivants peuvent être téléchargés. Les types de rapports sont décrits plus en détail dans le <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard#cohort-principles">tableau de bord «Cohorte».</Anchor><ul><li>**Acquisition d'utilisateurs :**  attribués à une source média d'acquisition d'utilisateurs, y compris la lifetime value (LTV) se produisant pendant les fenêtres de réengagement.</li><li>**Retargeting :** attribués à une source média de retargeting pour les événements qui ont lieu :<ul><li>pendant une fenêtre de réengagement ;</li><li>suite à une réattribution</li></ul></li><li>**Unifiés :** affichent les données sous la dernière source média ayant attiré l'utilisateur, selon les règles de <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">double attribution</Anchor> d'AppsFlyer. Cela signifie que les LTV survenant lors de réengagements s'affichent sous la source média de retargeting et non sous la source média d'UA.</li></ul> |
| --- | --- |
| Période de reporting | Utilisateurs ayant effectué des conversions au cours des 365 derniers jours. En d'autres termes, chaque jour, les rapports incluent les conversions effectuées par les utilisateurs au cours des 365 jours précédents. |
| Structure du rapport | Le schéma de chaque rapport (dimensions et métriques incluses) est fixe et ne peut pas être modifié. Voir la [structure du rapport](/docs/cohort-analytics-via-data-locker#report-structure). |
| Livraison du rapport | Voir [Activer les rapports de cohorte dans Data Locker](/docs/cohort-analytics-via-data-locker#enable-data-locker). |
| Actualisation des données | <ul><li>Quotidiennement.</li><li>Les mesures sont calculées à l'aide des données disponibles à minuit UTC. En d'autres termes, en fin de journée.</li><li>Les rapports sont disponibles dans Data Locker dans le dossier date-heure (dt) avant 10 h UTC. Par exemple, les données du lundi sont disponibles le mardi à 10 h UTC dans le dossier Lundi.</li></ul> |
| L'impact des politiques de rétention des partenaires | Considérez que certains partenaires mettent en œuvre une politique de conservation des données. Dans ce cas, les événements survenant après la fin de la période de rétention sont considérés comme organiques dans les rapports de cohorte.<br /><br />Exemple : Le SRN A a une politique de conservation des données de 180 jours. Les événements utilisateur survenus jusqu'au 180e jour sont attribués au SRN A. Les événements survenant après 180 jours sont considérés comme organiques. |

</Accordion>

<div id="report-structure" />

<Accordion title="Structure du rapport">

Le rapport est composé de mesures et de métriques.

Le format des champs est le suivant :

* **Mesures :** chaînes. La longueur maximale de la chaîne est dynamique et, dans la plupart des cas, dépend de la façon dont vous renseignez les éléments de la hiérarchie publicitaire.
* **Indicateurs** : nombres. **Remarque :** le format du champ selected\_currency est une chaîne.

#### Dimensions

<Table>
  <thead>
    <tr>
      <th>
        Nom du champ
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        Valeurs possibles : install, install-unified (représentant les installations dans le rapport unifié), réengagement, réattribution
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        Valeurs possibles : clic, impressions, préinstallation, inconnu, tv, nul
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        * Le nombre de jours écoulés depuis la date de conversion (pas l'horodatage spécifique de la conversion).
        * Astuce ! Utilisez ce tag pour calculer les jours de rétention et ceux des KPI.
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        * Date à laquelle un utilisateur effectue un événement donné.
        * Format : aaaa-mm-jj
        * Exemple : La date à laquelle un utilisateur a effectué un événement in-app donné. Dans le cas d’une conversion.
        * Important ! Si le event\_name est af\_conversion, la date de l’événement et la date de conversion seront les mêmes.
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        * La date à laquelle la conversion a eu lieu
        * Format : aaaa-mm-jj
        * Exemple : La date d’installation
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        Identifie l’événement. Certains noms d’événements ont une signification spécifique, tandis que d’autres sont liés à des événements intégrés définis par l’annonceur dans l’application. 

        | event\_name | Qu’a fait l’utilisateur ? |
        | --- | --- |
        | af\_conversion | Utilisateur converti. Utilisez conversion\_type pour identifier s’il s’agit d’une installation, d’un réengagement ou d’une réattribution. |
        | af\_session | a ouvert l'application |
        | cohort\_uninstalls | A désinstallé l'app |
        | Événement in-app défini par l’annonceur | a effectué un événement dans l’application |
      </td>
    </tr>
    <tr>
      <td>
        campagne
      </td>
      <td>
        Hiérarchie des campagnes

        N'oubliez pas : il n’est pas possible de modifier le nom de la campagne, une fois celui-ci établi. Par conséquent, plusieurs noms peuvent être associés à un même identifiant de campagne.
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        adset
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        ad
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        canal
      </td>
      <td>
        Hiérarchie des campagnes.

        [À jour le 27 octobre 2021] À l'heure actuelle, les annonces Meta ne renseignent pas le canal dans les données fournies via le mécanisme de référencement d'installation de Google, le Google Install Referrer.
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        Hiérarchie des campagnes
      </td>
    </tr>
    <tr>
      <td>
        {"is_primary_"} attribution
      </td>
      <td>
        Permet d’identifier et de dédupliquer les données de retargeting.
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        Le code de pays ISO dérivé de l’adresse IP de l’utilisateur.
      </td>
    </tr>
    <tr>
      <td>
        agency
      </td>
      <td>
        * Information sur l'agence prise en charge.
        * Lorsque les agences ne fournissent pas de détails complets sur leurs activités (non transparentes), plusieurs lignes avec le même nom de campagne peuvent apparaître si l'annonceur et l'agence lancent des campagnes portant le même nom. Pas d'inquiétude. Les lignes ne sont pas dupliquées.
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        Applications Android uniquement : La boutique Android à partir de laquelle l’application a été téléchargée. Alimenté par les annonceurs mettant en œuvre <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution">l'attribution multi-magasins sur Android.</Anchor> Si ce champ est vide, cela signifie Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        keywords
      </td>
      <td>
        Le ou les mots utilisés par l'internaute lors de sa recherche. Tels que rapportés par le réseau publicitaire.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        [Champ disponible depuis le 27 avril 2022] ID de mot clé renvoyé par le réseau publicitaire.
      </td>
    </tr>
  </tbody>
</Table>

#### Métriques

| Nom du champ | Description | Format |
| --- | --- | --- |
| unique\_users | Nombre d’utilisateurs uniques le jour de l’événement. | Nombre |
| revenue\_usd | <ul><li>Montant du chiffre d’affaires en USD. Par exemple, 100,56 $ est présenté comme 100,56.</li><li>Maximum de 2 décimales après la virgule.</li></ul> | Nombre |
| event\_count | Nombre d'événements. | Nombre |
| selected\_currency | Code de devise à 3 lettres (USD, EUR) que vous définissez dans les paramètres de l’application. Format <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. Il s’agit de la même devise que celle utilisée pour afficher les revenus dans Cohorte dans l’interface utilisateur. | Chaîne |
| revenue\_selected\_currency | <ul><li>Montant du revenu dans la devise sélectionnée. Par exemple, si la devise sélectionnée est EUR, alors 1234,56 € est indiqué comme 1234,56</li><li>Maximum de 2 décimales après la virgule</li></ul> | Nombre |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="Considérations pour les développeurs BI">

**Portée des données dans le rapport**

Les rapports contiennent les installations par les utilisateurs en acquisition, les ré-attributions et les ré-engagements de retargeting, ainsi que les événements associés dans l'application.

Vous pouvez charger des rapports unifiés, d’acquisition d’utilisateurs et de retargeting séparément ou ensemble dans votre BI. Si vous les chargez ensemble et que vous souhaitez filtrer les vues par vous-même :

* Pour consolider les données, utilisez le champ is\_primary\_attribution=true ou laissez le champ nul.
* Pour l’acquisition d’utilisateurs, utilisez conversion\_type=Install.
* Pour le retargeting, utilisez conversion\_type=réengagement ou réattribution.

Si vous utilisez simplement la vue unifiée dans votre processus de chargement des données, vous pouvez utiliser la logique pour répartir les données entre les types de campagne, c’est-à-dire l’attribution des utilisateurs (installations) et le retargeting (réengagements). Pour ce faire, utilisez les conversion\_type=install, install-unified, re-engagement ou re-attribution. <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">Double attribution d'événements de retargeting.</Anchor>

**Considérations au niveau du champ**

* Utilisez les jours de post-attribution pour faciliter le calcul des mesures de rétention.
* Calcul des utilisateurs uniques à l’aide des mesures liées au nom et et à l’ID de campagne : Si vous pouvez ignorer la granularité des noms de campagne, vous pouvez totaliser un décompte unique à partir de l'ID de campagne. Les indicateurs seront ainsi fiables.
* Vous pouvez agréger les données à l’aide des champs de hiérarchie de campagne.
* Les revenus en USD sont calculés en utilisant le taux de change du jour de l’événement.
* Les événements liés aux revenus publicitaires sont inclus lorsqu'ils sont disponibles, mais ils peuvent être mis à jour avec un retard allant jusqu'à 3 jours.

**Considérations générales**

Les données de toutes les applications sont fournies dans un seul fichier. Utilisez le champ App ID pour séparer les données par application ou configurez Data Locker pour les séparer par application.

</Accordion>

<div id="use-cases" />

<Accordion title="Cas d’utilisation">

Voici quelques exemples d’applications populaires et pratiques des données de cohorte que les développeurs BI peuvent extraire via Data Locker. Chaque exemple est illustré par une requête SQL et un exemple de visuel Excel.

#### **1. Calcul de la rétention**

Dans l’exemple suivant, nous :

* Calculons la rétention Jour 1 et Jour 7, ainsi que le nombre total d’installations par campagne et publicité ;
* Additionnons le nombre d’événements par événement de conversion en filtrant `event_name` pour qu’il soit `af_conversion` ;
* Analysons spécifiquement les campagnes d’acquisition d’utilisateurs en filtrant les données afin que `conversion_type=install`.

**instruction SQL**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as installs,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and conversion_type = 'install'
    and app_id = YOUR_APP
group by 1,2
```

**Exemple d’Excel**

| ID de campagne | ID publicitaire | Installations | Jour 1 de rétention | Jour 7 de rétention |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30 % | 10 % |
| 98765432 | 123456 | 200 | 25 % | 15 % |
| 07315466 | 613770 | 300 | 20 % | 12 % |

#### **2. Calcul de l’ARPU de plusieurs événements dans l’application**

Dans l’exemple suivant, nous :

* Calculons l’ARPU de plusieurs événements in-app par campagne.
* Analysons spécifiquement les campagnes de reciblage en filtrant les données de sorte que `conversion_type=re-engagement` et `conversion_type=re-attribution`.
* Additionnons le nombre d’événements par événement de conversion en filtrant `event_name` pour qu’il soit `af_conversion` ;
* Additionnons les revenus de plusieurs événements, dans ce cas `af_purchase`et `af_coins`.
* Définissez `days_post_attribution` le minimum nécessaire (dans ce cas, 7) pour minimiser la charge de traitement des données.

**Instruction SQL**

```sql
select
    campaign_id,
    sum(if(days_post_attribution <= 1 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day1,
    sum(if(days_post_attribution <= 3 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day3,
    sum(if(days_post_attribution <= 7 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and days_post_attribution <= 7
    and conversion_type in ('re-engagement', 're-attribution')
    and app_id = YOUR_APP
group by 1
```

**Exemple Excel**

| ID de campagne | Types de conversion | ARPU<br /><br />Jour 1 | ARPU<br /><br />Jour 3 | ARPU<br /><br />Jour 7 |
| --- | --- | --- | --- | --- |
| 12345678 | Réengagement | 6,23 | 5,11 | 2,34 |
| 98765432 | Réengagement | 3,57 | 1,34 | 4,86 |
| 07315466 | Réattribution | 7,41 | 6,79 | 5,29 |

#### **3. Calcul du taux de conversion des événements in-app pour un jour de cohorte spécifique**

Dans l’exemple suivant, nous :

* Calculons le taux de conversion de l’événement dans l’application Jour 0 pour plusieurs mesures (dans ce cas, la date de conversion, la zone géographique, la campagne, l’annonce et l’ID du site).
* Analysons les données unifiées (UA et campagnes de remarketing) en filtrant les données de sorte que `is_primary=true`.
* Additionnons le nombre d’événements par événement de conversion en filtrant `event_name` pour qu’il soit `af_conversion` ;
* Définissons `days_post_attribution` le minimum nécessaire (dans ce cas, 7) pour minimiser la charge de traitement des données.

**Instruction SQL**

```sql
select
    conversion_date, geo, campaign_id, ad_id, site_id,
    sum(if(days_post_attribution = 0 and event_name = 'af_complete_tutorial', unique_users, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as day0_af_tutorial_conversion
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and is_primary = true
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Exemple Excel**

| Date de la conversion | Géo | ID de campagne | ID publicitaire | ID de site | Jour 0 af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 2022-11-07 | États-Unis | 12345678 | 123456 | site\_123 | 45 % |
| 2022-11-05 | GB | 98765432 | Nul | site\_654 | 70 % |
| 2022-10-31 | KR | 07315466 | Nul | Nul | 63% |

#### **4. Calcul des installations quotidiennes**

Dans l’exemple suivant, nous :

* Calculons le nombre d’installations par ID d’application, date de conversion, source média, nom de l’événement et type de conversion.
* Filtrons les données pour afficher les installations UA (pas le retargeting), en définissant `conversion_type` sur `install`.
* Additionnons les installations en définissant `event_name` pour qu’elles soient `af_conversion`

**Instruction SQL**

```sql
select
    app_id,
    conversion_date,
    media_source,
    event_name,
    conversion_type,
    sum(events_count) as total
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and conversion_type = 'install'
    and event_name = 'af_conversion'
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Exemple Excel**

| ID d'app | Date de la conversion | Source média | Nom de l'événement | Total |
| --- | --- | --- | --- | --- |
| id123456789 | 2022-11-07 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 2022-11-05 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 2022-10-31 | adnet3\_int | af\_conversion | 327 |

#### **5. Calcul des revenus à partir des publicités Facebook**

Dans l’exemple suivant, nous :

* Calculons les revenus de Facebook du jour 3 par date de conversion et ID d’application.
* Analysons les données Facebook en filtrant les données de sorte que `media_source='Facebook Ads'`.
* Définissons `days_post_attribution` le minimum nécessaire (dans ce cas, 3) pour minimiser la charge de traitement des données.

**Instruction SQL**

```sql
select
    conversion_date,
    app_id,
    media_source,
    sum(if(days_post_attribution <= 3, revenue_usd, 0)) as revenue_day3
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and days_post_attribution <= 3
    and media_source = 'Facebook Ads'
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3
```

**Exemple Excel**

| Date de la conversion | ID d'app | Source média | Revenus<br /><br />Jour 3 |
| --- | --- | --- | --- |
| 2022-11-07 | id123456789 | adnet1\_int | 400,45 |
| 2022-11-05 | id123456789 | adnet2\_int | 99,23 |
| 2022-10-31 | id123456789 | adnet3\_int | 13,34 |

#### **6. Calcul de l’ARPU par ID de mot-clé ASA pour un maximum de 365 jours de cohorte**

Dans l’exemple suivant, nous :

* Calculons l’ARPU à partir d’Apple Search Ads par identifiant de mot-clé jusqu’au jour de cohorte 365.
* Analysons les données Apple Search Ads en les filtrant de sorte que `media_source='Apple Search Ads'`.
* Additionnons le nombre d’événements par événement de conversion en filtrant `event_name` pour qu’il soit `af_conversion` ;

**Instruction SQL**

```sql
select
    media_source,
    keyword_id,
    sum(if(days_post_attribution <= 365, revenue_usd,0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day365
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and media_source = 'Apple Search Ads'
    and app_id = YOUR_APP
group by 1
```

**Exemple Excel**

| Source média | ID de mot clé | ARPU<br /><br />Jour 365 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57 019,93 |
| adnet2\_int | 987654 | 64 867,84 |
| adnet3\_int | 666854 | 48 160,02 |

#### **7. Calcul du ARPU (revenu moyen par utilisateur) à J+7 par heure d'attribution et par zone géographique**

L’exemple suivant illustre comment utiliser <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard#trend-type-kpi-by-attribution-time">les indicateurs de performance par heure d’attribution</Anchor>. :

* Calcul de l’ARPU à J+7 par date d’attribution et par zone géographique ;
* Les résultats sont triés en fonction du nombre de conversions, les 20 premières zones géographiques s’affichant ;
* Les données sont filtrées de sorte que `conversion_type='install'` ;
* La première colonne indique la zone géographique. La deuxième colonne indique le nombre total de conversions. Les colonnes suivantes affichent le revenu à J+7 pour chaque jour spécifié comme une ligne dans la requête.

**Instruction SQL**

```sql
select
    geo,
    sum(if(event_name = 'af_conversion', event_count, 0)) total_conversions,
    sum(if(cohort_day = '2023-07-11' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-11' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_11,
    sum(if(cohort_day = '2023-07-12' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-12' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_12,
    sum(if(cohort_day = '2023-07-13' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-13' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_13,
    sum(if(cohort_day = '2023-07-14' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-14' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_14,
    sum(if(cohort_day = '2023-07-15' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-15' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_15,
    sum(if(cohort_day = '2023-07-16' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-16' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_16
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-07-11' and '2023-07-16'
    and days_post_attribution <= 7
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Exemple Excel**

| Géo | Total des conversions | ARPU Jour 7 pour 11/07/2023 | ARPU Jour 7 pour 12/07/2023 | ARPU Jour 7 pour 13/07/2023 | ARPU Jour 7 pour 14/07/2023 | ARPU Jour 7 pour 15/07/2023 | ARPU Jour 7 pour 16/07/2023 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Corée du Sud | 120.660 | 7.798,89 $ | 6.997,37 $ | 8.258,95 $ | 9.050,21 $ | 10.018,04 $ | 13.765,73 $ |
| Canada | 35.099 | 64.867,84 $ | 7.050,19 $ | 5.656,33 $ | 9.553,75 $ | 8.632,41 $ | 11.308,06 $ |
| Chili | 26.750 | 48.160,02 $ | 21.249,55 $ | 22.584,57 $ | 24.033,07 $ | 31.118,91 $ | 41.145,22 $ |

</Accordion>

## Informations supplémentaires

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique |  |
| --- | --- |
| Données de coûts | Non disponible. <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports">Utilisez Cost ETL.</Anchor> |
| Changements de nom de campagne | Pas de prise en charge. |
| Actualisation des données | UTC quotidien Les rapports se trouvent dans le dossier date-heure (dt) de Data Locker du jour de rapport avant 10h00 UTC le lendemain. |
| Revenus publicitaires | <ul><li>Disponible</li><li>Pour les événements af\_ad\_revenue, la mesure des utilisateurs uniques n'est pas disponible pour les dates comprises entre le 5 octobre 2022 et le 16 février 2023.</li></ul> |
| Devise | L’USD et la devise spécifique à l’application sont toutes deux disponibles par ligne |
| Fuseau horaire | <ul><li>UTC</li><li>Le fuseau horaire spécifique à l'application est disponible dans la version bêta.</li></ul> |
| Données organiques | Disponible |
| Jours après la conversion (installation, réattribution, réengagement) | <ul><li>365 jours de données post-installation sont disponibles.</li><li>1 095 jours sont disponibles avec la version bêta.</li></ul> |
| Transparence de l'agence | <ul><li>Pris en charge</li><li>Les données des publicités X et Meta sont toujours transparentes</li></ul> |
| Segmentation des apps | Pris en charge |
| Données SKAN | Non inclus. Cela signifie que les données sont fournies par les postbacks iOS. |
| Réinstallations | <ul><li>Si les événements survenus après la réinstallation sont considérés comme organiques non attribués :<ul><li>Ils ne sont inclus qu'à compter du 26 mai 2024. <Anchor target="_blank" href="/marketers/fr/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">En savoir plus</Anchor></li><li>La date d'installation attribuée aux événements organiques non attribués est la date de la première installation, à l'exception des événements liés aux revenus. <Anchor target="_blank" href="/marketers/fr/docs/measure-reinstalls#unattributed-organic-inapps">En savoir plus</Anchor></li></ul></li><li>S'ils sont attribués à la première installation, ils sont toujours inclus. <Anchor target="_blank" href="/marketers/fr/docs/measure-reinstalls#les-événements-in-app-et-leur-système-dattribution">En savoir plus</Anchor></li></ul> |

</Accordion>

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard">Tableau de bord des cohortes</Anchor>

<div data-zendesk-anchors="cohort-analytics-in-data-locker=analyse-des-cohortes-dans-data-locker 01H7WG3CA1DDAN79D1PBPE0RJ3=analyse-des-cohortes-dans-data-locker 01H7WG3CA1ZMNTGZ5B8FNXNC4A=enable-data-locker 01H7WG3CA179D6VCWYPCJ1G49M=facts 01H7WG3CA1R3PZCKSGWC90E7RC=report-structure 01H7WG3CA14PQ2PJ58FX8TE6ZH=dimensions metrics=m%C3%A9triques 01H7WG3CA24VQKFVP99S82GCXZ=m%C3%A9triques 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-calculating-retention=1-calcul-de-la-r%C3%A9tention h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-calcul-de-la-r%C3%A9tention 2-calculating-arpu-of-multiple-inapp-events=2-calcul-de-larpu-de-plusieurs-%C3%A9v%C3%A9nements-dans-lapplication h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-calcul-de-larpu-de-plusieurs-%C3%A9v%C3%A9nements-dans-lapplication 3-calculating-inapp-event-conversion-rate-for-a-specific-cohort-day=3-calcul-du-taux-de-conversion-des-%C3%A9v%C3%A9nements-in-app-pour-un-jour-de-cohorte-sp%C3%A9cifique h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-calcul-du-taux-de-conversion-des-%C3%A9v%C3%A9nements-in-app-pour-un-jour-de-cohorte-sp%C3%A9cifique 4-calculating-daily-installs=4-calcul-des-installations-quotidiennes h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-calcul-des-installations-quotidiennes 5-calculating-revenue-from-facebook-ads=5-calcul-des-revenus-%C3%A0-partir-des-publicit%C3%A9s-facebook h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-calcul-des-revenus-%C3%A0-partir-des-publicit%C3%A9s-facebook 6-calculating-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-calcul-de-larpu-par-id-de-mot-cl%C3%A9-asa-pour-un-maximum-de-365-jours-de-cohorte h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-calcul-de-larpu-par-id-de-mot-cl%C3%A9-asa-pour-un-maximum-de-365-jours-de-cohorte calculating-arpu-days-0-7-by-attribution-time-per-geo=7-calcul-du-arpu-revenu-moyen-par-utilisateur-%C3%A0-j7-par-heure-dattribution-et-par-zone-g%C3%A9ographique 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-calcul-du-arpu-revenu-moyen-par-utilisateur-%C3%A0-j7-par-heure-dattribution-et-par-zone-g%C3%A9ographique additional-information=informations-suppl%C3%A9mentaires 01H7WG3CA255TG9HW150RW1QTX=informations-suppl%C3%A9mentaires 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=articles-connexes" />
