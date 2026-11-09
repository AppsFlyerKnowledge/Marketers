---
title: Test de l'intégration du SDK web de PBA
metadata:
  keywords:
    - Developers
    - PBA
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-09-01T19:09:41Z'
  edited_at: '2024-01-11T11:04:05Z'
  id: 360012729178
  locale: fr
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/fr/articles/360012729178
---
> **En bref :** Tester l'intégration du plugin PBA du SDK web.

<div id="test-pba-web-events" />

## Tester les événements web PBA

**Principes d'utilisation de la page de test**

Le SDK web envoie des événements web à la PBA, qui sont mis à disposition via les tableaux de bord PBA et les rapports de données brutes, après un traitement quotidien. Pour permettre un processus de test efficace, vous envoyez des événements de test sans attendre le traitement quotidien. Les évènements de test sont les suivants :

* Analysé et validé à la réception.
* Mis à votre disposition dans l'interface utilisateur. Cela inclut les erreurs de traitement. Si elles existent, envoyez à nouveau des événements corrigés pour vous assurer qu'elles sont traitées correctement.
* Elles sont traitées comme n'importe quel autre événement dans le cadre du traitement quotidien. Cela signifie qu'elles sont ajoutées aux tableaux de bord et aux données brutes.

<div id="web-sdk-integration-test-page" />

#### Page de test d'intégration du SDK web

<Table>
  <tbody>
    <tr>
      <td>
        <span id="page-main-view"></span>**Vue principale de la page**

        [<Image alt="TestScreen_us-en.jpg" src="https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg" width="338px" />](https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg)

        * Les événements les plus récents apparaissent en premier.
        * **Cache de l'événement** :
          * Contient jusqu'à 100 événements
          * Les anciens événements sont supprimés pour laisser la place à des événements plus récents
          * Les événements mis en cache sont supprimés après 24 heures
        * **Contrôles des pages** :
          * **Indicateur de taux de rafraîchissement**: La page est rafraîchie automatiquement toutes les 5 secondes.
          * **Tout supprimer** : Efface définitivement les événements du cache. **Attention !** Le cache est commun aux sites web partageant la même clé web dev. Ainsi, si un autre développeur utilise la page de test, celle-ci s'affichera également pour lui.
          * **Pause/démarrage** : Interrompt le rafraîchissement automatique. Les nouveaux événements ne s'affichent pas tant que vous n'avez pas cliqué sur démarrer.

        **Colonnes du tableau des événements**

        | Champ | Description |
        | --- | --- |
        | Heure (UTC) | Heure de l'évènement |
        | Type d'événement | Les types d'événements sont les suivants :<br /><br />* Événements envoyés par vous :<br />  * `EVENT`<br />  * `setCustomerUserId`<br />  * `pageLoad` : Envoyé par le SDK web à chaque fois qu'une page est chargée/réactualisée sur votre site web. |
        | Contenu de l'événement | La charge utile de l'événement, telle qu'enregistrée par PBA. |
        | Commentaires | * **Valide** : PBA a reçu et enregistré l'événement. Aucune autre action n'est requise.<br />* **Invalide** : Liste des erreurs nécessitant une action corrective. Le format du message d'erreur est le suivant :  <br />  nom du champ de l'événement : description de l'erreur<br />* Survolez les messages d'erreur pour en voir les détails :  <br /><br />  ![PBAWebSDKTestingErrorMessagesPopup_en-us.png](https://files.readme.io/0e050e60dbf9f1289880b5d58c4885d4be66392265986eaf4b2f76876697e429-360011317358.png) |
      </td>
    </tr>
    <tr>
      <td>
        **Vue en étude détaillée**[<Image alt="mceclip0.png" src="https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png" width="573px" />](https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png)

        Cliquez sur une ligne d'événement pour afficher son contenu après traitement. Pour plus d'informations, voir les <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">paramètres d'événement du SDK web</Anchor>
      </td>
    </tr>
  </tbody>
</Table>

<div id="procedures" />

## Procédures

Complétez les procédures suivantes.

<div id="enable-test-mode" />

<Accordion title="Activer le mode test">

**Conditions techniques**

Avant de procéder aux tests, <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide#installation-and-integration">le SDK web doit être mis en œuvre sur votre site web</Anchor> ou sur un site web de test.

**Limitation du navigateur**

Si le mode test est activé sur un navigateur donné, quel que soit l'onglet, le navigateur ne peut être utilisé que pour se connecter au site web spécifié et à aucun autre site web. Utiliser un autre navigateur, par exemple Safari au lieu de Chrome, pour se connecter à un autre site web à partir de la même machine.

**Pour activer le mode test :**

1. **Vérifiez que le SDK est chargé :**
   1. Dans AppsFlyer, dans le menu supérieur, sélectionnez **Mes applications** > **Voir les bundles de marques.**
   2. Sélectionnez le test d'intégration **SDK web requis.**  
      La page d'intégration s'ouvre. La clé web dev s'affiche.  

      <Image align="center" alt="pba_web_sdk_integration_test_web_dev_key_en-us.png" src="https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png" />
   3. Dans un nouvel onglet du navigateur, accédez à votre site web (sur lequel le SDK web est installé).
   4. Cliquez avec le bouton droit de la souris et sélectionnez inspecter pour ouvrir les outils de développement du navigateur.
   5. Allez dans l'onglet **Console.**
   6. Dans la console, entrez :  

      ```javascript
      window.AF_SDK.initPluginsConfig.pba.webAppId
      ```

      Le webAppID s'affiche.

      <Image align="center" alt="testing_pba_integration_webappid_check_en-us.png" src="https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png" />
   7. Vérifiez que l'identifiant webAppID est identique à la clé web dev dans la page de **test d'intégration du SDK web.**
2. **Activer le mode test** :
   1. Dans l'onglet du navigateur du site web, allez à l'onglet **Console.**
   2. Saisissez :

      ```javascript
      window.AF_SDK.PLUGINS.PBA.turnOnDevMode()
      ```

      La fonction renvoie `undefined`.

      <Image align="center" alt="testing_pba_integration_turnondevmode.png" src="https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png" />
3. **Vérifiez que le mode test est activé :**
   * Dans l'onglet **Console**, appuyez sur Entrée :  

     ```javascript
     window.AF_SDK.PLUGINS.PBA.isDevModeOn()
     ```

     La valeur de retour est `true`. Ceci indique que le mode test est actif.   
     <Image align="center" alt="PBATestingWebSDKIntegrationIsDevModeOn_en-us.png" src="https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png" />

</Accordion>

<div id="send-test-events" />

<Accordion title="Envoyer des événements de test">

* En mode test, les événements que vous envoyez sont affichés dans la page d'intégration des tests.
* Attention ! Les événements de test sont traités et seront ensuite inclus dans les rapports PBA. Pour éviter de fausser les rapports, remplissez `eventRevenue` avec des valeurs faibles (petites). Si aucune valeur n'est envoyée, PBA remplit le champ avec 0.

Envoyez des exemples d'événements pour chacun des types décrits.

| Étape | Action<br /><br />(Saisir les commandes) | Page d'intégration des tests du SDK web<br /><br />(Résultat attendu) |
| --- | --- | --- |
| 1 | Ouvrez un nouvel onglet dans le navigateur et accédez à n'importe quelle page de votre site web. | PBA enregistre un événement `'pageLoad'` chaque fois que votre site web s'ouvre/se rafraîchit :<br /><br />[<Image alt="PBATestingWebSDKPageLoadEvent_en-us.png" src="https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png" width="226px" />](https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png) |
| 2 | Connectez-vous/enregistrez-vous sur votre site web en tant qu'utilisateur <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">pour déclencher un événement setCustomerUserId.</Anchor> | [<Image alt="mceclip3.png" src="https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png" width="226px" />](https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png) |
| 3 | <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide#recording-event-scenarios">Commencez à envoyer des événements web</Anchor> pour vérifier que PBA les traite correctement.<br /><br />**Remarque** :<br /><br />Si elles ne sont pas spécifiées, `eventRevenue` et `eventRevenueCurrency` sont remplies avec des valeurs par défaut :<ul><li>`eventRevenueCurrency: "USD"`</li><li>`eventRevenue: 0`</li></ul>[<Image alt="PBAWebSDKTestEventEVENT_en-us.png" src="https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png" width="233px" />](https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png)<br /><br />Voir les <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">paramètres d'événement du SDK web pour plus de détails</Anchor>. | [<Image alt="mceclip5.png" src="https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png" width="226px" />](https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png) |

</Accordion>

<div id="troubleshooting" />

## Dépannage

<div id="events-do-not-display-in-the-test-page" />

<Accordion title="Les événements ne s'affichent pas sur la page de test">

1. Dans les outils de développement du navigateur, allez dans l'onglet Réseau.
2. Dans le champ du filtre, entrez "websdk".
3. En fonction du code de réponse HTTP, procédez comme suit :
   * 200 : Contactez le support technique d'AppsFlyer.
   * 400 : Vérifiez que tous les paramètres sont entourés de " ".

</Accordion>

<div data-zendesk-anchors="test-pba-web-events=tester-les-%C3%A9v%C3%A9nements-web-pba h_01HKW32BE04AKHFMY853211C1A=tester-les-%C3%A9v%C3%A9nements-web-pba web-sdk-integration-test-page=page-de-test-dint%C3%A9gration-du-sdk-web h_01HKW32BE0Z2ZKTBHSCSWVT04N=page-de-test-dint%C3%A9gration-du-sdk-web procedures=proc%C3%A9dures h_01HKW32BE0VA0X9ZX4Z26EY6CZ=proc%C3%A9dures h_01HKW32BE08Z9CCMBPK4Z0854C=enable-test-mode h_01HKW32BE0E4A1W221FKY97EZB=send-test-events troubleshooting=d%C3%A9pannage h_01HKW32BE1HFV0NM64QMASBCCT=d%C3%A9pannage h_01HKW32BE1QHV0W6ZDYHG94RQA=events-do-not-display-in-the-test-page" />
