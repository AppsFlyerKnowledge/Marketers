---
title: Swrve integration with AppsFlyer
metadata:
  keywords:
    - Swrve
    - Adobe Analytics
    - 3rd Party
    - SDK
    - Integration
    - integrated partner
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:46:00Z'
  edited_at: '2026-08-14T16:22:59Z'
  id: 207040656
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207040656-Swrve-integration-with-AppsFlyer
---
> **At a glance:** Swrve, an AppsFlyer integrated partner, is a cross-platform customer interaction engine, allowing advertisers to deliver targeted, personal and optimized interactions to end-users:

* Dynamic optimization and testing of core app content
* In-app and push notification campaigns
* Email

Alongside AppsFlyer, Swrve provides a complete lifecycle solution for maximizing the ROI on development and acquisition spend, and delivers outstanding user experiences throughout the mobile app journey. That includes customizing user experience based on acquisition source shared between the two platforms, meaning users can be served content specific to their user journey from the moment they open the app for the first time.

The integration works by notifying Swrve of installs to their API using their REST API. To do so, you will need to set up a server postback in your AppsFlyer account for each one of your mobile apps.

> 🚧 **Important**
>
> <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Integrating Swrve and AppsFlyer

Setting up a postback that allows Swrve to measure LTV and user behavior for different acquisition sources:

**Step 1**: After initializing Swrve, set your user’s ID (before any call to the AppsFlyer SDK) with the following:

<Tabs>
<Tab title="For Android">

```java
AppsFlyerLib.setCustomerUserId(SwrveSDK.getUserId());
```

</Tab>

<Tab title="For iOS">

```objectivec
NSString* swrve_user_id = [[Swrve sharedInstanceWithAppID:appId apiKey:apiKey] userID];
[[AppsFlyerTracker sharedTracker].customerUserID = swrve_user_id];
```

</Tab>

<Tab title="For Unity">

```swift
Appsflyer.setCustomerUserID(SwrveComponent.Instance.SDK.UserId);
```

</Tab>
</Tabs>

**Step 2**: Set a postback in your AppsFlyer dashboard by performing the following actions:

## Setting up Swrve

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

Swrve's configuration window only uses the **Integration** tab.

For a detailed description of the Partner Configuration Window Header, click <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">here</Anchor>.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable the set up of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">here</Anchor>.

### General settings

**App ID and API Key**

Swrve connects with AppsFlyer via a unique App ID and API Key. If you don't already have them, you must obtain them from Swrve to continue with the integration.

![Swrve_msc_new_3.png](https://files.readme.io/feb1d5f846629d1909727b70b66e4b36138704ebbe4518e2dc03652b9fe5c57a-360001902065.png)

Perform the following steps, as required:

* Enter the **APP\_ID**
* Enter the **api\_key**
* Select **EU** for EU customers
* Select **Advanced Data Sharing** to send the following additional information to Swrve: cost\_value, channel, keywords, siteID, and c (campaign)

### Default postbacks

AppsFlyer can send automatic postbacks to Swrve following user installs. Use this section to define sending these postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/8d263c9367eb9668c985ffcadf5981475de9f4336b6da8c4c6cef45734a7897b-360001902245.png)

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Swrve.

Click **Save**

Once saved, AppsFlyer begins sending the following data to Swrve for every organic and non-organic install:

* api\_key
* Swrve user ID as set in the SDK
* Media Source
* Campaign Name

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for Swrve.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions are not available for Swrve.

</Accordion>

## Swrve reporting with AppsFlyer data

After you have server postbacks set up to send attribution information from AppsFlyer to Swrve, you can view acquisition data in the Swrve platform and utilize the full range of Swrve targeting and testing functionalities.

The main dashboard page for your app includes all of your app's vital information at a glance. From this page, you can continue to utilize the testing, targeting, and reporting features by selecting the relevant tabs in the main navigation bar.

![Swrve dashboard acquisition graph](https://files.readme.io/6a3e4cf709f58b20f2932ab47e6fa9289653504d85a0b6eec2580718e2a4dc7c-49839257162769.png)
![Swrve dashboard acquisition data table](https://files.readme.io/561403abefae9e98e24934c96dd25b1ee34ae24cf30695354c4930404e0a7f19-49839257163537.png)

<div data-zendesk-anchors="h_01H9HWK5DM1K9P5XXC6S7ENAGV=integrating-swrve-and-appsflyer h_01H9HWK5DMS8HAK25BF5EXZT51=setting-up-swrve h_01H9HWK5DN9D0DS46X72EDAW54=integration-tab h_01H9HWK5DN375XJVHQCZ8Y3K13=activate-partner h_01H9HWK5DN0XK2E0HXS61GRECE=general-settings h_01H9HWK5DNH6SYY8T9NX09MRYS=default-postbacks h_01H9HWK5DNZVQDZ0Q1Z9WSKRSR=attribution-link-tab h_01H9HWK5DNPG89HSB0107TKHED=cost-tab h_01H9HWK5DNARD4K0MPHPXKBPXZ=ad-revenue-tab h_01H9HWK5DNFKAT0J98JWVRPQ1G=permissions-tab h_01H9HWK5DN3QB9V593EV566GAQ=swrve-reporting-with-appsflyer-data" />
