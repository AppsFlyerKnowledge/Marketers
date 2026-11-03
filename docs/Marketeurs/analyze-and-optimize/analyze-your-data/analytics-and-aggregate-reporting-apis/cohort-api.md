---
title: API de cohorte
metadata:
  keywords:
    - API
    - Advertisers
    - Partners
    - Developer
    - Premium
    - Gray
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2020-01-14T07:04:32Z'
  edited_at: '2023-11-22T12:30:34Z'
  id: 360004799057
  locale: fr
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/fr/articles/360004799057
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** L'API de rapports des cohortes donne aux annonceurs un moyen pratique pour obtenir les données de cohorte. L'API permet d'intégrer les données de cohorte dans les BI et les systèmes d'automatisation marketing.

## API de rapports des cohortes

L'API de rapports des cohortes permet d'obtenir les performances des campagnes de cohorte depuis la plateforme AppsFlyer. Elle fonctionne comme le <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard">tableau de bord des cohortes</Anchor>.

### À l'attention des développeurs

* **Dates :** les dates ou périodes se réfèrent aux dates de lifetime (<Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV</Anchor>), c'est-à-dire à la date d'attribution (conversion) de l'utilisateur et non celle de l'activité elle-même.
* **Valeurs booléennes :** doit être *true* ou *false* (sensible à la casse).
* **Trafic d'agence transparent et non transparent :** la source média du trafic issue d'une agence correspond toujours à l'agence et non à la source média d'origine. Pour l'instant, la version de cohorte UI de cohorte se comporte différemment.
* **Application unique** : l'API de Cohorte est une solution pour application unique. Elle contraste avec le tableau de bord de cohorte qui prend en charge plusieurs applications pour même appel.
* **Actualisation des données :** cf [caractéristiques et limitations](/docs/cohort-api#traits-and-limitations).

## Mode d'emploi de l'API

Les sections contiennent les informations pour générer et utiliser l'API de Cohorte. 

<div id="cohort-api-facts" />

<Accordion title="Faits relatifs à l'API de cohorte">

| Présentation | L'appel de l'API se compose du chemin d'accès, d'en-têtes et d'un JSON contenant la demande de données. Les données sont renvoyées par défaut dans un fichier CSV. |
| --- | --- |
| Chemin | `https://hq1.appsflyer.com/api/cohorts/v1/data/app/app_id` |
| Paramètres du chemin d'accès (obligatoire) | <ul><li>`app_id` : l'identifiant de l'application tel qu'il apparaît dans le tableau de bord d'AppsFlyer. Utilisez-le exactement tel qu'il s'affiche dans le tableau de bord.</li></ul> |
| Paramètres de requête<br /><br />(facultatif) | Les résultats sont renvoyés au format CSV ou JSON. La structure du fichier CSV est en tableau, tandis que celle du fichier JSON est conçue pour être enregistrée.<ul><li>[Défaut] <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360006698277">`csv`</Anchor> le [nom du fichier](/docs/cohort-api#csv-file-name-structure) dépend de la requête.</li><li>`json` contenant une requête et une partie résultat</li><li>Exemple : `format=json`</li><li>`https://hq1.appsflyer.com/api/cohorts/v1/data/app/app_id?format=json`</li></ul> |
| Méthode HTTP | `POST` |
| Types de contenu acceptés | `application/json` |
| Autorisation | <ul><li>Jeton porteur dans l'en-tête de la requête</li><li>Contactez votre CSM pour activer l'API de Cohorte et <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">obtenir le jeton depuis le tableau de bord</Anchor>.<ul><li>Le même jeton est utilisé pour l'ensemble des apps du compte.</li></ul></li></ul> |
| Limites dans le temps | <ul><li>La date la plus ancienne prise en charge, 730 jours avant la date du jour (c'est à dire 2 ans).</li><li>Période de requête maxi : 60 jours.</li></ul> |
| Limitation de taux | <ul><li>Débit d'appel d'API limité à 60 appels par minute et 50 000 appels par jour et par compte</li><li>Les requêtes renvoient jusqu'à 30 000 lignes</li></ul> |
| Valeurs booléennes | Toujours en minuscules : *true*, *false* |

### En-têtes de requête

| Clé | valeur | Obligatoire |
| --- | --- | --- |
| Type de contenu | `application/json` | Oui |
| Authorization | `Porteur api_token_placeholder` | Oui |
| Accepter | `application/json` | Oui |

</Accordion>

<div id="filtering-and-grouping-parameters" />

<Accordion title="Paramètres de filtrage et de regroupement">

Utilisez les paramètres de filtrage suivants pour obtenir les données nécessaires. 

| Nom du paramètre | Description | Obligatoire |
| --- | --- | --- |
| <span id="cohort-_type"></span>cohort \_type | Le type d'attribution de cohorte (conversion) est l'un des suivants : `user_acquisition`, `retargeting`, `unified`<ul><li>Unifiée : somme des performances de campagnes d'acquisition d'utilisateurs et de retargeting.</li><li>Si un événement est attribué à la fois à des campagnes de retargeting et d'acquisition d'utilisateurs, seul l'événement de retargeting est inclus dans les KPI, c'est à dire *<Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">is\_primary=true</Anchor>.*</li><li>Format : chaîne</li><li>Exemple : `"cohort_type": "user_acquisition"`</li></ul> | Oui |
| <span id="min_cohort_size"></span>min\_cohort\_size | La taille minimum de cohorte permet de réduire le nombre d'enregistrements renvoyés vec des cohortes qui ont peu d'utilisateurs. Cela signifie que le KPI des *users* aura une valeur égale ou supérieure à celle spécifiée.<ul><li>Format : entier</li><li>Valeur minimum autorisée : 1. Ne jamais envoyer 0 (Zéro)</li><li>Par défaut : 1</li><li>Exemple : `"min_cohort_size": 50`</li></ul> | Non |
| <span id="from"></span>de | Seuil le plus bas de la période d'attribution LTV La date la plus ancienne prise en charge, 720 jours avant la date actuelle.<ul><li>Format : chaîne aaaa-mm-jj</li><li>Exemple : `"from": "2020-01-02"`</li></ul> | Oui |
| <span id="to"></span>to | Limite maximum de la période d'attribution LTV<ul><li>Nombre de jours dans la période : 1-31 jours</li><li>Pour un seul jour : les valeurs `from` et `to` sont identiques.</li><li>Format : aaaa-mm-jj</li><li>Exemple : `"from": "2020-01-01", "to": 2020-01-31` correspond à 31 jours.</li></ul> | Oui |
| <span id="granularity"></span>granularité | Granularité horaire pour les 72 heures précédentes en définissant  `"granularity": "hour"` et en réglant la durée entre `from` et `to` pour contenir l'heure de la journée.<ul><li>Format : aaaa-mm-jj hh:mm:ss</li><li>Exemple :</li></ul>`"granularity": "hour","from": "2021-12-01 14:00:00", "to": "2021-12-03 11:00:00",` | Non |
| <span id="partial_data"></span>partial\_data | Pour éviter les erreurs d'interprétation, la cohorte renvoie les données des jours complets. Les données des jours partiels peuvent cependant aussi être utiles.<br /><br />Le nombre de jours de cohorte complets pour une requête est calculé en soustrayant la date du jour de la date qui correspond à *to*.<ul><li>[Par défaut] Si *false*, renvoie les jours complets.</li><li>Si *true*, jusqu'à 180 jours de cohorte sont renvoyés, ce qui inclut les jours où les données sont incomplètes.</li><li>Format : booléen</li><li>Version de l'UI de la plateforme : false</li></ul>**Exemple** : au 10 mai, le nombre de jours de cohorte complets pour les utilisateurs convertis entre le 1er et le 30 avril est de 10.<ul><li>Si false [défaut], les jours de cohorte 0-9 sont renvoyés. C'est le nombre de jours (10) entre la dernière date de conversion et la date du jour.</li><li>Si true, les jours de cohorte 1 à 40 sont renvoyés. Les jours 11 à 40 contiennent des données partielles et ne sont pas renvoyés. Par exemple, depuis le 20 avril, il ne s'est écoulé que 20 jours, etc.</li></ul>**Remarque** : les données partielles ne sont autorisées que lorsque le type d'agrégation est cumulatif. | Non |
| <span id="filters"></span>Filtres | Filtrer les données et les jours de période renvoyés. Sélectionnez les filtres dans la [liste des dimensions de filtre](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).<ul><li>Format : chaînes de caractères dans un JSON imbriqué</li><li>**Exemple de limitation pour certains géos :** `"filters":``{"geo": "US"}`n'inclut que les utilisateurs attribués aux États-Unis.</li><li>**Exemple de jours de période (cohorte)** : le filtre `period` définit les jours où les mesures sont renvoyées. Les valeurs possibles sont comprises entre 0 et 180.</li><li>Défaut : si aucun filtre de période n'est défini, les jours 0-30, 60, 90 et 180 s'affichent. [Exemple de filtre avec période](/docs/cohort-api#using-period-filters)</li></ul> | Non |

Utilisez les paramètres de regroupement suivants pour inclure des colonnes supplémentaires et diminuer la granularité de vos rapports.

| Paramètre | Valeurs | Obligatoire |
| --- | --- | --- |
| regroupements | <ul><li>Sélectionnez 1 à 7 regroupements dans la [liste des dimensions de regroupement](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).</li><li>Format : ensemble de chaînes</li><li>Example: `"groupings": ["af_ad", "c", "af_c_id", "af_prt"]`</li></ul> | Oui |

</Accordion>

<div id="selecting-and-formatting-kpis" />

<Accordion title="Sélectionner et formater les KPI">

* Le tableau énumère les KPI disponibles avec les fonctionnalités. Lorsque vous appelez un KPI, toutes ses fonctionnalités sont renvoyées.
* Les KPI suivants sont toujours renvoyés : utilisateurs, ecpi et coût.
* Sélectionnez un KPI supplémentaire par appel.

<table><thead><tr><th> </th><th> </th><th colspan="5">Fonctions</th></tr><tr><th rowspan="2">Défaut / Facultatif </th><th rowspan="2">V (nom des dimensions) </th><th>Décompte</th><th>cvr (taux de conversion)</th><th>Taux</th><th>Total</th><th>Utilisateurs uniques</th></tr><tr><th>Nombre</th><th>Pourcentage</th><th>Pourcentage</th><th>Nombre</th><th>Nombre</th></tr></thead><tbody><tr><td>Toujours</td><td>utilisateurs</td><td><span>Y</span></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Toujours</td><td>eCPI</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>Toujours</td><td>coût</td><td>-</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>OPTIONNEL</td><td><span><code>"event_name"</code>(4) </span></td><td><span>Y</span></td><td><span>Y</span></td><td>-</td><td><span>Y (3)</span></td><td><span>Y</span></td></tr><tr><td>OPTIONNEL</td><td>revenus</td><td><span>Y</span></td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>OPTIONNEL</td><td>ROAS</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>OPTIONNEL</td><td>roi</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>OPTIONNEL</td><td>Sessions</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td><span>Y(1)</span></td></tr><tr><td>OPTIONNEL</td><td>désinstallations (2)</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr></tbody><tfoot><tr><td colspan="7"><p>(1) Les sessions uniques se réinitialisent lorsque <em>aggregation_type=on_day</em></p><p>(2) Non disponible lorsque cohort_type=unified </p><p>(3) La somme correspond au revenu total généré par l'événement. Dans le rapport, il est désigné par <span><code>sum_event_name</code></span>)</p><p><span>Attention : les noms d'évènements sont sensibles à la casse.</span></p></td></tr></tfoot></table>

| Paramètre | Valeurs | Paramètre obligatoire |
| --- | --- | --- |
| KPIs | Sélectionnez **un** KPI parmi les KPI disponibles. À l'avenir, nous prévoyons d'autoriser la sélection de plusieurs KPI.<ul><li>Pour chaque KPI demandé, toutes les fonctionnalités sont renvoyées.</li><li>Format : ensemble de chaînes</li><li>Example A: `"kpis": ["sessions"]`</li><li>Exemple B : `"kpis": ["event_name"]`</li></ul> | Oui |

### Présentation des fonctionnalités du KPI

Les formats de paramètres des KPI P suivants définissent le format des KPI renvoyés.

| Paramètre | Valeurs | Obligatoire |
| --- | --- | --- |
| preferred\_currency | Devise du revenu de KPI<ul><li>Si true, les revenus sont renvoyés en utilisant la <Anchor target="_blank" href="/marketers/fr/docs/app-settings#localization-currency">devise propre à l'app</Anchor> qui a été définie sur la plateforme.</li><li>[Défaut] Si false, les résultats sont affichés en USD.</li><li>Format : booléen</li><li>Version de l'UI de plateforme : true</li></ul> | Non |
| preferred\_timezone | **Fuseau horaire des périodes de données**<ul><li>Si true, les heures sont exprimées dans le <Anchor target="_blank" href="/marketers/fr/docs/app-settings#localization-time-zone">fuseau horaire propre à l'application</Anchor> qui a été défini sur la plateforme.</li><li>[Par défaut] Si false, les heures sont affichées dans le format UTC.</li><li>Format : booléen</li><li>Version de l'UI de plateforme : true</li></ul> | Non |
| aggregation\_type | <ul><li>`Cumulé`</li><li>`on_day`</li></ul>`"aggregation_type": "cumulative"`<br /><br />`Format: String` | Oui |
| per\_user | Divisez la fonction du KPI par le nombre d'utilisateurs de l'app. Ne s'applique qu'aux KPI concernés.<ul><li>Si true, les valeurs du KPI sont divisées par le nombre d'utilisateurs de la cohorte.</li><li>Si false, les valeurs du KPI ne sont pas divisées par le nombre d'utilisateurs.</li><li>Format : booléen</li><li>Exemple si true : le revenu total est de 1000 $, le nombre d'utilisateurs de l'application est de 500, la valeur renvoyée est donc 2 $.</li></ul> | Non |

</Accordion>

<div id="list-of-group-by-and-filter-by-dimensions" />

<Accordion title="Liste des dimensions de regroupement et de filtrage">

<table><tbody><tr><th><p>Nom de la dimension </p></th><th><p>Valeurs des dimensions d'API</p></th><th><p>Regroupements</p></th><th><p>Filtres</p></th></tr><tr><td><p><span>Publicité</span></p></td><td><p><span>af_ad</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Identifiant de publicité</span></p></td><td><p><span>af_ad_id</span></p></td><td><p><span>Y</span></p></td><td><span><span>Y</span></span></td></tr><tr><td><p><span>Campagne</span></p></td><td><p><span>C</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Identifiant de la campagne</span></p></td><td><p><span>af_c_id</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Canal</span></p></td><td><p><span>af_channel</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Source média</span></p></td><td><p><span>PID</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Sous-paramètre 1</span></p></td><td><p><span>af_sub1</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Mots-clés</span></p></td><td><p><span>af_keywords</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>agences</span></p></td><td><p><span>af_prt</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Type de conversion (1) </span></p></td><td><p><span>cohort_type</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>ID site</span></p></td><td><p><span>site_id</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Type de revenu (2)</span></p></td><td><p><span>revenue_type</span></p></td><td><p><span><span>x </span></span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Type de touch attribué (3)</span></p></td><td><p><span>attributed_touch_type</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Ensemble de publicités</span></p></td><td><p><span>af_adset</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Identifiant de l'ensemble de publicités</span></p></td><td><p><span>af_adset_id</span></p></td><td><p><span>Y</span></p></td><td><span> Y</span></td></tr><tr><td><p><span>Pays</span></p></td><td><p><span>geo</span></p></td><td><p><span>Y</span></p></td><td><span>Y</span></td></tr><tr><td><p><span>Date (date d'installation/d'attribution/d'engagement pour le type de cohorte sélectionné) </span></p></td><td><p><span>date</span></p></td><td><p><span>Y</span></p></td><td><span><span>x </span></span></td></tr><tr><td><p>Période</p></td><td><p><span>période </span><span></span></p><p><a href="./cohort-api#using-period-filters">Explication détaillée</a></p></td><td><p><span><span>X</span></span></p></td><td><p><span>Y</span></p></td></tr><tr><td colspan="4"><p>Remarque :</p><p>Options de dimensions :</p><p>(1) Type de conversion :  <span><code>user_acquisition</code>, <code>retargeting</code>(<code>re-engagement</code> et <code>re-attribution</code>), </span><span><code>unified</code></span></p><ul><li> <span>Lors de l'exportation :</span><ul><li><span>le <code>re-engagement</code> sera considéré comme <code>retargeting</code></span></li><li><span><code>re-attribution</code> s'affichera sous <code>reattr</code></span></li></ul></li></ul><p>(2) Type de revenu : <code>regular</code>, <code>ad_monetization</code><span></span></p> (3) Type de touch attribué : <code>clic</code>, <code>impression</code>, <code>TV</code>, <code>pre-installed</code> </td></tr></tbody></table>

</Accordion>

<div id="curl-example" />

<Accordion title="Exemple en curl">

Cet exemple contient un appel d'API complet.

```shell
curl -L -X POST 'https://hq1.appsflyer.com/api/cohorts/v1/data/app/<insert your app_id here>?format=<insert results format here>' \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <cohort_api_token_placeholder. Note the token has more than 700 characters.>' \
-H 'Accept: application/json' \
--data-raw '{
    "cohort_type": "user_acquisition",
    "min_cohort_size": 1,
    "preferred_timezone": false,
    "from": "2020-01-01",
    "to": "2020-01-31",
    "filters": {
        "period": [
            0,
            1,
            2,
            10,
            30,
            60
        ],
        "geo": [
            "US",
            "CN"
        ],
        "pid": [
            "Meta ads",
            "googleadwords_int"
        ]
    },
    "preferred_currency": true,
    "aggregation_type": "on_day",
    "per_user": false,    
    "groupings": [
        "pid",
        "date"
    ],
    "kpis": [
        "sessions"
    ]
}'
```

Exemples de fichiers renvoyés : <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360006698277">CSV</Anchor>, <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360006773078">JSON</Anchor>

</Accordion>

<div id="python-example" />

<Accordion title="Exemple Python">

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("hq1.appsflyer.com")
payload = "{\r\n    \"cohort_type\": \"user_acquisition\",\r\n    \"min_cohort_size\": 1,\r\n    \"preferred_timezone\": false,\r\n    \"from\": \"2020-05-01\",\r\n    \"to\": \"2020-05-10\",\r\n    \"preferred_currency\": true,\r\n    \"aggregation_type\": \"cumulative\",\r\n    \"per_user\": false,   \r\n     \"groupings\": [\r\n               \"pid\",\r\n         \"date\"\r\n        ],\r\n    \"kpis\": [\r\n        \"roas\"\r\n    ]\r\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer [Enter token here]',
  'Accept': 'application/json',
  'Content-Type': 'application/json'
}
conn.request("POST", "/api/cohorts/v1/data/app/[My App ID here]?format=csv", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

</Accordion>

<div id="use-case-examples" />

<Accordion title="Exemples pratiques">

**Exemple 1 : rétention**

Rétention des sources média (sessions) des utilisateurs qui ont installé l'application en janvier, aux jours 7, 14 et 28.

```json
{
  "per_user": false,
  "groupings": [
    "pid"
  ],
  "filters": {
    "period": [
      7, 14, 28
    ]
  },
  "partial_data": false,
  "aggregation_type": "on_day",
  "min_cohort_size": 1,
  "cohort_type": "user_acquisition",
  "from": "2021-01-01",
  "to": "2021-01-30",
  "kpis": [
    "sessions"
  ]
}
```

**Exemple 2 : achats de campagne**

Revenu post-installation du jour 3 de cohorte par campagne

```json
{  
  "per_user": false,
  "groupings": [
    "c"
  ],
  "filters": {
    "period": [
      3
    ],
    "c":[
        "example_campaign_name"
    ]
  },
  "partial_data": false,
  "aggregation_type": "cumulative",
  "min_cohort_size": 1,
  "cohort_type": "user_acquisition",
  "from": "2021-01-01",
  "to": "2021-01-30",
  "kpis": [
    "Checkout Start"
  ]
}
```

**Exemple 3 : Activité d'hier**Quelle activité ont effectué les utilisateurs convertis (installés, réengagés, réattribués) au cours d'une période de conversion donnée ?

Utiliser les données disponibles via <Anchor target="_blank" href="/marketers/fr/docs/cohort-analytics-via-data-locker">Cohorte pour Data Locker</Anchor>. La période de conversion est limitée aux 360 jours précédents.

</Accordion>

## Informations supplémentaires

<div id="response-codes-and-troubleshooting" />

<Accordion title="Codes de réponse et dépannage">

| Code de réponse | Message | Remarque |
| --- | --- | --- |
| 200 | OK | Données valides renvoyées |
| 200 | OK | <ul><li>Aucune donnée n'est renvoyée<ul><li>La requête était valide, mais aucune donnée correspondant à la requête n'a été trouvée.</li><li>Vérifiez que la période n'inclut pas de dates en dehors de la période.</li><li>Aucun jeton n'a été envoyé lors de l'appel.</li></ul></li></ul> |
| 401 | Non autorisé | <ul><li>Le jeton d'autorisation est incorrect. Vérifiez que vous utilisez le bon jeton, qui doit comporter plus de 700 caractères.</li></ul> |
| 404 | Pas de résultat | <ul><li>Éliminez tout problème lié au réseau, pare-feu, etc.</li><li>Assurez-vous que vous utilisez bien le jeton le plus récent. Récupèrez le jeton depuis le tableau de bord.</li><li>Assurez-vous que l'application spécifiée dans le chemin d'accès est autorisée à utiliser l'API de Cohorte. Ce qui signifie qu'elle doit faire partie de votre forfait. Un admin de compte AppsFlyer pourra vérifier si c'est le cas dans la rubrique Mon forfait.</li></ul> |
| 422 | Entité non traitable | Les raisons fréquentes pour ce code d'erreur sont les suivantes :<ul><li>Assurez-vous que la demande est contenue dans un JSON et qu'elle n'est pas envoyée en tant que paramètres de requête.</li><li>Veillez à ce que le format JSON soit conforme au présent document.</li><li>Date illégale</li></ul> |

</Accordion>

<div id="csv-file-name-structure" />

<Accordion title="Structure du nom de fichier CSV">

Le nom attribué à un fichier CSV est généré à partir de la requête d'API. La du fichier structure est détaillée dans le tableau suivant.

**Exemple de nom de fichier CSV**

```
cohort_aggregation_type_per_user_kpi_report_app_id_from_to_timezone_currency_hash.csv
```

| Variable | Valeurs possibles |
| --- | --- |
| aggregation\_type | <ul><li>*on\_day*</li><li>*Cumulé*</li></ul> |
| per\_user | <ul><li>*per\_user*</li><li>false: Null</li></ul> |
| KPI | Exemple : sessions |
| app\_id | L'ID d'app appelée |
| from | **from** date : format *aaaa-mm-jj* |
| to | **to** date : format *aaaa-mm-jj* |
| Fuseau horaire | Fuseau horaire par défaut UTC |
| devise | Code devise par défaut USD |
| hachage | Chaîne de hachage alphanumérique longueur=5 |

</Accordion>

<div id="using-period-filters" />

<Accordion title="Utilisation des filtres pour les périodes">

La période fait référence au jour suivant l'attribution, la période 0 correspondant au jour de l'attribution. Exemple, un utilisateur installe l'application au 1er janvier. C'est le jour de l'attribution. Un achat effectué au cours de la période 0 signifie qu'il a été effectué durant le 1er janvier. Un achat effectué à la période 3 signifie qu'il a été effectué le 4 janvier. De même, un utilisateur qui installe l'app le 11 janvier correspond à la période 0. Un achat effectué le 14 janvier correspond à la période 3.

Si la période couverte par votre rapport va du 1er au 11 janvier, les utilisateurs qui sont attribués (qui ont installé l'app) au cours de cette période sont compris dans le rapport. Aucune autre donnée n'est incluse.

* La valeur de la période peut être une ou plusieurs des nombres suivants compris entre 0 et 180. Par exemple 0, 1, 2, 30, 180.
* Si aucune période n'est spécifiée, les valeurs par défaut 0, 1, 2, etc jusqu'à 30, 60, 90 et 180 seront renvoyées.

> 📄 **Exemple de filtre de période**
>
> * Cet exemple contient les paramètres de la requête JSON, les données brutes et le fichier CSV résultant.
> * La requête *filters period* de 0, 1, et 2 et le KPI sélectionné est *revenue*.
> * Ainsi, les données renvoyées contiennent :
>   * Les mesures des utilisateurs, du coût et de l'ecpi qui sont systématiquement renvoyés
>   * Mesures des revenus consistant en la somme et le décompte pour chaque période, c'est-à-dire les périodes 0, 1 et 2.
>
> **Requête**
>
> ```json
> {
>     "cohort_type": "user_acquisition",
>     "min_cohort_size": 1,
>     "preferred_timezone": false,
>     "from": "2019-12-01",
>     "to": "2020-01-01",
>     "filters": {
>         "period": [
>             0,
>             1,
>             2
>         ]
>     },
>     "aggregation_type": "on_day",
>     "per_user": false,
>     "groupings": [
>         "pid"
>     ],
>     "kpis": [
>         "revenue"
>     ]
> }
> ```
>
> **Données Brutes**
>
> **![mceclip1.png](https://files.readme.io/846aade481d3b5fa72536817533bc3edad721f1ce6015edcb48bd500461342b9-32131110606865.png)**
>
> **Résultats**
>
> ![mceclip0.png](https://files.readme.io/c284e5133e4e811b9416c850e399ddefb3c5bfcfcf879f469556b7a6bc0062c6-32131110607249.png)

</Accordion>

<div id="user-interface-mapping-to-api-parameters" />

<Accordion title="Mapping entre l'interface utilisateur et les paramètres de l'API">

Les chiffres suivants matchent l'interface utilisateur d'analyse de Cohorte avec les paramètres de l'API. Les deux solutions - API et interface utilisateur - sont similaires mais pas complétement identiques.

La version API contient les options supplémentaires suivantes :

* Sélection de la devise
* Sélection du fuseau horaire
* Filtrage par période

[![CohortMapping.jpg](https://files.readme.io/28b5973a6c476407f342cbc55dbf03162fdd3047d4fd9b93b78a6de8dff11cdb-360012218018.jpg)](https://files.readme.io/28b5973a6c476407f342cbc55dbf03162fdd3047d4fd9b93b78a6de8dff11cdb-360012218018.jpg) [![Cohortmapping2.jpg](https://files.readme.io/59f2e9fd5120b7efbb81a937a42ee4a8145fd7ae74ddf855ec6ba13f061ba6c2-360006378018.jpg)](https://files.readme.io/59f2e9fd5120b7efbb81a937a42ee4a8145fd7ae74ddf855ec6ba13f061ba6c2-360006378018.jpg)

Différence entre les types d'agrégation

![CohortRevnueCumulative.jpg](https://files.readme.io/1c9ca17e217a941e989556637d4397147bac9d1ab65e7485a10c0757a70dec41-360006379038.jpg)

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Accès du ad network | Les <Anchor target="_blank" href="/partners/fr/docs/access-to-aggregated-analytics-tools-for-api-partners">partenaires de gestion de campagne</Anchor> peuvent utiliser l'API si l'annonceur leur en donne l'autorisation. |
| Autorisations de l'agence | Non |
| Transparence de l'agence | Non pris en charge |
| Fuseau horaire spécifique à l'app | Oui |
| Devise spécifique à l'app | Oui |
| Limitations de taille | Aucun |
| Limitation de taux | Limite d'appels d'API : 60 appels par minute et par compte |
| Données organiques | Disponible |
| Données non organiques | Disponible |
| Limitation des données de coûts | <ul><li>Les données de coûts ne concernent que les campagnes avec au moins une installation enregistrée.</li><li>AppsFlyer ne rapporte pas les données de coûts pour les mots-clés qui contiennent des lettres majuscules dans le rapport de cohorte ou l'API de cohorte</li><li>Certaines combinaisons de regroupement ne peuvent être associées au coût. Par exemple, les Meta Ads peuvent être regroupées par zone géo ou canal, mais pas les deux à la fois. Les combinaisons de regroupements dépendend du réseau publicitaire.</li></ul> |
| Actualisation des données | L'actualisation des données dépend de [*partial\_data*](/docs/cohort-api#partial_data) comme suit :<ul><li>[Défaut] Si false, <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#daily">quotidien</Anchor></li><li>Si true, <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">continu (en temps réel</Anchor>)</li><li>Les mesures de coût et de désinstallation sont mises à jour quotidiennement dans tous les cas.</li></ul> |
| Données historiques | Cohorte quotidienne : 2 ans |
| Accès utilisateur du compte | Le jeton d'autorisation est disponible pour les utilisateurs admin dans le tableau de bord. |
| Revenus publicitaires | Pour les événements af\_ad\_revenue, la mesure des utilisateurs uniques n'est pas disponible lorsque le type d'agrégation est réglé sur "on day," pour les dates comprises entre le 5 octobre 2022 et le 16 février 2023. |
| Regroupements hebdomadaires et mensuels | Le regroupement des dimensions hebdomadaires et mensuelles n'est pas disponible avec l'API de cohorte. Utilisez le tableau de bord de Cohorte. |
| API de cohorte | <ul><li>La période de conversion est désignée par 0 (heure 0 ou jour 0). La période qui suit la conversion est désignée par 1 (heure 1 ou jour 1), et ainsi de suite.</li><li>Dans AppsFlyer, une période de cohorte ne prend pas en compte l'heure de l'installation. Les heures de la cohorte sont arrondies à l'heure la plus proche et les jours de la cohorte sont basés sur le jour calendaire. Cela peut entraîner des divergences lorsque l'on compare les données de cohorte d'AppsFlyer aux données de cohorte d'autres réseaux, où toutes les périodes de cohorte sont déterminées par l'heure précise de l'installation (une heure correspond à 60 minutes après l'heure de l'installation, un jour correspond à la période de 24 heures après l'heure de l'installation, etc.)</li></ul> |

</Accordion>

<div data-zendesk-anchors="cohort-reporting-api=api-de-rapports-des-cohortes 01H7WFZR41YAQX4MFPBMJD1MBP=api-de-rapports-des-cohortes considerations-for-developers=%C3%A0-lattention-des-d%C3%A9veloppeurs 01H7WFZR414KXJBQS563VNKPXR=%C3%A0-lattention-des-d%C3%A9veloppeurs api-instructions=mode-demploi-de-lapi 01H7WFZR41SNPGFKRH6J5DJG95=mode-demploi-de-lapi 01H7WFZR4184TKQYEC4Q10D9HH=cohort-api-facts request-headers=en-t%C3%AAtes-de-requ%C3%AAte 01H7WFZR42NHX3N1V72VKP06ZR=en-t%C3%AAtes-de-requ%C3%AAte 01H7WFZR42H3CA0CSB4E3XED3H=filtering-and-grouping-parameters 01H7WFZR42XV4JY46GY11KT3CF=selecting-and-formatting-kpis presentation-of-kpi-functions=pr%C3%A9sentation-des-fonctionnalit%C3%A9s-du-kpi 01H7WFZR43HFF65TSWG1AN0JTB=pr%C3%A9sentation-des-fonctionnalit%C3%A9s-du-kpi 01H7WFZR43BJ8E6KVHSGV4CDDP=list-of-group-by-and-filter-by-dimensions 01H7WFZR448CBBZ3V7RT0PF072=curl-example 01H7WFZR44RBVB9Q6VZPG1EWNX=python-example 01H7WFZR44H0G3QCBRTRQ5Y0HD=use-case-examples additional-information=informations-suppl%C3%A9mentaires 01H7WFZR448RNM8539DD8WCBH0=informations-suppl%C3%A9mentaires 01H7WFZR441022SK7BQB00F0BJ=response-codes-and-troubleshooting 01H7WFZR443YKCSJTHJ9W6H2S3=csv-file-name-structure 01H7WFZR440NTXWWQ2T4P2ANWK=using-period-filters 01H7WFZR44RCXA56CXSCEZ0KXH=exemple-de-filtre-de-p%C3%A9riode 01H7WFZR45QFHJWXZAAX2HRXQ2=user-interface-mapping-to-api-parameters 01H7WFZR45VC96KYW1W9A8PBFT=traits-and-limitations" />
