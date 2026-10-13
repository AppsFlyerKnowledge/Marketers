---
title: "ROI360—cost reporting options for agencies"
excerpt: "Report cost data via cost API (requires a subscription to ROI360 premium solution), and cost by click."
x-zendesk:
  id: 360014054998
  url: https://support.appsflyer.com/hc/en-us/articles/360014054998-ROI360-cost-reporting-options-for-agencies
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Cost sharing for ad networks
  section_id: 6551141756177
  position: 3
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-maytav-avnat, Agencies, ROI360]
  labels: [clicks, cost, Agencies, Partners, ad spend, Xpend]
  promoted: false
  comments_disabled: true
  created_at: '2020-10-04T15:07:34Z'
  edited_at: '2023-03-15T08:18:33Z'
---
## Cost reporting for agencies

Advertisers use AppsFlyer as their source of truth for ROI, billing, and to make marketing budget allocation decisions. To do so, they need to have all the cost information on a single platform. ROI360, an AppsFlyer premium solution, enables advertisers and agencies to collect cost data via API, making it available for viewing using AppsFlyer dashboards and reporting tools.

Cost data can be aggregated via either of the following methods:

- **Cost API**: AppsFlyer pulls data from partners
- **Cost by click:** Networks report cost each time an attribution link is clicked

The following table lists cost aggregation capabilities available with, and without, ROI360.

| Option | Requires ROI360 subscription | Description |
| --- | --- | --- |
| [Cost API](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) | Yes | - Agencies use their ad network API credentials to connect to enable cost API in the AppsFlyer dashboard.<br />- Cost data is reflected according to [agency transparency](/docs/view-agency-data). (For SRNs, this includes clicks and impressions.)<br />- Supports all cost models<br />- Accurate<br />- Data refresh rate: 6 times a day, every four hours. |
| [Cost by click](/docs/cost-reporting-on-the-attribution-link-for-ad-networks)<br />(on the attribution link) | No | - Agencies send their CPI, value, and cost currency on the attribution link. AppsFlyer aggregates the cost.<br />- Data freshness: Near real-time<br />**Limitations:**<br />- Limited to CPI cost model<br />- If the wrong data is sent on the link, it can't be changed retroactively.<br />- Cost reported by click is not available in the SKAdNework dashboard.<br />- Cost by click is less accurate if the advertiser uses SKAdNetwork. |