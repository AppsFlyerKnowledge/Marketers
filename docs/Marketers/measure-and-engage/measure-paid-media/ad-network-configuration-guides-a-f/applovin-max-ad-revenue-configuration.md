---
title: "Applovin MAX ad revenue configuration"
excerpt: "Applovin MAX, an AppsFlyer integrated partner, provides app owners with ad revenue-generating solutions."
x-zendesk:
  id: 360004707378
  url: https://support.appsflyer.com/hc/en-us/articles/360004707378-Applovin-MAX-ad-revenue-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  position: 9
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-michael-talapov, Marketers, ROI360, Ad Networks]
  labels: [Ad Network, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2020-01-09T10:53:21Z'
  edited_at: '2026-06-16T09:35:28Z'
---
![](https://cdn.appsflyer.com/marketplace/static/logo/applovinmax.png)

## Setting up Applovin MAX integration

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Important note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

### Setting tabs

Update setting tabs content as required: Ad revenue.

### Ad revenue

Applovin MAX provides ad revenue mediation with aggregate data at the device level.

> 📘 **Note**
>
> * Ad revenue for the Fire OS platform isn't reported in AppsFlyer.
> * Learn more about [ad revenue attribution](/docs/roi360-guide-ad-revenue-attribution) (ad monetization).


**To enable the ad revenue API**:

* Follow [these integration instructions](/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners).

### Best practice

If you monetize with Meta ads and are using Applovin Max, it's best if you don't have a direct Facebook ad revenue integration with AppsFlyer. This way, you'll receive user-level data. If you have a direct Facebook ad revenue integration, data is at aggregate-level.