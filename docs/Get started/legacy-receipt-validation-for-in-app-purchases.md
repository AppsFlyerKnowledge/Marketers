---
title: "[Legacy] Receipt validation for in-app purchases"
excerpt: "Learn how the legacy receipt validation flow works to protect against fraudulent in-app purchases in iOS and Android app stores."
---
> 🚧 Important!
>
> This article describes the deprecated Receipt validation feature. For more information, see [Bulletin: Legacy Receipt validation is deprecated](https://support.appsflyer.com/hc/articles/42133487071121-Bulletin-Legacy-Receipt-Validation-is-deprecated)

**At a glance:** Implement receipt validation to protect against fraudulent in-app purchases made in iOS and Android app stores, and make sure an in-app purchase occurred as reported. **Note**: This is a legacy feature. Learn more about the new, fully automatic, and improved [in-app purchase validation mechanism](https://support.appsflyer.com/hc/articles/42120228484241).

## Receipt validation flow

The receipt validation flow is as follows:

1. The user performs an in-app purchase.
2. The app store notifies the app of the successful purchase.
3. The app developer calls the SDK Receipt Validation function.

```auto
validateAndLogInAppPurchase
```

4. The SDK calls the AppsFlyer validation service.
5. AppsFlyer validates the purchase to make sure it is not fraudulent.
6. Upon success, AppsFlyer internally creates a regular af_purchase event. Otherwise, the created event is marked as fraudulent (available via Protect360).
7. The AppsFlyer validation service transfers the response to the SDK.
8. The SDK transfers the receipt validation response to the app (either success or fail).

If receipt validation fails, the event displays in the [blocked in-app events raw-data](https://support.appsflyer.com/hc/articles/360015179337#inapp-level-blocked-reasons) report (available to Protect360 subscribers).

For details about the implementation of receipt validation, see our developer SDK documentation:

- [Android](https://dev.appsflyer.com/hc/docs/in-app-events-android#validating-purchases)
- [iOS](https://dev.appsflyer.com/hc/docs/in-app-events-ios#purchase-validation-using-validateandloginapppurchase)

**Notes:**

- For iOS sandbox apps, meaning apps that are not live in the App Store, receipt validation requires [some additional code](https://dev.appsflyer.com/hc/docs/validate-and-log-purchase-ios#testing-purchase-validation-in-sandbox-mode).
- Purchases made in the sandbox environment are recorded as regular af_purchase events, and their revenue is reflected in AppsFlyer dashboards and reports.
- The AppsFlyer receipt validation service is free of charge to all account plans.
- For Android, receipt validation may return a `null` result and consider the validation failed if the end user doesn't have internet access during the purchase.

> 🚧 Important!
>
> Calling `validateAndLogInAppPurchase` also generates an **af_purchase** in-app event. As such, don't generate an af_purchase event when validating. Doing so results in duplicate revenue events.

> 📘 Note
>
> - The legacy receipt validation explained here does not support _StoreKit v2_. For the current version, see [Set up integration with iOS App Store.](https://support.appsflyer.com/hc/articles/7459048170769-Set-up-in-app-purchase-and-subscription-revenue-measurement#step-2-set-up-notifications-from-the-ios-app-store)
> - Receipt validation for in-app purchases isn't supported for third-party Android app stores.