---
title: Réseaux auto-reporting (SRN)
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Ad Networks
    - srn
    - Self-reporting
    - networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-10-22T05:21:45Z'
  edited_at: '2023-11-20T14:48:04Z'
  id: 360001546905
  locale: fr
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/fr/articles/360001546905
---
> **En bref :** tout savoir sur les réseaux sel reporting (SRN) - attribution, deep linking, recommandations selon l'iOS, et FAQ.

## SRN intégrés à AppsFlyer

| **SRN** | **Logo** |
| --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/apple-ads-integration-setup">Apple Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/iossearchads.png" width="131px" /> |
| <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png?v=1" width="47px" /> |
| Google Marketing Platform | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png?v=1" width="45px" /> |
| <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-integration-setup">Meta Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/facebook.png?v=1" width="67px" /> |
| <Anchor target="_blank" href="/marketers/fr/docs/snapchat-advanced-srn-integration-setup">Snapchat</Anchor> | <Image alt="snapchat_logo.png" src="https://files.readme.io/c9b62d55d5c1497011d7411a21dca6f1668308bbe2806ab238b71742c421b182-32259457816209.png" width="41px" /> |
| Tencent Social Ads | <Image alt="blobid0.jpg" src="https://files.readme.io/6d6e9661c9d81f80ffeedfdf4850a84f3cc183faa49a514d1d3bb116641738da-32259428896017.jpg" width="80px" /> |
| <Anchor target="_blank" href="/marketers/fr/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Business - SRN avancé</Anchor> | <Image alt="tiktok_logo.png" src="https://files.readme.io/307a95d0d848bd9e692b9a1996dffc11449a25cac1c7deeb7573b566506aeb73-15166720478993.png" width="106px" /> |
| <Anchor target="_blank" href="/marketers/fr/docs/x-ads-formerly-twitter-ads-setup-guide-overview">Twitter</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/twitter.png?v=1" width="40px" /> |
| <Anchor target="_blank" href="/marketers/fr/docs/yahoo-integration-setup">Yahoo (plates-formes publicitaires/Yahoo Gemini)</Anchor> | <Image alt="verizonmedia.png" src="https://files.readme.io/36291ff556d07a5dbf2ae8ff693ea33d21dae9e0518a94b251202634a24049cf-32259428916369.png" width="76px" /> |
| <Anchor target="_blank" href="/marketers/fr/docs/yahoo-japan-search-ads-campaign-configuration">Yahoo! Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yahoojapansearch.png" width="139px" /> |

**Remarque** : les SRN appliquent des <Anchor target="_blank" href="/marketers/fr/docs/user-level-data-retention">restrictions de retention et d'utilisation des données de niveau utilisateur.</Anchor>

## Attribution

Contrairement aux non-SRN (réseaux publicitaires), qui utilisent des liens d'attribution pour signaler les événements à AppsFlyer, les SRN s'attribuent eux-mêmes via l'ID d'appareil lorsque AppsFlyer les informe d'une installation.

L'attribution AppsFlyer pour les SRN et les non-SRN suit les logiques ci-dessous :

* Utilisation des deux méthodes last-touch et multi-touch.
* AppsFlyer applique sa méthode d'attribution habituelle pour séquencer les données d'impression et de clic.

### Comment fonctionne l'attribution avec les SRN ?

Les SRN transmettent les événements (de type nouvelles installations et événements in-app) à AppsFlyer de la manière suivante :

* Ils utilisent des API pour communiquer avec les fournisseurs d'attribution et d'analyses.
* Lorsque les fournisseurs d’attribution tiers détectent une installation, ils interrogent le réseau avec l’ID publicitaire.
* Ils rapportent les infos détaillées pour tous les clics ou impressions publicitaires concernés.

Une fois l'attribution réalisée par AppsFlyer, les postbacks in-app sont envoyés au SRN jusqu'à ce que la <Anchor target="_blank" href="/marketers/fr/docs/user-level-data-retention#périodes-de-conservation-des-données-des-partenaires">période de conservation des données du partenaire soit écoulée</Anchor>.

### Comment fonctionne l'attribution avec les SRN avancés ?

La méthode d'attribution est la même pour les SRN avancés que pour les SRN classiques. Cependant, les SRN avancés peuvent également attribuer des engagements lorsqu'il n'y a pas d'identifiant de dispositif (IDFA), et ce en passant par la <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-knowledge-base-glossary#confidentialité-avancée-agrégée">confidentialité avancée agrégée</Anchor> et en utilisant le <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#device-id-matching">matching d'identifiant</Anchor> et la <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#probabilistic-modeling">modélisation probabiliste</Anchor> via lien d'attribution.

### Attribution d'installation

Les utilisateurs consultent et explorent souvent plusieurs publicités avant de finir par installer une application. En général, les fournisseurs d'attribution indiquent aux annonceurs l'attribution qui reflète le dernier touch, ce qui attribue l'installation au tout dernier clic réalisé avant que l'installation n'ait lieu.

Lorsqu'une app est lancée pour la première fois :

* AppsFlyer vérifie les points suivants :
  * L’app est configurée pour recevoir le trafic des SRN.
  * L'utilisateur a un ID publicitaire.
* Si les deux conditions sont remplies, AppsFlyer interroge les SRN à l’aide de l’ID publicitaire.
* AppsFlyer procède à l'attribution après avoir pris en compte les exigences du SRN.

#### Exemples d'attribution d'installation

<div id="example-a-assisted-attribution" />

<Accordion title="Exemple A : attribution assistée">

![SRN_1.png](https://files.readme.io/8e244c99f54b36a4e88b03bf05bb7ca0da2db5c7c601882ea9f68c191c38981b-32259428920337.png)

**Lundi :** le réseau A rapporte un clic d'utilisateur.

**Mardi :** le réseau B rapporte un engagement vidéo.

**Mercredi :** le réseau C rapporte un clic sur une publicité vidéo et, 30 minutes plus tard, une installation a lieu.

**AppsFlyer** attribue l'installation au réseau C et considère que les réseaux A et B ont assisté l'installation.

AppsFlyer fournit aux annonceurs les données d'assistance (c'est à dire les engagements non attribués qui ont lieu avant installation). Ces données permettent aux annonceurs de personnaliser leurs modèles d'attribution multi-touch ou fractionnée. Pour en savoir plus, veuillez consulter cette <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">courte explication</Anchor>.

</Accordion>

<div id="example-b-last-click-attribution" />

<Accordion title="Exemple B : attribution du dernier clic">

![SRN_2.png](https://files.readme.io/6817d8235acfdbbb5324d07ea8a31ace21cf2306e8e099129d9802e3e0d58b0c-32259457863825.png)

**Le réseau D** (SRN) rapporte un clic quelques minutes avant le réseau C.

**Le réseau C** utilise une intégration d'attribution standard.

**AppsFlyer** attribue l'installation au réseau C, associé au dernier clic.

</Accordion>

### Fenêtres d'attribution

Les fenêtres d'attribution comprennent les fenêtres rétrospectives et post-vue.Certains SRN facturent les annonceurs en fonction des installations basées sur le coût par impression (CPM) ou le coût par action (CPA) (c'est à dire basées sur les clics ou impressions qui se produisent sur une période allant de 1 à 28 jours).

**AppsFlyer** attribue l'installation, l'activité, le coût effectif par installation (eCPI) et le coût effectif par action (eCPA) en fonction de la méthode d'attribution préférée de l'annonceur et des fenêtres rétrospectives.

Les **annonceurs** peuvent avoir à payer les installations en fonction de la fenêtre rétrospective d'attribution SRN ou d'un modèle post-vues.

* Les annonceurs attendent d'AppsFlyer et de sa méthodologie d'attribution universelle tierce qu'il optimise et alloue leurs dépenses publicitaires.
* Pourquoi ? Parce que AppsFlyer rapporte les eCPI et eCPA en fonction des termes qui ont été définis par l'annonceur.
* Les SRN peuvent en bénéficier à court terme car ils imposent souvent leurs propres conditions de paiement. Mais les annonceurs font en sorte que cela ne se produise pas en passant par des fournisseurs d'attribution tiers.

## Deep Linking avec des SRN

Pour que les utilisateurs ouvrent l'application lorsque le lien est cliqué, il vous suffit de configurer les Liens d'app / Liens universels / Schéma d'URI. Ceci étant dit, pour appliquer un deep linking direct ou différé à une certaine page ou activité de votre app, les SRN utilisent leurs propres méthodes, qui ne recourent pas au procédé de deep linking AppsFlyer.

Comment pouvez-vous rediriger vos utilisateurs via le Deep Linking et obtenir les données pertinentes de la part des SRN ?

<div id="direct-deep-linking" />

<Accordion title="Deep linking direct">

Lorsque l'appareil d'un utilisateur effectue un deep linking, le deep linking direct sans SRN se fait sans recourir à la méthode de deep linking AppsFlyer. Dans l'exemple ci-dessous, les utilisateurs existants qui cliquent sur une publicité sont redirigés vers l'activité en suivant le procédé Facebook, tandis que les nouveaux utilisateurs vivent la même chose en passant par les données de conversion AppsFlyer. Découvrez comment <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-faq#who-needs-facebooks-sdk">Facebook utilise OneLink pour générer le deep linking.</Anchor>

> 📄 **Exemple**
>
> Jill, la marketeuse de l'app mobile greatapp, décide de lancer sur Meta ads une campagne de deep linking destinée au grand public. Tous les utilisateurs qui cliquent sur la campagne sont redirigés vers une activité « bonus ».
> Jack, le développeur mobile, ajoute la logique suivante après avoir obtenu les données de conversion :
>
> 1. Proviennent-elles de Facebook ("is\_fb=true") ?
> 2. Si «true», obtenir la valeur du paramètre groupe publicitaire.
> 3. Si la valeur contient le mot « bonus », rediriger l'utilisateur vers l'activité « bonus ».

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Deep linking différé">

Contrairement au deep linking, le deep linking différé avec les SRN est possible en passant par l'API GCD AppsFlyer.   
AppsFlyer reçoit les données de conversion, puis les met à la disposition de l'application lors du premier lancement.  
Les nouveaux utilisateurs qui installent l'application après avoir cliqué sur une campagne de deep linking / retargeting d'un SRN peuvent être redirigés dans l'app au moment de son lancement, et ce grâce aux données de conversion.

Toutefois, les SRN ne disposent pas des paramètres de Deep Linking standard d'AppsFlyer sous forme de données de Deep Linking.  
 Pour utiliser ces données dans l'app, le développeur doit utiliser une logique supplémentaire basée sur les paramètres disponibles tels que les campagnes, les ad sets ou les noms de publicité uniques.

**Remarque** : avec <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-faq#who-needs-facebooks-sdk">Meta ads</Anchor>, le deferred deep linking via GCD est disponible pour les apps Android qui utilisent le procédé Google Install Referrer. Il n’est pas disponible pour les apps iOS.

</Accordion>

## Conditions de version iOS

La plupart des SRN prennent en charge SKAdNetwork et ont l'intégration nécessaire avec AppsFlyer.

<div id="ios-145-srn-attribution" />

<Accordion title="Attribution SRN sous iOS 14.5">

Depuis iOS 14.5, lorsque les utilisateurs acceptent l'ATT tant pour les apps annonceur qu'éditeur (<Anchor target="_blank" href="/marketers/fr/docs/appsflyer-knowledge-base-glossary#double-consentement">double consentement</Anchor>), les installations SRN (enregistrées dans le <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">tableau de bord SKAdNetwork</Anchor>), apparaissent également dans les tableaux de bord classiques.

> 📘 **Note**
>
> * Le tableau de bord classique montre une réduction du nombre d'installations attribuées aux SRN. Pour améliorer les performances du SRN , utilisez le <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">tableau de bord SKAdNetwork</Anchor>. Globalement, il faut s'attendre à une diminution des installations attribuées aux SRN, et à une augmentation proportionnelle des installations organiques. Toutefois, pour les SRN avancés, l'impact est plus faible car ils attribuent également les engagements lorsqu'il n'y a pas d'ID d'appareil.
> * Le tableau de bord SKAdNetwork  est mis à jour avec un décalage pouvant aller de 48 à 72 heures après l'installation.
> * Les installations effectuées par Apple Search Ads (ASA) ne sont pas attribuées dans le tableau de bord SKAdNetwork.

</Accordion>

<div id="sending-event-postbacks-to-srns" />

<Accordion title="Envoi de postbacks d'événements aux SRN">

Les SRN recevant des postbacks d'événements se basent sur l'ID d'appareil que le postback contient. Cela permet aux SRN d'auto-attribuer les actions d'un utilisateur défini. De nombreux utilisateurs d'iOS 14 ne donnent pas leur consentement, ce qui signifie qu'ils n'autorisent pas l'accès à leur ID d'appareil (IDFA). Les conséquences sont les suivantes :

* Une diminution du nombre de postbacks d'événements envoyés aux SRN.
* Un nombre différent de postbacks d'événements entre les SRN et AppsFlyer, qui enregistrent tous les événements.

> 📘 **Note**
>
> * S'il n'y a pas d'IDFA, les postbacks d'installations, d'ouvertures d'app ou d'événements in-app ne sont pas envoyés aux SRN ([sauf dans le cas des Google Ads](/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid)). Sachez cependant que certains SRN avancés peuvent recevoir des postbacks en l'absence d'IDFA.
> * Les réseaux publicitaires par clic ne sont pas affectés, car ils utilisent leurs propres identifiants de transaction, et non les identifiants d'appareil, pour auto-attribuer des informations de postback d'événement.

</Accordion>

## FAQ

<div id="how-does-retargeting-work-with-srns" />

<Accordion title="Comment fonctionne le retargeting avec les SRN ?">

Les clics de retargeting de sources non-SRN sont facilement identifiables grâce au paramètre `is_retargeting=true` dans le lien d'attribution de retargeting.  
Avec les SRN, il n'y a aucune indication similaire. Pour permettre d'attribuer les réengagements des sources SRN, AppsFlyer utilise une autre logique :

* Prérequis :
  * Sur la page des **paramètres d'app** , sélectionnez **Activer le retargeting.**
  * Sur la page **Intégrations actives**, sélectionnez le SRN et activez le **Retargeting**.
* À chaque lancement d'app, AppsFlyer interroge le SRN sur les engagements récents de l'ID d'appareil avec des publicités de campagne pour l'app.
  * Si le SRN répond avec les éléments détaillés de l'engagement, AppsFlyer valide que l'engagement se situe dans la fenêtre rétrospective et dépasse le délai minimum autorisé entre les réengagements.
  * Les engagements validés sont enregistrés comme des réengagements et attribués au SRN.

</Accordion>

<div id="what-is-srn-mistargeting" />

<Accordion title="Qu'est-ce qu'un mauvais ciblage SRN ?">

Les campagnes SRN sont censées cibler un public précis, mais ce n'est pas toujours le cas : des non-utilisateurs peuvent être touchés dans des campagnes d'acquisition d'utilisateurs, et des utilisateurs existants peuvent l'être dans des campagnes de retargeting.

Si un SRN est utilisé pour lancer à la fois des campagnes d'acquisition d'utilisateurs et de retargeting, il y a des choses d'obtenir un mauvais ciblage des utilisateurs. Le résultat, c'est que vous payez pour un trafic dont vous ne vouliez pas.

**Scénario :** un SRN de la plate-forme AppsFlyer est activé pour une campagne d'acquisition utilisateur.

* Après chaque lancement d'app, AppsFlyer interroge le SRN pour vérifier si l'ID publicitaire (utilisateur) a eu un engagement récent.
* Si tel est le cas,
  * le SRN répond en donnant le nom de la campagne.
  * AppsFlyer détermine s'il s'agit du premier lancement (ou non) et gère les attributions :  
    **Premier lancement** : une nouvelle installation est attribuée à la campagne.  
     **Deuxième lancement ou lancement ultérieur** : un événement de retargeting est attribué à la campagne.

**Conclusion :** il est contre-productif de vouloir obtenir les événements de retargeting à partir d'une campagne d'acquisition d'utilisateurs.

#### Le mauvais ciblage pose-t-il des problèmes ?

Les analystes de données AppsFlyer ont surveillé les campagnes **d'acquisition d'utilisateurs** de Meta ads pendant un mois donné.

* Le retargeting était activé.
* Dans 30 % des campagnes, au moins 15 % des utilisateurs ciblés étaient des utilisateurs de l'app déjà existants.
* Dans 5 % des campagnes, au moins 40 % d'entre eux étaient des utilisateurs déjà existants de l'app.
* **Conclusion : dans les campagnes d'acquisition d'utilisateurs SRN, 1 utilisateur ciblé sur 10 est déjà un utilisateur existant.**

[![mistargeted_users.png](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)

#### Comment résoudre le problème du mauvais ciblage

**Solution imparable  :** ne pas inclure les utilisateurs existants dans une campagne d'acquisition d'utilisateurs.

* Le SRN ciblera uniquement les nouveaux utilisateurs.
* **Maximise les résultats d'acquisition des nouveaux utilisateurs avec le même budget**.
* Mettez périodiquement (et manuellement) la campagne à jour, par exemple une fois par mois.
* Toutefois, en raison de certains délais, les utilisateurs existants pourront être ciblés par une campagne d'acquisition d'utilisateurs durant le premier mois qui suivra l'installation de leur app.

**<Anchor target="_blank" href="/marketers/fr/docs/audiences-guide">Audiences</Anchor>**, qui est une fonctionnalité premium AppsFlyer, vous permet d'envoyer automatiquement et chaque jour à des dizaines de réseaux publicitaires, un segment choisi de votre base d'utilisateurs.

Des études AppsFlyer indiquent qu'en corrigeant un mauvais ciblage, l'impact sur le marketing et sur les actions d'acquisition d'utilisateurs peut être significatif.

</Accordion>

<div id="why-is-the-original-url-field-empty-in-raw-data-reports" />

<Accordion title="Pourquoi le champ URL d'origine est-il vide dans les rapports de données brutes ?">

Le clic est effectué dans l'environnement SRN mais sans lien d'attribution AppsFlyer. Les données d'URL d'origine associées au clic ne sont donc pas disponibles pour AppsFlyer.

</Accordion>

<div id="dashboard-doesnt-show-srn-clicks-and-impressions" />

<Accordion title="Le tableau de bord n'affiche pas les clics et les impressions SRN">

Le clic est effectué dans l'environnement SRN mais sans lien d'attribution AppsFlyer. Par conséquent, certains SRN ne fournissent pas de données de clics et d'impressions à AppsFlyer.

<Anchor target="_blank" href="/marketers/fr/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta ads</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-cost-and-ad-revenue">Google</Anchor> transmettent à AppsFlyer des données agrégées.

</Accordion>

<div id="can-agencies-configure-srn-campaigns" />

<Accordion title="Les agences peuvent-elles configurer des campagnes SRN ?">

Oui, <Anchor target="_blank" href="/partners/fr/docs/about-agency-accounts#ad-networks-auto-reporting">vous pouvez consulter ici la configuration SRN par les agences</Anchor>.

</Accordion>

<div id="does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid" />

<Accordion title="Est-ce que AppsFlyer envoie des postbacks pour les ID de publicité manquants (IDFA / GAID) ?">

Lorsque les ID publicitaires contiennent une chaîne vide ("") ou affichent la valeur 00000000-0000-0000-0000-000000000000 (IDFA en zéro), AppsFlyer n'envoie pas de postback pour les installations, ouvertures d'app ou événements in-app, sauf dans les cas suivants :

* Dans le cas d'une intégration pour les mesures avec Google Ads, lorsqu'un utilisateur iOS n'ayant pas donné son accord ouvre l'app ou génère un événement in-app, AppsFlyer envoie le `gbraid` ainsi que les informations de l'événement à Google Ads (pour l'événement `additional_data_json` ).
* Sous Android, lorsqu'il n'y a pas d'ID d'appareil mais que la valeur du référent contient un `gclid` (pour les installations), ou qu'un événement de réengagement contient un deep link avec le paramètre `gclid`, AppsFlyer envoie le `gclid` ainsi que les informations d'événement à Google Ads.

**Paramètre** `gbraid` **Google Ads :** un ID agrégé généré par Google qui permet d'identifier un groupe d’appareils et qui est référencé par le deep link.

**ID de clic Google (paramètre `gclid`) :** un paramètre que transmet l'URL lors d'un clic sur une publicité, et qui permet d'identifier la campagne et autres attributs de clics associés à la publicité. Il permet le suivi des publicités et l’attribution des campagnes.

</Accordion>

<div data-zendesk-anchors="srns-integrated-with-appsflyer=srn-int%C3%A9gr%C3%A9s-%C3%A0-appsflyer h_01HFM2MET40AFB84AW5N8GKWF3=srn-int%C3%A9gr%C3%A9s-%C3%A0-appsflyer h_01HFM2MET4ZNKEZBT3S74N8CMC=attribution how-does-attribution-work-with-srns=comment-fonctionne-lattribution-avec-les-srn h_01HFM2MET42R6C87XB5RWX9ABJ=comment-fonctionne-lattribution-avec-les-srn how-does-attribution-work-with-advanced%E2%80%94srns=comment-fonctionne-lattribution-avec-les-srn-avanc%C3%A9s h_01HFM2MET4Q6WCSANH18VTGBQX=comment-fonctionne-lattribution-avec-les-srn-avanc%C3%A9s install-attribution=attribution-dinstallation h_01HFM2MET4YQGN3GZKTTBRQ4HK=attribution-dinstallation install-attribution-examples=exemples-dattribution-dinstallation h_01HFM2MET40Y9V8YGA20CCGVNN=exemples-dattribution-dinstallation h_01HFM2MET47BP3T07NTRVDWSJ3=example-a-assisted-attribution h_01HFM2MET4FY6SRS534NEA25WV=example-b-last-click-attribution attribution-windows=fen%C3%AAtres-dattribution h_01HFM2MET4ZJF290QNE3TPXQMA=fen%C3%AAtres-dattribution deep-linking-with-srns=deep-linking-avec-des-srn h_01HFM2MET4ZA6WD6HX92JNFW7X=deep-linking-avec-des-srn h_01HFM2MET4VZX943736W52V0ZJ=direct-deep-linking h_01HFM2MET4HSVHM0Q1C8D5Z279=exemple h_01HFM2MET4WGVMRJW7NJ7TF8GQ=deferred-deep-linking ios-implications=conditions-de-version-ios h_01HFM2MET4DGERZJ18A7CEFDS9=conditions-de-version-ios h_01HFM2MET4SRX0YRZRMHBY6DKT=ios-145-srn-attribution h_01HFM2MET471M5J2XFE7G2Z6J3=note h_01HFM2MET42KNAMWE9S9BSF4PK=sending-event-postbacks-to-srns h_01HFM2MET4WJ6TMTXM03NFFCAG=note-1 h_01HFM2MET49FZ8QHDMA7H92BTE=faq h_01HFM2MET4VYGPWR98HMAWK4YP=how-does-retargeting-work-with-srns h_01HFM2MET4JGYTW6P1VGYMYGFS=what-is-srn-mistargeting is-mistargeting-a-problem=le-mauvais-ciblage-pose-t-il-des-probl%C3%A8mes h_01HFM2MET4C1HMWH715XP42ZAQ=le-mauvais-ciblage-pose-t-il-des-probl%C3%A8mes solving-the-mistargeting-problem=comment-r%C3%A9soudre-le-probl%C3%A8me-du-mauvais-ciblage h_01HFM2MET41CDCP8VNGR39YMCK=comment-r%C3%A9soudre-le-probl%C3%A8me-du-mauvais-ciblage h_01HFM2MET4DETEHT8PACHS6C6B=why-is-the-original-url-field-empty-in-raw-data-reports h_01HFM2MET48Y4ATGB1HNDGSFEP=dashboard-doesnt-show-srn-clicks-and-impressions h_01HFM2MET4JEA8BBGN564CQPYX=can-agencies-configure-srn-campaigns h_01HFM2MET42V7AVV2BPZGDRARV=does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid" />
