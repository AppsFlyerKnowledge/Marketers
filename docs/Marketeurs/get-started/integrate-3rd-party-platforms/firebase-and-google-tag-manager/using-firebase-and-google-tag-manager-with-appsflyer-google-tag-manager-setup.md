---
title: >-
  Utilisation de Firebase et de Google Tag Manager avec AppsFlyer—Configuration
  de Google Tag Manager
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:28:45Z'
  edited_at: '2024-09-20T13:48:41Z'
  id: 4410481509393
  locale: fr
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/fr/articles/4410481509393
---
> **En bref :** Instructions pour configurer l'envoi d'événements signalés via le SDK Firebase à AppsFlyer dans Google Tag Manager.

<div id="google-tag-manager-setup" />

## Configuration de Google Tag Manager

Cette section décrit la configuration nécessaire dans l'interface utilisateur de Google Tag Manager (GTM). Toutes les étapes décrites dans cette section sont nécessaires pour que GTM puisse envoyer des événements à AppsFlyer. Suivez les étapes dans l’ordre indiqué.

Les étapes suivantes concernent Google Tag Manager pour les applications mobiles. Si votre interface Google Tag Manager diffère des captures d'écran présentées dans les différentes étapes, vérifiez les points suivants :

1. Votre conteneur Google Tag Manager est configuré pour les applications mobiles.
2. Le conteneur est en version 5. Pour plus d'informations, cliquez <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7003315">ici</Anchor>.

<div id="note" />

> 📘 **Remarque**
>
> Les étapes décrites dans cette section concernent un événement d'achat, mais elles sont pertinentes pour tout événement que vous souhaitez envoyer.

<div id="1-creating-event-parameter-variables" />

<Accordion title="1. Création de variables de paramètres d'événement">

Les variables de paramètres d'événements permettent à Google Tag Manager d'obtenir des données à partir de l'événement. Lorsque l'événement est envoyé, les variables ID AppsFlyer et Dev Key sont transmises avec. Google Tag Manager évalue ensuite leur valeur et c'est ainsi qu'il les obtient. Les données de l'événement ont deux fonctions :

1. Fournir à Google Tag Manager l'ID AppsFlyer et la clé de développement
2. Fournir à Google Tag Manager le nom et les paramètres de l'événement

<Tabs>
<Tab title="ID de l'appareil AppsFlyer et clé de développement">

Chaque fois que Google Tag Manager envoie un événement à AppsFlyer, il doit être accompagné de l'ID AppsFlyer et de la clé de développement. La clé de développement permet à Google Tag Manager de communiquer avec les serveurs AppsFlyer. L'ID AppsFlyer permet à AppsFlyer de savoir à quel utilisateur attribuer l'événement.

1. Dans Google Tag Manager, cliquez sur ***Variables*** puis sur ***Nouveau***.
2. Nommez la variable « AppsFlyer Dev Key » et cliquez sur ***Configuration des variables***
3. Choisissez ***Paramètre d'événement***
4. Choisissez ***Paramètre personnalisé***
5. Dans le champ ***Paramètre d'événement*** , saisissez « dev\_key » et enregistrez
6. Répétez le processus pour l'ID AppsFlyer également : nommez la variable « AppsFlyer Device ID » et saisissez « af\_id » dans le champ ***Paramètre d'événement***

<div id="note-1" />

> 📄 **Exemple**
>
> Vous trouverez ci-dessous une capture d'écran de l'interface utilisateur de GTM. Elle montre la configuration finale du paramètre d'événement :
>
> ![event_parameter_variable_dev_key.png](https://files.readme.io/f5030ce110ec4459f673a4088c2c09a4e3f90a35976f4fbfccb8750cb112e69e-49839295695889.png)

<div id="important" />

> 🚧 **Important !**
>
> Pour iOS, un paramètre d'événement supplémentaire doit être configuré. Suivez le même flux qu'indiqué ci-dessus. Créez une variable et nommez-la « Apple App ID ». Dans le champ Paramètre d'événement, saisissez « apple\_app\_id » et enregistrez.

L'étape suivante consiste à créer et définir les variables AppsFlyer ID et Dev Key dans l'application. Cette étape est expliquée dans la section <Anchor target="_blank" href="/marketers/fr/docs/using-firebase-and-google-tag-manager-with-appsflyer-sending-installs-and-events#configurer-des-événements-dans-lapp">Envoi d'événements</Anchor>.

</Tab>

<Tab title="Chiffre d'affaires et prix">

La plupart des événements intégrés nécessitent des paramètres de valeur d'événement. Dans ce cas, il s'agit des paramètres af\_revenue et af\_price, mais vous pouvez envoyer n'importe quel paramètre d'événement. Maintenant que l'événement est configuré dans l'application, les variables de revenu et de prix doivent être créées dans Google Tag Manager. Ces variables sont utilisées ultérieurement dans la balise d'événement d'achat.

1. Dans Google Tag Manager, créez deux variables de paramètres d'événement pour af\_revenue et af\_price.
2. Pour « af\_revenue », nommez la variable « Revenu » et définissez la clé de paramètre d'événement sur « af\_revenue »
3. Pour « af\_price », nommez la variable « Prix » et définissez la clé de paramètre d'événement sur « af\_price »

<div id="note-2" />

> 📄 **Exemple**
>
> Vous trouverez ci-dessous une capture d'écran de l'interface utilisateur de GTM. Elle montre la configuration finale du paramètre d'événement :
>
> ![event_parameter_variable_revenue.png](https://files.readme.io/40e6ccd8d2df9370210847d6ff54a5a44c04f295dac9ece18dac715e5fc335a1-49839295696657.png)

<div id="note-3" />

> 📘 **Remarque**
>
> L'exemple suivant montre comment créer des variables de paramètres d'événement pour les paramètres Revenu et Prix. Vous pouvez créer des variables de paramètres d'événement pour tout type de paramètre d'événement, en fonction de l'événement envoyé.

</Tab>
</Tabs>

</Accordion>

<div id="2-creating-a-trigger-for-the-purchase-event" />

<Accordion title="2. Créer un déclencheur pour l'événement d'achat">

Pour que Google Tag Manager sache si l'événement doit être envoyé à AppsFlyer, vous devez configurer un déclencheur pour cet événement.

1. Dans Google Tag Manager, cliquez sur ***Déclencheurs*** , puis sur ***Nouveau***.
2. Nommez le déclencheur « Achat » et cliquez sur ***Configuration du déclencheur***.
3. Choisissez ***Personnalisé***.
4. Sélectionnez ***Certains événements***.
5. Dans les conditions, définissez le déclencheur pour qu'il s'active lorsque le ***nom de l'événement*** est égal à « af\_purchase ».
6. Cliquez sur ***Enregistrer***.

<div id="note-4" />

> 📄 **Exemple**
>
> Vous trouverez ci-dessous une capture d'écran de l'interface utilisateur de GTM. Voici la configuration finale du déclencheur :
>
> ![trigger_purchase_event.png](https://files.readme.io/ef2e70fb2aa0b25f1243d6fa565e3cdb1df407fd2d4b3105dee412ccad7f2704-49839256428689.png)

</Accordion>

<div id="3-creating-a-tag-for-the-purchase-event" />

<Accordion title="3. Créer une balise pour l'événement d'achat">

Maintenant que les variables requises et le déclencheur de l'événement sont définis, vous pouvez créer la balise « Achat ».

1. Dans Google Tag Manager, cliquez sur ***Balises*** , puis sur ***Nouveau***.
2. Nommez la balise « Achat » et cliquez sur ***Configuration de la balise***.
3. Choisissez ***AppsFlyer***.
4. Dans le champ ***ID d'application*** , définissez la variable intégrée ID d'application.

   <div id="important-1" />

   > 🚧 **Important !**
   >
   > Pour iOS, définissez la variable personnalisée « apple\_app\_id » dans le champ ***ID d'application*** .

5. Dans le champ ***Clé de développement*** , choisissez la variable « AppsFlyer Dev Key ».
6. Dans le champ ***ID de l'appareil AppsFlyer*** , choisissez la variable « AppsFlyer Device ID ».
7. Dans le champ Nom de l'événement, définissez la variable intégrée ***Nom de l'événement***.
8. Dans le champ ***Devise de l'événement*** , définissez votre code de devise, par exemple USD.
9. Cliquez deux fois sur ***Ajouter une valeur d'événement***.
10. Définissez les éléments suivants :  
    ***Clé*** : af\_revenue, ***Valeur*** : choisissez la variable de paramètre d'événement « Revenue ».  
    ***Clé*** : af\_price, ***Valeur*** : choisissez la variable de paramètre d'événement « Prix ».
11. Dans la section ***Déclenchement***, définissez le ***Déclencheur de déclenchement***sur le déclencheur d'événement « Achat ».
12. Cliquez sur ***Enregistrer***.

<div id="note-5" />

> 📄 **Exemple**
>
> Vous trouverez ci-dessous une capture d'écran de l'interface utilisateur de GTM. Voici la configuration finale de la balise :
>
> ![purchase_tag.png](https://files.readme.io/893bdf6ce65bf6bd0435f4e7c02ff044b35e5e14ebea131f547040f763d7512d-49839295697169.png)

</Accordion>

<div id="4-publishing-the-tag-manager-container" />

<Accordion title="4. Publication du conteneur dans Google Tag Manager">

Après chaque modification dans Google Tag Manager (ajout de balises, etc.), vous devez télécharger le conteneur et l'ajouter au dossier racine de votre application :

* Android - app/src/main/assets/containers
* iOS - dossier racine/conteneur

Créez et installez l'application sur un appareil de test et vérifiez le journal de débogage pour voir si l'événement est déclenché et envoyé.

</Accordion>

<div data-zendesk-anchors="google-tag-manager-setup=configuration-de-google-tag-manager h_01HE7SFG97FKSVAY5QHVHGF3GV=configuration-de-google-tag-manager h_01HE7SFG97RP20KAEYDJMM460D=remarque h_01HE7SFG97YVYNT385MNFA9ECN=1-creating-event-parameter-variables h_01HE7SFG97NDENJQH63J8M8CDK=exemple h_01HE7SFG97GYZP68YKW93Y0VFR=important- h_01HE7SFG97WY50DX10ATM7Z31Y=exemple-2 h_01HE7SFG97E6Z7FEJET53T4CKR=remarque h_01HE7SFG98XGBMTA7ZF8XSNF29=2-creating-a-trigger-for-the-purchase-event h_01HE7SFG98CRQE99PJ3CEHWM0E=exemple-3 h_01HE7SFG98R4DGTRWXE247MRPK=3-creating-a-tag-for-the-purchase-event h_01HE7SFG98DWKMETHSP0M15GW8=important--1 h_01HE7SFG986JJKFKDZQCR6JKMQ=exemple-3 h_01HE7SFG98R2KGRRDA9TQTYD3B=4-publishing-the-tag-manager-container" />
