---
title: Liste et interfaces des API des annonceurs
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-05-24T15:14:53Z'
  edited_at: '2024-05-26T07:26:52Z'
  id: 360009122638
  locale: fr
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/fr/articles/360009122638
---
> **En bref :** API disponibles pour les annonceurs pour accéder ou mettre à jour les données.

## Liste et interfaces des API des annonceurs

<span id="01EEQJERAWW3HY59HVPY3YWA0B"></span>Informations spécifiques aux rapports, outils de reporting et API de reporting :

* <span id="01EEQJERAW2ZTBWBQKBCDSC76Z"></span><span id="01EEQJERAWQ2WCPV0207XM6FR4"></span><Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview"><span id="01EEQJERAX0W7RCYQWVM2M5S13"></span>API/Outils de reporting des données brutes</Anchor>
* <span id="01EEQJERAWA09P200SGR985846"></span><span id="01EEQJERAW6AC6WR7E46T5DMHW"></span><Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview">Outils/API de reporting agrégé et analytique</Anchor>

#### Interfaces pour les annonceurs

| Arène | Nom de l'API | <Image alt="af_premium.png" src="https://files.readme.io/ad0c279c48242ea25529f1bc386ee2c747bcd332f5fb1eb2fc26dd378a257f6e-4403570953105.png" width="80px" /><br /><br />Fonctionnalité Premium | Description | Authentification  <br />token/clé | Type d'interface |
| --- | --- | --- | --- | --- | --- |
| Attribution mobile | <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">Événements de serveur à serveur</Anchor> | Non | Enregistrer les événements dans l'application qui se produisent en dehors d'une application mobile. | <Anchor target="_blank" href="/marketers/fr/docs/app-settings#sdk-authentication-dev-key">Clé dev du SDK</Anchor> | API REST |
| Attribution basée sur les personnes (PBA) | <Anchor target="_blank" href="ttps://support.appsflyer.com/docs/web-server-to-server-events-api-for-pba-web-s2s">API de serveur à serveur</Anchor> | Non | Signaler les événements PBA qui se produisent dans le Backend | <Anchor target="_blank" href="/marketers/fr/docs/pba-brand-bundles-and-settings#gérer-les-bundles-de-marque">Clé PBA</Anchor> | API REST |
| Engagement | <Anchor target="_blank" href="/marketers/fr/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">Le lien profond universel OneLink</Anchor> | Oui | Gérer OneLinks : créer, mettre à jour, récupérer, supprimer | <Anchor target="_blank" href="/marketers/fr/docs/app-settings#sdk-authentication-dev-key">Clé dev du SDK</Anchor> | API REST |
| Remarketing | <Anchor target="_blank" href="/marketers/fr/docs/audiences-guide#import-an-audience">Audiences</Anchor> | Oui | Télécharger des listes d'utilisateurs sur Audiences | <Anchor target="_blank" href="/marketers/fr/docs/audiences-import-audience-segments-from-internal-systems">Clé d'importation</Anchor> | API REST |
| Confidentialité | 1. Demandes RGPD | Non | Demandes et statut de suppression de données | <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">V1.0</Anchor> | API REST |
| Reporting | <Anchor target="_blank" href="/marketers/fr/docs/master-api-user-acquisition-metrics-via-api">Maîtriser les KPI de performance</Anchor> | Oui | Statistiques de performances des campagnes multi-applications dans des fichiers CSV | <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">V1.0</Anchor> | API REST |
| Reporting | <Anchor target="_blank" href="/marketers/fr/docs/pull-api-aggregate-data">Extraire des rapports agrégés</Anchor> | Non | Regrouper les rapports dans des fichiers CSV | <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">V1.0</Anchor> | API REST |
| Reporting | <Anchor target="_blank" href="/marketers/fr/docs/pull-api-raw-data">Extraire des données brutes</Anchor> | Oui | Rapports de données brutes dans des fichiers CSV | <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">V1.0</Anchor> | API REST |
| Reporting | <Anchor target="_blank" href="/marketers/fr/docs/cohort-api">Analyse de cohorte</Anchor> | Oui | Métriques de cohorte dans des fichiers JSON ou CSV | <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">V2.0</Anchor> | API REST |
| Reporting | <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">Data Locker</Anchor> | Oui | Rapports de données brutes et agrégées | N/A | Stockage sur le Cloud |
| Attribution mobile | <Anchor target="_blank" href="/marketers/fr/docs/push-api-streaming-raw-data">Push</Anchor> | Oui | Installations en temps réel et événements in-app envoyés aux serveurs des annonceurs | N/A | API REST |
| Coût de la campagne | <Anchor target="_blank" href="/partners/fr/docs/cost-import-for-ad-networks">Importation des coûts</Anchor> | Non | Signaler le coût de la campagne | N/A | Téléchargement de fichiers |
| Compte | <Anchor target="_blank" href="/marketers/fr/docs/app-list-api-for-app-owners">Obtenir la liste des apps</Anchor> | Non | Obtener une liste des applications dans votre compte | <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">V2.0</Anchor> | API REST |
| Reporting | <Anchor target="_blank" href="/marketers/fr/docs/set-up-and-use-roi360-cost-etl-reports">Coût ETL</Anchor> | Oui | Coût ETL détaillé de la campagne | N/A | Stockage sur le Cloud |
| Reporting | <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#reporting-options">Rapports SKAN</Anchor> | Non | Rapports agrégés SKAN | V2.0 | API REST |
| Partenaires intégrés | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_copy">Copier les paramètres d'intégration des partenaires</Anchor> | Non | Copier les paramètres de configuration d'intégration d'une application à l'autre | V2.0 | API REST |
| Partenaires intégrés | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Définir la clé de décryptage du référent d'installation</Anchor> | Non | Définir la clé de déchiffrage du référent d'installation reçue des méta-annonces | V2.0 | API REST |

<div data-zendesk-anchors="advertiser-api-list-and-interfaces=liste-et-interfaces-des-api-des-annonceurs h_01HX9638DX6EHR4ETMSH10K68F=liste-et-interfaces-des-api-des-annonceurs interfaces-for-advertisers=interfaces-pour-les-annonceurs h_01HX9638DXNJM3A968A2PSRRKS=interfaces-pour-les-annonceurs" />
