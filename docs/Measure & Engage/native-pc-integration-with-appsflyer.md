---
title: "Native PC integration with AppsFlyer"
excerpt: "Integrate your PC game or app with AppsFlyer to receive attribution and event data for your PC campaigns."
---
At a glance: Integrate your PC game or app with AppsFlyer to receive attribution and event data for your PC campaigns. The Native PC integration supports attribution and in-app event recording for PC apps (in other words, attribution and recording on a user's PC).

## About Native PC attribution

Native PC runs across Windows devices, through the installation of an .EXE or .MSI file extension.

This is different than the [AppsFlyer Windows SDK 2.4.1](https://support.appsflyer.com/hc/articles/207032026-Windows-and-Xbox-SDK-integration-for-developers) which works with installs from the Microsoft App Store, Windows phones, and UWP.

Apps running on PC can integrate with AppsFlyer via S2S API or SDK to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

### Example attribution flow

The following is an example flow that highlights the most important steps in a user journey from ad engagement to attribution. It includes the AppsFlyer-recommended cross-platform landing page.

> 📘 Note
>
> While we recommend using the cross-platform landing page, you can also use direct attribution links

<Image src="https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg" alt="User_windows.jpg" />

1. Marketing touchpoint: Customers interact with your brand through online or offline marketing touchpoints. These can include, email and newsletters, social media, mobile web, and more.
2. Game landing page: A game landing page directs customers to your download app page. This step is important for collecting UTM and other URL parameters to attribute customers from the click/install to the original media sources or to your owned media sources.

The landing page is also useful because it provides links to the various platforms your game supports. For example, you can also have links to your Xbox, Microsoft store, and Steam page on your landing page.
3. App page: This is the URL to your Native PC app page that hosts your app for customers to download.
4. Game install: The user installs the game, triggering attribution and the recording of in-app events and sessions.

## Integration procedures

The following table lists the tasks required to integrate your PC app with AppsFlyer.

> 📘 Note
>
> Adding team members and setting up reports in Data Locker are not mandatory.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | - [Create an AppsFlyer account](https://www.appsflyer.com/get-started/)<br>- [Add account users with appropriate permissions](https://support.appsflyer.com/hc/articles/4409128270481--Beta-User-management)<br>- [Add your PC app in AppsFlyer](https://support.appsflyer.com/hc/articles/207377436) | Marketer |
| SDK integration with your app (via S2S or SDK) | There are two methods of integration you can use: S2S and SDK.<br>For the S2S method, [integrate the AppsFlyer API](https://dev.appsflyer.com/hc/reference/overview-4) into your app with commands to report the following events to AppsFlyer.<br>- First opens<br>- In-app events<br>- Sessions<br>**Note**: <br>- First app opens must be reported before in-app events and sessions.<br>- For the `device_ids` parameter, select the type `custom`.<br>  <br>  - The `custom` generated ID for [first opens](https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id) should match your [in-app events](https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id), and [sessions](https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id) ID.<br>- Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer. <br>- To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id)<br>For the SDK method, there are three versions: native [C++](https://dev.appsflyer.com/hc/docs/nativepc-vanilla), [Unreal](https://dev.appsflyer.com/hc/docs/unreal-nativepc), and [Unity](https://dev.appsflyer.com/hc/docs/unity-nativepc).<br>**Note**:<br>If you have an existing user base and therefore want the first session to be considered a session and not an install, the developer can use the method `skipFirst=true`. | App developer |
| Cross-platform landing page setup | **Recommended**: Across-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Steam.<br>[Learn about cross-platform landing pages](https://support.appsflyer.com/hc/articles/4404083608849-Connected-TV-CTV-PC-and-console-platform-attribution-overview#landing-page)<br>[Learn how to set up a cross-platform landing page](https://support.appsflyer.com/hc/articles/18440789126289)<br>For Native PC, the following parameters are required:<br>- **App name**<br>- **app_id** An app ID is needed for AppsFlyer to use. Native PC apps don't have specific app ID rules, so your developer can choose and create any app ID they want for your app. **Recommended**: Choose an ID meaningful to you, but that is unlikely to be used by apps. For example, `app-name-is-the-best`. <br>- **af_media_source**<br>- **af_campaign_id**<br>- **platform**<br>  <br>  Example: steam<br>The following parameters are not required but recommended:<br>- **campaign**<br>- **ad**<br>- **ad_set** | Marketer (may require developer assistance) |
| Direct attribution link setup | - If you don’t use a cross-platform landing page, you can create direct attribution links to place behind ads.<br>- If you do use a cross-platform landing page, we recommend also using direct attribution links and placing them behind the dedicated platform buttons on the landing page.<br>- [Learn how to create direct attribution links](https://support.appsflyer.com/hc/articles/15199908310801) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](https://support.appsflyer.com/hc/articles/4404083608849#data-availability) | Marketer/Data engineer |

### Removing AppsFlyer data when uninstalling the app

To remove all AppsFlyer SDK data when uninstalling the app, please ask your developer to perform the steps specified [here](https://dev.appsflyer.com/hc/docs/nativepc-vanilla#deleting-appsflyer-data-on-uninstall).

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