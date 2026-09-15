---
title: "Measuring attribution with multiple MMPs"
excerpt: "Learn which media sources support attribution measurement when working with multiple MMPs simultaneously and how to compare results."
---
When looking into migrating from another MMP to AppsFlyer, advertisers may wish to simultaneously compare both MMP measurements over the same media sources and campaigns. To do this, the following requirements must be met:

- The tested app must have **both MMP SDKs integrated**
- The media sources must be **configured to support attribution with two MMPs**

However, not all media sources support measurement with more than one MMP.

## Details and limitations of media source measurement

Following are details and limitations of media source measurement when working with multiple MMPs simultaneously.

### Self-reporting networks

| SRN | Details and limitations | Supports measurement |
| --- | --- | --- |
| Apple Search Ads | ASA supports multiple MMP measurements without limitation. When there is an API call request from multiple MMPs, data is sent to the corresponding MMPs. | **✓** |
| DV360 (GMP) | Multiple MMPs are possible, but the campaign setup must have separate line items for each floodlight tracking (Link ID). | **✓** |
| Google Ads | Google Ads supports multiple MMP measurements:<br />- Advertisers can link multiple MMP Link IDs to a single Google Ads account and receive postbacks from each MMP<br />- Google Ads can receive postbacks from multiple MMPs<br />- Multiple MMP performances can be measured<br />**Note:** Once data flows in the new MMP, Google Ads recommends stopping the existing integration. | **✓** |
| Meta ads | Meta ads receives data requests from multiple MMPs. However, they strongly recommend **not** having more than one MMP for the following reasons:<br />- Meta ads can only handle deduplication on installs, not for events. Therefore, events should be sent only from one MMP<br />- When inserting multiple SDKs from MMPs there's a very high probability of issues and secondary errors during the process of deduplication<br />- When a large amount of data is sent to Meta ads, doubled data may be fed into their optimization and measurement systems.<br />Therefore, multiple MMP attribution may be supported for a short term only. | With limitation |
| Snapchat | Transferring data between Snapchat and multiple MMPs is possible. However, it’s recommended to minimize the overlapping migration period. When receiving multiple MMP data, there is no option to optimize by selecting a specific MMP. This means optimization is performed for both MMPs and overlapping data is highly likely. | With limitation |
| TikTok for Business | Sending postbacks to TikTok for Business is supported for one MMP only. When migrating from another MMP, to enable AppsFlyer to attribute conversions to TikTok for Business, you’ll first need to turn off postbacks from the other MMP and then configure AppsFlyer. | x |
| X Ads | X Ads doesn't support multiple MMP integration | x |

### SKAN

Sending [SKAN conversion postbacks](/docs/skan-conversion-studio#skan-conversion-studio-basics) **isn't supported for multiple MMPs**. Only one SDK can trigger sending SKAN postbacks to partners. This means that when more than one SDK is integrated into your app, SKAN postbacks are only sent to one SDK.

### Non-SRN ad networks

MMP attribution links record the engagements of users on non-SRN ad networks and are subsequently used to attribute the engagements that become actual installs. To enable attribution for multiple MMPs simultaneously, the ad network must make sure the following requirements are met:

| Ad network requirement | Details |
| --- | --- |
| Data for a single engagement must be sent to both MMPs | - **Clicks:** As attribution links redirect users to the app store, only one attribution link can be used. We recommend continuing to use the attribution link from the existing MMP while [sending click-attribution data to AppsFlyer](/docs/redirecting-users-to-the-app-store#overview).<br />- **Impressions:** As impressions don't redirect users to the app store, the ad network should send impression data to both MMPs. |
| Received install postbacks should be deduped | Ad networks receive install postbacks from both MMPs. To avoid double charges, the ad network should dedupe one of these postbacks. |
| Received in-app event postbacks should be deduped | When each of the MMPs is configured to send in-app event postbacks, ad networks receive in-app event postbacks from both MMPs. To avoid double attribution resulting in double charges, the ad network should dedupe one of these postbacks. If the ad network can't dedupe double in-app event postbacks, make sure in-app event postbacks are configured in only one MMP. |

### Owned media

As with non-SRN ad networks, attributing installs from owned media requires using MMP attribution links. However, for some types of owned media, such as email lists, SMSs, or QR codes, MMPs can send data on a single engagement only once. AppsFlyer's [mobile web-to-app attribution](/docs/convert-your-mobile-web-visitors-to-app-users) solution enables measuring **installs coming from a website or a landing page**. The advantage of using owned media for comparing MMP attribution is the fact that no install or event deduping is needed.

## Avoiding attribution discrepancies

When MMPs use different attribution models to measure traffic, it may lead to discrepancies. You can minimize discrepancies with these steps:

- Make sure both MMPs use the same timezone for the app. Here's how to [set the app timezone in AppsFlyer](/docs/changing-app-time-zone-settings).
- For non-SRNs and owned media: Make sure to configure the attribution link using the same parameter values. For example, set the same lookback window in both MMPs.
- When comparing the data on the MMPs dashboards or reports, make sure to compare the same criteria, such as traffic from the same date range, and geo.