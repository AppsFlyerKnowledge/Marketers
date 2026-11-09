---
title: ROI360—Présentation de l'agrégation des coûts
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2015-12-24T10:45:16Z'
  edited_at: '2024-05-26T08:18:59Z'
  id: 207040526
  locale: fr
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/fr/articles/207040526
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** Découvrez les méthodes permettant aux annonceurs de regrouper et de consulter les données relatives aux coûts marketing.

<Image align="center" alt="roi360_image.png" src="https://files.readme.io/1eaf922de9a1174c1971582dd32f53b995de014c8c2bf288b52a93c83334374e-11245891045777.png" />

<div id="cost-aggregation" />

## Agrégation des coûts

**ROI360** :

* Fournit des données globales sur les coûts publicitaires et des mesures de performance LTV liées aux coûts. Ces informations sont disponibles via des tableaux de bord et des rapports de performance. Les indicateurs de coût disponibles comprennent le ROI, le ROAS, les clics, les impressions, le ROI de la campagne et le coût effectif moyen par installation (eCPI) au fil du temps.
* Prise en charge des différents modèles de coûts utilisés par le partenaire, notamment CPI, CPA, CPC et CPM.
* Enregistre les coûts publicitaires par API, importation des coûts (téléchargement d'un fichier CSV) et <Anchor target="_blank" href="/marketers/fr/docs/view-aggregated-cost-data-for-attribution-links">coût par clic</Anchor>.
* Les agences peuvent accéder aux données de coûts ROI360 pour les annonceurs avec un abonnement ROI360.

Les indicateurs suivants sont disponibles pour les annonceurs ne disposant pas d'un abonnement à ROI360 :

* <Anchor target="_blank" href="/marketers/fr/docs/view-aggregated-cost-data-for-attribution-links">Données sur les coûts par clic</Anchor>.
* Données de clics et d'impressions du SRN, configurées via l'onglet **Coût** du partenaire intégré du SRN.

<div id="example" />

<div id="cost-in-the-unified-view" />

<div id="note" />

<div id="cost-in-the-ua-view" />

<div id="principles-of-cost-data-aggregation" />

## Principes de l'agrégation des données sur les coûts

Cette section décrit les principes clés de l'agrégation des données de coûts des campagnes.

<div id="cost-aggregation-methods" />

<Accordion title="Méthodes d'agrégation des coûts">

Les données sur les coûts sont obtenues auprès des partenaires par une ou plusieurs méthodes. Si les coûts sont déclarés par plusieurs méthodes, le[mécanisme de hiérarchisation des coûts](/docs/roi360-cost-aggregation-overview#cost-prioritization-mechanism)  détermine les données à utiliser. Cela permet de s'assurer que les données relatives aux coûts ne sont pas sur-évaluées.

Après qu'AppsFlyer ait traité les données, elles s'affichent par défaut en fuseau horaire UTC ou selon <Anchor target="_blank" href="/marketers/fr/docs/changing-app-time-zone-settings">les paramètres de fuseau horaire</Anchor>  spécifiques à votre application.

<table><thead><tr><th>Méthode d'agrégation des coûts</th><th>Modèles de coûts pris en charge</th><th>Granularité des données</th><th>Actualisation des données</th><th>Remarques</th></tr></thead><tbody><tr><td> <a href="./set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api" target="_blank">API</a>\*</td><td>Tous</td><td><p>Le niveau dépend de l'intégration</p></td><td><a href="./about-data-freshness-and-timezone-support#intraday-during-the-day" target="_blank">Dans la journée</a></td><td>Les données peuvent changer après l'événement de coût, car nous visons à recevoir des données jusqu'à 7 jours en arrière (en fonction du réseau publicitaire). Cela nous permet de prendre en compte les modifications rétroactives apportées par le réseau publicitaire.  </td></tr><tr><td><a href="./import-cost-data" target="_blank">Importation des coûts (téléchargement de fichiers)</a></td><td>Tous</td><td> <span>Le niveau </span><span>dépend du fichier téléchargé</span> </td><td>Jusqu'à 4 heures après l'importation</td><td>Les coûts déclarés peuvent être annulés et les données corrigées peuvent être soumises pendant 90 jours.</td></tr><tr><td> Lien d'attribution de <a href="./view-aggregated-cost-data-for-attribution-links" target="_blank">clics</a> </td><td>CPI</td><td>Niveau utilisateur</td><td><p>Minimum : temps réel</p><p>Maximum : Jusqu'à 4 heures après le clic</p></td><td>Pas de changement possible</td></tr><tr><td colspan="5">\* Les intégrations API entre les partenaires et AppsFlyer se font soit par Cost API, soit par InCost API (jamais les deux). L'API utilisée et la granularité des données fournies dépendent du partenaire.</td></tr></tbody></table>

</Accordion>

<div id="cost-data-availability-and-reports" />

<Accordion title="Disponibilité des données sur les coûts et rapports">

Le tableau suivant indique où les données sur les coûts sont disponibles.

Pour la compréhension du tableau, les explications suivantes s'appliquent, sauf indication spécifique présente dans l’onglet «remarque» de ce même tableau :

* UA : Données sur les coûts pour les campagnes d'acquisition d'utilisateurs avec au moins une installation récemment enregistrée (non attribuée par SKAN) (c'est-à-dire au cours des 7 derniers jours environ).
* Unifié : Données sur les coûts de toutes les campagnes de l'application sélectionnée, y compris celles pour lesquelles aucune installation n'a été enregistrée récemment (c'est-à-dire au cours des 7 derniers jours environ). Le tableau indique quand les données ne sont disponibles que pour les campagnes ayant au moins une installation récemment enregistrée.
* Si les changements de nom de campagne ne sont pas pris en charge, les deux noms de campagne s'affichent, l'un avec les données d'attribution, l'autre avec les données de coût. Aucun des noms de campagne affichés ne comprendra l'ensemble des données.

<div id="note-1" />

<div id="cost-data-availability-and-reports-table" />

#### Disponibilité des données sur les coûts et rapports

| Méthode de reporting | Vue/type de données | Support pour le changement de nom de la campagne | Remarques |
| --- | --- | --- | --- |
| Vue d'ensemble du tableau de bord | <ul><li>UA</li><li>Unifié</li></ul> | Oui | La vue retargeting n'affiche pas le coût. Coût du retargeting des écrans dans la vue unifiée. |
| Tableau de bord d'activité | UA | Oui |  |
| Tableau de bord des cohortes | <ul><li>UA</li><li>Unifié</li></ul> | Oui | <ul><li>La vue retargeting n'affiche pas le coût.</li><li>Ces données unifiées ne concernent que les campagnes avec au moins une installation récemment enregistrée.</li></ul> |
| API de cohorte | <ul><li>UA</li><li>Unifié</li></ul> | Oui | Ces données unifiées ne concernent que les campagnes avec au moins une installation récemment enregistrée. |
| Tableau de bord SKAN | SKAN | Non | Les installations SKAN s'affichent, ainsi que les données de coûts pour **toutes les** installations (y compris les installations non SKAN). |
| API de performances agrégées SKAN | SKAN | Non | Les installations SKAN s'affichent, ainsi que les données de coûts pour **toutes les** installations (y compris les installations non SKAN). |
| Tableau de bord croisé dynamique | UA | Non |  |
| API principale | UA | Non |  |
| Tableau de bord personnalisé | UA | Non |  |
| ETL des coûts | Unifié | Oui | Toutes les données disponibles sur les coûts s'affichent. |
| API Pull agrégée | UA | Non |  |
| API Push | Données brutes sur les clics (non agrégées) | Non valide |  |
| API Pull de données brutes | Données brutes sur les clics (non agrégées) | Non valide |  |
| Data Locker | Données brutes sur les clics (non agrégées) | Non valide | Data Locker Cohort ne prend pas en charge les coûts. |

**Remarque**:

* La granularité des données peut varier en fonction du type de dashboard/rapport. <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports">L'outil de reporting de coût ETL</Anchor> contient l'ensemble des données. Cela inclut les détails de la hiérarchie de la campagne (source média, nom de la campagne, adset, et les mesures mises à disposition par le réseau publicitaire, y compris la géolocalisation, le canal, l'ID du site et les mots-clés).
* Les données sur les coûts de clic sont disponibles dans les rapports de données brutes.

</Accordion>

<div id="cost-prioritization-mechanism" />

<Accordion title="Mécanisme de hiérarchisation des coûts">

Le coût peut être fourni par plus d'une méthode d'agrégation pour une source média donnée. Pour éviter l'inflation des coûts, un mécanisme de hiérarchisation des coûts de campagne permet de décider quelles données de coûts sont mises à disposition sur la plateforme. La priorité est donnée en fonction de la méthode d'agrégation. La priorité, de la plus faible à la plus élevée, est la suivante : Cliquez sur > Cost API > Cost Import

Le mécanisme de hiérarchisation des coûts a une incidence sur les rapports de données agrégées et les tableaux de bord. Les données sur les coûts de clics disponibles dans les rapports de données brutes ne tiennent pas compte de cette hiérarchisation.

**Attention**:

* Pour chaque jour où l'API des coûts est activée, le coût des clics est ignoré.
* Si vous modifiez les méthodes d'agrégation des coûts, la modification a un impact rétroactif. Les données historiques des coûts totaux peuvent changer.
* La modification de la méthode d'agrégation des coûts affecte de la même manière le trafic généré par les agences. Cela concerne les agences transparentes et non transparentes.
* Le mécanisme de priorité fonctionne au niveau des campagnes. Cela signifie que si vous obtenez deux entrées de coûts pour une campagne par le biais de mécanismes différents, elles sont en concurrence et la priorité la plus élevée l'emporte pour l'ensemble de la campagne.

**Priorisation de la méthode de calcul du coût des campagnes**

<Image align="center" alt="" src="https://support.appsflyer.com/hc/article_attachments/24855895951377" />

<div id="closed-beta--cost-split" />

<div id="limitations" />

<div id="equal-split-no-conversions" />

<div id="note-2" />

<div id="proportional-split-by-conversions" />

<div id="example-1" />

> 📄 **Exemple**
>
> **Scénario :** Un réseau publicitaire indique le coût par clic, mais vous décidez d'activer l'API des coûts du réseau publicitaire.
>
> **Résultat :** Le coût est agrégé à la fois par les clics et par l'API des coûts. Mais comme l'API des coûts est prioritaire, les coûts des clics sont ignorés.

</Accordion>

<div id="additional-information" />

## Informations supplémentaires

<div id="ad-networks-supporting-cost-api" />

<Accordion title="Liste des réseaux publicitaires prenant en charge l'API des coûts">

Le tableau suivant répertorie tous les réseaux publicitaires prenant en charge l'API de coût, ainsi que la granularité des données disponibles pour chacun d'entre eux :

* Dimensions
* Dispositifs pris en charge et leurs caractéristiques
* Mesures (telles que rapportées par les réseaux publicitaires)

Télécharger le fichier [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=csv), <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=xlsx">XLS</Anchor>

<Embed title="ROI360—Présentation de l'agrégation des coûts" typeOfEmbed="iframe" url="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pubhtml?widget=true&amp;headers=false" providerUrl="https://docs.google.com" height="500px" />

</Accordion>

<div id="changing-campaign-names" />

<Accordion title="Changement de nom de la campagne">

AppsFlyer affiche les campagnes en utilisant l'ID de la campagne comme clé.

Pour éviter les anomalies d'affichage, assurez-vous que

* Les campagnes ont un numéro d'identification unique qui leur est attribué ;
* Vous ne pouvez pas utiliser le même nom de campagne avec des identifiants de campagne différents.

<Anchor target="_blank" href="/marketers/fr/docs/campaign-name-changes">En savoir plus sur les changements de noms de campagne</Anchor>

</Accordion>

<div id="costs-without-installs" />

<Accordion title="Coûts sans installation">

**Pourquoi les données relatives aux coûts n'indiquent-elles aucune installation ?** Cela se produit lorsque le coût est fourni à un niveau hiérarchique supérieur (par exemple au niveau de la campagne), mais que les informations sur les performances (clics et installations) sont fournies à un niveau inférieur de la hiérarchie publicitaire (par exemple au niveau de l'adset).

AppsFlyer complète les données de coûts pour les dimensions manquantes d'une hiérarchie de niveau supérieur. Cela garantit une vue d'ensemble des données relatives aux coûts à tous les niveaux et minimise les divergences internes.

<div id="example-2" />

> 📄 **Exemple**
>
> Un annonceur lance une campagne. La hiérarchie publicitaire est la suivante :
>
> * **Source média** : media\_eg
> * **Campagne**: campaign\_eg
> * **Adsets**: **adset1**, **adset2**
>
> Les informations suivantes relatives à la source de média s'affichent.
>
> Hiérarchie : Tous les médias > media\_eg
>
>
>
> | Campagne | Coût | Installations |
> | --- | --- | --- |
> | campaign\_eg | 100 $ | 100 |
> | campaign\_yy | 200 $ | 1000 |
> | campaign\_zz | 300 $ | 2000 |
>
>
>
> En descendant dans campaign\_eg, le niveau adset s'affiche.
>
> Hiérarchie : Tous les médias > media\_eg > campaign\_eg
>
>
>
> | Adset | Coût | Installations |
> | --- | --- | --- |
> | Aucun | 100 $ |  |
> | adset\_1 | N/A | 30 |
> | adset\_2 | N/A | 70 |
>
>
>
> Dans ce cas, le coût de campaign\_eg est de 100 $ et est fourni au niveau de la campagne. Lors de l'analyse détaillée au niveau de l'ensemble de publicités (adset), qui dans ce cas est le niveau de composant, le coût ne peut pas être ventilé par ensemble de publicités.
>
> Pour éviter ce problème, AppsFlyer reporte les dépenses publicitaires au niveau de la campagne et les affiche sur une ligne distincte. Dans ce cas, l'adset indique «none» et le champ «Installations» reste vide.

<div id="cost-currency-conversion" />

<Accordion title="Conversion des coûts en devises">

Si la devise du coût de la campagne fournie par le réseau publicitaire diffère de la devise définie par l'application sur la plateforme, le coût est converti dans la devise définie par l'application de la manière suivante :

* AppsFlyer obtient les tarifs d'<Anchor target="_blank" href="https://openexchangerates.org/">openexchangerates.org</Anchor>
* Les taux de change sont mis à jour toutes les heures
* Les conversions de devises sont effectuées sur la base du dernier taux connu

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Agences | <ul><li>Les agences peuvent accéder aux données de coûts ROI360 pour les annonceurs avec un abonnement ROI360.</li><li>Lorsque des agences transparentes gèrent des campagnes, les annonceurs peuvent voir le coût affiché dans les tableaux de bord et les rapports qui prennent en charge une vue unifiée.  [En savoir plus](/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports)</li><li>Si un annonceur met fin à sa relation avec une agence et désactive les autorisations de l'agence au niveau de l'application, et si l'agence a configuré des coûts pour l'application, les données de coûts sont toujours extraites. Si l'annonceur souhaite empêcher l'extraction de ces données, il doit demander à l'agence de désactiver l'intégration des coûts dans AppsFlyer.</li><li>Pour certains réseaux publicitaires, les agences doivent contacter l'annonceur pour activer l'intégration et sont invitées à le faire dans l'interface utilisateur d'AppsFlyer. Pour ces réseaux, les agences et les annonceurs doivent s'assurer que lorsque le réseau publicitaire envoie des données, il inclut le `af_prt`paramètre nécessaire à l'attribution des coûts de l'agence.</li></ul> |
| Actualisation des données de l'API | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Intrajournalier</Anchor> (sauf pour Moloco)</li><li>Les données Mintegral sont disponibles via l'API le jour suivant, environ 4 heures après la fin de la journée précédente (en fonction des paramètres de votre fuseau horaire Mintegral). En d'autres termes, si l'événement s'est produit le jour 1, les données relatives aux coûts sont disponibles le jour 2, vers 16h00.</li></ul> |
| Changements de nom de campagne | Les données relatives aux dépenses publicitaires s'affichent en utilisant le nom de campagne le plus récent. **Remarque** : Il s'agit de  l'affichage des données agrégées sur le site, et non des données brutes elles-mêmes. |
| Fuseau horaire | Si un réseau publicitaire ne prend en charge qu'un seul fuseau horaire et qu'il existe une différence entre le fuseau horaire pris en charge par le réseau publicitaire et le fuseau horaire défini dans les paramètres de votre application, c'est le fuseau horaire pris en charge par le réseau publicitaire qui est utilisé. |
| Plateformes CTV, PC et console | En ce qui concerne les applications sur ces plateformes, les données de coûts doivent être envoyées via <Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">Ad Spend Ingestion</Anchor> en utilisant la méthode de téléchargement de fichiers par e-mail. |
| Apps hors store | Les données de coût de Mintegral ne sont pas disponibles pour les applications hors store (applications provenant de plateformes autres que Google Play et App Store). |
| Géo | La ventilation par zone géographique et par pays n'est pas disponible pour les campagnes groupées Mistplay (campagnes ciblées sur plusieurs pays). Pour ces campagnes, la géographie est affichée comme N/A. |

</Accordion>

</Accordion>

<div data-zendesk-anchors="cost-aggregation=agr%C3%A9gation-des-co%C3%BBts h_01HC7K2Y627P56F5JH9QT47GB2=agr%C3%A9gation-des-co%C3%BBts principles-of-cost-data-aggregation=principes-de-lagr%C3%A9gation-des-donn%C3%A9es-sur-les-co%C3%BBts h_01HC7K2Y62ZC932EDX00YP7DAW=principes-de-lagr%C3%A9gation-des-donn%C3%A9es-sur-les-co%C3%BBts h_01HC7K2Y62K78M02ZN034N99T0=cost-aggregation-methods h_01HC7K2Y62YPM3A6Z0HBY58J00=cost-data-availability-and-reports cost-data-availability-and-reports::865c5bcd=disponibilit%C3%A9-des-donn%C3%A9es-sur-les-co%C3%BBts-et-rapports h_01HC7K2Y62ZY6HWG5TJDEPHZKH=disponibilit%C3%A9-des-donn%C3%A9es-sur-les-co%C3%BBts-et-rapports h_01HC7K2Y62112X308A0Y7DDDRM=cost-prioritization-mechanism h_01HC7K2Y62SZKXD4W0EJGYF6RS=exemple list-of-ad-networks=informations-suppl%C3%A9mentaires h_01HC7K2Y63T9GK0WW95YM39B5C=informations-suppl%C3%A9mentaires h_01HC7K2Y63MG10M4Z66VHY5WYW=ad-networks-supporting-cost-api h_01HE0T3TGPZFB2ZBHFGGWXY6AP=changing-campaign-names h_01HE0T3TGQGK6135KM7AYJ7S1G=costs-without-installs h_01HE0T3TGQMK285N8RV48KG8N9=exemple-1 h_01HE0T3TGQ7MSSB09GFNPYFKR1=cost-currency-conversion h_01HJ10FMTJKH48CEXM0G40Y9J1=traits-and-limitations" />
