---
title: Ajouter une application à AppsFlyer
metadata:
  keywords:
    - Add App
    - adding an app
    - Advertisers
    - could not add app
    - security reasons
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2016-01-20T08:57:00Z'
  edited_at: '2023-11-30T11:59:07Z'
  id: 207377436
  locale: fr
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/fr/articles/207377436
---
> **En bref :** découvrez comment ajouter votre application à AppsFlyer pour obtenir des données d'attribution des installations et événements in-app, pour analyser ensuite les données à l'aide des différents outils AppsFlyer.

<div id="overview" />

## Présentation

Si vous n'avez pas encore ajouté d'app à votre tableau de bord, la page onboarding de l'app s'affichera lorsque vous vous connecterez à AppsFlyer. L'onboarding de l'app vous guidera étape par étape pour ajouter votre application et la préparer à l'attribution. 

<div id="entering-the-wizard-for-adding-an-app" />

### Accéder à l'assistant pour ajouter une application

Vous pouvez accéder à l'assistant d'ajout d'applications depuis la plateforme, ou vous pouvez ajouter votre app via la page d'onboarding de l'app (pour les apps Android et iOS uniquement).

**Pour accéder à l'assistant depuis la page d'onboarding de l'app :**

* Dans l'étape **Ajouter votre application**, cliquez sur **Ajouter une app** et suivez les instructions.

> 📘 **Remarque**
>
> Si la page d'onboarding n'est pas encore ouverte, cliquez sur **Onboarding de l'app** dans le menu supérieur > liste déroulante > adresse e-mail

![onboarding page.png](https://files.readme.io/8903839c25f12df28e1c4b488699670e2dadca83af9ddfebfc0cf4eacd2ce744-33198275479953.png)

**Pour accéder à l'assistant depuis la plateforme :**

* Dans le menu supérieur > **Mes apps,** cliquez sur **+ Ajouter une app**.
* Sur la page d'accueil d'AppsFlyer, cliquez sur **+ Ajouter une app**
* Dans le menu supérieur > adresse e-mail, menu déroulant > Onboarding de l'app, cliquez sur **+ Onboarding d'une nouvelle app**

<Image alt="add an app (1).png" src="https://files.readme.io/894b7b76c1da76e2308b110266cbffeb579c551033ce302ade182c1d63fd9384-33198275483793.png" width="593px" />

<div id="adding-an-app" />

## Ajouter une application

Une fois que vous avez [ouvert l'assistant **Ajouter une app**](/docs/adding-an-app-to-appsflyer#accéder-à-lassistant-pour-ajouter-une-application) , procédez comme suit :

1. [Saisissez les éléments de l'app](/docs/adding-an-app-to-appsflyer#saisir-les-infos-de-lapp).
2. [Saisissez les infos supplémentaires](/docs/adding-an-app-to-appsflyer#2--saisir-les-infos-supplémentaires-ne-concerne-pas-les-apps-web).
3. Cliquez sur **Ajouter mon app**.
4. Copiez la clé Dev à utiliser pour <Anchor target="_blank" href="/marketers/fr/docs/getting-started-onboarding-for-marketers#étape-3-intégration-du-sdk">l’intégration du SDK</Anchor> (vous pourrez la récupérer à partir de la page <Anchor target="_blank" href="/marketers/fr/docs/app-settings#paramètres-généraux-de-lapp">Paramètres de l’app</Anchor>).
5. Cliquez sur **Terminé** ou sur **+ Ajouter une autre app** pour ajouter de nouvelles apps.

> 📘 **Note**
>
> * Seuls les admins et les utilisateurs du compte <Anchor target="_blank" href="/marketers/fr/docs/user-management">disposant des autorisations nécessaires</Anchor> peuvent ajouter des applications.
> * Lorsque vous suivez les étapes d'ajout d'une application (ci-dessous), les options disponibles varient en fonction des options précédemment sélectionnées.

Après avoir enregistré l'app, celle-ci apparaîtra dans le tableau de bord. Pour que les installations et les événements in-app soient enregistrés et attribués aux bonnes sources média, vous devez :

* Intégrer le SDK
* Connecter l'app aux partenaires dans le Marketplace des partenaires

Voir <Anchor target="_blank" href="/marketers/fr/docs/getting-started-onboarding-for-marketers">toutes les étapes</Anchor> du processus d'intégration.

<div id="enter-app-details" />

### Saisir les infos de l'app

Sélectionnez la plateforme de l'app et entrez les informations requises, comme indiqué ci-dessous :

<div id="android-androidtv-fire" />

<Accordion title="Android, AndroidTV, Fire">

Utilisez cette option pour les plateformes suivantes :

* Android (mobile)
* AndroidTV
* Amazon Fire
* Amazon Fire TV
* Kindle

| Statut Google Play | Quand l'utiliser ? | Infos requises |
| --- | --- | --- |
| <span id="in-store"></span>Dans le store | Votre application est actuellement disponible dans le Google Play store | **URL de Google Play** (copiée depuis Google Play)<ul><li>**Exemple :** https://play.google.com/store/apps/details?id=com.appsflyer.adNetworkTest& hl=en&gl=GB</li><li>**Important !**<ul><li>Si votre app n'est **pas** listée dans Google Play store États-Unis :<ul><li>L'URL doit inclure le code pays de tout store dans lequel l'app est répertoriée, comme indiqué dans l'exemple ci-dessus : **& gl=`{country_code}.** Si vous n'indiquez pas le code du pays, vous recevrez un message d'erreur lorsque vous tenterez d'ajouter l'application.</li><li>Le code de la langue est facultatif : **& hl={language_code}`**</li></ul></li><li>Si votre store **est** listé dans Google Play États-Unis, les codes de pays et de langue sont facultatifs.</li></ul></li></ul> |
| <span id="pending-approval-not-published"></span>Approbation en attente / non publiée | Votre application n'est pas encore publiée ou attend d'être approuvée par Google Play | **Nom du package Android**<ul><li>**Exemple :** com.appsflyer.adNetworkTest</li><li>**Remarque** : le nom du package est sensible à la casse</li><li>**Format :**<ul><li>Deux segments minimum (un ou plusieurs points)</li><li>Chaque segment doit commencer par une lettre</li><li>Tous les caractères sont des chiffres, des lettres, ou des tirets du bas (a-z, A-Z, 0-9 ou \_).</li><li>Longueur maximale du paramètre : 100 caractères.</li></ul></li></ul>Pour plus d'informations, consultez la <Anchor target="_blank" href="https://developer.android.com/studio/build/application-id">documentation à l'usage des développeurs Android</Anchor> |
| <span id="third-party-store-out-of-store"></span>Store tiers et hors-store | Votre application se trouve dans un app store Android autre que Google Play, et/ou elle peut être téléchargée ailleurs que depuis un app store. | **Nom du package Android**<br /><br />Pour connaître les infos détaillées, cf ligne précédente (approbation en attente/non publiée)<br /><br />**Nom du canal :** nom unique que vous avez défini pour chaque store tiers/location dans l'APK individuelle préparée pour le store ou la location<ul><li>**Exemple :** Amazon</li><li>**Format :** lettres majuscules ou minuscules uniquement (a-z ou A-Z). Aucun autre caractère, de type trait d'union (-) ou tiret du bas (\_), n'est autorisé.</li></ul>**URL de l'app** (copiée depuis l'app store tiers ou quelque part hors-store)<br /><br /><br /><br />**<span id="important"></span><span id="01H815FE641Q6N5JY5846QE59Y"></span>Important !**<br />Si votre application est disponible via plus d'une source (soit tout ensemble de Google Play, d'app stores tiers ou d'emplacements hors store), nous vous recommandons vivement d'étudier les options pour <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution">mettre en place une attribution multi-stores Android.</Anchor> Si l'implémentation est la bonne dès le départ, vous pourrez accéder aux données que vous cherchez, et dans le format souhaité. |

</Accordion>

<div id="ios-tvos-macos" />

<Accordion title="ioS, tvOS, MacOS">

Utilisez cette option pour les plateformes suivantes :

* iOS
* tvOS
* MacOS

| Statut de l'app store | Quand l'utiliser ? | Infos requises |
| --- | --- | --- |
| <span id="in-store::f93cfa22"></span>Dans le store | Votre application est actuellement disponible dans l'app store | **URL de l'app store** (copiée depuis l'app store)<ul><li>**Exemple :** https://apps.apple.com/us/app/partner-integrations/id1543229303</li><li>**Remarque :**<ul><li>vérifiez que l'URL comporte bien le code pays de l'app store à 2 lettres (par exemple, **us** dans l'URL ci-dessus)</li><li>Une app qui a été ajoutée à l'app store avant le 14 juin 2019 peut contenir itunes.apple.com dans son URL (à la place de apps.apple.com).</li></ul></li></ul> |
| <span id="pending-approvalnot-published"></span>Approbation en attente / non publiée | Votre application n'est pas encore publiée ou attend d'être approuvée par l'app store | **Pays** de l'app store à qui l'app a été soumise<br /><br />**ID d'app** attribué par l'app store, sans le préfixe id<ul><li>**Exemple :** 1543229303</li><li>**Format :** 9 ou 10 chiffres (0-9)</li></ul> |

</Accordion>

<div id="windows-xbox" />

<Accordion title="Windows">

Utilisez cette option pour les plateformes suivantes :

* Windows Phone
* Windows (ordinateur)

| Statut du Microsoft Store | Quand l'utiliser ? | Infos requises |
| --- | --- | --- |
| Dans le store | Votre application est actuellement disponible dans le Microsoft Store | **URL Microsoft Store** (copiée depuis le Microsoft Store)<ul><li>**Exemple:** https://www.microsoft.com/en-us/p/wordament/9wzdncrfhwfg</li><li>**Remarque :** L'URL ci-dessus est un exemple pour une application Windows Phone. Le format de l'URL varie pour les applications de bureau Windows.</li></ul> |
| Approbation en attente / non publiée | Votre app n'a pas encore été publiée ou attend d'être approuvée par le store | **ID d'app** attribué par le Microsoft Store<ul><li>**Exemple :** 9wzdncrfhwfg</li><li>**Remarque** : l'ID d'app est sensible à la casse.</li></ul> |

</Accordion>

<div id="web-pba" />

<Accordion title="web (PBA)">

<div id="note-3" />

> 📘 **Note**
>
> Une application web permet de définir un site web à inclure dans un bundle de marques pour notre fonctionnalité People-Based Attribution (PBA).
>
> * Cette option n'est disponible que pour les clients qui ont souscrit à la fonctionnalité PBA.
> * <Anchor target="_blank" href="/marketers/fr/docs/people-based-attribution-pba-overview">En savoir plus</Anchor> sur l'option PBA et l'attribution des visites web, des événements web et des installations assistées par site web pour obtenir une vue globale des parcours des clients à travers les canaux, plateformes et appareils.

**URL complète :** URL complète du site web dont vous souhaitez mesurer le trafic. Il s'agit du site web sur lequel vous avez ou allez implémenter le <Anchor target="_blank" href="/marketers/fr/docs/onboarding-guide-to-people-based-attribution#2">SDK web PBA</Anchor>.

[<Image alt="URL_diagram" src="https://files.readme.io/45c6e433af693fd8c293380192a8e60f26c82588195bab61bafbc9839baf5c7b-33198323426961.png" width="377px" />](https://files.readme.io/45c6e433af693fd8c293380192a8e60f26c82588195bab61bafbc9839baf5c7b-33198323426961.png)

Inclure –

* schéma
* sous-domaine [facultatif]
* Nom du domaine
* domaine de premier niveau
* chemin *[facultatif] –*l'adresse d'un répertoire ou d'une page de votre site web

**Nom de l'app :** nom que vous avez choisi pour votre application

* Longueur maxi du paramètre : 100 caractères
* Les balises XSS ne sont pas autorisées

<div id="important-1" />

> 🚧 **Important !**
>
> Une fois que vous avez créé une application web, vous ne pouvez pas modifier ses propriétés (URL et nom de l'app) sans la supprimer et la recréer. **Cela signifie que vous devez également <Anchor target="_blank" href="/marketers/fr/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle">supprimer le bundle de marques</Anchor> dont elle fait partie.**

**Étapes suivantes :**

* Ajoutez votre nouvelle application web à un <Anchor target="_blank" href="/marketers/fr/docs/pba-brand-bundles-and-settings">bundle de marques PBA</Anchor> pour la voir dans le tableau de bord PBA.
  * Assurez-vous que toutes les apps mobile que vous souhaitez inclure dans le bundle de marques ont été ajoutées à votre compte *avant* de créer le bundle.
* <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide">Intégrez le SDK web PBA</Anchor> au site web spécifié dans l'app web pour permettre la transmission des données de mesure.

</Accordion>

<div id="roku" />

<Accordion title="Roku">

**Nom de l'app :** nom du canal copié à partir du <Anchor target="_blank" href="https://developer.roku.com/developer">tableau de bord de développeur Roku</Anchor>.

* **Exemple :** mon canal Roku
* **Format :**
  * Longueur maximale du paramètre : 100 caractères.
  * Les balises XSS ne sont pas autorisées

**ID de canal :** ID numérique attribué au canal par Roku

* **Exemple :** 1234567
* **Format :**
  * Caractères numériques, 0-9
  * Longueur maxi du paramètre : 50 caractères.
* **Comment le trouver ?**
  * À partir du <Anchor target="_blank" href="https://developer.roku.com/developer">tableau de bord de développeur Roku</Anchor>, cliquez sur le nom du canal que vous ajoutez à AppsFlyer. Cela ouvre la page Aperçu et Publication Roku pour le canal.
  * Le numéro qui apparaît à la fin de l'URL de la page dans votre navigateur est l'ID du canal :

    <Image alt="find_channel_id.png" src="https://files.readme.io/11ef90a222a1deaf6d4718169e5a29f734f0f05d859c009d47b8ae5cb6519639-4411061399569.png" width="476px" />

</Accordion>

<div id="vizio-smartcast" />

<Accordion title="Vizio SmartCast">

**Nom de l'app :** nom que vous avez choisi pour votre application

**ID d'app :** l'ID de l'application telle qu'elle est reconnue par Vizio (commence généralement par les lettres **vz**). Si vous avez besoin de confirmer l'ID de l'app, contactez votre représentant Vizio.

</Accordion>

<div id="samsung-tizen" />

<Accordion title="Samsung Tizen">

**Nom de l'app :** nom que vous avez choisi pour votre application

**ID d'app :** l'ID de bundle attribué à votre application par Samsung. Vous le trouverez à la fin de l'URL de l'app store de votre application :

<Image alt="samsung_tizen_url_app_id.png" src="https://files.readme.io/d4789b59faf551cfc1603dd3d8f95f286d5bb45b59927489bdd2263ac03a3a36-7369359502097.png" width="364px" />

</Accordion>

<div id="lg-webos" />

<Accordion title="LG webOS">

**Nom de l'app :** nom que vous avez choisi pour votre application

**ID d'app :** l'ID de l'application LG webOS

</Accordion>

<div id="playstation" />

<Accordion title="PlayStation">

**Nom de l'app :** nom que vous avez choisi pour votre application

**ID d'app :** l'ID du concept PlayStation, un identifiant unique attribué à un jeu ou à un autre concept de contenu. Il apparaît sous la forme d'un numéro de 5 à 9 chiffres dans l'URL du PlayStation Store :

![playstation_app_id_url.png](https://files.readme.io/df92705244e55e7adc44a88076556609983ec3dff89c03df77e19f0f1a061bbb-33198323434513.png)

</Accordion>

<div id="vidaa" />

<Accordion title="Vidaa">

**Nom de l'app :** nom que vous avez choisi pour votre application

**ID d'app :** l'ID d'application Vidaa

</Accordion>

<div id="steam" />

<Accordion title="Steam">

**Nom de l'app :** nom que vous avez choisi pour votre application

**ID d'app :** l'ID d'app Steam. Il s'agit du numéro de 5-8 chiffres qui apparaît dans l'URL de la boutique Steam :

![steam_store_app_url.png](https://files.readme.io/4976c0323eab0c08b61d4a1a7a75ebf7ea9fcd819176ff574421f0de4d8c614c-33198275497617.png)

</Accordion>

<div id="meta-quest" />

<Accordion title="Meta Quest (Oculus)">

**Nom de l'app :** nom que vous avez choisi pour votre application

**ID d'app :** l'ID de l'app Meta Quest (tel qu'il apparaît dans le store où l'app a été téléchargée).

* Exemple : 1903584373052986

</Accordion>

<div id="nintendo-switch" />

<Accordion title="Nintendo Switch">

**Nom de l'app :** nom que vous avez choisi pour votre application

**ID d'app :** l'ID de l'app Nintendo Switch (tel qu'il apparaît dans le store où l'app a été téléchargée).

</Accordion>

<div id="xbox" />

<Accordion title="Xbox">

**Nom de l'app :** nom que vous avez choisi pour votre application

**ID d'app :** l'ID de l'app Xbox (tel qu'il apparaît dans le store où l'app a été téléchargée).

* **Exemple :** 9wzdncrfhwfg
* **Remarque** : l'ID d'app est sensible à la casse.

</Accordion>

<div id="epic-games" />

<Accordion title="Epic Games">

**Nom de l'app :** nom que vous avez choisi pour votre application

**ID d'app :** l'ID de l'app Epic Games (tel qu'il apparaît dans le store où l'app a été téléchargée).

</Accordion>

<div id="native-pc" />

<Accordion title="Native PC">

**Nom de l'app :** nom que vous avez choisi pour votre application

**ID d'app :** l'ID de l'application Native PC (caractères possibles : `A-Z` `a-z` `0-9` `.` `_` `-`)

</Accordion>

<div id="enter-additional-information-not-applicable-to-web-apps" />

### #2 – Saisir les infos supplémentaires *(ne concerne pas les apps web) :*

<Image alt="" src="https://files.readme.io/561aea51bbfaa733721040706cac2b9520e35cfe71027fa34d08ed7890baf00c-33198323448081.png" width="559px" />

1. **Sélectionner une devise**

   Sélectionnez la devise qui sera utilisée pour afficher les données de cette application dans le tableau de bord. Les événements de revenus et de dépenses seront convertis dans cette devise en se basant sur le taux de change en vigueur au moment de l'événement. <Anchor target="_blank" href="/marketers/fr/docs/app-settings#localization-currency">En savoir plus</Anchor> sur le paramétrage de la devise d'une app, et ses effets.

   <div id="important-2" />

   > 🚧 **Important !**
   >
   > Choisissez avec soin la devise que vous voulez utiliser pour cette app. Vous ne pourrez plus la modifier une fois que les coûts et les revenus auront été enregistrés.

2. **Sélectionner un fuseau horaire**

   Synchronisez le fuseau horaire que vous choisissez ici avec celui que vous avez défini avec les autres partenaires d'attribution (comme Meta ads et Google Ads). Vous aurez ainsi la garantie que les données rapportées dans le tableau de bord AppsFlyer et les données que vous recevez de ces mêmes partenaires seront parfaitement accordées. <Anchor target="_blank" href="/marketers/fr/docs/changing-app-time-zone-settings">En savoir plus</Anchor> sur le paramétrage de fuseau horaire d'une app, et ses effets.
3. **Paramétrer les indications d'une application destinée aux enfants**

   Sélectionnez **Oui** ou **Non** pour indiquer si votre application est destinée aux enfants ou au tout public (enfants et adultes).  
   Si vous avez sélectionné **Oui :**

   1. Ouvrez et lisez le <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">guide</Anchor> sur la conformité des applications destinées aux enfants.
   2. Cochez la case pour confirmer que vous avez lu le guide et que vous mettrez en place les systèmes de vérifications qui y sont détaillés.

      <div id="note-6" />

      > 📘 **Remarque**
      >
      > Deux semaines après avoir ajouté l'application, vous recevrez une notification vous demandant de confirmer que vous avez mis en place des contrôles de confidentialité des applications destinées aux enfants. Une fois fait, vous recevrez un message de confirmation. Vous pouvez accéder au message de confirmation à partir du centre de notification, ou consulter les détails de la confirmation dans le <Anchor target="_blank" href="/marketers/fr/docs/audit-log">journal d'audit</Anchor>.


<div id="about-pending-apps" />

## À propos des applications en attente

Travailler avec une application en attente peut être utile lorsque vous corriger des bugs pour tester le SDK d'AppsFlyer.

Lorsqu'une app a le statut *en attente* dans le tableau de bord, cela n'affecte ni la collecte ni la mesure des données. Si l'app est *en ligne* ou *en attente* sur un app store et que des utilisateurs l'installent et interagissent avec elle, les données des événements d'installation et des événements in-app seront toujours enregistrées dans le tableau de bord.

Une fois que votre app n'est plus en attente et passe en ligne, AppsFlyer détecte et met automatiquement à jour son statut, vous n'avez donc pas à l'ajouter une nouvelle fois. <Anchor target="_blank" href="/marketers/fr/docs/why-is-my-app-still-pending">En savoir plus</Anchor> sur les apps en attente et sur l'opération facultative visant à actualiser manuellement leur statut.

<div id="troubleshooting" />

## Dépannage

Résoudre les problèmes les plus courants :

<div id="app-wasnt-added" />

<Accordion title="L'app n'a pas été ajoutée">

Si cette erreur se produit, contactez votre CSM ou envoyez un e-mail à [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<div id="app-not-in-the-store" />

<Accordion title="L'app n'est pas présente dans le store">

Vérifiez que vous avez correctement copié l'URL du store, et que vous avez utilisé le bon nom / ID d'app.

</Accordion>

<div id="cant-access-marketplace" />

<Accordion title="Accès au marché impossible">

Ce problème peut survenir si vous ajoutez une app Android depuis un store situé hors des États-Unis. Pour le résoudre, veuillez suivre les étapes suivantes :

1. Ajoutez l'app avec le statut **En attente d'approbation/non publiée**, comme décrit ci-dessus.
2. Allez sur la page AppsFlyer des **Paramètres de l'app**.
3. Modifiez le **pays de l'app store** en choisissant celui qui convient (ex : Japon).

</Accordion>

<div id="something-went-wrong" />

<Accordion title="un problème est survenu... Merci de bien vouloir réessayer.">

Cette erreur peut s'expliquer par la tentative d'ajout d'une app Android sans code pays (pour les apps **non** listées dans Google Play Store États-Unis). Voir [ci-dessus](/docs/adding-an-app-to-appsflyer#in-store) la marche à suivre pour résoudre ce problème.

</Accordion>

<div data-zendesk-anchors="overview=pr%C3%A9sentation 01H8Y09SSKZS2RHM35JT16ESKM=pr%C3%A9sentation entering-the-wizard-for-adding-an-app=acc%C3%A9der-%C3%A0-lassistant-pour-ajouter-une-application 01H8Y0K9EHWH05DB5K02ASJG11=acc%C3%A9der-%C3%A0-lassistant-pour-ajouter-une-application 01H8F2TENNWXADKVZFHY9SE8JC=remarque adding-an-app=ajouter-une-application 01H8ECFB7V0DCNE0ZKPZ2GCVMP=ajouter-une-application 01H81661SR41SQFZZ0AW6K2EDM=note 1-%E2%80%93-enter-app-details=saisir-les-infos-de-lapp 01H815FE64VZZS9WGJSC8VY74D=saisir-les-infos-de-lapp 01H815FE64CXEHWTV40NVYQHGJ=android-androidtv-fire 01H815FE64X0SPA71TBQ9T4ZVB=ios-tvos-macos 01H815FE64ZZA2N1XQFBRXVF41=windows-xbox 01H815FE64XZKDJW1CX5R1JE1T=web-pba 01H815FE646GWA7KJ83KTGHH05=note-1 01H815FE65R1Z06TJR0DNC8PFY=important- 01H815FE65X37H40AN99EZJ940=roku 01H815FE654W6D4FCANR1DET8A=vizio-smartcast 01H815FE65J6T610QQXWJS0CJS=samsung-tizen 01H815FE65CRW81AD1006KHGV4=lg-webos 01H815FE65ESQZ56C8B4HG9P8M=playstation 01H815FE65483DV8MD4STH3QTR=vidaa 01H815FE655PZS1H9YW95X1R53=steam 01H815FE655XP075WYRVVFKD4F=meta-quest 01H815FE65XJEVHNT45SHGWJS4=nintendo-switch 01H815FE6598PD87PNBE7MFEQ8=xbox 01H815FE658WJCB1ZCPGAD4GGS=epic-games 01H815FE652P3HCWY2PEDJJARM=native-pc 2-%E2%80%93-enter-additional-information-not-applicable-to-web-apps=2--saisir-les-infos-suppl%C3%A9mentaires-ne-concerne-pas-les-apps-web 01H815FE65AWE8VKV9FYJ7N8MV=2--saisir-les-infos-suppl%C3%A9mentaires-ne-concerne-pas-les-apps-web 01H815FE65X7BCFKH1EEFA91GQ=important--1 h_01H9MYF17VNBETQ0HS745EJ85H=remarque-1 about-pending-apps=%C3%A0-propos-des-applications-en-attente 01H815FE65MYPABC3DTVEMA8E9=%C3%A0-propos-des-applications-en-attente troubleshooting=d%C3%A9pannage 01H815FE655HS8EA4R00D0VCYD=d%C3%A9pannage 01H815FE65V2GYP0Q612512DE0=app-wasnt-added 01H815FE65A0HPTVVCT42QQA6M=app-not-in-the-store 01H815FE65EN3PBSH5BKRGNNXD=cant-access-marketplace 01H815FE65FR4ATDA4CVX2FW9N=something-went-wrong" />
