---
title: Événements recommandés pour les apps de gaming
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2021-04-06T14:46:54Z'
  edited_at: '2022-01-25T17:22:19Z'
  id: 360018941117
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/360018941117
---
> **En bref :** mesurez la qualité de vos utilisateurs tout au long de leur parcours en enregistrant ces événements in-app que nous recommandons pour votre app de gaming.

## <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="100px" />Gaming

Les apps de gaming comprennent les jeux d'arcade, de stratégie, éducatifs et les jeux d'argent. Les principaux événements que nous vous recommandons d'enregistrer sont les achats in-app, le partage sur les réseaux sociaux et les invitations d'amis. Vous pouvez aussi y inclure les événements de type «passage au niveau supérieur» et «tutoriel du jeu complété»

L'enregistrement de ces évènements peut vous aider à déterminer :

* Les offres que les utilisateurs achètent le plus
* Ce qui attire les utilisateurs
* Le nombre d'utilisateurs qui partagent des posts sur les réseaux sociaux
* Le nombre d'utilisateurs qui invitent leurs amis à installer l'app

Ces événements sont également utiles pour les apps de gaming qui tournent sur les plateformes suivantes :

* Android Smart TV
* Apple TV (tvOS)
* Amazon Fire TV
* Xbox
* Appareils mobiles Windows

> 🚧 **Important !**
>
> * Veillez à lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#introduction-setting-up-inapp-events">instructions</Anchor> à l'attention des marketeurs pour implémenter les événements in-app.
> * Pour simplifier l'implémentation, [téléchargez un fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSJsgqgzIInw8NAzY8ILsk2H4Vjp-7dRIc1Ed6vNb34mOayiTjutUs-cOnd4H5u18EvgpspKe7Dx2xb/pub?gid=1420540349&single=true&output=csv) contenant tous les événements in-app de base décrits dans cet article, puis modifiez les événements en fonction des besoins de votre entreprise. Une fois terminé, partagez le fichier avec votre développeur.
> * Pour chaque événement recommandé que contient cet article, vous trouverez des extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour plus d'informations sur l'enregistrement des événements in-app, consultez le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">guide des événements in-app riches</Anchor>.

[![Flowchart_for_recommended_events gaming_app_user_journey](https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png)](https://files.readme.io/18546b2ca811e534d7b15527d3dadb4750edd8e985154543fa156216ad023f78-360020169778.png)

## Structures recommandées pour les événements prédéfinis

La section suivante propose une liste des structures d'événement qui sont le plus souvent utilisées dans le secteur du gaming. Chaque structure donne un nom d'événement prédéfini, ainsi que des suggestions de paramètres d'événement à appliquer. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

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

<Accordion title="Achat (af_purchase)">

**Objectif**

De nombreuses apps de gaming permettent aux utilisateurs d'acheter certains articles comme des pièces, des pierres précieuses ou des armes. Enregistrer ces achats peut vous permettre de :

* Déterminer la LTV de vos utilisateurs et le ROI de vos campagnes sur les réseaux publicitaires et les agences de publicité
* Déterminer quelles offres sont les plus populaires auprès de vos utilisateurs
* Réaliser une référence croisée de campagne avec les articles qui ont été achetés afin d'optimiser le ciblage de vos campagnes

**Déclencheur**

Lorsque l'utilisateur atterrit sur la page de remerciement une fois l'achat terminé

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Le revenu estimé provenant de l'achat | 199.99 |
| af\_currency | Code de devise | THB, USD |
| af\_quantity | Nombre d'articles achetés | 2 |
| af\_content\_id | ID de l'article | 001, 092 |
| af\_order\_id | ID de la commande | 9277 |
| af\_receipt\_id | ID du reçu | 9277 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REVENUE, "199.99");
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
eventValue.put(AFInAppEventParameterName.QUANTITY, "2");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "092");
eventValue.put(AFInAppEventParameterName.ORDER_ID, "9277");
eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "9277");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),AFInAppEventType.PURCHASE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventPurchase
withValues: @{
   AFEventParamRevenue: @199.99, AFEventParamCurrency: @"USD", AFEventParamQuantity: @2, AFEventParamContentId: @"092", AFEventParamOrderId: @"9277", AFEventParamReceiptId: @"9277" }];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventPurchase, 
withValues: [
   AFEventParamRevenue: 199.99, AFEventParamCurrency: "THB", AFEventParamQuantity: 2, AFEventParamContentId: "092", AFEventParamOrderId: "9277", AFEventParamReceiptId: "9277" ]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> purchaseEvent = new Dictionary<string, string>();
purchaseEvent.Add("af_revenue", "199.99"); purchaseEvent.Add("af_currency", "USD"); purchaseEvent.Add("af_quantity", "2"); purchaseEvent.Add("af_content_id", "001"); purchaseEvent.Add("af_order_id", "9277"); purchaseEvent.Add("af_receipt_id", "9277"); AppsFlyer.sendEvent ("af_purchase", purchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Niveau atteint (af_level_achieved)">

**Objectif**

L'un des principaux objectifs d'un utilisateur de jeu, c'est de passer au niveau supérieur. Passer au niveau supérieur débloque souvent de nouvelles fonctionnalités et de nouvelles zones, ce qui incite le joueur à continuer. Enregistrer le niveau de succès peut vous aider à :

* Déterminer les campagnes qui génèrent le plus d'utilisateurs actifs
* Découvrir quels types d'utilisateurs sont les plus actifs et les plus investis
* Associer l'activité globale de l'utilisateur à des dimensions de type revenus

**Déclencheur**

Lorsque l'utilisateur atterrit sur la page qui indique qu'un niveau a été atteint

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_level | Le niveau atteint par l'utilisateur | 3 |
| af\_score | Score associé au succès de l'utilisateur | 500 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.LEVEL, 10);
eventValue.put(AFInAppEventParameterName.SCORE, 500);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.LEVEL_ACHIEVED, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventLevelAchieved
withValues: @{
  AFEventParamLevel: @10,
  AFEventParamScore: @500
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventLevelAchieved,
withValues: [
  AFEventParamLevel: 3,
  AFEventParamScore: 500
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LevelAchievedEvent = new Dictionary<string, string>();
LevelAchievedEvent.Add("af_level", "10");
LevelAchievedEvent.Add("af_score", "500");
AppsFlyer.sendEvent ("af_level_achieved", LevelAchievedEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Tutoriel achevé (af_tutorial_completion)">

**Objectif**

Les tutoriels apprennent aux utilisateurs comment faire fonctionner l'application. Enregistrer cet événement peut vous permettre de déterminer :

* Les sujets qui peuvent poser problème aux utilisateurs
* Quels tutoriels ne sont pas très effectifs

**Déclencheur**

* Lorsque l'utilisateur achève le tutoriel.
* Lorsque l'utilisateur commence le tutoriel mais le ferme sans l'avoir abouti.

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_success | Si l'utilisateur a terminé le tutoriel ou non | true |
| af\_tutorial\_id | ID de tutoriel | 3 |
| af\_content | Nom du tutoriel | Mise en route |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.SUCCESS, true);
eventValue.put(AFInAppEventParameterName.TUTORIAL_ID, "3");
eventValue.put(AFInAppEventParameterName.CONTENT, "Getting Started");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.TUTORIAL_COMPLETION, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventTutorial_completion
withValues: @{
  AFEventParamSuccess: @TRUE,
  AFEventParamTutorialId: @"3",
  AFEventParamContent: @"Getting Started"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventTutorial_completion, 
withValues: [
  AFEventParamSuccess: true,
  AFEventParamTutorialId: "3",
  AFEventParamContent: "Getting started"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> TutorialCompletiondEvent = new Dictionary<string, string>();
TutorialCompletiondEvent.Add("af_success", "true");
TutorialCompletiondEvent.Add("af_tutorial_id", "3");
TutorialCompletiondEvent.Add("af_tutorial_content", "Getting started");
AppsFlyer.sendEvent ("af_tutorial_completion", TutorialCompletiondEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Partage (af_share)">

**Objectif**

Les joueurs aiment partager leurs succès sur les sites de réseaux sociaux. Le partage alimente la notoriété de la marque et peut donner envie à d'autres utilisateurs de télécharger et installer votre app. Enregistrer cet événement peut vous permettre de comprendre dans quel contexte les utilisateurs sont le plus à même de partager une app avec leurs amis. En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/user-invite-attribution">l'enregistrement des partages et invitations</Anchor>.

**Déclencheur**

Lorsqu'un utilisateur partage un post sur les réseaux sociaux

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_description | Motif du partage sur les réseaux sociaux, comme un nouveau record, ou un nouveau niveau atteint | Nouveau record, nouveau niveau, jeu terminé |
| platform | Plateforme utilisée pour publier les posts | Facebook, Whatsapp, e-mail |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.DESCRIPTION, "New High Score");
eventValue.put("platform", "Facebook");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.SHARE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventShare
withValues: @{
  AFEventParamDescription: @"New High Score",
  @"platform": @"Facebook"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventShare, 
withValues: [
  AFEventParamDescription: "New High Score",
  "platform": "Facebook"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ShareEvent = new Dictionary<string, string>();
ShareEvent.Add("af_description", "New High Score");
ShareEvent.Add("platform", "Facebook");
AppsFlyer.sendEvent ("af_share", ShareEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Invitation (af_invite)">

**Objectif**

Découvrez sur quels sites de réseaux sociaux les utilisateurs envoient leurs invitations, et combien invitent leurs amis à télécharger puis installer l'app.

**Déclencheur**

Lorsque l'utilisateur invite un ami à télécharger et installer l'application

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_description | Contenu de l'invitation | Essayez cette app |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.DESCRIPTION, "Try this app");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.INVITE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventInvite
withValues: @{
  AFEventParamDescription: @"Try this app"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventInvite, withValues: [
  AFEventParamDescription: "Try this app"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> InviteEvent = new Dictionary<string, string>();
InviteEvent.Add("af_description", "Try this app");
AppsFlyer.sendEvent ("af_invite", InviteEvent);
```

</Tab>
</Tabs>

</Accordion>

## Structures recommandées pour les événements personnalisés

La section suivante fournit une structure d'événement qui comprend un nom d'événement personnalisé et les suggestions de paramètres d'événement à utiliser. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<Accordion title="Bonus réclamé (bonus_claimed)">

**Objectif**

Découvrir combien d'utilisateurs ont réclamé les bonus qui leur sont offerts, puis comparer les bonus réclamés avec l'activité et l'engagement des utilisateurs.

**Déclencheur**

Lorsque l'utilisateur a réclamé un bonus et qu'il est mis à jour sur son compte

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| bonus\_type | Le type de bonus que l'utilisateur a réclamé | Pièces |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("bonus_type", "coins");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "bonus_claimed", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"bonus_claimed"
withValues: @{
  @"bonus_type": @"coins"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("bonus_claimed", withValues: [
  "bonus_type": "coins"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> BonusClaimedEvent = new Dictionary<string, string>();
BonusClaimedEvent.Add("bonus_type", "coins");
AppsFlyer.sendEvent ("bonus_type", BonusClaimedEvent);
```

</Tab>
</Tabs>

</Accordion>
