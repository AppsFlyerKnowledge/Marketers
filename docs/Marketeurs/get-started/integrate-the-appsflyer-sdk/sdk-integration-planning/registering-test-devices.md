---
title: 'Enregistrer les appareils de test '
metadata:
  keywords:
    - whitelisting
    - Testing
    - device
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-03-10T08:19:35Z'
  edited_at: '2023-11-30T11:59:05Z'
  id: 207031996
  locale: fr
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/fr/articles/207031996
---
> **En bref :** lors des tests d'attribution, enregistrez votre appareil de test pour vous assurer que chaque installation est enregistrée en tant que nouvelle installation. Un appareil de test enregistré empêche les installations d'être enregistrées comme des réinstallations.

<div id="why-register-a-test-device" />

## Pourquoi enregistrer un appareil de test ?

Lors des tests d'attribution, la fenêtre de réattribution limite les attributions d'installation à une par fenêtre de 90 jours. Ainsi, si vous utilisez plusieurs fois le même appareil pour tester les attributions d'installation, rien n'est enregistré. Un appareil de test enregistré empêche les installations d'être enregistrées comme des réinstallations.

<div id="methods-for-registering-a-test-device" />

## Méthodes d'enregistrement d'un appareil de test

Pour enregistrer un appareil de test, vous devez sélectionner le système d'exploitation de l'appareil (Android, iOS ou Windows) et ajouter l'identifiant de ce dernier.

Vous pouvez utiliser l'une des méthodes suivantes pour enregistrer votre appareil :

* [Téléchargez et installez l'app My Device ID by AppsFlyer](#register-a-device-using-the-appsflyer-device-id-app-admin-only) : une fois que vous avez installé l'app sur l'appareil de test, vous pouvez automatiquement enregistrer l'appareil et partager les détails de son ID avec votre compte AppsFlyer. L'appareil sera automatiquement répertorié sur la page **Dispositifs de test**.

  > 📘 **Note**
  >
  > Dans les appareils de test iOS 14+, vous pouvez utiliser cette méthode d'enregistrement uniquement si la fonction AppTransparency Tracking (ATT) a été mise en place sur votre app et que vous souhaitez effectuer des tests en tant qu'utilisateur consentant. Si ce n'est pas le cas, utilisez la méthode manuelle.

* [Ajoutez manuellement l'appareil de test](#register-a-device-manually) : tout utilisateur d'un compte peut enregistrer directement un appareil de test en ajoutant l'identifiant de l'appareil à la page **Appareils de test**.

Remarques :

* Les appareils de test enregistrés sont utilisables par toutes les apps qui appartiennent au compte.
* Les ad networks doivent demander à l'annonceur d'ajouter des appareils ; les agences peuvent ajouter elles-mêmes leurs propres appareils.

<div id="supported-device-identifiers" />

<Accordion title="Identifiants d'appareil pris en charge">

Les identifiants des appareils sont les suivants :

* **Android :** AID (GAID ou OAID), IMEI, ID Android

  > 📘 **Note**
  >
  > Lorsque vous enregistrez un appareil de test, vous ne devez ajouter les IMEI ou ID Android que dans le cas où votre application collecte et utilise ces identifiants.

* **iOS :** IDFA, IDFV
* **Windows Phone :** ID publicitaire Windows

</Accordion>

<div id="android::7db075c7" />

<div id="ios::41efa11e" />

<div id="windows::6c6af14b" />

<div id="ios::80f176b3" />

<div id="android::db8cc168" />

<div id="windows" />

<div id="ios" />

<div id="android" />

<div id="managing-test-device-registration" />

## Gestion de l'enregistrement des appareils de test

<div id="register-a-device-using-the-appsflyer-device-id-app-admin-only" />

<Accordion title="Enregistrer un appareil à l'aide de l'application AppsFlyer device ID">

**Pour télécharger l'app AppsFlyer ID d'appareil :**

1. Téléchargez et installez l'app en utilisant le code QR (Google Play store) ou l'un des liens fournis.  

   <Tabs>
   <Tab title="Android">

   <Image align="center" alt="" src="https://support.appsflyer.com/hc/article_attachments/360005641117" width="233px" />

   **Liens :** [Google Play](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid&hl=en) et [marché hors magasin](https://apkpure.com/my-device-id-by-appsflyer/com.appsflyer.android.deviceid)

   </Tab>

   <Tab title="iOS">

   <Image align="center" alt="" src="https://support.appsflyer.com/hc/article_attachments/360001988157" width="233px" />

   </Tab>

   <Tab title="Windows">

   <Image align="center" alt="" src="https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png" width="233px" />

   </Tab>
   </Tabs>

2. Pour autoriser la collecte de l'IDFA sur un appareil iOS 14.5+, appuyez sur **Autoriser** lorsque l'invitation ATT s'affiche.

   <Image align="center" alt="" src="https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png" />
3. Sur l'écran Android/iOS/Windows, touchez **Enregistrer** pour enregistrer l'appareil.

   <Tabs>
   <Tab title="Android">

   <Image align="center" alt="" src="https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png" />

   </Tab>

   <Tab title="iOS">

   <Image align="center" alt="" src="https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png" />

   </Tab>

   <Tab title="Windows">

   <Image align="center" alt="" src="https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg" />

   </Tab>
   </Tabs>

4. Saisissez vos identifiants de connexion AppsFlyer. L'appareil est maintenant enregistré.
5. Appuyez sur **Partager** les détails pour partager les informations d'ID d'appareil.

</Accordion>

<div id="register-a-device-manually" />

<Accordion title="Enregistrer un appareil manuellement">

Les utilisateurs du compte peuvent enregistrer manuellement un appareil des façons suivantes :

1. Dans AppsFlyer, en haut à droite, cliquez sur votre adresse e-mail.
2. Sélectionnez **Tester** **les appareils**.
3. Cliquez sur **+ Ajouter un appareil.**

   <Image align="center" alt="" src="https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png" />
4. Renseignez les paramètres suivants :
   * **Nom (caractères latins uniquement) :** entrez un nom d'identification pour l'appareil.
   * **OS :** sélectionnez un système d'exploitation.
   * **Type d'identifiant d'appareil :** sélectionnez un identifiant d'appareil.
   * **ID de l'appareil :** fournissez l'ID de l'appareil en fonction du système d'exploitation :

     <Tabs>
     <Tab title="iOS">

     Comment obtenir les identifiants de IDFA ou de IDFV :

     * **IDFA :** installez l'application AppsFlyer device ID sur votre appareil de test. Pour savoir comment, cf [Ajouter un appareil](#register-a-device-manually) à l'aide de l'application AppsFlyer device ID (admin uniquement) ci-dessus.
     * **IDFV :** demandez à votre développeur d'installer l'application de l'outil de test IDFV sur votre appareil de test. Une fois installée et lancée, l'application de l'outil affichera l'IDFV. **Remarque :** L'outil de test peut être installé une fois que le développeur a effectué les étapes préliminaires dans X-Code.

     Pour savoir quand utiliser IDFA ou IDFV, voir [Enregistrer un appareil de test iOS.](#enregistrement-dun-appareil-de-test-ios)

     </Tab>

     <Tab title="Android">

     Récupérez les identifiants en utilisant l'app AppsFlyer Device ID, ou en entrant les codes dans l'appareil :

     | Identifiant | Méthode de récupération | Google Play | Autre |
     | --- | --- | --- | --- |
     | AID (GAID ou OAID) | Utilisez l'app [AppsFlyer Device ID](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid). | Obligatoire | Permet d'enregistrer l'appareil |
     | imei | *#06#* | Ne s'applique pas | Permet d'enregistrer l'appareil |
     | ID Android | *#*#8255#*#*  (peut ne pas fonctionner sur les appareils les plus récents) | Ne s'applique pas | Permet d'enregistrer l'appareil |

     </Tab>

     <Tab title="Windows">

     **Windows Ad ID** [Obtenir l'identifiant publicitaire de Windows](https://www.microsoft.com/en-us/p/my-ad-device-id/9nn69nbsj9xw?activetab=pivot:overviewtab)

     </Tab>
     </Tabs>

5. Cliquez sur **Enregistrer**. L'appareil s'affiche désormais dans la liste des appareils enregistrés. **Remarque :** Bien que l'appareil soit immédiatement visible dans la liste des appareils enregistrés, il peut prendre quelques minutes pour s'enregistrer dans le système et fonctionner comme prévu.

> 📘 **Note**
>
> **Ajout de plusieurs identifiants**
>
> Il peut arriver que vous souhaitiez ajouter plus d'un identifiant à votre appareil de test, par exemple, à la fois IDFA et IDFV sur le même appareil.
>
> **Pour ajouter un identifiant supplémentaire :**
>
> 1. Cliquez sur **Ajouter un appareil.**
> 2. Utilisez le même nom pour l'appareil de test et ajoutez le 2e identifiant.
> 3. Cliquez sur **Enregistrer**.

</Accordion>

<div id="unregister-a-device" />

<Accordion title="Annuler l'enregistrement d'un appareil">

Un maximum de 200 appareils par compte peut être enregistré. Seul l'admin est habilité à supprimer des appareils de test.

**Pour supprimer un appareil de la liste :**

1. Dans AppsFlyer, en haut à droite, cliquez sur votre adresse e-mail.
2. Sélectionnez **Tester** **les appareils**.
3. Cliquez sur l'icône de suppression pour supprimer les appareils.

</Accordion>

<div id="registering-an-ios-test-device" />

## Enregistrement d'un appareil de test iOS

L'organigramme ci-dessous illustre différentes étapes possibles lors de l'enregistrement de vos appareils de test iOS.

<Image align="center" alt="" src="https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png" />

Sélectionnez l'une des options suivantes lors de l'enregistrement de votre appareil de test iOS :

<div id="register-your-testing-device-with-idfa" />

<Accordion title="Enregistrez votre appareil de test avec l'IDFA">

<div id="when-to-use-idfa-for-test-device-registration" />

#### **Quand utiliser l'IDFA pour l'enregistrement d'un appareil de test ?**

Enregistrez l'IDFA si la fonction AppTransparency Tracking (ATT) a été mise en place sur votre app et que vous souhaitez effectuer des tests en tant qu'utilisateur consentant. Lorsque vous lancez l'app pour la première fois, pensez à cliquer sur **Autoriser** lorsque la fenêtre de demande d'ATT s'affiche.

<div id="how-to-register-your-test-device-with-an-idfa" />

#### **Comment enregistrer votre appareil de test avec l'IDFA ?**

Pour obtenir votre IDFA, enregistrez un appareil à l'aide de l'application AppsFlyer device ID.

</Accordion>

<div id="register-your-testing-device-with-idfv" />

<Accordion title="Enregistrez votre appareil de test avec l'IDFV">

<div id="when-to-use-idfv-for-test-device-registration" />

#### **Quand utiliser l'IDFV pour l'enregistrement d'un appareil de test ?**

Lorsque l'IDFA n'est pas accessible, l'IDFV est votre seule option. Dans les scénarios suivants, vous **devez utiliser l'IDFV**:

* **La fonction ATT a été implémentée** et vous souhaitez exécuter des tests en tant qu'utilisateur sans consentement. Lorsque vous lancez l'app pour la première fois, cliquez sur **Refuser** lorsque l'invitation ATT s'affiche.
* **La fonction ATT n'a pas été implémentée.**

<div id="how-to-register-your-device-with-idfv" />

#### **Comment enregistrer votre appareil de test avec l'IDFV**

1. Avant de pouvoir enregistrer l'appareil de test avec l'IDFV, demandez à votre développeur d'installer l'application de l'outil de test IDFV sur votre appareil de test. Pour les instructions destinées aux développeurs, vous pouvez vous référer à <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-the-idfv-test-tool-app">cet article</Anchor>.
2. Une fois que votre développeur a installé l'outil de test IDFV, lancez-le et copiez l'IDFV affiché.
3. [Enregistrez le dispositif de test manuellement](#register-a-device-manually) à l'aide de l'IDFV.

> 📘 **Note**
>
> **Pourquoi installer l'application de l'outil de test IDFV ?**
>
> * L'outil de test IDFV est utilisé pour extraire l'IDFV dont vous avez besoin pour enregistrer l'appareil de test.
> * Si aucune autre application appartenant à votre compte de développeur n'est installée sur votre appareil de test. Dans ce cas, iOS attribue un nouvel ID de vendeur chaque fois que vous réinstallez l'application. Étant donné que le test implique dans de nombreux cas la réinstallation de l'application, chaque réinstallation déclenche la réinitialisation de l'IDFV par iOS. **L'application utilitaire, en prétendant appartenir au vendeur, empêche iOS de créer un nouvel IDFV chaque fois que l'application est réinstallée sur l'appareil de test.**

</Accordion>

<div id="dont-register-a-testing-device" />

<Accordion title="Ne pas enregistrer un dispositif de test">

Utilisez cette option si vous ne pouvez pas enregistrer un appareil de test avec l'IDFA ou l'IDFV. Dans ce cas, la modélisation probabiliste est utilisée pour l'attribution. Chaque installation est enregistrée comme une nouvelle installation sur l'appareil de test. Cette méthode permet d'enregistrer une succession d'installations test sur un même appareil si au moins l'une des conditions suivantes s'applique :

* Le SDK iOS AppsFlyer est en version 6.8.0 ou inférieure.
* La détection des réinstallations est désactivée pour l'app (non recommandé pour les apps actives).
* Le lien d’attribution du test contient « is\_retargeting=true ». Dans ce cas, les installations sont enregistrées en tant que réattributions et apparaissent dans le tableau de bord de retargeting ainsi que les rapports de données brutes de retargeting.

</Accordion>

<div data-zendesk-anchors="why-register-a-testing-device=pourquoi-enregistrer-un-appareil-de-test- 01H7W9EA7RQDB69QS339XFHAFZ=pourquoi-enregistrer-un-appareil-de-test- methods-for-registering-a-testing-device=m%C3%A9thodes-denregistrement-dun-appareil-de-test 01H7W9EA7RRRJBFSXW3KY53R9K=m%C3%A9thodes-denregistrement-dun-appareil-de-test 01H7W9EA7RTTQ1FHZZ6GBGV0WP=note 01H7W9EA7RWWNACKSEETMCP90W=supported-device-identifiers 01H7W9EA7R9A8KCNRD0BTPPQTH=note-1 managing-testingdevice-registration=gestion-de-lenregistrement-des-appareils-de-test 01H7W9EA7R7SJVVQCST3WA6YBM=gestion-de-lenregistrement-des-appareils-de-test h_01H6V7FQFF10E4C82ZQ97PEEZA=register-a-device-using-the-appsflyer-device-id-app-admin-only h_01H6V7GM8KKXF8VS5ZRA4NV592=register-a-device-manually 01H7W9EA7R190M9DH7GPY1VJ77=note-2 01H7W9EA7R0KGH3YXZ9SMAFESZ=unregister-a-device registering-an-ios-testing-device=enregistrement-dun-appareil-de-test-ios h_01H6S2AKDH181MBDFGPBP1BQPV=enregistrement-dun-appareil-de-test-ios 01H7W9EA7SPA47GR1X0S9WZKDH=register-your-testing-device-with-idfa when-to-use-idfa-for-testing-device-registration=quand-utiliser-lidfa-pour-lenregistrement-dun-appareil-de-test 01H7W9EA7SRD5V5134H2BRZ2AF=quand-utiliser-lidfa-pour-lenregistrement-dun-appareil-de-test how-to-register-your-testing-device-with-an-idfa=comment-enregistrer-votre-appareil-de-test-avec-lidfa 01H7W9EA7SBBCAP3Y24FFCCGJW=comment-enregistrer-votre-appareil-de-test-avec-lidfa 01H7W9EA7SNZ3ER02MBV8VJGH3=register-your-testing-device-with-idfv when-to-use-idfv-for-testing-device-registration=quand-utiliser-lidfv-pour-lenregistrement-dun-appareil-de-test 01H7W9EA7S3103TSHSH4XHTP1R=quand-utiliser-lidfv-pour-lenregistrement-dun-appareil-de-test how-to-register-your-device-with-idfv=comment-enregistrer-votre-appareil-de-test-avec-lidfv 01H7W9EA7SGTDQCRVJKKRH0EVT=comment-enregistrer-votre-appareil-de-test-avec-lidfv 01H7W9EA7SHVSDPJN8P2WBSFN1=note-3 01H7W9EA7S3KJ89AN9ZBMHFGRR=dont-register-a-testing-device" />
