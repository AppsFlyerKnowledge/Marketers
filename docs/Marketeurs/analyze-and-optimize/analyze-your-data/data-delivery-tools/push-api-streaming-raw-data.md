---
title: Flux de données brutes des API Push
metadata:
  keywords:
    - Push API
    - Real-time
    - Installation and Conversion
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:19:42Z'
  edited_at: '2023-11-20T08:40:13Z'
  id: 207034356
  locale: fr
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/fr/articles/207034356
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** transmettez en temps réel les événements d'attribution des données brutes à vos points de terminaison côté serveur.

![6970_Push_API_image.png](https://files.readme.io/0bb5747a65a6ca6ed8f55f72f189b92e780649d55b766c5d295f5602745f04f5-4405028260241.png)

## API push

L'API Push transmet à vos serveurs les données brutes générés par l'attribution AppsFlyer ainsi que l'attribution SKAdNetwork (SKAN) sous forme de messages. Vous pouvez choisir le type et le contenu des messages, et définir les points de terminaison.

Les types de messages proposés, l'actualisation des données et les champs disponibles dépendent de l'infrastructure d'attribution (i.e. AppsFlyer ou SKAdNetwork), ce qui est détaillé dans les sections suivantes.

<div id="appsflyer-attribution-messages" />

<Accordion title="Messages d'attribution AppsFlyer">

Caractéristiques du message

| Caractéristiques | Détails |
| --- | --- |
| Segmentation des types de messages | <ul><li>Vous pouvez soit segmenter les messages par point de terminaison (6 points de terminaison maximum par app), soit déterminer le type de message en fonction de la valeur des champs disponibles :<ul><li>event\_name</li><li>conversion\_type</li><li>campaign\_type</li></ul></li><li>Les valeurs des champs, selon le type de message, sont indiquées dans le tableau suivant.</li></ul>**Exemple :**<br /><br />Un message contient les éléments suivants :<ul><li>conversion\_type=install</li><li>campaign\_type=organic</li><li>event\_name=install</li></ul>Utilisez le tableau pour définir si cet événement est l'événement d'installation d'un utilisateur organique. |
| Actualisation des données | Les messages sont envoyés peu après l'enregistrement de l'événement sur la plateforme AppsFlyer. C'est en général une question de minutes. |
| Éléments du message (champs) | <ul><li>Les messages possèdent la structure `key:value`.</li><li>Consultez les champs <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#field-availability-by-reporting-tool">d'API Push</Anchor> proposés pour l'attribution AppsFlyer.</li><li>Chaque clé représente un champ de données brutes. Voir la <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#data-fields-dictionary">description des champs de données brutes dans AppsFlyer</Anchor>.</li><li>Les clés vides ou nulles ne sont jamais envoyées.</li><li>L'exemple affiche des champs à la fois null et vides. Dans la réalité les postbacks n'ont jamais de champs vides ou null. L'exemple est au format JSON.<ul><li>[iOS](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=0&single=true&output=csv)</li><li>[Android](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=233131974&single=true&output=csv)</li></ul></li></ul> |
| Format des champs horodateur | <ul><li>Horodateurs en UTC : `aaaa-mm-jj hh:mm:ss.sss`.Exemple d'affichage : `2019-09-17 00:09:00.123`. Un événement s'est produit à 18h00, heure de Tokyo. L'heure de l'événement est convertie en UTC, soit 05h00. L'heure qui est enregistrée est l'heure UTC.</li><li>Horodateur dans le fuseau horaire sélectionné (spécifique à l'app) : `yyyy-mm-dd hh:mm:ss.sss±th:tm`. Exemple : `2019-09-17 18:00:16.000+0900`. Un événement s'est produit à 18h00, heure de Tokyo. L'heure de l'événement est enregistrée ainsi : 18:00+09:00. 09:00 étant le fuseau horaire de Tokyo.</li></ul> |

#### Types de messages disponibles

<table><tbody><tr><th>Contexte d'attribution</th><th>Type de message</th><th>conversion_type field</th><th>champ campaign_type</th><th>champ event_name</th><th>event_type field</th></tr><tr><td>Acquisition des utilisateurs</td><td>Installation\*</td><td><span>sans rapport</span></td><td><p>Non organique : UA</p><p>Organique : organic</p></td><td><p>sans rapport</p></td><td><ul><li><p>sans rapport</p></li><li><p>organic-install</p></li></ul></td></tr><tr><td>Acquisition d'utilisateurs </td><td>Événements in-app d'installation</td><td><span>sans rapport</span></td><td><p>Non organique : UA</p><p>Organique : organic</p></td><td><p>Noms d'événement définis par l'annonceur</p></td><td><ul><li><p>install-in-app-event</p></li><li><p>organic-install-in-app-event</p></li></ul></td></tr><tr><td><p>Retargeting</p></td><td>RÉENGAGEMENT</td><td><span>RÉENGAGEMENT</span></td><td>retargeting</td><td>RÉENGAGEMENT</td><td><p>RÉENGAGEMENT</p></td></tr><tr><td>Retargeting </td><td>Évènements in-app de réengagement</td><td>RÉENGAGEMENT</td><td>retargeting</td><td>Noms d'événement définis par l'annonceur</td><td><p>re-engagement-in-app-event</p></td></tr><tr><td>Retargeting </td><td>Réattribution </td><td>Réinstallation</td><td>retargeting</td><td>Réattribution</td><td><p>Réattribution</p></td></tr><tr><td>Acquisition d'utilisateurs </td><td>Réinstallation</td><td>Réinstallation</td><td><p>Non organique : UA</p><p>Organique : organic</p></td><td><p>Réinstallation</p></td><td><ul><li><p>Réinstallation</p></li><li><p>organic-reinstall</p></li></ul></td></tr><tr><td>Retargeting</td><td>Évènements in-app de réattribution</td><td>Réinstallation</td><td>retargeting</td><td>Noms d'événement définis par l'annonceur</td><td><p>re-attribution-in-app-event</p></td></tr><tr><td colspan="6">\* Certaines installations relatives à l'attribution post vue sont attribuées à la <a href="./about-raw-data-identifier-restrictions" target="_blank">source média restreinte</a>. </td></tr></tbody></table>

#### Champs uniques

<table><tbody><tr><th>Nom d'affichage</th><th>Nom de l'API Push</th></tr><tr><td>Devise sélectionnée\*</td><td>selected_currency</td></tr><tr><td>Revenus dans la devise sélectionnée</td><td>revenue_in_selected_<br/> devise</td></tr><tr><td>Coût dans la devise sélectionnée</td><td>cost_in_selected_<br/> devise</td></tr><tr><td>Fuseau horaire sélectionné pour l'heure de téléchargement sur l'appareil</td><td>device_download_time_selected_timezone</td></tr><tr><td>Fuseau horaire sélectionné pour l'heure d'attribution du touch</td><td>attributed_touch_time_selected_timezone</td></tr><tr><td>Fuseau horaire sélectionné pour l'heure d'installation</td><td>install_time_selected_<br/> fuseau horaire</td></tr><tr><td>Fuseau horaire sélectionné pour l'heure d'évènement</td><td>event_time_selected_<br/> fuseau horaire</td></tr><tr><td><p>Fuseau horaire sélectionné(\*)</p></td><td>selected_timezone</td></tr></tbody><tbody><tr><td colspan="2">\* Il s'agit du paramètre au niveau de l'app qui est en vigueur au moment de l'envoi du message API.</td></tr></tbody></table>

</Accordion>

<div id="skan-attribution-messages" />

<Accordion title="Messages d'attribution SKAN">

Cette section décrit les messages (types de rapports) proposés pour SKAN et explique comment identifier les messages. Une fois que vous aurez parcouru cette section, [configurez le point de terminaison d'attribution SKAdNetwork.](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)

Lecture connexe :<Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports">champs de données brutes SKAdNetwork</Anchor>. Les messages API Push ont la même structure et les mêmes champs.

Caractéristiques du message :

| Caractéristiques | Détails |
| --- | --- |
| Segmentation des types de messages | <ul><li>Tous les messages sont envoyés au point de terminaison que vous avez défini.</li><li>Pour déterminer le type de message, utilisez les champs suivants :<ul><li>event\_name</li><li>skad\_redownload</li></ul></li><li>La valeur des champs, selon chaque type de message, est indiquée dans le tableau suivant</li></ul>Exemple :<br /><br />Un message contient les éléments suivants :<ul><li>event\_name: install</li><li>skad\_redownload: true</li></ul>Comme « skad\_redownload: true », vous déterminez qu'il s'agit d'un événement de re-téléchargement. |
| Actualisation des données | <ul><li>Installations, re-téléchargements et événements in-app :<ul><li>Traitement quotidien</li><li>Envoyé à votre point de terminaison le jour qui suit la réception du postback iOS par AppsFlyer</li><li>Les messages d'événement arrivent entre 05:00 et 08:00 UTC (l'heure exacte est fluctuante)</li><li>Exemple : des postbacks reçus le lundi seront envoyés à compter du mardi à 05:00 UTC</li></ul></li><li>Postbacks d'iOS et copie de Postbacks : les messages sont envoyés peu après leur arrivée chez AppsFlyer</li></ul> |
| Exemples de messages | La feuille de calcul contient des exemples de messages. L'exemple présenté est au format JSON. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vS0CO6W7jgx6zxMeSGIo-hbqLbFh3AO0OT6qp4cWmgdbWVMjLJ-2dermVz49jmAXexewiOGzR1YjGzu/pub?output=xlsx">Exemple de messages SKAN</Anchor>. |

#### Types de messages pour l'attribution SKAN

| Type de message | champ event\_name | champ skad\_redownload | event\_type field |
| --- | --- | --- | --- |
| Installations | sans rapport | <ul><li>Valeurs possibles : false, blank, null.</li><li>Si le champ ne figure pas dans le message, considérez sa valeur comme « false ».</li></ul> | skad-installs |
| Re-téléchargements | sans rapport | true | skad-re-downloads |
| Évènements in-app | Le nom de l'événement défini par l'annonceur | Le nom de l'événement défini par l'annonceur | skad-in-app-events |
| Postbacks provenant d'iOS | Jamais proposé dans ce message précis | Parfois proposé | skad-postbacks |
| <Anchor target="_blank" href="/marketers/fr/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">Copie des postbacks</Anchor> | Jamais proposé dans ce message précis | Parfois proposé | skad-postbacks-copy |

**Déterminer le type de message d'attribution SKAN**

**Remarque :** ne s’applique pas aux messages de copie de postbacks acheminés directement depuis iOS.

![PushAPI-2_en-us.png](https://files.readme.io/7a3ede8da87e48cc640e6e61d8f42011174122140ca63ace37c1d5c25ceadc19-20274836865809.png)

</Accordion>

## Configurer les points de terminaison API Push

> ❗️ **Attention**
>
> Vous ne devez pas utiliser l'API Push pour envoyer aux tiers des données attribuées par AppsFlyer, et ce pour les raisons suivantes :
>
> * Vous risquez de violer les règles de protection de la vie privée (comme la CCPA) si l'utilisateur a refusé que ses données soient transmises à un tiers.
> * Certaines sources média appliquent des restrictions quant à la façon dont les données de niveau utilisateur qu'elles fournissent sont utilisées ou partagées avec des tiers. Veillez à bien respecter les conditions d'utilisation de la source média.
>   Exemple : [Twitter,](https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html) [Snapchat,](https://www.snap.com/en-US/privacy/privacy-policy/) [Pinterest.](https://policy.pinterest.com/en/privacy-policy)
>
> Remarque : cette consigne ne s'applique pas aux données SKAN. Utilisez l'API Push pour envoyer des données SKAN à des points de terminaison tiers.

Pour configurer l'API Push, suivez les étapes suivantes.

#### Marche à suivre pour configurer l'API Push

<table><tbody><tr><th>Étape n°</th><th>Attribution AppsFlyer</th><th>Attribution SKAdNetwork </th></tr><tr><td>1</td><td colspan="2"><p>Si vous avez déjà un point de terminaison API Push actif, vous pouvez ignorer cette étape.</p><p>Suivez la procédure <a href="./push-api-streaming-raw-data#serverside-requirements-your-server">requise du côté du serveur</a>.</p></td></tr><tr><td>2</td><td><p>Pour l'attribution AppsFlyer, paramètrez les points de terminaison en suivant la <a href="./push-api-streaming-raw-data#push-api-planning-checklist-for-appsflyer-attribution">marche à suivre pour configurer l'API Push.</a></p></td><td><p>Ne s'applique pas</p></td></tr><tr><td>3</td><td><p><a href="./push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">Configurez le point de terminaison d'attribution AppsFlyer</a></p></td><td><p><a href="./push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint">Configurez le point de terminaison d'attribution SKAdNetwork</a></p></td></tr></tbody></table>

<div id="serverside-requirements-your-server" />

<Accordion title="Exigences côté serveur (votre serveur)">

Votre serveur doit suivre conformément les exigences suivantes :

#### Exigences côté serveur

| URL du point de terminaison | <ul><li>Nom de domaine valide</li><li>Nombre maximal de points de terminaison uniques par app :<ul><li>AppsFlyer : 6 points de terminaison</li><li>SKAdNetwork : 3 points de terminaison</li></ul></li></ul> |
| --- | --- |
| Code retour du point de terminaison | À la réception d'un message, le point de terminaison doit renvoyer un code d'état HTTP 200. |
| Liste des serveurs autorisés AppsFlyer | Allowlist AppsFlyer server <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-server-ip-address-ranges-allowlisting">Adresses IP</Anchor> des serveurs autorisés AppsFlyer dans vos pare-feux et systèmes de sécurité pour assurer la communication avec le point de terminaison. |
| Versions TLS | <ul><li>Protocole TLS 1.1</li><li>TLS 1.2+ Voir les <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-https-ssl-encryption-policy-support#outgoing-messages-appsflyer-as-client">codes pris en charge</Anchor></li></ul> |
| Ports | Ports : 80, 443 |

</Accordion>

<div id="push-api-planning-checklist-for-appsflyer-attribution" />

<Accordion title="Marche à suivre pour préparer l'API Push à l'attribution AppsFlyer">

* Suivez ces étapes pour organiser vos paramètres d'attribution AppsFlyer. Les numéros qui figurent dans l'illustration correspondent aux numéros de ligne de la marche à suivre.
* Cette section ne concerne pas l'attribution SKAdNetwork. Veuillez consulter [Configurer l'attribution SKAdNetwork.](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)

**Point de terminaison**

[![PushAPI_us-en.png](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)

#### Table de planification des points de terminaison

| Non. | Réglage | Détails | Utilisez cette colonne pour noter les paramètres réglés |
| --- | --- | --- | --- |
| 1 | Méthode | POST ou GET |  |
| 2 | URL du point de terminaison | - |  |
| 3 | Types de messages d'événement | <ul><li>Sélectionnez au moins un type de message d'événement.</li><li>Pour sélectionner des messages d'événement in-app, vous devez enregistrer un événement in-app. Tant que vous ne le faites pas, vous ne pouvez pas sélectionner de messages d'événement in-app.</li></ul>[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png) |  |
| 4 | <ul><li>Champs</li><li>La liste des champs est commune à tous les types de messages</li></ul> | **<span id="01H8E8DET2PBGQAKHJY40R1P9Z"></span>Avertissement**<br />Si vous cochez **Sélectionner tout**, les champs nouvellement ajoutés seront également sélectionnés automatiquement. Afin d'éviter tout problème, vérifiez que vous pouvez prendre en charge tous les nouveaux champs ajoutés automatiquement au schéma.<br /><br /><br /><br />Sélectionnez les champs requis.<ul><li>Les champs les plus courants sont présélectionnés par défaut.</li><li>Nous n'envoyons pas de champ vide/nul</li></ul> |  |
| 5 | Type d’événements in-app | Filtrez par événements in-app pour réduire le trafic envoyé à votre point de terminaison.<ul><li>Sélectionnez un, plusieurs ou tous les événements in-app. Attention ! Si l'événement ne s'affiche pas dans la liste, vous devez le rechercher.</li><li>Si vous sélectionnez tout, les nouveaux événements in-app sont ajoutés automatiquement.</li><li>Vous pouvez sélectionner un évènement in-app uniquement après qu'il a été enregistré au moins une fois. Si nécessaire, utilisez <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> pour déclencher l'événement.</li><li>[![mceclip1.png](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)</li></ul> |  |

</Accordion>

<div id="set-up-appsflyer-attribution-endpoint" />

<Accordion title="Configurez le point de terminaison d'attribution AppsFlyer">

**Remarque** : seuls les [propriétaires de compte](/docs/push-api-streaming-raw-data#specifications-and-limitations) AppsFlyer sont habilités à modifier les paramètres API. Les autres utilisateurs du compte peuvent quant à eux consulter les paramètres.

**Pour ajouter un point de terminaison d'attribution AppsFlyer :**

1. Rendez-vous dans **Intégration** > **Accès API.** Faites défiler jusqu'à la section API Push.
2. Cliquez sur **Ajouter un point de terminaison.**
3. Choisissez une méthode HTTP : **POST** ou **GET**
4. Saisissez l'**URL du point de terminaison**.Si vous voyez le message *cette URL n'est pas sécurisée*, contactez l'assistance AppsFlyer.
5. Sélectionnez un ou plusieurs types d'événements. **Remarque** : si les messages d'événements in-app sont désactivés, cela signifie qu'aucun événement in-app n'a encore été enregistré.
6. Sélectionnez les champs à remplir avec le message de l'API Push. Remarque :
   * Les champs obligatoires sont toujours envoyés. Ce sont les suivants : l'ID d'app, le nom de l'événement, l'heure de l'événement, l'IDFA (iOS) ou l'ID Advertising (Android)
   * Utilisez les commandes illustrées dans l'illustration suivante pour sélectionner des champs facultatifs.

     [![PushAPIFieldSelect1.jpg](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)

     * Les champs les plus courants sont présélectionnés par défaut. Vous pouvez effacer les sélections.
     * Sélectionnez les champs facultatifs selon vos besoins.
     * Utilisez **Tout effacer** pour effacer tous les champs facultatifs.
     * Nous n'envoyons pas les champs nuls/vides et la clé associée. Merci de le prendre en compte lorsque vous prévoyez vos procédures d'importation et de préparation.
7. Sélectionnez un ou plusieurs événements in-app (52 max) ou **Tous** les événements in-app.  
   * La liste est remplie par les types d'événements qui ont déjà été enregistrés. Si un événement manque, envoyez un événement de ce type à l'aide d'un périphérique de test.
8. Cliquez sur **Enregistrer**.  
   L'API Push est désormais active. Les données de conversion sont envoyées au point de terminaison.
9. Testez le point de terminaison à l'aide de la procédure suivante.

**Pour tester le point de terminaison :**

1. Cliquez sur **Envoyer le test.** Un message contenant le résultat du test s'affiche sous le bouton **Envoyer le test**.   
   Un message de test est envoyé au point de terminaison. Si le test échoue, vérifiez que les <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-server-ip-address-ranges-allowlisting">adresses IP AppsFlyer sont bien autorisées</Anchor>.**Important** ! Un compte-à-rebours, d'une durée de 2 secondes, est suivi. Si AppsFlyer ne reçoit pas de message OK dans le délai imparti, AppsFlyer considère que le message est en échec d'envoi.
2. Vérifiez que votre point de terminaison a bien reçu le message de test.  
   [Affichez une copie du message envoyé.](https://docs.google.com/spreadsheets/d/e/2PACX-1vScQf189h3Ry0BU-ejbZYkMZCJRdXXYeOwuNxPEHwY77vCVYWW9P9xCTUSJKmTvVbp_yzLidXD0WGLm/pub?gid=0&single=true&output=csv)

</Accordion>

<div id="set-up-skadnetwork-attribution-endpoint" />

<Accordion title="Configurez le point de terminaison d'attribution SKAdNetwork">

**Remarque** : seuls les [propriétaires de compte](/docs/push-api-streaming-raw-data#specifications-and-limitations) AppsFlyer sont habilités à modifier les paramètres API. Les autres utilisateurs du compte peuvent quant à eux consulter les paramètres.

**Pour ajouter un point de terminaison API Push SKAdNetwork :**

1. Rendez-vous dans **Intégration** > **Accès API.** Faites défiler jusqu'à la section API Push.
2. Sélectionnez **SKAdNetwork** comme entité d'attribution.
3. Cliquez sur **Ajouter un point de terminaison.   
   Remarque** : vous pouvez définir un seul point de terminaison SKAdNetwork par app.
4. Choisissez une méthode HTTP : **POST** ou **GET**
5. Saisissez **l'URL** **du point de terminaison**. Si vous voyez le message *cette URL n'est pas sécurisée*, contactez l'assistance AppsFlyer.
6. Nous n'envoyons pas les champs nuls/vides et la clé associée. Merci de le prendre en compte lorsque vous prévoyez vos procédures d'importation et de préparation.
7. Cliquez sur **Enregistrer**.  
   L'API Push est désormais active. Les données sont envoyées au point de terminaison.

</Accordion>

## Procédures supplémentaires - gestion des points de terminaison

<div id="change-an-endpoint" />

<Accordion title="Modifier un point de terminaison">

**Remarque** : seuls les [propriétaires de compte](/docs/push-api-streaming-raw-data#specifications-and-limitations) AppsFlyer sont habilités à modifier les paramètres API. Les autres utilisateurs du compte peuvent quant à eux consulter les paramètres.

**Pour modifier les paramètres de point de terminaison :**

1. Rendez-vous dans **Intégration** > **Accès API.** Faites défiler jusqu'à la section API Push.
2. Localisez le point de terminaison à modifier.
3. Faites les modifications.
4. Cliquez sur ***Enregistrer***.

</Accordion>

<div id="delete-an-endpoint" />

<Accordion title="Supprimer un point de terminaison">

**Remarque** : seuls les [propriétaires de compte](/docs/push-api-streaming-raw-data#specifications-and-limitations) AppsFlyer sont habilités à modifier les paramètres API. Les autres utilisateurs du compte peuvent quant à eux consulter les paramètres.

**Pour supprimer un point de terminaison** :

1. Rendez-vous dans **Intégration** > **Accès API.**  
    Faites défiler jusqu'à la section Accès API Push.
2. Cliquez sur ***Supprimer le point de terminaison.***
3. Cliquez sur **Enregistrer**.  
    Le point de terminaison est supprimé.

</Accordion>

## Dépannage, caractéristiques et seuils

<div id="test-message-fails" />

<Accordion title="Échec du message de test">

Si vous ne recevez pas le message de test et que vous limitez l'accès à vos serveurs selon les adresses IP : vérifiez que <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-server-ip-address-ranges-allowlisting">toutes les adresses IP AppsFlyer sont bien autorisées</Anchor>.

</Accordion>

<div id="duplicate-retargeting-inapp-events" />

<Accordion title="Duplication des événements in-app de retargeting">

Les événements de retargeting in-app sont dupliqués lorsqu'un événement d'achat a lieu dans le cadre d'une campagne de retargeting et sur la durée de la fenêtre de réengagement UA. Cette opération permet d'attribuer des revenus aussi bien à la source média UA qu'à la source média de retargeting.

Vous ne recevrez des événements dupliqués que si vous avez activé ces deux options :

* Événements in-app d'installation
* événements in-app de retargeting

<Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">Identifier et dédupliquer les événements in-app</Anchor>

</Accordion>

<div id="inapp-event-message-selection-is-disabled" />

<Accordion title="La sélection des messages d'événement in-app est désactivée">

[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)

* Les messages d'événement in-app peuvent être sélectionnés uniquement lorsqu'ils ont été enregistrés.
* Utilisez un appareil de test pour générer un événement in-app, ou utilisez <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">l'API S2S</Anchor> pour le faire manuellement.

</Accordion>

<div id="missing-push-messages-and-cloudfront" />

<Accordion title="Messages push et CloudFront manquants">

Vous utilisez Amazon CloudFront comme point de terminaison ? Vérifiez si CloudFront rejette le message avec le code de rejet 421. Si tel est le cas, reportez-vous à la rubrique <Anchor target="_blank" href="https://docs.aws.amazon.com/en_pv/AmazonCloudFront/latest/DeveloperGuide/cnames-https-dedicated-ip-or-sni.html">Choisir comment CloudFront sert les requêtes HTTPS</Anchor>.

</Accordion>

<div id="endpoint-error-messages" />

<Accordion title="Messages d'erreur des points de terminaison">

**Problème :** le message *cette URL n'est pas sécurisée* s'affiche lorsque vous définissez l'URL du point de terminaison.

**Action requise** : contactez l'assistance AppsFlyer ; renseignez l'ID de l'app, l'URL du point de terminaison et ajoutez une capture d'écran du message d'erreur.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| **Caractéristique** | Remarques |
| --- | --- |
| <span id="ad-networks"></span>Réseaux publicitaires | Non disponible |
| <span id="agencies"></span>Agences | Non disponible |
| <span id="appspecific-time-zone"></span>Fuseau horaire spécifique à l'app | Prise en charge |
| <span id="appspecific-currency"></span>Devise spécifique à l'app | Prise en charge |
| <span id="size-limitations"></span>Limitations de taille | Ne s'applique pas |
| <span id="organic"></span>Organique | Oui |
| <span id="nonorganic"></span>Non organique | Oui |
| <span id="data-freshness"></span>Actualisation des données | En continu |
| <span id="historical-data"></span>Données historiques | Pas de prise en charge. S'il vous manque des données, utilisez l'API Pull pour les obtenir. Dans le cadre de SKAN, vous pouvez accéder aux données historiques via Data Locker (limité par la fenêtre Data Locker Availability). |
| <span id="account-owneruser-access"></span>Accès propriétaire / utilisateur du compte | Seuls les **propriétaires de compte** AppsFlyer sont habilités à modifier les paramètres API.<ul><li>Chaque compte AppsFlyer dispose d'un propriétaire de compte **unique**. Le propriétaire est le  premier utilisateur d'AppsFlyer (celui qui a été créé au moment de l'ouverture du compte).</li></ul>Les autres utilisateurs du compte peuvent consulter les paramètres d'API Push, mais ils ne peuvent pas les modifier. |

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Comparer les outils de livraison des données brutes</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_app-app-id">Configurer l'API Push à l'aide d'une API</Anchor>

<div data-zendesk-anchors="push-api=api-push 01H89PJFBPXVKJGGH18CJBJ41W=api-push 01H89PJFBP45FQDHT4YGS58NP8=appsflyer-attribution-messages available-message-types=types-de-messages-disponibles 01H89PJFBP9DEX520BDGC5PANQ=types-de-messages-disponibles unique-fields=champs-uniques 01H89PJFBPBK09Q7CRPMM4G7PJ=champs-uniques 01H89PJFBQM4NKFSFF8XGMX9XT=skan-attribution-messages message-types-for-skan-attribution=types-de-messages-pour-lattribution-skan 01H89PJFBQBFCK5QVWW2X09H28=types-de-messages-pour-lattribution-skan set-up-push-api-endpoints=configurer-les-points-de-terminaison-api-push 01H89PJFBQZ2FW3ST5V4FW91GS=configurer-les-points-de-terminaison-api-push 01H89PJFBQ6WP7ERP0DJ69QZ1G=attention push-api-setup-checklist=marche-%C3%A0-suivre-pour-configurer-lapi-push 01H89PJFBQ625A7G3QT5HQJXMW=marche-%C3%A0-suivre-pour-configurer-lapi-push 01H89PJFBQGW8ZV76Z0HTNX2AB=serverside-requirements-your-server serverside-requirements=exigences-c%C3%B4t%C3%A9-serveur 01H89PJFBQ2BC5GHX403RD2RAT=exigences-c%C3%B4t%C3%A9-serveur 01H89PJFBQ4FXB7ABMFVHX326H=push-api-planning-checklist-for-appsflyer-attribution endpoint-planning-table=table-de-planification-des-points-de-terminaison 01H89PJFBQJXWWPQDKZ387VYX3=table-de-planification-des-points-de-terminaison 01H89PJFBQZE6KJDHXRB8GK7TF=set-up-appsflyer-attribution-endpoint 01H89PJFBQQS31C6AF245SSJ61=set-up-skadnetwork-attribution-endpoint additional-procedures%E2%80%94managing-endpoints=proc%C3%A9dures-suppl%C3%A9mentaires---gestion-des-points-de-terminaison 01H89PJFBQ7WV3NM7JR5Z9QEFB=proc%C3%A9dures-suppl%C3%A9mentaires---gestion-des-points-de-terminaison 01H89PJFBQ9RZXNHGNNYV5MP7P=change-an-endpoint 01H89PJFBQGE1WESD7ZEMBEFNE=delete-an-endpoint troubleshooting-traits-and-limitations=d%C3%A9pannage-caract%C3%A9ristiques-et-seuils 01H89PJFBQJDGT1FVHKG9DETHJ=d%C3%A9pannage-caract%C3%A9ristiques-et-seuils 01H89PJFBQAAZYF7YWKC7TP884=test-message-fails 01H89PJFBQHQJSHE09GC599AQ6=duplicate-retargeting-inapp-events 01H89PJFBRDET8T8CTAP1GW0J9=inapp-event-message-selection-is-disabled 01H89PJFBRH58FX1FTH37DP3HC=missing-push-messages-and-cloudfront 01H89PJFBR3CJSR2AEFP3HT5JE=endpoint-error-messages 01H89PJFBRZXXEMPBGBPB35MQ9=specifications-and-limitations h_01HE7SH7XFMPJ13DKCZ04RCJDD=%C3%A0-consulter-%C3%A9galement" />
