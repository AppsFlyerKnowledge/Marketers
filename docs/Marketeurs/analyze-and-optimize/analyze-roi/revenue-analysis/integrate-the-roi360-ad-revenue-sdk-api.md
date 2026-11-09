---
title: >-
  Guide sur l’intégration du connecteur SDK ROI360 des revenus publicitaires
  génériques de niveau impression
metadata:
  keywords:
    - ROI
    - ad revenue
    - Advertisers
    - Advertiser
    - Developer
    - Developers
    - ad revenue SDK
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-12T09:09:07Z'
  edited_at: '2024-07-01T13:48:48Z'
  id: 4416353506833
  locale: fr
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/fr/articles/4416353506833
---
> **En bref :** Le connecteur SDK générique AppsFlyer des revenus publicitaires communique avec les réseaux publicitaires pour rapporter les revenus publicitaires au niveau de l'impression.

<Image align="center" alt="mceclip1__1_.png" src="https://files.readme.io/202ded6950dfbf370bb48738876224936d28ecfae0c0aba09d1c49892b774cb5-31202279100177.png" />

<div id="impression-level-ad-revenue-reporting-by-sdk-api" />

## Rapports des revenus publicitaires de niveau impression par connecteur SDK

**Rapport des revenus publicitaires**

Les revenus publicitaires sont transmis à AppsFlyer avec une granularité globale (via API) ou une granularité au niveau de l'impression (via SDK). Données de niveau impression via SDK :

* Les données sont plus fraîches et disponibles plus rapidement dans AppsFlyer.
* Prend en charge SKAN.

Remarque :

* Ces impressions sont collectées et traitées au sein d’AppsFlyer, mais elles ne sont pas comptabilisées dans votre forfait in-app.
* Il existe <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad_revenue_unity_connector">un plug-in AppsFlyer pour Unity</Anchor>.

<div id="reporting-ad-revenue-using-the-sdk-api" />

### Rapport sur les revenus publicitaires via le connecteur SDK

**Les principes du SDK**

Le connecteur SDK de revenus publicitaires envoie les données des revenus d'impression au SDK AppsFlyer. Ces événements d'impression sont collectés et traités dans AppsFlyer, puis l'événement de revenu publicitaire `af_ad_revenue`est généré dans la plateforme où le revenu est attribué à la source AU d’origine.

**Affichage des données**

C’est l'événement `af_ad_revenue` qui est utilisé pour identifier les revenus publicitaires. Cet événement est utilisé sur toute la plateforme, y compris dans les tableaux de bord et les outils de fourniture des données.

**Réseaux pris en charge**

Voici la liste des réseaux de médiation et de monétisation des revenus publicitaires qui sont pris en charge, et qui peuvent nous transmettre les données via le connecteur SDK générique des revenus publicitaires :

* <Anchor target="_blank" href="/marketers/fr/docs/ironsource-campaign-configuration#ad-revenue-tab">Médiation Unity LevelPlay</Anchor> (anciennement ironSource)
* <Anchor target="_blank" href="/marketers/fr/docs/applovin-max-ad-revenue-configuration">AppLovin Max</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/fyber-campaign-configuration">Fyber</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/appodeal-campaign-configuration">Appodeal</Anchor>
* Admost
* Topon
* Tradplus
* <Anchor target="_blank" href="/marketers/fr/docs/yandex-direct-campaign-configuration">Yandex</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/chartboost-campaign-configuration">Chartboost</Anchor>
* customMediation (lorsque la solution de médiation n’est pas dans la liste des partenaires de médiation pris en charge))
* directMonetizationNetwork (lorsque l'app s'intègre directement aux réseaux de monétisation sans médiation)

**Actualisation des données**

Le connecteur SDK **transmet les données de revenus à la plateforme au moment où la publicité s'affiche. Pour les clients ROI360 premium, les données sont disponibles à :**

* **1 heure du matin, puis chaque heure suivante pour le sujet DataLocker de niveau impression**
* **5 heures du matin UTC, puis toutes les 4 heures pour les rapports de Cohorte et d’Activité AppsFlyer**

<div id="implementing-appsflyer-ad-revenue-sdk-api" />

## Implémenter le connecteur SDK générique AppsFlyer pour les revenus publicitaires

**Pour installer le connecteur SDK générique de revenus publicitaires AppsFlyer** :

1. <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Dans AppsFlyer, activez les revenus publicitaires de niveau SDK</Anchor> pour le partenaire que vous souhaitez connecter. **Remarque** : Cette opération doit s’effectuer séparément pour chaque application.
2. Demandez à votre développeur d'intégrer le connecteur SDK générique de revenus publicitaires AppsFlyer en suivant <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">ces instructions</Anchor>.
3. Pour enregistrer les revenus publicitaires dans votre tableau de bord SKAdNetwork, suivez les <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">instructions relatives aux revenus publicitaires SKAN</Anchor>.

<div id="traits-and-limitations" />

## Caractéristiques et limitations

| Caractéristique | Remarques |
| --- | --- |
| Admob | <ul><li>Pour activer iLTV dans Admob, suivez <Anchor target="_blank" href="https://support.google.com/admob/answer/11322405#getstarted">ce lien</Anchor></li><li>Pour Android et Unity, les revenus d'impression sont rapportés par le SDK Admob iLTV en <Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/AdValue#public-long-getvaluemicros">micro-unités</Anchor>. Pour que le montant en USD des revenus publicitaires affiché dans AppsFlyer soit correct, divisez le montant extrait du gestionnaire d'événements iLTV par 1 million avant de l'envoyer à AppsFlyer.</li></ul> |
| Valeur des revenus publicitaires | Les événements d'impression dont les revenus dépassent 10 USD (et l'équivalent dans les autres devises) ne seront pas traités par le connecteur SDK. |
| Canal | Le canal n'est pas pris en charge pour les apps hors-store, sauf pour Amazon. |
| Type de publicité | Pas de prise en charge. |

<div data-zendesk-anchors="impressionlevel-ad-revenue-reporting-by-sdk-connector=rapports-des-revenus-publicitaires-de-niveau-impression-par-connecteur-sdk 01H8HHAQHK6CDK8X2Y6N4GANNC=rapports-des-revenus-publicitaires-de-niveau-impression-par-connecteur-sdk reporting-ad-revenue-using-the-sdk-connector=rapport-sur-les-revenus-publicitaires-via-le-connecteur-sdk 01H8HHAQHKQ3H3R21Z1JYNJ2EE=rapport-sur-les-revenus-publicitaires-via-le-connecteur-sdk implementing-generic-appsflyer-ad-revenue-sdk-connector=impl%C3%A9menter-le-connecteur-sdk-g%C3%A9n%C3%A9rique-appsflyer-pour-les-revenus-publicitaires 01H8HHAQHKCXKPJJE8EDT1J9CR=impl%C3%A9menter-le-connecteur-sdk-g%C3%A9n%C3%A9rique-appsflyer-pour-les-revenus-publicitaires traits-and-limitations=caract%C3%A9ristiques-et-limitations 01H8HHAQHMCSVQ2ZAT3G7XJKAN=caract%C3%A9ristiques-et-limitations" />
