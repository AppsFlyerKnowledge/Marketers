---
title: Nintendo Switch integration with AppsFlyer
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
> **At a glance:** Integrate your Nintendo Switch game or app with AppsFlyer to receive attribution and event data for your Nintendo Switch campaigns.

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
        * <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">Add your Nintendo Switch app in AppsFlyer</Anchor>
      </td>
      <td>
        Marketer
      </td>
    </tr>
    <tr>
      <td>
        API integration with your app (via S2S)
      </td>
      <td>
        <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">Integrate the AppsFlyer API</Anchor> into your app with commands to report the following events to AppsFlyer.

        * First opens
        * In-app events
        * Sessions

        **Note**:

        * First app opens must be reported before in-app events and sessions.
        * For the `device_ids` parameter, select the type `custom`.
          * The `custom` generated ID for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">first opens</Anchor> should match your <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">in-app events</Anchor>, and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sessions</Anchor> ID.
          * Send events using the API. Tell your developer which events to send. Verify that when you set up the API, you set up and map the events to send to AppsFlyer.

        To report owned media engagements, integrate the <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor>
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

        For Nintendo Switch, the following parameters are required:

        * **platform**  
          switch
        * **nintendo\_app\_id**  
          The ID of the app page.  

          You can find your unique app ID by copying it from the URL bar or by going to <Anchor target="_blank" href="https://www.nintendo.com/store/products/octopath-traveler-ii-switch/">https://www.nintendo.com/store/products/</Anchor> and searching for your game. For example,

          ```http
          https://www.nintendo.com/store/products/app-id-switch/
          ```

          where **app-id** is your unique app ID.
        * **media\_source**

        The following parameters are not required but recommended:

        * **campaign**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**  
          The full URL of your Nintendo Switch storefront for your app including your **nintendo\_app\_id**.  
          For example,

          ```http
          https://www.nintendo.com/store/products/app-id-switch/
          ```
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

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Retargeting | Not currently supported |
| Cost data | Cost data must be sent via <Anchor target="_blank" href="/marketers/vi/docs/import-cost-data">Ad Spend Ingestion</Anchor> using the upload file by email method. |

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform overview</Anchor>

<div data-zendesk-anchors="01H7Z1HPD0AB0VP6REMBF2HCR8=about-nintendo-switch-attribution h_01HP1QDGDAXV0Y7MVJYHW3H4SQ=example-attribution-flow 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint 01H7Z1HPD0VAMPEHBPN8MAT3ST=integration-procedures 01H7Z1HPD0CS7CTX2KS2RVD3VA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=see-also" />
