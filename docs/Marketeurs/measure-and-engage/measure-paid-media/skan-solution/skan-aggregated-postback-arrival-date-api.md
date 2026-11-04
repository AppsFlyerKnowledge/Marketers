---
title: API de date d'arrivée de postback agrégé SKAN
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-12-21T09:03:09Z'
  edited_at: '2024-09-19T12:50:53Z'
  id: 360016646557
  locale: fr
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/fr/articles/360016646557
---
> **En bref :** Postbacks SKAdNetwork agrégés par l'intermédiaire de l'API. Les données sont agrégées à l'aide de la date d'arrivée des postbacks.

<div id="skan-aggregated-postback-arrival-date-api" />

## API de date d'arrivée de postback agrégé SKAN

L'API renvoie les postbacks SKAdNetwork agrégés, en utilisant leur plage de dates d'arrivée.

**Remarque** ! La date d'arrivée des postbacks diffère de la date d'installation utilisée dans le tableau de bord et les rapports SKAdNetwork.

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="Utilisation de l'API de rapport de performance agrégé SKAN">

**Pour utiliser l'API de rapport de performance agrégé SKAN** :

1. Obtenez le jeton API. Un administrateur doit récupérer le jeton.
2. Donnez à votre développeur le jeton API à utiliser dans l'en-tête d'authentification.
3. Fournissez à vos développeurs les paramètres à saisir lors de l'appel d'API, comme décrit dans la section suivante. Les paramètres déterminent les éléments sur lesquels se concentre le rapport, comment il est organisé et ils fournissent un calendrier de reporting.
4. Demandez à votre développeur de suivre leur <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-postback-arrival-date-api-get">API de rapport de performance agrégé SKAN</Anchor> dans le hub des développeurs.

<div id="parameters" />

#### Paramètres

| Nom du paramètre | Détails | Obligatoire |
| --- | --- | --- |
| `start_date` | La plage de dates d'arrivée des postbacks est délimitée par start\_date et end\_date. Remarque! La date d'arrivée diffère de la date d'installation utilisée dans le tableau de bord et les rapports SKAdNetwork.<ul><li>AAAA-MM-JJ</li><li>Date la plus ancienne autorisée : 2020-11-01<br />Exemple: `2020-11-05`</li></ul> | Oui |
| `end_date` | <ul><li>AAAA-MM-JJ</li><li>Nombre maximum de jours par appel de rapport : 60 jours</li><li>Exemple: `2020-11-12`</li></ul> | Oui |
| `ad_network_name` | Filtrer par source média | Non |
| `geo` | Filtrer par code pays en utilisant ISO 3166 (alpha-2). Exemple : `US`, `CN` | Non |
| `skad_redownload` | Filtrer par `true` ou `false` | Non |
| `skad_source_app_id` | Filtrer par ID d'application source | Non |
| `ad_network_campaign_id` | Filtrer par ID de campagne de réseau publicitaire.<br /><br />**Remarque** : Ceci n'est pas l'ID de campagne signalé par SKAdNetwork. | Non |
| `modeled_conversion_values` | <ul><li>Pris en charge uniquement à partir de la version 2</li><li>La valeur peut être soit  soit</li><li>Si `true`, le postback remplit la colonne « count » avec des données de valeur de conversion modélisées.  [Voir le champ disponible pour les données modélisées](/docs/skan-aggregated-postback-arrival-date-api#report-structure-and-example)</li><li>Si , le postback présente le nombre de valeurs de conversion et tous les champs disponibles tels que reçus, répertoriés dans la structure du rapport, sans données modélisées.</li><li>La valeur par défaut est .</li></ul> | Non |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="Structure et exemple de rapport">

L'API retourne un fichier CSV.

Les colonnes et les mesures disponibles sont listées dans le tableau ci-dessous.

Exemples : <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRXgsWlkyvMS20HgZuOQnH1YC8QQcRhOMYIOxyj_fcgikfDfmW6wNAMHO6alPWVA1j_KZwtqowohqrK/pub?gid=0&single=true&output=csv">V1</Anchor> | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRMFEELm8JCAQBBAIJqAc1eE5YdN0kOcSVkOPd_Ki2ngnX61wHL4sXypVouOhto8u-JCQmdIYY_5UG6/pub?gid=219191499&single=true&output=csv">V2</Anchor>

| Nom de la colonne | Dimension ou mesure | Disponible avec le jeton API V1 | Disponible avec le jeton API V2 | Disponible avec le jeton API V2 (pour SKAN 4) | Disponible avec le filtre de données modélisées uniquement |
| --- | --- | --- | --- | --- | --- |
| index\_de\_séquence\_de\_postback\_skad | Regrouper par | N | N | O | O |
| valeur\_de\_conversion\_skad | Regrouper par | O | O | O | O |
| valeur\_grossière\_de\_conversion\_skad | Regrouper par | N | N | O | O |
| identifiant\_réseau\_skad\_ad<br /><br />Certains SRN ne partagent pas leur identifiant avec nous. Dans ce cas, le champ est vide et nom\_du\_réseau\_publicitaire est renseigné. | Regrouper par | O | O | O | O |
| nom\_du\_réseau\_publicitaire<br /><br />Actuellement, dans la plupart des cas, ce champ est vide. Nous le renseignons dans le cas des SRN qui ne partagent pas leur identifiant\_réseau\_skad\_ad. | Regrouper par | O | O | O | O |
| identifiant\_source\_skad | Regrouper par | N | N | O | O |
| identifiant\_campagne\_skad | Regrouper par | O | O | O | O |
| identifiant\_campagne\_réseau\_publicitaire | Regrouper par | O | O | O | O |
| nom\_campagne\_réseau\_publicitaire | Regrouper par | O | O | O | O |
| identifiant\_adset\_réseau\_publicitaire | Regrouper par | N | O | O | O |
| nom\_adset\_réseau\_publicitaire | Regrouper par | N | O | O | O |
| identifiant\_pub\_réseau\_publicitaire | Regrouper par | N | O | O | N |
| nom\_pub\_réseau\_publicitaire | Regrouper par | N | O | O | N |
| créatif\_réseau\_publicitaire | Regrouper par | N | N | O | N |
| canal\_réseau\_publicitaire | Regrouper par | N | N | O | N |
| version\_skad | Regrouper par | O | O | O | N |
| skad\_redownload | Regrouper par | O | O | O | N |
| identifiant\_app\_source\_skad | Regrouper par | O | O | O | N |
| domaine\_source\_skad | Regrouper par | N | N | O | O |
| type\_de\_fidélité\_skad | Regrouper par | N | O | O | N |
| géolocalisation | Regrouper par | O | O | O | N |
| date\_d'arrivée | Regrouper par | O | O | O | O |
| compter | Mesure | O | O | O | O |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Spécifications et limitations">

| Spécifications | Remarques |
| --- | --- |
| Actualisation des données | Le rapport est mis à jour <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#eod">quotidiennement.</Anchor><br /><br />La disponibilité des données dépend du taux d’actualisation des données <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#skan">SKAdNetwork</Anchor>. |
| Plage de dates | <ul><li>Date la plus ancienne prise en charge : Novembre 1, 2020</li><li>Plage de requête maximale : 60 jours</li></ul> |
| Limite de taux | <ul><li>Les requêtes retournent jusqu'à 200 000 lignes</li><li>60 appels par minute</li></ul> |
| SRN | Google Ads : La date d'arrivée du postback est déterminée à partir de l'heure du dernier clic rapportée par Google. |
| Accès au réseau publicitaire | Disponible pour les partenaires analytiques si l'annonceur donne son autorisation. |
| Accès aux agences | Non disponible |
| Fuseau horaire spécifique à l'application | UTC uniquement |
| Devise spécifique à l'application | Toujours en USD |
| Données organiques | Non disponible avec cette API |
| Données non organiques | Calculé à partir des postbacks SKAdNetwork reçus par AppsFlyer |
| Données historiques | Données de conversion les plus anciennes (installation ou reciblage) prises en charge : 1er novembre 2020 |
| Accès utilisateur du compte | Le jeton d'autorisation est disponible pour un utilisateur administrateur dans le tableau de bord. |

</Accordion>

<div id="see-also" />

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/skan-aggregated-performance-report-api">API de rapport des performances agrégées SKAN</Anchor>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=api-de-date-darriv%C3%A9e-de-postback-agr%C3%A9g%C3%A9-skan h_01HDNZKFEHWET0FPX9WN136MB2=api-de-date-darriv%C3%A9e-de-postback-agr%C3%A9g%C3%A9-skan h_01HDNZKFEH76Y06091QS6Y5K1Z=using-skan-aggregated-performance-report-api parameters=param%C3%A8tres h_01HDNZKFEHA6N6EE4RMG0HGABA=param%C3%A8tres h_01HDNZKFEHM2D7GS3RMSRCKZY7=report-structure-and-example h_01HDNZKFEJ5P3245V1R99DGAQW=specifications-and-limitations h_01HDNZP87CWGVJ3G1BDXAR1WN0=articles-connexes" />
