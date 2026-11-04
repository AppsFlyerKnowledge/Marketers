---
title: Onboard Web Performance Measurement
metadata:
  keywords:
    - Attribution
    - Agencies
    - Web Attribution
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T19:35:31Z'
  edited_at: '2026-08-24T07:22:47Z'
  id: 43529798016401
  locale: en-us
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/43529798016401-Onboard-Web-Performance-Measurement
---
> **At a glance:** Follow the onboarding instructions in this guide to set up Web Performance Measurement. Once set up, you can measure and attribute website visits and web events to marketing sources, understand what drives meaningful website outcomes, and support cross-platform measurement.

<div id="about-web-performance-measurement" />

## About Web Performance Measurement

Web Performance Measurement helps you connect what happens on your website, such as visits and web events, to the marketing sources that drove them. In other words, it shows you which media sources and campaigns bring users to your site and influence what they do next, so you can measure performance and optimize ROI.

<div id="create-a-web-app-in-appsflyer" />

### Create a web app in AppsFlyer

<Embed title="Onboard Web Performance Measurement" typeOfEmbed="youtube" url="https://www.youtube.com/embed/MOn_UsirYCU" providerUrl="https://www.youtube.com" />

<div id="set-up-network-integrations-postbacks-and-cost-measurement" />

### Set up network integrations, postbacks, and cost measurement

<Embed title="Onboard Web Performance Measurement" typeOfEmbed="youtube" url="https://www.youtube.com/embed/-sYIv3YQEwo" providerUrl="https://www.youtube.com" />

To start measuring website visits and web events in AppsFlyer, follow the onboarding steps in the Web Performance Measurement setup checklist below.

<div id="web-performance-measurement-setup-checklist" />

## Web Performance Measurement setup checklist

Use the table below to complete the key setup tasks, who needs to do what, and in what order, to start collecting web visits and web events in AppsFlyer.

| Task | Actions required | Where to learn | Who’s involved |
| --- | --- | --- | --- |
| 1. Create a web app | In the **App settings** page:<ul><li>Copy the **Web SDK ID** and share it with your developer.</li><li>Set the reporting **Timezone** and **Currency**.</li><li>Select the **Excluded domains**.</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer#web">Configure the web app settings</Anchor></li></ul> | Marketer |
| 2. (Optional) Create a product line for cross-platform LTV | To enable cross-platform attribution and lifetime value (LTV) user-journey measurement, create a product line entity and either associate the relevant apps/web properties or add your web app to an existing product line. | <ul><li><Anchor target="_blank" href="/marketers/docs/product-line-group-apps-for-cross-platform-attribution">Create a product line</Anchor></li></ul> | Marketer |
| 3. Install and configure the Web SDK | Integrate the AppsFlyer Web SDK into your website. | <ul><li><Anchor target="_blank" href="/marketers/docs/integrate-appsflyer-web-sdk">Integrate the Web SDK into your website</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/use-the-web-sdk-test-page">Test your Web SDK integration</Anchor></li></ul> | Developer |
| 4. Send web data using the S2S API | Use the server-to-server (S2S) API to send web visits and events to AppsFlyer directly from your server. Use it alongside the Web SDK to increase measurement coverage and enrich event data, or on its own for a fully server-side integration. | <ul><li><Anchor target="_blank" href="/marketers/docs/server-to-server-s2s-api-for-web-performance-measurement">Set up the S2S API for Web Performance Measurement</Anchor></li></ul> | Business intelligence (BI) engineer |
| 5. Configure the web app attribution settings | In the **App settings** page, configure the web app attribution settings, such as lookback windows and the user acquisition events.  <br />**Note:** Custom user acquisition events can be selected only after the Web SDK is integrated into your website. | <ul><li><Anchor target="_blank" href="/marketers/docs/configure-web-performance-measurement-settings">Configure the web app attribution settings</Anchor></li></ul> | Marketer |
| 6. Create URLs for Web Performance Measurement | Create URLs using the correct attribution parameters to get the most accurate and granular attribution results. | <ul><li><Anchor target="_blank" href="/marketers/docs/choose-attribution-parameters-for-landing-page-urls">Choose attribution parameters for landing page URLs</Anchor></li></ul> | Marketer |
| 7. Set up integration with supported partners | Activate the partners and set the postbacks sent to them.<br />Supported partners:<ul><li>Google Ads</li><li>Meta Ads</li><li>TikTok Ads</li><li>Snapchat Ads</li></ul> | Create web campaigns for website apps with:<ul><li><Anchor target="_blank" href="/marketers/docs/google-ads-adwords-create-web-campaigns-for-website-apps">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/meta-ads-create-web-campaigns-for-website-apps">Meta Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/tiktok-for-business-create-web-campaigns-for-website-apps">TikTok Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/snapchat-create-web-campaigns-for-website-apps">Snapchat Ads</Anchor></li></ul> | Marketer |
| 8. Export Web Performance Measurement data from Data Locker | Configure **Data Locker** for Web Performance Measurement raw-data reports so business intelligence and analytics teams can analyze web journeys. | <ul><li><Anchor target="_blank" href="/marketers/docs/export-web-performance-measurement-report-data-from-data-locker">Export Web Performance Measurement data from Data Locker</Anchor></li></ul> | Marketer / BI engineer |
| 9. View your web data in the cross-platform dashboard | View how web sessions and events appear in the cross-platform dashboard. | <ul><li><Anchor target="_blank" href="/marketers/docs/my-dashboards#web-attribution-in-the-cross-platform-dashboard">Web attribution in the cross-platform dashboard</Anchor></li></ul> | Marketer |
| 10. Measure the cost of website campaigns<br /><br />**(For ROI360 only)** | Connect your web app to the cost integrations in **Cost Settings** for supported self-reporting networks (SRNs): Google, Meta (Facebook), Snapchat, and TikTok.  <br />  <br />Once connected, AppsFlyer reports cost, clicks, and impressions for web campaigns in near real time in Cost ETL reports and My Dashboard.  <br />  <br />For the **ROI360 advanced package**, add your web app to the included apps list in the Cost ETL configuration page.  <br />  <br />**Note:** Attribution links must include a campaign ID in the landing page URL. | Connect your web app to cost integrations:<ul><li><Anchor target="_blank" href="/marketers/docs/google-ads-adwords-create-web-campaigns-for-website-apps#measure-web-performance-data-with-web-cost">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/meta-ads-create-web-campaigns-for-website-apps#measure-web-attribution-data-with-web-cost">Meta Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/snapchat-create-web-campaigns-for-website-apps#measure-web-attribution-data-with-web-cost">Snapchat Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">Set up Cost ETL</Anchor></li></ul> | Marketer / BI engineer |

<div data-zendesk-anchors="about-appsflyer-web-attribution=about-web-performance-measurement h_01KGN43TYPKCQ7H3SRRHHPT387=about-web-performance-measurement how-to-create-a-web-app-in-appsflyer=create-a-web-app-in-appsflyer h_01KVSNN9H462X8DVYBS6TJ8JXQ=create-a-web-app-in-appsflyer how-to-set-up-network-integrations-postbacks-and-cost-measurement=set-up-network-integrations-postbacks-and-cost-measurement h_01KVSNSSZ7QY090JVWVTRF88ND=set-up-network-integrations-postbacks-and-cost-measurement appsflyer-web-attribution-setup-checklist=web-performance-measurement-setup-checklist h_01KGN43TYP1EV5KFQ37FC4SM0C=web-performance-measurement-setup-checklist" />
