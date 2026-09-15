---
title: "Redirect users to custom app store product pages"
excerpt: "Learn how to redirect users to custom store listings in Google Play or custom product pages in the App Store using AppsFlyer OneLink URLs."
---
At a glance: Redirect users to your app's custom store listings in Google Play or custom product pages in the App Store. Use AppsFlyer data about the custom store pages to optimize your campaigns.

## Overview

Google Play custom store listings and Apple App Store custom product pages (referred to collectively in this article as custom store product pages), allow app owners to create additional versions of their Google Play and App Store pages that showcase different features or content within their app. Custom store product pages can have promotional text, screenshots, and previews that are different from those on the default store page.

For Google Play, you can create up to 50 custom pages. For the App Store, you can create up to 35.

You can use AppsFlyer OneLink URLs or single-platform attribution links to redirect users to these custom store product pages and create distinct contextual journeys for different target audiences.

Data regarding the custom store product pages is available in the AppsFlyer dashboard and raw data reports as described in the section that follows. You can use the data to A/B test and optimize your campaigns and product pages.

## Data availability

### Dashboard

Aggregate data for App Store custom product pages is available in the [Overview dashboard](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv). For Google Play custom store listings, availability is coming soon.

**To view the data**:

* In the [Overview dashboard](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#view-types), add the **Store product page** grouping dimension.

Custom store product page displays in the dashboard charts and tables.

### Raw data

Raw data is available via the [AppsFlyer reporting tools](/docs/raw-data-reporting-overview#reporting-tools%E2%80%94characteristics-and-features).

In the reports, the `store_product_page` field indicates which custom page a given user was redirected to.

## Setup

<Tabs>
<Tab title="Google Play">

To set up redirections to a custom store listing in Google Play, you can either:

* Use the OneLink UI.
* Add the parameter `af_android_store_csl` to your OneLink URLs or single-platform attribution links with the value being the custom store listing you chose in Google Console. For example: `af_android_store_csl=abc123`

> 🚧 Note
>
> Due to system changes in some browsers, including Google Chrome, using custom store listing redirection may lead to a web version of the Google Play store with the custom store listing view (instead of the app version).

#### Use the OneLink UI—Google Play

Prerequisites:

* Custom store listing created in Google Console.

> 📘 Note
>
> In Google Console, the custom listing must be set to be via a unique URL param.

* [OneLink template](/docs/create-a-onelink-template#procedures)
* [OneLink custom link](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link)

**To add a redirection to a custom store listing to a OneLink custom link**:

1. In your OneLink custom link, go to the **Deep linking & redirections** section **.**
2. Scroll down to the **When app isn’t installed** settings.

<Image src="https://files.readme.io/d354feb4d47171b14f0612011b7a52b579bd9062a87544095df226ba58c57ec6-11591784334865.png" alt="android_cpp.png" />

3. For Android, make sure **Redirect to** is set to Google Play.
4. In the **Custom store listing** textbox, enter the value you defined for the listing's unique URL parameter in Google Console. For example: abc123
5. Click **Update link**.
6. [Recommended] Test the link on different Android browsers to make sure it works as expected.

</Tab>

<Tab title="App Store">

To set up redirections to a custom product page in the App Store, you can either:

* Use the OneLink UI.
* Add the parameter `af_ios_store_cpp` to your OneLink URLs or single-platform attribution links with the value being the custom product page ID. For example: `af_ios_store_cpp=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`

> 📘 Note
>
> In raw data and aggregated reporting, the `af_ios_store_cpp` value is recorded for clicks but not for impressions (display name: store\_product\_page).

#### Use the OneLink UI—App Store

Prerequisites:

* Custom product page created in App Store Connect
* [OneLink template](/docs/create-a-onelink-template#procedures)
* [OneLink custom link](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link)

**To add a redirection to a custom product page to a OneLink custom link**:

1. In your OneLink custom link, go to the **Deep linking & redirections** section **.**
2. Scroll down to the **When app isn’t installed** settings.

<Image src="https://files.readme.io/76f6b46644efc478dc27cb373b3de4a4a80600936db5d7e6725fdb4b9182f6bb-11591824202641.png" alt="ios_cpp.png" />

3. For iOS, make sure **Redirect to** is set to App Store.
4. In the **Custom product page** textbox, enter the ID of your custom product page (ppid), as defined in App Store Connect. For example: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
5. Click **Update link**.

</Tab>
</Tabs>

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| Browsers | - Google Play custom store listings aren't supported by Naver Blog. |