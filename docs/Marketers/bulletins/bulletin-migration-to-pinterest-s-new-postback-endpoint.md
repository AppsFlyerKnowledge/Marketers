---
title: "Bulletin: Migration to Pinterest’s New Postback Endpoint"
excerpt: "Pinterest has migrated to a new endpoint based on their Conversions API (CAPI) infrastructure, requiring an upgrade to continue sending app events."
---
## What’s New

Pinterest has migrated to a new endpoint based on their Conversions API (CAPI) infrastructure. You must upgrade in order to continue to send your app events to Pinterest. We will be deprecating the old endpoint on September 30, 2025.

* **Effective Date:** 07/23/2025

## What you need to know

This bulletin includes information relating to the migration phase to CAPI. For general information about the Pinterest integration see [the KB article](https://support.appsflyer.com/hc/articles/216912786-Pinterest-campaign-configuration#inapp-events-settings).

Updating to the new API In-app events settings will ensure Pinterest measurement will continue without interruption, and it also includes:
- **More “events” types**: Track additional events to better align with your goals, such as: Lead, Search, Category Viewed, Page Visit, and more.
- **Improved data quality:** Benefit from enhanced matching and stronger attribution accuracy.

> 📘 Event Names Have Changed
>
> Event names for the new Pinterest V5 endpoint are different. Unless the dashboard is updated accordingly, events report will display “unknown”. Please review the new event names below.

The new integration requires both an **Ad Account ID** and an **Access Token**. To maintain postback functionality, partners must transition to the new postback endpoint by 9/30/25.

### How to find Pinterest AppsFlyer Ad Account ID

You can find the current AppsFlyer Pinterest Conversion reporting Ad Account ID in Pinterest **Business Manager** or Pinterest **Conversions** reporting.

1. Log in to your Pinterest business account (you must be in a business profile to see the Hub options).
2. Type or paste `https://www.pinterest.com/business/hub/` into your browser and press Enter.
3. Look at the dark-gray navigation column on the left side of the Hub. If the column is collapsed, click the small “≡” (hamburger) icon in the upper-left corner to expand it.
4. Scroll a little until you see the section titled “Manage business.”
5. Click **Conversions** (it sits right under “Manage business”). This opens the Conversions dashboard, where you can review AppsFlyer conversions sent to Pinterest.
6. Ad Account ID will be present in the URL.
7. If multiple Pinterest Ad Account IDs receive cloned conversions from AppsFlyer, verify all existing Ad Account IDs with Conversions in Pinterest Business Manager. Please ensure the original parent Ad Account ID for AppsFlyer conversions is selected.

### How to find Pinterest AppsFlyer Access Token

Please follow the steps outlined on Pinterest’s Help Center [here](https://help.pinterest.com/en/business/article/getting-started-with-the-conversions-api). Once in Pinterest Conversions, click on **Conversions API** > **Set-up API**, and generate a new access token for the account.

> 📘 Note
>
> If you have already set-up Conversions API for Pinterest separately outside of AppsFlyer, use the same Access Token here for AppsFlyer conversions as well.

## What you need to do

Please follow the instructions below for setting up and migrating in-app event postbacks in the AppsFlyer dashboard.

### 1. In-App Event Settings and Dashboard Parameter Handling

We currently support the following dashboard parameters for mapping your Appsflyer events with Pinterest:

- **Ad Account ID** (visible)
- **Access Token** (visible)
- **Tag ID** (not visible on the dashboard, but supported in the backend to assist with the transition to the new V5 version. Once the transition to the V5 endpoint is fully supported, the Tag ID will also be removed from the backend.)

> ❗️ Important
>
> For the new postback setup, you must enter both the **Ad Account ID** and **Access Token** (these can be obtained from Pinterest if not already available). **If either of these values are missing, the postback will fail**. Kindly ensure both parameters are correctly filled in the Pinterest **Active Integration** page. For more information, see [the KB article](https://support.appsflyer.com/hc/articles/216912786-Pinterest-campaign-configuration#inapp-events-settings).

Your cooperation is important for a smooth transition. Thank you for your support.

### 2. In-App Event Mapping and Postback Settings

1. Please replace and map your current Pinterest event names with the new Pinterest Conversion API event names for the **Partner event name** section. For example, if you are currently using `pin_add_to_cart` in the Partner event section, replace that with `add_to_cart` instead. For more information see [the KB article](https://support.appsflyer.com/hc/articles/216912786-Pinterest-campaign-configuration#inapp-event-postbacks).

| event name (Legacy) | event name (new Conversions API) |
| --- | --- |
| pin_add_to_cart | add_to_cart |
| pin_purchase | checkout |
| pin_search | search |
| pin_registration | signup |
| pin_sign_up | signup |
| pin_category_view | view_category |
| add_cart | add_to_cart |
| start_checkout | checkout |
| content_view | view_category |

> 🚧 Note
>
> Failure to update the legacy event names with the correct event names for Conversions API will result in ‘Other’ showing up for event names in Pinterest, instead of the correct event name.

2. Select **in-app event postback window** to **Lifetime** so Pinterest can receive maximum number of conversions for ads optimization.
3. Select **All media sources including organic** for **To users from** so Pinterest can receive maximum number of conversions for ads optimization. For more information see [the KB article](https://support.appsflyer.com/hc/articles/216912786-Pinterest-campaign-configuration#inapp-event-postbacks).

### 3. Roll-back process in case of issues

Advertisers are advised to monitor their AppsFlyer app conversions on Pinterest to detect any issues or problems with the migration. Please give it up to 30 mins for AppsFlyer conversions data to show up in Pinterest and ensure regular monitoring for a few days to validate migration success.

Advertisers can revert to the legacy endpoint by omitting either one or both of the `account_id` and `access_token` in the integration setup.

**Behavior Rules:**

- Both `account_id` and `access_token` are absent → Postbacks are sent to the legacy (old) endpoint.
- Only `account_id` is provided (i.e., `access_token` is empty) → Postbacks are sent to the legacy endpoint.
- Only `access_token` is provided (i.e., `account_id` is empty) → Postbacks are sent to the legacy endpoint.
- Both `account_id` and `access_token` are provided → Postbacks are sent to the new endpoint.

If you are facing any issues, please reach out to AppsFlyer Support through support@appsflyer.com. For any issues on Pinterest please reach out to api-support@pinterest.com or to your Pinterest representative.