---
title: Événements recommandés pour les apps de prêt P2P
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
  created_at: '2021-04-28T09:01:59Z'
  edited_at: '2022-01-25T17:24:52Z'
  id: 360019614017
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/360019614017
---
> **En bref :** mesurez la qualité de vos utilisateurs tout au long de leur parcours en enregistrant ces événements in-app suggérés pour votre app de prêts P2P .

<div id="-p2p-lending" />

## <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="100px" /> Prêts P2P

Le prêt P2P est une nouvelle façon pour les particuliers et les entreprises de prêter et d'emprunter de l'argent. Les événements typiques que nous vous conseillons d'enregistrer sont les activités des prêteurs et des emprunteurs individuels, les types de prêts proposés, et les taux d'acceptation et de rejet des prêts.

Les données rassemblées via l'enregistrement d'évènements vous permettent de mettre en évidence les emprunteurs fiables et de leur offrir de meilleurs taux d'intérêt. De même, vous pouvez découvrir qui sont les prêteurs les plus actifs et leur proposer des frais réduits. De plus, une fois que vous savez quels types de prêts sont les plus populaires auprès de vos utilisateurs, vous pouvez lancer des campagnes marketing qui ciblent ces audiences.

<div id="important" />

> 🚧 **Important !**
>
> * Veillez à lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#introduction-setting-up-inapp-events">instructions</Anchor> à l'attention des marketeurs pour implémenter les événements in-app.
> * Pour simplifier l'implémentation, [téléchargez un fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSJsgqgzIInw8NAzY8ILsk2H4Vjp-7dRIc1Ed6vNb34mOayiTjutUs-cOnd4H5u18EvgpspKe7Dx2xb/pub?gid=1307505217&single=true&output=csv) contenant tous les événements in-app de base décrits dans cet article, puis modifiez les événements en fonction des besoins de votre entreprise. Une fois terminé, partagez le fichier avec votre développeur.
> * Pour chaque événement recommandé que contient cet article, vous trouverez des extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour plus d'informations sur l'enregistrement des événements in-app, consultez le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">guide des événements in-app riches</Anchor>.

[![Flowchart_for_recommended_events P2P_lending_app_user_journey](https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png)](https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png)

<div id="recommended-structures-for-predefined-events" />

## Structures recommandées pour les événements prédéfinis

La section suivante fournit une liste des structures d'événements typiques du secteur des prêts P2P. Chaque structure donne un nom d'événement prédéfini, ainsi que des suggestions de paramètres d'événement à appliquer. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Inscription terminée (af_complete_registration)">

**Objectif**

Découvrez combien d'utilisateurs achèvent le processus de vérification de l'identité après s'être inscrits. Vous pouvez attribuer ces utilisateurs aux campagnes et découvrir quelles campagnes génèrent des utilisateurs actifs.

**Déclencheur**

Lorsque l'inscription de l'utilisateur est approuvée

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
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
Dictionary<string, string> CompleteRegistration = new Dictionary<string, string>();
CompleteRegistration.Add("af_registration_method", "Facebook");
AppsFlyer.sendEvent("af_complete_registration", CompleteRegistration);
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

<div id="recommended-structures-for-custom-events" />

## Structures recommandées pour les événements personnalisés

La section suivante fournit une liste de structures d'événements qui comprennent des noms d'événements personnalisés et les suggestions de paramètres d'événement à utiliser. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<div id="registration-submitted-registration_submitted" />

<Accordion title="Enregistrement soumis (registration_submitted)">

**Objectif**

Le prêt P2P étant soumis aux risques, les utilisateurs doivent d'abord vérifier leur identité. Ils le font en soumettant une demande d'inscription. Cet évènement peut vous aider à :

* Enregistrer le nombre d'utilisateurs qui s'inscrivent mais qui ne confirment pas leur compte via la vérification
* Établir la corrélation entre la méthode d'inscription (email, Facebook, Google) et les taux de vérification

**Déclencheur**

Après que l'utilisateur a soumis une demande d'inscription

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_registration\_method | Le type de méthode d'inscription | email, facebook |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REGSITRATION_METHOD, "Facebook");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "registration_submitted", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"registration_submitted" 
withValues: @{
  AFEventParamRegistrationMethod: @"Facebook",
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("registration_submitted", 
withValues: [
  AFEventParamRegistrationMethod: "Facebook"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RegistrationSubmitted = new Dictionary<string, string>();
RegistrationSubmitted.Add("af_registration_method", "Facebook");
AppsFlyer.sendEvent("registration_submitted", RegistrationSubmitted);
```

</Tab>
</Tabs>

</Accordion>

<div id="fill-loan-form-fill_loan_form_form_name" />

<Accordion title="Formulaire de prêt (fill_loan_form_&lt;FORM_NAME>)">

**Objectif**

Déterminer le taux d'abandon et recibler les emprunteurs qui ne complètent pas leur demande de prêt.

Lorsque vous envoyez cet évènement, précisez le nom du formulaire dans le nom de l'évènement.

**Déclencheur**

Lorsqu'un emprunteur soumet un formulaire

**Paramètres d'événement**

Peut être envoyé sans paramètre supplémentaire

> 📘 **Note**
>
> Nous vous recommandons fortement d'associer les prêts aux créditeurs. Pour ce faire, pensez à définir l'ID utilisateur du client (CUID). <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">Définir l'ID utilisateur du client</Anchor> est le meilleur moyen d'associer les organismes créditeurs avec les utilisateurs de votre app, tels qu'affichés dans AppsFlyer. En définissant l'ID utilisateur du client, vous vous assurez que tout événement sera envoyé accompagné de l'ID utilisateur du client.
>
> **Exemples de code**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "fill_loan_form_FORM_NAME", null);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:@"fill_loan_formFORM_NAME" 
> withValues: nil];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent("fill_loan_form_FORM_NAME", 
> withValues: nil);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> AppsFlyer.sendEvent("fill_loan_form_FORM_NAME", null);
> ```
>
> </Tab>
> </Tabs>
>

<div id="submit-loan-application-submit_loan_application" />

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
| loan\_amount | Montant demandé | 1000 |
| loan\_type | Durée du prêt | 3 mois |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("loam_amount", 1000);
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"submit_loan_application", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"submit_loan_application"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @1000,
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("submit_loan_applications", 
withValues: [
   "loan_id": "1735102",
   "loan_amount": 1000,
   "loan_type": "3 months"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubmitLoanApplication = new Dictionary<string, string>();
SubmitLoanApplication.Add("loan_id", "1735102");
SubmitLoanApplication.Add("loan_amount", "1000");
SubmitLoanApplication.Add("loan_type", "3 months");
AppsFlyer.sendEvent("submit_loan_application", SubmitLoanApplication);
```

</Tab>
</Tabs>

</Accordion>

<div id="loan-form-loan_form" />

<Accordion title="Formulaire de prêt (loan_form)">

**Objectif**

Examiner les demandes de prêt soumises par les emprunteurs

**Déclencheur**

Lorsque l'emprunteur soumet avec succès une demande de prêt

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| loan\_id | ID du prêt | 1735102 |
| loan\_amount | Montant demandé | 1000 |
| loan\_type | Durée du prêt | 3 mois |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("loam_amount", 1000);
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"loan_form", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"loan_form"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @1000,
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("loan_form", 
withValues: [
   "loan_id": "1735102",
   "loan_amount": 1000,
   "loan_type": "3 months"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LoanForm = new Dictionary<string, string>();
SubmitLoanApplication.Add("loan_id", "1735102");
SubmitLoanApplication.Add("loan_amount", "1000");
SubmitLoanApplication.Add("loan_type", "3 months");
AppsFlyer.sendEvent("loan_form", LoanForm);
```

</Tab>
</Tabs>

</Accordion>

<div id="submit-credit-check-submit_credit_check" />

<Accordion title="Soumettre une vérification de crédit (submit_credit_check)">

**Objectif**

Vérifier l'historique financier de l'emprunteur (par exemple, crédit passé, habitudes de paiement et types de prêts) pour évaluer le niveau de risque.

**Déclencheur**

Après que le prêteur a reçu une demande de prêt

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| loan\_id | ID du prêt | 1735102 |
| loan\_amount | Montant demandé | 1000 |
| loan\_type | Durée du prêt | 3 mois |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("loam_amount", 1000);
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"submit_credit_check", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"submit_credit_check"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @1000,
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("submit_credit_check", 
withValues: [
   "loan_id": "1735102",
   "loan_amount": 1000,
   "loan_type": "3 months"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubmitCreditCheck = new Dictionary<string, string>();
SubmitLoanApplication.Add("loan_id", "1735102");
SubmitLoanApplication.Add("loan_amount", "1000");
SubmitLoanApplication.Add("loan_type", "3 months");
AppsFlyer.sendEvent("submit_credit_check", SubmitCreditCheck);
```

</Tab>
</Tabs>

</Accordion>

<div id="loan-accepted-loan_accepted" />

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
| loan\_amount | Montant demandé | 1000 |
| loan\_type | Durée du prêt | 3 mois |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("loam_amount", 1000);
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"loan_accepted" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"loan_accepted"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @1000,
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("loan_accepted", 
withValues: [
  "loan_id": "1735102",
  "loan_amount": 1000,
  "loan_type": "3 months"
]);
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

<div id="loan-rejected-loan_rejected" />

<Accordion title="Prêt rejeté (loan_rejected)">

**Objectif**

Comprenez les raisons pour lesquelles les prêts sont refusés. Vous pouvez voir la corrélation entre le montant et la période de prêt et les taux de refus. Vous pouvez également recibler les utilisateurs dont le prêt est refusé et leur suggérer de demander un prêt à montant moins élevé.

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
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");eventValue.put("loan_amount", 1000) ;
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),loan_rejected" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"loan_rejected"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @1000,
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("loan_rejected", withValues: [
  "loan_id": "1735102",
  "loan_amount": 1000,
  "loan_type": "3 months"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LoanRejected = new Dictionary<string, string>();
LoanRejected.Add("loan_id", "1735102");
LoanRejected.Add("loan_amount", "1000");
LoanRejected.Add("loan_type", "3 months");
AppsFlyer.sendEvent("loan_rejected", LoanRejected);
```

</Tab>
</Tabs>

</Accordion>

<div id="payment-payment" />

<Accordion title="Paiement (paiement)">

**Objectif**

Vous aide à marquer les emprunteurs comme étant fiables. Les emprunteurs fiables sont ceux qui respectent leur obligation de rembourser leur prêt. Vous pouvez attribuer les emprunteurs à des campagnes et découvrir quelles campagnes génèrent des emprunteurs fiables. Enregistrer cet évènement peut également vous aider à recueillir des données concernant le montant minimal, maximal et moyen des paiements.

**Déclencheur**

Lorsqu'un emprunteur effectue un paiement sur son emprunt

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| loan\_id | ID du prêt | 1735102 |
| payment\_amount | Montant payé | 100 |
| payment\_id | ID de paiement | AE12SF |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("payment_amount", 100);
eventValue.put("payment_id", "AE12SF");
AppsFlyerLib.getInstance().logEvent(
			  getApplicationContext(),
			 "payment" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"payment"
withValues: @{
  @"loan_id": @"1735102",
  @"payment_amount": @100,
  @"payment_id": @"AE12SF"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("payment", 
withValues: [
  "loan_id": "1735102",
  "payment_amount": 100,
  "payment_id": "AE12SF"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> Payment = new Dictionary<string, string>();
Payment.Add("loan_id", "1735102");
Payment.Add("payment_amount", "100");
Payment.Add("payment_id", "AE12SF");
AppsFlyer.sendEvent("payment", Payment);
```

</Tab>
</Tabs>

</Accordion>

<div id="payment-completed-payment_completed" />

<Accordion title="Paiement effectué (payment_completed)">

**Objectif**

Identifier les emprunteurs qui respectent leur obligation de rembourser le prêt. Vous pouvez également recibler ces emprunteurs et leur offrir des taux d'intérêt réduits ou d'autres promotions.

**Déclencheur**

Lorsqu'un prêt est entièrement remboursé

**Paramètres d'événement**

| Nom du champ | Description | Exemple de valeur |
| --- | --- | --- |
| loan\_id | ID du prêt | 1735102 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"payment_completed" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"payment_completed"
withValues: @{
   @"loan_id": @"1735102"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("payment_completed", 
withValues: [
   "loan_id": "1735102"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> PaymentCompleted = new Dictionary<string, string>();
PaymentCompleted.Add("loan_id", "1735102");
AppsFlyer.sendEvent("payment_completed", PaymentCompleted);
```

</Tab>
</Tabs>

</Accordion>

</Accordion>

<div id="payment-received-payment_received" />

<Accordion title="Paiement reçu (payment_received)">

**Objectif**

Vérifier que l'emprunteur effectue le paiement du prêt conformément aux conditions de l'accord de prêt.

**Déclencheur**

Lorsqu'un emprunteur effectue un paiement sur son emprunt

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| loan\_id | ID du prêt | 1735102 |
| payment\_amount | Montant payé | 100 |
| payment\_id | ID de paiement | AE12SF |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("payment_amount", 100);
eventValue.put("payment_id", "AE12SF");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "payment_received" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"payment_received"
withValues: @{
  @"loan_id": @"1735102",
  @"payment_amount": @100,
  @"payment_id": @"AE12SF"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("payment_received", 
withValues: [
  "loan_id": "1735102",
  "payment_amount": 100,
  "payment_id": "AE12SF"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> PaymentReceived = new Dictionary<string, string>();
Payment.Add("loan_id", "1735102");
Payment.Add("payment_amount", "100");
Payment.Add("payment_id", "AE12SF");
AppsFlyer.sendEvent("payment_received", PaymentReceived);
```

</Tab>
</Tabs>

</Accordion>
