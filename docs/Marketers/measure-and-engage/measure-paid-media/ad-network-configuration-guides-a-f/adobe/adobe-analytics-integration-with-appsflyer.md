---
title: "Adobe Analytics integration with AppsFlyer"
excerpt: "Learn how to set up the two-way data flow between AppsFlyer and Adobe Analytics to automatically transfer attribution data."
x-zendesk:
  id: 115003326706
  url: https://support.appsflyer.com/hc/en-us/articles/115003326706-Adobe-Analytics-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Adobe
  section_id: 6551419728657
  position: 0
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Adobe Analytics, Integration, Advertisers, Developers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2017-07-05T07:20:10Z'
  edited_at: '2026-09-22T08:30:33Z'
---
**At a glance:** [Adobe Analytics](http://www.adobe.com/marketing-cloud/web-analytics.html) (formerly Omniture) is a set of tools for predictive and real-time analytics that can be integrated into third-party sources. It includes the Marketing Reports and Analytics (SiteCatalyst), Ad hoc analysis (Adobe Discover), and Insight applications to help create a holistic view of business activities by transforming customer interactions into insights.

## Overview

This integration consists of a two-way data flow between Adobe and AppsFlyer. For the integration to be successful, this integration requires code implementation in your app. Both AppsFlyer and Adobe requirements must be met for the integration to be fully successful.

## Setting up Adobe Analytics integration

If you are using Adobe Analytics Report Suite for overall campaign performance analysis and segment creation, then the AppsFlyer integration with Adobe Analytics enables the automatic transfer of attribution data from AppsFlyer to Adobe to help you achieve your goals.

### Prerequisites:

* Setting up [Adobe Experience Platform mobile SDK docs](https://developer.adobe.com/client-sdks/documentation/)
* [Marketing Cloud Visitor ID](https://experienceleague.adobe.com/en/docs/id-service/using/home) or Experience cloud ID service
* Three eVars in each report suite that can be used for the sole purpose of this integration

### Step 1: Share Adobe Experience Cloud ID (ECID, Marketing Cloud ID, or Visitor ID) with AppsFlyer.

To extract and share Adobe Experience Cloud ID:

1. [Update the application and extract the Marketing Cloud Visitor ID](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid) using the Adobe SDK method right after the Adobe SDK is initialized.
2. Use one of the following AppsFlyer SDK methods to set the Adobe Marketing Cloud Visitor ID:

### setAdditionalData

Android iOS Unity

Learn more about [the setAdditionalData method](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata).

```
HashMap<String, Object> customData = new HashMap<String,Object>();
customData .put("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyerLib.setAdditionalData(customData);
```

Learn more about [the setAdditionalData method](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata).

Objective C

```json
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{
  @"marketingCloudID" : "ADOBE_VISITOR_ID"
}];
```

Swift

```javascript
let CustomDataMap: [AnyHashable: Any] = [
  "marketingCloudID" : "ADOBE_VISITOR_ID"
]
AppsFlyerTracker.shared().customData = CustomDataMap
```

Learn more about [the setAdditionalData method](https://dev.appsflyer.com/hc/docs/api#setadditionaldata).

```
Dictionary<string, string> CustomDataMap = new Dictionary<string, string>();
CustomDataMap.Add("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyer.setAdditionalData(CustomDataMap);
```

### setCustomerUserId

Android iOS

Learn more about [the](/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer) [setCustomerUserId](/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer)[method](/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer).

```
AppsFlyerLib.getInstance().setCustomerUserId("ADOBE_VISITOR_ID");
```

Learn more about [the setCustomerUserId method](/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer).

Objective C

```
NSString *customerUserID = [AppsFlyerLib shared].customerUserID;
```

Swift

```javascript
let customerUserID = AppsFlyerLib.shared().customerUserIDp
```

### Step 2: Configure Adobe analytics in AppsFlyer

**Prerequisite:** Before setting up the integration, make sure to [pass the Adobe Marketing Cloud Visitor ID to the AppsFlyer SDK](/docs/adobe-analytics-integration-with-appsflyer#step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer).

**To activate or edit the integration:**

1. **To activate:** In AppsFlyer, from the side menu, select**Collaborate**> **Partner Integrations > Marketplace** tab.  
   **To edit**: In AppsFlyer, from the side menu, select**Collaborate**> **Partner Integrations > Active integrations tab**.
2. Search for the **Adobe Analytics** and select it.
3. Click **Integrate**. You’re directed to the integration setup page.
4. In the **Integration** tab, select the app for the integration and turn **Activate partner** on.  
   **Note:** The toggle must be on [(activated)](/docs/partner-activation-deactivation) for as long as you work with the partner.
5. Configure the default postbacks sent to Adobe Analytics. AppsFlyer can send automatic postbacks for both installs and re-engagements (including re-attributions). Learn more about [default postbacks](/docs/set-up-an-integrated-partner#default%20postbacks).
6. From the **Adobe Analytics SDK**, as part of the **ADBMobileConfig.XML** file, copy the **Report\_Suite\_ID** (highlighted in blue) and the **Adobe\_Analytic\_server\_URL** (highlighted in green) and paste them into the respective fields in the Adobe Analytics integration page in AppsFlyer.

   ![](https://files.readme.io/fb46a40178b88dc8f8fb0f9bcce5aa289fc27c2dbf52d1e67783c7b764729f0f-360001063605.png)
7. Click **Save Integration**.

Once saved, AppsFlyer sends the following data to Adobe Analytics for every organic and non-organic install:

* Adobe ID (MCVID)
* Report Suite ID & Server URL
* Customer Device ID
* Media Source
* Campaign Name

> 📘 **Note**
>
> In accordance with the terms of service of both Meta ads and X Ads, AppsFlyer is prohibited from sharing user-level data with third parties. This means that Meta ads and X Ads installs are sent as organic.

### Step 3: Map data to eVars in Adobe Analytics

Due to the deprecation of the Adobe Analytics Data Connectors, you will need to leverage processing rules to map context variables to the eVars.

Learn more about [how to use processing rules](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html?lang=en).

AppsFlyer context data variables mapped accordingly:

* MobileAdCampaign(Context Data)
* MobileAdNetwork(Context Data)
* MobileAdProvider(Context Data)

Should you have issues with mapping AppsFlyer context data variables through processing rules, contact your Adobe account team for further support

### Step 4 [optional]: Set up your marketing channel

See [Adobe Analytics documentation](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-channels.html) on how to set up your marketing channel on their platform. Make sure to select the following fields under the identifying rules:

1. "The conversion variable value set by Adobe's web beacon": Select **AppsFlyer** and **Exists**.
2. "Identify the channel as": Select **Mobile App Attribution**.
3. "Set the channel's value to:" Select **AppsFlyer Campaign**.

## Domain and security details

Set out below are the details of the domain and security issues:

1. ANALYTIC\_SERVER\_DOMAIN can be found as the server variable in your App’s Config file. You can select any domain for attribution analytics. In general, standard domains for the Adobe Analytics collections service such as sc.omtrdc.net are used. This can be found under the analytics (server) settings in their **ADBMobile.config** file.
2. The protocol (HTTP/HTTPS) of the URL depends on whether the ANALYTIC Server Domain is secure or not. It is important that you use the correct protocol. To find out if the setting is secure, check whether the analytics (SSL) setting is set to **true** in the **ADBMobile.config** file. If your connection is secure use HTTPS, if it is not secure use HTTP.
3. REPORT SUITE ID can be found as the **rsids** variable in your Apps’ Config file. You can give any name to your report suite.
4. The ts=`{timestamp}` is only used if your **offlineEnabled** configuration is true in your Config file. Remove this parameter from the URL if the **offlineEnabled** is set to False or if your report suite is not **Time Stamp** enabled.