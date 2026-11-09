---
title: Évènements d'app de formation en ligne recommandés
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
  created_at: '2021-04-28T12:35:57Z'
  edited_at: '2022-01-25T17:24:20Z'
  id: 360019794378
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/360019794378
---
> **En bref :** mesurez la qualité de vos utilisateurs tout au long de leur parcours en enregistrant ces événements in-app suggérés pour votre app de formation en ligne.

<div id="-online-education" />

## <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="100px" /> Formation en ligne

Les apps de formation en ligne permettent aux utilisateurs d'apprendre à distance. Les événements typiques que nous recommandons d'enregistrer comprennent l'inscription, les tutoriels et les cours suivis, ainsi que les certificats reçus.

L'enregistrement de ces évènements peut vous aider à déterminer :

* Les cours que les utilisateurs souhaitent le plus, et des idées de ciblage
* Quels utilisateurs peuvent être reciblés et contactés pour leur rappeler qu'ils disposent de tutoriels supplémentaires pour terminer un cours
* Quels cours et certificats sont les plus demandés

<div id="important" />

> 🚧 **Important !**
>
> * Veillez à lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#introduction-setting-up-inapp-events">instructions</Anchor> à l'attention des marketeurs pour implémenter les événements in-app.
> * Pour simplifier l'implémentation,  [téléchargez un fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSJsgqgzIInw8NAzY8ILsk2H4Vjp-7dRIc1Ed6vNb34mOayiTjutUs-cOnd4H5u18EvgpspKe7Dx2xb/pub?gid=465330661&single=true&output=csv) contenant tous les événements in-app de base décrits dans cet article,  puis modifiez les événements en fonction des besoins de votre entreprise. Partagez ensuite le fichier avec votre développeur.
> * Pour chaque événement recommandé que contient cet article, vous trouverez des extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour plus d'informations sur l'enregistrement des événements in-app, consultez le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">guide des événements in-app riches</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events_online_education_app_user_journey" src="https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png" />

<div id="recommended-structures-for-predefined-events" />

## Structures recommandées pour les événements prédéfinis

La section suivante fournit une liste des structures d'événements typiques du secteur des formations en ligne. Chaque structure donne un nom d'événement prédéfini, ainsi que des suggestions de paramètres d'événement à appliquer. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

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
Dictionary<string, string> CompleteRegistrationEvent = new Dictionary<string, string>();
CompleteRegistrationEvent.Add("af_registration_method", "Facebook");
AppsFlyer.sendEvent ("af_complete_registration", CompleteRegistrationEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="Tutoriel achevé (af_tutorial_completion)">

**Objectif**

Enregistrer cet événement peut vous permettre de déterminer :

* Les sujets qui peuvent poser problème aux utilisateurs
* Quels tutoriels n'obtiennent pas de bons résultats, afin de les améliorer ?
* Associer l'activité globale de l'utilisateur à des dimensions de type revenus

**Déclencheur**

* Lorsque l'utilisateur achève le tutoriel.
* Lorsque l'utilisateur commence le tutoriel mais le ferme sans l'avoir abouti.

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_success | Si l'utilisateur a terminé le tutoriel ou non | yes |
| af\_tutorial\_id | ID du tutoriel | 3 |
| af\_content | Nom du tutoriel | algebra |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();  
eventValue.put(AFInAppEventParameterName.SUCCESS, yes);  
eventValue.put(AFInAppEventParameterName.TUTORIAL_ID, "3");  
eventValue.put(AFInAppEventParameterName.CONTENT, "algebra");  
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.TUTORIAL_COMPLETION, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventTutorial_completion
withValues: @{
  AFEventParamSuccess: @YES,
  AFEventParamTutorialId: @"3",
  AFEventParamContent: @"algebra"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventTutorial_completion, 
withValues: [
  AFEventParamSuccess: YES,
  AFEventParamTutorialId: "3",
  AFEventParamContent: "algebra"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> TutorialCompletiondEvent = new Dictionary<string, string>();
TutorialCompletiondEvent.Add("af_success", "yes");
TutorialCompletiondEvent.Add("af_tutorial_id", "3");
TutorialCompletiondEvent.Add("af_tutorial_content", "algebra");
AppsFlyer.sendEvent ("af_tutorial_completion", TutorialCompletiondEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Achat (af_purchase)">

**Objectif**

Enregistrer les achats in-app effectués par les utilisateurs, pour vous aider à :

* Déterminer la LTV de vos utilisateurs et le ROI de vos campagnes sur les réseaux publicitaires et les agences de publicité
* Déterminer quelles offres sont les plus populaires auprès de vos utilisateurs
* Réaliser une référence croisée de campagne avec les articles qui ont été achetés afin d'optimiser le ciblage de vos campagnes

**Déclencheur**

Lorsque l'utilisateur atterrit sur la page de remerciement une fois l'achat terminé

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Le revenu estimé provenant de l'achat | 250.99 |
| af\_currency | Code de devise | USD |
| af\_content\_id | ID de l'élément | 001, 092 |
| order\_id | ID de la commande | 9277 |
| af\_receipt\_id | ID du reçu | 9277 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put(AFInAppEventParameterName.REVENUE, 250.99);
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "092");
eventValue.put("order_id", "9277");
eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "9277");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),AFInAppEventType.PURCHASE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventPurchase
withValues: @{
   AFEventParamRevenue: @250.99,
   AFEventParamCurrency: @"USD",
   AFEventParamContentId: @"092",
   @"order_id": @"9277",
   AFEventParamReceiptId: @"9277"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventPurchase, 
withValues: [
   AFEventParamRevenue: 250.99,
   AFEventParamCurrency: "USD",
   AFEventParamContentId: "092",
   "order_id": "9277",
   AFEventParamReceiptId: "9277"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> purchaseEvent = new Dictionary<string, string>();
purchaseEvent.Add("af_revenue", "250.99");
purchaseEvent.Add("af_currency", "USD");
purchaseEvent.Add("af_content_id", "001");
purchaseEvent.Add("order_id", "9277");
purchaseEvent.Add("af_receipt_id", "9277");
AppsFlyer.sendEvent ("af_purchase", purchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Structures recommandées pour les événements personnalisés

La section suivante fournit une liste de structures d'événements qui comprennent des noms d'événements personnalisés et les suggestions de paramètres d'événement à utiliser. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<div id="complete-exercise-complete_excercise" />

<Accordion title="Terminer l'exercice (complete_excercise)">

**Objectif**

Enregistrer cet évènement et le comparer avec d'autres données pour en savoir plus sur vos utilisateurs. Par exemple, vous pouvez savoir combien d'utilisateurs commencent mais ne terminent pas un exercice.

**Déclencheur**

Lorsque l'utilisateur termine un exercice

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| course\_name | Nom du cours | algebra |
| exercise\_name | Nom de l'exercice | 2 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
              eventValue.put("course_name", "algebra");
              eventValue.put("exercise_name", "2");
              AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "complete_exercise", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"complete_exercise"
withValues: @{ 
  @"course_name": @"algebra",  
 @"exercise_name": @"2"  
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("complete_exercise",withValues: 
["course_name": "algebra","exercise_name": "2" ])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CompleteExerciseEvent = new Dictionary<string, string>();
CompleteExerciseEvent.Add("course_name", "algebra");  
CompleteExerciseEvent.Add("exercise_name", "2");
AppsFlyer.sendEvent ("complete_exercise", CompleteExerciseEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="course-completed-course_completed" />

<Accordion title="Cours terminé (course_completed)">

**Objectif**

Enregistrer cet évènement et le comparer avec d'autres données pour en savoir plus sur vos utilisateurs. Par exemple, vous pouvez savoir combien d'utilisateurs commencent mais ne terminent pas un exercice.

**Déclencheur**

Lorsque l'utilisateur termine un exercice

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| course\_name | Nom du cours | algebra |
| course\_completed | Si le cours a été achevé | yes |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("course_name", "algebra");
eventValue.put("course_completed", "yes");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "course_completed", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[AppsFlyerLib shared] logEvent:@"course_completed" withValues:@{ 
@"course_name": @"algebra", 
@"course_completed": @"yes"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("course_completed", withValues: 
[ "course_name": "algebra",
"course_completed": "yes"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CourseCompletedEvent = new Dictionary<string, string>();
CourseCompletedEvent.Add("course_name", "algebra");  
CourseCompletedEvent.Add("course_completed", "yes");
AppsFlyer.sendEvent ("course_completed", CourseCompletedEvent);
```

</Tab>
</Tabs>

</Accordion>

<div id="certificate-issued-certificate_issued" />

<Accordion title="Certificat émis (certificate_issued)">

**Objectif**

Enregistrer cet évènement et le comparer avec d'autres données pour en savoir plus sur vos utilisateurs. Par exemple, vous pouvez savoir combien d'utilisateurs terminent un cours, puis les recibler pour le cours suivant.

**Déclencheur**

Lorsque l'utilisateur reçoit un certificat

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| course\_name | Nom du cours | algebra |
| certificate\_received | Si le certificat a été délivré ou non | yes |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("course_name", "algebra");
eventValue.put("certificate_received", "yes");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "certificate issued", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"course_completed" withValues: @{ 
@"course_name": @"algebra", 
@"certificate_received": @"yes"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("certificate issued", withValues: 
[ "course_name": "algebra",
"certificate_received": "yes"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CertificateIssuedEvent = new Dictionary<string, string>();
CertificateIssuedEvent.Add("course_name", "algebra");  
CertificateIssuedEvent.Add("certificate_received", "yes");
AppsFlyer.sendEvent ("certificate issued", CertificateIssuedEvent);
```

</Tab>
</Tabs>

</Accordion>
