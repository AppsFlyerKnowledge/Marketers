---
title: Événements recommandés pour les apps de soins de santé
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
  created_at: '2021-05-01T10:41:05Z'
  edited_at: '2022-01-25T17:23:37Z'
  id: 360019888518
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/360019888518
---
> **En bref :** mesurez la qualité de vos utilisateurs tout au long de leur parcours en enregistrant ces suggestions d'événements in-app pour votre app de soins de santé .

<div id="-healthcare" />

## <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="100px" /> Soins médicaux

Les apps de soins médicaux permettent aux utilisateurs d'effectuer des tâches telles que souscrire une assurance maladie, prendre des rendez-vous et recevoir des conseils médicaux. Les événements typiques que nous recommandons d'enregistrer incluent les achats et les réservations.

L'enregistrement de ces évènements peut vous aider à déterminer :

* Quels médicaments sont les plus utilisés et demandés
* Quels emballages préfèrent les utilisateurs
* Quels problèmes de santé préoccupent le plus les utilisateurs

<div id="important" />

> 🚧 **Important !**
>
> * Veillez à lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#introduction-setting-up-inapp-events">instructions</Anchor> à l'attention des marketeurs pour implémenter les événements in-app.
> * Pour simplifier l'implémentation, [téléchargez un fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSJsgqgzIInw8NAzY8ILsk2H4Vjp-7dRIc1Ed6vNb34mOayiTjutUs-cOnd4H5u18EvgpspKe7Dx2xb/pub?gid=455898016&single=true&output=csv) contenant tous les événements in-app de base décrits dans cet article, puis modifiez les événements en fonction des besoins de votre entreprise. Une fois terminé, partagez le fichier avec votre développeur.
> * Pour chaque événement recommandé que contient cet article, vous trouverez des extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour plus d'informations sur l'enregistrement des événements in-app, consultez le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">guide des événements in-app riches</Anchor>.

<Image align="center" alt="In_appEvents__Healthcare__en-us.png" src="https://files.readme.io/43ae6b0684c26ae42d43b0247a547e7f54e18bf1be66d6b188aaaf9e2274ca98-4404607774353.png" />

<div id="purchase-af_purchase" />

<div id="add-to-cart-af_add_to_cart" />

<div id="complete-registration-af_complete_registration" />

<div id="login-af_login" />

<div id="recommended-structures-for-predefined-events" />

## Structures recommandées pour les événements prédéfinis

La section suivante fournit une liste des structures d'événements typiques du secteur des soins médicaux. Chaque structure donne un nom d'événement prédéfini, ainsi que des suggestions de paramètres d'événement à appliquer. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<Accordion title="Connexion (af_login)">

**Objectif**

Comprendre le taux de rétention de vos utilisateurs inscrits

**Déclencheur**

Dès que l'utilisateur se connecte avec succès

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
AppsFlyer.sendEvent ("af_login", null);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Inscription terminée (af_complete_registration)">

**Objectif**

Découvrir combien d'utilisateurs ont installé l'app et sont allés au bout du processus d'inscription, et quelles méthodes d'inscription vos utilisateurs privilégient.

**Déclencheur**

Lorsque l'utilisateur finalise le processus d'inscription

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_registration\_method | Le type de méthode d'inscription | email, facebook |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put(AFInAppEventParameterName.REGISTRATION_METHOD, "Facebook");
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
Dictionary<string, string> CompleteRegistrationEvent = new Dictionary<string, string>();
CompleteRegistrationEvent.Add("af_registration_method", "Facebook");
AppsFlyer.sendEvent ("af_complete_registration", CompleteRegistrationEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Ajouter au panier (af_add_to_cart)">

**Objectif**

Enregistrez l'ajout de produits au panier. Cet événement peut vous aider à déterminer :

* Le nombre de produits que les acheteurs ajoutent en moyenne lors d'un achat
* Le temps qui s'écoule entre l'ajout de deux produits différents
* le nombre d'acheteurs qui abandonnent leur panier

**Déclencheur**

Lorsque l'utilisateur ajoute un produit au panier

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| medicine\_name | Nom du médicament | rhinos |
| af\_quantity | Montant commandé | 1 |
| af\_price | Prix du médicament | 10 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("medicine name", "rhinos");
eventValue.put("quantity", "1");
eventValue.put("price", "10");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "add_to_cart", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"add_to_cart" withValues: @{ 
@"medicine name": @"rhinos", 
@"quantity": @"1", 
@"price": @"10"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("add_to_cart", withValues: 
[ "medicine name": "rhinos",
"quantity": "1",
"price": "10"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> AddToCartEvent= new Dictionary<string, string>();
AddToCartEvent.Add("medicine name", "rhinos");
AddToCartEvent.Add("quantity", "1");
AddToCartEvent.Add("price", "10");
AppsFlyer.sendEvent ("add_to_cart", AddToCartEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Achat (af_purchase)">

**Objectif**

Enregistrez les achats in-app effectués par les utilisateurs. Cet évènement peut vous aider à :

* Déterminer la LTV de vos utilisateurs et le ROI de vos campagnes sur les réseaux publicitaires et les agences de publicité
* Déterminer quelles offres sont les plus populaires auprès de vos utilisateurs
* Réaliser une référence croisée de campagne avec les articles qui ont été achetés afin d'optimiser le ciblage de vos campagnes

**Déclencheur**

Lorsque l'utilisateur atterrit sur la page de remerciement une fois l'achat terminé

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Revenu des achats | 50.55 |
| af\_currency | Code de devise | USD |
| af\_content\_type | Nom de l'achat | labo |
| af\_order\_id | ID de la commande | 9277 |
| payment\_method\_type | Mode de paiement utilisé | carte de crédit, locale |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put(AFInAppEventParameterName.REVENUE, 50.55);
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "lab");
eventValue.put("AFInAppEventParameterName.ORDER_ID", "9277");
eventValue.put("payment_method_type", "credit card");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),AFInAppEventType.PURCHASE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventPurchase
withValues: @{
   AFEventParamRevenue: @50.55,
   AFEventParamCurrency: @"USD",
   AFEventParamContentType: @"lab",
   AFEventParamContentTypeOrderId: @"9277",
   @"payment_method_type": @"credit card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventPurchase, 
withValues: [
   AFEventParamRevenue: 50.55,
   AFEventParamCurrency: "USD",
   AFEventParamContentType: "lab",
   AFEventParamContentTypeOrderId: "9277",
   "payment_method_type": "credit card",
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> purchaseEvent = new Dictionary<string, string>();
purchaseEvent.Add("af_revenue", "50.55");
purchaseEvent.Add("af_currency", "USD");
purchaseEvent.Add("af_content_type", "lab");
purchaseEvent.Add("af_order_id", "9277");
purchaseEvent.Add("payment_method_type", "credit card");
AppsFlyer.sendEvent ("af_purchase", purchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="topup-success-top_up_success" />

<div id="recommended-structures-for-custom-events" />

## Structures recommandées pour les événements personnalisés

La section suivante fournit une liste de structures d'événements qui comprennent des noms d'événements personnalisés et les suggestions de paramètres d'événement à utiliser. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<Accordion title="Rendez-vous confirmé (confirmed_appointment)">

**Objectif**

En enregistrant cet événement, vous pouvez utiliser les données pour recibler les utilisateurs et envoyer des rappels pour les examens réguliers et les rendez-vous futurs.

**Déclencheur**

Lorsque l'utilisateur prend rendez-vous

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| doctor\_name | Nom du médecin | Julie Robert |
| appointment\_number | Numéro du rendez-vous | 001 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("doctor_name", "Robert James");
eventValue.put("appointment_number", "001");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "confirmed_appointment", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"confirmed_appointment" withValues: @{ 
@"doctor_name": @"Robert James", 
@"appointment_number": @"001"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("confirmed_appointment", withValues: 
[ "doctor_name": "Robert James",
"appointment_number": "001"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ConfirmedAppointmentEvent= new Dictionary<string, string>();
ConfirmedAppointmentEvent.Add("doctor_name", "Robert James");
ConfirmedAppointmentEvent.Add("appointment_number", "001");
AppsFlyer.sendEvent ("confirmed_appointment", ConfirmedAppointmentEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Rendez-vous annulé (canceled_appointment)">

**Objectif**

En enregistrant cet événement, vous pouvez utiliser les données pour recibler les utilisateurs et envoyer des rappels pour reprogrammer les rendez-vous.

**Déclencheur**

Lorsque l'utilisateur annule un rendez-vous

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| doctor\_name | Nom du médecin | Julie Robert |
| appointment\_number | Numéro du rendez-vous | 001 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("doctor_name", "Robert James");
eventValue.put("appointment_number", "001");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "canceled_appointment", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"canceled_appointment" withValues: @{ 
@"doctor_name": @"Robert James", 
@"appointment_number": @"001"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("canceled_appointment", withValues: 
[ "doctor_name": "Robert James",
"appointment_number": "001"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CanceledAppointmentEvent= new Dictionary<string, string>();
CanceledAppointmentEvent.Add("doctor_name", "Robert James");
CanceledAppointmentEvent.Add("appointment_number", "001");
AppsFlyer.sendEvent ("canceled_appointment", CanceledAppointmentEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Première prise de rendez-vous auprès du médecin (doctor_first_booking)">

**Objectif**

En enregistrant cet événement, vous pouvez utiliser les données pour envoyer des promotions et des publicités de retargeting aux utilisateurs.

**Déclencheur**

Lorsque l'utilisateur prend son premier rendez-vous

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| doctor\_name | Nom du médecin | Julie Robert |
| spécialité | Spécialité médicale | neurologie |
| durée | Durée de la consultation | Chat de 30 minutes |
| prix | Tarif de la consultation | 50 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("doctor_name", "Robert James");
eventValue.put("specialty", "neurology");
eventValue.put("duration", "30 min chat");
eventValue.put("price", "135790");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "doctor_first_booking", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"doctor_first_booking" withValues: @{ 
@"doctor_name": @"Robert James", 
@"specialty": @"neurology", 
@"duration": @"30 min chat", 
@"price": @"50"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("doctor_first_booking", withValues: 
[ "doctor_name": "Robert James",
"specialty": "neurology",
"duration": "30 min chat",
"price": "50"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> DoctorFirstBookingEvent= new Dictionary<string, string>();
DoctorFirstBookingEvent.Add("doctor_name", "Robert James");
DoctorFirstBookingEvent.Add("specialty", "neurology");
DoctorFirstBookingEvent.Add("duration", "30 min chat");
DoctorFirstBookingEvent.Add("price", "50");
AppsFlyer.sendEvent ("doctor_first_booking", DoctorFirstBookingEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Premier rendez-vous au laboratoire (lab_first_appointment)">

**Objectif**

En enregistrant cet événement, vous pouvez utiliser les données pour envoyer des promotions et des publicités de retargeting aux utilisateurs.

**Déclencheur**

Lorsque l'utilisateur prend son premier rendez-vous

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| lab\_selection | Nom de l'examen en laboratoire | check-up général |
| quantité | Montant commandé | 2 |
| prix | Tarif du laboratoire | 500 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("lab_selection", "full body checkup");
eventValue.put("quantity", "30 min chat");
eventValue.put("price", "135790");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "lab_first_appointment", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"lab_first_appointment" withValues: @{ 
@"lab_selection": @"full body checkup", 
@"quantity": @"2", 
@"price": @"500"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("lab_first_appointment", withValues: 
[ "lab_selection": "full body checkup",
"quantity": "2",
"price": "500"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LabFirstAppointmentEvent= new Dictionary<string, string>();
LabFirstAppointmentEvent.Add("lab_selection", "full body checkup");
LabFirstAppointmentEvent.Add("quantity", "2");
LabFirstAppointmentEvent.Add("price", "500");
AppsFlyer.sendEvent ("lab_first_appointment", LabFirstAppointmentEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Premier achat en pharmacie (pharmacy_first_purchase)">

**Objectif**

En enregistrant cet événement, vous pouvez utiliser les données pour envoyer des promotions et des publicités de retargeting aux utilisateurs.

**Déclencheur**

Lorsque l'utilisateur effectue son premier achat

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| medicine\_name | Nom du médicament | rhinos |
| quantité | Montant commandé | 1 |
| prix | Prix du médicament | 10 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("medicine_name", "rhinos");
eventValue.put("quantity", "1");
eventValue.put("price", "10");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "pharmacy_first_purchase", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"pharmacy_first_purchase" withValues: @{ 
@"medicine_name": @"rhinos", 
@"quantity": @"1", 
@"price": @"10"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("pharmacy_first_purchase", withValues: 
[ "medicine_name": "rhinos",
"quantity": "1",
"price": "10"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> PharmacyFirstPurchaseEvent= new Dictionary<string, string>();
PharmacyFirstPurchaseEvent.Add("medicine_name", "rhinos");
PharmacyFirstPurchaseEvent.Add("quantity", "1");
PharmacyFirstPurchaseEvent.Add("price", "10");
AppsFlyer.sendEvent ("pharmacy_first_purchase", PharmacyFirstPurchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Réservation de médecin (doctor_booking)">

**Objectif**

Obtenir des informations supplémentaires sur les besoins et les intérêts de vos utilisateurs.

**Déclencheur**

Lorsque l'utilisateur prend un rendez-vous en personne

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| doctor\_name | Nom du médecin | Julie Robert |
| spécialité | Spécialité médicale | neurologie |
| durée | Durée de la consultation | Chat de 30 minutes |
| prix | Tarif de la consultation | 50 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("doctor_name", "Robert James");
eventValue.put("specialty", "neurology");
eventValue.put("duration", "30 min chat");
eventValue.put("price", "135790");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "doctor_booking", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"doctor_booking" withValues: @{ 
@"doctor_name": @"Robert James", 
@"specialty": @"neurology", 
@"duration": @"30 min chat", 
@"price": @"50"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("doctor_booking", withValues: 
[ "doctor_name": "Robert James",
"specialty": "neurology",
"duration": "30 min chat",
"price": "50"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> DoctorBookingEvent= new Dictionary<string, string>();
DoctorBookingEvent.Add("doctor_name", "Robert James");
DoctorBookingEvent.Add("specialty", "neurology");
DoctorBookingEvent.Add("duration", "30 min chat");
DoctorBookingEvent.Add("price", "50");
AppsFlyer.sendEvent ("doctor_booking", DoctorBookingEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Chat avec le médecin (chat_doctor)">

**Objectif**

Obtenir des informations supplémentaires sur les besoins et les intérêts de vos utilisateurs.

**Déclencheur**

Lorsque l'utilisateur effectue une réservation

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| doctor\_name | Nom du médecin | Julie Robert |
| spécialité | Spécialité médicale | neurologie |
| durée | Durée de la consultation | Chat de 30 minutes |
| prix | Tarif de la consultation | 50 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("doctor_name", "Robert James");
eventValue.put("specialty", "neurology");
eventValue.put("duration", "30 min chat");
eventValue.put("price", "135790");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "chat_doctor", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"chat_doctor" withValues: @{ 
@"doctor_name": @"Robert James", 
@"specialty": @"neurology", 
@"duration": @"30 min chat", 
@"price": @"50"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("chat_doctor", withValues: 
[ "doctor_name": "Robert James",
"specialty": "neurology",
"duration": "30 min chat",
"price": "50"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ChatDoctorEvent= new Dictionary<string, string>();
ChatDoctorEvent.Add("doctor_name", "Robert James");
ChatDoctorEvent.Add("specialty", "neurology");
ChatDoctorEvent.Add("duration", "30 min chat");
ChatDoctorEvent.Add("price", "50");
AppsFlyer.sendEvent ("chat_doctor", ChatDoctorEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Rendez-vous au laboratoire (lab_appointment)">

**Objectif**

En enregistrant cet événement, vous pouvez utiliser les données pour envoyer des promotions et des publicités de retargeting aux utilisateurs.

**Déclencheur**

Lorsque l'utilisateur prend un rendez-vous au laboratoire

Paramètres d'événement

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| lab\_selection | Nom du type de laboratoire | check-up général |
| quantité | Montant commandé | 2 |
| prix | Tarif du laboratoire | 500 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("lab selection", "full body checkup");
eventValue.put("quantity", "2");
eventValue.put("price", "500");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "lab_appointment", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"lab_appointment" withValues: @{ 
@"lab_selection": @"full body checkup", 
@"quantity": @"2", 
@"price": @"500"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("lab_appointment", withValues: 
[ "lab selection": "full body checkup",
"quantity": "2",
"price": "500"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LabAppointmentEvent= new Dictionary<string, string>();
LabAppointmentEvent.Add("lab selection", "full body checkup");
LabAppointmentEvent.Add("quantity", "2");
LabAppointmentEvent.Add("price", "500");
AppsFlyer.sendEvent ("lab_appointment", LabAppointmentEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Achat en pharmacie (pharmacy_purchase)">

**Objectif**

En enregistrant cet événement, vous pouvez utiliser les données pour envoyer des promotions et des publicités de retargeting aux utilisateurs.

**Déclencheur**

Lorsque l'utilisateur effectue un achat pharmaceutique

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| medicine\_name | Nom du médicament | rhinos |
| quantité | Montant commandé | 1 |
| prix | Prix du médicament | 10 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("medicine_name", "rhinos");
eventValue.put("quantity", "1");
eventValue.put("price", "10");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "pharmacy_purchase", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"pharmacy_purchase" withValues: @{ 
@"medicine_name": @"rhinos", 
@"quantity": @"1", 
@"price": @"10"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("pharmacy_purchase", withValues: 
[ "medicine_name": "rhinos",
"quantity": "1",
"price": "10"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> PharmacyPurchaseEvent= new Dictionary<string, string>();
PharmacyPurchaseEvent.Add("medicine_name", "rhinos");
PharmacyPurchaseEvent.Add("quantity", "1");
PharmacyPurchaseEvent.Add("price", "10");
AppsFlyer.sendEvent ("pharmacy_purchase", PharmacyPurchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Inscription mutuelle (insurance_membership)">

**Objectif**

En savoir plus sur vos utilisateurs, puis les recibler en conséquence.

**Déclencheur**

Lorsque l'utilisateur adhère à une mutuelle

Paramètres d'événement

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| insurance\_name | Nom de la compagnie d'assurance | Mutuelle4000 |
| insurance\_type | Type de régime d'assurance | premium |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("insurance_name", "DavidShield");
eventValue.put("insurance_type", "premium");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "insurance_membership", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"insurance_membership" withValues: @{ 
@"insurance_name": @"DavidShield", 
@"insurance_type": @"premium"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("insurance_membership", withValues: 
[ "insurance_name": "DavidShield",
"insurance_type": "premium"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> InsuranceMembershipEvent= new Dictionary<string, string>();
InsuranceMembershipEvent.Add("insurance_name", "DavidShield");
InsuranceMembershipEvent.Add("insurance_type", "premium");
AppsFlyer.sendEvent ("insurance_membership", InsuranceMembershipEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Émission du reçu (receipt_issuance)">

**Objectif**

Les utilisateurs disposant d'un reçu peuvent potentiellement réclamer le remboursement de la consultation chez le médecin, du rendez-vous au laboratoire ou des médicaments à leur assureur. En enregistrant cet événement, vous pouvez utiliser les données pour des campagnes de retargeting sur l'assurance personnelle.

**Déclencheur**

Lorsque l'utilisateur reçoit un reçu

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| app\_name | Nom de votre app | App de soins médicaux |
| doctor\_name | Nom du médecin | Julie Robert |
| consultation\_description | Description du problème de santé | fièvre |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("app_name", "Healthcare App");
eventValue.put("doctor_name", "Robert James");
eventValue.put("consultation_description", "fever");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "receipt_issuance", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"receipt_issuance" withValues: @{ 
@"app_name": @"Healthcare App", 
@"doctor_name": @"Robert James", 
@"consultation_description": @"fever"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("receipt_issuance", withValues: 
[ "app_name": "Healthcare App",
"doctor_name": "Robert James",
"consultation_description": "fever"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ReceiptIssuanceEvent= new Dictionary<string, string>();
ReceiptIssuanceEvent.Add("app_name", "Healthcare App");
ReceiptIssuanceEvent.Add("doctor_name", "Robert James");
ReceiptIssuanceEvent.Add("consultation_description", "fever");
AppsFlyer.sendEvent ("receipt_issuance", ReceiptIssuanceEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Recharge réussie (top_up_success)">

**Objectif**

Les fonds complémentaires peuvent être utilisés pour acheter n'importe quel forfait ou service proposé dans l'app. Vous pouvez enregistrer cet évènement et le comparer avec d'autres données pour en savoir plus sur vos utilisateurs. Par exemple, vous pouvez savoir quel montant les gens sont prêts à déposer sur leurs comptes et utiliser les montant des recharge pour cibler les utilisateurs avec des campagnes personnalisées selon leur budget de rechargement.

**Déclencheur**

Lorsque l'utilisateur termine l'ajout d'une recharge

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Montant de la recharge | 2000.55 |
| top\_up\_id | L'ID de la recharge | 397 |
| payment\_method\_type | Mode de paiement utilisé | carte de crédit, paiement local |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();  
eventValue.put(AFInAppEventParameterName.REVENUE, 2000.55);
eventValue.put("top_up_id", "397");
eventValue.put("payment_method_type", "creditcard");  
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "top_up_success", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"top_up_success"
withValues: @{
  AFEventParamRevenue: @2000.55,   
   @"top_up_id": @"397",
   @"payment_method_type": @"credit card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("top_up_success", 
withValues: [
   AFEventParamRevenue: 2000.55,   
   "top_up_id": "397",
   "payment_method_type": "credit card",
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> TopUpSuccessEvent = new Dictionary<string, string>();
TopUpSuccessEvent.Add("af_revenue", "2000.55");
TopUpSuccessEvent.Add("top_up_id", "397");
TopUpSuccessEvent.Add("payment_method_type", "credit card");
AppsFlyer.sendEvent("top_up_success", TopUpSuccessEvent);
```

</Tab>
</Tabs>

</Accordion>
