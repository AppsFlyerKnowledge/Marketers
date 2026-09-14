---
title: "Meta Ads—integration setup"
excerpt: "Learn how to integrate Meta ads with AppsFlyer to attribute mobile app installations, configure advanced settings, and map in-app events."
---
Learn about integrating Meta ads with AppsFlyer.

## Meta ads setup guide

How long does it take to start attributing your Meta ads mobile app ads with AppsFlyer?

If you already have the [AppsFlyer SDK integrated into your app](https://support.appsflyer.com/hc/sections/6551164458257-Integrate-the-AppsFlyer-SDK) and have already defined your app on Meta ads, the answer is less than a minute!

You don't need to implement Facebook Login or integrate your app with Facebook's SDK for mobile attribution. Just follow the [basic step-by-step setup](/docs/meta-ads-integration-setup#basic-facebook-attribution-setup) instructions below. Afterward, check out [advanced setup options](/docs/meta-ads-integration-setup#advanced-facebook-attribution-setup) for Meta ads.

## Basic Meta ads attribution setup

### Create and retrieve a Facebook App ID

To integrate Meta ads with AppsFlyer, first, create a [Facebook App ID](https://developers.facebook.com/docs/apps/register), then retrieve it.

**To create a Facebook App ID**:

1. On **Meta ads**, go to your [App Dashboard](https://developers.facebook.com/apps).
2. Under **Apps**, click **Create New App.**
3. Complete the app name and enter a unique namespace. Make sure to add the correct platform for your app; otherwise, installs might not be attributed correctly.

**To retrieve the Facebook App ID**:

1. On **Meta ads**, go to your [App Dashboard.](https://developers.facebook.com/apps)
2. Click the required app.
3. Click the App ID at the top left of the screen to copy it.

> 📘 Note
>
> AppsFlyer attributes data per App ID. The same Facebook App ID can be used for [both your Android and iOS apps](https://developers.facebook.com/docs/app-ads/app-setup/). Note that for iOS 14+, Meta ads limits ad accounts to nine accounts per app.

### Enable Meta ads device-level data

Starting June 17, 2025, Meta has re-enabled **Advanced Mobile Measurement (AMM)** reporting. Once you opt in, you’ll receive:

- Device-level mobile analytics
- Event-level attribution metrics for Meta campaigns
- Full integration with your existing AppsFlyer dashboards and exports

**To enable AMM, follow these steps:**

1. Visit [Meta Ads](https://business.facebook.com/business/loginpage/?next=https%3A%2F%2Fdevelopers.facebook.com%2Fadvanced_mobile_measurement%2Fterms).
2. Select the relevant app ID(s).
3. Accept Meta's Advanced Mobile Measurement terms.

> ❗️ Important!
>
> - An admin of your Meta developer app is required to accept Meta's AMM terms.
> - Device-level data with full attribution visibility is only available for new attributed devices after the AMM terms have been accepted.
> - In-app events inherit the restriction status of their attributed conversions. This means:
>   - If the in-app event is attributed to a conversion that occurred before signing the Advanced Mobile Measurement (AMM) agreement, the event remains restricted.
>   - If the in-app event is attributed to a conversion that occurred after signing the AMM agreement, the event is available in raw data reports.

### Set the Meta Ads active integration

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.
2. Search for Meta ads and then select it.
3. Click **Integrate**. You’re directed to the integration setup page.
4. In the **Integration** tab, turn on **Activate partner**.

> 📘 Note
>
> The toggle must stay on ([activated](https://support.appsflyer.com/hc/articles/360000844778)) for as long as you work with the partner.

5. Under **General settings**:
   - Paste your [Facebook app ID](/docs/meta-ads-integration-setup#create-and-retreive-facebook-app-id) in the **Facebook App ID** field.
   - Paste the install referrer [decryption key from Meta ads](https://support.appsflyer.com/hc/articles/207033826-Meta-ads-integration-setup#encrypted-data-from-google-play-referrer-api-or-meta-install-referrer).
6. Turn **Advanced data sharing on or off;** see [Advanced data sharing](/docs/meta-ads-integration-setup#advanced_data_sharing) below. (Gradually available to all accounts by October 14, 2024.)
7. Turn **Advanced Matching data sharing on or off;** see [Advanced Matching data sharing](/docs/meta-ads-integration-setup#advanced_matching_data_sharing) below.
8. Click **Save Integration**.

### [Optional] Configure recommended settings

> 👍 Recommended Settings
>
> - To match with the click-through lookback window of Meta ads, set it to 7 days. (Note that [there are some specific cases where the default is different](https://www.facebook.com/business/help/395050428485124?id=428636648170202).)
> - To match Meta ads' view-through lookback window, set it to one day.
> - The **Reinstall attribution** toggle is turned on by default for new integrations. Reinstall attribution lets you measure users who reinstall your app during their re-attribution window. No separate lookback window configuration is needed, as reinstall attribution uses the values from your install attribution settings. For more information, see [Measure reinstalls](/docs/measure-reinstalls).

## Advanced Meta ads attribution setup

With basic attribution already set up for Meta ads, it's time for some quick advanced attribution setup.

### Getting device-level data for Android installs

#### Google Play Install Referrer API

Meta ads share campaign metadata with advertisers for Android app ads that direct users to the Google Play Store. In this case, attribution fields are available to advertisers in the Google Play Install Referrer API, which must be [integrated into your app.](https://support.appsflyer.com/hc/articles/207032066#attribute-apps-published-on-google-play) The fields provided via the Google Play install referrer API populate AppsFlyer raw data reports with the match type `gp_referrer`. This is only available once the decryption key is submitted and an install is attributed to Meta ads. This enables AppsFlyer to attribute users who don't have an advertising ID (LAT-enabled).

#### Meta install referrer

> 📘 Note
>
> Meta install referrer allows AppsFlyer to receive ad campaign metadata from a device’s local storage. See [the Dev Hub](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer) to learn how to enable the SDK to access the Meta install referrer.

In addition to the Google Play Install Referrer API, the Meta install referrer allows AppsFlyer to receive ad campaign metadata from a device’s local storage. This data is used for attribution measurement. The primary differences between the Google Play Install Referrer API and the Meta install referrer are:

- The Meta install referrer can include impression and click data, whereas the Google Play Install Referrer API is limited to click data
- The Meta install referrer potentially includes data from multiple sessions, whereas the Google Play Install Referrer API is limited to data from the last session only (the device must install the app in the same session as the click occurred)

As a result, you may see an increase in Meta-attributed installs in raw data reports. When an install is attributed via Google Play Install Referrer API or the Meta install referrer, the data is available in raw data reports. The fields that may be available for attribution via the Meta install referrer populate AppsFlyer raw data reports with a match type `fb_referrer` for attribution from the Facebook app and `ig_referrer` for attribution from the Instagram app. This is only available once the decryption key is submitted and an install is attributed to Meta ads. The Meta install referrer decryption key is the same key [used for the Google Play Install Referrer](https://support.appsflyer.com/hc/articles/32588692156945--WIP-Meta-ads-integration-setup#encrypted-data-from-the-referrer) and does not need to be provided to AppsFlyer a second time.

**Campaign attribution fields available via the referrer:**

- Ad ID
- Ad name
- Adset ID
- Adset name
- Campaign ID
- Campaign name
- Account ID
- Channel

> 📘 Note
>
> - **For the Google Play Install Referrer API:**
>   - AppsFlyer SDK must be **V5.4.0+** for the referrer data to be passed properly. Referrer data has priority over data provided by the API and isn't restricted. This solution applies to click-through attribution and not view-through attribution.
>   - The Channel field is determined by the channel value received from the Google Play Referrer API (sent to Google Play by Meta). If an empty string is received, the Channel field shows "None".
> - **For the Meta install referrer:** Refer to the [prerequisites and required actions](/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe) described in the bulletin.

<Accordion title="Meta install referrer—FAQ">

**In which cases is the Meta install referrer applicable for attribution?**

- For install attribution:
  - Click-through attribution, for all campaigns
  - View-through attribution is supported for all Advantage+ App Campaigns and Manual App Promotion Campaigns with broad targeting (for example, where age and gender are set to Default).
- Compatibility: Google Play Store and non-Google Play Android app stores
- Exclusions: This doesn't include campaigns redirecting to landing pages

**What is "broad targeting" used for in Meta ads?**

Broad targeting is required for receiving view-through install data. The supported campaign configuration includes:

- Age: Default setting (18-65+) is applied
- Gender: Default setting (All genders) is applied
- Location: Country groups and countries are supported. **Note:** For more targeted locations (such as cities or zip codes), campaigns utilizing inclusion targeting with these need to be set as relaxed.
- Detailed Targeting: Interest segments, behaviors, and advanced demographics are set as relaxed.
- Custom Audiences: Set as relaxed.
- For "relaxed", the "Advantage detailed targeting" box for ad campaigns must be selected.

</Accordion>

#### Encrypted data from Google Play Referrer API or Meta install referrer

Data from either the Google Play Referrer API or the Meta install referrer is encrypted by Meta. This data can be decrypted using a key available to you in your Meta developer account. You must provide us with the decryption key described in the actions required row. The decryption key needs to be submitted only once per app.

Note that if the key is not provided or was deleted, there are some cases in which Meta ads is still attributed for the install based on the referrer - even without the campaign attribution fields (mentioned in the list above). This happens when:

- Meta ads didn’t claim the install
- The data received from the Google Play Install Referrer API was received but not decoded
- And this was the last click

**To get your decryption key from Meta:**

1. Log in to your Meta developer portal.
2. Navigate to **My Apps** in the upper right-hand corner.
3. Select the app for which you would like to access your decryption key.
4. Navigate to **Settings** > **Basic** on the left-hand side of the page.
5. Scroll down to the Android section, and you will see your decryption key labeled Install Referrer decryption key underneath the Package Names field. Note: This is the same section in which you configured your package name and the Google Play Store.

**To set the decryption key in AppsFlyer:**

1. [Mandatory] Verify that AppsFlyer SDK V5.4+ is adopted in your app. Don't rely on earlier versions.
2. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.
3. Select **Meta ads**.
4. In the **Integration** tab, paste the key in the | **Install Referrer Decryption Key**. This needs to be done only once per app.
5. Click **Save integration**.

### Cost, clicks, and impressions

<Image src="https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png" alt="Meta Cost Tab" />

This integration provides aggregated data on cost, clicks, and impressions for your campaigns, adsets, ads, and geos/countries. See the [ad network cost integration table](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features.

**Note:** Data on clicks and impressions is included in the integration. However, **cost data requires an** [**ROI360**](/docs/roi360-cost-aggregation-overview) **subscription**.

**To enable the cost API**:

1. Make sure you are logged into the Meta ads user account, which is enabled to handle the account's campaigns on Meta ads. The user signing in must have permission to run all the campaigns in Meta Business Manager.
2. Go to the **Cost** tab.
3. Turn on **Get Cost, Clicks and Impressions Data**.
4. Click the **f login** button. You can log in with a Meta ads business or admin account.
5. When prompted, allow AppsFlyer to access your Meta ads campaign data.

**Note**: In the first data sync after integration, as well as subsequent syncs, AppsFlyer receives Meta ads cost data for up to the last 7 days retroactively.

**To delete a connected Meta ads account:** In the actions column, hover over an account and click **Delete connection.**

> 📘 Notes
>
> - If you are already logged into Meta ads, when you click the **f login** button, the window immediately opens and closes. This is regular behavior.
> - If you have several users with permissions to Meta ads, the best practice is to perform the login for all of them to [avoid getting partial data](https://support.appsflyer.com/hc/articles/4410472805649#why-doesnt-cost-data-include-data-from-all-campaigns).

#### Cost data sync status

[View your cost API status](https://support.appsflyer.com/hc/articles/360008850257#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard or in the individual ad network dashboard.

You can sync several accounts for pulling cost data. For each synced account, AppsFlyer shows the status of cost integration and the last time AppsFlyer managed to pull matching cost data.

Learn more about enriching your data with [cost, clicks, and impressions data](https://support.appsflyer.com/hc/articles/4410472805649#facebook-ads-cost-faq).

### In-app event mapping

<Image src="https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png" alt="Meta In-App Event Postbacks" />

**To map in-app events:**

1. Turn on **In-app event postbacks.**

When enabling the Meta ads in-app events mapping for an app **for the first time**, **af_app_open** is automatically mapped to **fb_mobile_activate_app**.
2. Fill in the following parameters:

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br>**Tip**: Don't see the event you are looking for?<br>   - Make sure to activate the event on a device with a non-organic installation and recheck.<br>   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](https://support.appsflyer.com/hc/articles/208439256#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on Meta ads. Possible mapping configurations are:<br>   - **Text field:** Get the corresponding event ID from Meta ads<br>   - **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br>   - **As is**: Send the events as they are, without name mapping. |
| **for users from** | Select the sending option for the event:<br>   - **This partner only**: send postbacks only when this event is attributed to Meta ads.<br>   - **All media sources, including organic**: send postbacks for events attributed to any partner and organic events. |
| **including** | - **No data (default)**: send only the event itself without the event value.<br>   - **Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event).<br>   - **Values without revenue**: send all the parameters **excluding** the revenue value. |

3. To add an SDK or server-to-server event to the list, click **Add event**.

**Limitations regarding event names:**

- Length limitation of event names: 2-40 characters
- The following characters are not allowed:
  - Colon (:)
  - Period (.)
  - Non-Latin (English) character sets: As of January 12, 2020, Meta ads rejects Chinese characters. AppsFlyer has not tested other character sets, and you should use these only after verifying with Meta ads if they support these character sets in postbacks.
- Event names are case-sensitive. To avoid discrepancies, make sure you use the correct case in the event names for all media sources and app versions.

> 📘 Note
>
> Meta ads can optimize your campaigns based on your ad revenue data by [mapping the af_ad_revenue event to the right Meta ads event](/docs/meta-ads-in-app-event-mapping#mapping-ad-revenue-data-for-campaign-optimization).

### Retargeting attribution

AppsFlyer retargeting attribution for Meta ads lets advertisers attribute an existing user's engagement with a Facebook ad, and measure the quality of the user, post engagement, using the AppsFlyer reports. It should be used only if you are actively running campaigns targeted at your own Facebook users.

1. [Turn on retargeting on the App Settings](https://support.appsflyer.com/hc/articles/211719806#reengagement-attribution) page.
2. On the Meta ads partner page, turn on **Re-engagement attribution**.
3. Set the **Re-engagement click-through lookback window**.

The re-engagement lookback window is the period of time, starting from an ad click, during which the app must be launched for the click to be recorded as a re-engagement.

Select the lookback window units (hours or days), and set the slider to the desired value.

4. Enable **Re-engagement view-through attribution**.
5. Set the **Re-engagement view-through lookback window** slider to the desired value (up to 24 hours). This is the period of time starting from an ad impression, during which the app must be launched for the impression to be recorded as a re-engagement.
6. Set the **Re-engagement window**.

This is the period when the user's in-app events are attributed to the retargeting media source as the primary source.

You can set the value in days (1-90), hours (up to 23), or even lifetime. The default is 30 days.

Learn more about [AppsFlyer retargeting attribution](https://support.appsflyer.com/hc/articles/207033786-AppsFlyer-s-Retargeting-Attribution).

Learn more about [deep linking users from SRNs such as Meta ads](https://support.appsflyer.com/hc/articles/360001546905-About-self-reporting-networks-SRNs-#deep-linking-with-srns).

#### WhatsApp retargeting campaign attribution

AppsFlyer supports the measurement of WhatsApp Marketing message campaigns used for re-engagement via deep link attribution on both iOS and Android.

When the **re-engagement** toggle is enabled at both the **integration level** and the **app level**, these campaigns are measured automatically, with no additional setup required.

In your attribution data, the **channel** field will display **"WhatsApp"** for these campaign types.

### Advanced data sharing

When **Advanced data sharing** is turned on, Meta receives postbacks and events with device-level identifiers for all devices, including devices that have not made their Advertising ID (IDFA) available.

Furthermore, when **Advanced Data Sharing** is turned on, AppsFlyer attributes these events. When turned off, only postbacks and events from devices with an IDFA are sent and attributed.

This method attributes iOS click-through and view-through installs, as well as iOS deep link re-engagements, for single and dual-opt-out devices. Attribution is based on last-touch attribution with a maximum attribution window of 24 hours.

> 📘 Note
>
> If the **Advanced Data Sharing** toggle is turned on and you’re not receiving attribution with Meta, check if the shared events meet Meta's eligibility criteria. See [Meta documentation](https://www.facebook.com/business/help/716239976391518?id=1877298665783613)

### Advanced Matching data sharing

When **Advanced Matching data sharing** is turned on, Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, hashed last name, and Facebook login ID, are shared with Meta if these fields are included in the event information sent to AppsFlyer. For more information, see: [Advanced Matching Data Sharing](/docs/advanced-matching-data-sharing).

### Use deep links in Meta Ads campaigns

When running Meta Ads campaigns, you can use deep links to send users directly to a specific in-app page or experience. The sections below describe how to set up AppsFlyer deep linking in Meta Ads.

Before selecting a campaign objective, make sure your app uses one of the following supported deep link (DL) formats:

- AppsFlyer OneLink, if the app has Universal Links or Android App Links integration
- Apple Universal Links
- Android App Links
- Custom URI schemes
- Facebook App Links

The table below describes which Meta Ads campaign objectives support direct deep links and deferred deep links (DDL), along with setup instructions and limitations for each.

| Campaign objective | Direct deep link | Deferred deep link (DDL) | Setup | Limitations and prerequisites |
| --- | --- | --- | --- | --- |
| App Promotion / Install | Supported | Supported | Enter the DDL URL in the **Deferred Deep Link** field at the ad level, in the **Destination** section. | - In iOS, DDL is supported only in [AEM enabled apps](https://support.appsflyer.com/hc/articles/19228737402129-Meta-ads-Aggregate-Event-Measurement-AEM-for-iOS) or apps with double consent (Meta + App)<br>- DDL requires the Facebook SDK for iOS and Android. |
| Sales | Supported | Not supported | Configure at the ad set level under **Conversion**, or use Catalog settings. You can override catalog deep links with a website URL if needed. | - Requires **Enable Install Tracking** to be active.<br>- The destination must be a mobile app. |
| Traffic | Supported | Not supported | Configure at the ad set level under **Conversion**. Supports fallbacks to the App Store or a website. | - Requires **Enable Install Tracking** to be active. |
| Awareness | Supported | Not supported | Configure at the ad level in the **Destination** section. | - Requires **Enable Install Tracking** to be active. |
| Leads | Supported | Not supported | Configure at the ad set level under **Conversion**. | - Requires **Enable Install Tracking** to be active. |

#### See also

- [OneLink guide](/docs/onelink-guide)
- [Create deep linking and redirection links for your campaigns with OneLink](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink)

### Comply with California Consumer Privacy Act (CCPA)

Complying with CCPA privacy regulations limits the data coming from Meta ads users based in California, USA.

**To enable compliance with CCPA:** Turn on **Limit Meta ads use of users' personal information (CCPA)** in the **Integration** tab.

Learn more about [data protection laws](https://support.appsflyer.com/hc/articles/11332840660625).

### Ad revenue recording

If your app uses Meta Audience Network Ad Revenue for ad monetization, you can record your revenues from Meta ads on AppsFlyer. This, with or without in-app purchase revenue data, gives you a **complete picture of your user revenues**.

#### Record Meta Audience Network Ad Revenue

1. On the **Ad Revenue** tab and turn on **Get ad revenue data**.
2. Select the type of aggregated ad revenue data you want to receive: **Attributed revenue** and/or **Aggregated monetization revenue**:
   - **Attributed Revenue**: Revenue based on the user acquisition source.

     Set the **Event Source**, which is the event representing your ad revenue model in the best possible way. For example, if your revenue is based on impressions, it is recommended to send AppsFlyer an ad_viewed event. The best event can be configured for each monetization platform separately. However, it is also possible to use the `af_app_opened` event. In this case, ad revenue is attributed for every app open performed by the user.
   - **Aggregated monetization revenue**: Revenue based on the ad source.
3. The **Ad Revenue Event** is displayed. It is a read-only field presenting the new ad revenue event called [source event]_monetized (for example, Ad_Watched_Monetized as displayed above). The ad revenue event is presented in the dashboard as an additional event.
4. Click **Connect to Meta ads** to enable the collection of Meta Audience Network Ad Revenue on Meta ads. Log in with your Meta ads credentials to authorize Meta Audience Network Ad Revenue.
5. Enter the **Audience Network App ID (** [**Facebook App ID**](https://support.appsflyer.com/hc/articles/207033826#facebook-app-id) **).** Get this from Meta Audience Network.
   - Get the [Facebook App ID](https://support.appsflyer.com/hc/articles/207033826#facebook-app-id).
   - Copy the ID to the **Audience Network App ID** field in AppsFlyer.
6. Click **Save ad revenue**.

### Permissions

Enable Meta ads to perform various actions and to access your data according to the available permissions.

Learn more about [granting permissions to integrated partners](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).

## Aggregate Event Measurement (AEM) for iOS

AppsFlyer supports the [Meta ads Aggregated Event Measurement (AEM)](https://support.appsflyer.com/hc/articles/19228737402129). This solution helps optimize iOS conversions and in-app events while also attributing iOS re-engagements on Meta ads.

## Meta ads integration troubleshooting

If you have completed the basic integration and still not seeing results from Meta ads on the AppsFlyer dashboard, first verify that you have new installs from Meta ads since the integration.

If so, please consult the main reasons below for solving this issue:

### No IDFA collection

As stated in the SDK Integration Guide - iOS, you must add the AdSupport.framework to your project for IDFA collection to take place. Check the Installation Raw Data report to see if the IDFA column is indeed empty or not. It is recommended to enable your app to collect IDFA in the case of iOS apps and GAID in the case of Android apps.

Starting iOS 14.5 you'll have to display the Apple ATT prompt and get user consent before you can collect IDFA.

**Note:** SKAdNetwork attribution isn't impacted by the availability of IDFA. However, make sure that you enable the iOS 14 Campaign toggle on Meta ads while setting up iOS 14 campaigns.

### Wrong Facebook App ID

The Facebook App ID was configured incorrectly in AppsFlyer.

Verify that the app ID is correct and matches the value in the Meta ads dashboard.

Note - you can also use [Facebook's Graph API](https://developers.facebook.com/tools/explorer/?method=GET&path=&version=v6.0) to validate your Facebook App ID.

### App status on Meta ads

The app must be defined on Meta ads as **Live** rather than **In development** for attribution to work.

### Wrong type of Meta ads campaign

Make sure the Meta ads campaign is for **Mobile app install ads** or **Mobile App Engagement**. For other campaign objectives, to measure mobile installs, the advertiser must [check the **App Event recording** option](/docs/attributing-app-installs-to-non-mobile-ads-from-meta-ads) when defining the Meta ads campaign.

### AEM attribution is not working

If the **Advanced Data Sharing** toggle is turned on and you’re not receiving attribution with Meta, check if the shared events meet Meta's eligibility criteria. See [Meta documentation](https://www.facebook.com/business/help/716239976391518?id=1877298665783613).

### Meta ads app install

When setting up the Meta ads app install campaign, you can select the app from a dropdown list or paste the full store URL to the app. While both work for you on Meta ads, the second method fails AppsFlyer attribution.

### iOS 14 updates relating to Meta ads

AppsFlyer confirms that our MMP integration with Meta ads always implements the _Advertiser Tracking Enabled_ flag. Meaning, no action is required of you in AppsFlyer. This information is provided pursuant to the Meta ads app guidance iOS 14 checklist dated February 2021.

#### See also

- For iOS 14-related considerations, see [Meta ads SKAN interoperation](https://support.appsflyer.com/hc/articles/360017095198-SKAN-interoperation-with-Facebook)
- [Meta campaign management partners configuration](https://support.appsflyer.com/hc/articles/360000562569) ([Bidalgo](https://support.appsflyer.com/hc/articles/218002103-Bidalgo-Facebook-Ads-Marketing-Partner-campaign-configuration) / [Kenshoo](https://support.appsflyer.com/hc/articles/360001430625-Kenshoo-Facebook-Marketing-Partner-campaign-configuration) / [Adquant](https://support.appsflyer.com/hc/articles/360001425369-Adquant-FMP-campaign-configuration) / [Webpals](https://support.appsflyer.com/hc/articles/115000135126-Webpals-Mobile-Facebook-Ads-Marketing-Partner-campaign-configuration))