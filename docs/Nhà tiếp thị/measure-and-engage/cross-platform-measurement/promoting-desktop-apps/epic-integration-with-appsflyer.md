---
title: Epic integration with AppsFlyer
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
  created_at: '2023-04-03T07:18:07Z'
  edited_at: '2026-05-19T08:10:01Z'
  id: 14241298075921
  locale: en-us
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/14241298075921-Epic-integration-with-AppsFlyer
---
> **At a glance:** Integrate your Epic game with AppsFlyer to receive attribution and event data for your Epic campaigns. The Epic integration supports attribution and in-app event recording for Epic games (in other words, attribution and recording on a user's device).

## About Epic game attribution

Games running on Epic can integrate with AppsFlyer via API (both S2S and client-side) to receive attribution data and performance measurements about which sources and campaigns drive app open and in-app events. Marketers rely on these insights to measure and optimize marketing activities.

### Example attribution flow

The following is an example flow that highlights the most important steps in a user journey from ad engagement to attribution. It includes the AppsFlyer-recommended cross-platform landing page. **Note**: While we recommend using the cross-platform landing page, you can also use direct attribution links.

<Image align="center" alt="Epic_journey.jpg" src="https://files.readme.io/c5807442cff142ceb4aa3c4d55628e75b37627a011ca531fa390e46ccc3e23b8-small-14241275857553.jpg" />

1. Marketing touchpoint: Customers interact with your brand through online or offline marketing touchpoints. These can include, email and newsletters, social media, mobile web, and more.
2. Game landing page:  A game landing page directs customers to your Epic game page. This step is important for collecting UTM and other URL parameters to attribute customers from the click/install to the original media sources or to your owned media sources.  
   The landing page is also useful because it provides links to the various platforms your game supports. For example, you can also have links to your Xbox, Microsoft store, and Steam page on your landing page.
3. Epic app page: This is your Epic storefront page that hosts your Epic game for customers to download.
4. Game install: The user installs the game, triggering attribution and the recording of in-app events and sessions.

## Integration procedures

The following table lists the tasks required to integrate your Epic game with AppsFlyer.∑

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
        * <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">Add your Epic game in AppsFlyer</Anchor>
      </td>
      <td>
        Marketer
      </td>
    </tr>
    <tr>
      <td>
        API integration with your app (via S2S or client-side)
      </td>
      <td>
        There are two methods of integration you can use: S2S and client-side.

        For the S2S method:

        <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-epic-sample">Integrate the AppsFlyer Epic API</Anchor> into your app with commands to report the following events to AppsFlyer.

        * First opens
        * In-app events
        * Sessions

        **Note**:

        * First app opens must be reported before in-app events and sessions.
        * For the `device_ids` parameter, select the type `custom` or `epicid`.
          * The `custom` or `epicid` for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">first opens</Anchor> should match your <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">in-app events</Anchor>, and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sessions</Anchor> ID.
        * Send events using the API. Tell your developer which events to send.
        * To report owned media engagements, integrate the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor>

        For the client-side method, there are three versions: native <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-epic-sample">C++</Anchor>, <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unreal-epic-sample-app">Unreal</Anchor>, and <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-epic-sample-app">Unity</Anchor>.

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
        **Recommended**: A cross-platform landing page running the AppsFlyer Smart Script lets you perform web-to-app attribution. It's most recommended when your campaign promotes an app that's also available on other platforms, like Epic and Steam.

        <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Learn about cross-platform landing pages</Anchor>

        <Anchor target="_blank" href="/marketers/vi/docs/cross-platform-landing-pages-with-smart-script">Learn how to set up a cross-platform landing page</Anchor>

        **Note**:

        For Epic, the following parameters are required:

        * **platform**  
          epic
        * **app\_id**  
          The app ID of the game page on the Epic store.

          You can find your unique game ID on your Epic developer console. For example,

          ```http
          https://store.epicgames.com/en-us/p/YOUR-GAME-ID
          ```
        * **media\_source**

        The following parameters are not required but recommended:

        * **campaign**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**  
          The full URL of your Epic storefront for your app including your **app\_id**.  
          For example, `https://store.epicgames.com/en-us/p/12345678/`
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
        Mareketer/Data engineer
      </td>
    </tr>
  </tbody>
</Table>

### Removing AppsFlyer data when uninstalling the app

To remove all AppsFlyer SDK data when uninstalling the app, please ask your developer to perform the steps specified [here](https://dev.appsflyer.com/hc/docs/epic-vanilla#deleting-appsflyer-data-on-uninstall).

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via <Anchor target="_blank" href="/marketers/vi/docs/import-cost-data">Ad Spend Ingestion</Anchor> using the upload file by email method. |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform overview</Anchor>

<div data-zendesk-anchors="about-steam-attribution=about-epic-game-attribution 01H7Z1F3SE03BXJD0WAJV8RE7Q=about-epic-game-attribution flow=example-attribution-flow 01H7Z1F3SETVXQKRQ71YAJACY3=example-attribution-flow 01H7Z1F3SF4J2WJ2Y6QG3VGGVK=integration-procedures h_01J3349MAA4J231B6FJ74V3PTB=removing-appsflyer-data-when-uninstalling-the-app h_01HF9WA5FJ6P4C357ZE231GMR0=traits-and-limitations h_01HE7T4JX3RX3SZW2VPW5ZZY7E=see-also" />
