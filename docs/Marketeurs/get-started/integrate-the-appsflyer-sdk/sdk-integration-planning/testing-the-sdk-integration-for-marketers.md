---
title: Test de l'intégration du SDK pour les spécialistes du marketing
metadata:
  keywords:
    - Testing
    - SDK
    - Advertisers
    - Debug
    - Debugging
    - redirects test
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-11-12T14:15:08Z'
  edited_at: '2024-11-06T13:56:40Z'
  id: 360001559405
  locale: fr
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/fr/articles/360001559405
---
> **En bref :** Testez l'intégration de votre application Android ou iOS avec AppsFlyer.

## Aperçu

Une fois l’intégration du SDK terminée, vous pouvez vérifier que le SDK communique correctement avec les serveurs AppsFlyer. Les spécialistes du marketing peuvent choisir entre deux méthodes de test :

* Tester à l'aide de la page **Test d'intégration SDK** qui vous permet de :
  * <Image alt="" src="https://files.readme.io/16b90e430d7beea0eaa1530130d094d590c0a202f6c6ad298a88aac9508fee7a-31828933593745.png" width="30px" /> [Afficher les événements en temps réel](#view-live-events) au fur et à mesure qu'ils se produisent dans votre application testée.
  * [Tester les installations non organiques](#test-nonorganic-installs)
  * [Tester les liens profonds (retargeting)](#test-deep-links-retargeting)
* [Testez en utilisant des liens d'attribution.](#tests-à-laide-de-liens-dattribution)

Les développeurs peuvent effectuer des tests d'intégration dans leur environnement de développement. Consultez les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integration-testing">articles sur les tests d'intégration du Dev Hub</Anchor>.

Les applications CTV peuvent également être testées, voir [Test des applications CTV](#test-de-ctv).

## Tests à l'aide de la page Tests d'intégration du SDK

Utilisez la page **Tests d'intégration SDK** pour afficher les événements en direct en temps réel, les installations et les événements in-app au fur et à mesure qu'ils se produisent dans votre application, tester les installations non organiques, les événements in-app et les liens profonds (retargeting) et identifier les problèmes d'intégration dans votre projet. Le visualiseur d'événements en direct remplace l'ancien outil de test d'événements in-app.

**iOS uniquement** : La page de test d'intégration du SDK s'applique uniquement aux applications iOS qui implémentent l'ATT. Vous pouvez tester des applications non-ATT en utilisant la procédure spécifiée [ici.](https://dev.appsflyer.com/hc/docs/testing-ios#apps-that-dont-implement-att)

### **Préparer un appareil de test**

1. Préparez un appareil (Android ou iOS) sur lequel l'application n'est pas installée. Si nécessaire, désinstallez l'application de l'appareil.
2. <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">Enregistrez l'appareil comme appareil de test.</Anchor>

### Effectuer les tests d'intégration

La page **Tests d'intégration du SDK** fournit les trois tests suivants :

<div id="view-live-events" />

<Accordion title="Voir les événements en direct">

Le visualiseur d'événements en direct est un outil de test affichant les données en temps réel envoyées depuis le SDK vers AppsFlyer, telles que les événements d'installation et d'autres événements in-app. Pour chaque événement capturé, vous pouvez voir le journal des événements et les détails.

**Pour afficher les événements dans le visualiseur d'événements en direct :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Paramètres** > **Tests d'intégration SDK**.
2. Cliquez sur **Événements en direct**.

   [altalt](https://files.readme.io/6ec1edba14e51bb27babf80d2d6f4873dbaa5113752217b4fb13399f7a1c61f1-31828925849489.png)
3. Dans la liste **App**, sélectionnez l’application que vous souhaitez tester.
4. Dans la liste **appareils de test,** sélectionnez l'appareil que vous souhaitez utiliser pour tester votre application. Si vous n'avez pas d'appareil de test, vous pouvez en enregistrer un en cliquant sur le lien **Ajouter un appareil de test**.
5. Cliquez sur **Continuer** pour commencer l'enregistrement des événements de votre application.
6. Lancez l'application et interagissez avec elle pour générer des sessions et des événements in-app.
7. Cliquez sur un élément d'événement pour afficher les détails de l'événement dans le panneau de droite.
8. Si vous souhaitez arrêter l'enregistrement des événements, cliquez sur **Arrêter**. Cliquez à nouveau sur **Démarrer** lorsque vous voulez continuer.

</Accordion>

<div id="test-nonorganic-installs" />

<Accordion title="Tester les installations non organiques">

**Pour tester les installations non organiques :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Paramètres** > **Tests d'intégration SDK**.

   [altalt](https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png)
2. Cliquez sur le test **Installations non organiques**.

   [altalt](https://files.readme.io/34440ab6d328e2d519f759f3c2a1b17dbcbee55af32b47bdbd52bb9f537c6735-31828933612177.png)
3. Dans la liste **App**, sélectionnez l’application que vous souhaitez tester.
4. Dans la liste **appareils de test,** sélectionnez l'appareil que vous souhaitez utiliser pour tester votre application. Si vous n'avez pas d'appareil de test, vous pouvez en enregistrer un en cliquant sur le lien **Ajouter un appareil de test**.
5. Si l'application testée est installée sur votre appareil de test, supprimez-la.
6. Cochez la case **J'ai supprimé l'application de l'appareil testé**.
7. Cliquez sur **Continuer** et suivez les étapes de l'assistant.

**Si l'application n'enregistre pas une installation non organique, les raisons possibles peuvent être :**

* L'IDFA est disponible mais l'appareil de test n'a pas été <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices#enregistrement-dun-appareil-de-test-ios">enregistré avec cet identifiant sur la page Appareils de test</Anchor>.
* Vous avez plus d'une app, en plus de l'application de test, installées sur l'appareil de test, mais cet appareil n'a pas été <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices#enregistrement-dun-appareil-de-test-ios">enregistré avec l'IDFV sur la page Appareils de test</Anchor>.
* Une installation organique a été enregistrée.
* Le test a été effectué sur une version de l'application qui n'inclut pas le SDK.

Pour des erreurs d'intégration, contactez votre développeur.

</Accordion>

<div id="test-deep-links-retargeting" />

<Accordion title="Tester le deep linking (retargeting)">

**Avant de commencer :**

* Lancez l'application de test au moins trois fois.
* Pour tester le deep linking (retargeting), OneLink doit être configuré pour votre application. Pour plus d'informations, consultez le <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">Guide de configuration OneLink</Anchor>.
* Vérifiez que le <Anchor target="_blank" href="/marketers/fr/docs/app-settings#reengagement-attribution">retargeting</Anchor> est activé.

**Pour tester les liens profonds :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Paramètres** > **Tests d'intégration SDK**.

   [altMoteur de clavier Maestro 2024-10-06 10.00.47.pngalt](https://support.appsflyer.com/hc/article_attachments/29754088076433)
2. Cliquez sur **Retargeting**.

   [altalt](https://files.readme.io/7c5eb6870e8d4c25a817f6c2895163b699e0a4972a6cc675b94396c386288d72-31828925858961.png)
3. Dans la liste **App**, sélectionnez l’application que vous souhaitez tester.
4. Dans la liste **appareils de test,** sélectionnez l'appareil que vous souhaitez utiliser pour tester votre application. Si vous n'avez pas d'appareil de test, vous pouvez en enregistrer un en cliquant sur le lien **Ajouter un appareil de test**.
5. Cliquez sur **Continuer** et suivez les étapes de l'assistant.

</Accordion>

## Tests à l'aide de liens d'attribution

La section suivante décrit les procédures à suivre pour tester les installations avec des liens d'attribution. Vous pouvez effectuer ces tests même si l'application est encore en attente (c'est-à-dire non répertoriée dans le Google Play Store ou l'App Store Apple).

<div id="test-install-attribution" />

<Accordion title="Attribution de l'installation test">

Les tests d'installation vous permettent de vérifier que le SDK d'AppsFlyer attribue correctement les installations à différentes sources média.

**Pour tester l'attribution des installations :**

1. Copiez le lien suivant (Android ou iOS) et effectuez ces modifications :

   1. Valeur de **app\_id** : Ajoutez votre ID d'application dans AppsFlyer.
   2. Paramètre **pid** : Indiquez le nom de la source média à laquelle l'installation est attribuée.
   3. Paramètre **c** : Indiquez le nom de la campagne.
   4. Si vous testez une application disponible via une boutique Android tierce, ajoutez le <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links">paramètre af\_r</Anchor> au lien d'attribution.
   5. Remplacez le GAID, l'IDFA ou l'IDFV par l'identifiant spécifique de votre appareil.

   <Tabs>
   <Tab title="Android">

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&advertising_id=<GAID>
   ```

   </Tab>

   <Tab title="iOS">

   IDFA

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfa=<IDFA>
   ```

   IDFV

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfv=<IDFV>
   ```

   </Tab>
   </Tabs>

   Voici des exemples de liens d'attribution avec des valeurs spécifiques :

   <Tabs>
   <Tab title="Android">

   ```

   ```

   ```http
   https://app.appsflyer.com/com.my.app?pid=Test&c=Test&advertising_id=12345f9*-eba*-421*-876*-7654ac67876*
   ```

   </Tab>

   <Tab title="iOS">

   ```

   ```

   ```http
   https://app.appsflyer.com/id123456789?pid=Test&c=Test&idfa=1A2B****-9128-4***-123*-04E***654321
   ```

   </Tab>
   </Tabs>

   > 📘 **Note**
   >
   > Si vous testez une application iOS sans <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">enregistrer un appareil de test</Anchor>, votre clic de test peut être signalé comme frauduleux par Fraud 360.
   >
   > Pour éviter que cet événement ne soit détecté comme une fraude, ajoutez le paramètre de requête suivant à votre lien : `pid=”ios_testing”`

2. Copiez votre lien mis à jour, envoyez-le à l'appareil de test, puis cliquez sur le lien.

   > 📘 **Note**
   >
   > Sous iOS, utilisez iMessage ou email pour envoyer le lien à l'appareil. Ne collez pas le lien dans l'application Notes iOS et ne cliquez pas sur le lien. Cette action peut provoquer la rupture du lien.

3. Effectuez l'une des actions suivantes :

   * Si l'application est en ligne, procédez à son installation.
   * Si l'application est en attente, le message suivant s'affiche : «*L'application que vous recherchez n'est pas encore disponible sur le marché.*» C'est le résultat attendu. Étant donné que l'application n'est pas en ligne, le lien d'attribution ne mène à aucun app store. Cependant, le lien d'attribution reste valide à des fins d'attribution et vous devez installer l'application comme suit :
     * **Pour Android :** À partir d'un fichier APK (ou Android Studio pour les développeurs)
     * **Pour iOS :** Depuis TestFlight (ou Xcode pour les développeurs)

   Vous devriez voir une installation attribuée à la campagne de test sous la source média appelée **Test**. Attendez jusqu'à 30 minutes pour que l'installation apparaisse dans le tableau de bord de l'application.

   [altLien\_d'attribution\_d'installation\_de\_testalt](https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png)

> 👍 **Conseil**
>
> Voici des manières alternatives de vérifier les résultats de vos tests :
>
> * Si vous avez accès aux rapports de données brutes, téléchargez le <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">rapport de données brutes sur les installations</Anchor>. Le téléchargement de ce rapport peut prendre plusieurs minutes. **Pour télécharger le rapport :**
>   1. Dans AppsFlyer, depuis le menu latéral, sélectionnez **Rapport** > **Exportation de données brutes.**
>   2. Dans la liste **Acquisition utilisateurs (non organique)**, cliquez sur **Installations**, puis téléchargez le rapport.
> * Si vous avez accès aux journaux de débogage, vous pouvez utiliser l'API de test d'intégration SDK  pour récupérer les résultats d'attribution pour une installation spécifique.

</Accordion>

<div id="test-inapp-events-attribution" />

<Accordion title="Tester l'attribution des événements in-app">

Le test des événements in-app vous permet de vérifier que les revenus associés à un événement sont affichés et que les événements in-app sont attribués à la source média qui a généré l'installation.

**Pour tester l'attribution des événements in-app :**

1. Lancez l’application, puis générez quelques événements in-app.
2. Ouvrez le tableau de bord de l'application et cliquez sur **Événements**.

   Vous devriez voir les événements, leurs revenus (si des revenus leur sont associés) et la source média à laquelle ils sont attribués. Prévoyez jusqu'à 60 à 70 minutes pour que les événements apparaissent dans le tableau de bord.

   ![Test_d'attribution_d'événements_in-app](https://support.appsflyer.com/hc/article_attachments/4406219144593)

**Astuce !** Pensez à télécharger le rapport de données brutes sur les événements in-app  pour vérifier que les événements sont correctement attribués. Le téléchargement de ce rapport peut prendre plusieurs minutes.

**Pour télécharger le rapport :**

1. Dans AppsFlyer, depuis le menu latéral, sélectionnez **Rapport** > **Exportation de données brutes.**
2. Dans la section **Rapports de données brutes**, téléchargez le rapport de données brutes des événements in-app.

</Accordion>

<div id="test-onelink" />

<Accordion title="Testez OneLink">

OneLink vous permet de définir un lien d'attribution unique pour Android et iOS. OneLink reconnaît l'appareil de l'utilisateur et le redirige vers l'app store approprié.

De plus, OneLink permet la création de liens profonds. Le Deep Linking vous permet d'ouvrir l'application dans une activité spécifique tout en fournissant du contenu personnalisé.

Pour plus d'informations, consultez notre guide sur le <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">test des URL OneLink</Anchor>.

</Accordion>

## Tester le retargeting à l'aide de liens d'attribution

Les sections suivantes décrivent les procédures à suivre pour tester l'attribution de retargeting.

<div id="about-retargeting-tests" />

<Accordion title="À propos des tests de retargeting">

L'attribution de retargeting se produit lorsqu'un utilisateur interagit avec une campagne de retargeting en cliquant sur un lien d'attribution de retargeting. Cela déclenche un événement de réattribution ou de réengagement. Pour plus d'informations, consultez le <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">guide d'attribution du retargeting</Anchor>.

Les tests de retargeting incluent les éléments suivants :

* [**Pour la réattribution :**](/docs/testing-the-sdk-integration-for-marketers#test-reattribution) Désinstaller et réinstaller l'application. Ensuite, vérifiez dans le tableau de bord qu'une installation a été enregistrée.
* [**Pour le réengagement :**](/docs/testing-the-sdk-integration-for-marketers#test-reengagement) Cliquez sur un lien d'attribution de retargeting ou sur un lien profond, puis vérifiez qu'un réengagement est attribué à la bonne source média.

</Accordion>

<div id="prerequisites-to-run-retargeting-tests" />

<Accordion title="Prérequis pour exécuter des tests de retargeting">

Avant de procéder à des tests de retargeting, la configuration suivante est requise :

* Le retargeting doit être activé pour l'application que vous testez.
* Créez un lien spécifique à l'application ou récupérez un lien personnalisé OneLink. Ces liens doivent inclure le paramètre de retargeting.

**Pour configurer des tests de retargeting :**

1. Activez le retargeting dans les paramètres de l'application.

   Dans le tableau de bord de l'application, cliquez sur **Paramètres de l'application** et activez **Activer l'attribution de retargeting**.

   ![Définir la fenêtre de réattribution](https://files.readme.io/1fe0c8c4add90c75237b0c5c97b6ff26d8f08ff95bd952912ef746fdec2e9f3d-31828933628561.png)
2. Effectuez l'une des actions suivantes :
   * Créez un lien d’attribution spécifique à l’application. Assurez-vous d'inclure le paramètre de retargeting, `is_retargeting=true`, et l'ID publicitaire. Pour afficher le GAID, l'IDFA ou l'IDFV, suivez les instructions <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">Enregistrement d'un appareil de test</Anchor>.    
     Voici un exemple de lien d’attribution qui inclut un paramètre spécifique à Android comme identifiant de l'appareil (GAID). Pour plus d'informations sur l'ajout d'autres paramètres d'identification de l'appareil, tels que l'IDFA ou l'IDFV, consultez <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#paramètres-spécifiques-à-ios">Structure et paramètres du lien d'attribution</Anchor>.

     ```

     ```

     ```http
     https://app.appsflyer.com/<app_id>?pid=Test&c=Test&is_retargeting=true&advertising_id=<GAID>
     ```
   * Récupérez l'<Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink">URL longue du lien personnalisé</Anchor> à partir d'un <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#procédures">modèle OneLink</Anchor>. Assurez-vous d'activer la <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">campagne de retargeting</Anchor>. L'image suivante montre un exemple d'URL longue personnalisée : ![Testing_LongLink_en-us.png](https://files.readme.io/19c706b0cc11b83a5cb08d51b3418654c6fa1e597ee7ff9e631db21c33c00b82-31828933632401.png)

Vous pouvez maintenant procéder au test de réattribution et de réengagement.

</Accordion>

<div id="test-reattribution" />

<Accordion title="Test de réattribution">

**Avant de commencer :**

* Suivez les [instructions](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) pour configurer des tests de retargeting.
* Assurez-vous que votre appareil de test n'est **pas** enregistré.

**Pour tester la réattribution :**

1. Désinstallez l'application de l'appareil. Si vous venez d'installer l'application, attendez quelques minutes.
2. Copiez le [lien d'attribution](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) que vous avez créé précédemment, soit le lien d'attribution spécifique à l'application, soit le lien long personnalisé du modèle OneLink, envoyez-le à l'appareil de test, puis cliquez sur le lien.

   > 📘 **Note**
   >
   > Sous iOS, utilisez iMessage ou email pour envoyer le lien à l'appareil. Ne collez pas le lien dans l'application Notes iOS et ne cliquez pas sur le lien. Cette action peut entraîner la rupture du lien.

3. Effectuez l'une des actions suivantes :
   * Si l'application est en ligne, procédez à son installation.
   * Si l'application est en attente, installez-la comme suit :
     * **Pour Android** : Installez depuis Android Studio ou un fichier APK.
     * **Pour iOS :** Installez depuis TestFlight.
4. Ouvrez le tableau de bord de l'application et dans la zone **Type d'affichage**, sélectionnez **Retargeting**.
5. Dans la case **Type d'attribution**, sélectionnez **Réattributions**.

   Vous devriez voir l'installation attribuée à la source média et à la campagne. Attendez jusqu'à 30 minutes pour que l'installation reciblée apparaisse dans le tableau de bord.

   [altTesting\_SDK\_Reattributionalt](https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png)

> 👍 **Conseil**
>
> Voici des manières alternatives de vérifier les résultats de vos tests :
>
> * Si vous avez accès à des rapports de données brutes, téléchargez le <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">rapport de données brutes sur les conversions</Anchor>. Le téléchargement de ce rapport peut prendre plusieurs minutes. **Pour télécharger le rapport :**
>   1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Rapport** > **Exportation de données brutes**.
>   2. Dans la liste **Retargeting**, cliquez sur **Conversions (réengagements et réattributions)**, puis téléchargez le rapport.
> * Si vous avez accès aux journaux de débogage, vous pouvez utiliser l'API de test d'intégration SDK  pour récupérer les résultats d'attribution pour une installation spécifique.

</Accordion>

<div id="test-reengagement" />

<Accordion title="Test de réengagement">

**Avant de commencer :**

* Suivez les [instructions](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) pour configurer des tests de retargeting.
* À des fins de test, définissez le temps minimum entre les conversions sur **Aucun**. Cela permet d'enregistrer et d'attribuer toutes les conversions de réengagement pendant les tests. alt
* Assurez-vous que l'application est installée sur votre appareil de test et qu'elle a été lancée plusieurs fois. Si vous venez d'installer l'application, attendez quelques minutes.

**Pour tester le réengagement (lien profond direct) :**

Assurez-vous que votre application est configurée pour les <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">liens profonds</Anchor>, puis suivez <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">cette procédure</Anchor> pour les tests.

**Pour tester le réengagement (lien profond indirect) :**

1. Copiez le [lien d'attribution](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) que vous avez créé précédemment, soit le lien d'attribution spécifique à l'application, soit le lien long personnalisé du modèle OneLink.
2. Envoyez le lien à votre appareil de test, puis cliquez sur le lien.
3. Pour ouvrir l’application, effectuez l’une des opérations suivantes :

   * Dans l'app store, cliquez sur **Ouvrir**.
   * Lancez l'application depuis votre appareil.

   Dans le tableau de bord, vous devriez voir un réengagement attribué à la source média et à la campagne. Prévoyez jusqu'à 30 minutes pour que le réengagement apparaisse.

   [altTesting\_SDK\_Re-engagementalt](https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png)

**Astuce !** Envisagez de télécharger le rapport de données brutes de conversions pour vérifier que le réengagement a été attribué à la bonne source média. Le téléchargement de ce rapport peut prendre plusieurs minutes.

**Pour télécharger le rapport :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Rapport** > **Exportation de données brutes**.
2. Dans la section **Retargeting**, téléchargez le rapport **Conversions (réengagements et réattributions)**.

</Accordion>

## Tester les installations organiques

Nous vous recommandons de commencer par tester une installation organique.

**Pour tester une installation organique :**

1. Installez l'application sur un <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">appareil de test enregistré</Anchor>.
2. Lancez l'application.

Le tableau de bord de l'application affiche une nouvelle installation organique. Prévoyez jusqu'à 30 minutes pour que l'installation apparaisse.

## Test de CTV

Les cas de test spéciaux incluent ce qui suit :

* **Android TV :** Le SDK est compatible avec les téléviseurs intelligents basés sur Android. Un spécialiste du marketing ou tout membre de l'équipe peut tester ces applications TV en suivant les procédures décrites dans cet article.
* **Apple TV (tvOS) :** Le SDK est compatible avec les Apple TV (tvOS). Un spécialiste du marketing ou tout membre de l'équipe peut tester ces applications TV en suivant les procédures décrites dans cet article.
* **Applications tvOS non publiées :** Nécessite le travail conjoint d'un spécialiste marketing et d'un développeur (voir <Anchor target="_blank" href="/marketers/fr/docs/testing-tvos-integration-before-publishing">Tester l'intégration de tvOS avant la publication</Anchor>).
* **Amazon Fire TV :** Un spécialiste marketing peut [tester l'intégration](/docs/testing-the-sdk-integration-for-marketers#testing-from-the-dashboard) en utilisant la méthode de test du SDK Android dans le tableau de bord AppsFlyer. (En savoir plus sur l'<Anchor target="_blank" href="/marketers/fr/docs/setting-up-amazon-fire-tv-ad-attribution">attribution d'Amazon Fire TV</Anchor>).
* **Événements web PBA :** Nécessite la collaboration d'un spécialiste marketing et d'un développeur (voir <Anchor target="_blank" href="/marketers/fr/docs/test-pba-web-sdk-integration">Tester l'intégration du SDK web PBA</Anchor>).

> 📄 **Voir aussi**
>
> * Test de l'intégration du réseau publicitaire <Anchor target="_blank" href="/partners/fr/docs/getting-started-onboarding-guide-for-ad-networks">Test de l'intégration du réseau publicitaire</Anchor>

<div data-zendesk-anchors="overview=aper%C3%A7u 01H88X11QS2VYFXJGC95TXC6PN=aper%C3%A7u testing-using-the-sdk-integration-tests-page=tests-%C3%A0-laide-de-la-page-tests-dint%C3%A9gration-du-sdk h_01HYX9R159XMZKMH1MBMBH9K9J=tests-%C3%A0-laide-de-la-page-tests-dint%C3%A9gration-du-sdk prepare-a-test-device=pr%C3%A9parer-un-appareil-de-test h_01J9GTS4S2RXJAMYGG6XJ5HFRZ=pr%C3%A9parer-un-appareil-de-test perform-the-integration-tests=effectuer-les-tests-dint%C3%A9gration h_01J9GTW7RAGZXE7GK5BWGBA7N5=effectuer-les-tests-dint%C3%A9gration h_01HYX9R15983XCT54TJ0VDE8DE=view-live-events h_01HYX9R15931HJEA06SY3K47W5=test-nonorganic-installs h_01HYX9R159DDNJW53AWTWT4C2Z=test-deep-links-retargeting testing-using-attribution-links=tests-%C3%A0-laide-de-liens-dattribution 01H88X11QT0WDRW5GZDCR7MZ3D=tests-%C3%A0-laide-de-liens-dattribution 01H88X11QT6YVB3TQ6JEM4G92G=test-install-attribution h_01HMDX7JMR8RMDMGS49K3DVJGG=note 01H88X11QTG2NZ3VGMQXJR7368=note-2 01H88X11QT5TY25HRTX4RD06C7=conseil 01H88X11QTRBQQ11C8SAK7DCTC=test-inapp-events-attribution 01H88X11QTJE6HNPDHBMKQMDCP=test-onelink testing-retargeting-using-attribution-links=tester-le-retargeting-%C3%A0-laide-de-liens-dattribution 01H88X11QTQ94BAJGEE1V11F6X=tester-le-retargeting-%C3%A0-laide-de-liens-dattribution 01H88X11QT4DR3WA6RGB8HDZB3=about-retargeting-tests 01H88X11QTR3AGQHN674ZYEYF7=prerequisites-to-run-retargeting-tests 01H88X11QVFQ6552C272ST108D=test-reattribution 01H88X11QVYBPJPYSPZH2HS308=note-2 01H88X11QV5YVR7HCFTGD9BEFJ=conseil-1 01H88X11QVKAG3JWRQ6KXESTQA=test-reengagement testing-organic-installs=tester-les-installations-organiques h_01HYX9R1594DD9BEZ6PMV9PJM8=tester-les-installations-organiques Testing%20CTV=test-de-ctv 01H88X11QT72F71N49G65BAEAE=test-de-ctv h_01H9FHRVKE88CXGH8G7E26ZXT2=voir-aussi" />
