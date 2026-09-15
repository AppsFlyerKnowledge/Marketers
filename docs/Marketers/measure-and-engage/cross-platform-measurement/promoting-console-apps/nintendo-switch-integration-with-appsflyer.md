---
title: "Nintendo Switch integration with AppsFlyer"
excerpt: "Integrate your Nintendo Switch game or app with AppsFlyer to receive attribution and event data for your Nintendo Switch campaigns."
---
## About Nintendo Switch attribution

Apps running on Nintendo Switch can integrate with AppsFlyer via S2S API to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

### Example attribution flow

The following is an example flow that highlights the most important steps in a user journey from ad engagement to attribution. It includes the AppsFlyer-recommended cross-platform landing page. 

> 📘 Note
>
> While we recommend using the cross-platform landing page, you can also use direct attribution links

![User_windows.jpg](https://files.readme.io/ce8489a16998ffbc4720fe2aae4496393db921cc582a331f59edb775a59b1331-small-22325350590097.jpg)

1. Marketing touchpoint: Customers interact with your brand through online or offline marketing touchpoints. These can include, email and newsletters, social media, mobile web, and more.
2. Game landing page: A game landing page directs customers to your download app page. This step is important for collecting UTM and other URL parameters to attribute customers from the click/install to the original media sources or to your owned media sources.

The landing page is also useful because it provides links to the various platforms your game supports. For example, you can also have links to your Xbox, Microsoft store, and Steam page on your landing page.
3. App page: This is the URL to your Nintendo Switch app page that hosts your app for customers to download.
4. Game install: The user installs the game, triggering attribution and the recording of in-app events and sessions.

## Integration procedures

The following table lists the tasks required to integrate your Nintendo Switch app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | - [Create an AppsFlyer account](https://www.appsflyer.com/get-started/)<br>- [Add account users with appropriate permissions](https://support.appsflyer.com/hc/articles/4409128270481--Beta-User-management)<br>- [Add your Nintendo Switch app in AppsFlyer](https://support.appsflyer.com/hc/articles/207377436) | Marketer |
| API integration with your app (via S2S) | [Integrate the AppsFlyer API](https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview) into your app with commands to report the following events to AppsFlyer.<br>- First opens<br>- In-app events<br>- Sessions<br>**Note**: <br>- First app opens must be reported before in-app events and sessions.<br>- For the `device_ids` parameter, select the type `custom`.<br>  <br>  - The `custom` generated ID for [first opens](https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id) should match your [in-app events](https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id), and [sessions](https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id) ID.<br>  - Send events using the API. Tell your developer which events to send.Verify that when you set up the API, you set up and map the events to send to AppsFlyer.<br>To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id) | App developer |
| Cross-platform landing page setup | **Recommended**: Across-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Native PC.<br>[Learn about cross-platform landing pages](https://support.appsflyer.com/hc/articles/4404083608849-Connected-TV-CTV-PC-and-console-platform-attribution-overview#landing-page)<br>[Learn how to set up a cross-platform landing page](https://support.appsflyer.com/hc/articles/18440789126289)<br>**Note**: <br>For Nintendo Switch, the following parameters are required:<br>- **platform**<br>  <br>  switch<br>- **nintendo_app_id**<br>  <br>  The ID of the app page.<br>  <br>  <br>  You can find your unique app ID by copying it from the URL bar or by going to [https://www.nintendo.com/store/products/](https://www.nintendo.com/store/products/octopath-traveler-ii-switch/) and searching for your game. For example,<br>  <br>  <br>  ```http<br>  HTTPhttps://www.nintendo.com/store/products/app-id-switch/<br>  ```<br>  <br>  <br>  where **app-id** is your unique app ID.<br>  <br>- **media_source**<br>The following parameters are not required but recommended:<br>- **campaign**<br>- **ad**<br>- **ad_set**<br>- **storefront_redirect_url**<br>  <br>  The full URL of your Nintendo Switch storefront for your app including your **nintendo_app_id**.<br>  <br>  For example,<br>  <br>  <br>  ```http<br>  HTTPhttps://www.nintendo.com/store/products/app-id-switch/<br>  ``` | Marketer (may require developer assistance) |
| Link setup | If you don't use a cross-platform landing page, you can create direct attribution links to place behind ads.<br>[Learn how to create direct attribution links](https://support.appsflyer.com/hc/articles/15199908310801) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](https://support.appsflyer.com/hc/articles/4404083608849#data-availability) | Marketer/Data engineer |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via [Ad Spend Ingestion](https://support.appsflyer.com/hc/articles/360002516838) using the upload file by email method. |

<Cards>
  <Card title="CTV, PC, and console platform overview" href="https://support.appsflyer.com/hc/articles/4404083608849">
    Learn more about Connected TV, PC, and console platform attribution overview.
  </Card>
</Cards>