---
title: "Data Locker reports for API partners"
excerpt: "Learn how API partners can access and configure Data Locker reports, including cohort and advanced aggregated analytics."
---
> 📘 At a glance
>
> Reports listed in this article are available to you (API partners) in your Data Locker. Before we can share the data with you, the advertiser (app owner) must grant you data access as detailed in this article.

To get reports you, the API partner must:

- Ensure that the advertiser has provided you with permission to [access Aggregated analytics reporting](/docs/access-to-aggregated-analytics-tools-for-api-partners#grant-permission-to-a-partner).
- [Set up Data Locker](/docs/data-locker-for-partners#set-up-data-locker). **Note**: Skip steps 3-4.

The following reports are available to API partners: (daily)

- [Cohort unified](/docs/cohort-analytics-via-data-locker) (daily)
- [Cohort user acquisition](/docs/cohort-analytics-via-data-locker) (daily)
- [Cohort retargeting](/docs/cohort-analytics-via-data-locker) (daily)
- [Advanced aggregated (versioned) reports](/docs/advanced-aggregated-reports-in-data-locker) are also available, with better data freshness.

Reports are streamed to the h=23 folder.

### Traits and limitations

| Spec | Remarks |
| --- | --- |
| Agency transparency | Not supported |
| App-specific timezone | Available in advanced aggregated (versioned) reports |
| App-specific currency | Yes |
| Organic data | Available |
| Non-organic data | Available |
| Cost data | Not available |
| Data freshness | - For daily cohort reports:<br />  - Reports are typically available by 10:00 UTC in the h=23 folder of the preceding day. For example, the report for data generated on Monday is in the Monday h=23 folder.<br />  - Exception: Ad revenue events have data freshness of Day 0+3. Meaning, ad revenue events in the Monday report occurred on Saturday.<br />- The first versioned reports are typically available by 06:00 UTC. |

<Cards>
  <Card title="Aggregated analytics tools for API partners" href="/docs/access-to-aggregated-analytics-tools-for-api-partners" icon="fa-solid fa-handshake">
    Learn more about aggregated analytics tools available for API partners.
  </Card>
</Cards>