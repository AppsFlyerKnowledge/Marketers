---
title: "Advanced Privacy guide & postback macros for ad networks"
excerpt: "Data sharing with partners when Advanced Privacy is enabled. Instructions for ad networks on setting up Advanced Privacy postbacks. Note! This article is not related to either SKAdNetwork postbacks nor is it intended for use by advertisers."
x-zendesk:
  id: 360011316197
  url: https://support.appsflyer.com/hc/en-us/articles/360011316197-Advanced-Privacy-guide-postback-macros-for-ad-networks
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: End-user privacy
  section_id: 6551186412689
  position: 2
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Mobile Attribution, Ad Networks]
  labels: [Ad Networks, Partners, ios14, SKAD, Advanced Privacy]
  promoted: false
  comments_disabled: true
  created_at: '2020-07-27T07:09:37Z'
  edited_at: '2026-04-19T14:49:32Z'
---
> 📘 **Advanced Privacy for Ad Networks news**
>
> The Advanced Privacy postback mechanism described in this article works when all of the following are true:
>
> * The user device is running iOS 14.5+
> * Advanced Privacy is on

![AdvancedPrivacy.png](https://files.readme.io/2a80740637c1003e03bc169df274bf0fa6240ee850c7fd6e967c4abea234e0d1-360018213598.png)

This article discusses:

* The impact of Advanced Privacy data sharing on partners
* [Click URL](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#click-url-requirements) requirements in order to be eligible for attribution
* Setting up your Advanced Privacy [postbacks](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#advanced-privacy-postback-specification) in the AppsFlyer dashboard
* The difference between [Advanced Privacy and SKAdNetwork.](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#ap-vs-skadnetwork)

## Ad network Advanced Privacy data-sharing principles

Starting iOS 14.5+ the AppsFlyer [Aggregated Advanced Privacy Framework](/docs/apply-aggregated-advanced-privacy-framework) (AAP) provides advertisers with the ability to control the availability of user-level attribution data provided via the AppsFlyer platform.

In the context of ad networks, the AAP framework is implemented using Advanced Privacy (AP). For ease of understanding, the terms Advanced Privacy and AP are used interchangeably in this article.

AP doesn't impact the customer's ability to make aggregated data available to partners or ad networks.

**What data is affected by AP**

When AP is on, the data customers may make available via postbacks or other reporting methods is aggregated only. User-level data, including Protect360 fraud-related reports, is not included.

In the context of postbacks, different postback types are used depending on whether an advertiser ID is available and other factors.

You can view the current AP setting, per app: In AppsFlyer, from the side menu, select **Collaborate**> **Active Integrations** > select your ad network > **Integration tab.** The default setting is on.

![APforPartners2.png](https://files.readme.io/e4fb5617a47635f24dc83881c2be3d18b770200a576cb67bd3312e6fc2c123e1-360018154777.png)

#### Types of templates for sending postbacks

* **Regular template:** Your existing integration template with AppsFlyer with user-identifier and attribution-data macros. This template is used for sending postbacks containing user-level attribution data.
* **Advanced Privacy template**: A template with no user-identifier macros. This template is used for sending postbacks containing aggregated attribution data.   
  **Note:** If an AP postback is required and you haven't completed AP integration, no postback is sent. You can set up AP integration using our self-service [Postback Management](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#setting-up-your-advanced-privacy-postback) tool.

> 📘 **Note**
>
> * If a user gives ATT consent in the apps of both the advertiser and the publisher ("dual consent"), regular postbacks are sent to both the attributed and non-attributed ad networks.
> * **Exception:** For installs attributed to Apple Search Ads (ASA), ASA sends install postbacks to the ad network even when Advanced Privacy is turned on for the advertiser in the following conditions:
>   * An Advertiser ID is unavailable
>   * Install postback on the ad network was set to **All media sources, including organic**
>   * The ad network doesn't support Advanced Privacy

### Type of postback used

The following table describes postback types based on Advertiser ID availability and Advanced Privacy status.

#### Postback type for iOS 14.5+

| AP status | Advertiser ID Availability | | Postback template type to attributed partner* supporting AP | Postback template type to attributed partner* not-supporting AP | Unattributed postback partner* |
| --- | --- | --- | --- | --- | --- |
| Publisher app | Advertiser app |
| On | Available | Unavailable | [AP template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) (aggregated data) | No postback | None |
| On | Unavailable | Available | [AP template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) (aggregated data) | No postback | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks)  [Attribution fields](/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields) aren't available.* |
| On | Available | Available | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks). This includes available IDs like: IDFA, IDFV, CUID, Click ID and attribution fields. | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks). This includes available IDs like: IDFA, IDFV, CUID, Click ID and attribution fields. | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) including available IDs. [Attribution fields](/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields) aren't available.* |
| On | Unavailable | Unavailable | [AP template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#type-of-postback-used) (aggregated data) | No postback | None |
| Off | Not considered | Not considered | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks).  [Attribution fields](/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields) aren't available.* |

**(*) Principles for data sharing with partners**

For any given event, multiple ad network partners may be entitled to a postback. The postbacks sent are as follows:

* Attributed partner: Ad network credited with the event
* Unattributed partner: Integrated partner not credited with the event, when the **In-app events postback** > **Sending option** is set to **All media sources including organic.** If the advertiser app has ATT consent, the postback contains user IDs without attributed data. (This option is not supported by all ad networks.)

  ![InAppEventAll.png](https://files.readme.io/8167a7a133cd7a8e31947e7e26ba66b08363ddb9973b9626cc8874f7c4a57c42-360018213678.png)

### Web campaigns

AP behaves differently when the ad network serves an ad on the web.

To indicate whether a click came from the web or from an app, you must send the `af_media_type=web` or `af_media_type=app` parameter in the click URL.

If you don't send `af_media_type`, the default is `app`.

#### Postback type used for iOS 14.5+ when AP is on

| ATT status | | Postback type to attributed partner* | Postback type to unattributed partner* |
| --- | --- | --- | --- |
| Publisher app | Advertiser app |
| N/A | Not authorized | Advanced Privacy | None |
| N/A | Authorized | Regular. User-level with the following IDs: IDFA, IDFV, CUID, Click ID. | Regular. User-level IDs only. |

## Integration

Update your click URLs and complete Advanced Privacy integration.

### Click URL requirements

In many cases, an Advertiser ID may not be available in the publisher app, the advertiser app, or both. In these instances, attribution is performed using the [Aggregated Advanced Privacy](/docs/appsflyer-attribution-model#aggregated-advanced-privacy-aap) framework or other privacy-preserving campaign measurement methods.

**[Best practice]** To maximize your attributions, send all parameters listed.

1. Append the following parameters to click URLs:

   

| Identifier | Click parameter | Example |
| --- | --- | --- |
| Campaign | c | US\_20\_30 |
| Campaign ID | af\_c\_id | 12345 |
| Adset | af\_adset | ADSET\_1 |
| Adset ID | af\_adset\_id | 56789 |
| Ad | af\_ad | creative\_name |
| Ad ID | af\_ad\_id | 34567 |
| Site ID | af\_siteid | abcdefgh12345678 |
| Subsite ID | af\_sub\_siteid | abcdefgh12345678 |
| Channel | af\_channel | channel\_name |
| Ad type | af\_ad\_type | video |
| iOS device model* | af\_model | The device model. Values permitted:   * iphone (all lower case) * ipad (all lower case) |
| Operating system* | af\_os | The operating system version |
| * Some information may also be provided via the user agent. In this case, the value sent using the specific identifier takes precedence. | | |

   **Append campaign details to the click URL**

   The example that follows shows how to add your campaign details to the click URL:

   

| `https://app.appsflyer.com/id123456789?pid=YOUR_NETWORK_ID&c={CampaignName}&af_c_id={CampaignID}&af_adset={adset name}&af_adset_id={adset ID}&af_ad={ad name}&af_ad_id={ad ID}&af_ad_type={Ad type}&af_siteid={PublisherId}` |
| --- |

2. Add the following mandatory parameters to click URLs*:

   CALLSTART::Note::

   #### Caution

   If your click URL does not pass the mandatory parameters, you will not be credited with the majority of installs you drive.

   CALLEND::
   * IP
   * User-agent

   * No action is required when sending a click using a simple HTTP referrer that redirects to AppsFlyer.

   Use the extraction method described to append the parameters to the click URL when using either of the following methods:

   * Redirect via in-app
   * Server-to-server clicks (aka, S2S)

   #### Parameters for Advanced Privacy attribution

   

| Parameter | Mandatory | Extraction method |
| --- | --- | --- |
| **Device language and locale**<br /><br />af\_lang | No | NSString *language = [[NSLocale preferredLanguages] objectAtIndex:0];<br /><br />[Recommended] Provide the language and locale; for example, en-US. |
| **User-agent**<br /><br />af\_ua | Yes | Extract the user-agent with the format:<br /><br />```<br />Mozilla%2F5.0+%28iPhone%3B+CPU+iPhone+OS+13_3_1<br />+like+Mac+OS+X%29 AppleWebKit%2F605.1.15+%28KHTML%2C<br />+like+Gecko%29+Mobile%2F15E148<br />```<br /><br />* **Do not** extract the CFNetwork *user-agent,* extract the other one.<br />* The user-agent should be URL encoded. |
| **Device IP address**<br /><br />af\_ip | Yes | Best option: If available, provide the device IP under the af\_ip parameter.<br /><br />Next option: If available, AppsFlyer will use the IP in X-Forwarded-For. |

   **Append parameters to the click URL**

   To pass these mandatory parameters on the click attribution link, use this reference:

   

| `https://app.appsflyer.com/id123456789?pid=YOUR_NETWORK_ID&c={CampaignName}&af_c_id={CampaignID}&af_adset={adset name}&af_adset_id={adset ID}&af_ad={ad name}&af_ad_id={ad ID}&af_ad_type={Ad-type}&af_siteid={PublisherId}&af_ua={USER-AGENT}&af_lang={LANGUAGE}&af_ip={IP}` |
| --- |

   **Example**

   

| `GET https://app.appsflyer.com/id123456789?pid=YOUR_NETWORK_ID&c={CampaignName}&af_c_id={CampaignID}&af_adset={adset name}&af_adset_id={adset ID}&af_ad={ad name}&af_ad_id={ad ID}`  <br />`&af_ad_type={Ad type}&af_siteid={PublisherId}`<br /><br />`&af_ua=Mozilla%2F5.0%20%28iPhone%3B%20CPU%20iPhone%20OS%2012_1_4%20`  <br />`like%20Mac%20OS%20X%29%20AppleWebKit%`<br /><br />`2F605.1.15%20%28KHTML%2C%20like%20Gecko%29%20Mobile%2F16D57&af_lang=en-US&af_ip=11.11.1.11` |
| --- |

   * Query parameters must be URL-encoded.

   **Pass data on click URL headers**

   To pass the fields on the click URL header, use this reference:

   

| `GET https://app.appsflyer.com/id123456789?pid=YOUR_NETWORK_ID&c={CampaignName}&af_c_id={CampaignID}&af_adset={adset name}&af_adset_id={adset ID}&af_ad={ad name}&af_ad_id={ad ID}&af_ad_type={Ad type}&af_siteid={PublisherId}`<br /><br />`accept-language: en-US,en;q=0.`<br /><br />`User-Agent: Mozilla/5.0 (iPhone; CPU iPhone OS 13_5_1 like Mac OS X)`<br /><br />`AppleWebKit/605.1.15 (KHTML, like Gecko) Mobile/15E148`<br /><br />`X-Forwarded-For: 11.11.1.11, 222.222.2.222` |
| --- |

### Advanced Privacy postback specification

To receive Advanced Privacy postbacks, you must set up an Advanced Privacy integration in addition to the regular postback integration. You can configure the [Advanced Privacy postback](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#setting-up-your-advanced-privacy-postback) yourself in the AppsFlyer dashboard.

**Differences between the regular template and Advanced Privacy template**

* Postback time does not correlate with actual event times.
* Timestamp macros:
  * For installs and in-app events, timestamps are rounded down to the hour in which they occurred. For example, 22:55:30 is reported as 22:00:00.
  * Are reported using the UTC time zone. Example timestamp: (2020-07-20 20:00:00)
* The following parameters are unavailable in Advanced Privacy postbacks: Click ID, Customer User ID, AppsFlyer ID, IDFA, IDFV, device model, OS version, and carrier.

**Action required by the ad network to integrate:**

1. [Set up your Advanced Privacy postback in the AppsFlyer dashboard.](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#setting-up-your-advanced-privacy-postback)
2. [Test Advanced Privacy integration.](/docs/ios-integration-testing-for-ad-networks)

> 📘 **Important!**
>
> * In order to be able to distinguish between postbacks for legitimate events and rejected postbacks, you must configure the rejected postback macros.
> * To enable rejected installs/events postback, contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).

#### Advanced Privacy postback endpoint [complete as required]

| Postback type |
| --- |
| Install |
| In-app |

#### Advanced Privacy attribution macros available

| AP status | Advertiser ID Availability | | Postback template type to attributed partner* supporting AP | Postback template type to attributed partner* not-supporting AP | Unattributed postback partner* |
| --- | --- | --- | --- | --- | --- |
| Publisher app | Advertiser app |
| On | Available | Unavailable | [AP template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) (aggregated data) | No postback | None |
| On | Unavailable | Available | [AP template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) (aggregated data) | No postback | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks)  [Attribution fields](/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields) aren't available.* |
| On | Available | Available | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks). This includes available IDs like: IDFA, IDFV, CUID, Click ID and attribution fields. | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks). This includes available IDs like: IDFA, IDFV, CUID, Click ID and attribution fields. | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) including available IDs. [Attribution fields](/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields) aren't available.* |
| On | Unavailable | Unavailable | [AP template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#type-of-postback-used) (aggregated data) | No postback | None |
| Off | Not considered | Not considered | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks).  [Attribution fields](/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields) aren't available.* |

0

### Setting up your Advanced Privacy postback

Set up your AP postback using the Postback management option in the AppsFlyer dashboard.

**Prerequisites**:

* You must have an active integration with AppsFlyer to manage your Advanced Privacy postback. Contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif) to [create an integration](/docs/getting-started-onboarding-guide-for-ad-networks).
* ![AppsFlyerAdmin_us-en.png](https://files.readme.io/7a7e18d7e1a5cc9d27c45900651ca4b57377567ac3e8360c52417ead634680c3-360018153137.png) Postback management is performed by the account admin; team members do not have access.

**To set up the postback:**

1. From the top bar, open the account menu (email address dropdown) > **Postback management**.
2. Select the postback type: **Advanced Privacy.**
3. Activate the builder.

   ![postback-management-enter-endpoint_en-us.png](https://files.readme.io/4ea0ffc61d1ecdb11d3c745876c29a942fde4133b8ebb54a1426a73c1dc63b16-360018215218.png)
4. Enter the **endpoint address**: The endpoint URL to which AppsFlyer sends postbacks. Enter the relevant URLs for installs and/or in-app events.
5. Enter the parameters to be included in the postbacks:

   * **Parameter name**: AppsFlyer parameter screen name
   * **Your receiving parameter**: the respective receiving parameter on your side
   * **Parameter value** (available for some parameters): choose the value format. For example, for Boolean values, choose whether to receive them as "true"/"false", or 1/0.
   * **Install**: check the box to include the parameter in the install postback.
   * **In-app event**: check the box to include the parameter in the in-app event postback.

   ![postback-management-parameters_en-us.png](https://files.readme.io/818ef31df9c4e349ca26b5421a0ba0582ed5f7f9fae39f1d0e4ec3b7562f4192-360018213698.png)

   Complete list of [Advanced Privacy postback macros.](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#advanced-privacy-postback-specification)
6. **[Optional]** Add custom parameters that are not provided by AppsFlyer:

   ![postback-management-custom-parameters_en-us.png](https://files.readme.io/6bca46e1d39c6822b0e041eb1dcbb1b2d40e42fa062c34877c8cbf0c2d2847d6-16589581250321.png)
7. Check the final postback template preview to make sure everything is correct.

   ![postback-management-template_en-us.png](https://files.readme.io/b5e41cad37859365c7818c4561620f8a78250c207d8326dae53ed9b522fe3716-360018213718.png)
8. Click **Save**. Note that when you save the postback, the changes take effect immediately.

In the case of any issues, reach out to us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).

## Additional information

### AP for analytics partners

Postbacks are sent to analytics partners as follows:

* AP off: The customer may make user-level postback data available without restriction.
* AP on: Postback type depends on user source and Advertiser ID availability, as detailed in the following table.

#### Analytics partner postback type according to ATT status and user source

| AP status | Advertiser ID Availability | | Postback template type to attributed partner* supporting AP | Postback template type to attributed partner* not-supporting AP | Unattributed postback partner* |
| --- | --- | --- | --- | --- | --- |
| Publisher app | Advertiser app |
| On | Available | Unavailable | [AP template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) (aggregated data) | No postback | None |
| On | Unavailable | Available | [AP template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) (aggregated data) | No postback | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks)  [Attribution fields](/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields) aren't available.* |
| On | Available | Available | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks). This includes available IDs like: IDFA, IDFV, CUID, Click ID and attribution fields. | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks). This includes available IDs like: IDFA, IDFV, CUID, Click ID and attribution fields. | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) including available IDs. [Attribution fields](/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields) aren't available.* |
| On | Unavailable | Unavailable | [AP template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#type-of-postback-used) (aggregated data) | No postback | None |
| Off | Not considered | Not considered | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks) | [Regular template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks).  [Attribution fields](/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields) aren't available.* |

1

### AP vs. SKAdNetwork

[SKAdNetwork](/docs/skan-integration-guide-for-ad-networks) is an Apple-provided attribution technology for iOS devices. Advanced Privacy is part of the [AppsFlyer Aggregated Advanced Privacy](/docs/apply-aggregated-advanced-privacy-framework) (AAP) framework and pertains to AppsFlyer's attribution. AAP enables advertisers to control which attribution data they make available via the AppsFlyer platform. Typically, ad networks support both AP and SKAdNetwork integration.