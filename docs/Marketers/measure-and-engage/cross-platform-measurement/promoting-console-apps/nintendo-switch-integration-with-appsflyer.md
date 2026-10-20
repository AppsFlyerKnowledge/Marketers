---
title: Nintendo Switch integration with AppsFlyer
excerpt: >-
  Integrate your Nintendo Switch game or app with AppsFlyer to receive
  attribution and event data for your Nintendo Switch campaigns.
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-05-02T10:50:43Z'
  edited_at: '2024-02-08T00:01:01Z'
  id: 14988397864593
  locale: en-us
  section: Promoting Console apps
  section_id: 15329052471057
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/14988397864593-Nintendo-Switch-integration-with-AppsFlyer
---
## About Nintendo Switch attribution

Apps running on Nintendo Switch can integrate with AppsFlyer via S2S API to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

### Example attribution flow

The following is an example flow that highlights the most important steps in a user journey from ad engagement to attribution. It includes the AppsFlyer-recommended cross-platform landing page. **Note**: While we recommend using the cross-platform landing page, you can also use direct attribution links

![User_windows.jpg](https://files.readme.io/ce8489a16998ffbc4720fe2aae4496393db921cc582a331f59edb775a59b1331-small-22325350590097.jpg)

1. <span id="marketing-touchpoint"></span>Marketing touchpoint: Customers interact with your brand through online or offline marketing touchpoints. These can include, email and newsletters, social media, mobile web, and more.
2. Game landing page: A game landing page directs customers to your download app page. This step is important for collecting UTM and other URL parameters to attribute customers from the click/install to the original media sources or to your owned media sources.  
   The landing page is also useful because it provides links to the various platforms your game supports. For example, you can also have links to your Xbox, Microsoft store, and Steam page on your landing page.
3. App page: This is the URL to your Nintendo Switch app page that hosts your app for customers to download.
4. Game install: The user installs the game, triggering attribution and the recording of in-app events and sessions.

## Integration procedures

The following table lists the tasks required to integrate your Nintendo Switch app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | <ul><li>[Create an AppsFlyer account](https://www.appsflyer.com/get-started/)</li><li>[Add account users with appropriate permissions](/docs/user-management)</li><li>[Add your Nintendo Switch app in AppsFlyer](/docs/adding-an-app-to-appsflyer)</li></ul> | Marketer |
| API integration with your app (via S2S) | [Integrate the AppsFlyer API](https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview) into your app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**Note**:<ul><li>First app opens must be reported before in-app events and sessions.</li><li>For the `device_ids` parameter, select the type `custom`.<ul><li>The `custom` generated ID for [first opens](https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id) should match your [in-app events](https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id), and [sessions](https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id) ID.</li><li>Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.</li></ul></li></ul>To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id) | App developer |
| Cross-platform landing page setup | **Recommended**: A cross-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Native PC.<br /><br />[Learn about cross-platform landing pages](/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page)<br /><br />[Learn how to set up a cross-platform landing page](/docs/cross-platform-landing-pages-with-smart-script)<br /><br />**Note**:<br /><br />For Nintendo Switch, the following parameters are required:<ul><li>**platform**<br />switch</li><li>**nintendo\_app\_id**<br />The ID of the app page.</li></ul>You can find your unique app ID by copying it from the URL bar or by going to [https://www.nintendo.com/store/products/](https://www.nintendo.com/store/products/octopath-traveler-ii-switch/) and searching for your game. For example,<br /><br />```<br />https://www.nintendo.com/store/products/app-id-switch/<br />```<br /><br />where **app-id** is your unique app ID.<ul><li>**media\_source**</li></ul>The following parameters are not required but recommended:<ul><li>**campaign**</li><li>**ad**</li><li>**ad\_set**</li><li>**storefront\_redirect\_url**<br />The full URL of your Nintendo Switch storefront for your app including your **nintendo\_app\_id**.<br />For example,</li></ul>```<br />https://www.nintendo.com/store/products/app-id-switch/<br />``` | Marketer (may require developer assistance) |
| Link setup | If you don't use a cross-platform landing page, you can create direct attribution links to place behind ads.<br /><br />[Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability) | Marketer/Data engineer |

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via [Ad Spend Ingestion](/docs/import-cost-data) using the upload file by email method. |

</Accordion>

> 📘 **See also**
>
> * [CTV, PC, and console platform overview](/docs/ctv-pc-and-console-platform-attribution-concepts)

<div data-zendesk-anchors="01H7Z1HPD0AB0VP6REMBF2HCR8=about-nintendo-switch-attribution h_01HP1QDGDAXV0Y7MVJYHW3H4SQ=example-attribution-flow 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint 01H7Z1HPD0VAMPEHBPN8MAT3ST=integration-procedures 01H7Z1HPD0CS7CTX2KS2RVD3VA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=see-also" />
