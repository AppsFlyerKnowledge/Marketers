---
title: Set up Smart Script to convert web visitors
excerpt: >-
  Set up OneLink Smart Script to convert and attribute your mobile website
  visitors, coming from any source, into mobile app users.
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2021-12-13T09:57:23Z'
  edited_at: '2026-09-02T13:20:25Z'
  id: 4413588932241
  locale: en-us
  section: Web-to-app attribution
  section_id: 6551240476177
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4413588932241-Set-up-Smart-Script-to-convert-web-visitors
---
![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/4f506532e65c118a76e875b992be59cf8cca925f78e125dbb35b958fc1639d16-42045468431121.png)

## Setup

There are two versions of OneLink Smart Script:

**OneLink Smart Script V2 (recommended)**: If you are setting up OneLink Smart Script for the first time, this is the preferred version to use. It can be generated in the AppsFlyer UI without developer assistance. If for some reason, a developer is needed, their work portion is easier. And it can also be set up using Google Tag Manager. [See developer instructions](https://dev.appsflyer.com/hc/docs/dl_smart_script_v2)

[**OneLink Smart Script V1 (legacy)**](/docs/legacy-onelink-smart-script-v1-setup): If you already have Onelink Smart Script set up, use the documentation for this version to maintain and edit this script. **Note**: Although not mandatory, consider migrating to V2 to properly get [view-thorough attributions](https://www.appsflyer.com/glossary/view-through-attribution/) using the OneLink Smart Script.

### Set up OneLink Smart Script

To set up the Smart Script, you can either:

* Embed the script in your website.
* Use Google Tag Manager.

#### Scope of work

**Who's involved**

* **Advertiser**:
  * Decides what the outgoing URL should contain based on the [arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) in the script that process the incoming URL. This determines the attribution and deep linking data that gets appended to the outgoing URL, either by manipulating the incoming URL or by forcing certain values.
  * Generates the Smart Script in the AppsFlyer UI.
  * Makes sure all campaigns leading to the mobile website have incoming URLs with parameters that the script works for.
  * [Tests the Smart Script](https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html).
* **Web developer**:
  * Verifies the script runs on the mobile site/pages on which you want it to work.
  * Uses the result value as needed, for example, to place it as a link under a CTA on your website.
  * May be needed to create QR codes using the script.
  * May be needed to manually add advanced arguments to the script.

**Prerequisites**

* An AppsFlyer account with at least one app.
* A [OneLink template](/docs/create-a-onelink-template#create-a-onelink-template) that serves as the value of the [OneLinkURL parameter](/docs/set-up-smart-script-to-convert-web-visitors#arguments).

<div id="how-to-create-a-onelink-smart-script" />

<Accordion title="Create a OneLink Smart Script">

**To create a OneLink Smart Script:**

1. In AppsFlyer, from the side menu, select **Engage** > **Web-to-app** > **Smart Script**.
2. ***For new users***
   1. *Click on the **Get started** button.*
   2. *Follow steps 4 and onwards.*
3. Click on the **+ New Smart Script button** at the top of the page.
4. Follow the onscreen instructions to name your Smart Script.
5. Select a OneLink template to base the script. The template contains the basic redirection settings.
6. Map the parameters that the outgoing URL should contain. These parameters are based on the parameters of the incoming URL. **Note**: The media source (pid) parameter is mandatory.
   1. Select the outgoing parameter/dimension to map.  
      Often, this is an AppsFlyer parameter name that can't be changed, but in some cases, you need to enter your parameter name.
   2. Decide and configure what the value of the outgoing parameter should be based on either:
      * Incoming URL parameters: List one or more possible incoming URL parameters that you want replaced by the outgoing URL parameter. The values of the incoming URL parameters will be the values of your outgoing URL parameter.
        * Example: any\_param\_name, utm\_param\_name. If utm\_param\_name is found in the incoming URL, its value will be used as the value of your selected outgoing URL parameter.
        * The Smart Script searches the list of parameters from left to right and maps the first match to the outgoing parameter URL.
        * This list of parameters is referred to by developers as keys.
      * Default value: Enter your desired default value for the outgoing parameter value for when an incoming URL parameter isn't found or if you don’t list any incoming URL parameters.
        * Example: For the outgoing parameter, if the incoming URL parameter lists any\_paramname, utm\_paramname, when neither parameter in the list is found, the default value will be used as the value of the outgoing parameter.
      * Override values: Configure one or more values from the incoming URL alongside the values of the outgoing URL you want them to be replaced with.
        * Example: For the campaign parameter, if the value in the incoming URL is campaign\_name, the value in the outgoing URL can be changed to new\_campaign\_name.
   3. [Optional] Click **+ New parameter** to map additional parameters. See all the [additional arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) (parameter configurations) you can use.
7. [Optional] Turn on **Media Source for organic search installs,** under the **Web** **referrer mapping** section, to automatically set the media source for organic search traffic when it isn't already resolved by the URL parameter mapping section. [Learn more](#seo-referrer-mapping)
8. Select how to implement the Smart Script on your website:
   * **Embed the script in your website.**
   * **Use Google Tag Manager.**
9. Click on **Test** to test the script on the [Smart Script test page](https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html). Make sure the correct outgoing URL is generated.
10. Click
    1. **Save** to save your changes
    2. **Save and Generate** to save and generate the script
       1. Click **Download script**.
11. If you selected to embed the script in your website: Send the script to your web developer to implement and tell them what to do with the generated outgoing URL. For example, place it under a CTA button on your mobile site or present a QR code on your desktop site. [Developer instructions](https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#embed-the-script-in-your-website)
12. If you selected to use Google Tag Manager:
    1. In Google Tag Manager, create a new tag, name the tag, click **Tag Configuration**, and select **Custom HTML**.
    2. In the HTML box, paste the generated Smart Script code.
    3. Click **Triggering**, create a new trigger, name it, and choose a **Trigger Configuration** (for example, all page views). [See GTM documentation to learn more](https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108)
    4. Click **Save**
    5. Tell your web developer what to do with the generated outgoing URL. For example, place it under a CTA button on your mobile site or present a QR code on your desktop site. [Developer instructions](https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#use-google-tag-manager)
13. Saved scripts can be viewed in the [dropdown menu](/docs/set-up-smart-script-to-convert-web-visitors#how-to-edit-or-delete-a-script).

> 📘 **Important!**
>
> Every time you update the script, it needs to be implemented again

</Accordion>

<div id="how-to-edit-or-delete-a-script" />

<Accordion title="Edit or delete a script">

**To edit or delete a script:**

1. Click the dropdown arrow ![Down_arrow.jpg](https://files.readme.io/a82023665721be681f985548857c4c329f626435780bb1bff7a3821b32b69078-42045468433041.jpg) next to the Smart Script name.  
   Here you can see all your saved scripts  

   ![Script_steps.jpg](https://files.readme.io/824c042dc23acaa14b360ce8cd792cfc2e85ee3c9c95e3fa694f96badfeb1fc2-42045468432657.jpg)
2. Click on the pen icon next to the script you want to edit
   1. Follow the steps in [How to create a OneLink Smart Script](/docs/set-up-smart-script-to-convert-web-visitors#set-up-onelink-smart-script)
3. Click on the trash bin icon to delete the Smart Script

> 📘 **Important!**
>
> Every time you update the script, it needs to be implemented again

</Accordion>

<div id="how-to-duplicate-a-script" />

<Accordion title="Duplicate a script">

**To duplicate a script:**

1. Go to the Smart Script you want to duplicate
2. Click on the duplicate button ![SmartScript_duplicate.jpg](https://files.readme.io/ec05ea217331b588dc7033984287d46b61a37e41510546b67a0046ea281e0979-42045454920721.jpg) on the top banner
3. Follow the steps in [How to create a OneLink Smart Script](/docs/set-up-smart-script-to-convert-web-visitors#set-up-onelink-smart-script)

</Accordion>

<div id="argument-structure" />

<Accordion title="Argument structure">

The OneLink Smart Script uses arguments to generate an outgoing URL based on the parameters of the incoming URL and the arguments defined in the script. The afParameters argument has a structure made up of several other arguments (parameters) used for attribution and deep linking, each of which contains a structure (referred to by developers as a configuration object) that has keys, override values, and a default value, as described in the table that follows.

| Argument | Description | Example |
| --- | --- | --- |
| Incoming URL parameters (referred to by developers as keys) | <ul><li>List of strings</li><li>List of possible parameter/s in the incoming URL the script looks for, the value of which is placed as the value in the outgoing URL.</li><li>The script searches from left to right and stops at the first match.</li></ul> | <ul><li>Example: ['in\_channel', 'utm\_channel']</li><li>For the channel parameter in the script, the script searches the incoming link for in\_channel and uses the value as the value for channel.</li></ul> |
| Default value | <ul><li>String</li><li>State what you want your "fallback" value to be.</li><li>If a parameter is not found from your key list, the defaultValue value is used in the outgoing URL.</li><li>You can force a default value by passing an empty keys list.</li></ul> | Example: ['web\_video']<br /><br />For the channel parameter in the script, if you have the param in\_channel is not found, web\_video is used as the channel value. |
| Override values | <ul><li>Dictionary \{string: string\}</li><li>For values you want changed in the outgoing link, list the values in the incoming URL, alongside what you want them to be replaced with.</li><li>The script replaces the param values of the incoming URL with the values you define.</li></ul> | Example: \{'video': 'video\_new'\}<br /><br />For the channel parameter in the script, anytime the incoming value is video, the script changes it to video\_new on the outgoing link. |

</Accordion>

<div id="arguments" />

<Accordion title="Arguments (parameters and values)">

The OneLink Smart Script uses arguments to generate an outgoing URL based on the parameters of the incoming URL and the arguments defined in the script.

#### Arguments (parameters and values) to implement the Smart Script

<table><thead><tr><th colspan="2">Argument</th><th>Remarks</th><th>Record your responses (for you or your developer to use)</th></tr></thead><tbody><tr><td colspan="2">oneLinkURL (required)</td><td><ul><li>Provide the OneLink template domain + template ID. <strong>Note: </strong>Not a OneLink custom link URL!</li><li>Example: <strong>yourbrand.onelink.me/A1b2</strong></li><li>Branded domain example: <strong>click.yourbrand.com/A1b2</strong></li></ul></td><td> </td></tr><tr><td rowspan="9"><p>afParameters</p><p>(required)</p></td><td><p>mediaSource</p><p>(required)</p></td><td><ul><li>Configuration object for media source.</li><li>Example:<ul><li>Keys: ['incoming_mediasource’' 'utm_source']</li><li>Default value: ['any_source']</li><li>Override values: `{twitter: 'twitter_int', orig_src: 'new_src',  seo:'false'}</li></ul></li></ul></td><td><p>Keys:</p><p>Default value:</p><p>Override values:</p></td></tr><tr><td>campaign</td><td><ul><li>Configuration object for campaign.</li><li>Example:<ul><li>Keys: ['incoming_campaign', 'utm_campaign']</li><li>Default value: ['any_campaign_name']</li><li>Override values: {campaign_name: 'new_campaign_name'}</li></ul></li></ul></td><td><p>Keys:</p><p>Default value:</p><p>Override values:</p></td></tr><tr><td>channel</td><td><ul><li>Configuration object for channel.</li><li>Example:<ul><li>Keys: ['incoming_channel', 'utm_channel']</li><li>Default value: ['any_video']</li><li>Override values: {video: 'new_video'}</li></ul></li></ul></td><td><p>Keys:</p><p>Default value:</p><p>Override values:</p></td></tr><tr><td>ad</td><td><ul><li>Configuration object for ad.</li><li>Example:<ul><li>Keys: ['incoming_ad', 'utm_ad']</li><li>Default value: ['any_ad_name']</li><li>Override values: {ad_name: 'new_ad_name'}</li></ul></li></ul></td><td><p>Keys:</p><p>Default value:</p><p>Override values:</p></td></tr><tr><td>adSet</td><td><ul><li>Configuration object for adset.</li><li>Example:<ul><li>Keys: ['incoming_adset', 'utm_adset']</li><li>Default value: ['any_ad_name']</li><li>Override values: {adset_name: 'new_adset_name'}</li></ul></li></ul></td><td><p>Keys:</p><p>Default value:</p><p>Override values:</p></td></tr><tr><td>deepLinkValue</td><td><ul><li>Configuration object for <strong>deep_link_value</strong>.</li><li>Example:<ul><li>Keys: ['product_id', 'page_name']</li><li>Default value: 'new_offers_page'</li><li>Override values: {twenty_percent_off: 'thirty_percent_off'}</li></ul></li></ul></td><td><p>Keys:</p><p>Default value:</p><p>Override values:</p></td></tr><tr><td>afSub1-5</td><td>Configuration object for <strong>af_sub[1-5]</strong>.</td><td><p>Keys:</p><p>Default value:</p><p>Override values:</p></td></tr><tr><td>googleClickIdKey</td><td>State what to call the parameter that carries the <a href="https://support.google.com/google-ads/answer/9744275?hl=en">GCLID</a>.<br/><strong>Note</strong>! <span>To display in AppsFlyer raw data reports, the param must be one of <strong>af_sub[1-5]</strong>.</span></td><td> </td></tr><tr><td><span>Other (custom) query parameters</span><br/> </td><td><ul><li>List any other parameters you want to be included in the outgoing OneLink URL for attribution or deep linking, along with their configuration objects.</li><li>The name of the custom parameter is listed by the developer as a paramKey in the configuration object.<span></span></li><li>Example:<ul><li>paramKey: 'deep_link_sub1'</li><li>Keys: ['page_id']</li><li>Default value: 'page1'</li><li>Override values: {page12: 'new_page12'}`</li></ul></li></ul></td><td><p>Param key:</p><p>Keys:</p><p>Default value:</p><p>Override values:</p></td></tr></tbody></table>

</Accordion>

<div id="advanced-arguments" />

<Accordion title="Advanced arguments">

The following table describes arguments that technical-savvy marketers or developers can implement in the Smart Script.

#### Advanced arguments (parameters and values) to implement in the Smart Script

<table><thead><tr><th colspan="2">Argument</th><th>Remarks</th><th>Record your responses (for you or your developer to use)</th></tr></thead><tbody><tr><td colspan="2"><br/>referrerSkipList</td><td><ul><li>List of the strings in the HTTP referrer for a particular click (for example Twitter or Facebook) that if found, cause the Smart Script to return <code>null</code>. This can be useful for SRNs like X Ads and Meta ads, for which clicks are already reported.</li><li>Implementing this argument results in the script NOT generating a OneLink URL.</li></ul></td><td> </td></tr><tr><td colspan="2">urlSkipList</td><td><ul><li>List of the strings in the URL for a particular click (for example af_r) that if found, cause the Smart Script to return <code>null</code>. This can be useful if you use an AppsFlyer attribution link with af_r to redirect users to your mobile website, and don't want data from the original click to be lost.</li><li>Implementing this argument results in the script NOT generating a OneLink URL.</li></ul></td><td> </td></tr><tr><td colspan="2">SEO</td><td><ul><li>When enabled, and the media source isn't resolved from the <strong>URL parameter mapping</strong> section, we'll check whether users arrived from a search engine based on their web referrer URL and set the media source accordingly. (Available from version 2.10.3)</li></ul></td><td> </td></tr></tbody></table>

</Accordion>

## Use cases

The following sections provide Smart Script use cases for some common campaign/media source scenarios.

<div id="utm-parameters" />

<Accordion title="UTM parameters">

**To set up the script for UTM parameters**:

1. Make a list of UTM parameters on the incoming URL (for example: **utm\_source** and **utm\_campaign**) and match them to the parameters for the outgoing URL (for example: **media\_source** and **campaign**).
2. Provide these in the [list of arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) to the web developer.

**Result**: The values in the incoming parameters (**utm\_source** and **utm\_campaign**) are used to populate the values of the (**media\_source** and **campaign**) parameters in the outgoing link.

</Accordion>

<div id="google-ads-gclid" />

<Accordion title="Google Ads GCLID">

The usual process for install attribution of Google Ads campaigns (which carry a GCLID parameter) requires users who click your ad to be redirected to the app store page URL.

Since in this case, you are redirecting leads from Google Ads to a web/landing page, the script takes the GCLID parameter from the Google Ads install campaign URL and puts it into the outgoing URL. From Smart Script version 2.9.0, GCLID, WBRAID, and GBRAID parameters, when available, are automatically forwarded "as is" on outgoing URLs generated by the Smart Script.

You can also map Click IDs to other outgoing parameters (**af\_sub[1-5]**) to have them available in AppsFlyer raw data reports.

**Note!**

* This applies to install campaigns. For non-ACI search campaigns, meaning re-engagement campaigns, Google may be attributed as the media source, despite the Smart Script output.
* If a GCLID is found, the script looks for the incoming parameter keyword. If found, it puts the keyword value in the outgoing URL as the value of af\_keywords.

**Prerequisite**: On the Google dashboard, [enable auto-tagging](https://support.google.com/analytics/answer/1033981?hl=en).  
With auto-tagging enabled, the URL contains the *GCLID* parameter.

**To set up the script to map Google Ads GCLID to other parameters**:

1. Select a parameter in the outgoing URL to contain the GCLID.  
   Best practice: Select **af\_sub[1-5]**, so that the data displays in AppsFlyer raw data reports.
2. Provide this in the [list of arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) to the web developer. The result will be that in the outgoing URL, the GCLID will be the value of the **af\_sub[1-5]** param.

**To notify Google Ads about these installs:**

**Recommended:** Set up [Google web integration](/docs/google-ads-adwords-create-web-based-campaigns). This integration supports automatic postbacks for installs.

**If you don't have the integration:**

1. Get the GCLID data from the param **af\_sub[1-5]** via CSV, or Push API in real-time for every install.
2. Upload the GCLID data to Google either [manually](https://support.google.com/adwords/answer/7014069) or via [Google Ads API](https://developers.google.com/google-ads/api/docs/start).

> 📘 **Note**
>
> This GCLID solution is not officially supported or recommended by Google. In case Google deprecates the GCLID parameter we will change the script to support the changes. Follow this article, by clicking the **Follow** button in the article header, to get informed when there is an update to the article or attached script.

</Accordion>

<div id="facebook-click-id" />

<Accordion title="Facebook FBCLID">

Meta ads carry click IDs, called FBCLID. Starting in Smart Script version 2.8.1, when available, FBCLID will automatically be forwarded "as is" on outgoing URLs generated by the Smart Script. You can also map Click IDs to other outgoing parameters to have them available in AppsFlyer raw data reports.

**To set up the script to map FBCLID to other parameters:**

1. Select a parameter in the outgoing URL to contain the FBCLID.   
   Best practice: Select **af\_sub[1-5]**, so that the data displays in AppsFlyer raw data reports.
2. Provide this in the [list of arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) to the web developer. The result will be that in the outgoing URL, the FBCLID will be the value of the **af\_sub[1-5]** param.

</Accordion>

<div id="tiktok-ttclid-x-twclid-and-snapsccid" />

<Accordion title="TikTok (ttclid), X (twclid), and Snap(ScCid)">

Install attribution for TikTok, X (formerly Twitter), and Snap ad campaigns relies on network-specific Click ID parameters that are appended to ad clicks and used to match installs and post-install events to the originating ad.

When traffic is first redirected to a web page or landing page, the Click ID should be preserved and forwarded to ensure proper attribution. In this case, the Smart Script captures the incoming Click ID parameter and appends it to the outgoing URL it generates.

The Click ID will be captured on install and will be used in future events associated with the install.

From Smart Script version 2.10.0, the following Click ID parameters, when available, are automatically forwarded “as is” on outgoing URLs generated by the Smart Script:

* TikTok: ttclid
* X (formerly Twitter): twclid
* Snap: ScCid

You can also map these Click IDs to other outgoing parameters - such as af\_sub1-af\_sub5 to make them available in AppsFlyer raw data reports.

See the following relevant web integration articles:

* [TikTok](/docs/tiktok-for-business-create-web-based-campaigns)
* [Snap](/docs/snapchat-create-web-based-campaigns)

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="SRNs, owned media, and other media source links">

[SRNs](/docs/self-reporting-networks-srns#srns-integrated-with-appsflyer) like Snapchat or X Ads, work differently than Google Ads or a cross-platform like Meta ads. Campaigns from these SRNs lead your users to the web/landing page, and you are billed according to clicking leads, unrelated to any derived mobile users.

For these SRNs, script setup is the same as for links from owned media, or other media sources you might use.

**To set up the script**:

1. Make a list of the media source and campaign parameter names that are in the incoming links.
2. Provide these in the [list of arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) to the web developer.  
   The SRN/media source type should be the media source value in the incoming URL, and the script finds it and uses it as the **media\_source** value in the outgoing OneLink URL behind the download button on the web/landing page. If you want to change the outgoing **media\_source**, provide the incoming media source value and the override media\_source value in the [list of arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) you give to the web developer.

**Result**: For these SRNs/media sources, the values in the media source and campaign parameters in the incoming link are used to populate the values for the **media\_source** and **campaign** parameters in the outgoing link.

> 📘 **Example**
>
> **Incoming URL**: https://hotel.me/incoming_mediasource=twitter&incoming_campaign=big_social
>
> **Outgoing URL**: https://hotel.onelink.me/Ac4G?pid=twitter&c=big_social

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="AppsFlyer attribution links">

AppsFlyer attribution links can be used when the media source is a click ad network. When you set up such a link in AppsFlyer, you have the option to add a **Redirection URL path (af\_r)** parameter with the desired URL path to your mobile website for web campaign-to-app attribution. You may not want the Script to create an outgoing OneLink URL, as then, some of the data from the original click may be lost.

**Action:** Use the **urlSkipList** argument to list the **af\_r** parameter.

**Result**: When the Smart Script finds the **af\_r** parameter on the incoming link, the Smart Script doesn't produce an outgoing URL and the developer must decide what link to place as the outgoing URL and implement it.

> 📘 **Example**
>
> **Incoming URL**: https://app.appsflyer.com/id123456789?pid=click_ad_network_int&c=orlando&af_r=hotel.me
>
> **Outgoing URL**: No outgoing URL.

</Accordion>

<div id="web-referrer-mapping" />

<Accordion title="Web referrer mapping">

Web referrer mapping shows you which page users arrived at your website from (for example, organic search results), enriching the data you have for analyzing installs and re-engagements from your Smart Script web-to-app flow.

You can set the Smart Script to collect this information from your landing page or website HTTP header [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) field. This field contains the base URL of the page from which users clicked a link that sent them to your web page.

**To set up the script to collect the web referrer**

1. Open the **Smart Script** page
2. Under the **Web referrer mapping** area section select the outgoing URL parameter key for the web referrer value:
   * af\_channel - Parameter is available in dashboards and raw data
   * af\_sub1-5 - Parameter is available in raw data under the **af\_sub1-5** columns and in the **original URL** column.
   * Custom parameter - This is made up of the parameter name and value. The parameter is shown in raw data in **the original URL** column.

To learn about organic search attribution for re-engagements using Universal Links and App Links, see [here](/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution).

</Accordion>

<div id="seo-referrer-mapping" />

<Accordion title="SEO referrer mapping">

You can turn on **Media source for organic search installs** to automatically set the media source for organic search traffic when it isn't already resolved by the **URL parameter mapping** section.

* If the user's web referrer matches a supported search engine (for example, google.com or bing.com), Media Source is set to the matching channel (for example, google\_organic\_seo).
* If there's no match, the **Default value**, configured in URL parameter mapping, is used.

</Accordion>

<div id="desktop" />

<Accordion title="Desktop">

Most use cases in this article are of users coming from mobile devices. Therefore, when directed from the mobile website to an app store, they can immediately download your app.

However, desktop users shouldn't immediately be sent to an app store, because their device (a desktop or laptop) isn't compatible with mobile app downloads.

**To set up the script for desktop users**:

* In your [OneLink template](/docs/create-a-onelink-template#create-a-onelink-template), set a destination URL for **When link is clicked on desktop**. The URL should redirect to a dedicated web/landing page. The landing page can contain a web form where they fill in their details to get an SMS or an email with a link to download the app. It's up to you to create the web form and provide the URL to it in the script.

**Result**: The script detects the device or platform the user is on. If it's desktop, the script generates an outgoing OneLink URL that redirects the user to your dedicated web/landing page.

See also [Desktop-to-app conversion](/docs/qr-to-app-conversion).

</Accordion>

<div id="qr-codes" />

<Accordion title="QR codes">

Smart Script displays a QR code on your web page, instead of a button with a link behind it. 

**To display a QR code:**

1. Make sure you use Smart Script 2.6+ when you set up your Smart Script.
2. Tell your developer to follow [their instructions](https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#create-a-qr-code-with-the-smart-script-result) to create a QR code with the Smart Script result.
3. [Best practice] Tell the developer to:
   * [Customize the QR code](https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#create-a-qr-code-with-the-smart-script-result) by adding your app logo to the QR code center and customizing the color.
   * Show the QR code when users are on desktop and show the button with the link when users are on mobile.

**Result**: The script displays a QR code instead of a button with a URL behind it.

> 📘 **Example**
>
> **Incoming URL**:
>
> https://hotel.me/qr_code.html?incmp=gogo&inmedia=email
>
> **Outgoing URL**:
>
> https://hotel.onelink.me/LtRd/?af_js_web=true&af_ss_ver=2_1_0&pid=email&c=gogo
>
> **Outgoing QR code**:
>
> ![](https://files.readme.io/2f06149c901d8a97c2a544b8196e9afecbe3b3748ed8419a39c2dc5e3afa61ba-42045454923153.png)

</Accordion>

<div id="impressions" />

<Accordion title="Impressions">

The OneLink Smart Script can be used to count impressions on your website. To do so, the developer needs to call the impression function. Installs are then attributed to the impressions via [view-through attribution](/docs/measure-view-through-engagements).

**Note**:

* Counting impressions is in addition to the normal Smart Script-produced URL that counts clicks. Smart Script can be used to count clicks, impressions, or both.
* View-through attribution via Smart Script only works on mobile devices; not on desktop.

**To attribute new installs to these impressions (which is view-through attribution):**

1. Make sure you use Smart Script 2.3+ when you set up your Smart Script.
2. Tell your developer to [call the impression function](https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#fire-an-impression) in the Smart Script.
3. Make sure [view-through attribution is turned on](/docs/measure-view-through-engagements).

> 📘 **Important!**
>
> As of February 1st, 2023 (Chrome 110 stable release), Google has made some changes to [reduce User-Agent data](https://developer.chrome.com/en/docs/privacy-sandbox/user-agent/). In order to properly get [view-thorough attributions](https://www.appsflyer.com/glossary/view-through-attribution/) using the OneLink Smart Script, you should use the OneLink Smart Script version 2.3 and above.

</Accordion>

## Additional information

<div id="faq" />

<Accordion title="FAQ">

#### **Will the incoming URL for OneLink link generation work if the user browses to a different page on the website?**

Yes. Incoming URL parameters are stored for the duration of the browsing session and applied to the outgoing parameters of the Smart Script-generated OneLink link. For more implementation info, [see our developer hub](https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#preserve-incoming-url-parameters-across-pages).

#### **Why do I get an error when implementing Smart Script via Google Tag Manager?**

Sometimes when you generate the Smart Script in AppsFlyer and try to insert it into Google Tag Manager (GTM), a "JavaScript too long" error displays. If this occurs, delete the GTM tag and create a new one.

#### **Can I add parameters that are not listed?**

Yes. In your OneLink Smart Script page, click on + **New parameter** to map additional parameters.

* New parameters can be custom parameters or AppsFlyer reserved parameters that are not listed in the dropdown.
  * See all the [additional arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) (parameter configurations) you can use.
* Use the Custom option from the dropdown and your parameter to the **Outgoing URL parameters** field.

For example, to add is\_retargeting as a parameter, Custom parameter would be selected in the **mapping for** field, and then our is\_retargeting parameter to the **Outgoing URL parameters** field.

![Smart_Script_Custom.jpg](https://files.readme.io/5a09d18b01ece93bbb47667b676039c98742ebc3b88c5235ad92c7e44d5316b9-small-42045454926609.jpg)

#### **Adset and other parameters are not showing in the dropdown**

We recommend turning off any ad blockers you have on your browser when creating or adding new parameters. Sometimes ad blockers will remove an option if it has the word 'Ad' in it.

#### **What browsers does Smart Script work on?**

Smart Script uses Javascript and should work on all browsers.

</Accordion>

<div id="specs-and-limitations" />

<Accordion title="Specs and limitations">

| **Spec** | **Remarks** |
| --- | --- |
| URI scheme | Even if a URI scheme is set in the OneLink template to open the app for existing users, for links created using Smart Script, the af\_dp parameter with the URI scheme must be added by the developer to URLs as a [custom parameter](https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#set-additional-custom-parameters). |
| **in incoming URL**| Smart Script encounters issues when handling incoming URLs that include a hash ('#') symbol preceding the query parameters (indicated by a '?' sign). In such cases, Smart Script  reverts to default values. |

</Accordion>

<div data-zendesk-anchors="h_01H95PGMNWR12KQ2P0KT8BBGEC=setup h_01H95PGMNW6N63XQ1EQSQSHHB2=set-up-onelink-smart-script h_01H95PGMNWPBRHSZBPMKNJ2PS6=scope-of-work h_01H95PGMNWWYRRNVNTK31XYRN3=how-to-create-a-onelink-smart-script h_01H95PGMNW5HA4FWBFW7AR89AV=important h_01H95PGMNXZAES8DPJ1B4E1QV8=how-to-edit-or-delete-a-script h_01H95PGMNX5ZT7DPV2WBG0CTKB=important-1 h_01H95PGMNXNT9C07B0YTS1KK82=how-to-duplicate-a-script h_01H95PGMNXWJ9V5JW9JEAHF81S=argument-structure h_01H95PGMNXR2HTV1EF07QVQB6W=arguments arguments-parameters-and-values-to-implement-the-smart-script::d4f6bf94=arguments-parameters-and-values-to-implement-the-smart-script h_01H95PGMNXPMCM73XT3GTDVAXJ=arguments-parameters-and-values-to-implement-the-smart-script h_01H95PGMNX4B8W84DHJR9T4CR2=advanced-arguments arguments-parameters-and-values-to-implement-the-smart-script=advanced-arguments-parameters-and-values-to-implement-in-the-smart-script h_01H95PGMNXCAHTTJATG75Y3TRN=advanced-arguments-parameters-and-values-to-implement-in-the-smart-script h_01H95PGMNXBPFFNE44YGGECBPR=use-cases h_01H95PGMNX3W95JW47YQGSEYQ6=utm-parameters h_01H95PGMNXGZZEMZ6PMAB4XFQQ=google-ads-gclid h_01H95PGMNXZT08G8RTMMG6BQCJ=note h_01H95PGMNXHJXGB2QXH0YTB6Z0=facebook-click-id h_01KD5EZQFF23MYGXGJF1CF6VPT=tiktok-ttclid-x-twclid-and-snapsccid h_01H95PGMNXBKXFG9M169WG89TK=srns-owned-media-and-other-media-source-links h_01H95PGMNXZPB6CT3ZKJ2KMQ1J=example h_01H95PGMNX8Q0BASSESVD06MXE=appsflyer-attribution-links h_01H95PGMNX741EJGPF9G2DS67N=example-1 h_01HAS199KS0C0V3G41WGXTK4PF=web-referrer-mapping h_01M1BK4M22YAQ6YX4RZXRKZF7C=seo-referrer-mapping h_01H95PGMNY0P2354ZFVC92TMVC=desktop h_01H95PGMNYDSFP6GJDWC9AE0J2=qr-codes h_01H95PGMNYGJ9BJ86YCP7FYH6G=example-2 h_01H95PGMNYZBGZWNFESDTE9GY9=impressions h_01H95PGMNYX1FDT1KK9PQAMX5N=important-2 h_01H95PGMNYB6A8VKEAH8Z8TDPE=additional-information h_01H95PGMNYKQ8TNM3KKK9EXANV=faq h_01H95PGMNYM5X2K9J0WZW6PZ8A=will-the-incoming-url-for-onelink-link-generation-work-if-the-user-browses-to-a-different-page-on-the-website why-do-i-get-an-error-when-implemeting-smart-script-via-google-tag-manager=why-do-i-get-an-error-when-implementing-smart-script-via-google-tag-manager h_01H95PGMNYSQX6BJCN56D4XZZF=why-do-i-get-an-error-when-implementing-smart-script-via-google-tag-manager h_01H95PGMNY2AVJ0CYDAM62Q9PA=can-i-add-parameters-that-are-not-listed h_01H95PGMNY97BY6BCPPMYHBF0Q=adset-and-other-parameters-are-not-showing-in-the-dropdown h_01H95PGMNY5AV0DTX51X0DJMTK=what-browsers-does-smart-script-work-on h_01H95PGMNY4W9X51KV6GM4BSPG=specs-and-limitations" />
