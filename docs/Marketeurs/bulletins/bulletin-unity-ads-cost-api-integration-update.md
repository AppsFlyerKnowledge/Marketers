---
title: "Bulletin\_: Mise à jour de l'intégration de l'API Unity Ads"
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2024-06-20T14:43:15Z'
  edited_at: '2024-09-12T12:36:17Z'
  id: 26078530790289
  locale: fr
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/fr/articles/26078530790289
---
| **Nouveautés** | AppsFlyer a intégré une API à Unity qui lui permet d'obtenir les données de coûts. L'API sera bientôt mise à jour. Vous allez donc devoir mettre à jour votre intégration pour continuer à obtenir les données de coûts Unity. |
| --- | --- |
| **Date de la mise à jour** | 6 août 2024 |
| **Important à savoir** | <ul><li>Unity introduit une nouvelle intégration d'API de coûts.</li><li>L'ancienne intégration de l'API de coûts permet d'obtenir des données de coûts, et ce jusqu'à sa date d'obsolescence, soit le 1er octobre 2024.</li></ul> |
| **Ce que vous devez faire** | Vous devez mettre à jour vos informations d'identification pour la nouvelle intégration de l'API Unity Cost pour continuer à obtenir des données de coûts après le 1er octobre 2024.<br /><br />Les informations d'identification demandées sont les suivantes :<ul><li>ID principal de l’organisation</li><li>Clé secrète du compte de service</li><li>ID de clé du compte de service</li></ul>Suivez les instructions des sections ci-dessous pour mettre à jour l'intégration des coûts Unity dans AppsFlyer. L'intégration comporte 2 étapes :<ol><li>[Obtenir les nouveaux identifiants Unity](/docs/bulletin-unity-ads-cost-api-integration-update#get-unity-credentials).</li><li>[Mettre à jour l'intégration de l'API Unity Cost en saisissant les identifiants dans AppsFlyer.](/docs/bulletin-unity-ads-cost-api-integration-update#set-up-unity-cost-api-integration-in-appsflyer)</li></ol> |

## Procédures d'intégration de l'API Unity Cost

L'intégration de l'API Unity Cost se fait en deux étapes :

1. Récupérer les nouveaux identifiants Unity.
2. Mettre à jour l'intégration de l'API Unity Cost en saisissant les identifiants dans AppsFlyer.

Les étapes sont détaillées dans les sections suivantes.

<div id="get-unity-credentials" />

<Accordion title="Obtenir les identifiants Unity">

Les éléments d'identification requis pour l'intégration de l'API Unity Cost sont les suivants :

* ID principal de l’organisation
* Clé secrète du compte de service
* ID de clé du compte de service

**Remarque** : Il est recommandé de créer un nouveau compte de service Unity pour obtenir la clé secrète et l'ID de clé. Vous trouverez ci-dessous des instructions sur la marche à suivre.

**Pour configurer un compte de service Unity et obtenir les éléments d'identification requis pour l'intégration de l'API Unity cost** :

1. Connectez-vous à votre compte Unity Cloud.
2. Dans le menu de gauche, allez dans **Croissance (Acquisition utilisateurs Unity Ads)** > **Paramètres.**  
    [![](https://files.readme.io/2fcc359913c11a4bcce29e1aaf30cb84161a09e39b14cdcd4ad4f141debd1798-26134832885137.png)](https://files.readme.io/2fcc359913c11a4bcce29e1aaf30cb84161a09e39b14cdcd4ad4f141debd1798-26134832885137.png)
3. Recherchez, copiez et enregistrez l'**ID principal de l'organisation**.  
   Exemple d'ID principal d'organisation : 5773102414648
4. Dans le menu de gauche, allez dans **Croissance (Unity Ads User Acquisition)** > **`{}` Gestion d’API**, puis dans la section **Stats d’API v2.0**, **cliquez sur Compte de service**.  
    [![](https://files.readme.io/36dd40e68eeeb6562c1e5a19f92873e8eb99b66f80c45db066e0ff54b66d0080-26369979011985.png)](https://files.readme.io/36dd40e68eeeb6562c1e5a19f92873e8eb99b66f80c45db066e0ff54b66d0080-26369979011985.png)
5. Cliquez sur **+ Nouveau** pour créer un nouveau compte de service.  
    [![](https://files.readme.io/3a53e932bf8d023e910b66f74ea6f630c8048787885d45ea4206b2f1f3d4f65e-26136910848785.png)](https://files.readme.io/3a53e932bf8d023e910b66f74ea6f630c8048787885d45ea4206b2f1f3d4f65e-26136910848785.png)
6. Dans la section **Clés**, cliquez sur **+ Ajouter une clé** afin de créer une clé pour le compte de service.  
    [![](https://files.readme.io/f528d44a9659372bfeeb8d13538f9caf0a7955f53194194543988af983f9c517-26136957380753.png)](https://files.readme.io/f528d44a9659372bfeeb8d13538f9caf0a7955f53194194543988af983f9c517-26136957380753.png)
7. Copiez et enregistrez l'**ID de clé** et la **clé secrète**. **Remarque** : C'est la seule fois où vous pourrez accéder à la clé secrète, alors pensez à bien la sauvegarder quelque part !
   * Exemple de clé secrète de compte de service : b0de73b1-b3ad-4175-bf9b-4913a0ff83ec
   * Exemple d'ID de clé secrète de compte de service : A0x\_CQHIxH4ABPS1QR9TCy6EJDVG8QL5  
      [![](https://files.readme.io/6de3cd868541ab5487370dbefc758a375c3395434e07361f74553a1b9a9c7d57-26136957383697.png)](https://files.readme.io/6de3cd868541ab5487370dbefc758a375c3395434e07361f74553a1b9a9c7d57-26136957383697.png)
8. Dans la section **Rôles de l'organisation**, cliquez sur **+ Gérer les rôles de l'organisation**.  
    [![](https://files.readme.io/d368d6c611db2a8df76e341c7b6a692128b5ae37f51f6642fa7e60cd00f29689-26136910860689.png)](https://files.readme.io/d368d6c611db2a8df76e341c7b6a692128b5ae37f51f6642fa7e60cd00f29689-26136910860689.png)
9. Dans **Modifier les rôles de l'organisation**, définissez **Croissance sur Publicité** **Stats d’API MMP Lecteur**.  
    [![](https://files.readme.io/f1243cb65978d2f96d148ceb34b528ca005091c38dbed95368923047b3cfbfd1-26136957386513.png)](https://files.readme.io/f1243cb65978d2f96d148ceb34b528ca005091c38dbed95368923047b3cfbfd1-26136957386513.png)

</Accordion>

<div id="set-up-unity-cost-api-integration-in-appsflyer" />

<Accordion title="Mettre à jour l'intégration de l'API Unity Cost dans AppsFlyer">

**Pour mettre à jour l'API Unity Cost dans AppsFlyer** :

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégrations actives** puis choisissez **Unity**.
2. Cliquez sur **Gérer l'intégration**.
3. Ouvrez l'onglet **Coûts** du partenaire intégré.
4. Activez le bouton **Obtenir les données de coûts**. Les conditions pour se connecter à l'écran partenaire s’affichent.
5. Saisissez vos identifiants Unity.
6. **Cliquez** sur Enregistrer les coûts.
7. Cliquez sur **Tester la connexion.**  
   * L'API est active. AppsFlyer collecte les données du partenaire 6 fois par jour, soit en moyenne toutes les quatre heures.

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data">En savoir plus sur la connexion des intégrations de coûts</Anchor>

</Accordion>

<div data-zendesk-anchors="unity-cost-api-integration-procedures=proc%C3%A9dures-dint%C3%A9gration-de-lapi-unity-cost h_01J11ZP5XG6VDSQKRWASAYK4QJ=proc%C3%A9dures-dint%C3%A9gration-de-lapi-unity-cost h_01J14M3C6WNXPJJQHVWVNFB4GS=get-unity-credentials h_01J11ZHPJDZDZ7S24ZQK58B2FN=set-up-unity-cost-api-integration-in-appsflyer" />
