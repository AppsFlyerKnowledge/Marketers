---
title: "PlayStation integration with AppsFlyer"
excerpt: "Integrate your PlayStation app with AppsFlyer via S2S API to receive attribution and event data for your campaigns."
---
At a glance: Integrate your PlayStation app with AppsFlyer to receive attribution and event data for your campaigns on PlayStation.

## About PlayStation attribution

The PlayStation OS for console and CTV (Connected TV) apps runs across all PlayStation devices.

Apps running on PlayStation can integrate with AppsFlyer via S2S (server-to-server) API to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

The PlayStation API integration supports:

- PlayStations.
- Attribution and event recording for PlayStation apps, which means attribution and recording on a user's PlayStation device.

### Example attribution flow

The following is an example flow that highlights the most important steps in a user journey from ad engagement to attribution. It includes the AppsFlyer-recommended cross-platform landing page. 

> 📘 Note
>
> While we recommend using the cross-platform landing page, you can also use direct attribution links.

![User_windows.jpg](https://files.readme.io/eaa57bd6977d5eae5dff2d135bc80e847040103eacb00dff6add79e02b450763-small-49667524948369.jpg)

1. Marketing touchpoints: Customers interact with your brand through online or offline channels. These can include email and newsletters, social media, mobile web, and more.
2. Game landing page: A game landing page directs customers to your download app page. This step is important for collecting UTM (Urchin Tracking Module) and other URL parameters to attribute customers from the click/install to the original media sources or to your owned media sources.

The landing page is also useful because it provides links to the various platforms your game supports. For example, you can also have links to your Xbox, Microsoft Store, and Steam page on your landing page.
3. App page: This is the URL to your PlayStation app page that hosts your app for customers to download.
4. Game install: The user installs the game, triggering attribution and the recording of in-app events and sessions.

## Integration procedures

The following table lists the tasks required to integrate your PlayStation app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | - [Create an AppsFlyer account](https://www.appsflyer.com/get-started/)<br />- [Add account users with appropriate permissions](/docs/user-management)<br />- [Add your PlayStation app to AppsFlyer](/docs/adding-an-app-to-appsflyer) | Marketer |
| API integration with your app (via S2S) | [Integrate the AppsFlyer API](https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview) into your app with commands to report the following events to AppsFlyer.<br />- First opens<br />- In-app events<br />- Sessions<br />**Note**:<br />- The first app open event must be reported before in-app events and sessions.<br />- For the `device_ids` parameter, select the type `custom`.<br />  - The `custom` generated ID for [first opens](https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id) must match the ID you use for [in-app events](https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id) and [sessions](https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id).<br />- Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer. <br />- The `psid` device ID type is intended for use as an advertising ID. At the moment, PlayStation does not support advertising ID matching, so there is no need to use this device ID type.<br />- We recommend sharing the `psn_uid`, which is the PlayStation account ID in the `customer_user_id` field. Make sure to anonymize the value before sharing it.<br />To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id) | App developer |
| Cross-platform landing page setup | **Recommended**: A cross-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's recommended when your campaign promotes an app that's also available on other platforms, like Epic and Native PC.<br />[Learn about cross-platform landing pages](/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page)<br />[Learn how to set up a cross-platform landing page](/docs/cross-platform-landing-pages-with-smart-script)<br />**Note**:<br />For PlayStation, the following parameters are required:<br />- **platform**: playstation<br />- **app_id**: The ID of the app<br />- **media_source**<br />The following parameters are not required but recommended:<br />- **campaign**<br />- **ad**<br />- **ad_set** | Marketer (may require developer assistance) |
| Link setup | If you don't use a cross-platform landing page, you can create direct attribution links to place behind ads.<br />[Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability) | Marketer/Data engineer |

## Traits and limitations

| Trait | Description |
| --- | --- |
| Cost data | Cost data must be sent via [Ad Spend Ingestion](/docs/import-cost-data) using the upload file by email method. |

<Cards>
  <Card title="CTV, PC, and console platform overview" href="/docs/ctv-pc-and-console-platform-attribution-concepts">
    Learn more about attribution for Connected TV, PC, and console platforms.
  </Card>
</Cards>