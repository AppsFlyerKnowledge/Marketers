---
title: Meta Quest (Oculus) integration with AppsFlyer
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-12-08T10:10:00Z'
  edited_at: '2026-10-05T07:01:20Z'
  id: 11241398279569
  locale: en-us
  section: Promoting Console apps
  section_id: 15329052471057
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/11241398279569-Meta-Quest-Oculus-integration-with-AppsFlyer
---
> **At a glance:** Integrate your Meta Quest (Oculus) app with AppsFlyer to receive attribution and event data for your campaigns on Meta Quest (Oculus).

## About Meta Quest (Oculus) attribution

The Meta Quest (Oculus) OS for gaming runs across all Meta Quest (Oculus) devices.

Apps running on Meta Quest can integrate with AppsFlyer via S2S API or SDK to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

## Integration procedures

The following table lists the tasks required to integrate your Meta Quest (Oculus) app with AppsFlyer.

<Table>
  <thead>
    <tr>
      <th>
        Task
      </th>
      <th>
        Actions
      </th>
      <th>
        Who's involved
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        App setup
      </td>
      <td>
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Create an AppsFlyer account</Anchor>
        * <Anchor target="_blank" href="/marketers/docs/user-management">Add account users with appropriate permissions</Anchor>
        * <Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer">Add your Meta Quest (Oculus) app in AppsFlyer</Anchor>
      </td>
      <td>
        Marketer
      </td>
    </tr>
    <tr>
      <td>
        SDK integration with your app (via S2S or SDK)
      </td>
      <td>
        There are two methods of integration you can use: S2S and SDK.

        For the S2S method, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">integrate the AppsFlyer API</Anchor> into your app with commands to report the following events to AppsFlyer.

        * First opens
        * In-app events
        * Sessions

        **Note**:

        * First app opens must be reported before in-app events and sessions.
        * For the `device_ids` parameter, select the type `custom`.
          * The `custom` generated ID for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">first opens</Anchor> should match your <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">in-app events</Anchor>, and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sessions</Anchor> ID.
          * Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.
          * To report owned media engagements, integrate the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor>

        For the SDK method, there are two versions: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unity">Unity</Anchor>, and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unreal">Unreal</Anchor>.

        **Note**:

        If you have an existing user base and therefore want the first session to be considered a session and not an install, the developer can use the method `skipFirst=true`.
      </td>
      <td>
        App developer
      </td>
    </tr>
    <tr>
      <td>
        Cross-platform landing page setup
      </td>
      <td>
        **Recommended**: A cross-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Native PC.

        <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Learn about cross-platform landing pages</Anchor>

        <Anchor target="_blank" href="/marketers/docs/cross-platform-landing-pages-with-smart-script">Learn how to set up a cross-platform landing page</Anchor>

        **Note**:

        For Meta Quest, the following parameters are required:

        * **platform**: quest
        * **QUEST\_APP\_ID**: The Quest Store app ID.  
          For Quest 2, this is the number in the store URL, for example:

          ```http
          https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/
          ```

          where **XXXXXXXXXXXXXXXX** is your unique app ID.
        * **media\_source**

        The following parameters are not required but recommended:

        * **campaign**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**: The full URL of the Oculus storefront for your app, including your **QUEST\_APP\_ID**. For example, `https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/`
      </td>
      <td>
        Marketer (may require developer assistance)
      </td>
    </tr>
    <tr>
      <td>
        Link setup
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-direct-attribution-links">Learn how to create direct attribution links</Anchor>
      </td>
      <td>
        Marketer
      </td>
    </tr>
    <tr>
      <td>
        Report setup/view data
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts#data-availability">Learn about data availability in dashboards and reports</Anchor>
      </td>
      <td>
        Marketer/Data engineer
      </td>
    </tr>
  </tbody>
</Table>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Import cost data via <Anchor target="_blank" href="/marketers/docs/import-cost-data">Cost Import</Anchor> using the upload file **by email** method. You can also pull data **via API** for Google, Meta, or TikTok. |

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform overview</Anchor>

<div data-zendesk-anchors="about-meta-quest-attribution=about-meta-quest-oculus-attribution 01H7Z1MK9JHA4C5CB7YME4AJMA=about-meta-quest-oculus-attribution 01H7Z1MK9JNRKAY9VNH5RTF03F=integration-procedures 01H7Z1MK9KXFY4XVPCDSJPQ26N=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=see-also" />
