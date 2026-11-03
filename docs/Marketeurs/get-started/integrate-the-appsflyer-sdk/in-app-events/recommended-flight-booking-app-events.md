---
title: ' Événements recommandés pour les apps de réservation de vols'
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-04-29T13:07:29Z'
  edited_at: '2022-01-25T17:24:26Z'
  id: 360019670857
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/360019670857
---
> **En bref :** mesurez la qualité de vos utilisateurs tout au long de leur parcours en enregistrant ces événements in-app suggérés pour votre app de réservation de vols.
>
> ## <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="100px" /> Réservation de vols
>
> Les apps de réservation de vols permettent aux voyageurs de réserver facilement des vols et d'obtenir les meilleures offres. Les évènements que nous vous recommandons d'enregistrer sont la réservation d'un vol, la recherche de vols et la visualisation des offres.
>
> L'enregistrement de cet évènement peut vous aider à :
>
> * Découvrir les destinations populaires.
> * Analyser les tendances saisonnières
> * Découvrir les compagnies aériennes populaires avec lesquelles les utilisateurs préfèrent voyager
>
> **Important !**
>
> * Veillez à lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#introduction-setting-up-inapp-events">instructions</Anchor> à l'attention des marketeurs pour implémenter les événements in-app.
> * Pour simplifier l'implémentation, [téléchargez un fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSJsgqgzIInw8NAzY8ILsk2H4Vjp-7dRIc1Ed6vNb34mOayiTjutUs-cOnd4H5u18EvgpspKe7Dx2xb/pub?gid=768870019&single=true&output=csv) contenant tous les événements in-app de base décrits dans cet article,  puis modifiez les événements en fonction des besoins de votre entreprise. Une fois terminé, partagez le fichier avec votre développeur.
> * Pour chaque événement recommandé que contient cet article, vous trouverez des extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour plus d'informations sur l'enregistrement des événements in-app, consultez le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">guide des événements in-app riches</Anchor>.
>
>
>
> [![Flowchart_for_recommended_events flight_booking_app_user_journey](https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png)](https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png)
>
> ## Structures recommandées pour les événements prédéfinis
>
> La section suivante fournit une liste des structures d'événements typiques du secteur de la réservation de vols. Chaque structure donne un nom d'événement prédéfini, ainsi que des suggestions de paramètres d'événement à appliquer. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.
>
>
> <Accordion title="Inscription terminée (af_complete_registration)">
>
> **Objectif**
>
> Découvrez combien d'utilisateurs ont installé l'app et terminé le processus d'inscription, ainsi que les méthodes d'inscription préférées de vos utilisateurs.
>
> **Déclencheur**
>
> Lorsque l'utilisateur finalise le processus d'inscription
>
> Paramètres d'événement
>
>
>
> | Nom du champ | Description | Exemple de valeur |
> | --- | --- | --- |
> | af\_registration\_method | Le type de méthode d'inscription | email, facebook |
>
>
>
> **Exemples de code**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.REGSITRATION_METHOD, "Facebook");
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.COMPLETE_REGISTRATION, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventCompleteRegistration
> withValues: @{ 
>   AFEventParamRegistrationMethod: @"Facebook" 
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventCompleteRegistration, 
> withValues: [
>   AFEventParamRegistrationMethod: "Facebook"
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> CompletedRegistrationEvent = new Dictionary<string, string>();
> CompletedRegistrationEvent.Add("af_registration_method", "Facebook");
> AppsFlyer.sendEvent ("af_complete_registration", CompletedRegistrationEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Connexion (af_login)">
>
> **Objectif**
>
> Comprendre le taux de rétention de vos utilisateurs inscrits
>
> **Déclencheur**
>
> Lorsque l'utilisateur se connecte avec succès
>
> **Paramètres d'événement**
>
> Peut être envoyé sans paramètre supplémentaire
>
> **Exemples de code**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(),   
> AFInAppEventType.LOGIN, null);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventLogin  
>  withValues: nil  
> ];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventLogin, withValues: nil);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> AppsFlyer.sendEvent ("af_login", null);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Réservation de voyage (travel_booking)">
>
> **Objectif**
>
> La possibilité de réserver des vols constitue la fonctionnalité principale de l'app. Cet événement peut vous aider à déterminer :
>
> * Destinations populaires
> * Compagnies aériennes populaires
> * Tendances saisonnières
>
> **Déclencheur**
>
> Lorsque l'utilisateur atterrit sur la page de remerciement une fois la réservation de vol terminée
>
> **Paramètres d'événement**
>
>
>
> | Nom | Description | Exemple de valeur |
> | --- | --- | --- |
> | <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Revenu associé à la réservation | 647.99 |
> | af\_currency | Code de devise | SGD |
> | af\_price | Prix | 674 |
> | af\_content\_id | ID de l'offre de vol | ODIRNH |
> | af\_departing\_departure\_date | Date de départ | 2018-06-21 |
> | af\_returning\_departure\_date | Date de retour | 2018-06-26 |
> | af\_destination\_a | Première destination | BKK |
> | af\_destination\_b | Deuxième destination (le cas échéant) | SYD |
> | airline\_code | Code de la compagnie aérienne | KLM |
> | af\_class | Classe du vol réservé | classe économique |
> | purchase\_method | Méthode d'achat | carte de crédit |
>
>
>
> **Exemples de code**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.REVENUE, 647.99);
> eventValue.put(AFInAppEventParameterName.CURRENCY, "SGD");
> eventValue.put(AFInAppEventParameterName.PRICE, 674);
> eventValue.put(AFInAppEventParameterName.CONTENT_ID, "ODIRNH");
> eventValue.put(AFInAppEventParameterName.DEPARTING_DEPARTURE_DATE, "2018-06-21");
> eventValue.put(AFInAppEventParameterName.RETURNING_DEPARTURE_DATE, "2018-06-26");
> eventValue.put(AFInAppEventParameterName.DESTINATION_A, "BKK");
> eventValue.put(AFInAppEventParameterName.DESTINATION_B, "SYD");
> eventValue.put("airline_code", "KLM");
> eventValue.put(AFInAppEventParameterName.CLASS, "economy");
> eventValue.put("purchase_method", "credit card");
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.TRAVEL_BOOKING, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventTravelBooking
> withValues: @{
>  AFEventParamRevenue: @647.99,
>  AFEventParamCurrency: @"SGD",
>  AFEventParamPrice: @674,
>  AFEventParamContentId: @"ODIRNH",
>  AFEventParamDepartingDepartureDate: @"2018-21-06",
>  AFEventParamReturningDepartureDate: @"2018-26-06",
>  AFEventParamDestinationA: @"BKK",
>  AFEventParamDestinationB: @"SYD",
>  @"airline_code": @"KLM",
>  AFEventParamClass: @"economy",
>  @"purchase_method": @"credit card"
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventTravelBooking, 
> withValues: [
>  AFEventParamRevenue: 647.99,
>  AFEventParamCurrency: "SGD",
>  AFEventParamPrice: 674,
>  AFEventParamContentId: "ODIRNH",
>  AFEventParamDepartingDepartureDate: "2018-21-06",
>  AFEventParamReturningDepartureDate: "2018-26-06",
>  AFEventParamDestinationA: "BKK",
>  AFEventParamDestinationB: "SYD",
>  "airline_code": "KLM",
>  AFEventParamClass: "economy",
>  "purchase_method": "credit card"
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> TravelBookingEvent = new Dictionary<string, string>();
> TravelBookingEvent.Add("af_revenue", "647.99");
> TravelBookingEvent.Add("af_currency", "SGD");
> TravelBookingEvent.Add("af_price", "974");
> TravelBookingEvent.Add("af_content_id", "ODIRNH");
> TravelBookingEvent.Add("af_departing_departure_date", "2018-06-21");
> TravelBookingEvent.Add("af_returning_departure_date", "2018-06-26");
> TravelBookingEvent.Add("af_destination_a", "BKK");
> TravelBookingEvent.Add("af_destination_b", "SYD");
> TravelBookingEvent.Add("airline_code", "KLM");
> TravelBookingEvent.Add("af_class", "economy");
> TravelBookingEvent.Add("purchase_method", "credit card");
> AppsFlyer.sendEvent ("af_travel_booking", TravelBookingEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Affichage du contenu (af_content_view)">
>
> **Objectif**
>
> Cet événement peut vous aider à déterminer :
>
> * Les offres de vol les plus attrayantes pour les utilisateurs
> * Si les résultats proposés répondent bien aux éléments recherchés
>
> **Déclencheur**
>
> Lorsqu'un utilisateur clique sur un résultat de recherche
>
> **Paramètres d'événement**
>
>
>
> | Nom | Description | Exemple de valeur |
> | --- | --- | --- |
> | af\_departing\_departure\_date | Date de départ | 2018-06-21 |
> | af\_returning\_departure\_date | Date de retour | 2018-06-26 |
> | af\_destination\_a | Première destination | BKK |
> | af\_destination\_b | Deuxième destination (le cas échéant) | SYD |
>
>
>
> **Exemples de code**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.DEPARTING_DEPARTURE_DATE, "2018-06-21");
> eventValue.put(AFInAppEventParameterName.RETURNING_DEPARTURE_DATE, "2018-06-26");
> eventValue.put(AFInAppEventParameterName.DESTINATION_A, "BKK");
> eventValue.put(AFInAppEventParameterName.DESTINATION_B, "SYD");
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.CONTENT_VIEW, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventContentView
> withValues: @{
>   AFEventParamDepartingDepartureDate: @"2018-21-06",
>   AFEventParamReturningDepartureDate: @"2018-26-06",
>   AFEventParamDestinationA: @"BKK",
>   AFEventParamDestinationB: @"SYD"
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventContentView, withValues: [
>  AFEventParamDepartingDepartureDate: "2018-21-06",
>  AFEventParamReturningDepartureDate: "2018-26-06",
>  AFEventParamDestinationA: "BKK",
>  AFEventParamDestinationA: "SYD"
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> ContentViewEvent = new Dictionary<string, string>();
> ContentViewEvent.Add("af_departing_departure_date", "2018-06-21");
> ContentViewEvent.Add("af_returning_departure_date", "2018-06-26");
> ContentViewEvent.Add("af_destination_a", "BKK");
> ContentViewEvent.Add("af_destination_b", "SYD");
> AppsFlyer.sendEvent ("af_content_view", ContentViewEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Recherche (af_search)">
>
> **Objectif**
>
> Les apps de réservation de vols permettent aux utilisateurs de rechercher des vols et des offres. Pour obtenir des informations sur les préférences des utilisateurs, vous pouvez par exemple enregistrer les paramètres de recherche. Cet évènement peut vous aider à :
>
> * Savoir ce que les utilisateurs recherchent
> * Découvrir quelles destinations sont les plus demandées
> * Découvrir le nombre d'utilisateurs voyageant avec des enfants
> * Découvrir à quelle période de l'année les utilisateurs préfèrent ou prévoient de voyager
>
> **Déclencheur**
>
> Après que l'utilisateur a rempli le formulaire de recherche et cliqué sur le bouton de recherche
>
> **Paramètres d'événement**
>
>
>
> | Nom | Description | Exemple de valeur |
> | --- | --- | --- |
> | af\_num\_children | Nombre d'enfants qui voyagent | 0 |
> | af\_destination\_a | Première destination | BKK |
> | af\_destination\_b | Deuxième destination (le cas échéant) | SYD |
> | af\_departing\_departure\_date | Date de départ | 2018-06-21 |
> | af\_returning\_departure\_date | Date de retour | 2018-06-26 |
> | af\_num\_infants | Nombre de bébés qui voyagent | 0 |
> | af\_num\_adults | Nombre d'adultes qui voyagent | 1 |
>
>
>
> **Exemples de code**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, 
> eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
> eventValue.put(AFInAppEventParameterName.DESTINATION_A, "BKK");
> eventValue.put(AFInAppEventParameterName.DESTINATION_B, "SYD");
> eventValue.put(AFInAppEventParameterName.DEPARTING_DEPARTURE_DATE, "2018-06-21");
> eventValue.put(AFInAppEventParameterName.RETURNING_DEPARTURE_DATE, "2018-06-26");
> eventValue.put(AFInAppEventParameterName.NUM_INFANTS, 0);
> eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 1);
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.SEARCH, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventSearch
> withValues: @{
>  AFEventParamNumChildren: @0,
>  AFEventParamDestinationA: @"BKK",
>  AFEventParamDestinationB: @"SYD",
>  AFEventParamDepartingDepartureDate: @"2018-21-06",
>  AFEventParamReturningDepartureDate: @"2018-26-06",
>  AFEventParamNumInfants: @0,
>  AFEventParamNumAdults: @1
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventSearch, withValues: [
>  AFEventParamNumChildren: 0,
>  AFEventParamDestinationA: "BKK",
>  AFEventParamDestinationB: "SYD",
>  AFEventParamDepartingDepartureDate: "2018-21-06",
>  AFEventParamReturningDepartureDate: "2018-26-06",
>  AFEventParamNumInfants: 0,
>  AFEventParamNumAdults: 1
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> SearchEvent = new Dictionary<string, string>();
> SearchEvent.Add("af_num_children", "0");
> SearchEvent.Add("af_destination_a", "BKK");
> SearchEvent.Add("af_destination_b", "SYD");
> SearchEvent.Add("af_departing_departure_date", "2018-06-21");
> SearchEvent.Add("af_returning_departure_date", "2018-06-26");
> SearchEvent.Add("af_num_infants", "0");
> SearchEvent.Add("af_num_adults", "0");
> AppsFlyer.sendEvent ("af_search", SearchEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Ajouter des informations de paiement (af_add_payment_info)">
>
> **Objectif**
>
> Enregistrer les tentatives réussies et infructueuses d'ajout des informations de paiement lors de la réservation d'un vol.
>
> **Déclencheur**
>
> Lorsqu'un utilisateur clique sur le bouton de réservation
>
> **Paramètres d'événement**
>
>
>
> | Nom | Description | Exemple de valeur |
> | --- | --- | --- |
> | af\_success | Si l'ajout de la méthode de paiement a réussi ou non | true |
>
>
>
> **Exemples de code**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.SUCCESS, true);
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.ADD_PAYMENT_INFO, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventAddPaymentInfo
> withValues: @{
>   AFEventParamSuccess: @TRUE
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventAddPaymentInfo, 
> withValues: [
>   AFEventParamSuccess: true
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> AddPaymentInfoEvent = new Dictionary<string, string>();
> AddPaymentInfoEvent.Add("af_success", "true");
> AppsFlyer.sendEvent ("af_add_payment_info", AddPaymentInfoEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Achat (af_purchase)">
>
> **Objectif**
>
> Découvrir les tendances d'achat dans votre app de réservation de vols. Cet évènement peut vous aider à :
>
> * Déterminer la LTV de vos utilisateurs et le ROI de vos campagnes sur les réseaux publicitaires et les agences de publicité
> * Déterminer quelles offres sont les plus populaires auprès de vos utilisateurs
> * Réaliser une référence croisée de campagne avec les articles qui ont été achetés afin d'optimiser le ciblage de vos campagnes
>
> **Déclencheur**
>
> Lorsque l'utilisateur atterrit sur la page de remerciement une fois l'achat terminé
>
> **Paramètres d'événement**
>
>
>
> | Nom | Description | Exemple de valeur |
> | --- | --- | --- |
> | <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Le revenu estimé provenant de l'achat | 1205.99 |
> | af\_price | Montant global des achats | 4000 |
> | af\_content\_id | ID de l'article | 121 |
> | af\_content\_type | Catégorie de l'article | flight |
> | af\_currency | Code de devise | AUD |
> | af\_quantity | Nombre d'articles dans le panier | 1 |
> | af\_order\_id | ID de la commande générée après l'achat. | X123ABC |
> | af\_receipt\_id | ID de commande, nécessaire pour l'intégration du retargeting CRITEO et Google AdWords | X123ABC |
>
>
>
> **Exemples de code**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.PRICE, 4000);
> eventValue.put(AFInAppEventParameterName.CONTENT_ID, "121");
> // for multiple product categories, set the param value as: // new String {"121", "262"}
> eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "flight");
> // for multiple product categories,, set the param value as: new String {"flight", "meals"}
> eventValue.put(AFInAppEventParameterName.CURRENCY, "AUD");
> eventValue.put(AFInAppEventParameterName.QUANTITY, 2);
> // for multiple product categories, set the param value as: new int {2, 5}
> eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "X123ABC");
> eventValue.put("af_order_id", "X123ABC");
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.PURCHASE, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventPurchase
> withValues: @{
>   AFEventParamRevenue: @1205.99,
>   AFEventParamPrice: @4000,
>   AFEventParamContentId: @"121",
>   // for multiple product categories, set the param value as:   
>   // @[@"121", @"124"]
>   AFEventParamContentType: @"flight",
>   // for multiple product categories, set the param value as:   
>   // @[@"flight", @"meals"]
>   AFEventParamCurrency: @"AUD",
>   AFEventParamQuantity: @2,
>   // for multiple product categories, set the param value as:   
>   // @[@2, @5]
>   AFEventParamOrderId: @"X123ABC",
>   AFEventParamReceiptId: @"X123ABC"
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventPurchase, withValues: [
>   AFEventParamRevenue: 1205.99,
>   AFEventParamPrice: 4000,
>   AFEventParamContentId: "121",
>   // for multiple product categories, set the param value as: ["221", "124"],
>   AFEventParamContentType: "flight",
>   // for multiple product categories, set the param value as: ["flight", "meals"] 
>   AFEventParamCurrency: "AUD",
>   AFEventParamQuantity: 2,
>   // for multiple product categories, set the param value as: [2, 5]
>   AFEventParamOrderId: "X123ABC", 
>   AFEventParamReceiptId: "X123ABC"
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> PurchaseEvent = new Dictionary<string, string>();
> PurchaseEvent.Add("af_revenue", "1205.99");
> PurchaseEvent.Add("af_price", "4000");
> PurchaseEvent.Add("af_content_id", "121");
> // for multiple product categories, set the param value as: ["121", "124"]
> PurchaseEvent.Add("af_content_type", "flight");
> // for multiple product categories, set the param value as: ["flight", "meals"]
> PurchaseEvent.Add("af_currency", "AUD");
> PurchaseEvent.Add("af_quantity", "2");
> // for multiple product categories, set the param value as: [2, 5] 
> PurchaseEvent.Add("af_order_id", "X123ABC");
> PurchaseEvent.Add("af_receipt_id", "X123ABC");
> AppsFlyer.sendEvent ("af_purchase", PurchaseEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
> ## Structures recommandées pour les événements personnalisés
>
> La section suivante fournit une liste de structures d'événements qui comprennent des noms d'événements personnalisés et les suggestions de paramètres d'événement à utiliser. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.
>
>
> <Accordion title="Premier achat (first_purchase)">
>
> **Objectif**
>
> Identique à l'événement [Achat](/docs/recommended-flight-booking-app-events#purchase-af_purchase). Cet événement peut également vous aider à déterminer :
>
> * Combien de temps il faut à un nouvel acheteur pour procéder à l'achat
> * Les vols que les nouveaux acheteurs réservent le plus
> * Le prix moyen et les revenus issus des premiers achats
>
> **Déclencheur**
>
> Lorsque l'utilisateur finalise son premier achat
>
> **Paramètres d'événement**
>
>
>
> | Nom | Description | Exemple de valeur |
> | --- | --- | --- |
> | <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Revenu des achats | 1205.99 |
> | af\_price | Montant global des achats | 4000 |
> | af\_content\_id | ID de l'article | 121, 262 |
> | af\_content\_type | Catégorie de l'article | flight |
> | af\_currency | Devise | AUD |
> | af\_quantity | Quantité d'articles dans le panier | 1 |
> | af\_order\_id | ID de la commande qui est généré après l'achat. | X123ABC |
> | af\_receipt\_id | ID de commande, nécessaire pour l'intégration du retargeting CRITEO et Google AdWords | X123ABC |
>
>
>
> **Exemples de code**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.PRICE, 4000);
> eventValue.put(AFInAppEventParameterName.CONTENT_ID, "221");
> // for multiple product categories, set the param value as: new String {"221", "124"}
> eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "flight");
> // for multiple product categories set the param value as: new String {"flight", "meal"}
> eventValue.put(AFInAppEventParameteName.CURRENCY, "USD");
> eventValue.put(AFInAppEventParameterName.QUANTITY, 2);
> // for multiple product categories, set the param value as: new int {1}
> eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "X123ABC");
> eventValue.put("af_order_id", "X123ABC");
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "first_purchase", eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:("first_purchase")
> withValues: @{
>   AFEventParamRevenue: @1205.99,
>   AFEventParamPrice: @4000,
>   AFEventParamContentId: @"221",
>   // for multiple product categories, set the param value as: @[@"221", @"124"]
>   AFEventParamContentType: @"flight",
>   // for multiple product categories, set the param value as: @[@"flight" , @"meal"]
>   AFEventParamCurrency: @"USD",
>   AFEventParamQuantity: @2,
>   // for multiple product categories, set the param value as: @[@1]
>   AFEventParamOrderId: @"X123ABC",
>   AFEventParamReceiptId: @"X123ABC"
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent("first_purchase", withValues: [ 
>   AFEventParamRevenue: 1205.99,
>   AFEventParamPrice: 4000,
>   AFEventParamContentId: "221",
>   // for multiple product categories, set the param value as: ["221", "124"]
>   AFEventParamContentType: "flight",
>   // for multiple product categories, set the param value as: ["flight", "meal"]
>   AFEventParamCurrency: "USD",
>   AFEventParamQuantity: 2,
>   // for multiple product categories, set the param value as: // [1]
>   AFEventParamOrderId: "X123ABC",
>   AFEventParamReceiptId: "X123ABC"
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> FirstPurchaseEvent = new Dictionary<string, string>();
> FirstPurchaseEvent.Add("af_revenue", "1205.99");
> FirstPurchaseEvent.Add("af_price", "4000");
> FirstPurchaseEvent.Add("af_content_id", "121");
> // for multiple product categories, set the param value as: ["221", "124"]
> FirstPurchaseEvent.Add("af_content_type", "flight");
> // for multiple product categories, set the param value as: ["flight", "meal"]
> FirstPurchaseEvent.Add("af_currency", "USD");
> FirstPurchaseEvent.Add("af_quantity", "2");
> // for multiple product categories, set the param value as: [1] 
> FirstPurchaseEvent.Add("af_order_id", "X123ABC");
> FirstPurchaseEvent.Add("af_receipt_id", "X123ABC");
> AppsFlyer.sendEvent ("first_purchase", FirstPurchaseEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>