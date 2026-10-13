---
title: "Meta Quest (Oculus) integration with AppsFlyer"
excerpt: "Integrate your Meta Quest (Oculus) app with AppsFlyer to receive attribution and event data for your campaigns."
x-zendesk:
  id: 11241398279569
  url: https://support.appsflyer.com/hc/en-us/articles/11241398279569-Meta-Quest-Oculus-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Promoting Console apps
  section_id: 15329052471057
  position: 12
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roi-tamir, Marketers, PC & Console Attribution]
  labels: [CTV, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2022-12-08T10:10:00Z'
  edited_at: '2026-10-05T07:01:20Z'
---
**At a glance:** Integrate your Meta Quest (Oculus) app with AppsFlyer to receive attribution and event data for your campaigns on Meta Quest (Oculus).

## About Meta Quest (Oculus) attribution

The Meta Quest (Oculus) OS for gaming runs across all Meta Quest (Oculus) devices.

Apps running on Meta Quest can integrate with AppsFlyer via S2S API or SDK to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

## Integration procedures

The following table lists the tasks required to integrate your Meta Quest (Oculus) app with AppsFlyer.

| Task | Actions | Who's involved |
| --- | --- | --- |
| App setup | * [Create an AppsFlyer account](https://www.appsflyer.com/get-started/)<br />* [Add account users with appropriate permissions](/docs/user-management)<br />* [Add your Meta Quest (Oculus) app in AppsFlyer](/docs/adding-an-app-to-appsflyer) | Marketer |
| SDK integration with your app (via S2S or SDK) | There are two methods of integration you can use: S2S and SDK.<br /><br />For the S2S method, [integrate the AppsFlyer API](https://dev.appsflyer.com/hc/reference/overview-4) into your app with commands to report the following events to AppsFlyer.<br /><br />* First opens<br />* In-app events<br />* Sessions<br /><br />**Note**:<br /><br />* First app opens must be reported before in-app events and sessions.<br />* For the `device_ids` parameter, select the type `custom`.<br />  * The `custom` generated ID for [first opens](https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id) should match your [in-app events](https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id), and [sessions](https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id) ID.<br />  * Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.<br />  * To report owned media engagements, integrate the [impression engagement API.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id)<br /><br />For the SDK method, there are two versions: [Unity](https://dev.appsflyer.com/hc/docs/meta-quest2-unity), and [Unreal](https://dev.appsflyer.com/hc/docs/meta-quest2-unreal).<br /><br />**Note**:<br /><br />If you have an existing user base and therefore want the first session to be considered a session and not an install, the developer can use the method `skipFirst=true`. | App developer |
| Cross-platform landing page setup | **Recommended**: A cross-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Native PC.<br /><br />[Learn about cross-platform landing pages](/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page)<br /><br />[Learn how to set up a cross-platform landing page](/docs/cross-platform-landing-pages-with-smart-script)<br /><br />**Note**:<br /><br />For Meta Quest, the following parameters are required:<br /><br />* **platform**: quest<br />* **QUEST\_APP\_ID**: The Quest Store app ID.  <br />  For Quest 2, this is the number in the store URL, for example:<br /><br />  ```<br />  https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/<br />  ```<br /><br />  where **XXXXXXXXXXXXXXXX** is your unique app ID.<br />* **media\_source**<br /><br />The following parameters are not required but recommended:<br /><br />* **campaign**<br />* **ad**<br />* **ad\_set**<br />* **storefront\_redirect\_url**: The full URL of the Oculus storefront for your app, including your **QUEST\_APP\_ID**. For example, `https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/` | Marketer (may require developer assistance) |
| Link setup | [Learn how to create direct attribution links](/docs/ctv-pc-and-console-platform-direct-attribution-links) | Marketer |
| Report setup/view data | [Learn about data availability in dashboards and reports](/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability) | Marketer/Data engineer |

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Import cost data via [Cost Import](/docs/import-cost-data) using the upload file **by email** method. You can also pull data **via API** for Google, Meta, or TikTok. |

> 📘 **See also**
>
> * [CTV, PC, and console platform overview](/docs/ctv-pc-and-console-platform-attribution-concepts)