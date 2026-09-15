---
title: "Apple Ads integration setup"
excerpt: "Learn how to set up Apple Ads integration in AppsFlyer, configure agencies and marketing partners, and resolve reporting discrepancies."
---
Apple Ads, an AppsFlyer SRN (Self-Reporting Network) partner, helps users find your app in the App Store using keywords.

![medium_originaljpeg_apple_ads_logo_blk_highres_720 (1) (1).jpg](https://files.readme.io/f89d1a5ec1a1de2ec2dfdec7465465fc2be73e0cf41ddd6be8b2e3f62de3c9e8-47598828154001.jpg)

App relevance determines if your ad is the one displayed in response to a search query in the App Store. User response to an ad is a signal of ad relevance. Apple Ads uses user response as a signal in deciding which ads to display the most.

* AppsFlyer supports Apple Ads click-based mobile attribution, user retargeting, and cost data via API (with an ROI360 subscription).
* Starting March 27, 2025, AppsFlyer will also support Apple Ads impression-based mobile attribution.
* Starting September 1, 2026, Apple Ads adds an exact timestamp to all iOS attribution claims.

## Set up Apple Ads integration
<Accordion title="Get started">

``
Prerequisite
``The most recent version of the AppsFlyer iOS SDK is adopted
Set up Apple Ads in AppsFlyer:
The setup is done from the Active Integrations page, but to find new partners you must first go to the `[`Partner Marketplace](/docs/partner-integrations). Complete the configuration using the relevant tabs, as described below.
``
``Before setting up an integration, make sure you contact the partner and open an account with them.

</Accordion>
<Accordion title="Integration tab">

``
Apple Ads, an SRN, integrates with AppsFlyer via API. As such, there are no postback settings. Complete the following sections according to your attribution goals. 
``

| Section | Details |
| --- | --- |
| Integration activation | **To set up a new integration:**   1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab. 2. Select the relevant app. 3. Search for the partner and select **Integrate**. 4. In the **Integration** tab, turn on the **Activate partner** toggle. Keep it on as long as you work with the partner. 5. Complete the configuration using the relevant tabs, as described below.   **To edit an existing integration:**  In AppsFlyer, go to **Collaborate > Partner Integrations > Active integrations** tab, search for the partner, and make your changes. |
| Install click-through attribution | 1. **Set the Install click-through lookback window** Set the maximum time from ad click to install. Doing so enables AppsFlyer to attribute installs (first launches) taking place within the lookback window to Apple Ads.     * **Range:** 1–30 days    * **Default:** 30 days For more information, see [Lookback windows explained](/docs/set-up-lookback-windows).  1. **Pre-registration (Pre-order) campaigns measurement** If you run pre-registration campaigns for iOS apps, set the pre-registration campaign lookback window.  This slider determines the lookback window for attributing installs to pre-registration campaigns. The pre-registration lookback window allows attribution of installs that happen when pre-registered (pre-ordered) apps are released, linking them back to the original ad engagement.    * **Range:** 1–90 days    * **Default:** 90 days |
| Install view-through attribution | 1. **Set the install view-through lookback window** Set the maximum time from ad view to install. AppsFlyer attributes installs (first launches) that occur within this window to Apple Ads. **Note:** The install view-through lookback window slider supports only hours (max: 24h, default: 24h).     * **Range:** 1–24 hours    * **Default:** 24 hours For more information, see [Lookback windows explained](/docs/set-up-lookback-windows). 2. **Pre-registration (Pre-order) campaign measurement** If you run pre-registration campaigns for iOS apps, set the pre-registration campaign lookback window. This slider determines the lookback window for attributing installs to pre-registration campaigns. The Pre-registration lookback window allows attribution of installs that happen when pre-registered (pre-ordered) apps are released, linking them back to the original ad engagement.    * **Range:** 1–61 days    * **Default:** 61 days |
| Reinstalls | **Reinstall attribution**  If **Reinstall attribution is** on, AppsFlyer can attribute reinstalls to Apple Ads.  Reinstall attribution lookback window settings are set according to the install attribution settings.  If the user is within the [re-attribution window](/docs/set-up-re-attribution-window) (set at the time of the original install), the install is attributed to Apple Ads as a reinstall.  The reinstall can be seen in the retargeting view of the Overview dashboard.  The **Store reinstall** raw data field is set to true.  Currently Apple Ads retargeting does not support re-engagements. |
| **Inactivity window**  Set the user [inactivity threshold](/docs/set-retargeting-inactivity-window) (in days) to control the impact of retargeting campaigns. |
| Postbacks | Currently Apple Ads integration doesn't support postbacks. |

</Accordion>
<Accordion title="Cost tab">

``
The cost integration provides the following aggregated data:

``Cost data for your campaigns, adsets, geos/countries, and keywords. See the `[`ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features.`<br/>`Note: Cost data requires an ROI360 subscription.

``Data on clicks, impressions, and enriched data—keywords, campaign names, and adsets.

``
``
``The use of multiple Apple Ads accounts is supported. In other words, if you run campaigns for the same app using different Apple Ads accounts, AppsFlyer can receive this data from all accounts.
``Cost data for "campaign groups" is not supported by the Apple Ads reporting API, so "campaign group" data is not available in AppsFlyer.
``To sign in with Apple, you need Apple Ads Campaign Group Manage permissions (either Account Read Only or Account Read and Write).
``When you sign in with Apple, authorization of Apple Ads campaign groups isn't cumulative. This means that when you integrate a new app, the authorization for campaign groups chosen for the previous apps is revoked unless chosen again.
``When you sign in with Apple, you can't use a federated login. 

To enable cost, clicks, impressions, and enriched data:
``Follow `[`these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api)

`[`View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>
<Accordion title="Permissions tab">

```[`Setting ad network and agency permissions.](/docs/set-up-an-integrated-partner#permissions-tab)

</Accordion>

## Set up agencies and Apple Ads marketing partners
<Accordion title="Principles">

``
Apple Ads: Marketing partner vs. Agency
Advertisers and agencies can elect to work with Apple Ads Marketing Partners to report and optimize campaigns on Apple Ads. 
The differences between agencies and marketing partners are enumerated in the table that follows. 
``Agency vs. marketing partner
``

|  | Agency | Marketing partner |
| --- | --- | --- |
| AppsFlyer sends postbacks | No | Yes |
| Technology | Run campaigns on your behalf | Have a value add technology solution to optimize campaigns |

``Configuring agencies and marketing partners 
Use the checklist that follows to make sure you complete all steps in the configuration process. Detailed instructions are contained per partner type in the sections that follow. 
``Configuration steps checklist
``

| Configured by | Integration with an agency | Integration with a marketing partner |
| --- | --- | --- |
| Advertiser | 1. In AppsFlyer, in the Apple Ads integration tab, turn on **Activate partner.**<br />2. Select the agency, in the Agency permissions tab, turn on **Agency Permission.** | 1. In the Apple Ads integration tab, turn on **Activate partner.**<br />2. In the Apple Ads dashboard get the marketing partner's **Campaign Group ID.**<br />3. In the marketing partner's integration tab:<br />   1. Turn on **Activate partner.**<br />   2. Set Campaign Group.<br />   3. Configure in-app events postback. |
| Agency | In the Apple Ads integration tab, set **Apple Ads Campaign Group.** | 1. In the Apple Ads integration tab, turn on **Activate partner.**<br />2. In the Apple Ads dashboard get the marketing partner's **Campaign Group ID.**<br />3. In the marketing partner's integration tab:<br />   1. Turn on **Activate partner.**<br />   2. Set Campaign Group.<br />   3. Configure in-app events postback. |

</Accordion>
<Accordion title="Marketing partner setup">

``
To set up a marketing partner:

``If required, activate Apple Ads integration:
``In AppsFlyer, go to Configuration&gt; Active integration partners &gt; Apple Ads.
``Turn on Activate Partner.
``Click Save.

``
In your Apple Ads dashboard: Get the Apple Ads Campaign Group ID parameter related to the marketing partner. Use the screenshot that follows as a guide to locating the ID. 
```![ASACGroupID.png](https://files.readme.io/843f5e6b35470cddd6e502d50554b49b258f0d9f7952dced511aea73f471694e-31197514608145.png)`

``
In AppsFlyer, configure the Apple Ads marketing partner:
``In AppsFlyer, from the side menu, select Collaboration &gt; Active integrations.

``Search for the Apple Ads marketing partner.`<br/>`The list of marketing partners displays.
``Select a marketing partner.
``Turn on Activate Partner.
``Enter the partner's Apple Ads Campaign Group ID that you retrieved in the earlier step. Enter the digits (numbers) only.
``Click Save.

``[Optional] Configure in-app events postback:
``Turn on In-app events postback.

``Click Add event to add an SDK event to the list.
``Complete the following parameters:
``
SDK event name: The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events. Tip: If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck.
``
Send revenue: Select one of the following: No values and no revenue, Values and no revenue, or Values and revenue.

``
Click Save integration.

</Accordion>
<Accordion title="Agency setup">

``
Advertisers permit agencies to run campaigns on their behalf using Apple Ads. Both advertisers and agencies perform setup actions in AppsFlyer as described in this section. 
Prerequisites
Before configuring an agency on AppsFlyer, both the agency and the advertiser must take the following steps on the Apple Ads platform:

``
Agency:
``Create separate campaign groups within the agency account.
``Invite the advertiser as a Campaign Group Manager or through the Link Accounts role to connect their App Store Connect account.

``
Advertiser: After receiving the invitation to link accounts, the advertiser must link the campaign groups to its App Store Connect account.

See Apple Ads documentation on `[`How to link a client’s App Store Connect account to an agency account.](https://searchads.apple.com/help/get-started/0012-link-app-store-connect-accounts)
Apple Ads campaign group

``Agency campaigns and advertiser campaigns must be separate Apple Ads ID campaign groups.
``Don't use special characters and spaces for the group name.
``When you sign in with Apple, authorization of Apple Ads campaign groups isn't cumulative. This means that when you integrate a new app, the authorization for campaign groups chosen for the previous apps is revoked unless chosen again. You will need to select Limited Access and each of the relevant campaign groups (related to the apps you want to connect for the advertiser).

``Advertiser actions
Prerequisite:
`[`Grant permission to an agency](/docs/set-up-an-integrated-partner#agency-permissions). 
To enable attribution of Apple Ads the advertiser:

``In AppsFlyer, from the side menu, select Collaboration &gt; Active integrations.

``Select Apple Ads.

``Go to the Integration tab, switch on Activate partner.
``[Optional] If you want to attribute users who reinstall the app during the re-attribution window, switch on Reinstall attribution.

``Click Save.

``Agency actions

``
In your Apple Ads dashboard: Get your Campaign Group ID. Use the screenshot that follows as a guide to locating the ID. Get only the digits.
```![ASACGroupID.png](https://files.readme.io/843f5e6b35470cddd6e502d50554b49b258f0d9f7952dced511aea73f471694e-31197514608145.png)`

``In AppsFlyer, select an App.
``From the side menu, select Collaboration &gt; Active integrations.
``Select Apple Ads.

``Enter the Apple Ads Campaign ID parameter. Note! Enter digits (numbers only)
``Click Save. 

``
``When an agency works with an Apple Ads Marketing Partner, the agency must configure the same campaign group ID in both the Apple Ads configuration page and the Marketing Partner configuration page.

``Cost, clicks, and impressions data
If you enable cost API, AppsFlyer receives cost, clicks, and impression data from Apple Ads via API. See the `[`ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. Note: Cost data requires an ROI360 subscription. Without ROI360, only click and impression data is received. 
To enable the cost API:
````Follow `[`these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api). Make sure that when prompted to log into your Apple Ads account in Select permissions, select one of the following:``
``Account Read and Write
``
Account Read Only`<br/>`Note: If you choose Limited Access and a specific campaign group, you may encounter data errors. 

`[`View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.
``
``Apple Ads cost data isn’t available in the SKAdNetwork (SKAN) dashboard or SKAN Pull API because SKAN postbacks don’t include campaign-level data. However, cost data is available in SSOT reports, which combine SKAN install data with cost information retrieved via our classic Apple Ads integration.

</Accordion>
<Accordion title="Disable agencies and marketing partners">

``
To stop recording attribution of Apple Ads installs generated by agencies or marketing partners: 

``In AppsFlyer, from the side menu, select Collaboration &gt; Active integrations.

``Select the agency or marketing partner as the case may be.
``Delete the content of the Apple Ads Campaign Group ID field.

``Click Save integration. 

</Accordion>

## Additional information
<Accordion title="Apple Ads attribution">

``
Apple Ads functions independently of SKAdNetwork and deterministically attributes users, regardless of ATT (App Tracking Transparency) consent. This means that for users attributed to Apple Ads, you have the full range of features and measurements provided by our `[`LTV attribution model.](/docs/appsflyer-attribution-model)
Apple Ads attribution doesn't rely on IDFA, attribution is done using a token from the device (deterministic attribution).
``After September 1, 2026
Click and impression time is available regardless of ATT status. The lookback window is set by the advertiser, and AppsFlyer applies its last-touch attribution rules to the engagement.
``Before September 1, 2026
Click and impression time availability and the lookback window differ according to ATT consent:
``

| **ATT consent** | **Click/impression time available** | **Click/Impression lookback window** | **Remarks** |
| --- | --- | --- | --- |
| Yes | Yes | Set by the advertiser | AppsFlyer last-touch attribution rules used |
| No | No | Clicks: 30 days (set by Apple Ads), Impressions: 24h | No click or impression time is provided. Priority is given to deterministic candidates |

</Accordion>
<Accordion title="Discrepancies">

``
AppsFlyer and Apple Ads use different attribution logic resulting in discrepancies between the platforms. `[`Apple Ads](/docs/self-reporting-networks-srns#attribution), an SRN, reports new installs by API. 
Apple Ads reporting to AppsFlyer by API

``Campaigns are aggregated by Geo.
``The following are not reported: Impressions, taps, or cost of Geos having less than 100 impressions for a given campaign.
``When grouping by Geo in AppsFlyer, Geos with unavailable data are not shown, and the total of unavailable data appears under N/A.

``Retargeting related discrepancies
The AppsFlyer retargeting attribution mechanism allows advertisers to measure and analyze retargeting campaigns, in addition to user acquisition campaigns.
The figures that follow show how discrepancies can occur in relation to retargeting campaigns (irrespective of the retargeting controls setting) running on Apple Ads.
Retargeting on
 
``
`![ASA R Enabled2.jpg](https://files.readme.io/0d26cc4844aa97adb793a266cb2a51961a1345e71a24eec305fcc16539d86027-31197524086801.jpg)`

 
Retargeting off
 
``
`![ASA_R_Disabled.png](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)`

 
``Additional reasons for discrepancies
The table that follows lists the main reasons for discrepancies.
``

| Discrepancy | Apple Ads | AppsFlyer |
| --- | --- | --- |
| Differences related to AppsFlyer SDK versions | Counts conversions irrespective of the AppsFlyer SDK version. | For AdsServices, SDK V6.1.3+ is required to attribute correctly. |
| Limit ad tracking (LAT) and ATT. | Always counts the conversion.<br /><br />If your campaign is limited by age and gender LAT users are excluded from the campaign.<br /><br />Apple users younger than 18 are always LAT. | LAT conversions are attributed to organic.<br /><br />If AdServices is implemented and iOS14.3+ is installed, then non-consented users are attributed correctly. |
| Counting users | Counts users based on downloads | Counts users based on first app open |
| Reinstall: A user, after installing the app, deletes it, clicks on an Apple Ad, then installs the app again | Counts as a conversion (install) | * With IDFA: AppsFlyer identifies the reinstall and does not count it for UA purposes. Tip! Enable retargeting and the reinstall is recorded as a retargeting install (AKA re-attribution)<br />* Without IDFA: AppsFlyer can rely on IDFV to determine whether this is a re-install or a new install:<br />  1. If one or more other apps of the vendor are installed on the device, AppsFlyer attributes Apple Ads with a re-attribution.<br />  2. Otherwise (no other app exists), AppsFlyer attributes Apple Ads with a new install. |
| Click lookback window | Fixed 30-day window | For responses from AdServices that don't have a click time, the click lookback window is fixed to a 30-day window. |
| Impression lookback window | Fixed 24-hour window | For responses from AdServices that don't have an impression time, the impression lookback window is fixed to a 24-hour window. |
| Pre-registration click and impression lookback window discrepancy |  | For responses from AdServices that don't have a click or impression time, the click or impression lookback window is fixed.<br /><br />* **Click**: 90 days<br />* **Impression**: 61 days |
| Winning click | Always attributes to itself if the user engaged and downloaded the app. | Has visibility across multiple networks, and attribute according to last-click methodology |
| Install time | App download time | First app open |
| Timezone | App store local timezone | UTC timezone or as set in AppsFlyer settings |
| Conversion data | It can take more than 5 seconds for AppsFlyer to be updated that Apple Ads brought the install | Attributes within 5 seconds at which time the Conversion data API responds. If no data has been received then the response is organic. |
| Cost data | Reports cost for all keywords | Doesn't report cost data for keywords containing uppercase letters in the cohort dashboard or cohort API. |
| Geo locations | Apple Ads allows advertisers to target users according to their country and region. Apple Ads supports a limited number of [**countries**](https://searchads.apple.com/storefronts/). | AppsFlyer recognizes the exact geographic location of the user based on the IP address, and so reports on Geos not available on Apple Ads.<br /><br />Tip! Users that install while being in the actual country of the app store have the same Geo data in AppsFlyer and Apple Ads |
| Missing conversion payload for gender or age targeted users (applies as of September 1, 2026) | May count these conversions in Apple Ads reporting, even though Apple does not provide an attribution claim for this cohort. | Ad groups with age or gender targeting return an attribution payload of false, so these users are not attributed to Apple Ads in AppsFlyer. This can cause Apple Ads to report more conversions than AppsFlyer for the affected ad groups. |

</Accordion>
<Accordion title="Tips">

``
Working with Apple Ads enables you to collect valuable marketing data, which can impact your user acquisition efforts with all media sources for your iOS apps.
Tips to help you maximize the benefits of using Apple Ads:
``

| Tip | Details |
| --- | --- |
| Get keyword data | Apple Ads shares keyword data with AppsFlyer. You can view the keyword data in raw data and analytics tools like Pivot, Retention, and Cohort.<br /><br />**Note:**<br /><br />* Obtaining keyword data may be delayed for 8-12 hours, and in some cases, may only include the keyword ID without the keyword term<br />* To obtain keyword data, the Cost toggle must be turned on. Keyword data is provided as part of the [Cost integration](/docs/apple-ads-integration-setup#cost-tab), without the need for an ROI360 subscription.<br /><br />If keyword data is missing in AppsFlyer, this can be caused by:<br /><br />* **Package type:** Keyword data is shared by Apple Ads with advertisers, that have the Apple Ads [advanced](https://searchads.apple.com/advanced/) package.<br />* **Campaign type:** You can configure different campaign keyword matching types in Apple Ads. Based on match type, Apple Ads shares the keywords as follows:<br />  * **Exact match**: The exact keywords searched for by the user<br />  * **Broad match**: The keywords Apple used to perform the search. These are similar to the user's actual search terms.<br />  * **Search match**: Apple does **not** share these keywords with advertisers.<br /><br />**Use only exact or broad match** search campaigns to receive complete keyword data. |
| Compare the quality of users based on keyword data | Not all keywords are equal meaning that while different keywords may cost the same the quality of users attracted could be different. Use the Retention or [Pivot](/docs/pivot-table-user-metrics) reports to identify the keywords that maximize your ROI. |
| Analyze keyword cost | The platform contains aggregate keyword cost data when Apple Ads keyword campaigns are configured as an [exact match or broad match](/docs/apple-ads-integration-setup#get-keyword-data). Keyword cost data has the following characteristics:<br /><br />* Historical data is available starting October 13, 2019.<br />* Dimensions:<br />  * Date<br />  * Campaign<br />  * Adset<br />* Analysis tools:<br />  * [Cohort](/docs/cohort-and-retention-dashboard)<br />  * [Pivot](/docs/pivot-table-user-metrics)<br />  * [Master API](/docs/master-api-user-acquisition-metrics-via-api)<br /><br />**Limitations**<br /><br />* Only use the noted dimensions to filter and group cost data queries. For example, don't filter or group using Geo.<br /><br />#### Examples<br /><br />#### Cohort Example<br /><br />The following example displays how to set up Cohort to view cost and ROI information.<br /><br />**Cohort setup**<br /><br />![CohortRequest.png](https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png)<br /><br />**Cohort result table**<br /><br />In the table that follows, the total cost and Cohort ROI is displayed<br /><br />![CohortTable.png](https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png)<br /><br />#### Pivot example<br /><br />**Pivot setup**<br /><br />![Pivot_define.png](https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png)<br /><br />**Pivot result table**<br /><br />![Pivot.png](https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png) |
| Find the best performing creative set | ![creative_sets.png](https://files.readme.io/ef8e38d67121283742dcbd1faef11d94a8ea1c612dc258611e72cbf826d7ef8f-31197524112785.png)<br /><br />It's good practice to test how leads respond to different creative sets you use. The best-performing creative sets have the highest conversion rates. In addition, the best creative sets convert users with a higher level of engagement.<br /><br />This impacts all your iOS leads, not only Apple Ads leads, for they all reach your app page in the app store. However, with Apple Ads installs, AppsFlyer indicates the creative set ID in the [raw data](/docs/raw-data-field-dictionary) **Ad ID** parameter, enabling you to compare the performance of different creative sets. |
| Target re-downloaders | Your past users are possibly the best audience for you to target using Apple Ads.<br /><br />A user, who uninstalled your app, and as a result of your Apple Ads retargeting campaign installs again, is called a Re-Downloader by Apple Ads. If the re-install is performed during the [re-attribution window](/docs/set-up-re-attribution-window), AppsFlyer calls this a Re-Attribution. In all other cases, it is treated as a new install.<br /><br />![ASACGroupID.png](https://files.readme.io/ebdc380f2abc3e9a3b134cd258d90ae32f75b3ee4d9eadde39adbc728daae523-31197514645265.png) |

</Accordion>
<Accordion title="Apple Ads change log">

````

| Effective date | Update/change |
| --- | --- |
| 2026-09-01 | As of September 1, 2026:<br /><br />* Apple's AdServices API adds an engagement timestamp to all iOS attribution claims, regardless of ATT status. AppsFlyer uses this timestamp to apply the advertiser's configured lookback window and last-touch attribution rules to these claims.<br />* For ad groups with age or gender targeting, Apple will return an attribution payload of false, meaning no SRN measurement can be applied for that targeted cohort.<br /><br />See Apple's AdServices developer documentation for details. |
| 2023-02-07 | The enriched attribution parameters `Campaign name`, `Adset name`, and `Keywords` are available only when the Cost tab is enabled, irrespective of your subscription plan.  <br />**This means that for your dashboards and raw data reports to show campaign names, adset names, or keywords, you must have the Cost tab enabled.** |
| 2022-02-16 | Keywords are available via Cost API. You must enable the API in the Apple Ads integration page. Note! The API is available to all advertisers irrespective of your subscription plan. |
| 2021-04-07 | Apple Ads integration: Apple Ads functions independently of SKAdNetwork and deterministically attributes users. This means that for users attributed to Apple Ads you have the full range of features and measurements provided by our [LTV attribution model.](/docs/appsflyer-attribution-model) |
| 2021-03-07 | Apple Ads is rolling out Campaign Management API V4.0. The API relates to cost and other campaign-related data. It has no impact on attribution. We are in the process of adopting the updated API. No action is required from you. |
| 2021-02-15 | Starting this date, the campaign name and adset name fields can be populated if you enable the Apple Ads [Cost API](/docs/apple-ads-integration-setup#cost-tab). The API is available to all advertisers irrespective of the subscription plan. |

Apple Ads updates and changes

</Accordion>
<Accordion title="Availability of Apple Ads campaign parameters">

``
The table below shows the availability of attribution parameters in raw data reports or on the dashboard.
``

| Raw data report parameter | Availability |
| --- | --- |
| Campaign name | For this parameter to be available, you must enable the [Cost](/docs/apple-ads-integration-setup#cost-tab) API on the Apple Ads integration page. The API is available to all advertisers, irrespective of their subscription plan |
| Campaign ID | Always available |
| Adset name | For this parameter to be available, you must enable the [Cost](/docs/apple-ads-integration-setup#cost-tab) API on the Apple Ads integration page. The API is available to all advertisers, irrespective of their subscription plan |
| Adset ID | Always available |
| Ad | Currently unavailable |
| Ad ID | This parameter is only available when both of the following conditions are met:<br /><br />* Users are on iOS 15.2 and later<br />* The ad uses<br /><br />  [Custom Product Pages](https://developer.apple.com/app-store/product-page/) for campaigns that are associated with either of the following ad placements:<br /><br />  * `Today tab`<br />  * `Search results` |
| Keywords | For this parameter to be available, you must enable the [Cost](/docs/apple-ads-integration-setup#cost-tab) API on the Apple Ads integration page. The API is available to all advertisers, irrespective of their subscription plan |
| Keyword ID | This parameter is available via raw data reports. However, it must be explicitly selected in Data Locker, Push API, and Export data. In the case of Pull API, add `keyword_id` to the  `&additional_fields` parameter [of the Pull API call](/docs/pull-api-raw-data#additional-fields). |
| Keyword Match Type | Currently unavailable |

</Accordion>
<Accordion title="Impact of Aggregated Advanced Privacy">

``
Starting in iOS 14, `[`ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) (ATT) governs the availability of IDFA, and Apple Ads controls the user-level attribution data of installs brought by Apple Ads. As such, the user-level data availability of installs brought by Apple Ads is not affected by `[`Aggregated Advanced Privacy](/docs/apply-aggregated-advanced-privacy-framework).
``After September 1, 2026
``

| **ATT consent** | **Click/impression time available** | **Click/Impression lookback window** | **Remarks** | **Data availability** | **IDFA available** |
| --- | --- | --- | --- | --- | --- |
| Consenting and non-consenting | Yes | Set by the advertiser | AppsFlyer last-touch attribution rules used | User-level attribution data | Yes for consenting, no for non-consenting |

``Before September 1, 2026
Click/impression time availability, the lookback window, and data availability differed according to ATT consent:
``

| Section | Details |
| --- | --- |
| Integration activation | **To set up a new integration:**   1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab. 2. Select the relevant app. 3. Search for the partner and select **Integrate**. 4. In the **Integration** tab, turn on the **Activate partner** toggle. Keep it on as long as you work with the partner. 5. Complete the configuration using the relevant tabs, as described below.   **To edit an existing integration:**  In AppsFlyer, go to **Collaborate > Partner Integrations > Active integrations** tab, search for the partner, and make your changes. |
| Install click-through attribution | 1. **Set the Install click-through lookback window** Set the maximum time from ad click to install. Doing so enables AppsFlyer to attribute installs (first launches) taking place within the lookback window to Apple Ads.     * **Range:** 1–30 days    * **Default:** 30 days For more information, see [Lookback windows explained](/docs/set-up-lookback-windows).  1. **Pre-registration (Pre-order) campaigns measurement** If you run pre-registration campaigns for iOS apps, set the pre-registration campaign lookback window.  This slider determines the lookback window for attributing installs to pre-registration campaigns. The pre-registration lookback window allows attribution of installs that happen when pre-registered (pre-ordered) apps are released, linking them back to the original ad engagement.    * **Range:** 1–90 days    * **Default:** 90 days |
| Install view-through attribution | 1. **Set the install view-through lookback window** Set the maximum time from ad view to install. AppsFlyer attributes installs (first launches) that occur within this window to Apple Ads. **Note:** The install view-through lookback window slider supports only hours (max: 24h, default: 24h).     * **Range:** 1–24 hours    * **Default:** 24 hours For more information, see [Lookback windows explained](/docs/set-up-lookback-windows). 2. **Pre-registration (Pre-order) campaign measurement** If you run pre-registration campaigns for iOS apps, set the pre-registration campaign lookback window. This slider determines the lookback window for attributing installs to pre-registration campaigns. The Pre-registration lookback window allows attribution of installs that happen when pre-registered (pre-ordered) apps are released, linking them back to the original ad engagement.    * **Range:** 1–61 days    * **Default:** 61 days |
| Reinstalls | **Reinstall attribution**  If **Reinstall attribution is** on, AppsFlyer can attribute reinstalls to Apple Ads.  Reinstall attribution lookback window settings are set according to the install attribution settings.  If the user is within the [re-attribution window](/docs/set-up-re-attribution-window) (set at the time of the original install), the install is attributed to Apple Ads as a reinstall.  The reinstall can be seen in the retargeting view of the Overview dashboard.  The **Store reinstall** raw data field is set to true.  Currently Apple Ads retargeting does not support re-engagements. |
| **Inactivity window**  Set the user [inactivity threshold](/docs/set-retargeting-inactivity-window) (in days) to control the impact of retargeting campaigns. |
| Postbacks | Currently Apple Ads integration doesn't support postbacks. |

0

</Accordion>

#### See also

* [Aggregated Advanced Privacy framework](/docs/apply-aggregated-advanced-privacy-framework)
* [Lookback windows explained](/docs/set-up-lookback-windows)