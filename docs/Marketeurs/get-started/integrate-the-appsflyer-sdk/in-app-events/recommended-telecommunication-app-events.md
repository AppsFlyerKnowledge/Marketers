---
title: Événements recommandés pour les apps de télécommunication
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
  created_at: '2021-05-02T11:59:16Z'
  edited_at: '2022-01-25T17:23:33Z'
  id: 360019896558
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/360019896558
---
> **En bref :** mesurez la qualité de vos utilisateurs tout au long de leur parcours en enregistrant ces événements in-app suggérés pour votre app de télécommunication.

<div id="-telecommunication" />

## <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="100px" /> Télécommunication

Les applications de télécommunications permettent aux utilisateurs d'acheter et de gérer des plans de téléphonie cellulaire, des plans de données, etc. Les principaux événements que nous suggérons d'enregistrer incluent les achats, les recharges et les abonnements.

L'enregistrement de ces événements peut vous aider à déterminer :

* Quels forfaits d'opérateur sont les plus populaires
* Quels produits ou forfaits les utilisateurs peuvent se permettre d'acheter
* Quels forfaits sont susceptibles de générer le plus d'engagement à long terme chez les clients

<div id="important" />

> 🚧 **Important !**
>
> * Veillez à lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#introduction-setting-up-inapp-events">instructions</Anchor> à l'attention des marketeurs pour implémenter les événements in-app.
> * Pour simplifier l'implémentation, [téléchargez un fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSJsgqgzIInw8NAzY8ILsk2H4Vjp-7dRIc1Ed6vNb34mOayiTjutUs-cOnd4H5u18EvgpspKe7Dx2xb/pub?gid=211685733&single=true&output=csv) contenant tous les événements in-app de base décrits dans cet article, puis modifiez les événements en fonction des besoins de votre entreprise. Une fois terminé, partagez le fichier avec votre développeur.
> * Pour chaque événement recommandé que contient cet article, vous trouverez des extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour plus d'informations sur l'enregistrement des événements in-app, consultez le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">guide des événements in-app riches</Anchor>.

[![Flowchart_for_recommended_events_telecommunication_app_user_journey](https://files.readme.io/ae4c696208b49aa546ffc0a15f76b148b35af43984a76e699d1df7c54507352c-4404604045457.png)](https://files.readme.io/ae4c696208b49aa546ffc0a15f76b148b35af43984a76e699d1df7c54507352c-4404604045457.png)

<div id="recommended-structures-for-predefined-events" />

## Structures recommandées pour les événements prédéfinis

La section suivante fournit une liste des structures d'événements typiques du secteur des télécommunications. Chaque structure donne un nom d'événement prédéfini, ainsi que des suggestions de paramètres d'événement à appliquer. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins

<div id="login-af_login" />

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

<div id="complete-registration-af_complete_registration" />

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

<div id="content-view-af_content_view" />

<Accordion title="Affichage du contenu (af_content_view)">

**Objectif**

Déterminer le taux d'affichage de certains produits et :

* Mettre en corrélation les vues du produit avec les ventes du produit.
* Comprendre quelles catégories sont les plus populaires selon les vues du produit.
* Voir la corrélation entre la devise des acheteurs et les produits qu'ils consultent

**Déclencheur**

Lorsque l'utilisateur consulte la page d'informations d'un certain produit

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Prix du produit | 200 |
| af\_content\_id | ID du produit | 102 |
| af\_content\_type | Catégorie du produit | Forfaits internet |
| af\_currency | La devise sur la page d'informations du produit | THB, USD |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 200);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "102";
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "Internet packages");
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.CONTENT_VIEW, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventContentView
withValues: @{
  AFEventParamPrice: @200,
  AFEventParamContentId: @"102",
  AFEventParamContentType: @"Internet packages",
  AFEventParamCurrency: @"USD"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventContentView,
withValues: [
 AFEventParamPrice: 200,
 AFEventParamContentId: "102",
 AFEventParamContentType: "Internet packages",
 AFEventParamCurrency: "USD"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ContentViewEvent = new Dictionary<string, string>();
ContentViewEvent.Add("af_price", "200");
ContentViewEvent.Add("af_content_type", "Internet packages");
ContentViewEvent.Add("af_currency", "USD");
AppsFlyer.sendEvent("af_content_view", ContentViewEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Affichage de la liste (af_list_view)">

**Objectif**

Enregistrer les listes que les acheteurs consultent le plus (ex : derniers produits ajoutés, produits connexes ou produits recommandés).

**Déclencheur**

Lorsque l'utilisateur consulte une liste spécifique

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_content\_type | Type de liste | connexe, recommandé, nouveautés |
| af\_content\_list | Liste des ID contenu de la catégorie | 001, 092 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "related products");
eventValue.put(AFInAppEventParameterName.CONTENT_LIST, new String[] {"001", "092"});
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "af_list_view", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventListView
withValues: @{
  AFEventParamContentType: @"related products",
  AFEventParamContentList: @[@"001", @"092"]
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventListView,
>withValues: [
  AFEventParamContentType: "related products",
  AFEventParamContentList: ["001", "092"]
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ListViewEvent = new Dictionary<string, string>();
ListViewEvent.Add("af_content_type", "related products");
ListViewEvent.Add("af_content_list", "['001', '092']");
AppsFlyer.sendEvent("af_list_view", ListViewEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Achat (af_purchase)">

**Objectif**

De nombreuses apps de télécommunications permettent aux utilisateurs d'acheter des articles, comme des données supplémentaires. L'enregistrement de cet évènement peut vous aider à :

* Déterminer la LTV de vos utilisateurs et le ROI de vos campagnes sur les réseaux publicitaires et les agences de publicité
* Déterminer quelles offres sont les plus populaires auprès de vos utilisateurs
* Réaliser une référence croisée de campagne avec les articles qui ont été achetés afin d'optimiser le ciblage de vos campagnes

**Déclencheur**

Lorsque l'utilisateur atterrit sur la page de remerciement une fois l'achat terminé

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Le revenu estimé provenant de l'achat | 2050.50 |
| af\_currency | Code de devise | THB |
| af\_content\_type | Nom du forfait acheté | 5G |
| af\_order\_id | ID de la commande | 9277 |
| payment\_method\_type | Le type de méthode de paiement | carte de crédit, paiement local |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put(AFInAppEventParameterName.REVENUE, 2050.50);
eventValue.put(AFInAppEventParameterName.CURRENCY, "THB");
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "5G");
eventValue.put("AFInAppEventParameterName.ORDER_ID", "9277");
eventValue.put("payment_method_type", "credit_card");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),AFInAppEventType.PURCHASE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventPurchase
withValues: @{
   AFEventParamRevenue: @2050.50,
   AFEventParamCurrency: @"THB",
   AFEventParamContentType: @"5G",
   AFEventParamContentTypeOrderId: @"9277",
   @"payment_method_type": @"credit_card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventPurchase, 
withValues: [
   AFEventParamRevenue: 2050.50,
   AFEventParamCurrency: "THB",
   AFEventParamContentType: "5G",
   AFEventParamContentTypeOrderId: "9277",
   "payment_method_type": "credit_card",
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> purchaseEvent = new Dictionary<string, string>();
purchaseEvent.Add("af_revenue", "2050.50");
purchaseEvent.Add("af_currency", "THB");
purchaseEvent.Add("af_content_type", "5G");
purchaseEvent.Add("af_order_id", "9277");
purchaseEvent.Add("payment_method_type", "credit_card");
AppsFlyer.sendEvent ("af_purchase", purchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Structures recommandées pour les événements personnalisés

La section suivante fournit une structure d'événement qui comprend un nom d'événement personnalisé et les suggestions de paramètres d'événement à utiliser. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<div id="select-package-select_package" />

<Accordion title="Sélection du forfait (select_package)">

**Objectif**

Enregistrez lorsqu'un utilisateur décide d'acheter un forfait, et avant que le paiement a été effectué. Vous pouvez par exemple utiliser ces données pour recibler les utilisateurs et leur envoyer des offres en lien avec d'autres services.

**Déclencheur**

Lorsque l'utilisateur sélectionne un forfait mais ne finalise pas le paiement

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| price | Prix de l'abonnement | 50000 |
| af\_content\_type | Type de contenu sélectionné par l'utilisateur | 5 Go de données |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("price", "50000");
eventValue.put("af_content_type ", "Data 5 GB ");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "select_package", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"select_package" withValues: @{ 
@"price": @"50000", 
@"af_content_type ": @"Data 5 GB "}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("select_package", withValues: 
[ "price": "50000",
"af_content_type ": "Data 5 GB "])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SelectPackageEvent= new Dictionary<string, string>();
SelectPackageEvent.Add("price", "50000");  
SelectPackageEvent.Add("af_content_type ", "Data 5 GB ");
AppsFlyer.sendEvent ("select_package", SelectPackageEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="topup-success-top_up_success" />

<Accordion title="Recharge réussie (top_up_success)">

**Objectif**

Les fonds de recharge peuvent être utilisés pour acheter n'importe quel forfait ou tout autre service offert dans l'app. Enregistrer cet évènement et le comparer avec d'autres données pour en savoir plus sur vos utilisateurs. Par exemple, vous pouvez apprendre quels montants les utilisateurs sont prêts à déposer sur leurs comptes, puis utiliser les montants de recharge pour les cibler avec des campagnes personnalisées en accord avec leur budget.

**Déclencheur**

Lorsque l'utilisateur finalise l'ajout d'une recharge

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Montant de la recharge | 2050.50 |
| top\_up\_id | L'ID de la recharge | 397 |
| payment\_method\_type | Le type de méthode de paiement | carte de crédit, paiement local |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();  
eventValue.put(AFInAppEventParameterName.REVENUE, 2050.50);
eventValue.put("top_up_id", "397");
eventValue.put("payment_method_type", "credit_card");  
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "top_up_success", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent :"top_up_success"
 withValues : @{
  AFEventParamRevenue: @2050.50,   
   @"top_up_id": @"397",
   @"payment_method_type": @"credit_card"
}] ;
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("top_up_success", 
withValues: [
   AFEventParamRevenue: 2050.50,   
   "top_up_id": "397",
   "payment_method_type": "credit_card",
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> TopUpSuccessEvent = new Dictionary<string, string>();
TopUpSuccessEvent.Add("af_revenue", "2050.50");
TopUpSuccessEvent.Add("top_up_id", "397");
TopUpSuccessEvent.Add("payment_method_type", "credit_card");
AppsFlyer.sendEvent ("top_up_success", TopUpSuccessEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="topup-unsuccessful-top_up_unsuccessful" />

<Accordion title="Échec de la recharge (top_up_unsuccessful)">

**Objectif**

Enregistrer cet évènement et le comparer avec d'autres données pour en savoir plus sur vos utilisateurs. Par exemple, vous pouvez savoir combien d'utilisateurs essaient de recharger mais n'y parviennent pas.

**Déclencheur**

Lorsque l'utilisateur essaie de recharger mais que l'action échoue

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| error\_reason | Motif de l'échec de la recharge | exceeded\_daily\_limit |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
              eventValue.put("error_reason", "exceeded_daily_limit");
              AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "top_up_unsuccessful", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"top_up_unsuccessful" withValues: @{ 
              @"error_reason": @"exceeded_daily_limit"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("top_up_unsuccessful",withValues:
              ["error_reason": "exceeded_daily_limit" ])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> TopUpUnsuccessfulEvent = new Dictionary<string, string>() ;
ErrorReasonEvent.Add("error_reason", "exceeded_daily_limit") ;  
AppsFlyer.sendEvent (" top_up_unsuccessful" , TopUpUnsuccessfulEvent) ;
```

</Tab>
</Tabs>

</Accordion>

<div id="subscription-complete-subscription_complete" />

<Accordion title="Abonnement terminé (subscription_complete)">

**Objectif**

L'enregistrement de cet évènement peut vous aider à :

* Voir quelles campagnes produisent des utilisateurs qui s'inscrivent
* Comparer le nombre d'utilisateurs inscrits avec le nombre d'utilisateurs non inscrits
* Enregistrer les revenus générés par les abonnements et les attribuer aux campagnes et aux sources média

**Déclencheur**

* Lorsque l'utilisateur s'inscrit avec succès
* Lorsqu'un abonnement est renouvelé

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| subscription\_type | Type d'abonnement | 30 Go par mois |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Montant de l'abonnement | 555.50 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("subscription_type", "Monthly 30 GB"); 
eventValue.put(AFInAppEventParameterName.REVENUE, "555.50"); 
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "subscription_complete", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[AppsFlyerLib shared] logEvent:@"subscription_complete" withValues:@{
              @"subscription_type": @"Monthly 30 GB", 
              AFEventParamRevenue: @"555.50"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
ApAppsFlyerLib.shared().logEvent(" subscription_complete" ,  
 withValues: 
[ "subscription_type": "Monthly 30 GB",  
 "af_revenue": "555.50"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubscriptionCompleteEvent = new Dictionary<string, string>();
SubscriptionCompleteEvent.Add("subscription_type", "Monthly 30 GB");  
SubscriptionCompleteEvent.Add("af_revenue", "555.50");   
AppsFlyer.sendEvent("subscription_complete", SubscriptionCompleteEvent);
```

</Tab>
</Tabs>

</Accordion>
