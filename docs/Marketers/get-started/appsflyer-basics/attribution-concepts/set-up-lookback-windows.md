---
title: Set up lookback windows
metadata:
  keywords:
    - Advertisers
    - look back
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-07T09:27:55Z'
  edited_at: '2026-07-13T14:30:13Z'
  id: 208338403
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/208338403-Set-up-lookback-windows
---
**At a glance:** Customize the click-through and view-through lookback windows, based on your agreements with media sources.

## Lookback windows

Configurable attribution lookback window allows you to customize the attribution period based on your agreement with media sources.

By setting attribution lookback windows per media source, AppsFlyer attributes according to the agreed terms.

**Lookback window types**:

* **Click lookback window**: Maximum period of time after an ad is clicked within which an install can be attributed to the ad. Installs that take place after the lookback window are considered Organic.
* **Engaged click lookback window:** The maximum period of time after an engaged click within which an install can be attributed to the engaged click.  Installs that take place after the lookback window are considered Organic.
* **Engaged view lookback window:** The maximum period of time after an engaged view within which an install can be attributed to the engaged view.  Installs that take place after the lookback window are considered Organic.
* **View-through lookback window**: Maximum period of time after an ad is viewed within which an install can be attributed to the ad. Installs that take place after the lookback window are considered Organic.

#### Configurable lookback windows per attribution type

<table><thead><tr><th rowspan="2"><p><strong>Attribution type</strong></p></th><th rowspan="2"><p><strong>Attribution method</strong></p></th><th colspan="2"><strong>Lookback window</strong> </th></tr><tr><th><strong>Range</strong></th><th><strong>Default</strong></th></tr></thead><tbody><tr><td rowspan="3"><p>Click-through</p><p>(All media sources)</p></td><td>Referrer, ID matching</td><td>1-30 Days OR<br/>1-23 Hours</td><td>7 days</td></tr><tr><td>Probabilistic modeling (mobile)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptive</a></td><td>Up to 24 hours</td></tr><tr><td>Probabilistic modeling (CTV, PC and Console - single platform links)</td><td>Up to 7 days. (Set in the <code>af_lookback_window</code> link parameter.)</td><td>7 days</td></tr><tr><td rowspan="2"><p>Engaged click-through</p><p>(Selected non-SRN <a href="./about-enriched-engagement-types#which-networks-can-report-engaged-views-and-engaged-clicks" target="_blank">media sources</a>\*)</p></td><td>ID matching</td><td>1-7 days or 1-23 hours</td><td>2 days</td></tr><tr><td>Probabilistic modeling (mobile)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptive</a></td><td>Up to 24 hours</td></tr><tr><td rowspan="2"><p>Engaged view-through</p><p>(Selected non-SRN <a href="./about-enriched-engagement-types#which-networks-can-report-engaged-views-and-engaged-clicks" target="_blank">media sources</a>\*)</p></td><td>ID matching</td><td>1-7 days or 1-23 hours</td><td>2 days</td></tr><tr><td>Probabilistic modeling (mobile)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptive</a></td><td>Up to 24 hours</td></tr><tr><td rowspan="4"><p>View-through</p><p>(Selected <a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">media sources</a>)</p></td><td>ID matching</td><td><p>1-24 hours</p><p>[Until Dec 15, 2021, the upper bound was 7 days]</p></td><td>24 hours</td></tr><tr><td>Probabilistic modeling (mobile)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptive</a></td><td>Up to 24 hours</td></tr><tr><td>Probabilistic modeling (CTV, PC and Console - single platform links)</td><td>Up to 7 days. (Set in the <code>af_lookback_window</code> link parameter.)</td><td>24 hours</td></tr><tr><td>Probabilistic modeling (CTV, PC and Console - <a href="./set-up-cross-platform-links-for-multi-device-campaigns#traits-and-limitations" target="_blank">cross-platform OneLink attribution links</a>)</td><td>Up to 72 hours. (Set in the <code>af_xplatform_vt_lookback</code> link parameter.)</td><td>24 hours</td></tr></tbody></table>

*Lookback windows for `engaged_click` and `engaged_view` can only be set for non-SRN networks. For SRNs, `engaged_click` and `engaged_view` parameters share the same lookback window as clicks and are, therefore, set by the **Install Click-Through Attribution Lookback** sliders.

### Probabilistic modeling lookback window

The Probabilistic modeling lookback window, used to maintain attribution accuracy, has the following characteristics:

* Applies to both clicks and impressions
* Has an adaptive duration of up to 24 hours
* Disregards window duration settings sent on the attribution link
* Has a shorter duration than windows used by deterministic models

To learn more, read about the <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#probabilistic-modeling">AppsFlyer Probabilistic modeling method</Anchor>.

## Lookback window setup

Following, we list the lookback window setup process for SRNs and Attribution Links

<Tabs>
<Tab title="SRNs Lookback Window">

### Attribution lookback window for SRNs

> 🚧 **Important!**
>
> Each SRN has its own default lookback. We recommend matching the lookback window value in AppsFlyer with the SRN's value to minimize discrepancies. Changing it might result in discrepancies. To learn more, see an [SRN discrepancy example](#scenarios-and-examples).

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Marketplace**.
2. Search and select the SRN - see the <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns#srns-integrated-with-appsflyer">list of supported SRNs</Anchor>.
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

<div id="attribution-lookback-window-with-attribution-links" />

### Non-SRN Attribution lookback window for click-through and view-through

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.
2. Search and select a partner.
3. By default, View-Through attribution is enabled.
4. Click the **Attribution link** tab.
5. Choose if you want to set the time in days or hours.
6. Use the sliders under **Click-through attribution** (`af_click_lookback` parameter) and **View-through attribution** (`af_viewthrough_lookback` parameter) to set the attribution window.  
   The selected time is automatically reflected in the attribution link.
7. Select the parameters that correspond to the campaign i.e. campaign name, ad set etc.
8. Copy and save the link - this is the link that you provide to the ad network.

<div id="h_01JKWVQB6TTA24VAZ9WVJMGY4X" />

### Non-SRN Attribution lookback window for engaged click-through and engaged view-through

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.
2. Search and select a partner.
3. In the Integration tab, scroll down to the **Install engaged click-through lookback window** slider or to the **Install engaged view-through lookback window** slider.
4. Set the lookback window using the sliders.

> 👍 **Tip**
>
> * Want some tips and tricks for the lookback window configuration? Check out this <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">short, informative course</Anchor> on the AppsFlyer Learning Portal.
> * [Click here](/docs/set-up-lookback-windows#lookback-in-hours-for-flash-campaigns) to learn when you should use hours for attribution windows.

<div id="lookback-window-in-onelink" />

### Lookback window in OneLink™

You can set the lookback window in OneLink as well.

1. <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template">Configure a OneLink</Anchor>
2. <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link">Create a Custom Attribution Link</Anchor>
3. Under **Advanced**, turn on **Customize Lookback Window** and set the lookback window.

</Tab>
</Tabs>

## Distribution of first app launches

Below is a graph that shows the distribution of first app launches from the day of engagement.

[![](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)

The graph can give you a better sense of the number of users who install the app as a function of the lookback window.

The majority of users, a little over 97%, who launch the app do so within 7 days of engaging with the ad. The remaining 2% do so in the span between day 7 and the end of the lookback window (day 30).

In fact, almost 62% of users who launch the app, do so within 15 minutes of engaging the ad. 72% of users do so within the first hour.

## Scenarios and examples

Below is a list of possible scenarios and examples of lookback window usage.

<div id="srn-discrepancy-srn-lookback-longer-than-appsflyer" />

<Accordion title="SRN discrepancy: SRN lookback longer than AppsFlyer">

You set a campaign on X Ads and configure the click-through lookback window to 7 days. X Ads, on the other hand, has a default lookback window of 14 days.

[![srn-discrepancy-srn-lookback-larger-than-appsflyer.png](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)

</Accordion>

<div id="srn-lookback-smaller-than-appsflyer" />

<Accordion title="SRN lookback smaller than AppsFlyer">

You set a campaign on X Ads and configure the click-through lookback window to 28 days. X Ads, on the other hand, has a default lookback window of 14 days.

[![srn-lookback-smaller-than-appsflyer.png](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)

</Accordion>

<div id="attribution-link-without-a-lookback-window-parameter" />

<Accordion title="Attribution link without a lookback window parameter">

It is possible to have an attribution link that doesn't have a lookback window parameter. In such cases, AppsFlyer defaults to a 7-day lookback window for clicks, and a 1-day lookback window for impressions.

</Accordion>

<div id="lookback-in-hours-for-flash-campaigns" />

<Accordion title="Lookback in hours for flash campaigns">

Flash campaigns are campaigns whose intention is to prompt users to install the app as quickly as possible and within a short promotion window.

An eCommerce app called SuperShopping runs a flash campaign. In this campaign, a user who installs the app within an hour gets special offers.

Johnny, SuperShopping's lead marketer, creates an attribution Link and sets the lookback window to 1 hour. This way Johnny knows how many users respond to the campaign.

In addition, the app's developer can identify the users that come from this flash campaign and deliver the promotions that the campaign advertises.

</Accordion>

> 👍 **Tip**
>
> Want some tips and tricks on lookback windows and attribution? Check out this short, informative <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">course on the AppsFlyer Learning Portal</Anchor>.

<div data-zendesk-anchors="h_01HGFQVP7QZACJ3EGSWEP4HPFV=lookback-windows h_01HGFQVP7QM0J507CFQ753YS5X=configurable-lookback-windows-per-attribution-type h_01JKWV7S7J5B4YA84VGEB478TT=probabilistic-modeling-lookback-window h_01HGFQVP7QCCN7CHRCAFSNJVHA=lookback-window-setup h_01HGFQVP7QP61C2K0P7C7YM56Z=attribution-lookback-window-for-srns h_01HGFQVP7QXTQKGVQJEZ0NEW0M=important h_01HGFQVP7QDBFP85A9DJFZE38S=attribution-lookback-window-with-attribution-links h_01HGFQVP7Q69H5621GXMYZ441N=tip-1 lookback-window-in-onelink%E2%84%A2=lookback-window-in-onelink h_01HGFQVP7QSJEE8D7TCWZMSXGK=lookback-window-in-onelink h_01HGFQVP7Q96827N7Q9Q0363SR=distribution-of-first-app-launches h_01HGFQVP7Q02NS8MXF7WKYQ8V1=scenarios-and-examples h_01HGFQVP7Q1CYRAHAKY3WK8BK0=srn-discrepancy-srn-lookback-longer-than-appsflyer h_01HGFQVP7QAWDP40H89YBN66GV=srn-lookback-smaller-than-appsflyer h_01HGFQVP7QYE3V2DKW7T4171MX=attribution-link-without-a-lookback-window-parameter h_01HGFQVP7Q7CXSK5G8A0937H5Z=lookback-in-hours-for-flash-campaigns h_01HGFQVP7QM3R973QS99661VPG=tip-1" />
