---
title: About ROI360 store revenue
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T16:34:39Z'
  edited_at: '2026-10-05T09:07:40Z'
  id: 42138855425297
  locale: en-us
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/42138855425297-About-ROI360-store-revenue
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**At a glance:** Use ROI360 store revenue to validate in-app purchases and subscriptions, prevent duplicates, and calculate net revenue.

> 🚧 **Important!**
>
> ROI360 store revenue is available only to customers on the ROI360 premium plan. To check your plan or upgrade, contact your Customer Success Manager (CSM).

ROI360 store revenue is AppsFlyer’s premium solution for complete and accurate measurement of revenue from in-app purchases and subscriptions. It provides a comprehensive view of the customer life cycle, enabling the accurate measurement of Return On Ad Spend (ROAS).

| Feature | Details |
| --- | --- |
| Revenue measurement scope | <ul><li>Revenue from all in-app purchases of products and subscriptions managed through App Store Connect (iOS) and Google Play Console (Android)</li><li>Refunds</li><li>Pending and deferred transaction revenue (Android)</li><li>Subscription-related events that occur both inside and outside the app</li><li>Net revenue, which accounts for store commissions and taxes</li></ul> |
| Revenue validation and accuracy | The solution prevents duplicate transactions from being recorded. On iOS, this also includes preventing duplication caused by Family Sharing. ROI360 store revenue can also forward Apple App Store transaction data directly to advertisers. |
| Data sources | <ul><li>AppsFlyer purchase SDK connector for Android and iOS</li><li>App Store server notifications</li><li>Google Play Real-Time Developer Notifications (RTDN)</li></ul> |
| Reporting and data availability | Revenue data is available in AppsFlyer dashboards and reports and can also be shared with partners through postbacks. |

> ❗️ **Warning**
>
> When using ROI360 store revenue, do not send in-app purchase events, as this will result in duplicate revenue reporting.

## How does ROI360 store revenue work?

1. A user makes an in-app purchase or an auto-renewable subscription.
2. The app makes a transaction in the app store.
3. The AppsFlyer purchase SDK connector automatically detects purchases and sends their payloads to AppsFlyer for validation and logging.
4. AppsFlyer validates the purchase with the relevant store to ensure it's not fraudulent.
   * Upon successful validation, AppsFlyer logs the purchase or subscription in-app event.
   * If receipt validation fails, the event displays in the blocked in-app events raw data report (available to Protect360 subscribers) and in the Live events viewer page with parameter `af_validated` = false.
5. AppsFlyer transfers the response to the SDK connector, which in turn transfers the receipt validation response (success or failure) to the app.
6. Any incoming server notifications from the app stores are also processed by the AppsFlyer purchase and subscription revenue business logic.
   * Notifications regarding transactions previously reported via the SDK connector are validated and processed, and result in the internal creation of a purchase or life cycle event.
   * Notifications regarding unknown transactions are dropped.
   * For iOS, all server notifications can be rerouted to your own servers.

## Activate ROI360 store revenue

To activate ROI360 store revenue measurement, follow these steps:

1. In AppsFlyer, from the side menu, open <Image alt="settings-roi.png" src="https://files.readme.io/86023f68c41c5260314171f40b28b73ccd6c9dbdf263391c3c751041625a6ed9-42138855423633.png" width="2.17%" /> **Settings** and under **ROI360** select **Revenue Settings**.
2. Open the **Purchases & subscriptions** tab.
3. Under **1 Choose Product type**, select **ROI360**.
4. Click **Next** to continue.

## Set up ROI360 store revenue

See the <Anchor target="_blank" href="/marketers/docs/set-up-roi360-store-revenue">Set up ROI360 store revenue</Anchor> article

## Reference

The following sections provide additional details about key aspects of ROI360 in-app purchase (IAP) and subscription revenue measurement. These include events and parameters for IAP and subscription events, Net revenue, which supports gross-to-net revenue calculations, and the general characteristics and limitations of the ROI360 IAP and subscription revenue measurement solution.

> 📘 **Note**
>
> To send additional custom parameters with your in-app events, configure a **custom data source** in the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-connector">Purchase SDK Connector</Anchor>. This allows you to enrich purchase and subscription events with your own business logic or metadata.
> These parameters will be available in the raw data report's `custom_data` field.

<div id="iaprelated-events-and-parameters" />

<Accordion title="IAP-related events and parameters">

The following sections display the IAP-related events that AppsFlyer measures and the parameters recorded for each event. For an explanation of the included parameters, see the [event parameter dictionary](#parameter-dictionary).

**All generated events have the following properties:**

* Server-to-server (S2S) events.
* Available in raw data reports as organic or non-organic in-app events, and included in the Revenue ETL Stores reports.
* Sent to partners via postbacks.
* Supported in SKAN Conversion Studio.

<div id="purchase-af_purchase" />

<Accordion title="Purchase (af_purchase)">

**Description**

Recorded when a user makes a purchase.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-af_purchase_free" />

<Accordion title="Purchase free (af_purchase_free)">

**Description**

Recorded when a user makes a purchase that has no revenue amount. All revenue parameters will display 0.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-canceled-af_purchase_canceled" />

<Accordion title="Purchase canceled (af_purchase_canceled)">

**Description**

Recorded when a user cancels a purchase.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="purchase-pending-af_purchase_pending" />

<Accordion title="Purchase pending (af_purchase_pending)">

**Description**

Recorded when a user makes a purchase but the payment isn't yet processed.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="refund-af_purchase_refund" />

<Accordion title="Refund (af_purchase_refund)">

**Description**

Recorded when a purchase is refunded.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue (included in the event when the revenue exceeds zero)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="test-purchase-af_purchase_sandbox_sdk" />

<Accordion title="Test purchase (af_purchase_sandbox_sdk)">

**Description**

Recorded when testing a purchase recorded via SDK in sandbox environment.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_purchase_sandbox_s2s" />

<Accordion title="Test purchase (af_purchase_sandbox_s2s)">

**Description**

Recorded when testing a purchase reported via S2S in a sandbox environment.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="subscriptionrelated-events-and-parameters" />

<Accordion title="Subscription-related events and parameters">

The following sections display the subscription-related events that AppsFlyer measures, and the parameters that are recorded for each event. See the [event parameter dictionary](#parameter-dictionary) for an explanation of the included parameters.

All generated events:

* Are considered S2S events.
* Are accessible in raw data reports (as organic or non-organic in-app events).
* Can be sent via postbacks to partners.
* Can be used in SKAN Conversion Studio.

**Note:** Depending on the user device platform, some parameters aren't always populated for an in-app event.

<div id="trial-started-af_ars_trial_started" />

<Accordion title="Trial started (af_ars_trial_started)">

**Description**

Recorded when a subscriber begins a trial period.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-canceled-af_ars_trial_canceled" />

<Accordion title="Trial canceled (af_ars_trial_canceled)">

**Description**

Recorded when a subscriber cancels the automatic renewal of the subscription during the trial period. If a user doesn't restore the auto-renewal within the trial period, a churn event follows.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-churned-af_ars_trial_churned" />

<Accordion title="Trial churned (af_ars_trial_churned)">

**Description**

Recorded when a subscriber churns following a trial period. This happens after auto-renewal cancelation and trial period expiration. It can also follow a billing or technical issue with the renewal leading to churn.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_reason

</Accordion>

<div id="trial-converted-af_ars_trial_converted" />

<Accordion title="Trial converted (af_ars_trial_converted)">

**Description**

Recorded when a fully priced renewal starts, following a trial period.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* store\_commission
* af\_revenue (included in the event only when the revenue exceeds zero)
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-started-af_ars_subscription_started" />

<Accordion title="Subscription started (af_ars_subscription_started)">

**Description**

Recorded when a discounted or a fully priced subscription starts.

**Note**:

* New subscriptions can only be recorded via the SDK connector.
* For iOS, if a subscriber repurchases a subscription they already own, the SDK connector reports a successful receipt validation back to the app, but doesn't record a new transaction in AppsFlyer.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue (included in the event when the revenue exceeds zero)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-canceled-af_ars_subscription_canceled" />

<Accordion title="Subscription canceled (af_ars_subscription_canceled)">

**Description**

Recorded when an auto-renewal subscription is canceled in the middle of a billing period. If a user doesn't restore the auto-renewal within the same billing period, a churn event follows.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-paused-af_ars_subscription_paused-android-only" />

<Accordion title="Subscription paused (af_ars_subscription_paused) - Android only">

**Description**

Recorded when a user pauses an active subscription.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-resumed-af_ars_subscription_resumed" />

<Accordion title="Subscription resumed (af_ars_subscription_resumed)">

**Description**

Recorded when a fully priced subscription is resumed following a churned or refunded subscription.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* af\_reason
* event\_revenue (included in the event when event revenue exceeds zero)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-churned-af_ars_subscription_churned" />

<Accordion title="Subscription churned (af_ars_subscription_churned)">

**Description**

Recorded when a subscriber churns. This usually happens after auto-renewal cancelation or billing period expiration. It can also follow a billing or technical issue, with the renewal leading to churn.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_reason

</Accordion>

<div id="subscription-refunded-af_ars_subscription_refunded" />

<Accordion title="Subscription refunded (af_ars_subscription_refunded)">

**Description**

Recorded when a subscriber is issued a refund.

**Note:**

* This event is usually generated along with a negative value. In cases where it is impossible to detect which transactions were refunded, or details of the refund aren't included in the notification, the refund event shows no value.

**Parameters**

* app\_id
* customer\_user\_id
* af\_reason
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_refunded\_transaction\_ids
* event\_revenue\_usd
* event\_revenue (included in the event when the revenue exceeds zero)
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_store
* af\_environment
* af\_period\_type
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-billing-grace-af_ars_subscription_billing_grace" />

<Accordion title="Subscription billing grace (af_ars_subscription_billing_grace)">

**Description**

Recorded when a subscription renewal fails due to a billing issue and the subscriber enters the billing grace period.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-renewed-af_ars_subscription_renewed" />

<Accordion title="Subscription renewed (af_ars_subscription_renewed)">

**Description**

Recorded when an auto-renewal subscription takes place.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue (included in the event when the revenue exceeds zero)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-changed-af_ars_subscription_xgraded" />

<Accordion title="Subscription changed (af_ars_subscription_xgraded)">

**Description**

Recorded when a subscriber upgrades, downgrades, or cross-grades to a different product.

**Parameters**

* app\_id
* customer\_user\_id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue (included in the event when the revenue exceeds zero)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="existing-subscriber-af_ars_existing_subscriber" />

<Accordion title="Existing subscriber (af_ars_existing_subscriber)">

**Description**

Recorded when the SDK connector is notified about a subscriber in the middle of a billing cycle, before getting a follow-up server notification that transitions the subscriber to another relevant lifecycle stage. This event is usually generated during your onboarding and SDK connector adoption period.

**Parameters**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated

</Accordion>

<div id="test-purchase-af_ars_sandbox_sdk" />

<Accordion title="Test purchase (af_ars_sandbox_sdk)">

**Description**

Recorded when testing a purchase recorded via SDK in sandbox environment.

**Parameters**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_ars_sandbox_s2s" />

<Accordion title="Test purchase (af_ars_sandbox_s2s)">

**Description**

Recorded when testing a purchase reported via S2S in a sandbox environment.

**Parameters**

* app\_id
* customer\_user\_id
* country
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="parameter-dictionary" />

<Accordion title="Parameter dictionary">

Parameters for IAP and subscription events display in raw data reports either as their own columns or populated as part of the **Event value**.

The parameters that have their own columns are:

* app\_id
* customer\_user\_id
* country\_code
* af\_currency
* event\_revenue\_usd
* af\_revenue
* android\_id
* ip
* idfa
* appsflyer\_id

See the <Anchor target="_blank" href="/marketers/docs/raw-data-field-dictionary">data fields dictionary</Anchor> for more details about these parameters.

The following table describes the raw data parameters available in ARS and VIAP events.

| Parameter | Remarks | Product |
| --- | --- | --- |
| af\_cancelation\_date\_ms | Date of the cancelation | IAP |
| af\_cuids | <ul><li>In the context of ARS, this parameter contains an array with all CUIDs.</li><li>The array of CUIDs displays irrespective of the device IDs. Thus, the same CUIDs can display for more than one device ID.</li></ul> | Subscription |
| af\_discount\_id | The offer ID presented to the user during the initial purchase. The ID is populated only when there is a discount code. | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_discount\_type | The discount type redeemed by the user. Possible values:<ul><li>IOS<ul><li>introductory</li><li>promotional</li><li>offer\_codes</li><li>win\_back</li></ul></li><li>Android<ul><li>intro price</li><li>one\_time\_code</li><li>vanity\_code</li></ul></li></ul> | Subscription |
| af\_environment | The environment from which data is received, either production or sandbox. | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_expires\_date\_ms | The expiration date of the current subscription billing cycle | Subscription |
| af\_net\_revenue | Net revenue calculated based on all factored reasons. See af\_net\_revenue\_factors. | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_net\_revenue\_country | <ul><li><Anchor target="_blank" href="https://www.nationsonline.org/oneworld/country_code_list.htm">Two-letter ISO country code</Anchor> for which the tax is applied.</li><li>Example: CA</li><li>Note: For United Kingdom, the code implemented is UK, not GB.</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_net\_revenue\_factors | <ul><li>An array representing all factored reasons that produce the reported af\_net\_revenue amount.</li><li>Example value: store\_commission</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_net\_revenue\_postal\_code | <ul><li>String of letters and/or numbers</li><li>Example: L4J8E3</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_net\_revenue\_subdivision | <ul><li>For some countries, there can be an additional state or subdivision. This is handled according to <Anchor target="_blank" href="https://service.unece.org/trade/locode/2023-1%20SubdivisionCodes.htm">ISO 3166-2 subdivision codes</Anchor>.</li><li>Includes the country code and subdivision code.</li><li>Example: US-CA</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_net\_revenue\_tax\_exclusive | <ul><li>Boolean parameter, either true or false.</li><li>False means tax is included in the overall revenue.</li><li>True means tax is in addition to the overall stated revenue.</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_net\_revenue\_tax\_name | <ul><li>Name appearing in the customer invoice that describes the specific type of tax.</li><li>Example: Sales, VAT, GST</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_net\_revenue\_tax\_rate | <ul><li>Number up to 4 decimal places representing the tax percentage collected.</li><li>Example: 7.25</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_offer\_id | <ul><li>The offer ID applied to the transaction, when relevant (for example, discounted or promotional offers).</li><li>Android only</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_order\_id | <ul><li>The order ID for the transaction</li><li>Android only</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_original\_transaction\_id | <ul><li>The original transaction ID</li><li>iOS only</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_original\_transaction\_id | <ul><li>The original ID of the transaction</li><li>iOS only</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_period\_type | <ul><li>Subscription or trial period type.</li><li>Possible values:<ul><li>trial</li><li>intro</li><li>normal</li></ul></li></ul> | Subscription |
| af\_product\_id | The subscription product ID | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_purchase\_date\_ms | The purchase date for the reported product ID in-app event | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_purchase\_option\_id | <ul><li>The purchase option ID associated with the transaction.</li><li>Android only</li></ul> | IAP |
| af\_purchase\_option\_type | The purchase option type of the transaction. Possible values (Android):<ul><li>buy</li><li>rent</li></ul> | IAP |
| af\_purchase\_state | Possible values:<ul><li>Purchased</li><li>Canceled</li><li>Pending</li></ul> | IAP |
| af\_purchase\_token | <ul><li>The purchase token for the transaction</li><li>Android only</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_reason | [content unchanged] | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_refunded\_transaction\_ids | <ul><li>An array of all refunded transaction IDs</li><li>iOS only</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_store | The app store the subscription product was purchased from | <ul><li>IAP</li><li>Subscription</li></ul> |
| af\_subscription\_ownership\_type | FAMILY\_SHARED means the user has access via family sharing. PURCHASED means the paying user made the purchase. | Subscription |
| af\_transaction\_id | <ul><li>The ID of the transaction</li><li>iOS only</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |
| store\_commission | <ul><li>The calculated percentage of commission the store gets from the purchased product.</li><li>Displayed as a decimal.</li><li>Example: 30</li></ul> | <ul><li>IAP</li><li>Subscription</li></ul> |

</Accordion>

<div id="true-revenue" />

<Accordion title="Net revenue">

Net revenue is a business logic layer built to serve the ROI360 Store revenue solution. It automatically calculates the net revenue value for each incoming transaction in real time and includes it in reports.

> 📘 **Note**
>
> Net revenue is displayed in raw data reports and can be sent in real time via in-app event postbacks. It is also available in <Anchor target="_blank" href="/marketers/docs/my-dashboards">My Dashboards</Anchor> as the Net metrics (Net revenue, Net ROI, Net ROAS, Net ARPU, Net profit).
>
> To send net revenue in postbacks, configure the in-app event with the **Values, revenue & net revenue option**. See <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks">In-app event postback configuration</Anchor> for details.

> 📘 **Tip**
>
> You can also configure your in-app event postbacks to send net revenue instead of gross revenue for the standard revenue (monetary) parameter. To get access to this configuration, contact your Customer Success Manager (CSM).

Net revenue considers the following factors in the gross-to-net revenue calculation:

* **Store commission**:
  * It is calculated and reported automatically. No action is required on your part.
  * For purchases (IAP), the default store commission depends on the storefront:
    * App Store — Japan and EU countries: 26%. China mainland (CN): 25%. Rest of the world: 30%.
    * Play Store: 30%.
  * For subscriptions, the commission is automatically calculated per subscriber, based on the subscriber's lifetime.
    * App Store — first 12 months: 26% in Japan and EU countries, 25% in China mainland (CN), 30% in the rest of the world. From the 13th month: 15% in Japan, 12% in China mainland (CN), 15% in the rest of the world.
    * Play Store: 15% from day one.
  * Related net revenue parameters are available in raw data reports.
  * Use <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">the Net revenue API</Anchor> to set a different store commission rate than the default. This is useful, for example, if your app is enrolled in Apple's Small Business Program, where the commission rate is 15% (12% in China mainland (CN)).
* **Tax**:
  * Tax is reported by default for any transaction measured by ROI360 using the default tax rate configuration.
  * This applies to tax-inclusive countries (where tax is included in the list price). So, for example, in the UK, AppsFlyer deducts the sum of the tax and the store commission. For tax-exclusive countries, such as the USA, where the list price does not include tax, revenue and net revenue parameters do not include tax by default.
  * The configuration can be edited using <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">the Net revenue API</Anchor>. To learn which countries are supported and their default tax rates, see <Anchor target="_blank" href="https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub">this JSON file</Anchor>. The developer can edit it or use it as-is in the API.

When viewing net revenue in reports, the following parameters contain the net revenue data. See the [parameter dictionary](#parameter-dictionary) for more details.

| Parameter | Net revenue factor |
| --- | --- |
| `store_commission` | Store commission |
| `af_net_revenue_tax_name` | Tax |
| `af_net_revenue_tax_rate` | Tax |
| `af_net_revenue_tax_exclusive` | Tax |
| `af_net_revenue_postal_code` | Tax |
| `af_net_revenue_country` | Tax |
| `af_net_revenue_subdivision` | Tax |
| `af_net_revenue` | <ul><li>Store commission</li><li>Tax</li></ul> |
| `af_net_revenue_factors` | <ul><li>Store commission</li><li>Tax</li></ul> |

</Accordion>

<div id="troubleshooting-and-disprepancies" />

<Accordion title="Troubleshooting and discrepancies">

| Symptom | Explanation / Solution |
| --- | --- |
| AppsFlyer shows fewer in-app purchase and subscription events than the actual app stores. | In AppsFlyer, events are generated only for users who have updated to an app version that includes the SDK connector. Meanwhile, the app stores log every event, regardless of the user's app version. As a result, until the updated app version is fully adopted, a discrepancy between the app's revenue data and the store's data is expected. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Specification | Product | Remarks |
| --- | --- | --- |
| Installment subscriptions (Android) | Subscription revenue | Not supported |
| Subscription pending  <br />transactions (Android) | Subscription revenue | Not supported |
| New subscriptions | Subscription revenue | Only recorded via the AppsFlyer purchase SDK |
| Price change | Subscription revenue | If subscription revenue doesn't receive an SDK-generated notification with the new product price, it continues to report the previous product price as revenue. Once the new product price is received from the purchase SDK, it is recorded. |
| Gross revenue | <ul><li>IAP</li><li>Subscription revenue</li></ul> | Supported |
| Net revenue | <ul><li>IAP</li><li>Subscription revenue</li></ul> | Supported in raw data and in My Dashboards (as the Net metrics) |
| Refunds | IAP | Can be reported until 180 days after the original purchase. |
| Deduplication | <ul><li>IAP</li><li>Subscription revenue</li></ul> | Supported for transactions reported up to 180 days after the event date. |
| SDK strict mode | <ul><li>IAP</li><li>Subscription revenue</li></ul> | ROI360 subscriptions and IAP are supported under SDK strict mode from the:<ul><li>AppsFlyer iOS purchase SDK connector V6.13.0</li><li>Unity purchase SDK connector V2.0.1</li></ul> |
| Currency | <ul><li>IAP</li><li>Subscription revenue</li></ul> | Revenue is reported in the original currency (using the event\_revenue parameter) and in USD (using the event\_revenue\_usd parameter). |
| Data freshness | <ul><li>IAP</li><li>Subscription revenue</li></ul> | <ul><li>Transaction-level store revenue report: Hourly</li><li>Device-level store revenue report: Every 8 hours</li></ul> |
| StoreKit 2 | <ul><li>IAP</li><li>Subscription revenue</li></ul> | <ul><li>StoreKit 2 is supported starting with Purchase SDK Connector version 6.16.2.</li><li>Make sure your app uses the updated App Store credentials described <Anchor target="_blank" href="/marketers/docs/bulletin-update-app-store-credentials-for-ios-roi360-receipt-validation">here</Anchor>.</li></ul> |
| Google one-time products | IAP | <ul><li>Supported purchase options: Buy and Rent</li><li>Pre-order: Not supported</li></ul> |

</Accordion>

<div data-zendesk-anchors="h_01KSAJW61CZZBWBQ112VR5095C=important h_01KD0W3J6105033NV6FYKGQ8BQ=warning h_01KD2JZQ0JYVF8S1E2W3N91KYV=how-does-roi360-store-revenue-work enable-roi360-store-revenue=activate-roi360-store-revenue h_01KD2JZQ0JS9YQ2SPNN6NHAJEH=activate-roi360-store-revenue h_01KD2JZQ0JD53598CES8ECAHR3=set-up-roi360-store-revenue h_01JKWGTJQY938NV6VCJ7KKS23E=reference h_01KD6B3KC75RFDV08G9RT1BX1M=note h_01HDEPSK8DFQ24EZ5T0EPBSVS4=iaprelated-events-and-parameters 01H8VJJP1ER9N6BPAES8H8CK4T=purchase-af_purchase h_01J50N58GYF2BYC57HA7THSWW6=purchase-af_purchase_free 01H8VJJP1EXYE1EQS08CK8BG02=purchase-canceled-af_purchase_canceled 01H8VJJP1ET5TAAQ17EMK6TVRE=purchase-pending-af_purchase_pending 01H8VJJP1E8JKPGT2V9CCB1XW8=refund-af_purchase_refund 01H8VJJP1ECQMS49M8Z1X1FT4B=test-purchase-af_purchase_sandbox_sdk 01H8VJJP1E3X7YZNYT5D8REVEW=test-purchase-af_purchase_sandbox_s2s h_01HDEQBACTTPZ04YYD1KV49SEZ=subscriptionrelated-events-and-parameters 01H8VJJP1EHAZBGT82WRWB00JT=trial-started-af_ars_trial_started 01H8VJJP1ETCHTK6JMK9ERS5A5=trial-canceled-af_ars_trial_canceled 01H8VJJP1EC45X8PJVPWT3G7S3=trial-churned-af_ars_trial_churned 01H8VJJP1EYPQM50JVX1KPZXAZ=trial-converted-af_ars_trial_converted 01H8VJJP1EA4WTCEJWBB1HPRJF=subscription-started-af_ars_subscription_started 01H8VJJP1EF744NE425Y30VG0M=subscription-canceled-af_ars_subscription_canceled 01H8VJJP1EMKBP27070NRR9CZ5=subscription-paused-af_ars_subscription_paused-android-only 01H8VJJP1EGHNQ35JM1TWV4ND0=subscription-resumed-af_ars_subscription_resumed 01H8VJJP1EM2GJ28VBE6V76SBG=subscription-churned-af_ars_subscription_churned 01H8VJJP1E28XXAQSGZ9PYDT08=subscription-refunded-af_ars_subscription_refunded 01H8VJJP1E399B2AVWP9VKZ0D4=subscription-billing-grace-af_ars_subscription_billing_grace 01H8VJJP1EEZZ0DE75VXAZQP3E=subscription-renewed-af_ars_subscription_renewed 01H8VJJP1FGXHRK3J0XB2G4PCQ=subscription-changed-af_ars_subscription_xgraded 01H8VJJP1FKC8KZ2HKJVGZEV23=existing-subscriber-af_ars_existing_subscriber 01H8VJJP1F720QT97Q0TW4SEM2=test-purchase-af_ars_sandbox_sdk 01H8VJJP1FSRHG26EXMEG3325P=test-purchase-af_ars_sandbox_s2s 01H8VJJP1F0ZV2PX39D9JCG6B4=parameter-dictionary 01H8VJJP1FF219YN3XHRCGW7Z3=true-revenue h_01KBFWTM4XJ417930YVDD36ASK=note-1 h_01KRKEP613DR8RZ5Q2A5H7KZAH=tip 01JHZG8FFHTYE2PMRWWS8WNR6X=troubleshooting-and-disprepancies 01H8VJJP1FP2MPRF8AN77REXD0=traits-and-limitations" />
