---
title: "SearchAds.com (by MobileAction) setup"
excerpt: "Learn how to optimize Apple Ads campaigns by configuring AppsFlyer to send postbacks to SearchAds.com by MobileAction."
---
**At a glance:** Optimize Apple Ads campaigns by using SearchAds.com by MobileAction. When configured, AppsFlyer sends postbacks to SearchAds.com.

## Enabling Apple Ads attribution

To be able to send postbacks to SearchAds.com, you should first enable attribution for Apple Ads. This can be done by either an advertiser or an agency.

> 📘 **Note**
>
> If the advertiser or the agency disables attribution for Apple Ads, postbacks for SearchAds.com and other Apple Ads Marketing Partners are stopped.

* **Advertisers**: follow the instructions below on how to enable attribution for Apple Ads.
* **Agencies**: [follow these instructions](/docs/apple-ads-integration-setup#agency-setup) to enable attribution for Apple Ads.

## Setting up SearchAds.com in AppsFlyer

### Getting required information from SearchAds.com

Before you start configuring SearchAds.com in AppsFlyer, obtain your **api\_key** and your **Apple Ads campaign group ID**.

* For api\_key, go to your SearchAds.com dashboard, click **Integrations** > **AppsFlyer**. In the popup that opens, copy the ID. [![SearchAds.com API key](https://files.readme.io/1acc061c44fe616a4485b576251d1ad64cb05607f4727bbd21b0bf6871720b40-4402869972241.png)](https://files.readme.io/1acc061c44fe616a4485b576251d1ad64cb05607f4727bbd21b0bf6871720b40-4402869972241.png)
* For Apple Ads Campaign Group ID: In your **Apple Ads dashboard,** get the Apple Ads Campaign Group ID for the relevant campaign group:

  ![apple-search-ads-campaign-group-id.png](https://files.readme.io/dbc7f9d2474a2126a2277db279b7d2fa815770c55138e0d42c71eecb36d5abcc-4402898560017.png)

### Setting up campaigns in AppsFlyer

**To set up a SearchAds.com:**

1. If required, activate **Apple Ads integration:**
   1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Partner Marketplace**.
   2. Search for and select the partner. You're directed to the partner configuration page.
   3. From the **Integration** tab, turn on **Activate partner**.
   4. Click **Save Integration**.
2. **In AppsFlyer, configure SearchAds.com:**
   1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations.**
   2. Search for SearchAds.com (by MobileAction).  
      The list of marketing partners displays.
   3. Select SearchAds.com (by MobileAction).
   4. Turn on **Activate Partner**.
   5. Enter the API key in the **api\_key** field.
   6. Enter SearchAds.com's **Apple Ads Campaign ID**. Enter the digits (numbers) only.
   7. Click **Save**.

#### Configuring in-app event postbacks

**To configure postback that should be sent to SearchAds.com upon in-app events:**

1. Enter the **api\_key**.
2. Turn on **In-app events postback**.
3. Select **Send all events**.
4. Under **Send revenue**, select **Values&Revenue**.
5. Click **Save Integration**.