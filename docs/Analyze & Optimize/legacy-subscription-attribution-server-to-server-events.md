---
title: "[Legacy] Subscription attribution—Server-to-server events"
excerpt: "Implement server-to-server events to record subscriptions and send subscription events to AppsFlyer."
---
> 📘 Legacy Feature
>
> This is a legacy feature. Learn more about the new, fully automatic, and improved [subscription revenue mechanism](https://support.appsflyer.com/hc/articles/4621716453009).

To implement server-to-server events, you need to design backend logic. The backend logic keeps track of subscriptions (new and renewed) and sends subscription events to AppsFlyer as necessary.

## Sending server-to-server events to AppsFlyer for subscription notifications

AppsFlyer by default doesn't receive notifications of renewal or subscription events from the app stores. This section discusses how to set up a connection to the respective app store and pass subscription information to AppsFlyer as a server-to-server event.

<Tabs>
<Tab title="Android">

Managing subscriptions on Android can be done on the App and Server levels. On the App level, communication is done through Google Play Billing Library. On the Server level while it is done through Google Play Developer API. The recommended way for managing subscriptions is through Google Play Developer API. This is the way that is discussed in this article.

#### Step 1: Set up the server endpoint to receive subscription-related notifications

Create a server endpoint that receives subscription-related notifications from Google Cloud. Then, enable real-time developer notifications:

1. Determine a URL endpoint on your server to use for subscription status updates. For example, https://myserver/subscription-notifications.
2. Set up [Cloud Pub/Sub](https://cloud.google.com/pubsub/) in your Google Cloud Platform (GCP) project.
3. [Enable real-time developer notifications](https://developer.android.com/google/play/billing/realtime_developer_notifications#overview) for your Android app.

#### Step 2: Handle real-time subscription notifications

Once you set up a server endpoint to receive notifications, write the logic to handle these notifications. By default, Google sends notifications through Pub/Sub with `subscriptionId` and `purchaseToken`. The notification message doesn't contain any relevant information about the actual subscription. You need to take the purchase token and send a request to the [Google Play Developer API to purchases.subscriptions](https://developers.google.com/android-publisher/api-ref/purchases/subscriptions/get).

The subscription notification contains the following:

```json
{
	"version": string,
	"packageName": string,
	"eventTimeMillis": 1578509686,
	"subscriptionNotification": SubscriptionNotification,
	"testNotification": AppsFlyerTest
}
```

In the subscription notification, there's an object called `SubscriptionNotification`. It contains the following.

```json
{
	"version": 1.0,
	"notificationType": 4,
	"purchaseToken": "0f43308f-bf3f-4fa1-8aef-d515c941334b",
	"subscriptionId": 123456789
}
```

`purchaseToken` is the token that you send to [Google Play Developer API to purchases.subscriptions](https://developers.google.com/android-publisher/api-ref/purchases/subscriptions/get) get data about the subscription.

The `subscriptionId` is the value you store into your database and associate it with the AppsFlyer ID.

#### Step 3: Associate subscription with Appsflyer ID and GAID in your database

Once you get the data about the subscription, you need to set up a link between the subscription ID and the AppsFlyer ID and GAID. The AppsFlyer ID is mandatory for sending server-to-server events to AppsFlyer. We strongly recommend including the GAID  when sending a server-to-server event. Including it allows AppsFlyer to send event postbacks to SRNs (self-reporting networks). It also opens for you the option to [use AppsFlyer Audiences](https://support.appsflyer.com/hc/articles/115002689186). You can get the AppsFlyer ID and GAID in one of the following ways:

- [SDK](https://support.appsflyer.com/hc/articles/207032066#unique-identifier-for-installs)
- [Raw data](https://support.appsflyer.com/hc/articles/208387843)
- [Push API](https://support.appsflyer.com/hc/articles/207034356)
- [Pull API](https://support.appsflyer.com/hc/articles/360007530258)

#### The complete Android subscription attribution flow

See the following flowchart for the complete subscription attribution flow:

- Getting notified about a subscription status change.
- Associating a subscription with AppsFlyer ID and GAID.
- [Sending a subscription-related event to AppsFlyer](https://support.appsflyer.com/hc/articles/4411049918865#sending-the-event-to-appsflyer).

<Image src="https://files.readme.io/5fbb1479ba0b743c9fd331e02521a206fa437ae7a5e80969599418b11e745b2a-4411621302417.png" alt="google-play-server-notifications-flow.png" />

</Tab>
<Tab title="iOS">

Apple calls its service [Server-to-Server notifications](https://developer.apple.com/documentation/storekit/in-app_purchase/enabling_server-to-server_notifications). This service is designed specifically for auto-renewable subscriptions. The App Store sends notifications of real-time changes in a subscription's status. You can use these notifications and their data to send subscription-related events to AppsFlyer.

#### Step 1: Set up the server endpoint to receive subscription-related notifications

Set up a server endpoint that receives post requests. Configure the endpoint as follows:

1. Support App Transport Security (ATS) on your server. The App Store must establish a secure network connection with your server by using ATS protocols before sending notifications. For more information, see [preventing insecure network connections](https://developer.apple.com/documentation/security/preventing_insecure_network_connections).
2. Determine a URL endpoint on your server to use for subscription status updates. For example, https://myserver/subscription-notifications.
3. Configure the subscription status URL for your app in App Store Connect. For guidance, see [Enable status notifications for auto-renewable subscriptions](https://help.apple.com/app-store-connect/#/dev0067a330b).

#### Step 2: Connect the server endpoint to your app:

Once the endpoint is configured, input the server URL in the _**Subscription Status URL**_ field in App Store Connect:

<Image src="https://files.readme.io/f480f594a6ff6077f7921b233f6ef7aa9493a45740dda40063a2a39c1049bf2d-4411628013073.png" alt="apple-app-store-server-notifications.png" />

#### Step 3: Receive the notification and associate it with AppsFlyer IDs and IDFA in your database

Now you are ready to receive notifications from Apple about subscriptions. See the following sample notification:

```json
{
    "latest_receipt": "ewoXXXXX",
    "latest_receipt_info": {
        "original_purchase_date_pst": "2019-07-29 21:13:18 America/Los_Angeles",
        "quantity": "1",
        "unique_vendor_identifier": "XXX",
        "original_purchase_date_ms": "1564459998000",
        "expires_date_formatted": "2019-08-06 04:13:17 Etc/GMT",
        "is_in_intro_offer_period": "false",
        "purchase_date_ms": "1564459997000",
        "expires_date_formatted_pst": "2019-08-05 21:13:17 America/Los_Angeles",
        "is_trial_period": "true",
        "item_id": "1452171111",
        "unique_identifier": "00000",
        "original_transaction_id": "0000000",
        "expires_date": "00000000",
        "app_item_id": "0000000",
        "transaction_id": "00000000",
        "bvrs": "00000",
        "web_order_line_item_id": "00000000",
        "version_external_identifier": "000000",
        "bid": "com.XXX",
        "product_id": "XXXXX",
        "purchase_date": "2019-07-30 04:13:17 Etc/GMT",
        "purchase_date_pst": "2019-07-29 21:13:17 America/Los_Angeles",
        "original_purchase_date": "2019-07-30 04:13:18 Etc/GMT"
    },
    "environment": "PROD",
    "auto_renew_status": "true",
    "password": "*****",
    "auto_renew_product_id": "com.XXXX",
    "notification_type": "INITIAL_BUY"
}
```

> ❗️ Important
>
> The data from **Apple's Status Update Notification** doesn't contain the subscription price. You should implement backend logic to match the notification from Apple with the correct subscription price.

You use this data to send subscription-related events to AppsFlyer. To do so, you need to associate a subscription with an AppsFlyer ID and IDFA. We strongly recommend including the IDFA when sending a server-to-server event. Including it allows AppsFlyer to send event postbacks to SRNs (self-reporting networks). It also opens for you the option to [use AppsFlyer Audiences](https://support.appsflyer.com/hc/articles/115002689186).

You can get the AppsFlyer ID and IDFA in one of the following ways:

- [SDK](https://support.appsflyer.com/hc/articles/207032066#unique-identifier-for-installs)
- [Raw data](https://support.appsflyer.com/hc/articles/208387843)
- [Push API](https://support.appsflyer.com/hc/articles/207034356)
- [Pull API](https://support.appsflyer.com/hc/articles/360007530258)

#### The complete iOS subscription attribution flow

See the following flowchart for the complete subscription attribution flow:

- Getting notified about a subscription status change.
- Associating a subscription with AppsFlyer ID and IDFA.
- [Sending a subscription-related event to AppsFlyer](https://support.appsflyer.com/hc/articles/4411049918865#sending-the-event-to-appsflyer).

<Image src="https://files.readme.io/da0f0f8ed0278583e5c64fe22d575b85c680d42ee4e0ac61c554379b767f8d8d-4411628011153.png" alt="apple-app-store-server-notifications-flow.png" />

</Tab>
</Tabs>

### Sending the event to AppsFlyer

At this point, you have knowledge of a subscription status change (purchase, renewal, cancellation) and have associated it with an AppsFlyer ID. Now, make sure the following takes place:

1. Your server gathers the necessary data for the event. Such data should include the following: revenue, subscription type, subscription ID (item_id in the data from Apple), AppsFlyer ID, time of renewal. Recommended mapping (see the code snippet below):
   - af_revenue: revenue
   - af_content_type: subscription type
   - af_content_id: subscription ID (item_id in the data from Apple)
   - renewal: true/false (based on subscription status change)
   - eventTime: the time the notification reaches your server
2. Based on the type of event (purchase, renewal, cancellation), the server sends the event to AppsFlyer as a subscription event with all related data.

### Formatting and sending the event

Subscription event request example:

```json
HTTP POST https://api2.appsflyer.com/inappevent/<APP_ID>
HTTP/1.1
headers:
{
  authentication: '<YOUR_DEV_KEY>',
  Host: 'api2.appsflyer.com',
  Accept: 'application/json',
  'Content-Type': 'application/json'
}
body:
{
  "appsflyer_id":"<APPS_FLYER_ID>",
  "customer_user_id":"123456",
  "eventName":"af_subscribe",
  "eventValue":"{\"af_revenue\":\"200\",\"af_content_id\":\"092\", \"af_content_type\": \"123\", \"renewal\":\"true\"}",
  "eventCurrency":"USD",
  "ip":"1.0.0.0",
  "eventTime":"2018-07-09 4:17:00.000",
  "af_events_api":"true"
}
```

To learn how to format and send the event to AppsFlyer, see [sending server-to-server events](https://support.appsflyer.com/hc/articles/207034486-Server-to-Server-In-App-Events-API-HTTP-API-).