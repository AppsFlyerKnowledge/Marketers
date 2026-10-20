---
title: '[Legacy] Receipt validation for in-app purchases'
deprecated: true
metadata:
  keywords:
    - iOS
    - Android
    - Receipt
    - Validation
    - Receipt Validation
    - SDK
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
  created_at: '2015-02-26T10:30:58Z'
  edited_at: '2025-12-28T12:17:51Z'
  id: 207032106
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207032106--Legacy-Receipt-validation-for-in-app-purchases
---
> 📘 **Important!**
>
> This article describes the deprecated Receipt validation feature. For more information, see [Bulletin: Legacy Receipt validation is deprecated](/docs/bulletin-legacy-receipt-validation-is-deprecated)

**At a glance:** Implement receipt validation to protect against fraudulent in-app purchases made in iOS and Android app stores, and make sure an in-app purchase occurred as reported. **Note**: This is a legacy feature. Learn more about the new, fully automatic, and improved [in-app purchase validation mechanism](/docs/purchase-and-subscription-validation-overview).

## Receipt validation flow

The receipt validation flow is as follows:

1. The user performs an in-app purchase.
2. The app store notifies the app of the successful purchase.
3. The app developer calls the SDK Receipt Validation function.

   ```
   validateAndLogInAppPurchase
   ```
4. The SDK calls the AppsFlyer validation service.
5. AppsFlyer validates the purchase to make sure it is not fraudulent.
6. Upon success, AppsFlyer internally creates a regular af\_purchase event. Otherwise, the created event is marked as fraudulent (available via Protect360).
7. The AppsFlyer validation service transfers the response to the SDK.
8. The SDK transfers the receipt validation response to the app (either success or fail).  
   If receipt validation fails, the event displays in the [blocked in-app events raw-data](/docs/protect360-raw-data-reports#inapp-level-blocked-reasons) report (available to Protect360 subscribers).

For details about the implementation of receipt validation, see our developer SDK documentation:

* [Android](https://dev.appsflyer.com/hc/docs/in-app-events-android#validating-purchases)
* [iOS](https://dev.appsflyer.com/hc/docs/in-app-events-ios#purchase-validation-using-validateandloginapppurchase)

**Notes:**

* For iOS sandbox apps, meaning apps that are not live in the App Store, receipt validation requires [some additional code](https://dev.appsflyer.com/hc/docs/validate-and-log-purchase-ios#testing-purchase-validation-in-sandbox-mode).
* Purchases made in the sandbox environment are recorded as regular af\_purchase events, and their revenue is reflected in AppsFlyer dashboards and reports.
* The AppsFlyer receipt validation service is free of charge to all account plans.
* For Android, receipt validation may return a `null` result and consider the validation failed if the end user doesn't have internet access during the purchase.

> 📘 **Important!**
>
> Calling `validateAndLogInAppPurchase` also generates an **af\_purchase** in-app event. As such, don't generate an af\_purchase event when validating. Doing so results in duplicate revenue events.

> 📘 **Note**
>
> * *T*he legacy receipt validation explained here does not support *StoreKit v2*. For the current version, see Set up integration with iOS App Store.
> * Receipt validation for in-app purchases isn't supported for third-party Android app stores.

<div data-zendesk-anchors="h_01KDJ7QZD8X692EVP1XXGV0KY4=important 01JDSM0JDAQXH8QX8ZAXNB0ZMB=receipt-validation-flow 01JDSM0JDT6Q3WYW9K484QHY2M=important-1 01JDSM0JD90J3EDMVN6D6Z9J40=note" />
