---
title: '[Obsolète] Script d''attribution de la page de renvoi mobile'
deprecated: true
metadata:
  keywords:
    - Landing Page
    - Facebook
    - Adwords
    - Advertisers
    - Agencies
    - GCLID
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Agencies
    - Smart Banners and Scripts
  created_at: '2020-12-16T17:28:55Z'
  edited_at: '2024-09-09T12:24:37Z'
  id: 360016643258
  locale: fr
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/fr/articles/360016643258
---
> **En bref :** Ce script est obsolète depuis le 17 décembre 2020 et est remplacé par le <Anchor target="_blank" href="/marketers/fr/docs/onelink-smart-script-overview">OneLink Smart Script.</Anchor> Cette version continue de fonctionner, mais ne sera pas mise à jour ou modifiée. Le script génère des URL qui sont intégrées derrière un bouton sur votre site web mobile et redirige les visiteurs vers le téléchargement de votre app. Les URL permettent également l'attribution d'installations et la création de deeplinking.

<Image align="center" alt="5648_Sunset_and_deprecation-01.png" src="https://files.readme.io/f2a154145e26577b698d00c4c3719be3eea7298576e6883bd47e6fb42897c71a-360015062398.png" />

**<Anchor target="_blank" href="/marketers/fr/docs/onelink-smart-script-overview">Migrer vers OneLink Smart Script</Anchor>**

Les pages de renvoi sont une technique très répandue parmi les spécialistes du marketing numérique. Elles permettent à ces derniers d'enregistrer les coordonnées de leurs clients potentiels à des fins de remarketing, même si ces utilisateurs ne se convertissent pas dans un premier temps.

Cependant, pour l'acquisition d'utilisateurs mobiles, la stratégie de la page de renvoi présente des avantages et des inconvénients.

<div id="the-upsides" />

#### Les avantages :

* Les prospects, qui finissent par installer l'app, sont plus engagés.
* Les services plus complexes (par exemple, les services financiers) nécessitent davantage d'explications pour convertir leurs clients potentiels, ce que permettent les pages de renvoi.

<div id="the-downsides" />

#### Les inconvénients :

* Le tunnel plus long réduit le nombre final de prospects convertis.
* L'attribution est plus difficile sur le plan technique.

<div id="the-challenges-of-mobile-attribution-on-landing-pages" />

## Les défis de l'attribution mobile sur les pages de renvoi

* **Les différentes sources média requièrent des méthodes différentes** pour compléter le scénario de la page de renvoi avec les données d'attribution correctes.
* Le **modèle d'attribution au dernier clic peut entraîner la perte d'une attribution correcte** si la page de renvoi possède ses propres liens d'attribution.
* **Les visiteurs directs du site web sont enregistrés comme des visiteurs organiques**, sauf si la page de renvoi possède ses propres liens d'attribution.
* **Les visiteurs de bureau sont enregistrés comme des visiteurs organiques**, sauf si la page de destination dispose d'une méthode d'enregistrement des conversions en utilisateurs mobiles.

<div id="the-solution" />

## La solution

Pour résoudre les problèmes d'attribution mentionnés ci-dessus, vous devez implémenter un flux javascript dans votre page de renvoi. Nous vous proposons un exemple de script à utiliser, veillez l’adapter à vos besoins.

Dans certains cas, vous devez également adapter vos campagnes.

Les scénarios ci-dessous couvrent les exigences pour tous les cas possibles de sources média.

<div id="landing-page-scenarios" />

## Scénarios de page de renvoi

Suivez les instructions de mise en œuvre ci-dessous **pour toutes les sources média** qui envoient des prospects vers vos pages de renvoi.

<div id="facebook-ads-crossplatform-attribution" />

<Accordion title="Meta ads : attribution multiplate-forme">

#### Description :

Meta ads est un SRN qui n'utilise pas de liens d'attribution externes.

Lors du premier lancement de l'app, AppsFlyer demande à Meta ads si l'utilisateur s'est déjà engagé (au cours des 28 derniers jours) avec une publicité de l'annonceur sur l'app Facebook. Si c'est le cas, les publicités Meta ads s'auto-attribuent.

Les publicités Meta ads sont également multiplate-formes, ce qui signifie que l'utilisateur peut interagir avec n'importe quel type de campagne, mobile ou non, sur n'importe quelle plate-forme, afin d'être auto-attribué par Meta ads.

#### Conclusion :

Un utilisateur potentiel avec l'ID d'appareil disponible, provenant de l'app Facebook vers une page de renvoi, est correctement attribué à Meta ads. Cela se produit indépendamment du nouveau clic enregistré sur la page de renvoi.  
Toutefois, lorsque les utilisateurs choisissent de ne pas partager leur ID d’appareil, comme cela devrait être le cas pour les utilisateurs d'iOS 14 au cours de l'année 2021, l'attribution multiplate-forme de Meta ads risque de ne plus fonctionner.

**Lorsque le partage de l'ID d'appareil devient facultatif, utilisez la [méthode Autres SRN](/docs/deprecated-mobile-landing-page-attribution-script#other-srns-add-parameter) pour Meta ads.**

* Les nouveaux utilisateurs qui partagent leur ID d’appareil se verront attribuer correctement les publicités Meta ads.
* Les nouveaux utilisateurs qui ne partagent pas leur ID d’appareil seront attribués à "Facebook\_LP".

#### Instructions :

1. Sur votre compte Meta ads, créez une **campagne Trafic ou Conversions avec l'attribution mobile activée**, en envoyant les prospects sur votre page de renvoi.
2. Bouton de téléchargement de la page de renvoi Android - lien direct vers Google Play.
3. Bouton de téléchargement iOS de la page de renvoi - lien direct vers iTunes (OU lien d'attribution **sans l'ID d’appareil**).

<div id="what-the-script-does" />

#### Ce que fait le script

Le script de la page de renvoi n'apporte aucune modification. Le script est conçu pour détecter un utilisateur venant de l'app Facebook. Si c'est le cas, il ne fait rien. Les liens directs de la page de renvoi vers les app store restent inchangés. Cela empêche l'enregistrement d'un autre clic, ce qui pourrait affecter le CTR.

Dans le script, recherchez une méthode appelée ***isFacebook()*** pour en savoir plus sur ce que fait le script pour les utilisateurs venant de l'app Facebook.

</Accordion>

<div id="google-ads-gclid-offline-conversion-upload" />

<Accordion title="Google Ads : GCLID + téléchargement de la conversion hors ligne">

#### Description :

Le processus habituel d'attribution de l'installation pour les campagnes Google Ads exige que les clients potentiels qui cliquent soient redirigés vers l'URL de la page de vente de l'app.

Par conséquent, lorsque vous redirigez des prospects de Google Ads vers une page de renvoi, utilisez un médiateur pour faire le lien entre l'installation mobile et le clic original de la campagne Google Ads non mobile.

#### Conclusion :

La solution pour Google Ads se compose de 2 parties.

La première partie permet d'**attribuer à AppsFlyer** les utilisateurs mobiles qui arrivent sur la page de renvoi depuis Google et qui installent l'app à partir de là. Il faut marquer les URL de clics à partir de Google, les identifier sur la page de renvoi et créer un OneLink dynamique avec les données de l'URL.

La deuxième partie consiste à **informer Google Ads** de ces installations mobiles, en utilisant la méthode de téléchargement des conversions hors ligne de Google.

<div id="note" />

> 📘 **Remarque**
>
> Cette solution GCLID n’est pas officiellement prise en charge ou recommandée par Google.
> Si jamais Google déprécie le paramètre GCLID, nous modifierons le script pour prendre en charge les modifications.
> Nous vous recommandons de suivre cet article en cliquant sur le bouton ***Suivre*** dans l'en-tête, afin d'être informé de toute mise à jour de l'article ou du script joint.

<div id="instructions-1" />

#### Instructions :

Partie 1 - Attribution à Google Ads sur AppsFlyer

Dans le tableau de bord de Google, **activez le marquage automatique** <Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">(voici comment).</Anchor>

Lorsque le marquage automatique est activé, l**'URL de la page de renvoi contient le paramètre *GCLID.***

Exemple d'URL : `http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}`

Sur votre page de renvoi -

1. Activer la fonction Javascript ***generateUrl***
2. La fonction (voir ci-dessous) recherche le ***GCLID*** et crée une URL OnleLink longue contenant sa valeur sous le paramètre af\_sub1 (vous pouvez utiliser n'importe lequel des <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">paramètres d'abonné</Anchor> af\_sub1 - af\_sub5).
3. Le bouton de téléchargement de la page de renvoi utilise l'URL OneLink générée.  
   Exemple d'URL OneLink : `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}`
4. Les nouveaux utilisateurs mobiles sont attribués à la source média **google\_lp** et à la campagne CAMPAIGN\_NAME (facultatif).
5. Aucun postback n'est envoyé à la source média

À ce stade, les installations sont signalées dans AppsFlyer dans la source media ***google\_lp*** avec le GCLID, mais pas dans Google Ads.

Partie 2 - Téléchargement des installations sur Google en tant que conversions hors ligne

**Cette étape n'est nécessaire que si vous souhaitez que les conversions soient enregistrées dans la plate-forme Google Ads.**

Pour les utilisateurs attribués à google\_lp, les données brutes d'AppsFlyer affichent désormais la valeur GCLID dans la colonne **af\_sub1.** Le GCLID est nécessaire pour télécharger les conversions hors ligne dans Google Ads. Vous pouvez trouver plus d'informations sur le processus <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">ici</Anchor>).

Les conversions peuvent être téléchargées manuellement ou via une API Adwords (plus d'informations sur l'API <Anchor target="_blank" href="https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions">ici)</Anchor>.

Vous pouvez exporter les CSV avec ces informations depuis votre compte AppsFlyer, ou vous pouvez obtenir ces données à partir de l'API Push en temps réel pour chaque installation.

<div id="tip" />

> 👍 **Astuce**
>
> Vous pouvez également voir les mots-clés recherchés par vos utilisateurs dans les données brutes d'AppsFlyer, de la même manière que vous obtenez le GCLID :
>
> 1. Pour l'enregistrement des mots-clés, vous devez inclure le <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2375447">paramètre ValueTrack</Anchor> du mot-clé dans l'URL finale de Google Ads vers la page de destination.
>    Exemple d'URL : `http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}&keyword={USER_KEYWORD}`
> 2. La fonction Javascript (voir ci-dessous) recherche le paramètre ***mot-clé***
> 3. La valeur est ajoutée à l'URL OneLink générée sous af\_keywords
>    Exemple d'URL OneLink : `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}&af_keywords={USER_PARSED_KEYWORD}`
>
> La fonction JS ci-dessous contient déjà le code permettant d'analyser le paramètre de mot-clé.

<div id="what-the-script-does-1" />

#### Ce que fait le script

Google Ads comportent un paramètre gclid. Le script recherche ce paramètre dans l'URL de la page de renvoi. S'il le voit, il crée le OneLink de manière à indiquer que l'utilisateur provient de Google Ads. Le script place ensuite le OneLink comme lien derrière les boutons de téléchargement sur la page de renvoi.

Dans le script, recherchez **gclidValue** pour savoir comment le script détecte les utilisateurs provenant de Google Ads et crée le OneLink en conséquence.

</Accordion>

<div id="other-srns-add-parameter" />

<Accordion title="Autres SRN : ajouter un paramètre">

#### Description :

D'autres <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#srn-intégrés-à-appsflyer">SRN</Anchor>, par exemple Snapchat ou Twitter, ne sont pas multiplate-formes comme Meta ads, et nécessitent un peu de travail pour que vos utilisateurs mobiles leur soient attribués.

Vos campagnes avec d'autres SRN conduisent vos utilisateurs à la page de renvoi, et vous êtes facturé en fonction des clics, sans rapport avec les utilisateurs mobiles dérivés.

#### Conclusion :

Lorsque vous définissez l'URL de la page de renvoi d'une campagne sur les SRN (en plus de Meta ads et Google ads), ajoutez un paramètre ID partenaire à l'URL, qui indique le SRN d'origine.  
La page de renvoi lance un JavaScript (voir ci-dessous) qui analyse ce paramètre et crée une URL OneLink qui contient la valeur de l'ID du partenaire. Lorsque les utilisateurs mobiles cliquent sur ce OneLink et l'installent, ils sont attribués à la source média indiquée.

<div id="instructions-2" />

#### Instructions :

Sur votre compte SRN -

1. Créer une campagne non mobile
2. Lors de la définition de l'URL de la page de renvoi, ajoutez un paramètre ID partenaire + page de renvoi à l'URL (qui n'est pas un lien d'attribution AF). Le format est le suivant : "***&af\_pid=srn\_lp***" (voir l'exemple ci-dessous).

Sur votre page de renvoi -

1. Activer la fonction Javascript ***generateUrl***
2. La fonction recherche le paramètre ***af\_pid*** et construit une URL OneLink contenant sa valeur dans le paramètre ***pid***.
3. Le bouton de téléchargement de la page de renvoi utilise l'URL OneLink générée
4. Les nouveaux utilisateurs mobiles sont attribués à la source média personnalisée ID partenaire + page de renvoi.
5. Aucun postback n'est envoyé à la source média

Si vous spécifiez le vrai nom du SRN, par exemple twitter\_int, un postback peut être envoyé à ce SRN. Cela pourrait entraîner une double facturation. Voir la note ci-dessous pour des noms alternatifs.

Le script lui-même contient une logique qui vous empêche d'utiliser ces noms. Recherchez `var SRNs` dans le script. Vous devriez voir une liste de noms SRN et une condition qui vérifie si `pidValue` est l'un de ces noms. Supprimez cette logique après avoir testé le script.

<div id="note-1" />

> 📘 **Remarque**
>
> Si vous envoyez des utilisateurs vers votre page de renvoi, nous vous recommandons d'inclure le paramètre suivant dans l'URL de votre page :
>
> * Pour Twitter : utilisez "***&af\_pid=twitter\_lp***"
> * Pour Snapchat : utilisez "***&af\_pid=snapchat\_lp***"
> * Pour Doubleclick : utilisez "***&af\_pid=doubleclick\_lp***"
> * Pour Meta ads Post (non rémunéré) : utilisez "***&af\_pid=fbpost\_lp***"
> * Pour Oath (anciennement Yahoo Gemini) : utilisez "***&af\_pid=oath\_lp***"

<div id="what-the-script-does-2" />

#### Ce que fait le script

Le script voit le paramètre af\_pid dans l'URL de la page de renvoi et en conclut que l'utilisateur provient d'un SRN ou d'un autre réseau personnalisé. Le script crée un OneLink en conséquence et le définit comme le lien derrière le bouton de téléchargement sur la page de renvoi.

Pour en savoir plus sur l'action du script, recherchez **pidValue** dans le script.

</Accordion>

<div id="attribution-links-redirect-with-af_r" />

<Accordion title="Liens d'attribution : redirection avec af_r">

#### Description :

Des liens d'attribution sont utilisés pour toute source média qui n'est pas un SRN. Cela inclut des milliers de partenaires intégrés et tout média propre que vous souhaitez attribuer.

Heureusement, la solution pour l'attribution de la page de destination lors de l'utilisation des liens d'attribution AppsFlyer est simple (et similaire à la solution pour Meta ads).

#### Conclusion :

le lien d'attribution redirige le prospect vers une page de renvoi, ce qui permet d'assurer une attribution correcte (si une installation mobile suit).

Il ne reste plus qu'à NE PAS empêcher l'attribution correcte avec un dernier clic.

<div id="instructions-3" />

#### Instructions :

1. <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink">Créez le lien d'attribution de</Anchor> la source média
2. Ajoutez au lien d'attribution le <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection">paramètre de la page de renvoi</Anchor> menant à votre page de renvoi.
3. Ajoutez `&af_redirect=true` à la valeur de la page de renvoi sous **tous les paramètres de redirection** (c'est-à-dire af\_r, af\_ios\_url et af\_android\_url) dans le lien d'attribution.  
   Example : `https://yourapp.onelink.me/abcd?pid=email&c={CAMPAIGN_NAME}&af_r=http://www.yoursite.com/yourlandingpage?af_redirect=true`
4. **Facultatif** - ajoutez l'ID d’appareil (GAID / IDFA) au lien d'attribution pour permettre l'attribution par correspondance d'ID au lieu de la modélisation probabiliste.
5. Bouton de téléchargement de la page de renvoi Android - lien direct vers Google Play
6. Bouton de téléchargement de la page de renvoi iOS - lien direct vers iTunes  

   <div id="note-2" />

   > 📘 **Remarque**
   >
   > Le script et la page d'exemple HTML offrent la possibilité de définir un seul bouton de téléchargement pour Android et iOS. Lisez les commentaires du script pour savoir comment le mettre en œuvre.


<div id="what-the-script-does-3" />

#### Ce que fait le script

Le script recherche le paramètre **af\_redirect** dans l'URL de la page de renvoi. S'il le voit, il ne modifie pas les boutons de téléchargement de la page de renvoi. Le paramètre af\_redirect indique que l'utilisateur atteint la page de renvoi après un clic. Il n'est donc pas nécessaire d'ajouter des liens d'attribution.

Pour en savoir plus sur ce que fait le script pour traiter les cas où les utilisateurs atteignent la page de renvoi après avoir cliqué sur un lien d'attribution, voir la méthode **isAFLink()** dans le script.

</Accordion>

<div id="links-with-utm-parameters-dynamic-onelink" />

<Accordion title="Liens avec paramètres utm : OneLink dynamique">

#### Description

Vous pouvez avoir des sources de trafic qui redirigent les utilisateurs vers votre page de renvoi en utilisant des liens avec des paramètres UTM.

#### Conclusion :

Si l'URL d'origine n'est PAS un lien d'attribution AppsFlyer, le script recherche les paramètres ***utm\_source*** et ***utm\_campaign*** dans le lien. S'ils existent, le script prépare une URL OneLink qui les contient respectivement en tant que nom de la source média (pid) et nom de la campagne (c).

Notez que pour les liens d'attribution AppsFlyer, qui contiennent également des paramètres UTM, ce sont les paramètres AppsFlyer qui sont utilisés, et non les paramètres UTM.

<div id="instructions-4" />

#### Instructions :

Dans la source média -

1. Assurez-vous que l'option ***utm\_source*** existe dans le lien.
2. ***utm\_campaign*** est facultatif mais fortement recommandé.

Sur votre page de renvoi -

1. Activer la fonction Javascript ***generateUrl***
2. La fonction recherche les paramètres ***utm\_source*** et ***utm\_campaign*** et construit une URL OneLink contenant leurs valeurs
3. Le bouton de téléchargement de la page de renvoi utilise l'URL OneLink générée
4. Les nouveaux utilisateurs de téléphones mobiles sont attribués à la valeur de ***utm\_source*** en tant que source média
5. Aucun postback n'est envoyé à la source média.

<div id="what-the-script-does-4" />

#### Ce que fait le script

Le script recherche les paramètres UTM dans l'URL de la page de renvoi. S'il en trouve, il les convertit en paramètres OneLink. De cette manière, les informations relatives à la campagne sont reportées sur l'attribution finale.

</Accordion>

<div id="mobile-organic-visitors-onelink-with-pidwebsite" />

<Accordion title="Visiteurs organiques mobiles : OneLink avec pid=website">

#### Description

Les visiteurs organiques mobiles sont, par définition, des prospects web mobiles directs provenant de sources inconnues. Ils visitent rarement des pages de renvoi dédiées, mais peuvent constituer la grande majorité des installations mobiles provenant du site web de l'annonceur.

#### Conclusion :

Si votre site web génère un volume important de trafic organique mobile, il est fortement recommandé d'enregistrer les données d'attribution de votre propre trafic.

<div id="instructions-5" />

#### Instructions :

Afin d'attirer les visiteurs organiques mobiles, le site web doit comporter les boutons ***Télécharger*** ou ***Installer*** incluant un lien d'attribution OneLink. OneLink permet de diagnostiquer le type d'appareil et de rediriger l'utilisateur vers l’app store approprié.

Pour savoir comment créer des URL OneLink, <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">cliquez ici.</Anchor>

<div id="tip-1" />

> 👍 **Astuce**
>
> Ajoutez "&pid=website" à votre lien d'attribution pour attribuer tous ces visiteurs à votre site web.
> Dans chaque page de votre site web qui comporte un bouton de téléchargement/d’installation avec un lien d'attribution, ajoutez "&c=`{PAGE NAME}`". Cela peut vous aider à identifier les pages les plus et les moins performantes de votre site web.

<div id="what-the-script-does-5" />

#### Ce que fait le script

Après avoir épuisé toutes les autres options, le script détermine que l'utilisateur est un utilisateur organique qui ne provient d'aucune campagne. Le script crée un OneLink qui le reflète et le place comme lien derrière le bouton de téléchargement sur la page de renvoi.

</Accordion>

<div id="desktop-visitors-telephoneemail-form" />

<Accordion title="Utilisateurs d’ordinateurs de bureau : formulaire téléphonique/email">

#### Description

Toutes les options décrites ci-dessus supposent que les utilisateurs se servent d'appareils mobiles pour s'engager dans la campagne et la page de renvoi.

Mais qu'en est-il des utilisateurs d'ordinateurs de bureau ?

Les utilisateurs d'ordinateurs de bureau peuvent arriver sur votre page de renvoi/site web, puis visiter indépendamment l’app store avec leurs appareils mobiles et installer l'app mobile. Sans l'engagement précédent avec les appareils mobiles, il est impossible d'attribuer ces utilisateurs, et ils sont donc étiquetés comme organiques.

#### Conclusion :

Pour résoudre ce problème d'attribution, vous pouvez utiliser un **formulaire de téléchargement de texte sur votre page de renvoi**, uniquement pour les utilisateurs d'ordinateurs de bureau. Il faut ensuite envoyer à l'appareil mobile un SMS ou un e-mail contenant l'URL OneLink.

<div id="instructions-6" />

#### Instructions :

1. Identifier les utilisateur d’ordinateurs de bureau
2. Lorsque votre utilisateur tape son numéro de téléphone, envoyez-lui par SMS un lien vers votre app, avec une URL courte OneLink. Vous pouvez également lui demander son e-mail pour lui envoyer des messages de téléchargement d'app.
3. L'utilisation de OneLink est cruciale ici, car la plate-forme de l'appareil mobile n'est pas connue lors de l'envoi du message aux utilisateurs. Les fonctionnalités de diagnostic et de redirection de OneLink s'en chargent pour vous.
4. Ajoutez &pid=desktop\_website à l'URL OneLink pour identifier cette source.
5. Ajoutez &c=`{PAGE NAME}` pour vous aider à trouver les pages les plus et les moins performantes de votre site web pour les utilisateurs d'ordinateurs de bureau.

<div id="what-the-script-does-6" />

#### Ce que fait le script

Le script détecte l'appareil ou la plate-forme sur lequel l'utilisateur se trouve. S'il s'agit d'un ordinateur de bureau, le script renvoie un lien vers l'URL d'un formulaire web et le place derrière les boutons de téléchargement. Lorsque l'utilisateur clique sur télécharger, il est envoyé vers un formulaire web où il remplit ses coordonnées afin de recevoir un SMS ou un e-mail contenant un lien pour télécharger l'app.

Vous pouvez créer le formulaire web et le fournir à l'URL dans le script.  Pour en savoir plus, recherchez **isMobileDevice()** dans le script.

</Accordion>

<div id="landing-page-javascript" />

## Page de renvoi javascript

Vous trouverez ci-dessous le code d'implémentation du javascript qui permet d'attribuer les sources média et les campagnes dans les scénarios de pages de renvoi. **Si vous souhaitez disposer de données supplémentaires telles que les adsets et les identifiants publicitaires, vous devez procéder aux ajustements nécessaires dans le script.**

Pour plus de commodité, vous pouvez également télécharger l'exemple de page de renvoi ci-joint.

Sous le code, vous trouverez les instructions pour l'adapter aux besoins de votre page de renvoi.

<div id="the-script" />

<Accordion title="Le script">

Tenez compte des éléments suivants avant de mettre en œuvre le script :

* Le texte est proposé à titre d'exemple uniquement. Il couvre le flux commun de la page de renvoi à l'attribution. Adaptez le script à vos besoins.
* Le script recherche des paramètres spécifiques dans l'URL de la page de renvoi, comme la source média, la campagne, les mots-clés, etc. Si vous souhaitez ajouter d'autres paramètres tels que l'identifiant du site et les ad sets, vous devez modifier le script en conséquence.

```javascript
//Returns the value of a parameter existing in the page's URL or ' ' if not exists.
function getParameterFromURL(name, url) {
  if (!url) url = window.location.href;
  name = name.replace(/[\[\]]/g, '\\$&');
  var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
    results = regex.exec(url);
  if (!results) return null;
  if (!results[2]) return '';
  return decodeURIComponent(results[2].replace(/\+/g, ' '));
}

function isMobileDevice() {
  return (typeof window.orientation !== "undefined") || (navigator.userAgent.indexOf('IEMobile') !== -1);
}

function getMobileOperatingSystem() {
  var userAgent = navigator.userAgent || navigator.vendor || window.opera;
  if (userAgent) {
    if (/android/i.test(userAgent)) {
      return "Android";
    }

    // iOS detection from: http://stackoverflow.com/a/9039885/177710
    if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
      return "iOS";
    }
  }
  return "unknown";
}

function isAFLink() {
  return getParameterFromURL('af_redirect');
}

// Note - when device ID sharing becomes optional stop calling this method (or always return false)
function isFacebook() {
  if (document.referrer && document.referrer != "") {
    return document.referrer.toLowerCase().includes('facebook');
  } else {
    return false;
  }
}

// generateUrl returns the URL to use behind the iOS and Android "Download" buttons on a landing page, based on the source of the page visitor.
// By default these buttons should direct to the apps' pages on iTunes and Google Play.
// If these links should be kept with no change, generateUrl returns ' '.
// Otherwise, generateUrl returns the URL to be used under BOTH buttons (a single app download button could also be used in this case).
// Parameters: isDebug - if true, alerts are issued for each of the cases, otherwise not.  	 
function generateUrl(isDebug) {
  var oneLinkURL = 'https://yourapp.onelink.me/abcd';   // **** Replace with your own basic OneLink URL ****
  var webFormURL = 'https://yoursite.com/webform.html'; // **** Replace with your own web form URL for getting the user's email or SMS ****
  var finalURL = "";
  var partnerIDParam = '?pid=';

  var campaignValue;
  if (getParameterFromURL('c')) {
    campaignValue = getParameterFromURL('c');
  } else if (getParameterFromURL('utm_campaign')) {
    campaignValue = getParameterFromURL('utm_campaign');
  } else if (document.getElementsByTagName('title')[0]) {
    campaignValue = document.getElementsByTagName('title')[0].innerText;
  } else {
    campaignValue = 'unknown';
  }
  var campaignParam = '&c=';
  var gclidParam = '&af_sub1=';
  var gclidValue = getParameterFromURL('gclid');
  var kwParam = '&af_keywords=';
  var pidValue;
  var kwValue = getParameterFromURL('keyword');

  if (getParameterFromURL('af_pid')) {
    pidValue = getParameterFromURL('af_pid');
  } else if (getParameterFromURL('utm_source')) {
    pidValue = getParameterFromURL('utm_source');
  }

  // Prevent the use of real SRN names. Remove this part after you are done testing the script.
    var SRNs = [
    'twitter_int',
    'facebook_int',
    'snapchat_int',
    'doubleclick_int',
    'yahoogemini_int',
    'yahoojapan_int',
  ];

  if (SRNs.includes(pidValue)) {
  	alert("DO NOT USE NAMES OF SRNS IN af_pid or utm_source - use the names listed in Other SRNs: Add Parameter section in the landing page article\nhttps://support.appsflyer.com/hc/en-us/articles/360000677217#other-srns-add-parameter");
    return;
  }

  // Desktop user
  if (!isMobileDevice()) {
    return webFormURL;
  }

  // User was redirected using af_r parameter on an AppsFlyer attribution link
  if (isAFLink()) {
    if (isDebug) {
      alert("This user comes from AppsFlyer by redirection and is ready to be attributed. \nKeep direct app store links.");
    }
    return; // in this case, the original store links in the install buttons stay the same

    /*
    If you want one install button in the landing page that serves both iOS and Android, uncomment the code below
    The code identifies the operating system and returns the relevant direct link to Google Play or iTunes

    if (getMobileOperatingSystem() === 'Android') {
      return 'direct link to Google Play';
    } 

    if (getMobileOperatingSystem() === 'iOS') {
      return 'direct link to iTunes';
    }
    */
  }

  // Google Ads
  if (gclidValue) {
    partnerIDParam += 'google_lp';
    campaignParam += campaignValue;
    gclidParam += gclidValue
    if (!kwValue) {
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam;
      if (isDebug) {
        alert("This user comes from Google AdWords\n " + finalURL);
      }
      return finalURL;

    } else { // Google Ads with KW
      kwParam += kwValue;
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam + kwParam;
      if (isDebug) {
        alert("This user comes from Google AdWords - there is a keyword associated with the ad\n " + finalURL);
      }
      return finalURL;
    }

  // Other SRNs and custom networks  
  } else if (pidValue) {
    campaignParam += campaignValue;
    partnerIDParam += pidValue;
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("This user comes the SRN or custom network " + pidValue + "\n" + finalURL);
    }
    return finalURL;
  } else if (isFacebook()) {
    if (isDebug) {
      alert("This user comes from a paid Facebook ad - don't do anything. \nKeep direct app store links.");
    }
    return ' ';

  } else { // organic mobile user
    campaignParam += campaignValue;
    partnerIDParam += 'website'; //**** Replace value if you wish organic users to be attributed to another media source than 'website' ****
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("This user comes from an unknown mobile source.\n The user would be attributed to media source 'website' and to the campaign " + campaignParam + "\n" + finalURL);
    }
    return finalURL;
  }
}
```

</Accordion>

<div id="html-sample-for-landing-page" />

<Accordion title="Exemple HTML pour la page de renvoi">

```html Markup
<html>
<head>
  <title>Landing Page</title>
</head>
<body>
  <h1>Landing Page</h1>
  <!-- By default, the install buttons should have direct links to the stores -->
  <div>
    <a id="andrd_link" href="https://play.google.com/store/apps/details?id=com.appsflyer.sampleapp"><img src="/images/andrd.png"alt=""></a>
  </div>
  <div>
    <a id="ios_link" href="https://itunes.apple.com/us/app/id3********"><img src="/images/ios.png" alt=""></a>
  </div>
  <!-- If you want one button to serve both Android and iOS, use the code below instead
  <a id="store_link" href=""><img src="download.png" alt=""></a>
  -->
  <script type="text/javascript" src="/landing-page-test.js"></script>
  <script type="text/javascript">
    window.onload = function () {
      var url = generateUrl(true);

      // onelink is generated
      if (url) {
        document.getElementById('andrd_link').setAttribute('href', url);
        document.getElementById('ios_link').setAttribute('href', url);
      }

      //otherwise, if onelink is not generated it means that the user is redirected
      // and the store links in the buttons stay the same

      /* for the one button solution for both Android and iOS, use the code below instead

      document.getElementById('store_link').setAttribute('href', url);

      */

    };
  </script>
</body>

</html>
```

</Accordion>

<div id="tip-2" />

> 👍 **Astuce**
>
> Vous pouvez implémenter le snippet javascript à l'aide de Google Tag Manager. Google Tag Manager vous permet de contrôler plus facilement quand et où le javascript de la page de renvoi doit être utilisé.

<div id="instructions-7" />

### Instructions

1. Activez la fonction ***generateUrl*** au chargement de n'importe quelle page de votre site web, sur laquelle les visiteurs peuvent atterrir directement, et qui propose un bouton ***Téléchargement*** pour votre/vos app(s) mobile(s).  

   <div id="important" />

   > 🚧 **Attention !**
   >
   > **Par défaut, les boutons de *téléchargement* doivent renvoyer aux pages des apps sur iTunes et Google Play.** Si ces liens sont conservés sans changement (par exemple, le visiteur du lien d'attribution AF ou de Meta ads), ***generateUrl*** renvoie ' '. Sinon, il renvoie l'URL à utiliser avec les DEUX boutons de téléchargement (un seul bouton ***Télécharger*** pourrait également être utilisé dans ce cas pour couvrir les deux apps avec OneLink).

2. Remplacer la valeur du paramètre***oneLinkURL*** par votre propre URL de base OneLink, au format exact de l'espace réservé `https://yourapp.onelink.me/abcd`.  
   OBLIGATOIRE pour attribuer les visiteurs de tous les SRN (sauf les publicités payées Meta ads) et pour les visiteurs mobiles organiques.
3. Remplacez la valeur du paramètre ***webFormURL*** par votre propre lien de formulaire web. Le formulaire web doit pouvoir recevoir l'e-mail ou le SMS de l'utilisateur et envoyer à son appareil mobile un message contenant une URL OneLink pour le téléchargement de l'app.  
   OBLIGATOIRE pour attribuer les visiteurs de bureau.
4. Remplacez le paramètre ***partnerIDParam*** si vous souhaitez que les utilisateurs mobiles organiques soient attribués à une autre source média que le site web.
5. Par défaut, les utilisateurs se voient attribuer la page web sur laquelle ils se trouvent lorsqu'ils cliquent sur le bouton ***Télécharger*** à moins qu'un autre nom de campagne ne soit spécifié dans l'URL de la page de renvoi (`&c={CAMPAIGN_NAME}`). Pour modifier cela, remplacez la valeur du paramètre ***campaignParam***.  
   Facultatif pour TOUS les scénarios, à l'exception des publicités payantes Meta ads.

<div id="viewing-the-results" />

## Visualisation des résultats

<Image align="center" alt="dashboard_landing_page_results.png" src="https://files.readme.io/29d7b6b096687a1f106efa4dcfc65ab1f550976516c87c3ffafde29f852855bb-360001342158.png" />

Comme pour toute source média, vous pouvez visualiser les résultats de votre page de renvoi sur le tableau de bord de votre app, dans les données brutes ou via les API d'AppsFlyer.

Si votre tunnel de marketing mobile mène toujours à votre page de renvoi, ces sources média représentent ce qui suit :

| **Source** | **Description** |
| --- | --- |
| **organique** | Les utilisateurs qui ne sont pas passés par la page de renvoi ou qui n'y ont pas participé. Par ailleurs, les utilisateurs qui se sont engagés mais qui n'ont pas été attribués pour diverses raisons, par exemple parce qu'ils ont passé la fenêtre d'attribution rétrospective avant de lancer l'app. |
| **site web** | Utilisateurs mobiles organiques visitant votre page de renvoi/site web et installant l’app par la suite. |
| **Meta ads** | Utilisateurs provenant des publicités Meta ads payantes |
| **fbpost\_lp** | Utilisateurs provenant de publicités virales non payées de Meta ads |
| **google\_lp** | Utilisateurs provenant de Google ads |
| **[SRN]\_lp** | Utilisateurs d'autres SRN, c'est-à-dire Twitter (twitter\_lp), Snapchat (snapchat\_lp), Doubleclick (doubleclick\_lp) ou Oath (oath\_lp) |
| **ID de partenaire intégré** | Utilisateurs provenant d'une publicité d'un partenaire intégré qui utilise le lien d'attribution d'AppsFlyer. Par exemple, inmobi\_int, tapjoy\_int |
| **ordinateur de bureau** | Les utilisateurs d'ordinateurs de bureau remplissent le formulaire web et procèdent à l'installation après avoir cliqué sur le SMS ou l'e-mail envoyé à leur appareil mobile. |
| **Autres sources** | Utilisateurs provenant de sources média détenues, qui utilisent les liens d'attribution d'AppsFlyer. Par exemple, email, sms, blog\_post, etc. |

<div id="onelink-for-landing-page-solution" />

## Solution OneLink pour les pages de renvoi

OneLink™ est un lien d'attribution unique d'AppsFlyer utilisé pour la détection et la redirection des appareils, ou pour la création de deep linking.

La solution de <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">page de renvoi pour les apps sociales</Anchor> nécessite que l'annonceur dispose d'une URL OneLink de base. Les utilisateurs qui cliquent sur les publicités dans les apps de réseaux sociaux sont ensuite redirigés vers une page de renvoi générée par AppsFlyer. De là, ils peuvent être deep linkés, ou continuer à installer l'app.

AppsFlyer fournit une variété de templates de page de d'accueil d'apps de réseaux sociaux. La position des éléments dans les templates est fixe, mais les éléments en eux-mêmes sont personnalisables, y compris l'image ou la couleur d'arrière-plan, les titres, les textes, les images, les boutons, les balises, etc.

Si vous n'avez pas encore mis en place OneLink pour votre app :

1. Configurez le <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#procédures">template OneLink</Anchor>.
2. Créez une <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink">URL OneLink</Anchor> basée sur le template.
3. Dans le script, remplacez https://yourapp.onelink.me/abcd par votre URL OneLink.

<div data-zendesk-anchors="the-upsides=les-avantages- the-downsides=les-inconv%C3%A9nients- the-challenges-of-mobile-attribution-on-landing-pages=les-d%C3%A9fis-de-lattribution-mobile-sur-les-pages-de-renvoi the-solution=la-solution landing-page-scenarios=sc%C3%A9narios-de-page-de-renvoi instructions=instructions- what-the-script-does=ce-que-fait-le-script description::7888dd9d=description-1 conclusion::11bed45=conclusion-1 instructions::5aa3290f=instructions--1 what-the-script-does::2a675257=ce-que-fait-le-script-1 description::650e3f28=description-2 conclusion::a982e4bd=conclusion-2 instructions::afffc83f=instructions--2 what-the-script-does::3fd4ce35=ce-que-fait-le-script-2 description::9c3fcdaa=description-3 conclusion::bf993a93=conclusion-3 instructions::350b4cb1=instructions--3 what-the-script-does::3dda504d=ce-que-fait-le-script-3 description::5150e1b5=description-4 conclusion::d51c1aec=conclusion-4 instructions::e083609=instructions--4 what-the-script-does::85ffec6c=ce-que-fait-le-script-4 description::f5a2038b=description-5 conclusion::4593a93c=conclusion-5 instructions::2e4dd2ee=instructions--5 what-the-script-does::d6370587=ce-que-fait-le-script-5 description::e20640cf=description-6 conclusion::c818491=conclusion-6 instructions::ba61ae3e=instructions--6 what-the-script-does::3668d917=ce-que-fait-le-script-6 landing-page-javascript=page-de-renvoi-javascript instructions::10da52a9=instructions viewing-the-results=visualisation-des-r%C3%A9sultats onelink-for-landing-page-solution=solution-onelink-pour-les-pages-de-renvoi" />
