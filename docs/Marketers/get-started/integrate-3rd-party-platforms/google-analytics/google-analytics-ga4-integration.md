---
title: "Google Analytics (GA4) integration"
excerpt: "Learn how to integrate AppsFlyer with Google Analytics (GA4) to send attribution data and selected in-app events."
---
AppsFlyer integration with Google Analytics (GA4) enables advertisers to send attribution data and selected in-app events from AppsFlyer to GA4. This integration works with iOS and Android apps that already have the [Google Analytics for Firebase SDK](https://firebase.google.com/docs/analytics) implemented.

> ❗️ Important!
>
> This integration works with iOS and Android apps that already have the [Google Analytics for Firebase SDK implemented](https://firebase.google.com/docs/analytics). For the integration to succeed, the AppsFlyer SDK has to collect the `app_instance_id` value from the Firebase SDK. See instructions on [how to retrieve the app instance ID from the Firebase SDK](#6-retrieve-app-instance-id-in-appsflyer-sdk).

## How does it work?

- When a new install occurs, AppsFlyer sends the touchpoint details— media source, campaign name, and campaign ID—to GA4. It also sends the Firebase SDK's `app_instance_id` to ensure the touchpoint is recorded in GA4 for that user.
- When in-app events occur, GA4 will attribute the event to the last touchpoint.

## Set up Google Analytics (GA4) integration

Follow the instructions below to configure the integration with Google Analytics (GA4).

### 1. Select Google Analytics (GA4) in the Partner Marketplace

**Prerequisite:** Before setting up the integration, make sure you [contact the partner](/docs/partner-integrations#contact-details) and open an account with them.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for Google Analytics (GA4) and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle **must stay on (active) as long as you work with Google Analytics (GA4)**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below.

The Google Analytics configuration only includes the **Integration** tab.

### 2. Set GA4 Integration in AppsFlyer

Configure the following settings:

1. In the **Integration** tab, select the app for the integration and turn **Activate partner** on.

> 📘 Note
>
> The toggle must be on [(activated)](/docs/partner-activation-deactivation) for as long as you work with the partner.

2. In **Firebase App ID,** enter the identifier of the Firebase app. To learn how to locate the Firebase App ID, see [the Firebase documentation](https://firebase.google.com/support/faq#find-app-id).
3. In **API Secret,** enter the API Secret used to authenticate postbacks to Google Analytics. An API Secret is generated through the Google Analytics user interface. To view, edit, or create a secret, follow the instructions in the [Google documentation](https://support.google.com/analytics/answer/9814495?sjid=5179426966283787649-EU). **When instructed to select a web data stream, choose an Android or iOS data stream instead.**
4. Turn on **Customer User ID** to send the customer user ID (CUID) instead of the advertising ID (IDFA).
5. Under the **Default postbacks** section, **for users from**, select **All media sources including organic**.

> 📘 Note
>
> The install postback includes only the touchpoint details (media source, campaign name, and campaign ID).

### 3. Set default postbacks

AppsFlyer can send automatic postbacks to GA4 following user installs, including both installs and re-engagements (including re-attributions). Re-engagements occur when a user who already has the app installed opens it after clicking a campaign link. Learn more about [default postbacks](/docs/set-up-an-integrated-partner#default%20postbacks).

### 4. Set in-app event postbacks

In the **Integration** tab, map AppsFlyer in-app events to Google Analytics (GA4) events, sent via postbacks.

> 📘 Note
>
> - Postbacks for mobile in-app events sent via S2S aren't supported.
> - GA4 does not deduplicate events sent from both the Firebase SDK and AppsFlyer. We recommend configuring in-app event postbacks only for events that are not already sent to GA4 via the Firebase SDK.

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received from the AppsFlyer SDK integrated into your app.<br />**Tip**: Don't see the event you are looking for?<br />   - Make sure to activate the event on a device with a non-organic installation, and recheck.<br />   - Type it in **AppsFlyer event**, then click **Create custom**.<br />Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br />   - **Text field:** Get the corresponding event ID from the partner.<br />   - **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br />   - **As is**: Send the events as they are, without name mapping. |
| **for users from** | Select the sending option for the event:<br />   - **All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events. |
| **including** | - **No data (default)**: Send only the event itself without any event values.<br />   - **Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).<br />   - **Values without revenue**: Send all the parameters **excluding** the revenue value. |

3. [Optional] Click the **Add condition** icon ( <Image src="https://files.readme.io/959329be2b1286507b5c87b033785e91ab135592ae37cf3200539400832490c0-25709762755857.png" alt="condition-2.png" />) to [set conditions](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) for an event.
4. Click **Save integration**.
5. Send the event postback mapping

### 5. Send your developer the postback event mapping

After you have set up the in-app event mapping, send your developer a table where each mapped event corresponds to a row with the following columns:

- **AF event:** Name of the AppsFlyer event.
- **Mapped to Google event:** Name of the event in Google Analytics.

> ❗️ Important!
>
> Don’t use any of the [Google reserved events](/docs/google-analytics-ga4-integration#h_01HZQ4ABBN6ZEB7RJQMFS0AB73) as names for custom Google Analytics events.

- **AF event parameters (MANDATORY):** Predefined AppsFlyer event parameters that must be included in the event postback sent to Google Analytics.

> ❗️ Important!
>
> It is mandatory to include all predefined AF event parameters within the event definition exactly as they are listed in the table; failure to do so will result in Google Analytics rejecting the postback.

#### The event mapping table

The following table includes all the Google Analytics events and their predefined AppsFlyer parameters. Send your developer a table containing just the events that you mapped.

| AF recommended name (Optional) | The Google Ads Event name | Predefined AF event parameters (MANDATORY) |
| --- | --- | --- |
| af\_add\_payment\_info | [add\_payment\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_payment_info) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue), [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
|  | [add\_shipping\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_shipping_info) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue), [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
| af\_add\_to\_cart | [add\_to\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_cart) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue), [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
| af\_add\_to\_wishlist | [add\_to\_wishlist](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_wishlist) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue), [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
| af\_initiated\_checkout | [begin\_checkout](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#begin_checkout) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue), [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
|  | [campaign\_details](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#campaign_details) | campaign id, campaign name |
| af\_spent\_credits | [earn\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#earn_virtual_currency) | [af\_revenue](/docs/in-app-events-event-structure#af_revenue) |
|  | [generate\_lead](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#generate_lead) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue) |
|  | [join\_group](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#join_group) |  |
| af\_level\_achieved | [level\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#level_up) |  |
| af\_login | [login](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#login) |  |
|  | [post\_score](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#post_score) | af\_user\_score |
| af\_purchase | [purchase](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#purchase) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue), [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content), [af\_receipt\_id](/docs/in-app-events-event-structure#af_receipt_id) |
|  | [refund](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#refund) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue), [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content), [af\_receipt\_id](/docs/in-app-events-event-structure#af_receipt_id) |
|  | [remove\_from\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#remove_from_cart) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue), [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
|  | [screen\_view](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#screen_view) |  |
| af\_search | [search](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#search) |  |
|  | [select\_content](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_content) |  |
|  | [select\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_item) | [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
|  | [select\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_promotion) | [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
|  | [share](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#share) |  |
|  | [sign\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#sign_up) |  |
|  | [spend\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#spend_virtual_currency) | [af\_revenue](/docs/in-app-events-event-structure#af_revenue) |
|  | [tutorial\_begin](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_begin) |  |
| af\_tutorial\_completion | [tutorial\_complete](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_complete) |  |
| af\_achievement\_unlocked | [Unlock\_achievement](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#unlock_achievement) | af\_achievement\_id |
|  | [view\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_cart) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue), [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
|  | [view\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue), [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
|  | [view\_item\_list](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item_list) | [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
|  | [view\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_promotion) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue), [af\_price](/docs/in-app-events-event-structure#af_price), [af\_content\_id](/docs/in-app-events-event-structure#af_content_id), [af\_content](/docs/in-app-events-event-structure#af_content) |
|  | [view\_search\_results](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_search_results) |  |
| af\_ad\_view | [ad\_impression](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#ad_impression) | [af\_currency](/docs/in-app-events-event-structure#af_currency), [af\_revenue](/docs/in-app-events-event-structure#af_revenue) |

#### Reserved Google event names

The following event names are reserved and cannot be used as custom event names:

- `ad_activeview`
- `ad_click`
- `ad_exposure`
- `ad_query`
- `ad_reward`
- `adunit_exposure`
- `app_clear_data`
- `app_exception`
- `app_install`
- `app_remove`
- `app_store_refund`
- `app_update`
- `app_upgrade`
- `dynamic_link_app_open`
- `dynamic_link_app_update`
- `dynamic_link_first_open`
- `error`
- `firebase_campaign`
- `firebase_in_app_message_action`
- `firebase_in_app_message_dismiss`
- `firebase_in_app_message_impression`
- `first_open`
- `first_visit`
- `in_app_purchase`
- `notification_dismiss`
- `notification_foreground`
- `notification_open`
- `notification_receive`
- `notification_send`
- `os_update`
- `session_start`
- `user_engagement`

### 6. Retrieve app instance ID in AppsFlyer SDK

The `app_instance_id` uniquely identifies a Firebase app installation, and the `ga_session_id` uniquely identifies a Firebase app session. Retrieve these values from the Firebase SDK, then send them to GA4 using the `setAdditionalData` API.

Let your developer implement the code to:

1. Collect the `app_instance_id` and the `ga_session_id` fields from Firebase.
2. Call `setAdditionalData`, before the first launch, to include the app instance ID and `ga_session_id`, in installs, sessions, and in-app events.

> ❗️ Important!
>
> `setAdditionalData` (Android / Unity / React Native) and `customData` (iOS) accept a **mapping of key-value pairs**. Sends both `app_instance_id` and `ga_session_id` **together in the same mapping,** so both values are included. If you send them in **separate** `setAdditionalData` calls, the later one will overwrite the earlier one.
**Android native**

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).appInstanceId.addOnCompleteListener { task ->
   if (task.isSuccessful) {
       AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.result)
    }
}
```

**Java**

```java
FirebaseAnalytics.getInstance(this).getAppInstanceId().addOnCompleteListener(task -> {
       if (task.isSuccessful()) {
           AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.getResult());
       }
  });
```

API reference: [setAdditionalData](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata)
**iOS native**

**Swift**

```swift
let appInstanceId = Analytics.appInstanceID()
    AppsFlyerLib.shared().customData = ["app_instance_id": appInstanceId]
```

**Objective C**

```objectivec
- (void) fetchAnalyticsInstanceId {
           NSString *instanceID = [FIRAnalytics appInstanceID];
           [[AppsFlyerLib shared] setAdditionalData:@{@"app_instance_id": instanceID}];
}
```

API reference: [customData](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata)
**Unity**

```csharp
using Firebase.Analytics;
    public class AnalyticsManager : MonoBehaviour
    {
        private async void Start()
        { 
           AppsFlyer.initSDK(devKey, appID, this);
           string appInstanceId = await FirebaseAnalytics.GetAnalyticsInstanceIdAsync();
           Dictionary <string, string> customData = new Dictionary<string, string>();
           customData.Add("app_instance_id", appInstanceId);
           AppsFlyer.setAdditionalData(appInstanceId);
           AppsFlyer.startSDK();
        }
}
```

API reference: [setAdditionalData](https://dev.appsflyer.com/hc/docs/api#setadditionaldata)
**React native**

API reference: [setAdditionalData](https://dev.appsflyer.com/hc/docs/rn_api#setadditionaldata)
### 7. Retrieve GA4 session ID in the AppsFlyer SDK

The `ga_session_id` uniquely identifies a session of a Firebase app. This value must be retrieved from the Firebase SDK and sent to GA4 using the `setAdditionalData` API.

Let your developer implement the code to:

1. Collect the `ga_session_id` field from Firebase.
2. Call `setAdditionalData` before the first launch to include the session ID (and `app_instance_id`, if used).
3. Use the key `ga_session_id` when calling the API.

> ❗️ Important!
>
> `setAdditionalData` (Android / Unity / React Native) and `customData` (iOS) accept a **mapping of key-value pairs**. If your app sends both `app_instance_id` and `ga_session_id` (see [step 5](#6-retrieve-app-instance-id-in-appsflyer-sdk)), **send them together in the same mapping** so both values are included. If you send them in **separate** `setAdditionalData` calls, the later one will overwrite the earlier one.
**Android native**

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).sessionId.addOnCompleteListener { task ->
    if (task.isSuccessful) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.result)
    }
}
```

**Java**

```java
FirebaseAnalytics.getInstance(this).getSessionId().addOnCompleteListener(task -> {
    if (task.isSuccessful()) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.getResult());
    }
});
```

API reference: [setAdditionalData](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata)
**iOS native**

**Swift**

```swift
if #available(iOS 14.0, *) {
    Analytics.sessionID { sessionID, error in
        if let sessionID = sessionID {
            AppsFlyerLib.shared().customData = ["ga_session_id": sessionID]
        }
    }
}
```

**Objective-C**

```objectivec
- (void)fetchAnalyticsSessionId {
    if (@available(iOS 14.0, *)) {
        [FIRAnalytics sessionIDWithCompletion:^(NSString * _Nullable sessionID, NSError * _Nullable error) {
            if (sessionID) {
                [[AppsFlyerLib shared] setAdditionalData:@{@