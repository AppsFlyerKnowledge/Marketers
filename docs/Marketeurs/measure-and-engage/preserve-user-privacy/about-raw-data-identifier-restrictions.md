---
title: >-
  Restriction du contenu des données brutes - identifiants utilisateur ou source
  du média
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2020-03-23T08:29:01Z'
  edited_at: '2023-11-27T12:39:32Z'
  id: 360006868017
  locale: fr
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/fr/articles/360006868017
---
> **En bref :** dans certains rapports de données brutes, les champs sont restreints pour des raisons de confidentialité. Dans d'autres cas, les partenaires exigent que la source média soit retirée lorsqu'ils transmettent les données à des plateformes tierces. Cet article vous détaille ces restrictions et leurs effets.

<div id="raw-data-restriction" />

## Restriction des données brutes

AppsFlyer limite la présence de certains champs dans les rapports de données brutes afin de respecter la vie privée des utilisateurs. Cette action se conforme aux paramètres <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">AAP</Anchor> des annonceurs, ainsi qu'aux politiques de partage des données des réseaux publicitaires qui fournissent les données. Les restrictions diffèrent selon le type de rapport et leur cadre d'application.Les restrictions concernent les données brutes émises par des <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">outils de diffusion des données brutes.</Anchor>

<div id="media-source-restrictions" />

### Restrictions des sources média

Le tableau suivant répertorie les restrictions pour chaque source média.

<div id="note" />

> 📘 **Remarque**
>
> * Les données agrégées et analytiques de la plateforme AppsFlyer sont accessibles sans restriction.
> * <Anchor target="_blank" href="/marketers/fr/docs/discrepancies-between-appsflyer-and-third-party-platforms">Restrictions concernant les postbacks sur les plateformes tierces</Anchor>
>   * Les postbacks des événements limités par les sources média, tels que décrits dans le tableau ci-dessous, **ne sont pas envoyés aux plateformes tierces** (comme les plateformes d'analyse ou de marketing).
>   * D'autres restrictions de postback peuvent s'appliquer pour certains événements

| Source média | Restriction du type d'attribution |
| --- | --- |
| <span id="meta-ads"></span>Meta Ads | <ul><li>Jusqu'au 28 octobre 2021 : post-vue</li><li>Depuis le 29 octobre 2021 : post-clic et post-vue. Cependant, si vous activez le procédé de référent d'installation Google Play, certaines données de clics sont accessibles. Notez que le référent d'installation Google Play ne s'applique pas aux campagnes de retargeting, et qu'il est disponible sans aucune restriction.</li><li>**Exception :** toutes les données d'<Anchor target="_blank" href="/marketers/fr/docs/meta-ads-integration-setup#app-aem-for-reengagement">attribution de réengagement de deep linking</Anchor> sont mentionnées dans les rapports sans limitation.</li></ul> |
| <span id="pinterest"></span>Pinterest | À compter du 4 septembre 2023 : attribution post clic et post vue |
| <span id="roku-oneview"></span>Roku OneView | Post-clic et post-vue sur toutes les plateformes (CTV et mobile) |
| <span id="samsung-dsp"></span>Samsung DSP | Depuis le 17 octobre 2021, l'attribution post vue et post clic est soumise à limitation.Les champs suivants **sont renseignés** dans les outils de transmission des données brutes :<ul><li>Source média (samsungdsp\_int)</li><li>Canal</li><li>Type de touche d'attribution</li><li>Temps de touch attribué</li><li>Détails de la campagne : nom de la campagne, ID de la campagne, nom d'adset, ID d'adset, nom de la publicité et ID de la publicité.</li></ul> |
| <span id="snapchat"></span>Snapchat | <ul><li>Depuis le 1er mars 2023, les désinstallations de Snapchat ne sont pas incluses dans les rapports de données brutes.</li><li>Depuis le 13 septembre 2023, l'attribution post-vue est soumise à limitation. Les champs suivants **sont renseignés** dans les outils de transmission des données brutes :<ul><li>Source média (snapchat\_int)</li><li>Canal</li><li>Type de touch attribué (impression)</li><li>Date de touch attribué (date uniquement - « jj/mm/aaaa »)</li><li>La campagne est marquée comme « *restreinte* »</li></ul></li></ul> |
| <span id="tiktok-for-business"></span>TikTok pour les entreprises | <ul><li>Entre le 28 juillet 2021 et le 23 octobre 2021, la consultation des données d'attribution post-vue est restreinte.</li><li>Depuis le 23 octobre 2021, l'attribution post-vue est soumise à limitation. Les champs suivants **sont renseignés** dans les outils de transmission des données brutes :<ul><li>Source média (bytedanceglobal\_int et tiktokglobal\_int)</li><li>Canal</li><li>Type de touch attribué (impression)</li><li>Date de touch attribué (date uniquement - « jj/mm/aaaa »)</li><li>La campagne est marquée comme « *restreinte* »</li></ul></li></ul> |
| <span id="twitter"></span>Twitter | Dans certains cas, Twitter refuse la mise à disposition des données brutes sur la plateforme AppsFlyer. Lorsque cela se produit, les événements n'apparaissent pas dans les rapports de données brutes. |

<div id="raw-data-context" />

### Contexte des données brutes

Les champs des données brutes sont restreints en fonction du cadre d'obtention des données, comme indiqué dans le tableau suivant.

| Type de restriction | Rapports affectés |
| --- | --- |
| [Source média restreinte](/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média) : d'où est issu l'utilisateur | <ul><li>Attribution : installations, conversions de retargeting, désinstallations</li><li>Événements in-app, sessions</li><li>Rapports Protect360</li></ul> |
| Restriction absolue | <ul><li>Clics</li><li>Impressions</li><li>Clics bloqués (Protect360)</li></ul> |

**Livraison des données brutes**

Dans AppsFlyer, les données d'attribution de niveau utilisateur sont fournies par les outils de livraison des données brutes suivants :

* Data Locker
* API Pull de données brutes
* API push
* Page d'exportation du dashboard
* Postbacks envoyés aux réseaux
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">Obtenir l'API de données de conversion (GCD)</Anchor> dans le cadre de l'API de données de niveau utilisateur côté client

<div id="unavailable-attribution-fields" />

<Accordion title="Champs d'attribution non disponibles">

Les champs suivants ne sont pas disponibles lorsque la source média est restreinte :

| Nom d'affichage | Nom de l'API |
| --- | --- |
| Publicité | af\_ad |
| Identifiant de publicité | af\_ad\_id |
| Type de publicité | af\_ad\_type |
| Ensemble de publicités | af\_adset |
| Identifiant de l'ensemble de publicités | af\_adset\_id |
| Fenêtre d'attribution rétrospective | af\_attribution\_lookback |
| Identifiant de la campagne | af\_c\_id |
| Canal | af\_channel |
| Devise des coûts | af\_cost\_currency |
| Modèle de coût | af\_cost\_model |
| Valeur des coûts | af\_cost\_value |
| Mots-clés | af\_keywords |
| Partenaire | af\_prt |
| ID site | af\_siteid |
| Identifiant du sous-site | af\_sub\_siteid |
| Sous-paramètre [n] (n=1-5) | af\_sub[n] (n=1-5) |
| Temps de touch attribué | attributed\_touch\_time |
| Type de touche d'attribution | attributed\_touch\_type |
| Campagne | campagne |
| Source média (n=1-3) du contributeur [n] | contributor[n]\_media\_source (n=1-3) |
| Partenaire (n=1-3) du contributeur [n] | contributor[n]\_af\_prt  <br />(n=1-3) |
| Campagne du contributeur [n] (n=1-3) | contributor[n]\_campaign  <br />(n=1-3) |
| Type de correspondance (n=1-3) du contributeur [n] | contributor[n]\_match\_type (n=1-3) |
| Heure de touch (n=1-3) du contributeur [n] | contributor[n]\_touch\_time  <br />(n=1-3) |
| Type de touch (n=1-3) du contributeur [n] | contributor[n]\_touch\_type  <br />(n=1-3) |
| URL de deep link | deeplink\_url |
| Référent HTTP | http\_referrer |
| App store d'installation | install\_app\_store |
| ID de mot clé | keyword\_id |
| Type de correspondance de mots-clés | keyword\_match\_type |
| Type de correspondance | match\_type |
| ID de compte réseau | network\_account\_id |
| URL d'origine | original\_url |
| Fenêtre de réengagement | af\_reengagement\_window |
| Page du produit du store | store\_product\_page |

</Accordion>

<div id="identifier-restriction" />

<Accordion title="Restriction de l'identifiant">

Lorsque la restriction d'identifiant s'applique, les champs listés dans le tableau suivant sont les seuls proposés dans les rapports de données brutes.

| Nom de l'API |
| --- |
| <span id="event_time"></span>event\_time |
| <span id="event_name"></span>event\_name |
| <span id="event_revenue"></span>event\_revenue |
| <span id="event_revenue_currency"></span>event\_revenue\_currency |
| <span id="event_revenue_usd"></span>event\_revenue\_usd |
| <span id="af_cost_model"></span>af\_cost\_model |
| <span id="af_cost_value"></span>af\_cost\_value |
| <span id="af_cost_currency"></span>af\_cost\_currency |
| <span id="event_source"></span>event\_source |
| <span id="media_source"></span>media\_source |
| <span id="af_channel"></span>af\_channel |
| <span id="campaign"></span>campagne |
| <span id="af_c_id"></span>af\_c\_id |
| <span id="af_adset"></span>af\_adset |
| <span id="af_adset_id"></span>af\_adset\_id |
| <span id="af_ad"></span>af\_ad |
| <span id="af_ad_id"></span>af\_ad\_id |
| <span id="af_ad_type"></span>af\_ad\_type |
| <span id="af_siteid"></span>af\_siteid |
| <span id="af_sub_siteid"></span>af\_sub\_siteid |
| <span id="app_id"></span>app\_id |
| <span id="app_name"></span>app\_name |
| <span id="bundle_id"></span>bundle\_id |
| <span id="is_retargeting"></span>is\_retargeting |
| <span id="retargeting_conversion_type"></span>retargeting\_conversion\_type |
| <span id="is_primary_attribution"></span>is\_primary\_attribution |
| <span id="af_attribution_lookback"></span>af\_attribution\_lookback |
| <span id="af_reengagement_window"></span>af\_reengagement\_window |
| <span id="country_code"></span>country\_code |
| <span id="blocked_reason"></span>blocked\_reason |
| <span id="blocked_reason_value"></span>blocked\_reason\_value |
| <span id="blocked_reason_rule"></span>blocked\_reason\_rule |
| <span id="blocked_sub_reason"></span>blocked\_sub\_reason |
| <span id="platform"></span>platform |
| <span id="is_paid_media"></span>is\_paid\_media |

</Accordion>

## FAQ

<div id="what-events-are-restricted" />

<Accordion title="Quels sont les événements soumis à restrictions ?">

Les événements restreints, tels que détaillés dans le [tableau ci-dessus](/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média), peuvent inclure des conversions (installations et réengagements) et événements in-app associés auxquels le réseau publicitaire restrictif est attribué.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-raw-data-reports" />

<Accordion title="En quoi une source média restreinte modifie-t-elle les rapports de données brutes ?">

* Dans le champ *source media* est inscrit *restricted* (restreinte).
* Les champs d'attribution énumérés dans cet article sont soit laissés vides, soit remplis par *null*.

**Exemple de rapport** : <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv">données brutes restreintes</Anchor> des installations dans un fichier CSV. Les autres rapports de données brutes sont remplis de la même manière.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-postbacks-sent-to-partners" />

<div id="what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted" />

<Accordion title="En quoi une source média restreinte modifie-t-elle les postbacks envoyés aux partenaires ?">

Les postbacks envoyés aux partenaires n'incluent pas les champs d'attribution.

</Accordion>

<div id="how-do-restricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="En quoi un évènement restreint modifie-t-il les postbacks envoyés aux plateformes tierces ?">

Les postbacks destinés aux réseaux publicitaires attribués listés dans le [tableau ci-dessus](/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média) ne sont pas envoyées aux plateformes tierces.

</Accordion>

<div id="do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="En quoi un évènement non restreint modifie-t-il les postbacks envoyés aux plateformes tierces ?">

[Dans certains cas](/docs/about-raw-data-identifier-restrictions#media-source-sharing-limitations-on-thirdparty-platforms), les postbacks non restreints envoyés à des plateformes tierces n'incluent pas la source média. Cela signifie que l'attribution est considérée comme organique.

</Accordion>

<div id="what-about-the-data-of-assists-that-form-part-of-the-attribution" />

<Accordion title="Qu'en est-il des données propres aux assistances inclues dans l'attribution ?">

Les données des *assistances* sont considérées comme des données d'attribution et ne sont donc pas disponibles.

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> <Anchor target="_blank" href="/marketers/fr/docs/user-level-data-retention">Rétention des données de niveau utilisateur</Anchor>

<div data-zendesk-anchors="raw-data-restriction=restriction-des-donn%C3%A9es-brutes 01H7WQHTV9RM2JF2BV45XF626H=restriction-des-donn%C3%A9es-brutes media-source-restrictions=restrictions-des-sources-m%C3%A9dia 01H7WQHTV9HJEHHH1N8VN6APX6=restrictions-des-sources-m%C3%A9dia 01H7WQHTV90YFRP3Z9AEP7ACRD=remarque raw-data-context=contexte-des-donn%C3%A9es-brutes 01H7WQHTVA8H9FTBJ1FB6BJQ2A=contexte-des-donn%C3%A9es-brutes 01H7WQHTVA0XP6B2H95EEM7EYD=unavailable-attribution-fields 01H7WQHTVA7ERWW1PC3DF5H0NP=identifier-restriction 01H7WQHTVA5439QPE6GNXNKJ63=faq h_01HDBND48E05P1WV51ZJGD072N=what-events-are-restricted 01H7WQHTVAHCK7QDZ5P25YRQ2D=how-does-the-restricted-media-source-impact-raw-data-reports 01H7WQHTVABKATP6B6XN4NRC54=what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted h_01HDBND48EDTAFBFXTADGWJADM=how-do-restricted-events-impact-postbacks-to-thirdparty-platforms h_01HE5TK3WSNBPM6W5D1Y9S6PDX=do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms 01H7WQHTVA60PWZ017WJMRTKVP=what-about-the-data-of-assists-that-form-part-of-the-attribution h_01HE7SCVN3VJ4Y6KF2QZSNBEMZ=%C3%A0-consulter-%C3%A9galement" />
