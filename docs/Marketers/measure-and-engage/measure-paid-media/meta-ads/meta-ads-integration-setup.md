---
title: Meta Ads—integration setup
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Facebook
    - App Install
    - View-Through
    - integrated partner
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
  created_at: '2013-01-24T20:13:58Z'
  edited_at: '2026-09-09T13:34:51Z'
  id: 207033826
  locale: en-us
  section: Meta ads
  section_id: 6551109855761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207033826-Meta-Ads-integration-setup
---
> **At a glance:** Learn about integrating Meta ads with AppsFlyer.

## Meta ads setup guide

How long does it take to start attributing your Meta ads mobile app ads with AppsFlyer?

If you already have the <Anchor target="_blank" href="/marketers/docs/integrate-the-appsflyer-sdk">AppsFlyer SDK integrated into your app</Anchor> and have already defined your app on Meta ads, the answer is less than a minute!

You don't need to implement Facebook Login or integrate your app with Facebook's SDK for mobile attribution. Just follow the [basic step-by-step setup](#basic-meta-ads-attribution-setup) instructions below. Afterward, check out [advanced setup options](#advanced-meta-ads-attribution-setup) for Meta ads.

## Basic Meta ads attribution setup

<div id="create-and-retreive-facebook-app-id" />

<Accordion title="Create and retrieve a Facebook App ID">

To integrate Meta ads with AppsFlyer, first, create a <Anchor target="_blank" href="https://developers.facebook.com/docs/apps/register">Facebook App ID</Anchor>, then retrieve it.

**To create a Facebook App ID**:

1. On **Meta ads**, go to your <Anchor target="_blank" href="https://developers.facebook.com/apps">App Dashboard</Anchor>.
2. Under **Apps**, click **Create New App.**
3. Complete the app name and enter a unique namespace. Make sure to add the correct platform for your app; otherwise, installs might not be attributed correctly.

**To retrieve the Facebook App ID**:

1. On **Meta ads**, go to your <Anchor target="_blank" href="https://developers.facebook.com/apps">App Dashboard.</Anchor>
2. Click the required app.
3. Click the App ID at the top left of the screen to copy it.

   [![](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)

AppsFlyer attributes data per App ID. The same Facebook App ID can be used for [both your Android and iOS apps](https://developers.facebook.com/docs/app-ads/app-setup/). Note that for iOS 14+, Meta ads limits ad accounts to nine accounts per app.

</Accordion>

<div id="enable-meta-ads-device-level-data" />

<Accordion title="Enable Meta ads device-level data">

Starting June 17, 2025, Meta has re-enabled **Advanced Mobile Measurement (AMM)** reporting. Once you opt in, you’ll receive:

* Device-level mobile analytics
* Event-level attribution metrics for Meta campaigns
* Full integration with your existing AppsFlyer dashboards and exports

**To enable AMM, follow these steps:**

1. Visit <Anchor target="_blank" href="https://business.facebook.com/business/loginpage/?next=https%3A%2F%2Fdevelopers.facebook.com%2Fadvanced_mobile_measurement%2Fterms">Meta Ads</Anchor>.
2. Select the relevant app ID(s).
3. Accept Meta's Advanced Mobile Measurement terms.

> 🚧 **Important!**
>
> * An admin of your Meta developer app is required to accept Meta's AMM terms.
> * Device-level data with full attribution visibility is only available for new attributed devices after the AMM terms have been accepted.
> * In-app events inherit the restriction status of their attributed conversions. This means:
>   * If the in-app event is attributed to a conversion that occurred before signing the Advanced Mobile Measurement (AMM) agreement, the event remains restricted.
>   * If the in-app event is attributed to a conversion that occurred after signing the AMM agreement, the event is available in raw data reports.

</Accordion>

<div id="set-the-meta-ads-active-integration" />

<Accordion title="Set the Meta Ads active integration">

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.
2. Search for Meta ads and then select it.
3. Click **Integrate**. You’re directed to the integration setup page.
4. In the **Integration** tab, turn on **Activate partner**.  
   **Note:** The toggle must stay on (<Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">activated</Anchor>) for as long as you work with the partner.
5. Under **General settings**:

   [![](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)

   * Paste your [Facebook app ID](#create-and-retreive-facebook-app-id) in the **Facebook App ID** field.
   * Paste the install referrer [decryption key from Meta ads](/docs/meta-ads-integration-setup#encrypted-data-from-google-play-referrer-api-or-meta-install-referrer).
6. Turn **Advanced data sharing on or off;** see [Advanced data sharing](#advanced_data_sharing) below. (Gradually available to all accounts by October 14, 2024.)
7. Turn **Advanced Matching data sharing on or off;** see [Advanced Matching data sharing](#advanced_matching_data_sharing) below.
8. Click **Save Integration**.

</Accordion>

<div id="optional--configure-recommended-settings" />

<Accordion title="[Optional] Configure recommended settings">

[![](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)

* To match with the click-through lookback window of Meta ads, set it to 7 days.  
  (Note that [there are some specific cases where the default is different](https://www.facebook.com/business/help/395050428485124?id=428636648170202).)
* To match Meta ads' view-through lookback window, set it to one day.
* The **Reinstall attribution** toggle is turned on by default for new integrations. Reinstall attribution lets you measure users who reinstall your app during their re-attribution window. No separate lookback window configuration is needed, as reinstall attribution uses the values from your install attribution settings. For more information, see <Anchor target="_blank" href="/marketers/docs/measure-reinstalls">Measure reinstalls</Anchor>.

</Accordion>

## Advanced Meta ads attribution setup

With basic attribution already set up for Meta ads, it's time for some quick advanced attribution setup.

<div id="getting-userlevel-data-for-android-installs" />

<Accordion title="Getting device-level data for Android installs">

#### Google Play Install Referrer API

Meta ads share campaign metadata with advertisers for Android app ads that direct users to the Google Play Store. In this case, attribution fields are available to advertisers in the Google Play Install Referrer API, which must be <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">integrated into your app.</Anchor> The fields provided via the Google Play install referrer API populate AppsFlyer raw data reports with the match type `gp_referrer`. This is only available once the decryption key is submitted and an install is attributed to Meta ads. This enables AppsFlyer to attribute users who don't have an advertising ID (LAT-enabled).

#### **Meta install referrer**

> 📘 **Note**
>
> Meta install referrer allows AppsFlyer to receive ad campaign metadata from a device’s local storage. See [the Dev Hub](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer) to learn how to enable the SDK to access the Meta install referrer.

In addition to the Google Play Install Referrer API, the Meta install referrer allows AppsFlyer to receive ad campaign metadata from a device’s local storage. This data is used for attribution measurement. The primary differences between the Google Play Install Referrer API and the Meta install referrer are:

* The Meta install referrer can include impression and click data, whereas the Google Play Install Referrer API is limited to click data
* The Meta install referrer potentially includes data from multiple sessions, whereas the Google Play Install Referrer API is limited to data from the last session only (the device must install the app in the same session as the click occurred)

As a result, you may see an increase in Meta-attributed installs in raw data reports. When an install is attributed via Google Play Install Referrer API or the Meta install referrer, the data is available in raw data reports. The fields that may be available for attribution via the Meta install referrer populate AppsFlyer raw data reports with a match type `fb_referrer` for attribution from the Facebook app and `ig_referrer` for attribution from the Instagram app. This is only available once the decryption key is submitted and an install is attributed to Meta ads. The Meta install referrer decryption key is the same key used for the Google Play Install Referrer and does not need to be provided to AppsFlyer a second time.

#### **Campaign attribution fields available via the referrer:**

* Ad ID
* Ad name
* Adset ID
* Adset name
* Campaign ID
* Campaign name
* Account ID
* Channel

> 📘 **Note**
>
> * **For the Google Play Install Referrer API:**
>   * AppsFlyer SDK must be **V5.4.0+** for the referrer data to be passed properly. Referrer data has priority over data provided by the API and isn't restricted. This solution applies to click-through attribution and not view-through attribution.
>   * The Channel field is determined by the channel value received from the Google Play Referrer API (sent to Google Play by Meta). If an empty string is received, the Channel field shows "None".
>
> * **For the Meta install referrer:** Refer to the <Anchor target="_blank" href="/marketers/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">prerequisites and required actions</Anchor> described in the bulletin.

#### Meta install referrer—FAQ

**In which cases is the Meta install referrer applicable for attribution?**

* For install attribution:
  * Click-through attribution, for all campaigns
  * View-through attribution is supported for all Advantage+ App Campaigns and Manual App Promotion Campaigns with broad targeting (for example, where age and gender are set to Default).

* Compatibility: Google Play Store and non-Google Play Android app stores
* Exclusions: This doesn't include campaigns redirecting to landing pages

**What is "broad targeting" used for in Meta ads?**

Broad targeting is required for receiving view-through install data. The supported campaign configuration includes:

* Age: Default setting (18-65+) is applied
* Gender: Default setting (All genders) is applied
* Location: Country groups and countries are supported. **Note:** For more targeted locations (such as cities or zip codes), campaigns utilizing inclusion targeting with these need to be set as relaxed.
* Detailed Targeting: Interest segments, behaviors, and advanced demographics are set as relaxed.
* Custom Audiences: Set as relaxed.
* For "relaxed", the "Advantage detailed targeting" box for ad campaigns must be selected: [![](https://files.readme.io/58ad1f360c324a4e53290f2aa6bc18e30efea0a08f37012342f2811bbb022c6a-30354145604369.png)](https://files.readme.io/58ad1f360c324a4e53290f2aa6bc18e30efea0a08f37012342f2811bbb022c6a-30354145604369.png)

#### Encrypted data from Google Play Referrer API or Meta install referrer

Data from either the Google Play Referrer API or the Meta install referrer is encrypted by Meta. This data can be decrypted using a key available to you in your Meta developer account. You must provide us with the decryption key described in the actions required row. The decryption key needs to be submitted only once per app.

Note that if the key is not provided or was deleted, there are some cases in which Meta ads is still attributed for the install based on the referrer - even without the campaign attribution fields (mentioned in the list above). This happens when:

* Meta ads didn’t claim the install
* The data received from the Google Play Install Referrer API was received but not decoded
* And this was the last click

**To get your decryption key from Meta:**

1. Log in to your Meta developer portal.
2. Navigate to **My Apps** in the upper right-hand corner.
3. Select the app for which you would like to access your decryption key.
4. Navigate to **Settings** > **Basic** on the left-hand side of the page. [![](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)
5. Scroll down to the Android section, and you will see your decryption key labeled Install Referrer decryption key underneath the Package Names field. Note: This is the same section in which you configured your package name and the Google Play Store.

**To set the decryption key in AppsFlyer:**

1. [Mandatory] Verify that AppsFlyer SDK V5.4+ is adopted in your app. Don't rely on earlier versions.
2. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.
3. Select **Meta ads**. [![](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)
4. In the **Integration** tab, paste the key in the |**Install Referrer Decryption Key**. This needs to be done only once per app.
5. Click **Save integration**.

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="Cost, clicks, and impressions">

[![meta_cost_tab.png](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)

This integration provides aggregated data on cost, clicks, and impressions for your campaigns, adsets, ads, and geos/countries. See the <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features.

**Note:** Data on clicks and impressions is included in the integration. However, **cost data requires an** <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview?query=xpend">**ROI360**</Anchor> **subscription**.

**To enable the cost API**:

1. Make sure you are logged into the Meta ads user account, which is enabled to handle the account's campaigns on Meta ads. The user signing in must have permission to run all the campaigns in Meta Business Manager.
2. Go to the **Cost** tab.
3. Turn on **Get Cost, Clicks and Impressions Data**.
4. Click the **f login** button. You can log in with a Meta ads business or admin account.
5. When prompted, allow AppsFlyer to access your Meta ads campaign data.  
   **Note**: In the first data sync after integration, as well as subsequent syncs, AppsFlyer receives Meta ads cost data for up to the last 7 days retroactively.

**To delete a connected Meta ads account:** In the actions column, hover over an account and click **Delete connection.**

> 📘 **Notes**
>
> * If you are already logged into Meta ads, when you click the **f login** button, the window immediately opens and closes. This is regular behavior.
> * If you have several users with permissions to Meta ads, the best practice is to perform the login for all of them to <Anchor target="_blank" href="/marketers/docs/meta-ads-faq#why-doesnt-cost-data-include-data-from-all-campaigns">avoid getting partial data</Anchor>.

#### Cost data sync status

<Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard or in the individual ad network dashboard. 

You can sync several accounts for pulling cost data. For each synced account, AppsFlyer shows the status of cost integration and the last time AppsFlyer managed to pull matching cost data.

Learn more about enriching your data with <Anchor target="_blank" href="/marketers/docs/meta-ads-faq#meta-ads-cost-faq">cost, clicks, and impressions data</Anchor>.

</Accordion>

<div id="inapp-event-mapping" />

<Accordion title="In-app event mapping">

[![meta_iae_postbacks.png](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)

**To map in-app events:**

1. Turn on **In-app event postbacks.**  
   When enabling the Meta ads in-app events mapping for an app **for the first time**, **af\_app\_open** is automatically mapped to **fb\_mobile\_activate\_app**.
2. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#custom-events">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on Meta ads. Possible mapping configurations are:<ul><li>**Text field:** Get the corresponding event ID from Meta ads</li><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li><li>**As is**: Send the events as they are, without name mapping.</li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: send postbacks only when this event is attributed to Meta ads.</li><li>**All media sources, including organic**: send postbacks for events attributed to any partner and organic events.</li></ul> |
| **including** | <ul><li>**No data (default)**: send only the event itself without the event value.</li><li>**Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: send all the parameters **excluding** the revenue value.</li></ul> |

3. To add an SDK or server-to-server event to the list, click **Add event**.

**Limitations regarding event names:**

* Length limitation of event names: 2-40 characters
* The following characters are not allowed:
  * Colon (:)
  * Period (.)
  * Non-Latin (English) character sets: As of January 12, 2020, Meta ads rejects Chinese characters. AppsFlyer has not tested other character sets, and you should use these only after verifying with Meta ads if they support these character sets in postbacks.
* Event names are case-sensitive. To avoid discrepancies, make sure you use the correct case in the event names for all media sources and app versions.

> 📘 **Note**
>
> Meta ads can optimize your campaigns based on your ad revenue data by <Anchor target="_blank" href="/marketers/docs/meta-ads-in-app-event-mapping#mapping-ad-revenue-data-for-campaign-optimization">mapping the af\_ad\_revenue event to the right Meta ads event</Anchor>.

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Retargeting attribution">

AppsFlyer retargeting attribution for Meta ads lets advertisers attribute an existing user's engagement with a Facebook ad, and measure the quality of the user, post engagement, using the AppsFlyer reports. It should be used only if you are actively running campaigns targeted at your own Facebook users.

1. <Anchor target="_blank" href="/marketers/docs/app-settings#reengagement-attribution">Turn on retargeting on the App Settings</Anchor> page.
2. On the Meta ads partner page, turn on **Re-engagement attribution**.
3. Set the **Re-engagement click-through lookback window**.  
   The re-engagement lookback window is the period of time, starting from an ad click, during which the app must be launched for the click to be recorded as a re-engagement.  
   Select the lookback window units (hours or days), and set the slider to the desired value.  
   [![](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)
4. Enable **Re-engagement view-through attribution**.
5. Set the **Re-engagement view-through lookback window** slider to the desired value (up to 24 hours). This is the period of time starting from an ad impression, during which the app must be launched for the impression to be recorded as a re-engagement.[![](https://files.readme.io/82028408b7475e6ad5bcd35f2d597b7f5344b9eca432157559265cf73bdb952c-30354145625873.png)](https://files.readme.io/82028408b7475e6ad5bcd35f2d597b7f5344b9eca432157559265cf73bdb952c-30354145625873.png)
6. Set the **Re-engagement window**.  
   This is the period when the user's in-app events are attributed to the retargeting media source as the primary source.  
   You can set the value in days (1-90), hours (up to 23), or even lifetime. The default is 30 days.  
   [![](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)

Learn more about <Anchor target="_blank" href="/marketers/docs/retargeting-attribution-guide">AppsFlyer retargeting attribution</Anchor>.

Learn more about <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns#deep-linking-with-srns">deep linking users from SRNs such as Meta ads</Anchor>.

#### WhatsApp retargeting campaign attribution

AppsFlyer supports the measurement of WhatsApp Marketing message campaigns used for re-engagement via deep link attribution on both iOS and Android.

When the **re-engagement** toggle is enabled at both the **integration level** and the **app level**, these campaigns are measured automatically, with no additional setup required.

In your attribution data, the **channel** field will display **"WhatsApp"** for these campaign types.

</Accordion>

<div id="advanced_data_sharing" />

<Accordion title="Advanced data sharing">

When **Advanced data sharing** is turned on, Meta receives postbacks and events with device-level identifiers for all devices, including devices that have not made their Advertising ID (IDFA) available.

Furthermore, when **Advanced Data Sharing** is turned on, AppsFlyer attributes these events. When turned off, only postbacks and events from devices with an IDFA are sent and attributed.

This method attributes iOS click-through and view-through installs, as well as iOS deep link re-engagements, for single and dual-opt-out devices. Attribution is based on last-touch attribution with a maximum attribution window of 24 hours.

> 📘 **Note**
>
> If the **Advanced Data Sharing** toggle is turned on and you’re not receiving attribution with Meta, check if the shared events meet Meta's eligibility criteria. See <Anchor target="_blank" href="https://www.facebook.com/business/help/716239976391518?id=1877298665783613">Meta documentation</Anchor>

</Accordion>

<div id="advanced_matching_data_sharing" />

<Accordion title="Advanced Matching data sharing">

When **Advanced Matching data sharing** is turned on, Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, hashed last name, and Facebook login ID, are shared with Meta if these fields are included in the event information sent to AppsFlyer. For more information, see: <Anchor target="_blank" href="/marketers/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor>.

</Accordion>

<div id="use-deep-links-in-meta-ads-campaigns" />

<Accordion title="Use deep links in Meta Ads campaigns">

When running Meta Ads campaigns, you can use deep links to send users directly to a specific in-app page or experience. The sections below describe how to set up ,AppsFlyer deep linking in Meta Ads

Before selecting a campaign objective, make sure your app uses one of the following supported deep link (DL) formats:

* AppsFlyer OneLink, if the app has Universal Links or Android App Links integration
* Apple Universal Links
* Android App Links
* Custom URI schemes
* Facebook App Links

The table below describes which Meta Ads campaign objectives support direct deep links and deferred deep links (DDL), along with setup instructions and limitations for each.

| Campaign objective | Direct deep link | Deferred deep link (DDL) | Setup | Limitations and prerequisites |
| --- | --- | --- | --- | --- |
| App Promotion / Install | Supported | Supported | Enter the DDL URL in the **Deferred Deep Link** field at the ad level, in the **Destination** section. | <ul><li>In iOS, DDL is supported only in <Anchor target="_blank" href="/marketers/docs/meta-ads-aggregate-event-measurement-aem-for-ios">AEM enabled apps</Anchor> or apps with double consent (Meta + App)</li><li>DDL requires the Facebook SDK for iOS and Android.</li></ul> |
| Sales | Supported | Not supported | Configure at the ad set level under **Conversion**, or use Catalog settings. You can override catalog deep links with a website URL if needed. | <ul><li>Requires **Enable Install Tracking** to be active.</li><li>The destination must be a mobile app.</li></ul> |
| Traffic | Supported | Not supported | Configure at the ad set level under **Conversion**. Supports fallbacks to the App Store or a website. | <ul><li>Requires **Enable Install Tracking** to be active.</li></ul> |
| Awareness | Supported | Not supported | Configure at the ad level in the **Destination** section. | <ul><li>Requires **Enable Install Tracking** to be active.</li></ul> |
| Leads | Supported | Not supported | Configure at the ad set level under **Conversion**. | <ul><li>Requires **Enable Install Tracking** to be active.</li></ul> |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink guide</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Create deep linking and redirection links for your campaigns with OneLink</Anchor>

</Accordion>

<div id="comply-with-california-consumer-privacy-act-ccpa" />

<Accordion title="Comply with California Consumer Privacy Act (CCPA)">

Complying with CCPA privacy regulations limits the data coming from Meta ads users based in California, USA.

**To enable compliance with CCPA:** Turn on **Limit Meta ads use of users' personal information (CCPA)** in the **Integration** tab.

Learn more about <Anchor target="_blank" href="/marketers/docs/send-opendsr-api-requests">data protection laws</Anchor>.

</Accordion>

<div id="ad-revenue-recording" />

<Accordion title="Ad revenue recording">

[![](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)

If your app uses Meta Audience Network Ad Revenue for ad monetization, you can record your revenues from Meta ads on AppsFlyer. This, with or without in-app purchase revenue data, gives you a **complete picture of your user revenues**.

#### Record Meta Audience Network Ad Revenue

1. On the **Ad Revenue** tab and turn on **Get ad revenue data**.
2. Select the type of aggregated ad revenue data you want to receive: **Attributed revenue** and/or **Aggregated monetization revenue**:
   * **Attributed Revenue**: Revenue based on the user acquisition source.  
     Set the **Event Source**, which is the event representing your ad revenue model in the best possible way. For example, if your revenue is based on impressions, it is recommended to send AppsFlyer an ad\_viewed event. The best event can be configured for each monetization platform separately. However, it is also possible to use the `af_app_opened` event. In this case, ad revenue is attributed for every app open performed by the user.
   * **Aggregated monetization revenue**: Revenue based on the ad source.
3. The **Ad Revenue Event** is displayed. It is a read-only field presenting the new ad revenue event called [source event]\_monetized (for example, Ad\_Watched\_Monetized as displayed above). The ad revenue event is presented in the dashboard as an additional event.
4. Click **Connect to Meta ads** to enable the collection of Meta Audience Network Ad Revenue on Meta ads. Log in with your Meta ads credentials to authorize Meta Audience Network Ad Revenue.
5. Enter the **Audience Network App ID (**[**Facebook App ID**](/docs/meta-ads-integration-setup#facebook-app-id)). Get this from Meta Audience Network.
   * Get the [Facebook App ID](/docs/meta-ads-integration-setup#facebook-app-id).
   * Copy the ID to the **Audience Network App ID** field in AppsFlyer.
6. Click **Save ad revenue**.

</Accordion>

<div id="permissions" />

<Accordion title="Permissions">

Enable Meta ads to perform various actions and to access your data according to the available permissions.

Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">granting permissions to integrated partners</Anchor>.

</Accordion>

## Aggregate Event Measurement (AEM) for iOS

AppsFlyer supports the <Anchor target="_blank" href="/marketers/docs/meta-ads-aggregate-event-measurement-aem-for-ios">Meta ads Aggregated Event Measurement (AEM)</Anchor>. This solution helps optimize iOS conversions and in-app events while also attributing iOS re-engagements on Meta ads.

## Meta ads integration troubleshooting

If you have completed the basic integration and still not seeing results from Meta ads on the AppsFlyer dashboard, first verify that you have new installs from Meta ads since the integration.

If so, please consult the main reasons below for solving this issue:

<div id="no-idfa-collection" />

<Accordion title="No IDFA collection">

As stated in the SDK Integration Guide - iOS, you must add the AdSupport.framework to your project for IDFA collection to take place. Check the Installation Raw Data report to see if the IDFA column is indeed empty or not. It is recommended to enable your app to collect IDFA in the case of iOS apps and GAID in the case of Android apps.  
Starting iOS 14.5 you'll have to display the Apple ATT prompt and get user consent before you can collect IDFA.

**Note:** SKAdNetwork attribution isn't impacted by the availability of IDFA. However, make sure that you enable the iOS 14 Campaign toggle on Meta ads while setting up iOS 14 campaigns.

</Accordion>

<div id="wrong-facebook-app-id" />

<Accordion title="Wrong Facebook App ID">

The Facebook App ID was configured incorrectly in AppsFlyer.  
Verify that the app ID is correct and matches the value in the Meta ads dashboard.  

Note - you can also use <Anchor target="_blank" href="https://developers.facebook.com/tools/explorer/?method=GET&path=&version=v6.0">Facebook's Graph API</Anchor> to validate your Facebook App ID.

</Accordion>

<div id="app-status-on-meta-ads" />

<Accordion title="App status on Meta ads">

The app must be defined on Meta ads as **Live** rather than **In development** for attribution to work.

[![](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)

</Accordion>

<div id="wrong-type-of-meta-ads-campaign" />

<Accordion title="Wrong type of Meta ads campaign">

Make sure the Meta ads campaign is for **Mobile app install ads** or **Mobile App Engagement**. For other campaign objectives, to measure mobile installs, the advertiser must <Anchor target="_blank" href="/marketers/docs/attributing-app-installs-to-non-mobile-ads-from-meta-ads">check the **App Event recording** option</Anchor> when defining the Meta ads campaign.

<div id="aem-attribution-is-not-working" />

<Accordion title="AEM attribution is not working">

If the **Advanced Data Sharing** toggle is turned on and you’re not receiving attribution with Meta, check if the shared events meet Meta's eligibility criteria. See [Meta documentation](https://www.facebook.com/business/help/716239976391518?id=1877298665783613).

</Accordion>

</Accordion>

<div id="meta-ads-app-install" />

<Accordion title="Meta ads app install">

When setting up the Meta ads app install campaign, you can select the app from a dropdown list or paste the full store URL to the app. While both work for you on Meta ads, the second method fails AppsFlyer attribution.

Correct set-up - attribution works.

[![](https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png)](https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png)

Incorrect set-up - attribution fails.

[![](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)

</Accordion>

### iOS 14 updates relating to Meta ads

AppsFlyer confirms that our MMP integration with Meta ads always implements the *Advertiser Tracking Enabled* flag. Meaning, no action is required of you in AppsFlyer. This information is provided pursuant to the Meta ads app guidance iOS 14 checklist dated February 2021.

> 📄 **See also**
>
> * For iOS 14-related considerations, see <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-interoperation-with-meta-ads">Meta ads SKAN interoperation</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/configuring-meta-campaign-management-partners">Meta campaign management partners configuration</Anchor> (<Anchor target="_blank" href="/marketers/docs/bidalgo-meta-campaign-management-partner-configuration">Bidalgo</Anchor> / <Anchor target="_blank" href="/marketers/docs/kenshoo-meta-campaign-management-partner-configuration">Kenshoo</Anchor> / <Anchor target="_blank" href="/marketers/docs/adquant-meta-campaign-management-partner-configuration">Adquant</Anchor> / <Anchor target="_blank" href="/marketers/docs/webpals-mobile-meta-campaign-management-partner-configuration">Webpals</Anchor>)

<div data-zendesk-anchors="facebook-ads-setup-guide=meta-ads-setup-guide 01H7YJVNMSZ4WG4HWBZF648HZN=meta-ads-setup-guide basic-facebook-attribution-setup=basic-meta-ads-attribution-setup 01H7YJVNMTFW076FAJZGJWT4R9=basic-meta-ads-attribution-setup h_01JXYJW7AFB53PY7WHGM05HDMH=create-and-retreive-facebook-app-id h_01JKX03GC8ZSMGCSX84381QW0A=enable-meta-ads-device-level-data h_01JYPKG2RH3R08604V7B3NC5WQ=important h_01JXYHEFW19DJXXXRNN186E07B=set-the-meta-ads-active-integration %5Boptional%5D-configure-recommended-settings=optional--configure-recommended-settings h_01JXYHEFW15E6K39JY2VBCN79E=optional--configure-recommended-settings advanced-facebook-attribution-setup=advanced-meta-ads-attribution-setup 01H7YJVNMTHF800PD5CEWPFS49=advanced-meta-ads-attribution-setup h_01JKX03GC8B4VKC6KJT4CZ9VT8=getting-userlevel-data-for-android-installs h_01JKX2BE00WYHMJ3RX1FK8DQV5=google-play-install-referrer-api h_01JKX2BNRDHHNJCN257H3QBZ65=meta-install-referrer h_01JKX03GC8JRZSD13TVDDM1MWE=note h_01JKX2CF8RE4T5R3V83FS1PBQR=campaign-attribution-fields-available-via-the-referrer h_01JKX03GC9BG4GFDKR7JHG31BQ=note-1 meta-install-referrer%E2%80%94faq=meta-install-referrerfaq h_01JKX2DSY85X6570AHYKHM34KS=meta-install-referrerfaq h_01JKX2E4A44QHKADG4S8ZM9KC5=encrypted-data-from-google-play-referrer-api-or-meta-install-referrer 01H7YJVNMTBN9RJ6Q7TJ1AJ0XX=cost-clicks-and-impressions 01H7YJVNMTGRBQG54DVMJDHDKS=notes 01H7YJVNMTRQAYG7TY29AX4MZS=cost-data-sync-status 01H7YJVNMTNRREKWY96CK9JJKV=inapp-event-mapping 01H7YJVNMT2DRVR26F8CDDTWHP=note-2 01H7YJVNMV5AZ9G2KCKEFF1CSV=retargeting-attribution h_01KBZ2CAGX18ZZPXQGMPTEPSCP=whatsapp-retargeting-campaign-attribution 01H7YJVNMVSA4Y33MW6Q8Y777Y=advanced_data_sharing 01JDH9Y65409Y5E162NWJA25E3=note-3 h_01KPK96J1G0BY3PPEBN9RB005V=use-deep-links-in-meta-ads-campaigns h_01KPK96J1GZE9ZHQB5NHFCVAG6=see-also h_01JKTYRMD70ZGN31FSQ7BXF1HB=comply-with-california-consumer-privacy-act-ccpa 01H7YJVNMVWRG10SZY1B33H5EA=ad-revenue-recording 01H7YJVNMV1TTHKMMX4TFB2BF3=record-meta-audience-network-ad-revenue 01H7YJVNMVMW5BXWEP8BPX4D7E=permissions 01H7YJVNMVGFYMHE5FACTD9NS0=aggregate-event-measurement-aem-for-ios 01H7YJVNMVCAQ6ETKBGCAM31B9=meta-ads-integration-troubleshooting 01H7YJVNMV3YRF59RX87TJCT8D=no-idfa-collection 01H7YJVNMVHCYVWKDW5WWPX1A5=wrong-facebook-app-id 01H7YJVNMVE9QJAXQBD4P14C88=app-status-on-meta-ads 01H7YJVNMVBRVTT9HH7KM8P33B=wrong-type-of-meta-ads-campaign h_01JKTYRMD7YPGJRZXR4Y66BAHG=aem-attribution-is-not-working 01H7YJVNMV4G3VP40E6VFD7SJD=meta-ads-app-install ios-14-updates-relating-to-facebook=ios-14-updates-relating-to-meta-ads 01H7YJVNMVQP5PR6XDHTCPXVDC=ios-14-updates-relating-to-meta-ads h_01HDP0Y4CZBZEK5VZ6FG3T31JB=see-also-1" />
