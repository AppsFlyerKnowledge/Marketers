---
title: "Cost-sharing options for ad networks"
excerpt: "Compare the different cost-sharing methods available to AppsFlyer ad network partners, including InCost API, Cost API, Cost Import, and Cost by click."
x-zendesk:
  id: 360012893658
  url: https://support.appsflyer.com/hc/en-us/articles/360012893658-Cost-sharing-options-for-ad-networks
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Cost sharing for ad networks
  section_id: 6551141756177
  position: 0
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-maytav-avnat, ROI360, Ad Networks]
  labels: [clicks, Partner, cost, Ad Networks, Partners, ad spend, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2020-09-07T13:50:24Z'
  edited_at: '2024-05-22T12:07:38Z'
---
At a glance: Compare cost-sharing methods available to AppsFlyer ad network partners.

## Sharing cost with AppsFlyer and advertisers

Advertisers use AppsFlyer as their source of truth for ROI, billing, and to make marketing budget allocation decisions. For networks to be visible, sharing cost data with AppsFlyer is a must. Networks with no cost data appear at the bottom of the AppsFlyer dashboard list.

Ad networks share cost with AppsFlyer using any of the following:

- **InCost API**: Push data to AppsFlyer
- **Cost API**: AppsFlyer pulls data
- **Cost Import**: Cost data files are uploaded/sent to AppsFlyer
- **Cost by click:** Networks report cost each time an attribution link is clicked

### Cost badge for ad networks

<Image src="https://files.readme.io/6b660b68b932802f7982a3beb3a155ecc350de1b4cb3baede6e84ef0d704388c-360011247338.jpg" alt="CostBadge.jpg" />

- A cost badge displays in the [partner details page](/docs/partner-integrations#partner-details-and-performance) highlighting partners using the InCost or Cost API.
- The badge certifies that the partner as a cost-capable partner.
- Internal analytics and extensive user surveys show that advertisers are always on the lookout for new partners. Those with a cost badge are more likely to stand out, as advertisers want to understand their marketing performance based on ROI analysis.

### Reporting cost options available to ad networks

| Option | Qualify for a cost badge | Option characteristics |
| --- | --- | --- |
| [InCost API](/docs/incost-api-for-ad-networks) | **✓** | The ad network has full ownership of when to set up InCost reporting. <br />InCost has the following features: <br />- Supports all cost models<br />- Accurate and reliable<br />- Fully automated<br />- Ad network partner controls:<br />  <br />  <br />  - Data upload scheme<br />  - When to upload (data freshness rate)<br />- The advertiser grants permission in the AppsFlyer dashboard to the partner to upload cost data<br />**Limitation**: <br />AppsFlyer agency accounts aren't supported. |
| Cost API | **✓** | - Supports all cost models<br />- Accurate<br />- Partner retains some control over their cost data in AppsFlyer<br />- Supports cost for agency accounts in AppsFlyer<br />- Advertisers provide their partner credentials in the AppsFlyer dashboard<br />- Data refresh rate: 6 times a day, every four hours<br />**Limitation**:<br />Integration is subject to AppsFlyer priorities. |
| [Cost Import](/docs/cost-import-for-ad-networks)<br />(file upload) | No | - The ad network partner:  - Uploads data manually if it does not have engineering resources to automate<br />  - Controls when to upload data<br />  - Retains some control over their cost data in AppsFlyer<br />  - Integration is per app. The advertiser grants permission in the AppsFlyer dashboard to the partner to upload cost data.<br />  - Matching to attribution data is based on campaign name (not campaign ID)<br />**Limitation**: <br />- AppsFlyer agency accounts aren't supported<br />- Risk of failure if the upload is automated via email |
| [Cost by click](/docs/cost-reporting-on-the-attribution-link-for-ad-networks)<br />(on the attribution link) | No | - Quick solution for CPI campaigns<br />- Near real-time<br />- Cost by click can be less accurate if the advertiser uses SKAdNetwork<br />**Limitation**:<br />- Limited to CPI cost model<br />- If the wrong data is sent on the link, it can't be changed retroactively<br />- Retargeting not supported<br />- Cost reported by click is displayed in the SKAdNework dashboard when available |