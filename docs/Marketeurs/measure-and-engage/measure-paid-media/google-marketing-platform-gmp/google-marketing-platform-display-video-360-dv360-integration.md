---
title: Google Marketing Platform - Intégration de Display & Video 360 (DV360)
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-02-02T17:40:13Z'
  edited_at: '2024-08-13T14:57:37Z'
  id: 360017595598
  locale: fr
  section: Google Marketing Platform (GMP)
  section_id: 6551212604305
  url: https://support.appsflyer.com/hc/fr/articles/360017595598
---
> **En bref :** Google Marketing Platform - Display & Video 360 (GMP-DV360) est un partenaire du réseau self-reporting (SRN) d'AppsFlyer qui mêle la publicité et les analyses. L'intégration de GMP-DV360 (dv360\_int) offre la publicité et l’analyse pour améliorer la relation clientèle, obtenir des informations précieuses et booster les performances marketing.

> 🚧 **Attention !**
>
> Voir le bulletin sur la <Anchor target="_blank" href="/marketers/fr/docs/bulletin-supporting-the-new-google-eu-consent-policy">prise en charge de la nouvelle politique de consentement Google dans l'UE</Anchor>.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png" width="121px" />

## Présentation

L'intégration GMP-DV360 utilise les ID de lien pour la mesurer les conversions. Vous pouvez travailler avec GMP-DV360 soit directement, soit via une agence, soit les deux, avec les intégrations suivantes :

* [DV360 pour les annonceurs](#configuration-de-gmp-dv360-pour-les-annonceurs) : à compléter une fois (obligatoire)
* [DV360 pour les agences](#mettre-en-place-gmp-dv360-pour-les-agences) : facultatif pour chaque agence

> 📘 **Remarque**
>
> * L'intégration GMP-DV360 est conçue pour remplacer l'intégration héritée de GMP DV360/CM (doubleclick\_int), qui est obsolète depuis la fin du deuxième trimestre 2024.
> * Pour utiliser l'API, contactez votre gestionnaire de compte GMP-DV360.

Le tableau ci-dessous décrit les solutions d’intégration GMP :

| Solution GMP | Description | Actions nécessaires à l'intégration |
| --- | --- | --- |
| DV360 | Intégrer DV360 à AppsFlyer pour mesurer l'attribution dv360\_int | Compléter l'[intégration de l'annonceur](#configuration-de-gmp-dv360-pour-les-annonceurs) |
| CM360 & DV360 | Acheter du trafic DV360 via CM360, mesuré comme attribution dv360\_int dans AppsFlyer. | Compléter l'[intégration de l'annonceur](#configuration-de-gmp-dv360-pour-les-annonceurs) |
| CM360 et source média tierce non DV360 | Acheter le trafic des sources média tierces et mesurer les conversions d'app mobile issues de ce trafic dans CM360. | <Anchor target="_blank" href="/marketers/fr/docs/gmp-use-case-of-traffic-measurement-from-3rd-parties-in-cmp360">Mesurer le trafic tiers avec CM360</Anchor> |

### Partager les données entre AppsFlyer et GMP - DV360

**Données fournies par AppsFlyer :** AppsFlyer envoie à GMP-DV360 des postbacks sur les conversions et événements in-app.

**Données transmises à AppsFlyer :** Lorsque GMP-DV360 revendique une conversion, il fournit à AppsFlyer les paramètres de la source média. Ces paramètres permettent d’alimenter les analyses et rapports de données brutes. Le tableau ci-dessous indique les paramètres de mappage pour GMP-DV360 et AppsFlyer.

| GMP | AppsFlyer |
| --- | --- |
| interaction type | attributed\_touch\_type |
| timestamp | attributed\_touch\_time |
| line\_item\_id | campaign\_id |
| line\_item\_name | campaign\_name |
| creative\_id | ad\_id |
| product\_type | af\_channel |
| external\_customer\_id | network\_account\_id |
| site\_id | af\_siteid |

## Configuration de GMP-DV360 pour les annonceurs

**Conditions techniques**

Avant de configurer l'intégration, vous devrez :

* <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">Contacter le partenaire</Anchor> pour ouvrir un compte chez lui.
* <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/10956727">Obtenir l'ID du lien GMP-DV360</Anchor>.

**Pour activer ou modifier l'intégration :**

1. Activation :** dans AppsFlyer, dans le menu latéral, choisissez **Collaboration**** > Partenaire Marketplace.  
   **Modification :** Dans AppsFlyer, dans le menu latéral, choisissez **Collaborer** > **Intégrations actives**.
2. Lancez une reccherche et sélectionnez **Google Marketing Platform - Display & Video 360 (DV360)**.
3. Cliquez sur Configurer l'intégration. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l'onglet Integration, sélectionnez l'app à intégrer et cochez l’option **Activer le partenaire**.  
   **Remarque : La case doit rester cochée (activée) tant que vous collaborez avec le partenaire./strong>**
5. Terminez la configuration pour chacun des onglets détaillés ci-après.

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

Lorsque AppsFlyer interroge GMP-DV360, il renvoie les paramètres contenus dans sa réponse. Ceux-ci sont mappés aux paramètres AppsFlyer ainsi qu’aux données brutes, comme l’indique le tableau ci-dessous.

| GMP - paramètre hérité | Paramètre GMP-DV360 | Paramètre AppsFlyer | Paramètre URL |
| --- | --- | --- | --- |
| ID de placement | Nom de l'élément de ligne | Nom de la campagne | c |
| ID de placement | ID de l'élément de ligne | ID de campagne | af\_c\_id |
| ID de site | ID de site | ID de site | af\_siteid |
| ID de création | ID de création | ID publicitaire | af\_ad\_id |

<span id="activate-partner::e4f2f638"></span>L'onglet **Integration** comprend un certain nombre de sections, détaillées ci-dessous.

#### Activer le partenaire

Pour configurer l'intégration, vous devez d'abord **déclencher** l’option<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation#activating-a-partner">Activer le partenaire</Anchor>. En savoir plus sur **l'activation et la désactivation des intégrations des partenaires.**

#### Paramètres généraux

**ID de lien :** Saisissez l'ID de lien indiqué dans les conditions techniques.

**Utilisateurs hors UE : Faites le choix d'activer ou non lesUtilisateurs hors UE/strong>**.

<Image alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="536px" />

#### Attribution des installations

Définissez les différentes fenêtres d'attribution pour attribuer les nouvelles installations (premiers lancements) des utilisateurs qui ont consulté, ou cliqué sur, votre publicité. Elles correspondent au temps maximum entre le moment du clic/de l'affichage, et celui de l'installation. Seules les installations effectuées au cours de la fenêtre rétrospective peuvent être attribuées à Google Marketing Platform - Display & Video 360 (DV360).

1. Définissez la **Fenêtre rétrospective post-clic d'installation** sur 1-23 heures ou 1-30 jours.
2. [Facultatif] Activez **l'attribution après affichage de l'installation** et définissez la fenêtre de rétrospection sur 1 à 23 heures ou 1 à 30 jours.

#### Attribution du ré-engagement

Définissez les différentes fenêtres d'attribution pour attribuer les réengagements des utilisateurs existants qui ont soit consulté, soit cliqué sur votre publicité. Notez que seules les ré-engagements réalisés dans la fenêtre rétrospective peuvent être attribués à GMP-DV360.

1. Définissez la **Fenêtre rétrospective post-clic de ré-engagement** sur 1-23 heures ou 1-30 jours.
2. [Facultatif] Activez **l'attribution post-vue de ré-engagement** et définissez la fenêtre rétrospective sur 1 à 23 heures ou 1 à 7 jours.

Pour en savoir plus sur les <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide#reengagement-rules-and-windows">règles et fenêtres du ré-engagement</Anchor>.

#### Fenêtre de ré-engagement

Définissez la fenêtre pendant laquelle les événements in-app sont d’abord attribués à la conversion de ré-engagement <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide#setup-reengagement-window">En savoir plus</Anchor>.

* Définissez la **fenêtre de ré-engagement** sur 1 à 23 heures, 1 à 90 jours ou **lifetime**.

#### Ignorer les utilisateurs actifs pour le retargeting

Définissez la période pendant laquelle les <Anchor target="_blank" href="/marketers/fr/docs/set-retargeting-inactivity-window#période-dinactivité">ré-engagements et réattributions</Anchor> des utilisateurs qui ont lancé votre application seront ignorés. Ce qui signifie que leur activité durant la fenêtre ne sera pas enregistrée dans AppsFlyer.

> 📘 **Remarque**
>
> Les conversions de ré-engagement et de réattribution des utilisateurs qui étaient **inactifs** pendant la période définie **seront par contre enregistrées**.

1. Activez **Ignorer les utilisateurs actifs pour le retargeting**.
2. Définissez la fenêtre d'inactivité.

#### Postbacks d'évènements in-app

Configurer le mappage des événements in-app avec les événements GMP-DV360 envoyés via postback :

1. Activez les**Postbacks d'événement in-app.**
2. Cliquez sur **Ajouter un événement** pour ajouter à la liste un SDK ou un événement de serveur à serveur. Le tableau suivant vous explique comment remplir les champs :  

| Nom du paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis des événements de serveur à serveur.<br />**Conseil** : Vous ne voyez pas s'afficher un certain événement ?<ul><li>veillez à activer l'évènement sur un appareil avec une installation non-organique et vérifiez à nouveau.</li><li>Saisissez l’événement dans la rubrique **Evénement AppsFlyer** puis cliquez sur **Créer un événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor></li></ul> |
| **mappé à l’événement partenaire** | Le nom ou l'identifiant unique de chaque événement, tel que défini du côté du partenaire. Les différentes configurations du mappage sont :<ul><li>**Liste déroulante :** sélectionnez l’événement AppsFlyer prédéfini le plus adapté.</li><li>**PERSONNALISATION :** lorsque vous sélectionnez cette option, AppsFlyer envoie l'événement tel qu'il apparaît dans le champ **événement AppsFlyer** .</li></ul>**Remarque :**<ul><li>Il est recommandé de sélectionner un événement standard dans la liste. Cependant, dans le cas de plusieurs événements PERSONNALISÉS, mieux vaut les définir de manière unique, par exemple PERSO\_1 et PERSO\_2. Cela vous aidera à repérer les événements dans DV360/CM360.</li><li>Les événements AppsFlyer (comme `af_purchase`, etc.) sont toujours envoyés avec leurs `u` variables, par exemple `u24=`. Cela vous permet de les identifier dans CM360, même lorsqu'ils sont envoyés en tant qu’événement personnalisé.</li><li>CM360 autorise un maximum de 10 événements en tout, qui peuvent être des événements personnalisés ou standard.</li></ul> |
| **pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<ul><li>**Ce partenaire uniquement** (par défaut): envoie des postbacks uniquement lorsque cet événement est attribué à GMP-DV360.</li><li>**Toutes les sources média, y compris les sources organiques** : envoie des postbacks pour les événements attribués à n’importe quel partenaire, ainsi que pour les événements organiques.</li></ul> |
| **Y compris** | <ul><li>**Pas de valeur et pas de revenu** (par défaut) : envoie uniquement l'événement, sans aucune de ses valeurs.</li><li>**Valeurs et pas de revenus** : envoie tous les paramètres **à l'exception** de la valeur du revenu.</li><li>**Valeurs et revenus :** envoie tous les paramètres de l’événement, **y compris** la valeur du revenu (si présente dans l’événement).</li></ul> |

3. [Facultatif] Cliquez sur **Ajouter une condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/adc9e4826101d528a07ea04b88c323030258dcf891d9ba419baed60e662cdda1-22715359959697.png" width="30px" />icônepour <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#postbacks-conditionnels-dévénements-in-app">définir les conditions</Anchor> d'un événement.
4. Cliquez sur **Enregistrer l'intégration**.
5. [Facultatif] Une fois l'intégration enregistrée, restez sur la page de configuration pour intégrer plus d'apps avec GMP-DV360 :
   1. En haut à gauche, sous le nom du partenaire, cliquez sur le nom de l’app pour ouvrir la liste des apps.
   2. Sélectionnez une nouvelle app dans la liste déroulante.
   3. Répétez les différentes étapes d’intégration pour l’app sélectionnée.

> 📘 **Remarque**
>
> Pour les apps iOS uniquement : le contrôle que vous avez sur les données partagées avec le partenaire via les postbacks et <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">rapports</Anchor> dépend de **l'état d’activation de la Confidentialité avancée** (pour iOS 14.5 et +).

#### Mappage des paramètres U

AppsFlyer prend en charge l'envoi de paramètres supplémentaires (paramètres U), avec pour maximum u26. Les paramètres U sont pré-mappés et définis du côté d'AppsFlyer. Remarques importantes :

* Étant donné que ces paramètres sont pré-mappés, aucun paramètre U personnalisé supplémentaire ne peut être configuré.
* Si des données viennent à manquer pour un paramètre U, alors AppsFlyer ne les enverra pas. Exemple : si les données de l'opérateur sont manquantes, AppsFlyer n'envoie pas U5.

| Paramètre U | Nom | Exemple de valeur |
| --- | --- | --- |
| u1= | ID d'appareil af | 1540995037437-2811776739500410055 |
| u2= | ID utilisateur du client | eaf8a5f2.1836.4686 |
| u3= | **Android** :  <br />ID publicitaire  <br />**iOS** : idfa | 9d9d03ab-f211-4e17-994e-d0afdf23ac01 |
| u4= | wifi | true |
| u5= | fournisseur | Jio%204G |
| u6= | code pays | IN |
| u7= | Région | HR |
| u8= | ville | Gurgaon |
| u9= | type d'appareil | motorola::Moto G (4) |
| u10= | version de l’OS | 7 |
| u11= | version du SDK | v4.8.18 |
| u12= | version de l'app | 3.31.1 |
| u13= | heure de l'installation | 1540995041 |
| u14= | heure du clic | 1546441586 |
| u15= | heure d'impression | 1546441586 |
| u16= | nom de la campagne* | Appinstall\_campaign |
| u17= | ID de campagne | 12345ABC |
| u18= | nom d'adset* | Appinstall\_adset |
| u19= | ID d'adset | 12345ABC |
| u20= | nom de la publicité* | Appinstall\_ad |
| u21= | ID publicitaire | 1234567ABCDE |
| u22= | id de site | site\_id\_123456 |
| u23= | heure de l'évènement | 2019-01-04 12:56:35.707 |
| u24= | nom de l'événement | af\_purchase |
| u25= | valeur de l'événement | `{"af_price":459,"af_content_id":"77147","af_revenue":4.59,"af_currency":"EUR"}` |
| u26= | devise | EUR |

* Si AppsFlyer ne reçoit pas ce nom de paramètre dans la réponse de GMP-DV360, le champ est rempli avec l'ID correspondant. Par exemple, le nom de l'adset affichera l'ID de l'adset, qui est `12345ABC`.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Il est possible d'**utiliser les liens d'attribution d'AppsFlyer avec DV360 pour les impressions et l'enregistrement de clic uniquement**. Ces liens ne sont PAS utilisés pour l'attribution et toute information supplémentaire qu'ils contiennent n'est pas analysée ou utilisée à quelque fin que ce soit.

Si vous souhaitez pouvoir mesurer le nombre de clics provenant de DVM360 sur AppsFlyer, vous devez ajouter une URL d'attribution AppsFlyer à votre tableau de bord DVM360. Assurez-vous (si possible) que le nom de la campagne dans l'URL d'attribution **est identique** à l'ID d'emplacement sur GMP, et ce afin qu'AppsFlyer puisse récupérer et ajouter les données de clic aux campagnes appropriées.

> 🚧 **Important !**
>
> L'utilisation des liens d'attribution pour **DV360**n'est pas obligatoire.

**Si vous souhaitez comptabiliser les clics dans AppsFlyer, utilisez ce lien :**

```http
https://app.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=${UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

Si vous voulez compter les **impressions** dans AppsFlyer, utilisez ce lien :

```http
https://impression.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=%24{UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="Onglet Coût (pour les coûts, clics et impressions)">

Les données de coût ne sont pas prises en charge avec cette intégration.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Les revenus publicitaires ne sont pas pris en charge avec cette intégration.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Définissez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">les autorisations à accorder à</Anchor> Google Marketing Platform - Display & Video 360 (DV360).

</Accordion>

## Mettre en place GMP-DV360 pour les agences

Les agences peuvent mener des campagnes avec GMP-DV360 en votre nom.

#### Configuration de l'agence

| Procédure réalisée par | Marche à suivre |
| --- | --- |
| Annonceur | <ol><li>Vérifiez que vous avez bien complété l’intégration de l’annonceur GMP-DV360.</li><li>Dans AppsFlyer, dans le menu latéral, choisissez Collaborer > **Intégrations actives**.</li><li>Sélectionnez une agence.</li><li>Allez dans l'onglet **Autorisations** et cliquez sur **Autorisations de l'agence.**</li><li>[Obligatoire] Dans l'onglet Integration, activez **Postbacks d'évènement in-app**. **Cela permettra à l'agence d'activer ou désactiver les postbacks de son côté.**</li></ol> |
| Agence | <ol><li>Dans AppsFlyer, dans le menu latéral, choisissez Collaborer > **Intégrations actives**.</li><li>Sélectionnez **Google Marketing Platform - Display & Video 360 (DV360).**</li><li>Ouvrez l'onglet **Intégration**.<br />Le statut de l'intégration avec GMP s'affiche.</li></ol>[![mceclip2.png](https://files.readme.io/153226084274c9e2bf0c5cfdca65f7d36076a2020c605e21177c8c71613b69f6-360017196637.png)](https://files.readme.io/153226084274c9e2bf0c5cfdca65f7d36076a2020c605e21177c8c71613b69f6-360017196637.png)<ol><li>Vérifiez que l’option **Activer le partenaire** est cochée. Si ce n’est pas encore fait, l’annonceur doit compléter [l’intégration de l’annonceur GMP-DV360.](#configuration-de-gmp-dv360-pour-les-annonceurs)</li><li>Vérifiez que les paramètres restants, comme les fenêtres rétrospectives et le mappage des événements in-app, sont corrects. Demandez à l'annonceur d'apporter les modifications nécessaires en cas de besoin.</li><li>Saisissez un ou plusieurs **ID d’annonceur DBM**. L'ID se trouve dans votre <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/3423704?hl=en&ref_topic=9133452">tableau de bord GMP.</Anchor></li><li>Cliquez sur **Enregistrer**.</li></ol> |

## Écarts de résultats dans GMP-DV360

Découvrez ce qui peut provoquer des inexactitudes dans les résultats, et comment les éviter :

| Cause | Description | Conseil AppsFlyer |
| --- | --- | --- |
| Fenêtre d'attribution post-vue | La fenêtre d'attribution post-vue de GMP-DV360 est de 14 jours, alors que chez AppsFlyer elle est de 1 jour par défaut. | Définissez la fenêtre post vue dans AppsFlyer pour qu'elle corresponde à celle définie dans la fenêtre de configuration de GMP-DV360. |
| Mappage incorrect | Le mappage entre AppsFlyer et GMP-DV360 n'est pas bon | <ul><li>Vérifiez l'ID du lien</li><li>Vérifiez que les événements in-app sont correctement mappés</li></ul> |

<div data-zendesk-anchors="h_01HMEH8VW3PYCZ6GC4T5BYBS3V=attention- overview=pr%C3%A9sentation 01H8E4ZJNRMXY183TQCPW15ZQB=pr%C3%A9sentation 01H8DYEV7JPV80T3YAJQQHBA6C=remarque data-sharing-between-appsflyer-and-gmp=partager-les-donn%C3%A9es-entre-appsflyer-et-gmp---dv360 h_01HQ0QJJRMYP3E6B5FVA0V6861=partager-les-donn%C3%A9es-entre-appsflyer-et-gmp---dv360 advertiser-gmp-integration=configuration-de-gmp-dv360-pour-les-annonceurs 01H8DYEV7KYNB2FJG7N1CTEE86=configuration-de-gmp-dv360-pour-les-annonceurs h_01HPYMRJ1WVVKCHKKEA6WD0XZP=integration-tab 01H8VVCC8G0KR4AA2HD9S8QBKD=activer-le-partenaire general-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux 01H8VVCC8GSDPSNN0AJPVZPR8P=param%C3%A8tres-g%C3%A9n%C3%A9raux install-attribution=attribution-des-installations 01H8VVCC8GK8VFPBEPAMVHCAWM=attribution-des-installations reengagement-attribution=attribution-du-r%C3%A9-engagement 01H8VVCC8HHG5290PYF0BT29QA=attribution-du-r%C3%A9-engagement reengagement-window=fen%C3%AAtre-de-r%C3%A9-engagement h_01HQ06JCJZD6AMFR2B6GTMSM9S=fen%C3%AAtre-de-r%C3%A9-engagement ignore-active-users-for-retargeting=ignorer-les-utilisateurs-actifs-pour-le-retargeting h_01HNWSTJZPFQVQ5C8M0JA1J0T5=ignorer-les-utilisateurs-actifs-pour-le-retargeting h_01HMXNJVHK9C3FT8E04RE0TH99=remarque-1 inapp-event-postbacks=postbacks-d%C3%A9v%C3%A8nements-in-app 01H8VVCC8HHZRFQ2T1X478YZMP=postbacks-d%C3%A9v%C3%A8nements-in-app 01H8VVCC8HDMTY1P2SG31HD61K=remarque-2 parameter-mapping=mappage-des-param%C3%A8tres-u h_01HBBJQZSTT1HFENXNACMHFC18=mappage-des-param%C3%A8tres-u 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab h_01HBBJQZSW45X3SM92H4FS94HM=important- 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab 01H8VVCC8HAG0XVWE2T9PRDHTK=permissions-tab setting-up-gmp-dv360-for-agencies=mettre-en-place-gmp-dv360-pour-les-agences 01H8VVCC8HVNNQ9PJS4ZQCVDNS=mettre-en-place-gmp-dv360-pour-les-agences agency-setup=configuration-de-lagence 01H8DYEV7MNFFY9ESFF2S3ETEB=configuration-de-lagence gmp-discrepancies=%C3%A9carts-de-r%C3%A9sultats-dans-gmp-dv360 01H8DYEV7MTPJMY12AVHX45YFF=%C3%A9carts-de-r%C3%A9sultats-dans-gmp-dv360" />
