---
title: Mesure des désinstallations
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-14T08:03:47Z'
  edited_at: '2023-10-25T11:00:34Z'
  id: 4408933557137
  locale: fr
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/fr/articles/4408933557137
---
> **En bref** : mesurez le nombre de désinstallations de votre app et déterminez quelles sont les sources (sources média, campagnes, publicités ou géo) qui produisent des utilisateurs de qualité.

<div id="overview" />

## Introduction

Pour comprendre la valeur des utilisateurs de votre app, vous devez analyser à la fois le nombre d'installations et les taux de désinstallations. La mesure des désinstallations peut vous permettre d'évaluer les performances de votre app, et de comprendre dans quel cas et pour quel motif les utilisateurs abandonnent votre application.

<div id="how-does-it-work" />

### Comment fonctionne l'API de test ?

Une fois par jour, AppsFlyer envoie des notifications push silencieuses pour vérifier si une app est toujours installée sur un appareil donné. En l'absence de réponse, une désinstallation est enregistrée et celle-ci est attribuée à la source média qui a drainé initialement l'utilisateur.

<div id="how-to-use-uninstall-data" />

## Comment utiliser les données de désinstallations

Les exemples suivants vous permettent de comprendre ce que la mesure des désinstallations peut vous apporter, et comment vous pouvez mettre à profit ces données pour optimiser vos campagnes et l’engagement des utilisateurs.

<div id="compare-the-quality-of-sources" />

<Accordion title="Comparer la qualité des sources">

En comparant la qualité des utilisateurs d'après leur source (source média, campagne, publicité ou géo), vous pouvez repérer les sources média qui ont les taux de désinstallation les plus bas, et investir plus sur elles.

> 📄 **Exemple**
>
> Vous êtes un  marketeur spécialisé dans les apps de gaming pour PlayIt Gaming International. Vous venez tout juste de lancer une nouvelle application et vous avez lancé des campagnes sur deux sources média différentes (source média A et source média B).
>
> En consultant le tableau de bord, vous constatez que bien que la source média A ait le plus grand nombre d'installations (10 390), elle montre aussi le taux de désinstallations le plus élevé (30 %).
>
> La source média B quant à elle, annonce 5 949 installations et possède le taux de désinstallations le plus bas (12%).
>
> [![Uninstall rates.png](https://files.readme.io/36fb732bfe3a63729b1aa0913f2fe3f24df6a7c86adde9f5c2b95424d840dec4-33839423253137.png)](https://files.readme.io/36fb732bfe3a63729b1aa0913f2fe3f24df6a7c86adde9f5c2b95424d840dec4-33839423253137.png)
>
> En vous basant sur ces éléments, vous savez donc que vous pouvez affecter un plus grand budget à la source média B afin de chercher à obtenir des utilisateurs plus engagés.

</Accordion>

<div id="share-uninstall-data-with-ad-networks-for-optimization" />

<Accordion title="Partager les données de désinstallations avec les réseaux publicitaires afin d'optimiser les résultats">

Envoyer les postbacks d'évènement de désinstallation aux réseaux publicitaires est un bon moyen pour optimiser vos campagnes d'acquisition d'utilisateurs. Vous pouvez envoyer chaque événement de désinstallation [en mappant af\_uninstall à votre réseau publicitaire](/docs/measure-uninstalls#mappage-de-lévènement-de-désinstallation). Une fois le mappage effectué, un événement est envoyé dès qu’un utilisateur désinstalle l’app.Les réseaux publicitaires peuvent mettre à profit ces informations pour repérer les utilisateurs les moins engagés et plutôt chercher à obtenir ceux qui le sont le plus.

> 📄 **Exemple**
>
> Vous êtes un marketeur spécialisé dans les apps de gaming pour PlayIt Gaming International. La source média A est un réseau publicitaire avec lequel vous collaborez pour lancer votre nouvelle application sous Android. Dans la précédente campagne que vous avez lancé avec la source média A, 1 000 nouveaux utilisateurs ont installé votre app, puis 300 l'ont désinstallée. Pour la nouvelle campagne, il est souhaitable que la source média A reçoive les données liées aux désinstallations. Cela permettra à la source média A de répondre rapidement aux problèmes qui y sont liés.
>
> Avec les informations issues de la campagne précédente, Media source A crée une liste d’exclusion pour la campagne qui retire certains types d’utilisateurs des publicités diffusées dans la nouvelle campagne :
>
> * Les utilisateurs qui ont déjà montré qu’ils n'ont pas de valeur pour votre app.
> * Les utilisateurs qui désinstallent régulièrement vos apps.
>
> Media source A peut ainsi optimiser le ciblage d'audience pour que votre budget de campagne ne soit pas absorbé par les utilisateurs qui n’ont aucun intérêt à voir certaines publicités de la campagne.

</Accordion>

<div id="exclude-uninstalls-from-retargeting-campaigns" />

<Accordion title="Exclure les désinstallations des campagnes de retargeting">

Dans certains cas, pour vous conformer à <Anchor target="_blank" href="/marketers/fr/docs/apply-privacy-preserving-sdk-methods#scénarios-de-demande-de-consentement">différentes réglementations de type RGPD ou CCPA</Anchor>, vous êtes dans l'obligation d'exclure des campagnes de retargeting les utilisateurs qui ont déjà désinstallé votre application. Les informations liées aux désinstallations vous permettent de créer des listes d'exclusion, puis d'appliquer des mesures de confidentialité visant à protéger la vie privée et les données de vos clients.

Les méthodes pour exclure les utilisateurs sont les suivantes :

* <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview#user-journey-report-availability">Rapports de données brutes :</Anchor> une méthode manuelle qui vise à récupérer dans le **rapport de Désinstallations** la liste des utilisateurs qui ont effectué une désinstallation, puis d'en faire une liste d'exclusion.
* <Anchor target="_blank" href="/marketers/fr/docs/audiences-guide">AppsFlyer Audiences :</Anchor> une méthode automatique qui vise à définir un public cible en fonction de certains critères (exemple : les utilisateurs qui **n’ont pas désinstallé** votre app). Les utilisateurs qui ne répondent pas aux critères spécifiés sont exclus de l’audience.

> 📄 **Exemple**
>
> Vous êtes un marketeur spécialisé dans les apps de gaming pour PlayIt Gaming International. Vous lancez une campagne de retargeting pour l'une de vos apps Android et vous choisissez d'utiliser Audiences AppsFlyer pour définir une audience de retargeting. Les critères de votre audience sont les suivants :
>
> * Les utilisateurs qui n'ont pas désinstallé l'app.
> * Les utilisateurs qui n’ont pas lancé l’application sur les 30 derniers jours.
>
> Vous créez ainsi une audience de retargeting plus précise. Lorsque votre campagne de retargeting se lance, les publicités ne sont envoyées qu'aux utilisateurs qui ont été définis dans votre audience de retargeting.

</Accordion>

<div id="setting-up-uninstall-measurement" />

## Configurer la mesure des désinstallations

Pour mettre en place la mesure des désinstallations, une collaboration entre le marketeur et le développeur est indispensable. La marche à suivre dépend du système d’exploitation de votre application.

Le marketeur et le développeur doivent suivre les étapes suivantes :

<Tabs>
<Tab title="Android">

| Tâche | Propriétaire |
| --- | --- |
| [Connecter Firebase Cloud Messaging (FCM) à AppsFlyer](/docs/measure-uninstalls#connecter-la-messagerie-cloud-firebase-à-appsflyer-android) | Marketeur |
| [Configurer la mesure des désinstallations dans AppsFlyer](/docs/measure-uninstalls#configurer-la-mesure-des-désinstallations-dans-appsflyer) | Marketeur |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">Intégration avec le SDK</Anchor> | Développeur Android |
| [Tester la mesure des désinstallations](/docs/measure-uninstalls#tester-la-mesure-des-désinstallations) | Marketeur |
| [Facultatif] [Mapper l'événement de désinstallation](/docs/measure-uninstalls#mappage-de-lévènement-de-désinstallation) aux partenaires concernés (dans le tableau de bord) | Marketeur |

</Tab>

<Tab title="iOS">

| Tâche | Propriétaire |
| --- | --- |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#creating-a-p12-certificate">Générer un certificat P12</Anchor> | Développeur iOS |
| [Configurer la mesure des désinstallations dans AppsFlyer](/docs/measure-uninstalls#configurer-la-mesure-des-désinstallations-dans-appsflyer) | Marketeur |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">Intégration avec le SDK</Anchor> | Développeur iOS |
| [Tester la mesure des désinstallations](/docs/measure-uninstalls#tester-la-mesure-des-désinstallations) | Marketeur |
| [Facultatif] [Mapper l'événement de désinstallation](/docs/measure-uninstalls#mappage-de-lévènement-de-désinstallation) aux partenaires concernés (dans le tableau de bord) | Marketeur |

</Tab>
</Tabs>

<div id="implementation-procedures" />

## Marche à suivre

Pour permettre l'implémentation, votre développeur mobile doit intégrer un mécanisme qui répond aux notifications push envoyées sur votre application. Les étapes de la mise en œuvre varient en fonction du système d’exploitation.

<div id="connect-firebase-cloud-messaging-to-appsflyer-android" />

### Connecter la messagerie cloud Firebase à AppsFlyer (Android)

Pour mesurer les désinstallations sous Android, vous devez configurer la mesure des désinstallations dans AppsFlyer puis intégrer Firebase Cloud Messaging (FCM) à votre app.

<div id="http-v1" />

<Accordion title="HTTP V1">

**Pour configurer FCM HTTP V1 pour les désinstallations :**

1. **Pour obtenir l'ID du projet** :
   1. Allez à la [console FCM.](https://console.firebase.google.com/)
   2. Sélectionnez un projet.
   3. Allez dans **Aperçu du projet** > **Paramètres du projet.**

      ![UninstallFirebase.png](https://files.readme.io/15e74e10daa2f1f1d872f0c8fea274c9819c52c4655baa903728257dd6337e80-33839423254289.png)
   4. Copiez l'ID du projet. Vous en aurez besoin plus tard dans le processus.
2. **Pour attribuer le rôle de désinstallation à AppsFlyer :**
   1. Allez dans l'onglet **Comptes de service**.
   2. Cliquez sur **Gérer les permissions du compte de service**.   
      Un nouvel onglet du navigateur s'ouvre dans Google Cloud Platform.
   3. Dans le menu latéral, sélectionnez **Rôles**.
   4. Cliquez sur **+Créer un rôle.**
   5. Renseignez les champs de la façon suivante :
      * Titre : saisissez **Désinstallations AppsFlyer.**
      * ID : saisissez `af_uninstalls`.
      * Étape de lancement du rôle  : sélectionnez **Disponibilité générale**.
   6. Recherchez puis sélectionnez `cloudmessaging.messages.create`.  

      ![AddPermissions.png](https://files.readme.io/efd461ecb74a61c15232e30a6e10eaaecac18f2e24a28565ba8b208ce0654d1a-5542178507665.png)
   7. Cliquez sur **Ajouter**.
   8. Cliquez sur **Créer** .
3. **Pour attribuer à AppsFlyer le rôle de désinstallation FCM :**
   1. Dans le menu latéral, sélectionnez **IAM**.
   2. Cliquez sur **+ Ajouter**.
   3. Dans le champ **Nouveaux membres** , inscrivez af-uninstalls-tracking@af-uninstalls-tracking.iam.gserviceaccount.com
   4. Dans la liste **Sélectionner un rôle**, choisissez **Désinstallations AppsFlyer**.
   5. Cliquez sur **Enregistrer**.   
      Le rôle des désinstallations AppsFlyer a été attribué au compte de service AppsFlyer.

</Accordion>

<div id="legacy-http" />

<Accordion title="[Obsolète] HTTP version héritée">

> 🚧 **Important !**
>
> L'API en version HTTP héritée a été classée comme obsolète par Firebase le 20 juin 2023, elle sera définitivement supprimée en juin 2024. Si vous utilisez l'ancienne version d'API, nous vous recommandons vivement d'utiliser [l'API HTTP v1](/docs/measure-uninstalls#http-v1). <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/http-server-ref">En savoir plus</Anchor>

La mesure des désinstallations via la messagerie Firebase est prise en charge à partir de la version V4.7.0 du SDK Android.

**Pour obtenir la clé serveur Firebase :**

1. Créez un projet d'app Android Firebase (si ce n'est pas déjà fait), ou migrez votre projet de la **console développeur Google** (suivez les instructions ci-dessous) Pour plus d'informations, rendez-vous sur <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/android/client">Firebase</Anchor>.
2. Ouvrez la <Anchor target="_blank" href="https://console.firebase.google.com">Console</Anchor> Firebase.
3. Sur la page Console Firebase, accédez aux paramètres du projet (cliquez sur la roue dentée à côté de Vue d'ensemble du projet dans le volet gauche de la page).  

   ![firebase_cloud_messaging_server_key.png](https://files.readme.io/4e31c02a1bea013c823b0148ba1704d4492f66d04e23f0e13e00a9c0c22d286c-33839382513041.png)
4. Dans l'onglet Messagerie cloud, vous voyez deux clés serveur.
5. Copiez la **clé de serveur**.

</Accordion>

<div id="configure-uninstall-measurement-in-appsflyer" />

### Configurer la mesure des désinstallations dans AppsFlyer

<Tabs>
<Tab title="Android">

**Conditions requises** : le développeur Android doit suivre les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">instructions d'intégration</Anchor>.

**Pour configurer la mesure des désinstallations dans AppsFlyer** :

1. Dans AppsFlyer, allez à **Configuration** > **Paramètres de l'app**.
2. Si nécessaire, activez la **mesure des désinstallations**.
3. Sélectionnez **HTTP V1, puis saisissez l'ID de projet que vous avez préparé.**

   ![UninstallHTTPV1.png](https://files.readme.io/80d13e47ea7ae1585d2ecc0e2f7210572e47dba936557c8e96314e49b0d738d8-33839423258641.png)
4. Cliquez sur **Test de connexion**.  
   Le message Succès ! s'affiche.
5. Cliquez sur **Enregistrer les paramètres**.

</Tab>

<Tab title="iOS">

**Conditions requises** : le développeur IOS doit suivre les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">instructions d'intégration</Anchor>.

**Pour configurer la mesure des désinstallations dans AppsFlyer :**

1. Récupérez le fichier P12 fourni par votre développeur.
2. Dans AppsFlyer, rendez-vous dans**Configuration** > **Paramètres de l'app.**
3. Faites défiler la page jusqu'à la section Désinstallation.
4. Activez la **mesure des désinstallations**.

   ![Uninstall_iOS_p2.png](https://files.readme.io/3f9de3ebe6099886fa9bc210bd6e491ba91e8ff2c890c980f66c4d48398a597c-33839423260561.png)
5. Cliquez sur l’icône de téléchargement puis sélectionnez le fichier P12.
6. [Facultatif] Si le certificat P12 est protégé par un mot de passe, saisissez le mot de passe.
7. Cliquez sur **Valider** pour envoyer le certificat à AppsFlyer afin de procéder à sa vérification.
8. Cliquez sur ***Enregistrer les paramètres***.

</Tab>
</Tabs>

<div id="testing-uninstall-measurement" />

## Tester la mesure des désinstallations

Une fois l'implémentation terminée, vous pouvez installer puis désinstaller l’application afin de vérifier que les désinstallations sont correctement enregistrées. Les taux de désinstallation et de désinstallation s'affichent dans le tableau de bord général.

<Tabs>
<Tab title="Android">

Vous pouvez effectuer ce test sur les applications qui sont :

* Présentes dans Google Play Store
* En attente (non répertoriées dans Google Play Store)
* Disponibles en téléchargement direct
* Présentes dans les app stores équivalents

Gardez à l’esprit les éléments suivants lorsque vous testez une application Android :

* La mesure des désinstallations est traitée <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#uninstalls">quotidiennement</Anchor>. Tout événement de désinstallation est enregistré dans les 24 heures, mais si l’application est réinstallée au cours de cette période, alors l'événement n’est pas enregistré.
* **Les événements de désinstallation prennent jusqu’à 48 heures avant de s'afficher** dans <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">les rapports de données brutes</Anchor> et dans le tableau de bord AppsFlyer (rapport de performances agrégées).

</Tab>

<Tab title="iOS">

Gardez à l’esprit les éléments suivants lorsque vous testez une application IOS :

* Les désinstallations n'apparaissent pas immédiatement dans le tableau de bord AppsFlyer. En raison du fonctionnement des notifications push d'Apple, il faut au minimum 9 jours pour que les désinstallations apparaissent dans le tableau de bord. AppsFlyer met à jour et regroupe les mesures liées aux désinstallations une fois toutes les 24 heures.

  <div id="h_01HB8CXQ49QN0PH138V2PD2QXE" />

  > 📄 **Exemple**
  >
  > * Jour 1 : un utilisateur installe votre application.
  > * Jour 4 : Un utilisateur désinstalle votre application.
  > * Jour 12 : le service de notifications push signale la suppression de l'app 8 jours après sa désinstallation.
  > * Jour 13 : les données de désinstallations s'affichent dans le tableau de bord AppsFlyer et dans les données brutes.

* Si vous lancez des tests sur une version test de l’application, pensez à utiliser un environnement sandbox. Cf Instructions à l'attention des développeurs pour la [procédure liée aux désinstallations en environnement sandbox.](https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#testing-uninstall-measurement)

</Tab>
</Tabs>

<div id="mapping-the-uninstall-event" />

## Mappage de l'évènement de désinstallation

![Uninstall_event_postback.png](https://files.readme.io/9c3c7f3fd330720d4f6f41fdf509c5af00d042291c1350ab83a1951464ac8e8f-33839423261713.png)

Pour partager les données de désinstallations avec un réseau publicitaire, vous devez mapper <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#g">l’événement af\_uninstall</Anchor> à un partenaire. Contrairement aux postbacks d'événements in-app classiques, les événements de désinstallation ne sont pas envoyés en temps réel. L'heure de l'événement indiquée correspond à l'heure à laquelle AppsFlyer a appris que l'app a été désinstallée, et non à l'heure de la désinstallation en elle-même.

Remarques :

* AppsFlyer ne peut envoyer le postback que si l'événement a réellement lieu, et s'il est enregistré par AppsFlyer.
* Si aucune désinstallation ne figure sur la page de présentation du tableau de bord, ou dans le rapport de données brutes, cela signifie qu'aucun postback de désinstallation n'a été transmis au partenaire, même si l'événement **af\_uninstall** a été mappé.

<div id="limitations" />

#### Limites

* Les événements de désinstallation ne sont pas inclus dans les rapports de postback des événements in-app.
* L'événement **af\_uninstall** est pris en charge par l'ensemble des partenaires. Si vous souhaitez le mapper à un partenaire, mais qu'il s'avère que l'événement n'est pas disponible dans l'onglet intégration de celui-ci, contactez votre CSM ou écrivez à [hello@appsflyer.com](mailto:hello@appsflyer.com).

<Tabs>
<Tab title="Firebase">

Règles Firebase

</Tab>

<Tab title="GCM">

Règles GCM

</Tab>
</Tabs>

<div id="turning-off-uninstall-measurement" />

## Désactiver la mesure des désinstallations

<Tabs>
<Tab title="Android">

Si une clé de serveur Firebase/GCM est fournie, la mesure de désinstallation de l'app est activée par défaut. Les propriétaires d'app peuvent désactiver cette fonctionnalité via le tableau de bord.

</Tab>

<Tab title="iOS">

Si un certificat P12 est fourni et validé, la mesure de désinstallation de l'app est activée par défaut. Les propriétaires d'app peuvent désactiver cette fonctionnalité via le tableau de bord.

</Tab>
</Tabs>

**Important** ! Pour qu'une désinstallation soit signalée, l'option **Activer la mesure des désinstallations** doit être activée au moment de l'installation de l'app. Les installations qui se produisent lorsque l'option **Activer la mesure des désinstallations** est désactivée ne seront pas transmises.

<div id="to-turn-off-uninstall-measurement" />

#### **Pour désactiver la mesure des désinstallations** :

1. Dans AppsFlyer, rendez-vous dans **paramètres de l'app**.
2. Rendez-vous dans **Attribution** > **Mesure des désinstallations** et désélectionnez **Activer la mesure des désinstallations.**

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Remarques |
| --- | --- |
| CUID | Le CUID n'est pas envoyé dans les postbacks de désinstallation. |

</Accordion>

<div data-zendesk-anchors="overview=introduction h_01HB8CXQ4824V2WEPYGK8YS4DC=introduction how-does-it-work=comment-fonctionne-lapi-de-test h_01HB8CXQ48JEJECC1HR79DXCRK=comment-fonctionne-lapi-de-test how-to-use-uninstall-data=comment-utiliser-les-donn%C3%A9es-de-d%C3%A9sinstallations h_01HB8CXQ48E2SRN95MH4E2H7ZH=comment-utiliser-les-donn%C3%A9es-de-d%C3%A9sinstallations h_01HB8CXQ48HX9RH50G45FZMZTK=compare-the-quality-of-sources h_01HB8CXQ48DZYQW7FYBD3XYREM=exemple h_01HB8CXQ488E22GPCEBE69VQ3M=share-uninstall-data-with-ad-networks-for-optimization h_01HB8CXQ48ZE5TTZRPQE5SEKJS=exemple-1 h_01HB8CXQ48JTET73GH0QQBX5HF=exclude-uninstalls-from-retargeting-campaigns h_01HB8CXQ4832ZHRYQECYCQPP66=exemple-2 setting-up-uninstall-measurement=configurer-la-mesure-des-d%C3%A9sinstallations h_01HB8CXQ4810HTB45FAS5ZVRHF=configurer-la-mesure-des-d%C3%A9sinstallations implementation-procedures=marche-%C3%A0-suivre h_01HB8CXQ489HRF72VRZ4G532GX=marche-%C3%A0-suivre connect-firebase-cloud-messaging-to-appsflyer-android=connecter-la-messagerie-cloud-firebase-%C3%A0-appsflyer-android h_01HB8CXQ48ZD5Y0RKTG1W51TKW=connecter-la-messagerie-cloud-firebase-%C3%A0-appsflyer-android h_01HB8CXQ4865MNVG0VERSNSE3F=http-v1 h_01HB8CXQ48H079WQ6Q6G0XSQC7=legacy-http h_01HB8CXQ48ENMG65YH5ECGST9Z=important- configure-uninstall-measurement-in-appsflyer=configurer-la-mesure-des-d%C3%A9sinstallations-dans-appsflyer h_01HB8CXQ48CVA9B8B78W0H357C=configurer-la-mesure-des-d%C3%A9sinstallations-dans-appsflyer testing-uninstall-measurement=tester-la-mesure-des-d%C3%A9sinstallations h_01HB8CXQ48SW2TT5Z85XD3XWT6=tester-la-mesure-des-d%C3%A9sinstallations mapping-the-uninstall-event=mappage-de-l%C3%A9v%C3%A8nement-de-d%C3%A9sinstallation h_01HB8CXQ499ABX9ZGDFB1VAE8W=mappage-de-l%C3%A9v%C3%A8nement-de-d%C3%A9sinstallation limitations=limites h_01HB8CXQ49F2ARQTEV8Q032P9V=limites turning-off-uninstall-measurement=d%C3%A9sactiver-la-mesure-des-d%C3%A9sinstallations h_01HB8CXQ49Y5NCG7GK93HXHYMD=d%C3%A9sactiver-la-mesure-des-d%C3%A9sinstallations to-turn-off-uninstall-measurement=pour-d%C3%A9sactiver-la-mesure-des-d%C3%A9sinstallations h_01HB8CXQ49WXZS4M6CK5XG1BCX=pour-d%C3%A9sactiver-la-mesure-des-d%C3%A9sinstallations h_01HB8CXQ4916CJ9NDZWGWQHKSA=traits-and-limitations" />
