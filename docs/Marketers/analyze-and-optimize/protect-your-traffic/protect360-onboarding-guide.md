---
title: Protect360 onboarding guide
excerpt: >-
  Quickly and effectively safeguard your marketing investments by following this
  step-by-step onboarding guide to maximize your Protect360 value within just 6
  weeks.
metadata:
  keywords:
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-04-21T09:58:52Z'
  edited_at: '2026-01-08T11:54:02Z'
  id: 34554022072209
  locale: en-us
  section: Protect your traffic
  section_id: 6551015912465
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/34554022072209-Protect360-onboarding-guide
---
## **Onboarding timeline and what to expect?**

This guide outlines a phased onboarding approach of 6 weeks:

* **Setup (weeks 1–3)**: Integrate and validate Protect360.
* **Optimization (weeks 3–5)**: Optimize based on initial insights.
* **Reconciliation (weeks 5–6)**: Reconcile fraud data with ad partners.
* **Advanced protection (week 6+) [Optional]**: Enable advanced fraud protection layers.

## **About Protect360**

Protect360 is an advanced fraud protection solution designed to detect, prevent, and respond to ad fraud. Powered by AI and with real-time detection, it helps block fraud, reduce wasted spending, and protect your marketing from threats such as click injection, fake installs, and bots. It enables precise control and full transparency through features like validation rules and Fraud Protection Studio.

<div id="setup-weeks-1-3" />

<Accordion title="Setup (weeks 1–3)">

In this step, the focus is to send in-app data to AppsFlyer, set up the basic settings for Fraud Protection, and align your BI terms with AppsFlyer.

**In-App event data**

There are two ways to send in-app events data to AppsFlyer: SDK and Server-to-Server (S2S). Depending on the method used, there may be some action required:

* **SDK**: No action required.
* **Server-to-Server (S2S)**: Ensure events are sent via API3. [Learn more about how to do this here.](/docs/bulletin-upgrading-the-appsflyer-s2s-api)

> 📘 **Note**
>
> If unsure which one you use, confirm with your development or marketing operations teams

#### **Fraud Protection Studio settings**

Fraud Protection Studio offers a way to evaluate the impact and value of the different layers of AppsFlyer’s fraud protection solution. It enables you to clearly distinguish between fraud detection and enforcement.

Understanding these differences and available options is key to making informed decisions:

* **Implemented** (default): Automatically blocks fraudulent activity in real-time or marks it as post-attribution fraud if detected post-install. This is ideal if immediate fraud prevention aligns with your goals.
* **Tagged**: Fraud is detected and tagged but remains valid for attribution, allowing you to analyze and review without automatically blocking. Choose this if you prefer flexibility and deeper initial analysis before implementing.

> 📘 **Note**
>
> You can switch ([Admin only](/docs/user-management)) between **Implemented** and **Tagged** modes anytime to match your evolving business objectives. [Learn more here](/docs/beta-fraud-protection-studio#key-concepts).

![](https://files.readme.io/70bf87550e949fed4898270f731424e948a24f7cf2cff39e81ba44473af94189-35506628777105.png)

Tip: At this stage, when your team is getting familiar with Protect360, we strongly recommend visiting the [**App detection evaluation**](/docs/beta-fraud-protection-studio#app-detection-evaluation) card within the Fraud Protection Studio to test and understand these settings on the app level.

#### **Data connection setup**

You can export Protect360 data in three ways: [Raw Data Report](/docs/protect360-raw-data-reports#about-protect360-raw-data-reports), [Pull API](/docs/protect360-raw-data-reports#pull-api), or [Data Locker](/docs/protect360-raw-data-reports#data-locker). Whichever way you choose, it is important to configure your data connections properly to ensure accurate fraud data reporting and effective analysis.

![](https://files.readme.io/d6a96db3fd8ffd3ed6f3f8abb680b4f3778a457142166d69e1ade7fe3263709e-35506660373393.png)

> 📘 **Important!**
>
> In order to get the full value of Protect360, export the [Post-attribution report](/docs/protect360-raw-data-reports#postattribution-reports) every 8th of every month, so you can reconsolidate with partners.

#### **How to display hijacked installs correctly in your BI**

For greater alignment and granularity of fraud protection data within your systems, you may u**se Raw Data Reports, Pull APIs, or Data Locker to properly view hijacked installs within your BI.**

#### **Raw Data Report**

To display hijacked installs properly in your BI:

1. Look for the **Rejected Reason Value** field.
2. This field will be populated with one of the following:
   1. Blank, organic, contributor1, contributor2, etc.
3. Inform your BI team on the meaning of each, so they can align the terms and their implications.

* Blank - Not hijacked
* Organic - Change attribution to organic
* Contributor1, contributor2, contributor3, etc. - Correct attribution to the specified media source.

> 📘 **Note**
>
> To get more insight about your **Tagged** data, you can view the 4 raw data reports:
>
> * Tagged Installs
> * Tagged post attribution installs
> * Tagged in-app events
> * Tagged post attribution in-app events

![](https://files.readme.io/70d33b5c4359f839da8d46c4b07baf277148fc4d5c6ebc7a3e8b2d600bd7c5fc-35506628785169.png)

#### **Pull API**

To display hijacked installs properly in your BI:

4. Look for the **Rejected Reason Value** field.
5. This field will be populated with one of the following:
   1. Blank, organic, contributor1, contributor2, etc.
6. Inform your BI team on the meaning of each so they can align the terms and their implications.

* Blank - Not hijacked
* Organic - Adjust attribution to organic
* Contributor1, contributor2, contributor3, etc. - Correct attribution to the specified media source.

#### **Data Locker**

To display hijacked installs properly in your BI:

7. Look for the **validation\_reason\_value** field.
8. This field will be populated with one of the following:
   1. Blank, organic, contributor1, contributor2, etc.
9. Inform your BI team on the meaning of each so they can align the terms and their implications.

* Blank - Not hijacked
* Organic - Adjust attribution to organic
* Contributor1, contributor2, contributor3, etc. - Correct attribution to the specified media source.

#### **Validation rules**

Validation rules allow you to add a business logic layer to your fraud protection, tailored to your marketing strategy. With validation rules, you can define which installs are considered valid or invalid based on a variety of parameters across multiple use cases.

Contact your Customer Success Manager or Account Manager to learn more about best practices recommended for your vertical.

> 📘 **Note**
>
> For the rules to be as effective as possible, it’s recommended to review your UA / marketing / media buying strategy and assess which types of installs or app events match your efforts, to allow or block per your needs. For example, if you do not promote your app in country (GEO) X, you can create a rule to automatically block any such activity arriving from GEO X. You can create multiple rules to align protection to your marketing strategy.

#### **Working with dashboards**

The [Protect360 dashboard](/docs/protect360-dashboard) provides a visual overview of your fraud data, allowing you to investigate further and better understand fraud detection and its impact on your activities.

![](https://files.readme.io/4717e1f00d832a9808ac6469d89bf3a87f6701afb24a47f3b4393e4e393111ee-35506628785809.png)

</Accordion>

<div id="optimization-weeks-3-5" />

<Accordion title="Optimization (weeks 3–5)">

#### **Campaign optimization**

In this step, it is time to optimize your campaign to ensure you are getting the most out of Protect360. To do this, you should:

* See [best practices](/docs/protect360-onboarding-guide#best-practices)
* [Review your Fraud Protection settings](/docs/protect360-onboarding-guide#review-your-fraud-protection-settings)

#### Best practices

* Combine real-time and post-attribution data to evaluate campaign performance based on quality (retention, in-app events, etc) and fraud.
* Optimize campaigns based on site\_id or subsite\_id.
* Analyze partner-specific fraud rates and types.

#### Review your Fraud Protection settings

Review your [Fraud Protection Studio settings](/docs/protect360-onboarding-guide#fraud-protection-studio-settings) to ensure they still align with your objectives.

> 📘 **Note**
>
> **Tagged** installs are a subset of valid. Switch to **implemented** mode to block in real-time according to the Protect360 detection

</Accordion>

<div id="reconciliation-weeks-5-6" />

<Accordion title="Reconciliation (weeks 5–6)">

#### **Fraud data reconciliation**

After implementing Protect360 and accumulating several weeks of fraud detection data, it's time to reconcile your fraud insights with your ad partners.

This critical step helps ensure that you and your partners are aligned on campaign performance, fraud detection methods, and accuracy.

Download your [post-attribution data](/docs/protect360-anti-fraud-guide#postattribution-detection) and collaborate closely with your ad partners to cross-reference fraud metrics. This reconciliation helps identify discrepancies, resolve disputes proactively, and build transparency. Find out how to reconcile fraud data with ad partners [here](/docs/protect360-anti-fraud-guide#fraud-reconciliation-with-ad-networks).

</Accordion>

<div id="advanced-protection-setup-week-6--optional" />

<Accordion title="Advanced protection setup (week 6+) [optional]">

#### **Advanced Security Module**

Available exclusively for Protect360 clients, the Advanced Security Module is designed for high-trafficked apps. It adds a vital security layer to your Android SDK, validating network requests in real-time to block spoofed installs and manipulated traffic.

By filtering out unauthorized signals at the source, it helps reduce app store discrepancies, strengthens attribution accuracy, and protects your data from sophisticated cyber fraud.

Reach out to your CSM or send an email to `<hello@appsflyer.com>`

</Accordion>

<div data-zendesk-anchors="what-to-expect=onboarding-timeline-and-what-to-expect h_01JSBWNSH94Q2FBXJ5JSB2JKQ6=onboarding-timeline-and-what-to-expect h_01JSBWNSHDZ8J3B70KYEG2T03X=about-protect360 setup-weeks-1%E2%80%933=setup-weeks-1-3 h_01JSBWJJMHSF6YQ5PDEWE0YTN5=setup-weeks-1-3 h_01JVVK5Z1HWN0TXKZVNNGK1CBV=note h_01JSY4SNK5X23DBVD374FV12FG=fraud-protection-studio-settings h_01JVVK5Z1HZAVV3ZEA1AM7KVAY=note-1 h_01JSY4SNK57K77TBXZB92QPBKA=data-connection-setup h_01JVVK5Z1H0TZH02S76M7JRKWQ=important h_01JVVJBVB4FRATEHVZ2Q7EWC54=how-to-display-hijacked-installs-correctly-in-your-bi h_01JWDAV3K7JF8ATZP88D4NQRW4=raw-data-report h_01JVVK5Z1HB5AVVF3XV5Q9KNGA=note-2 h_01JWDAV8GC5N1859AD1PMEQXH9=pull-api h_01JWDAVEVDAJD47WQYY0FNSPE9=data-locker h_01JSY4SNK5HAG08PAJQEPB7MQ4=validation-rules h_01JVVK5Z1H05XX8BXECMXAJ4J7=note-3 h_01JSY4SNK50RHSQ95E1E2ZK068=working-with-dashboards optimization-weeks-3%E2%80%935=optimization-weeks-3-5 h_01JSBWJJMH4YW52GSBE6639BP4=optimization-weeks-3-5 h_01JV255GGVBY8XGQS28F0QZRVH=campaign-optimization h_01JV6WFR7MN2X8KTN7RMTXQ5KX=best-practices h_01JV6WGDRP200GHN6MJNZJ5MQE=review-your-fraud-protection-settings h_01JVVK5Z1HXPM2G6HAMTYV7MY5=note-4 reconciliation-weeks-5%E2%80%936=reconciliation-weeks-5-6 h_01JSBWJJMH1481TJW2EQMF118Q=reconciliation-weeks-5-6 h_01JV25RP3VAJBCEWWK2TEZFKB2=fraud-data-reconciliation advanced-protection-setup-week-6-%5Boptional%5D=advanced-protection-setup-week-6--optional h_01JSBWJJMHZQNYE1N0W2BSJ37X=advanced-protection-setup-week-6--optional h_01JV260Y9M3M6CC48854YHQ01S=advanced-security-module" />
