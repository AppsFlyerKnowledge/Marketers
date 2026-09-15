---
title: "Samsung integration with AppsFlyer"
excerpt: "Integrate your Samsung Connected TV (CTV) app with AppsFlyer to receive attribution and event data for your campaigns on Samsung."
---
## About Samsung CTV attribution

The Samsung Tizen OS for streaming runs across all Samsung TVs.

CTV apps streaming on Samsung can integrate with AppsFlyer via API to receive attribution data and performance measurements about which sources (organic and non-organic) and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The Samsung API integration supports:

- Samsung Smart TVs.
- CTV-to-CTV attribution and event recording. Meaning, attribution and recording on a user's Samsung device.

### Samsung attribution flow

<Image src="https://files.readme.io/f2ee9731dd95156a59ab49ac7a607b25e9cecc4f608301d4dafb2b2a718ebb9d-7215151128209.png" alt="CTV attribution flow - Samsung" />

## Integration procedures

The following table lists the tasks required to integrate your Samsung CTV app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | - [Create an AppsFlyer account](https://www.appsflyer.com/get-started/)<br />- [Add account users with appropriate permissions](/docs/user-management)<br />- [Add your Samsung CTV app in AppsFlyer](/docs/adding-an-app-to-appsflyer) | Marketer |
| API integration with your app (via S2S or SDK) | There are two methods of integration you can use: S2S and SDK.<br />For the S2S method, [integrate the AppsFlyer API](https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview) into your app with commands to report the following events to AppsFlyer.<br />- First opens<br />- In-app events<br />- Sessions<br />**Note**:<br />- Installs must be reported before in-app events and sessions.<br />- Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer. <br />To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id)<br />For the SDK method, see the developer hub for [Samsung documentation](https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk). | App developer |
| Partner integration | Add Samsung as an ad network (integrated partner) in AppsFlyer.<br />1. [Activate partner](/docs/set-up-an-integrated-partner#a-activate-partner)<br />2. [Optional] Turn on [**View-through attribution**](/docs/set-up-an-integrated-partner#e-install-attribution) **.** | Marketer |
| Link setup | [Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability) | Marketer/Data engineer |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via [Cost Import](/docs/import-cost-data) using the upload file by email method. |
| Supported regions | CTV campaigns are supported only in the US, except for preload campaigns, which are supported globally. |

<Cards>
  <Card title="CTV, PC, and console platform overview" href="/docs/ctv-pc-and-console-platform-attribution-concepts">
    Read the platform overview for Connected TV, PC, and console attribution.
  </Card>
</Cards>