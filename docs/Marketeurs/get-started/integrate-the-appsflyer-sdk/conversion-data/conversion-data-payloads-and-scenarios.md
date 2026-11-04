---
title: Charges utiles et exemples de données de conversion
metadata:
  keywords:
    - Conversion
    - Retargeting
    - Installs
    - Re-attribution
    - Re-engagement
    - Developers
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-31T13:05:33Z'
  edited_at: '2023-10-30T15:34:04Z'
  id: 360000726098
  locale: fr
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/fr/articles/360000726098
---
> **En bref :** utilisez les données de conversion pour identifier les scénarios de conversion, personnaliser l'expérience utilisateur, etc.

<div id="overview" />

## Présentation

Le guide suivant expose différents exemples de conversion d'utilisateur avec les charges utiles de données correspondantes :

* [Acquisition d'utilisateur (UA)](#données-de-conversion-ua-avec-les-srn)
* [Retargeting](#données-de-conversion-pour-le-retargeting)

Les données de conversion sont mises à disposition sur la plateforme via l'un des moyens suivants :

* <Anchor target="_blank" href="/marketers/fr/docs/raw-data-export-page">Rapports de données brutes</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/push-api-streaming-raw-data">API Push</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">Le SDK AppsFlyer</Anchor>

En raison du rapport précision/latence, les données de conversion pour les mêmes ID d'appareils peuvent varier d'une API à l'autre.

<div id="non-organic-conversion-data-payload-fields" />

### Champs de charge utile des données conversion non organique

<div id="fields-always-available" />

#### Champs toujours proposés

Le tableau suivant liste les champs systématiquement présents pour les conversions **non organiques**, quelle que soit la `media_source` de conversion.

| Nom du champ de la charge utile | Nom du champ de données brutes | Remarques |
| --- | --- | --- |
| `media_source` | Source média | Éditeur attribué. Équivaut au paramètre `pid` dans les liens d'attribution |
| `install_time` | Heure d'installation |  |
| `click_time` | Temps de touch attribué | L'heure (UTC) à laquelle le clic ou l'impression a eu lieu. |
| `is_first_launch` | S/O | `true`, `false` |
| `af_status` | Les données brutes sont divisées en rapports séparés : organiques, non organiques | `"Non-organic"` |
| `af_siteid` | ID site |  |
| `adgroup_id` | Identifiant de publicité |  |
| `adset` | Ensemble de publicités |  |
| `adset_id` | Identifiant de l'ensemble de publicités |  |
| `agency` | Partenaire | `null`, ou le nom de l'agence (pour les campagnes gérées par une agence) |
| `campagne` | Campagne |  |
| `campaign_id` | Identifiant de la campagne |  |
| `http_referrer` | Référent HTTP |  |
| `retargeting_conversion_type` | Type de conversion de retargeting | *none*, ou retargeting\_conversion\_type |
| `af_sub[n] (n=1-5)` | Sous-paramètre [n] (n=1-5) |  |

<div id="fields-available-in-some-cases" />

#### Champs proposés dans certains cas

Les champs indiqués dans le tableau suivant sont disponibles en fonction de la manière dont le SRN renseigne l'événement individuel.

<table><thead><tr><th>Nom du champ de données utiles</th><th>Nom du champ de données brutes</th><th>Remarques</th></tr></thead><tbody><tr><td><code>af_channel</code></td><td>Canal</td><td><p>Les SRN qui renseignent ce paramètre :</p><ul><li>AppLovin</li><li>Google Ads</li><li>Meta Ads</li><li>Snapchat</li><li>TikTok for Business</li><li>Twitter</li></ul><p>Exemple : Facebook-Instagram, Google-YouTube </p></td></tr><tr><td><code>orig_cost</code></td><td> </td><td><p>Remarque (1)</p></td></tr><tr><td><code>costs_cents_USD</code></td><td> </td><td><p>Remarque (1)</p></td></tr><tr><td><code>af_cpi</code></td><td> </td><td><p>Remarque (1)</p></td></tr></tbody><tbody><tr><td colspan="4"><p><strong>Remarque</strong></p><p>(1) Les champs de coûts sont renseignés avec les valeurs transmises par le réseau publicitaire. Pour que le réseau publicitaire partage les données de coûts avec AppsFlyer, vous devez activer l'intégration des coûts sur la page <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank"><strong>Intégrations actives</strong></a>. Certains SRN proposent le partage des coûts en masse. Dans ce cas, les champs du coût au niveau de l'événement indiquent 0. </p></td></tr></tbody></table>

<div id="additional-fields" />

### Champs supplémentaires

* <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#paramètres-du-lien-dattribution">Liste des paramètres AppsFlyer</Anchor>
* Vous pouvez ajouter des paramètres au lien d'attribution, ils sont proposés dans la charge utile.

Consultez le <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#data-fields-dictionary">dictionnaire des champs de données brutes</Anchor> pour obtenir plus d'informations.

<div id="limitations" />

### Restrictions

<div id="custom-parameter-names" />

<Accordion title="Nom du paramètre personnalisé">

Les paramètres personnalisés ne peuvent pas avoir pour nom `name` (avec un n minuscule), `Name` avec un N majuscule est valide).

Si un paramètre a pour nom `name`, il est retiré de la charge utile.

</Accordion>

---

<div id="ua-conversion-data-with-srns" />

## Données de conversion UA avec les SRN

<Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">Les réseaux auto-reporting</Anchor>  (SRN) sont des réseaux publicitaires qui ont leurs propres mécanismes d'attribution, comme Meta ads et Google.

Les SRN n'utilisent pas de liens d'attribution. Ce qui signifie que :

* Les champs de charges utiles sont prédéfinis
* Vous ne pouvez pas ajouter de champs à la charge utile en inscrivant un paramètre dans le lien d'attribution.

Les SRNs transmettent les conversions à AppsFlyer. Les données de conversion sont disponibles dans l'application. Les champs disponibles varient selon le SRN et sont détaillés dans les onglets propres à chaque SRN ci-dessous.

<div id="a-note-about-meta-ads" />

#### Un point sur Meta Ads

Si vous menez des campagnes Meta ads sans avoir signé les conditions d'utilisation de Meta, c'est AppsFlyer qui attribue l'installation. La disponibilité des rapports est limitée comme suit :

* **Disponible :** tableaux de bord et rapports agrégés et analytiques
* **Non disponible :** données brutes

<Tabs>
<Tab title="Meta ads">

<div id="meta-ads-conversion-data" />

### Données de conversion Meta ads

| Nom du champ | Remarques | Source des données |
| --- | --- | --- |
| `match_type` | Toujours `"srn"` | AppsFlyer |
| `media_source` | Toujours `"Meta ads"` | AppsFlyer |
| `agency` | *null* ou valeur du paramètre `af_prt` dans le lien d'attribution | Meta Ads |
| `http_referrer` | Toujours `null` | Meta Ads |
| `retargeting_conversion_type` |  | AppsFlyer |
| `af_channel` |  | Meta ads (publisher\_platform) |
| `af_status` | Toujours `"Non-organic"` | AppsFlyer |
| `ad_id` | Réservé à l'usage interne de Meta ads. | Meta ads (ad\_id) |
| `click_time` |  | AppsFlyer |
| `install_time` |  | AppsFlyer |
| `is_first_launch` | `true`, `false` | Appareil |
| `adset_id` | Disponible en données brutes : Adset ID | Meta ads (campaign\_id) |
| `is_fb` | Toujours `true` | AppsFlyer |
| `campagne` | Disponible en données brutes : nom de campagne | Meta ads (campaign\_group\_name) |
| `campaign_id` | Disponible en données brutes : ID de campagne | Meta ads (campaign\_group\_id) |
| `is_paid` | Toujours `true` | Meta Ads |
| `adgroup` | Disponible en données brutes : Ad | Meta ads (adgroup\_name) |
| `adgroup_id` | Disponible en données brutes : ID publicitaire | Meta ads (adgroup\_id) |
| `adset` | Disponible en données brutes : Adset | Meta ads (campaign\_name) |
| `af_siteid` | Toujours `null` | Meta Ads |
| `af_sub [1-5]` | Toujours `null` | Annonceur |

**Attention** ! Les champs concernant les coûts ne sont pas disponibles, car Meta ads ne transmet pas les données de coûts lors de la conversion. Si l'option <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-integration-setup#cost-clicks-and-impressions">partage des coûts</Anchor> est activée, Meta ads transmet les données de coûts à AppsFlyer plusieurs fois par jour.

</Tab>

<Tab title="Google">

<table><caption><h3><span id="google-ads-conversion-data"></span>Données de conversion Google Ads</h3></caption><thead><tr><th>Nom du champ</th><th>Remarques</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Toujours <code>"srn"</code> </td></tr><tr><td><code>media_source</code></td><td>Toujours <code>"googleadwords_int"</code> </td></tr><tr><td><code>agency</code></td><td> <code>"none"</code> ou la valeur de <code>af_prt</code> </td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td><code>af_channel</code></td><td><p>Remarque (1)</p></td></tr><tr><td><code>af_status</code></td><td>Toujours <code>"Non-organic"</code> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>adgroup_name</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td>Toujours <code>null</code> </td></tr><tr><td><code>campagne</code></td><td>Remarque (3)</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>adset</code></td><td>Remarque (3)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_sub [1-5]</code></td><td> </td></tr><tr><td><code>ad_event_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td>Chaîne vide</td></tr><tr><td><code>af_ad_id</code></td><td>Chaîne vide</td></tr><tr><td><code>af_ad_type</code></td><td><span>Type de publicité AdWords</span></td></tr><tr><td><code>af_adset</code></td><td><span>Disponible en données brutes : Adset</span></td></tr><tr><td><code>af_adset_id</code></td><td>Disponible en données brutes : Adset ID</td></tr><tr><td><code>af_c_id</code></td><td>Disponible en données brutes : ID de campagne</td></tr><tr><td><code>af_click_lookback</code></td><td></td></tr><tr><td><code>af_cpi</code></td><td>Remarque (2)</td></tr><tr><td><code>af_dp</code></td><td>Valable uniquement pour <a href="./google-ads-adwords-integration-setup-for-advertisers#utilisation-du-deep-linking-différé-dans-les-campagnes-dapp" target="_blank">les campagnes Google App dans Feeds.</a> </td></tr><tr><td><code>af_keywords</code></td><td>Disponible dans les données brutes : mots-clés</td></tr><tr><td><code>af_prt</code></td><td> <code>"none"</code> ou la valeur de <code>af_prt</code> </td></tr><tr><td><code>af_reengagement_window</code></td><td>Disponible dans les données brutes : fenêtre de réengagement </td></tr><tr><td><code>af_viewthrough_lookback</code></td><td>Disponible dans les données brutes : fenêtre rétrospective pour l'attribution post-vue</td></tr><tr><td><code>click_url</code></td><td>Disponible dans les données brutes : référent HTTP</td></tr><tr><td><code>click-timestamp</code></td><td>Source : AppsFlyer</td></tr><tr><td><code>cost_cents_USD</code></td><td>Remarque (2)</td></tr><tr><td><code>external_account_id</code></td><td>ID du compte AdWords</td></tr><tr><td><code>gclid</code></td><td> </td></tr><tr><td><code>lat</code></td><td> </td></tr><tr><td><code>network</code></td><td>Remarque (1)</td></tr><tr><td><code>orig_cost</code></td><td>Remarque (2)</td></tr><tr><td><code>video_id</code></td><td>Toujours <code>null</code> </td></tr><tr><td colspan="2"><p><strong>Remarque</strong><br/>(1) Google fait appel à plusieurs réseaux publicitaires. Utilisez la paire <code>af_channel</code> et <code>network</code> pour dériver la source d'installation.<br/>(2) Ces champs renvoient la valeur 0. Si l'annonceur active le partage des coûts, Google envoie les données de coûts à AppsFlyer plusieurs fois par jour.(3) Utilisez <code>campaign</code> et <code>ad_set</code> pour personnaliser le contenu utilisateur.</p></td></tr></tbody></table>

</Tab>

<Tab title="ASA">

<table><caption><h3><span id="tiktok-conversion-data"></span><span id="twitter-conversion-data"></span><span id="tiktok-for-business-conversion-data"></span><span id="x-ads-conversion-data"></span><span id="snapchat-conversion-data"></span><span id="apple-search-ads-conversion-data"></span>Données de conversion de Apple Search Ads</h3></caption><thead><tr><th>Nom du champ</th><th>Remarques</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Toujours <code>"srn"</code> </td></tr><tr><td><code>media_source</code></td><td>Toujours <code>"Apple Search Ads"</code> </td></tr><tr><td><code>{"<strike>adset</strike>"}</code></td><td>Remarque (2)</td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><code>{"<strike>af_adset</strike>"}</code></td><td>Remarque (2)</td></tr><tr><td><code>af_adset_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Remarque (1)</td></tr><tr><td><code>{"<strike>af_keywords</strike>"}</code></td><td><p>Remarque (2) - Utilisez les ID de mots-clés</p></td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Toujours <code>"Non-organic"</code> </td></tr><tr><td><code>af_sub [1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td> <code>null</code> ou la valeur de <code>af_prt</code> </td></tr><tr><td><code>{"<strike>campagne</strike>"}</code></td><td>Remarque (2)</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Remarque (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Remarque (1)</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr></tbody><tbody><tr><td colspan="3"><p><strong>Remarque</strong><br/>(1) Apple Search Ads prend en charge le partage des coûts en masse, mais pas les données de conversion.<br/>(2) Obsolète depuis le 15 février 2021 suite à l'adoption de l'API AdServices. par Apple Search Ads.</p></td></tr></tbody></table>

</Tab>

<Tab title="Snap">

| Nom du champ | Remarques |
| --- | --- |
| `match_type` | `"srn"` |
| `media_source` | `"snapchat_int"` |
| `adset` |  |
| `adset_id` |  |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_c_id` |  |
| `af_channel` |  |
| `af_cpi` |  |
| `af_siteid` |  |
| `af_status` | Toujours `"Non-organic"` |
| `af_sub [1-5]` |  |
| `af_viewthrough_lookback` |  |
| `agency` |  |
| `campagne` |  |
| `campaign_id` |  |
| `click_time` |  |
| `cost_cents_USD` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `orig_cost` |  |
| `retargeting_conversion_type` |  |

</Tab>

<Tab title="Twitter">

| Nom du champ | Remarques |
| --- | --- |
| `match_type` | Toujours `"srn"` |
| `media_source` | Toujours `"Twitter"` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_channel` |  |
| `af_siteid` |  |
| `af_status` | Toujours `"Non-organic"` |
| `af_sub [1-5]` |  |
| `agency` | Toujours `null` |
| `campagne` |  |
| `campaign_id` | `null` ou ID de campagne |
| `click_time` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` | `true`, `false` |
| `adgroup` |  |
| `adgroup_id` |  |
| `retargeting_conversion_type` | Toujours `"none"` |

**Remarque**  
 : Les champs de coûts n'apparaissent pas dans la charge utile car Twitter ne prend pas en charge le partage des données de coûts.

</Tab>

<Tab title="Oath">

<table><caption><h3><span id="oath-ad-platforms-conversion-data"></span>Données de conversion de Oath Ad Platforms</h3></caption><thead><tr><th>Nom du champ</th><th>Remarques</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Toujours <code>"srn"</code> </td></tr><tr><td><code>media_source</code></td><td>Toujours <code>"yahoogemini_int"</code> </td></tr><tr><td><code>adset</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td> </td></tr><tr><td><code>af_ad_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Remarque (1)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Toujours <code>"Non-organic"</code> </td></tr><tr><td><code>af_sub [1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td> </td></tr><tr><td><code>campagne</code></td><td> </td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>campaign_type</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Remarque (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Remarque (1)</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td colspan="2"> <strong>Remarque</strong><br/>(1) Oath prend en charge le partage des coûts mais il transmet les données de coûts en masse, et non via les données de conversion.</td></tr></tbody></table>

</Tab>
</Tabs>

<div id="ua-conversion-with-other-ad-networks" />

## Conversion UA avec les autres réseaux publicitaires

Pour les autres réseaux publicitaires, les données de la charge utile découlent directement des <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">paramètres inscrits dans le lien d'attribution.</Anchor>

Examinez les charges utiles JSON suivantes.

**Attention !** Les données de conversion sont renvoyées sous forme de carte. Le développeur **n'interagit pas avec le JSON brut**.

<div id="applovin" />

<Accordion title="Applovin">

<div id="attribution-link" />

#### Lien d'attribution :

```http HTTPS
https://app.appsflyer.com/com.company.app?af_ad=ad_name&af_ad_type=INTER
  &af_channel=video&af_siteid=123_site_id&af_c_id=b8******************************&
  af_adset=_DEFAULT&pid=applovin_int&c=campaign_name
  &af_click_lookback=7d&clickid=10****************
  &advertising_id=50********************************&af_ip=
```

<div id="payload" />

#### Charge utile :

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "applovin_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:49:54.186",
      "adgroup_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-24 14:29:33.738",
      "agency": null,
      "cost_cents_USD": "0",
      "af_ad_type": "INTER",
      "af_c_id": "b8******************************",
      "adset": null,
      "advertising_id": "50********************************",
      "af_sub1": null,
      "clickid": "10****************",
      "af_click_lookback": "7d",
      "af_siteid": "123_site_id",
      "af_ad": "ad_name",
      "http_referrer": null,
      "af_channel": "video",
      "af_adset": "_DEFAULT",
      "af_sub5": null,
      "af_sub4": null,
      "af_cpi": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* Les paramètres du lien d'attribution apparaissent sous forme de champs dans la charge utile.
* Les autres champs de la charge utile **qui ne sont pas dans le lien d'attribution** portent une valeur nulle.
* AppLovin prend en charge le partage des coûts publicitaires, mais transmet en masse les données de coûts à AppsFlyer. Les champs liés aux coûts indiquent la valeur 0.

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

<div id="attribution-link-1" />

#### Lien d'attribution :

```http HTTPS
https://app.appsflyer.com/id123456789?
  af_ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &clickid=ab*******************&redirect=false
  &ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &af_lang=pt&imei=&af_sub1=&advertising_id=&af_ip=192.168.0.1&pid=ironsource_int
  &device_ip=192.168.0.1&c=campaign_name
  &idfa=01**********************************&af_siteid=123_site_id&
  af_enc_data=cN*********************************************************************
```

<div id="payload-1" />

#### Charge utile :

```json
{
      "adgroup": null,
      "af_enc_data": "cN**************************************************************************************",
      "campaign": "campaign_name",
      "media_source": "ironsource_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:59:32.194",
      "adgroup_id": null,
      "redirect": "false",
      "orig_cost": "0.75",
      "click_time": "2018-12-30 23:58:54.517",
     "agency": null,
      "cost_cents_USD": "75",
      "adset": null,
      "advertising_id": "35**********************************",
      "af_sub1": null,
      "af_ip": "192.168.0.1",
      "clickid": "ab*******************",
      "af_sub3": null,
      "af_cost_value": "0.75",
      "af_ref": "ironsource_5f******************************************",
      "af_siteid": "123_site_id",
      "http_referrer": null,
      "af_cost_model": "cpi",
      "af_ua": "Mozilla/5.0 (Linux; Android 8.0.0; SM-N950F Build/R16NW; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/71.0.3578.99 Mobile Safari/537.36",
      "af_cost_currency": "USD",
      "af_sub5": null,
      "af_sub4": null,
      "af_lang": "en",
      "af_cpi": null,
      "af_click_lookback": "7d",
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

ironSource transmet les données de coûts à AppsFlyer lors de la conversion via les champs `orig_cost`, `costs_cents_USD`, et `af_cost_value`.

Cependant, les données de coûts **n'apparaissent pas dans le lien d'attribution**. ironSource crypte les données de coûts et les enregistre dans le champ `af_enc_data`.

</Accordion>

<div id="tip" />

<div id="retargeting-conversion-data" />

## Données de conversion pour le retargeting

Le retargeting comprend deux types de conversions : la réattribution ou le réengagement.

> 👍 **Astuce**
>
> Les données de conversion pour le retargeting n'indiquent pas toujours clairement le type de conversion. Cf [Autres sources de données de conversion](#autres-sources-de-données-de-conversion).

<div id="note" />

<div id="re-attribution-with-srns" />

### Réattribution avec les SRN

Lorsqu'un utilisateur est réattribué via un SRN, la charge utile des données de conversion n'indique pas qu'il s'agit d'une campagne de retargeting. Comme les SRN n'utilisent pas de liens d'attribution, il n'est pas possible de définir de paramètre `is_retargeting=true` dans le lien d'attribution. Pour les **SRN qui prennent en charge le retargeting**, AppsFlyer détermine si l'utilisateur doit être réattribué ou non.

Il n'y a donc aucun moyen au niveau du SDK pour savoir si une installation provient d'une campagne de retargeting. Le seul moyen possible est de définir le nom de la campagne pour qu'il indique que c'est une campagne de retargeting.

> 📘 **Remarque**
>
> Définir le nom de la campagne de manière à ce qu'il indique un retargeting **n'est pas une méthode infaillible**. Cf [ces exemples pour en savoir plus](#exemples-dacquisition-utilisateur-et-de-réattribution-mélangées).

<div id="re-attribution-with-regular-ad-networks" />

### Réattribution avec les réseaux publicitaires classiques

L'attribution aux réseaux publicitaires repose sur les liens d'attribution. Qu'il s'agisse de liens d'attribution ordinaires ou de OneLink, avec le retargeting le lien d'attribution comporte toujours le paramètre `is_retargeting=true`.

<div id="retargeting-campaign-with-criteo" />

<Accordion title="Campagne de retargeting avec Criteo">

<div id="attribution-link-2" />

#### Lien d'attribution

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
 c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
 & af_reengagement_window=30d
```

<div id="conversion-data-payload" />

#### Charge utile de données de conversion

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "criteo_int",
      "retargeting_conversion_type": "re-attribution",
      "adset_id": null,
      "campaign_id": null,
      "af_reengagement_window": "30d",
      "install_time": "2018-12-01 23:13:03.126",
      "adgroup_id": null,
      "redirect": "false",
      "af_sub5": null,
      "click_time": "2018-11-18 20:02:31.559",
      "agency": null,
      "cost_cents_USD": "0",
      "is_retargeting": "true",
      "af_cpi": null,
      "af_click_lookback": "30d",
      "af_siteid": null,
      "idfa": "68**********************************",
      "http_referrer": null,
      "orig_cost": "0.0",
      "af_sub4": null,
      "adset": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* Paramètre `retargeting_conversion_type` - ce paramètre indique le type de retargeting. Peut être une réattribution, un réengagement, ou aucun des deux.
* Paramètre `is_retargeting : true` - ce paramètre indique que l'installation est une installation réattribuée
* `af_reengagement_window`: la fenêtre d'attribution du réengagement correspond au nombre de jours au cours durant lequel un événement peut être attribué à un **utilisateur réengagé**. Comme il s'agit d'une conversion de réattribution, ce paramètre est redondant.

</Accordion>

<div id="re-attribution-with-deferred-deep-linking" />

### Réattribution avec deep linking différé

En général, vous cherchez à deep linker des utilisateurs réattribués qui, par définition, n'ont pas installé l'application. Par exemple, vous mettez en place une campagne qui vise à faire revenir les utilisateurs qui ont désinstallé l'application. La campagne fait la promotion d'un produit ou d'un service et vous souhaitez proposer aux utilisateurs un contenu relatif à ce même produit ou service.

C'est ce qu'on appelle le Deep Linking différé. La charge utile des données de conversion pour le Deep Linking différé est issue de la méthode `onConversionDataSuccess`.

<div id="deferred-deep-linking-with-srns" />

<Accordion title="Deferred Deep Linking avec des SRN">

Les paramètres de Deep Link définis dans les campagnes SRN ne sont pas disponibles en dehors du SRN. Il le paramètre `af_dp`, qui contient le chemin du schéma dans l'application. La seule exception à cette règle est lorsque vous utilisez les <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#utilisation-du-deep-linking-différé-dans-les-campagnes-dapp">campagnes Google App dans Feeds</Anchor>. Pour installer le deep linking différé, une autre logique s'applique aux campagnes SRN. Vous devez utiliser les données de la réponse `onConversionSuccess`, comme la campagne, l'adset, l'adgroup, pour rediriger par programme vos utilisateurs.

<div id="note-1" />

<div id="conversion-data-for-deferred-deep-linking-with-meta-ads" />

#### Données de conversion pour le deep linking différé avec Meta ads

<Tabs>
<Tab title="Android">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"Non-organic",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

</Tab>

<Tab title="iOS">

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,  
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

</Tab>
</Tabs>

Vous pouvez utiliser les données de la réponse getConversionData (comme la campagne, l'adset, etc.) pour rediriger par programme vos utilisateurs et leur proposer un contenu qui suscitera leur intérêt.

> 📄 **Exemple**
>
> L'application est une app de eCommerce spécialisée dans les vêtements de sport. Un utilisateur qui n'a pas encore installé l'app s'engage avec une publicité et installe l'application. Une fois l'app lancée, le SDK transmet les données de conversion. Le développeur fait en sorte que l'app ouvre l'activité **collection de chaussures de course d'été** (campagne) dans le store, et propose la catégorie **chaussures de course pour femmes** (adset).

</Accordion>

<div id="deferred-deep-linking-with-attribution-links" />

<Accordion title="Deep linking différé avec liens d'attribution">

Il existe trois façons de créer des deep links pour les utilisateurs :

<div id="uri-schemes" />

#### Schémas d'URI

Avec les schémas URI, tant pour les liens d'attribution que pour OneLink, le lien d'attribution et les données utiles sont les suivants :

**Lien d'attribution**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**Le lien profond universel OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
 https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**Charge utile**

```json
{
      "af_deeplink": true,
      "campaign": "campaign_name",
      "media_source": "media_source_name",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-30 23:59:09",
      "install_time": "2018-12-30 23:59:39.330",
      "agency": null,
      "cost_cents_USD": "0",
      "adset": "AD_SET_NAME",
      "ad_id": "AD_ID",
      "af_siteid": null,
      "http_referrer": null,
      "af_cpi": null,
      "af_sub5": null,
      "af_sub4": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink : true` - lorsque ce paramètre apparaît et qu'il est défini sur *true*, recherchez les champs `scheme` et `host`
* `scheme` et `host` - ces champs découlent du paramètre `af_dp` du lien d'attribution, ils indiquent le schéma et l'activité vers lesquels l'utilisateur doit être deep linké.

<div id="note-2" />

<div id="important" />

<div id="ios-universal-links-and-android-app-links" />

#### Liens universels iOS et liens vers les apps Android

Ce sont les deux autres moyens pour actionner le deep linking.

Lorsque vous utilisez des liens universels ou des liens d'app, le OneLink et la charge utile sont les suivants :

**Le lien profond universel OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
 https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**Charge utile**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "Non-organic",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* `champ shortlink` - il s'agit du champ qui indique le OneLink d'où provient l'utilisateur. Il permet au développeur de savoir comment procéder pour lancer une activité et proposer du contenu. D'autres champs, comme `campaign`, peuvent être utilisés dans le même but.

  > 🚧 **Important !**
  >
  > Le champ `shortlink` n'apparaît pas dans la charge utile avec l'utilisation d'un long OneLink.
  >
  > Dans les deux cas (OneLink court ou long), nous recommandons d'ajouter un paramètre personnalisé qui indiquera l'activité. Par exemple `&deep_link_activity=shoes_cateogry`


> 📘 **Remarque**
>
> L'utilisation de liens universels et des liens d'app n'est possible qu'avec OneLink.

</Accordion>

<div id="re-engagement-with-srns" />

### Réengagement avec les SRN

Comme pour les campagnes de réattribution, lorsqu'un utilisateur est réattribué via un SRN, les données de conversion n'indiquent pas qu'il s'agit d'une campagne de ré-engagement. Vous pouvez définir le nom de la campagne pour qu'il indique qu'il s'agit d'une campagne de ré-engagement.

<div id="re-engagement-with-regular-ad-networks" />

### Ré-engagement avec les réseaux publicitaires classiques

Ici aussi, la charge utile des données de conversion n'indique pas que l'utilisateur provient d'une campagne de ré-engagement. Pour pallier ce problème, vous pouvez donner un nom à la campagne qui indique que c'est une campagne de ré-engagement.

<div id="re-engagement-with-deep-linking" />

### Réengagement via le deep linking

La principale fonction du ré-engagement est d'envoyer l'utilisateur à un endroit précis. Par exemple la publicité pour un produit ou une promotion. Dans ce cas, vous voudrez envoyer les utilisateurs qui ont cliqué sur la publicité directement vers l'activité de l'application qui concerne ce produit ou cette promotion.

Pour ce faire, vous passez par le Deep Linking. Les données de conversion dans le Deep Linking sont très importantes. Elles contiennent les informations qui permettent au développeur de personnaliser l'expérience de l'utilisateur et le diriger vers la bonne activité.

<div id="reengagement-deep-linking-with-srns" />

<Accordion title="Ré-engagement : deep linking avec les SRN">

Les données de conversion ne sont pas disponibles lorsqu'un utilisateur ré-engagé provient d'un SRN. Le développeur doit utiliser les méthodes du SRN pour les obtenir au moment où l'application est lancée.

</Accordion>

<div id="reengagement-deep-linking-with-ad-networks" />

<Accordion title="Ré-engagement : deep linking avec les réseaux publicitaires">

Lorsqu'un utilisateur est ré-engagé et que l'app est lancée, les données de conversion suivantes sont disponibles dans la méthode `onAppOpenAttribution` :

Sous iOS comme Android, en cas d'utilisation de la version courte du OneLink, les données de conversion s'affichent sous la forme d'une carte avec l'ensemble des paramètres du lien :

Exemple :

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* Le développeur d'app peut utiliser ces paramètres, comme `af_dp` ou le nom de la campagne, pour envoyer l'utilisateur vers une activité précise, et lui proposer le contenu correspondant.

<div id="important-1" />

> 🚧 **Important !**
>
> Nous vous recommandons d'utiliser la version courte du OneLink. Cliquez <Anchor target="_blank" href="/marketers/fr/docs/understand-onelink-short-vs-long-urls">ici</Anchor> pour en savoir plus.

Une autre des raisons qui fait qu'il vaut mieux utiliser la version courte du OneLink, c'est la structure des données de conversion renvoyée par la version longue. Avec la version longue, les données de conversion s'affichent sous forme de carte avec un champ unique appelé `link` et qui contient l'intégralité du OneLink long.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

<div id="alternative-conversion-data-sources" />

### Autres sources de données de conversion

* API Push offre une charge utile de conversion détaillée qui stipule la réattribution ou le ré-engagement. Les charges utiles de l'API Push comprennent un champ appelé `re_targeting_conversion_type`. Ce champ indique le type de conversion, réattribution ou réengagement. Pour en savoir plus, consultez notre guide sur <Anchor target="_blank" href="/marketers/fr/docs/push-api-streaming-raw-data">l'API Push</Anchor>.
* Les rapports de données brutes contiennent également des indicateurs pour le type de conversion. Dans le rapport de données brutes pour les conversions de retargeting, il se trouve une colonne ***Nom de l'événement***. La valeur de cette colonne est soit **reengagement** soit ***reattribution*** en fonction du type de conversion.

<div id="note-3" />

<div id="examples-of-mixed-user-acquisition-and-re-attribution" />

### Exemples d'acquisition utilisateur et de réattribution mélangées

> 📄
>
> 1. Un utilisateur installe votre application, puis la désinstalle. L'installation place l'utilisateur dans une <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">fenêtre de réattribution.</Anchor> Vous avez mis en place une campagne d'acquisition d'utilisateurs (et non de retargeting) dans Meta ads. Vous avez également paramétré l'intégration d'AppsFlyer avec Facebook pour autoriser le retargeting.
>
>    Alors qu'il se trouve toujours dans la fenêtre de réattribution, l'utilisateur voit la publicité, clique dessus et réinstalle l'application. Pour AppsFlyer, l'utilisateur est un utilisateur réattribué.
>
>    Cela repose sur deux choses :
>    1. La configuration avec Meta ads autorise le retargeting
>    2. L'utilisateur se trouve dans la fenêtre de réattribution
>    Dans ce cas, le nom de la campagne n'indique pas la réattribution.
> 2. Prenons le même exemple, mais cette fois, l'utilisateur se trouve en dehors de la fenêtre de réattribution. Dans ce cas, l'installation sera une nouvelle installation non organique.
> 3. Prenons un autre exemple. Vous avez mis en place une campagne de retargeting sur Meta ads. Certains utilisateurs tombent sur la campagne et installent l'application. Cependant, ces utilisateurs installent l'application pour la première fois. Ces utilisateurs ne sont donc pas considérés comme des utilisateurs réattribués. AppsFlyer les considère par contre comme des utilisateurs issus d'une campagne d'acquisition d'utilisateurs.

<div data-zendesk-anchors="overview=pr%C3%A9sentation h_01HCY86CKDJK9TNHPAZB0QX2ZX=pr%C3%A9sentation nonorganic-conversion-data-payload-fields=champs-de-charge-utile-des-donn%C3%A9es-conversion-non-organique h_01HCY86CKDEMB3428YHCNJQA5R=champs-de-charge-utile-des-donn%C3%A9es-conversion-non-organique fields-always-available=champs-toujours-propos%C3%A9s h_01HCY86CKDBQRGAY7GHNBJE4WK=champs-toujours-propos%C3%A9s fields-available-in-some-cases=champs-propos%C3%A9s-dans-certains-cas h_01HCY86CKDYQMYB9BQ4MXWP8A5=champs-propos%C3%A9s-dans-certains-cas additional-fields=champs-suppl%C3%A9mentaires h_01HCY86CKD47M85AZVEA5C4JH7=champs-suppl%C3%A9mentaires limitations=restrictions h_01HCY86CKEFX646H9BSKSFGZ36=restrictions h_01HCY86CKEZ2483XB461M2C9EC=custom-parameter-names ua-conversion-data-with-srns=donn%C3%A9es-de-conversion-ua-avec-les-srn h_01EGKTQN6XDYHA60P2WKHBBVFT=donn%C3%A9es-de-conversion-ua-avec-les-srn a-note-about-facebook=un-point-sur-meta-ads h_01HCY86CKENFEGX53G9G4SGPSK=un-point-sur-meta-ads facebook-conversion-data=donn%C3%A9es-de-conversion-meta-ads h_01HCY86CKE658H36F3VJQMATQK=donn%C3%A9es-de-conversion-meta-ads h_01HCY86CKF6FY96PAWB5Y7YXSQ=google-ads-conversion-data h_01HCY86CKFMNNNJZTPGK4870YN=apple-search-ads-conversion-data h_01HCY86CKFS5SJBECSY42VRJWP=oath-ad-platforms-conversion-data ua-conversion-with-other-ad-networks=conversion-ua-avec-les-autres-r%C3%A9seaux-publicitaires h_01HCY86CKFB0GEJRTYSXN9YZ08=conversion-ua-avec-les-autres-r%C3%A9seaux-publicitaires h_01HCY86CKFY787RD4BHQDVEVFV=applovin attribution-link=lien-dattribution- h_01HCY86CKFXM5XXJZSPXPB6397=lien-dattribution- payload=charge-utile- h_01HCY86CKFDDXWT2KKFTKKBGHM=charge-utile- h_01HCY86CKFV55GYY7C51D7F72S=ironsource attribution-link::a45a1b4a=lien-dattribution--1 h_01HCY86CKFYGEYR2TRPSD87KDA=lien-dattribution--1 payload::81867f5c=charge-utile--1 h_01HCY86CKFKKFQDG1P42R1FSDJ=charge-utile--1 retargeting-conversion-data=donn%C3%A9es-de-conversion-pour-le-retargeting h_01EHQ74JS84509GT6M93SZA4HX=donn%C3%A9es-de-conversion-pour-le-retargeting h_01HCY86CKFP0DWCFMKSB1V130D=astuce reattribution-with-srns=r%C3%A9attribution-avec-les-srn h_01HCY86CKFAVWP1W0ZNEN5P30A=r%C3%A9attribution-avec-les-srn h_01HCY86CKF2QY9DV1J9MWHKJ5P=remarque reattribution-with-regular-ad-networks=r%C3%A9attribution-avec-les-r%C3%A9seaux-publicitaires-classiques h_01HCY86CKF1PV8MRR902RAHQGW=r%C3%A9attribution-avec-les-r%C3%A9seaux-publicitaires-classiques h_01HCY86CKF1RGK01VTV3EEHQVM=retargeting-campaign-with-criteo attribution-link::c16e96bb=lien-dattribution h_01HCY86CKFSKBBMFKA8NN8XTPC=lien-dattribution conversion-data-payload=charge-utile-de-donn%C3%A9es-de-conversion h_01HCY86CKG2YQQC629SC3RAFKE=charge-utile-de-donn%C3%A9es-de-conversion reattribution-with-deferred-deep-linking=r%C3%A9attribution-avec-deep-linking-diff%C3%A9r%C3%A9 h_01HCY86CKGXV50H79R0YH1GB2C=r%C3%A9attribution-avec-deep-linking-diff%C3%A9r%C3%A9 h_01HCY86CKG12YRGFEEJ27DQART=deferred-deep-linking-with-srns conversion-data-for-deferred-deep-linking-with-facebook=donn%C3%A9es-de-conversion-pour-le-deep-linking-diff%C3%A9r%C3%A9-avec-meta-ads h_01HCY86CKGX9VHSV3ASKXMFM0X=donn%C3%A9es-de-conversion-pour-le-deep-linking-diff%C3%A9r%C3%A9-avec-meta-ads h_01HCY86CKGHM9FKBEHMYBF4597=exemple h_01HCY86CKG3XWM4X0YH7WYCEH4=deferred-deep-linking-with-attribution-links uri-schemes=sch%C3%A9mas-duri h_01HCY86CKGDM2NE1FCRC92K8R0=sch%C3%A9mas-duri ios-universal-links-and-android-app-links=liens-universels-ios-et-liens-vers-les-apps-android h_01HCY86CKGY1NE4214DES0Y2AV=liens-universels-ios-et-liens-vers-les-apps-android h_01HCY86CKG1NGYR8WCS7NMM782=important- h_01HCY86CKG9VF8MBJQTWJGDJ6Z=remarque-1 reengagement-with-srns=r%C3%A9engagement-avec-les-srn h_01HCY86CKG4TRYR6TWYYVB0FJE=r%C3%A9engagement-avec-les-srn reengagement-with-regular-ad-networks=r%C3%A9-engagement-avec-les-r%C3%A9seaux-publicitaires-classiques h_01HCY86CKGM2JS7C9T71R6GPH1=r%C3%A9-engagement-avec-les-r%C3%A9seaux-publicitaires-classiques reengagement-with-deep-linking=r%C3%A9engagement-via-le-deep-linking h_01HCY86CKG0NPQAA2ZRWWNKGQD=r%C3%A9engagement-via-le-deep-linking h_01HCY86CKGEBHQVFRGJH96KDFJ=reengagement-deep-linking-with-srns h_01HCY86CKGJ9HG7AGB5MFP33RK=reengagement-deep-linking-with-ad-networks h_01HCY86CKGC3AF6YDKTY95XMV5=important--1 alternative-conversion-data-sources=autres-sources-de-donn%C3%A9es-de-conversion h_01HCY86CKG3N6ZXV70G4VMZ0X5=autres-sources-de-donn%C3%A9es-de-conversion examples-of-mixed-user-acquisition-and-reattribution=exemples-dacquisition-utilisateur-et-de-r%C3%A9attribution-m%C3%A9lang%C3%A9es h_01HCY86CKGK9DVVB7T6CVNB8ZN=exemples-dacquisition-utilisateur-et-de-r%C3%A9attribution-m%C3%A9lang%C3%A9es" />
