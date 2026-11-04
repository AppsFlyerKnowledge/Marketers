---
title: Intégration de LG avec AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Developers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2022-07-03T10:31:42Z'
  edited_at: '2024-05-27T07:14:30Z'
  id: 7341725624081
  locale: fr
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/fr/articles/7341725624081
---
> **En bref :** Intégrez votre application LG Connected TV (CTV) à AppsFlyer pour recevoir des données d'attribution et d'événements pour vos campagnes sur LG.

<div id="about-lg-ctv-attribution" />

## À propos de l'attribution de LG CTV

Le système d'exploitation Webos de LG pour la diffusion en continu fonctionne sur tous les téléviseurs LG.

Les applications CTV diffusées sur LG peuvent s'intégrer à AppsFlyer via l'API pour recevoir des données d'attribution et des mesures de performance concernant les sources (organiques et non organiques) et les campagnes qui conduisent à l'ouverture de l'application et aux événements in-app. Les marketeurs s'appuient sur ces informations pour mesurer et optimiser les activités de marketing.

L'intégration de l'API LG prend en charge :

* Téléviseurs intelligents LG.
* Attribution CTV-to-CTV et enregistrement d'événements. Signification, attribution et enregistrement sur l'appareil LG de l'utilisateur.

<div id="integration-procedures" />

## Procédures d'intégration

Le tableau suivant répertorie les tâches requises pour intégrer votre application LG CTV à AppsFlyer.

| Tâche | Actions | Personnes concernées |
| --- | --- | --- |
| Configuration de l'application | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Créez un compte AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/user-management">Ajouter des utilisateurs de compte avec les permissions appropriées</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Ajoutez votre application LG CTV dans AppsFlyer</Anchor></li></ul> | Marketeur |
| Intégration API avec votre application (via S2S ou SDK) | Il existe deux méthodes d'intégration possibles : S2S et SDK.<br /><br />Pour la méthode S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">intégrez l'API AppsFlyer</Anchor> dans votre application avec des commandes pour signaler les événements suivants à AppsFlyer.<ul><li>Premières ouvertures</li><li>Événements in-app</li><li>Sessions</li></ul>**Remarque** :<ul><li>Les installations doivent être signalées avant les événements et sessions in-app.</li><li>Envoyer des événements à l'aide de l'API. Indiquez à votre développeur les événements à envoyer. Vérifiez que lorsque vous avez configuré l'API, vous avez configuré et mappé les événements à envoyer à AppsFlyer.</li></ul>Pour rendre compte des engagements dans les médias détenus, intégrez l'<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API d'engagement des impressions</Anchor>.<br /><br />Pour la méthode SDK, voir le hub des développeurs pour la <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk">documentation LG</Anchor>. | Développeur d'apps |
| Intégration des partenaires | Ajouter Samsung comme réseau publicitaire (partenaire intégré) dans AppsFlyer.<ol><li><Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#a-activate-partner">Activation du partenaire</Anchor></li><li>[Facultatif] Activez l'**<Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#e-install-attribution">attribution de type "View-through"</Anchor>**.</li></ol> | Marketeur |
| Configuration du lien | <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-direct-attribution-links">Apprendre à créer des liens d'attribution directe</Anchor> | Marketeur |
| Configuration du rapport/visualisation des données | <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilité-des-données">En savoir plus sur la disponibilité des données dans les tableaux de bord et les rapports</Anchor> | Mareketer / Ingénieur data |

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Retargeting | Pas pris en charge actuellement |
| Données de coûts | Les données relatives aux coûts doivent être envoyées via <Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">Importation de coûts</Anchor> en utilisant la méthode de téléchargement de fichiers par emmail. |
| Attribution | LG Ads utilise la modélisation probabiliste pour l'attribution. Cependant, la correspondance des identifiants n'est pas disponible actuellement. |

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Aperçu des plateformes CTV, PC et consoles</Anchor>

<div data-zendesk-anchors="about-lg-ctv-attribution=%C3%A0-propos-de-lattribution-de-lg-ctv 01H7Z17N0YAAGTDPMGZ89F7AVB=%C3%A0-propos-de-lattribution-de-lg-ctv integration-procedures=proc%C3%A9dures-dint%C3%A9gration 01H7Z17N0Y8RE5PS15N2JG5NRH=proc%C3%A9dures-dint%C3%A9gration 01H7Z17N0YCX89SYYJ1AMPM6W4=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%C3%A0-consulter-%C3%A9galement" />
