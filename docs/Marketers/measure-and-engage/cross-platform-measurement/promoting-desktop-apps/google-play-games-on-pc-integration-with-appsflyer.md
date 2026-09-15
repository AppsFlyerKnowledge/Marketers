---
title: "Google Play Games on PC integration with AppsFlyer"
excerpt: "Integrate your Google Play Games on PC/Android game or app with AppsFlyer to measure the performance of campaigns marketing these apps."
---
## About Google Play Games for PC attribution

Google Play Games is a PC application that lets users browse, download, and play selected Android mobile games on a Windows desktop or laptop. Google Play Games runs across Windows PC devices.

Apps running on Google Play Games are like any other Android app. They are essentially mobile Android games available on PC. And just like any mobile Android app, they can integrate out of the box with AppsFlyer using the AppsFlyer Android SDK, to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

AppsFlyer uses the same attribution flow for apps running on Google Play Games as it does for mobile Android apps.

## Integration procedures

The following table lists the tasks required to integrate your Google Play Games app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | - [Create an AppsFlyer account](https://www.appsflyer.com/get-started/)<br />- [Add account users with appropriate permissions](/docs/user-management)<br />- [Add your Android app in AppsFlyer](/docs/adding-an-app-to-appsflyer) | Marketer |
| SDK integration with your app | Integrate the [AppsFlyer Android SDK](https://dev.appsflyer.com/hc/docs/android-sdk). | App developer |
| Cross-platform landing page setup | **Recommended**: Across-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Steam.<br />[Learn about cross-platform landing pages](/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page)<br />[Learn how to set up a cross-platform landing page](/docs/cross-platform-landing-pages-with-smart-script) | Marketer (may require developer assistance) |
| Link setup | If you don't use a cross-platform landing page, you can create direct attribution links to place behind ads. Marketing campaigns for Google Play Games apps use links similar to the attribution links created in AppsFlyer for mobile apps.<br />[Learn how to create links](/docs/about-link-structure-and-parameters) | Marketer |
| Report setup/view data | AppsFlyer dashboards and reports for Google Play Games apps are similar to those available for mobile apps.<br />[Learn more about AppsFlyer dashboards and reports](/docs/analyze-your-data) | Marketer/Data engineer |

<Cards>
  <Card title="CTV, PC, and console platform concepts" href="/docs/ctv-pc-and-console-platform-attribution-concepts" icon="fa-solid fa-diagram-project">
    Learn about Connected TV, PC, and console platform attribution concepts.
  </Card>
  <Card title="Google Ads Web integration for PC and console apps" href="/docs/google-ads-web-integration-for-pc-and-console-apps" icon="fa-solid fa-bullhorn">
    Learn how to integrate Google Ads Web for PC and console applications.
  </Card>
</Cards>