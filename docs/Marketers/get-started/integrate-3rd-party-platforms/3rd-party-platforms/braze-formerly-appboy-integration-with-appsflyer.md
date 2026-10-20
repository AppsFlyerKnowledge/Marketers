---
title: Braze (formerly Appboy) integration with AppsFlyer
excerpt: >-
  Braze, an AppsFlyer integrated partner, offers a lifecycle engagement platform
  for marketing, growth, and engagement teams. The platform enables marketers to
  connect human-to-human, at scale, with their customers, driving deep
  engagement and ROI. The center of our platform is the holistic user profile,
  which provides a single view of the customer.
metadata:
  keywords:
    - Appboy
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
  created_at: '2017-03-30T08:39:03Z'
  edited_at: '2026-08-14T15:06:14Z'
  id: 115001603343
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115001603343-Braze-formerly-Appboy-integration-with-AppsFlyer
---
Learn more at [braze.com](https://www.braze.com/).

**Important notes**

* [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.
* Postbacks won't be sent if the source is organic.

## Integration overview

Follow the instructions below to configure the integration with Braze.

Minimum requirements - AppsFlyer SDK:

* [Android](/docs/sdk-integration-overview) (Android SDK – version 2.3.1.18 and above)
* [iOS](/docs/sdk-integration-overview)

On Android, integrating with Braze requires that the Braze [Device ID](https://www.braze.com/docs/partners/advertising_technologies/attribution/appsflyer/#integration) (Braze unique user identifier) is populated in AppsFlyer Android SDK. This parameter is sent with every postback and enables the identification of each user. To perform this you must insert the following strings to your app code:

**Important Note**

Make sure the lines of code are inserted at the correct place – after Braze SDK is launched and before the initialization code for AppsFlyer SDK (see the Initializing the SDK section in our Android SDK Integration Guide).

<Accordion title="Android">

```
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId =(Braze.getInstance(MyActivity.this).getDeviceId());
customData.put("brazeCustomerId", deviceId);
AppsFlyerLib.getInstance().setAdditionalData(customData);
```

</Accordion>

<Accordion title="iOS">

**Swift**

There are two Swift APIs, one with a completion handler and another using the new Swift concurrency support. They both produce the same value—choosing which to use depends on the context.

**Swift completion handler**

```javascript
let configuration = Braze.Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
braze.deviceId {
    brazeDeviceId in
    AppsFlyerLib.shared().customData = ["brazeDeviceId": brazeDeviceId]
}
```

**Swift await**

```javascript
let configuration = Braze.Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
let brazeDeviceId = await braze.deviceId()
AppsFlyerLib.shared().customData = ["brazeDeviceId": brazeDeviceId]
```

**Objective-C**

```
BRZConfiguration *configurations = [[BRZConfiguration alloc] initWithApiKey:@"BRAZE_API_KEY" endpoint:@"BRAZE_END_POINT"];
[configurations setUseUUIDAsDeviceId:NO];
Braze *braze = [[Braze alloc] initWithConfiguration:configurations];
[braze deviceIdWithCompletion:^(NSString * _Nonnull brazeDeviceId) {
    NSLog(@">>[BRZ]: %@", brazeDeviceId);
    [[AppsFlyerLib shared] setAdditionalData:@{
        @"brazeDeviceId": brazeDeviceId
    }];
}];
```

</Accordion>

<Accordion title="Unity">

```
Appboy.AppboyBinding.getDeviceID()
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("brazeCustomerId", Appboy.AppboyBinding.getDeviceId());
AppsFlyer.setAdditionalData(customData);
```

</Accordion>

## Setting up Braze

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.  
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations](/docs/set-up-an-integrated-partner).

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you must ***Activate the Partner*** to enable the setup of the integration tab parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### General settings

Braze connects with AppsFlyer via a unique API Key and REST Endpoint.

**To get Braze's API Key and REST endpoint:**

1. In your Braze account, under **Technology Partners,** go to **Attribution**.
2. Select **AppsFlyer**.
   ![Select AppsFlyer as the technology partner in Braze](https://files.readme.io/db96e8b5e2363f5250c6c1146a1f7a15e1ed6457fe4543dbe649f8818bb5db78-360017328637.png)
3. Under **Data Import for Install Attribution**, click Generate API Key.
4. Copy the generated API Key and the REST endpoint.
5. In AppsFlyer, insert the Braze API Key and the REST endpoint.
   ![Enter the Braze API Key and REST endpoint in AppsFlyer](https://files.readme.io/b13aba84c394c0b4603e0aad2edd723525dadf204250349620b571bc47b0ba9d-360001907229.png)
6. Click **Save and Close**

Once you have saved the configuration, AppsFlyer sends the following data to Braze for every organic and non-organic install:

* Braze Dev\_ID
* Media Source
* Campaign name
* Adgroup name
* Ad name

### Default postbacks

AppsFlyer can send automatic postbacks to Braze user installs. Use this section to define sending these postbacks.

![Default postbacks section](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Select **Events attributed to any partner or organic** to send postbacks to Braze for any user that downloads the app.

Click **Save.**

**Note**

Although all events are sent by AppsFlyer, organic installs are not counted by Braze and therefore are ignored by the Braze API.

</Accordion>

<Accordion title="Attribution link tab">

Attribution Links are not available for Braze.

</Accordion>

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<Accordion title="Permissions tab">

Permissions are not available for Braze.

</Accordion>

## Viewing user attribution data in Braze

Your user base can be segmented by attribution data in the Braze dashboard using the Install Attribution filters.

![Install Attribution filters in the Braze dashboard](https://files.readme.io/7289491d4d301eb38618298536ac5b895a610024bf162c733409d3f50b10b8f4-360001908045.png)

Additionally, attribution data for a particular user is available on each user’s profile in the Braze dashboard.

![Attribution data on a user profile in Braze](https://files.readme.io/d9ee5206a8bf3c092c5297c361cf38b2c77717fbb9638b282032e4fc4c31091e-360001907289.png)

<div data-zendesk-anchors="h_01H9FK453A9W5DCPR4X8PR06MZ=integration-overview h_01H9FK453AWXF006KEVKD797QF=setting-up-braze h_01H9FK453AVK4YKF41FEP0YRJN=activate-partner h_01H9FK453AG6AXA7J43X6NGZT1=general-settings h_01H9FK453ASAKVHT7GV8BG56YS=default-postbacks h_01H9FK453AQXG7NNT2841686MJ=viewing-user-attribution-data-in-braze" />
