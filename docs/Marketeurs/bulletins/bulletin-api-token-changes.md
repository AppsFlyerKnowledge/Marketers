---
title: 'Bulletin : modifications des jetons d''API'
metadata:
  keywords:
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2023-01-23T15:35:25Z'
  edited_at: '2023-10-04T13:29:54Z'
  id: 12399683708305
  locale: fr
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/fr/articles/12399683708305
---
| **Quoi de neuf ?** | Afin d'améliorer l'utilisation des API, le jeton d'API V1 (qui apparaissait dans les URL d'API) a été supprimé pour être remplacé par le jeton d'API V2, un jeton JWT qui est transmis dans l'en-tête pour l'autorisation du porteur.<br /><br />Le jeton d'API V1 ainsi que les API qui l'utilisent ne sont plus disponibles depuis le 18 septembre 2023. |
| --- | --- |
| **Date d'entrée en vigueur** | 18 septembre 2023 |
| **Conditions préalables** | Seul un admin peut <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens#récupération-des-jetons-dapi">récupérer le jeton d'API V2</Anchor> depuis le tableau de bord AppsFlyer. |
| **Qui doit mettre à jour le jeton d'API ?** | Les annonceurs et les agences qui utilisent encore le jeton d'API V1 doivent mettre à jour leurs jetons. |
| **Comment repérer les jetons d'API V1** | Utilisez le journal d'audit  pour filtrer les jetons d'API V1 en cours d'utilisation. Vous pourrez ensuite télécharger les données dans un fichier CSV :<ol><li>Rensez-vous dans le [tableau de bord du journal d'audit.](https://hq1.appsflyer.com/audit-reader/dashboard)</li><li>Tapez «jeton d'API V1» dans la barre de recherche.</li><li>Dans le filtre **Service** , sélectionnez uniquement les **appels d'API**, puis filtrez les résultats.</li><li>Cliquez sur l'icône de téléchargement (en haut à droite de la page).<br />Votre fichier CSV se télécharge, il comprend l'ID de votre app, le service utilisé et l'URL de l'appel d'API.</li></ol> |
| **Action requise** | **Mettez à jour les API suivantes pour le jeton d'API V2 :**<ol><li>Allez sur la page <Anchor target="_blank" href="https://hq1.appsflyer.com/account/api-tokens">Jeton d'API.</Anchor></li><li>Dans Jeton d'API V2.0, cliquez sur l'icône **Copier dans le presse-papier**.</li><li>Pour chacune des API suivantes :<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/master_api_get">API principale V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">API Pull agrégée V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">API Pull d'extraction des données brutes V2</Anchor></li></ul><ol><li>Remplacez l'URL de l'API V1 par l'URL indiqué dans les liens ci-dessus.</li><li>Collez le jeton que vous avez copié dans l'en-tête d'authentification du porteur.<br />![token_v2_bearer.png](https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png)</li><li>Pour l'API **OpenDSR**, collez le jeton dans l'en-tête de porteur de requête :<br />`'Authorization' : 'Bearer %AuthTokenV2%'`</li></ol></li></ol> |
| **À propos des jetons d'API** | **En savoir plus sur les jetons d'API :**<ul><li><Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">Gestion des jetons d'API</Anchor><ul><li><Anchor target="_blank" href="/marketers/fr/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/pull-api-aggregate-data">API Pull agrégées</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/pull-api-raw-data">Données Brutes</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/send-opendsr-api-requests#gdpr-request-format">API OpenDSR</Anchor></li></ul></li></ul> |