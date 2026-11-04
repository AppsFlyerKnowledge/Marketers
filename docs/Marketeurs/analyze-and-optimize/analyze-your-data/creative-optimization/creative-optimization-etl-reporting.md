---
title: Optimisation des créations - Rapports ETL
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-10-10T14:33:17Z'
  edited_at: '2023-12-11T08:17:03Z'
  id: 19253873174801
  locale: fr
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/fr/articles/19253873174801
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** diffusez automatiquement et en continu les rapports d'optimisation créative vers le stockage cloud avec Data Locker, puis chargez-les de manière efficace dans vos systèmes BI.

## À propos de l'ETL de l'optimisation des créations

L'ETL (Extract Transform Load) de l'optimisation des créations fournit à vos analystes de données toutes les informations dont ils ont besoin pour l'analyse des performances créatives. Pour ce faire, elle diffuse automatiquement les rapports <Anchor target="_blank" href="/marketers/fr/docs/creative-optimization-guide">d'optimisation créative</Anchor> dans un espace de stockage cloud, afin de les charger de manière programmatique dans vos systèmes BI.

Des rapports de performance complets de niveau ressource sont fournis, incluant tous les KPI, KPI du tunnel supérieur et inférieur, les données d'attribution et les données sur les ressources créatives.

L'ETL de l'optimisation des créations utilise <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">Data Locker</Anchor> pour envoyer les données de rapport d'optimisation créative vers un stockage cloud. Vous pouvez choisir parmi différentes destinations de stockage, telles qu'un compartiment appartenant à AppsFlyer dans Amazon Web Services (AWS) ou votre propre stockage dans AWS, GCS, Yandex, BigQuery, Snowflake, etc. Data Locker prend en charge plusieurs destinations. Vous pouvez envoyer toutes les données à une ou plusieurs destinations, envoyer des données à certaines destinations et personnaliser la livraison des données en fonction de vos besoins. Creative Optimization ETL est **disponible avec un plan d'abonnement Creative Optimization Premium**.

<div id="get-started" />

## Démarrer

Cette section décrit comment configurer Data Locker pour les rapports d'optimisation créative.

<div id="set-up-data-locker" />

<Accordion title="Configurer Data Locker">

Tout d'abord, vous devez souscrire au plan Creative Optimization Premium et au Data Locker via votre AppsFlyer CSM. Une fois inscrit, vous pouvez configurer Data Locker.

**Pour configurer Data Locker :**

1. Suivez les <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers#set-up-data-locker">instructions</Anchor> suivantes.

2. Lors de la configuration de Data Locker, sélectionnez **Créations** (dans **Sélection des rapports**), sur la page de configuration de Data Locker.

![Data Locker - select Creative.jpg](https://files.readme.io/bd1528ac5419f1bbf033a4a96c028f5a1bf7ff798c452371ac906ea650255d31-19276693230353.jpg)

</Accordion>

<div id="edit-data-locker-configuration" />

<Accordion title="Modifiez la configuration de Data Locker">

Cette section décrit comment modifier la configuration de votre Data Locker existant pour ajouter des rapports d'optimisation  créative.

**Pour ajouter les rapports d'optimisation créative à Data Locker :**

1. Dans la section **Intégrations** du menu latéral principal d'AppsFlyer, cliquez sur **Data Locker**.

<Image alt="from Integration select Data Locker.jpg" src="https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg" width="200px" />

2. Sélectionnez **Créations** (dans **Sélection des rapports**), sur la page de configuration de Data Locker.

![Data Locker - select Creative.jpg](https://files.readme.io/bd1528ac5419f1bbf033a4a96c028f5a1bf7ff798c452371ac906ea650255d31-19276693230353.jpg)

</Accordion>

## Données

Cette section décrit la disponibilité des données dans l'ETL d'optimisation créative.

<div id="data-freshness" />

<Accordion title="Actualisation des données">

Une fois configuré, le rapport d'optimisation  créative est transmis quotidiennement à Data Locker, accompagné des données des 30 derniers jours. L'exportation des données est disponible quotidiennement à UTC + 12. <Anchor target="_blank" href="/marketers/fr/docs/data-locker-advertiser-reports#data-freshness-explanations">En savoir plus</Anchor>

</Accordion>

<div id="what-happens-if-a-report-runs-more-than-once-on-the-same-day" />

<div id="how-do-i-add-new-inapp-events-to-an-existing-custom-creative-etl-report" />

<div id="can-i-have-multiple-custom-creative-etl-reports-with-different-report-types" />

<div id="can-i-run-both-standard-creative-etl-and-custom-creative-etl-at-the-same-time" />

<div id="whats-the-difference-between-standard-creative-etl-and-custom-creative-etl" />

<div id="custom-creative-etl" />

<div id="see-also" />

<div id="faq" />

<div id="limitations" />

<div id="in-app-events" />

<div id="metrics" />

<div id="note-7" />

<div id="ai-dimensions" />

<div id="dimensions" />

<div id="mandatory-fields" />

<div id="schema-reference" />

<div id="data-delivery" />

<div id="note-6" />

<div id="report-management" />

<div id="important-1" />

<div id="note-5" />

<div id="edit-an-existing-report" />

<div id="important" />

<div id="note-4" />

<div id="note-3" />

<div id="what-is-a-schema" />

<div id="step-3---schema" />

<div id="note-2" />

<div id="step-2---details" />

<div id="step-1---destination" />

<div id="set-up-custom-creative-etl" />

<div id="before-you-begin" />

<div id="note-1" />

<div id="available-data" />

<Accordion title="Données disponibles">

Les données créatives suivantes sont disponibles dans Data Locker.

| Champ | Type |
| --- | --- |
| date | chaîne |
| asset\_link | chaîne |
| Création | chaîne |
| media\_source | chaîne |
| campagne | chaîne |
| campaign\_id | chaîne |
| ad | chaîne |
| ad\_id | chaîne |
| adset | chaîne |
| adset\_id | chaîne |
| app\_name | chaîne |
| app\_id | chaîne |
| creative\_first\_seen | chaîne |
| creative\_type | chaîne |
| duration | chaîne |
| end\_card\_type | chaîne |
| geo | chaîne |
| platform | chaîne |
| Orientation | chaîne |
| Résolution | chaîne |
| impressions | chaîne |
| clicks | chaîne |
| installs | chaîne |
| CTR | chaîne |
| CVR | chaîne |
| IPM | chaîne |
| coût | chaîne |
| eCPI | chaîne |
| reattributions | chaîne |
| reengagements | chaîne |
| CPM | chaîne |
| roas\_d1 | chaîne |
| roas\_d7 | chaîne |
| roas\_d14 | chaîne |
| roas\_d30 | chaîne |
| roas\_d60 | chaîne |
| roas\_d90 | chaîne |
| retention\_d1 | chaîne |
| retention\_d7 | chaîne |
| retention\_d14 | chaîne |
| retention\_d30 | chaîne |
| retention\_d60 | chaîne |
| retention\_d90 | chaîne |
| revenue\_d1 | chaîne |
| revenue\_d14 | chaîne |
| revenue\_d30 | chaîne |
| revenue\_d60 | chaîne |
| revenue\_d7 | chaîne |
| Revenue\_d90 | chaîne |
| partner\_cpm | chaîne |
| partner\_ctr | chaîne |
| partner\_cvr | chaîne |
| partner\_clicks | chaîne |
| partner\_cost | chaîne |
| partner\_ipm | chaîne |
| partner\_impressions | chaîne |
| partner\_installs | chaîne |
| partner\_ecpi | chaîne |
| partner\_ecpi | chaîne |

> 📘 **Remarque**
>
> **Les données suivantes ne sont pas disponibles :**
>
> * Dimension personnalisée
> * Mesures personnalisées
> * Évènements in-app
> * Données IA (éléments et scènes)
> * Données de retargeting

</Accordion>

<div data-zendesk-anchors="about-creative-etl=%C3%A0-propos-de-letl-de-loptimisation-des-cr%C3%A9ations h_01HCF5ZDDGTN52MZ9DX2MDKJV7=%C3%A0-propos-de-letl-de-loptimisation-des-cr%C3%A9ations get-started=d%C3%A9marrer h_01HCF65RS2NKHEDHFE9TN78ES8=d%C3%A9marrer h_01HCFF8BWHGFX5KEZWKVDYXKKA=set-up-data-locker h_01HCFF8BWJCQHNN17N8G555FP9=edit-data-locker-configuration data=donn%C3%A9es h_01HCF8C8S392WJMYYHV6ECMNCW=donn%C3%A9es h_01HCFC87EDDD3X0ZXNCAQAHTZB=data-freshness h_01HCFBYBBMNZ52TH4M3G3YB3YM=available-data h_01HF44ZFSHJ8MX9ZNBF7SWB5JN=remarque" />
