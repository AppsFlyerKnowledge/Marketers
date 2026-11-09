---
title: Événements recommandés pour les apps de réservation d'hôtels
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-04-29T14:49:54Z'
  edited_at: '2022-01-25T17:23:41Z'
  id: 360019843558
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/360019843558
---
> **En bref :** mesurez la qualité de vos utilisateurs tout au long de leur parcours en enregistrant ces suggestions d'événements in-app pour votre app de réservation d'hôtels .

<div id="-hotel-booking" />

## <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="100px" /> Réservation d'hôtel

Les apps de réservation d'hôtel permettent aux voyageurs de réserver facilement des hôtels et d'obtenir les meilleures offres. Nous vous recommandons d'enregistrer les évènements typiques de recherche, d'achat, de réservation de voyage et d'ajout à la liste d'envies.

L'enregistrement de ces évènements peut vous aider à déterminer :

* Quelles campagnes et sources média amènent des utilisateurs qui réservent réellement des vacances
* Quelles campagnes et sources média amènent les utilisateurs qui réservent le plus et génèrent plus de revenus

Vous pouvez attribuer des préférences telles que la note de l'hôtel, la saison, le pays et le nombre d'enfants pour les utilisateurs provenant de certaines sources média. Cela vous permettra d'optimiser vos campagnes en ciblant ces préférences des utilisateurs.

<div id="important" />

> 🚧 **Important !**
>
> * Veillez à lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#introduction-setting-up-inapp-events">instructions</Anchor> à l'attention des marketeurs pour implémenter les événements in-app.
> * Pour simplifier l'implémentation, [téléchargez un fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSJsgqgzIInw8NAzY8ILsk2H4Vjp-7dRIc1Ed6vNb34mOayiTjutUs-cOnd4H5u18EvgpspKe7Dx2xb/pub?gid=2004888002&single=true&output=csv) contenant tous les événements in-app de base décrits dans cet article,  puis modifiez les événements en fonction des besoins de votre entreprise. Une fois terminé, partagez le fichier avec votre développeur.
> * Pour chaque événement recommandé que contient cet article, vous trouverez des extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour plus d'informations sur l'enregistrement des événements in-app, consultez le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">guide des événements in-app riches</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events_hotel_booking_app_user_journey" src="https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png" />

<div id="recommended-structures-for-predefined-events" />

## Structures recommandées pour les événements prédéfinis

La section suivante fournit une liste des structures d'événements typiques du secteur de la réservation d'hôtels. Chaque structure donne un nom d'événement prédéfini, ainsi que des suggestions de paramètres d'événement à appliquer. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Inscription terminée (af_complete_registration)">

**Objectif**

Découvrez combien d'utilisateurs ont installé l'app et terminé le processus d'inscription, les méthodes d'inscription préférées de vos utilisateurs et les sources média qui amènent les utilisateurs qui s'inscrivent.

**Déclencheur**

Lorsque l'utilisateur finalise le processus d'inscription

Paramètres d'événement

| Nom du champ | Description | Exemple de valeur |
| --- | --- | --- |
| af\_registration\_method | Le type de méthode d'inscription | email, facebook |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REGSITRATION_METHOD, "Facebook");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.COMPLETE_REGISTRATION, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventCompleteRegistration
withValues: @{ 
  AFEventParamRegistrationMethod: @"Facebook" 
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventCompleteRegistration, 
withValues: [
  AFEventParamRegistrationMethod: "Facebook"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CompletedRegistrationEvent = new Dictionary<string, string>();
CompletedRegistrationEvent.Add("af_registration_method", "Facebook");
AppsFlyer.sendEvent ("af_complete_registration", CompletedRegistrationEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="login-af_login" />

<Accordion title="Connexion (af_login)">

**Objectif**

Comprendre le taux de rétention de vos utilisateurs inscrits

**Déclencheur**

Lorsque l'utilisateur se connecte avec succès

**Paramètres d'événement**

Peut être envoyé sans paramètre supplémentaire

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),   
AFInAppEventType.LOGIN, null);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventLogin  
 withValues: nil  
];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventLogin, withValues: nil);
```

</Tab>

<Tab title="Unity">

```csharp
AppsFlyer.sendEvent ("af_login", null);
```

</Tab>
</Tabs>

</Accordion>

<div id="search-af_search" />

<Accordion title="Recherche (af_search)">

**Objectif**

Découvrir ce que les utilisateurs recherchent, et quels résultats de recherche sont les plus pertinents et mènent à un achat. De plus, vous pouvez voir ce que les utilisateurs provenant de certaines zones géographiques recherchent et les cibler en conséquence grâce aux sources média.

**Déclencheur**

Lorsque l'utilisateur effectue une recherche

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_date\_a | Date d'arrivée | 2018/07/26 |
| af\_date\_b | Date de départ | 2018/08/01 |
| af\_destination\_a | Localisation de l'utilisateur | London |
| af\_destination\_b | Localisation de l'hôtel | Madrid |
| af\_num\_adults | Nombre de clients | 2 |
| af\_num\_children | Nombre d'enfants | 0 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.DATE_A, "2018/07/26");
eventValue.put(AFInAppEventParameterName.DATE_B, "2018/08/01");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "London");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Madrid");
eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 2);
eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.SEARCH, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventSearch
withValues: @{
  AFEventParamDateA: @"2018/07/26",
  AFEventParamDateB: @"2018/08/01",
  AFEventParamDestinationA: @"London",
  AFEventParamDestinationB: @"Madrid",
  AFEventParamNumAdults: @2,
  AFEventParamNumChildren: @0
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventSearch, withValues: [
  AFEventParamDateA: "2018/07/26",
  AFEventParamDateB: "2018/08/01",
  AFEventParamDestinationA: "London",
  AFEventParamDestinationB: "Madrid",
  AFEventParamNumAdults: 2,
  AFEventParamNumChildren: 0
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> Search = 
			new Dictionary<string, string>();
Search.Add("af_date_a", "2018/07/26");
Search.Add("af_date_b", "2018/08/01");
Search.Add("af_destination_a", "London");
Search.Add("af_destination_b", "Madrid");
Search.Add("af_num_adults", "2");
Search.Add("af_num_children", "0");
AppsFlyer.sendEvent("af_add_to_wish_list", Search);
```

</Tab>
</Tabs>

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Affichage du contenu (af_content_view)">

**Objectif**

Cet événement peut vous aider à déterminer :

* Si les résultats proposés répondent bien aux éléments recherchés
* Les types de biens recherchés
* Tendances saisonnières
* Les destinations populaires
* Quelles sources média amènent les utilisateurs, puis recibler ces derniers dans des publicités et des promotions

**Déclencheur**

Lorsque l'utilisateur visualise un établissement

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Tarif en vigueur de l'hôtel | 674 |
| af\_content\_id | ID de l'hôtel | ODIRNH |
| af\_date\_a | Date d'arrivée | 2018/07/26 |
| af\_date\_b | Date de départ | 2018/08/01 |
| af\_destination\_a | Localisation de l'utilisateur | London |
| af\_destination\_b | Localisation de l'hôtel | Madrid |
| af\_class | Type de chambre | De luxe |
| af\_num\_adults | Nombre de clients | 2 |
| af\_num\_children | Nombre d'enfants | 0 |
| af\_hotel\_score | Note de l'hôtel selon les avis | 9.6 |
| af\_preferred\_star\_ratings | Nombre d'étoiles de l'hôtel préféré | 5 |
| af\_preferred\_neighborhoods | Zone dans laquelle se trouve l'hôtel | Centro |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CURRENCY, "GBP");
eventValue.put(AFInAppEventParameterName.PRICE, 674);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "ODIRNH");
eventValue.put(AFInAppEventParameterName.DATE_A, "2018/07/26");
eventValue.put(AFInAppEventParameterName.DATE_B, "2018/08/01");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "London");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Madrid");
eventValue.put(AFInAppEventParameterName.CLASS, "Deluxe");
eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 2);
eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
eventValue.put(AFInAppEventParameterName.HOTEL_SCORE, 9.6);
eventValue.put(AFInAppEventParameterName.PREFERRED_STAR_RATINGS, 5);
eventValue.put(AFInAppEventParameterName.PREFERRED_NEIGHBORHOODS, "Centro");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.CONTENT_VIEW, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventContentView
withValues: @{
  AFEventParamCurrency: @"GBP",
  AFEventParamPrice: @674,
  AFEventParamContentId: @"ODIRNH",
  AFEventParamDateA: @"2018/07/26",
  AFEventParamDateB: @"2018/08/01",
  AFEventParamDestinationA: @"London",
  AFEventParamDestinationB: @"Madrid",
  AFEventParamClass: @"Deluxe",
  AFEventParamNumAdults: @2,
  AFEventParamNumChildren: @0,
  AFEventParamHotelScore: @9.6,
  AFEventParamPreferredStarRatings: @5,
  AFEventParamPreferredNeighborhoods: @"Centro"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventContentView, withValues: [
  AFEventParamCurrency: "GBP",
  AFEventParamPrice: 674,
  AFEventParamContentId: "ODIRNH",
  AFEventParamDateA: "2018/07/26",
  AFEventParamDateB: "2018/08/01",
  AFEventParamDestinationA: "London",
  AFEventParamDestinationB: "Madrid",
  AFEventParamClass: "Deluxe",
  AFEventParamNumAdults: 2,
  AFEventParamNumChildren: 0,
  AFEventParamHotelScore: 9.6,
  AFEventParamPreferredStarRatings: 5,
  AFEventParamPreferredNeighborhoods: "Centro"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ContentView = 
			new Dictionary<string, string>();
ContentView.Add("af_currency", "GBP");
ContentView.Add("af_price", "674");
ContentView.Add("af_content_id", "ODIRNH");
ContentView.Add("af_date_a", "2018/07/26");
ContentView.Add("af_date_b", "2018/08/01");
ContentView.Add("af_destination_a", "London");
ContentView.Add("af_destination_b", "Madrid");
ContentView.Add("af_class", "Deluxe");
ContentView.Add("af_num_adults", "2");
ContentView.Add("af_num_children", "0");
ContentView.Add("af_hotel_score", "9.6");
ContentView.Add("af_preferred_star_ratings", "5");
ContentView.Add("af_preferred_neighborhoods", "Centro");
AppsFlyer.sendEvent("af_content_view", ContentView);
```

</Tab>
</Tabs>

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Ajouter à la liste de souhaits (af_add_to_wishlist)">

**Objectif**

Enregistrer les hôtels et les destinations que les utilisateurs souhaitent réserver. Lorsque vous avez connaissance des hôtels, des régions et des évaluations par étoiles que recherchent les utilisateurs, vous pouvez utiliser ces données pour les recibler.

**Déclencheur**

Lorsqu'un utilisateur ajoute une liste à sa liste d'envies

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Tarif en vigueur de l'hôtel | 674 |
| af\_content\_id | ID de l'hôtel | ODIRNH |
| af\_date\_a | Date d'arrivée | 2018/07/26 |
| af\_date\_b | Date de départ | 2018/08/01 |
| af\_destination\_a | Localisation de l'utilisateur | London |
| af\_destination\_b | Localisation de l'hôtel | Madrid |
| af\_class | Type de chambre | De luxe |
| af\_num\_adults | Nombre de clients | 2 |
| af\_num\_children | Nombre d'enfants | 0 |
| af\_hotel\_score | Note de l'hôtel selon les avis | 9.6 |
| af\_preferred\_star\_ratings | Nombre d'étoiles de l'hôtel préféré | 5 |
| af\_preferred\_neighborhoods | Zone dans laquelle se trouve l'hôtel | Centro |
| purchase\_method | Méthode d'achat | Carte de crédit |
| af\_coupon\_code | Code promotionnel ou points de fidélité | SUM2018 |
| property\_type | Type d'établissement | Hôtel |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CURRENCY, "GBP");
eventValue.put(AFInAppEventParameterName.PRICE, 674);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "ODIRNH");
eventValue.put(AFInAppEventParameterName.DATE_A, "2018/07/26");
eventValue.put(AFInAppEventParameterName.DATE_B, "2018/08/01");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "London");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Madrid");
eventValue.put(AFInAppEventParameterName.CLASS, "Deluxe");
eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 2);
eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
eventValue.put(AFInAppEventParameterName.HOTEL_SCORE, 9.6);
eventValue.put(AFInAppEventParameterName.PREFERRED_STAR_RATINGS, 5);
eventValue.put(AFInAppEventParameterName.PREFERRED_NEIGHBORHOODS, "Centro");
eventValue.put("purchase_method", "credit card");
eventValue.put(AFInAppEventParameterName.COUPON_CODE, "SUM2018");
eventValue.put("property_type", "hotel");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.ADD_TO_WISH_LIST, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventAddToWishlist
withValues: @{
  AFEventParamCurrency: @"GBP",
  AFEventParamPrice: @674,
  AFEventParamContentId: @"ODIRNH",
  AFEventParamDateA: @"2018/07/26",
  AFEventParamDateB: @"2018/08/01",
  AFEventParamDestinationA: @"London",
  AFEventParamDestinationB: @"Madrid",
  AFEventParamClass: @"Deluxe",
  AFEventParamNumAdults: @2,
  AFEventParamNumChildren: @0,
  AFEventParamHotelScore: @9.6,
  AFEventParamPreferredStarRatings: @5,
  AFEventParamPreferredNeighborhoods: @"Centro",
  @"purchase_method": @"credit card",
  AFEventParamCouponCode: @"SUM2018",
  @"property_type": @"hotel"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventAddToWishlist, withValues: [
  AFEventParamCurrency: "GBP",
  AFEventParamPrice: 674,
  AFEventParamContentId: "ODIRNH",
  AFEventParamDateA: "2018/07/26",
  AFEventParamDateB: "2018/08/01",
  AFEventParamDestinationA: "London",
  AFEventParamDestinationB: "Madrid",
  AFEventParamClass: "Deluxe",
  AFEventParamNumAdults: 2,
  AFEventParamNumChildren: 0,
  AFEventParamHotelScore: 9.6,
  AFEventParamPreferredStarRatings: 5,
  AFEventParamPreferredNeighborhoods: "Centro",
  "purchase_method": "credit card",
  AFEventParamCouponCode: "SUM2018",
  "property_type": "hotel"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> AddToWishList = 
			new Dictionary<string, string>();
AddToWishList.Add("af_currency", "GBP");
AddToWishList.Add("af_price", "674");
AddToWishList.Add("af_content_id", "ODIRNH");
AddToWishList.Add("af_date_a", "2018/07/26");
AddToWishList.Add("af_date_b", "2018/08/01");
AddToWishList.Add("af_destination_a", "London");
AddToWishList.Add("af_destination_b", "Madrid");
AddToWishList.Add("af_class", "Deluxe");
AddToWishList.Add("af_num_adults", "2");
AddToWishList.Add("af_num_children", "0");
AddToWishList.Add("af_hotel_score", "9.6");
AddToWishList.Add("af_preferred_star_ratings", "5");
AddToWishList.Add("af_preferred_neighborhoods", "Centro");
AddToWishList.Add("purchase_method", "credit card");
AddToWishList.Add("af_coupon_code", "SUM2018");
AddToWishList.Add("af_property_type", "hotel");
AppsFlyer.sendEvent("af_add_to_wish_list", AddToWishList);
```

</Tab>
</Tabs>

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Paiement initié (af_initiated_checkout)">

**Objectif**

Comprendre le comportement des acheteurs lorsqu'ils procèdent au paiement. Cet événement peut vous aider à déterminer :

* La méthode d'achat qui a été utilisée (ex  : carte bancaire ou eWallet)
* Si les utilisateurs terminent le processus de paiement

**Déclencheur**

Lorsque l'utilisateur ajoute ses informations de carte bancaire ou connecte son eWalllet

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Tarif en vigueur de l'hôtel | 674 |
| af\_content\_id | ID de l'hôtel | ODIRNH |
| af\_date\_a | Date d'arrivée | 2018/07/26 |
| af\_date\_b | Date de départ | 2018/08/01 |
| af\_destination\_a | Localisation de l'utilisateur | London |
| af\_destination\_b | Localisation de l'hôtel | Madrid |
| af\_class | Type de chambre | De luxe |
| af\_num\_adults | Nombre de clients | 2 |
| af\_num\_children | Nombre d'enfants | 0 |
| af\_hotel\_score | Note de l'hôtel selon les avis | 9.6 |
| af\_preferred\_star\_ratings | Nombre d'étoiles de l'hôtel préféré | 5 |
| af\_preferred\_neighborhoods | Zone dans laquelle se trouve l'hôtel | Centro |
| purchase\_method | Méthode d'achat | Carte de crédit |
| af\_coupon\_code | Code promotionnel ou points de fidélité | SUM2018 |
| property\_type | Type d'établissement | Hôtel |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CURRENCY, "GBP");
eventValue.put(AFInAppEventParameterName.PRICE, 674);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "ODIRNH");
eventValue.put(AFInAppEventParameterName.DATE_A, "2018/07/26");
eventValue.put(AFInAppEventParameterName.DATE_B, "2018/08/01");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "London");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Madrid");
eventValue.put(AFInAppEventParameterName.CLASS, "Deluxe");
eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 2);
eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
eventValue.put(AFInAppEventParameterName.HOTEL_SCORE, 9.6);
eventValue.put(AFInAppEventParameterName.PREFERRED_STAR_RATINGS, 5);
eventValue.put(AFInAppEventParameterName.PREFERRED_NEIGHBORHOODS, "Centro");
eventValue.put("purchase_method", "credit card");
eventValue.put(AFInAppEventParameterName.COUPON_CODE, "SUM2018");
eventValue.put("property_type", "hotel");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.INITIATED_CHECKOUT, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventInitiatedCheckout
withValues: @{
  AFEventParamCurrency: @"GBP",
  AFEventParamPrice: @674,
  AFEventParamContentId: @"ODIRNH",
  AFEventParamDateA: @"2018/07/26",
  AFEventParamDateB: @"2018/08/01",
  AFEventParamDestinationA: @"London",
  AFEventParamDestinationB: @"Madrid",
  AFEventParamClass: @"Deluxe",
  AFEventParamNumAdults: @2,
  AFEventParamNumChildren: @0,
  AFEventParamHotelScore: @9.6,
  AFEventParamPreferredStarRatings: @5,
  AFEventParamPreferredNeighborhoods: @"Centro",
  @"purchase_method": @"credit card",
  AFEventParamCouponCode: @"SUM2018",
  @"property_type": @"hotel"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventInitiatedCheckout, withValues: [
  AFEventParamCurrency: "GBP",
  AFEventParamPrice: 674,
  AFEventParamContentId: "ODIRNH",
  AFEventParamDateA: "2018/07/26",
  AFEventParamDateB: "2018/08/01",
  AFEventParamDestinationA: "London",
  AFEventParamDestinationB: "Madrid",
  AFEventParamClass: "Deluxe",
  AFEventParamNumAdults: 2,
  AFEventParamNumChildren: 0,
  AFEventParamHotelScore: 9.6,
  AFEventParamPreferredStarRatings: 5,
  AFEventParamPreferredNeighborhoods: "Centro",
  "purchase_method": "credit card",
  AFEventParamCouponCode: "SUM2018",
  "property_type": "hotel"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> InitiatedCheckout = 
			new Dictionary<string, string>();
InitiatedCheckout.Add("af_currency", "GBP");
InitiatedCheckout.Add("af_price", "674");
InitiatedCheckout.Add("af_content_id", "ODIRNH");
InitiatedCheckout.Add("af_date_a", "2018/07/26");
InitiatedCheckout.Add("af_date_b", "2018/08/01");
InitiatedCheckout.Add("af_destination_a", "London");
InitiatedCheckout.Add("af_destination_b", "Madrid");
InitiatedCheckout.Add("af_class", "Deluxe");
InitiatedCheckout.Add("af_num_adults", "2");
InitiatedCheckout.Add("af_num_children", "0");
InitiatedCheckout.Add("af_hotel_score", "9.6");
InitiatedCheckout.Add("af_preferred_star_ratings", "5");
InitiatedCheckout.Add("af_preferred_neighborhoods", "Centro");
InitiatedCheckout.Add("purchase_method", "credit card");
InitiatedCheckout.Add("af_coupon_code", "SUM2018");
InitiatedCheckout.Add("af_property_type", "hotel");
AppsFlyer.sendEvent("af_initiated_chekcout", InitiatedCheckout);
```

</Tab>
</Tabs>

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Achat (af_purchase)">

**Objectif**

Découvrir les tendances d'achat dans votre app de réservation d'hôtels. Cet évènement peut vous aider à :

* Déterminer la LTV de vos utilisateurs et le ROI de vos campagnes sur les réseaux publicitaires et les agences de publicité
* Déterminer quelles offres sont les plus populaires auprès de vos utilisateurs
* Réaliser une référence croisée de campagne avec les articles qui ont été achetés afin d'optimiser le ciblage de vos campagnes

**Déclencheur**

Lorsque l'utilisateur atterrit sur la page de remerciement une fois l'achat terminé

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Le revenu estimé provenant de l'achat | 1205.99 |
| af\_price | Montant global des achats | 4000 |
| af\_content\_id | ID de l'article | 121 |
| af\_content\_type | Catégorie de l'article | hotel |
| af\_currency | Code de devise | AUD |
| af\_quantity | Nombre d'articles dans le panier | 1 |
| af\_order\_id | ID de la commande générée après l'achat. | X123ABC |
| af\_receipt\_id | ID de commande, nécessaire pour l'intégration du retargeting CRITEO et Google Ad Words | X123ABC |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 4000);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "121");
// for multiple product categories, set the param value as: // new String {"121", "262"}
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "hotel");
// for multiple product categories,, set the param value as: new String {"hotel", "meals"}
eventValue.put(AFInAppEventParameterName.CURRENCY, "AUD");
eventValue.put(AFInAppEventParameterName.QUANTITY, 2);
// for multiple product categories, set the param value as: new int {2, 5}
eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "X123ABC");
eventValue.put("af_order_id", "X123ABC");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.PURCHASE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventPurchase
withValues: @{
  AFEventParamRevenue: @1205.99,
  AFEventParamPrice: @4000,
  AFEventParamContentId: @"121",
  // for multiple product categories, set the param value as:   
  // @[@"121", @"124"]
  AFEventParamContentType: @"hotel",
  // for multiple product categories, set the param value as:   
  // @[@"hotel", @"meals"]
  AFEventParamCurrency: @"AUD",
  AFEventParamQuantity: @2,
  // for multiple product categories, set the param value as:   
  // @[@2, @5]
  AFEventParamOrderId: @"X123ABC",
  AFEventParamReceiptId: @"X123ABC"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventPurchase, withValues: [
  AFEventParamRevenue: 1205.99,
  AFEventParamPrice: 4000,
  AFEventParamContentId: "121",
  // for multiple product categories, set the param value as: ["221", "124"],
  AFEventParamContentType: "hotel",
  // for multiple product categories, set the param value as: ["hotel", "meals"] 
  AFEventParamCurrency: "AUD",
  AFEventParamQuantity: 2,
  // for multiple product categories, set the param value as: [2, 5]
  AFEventParamOrderId: "X123ABC", 
  AFEventParamReceiptId: "X123ABC"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> PurchaseEvent = new Dictionary<string, string>();
PurchaseEvent.Add("af_revenue", "1205.99");
PurchaseEvent.Add("af_price", "4000");
PurchaseEvent.Add("af_content_id", "121");
// for multiple product categories, set the param value as: ["121", "124"]
PurchaseEvent.Add("af_content_type", "hotel");
// for multiple product categories, set the param value as: ["hotel", "meals"]
PurchaseEvent.Add("af_currency", "AUD");
PurchaseEvent.Add("af_quantity", "2");
// for multiple product categories, set the param value as: [2, 5] 
PurchaseEvent.Add("af_order_id", "X123ABC");
PurchaseEvent.Add("af_receipt_id", "X123ABC");
AppsFlyer.sendEvent ("af_purchase", PurchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Réservation de voyage (travel_booking)">

**Objectif**

Déterminer le taux de réservation global de votre app. Cet évènement peut vous aider à :

* Enregistrer les revenus générés par les réservations
* Connaître le nombre d'utilisateurs qui réservent un séjour avec leurs enfants
* Comprendre les tendances saisonnières
* Identifier les hôtels populaires

**Déclencheur**

Lorsque l'utilisateur atteint la page de remerciement après avoir réservé un hôtel

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Revenus des réservations | 647.95 |
| af\_currency | Code de devise | GBP |
| af\_price | Tarif en vigueur de l'hôtel | 674 |
| af\_content\_id | ID de l'hôtel | ODIRNH |
| af\_date\_a | 2018/07/26 | Date d'arrivée |
| af\_date\_b | Date de départ | 2018/08/01 |
| af\_destination\_a | Localisation de l'utilisateur | London |
| af\_destination\_b | Localisation de l'hôtel | Madrid |
| af\_class | Type de chambre | De luxe |
| af\_num\_adults | Nombre de clients | 2 |
| af\_num\_children | Nombre d'enfants | 0 |
| af\_hotel\_score | Note de l'hôtel selon les avis | 9.6 |
| af\_preferred\_star\_ratings | Nombre d'étoiles de l'hôtel préféré | 5 |
| af\_preferred\_neighborhoods | Zone dans laquelle se trouve l'hôtel | Centro |
| purchase\_method | Méthode d'achat | Carte de crédit |
| af\_coupon\_code | Code promotionnel ou points de fidélité | SUM2018 |
| property\_type | Type d'établissement | Hôtel |
| new\_booking | Première réservation de l'utilisateur | true |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REVENUE, 647.95);
eventValue.put(AFInAppEventParameterName.CURRENCY, "GBP");
eventValue.put(AFInAppEventParameterName.PRICE, 674);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "ODIRNH");
eventValue.put(AFInAppEventParameterName.DATE_A, "2018/07/26");
eventValue.put(AFInAppEventParameterName.DATE_B, "2018/08/01");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "London");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Madrid");
eventValue.put(AFInAppEventParameterName.CLASS, "Deluxe");
eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 2);
eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
eventValue.put(AFInAppEventParameterName.HOTEL_SCORE, 9.6);
eventValue.put(AFInAppEventParameterName.PREFERRED_STAR_RATINGS, 5);
eventValue.put(AFInAppEventParameterName.PREFERRED_NEIGHBORHOODS, "Centro");
eventValue.put("purchase_method", "credit card");
eventValue.put(AFInAppEventParameterName.COUPON_CODE, "SUM2018");
eventValue.put("property_type", "hotel");
eventValue.put("new_booking", true);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.TRAVEL_BOOKING, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventTravelBooking
withValues: @{
  AFEventParamRevenue: @647.95,
  AFEventParamCurrency: @"GBP",
  AFEventParamPrice: @674,
  AFEventParamContentId: @"ODIRNH",
  AFEventParamDateA: @"2018/07/26",
  AFEventParamDateB: @"2018/08/01",
  AFEventParamDestinationA: @"London",
  AFEventParamDestinationB: @"Madrid",
  AFEventParamClass: @"Deluxe",
  AFEventParamNumAdults: @2,
  AFEventParamNumChildren: @0,
  AFEventParamHotelScore: @9.6,
  AFEventParamPreferredStarRatings: @5,
  AFEventParamPreferredNeighborhoods: @"Centro",
  @"purchase_method": @"credit card",
  AFEventParamCouponCode: @"SUM2018",
  @"property_type": @"hotel",
  @"new_booking": @TRUE
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventTravelBooking, withValues: [
  AFEventParamRevenue: 647.95,
  AFEventParamCurrency: "GBP",
  AFEventParamPrice: 674,
  AFEventParamContentId: "ODIRNH",
  AFEventParamDateA: "2018/07/26",
  AFEventParamDateB: "2018/08/01",
  AFEventParamDestinationA: "London",
  AFEventParamDestinationB: "Madrid",
  AFEventParamClass: "Deluxe",
  AFEventParamNumAdults: 2,
  AFEventParamNumChildren: 0,
  AFEventParamHotelScore: 9.6,
  AFEventParamPreferredStarRatings: 5,
  AFEventParamPreferredNeighborhoods: "Centro",
  "purchase_method": "credit card",
  AFEventParamCouponCode: "SUM2018",
  "property_type": "hotel",
  "new_booking": true
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> TravelBooking = 
new Dictionary<string, string>();
TravelBooking.Add("af_revenue", "647.95");
TravelBooking.Add("af_currency", "GBP");
TravelBooking.Add("af_price", "674");
TravelBooking.Add("af_content_id", "ODIRNH");
TravelBooking.Add("af_date_a", "2018/07/26");
TravelBooking.Add("af_date_b", "2018/08/01");
TravelBooking.Add("af_destination_a", "London");
TravelBooking.Add("af_destination_b", "Madrid");
TravelBooking.Add("af_class", "Deluxe");
TravelBooking.Add("af_num_adults", "2");
TravelBooking.Add("af_num_children", "0");
TravelBooking.Add("af_hotel_score", "9.6");
TravelBooking.Add("af_preferred_star_ratings", "5");
TravelBooking.Add("af_preferred_neighborhoods", "Centro");
TravelBooking.Add("purchase_method", "credit card");
TravelBooking.Add("af_coupon_code", "SUM2018");
TravelBooking.Add("af_property_type", "hotel");
TravelBooking.Add("af_new_booking", "true");
AppsFlyer.sendEvent("af_travel_booking", TravelBookingEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Structures recommandées pour les événements personnalisés

La section suivante fournit une liste de structures d'événements qui comprennent des noms d'événements personnalisés et les suggestions de paramètres d'événement à utiliser. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<div id="first-purchase-first_purchase" />

<Accordion title="Premier achat (first_purchase)">

**Objectif**

Identique à l'événement [Achat](/docs/recommended-hotel-booking-app-events#purchase-af_purchase). Cet événement peut également vous aider à déterminer :

* Combien de temps il faut à un nouvel acheteur pour procéder à l'achat
* Les produits que les nouveaux acheteurs préfèrent acheter
* Le prix moyen et les revenus issus des premiers achats

**Déclencheur**

Lorsque l'utilisateur finalise son premier achat

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Revenu des achats | 1205.95 |
| af\_price | Montant global des achats | 4000 |
| af\_content\_id | ID de l'article | 121, 262 |
| af\_content\_type | Catégorie de l'article | hotel |
| af\_currency | Devise | AUD |
| af\_quantity | Quantité d'articles dans le panier | 1 |
| af\_order\_id | ID de la commande qui est généré après l'achat. | X123ABC |
| af\_receipt\_id | ID de commande, nécessaire pour l'intégration du retargeting CRITEO et Google AdWords | X123ABC |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 4000);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "221");
// for multiple product categories, set the param value as: new String {"221", "124"}
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "hotel");
// for multiple product categories set the param value as: new String {"hotel", "meals"}
eventValue.put(AFInAppEventParameteName.CURRENCY, "USD");
eventValue.put(AFInAppEventParameterName.QUANTITY, 2);
// for multiple product categories, set the param value as: new int {1}
eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "X123ABC");
eventValue.put("af_order_id", "X123ABC");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "first_purchase", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:("first_purchase")
withValues: @{
  AFEventParamRevenue: @1205.95,
  AFEventParamPrice: @4000,
  AFEventParamContentId: @"221",
  // for multiple product categories, set the param value as: @[@"221", @"124"]
  AFEventParamContentType: @"hotel",
  // for multiple product categories, set the param value as: @[@"hotel", @"meals"]
  AFEventParamCurrency: @"USD",
  AFEventParamQuantity: @2,
  // for multiple product categories, set the param value as: @[@1]
  AFEventParamOrderId: @"X123ABC",
  AFEventParamReceiptId: @"X123ABC"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("first_purchase", withValues: [ 
  AFEventParamRevenue: 1205.95,
  AFEventParamPrice: 4000,
  AFEventParamContentId: "221",
  // for multiple product categories, set the param value as: ["221", "124"]
  AFEventParamContentType: "hotel",
  // for multiple product categories, set the param value as: ["hotel", "meals"]
  AFEventParamCurrency: "USD",
  AFEventParamQuantity: 2,
  // for multiple product categories, set the param value as: // [1]
  AFEventParamOrderId: "X123ABC",
  AFEventParamReceiptId: "X123ABC"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> FirstPurchaseEvent = new Dictionary<string, string>();
FirstPurchaseEvent.Add("af_revenue", "1205.95");
FirstPurchaseEvent.Add("af_price", "4000");
FirstPurchaseEvent.Add("af_content_id", "121");
// for multiple product categories, set the param value as: ["221", "124"]
FirstPurchaseEvent.Add("af_content_type", "hotel");
// for multiple product categories, set the param value as: ["hotel", "meals"]
FirstPurchaseEvent.Add("af_currency", "USD");
FirstPurchaseEvent.Add("af_quantity", "2");
// for multiple product categories, set the param value as: [1] 
FirstPurchaseEvent.Add("af_order_id", "X123ABC");
FirstPurchaseEvent.Add("af_receipt_id", "X123ABC");
AppsFlyer.sendEvent ("first_purchase", FirstPurchaseEvent);
```

</Tab>
</Tabs>

</Accordion>
