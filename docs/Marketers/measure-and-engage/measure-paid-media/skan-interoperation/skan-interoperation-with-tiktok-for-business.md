---
title: "SKAN interoperation with TikTok for Business"
excerpt: "Learn how to configure SKAN interoperability between AppsFlyer and TikTok for Business to share conversion value mappings and optimize your iOS 14 campaigns."
---
**At a glance:** SKAN interoperability enables TikTok to share SKAN postbacks with AppsFlyer and enables AppsFlyer to share your conversion value measurement mapping with TikTok.

## SKAN interoperability: AppsFlyer &lt;-> TikTok

If you work with multiple ad network partners, the best practice is to set it up in AppsFlyer. By doing so, SKAN performance metrics, enriched with other metrics like cost, are available via the AppsFlyer platform.

### Scope of SKAN interoperability with TikTok

The interoperation allows AppsFlyer and TikTok to share the SKAN conversion value mapping (set in AppsFlyer). This enables both sides to provide performance metrics. When enabling the TikTok for Business integration (either the legacy or the [Advanced SRN](/docs/tiktok-for-business-advanced-srn-integration-setup) integration), AppsFlyer provides TikTok events for optimization purposes. See the [list of enrichment fields](/docs/skan-integrated-partners-list) supported by TikTok.

### TikTok for Business guidance

In configuring your TikTok for Business campaigns, read TikTok's [iOS 14 Impact & Guidance](https://ads.tiktok.com/help/article?aid=10000858) and take into account the following:

* Make sure that the [AppsFlyer SDK](/docs/sdk-integration-overview) is up to date.
* [Configure a TikTok App ID](https://ads.tiktok.com/help/article?aid=10001060) for each app you advertise on TikTok for Business.
  * TikTok App ID is a unique code generated in TikTok Ads Manager and is used by TikTok to confirm advertiser ownership of their apps.
  * Although not mandatory, it is recommended to enter your App ID of all your apps.  
    This helps you to better control your TikTok For Business data and to unlock additional products.
  * **To add more than one TikTok App ID:**
    1. Enter your first TikTok App ID.
    2. Press **Enter.**
    3. Enter your next TikTok App ID.
  * Configuring a TikTok App ID doesn't impact your data in AppsFlyer.
  * [Learn more about TikTok App ID requirements for iOS 14](https://ads.tiktok.com/help/article?aid=10001070).
* [Complete conversion event mapping](/docs/skan-interoperation-with-tiktok-for-business#3) for bytedanceglobal\_int and tiktokglobal\_int.
* Review guidance on campaign limitation and account/campaign consolidation.

Work directly with your TikTok for Business account manager on SKAN configuration and strategy.

TikTok supports SKAN as follows:

* Measurement and optimization via conversion measurement API.
* Reporting of dedicated iOS 14 campaigns in TikTok for Business.

### Campaign limits for dedicated iOS 14 campaigns

Due to SKAN API limitations, TikTok for Business supports the following when creating dedicated iOS 14 campaigns (applicable to App Install ads and Dynamic Product Ads for app prospecting):

* ​iOS apps are limited to 15 campaigns with 5 ad group per campaign.
* Dedicated iOS 14 campaigns:
  * Can be created from multiple ad accounts, but the total number of active campaigns is limited to 15.
  * Across all relevant objectives count towards the limit (15), and after reaching the campaign limit, advertisers must wait at least 72 hours after a campaign has been paused, turned off, or deleted to free up a campaign slot before beginning a new campaign.

### Enabling interoperation

Interoperation is achieved via settings in the AppsFlyer and TikTok for Business dashboards. No interoperability or changes are required in the app itself.

**To enable AppsFlyer SKAN interoperation with** **TikTok for Business:**

| Step | Action | Details |
| --- | --- | --- |
| 1 | App prerequisites | * Integrate the latest AppsFlyer SDK into your app. |
| 2 | SKAN settings review | Set up and turn on AppsFlyer [SKAN solution.](/docs/skadnetwork-skan-solution-guide)<br /><br />**To view SKAN settings**:<br /><br />1. In AppsFlyer, go to **Settings** > **SKAN Conversion Studio**.<br />2. Click options (**⋮**), and make sure that **SKAN measurement** is on.  <br />   ![skan-settings.png](https://files.readme.io/87c05b45d44f266785b3d8df57267fb3103543c9bae9b7764e58867e38c8dcdf-4406446668049.png)<br />3. Select your preferred measurement mode.  <br />   Learn more about [SKAN Conversion Studio](/docs/skan-conversion-studio).<br />4. Make a note of the exact event names set. You'll need them in the next step. |
| 3 | In-app event mapping | Review, and if necessary, make changes to your TikTok for Business in-app event mappings.<br /><br />**To view and set in-app event mappings**:<br /><br />1. In AppsFlyer, Go to **Settings** > **Active Integrations**.<br />2. Search for and select **TikTok for Business**.<br />3. From the **Integration** tab, make sure the [integration with TikTok for Business is activated and configured](/docs/tiktok-for-business-advanced-srn-integration-setup).<br />4. In the **In-app events postback section:**<br />   1. [Mandatory] If not on, turn on **In-app events postback**.<br />   2. Verify that the in-app events you set in [SKAN conversion studio](/docs/skan-conversion-studio) are mapped to TikTok for Business event names or to the events in your [custom conversion map](/docs/skan-cv-decode-map-your-cv-to-events).  <br />      **Note:** Only map `af_skad_revenue` to TikTok’s `Purchase` event when your SKAN conversion schema measures overall revenue.  <br />      [![](https://support.appsflyer.com/hc/article_attachments/25706935571217)](https://support.appsflyer.com/hc/article_attachments/25706935571217)<br />5. Click **Save integration**. |

> 📘 **Note**
>
> #### See also
>
> * [AppsFlyer SKAN solution guide](/docs/skadnetwork-skan-solution-guide)