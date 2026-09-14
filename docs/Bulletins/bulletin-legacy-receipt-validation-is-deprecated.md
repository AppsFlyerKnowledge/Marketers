---
title: "Bulletin: Legacy Receipt validation is deprecated"
excerpt: "AppsFlyer is sunsetting its legacy Receipt validation backend service on September 7, 2026, requiring apps to migrate to either the new Receipt validation or ROI360 Store Revenue."
---
On September 7, 2026, AppsFlyer will stop supporting the legacy Receipt validation backend service. Starting from this date, any app calling the legacy `validateAndLogInAppPurchase` method, regardless of SDK version, will receive no validation response, and `af_purchase` events validated and logged by that method will no longer be recorded in AppsFlyer.

In addition, the legacy method will be removed from the SDK starting from AppsFlyer SDK v7.0.0. Apps that upgrade to v7.0.0 or later will not be able to call the legacy method.

To continue measuring validated purchases, AppsFlyer provides two alternatives:
- **Receipt validation**, a free solution that validates purchases with the app stores using the new `validateAndLogInAppPurchase` (v2) SDK method.
- **ROI360 Store Revenue**, a premium revenue measurement solution that includes refund tracking, full subscription lifecycle visibility, and net revenue calculation.

### Key Information

| Section | Details |
| --- | --- |
| **Effective date** | The following dates apply:<br>- Update date: June 17, 2026<br>- Full sunset date: September 7, 2026 |
| **What you need to know** | - **Onboarding is now required.** Unlike Legacy, the new Receipt validation only works after the product type and store credentials are configured in AppsFlyer. Without this setup, the SDK returns an error.<br>- **Gross revenue replaces custom revenue values.** The new Receipt validation records the gross revenue returned by the store, not the value you pass in the SDK call. If you previously passed a custom value (for example, net after store fee deduction), expect a difference in dashboards and partner postbacks after migration. For net revenue, use ROI360 Store Revenue.<br>- **Dashboards and postbacks use only the price and currency from the store validation response.** Unlike Legacy, the new `validateAndLogInAppPurchase` does not accept price or currency in the SDK call. These values are extracted directly from the store validation response. Any `af_revenue` you pass as an additional parameter lands in the event's `custom_data` object but is not used for dashboards or postbacks.<br>- **New mandatory parameter:** `PurchaseType`. Tells the SDK whether the transaction is a one-time purchase or a subscription. |
| **What you need to do** | To migrate to one of the two solutions (before September 7, 2026), perform one of the following:<br>- [Set up Receipt validation](/docs/set-up-receipt-validation) (includes a section for customers migrating from Legacy)<br>- [Set up ROI360 store revenue](https://support.appsflyer.com/hc/articles/42158608158353)<br>For more information, see:<br>- [A side-by-side comparison of Receipt validation and ROI360 Store Revenue](/docs/purchase-and-subscription-validation-overview#compare-receipt-validation-and-roi360-stores-revenue)<br>- The FAQ below |

## FAQ

<Accordion title="How do I know which of my apps still use Legacy Receipt validation?">

Legacy does not appear as a product type in the Revenue settings page, so you cannot confirm Legacy usage from the UI alone. Use the following methods together:

- **Scan raw data first.** Look for `af_purchase` events with `event_source: SDK` and `is_receipt_validated: true`. These are candidates, but `logEvent` calls can produce similar events, so this is not conclusive on its own.
- **Confirm in the SDK code.** If your app calls `validateAndLogInAppPurchase` with the legacy signature, it is on Legacy. The legacy signature includes:
  - **Android:** license key, JSON payload, price, currency
  - **iOS:** product ID, price, currency, transaction ID
- **Contact your CSM.** They can confirm which of your apps are still on Legacy.

</Accordion>

<Accordion title="What exactly happens on September 7, 2026?">

The Legacy Receipt validation backend service shuts down. From that day:

- Any call to the legacy `validateAndLogInAppPurchase` method returns no validation response, regardless of SDK version.
- `af_purchase` events validated and logged by that method are no longer recorded in AppsFlyer.
- Dashboards, raw data, and partner postbacks no longer receive purchase data from Legacy.

To keep capturing validated purchases, migrate to one of the supported alternatives before September 7, 2026.

</Accordion>

<Accordion title="Will enabling the new Receipt validation affect my live app versions that still call the legacy method?">

No. The two products run in parallel until September 7, 2026. Enabling the new Receipt validation in AppsFlyer has no effect on app versions that still call the legacy method. They continue to work as before until the sunset date.

</Accordion>

<Accordion title="What happens to users on old app versions that never get updated?">

Users on old app versions continue to generate validated `af_purchase` events until September 7, 2026. To continue getting validated purchase data, release your updated app version with enough lead time to reach most of your user base before the sunset.

</Accordion>

<Accordion title="Can I switch from Receipt validation to ROI360 Store Revenue later?">

Yes. Both products use the same `validateAndLogInAppPurchase` (v2) SDK method, so switching from Receipt validation to ROI360 Store Revenue does not require an SDK change or app release. To switch, change the **Product type** on the **Revenue settings** page and complete the additional ROI360 setup (App Store server notifications for iOS, Google Play RTDN for Android). See [Switch to ROI360 Store Revenue from Receipt validation](/docs/set-up-roi360-store-revenue#switch-to-roi360-store-revenue-from-receipt-validation).

If you want to go further and enable automatic purchase detection, full subscription lifecycle coverage (including renewals, upgrades, and existing subscribers), and subscription price-change handling, integrate the **Purchase Connector** SDK component. That's an app update, but it's optional. The manual `validateAndLogInAppPurchase` (v2) flow works in ROI360 Store Revenue without it.

</Accordion>

<Accordion title="Can I skip AppsFlyer purchase validation entirely?">

Yes. You can report in-app purchase events with the standard `logEvent` API. But you'll miss out on:

- Receipt validation against the app stores, which filters out fraudulent purchases
- The `af_validated` flag on events: set to `true` when AppsFlyer successfully verifies the purchase with the store, `false` when it fails. Without validation, this flag is absent.
- Accurate revenue postbacks to your UA partners. Without validation, any `af_revenue` you pass is recorded and sent to networks as-is, with no confirmation that the purchase actually occurred

For these reasons, AppsFlyer recommends using either Receipt validation or ROI360 Store Revenue rather than skipping validation entirely.

</Accordion>

<Accordion title="What happens if Apple's or Google's validation service has an outage?">

It depends on which product you use:

- **Receipt validation:** the SDK callback returns an error code. Your app needs to handle the failure and implement its own retry logic.
- **ROI360 Store Revenue:** AppsFlyer retries validation automatically once the store service recovers, and regenerates any missed events for the outage window.

</Accordion>

<Accordion title="Why did my dashboard revenue change after migration?">

The revenue source changed. Legacy used the value you passed in the SDK call. The new Receipt validation uses the gross revenue returned by the store. If you previously passed a custom value, for example net revenue after store fee deduction, your dashboards and partner postbacks will reflect a different number after migration.

If you need net revenue, use **ROI360 Store Revenue**. It records both gross and net (gross minus store fees and taxes).

</Accordion>

<Accordion title="What happens to my custom af_revenue value?">

If you still pass the `af_revenue` value, it's preserved on the event inside the `custom_data` object. Dashboards and partner postbacks use the gross value from the store response, not your custom value.

</Accordion>

<Accordion title="Will my partners see the new gross revenue in postbacks?">

Yes. After migration, `af_purchase` postbacks carry the gross revenue from the store. If you previously passed a custom value under Legacy, your partners will see a different number. Make sure to inform your UA partners before rolling out the migration, especially those partners that use revenue data for campaign optimization.

</Accordion>

<Accordion title="How do event names change after migration?">

Legacy produced a single `af_purchase` event for all transaction types. The new Receipt validation uses distinct event names:

- One-time purchase: `af_purchase`
- Trial start: `af_ars_trial_started`
- Subscription start: `af_ars_subscription_started`
- Sandbox purchase: `af_purchase_sandbox_sdk`
- Sandbox subscription or trial: `af_ars_sandbox_sdk`

Full subscription lifecycle events (renewals, cancellations, refunds, upgrades) are only available in ROI360 Store Revenue. For the full event list, see [About Receipt validation](https://support.appsflyer.com/hc/articles/42136725767569).

</Accordion>

<Accordion title="Can I use the SDK validation response to control access to purchased content?">

The new Receipt validation still returns a validation result to your SDK callback that you can use to control access to purchased content. The result is more accurate because it relies on the latest validation mechanisms provided by the Apple App Store and Google Play, so the signal you receive in the callback is more trustworthy.

</Accordion>

<Accordion title="How does the new method distinguish between subscriptions and one-time purchases?">

The new `validateAndLogInAppPurchase` requires a mandatory `PurchaseType` parameter. Set it to `one-time` or `subscription` based on the transaction type.

</Accordion>

<Accordion title="Why is the SDK returning &quot;Purchase validation is not enabled for this app in AppsFlyer&quot;?">

Your app has integrated the new `validateAndLogInAppPurchase` (v2) method, but the product isn't configured in the AppsFlyer dashboard. Open **Settings > ROI360 > Revenue settings > Purchases & subscriptions**, select either **Receipt validation** or **ROI360**, and complete the setup steps.

</Accordion>

<Accordion title="Why is my new SDK build only logging sandbox events, not af_purchase?">

`af_purchase` is logged only for production transactions. Sandbox transactions are logged as `af_purchase_sandbox_sdk`. To produce a real `af_purchase` event, test through a production pipeline (non-TestFlight on iOS, non-Licensed Tester on Android).

</Accordion>