---
title: Guide d’intégration du SDK Web PBA
metadata:
  keywords:
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-05-17T09:05:30Z'
  edited_at: '2026-08-14T16:22:54Z'
  id: 360001610038
  locale: fr
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/fr/articles/360001610038
---
> **En bref :** Intégrez AppsFlyer aux sites web à l’aide du SDK Web pour enregistrer et mesurer les visites, les événements, les conversions et les revenus.

[![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)

<div id="advanced-verification-with-smart-banners" />

<div id="advanced-verification-without-smart-banners" />

<div id="standard-with-smart-banners" />

<div id="standard-without-smart-banners" />

<div id="advanced-sdk-verification" />

<div id="standard-web-sdk" />

<div id="important" />

<div id="selecting-a-code-snippet" />

<div id="web-sdk-user-and-integration-guide" />

## Guide d’utilisation et d’intégration du SDK Web

* Balise JavaScript du SDK Web :
  * fait partie de la solution People-Based Attribution (PBA) pour analyser les parcours des utilisateurs sur plusieurs plateformes.
  * signale les visites et les actions des utilisateurs sur votre site Web à la plateforme AppsFlyer.
  * est un module de plug-in de site Web  qui ne nécessite aucune programmation. Il est indépendant du système d’exploitation et du navigateur du visiteur du site Web.
  * Taille : 40 à 60 Ko.
* Implémentez le SDK Web en même temps que le SDK mobile AppsFlyer pour enregistrer et cartographier l’activité des utilisateurs dans votre application mobile et vos environnements web.
* Les événements se produisant en dehors du site web peuvent être enregistrés à l’aide de <Anchor target="_blank" href="/marketers/fr/docs/web-server-to-server-events-api-for-pba-web-s2s">l’API d’événements web de serveur à serveur</Anchor> (Web S2S)

<div id="integrating-the-web-sdk-into-the-website" />

## Intégration du SDK Web dans le site web

<div id="installation-and-integration" />

<Accordion title="Installation et intégration">

<div id="considerations-and-actions-required" />

#### Considérations et mesures requises

| Liste de contrôle d’intégration |
| --- |
| Pour garantir l’enregistrement des visites et des événements, le SDK Web doit être installé sur toutes les pages du site web. |
| Placez l’extrait de code de manière à ce qu’il se charge le plus tôt possible dans la page. Pour ce faire, placez le code en haut, près de la balise head. |
| Si vous intégrez le SDK à l’aide de Google Tag Manager (GTM) :<ul><li>Assurez-vous que le SDK se charge une fois par chargement de page.</li><li>Configurez le SDK pour qu’il se charge dès le chargement de la page à l’aide de la <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">hiérarchisation GTM.</Anchor></li></ul> |
| Vous pouvez implémenter le SDK Web **avec** ou **sans** Smart Banners. Suivez les instructions qui s’appliquent dans les sections qui suivent. |
| Exigences obligatoires en matière d’intégration<ul><li>Enregistrement des visites</li><li>Enregistrement d’événements</li><li>Définition de [l’ID utilisateur client](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid) (CUID)  : Si vous n’avez pas de CUID, contactez votre CSM pour discuter des alternatives.</li></ul>Valider l’intégration à l’aide de <Anchor target="_blank" href="/marketers/fr/docs/test-pba-web-sdk-integration">l’outil de test</Anchor> |

**Avant de commencer** :

* Vérifiez auprès du spécialiste du marketing qu’il a créé le <Anchor target="_blank" href="/marketers/fr/docs/pba-brand-bundles-and-settings">bundle de marque.</Anchor>
* Pour plus de conseils, consultez le <Anchor target="_blank" href="/marketers/fr/docs/onboarding-guide-to-people-based-attribution">guide d’intégration de la PBA</Anchor>.
* N'oubliez pas : Si vous disposez déjà du SDK Web Smart Banners autonome, supprimez-le et remplacez-le par le SDK Web Smart Banners et l'attribution basée sur les personnes. Ne vous contentez pas d'ajouter seulement le SDK Web pour PBA autonome.

**Procédez comme suit :**

* Obtenez la clé de développement web du SDK Web. **Attention !** Ce n’est pas la clé utilisée par les applications mobiles.
  * **Pour obtenir la clé de dev Web :**
    1. Dans AppsFlyer, dans le menu supérieur, sélectionnez l’onglet **Mes applications**.
    2. Cliquez sur **Voir le bundle de marques.**
    3. Copiez la clé de développement web requise.**(WEB\_DEV\_KEY)**
* Si vous implémentez des bannières intelligentes, obtenez la clé Smart Banners.   
  * **Pour obtenir la clé Smart Banners :**
    1. Dans AppsFlyer, dans le menu latéral, accédez à **Engagement** > **Web to App** > **Smart Banners.**
    2. Copiez la **clé Smart Banners** requise.
* Autorisations pour ajouter des scripts aux balises d’en-tête sur le site web.
* Si vous utilisez Google Tag Manager, il doit être intégré au site web.

**Procédez à l’intégration du SDK web à l’aide de l’une des options suivantes.**

<Tabs>
<Tab title="">

<div id="javascript-code-snippet" />

#### Extrait de code JavaScript

Intégrez le SDK web à l’aide de l’une des méthodes suivantes.

<div id="to-install-the-web-sdk-without-smart-banners" />

#### **Pour installer le SDK Web sans Smart Banners :**

1. Répétez la procédure qui suit sur toutes les pages de votre site web.
2. Dans l’extrait de code qui suit, remplacez le `WEB_DEV_KEY` à l’aide de la clé spécifiée dans les prérequis.
3. Collez l’extrait de code dans la balise head de votre site web. Collez-le en haut de la balise head.

```html
<script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
</script>
```

<div id="to-implement-the-web-sdk-with-smart-banners" />

#### **Pour implémenter le SDK Web avec Smart Banners :**

1. Répétez la procédure qui suit sur toutes les pages de votre site web.
2. Dans l’extrait de code qui suit, remplacez `WEB_DEV_KEY` et `YOUR_BANNER_KEY`à l’aide des clés spécifiées dans les prérequis.
3. Collez cet extrait de code dans la balise head du site web. Collez-le en haut de la balise head.

```html
<script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF", "pba,banners",{pba: {webAppId: "WEB_DEV_KEY"}, banners: {key: "YOUR_BANNER_KEY"}});
AF('banners', 'showBanner');
</script>
```

</Tab>

<Tab title="Google Tag Manager">

**Pour implémenter le SDK Web avec Google Tag Manager (GTM) :**  

1. <Anchor target="_blank" href="https://developers.google.com/tag-manager/quickstart">Accédez à Google Tag Manager.</Anchor>
2. Créez une balise pour le SDK web AppsFlyer.  

   [![](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)
3. Sélectionnez le type de balise **HTML personnalisée**.
4. Donnez un nom significatif à la balise.
5. Effectuez l'une des opérations suivantes :
   * Si vous intégrez le SDK web **sans** Smart Banners :
     1. Collez l’extrait de code qui suit dans la fenêtre de **configuration de la balise**.
     2. Dans l’extrait de code, remplacez `WEB_DEV_KEY` par la clé mentionnée dans les prérequis.  

        ```javascript
        <!-- AppsFlyer web SDK -->
        <script>
        !function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
        (t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
        t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
        o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
        p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
        </script>
        ```
   * Si vous intégrez le SDK web **aux** Smart Banners :
     1. Collez l’extrait de code qui suit dans la fenêtre de **configuration de la balise**.
     2. Dans l’extrait de code, remplacez `WEB_DEV_KEY` et `YOUR_BANNER_KEY`à l’aide des clés mentionnées dans les prérequis.  

        ```javascript
        <!-- AppsFlyer web SDK -->  
        <script>
        !function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
        (t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
        t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
        o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
        p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF", "pba,banners",{pba: {webAppId: "WEB_DEV_KEY"}, banners: {key: "YOUR_BANNER_KEY"}});
        AF('banners', 'showBanner');
        </script>
        ```
6. Cliquez sur **Enregistrer**.
7. Effectuez l'une des opérations suivantes :
   * **Pour ajouter le déclencheur à toutes les pages :**
     1. Cliquez sur **Ajouter un déclencheur**.

        [![gtm-af-tag-sdk-trigger.png](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)
     2. Sélectionnez **Toutes les pages**.
     3. Cliquez sur **Enregistrer.**
     4. Saisissez un nom de balise, cliquez sur **Enregistrer**.  
        Vous avez terminé la procédure.
   * **Pour ajouter le déclencheur à des pages spécifiques :**

     1. Cliquez sur **Enregistrer la balise**.
     2. Dans la fenêtre principale de GTM, sélectionnez **Déclencheurs.** Cliquez sur **Nouveau**.
     3. Cliquez sur l’icône du stylo.
     4. Choisissez le type de déclencheur **Page vue**.  
        [![PBAselectTrigger_us-en.jpg](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)
     5. Sélectionnez **Certaines pages vues.**
     6. Définissez la page et déclenchez les conditions selon vos besoins.
     7. Cliquez sur **Enregistrer**.
     8. Associez le déclencheur à la balise SDK Web AppsFlyer. Pour ce faire :
        1. Dans la fenêtre principale de GTM, sélectionnez Balises.
        2. Sélectionnez la balise que vous avez créée précédemment.
        3. Dans le panneau de déclenchement, cliquez sur le stylet.
        4. Sélectionnez le déclencheur d’affichage de page que vous avez créé précédemment.  

           [![](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)
        5. Cliquez sur **Enregistrer**.

</Tab>

<Tab title="Adobe Launch Tag Manager">

1. [Création d’une propriété dans Adobe Experience Cloud](/docs/pba-web-sdk-integration-guide#create-a-property-in-adobe-experience-cloud)
2. [Ajout du SDK web à la propriété Adobe Launch](/docs/pba-web-sdk-integration-guide#add-the-web-sdk-to-the-adobe-launch-property)
3. [Ajout de la balise Adobe Launch au site web](/docs/pba-web-sdk-integration-guide#add-the-adobe-launch-tag-to-the-website)
4. [Publication de l’environnement Adobe Launch](/docs/pba-web-sdk-integration-guide#publish-the-adobe-launch-environment)

<div id="create-a-property-in-adobe-experience-cloud" />

<Accordion title="Création d’une propriété dans Adobe Experience Cloud">

![adobe_create_property.png](https://files.readme.io/1f97d619d5fdfe47b1dd1a2e17c0169e939c32bcda62580ba259d6e86f61d6c2-20260884824209.png)

1. Allez sur **Adobe Experience Cloud** > **Lancer**.
2. Dans **Adobe Experience Cloud Launch**, cliquez sur **Accéder au lancement.**
3. Cliquez sur **Nouvelle propriété**.
4. Nommez la propriété.
5. Dans **Plateforme**, sélectionnez **Web**.
6. Saisissez le domaine de votre site web.
7. Cliquez sur **Enregistrer**.

</Accordion>

<div id="add-the-web-sdk-to-the-adobe-launch-property" />

<Accordion title="Ajout du SDK web à la propriété Adobe Launch">

<Image alt="web_property_rules.png" src="https://files.readme.io/5f592f3ce1f5b319c8f6f96a6235618d884a4faccb1387b1f22c1fd2ce662d15-360006168098.png" width="491px" />

1. Sur la page **Mes propriétés Web**, sélectionnez l’onglet **Règles** .
2. Nommez la règle. Nous vous recommandons d’utiliser **Charger le SDK web**.
3. Dans la section **IF**, sous **EVENEMENTS**, cliquez sur **+Ajouter**.
   * Dans **Type d'événement**, sélectionnez **Core - DOM Ready**.
   * Cliquez sur **Conserver les modifications**.
4. Dans la section **THEN**, sous **Actions**, cliquez sur **+Ajouter**.
   * Dans **Type d'action**, cliquez sur **Code personnalisé**.
   * Sélectionnez **JavaScript** > **Ouvrir l’éditeur** et collez l’extrait de code du SDK Web **sans les balises &lt;script>**.
   * Cliquez sur **Conserver les modifications** pour fermer l'éditeur de code.
5. Cliquez sur **Enregistrer**.

</Accordion>

<div id="add-the-adobe-launch-tag-to-the-website" />

<Accordion title="Ajout de la balise Adobe Launch au site web">

[![adobe_tag.png](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)

1. Sur la page **Mes propriétés web**, sélectionnez l'onglet **Environnements**.
2. Trouvez la ligne avec l'environnement que vous voulez publier (développement ou production).
   * Sous le header **INSTALL**, cliquez sur l'icône en forme de boîte sur la ligne concernée. Il s'agit généralement d'un environnement de production.
   * Consultez la section relative à la publication de l'environnement **Adobe Launch** .
3. Dans la boîte de dialogue **Instructions d'installation web** :
   * Copiez l'extrait de code de script.
   * Fermez la boîte de dialogue.
4. Collez l’extrait de code dans la balise &lt;head> du site Web.

</Accordion>

<div id="publish-the-adobe-launch-environment" />

<Accordion title="Publication de l’environnement Adobe Launch">

[![adobe_publishing_env.png](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)

1. Sur la page **Mes propriétés web**, accédez à l'onglet **Publication**.
2. Dans la section **Développement** , cliquez sur **Ajouter une nouvelle bibliothèque.**
   * Nommez la bibliothèque et choisissez un environnement.
   * Dans **CHANGEMENTS DE RESSOURCES**, cliquez sur **Ajouter une ressource.**
   * Cliquez sur **Règles** > **Charger le SDK Web** > **Dernières** > **Sélectionner et créer une nouvelle révision**.
   * Cliquez sur **Enregistrer**.
3. Dans la section **Développement** :
   * À côté de la bibliothèque nouvellement créée, cliquez sur le menu Action (3 points) > sélectionnez **Build de développement.**
   * Cliquez à nouveau sur le menu d’action > sélectionnez **Soumettre pour approbation**.
4. Dans la section **Soumis** :
   * Cliquez sur le menu d’action > sélectionnez **Build de test**.
   * Cliquez à nouveau sur le menu d’action > sélectionnez **Approuver pour publication**.
5. Dans la section **Approuvé** :
   * Cliquez sur le menu d’action > sélectionnez **Créer et publier en production.**
   * Le processus est maintenant terminé.

</Accordion>

Lorsque le site web se charge sur un appareil mobile, la création active s’affiche dans la bannière. Pour afficher la bannière sur certaines pages uniquement ou selon les actions de l'utilisateur, consultez les <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">règles Adobe Launch</Anchor>.

</Tab>
</Tabs>

</Accordion>

<div id="ensure-that-the-sdk-is-working" />

<Accordion title="Assurez-vous que le SDK fonctionne">

Une fois installé, vérifiez que le SDK Web AppsFlyer est appelé par le navigateur du visiteur et que les messages sont envoyés. Pour cela, examinez le message de connexion au réseau dans le navigateur.

**Pour vous assurer que le SDK se charge et fonctionne :**

1. Allez sur le site Web.
2. Ouvrez les outils de développement du navigateur.

   ![WebSDK_us-en.jpg](https://files.readme.io/5550f0ee8c1a5852a983e6482cb0489696b669ffe5fade49d2308ee32f57201b-360009548497.jpg)
3. Accédez à l’onglet **Réseau** (A).
4. Actualisez la page.
5. Filtrez par **wa.Appsflyer** (B).
6. Sélectionnez le message **d’événements** (C).
7. Dans l’onglet En-têtes (D), assurez-vous que :
   * **L’URL de la demande** est wa.appsflyer.com/events.
   * site\_id query parameter= `WEB_DEV_KEY`.
   * **Le code d’état est 200** (E).
8. Vérifiez que la valeur de site\_id est égale à la valeur de `WEB_DEV_KEY` dans les paramètres de bundle de marques :
   1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Paramètres** > **Bundles de marques.**
   2. Cliquez sur **Clé de développement Web** pour copier la clé.
   3. Collez la clé à n’importe quel emplacement (nouvel onglet du navigateur, bloc-notes) pour l’afficher.
   4. Vérifiez que les site\_id et `WEB_DEV_KEY` correspondent.
9. Assurez-vous que le SDK ne se charge qu’une seule fois. Le chargement de plusieurs SDK peut entraîner l’arrêt du fonctionnement du SDK.

</Accordion>

<div id="sending-events-optinoptout" />

<Accordion title="Envoi d’événements opt-in/opt-out">

![5578-VistiorPrivacyOptIn_us-en.png](https://files.readme.io/cd6cbcaeb7f831f4efe74a9a6c6b20d5095602e7edf4dd38becd90864e73c2fb-360010263157.png)

Le SDK Web envoie les données d’événement des visiteurs à AppsFlyer. Vous pouvez contrôler, arrêter ou démarrer l’envoi d’événements tel que décrit dans cette section.

N'oubliez pas :

* **Paramètre d’état initial du SDK** : détermine si le SDK envoie des événements lors du chargement initial de la page web ou s’il doit attendre une commande explicite pour commencer à envoyer des événements. Le paramètre est contenu dans l’extrait de code web.
* **Contrôle explicite :** permet d’arrêter ou de démarrer l’envoi d’événements. Par exemple, si vous implémentez des bannières d’acceptation et de désactivation des données (alias bannières de consentement aux cookies), intégrez les commandes explicites dans vos contrôles de bannière pour démarrer et arrêter l’envoi d’événements. Le contrôle explicite explicite a la priorité sur le paramètre d’état initial du SDK et utilise des cookies propriétaires persistants présentant les caractéristiques suivantes :  
  * Définie sur le domaine du site web.
  * Expire après une période définie par le SDK Web ou déterminée par le navigateur. Après l’expiration du cookie, le SDK Web revient à l’état initial.
  * Le cookie du SDK Web n’interfère pas avec les paramètres de cookies spécifiques au navigateur et y est toujours soumis.

<div id="sdk-initial-state-setting" />

#### Réglage de l’état initial du SDK

| Paramètre | Extrait requis |
| --- | --- |
| [Par défaut] Envoyer des événements | Apportez la modification suivante à l’extrait de code du SDK Web. Si nécessaire, ajoutez le paramètre measurementStatus :<br /><br />Définir measurementStatus=true<br /><br />`{pba:{webAppId: "********-****-****-*****************",measurementStatus:true}` |
| Ne pas envoyer d’événements | Apportez la modification suivante à l’extrait de code du SDK Web. Si nécessaire, ajoutez le paramètre measurementStatus :<br /><br />Définir measurementStatus=false  <br />  <br />`{pba: {webAppId: "********-****-****-*****************",measurementStatus:false}` |

<div id="nonce-with-smart-banners" />

<div id="nonce-without-smart-banners" />

<div id="advanced-sdk-verification-with-csp-nonce-snippets" />

<div id="content-security-policy-csp" />

<div id="explicit-control" />

#### Contrôle explicite :

| Option | Commande |
| --- | --- |
| Commencer à envoyer des événements (opt-in) | `window.AF_SDK.PLUGINS.PBA.enableMeasurement()` |
| Arrêter d’envoyer des événements (opt-out) | `window.AF_SDK.PLUGINS.PBA.disableMeasurement()` |

</Accordion>

<div id="implement-a-content-security-policy-csp-policy" />

<Accordion title="Mettre en œuvre une stratégie de sécurité du contenu (CSP)">

Certains webmasters exigent que Javascript soit sécurisé par leur CSP. Vous pouvez utiliser un certain nombre de mécanismes CSP pour ce faire, notamment :

* CSP *self*
* CSP nonce : Ajoutez la commande nonce à la balise de script à l’aide d’une valeur nonce aléatoire que vous avez générée.

  ```html
  <script nonce="random value generated by you">
  !function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
  ....
  </script>
  ```

</Accordion>

<div id="discard-query-params" />

<Accordion title="Ignorer les paramètres de requête">

Si vos paramètres de requête incluent des informations que vous ne souhaitez pas qu’AppsFlyer enregistre, vous pouvez configurer la plate-forme pour qu'elle ignore certains ou tous ces paramètres. Ces informations ne seront pas disponibles dans les données brutes ou les rapports.

Vous pouvez implémenter les méthodes décrites en ce qui concerne les URL, les référents et les header\_referer.

<div id="query-discard-options" />

#### Options de rejet de requête

| Méthode | Description |
| --- | --- |
| Ignorer tous les paramètres de requête | Ajouter `af_url=true` à l’url |
| Ignorer les paramètres de requête spécifiés | En définissant un masque de paramètre de requête, vous spécifiez les paramètres à ignorer.  Définissez le masque de rejet en utilisant `af_url_mask=param` où param est le nom du paramètre.<br /><br />Exemple :<br /><br />**Url avec masque :**<br /><br />`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`<br /><br />**URL après rejet :**<br /><br />**`param1=value1&af_url_mask=param2;param3`** |

</Accordion>

<div id="principles-of-event-recording" />

## Principes de l’enregistrement des événements

<div id="conversion-and-standard-events" />

<Accordion title="Conversions et événements standard">

* Les événements utilisateur sont enregistrés par le SDK, qui envoie l’événement à la plate-forme AppsFlyer.
* À l’aide de la liste des <Anchor target="_blank" href="/marketers/fr/docs/pba-brand-bundles-and-settings#web-event-settings">événements de conversion</Anchor> définie par le spécialiste du marketing, AppsFlyer divise les événements en événements standard et événements de conversion.
* Les données relatives aux événements de conversion sont disponibles dans les tableaux de bord PBA.
* Les données de conversion et d’événement standard sont disponibles dans <Anchor target="_blank" href="/marketers/fr/docs/pba-raw-data-reports">les rapports de données brutes.</Anchor>

<div id="conversion-events" />

### Événements de conversion

* Les événements de conversion fournissent des informations sur vos efforts marketing et commerciaux. Les événements de conversion comprennent les achats, les téléchargements, les inscriptions et les abonnements.
* PBA attribue les événements de conversion à la source média qui a poussé l’utilisateur à visiter le site web.
* En identifiant la source média attribuée, vous pouvez mesurer et différencier la qualité des utilisateurs apportés par différentes sources média.
* Les événements de conversion sont utilisés pour enregistrer les revenus et calculer le ROI.
* Utilisez-les pour comparer le budget des publicités pour des sources média spécifiques aux revenus générés par les utilisateurs provenant de ces sources.

<div id="standard-events" />

### Événements standard

* Les événements standard sont utilisés pour valider le parcours utilisateur et les tunnels qui mènent aux conversions.
* Utilisez-les pour mesurer l’activité des utilisateurs et mettre en évidence les sources média qui suscitent l’intérêt.
* Enregistrez l’activité des utilisateurs pour marquer ces derniers pour les campagnes de réengagement.

<div id="recording-events" />

### Enregistrement d’événements

Déclenchez le SDK Web pour enregistrer des événements lorsque certaines conditions sont remplies, par exemple, lors du chargement d’une page de destination ou lorsque les utilisateurs interagissent avec des éléments du site web. Voir des [exemples d’enregistrement d’événements](/docs/pba-web-sdk-integration-guide#enregistrement-dévénements).

</Accordion>

<div id="identifying-users-using-customer-user-id-cuid" />

<Accordion title="Identification des utilisateurs à l’aide de l’ID utilisateur client (CUID)">

* Les utilisateurs web sont identifiés dans AppsFlyer à l’aide du CUID unique que vous leur attribuez. En règle générale, le CUID est géré par vos serveurs d’arrière plan.
* Utilisez la même valeur CUID que celle que vous utilisez dans l’environnement mobile. Cela vous permet d’avoir une vue globale de l’activité des utilisateurs sur plusieurs plate-formes. La fonction du SDK mobile est la fonction setCustomerUserId (<Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid#paramétrer-le-cuid">iOS,</Anchor> <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid#paramétrer-le-cuid">Android,</Anchor> <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid#paramétrer-le-cuid">Unity</Anchor>).
* Pour définir le CUID dans le SDK Web :
  * Définissez le CUID au moment où vous y avez accès. La plupart du temps, cela signifie que vous devez attendre que l’utilisateur s’identifie via la connexion ou l’inscription.
  * Déclenchez l’appel JavaScript à setCustomerUserId(), comme indiqué dans l’exemple suivant.   
    Remarque : envoyez le CUID sous forme de chaîne, même s’il s’agit d’un nombre. Utilisez des guillemets.
* Si vous implémentez Web S2S, vous devez potentiellement informer PBA lorsque vous <Anchor target="_blank" href="/marketers/fr/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method">associez</Anchor> un CUID à un identifiant de visiteur web en arrière plan.
* Les CUID ne doivent pas contenir <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid#cuid-et-confidentialité">d’informations personnelles directement identifiables</Anchor> telles qu’un numéro de téléphone ou une adresse e-mail.

**Exemple : définir le CUID**

```javascript
// Associate all current user web events to distinct ID 663274 
AF('pba', 'setCustomerUserId' , '663274')
```

</Accordion>

<div id="web-sdk-event-parameters" />

<Accordion title="Paramètres d’événement du SDK Web">

| Nom du paramètre | Obligatoire | Description |
| --- | --- | --- |
| eventType | Oui | Type d'événement<br /><br />Format : Chaîne<br /><br />Renseignez toujours ce paramètre avec EVENT.<br /><br />Exemple : eventType : « ÉVÉNEMENT » |
| eventName | Oui | Nom de l'événement<br /><br />Format : Chaîne<br /><br />Exemple : Achat, abonnement |
| eventCategory | Non | Ce paramètre est obsolète et sera prochainement supprimé du système. Utilisez plutôt le paramètre eventValue. |
| eventLabel | Non | Ce paramètre est obsolète et sera prochainement supprimé du système. Utilisez plutôt le paramètre eventValue. |
| eventRevenue | Non | Revenus affectés à un événement de conversion<br /><br />Format : Float |
| eventRevenueCurrency | Non | Devise du revenu<ul><li>Code de devise <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> à 3 caractères.</li><li>Par défaut : USD</li></ul>Format : Chaîne |
| Valeur de l'événement | Non | Carte des paramètres de l’événement décrivant l’événement. Utilisez ce paramètre pour envoyer des évènements rich in-app, tels que la référence SKU du produit et le prix de l’article.<br /><br />Format : JSON<br /><br />**Exemple :** Pour envoyer le SKU ABC123, de couleur bleue et au prix unitaire de 3,99 $<br /><br />`{"sku": "ABC123", “color": "blue", "unit_price":3.99,"currency": "USD"}`<br /><br />**Limitation :** 1000 caractères. Ne dépassez pas cette limite, sinon la valeur sera tronquée. |

</Accordion>

<div id="recording-event-scenarios" />

<Accordion title="Enregistrement de scénarios d’événements">

Exemple d’événement

```javascript
// purchase event of shoes with associated revenue
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

Les événements que vous envoyez dépendent de la nature de votre application web. Par exemple, une application de boutique en ligne nécessite un ensemble d'événements différent de celui d'un site d'actualités. Consultez les scénarios qui suivent pour avoir une idée des événements que vous devez envoyer et quand.

<div id="online-store" />

#### Boutique en ligne

Supposons que vous gériez une boutique en ligne. Voici quelques événements standard que vous voudrez peut-être enregistrer :

* Rechercher : événement standard
* Ajouter au panier : événement standard
* Retirer du panier : événement standard
* Achat : événement de conversion

Site d’actualités

Supposons que vous gériez un nouveau site d’actualités. Voici quelques événements que vous voudrez peut-être enregistrer :

* Inscription : événement de conversion
* Achat d’abonnement : événement de conversion

</Accordion>

<div id="ensuring-that-events-are-sent" />

<Accordion title="S’assurer que les événements sont envoyés">

Cette section s’adresse aux développeurs web.

<Anchor target="_blank" href="/marketers/fr/docs/test-pba-web-sdk-integration">Test de l’intégration du SDK Web PBA :</Anchor> visualisez les événements de test en temps réel.

**Pour vous assurer que les événements sont envoyés à AppsFlye**r :

1. Ouvrez le site web.
2. Ouvrez les outils de développement du navigateur.
   * <Anchor target="_blank" href="https://developers.google.com/web/tools/chrome-devtools/open#console">Comment ouvrir les outils de développement dans Chrome</Anchor>
   * <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/Web_Inspector_Tutorial/EnableWebInspector/EnableWebInspector.html">Comment ouvrir les outils de développement dans Safari</Anchor>
3. Basculez vers l’onglet Réseau.
4. Déclenchez l'événement.
5. Filtrez par message.

   ![pba_af_event.png](https://files.readme.io/394f43890d1aaf09114054a3bca1a003178526e768a5da0b554dbc8d63ef1eb4-360003502238.png)
6. Recherchez une requête réseau qui commence par la destination wa.appsflyer.com (voir capture d’écran ci-dessous).
7. Assurez-vous que :
   1. Le code d’état est 200.
   2. La charge utile de la requête s’aligne sur les paramètres de l’événement.

</Accordion>

<div id="examples" />

## Exemples

<div id="recording-events::f1e16eae" />

<Accordion title="Enregistrement d’événements">

Le code fourni est fourni à titre indicatif. N’utilisez pas ce code tel quel.

* Hypothèses: Le SDK Web est déjà chargé par la page au moment de l’envoi de l’événement.
* Les exemples de scénarios contiennent le code d’enregistrement des événements dans les cas suivants :
  * Une page de destination se charge.
  * Les utilisateurs interagissent avec le site web.

<Tabs>
<Tab title="Enregistrement d’événements natif">

**Enregistrement des événements lors du chargement d’une page de destination**

* Vous avez mis en place une page d’abonnement aux newsletters et souhaitez enregistrer les abonnements.
* Vous pouvez également configurer une page de remerciement et rediriger les utilisateurs vers celle-ci après leur inscription.

```html
<html>
    <head>
        <!-- Assume that the server returns a response with details about the newly subscribed user -->
        <!-- Alternatively, you can extract data from localStorage or cookies,
            in case data was set in either of them during the subscription process
        -->
        <script>window.onload = function(){
            AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion', eventValue: {'label' : 'newspaper'}, eventName: 'subscription',}); } </script> </head> <body> <h1>Thank You for Subscribing to Our Newsletter</h1> </body> </html>
```

* Le code précédent contient une page HTML de base. La page web doit charger le SDK Web pour que vous puissiez envoyer des événements.
* Lorsque la page est chargée et que l’utilisateur y est redirigé, la méthode de chargement de la fenêtre appelle la méthode AF() pour envoyer l’événement d’abonnement à AppsFlyer.

**Enregistrement des événements lorsque les utilisateurs interagissent avec le site web**

* Vous avez un site web de commerce électronique et vous souhaitez enregistrer les événements de paiement.
* Lorsque l’utilisateur clique sur le bouton de paiement, le SDK Web envoie un événement à AppsFlyer.

```html
<html>
<head>
    <!-- Assume that data about products in the shopping cart
    is stored in localStorage -->
    <script>
        window.onload = function () {
            document.getElementById('checkout').addEventListener('click', function () {
                AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
            });
        }
    </script>
</head>
<body>
    <h1>Shopping Cart</h1>
    <h2>Shirt</h2>
    <p>
        <ul>
            <li>Color: Blue</li>
            <li>Quantity: 2</li>
            <li>Price: $20</li>
        </ul>
    </p>
    <h2>Pants</h2>
    <p>
        <ul>
            <li>Color: Black</li>
            <li>Quantity: 3</li>
            <li>Price: $15</li>
        </ul>
    </p>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

Le code précédent ci-dessus montre une page HTML de base. La page web doit charger le SDK Web pour que vous puissiez envoyer des événements.

* Une fois la page chargée, elle lie un écouteur de clic au bouton **Paiement** .
* Lorsque l’utilisateur clique sur le bouton **Paiement**, la fonction de rappel :
  * Récupère les données de localStorage.
  * Appelle la méthode AF() et lui transmet des données.
* La méthode AF() envoie l’événement à AppsFlyer.

</Tab>

<Tab title="Enregistrement d’événements via Tag Manager">

**Enregistrement des événements lors du chargement d’une page de destination**

* Vous avez mis en place une page d’abonnement aux newsletters et souhaitez enregistrer les abonnements réussis.
* Vous configurez une page de remerciement vers laquelle les utilisateurs sont redirigés après s’être inscrits avec succès.

1. Créez une page de remerciement  

   ```html Markup
   <html>
   <head>
       <script>
            // Google Tag Manager loads the Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
        <script>
           // Assume that the server returns a response with details about the newly subscribed user
           function getResponseFromServer() {
               return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
           }
           //Alternatively, you can extract data from localStorage or cookies,
           //in case data was set in either of them during the subscription process
           localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
       </script>
   </head>
   <body>
       <h1>Thank You for Subscribing to Our Newsletter</h1>
   </body>
   </html>
   ```

   Le code précédent charge GTM, qui charge à son tour le SDK Web. Par la suite, deux autres actions ont lieu dans le script. L’une est une fonction qui reçoit une réponse du serveur avec les détails de l’utilisateur. L’autre définit les données sur le stockage local. GTM a accès à la fois à la fonction et à localStorage. Vous pouvez appeler la fonction et accéder à localStorage à l’aide de GTM.
2. Ajoutez une nouvelle balise pour attribuer les abonnements après le chargement de la page de remerciement  

   [![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
3. Donnez un nom distinct à la balise et sélectionnez l’option de type de balise **HTML personnalisée**.
4. Mettez le code suivant dans le **code HTML personnalisé**.  

   ```html
   <script> 
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'}); </script>
   ```

   ![gtm_tag_after_subscribe.png](https://files.readme.io/6cf080f94a97a7f38c50899a93d154320995e91f60963c075a5dd03b3a080408-360003515298.png)
5. Développez le contrôle **Paramètres avancés**, puis le contrôle **Séquencement des balises** sous la zone de texte et assurez-vous qu’il est configuré pour déclencher la conversion après l’exécution de la balise.  

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. Pour déclencher la balise de conversion, définissez un déclencheur. Dans l’exemple, le déclencheur est déclenché lors du chargement de la page de remerciement.  

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

**Enregistrement des événements lorsque les utilisateurs interagissent avec le site web**

* Vous avez un site web de commerce électronique et vous souhaitez enregistrer les événements de paiement.
* Une fois que l’utilisateur a cliqué sur le bouton de paiement, le SDK Web envoie un événement à AppsFlyer.

1. Configurez une page de paiement  

   ```html Markup
   <html>
   <head>
       <script>
           // Google Tag Manager loads the Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
   </head>
   <body>
       <h1>Shopping Cart</h1>
       <h2>Shirt</h2>
       <p>
           <ul>
               <li>Color: Blue</li>
               <li>Quantity: 2</li>
               <li>Price: $20</li>
           </ul>
       </p>
       <h2>Pants</h2>
       <p>
           <ul>
               <li>Color: Black</li>
               <li>Quantity: 3</li>
               <li>Price: $15</li>
           </ul>
       </p>
       <button id='checkout'>Checkout</button>
   </body>
   </html>
   ```

   Le code précédent charge le SDK Web à l’aide de GTM. Le reste est simplement du HTML qui imite une page de panier. Notez le bouton **Paiement**, qui contient l’ID de paiement. Il est nécessaire lors de la configuration de GTM pour gérer un clic sur ce bouton.
2. Dans GTM, cliquez sur **Variables**, **Configurer** et cochez **Élément de clic** dans la liste des **variables intégrées.**  

    [![gtm-create-variable.png](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)
3. Créez une nouvelle variable, donnez-lui un nom significatif et choisissez le type de **Tous les éléments.**  
    [![gtm-checkout-all-elements.png](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png)](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png)
4. Dans la configuration du déclencheur, choisissez **Quelques clics**, choisissez **Élément de clic,** qui **correspond au sélecteur CSS** #checkout.  

    [![gtm-checkout-click-elememt.png](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)
5. Créez une balise pour l’action de paiement, choisissez le type HTML personnalisé et définissez le déclencheur sur le déclencheur de paiement.  

   ```html
   <script>
    AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'}); </script>
   ```

   ![gtm-checkout-tag.png](https://files.readme.io/8d3f99dcd3c3ff8df9e6fc13076b798237b86f8cbc5bbd26f349fa9948edb0d6-360003431857.png)

</Tab>
</Tabs>

* Assurez-vous que la balise de fonctions du SDK Web est chargée avant le déclenchement de l’événement.
* N’envoyez pas de caractères spéciaux dans les valeurs d’événement, comme les symboles monétaires dans la valeur des revenus.
* Les chaînes de valeur doivent être inférieures à 50 caractères.

</Accordion>

<div id="setting-customer-user-id-after-signup" />

<Accordion title="Définition de l’ID utilisateur du client après l’inscription">

Le code fourni dans ces exemples est fourni à titre indicatif uniquement. N’utilisez pas ce code tel quel. Si vous ne savez pas comment utiliser ce code, consultez votre développeur web. 

Supposition: Le SDK Web est chargé par la page avant l’envoi de l’événement ; ne chargez plus le SDK.

Scénario utilisateur :

* Un utilisateur s’inscrit sur votre site web.
* Le code du site web rassemble les détails de l’utilisateur et les envoie à votre serveur.
* Le serveur génère un CUID unique pour l’utilisateur.
* Dans la page de remerciement après l’inscription, vous interrogez le serveur pour obtenir le nouveau CUID.
* À l’aide de la réponse du serveur, vous définissez le CUID AppsFlyer à l’aide de la méthode setCustomerUserId() du SDK Web.

<Tabs>
<Tab title="Google Tag Manager">

Configurer une page d’inscription :

```html Markup
<html>
<head>
    <!-- The Web SDK script loads first -->
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        };
    // This function stores the user email sent to the server after the user reaches the thank you page
    // The response from the server is a unique CUID that should be set using the web SDK setCustomerUserId method
        function storeUserEmail (){
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Sign Up</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Name</label>
            <input type="text" name="name" id="name"></div>
        <br />
        <div> <label>Email</label>
            <input type="email" name="email" id="email"></div>
        <br />
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

Le code précédent ci-dessus est un simple formulaire d’inscription. Lorsque le formulaire est soumis, l’e-mail est stocké dans localStorage. Lorsque l’utilisateur atteint la page de remerciement, son adresse e-mail est envoyée au serveur pour générer le CUID unique de l’adresse e-mail.

Configurez une page de remerciement pour les utilisateurs qui s’inscrivent :

```html Markup
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        // Using the fetch API to send the user email to the server
        // and get the unique user id in return	
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                   res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }  </script> 
     </head> 
     <body> 
        <h1>Thank You for Signing Up!</h1> 
     </body> 
</html>
```

Le code utilise l’API fetch. Il envoie au serveur l’adresse e-mail saisie par l’utilisateur. En supposant que le serveur crée un utilisateur avec un CUID unique lors de l’inscription, l’envoi de l’adresse e-mail au serveur a pour but de recevoir un CUID unique. Le serveur répond avec un CUID unique et ce CUID unique est la valeur transmise avec la méthode setCustomerUserId.

</Tab>

<Tab title="natif">

1. Configurez une page d’inscription :

   ```html Markup
   <html>
   <head>
       <script>  
            // Google Tag Manager loads the Web SDK
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({
                   'gtm.start':
                       new Date().getTime(), event: 'gtm.js'
               }); var f = d.getElementsByTagName(s)[0],
                   j = d.createElement(s), dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true; j.src =
                       'https://www.googletagmanager.com/gtm.js?id=' + i + dl; f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');  

       // This function stores the user email to be sent to the server after the user reaches the thank you page
       // the response from the server is a unique CUID that should be used in the web SDK setCustomerUserId method
           function storeUserEmail (){
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
   </head>
   <body>
       <h1>Sign Up</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Name</label>
               <input type="text" name="name" id="name"></div>
           <br />
           <div> <label>Email</label>
               <input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
   </body>
   </html>
   ```

   Le code ci-dessus est un simple formulaire d’inscription. Lorsque le formulaire est envoyé, l’adresse e-mail est stockée dans localStorage. Lorsque l’utilisateur atteint la page de remerciement, son adresse e-mail est envoyée au serveur pour obtenir le CUID unique de cet e-mail.
2. Configurez une page de remerciement pour les utilisateurs qui s’inscrivent :

   ```html Markup
   (t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
   t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
   o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
   p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
       </script>
       <script>
           // using the fetch api to send the user email to the server
           // and get the unique user id in return 
           window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
                  res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
           } </script> 
       </head>
       <body> 
               <h1>Thank You for Signing Up!</h1> 
        </body> 
    </html>
   ```

   Le code précédent est une page de remerciement avec un déclencheur GTM qui envoie au serveur l’adresse e-mail fournie par l’utilisateur dans le formulaire d’inscription.  
   En supposant qu’à l’inscription, le serveur crée un utilisateur avec un CUID unique.  
   L’envoi de l’e-mail au serveur a pour but de recevoir un CUID unique.  
   Le serveur répond avec un CUID unique qui est envoyé à l’aide de la méthode setCustomerUserId().  
   Continuez cette procédure pour créer le déclencheur et l’onglet.
3. Ajoutez une nouvelle balise pour attribuer les abonnements après le chargement de la page de remerciement.[![](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. Donnez un nom distinct à la balise et sélectionnez l’option de type de balise « HTML personnalisé » [![GoogleTag.jpg](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

   ```html
   <script>
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
            res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
   </script>
   ```
5. Développez le contrôle **Paramètres avancés**, puis le contrôle **Séquencement des balises** sous la zone de texte et assurez-vous qu’il est configuré pour déclencher la conversion après l’exécution de la balise.  

   [![](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. Définissez un déclencheur pour la balise de conversion afin d’indiquer quand la balise de conversion doit être déclenchée (dans l’exemple ci-dessous, elle est déclenchée lors du chargement de la page « Merci »).  

   [![](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Tab>
</Tabs>

La fonction setCustomerUserId peut être envoyée à n’importe quelle étape du flux utilisateur, par exemple, après la connexion et l’inscription de l’utilisateur. AppsFlyer utilise le CUID le plus récent envoyé pour mettre à jour l’utilisateur observé actuel pour les points de contact et les événements passés ou futurs.

Utilisez la même valeur CUID que dans la fonction setCustomerUserd dans l’application mobile (voir mobile setCustomerUserId pour : <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid#paramétrer-le-cuid">iOS,</Anchor> <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid#paramétrer-le-cuid">Android,</Anchor> Unity).

</Accordion>

<div id="addtional-information" />

## Informations supplémentaires

<div id="web-sdk-cookies" />

<Accordion title="Cookies du SDK Web">

Les cookies répertoriés dans le tableau ci-dessous sont définis ou utilisés par Web SDK sur votre site web.

Dans le tableau, les abréviations suivantes sont utilisées :

* AMP : pages mobiles accélérées (Accelerated Mobile Pages)
* CDN : réseau de diffusion de contenu (Content Delivery Network)
* 3PC : Cookies (Third-party Cookies)

| Nom du cookie | Domaine | Durée de vie | Moment d’utilisation | Détails |
| --- | --- | --- | --- | --- |
| afUserid | Le domaine de votre site web | 395 jours | non-AMP | Identifier un utilisateur dans le contexte des événements de chargement et de navigation web |
| AF\_SYNC | Le domaine de votre site web | 1 semaine | non-AMP | <ul><li>Indicateur indiquant qu’un identifiant d’utilisateur final est défini</li><li>Permet de réduire les temps de chargement du site</li></ul> |
| af\_id | appsflyer.com | 395 jours | non-AMP lorsque 3PC sont autorisés | Identifier un utilisateur dans le contexte des événements de lancement et de navigation de l’application |
| af\_id | onelink.me | 395 jours | non-AMP lorsque 3PC sont autorisés | Associer des engagements de bannières, des engagements onelink ou les deux à des événements de lancement d’application. |
| amp-afUserid | AMP CDN ou le domaine de votre site web | 1 an | Pour le service de pages par AMP |  |

</Accordion>

<div id="release-notes" />

<Accordion title="Notes de mise à jour du SDK Web">

| Date | Version | Remarques |
| --- | --- | --- |
| 2021-07-01 | 1.0 | [Ignorer les paramètres de requête](/docs/pba-web-sdk-integration-guide#discard-query-params) |
| 2021-06-01 | 1.0 | [Mettre en œuvre une stratégie de sécurité du contenu (CSP)](/docs/pba-web-sdk-integration-guide#implement-a-content-security-policy-csp-policy) |
| 31/08/2020 | 1.0 | [Ajout d’une fonctionnalité de demande de consentement](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) |
| 16/04/2020 | 1.0 | La fonction customerUserId() remplace l’événement IDENTIFY pour l’envoi du CUID unique |
| 2020-07-30 | 1.0 | <ul><li>Contrôle explicite de démarrage/d’arrêt pour l’envoi des événements</li><li>Modification de l’état initial par défaut</li></ul> |

</Accordion>

<div id="deprecations" />

<Accordion title="Dépréciations">

* Un avis d’obsolescence indique notre intention d’arrêter de prendre en charge une fonctionnalité ou une méthode. La fonctionnalité ou la méthode continue de fonctionner jusqu’à sa date d’expiration.
* Considérez les avis d’obsolescence comme une opportunité d’apporter des modifications à votre code.

| Date d’obsolescence | Avis d'échéance | Détails |
| --- | --- | --- |
| 16/04/2020 | À annoncer | **Méthode obsolète :** Envoi de l’ID utilisateur client (CUID) dans le paramètre d’événement customUserId avec le type d’événement défini sur « IDENTIFY »<br /><br />**Méthode actuelle :** Envoyez le CUID à l’aide de la fonction setCustomerUserId(). |

</Accordion>

<div data-zendesk-anchors="web-sdk-user-and-integration-guide=guide-dutilisation-et-dint%C3%A9gration-du-sdk-web h_01HFKCMH8HAW5DN4K9H1A5Q2NJ=guide-dutilisation-et-dint%C3%A9gration-du-sdk-web integrating-the-web-sdk-into-the-website=int%C3%A9gration-du-sdk-web-dans-le-site-web h_01HFKCMH8HCDNGFJEN32BNA9F2=int%C3%A9gration-du-sdk-web-dans-le-site-web h_01HFKCMH8HVTJX37PD22ZFV0AY=installation-and-integration considerations-and-actions-required=consid%C3%A9rations-et-mesures-requises h_01HFKCMH8H0JBGD2GWY127428R=consid%C3%A9rations-et-mesures-requises javascript-code-snippet=extrait-de-code-javascript h_01HFKCMH8HC064MHGH8D66QCYK=extrait-de-code-javascript to-install-the-web-sdk-without-smart-banners=pour-installer-le-sdk-web-sans-smart-banners- h_01HFKCMH8HST7G880G44WXXXB6=pour-installer-le-sdk-web-sans-smart-banners- to-implement-the-web-sdk-with-smart-banners=pour-impl%C3%A9menter-le-sdk-web-avec-smart-banners- h_01HFKCMH8HX4SQP6YCBHJH4AX5=pour-impl%C3%A9menter-le-sdk-web-avec-smart-banners- h_01HFKCMH8JMMPMHFR4399QPRJV=create-a-property-in-adobe-experience-cloud h_01HFKCMH8J8WVHP7RZ2ENHGY9V=add-the-web-sdk-to-the-adobe-launch-property h_01HFKCMH8J2MAXJ3YVHJ2AJHWQ=add-the-adobe-launch-tag-to-the-website h_01HFKCMH8JWE1Q2749N54MAYRT=publish-the-adobe-launch-environment h_01HFKCMH8JFQQG0BEQ5CATGQ2P=ensure-that-the-sdk-is-working h_01HFKCMH8JCHH5WB5XRC8029DE=sending-events-optinoptout sdk-initial-state-setting=r%C3%A9glage-de-l%C3%A9tat-initial-du-sdk h_01HFKCMH8JSJR95Y9KNANABBKR=r%C3%A9glage-de-l%C3%A9tat-initial-du-sdk explicit-control=contr%C3%B4le-explicite- h_01HFKCMH8JG2C43P8QZ0SKZCBB=contr%C3%B4le-explicite- h_01HFKCMH8J9XDX87ES4F5WW4GJ=implement-a-content-security-policy-csp-policy h_01HFKCMH8JG40DT9NHXG6TPMJ1=discard-query-params query-discard-options=options-de-rejet-de-requ%C3%AAte h_01HFKCMH8JYSV81BEY5XQRZ24Y=options-de-rejet-de-requ%C3%AAte principles-of-event-recording=principes-de-lenregistrement-des-%C3%A9v%C3%A9nements h_01HFKCMH8JZCKH1JPTGBVJ3QP4=principes-de-lenregistrement-des-%C3%A9v%C3%A9nements h_01HFKCMH8JEDEDC48AH5A2797D=conversion-and-standard-events conversion-events=%C3%A9v%C3%A9nements-de-conversion h_01HFKCMH8JYYB7HG2W8XQ7RFPD=%C3%A9v%C3%A9nements-de-conversion standard-events=%C3%A9v%C3%A9nements-standard h_01HFKCMH8JQHSJF3T8SF4ZES7W=%C3%A9v%C3%A9nements-standard recording-events=enregistrement-d%C3%A9v%C3%A9nements h_01HFKCMH8J79VD5BX96ANAYAFQ=enregistrement-d%C3%A9v%C3%A9nements h_01HFKCMH8JPJZQ81TYZX5PDF91=identifying-users-using-customer-user-id-cuid h_01HFKCMH8JYPNHJGYVRK1SZFYB=web-sdk-event-parameters h_01HFKCMH8J35YT2448PX8ZRM5P=recording-event-scenarios online-store=boutique-en-ligne h_01HFKCMH8JQS3CTE6NTZY4G8ZR=boutique-en-ligne h_01HFKCMH8J1EDH3XM5V4ECYCPS=ensuring-that-events-are-sent examples=exemples h_01HFKCMH8J4KQSZ489TMDEN426=exemples h_01HFKCMH8JAK25DZ1BZDFS4THD=recording-events::f1e16eae h_01HFKCMH8J4XNY5B9MKAS81T6Z=setting-customer-user-id-after-signup addtional-information=informations-suppl%C3%A9mentaires h_01HFKCMH8KJDZ0A15RMQ8BDMDH=informations-suppl%C3%A9mentaires h_01HFKCMH8KV3QD9CPBSVWM3EVE=web-sdk-cookies h_01HFKCMH8KGJTE7BMK4VSQJF33=release-notes h_01HFKCMH8KP1SHA21JZA5PTZXG=deprecations" />
