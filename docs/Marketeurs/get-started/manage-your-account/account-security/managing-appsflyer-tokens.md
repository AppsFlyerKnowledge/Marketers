---
title: Gestion des jetons d'API
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-01-01T09:50:22Z'
  edited_at: '2023-11-16T11:41:06Z'
  id: 360004562377
  locale: fr
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/fr/articles/360004562377
---
> **![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) En bref :** les admins génèrent des jetons d'API pour permettre aux utilisateurs d'accéder aux données via les API AppsFlyer.

> 🚧 **Important !**
>
> * Pour garantir la sécurité des données, seuls les admins peuvent consulter la page des jetons d'API. Cela signifie que les utilisateurs de compte et les partenaires n'ont pas accès à cette page.
> * Veillez à conserver vos jetons, car ils permettent d'accéder à vos données. Ne publiez pas de jetons dans les répertoires de code publics.
> * Il est recommandé de réinitialiser le jeton d'API tous les 180 jours.

## Récupération des jetons d'API

**Pour obtenir un jeton d'API :**

1. Dans la barre de menu, accédez au menu utilisateur (liste déroulante des e-mails en haut à droite).
2. Sélectionnez **Centre de sécurité.**
3. Dans la section **Jetons d'API AppsFlyer**, cliquez sur **Gérer vos jetons d'API AppsFlyer.**
4. Le jeton disponible (V2.0) s'affiche.
5. Copiez le jeton requis.

## Réinitialisation des jetons d'API

> ❗️ **Attention**
>
> Si vous réinitialisez un jeton, le jeton actuel devient invalide et un jeton de remplacement est généré. Pour éviter toute perte des données, intégrez immédiatement le jeton de remplacement dans vos scripts et processus automatisés.

**Pour réinitialiser un jeton d'API :**

1. Dans la barre de menu, accédez au menu utilisateur (liste déroulante des adresses e-mail).
2. Sélectionnez **Centre de sécurité.**
3. Dans la section **Jetons d'API AppsFlyer**, cliquez sur **Gérer vos jetons d'API AppsFlyer.**
4. Le jeton disponible (V2.0) s'affiche.
5. Identifiez le jeton à réinitialiser et cliquez sur le lien **Réinitialiser** **le jeton**.
6. Si vous voulez continuer, cliquez sur **Réinitialiser le jeton** dans la boîte de dialogue.
7. Copiez le nouveau jeton.
8. Intégrez le jeton de remplacement aux scripts et aux processus automatisés qui nécessitent un jeton.

## Type de jeton requis selon le type d'API

### Jeton V2.0—API d'annonceurs

| API |
| --- |
| <Anchor target="_blank" href="/marketers/fr/docs/pull-api-aggregate-data">Données brutes d'API Pull</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/pull-api-aggregate-data">Extraire les données agrégées de l'API</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/app-list-api-for-app-owners">Obtenir la liste des apps</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/cohort-api">cohorte</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/skan-aggregated-performance-report-api">Rapport agrégé de SKAdNetwork</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_copy">Copier les paramètres d'intégration des partenaires</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Définir la clé de décryptage du référent d'installation</Anchor> |
| API de taxe sur les revenus réels |
| <Anchor target="_blank" href="/marketers/fr/docs/send-opendsr-api-requests">API OpenDSR</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor> |

### Jeton V2.0—API de réseaux publicitaires

| API |
| --- |
| <Anchor target="_blank" href="/partners/fr/docs/app-list-api-for-ad-networks">Liste d'apps pour les réseaux publicitaires</Anchor> |
| <Anchor target="_blank" href="/partners/fr/docs/access-to-aggregated-analytics-tools-for-api-partners">Intégration avec les plateformes de gestion de campagnes</Anchor> |
| <Anchor target="_blank" href="/partners/fr/docs/protect360-for-integrated-partners#protect360-ad-network-reporting-api">Rapports Protect360 pour les partenaires intégrés</Anchor> |
| <Anchor target="_blank" href="/partners/fr/docs/incost-api-for-ad-networks">InCost</Anchor> |

<div data-zendesk-anchors="h_01HBQN3T2HQKXZ0RC31DG28D6X=important- retrieving-api-tokens=r%C3%A9cup%C3%A9ration-des-jetons-dapi h_01HBQN3T2HKEMNC8MSR0THYW2S=r%C3%A9cup%C3%A9ration-des-jetons-dapi resetting-api-tokens=r%C3%A9initialisation-des-jetons-dapi h_01HBQN3T2HM6NV4NW723YMNQ48=r%C3%A9initialisation-des-jetons-dapi h_01HBQN3T2H58T5E075CZ14S9B9=attention token-type-required-per-api=type-de-jeton-requis-selon-le-type-dapi h_01HBQN7TBA4DX7HYMVK84SSNCP=type-de-jeton-requis-selon-le-type-dapi v20-token%E2%80%94advertiser-apis=jeton-v20api-dannonceurs h_01HBQN7TBASK192P8D7AEWM9P6=jeton-v20api-dannonceurs v20-token%E2%80%94ad-network-apis=jeton-v20api-de-r%C3%A9seaux-publicitaires h_01HBQN7TBAWAHEQXMYK9V14G0M=jeton-v20api-de-r%C3%A9seaux-publicitaires" />
