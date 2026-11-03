---
title: Google Play Games on PC integration with AppsFlyer
metadata:
  keywords:
    - Marketers
    - cross-platform
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-09-05T13:06:17Z'
  edited_at: '2024-08-29T15:14:48Z'
  id: 18315431772817
  locale: en-us
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/18315431772817-Google-Play-Games-on-PC-integration-with-AppsFlyer
---
> **At a glance:** Integrate your Google Play Games on PC/Android game or app with AppsFlyer to measure the performance of campaigns marketing these apps.

## About Google Play Games for PC attribution

Google Play Games is a PC application that lets users browse, download, and play selected Android mobile games on a Windows desktop or laptop. Google Play Games runs across Windows PC devices.

Apps running on Google Play Games are like any other Android app. They are essentially mobile Android games available on PC. And just like any mobile Android app, they can integrate out of the box with AppsFlyer using the AppsFlyer Android SDK, to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

AppsFlyer uses the same attribution flow for apps running on Google Play Games as it does for mobile Android apps.

## Integration procedures

The following table lists the tasks required to integrate your Google Play Games app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Create an AppsFlyer account</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/user-management">Add account users with appropriate permissions</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Add your Android app in AppsFlyer</Anchor></li></ul> | Marketer |
| SDK integration with your app | Integrate the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk">AppsFlyer Android SDK</Anchor>. | App developer |
| Cross-platform landing page setup | **Recommended**: A cross-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Steam.<br /><br /><Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Learn about cross-platform landing pages</Anchor><br /><br /><Anchor target="_blank" href="/marketers/fr/docs/cross-platform-landing-pages-with-smart-script">Learn how to set up a cross-platform landing page</Anchor> | Marketer (may require developer assistance) |
| Link setup | If you don't use a cross-platform landing page, you can create direct attribution links to place behind ads. Marketing campaigns for Google Play Games apps use links similar to the attribution links created in AppsFlyer for mobile apps.<br /><br /><Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">Learn how to create links</Anchor> | Marketer |
| Report setup/view data | AppsFlyer dashboards and reports for Google Play Games apps are similar to those available for mobile apps.<br /><br /><Anchor target="_blank" href="/marketers/fr/docs/analyze-your-data">Learn more about AppsFlyer dashboards and reports</Anchor> | Marketer/Data engineer |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform concepts</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/google-ads-web-integration-for-pc-and-console-apps">Google Ads Web integration for PC and console apps</Anchor>

<div data-zendesk-anchors="about-steam-attribution=about-google-play-games-for-pc-attribution 01H7Z1DJRW1KPJQ4CZ6T85ASRK=about-google-play-games-for-pc-attribution 01H7Z1DJRWX54DN2SNS21GPGXB=integration-procedures h_01HDP2XBSEJVQ5G0MD0V5R05CM=see-also" />
