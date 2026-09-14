---
title: "Applovin MAX ad revenue configuration"
excerpt: "Learn how to configure Applovin MAX ad revenue integration with AppsFlyer to receive device-level and aggregate ad monetization data."
---
At a glance: Applovin MAX, an AppsFlyer integrated partner, provides app owners with ad revenue-generating solutions.

## Setting up Applovin MAX integration

> 📘 Prerequisite
>
> An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> ❗️ Important note
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below.

### Setting tabs

Update setting tabs content as required: Ad revenue.

### Ad revenue

Applovin MAX provides ad revenue mediation with aggregate data at the device level.

> 📘 Note
>
> * Ad revenue for the Fire OS platform isn't reported in AppsFlyer.
> * Learn more about [ad revenue attribution](https://support.appsflyer.com/hc/articles/217490046) (ad monetization).

**To enable the ad revenue API**:

* Follow [these integration instructions](https://support.appsflyer.com/hc/articles/217490046-Ad-revenue-attribution-guide#connect-to-ad-revenue-integrated-partners).

### Best practice

If you monetize with Meta ads and are using Applovin Max, it's best if you don't have a direct Facebook ad revenue integration with AppsFlyer. This way, you'll receive user-level data. If you have a direct Facebook ad revenue integration, data is at aggregate-level.