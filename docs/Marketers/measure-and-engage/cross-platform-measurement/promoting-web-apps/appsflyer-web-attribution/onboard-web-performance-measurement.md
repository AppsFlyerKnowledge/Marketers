---
title: "Onboard Web Performance Measurement"
excerpt: "Follow this onboarding guide to set up Web Performance Measurement in AppsFlyer, allowing you to measure and attribute website visits and web events to marketing sources."
---
At a glance: Follow the onboarding instructions in this guide to set up Web Performance Measurement. Once set up, you can measure and attribute website visits and web events to marketing sources, understand what drives meaningful website outcomes, and support cross-platform measurement.

## About Web Performance Measurement

Web Performance Measurement helps you connect what happens on your website, such as visits and web events, to the marketing sources that drove them. In other words, it shows you which media sources and campaigns bring users to your site and influence what they do next, so you can measure performance and optimize ROI.

### Create a web app in AppsFlyer

<Embed title="Set up web attribution in AppsFlyer: Step-by-step guide" typeOfEmbed="youtube" url="https://www.youtube.com/embed/MOn_UsirYCU" />

### Set up network integrations, postbacks, and cost measurement

<Embed title="Set up website measurement campaign" typeOfEmbed="youtube" url="https://www.youtube.com/embed/-sYIv3YQEwo" />

To start measuring website visits and web events in AppsFlyer, follow the onboarding steps in the Web Performance Measurement setup checklist below.

## Web Performance Measurement setup checklist

Use the table below to complete the key setup tasks, who needs to do what, and in what order, to start collecting web visits and web events in AppsFlyer.

| Task | Actions required | Where to learn | Who’s involved |
| --- | --- | --- | --- |
| 1\. Create a web app | In the **App settings** page **:**<br />- Copy the **Web SDK ID** and share it with your developer.<br />- Set the reporting **Timezone** and **Currency**.<br />- Select the **Excluded domains**. | - [Configure the web app settings](/docs/adding-an-app-to-appsflyer#web) | Marketer |
| 2\. (Optional) Create a product line for cross-platform LTV | To enable cross-platform attribution and lifetime value (LTV) user-journey measurement, create a product line entity and either associate the relevant apps/web properties or add your web app to an existing product line. | - [Create a product line](/docs/product-line-group-apps-for-cross-platform-attribution) | Marketer |
| 3\. Install and configure the Web SDK | Integrate the AppsFlyer Web SDK into your website. | - [Integrate the Web SDK into your website](/docs/integrate-appsflyer-web-sdk)<br />- [Test your Web SDK integration](/docs/use-the-web-sdk-test-page) | Developer |
| 4\. Send web data using the S2S API | Use the server-to-server (S2S) API to send web visits and events to AppsFlyer directly from your server. Use it alongside the Web SDK to increase measurement coverage and enrich event data, or on its own for a fully server-side integration. | - [Set up the S2S API for Web Performance Measurement](/docs/server-to-server-s2s-api-for-web-performance-measurement) | Business intelligence (BI) engineer |
| 5\. Configure the web app attribution settings | In the **App settings** page, configure the web app attribution settings, such as lookback windows and the user acquisition events.<br />**Note:** Custom user acquisition events can be selected only after the Web SDK is integrated into your website. | - [Configure the web app attribution settings](/docs/configure-web-performance-measurement-settings) | Marketer |
| 6\. Create URLs for Web Performance Measurement | Create URLs using the correct attribution parameters to get the most accurate and granular attribution results. | - [Choose attribution parameters for landing page URLs](/docs/choose-attribution-parameters-for-landing-page-urls) | Marketer |
| 7\. Set up integration with supported partners | Activate the partners and set the postbacks sent to them.<br />Supported partners:<br />- Google Ads<br />- Meta Ads<br />- TikTok Ads<br />- Snapchat Ads | Create web campaigns for website apps with:<br />- [Google Ads](/docs/google-ads-adwords-create-web-campaigns-for-website-apps)<br />- [Meta Ads](/docs/meta-ads-create-web-campaigns-for-website-apps)<br />- [TikTok Ads](/docs/tiktok-for-business-create-web-campaigns-for-website-apps)<br />- [Snapchat Ads](/docs/snapchat-create-web-campaigns-for-website-apps) | Marketer |
| 8\. Export Web Performance Measurement data from Data Locker | Configure **Data Locker** for Web Performance Measurement raw-data reports so business intelligence and analytics teams can analyze web journeys. | - [Export Web Performance Measurement data from Data Locker](/docs/export-web-performance-measurement-report-data-from-data-locker) | Marketer / BI engineer |
| 9\. View your web data in the cross-platform dashboard | View how web sessions and events appear in the cross-platform dashboard. | - [Web attribution in the cross-platform dashboard](/docs/my-dashboards#web-attribution-in-cross-platform) | Marketer |
| 10\. Measure the cost of website campaigns<br />**(For ROI360 only)** | Connect your web app to the cost integrations in **Cost Settings** for supported self-reporting networks (SRNs): Google, Meta (Facebook), Snapchat, and TikTok.<br />Once connected, AppsFlyer reports cost, clicks, and impressions for web campaigns in near real time in Cost ETL reports and My Dashboard.<br />For the **ROI360 advanced package**, add your web app to the included apps list in the Cost ETL configuration page.<br />**Note:** Attribution links must include a campaign ID in the landing page URL. | Connect your web app to cost integrations:<br />- [Google Ads](/docs/google-ads-adwords-create-web-campaigns-for-website-apps#measure-web-attribution-data-with-web-cost)<br />- [Meta Ads](/docs/meta-ads-create-web-campaigns-for-website-apps#measure-web-attribution-data-with-web-cost)<br />- [Snapchat Ads](/docs/snapchat-create-web-campaigns-for-website-apps#measure-web-attribution-data-with-web-cost)<br />- [Set up Cost ETL](/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl) | Marketer / BI engineer |