---
title: Intégration de la Xbox avec AppsFlyer
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-04-13T08:28:00Z'
  edited_at: '2024-05-26T09:00:27Z'
  id: 14504812967057
  locale: fr
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/fr/articles/14504812967057
---
> **En bref :** Intégrez votre application Xbox à AppsFlyer pour recevoir des données d'attribution et d'événements pour vos campagnes sur Xbox.

<div id="about-xbox-attribution" />

## À propos de l'attribution sur Xbox

Le système d'exploitation Xbox pour console et les applications CTV fonctionne sur toutes les Xbox.

Les applications fonctionnant sur Xbox peuvent s'intégrer à AppsFlyer via l'API S2S pour recevoir des données d'attribution et des mesures de performance concernant les sources (organiques) et les campagnes qui conduisent à l'ouverture de l'application et aux événements in-app. Les marketeurs s'appuient sur ces informations pour mesurer et optimiser l’activité marketing.

Ce que contient l’intégration de l'API Xbox :

* Xboxes.
* Attribution et enregistrement d'événements pour les applications Xbox. Signification, attribution et enregistrement sur l'appareil Xbox de l'utilisateur.

<div id="integration-procedures" />

## Procédures d'intégration

Le tableau suivant répertorie les tâches nécessaires pour intégrer votre application Xbox à AppsFlyer.

| Tâche | Actions | Personnes concernées |
| --- | --- | --- |
| Configuration de l'application | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Créez un compte AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/user-management">Ajouter des utilisateurs de compte avec les permissions appropriées</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Ajoutez votre application Xbox dans AppsFlyer</Anchor></li></ul> | Marketeur |
| Intégration API avec votre application (via S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Intégrez l'API AppsFlyer</Anchor> dans votre application avec des commandes pour signaler les événements suivants à AppsFlyer.<ul><li>Premières ouvertures</li><li>Évènements in-app</li><li>Sessions</li></ul>**Remarque**:<ul><li>Les premières ouvertures de l'application doivent être signalées avant les événements et les sessions in-app.</li><li>Pour le paramètre `device_ids`, sélectionnez le type `custom`.</li><li>Envoyer des événements à l'aide de l'API. Indiquer à votre développeur les événements à envoyer. Vérifier que lorsque vous avez configuré l'API, vous avez configuré et mappé les événements à envoyer à AppsFlyer.</li></ul>Pour rendre compte des engagements dans les médias détenus, intégrez l'<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API d'engagement des impressions</Anchor>. | Développeur d'apps |
| Configuration des rapports | <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilité-des-données">En savoir plus sur la disponibilité des données dans les tableaux de bord et les rapports</Anchor> | Marketeur/ingénieur data |

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Retargeting | Non pris en charge actuellement |
| Données de coûts | Les données relatives aux coûts doivent être envoyées via <Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">Cost Import</Anchor> en utilisant la méthode de téléchargement de fichiers par email. |

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Aperçu des plateformes CTV, PC et consoles</Anchor>

<div data-zendesk-anchors="about-playstation-attribution=%C3%A0-propos-de-lattribution-sur-xbox 01H7Z1NEAJMRWKHS4K168V0753=%C3%A0-propos-de-lattribution-sur-xbox integration-procedures=proc%C3%A9dures-dint%C3%A9gration 01H7Z1NEAJJY4ZRVKY74ACXAAR=proc%C3%A9dures-dint%C3%A9gration 01H7Z1NEAJRA11P7NG05KRKR8Q=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%C3%A0-consulter-%C3%A9galement" />
