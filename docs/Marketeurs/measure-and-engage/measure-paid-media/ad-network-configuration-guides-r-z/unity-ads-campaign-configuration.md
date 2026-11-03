---
title: Configuration de la campagne Unity Ads
metadata:
  keywords:
    - Unity Ads
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-06T10:05:52Z'
  edited_at: '2023-11-06T08:37:39Z'
  id: 208005086
  locale: fr
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/fr/articles/208005086
---
> **En bref :** le réseau publicitaire vidéo pour iOS et Android Unity Ads est un partenaire intégré du réseau publicitaire AppsFlyer. Outre l'attribution mobile basée sur les clics, Unity Ads offre la possibilité d'enregistrer via AppsFlyer les coûts, les revenus publicitaires et l'attribution post-vue.

Pour configurer vos campagnes avec Unity Ads, suivez les étapes ci-dessous.

## Configurer Unity Ads

La configuration se fait depuis la page **Intégrations actives**, mais pour trouver le partenaire vous devez d'abord vous rendre dans le <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations">marketplace</Anchor>.

> 📘 **Remarque**
>
> Avant de configurer une attribution, vous devez <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">contacter le partenaire</Anchor> et ouvrir un compte chez lui.

**Pour activer l'intégration :**

1. Ouvrez le marketplace : dans le menu situé en haut de n'importe quelle page AppsFlyer, cliquez sur **Marketplace**.
2. Trouvez le partenaire voulu et sélectionnez-le.
3. Cliquez sur **Configurer l'intégration**. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l'**onglet Intégration**, enclenchez **Activer le partenaire**.  
   **Remarque :** La case doit rester cochée (<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">option activée</Anchor>) tant que vous travaillez avec le partenaire.
5. Terminez la configuration en suivant les onglets requis, cf description ci-dessous.

La fenêtre de configuration Unity Ads comprend 5 onglets : Intégration, Lien d'attribution, Coût, Revenu publicitaire et Autorisations. Cliquez sur les éléments ci-dessous pour en savoir plus sur la configuration des onglets.

Pour obtenir une description détaillée de l'en-tête de fenêtre de configuration du partenaire, cliquez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">ici</Anchor>.

> 👍
>
> * <span id="h_01HAPVZ5109NKD8GHD36EDN810"></span>L'étape <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#d">Paramètres généraux</Anchor> de l'onglet Intégration est **obligatoire** pour tous les partenaires.
> * Toutes les autres étapes sont soit descriptives, soit **optionnelles**

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

### Activer les partenaires

Lors de votre première visite, vous devrez cocher l'option **Activer le partenaire** pour configurer l'intégration. L'option doit rester activée tant que vous travaillez avec le partenaire.  
Pour plus de détails sur l'activation des partenaires, cliquez <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">ici</Anchor>.

### Paramètres généraux

**Envoi de l'ID de l'appareil (ID d'annonceur) à Unity**

En haut de l'onglet Intégration, une note indique que Unity Ads doit transmettre l'identifiant de l'appareil pour chaque installation—cela se fait automatiquement, vous n'avez rien à faire de votre côté.

[![Unity_msc_new_2.png](https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png)](https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png)

**ID de jeu Unity Ads**

Unity Ads nécessite une connexion avec AppsFlyer via un identifiant de jeu unique. Si vous ne connaissez pas le vôtre, vous pouvez l'obtenir directement dans Unity Ads ou le récupérer (après avoir téléchargé le jeu) dans **Apps** > **Campagnes**, comme le montre la capture d'écran ci-dessous.

[![](https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png)](https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png)

La plateforme Unity Ads associe une application à un ID de jeu unique Unity Ads, par niveau de compte (les annonceurs et les agences auront différents ID de jeu pour la même application). Différents comptes sur la plateforme Unity Ads ne peuvent pas utiliser la même application avec des identifiants de jeu différents.

**Activer l'attribution post vue**

Activez cette option pour attribuer les installations post vue à partir de Unity Ads. Le curseur rétrospectif post-vue est disponible dans l'onglet du lien d'attribution (décrit ci-dessous).

![Unity_ads_msc_new_3.png](https://files.readme.io/fab459ace7e8f1354d3bbfbca8ddefcd11376b7426a8e361abfab1b42b623880-360001875405.png)

### Postbacks par défaut

![Screen_Shot_2022-07-28_at_13.07.25.png](https://files.readme.io/a571ddc49e490373b34144e34626a18c6c18908cec3345cd7ac70c49aa855c05-7975491293329.png)

Pour envoyer des messages automatiques à Unity Ads lors d'installations et de réengagements d'utilisateurs. Utilisez cette section pour définir la source des utilisateurs qui autorisent l'envoi de ces postbacks :

* **Ce partenaire uniquement** : pour les événements provenant exclusivement d'utilisateurs attribués aux publicités Unity Ads.
* **Toutes les sources média, y compris organiques** :pour que l'ensemble de votre base d'utilisateurs soit prise en compte dans Unity Ads.

> 📘 **Note**
>
> En tant que réseau « toute installation », Unity Ads préfère recevoir des postbacks pour toutes les nouvelles installations de votre application, quelle qu'en soit la source, et recommande de sélectionner **Toutes les sources média, y compris organiques** pour envoyer tous les postbacks d'installation à Unity Ads.

### Paramètres des événements in-app

Mappage des événements AppsFlyer avec le partenaire via postback. Si l'envoi de postback est activé, il inclut les événements in-app rejetés (événements bloqués par Protect360 ou événements jugés non conformes par les règles de validation de cible).

[![](https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png)](https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png)

#### Pour configurer les postbacks d'événement in-app :

1. Saisissez le **game\_id**. Assurez-vous que le game\_id est correct, et qu'il est le même que celui utilisé pour l'attribution de l'installation.
2. Activez **Postbacks d'événement in-app.**
3. Si nécessaire, configurez la **fenêtre de postback des événements in-app** (en savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#fenêtre-des-postbacks-dévénements-in-app"> la configuration de la fenêtre de postback des événement in-app</Anchor>).
4. Cliquez sur **Ajouter un événement** pour ajouter à la liste un SDK ou un événement de serveur à serveur à la liste.
5. Remplissez les paramètres suivants :

| Nom du paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis les événements de serveur à serveur.<br />**Astuce** : vous ne voyez pas s'afficher un événement précis ?<ul><li>Assurez-vous d'activer l'évènement sur un appareil avec une installation non-organique puis revérifiez.</li><li>Saisissez-le dans **Événement AppsFlyer** puis cliquez sur **Créer un événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| **mappé à l’événement partenaire** | Le nom ou l'identifiant unique de chaque événement, tel que défini du côté du partenaire. Les différentes configurations du mapping sont :<ul><li>**Champ de texte :** obtenez l'ID d'événement correspondant auprès du partenaire.</li><li>**Liste déroulante :** sélectionnez l’événement AppsFlyer prédéfini approprié.</li><li>**Tel quel** : envoyez les événements à l'état brut, sans mappage du nom.</li></ul> |
| **pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<ul><li>**Ce partenaire uniquement** : envoie des postbacks exclusivement lorsque cet événement est attribué à ce partenaire.</li><li>**Toutes les sources média, y compris les sources organiques** : envoyez des postbacks pour les événements attribués à n'importe quel partenaire, ainsi que pour les événements organiques. Unity Ads recommande d'utiliser cette option.</li></ul> |
| **Y compris** | <ul><li>**Aucune donnée (par défaut)** : envoie uniquement l'événement, sans sa valeur.</li><li>**Valeurs et revenus** : envoie tous les paramètres de l'événement, **y compris** la valeur des revenus (si elle existe dans l'événement). Unity Ads recommande d'utiliser cette option.</li><li>**Avec valeurs et sans revenu** : envoie tous les paramètres **à l'exception** de la valeur de revenu.</li></ul> |

> 🚧 **Important !**
>
> Sélectionnez l'événement SDK/serveur-à-serveur correct et l'identifiant d'événement partenaire correspondant. Ne dupliquez pas les événements (ne transmettez pas les mêmes événements sous différents noms d'événements SDK/serveur-à-serveur).

> 📘 **Remarque**
>
> Vous pouvez envoyer <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">des postbacks de revenus publicitaires</Anchor> à Unity ads pour qu'il optimise les campagnes avec les données des revenus publicitaires :
>
> * **Nom de l'événement :** af\_ad\_revenue
> * **Mappé à :** adRevenue

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Générez et enregistrez les liens d’attribution et envoyez-les au partenaire pour attribuer des campagnes spécifiques, des ad sets ou des publicités uniques, à la fois pour les campagnes UA et les campagnes de retargeting. Vous pouvez utiliser un lien de plateforme unique ou un <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">En savoir plus sur la structure et les paramètres des liens d’attribution</Anchor>.  

**Pour générer un lien d’attribution,** suivez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">ces instructions</Anchor>.

**Remarque :**

* Lorsque le public cible d'une application Android comprend des enfants, Unity envoie des ID d'annonceur réduits à zéro.
* En savoir plus sur la façon dont Unity Ads définit les clics et les vues.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

Le coût par clic n'est pas pris en charge. AppsFlyer obtient les infos sur les coûts via l'API. Consultez le <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts des réseaux publicitaires</Anchor> pour obtenir tous les détails sur les dimensions, mesures et fonctionnalités prises en charge .

**Remarque** :

* Les données de coût nécessitent un abonnement ROI360.
* Les données de coût Unity Ads ne peuvent être reçues que pour les téléchargements provenant de Google Play ou de l'App Store d'Apple. Pour Android, les données de coût pour les app stores Android tiers ne sont pas prises en charge.
* Le coût de l'agence n'est pas pris en charge dans le cadre des coûts par clic ou API. Les annonceurs peuvent envoyer les données de coûts aux agences en passant par <Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">Ingestion des dépenses publicitaires.</Anchor>

**Pour activer l'API de coûts :**

* Veuillez suivre ces <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">étapes pour l'intégration</Anchor>. **Remarque** : Pour les intégrations de coûts Unity, toutes les apps avec la même clé API doivent contenir le même ID Org. Si ce n'est pas le cas, l'extraction des données de coûts sera impactée.

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Affichez le statut de votre API de coûts</Anchor> et la dernière fois qu'AppsFlyer a réussi à extraire des données de coûts correspondantes, soit dans le tableau de bord du statut d'intégration des coûts (et des revenus publicitaires), soit dans le tableau de bord du réseau publicitaire individuel.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Cette section vous concerne si vous agissez en tant qu'éditeur, affichant les publicités du partenaire à l'intention de vos utilisateurs. En tant que tel, vous souhaiterez certainement mesurer l'engagement de vos utilisateurs provenant de différentes sources, afin d'identifier celles qui offrent le maximum de rentabilité.

**Pour activer l'API de revenus publicitaires** :

* Suivez <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">ces instructions d'intégration</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Dans cet onglet, vous pouvez sélectionner les autorisations permettant à Unity Ads d’effectuer certaines actions. Notez que même si l'attribution est désactivée pour Unity Ads, l'onglet des autorisations est actif et vous pouvez accorder des autorisations à Unity Ads.  
En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">les autorisations que vous pouvez accorder.</Anchor>

</Accordion>

</Accordion>

<div data-zendesk-anchors="setting-up-unity-ads=configurer-unity-ads h_01HAPVZ510GTJRY1NXE0T3SMR6=configurer-unity-ads h_01HAPVZ5105TY4Q4V32GPYAEER=remarque h_01HAPVZ510KPB0HQS9X6R4BCWT=integration-tab activate-partners=activer-les-partenaires h_01HAPVZ510BGQ4KZ3S6ZP0QRE8=activer-les-partenaires general-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux h_01HAPVZ510EZ3HKJQVPMKHV5FH=param%C3%A8tres-g%C3%A9n%C3%A9raux default-postbacks=postbacks-par-d%C3%A9faut h_01HAPVZ511MRQXKPC78HR61X9P=postbacks-par-d%C3%A9faut h_01HAPVZ511CCXS93Y714STGQ67=note inapp-events-settings=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app h_01HAPVZ511CJ6JP49HYG9T6RPF=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app to-configure-inapp-event-postbacks=pour-configurer-les-postbacks-d%C3%A9v%C3%A9nement-in-app h_01HAPVZ511RMEVNASSTJNXKCJG=pour-configurer-les-postbacks-d%C3%A9v%C3%A9nement-in-app h_01HAPVZ511AV30DEKMZ0YB5ZBD=important- h_01HAPVZ511PC45Q5FEXQMZ4MFC=remarque-1 h_01HAPVZ5110QVYGGCGQDHRJEQM=attribution-link-tab h_01HAPVZ511DSKFAKKNWTKV9522=cost-tab h_01HAPVZ5111WPRRMPF6GZJTRJS=ad-revenue-tab h_01HAPVZ511RBNY3HHSHJHJDPWG=permissions-tab" />
