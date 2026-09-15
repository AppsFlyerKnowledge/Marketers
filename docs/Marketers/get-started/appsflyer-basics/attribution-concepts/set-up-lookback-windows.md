---
title: "Set up lookback windows"
excerpt: "Customize the click-through and view-through lookback windows based on your agreements with media sources."
---
Configurable attribution lookback window allows you to customize the attribution period based on your agreement with media sources.

By setting attribution lookback windows per media source, AppsFlyer attributes according to the agreed terms.

**Lookback window types**:

- **Click lookback window**: Maximum period of time after an ad is clicked within which an install can be attributed to the ad. Installs that take place after the lookback window are considered Organic.
- **Engaged click lookback window:** The maximum period of time after an engaged click within which an install can be attributed to the engaged click.  Installs that take place after the lookback window are considered Organic.
- **Engaged view lookback window:** The maximum period of time after an engaged view within which an install can be attributed to the engaged view.  Installs that take place after the lookback window are considered Organic.
- **View-through lookback window**: Maximum period of time after an ad is viewed within which an install can be attributed to the ad. Installs that take place after the lookback window are considered Organic.

#### Configurable lookback windows per attribution type

| **Attribution type** | **Attribution method** | **Lookback window** | **Default** |
| --- | --- | --- | --- |
| Click-through<br>(All media sources) | Referrer, ID matching | 1-30 Days OR<br>1-23 Hours | 7 days |
| Probabilistic modeling (mobile) | [Adaptive](https://support.appsflyer.com/hc/articles/207447053-Attribution-model-explained#probabilistic-modeling) | Up to 24 hours | - |
| Probabilistic modeling (CTV, PC and Console - single platform links) | - | Up to 7 days. (Set in the `af_lookback_window` link parameter.) | 7 days |
| Engaged click-through<br>(Selected non-SRN [media sources](https://support.appsflyer.com/hc/articles/21837486015889-Enriched-Engagement-Types#allowed-networks)\*) | ID matching | 1-7 days or 1-23 hours | 2 days |
| Probabilistic modeling (mobile) | [Adaptive](https://support.appsflyer.com/hc/articles/207447053-Attribution-model-explained#probabilistic-modeling) | Up to 24 hours | - |
| Engaged view-through<br>(Selected non-SRN [media sources](https://support.appsflyer.com/hc/articles/21837486015889-Enriched-Engagement-Types#allowed-networks)\*) | ID matching | 1-7 days or 1-23 hours | 2 days |
| Probabilistic modeling (mobile) | [Adaptive](https://support.appsflyer.com/hc/articles/207447053-Attribution-model-explained#probabilistic-modeling) | Up to 24 hours | - |
| View-through<br>(Selected [media sources](https://support.appsflyer.com/hc/articles/210084473#view-vta-partner-list)) | ID matching | 1-24 hours<br>[Until Dec 15, 2021, the upper bound was 7 days] | 24 hours |
| Probabilistic modeling (mobile) | [Adaptive](https://support.appsflyer.com/hc/articles/207447053-Attribution-model-explained#probabilistic-modeling) | Up to 24 hours | - |
| Probabilistic modeling (CTV, PC and Console - single platform links) | - | Up to 7 days. (Set in the `af_lookback_window` link parameter.) | 24 hours |
| Probabilistic modeling (CTV, PC and Console - [cross-platform OneLink attribution links](/docs/set-up-cross-platform-links-for-multi-device-campaigns#traits-and-limitations)) | - | Up to 72 hours. (Set in the `af_xplatform_vt_lookback` link parameter.) | 24 hours |

\*Lookback windows for `engaged_click` and `engaged_view` can only be set for non-SRN networks. For SRNs, `engaged_click` and `engaged_view` parameters share the same lookback window as clicks and are, therefore, set by the **Install Click-Through Attribution Lookback** sliders.

### Probabilistic modeling lookback window

The Probabilistic modeling lookback window, used to maintain attribution accuracy, has the following characteristics:

- Applies to both clicks and impressions
- Has an adaptive duration of up to 24 hours
- Disregards window duration settings sent on the attribution link
- Has a shorter duration than windows used by deterministic models

To learn more, read about the [AppsFlyer Probabilistic modeling method](https://support.appsflyer.com/hc/articles/207447053#probabilistic-modeling).

## Lookback window setup

Following, we list the lookback window setup process for SRNs and Attribution Links

<Tabs>
<Tab title="SRNs Lookback Window">

### Attribution lookback window for SRNs

> ❗️ Important!
>
> Each SRN has its own default lookback. We recommend matching the lookback window value in AppsFlyer with the SRN's value to minimize discrepancies. Changing it might result in discrepancies. To learn more, see an [SRN discrepancy example](/docs/set-up-lookback-windows#scenarios-and-examples).

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Marketplace**.
2. Search and select the SRN - see the [list of supported SRNs](https://support.appsflyer.com/hc/articles/360001546905-Self-Reporting-Networks#srns-integrated-with-appsflyer).
3. By default, View-Through attribution is enabled.
4. In the **Integration** tab, scroll down to the **Click-through attribution** and **View-through attribution** configuration.
5. Use the sliders to set the attribution window

See below each SRN lookback window:

| SRN | Default Click-Through Lookback Window (days) | Default View-Through Lookback Window (hours) |
| --- | --- | --- |
| Google | 30 | 24 |
| Meta ads | 7 | 24 |
| Snapchat | 28 | 24 |
| X Ads | 14 | 24 |
| Apple Search Ads | 30 | 24 |
| Oath (YahooGemini) | 7 | 24 |

</Tab>
<Tab title="Non-SRNs Lookback Window">

### Non-SRN Attribution lookback window for click-through and view-through

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.
2. Search and select a partner.
3. By default, View-Through attribution is enabled.
4. Click the **Attribution link** tab.
5. Choose if you want to set the time in days or hours.
6. Use the sliders under **Click-through attribution** (`af_click_lookback` parameter) and **View-through attribution** (`af_viewthrough_lookback` parameter) to set the attribution window.

The selected time is automatically reflected in the attribution link.
7. Select the parameters that correspond to the campaign i.e. campaign name, ad set etc.
8. Copy and save the link - this is the link that you provide to the ad network.

### Non-SRN Attribution lookback window for engaged click-through and engaged view-through

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.
2. Search and select a partner.
3. In the Integration tab, scroll down to the **Install engaged click-through lookback window** slider or to the **Install engaged view-through lookback window** slider.
4. Set the lookback window using the sliders.

> 👍 Tip
>
> Want some tips and tricks for the lookback window configuration? Check out this [short, informative course](https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks) on the AppsFlyer Learning Portal.
>
> [Click here](https://support.appsflyer.com/hc/articles/208338403#lookback-in-hours-for-flash-campaigns) to learn when you should use hours for attribution windows.

### Lookback window in OneLink™

You can set the lookback window in OneLink as well.

1. [Configure a OneLink](https://support.appsflyer.com/hc/articles/207032246)
2. [Create a Custom Attribution Link](https://support.appsflyer.com/hc/articles/208874366#create-a-onelink-link)
3. Under **Advanced**, turn on **Customize Lookback Window** and set the lookback window.

</Tab>
</Tabs>

## Distribution of first app launches

Below is a graph that shows the distribution of first app launches from the day of engagement.

The graph can give you a better sense of the number of users who install the app as a function of the lookback window.

The majority of users, a little over 97%, who launch the app do so within 7 days of engaging with the ad. The remaining 2% do so in the span between day 7 and the end of the lookback window (day 30).

In fact, almost 62% of users who launch the app, do so within 15 minutes of engaging the ad. 72% of users do so within the first hour.

## Scenarios and examples

Below is a list of possible scenarios and examples of lookback window usage.

### SRN discrepancy: SRN lookback longer than AppsFlyer

You set a campaign on X Ads and configure the click-through lookback window to 7 days. X Ads, on the other hand, has a default lookback window of 14 days.

<Image src="https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png" alt="srn-discrepancy-srn-lookback-larger-than-appsflyer.png" />

### SRN lookback smaller than AppsFlyer

You set a campaign on X Ads and configure the click-through lookback window to 28 days. X Ads, on the other hand, has a default lookback window of 14 days.

<Image src="https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png" alt="srn-lookback-smaller-than-appsflyer.png" />

### Attribution link without a lookback window parameter

It is possible to have an attribution link that doesn't have a lookback window parameter. In such cases, AppsFlyer defaults to a 7-day lookback window for clicks, and a 1-day lookback window for impressions.

### Lookback in hours for flash campaigns

Flash campaigns are campaigns whose intention is to prompt users to install the app as quickly as possible and within a short promotion window.

An eCommerce app called SuperShopping runs a flash campaign. In this campaign, a user who installs the app within an hour gets special offers.

Johnny, SuperShopping's lead marketer, creates an attribution Link and sets the lookback window to 1 hour. This way Johnny knows how many users respond to the campaign.

In addition, the app's developer can identify the users that come from this flash campaign and deliver the promotions that the campaign advertises.

> 👍 Tip
>
> Want some tips and tricks on lookback windows and attribution? Check out this short, informative [course on the AppsFlyer Learning Portal](https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks).