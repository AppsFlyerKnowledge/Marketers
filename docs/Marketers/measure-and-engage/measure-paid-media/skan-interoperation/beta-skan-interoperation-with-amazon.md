---
title: '[Beta] SKAN interoperation with Amazon'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2024-08-15T09:36:46Z'
  edited_at: '2026-09-08T06:52:18Z'
  id: 27548444974353
  locale: en-us
  section: SKAN interoperation
  section_id: 6552115163153
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/27548444974353--Beta-SKAN-interoperation-with-Amazon
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **At a glance:** SKAN interoperability enables Amazon to share SKAN postbacks with AppsFlyer and enables AppsFlyer to share your conversion value measurement mapping with Amazon.

<div id="note" />

> 📘 **Note**
>
> To participate in this closed beta, notify your Amazon representative.

<div id="skan-interoperability-appsflyer---amazon" />

## SKAN interoperability: AppsFlyer &lt;-> Amazon

If you work with multiple ad network partners, the best practice is to set it up in AppsFlyer. By doing so, SKAN performance metrics, enriched with other metrics like cost, are available via the AppsFlyer platform.

<div id="scope-of-skan-interoperability-with-amazon" />

### Scope of SKAN interoperability with Amazon

The interoperation allows AppsFlyer and Amazon to share the SKAN conversion value mapping (set in AppsFlyer). This enables both sides to provide performance metrics. See the <Anchor target="_blank" href="/marketers/docs/skan-integrated-partners-list">list of enrichment fields</Anchor> supported by Amazon.

<div id="amazon-dsp-app-install-ads-guidance" />

### Amazon DSP app install ads guidance

The Amazon DSP iOS Alpha Program empowers AppsFlyer users to run iOS app download campaigns, leveraging Amazon’s platform and Apple’s SKAdNetwork for privacy-focused performance measurement. This program is designed for advertisers seeking to effectively acquire and engage iOS app users. To configure:

**Prerequisites**

* Make sure that the <Anchor target="_blank" href="/marketers/docs/sdk-integration-overview">AppsFlyer SDK</Anchor> is up to date.
* Set Up SKAdNetwork in AppsFlyer
  * Integrate the AppsFlyer SDK into your app.
  * Configure your SKAdNetwork conversion value schema in the AppsFlyer Conversion Studio.
  * Verify that SKAdNetwork is enabled and your conversion schema is properly configured.
* Accept Amazon Advertiser Terms and Conditions

  * **Managed Service Clients:** Your Amazon representative will assist you in accepting the Advertiser Audience Agreement.
  * **Self-Service Clients:**
    * Log in to your Amazon Ads account.
    * Navigate to Amazon DSP > Campaign Manager > Events Manager > Conversions tab.
    * If prompted, accept the terms to proceed.

  **Onboarding steps**
* Register Your App with Amazon Ads
  * **Managed Service Clients:** Provide your app’s iTunes App ID and name to your Amazon representative.
  * **Self-Service Clients:**
    * Log in to advertising.amazon.com.
    * Go to Amazon DSP > Campaign Manager > Events Manager > Apps tab.
    * Click **Add App**, select **AppsFlyer** as your mobile measurement partner, and provide the following details:
      * Platform: iOS
      * App Name: Your app’s name
      * iTunes App ID: Found in the app’s URL on the Apple App Store (e.g. 123456789).
  * Enable **SKAdNetwork measurement** and save.
  * Check the Conversions tab to confirm that Amazon recognizes your conversion schema. If any events are missing, contact your Amazon representative.

**Next steps**

* Managed Clients: Notify your Amazon representative once onboarding is complete.
* Self-Service Clients: Follow Amazon’s campaign setup guide to start creating campaigns

**Key Program Features**

* Campaign Type: iOS app user acquisition campaigns.
* Measurement Framework: SKAdNetwork 2.0–4.0.
* Ad Environment: In-app ads on Amazon properties and select third-party exchanges.
* Reporting: Real-time campaign insights through AppsFlyer.

<div id="enabling-interoperation" />

### Enabling interoperation

Interoperation is achieved via settings in the AppsFlyer and Amazon dashboards. No interoperation or changes are required in the app itself.

**To enable AppsFlyer SKAN interoperation with** **Amazon:**

| Step | Action | Details |
| --- | --- | --- |
| <span id="1"></span>1 | App prerequisites | <ul><li>Integrate the latest AppsFlyer SDK into your app.</li></ul> |
| <span id="2"></span>2 | SKAN settings review | Set up and turn on AppsFlyer <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide">SKAN solution.</Anchor><br /><br />**To view SKAN settings**:<ol><li>In AppsFlyer, go to **Settings** > **SKAN Conversion Studio**.</li><li>Click options (⋮), and make sure that **SKAN measurement** is on.<br />![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)</li><li>Select your preferred measurement mode.<br />Learn more about <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Make a note of the exact event names set. You'll need them in the next step.</li></ol> |
| <span id="3"></span>3 | In-app event mapping | Review, and if necessary, make changes to your Amazon in-app event mappings. **At least one in-app event must be mapped to Amazon** for Amazon to retrieve the schema and complete the integration.<br /><br />**To view and set in-app event mappings**:<ol><li>In AppsFlyer, Go to **Settings** > **Active Integrations**.</li><li>Search for and select **Amazon Ads**.</li><li>In the **In-app events postback section:**<ol><li>[Mandatory] If not on, turn on **In-app events postback**.</li><li>Verify that the in-app events you set in <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">SKAN conversion studio</Anchor> are mapped to Amazon event names or to the events in your <Anchor target="_blank" href="/marketers/docs/skan-cv-decode-map-your-cv-to-events">custom conversion map</Anchor>.<br />**Note:** Map `af_skad_revenue` to Amazon's event name `OFF_AMAZON_purchases`</li></ol></li><li>Click **Save integration**.</li></ol> |

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide">AppsFlyer SKAN solution guide</Anchor>

<div data-zendesk-anchors="01JEBXBFKGN066TY78WKH0VEXC=note skan-interoperability-appsflyer-tiktok=skan-interoperability-appsflyer---amazon h_01HDNYZ0CT1MGCRSSP3MXTJK5V=skan-interoperability-appsflyer---amazon scope-of-skan-interoperability-with-tiktok=scope-of-skan-interoperability-with-amazon h_01HDNYZ0CT5NZHDHDBDSCFG911=scope-of-skan-interoperability-with-amazon tiktok-for-business-guidance=amazon-dsp-app-install-ads-guidance 01HR1TPFCSXRGYC610AR7KMTS5=amazon-dsp-app-install-ads-guidance h_01HDNYZ0CTJGY3GPC9F907NEPT=enabling-interoperation h_01HDNZ1BW5EBP0JCX84MTYPQ6K=see-also" />
