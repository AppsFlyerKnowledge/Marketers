---
title: Liens d'attribution directe pour les plateformes CTV, PC et consoles
metadata:
  keywords:
    - Advertiser
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2023-05-10T10:21:14Z'
  edited_at: '2024-09-20T13:42:33Z'
  id: 15199908310801
  locale: fr
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/fr/articles/15199908310801
---
> **En bref :**  Découvrez la structure et les paramètres des liens d'attribution AppsFlyer pour les plateformes CTV, PC et consoles. **Remarque** : Pour les applications Android et iOS, y compris les jeux PC Android, utilisez les <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">instructions relatives aux liens d'attribution mobile</Anchor>.

<div id="overview" />

## Aperçu

Les liens d'attribution directe pour les plateformes CTV, PC et consoles permettent aux annonceurs de rediriger les utilisateurs et de collecter des données après les clics. Ces liens d'attribution directe sont des liens AppsFlyer qui prennent en charge la redirection et l'attribution **pour une seule application de destination sur une seule plateforme à la fois**. La destination de la redirection est la valeur du paramètre af\_r inclus dans le lien.

**Remarque** : Pour les applications Android et iOS, y compris les jeux PC Android, utilisez les <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">instructions relatives aux liens d'attribution mobile</Anchor>.

Les liens d'attribution peuvent être directement créés par vous-même et placés derrière les publicités. Pour créer de tels liens, suivez les instructions de cet article.

Alternativement, des liens peuvent être créés via S2S en utilisant l'<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_click-app-platform-app-id">API Engagements</Anchor>. Cela nécessite un certain travail de développement. **Remarque** : Les liens créés via S2S peuvent également collecter des données d'impression.

<div id="attribution-link" />

### Lien d'attribution

<table><thead><tr><th colspan="2">Structure du lien d'attribution</th></tr></thead><tbody><tr><td>URL de base</td><td>engagements.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>Paramètres de chemin obligatoires</td><td><ul><li>plateforme<br/>Exemple : steam</li><li>identifiant_application<br/>Exemple : 123456</li></ul></td></tr><tr><td>Paramètres de requête obligatoires</td><td><ul><li>af_media_source</li><li>af_campaign_id</li><li>af_r</li></ul></td></tr><tr><td>Autres paramètres</td><td><a href="./ctv-pc-and-console-platform-direct-attribution-links#paramètres">Voir tous les paramètres</a></td></tr><tr><td>Structure de l'URL</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr><tr><td>Exemple d'URL</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=aloha&amp;af_campaign_id=1234&amp;af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello</code></td></tr></tbody></table>

<div id="parameters" />

### Paramètres

| Paramètre | Nom d'affichage dans l'exportation de données brutes et l'API Pull | Description | Type de champ |
| --- | --- | --- | --- |
| plateforme | Plateforme | <ul><li>Paramètre de chemin spécifiant la plateforme d'application.</li><li>Valeurs possibles :<ul><li>smartcast</li><li>tizen</li><li>roku</li><li>webos</li><li>vidaa</li><li>playstation</li><li>steam</li><li>quest</li><li>battlenet</li><li>epic</li><li>switch</li><li>xbox</li><li>nativepc</li></ul></li></ul> | String |
| identifiant\_application | ID de l'application | <ul><li>Paramètre de chemin qui spécifie l'ID de l'application pour laquelle vous publiez.</li><li>Exemple : ap123456</li></ul> | String |
| af\_media\_source | Source média | Il s'agit de l'identifiant unique du partenaire tel que défini sur la plateforme AppsFlyer.  <br />Les caractères spéciaux suivants ne sont pas autorisés : ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, %. | String |
| af\_campaign | Campagne | Nom de la campagne | String |
| af\_campaign\_id | ID de la campagne | ID de la campagne | String |
| af\_request\_id | N/A | Un identifiant unique pour chaque demande d'un partenaire. | String |
| af\_adset | Adset | Nom de l'adset | String |
| af\_adset\_id | ID de l'adset | ID de l'adset | String |
| af\_ad | Annonce | Nom de l'annonce | String |
| af\_ad\_id | ID de l'annonce | ID de l'annonce | String |
| af\_campaign\_type | Type de campagne | Soit :<ul><li>acquisition\_utilisateur</li><li>reciblage</li></ul> | String |
| af\_prt | Partenaire | <ul><li>Nom de compte d'agence qui permet d'attribuer des installations à l'agence</li><li>**Attention** : N'utilisez pas ce paramètre avant de vérifier que les **autorisations de l'agence** sont activées</li></ul> | String |
| af\_siteid | ID du site | <span id="query-getImpressionAppPlatformApp_id_af_siteid__description"></span>ID unique qui identifie l'éditeur affichant l'annonce | String |
| af\_sub\_siteid | ID du sous-site | <span id="query-getImpressionAppPlatformApp_id_af_sub_siteid__description"></span>ID du sous-réseau/éditeur publicitaire | String |
| af\_click\_id | N/A | <span id="query-getImpressionAppPlatformApp_id_af_click_id__description"></span>Identifiant de transaction unique du réseau publicitaire | String |
| af\_lookback\_window | N/A | <ul><li>Fenêtre de rétrospection pertinente pour l'attribution via une correspondance d'ID.</li><li>Cnombre de jours/heures configurable pour la période d'attribution de la fenêtre de rétrospection. Valeurs disponibles des paramètres : 1j-30j (jours) OU 1h-23h (heures).</li><li>Validation : 3 caractères max, en utilisant le schéma ci-dessus.</li><li>La valeur par défaut est de 24 heures pour les impressions et de 7 jours pour les clics.</li></ul> | String |
| af\_ad\_placement | N/A | <span id="query-getImpressionAppPlatformApp_id_af_ad_placement__description"></span>Identifiant de transaction unique du réseau publicitaire | String |
| af\_ad\_type | Type de publicité | <ul><li>Type de publicité. Utilisez la convention de dénomination suivante :<ul><li>**texte :** une unité publicitaire contenant uniquement du texte, par exemple un résultat de recherche</li><li>**bannière :** un format de base qui apparaît en haut ou en bas de l'écran de l'appareil</li><li>**interstitiel :** une annonce pleine page qui apparaît pendant les pauses dans l'expérience en cours</li><li>**vidéo :** une vidéo classique, qui ne donne pas droit à une récompense</li><li>**vidéo récompensée :** une unité publicitaire offrant des récompenses dans l'application en échange du visionnage d'une vidéo</li><li>**jouable :** une unité publicitaire contenant un aperçu interactif de l'application</li><li>**audio :** une publicité audio</li></ul></li><li>Respect de la casse.</li></ul> | String |
| af\_channel | Canal | <span id="query-getImpressionAppPlatformApp_id_af_channel__description"></span>Le canal de la source média à travers lequel les publicités sont diffusées, par exemple, UAC\_Search, UAC\_Display, Instagram, Meta Audience Network, etc. | String |
| af\_model | Modèle d'appareil | Modèle d'appareil | String 64 |
| af\_os\_version | N/A | <ul><li>Version de l'OS de l'appareil</li><li>Seuls les chiffres et les points sont autorisés</li><li>Exemple : 8.1.0</li></ul> | String |
| af\_device\_id\_type | N/A | <span id="query-getImpressionAppPlatformApp_id_af_device_id_type__description"></span>Type d'identifiant d'appareil Soit :<ul><li>vida</li><li>tifa</li><li>rida</li><li>lgudid</li><li>fire</li><li>advertising\_id</li><li>fire</li><li>personnalisé</li></ul> | String |
| af\_device\_id\_value | N/A | <span id="query-getImpressionAppPlatformApp_id_af_device_id_value__description"></span>Type d'identifiant d'appareil | String |
| af\_r | N/A | <ul><li>Obligatoire</li><li>Contient le lien vers la boutique d'applications ou la page de destination appropriée</li><li>Tout ce qui se trouve dans le paramètre af\_r doit être encodé. Cela inclut toutes les valeurs des paramètres UTM, si elles sont ajoutées.</li></ul> | String |

<div id="traits-and-limitations" />

## Caractéristiques et limitations

| Fenêtre rétrospective | Avec la modélisation probabiliste, une fenêtre rétrospective fixe de 24 heures pour les clics et les impressions est utilisée. La valeur af\_lookback\_window est ignorée. |
| --- | --- |
| Attribution d'agence | <ul><li>Flux CTV-PC-Consoles vers mobile - l'attribution d'agence est prise en charge.</li><li>Flux mobile vers CTV-PC-Consoles - l'attribution d'agence n'est pas prise en charge.</li></ul> |

<div data-zendesk-anchors="overview=aper%C3%A7u 01H7Z1003GTTMRY072BXWDFNP0=aper%C3%A7u attribution-link=lien-dattribution 01H7Z1003G0WYBCK3530064WM1=lien-dattribution attribution-link-parameters=param%C3%A8tres 01H7Z1003GNC551PDCKKFQMPVN=param%C3%A8tres traits-and-limitations=caract%C3%A9ristiques-et-limitations h_01HVED5DJPFR5XCWYDSYCHMCR6=caract%C3%A9ristiques-et-limitations" />
