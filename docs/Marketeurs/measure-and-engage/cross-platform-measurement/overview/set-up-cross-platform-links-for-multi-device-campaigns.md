---
title: Liens d’attribution multiplateforme
metadata:
  keywords:
    - Attribution
    - Advertisers
    - CTV
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2022-06-19T07:02:43Z'
  edited_at: '2024-09-19T09:02:39Z'
  id: 6966260647185
  locale: fr
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/fr/articles/6966260647185
---
> **En bref :** découvrez comment promouvoir, attribuer et mesurer les installations d’applications sur des plateformes à des vues publicitaires sur d’autres plateformes. Par exemple, les installations d’apps mobile pour les publicités visionnées sur les appareils CTV, les installations d’apps de console de jeu pour les publicités affichées sur mobile ou ordinateur de bureau (Web), et les installations d’apps CTV pour les publicités affichées sur mobile ou sur ordinateur de bureau (Web).

<div id="overview" />

## Présentation

Avec les liens d’attribution multiplateforme AppsFlyer (URL d’impression), vous pouvez attribuer les installations d’une plateforme aux vues de publicités affichées sur une autre plateforme. Plusieurs installations au sein d’un même foyer peuvent être attribuées à la même impression d’une publicité multiplateforme.

<div id="set-up-cross-platform-partner-integration" />

## Configurer l’attribution multiplateforme

Pour configurer l’attribution multiplateforme à l’aide d’URL d’impression multiplateforme, suivez ces étapes :

<div id="create-a-onelink-templatefor-cross-platform-attribution" />

<div id="step-1-create-or-edit-a-onelink-template-for-crossplatform-attribution" />

<Accordion title="Étape 1 : créer ou modifier un template OneLink pour l’attribution multiplateforme">

Un seul template prend en charge votre app sur plusieurs plateformes (ce qui signifie qu’un seul template fonctionne sur toutes les plateformes).

1. Créez ou modifiez un<Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">Template OneLinkpour</Anchor> l’attribution multiplateforme.
2. Dans**Attribution multiplateforme**, cliquez sur l’icône**bouton Modifier ->** **Activer l’attribution multiplateforme**
3. Dans la liste déroulante de la plateforme à configurer, sélectionnez l’application appropriée. **Remarque** : Chaque app ne peut être ajoutée qu’à un unique template OneLink lorsque l’attribution multiplateforme est activée.

   [<Image alt="Cross-platform attribution.png" src="https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png" width="476px" />](https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png)

</Accordion>

<div id="step-2-enable-viewthrough-attribution" />

<Accordion title="Étape 2 : activer l'attribution post-vue">

Pour que les liens soient utilisés par des partenaires intégrés, vous devez activer l’attribution post-vue.

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégrations actives**.
2. **Sélectionnez le partenaire intégré.**
3. Dans l'onglet **Intégration**, désactivez **l'attribution post-vue des installations**.
4. Cliquez sur **Enregistrer l'intégration**.

</Accordion>

<div id="step-3-enable-equal-priority-for-crossplatform-impressions" />

<Accordion title="Étape 3 : activer la priorité égale pour les impressions multiplateformes">

Vous pouvez configurer les impressions pour qu’elles aient la même priorité d’attribution qu’un clic déterministe. L’installation de l’application sera attribuée à la plateforme multiplateforme. Ceci peut être paramétré jusqu’à 6 heures maximum.

Pour activer la même priorité aux impressions multiplateformes :

1. Dans AppsFlyer, dans le menu latéral, sélectionnez**Collaboration**>**Intégrations actives**et sélectionnez le partenaire intégré.
2. Dans l’onglet **Intégration**, allez dans **Multiplateforme** et activez **Priorité égale d’attribution multiplateforme.**
3. Définissez la**Fenêtre rétrospective de priorité égale d’attribution**. [![](https://support.appsflyer.com/hc/article_attachments/13049451072017)](https://support.appsflyer.com/hc/article_attachments/13049451072017)
4. Cliquez sur **Enregistrer l'intégration**.

</Accordion>

<div id="step-4-create-an-attribution-link-crossplatform-impression-url" />

<Accordion title="Étape 4 : créer un lien d’attribution (URL d’impression multiplateforme)">

Pour créer un<Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">Lien d’attribution</Anchor> (URL d’impression multiplateforme) pour les réseaux intégrés

1. Dans AppsFlyer, dans le menu latéral, sélectionnez**Collaboration**>**Intégrations actives**et sélectionnez le partenaire intégré.
2. Dans **Lien d’attribution**, lors de la création du <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">Lien OneLink</Anchor>, sélectionnez Utiliser OneLink.
3. Sélectionnez le template OneLink que vous avez créé pour l’attribution multiplateforme.
4. Faites défiler vers le bas jusqu’à **Attribution post-vue**.[![](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)
5. Lancez l’**Attribution multiplateforme**. Cela ajoute le paramètre `af_xplatform=true` au lien d’attribution d’impression, et donne au lien des fonctionnalités d’attribution multiplateforme. Sans ce paramètre, l’URL fonctionne comme une URL d’impression standard qui ne peut pas attribuer plusieurs installations à la même impression.
6. Configurez la **Fenêtre rétrospective d’attribution post-vue multiplateforme**. Cela ajoute le paramètre `af_xplatform_vt_lookback` au lien d’attribution d’impression et indique le nombre d’heures (jusqu’à 72) suivant l’impression durant lesquelles l’installation de l’app peut être attribuée à l’impression.
7. Ajoutez tout autre paramètre d’attribution nécessaire. Utilisez des noms qui identifient clairement votre campagne d’app multiplateforme. <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">Plus d’infos ici</Anchor> sur les paramètres que vous pouvez ajouter pour obtenir des données et métriques supplémentaires.

   Exemple de lien :

   ```http
   https://impressions.onelink.me/{template_id}?pid=__media_source__&af_xplatform=true&af_xplatform_vt_lookback=24h&af_siteid=__CSITE__&c=__ctv_to_mobile__&af_channel=__PLACEMENT__&af_c_id=__CAMPAIGN_ID__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_source_platform=__source_platform__&af_source_device_category=__device_category__&af_ad_type=__CTYPE__&redirect=false
   ```
8. Transmettez le lien au réseau publicitaire pour qu’il le place après la publicité affichée sur les plateformes CTV, PC ou console.

<div id="important-1" />

> 🚧 **Attention !**
>
> Pour les médias propriétaire et les partenaires non intégrés, ajoutez les paramètres requis.  <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">Plus d’infos ici</Anchor> sur les paramètres que vous pouvez ajouter pour obtenir des données et métriques supplémentaires.

</Accordion>

## Liste des réseaux publicitaires

La liste des réseaux publicitaires qui diffusent des publicités sur les plateformes CTV, PC et console, et qui prennent en charge l’attribution multiplateforme (ex. CTV vers app mobile) se trouve dans la section <Anchor target="_blank" href="https://hq1.appsflyer.com/partner-marketplace/explore?integrationLevels=CROSS_PLATFORM">Marketplace des partenaires AppsFlyer</Anchor>. Pour y accéder vous devrez vous connecter à votre compte AppsFlyer.

<div id="traits-and-limitations" />

## Caractéristiques et limitations

| Caractéristique | Remarques |
| --- | --- |
| <span id="attribution-window"></span>Fenêtre d'attribution | Entre 1 et 72 heures, selon le paramètre de la fenêtre rétrospective `af_xplatform_vt_lookback`(la valeur par défaut est 24 heures). |
| <span id="retargeting"></span>Retargeting | <ul><li>Ré-attribution : prise en charge pour le multiplateforme vers mobile, mais pas pour les autres plateformes.</li><li>Ré-engagement : non pris en charge.</li></ul> |
| <span id="attribution-method"></span>Méthode d'attribution | Attribution post-vue via la modélisation probabiliste |
| <span id="household-attribution"></span>Attribution des foyers | Pris en charge. Cela signifie que plusieurs installations au sein d’un même foyer peuvent être attribuées à la même impression publicitaire multiplateforme. |
| <span id="reporting"></span>Reporting | <ul><li>Les installations multiplateformes sont disponibles dans les tableaux de bord et rapports AppsFlyer de base :<ul><li>Données agrégées <Anchor target="_blank" href="/marketers/fr/docs/getting-started-with-appsflyer-dashboards">Tableaux de bord</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview">Rapports</Anchor></li><li>Rapports de <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">données brutes</Anchor></li></ul></li><li>Les impressions multiplateformes ne s’affichent pas dans les tableaux de bord de niveau de application. Elles sont par contre disponibles dans le <Anchor target="_blank" href="/marketers/fr/docs/data-locker-advertiser-reports#user-journey">Rapport sur les engagements multiplateformes</Anchor> via Data Locker.</li><li>Veillez à nommer votre paramètre selon des critères qui permettent d’identifier facilement votre campagne multiplateforme.</li></ul> |
| <span id="ip-masking"></span>Masquer l’IP | Le masquage de l’IP pour les engagements multiplateformes n’est pas pris en charge, car il s’agit d’une caractéristique au niveau de l’application. Si `ip_masking`  est configuré, l’installation ne sera pas attribuée à l’engagement multiplateforme. |
| <span id="ctvto-mobile"></span>CTV-to-mobile | Les flux d’attribution CTV vers mobile ne sont disponibles que pour les partenaires intégrés qui ont l’autorisation de mener des campagnes multiplateformes. |
| <span id="cross-platform-attribution-links-in-mobile-devices"></span>Liens d’attribution multiplateformes sur les appareils mobile | Lorsqu’un lien d’attribution multiplateforme s’affiche sur un appareil mobile, l’attribution est déterminée par modélisation probabiliste mobile standard, et non par le flux d’attribution multiplateforme conçu pour les <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#tv-screens">CTV</Anchor>, PC et consoles. Par conséquent, les impressions mobile ne seront pas éligibles à la [Priorité égale](#step-3-enable-equal-priority-for-crossplatform-impressions), la [Période d’analyse prolongéeou](#attribution-window) l’[Attribution des foyers](#household-attribution) qui ne sont proposées qu’aux impressions multiplateformes véritables. |

<div id="discrepancies" />

## Écarts dans les mesures

AppsFlyer et tvScientific n’ont pas les mêmes modèles d’attribution. Cela peut entraîner des différences de résultat entre les tableaux de bord tvScientific et AppsFlyer. Ce qui peut causer des écarts :

| Cause | tvScientific | AppsFlyer |
| --- | --- | --- |
| Modèle de référence | Modèle d’attribution de crédit partagé | Modèle d’attribution last touch |
| Fenêtre rétrospective | Jusqu'à 30 jours | Jusqu’à 72 heures |
| Retargeting | Attribution des nouveaux utilisateurs (installations) **et** des utilisateurs récurrents (réengagements) | Attribution des nouveaux utilisateurs (installations) uniquement |
| Attribution des coûts | Le coût est attribué à l’impression quel que soit le système d’exploitation | Le coût est attribué à l’impression sur des systèmes séparés pour iOS et Android |

## FAQ

| Q : Faut-il activer l’option Attribution post-vue via modélisation probabiliste ?<br /><br />R : Non. Il n’est pas nécessaire d’activer l’Attribution post-vue via modélisation probabiliste dans les paramètres de votre application pour que l’attribution post-vue multiplateforme fonctionne. |
| --- |

<div data-zendesk-anchors="overview=pr%C3%A9sentation 01H8V0RV7X8JEVEJ36TJB1X43D=pr%C3%A9sentation set-up-crossplatform-attribution=configurer-lattribution-multiplateforme h_01HVECG1TZSDTP0WBG7XYM509G=configurer-lattribution-multiplateforme step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution=step-1-create-or-edit-a-onelink-template-for-crossplatform-attribution h_01HVECG1TZ8B5GH28CZM2186BF=step-1-create-or-edit-a-onelink-template-for-crossplatform-attribution h_01HVECG1TZKNG17STSN5XJAF9C=step-2-enable-viewthrough-attribution h_01HVECG1TZP1P67W5A9Q1ZB9F7=step-3-enable-equal-priority-for-crossplatform-impressions step-4-create-an%C2%A0attribution-link%C2%A0crossplatform-impression-url=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ6WP257R9D8A105FR=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ3K1EFA22716K2B9X=attention- list-of-ad-networks=liste-des-r%C3%A9seaux-publicitaires h_01HVED5DJP78EGF2D8SFJVND1H=liste-des-r%C3%A9seaux-publicitaires traits-and-limitations=caract%C3%A9ristiques-et-limitations h_01HVED5DJPFR5XCWYDSYCHMCR6=caract%C3%A9ristiques-et-limitations discrepancies=%C3%A9carts-dans-les-mesures h_01HVED5DJPMP3AQDTN3GM77T2F=%C3%A9carts-dans-les-mesures h_01HVED5DJPBPDSZ0AAY1RG8NEZ=faq" />
