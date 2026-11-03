---
title: Implémenter l’OAID Android dans le SDK
metadata:
  keywords:
    - China
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2020-02-27T20:21:05Z'
  edited_at: '2024-06-13T19:08:37Z'
  id: 360006278797
  locale: fr
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/fr/articles/360006278797
---
> **En bref :** Collectez l’OAID Android pour attribuer les installations issues des app stores Android tiers.

## À propos de l’OAID

L'Open Anonymous Device Identifier (OAID) est un identifiant unique et réinitialisable par l'utilisateur conçu pour les appareils Android. Il a été introduit comme alternative par la Mobile Security Alliance (MSA), l'Institut chinois de recherche sur l'information et la communication (CICRI) et les fabricants d'appareils, pour préserver la confidentialité des ID d'appareil non réinitialisables comme le IMEI.

L'OAID est généralement utilisé pour mesurer les publicités et attribuer l'installation sur les appareils où les services Google Play ne sont pas disponibles (c'est-à-dire où l'ID publicitaire Google n'existe pas).

<span id="supported-devices"></span>L'OAID peut être lu par tous les appareils qui utilisent un SDK fourni par le MSA, ou par les appareils Huawei utilisant le principal SDK du service mobile Huawei (HMS).

## L'intégration

L'intégration de l’OAID se fait en 3 étapes :

1. Intégration d'un SDK pour générer et fournir l'OAID (soit le SDK MSA, soit le SDK Huawei HMS).
2. Intégration du module plug-in OAID AppsFlyer.
3. Intégration du SDK AppsFlyer.

**Remarque** :

* Pour les apps destinées à être utilisées en Chine, le SDK MSA doit obligatoirement être choisi.
* Pour les apps destinées à être utilisées sur des appareils Huawei dans le reste du monde, vous devez utiliser la bibliothèque Huawei HMS.

<div id="msa-sdk" />

<Accordion title="SDK MSA">

**Pour intégrer et utiliser le SDK MSA** :

1. Suivez les instructions sur le [site de la MSA](http://www.msa-alliance.cn/col.jsp?id=120) pour enregistrer votre application.
   * Après enregistrement vous pourrez télécharger le SDK.
   * Lors de la procédure d’enregistrement, vous recevez un fichier de certificat qui doit être ajouté à l'application.
2. Demandez à vos développeurs de suivre les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#msa-sdk-integration">instructions d'intégration</Anchor>.

</Accordion>

<div id="huawei-hms-sdk" />

<Accordion title="SDK Huawei HMS">

**Pour intégrer et utiliser le SDK Huawei HMS** :

* Demandez à vos développeurs de suivre les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#huawei-hms-sdk-integration">instructions d'intégration</Anchor>.

</Accordion>

## Informations supplémentaires

<div id="opting-out-of-oaid-collection" />

<Accordion title="Se désinscrire de la collecte OAID">

Une fois l' intégration OAID terminée, le SDK cherche à collecter automatiquement l'OAID. Si vous souhaitez bloquer la collecte de l'OAID pour certains utilisateurs, demandez à vos développeurs d'utiliser les éléments suivants :

<Tabs>
<Tab title="Unity">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid">setCollectOAID(false) API</Anchor> ou <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>

<Tab title="Android">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectoaid">setCollectOAID(false) API</Anchor> ou <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>
</Tabs>

<div id="setting-oaid-manually" />

<Accordion title="Définir manuellement l'OAID">

Si votre application collecte déjà l’OAID, vous pouvez ignorer l'intégration du plug-in AppsFlyer OAID et définir manuellement la valeur de l’OAID dans le SDK AppsFlyer en passant par l'<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#setting-oaid-manually">API setOaidData</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="about-oaid=%C3%A0-propos-de-loaid h_01HG8PXBZS1SN3SY3AAH1EKMNP=%C3%A0-propos-de-loaid integration=lint%C3%A9gration h_01HG8PXBZS26P9X1TQ7J4WQNF5=lint%C3%A9gration h_01HG8PXBZSM0QYQE4C9S1FBFB1=msa-sdk h_01HG8PXBZS3HP9X1AZ7HQ8C34Y=huawei-hms-sdk additional-information=informations-suppl%C3%A9mentaires h_01HG8PXBZSW5HNTTDRQ7DFFF4D=informations-suppl%C3%A9mentaires h_01HG8PXBZS8Z3MTQWFN5R6FFA8=opting-out-of-oaid-collection h_01HG8PXBZSYNS8R1PCW4YXHFBA=setting-oaid-manually" />
