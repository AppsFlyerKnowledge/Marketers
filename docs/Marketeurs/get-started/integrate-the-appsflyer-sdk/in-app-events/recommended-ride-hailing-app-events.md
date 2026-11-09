---
title: Événements recommandés pour les apps de transport
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
  created_at: '2021-04-29T08:42:34Z'
  edited_at: '2022-01-25T17:24:49Z'
  id: 360019651957
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/360019651957
---
> **En bref :** mesurez la qualité de vos utilisateurs tout au long de leur parcours en enregistrant ces événements in-app suggérés pour votre app de transport.

<div id="-ride-hailing" />

## <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="100px" /> Transport

Les apps de transport sont récemment devenues très populaires, en particulier dans les zones urbaines où la plupart des résidents ne possèdent pas de voiture. Les événements typiques que nous recommandons d'enregistrer incluent les demandes et les réservations de transport.

L'enregistrement de ces évènements peut vous aider à déterminer :

* La façon dont les passagers et les conducteurs interagissent
* Les pays dans lesquels plus de personnes utilisent votre service de transport
* Les métriques de prix, de trajets et de distance parcourue

<div id="important" />

> 🚧 **Important !**
>
> * Veillez à lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#introduction-setting-up-inapp-events">instructions</Anchor> à l'attention des marketeurs pour implémenter les événements in-app.
> * Pour simplifier l'implémentation,  [téléchargez un fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSJsgqgzIInw8NAzY8ILsk2H4Vjp-7dRIc1Ed6vNb34mOayiTjutUs-cOnd4H5u18EvgpspKe7Dx2xb/pub?gid=1823896228&single=true&output=csv) contenant tous les événements in-app de base décrits dans cet article,  puis modifiez les événements en fonction des besoins de votre entreprise. Partagez ensuite le fichier avec votre développeur.
> * Pour chaque événement recommandé que contient cet article, vous trouverez des extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour plus d'informations sur l'enregistrement des événements in-app, consultez le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">guide des événements in-app riches</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events_ride_hailing_app_user_journey" src="https://files.readme.io/5ec4efcc699ef8749e1d5cd6e693472713f3d7945a41e1601965d0e7cdb68706-4402678863377.png" />

<div id="recommended-structures-for-predefined-events" />

## Structures recommandées pour les événements prédéfinis

La section suivante fournit une liste des structures d'événements typiques du secteur du transport. Chaque structure donne un nom d'événement prédéfini, ainsi que des suggestions de paramètres d'événement à appliquer. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Inscription terminée (af_complete_registration)">

**Objectif**

Cet évènement peut vous aider à :

* Déterminer les méthodes d'inscription préférées des utilisateurs
* Découvrir combien d'utilisateurs s'inscrivent réellement après avoir téléchargé et installé l'app
* Découvrir les tendances d'inscription dans tous les pays pour déterminer les pays dans lesquels les utilisateurs sont plus susceptibles d'utiliser votre app.

**Déclencheur**

Lorsque l'utilisateur finalise le processus d'inscription

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_registration\_method | Plate-forme ou méthode via laquelle l'utilisateur s'inscrit | Facebook |
| country\_code | Code pays (code téléphonique) | 66 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REGSITRATION_METHOD, "shoes");
eventValue.put("country_code", "66");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.COMPLETE_REGISTRATION, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventCompleteRegistration
withValues: @{
  AFEventParamRegistrationMethod: @"Facebook",
  @"country_code": @"66",
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventCompleteRegistration, 
withValues: [
  AFEventParamRegistrationMethod: "Facebook",
	  "country_code": "66"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CompleteRegistrationEvent = new Dictionary<string, string>();
CompleteRegistrationEvent.Add("af_registration_method", "Facebook");
CompleteRegistrationEvent.Add("country_code", "66");
AppsFlyer.sendEvent("af_complete_registration", CompleteRegistrationEvent);
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
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.LOGIN, null);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventLogin withValues: nil];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventLogin, withValues: nil);
```

</Tab>

<Tab title="Unity">

```csharp
AppsFlyer.sendEvent("af_login", null);
```

</Tab>
</Tabs>

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Ajouter des informations de paiement (af_add_payment_info)">

**Objectif**

Catégoriser les utilisateurs. Vous pouvez :

* Savoir combien de temps il faut à un utilisateur pour ajouter ses informations de paiement
* Identifier les méthodes de paiement les plus populaires, par exemple, la carte de crédit ou les portefeuilles électroniques
* Organiser des campagnes et des collaborations avec les fournisseurs de méthodes de paiement populaires

**Déclencheur**

Lorsque l'utilisateur ajoute avec succès des informations de paiement à son compte

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_success | Si l'ajout de la méthode de paiement a réussi ou non | true |
| credit\_card\_type | Type de carte de crédit (facultatif) | Visa, Mastercard |
| payment\_method\_type | Le type de méthode de paiement | carte de crédit, portefeuille électronique |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.SUCCESS, true);
eventValue.put("credit_card_type", "Visa");
eventValue.put("payment_method_type", true);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.ADD_PAYMENT_INFO, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventAddPaymentInfo
withValues: @{
  AFEventParamSuccess: @TRUE,
	  @"credit_card_type": @"Visa",
	  @"payment_method_type": @"credit card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventAddPaymentInfo, withValues: [
  AFEventParamSuccess: true,
	  "credit_card_type": "Visa",
	  "payment_method_type": "credit card"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> AddPaymentInfoEvent = new Dictionary<string, string>();
AddPaymentInfoEvent.Add("af_success", "true");
AddPaymentInfoEvent.Add("credit_card_type", "Visa");
AddPaymentInfoEvent.Add("payment_method_type", "credit card");
AppsFlyer.sendEvent("af_add_payment_info", AddPaymentInfoEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="Crédits dépensés (af_spent_credits)">

**Objectif**

L'événement [Réservation de trajet terminée](/docs/recommended-ride-hailing-app-events#ride-booking-completed-ride_booking_completed) comprend un paramètre nommé `credits_earned`. Cet attribut consigne les crédits que le passager gagne pour chaque trajet. Le passager peut ensuite échanger ces crédits contre des bons ou des remises.

Cet évènement peut vous aider à :

* Connaître le nombre de passagers qui échangent leurs crédits contre des bons
* Découvrir quel type de bons et de remises les passagers préfèrent

**Déclencheur**

Quand un passager dépense des crédits

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_content | Type de bon ou de remise | Billet de cinéma |
| credits\_used | Le nombre de crédits utilisés | 1000 |
| credits\_remaining | Le nombre de crédits restant sur le compte | 2090 |
| invoice\_id | ID de la facture créée pour les crédits dépensés | KO215123SD |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT, "Single movie ticket");
eventValue.put("credits_used", 1000);
eventValue.put("invoice_id", "");
eventValue.put("credits_remaining", "KO215123SD");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.SPENT_CREDITS , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"af_spent_credits"
withValues: @{
 AFEventParamContent: @"Single movie ticket",
 @"credits_used": @1000,
 @"credits_remaining": @2090,
 @"invoice_id": @"KO215123SD"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("af_spent_credits", 
withValues: [
 AFEventParamContent: "Single movie ticket",
 "credits_used": 1000,
 "credits_remaining": 2090,
 "invoice_id": "KO215123SD"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CreditsSpent = new Dictionary<string, string>();
CreditsSpent.Add("af_content", "Single movie ticket");
CreditsSpent.Add("credits_used", "1000");
CreditsSpent.Add("credits_remaining", "2090");
CreditsSpent.Add("invoice_id", "KO215123SD");
AppsFlyer.sendEvent("af_content_view", CreditsSpent);
```

</Tab>
</Tabs>

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Structures recommandées pour les événements personnalisés

La section suivante fournit une liste de structures d'événements qui comprennent des noms d'événements personnalisés et les suggestions de paramètres d'événement à utiliser. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<div id="ride-booking-requested-ride_booking_requested" />

<Accordion title="Demande de réservation de trajet (ride_booking_requested)">

**Objectif**

Cet évènement peut vous aider à :

* Découvrir les destinations populaires.
* Découvrir les tendances, savoir où les personnes se rendent et d'où elles partent
* Connaître la distance moyenne d'un trajet
* Découvrir de quels pays, régions et villes les utilisateurs sont originaires

De plus, enregistrer cet évènement et les autres évènements liés à la réservation peut vous aider à enregistrer les transactions réussies. Vous pouvez suivre les transactions réussies et les comparer aux transactions infructueuses. Par exemple, vous pouvez voir combien de réservations de trajet sont demandées et le nombre de réservations de trajet terminées ou abandonnées.

**Déclencheur**

Lorsque l'usager a créé une demande de réservation de trajet

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Prix indiqué pour le trajet | 22.4 |
| af\_currency | Devise | SGD |
| af\_destination\_a | Point de départ | Plaza Singapura |
| af\_destination\_b | Point d'arrivée | Marina Bay Sands |
| distance | Distance entre les deux destinations | 5.2 |
| af\_content\_type | Type de transport | Taxi |
| payment\_method\_type | Le type de méthode de paiement | carte de crédit, portefeuille électronique |
| af\_city | Ville dans laquelle le trajet est réservé | Singapore |
| af\_region | Région dans laquelle le trajet est réservé | SFA |
| af\_country | Pays dans lequel le trajet est réservé | Singapore |
| order\_id | ID de la commande | 135790 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 22.4);
eventValue.put(AFInAppEventParameterName.CURRENCY, "SGD");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "Plaza Singapura");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Marina Bay Sands");
eventValue.put("distance", 5.2);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "Taxi");
eventValue.put("payment_method_type", "credit card");
eventValue.put("notes", "Taxi stand");
eventValue.put(AFInAppEventParameterName.CITY, "Singapore");
eventValue.put(AFInAppEventParameterName.REGION, "SFA");
eventValue.put(AFInAppEventParameterName.COUNTRY, "Singapore");
eventValue.put("af_order_id", "135790");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "ride_booking_requested", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"ride_booking_requested"
withValues: @{
  AFEventParamPrice: @22.4,
  AFEventParamCurrency: @"SGD",
  AFEventParamDestinationA: @"Plaza Singapura",
  AFEventParamDestinationB: @"Marina Bay Sands",
  @"distance": @5.2,
  AFEventParamContentType: @"Taxi",
  @"payment_method_type": @"credit card",
	  @"notes": @"Taxi stand",
  AFEventParamCity: @"Singapore",
  AFEventParamRegion: @"SFA",
  AFEventParamCountry: @"Singapore",
  AFEventParamOrderId: @"135790"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("ride_booking_requested", 
withValues: [
 AFEventParamPrice: 22.4,
	 AFEventParamCurrency: "SGD",
	 AFEventParamDestinationA: "Plaza Singapura",
	 AFEventParamDestinationB: "Marina Bay Sands",
	 "distance": 5.2,
	 AFEventParamContentType: "Taxi",
	 "payment_method_type": "credit card",
	 "notes": "Taxi stand",
	 AFEventParamCity: "Singapore",
	 AFEventParamRegion: "SFA",
	 AFEventParamCountry: "Singapore",
	 AFEventParamOrderId: "135790"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RideBookingRequestedEvent = new Dictionary<string, string>();
RideBookingRequestedEvent.Add("af_price", "22.4");
RideBookingRequestedEvent.Add("af_currency", "SGD");
RideBookingRequestedEvent.Add("af_destination_a", "Plaza Singapura");
RideBookingRequestedEvent.Add("af_destination_b", "Marina Bay Sands");
RideBookingRequestedEvent.Add("distance", "5.2");
RideBookingRequestedEvent.Add("af_content_type", "Taxi");
RideBookingRequestedEvent.Add("payment_method_type", "credit card");
RideBookingRequestedEvent.Add("notes", "Taxi stand");
RideBookingRequestedEvent.Add("af_city", "Singapore");
RideBookingRequestedEvent.Add("af_region", "SFA");
RideBookingRequestedEvent.Add("af_country", "Singapore");
RideBookingRequestedEvent.Add("af_order_id", "135790");
AppsFlyer.sendEvent("ride_booking_requested", RideBookingRequestedEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="ride-booking-confirmed-ride_booking_confirmed" />

<Accordion title="Réservation de trajet confirmée (ride_booking_confirmed)">

**Objectif**

Cet évènement peut vous aider à :

* Découvrir qui sont les conducteurs les plus actifs
* Découvrir quelles destinations sont fréquentes chez les conducteurs
* Voir le prix moyen et total des trajets pour chaque conducteur

De plus, enregistrer cet évènement et les trois autres évènements liés à la réservation peut vous aider à mieux comprendre les activités du conducteur. Vous pouvez notamment voir les conducteurs qui confirment le plus de demandes de réservations de trajets, ceux qui préfèrent les trajets courts.

<div id="trigger" />

#### **Déclencheur**

Lorsque la réservation est acceptée par un conducteur

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Prix indiqué pour le trajet | 22.4 |
| af\_currency | Devise | SGD |
| af\_destination\_a | Point de départ | Plaza Singapura |
| af\_destination\_b | Point d'arrivée | Marina Bay Sands |
| distance | Distance entre les deux destinations | 5.2 |
| af\_content\_type | Type de transport | Taxi |
| driver\_id | ID du conducteur qui a confirmé faire le trajet | 1706 |
| payment\_method\_type | Le type de méthode de paiement | carte de crédit, portefeuille électronique |
| af\_city | Ville dans laquelle le trajet est réservé | Singapore |
| af\_region | Région dans laquelle le trajet est réservé | SFA |
| af\_country | Pays dans lequel le trajet est réservé | Singapore |
| af\_order\_id | ID de la commande | 135790 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 22.4);
eventValue.put(AFInAppEventParameterName.CURRENCY, "SGD");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "Plaza Singapura");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Marina Bay Sands");
eventValue.put("distance", 5.2);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "Taxi");
eventValue.put("driver_id", "1706");
eventValue.put("payment_method_type", "credit card");
eventValue.put("notes", "Taxi stand");
eventValue.put(AFInAppEventParameterName.CITY, "Singapore");
eventValue.put(AFInAppEventParameterName.REGION, "SFA");
eventValue.put(AFInAppEventParameterName.COUNTRY, "Singapore");
eventValue.put("af_order_id", "135790");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "ride_booking_confirmed", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"ride_booking_confirmed"
withValues: @{
 AFEventParamPrice: @22.4,
 AFEventParamCurrency: @"SGD",
 AFEventParamDestinationA: @"Plaza Singapura",
 AFEventParamDestinationB: @"Marina Bay Sands",
 @"distance": @5.2,
 AFEventParamContentType: @"Taxi",
	 @"driver_id": @"1706",
 @"payment_method_type": @"credit card",
	 @"notes": @"Taxi stand",
 AFEventParamCity: @"Singapore",
 AFEventParamRegion: @"SFA",
 AFEventParamCountry: @"Singapore",
 AFEventParamOrderId: @"135790"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("ride_booking_confirmed", 
withValues: [
 AFEventParamPrice: 22.4,
 AFEventParamCurrency: "SGD",
 AFEventParamDestinationA: "Plaza Singapura",
 AFEventParamDestinationB: "Marina Bay Sands",
 "distance": 5.2,
 AFEventParamContentType: "Taxi",
 "driver_id": "1706",
 "payment_method_type": "credit card",
 "notes": "Taxi stand",
 AFEventParamCity: "Singapore",
 AFEventParamRegion: "SFA",
 AFEventParamCountry: "Singapore", 
 AFEventParamOrderId: "135790"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RideBookingConfirmedEvent = new Dictionary<string, string>();
RideBookingConfirmedEvent.Add("af_price", "22.4");
RideBookingConfirmedEvent.Add("af_currency", "SGD");
RideBookingConfirmedEvent.Add("af_destination_a", "Plaza Singapura");
RideBookingConfirmedEvent.Add("af_destination_b", "Marina Bay Sands");
RideBookingConfirmedEvent.Add("distance", "5.2");
RideBookingConfirmedEvent.Add("af_content_type", "Taxi");
RideBookingConfirmedEvent.Add("driver_id", "1706");
RideBookingConfirmedEvent.Add("payment_method_type", "credit card");
RideBookingConfirmedEvent.Add("notes", "Taxi stand");
RideBookingConfirmedEvent.Add("af_city", "Singapore");
RideBookingConfirmedEvent.Add("af_region", "SFA");
RideBookingConfirmedEvent.Add("af_country", "Singapore");
RideBookingConfirmedEvent.Add("af_order_id", "135790");
AppsFlyer.sendEvent("ride_booking_confirmed", RideBookingConfirmedEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="ride-booking-canceled-ride_booking_canceled" />

<Accordion title="Réservation de trajet annulée (ride_booking_canceled)">

**Objectif**

Cet évènement peut vous aider à :

* Enregistrer les conducteurs ou les passagers qui annulent constamment
* Découvrir le nombre de trajets annulés
* Mettre en corrélation le taux d'annulation avec des attributs tels que le prix, la destination, la distance, les villes
* Découvrir pourquoi un trajet est annulé

**Déclencheur**

Lorsque la réservation est annulée

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Prix indiqué pour le trajet | 22.4 |
| af\_currency | Devise | SGD |
| af\_destination\_a | Point de départ | Plaza Singapura |
| af\_destination\_b | Point d'arrivée | Marina Bay Sands |
| distance | Distance entre les deux destinations | 5.2 |
| af\_content\_type | Type de transport | Taxi |
| driver\_id | ID du conducteur qui a confirmé le trajet | 1706 |
| cancelation\_reason | Raison pour laquelle le trajet est annulé | le prix est trop élevé, le conducteur n'était pas là, le passager n'était pas là |
| payment\_method\_type | Le type de méthode de paiement | carte de crédit, portefeuille électronique |
| af\_city | Ville dans laquelle le trajet est réservé | Singapore |
| af\_region | Région dans laquelle le trajet est réservé | SFA |
| af\_country | Pays dans lequel le trajet est réservé | Singapore |
| order\_id | ID de la commande | 135790 |
| canceled\_by | Si le trajet soit annulé par le passager ou le conducteur | Passager |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 22.4);
eventValue.put(AFInAppEventParameterName.CURRENCY, "SGD");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "Plaza Singapura");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Marina Bay Sands");
eventValue.put("distance", 5.2);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "Taxi");
eventValue.put("driver_id", "1706");
eventValue.put("cancellation_reason", "driver didn't show up");
eventValue.put("payment_method_type", "credit card");
eventValue.put("notes", "Taxi stand");
eventValue.put(AFInAppEventParameterName.CITY, "Singapore");
eventValue.put(AFInAppEventParameterName.REGION, "SFA");
eventValue.put(AFInAppEventParameterName.COUNTRY, "Singapore");
eventValue.put("af_order_id", "135790");
eventValue.put("canceled_by", "passenger");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "ride_booking_canceled", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"ride_booking_canceled"
withValues: @{
 AFEventParamPrice: @22.4,
 AFEventParamCurrency: @"SGD",
 AFEventParamDestinationA: @"Plaza Singapura",
 AFEventParamDestinationB: @"Marina Bay Sands",
 @"distance": @5.2,
 AFEventParamContentType: @"Taxi",
 @"driver_id": @"1706",
 @"cancelation_reason": @"driver didn't show up",
 @"payment_method_type": @"credit card",
 @"notes": @"Taxi stand",
 AFEventParamCity: @"Singapore",
 AFEventParamRegion: @"SFA",
 AFEventParamCountry: @"Singapore",
 AFEventParamOrderId: @"135790",
 @"canceled_by": @"passenger"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("ride_booking_canceled", 
withValues: [
 AFEventParamPrice: 22.4,
 AFEventParamCurrency: "SGD",
 AFEventParamDestinationA: "Plaza Singapura",
 AFEventParamDestinationB: "Marina Bay Sands",
 "distance": 5.2,
	 AFEventParamContentType: "Taxi",
 "driver_id": "1706",
 "cancelation_reason": "driver didn't show up",
 "payment_method_type": "credit card",
	 "notes": "Taxi stand",
 AFEventParamCity: "Singapore",
 AFEventParamRegion: "SFA",
 AFEventParamCountry: "Singapore",
 AFEventParamOrderId: "135790",
 "canceled_by": "passenger"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RideBookingCanceledEvent = new Dictionary<string, string>();
RideBookingCanceledEvent.Add("af_price", "22.4");
RideBookingCanceledEvent.Add("af_currency", "SGD");
RideBookingCanceledEvent.Add("af_destination_a", "Plaza Singapura");
RideBookingCanceledEvent.Add("af_destination_b", "Marina Bay Sands");
RideBookingCanceledEvent.Add("distance", "5.2");
RideBookingCanceledEvent.Add("af_content_type", "Taxi");
RideBookingCanceledEvent.Add("driver_id", "1706");
RideBookingCanceledEvent.Add("cancelation_reason", "driver didn't show up");
RideBookingCanceledEvent.Add("payment_method_type", "credit card");
RideBookingCanceledEvent.Add("notes", "Taxi stand");
RideBookingCanceledEvent.Add("af_city", "Singapore");
RideBookingCanceledEvent.Add("af_region", "SFA");
RideBookingCanceledEvent.Add("af_country", "Singapore");
RideBookingCanceledEvent.Add("af_order_id", "135790");
RideBookingCanceledEvent.Add("canceled_by", "passenger");
AppsFlyer.sendEvent("ride_booking_cancelled", RideBookingCanceledEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="ride-booking-completed-ride_booking_completed" />

<Accordion title="Réservation de trajet terminée (ride_booking_completed)">

**Objectif**

Cet évènement peut vous aider à :

* Découvrir les dépenses des passagers et les revenus des conducteurs
* Mettre en corrélation les trajets terminés avec des attributs tels que la destination, le type de paiement, l'ID du conducteur
* Découvrir la distance moyenne et totale pour les conducteurs et les passagers
* Comparer les trajets terminés aux trajets annulés
* Enregistrer et suivre le score des conducteurs

**Déclencheur**

Quand le trajet est terminé

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Prix indiqué pour le trajet | 22.4 |
| af\_currency | Devise | SGD |
| af\_destination\_a | Point de départ | Plaza Singapura |
| af\_destination\_b | Point d'arrivée | Marina Bay Sands |
| distance | Distance entre les deux destinations | 5.2 |
| af\_content\_type | Type de transport | Taxi |
| driver\_id | ID du conducteur qui a confirmé faire le trajet | 1706 |
| payment\_method\_type | Le type de méthode de paiement | carte de crédit, portefeuille électronique |
| af\_city | Ville dans laquelle le trajet est réservé | Singapore |
| af\_region | Région dans laquelle le trajet est réservé | SFA |
| af\_country | Pays dans lequel le trajet est réservé | Singapore |
| order\_id | ID de la commande | 135790 |
| credits\_earned | Les crédits que le passager a gagnés en terminant un trajet | 248 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 22.4);
eventValue.put(AFInAppEventParameterName.CURRENCY, "SGD");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "Plaza Singapura");
eventValue.put(AFInAppEventParameterName.DESTINATION_B,"Marina Bay Sands");
eventValue.put("distance", 5.2);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "Taxi");
eventValue.put("driver_id", "1706");
eventValue.put("payment_method_type", "credit card");
eventValue.put("notes", "Taxi stand");
eventValue.put(AFInAppEventParameterName.CITY, "Singapore");
eventValue.put(AFInAppEventParameterName.REGION, "SFA");
eventValue.put(AFInAppEventParameterName.COUNTRY, "Singapore");
eventValue.put("af_order_id", "135790");
eventValue.put("credits_earned", 248);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "ride_booking_completed" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"ride_booking_completed"
withValues: @{
  AFEventParamPrice: @22.4,
  AFEventParamCurrency: @"SGD",
  AFEventParamDestinationA: @"Plaza Singapura",
  AFEventParamDestinationB: @"Marina Bay Sands",
  @"distance": @5.2,
  AFEventParamContentType: @"Taxi",
  @"driver_id": @"1706",
  @"payment_method_type": @"credit card",
  @"notes": @"Taxi stand",
  AFEventParamCity: @"Singapore",
  AFEventParamRegion: @"SFA",
  AFEventParamCountry: @"Singapore",
  AFEventParamOrderId: @"135790",
  @"credits_earned": @248
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("ride_booking_completed", 
withValues: [
  AFEventParamPrice: 22.4,
  AFEventParamCurrency: "SGD",
  AFEventParamDestinationA: "Plaza Singapura",
  AFEventParamDestinationB: "Marina Bay Sands",
  distance": 5.2,
  AFEventParamContentType: "Taxi",
  "driver_id": "1706",
  "payment_method_type": "credit card",
  "notes": "Taxi stand",
  AFEventParamCity: "Singapore",
  AFEventParamRegion: "SFA",
  AFEventParamCountry: "Singapore",
  AFEventParamOrderId: "135790",
  "credits_earned": 248
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RideBookingCompletedEvent = new Dictionary<string, string>();
RideBookingCompletedEvent.Add("af_price", "22.4");
RideBookingCompletedEvent.Add("af_currency", "SGD");
RideBookingCompletedEvent.Add("af_destination_a", "Plaza Singapura");
RideBookingCompletedEvent.Add("af_destination_b", "Marina Bay Sands");
RideBookingCompletedEvent.Add("distance", "5.2");
RideBookingCompletedEvent.Add("af_content_type", "Taxi");
RideBookingCompletedEvent.Add("driver_id", "1706");
RideBookingCompletedEvent.Add("payment_method_type", "credit card");
RideBookingCompletedEvent.Add("notes", "Taxi stand");
RideBookingCompletedEvent.Add("af_city", "Singapore");
RideBookingCompletedEvent.Add("af_region", "SFA");
RideBookingCompletedEvent.Add("af_country", "Singapore");
RideBookingCompletedEvent.Add("af_order_id", "135790");
AppsFlyer.sendEvent("ride_booking_completed", RideBookingCompletedEvent);
```

</Tab>
</Tabs>

</Accordion>
