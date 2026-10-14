---
title: "About Receipt validation"
excerpt: "Understand how Receipt validation measures revenue from in-app purchases and subscriptions and verifies it with the app stores, ensuring accurate revenue measurement."
x-zendesk:
  id: 42136725767569
  url: https://support.appsflyer.com/hc/en-us/articles/42136725767569-About-Receipt-validation
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Purchase and subscription validation
  section_id: 42227328788241
  position: 1
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-michael-talapov, Marketers, ROI360]
  labels: []
  promoted: false
  comments_disabled: false
  created_at: '2025-12-21T14:32:24Z'
  edited_at: '2026-08-13T14:26:38Z'
---
Advertisers can use Receipt validation to validate and measure in-app purchases and subscriptions from the Play Store and the App Store.

Receipt validation is free of charge to all account plans.

Consider using our premium ROI360 store revenue solution to benefit from net revenue calculation, full subscription funnel coverage, refund handling, and automated purchase detection & deduplication. For more information and a comparison between the two solutions, see The two solutions for purchase and subscription validation.

## How does Receipt validation work?

The receipt validation flow is as follows:

1. The user performs an in-app purchase.
2. The app store notifies the app of the successful purchase.
3. The app developer calls the SDK's receipt validation method: `validateAndLogInAppPurchase`
4. The SDK calls the AppsFlyer validation service.
5. AppsFlyer validates the purchase to make sure it is not fraudulent.
6. Upon successful validation, AppsFlyer logs the purchase or subscription event.
7. If receipt validation fails, the event is displayed in the [Blocked in-app events raw data report](/docs/protect360-raw-data-reports#blocked-inapp-events) (available to Protect360 subscribers) and on the [Live events viewer page](/docs/testing-the-sdk-integration-for-marketers#view-live-events) with the parameter `af_validated` set to `false`.
8. The AppsFlyer validation service transfers the response to the SDK.
9. The SDK transfers the receipt validation response to the app (either success or failure).

## Activate Receipt validation

To activate Receipt validation, follow these steps:

1. In AppsFlyer, from the side menu, open **Settings** and under **ROI360** select **Revenue Settings**.
2. Open the **Purchases & subscriptions** tab.
3. Under **1 Choose Product type**, select **Receipt validation**.
4. Click **Save and next** to proceed to set up Receipt validation.

## Set up Receipt validation

For more information, see [Set up receipt validation](/docs/set-up-receipt-validation)[.](/docs/set-up-receipt-validation#step-3-verify-sdk-implementation)

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

## Switch from ROI360 store revenue to Receipt validation

If you currently use ROI360 store revenue and want to switch to Receipt validation, follow these steps:

1. In AppsFlyer, from the side menu, open ![settings-roi.png](https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png) **Settings** and under **ROI360** select **Revenue Settings**.
2. In the **Purchases & subscriptions** tab, confirm that the **Product type** is currently set to **ROI360**.
3. Click ![Untitled 3.png](https://files.readme.io/5f58109e6a7f7d2d3958a05e3da1aaa99d5d104c09346240ae7d20f48047afc6-42137388748177.png).
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

## Traits and limitations

| Trait | Remark |
| --- | --- |
| Supported stores | • Play Store  <br />• App Store  <br />• For any other (third-party) stores, you must manually send in-app purchase events. |
| iOS sandbox apps | For iOS sandbox apps, meaning apps that are not live in the App Store, 'Validate the Key' will always display invalid status |