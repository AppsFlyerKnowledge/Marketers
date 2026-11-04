---
title: 'Google Ads (AdWords) : FAQ et erreurs'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T10:06:31Z'
  edited_at: '2023-11-15T13:10:04Z'
  id: 4417303339921
  locale: fr
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/fr/articles/4417303339921
---
> **En bref :** pour résoudre les principaux problèmes et erreurs liés à Google Ads.

<div id="why-dont-i-see-inapp-events-in-the-google-ads-dashboard" />

<div id="why-don-t-i-see-installs-from-google-ads" />

<div id="still-not-working-1" />

<div id="note" />

<div id="quick-fix-checklist" />

<div id="still-not-working" />

<div id="quick-fix" />

<div id="google-ads-faq" />

## FAQ sur Google Ads

<div id="why-am-i-not-seeing-clicks-from-google-ads" />

<Accordion title="Pourquoi ne puis-je pas voir de clics provenant de Google Ads ?">

Les données agrégées sur les clics et les impressions de Google Ads sont recueillies une fois que vous avez <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">authentifié la collecte des coûts, des clics et des impressions</Anchor> dans l'onglet **Coût**.

Les données sur les clics et les impressions provenant de Google Ads ont été mises à disposition en août 2018, d'abord pour les applications Android, puis pour les applications iOS. Par conséquent, lors de l'analyse des données sur les clics de 2018 et antérieures, les données sur les clics provenant de Google Ads peuvent être manquantes ou incomplètes.

</Accordion>

<div id="why-am-i-not-seeing-first_open-conversions-on-google-ads" />

<Accordion title="Pourquoi ne puis-je pas voir les conversions first_open sur Google Ads ?">

Si vous ne voyez pas les conversions first\_open sur Google Ads, comme illustré dans la capture d'écran ci-dessous :

![AW_13.png](https://support.appsflyer.com/hc/article_attachments/4417310093457)  

Ce qui signifie que vous devez importer les conversions dans Google Ads. Suivez les instructions concernant <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">l'Importation des conversions.</Anchor>

</Accordion>

<div id="why-cant-i-see-inapp-events-on-google-ads" />

<Accordion title="Pourquoi ne puis-je pas voir les évènements in-app sur Google Ads ?">

Cet écran apparaît-il sur Google Ads une fois vos principaux évènements in-app mappés dans le tableau de bord AppsFlyer (<Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended">étape 3 de la configuration</Anchor>) ?

[![adwords missing events 2.png](https://support.appsflyer.com/hc/article_attachments/18726174138001)](https://support.appsflyer.com/hc/article_attachments/18726174138001)  

Dans ce cas, procédez de l'une des manières suivantes :

* Si l'option d'envoi pour les événements in-app est définie sur « Ce partenaire uniquement », assurez-vous d'attribuer l'installation sur votre appareil à Google, puis d'exécuter les événements sur votre appareil.
* Définissez <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended">l'option d'envoi</Anchor> des événements sur « Toutes les sources média, y compris organiques », puis exécutez les événements sur votre appareil.

> 🚧 **Important !**
>
> * Veillez à mapper les événements in-app avant de les exécuter sur votre appareil.
> * L'apparition des évènements sur le tableau de bord Google Ads peut prendre jusqu'à 6 heures.

</Accordion>

<div id="can-i-stop-google-cost-sync" />

<Accordion title="Puis-je arrêter Google Cost Sync ?">

Pour arrêter la synchronisation des coûts avec Google :

1. Accédez à vos <Anchor target="_blank" href="https://myaccount.google.com/permissions">autorisations de compte Google</Anchor>
2. Cliquez sur Supprimer (à côté de AppsFlyer Google Cost)  

   ![remove_appsflyer_cost.png](https://support.appsflyer.com/hc/article_attachments/4417304127249)

</Accordion>

<div id="do-i-need-to-create-and-then-import-session_start" />

<Accordion title="Dois-je créer puis importer session_start ?">

Cela dépend du type de campagne que vous exécutez. Si vous exécutez une campagne de réengagement, il est recommandé de créer et d'importer `session_start` pour mesurer les engagements.

Pour une campagne d'acquisition utilisateurs, ce n'est pas obligatoire.

</Accordion>

<div id="can-i-send-uninstall-information-to-google-ads" />

<Accordion title="Puis-je envoyer des informations de désinstallation à Google Ads ?">

Oui.  
 **Pour commencer à envoyer des événements de désinstallation à Google :**

1. Mappez l'événement af\_uninstall en tant qu'événement personnalisé dans la fenêtre de configuration de Google Ads.
2. Importez cette conversion dans Google.
3. Google reconnaît les événements s'ils sont reçus dans la fenêtre d'attribution de Google (qui débute avec l'engagement publicitaire et dure de 30 à 90 jours). Les événements reçus par Google après la durée de la fenêtre ne sont pas enregistrés dans Google.

</Accordion>

<div id="what-google-ads-data-does-appsflyer-display" />

<Accordion title="Quelles sont les données Google Ads affichées par AppsFlyer ?">

Vous pouvez visualiser les données aux niveaux suivants : campagne, canal, adset et geo.

</Accordion>

<div id="do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data" />

<Accordion title="Dois-je configurer quelque chose pour créer des listes d'audience dans Google Ads en fonction des données d'AppsFlyer ?">

Non. Dans l'API Google, ces informations sont déjà définies et sont basées sur la configuration de votre évènement in-App.

</Accordion>

<div id="im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard" />

<Accordion title="J'exécute une campagne UAC. Pourquoi les données ou les évènements de conversion ne s'affichent-ils pas dans le tableau de bord AppsFlyer ou Google Ads ?">

Il est fort probable que vous n’ayez pas encore importé d’évènements. Pour plus d'informations sur la manière d'importer des évènements, cliquez <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">ici</Anchor>.

</Accordion>

<div id="what-do-i-do-if-there-are-multiple-accounts" />

<Accordion title="Que dois-je faire en cas de comptes multiples ?">

L'utilisation de plusieurs comptes avec Google Ads et AppsFlyer ne pose aucun problème. AppsFlyer ne fonctionne qu'avec un seul identifiant de lien. Par conséquent, un seul identifiant de lien doit être généré dans Google Ads. Il peut être partagé entre plusieurs comptes. Pour plus d'informations, veuillez cliquer <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3030657">ici</Anchor>.

</Accordion>

<div id="what-happens-with-link-ids-created-at-mcc-level-vs-account-level" />

<Accordion title="Que se passe-t-il avec les identifiants de lien créés au niveau MCC et ceux crées au niveau du compte ?">

Les identifiants de lien au niveau MCC ou du compte sont pris en charge par AppsFlyer. Nous vous recommandons de travailler en étroite collaboration avec votre représentant Google Ads pour vous assurer que votre compte est correctement structuré. Pour plus d'informations, veuillez cliquer <Anchor target="_blank" href="/marketers/fr/docs/recording-multiple-agency-mcc-google-ads-accounts">ici</Anchor>.

</Accordion>

<div id="what-is-parallel-tracking" />

<Accordion title="Qu'est-ce que le suivi parallèle ?">

Le suivi parallèle de Google Ads accélère le chargement de votre page d'accueil, ce qui réduit le nombre de visites perdues. Cela entraîne l'augmentation des conversions et l'amélioration des performances des publicités. Avec le suivi parallèle, les utilisateurs sont dirigés vers l'URL finale, directement à partir de votre publicité, avant d'être dirigés vers les liens d'attribution, tandis que les clics sont comptabilisés en arrière-plan.

Pour une explication complète du suivi parallèle, cliquez <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">ici</Anchor>.

<div id="what-is-needed" />

#### Que faut-il faire ?

Pour que le suivi parallèle fonctionne correctement, l'URL finale doit correspondre à l'URL de la campagne et doit être placée dans <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en">le paramètre ValueTrack du `{lpurl}` de Google.</Anchor>

Vous avez plusieurs possibilités :

* Utiliser un lien d'attribution à plateforme unique (non recommandé)
  * Le paramètre af\_r doit être utilisé dans l'URL
* Utiliser un <Anchor target="_blank" href="/marketers/fr/docs/understand-onelink-short-vs-long-urls">lien long OneLink</Anchor> (recommandé)
  * Les paramètres URL suivants doivent être inclus dans l'URL de la campagne
    * af\_android\_url
    * af\_ios\_url
    * af\_web\_dp
  * af\_dp ne doit pas être utilisé
  * Ajouter votre URL finale (URL de destination) au paramètre ValueTrack de Google. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en#urlinsertion&zippy=%2Ctracking-template-only">En savoir plus</Anchor>

Exemple,

```
https://subdomain.onelink.me/template_id?pid=xxx&af_ios_url={lpurl}  
&af_android_url={lpurl}&af_web_dp={lpurl}
```

Remarque : Pour connaître tous les paramètres pris en charge, consultez cet article

Cliquez ici pour voir comment configurer les campagnes web de Google ad avec le suivi parallèle.

</Accordion>

<div id="how-do-you-configure-a-campaign-with-android-or-ios-configuration" />

<Accordion title="Comment configurer une campagne avec une configuration Android ou iOS ?">

<div id="important" />

> 🚧 **Important !**
>
> AppsFlyer prend en charge toutes les campagnes d'applications activées par Google Ads.
>
> Google est un SRN (Self Reporting Network : réseau auto-reporting). Pour plus d'informations sur le fonctionnement du flux d'attribution pour ces réseaux, cliquez <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">ici</Anchor>.
>
> AppsFlyer peut présenter toutes les informations de campagne fournies par Google. Le type de campagne (Recherche, Vidéo, Affichage et Réengagement) et les informations associées sont déterminés par Google. Il est recommandé de configurer les campagnes de l’App. Pour obtenir des conseils sur d'autres types de campagne, contactez votre représentant Google. Pour avoir plus d'informations sur ces campagnes, cliquez <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">ici.</Anchor>

<div id="android-configuration-for-google-ads" />

<Accordion title="Configuration Android pour Google Ads">

Pour prendre en charge l'attribution Android, assurez-vous que votre app prend en charge la collecte du GAID (identifiant Google Advertising) et qu'il est transmis à AppsFlyer via notre SDK.

<div id="creating-conversion-recording-installs" />

#### Création de l'enregistrement de conversion (Installations)

Pour plus d'informations sur la manière de créer un enregistrement de conversion, cliquez <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">ici</Anchor>.

<span id="inapp_events"></span>Google Ads - Configuration Android - Envoi d'évènements in-app

Si vous souhaitez mesurer davantage le succès de vos campagnes d’installation d’applications mobiles dans Google, vous pouvez envoyer des évènements in-app à votre compte Google Ads à partir de votre compte AppsFlyer.

<div id="create-a-conversion-in-app-events" />

#### Création d'une conversion (évènements in-app)

Pour plus d'informations sur la mesure des conversions de vos apps, cliquez <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">ici</Anchor>.

</Accordion>

<div id="ios-configuration-for-google-ads" />

<Accordion title="Configuration iOS pour Google Ads">

<div id="google-ads---ios-configuration-app-campaigns" />

#### Google Ads - Configuration iOS : campagnes d'apps

Les campagnes d'applications vous permettent de promouvoir votre application iOS via Google Search, YouTube et Display dans un seul lieu de configuration.

En règle générale, Google Ads ne peut pas attribuer lui-même les installations iOS des campagnes de recherche, car les clics proviennent de sources Web mobiles, ce qui empêche Google d'extraire l'IDFA des appareils et d'effectuer une correspondance d'identifiant.

En revanche, la **recherche iOS** **sur** les **campagnes d'applications peut être attribuée par Google Ads**, pour les publicités diffusées sur l'**application Google Search.**

<div id="creating-conversion-recording-installs-1" />

#### Création de l'enregistrement de conversion (Installations)

Pour plus d'informations sur la manière de créer un enregistrement de conversion, cliquez <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">ici</Anchor>.

<div id="google-ads---ios-configuration---sending-in-app-events" />

#### Google Ads - Configuration iOS - Envoi d'évènements in-app

Si vous souhaitez mesurer davantage le succès de vos campagnes d’installation d’applications mobiles dans Google, vous pouvez envoyer des évènements in-app à votre compte Google Ads à partir de votre compte AppsFlyer.

<div id="creating-a-conversion-in-app-events" />

#### Création d'une conversion (évènements in-app)

Pour plus d'informations sur la mesure des conversions de vos apps, cliquez <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">ici</Anchor>.

</Accordion>

</Accordion>

<div id="for-how-long-do-you-keep-google-ads--userlevel-data" />

<Accordion title="Combien de temps conservez-vous les données de niveau utilisateur de Google Ads ?">

Google Ads demande aux prestataires d'attribution de supprimer ses données de niveau utilisateur 6 mois après l'installation. Cela signifie que les évènements effectués par ces utilisateurs 6 mois après l'installation de l'app sont considérés comme organiques.

Les données agrégées passées restent les mêmes.

Ceci vaut pour tous les canaux Google Ads.

</Accordion>

<div id="google-ads-discrepancies" />

## Inexactitudes dans Google ads

Il existe parfois des écarts de mesure entre le tableau de bord Google Ads et le tableau de bord AppsFlyer.

Même si nous travaillons en étroite collaboration avec Google pour réduire ces écarts, les annonceurs doivent être conscients des causes suivantes :

<div id="both-ios-and-android" />

#### Sous iOS comme sous Android

| **Cause** | **Google Ads** | **AppsFlyer** |
| --- | --- | --- |
| **Installations assistées (alias attribution multi-touch)** | Google Ads, en tant que SRN, attribue toutes les installations liées à des engagements avec Google Ads, dans sa fenêtre d'attribution. | AppsFlyer n'attribue que le dernier clic du parcours d'un utilisateur, et traite tout engagement précédent comme une <Anchor target="_blank" href="/marketers/fr/docs/measure-assisted-installs">assistance</Anchor>. |
| **Heure d'enregistrement de l'installation** | Google Ads attribue la conversion à l'heure du clic. | AppsFlyer attribue la conversion à l'heure du lancement (ouverture de l'application). |
| **Fuseaux horaires** | Selon la localisation | Selon la localisation |
| **Fenêtres d'attribution** | 30 jours | L'intégration Google est définie sur 30 jours par défaut (modifiables). |
| **Conversions post vue** | Les conversions post-vues s'affichent uniquement dans la colonne ***Toutes les conversions*** et non dans la colonne ***Conversions***, sauf indication contraire dans Google Ads. | AppsFlyer affiche le nombre total d'installations. Cliquez sur installations et installations post vue. |
| **Réinstallations** | Google Ads affiche les réinstallations comme une conversion session\_start. | AppsFlyer attribue et affiche les réinstallations ( ou ré-attributions) dans le cadre de ses données de reciblage. |
| **Évènement in-app** | Google Ads attribue l'évènement in-app à l'heure du clic. | Dans le tableau de bord AppsFlyer, les évènements in-app sont attribués en fonction de l'heure d'installation. Dans les rapports de données brutes, AppsFlyer attribue les évènements in-app en fonction de l'heure de l'évènement. |
| **Règles de validation** | Google reçoit toutes les informations d'AppsFlyer, quelles que soient les règles de validation. | AppsFlyer peut déduire un certain nombre d'installations en fonction de leurs règles de validation. |
| **Inventaire de recherche de campagne d'app iOS** | Google Ads inclut un inventaire des résultats de recherche AC iOS à la fois dans le web mobile et l'app de recherche Google. | Google Ads ne répond pas aux requêtes des partenaires d'attribution concernant les conversions de recherche AC iOS sur le web mobile ou l'application de recherche Google. Ces installations ne sont donc pas attribuées à Google Ads dans AppsFlyer. |
| **Coût - Canaux de campagne Google Ads** | Google rapporte les coûts pour tous les canaux d'une campagne donnée - YouTube, affichage et recherche. | AppsFlyer obtient des données de coût de Google pour tous les canaux d'une campagne, mais attribue uniquement les conversions de YouTube et les canaux d'affichage dans AC iOS. Le CPI global dans AppsFlyer est donc plus élevé. |
| **Installations SKAN** | Depuis l'API Google Ads V10+, le tableau de bord Google Ads ne fait pas de différence entre les installations qui ont did\_win=TRUE et celles qui ont did\_win=NULL. La différence ne se fait qu'au niveau des données brutes. | Depuis l'API Google Ads V10+, AppsFlyer n'affiche que les installations issues des postbacks contenant did\_win=TRUE. Par conséquent, le nombre d'installations comptabilisé dans AppsFlyer peut être plus petit. |

<div id="notes" />

> 📘 **Remarques**
>
> * Alors que Google Ads affiche toutes les installations d’une campagne de retargeting au même endroit, dans la vue d'ensemble du tableau de bord AppsFlyer, la vue UA affiche les nouvelles installations, la vue de retargeting affiche les réattributions et la vue unifiée affiche les deux.
> * Lorsque vous comparez les données du tableau de bord Google Ads et AppsFlyer, assurez-vous que les données importées dans le tableau de bord Google Ads sont issues d'analyses tierces (AppsFlyer). Les données importées depuis Firebase ou Google Play sont structurées différemment et ne peuvent pas être comparées aux données AppsFlyer. Pour savoir comment importer des données depuis AppsFlyer dans le tableau de bord Google Ads, cliquez <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">ici</Anchor>.
> * Pour comparer les évènements d'installation (first\_open dans Google Ads), veillez à effectuer une analyse plus approfondie des évènements d'installation dans le rapport de conversion de Google Ads. Google Ads étant susceptible d'afficher toutes les conversions (installations, achats, abonnements, etc.), il est important de sélectionner uniquement ces évènements d'installation parmi tous les évènements de conversion.

<div id="see-also" />

> 📄 **À consulter également**
>
> * Pour iOS 14, voir l'<Anchor target="_blank" href="/marketers/fr/docs/get-skan-postback-data-from-google-ads">interopérabilité entre Google Ads SKAdNetwork et AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-ads-faq=faq-sur-google-ads h_01HA1SM7D91QPG17WH752FBAFT=faq-sur-google-ads h_01HA1SM7D9JWBEPNE0E8FE665E=why-am-i-not-seeing-clicks-from-google-ads h_01HA1SM7DAW984PPRGHXA5BYSX=why-am-i-not-seeing-first_open-conversions-on-google-ads h_01HA1SM7DAXB3N9M7X8X2YB91C=why-cant-i-see-inapp-events-on-google-ads h_01HA1SM7DAH6VBNW2RPJ1CE1PT=important- h_01HA1SM7DACQDVGWGKV5MZ63D6=can-i-stop-google-cost-sync h_01HA1SM7DA415FQP3MFC09AE3Y=do-i-need-to-create-and-then-import-session_start h_01HA1SM7DAEKGVPDTX77RJ9Y37=can-i-send-uninstall-information-to-google-ads h_01HA1SM7DAKKVZ82WF6RVEDHE9=what-google-ads-data-does-appsflyer-display h_01HA1SM7DANYQ0DAY54CH4HPV4=do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data h_01HA1SM7DA3XF8NBGYGZ0XTB69=im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard h_01HA1SM7DAY7JNTFSG86A1QGKC=what-do-i-do-if-there-are-multiple-accounts h_01HA1SM7DAYSVMENT91T2BE26Z=what-happens-with-link-ids-created-at-mcc-level-vs-account-level h_01HA1SM7DAK186BRZN970PKPRM=what-is-parallel-tracking additional-information=que-faut-il-faire- h_01HA1SM7DAMNG8X22VNWMKBJ8R=que-faut-il-faire- h_01HA1SM7DBNAS6DP8G9D8KFHPW=how-do-you-configure-a-campaign-with-android-or-ios-configuration h_01HA1SM7DB16T3RGBVGT5Z9REW=important--1 h_01HA1SM7DBC38CY8AN3EPMMJFW=android-configuration-for-google-ads creating-conversion-recording-installs=cr%C3%A9ation-de-lenregistrement-de-conversion-installations h_01HA1SM7DBF9KDRNEV25KJHGHN=cr%C3%A9ation-de-lenregistrement-de-conversion-installations create-a-conversion-inapp-events=cr%C3%A9ation-dune-conversion-%C3%A9v%C3%A8nements-in-app h_01HA1SM7DBDQVNDQ5GG7X2PJ8K=cr%C3%A9ation-dune-conversion-%C3%A9v%C3%A8nements-in-app h_01HA1SM7DBKKQ9R8MQMQT9GRXV=ios-configuration-for-google-ads google-ads-ios-configuration-app-campaigns=google-ads---configuration-ios-campagnes-dapps h_01HA1SM7DBNSDFCJA5BP59MMQ2=google-ads---configuration-ios-campagnes-dapps creating-conversion-recording-installs::6a56eb4b=cr%C3%A9ation-de-lenregistrement-de-conversion-installations-1 h_01HA1SM7DBXCT0NS4W50D4ZGEK=cr%C3%A9ation-de-lenregistrement-de-conversion-installations-1 google-ads-ios-configuration-sending-inapp-events=google-ads---configuration-ios---envoi-d%C3%A9v%C3%A8nements-in-app h_01HA1SM7DBEV9CJTAB5YHRJHYK=google-ads---configuration-ios---envoi-d%C3%A9v%C3%A8nements-in-app creating-a-conversion-inapp-events=cr%C3%A9ation-dune-conversion-%C3%A9v%C3%A8nements-in-app-1 h_01HA1SM7DBCQYSJ3R67F0856QK=cr%C3%A9ation-dune-conversion-%C3%A9v%C3%A8nements-in-app-1 for-how-long-do-you-keep-google-ads%E2%80%99-userlevel-data=for-how-long-do-you-keep-google-ads--userlevel-data h_01HA1SM7DBFAAV7C4ENA34B7JP=for-how-long-do-you-keep-google-ads--userlevel-data google-ads-discrepancies=inexactitudes-dans-google-ads h_01HA1SM7DBA7KK1DXFCE2G0QTP=inexactitudes-dans-google-ads both-ios-and-android=sous-ios-comme-sous-android h_01HA1SM7DB18BTDKK5BK4949HX=sous-ios-comme-sous-android h_01HA1SM7DBSTAREA36YWRRRG82=remarques h_01HDP2XBSEJVQ5G0MD0V5R05CM=%C3%A0-consulter-%C3%A9galement" />
