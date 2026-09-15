---
title: "Protect360—FAQ for partners"
excerpt: "Find answers to frequently asked questions by partners about AppsFlyer's Protect360 anti-fraud system, including impression capping and install rejections."
---
At a glance: Find answers to questions frequently asked by partners about Protect360.

## Impression level anomalies

<Accordion title="Why are impressions being capped?">

The AppsFlyer Protect360 system takes into account various parameters when making decisions on capping ad engagements, including but not limited to the volume of impressions, CVR, detected anomaly rate, normal fluctuations in activity, as well as industry and geographic benchmarks. The algorithm is dynamic and updated on an hourly basis, to take into consideration changing trends.

Once the capping mechanism is triggered, Protect360 blocks the ad network’s impressions for the related app within the current 24-hour cycle. This means that any impressions that occur after the threshold is reached are not recorded by AppsFlyer, nor are they eligible for attribution.

A network can avoid surpassing the threshold by stopping campaigns and publishers with unusually high volumes of ad engagements that do not show any impact on performance results.

We recommend taking a look at these articles:

[Impression capping](/docs/protect360-for-integrated-partners#impression-and-click-capping)

[Capping FAQ](/docs/protect360-for-integrated-partners#faq)

</Accordion>

<Accordion title="Why are installs blocked due to click flooding, yet the conversion rate is high?">

Our click-flood algorithms run at various intervals over the course of the day, and whenever the threshold is crossed, based on internal parameters and logic, the publisher’s ad engagements will be ineligible for attribution.

> 📘 Note
>
> Some of our click flood algorithms work across apps, implying that anomalies originating from identical fraudulent sources would be recognized for other advertised apps as well.

We recommend reading: [What is click flooding?](https://www.appsflyer.com/glossary/click-flooding/)

</Accordion>

## Install/in-app event level anomalies

<Accordion title="Why was my test install rejected from attribution?">

AppsFlyer’s anti-fraud detection applies different methodologies across various protection layers, such as single installs and install clusters. Clusters are being reviewed in various aggregations: by publisher, media source, app, and so on. The fraudulent activity is examined using various statistical algorithms and machine learning algorithms that consider each cluster as a whole. Thus, if a cluster is found fraudulent with high statistical significance, all installs in that cluster are considered fraudulent. It's a well-known fraudster tactic to mix some legitimate installs into high volumes of fraudulent activity in the hope that the fraud will be “diluted” enough to avoid triggering blocking mechanisms.

By default, all incoming installs are considered as LIVE traffic - hence to ensure your test install isn't categorized under the Protect360 algorithms, you would need to follow the steps mentioned in [this article](/docs/registering-test-devices) to register your device as a test device before performing a test.

</Accordion>

<Accordion title="What detection methods are used to detect install rejections?">

Please review the "fraud sub reason" associated with the rejection for better clarity. This data is also available in Protect360 reports and on the Protect360 dashboard, subject to access granted by the respective advertiser.

We recommend reading about [Protect360 blocked reasons](/docs/protect360-raw-data-reports#blocked-reasons).

</Accordion>

## Protect360 data visibility and comprehension

<Accordion title="How do I gain visibility into the Protect360 results?">

You can view the results of our detection efforts using the Protect360 dashboard and raw data reports, subject to access granted by the respective advertiser.

We recommend taking a look at these articles:

[Protect360 Dashboard](/docs/protect360-dashboard)

[Protect360 Raw Data](/docs/protect360-raw-data-reports#getting-raw-data-reports)

</Accordion>

<Accordion title="How can I get notified in real time about blocked traffic?">

AppsFlyer provides rejected attribution postbacks to ad networks for every install Protect360 rejects from attribution.

You can enable “rejected postback” by appending “rejected postback” parameters to your postback template by using [Integration Management](https://support.appsflyer.com/hc/articles/360018512658).

</Accordion>

<Accordion title="Why do I see spikes in post-attribution detections?">

Real-time detection before attribution and post-attribution detection both belong to AppsFlyer’s Protect360 anomaly detection mechanism that applies in different time dimensions.

Compared to real-time detection, post-attribution detection relies more on data pointers collected after the install, during which, if anomalies are observed, Protect360 will record anomalous activities and display them under the post-attribution category.

Considering the above, certain detection methods (timestamp_anomalies, behavioral_anomalies, etc.) are more likely to be detected in the post-attribution stage rather than in real time, since the data is inconclusive on the level of an individual install but gains significance when examined for its distribution in statistical analysis.

Learn more about [post-attribution detection](/docs/protect360-anti-fraud-guide#postattribution-detection).

</Accordion>