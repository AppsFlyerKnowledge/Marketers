---
title: Signal Hub guide
metadata:
  keywords:
    - Premium
    - Marketers
    - Signal Hub
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gilad-katan
    - Marketers
    - Signal Hub
  created_at: '2025-09-16T10:56:07Z'
  edited_at: '2026-08-19T09:03:23Z'
  id: 39096485642001
  locale: en-us
  section: Signal Hub
  section_id: 41021664993425
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/39096485642001-Signal-Hub-guide
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**At a glance:** The AppsFlyer Signal Hub enables marketers to create privacy-safe audiences with real-world purchase signals and activate them instantly across major media platforms.

<Embed title="Signal Hub guide" typeOfEmbed="youtube" url="https://www.youtube.com/embed/B71XCosnTXo" providerUrl="https://www.youtube.com" />

## About Signal Hub

The AppsFlyer Signal Hub is an advanced, privacy-safe solution empowering brands to gain access to high-value first-party data of leading brands, including leading finance companies, to unlock user insights far beyond their own data. By enriching audiences with real-world purchase signals, marketers can identify high-value users earlier, personalize campaigns based on proven spending behavior, and activate audiences instantly across major media platforms, such as Meta, Google, and TikTok.

Using AppsFlyer clean room infrastructure and integrations with identity resolution providers, everything is privacy-safe, requires no custom setup, and is fully measurable through omnichannel attribution.

**With Signal Hub, you can:**

* **Reach high-value customers earlier**  
  Identify and engage customers based on their actual spending behavior before they interact with your product.
* **Enrich and activate instantly**  
  Use purchase signals as standalone insights, or combine them with your AppsFlyer first-party data or external data connected to Signal Hub, to build enriched audiences and activate them across all major media platforms.
* **Skip the heavy lifting**  
  Gain access to purchase signals instantly. No setup, engineering effort, or legal teams working overtime required.
* **Rely on built-in privacy**   
  Activate securely in a clean room environment using hashed, pseudonymized identifiers. No raw data is ever moved, shared, or exported.
* **Gain full-funnel clarity**  
  Measure the impact of enriched segments on installs, purchases, retention, SKU-level measurement, and revenue through AppsFlyer's full-funnel, omnichannel measurement.

## Get started using Signal Hub

**To get started using Signal Hub, follow the steps below:**

**<span id="h_01J5WC8Z4J352AHSDTRCEP2W9H"></span>Prerequisite:** An AppsFlyer <Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">account</Anchor>. To access Signal Hub, contact your CSM or write to hello@appsflyer.com

<Accordion title="Step 1. Accept the collaboration invite">

After signing up for Signal Hub, AppsFlyer will arrange a brief meeting to discuss the specifics of your collaboration, including which purchase signals will be included. Afterwards, you'll receive a collaboration invite via email. Click the link in the email, log in to your account, and accept the collaboration.

</Accordion>

<Accordion title="Step 2. Add your first-party data to the collaboration (Optional)">

If you want to build audiences using your first-party data, you can <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-create-a-collaboration#associate-or-manage-sources">associate your existing AppsFlyer data</Anchor> (your SDK data) with the collaboration you were invited to.

Additionally, you can [connect external data sources](/docs/signal-hub-guide#add-your-own-custom-data-to-signal-hub-optional), such as your CRM or other relevant systems, directly to your clean room. Data remains in place and is never moved or copied. AppsFlyer is granted read-only access only.

</Accordion>

<Accordion title="Step 3. Build high-intent audiences and activate them">

Once you have all the relevant data sources associated with your collaboration, you can start <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-build-and-activate-audiences">building an enriched audience</Anchor> using the purchase signals data source. When done, you're ready to send them for activation.

</Accordion>

<Accordion title="Step 4. Measure campaign results">

After running your campaigns, check out the results in your AppsFlyer dashboards, such as the <Anchor target="_blank" href="/marketers/docs/my-dashboards#dashboard-templates">Performance Analysis dashboard</Anchor>.

</Accordion>

## Use cases

The use cases for Signal Hub are nearly endless. Here are a few industry-specific examples.

<Accordion title="Gaming">

A mobile gaming publisher wants to acquire players likely to spend shortly after installing. By combining demographic attributes (e.g., males aged 18–34) with in-app purchase history, they can create high-value segments and activate them across ad networks. This leads to stronger Day 1 ROAS and reduced CPIs.

</Accordion>

<Accordion title="Hospitality">

A hotel chain plans to drive bookings for a Valentine's Day promotion. By combining marital status, recent flight bookings, and travel-related spend, they can build a high-intent audience of couples likely to book getaways. Activating this audience across media channels boosts engagement and increases reservations.

</Accordion>

<Accordion title="Connected TV (CTV)">

A consumer electronics brand wants to promote new smart TVs. By leveraging streaming platform data (such as device ownership, subscription purchases, and engagement with entertainment apps), they can identify premium households and run highly targeted campaigns. This improves conversions for big-ticket items.

</Accordion>

## Additional information

See additional information to understand and guide your usage of Signal Hub.

<Accordion title="How Signal Hub works">

Signal Hub connects marketers with real-world purchase signals in a privacy-safe way. No raw data is ever moved, shared, or exported.

* **Aggregated purchase data**   
  Signal Hub partners with leading brands (e.g., Mastercard), which share aggregated purchase data at the ZIP+4 level (about 10–20 households). For example, Mastercard might show that "70% of consumers in this ZIP+4 purchased at Shoprite," offering real-world spending insights without user-level data.
* **Identity resolution**   
  Since ZIP+4 data can't be used directly for ad targeting, integrated AppsFlyer identity resolution partners translate it into privacy-safe hashed identifiers, such as hashed emails, that media platforms can recognize. [Learn more](/docs/signal-hub-guide#understand-identity-enrichment)
* **Audience building and activation**   
  Marketers can combine these purchase signals with their own first-party data inside AppsFlyer's clean room to create enriched audience segments. Once activated, the audiences are securely matched and delivered to media platforms, while AppsFlyer measures performance across channels.

</Accordion>

<Accordion title="Understand identity enrichment">

Signal Hub provides an enrichment metric to help you understand how much of the aggregated ZIP+4 data can be resolved into identifiers usable for activation. Identity enrichment refers to this process: matching aggregated purchase signal data (at the ZIP+4 level) to privacy-safe identifiers that can be used for audience activation.

In the data source shared to the collaboration, the **Identity enrichment** percentage shows how much of the provider's ZIP+4 data was successfully matched to privacy-safe identifiers that can be used for activation.

<Image alt="Identity enrichment.png" src="https://files.readme.io/fce84b456682695e1896a99749d08ba26ff885cf3e3c16ba661b2c93ff7fa8c9-40890476677521.png" width="1090px" />

* **Data provider:** The number of ZIP+4 groups shared by the purchase signal provider (e.g., Mastercard).
* **Identity data:** The number of those ZIP+4 groups that the identity resolution partner successfully matched to hashed identifiers (for example, hashed emails).
* **Estimated data pool:** The estimated number of users represented by the combined and enriched ZIP+4 data. This total reflects the audience size available for activation after matching.

The enrichment percentage shown next to "Customer data" (in the image above) represents the overlap between these two data sets, indicating how much of the provider's data is ready for use in AppsFlyer audience building and activation.

</Accordion>

<Accordion title="Data Clean Room (DCR) and Signal Hub">

The Signal Hub functions as the central point for data collaboration, including audience creation and activation. It relies on the advanced technology of the <Anchor target="_blank" href="/marketers/docs/data-clean-room-overview">Data Clean Room (DCR)</Anchor> to guarantee data privacy and security across all collaboration and audience management processes.

</Accordion>

<Accordion title="Connect external data sources to Signal Hub (Optional)">

You can add your own custom first-party data to Signal Hub as external data sources to build accurate audiences based on what you know about your customers. To do so,**follow these steps:**

1. <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">Set up your cloud services</Anchor>.
2. <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-create-and-manage-sources">Create your data sources</Anchor>.
3. <Anchor target="_blank" href="/marketers/docs/data-collaboration-platform-dcp-add-connections">Connect your cloud services to AppsFlyer</Anchor>.

</Accordion>

<div data-zendesk-anchors="introduction=about-signal-hub h_01J174QBCMPNBXTVVPZ9WD1C1R=about-signal-hub get-started-using-dcp=get-started-using-signal-hub h_01JF5ECVHPW0FS8E4KVK4WDDNE=get-started-using-signal-hub h_01K59AKK88MNMA1CBJKEQ9WJ0T=use-cases h_01K59BYQ59VDW3W13G50W401E1=additional-information" />
