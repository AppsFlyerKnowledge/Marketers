---
title: Intégration de Roku avec AppsFlyer
metadata:
  keywords:
    - Advertisers
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
  created_at: '2021-07-19T09:00:10Z'
  edited_at: '2024-06-23T12:16:42Z'
  id: 4404257169169
  locale: fr
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/fr/articles/4404257169169
---
> **En bref :** Intégrez votre application Roku Connected TV (CTV) à AppsFlyer pour recevoir des données d'attribution et d'événement pour vos campagnes sur Roku.

## À propos de l'attribution de Roku CTV

Le système d'exploitation Roku pour le streaming fonctionne sur tous les appareils Roku, y compris les lecteurs de streaming et les téléviseurs Roku. 

Les applications CTV, les chaînes AKA et le streaming sur Roku peuvent s'intégrer à AppsFlyer via l'API pour recevoir des données d'attribution et des mesures de performances sur les sources (non organiques ou organiques) et les campagnes payantes qui génèrent des installations d'applications ainsi que les événements post-installation. Les marketeurs s'appuient sur ces informations pour mesurer et optimiser leurs activités marketing.

L'intégration de l'API Roku prend en charge :

* Les appareils Roku Smart TV et CTV. L'intégration **ne prend pas** en charge les appareils mobiles, les tablettes ou les ordinateurs de bureau (desktop).
* L’attribution CTV-to-CTV et enregistrement des événements. Cela sous-entend l’attribution et l’enregistrement des installations de l'application Roku et des événements qui se produisent sur l'appareil Roku d'un utilisateur.

<div id="roku-attribution-flow" />

### Flux d'attribution Roku

![7435_CTV__3_.png](https://files.readme.io/51ab9ce816986134ed118ac7b8dd94336fff53d6a00daf5332eef2934c0048d8-4431541172241.png)

## Procédures d'intégration

Le tableau suivant répertorie les tâches requises pour intégrer votre application Roku CTV à AppsFlyer.

| Tâche | Actions | Personnes concernées |
| --- | --- | --- |
| Configuration de l'application | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Créez un compte AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/user-management">Ajouter des utilisateurs de compte avec les autorisations appropriées</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Ajoutez votre application Roku CTV dans AppsFlyer</Anchor></li></ul> | Marketeur |
| Intégration API avec votre application (via S2S ou SDK) | Vous pouvez utiliser deux méthodes d'intégration : S2S et SDK.<br /><br />Pour la méthode S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">intégrez l'API AppsFlyer</Anchor> dans votre application avec des commandes pour signaler les événements suivants à AppsFlyer.<ul><li>Installations</li><li>Évènements in-app</li><li>Sessions</li></ul>**Remarque**:<ul><li>Les installations doivent être remontées avant les événements in-app et les sessions dans l'application.</li><li>Envoyez des événements à l'aide de l'API. Transmettez à votre développeur quels événements envoyer. Vérifiez que lorsque vous configurez l'API, vous configurez et mappez les événements à envoyer à AppsFlyer.</li></ul>Pour signaler les engagements médiatiques détenus, intégrez l' <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API d'engagement avec les impressions.</Anchor><br /><br />Pour la méthode SDK, consultez la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/roku-brighscript#appsflyerrokusdk---interface">documentation du hub de développement pour Roku (BrightScript)</Anchor>. | Développeur d'apps |
| Intégration des partenaires | Ajoutez Roku en tant que réseau publicitaire (partenaire intégré) dans AppsFlyer :<ol><li><Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#a-activate-partner">Activation du partenaire</Anchor></li><li>[Facultatif] Modifier <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#e-install-attribution">**l'attribution par clic**</Anchor>. 14 jours par défaut<br />Le paramètre d'attribution par clic vous permet de définir la **durée maximale entre le clic et l'installation**. Seules les installations (premiers lancements) qui ont lieu pendant cette période d'analyse peuvent être attribuées à Roku. Voir <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">Fenêtres de contrôle de clics</Anchor>.</li><li>[Facultatif] Activez et modifiez **<Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#e-install-attribution">l'attribution après affichage</Anchor>.** 14 jours par défaut</li></ol>Utilisez le curseur pour définir le **délai maximum entre l'impression et l'installation.**. Seules les installations (premiers lancements) qui ont lieu dans cette fenêtre rétrospective, suite à une impression de publicité, sont attribuées au partenaire, à condition qu'il n'y ait pas eu d'autre clic pertinent sur la publicité.  Voir <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">Attribution post-vue</Anchor>. | Marketeur |
| Configuration du rapport/affichage des données | <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilité-des-données">En savoir plus sur la disponibilité des données dans les tableaux de bord et les rapports</Anchor> | Marketeur/Ingénieur Data |

<div id="roku-discrepancies-with-appsflyer" />

<Accordion title="Décalages entre Roku et AppsFlyer">

| Cause | Roku | AppsFlyer |
| --- | --- | --- |
| Clic sur la fenêtre rétrospective d'attribution | 14 jours | 1 heure à 14 jours Assurez-vous de définir 14 jours dans l'intégration du partenaire Roku. |
| Fenêtre rétrospective d'attribution post vue | 14 jours | 1 heure à 14 jours Assurez-vous de définir 14 jours dans l'intégration du partenaire Roku. |
| sans rapport | Roku enregistre les nouvelles installations au moment de l'installation. | AppsFlyer enregistre les nouvelles installations lors du premier lancement de l'application. |
| Attribution inter-appareils | Roku attribue les données à ses utilisateurs qui cliquent et installent sur différents appareils, par exemple, 2 téléviseurs différents. | AppsFlyer attribue des appareils uniques, qui effectuent à la fois l'engagement et l'installation |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Retargeting | Non pris en charge actuellement |
| Données de coûts | Les données de coût doivent être envoyées via<Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">Cost Import</Anchor>en utilisant la méthode de téléchargement du fichier par email. |

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Aperçu des plateformes CTV, PC et consoles</Anchor>

<div data-zendesk-anchors="about-roku-ctv-attribution=%C3%A0-propos-de-lattribution-de-roku-ctv 01H7Z13QPB40JD02GC4CJ9QCK4=%C3%A0-propos-de-lattribution-de-roku-ctv roku-attribution-flow=flux-dattribution-roku 01H7Z13QPBTKZ9BVCMGASYEM0R=flux-dattribution-roku integration-procedures=proc%C3%A9dures-dint%C3%A9gration 01H7Z13QPBZKT03CFBPEA50FVM=proc%C3%A9dures-dint%C3%A9gration 01H7Z13QPCJZZCHBSBFQNEDTMQ=roku-discrepancies-with-appsflyer 01H7Z13QPC6018MZ1KJKDFS5JN=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%C3%A0-consulter-%C3%A9galement" />
