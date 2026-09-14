---
title: "ROI360 - onboarding guide"
excerpt: "Follow the onboarding instructions in this guide to get ROI360 for cost, ad revenue, and in-app purchase and subscription revenue data up and running."
---
**At a glance**: Follow the onboarding instructions in this article to get ROI360 for cost and revenue data up and running.

## About ROI360

ROI360 is a suite of unique cost and revenue reporting tools that provide you with the most accurate and fresh data. With the combined cost and revenue insights, you get the complete picture of your return on ad spend (ROAS) and return on investment (ROI), and be able to optimize and improve accordingly.

Follow the onboarding instructions below to get the ROI360 tools for cost, ad revenue, and revenue (in-app purchases and subscription revenue) reporting up and running. Onboarding requires marketers, app developers, and BI developers to complete.

> 👍 Tip
>
> To onboard quickly, prioritize one app and complete all steps to get ROI360 operational. You can focus on cost, ad revenue, or in-app purchase and subscription revenue, but ensure you finish onboarding for one app first.

### Cost onboarding

With the ROI360 cost solution, you'll get detailed cost and ROI insights, updated multiple times daily. This enables you to effectively manage campaign cost and view budget allocations across various media sources (ad networks), campaigns, and geos, whether you use ad networks, owned media, or agencies.

After completing the cost onboarding, you'll be able to:

- Get comprehensive, updated overviews of campaign costs with automatic consolidation across all media sources.
- Base your data analysis on the most accurate cost data, updated post-install.
- For ROI360 Advanced users, stream detailed cost data to your BI system up to 4 times a day.
- Manage agency fees and precisely measure overall campaign costs for financial oversight and transparency.

| Task | Purpose | Actions required | Who's involved |
| --- | --- | --- | --- |
| Connect cost API integrations for all ad networks you work with. | Get cost data from every source tied to attribution at the most granular level. | [Enable Cost API](https://support.appsflyer.com/hc/articles/360008850257-Connecting-cost-integrations#enable-cost-api) for each ad network in the AppsFlyer UI. **Note**: Before integrating, you need to get the credentials/login info for each ad network. | Marketer |
| Set up Cost ETL reports. (Available to ROI360 Advanced subscribers) | View campaign cost data with the best granularity available per media source, updated up to 4 times per day. | Set up Cost ETL reports for [AWS S3](https://support.appsflyer.com/hc/articles/360008849238-Cost-ETL-granular-campaign-cost-in-a-bucket#set-up-cost-etl-for-aws-s3) or [GCS](https://support.appsflyer.com/hc/articles/360008849238-Cost-ETL-granular-campaign-cost-in-a-bucket#set-up-cost-etl-for-gcs). | Marketer/BI developer |
| Upload cost data via Cost Import. | Get cost data:<br>- For ad networks that don’t report cost via API or click.<br>- When you use OneLink links to advertise via influencers, etc.<br>- When you need to correct cost data. | Upload or email cost data files using [Cost Import](https://support.appsflyer.com/hc/articles/360002516838). | Marketer |
| Configure agency fees. | If you use agencies, get the total campaign cost, including the percentage fees agencies charge for traffic. | Create [agency fee rules](https://support.appsflyer.com/hc/articles/4402103019665) for each agency you work with. | Marketer |

### Ad revenue onboarding

With the ROI360 ad revenue solution, you'll receive valuable, granular ad revenue data updated multiple times daily.

After completing the ad revenue onboarding, including connecting to the mediation platforms or monetization networks you work with, implementing the ad revenue impression-level SDK API, and sharing data with UA partners, you'll be able to:

- Get accurate and fresh ad revenue data in all AppsFlyer dashboards and reports.
- Stream data to your BI system with granularity and freshness according to your needs.
- Enhance campaign performance by having UA networks optimize based ad revenue metrics.

| Task | Purpose | Actions required | Who's involved |
| --- | --- | --- | --- |
| Decide your ad revenue attribution integration type. | Understand the benefits of each integration type and decide which one best suits your business requirements. | Learn about the different [ad revenue integration types](https://support.appsflyer.com/hc/articles/217490046-Ad-revenue-attribution-guide#integration-types-for-ad-revenue-attribution) and choose 1. | Marketer |
| Connect to all ad revenue mediation and monetization networks you work with. | Get ad revenue data from your mediation or monetization networks. | [Connect ad revenue integrations](https://support.appsflyer.com/hc/articles/217490046-Ad-revenue-attribution-guide#connect-to-ad-revenue-integrated-partners) in the AppsFlyer UI. | Marketer |
| Implement the impression-level ad revenue SDK API. | - Relevant for SDK-level integration types.<br>- Get ad revenue data with near-real-time data freshness. | 1. Integrate the [ROI360 AppsFlyer ad revenue SDK API](https://support.appsflyer.com/hc/articles/4416353506833).<br>2. To see ad revenue data in the SKAN dashboard, turn on [SKAdNetwork server-to-server support](https://support.appsflyer.com/hc/articles/4403727223185#report-events-by-servertoserver-api). | Developer/Marketer |
| Share ad revenue data with UA partners. | UA ad networks can use the ad revenue data to optimize their UA campaigns. | 1. Learn about the 2 [methods to share ad revenue data with UA partners](https://support.appsflyer.com/hc/articles/24100803679761#about-sharing-ad-revenue-data-with-ua-partners).<br>2. [Implement the method](https://support.appsflyer.com/hc/articles/24100803679761-ROI360-Sharing-ad-revenue-data-with-UA-partners#procedures) you choose. | Marketer |
| Set up Revenue ETL reports. (Available to ROI360 Advanced subscribers) | Stream and view ad revenue data in your BI with the best granularity available updated multiple times per day. | Set up [ad revenue ETL reports](https://support.appsflyer.com/hc/articles/16464765619985). | Marketer/BI developer |

### In-app purchase and subscription revenue onboarding

With the ROI360 revenue solution, you gain proactive control over your revenue streams.

After completing the revenue onboarding, including setting up store notifications and implementing purchase SDK APIs for Android and iOS, you will:

- Establish automatic validation and measurement for App Store and Google Play transactions.
- Enjoy seamless, accurate revenue reporting with no further developer efforts required; ROI360 will handle recording all in-app revenue events for you.
- Get accurate revenue measurements to effectively manage strategic growth initiatives across your portfolio.

| Task | Purpose | Actions required | Who's involved |
| --- | --- | --- | --- |
| Implement the ROI360 in-app purchase and subscription revenue solution. | Automatically validate and measure revenue from in-app purchases, auto-renewable subscriptions, and related events that come through either the App Store (iOS) or Google Play (Android). | Follow [these instructions](/docs/purchase-and-subscription-validation-overview) to:<br>1. Set up integration with Google Play.<br>2. Set up integration with iOS App Store.<br>3. Integrate the AppsFlyer purchase SDK connector.<br>4. Test in-app purchase and subscription revenue measurement.<br>5. Release the app versions with the SDK connector. | Developer/Marketer |
| Set up Revenue ETL reports. (Available to ROI360 Advanced subscribers) | Stream and view revenue data in your BI with the best granularity available updated multiple times per day. | Set up [revenue ETL reports](https://support.appsflyer.com/hc/articles/16464765619985). | Marketer/BI developer |