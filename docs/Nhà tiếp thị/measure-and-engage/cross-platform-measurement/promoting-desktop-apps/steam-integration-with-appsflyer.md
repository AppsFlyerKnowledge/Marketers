---
title: Steam integration with AppsFlyer
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
  created_at: '2022-12-08T10:02:09Z'
  edited_at: '2026-10-05T06:59:19Z'
  id: 11241130508433
  locale: en-us
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/11241130508433-Steam-integration-with-AppsFlyer
---
> **At a glance:** Integrate your Steam game/app with AppsFlyer to receive attribution and event data for your Steam campaigns. The Steam integration supports attribution and in-app event recording for Steam apps on a user's Steam device.

## About Steam attribution

Steam runs across Windows and Mac devices, Steam Deck, and other Steam OS devices.

Apps running on Steam can integrate with AppsFlyer via S2S API or SDK to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

### Example attribution flow

The following is an example flow that highlights the most important steps in a user journey from ad engagement to attribution. It includes the AppsFlyer-recommended cross-platform landing page. **Note**: While we recommend using the cross-platform landing page, you can also use direct attribution links

<Image align="center" alt="Steam_user_journey.jpg" src="https://files.readme.io/4979821043af1ed3e662b55c84df10a17a863e79084d050c478fa31767ed8eaa-51473918246929.jpg" />

1. Marketing touchpoint: Customers interact with your brand through online or offline marketing touchpoints. These can include, email and newsletters, social media, mobile web, and more.
2. Game landing page: A game landing page directs customers to your Steam game page. This step is important for collecting UTM and other URL parameters to attribute customers from the click/install to the original media sources or to your owned media sources.  
   The landing page is also useful because it provides links to the various platforms your game supports. For example, you can have links to your Xbox, Microsoft store, and Steam page on your landing page.  
   <Image align="center" alt="awesome_game.png" src="https://files.readme.io/37cabff10a2e0a721b4d2901e7df47f53a7dedff25bdac80b97003b60eaef430-51473918248465.png" />
3. <span id="marketing-touchpoint"></span>Steam app page: This is your Steam storefront page that hosts your Steam app for customers to download.
4. Game install: The user installs the game, triggering attribution and the recording of in-app events and sessions.

## Integration procedures

The following table lists the tasks required to integrate your Steam app with AppsFlyer.

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
        * <Anchor target="_blank" href="/marketers/vi/docs/user-management">Add account users with appropriate permissions</Anchor>
        * <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">Add your Steam app to AppsFlyer</Anchor>
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
        There are two methods of integration you can use: S2S and SDK.

        For the S2S method, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">integrate the AppsFlyer API</Anchor> into your app with commands to report the following events to AppsFlyer.

        * First opens
        * In-app events
        * Sessions

        **Note**:

        * First app opens must be reported before in-app events and sessions.
        * For the `platform` parameter, select `steam`.
        * For the `device_ids` parameter, select the type `custom` or `steamid`.
          * The `custom` or `steamid` for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">first opens</Anchor> should match your <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">in-app events</Anchor>, and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sessions</Anchor> ID.
        * Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.
        * To report owned media engagements, integrate the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor>

        For the SDK method, there are three versions: native <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/steam-vanilla">C++</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-steam">Unreal</Anchor>, and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-steam">Unity</Anchor>.

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

        <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Learn about cross-platform landing pages</Anchor>

        <Anchor target="_blank" href="/marketers/vi/docs/cross-platform-landing-pages-with-smart-script">Learn how to set up a cross-platform landing page</Anchor>

        **Note**:

        For Steam, the following parameters are required:

        * **platform**: steam
        * **steam\_app\_id**: The ID of the app page.

          You can find your unique app ID by copying it from the URL bar or by going to <Anchor target="_blank" href="https://steamdb.info/">https://steamdb.info/</Anchor> and searching for your game. For example,

          ```http
          https://store.steampowered.com/app/12345678/
          ```

          where **12345678** is your unique app ID.
        * **media\_source**

        The following parameters are not required but recommended:

        * **campaign**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**: The full URL of the Steam storefront for your app including your **steam\_app\_id**. For example, `https://store.steampowered.com/app/12345678/`
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
        If you don't use a cross-platform landing page, you can create direct attribution links to place behind ads.

        <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-direct-attribution-links">Learn how to create direct attribution links</Anchor>
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
        <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts#tính-khả-dụng-của-dữ-liệu">Learn about data availability in dashboards and reports</Anchor>
      </td>
      <td>
        Marketer/Data engineer
      </td>
    </tr>
  </tbody>
</Table>

### Removing AppsFlyer data when uninstalling the app

To remove all AppsFlyer SDK data when uninstalling the app, please ask your developer to perform the steps specified [here](https://dev.appsflyer.com/hc/docs/steam-vanilla#deleting-appsflyer-data-on-uninstall).

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Import cost data via <Anchor target="_blank" href="/marketers/vi/docs/import-cost-data">Cost Import</Anchor> using the upload file **by email** method. You can also pull data **via API** for Google, Meta, or TikTok. |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform attribution</Anchor>

<div data-zendesk-anchors="01H7Z1DJRW1KPJQ4CZ6T85ASRK=about-steam-attribution flow=example-attribution-flow 01H7Z1DJRWHB8TQC15WW4FVSHG=example-attribution-flow 01H7Z1DJRWX54DN2SNS21GPGXB=integration-procedures h_01J3349MAA4J231B6FJ74V3PTB=removing-appsflyer-data-when-uninstalling-the-app h_01HDEHMH0HF201TH4XDW691STH=traits-and-limitations h_01HDP1K6FDDEED5P2WNESST7GE=see-also" />
