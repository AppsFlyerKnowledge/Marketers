---
title: "About the Enhanced attribution model"
excerpt: "The Enhanced attribution model improves attribution accuracy by attributing only eligible clicks and impressions when click and impression flooding is detected on the device."
---
The Enhanced attribution model combats engagement flooding by only considering signals that reflect real user engagement for attribution. When AppsFlyer detects engagement patterns that indicate flooding, AppsFlyer considers eligible clicks and impressions only. As a result, attribution is based on the last eligible click, which is not necessarily the most recent click.

The model works continuously in the background and applies to all relevant traffic without requiring any action from advertisers or partners.

## How the Enhanced attribution model helps

Enhanced attribution model helps advertisers, ad networks, and partners in the following ways:

- **Advertisers**
  - Increases attribution accuracy across both acquisition and retargeting flows.
  - Enables confident scaling in high-growth channels without compromising attribution quality.
  - Improves spend protection by basing decisions on more reliable attribution data.
  - Helps identify and prioritize high-value channels and partners.

- **Ad networks and partners**
  - Ensure attribution is based on real user activity.
  - Improve the accuracy of reporting and optimization decisions.
  - Maintain consistent and fair attribution competition.
  - Reduce the effect of artificially increased engagement volumes.

## How the Enhanced attribution model works

Here’s how it works:

1. AppsFlyer receives engagement records from multiple media sources, such as clicks or impressions.
2. When AppsFlyer detects a flooding pattern during the attribution process, an additional model helps select eligible engagements.

## Where Enhanced attribution data appears in AppsFlyer reports

You can view Enhanced attribution data in the following channels:

### Raw data reports

**Total candidates for attribution** is a metric displayed in raw data reports. It indicates the number of engagements that would have entered the attribution competition before enhanced attribution and Protect360 fraud detection logic are applied. Because contributor reporting reflects post-filtering results, the total number of candidates can be significantly higher than the number of contributors.

This metric can indicate potential engagement flooding and helps advertisers understand engagement volume and source patterns. It does not represent the number of devices or users.

> 📘 Note
>
> The metric can also be greater than zero for organic installs, as organic engagements may still enter the attribution competition prior to validation.

### Protect360 dashboards and reports

- Average engagements per compromised and non-compromised installs
- Attribution trends segmented by compromised and non-compromised installs

> 📘 Note
>
> Compromised data starts to appear in the Protect360 dashboard only after an app is added to Enhanced attribution. However, compromised and non-compromised data can still be shown for historical timeframes from before the app was added to the feature.