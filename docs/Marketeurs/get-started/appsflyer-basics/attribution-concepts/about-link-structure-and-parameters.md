---
title: Structure et paramètres des liens d'attribution
metadata:
  keywords:
    - pid
    - Marketers
    - af_
    - af
    - c
    - af_mp
    - clickid
    - af_siteid
    - af_sub_siteid
    - af_c_id
    - af_adset_id
    - af_ad_type
    - af_viewthrough
    - af_cost_model
    - af_cost_value
    - af_web_dp
    - af_ref
    - af_ip
    - af_os_version
    - deep_link_sub
    - deep_link_value
    - af_og_title
    - af_og_description
    - af_og_image
    - af_prt
    - af_adset
    - af_ad
    - af_ad_id
    - af_channel
    - af_keywords
    - af_cost_currency
    - af_sub
    - af_r
    - af_dp
    - af_force_deeplink
    - is_incentivized
    - af_param_forwarding
    - af_partner_account_id
    - af_ua
    - af_os
    - af_model
    - af_media_type
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T11:50:00Z'
  edited_at: '2023-11-20T14:48:33Z'
  id: 207447163
  locale: fr
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/fr/articles/207447163
---
> **En bref** : en savoir plus sur la structure et les paramètres des liens d’attribution.

<div id="important" />

<div id="overview" />

## Présentation

Les liens d'attribution permettent aux annonceurs de récupérer des données concernant l'engagement d'un utilisateur avec une publicité. Les liens d'attribution sont placés à la fin de la publicité, ils renseignent AppsFlyer lorsque un utilisateur interagit avec une publicité. L'engagement peut se faire via un clic sur une publicité ou lorsqu'un utilisateur affiche une impression publicitaire. Une copie de l'URL d'attribution est envoyée à AppsFlyer.

Les liens d’attribution sont générés via **OneLink** ou à partir d'un **lien de plateforme unique**.

|  | OneLink (lien multi-plateforme) | Lien vers une plateforme unique |
| --- | --- | --- |
| Description et utilisation | Vous pouvez l'utiliser quand :<ul><li>Vous voulez obtenir un lien unique pour toutes les plateformes.</li><li>Des capacités de deep linking sont demandées.</li><li>Vous voulez utiliser les liens d'app Android ou des liens universels iOS pour ouvrir l'app.</li></ul><Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">En savoir plus sur OneLink</Anchor> | Vous pouvez l'utiliser quand :<ul><li>Vous n’utilisez qu’une seule plateforme. Ex : Android mais pas iOS.</li><li>Vous utilisez uniquement des schémas d’URI pour ouvrir l’application.</li></ul><Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">En savoir plus sur la configuration d'un partenaire intégré</Anchor> |
| Conditions préalables | <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">Template OneLink</Anchor> | Aucun |
| Informations obligatoires | <ul><li>[Source média](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Campagne](#c)</li><li>[ID de site / sous-site](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <ul><li>[Source média](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Campagne](#c)</li><li>[ID de site / sous-site](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> |
| URL de base | `{subdomain}`.onelink.me | app.appsflyer.com |
| Identifiant unique | ID du template | app\_id |
| Structure de l'URL | `https://{subdomain}.onelink.me/`<br />`{templateid}?pid={media_source}`<br />`&af_siteid={ApplicationID}`<br />`&c={CampaignName}` | `https://app.appsflyer.com/{app_id}?pid={media_source}&af_siteid={ApplicationID}&c={CampaignName}` |
| Exemple | `https://yourbrand.onelink.me/aAB1?pid=greatnetwork_int`<br />`&c=GreatCampaign&af_siteid=A1b1` | `https://app.appsflyer.com/com.greatapp?pid=greatnetwork_int&`<br />`c=GreatCampaign&af_siteid=A1b1` |

<div id="attribution-link-parameters" />

## Paramètres du lien d'attribution

* Les paramètres énumérés sont disponibles pour être utilisés dans le lien d'attribution.
* La valeur dans la colonne **Type de champ** correspond à la limite de caractères de la valeur du paramètre. Pour des informations sur les limites de la longueur des valeurs du paramètre, cliquez <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">ici.</Anchor>

<div id="af_engagement_destination" />

<div id="af_ad_format" />

<div id="attribution-link-parametersua-and-retargeting" />

### Paramètres du lien d'attribution—UA et retargeting

Le tableau suivant peut être [téléchargé en `.csv`.](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZQnoDdFo2NxBuWXBs5gGgvkGU2pr_hn58H9Dtf5uHBAHv4Io89Wd44rRtL24pRsOXHthnBitaOyfp/pub?gid=0&single=true&output=csv)

<div id="attribution-parameters" />

| Paramètre | Nom d'affichage dans les données brutes | Description | Type et longueur du champ |
| --- | --- | --- | --- |
| <span id="pid"></span>pid | Source média | Identifie de manière unique un partenaire intégré AppsFlyer. Ne le modifiez pas. [Plus d'informations](/docs/about-link-structure-and-parameters#partner-id-pid-parameter). | <span id="PID"></span>Chaîne 150 |
| <span id="c"></span>c | Campagne | Fourni par l'annonceur ou l'éditeur. Voir les [limites de caractères pour les noms de campagne.](/docs/about-link-structure-and-parameters#what-limits-are-there-on-campaign-names) | <span id="Campaign"></span>Chaîne 100 |
| <span id="af_prt"></span>af\_prt | Partenaire | <ul><li>Le nom de compte de l'agence permet d'attribuer les installations à l'agence</li><li>**Remarque** : n'utilisez pas ce paramètre avant de vous assurer que les**autorisations d'agence** sont activées</li></ul> | Chaîne 50 |
| <span id="af_mp"></span>af\_mp | S/O | <ul><li>Active l'envoi de postbacks aux partenaires marketing des éditeurs pour chaque installation.</li><li>**Remarque** : à l'heure actuelle, ce paramètre n'est utilisé que pour les partenaires marketing de Pinterest.</li></ul> |  |
| <span id="clickid"></span>clickid | S/O | Identifiant de clic unique des ad networks |  |
| <span id="af_siteid"></span>af\_siteid | Site ID | <ul><li>L'ID unique qui définit l'éditeur qui affiche la publicité. [En savoir plus](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <span id="Site_id"></span>Chaîne 24 |
| <span id="af_sub_siteid"></span>af\_sub\_siteid | Identifiant du sous-site | <ul><li>ID du sous-réseau/de l'éditeur.</li><li>Si en plus de l'éditeur principal (ID de site) il existe un sous-éditeur, ou bien si vous souhaitez inclure des infos supplémentaires, comme le type de publicité ou l'emplacement dans l'app (bannière, interstitiel, vidéo, etc.), veuillez utiliser af\_sub\_siteid. Exemple : af\_sub\_siteid =ABCD\_4567</li></ul> | Chaîne 50 |
| <span id="af_c_id"></span>af\_c\_id | Identifiant de la campagne | Fourni par l'annonceur/l'éditeur | Chaîne 24 |
| <span id="af_adset"></span>af\_adset | Ensemble de publicités | <ul><li>Fourni par l'annonceur/l'éditeur</li><li>Adset représente un niveau intermédiaire dans la hiérarchie entre campagne et publicité. [En savoir plus](/docs/about-link-structure-and-parameters#niveaux-de-granularité-des-données)</li></ul> | Chaîne 100 |
| <span id="af_adset_id"></span>af\_adset\_id | Identifiant de l'ensemble de publicités | Fourni par l'annonceur/l'éditeur | Chaîne 24 |
| <span id="af_ad"></span>af\_ad | Publicité | Nom de la publicité ([voir plus](/docs/about-link-structure-and-parameters#niveaux-de-granularité-des-données)) - fourni par l'annonceur/l'éditeur | Chaîne 100 |
| <span id="af_ad_id"></span>af\_ad\_id | Identifiant de publicité | Fourni par l'annonceur/l'éditeur | Chaîne 24 |
| <span id="af_ad_type"></span>af\_ad\_type | Type de publicité | Utilisez la convention de dénomination suivante :<ul><li>**text :** une unité publicitaire qui ne contient que du texte, par exemple un résultat de recherche</li><li>**banner :** un format de base qui apparaît en haut ou en bas de l'écran de l'appareil</li><li>**interstitial :** une publicité en pleine page qui s'affiche à certains moments clés</li><li>**video:** une vidéo standard, sans récompense</li><li>**rewarded\_video :** un bloc de publicités qui offre des récompenses in-app aux utilisateurs qui décident de regarder une vidéo</li><li>**playable :** un bloc de publicités contenant un aperçu interactif de ce que propose l'app</li><li>**sponsor\_contenu :** un lien inclus dans un extrait de contenu sponsorisé, comme un article publicitaire</li><li>**audio :** une publicité audio</li></ul> | Chaîne 24 |
| <span id="af_click_lookback"></span>af\_click\_lookback | Fenêtre d'attribution rétrospective | <ul><li>Fenêtre rétrospective pour l'attribution de clics.  La durée de cette fenêtre est le CTIT (Click Time to Install) pour que le nouvel utilisateur soit attribué à la source affichant la publicité/le lien.</li><li>Nombre de jours configurable pour la période d'attribution rétrospective de clics. Valeurs de paramètres disponibles : 1j - 30j (jours) OU 1h - 23h (heures). La valeur par défaut est 7j.</li><li>La fenêtre d'attribution peut être personnalisée pour les <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows#configuration-de-la-fenêtre-dattribution">OneLinks et les SRN</Anchor>.</li></ul>**Remarque** : n'affecte que les URL des clics, pas les URL d'impression. | 3 car. max. |
| <span id="af_viewthrough_lookback"></span>{"af_viewthrough_"}  <br />lookback | S/O | <ul><li>Nombre configurable de jours pour la période d'attribution post vue rétrospective. Valeurs de paramètre disponibles : 1h - 24h (heures). La valeur par défaut est 24h.</li><li>La fenêtre d'attribution peut être personnalisée pour les <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows#configuration-de-la-fenêtre-dattribution">SRN</Anchor>.</li></ul>**Remarque** : n'affecte que les URL des impressions, pas les URL des clics. | 3 car. max. |
| <span id="af_channel"></span>af\_channel | Canal | Le canal de la source média par où les publicités sont distribuées, exemple : UAC\_Search, UAC\_Display, Instagram, Meta Audience Network, etc. | Chaîne Enum dynamique Chaîne 20 |
| <span id="af_keywords"></span>af\_keywords | Mots-clés | Liste des mots-clés pour les campagnes ciblées sur le texte | Chaîne 100 |
| <span id="af_cost_model"></span>af\_cost\_model | Modèle de coût | <ul><li>Le modèle de coût, CPI (par défaut) est actuellement le seul modèle pris en charge pour le signalement du coût par clic, qui renseigne la <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">valeur du coût dans les rapports de données agrégées AppsFlyer</Anchor> .</li><li>Dans la mesure du possible, indiquez le coût par <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">API.</Anchor>  Dans les cas où le coût est signalé à la fois dans le lien et par API, c'est l'API qui a la priorité.</li></ul> | Chaîne 20 |
| <span id="af_cost_currency"></span>af\_cost\_currency | Devise des coûts | <ul><li>Code de devise à 3 lettres conforme à la <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">norme ISO-4217.</Anchor> Par exemple, USD, ZAR, EUR</li><li>[Par défaut] : USD</li></ul> | Enum 3 car |
| <span id="af_cost_value"></span>af\_cost\_value | Valeur des coûts | <ul><li>Valeur de coût en utilisant la devise de coût.</li><li>Jusqu'à 4 chiffres après la virgule.</li><li>Utilisez UNIQUEMENT des chiffres (utilisez un point en guise de virgule si nécessaire) ex. «56» ou «2.85»</li></ul> | Chaîne 20 |
| <span id="af_sub-n-n15-example-af_sub1"></span>af\_sub[n]<br /><br />(n=1-5) exemple : af\_sub1 | Sous-paramètre [n] | Paramètre personnalisé facultatif défini par l'annonceur. Pour plus d'informations sur l'utilisation de ces paramètres, consultez la section [Caractéristiques et limitations](/docs/about-link-structure-and-parameters#traits-and-limitations). | Chaîne 100 |
| <span id="af_r"></span>af\_r | S/O | Utilisé dans les liens vers plateforme unique pour rediriger les utilisateurs vers l'URL qui a été définie pour les **deux plateformes** (Android et iOS).<ul><li>Remplacé par les paramètres de plateforme unique de niveau lien suivants :<ul><li>[`af_android_url`](/docs/about-link-structure-and-parameters#af_android_url)</li><li>[`af_ios_url`](/docs/about-link-structure-and-parameters#af_ios_url)</li><li>[`af_web_dp`](/docs/about-link-structure-and-parameters#af_web_dp)</li></ul></li></ul><ul><li>Remplace les paramètres de niveau template suivants :<ul><li>`android_custom_url`</li><li>`ios_custom_url`</li></ul></li></ul> |  |
| <span id="af_web_dp"></span>af\_web\_dp | S/O | URL qui redirige les utilisateurs d'ordinateur de bureau (comme Windows ou Mac) vers une page web différente de celle configurée dans le template OneLink. Cette option permet de conserver les données d'attribution des utilisateurs d'ordinateur de bureau sur d'autres plateformes (ex : Google Analytics ou Omniture)<br /><br />**Remarque** : si vous disposez d'une <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-api-allowlist#redirect-allowlists">liste des redirections autorisées</Anchor> active, vérifiez que le domaine de cette URL apparait bien dans la liste. |  |
| <span id="af_dp"></span>af\_dp | S/O | La valeur du schéma d'URI de secours qui lance l'app, à utiliser en cas d'échec de la méthode Universal Link ou Android App Link, et pour les utilisateurs d'Android version 6.0 et -. Elle ne doit indiquer que le <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">chemin de base</Anchor>, c'est-à-dire l'activité par défaut. |  |
| <span id="af_force_deeplink"></span>af\_force\_deeplink | S/O | <Anchor target="_blank" href="/marketers/fr/docs/onelink-troubleshooting-and-faq">Force le deep linking</Anchor> dans l'activité indiquée dans la valeur af\_dp |  |
| <span id="af_ref"></span>af\_ref | S/O | Les réseaux publicitaires travaillant avec les clics S2S peuvent envoyer une valeur de référence unique en utilisant le paramètre suivant :  &af\_ref=**ReferrerValue**<br /><br />La valeur af\_ref **doit** consister en une valeur unique, structurée comme suit :<br /><br />**NetworkName\_UniqueClickValueForEachClick**<br /><br />Exemple : af\_ref=networkname\_123456789ABCDEF<br /><br />Le nom de réseau peut être n'importe quelle chaîne valide. Par exemple, « networkname\_int » ou juste « networkname ».<br /><br />AppsFlyer peut utiliser ce paramètre pour l'attribution sur les appareils Android. AppsFlyer n'utilise pas ce paramètre pour l'attribution sur les appareils iOS ou Windows. |  |
| <span id="is_incentivized"></span>is\_incentivized | S/O | Booléen : true/false<br /><br />Campagnes avec incitations ou sans incitations |  |
| <span id="af_param_forwarding"></span>af\_param\_forwarding | S/O | <ul><li>Lorsque la valeur est définie sur false, les paramètres du lien d'attribution ne sont pas transférés à la page redirigée.</li><li>Utilisez ce paramètre pour obtenir une URL plus claire dans la page redirigée, ou si les paramètres du lien d'attribution entraînent des problèmes en raison de la gestion des paramètres de requête sur la page redirigée</li></ul> |  |
| <span id="af_base_params_forward"></span>af\_base\_params\_forward | S/O | <ul><li>Lorsque la valeur est définie sur false, les paramètres PID et C d'AppsFlyer dans le lien d'attribution ne sont pas transférés vers la page redirigée.</li><li>Utilisez cette option si l'URL est cliquée depuis un ordinateur de bureau, et si vous souhaitez que les paramètres CRM essentiels soient conservés tout en supprimant les paramètres AppsFlyer PID et C. Cela vous évitera d'avoir plusieurs PID dans l'URL.</li></ul> |  |
| <span id="af_partner_account_id"></span>af\_partner\_account\_id | ID de compte réseau | ID du compte de l'annonceur auprès du partenaire | Chaîne 100 |
| <span id="af_redirect"></span>Rediriger | S/O | Avec `&redirect=false`, le paramètre permet à AppsFlyer de savoir qu'il s'agit d'un clic S2S et que le partenaire s'occupe de rediriger l'utilisateur qui a cliqué. |  |
| <span id="af_ua"></span>af\_ua | Agent utilisateur | Concerne les réseaux publicitaires qui envoient les clics et les impressions <Anchor target="_blank" href="/partners/fr/docs/redirecting-users-to-the-app-store">de serveur à serveur</Anchor>.<br /><br />La chaîne de caractères de l'agent-utilisateur est la suivante :<ol><li>Paramètre URL (codé en URL)</li><li>En-tête de requête HTTP (non codé)</li></ol>L'agent-utilisateur doit être **identique dans le paramètre de l'URL et l'en-tête HTTP**.<br /><br />**Note** : dans Android, l'agent-utilisateur est parfois réduit à Client Hints. Il doit être envoyé même dans ce cas.<ul><li>Exemple d'agent utilisateur complet : `Mozilla/5.0 (Linux ; Android 12 ; Pixel 5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.16 Mobile Safari/537.36`</li><li>Exemple d'agent-utilisateur réduit : `Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36 (KHTML, comme Gecko) Chrome/95.0.0.0 Mobile Safari/537.36`</li></ul> |  |
| <span id="af_ip"></span>af\_ip | IP | Concerne les réseaux publicitaires qui envoient les clics et les impressions <Anchor target="_blank" href="/partners/fr/docs/redirecting-users-to-the-app-store">de serveur à serveur</Anchor>.<br /><br />**Adresse IP de l'appareil**<br /><br />**Recommandé** : si il est disponible, fournissez l'IP de l'appareil sous le paramètre af\_ip.<br /><br />**Option suivante** : si disponible, AppsFlyer utilisera l'IP dans X-Forwarded-For. |  |
| <span id="deprecated--af_os"></span>[Obsolète] af\_os | Version OS | [Pour iOS uniquement] La version du système d'exploitation de l'appareil<br /><br />Bien qu'il soit obsolète, ce paramètre est toujours pris en charge par AppsFlyer. Recommandé : utilisez le paramètre af\_os\_version à la place. |  |
| <span id="af_os_version"></span>af\_os\_version | Version OS | <ul><li>Concerne les réseaux publicitaires qui envoient les clics et les impressions <Anchor target="_blank" href="/partners/fr/docs/redirecting-users-to-the-app-store">de serveur à serveur</Anchor>.</li><li>La version du système d'exploitation de l'appareil.<ul><li>Android :<ul><li>Exemple : 12</li><li>Pour les agents-utilisateurs réduits (en raison des navigateurs fonctionnant sur ordinateur ou Android et utilisant le moteur Chrome 110+), le réseau publicitaire doit utiliser l'API <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">Client Hints</Anchor> pour obtenir cette valeur.</li><li>Pour les agents-utilisateurs qui ne sont **pas réduits**, utilisez la regex suivante pour extraire la version d'Android OS de la chaîne agent-utilisateur : `(\d+(?:\.\d+)*) ;(?:\s..-.. ;)?\s(.+ ?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS :<ul><li>Exemple : 16.2</li></ul></li></ul></li></ul> |  |
| <span id="af_model"></span>af\_model | Modèle d'appareil | <ul><li>Concerne les réseaux publicitaires qui envoient les clics et les impressions <Anchor target="_blank" href="/partners/fr/docs/redirecting-users-to-the-app-store">de serveur à serveur</Anchor>.</li><li>Le modèle de l'appareil.<ul><li>Android :<ul><li>Exemple : Pixel 5</li><li>Pour les agents-utilisateurs réduits (en raison des navigateurs fonctionnant sur ordinateur ou Android et utilisant le moteur Chrome 110+), le réseau publicitaire doit utiliser l'API <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">Client Hints</Anchor> pour obtenir cette valeur.</li><li>Pour les agents-utilisateurs qui ne sont **pas réduits**, utilisez la regex suivante pour extraire la version Android de la chaîne agent-utilisateur : `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS :<ul><li>`iphone` ou `ipad` (tout en minuscule)</li></ul></li></ul></li></ul> |  |
| <span id="af_media_type"></span>af\_media\_type | Type de média | Positionnement de la publicité portant le lien comme suit :<ul><li>app : le lien est disponible via une app</li><li>web : le lien est disponible sur un site web mobile</li></ul> |  |
| <span id="deep_link_sub110"></span>deep\_link\_sub1-10 | S/O | Valeurs supplémentaires du deep link. Les développeurs implémentent dans le code le comportement des valeurs souhaité. |  |
| <span id="deep_link_value"></span>deep\_link\_value | S/O | Nom du contenu in-app vers lequel les utilisateurs seront dirigés. Les développeurs implémentent dans le code le comportement souhaité de deep\_link\_value. |  |
| <span id="af_og_title"></span>af\_og\_title | S/O | Lorsqu'un lien est publié sur les réseaux sociaux, le titre de l'open graph (OG) génère un aperçu de titre. | Chaîne 40 |
| <span id="af_og_description"></span>af\_og\_description | S/O | Lorsqu'un lien est publié sur les réseaux sociaux, la description de l'open graph (OG) génère un aperçu de description. | Chaîne 300 |
| <span id="af_og_image"></span>af\_og\_image | S/O | Lorsqu’un lien est publié sur les médias sociaux, l’image de l'open graph (OG) génère un aperçu d’image. |  |

<div id="attribution-link-parametersretargeting-only" />

### Paramètres du lien d'attribution—retargeting uniquement

| Paramètre | Nom d'affichage dans les données brutes | Description | Type et longueur du champ |
| --- | --- | --- | --- |
| <span id="is_retargeting"></span>is\_retargeting | S'agit-il de retargeting (campagne) | Les URL cliquables des campagnes de retargeting doivent inclure `&is_retargeting=true`.  <br />Si le paramètre n'est pas inclus ou si sa valeur est « false », la campagne est considérée comme une campagne d'acquisition d'utilisateur normale. | Enum 5 car |
| <span id="af_reengagement_window"></span>af\_reengagement\_window | Fenêtre de réengagement | Modifiez <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window#setting-the-re-attribution-window">la fenêtre d'attribution du réengagement</Anchor> en ajoutant ce paramètre au lien d'attribution.<br /><br />Les options de plage de fenêtres possibles sont les suivantes :<ul><li>Jours : 1-90  ou heures 1-36</li><li>Durée de vie : cela signifie que la fenêtre de réengagement est illimitée. Exemple :`&af_reengagement_window=lifetime`</li></ul>Valeur par défaut : 30 jours<br /><br />Exemple : `&af_reengagement_window=60d` définit la fenêtre de réengagement à 60 jours. | S/O |

<div id="viewability-parameters" />

### Paramètres de type de publicité

En fonction du type de publicités, vous pouvez également envoyer le paramètre de visibilité correspondant en précisant les spécifications de l'engagement. Vous trouverez ci-dessous une liste des valeurs possibles pour « af\_ad\_type » ainsi que les paramètres de visibilité attendus.

#### Type de publicité (af\_ad\_type)

| Paramètre | Format de la valeur | Description |
| --- | --- | --- |
| <span id="af_video_total_length"></span>af\_video\_total\_length | secondes | Durée totale possible de la vidéo |
| <span id="af_video_played_length"></span>af\_video\_played\_length | secondes | Durée de la vidéo ayant été vue |
| <span id="af_playable_played_length"></span>af\_playable\_played\_length | secondes | Durée de l'élément jouable ayant été joué une fois complètement chargé |
| <span id="af_ad_time_viewed"></span>af\_ad\_time\_viewed | secondes | Durée pendant laquelle le modèle de publicité était visible à l'écran |
| <span id="af_ad_displayed_percent"></span>af\_ad\_displayed\_percent | % | Pourcentage maximal du modèle de publicité visible sur l'écran de l'appareil |
| <span id="af_audio_total_length"></span>af\_audio\_total\_length | secondes | Durée possible totale de l'audio |
| <span id="af_audio_played_length"></span>af\_audio\_played\_length | secondes | Durée de l'audio ayant été entendue |

<div id="android-specific-parameters" />

### Paramètres Android spécifiques

| Paramètre | Nom d'affichage dans les données brutes | Description | Type de champ |
| --- | --- | --- | --- |
| <span id="advertising_id"></span>advertising\_id | Advertising ID | Google Advertising ID - Doit être pris en charge par le réseau publicitaire | 40 caractères max. |
| <span id="sha1_advertising_id"></span>sha1\_advertising\_id | S/O | Google Advertising ID haché avec SHA1 - Doit être pris en charge par le réseau publicitaire |  |
| <span id="md5_advertising_id"></span>md5\_advertising\_id | S/O | Google Advertising ID haché avec SHA1 - Doit être pris en charge par le réseau publicitaire | Pris en charge avec les installations et les réattributions uniquement |
| <span id="android_id"></span>android\_id | Android ID | Device Android\_id - Doit être pris en charge par le réseau publicitaire | 20 caractères max. |
| <span id="sha1_android_id"></span>sha1\_android\_id | S/O | Device Android\_id haché avec SHA1 - Doit être pris en charge par le réseau publicitaire |  |
| <span id="md5_android_id"></span>md5\_android\_id | S/O | Device Android\_id haché avec MD5 - Doit être pris en charge par le réseau publicitaire | Pris en charge avec les installations et les réattributions uniquement |
| <span id="imei"></span>imei | IMEI | ID IMEI de l'appareil |  |
| <span id="sha1_imei"></span>sha1\_imei | S/O | ID IMEI appareil haché avec SHA1 - Doit être pris en charge par le réseau publicitaire |  |
| <span id="md5_imei"></span>md5\_imei | S/O | ID IMEI appareil haché avec MD5 - Doit être pris en charge par le réseau publicitaire |  |
| <span id="oaid"></span>oaid | OAID | Ouvrir l'identifiant de périphérique anonyme | Disponible à partir du SDK Android version 4.10.3 |
| <span id="sha1_oaid"></span>sha1\_oaid | S/O | Ouvrir l'identifiant de périphérique anonyme haché avec SHA1 - Doit être pris en charge par le réseau publicitaire | Disponible à partir du SDK Android version 4.10.3 |
| <span id="md5_oaid"></span>md5\_oaid | S/O | Ouvrir l'identifiant de périphérique anonyme haché avec MD5 - Doit être pris en charge par le réseau publicitaire | Disponible à partir du SDK Android version 4.10.3 |
| <span id="af_android_url"></span>af\_android\_url | S/O | Redirige les utilisateurs d'Android vers une URL autre de celle de la page de l'app sur Google Play. À utiliser pour les <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution#tableau-de-bord-unique-et-tableau-de-bord-par-store">app stores tiers</Anchor>.<br /><br />**Remarque** : si vous disposez d'une <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-api-allowlist#redirect-allowlists">liste des redirections autorisées</Anchor> active, vérifiez que le domaine de cette URL apparait bien dans la liste. |  |
| <span id="sha1_el"></span>sha1\_el | S/O | Utilisé pour les ordinateurs portables comme pour l'attribution mobile - e-mail haché avec SHA1. Doit être pris en charge par le réseau publicitaire |  |
| <span id="fire_advertising_id"></span>fire\_advertising\_id | S/O | Identifiant de publicité Amazon Fire |  |
| <span id="af_android_store_csl"></span>af\_android\_store\_csl | store\_product\_page | Liste personnalisée des stores dans Google Console | chaîne |

<div id="md5_idfa" />

<div id="ios-specific-parameters" />

### Paramètres spécifiques à iOS

| Paramètres | Nom d'affichage | Description |
| --- | --- | --- |
| <span id="idfa"></span>idfa | IDFA | Utilisez les majuscules. Doit être pris en charge par le réseau publicitaire<br /><br />Type de champ : 40 caractères max. |
| <span id="idfv"></span>idfv | IDFV | Utilisez des majuscules. |
| <span id="af_ios_url"></span>af\_ios\_url |  | Redirection de la page d'accueil : permet de rediriger les utilisateurs iOS (iPhone ou iPad) vers une autre URL que celle de la page de l'app sur iTunes<br /><br />**Remarque** : si vous disposez d'une <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-api-allowlist#redirect-allowlists">liste des redirections autorisées</Anchor> active, vérifiez que le domaine de cette URL apparait bien dans la liste. |
| <span id="af_ios_store_cpp"></span>af\_ios\_store\_cpp | store\_product\_page | ID de page produit personnalisée (ppid) |
| <span id="af_ios_fallback--deprecated"></span>af\_ios\_fallback [obsolète] | S/O | **Obsolète** : les utilisateurs sont redirigés en fonction du <Anchor target="_blank" href="/marketers/fr/docs/uri-scheme-fallback-for-ios">flux du schéma d'URI iOS</Anchor>. |
| <span id="sha1_idfa"></span>sha1\_idfa | S/O | IDFA haché avec SHA1. Doit être pris en charge par le réseau publicitaire |
| <span id="sha1_idfv"></span>sha1\_idfv | S/O | IDFV haché avec SHA1. |
| <span id="mac"></span>mac | S/O | Adresse mac des appareils. Doit être pris en charge par le réseau publicitaire |
| <span id="md5_idfv"></span>md5\_idfv | S/O | IDFV haché avec MD5 |
| <span id="sha1_mac"></span>sha1\_mac | S/O | Adresse des appareils mac hachée avec SHA1. Doit être pris en charge par le réseau publicitaire |

<div id="example" />

> 📄 **Exemple**
>
> ```http
> https://app.appsflyer.com/{app_id}/?pid=airpush_int&c=RedBanner&
> 	  af_siteid={publisher_id}&af_sub1=1.5&af_sub2=USD&af_sub3=burst_campaign
> ```

Tous les paramètres sont disponibles dans le <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">Rapport d'installations</Anchor> et les <Anchor target="_blank" href="/marketers/fr/docs/analytics-and-aggregate-reporting-apis">Analyses, Rapports et API</Anchor>.

<div id="note" />

<div id="custom-parameters" />

### Paramètres personnalisés

Vous pouvez définir des paramètres personnalisés en plus des paramètres par défaut spécifiques à Android et iOS. Ces paramètres spécifiques vous permettront de personnaliser le contenu de l'utilisateur et ce qu'il expérimente en fonction du lien d'attribution qui déclenche une installation.

Vous pouvez ajouter un paramètre personnalisé au lien d'attribution au format `parameter=value`. Par exemple :

```http
https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&af_adset=coats&af_ad=cashmere&my_custom_param=my_custom_value
```

Voici deux choses à savoir sur les paramètres personnalisés :

* Les paramètres personnalisés n'apparaissent pas dans les données brutes.
* Les paramètres personnalisés peuvent être récupérés à partir <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">de l'API du SDK Obtenir les données de conversion</Anchor>.

<div id="partner-id-pid-parameter" />

<Accordion title="Paramètre de l'ID de partenaire (PID)">

Parmi tous les paramètres de lien d'attribution disponibles, le PID est obligatoire. Le PID est l'identifiant unique de la source média attribuée par AppsFlyer.

Chaque <Anchor target="_blank" href="http://appsflyer.com/partners">partenaire intégré</Anchor> a sa propre valeur de PID. Le PID se termine par le suffixe *\_int*. Lorsque vous utilisez un <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">lien OneLink</Anchor>, vous pouvez définir le PID sur la valeur de votre choix, tant qu'il n'est pas réservé à un partenaire intégré. Pour éviter tout conflit, n'utilisez pas le suffixe *\_int*.

Quelques ID d'éditeurs intégrés parmi les plus importants : organic, googleadwords\_int (Google AdWords), Meta ads, Twitter. Vous pouvez utiliser le nom que vous souhaitez pour les sources non intégrées, comme les e-mails, sms ou pigeons voyageurs.

<div id="avoid-common-pid-issues" />

#### Comment éviter les problèmes de PID les plus courants :

* **Intégrez systématiquement le PID dans vos liens d'attribution.** En l'absence de PID dans le lien d'attribution, l'utilisateur est automatiquement attribué à une source média « inexistante »**, et la source d'installation originale disparaît**.
* **Pour les sources personnalisées, utilisez les PID des partenaires non intégrés.** Pour chaque source intégrée, utilisez uniquement le PID désigné pour obtenir la bonne attribution de ses installations. Pour toute source média personnalisée, comme les e-mails, les SMS, voire les posts viraux non payés sur Facebook, utilisez des valeurs de PID non intégrés différentes.
* **N'utilisez que les caractères autorisés**. Si le paramètre PID du lien d'attribution contient l'un des caractères suivants /&lt;>*&?\
  * Le clic ou l'installation s'affichera dans le tableau de bord comme ***af\_invalid\_param***
  * Les liens d'attribution ne seront pas attribués
  * Le deep linking ne fonctionnera pas après les clics

<div id="tip" />

> 👍 **Astuce**
>
> Évitez d'utiliser des espaces dans la valeur du PID, ou veillez à encoder vos liens d'attribution dans l'URL avant de les utiliser.

</Accordion>

<div id="site-id-parameter" />

<Accordion title="Paramètre de l'ID de site">

L'identifiant du site est l'identifiant unique de l'éditeur diffusant la publicité. En d'autres termes, le site web ou l'app qui affiche la publicité. Les réseaux publicitaires attribuent des identifiants de site uniques à chaque éditeur.

Cet identifiant est inclus dans le paramètre `af_siteid` transmis à AppsFlyer dans le lien d'attribution. Il est rendu disponible via les tableaux de bord, options de rapport et postbacks d'AppsFlyer.

L'ID de site doit être transmis à AppsFlyer via le lien d'attribution pour les raisons suivantes :

* Il fournit clarté et transparence sur l'éditeur.
* Il est utilisé par AppsFlyer pour identifier et éliminer les éditeurs frauduleux, ou tout autre cluster de trafic.

Le paramètre d'ID de site contient uniquement l'ID de l'éditeur qui diffuse la publicité.

Pour inclure des informations supplémentaires, telles que le type de publicité, le placement ou les deux au sein de l'app, par exemple la bannière, l'intersection ou la vidéo, utilisez le paramètre ID de sous-site.

<div id="example-1" />

> 📄 **Exemple**
>
> Le lien d'attribution suivant comprend :
>
> * `af_siteid` (ID de site) : ID de l'éditeur
> * `af_sub_siteid` (ID de sous-site) : infos d'identification additionnelles (dans le cas présent, une source affiliée et un emplacement de type de publicité)
>
> `https://app.appsflyer.com/com.yourapp?pid=mediaName_int&clickid={clickid}&advertising_id={gaid}&af_siteid=1234&af_sub_siteid=ABCD_4567`
>
> Dans l'exemple de lien :
>
> * 1234 = ID d'éditeur
> * ABCD = source affiliée (sous-éditeur) avec laquelle l'éditeur collabore
> * 4567 = emplacement dans l'app du type de publicité, comme une bannière, un interstitiel ou une vidéo

<div id="faq-why-does-traffic-result-in-many-blocked-installs" />

#### **FAQ : pourquoi le trafic génère-t-il autant d'installations bloquées ?**

Les installations peuvent être bloquées pour les motifs suivants :

* **ID de site manquant :** le paramètre `af_siteid` est vide dans l'URL de clic. Les engagements qui sont envoyés avec un ID de site manquant indiquent soit un problème technique, soit une tentative de contournement des systèmes de détection des fraudes.
* **Plusieurs ID de site :** le même éditeur est envoyé sur plusieurs URL de clics, à l'aide de différents ID de site. Ceci est vu comme un acte frauduleux visant à dissimuler l'activité réelle de l'éditeur, il est souvent associé à un <Anchor target="_blank" href="https://www.appsflyer.com/blog/click-flooding-detection-false-positive-challenge/">click flooding</Anchor>.
* **ID de site mal formaté :** l'envoi d'un format incorrect, associé à d'autres signes de fraude, peut entraîner le blocage non seulement de l'éditeur en question, mais aussi d'un cluster de niveau plus élevé, ce qui peut se répercuter de manière très forte sur l'activité du partenaire.

Pour éviter les blocages d'installations, veillez à n'envoyer qu'un seul paramètre d'ID de site par éditeur, comme indiqué dans notre exemple.

</Accordion>

<div id="levels-of-data-granularity" />

## Niveaux de granularité des données

Vous pouvez utiliser jusqu'à quatre paramètres d'URL pour analyser en profondeur la performance de vos publicités.

L'utilisation des 4 paramètres sur tous vos liens d'attribution actifs vous permet :

* D'attribuer tous les événements et installations des utilisateurs à certaines publicités spécifiques
* Évaluez et comparez les performances de toutes vos publicités par ad set, campagne et source média au sein de rapports agrégés, et optimisez l'ensemble des niveaux
* De comparer toutes vos publicités sur toutes vos sources médias sur les rapports de données brutes et votre <Anchor target="_blank" href="/marketers/fr/docs/pivot-table-user-metrics">tableau Pivot</Anchor>

Les paramètres sont :

* `Source média (pid=)`
* `nom de campagne (c=)`
* `Ensemble de publicités (af_adset=)`
* `Nom de publicité (af_ad=)`

<div id="frequently-asked-questions" />

<div id="example-2" />

> 📄 **Exemple**
>
> Le lien d'attribution suivant utilise 4 niveaux de granularité pour enregistrer la publicité « cachemire » dans l'ad set « manteaux » de la campagne « hiver » diffusée sur la source média « networkx » intégrée.
>
> ```http
> https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&
> af_adset=coats&af_ad=cashmere
> ```

<div id="telegram-webview-attribution" />

<div id="uri-scheme-validity-requirements" />

<div id="a-popup-appears-when-clicking-on-a-uri-scheme-link-from-chrome-browser-on-ios" />

<div id="deep-linking-is-not-supported-in-the-android-naver-blog-app" />

<div id="agencies" />

<div id="url-characteravailable" />

<div id="redirection-parameters" />

<div id="special-characters" />

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Remarques |
| --- | --- |
| Caractères spéciaux | Les caractères spéciaux qui suivent ne sont pas autorisés dans le paramètre ou les valeurs  : ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \} et % |
| Nbre maxi de caractères dans l'URL | La longueur totale de l'URL ne doit pas dépasser 2 000 caractères |
| Apps sociales Android WebView redirection du deep linking | Voir les détails de la limitation <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection">ici</Anchor> |

</Accordion>

<div id="should-i-use-lower-or-upper-case-letters-for-parameters" />

<Accordion title="Dois-je utiliser des lettres majuscules ou minuscules pour les paramètres ?">

Vous pouvez choisir d'utiliser l'un ou l'autre, mais ne changez pas d'avis en cours de procédure. Si vous définissez un paramètre personnalisé avec des caractères majuscules ou minuscules, veillez à toujours utiliser ce paramètre.

Par exemple, si vous paramétrez pid=MyMediaSource, vous devrez l'utiliser à chaque fois. Si vous utilisez **pid=MyMediaSource** sur un lien d'attribution et **pid=mymediasource** sur un autre, les données seront inconsistantes. Cela est valable pour chacun des paramètres que vous définissez sur le lien d'attribution.

</Accordion>

<div id="is-the-appsflyer-attribution-link-dynamic-or-static" />

<Accordion title="Le lien d'attribution Appsflyer est-il dynamique ou statique ?">

Les liens d'attribution peuvent être dynamiques ou statiques.  
Comment faire la différence entre un lien dynamique ou statique ?  
Si le **lien d'attribution comporte des paramètres**, il s'agit d'un lien d'attribution long prédéfini, et il est donc **statique**.  
**Seules les URL courtes** (ex : `yourbrand.onelink.me/HaT8/r5c2b371`) utilisées pour les liens d'attribution personnalisés, **sont dynamiques**.  
Par conséquent, lorsque vous commencez à utiliser un lien d'attribution pour un partenaire intégré (ou une URL longue pour un média propre) ce lien reste inchangé quel que soit le prospect qui interagit avec lui, et ce même si vous modifiez les valeurs du lien d'attribution dans le tableau de bord AppsFlyer. Si vous souhaitez faire une modification, vous devrez ainsi utiliser la nouvelle URL longue.  
De plus, les URL courtes des médias propres ne contiennent pas directement de paramètres. Lorsqu'un prospect interagit avec une URL courte AppsFlyer, il est redirigé vers AppsFlyer, et les paramètres définis s'appliquent de manière dynamique.

</Accordion>

<div id="what-is-this-play-store-error-message" />

<Accordion title="Qu'est-ce que ce message d'erreur du Play Store ?">

Si vous rencontrez le message d'erreur suivant dans le Play Store après avoir suivi un lien d'attribution :

![TL_error_message.png](https://files.readme.io/03e509d3cbe68aa0621bb0f43ab113c25a8427e70826c5af5258f1fc9e3f3d36-360000002485.png)

C'est parce que le lien d'attribution comprend un caractère #. Par exemple :

```http
https://app.appsflyer.com/com.travelco?pid=globalwide_int&clickid=#reqid#
```

Habituellement, ces caractères sont inclus dans le lien parce qu'il s'agit de macros, et ils sont remplacés dynamiquement par une valeur. Ce n'est donc pas un problème très important, et vous pouvez ignorer le message.

</Accordion>

<div id="what-are-subscriber-parameters-good-for" />

<Accordion title="À quoi servent les Paramètres de souscripteur ?">

Les paramètres de souscripteur, c-à-d. af\_sub1, af\_sub2, jusqu'à af\_sub5, peuvent être utilisés pour enregistrer tout KPI utile. Ces paramètres sont analysés et apparaissent dans le rapport des données brutes, ce qui les rend très utiles pour l'agrégation ou le filtre des données.

<div id="example-3" />

> 📄 **Exemple**
>
> Une app de transport à la demande, Luber, a prévu des créatifs avec 3 modèles de couleur : bleu, jaune et rouge. Linda, marketeuse mobile, veut tester les modèles pour voir quelle couleur génère le plus d'installations. Pour cela, elle ajoute `&af_sub3=blue` aux liens d'attribution de toutes les publicités bleues pour TOUTES les sources médias non-SRN. Elle fait la même chose pour les publicités jaunes et rouges. Une fois ces informations analysées et affichées dans les rapports des données brutes, Linda peut évaluer le succès des publicités selon les différentes couleurs, et choisir celle qui obtient le meilleur taux de conversion.

</Accordion>

<div id="what-limits-are-there-on-campaign-names" />

<Accordion title="Quel est le nombre de caractères autorisé pour les noms de campagne ?">

* La longueur maximale du nom d'une campagne dans l'URL du lien d'attribution est de 100 caractères. En cas de dépassement, le nom de la campagne est modifié et devient : `c_name_exceeded_max_length`
* Le nom de la campagne ne doit pas commencer ou se terminer par un espace vide car cela peut entraîner des divergences dans les tableaux de bord et les rapports

</Accordion>

<div data-zendesk-anchors="overview=pr%C3%A9sentation 01H8GN1XXC5T2ENFHBK0G4WQ1P=pr%C3%A9sentation attribution-link-parameters=param%C3%A8tres-du-lien-dattribution 01H8GN1XXDX1XMQ1GJTHCP425D=param%C3%A8tres-du-lien-dattribution attribution-link-parameters%E2%80%94ua-and-retargeting=param%C3%A8tres-du-lien-dattributionua-et-retargeting 01H8GN1XXDEWPB2MPP3KJVPRJV=param%C3%A8tres-du-lien-dattributionua-et-retargeting af_sub%5Bn%5D%C2%A0%0An15-example-af_sub1=af_sub-n-n15-example-af_sub1 %5Bdeprecated%5D-af_os=deprecated--af_os attribution-link-parameters%E2%80%94retargeting-only=param%C3%A8tres-du-lien-dattributionretargeting-uniquement 01H8GN1XXD9X7CWZJN43PSS94R=param%C3%A8tres-du-lien-dattributionretargeting-uniquement ad-type-parameters=param%C3%A8tres-de-type-de-publicit%C3%A9 01H8GN1XXETQEYT39F05ZYX4E2=param%C3%A8tres-de-type-de-publicit%C3%A9 ad-type-af_ad_type=type-de-publicit%C3%A9-af_ad_type 01H8GN1XXEPEZ53C3XFB601838=type-de-publicit%C3%A9-af_ad_type androidspecific-parameters=param%C3%A8tres-android-sp%C3%A9cifiques 01H8GN1XXEE9RGSB1H72H025Z4=param%C3%A8tres-android-sp%C3%A9cifiques iosspecific-parameters=param%C3%A8tres-sp%C3%A9cifiques-%C3%A0-ios 01H8GN1XXESJ9VE3W8CYKRFFYX=param%C3%A8tres-sp%C3%A9cifiques-%C3%A0-ios af_ios_fallback-%5Bdeprecated%5D=af_ios_fallback--deprecated 01H8GN1XXEFRSQSERTB6ARC773=exemple custom-parameters=param%C3%A8tres-personnalis%C3%A9s 01H8GN1XXEB58JN4SV9HX1ZV6S=param%C3%A8tres-personnalis%C3%A9s 01H8GN1XXE8EXMMKDZMJ2WNNH5=partner-id-pid-parameter avoid-common-pid-issues=comment-%C3%A9viter-les-probl%C3%A8mes-de-pid-les-plus-courants- 01H8GN1XXEXTGC4M8AMJ256Q9G=comment-%C3%A9viter-les-probl%C3%A8mes-de-pid-les-plus-courants- 01H8GN1XXEGNVX9GM5JYBMBGCF=astuce 01H8GN1XXEVG65YP782CM37RES=site-id-parameter 01H8GN1XXED2MVSNRXN11KZ955=exemple-1 faq-why-does-traffic-result-in-many-blocked-installs=faq--pourquoi-le-trafic-g%C3%A9n%C3%A8re-t-il-autant-dinstallations-bloqu%C3%A9es- 01H8GN1XXEK0G9TDW8WHWM17HK=faq--pourquoi-le-trafic-g%C3%A9n%C3%A8re-t-il-autant-dinstallations-bloqu%C3%A9es- levels-of-data-granularity=niveaux-de-granularit%C3%A9-des-donn%C3%A9es 01H8GN1XXE4RF9J0APAAKD1WEG=niveaux-de-granularit%C3%A9-des-donn%C3%A9es 01H8GN1XXEHPFKX7V0RRW2MH2G=exemple-2 01H8GN1XXEBTW3XRGNZ3A8ZZJP=traits-and-limitations 01H8GN1XXEND9X8YVRQE1YFA5W=should-i-use-lower-or-upper-case-letters-for-parameters 01H8GN1XXER749PH4Z14A7AJ0F=is-the-appsflyer-attribution-link-dynamic-or-static 01H8GN1XXEPQTY0XNW6EZSA9ZN=what-is-this-play-store-error-message 01H8GN1XXFYAFYFX9MNBP6D35B=what-are-subscriber-parameters-good-for 01H8GN1XXFEFA498J22GRF5F8G=exemple-3 01H8GN1XXFS1DFS3HAHVTVG93A=what-limits-are-there-on-campaign-names" />
