---
title: ' Événements recommandés pour les apps de eCommerce'
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
  created_at: '2021-04-19T06:32:18Z'
  edited_at: '2022-01-25T17:21:44Z'
  id: 360019347957
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/360019347957
---
> **En bref :** mesurez la qualité de vos utilisateurs tout au long de leur parcours en enregistrant ces événements in-app suggérés pour votre app de eCommerce .

<div id="-ecommerce" />

## <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="67px" />e-commerce

Les apps d'e-commerce permettent aux acheteurs de rechercher et d'acheter facilement des produits en ligne. Nous vous recommandons d'enregistrer les évènements typiques de recherche, d'achat, d'ajout au panier et d'ajout à la liste d'envies.

L'enregistrement de ces évènements peut vous aider à déterminer :

* Les catégories les plus populaires
* Ce que les acheteurs recherchent
* Combien d'acheteurs ont effectué un paiement
* Combien d'acheteurs sont des acheteurs récurrents et combien sont des acheteurs uniques

<div id="important" />

> 🚧 **Important !**
>
> * Veillez à lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#introduction-setting-up-inapp-events">instructions</Anchor> à l'attention des marketeurs pour implémenter les événements in-app.
> * Pour simplifier l'implémentation, [téléchargez un fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSJsgqgzIInw8NAzY8ILsk2H4Vjp-7dRIc1Ed6vNb34mOayiTjutUs-cOnd4H5u18EvgpspKe7Dx2xb/pub?gid=182631520&single=true&output=csv) contenant tous les événements in-app de base décrits dans cet article, puis modifiez les événements en fonction des besoins de votre entreprise. Une fois terminé, partagez le fichier avec votre développeur.
> * Pour chaque événement recommandé que contient cet article, vous trouverez des extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour plus d'informations sur l'enregistrement des événements in-app, consultez le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">guide des événements in-app riches</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events e-Commerce_app_user_journey" src="https://files.readme.io/81af149c4fbe9185af3dad4057147dbf9882eb30d30b0724f2ffad2714517084-360020063077.png" />

<div id="recommended-structures-for-predefined-events" />

## Structures recommandées pour les événements prédéfinis

La section suivante fournit une liste des structures d'événements typiques du secteur du eCommerce. Chaque structure donne un nom d'événement prédéfini, ainsi que des suggestions de paramètres d'événement à appliquer. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

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
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REGSITRATION_METHOD,"Facebook");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),AFInAppEventType.COMPLETE_REGISTRATION, eventValue);
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

<div id="search-af_search" />

<Accordion title="Recherche (af_search)">

**Objectif**

Découvrir ce que les utilisateurs recherchent, et quels résultats de recherche sont les plus pertinents et mènent à un achat.

**Déclencheur**

L'une des opérations suivantes :

* Lorsque l'utilisateur clique sur le bouton de recherche
* Lorsque l'utilisateur atterrit sur la page des résultats de la recherche

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_search\_string | Terme de recherche | Robe rouge, chaussures de course |
| af\_content\_list | Liste des ID de contenu | 001, 092 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.SEARCH_STRING, "red shoes");
eventValue.put(AFInAppEventParameterName.CONTENT_LIST, new String[] {"001", "092"});
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.SEARCH, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventSearch
withValues: @{
  AFEventParamSearchString: @"red shoes",
  AFEventParamContentList: @[@"001", @"092"]
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventSearch, withValues: [
  AFEventParamSearchString: "red shoes",
  AFEventParamContentList: ["001", "092"]
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SearchEvent = new Dictionary<string, string>();
SearchEvent.Add("af_search_string", "red shoes");
SearchEvent.Add("af_content_list", "['001', '092']");
AppsFlyer.sendEvent("af_search", SearchEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Affichage du contenu (af_content_view)">

**Objectif**

Déterminer le taux d'affichage de produits spécifiques. Cet évènement peut vous aider à :

* Mettre en corrélation les vues du produit avec les ventes du produit.
* Comprendre quelles catégories sont les plus populaires selon les vues du produit.
* Voir la corrélation entre la devise des acheteurs et les produits qu'ils consultent

**Déclencheur**

Lorsque l'utilisateur consulte la page d'informations d'un certain produit

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Prix du produit | 2000 |
| af\_content | Numéro international d'article (EAN) si disponible, ou autre identifiant de produit ou de contenu.<br /><br />**Paramètre obligatoire pour les publicités dynamiques Facebook** | ABC123 |
| af\_content\_id | ID du produit<br /><br />**Paramètre obligatoire pour les publicités dynamiques Facebook** | 102 |
| af\_content\_type | Catégorie du produit<br /><br />**Paramètre obligatoire pour les publicités dynamiques Facebook** | Chaussures |
| af\_currency | La devise sur la page d'informations du produit | THB, USD |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, "2000");
eventValue.put(AFInAppEventParameterName.CONTENT, "ABC123";
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "102";
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "shoes");
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.CONTENT_VIEW, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventContentView
withValues: @{
  AFEventParamPrice: @"2000",
  AFEventParamContent: @"ABC123",
  AFEventParamContentId: @"102",
  AFEventParamContentType: @"shoes",
  AFEventParamCurrency: @"USD"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventContentView,
withValues: [ AFEventParamPrice: "2000", AFEventParamContent: "ABC123", AFEventParamContentId: "102", AFEventParamContentType: "shoes", AFEventParamCurrency: "USD"]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ContentViewEvent = new Dictionary<string, string>();
ContentViewEvent.Add("af_price", "2000");
ContentViewEvent.Add("af_content", "ABC123");
ContentViewEvent.Add("af_content_id", "102");
ContentViewEvent.Add("af_content_type", "shoes");
ContentViewEvent.Add("af_currency", "USD");
AppsFlyer.sendEvent("af_content_view", ContentViewEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Affichage de la liste (af_list_view)">

**Objectif**

Enregistrez les listes (par exemple, les nouveaux produits, les produits connexes ou les produits recommandés) que les acheteurs consultent le plus.

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

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Ajouter à la liste de souhaits (af_add_to_wishlist)">

**Objectif**

Enregistrer les produits et les catégories que les acheteurs ajoutent à leur liste d'envie. Une fois que vous savez quels produits sont souvent ajoutés aux listes de vœux, vous pouvez offrir des remises sur ces produits afin d'inciter les acheteurs à les acheter. Vous pouvez également recibler ces utilisateurs selon les produits qu'ils ont ajouté à leur liste d'envies.

**Déclencheur**

Lorsque l'utilisateur ajoute des articles à sa liste d'envies

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Prix du produit | 600 |
| af\_content\_id | ID du produit | 300 |
| af\_content\_type | Catégorie du produit | Chaussures, électronique |
| af\_currency | Devise affichée sur la page d'informations du produit | GBP |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 600);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "300");
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "electronics");
eventValue.put(AFInAppEventParameterName.CURRENCY, "GBP");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.ADD_TO_WISH_LIST, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventAddToWishlist
withValues: @{
  AFEventParamPrice: @600,
  AFEventParamContentId: @"300",
  AFEventParamContentType: @"electronics",
  AFEventParamCurrency: @"GBP"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventAddToWishlist, 
withValues: [
  AFEventParamPrice: 600,
  AFEventParamContentId: "300",
  AFEventParamContentType: "electronics",
  AFEventParamCurrency: "GBP"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> AddToWishListEvent =
new Dictionary<string, string>();
AddToWishListEvent.Add("af_price", "600");
AddToWishListEvent.Add("af_content_id", "300");
AddToWishListEvent.Add("af_content_type", "electronics");
AddToWishListEvent.Add("af_currency", "GBP");
AppsFlyer.sendEvent("af_add_to_wishlist", AddToWishListEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Ajouter au panier (af_add_to_cart)">

**Objectif**

Enregistrer l'ajout de produits au panier. Cet événement peut vous aider à déterminer :

* Le nombre de produits que les acheteurs ajoutent en moyenne lors d'un achat
* Le temps qui s'écoule entre l'ajout de deux produits différents
* le nombre d'acheteurs qui abandonnent leur panier

**Déclencheur**

Lorsque l'utilisateur ajoute un produit au panier

**Paramètres d'événement**

| Nom du champ | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Prix du produit | 350, 1000 |
| af\_content | Numéro international d'article (EAN) si disponible, ou autre identifiant de produit ou de contenu.<br /><br />**Paramètre obligatoire pour les publicités dynamiques Facebook** | ABC123 |
| af\_content\_id | ID du produit<br /><br />**Paramètre requis pour les publicités dynamiques Facebook** | 001, 092 |
| af\_content\_type | Type de produit<br /><br />**Paramètre obligatoire pour les publicités dynamiques Facebook** | Chemise, chaussures |
| af\_currency | Devise du produit | THB, USD |
| af\_quantity | Combien d'articles du même produit ont été ajoutés au panier | 2, 5 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, "350");
eventValue.put(AFInAppEventParameterName.CONTENT, "ABC123");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "001");
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "shirt");
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
eventValue.put(AFInAppEventParameterName.QUANTITY, "2");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.ADD_TO_CART, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventAddToCart
withValues: @{
 AFEventParamPrice: @"350",
 AFEventParamContent: @"ABC123",
 AFEventParamContentId: @"001",
 AFEventParamContentType: @"shirt",
 AFEventParamCurrency: @"USD",
 AFEventParamQuantity: @"2"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventAddToCart, withValues: [ AFEventParamPrice: "350", AFEventParamContent: "ABC123", AFEventParamContentId: "001", AFEventParamContentType: "shirt", AFEventParamCurrency: "USD", AFEventParamQuantity: "2"]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> AddToCartEvent = new Dictionary<string, string>();
AddToCartEvent.Add("af_price", "350");
AddToCartEvent.Add("af_content", "ABC123");
AddToCartEvent.Add("af_content_id", "001");
AddToCartEvent.Add("af_content_type", "shirt");
AddToCartEvent.Add("af_currency", "USD");
AddToCartEvent.Add("af_quantity", "2");
AppsFlyer.sendEvent("af_add_to_cart", AddToCartEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Paiement initié (af_initiated_checkout)">

**Objectif**

Comprendre le comportement des acheteurs lorsqu'ils procèdent au paiement. Cet événement peut vous aider à déterminer :

* Le prix moyen lorsque les acheteurs procèdent au paiement par rapport au prix moyen de l'événement d'achat
* Si les utilisateurs ajoutent ou retirent des produits au moment de passer au paiement

**Déclencheur**

Lorsque l'acheteur initie le paiement mais ne l'a pas encore finalisé

**Paramètres d'événement**

| Nom du champ | Description | Exemple de valeur |
| --- | --- | --- |
| af\_price | Prix total du panier | 4000 |
| af\_content\_id | ID des produits dans le panier | 221, 124 |
| af\_content\_type | Liste des catégories de produits | Chemise, pantalons |
| af\_currency | Devise au moment du paiement | THB |
| af\_quantity | Nombre total d'articles dans le panier | 2, 5 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 350);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "221");
// for multiple product categories, set the param value as: new String {"221", "124"}
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "shirt");
// for multiple product categories,, set the param value as: new String {"shirt", "pants"}
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
eventValue.put(AFInAppEventParameterName.QUANTITY, 2);
// for multiple product categories,, set the param value as: new int {2, 5}
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.INITIATED_CHECKOUT, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventInitiatedCheckout
withValues: @{
  AFEventParamPrice: @350,
  AFEventParamContentId: @"221",
  // for multiple product categories, set the param value as: @[@"221", @"124"]
  AFEventParamContentType: @"shirt",
  // for multiple product categories, set the param value as: @[@"shirt", @"pants"]
  AFEventParamCurrency: @"USD",
  AFEventParamQuantity: @2
  // for multiple product categories, set the param value as: @[@2, @5]
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventInitiatedCheckout,
withValues: [AFEventParamPrice: 350, 
 AFEventParamContentId: "221",
 // for multiple product categories, set the param value as: ["221", "124"]*/
 AFEventParamContentType: "shirt", 
 // for multiple product categories, set the param value as: ["shirt", "pants"] AFEventParamCurrency: "USD",
 AFEventParamQuantity: 2 
 //for multiple product categories, set the param value as: [2, 5] 
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> InitiatedCheckoutEvent = new Dictionary<string, string>();
InitiatedCheckoutEvent.Add("af_price", "350");
InitiatedCheckoutEvent.Add("af_content_id", "001");
InitiatedCheckoutEvent.Add("af_content_type", "shirt");
InitiatedCheckoutEvent.Add("af_currency", "USD");
InitiatedCheckoutEvent.Add("af_quantity", "2");
AppsFlyer.sendEvent ("af_initiated_checkout", InitiatedCheckoutEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Achat (af_purchase)">

**Objectif**

Découvrir les tendances d'achat dans votre app. Cet évènement peut vous aider à :

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
| af\_content | Numéro international d'article (EAN) si disponible, ou autre identifiant de produit ou de contenu.<br /><br />**Paramètre requis pour les publicités dynamiques** **Facebook** | ABC123 |
| af\_content\_id | ID de l'article<br /><br />**Paramètre obligatoire pour les publicités dynamiques Facebook** | 121, 262 |
| af\_content\_type | Catégorie de l'article<br /><br />**Paramètre obligatoire pour les publicités dynamiques Facebook** | Chaussures, pantalons |
| af\_currency | Code de devise | AUD |
| af\_quantity | Nombre d'articles dans le panier | 2, 5 |
| af\_order\_id | ID de la commande générée après l'achat. | X123ABC |
| af\_receipt\_id | ID de la commande<br /><br />**Paramètre requis pour l'intégration de retargeting CRITEO et Google Ad Words** | X123ABC |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 350);
eventValue.put(AFInAppEventParameterName.CONTENT, "ABC123");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "221");
// for multiple product categories, set the param value as: // new String {"221", "124"}
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "shirt");
// for multiple product categories,, set the param value as: new String {"shoes", "pants"}
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
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
  AFEventParamContent: @"ABC123",
  AFEventParamContentId: @"221",
  // for multiple product categories, set the param value as:   
  // @[@"221", @"124"]
  AFEventParamContentType: @"shirt",
  // for multiple product categories, set the param value as:   
  // @[@"shoes", @"pants"]
  AFEventParamCurrency: @"USD",
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
AppsFlyerLib.shared().logEvent(AFEventPurchase,  withValues: [
  AFEventParamRevenue: 1205.99,
  AFEventParamPrice : 4000,  AFEventParamContent : "ABC123",  AFEventParamContentId : "221",  // pour différentes catégories de produits, définissez la valeur du paramètre sur : ["221", "124"],  AFEventParamContentType : "shirt",  // pour différentes catégories de produits, définissez la valeur du paramètre sur : ["shoes", "pants"]  AFEventParamCurrency : "USD",  AFEventParamQuantity : 2,  // pour différentes catégories de produits, définissez la valeur du paramètre sur : [2, 5]  AFEventParamOrderId : "X123ABC",   AFEventParamReceiptId : "X123ABC"]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> PurchaseEvent = new Dictionary<string, string>();PurchaseEvent.Add("af_revenue", "1205.99");PurchaseEvent.Add("af_price", "4000"); 
 PurchaseEvent.Add("af_content", "ABC123"); 
 PurchaseEvent.Add("af_content_id", "121"); 
 // pour différentes catégories de produits, définissez la valeur du paramètre comme suit : ["221", "124"] 
 PurchaseEvent.Add("af_content_type", "shoes"); 
 // pour différentes catégories de produits, définissez la valeur du paramètre comme suit : ["shirt", "pants"] 
 PurchaseEvent.Add("af_currency", "USD"); 
 PurchaseEvent.Add("af_quantity", "2"); 
 // pour différentes catégories de produits, définissez la valeur du paramètre comme suit : [2, 5] 
 PurchaseEvent.Add("af_order_id", "X123ABC"); 
 PurchaseEvent.Add("af_receipt_id", "X123ABC"); 
 AppsFlyer.sendEvent ("af_purchase", PurchaseEvent) ;
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

Identique à l'événement [Achat](/docs/recommended-ecommerce-app-events#purchase-af_purchase). Cet événement peut également vous aider à déterminer :

* Combien de temps il faut à un nouvel acheteur pour procéder à l'achat
* Les produits que les nouveaux acheteurs préfèrent acheter
* Le prix moyen et les revenus issus des premiers achats

**Déclencheur**

Lorsque l'utilisateur finalise son premier achat

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Revenu des achats | 1205.99 |
| af\_price | Montant global des achats | 4000 |
| af\_content | Numéro international d'article (EAN) si disponible, ou autre identifiant de produit ou de contenu.<br /><br />**Paramètre obligatoire pour les publicités dynamiques Facebook** | ABC123 |
| af\_content\_id | ID de l'article<br /><br />**Paramètre obligatoire pour les publicités dynamiques Facebook** | 121, 262 |
| af\_content\_type | Catégorie de l'article<br /><br />**Paramètre obligatoire pour les publicités dynamiques Facebook** | Chaussures, pantalons |
| af\_currency | Devise | AUD |
| af\_quantity | Quantité d'articles dans le panier | 2, 5 |
| af\_order\_id | ID de la commande générée après l'achat. | X123ABC |
| af\_receipt\_id | ID de la commande<br /><br />**Paramètre requis pour l'intégration de retargeting CRITEO et Google AdWords** | X123ABC |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, "350");
eventValue.put(AFInAppEventParameterName.CONTENT, "ABC123");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "221");
// for multiple product categories, set the param value as: new String {"221", "124"}
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "shirt");
// for multiple product categories set the param value as: new String {"shoes", "pants"}
eventValue.put(AFInAppEventParameteName.CURRENCY, "USD");
eventValue.put(AFInAppEventParameterName.QUANTITY, "2");
// for multiple product categories, set the param value as: new int {2, 5}
eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "X123ABC");
eventValue.put("af_order_id", "X123ABC");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "first_purchase", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:("first_purchase")
withValues: @{
  AFEventParamRevenue: @1205.99,
  AFEventParamPrice: @4000,
  AFEventParamContent: @"ABC123",
  AFEventParamContentId: @"221",
  // for multiple product categories, set the param value as: @[@"221", @"124"]
  AFEventParamContentType: @"shirt",
  // for multiple product categories, set the param value as: @[@"shoes", @"pants"]
  AFEventParamCurrency: @"USD",
  AFEventParamQuantity: @2,
  // for multiple product categories, set the param value as: @[@2, @5]
  AFEventParamOrderId: @"X123ABC",
  AFEventParamReceiptId: @"X123ABC"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("first_purchase", withValues: [  AFEventParamRevenue: 1205.99,  AFEventParamPrice : 4000,  AFEventParamContent : "ABC123",  AFEventParamContentId : "221",  // pour différentes catégories de produits, définissez la valeur du paramètre sur : ["221", "124"],  AFEventParamContentType : "shirt",  // pour différentes catégories de produits, définissez la valeur du paramètre sur : ["shoes", "pants"]  AFEventParamCurrency : "USD",  AFEventParamQuantity : 2,  // pour différentes catégories de produits, définissez la valeur du paramètre sur : [2, 5]  AFEventParamOrderId : "X123ABC",   AFEventParamReceiptId : "X123ABC"]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> FirstPurchaseEvent = new Dictionary<string, string>();
FirstPurchaseEvent.Add("af_revenue", "1205.99");
FirstPurchaseEvent.Add("af_price", "4000"); 
 FirstPurchaseEvent.Add("af_content", "ABC123"); 
 FirstPurchaseEvent.Add("af_content_id", "121"); 
 // pour différentes catégories de produits, définissez la valeur du paramètre comme suit : ["221", "124"] 
 FirstPurchaseEvent.Add("af_content_type", "shoes"); 
 // pour différentes catégories de produits, définissez la valeur du paramètre comme suit : ["shirt", "pants"] 
 FirstPurchaseEvent.Add("af_currency", "USD"); 
 FirstPurchaseEvent.Add("af_quantity", "2"); 
 // pour différentes catégories de produits, définissez la valeur du paramètre comme 
 FirstPurchaseEvent.Add("af_order_id", "X123ABC"); 
 FirstPurchaseEvent.Add("af_receipt_id", "X123ABC"); 
 AppsFlyer.sendEvent ("first_purchase", FirstPurchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="remove-from-cart-remove_from_cart" />

<Accordion title="Supprimer du panier (remove_from_cart)">

**Objectif**

L'enregistrement de cet évènement peut vous aider à :

* Savoir quels articles les acheteurs retirent de leur panier
* Voir les catégories produit des articles que les acheteurs retirent de leur panier
* Comparez les données de l'événement [Ajouter au panier](/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart) pour obtenir des informations sur les produits qui ne parviennent pas jusqu'au paiement

**Déclencheur**

Lorsque l'utilisateur retire un article du panier

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_content\_id | ID de l'article ou du produit | 521 |
| af\_content\_type | Catégorie de l'article ou du produit | Chaussures |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "521");
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "shoes");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "remove_from_cart", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"remove_from_cart"
withValues: @{
  AFEventParamContentId: @"521",
  AFEventParamContentType: @"shoes",
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("remove_from_cart", withValues: [ 
  AFEventParamContentId: "521",
  AFEventParamContentType: "shoes",
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RemoveFromCartEvent = new Dictionary<string, string>();
RemoveFromCartEvent.Add("af_content_id", "521");
RemoveFromCartEvent.Add("af_content_type", "shoes");
AppsFlyer.sendEvent ("remove_from_cart", RemoveFromCartEvent);
```

</Tab>
</Tabs>

</Accordion>
