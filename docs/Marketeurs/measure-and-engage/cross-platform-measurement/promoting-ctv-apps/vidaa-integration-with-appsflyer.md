---
title: Intégration de Vidaa avec AppsFlyer
metadata:
  keywords:
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
  created_at: '2022-11-06T08:13:09Z'
  edited_at: '2024-05-27T08:35:05Z'
  id: 10400222972433
  locale: fr
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/fr/articles/10400222972433
---
> **En bref :** Intégrez votre application Vidaa Connected TV (CTV) à AppsFlyer pour recevoir des données d'attribution et d'événements pour vos campagnes sur Vidaa.

## À propos de l'attribution de Vidaa CTV

Le système d'exploitation Vidaa pour le streaming fonctionne sur tous les téléviseurs Vidaa.

Les applications CTV diffusées sur Vidaa peuvent s'intégrer à AppsFlyer via l'API pour recevoir des données d'attribution et des mesures de performance concernant les sources (organiques uniquement, pour l’instant) et les campagnes qui conduisent à l'ouverture de l'application et aux événements in-app. Les marketeurs s'appuient sur ces informations pour mesurer et optimiser l’activité marketing de leurs produits.

L'intégration de l'API Vidaa prend en charge :

* Téléviseurs intelligents Vidaa.
* Attribution CTV-to-CTV et enregistrement d'événements. Signification, attribution et enregistrement sur l'appareil Vidaa de l'utilisateur.

## Procédures d'intégration

Le tableau suivant énumère les tâches nécessaires pour intégrer votre application Vidaa CTV à AppsFlyer. Pour suivre votre progression, vous pouvez téléchargez <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx">cette feuille de calcul</Anchor>.

| Tâche | Actions | Personnes concernées |
| --- | --- | --- |
| Configuration de l'application | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Créez un compte AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/user-management">Ajouter des utilisateurs de compte avec les permissions appropriées</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Ajoutez votre application Vidaa CTV dans AppsFlyer</Anchor></li></ul> | Marketeur |
| Intégration API avec votre application (via S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Intégrez l'API AppsFlyer CTV</Anchor> dans votre application CTV avec des commandes pour signaler les événements suivants à AppsFlyer.<ul><li>Premières ouvertures</li><li>Évènements in-app</li><li>Sessions</li></ul>**Remarque**:<ul><li>Les installations doivent être signalées avant les événements et sessions in-app.</li><li>Envoyer des événements à l'aide de l'API. Indiquez à votre développeur les événements à envoyer. Vérifiez que lorsque vous avez configuré l'API, vous avez configuré et mappé les événements à envoyer à AppsFlyer.</li><li>Pour le paramètre `device_ids` , sélectionnez le type `custom`.</li></ul>Pour rapporter les engagements sur les médias propriétaires, intégrez l'<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API d'engagement par impression.</Anchor> | Développeur d'apps |
| Configuration du lien | <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-direct-attribution-links">Apprendre à créer des liens d'attribution directe</Anchor> | Marketeur |
| Configuration du rapport/visualisation des données | <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilité-des-données">En savoir plus sur la disponibilité des données dans les tableaux de bord et les rapports</Anchor> | Marketeur / Ingénieur data |

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Sources non-organiques | Prochainement disponible |
| Retargeting | Pas de prise en charge actuellement |
| Données de coûts | Les données relatives aux coûts doivent être envoyées via <Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">Cost Import</Anchor> en utilisant la méthode de téléchargement de fichiers par email. |

</Accordion>

> 📄 **À consulter également**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Aperçu des plateformes CTV, PC et consoles</Anchor>

<div data-zendesk-anchors="about-vidaa-ctv-attribution=%C3%A0-propos-de-lattribution-de-vidaa-ctv 01H7Z180QRR77E1GBQ0P0RHVN5=%C3%A0-propos-de-lattribution-de-vidaa-ctv integration-procedures=proc%C3%A9dures-dint%C3%A9gration 01H7Z180QR6HT4R3N9DYSM8WB9=proc%C3%A9dures-dint%C3%A9gration 01H7Z180QR0QQ0HK3N5N1G4ENZ=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%C3%A0-consulter-%C3%A9galement" />
