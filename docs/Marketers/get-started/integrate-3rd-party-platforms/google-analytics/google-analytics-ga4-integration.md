---
title: "Google Analytics (GA4) integration"
excerpt: "Learn how to integrate AppsFlyer with Google Analytics (GA4) to send attribution data and selected in-app events."
x-zendesk:
  id: 25707682812561
  url: https://support.appsflyer.com/hc/en-us/articles/25707682812561-Google-Analytics-GA4-integration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Google Analytics
  section_id: 6551226043793
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Marketers, Loc Published]
  promoted: false
  comments_disabled: false
  created_at: '2024-06-06T15:26:00Z'
  edited_at: '2026-09-27T12:24:13Z'
---
AppsFlyer integration with Google Analytics (GA4) enables advertisers to send attribution data and selected in-app events from AppsFlyer to GA4. This integration works with iOS and Android apps that already have the [Google Analytics for Firebase SDK](https://firebase.google.com/docs/analytics) implemented.

**Important!**

This integration works with iOS and Android apps that already have the [Google Analytics for Firebase SDK implemented](https://firebase.google.com/docs/analytics). For the integration to succeed, the AppsFlyer SDK has to collect the `app_instance_id` value from the Firebase SDK. See instructions on [how to retrieve the app instance ID from the Firebase SDK](#5-retrieve-app-instance-id-in-appsflyer-sdk).

## How does it work?

* When a new install occurs, AppsFlyer sends the touchpoint details— media source, campaign name, and campaign ID—to GA4. It also sends the Firebase SDK's `app_instance_id` to ensure the touchpoint is recorded in GA4 for that user.
* When an in-app event occurs, GA4 will attribute the event to the last touchpoint.

## Set up Google Analytics (GA4) integration

Follow the instructions below to configure the integration with Google Analytics (GA4).

<Accordion title="1. Select Google Analytics (GA4) in the Partner Marketplace">

**Prerequisite:** Before setting up the integration, make sure you [contact the partner](/docs/partner-integrations#contact-details) and open an account with them.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for Google Analytics (GA4) and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with Google Analytics (GA4)**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

The Google Analytics configuration only includes the **Integration** tab.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

</Accordion>

<Accordion title="2. Set GA4 Integration in AppsFlyer">

Configure the following settings:

1. In the **Integration** tab, select the app for the integration and turn **Activate partner** on.

   **Note:** The toggle must be on [(activated)](/docs/partner-activation-deactivation) for as long as you work with the partner.

   For more details about partner activation, click [here](/docs/partner-activation-deactivation).
2. In **Firebase App ID,** enter the identifier of the Firebase app. To learn how to locate the Firebase App ID, see [the Firebase documentation](https://firebase.google.com/support/faq#find-app-id).
3. In **API Secret,** enter the API Secret used to authenticate postbacks to Google Analytics. An API Secret is generated through the Google Analytics user interface. To view, edit, or create a secret, follow the instructions in the [Google documentation](https://support.google.com/analytics/answer/9814495?sjid=5179426966283787649-EU). **When instructed to select a web data stream, choose an Android or iOS data stream instead.**
4. Turn on **Customer User ID** to send the customer user ID (CUID) instead of the advertising ID (IDFA).
5. Under the **Default postbacks** section, **for users from**, select **All media sources including organic**.

**Note**

The install postback includes only the touchpoint details (media source, campaign name, and campaign ID).

</Accordion>

<Accordion title="3. Set default postbacks">

AppsFlyer can send automatic postbacks to GA4 following user installs, including both installs and re-engagements (including re-attributions). Re-engagements occur when a user who already has the app installed opens it after clicking a campaign link. Learn more about [default postbacks](/docs/set-up-an-integrated-partner#default%20postbacks).

</Accordion>

<Accordion title="4. Set in-app event postbacks">

In the **Integration** tab, map AppsFlyer in-app events to Google Analytics (GA4) events, sent via postbacks.

**Note**

* Postbacks for mobile in-app events sent via S2S aren't supported.
* GA4 does not deduplicate events sent from both the Firebase SDK and AppsFlyer. We recommend configuring in-app event postbacks only for events that are not already sent to GA4 via the Firebase SDK.

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK event to the list. The following table describes the fields to complete:

   

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received from the AppsFlyer SDK integrated into your app.<br /><br />**Tip**: Don't see the event you are looking for?<br /><br />* Make sure to activate the event on a device with a non-organic installation, and recheck.<br />* Type it in **AppsFlyer event**, then click **Create custom**.<br /><br />Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br /><br />* **Text field:** Get the corresponding event ID from the partner.<br />* **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br />* **As is**: Send the events as they are, without name mapping. |
| **for users from** | Select the sending option for the event:<br /><br />* **All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events. |
| **including** | * **No data (default)**: Send only the event itself without any event values.<br />* **Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).<br />* **Values without revenue**: Send all the parameters **excluding** the revenue value. |

3. [Optional] Click the **Add condition** icon (![condition-2.png](https://files.readme.io/959329be2b1286507b5c87b033785e91ab135592ae37cf3200539400832490c0-25709762755857.png)) to [set conditions](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) for an event.
4. Click **Save integration**.
5. Send the event postback mapping

</Accordion>

<Accordion title="5. Send your developer the postback event mapping">

After you have set up the in-app event mapping, send your developer a table where each mapped event corresponds to a row with the following columns:

* **AF event:** Name of the AppsFlyer event.
* **Mapped to Google event:** Name of the event in Google Analytics.

**Important!**

Don’t use any of the [Google reserved events](#h_01HZQ4ABBN6ZEB7RJQMFS0AB73) as names for custom Google Analytics events.

* **AF event parameters (MANDATORY):** Predefined AppsFlyer event parameters that must be included in the event postback sent to Google Analytics.

**Important!**

It is mandatory to include all predefined AF event parameters within the event definition exactly as they are listed in the table; failure to do so will result in Google Analytics rejecting the postback.

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
|  | [generate\_lead](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#generate_lead) | [af\_currency](/docs/in-app-events-event-structure#af_currency),[af\_revenue](/docs/in-app-events-event-structure#af_revenue) |
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

* `ad_activeview`
* `ad_click`
* `ad_exposure`
* `ad_query`
* `ad_reward`
* `adunit_exposure`
* `app_clear_data`
* `app_exception`
* `app_install`
* `app_remove`
* `app_store_refund`
* `app_update`
* `app_upgrade`
* `dynamic_link_app_open`
* `dynamic_link_app_update`
* `dynamic_link_first_open`
* `error`
* `firebase_campaign`
* `firebase_in_app_message_action`
* `firebase_in_app_message_dismiss`
* `firebase_in_app_message_impression`
* `first_open`
* `first_visit`
* `in_app_purchase`
* `notification_dismiss`
* `notification_foreground`
* `notification_open`
* `notification_receive`
* `notification_send`
* `os_update`
* `session_start`
* `user_engagement`

</Accordion>

<Accordion title="6. Retrieve app instance ID in AppsFlyer SDK">

The `app_instance_id` uniquely identifies a Firebase app installation, and the `ga_session_id` uniquely identifies a Firebase app session. Retrieve these values from the Firebase SDK, then send them to GA4 using the `setAdditionalData` API.

Let your developer implement the code to:

1. Collect the `app_instance_id` and the `ga_session_id` fields from Firebase.
2. Call `setAdditionalData`, before the first launch, to include the app instance ID and `ga_session_id`, in installs, sessions, and in-app events.

**Important!**

`setAdditionalData` (Android / Unity / React Native) and `customData` (iOS) accept a **mapping of key-value pairs**. Sends both `app_instance_id` and `ga_session_id` **together in the same mapping,** so both values are included. If you send them in **separate** `setAdditionalData` calls, the later one will overwrite the earlier one.

<Accordion title="Android native">

**Kotlin**

```
FirebaseAnalytics.getInstance(this).appInstanceId.addOnCompleteListener { task ->
   if (task.isSuccessful) {
       AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.result)
    }
}
```

**Java**

```
FirebaseAnalytics.getInstance(this).getAppInstanceId().addOnCompleteListener(task -> {
       if (task.isSuccessful()) {
           AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.getResult());
       }
  });
```

API reference: [setAdditionalData](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata)

</Accordion>

<Accordion title="iOS native">

**iOS native**

```
let appInstanceId = Analytics.appInstanceID()
    AppsFlyerLib.shared().customData = ["app_instance_id": appInstanceId]
```

**Objective C**

```
(void) fetchAnalyticsInstanceId {
           NSString *instanceID = [FIRAnalytics appInstanceID];
           [[AppsFlyerLib shared] setAdditionalData:@{@"app_instance_id": instanceID}];
}
```

API reference: [customData](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata)

</Accordion>

<Accordion title="Unity">

```
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

</Accordion>

<Accordion title="React native">

API reference: [setAdditionalData](https://dev.appsflyer.com/hc/docs/rn_api#setadditionaldata)

</Accordion>

</Accordion>

<Accordion title="7. Retrieve GA4 session ID in the AppsFlyer SDK">

The `ga_session_id` uniquely identifies a session of a Firebase app. This value must be retrieved from the Firebase SDK and sent to GA4 using the `setAdditionalData` API.

Let your developer implement the code to:

1. Collect the `ga_session_id` field from Firebase.
2. Call `setAdditionalData` before the first launch to include the session ID (and `app_instance_id`, if used).
3. Use the key `ga_session_id` when calling the API.

**Important!**

`setAdditionalData` (Android / Unity / React Native) and `customData` (iOS) accept a **mapping of key-value pairs**. If your app sends both `app_instance_id` and `ga_session_id` (see [step 5](#5-retrieve-app-instance-id-in-appsflyer-sdk)), **send them together in the same mapping** so both values are included. If you send them in **separate** `setAdditionalData` calls, the later one will overwrite the earlier one.

<Accordion title="Android native">

**Kotlin**

```
FirebaseAnalytics.getInstance(this).sessionId.addOnCompleteListener { task ->
    if (task.isSuccessful) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.result)
    }
}
```

**Java**

```
FirebaseAnalytics.getInstance(this).getSessionId().addOnCompleteListener(task -> {
    if (task.isSuccessful()) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.getResult());
    }
});
```

API reference: [setAdditionalData](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata)

</Accordion>

<Accordion title="iOS native">

**Swift**

```
if #available(iOS 14.0, *) {
    Analytics.sessionID { sessionID, error in
        if let sessionID = sessionID {
            AppsFlyerLib.shared().customData = ["ga_session_id": sessionID]
        }
    }
}
```

**Objective-C**

```
- (void) fetchAnalyticsSessionId {
    if (@available(iOS 14.0, *)) {
        [FIRAnalytics sessionIDWithCompletion:^(NSString * _Nullable sessionID, NSError * _Nullable error) {
            if (sessionID) {
                [[AppsFlyerLib shared] setAdditionalData:@{@"ga_session_id": sessionID}];
            }
        }];
    }
}
```

API reference: [customData](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata)

</Accordion>

<Accordion title="Unity">

```
using Firebase.Analytics;
using System.Threading.Tasks;
using AppsFlyerSDK;
using UnityEngine;
using System.Collections.Generic;

public class AnalyticsManager : MonoBehaviour
{
    private async void Start()
    {
        AppsFlyer.initSDK("yourDevKey", "yourAppID", this);

        // Get session ID
        string sessionId = await FirebaseAnalytics.GetSessionIdAsync();

        Dictionary<string, string> customData = new Dictionary<string, string>();
        customData.Add("ga_session_id", sessionId);
        AppsFlyer.setAdditionalData(customData);

        AppsFlyer.startSDK();
    }
}
```

API reference: [setAdditionalData](https://dev.appsflyer.com/hc/docs/api#setadditionaldata)

</Accordion>

</Accordion>

<Accordion title="8. Validate the GA4 integration">

Make sure the events in the postbacks you send to GA4 are registered and read by Google Analytics. There are two methods advertisers can use to view their data:

* Using [GA4 Explorations](https://support.google.com/analytics/answer/7579450?hl=en&ref_topic=12153537,12153943,2986333,&sjid=20462331341270448-EU&visit_id=638532662145815538-1056226594&rd=1#access-analysis&zippy=%2Cin-this-article), you can explore the raw event data with all associated parameters. **Prerequisite:** [Big Query export](https://support.google.com/analytics/answer/9823238) must be set up in your property)
* **The Events report** enables advertisers to view their postback events. The report can be found under one or more report collections.  
  For example, the Events reports can be found in the [Life cycle](https://support.google.com/analytics/answer/12924233?hl=en) or the [Games reporting](https://support.google.com/analytics/answer/12925133?hl=en&sjid=5454549956257318969-NC) collections under **Engagement** > **Events**.   
  For more information on the Events report see [the Google documentation](https://support.google.com/analytics/answer/12926615?sjid=5454549956257318969-NC).

  ![GA4 Events report](https://files.readme.io/01625878b13a46b8a87c34bf465c0ef6494a0f528960d62ce5535b69b29e7d0a-25707728713745.png)
* **The Traffic acquisition report** helps you understand where your website and app visitors are coming from.

  Under the [Life cycle collection](https://support.google.com/analytics/answer/12924233?hl=en) go to **Acquisition** > **Traffic Acquisition**).

  For more information on the Traffic acquisition report, see [the Google documentation](https://support.google.com/analytics/answer/12923437?hl=en&sjid=5454549956257318969-NC#zippy=%2Chow-do-i-filter-out-traffic-sources-from-the-report).

  ![GA4 Traffic acquisition report](https://files.readme.io/fa51e22d1a7941666224eb668efcbfc5a3bb8cce42cf373a82f3b1e096d2a9db-25707770926353.png)

</Accordion>
