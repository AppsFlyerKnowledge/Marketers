---
title: Attribution du référent de préchargement AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2022-03-02T09:54:10Z'
  edited_at: '2023-11-15T13:04:33Z'
  id: 4543811207313
  locale: fr
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/fr/articles/4543811207313
---
> **En bref :** AppsFlyer utilise le référent de préchargement pour attribuer les installations aux campagnes de préchargement, où les marketeurs signent un contrat avec les fabricants d'équipements d'origine (OEM), les opérateurs mobile et les partenaires de découverte d'apps pour précharger leur app au moment de la construction de l'appareil, ou lorsque l'utilisateur l'allume pour la première fois.

<div id="overview" />

## Attribution du référent de préchargement AppsFlyer

Dans les campagnes de préchargement, les fabricants d'appareils d'origine (OEM), les opérateurs mobile et les partenaires de découverte d'applications préchargent les applications dans les appareils avant que l'utilisateur n'y ait accès. Cette opération peut être effectuée par l'OEM en usine ou par les fournisseurs lorsque l'appareil est activé pour la première fois.

Les campagnes de préchargement permettent aux annonceurs d'atteindre un plus large public sans avoir à lancer de campagnes en ligne.

L'attribution du référent de préchargement (l'une des 3 <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#preload-campaigns">méthodes d'attribution de préchargement</Anchor>) permet aux marketeurs de mesurer avec précision les performances des campagnes de préchargement tout en respectant la confidentialité des utilisateurs. Cette méthode offre aux marketeurs des résultats d'attribution déterministes, et elle garantit le respect de la vie privée de l'utilisateur puisque l'attribution est effectuée en associant le référent à un référent généré indépendamment de l'ID de l'appareil et de l'utilisateur.

Cette solution fournit :

* Une prise en charge transparente des mises à jour et re-téléchargements de l'app.
* Une visibilité et un suivi des mesures entre le moment de la première activation de l'appareil et celui du premier lancement de l'app. Vous avez ainsi la possibilité de savoir combien d'appareils ayant l'app préchargée ont été activés pour un partenaire en particulier, puis de savoir quand l'application est lancée pour la première fois.

<div id="preload-referrer-options" />

### Options du référent de préchargement

Les référents peuvent être utilisés pour attribuer les installations via préchargement ou via clic de téléchargement. Cf le tableau suivant pour obtenir plus d'infos.

AppsFlyer donne la priorité à l'attribution de préchargement. Cela signifie que si un utilisateur participe à d'autres campagnes avant d'ouvrir l'app pour la première fois, la campagne de préchargement reste tout de même attribuée. Les autres engagements seront considérés comme des installations assistées. **Remarque** : Vous pouvez activer la priorité égale pour les engagements de pré chargement. Cela donne aux clics déterministes la même priorité d'attribution qu'aux engagements de préchargement sur toute la fenêtre rétroactive de préchargement, de sorte que l'attribution de la campagne de préchargement peut être remplacée par un autre engagement publicitaire.

| Option du référent | Description | L'UA installe un type de matching pour les données brutes |
| --- | --- | --- |
| Préchargement | <ul><li>L'application est préchargée au moment de l'assemblage de l'appareil, ou lors de sa première activation. Il est aussi possible d'inviter l'utilisateur à télécharger l'app lors de la première activation de l'appareil.</li><li>Un événement de préchargement, équivalent à un clic, est transmis à AppsFlyer lorsque l'appareil est allumé pour la première fois.</li><li>L'attribution a lieu lorsque l'utilisateur ouvre l'app pour la première fois.</li><li>L'événement de pré-chargement a la priorité d'attribution la plus haute (sauf si la priorité d'attribution égale est activée).</li></ul> | `preload_rfr` |
| Clic de téléchargement | <ul><li>L'installation de l'application a lieu plus tard durant la vie de l'appareil, via des notifications push, des stores partenaires, etc.</li><li>Lorsque l'utilisateur réagit à une publicité ou à un message push, l'app est automatiquement téléchargée et installée sur l'appareil, sans qu'il y ait besoin de rediriger l'utilisateur vers un app store.</li><li>L'attribution se fait selon les règles AppsFlyer qui déterminent le dernier clic.</li></ul> | `af_referrer` |

<div id="view-preload-attribution-data" />

### Disponibilité des données

Les données de performance des campagnes d'engagement pour télécharger par préchargement/clic sont disponibles comme indiqué ci-dessous :

* **Tableau de bord général :** les engagements sont comptabilisés comme des clics dans les rapports et tableaux de bord agrégés. Ils sont agrégés au niveau du partenaire de préchargement (source média) et de la campagne.
* **Données brutes :** les engagements sont disponibles dans les rapports de clics disponibles uniquement via Data Locker. Ils se trouvent dans le champ URL d'origine et peuvent être définis dans le paramètre af\_engagement\_type soit comme *preload*, soit comme *click\_to\_download*. Pour les installations, cf le tableau de la section précédente pour voir comment le type de matching est indiqué dans les données brutes.

<div id="traits-and-limitations" />

<div id="set-up-samsung-preload-referrer-attribution" />

<div id="samsung-preload-referrer" />

<div id="set-up-preload-referrer-attribution" />

### Configurer l'attribution du référent de préchargement

**Conditions préalables :**

* Avoir intégré le SDK <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-android-sdk-release-notes">Android 6.10.1 et +</Anchor> AppsFlyer.
* Avoir un contrat avec un partenaire de préchargement AppsFlyer.

**Pour configurer l'attribution des référents de préchargement**:

1. Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**.
2. Sélectionnez le partenaire de préchargement.
3. Dans l'onglet **Integration**, activez **Attribution de préchargement**.  

   [<Image alt="" src="https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png" width="538px" />](https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png)
4. Définissez la durée de la **fenêtre rétrospective de préchargement.** Durée : 1-180 jours.
5. Activez l'option de **priorité égale pour les préchargements.** Cela donne aux clics déterministes la même priorité d'attribution que l'attribution de préchargement, ce qui signifie que si un clic déterministe est enregistré entre l'engagement du référent de préchargement et l'installation, le clic est attribué selon le principe du dernier touch, au lieu du référent de préchargement.
6. Cliquez sur **Enregistrer l'intégration**.
7. Faites savoir au partenaire de préchargement que vous êtes en capacité d'attribuer ses campagnes.

<div id="partners-supporting-preload-referrer-campaigns" />

### Partenaires prenant en charge les campagnes de référent par préchargement

<table><thead><tr><th rowspan="2">Partenaire</th><th rowspan="2">PID</th><th colspan="2">Options des campagnes de référent par préchargement <a href="./set-up-appsflyer-preload-referrer-attribution#options-du-référent-de-préchargement"><span>En savoir plus</span></a> </th></tr><tr><th>Préchargement</th><th>Clic de téléchargement</th></tr></thead><tbody><tr><td>Digital Turbine dans l'appareil</td><td>digitalturbine_int</td><td><span><span>✓</span></span></td><td><p>Prochainement</p></td></tr><tr><td>Aura par Unity</td><td>aura_int</td><td><span><span>✓</span></span></td><td><p>Prochainement</p></td></tr><tr><td><span>Appnext</span></td><td><span>appnext_int</span></td><td><span><span>✓</span></span></td><td><p>Prochainement</p></td></tr><tr><td> <span>Glance</span><span><br/></span> </td><td><span>glance_int</span></td><td><span><span>✓</span></span></td><td><p><span><span>✓</span></span></p></td></tr></tbody></table>

<div data-zendesk-anchors="appsflyer-preload-referrer-attribution=attribution-du-r%C3%A9f%C3%A9rent-de-pr%C3%A9chargement-appsflyer h_01HEKAF7K41PH189PSCKBRF070=attribution-du-r%C3%A9f%C3%A9rent-de-pr%C3%A9chargement-appsflyer preload-referrer-options=options-du-r%C3%A9f%C3%A9rent-de-pr%C3%A9chargement h_01HEKAF7K4H3HNAMEYM6C58Y29=options-du-r%C3%A9f%C3%A9rent-de-pr%C3%A9chargement campaign-performance-data-availability=disponibilit%C3%A9-des-donn%C3%A9es h_01HEKAF7K4GJDDPHCFTTC75YBS=disponibilit%C3%A9-des-donn%C3%A9es run-preload-referrer-campaigns=configurer-lattribution-du-r%C3%A9f%C3%A9rent-de-pr%C3%A9chargement h_01HEKAF7K41RBRVXC6GF6PCN3Y=configurer-lattribution-du-r%C3%A9f%C3%A9rent-de-pr%C3%A9chargement partners-supporting-preload-referrer-campaigns=partenaires-prenant-en-charge-les-campagnes-de-r%C3%A9f%C3%A9rent-par-pr%C3%A9chargement h_01HEKAF7K5CWX2P9TY8M0MTQAM=partenaires-prenant-en-charge-les-campagnes-de-r%C3%A9f%C3%A9rent-par-pr%C3%A9chargement" />
