---
title: Intégration de Samsung avec AppsFlyer
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
  created_at: '2022-05-03T09:19:48Z'
  edited_at: '2024-05-27T06:48:07Z'
  id: 5860544738065
  locale: fr
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/fr/articles/5860544738065
---
> **En bref :** Intégrez votre application Samsung Connected TV (CTV) à AppsFlyer pour recevoir des données d’attribution et d’événement pour vos campagnes sur Samsung.

<div id="about-samsung-ctv-attribution" />

## À propos de l’attribution CTV de Samsung

Le système d’exploitation Tizen de Samsung pour le streaming fonctionne sur tous les téléviseurs Samsung.

Les applications CTV diffusées sur Samsung peuvent s’intégrer à AppsFlyer via l’API pour recevoir des données d’attribution et des mesures de performance sur les sources (organiques et non organiques) et les campagnes qui génèrent des événements ouverts et intégrés à l’application. Les marketeurs s’appuient sur ces informations pour mesurer et optimiser les activités marketing.

L’intégration de l’API Samsung prend en charge :

* Les Smart TV Samsung.
* L’attribution CTV-to-CTV et enregistrement d’événements. Signification, attribution et enregistrement sur l’appareil Samsung d’un utilisateur.

<div id="samsung-attribution-flow" />

### Flux d’attribution Samsung

<Image align="center" alt="CTV_attribution_flow_-_Samsung__1_.png" src="https://files.readme.io/a1031878e8aced81da5762d06ae0163770cd73b9a7c91224ea7665aa142d2ce8-7215151128209.png" />

<div id="h_01M349521V96NRS5CJKXZKMA6P" />

<div id="integration-procedures" />

## Procédures d'intégration

Le tableau suivant répertorie les tâches requises pour intégrer votre application Samsung CTV à AppsFlyer.

| Tâche | Actions | Personnes concernées |
| --- | --- | --- |
| Configuration de l’application | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Créez un compte AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/user-management">Ajouter des utilisateurs de compte avec les autorisations appropriées</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Ajouter votre application Samsung CTV dans AppsFlyer</Anchor></li></ul> | Marketeur |
| Intégration de l’API avec votre application (via S2S ou SDK) | Il existe deux méthodes d’intégration que vous pouvez utiliser : S2S et SDK.<br /><br />Pour la méthode S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">intégrez l’API AppsFlyer</Anchor> dans votre application avec des commandes pour signaler les événements suivants à AppsFlyer.<ul><li>Premières ouvertures</li><li>Évènements in-app</li><li>Sessions</li></ul>**Remarque** :<ul><li>Les installations doivent être signalées avant les événements et les sessions dans l’application.</li><li>Envoyez des événements à l’aide de l’API. Indiquez à votre développeur les événements à envoyer. Vérifiez que lorsque vous configurez l’API, vous configurez et mappez les événements à envoyer à AppsFlyer.</li></ul>Pour générer des rapports sur les engagements avec les médias propriétaires, intégrez <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">l’API d’engagement par impression.</Anchor><br /><br />Pour la méthode SDK, consultez la documentation du hub de développeur pour <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk">Samsung</Anchor>. | Développeur d'apps |
| Intégration des partenaires | Ajoutez Samsung en tant que réseau publicitaire (partenaire intégré) dans AppsFlyer.<ol><li><Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#a-activate-partner">Activation du partenaire</Anchor></li><li>[Facultatif] Activez **<Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#e-install-attribution">l’attribution après affichage</Anchor>.**</li></ol> | Marketeur |
| Configuration du lien | <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-direct-attribution-links">Découvrez comment créer des liens d’attribution directe</Anchor> | Marketeur |
| Paramétrage/affichage des données du rapport | <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilité-des-données">En savoir plus sur la disponibilité des données dans les tableaux de bord et les rapports</Anchor> | Marketeur / Ingénieur data |

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Retargeting | Non pris en charge actuellement |
| Données de coûts | Les données de coût doivent être envoyées via  <Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">Cost Import</Anchor> <Anchor target="_blank" href="/marketers/fr/docs/import-cost-data"> en utilisant la méthode de téléchargement de fichier par e-mail.</Anchor> |

</Accordion>

> 📄 **À consulter également**
>
> <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Aperçu des plateformes CTV, PC et consoles</Anchor>

<div data-zendesk-anchors="about-samsung-ctv-attribution=%C3%A0-propos-de-lattribution-ctv-de-samsung 01H7Z17A1QPJQH9R5MRBVTMG37=%C3%A0-propos-de-lattribution-ctv-de-samsung samsung-attribution-flow=flux-dattribution-samsung 01H7Z17A1Q03CEJT848FRFHDPQ=flux-dattribution-samsung integration-procedures=proc%C3%A9dures-dint%C3%A9gration 01H7Z17A1QQN4FYJXZFS5FP2NY=proc%C3%A9dures-dint%C3%A9gration 01H7Z17A1QVW58B2FZE7SDJHHJ=traits-and-limitations h_01HE7RG1GE2E37NN4WT1XYG9YX=%C3%A0-consulter-%C3%A9galement" />
