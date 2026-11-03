---
title: Types d'engagements enrichis
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-01-21T13:45:23Z'
  edited_at: '2024-11-11T15:12:33Z'
  id: 21837486015889
  locale: fr
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/fr/articles/21837486015889
---
> **En bref :** Alors que les types de publicités sont devenus sophistiqués et complexes, les rapports sont restés très limités, se concentrant uniquement sur l'attribution des vues et des clics. Les types d'engagement enrichis changent la donne en reflétant le spectre complet de l'engagement et de l'intentionnalité des utilisateurs lorsqu'ils voient une publicité ou interagissent avec elle.

## Introduction

Au cours des dernières années, de nouveaux types de publicités créatives telles que les publicités jouables, les publicités ignorables et les vidéos courtes ont été introduites sur le marché, offrant de nouvelles façons de se connecter avec les utilisateurs. Ces nouveaux types de publicités diffèrent considérablement des bannières statiques et des unités vidéo de faible qualité du passé et offrent aux annonceurs des capacités plus étendues et des formats plus larges.

Cependant, bien que les types de publicités soient devenus sophistiqués, plus complexes et plus interactifs, les rapports sont restés très limités, se concentrant uniquement sur l'attribution des vues et des clics. Les différents types d'engagements ont des poids, des niveaux d'intention et un impact différents, mais les méthodologies de mesure actuelles ne tiennent pas compte cette nouvelle réalité. Naturellement, les réseaux publicitaires veulent s'assurer que les niveaux d'intention et d'engagement sont représentés de la meilleure façon possible, ce qui a conduit à un manque de standardisation dans l'écosystème. Cela entraîne en fin de compte une compréhension partielle par les annonceurs de la performance de leurs dépenses publicitaires.

En collaboration avec les principaux réseaux, AppsFlyer introduit une nouvelle norme pour les engagements afin d'offrir confiance et transparence dans tout l'écosystème. Les types d'engagement enrichis reflètent le spectre complet de l'engagement et de l'intentionnalité des utilisateurs lorsqu'ils voient une publicité ou interagissent avec elle. Ce cadre garantit que ces normes sont maintenues dans l'écosystème des partenaires d'AppsFlyer et au-delà. Grâce aux types d'engagement enrichis, les annonceurs peuvent s'assurer d'avoir une vision standardisée et détaillée de la performance de leurs dépenses publicitaires et peuvent exploiter ces informations pour améliorer l'allocation de leur budget et augmenter leur ROAS.

## Types d'engagements enrichis

Le cadre des types d'engagement enrichis offre une visibilité sur les nuances du parcours utilisateur, en indiquant par exemple quand les vues (par exemple, les vidéos pouvant être sautées pendant plus de 5 secondes) et quand les clics ne mènent pas à l'ouverture de l'application ou à la boutique d'applications. Ce faisant, les marketeurs obtiennent plus d'informations sur les actions de leurs utilisateurs, ce qui conduit à une allocation de budget plus intelligente et à un meilleur ROI.

Voici la liste des nouveaux types d'engagement :

| Type d’engagement | Description |
| --- | --- |
| <span id="preload"></span>preload | L'application est préinstallée par le fabricant d'équipements d'origine (OEM) à l'usine ou par le fournisseur lors de la première activation de l'appareil. Il est aussi possible d'inviter l'utilisateur à télécharger l'app lors de la première activation de l'appareil. |
| <span id="click_to_download"></span>click\_to\_download | Lorsque l'utilisateur interagit avec une publicité, l'application est automatiquement téléchargée et installée sur l'appareil sans redirection vers un app store. |
| <span id="click_to_app"></span>click\_to\_app | Un clic sur une annonce, un scan QR code, un lien en deep linking ou tout autre clic qui redirige l’utilisateur vers l’application ou vers l’app store concerné pour télécharger l’application. |
| <span id="engaged_click"></span>engaged\_click | Un clic qui maintient l’utilisateur dans le même environnement, en interagissant avec la pub, et qui ne le dirige PAS vers l’App Store ou pour lancer l’application. |
| <span id="engaged_view"></span>engaged\_view | Une vue engagée se produit lorsqu'une vue significative est affichée, dans des vidéos pouvant être ignorées, des vidéos avec récompenses ou des publicités diffusées par StoreKit. Par exemple, lorsqu'un utilisateur regarde une publicité vidéo pouvant être sautée pendant au moins 5 secondes après l'apparition de l'option de saut. |
| <span id="view"></span>Vue | On parle de vue d’annonce (ad view) lorsqu’une annonce est affichée et qu’une impression a lieu. |
| <span id="listening"></span>écoute | On parle d’écoute lorsqu’un utilisateur écoute une publicité audio, telle qu’une publicité pour un podcast. |

## Fenêtre rétrospective d'attribution de priorité égale

Le cadre des types d'engagement enrichis n'a pas d'incidence sur la priorité d'attribution des types d'engagement. Par conséquent, l'introduction de l'EET ne devrait pas avoir d'incidence sur votre taux d'installation et de conversion.

Le tableau ci-dessous précise la <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#attribution-waterfall">priorité d'attribution</Anchor> et la <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows#fenêtre-dattribution">fenêtre de contrôle</Anchor> pour chaque type d'engagement :

<table><thead><tr><th>Engagement</th><th>Types d'engagement</th><th>Priorité d’attribution</th><th>Fenêtre rétrospective\*\*</th></tr></thead><tbody><tr><td rowspan="2">Télécharger </td><td>preload</td><td>1</td><td>1h-180j | par défaut : 90d</td></tr><tr><td>click_to_download</td><td>2</td><td>1h-30j | default : 7j</td></tr><tr><td rowspan="2">Clic</td><td>click_to_app</td><td>2</td><td>1h-30j | default : 7j</td></tr><tr><td>engaged_click</td><td>2</td><td>1h-7j | par défaut : 2d </td></tr><tr><td rowspan="3">Impression</td><td>engaged_view</td><td>2</td><td>1h-7j | par défaut : 2d</td></tr><tr><td>Vue</td><td>3</td><td>1h-24h | par défaut : 24h</td></tr><tr><td>écoute</td><td>3</td><td>1h-24h | par défaut : 24h</td></tr></tbody></table>

Lorsqu'un type d'engagement n'est pas signalé, la priorité par défaut est définie*(click\_to\_app* pour les clics, *view* pour les impressions).

Les fenêtres de rétroaction pour `engaged_click` et `engaged_view` ne peuvent être définies que pour les réseaux non-SRN.

## Quels réseaux peuvent signaler l'EET à AppsFlyer ?

Une assistance pour l'engagement enrichi sera disponible pour les réseaux qui répondent aux critères Premier, Advance ou Engage du programme partenaire AppsFlyer. Ces niveaux se réfèrent aux réseaux ayant un historique significatif de fourniture de trafic de haute qualité de manière constante à grande échelle pour nos clients communs, transmettant les données d'engagement de manière transparente et fiable, et intégrés avec une gamme complète de services AppsFlyer.

Les réseaux autorisés peuvent être classés en deux groupes :

* [Les réseaux qui remplissent les conditions requises pour bénéficier d'un soutien à l'engagement enrichi **, y compris les** clics et les vues engagés.](#networks-that-report-engagement-types) Ces réseaux nécessitent une configuration spéciale dans AppsFlyer.
* [Les réseaux qui remplissent les conditions requises pour bénéficier de l'Engagement enrichi **excluent les** clics et les vues engagés](#01JCAT81K2EJNH91YS6NJGMXMB-data-title). Pour pouvoir rapporter les clics et les vues engagés, contactez le support AppsFlyer car une configuration spéciale est nécessaire.

> ❗️ **Avertissement**
>
> Les clics et les impressions provenant de réseaux non autorisés qui incluent le paramètre af\_engagement\_type seront rejetés et ne seront pas utilisés pour l'attribution.

<div id="networks-that-report-engagement-types" />

<Accordion title="Des réseaux qui favorisent les clics et les vues engagés">

Le tableau ci-dessous énumère les réseaux qualifiés par AppsFlyer pour signaler `engaged_clicks` et `engaged_views`. Les réseaux qui souhaitent communiquer ces données doivent contacter le service d'assistance d'AppsFlyer.

| **Réseau publicitaire** | **Les opinions engagées soutiennent** | **Soutien aux clics engagés** |
| --- | --- | --- |
| facebook\_int | Oui |  |
| tiktokglobal\_int | Oui | Oui |
| snapchat\_int | Oui | Oui |
| bytedanceglobal\_int | Oui | Oui |
| adjoe\_int |  | Oui |
| appier\_int | Oui | Oui |
| appnext\_int | Oui |  |
| inmobidsp\_int | Oui | Oui |
| ironsource\_int | Oui |  |
| lap\_int | Oui |  |
| liftoff\_int | Oui | Oui |
| mintegral\_int | Oui | Oui |
| moloco\_int | Oui | Oui |
| smadex\_int | Oui | Oui |
| trademob\_int | Oui |  |
| unityads\_int | Oui |  |
| vungle\_int | Oui |  |
| yahoojapan\_int | Oui |  |
| youappi\_int | Oui | Oui |

</Accordion>

<div id="01JCAT81K2EJNH91YS6NJGMXMB-data-title" />

<Accordion title="Liste des réseaux autorisés">

La liste des réseaux autorisés comprend les partenaires qui peuvent signaler des événements de type engagement enrichi, à l'exception des clics engagés et des vues engagées. Les réseaux autorisés qui souhaitent signaler `engaged_clicks` et `engaged_views` doivent contacter le service d'assistance d'AppsFlyer. Voir [ci-dessus](#networks-that-report-engagement-types) la liste des réseaux autorisés à signaler `engaged_clicks` et `engaged_views`.

| Nom du partenaire |
| --- |
| Jampp |
| Fluent |
| AWIN |
| Rakuten |
| OPPOPAI Pre-Install |
| VK Ads (anciennement myTarget) |
| Vivo Preload |
| OPPO Global |
| Mistplay |
| Amazon DSP |
| Adikteev |
| Criteo |
| OPPO |
| Glance |
| OPPO Store Traffic (Global) |
| XiaomiPAI Pre-Install |
| YouAppi |
| Yandex Direct |
| vivo Global |
| Remerge |
| adjoe GmbH |
| Treasure Data |
| Xiaomi Global |
| Smadex |
| Bigo |
| Motorola Pre-Install |
| Amazon |
| Bidease |
| Yahoo Japan |
| Kakao |
| Line |
| Reddit |
| Trade Desk |
| OneView |
| Samsung |
| Adaction |
| Adaction3 |
| Stackadapt |
| Cauly |
| Naver |
| Hotstar |
| Truecaller |
| Josh |
| PayTM |
| Transsion |
| Huawei |
| Mintegral |
| Apple Search Ads |
| Meta Ads |
| Google Ads (Adwords) |
| X Ads (anciennement Twitter Ads) |
| Snapchat |
| ByteDance Ads China |
| TikTok for Business - SRN avancé |
| TikTok for Business - Legacy |
| Google Marketing Platform (DV360/CM360) |
| AdColony |
| Digital Turbine dans l'appareil |
| Digital Turbine |
| Appreciate |
| Liftoff |
| Appnext |
| AppLovin |
| ironSource |
| Moloco |
| Unity Ads |
| Tapjoy |
| Vungle |
| Kuaishou |
| Aura de Unity |
| Tencent AMS |
| Roku |
| TV Scientific |
| Chartboost |
| Appier |
| kwaiforbusiness |
| Mobupps |
| Kayzen |
| Vibe |
| InMobi DSP |

</Accordion>

## Définir des fenêtres de rétroaction pour les clics et les vues engagés

**Pour définir les fenêtres de rétroaction pour les clics engagés et les vues engagées :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaborer** > **Intégrations actives**.
2. Sélectionnez le partenaire intégré.
3. Définir les fenêtres rétrospectives pour l'attribution des vues et des clics engagés.

   > 📘 **Note**
   >
   > Les fenêtres de retour des clics et des vues engagés sont toujours définies dans l'**onglet Intégration du** partenaire, contrairement aux fenêtres de retour des vues et des clics, qui peuvent être définies sur les liens d'attribution.

4. Cliquez sur **Enregistrer l'intégration**.

## Visualiser et analyser les données EET

### Rapports de données brutes

`engagement_type` sera indiqué dans les rapports de données brutes lorsque le réseau publicitaire en fait état. Il sera également disponible pour les données des contributeurs.

Lorsque aucun clic n'est enregistré, comme dans les cas de préchargement ou de deep linking, AppsFlyer définira la valeur pertinente (préchargement ou `click_to_app` pour le deep linking) dans le nouveau champ dans les rapports de données brutes.

Dans les scénarios ci-dessous, le nouveau champ restera vide dans les rapports de données brutes :

* En cas de non-concordance entre l'engagement (clic/impression) et le type d'engagement, sera déclaré vide.
* Lorsque `af_engagement_type` n'est pas envoyé ou est envoyé avec une valeur vide.

Pour voir le type d'engagement dans les rapports de données brutes, les annonceurs doivent sélectionner ces champs dans le produit de données brutes concerné (le type d'engagement et le type d'engagement des contributeurs ne sont pas sélectionnés par défaut).

### Tableaux de bord

La dimension du type d'engagement est ajoutée dans les tableaux de bord.

[![eet-dashboard.png](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)

## Pour les clients bêta uniquement

Le contenu de cette section est mis à jour pour refléter le support et la fonctionnalité des types d'engagement enrichis (EET) disponibles uniquement pour les clients BETA opt-in. Si vous souhaitez rejoindre le programme BETA, contactez l'assistance AppsFlyer.

### **Priorité d'attribution de l'EET et fenêtre de contrôle** (participants BETA uniquement)

Le cadre des types d'engagement enrichis introduit pour les clients Bêta une nouvelle logique d'attribution, basée sur une <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#attribution-waterfall">priorité d'attribution</Anchor> et des <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows#fenêtre-dattribution">fenêtres de retour</Anchor> actualisées.

Le tableau ci-dessous précise, pour les clients Beta, la priorité d'attribution et la fenêtre de contrôle de chaque type d'engagement :

<table><thead><tr><th>Engagement</th><th>Types d'engagement</th><th>Priorité d’attribution</th><th>Fenêtre rétrospective\*\*</th></tr></thead><tbody><tr><td rowspan="2">Télécharger </td><td>preload</td><td>1</td><td>1h-180j | par défaut : 90d</td></tr><tr><td>click_to_download</td><td>2</td><td>1h-30j | default : 7j</td></tr><tr><td rowspan="2">Clic</td><td>click_to_app</td><td>2</td><td>1h-30j | default : 7j</td></tr><tr><td>engaged_click</td><td>3</td><td>1h-7j | par défaut : 2d</td></tr><tr><td rowspan="3">Impression</td><td>engaged_view</td><td>3</td><td>1h-7j | par défaut : 2d</td></tr><tr><td>Vue</td><td>4</td><td>1h-24h | par défaut : 24h</td></tr><tr><td>écoute</td><td>4</td><td>1h-24h | par défaut : 24h</td></tr></tbody></table>

Lorsqu'un type d'engagement n'est pas signalé, la priorité par défaut est définie*(click\_to\_app* pour les clics, *view* pour les impressions).

Les fenêtres de rétroaction pour `engaged_click` et `engaged_view` ne peuvent être définies que pour les réseaux non-SRN.

### Définir l'attribution de l'enrichissement engagé pour les non-SRN (participants BETA uniquement)

Par défaut, l'attribution des clics engagés et des vues est activée dans l'onglet Intégration pour les partenaires qui la prennent en charge. Ces options seront disponibles à partir du 3 septembre 2024.

**Pour définir l'attribution de l'enrichissement engagé :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaborer** > **Intégrations actives**.
2. Sélectionnez le partenaire intégré.
3. Dans l'onglet **Intégration**, activez l'option **Installer l'attribution des vues engagées** ou **Installer l'attribution des clics engagés**.

   Définir les fenêtres rétrospectives pour l'attribution des vues et des clics engagés.

   > 📘 **Note**
   >
   > Les fenêtres de retour des clics et des vues engagés sont toujours définies dans l'**onglet Intégration du** partenaire, contrairement aux fenêtres de retour des vues et des clics, qui peuvent être définies sur les liens d'attribution.

4. Cliquez sur **Enregistrer l'intégration**.

> 📘 **Note**
>
> * L'attribution des vues et des clics engagés peut être désactivée pour chaque source média. Toutefois, si des clics et des vues engagés sont reçus alors que leur attribution est désactivée, leur nombre peut toujours être disponible dans le tableau de bord, bien qu'il ne soit pas utilisé pour l'attribution.

## **FAQ**

<div id="why-in-some-cases-engaged_clicks-and-engaged_views-get-equal-priority-to-clicks" />

<Accordion title="Pourquoi, dans certains cas, engaged_clicks et engaged_views ont-ils la même priorité que les clics ?">

Les réseaux qui envoient `af_engagement_type=engaged_view/engaged_click` bénéficieront d'une priorité égale à celle des réseaux qui envoient des clics sans `af_engagement_type`. Le crédit sera attribué au point de contact final, tel que déterminé par le modèle d’attribution au dernier clic.

</Accordion>

<div id="is-owned-media-supported" />

<Accordion title="Les médias propriétaires sont-ils pris en charge ?">

Les médias propriétaires ne sont pas pris en charge actuellement. Les liens vers les médias possédés ne doivent pas inclure le paramètre `af_engagement_type`.

</Accordion>

<div id="what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types" />

<Accordion title="Quels types de campagnes sont pertinents pour les types d'engagement enrichis ?">

Les types d'engagement enrichis s'appliquent aux campagnes d'AU et de retargeting.

</Accordion>

<div id="are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard" />

<Accordion title="Les clics et les vues engagés sont-ils inclus dans les nombres globaux de clics et d'impressions du tableau de bord général ?">

Pour les non-SRN, les chiffres sont inclus et comptabilisés en fonction du type de contact (c'est-à-dire que les clics engagés sont comptabilisés en tant que clics, et les vues engagées sont comptabilisées en tant qu'impressions). Pour les SRN, ces données ne sont actuellement pas incluses ni comptabilisées, en attendant la prise en charge par les API des SRN.

</Accordion>

<div id="why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions" />

<Accordion title="Pourquoi ne puis-je pas voir le type d'engagement dans les conversions gp_referrer de Meta ?">

Meta n'indique que engagement\_type=engaged\_view dans son API SRN. Pour les autres conversions, y compris gp\_referrer, le type d'engagement n'est pas disponible.

</Accordion>

<div data-zendesk-anchors="h_01HNCNA03SZ0MJFQ9XHDFXNTA1=introduction enriched-engagement-types=types-dengagements-enrichis h_01HNCNBR7KMT1KQBG5CPZY8YQY=types-dengagements-enrichis eet-attribution-priority-and-lookback-window=fen%C3%AAtre-r%C3%A9trospective-dattribution-de-priorit%C3%A9-%C3%A9gale h_01HNCVYDH17NGA8SH5XNWR4P9X=fen%C3%AAtre-r%C3%A9trospective-dattribution-de-priorit%C3%A9-%C3%A9gale allowed-networks=quels-r%C3%A9seaux-peuvent-signaler-leet-%C3%A0-appsflyer- h_01J00XFV136HPEHVQNPD934409=quels-r%C3%A9seaux-peuvent-signaler-leet-%C3%A0-appsflyer- h_01J00XFV133YYAB7YPQNXM5R37=avertissement 01JCAT81K21T0D1KH9FZNSDK83=networks-that-report-engagement-types 01JCAT81K2EJNH91YS6NJGMXMB%20data-title%3D=01JCAT81K2EJNH91YS6NJGMXMB-data-title allowed-network-list=01JCAT81K2EJNH91YS6NJGMXMB-data-title set%C2%A0engaged-enrichment-attribution=d%C3%A9finir-des-fen%C3%AAtres-de-r%C3%A9troaction-pour-les-clics-et-les-vues-engag%C3%A9s h_01J5B6EVM9P3M1SVR3K7WWK02J=d%C3%A9finir-des-fen%C3%AAtres-de-r%C3%A9troaction-pour-les-clics-et-les-vues-engag%C3%A9s h_01J5B97RCQQG6GN4PCKTQWVF54=note reporting=visualiser-et-analyser-les-donn%C3%A9es-eet h_01J00XFV13YN8QNFZJTGM78EG2=visualiser-et-analyser-les-donn%C3%A9es-eet raw-data=rapports-de-donn%C3%A9es-brutes h_01J00XFV132M8TM6EGFZ7A7C3A=rapports-de-donn%C3%A9es-brutes dashboards=tableaux-de-bord h_01J00XFV13W0SD4MD7H4BT1RC9=tableaux-de-bord for-beta-customers-only=pour-les-clients-b%C3%AAta-uniquement attribution-model-with-enriched-engagement-types-beta=priorit%C3%A9-dattribution-de-leet-et-fen%C3%AAtre-de-contr%C3%B4le-participants-beta-uniquement set-engaged-enrichment-attribution-for-nonsrns-beta-participants-only=d%C3%A9finir-lattribution-de-lenrichissement-engag%C3%A9-pour-les-non-srn-participants-beta-uniquement h_01J5B6EVM98GVYNKYFW29PECPF=note-2 h_01J00XFV13KSZTQEN3QXNJYACP=faq h_01J00XFV135A0ERGVTS0T81V54=why-in-some-cases-engaged_clicks-and-engaged_views-get-equal-priority-to-clicks h_01J00XFV13TG4776DCPHQKRA9E=is-owned-media-supported h_01HNFTS74KF3YFA0SWRGEQAGYQ=what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types h_01HNYY1S6YQ6YNR6RSY7B8H4EM=are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard h_01HQG5Y4JVNCB60AXR9K2GGD0H=why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions" />
