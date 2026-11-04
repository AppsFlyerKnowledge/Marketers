---
title: Rapports Data Locker Revenus ETL ROI360
metadata:
  keywords:
    - Marketers
    - revenue
    - etl
    - revenueetl
    - revenue etl
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2023-06-25T16:57:02Z'
  edited_at: '2024-09-09T12:21:07Z'
  id: 16464765619985
  locale: fr
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/fr/articles/16464765619985
---
> **En bref :** découvrez les rapports de revenus ROI360, leurs sources, comment ils sont générés, leur disponibilité et comment y accéder. Découvrez la structure et les champs des rapports en téléchargeant l’exemple de données.

<div id="revenue-etl" />

## Revenus ETL

Avec les Revenus ETL ROI360, les données de vos revenus sont envoyées via Data Locker dans le stockage sur le cloud pour être chargées dans vos systèmes BI.

Le tableau suivant indique les rapports de revenus disponibles. **Remarque** : À l'exception des rapports sur les revenus publicitaires hérités [version unique], tous les rapports nécessitent d’voir un abonnement au package ROI360 Advanced.

| Rapport | Type d'intégration | Description | Actualisation des données |
| --- | --- | --- | --- |
| [revenus publicitaires hérités [version unique]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level) :<ul><li>Revenus publicitaires attribués [version unique x+1]</li><li>Revenus publicitaires organiques [version unique x+1]</li><li>Revenus publicitaires de retargeting [version unique x+1]</li></ul> | <ul><li>Niveau impression (via SDK)</li><li>Niveau appareil (via API S2S)</li><li>Niveau impression (via SDK) avec niveau appareil (via API S2S)</li></ul> | <ul><li>Contient les données des revenus publicitaires.</li><li>Version unique (pas de nouvelle mise à jour des données).</li><li>S'il existe à la fois des intégrations d’API et de SDK, les rapports contiennent uniquement les données des API.</li></ul> | <ul><li>Quotidien (disponible au Jour X+1) <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#data-freshness">En savoir plus</Anchor></li></ul> |
| [Revenus publicitaires (multiples versions) :](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level)<ul><li>Revenus publicitaires attribués (multiples versions)</li><li>Revenus publicitaires organiques (multiples versions)</li><li>Revenus publicitaires de retargeting (multiples versions)</li></ul> | <ul><li>Niveau impression (via SDK)</li><li>Niveau appareil (via API S2S)</li><li>Niveau impression (via SDK) avec niveau appareil (via API S2S)</li></ul> | <ul><li>Contient les données de revenus publicitaires les plus récentes.</li><li><Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers#version-folders">Multiples versions</Anchor></li></ul> | <ul><li>Dans la journée. <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#data-freshness">En savoir plus</Anchor></li><li>Mise à jour des données entre 4 heures et 14 jours après l’impression publicitaire.</li></ul> |
| [Revenus publicitaires [niveau impression du SDK]](/docs/revenue-etl-reports#impression-level-report) | <ul><li>Niveau impression (via SDK)</li><li>Niveau impression (via SDK) avec niveau appareil (via API S2S)</li></ul> | <ul><li>Contient les données des revenus publicitaires.</li><li>Précision et actualisation des données optimales.</li></ul> | Par heure. <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#data-freshness">En savoir plus</Anchor> |
| [Revenus des stores au niveau des transactions](/docs/revenue-etl-reports#transactionlevel-stores-revenue-report) | Intégration des revenus des IAP ROI360 et des abonnements | <ul><li>Contient les données brutes des achats in-app validés par ROI360 et les données brutes des abonnements de niveau transaction.</li><li>Précision et actualisation des données optimales.</li><li>Inclut les données uniques liées à la monétisation ROI360 et aux revenus nets.</li></ul> | Par heure |
| [Revenus des stores au niveau de l’appareil (multiples versions)](/docs/revenue-etl-reports#devicelevel-stores-revenue-report) | Intégration des revenus des IAP ROI360 et des abonnements | <ul><li>Contient les données brutes des achats in-app validés par ROI360 et les données brutes des abonnements de niveau appareil.</li><li>Inclut les données de revenus nets ROI360 uniques.</li></ul> | Toutes les 8 heures |

<div id="reports" />

## Rapports

Les sections suivantes contiennent toutes les infos sur les différents rapports : leur fonctionnement, comment s’y abonner et comment y accéder.

<div id="ad-revenue-single-version-report-device-level" />

<Accordion title="Revenus publicitaires hérités (version unique)">

Le rapport contient une seule version des données des revenus publicitaires sur une journée, agrégées au niveau appareil. Le rapport est disponible au jour X+1 (X étant le jour ou s’est produit l’événement de revenu).

**Remarque :** Des rapports distincts fournissent les données sur les revenus organiques et de retargeting. Ces rapports ont les mêmes structures et niveau de disponibilité.

<span id="download-the-report-data-sample"></span>[Téléchargez l’exemple de données du rapport en version unique des revenus publicitaires.](https://docs.google.com/spreadsheets/d/e/2PACX-1vQek1x3rYnYQq3jctSz5hnWG_Nk_LQk2ixMTQFVMb8K6w-UmeNKvKOif3-nudAyIqp9tyuoq9R-FhVz/pub?output=csv)

<div id="data-sources" />

#### Sources des données

Selon le type d'intégration du partenaire de revenu publicitaire, les données du rapport proviennent de l'une des sources suivantes :

* **SDK** : Charges utiles des données de niveau impression envoyées par le connecteur SDK des revenus publicitaires ROI360.
* **S2S** : Rapports de données de niveau appareil issues d’une requête d’API des partenaires (réseau de médiation ou monétisation)

Pour savoir comment paramétrer le type d’intégration, cf Se connecter aux partenaires intégrés de revenus publicitaires.

<div id="data-flow" />

#### Flux des données

1. **Ingestion des données :** Le rapport peut provenir du connecteur SDK des revenus publicitaires, ou de la requête d'API S2S (voir la section ci-dessus).
2. **Traitement des données :** AppsFlyer ROI360 des revenus publicitaires effectue les opérations suivantes :
   1. <span class="af-ol-a"></span>Normalisation des données
   2. Attribution à la source d'installation et enrichissement des données
   3. Génération des événements de revenus publicitaires
   4. Les événements sont agrégés au niveau de l'appareil

   **Remarque :** Un rapport peut avoir plusieurs agrégations au niveau de l'appareil pour le même appareil. Cela se produit quand l'agrégation de niveau appareil se base sur des dimensions liées à la monétisation, comme le réseau de monétisation, le placement et le type de publicité. Par exemple, si l'app affiche des publicités dans deux emplacements différents, les événements de revenus de chaque emplacement sont agrégés séparément au niveau de l'appareil.
3. **Fourniture des données :** Les données de niveau appareil sont inscrites dans le rapport en version unique.

<div id="when-is-the-report-data-available" />

#### Quand les données du rapport sont-elles disponibles ?

| Type d'intégration | Jour de la version (X = jour où l’événement s’est produit) | Version disponible à | La version inclut les événements de revenu qui se produisent entre |
| --- | --- | --- | --- |
| SDK | Jour X+1 | 20:00 | 00:00 — 24:00 |
| SDK + S2S | Jour X+1 | 17:00 | 00:00 — 24:00 |

<div id="how-to-subscribe-to-the-report" />

#### Comment s’abonner au rapport ?

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Rapport > Data Locker**.
2. Dans le panneau du **contenu Data Locker**, faites défiler jusqu’au volet **revenus ETL ROI360** .
3. **Sélectionnez Revenus attribués [version unique]**.

**Remarque :** Vous pouvez également sélectionner le même rapport pour le retargeting et l’organique (Revenus publicitaires de retargeting/organique [version unique]).

<div id="how-to-access-the-report-in-your-bucket" />

#### Comment accéder au rapport depuis votre compartiment ?

Le chemin vers le rapport suit cette hiérarchie de dossiers :

Avec le format suivant : `/t=attributed_ad_revenue/dt=`

<div id="report-folder-hierarchy" />

#### Hiérarchie des dossiers d’un rapport

Exemple de hiérarchie des dossiers d’un rapport en version unique des revenus publicitaires attribués dans le compartiment d’un annonceur :

```
bucket
|
└── t=attributed_ad_revenue
    |
    ├── dt=2023-06-02
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        |
    |        ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        │
    |        └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |
    ├── dt=2023-06-01
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |
    ├── dt=2023-05-31
    |   |
    .   . 
    .   .
```

**Légende :**

* **dt** : **jour où les événements inclus dans le rapport se sont produits.**
* **t** : type de rapport.
* **h :** heure de création de la version unique

</Accordion>

<div id="ad-revenue-versioned-report-device-level" />

<Accordion title="Revenus publicitaires (différentes version)">

Le rapport affiche plusieurs versions des données de revenus pour une même date. Par exemple, les revenus générés le 21 juin sont rapportés les 21 juin, 22 juin, 23 juin, 24 juin, 28 juin et 5 juillet.

Collecter plusieurs versions d’une même journée vise à saisir les différents calculs de revenus qui découlent de conditions temporelles. Par exemple, les impressions qui ont une certaine valeur de revenu en temps réel peuvent avoir une autre valeur un jour plus tard.

**Remarque :** Des rapports distincts fournissent les données sur les revenus organiques et de retargeting. Ces rapports ont les mêmes structures et niveau de disponibilité.

[Téléchargez l’exemple de données du rapport en multiples versions des revenus publicitaires.](https://docs.google.com/spreadsheets/d/e/2PACX-1vQek1x3rYnYQq3jctSz5hnWG_Nk_LQk2ixMTQFVMb8K6w-UmeNKvKOif3-nudAyIqp9tyuoq9R-FhVz/pub?output=csv)

<div id="data-sources-1" />

#### Sources des données

Selon le type d'intégration du partenaire, les données du rapport proviennent de l'une des sources suivantes :

* **SDK** : Charges utiles des données de niveau impression envoyées par le connecteur SDK des revenus publicitaires ROI360.
* **S2S** : Rapports de données de niveau appareil issues d’une requête d’API des partenaires (réseau de médiation ou monétisation)
* **S2S + SDK :** Charges utiles provenant à la fois du SDK et du S2S.

Pour savoir comment paramétrer le type d’intégration, cf Se connecter aux partenaires intégrés de revenus publicitaires.

<div id="data-flow-1" />

#### Flux des données

1. **Ingestion des données :** Le rapport peut provenir soit du SDK, soit de la requête d'API S2S (voir la section ci-dessus).
2. **Traitement des données :** AppsFlyer ROI360 des revenus publicitaires effectue les opérations suivantes :
   1. <span class="af-ol-a"></span>Normalisation des données
   2. Attribution à la source d'installation et enrichissement des données
   3. Génération des événements de revenus publicitaires
   4. Les événements sont agrégés au niveau de l'appareil

   **Remarque :** Un rapport peut avoir plusieurs agrégations au niveau de l'appareil pour le même appareil. Cela se produit quand l'agrégation de niveau appareil se base sur des dimensions liées à la monétisation, comme le réseau de monétisation, le placement et le type de publicité. Par exemple, si l'app affiche des publicités dans deux emplacements différents, les événements de revenus de chaque emplacement sont agrégés séparément au niveau de l'appareil.
3. **Fourniture des données :** Les données de niveau appareil sont inscrites dans plusieurs versions du rapport selon un calendrier prédéterminé (voir ci-dessous).

<div id="when-are-the-report-versions-available" />

#### Quand les versions du rapport sont-elles disponibles ?

Le tableau ci-dessous indique les délais de génération des rapports pour les versions S2S et SDK. Les clients qui bénéficient de ROI360 Ad Revenue Freshness to Accuracy reçoivent les deux versions, ce qui leur garantit une formidable précision des données.

| Type d'intégration | Jour de la version (X = jour où l’événement s’est produit) | Version disponible à | La version inclut les événements de revenu qui se produisent entre |
| --- | --- | --- | --- |
| SDK | Jour X | 03:00 - 04:00 | 00:00 - 03:00 |
| SDK | Jour X | 07:00 - 08:00 | 00:00 - 07:00 |
| SDK | Jour X | 11:00 - 12:00 | 00:00 - 11:00 |
| SDK | Jour X | 15:00 - 16:00 | 00:00 - 15:00 |
| SDK | Jour X | 19:00 - 20:00 | 00:00 - 19:00 |
| SDK | Jour X | 23:00 - 24:00 | 00:00 - 23:00 |
| SDK | Jour X+1 | 04:00 - 05:00 | 00:00 - 24:00 |
| S2S | Jour X+1 | 12:00 - 13:00 | 00:00 - 24:00 |
| S2S | Jour X+1 | 18:00 - 19:00 | 00:00 - 24:00 |
| S2S | Jour X+2 | 00:00 - 01:00 | 00:00 - 24:00 |
| S2S | Jour X+2 | 12:00 - 13:00 | 00:00 - 24:00 |
| S2S | Jour X+3 | 06:00 - 07:00 | 00:00 - 24:00 |
| S2S | Jour X+7 | 08:00 - 09:00 | 00:00 - 24:00 |
| S2S | Jour X+14 | 10:00 - 11:00 | 00:00 - 24:00 |
| SDK + S2S | Toutes les versions SDK et S2S ci-dessus |  |  |

**Remarque :** Certaines versions S2S peuvent ne pas être créées. Si les données du ou des partenaires n'ont pas changé depuis la dernière collecte, il n’y a PAS de nouvelle version générée.

<div id="how-to-subscribe-to-the-report-1" />

#### Comment s’abonner au rapport ?

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Rapport > Data Locker**.
2. Dans le panneau du **contenu Data Locker**, faites défiler jusqu’au volet **revenus ETL ROI360** .
3. Sélectionnez **Revenus publicitaires attribués (multiples versions).**

**Remarque :** Vous pouvez également sélectionner le même rapport pour le retargeting et l’organique **(Revenus publicitaires de retargeting/organique [multiples versions])./strong>**

<div id="how-to-access-the-report-in-your-bucket-1" />

#### Comment accéder au rapport depuis votre compartiment ?

Le chemin vers le rapport suit cette hiérarchie de dossiers :

\`/t=attributed_ad_revenue_v2/dt=

/version=&lt;9999999>/\`

<div id="report-folder-hierarchy-2" />

<div id="report-folder-hierarchy-1" />

#### Hiérarchie des dossiers dans un rapport

Exemple d’une arborescence de dossiers dans un compartiment d’annonceur :

```
bucket
|
└── t=attributed_ad_revenue_v2
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

* **Légende :**
  * **t :** type de rapport
  * **dt** : **jour où les événements inclus dans le rapport se sont produits.**
  * **version :** Le nom de la version correspond à l’horodatage de la date et l’heure où la version a été créée, exemple : **version=1685588879.**
* L’origine de la version, SDK ou S2S, peut être déduite de l’heure de création de la version. Les premières versions sont issues du SDK. Les autres proviennent du S2S.

</Accordion>

<div id="impression-level-report" />

<Accordion title="Revenus publicitaires (niveau impression du SDK)">

Le rapport affiche les données de niveau impression divisées en dossiers qui correspondent à heure de l’impression. Chaque dossier contient exclusivement les impressions qui se sont produites durant cette heure.

[Téléchargez l’exemple de données du rapport des revenus publicitaires de niveau impression.](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5zVxFGaCMNZMbCCYPae6f7MmbtelxrqXb-A5DBENuyTFCN4deRfICvbL0_dNeYVipojmAeUdrGbKI/pub?output=csv)

<div id="data-source" />

#### Source des données

Les données du rapport proviennent des données de niveau impression envoyées par le connecteur SDK des revenus publicitaires ROI360 et nécessitent une intégration de type SDK.

Pour savoir comment paramétrer le type d’intégration, cf Se connecter aux partenaires intégrés de revenus publicitaires.

<div id="data-flow-2" />

#### Flux des données

1. **Ingestion des données :** Les données du rapport proviennent des données de niveau impression envoyées par le connecteur SDK des revenus publicitaires ROI360 et nécessitent une intégration de type SDK.
2. **Traitement des données :** AppsFlyer ROI360 des revenus publicitaires effectue les opérations suivantes :
   1. <span class="af-ol-a"></span>Normalisation des données
   2. Attribution à la source d'installation et enrichissement des données
   3. Génération des événements de revenus publicitaires de niveau impression
3. **Fourniture des données :** Les événements d'impression sont inscrits dans des fichiers, divisés par dossiers selon l'heure où l’impression a eu lieu. Chaque dossier contient exclusivement les impressions qui se sont produites durant cette heure.

<div id="when-is-the-report-data-available-1" />

#### Quand les données du rapport sont-elles disponibles ?

| Type d'intégration | Jour de la version (X = jour où l’événement s’est produit) | Version disponible à |
| --- | --- | --- |
| SDK | Jour X | À la fin de chaque heure rapportée |

<div id="how-to-subscribe-to-the-report-2" />

#### Comment s’abonner au rapport ?

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Rapport > Data Locker**.
2. Dans le panneau du **contenu Data Locker**, faites défiler jusqu’au volet **revenus ETL ROI360** .
3. Sélectionnez **Revenus publicitaires (niveau impression du SDK)**

<div id="how-to-access-the-report-in-your-bucket-3" />

<div id="how-to-access-the-report-in-your-bucket-2" />

#### Comment accéder au rapport depuis votre compartiment ?

Le chemin vers le rapport suit cette hiérarchie de dossiers :

\`/t=attributed_adrevenue_sdk_impression_level/dt=

/h=\`

#### Hiérarchie des dossiers dans un rapport

Exemple d’une arborescence de dossiers dans un compartiment d’annonceur :

```
bucket
|
└── t=attributed_adrevenue_sdk_impression_level/
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**Légende :**

* **t :** type de rapport
* **dt** : **jour où les événements inclus dans le rapport se sont produits.**
* **h** : Dossier horaire contenant le fichier CSV avec les impressions survenues au cours de l’heure mentionnée.

</Accordion>

<div id="transactionlevel-stores-revenue-report" />

<Accordion title="Revenus des stores au niveau des transactions">

Ce rapport présente les données brutes de la journée au niveau des transactions, divisées en dossiers horaires contenant uniquement les transactions qui ont eu lieu durant cette heure.

[Téléchargez l'exemple de données d’un rapport sur les stores au niveau des transactions](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGlRSg_Xrp2EsqK2uaisjhlqeSuZsypqKqSSRGX3AQBwBLlNdG_5LOOKCM9f9gCcLguMQgQwT--Dz7/pub?output=csv)

<div id="data-sources-2" />

#### Sources des données

Les données du rapport proviennent des transactions collectées via le connecteur d'achat du SDK ROI360, et des notifications des stores de serveur à serveur.

<div id="data-flow-3" />

#### Flux des données

1. Les données du rapport proviennent des transactions collectées via les charges utiles du connecteur d'achat du SDK ROI360, ou des notifications des stores S2S.
2. AppsFlyer ROI360 VIAP/Abonnements traite les données, les attribue, puis crée des événements et des valeurs au niveau des transactions.
3. Les événements de niveau transaction sont inscrits dans le rapport segmenté en différents dossiers horaires.

<div id="when-is-the-report-data-available-2" />

#### Quand les données du rapport sont-elles disponibles ?

| Jour de la version (X = jour où l’événement s’est produit) | Version disponible à |
| --- | --- |
| Jour X | À la fin de chaque heure rapportée |

<div id="how-to-subscribe-to-the-report-3" />

#### Comment s’abonner au rapport ?

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Rapport > Data Locker**.
2. Dans le panneau du **contenu Data Locker**, faites défiler jusqu’au volet **revenus ETL ROI360** .
3. Sélectionnez **Rapport sur les revenus des stores au niveau des transactions**

<div id="how-to-access-the-report-in-your-bucket-4" />

#### Comment accéder au rapport depuis votre compartiment ?

Le chemin vers le rapport suit cette hiérarchie de dossiers :

\`/t=stores_rawdata/dt=

/h=\`

<div id="report-folder-hierarchy-3" />

#### Hiérarchie des dossiers dans un rapport

Exemple d’une arborescence de dossiers dans un compartiment d’annonceur :

```
bucket
|
└── t=stores_rawdata
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**Légende :**

* **t** : type de rapport.
* **dt** : **jour où les événements inclus dans le rapport se sont produits.**
* **h** : **dossier horaire contenant le fichier CSV avec les transactions survenues au cours de l’heure mentionnée.**

</Accordion>

<div id="devicelevel-stores-revenue-report" />

<Accordion title="Revenus des stores au niveau de l’appareil (multiples versions)">

Le rapport sur les revenus des stores au niveau de l'appareil contient les événements in-app et d'abonnement à renouvellement automatique capturés par les produits ROI360. Ces événements incluent des dimensions uniques liées à la monétisation ROI360. Les événements in-app indiqués par le client ne sont pas inclus dans ce rapport.

<span id="download-the-report-data-sample::8cbba4e3"></span>[Téléchargez l'exemple de données d’un rapport sur les revenus de stores au niveau appareil](https://docs.google.com/spreadsheets/d/e/2PACX-1vSpomvcf2axYeSFcCh0kEx3ShYYRGVfF9WYZXG1UYBkeymeVfh8mcypAOpq2drqE3zhdmbcmrMtahsl/pub?output=csv)

<div id="data-sources-3" />

#### Sources des données

Les données du rapport proviennent des transactions collectées via :

1. Le connecteur d’achat SDK ROI360.
2. Les stores (comme l’App Store ou Google Play) via des notifications de serveur à serveur.

<div id="data-flow-4" />

#### Flux des données

1. Les données du rapport proviennent des transactions collectées via les charges utiles du connecteur d'achat du SDK ROI360, ou des notifications des stores S2S.
2. AppsFlyer ROI360 VIAP/Abonnements traite les données, les attribue, puis crée des événements in-app.
3. Les événements in-app sont agrégés au niveau de l'appareil et inscrits dans une version du rapport issue toutes les quatre heures.

<div id="when-are-the-report-versions-available-1" />

#### Quand les versions du rapport sont-elles disponibles ?

| Jour de la version (X = jour où l’événement s’est produit) | Version disponible à | La version inclut les événements de revenu qui se produisent entre |
| --- | --- | --- |
| Jour X | 04:00 - 05:00 | 00:00 - 04:00 |
| Jour X | 12:00 - 13:00 | 00:00 - 12:00 |
| Jour X | 20:00 - 21:00 | 00:00 - 20:00 |
| Jour X+1 | 05:00 - 06:00 | 00:00 - 24:00 |

<div id="how-to-subscribe-to-the-report-4" />

#### Comment s’abonner au rapport ?

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Rapport > Data Locker**.
2. Dans le panneau du **contenu Data Locker**, faites défiler jusqu’au volet **revenus ETL ROI360** .
3. Rapport sur les revenus des stores au niveau appareil [multiples versions]

#### Comment accéder au rapport depuis votre compartiment ?

Le chemin vers le rapport suit cette hiérarchie de dossiers :

\`/t=stores_devicedata/dt=

/version=&lt;999999999>\`

<div id="report-folder-hierarchy-4" />

#### Hiérarchie des dossiers dans un rapport

Exemple d’une arborescence de dossiers dans un compartiment d’annonceur :

```
bucket
|
└── t=stores_devicedata
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

**Légende :**

* **t** : type de rapport.
* **dt** : **jour où les événements inclus dans le rapport se sont produits.**
* **version** : le nom de la version correspond à l’horodatage de la date et l’heure où la version a été créée, exemple : **version=1685588879.**

</Accordion>

<div data-zendesk-anchors="revenue-etl=revenus-etl h_01HMBTDD8TASZ2NEBXP7CZ3Q81=revenus-etl reports=rapports h_01HME0BBF2M47M2AV437RYQ070=rapports h_01HETBAQVVYW14END06HBPBQSN=ad-revenue-single-version-report-device-level h_01HETBAQVVZB87JNT0JVYSP80D=download-the-report-data-sample the-report-data-sources=sources-des-donn%C3%A9es h_01HETBAQVVSKVDM4J90A0WGFJW=sources-des-donn%C3%A9es the-report-data-flow=flux-des-donn%C3%A9es h_01HETBAQVV97R7G6F67RM6K62K=flux-des-donn%C3%A9es when-is-the-report-data-available=quand-les-donn%C3%A9es-du-rapport-sont-elles-disponibles- h_01HETBAQVVKDAWW2S98TG6682S=quand-les-donn%C3%A9es-du-rapport-sont-elles-disponibles- how-to-subscribe-to-the-report=comment-sabonner-au-rapport- h_01HETBAQVVFSDRW778VQSSE107=comment-sabonner-au-rapport- how-to-access-the-report-in-dl=comment-acc%C3%A9der-au-rapport-depuis-votre-compartiment- h_01HETBAQVV15T92VXRHG2CP2KJ=comment-acc%C3%A9der-au-rapport-depuis-votre-compartiment- the-report-folder-hierarchy-in-aws=hi%C3%A9rarchie-des-dossiers-dun-rapport h_01HETBAQVVA750VTE1ABSM2M47=hi%C3%A9rarchie-des-dossiers-dun-rapport h_01HETBAQVVCB2SYMW9876HPE7N=ad-revenue-versioned-report-device-level data-sources=sources-des-donn%C3%A9es-1 h_01HMTZ9VQ5WE6D7E5NEBYH71SZ=sources-des-donn%C3%A9es-1 data-flow=flux-des-donn%C3%A9es-1 h_01HMTZ9VQ5PS8G9JTQ2YXF1G7X=flux-des-donn%C3%A9es-1 when-are-the-report-versions-available=quand-les-versions-du-rapport-sont-elles-disponibles- h_01HETBAQVVP1M40KHB66AW545S=quand-les-versions-du-rapport-sont-elles-disponibles- how-to-subscribe-to-the-report::cae4aa15=comment-sabonner-au-rapport--1 h_01HMTZ9VQ5BBFNNE7Z8EP084CF=comment-sabonner-au-rapport--1 how-to-access-the-report-in-your-bucket=comment-acc%C3%A9der-au-rapport-depuis-votre-compartiment--2 h_01HMTZ9VQ5FGBC56AP4R49P4BX=comment-acc%C3%A9der-au-rapport-depuis-votre-compartiment--2 report-folder-hierarchy=hi%C3%A9rarchie-des-dossiers-dans-un-rapport h_01HMTZ9VQ5HCKP7T3JQ2RHZV50=hi%C3%A9rarchie-des-dossiers-dans-un-rapport h_01HETBAQVVR90NJC522WNAG190=impression-level-report the-source-of-the-report-data=source-des-donn%C3%A9es h_01HETBAQVV3KBEW4VV4RY9VRA2=source-des-donn%C3%A9es data-flow::c7ffb834=flux-des-donn%C3%A9es-2 h_01HMTZ9VQ5J837PGG99S8ARAGV=flux-des-donn%C3%A9es-2 when-is-the-report-data-available::272621c9=quand-les-donn%C3%A9es-du-rapport-sont-elles-disponibles--1 h_01HMTZ9VQ5YQKBQ779YWBWESDZ=quand-les-donn%C3%A9es-du-rapport-sont-elles-disponibles--1 how-to-subscribe-to-the-report::67646c99=comment-sabonner-au-rapport--2 h_01HMTZ9VQ5ZST1M7JYKFC3DA62=comment-sabonner-au-rapport--2 how-to-access-the-report-in-aws-the-bucket=comment-acc%C3%A9der-au-rapport-depuis-votre-compartiment--2 h_01HETBAQVVHE80MH3SM3GX21V1=comment-acc%C3%A9der-au-rapport-depuis-votre-compartiment--2 report-folder-hierarchy::26ec73c6=hi%C3%A9rarchie-des-dossiers-dans-un-rapport-1 h_01HMTZ9VQ5FFSA1XF7YSATM6WH=hi%C3%A9rarchie-des-dossiers-dans-un-rapport-1 h_01HETBAQVWZKYBAG5E71KVB9PM=transactionlevel-stores-revenue-report data-sources::68e71455=sources-des-donn%C3%A9es-3 h_01HMTZ9VQ5SWTWTSNW5M9KJ1XN=sources-des-donn%C3%A9es-3 data-flow::bde19643=flux-des-donn%C3%A9es-4 h_01HMTZ9VQ6XVHDHBKV86F3Q9DJ=flux-des-donn%C3%A9es-4 when-is-the-report-data-available::87d17fc2=quand-les-donn%C3%A9es-du-rapport-sont-elles-disponibles--2 h_01HMTZ9VQ64AJQM861M6ENHVWC=quand-les-donn%C3%A9es-du-rapport-sont-elles-disponibles--2 how-to-subscribe-to-the-report::6569d202=comment-sabonner-au-rapport--3 h_01HMTZ9VQ60HMM6TXAPYSZG5CT=comment-sabonner-au-rapport--3 how-to-access-the-report-in-your-bucket::b136ba80=comment-acc%C3%A9der-au-rapport-depuis-votre-compartiment--3 h_01HMTZ9VQ67ZEX3KM6CV32SNBD=comment-acc%C3%A9der-au-rapport-depuis-votre-compartiment--3 report-folder-hierarchy::805d4d8=hi%C3%A9rarchie-des-dossiers-dans-un-rapport-2 h_01HMTZ9VQ68VRJRHXSNAE38A0E=hi%C3%A9rarchie-des-dossiers-dans-un-rapport-2 h_01HETBAQVVWAFEMK8ENWN7DYEY=devicelevel-stores-revenue-report h_01HETBAQVV9PSDJNS76SNX522C=download-the-report-data-sample::8cbba4e3 the-report-data-sources::af31e5d1=sources-des-donn%C3%A9es-3 h_01HETBAQVWE2R75D034VCYMTR1=sources-des-donn%C3%A9es-3 the-report-data-processing-flow=flux-des-donn%C3%A9es-4 h_01HETBAQVWZRBE84NV403BCZ9F=flux-des-donn%C3%A9es-4 when-are-the-report-versions-available::2f1bc55f=quand-les-versions-du-rapport-sont-elles-disponibles--1 h_01HETBAQVWQFCKHMT6PJNPXX7D=quand-les-versions-du-rapport-sont-elles-disponibles--1 how-to-subscribe-to-the-report::a624afde=comment-sabonner-au-rapport--4 h_01HETBAQVW54MD9Q09RNC673PE=comment-sabonner-au-rapport--4 how-to-access-the-report-in-the-aws-bucket=comment-acc%C3%A9der-au-rapport-depuis-votre-compartiment--4 h_01HETBAQVWYDR81WS9Q9G20ZND=comment-acc%C3%A9der-au-rapport-depuis-votre-compartiment--4 the-report-folder-hierarchy-in-aws::45c0d598=hi%C3%A9rarchie-des-dossiers-dans-un-rapport-3 h_01HETBAQVWXHK6DXFA90GJQWPV=hi%C3%A9rarchie-des-dossiers-dans-un-rapport-3" />
