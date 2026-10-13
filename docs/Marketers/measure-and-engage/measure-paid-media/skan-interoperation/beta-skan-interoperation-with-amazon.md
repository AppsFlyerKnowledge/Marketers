---
title: "[Beta] SKAN interoperation with Amazon"
excerpt: "SKAN interoperability enables Amazon to share SKAN postbacks with AppsFlyer and enables AppsFlyer to share your conversion value measurement mapping with Amazon."
x-zendesk:
  id: 27548444974353
  url: https://support.appsflyer.com/hc/en-us/articles/27548444974353--Beta-SKAN-interoperation-with-Amazon
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SKAN interoperation
  section_id: 6552115163153
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, SKAdNetwork (SKAN)]
  labels: [Marketers, Beta feature]
  promoted: false
  comments_disabled: true
  created_at: '2024-08-15T09:36:46Z'
  edited_at: '2026-09-08T06:52:18Z'
---
> 📘 Note
>
> To participate in this closed beta, notify your Amazon representative.

## SKAN interoperability: AppsFlyer &lt;-> Amazon

If you work with multiple ad network partners, the best practice is to set it up in AppsFlyer. By doing so, SKAN performance metrics, enriched with other metrics like cost, are available via the AppsFlyer platform.

### Scope of SKAN interoperability with Amazon

The interoperation allows AppsFlyer and Amazon to share the SKAN conversion value mapping (set in AppsFlyer). This enables both sides to provide performance metrics. See the [list of enrichment fields](/docs/skan-integrated-partners-list) supported by Amazon.

### Amazon DSP app install ads guidance

The Amazon DSP iOS Alpha Program empowers AppsFlyer users to run iOS app download campaigns, leveraging Amazon’s platform and Apple’s SKAdNetwork for privacy-focused performance measurement. This program is designed for advertisers seeking to effectively acquire and engage iOS app users. To configure:

**Prerequisites**

* Make sure that the [AppsFlyer SDK](/docs/sdk-integration-overview) is up to date.
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

### Enabling interoperation

Interoperation is achieved via settings in the AppsFlyer and Amazon dashboards. No interoperation or changes are required in the app itself.

**To enable AppsFlyer SKAN interoperation with Amazon:**

| Step | Action | Details |
| --- | --- | --- |
| 1 | App prerequisites | - Integrate the latest AppsFlyer SDK into your app. |
| 2 | SKAN settings review | Set up and turn on AppsFlyer [SKAN solution.](/docs/skadnetwork-skan-solution-guide)<br />**To view SKAN settings**:<br />1. In AppsFlyer, go to **Settings** \> **SKAN Conversion Studio**.<br />2. Click options ( **⋮**), and make sure that **SKAN measurement** is on.<br />   <br />   ![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)<br />3. Select your preferred measurement mode.<br />   <br />   Learn more about [SKAN Conversion Studio](/docs/skan-conversion-studio).<br />4. Make a note of the exact event names set. You'll need them in the next step. |
| 3 | In-app event mapping | Review, and if necessary, make changes to your Amazon in-app event mappings. **At least one in-app event must be mapped to Amazon** for Amazon to retrieve the schema and complete the integration.<br />**To view and set in-app event mappings**:<br />1. In AppsFlyer, Go to **Settings** \> **Active Integrations**.<br />2. Search for and select **Amazon Ads**.<br />3. In the **In-app events postback section:**<br />   1. [Mandatory] If not on, turn on **In-app events postback**.<br />   2. Verify that the in-app events you set in [SKAN conversion studio](/docs/skan-conversion-studio) are mapped to Amazon event names or to the events in your [custom conversion map](/docs/skan-cv-decode-map-your-cv-to-events).<br />      <br />      **Note:** Map `af_skad_revenue` to Amazon's event name `OFF_AMAZON_purchases`<br />4. Click **Save integration**. |

<Cards>
  <Card title="AppsFlyer SKAN solution guide" href="/docs/skadnetwork-skan-solution-guide" icon="fa-solid fa-lock">
    Read the comprehensive guide to setting up and using the AppsFlyer SKAN solution.
  </Card>
</Cards>