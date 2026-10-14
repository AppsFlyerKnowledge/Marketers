---
title: ROI360 - onboarding guide
excerpt: >-
  Follow the onboarding instructions in this article to get ROI360 for cost and
  revenue data up and running.
metadata:
  keywords:
    - ROI
    - cost
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2024-05-23T08:36:31Z'
  edited_at: '2026-09-09T15:54:38Z'
  id: 25301111725329
  locale: en-us
  section: Overview
  section_id: 15173289016593
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/25301111725329-ROI360-onboarding-guide
---
![](https://files.readme.io/fa3644980702d735f81d7243f91cb0f0d454bd971e83685ab9759ff7bd925e93-26137252926097.png)

## About ROI360

ROI360 is a suite of unique cost and revenue reporting tools that provide you with the most accurate and fresh data. With the combined cost and revenue insights, you get the complete picture of your return on ad spend (ROAS) and return on investment (ROI), and be able to optimize and improve accordingly.

Follow the onboarding instructions below to get the ROI360 tools for cost, ad revenue, and revenue (in-app purchases and subscription revenue) reporting up and running. Onboarding requires marketers, app developers, and BI developers to complete.

**Tip**! To onboard quickly, prioritize one app and complete all steps to get ROI360 operational. You can focus on cost, ad revenue, or in-app purchase and subscription revenue, but ensure you finish onboarding for one app first.

<div id="cost-onboarding" />

<Accordion title="Cost onboarding">

![](https://files.readme.io/0e7102766b3b7cdba3f301ca89c51edf8e4bd2ec88e09bc912ce3c1436c43fcb-26137252929681.png)

With the ROI360 cost solution, you'll get detailed cost and ROI insights, updated multiple times daily. This enables you to effectively manage campaign cost and view budget allocations across various media sources (ad networks), campaigns, and geos, whether you use ad networks, owned media, or agencies.

After completing the cost onboarding, you'll be able to:

* Get comprehensive, updated overviews of campaign costs with automatic consolidation across all media sources.
* Base your data analysis on the most accurate cost data, updated post-install.
* For ROI360 Advanced users, stream detailed cost data to your BI system up to 4 times a day.
* Manage agency fees and precisely measure overall campaign costs for financial oversight and transparency.

| Task | Purpose | Actions required | Who's involved |
| --- | --- | --- | --- |
| Connect cost API integrations for all ad networks you work with. | Get cost data from every source tied to attribution at the most granular level. | [Enable Cost API](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api) for each ad network in the AppsFlyer UI. **Note**: Before integrating, you need to get the credentials/login info for each ad network. | Marketer |
| Set up Cost ETL reports. (Available to ROI360 Advanced subscribers) | View campaign cost data with the best granularity available per media source, updated up to 4 times per day. | Set up Cost ETL reports for [AWS S3](/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-aws-s3) or [GCS](/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-gcs). | Marketer/BI developer |
| Upload cost data via Cost Import. | Get cost data:<ul><li>For ad networks that don’t report cost via API or click.</li><li>When you use OneLink links to advertise via influencers, etc.</li><li>When you need to correct cost data.</li></ul> | Upload or email cost data files using [Cost Import](/docs/import-cost-data). | Marketer |
| Configure agency fees. | If you use agencies, get the total campaign cost, including the percentage fees agencies charge for traffic. | Create [agency fee rules](/docs/incorporate-agency-fees-into-campaign-costs) for each agency you work with. | Marketer |

</Accordion>

<div id="ad-revenue-onboarding" />

<Accordion title="Ad revenue onboarding">

![](https://files.readme.io/877e4abddd466bbe7dfa31f7fffb2f17fe3e6419f3bf6345e9d619253126b0e6-26137252932369.png)

With the ROI360 ad revenue solution, you'll receive valuable, granular ad revenue data updated multiple times daily.

After completing the ad revenue onboarding, including connecting to the mediation platforms or monetization networks you work with, implementing the ad revenue impression-level SDK API, and sharing data with UA partners, you'll be able to:

* Get accurate and fresh ad revenue data in all AppsFlyer dashboards and reports.
* Stream data to your BI system with granularity and freshness according to your needs.
* Enhance campaign performance by having UA networks optimize based ad revenue metrics.

| Task | Purpose | Actions required | Who's involved |
| --- | --- | --- | --- |
| Decide your ad revenue attribution integration type. | Understand the benefits of each integration type and decide which one best suits your business requirements. | Learn about the different [ad revenue integration types](/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution) and choose 1. | Marketer |
| Connect to all ad revenue mediation and monetization networks you work with. | Get ad revenue data from your mediation or monetization networks. | [Connect ad revenue integrations](/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners) in the AppsFlyer UI. | Marketer |
| Implement the impression-level ad revenue SDK API. | <ul><li>Relevant for SDK-level integration types.</li><li>Get ad revenue data with near-real-time data freshness.</li></ul> | <ol><li>Integrate the [ROI360 AppsFlyer ad revenue SDK API](/docs/integrate-the-roi360-ad-revenue-sdk-api).</li><li>To see ad revenue data in the SKAN dashboard, turn on [SKAdNetwork server-to-server support](/docs/skan-conversion-studio#report-events-by-servertoserver-api).</li></ol> | Developer/Marketer |
| Share ad revenue data with UA partners. | UA ad networks can use the ad revenue data to optimize their UA campaigns. | <ol><li>Learn about the 2 [methods to share ad revenue data with UA partners](/docs/share-ad-revenue-data-with-partners#about-sharing-ad-revenue-data-with-partners).</li><li>[Implement the method](/docs/share-ad-revenue-data-with-partners#procedures) you choose.</li></ol> | Marketer |
| Set up Revenue ETL reports. (Available to ROI360 Advanced subscribers) | Stream and view ad revenue data in your BI with the best granularity available updated multiple times per day. | Set up [ad revenue ETL reports](/docs/revenue-etl-reports). | Marketer/BI developer |

</Accordion>

<div id="revenue-onboarding" />

<Accordion title="In-app purchase and subscription revenue onboarding">

![](https://files.readme.io/811c90ec42465994455fe42be8400b4ebb94ab6d1a5703bc9a77251aba95ed3b-26137252934545.png)

With the ROI360 revenue solution, you gain proactive control over your revenue streams.

After completing the revenue onboarding, including setting up store notifications and implementing purchase SDK APIs for Android and iOS, you will:

* Establish automatic validation and measurement for App Store and Google Play transactions.
* Enjoy seamless, accurate revenue reporting with no further developer efforts required; ROI360 will handle recording all in-app revenue events for you.
* Get accurate revenue measurements to effectively manage strategic growth initiatives across your portfolio.

| Task | Purpose | Actions required | Who's involved |
| --- | --- | --- | --- |
| Implement the ROI360 in-app purchase and subscription revenue solution. | Automatically validate and measure revenue from in-app purchases, auto-renewable subscriptions, and related events that come through either the App Store (iOS) or Google Play (Android). | Follow [these instructions](/docs/purchase-and-subscription-validation-overview) to:<ol><li>Set up integration with Google Play.</li><li>Set up integration with iOS App Store.</li><li>Integrate the AppsFlyer purchase SDK connector.</li><li>Test in-app purchase and subscription revenue measurement.</li><li>Release the app versions with the SDK connector.</li></ol> | Developer/Marketer |
| Set up Revenue ETL reports. (Available to ROI360 Advanced subscribers) | Stream and view revenue data in your BI with the best granularity available updated multiple times per day. | Set up[revenue ETL reports](/docs/revenue-etl-reports). | Marketer/BI developer |

</Accordion>

<div data-zendesk-anchors="overview=about-roi360 h_01HKHGX9JJQQCKF9SDZRSCM1XJ=about-roi360 h_01HYJ8PSPTFR6QH329TBR73AXM=cost-onboarding h_01HYJ8PSPTKBZ60TF7T0EMSCXW=ad-revenue-onboarding h_01HYJ8PSPTWK4SEGVJWG5J86E2=revenue-onboarding" />
