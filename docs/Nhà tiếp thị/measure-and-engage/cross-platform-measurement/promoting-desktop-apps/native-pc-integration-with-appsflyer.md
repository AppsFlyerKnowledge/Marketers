---
title: Native PC integration with AppsFlyer
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
  created_at: '2023-06-20T05:52:13Z'
  edited_at: '2026-10-05T06:59:57Z'
  id: 16308237781649
  locale: en-us
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/16308237781649-Native-PC-integration-with-AppsFlyer
---
> **At a glance:** Integrate your PC game or app with AppsFlyer to receive attribution and event data for your PC campaigns. The Native PC integration supports attribution and in-app event recording for PC apps (in other words, attribution and recording on a user's PC).

## About Native PC attribution

Native PC runs across Windows devices, through the installation of an .EXE or .MSI file extension.

This is different than the <Anchor target="_blank" href="/marketers/vi/docs/windows-sdk-integration-for-developers">AppsFlyer Windows SDK 2.4.1</Anchor> which works with installs from the Microsoft App Store, Windows phones, and UWP.

Apps running on PC can integrate with AppsFlyer via S2S API or SDK to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

### Example attribution flow

The following is an example flow that highlights the most important steps in a user journey from ad engagement to attribution. It includes the AppsFlyer-recommended cross-platform landing page. **Note**: While we recommend using the cross-platform landing page, you can also use direct attribution links

![User_windows.jpg](https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg)

1. <span id="marketing-touchpoint"></span>Marketing touchpoint: Customers interact with your brand through online or offline marketing touchpoints. These can include, email and newsletters, social media, mobile web, and more.
2. Game landing page: A game landing page directs customers to your download app page. This step is important for collecting UTM and other URL parameters to attribute customers from the click/install to the original media sources or to your owned media sources.  
   The landing page is also useful because it provides links to the various platforms your game supports. For example, you can also have links to your Xbox, Microsoft store, and Steam page on your landing page.
3. App page: This is the URL to your Native PC app page that hosts your app for customers to download.
4. Game install: The user installs the game, triggering attribution and the recording of in-app events and sessions.

## Integration procedures

The following table lists the tasks required to integrate your PC app with AppsFlyer.

**Note:** Adding team members and setting up reports in Data Locker are not mandatory.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Create an AppsFlyer account</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/user-management">Add account users with appropriate permissions</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">Add your PC app in AppsFlyer</Anchor></li></ul> | Marketer |
| SDK integration with your app (via S2S or SDK) | There are two methods of integration you can use: S2S and SDK.<br /><br />For the S2S method, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">integrate the AppsFlyer API</Anchor> into your app with commands to report the following events to AppsFlyer.<ul><li>First opens</li><li>In-app events</li><li>Sessions</li></ul>**Note**:<ul><li>First app opens must be reported before in-app events and sessions.</li><li>For the `device_ids` parameter, select the type `custom`.<ul><li>The `custom` generated ID for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">first opens</Anchor> should match your <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">in-app events</Anchor>, and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sessions</Anchor> ID.</li></ul></li><li>Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.</li><li>To report owned media engagements, integrate the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor></li></ul>For the SDK method, there are three versions: native <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/nativepc-vanilla">C++</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-nativepc">Unreal</Anchor>, and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-nativepc">Unity</Anchor>.<br /><br />**Note**:<br /><br />If you have an existing user base and therefore want the first session to be considered a session and not an install, the developer can use the method `skipFirst=true`. | App developer |
| Cross-platform landing page setup | **Recommended**: A cross-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Steam.<br /><br /><Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Learn about cross-platform landing pages</Anchor><br /><br /><Anchor target="_blank" href="/marketers/vi/docs/cross-platform-landing-pages-with-smart-script">Learn how to set up a cross-platform landing page</Anchor><br /><br />For Native PC, the following parameters are required:<ul><li>**App name**</li><li>**app\_id**<br />An app ID is needed for AppsFlyer to use. Native PC apps don't have specific app ID rules, so your developer can choose and create any app ID they want for your app. **Recommended**: Choose an ID meaningful to you, but that is unlikely to be used by apps. For example, `app-name-is-the-best`.</li><li>**af\_media\_source**</li><li>**af\_campaign\_id**</li><li>**platform**<br />Example: steam</li></ul>The following parameters are not required but recommended:<ul><li>**campaign**</li><li>**ad**</li><li>**ad\_set**</li></ul> | Marketer (may require developer assistance) |
| Direct attribution link setup | <ul><li>If you don’t use a cross-platform landing page, you can create direct attribution links to place behind ads.</li><li>If you do use a cross-platform landing page, we recommend also using direct attribution links and placing them behind the dedicated platform buttons on the landing page.</li><li><Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-direct-attribution-links">Learn how to create direct attribution links</Anchor></li></ul> | Marketer |
| Report setup/view data | <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts#tính-khả-dụng-của-dữ-liệu">Learn about data availability in dashboards and reports</Anchor> | Marketer/Data engineer |

### Removing AppsFlyer data when uninstalling the app

To remove all AppsFlyer SDK data when uninstalling the app, please ask your developer to perform the steps specified [here](https://dev.appsflyer.com/hc/docs/nativepc-vanilla#deleting-appsflyer-data-on-uninstall).

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Import cost data via <Anchor target="_blank" href="/marketers/vi/docs/import-cost-data">Cost Import</Anchor> using the upload file **by email** method. You can also pull data **via API** for Google, Meta, or TikTok. |

> 📄 **See also**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform overview</Anchor>

<div data-zendesk-anchors="about-steam-attribution=about-native-pc-attribution 01H7Z19FJ5J1CB4ESE55Z32C1C=about-native-pc-attribution flow=example-attribution-flow 01H7Z19FJ5R869054GDRKHTBJ8=example-attribution-flow 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint 01H7Z19FJ5KKPJ88KAQM49FNVA=integration-procedures h_01J3349MAA4J231B6FJ74V3PTB=removing-appsflyer-data-when-uninstalling-the-app h_01HF9W8YG149TMQE1F57BG0ZS7=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=see-also" />
