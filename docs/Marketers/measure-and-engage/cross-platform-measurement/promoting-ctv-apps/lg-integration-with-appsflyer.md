---
title: "LG integration with AppsFlyer"
excerpt: "Integrate your LG Connected TV (CTV) app with AppsFlyer to receive attribution and event data for your campaigns on LG."
---
## About LG CTV attribution

The LG Webos OS for streaming runs across all LG TVs.

CTV apps streaming on LG can integrate with AppsFlyer via API to receive attribution data and performance measurements about which sources (organic and non-organic) and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The LG API integration supports:

- LG Smart TVs.
- CTV-to-CTV attribution and event recording. Meaning, attribution and recording on a user's LG device.

## Integration procedures

The following table lists the tasks required to integrate your LG CTV app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | - [Create an AppsFlyer account](https://www.appsflyer.com/get-started/)<br>- [Add account users with appropriate permissions](https://support.appsflyer.com/hc/articles/4409128270481--Beta-User-management)<br>- [Add your LG CTV app in AppsFlyer](https://support.appsflyer.com/hc/articles/207377436) | Marketer |
| API integration with your app (via S2S or SDK) | There are two methods of integration you can use: S2S and SDK.<br>For the S2S method, [integrate the AppsFlyer API](https://dev.appsflyer.com/hc/reference/overview-4) into your app with commands to report the following events to AppsFlyer.<br>- First opens<br>- In-app events<br>- Sessions<br>**Note**:<br>- Installs must be reported before in-app events and sessions.<br>- Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer. <br>To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id)<br>For the SDK method, see the developer hub for [LG documentation](https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk). | App developer |
| Partner integration | Add LG Ads as an ad network (integrated partner) in AppsFlyer.<br>1. [Activate partner](https://support.appsflyer.com/hc/articles/4410395957521#a-activate-partner)<br>2. [Optional] Turn on [**View-through attribution**](/docs/set-up-an-integrated-partner#e-install-attribution) **.** | Marketer |
| Link setup | [Learn how to create direct attribution links](https://support.appsflyer.com/hc/articles/15199908310801) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](https://support.appsflyer.com/hc/articles/4404083608849#data-availability) | Mareketer/Data engineer |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via [Cost Import](https://support.appsflyer.com/hc/articles/360002516838) using the upload file by email method. |
| Attribution | LG Ads uses probabilistic modeling for attribution; ID matching isn't currently available. |
| Customer ID | Populate this parameter with the LG customer ID (`cust_id`) obtained from LG Ads. |
| Deterministic attribution | There is an option to enable deterministic ad ID matching for attribution. To do so, the following requirements must be met:<br>- LG must conduct a legal review before content partner apps can be enabled to surface the AD ID.<br>- This legal review involves the content partner working directly with LG Electronics and requires both parties to sign a legal agreement.<br>- Content partner apps must integrate the functionality to collect and transmit the LG AD ID, and release a user-initiated app update to begin surfacing the AD ID to AppsFlyer.<br>- For more information, contact your AppsFlyer CSM and [partnerships@lgads.tv](mailto:partnerships@lgads.tv) |

<Cards>
  <Card title="CTV, PC, and console platform overview" href="https://support.appsflyer.com/hc/articles/4404083608849">
    Learn more about the overview of CTV, PC, and console platforms.
  </Card>
</Cards>