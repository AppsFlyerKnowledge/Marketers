---
title: Événements recommandés pour les apps de divertissement
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
  created_at: '2021-04-25T10:44:33Z'
  edited_at: '2022-01-25T17:24:24Z'
  id: 360019699898
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/360019699898
---
> **En bref :** mesurez la qualité de vos utilisateurs tout au long de leur parcours en enregistrant ces événements in-app suggérés pour votre app de divertissement .

<div id="-entertainment" />

## <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="100px" /> Divertissement

En raison de la demande croissante de contenu à la demande de la part des utilisateurs, le marché des apps de divertissement est devenu très compétitif. Les événements typiques que nous suggérons d'enregistrer sont les abonnements des utilisateurs, la diffusion de contenu en streaming, ainsi que le téléchargement et l'enregistrement de contenu.

L'enregistrement de ces évènements peut vous aider à déterminer :

* Quels contenus les utilisateurs consomment
* Performance des campagnes (en fonction de la demande des utilisateurs)
* Engagement des utilisateurs et utilisation faite

Ces événements sont également pertinents pour les apps de divertissement qui fonctionnent sur les téléviseurs intelligents suivants :

* Android Smart TV
* Apple TV (tvOS)
* Amazon Fire TV

<div id="important" />

> 🚧 **Important !**
>
> * Veillez à lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#introduction-setting-up-inapp-events">instructions</Anchor> à l'attention des marketeurs pour implémenter les événements in-app.
> * Pour simplifier l'implémentation,  [téléchargez un fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vSJsgqgzIInw8NAzY8ILsk2H4Vjp-7dRIc1Ed6vNb34mOayiTjutUs-cOnd4H5u18EvgpspKe7Dx2xb/pub?gid=0&single=true&output=csv) contenant tous les événements in-app de base décrits dans cet article,  puis modifiez les événements en fonction des besoins de votre entreprise. Partagez ensuite le fichier avec votre développeur.
> * Pour chaque événement recommandé que contient cet article, vous trouverez des extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour plus d'informations sur l'enregistrement des événements in-app, consultez le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">guide des événements in-app riches</Anchor>.

[![Flowchart_for_recommended_events entertainment_app_user_journey](https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png)](https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png)

<div id="recommended-structures-for-predefined-events" />

## Structures recommandées pour les événements prédéfinis

La section suivante fournit une liste des structures d'événements typiques du secteur du divertissement. Chaque structure donne un nom d'événement prédéfini, ainsi que des suggestions de paramètres d'événement à appliquer. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Inscription terminée (af_complete_registration)">

**Objectif**

Découvrir combien d'utilisateurs ont installé l'app et sont allés au bout du processus d'inscription, et quelles méthodes d'inscription vos utilisateurs privilégient.

**Déclencheur**

Lorsque l'utilisateur termine le processus d'inscription

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_registration\_method | La méthode que choisit l'utilisateur pour s'inscrire | Facebook, Google, email |

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

Comprendre la rétention de vos utilisateurs inscrits

**Déclencheur**

Lorsque l'utilisateur se connecte avec succès

**Paramètres d'événement**

Peut être envoyé sans paramètres supplémentaires

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

<div id="start-trial-af_start_trial" />

<Accordion title="Début de l'essai (af_start_trial)">

**Objectif**

De nombreux services de streaming proposent aux utilisateurs une période d'essai leur permettant de découvrir les fonctionnalités premium. Cet évènement peut vous aider à :

* Voir combien d'utilisateurs s'inscrivent à une période d'essai
* Si l'essai fait partie d'une promotion ou d'une collaboration avec un partenaire
* Quelle promotion a incité l'utilisateur à activer la période d'essai

**Déclencheur**

Lorsque l'utilisateur s'inscrit et active la période d'essai

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| trial\_method | Méthode pour activer l'essai | Offert avec un nouveau téléphone, offert avec un opérateur, promotion, code promo |
| trial\_method\_identifier | Identifiant de la méthode d'essai | Nom de l'opérateur (ex : **Vodafone**)<br /><br />Nom du partenaire (ex : **Facebook**)<br /><br />Code promotionnel (ex : **TRA123)** |

<div id="note" />

> 📘 **Remarque**
>
> Si vous mappez cet événement à l'événement Facebook StartTrial et que vous souhaitez associer les revenus, utilisez le paramètre af\_price au lieu du paramètre af\_revenue.

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("trial_method", "coupon code");
eventValue.put("trial_method_identifier", "TRA123");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.START_TRIAL, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventStartTrial
withValues: @{
  @"trial_method": @"coupon code",
  @"trial_method_identifier": @"TRA123"
  }]
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventStartTrial,
withValues: [
  "trial_method": "coupon code",
  "trial_method_identifier": "TRA123"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubscriptionTrial = new Dictionary<string, string>();
SubscriptionTrial.Add("trial_method ", "coupon code");
SubscriptionTrial.Add("trial_method_identifier", "TRA123");
AppsFlyer.sendEvent("af_start_trial", SubscriptionTrial);
```

</Tab>
</Tabs>

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="Abonnement (af_subscribe)">

**Objectif**

L'abonnement constitue le cœur des services de streaming. Cet évènement peut vous aider à :

* Voir quelles campagnes produisent des utilisateurs qui s'inscrivent
* Comparer le nombre d'utilisateurs en période d'essai et le nombre d'utilisateurs abonnés
* Déterminer les revenus générés par les abonnements et les attribuer aux campagnes et aux sources média

**Déclencheur**

* Lorsque l'utilisateur s'inscrit avec succès
* Lorsqu'un abonnement est renouvelé

Reportez-vous à notre Guide de suivi des abonnements pour en savoir plus.

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| new\_subscription | Qu'il s'agisse d'un nouvel abonnement ou d'un renouvellement | true / false |
| af\_coupon\_code | Le code promotionnel, s'il est utilisé lors de la soumission de l'abonnement | 3MonthsSubscription |
| coupon\_code\_value | Le montant déduit du prix initial grâce au code de réduction | 10% |
| <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Le revenu associé à l'abonnement | 5.95 |
| af\_currency | La devise du paiement pour l'abonnement | USD |
| subscription\_method | La méthode de paiement utilisée pour l'abonnement | carte de crédit, portefeuille électronique, PayPal |
| expiration\_date | La date d'expiration de l'abonnement | 2018/07/18 |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("new_subscription", true);
eventValue.put(AFInAppEventParameterName.COUPON_CODE, "3MonthsSubscription");
eventValue.put("coupon_code_value", "10%");
eventValue.put(AFInAppEventParameterName.REVENUE, 5.95);
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
eventValue.put("subscription_method", "");
eventValue.put("expiration_date", "2018/07/18");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.SUBSCRIBE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventSubscribe
withValues: @{
 @"new_subscription": @TRUE,
 AFEventParamCouponCode: @"3MonthsSubscription",
 @"coupon_code_value": @"10%",
 AFEventParamRevenue: @5.95,
 AFEventParamCurrency: @"USD",
 @"subscription_method": @"",
 @"expiration_date": @"2018/07/18"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventSubscribe, 
withValues: [
 "new_subscription": true,
 AFEventParamCouponCode: "3MonthsSubscription",
 "coupon_code_value": "10%",
 AFEventParamRevenue: 5.95,
 AFEventParamCurrency: "USD",
 "subscription_method": "",
 "expiration_date": "2018/07/18"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> Subscription = new Dictionary<string, string>();
Subscription.Add("new_subscription", "true");
Subscription.Add("af_coupon_code", "3MonthsSubscription");
Subscription.Add("coupon_code_value", "10%");
Subscription.Add("af_revenue", "5.95");
Subscription.Add("af_currency", "USD");
Subscription.Add("subscription_method", "");
Subscription.Add("expiration_date", "2018/07/18");
AppsFlyer.sendEvent("af_subscribe", Subscription);
```

</Tab>
</Tabs>

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Structures recommandées pour les événements personnalisés

La section suivante fournit une liste de structures d'événements qui comprennent des noms d'événements personnalisés et les suggestions de paramètres d'événement à utiliser. Veuillez noter que les événements in-app peuvent inclure tous les paramètres d'événement qui correspondent à vos besoins.

<div id="media-play-media_play" />

<Accordion title="Lecture média (media_play)">

**Objectif**

Enregistrer les événements dans lesquels les utilisateurs lisent les médias que vous proposez. Ces médias peuvent être des vidéos, de la musique, des séries TV, des émissions de radio, etc.

Enregistrer cet événement peut vous permettre de déterminer :

* Consommation de médias par type et contenu
* Les langues des contenus en streaming les plus populaires
* La durée minimum, maximum et moyenne des contenus en streaming

**Déclencheur**

Après un temps prédéfini de lecture en streaming d'un contenu, 2 minutes par exemple.

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_content\_type | Type de contenu regardé en streaming | série TV, musique |
| af\_content\_id | ID du contenu regardé en streaming | 092, E34 |
| af\_content | Le titre du contenu, par ex. le nom de la chanson ou le titre et l'épisode d'une série TV | Titre du contenu |
| media\_duration | Temps de lecture | 5 |
| language | Langue du contenu | en-us, fr, es |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "tv show");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "E34");
eventValue.put(AFInAppEventParameterName.CONTENT, "My Show");
eventValue.put("media_duration", 5);
eventValue.put("language", "en-us");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "media_play", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"media_play"
withValues: @{
	AFEventParamContentType: @"tv show",
	AFEventParamContentId: @"E34",
	AFEventParamContent: @"My Show",
	@"duration": @5,
	@"langague": @"en-us"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("media_play", 
withValues: [
AFEventParamContentType: "tv show",
AFEventParamContentId: "E34",
AFEventParamContent: "My Show",
"media_duration": 5,
"language": "en-us"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> MediaPlay = new Dictionary<string, string>();
MediaPlay.Add("af_content_type", "tv show");
MediaPlay.Add("af_content_id", "E34");
MediaPlay.Add("af_content", "My show");
MediaPlay.Add("media_duration", "5");
MediaPlay.Add("language", "en-us");
AppsFlyer.sendEvent("media_play", MediaPlay);
```

</Tab>
</Tabs>

</Accordion>

<div id="media-minutes-media_minutes" />

<Accordion title="Minutes de média (media_minutes)">

**Objectif**

Les minutes de média représentent la durée pendant laquelle un utilisateur a consommé un certain contenu. Après l'indicateur de revenu, il s'agit de la métrique la plus importante du secteur du streaming. Cet indicateur est important car il vous permet d'estimer l'utilisation du service par les utilisateurs. Il vous permet également de déterminer le taux d'utilisation global du service et le contenu le plus populaire. Cet évènement peut vous aider à :

* Découvrez quels utilisateurs utilisent le plus votre service
* Déterminer quels types de média et de contenu sont populaires

**Déclencheur**

L'une des opérations suivantes :

* Voir lorsqu'un utilisateur termine le streaming d'un élément de média
* Voir lorsqu'un utilisateur quitte le streaming d'un élément de média

**Paramètres d'événement**

| Nom | Description | Exemple  de valeur |
| --- | --- | --- |
| minutes\_consumed | Temps réel d'exécution du média par l'utilisateur | 3 |
| af\_content\_type | Type de contenu regardé en streaming | série TV, musique |
| af\_content\_id | ID du contenu regardé en streaming | 092, E34 |
| af\_content | Titre du contenu, par ex. le nom de la chanson, le titre et l'épisode d'une série | Titre du contenu |
| media\_duration | Temps de lecture | 5 |
| language | Langue du contenu | en-us, fr, es |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "tv show");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "E34");
eventValue.put(AFInAppEventParameterName.CONTENT, "My Show");
eventValue.put("media_duration", 5);
eventValue.put("language", "en-us");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"media_minutes", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"media_minutes"
withValues: @{
 @"minutes_consumed": @3,
 AFEventParamContentType: @"tv show",
 AFEventParamContentId: @"E34",
 AFEventParamContent: @"My Show",
 @"duration": @5,
 @"langague": @"en-us"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("media_minutes", withValues: [
 "minutes_consumed": 3,
 AFEventParamContentType: "tv show",
 AFEventParamContentId: "E34",
 AFEventParamContent: "My Show",
 "media_duration": 5,
 "language": "en-us"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> MediaMinutes = 
		 new Dictionary<string, string>();
MediaMinutes.Add("minutes_consumed", "3");
MediaMinutes.Add("af_content_type", "tv show");
MediaMinutes.Add("af_content_id", "E34");
MediaMinutes.Add("af_content", "My show");
MediaMinutes.Add("media_duration", "5");
MediaMinutes.Add("language", "en-us");
AppsFlyer.sendEvent("media_minutes", MediaMinutes);
```

</Tab>
</Tabs>

</Accordion>

<div id="media-downloaded-media_downloaded" />

<Accordion title="Média téléchargé (media_downloaded)">

**Objectif**

Déterminer les préférences des utilisateurs en enregistrant la lecture et le téléchargement des médias et en comparant les deux. Vous pouvez découvrir ce que les utilisateurs de médias préfèrent lire en streaming et les médias qu'ils préfèrent télécharger.

**Déclencheur**

Quand un utilisateur commence à télécharger un média

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_content\_type | Type de contenu | série TV, musique |
| af\_content\_id | ID de contenu | 092, E34 |
| af\_content | Titre du contenu, par ex. le nom de la chanson ou le titre et l'épisode d'une série TV | Titre du contenu |
| media\_duration | Temps de lecture | 5 |
| language | Langue du contenu | en-us, fr, es |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "tv show");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "E34");
eventValue.put(AFInAppEventParameterName.CONTENT, "My Show");
eventValue.put("media_duration", 5);
eventValue.put("language", "en-us");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "media_downloaded", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"media_downloaded"
withValues: @{
	@"minutes_consumed": @3,
	AFEventParamContentType: @"tv show",
	AFEventParamContentId: @"E34",
	AFEventParamContent: @"My Show",
	@"duration": @5,
	@"langague": @"en-us"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("media_downloaded", 
withValues: [
	"minutes_consumed": 3,
	AFEventParamContentType: "tv show",
	AFEventParamContentId: "E34",
	AFEventParamContent: "My Show",
	"media_duration": 5,
	"language": "en-us"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> MediaDownloaded = new Dictionary<string, string>();
MediaDownloaded.Add("minutes_consumed", "3");
MediaDownloaded.Add("af_content_type", "tv show");
MediaDownloaded.Add("af_content_id", "E34");
MediaDownloaded.Add("af_content", "My show");
MediaDownloaded.Add("media_duration", "5");
MediaDownloaded.Add("language", "en-us");
AppsFlyer.sendEvent("media_downloaded", MediaDownloaded);
```

</Tab>
</Tabs>

</Accordion>

<div id="media-saved-media_saved" />

<Accordion title="Media enregistré (media_saved)">

**Objectif**

Mettre en évidence les préférences des utilisateurs

**Déclencheur**

Chaque fois qu'un média est enregistré sur l'appareil de l'utilisateur

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_content\_type | Type de contenu | série TV, musique |
| af\_content\_id | ID de contenu | 092, E34 |
| af\_content | Titre du contenu, par ex. le nom de la chanson, le titre et l'épisode d'une série | Titre du contenu |
| media\_duration | Temps de lecture | 5 |
| language | Langue du contenu | en-us, fr, es |

**Exemples de code**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "tv show");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "E34");
eventValue.put(AFInAppEventParameterName.CONTENT, "My Show");
eventValue.put("media_duration", 5);
eventValue.put("language", "en-us");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "media_saved", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"media_saved"
withValues: @{
	@"minutes_consumed": @3,
	 AFEventParamContentType: @"tv show",
	 AFEventParamContentId: @"E34",
	 AFEventParamContent: @"My Show",
	 @"duration": @5,
	 @"langague": @"en-us"  
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("media_saved", 
withValues: [  
 "minutes_consumed": 3,
	 AFEventParamContentType: "tv show",
	 AFEventParamContentId: "E34",
	 AFEventParamContent: "My Show",
	 "media_duration": 5,
	 "language": "en-us"]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> MediaSaved = new Dictionary<string, string>();
MediaSaved.Add("minutes_consumed", "3");
MediaSaved.Add("af_content_type", "tv show");
MediaSaved.Add("af_content_id", "E34");
MediaSaved.Add("af_content", "My show");
MediaSaved.Add("media_duration", "5");
MediaSaed.Add("language", "en-us");
AppsFlyer.sendEvent("media_saved", MediaSaved);
```

</Tab>
</Tabs>

</Accordion>
