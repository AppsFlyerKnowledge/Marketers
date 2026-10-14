---
title: Epic integration with AppsFlyer
excerpt: >-
  Integrate your Epic game with AppsFlyer to receive attribution and event data
  for your Epic campaigns. The Epic integration supports attribution and in-app
  event recording for Epic games (in other words, attribution and recording on a
  user's device).
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2023-04-03T07:18:07Z'
  edited_at: '2026-05-19T08:10:01Z'
  id: 14241298075921
  locale: en-us
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/14241298075921-Epic-integration-with-AppsFlyer
---
## About Epic game attribution

Games running on Epic can integrate with AppsFlyer via API (both S2S and client-side) to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

### Example attribution flow

The following is an example flow that highlights the most important steps in a user journey from ad engagement to attribution. It includes the AppsFlyer-recommended cross-platform landing page. **Note**: While we recommend using the cross-platform landing page, you can also use direct attribution links.

![Epic_journey.jpg](https://files.readme.io/c5807442cff142ceb4aa3c4d55628e75b37627a011ca531fa390e46ccc3e23b8-small-14241275857553.jpg)

1. Marketing touchpoint: Customers interact with your brand through online or offline marketing touchpoints. These can include, email and newsletters, social media, mobile web, and more.
2. Game landing page:  A game landing page directs customers to your Epic game page. This step is important for collecting UTM and other URL parameters to attribute customers from the click/install to the original media sources or to your owned media sources.  
   The landing page is also useful because it provides links to the various platforms your game supports. For example, you can also have links to your Xbox, Microsoft store, and Steam page on your landing page.
3. Epic app page: This is your Epic storefront page that hosts your Epic game for customers to download.
4. Game install: The user installs the game, triggering attribution and the recording of in-app events and sessions.

## Integration procedures

The following table lists the tasks required to integrate your Epic game with AppsFlyer.∑

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | <ul><li>[Create an AppsFlyer account](https://www.appsflyer.com/get-started/)</li><li>[Add account users with appropriate permissions](/docs/user-management)</li><li>[Add your Epic game in AppsFlyer](/docs/adding-an-app-to-appsflyer)</li></ul> | Marketer |
| API integration with your app (via S2S or client-side) | There are two methods of integration you can use: S2S and client-side.<br /><br />For the S2S method:<br /><br />[Integrate the AppsFlyer Epic API](https://github.com/AppsFlyerSDK/appsflyer-epic-sample) into your app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**Note**:<ul><li>First app opens must be reported before in-app events and sessions.</li><li>For the `device_ids` parameter, select the type `custom` or `epicid`.<ul><li>The `custom` or `epicid` for [first opens](https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id) should match your [in-app events](https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id), and [sessions](https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id) ID.</li></ul></li><li>Send events using the API. Tell your developer which events to send.</li><li>To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id)</li></ul>For the client-side method, there are three versions: native [C++](https://github.com/AppsFlyerSDK/appsflyer-epic-sample), [Unreal](https://github.com/AppsFlyerSDK/appsflyer-unreal-epic-sample-app), and [Unity](https://github.com/AppsFlyerSDK/appsflyer-unity-epic-sample-app).<br /><br />**Note**:<br /><br />If you have an existing user base and therefore want the first session to be considered a session and not an install, the developer can use the method `skipFirst=true`. | App developer |
| Cross-platform landing page setup | **Recommended**: A cross-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Steam.<br /><br />[Learn about cross-platform landing pages](/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page)<br /><br />[Learn how to set up a cross-platform landing page](/docs/cross-platform-landing-pages-with-smart-script)<br /><br />**Note**:<br /><br />For Epic, the following parameters are required:<ul><li>**platform**<br />epic</li><li>**app\_id**<br />The app ID of the game page on the Epic store.</li></ul>You can find your unique game ID on your Epic developer console. For example,<br /><br />```<br />https://store.epicgames.com/en-us/p/YOUR-GAME-ID<br />```<ul><li>**media\_source**</li></ul>The following parameters are not required but recommended:<ul><li>**campaign**</li><li>**ad**</li><li>**ad\_set**</li><li>**storefront\_redirect\_url**<br />The full URL of your Epic storefront for your app including your **app\_id**.<br />For example, `https://store.epicgames.com/en-us/p/12345678/`</li></ul> | Marketer (may require developer assistance) |
| Link setup | If you don't use a cross-platform landing page, you can create direct attribution links to place behind ads.<br /><br />[Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability) | Mareketer/Data engineer |

### Removing AppsFlyer data when uninstalling the app

To remove all AppsFlyer SDK data when uninstalling the app, please ask your developer to perform the steps specified [here](https://dev.appsflyer.com/hc/docs/epic-vanilla#deleting-appsflyer-data-on-uninstall).

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via [Ad Spend Ingestion](/docs/import-cost-data) using the upload file by email method. |

> 📘 **See also**
>
> * [CTV, PC, and console platform overview](/docs/ctv-pc-and-console-platform-attribution-concepts)

<div data-zendesk-anchors="about-steam-attribution=about-epic-game-attribution 01H7Z1F3SE03BXJD0WAJV8RE7Q=about-epic-game-attribution flow=example-attribution-flow 01H7Z1F3SETVXQKRQ71YAJACY3=example-attribution-flow 01H7Z1F3SF4J2WJ2Y6QG3VGGVK=integration-procedures h_01J3349MAA4J231B6FJ74V3PTB=removing-appsflyer-data-when-uninstalling-the-app h_01HF9WA5FJ6P4C357ZE231GMR0=traits-and-limitations h_01HE7T4JX3RX3SZW2VPW5ZZY7E=see-also" />
