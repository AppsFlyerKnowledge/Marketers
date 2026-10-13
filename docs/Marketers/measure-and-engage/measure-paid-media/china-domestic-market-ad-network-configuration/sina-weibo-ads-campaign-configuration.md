---
title: "Sina Weibo Ads campaign configuration"
excerpt: "Learn how to configure Sina Weibo Ads campaigns in AppsFlyer, including setting up attribution links, retargeting, and permissions."
x-zendesk:
  id: 115004134086
  url: https://support.appsflyer.com/hc/en-us/articles/115004134086-Sina-Weibo-Ads-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: China domestic market ad network configuration
  section_id: 6552066355601
  position: 29
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Advertisers, Sina Weibo Ads, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2017-08-15T08:37:03Z'
  edited_at: '2026-09-15T10:50:56Z'
---
**At a glance:** Sina Weibo Ads, an AppsFlyer ad network integrated partner, is one of the most popular social media platforms in China.

## Setting up Sina Weibo Ads

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

The Sina Weibo Ads configuration window includes 3 active tabs: Integration, Attribution link, and Permissions. Click on the items below to read about the tabs setup.

## Integration tab

This section is used for connecting the partner with AppsFlyer. Relevant messages for the advertiser regarding the specific partner also appear here.

### Activate partners

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

Default Postbacks

If attribution/integration is enabled for the partner, AppsFlyer can send automatic postbacks to it following user installs, launches, re-engagements, and rejected installs. Use this section to define the **source of the users** that postbacks are sent for.

![Sina_Weibo_msc_new_2.png](https://files.readme.io/0f71568fd13ce9357f07282636e0b86fdbb9e9b1f6ef9db8ba673bb2066881aa-360002277585.png)

The option "**Only events attributed to this partner**" for partner attributed users only, is selected by default.

Click **Save**.

## Attribution link tab

In this tab, you can create the attribution links you want to send to Sina Weibo Ads for attributing the Sina Weibo Ads campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* **Campaign** - add it to compare different campaigns running with Sina Weibo Ads.  
  **Attribution link parameter:** c
* **Adset** - set ad set names to compare different ad sets within specific Sina Weibo Ads campaigns.  
  **Attribution link parameter:** af\_adset
* **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Sina Weibo Ads.  
  **Attribution link parameter:** af\_ad
* **Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.  
  **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.  
  **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

[![](https://files.readme.io/d3efcf846c2f75515e714e3ae8a7a15000dd76093702f82bc0d8bfb04a3a8aee-360002299609.png)](https://files.readme.io/d3efcf846c2f75515e714e3ae8a7a15000dd76093702f82bc0d8bfb04a3a8aee-360002299609.png)

Add any other parameter to the attribution link simply by typing it in a new parameter box. More information about[**AppsFlyer Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters)**.**

### Retargeting settings

You can add any other parameter to the attribution link simply by typing it in a new parameter box. You can find all AppsFlyer available URL parameters here: [**AppsFlyer Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters)

When enabled, AppsFlyer recognizes a link as a [retargeting](/docs/retargeting-attribution-guide) attribution link, rather than a user acquisition link, by adding the `&is_retargeting=true` to the click recording link. Note that retargeting is currently only supported for click-through and not view-through attribution.

**Attribution link parameter**: `is_retargeting`

The setup below is displayed when retargeting is enabled.

![retargeting_settings.png](https://files.readme.io/b883d2601724f887b8c217668f6398041e643ca24c3eb0a032abb20536beebc1-360002299629.png)

***Standard Link*** **vs.** ***OneLink***

Select ***standard attribution link*** option if:

* You don't need to deep link with the URL or
* You plan to use only [URI schemes](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings) for deep linking

Select ***Use OneLink*** for:

* Using a single link for both Android and iOS apps or
* Deep linking using Universal or app links

Note that selecting OneLink changes the click recording link from app specific to a [OneLink URL](/docs/onelink-guide).

***Deep Link URL***

Use this field if the link is meant to deep link users to any specific activity within your app.  
**Attribution link parameter**: `af_dp`  
You can find more information about AppsFlyer's [deep linking solution in this guide.](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink)

***Re-engagement Window***

Set the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source. You can set the value in days (1-90), hours (up to 23), or even lifetime.

**Attribution link parameter**: `af_reengagement_window`

Read here [how to set up retargeting](/docs/sina-weibo-ads-campaign-configuration#creating-retargeting-campaigns-on-weibo-ads-dashboard) on Sina Weibo dashboard.

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Sina Weibo Ads.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

[![sina weibo clickthrough settings](https://files.readme.io/2c6cba9eba0b01cba638707df6bdb94c1a78b4d2b98f65d5210538311458b763-360002715417.png)](https://files.readme.io/2c6cba9eba0b01cba638707df6bdb94c1a78b4d2b98f65d5210538311458b763-360002715417.png)

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Sina Weibo Ads to be activated when leads click on a corresponding ad.

## Cost tab

Cost integration is not available for Sina Weibo Ads.

## Ad revenue tab

Ad Revenue data is not supported by this partner.

## Permissions tab

In this tab, you can select the permissions to grant to the partner, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for the partner, the permissions tab is active and you can grant control to the partner.

![sina-weibo-permissions.png](https://files.readme.io/a22be58687921e80108fe4b2cbd2863d9277a938a751ed5c666f147d78041c05-360002799478.png)

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -*only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*****a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions](/docs/set-up-an-integrated-partner#permissions-tab).

## Setting AppsFlyer attribution on Weibo ads dashboard

Login to Sina Weibo Ads, using this link: [https://ad.weibo.com/](https://ad.weibo.com)

Go to the **Tools** page to upload your apps in the Apps Management section:

[![](https://files.readme.io/56d413ce75a2a3b4ca78a6928f60b9898bbd892d43d370197189da66ef9b078b-360000449769.png)](https://files.readme.io/56d413ce75a2a3b4ca78a6928f60b9898bbd892d43d370197189da66ef9b078b-360000449769.png)

Click to add new apps:

[![](https://files.readme.io/2c372745a5fe9b05325731e29e24f0b5097a43664e9a28e288d0b9300aecee8e-360000441885.png)](https://files.readme.io/2c372745a5fe9b05325731e29e24f0b5097a43664e9a28e288d0b9300aecee8e-360000441885.png)

Android: Enter the APK download page (end with .apk) or upload the APK document.

iOS: Enter the iTunes link.

### Setting the attribution link

Go to the **Promotions** page and Create New Ad Series

[![](https://files.readme.io/eaf980c1adc0b134265162c114f66b1bf049a80336116db76d353ee5113a9ae5-360000449909.png)](https://files.readme.io/eaf980c1adc0b134265162c114f66b1bf049a80336116db76d353ee5113a9ae5-360000449909.png)

If you want to acquire new users for your app, select **Increase App Installs** ad type, as shown below:

[![](https://files.readme.io/b9e75ac4c9681cebfa06ba6965032b1ff0dc11b2da6e8c2b11cc9219555fa4e7-360000442105.png)](https://files.readme.io/b9e75ac4c9681cebfa06ba6965032b1ff0dc11b2da6e8c2b11cc9219555fa4e7-360000442105.png)

### Setup ad series

Select the app you want to promote:

[![](https://files.readme.io/cf9697b09d8d8b5416b8029cb20c2137eda24d9616bf2db2e1e45a3ec150fcf3-360000450049.png)](https://files.readme.io/cf9697b09d8d8b5416b8029cb20c2137eda24d9616bf2db2e1e45a3ec150fcf3-360000450049.png)

Set the audience features, budget, and promotion periods:

[![](https://files.readme.io/709297bb78cbd48218ee5438a40a5a12e78eeeecf4e35414ec36de89420791b6-360000442205.png)](https://files.readme.io/709297bb78cbd48218ee5438a40a5a12e78eeeecf4e35414ec36de89420791b6-360000442205.png)

### Uploading ad creatives and set the attribution link

Weibo provides four ad formats to promote App installs:

* Weibo Post
* Big Cards
* App Card
* App 9 Pics

All of the ad formats support AppsFlyer Attribution.

[![](https://files.readme.io/5404349a21a783509e6de074826ace0db0d66248853f229ad444fabec95b8311-360000450369.png)](https://files.readme.io/5404349a21a783509e6de074826ace0db0d66248853f229ad444fabec95b8311-360000450369.png)

Enter the AppsFlyer attribution link

> 📘 **Example**
>
> ```
> https://app.appsflyer.com/com.king.candycrushsaga?pid=sinaweibo_int&c=creative1
> 	&clickid=`{IMP}&md5_idfa={idfa_MD5}&md5_imei={imei_MD5}`&redirect=false
> ```

[![](https://files.readme.io/27113a1303fea22bde74527c7103bfbda8e8fd7755c44a52508a02368e0a6407-360000442725.png)](https://files.readme.io/27113a1303fea22bde74527c7103bfbda8e8fd7755c44a52508a02368e0a6407-360000442725.png)

Complete any additional settings and publish the ad.

> 📘 **Note**
>
> * You can preview the Ad Format in the upper right part at Ad Creative Setting Page.
> * If you are not using deep linking in the ad campaign, leave the deep link box empty.

## Creating retargeting campaigns on Weibo ads dashboard

On ad campaign level, set up the targeting, budget, and campaign time:

![sina-weibo-retargeting.png](https://files.readme.io/8225fbfd74d16bb1a3e2e816933cb22d5f581a219ee35dd7f9d5285bacd49d2d-360002715577.png)

On the ad level, set up the deep link and AppsFlyer attribution link:

1. Choose ***deeplink+app***, and paste the deep link into the relevant box:

   ![sina-weibo-retargeting-deeplink.png](https://files.readme.io/dc5666893ff99dcb808a15aa2e41396b359617e2f6271f246a10893d4b05eebe-360002715557.png)

   CALLSTART::Note::

   #### Example

   ```
   myapp://products/page1&pid=sinaweibo_int&is_retargeting=true
   ```

   CALLEND::
2. Copy the attribution link from AppsFlyer dashboard with all the required parameters and paste it into the attribution link box:

   ![sina-weibo-retargeting-links.png](https://files.readme.io/edd0861728e19a0bc0e23641161c2365cf5c41eeccaa801bd4e8c3392215fe83-360002799598.png)

   CALLSTART::Note::

   #### Example

   ```
   https://app.appsflyer.com/com.mycompany.myapp?pid=sinaweibo_int&c=test&clickid={IMP}
   &md5_idfa={idfa_MD5}&md5_imei={imei_MD5}&redirect=false&is_retargeting=true
   ```

   CALLEND::
   CALLSTART::Note::

   #### Note

   Note that all following parameters should be included in both the deep link and the attribution link and be identical in both links:

   * `&pid=sinaweibo_int` — partner ID parameter that identifies Sina Weibo as media source
   * `&c=campaign_name` — parameter that identifies a specific campaign
   * `&is_retargeting=true` — parameter that identifies an ad as a part of a retargeting campaign

   If you use deferred deep linking, include the following parameters as well:

   * `&af_adset=adset_name`
   * `&af_ad=ad_name`

   Read more about [AppsFlyer's Attribution Link Structure and Parameters](/docs/about-link-structure-and-parameters) and Sina Weibo's [attribution links](#attribution-link-tab).

   CALLEND::