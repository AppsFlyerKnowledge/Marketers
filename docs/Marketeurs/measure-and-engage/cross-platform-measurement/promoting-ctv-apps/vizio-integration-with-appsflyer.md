---
title: Intégration de Vizio avec AppsFlyer
metadata:
  keywords:
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
  created_at: '2022-03-27T15:48:04Z'
  edited_at: '2024-05-27T06:18:50Z'
  id: 5045234293777
  locale: fr
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/fr/articles/5045234293777
---
> **En bref :** Intégrez votre application (chaîne) Vizio Connected TV (CTV) avec AppsFlyer pour recevoir l'attribution et les données d'événements pour vos campagnes sur Vizio.

<div id="about-vizio-ctv-attribution" />

## À sujet de l’attribution de Vizio CTV

Le système d’exploitation Vizio SmartCast pour le streaming fonctionne sur tous les téléviseurs Vizio.

Les applications CTV diffusées sur Vizio peuvent s’intégrer à AppsFlyer via l’API pour recevoir des données d’attribution et des mesures de performance sur les sources (non organiques ou organiques) et les campagnes payantes qui génèrent des événements ouverts et intégrés à l’application. Les marketeurs s’appuient sur ces informations pour mesurer et optimiser l’activité marketing de leurs produits.

L’intégration de l’API Vizio comprend :

* Les téléviseurs intelligents Vizio.
* L’attribution CTV-to-CTV et enregistrement d’événements. Signification, attribution et enregistrement des premières ouvertures d’applications Vizio (l’équivalent des installations) et des événements qui se produisent sur l’appareil Vizio d’un utilisateur.

<div id="vizio-attribution-flow" />

### Flux d’attribution Vizio

<Image align="center" alt="CTV_attribution_flow_-_Vizio__1_.png" src="https://files.readme.io/f4ab4b6c9e045fe00b537814fa9f10746b525a5512e5805e62eb0c2e4c9a8615-6318406872337.png" />

<div id="integration-procedures" />

## Procédures d'intégration

Le tableau suivant répertorie les tâches requises pour intégrer votre application Vizio CTV à AppsFlyer.

| Tâche | Actions | Personnes concernées |
| --- | --- | --- |
| Configuration de l’application | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Créez un compte AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/user-management">Ajouter des utilisateurs de compte avec les autorisations appropriées</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Ajoutez votre application Vizio CTV dans AppsFlyer</Anchor></li></ul> | Marketeur |
| Intégration de l’API avec votre application (via S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Intégrez l’API CTV AppsFlyer</Anchor> dans votre application CTV avec des commandes pour signaler les événements suivants à AppsFlyer.<ul><li>Premières ouvertures</li><li>Événements in-app</li><li>Sessions</li></ul>**Remarque** :<ul><li>Les installations doivent être signalées avant les événements et les sessions dans l’application.</li><li>Envoyez des événements à l’aide de l’API. Indiquez à votre développeur les événements à envoyer. Vérifiez que lorsque vous configurez l’API, vous configurez et mappez les événements à envoyer à AppsFlyer.</li></ul>Pour générer des rapports sur les engagements avec les médias propriétaires, intégrez <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">l’API d’engagement par impression.</Anchor> | Développeur d'apps |
| Intégration des partenaires | Ajoutez Vizio en tant que réseau publicitaire (partenaire intégré) dans AppsFlyer :<ol><li><Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#a-activate-partner">Activation du partenaire</Anchor></li><li>[Facultatif] Activez **<Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#e-install-attribution">l’attribution après affichage</Anchor>.**</li></ol> | Marketeur |
| Configuration du lien | <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-direct-attribution-links">Découvrez comment créer des liens d’attribution directe</Anchor> | Marketeur |
| Paramétrage/affichage des données du rapport | <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilité-des-données">En savoir plus sur la disponibilité des données dans les tableaux de bord et les rapports</Anchor> | Marketeur / Ingénieur data |

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Retargeting | Non pris en charge actuellement |
| Attribution post vue | La valeur par défaut est de 24 heures |
| Données de coûts | Les données de coût doivent être envoyées via  <Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">Cost Import</Anchor><Anchor target="_blank" href="/marketers/fr/docs/import-cost-data"> en utilisant la méthode de téléchargement de fichier par e-mail.</Anchor> |

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Aperçu des plateformes CTV, PC et consoles</Anchor>

<div data-zendesk-anchors="about-vizio-ctv-attribution=%C3%A0-sujet-de-lattribution-de-vizio-ctv 01H7Z16QWWCPR309JDKV7H0469=%C3%A0-sujet-de-lattribution-de-vizio-ctv vizio-attribution-flow=flux-dattribution-vizio 01H7Z16QWW3GJEAGV0F3JHTKE1=flux-dattribution-vizio integration-procedures=proc%C3%A9dures-dint%C3%A9gration 01H7Z16QWW1WX5F947WPH9HBQX=proc%C3%A9dures-dint%C3%A9gration 01H7Z16QWX24K8QCEJVBX1SQEA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%C3%A0-consulter-%C3%A9galement" />
