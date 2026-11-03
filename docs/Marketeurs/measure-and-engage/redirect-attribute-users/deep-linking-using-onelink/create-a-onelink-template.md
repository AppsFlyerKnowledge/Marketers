---
title: Templates OneLink
metadata:
  keywords:
    - template
    - Marketers
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2014-11-03T12:35:49Z'
  edited_at: '2023-11-15T15:26:26Z'
  id: 207032246
  locale: fr
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/fr/articles/207032246
---
> **En bref :** créez un template pour former la base de redirection pour tous les liens OneLink que vous créez pour vos différentes campagnes marketing. Un template est requis pour créer des liens et des expériences d'utilisateur final.

## Templates OneLink

<Embed title="Lecteur vidéo YouTube" typeOfEmbed="youtube" url="https://www.youtube.com/embed/d4AtCJ9122Q" providerUrl="https://www.youtube.com" />

Un template OneLink :

* N'est pas un lien cliquable pour vos utilisateurs finaux, c'est le socle qui permet de générer de nombreux liens personnalisés. Habituellement, vous n’avez besoin que d’un seul template par app (en dehors des tests) pour générer autant de liens que vous le souhaitez pour toutes vos campagnes publicitaires.
* C'est l'endroit où vous prenez vos décisions sur la manière de rediriger les utilisateurs, selon la plateforme de leur appareil, et selon qu'ils ont déjà installé votre app ou non.
* Représente la logique de routage au centre de tous les liens OneLink que vous créez pour vos campagnes marketing. Cela inclut les paramètres de redirection pour :
  * **Les nouveaux utilisateurs qui n'ont pas installé votre app** vers l'app store ou l'URL web appropriée.
  * **Les utilisateurs existants avec votre app installée** : ouverture de l’app via des liens d’app Android, des liens universels iOS ou des schémas d’URI. Cela nécessite un développeur.
  * **Remarque** : les paramètres de redirection pour le site web ou l’App Store peuvent être remplacés au niveau du lien.

## Procédures

| **Personnes concernées**<ul><li>Seul un marketeur est nécessaire pour configurer la logique de redirection pour les nouveaux utilisateurs qui n'ont pas installé votre app (par exemple, vers l'app store ou la page web appropriée).</li><li>Pour ajouter une logique de redirection pour les utilisateurs existants qui ont déjà installé votre app (par exemple pour ouvrir l’app), un marketeur et des développeurs Android/iOS sont requis.</li></ul> |
| --- |
| **Conditions préalables**<ul><li>Un compte AppsFlyer avec au moins une app.</li><li>Le marketeur doit être un admin AppsFlyer, ou avoir <Anchor target="_blank" href="/marketers/fr/docs/user-management">l'autorisation d'ajouter/de modifier des templates OneLink</Anchor>.</li></ul> |
| **Durée**<br /><br />Environ une heure et demie, en collaboration avec vos développeurs Android/iOS. |
| **Résultat**<ul><li>Un template à partir duquel vous pouvez créer des liens qui dirigent les utilisateurs vers l'app store, la page web ou l'app appropriée en fonction de leur appareil.</li></ul> |

<div id="create-a-onelink-template-with-redirection-logic-for-new-app-users" />

<Accordion title="Créer un template OneLink avec redirection pour les nouveaux utilisateurs">

**Pour créer un template OneLink :**

1. Dans le tableau de bord AppsFlyer, allez dans **Experiences et deep linking** > **Gestion OneLink.**  
   La suite OneLink est une fonctionnalité proposée au niveau du compte, elle vous permet de créer des templates OneLink avec leurs liens personnalisés pour l'ensemble de vos apps.  

   [![](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)

   **Remarque** : si vous n'avez pas créé de templates, un assistant d'accompagnement s'ouvre. Suivez les instructions de l'assistant et ignorez le reste de cette procédure.
2. Cliquez sur l'icône Menu > **Ajouter un template OneLink**.  
   La page de configuration de template OneLink s'ouvre.  

   [![OneLink_template_page_en-us.png](https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png)](https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png)
3. Dans le champ **nom du template** **One** Link, saisissez un nom.

   > 📘 **Note**
   >
   > * Un bon nom de template OneLink contient le **nom de l'app** (par exemple livrez\_moi) ou le cas d'utilisation, ou bien l'expérience représentée par le OneLink (ex : page\_accueil\_pre\_lancement).
   > * Le nom ne doit pas inclure le nom de la campagne, du canal ou de la source média (puisqu'il ne s'agit pas du vrai lien de l'utilisateur final, mais seulement le sous-modèle qui permet de créer différents liens), ni le nom de la plateforme (Android, iOS, puisque l'utilisation d'un template OneLink est souvent motivée par la pluralité des plateformes).
   > * Ce nom de template est utilisé exclusivement en interne. Il n'affecte pas vos données d'attribution marketing et n'est pas visible par les utilisateurs.

4. Dans le champ **Sous-domaine**, entrez votre nom de <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-knowledge-base-glossary#subdomain-sous-domaine">sous-domaine</Anchor>.
   * Choisissez un sous-domaine qui correspond à votre marque. Par exemple, si votre site web s'appelle www.abcd.com, choisissez abcd comme nom de sous-domaine.
   * Les utilisateurs verront ce sous-domaine comme faisant partie de l'URL du lien. Par exemple : `https://abcd.onelink.me/RPsv/37e5cd36`.
   * Le sous-domaine ne peut pas être modifié une fois que les liens personnalisés sont créés sur la base de ce template.
   * N'utilisez que des lettres minuscules, des chiffres ou des tirets (-).
   * OneLink prend également en charge les domaines de marque complète, ce qui peut vous aider à améliorer les performances des campagnes et à augmenter l'exposition de la marque. <Anchor target="_blank" href="/marketers/fr/docs/brand-onelink-with-your-domain">En savoir plus</Anchor>
5. Sélectionnez votre app Android, iOS ou les deux.
6. Définissez où rediriger les utilisateurs **lorsque l'app n'est pas installée**.

   * Si vous avez sélectionné une app Android et une app iOS, le template est configuré par défaut pour envoyer les nouveaux utilisateurs de l'app vers le bon app store.
   * Si vous n'avez sélectionné qu'une seule app (Android ou iOS), le template sera configuré pour envoyer TOUS les utilisateurs (iOS et Android, nouveaux et existants) vers la destination unique qui a été définie.
   * Si vous sélectionnez une app Android qui n'est pas dans Google Play, vous devez saisir l'URL vers laquelle les utilisateurs Android seront redirigés.
   * [Facultatif] Si l'app se trouve dans différents stores en plus de Google Play : **redirection vers les app stores tiers**. Vérifiez que dans les autres stores, l'app a bien le même nom de package que l'app Android sélectionnée dans votre template OneLink.
   * [facultatif] **Changement d'URL**:  dans certains cas, vous pouvez décider de guider les nouveaux utilisateurs vers une expérience web mobile plutôt que sur l'app store directement (votre application n'est pas forcément listée dans le store). Pour implémenter cette solution, entrez cette URL dans le champ URL. **Remarque** : si vous voyez s'afficher une redirection vers un store tiers en plus d'une URL, la redirection par défaut se fera toujours vers l'app store tiers.
   * [Facultatif] Activez **Afficher les extraits d'app pour les utilisateurs avec Private Relay** (disponible sous iOS 14 et +). <Anchor target="_blank" href="/marketers/fr/docs/apple-app-clips-integration-guide">En savoir plus sur les extraits d'app</Anchor>.
7. Passez **Si l'app est installée**. Ce point est abordé dans le [guide suivant](/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users) .
8. [Facultatif] Modifiez la destination pour **Si vous cliquez sur le lien depuis un ordinateur.**  
   * Dans certains cas, votre lien peut être cliqué depuis un ordinateur de bureau, surtout s'il est envoyé par mail ou via un réseau social. Si vous pensez que votre lien sera beaucoup consulté sur ordinateur, vous pouvez envoyer les utilisateurs vers une page d'accueil, vers la page d'accueil du site, ou bien vers une page où ils pourront demander à recevoir un lien par SMS sur leur téléphone, au lieu de l'app store correspondant.
   * Par défaut, les utilisateurs d'ordinateur sont redirigés vers la page App store de vos apps ou vers la page de l'app Google Play si aucune app iOS n'est définie.
9. [Facultatif]  **Sélectionnez des apps provenant d'autres plateformes**  
    si vous disposez d'une version d'app dédiée pour ce qui suit :
   * **Windows Phone** : activez et sélectionnez l'app ou **changez d'URL**.
   * **iPad** : activez le curseur et sélectionnez l’application iPad.
   * **Amazon Kindle Fire** : activez la sélection et ajouter l'ASIN Amazon store ou l'URL de la page de l'app.
10. Cliquez sur **Sauvegarder le template OneLink** (mettez à jour le template OneLink pour les templates qui ont été modifiés).   
    Votre template OneLink est maintenant créé et peut être utilisé pour créer de nombreux liens cliquables différents (<Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Liens et expériences OneLink</Anchor>).

</Accordion>

<div id="add-redirection-logic-for-existing-app-users" />

<Accordion title="Ajouter une fonction de redirection pour les utilisateurs existants de l'app">

Les utilisateurs existants de l'app s'attendent généralement à être redirigés directement vers l'app, et non vers un app store ou une page web. Trois technologies sont disponibles pour ouvrir l'app directement après un clic :

* **Liens universels IOS** : fonctionnent avec iOS 9 et +, et offrent une expérience fluide et sécurisée lors de l'ouverture de votre app.
* **App Links Android** : fonctionne sous Android 6 et +, et permet une utilisation fluide et sécurisée lors de l'ouverture de votre app.  **Remarque** : un OS Samsung ne pourra pas ouvrir les applications en utilisant les App Links Android.
* **Schéma d'URI** :  
  * Solution de secours :
    * Android : le schéma d'URI est une solution de secours efficace lorsque les liens d'app Android ne parviennent pas à ouvrir l'app, soit parce qu'ils ne fonctionnent pas, soit parce qu'ils ne sont pas configurés.
    * iOS : solutions de secours limitées au cas où les liens universels ne parviennent pas à ouvrir l'app, soit parce qu'ils ne fonctionnent pas, soit parce qu'ils ne sont pas configurés. <Anchor target="_blank" href="/marketers/fr/docs/uri-scheme-fallback-for-ios">En savoir plus</Anchor>
  * Principale méthode d'ouverture des apps sur les appareils Samsung.
  * C'est une adresse qui une fois accédée ouvre votre app, si celle-ci est déjà installée. Ils sont identiques aux liens de site web, la différence étant qu'ils ouvrent une app au lieu d'un site.
  * Doit être identique pour iOS et Android.

Pour optimiser l'expérience utilisateur, la sécurité et la couverture des appareils, nous vous conseillons d'activer le maximum de technologies. Si vous activez toutes les technologies de liens, OneLink appliquera automatiquement la meilleure méthode pour chaque utilisateur.

**Pour ajouter une logique de redirection pour les utilisateurs d'app existants à votre template OneLink :**

1. Dans le tableau de bord AppsFlyer, allez dans **Experiences et deep linking** > **Gestion OneLink.**
2. Passez le curseur de la souris sur le template OneLink que vous souhaitez modifier, puis cliquez sur l’icône **Modifier** .
3. Faites défiler jusqu'à la section **Quand l'app est installée**.

   [![](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)
4. Suivez les instructions pour la configuration iOS, Android et de la solution de secours :  

   <Tabs>
   <Tab title="Liens universels iOS">

   Les liens universels ont le même format que les liens Web habituels (ex :https://yourbrand.onelink.me ou https://www.yourbrand.com) et nécessitent donc qu'un sous-domaine soit défini (explications dans le [guide précédent](/docs/create-a-onelink-template#procédures)). OneLink prend également en charge les <Anchor target="_blank" href="/marketers/fr/docs/brand-onelink-with-your-domain">domaines qui ne sont qu'une marque</Anchor>, mais nous ne l'évoquerons pas dans ce guide.

   **Pour lancer l'app en utilisant des liens universels** :

   1. Contactez votre développeur iOS :
      * Indiquez-lui le sous-domaine pour ce template OneLink.
      * Demandez-lui de suivre <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">ces instructions</Anchor>.
      * Le développeur vous renvoie l'ID d'équipe (également appelé préfixe d'ID d'app Apple, par exemple, PF23MIWNTW).
      * Si l'app n'est pas encore publiée, le développeur doit également vous donner l'ID de groupe (par exemple, com.myapp.something).  

        [![](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)
   2. Dans la page du template OneLink, cliquez sur **Modifier pour lancer l'app en utilisant les liens universels**.
   3. Dans la nouvelle fenêtre, sélectionnez **Lancer l'app en utilisant les liens universels**.
   4. Dans le champ**ID d'équipe**, entrez l'identifiant d'équipe fourni par le développeur.
   5. Si l'app n'est pas publiée, entrez également l'**ID de groupe**.
   6. Cliquez sur **Enregistrer les modifications**.

   </Tab>

   <Tab title="Android App Links">

   Les App Links ont le même format que les liens Web habituels (ex : https://yourbrand.onelink.me ou https://www.yourbrand.com) et nécessitent donc qu'un sous-domaine soit défini (explications dans le [guide précédent](/docs/create-a-onelink-template#procédures)). OneLink prend également en charge les <Anchor target="_blank" href="/marketers/fr/docs/brand-onelink-with-your-domain">domaines qui ne sont qu'une marque</Anchor>, mais nous ne l'évoquerons pas dans ce guide.

   Avant de commencer :

   Enregistrez le sous-domaine que vous avez choisi pour ce template OneLink.

   **Pour lancer l'app en utilisant des Android App Links** :

   1. Contactez votre développeur Android :   
      dites-lui de générer un fingerprint SHA256 en suivant <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#generating-a-sha256-fingerprint">ces instructions</Anchor>.  
       Le développeur reviendra vers vous avec le fingerprint SHA256. For example: `DC:65:43:67:F3:BD:02:52:AC:B4:50:F1:74:54:23:49:4D:49:6C:E6:DF:56:BD:CB:53:06:11:5B:C9:4E:5D:0C`
   2. Dans la page du template OneLink, cliquez sur **Modifier pour lancer l'app en utilisant les App Links**.
   3. Dans la nouvelle fenêtre, sélectionnez **Lancer l'app en utilisant les App Links**.
   4. Dans le champ **fingerprint SHA256**, saisissez le fingerprint SHA256 fourni par le développeur.  
      Un code «intent-filter» généré automatiquement s'affiche.
   5. Contactez votre développeur Android :   
      donnez-lui le code intent-filter  
       généré automatiquement.  
      Dites-lui de suivre <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">ces instructions</Anchor> et demandez-lui de vous confirmer que tout est en ordre.

   </Tab>

   <Tab title="Schéma d'URI">

   Le schéma d'URI sert principalement de solution de secours pour les utilisateurs d'iOS et d'Android, et doit donc être le même pour les deux cas.

   **Pour définir l'URI de secours pour Android et iOS :**

   1. Contactez vos développeurs iOS ET Android et décidez d'un schéma d'URI. Par exemple : `applivrezmoi://`  

      > 👍
      >
      > * <span id="h_01H9Q4E7VR4CAK0PJY269GQ9XJ"></span>Ni Apple ni Google n'appliquent une dénomination spécifique pour les schémas d'app.**Choisissez un nom de schéma propre à votre marque**pour éviter les conflits entre les différentes applications. Un bon nom de schéma peut correspondre à l'ID de groupe de votre app, par exemple**com.company.app**
      > * Pour permettre à OneLink de répondre sur iOS autant qu'Android, il est important que **le même schéma soit défini pour les deux plates-formes**. Voici les instructions pour <Anchor target="_blank" href="https://help.contrast.co/hc/fr/articles/200865293-URL-Scheme-Intro-for-App-Developers">iOS</Anchor> et <Anchor target="_blank" href="https://developer.android.com/training/app-links/deep-linking.html">Android</Anchor>.
      > * Le schéma d'URI ne doit pas commencer par http ou https.

   2. Demandez au développeur iOS d'implémenter le schéma d'URI dans son app en <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-uri-scheme">suivant ces instructions</Anchor>.  
       **ET**  
      dites au développeur Android d'implémenter le schéma d'URI dans son app en <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#procedures-for-uri-scheme">suivant ces instructions</Anchor>.
   3. Une fois fait, le développeur doit vous confirmer la valeur du schéma d'URI implémenté. Il doit ressembler à : `exampleapp://` ou `exampleapp://home` ou `exampleapp://main`, etc.
   4. Dans la page du template OneLink, cliquez sur **Ajouter un schéma d'URI pour lancer l'app**.
   5. Sélectionnez **Lancer l'app en utilisant le schéma d'URI**.
   6. Entrez la valeur du schéma d'URI.
   7. Cliquez sur **Enregistrer les modifications**.
   8. Testez le schéma d'URI (peut être effectué par vous OU par vos développeurs) :
      1. Accédez à <Anchor target="_blank" href="https://halgatewood.com/deeplink/">cet outil de test public gratuit</Anchor> et utilisez-le à la fois sur un appareil iOS et sur un appareil Android sur lequel votre app est installée.
      2. Activez le lien généré par l'outil.  
          Si l'app s'ouvre c'est que le schéma d'URI est correct.

   </Tab>
   </Tabs>

5. Cliquez sur **Mettre à jour le template OneLink**.

> 📘 **Note**
>
> * Lorsque vous enregistrez ou mettez à jour votre template OneLink, AppsFlyer génère automatiquement le fichier AASA et/ou Digital Asset Links JSON pour vérifier le domaine de votre app, et l'héberge pour vous. Cette opération est essentielle au bon fonctionnement de vos liens universels et liens d'application.
> * Les mises à jour des templates OneLink peuvent prendre jusqu'à une heure.

</Accordion>

<div id="customize-qr-codes" />

<Accordion title="Personnalisez les QR codes">

![OnelinkQRFinal__1_.gif](https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif)

Les QR codes générés par OneLink peuvent être customisés des manières suivantes :

* Ajout de votre logo QR code
* Modification de la couleur du QR code.

**Remarque** : la personnalisation du QR code se fait au niveau du template, et non au niveau du lien individuel. Il en résulte que toute personnalisation affectera l'ensemble des QR codes en fonction du template modifié.

**Pour personnaliser votre QR code** :

1. Dans le tableau de bord AppsFlyer, allez dans **Expériences et deep linking** > **Liens personnalisés OneLink**.
2. Survolez l'icône **Actions** du template que vous souhaitez modifier, puis cliquez sur **Personnaliser le QR code**.L'éditeur de QR code s'ouvre.
3. Enter the URL where your logo is hosted. For example: https://yourbrand.com/logo.png.  

   Exigences relatives au logo :

   * Format PNG ou JPG
   * Carré ou rond avec fond transparent
   * Dimensions minimales 400 x 400 px
   * Pour l'impression, utilisez la résolution maximale de l'image
4. Définissez la couleur du QR code.
5. Cliquez sur ***Enregistrer***.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Remarques |
| --- | --- |
| Agences | <ul><li>Les agences ne peuvent pas créer de templates OneLink.</li><li>Une agence peut utiliser les templates OneLink existants pour créer des liens d'attribution personnalisés pour elle-même **si elle est partenaire de toutes les apps du template**.</li></ul> |
| Ajouter / modifier les templates OneLink | Les utilisateurs du compte doivent disposer de <Anchor target="_blank" href="/marketers/fr/docs/user-management">l'autorisation</Anchor> pour ajouter et modifier les templates OneLink. |
| Templates OneLink | Jusqu'à 600 templates OneLink autorisés par compte. |
| Ordinateur | Lorsque vous définissez l'URL ou le template OneLink pour rediriger les utilisateurs d'ordinateur vers une autre URL, l'URL web est ajoutée au lien dans le paramètre `af_web_dp`. Si le lien contient `af_web_dp`, AppsFlyer n'enregistre pas le clic s'il provient d'un ordinateur de bureau. |
| Rediriger vers les app stores tiers | Plusieurs app stores peuvent être définis sur le template OneLink à la condition que le nom du package d'app soit identique pour tous les app stores.<br /><br />**Remarque** :<ul><li>Huawei utilise des noms de package différents, un même template OneLink ne peut donc pas être utilisé pour plusieurs app stores.</li><li>Si le nom du package est le même mais que le canal est différent, la redirection fonctionnera mais pas l'attribution.</li><li><Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution">En savoir plus</Anchor> sur l’attribution et les données des App Stores tiers.</li></ul> |
| Mettre à jour un template | Il faut environ une heure pour que les modifications apportées à la configuration d'un template OneLink s'appliquent. |

</Accordion>

Vous avez une question sur les templates OneLink ? Consultez notre <Anchor target="_blank" href="/marketers/fr/docs/onelink-troubleshooting-and-faq#faq-sur-les-templates-onelink">FAQ</Anchor> !

## Prochaine étape

Suivez les instructions pour <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">créer des liens OneLink</Anchor> basés sur votre template.

<div data-zendesk-anchors="onelink-templates=templates-onelink h_01H9Q4E7VQ0GKZ9HFF88190TYN=templates-onelink procedures=proc%C3%A9dures h_01H9Q4E7VQYGZ1MH5SS3ZYZF1K=proc%C3%A9dures h_01H9Q4E7VQ648CQ1VJTB1TC571=create-a-onelink-template-with-redirection-logic-for-new-app-users h_01H9Q4E7VQ15AAR1VXNKWR1XGT=note h_01H9Q4E7VQ4NEWYAD6AMR9YKGY=add-redirection-logic-for-existing-app-users h_01H9Q4E7VR8164HR6MD0EAV2SN=note-1 h_01H9Q4E7VR0F4B7CTF08YTG715=customize-qr-codes h_01H9Q4E7VR2B50EQE31DDG8GNZ=traits-and-limitations next-step=prochaine-%C3%A9tape h_01H9Q4E7VRJK31P9CSGJFCKQQF=prochaine-%C3%A9tape" />
