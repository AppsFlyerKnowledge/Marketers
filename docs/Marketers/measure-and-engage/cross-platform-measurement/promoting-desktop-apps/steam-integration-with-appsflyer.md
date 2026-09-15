---
title: "Steam integration with AppsFlyer"
excerpt: "Integrate your Steam game or app with AppsFlyer to receive attribution and event data for your Steam campaigns."
---
At a glance: Integrate your Steam game/app with AppsFlyer to receive attribution and event data for your Steam campaigns. The Steam integration supports attribution and in-app event recording for Steam apps on a user's Steam device.

## About Steam attribution

Steam runs across Windows and Mac devices, Steam Deck, and other Steam OS devices.

Apps running on Steam can integrate with AppsFlyer via S2S API or SDK to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

### Example attribution flow

The following is an example flow that highlights the most important steps in a user journey from ad engagement to attribution. It includes the AppsFlyer-recommended cross-platform landing page.

> 📘 Note
>
> While we recommend using the cross-platform landing page, you can also use direct attribution links

![Steam_user_journey.jpg](https://files.readme.io/b3c8594be74db3349924e48627f2c6745870205ffb902a63c2c0ba70e8424ccc-small-13212274650769.jpg)

1. Marketing touchpoint: Customers interact with your brand through online or offline marketing touchpoints. These can include, email and newsletters, social media, mobile web, and more.
2. Game landing page: A game landing page directs customers to your Steam game page. This step is important for collecting UTM and other URL parameters to attribute customers from the click/install to the original media sources or to your owned media sources.

The landing page is also useful because it provides links to the various platforms your game supports. For example, you can have links to your Xbox, Microsoft store, and Steam page on your landing page.

![awesome_game.png](https://files.readme.io/1d0735c60a5a03f1763dc50a0dbf33fda4c2298a7c076ed1bff1d3a380e9a6cd-13212305462289.png)
3. Steam app page: This is your Steam storefront page that hosts your Steam app for customers to download.
4. Game install: The user installs the game, triggering attribution and the recording of in-app events and sessions.

## Integration procedures

The following table lists the tasks required to integrate your Steam app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | - [Create an AppsFlyer account](https://www.appsflyer.com/get-started/)<br />- [Add account users with appropriate permissions](/docs/user-management)<br />- [Add your Steam app to AppsFlyer](/docs/adding-an-app-to-appsflyer) | Marketer |
| SDK integration with your app (via S2S or SDK) | There are two methods of integration you can use: S2S and SDK.<br />For the S2S method, [integrate the AppsFlyer API](https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview) into your app with commands to report the following events to AppsFlyer.<br />- First opens<br />- In-app events<br />- Sessions<br />**Note**: <br />- First app opens must be reported before in-app events and sessions.<br />- For the `platform` parameter, select `steam`.<br />- For the `device_ids` parameter, select the type `custom` or `steamid`.<br />  <br />  - The `custom` or `steamid` for [first opens](https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id) should match your [in-app events](https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id), and [sessions](https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id) ID.<br />- Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer. <br />- To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id)<br />For the SDK method, there are three versions: native [C++](https://dev.appsflyer.com/hc/docs/steam-vanilla), [Unreal](https://dev.appsflyer.com/hc/docs/unreal-steam), and [Unity](https://dev.appsflyer.com/hc/docs/unity-steam).<br />**Note**:<br />If you have an existing user base and therefore want the first session to be considered a session and not an install, the developer can use the method `skipFirst=true`. | App developer |
| Cross-platform landing page setup | **Recommended**: Across-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Native PC.<br />[Learn about cross-platform landing pages](/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page)<br />[Learn how to set up a cross-platform landing page](/docs/cross-platform-landing-pages-with-smart-script)<br />**Note**: <br />For Steam, the following parameters are required:<br />- **platform**: steam<br />- **steam_app_id**: The ID of the app page.<br />  <br />  <br />  You can find your unique app ID by copying it from the URL bar or by going to [https://steamdb.info/](https://steamdb.info/) and searching for your game. For example,<br />  <br />  <br />  ```http
  HTTPhttps://store.steampowered.com/app/12345678/
  ```<br />  <br />  <br />  where **12345678** is your unique app ID.<br />  <br />- **media_source**<br />The following parameters are not required but recommended:<br />- **campaign**<br />- **ad**<br />- **ad_set**<br />- **storefront_redirect_url**: The full URL of the Steam storefront for your app including your **steam_app_id**. For example, `https://store.steampowered.com/app/12345678/` | Marketer (may require developer assistance) |
| Link setup | If you don't use a cross-platform landing page, you can create direct attribution links to place behind ads.<br />[Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability) | Marketer/Data engineer |

### Removing AppsFlyer data when uninstalling the app

To remove all AppsFlyer SDK data when uninstalling the app, please ask your developer to perform the steps specified [here](https://dev.appsflyer.com/hc/docs/steam-vanilla#deleting-appsflyer-data-on-uninstall).

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via [Ad Spend Ingestion](/docs/import-cost-data) using the upload file by email method. |

<Cards>
  <Card title="CTV, PC, and console platform attribution" href="/docs/ctv-pc-and-console-platform-attribution-concepts" icon="fa-solid fa-diagram-project">
    Learn more about Connected TV, PC, and console platform attribution with AppsFlyer.
  </Card>
</Cards>