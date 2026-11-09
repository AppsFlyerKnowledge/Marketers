---
title: Concepts d'attribution des plates-formes CTV, PC et consoles
metadata:
  keywords:
    - Attribution
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
  created_at: '2021-07-15T11:30:45Z'
  edited_at: '2024-03-17T12:01:51Z'
  id: 4404083608849
  locale: fr
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/fr/articles/4404083608849
---
> D'un seul regard Découvrez comment fonctionne l'attribution pour les plateformes CTV, PC et consoles afin de permettre à AppsFlyer de recevoir des données d'attribution et d'événements pour vos campagnes sur ces appareils multiplateformes.

<Image align="center" alt="7435_CTV_image.png" src="https://files.readme.io/7fc57fd80ad86bb173bcf81581b9fe8b4625ed2a044d302a6d72194560019e81-4410336840977.png" width="471px" />

<div id="tv-screens" />

<div id="the-appsflyer-cross-platform-solution" />

## La solution multiplateforme AppsFlyer

Dans le paysage numérique d'aujourd'hui, les professionnels de la croissance doivent relever le défi d'atteindre les consommateurs à travers de multiples dispositifs et plateformes. Les méthodes de mesure traditionnelles ne permettent pas d'appréhender l'ensemble des parcours des utilisateurs qui s'étendent sur plusieurs plateformes. La mesure multiplateforme est essentielle pour comprendre l'impact des activités de marketing et prendre des décisions éclairées.

AppsFlyer offre une solution multiplateforme étendue qui complète les outils d'attribution mobiles conventionnels. Il aide les professionnels de la croissance à mesurer et à attribuer avec précision les efforts de marketing lorsque les utilisateurs interagissent sur plusieurs plateformes et appareils. Cette solution est axée sur les plates-formes CTV, PC et consoles.

Les annonceurs peuvent faire la promotion d'une application sur la même plateforme ou sur une plateforme différente de celle sur laquelle la publicité est affichée. Par exemple, un annonceur peut afficher une publicité pour une application Steam sur la plateforme Steam. Ils peuvent également afficher une publicité pour une application Steam sur le web, par exemple via Google Ads. Quelle que soit leur stratégie marketing, les annonceurs s'intègrent à AppsFlyer pour recevoir des données d'attribution et des mesures de performance concernant les sources (non organiques ou organiques) et les campagnes qui génèrent des installations d'applications sur les plates-formes CTV, PC et consoles, ainsi que des événements post-installation. Les spécialistes du marketing utilisent ces informations pour calculer la valeur de la durée de vie de l'utilisateur (LTV) et pour mesurer et optimiser les activités de marketing. <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">En savoir plus sur l'attribution d'AppsFlyer</Anchor>

<div id="integrate-with-ad-networks-that-support-specified-ctv-pc-and-console-platforms" />

<div id="supported-platforms" />

### Plateformes prises en charge

<table><thead><tr><th>Plateforme</th><th colspan="2">Méthode d'intégration AppsFlyer</th></tr><tr><th> </th><th>S2S</th><th>SDK</th></tr></thead><tbody><tr><td>Android TV</td><td><span>-</span></td><td><span><span>✓</span></span></td></tr><tr><td>tvOS (Apple TV)</td><td><span>-</span></td><td><span><span>✓</span></span></td></tr><tr><td>MacOS</td><td><span><span>-</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Amazon Fire TV</td><td><span><span>-</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Chromecast</td><td><span><span>-</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Roku</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Vizio</td><td><span><span>✓</span></span></td><td><span>-</span></td></tr><tr><td>Samsung</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>LG</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>PlayStation</td><td><span><span>✓</span></span></td><td><span>-</span></td></tr><tr><td>Vidaa</td><td><span><span>✓</span></span></td><td><span>-</span></td></tr><tr><td>Steam</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Native PC</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Meta Quest (Oculus)</td><td><span><span>✓</span></span></td><td><span><span><span>✓</span></span></span></td></tr><tr><td>Epic Games</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td>Nintendo Switch</td><td><span><span>✓</span></span></td><td><span>-</span></td></tr><tr><td>Xbox</td><td><span><span>✓</span></span></td><td><span>-</span></td></tr></tbody></table>

<div id="cross-platform-attribution-flows" />

## Attribution multiplateforme

Lors de la commercialisation d'applications sur les plates-formes CTV, PC et consoles, plusieurs flux- de l'affichage de la publicité (impression ou clic) à l'attributionAppsFlyer - s'appliquent à toutes les plates-formes :

* Lien d'attribution de clics
* Lien OneLink multiplateforme
* SRN (self-reporting network, également connu sous le nom de SAN, self-attributing network)
* Page d'atterrissage multiplateforme

Chaque application, annonceur et plateforme peut avoir un ou plusieurs de ces flux mis en œuvre en même temps. Les sections suivantes expliquent les différents types de flux et quand chacun d'entre eux est utilisé.

<div id="direct-attribution-link" />

<Accordion title="Lien d'attribution de clics">

Les liens d'attribution directe sont des liens AppsFlyer qui prennent en charge la redirection et l'attribution pour une seule application de destination sur une seule plateforme à la fois. Ils sont généralement utilisés pour :

* Publicité de plateforme à plateforme. Cela signifie que la plateforme qui affiche la publicité et celle qui supporte l'application sont identiques. Par exemple, un annonceur peut afficher une publicité pour une application Samsung TV sur un téléviseur Samsung.
* Publicité de plateforme à plateforme, la destination/plateforme étant prédéterminée. Par exemple, une page d'atterrissage d'un site web de bureau affiche une publicité avec un ou plusieurs boutons, chaque bouton redirigeant vers un magasin/marché spécifique de la plateforme.

Les liens d'attribution directe prennent en charge à la fois la modélisation probabiliste et les méthodes d'attribution déterministes (lorsqu'un identifiant est fourni dans le lien), selon lesquelles une installation effectuée par un utilisateur est associée à un clic publicitaire ou à une impression. Le flux d'attribution est illustré dans le diagramme suivant.

<Image align="center" alt="Flux d'attribution CTV - Flux de liens d'attribution directe.png" src="https://files.readme.io/2af32b096faa381843040314c9c183056256d03a7e2e6095e72a59bb7211727f-19374976446225.png" />

Comme les liens d'attribution directe concernent une application sur une plateforme spécifique prédéterminée et mènent à une destination spécifique, ils contiennent toujours l'identifiant de l'application et les informations relatives à la plateforme dans l'URL.

Exemple de lien d'attribution directe : `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/1234561?&af_media_source=game_media_source&af_campaign=campaign_yellow&af_campaign_id=1234&af_ad=game_ad_name&af_adset=game_adset_name&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F1176160%2FSpace_Wars%2F`

<Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-direct-attribution-links#lien-dattribution">Apprenez à mettre en place des liens d'attribution directe</Anchor>.

</Accordion>

<div id="crossplatform-onelink" />

<Accordion title="Lien OneLink multiplateforme">

Les liens OneLink multiplateformes permettent la redirection et l'attribution lorsque les plateformes de publicité et de destination diffèrent. Ils sont utilisés lorsqu'il existe plusieurs choix de plates-formes. Par exemple, dans un flux CTV vers mobile, une publicité s'affiche sur une plateforme/un appareil Roku, mais la destination peut être une application Android/iOS. Un autre exemple est un flux web de bureau vers console, où la publicité s'affiche sur le web de bureau, mais où le jeu est disponible sur PC et sur plusieurs plateformes de console, comme PlayStation, Xbox et Steam.

Les liens OneLink multiplateformes ne prennent en charge que la méthode d'attribution par modélisation probabiliste (basée sur l'adresse IP). C'est pourquoi plusieurs installations par plusieurs utilisateurs peuvent être attribuées à la même impression. Le flux d'attribution est illustré dans le diagramme suivant.

<Image align="center" alt="CTV attribution flow - Cross-platform Onelink link attribution flow (1).png" src="https://files.readme.io/d1d92c740510435582dbfe6e736493a4e5f132d8987fde4c95593ea5e7de1662-19374961369873.png" />

Toutes les destinations/plateformes d'applications possibles sont configurées dans le modèle OneLink. À cette fin, les liens OneLink multiplateformes ne contiennent pas d'identifiant d'application spécifique ni d'informations spécifiques à la plateforme dans l'URL. Au lieu de cela, l'URL inclut l'ID du modèle où toutes les destinations/plateformes possibles de l'application sont configurées.

Exemple de lien OneLink multiplateforme : `https://impressions.onelink.me/ch/AG7A?pid=game_media_source&c=game_landing_page&af_ad=game_ad_name&af_adset=game_adset_name&af_xplatform=true`

<Anchor target="_blank" href="/marketers/fr/docs/set-up-cross-platform-links-for-multi-device-campaigns">Apprendre à configurer des liens OneLink multiplateformes</Anchor>

</Accordion>

<div id="srn" />

<Accordion title="SRN">

Avec des liens d'attribution directe et des liens OneLink multiplateformes, AppsFlyer attribue les installations via les données contenues dans l'URL. En revanche, les réseaux à déclaration automatique (SRN), parfois également appelés réseaux à attribution automatique (SAN), s'attribuent eux-mêmes l'identifiant de l'appareil lorsqu'ils sont informés d'une installation par AppsFlyer.

L'attribution aux SRN se fait par le biais d'une correspondance déterministe. Lorsqu'un annonceur intègre un SRN, l'attribution fonctionne comme illustré dans le diagramme suivant.

<Image align="center" alt="Flux d'attribution CTV - Flux d'attribution SRN (1).png" src="https://files.readme.io/ba0d84643aefd6a20e95c8aca9424affea8169c95ccc428ddf3d35bb8787a67c-19374961372945.png" />

Actuellement, l'attribution du SRN ne fonctionne que pour la publicité entre deux plates-formes. C'est-à-dire lorsque le point de contact (clic ou impression) se produit sur la même plateforme que l'installation. Par exemple, si l'installation d'un Roku CTV est vérifiée avec Roku Endemic Media (le SRN pour Roku) et qu'une impression est constatée sur un appareil Roku. Si l'impression s'est produite sur une autre plateforme, par exemple mobile, elle n'est pas prise en compte pour l'attribution.

À l'avenir, l'attribution SRN pourrait être disponible pour les publicités de toute plate-forme à toute plate-forme, ce qui permettrait une attribution multiplateforme plus complète.

</Accordion>

<div id="landing-page" />

<Accordion title="Page d'atterrissage multiplateforme">

Les pages d'atterrissage multiplateformes sont conçues pour prendre en charge les parcours utilisateurs et les flux marketing multiplateformes communs. Elles sont le plus souvent utilisées pour les applications de jeux. Les pages d'atterrissage exécutent le Smart Script d'AppsFlyer pour effectuer l'attribution du web à l'application. Cela signifie qu'ils attribuent les installations sur toutes les plateformes (telles que CTV, PC, consoles et plateformes mobiles) aux publicités affichées sur le web.

Le Smart Script d'une page d'atterrissage multiplateforme utilise le lien entrant (le lien de la publicité en ligne) pour faire deux choses qui garantissent que la source média d'origine et la publicité en ligne sont attribuées à l'installation :

* Créez un lien OneLink multiplateforme qui envoie une impression à AppsFlyer. Cela permet à AppsFlyer d'enregistrer une impression qui peut être utilisée ultérieurement pour attribuer les installations des utilisateurs. Les impressions sont envoyées lorsque la page d'atterrissage s'ouvre. Même si les utilisateurs quittent la page de renvoi sans cliquer sur aucun bouton, puis téléchargent et installent l'application par eux-mêmes, l'impression est toujours attribuée.
* Créez des liens d'attribution directe pour chaque application/plateforme. Lorsque les utilisateurs cliquent sur ces liens, ils sont dirigés vers la bonne plateforme/application. Et lorsqu'ils téléchargent et installent ensuite l'application, l'installation est attribuée au clic.

La page de renvoi prend en charge à la fois la modélisation probabiliste et les méthodes d'attribution déterministes (lorsqu'un identifiant est fourni dans le lien). Avec la modélisation probabiliste, il est possible que plusieurs installations par plusieurs utilisateurs puissent être attribuées à la même impression. Le flux d'attribution est illustré dans le diagramme suivant.

<Image align="center" alt="CTV attribution flow - Landing page attribution flow.png" src="https://files.readme.io/28e4d14d14532332027e5d429ac3f95c8d4d451d94125e399cfb9ad04727b278-19374961376529.png" />

Par exemple :

1. Vous disposez d'une application de jeu qui peut être téléchargée et utilisée sur des plateformes de bureau, mobiles, Epic ou Steam.
2. Vous faites de la publicité sur le web.
3. Un utilisateur voit la publicité sur le web, qu'il s'agisse de résultats de recherche payants ou de promotions sur les médias sociaux.
4. Les utilisateurs cliquent sur l'annonce et sont redirigés vers une page d'atterrissage, qui comporte des boutons de téléchargement distincts pour chaque plateforme : ordinateur de bureau, mobile, Epic et Steam.
5. La page d'atterrissage utilise le Smart Script d'AppsFlyer :
6. Capture les points de données essentiels du lien entrant (le lien qui a amené l'utilisateur du web à la page de destination), comme la requête ou les paramètres UTM, ou les valeurs par défaut, qui identifient la source du média, la campagne, l'annonce, et plus encore.
7. Utilise les points de données ci-dessus pour générer une impression et l'envoyer à AppsFlyer.
8. Génère des liens sortants pour chacun des boutons de téléchargement de la plateforme.
9. L'utilisateur clique sur l'un des boutons de téléchargement, est dirigé vers le magasin d'applications de la plateforme, télécharge et ouvre l'application.
10. L'installation/la première ouverture d'application est associée à l'impression et attribuée à la source média qui a diffusé l'annonce originale sur le web.

Informations supplémentaires

* <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">Voir un exemple de page d'atterrissage multiplateforme</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/cross-platform-landing-pages-with-smart-script">Apprenez à créer des pages d'atterrissage multiplateformes avec Smart Script</Anchor>

</Accordion>

<div id="note" />

<div id="data-availability" />

## Disponibilité des données

Les données des plateformes CTV, PC et consoles comprennent les données d'installation, ainsi que les données d'événements in-app qui donnent aux annonceurs des indications sur la valeur à vie (LTV) des utilisateurs organiques et non organiques, ben fonction de l'abonnement, des achats in-app et de la monétisation de la publicité. Les mesures LTV sont calculées entre la date d'attribution et l'instant présent.

Les données sont disponibles comme suit :

* Agréger les données via le tableau de bord de la vue d'ensemble.
* Données brutes via :
  * Data Locker
  * Exporter
  * API Pull

**Remarque** : Pour les plateformes dotées des systèmes d'exploitation Android et iOS, la disponibilité des rapports sur les <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">données</Anchor> <Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview">agrégées</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">brutes</Anchor> est la même que pour les applications mobiles.

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Fenêtre de réattribution | Pour les plateformes CTV, PC et console, la fenêtre de réattribution est basée sur une période d'inactivité définie (90 jours par défaut). |
| Événements postérieurs à la réinstallation | Attribué à la première installation <Anchor target="_blank" href="/marketers/fr/docs/measure-reinstalls#attributed-to-the-first-install">En savoir plus</Anchor> |
| Retargeting | <ul><li>Réattribution Prise en charge de l'interopérabilité entre plateformes et mobiles. Pas pour les autres plateformes.</li><li>RÉENGAGEMENT Non pris en charge</li></ul> |
| Méthode d'attribution | <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#méthodes-dattribution">Voir les méthodes d'attribution des plates-formes CTV, PC et consoles</Anchor> |
| Devise | USD ou tel que défini dans les paramètres de l'application AppsFlyer |
| Fuseau horaire | UTC |
| Données de coûts | En ce qui concerne les applications sur ces plateformes, les données de coûts doivent être envoyées via <Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">l'Ingestion des dépenses publicitaires</Anchor> en utilisant la méthode de téléchargement de fichiers par e-mail. |

</Accordion>

<div data-zendesk-anchors="about-ctv-attribution=la-solution-multiplateforme-appsflyer 01H7ZRK7PCNZG54ZQ0804HMR38=la-solution-multiplateforme-appsflyer list-of-supported-ctv-and-gaming-device-types=plateformes-prises-en-charge 01H7ZRK7PCP1KWRX1A5K81F4KR=plateformes-prises-en-charge crossplatform-attribution=attribution-multiplateforme 01H8EHHJNBA8NKMX2C8RSV7P31=attribution-multiplateforme 01H8EQ4KS75Q62Z7WVNSTDXBZX=direct-attribution-link 01H8EQ4KS7C6HADNKQZYNTTFMF=crossplatform-onelink 01H8EQ4KS7NVYAD6MQ6MM26AVW=srn data-availability=disponibilit%C3%A9-des-donn%C3%A9es h_01H9G52NKMQG9QD9S3N537BM7N=disponibilit%C3%A9-des-donn%C3%A9es 01H7ZRK7PCJ6BRQZ2AKQTV5Q5E=traits-and-limitations" />
