---
title: "Google Play Games on PC integration with AppsFlyer"
excerpt: "Integrate your Google Play Games on PC/Android game or app with AppsFlyer to measure the performance of campaigns marketing these apps."
x-zendesk:
  id: 18315431772817
  url: https://support.appsflyer.com/hc/en-us/articles/18315431772817-Google-Play-Games-on-PC-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Promoting Desktop apps
  section_id: 15329004312593
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roi-tamir, Marketers, PC & Console Attribution]
  labels: [Marketers, cross-platform, Loc In Prog]
  promoted: false
  comments_disabled: true
  created_at: '2023-09-05T13:06:17Z'
  edited_at: '2024-08-29T15:14:48Z'
---
## About Google Play Games for PC attribution

Google Play Games is a PC application that lets users browse, download, and play selected Android mobile games on a Windows desktop or laptop. Google Play Games runs across Windows PC devices.

Apps running on Google Play Games are like any other Android app. They are essentially mobile Android games available on PC. And just like any mobile Android app, they can integrate out of the box with AppsFlyer using the AppsFlyer Android SDK, to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

AppsFlyer uses the same attribution flow for apps running on Google Play Games as it does for mobile Android apps.

## Integration procedures

The following table lists the tasks required to integrate your Google Play Games app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | <ul><li>[Create an AppsFlyer account](https://www.appsflyer.com/get-started/)</li><li>[Add account users with appropriate permissions](/docs/user-management)</li><li>[Add your Android app in AppsFlyer](/docs/adding-an-app-to-appsflyer)</li></ul> | Marketer |
| SDK integration with your app | Integrate the [AppsFlyer Android SDK](https://dev.appsflyer.com/hc/docs/android-sdk). | App developer |
| Cross-platform landing page setup | **Recommended**: A cross-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Steam.<br /><br />[Learn about cross-platform landing pages](/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page)<br /><br />[Learn how to set up a cross-platform landing page](/docs/cross-platform-landing-pages-with-smart-script) | Marketer (may require developer assistance) |
| Link setup | If you don't use a cross-platform landing page, you can create direct attribution links to place behind ads. Marketing campaigns for Google Play Games apps use links similar to the attribution links created in AppsFlyer for mobile apps.<br /><br />[Learn how to create links](/docs/about-link-structure-and-parameters) | Marketer |
| Report setup/view data | AppsFlyer dashboards and reports for Google Play Games apps are similar to those available for mobile apps.<br /><br />[Learn more about AppsFlyer dashboards and reports](/docs/analyze-your-data) | Marketer/Data engineer |

> 📘 **See also**
>
> * [CTV, PC, and console platform concepts](/docs/ctv-pc-and-console-platform-attribution-concepts)
> * [Google Ads Web integration for PC and console apps](/docs/google-ads-web-integration-for-pc-and-console-apps)