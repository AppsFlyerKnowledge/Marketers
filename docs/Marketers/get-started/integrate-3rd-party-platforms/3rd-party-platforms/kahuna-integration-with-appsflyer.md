---
title: "Kahuna integration with AppsFlyer"
excerpt: "Kahuna, an AppsFlyer integrated partner, dedicated to empowering businesses to grow and thrive in the mobile era. We enable a new level of authentic engagement between brands and their customers wherever they are — the web, email, mobile, social channels — through personalized communication at scale. Powered by big data and machine learning, we help create delightful experiences for every customer with the perfect message, delivered on the right channel, at just the right time."
x-zendesk:
  id: 212561966
  url: https://support.appsflyer.com/hc/en-us/articles/212561966-Kahuna-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 14
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [kahuna, Advertisers, Ad Networks, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-09-14T11:26:59Z'
  edited_at: '2026-06-16T11:44:01Z'
---
> 📘 **Important!**
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

Follow the instructions below to configure the integration with Kahuna:

1. Minimum requirements - AppsFlyer SDK:

* Android – version 2.3.1.18 and above
* iOS – version 3.3.3 and above

2. Integrating with Kahuna requires that the Kahuna [Device ID](https://www.appsflyer.com/mobile-fraud-glossary/deviceid/) (Kahuna’s unique user identifier) is populated in AppsFlyer's SDK. This parameter is sent with every postback and enables the identification of each user. To perform this you must insert the following strings to your app code:

> 📘 **Important Note**
>
> Make sure the lines of code are inserted at the correct place – after Kahuna SDK was launched and before the appsflyer.sendtracking (Android) / trackAppLaunch (iOS) methods are called.

For AndroidFor iOS

```
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId = Kahuna.getInstance().getKahunaDeviceId();
customData .put("customData", deviceId);
AppsFlyerLib.setAdditionalData(customData);
```

```
NSString *kahunaDeviceID = [Kahuna getKahunaDeviceId];
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{@"customData" : kahunaDeviceID}];
```

## Setting up Kahuna

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

The Kahuna configuration window uses only the ***Integration*** tab.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you will need to toggle below. ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### General settings

**Kahuna Secret Key, Staging and Production**

Kahuna connects with AppsFlyer via a unique Secret Key. If you don't already have it, you must obtain it from Kahuna to continue with the integration or follow the steps below. [![](https://files.readme.io/941ce1b787ab4c34a502f254f7ec3ec8da356a05c99625f5e60e54b0da1f06b6-360002216249.png)](https://files.readme.io/941ce1b787ab4c34a502f254f7ec3ec8da356a05c99625f5e60e54b0da1f06b6-360002216249.png)

### Obtaining the kahuna secret key

1. Login to your Kahuna account

2. Click the user icon and Select **Settings** on the right-hand corner of dashboard menu

[![](https://files.readme.io/4962454c4dd428c69e90d4ebcfa20304dc0ea57c7d58a1368c9a9369ba3e563a-207206166.png)](https://files.readme.io/4962454c4dd428c69e90d4ebcfa20304dc0ea57c7d58a1368c9a9369ba3e563a-207206166.png)

3. Copy the Kahuna secret key:

[![](https://files.readme.io/73d24826e6c55636dafbc22766910fea12fbe7a58c49079c800d5056be45352a-207229823.png)](https://files.readme.io/73d24826e6c55636dafbc22766910fea12fbe7a58c49079c800d5056be45352a-207229823.png)

4. Select **APIs & Integrations**– on this page you can find the parameters:

* Insert the Kahuna Master Key taken from Kahuna console (see Section 3)
* If you want to send the events to Kahuna’s Sandbox environment insert the letter S in the Staging box (see “Testing with Kahuna Sandbox”)
* For the Production environment insert the letter P in the production
* If you insert both, the events are sent to production
* Click **Save**

### Default postbacks

AppsFlyer can send automatic postbacks to Kahuna user installs. Use this section to define sending these postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/658d00352fc237b1fb1a3a376f376f600f245e47fffa19b9f1f1ca5cc20c8386-18274496571537.png)

Select **Events attributed to any partner or organic** to send postbacks for any user that downloads the app to Kahuna.

Click **Save.**

Once you have saved the configuration, AppsFlyer sends the following data to Kahuna for every organic and non-organic install:

* Kahuna Dev\_ID
* Media Source
* Country code
* OS Version

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for Kahuna.

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

Permissions are not available for Kahuna.

</Accordion>

## View user attribution data in Kahuna

The install events can be viewed as Newbies in Kahuna's main dashboard.

[![](https://files.readme.io/ebbb7f265e37ead80dd77a9956b9629ce07eeb2fcc9b283ad7b6cc927fe10758-207230483.png)](https://files.readme.io/ebbb7f265e37ead80dd77a9956b9629ce07eeb2fcc9b283ad7b6cc927fe10758-207230483.png)

You can search for a specific user or go to “Top People” in your left side navigation.

[![](https://files.readme.io/ea6ae8494f600bb8a9b9b0af3e36a976e65d72b64052da3e7399f9a9b0c9458c-207230503.png)](https://files.readme.io/ea6ae8494f600bb8a9b9b0af3e36a976e65d72b64052da3e7399f9a9b0c9458c-207230503.png)

Selecting one of the users opens the Mini Profile where you can see the install event “af\_install” in the Top Events section:

[![](https://files.readme.io/3e0a99f178cc1a9ab18886a576b4ba56878fecb6dbd0866926730fb32b65bc59-207230563.png)](https://files.readme.io/3e0a99f178cc1a9ab18886a576b4ba56878fecb6dbd0866926730fb32b65bc59-207230563.png)

## Testing with sandbox

If you haven’t released your app to the app store yet and want to test the integration from Kahuna’s Sandbox environment, follow these steps:

1. Make sure you enter “s” in the Staging Textbox when configuring Kahuna within AppsFlyer

[![](https://files.readme.io/b69fc390ed7f1303ee8ba6dd1345d2c76b5b4c22b4b0b6ec0957a108d709247b-360002217229.png)](https://files.readme.io/b69fc390ed7f1303ee8ba6dd1345d2c76b5b4c22b4b0b6ec0957a108d709247b-360002217229.png)

2. Make sure you have added the code to your App to integrate AppsFlyer and Kahuna SDKs as described in the above sections

3. You must obtain the Advertising ID from your test device (you can find the Advertising ID by installing the app on your device and looking at the logs)

4. Ask AppsFlyer to allowlist your Advertising ID

5. Uninstall the app from your device

6. Configure this URL with your data (app package name, advertising ID, and campaign name...don’t include the brackets) - [https://app.appsflyer.com/[APP PACKAGE NAME]?pid=[SOMETHING]&advertising\_id=](https://app.appsflyer.com/com.dailylabs.kahunatest?pid=Testing_Installs&advertising_id=0eea1488-3037-44b2-a944-11f8bfc3e479)[DEVICE’S ADVERTISING ID]

7. Go to that URL, you may see this:

[![](https://files.readme.io/8b16b6d84f0244db3510e4376bf5fc51b6a737e13df89da82e951e1bda90711a-207230963.png)](https://files.readme.io/8b16b6d84f0244db3510e4376bf5fc51b6a737e13df89da82e951e1bda90711a-207230963.png)

8. Install the App on your device

9. Go to Kahuna’s dashboard and search for the user (you can enable Kahuna debugging and look at the logs to get the Kahuna unique device ID for that user.. “dev\_id”... or if your app requires log-in and you pass credentials to Kahuna, then you can search by that credential also). Once you find the user, you should see an “af\_install” event for that user.

[![](https://files.readme.io/b365a27e7638a6a87e6a5b46a67d329956f6a678b234bd1fd802acaeeceaaeb2-207207606.png)](https://files.readme.io/b365a27e7638a6a87e6a5b46a67d329956f6a678b234bd1fd802acaeeceaaeb2-207207606.png)

<div data-zendesk-anchors="h_01H9FKAF22A3FTGC7CSE5K0CY4=important h_01H9FKAF22W59PMYJRFW8HKBQ7=important-note h_01H9FKAF222ES9240V0THQQ5X0=setting-up-kahuna h_01H9FKAF227SZWFTCP9P1B7HEK=integration-tab h_01H9FKAF22EFF1F8D2QR1F38PV=activate-partner h_01H9FKAF221EXQYBJGS8GFRF4S=general-settings h_01H9FKAF22XMJW7A89MBD0J276=obtaining-the-kahuna-secret-key h_01H9FKAF2258JVR3XS6P7TT8H3=default-postbacks h_01H9FKAF22DMF1NNJRY3SJB5XX=attribution-link-tab h_01H9FKAF22KPY1ABFJN63XZ5CM=cost-tab h_01H9FKAF22KRDEFTVBR954JSJT=ad-revenue-tab h_01H9FKAF22HJPHZZM59TQ7RRFM=permissions-tab h_01H9FKAF22A5910NXRFDGC1JTG=view-user-attribution-data-in-kahuna h_01H9FKAF22KW2J6H2B6F9AMDP9=testing-with-sandbox" />
