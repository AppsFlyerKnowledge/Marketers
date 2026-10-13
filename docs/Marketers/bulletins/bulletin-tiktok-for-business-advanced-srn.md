---
title: "Bulletin: TikTok for Business—advanced SRN"
table_of_contents: false
x-zendesk:
  id: 7925111265041
  url: https://support.appsflyer.com/hc/en-us/articles/7925111265041-Bulletin-TikTok-for-Business-advanced-SRN
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 42
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-07-26T12:27:56Z'
  edited_at: '2025-09-09T06:46:47Z'
---
> 🚧 Important Transition Notice
>
> On January 30, 2023, the new **TikTok for Business—advanced SRN** integration `tiktokglobal_int` was added, while the **Legacy** **TikTok for Business** integration `bytedanceglobal_int` is gradually phasing out and will be deprecated by Sept 9, 2025. This transition is handled by TikTok and they will notify all customers when to delete their old integration. **To avoid any data loss, make sure to keep both integrations live during the transition phase**.

| | |
| --- | --- |
| **Headline** | AppsFlyer now supports TikTok For Business as an advanced Self-Reporting Network (SRN) |
| **Effective Date** | - January 30, 2023: New `tiktokglobal_int`<br />- Sept 9, 2025: Legacy `bytedanceglobal_int` deprecation |
| **Where is it changing** | The TikTok For Business integration page in Active Integrations. |
| **Required actions** | - [Set up the new integration](/docs/tiktok-for-business-advanced-srn-integration-setup). The new PID for TikTok For Business is `tiktokglobal_int`.<br />- If you have an existing integration with the Legacy TikTok For Business `bytedanceglobal_int`, to avoid data loss, don't delete it until your **transition date** (see the row below). |
| **Transition date** | Once you’ve enabled the new integration and TikTok For Business have tested that it works as expected, they will contact you to notify you of the exact date of your transition from the legacy `bytedanceglobal_int` integration to the new integration. This **may take up to 45 days**, during which the dashboards and reports continue showing data from the legacy integration.<br />After the transition date, the dashboards and reports show data from the new `tiktokglobal_int` integration.<br />**Note:** For new integrations that aren't transitioning from the legacy integration, the data is immediately shown on the dashboards and reports. |
| **What does this new integration mean?** | - **Dashboards and reports**  - After your transition date, all TikTok For Business new conversions will be attributed to the new PID `tiktokglobal_int`.<br />  - Clicks and impressions recorded before enabling the new integration will be attributed to `bytedanceglobal_int`.<br />- **Aggregated clicks and impressions**<br />  <br />  After your transition date, clicks and impressions won't be available via raw-level reports; they'll be available in reports containing aggregated data, after [enabling the API connection with TikTok](/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions).<br />  <br />  **Note:**  - Make sure to enable the API connection while setting up the integration.<br />  - The transition process requires a significant shift in AppsFlyer measurement reporting, so click and impression data will not be immediately available for the new integration.<br />- **Cost data**  - **Duplicated cost data:** If both the new [`tiktokglobal_int`](/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions) and the legacy `bytedanceglobal_int` [Cost integrations](/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions) are enabled simultaneously, **cost data may appear twice**. You can avoid this by making sure only **one Cost integration is turned on**.<br />      <br />      However, when enabling the new cost integration, cost data from 5 days preceding the transition day is automatically collected. This means the new integration is expected to show duplicated cost data for those 5 days. **For example**, if the old cost integration was disabled on January 15th and the new cost integration was enabled on the same day, duplicate cost data is seen in the new cost integration between January 10th to 14th, even though it was only enabled on January 15th.<br />  - **To make sure only one Cost integration is turned on:**    1. On the **transition day**, go to the **Cost** tab of the **legacy integration** and **turn off** the toggle.<br />    2. Then go to the **Cost** tab of the **new integration** and **turn on** the toggle.<br />  - After your transition date, cost data will be associated with the new PID. To view older cost data, include the legacy PID in any of the dashboard filtering options.<br />  - During the transition period, install numbers might be split between the two integrations for a few days, while the cost data will show everything. Note that during this time, KPIs relying on this data (like eCPI and ROI) might not be accurate.<br />    <br />    <Image src="https://files.readme.io/802e43a872253691d15cdf68feeaf59b7d21f348380819a38742be5e70987b51-18535286024337.png" alt="cost integration on.png" /><br />- **SKAN postbacks**<br />  <br />  After your transition date, all SKAN postbacks will be associated with the new integration `tiktokglobal_int`.<br />- **Retargeting campaigns**<br />  <br />  When migrating to the new integration, the **Re-engagement** toggle is **turned off by default**, regardless of its state in the legacy integration. For [retargeting campaigns](/docs/retargeting-attribution-guide), **to ensure continuity, make sure to** **turn on** the **Re-engagement** toggle in the new integration **.** |
| **Example illustrating the process** | - **Day 1 (enablement day):** Enable the new TikTok integration from the integration tab only. Keep the Cost integration off. Although both integrations are on, the new integration isn't yet active and there's no attribution to it.<br />- **Days 2-10 (TikTok review period. May take up to 45 days):** TikTok is testing the new integration. After approving the data, they notify you of the transition date. In this example, it'll be on day 11. <br />  <br />  In the meantime, dashboards and reports show attribution for the legacy integration only. If Cost is turned on in both integrations, they'll both show double cost data. To avoid this, it's better to keep Cost off for the new integration.<br />- **Day 11 (transition day):** TikTok makes the switch and starts attributing to the new integration. For about a week from the transition day (until all old clicks expire), install attribution data is split between both integrations:   - For the new integration, TikTok sends data as an SRN. <br />  - For the legacy integration, AppsFlyer may still attribute old clicks from prior to transition day.<br />- **Day 18 (post-transition phase)**: No more install attribution for the legacy integration, only for the new integration. <br />  <br />  For the next 60 days, attribution for in-app events may continue coming in for the legacy integration. Therefore, to allow AppsFlyer to continue sending postbacks for these events, it's recommended to keep the legacy integration on (from the integration tab). <br />  <br />  If the Cost integration is turned off for the new integration, you can now turn it on. To avoid seeing double cost data, turn off Cost from the legacy integration.<br />- **Day 78 (final transition):** Turn off the legacy integration. TikTok now acts as an SRN and no longer needs in-app event postbacks. <br />  <br />  Although the legacy integration is turned off, if you haven't yet turned off the legacy Cost integration, you'll continue seeing duplicate cost data in the new integration. |

<Cards>
  <Card title="Successfully transition to the new Advanced SRN integration with TikTok" href="https://appsflyer.showpad.com/share/XB6r4QA1TN0wN63kqmslA" icon="fa-solid fa-right-left">
    Learn how to transition to the new Advanced SRN integration with TikTok.
  </Card>
</Cards>