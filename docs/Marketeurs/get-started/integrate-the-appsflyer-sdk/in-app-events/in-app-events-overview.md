---
title: 'Les événements in-app riches : aperçu'
metadata:
  keywords:
    - ios
    - Rich
    - In-App
    - android
    - Advertisers
    - In app events
    - Marketers
    - inapp events
    - attribution
    - inapp
    - inapp events attribution
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-11-02T08:12:51Z'
  edited_at: '2023-11-15T13:04:44Z'
  id: 115005544169
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/115005544169
---
> **En bref :** enregistrez les événements in-app riches post-installation (tels que la connexion, l'inscription ou l'achat in-app) attribués aux sources média et aux campagnes.

## Pourquoi enregistrer des évènements in-app ?

Les événements in-app donnent un aperçu de ce qui se passe dans votre app et constituent l'outil idéal pour déterminer la valeur des utilisateurs de l'app et la **qualité du trafic en provenance de différentes sources média**. L'enregistrement des évènements in-app vous permet de mesurer les KPI tels que le ROI (retour sur investissement) et la LTV (lifetime value, durée de vie).

Lorsque vos utilisateurs valident une inscription, complètent un tutoriel, ajoutent un article au panier ou font des achats, les données d’évènements in-app peuvent alors enregistrer les évènements accompagnés de leurs détails. L'implémentation d'événements in-app est obligatoire à toutes les fins d'analyse post-installation.

## À propos des événements in-app

Un événement in-app comprend un nom d'événement et peut inclure des paramètres d'événement. Lorsque vous ajoutez des paramètres d'événement à un événement in-app, ce dernier devient un événement in-app riche. Les paramètres d'événement vous fournissent plus de contexte et d'informations sur l'événement en cours. Par exemple, en plus de savoir qu'un utilisateur a effectué une réservation, les paramètres d'événement vous donnent accès à des détails tels que le type d'achat, la destination et les revenus.

![travel.png](https://files.readme.io/0ebe64e7aa3ccc40ef014c55ee3a91edf678e21b2d00a7f8be1298d6b494e925-30858351609617.png)

> 👍 **Astuce**
>
> Voulez-vous en savoir plus sur les évènements in-app ? Suivez cette <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7774/play/18613/in-app-events-and-integrated-partners-part-1">formation éclaire</Anchor> sur le portail d'apprentissage AppsFlyer.

<div id="predefined-and-custom-events" />

<Accordion title="Événements prédéfinis et personnalisés">

Pour pouvoir envoyer les événements in-app de votre choix, votre développeur doit implémenter du code dans votre app. Les noms et les paramètres d'événement sont classés comme suit :

* **Prédéfinis** : ce sont des noms d'événement et des paramètres d'événement couramment utilisés parmi différentes apps. Nous vous recommandons fortement d'utiliser des <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-event-structure#noms-dévénements-prédéfinis">noms d'événement</Anchor> et des <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-event-structure#paramètres-dévénements-prédéfinis">paramètres d'événement</Anchor> prédéfinis autant que possible pour les raisons suivantes :
  * Les noms prédéfinis permettent de mapper automatiquement les événements aux partenaires.
  * Si AppsFlyer décide de modifier le nom ou le paramètre d'un évènement, votre implémentation est rétrocompatible.
* **Personnalisés :** il s'agit de noms d'événements et de paramètres que vous définissez pour des scénarios utilisateur spécifiques qui se produisent dans votre app. Vous pouvez utiliser n'importe quel nom d'événement ou chaîne de nom de paramètre personnalisée, mais n'oubliez pas que les événements personnalisés doivent être gérés par votre développeur. Voir [Conseils](/docs/in-app-events-overview#tips) et [Limitations](/docs/in-app-events-overview#limitations).

</Accordion>

<div id="revenue-events" />

<Accordion title="Évènements générateurs de revenus">

Chaque fois que vous envoyez des événements in-app, par exemple un achat ou une réservation de vol, vous envoyez également les revenus associés. Le seul paramètre qui génère des revenus dans les événements in-app est`af_revenue`

* <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#record-revenue">Enregistrement des revenus dans le SDK</Anchor>
* Enregistrement des revenus dans Unity

Vous pouvez également enregistrer des revenus négatifs si un utilisateur annule un achat ou si vous effectuez un remboursement. Pour enregistrer des revenus négatifs, il vous suffit d'ajouter le signe moins (-) à la valeur de revenu que vous transmettez à `af_revenue`.

**af\_revenue** est le seul paramètre qui totalise le revenu de vos utilisateurs. Veillez à toujours l’utiliser avec des événements in-app qui représentent les revenus réels associés à votre logique métier.

**af\_revenue** peut également avoir des valeurs de revenus négatives si vous suivez des évènements comme les transactions annulées ou les remboursements.

La valeur des revenus ne doit contenir que des chiffres (et un point décimal, si nécessaire) :

* **N** 'incluez pas d'autres caractères ou ne formatez pas la valeur des revenus d'une autre manière. Cela signifie qu'il n'y a pas de virgules, de signes monétaires (exemple $), de caractères spéciaux ni de texte.
* AppsFlyer fournit une valeur de revenu avec une **précision allant jusqu'à cinq décimales**.
* La plage de cette valeur doit être comprise entre -10 000 $ et +10 000 $, ou le montant équivalent dans la devise d'origine. Les montants en dehors de cette plage sont affichés dans les rapports de données brutes mais pas dans les rapports agrégés.
* Exemple : 1234.56
* Lorsque les revenus sont envoyées sous forme de chaîne, la valeur entre guillemets doit être valide. Par exemple : 1234.56

**Remarque** :

* AppsFlyer affiche le revenu exact envoyé par le SDK. Cela n'inclut pas de calcul de TVA ni de commissions sur l'App Store, etc., sauf si ceux-ci ont été inclus par le développeur côté SDK avant l'envoi à AppsFlyer.

**af\_currency** représente la devise indiquée dans **af\_revenue** (ou **af\_price**). Si **af\_currency** ne figure pas dans les paramètres de l’événement, AppsFlyer l'envoie avec la valeur par défaut USD.

Vous pouvez utiliser **af\_price** comme paramètre monétaire qui ne sera pas considéré comme revenu (par exemple, dans un événement « Ajouter au panier »). Ce paramètre renvoie au prix de chaque article individuel. Le montant total des achats s’affiche sous le paramètre af\_revenue.

### Devise du revenu

Il est important de comprendre comment AppsFlyer gère les paramètres et conversions des devises.

AppsFlyer gère la différence entre la devise des paramètres de l'app et la devise des événements in-app en utilisant la conversion de devise.

![revenue_normalization_flow.png](https://files.readme.io/f890d34168f92202c94da4bfa548bd0f471c98dec9c8d4282b2549f5878e9321-46334674326033.png)

Le diagramme ci-dessus illustre le processus suivant :

1. Les événements in-app sont envoyés - la devise est différente pour chaque événement
2. AppsFlyer échange toutes les devises en USD
3. AppsFlyer traite les données de revenus
4. Les données de revenus dans le tableau de bord s'affichent dans la devise des paramètres de l'app
5. AppsFlyer remplit les données de revenus dans les rapports de données brutes dans la devise des paramètres d'événement et d'app.

AppsFlyer utilise <Anchor target="_blank" href="https://openexchangerates.org/">Open Exchange Rates</Anchor> pour la conversion de devise. Le taux de change est mis à jour toutes les heures. Chaque fois qu’AppsFlyer effectue une conversion de devise, le taux de change effectif l'heure précédente est utilisé.

#### Conversion de devise

> 📄 **Exemple**
>
> Dans les paramètres de votre app, vous définissez la devise sur GBP. Un utilisateur français achète un produit via votre app. Le prix est indiqué en EUR (€). L’événementin-app que vous envoyez à AppsFlyer ressemble à ceci :
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.REVENUE,200);
> eventValue.put(AFInAppEventParameterName.CONTENT_TYPE,"category_a");
> eventValue.put(AFInAppEventParameterName.CONTENT_ID,"1234567");
> eventValue.put(AFInAppEventParameterName.CURRENCY,"EUR");
> AppsFlyerLib.getInstance().trackEvent(getApplicationContext() , AFInAppEventType.PURCHASE , eventValue);
> ```
>
> Dans ce cas, AppsFlyer convertit les revenus de EUR en USD, puis en GBP. Supposons que le taux de change soit 1 = 1,13 $. 200 € deviennent 226,85 $. Ensuite, AppsFlyer convertit les USD en GBP. Supposons que le taux de change soit de 1 $ = 0,78 £. Donc 226,85 $ deviennent 176,92 £.

#### Affichage de la devise

<Anchor target="_blank" href="/marketers/fr/docs/app-settings#localization-currency">La devise est définie dans les paramètres de l'app</Anchor>. La devise que vous définissez dans les paramètres de l’app est la devise qui apparaît dans le tableau de bord. Quelle que soit la devise que vous envoyez aux événements in-app, les revenus du tableau de bord apparaissent toujours dans la devise définie dans les paramètres de l'app.

> 📄 **Exemple**
>
> Supposons que vous envoyiez des événements in-app avec des devises différentes de celle définie dans les paramètres de l'app, voire sans aucune devise. Dans cet exemple, la devise dans les paramètres de l’application est définie sur **GBP**.
>
> Vous envoyez trois événements in-app à AppsFlyer.
>
> 1. L'événement A a un revenu de **234** et la devise **GBP**.
> 2. L'événement B a un revenu de **171** et la devise **EUR**.
> 3. L’événement C a un revenu de **171** et **aucune devise n'est spécifiée**.
>
> #### Données de revenus dans le tableau de bord
>
> Le revenu qui apparaît dans le tableau de bord est la **valeur convertie** de la devise en USD de l’événement in-app, puis dans la devise des paramètres de l’app.
>
> Si aucune devise n'est spécifiée dans l'événement, **AppsFlyer utilise la devise USD par défaut**. Le tableau de bord affiche l’événement et les revenus de la façon suivante :
>
>
>
> | In-Apps Events | Utilisateurs uniques | Nombre d'Actions | Revenu |
> | --- | --- | --- | --- |
> | A | 1 | 1 | 234 £ |
> | B | 1 | 1 | 149,4 £ - converti de EUR en USD puis en GBP. |
> | C | 1 | 1 | 132,9 £ - USD par défaut étant donné qu'aucune devise n'est spécifiée. Converti de USD en GBP directement. |
>
>
>
> #### Données sur les revenus dans les rapports de données brutes
>
> Si vous définissez la devise sur **GBP** dans les paramètres de l'app mais que vous envoyez des événements in-app avec différentes devises, le rapport de données brutes affiche les revenus dans la devise des paramètres de l'app ainsi que dans la devise de l'événement in-app.
>
> Si vous définissez la devise sur **GBP** dans les paramètres de l'app mais que vous envoyez des événements in-app sans devise, le rapport de données brutes affiche les revenus dans la devise paramétrée dans l'app, et en USD.
>
> Le rapport de données brutes des événements in-app affiche l'événement et les revenus de la façon suivante :
>
>
>
> | Événement | Revenu de l'évènement | Devise du revenu des évènements | Revenus de l'événement en GBP |
> | --- | --- | --- | --- |
> | A | 234 | GBP | 234 |
> | B | 171 | EUR | 149,4 £ - converti de EUR en USD puis en GBP. |
> | C | 171 | USD | 132,9 £ - USD par défaut étant donné qu'aucune devise n'est spécifiée. Converti de USD en GBP directement. |

</Accordion>

## Envoi d'événements

Vous pouvez envoyer des événements in-app à AppsFlyer de différentes manières :

* <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">**SDK AppsFlyer** :</Anchor> il s'agit du moyen le plus courant d'envoyer des événements. Vous pouvez envoyer des événements in-app riches qui enregistrent les actions de l'utilisateur dans l’app avec des API d'événements in-app AppsFlyer au niveau du SDK.
* **<Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">API de serveur à serveur :</Anchor>** utilisez l'API de serveur à serveur pour envoyer directement à AppsFlyer des événements qui se produisent en dehors de l'app mobile. Par exemple, si un utilisateur est actif sur les interfaces web et mobile, vous pouvez enregistrer des événements provenant des deux sources puis les attribuer au même utilisateur dans AppsFlyer. Il peut s'agir d'un événement in-app ou d'un autre événement, comme les événements de site, événements de centre d'appels ou bien encore les achats dans votre boutique de matériaux de construction.
* **<Anchor target="_blank" href="/marketers/fr/docs/legacy-receipt-validation-for-in-app-purchases">Validation de la réception</Anchor> :** il s'agit d'un mécanisme sécurisé où la plate-forme de paiement, par exemple Apple ou Google, vérifie que l'achat in-app a eu lieu comme indiqué. La validation de l'achat est le tout premier outil pour empêcher les événement de revenus frauduleux. Cela vous permet également de voir le revenu réel et d'éliminer les achats in-app incomplets.
* **<Anchor target="_blank" href="/marketers/fr/docs/in-app-events-for-hybrid-apps">Apps hybrides</Anchor>** : combinent des vues natives et du contenu HTML, et peuvent également enregistrer des événements in-app. Cependant, étant donné que le SDK peut uniquement envoyer des événements du côté natif, les développeurs doivent transférer toutes les données d'événement au code natif.

## Configuration des événements in-app

Le processus de configuration des événements in-app nécessite que le marketeur et le développeur travaillent ensemble, de la façon suivante :

| Étape | Role | Tâche | Détails |
| --- | --- | --- | --- |
| 1 | Marketeur | Déterminez les événements in-app à mesurer. [Définissez](/docs/in-app-events-overview#defining-an-inapp-event) et communiquez les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-event-structure#noms-dévénements-prédéfinis">noms</Anchor> et les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-event-structure#paramètres-dévénements-prédéfinis">paramètres</Anchor> des événements à votre développeur. | Nous vous recommandons de démarrer par 3 à 5 événements, que vous pourrez utiliser comme KPI pour mesurer la qualité de vos utilisateurs (par exemple : les achats, l'inscription et le partage). Les paramètres d'événement sont facultatifs, et vous pouvez utiliser n'importe quel paramètre d'événement avec n'importe quel nom d'événement.<br /><br />Voir [Événements recommandés par secteur d'activité](/docs/in-app-events-overview#recommended-events-by-business-vertical) pour les événements in-app typiques. |
| 2 | Développeur | Implémenter le code dans votre app, le cas échéant. | La documentation destinée aux développeurs est disponible <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk">ici</Anchor>. |
| 3 [Facultatif] | Marketeur | Travaillez en collaboration avec votre développeur pour définir le <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">champ ID utilisateur du client (CUID)</Anchor>. | Ce champ permet d'enrichir les données sur les événements in-app en comparant les données d'attribution AppsFlyer avec vos autres données qui utilisent le CUID comme clé. |
| 4 [Facultatif] | Marketeur | <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#le-mappage-dévénement">Mapper les événements</Anchor> vers les partenaires concernés dans le tableau de bord. | Il s'agit d'une tâche permanente, qui dépend des partenaires avec lesquels vous êtes intégré. |

<div id="defining-an-inapp-event" />

<Accordion title="Définissez un événement in-app">

Une fois que vous avez déterminé les événements in-app à mesurer, utilisez notre <Anchor target="_blank" href="https://evgen.appsflyer.com/">générateur d'événements in-app</Anchor> pour définir les événements et les paramètres comme indiqué ci-dessous :

1. Sélectionnez le nom d'événement qui convient le mieux au scénario que vous souhaitez enregistrer.
2. Sélectionnez les paramètres d'événement que vous souhaitez associer à l'événement. Choisissez des paramètres qui donneront un contexte supplémentaire à l'événement et enrichiront les données.
3. Téléchargez le fichier terminé à partir du générateur d'événements in-app, et transmettez-le à votre développeur.

> 📄 **Exemple**
>
> Le marketeur d'une app de commerce électronique souhaite enregistrer le type de contenu que les utilisateurs consultent, afin d'identifier les catégories les plus populaires et de relier les consultations de produits aux ventes de produits.
>
> Le tableau suivant est un exemple de structure d'événement que le marketeur transmet au développeur :
>
> <table><thead><tr><th>Nom de l'événement</th><th>Paramètres d'événement</th><th>Valeurs de paramètre</th><th>Quand l'événement est-il déclenché ?</th></tr></thead><tbody><tr><td rowspan="3">af_content_view</td><td>af_price</td><td>Prix du produit</td><td rowspan="3"><p><span>Lorsqu'un utilisateur consulte la page d'informations d'un certain produit</span></p></td></tr><tr><td><span>af_content_type</span></td><td><span>Nom de la catégorie de produit, par exemple, chaussures </span></td></tr><tr><td><span>af_content_id</span></td><td><p><span>ID du produit, par exemple, SKU</span></p></td></tr></tbody></table>

</Accordion>

<div id="recommended-events-by-business-vertical" />

<Accordion title="Événements recommandés par secteur d'activité">

Le tableau suivant fournit des liens vers des articles qui présentent des exemples et des flux d'événements in-app typiques que nous suggérons d'enregistrer par secteur.

| Secteur | Titre de l'article |
| --- | --- |
| <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="38px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-gaming-app-events">Événements recommandés pour les apps de gaming</Anchor> |
| <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="37px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-ecommerce-app-events">Événements recommandés pour les apps de eCommerce</Anchor> |
| <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="39px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-entertainment-app-events">Événements recommandés pour les apps de divertissement</Anchor> |
| <Image alt="banking.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="36px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-finance-and-banking-app-events">Événements recommandés pour les apps de gestion financière et bancaire</Anchor> |
| <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="36px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-p2p-lending-app-events">Événements recommandés pour les apps de prêt P2P</Anchor> |
| <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="37px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-online-education-app-events">Évènements d'app de formation en ligne recommandés</Anchor> |
| <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="37px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-ride-hailing-app-events">Événements recommandés pour les apps de transport</Anchor> |
| <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="38px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-flight-booking-app-events">Événements recommandés pour les apps de réservation de vols</Anchor> |
| <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="37px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-hotel-booking-app-events">Événements recommandés pour les apps de réservation d'hôtels</Anchor> |
| <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="37px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-healthcare-app-events">Événements recommandés pour les apps de soins de santé</Anchor> |
| <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="39px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-telecommunication-app-events">Événements recommandés pour les apps de télécommunication</Anchor> |
| <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="39px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-ewallet-app-events">Événements recommandé pour les apps de portefeuille électronique</Anchor> |
| <Image alt="soccer_ball.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="39px" /> | <Anchor target="_blank" href="/marketers/fr/docs/recommended-sports-betting-events">Événements recommandés pour les paris sportifs</Anchor> |

</Accordion>

<div id="view-inapp-event-data" />

<Accordion title="Afficher des données d’événement in-app">

Les événements in-app sont attribués à la source média responsable de l'installation pendant la durée vie de l'utilisateur. Les données d'événement sont présentées sous forme de <Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">données Life Time Value ou d'activité</Anchor>.

Vous pouvez consulter les données de vos événements in-app à ces endroits :

* Page de présentation du tableau de bord  affiche les performances d’acquisition d’utilisateurs LTV (UA) en temps réel. **Remarque** : cela inclut le revenu divisé entre les utilisateurs organiques et non organiques signalés via des événements in-app, et le retargeting des revenus <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">attribués en double.</Anchor>
* Page des événements : affiche les performances des événements in-app LTV sur l'ensemble des sources média
* <Anchor target="_blank" href="/marketers/fr/docs/activity-dashboard">Page Activité</Anchor> : affiche les activités in-app pour la plage de dates sélectionnée.
* <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">Rapport de données brutes d'évènements in-app</Anchor> : affiche les données d'activité, c'est-à-dire une liste chronologique des actions effectuées par votre base d'utilisateurs. Ce rapport inclut les valeurs des paramètres d'événement, par exemple :

  ```json
  {
    "af_level":"10",
    "af_score":"3387",
    "arena":"7",
    "char_type":"paladin"
  }
  ```

  Notez que les rapports de données brutes sont une fonctionnalité premium.

</Accordion>

<div id="tips" />

<Accordion title="Nos conseils">

Gardez à l’esprit les points suivants lorsque vous définissez les noms d’événements et les paramètres dans l’app :

* Pour assurer la cohérence des données dans les rapports de données brutes, nous recommandons de définir et d'utiliser les mêmes noms et structures d'événements in-app sur toutes les plate-formes.
* Utilisez un nombre minimal d’événements pour faciliter la comparaison de la qualité des utilisateurs issus de différentes sources.
* **Il est important de protéger la vie privée de vos utilisateurs.** **Ne remplissez pas les valeurs d'événements in-app avec des informations restreintes susceptibles de les identifier directement**. **Cela concerne par exemple, l'adresse e-mail, le nom, le numéro d'identité et, à certains endroits, le code postal. Pour plus d'informations sur les données restreintes, lisez la <Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">politique de confidentialité des services</Anchor>.**
* AppsFlyer collecte l'adresse IP des appareils lors des <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">engagements</Anchor>. Dans certaines juridictions ou certains scénarios d'utilisation, l'adresse IP peut être considérée comme une IPP. Nous utilisons l'adresse IP pour dériver la situation géographique de l'appareil à un niveau large (ville, district), mais pas l'adresse spécifique. Si nécessaire, vous pouvez sélectionner <Anchor target="_blank" href="/marketers/fr/docs/apply-ip-masking-to-user-data">Masquer les adresses IP</Anchor> afin que ces dernières n'apparaissent pas dans les rapports de données brutes.
* Les événements in-app sont la seule source de données de revenu dans AppsFlyer. Vous pouvez associer une valeur de revenu spécifique à chaque événement et la visualiser sur le tableau de bord de votre application. En savoir plus sur les [paramètres de monétisation](/docs/in-app-events-overview#revenue-events).

  ![revenue_data.png](https://support.appsflyer.com/hc/article_attachments/360020607037)

</Accordion>

<div id="limitations" />

<Accordion title="Limites">

Gardez à l’esprit les points suivants lorsque vous définissez les noms d’événements et les paramètres dans l’app :

* Nous vous recommandons d'utiliser uniquement des caractères alphanumériques en minuscule (a-z et 0-9) pour les noms de vos évènements in-app. Les noms d'évènements sont sensibles à la casse, ce qui signifie que af\_purchase et af\_PURCHASE sont deux évènements différents dans les données brutes. Cependant, dans les rapports agrégés (ex : aperçu, événements), ils peuvent s'afficher comme étant un même événement.
* Il y a une limite de cardinalité de 300 événements uniques par jour. <Anchor target="_blank" href="/marketers/fr/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_events_limit">En savoir plus</Anchor>
* Les utilisateurs uniques ne sont comptabilisés que pour les 100 premiers événements après l'installation de l'app.
* Les noms d'événement ne peuvent pas commencer par les caractères suivants : " = + -
* Les valeurs des événements ne doivent pas contenir le caractère +, sauf dans les URL encodées, ou encodées via <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">ASCII</Anchor>.
* Les noms d’événements ne peuvent pas contenir d’espaces vides. Vous pouvez utiliser des espaces soulignés (tirets du bas) avant ou après le nom de l'événement.
* Les valeurs des événements ne doivent pas dépasser 2000 caractères, où elles seront tronquées dans les rapports de données brutes.
* Si vous incluez l'URL de référence en tant que valeur d'événement, elle doit être <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">codée</Anchor>.
* Facebook impose des limitations pour les noms et paramètres des événements. Pour en savoir plus sur ces restrictions, cliquez <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#limits">ici</Anchor>.

</Accordion>

## FAQ

La section suivante comprend diverses FAQ sur les événements in-app.

<div id="how-do-i-use-the-revenue-parameter" />

<Accordion title="Comment utiliser le paramètre des revenus ?">

Vous pouvez transmettre les valeurs de revenu avec n'importe quel nom de paramètre et événement. Cependant, pour enregistrer les revenus (revenus négatifs inclus) dans les données brutes et agrégées d'AppsFlyer, vous DEVEZ OBLIGATOIREMENT utiliser le paramètre ***af\_revenue***. Pensez à toujours l’utiliser avec les évènements représentatifs d'une génération de revenus avérés dans votre activité.

**af\_currency** représente la devise indiquée dans **af\_revenue** (ou **af\_price**). Si **af\_currency** ne figure pas dans les paramètres de l’événement, AppsFlyer l'envoie avec la valeur par défaut USD.

Pour plus de détails sur le paramètre ***af\_revenue***, consultez [le guide d'attribution de revenu](/docs/in-app-events-overview#revenue-events).

</Accordion>

<div id="how-does-appsflyer-attribute-events" />

<Accordion title="Comment AppsFlyer attribue les événements ?">

Les événements in-app sont attribués à la source média via laquelle l’app a été installée.

Lors de l’installation d’une app (premier lancement), AppsFlyer utilise diverses <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#méthodes-dattribution">méthodes d’attribution</Anchor> pour déterminer l’attribution de l’installation. En parallèle, le SDK AppsFlyer crée un nouvel <Anchor target="_blank" href="/marketers/fr/docs/about-device-identifiers#appsflyer-id">ID AppsFlyer</Anchor> unique, qui est associé aux informations d’attribution.

Chaque événement in-app effectué par la suite avec le même appareil dans l’application aura cet ID. Cela permet à AppsFlyer d’attribuer l’événement à la source média d’origine. Les annonceurs peuvent l’utiliser pour suivre le parcours complet de l’utilisateur dans leur app.

Les événements d’utilisateurs récemment soumis au retargeting peuvent être <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">attribués en double double</Anchor>.

AppsFlyer attribue les événements des installations attribuées comme **organiques** dans les cas suivants :

* Plus de 24 mois se sont écoulés depuis la date d'installation
* Les conditions de la source média [impliquent la suppression des données au niveau de l’utilisateur](/docs/in-app-events-overview#how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations)
* L’utilisateur supprime les données de l’app stockées sur l’appareil, forçant la création d’un nouvel ID AppsFlyer.

</Accordion>

<div id="are-events-recorded-if-a-device-is-offline" />

<Accordion title="Les événements sont-ils enregistrés si un appareil est hors ligne ?">

Si un utilisateur initie un évènement lorsque la connexion Internet est indisponible, Appsflyer est capable de l'enregistrer. Le fonctionnement est le suivant :

1. Le SDK envoie les événements aux serveurs AppsFlyer et attend une réponse positive.
2. Si le SDK ne reçoit pas une réponse positive, l'événement est stocké dans le cache.
3. Une fois la réponse positive suivante reçue, l'événement stocké est renvoyé au serveur.
4. S'il y a plusieurs événements dans le cache, ils sont envoyés au serveur les uns après les autres.

> 📘 **Remarque**
>
> Le cache du SDK peut stocker jusqu’à 40 événements, ce qui signifie que seuls les 40 premiers événements survenus hors ligne sont enregistrés. Tout ce qui vient après, jusqu'à la prochaine réponse positive, n'est pas retenu.
>
> L'heure de l'événement qui apparaît dans les données brutes est l'heure à laquelle l'événement est envoyé à AppsFlyer après la reconnexion en ligne de l'appareil. Ce n'est pas le moment où l'événement a eu lieu.

</Accordion>

<div id="what-are-complex-inapp-events-and-how-do-i-set-them-up" />

<Accordion title="Que sont les événements in-app complexes et comment les configurer ?">

Les événements in-app complexes permettent d'envoyer plusieurs événements en une seul appel API.

Ils sont pratiques pour regrouper visuellement plusieurs actions d'utilisateur étroitement liées les unes aux autres (comme l'ajout au panier de plusieurs produits en une seule session).  
Exemple :

```json
{
  "af_revenue":"50.87",
  "af_currency":"USD",
  "af_receipt_id":"57601333",
  "product":[ 
   { 
	 "af_content_id":"1164_8186",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"1164_8186",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"1164_8186",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"1177_8185",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"0153_9077",
	 "af_price":"14.99",
	 "af_quantity":"1"
   }
  ]
}
```

> ❗️ **Attention**
>
> Les événements in-app complexes entraînent des problèmes de postback chez Meta ads et Criteo. Si vous voulez que l'événement soit entièrement mappé avec Meta ads et Criteo, envoyez des événements séparés pour chaque action de l'utilisateur (ex : vous envoyez un événement Ajouter au panier pour chaque article ajouté). Utilisez les données brutes d'événements in-app pour regrouper ces événements.

</Accordion>

<div id="can-i-add-multiple-items-to-a-single-transaction" />

<Accordion title="Puis-je combiner plusieurs éléments en une même transaction ?">

Vous pouvez combiner plusieurs éléments en une même transaction. Plutôt que d'utiliser des valeurs uniques par paramètre d’événement, vous pouvez avoir plusieurs éléments décrivant la transaction, séparés par des virgules.   Le format doit être une chaîne JSON.

> 📄 **Exemple**
>
> Au cours de la même transaction, Mr. Smith achète deux chemises identiques, une paire de chaussures et un chapeau auprès d’un magasin en ligne basé aux États-Unis. La séquence selon laquelle chaque élément est répertorié doit être identique pour chaque paramètre.
>
> ```json
> "{\"af_content_id\": [\"123\",\"988\",\"399\"], \"af_quantity\": [\"2\",\"1\",\"1\"], \"af_price\": [\"25\",\"50\",\"10\"], \"af_revenue\": \"110\", \"af_currency\": \"USD\"}"
> ```
>
> Plusieurs éléments à la fois sont transmis sous forme de tableau dans les <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration">postbacks</Anchor>. À l'heure actuelle, Meta ads et Twitter ne peuvent pas analyser correctement les paramètres de ces tableaux. Pour résoudre ce problème, AppsFlyer additionne la quantité d'éléments (af\_quantity) au lieu de les envoyer à ces SRN sous forme de tableau. Dans notre exemple, Meta ads recevrait **af\_quantity=4**.
>
> **<span id="h_01HDBZW9XFJ68WSM3066NVRATS"></span>Remarque**
>
> Plusieurs articles peuvent être utilisés avec les événements in-app suivants :
>
> af\_add\_to\_cart, af\_add\_to\_wishlist, af\_tutorial\_completion, af\_initiated\_checkout, af\_purchase, af\_rate, af\_spent\_credits, af\_content\_view, af\_travel\_booking, af\_update



</Accordion>

<div id="how-does-appsflyer-handle-event-deduplication" />

<Accordion title="Comment AppsFlyer gère-t-il la déduplication des événements ?">

Nous utilisons un mécanisme de déduplication d'événements in-app. Il vérifie tous les événements in-app afin de savoir si un événement in-app identique provenant du même appflyer\_id est apparu moins de 10 secondes auparavant. Si un tel événement est trouvé, le mécanisme supprime le doublon.

Deux événements sont considérés comme identiques si les champs suivants sont identiques dans les deux événements :

* Nom de l'événement
* Valeur de l'événement
* ID d'app
* ID AppsFlyer

> 📘 **Remarque**
>
> La déduplication ne fonctionne que pour les événements in-app envoyés à partir du SDK.
>
> Les événements in-app S2S ne sont pas dédupliqués.

</Accordion>

<div id="how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations" />

<Accordion title="Combien de temps AppsFlyer conserve-t-il les données niveau utilisateur et quelles sont les obligations de suppression ?">

AppsFlyer conserve les données brutes des utilisateurs pendant 24 mois, sauf indication contraire, obligation ou autorisation légale. Certains SRN/partenaires exigent des fournisseurs d'attribution, y compris AppsFlyer, qu'ils suppriment les données relatives aux utilisateurs liées aux SRN/partenaires avant l'expiration de la période de 24 mois.

Après suppression, les événements liés aux utilisateurs supprimés s'affichent en tant qu'événements organiques. Les données agrégées passées ne sont pas affectées. Pour plus d'informations, reportez-vous à la rubrique <Anchor target="_blank" href="/marketers/fr/docs/user-level-data-retention#obligations-concernant-la-conservation-et-leffacement-des-données">Obligations de conservation et de suppression des données</Anchor>.

</Accordion>

<div id="do-i-need-to-add-the-os-operating-system-parameter-to-my-events" />

<Accordion title="Dois-je ajouter le paramètre OS (système d'exploitation) à mes événements ?">

* Le SDK Android et le SDK iOS ajoutent automatiquement le paramètre OS (système d'exploitation).
* Avec <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">l'API S2S</Anchor>, depuis le 1er juillet 2021 vous devez envoyer le paramètre OS (système d'exploitation) pour les apps iOS. Si vous n'envoyez pas ce paramètre, les données sont considérées comme provenant d'un utilisateur iOS 14.5 et cela affecte la mise à disposition des <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">données brutes</Anchor>.

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration">Configuration des postbacks d'événements in-app</Anchor>

<div data-zendesk-anchors="why-record-inapp-events=pourquoi-enregistrer-des-%C3%A9v%C3%A8nements-in-app h_01HDBZW9XEBTY13MG4AN93RNCD=pourquoi-enregistrer-des-%C3%A9v%C3%A8nements-in-app about-inapp-events=%C3%A0-propos-des-%C3%A9v%C3%A9nements-in-app h_01HDBZW9XEBDSDA9T5X5B6KGTG=%C3%A0-propos-des-%C3%A9v%C3%A9nements-in-app h_01HDBZW9XE3Z40JE9576C4XSF4=astuce h_01HDBZW9XEMV1EFY7CEE7N1GZV=predefined-and-custom-events h_01HDBZW9XEZWDDHFATKY6KDN25=revenue-events revenue-currency=devise-du-revenu h_01HDBZW9XEMPVG76PJQN7WDAT6=devise-du-revenu currency-conversion=conversion-de-devise h_01HDBZW9XEMGA5RAW0DBBPV3FQ=conversion-de-devise h_01HDBZW9XERK3VN1GS8GHM911W=exemple currency-display=affichage-de-la-devise h_01HDBZW9XE85YC3JHG58YYAB8F=affichage-de-la-devise h_01HDBZW9XEQNG1RDH7A8H002ZD=exemple-1 revenue-data-in-the-dashboard=donn%C3%A9es-de-revenus-dans-le-tableau-de-bord h_01HDBZW9XEVWB9045N0YEVWE6Z=donn%C3%A9es-de-revenus-dans-le-tableau-de-bord revenue-data-in-raw-data-reports=donn%C3%A9es-sur-les-revenus-dans-les-rapports-de-donn%C3%A9es-brutes h_01HDBZW9XEGYFD3W9FT1N3ZGQW=donn%C3%A9es-sur-les-revenus-dans-les-rapports-de-donn%C3%A9es-brutes sending-events=envoi-d%C3%A9v%C3%A9nements h_01HDBZW9XFESG6MP9QF1XCJKE6=envoi-d%C3%A9v%C3%A9nements setting-up-inapp-events=configuration-des-%C3%A9v%C3%A9nements-in-app h_01HDBZW9XF13AGRCN2HJ18RHS2=configuration-des-%C3%A9v%C3%A9nements-in-app h_01HDBZW9XF6X9H4WCFWC28W1CD=defining-an-inapp-event h_01HDBZW9XFN2B8AC18VW99G8Z6=exemple-2 h_01HDBZW9XFM33BYF90EJPQ35V9=recommended-events-by-business-vertical h_01HDBZW9XF6G2R6Y6S5GFNDM6W=view-inapp-event-data h_01HDBZW9XF1Q1NB1YS8Q0HKA6K=tips h_01HDBZW9XFFNWCJ18NETEM2287=limitations h_01HDBZW9XF5H24H2HCJKKHCRTE=faq h_01HDBZW9XF5ZNGVEMND08137PR=how-do-i-use-the-revenue-parameter h_01HDBZW9XFZ144ND2FXW2AMGRW=how-does-appsflyer-attribute-events h_01HDBZW9XFDBFY580P939ZP0D4=are-events-recorded-if-a-device-is-offline h_01HDBZW9XFCDMKNWJ75AWHC2Y0=remarque h_01HDBZW9XF8Q57JZPD8J2Y25SB=what-are-complex-inapp-events-and-how-do-i-set-them-up h_01HDBZW9XF33FHR418MNVH6BS2=attention h_01HDBZW9XFRAFSXJE5N5ZPRW2R=can-i-add-multiple-items-to-a-single-transaction h_01HDBZW9XFB9TAT8W4CGNP1892=exemple-3 h_01HDBZW9XFGMG5B5FG2785ERAM=how-does-appsflyer-handle-event-deduplication h_01HDBZW9XFWKN7W90PSVMX73FS=remarque-1 h_01HDBZW9XFFXXBYY14A3QGENSF=how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations h_01HDBZW9XFH80JK748PAPG09B5=do-i-need-to-add-the-os-operating-system-parameter-to-my-events h_01HDNZ708FN0N286R5HDQGMNGZ=%C3%A0-consulter-%C3%A9galement" />
