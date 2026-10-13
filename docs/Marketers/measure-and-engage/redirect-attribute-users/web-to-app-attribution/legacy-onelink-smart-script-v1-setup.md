---
title: "[Legacy] OneLink Smart Script V1 setup"
x-zendesk:
  id: 4415354290321
  url: https://support.appsflyer.com/hc/en-us/articles/4415354290321--Legacy-OneLink-Smart-Script-V1-setup
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Web-to-app attribution
  section_id: 6551240476177
  position: 7
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, Smart Banners and Scripts]
  labels: [OneLink, Advertisers, Developers, Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2022-01-02T17:00:19Z'
  edited_at: '2024-06-13T09:47:15Z'
---
**At a glance:** Set up OneLink Smart Script to convert and attribute your mobile website visitors, coming from any source, into mobile app users. **Note**: Although not mandatory, consider migrating to [OneLink Smart Script V2](/docs/set-up-smart-script-to-convert-web-visitors).

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/89302407b5a7fb98299ce5255393651cc147ed963b0b17a6f74effbc0f7e16e0-4723094404753.png)

## Setup

There are two versions of OneLink Smart Script:

[**OneLink Smart Script V2 (recommended)**](/docs/set-up-smart-script-to-convert-web-visitors): If you are setting up OneLink Smart Script for the first time, this is the preferred version to use. The developer work portion is easier, and it can also be set up using Google Tag Manager. **Note**: Although not mandatory, consider migrating to V2. 

**OneLink Smart Script V1 (legacy)**: If you already have Onelink Smart Script set up, use the documentation for this version to maintain and edit this script. 

### Responsibilities



| **Who's involved**<br /><br />* **Advertiser**:  <br />  * Decides what the outgoing URL should contain. This includes what attribution data to append to the link, and data required for deep linking. Either by manipulating the incoming URL or by forcing certain values.<br />  * Makes sure all campaigns leading to the mobile website have incoming URLs with parameters that the script works for.<br />* **Web developer**:<br />  * Configures the data to initialize the script.<br />  * Enters the setters necessary to generate the outgoing OneLink URLs based on the incoming URL parameters provided by the marketer. This includes mandatory and optional parameters.<br />  * Embeds the script in the website or specific page/s. |
| --- |
| **Prerequisites**<br /><br />* An AppsFlyer account with at least one app.<br />* A [OneLink template](/docs/create-a-onelink-template#procedures) that serves as the value of the [OneLinkURL parameter](/docs/legacy-onelink-smart-script-v1-setup#parameters). |



**To implement the script on the web page**:

1. Decide what parameters/values the automatically-generated outgoing OneLink URL should contain. See the [list of parameters](/docs/legacy-onelink-smart-script-v1-setup#parameters) you can use.
   * Make sure that all campaigns with incoming URLs have parameters that the script works for (and can place as the **pid** and **c** parameters).
2. Provide the [list of parameters](/docs/legacy-onelink-smart-script-v1-setup#parameters) to the web developer.
3. Tell the developer to follow the [dev instructions](https://dev.appsflyer.com/hc/docs/onelink-smart-script) and implement the script so the correct outgoing link is generated.

### Parameters

#### Parameters/values provided to the developer to implement the Smart Script



| Param/value | Remarks | Record your responses (for the developer to use) |
| --- | --- | --- |
| oneLinkURL (required) | * Provide the OneLink template domain + template ID. **Note:** Not a OneLink custom link URL!<br />* Example: **yourbrand.onelink.me/A1b2**<br />* Branded domain example: **click.yourbrand.com/A1b2** |  |
| pidKeysList (media sources) | * List all the media source parameter/s in the incoming URL that will be placed as the media source (pid) parameter in the outgoing URL.<br />* Example: ['af\_pid', 'utm\_source'] |  |
| pidOverrideList | * For media sources you want changed in the outgoing link, list the media source values in the incoming URL, alongside what you want them to be replaced with.<br />* Example: `{  <br />  'twitter': 'twitter_int',  <br />  'snapchat': 'snapchat_int',  <br />  'some_social_net': 'some_social_net_int'  <br />  }` |  |
| pidStaticValue | * State what you want your "fallback" media source to be.<br />* If a media source parameter is not found in your pidKeysList, the pidStaticValue is used as the media source (pid) in the outgoing URL.<br />* Example: 'website' or 'landing\_page' |  |
| campaignKeysList (campaigns) | * List all the campaign parameter/s in the incoming URL that will be placed as the campaign (c) parameter in the outgoing URL.<br />* Example: ['af\_campaign', 'utm\_campaign'] |  |
| campaignStaticValue | * State what you want your "fallback" campaign to be.<br />* If a campaign parameter is not found in your campaignKeysList, the campaignStaticValue is used as the campaign (c) in the outgoing URL.<br />* Example: 'website' or 'landing\_page' |  |
| gclIdParam | * State what to call the parameter that carries the [GCLID](https://support.google.com/google-ads/answer/9744275?hl=en).  <br />  **Note**! To display in AppsFlyer raw data reports, the param must be one of **af\_sub[1-5]**. |  |
| skipList | * List the strings in the HTTP referrer that disable the Smart Script for a particular click (for example Twitter or Facebook). If the strings are found, the Smart Script doesn't run. This can be useful for SRNs like X Ads and Meta ads, for which clicks are already reported.<br />* If you always want the Smart Script to run, even for SRNs, tell the developer to pass an empty skip list. |  |
| Other query parameters | * List any other parameters you want to be included in the outgoing OneLink URL for attribution or deep linking.<br />* Add a **deep\_link\_value** for deep linking.<br />  * In addition to adding the param, you and your developer need to implement the deep linking logic. [Learn more](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link).<br />* You can either use parameters from the incoming URL, or force a static value. |  |



## Use cases

The following sections provide Smart Script use cases for some common campaign/media source scenarios.

### Meta ads—cross-platform attribution

Meta ads is an SRN that doesn't use external attribution links.

Upon first app launch, AppsFlyer queries Meta ads whether the user has previously (within the last [7 days](/docs/meta-ads-discrepancies#clickthrough-and-viewthrough-attribution)) engaged with an ad for the app. If the user has engaged with a Facebook ad of the advertiser, Meta ads self-attributes. Meta ads also attributes cross-platform, meaning that the user may interact with any type of campaign, mobile or not, on any platform, to be self-attributed by Meta ads.

**Action**: Tell your developer to use the [skipList method](https://dev.appsflyer.com/hc/docs/onelink-smart-script#skip-clicks-from-twitter-or-facebook) to disable the Smart Script for Meta ads (or any other strings you want). If Meta ads or any of the strings in the skip list appear in the HTTP referrer of the click, the Smart Script returns `null`.

**Note**: Meta ads cross-platform attribution may be affected when users opt not to share their device ID, as is expected with iOS 14 users during 2021.

### Google Ads—GCLID and UTM parameters

The usual process for install attribution of Google Ads campaigns (which carry a GCLID parameter) requires clicking leads to be redirected to the app's store page URL.

Since in this case, you are redirecting leads from Google Ads to a web/landing page, the script takes the GCLID parameter from the Google Ads install campaign URL and puts it into the outgoing URL in your choice of output parameter **af\_sub[1-5].** **Note!** This applies to install campaigns. For non-ACI search campaigns, meaning re-engagement campaigns, Google may be attributed as the media source, despite the Smart Script output.

**Prerequisite**: On the Google dashboard, [enable auto-tagging](https://support.google.com/analytics/answer/1033981?hl=en)**.**With auto-tagging enabled, the URL contains the *GCLID* parameter.

**To set up the script for Google Ads**:

1. Make a list of the media source and campaign parameter names that are in the incoming links.  
   For example: **utm\_source** and **utm\_campaign**.
2. Select a parameter in the outgoing URL to contain the GCLID.  
   Best practice: Select **af\_sub[1-5]**, so that the data displays in AppsFlyer raw data reports.
3. Provide these in the [list of parameters](/docs/legacy-onelink-smart-script-v1-setup#parameters) to the web developer.

**Result**:

* The values in the media source and campaign parameters (**utm\_source** and **utm\_campaign**) in the incoming link are used to populate the values for the **pid** and **c** parameters in the outgoing link.
* In the outgoing URL, the GCLID is the value of the **af\_sub[1-5]** param.

**To notify Google Ads about these installs:**

1. Get the GCLID data from the param **af\_sub[1-5]** via CSV, or Push API in real-time for every install.
2. Upload the GCLID data to Google either [manually](https://support.google.com/adwords/answer/7014069) or via an [Adwords API](https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions).

> 📘 **Note**
>
> This GCLID solution is not officially supported or recommended by Google. In case Google deprecates the GCLID parameter we will change the script to support the changes. Follow this article, by clicking the **Follow** button in the article header, to get informed when there is an update to the article or attached script.


### SRNs, owned media, and other media source links

[SRNs](/docs/self-reporting-networks-srns#srns-integrated-with-appsflyer) like Snapchat or X Ads, work differently than Google Ads or a cross-platform like Meta ads. Campaigns from these SRNs lead your users to the web/landing page, and you are billed according to clicking leads, unrelated to any derived mobile users.

For these SRNs, script setup is the same as for links from owned media, or other media sources you might use.

**To set up the script**:

1. Make a list of the media source and campaign parameter names that are in the incoming links.
2. Provide these in the [list of parameters](/docs/legacy-onelink-smart-script-v1-setup#parameters) to the web developer.  
   The SRN/media source type should be the media source value in the incoming URL, and the script finds it and uses it as the **pid** value in the outgoing OneLink URL behind the download button on the web/landing page. If you want to change the outgoing **pid**, provide the incoming media source value and the replacement **pid** value in the pid override list.

**Result**: For these SRNs/media sources, the values in the media source and campaign parameters in the incoming link are used to populate the values for the **pid** and **c** parameters in the outgoing link.

> 📘 **Example**
>
> **Incoming URL**: https://hotel.me/af\_pid=twitter&af\_c=big\_social
>
> **Outgoing URL**: https://hotel.onelink.me/Ac4G?pid=twitter&c=big\_social


### AppsFlyer attribution links

AppsFlyer attribution links can be used when the media source is a click ad network. When you set up such a link in AppsFlyer, you have the option to add a ***Redirection URL path (af\_r)***parameter with the desired URL path to your mobile website, for web campaign-to-app attribution. 

**Result**: If the **af\_r** and **af\_redirect=true** parameters are on the incoming link, the landing page script makes no changes. It leaves the web/landing page direct links to the app stores as they are. 

> 📘 **Example**
>
> **Incoming URL**: https://app.appsflyer.com/id123456789?pid=click\_ad\_network\_int&c=orlando&af\_redirect=true&af\_r=hotel.me
>
> **Outgoing URL**: Same


### Desktop

Most use cases in this article are of users coming from mobile devices. Therefore, when directed from the mobile website to an app store, they can immediately download your app.

However, desktop users shouldn't immediately be sent to an app store, because their device (a desktop or laptop) isn't compatible with mobile app downloads.

**To set up the script for desktop users**:

* In your [OneLink template](/docs/create-a-onelink-template#procedures), set a destination URL for **When link is clicked on desktop**. The URL should redirect to a dedicated web/landing page. The landing page can contain a web form where they fill in their details to get an SMS or an email with a link to download the app. It's up to you to create the web form and provide the URL to it in the script.

**Result**: The script detects the device or platform the user is on. If it's desktop, the script generates an outgoing OneLink URL that redirects the user to your dedicated web/landing page.

See also [Desktop-to-app conversion](/docs/qr-to-app-conversion).

## Limitations



| Limitation | Remarks |
| --- | --- |
| Tag manager | Smart Script cannot be implemented via tag manager. See [OneLink Smart Script V2](/docs/set-up-smart-script-to-convert-web-visitors) or [Smart Banners](/docs/smart-banners-mobile-web-to-app-for-marketers) as an alternative web-to-app attribution solution. |