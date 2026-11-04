---
title: Liens et expériences OneLink
metadata:
  keywords:
    - Marketers
    - onelink
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2016-05-22T10:03:37Z'
  edited_at: '2023-11-24T14:22:32Z'
  id: 208874366
  locale: fr
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/fr/articles/208874366
---
> **En bref :** [créez des liens OneLink](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink) pour offrir une expérience dédiée à vos utilisateurs. Les utilisateurs qui cliquent sur le lien sont redirigés vers l'App Store, l'URL web ou l'app de votre choix. Et les utilisateurs sont attribués à la source média qui correspond.

<div id="onelink-links-and-experiences" />

## Liens et expériences OneLink

<Embed title="Lecteur vidéo YouTube" typeOfEmbed="youtube" url="https://www.youtube.com/embed/KZBrxGEjVUE" providerUrl="https://www.youtube.com" />

Vos clients interagissent avec votre marque via différents points de contact, tant en ligne que hors ligne. Peu importe d’où viennent vos utilisateurs, vous pouvez créer un lien qui leur offre l’expérience parfaite, du clic à l’installation de l’app, en passant par le deep linking et le deep linking différé.

Les étapes nécessaires à la configuration d'un lien sont détaillées dans la section qui suit, mais globalement, elles comprennent les éléments suivants :

* Sélection d'une expérience utilisateur
* Paramètres généraux
* Paramètres de l’expérience dédiée
* Paramètres de deep linking et de redirection
* Paramètres supplémentaires

<div id="create-a-onelink-link" />

## Créer un lien OneLink

| **Personnes concernées**<ul><li>Un marketeur suffit pour créer des liens OneLink qui redirigent les utilisateurs vers les app stores, l’URL web ou, une fois le template configuré pour ouvrir l'app avec Android App Links et iOS Universal Links, vers la page d'accueil de l'app.</li><li>Pour ajouter des fonctionnalités de deep linking et de deep linking différé aux liens, un marketeur et un développeur Android / iOS sont requis.</li></ul> |
| --- |
| **Conditions préalables**<ul><li>Un compte AppsFlyer avec au moins une app.</li><li>Un <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">template OneLink</Anchor> sur lequel baser vos liens.</li><li>Pour l'attribution : le <Anchor target="_blank" href="/marketers/fr/docs/integrate-the-appsflyer-sdk">SDK AppsFlyer doit déjà être installé</Anchor> dans chacune de vos apps mobile.<ul><li>Si le SDK n'est pas encore installé dans vos apps, il est toujours possible de créer un lien de redirection fonctionnel, mais vous ne pourrez pas mesurer les installations dans votre tableau de bord, deep link ou deep link différé.</li></ul></li></ul> |
| **Durée**<br /><br />30 minutes pour la plupart des liens, mais environ 3 heures pour les liens qui nécessitent une fonctionnalité de deep linking ou de deep linking différé. |
| **Résultat**<ul><li>Un lien qui renvoie les utilisateurs vers l'app Store, la page web ou l'app appropriée en fonction de leur appareil, et qui leur donne l'expérience que vous souhaitez qu'ils traversent.</li></ul> |

**Pour créer un lien OneLink avec une expérience utilisateur dédiée :**

1. Dans le tableau de bord AppsFlyer, allez dans **Experiences et deep linking** > **Gestion OneLink.**
2. Sélectionnez le **template OneLink** où le lien personnalisé doit être ajouté.
3. Cliquez sur **Ajouter un lien**.
4. Sélectionnez [l’expérience](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#experiences) que vous souhaitez créer pour vos utilisateurs.
5. Sélectionnez une source média ou saisissez une source média personnalisée. Cela détermine la source média dans laquelle les données s’affichent chez AppsFlyer. La source média est incluse dans votre lien en tant que valeur de paramètre `pid`.
6. Cliquez sur **Suivant**.
7. Complétez les [**Paramètres généraux**](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings).
8. Cliquez sur **Suivant**.
9. [Facultatif] Suivez les procédures pertinentes pour l’expérience utilisateur que vous créez : 

| Expérience | Options de mise en œuvre |
| --- | --- |
| <ul><li>Social-to-app</li><li>Text-to-app</li><li>Referral-to-app</li><li>Lien personnalisé</li></ul> | <ul><li>[Aperçus des réseaux sociaux](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[Page d'accueil des apps sociales](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li></ul> |
| Email-to-app | Si vous utilisez un ESP, suivez les <Anchor target="_blank" href="/marketers/fr/docs/email-service-provider-esp-integration-guide">instructions d’intégration ESP</Anchor>. |
| App-to-app | Vous pouvez créer des liens dynamiques qui fonctionnent sur plusieurs apps via la <Anchor target="_blank" href="/marketers/fr/docs/cross-promotion-attribution-for-marketers">cross-promotion</Anchor>. |
| Referral-to-app | <ul><li>[Aperçus des réseaux sociaux](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[Page d'accueil des apps sociales](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li><li>Vous pouvez créer dynamiquement des liens referral-to-app via le SDK de votre app en passant par <Anchor target="_blank" href="/marketers/fr/docs/user-invite-attribution">l'intégration des invitations d'utilisateurs</Anchor>.</li></ul> |

10. Cliquez sur **Suivant**.
11. [Facultatif] Dans **Deep linking et redirection**, finalisez la [configuration du deep linking/ deferred deep linking.](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking) Ignorez cette section si ce lien n’est pas destiné au deep linking.
12. [Facultatif] Dans **Deep linking et redirection**, modifiez les [paramètres de redirection.](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection) Ignorez cette section si les paramètres de redirection du template OneLink sont corrects.
13. Cliquez sur **Suivant**.
14. Dans **Paramètres supplémentaires**, [ajoutez des paramètres prédéfinis ou personnalisés](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#additional-parameters) à votre lien pour une analyse plus granulaire. <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">Pour en savoir plus sur les paramètres d'attribution</Anchor>
15. Cliquez sur **Générer un lien**.

<div id="experiences" />

<Accordion title="Expériences">

Vous pouvez créer des liens pour les expériences utilisateur suivantes :

* **Social-to-app** : engagez vos utilisateurs issus des réseaux sociaux et envoyez-les depuis les publications de réseaux sociaux vers votre app.
* **App-to-app** : envoyez des utilisateurs vers votre app via des publicités qu'ils voient s'afficher dans d'autres apps.
* **QR-to-app** : utilisez les QR codes pour baliser l'installation de votre app : les utilisateurs scannent un QR code à chaque moment clé de leur expérience hors ligne. Vous pouvez également mettre des QR codes sur votre site desktop ou sur des publicités TV et CTV afin de diriger les utilisateurs vers votre app.
* **Email-to-app** : utilisez des ESP (fournisseurs de services e-mail) pour engager les utilisateurs par e-mail puis les envoyer vers votre app depuis leur boîte de réception.
* **Text-to-app** : créez des liens pour vos campagnes SMS et e-mail et contactez les utilisateurs via SMS.
* **Referral-to-app** : créez des liens d'invitation qui permettent aux utilisateurs ou influenceurs d'inviter d'autres personnes sur votre app, ou de partager un contenu in-app en particulier (comme un article).
* **Lien personnalisé** : pour les parcours utilisateur qui ne correspondent pas à l’une des expériences mentionnées ci-dessus, vous pouvez créer un lien personnalisé OneLink. Ensuite, peu importe d’où viennent vos utilisateurs, que ce soit d'un ordinateur de bureau ou d'un mobile, en ligne ou hors ligne, de médias propres ou payants, vous pouvez facilement les envoyer au bon endroit.

</Accordion>

<div id="general-settings" />

<Accordion title="Paramètres généraux">

Les paramètres généraux sont une étape du processus de création de liens OneLink qui s’applique à toutes les expériences.

**Pour définir les paramètres généraux** :

1. [Facultatif] Modifiez le nom de la source média.
2. [Facultatif] Modifiez le nom de la campagne.
3. [Facultatif] Activez le **retargeting** si vous prévoyez d'utiliser ce lien pour cibler les utilisateurs existants.  

   Cela vous permet de connaître les réengagements effectués par les utilisateurs qui cliquent sur votre lien personnalisé.

   Les utilisateurs existants qui cliquent sur les liens qui ne sont pas des liens de retargeting (AU) lancent également l'app, et ils ont la même expérience utilisateur. Mais leurs réengagements sont enregistrés comme des sessions régulières, il est donc impossible de mesurer l'efficacité de la campagne média propre.

   **Important !** Pour que le retargeting fonctionne, vous devez également l'activer pour l’app.
4. [Facultatif] Activez **Ignorer les utilisateurs actifs pour le retargeting** et sélectionnez la fenêtre d’inactivité.  
   Le paramètre af\_inactivity\_window=[nombre de jours] est alors ajouté à votre lien, et tous les utilisateurs en activité sur la période sont ignorés dans le cadre du retargeting.
5. Définissez la fenêtre de réengagement pour déterminer la période suivant le réengagement, où les événements in-app de l'utilisateur sont attribués à la source média de retargeting.

   * Vous pouvez définir la valeur en jours (1-90), en heures (jusqu'à 23) ou même en valeur vie.
   * La fenêtre de réengagement est ajoutée au lien dans le paramètre af\_reengagement\_window.
6. [Facultatif] Dans la sous-section **Marque du lien** :
   * Sélectionnez un autre domaine pour refléter votre marque. <Anchor target="_blank" href="/marketers/fr/docs/brand-onelink-with-your-domain">En savoir plus</Anchor>
   * Modifiez l'identifiant d'URL pour mettre en avant l'offre de la campagne. L'ID d'URL peut comporter au maximum 50 caractères et peut inclure des lettres et des chiffres. Par défaut, il comporte 8 caractères.

<div id="enable-retargeting-for-the-app" />

#### Activer le retargeting pour l’app

Si le retargeting n'a jamais été activé pour l'app, vous devez le faire une première fois. <Anchor target="_blank" href="/marketers/fr/docs/app-settings#paramètres-dattribution">En savoir plus</Anchor>

**Pour paramétrer le retargeting au niveau de l'app :**

1. Dans le tableau de bord AppsFlyer, rendez-vous dans **Configuration** > **Paramètres d'app**.
2. Dans la  section **Attribution**, activez l'**attribution de réengagement**.
3. Cliquez sur **Enregistrer les paramètres**.

</Accordion>

<div id="social-media-preview-og-tags" />

<Accordion title="Aperçu des réseaux sociaux : balises OG">

Lorsqu'un lien est partagé, les balises Open Graph (OG) sont utilisées pour générer un aperçu avec un titre, une description et une image.

Ces balises OG peuvent être automatiquement reprises de l'URL web ou de l'app store vers lequel vous redirigez. Il arrive cependant que cette méthode de génération d'aperçu échoue. Par conséquent, nous vous recommandons de configurer vos aperçus de réseaux sociaux dans OneLink, soit en utilisant l'interface utilisateur OneLink, soit, pour les liens non créés dans l'interface utilisateur OneLink, en ajoutant des paramètres de balise OG à votre lien.

La fonction d'aperçu des réseaux sociaux est prise en charge par les plateformes suivantes :

* Facebook : posts et messages directs
* X (anciennement Twitter) : posts et messages directs
* iMessage
* WhatsApp
* LinkedIn : posts et messages directs
* Line
* Telegram
* Slack
* Signal
* KakaoTalk
* Discord
* Reddit

**Pour créer votre propre aperçu des réseaux sociaux dans l'interface utilisateur de OneLink :**

1. Dans votre éditeur de lien personnalisé OneLink, accédez à la section **Partager sur les réseaux sociaux**.
2. Dans la section **Aperçu des réseaux sociaux** entrez les éléments suivants :
   * Titre
   * Description
   * URL de l'image

**Pour ajouter les paramètres des balises OG à votre lien** (s'il n'a pas été créé dans l'interface utilisateur de OneLink) :

* Ajoutez les paramètres suivants :
  * af\_og\_title (40 caractères max.)
  * af\_og\_description (jusqu’à 300 caractères)
  * af\_og\_image

**Remarque :** 

* Vous pouvez ajouter les paramètres de la balise OG à votre lien en dehors de l'interface utilisateur d'AppsFlyer.
* Si vous ajoutez des balises OG distinctes pour X (anciennement Twitter), elles remplaceront l'aperçu AppsFlyer habituel.

</Accordion>

<div id="social-app-landing-page" />

<Accordion title="Page d'accueil des apps sociales">

<div id="important-1" />

> 🚧 **Important !**
>
> Les liens universels iOS sont désormais pris en charge dans Meta ads.
>
> * Comme Meta prend maintenant en charge les liens universels , la page d'accueil sociale pour les Meta ads payantes qui prennent en charge les liens universels n'est plus requise.
> * Une page d'accueil sociale est nécessaire pour les posts propriétaires (publicités non payantes).

Les apps de réseaux sociaux peuvent perturber l'expérience des utilisateurs qui utilisent les liens universels. Pour résoudre ce problème :

* [**Recommandé**] Créez une page d'accueil pour les apps de réseaux sociaux.  
  Lors de la création de la page d'accueil d'une app de réseaux sociaux, nous vous recommandons de vous assurer que vous avez configuré un schéma d'URI.
* [Autre solution] <Anchor target="_blank" href="/marketers/fr/docs/onelink-troubleshooting-and-faq#deep-linking-forcé">Forcez l'ouverture de l'app</Anchor> en utilisant le paramètre `af_force_deeplink=true`.   
  **Remarque** : ce paramètre est activé automatiquement pour Kakaotalk, Naver, Naver-Blog, Chrome, Weibo et X (anciennement Twitter).

En utilisant la page d'accueil d'une app sociale, les utilisateurs qui cliquent sur des publicités dans des apps de réseaux sociaux sont ensuite redirigés vers une page d'accueil générée par AppsFlyer. De là, ils peuvent être deep linkés, ou continuer à installer l'app.

AppsFlyer fournit une variété de templates de page d'accueil d'app de réseaux sociaux. La position des éléments dans les templates est fixe, mais les éléments en eux-mêmes sont personnalisables, y compris l'image ou la couleur d'arrière-plan, les titres, les textes, les images, les boutons, les balises, etc.

La page d'accueil de l'app de réseaux sociaux peut être utilisée avec les apps de réseaux sociaux suivantes :

* Instagram
* Facebook/Facebook Messenger (**Remarque** : pour Facebook et Facebook Messenger, si à la fois un schéma d'URI et une page d'accueil d'app sociale sont configurés, alors la page d'accueil de l'app sociale ne s'affiche pas.)
* LinkedIn
* Pinterest pour iOS
* Snapchat
* X (anciennement Twitter)
* WeChat

**Expérience utilisateur**

Lorsque l'utilisateur interagit avec le bouton CTA sur la page de d'accueil :

* **Si l'app est installée** : l'utilisateur clique sur l'app pour la lancer.
* **Si l'app n'est PAS installée** : l'utilisateur est dirigé vers l'app store concerné. Lors de l'installation, il est possible de différer le deep linking de l'utilisateur (cf explications dans [Deep linking et deep linking différé](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)).

<div id="note-2" />

> 📘 **Note**
>
> La page d'accueil de l'app sociale prend uniquement en charge l'URL courte OneLink.

<div id="to-use-the-social-app-landing-page" />

#### **Pour configurer une page d'accueil d'app sociale :**

1. Configurez la page d'accueil comme décrit dans la section suivante.
2. Enregistrez l'URL OneLink **courte** qui a été générée.  
   La page d'accueil des app de réseaux sociaux ne fonctionne pas avec les URL OneLink longues.
3. Publiez l'URL courte OneLink sur l'app sociale.

L'attribution est déterminée en fonction de vos  paramètres d'attribution.

<div id="to-set-up-the-social-apps-landing-page" />

#### **Pour configurer la page d'accueil des apps sociales :**

1. Dans la configuration de votre lien personnalisé, ouvrez la section **Partager sur les réseaux sociaux**.
2. Dans la section **Page d'accueil de l’app sociale**, cliquez sur **Créer une page d'accueil**.  
   Une fenêtre permettant de choisir un template de page d'accueil s'ouvre.  

   [![](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)
3. Pour choisir un template de page d'accueil, passez la souris sur le template sélectionné et cliquez sur **Créer**.  

   **Astuce** : survolez l'icône 🛈d'un template pour voir dans quels cas il doit être utilisé. L'utilisation de Clustered Poster et de ShowAndTell est recommandée pour Instagram.
4. Personnalisez tous les éléments de la page d'accueil. Pour ce faire, sélectionnez les éléments d'après leur nom ou cliquez dessus dans l'image d'aperçu.  
    **Conseil** : enregistrez vos textes au cas où vous remplaceriez le template de création.
5. Remplacez toutes les images du template par vos propres images.  
   1. Enter image URLs including the extension, for example, `https://example.com/image.png`.
   2. Utilisez l'un des types de fichier suivants : jpeg, jpg, png.   
      **Remarque** : le format webp n'est pas pris en charge.
   3. Les recommandations pour les images sont les suivantes :  

| Type d'image de template | Taille maximale du fichier image | Ratio de l'image |
| --- | --- | --- |
| Collection | 300 Ko | 16:9 (horizontal) |
| <ul><li>Trapèze</li><li>Carrousel</li><li>ShowAndTell</li></ul> | 300 Ko | 1:1 |
| <ul><li>Flyer</li><li>Affiche</li><li>Affiche floutée</li><li>Affiche groupée</li></ul> | 300 Ko | 9:16 (vertical) |

   4. Si une ou plusieurs images n'ont pas une URL exacte, une erreur s'affiche et vous ne pouvez pas consulter la création.   

      [![](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)
6. Pour modifier la création de la page d'accueil, cliquez sur **Corriger**.  
   Si des modifications sont nécessaires, cliquez sur **Retour à l'éditeur**.  

   [![](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)
7. Pour enregistrer votre page d'accueil, cliquez sur  **Terminé**.  
   **Important** : les créations de page d'accueil qui sont soit nouvelles soit mises à jour ne s'afficheront qu'après avoir généré/mis à jour le lien personnalisé.
8. [Facultatif] Pour modifier votre page d'accueil, cliquez sur **Modifier la page d'accueil de l’app sociale**.

</Accordion>

<div id="deep-linking-and-deferred-deep-linking" />

<Accordion title="Deep Liinking et deep linking différé">

Le deep linking permet de recibler vos utilisateurs existants pour les envoyer directement vers une expérience définie au sein de l'app (ex : une page spécifique), et ce sans avoir à les diriger en premier lieu vers l'app store ou la page d'accueil de l'app. Ces utilisateurs seront attribués par attribution de retargeting.

Le deferred deep linking permet d'offrir aux nouveaux utilisateurs une expérience de deep linking similaire à celle des utilisateurs existants. Ils sont d'abord dirigés vers l'app store, puis, après avoir téléchargé et lancé l'app, ils sont dirigés vers une expérience ou une page spécifique.

**Remarque :** la configuration du deep linking et du deep linking différé nécessite l'intervention de développeurs Android et iOS.

**Pour configurer le deep linking et le deferred deep linking pour diriger les utilisateurs vers une expérience spécifique dans l’app :**

1. Contactez vos développeurs iOS et Android pour que le **deep\_link\_value**soit à terme défini sur vos liens.
   * **deep\_link\_value** est le nom de la valeur qui indique vers quel contenu de l'app les utilisateurs seront dirigés. Les développeurs implémentent dans le code le comportement attendu de **deep\_link\_value**.
   * Les développeurs implémentent le comportement souhaité dans le code. Le guide permettra aux développeurs de bien comprendre l'aspect technique et de consulter des exemples :
     * [Pour le deep linking ET le deep linking différé](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl) des utilisateurs nouveaux ou existants, avec ou sans votre app.**Considérations relatives au deep linking unifié :**
       * Nécessite le SDK V6.1 ou +.
       * La fenêtre rétrospective de clic peut durer jusqu'à 15 minutes.
     * **Remarque** : les clients qui utilisent déjà OneLink pour le deep linking peuvent utiliser les anciennes méthodes pour <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_gcd_legacy">Android</Anchor> et <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_gcd_legacy">iOS</Anchor> au lieu du DLU.  

       <div id="tips" />

       > 👍 **Conseils**
       >
       > La valeur **deep \_link\_value** peut être basée sur un SKU de produit, un ID de post sur les réseaux sociaux, un chemin d'URL, ou autre valeur.
       >
       > Collaborer avec vos développeurs est capital pour trouver la meilleure utilisation à long terme du  **deep\_link\_value** et de tout autre paramètre ou valeur. Vous réduirez ainsi le nombre de mises à jour nécessaires pour l'application. Proposez à votre développeur d'utiliser les valeurs dynamiques pour générer des deep links dirigés vers différentes parties de l'application, **ce qui évitera d'avoir à modifier le code de l'app à chaque fois.**
       >
       > Exemple : la valeur **deep link\_value** d'une espèce de fruit a été choisie, et les développeurs ont transformé les valeurs en valeurs dynamiques. Vous pouvez alors saisir le nom de n'importe quel fruit sans que votre équipe de développement n'ait à faire quoi que ce soit.
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=apples...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=bananas...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=peaches...`

2. Après avoir reçu la confirmation des développeurs que l'app se comporte selon les paramètres et valeurs sélectionnés, dans la section **Deep linking et redirection** de la page de configuration du lien, saisissez la **valeur du deep link** en fonction de ce que vous avez décidé avec les développeurs.
3. [Optionnel] Si votre deep linking engage plus d'une opération in-app (ex : vous souhaitez diriger les utilisateurs vers un produit ET leur offrir une réduction en parallèle), vous pouvez ajouter une **valeur supplémentaire de deep link (via le paramètre deep\_link\_sub1)** à la charge utile des données de deep linking. Des paramètres de deep linking supplémentaires (deep\_link\_sub2-10) peuvent être ajoutés dans la section **Paramètres supplémentaires**.
   1. Contactez vos développeurs iOS et Android pour planifier les valeurs.
   2. Les développeurs implémentent le comportement souhaité au sein du code.Transmettez ce guide aux développeurs pour les aider à comprendre la marche à suivre et leur donner des exemples pratiques.

      <Tabs>
      <Tab title="Android">

      [Instructions pour les développeurs sur OneLink](https://dev.appsflyer.com/hc/docs/dl_android_overview)

      </Tab>

      <Tab title="iOS">

      [Instructions pour les développeurs sur OneLink](https://dev.appsflyer.com/hc/docs/dl_ios_overview)

      </Tab>

      <Tab title="Unity">

      [Instructions pour les développeurs sur OneLink](https://dev.appsflyer.com/hc/docs/deeplinkintegrate)

      </Tab>
      </Tabs>

   3. Dans la section **Paramètres supplémentaires**, ajoutez des paramètres personnalisés **deep\_link\_sub2-10** et des valeurs selon les besoins, en fonction de ce que vous avez décidé avec les développeurs.

<div id="note-4" />

> 📘 **Note**
>
> Une fois que les paramètres et les valeurs dynamiques sont mis en œuvre par les développeurs, le marketeur peut utiliser l'API OneLink pour générer automatiquement des milliers de liens personnalisés. <Anchor target="_blank" href="/marketers/fr/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">En savoir plus</Anchor>

</Accordion>

<div id="redirection" />

<Accordion title="Redirection">

**Pour envoyer de nouveaux utilisateurs vers** **une page d'accueil, plutôt que sur l'App Store** :

1. Dans la section **Deep linking et redirection** de la page de configuration du lien, dans «Si l’app n’est pas installée», sélectionnez l'option pour envoyer les utilisateurs vers une url différente.  
   Les URL Android et iOS personnalisées redirigent les nouveaux utilisateurs vers la page d'accueil que vous avez définie.**Important !** Si votre template OneLink possède déjà une valeur définie sur une URL personnalisée, ces URL de lien personnalisées la remplacent.
2. Vous pouvez également envoyer les nouveaux utilisateurs vers <Anchor target="_blank" href="/marketers/fr/docs/redirect-users-to-custom-app-store-product-pages">des pages produits personnalisées du store</Anchor>.

</Accordion>

<div id="additional-parameters" />

<Accordion title="Paramètres supplémentaires">

Vous pouvez ajouter des paramètres supplémentaires à votre lien, comme la campagne, le nom de l'adset, le nom de la publicité, la chaîne, vos propres paramètres personnalisés ou 1 à 5 <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">paramètres d'abonné</Anchor>. Vous aurez ainsi accès à une analyse plus poussée de vos actions marketing. En savoir plus sur les <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">paramètres d'attribution supplémentaires</Anchor>.

Vous pouvez également ajouter des paramètres de deep linking supplémentaires (deep\_link\_sub2-10).

**Pour ajouter des paramètres** :

1. Dans la section **Paramètres supplémentaires** de la configuration du lien, cliquez sur **Ajouter un paramètre**.
2. Sélectionnez un paramètre à ajouter ou entrez un paramètre personnalisé.

</Accordion>

<div id="testing" />

<Accordion title="Test">

Vous pouvez vérifier si votre lien fonctionne pour rediriger :

* Les nouveaux utilisateurs qui n'ont pas installé votre app
* Les utilisateurs existants qui ont déjà installé votre app

<div id="new-users-without-your-app-installed" />

#### Les nouveaux utilisateurs qui n'ont pas installé votre app

**Condition préalable** : un <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">appareil de test enregistré</Anchor> où l'app n'a pas été installée.

**Pour tester votre lien :**

1. Dans le tableau de bord AppsFlyer, allez dans **Experiences et deep linking** > **Liens personnalisés OneLink**.
2. Survolez l'icône **Actions** du lien que vous souhaitez tester et cliquez sur  **Obtenir l'URL**.
3. Envoyez l'URL courte ou longue sur votre téléphone. Vous pouvez soit :
   * Scanner le code QR avec la caméra de votre téléphone ou bien l'app QR scanner.
   * Envoyez-vous le lien par e-mail ou par WhatsApp, et ouvrez-le sur votre téléphone  
     .**Important :** ne le collez pas dans un journal iOS, ni directement dans un navigateur mobile. La plupart du temps le système d'exploitation mobile refusera d'ouvrir l'app dans ce cas.
4. Cliquez sur le lien de votre appareil mobile.  
   Selon votre plateforme, il devrait vous diriger sur l'app store ou la page d'accueil.  
   **Remarque :** un clic réel sur un appareil mobile est obligatoire. Les redirections Javascript ou 301/302 ne peuvent pas déclencher les liens universels et les liens d'app Android. Avec ces méthodes, même les redirections de base échouent sur certains navigateurs.
5. Téléchargez et lancez l'app.
   * L'app devrait s'ouvrir sur son écran d'accueil.
   * Si vous avez implémenté le deferred deep linking, l’app doit s’ouvrir au contenu que vous avez spécifié dans les paramètres de lien.
6. Repérez la nouvelle installation dans le **tableau de bord général AppsFlyer** .  
   Dans la source média, recherchez le nouveau clic et la nouvelle installation (ex : test) ainsi que le nom de la campagne que vous avez mis dans l'URL.

Le lien ne fonctionne pas comme prévu ? Consultez la <Anchor target="_blank" href="/marketers/fr/docs/onelink-troubleshooting-and-faq">FAQ et le guide de dépannage OneLink.</Anchor>

<div id="existing-users-with-your-app-installed" />

#### Les utilisateurs existants qui ont déjà installé votre app

**Pré-requis :** un appareil Android et/ou iOS avec l'app installée. Vérifiez qu'il s'agit bien de l'app d'origine (et la version) à laquelle le ou les développeurs ont apporté des modifications (et ont implémenté des liens universels, des liens d'apps et/ou des schémas d'URI).

**Pour tester votre lien :**

1. Dans le tableau de bord AppsFlyer, allez dans **Experiences et deep linking** > **OneLink**.
2. Cliquez sur le **template OneLink sélectionné**.
3. Dans la liste, choisissez le lien personnalisé.
4. Survolez l'icône **Actions** du lien que vous souhaitez tester et cliquez sur  **Obtenir l'URL**.
5. Envoyez l'URL courte ou longue sur votre téléphone. Vous pouvez soit :
   * Scanner le code QR avec la caméra de votre téléphone ou bien l'app QR scanner.
   * Envoyez-vous le lien par e-mail ou par WhatsApp, et ouvrez-le sur votre téléphone  
     .**Important :** ne le collez pas dans un journal iOS, ni directement dans un navigateur mobile. La plupart du temps le système d'exploitation mobile refusera d'ouvrir l'app dans ce cas.
6. Cliquez sur le lien de votre appareil mobile.
   * L'app devrait s'ouvrir sur son écran d'accueil.
   * Si vous avez implémenté le deep linking, l’app doit s’ouvrir sur le contenu que vous avez spécifié dans les paramètres de lien.
7. Cliquez sur le tableau de bord de **Retargeting** .  
   Repérez le nouveau clic ou réengagement (ouverture de l'app) sous la source média de votre lien (ex : test) ainsi que le nom de campagne que vous avez inclus dans l'URL.

Le lien ne fonctionne pas comme prévu ? Consultez la <Anchor target="_blank" href="/marketers/fr/docs/onelink-troubleshooting-and-faq">FAQ et le guide de dépannage OneLink.</Anchor>

</Accordion>

<div id="additional-procedures" />

## Procédures supplémentaires

<div id="create-a-custom-impression-url" />

<Accordion title="Créer une URL d'impression personnalisée">

Les liens d'impression personnalisés vous permettent de :

* Mesurez les <Anchor target="_blank" href="/marketers/fr/docs/about-conversion-rates#les-étapes-du-tunnel-marketing-et-les-taux-de-conversion-1">taux de conversion des impressions en clic</Anchor> des publicités que vous affichez.
* Recevoir l'attribution des impressions.

**Pré-requis :** une URL longue de lien personnalisé Onelink fonctionnel. Les URL courtes ne sont pas prises en charge.

**Personnes concernées :**

Marketeur et développeur web

**Pour créer des URL d'impression à des fins de mesure uniquement :**

1. Dans le tableau de bord AppsFlyer, allez dans **Expériences et deep linking** > **Liens personnalisés OneLink**.
2. Survolez l'icône **Actions** du lien que vous souhaitez tester et cliquez sur **Obtenir l'URL**.
3. Copiez l'URL longue du OneLink à modifier.   
   Exemple :  `https://subdomain.onelink.me/j7rN?pid=email&c=Spring`
4. Remplacez le sous-domaine (ou l'ensemble du domaine de marque, si vous en utilisez un) par « impressions ».    
   Exemple : `https://subdomain.onelink.me/j7rN?pid=email&c=Spring`
5. Copiez l'URL d'impression et envoyez-la à votre développeur.
6. Demandez à votre développeur Web d'implémenter l'URL d'impression dans la logique du site Web.

Vous disposez maintenant d'une URL d'impression qui peut être utilisée pour compter les impressions sur les pages de votre site, **mais ne peut pas attribuer de nouvelles installations**.Pour l'attribution post vue, suivez les étapes suivantes.

**Pour utiliser des URL d'impression pour l'attribution :**

1. Préparez l'URL d'impression comme décrit dans les étapes précédentes.
2. Assurez-vous que <Anchor target="_blank" href="/marketers/fr/docs/measure-view-through-engagements">l'attribution post vue est activée</Anchor>.
3. [Facultatif] Si vous souhaitez modifier la valeur de la <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">fenêtre rétrospective</Anchor> (qui est de 1 jour par défaut), ajoutez le paramètre `af_viewthrough_lookback` à la nouvelle valeur. Exemple : `af_viewthrough_lookback=1d`.
4. Copiez l'URL d'impression et envoyez-la à votre développeur.
5. Demandez à votre développeur web d'implémenter l'URL d'impression dans la logique du site web.

Exemple d'URL d'impression complète :

```http
https://impressions.onelink.me/j7rN?pid=email&c=Spring&af_viewthrough_lookback=1d
```

</Accordion>

<div id="deep-linking-post-event" />

<Accordion title="Deep linker après l'événement">

Il peut parfois être utile de deep linker les utilisateurs vers des activités ou pages spécifiques uniquement après un événement, exemple :

* Connexion
* Visualisation d'un écran de démarrage
* Consentement aux conditions d'utilisation
* Liste non exhaustive

**Pour établir deep linker les utilisateurs après un événement**:

Demandez à vos développeurs de suivre la procédure permettant de deep linker les utilisateurs après événement pour [Android](https://dev.appsflyer.com/hc/docs/dl_android_dl_post_event) et [iOS](https://dev.appsflyer.com/hc/docs/dl_ios_dl_post_event).

</Accordion>

<div id="deferred-deep-linking-with-ios-private-relay" />

<Accordion title="Deferred Deep Linking avec Private Relay iOS">

Avec le lancement d'IOS 15, Apple fournit aux utilisateurs iCloud+ une fonctionnalité appelée <Anchor target="_blank" href="https://www.macworld.com/article/348965/icloud-plus-private-relay-safari-vpn-ip-address-encryption-privacy.html">Private Relay</Anchor>, qui leur permet de chiffrer leur trafic de navigation web et de masquer leur emplacement exact, leur adresse IP et le contenu de leur trafic de navigation. Si les utilisateurs acceptent Private Relay, cela peut interférer avec l'attribution et le deep linking différé. En d'autres termes, lorsqu'un nouvel utilisateur se rend dans l'App Store et installe et lance l'app, Private Relay pourrait l'empêcher d'être envoyé vers une page spécifique de l'app.

Pour garantir le fonctionnement du deferred deep linking (DDL), vous devez mettre en œuvre l'une des solutions AppsFlyer suivantes :

* **[Recommandé] Solution basée sur App Clip** : créez un clip d'app qui vous donne des données d'attribution d'utilisateur et dirige les utilisateurs vers une expérience App Clip personnalisée similaire à celle que vous souhaitez obtenir avec le DDL. Le clip d'app peut également inclure un flux pour diriger les utilisateurs de votre clip vers votre app complète.
* **Solution basée sur le presse-papiers** : créez une page d'accueil web qui copie les données de deferred deep linking de l'URL et redirige l'utilisateur vers l'app. **Remarque** : cette solution ne facilite pas l'attribution.

<div id="app-clipbased-solution" />

<Accordion title="Solution basée sur App Clip">

Cette solution qui combine des URL courtes OneLink avec la technologie App Clip disponible sur iOS vous permet d'envoyer des utilisateurs vers des flux spécifiques de votre app sans avoir besoin d'une installation complète. L'URL courte OneLink vous fournit des données d'attribution des utilisateurs et dirige ces derniers vers une expérience App Clip personnalisée similaire à celle que vous vouliez offrir via le DDL. Le clip d'app peut également inclure un flux pour diriger les utilisateurs vers votre application complète. **Note** : si les utilisateurs réinstallent l'app complète à partir de la solution basée sur App Clip, cela peut être considéré comme une installation organique dans AppsFlyer.

<div id="flow" />

#### **Flux**

Le flux de la solution DDL basée sur App Clip est le suivant :

1. L'annonceur crée un clip d'app et l'ajoute à un modèle OneLink pour les utilisateurs dont la fonctionnalité Private Relay est activée.
2. L'utilisateur presse l'URL OneLink.
3. Le gestionnaire web AppsFlyer vérifie les points suivants :
   * L'appareil utilise iOS 15 et +
   * Le navigateur est Safari
   * La fonctionnalité Private Relay est activée pour l'utilisateur.
4. Une fois qu'AppsFlyer confirme ce qui précède, l'utilisateur est invité à cliquer soit sur **Lire le clip d'app** soit sur **Afficher dans Safari**.
   * Si l'utilisateur clique sur **Lire le clip d'app**, une carte App Clip s'affiche.
   * Si l'utilisateur clique sur Afficher dans Safari, une page d'accueil s'ouvre, l'invitant à ouvrir le clip d'app.
5. L'utilisateur ouvre le clip d'app.
6. Le clip d'app s'ouvre et fournit à l'utilisateur l'expérience définie par le marketer et le développeur de l'app.
7. Si le clip d'app inclut un flux pour diriger les utilisateurs vers l'app complète, ceux-ci sont envoyés sur l'App Store pour télécharger l'app. Au lancement de l'app, ils obtiennent l'expérience utilisateur définie par le développeur.

**Conditions préalables :** SDK AppsFlyer V6.4.0 et +

**Pour configurer la solution DDL basée sur App Clip** :

1. Demandez au développeur de suivre les instructions <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#app-clip-based-solution">du dev hub de la solution basée sur App Clip</Anchor> et de créer un clip d'app qui offre l'expérience utilisateur souhaitée. Ce dernier peut également inclure un flux pour diriger les utilisateurs de votre clip vers votre app complète.
2. Créez ou modifiez un <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">template OneLink</Anchor> avec des liens universels et du deferred deep linking.
3. Dans le template OneLink, activez **Afficher clip d'app si l'utilisateur dispose de Private Relay**. Activez cette option uniquement si vous disposez d'un clip d'app.  
   **Note** : lorsque vous apportez des modifications à un template OneLink avec des liens universels, par exemple si vous ajoutez (ou supprimez) la fonctionnalité App Clip, la mise à jour du fichier AASA peut prendre plusieurs heures. Les fonctionnalités des liens que vous créez en vous basant sur le template peuvent donc ne pas se mettre immédiatement à jour.
4. Créez un lien personnalisé basé sur le template OneLink.
5. Dans App Store Connect, ouvrez la section **App Clip Experience**, faites défiler vers le bas jusqu'à **URL de l'App** et entrez l'URL de votre template OneLink (domaine + ID du modèle, exemple  : `yourbrand.onelink.me/GrbZ`), ou une URL courte de lien personnalisé OneLink spécifique.  
    **Note** : si vous saisissez un lien personnalisé OneLink, la solution basée sur App Clip ne fonctionnera que pour les utilisateurs qui sélectionnent ce lien spécifique. Les autres liens créés à partir du template OneLink ne fonctionneront pas.

</Accordion>

<div id="clipboardbased-solution" />

<Accordion title="Solution basée sur le presse-papiers">

<div id="flow-1" />

#### **Flux**

Le flux de la solution DDL basée sur le presse-papier est le suivant :

1. L'annonceur crée un lien deferred deep link qui contient le paramètre `af_cp_lp=true`.
2. L'utilisateur presse ce lien.
3. AppsFlyer vérifie les points suivants :
   * L'appareil utilise iOS 15 et +
   * Le navigateur est Safari
   * La fonctionnalité Private Relay est activée pour l'utilisateur.
   * Si le lien contient le paramètre `af_cp_lp=true`.
4. Une fois qu'AppsFlyer a confirmé ce qui précède, la page d'accueil web se charge et affiche l'icône et l'image de l'app, ainsi qu'un appel à l'action pour obtenir l'app depuis l'App Store. L'utilisateur voit également un message qui explique le processus : l'URL est copiée pour assurer la meilleure expérience utilisateur qui l'enverra vers une page spécifique de l'app.  

   ![ios_15_ip_masking__1_.png](https://files.readme.io/c130314c98ebd42f50feaafd752c0cea954f42c5bfd99a6dbd94daf9e48c2ff4-30151216595345.png)
5. L'utilisateur presse **Get the app (Obtenir l'app)**.
6. L'utilisateur est envoyé sur l'App Store pour installer l'app. Ensuite, au premier lancement, il est envoyé vers la page spécifique de l'app.

<div id="requirements" />

#### **Exigences**

La solution DDL Copier/Coller la page d'accueil nécessite les points suivants :

* Navigateur Safari.
* Deferred deep link incluant le paramètre `af_cp_lp=true`.
* SDK AppsFlyer iOS V6 et +.
* Votre développeur iOS doit implémenter un code qui colle les données de deferred deep link dans l'URL à partir du presse-papiers. Il ne fait pas partie du SDK AppsFlyer.
* L'utilisateur final doit cocher la case (par défaut). Si elle n'est pas cochée, l'URL n'est pas copiée et le deferred deep linking ne fonctionne pas.

<div id="setup" />

#### **Configuration**

**Pour configurer la solution DDL basée sur le presse-papiers** :

1. Dites à votre développeur iOS de : 
   1. Suivre les instructions du <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#clipboard-based-solution">dev hub</Anchor> et intégrer le code requis dans le SDK AppsFlyer.
   2. Implémenter un code qui colle les données du deferred deep link dans l'URL du presse-papiers. Cela ne fait pas partie du SDK AppsFlyer.
2. Ajoutez le paramètre `af_cp_lp=true` à vos liens.   
   Vous pouvez ajouter un paramètre personnalisé dans l'interface utilisateur du lien personnalisé AppsFlyer OneLink, ou simplement ajouter le paramètre à n'importe lequel de vos liens.

</Accordion>

</Accordion>

<div id="additional-information" />

## Informations supplémentaires

<div id="examples" />

<Accordion title="Exemples">

**Exemple de base**

Mark est le spécialiste marketing d’un célèbre service de livraison de courses appelé « Feed Me ». Mark cible ses numéros de téléphone d’utilisateurs pour le téléchargement des nouvelles apps mobiles iOS et Android de Feed Me. Une campagne SMS est prévue. Mais Mark ne sait pas quels utilisateurs ont un appareil Android ou iOS. Il ne sait pas non plus si l'app est installée ou non.

Pour résoudre ce problème, Mark envoie un SMS contenant une URL courte via OneLink. Lorsque les utilisateurs reçoivent le SMS et cliquent sur le lien :

* S'ils n'ont pas encore l'app, ils sont automatiquement dirigés vers l'app Store ou la page d'accueil appropriée. À partir de là, ils peuvent installer l'app facilement.
* S'ils ont déjà installé l'app, celle-ci s'ouvre directement.

Ces nouvelles installations sont attribuées à la campagne SMS, ce qui permet à Mark de vérifier l'efficacité de la campagne SMS dans AppsFlyer. 

**Exemple de deep linking**

Le SMS de Mark le marketeur (cf exemple précédent) a eu un léger succès pour amener les utilisateurs à télécharger et à ouvrir l’app. Cependant, peu d'utilisateurs ont cliqué sur le lien, ouvert l'app et passé une commande.

Mark décide d'augmenter la conversion en offrant un sachet gratuit de pêches, de pommes ou d'avocats avec chaque achat. Pour cela, Mark crée une expérience fluide de deep linking pour les utilisateurs existants. Il envoie à sa base d'utilisateurs un e-mail détaillé soulignant les bienfaits de ces 3 fruits sains. 

Pour chaque fruit mentionné dans l'e-mail, Mark inclut un deep link porté par OneLink, et configuré (avec l'aide de développeurs mobile) pour :

Pour résoudre ce problème, Mark envoie un SMS contenant une URL courte via OneLink. Lorsque les utilisateurs reçoivent le SMS et cliquent sur le lien :

* S'ils ont déjà installé l'app, ils sont directement dirigés vers la page du fruit concerné.
* S’ils n’ont pas encore l’app, ils sont dirigés vers l’app Store ou la page de destination appropriée, en fonction de leur appareil. Ensuite, une fois qu'ils ont téléchargé et ouvert l'app, ils sont dirigés directement vers la page correspondant aux fruits.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Remarques |
| --- | --- |
| <span id="onelink-characters"></span>Caractères OneLink | <ul><li>La longueur totale de l'URL ne doit pas dépasser 2 000 caractères</li><li>Le nom du lien et de la source média ne doit pas dépasser 150 caractères</li><li>Les caractères spéciaux qui suivent ne sont pas autorisés dans les paramètres ou valeurs OneLink : ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \} et %<ul><li>Le caractère spécial () n'est pas autorisé dans les paramètres de redirection Android, iOS et web.</li></ul></li><li>L'ID du lien court ne doit pas dépasser 50 caractères</li></ul> |
| <span id="posting-onelink-urls-in-web-pages"></span>Publier des URL OneLink sur des pages web | L'utilisation de `target="_blank"` dans la balise href HTML n'entraîne pas la redirection vers Google Play ou l'App Store. Si l'URL OneLink est placée dans une balise html **a** avec l'attribut **target="\_blank"**, une page vierge s'ouvre dans Chrome sur Android et iOS. Cela affecte la fonctionnalité OneLink. Assurez-vous que la balise **a** n'inclut pas l'attribut cible. |
| <span id="agencies"></span>Agences | Une agence peut utiliser les modèles OneLink existants pour créer des liens d'attribution personnalisés pour elle-même **si elle est partenaire de toutes les apps du modèle**. |
| <span id="social-media-preview-image"></span>Image de l'aperçu pour les réseaux sociaux | Si le type d'image n'est pas pris en charge par la plateforme de réseaux sociaux, celle-ci ne s'affiche pas. |
| <span id="desktop"></span>Ordinateur | Lorsque vous définissez l'URL ou le template OneLink pour rediriger les utilisateurs d'ordinateur vers une autre URL, l'URL web est ajoutée au lien dans le paramètre `af_web_dp`. Si le lien contient `af_web_dp`, AppsFlyer n'enregistre pas le clic s'il provient d'un ordinateur de bureau. |
| <span id="af_enc_data"></span>af\_enc\_data | Non pris en charge dans les URL d’impression. |
| <span id="social-media-preview-og-tag"></span>Aperçu des réseaux sociaux - balise OG | Pour WhatsApp, l'image ne doit pas dépasser 300 Ko. |
| <span id="android-social-apps-webview-deep-linking-redirection"></span>Apps sociales Android WebView redirection du deep linking | En raison de modifications apportées dernièrement à certaines apps sociales Android, le flux de redirection du deep linking dans la vue interne du navigateur (WebView) a été interrompu.<br /><br />Pour prendre en compte les changements et réactiver le deep linking et la redirection, nous avons dû introduire une nouvelle interaction d'utilisateur pour les apps sociales Android suivantes :<ul><li>Versions de Facebook supérieures à v420</li><li>Instagram</li><li>Facebook Messenger</li><li>Snapchat</li></ul>Le nouveau flux d'utilisateurs exige que les utilisateurs des apps susmentionnées cliquent sur un deuxième bouton de la page d'accueil pour déclencher la redirection vers Google Play Store ou tout autre app store.<br /><br /><br />**Remarque** :<ul><li>Les versions 420 et + de Facebook fonctionnent comme avant, sans besoin d'aucune autre action de la part de l'utilisateur.</li><li>Les liens d'app dans les posts Facebook fonctionnent comme avant, sans nécessiter aucune autre action de la part de l'utilisateur.</li><li>Les liens d'app dans le Chat Instagram fonctionnent comme avant, sans nécessiter aucune autre action de la part de l'utilisateur.</li><li>Dans le flux de deep linking, lorsque l'app n'est pas installée, il existe une exception : un message d'erreur pop-up. Ce message n'affecte pas le flux, l'utilisateur est bien redirigé vers l'app store comme il se doit.</li></ul> |
| <span id="onelink-link-previews-sometimes-fail-to-display-correctly-on-facebook-and-linkedin"></span>Les aperçus des liens OneLink ne s'affichent parfois pas correctement sur Facebook et LinkedIn. | **Description**  <br />Le problème survient lorsque le site web de destination ne voit pas la chaîne user-agent `AppsFlyerBot-Previewer/1.0` dans la requête de prévisualisation comme issue d'un robot (ou d'un crawler). Dans ce cas, le site web ne répond pas avec le contenu de prévisualisation avec balise OG approprié.<br /><br />**Solution**  <br />Vous pouvez configurer votre page d'accueil de manière à ce que les pages comportant la chaîne d'en-tête user-agent `AppsFlyerBot-Previewer/1.0` soient considérées comme provenant d'un robot en <Anchor target="_blank" href="https://moz.com/learn/seo/robotstxt">mettant à jour le fichier robot.txt de votre site web</Anchor>. |

</Accordion>

<div data-zendesk-anchors="onelink-links-and-experiences=liens-et-exp%C3%A9riences-onelink h_01H8Y6DDT4M8XGAEJJVTHKHPKV=liens-et-exp%C3%A9riences-onelink create-a-onelink-link=cr%C3%A9er-un-lien-onelink h_01H8Y6DDT41C6JYKXET0NDRB1G=cr%C3%A9er-un-lien-onelink h_01H8Y6DDT4C543RS2BXAGS487M=experiences h_01H8Y6DDT4WZ5FKZYBX2H08MFD=general-settings enable-retargeting-for-the-app=activer-le-retargeting-pour-lapp h_01H8Y6DDT4R7785X5DRES66BKJ=activer-le-retargeting-pour-lapp h_01H8Y6DDT4JT9H0R13ZNGHJ79S=social-media-preview-og-tags h_01H8Y6DDT4PHY2F5E3GK582P51=social-app-landing-page h_01H8Y6DDT463F5569B28DD17SV=important- h_01H8Y6DDT4MMD1AW6D1PNGNX5X=note to-use-the-social-app-landing-page=pour-configurer-une-page-daccueil-dapp-sociale h_01H8Y6DDT4JB4RT438MAGNNX2S=pour-configurer-une-page-daccueil-dapp-sociale to-set-up-the-social-apps-landing-page=pour-configurer-la-page-daccueil-des-apps-sociales h_01H8Y6DDT4G34S3RV3ZH64XT19=pour-configurer-la-page-daccueil-des-apps-sociales h_01H8Y6DDT5XNJVYW2Y8F6JWPK2=deep-linking-and-deferred-deep-linking h_01H8Y6DDT5JR3B3DMR87JCBZ69=conseils h_01H8Y6DDT5KSBE00WWDGQ5R1AQ=note-1 h_01H8Y6DDT58FC3HMSRZBMGZZRJ=redirection h_01H8Y6DDT5AAQ3BZD8QB9H19QB=additional-parameters h_01H8Y6DDT5B6M7CETQRD9NKX8R=testing new-users-without-your-app-installed=les-nouveaux-utilisateurs-qui-nont-pas-install%C3%A9-votre-app h_01H8Y6DDT50DH5TGVVPJPJC4MG=les-nouveaux-utilisateurs-qui-nont-pas-install%C3%A9-votre-app existing-users-with-your-app-installed=les-utilisateurs-existants-qui-ont-d%C3%A9j%C3%A0-install%C3%A9-votre-app h_01H8Y6DDT5KDEWS40XPYGYC8HK=les-utilisateurs-existants-qui-ont-d%C3%A9j%C3%A0-install%C3%A9-votre-app additional-procedures=proc%C3%A9dures-suppl%C3%A9mentaires h_01H8Y6DDT5YR8JA5YMZFPMCC2X=proc%C3%A9dures-suppl%C3%A9mentaires h_01H8Y6DDT58EFS8S46D1AVP3T1=create-a-custom-impression-url h_01H8Y6DDT5S4NEJMNJR4K3QMNH=deep-linking-post-event h_01H8Y6DDT58Y6CS27M2W3MHYAD=deferred-deep-linking-with-ios-private-relay h_01H8Y6DDT5A7J07KNNRWCXCBH2=app-clipbased-solution flow=flux h_01H8Y6DDT5VDKAR89B8N6D7YMB=flux h_01H8Y6DDT62H71A8DPG00A3ZTN=clipboardbased-solution flow::21baf6ac=flux-1 h_01H8Y6DDT638T7C9HQHZ1CJ726=flux-1 requirements=exigences h_01H8Y6DDT6JGP33AWFQV6Z8FF0=exigences setup=configuration h_01H8Y6DDT61ENGJFZ1XS28GS1T=configuration additional-information=informations-suppl%C3%A9mentaires h_01H8Y6DDT679SGBTSM669F9FHV=informations-suppl%C3%A9mentaires h_01H8Y6DDT6TX4WTP2HYRF11DZ3=examples h_01H8Y6DDT6TQYRS81BMHARB62S=traits-and-limitations" />
