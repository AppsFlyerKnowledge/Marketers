---
title: "CTV-to-mobile app view-through attribution for ad networks"
excerpt: "Learn how to attribute mobile app installs to ads viewed on Connected TV (CTV) devices using AppsFlyer cross-platform impression URLs."
---
With AppsFlyer cross-platform impression URLs, you can attribute mobile app installs to ads displayed on CTV. Multiple installs within the same household can be attributed to the same CTV ad impression.

![Diagram of the CTV-to-mobile app attribution flow](https://files.readme.io/401bcb083e1cc618794cb302668f7271cf825a5a6045ff10055e0164baf423a1-19774176963473.jpg)

CTV-to-mobile app view-through attribution uses a [OneLink impression URL](/docs/set-up-cross-platform-links-for-multi-device-campaigns#setup) based on a cross-platform OneLink template (with a template ID) created by the advertisers. This lets advertisers group multiple apps from different platforms (for example, both Android and iOS apps) using a single URL.

When users view the ad on CTV, you send AppsFlyer the impression URL in real time.

Example URL:

```auto
https://impressions.onelink.me/{template_id}?pid=__media_source__&af_xplatform=true&af_xplatform_vt_lookback=24h&af_siteid=__CSITE__&c=__CAMPAIGN_NAME__&af_channel=__PLACEMENT__&af_c_id=__CAMPAIGN_ID__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_source_platform=__source_platform__&af_source_device_category=__device_category__&af_ad_type=__CTYPE__&af_ip=__IP__&af_ua=__UA__&redirect=false
```

AppsFlyer sends postbacks to you after each conversion.

> 📘 Partner availability
>
> This feature is available only for designated partners. Contact your Partner Development Manager (PDM) if you’re interested.

### Set up CTV-to-mobile attribution

**To set up CTV-to-mobile app view-through attribution with an advertiser**:

1. Make sure you're an [AppsFlyer integrated partner](/docs/getting-started-onboarding-guide-for-ad-networks), that you have postbacks properly set up, and that you've [tested your CTV-to-mobile app integration](/docs/ctv-to-mobile-app-view-through-attribution-for-ad-networks#test-partner-integration) with AppsFlyer.
2. Make sure the URL has the [mandatory parameters](/docs/ctv-to-mobile-app-view-through-attribution-for-ad-networks#parameters), as well as any other parameters you want.
3. Send AppsFlyer the user IP address and user agent. These are required for CTV-to-mobile app view-through attribution. They can be sent either:
   1. As the `af_ip` and `af_ua` parameters on the impression URL.
   2. As `<X-Forwarded-For>` and `<User-Agent>` parameters in the headers of the request.

### Test partner integration

**To test CTV-to-mobile app view-through attribution**:

1. Use the following test apps: `com.appsflyer.android.deviceid` and `id1192323960`
2. Contact the AppsFlyer Partner Solutions Team to receive a test URL. To do so, log in to your [partner dashboard](https://hq1.appsflyer.com/auth/login), and from the top menu, click **Help** > **Contact our team**.
   * Sample URL: `https://impressions.onelink.me/dfHa?pid=partner_int&c=test_1&af_xplatform=true&af_xplatform_vt_lookback=24h&af_ip=MACRO&af_ua=MACRO&redirect=false`
3. Confirm that your partner ID in the `pid` parameter is correct.
4. Enter your IP address for the `af_ip` parameter.
5. Enter your user agent for the `af_ua` parameter.
6. Enter the URL into a desktop browser.
7. On your mobile device, go to the app store, and download, install, and launch the app.
8. A new install appears in AppsFlyer, along with a corresponding postback. If you don’t see the install or get the postback, contact the Partner Solutions Team.

### Parameters

The following parameters are used to provide attribution data and measurement to advertisers.

| Parameter | Mandatory | Description |
| --- | --- | --- |
| `template_id` | **✓** | The ID of the [OneLink template](/docs/create-a-onelink-template). The template contains basic prediction settings for the advertiser apps and is the basis for creating other links. Note: Never encode the `template_id` value. |
| `pid` | **✓** | The partner identifier, allocated by AppsFlyer to the media source (ad network) placing the ad. |
| `af_xplatform` | **✓** | - Set by the advertiser to indicate whether the link supports cross-platform attribution.<br />- Values: true/false |
| `af_xplatform_vt_lookback` | **-** | Configurable window that indicates the number of hours following the impression during which the app install can be attributed to the impression. Available parameter values: 1h - 72h (hours). The default is 24h. |
| `af_ip` | **✓** | - The IP address of the CTV device that displays the ad.<br />- If the IP address isn't sent in the URL, it must be sent in the headers of the request so AppsFlyer can perform CTV-to-mobile app attribution. |
| `af_ua` | **✓** | - The user agent of the CTV device that displays the ad.<br />- If the user agent isn't sent in the URL, it must be sent in the headers of the request so AppsFlyer can perform CTV-to-mobile app attribution. |
| `af_source_platform` | - | - A set list of values to represent the operating system where the impression occurs.<br />- Values:<br />  - android<br />  - ios<br />  - tizen<br />  - webos<br />  - smartcast<br />  - roku<br />  - windowsphone<br />  - vidaa<br />  - PlayStation<br />  - website |
| `af_source_device_category` | - | - A set list of values to represent the device type where the impression occurs.<br />  - tv<br />  - mobile_phone<br />  - desktop<br />  - tablet<br />  - set_top_box<br />  - games_console<br />  - unknown_device_category<br />  - media_player |

Other parameters that can be added to the URL can be found in the [attribution link structure and parameters article](/docs/about-link-structure-and-parameters).

### Traits and limitations

| Trait | Description |
| --- | --- |
| Attribution window | Between 1-72 hours, depending on the lookback window parameter `af_xplatform_vt_lookback`. |
| Retargeting | - Re-attribution: Supported for cross-platform-to-mobile. Not for other platforms.<br />- Re-engagement: Not supported |
| Attribution method | View-through attribution using probabilistic modeling (IP address) |
| Household attribution | Supported. Meaning multiple installs within the same household can be attributed to the same CTV ad impression. |
| Test partner integration | Not available for ad networks that have been flagged for high rates of mobile app-to-mobile app fraud or are affiliated with different flagged media sources. |