---
title: Intégration de Tealium avec AppsFlyer
metadata:
  keywords:
    - Marketers
    - TEST ID LOC
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-22T16:09:24Z'
  edited_at: '2024-02-14T08:41:03Z'
  id: 10820404821393
  locale: fr
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/fr/articles/10820404821393
---
> **En bref :** la plateforme de données client Tealium connecte les données clients à travers le Web, le mobile, l'IoT et le hors ligne. Découvrez comment partager automatiquement les données de conversion avec Tealium.

<Image alt="Tealium_icon.png" src="https://files.readme.io/e3cc1f95e8ce2de6fa83df63ff78dd4f4f76aebe1acb8e9378aa5b6aa4134364-10820461521681.png" width="276px" />

## Présentation

En intégrant Tealium à AppsFlyer, les clients mobile peuvent exploiter le SDK d'attribution mobile d'AppsFlyer et envoyer les données de conversion d'attribution directement à leur profil AudienceStream de Tealium.

> 🚧 **Important !**
>
> <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média">Certaines sources média</Anchor> limitent le partage de données avec des tiers .Par conséquent, les postbacks pour les événements limités ne seront pas envoyés à ce partenaire, quelle que soit la sélection configurée pour l'envoi de postbacks.

## Configurer Tealium

Les méthodes suivantes vous permettent d'intégrer Tealium à AppsFlyer :

* Intégration côté client
* Intégration côté serveur

### Intégration côté client

Utilisez des commandes à distance pour les bibliothèques iOS et Android, permettant au code natif d'être déclenché dans le SDK AppsFlyer.

**Pour intégrer Tealium avec l'intégration côté client :**

* Suivez le <Anchor target="_blank" href="https://docs.tealium.com/platforms/remote-commands/integrations/appsflyer/">guide d'intégration des commandes à distance</Anchor>

### Intégration côté serveur

Configurez le connecteur AppsFlyer App Events dans votre compte Customer Data Hub pour transmettre les données entre Tealium et AppsFlyer en temps réel.

**Pour intégrer Tealium avec l'intégration côté serveur :**

* Suivez le guide du connecteur <Anchor target="_blank" href="https://docs.tealium.com/server-side-connectors/appsflyer-app-events-connector/">Événements d'app AppsFlyer</Anchor>

<div data-zendesk-anchors="overview=pr%C3%A9sentation h_01H9HWK1ACY09ZVD7WHEQR4MR3=pr%C3%A9sentation h_01H9HWK1ACA6A743PDY3Q1Y0KV=important- setting-up-tealium=configurer-tealium h_01H9HWK1AC27GPZPZR13SFC3GM=configurer-tealium clientside-integration=int%C3%A9gration-c%C3%B4t%C3%A9-client h_01H9HWK1ACH6K0FDTVCHAPSKME=int%C3%A9gration-c%C3%B4t%C3%A9-client serverside-integration=int%C3%A9gration-c%C3%B4t%C3%A9-serveur h_01H9HWK1ACDZQEYVRZ7QWQ4KY3=int%C3%A9gration-c%C3%B4t%C3%A9-serveur" />
