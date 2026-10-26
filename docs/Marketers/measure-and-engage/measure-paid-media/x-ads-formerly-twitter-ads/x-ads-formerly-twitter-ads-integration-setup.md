---
title: X Ads (formerly Twitter Ads) integration setup
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:33:40Z'
  edited_at: '2026-09-15T09:23:09Z'
  id: 4410472471825
  locale: en-us
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4410472471825-X-Ads-formerly-Twitter-Ads-integration-setup
---
> **At a glance:** Integrate your X Ads account with AppsFlyer to display attribution data of X Ads campaigns.

## Overview

X Ads is an Advanced Self-Reporting Network (SRN), enabling AppsFlyer to support campaign measurement for X Ads campaigns through its range of privacy-preserving measurement methods.

### X-Ads attribution flow in AppsFlyer

**The AppsFlyer attribution flow for X Ads is as follows:**

1. AppsFlyer receives all engagement data from X Ads via server-to-server (S2S) integration and attributes the engagements as follows:
   * If both the install event and the engagement include a mobile advertiser ID (MAID), AppsFlyer performs deterministic ID matching.
   * If either the install or the engagement is missing an advertising ID, probabilistic modeling is used for attribution, unless the customer has otherwise configured it.
2. All install postbacks are sent to X Ads through the customer's integration, regardless of whether the install is attributed to X Ads.
3. When an advertiser ID is unavailable, and <Anchor target="_blank" href="/partners/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Advanced Privacy (AP)</Anchor> is active, certain fields in postbacks sent to X Ads will be restricted. The restricted fields are:

   * X Ads engagement ID
   * Hashed device ID
   * IP address
   * User Agent

   [![_- visual selection.png](https://files.readme.io/8c17755d275e732f88cf93e8e7e33df891911dd640d2dbfc2637313a9d59d43e-small-36433399199249.png)](https://files.readme.io/8c17755d275e732f88cf93e8e7e33df891911dd640d2dbfc2637313a9d59d43e-small-36433399199249.png)

## Connecting your X Ads account to AppsFlyer

> 📘 **Note**
>
> Before you begin, make sure you've added a payment method to your X Ads account. Otherwise, you won't be able to activate the partner integration in AppsFlyer.

1. Log in to your X Ads Account at <Anchor target="_blank" href="https://business.x.com/en/advertising">X Ads.</Anchor>  
   If you're not automatically directed to the Ads page, click the Ads button at the top-left corner.
2. When prompted to select either a **Simple (NEW)** or **Advanced** campaign, select **Advanced**.
3. Under **Campaign objective**, select **App Installs** or **App re-engagements**, then click **Next**.

   ![X-Ads-campaign-objective.png](https://files.readme.io/d91bd357dea4878f098086a573191f64c2d1a38af8a6a809c6de7c468e04e043-6148255768337.png)
4. Choose your app, then click the **mobile measurement partner** link.
5. On the **Conversion tracking** page, click **Go to AppsFlyer**.

   ![X-Ads-mmp-selection.png](https://files.readme.io/ebe8e97971c01e0d87c694d2ca1fcc996abf608309d96badcbcda2713ab80d3e-6148393350033.png)
6. A notification displays informing you that you're about to leave X Ads to go to the AppsFlyer website. Click **Go to AppsFlyer** and log in to your Dashboard.
7. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations > Marketplace** tab.
8. Search for **X Ads** and select it.
9. In the **Integration** tab, accept the X Ads Terms and Conditions for Mobile App Conversion Recording (MACT), then click **Save integration**.
10. Turn on **Activate partner**, and click **Log in with X Ads**.
11. Authorize AppsFlyer to use your X Ads account by clicking **Authorize app**.
12. Turn on **Activate Partner** again to display the **Integration** tab settings and enable attribution.  
    **Note:** The toggle must stay on (activated) for as long as you work with the partner. Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">partner activation.</Anchor>
13. Select your X Ads accounts to activate them, then click **Save & Close**.

## X Ads attribution setup

For a detailed description of the partner configuration page Header, click <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">here</Anchor>.

<div id="integration-tab" />

<Accordion title="Integration tab">

The **Integration Tab** is divided into different sections, as described below. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Partner must be activated</Anchor> on the first visit to enable its setup.

### Ad account connected

Select the accounts to enable attribution.

![X-Ads_msc_new_4.png](https://files.readme.io/c64dd5ddc51f35ce195c689b3d14ec4ed4010133662096926f4e8c45e48d60c4-4411049509137.png)

**Note:** You can connect up to 200 ad accounts in AppsFlyer. To avoid reaching this limit and ensure continued attribution for all active accounts, we recommend removing any ad accounts that are no longer in use.

### Advanced Privacy

For iOS apps only: The **Advanced Privacy (AP)** toggle lets you control the level of user data shared with X Ads via postbacks. This setting complies with iOS 14.5+ privacy requirements.  
When AP toggle is ON:

* Postbacks follow the <Anchor target="_blank" href="/partners/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Advanced Privacy template</Anchor>.
* Only <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">aggregated and anonymous data</Anchor> is shared. No device-level identifiers are included.

> 📘 **Note**
>
> * The Advanced Privacy toggle is **on by default** when activating the X Ads integration.
> * According to X Ads, keeping Advanced Privacy **ON** may result in **under-reporting** of campaign events and limit performance optimization on X Ads.

### Click-through attribution

Use the slider to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to X Ads.

You can customize this value to 1-23 hours or 1-30 days. We recommend setting the click-through lookback window to 14 days, to align with X Ads.

![X-Ads_msc_new_6.png](https://files.readme.io/39c3e080cf2fff3b7d9b3e2cf694fc439cd447a263b113ecfc6730a38f653283-4411047369361.png)

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to the install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to X Ads, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days. We recommend setting the View-through lookback window to 1 day, to align with X Ads.

![X-Ads_msc_new_7.png](https://files.readme.io/4f64c994b0cffec692ab99345e539caa4ef07b8f4a439851f18af3aada6ab473-4411049638033.png)

### Reinstall settings

The **Reinstall attribution** toggle is turned on by default for new integrations. Reinstall attribution lets you measure users who reinstall your app during their re-attribution window.

No separate lookback window configuration is needed, as reinstall attribution uses the values from your install attribution settings. For more information, see <Anchor target="_blank" href="/marketers/docs/measure-reinstalls">Measure reinstalls</Anchor>.

### Re-engagement settings

For retargeting campaigns on X Ads, AppsFlyer supports **Re-engagement** measurement only. That is an engagement with a retargeting campaign by a user who already has the app installed at the time of engagement.

> 🚧 **Important!**
>
> Ensure Retargeting is enabled for the app on the App Settings page. For details, click <Anchor target="_blank" href="/marketers/docs/app-settings#reengagement-attribution">here</Anchor>.

X Ads retargeting attribution includes only re-engagement conversions.

Turn on the **Re-engagement attribution** toggle to start attributing re-engagements for X Ads.

#### Re-engagement click-through lookback window

Set the duration of the **Re-engagement click-through lookback window** (the maximum period of time after an ad is clicked, within which a retargeted user can be attributed to the ad). You can set the value in hours (up to 23) or days (1-30).

![X-Ads-reengagement-activate.png](https://files.readme.io/9272c626eceeb8457584d2f1bd1d2adb16f9022994a2efa22eeaeb5b584e2149-4411049796625.png)

#### Re-engagement view-through lookback window

To start attributing impressions of retargeting ads, activate **Re-engagement view-through attribution**.

Then, set the duration of the **Re-engagement view-through lookback window** (the maximum period of time after an ad is viewed, within which a retargeted user can be attributed to the ad). You can set the value in hours (up to 23) or days (1-7):

![X-Ads-reengagement-view-through.png](https://files.readme.io/6d4b80bbe1b953e5df5a6420d71ead781342c616e864e4d1b4d71c68fa9d17fa-4411038679569.png)

#### Re-engagement window

Set the duration of the **Re-engagement window** (the period when the user's in-app events are attributed to the retargeting media source). You can set the value in days (1-90), hours (up to 23), or even lifetime:

<Image alt="X-Ads-reengagement-window.png" src="https://files.readme.io/de80d79c777fc97caa0a28a342657475f0a05c14e30b1f96d24898a4638e1af8-4411047581201.png" width="628px" />

#### Ignore active users for retargeting

Set an inactivity window period to prevent recording retargeting conversions for active users within the specified time frame. See more about the <Anchor target="_blank" href="/marketers/docs/set-retargeting-inactivity-window">Retargeting inactivity period</Anchor>.

### In-app event postback settings

In this section, you can map your AppsFlyer events with your partners via postbacks.

[![In-app_event_postbacks_en-us.png](https://files.readme.io/b215324955412d3a6fc0f719ad54560c25b537a4d1b87475d23c91fbf4262632-7900234463121.png)](https://files.readme.io/b215324955412d3a6fc0f719ad54560c25b537a4d1b87475d23c91fbf4262632-7900234463121.png)

**To configure in-app event postbacks:**

1. Set the **Partner ID** (if required).
2. Enable **In-app event postback.**
3. Click **Add event** to add an SDK or server-to-server event to the list.
4. Complete the parameters required according to the table below.

| Parameter | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#custom-events">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Select the most suitable pre-defined AppsFlyer event from the drop-down box. |
| **for users from** | Select the sending option for the event:<br /><br /><br /><br />**<span id="h_01HDJVBAEZATGM580CNC7BCVTN"></span>Note**<br />For X Ads to receive agency-attributed postbacks, you must select **All media sources, including organic**. Otherwise, X Ads won't receive such postbacks.<ul><li>**This partner only**: send postbacks only when this event is attributed to this partner.</li><li>**All media sources, including organic**: send postbacks for events attributed to any partner and organic events.</li></ul> |
| **including** | <ul><li>**No data (default)**: send only the event itself without the event value.</li><li>**Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: send all the parameters **excluding** the revenue value.</li></ul> |

5. [Optional] Click <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/d84715dd43041f10684d42e4fe56fd4f76aa4c38fbf9df227c8f8f5610c4f859-19616850611857.png" width="30px" /> to set conditions for sending certain in-app events to the partner.  
   Learn more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">conditional in-app event postbacks</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

X Ads does not use attribution links for attribution.

> 📘 **Note**
>
> For all <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns">self-reporting networks (SRNs)</Anchor>, such as Meta ads, Apple Ads, Google Ads, X Ads, etc., this tab is not functional since they don't use external attribution links.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

The cost integration provides the following aggregated data:

* Cost data for your campaigns, adsets, ads, channel, and geo/countries. See the <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features.  
  **Note:** Cost data requires an <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> subscription.
* Data on clicks, impressions, and enriched data (keywords, campaign names, and adset).

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue isn't available for X- Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant X Ads, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for X Ads, the permissions tab is active and you can grant control to X Ads.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks)
* **Allow to configure in-app event postbacks** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* **Allow access to your retention report** - only to the partner's own retention data
* **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data
* **Allow access to your aggregate in-app event data** - only to the partner's own in-app event data
* **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner
* **Allow access to your Protect360 dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions.</Anchor>

### Agency permissions

Learn about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#agency-permissions">granting agency permissions</Anchor>.

</Accordion>

## X-Ads features

<div id="mobile-app-promotion-on-x-ads" />

<Accordion title="Mobile app promotion on X Ads">

X Ads Mobile App Promotion is a method to promote apps on X Ads. It enables advertisers to promote their mobile apps with great App card design driving installs, app engagement, and deep linking. App users can easily install and engage with apps directly from the X Ads timeline.

</Accordion>

<div id="webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only" />

<Accordion title="Web-to-App: Measuring app activity for non-app campaigns (Android only)">

AppsFlyer's integration with X Ads enables measurement of app activity—including installs, re-engagements, and in-app events—for **non-app campaigns** on Android.

For example, even if the ad destination is a **web landing page**, app installs and other post-install activity can still be measured, enabling measurement of the Web-to-App (W2A) user journey.

To measure app activity from X non-app campaigns and gain valuable insights into user behavior, follow these steps in X Ads Manager:

1. Go to the campaign creation form in X Ads Manager.
2. In the **Delivery** section, turn on **App Conversions** measurement to enable tracking of installs and in-app conversions resulting from the campaign. See more details in the <Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">X Ads documentation</Anchor> (under *"Measuring app conversions on non-app objectives"*).

> 🚧 **Important!**
>
> This functionality is currently **supported only on Android**.

</Accordion>

<div id="twitter-ads-and-appsflyer-skan-interoperation" />

<Accordion title="X Ads and AppsFlyer SKAN interoperation">

X Ads sends SKAdNetwork postback data via a dedicated API. SKAN data from X Ads will be displayed in the <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN dashboard</Anchor>.

X Ads enriches SKAN postbacks with the following data fields:

* Campaign name
* Campaign ID
* Adset name
* Adset ID

</Accordion>

<div id="twitter-user-privacy" />

<Accordion title="X Ads user privacy">

X Ads advertisers and users can control how they share information with advertisers and business partners:

* Beginning **July 31, 2021**, advertisers who are **not enrolled** in the X Ads Advanced Mobile Measurement (AMM) program will no longer receive X Ads MACT user-level data. As a result, **all X Ads data will be restricted** in AppsFlyer’s raw data tools. <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions#x-ads-formerly-twitter">Learn more about X Ads data restrictions.</Anchor>
* If the advertiser is in the AMM program and the user has acknowledged the privacy notice, **no raw data restrictions will apply**.
* Regardless of AMM status, if the user is in the EU and has agreed to share data with business partners, **no raw data restrictions will apply**.
* If the user is in the EU and has **not** agreed to share data with business partners, **raw data restrictions will apply**.
* Aggregate attribution data reflects correctly in AppsFlyer and is not impacted by the X Ads policy.

Through the AMM Program, advertisers may receive more complete user-level data by granting X Ads the right to perform an audit. This audit ensures that X Ads data is used exclusively for measurement purposes, consistent with industry standards and data protection laws.

<Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">See more about the AMM program in the FAQ section</Anchor>. For detailed guidance, contact your X Ads Account Manager.

</Accordion>

## Advanced SRN parameter names

The following fields in the Advanced SRN integration for X Ads **replace** their legacy counterparts across the AppsFlyer dashboard, aggregated reports, and event-level raw data.

| **AppsFlyer’s**  <br />**Data Column** | **Legacy SRN** | Advanced SRN |
| --- | --- | --- |
| **PID** | Twitter | Twitter |
| **Campaign Name** | Campaign Name | Campaign name |
| **Campaign ID** | Campaign ID  <br />(base36: different X's dashboard, e.g. 21I3V9) | Campaign ID  <br />(base10: same as X's dashboard, e.g. 123456789) |
| **Adset Name** | Line Item ID  <br />(base36: different X's dashboard, e.g. 21I3V9) | Line Item Name |
| **Adset ID** | Line Item ID  <br />(base36: different X's dashboard, e.g. 21I3V9) | Line Item ID  <br />(base10: same as X's dashboard, e.g. 123456789) |
| **Ad Name** | Tweet ID | Ad Name  <br />(if available) |
| **Ad ID** | Tweet ID | Tweet ID |
| **Match Type** | srn | id\_matching / probabilistic |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Pre-roll attribution unsupported | X Ads doesn’t support MMP attribution for Pre-roll campaigns. |
| Ad Name "Untitled" | Ad Name is not a mandatory field in the X (formerly Twitter) Ads data model, so it may be missing. When the ad name is not defined in X Ads Manager, AppsFlyer will display it as **'Untitled.'** |
| Cost | For X Ads, cost data for SKAN-only campaigns (campaigns that only have SKAN installs and no "regular" installs) isn't available to agencies. The cost integration must be set up by the advertiser. And the data can only be viewed by the advertiser. |

<div data-zendesk-anchors="h_01JV7CGQNZNEM3P98K6KSYKB0D=overview xads-attribution-flow-in-appsflyer=x-ads-attribution-flow-in-appsflyer h_01JZG83EKX39SF8355EW62C462=x-ads-attribution-flow-in-appsflyer connecting-your-X-Ads-ads-account-to-appsflyer=connecting-your-x-ads-account-to-appsflyer h_01HDJVCRYQESA17XZ83GS81YZ3=connecting-your-x-ads-account-to-appsflyer h_01JV7D6AWYQ981HY6C130B021B=note X-Ads-ads-attribution-setup=x-ads-attribution-setup h_01HDJVBAEZ5W3JH1BN7WXJ08P6=x-ads-attribution-setup h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab h_01HDJVBAEZD89BSGHQTPR84HSC=ad-account-connected xads_advanced_privacy_toggle=advanced-privacy h_01JV7HVQJ2GTP74G6JYB300E71=note-1 clickthrough-attribution=click-through-attribution h_01HDJVBAEZFJWQ6FD4Q4GSPD76=click-through-attribution viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HDJVBAEZ2H91WBHNSMRQYQ7H=view-through-attribution-lookback-window h_01HDJVBAF0XRWRZJQSS4STH7YN=reinstall-settings reengagement-settings=re-engagement-settings h_01HDJVBAEZZR1W06YH4XJSBKHV=re-engagement-settings h_01JV9YQ7ZHRDD2NA5ENQXJQ31V=important reengagement-clickthrough-lookback-window=re-engagement-click-through-lookback-window h_01HDJVBAEZ59ERYD2WQQYK6T37=re-engagement-click-through-lookback-window reengagement-viewthrough-lookback-window=re-engagement-view-through-lookback-window h_01HDJVBAEZSCK7430NJ8AMQYVY=re-engagement-view-through-lookback-window reengagement-window=re-engagement-window h_01HDJVBAEZCMWY5X47FEEFXTBX=re-engagement-window ignore-active-users=ignore-active-users-for-retargeting h_01JVC3PWDR9KHEFBQF5NWHCQJN=ignore-active-users-for-retargeting inapp-event-postback-settings=in-app-event-postback-settings h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=in-app-event-postback-settings h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=note-2 h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab h_01HDJVBAF0BMSCKF6J9NJ019YJ=ad-network-permissions h_01HDJVBAF0W3ZE7J93CRE8EBRP=agency-permissions x-ad-features=x-ads-features h_01JZWQA6DXRZ17SRVT4HM2MQSH=x-ads-features h_01JZWQA6DX3BRNG8B5CJGA57AM=mobile-app-promotion-on-x-ads h_01JZWQA6DX7W9102P5S6KWJ1WB=webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only h_01JZWQA6DX8AX5XG3W4A6XB53S=important-1 h_01H9QR6TH74PKBGM5RC4M118GE=twitter-ads-and-appsflyer-skan-interoperation h_01H9QR6TH74R50K00H7FYN61KC=twitter-user-privacy x-ads-data-differences=advanced-srn-parameter-names h_01JYGPBHHNQARG3GRMQJA95JKD=traits-and-limitations" />
