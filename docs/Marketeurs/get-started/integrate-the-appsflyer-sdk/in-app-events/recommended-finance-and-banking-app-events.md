---
title: Événements recommandés pour les apps de gestion financière et bancaire
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
  created_at: '2021-04-27T12:58:44Z'
  edited_at: '2022-01-25T17:21:40Z'
  id: 360019598337
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/360019598337
---
> **En bref :**  mesurez la qualité de vos utilisateurs tout au long de leur parcours en enregistrant les événements in-app que nous recommandons pour votre app de gestion financière et bancaire.

<div id="-finance-and-banking" />

## <Image alt="banking.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="100px" /> Gestion financière et bancaire

Les apps financières et bancaires permettent aux utilisateurs d'effectuer un grand choix d'opérations en lien avec la gestion financière, comme l'inscription à une nouvelle carte de crédit ou une demande de prêt. Les principaux événements que nous conseillons d'enregistrer incluent les ouvertures de compte, les demandes de carte de crédit et les demandes de prêt.

L'enregistrement de ces événements peut vous aider à déterminer :

* Le type de compte que les usagers recherchent le plus, ce qui peut donner des idées pour le retargeting
* Les avantages que les utilisateurs recherchent dans une carte de crédit
* Pourquoi les utilisateurs ont besoin d'un apport financier, et combien ils demandent

<div id="important" />

> 🚧 **Important !**
>
> * Veillez à lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#introduction-setting-up-inapp-events">instructions</Anchor> à l'attention des marketeurs pour implémenter les événements in-app.
> * Pour simplifier l'implémentation, [téléchargez un fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSJsgqgzIInw8NAzY8ILsk2H4Vjp-7dRIc1Ed6vNb34mOayiTjutUs-cOnd4H5u18EvgpspKe7Dx2xb/pub?gid=221029448&single=true&output=csv) contenant tous les événements in-app de base décrits dans cet article,  puis modifiez les événements en fonction des besoins de votre entreprise. Une fois terminé, partagez le fichier avec votre développeur.
> * Pour chaque événement recommandé que contient cet article, vous trouverez des extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour plus d'informations sur l'enregistrement des événements in-app, consultez le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">guide des événements in-app riches</Anchor>.

[![Flowchart_for_recommended_events finance_banking_app_user_journey](https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png)](https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png)

<div id="recommended-structures-for-predefined-events" />

## Structures recommandées pour les événements prédéfinis

La section suivante propose une liste des structures d'événement généralement associées au secteur de la gestion financière et bancaire Chaque structure donne un nom d'événement prédéfini, ainsi que des suggestions de paramètres d'événement à appliquer. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

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
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.registration_method, "Facebook");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.complete_registration, eventValue);
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

<div id="recommended-structures-for-custom-events" />

## Structures recommandées pour les événements personnalisés

La section suivante fournit une liste de structures d'événements qui comprennent des noms d'événements personnalisés et les suggestions de paramètres d'événement à utiliser. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<Accordion title="Enregistrement vérifié (registration_verified)">

**Objectif**

Enregistrer cet évènement et le comparer avec différentes données pour en savoir plus sur vos utilisateurs. Vous pouvez par exemple savoir combien d'utilisateurs se sont inscrits mais n'ont pas été acceptés.

**Déclencheur**

Lorsque l'enregistrement est vérifié

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| submit\_registration | Le type de méthode d'inscription vérifiée. Ne pas remplir avec des informations personnelles identifiables (IPI). | email, facebook |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("submit_registration", "facebook");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "registration_verified", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"registration_verified" 
withValues: @{ 
  @"submit_registartion": @"facebook" 
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("registration_verified", 
withValues: [
  "submit_registration": "facebook"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RegistrationVerifiedEvent = new Dictionary<string, string>();
RegistrationVerifiedEvent.Add("submit_registration", "facebook");
AppsFlyer.sendEvent ("registration_verified", RegistrationVerifiedEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Soumettre une demande de compte (submit_account_application)">

**Objectif**

Enregistrer cet évènement et le comparer avec différentes données pour en savoir plus sur vos utilisateurs. Vous pouvez par exemple savoir combien d'utilisateurs se sont inscrits mais n'ont pas demandé à ouvrir de compte.

**Déclencheur**

Lorsque l'utilisateur termine la procédure de demande de compte

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| account\_type | Type de compte demandé pour | économies |
| application\_method | D'où la demande a été faite. | app |
| PII\_type | Type de pièce d'identité utilisée lors de la demande | passeport |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("account_type", "savings");  
eventValue.put("application_method", "app");
eventValue.put("PII_type", "passport");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "submit_account_application", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"submit_account_application" 
withValues: @{ 
  @"account_type": @"savings",   
 @"application_method": @"app",   
 @"PII_type": @"passport" 
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("submit_account_application",   
withValues: [   
"account_type": "savings",  
"application_method": "app",   
"PII_type": "passport"   
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubmitAccountApplicationEvent = new Dictionary<string, string>();
SubmitAccountApplicationEvent.Add("account_type", "savings");  
SubmitAccountApplicationEvent.Add("application_method", "app");
SubmitAccountApplicationEvent.Add("PII_type", "passport");
AppsFlyer.sendEvent ("submit_account_applicationn", SubmitAccountApplicationEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Ouverture du compte réussie (open_account_success)">

**Objectif**

Enregistrer cet évènement et le comparer avec différentes données pour en savoir plus sur vos utilisateurs. Vous pouvez par exemple savoir combien d'utilisateurs ont fait une demande de compte qui a abouti, et travailler à l'amélioration de l'entonnoir, ou bien recibler ces utilisateurs plus tard.

**Déclencheur**

Lorsque la demande de l'utilisateur est acceptée et que le compte est ouvert

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| account\_type | Type de compte ouvert | économies |
| application\_method | D'où la demande a été faite. | app |
| PII\_type | Type de pièce d'identité utilisée lors de la demande | carte d'identification |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("account_type", "savings");  
eventValue.put("application_method", "app");
eventValue.put("PII_type", "identification card");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "open_account_suucess", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"open_account_success" 
withValues: @{ 
    @"account_type": @"savings",   
 @"application_method": @"app",   
 @"PII_type": @"identification card"   
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("open_account_success", 
withValues: [
"account_type": "savings",  
"application_method": "app",   
"PII_type": "identification card"   
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> OpenAccountSuccessEvent = new Dictionary<string, string>();
OpenAccountSuccessEventEvent.Add("account_type", "savings");  
OpenAccountSuccessEventEvent.Add("application_method", "app");
OpenAccountSuccessEventEvent.Add("PII_type", "identification_card");
AppsFlyer.sendEvent ("open_account_success", OpenAccountSuccessEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Ouverture de compte refusée (open_account_rejected)">

**Objectif**

Enregistrer cet évènement et le comparer avec différentes données pour en savoir plus sur vos utilisateurs. Vous pouvez par exemple savoir combien d'utilisateurs ont fait une demande de compte qui a été rejetée, et travailler à l'amélioration de l'entonnoir ou bien recibler ces utilisateurs plus tard.

**Déclencheur**

Lorsque l'utilisateur finalise le processus d'inscription

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| account\_type | Type de compte demandé pour | économies |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("account_type", "savings");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "open_account_rejected", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"open_account_rejected"
withValues: @{ 
  @"account_type": @"savings" 
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("open_account_rejected", 
withValues: [
  "account_type": "savings"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> OpenAccountRejectedEvent = new Dictionary<string, string>();
OpenAccountRejectedEvent.Add("account_type", "savings");
AppsFlyer.sendEvent ("open_account_rejected", OpenAccountRejectedEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Demande de carte de crédit (submit_credit_card_app)">

**Objectif**

Enregistrer cet évènement et le comparer avec différentes données pour en savoir plus sur vos utilisateurs. Vous pouvez par exemple savoir combien d'utilisateurs ont fait une demande de carte de crédit qui a été rejetée, et améliorer l'entonnoir en conséquence, ou bien recibler ces utilisateurs plus tard.

**Déclencheur**

Lorsque l'utilisateur soumet une demande pour obtenir une nouvelle carte de crédit

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| credit\_card\_type | Type de carte de crédit demandé | carte gold |
| application\_method | D'où la demande a été faite. | app |
| PII\_type | Type de pièce d'identité utilisée lors de la demande | passeport |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("credit_card_type", "gold card");
eventValue.put("application_method", "app");
eventValue.put("PII_type", "passport");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "submit_credit_card_application", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"submit_credit_card_application"
withValues: @{
   @"credit_card_type": @"gold_card",
   @"application_method": @"app",
   @"PII_type": @"passport"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("submit_credit_card_application", 
withValues: [
   "credit_card_type": "gold_card",
   "application_method": "app",
   "PII_type": "passport"
   ])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubmitCreditCardApplicationEvent = new Dictionary<string, string>();
SubmitCreditCardApplicationEvent.Add("credit_card_type", "gold_card");
SubmitCreditCardApplicationEvent.Add("application_method", "app");
SubmitCreditCardApplicationEvent.Add("PII_type", "passport");
AppsFlyer.sendEvent ("submit_credit_card_application", SubmitCreditCardApplicationEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Demande de carte de crédit acceptée (credit_card_application_success)">

**Objectif**

Enregistrer cet évènement et le comparer avec différentes données pour en savoir plus sur vos utilisateurs. Vous pouvez par exemple savoir combien d'utilisateurs ont fait une demande de carte de crédit qui a été acceptée, et améliorer l'entonnoir en conséquence, ou bien recibler ces utilisateurs plus tard.

**Déclencheur**

Lorsque la demande de l'utilisateur pour obtenir une carte de crédit est acceptée

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| credit\_card\_type | Type de carte de crédit demandé | carte gold |
| application\_method | Où la demande a été faite. | app |
| PII\_type | Type de pièce d'identité utilisée lors de la demande | carte d'identification |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("credit_card_type", gold card);
eventValue.put("application_method", app);  
eventValue.put("PII_type", identification card);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "credit_card_application_success", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"credit_card_application_success"
withValues: @{
  @"credit_card_type": @"gold card",
  @"application_method": @"app",  
  @"PII_type": @"identification card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("credit_card_application_success",
withValues: [
 "credit_card_type": "gold card",
  "application_method": "app",  
  "PII_type": "identification card"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CreditCardApplicationSuccessEvent = new Dictionary<string, string>();
CreditCardApplicationSuccessEvent.Add("redit_card_type", "gold card");
CreditCardApplicationSuccessEvent.Add("application_method", "app");
CreditCardApplicationSuccessEvent.Add("PII_type", "identificationcard");
AppsFlyer.sendEvent ("credit_card_application_success", CreditCardApplicationSuccessEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Demande de carte de crédit refusée (credit_card_application_rejected)">

**Objectif**

Enregistrer cet évènement et le comparer avec différentes données pour en savoir plus sur vos utilisateurs. Vous pouvez par exemple savoir combien d'utilisateurs ont fait une demande de carte de crédit qui a été refusée, et améliorer l'entonnoir en conséquence, ou bien recibler ces utilisateurs plus tard.

**Déclencheur**

Lorsque la demande de l'utilisateur pour obtenir une carte de crédit est refusée

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| credit\_card\_type | Type de carte de crédit demandé | carte gold |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("credit_card_type", "gold card");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "credit_card_application_rejected", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent: @"credit_card_application_rejected"
withValues: @{
  "credit_card_type: @"gold card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("credit_card_application_rejected", 
withValues: [
  "credit_card_type: "gold card"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CreditCardApplicationRejectedEvent = new Dictionary<string, string>();
CreditCardApplicationRejectedEvent.Add("credit_card_type", "gold card");
AppsFlyer.sendEvent ("credit_card_application_rejected", CreditCardApplicationRejectedEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Activation de la carte de crédit (credit_card_activation)">

**Objectif**

Enregistrer cet évènement et le comparer avec différentes données pour en savoir plus sur vos utilisateurs. Vous pouvez par exemple savoir combien d'utilisateurs ont obtenu une carte de crédit mais ne l'ont pas activée, et améliorer l'entonnoir en conséquence, ou bien recibler ces utilisateurs plus tard.

**Déclencheur**

Lorsqu'un utilisateur active sa nouvelle carte de crédit

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| credit\_card\_type | Type de carte de crédit demandé | carte gold |
| application\_method | D'où la demande a été faite. | app |
| PII\_type | Type de pièce d'identité utilisée lors de la demande | carte d'identification |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("credit_card_type", gold card);
eventValue.put("application_method", app);  
eventValue.put("PII_type", identification card);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "credit_card_activation", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent: @"credit_card_activation"
withValues: @{
  @"credit_card_type": @"gold card",
  @"application_method: @"app",  
  @"PII_type": @"identification card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("credit_card_activation", 
withValues: [
 "credit_card_type": "gold card",
  "application_method": "app",  
  "PII_type": "identification card"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CreditCardActivationEvent = new Dictionary<string, string>();
CreditCardActivationEvent.Add("credit_card_type", "gold card");
CreditCardActivationEvent.Add(application_method", "app");  
CreditCardActivationEvent.Add(PII_type", "identification_card");
AppsFlyer.sendEvent ("credit_card_activation", CreditCardActivationEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Soumettre une demande de prêt (submit_loan_application)">

**Objectif**

Cet évènement peut vous aider à :

* Déterminer le nombre total de demandes de prêt dans votre app
* En apprendre plus sur le montant maximum, minimum et moyen des demandes de prêt.
* Savoir quels types de prêts les personnes sollicitent

**Déclencheur**

Lorsque l'utilisateur soumet avec succès une demande de prêt

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| loan\_id | ID du prêt | 1735102 |
| loan\_type | Objet du prêt | logement |
| loan\_amount | Montant demandé | 1000 |
| loan\_period | Durée du prêt | 3 mois |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("loan_id", "1735102");  
eventValue.put("loan_type", "housing");
eventValue.put("loam_amount", "1000");
eventValue.put("loan_period", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"submit_loan_application", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent: @"submit_loan_application"
withValues: @{
  @"loan_id": @"1735102",  
@"loan_type": @"housing",
  @"loan_amount": @"1000",
  @"loan_period": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("submit_loan_application", 
withValues: [
   "loan_id": "1735102",  
"loan_type": "housing",
   "loan_amount": "1000",
   "loan_period": "3 months"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubmitLoanApplication = new Dictionary<string, string>();
SubmitLoanApplication.Add("loan_id", "1735102");  
SubmitLoanApplication.Add("loan_type", "housing");
SubmitLoanApplication.Add("loan_amount", "1000");
SubmitLoanApplication.Add("loan_period", "3 months");
AppsFlyer.sendEvent("submit_loan_application", SubmitLoanApplication);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Prêt accepté (loan_accepted)">

**Objectif**

Découvrir les tendances en matière de prêts et autres métriques. Cet événement peut vous aider à déterminer :

* Les types de prêts qui sont acceptés
* Le montant qui est demandé pour les prêts accordés
* Quels sont les créditeurs qui acceptent le plus de demande de prêt

**Déclencheur**

Lorsqu'un prêt est accepté

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| loan\_id | ID du prêt | 1735102 |
| loan\_type | Objet du prêt | logement |
| loan\_amount | Montant demandé | 1000 |
| loan\_period | Durée du prêt | 3 mois |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("loam_amount", "1000");
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"loan_accepted" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent: @"loan_accepted"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @"1000",
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("loan_accepted", 
withValues: [
  "loan_id": "1735102",
  "loan_amount": "1000",
  "loan_type": "3 months"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LoanAccepted = new Dictionary<string, string>();
LoanAccepted.Add("loan_id", "1735102");
LoanAccepted.Add("loan_amount", "1000");
LoanAccepted.Add("loan_type", "3 months");
AppsFlyer.sendEvent("loan_accepted", LoanAccepted);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Prêt rejeté (loan_rejected)">

**Objectif**

Comprendre pourquoi les prêts sont refusés. Vous pouvez voir la corrélation entre le montant, la durée du prêt et les taux de refus. Vous pouvez également recibler les utilisateurs dont le prêt a été refusé et leur suggérer de solliciter un prêt d'un montant moins élevé.

**Déclencheur**

Quand un créditeur refuse un prêt

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| loan\_id | ID du prêt | 1735102 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("loan_id", "1735102");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "loan_rejected" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"loan_rejected"
withValues: @{
  @"loan_id": @"1735102",
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("loan_rejected",   
withValues: [
  "loan_id": "1735102",
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LoanRejected = new Dictionary<string, string>();
LoanRejected.Add("loan_id", "1735102");
AppsFlyer.sendEvent("loan_rejected", LoanRejected);
```

</Tab>
</Tabs>

</Accordion>
