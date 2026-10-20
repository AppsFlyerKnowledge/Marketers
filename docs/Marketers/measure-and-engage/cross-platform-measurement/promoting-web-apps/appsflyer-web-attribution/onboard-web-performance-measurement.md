---
title: Onboard Web Performance Measurement
excerpt: >-
  Follow the onboarding instructions in this guide to set up Web Performance
  Measurement. Once set up, you can measure and attribute website visits and web
  events to marketing sources, understand what drives meaningful website
  outcomes, and support cross-platform measurement.
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
## About Web Performance Measurement

Web Performance Measurement helps you connect what happens on your website, such as visits and web events, to the marketing sources that drove them. In other words, it shows you which media sources and campaigns bring users to your site and influence what they do next, so you can measure performance and optimize ROI.

### Create a web app in AppsFlyer

<Embed title="Onboard Web Performance Measurement" typeOfEmbed="youtube" url="https://www.youtube.com/embed/MOn_UsirYCU" providerUrl="https://www.youtube.com" />

### Set up network integrations, postbacks, and cost measurement

<Embed title="Onboard Web Performance Measurement" typeOfEmbed="youtube" url="https://www.youtube.com/embed/-sYIv3YQEwo" providerUrl="https://www.youtube.com" />

To start measuring website visits and web events in AppsFlyer, follow the onboarding steps in the Web Performance Measurement setup checklist below.

## Web Performance Measurement setup checklist

Use the table below to complete the key setup tasks, who needs to do what, and in what order, to start collecting web visits and web events in AppsFlyer.

| Task | Actions required | Where to learn | Who’s involved |
| --- | --- | --- | --- |
| 1. Create a web app | In the **App settings** page:<ul><li>Copy the **Web SDK ID** and share it with your developer.</li><li>Set the reporting **Timezone** and **Currency**.</li><li>Select the **Excluded domains**.</li></ul> | <ul><li>[Configure the web app settings](/docs/adding-an-app-to-appsflyer#web)</li></ul> | Marketer |
| 2. (Optional) Create a product line for cross-platform LTV | To enable cross-platform attribution and lifetime value (LTV) user-journey measurement, create a product line entity and either associate the relevant apps/web properties or add your web app to an existing product line. | <ul><li>[Create a product line](/docs/product-line-group-apps-for-cross-platform-attribution)</li></ul> | Marketer |
| 3. Install and configure the Web SDK | Integrate the AppsFlyer Web SDK into your website. | <ul><li>[Integrate the Web SDK into your website](/docs/integrate-appsflyer-web-sdk)</li><li>[Test your Web SDK integration](/docs/use-the-web-sdk-test-page)</li></ul> | Developer |
| 4. Send web data using the S2S API | Use the server-to-server (S2S) API to send web visits and events to AppsFlyer directly from your server. Use it alongside the Web SDK to increase measurement coverage and enrich event data, or on its own for a fully server-side integration. | <ul><li>[Set up the S2S API for Web Performance Measurement](/docs/server-to-server-s2s-api-for-web-performance-measurement)</li></ul> | Business intelligence (BI) engineer |
| 5. Configure the web app attribution settings | In the **App settings** page, configure the web app attribution settings, such as lookback windows and the user acquisition events.  <br />**Note:** Custom user acquisition events can be selected only after the Web SDK is integrated into your website. | <ul><li>[Configure the web app attribution settings](/docs/configure-web-performance-measurement-settings)</li></ul> | Marketer |
| 6. Create URLs for Web Performance Measurement | Create URLs using the correct attribution parameters to get the most accurate and granular attribution results. | <ul><li>[Choose attribution parameters for landing page URLs](/docs/choose-attribution-parameters-for-landing-page-urls)</li></ul> | Marketer |
| 7. Set up integration with supported partners | Activate the partners and set the postbacks sent to them.<br />Supported partners:<ul><li>Google Ads</li><li>Meta Ads</li><li>TikTok Ads</li><li>Snapchat Ads</li></ul> | Create web campaigns for website apps with:<ul><li>[Google Ads](/docs/google-ads-adwords-create-web-campaigns-for-website-apps)</li><li>[Meta Ads](/docs/meta-ads-create-web-campaigns-for-website-apps)</li><li>[TikTok Ads](/docs/tiktok-for-business-create-web-campaigns-for-website-apps)</li><li>[Snapchat Ads](/docs/snapchat-create-web-campaigns-for-website-apps)</li></ul> | Marketer |
| 8. Export Web Performance Measurement data from Data Locker | Configure **Data Locker** for Web Performance Measurement raw-data reports so business intelligence and analytics teams can analyze web journeys. | <ul><li>[Export Web Performance Measurement data from Data Locker](/docs/export-web-performance-measurement-report-data-from-data-locker)</li></ul> | Marketer / BI engineer |
| 9. View your web data in the cross-platform dashboard | View how web sessions and events appear in the cross-platform dashboard. | <ul><li>[Web attribution in the cross-platform dashboard](/docs/my-dashboards#web-attribution-in-the-cross-platform-dashboard)</li></ul> | Marketer |
| 10. Measure the cost of website campaigns<br /><br />**(For ROI360 only)** | Connect your web app to the cost integrations in **Cost Settings** for supported self-reporting networks (SRNs): Google, Meta (Facebook), Snapchat, and TikTok.  <br />  <br />Once connected, AppsFlyer reports cost, clicks, and impressions for web campaigns in near real time in Cost ETL reports and My Dashboard.  <br />  <br />For the **ROI360 advanced package**, add your web app to the included apps list in the Cost ETL configuration page.  <br />  <br />**Note:** Attribution links must include a campaign ID in the landing page URL. | Connect your web app to cost integrations:<ul><li>[Google Ads](/docs/google-ads-adwords-create-web-campaigns-for-website-apps#measure-web-performance-measurement-data-with-web-cost)</li><li>[Meta Ads](/docs/meta-ads-create-web-campaigns-for-website-apps#measure-web-attribution-data-with-web-cost)</li><li>[Snapchat Ads](/docs/snapchat-create-web-campaigns-for-website-apps#measure-web-attribution-data-with-web-cost)</li><li>[Set up Cost ETL](/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl)</li></ul> | Marketer / BI engineer |

<div data-zendesk-anchors="about-appsflyer-web-attribution=about-web-performance-measurement h_01KGN43TYPKCQ7H3SRRHHPT387=about-web-performance-measurement how-to-create-a-web-app-in-appsflyer=create-a-web-app-in-appsflyer h_01KVSNN9H462X8DVYBS6TJ8JXQ=create-a-web-app-in-appsflyer how-to-set-up-network-integrations-postbacks-and-cost-measurement=set-up-network-integrations-postbacks-and-cost-measurement h_01KVSNSSZ7QY090JVWVTRF88ND=set-up-network-integrations-postbacks-and-cost-measurement appsflyer-web-attribution-setup-checklist=web-performance-measurement-setup-checklist h_01KGN43TYP1EV5KFQ37FC4SM0C=web-performance-measurement-setup-checklist" />
