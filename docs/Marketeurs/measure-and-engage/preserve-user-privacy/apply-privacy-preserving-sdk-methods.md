---
title: Accord/refus de l'utilisateur dans le SDK AppsFlyer
metadata:
  keywords:
    - Advertisers
    - coppa
    - opt-out
    - opt out
    - consent management
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-08-20T11:14:36Z'
  edited_at: '2023-11-30T11:59:32Z'
  id: 360001422989
  locale: fr
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/fr/articles/360001422989
---
> **En bref :** limiter ou interrompre le transfert des données à AppsFlyer pour vous conformer aux réglementations sur la protection de la vie privée telles que le RGPD ou CCPA.

![OptInOptOut_us-en.png](https://files.readme.io/bd2cd3e2fa3c443b9cc6a736e3c6b60834f165ad13510b829d40005740615496-360010352638.png)

**Questions sur la confidentialité AppsFlyer**: le contrat de confidentialité établi entre vous et AppsFlyer est régi par la <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy">politique de confidentialité des services AppsFlyer.</Anchor> Pour toute question relative à la présente Politique de confidentialité de nos services, ou pour contacter notre délégué à la protection des données, veuillez nous envoyer un e-mail à [privacy@appsflyer.com](mailto:privacy@appsflyer.com). Aux fins de l'article 27 du Règlement général sur la protection des données, le représentant d'AppsFlyer au sein de l'UE est AppsFlyer Germany GmbH, Schönhauser Allee 180, 10119 Berlin, Allemagne (e-mail [privacy@appsflyer.com](mailto:privacy@appsflyer.com); tel +49-30-166373500).

## Scénarios de demande de consentement

* Le SDK AppsFlyer intégré aux applications peut être configuré pour :
  * Refus : arrêter ou limiter la collecte de données.
  * Accord donné : après un refus, reprise de la collecte de données.
* Le développeur de l'app et le marketeur, après avoir pris en compte les exigences réglementaires et commerciales, mettent en œuvre la demande de consentement comme indiqué dans cet article.
* Utilisez le refus pour :
  * Vous conformer aux réglementations de type RGPD ou CCPA qui interdisent ou limitent la collecte de données.
  * **Refus complet** : ne plus collecter de données d'attribution.
  * **Refus partiel :** envoyer certaines données ou anonymiser les données envoyées.
  * **Refus sélectif :** répond à certains critères ou à l'âge de l'utilisateur de l'application.
* **Utiliser l'accord :** pour passer du refus de l'utilisateur à son accord.

## Exclusion d'utilisateurs

Le refus peut se manifester à différents niveaux, en fonction des réglementations et des droits de l'utilisateur. Suivez la bonne procédure en utilisant un des scénarios de refus détaillé ci-dessous. Vous aurez ainsi la certitude de vous conformer aux demandes de consentement et vous pourrez continuer à collecter les données d'attribution correspondantes.

Dans les scénarios où le refus est activé, l'identifiant AppsFlyer est haché.

## Scénarios

### Refus à l'installation

**![coppa_compliant_appsflyer.png](https://files.readme.io/0f2588ad5a4e9d78df88958c6855f5e71498588e35c7a88c3b13c6ef676507f9-360002519649.png)**

**Quand** : lors du premier lancement (Ex. <Anchor target="_blank" href="https://www.ftc.gov/enforcement/rules/rulemaking-regulatory-reform-proceedings/childrens-online-privacy-protection-rule">Conformité COPPA</Anchor>)

**Quoi** : l'app nécessite l'accord de l'utilisateur pour **procéder à l'enregistrement des événements au cours des sessions.** Si l'utilisateur consent à l'enregistrement (par exemple s'il a l'âge requis), l'app appelle la méthode de SDK `start`. Dans le cas contraire, la méthode `start` ne doit pas être appelée.

> ❗️ **Attention**
>
> N'utilisez pas `stop` si `start` n'a jamais été appelé.

**Comment** : la méthode `start` doit toujours être appelée au début de la session des utilisateurs qui ont donné leur accord, mais elle ne doit pas être appelée pour les utilisateurs qui ne l'ont pas donné. De plus, les événements in-app ne peuvent pas être envoyés pour les utilisateurs qui n'ont jamais donné leur accord, puisqu'ils sont considérés comme provenant d'utilisateurs inconnus et sont donc organiques.

Pour les applications qui ont l'option ***Refus d'installation*** activée, nous recommandons donc de créer un paramètre flag permanent qui indique si `start` a été appelé au préalable ou non. Ce flag doit SYSTÉMATIQUEMENT être vérifié avant d'appeler `start` ou `logEvent`.

**Données transmises à AppsFlyer :** aucune donnée n'est envoyée. Si plus tard l'utilisateur donne son accord, les données d'attribution et de session sont envoyées à partir du moment où `start` est appelé.

> 📄 **Exemple**
>
> com.carefulapp demande aux utilisateurs de s'enregistrer lors de l'installation. Le formulaire contient une case où il faut cocher : «J'ai plus de 13 ans». David le développeur a ajouté un flag is\_tracking, qui ne devient true que pour les inscriptions où cette case est cochée, et qui active ensuite `start`.
>
> Exemple de code <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/SampleApp-Examples/blob/master/AndroidOptOutSampleApp/app/src/main/java/com/appsflyer/optoutsamples/OptInActivity.java">ici</Anchor>

### Empêcher le partage des données avec des tiers

**Quand** : **chaque fois que le SDK est initialisé**. 

**Quoi** : un utilisateur peut demander à ce que ses données ne soient pas partagées avec des tiers. En activant cette option dans le SDK AppsFlyer AVANT le premier appel de `start`, les conditions suivantes s'appliquent à l'ensemble de la session :

* **Les utilisateurs des SRN** sont attribués comme organiques, et leurs données ne sont pas partagées avec les partenaires intégrés.
* **Les utilisateurs de réseaux publicitaires par clic** (non-SRN) sont attribués correctement dans AppsFlyer, mais ne sont pas partagés avec les ad networks via des postbacks, des API, des rapports de données brutes, ou autre méthode.

**Comment** :

Empêcher le partage des données d'événements via :

* SDK (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">iOS</Anchor> avec un SDK V6.4 et +) :
  * Empêcher une sélection de sources média (ou toutes les sources média) de recevoir l'événement : utilisez la méthode de SDK `setSharingFilterForPartners`.
* S2S API :
  * Envoyez le paramètre <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_s2s_inappevent">S2S sharing\_filter</Anchor>

**Données envoyées à AppsFlyer :** les données sont envoyées à AppsFlyer, où elles sont stockées, mais elles ne sont jamais partagées avec les partenaires intégrés à AppsFlyer.

> 📄 **Exemple**
>
> com.to.california est une app de voyage pour les parcs à thème en Californie. Pour se conformer au CCPA, si un résident Californien ne donne pas son consentement, l'application demande à AppsFlyer de ne pas partager les données de l'événement de l'utilisateur avec des tiers.

### Refus de session

**Quand** : à chaque lancement de l'application.

**Quoi** : toutes les sessions de l'app nécessitent l'accord de l'utilisateur pour **procéder à l'enregistrement des événements et données au cours d'une session.**

**Comment** : dans le cas d'une **Session-accord non donné** , le premier appel au SDK intervient après que l'utilisateur a accepté ou refusé que des données soient envoyées depuis son appareil :

* Si l'utilisateur accepte d'envoyer les données, la méthode `start` doit être appelée.
* Si l'utilisateur refuse que les données soient envoyées, vous ne devez pas appeler `start`.

**Les données envoyées à AppsFlyer** dépendent du statut de consentement de chaque session, comme suit :

* **Session-accord non donné** : aucune donnée n'est envoyée.
* **Session-accord donné** : toutes les données de la session sont envoyées. **Remarque :** Les données d'attribution sont envoyées la première fois que l'utilisateur se connecte.

> 📄 **Exemple**
>
> com.adultsplay est une application de jeu pour les adultes de plus de 18 ans. Elle n'exige pas que les utilisateurs s'inscrivent, mais on leur demande de confirmer leur âge à chaque nouveau lancement. Les sessions où les utilisateurs confirment qu'ils ont plus de 18 ans bénéficient d'une expérience de jeu complète et sont enregistrées, alors que dans le cas contraire, aucun enregistrement n'a lieu.
>
> David le développeur a ajouté un flag is\_tracking, qui ne devient true que pour les sessions qui confirment que l'utilisateur a plus de 18 ans. Si ce flag est true, la méthode `start` est appelée. Dans le cas contraire, `start` n'est pas appelé.

### Refus ponctuel

![OpenGDPR-logo-BLK.png](https://files.readme.io/87560c35c45bf34d8eb7ede3e6bbf90fb4391ab41c7f3186e33a93d8f4f68a6e-360002512925.png)

**Quand** : n'importe quand (RGPD)

**Quoi** : le propriétaire de l'app collecte les données d'attribution et les données post-installation. **L'utilisateur demande l'arrêt de la collecte des données**, par exemple conformément à une demande <Anchor target="_blank" href="/marketers/fr/docs/send-opendsr-api-requests">RGPD</Anchor> .

**Comment**: n'appelez surtout pas `stop` juste après avoir appelé `start` !

Au premier lancement, utilisez plutôt la méthode `start` avec ***requestListener***. En cas de réponse positive, la fonction de callback appellera `stop`.

Pour toutes les sessions suivantes, n'appelez pas `start`.

**Données transmises à AppsFlyer :** les données d'installation et de session sont envoyées à AppsFlyer. Aucune donnée n'est envoyée à AppsFlyer après l'appel de la méthode *`stop`*.

> 📄 **Exemple**
>
> com.watchmegrow est une application où l'on voit les plantes pousser, les utilisateurs observent la croissance des plantes et voient s'afficher des publicités mobile. Le propriétaire de l'app souhaite garder confidentielles toutes les données relatives aux activités in-app.
>
> Lors du premier lancement, David le développeur appelle la méthode `start` avec **requestListener**. Lorsqu'il reçoit une réponse positive, il appelle `stop` à partir de la fonction de callback et attribue la valeur false au paramètre persistant ***is\_first\_launch***. Lors des lancements d'app suivants, David vérifie si ***is\_first\_launch*** est false, et ignore `start`.
>
> Exemple de code <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/SampleApp-Examples/blob/master/AndroidOptOutSampleApp/app/src/main/java/com/appsflyer/optoutsamples/TrackAndOptOut.java">ici</Anchor>

### Enregistrer l'installation et anonymiser

**Quand** : au premier lancement

**Quoi** : le propriétaire de l'app souhaite collecter toutes les données d'attribution, puis toutes les informations subsidiaires, comme les événements in-app ou les données de sessions, en tant que **données organiques non attribuées**. Après l'installation, tous les ID des appareils sont anonymisés lorsqu'ils sont envoyés à AppsFlyer par le SDK.

**Comment**: n'appelez surtout pas `stop` juste après avoir appelé `start` !

Au premier lancement, utilisez plutôt la méthode `start` avec ***requestListener***. En cas de réponse positive, la fonction de callback appellera `anonymizeUser(true)`.

**Données envoyées à AppsFlyer :**

* **Au moment de l'installation :** les données d'attribution intégrales sont envoyées à AppsFlyer.
* **Après l'installation** : les données des événements in-app et les données de session sont envoyées à AppsFlyer sans les données d'attribution. Dès réception, l'ID de l'utilisateur est anonymisé et l'identifiant AppsFlyer et l'adresse IP sont hachés. L'image suivante montre un exemple de données anonymisées et hachées. [![DataSample_anonymized.png](https://files.readme.io/71af1933aee76c2f7a77d24d941ef1976a15f35821448d50eb97db684ed9723c-360018851737.png)](https://files.readme.io/71af1933aee76c2f7a77d24d941ef1976a15f35821448d50eb97db684ed9723c-360018851737.png)

> 📄 **Exemple**
>
> Le propriétaire de l'app com.munisme pense que tous les utilisateurs sont égaux en droits et préfère considérer toutes leurs actions post-installation comme purement organiques.
>
> Lors du premier lancement , David le développeur appelle la méthode `start` avec ***requestListener**.En cas de succès, la fonction de callback appelle `anonymizeUser(true)`.*

## Refus des campagnes de retargeting

Vous devrez peut-être exclure les utilisateurs qui se sont retirés des campagnes de retargeting. Ces utilisateurs sont susceptibles de se plaindre d'être reciblés alors qu'ils n'ont initialement pas donné leur consentement.

Lors de l'exécution manuelle de campagnes de retargeting qui ciblent les utilisateurs actifs, veillez à supprimer des listes envoyées aux sources média les utilisateurs qui n'ont pas donné leur consentement.

Par ailleurs, si vous utilisez **AppsFlyer Audiences** pour créer vos listes d'audience et les envoyer aux sources média, les utilisateurs qui n'ont pas donné leur accord sont exclus des listes envoyées aux sources média.

## API `stop` et deep linking

L'utilisation de l'API `stop` interrompt toute communication du SDK AppsFlyer intégré dans l'application.

Après l'appel de `stop`, les liens courts ne sont donc plus décodés par le SDK AppsFlyer. Cela signifie que les liens raccourcis ne génèrent pas d'appel à ***onAppOpenAttribution***, et que le deep linking ne s'exécute pas correctement.

Si votre application a un pourcentage relativement élevé d'utilisateurs qui n'ont pas donné leur consentement, mais que vous prévoyez des campagnes de retargeting, utilisez des liens longs plutôt que des liens raccourcis.

## Redémarrage de la fonction SDK

Lorsqu'un utilisateur qui n'a pas donné son consentement donne finalement son accord, appelez la méthode `start` pour redémarrer le SDK et commencer à enregistrer les données d'attribution.

## SDK en mode strict (iOS uniquement)

Parfois, les développeurs préfèrent soumettre leurs app sans aucune référence dans leur code à l'infrastructure AdSupport ni à la collection IDFA. Dans ce cas, utilisez le <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK en mode strict.</Anchor>

<div data-zendesk-anchors="optin-and-optout-scenarios=sc%C3%A9narios-de-demande-de-consentement h_01HFPME3VYC6G1CA3WD73JJD46=sc%C3%A9narios-de-demande-de-consentement optingout-users=exclusion-dutilisateurs h_01HFPME3VYV81QKGT188CCR7QV=exclusion-dutilisateurs scenarios=sc%C3%A9narios h_01HFPME3VYP4P1Q440QW2PN32P=sc%C3%A9narios optout-at-installation=refus-%C3%A0-linstallation h_01HFPME3VY7JQY4Z71VT60NVVR=refus-%C3%A0-linstallation h_01HFPME3VYASX24WYXJSZVGPMY=attention h_01HFPME3VZ8FSNA9BR3DHMX408=exemple prevent-data-sharing-with-third-parties=emp%C3%AAcher-le-partage-des-donn%C3%A9es-avec-des-tiers h_01HFPME3VZXRT3MN6SSQNVPYQH=emp%C3%AAcher-le-partage-des-donn%C3%A9es-avec-des-tiers h_01HFPME3VZ7NGAFF8F7W77GJZZ=exemple-1 session-optout=refus-de-session h_01HFPME3VZKVV8G0C678X4N3BF=refus-de-session h_01HFPME3VZHBNZARMA5D75H2AF=exemple-2 onetime-optout=refus-ponctuel h_01HFPME3VZSKDBHBF6Q2573BVP=refus-ponctuel h_01HFPME3VZ1W6G78FH2XGZYDQZ=exemple-3 record-install-and-anonymize=enregistrer-linstallation-et-anonymiser h_01HFPME3VZ6RFCJ6VPREVZ93Q1=enregistrer-linstallation-et-anonymiser h_01HFPME3VZZRF8ERES0693D3DE=exemple-4 optingout-of-retargeting-campaigns=refus-des-campagnes-de-retargeting h_01HFPME3VZYKB97AG3T5BX9NG6=refus-des-campagnes-de-retargeting stop-api-and-deep-linking=api-stop-et-deep-linking h_01HFPME3VZ21D3W8RRBQHG0905=api-stop-et-deep-linking restarting-the-sdk-function=red%C3%A9marrage-de-la-fonction-sdk h_01HFPME3VZBWJXCAM7XZ3C5Y7E=red%C3%A9marrage-de-la-fonction-sdk strict-mode-sdk-ios-only=sdk-en-mode-strict-ios-uniquement h_01HFPME3VZFC8A3Y48HS1KEFF5=sdk-en-mode-strict-ios-uniquement" />
