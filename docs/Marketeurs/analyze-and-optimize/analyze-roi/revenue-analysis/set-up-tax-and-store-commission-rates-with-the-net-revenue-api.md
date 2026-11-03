---
title: Set up tax and store commission rates with the Net Revenue API
metadata:
  keywords:
    - Revenue
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
  created_at: '2024-11-28T13:57:14Z'
  edited_at: '2026-08-12T09:02:34Z'
  id: 30468586765841
  locale: en-us
  section: Revenue analysis
  section_id: 6551069075089
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/30468586765841-Set-up-tax-and-store-commission-rates-with-the-Net-Revenue-API
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Configure how AppsFlyer calculates net revenue for in-app purchases and subscriptions by using the Net Revenue API to customize store commission rates and tax rules per app. This ensures that your reports accurately reflect actual earnings, including cases with non-standard commission fees or specific tax rules.

The ROI360 store revenue product calculates the net revenue of in-app purchases and subscriptions by automatically deducting store commission and tax from gross revenue. The default configuration reflects standard commission fees and tax rules applied by the App Store and Google Play. If your store commission differs or if you operate in a country with special tax treatment, use the Net Revenue API to override the default configuration.

The Net Revenue API is implemented through two REST APIs that let you configure store commission rates and tax rules for individual apps.

* [Store commission rates](https://dev.appsflyer.com/hc/reference/post_store-commission-rates): Create, update, get, or delete store commission rates for one or more apps. Each app can have a specific commission rate based on various store programs.
* [Tax rate rules](https://dev.appsflyer.com/hc/reference/post_tax-rates-app-app-id): Create or get custom tax rate rules for a specific app.

For more information about how net revenue is calculated, see <Anchor target="_blank" href="/marketers/fr/docs/about-roi360-store-revenue#true-revenue">Net revenue</Anchor>.

> 📘 **Note**
>
> Net revenue is displayed in raw data reports and in My Dashboards as the Net metrics (Net revenue, Net ROI, Net ROAS, Net ARPU, Net profit).

## Update tax rate rules

Tax is reported by default for any transaction measured by ROI360 using the default tax rate configuration. In *tax-inclusive countries*, where tax is included in the list price, net revenue is calculated after deducting tax. For example, in the UK, AppsFlyer deducts the sum of the tax and the store commission. In *tax-exclusive countries*, such as the US, where the list price does not include tax, the revenue and net revenue parameters do not include tax by default.

To set the tax rate rules using the Net Revenue API, follow these steps:

1. Complete the following steps in your ROI360 store revenue settings:

   <div id="ios" />

   <Accordion title="iOS">

   * <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-store-revenue#step-1-ios-set-up-app-store-connect-keys">Step 1. Set up App Store Connect keys</Anchor>
   * <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-store-revenue#step-2-ios-set-up-app-store-server-notifications">Step 2. Set up App Store Server Notifications</Anchor>

   </Accordion>

   <div id="android" />

   <Accordion title="Android">

   * <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-store-revenue#step-1-android-set-up-service-account-key-and-permissions">Step 1. Set up service account key and permissions</Anchor>
   * <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-store-revenue#step-2-android-set-up-google-play-server-notifications">Step 2. Set up Google Play Server Notifications</Anchor>

   </Accordion>

2. Give your developer the following:
   * The <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">API V2 token</Anchor> to use as the authorization key.
   * The parameters and values that specify which taxes to calculate are outlined in the table that follows.
3. Instruct your developer to use the [Tax rates REST API](https://dev.appsflyer.com/hc/reference/post_tax-rates-app-app-id) to create tax rate rules. The API accepts a JSON file in the body of the POST request. [This JSON file](https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub) includes all supported countries and their default tax rates. Your developer can edit the file or use it as-is in the API.

### Tax Rate API parameters

| Parameter | Mandatory | Remarks |
| --- | --- | --- |
| `tax_name` | Yes | <ul><li>Name appearing in the customer invoice that describes the specific type of tax.</li><li>Example: Sales, VAT, GST</li></ul> |
| `tax_rate` | Yes | <ul><li>Value must be greater than 0.</li><li>Number up to 4 decimal places representing the tax percentage to be collected.</li><li>Example: 7.25</li></ul> |
| `tax_exclusive` | No | <ul><li>Boolean parameter, either true or false.</li><li>False means tax is included in the overall revenue.</li><li>True means tax is in addition to the overall stated revenue. For example, in the USA or Canada, where the list price doesn't include sales tax.</li><li>Default is false.</li></ul> |
| `country` | No | <ul><li>[Two-letter ISO country code](https://www.nationsonline.org/oneworld/country_code_list.htm) for which the tax is applied.</li><li>Example: CA</li><li>**Note:** For United Kingdom, the code implemented is UK, not GB.</li></ul> |
| `subdivision` | No | <ul><li>For some countries, there can be an additional state or subdivision.</li><li>Handled according to [ISO 3166-2 subdivision codes](https://service.unece.org/trade/locode/2022-2%20SubdivisionCodes.htm).</li><li>Must include the country code and subdivision code.</li><li>Example: US-CA</li></ul> |
| `postal_code` | No | <ul><li>String of letters and/or numbers.</li><li>Example: L4J8E3</li></ul> |
| `deduction_order` | No | <ul><li>Enum, either **0**, **1**, or **2**:<ul><li>**0** means store commission is deducted first from the gross revenue and tax is deducted from the remaining amount.</li><li>**1** means tax is deducted first from the gross revenue and store commission is deducted from the remaining amount.</li><li>**2** means that both tax and store commission are deducted from the total revenue.</li></ul></li></ul> |

## Set up store commission rates

By default, AppsFlyer applies standard store commission logic when calculating net revenue. App Store defaults are region-specific (see <Anchor target="_blank" href="/marketers/fr/docs/about-roi360-store-revenue#true-revenue">About ROI360 store revenue</Anchor> for the current rates per storefront). If your app operates under reduced or non-standard store fees, use the Net Revenue API to override the store commission rate at the app level.

A few examples:

* Your app qualifies for reduced store fees, such as:
  * Apple App Store Small Business Program (15% commission; 12% in China mainland (CN))
  * Google Play 15% service fee tier (first USD 1M in annual earnings)
* Your store commission changes over time, and because AppsFlyer has no visibility into your store commission status, you need to update the applied rate manually using the Net Revenue API, for example:
  * Applying a reduced commission when your app becomes eligible for a lower store fee
  * Reverting to the default store commission logic when the reduced rate no longer applies

### Update store commission with the Net Revenue API

You can use the Net Revenue API to manage store commission configurations in the following ways:

* Review existing configurations by sending a GET request to retrieve store commission rates for apps under the account
* Apply a custom commission by sending a POST request with the required commission rate
* Revert to the default logic by sending a DELETE request for the relevant app

Before using the API:

1. Complete the following steps in your ROI360 store revenue settings:

   <div id="ios::f410adfc" />

   <Accordion title="iOS">

   * <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-store-revenue#step-1-ios-set-up-app-store-connect-keys">Step 1. Set up App Store Connect keys</Anchor>
   * <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-store-revenue#step-2-ios-set-up-app-store-server-notifications">Step 2. Set up App Store Server Notifications</Anchor>

   </Accordion>

   <div id="android::659c7976" />

   <Accordion title="Android">

   * <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-store-revenue#step-1-android-set-up-service-account-key-and-permissions">Step 1. Set up service account key and permissions</Anchor>
   * <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-store-revenue#step-2-android-set-up-google-play-server-notifications">Step 2. Set up Google Play Server Notifications</Anchor>

   </Accordion>

2. Prepare the following information:
   * API V2 token to use as the authorization key
   * Store commission rate to apply (supported values: 1%–30%)
   * App ID(s) to which the custom commission applies
3. Note the following configuration details:
   * Store commission is configured **per app**
   * Supported values are **1%–30%**
   * The configuration applies **only to new incoming events**
   * If no custom commission is set, AppsFlyer uses the **default store commission logic**

For full request structures and examples, see the [Net Revenue API documentation](https://dev.appsflyer.com/hc/reference/overview-7).

<div data-zendesk-anchors="h_01KEFDF4KD0DCMP5DGE7ZJDBGX=note h_01KEFDF4KDJ5PVS3AW46BS57NC=update-tax-rate-rules h_01KEFDRXY0FWKKK0DK6PS340TC=ios h_01KEFDRXY0RTBH293JQXFWYAM2=android h_01KEFDF4KD60SEVBQ8G228PEXD=tax-rate-api-parameters h_01KEFDF4KDP4PFKFQ0D9FN8P5D=set-up-store-commission-rates h_01KEFDF4KDVTHTGKJ35CQ1GQ1E=update-store-commission-with-the-net-revenue-api h_01KEFDWVDFBPP7NPSZV0PRGKPZ=ios::f410adfc h_01KEFDWVDFZPHJP6EG0CPNG5A0=android::659c7976" />
