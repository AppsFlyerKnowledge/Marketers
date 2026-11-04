---
title: Politique d'identification des utilisateurs d'Audiences
metadata:
  keywords:
    - IDFA
    - Audiences
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-12-23T15:39:55Z'
  edited_at: '2024-11-19T11:51:17Z'
  id: 360016791118
  locale: fr
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/fr/articles/360016791118
---
> **En bref :** Configurez votre politique d'identification d'utilisateur pour exercer un contrôle **au niveau du compte** sur les données qu'Audiences partage avec les partenaires.

<div id="about" />

## À propos

Une fois que vous avez défini une audience, AppsFlyer Audiences envoie les identifiants des membres de cette audience à vos <Anchor target="_blank" href="/marketers/fr/docs/audiences-partner-connections">partenaires publicitaires</Anchor> sélectionnés. Cela leur permet de diffuser vos publicités uniquement à ces utilisateurs.

Pour respecter les exigences de confidentialité d'iOS 14.5 et d'autres considérations de confidentialité des utilisateurs, Audiences vous offre un contrôle total pour déterminer quels identifiants sont partagés avec les partenaires :

* au niveau du compte
* au niveau des connexions partenaires

Cet article explique le processus de gestion de votre politique d'identifiant utilisateur au niveau du compte. Pour plus d'informations sur la gestion des identifiants partagés au niveau des connexions partenaires, consultez la section <Anchor target="_blank" href="/marketers/fr/docs/audiences-guide#manage-connections">Gérer les connexions</Anchor> du guide Audiences.

<div id="user-identifiers" />

## Identifiants utilisateur

Cette section décrit les identifiants qui peuvent être partagés avec les partenaires.

<div id="shared-identifiers" />

<Accordion title="Identifiants partagés">

Par défaut, Audiences partage les identifiants suivants avec les partenaires :

* **iOS :** IDFA (sur iOS 14.5 et supérieur, disponible uniquement si un utilisateur autorise le partage de cet identifiant)
* **Android : GAID**

Certains partenaires publicitaires prennent également en charge les identifiants suivants :

* Email (haché)
* Numéro de téléphone (haché)
* OAID et IMEI (tous deux pertinents uniquement pour les magasins Android autres que Google Play)

D'autres identifiants supplémentaires peuvent être utiles pour vos processus internes (tels que le CRM ou l'analyse) :

* CUID
* IDFV (uniquement valable pour iOS)

Pour plus d'informations (y compris les exigences relatives à l'utilisation d'identifiants spécifiques dans AppsFlyer), consultez le tableau des identifiants ci-dessous.

</Accordion>

<div id="identifiers-table" />

<Accordion title="Tableau des identifiants">

<table><thead><tr><th>Identifiant</th><th>Système d'exploitation</th><th>Partagé par défaut ?</th><th><p>Exigences d'utilisation<br/>Remarques<br/><br/></p></th></tr></thead><tbody><tr><td>IDFA</td><td>iOS</td><td>Voir Remarque<br/>(droite)</td><td>Par défaut, partagé uniquement pour les utilisateurs avec le <a href="./audiences-user-identifier-policy#ios">statut ATT : autorisé ou non déterminé</a> </td></tr><tr><td>GAID</td><td>Android</td><td>Oui</td><td>Aucune</td></tr><tr><td>OAID</td><td>Android<br/>(hors Google Play)</td><td>Non</td><td> <a href="./android-oaid-implementation-in-the-sdk" target="_blank">Doit être configuré</a> dans le SDK AppsFlyer</td></tr><tr><td>IMEI</td><td>Android<br/>(hors Google Play)</td><td>Non</td><td> <a href="./android-oaid-implementation-in-the-sdk" target="_blank">Doit être configuré</a> dans le SDK AppsFlyer</td></tr><tr><td>CUID</td><td>iOS<br/>Android</td><td>Non</td><td><ul><li>Généré par l'annonceur et  <a href="./customer-user-id-field-cuid" target="_blank">signalé à AppsFlyer</a>  via les API ou SDK d'AppsFlyer</li><li>Non partagé avec des partenaires publicitaires, mais peut être utile pour vos besoins internes</li><li>Sous réserve des  <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Conditions d'utilisation des identifiants supplémentaires</a> </li></ul></td></tr><tr><td>IDFV</td><td>iOS</td><td>Non</td><td><ul><li>Non partagé avec des partenaires publicitaires, mais peut être utile pour vos besoins internes</li><li>Sous réserve des  <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Conditions d'utilisation des identifiants supplémentaires</a> </li></ul></td></tr><tr><td>Email (haché)</td><td>iOS<br/>Android</td><td>Non</td><td rowspan="2"><ul><li> <a href="./audiences-configure-additional-identifiers-for-partner-audience-creation" target="_blank">Doit être configuré</a> via le <span> SDK AppsFlyer ou l'API mobile S2S </span> </li><li>Doit être chiffré avec un hachage SHA256</li><li>Sous réserve des  <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Conditions d'utilisation des identifiants supplémentaires</a> </li></ul></td></tr><tr><td>Numéro de téléphone (haché)</td><td>iOS<br/>Android</td><td>Non</td></tr></tbody></table>

</Accordion>

<div id="setting-account-level-user-identifier-policy" />

## Définition de la politique d'identification des utilisateurs au niveau du compte

La politique d'identification des utilisateurs ne peut être définie que par un utilisateur administrateur.

**Pour définir ou modifier votre politique, suivez ces étapes :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Engage** > **Audiences**.
2. Cliquez sur l'icône des paramètres (engrenage) dans le coin supérieur droit.
3. Dans la fenêtre **Politique d'identification des utilisateurs**, sélectionnez les paramètres conformes aux politiques de confidentialité de votre organisation.
   * Si vous choisissez d'autoriser le partage d'identifiants autres que IDFA, GAID, OAID et IMEI, vous devez d'abord consulter et accepter les [Conditions d'utilisation des identifiants supplémentaires.](https://support.appsflyer.com/hc/article_attachments/360017900558)
   * Si vous choisissez d'interdire les identifiants téléchargés par les connexions partenaires existantes, il vous sera demandé de confirmer que vous souhaitez arrêter de télécharger ces identifiants.
4. Cliquez sur **Enregistrer**.

Les modifications apportées à votre politique IDFA entreront en vigueur à partir de la sortie d'iOS 14.5 par Apple. Toutes les autres modifications apportées à votre politique d'identification d'utilisateur prendront effet lors du prochain téléchargement vers les partenaires.

<div id="privacy-regulations" />

## Réglementations en matière de confidentialité

Cette section décrit les réglementations sur la confidentialité qui influencent comment les identifiants utilisateurs peuvent être partagés.

<div id="ios" />

<Accordion title="iOS">

À partir de la version 14.5, iOS exige que chaque application offre à l'utilisateur une option permettant d'autoriser ou d'interdire le partage de son identifiant appareil IDFA à des fins publicitaires (App Tracking Transparency). Le fait qu'un utilisateur ait vu et répondu, ou non, à cette option (la "boîte de dialogue de consentement ATT") détermine le <Anchor target="_blank" href="/marketers/fr/docs/att-implications-ios-14-and-deprecation-of-lat">statut ATT</Anchor> de cet utilisateur.

Les options de politique d'audience pour le partage d'identifiants dans iOS sont basées sur le statut ATT le plus récent d'un utilisateur. Vos options de partage sont les suivantes :

| Option de politique utilisateur | Statut ATT correspondant |
| --- | --- |
| Ne jamais télécharger | Cet identifiant n'est pas transmis aux partenaires |
| Statut ATT : uniquement autorisé | L'identifiant est téléchargé si le statut ATT le plus récent est **authorized** ou **af\_authorized** |
| Statut ATT : autorisé ou non déterminé | L'identifiant est téléchargé si le statut ATT le plus récent est **autorisé**, **af\_authorized**, **non\_déterminé** ou **af\_unavailable**  <br />  <br />*Option par défaut pour l'IDFA, depuis le lancement d'iOS 14.5 par Apple* |
| Toujours télécharger | L'identifiant est téléchargé indépendamment du statut ATT. Assurez-vous que votre application respecte bien ses conditions d'utilisation.  <br />  <br />*Option indisponible pour IDFA* |

**Remarque :** Audiences considère le statut ATT d'un nouvel utilisateur comme **non déterminé** jusqu'à ce qu'il ait vu et répondu à la boîte de dialogue de consentement ATT.

Pour des définitions détaillées du statut ATT, voir :

* <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">Définitions du statut ATT d'Apple</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/att-implications-ios-14-and-deprecation-of-lat#valeurs-att">Définitions du statut ATT d'AppsFlyer</Anchor> (af\_authorized, af\_unavailable)

De plus, tous les utilisateurs de l'Espace économique européen (EEE) sont soumis à l'application par Google de la [loi sur les marchés numériques (DMA)](/docs/audiences-user-identifier-policy#eu-digital-markets-act).

</Accordion>

<div id="android" />

<Accordion title="Android">

Les utilisateurs Android de l'Espace économique européen (EEE) sont soumis à l'application par Google de la [loi sur les marchés numériques (DMA)](/docs/audiences-user-identifier-policy#eu-digital-markets-act).

</Accordion>

<div id="eu-digital-markets-act" />

<Accordion title="Loi sur les marchés numériques de l'UE">

Dans le cadre de l'application par Google de la loi sur les marchés numériques (DMA) le 6 mars 2024, Google met à jour sa politique de consentement des utilisateurs de l'UE. En tant que partenaire Google App Attribution, AppsFlyer apporte les modifications nécessaires pour soutenir leurs exigences politiques, tout en garantissant que les annonceurs maximisent la valeur de leurs canaux marketing Google Ads. <Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">En savoir plus</Anchor>

**Voici comment les changements affecteront les audiences :**

* **Nouveau SDK AppsFlyer**  
  Le dernier SDK AppsFlyer recueillera le consentement des utilisateurs auprès des propriétaires d'applications pour l'<Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">Espace économique européen (EEE)</Anchor> afin que leurs données puissent être partagées avec Google. Pour les audiences créées dans AppsFlyer (telles que les audiences personnalisées et suggérées), les informations de consentement collectées à partir du SDK seront automatiquement partagées avec Audiences, puis avec Google. Une fois que vous avez mis à jour vers le dernier SDK, ce processus se déroulera automatiquement.
* **Audiences connectées à Google**
  * **Consentement accordé** - AppsFlyer enverra les appareils des utilisateurs de l'EEE ayant donné leur consentement pour partager leurs informations avec Google.
  * **Consentement refusé** - AppsFlyer n'enverra pas les appareils des utilisateurs de l'EEE qui ont refusé leur consentement à partager leurs informations avec Google.
  * **Consentement inconnu** - AppsFlyer enverra les appareils des utilisateurs de l'EEE qui n'ont ni accordé ni refusé leur consentement sous le statut «Non spécifié». Il est probable que Google ne les accepte pas pour inclusion dans l'audience de son côté.  

    Pour plus de détails, consultez la <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">FAQ</Anchor> de Google.
* **Audiences existantes**  
  Tous les appareils déjà inclus dans une audience chez Google avant le 6 mars 2024 ne seront pas impactés et resteront dans l'audience. Seules les nouvelles audiences ou les nouveaux appareils EEE ajoutés à une audience existante seront téléchargés sur Google avec consentement.
* **Taille de téléchargement de l'audience**  
  Les tailles estimées et réelles de téléchargement de l'audience peuvent être affectées selon le nombre d'utilisateurs accordant ou refusant leur consentement.
* #### <span id="importing-audiences"></span>**Importer des audiences**

  * **Importer une audience standard** - AppsFlyer ajoutera les données de consentement qu'il collecte à partir du SDK AppsFlyer et supprimera les appareils non consentis ou non spécifiés avant de l'envoyer à Google.
  * **Importer une audience « telle quelle »** - Lorsque vous importez une audience « telle quelle » via <Anchor target="_blank" href="/marketers/fr/docs/audiences-import-audience-segments-from-internal-systems#import-a-csv-file">CSV</Anchor> ou <Anchor target="_blank" href="/marketers/fr/docs/audiences-import-audience-segments-from-internal-systems#use-the-import-audience-api">API</Anchor>, deux champs de consentement supplémentaires devront être ajoutés. Ces champs sont :

| Champ AppsFlyer (1) | Champ Google (2) | Valeurs | Champ expliqué |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>Personnalisation des annonces activée | personnalisation des annonces | vrai\/faux | L'utilisateur a-t-il donné son consentement à Google pour utiliser ses données à des fins de publicité personnalisée ? |
| <span id="ad_user_data"></span>données utilisateur publicitaire activées | données\_utilisateur\_publicitaire | vrai\/faux | L'utilisateur a-t-il donné son consentement pour envoyer ses données utilisateur à Google ? |

Si les champs de consentement ne sont pas renseignés avec des valeurs, ils seront envoyés à Google comme «Non spécifié».

<div id="note" />

> 📘 **Remarque**
>
> L'application par Google du Digital Markets Act (DMA) s'applique aux plateformes Android et iOS.

</Accordion>

<div data-zendesk-anchors="background=%C3%A0-propos h_01HKA2FS9VBCSV8FP8FH79H4R0=%C3%A0-propos user-identifiers=identifiants-utilisateur h_01HKA2FS9VSVJD54R14GC7G0P4=identifiants-utilisateur h_01HNZH99Z8NA9607VHSYH5XVW0=shared-identifiers h_01HKA2FS9V1KBK9BJAJ63FP6CV=identifiers-table setting-accountlevel-user-identifier-policy=d%C3%A9finition-de-la-politique-didentification-des-utilisateurs-au-niveau-du-compte h_01HKA2FS9WNGGRP3NX5NKV15SK=d%C3%A9finition-de-la-politique-didentification-des-utilisateurs-au-niveau-du-compte user-identifier-policy-options=r%C3%A9glementations-en-mati%C3%A8re-de-confidentialit%C3%A9 h_01HKA2FS9W5NSKKRK2VCZARG15=r%C3%A9glementations-en-mati%C3%A8re-de-confidentialit%C3%A9 h_01HNZJ1ET6F87AHHVQK17QHZDD=ios h_01HNZJ1ET67JQQCPYSM3H6Y9VW=android h_01HNZN8MWETDCMGWKJ0MMM8JK4=eu-digital-markets-act importing-audiences=importer-des-audiences h_01HPGV1GYT8DW0GYWTC031TNVH=importer-des-audiences h_01HNZEAJT00KKEBDPR7FD0TJNR=remarque" />
