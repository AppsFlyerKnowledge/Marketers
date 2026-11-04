---
title: About Receipt validation
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T14:32:24Z'
  edited_at: '2026-08-13T14:26:38Z'
  id: 42136725767569
  locale: en-us
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/42136725767569-About-Receipt-validation
---
> **At a glance:** Understand how Receipt validation measures revenue from in-app purchases and subscriptions and verifies it with the app stores, ensuring accurate revenue measurement.

Advertisers can use Receipt validation to validate and measure in-app purchases and subscriptions from the Play Store and the App Store.

Receipt validation is free of charge to all account plans.

<div id="note" />

> 📘 **Note**
>
> Consider using our premium ROI360 store revenue solution to benefit from net revenue calculation, full subscription funnel coverage, refund handling, and automated purchase detection & deduplication. For more information and a comparison between the two solutions, see The two solutions for purchase and subscription validation.

<div id="how-does-receipt-validation-work" />

## How does Receipt validation work?

The receipt validation flow is as follows:

1. The user performs an in-app purchase.
2. The app store notifies the app of the successful purchase.
3. The app developer calls the SDK's receipt validation method: `validateAndLogInAppPurchase`
4. The SDK calls the AppsFlyer validation service.
5. AppsFlyer validates the purchase to make sure it is not fraudulent.
6. Upon successful validation, AppsFlyer logs the purchase or subscription event.
7. If receipt validation fails, the event is displayed in the <Anchor target="_blank" href="/marketers/docs/protect360-raw-data-reports#blocked-inapp-events">Blocked in-app events raw data report</Anchor> (available to Protect360 subscribers) and on the <Anchor target="_blank" href="/marketers/docs/testing-the-sdk-integration-for-marketers#view-live-events">Live events viewer page</Anchor> with the parameter `af_validated` set to `false`.
8. The AppsFlyer validation service transfers the response to the SDK.
9. The SDK transfers the receipt validation response to the app (either success or failure).

<div id="activate-receipt-validation" />

## Activate Receipt validation

To activate Receipt validation, follow these steps:

1. In AppsFlyer, from the side menu, open **Settings** and under **ROI360** select **Revenue Settings**.
2. Open the **Purchases & subscriptions** tab.
3. Under **1 Choose Product type**, select **Receipt validation**.
4. Click **Save and next** to proceed to set up Receipt validation.

<div id="set-up-receipt-validation" />

## Set up Receipt validation

For more information, see <Anchor target="_blank" href="/marketers/docs/set-up-receipt-validation">Set up receipt validation</Anchor><Anchor target="_blank" href="/marketers/docs/set-up-receipt-validation#step-3-verify-sdk-implementation">.</Anchor>

<div id="in-app-purchase-events-and-parameters-for-receipt-validation" />

## In-app purchase events and parameters for Receipt validation

All predefined events share the following properties:

* They are processed as S2S events.
* They are available in the dashboards and raw data reports as organic or non-organic in-app events.
* They can be sent via postbacks to partners.
* They can be used in SKAN Conversion Studio.

**The events recorded for in-app purchases are:**

* `af_purchase` - Production
* `af_purchase_sandbox_sdk` - Sandbox

**Subscription events:**

* `af_ars_trial_started` - Subscription with the trial period started.
* `af_ars_subscriptions_started` - Paid subscription (without trial period) started, production
* `af_ars_sandbox_sdk` - Trial or paid subscription started, sandbox

**The event includes the following predefined parameters:**

* `af_product_id`
* `af_transaction_id` (iOS only)
* `af_purchase_token` (Android only)
* `af_revenue` (for sandbox events - `af_sandbox_revenue`)
* `af_currency`
* `af_store` (app\_store / play\_store)
* `af_environment` (sandbox/production)
* `af_validation_type` (receipt\_validation)

**Additional custom parameters:**

* Any additional custom parameters sent in the SDK call will appear in the`custom_data` field in raw data reports

<div id="switch-from-roi360-store-revenue-to-receipt-validation" />

## Switch from ROI360 store revenue to Receipt validation

If you currently use ROI360 store revenue and want to switch to Receipt validation, follow these steps:

1. In AppsFlyer, from the side menu, open <Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.02%" /> **Settings** and under **ROI360** select **Revenue Settings**.
2. In the **Purchases & subscriptions** tab, confirm that the **Product type** is currently set to **ROI360**.
3. Click <Image alt="Untitled 3.png" src="https://files.readme.io/5f58109e6a7f7d2d3958a05e3da1aaa99d5d104c09346240ae7d20f48047afc6-42137388748177.png" width="2.07%" />.
4. A message appears outlining the impact of switching to Receipt validation:
   * ROI360 features such as refund attribution, subscription renewal measurement, and net revenue calculations will be disabled.
   * Data accuracy may decrease.
   * The Purchase Connector is not supported in Receipt Validation.
   * Only the `validateAndLogInAppPurchase` SDK method is supported.
5. Review the comparison table, if needed, by clicking '**View product comparison'**.
6. If you still want to proceed, click **Switch** to confirm the change.
7. After switching, the **Product type** updates to **Receipt validation,** and the screen reflects the simplified configuration.
8. You’ll need to revalidate the following:
   * **SDK implementation** for the validateAndLog method

<div id="traits-and-limitations" />

## Traits and limitations

| Trait | Remark |
| --- | --- |
| Supported stores | • Play Store  <br />• App Store  <br />• For any other (third-party) stores, you must manually send in-app purchase events. |
| iOS sandbox apps | For iOS sandbox apps, meaning apps that are not live in the App Store, 'Validate the Key' will always display invalid status |

<div data-zendesk-anchors="h_01KD0PBEK0M2NEZJ95QXBA1H3W=how-does-receipt-validation-work enable-receipt-validation=activate-receipt-validation h_01KD0PBEK0BZNW8YP02EW0DHH4=activate-receipt-validation h_01KD0PBEK1GZSJQPTP0P2TJMNJ=set-up-receipt-validation inapp-purchase-events-and-parameters-for-receipt-validation=in-app-purchase-events-and-parameters-for-receipt-validation h_01KD0PBEK1DVMRXR64EMSWT75W=in-app-purchase-events-and-parameters-for-receipt-validation h_01KD0PBEK1AKE1XM2XVTCNTJ68=switch-from-roi360-store-revenue-to-receipt-validation h_01KD0PBEK1HQKTGM7JP2KYPJAR=traits-and-limitations" />
