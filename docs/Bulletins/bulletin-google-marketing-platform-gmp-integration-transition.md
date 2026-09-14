---
title: "Bulletin: Google Marketing Platform (GMP) integration transition"
excerpt: "Learn how to transition from the legacy DoubleClick integration to the new DV360 integration to comply with Google's updated EU user consent policy."
---
As part of preparations for enforcing the [Digital Marketing Act](https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en) (DMA), Google is updating its [EU user consent policy](https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA). AppsFlyer is making the necessary changes to support Google’s policy requirements.

The following Google Marketing Platform (GMP) integrations are currently available:
- [[Legacy] CM360 (DoubleClick)](https://support.appsflyer.com/hc/articles/4410481185297) `doubleclick_int`
- [DV360 (new integration)](/docs/google-marketing-platform-display-video-360-dv360-integration) `dv360_int`

As of September 9th 2025, the legacy `doubleclick_int` integration will be deprecated. If you're using this integration, you'll need to transition to the new DV360 integration to continue running campaigns and measuring them using GMP.

> ❗️ Action required
>
> Transition to the new DV360 `dv360_int` integration as soon as possible, and no later than June 30, 2025.

### Steps to take

Make sure to configure both platforms, GMP and AppsFlyer:

**Configure in GMP**
1. Log in to your CM360 or DV360 account. 

   > 📘 Note
   >
   > Completing the steps in CM360 negates the need for completing them in DV360.

2. Create or reuse your partner attribution link (Link ID) using [these instructions](https://support.google.com/displayvideo/answer/10956727). 

**Configure in AppsFlyer**
1. Complete your DV360 integration in AppsFlyer using [these instructions](https://support.appsflyer.com/hc/articles/360017595598-Google-Marketing-Platform-App-Attribution-Integration-DV360-#integration-procedures). 

   > 📘 Note
   >
   > To maintain data consistency, make sure the configuration is similar to the legacy integration (lookback windows, in-app event postbacks, etc).

2. **Test the new integration:**
   Wait for about a day to confirm the new integration data. You can then disable the legacy integration.

### What you must know

<Accordion title="Media source PID">

After completing the migration, the DV360 media source PID changes from `doubleclick_int` to `dv360_int`.

If you're pulling raw data from AppsFlyer into your BI or any 3rd party analytics tool, consider the change in the media source name.

</Accordion>

<Accordion title="Out-of-store apps">

Apps from unofficial app stores aren't supported in the DV360 integration. The integration relies on a link ID, which is generated for apps obtained through official app stores.

If your app is downloaded from sources outside official app stores, contact your CSM or [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<Accordion title="Attribution data distribution">

When both integrations are active and claim attribution for installs, **attribution is randomly split between them**, with one being the primary source and the other acting as a contributor. This ensures data isn't duplicated. For example, if DV360 is responsible for 100 installs, you might see 70 installs from the legacy integration and 30 from DV360, or 80 installs from DV360 and 20 installs from the legacy integration.

In-app events for installs/re-engagements attributed to the legacy integration remain credited accordingly.

</Accordion>

<Accordion title="Re-engagement">

Re-engagement attribution is supported in the DV360 integration.

</Accordion>

### Field discrepancies

Due to differences between available data fields in the legacy and updated APIs, you may see differences in some AppsFlyer fields, as seen below:

| **AppsFlyer field** | **Legacy field (doubleclick_int)** | **DV360 field (dv360_int)** |
| :--- | :--- | :--- |
| Campaign name | placement_id | line_item_name |
| Campaign ID | placement_id | line_item_id |
| Adset name | ad_id | NA (not supported) |
| Adset ID | ad_id | NA (not supported) |
| Ad name | creative_id | NA (not supported) |
| Ad ID | creative_id | creative_id |