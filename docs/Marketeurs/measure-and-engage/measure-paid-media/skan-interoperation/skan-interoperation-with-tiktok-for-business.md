---
title: SKAN interoperation with TikTok for Business
metadata:
  keywords:
    - Advertisers
    - ios14
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-03-14T12:05:58Z'
  edited_at: '2026-06-03T07:48:26Z'
  id: 360018499098
  locale: en-us
  section: SKAN interoperation
  section_id: 6552115163153
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360018499098-SKAN-interoperation-with-TikTok-for-Business
---
> **At a glance:** SKAN interoperability enables TikTok to share SKAN postbacks with AppsFlyer and enables AppsFlyer to share your conversion value measurement mapping with TikTok.

## SKAN interoperability: AppsFlyer &lt;-> TikTok

If you work with multiple ad network partners, the best practice is to set it up in AppsFlyer. By doing so, SKAN performance metrics, enriched with other metrics like cost, are available via the AppsFlyer platform.

### Scope of SKAN interoperability with TikTok

The interoperation allows AppsFlyer and TikTok to share the SKAN conversion value mapping (set in AppsFlyer). This enables both sides to provide performance metrics. When enabling the TikTok for Business integration (either the legacy or the <Anchor target="_blank" href="/marketers/fr/docs/tiktok-for-business-advanced-srn-integration-setup">Advanced SRN</Anchor> integration), AppsFlyer provides TikTok events for optimization purposes. See the <Anchor target="_blank" href="/marketers/fr/docs/skan-integrated-partners-list">list of enrichment fields</Anchor> supported by TikTok.

### TikTok for Business guidance

In configuring your TikTok for Business campaigns, read TikTok's <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10000858">iOS 14 Impact & Guidance</Anchor> and take into account the following:

* Make sure that the <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">AppsFlyer SDK</Anchor> is up to date.
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
| <span id="1"></span>1 | App prerequisites | <ul><li>Integrate the latest AppsFlyer SDK into your app.</li></ul> |
| <span id="2"></span>2 | SKAN settings review | Set up and turn on AppsFlyer <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">SKAN solution.</Anchor><br /><br />**To view SKAN settings**:<ol><li>In AppsFlyer, go to **Settings** > **SKAN Conversion Studio**.</li><li>Click options (⋮), and make sure that **SKAN measurement** is on.<br />![skan-settings.png](https://files.readme.io/87c05b45d44f266785b3d8df57267fb3103543c9bae9b7764e58867e38c8dcdf-4406446668049.png)</li><li>Select your preferred measurement mode.<br />Learn more about <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Make a note of the exact event names set. You'll need them in the next step.</li></ol> |
| <span id="3"></span>3 | In-app event mapping | Review, and if necessary, make changes to your TikTok for Business in-app event mappings.<br /><br />**To view and set in-app event mappings**:<ol><li>In AppsFlyer, Go to **Settings** > **Active Integrations**.</li><li>Search for and select **TikTok for Business**.</li><li>From the **Integration** tab, make sure the <Anchor target="_blank" href="/marketers/fr/docs/tiktok-for-business-advanced-srn-integration-setup">integration with TikTok for Business is activated and configured</Anchor>.</li><li>In the **In-app events postback section:**<ol><li>[Mandatory] If not on, turn on **In-app events postback**.</li><li>Verify that the in-app events you set in <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">SKAN conversion studio</Anchor> are mapped to TikTok for Business event names or to the events in your <Anchor target="_blank" href="/marketers/fr/docs/skan-cv-decode-map-your-cv-to-events">custom conversion map</Anchor>.<br />**Note:** Only map `af_skad_revenue` to TikTok’s `Purchase` event when your SKAN conversion schema measures overall revenue.<br />[![](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)</li></ol></li><li>Click **Save integration**.</li></ol> |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">AppsFlyer SKAN solution guide</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-tiktok=skan-interoperability-appsflyer---tiktok h_01HDNYZ0CT1MGCRSSP3MXTJK5V=skan-interoperability-appsflyer---tiktok h_01HDNYZ0CT5NZHDHDBDSCFG911=scope-of-skan-interoperability-with-tiktok 01HR1TPFCSXRGYC610AR7KMTS5=tiktok-for-business-guidance h_01HDNYZ0CT7RNDAEWYKBHS6PET=campaign-limits-for-dedicated-ios-14-campaigns h_01HDNYZ0CTJGY3GPC9F907NEPT=enabling-interoperation h_01HDNZ1BW5EBP0JCX84MTYPQ6K=see-also" />
