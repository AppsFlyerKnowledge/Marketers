---
title: Configuration de la campagne The Trade Desk
metadata:
  keywords:
    - Advertisers
    - The Trade Desk
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-05-13T07:34:13Z'
  edited_at: '2023-12-07T17:40:39Z'
  id: 360000894849
  locale: fr
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/fr/articles/360000894849
---
> **En bref :** The Trade Desk, partenaire intégré du réseau publicitaire AppsFlyer, utilise sa solution de publicité mobile améliorée pour mettre en place des campagnes stratégiques, évolutives et intelligentes afin de répondre aux besoins des utilisateurs sur tous les appareils. The Trade Desk propose une attribution mobile basée sur les clics, une attribution mobile basée sur les vues et un retargeting basé sur les clics, qui peuvent tous être enregistrés via AppsFlyer.

## Configuration de The Trade Desk (TTD)

Suivez ces étapes pour activer la mesure des campagnes AppsFlyer.

<div id="step-1-define-conversion-events-in-ttd" />

<Accordion title="Étape 1 : Définir les événements de conversion dans TTD">

1. Dans le menu de gauche de votre page d'annonceur TTD, cliquez sur **DATA**.
2. Dans le menu supérieur, cliquez sur **Ajouter données d'app**.
3. Saisissez les champs suivants sur la page **Créer données d'app** :
   * **Nom d'app :** entrez le nom de l'application.
   * **Système d'exploitation :** sélectionnez **Android** ou **iOS**.   
     **Remarque :** TTD prend en charge la CTV sous les options Android et iOS.
   * **Suivi du fournisseur :** sélectionnez **AppsFlyer**.
   * **Événements :** cliquez sur **AJOUTER EVENEMENT** pour ajouter des événements de conversion et remplir les champs :
     * **NOM DE L'ÉVÉNEMENT**: entrez le nom de l'événement.  
       **Remarque :** assurez-vous que le nom est écrit exactement comme dans AppsFlyer, y compris les majuscules, les espaces et les symboles.
     * [Facultatif] **DESCRIPTION**: ajoutez une description.
     * [Facultatif] **UTILISATION DES DONNÉES COLLECTIVES**: sélectionnez **Attribution**. Cette option comprend à la fois l'attribution et le retargeting.
     * Pour ajouter d'autres événements, cliquez sur **AJOUTER EVENEMENT** et répétez la procédure.
   * **Source de crédit de conversion**: sélectionnez la source à laquelle attribuer les conversions, soit AppsFlyer, soit The Trade Desk.   
     **Remarque :**
     * Pour mesurer les achats cross-device et TTD, sélectionnez **The Trade Desk**.   
       Pour une vision globale des données, pas seulement pour TTD, sélectionnez **AppsFlyer**.
     * Ne modifiez jamais cette sélection au cours d'une campagne.
     * Veillez à sélectionner la bonne source avant de cliquer sur **CREER DONNEES D'APP**. Vous ne pouvez pas modifier la source de crédit de conversion au cours d'une campagne.
4. Cliquez sur **CREER DONNEES D'APP**.

</Accordion>

<div id="step-2-define-conversion-events-in-appsflyer" />

<Accordion title="Étape 2 : Définir les événements de conversion dans AppsFlyer">

Pour qu'AppsFlyer définisse les événements de conversion et vous permette d'envoyer des postbacks d'événements à TTD, vous devez d'abord [intégrer TTD à AppsFlyer](/docs/the-trade-desk-campaign-configuration#intégration-avec-appsflyer) et mettre en place les configurations suivantes :

* Paramètres d'intégration (y compris la configuration des postbacks d'événements)
* Lien d'attribution
* Autorisations

</Accordion>

<div id="step-3-map-defined-conversion-events-from-appsflyer" />

<Accordion title="Étape 3 : Cartographier les événements de conversion définis dans AppsFlyer">

1. Dans le menu de gauche de TTD, cliquez sur **CAMPAGNES**.
2. Faites défiler la page jusqu'à **Campagnes** et sélectionnez une campagne dans la liste.
3. Cliquez sur **Modifier les rapports et l'attribution**.
4. Cliquez sur **AJOUTER SOURCE DE DONNÉES DE CONVERSION**.
5. Sous **SOURCE DE DONNÉES DE CONVERSION**, sélectionnez ou tapez **AppsFlyer**. Les événements AppsFlyer sont désormais associés aux événements TTD.
6. **CONCEPT CROSS-DEVICE** :
   * Si vous avez choisi à [l'étape 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) (Source de crédit de conversion) d'attribuer les conversions via TTD, sélectionnez ici **Foyer** pour voir les conversions dans tous les canaux disponibles (tels que mobile in-app et CTV).
   * Si vous avez choisi AppsFlyer à [l'étape 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd), sélectionnez ici **Aucun**.
7. Cliquez sur **ENREGISTRER**.

</Accordion>

<div id="step-4-add-click-and-impression-trackers-to-campaign-creatives" />

<Accordion title="Étape 4 : Ajouter des traqueurs de clics et d'impressions aux campagnes créatives">

Dans cette étape, vous ajouterez les trackers de clics et d'impressions qui ont été créés dans AppsFlyer à chacune des créations dans TTD.

1. Sous **CAMPAGNES** dans le menu de gauche de TTD, cliquez sur **CRÉATIONS** dans l'onglet supérieur.
2. Sélectionnez une création dans la liste des créations associées à la campagne en cours.
3. Faites défiler les pages jusqu'à **Suivi**.
4. Copiez les [liens d'attribution](/docs/the-trade-desk-campaign-configuration#attribution-link-tab) (post-clic et post-vue) depuis AppsFlyer, et collez-les dans chacun des champs **URL de suivi des impressions 1x1 pixel** .
5. Cliquez sur **ENREGISTRER LES MODIFICATIONS**.
6. Répétez cette étape pour chacune des créations associées à la campagne.

</Accordion>

> 📘 **Note**
>
> Si vous avez choisi d'attribuer les conversions via TTD (dans [Étape 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd)), vous pouvez modifier les fenêtres d'attribution :
>
> 1. Dans le menu des icônes situé à droite de chaque page du site TTD, cliquez sur la roue dentée pour ouvrir le site **Préférences de l'annonceur**.
> 2. Faites défiler l'écran jusqu'à **Fenêtre d'attribution** et cliquez sur le bouton de modification à droite.
> 3. Sur la page **Gérer les fenêtres d'attribution**, modifiez les fenêtres d'attribution :
>    * **Fenêtres de déduplication :** le nombre de conversions que vous pouvez voir dans une certaine période de temps.
>    * **Fenêtres d'attribution de la campagne :** période allant de l'exposition à la publicité jusqu'à la conversion.
> 4. Cliquez sur **ENREGISTRER**.

## Intégration avec AppsFlyer

La configuration se fait depuis la page **Intégrations actives**, mais vous devez d'abord vous rendre dans le <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations">marketplace</Anchor> pour trouver le partenaire .

**Pour activer l'intégration :**

1. Ouvrez le marketplace : dans le menu situé en haut de n'importe quelle page AppsFlyer, cliquez sur **Marketplace**.
2. Trouvez le partenaire voulu et sélectionnez-le.
3. Cliquez sur **Configurer l'intégration**. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l'**onglet Intégration**, cochez **Activer le partenaire**.  
   **Remarque :** la case doit rester cochée (<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">option activée</Anchor>) tant que vous travaillez avec le partenaire.
5. Terminez la configuration en suivant les onglets requis, cf description ci-dessous.

La fenêtre de configuration de TTD comprend trois onglets actifs : Intégration, Lien d'attribution et Permissions. Cliquez sur les éléments ci-dessous pour en savoir plus sur la configuration des onglets.

Pour obtenir une description détaillée de l'en-tête de la fenêtre de configuration du partenaire, cliquez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">ici</Anchor>.

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

#### Activation du partenaire

Lors de votre première visite, vous devrez cocher l'option **Activer le partenaire** pour configurer l'intégration. L'option doit rester activée tant que vous travaillez avec TTD.  
Pour plus de détails sur l'activation des partenaires, cliquez <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">ici</Anchor>.

#### Protection de la vie privée avancée

Pour les applications iOS, le bouton <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">Activer la confidentialité avancée</Anchor> apparaît. Lorsqu'elle est activée, cette option limite le partage des identifiants des utilisateurs avec le partenaire. Notez que lorsque le bouton <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">Confidentialité avancée agrégée</Anchor> est activé dans les paramètres de l'application, **Activer la confidentialité avancée** est enclenché et verrouillé par défaut. 

#### Paramètres généraux

**ID de l'annonceur et ID du tracker**

The Trade Desk se connecte à AppsFlyer via un ID de réseau unique. Si vous n'avez pas encore le Tracker\_ID et l'ID de l'annonceur, vous devez les récupérer auprès de The Trade Desk pour poursuivre l'intégration.

![TTD_General_Settings_.png](https://files.readme.io/f7f2b66556f2713ff56a3bd2fcfe6fe8fe8d346a9b322904f93670ee55cf94c3-50612291000849.png)

**Activer l'attribution post-vue**

Enclenchez **Activer l'attribution post-vue** pour attribuer les installations post-vue via The Trade Desk. Le curseur de fenêtre d'attribution post-vue est disponible dans l'onglet du lien d'attribution (décrit ci-dessous).

#### Postbacks par défaut

![default_postbacks_en-us.png](https://files.readme.io/b291c9fd4ac858723f3071bf271a041403639d49bfb1984030fc7c7306c40c16-50612291002385.png)

Pour envoyer des messages automatiques à The Trade Desk lors d'installations et de réengagements d'utilisateurs. Utilisez cette section pour définir la source des utilisateurs qui autorisent l'envoi de ces postbacks :

* **Ce partenaire uniquement** : pour les événements provenant exclusivement d'utilisateurs attribués à The Trade Desk.
* **Toutes les sources média, y compris organiques** : pour que l'ensemble de votre base d'utilisateurs soit prise en compte dans The Trade Desk.

> 📘 **Note**
>
> En tant que réseau « toute installation », The Trade Desk préfère recevoir des postbacks pour toutes les nouvelles installations de votre application, quelle qu'en soit la source, et recommande de sélectionner **Toutes les sources média, y compris organiques**.

#### Paramètres des événements in-app

Mappage des événements AppsFlyer avec TTD via postback. Si l'envoi de postback est activé, il inclut les événements in-app rejetés (événements bloqués par Protect360 ou événements jugés non conformes par les règles de validation de cible).

![the_trade_desk_in_app_event_settings_en-us.png](https://files.readme.io/a72231e1f7d21eeb6ffd0b8e0ce056872ec7ef4670470a86e93eb7094ff9cea8-50612307447185.png)

**Pour configurer les postbacks d'événement in-app :**

1. Saisissez **l'ID d'annonceur** et **l'ID de tracker.**
2. Activez **Postbacks d'événements in-app**.
3. Si nécessaire, configurez la **fenêtre de postback des événements in-app** (en savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#fenêtre-des-postbacks-dévénements-in-app"> la configuration de la fenêtre de postback des événement in-app</Anchor>).
4. Si cela vous est proposé, vous devez choisir d'envoyer les événements automatiquement ou manuellement. En savoir plus sur l'envoi de <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">tous les événements tels quels.</Anchor>
5. Cliquez sur **Ajouter un événement** pour ajouter à la liste un SDK ou un événement de serveur à serveur.
6. Renseignez les paramètres demandés.
7. [Facultatif] Cliquez sur<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />pour définir les conditions d'envoi de certains événements in-app à TTD.  
   En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#postbacks-conditionnels-dévénements-in-app">les postbacks conditionnels d'événements in-app</Anchor>.

| Nom du paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis les événements de serveur à serveur.<br />**Astuce** : vous ne voyez pas s'afficher un événement précis ?<ul><li>Assurez-vous d'activer l'évènement sur un appareil avec une installation non-organique et revérifiez.</li><li>Saisissez-le dans **Événement AppsFlyer** puis cliquez sur **Créer un événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| **pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<ul><li>**Ce partenaire uniquement** : envoie des postbacks exclusivement lorsque cet événement est attribué à ce partenaire.</li><li>**Toutes les sources média, organiques comprises** : envoie des postbacks pour les événements attribués à n'importe quel partenaire ou et pour les événements organiques.</li></ul> |
| **Y compris** | <ul><li>**Aucune donnée (par défaut)** : envoie uniquement l'événement, sans sa valeur.</li><li>**Valeurs et revenus** : envoie tous les paramètres de l’événement, **y compris** la valeur de revenu (si présente dans l’événement).</li><li>**Avec valeurs et sans revenu** : envoie tous les paramètres **à l'exception** de la valeur de revenu.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Générez et enregistrez les liens d’attribution et envoyez-les à TTD pour attribuer des campagnes spécifiques, des ad sets ou des publicités uniques, à la fois pour les campagnes UA et les campagnes de retargeting. Vous pouvez utiliser un lien à plateforme unique ou <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">OneLink</Anchor>.

#### Paramètres du lien d'attribution

En ajoutant des paramètres au lien d'attribution vous pouvez effectuer des analyses beaucoup plus précises. Il est possible de modifier les paramètres déjà définis sur le lien d'attribution en les ajoutant, ainsi que leurs nouvelles valeurs, ici. Lors de l'enregistrement du lien d'attribution, tous les paramètres configurés dans cet onglet sont sauvegardés.

Sélectionnez les paramètres que vous souhaitez ajouter au lien d'attribution.

![ttd_attribution_link_parameters_en-us.png](https://files.readme.io/2658797286fd7d922c68a9c2f1705166672066d4179d72cf4fe0039ac3ede212-50612291012625.png)

#### Paramètres par défaut

| Nom | Description | Paramètre |
| --- | --- | --- |
| ID site | Utilisez le paramètre d'ID de sous-site pour ne pas risquer de dépasser le nombre d'ID de site autorisé. Si de nombreux éditeurs existent, nous conseillons de limiter le nombre d'ID de site utilisés et d'utiliser le paramètre ID de sous-site pour <Anchor target="_blank" href="/marketers/fr/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">éviter de dépasser les limites d'ID</Anchor> de site. | af\_siteid |
| Nom de la campagne | Ajoutez le nom de votre campagne pour comparer les différentes campagnes menées avec TTD. | C |
| Identifiant de la campagne | Ajoutez l'identifiant de votre campagne. | af\_c\_id |
| Identifiant de l'ensemble de publicités | Ajoutez votre ID d'adset pour comparer les performances de toutes vos publicités par adset. | af\_adset |
| Identifiant de publicité | Ajoutez votre identifiant publicitaire. | af\_ad\_id |

Vous pouvez ajouter d'autres paramètres pour le lien d'attribution. En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">la mise en place du lien d'attribution</Anchor> et sur <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">la structure et les paramètres du lien d'attribution.</Anchor>

#### Paramètres de mesure CTV

Vous pouvez mesurer le trafic CTV avec AppsFlyer en ajoutant les paramètres et valeurs suivants :

| Paramètre | valeur | Commentaires |
| --- | --- | --- |
| Rediriger | false |  |
| af\_xplatform\_vt\_lookback | 1h-72h | N'importe quelle valeur entre 1 et 72 heures peut être saisie |

#### Attribution post clic

![click-through_attribution_ttd_en-us.png](https://files.readme.io/9d8c4aed6aa5d8b3cba5b4e32a5245f4bd8b6d9cf50e8cc800dce66842487355-50612291014673.png)

Utilisez le curseur pour définir la durée maximale entre le clic et l'installation. Seules les installations (premiers lancements) qui ont lieu dans la fenêtre d'attribution seront attribuées.

Plage de la fenêtre d'attribution : 1-23 heures ou 1-30 jours.

Paramètre du lien d'attribution : af\_click\_lookback

En savoir plus sur la <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">fenêtre rétrospective de clic.</Anchor>

**Lien d'attribution post-clic :** contient tous les paramètres que vous avez inclus dans la configuration du lien d'attribution. Vous pouvez copier le lien et l'envoyer au partenaire pour qu'il soit activé lorsque vos prospects cliquent sur une publicité correspondante. 

#### Attribution post-vue

![view-through_attribution_ttd_en-us.png](https://files.readme.io/7435384719e46f0534149ef41612db6ee54c930bab8e8eadc1fd86ae84d5d777-50612307451921.png)

Utilisez le curseur pour définir le délai maximum entre l'impression et l'installation. Seules les installations (premiers lancements) qui ont lieu dans cette fenêtre d'attribution, suite à une impression de publicité, sont attribuées au partenaire, à condition qu'il n'y ait pas eu d'autre clic pertinent sur la publicité.

Fenêtre d'attribution : 1-24 heures.

Paramètre du lien d'attribution : af\_viewthrough\_lookback

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">l'attribution post-vue.</Anchor>

**Lien d'attribution post-vue :** contient tous les paramètres que vous avez inclus dans la configuration du lien d'attribution. Vous pouvez copier le lien et l'envoyer au partenaire pour qu'il soit activé lorsque vos clients cliquent sur la publicité correspondante.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

L'intégration des coûts n'est pas disponible pour The Trade Desk.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Les revenus publicitaires ne sont pas disponibles pour The Trade Desk.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Dans cet onglet, vous pouvez sélectionner les autorisations à accorder à The Trade Desk, qu'il agisse en tant que réseau publicitaire, agence ou même les deux. Notez que même si l'attribution est désactivée pour le partenaire, l'onglet des autorisations est actif et vous pouvez accorder le contrôle au partenaire.

![](https://files.readme.io/8d8c3d5eb38384d92e52afdc01b0631d8fe5c9590dd618386cbf6ce90fc978f3-50612307452817.png)

Utilisez ces boutons pour autoriser le réseau publicitaire à gérer sa propre configuration pour votre application :

#### **Autorisations pour le réseau publicitaire**

* **Autoriser la configuration de l'intégration :** permettre à TTD de configurer l'onglet d'intégration (sauf les postbacks d'événements in-app)
* **Autoriser la configuration des postbacks d'événement in-app** : permettre à TTD de configurer l'auto-mappage des postbacks d'événements in-app dans l'onglet Intégration
* **Autoriser l'accès à votre rapport de rétention** : valable uniquement pour les données de rétention de TTD
* **Autoriser l'accès aux données agrégées de vos utilisateurs fidèles** : valable uniquement pour les données des utilisateurs fidèles de TTD
* **Autoriser l'accès à vos données agrégées d'évènements in-app** : uniquement pour les données d'évènements in-app de TTD
* **Autoriser l'accès à vos données agrégées de revenus** : valable uniquement pour les données de revenus attribuées à TTD
* **Autoriser l'accès à votre tableau de bord Protect360 :** uniquement pour les données Protect360 de TTD, et à la condition que cette fonction soit activée

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">l'octroi d'autorisations à un réseau publicitaire.</Anchor>

</Accordion>

<div data-zendesk-anchors="setting-up-the-trade-desk-ttd=configuration-de-the-trade-desk-ttd h_01HH2DHQWXTB9K2R07SJP1AXER=configuration-de-the-trade-desk-ttd h_01HH2DHQWX9Y6R1J3HPYWTAC2Z=step-1-define-conversion-events-in-ttd h_01HH2DHQWXTZ5EMJNYRGJMY7QA=step-2-define-conversion-events-in-appsflyer h_01HH2DHQWXCWF0H1GJGJS2YYDA=step-3-map-defined-conversion-events-from-appsflyer step-4-add-click-and-impression-trackers%C2%A0to-campaign-creatives=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWX1Z10PTRM8S7538YX=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWXX1EEARNBC61W3CDK=note integrating-ttd-with-appsflyer=int%C3%A9gration-avec-appsflyer h_01GFNDH51M6KYE39C7DJW3BJ8W=int%C3%A9gration-avec-appsflyer h_01GF8CKQYVDW5Z7141MJDGGW4C=integration-tab activate-partner=activation-du-partenaire h_01HH2DHQWYME21J7JV176N71P2=activation-du-partenaire advanced-privacy=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e h_01HH2DHQWYFJB3ZCWVZZ048AQP=protection-de-la-vie-priv%C3%A9e-avanc%C3%A9e general-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux h_01HH2DHQWYN3CZZCFT9X2R2N9J=param%C3%A8tres-g%C3%A9n%C3%A9raux default-postbacks=postbacks-par-d%C3%A9faut h_01HH2DHQWY1GPVP5W5R4XV2H9C=postbacks-par-d%C3%A9faut h_01HH2DHQWY284121FR8HSFGH45=note-1 inapp-events-settings=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app h_01HH2DHQWY0XM70BPE7222XE78=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app h_01HH2DHQWY7X522JKKC4A45BHN=attribution-link-tab attribution-link-parameters=param%C3%A8tres-du-lien-dattribution h_01HH2DHQWY4GXPMCV5JEBFERG6=param%C3%A8tres-du-lien-dattribution default-parameters=param%C3%A8tres-par-d%C3%A9faut h_01HH2DHQWYZSECQWRQEKDB9KZH=param%C3%A8tres-par-d%C3%A9faut parameters-for-measuring-ctv=param%C3%A8tres-de-mesure-ctv h_01HH2DHQWYZPKCY947MWK7GEAP=param%C3%A8tres-de-mesure-ctv clickthrough-attribution=attribution-post-clic h_01HH2DHQWYCFGJK4ZT9CXFX3X3=attribution-post-clic viewthrough-attribution=attribution-post-vue h_01HH2DHQWYP6S95MRAS39Q4RTT=attribution-post-vue h_01HH2DHQWYP5GYN2GH3C839P3N=cost-tab h_01HH2DHQWYG3KZTE0HH7QV4H6X=ad-revenue-tab h_01HH2DHQWYA9HAWT5PV092T6E9=permissions-tab ad-network-permissions=autorisations-pour-le-r%C3%A9seau-publicitaire h_01HH2DHQWYCWYQFBDA19Z9BA8W=autorisations-pour-le-r%C3%A9seau-publicitaire" />
