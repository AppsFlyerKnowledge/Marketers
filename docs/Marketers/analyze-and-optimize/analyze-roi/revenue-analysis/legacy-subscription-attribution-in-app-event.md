---
title: "[Legacy] Subscription attribution—In-app event"
excerpt: "Learn how to configure and send subscription-related in-app events to record subscriptions and renewals using the AppsFlyer SDK."
---
Configure and send a subscription-related in-app event to record subscriptions and subscription renewals. 

> 📘 Note
>
> This is a legacy feature. Learn more about the new, fully automatic, and improved subscription revenue mechanism.

## In-app subscription event

Apps often need to check subscription status in order to enable subscription-specific features. You can use this mechanism in order to send subscription-related events to AppsFlyer. Once the app is aware of a subscription purchase or renewal, it can send the event.

> 🚧 Warning
>
> If a user subscribes but doesn't launch the app for more than a month, the subscription is not counted as an event. For example, a user subscribes through your website but then doesn't open the app. If the user doesn't open the app for more than a month after subscribing, the subscription is not counted.

### Checking subscription status in the app

The app can either communicate with your servers or receive push notifications with data about subscriptions.

You can configure your app to check the status of the subscription. There are two ways you can achieve this:

1. The app checks the subscription status and related data (active or not active, subscription type, expiration date, etc.)
2. The app receives a push notification about a subscription purchase or renewal.

> 👍 Tip
>
> **For Android applications**: You can use [Android's real-time developer notifications](https://developer.android.com/google/play/billing/realtime_developer_notifications) to notify the app about renewals in real-time.
>
> **For iOS applications**: The Store kit provides you with [payment queue and transaction observers](https://developer.apple.com/documentation/storekit/skpaymentqueue?changes=_3&language=objc). You can use these to verify a subscription purchase or renewal. Refer to Apple's documentation on [finalizing transactions](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/StoreKitGuide/Chapters/DeliverProduct.html#//apple_ref/doc/uid/TP40008267-CH5-SW10) for more information.

> 📘 Note
>
> Receipt validation is not supported for recording subscriptions.

### Sending a subscription-related in-app event

Once the app has the relevant subscription-related data, the following steps should take place:

1. The app checks to see if the subscription is a purchase or renewal.
2. The app gathers the relevant data (revenue, content_id, purchase or renewal, etc.).
3. The app sends the subscription event to AppsFlyer using the SDK.

### Subscription event example

| Parameter Name | Type | Example of Value | Description |
| --- | --- | --- | --- |
| af_revenue | float | 200 | The revenue associated with the subscription |
| af_currency | string | USD, GBP | The currency of the payment |
| af_content_id | string | 092, monthly_subscription | The name or code of the subscription |
| renewal | boolean | true, false | whether the subscription is new or renewed |

### Event code samples

The code snippet below demonstrates how to configure and send the event using the SDK.

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REVENUE, 200);
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "092");
eventValue.put("renewal", true);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.SUBSCRIBE, eventValue);
```

</Tab>
<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:(AFEventSubscribe) withValues: @{
  AFEventParamRevenue: @200,
  AFEventParamCurrency: @"USD",
  AFEventParamContentId: @"092",
  @"renewal": @TRUE
}];
```

</Tab>
<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventSubscribe, withValues: [
  AFEventParamRevenue: 200,
  AFEventParamCurrency: "USD",
  AFEventParamContentId: "092",
  "renewal": true
]);
```

</Tab>
<Tab title="Unity">

```csharp
Dictionary<string, string> SubscriptionEvent = new Dictionary<string, string>();
SubscriptionEvent.Add("af_revenue", "200");
SubscriptionEvent.Add("af_currency", "USD");
SubscriptionEvent.Add("af_content_id", "092");
SubscriptionEvent.Add("renewal", "true");
AppsFlyer.sendEvent("af_subscribe", SubscriptionEvent);
```

</Tab>
</Tabs>

> 📘 Note
>
> It is highly recommended that you associate subscriptions with customers. To do so, make sure to set the [customer user ID](/docs/customer-user-id-field-cuid). Setting the customer user ID is your way to match your customers with users of your app as they appear in AppsFlyer. By setting the customer user ID you make sure that any event, subscription-related events included, is sent with the customer user ID.