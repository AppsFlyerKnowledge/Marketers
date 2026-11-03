---
title: Guide d'intégration ROI360
metadata:
  keywords:
    - ROI
    - cost
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-05-23T08:36:31Z'
  edited_at: '2024-07-18T10:47:11Z'
  id: 25301111725329
  locale: fr
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/fr/articles/25301111725329
---
> **En bref :** Suivez les instructions d'intégration dans cet article pour mettre en place ROI360 afin d'obtenir des données sur les coûts et les revenus opérationnels.

## ![](https://files.readme.io/fa3644980702d735f81d7243f91cb0f0d454bd971e83685ab9759ff7bd925e93-26137252926097.png)

## Introduction

ROI360 est une suite d'outils de reporting uniques sur les coûts et les revenus qui vous fournissent les données les plus précises et les plus récentes. En comparant les informations sur les coûts et les revenus, vous pouvez tout connaître de votre retour sur investissement publicitaire (ROAS), et votre retour sur investissement (ROI).

Suivez les instructions d'intégration ci-dessous pour mettre en place les outils ROI360 pour le reporting des coûts, des revenus publicitaires et des revenus (achats in-app et abonnements). L'intégration nécessite la participation des marketeurs, des développeurs d'applications et des développeurs BI.

<div id="cost-onboarding" />

<Accordion title="Coût de l'intégration">

![](https://files.readme.io/0e7102766b3b7cdba3f301ca89c51edf8e4bd2ec88e09bc912ce3c1436c43fcb-26137252929681.png)

Avec la solution de coûts ROI360, vous obtiendrez des informations détaillées sur les coûts et le retour sur investissement, mises à jour plusieurs fois par jour. Cela vous permet de gérer efficacement les coûts de campagne et de visualiser les allocations budgétaires sur diverses sources médias (réseaux publicitaires), campagnes et zones géographiques, que vous utilisiez des réseaux publicitaires, des médias propriétaires ou des agences.

Après avoir terminé l'intégration des coûts, vous serez en mesure de :

* Obtenir des vues d'ensemble complètes et actualisées des coûts de la campagne avec une consolidation automatique de toutes les sources médiatiques.
* Baser votre analyse sur les données de coûts les plus précises, mises à jour après l'installation.
* Pour les utilisateurs de ROI360 Advanced, envoyer des données détaillées sur les coûts à votre système de BI jusqu'à 4 fois par jour.
* Gérer les frais d'agence et mesurer précisément les coûts globaux de la campagne dans un souci de contrôle financier et de transparence.

| Tâche | Objectif | Actions requises | Personnes concernées |
| --- | --- | --- | --- |
| Connectez les intégrations API de coût pour tous les réseaux publicitaires avec lesquels vous travaillez. | Obtenez des données sur les coûts de toutes les sources liées à l'attribution au niveau le plus granulaire. | <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Activez l'API des coûts</Anchor> pour chaque réseau publicitaire dans l'interface utilisateur AppsFlyer. **Remarque** : Avant de procéder à l'intégration, vous devez obtenir les informations d'identification de chaque réseau publicitaire. | Marketeur |
| Mise en place de rapports ETL sur les coûts. (Disponible pour les abonnés de ROI360 Advanced) | Consultez les données sur les coûts des campagnes avec la meilleure granularité disponible par source de média, actualisées 4 fois par jour. | Configurez des rapports ETL sur les coûts pour <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-aws-s3">AWS S3</Anchor> ou <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-gcs">GCS</Anchor>. | Marketeur/développeur BI |
| Charger les données de coûts via l'importation de coûts. | Obtenez les données de coûts<ul><li>Pour les réseaux publicitaires qui ne communiquent pas les coûts par API ou par clic.</li><li>Lorsque vous utilisez des liens OneLink pour faire de la publicité via des influenceurs, etc.</li><li>Lorsque vous devez corriger les données relatives aux coûts.</li></ul> | Téléchargez ou envoyez par courrier électronique des fichiers de données sur les coûts à l'aide de l'<Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">importation de coûts</Anchor>. | Marketeur |
| Configurez les frais d'agence. | Si vous faites appel à des agences, obtenez le coût total de la campagne, y compris le pourcentage de frais que les agences facturent pour le trafic. | Créez des <Anchor target="_blank" href="Create%20agency%20fee%20rules%20for%20each%20agency%20you%20work%20with">règles de frais d'agence</Anchor> pour chaque agence avec laquelle vous travaillez. | Marketeur |

</Accordion>

<div id="ad-revenue-onboarding" />

<Accordion title="Intégration des revenus de la publicité">

![](https://files.readme.io/877e4abddd466bbe7dfa31f7fffb2f17fe3e6419f3bf6345e9d619253126b0e6-26137252932369.png)

Avec la solution de revenus publicitaires ROI360, vous recevrez des données précieuses et granulaires sur les revenus publicitaires, actualisées plusieurs fois par jour.

Après avoir terminé l'intégration des revenus publicitaires, y compris la connexion aux plateformes de médiation ou réseaux de monétisation avec lesquels vous travaillez, l'implémentation du connecteur SDK au niveau de l'impression des revenus publicitaires, et le partage de données avec les partenaires AU, vous serez en mesure de :

* Obtenir des données précises et récentes sur les revenus publicitaires dans tous les tableaux de bord et rapports d'AppsFlyer.
* Envoyer des données en continu vers votre système de veille stratégique avec une granularité et une actualisation adaptées à vos besoins.
* Améliorer les performances de vos campagnes en demandant aux réseaux AU d'optimiser les mesures de revenus publicitaires.

| Tâche | Objectif | Actions requises | Personnes concernées |
| --- | --- | --- | --- |
| Décidez du type d'intégration de l'attribution des revenus publicitaires. | Comprenez les avantages de chaque type d'intégration et choisissez celui qui répond le mieux aux besoins de votre entreprise. | Découvrez les différents <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">types d'intégration des revenus publicitaires</Anchor> et choisissez-en 1. | Marketeur |
| Connectez-vous à tous les réseaux de médiation et de monétisation des revenus publicitaires avec lesquels vous travaillez. | Obtenez des données sur les revenus publicitaires de vos réseaux de médiation ou de monétisation. | <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Connecter les intégrations de revenus publicitaires</Anchor> dans l'interface utilisateur d'AppsFlyer. | Marketeur |
| Implémentez le connecteur SDK pour les revenus publicitaires au niveau de l'impression. | <ul><li>Concerne les types d'intégration au niveau du SDK.</li><li>Obtenez des données sur les revenus publicitaires en temps quasi réel.</li></ul> | <ol><li>Intégrez le <Anchor target="_blank" href="/marketers/fr/docs/integrate-the-roi360-ad-revenue-sdk-api">connecteur SDK ROI360 AppsFlyer pour les revenus publicitaires</Anchor>.</li><li>Pour voir les données sur les revenus publicitaires dans le tableau de bord SKAN, activez le <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#report-events-by-servertoserver-api">support SKAdNetwork de serveur à serveur</Anchor>.</li></ol> | Développeur/Marketer |
| Partager les données relatives aux revenus publicitaires avec les partenaires AU. | Les réseaux publicitaires AU peuvent utiliser les données relatives aux revenus publicitaires pour optimiser leurs campagnes AU. | <ol><li>Découvrez les deux <Anchor target="_blank" href="/marketers/fr/docs/share-ad-revenue-data-with-partners#about-sharing-ad-revenue-data-with-partners">méthodes de partage des données sur les revenus publicitaires avec les partenaires de AU</Anchor>.</li><li><Anchor target="_blank" href="/marketers/fr/docs/share-ad-revenue-data-with-partners#procedures">Mettez en œuvre la méthode</Anchor> choisie.</li></ol> | Marketeur |
| Mettre en place des rapports ETL sur les revenus. (Disponible pour les abonnés de ROI360 Advanced) | Diffusez et visualisez les données relatives aux revenus publicitaires dans votre système d'information décisionnel avec la meilleure granularité disponible, actualisées plusieurs fois par jour. | Mise en place de <Anchor target="_blank" href="/marketers/fr/docs/revenue-etl-reports">rapports ETL sur les revenus publicitaires</Anchor>. | Marketeur/développeur BI |

</Accordion>

<div id="revenue-onboarding" />

<Accordion title="Intégration des revenus des achats in-app et abonnements">

![](https://files.readme.io/811c90ec42465994455fe42be8400b4ebb94ab6d1a5703bc9a77251aba95ed3b-26137252934545.png)

Avec la solution de revenus ROI360, vous obtenez un contrôle proactif sur vos flux de revenus.

Après avoir terminé l'intégration des revenus, y compris la configuration des notifications de magasin et l'implémentation des connecteurs SDK d'achat pour Android et iOS, vous pourrez :

* Mettre en place une validation et une mesure automatiques pour les transactions de l'App Store et de Google Play.
* Bénéficier de rapports de revenus transparents et précis sans aucun effort supplémentaire de la part des développeurs ; ROI360 se chargera d'enregistrer tous les événements de revenus in-app pour vous.
* Obtenir des mesures précises des revenus pour gérer efficacement les initiatives de croissance stratégique dans l'ensemble de votre portefeuille.

| Tâche | Objectif | Actions requises | Personnes concernées |
| --- | --- | --- | --- |
| Mettez en place la solution ROI360 pour les achats in-app et les revenus d'abonnement. | Validez et mesurez automatiquement les revenus issus des achats in-app, des abonnements renouvelables automatiquement et des événements connexes qui passent par l'App Store (iOS) ou Google Play (Android). | Suivez ces instructions pour :<ol><li>Configurer les notifications à partir de Google Play.</li><li>Configurer les notifications depuis l'App Store iOS.</li><li>Intégrer le connecteur SDK d'achat AppsFlyer pour Android et iOS.</li><li>Intégrer l'API de taxe sur les revenus réels. (Cette option n'est nécessaire que si vous souhaitez modifier les taux fiscaux par défaut.)</li><li>Tester l'intégration.</li><li>Publier les versions des apps Android et iOS avec les connecteurs SDK d'achat.</li></ol> | Développeur/Marketer |
| Mettre en place des rapports ETL sur les revenus. (Disponible pour les abonnés de ROI360 Advanced) | Diffusez et visualisez les données relatives aux revenus dans votre système d'information décisionnel avec la meilleure granularité disponible, actualisées plusieurs fois par jour. | Mettez en place des <Anchor target="_blank" href="/marketers/fr/docs/revenue-etl-reports">rapports ETL sur les revenus</Anchor>. | Marketeur/développeur BI |

</Accordion>

<div data-zendesk-anchors="overview=introduction h_01HKHGX9JJQQCKF9SDZRSCM1XJ=introduction h_01HYJ8PSPTFR6QH329TBR73AXM=cost-onboarding h_01HYJ8PSPTKBZ60TF7T0EMSCXW=ad-revenue-onboarding h_01HYJ8PSPTWK4SEGVJWG5J86E2=revenue-onboarding" />
