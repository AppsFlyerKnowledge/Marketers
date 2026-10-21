---
title: Report generation quotas (rate limitations)
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2014-05-01T12:55:30Z'
  edited_at: '2026-10-14T09:37:22Z'
  id: 207034366
  locale: en-us
  section: Account management
  section_id: 6551191075473
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207034366-Report-generation-quotas-rate-limitations
---
> **At a glance:** A quota (rate limitation) mechanism limits the number of reports you can generate per day through both Pull API and the data export pages.

## Rate limits for reports

The quota limits the number of reports you can generate per day per report type. The quota varies according to your subscription plan.

**Principles:**

* **Agencies:** Agencies and advertisers have separate Pull API quotas. The quota applies per report, per day, and per app, in the same way for both. For reports from the export data page, agencies and advertisers also have separate quotas. If you often reach the quota limit, contact your Account Executive.
* **Ad networks:** Reports that ad networks generate don't count toward the advertiser quota.
* **Day:** Quotas apply per calendar day, starting at 00:00 UTC.

### Aggregated and analytics reports

| Data delivery tool | Quota |
| --- | --- |
| Pull API aggregate | <ul><li>Up to 2 days in the date range:<ul><li>Maximum of 1 call per minute per app per report</li></ul></li><li>3+ days date range, the following limits apply:<ul><li>Maximum 120 calls per day, per account</li><li>24 calls per day, per app</li></ul></li></ul> |
| Aggregated export data page | Unlimited |
| Master API | Unlimited |
| Cohort API | 60 calls per minute per account |
| SKAN aggregate reports | 10 calls per minute per account |

### Raw data

* A separate quota applies to each reporting tool, namely the Pull API and the raw data export page.
* Agencies and advertisers have separate Pull API quotas. Agency-generated reports don't count against the advertiser quota. The only exception is when an agency uses the advertiser's API token instead of their own, in which case the requests are indistinguishable from advertiser requests and count against the advertiser quota. For reports from the export data page, agencies and advertisers also have separate quotas.
* API pull quotas apply per:
  * Report
  * Day
  * App-level
  * Account-level
* For advertisers, the quotas depend on your AppsFlyer subscription. The quotas also apply to reports that require a premium subscription.
* The daily quotas for Pull API raw data reports and ad network postback reports are as indicated in the tables that follow.

For examples, see the FAQ below.

#### Pull API raw data daily quota

Pull API raw data reports have the following daily quotas:

| Report type | App-level daily quota (reports) | Account-level daily quota (reports) |
| --- | --- | --- |
| Installs | 24 | 120 |
| In-app events | 12 | 60 |

> 📘 **Note**
>
> The quotas apply per report type, so each report type has a separate quota.

#### Ad network postback reports daily quota

Ad networks can pull the following postback report types:

| Postback group | Report type  <br />(each report type has a separate quota) | App-level daily quota | Account-level daily quota |
| --- | --- | --- | --- |
| Postbacks for attribution | <ul><li>Installs</li><li>Retargeting conversions</li></ul> | 24 | 120 |
| Postbacks for in-app events | <ul><li>In-app events</li><li>In-app events retargeting</li></ul> | 12 | 60 |

## FAQ

* Q: For a given app, can I generate 24 organic install reports using Pull API and another 24 reports using the raw data export page?  
  A: Yes. The quota per reporting tool is separate.
* Q: For a given app, using the raw data export page, can I generate 24 organic install reports, 24 non-organic install reports, and 24 retargeting conversion reports?  
  A: Yes. The quota per report type is separate.
* Q: I have 25 apps in my account. Can I generate 10 organic install reports for each app?  
  A: No. This results in a total of 250 reports, which exceeds the account-level quota of 120.
* Q: Do agency-generated Pull API reports count against the advertiser's quota?  
  A: No. Agencies and advertisers have separate Pull API quotas. Agency-generated reports don't count against the advertiser quota. The only exception is when an agency uses the advertiser's API token instead of their own, in which case those requests count as advertiser requests.

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/data-availability-windows">Data availability windows</Anchor>

<div data-zendesk-anchors="h_01H9JNZFPSVXPKMEVR1ZR6PSYG=rate-limits-for-reports h_01H9JNZFPS62A5CFWSXVPN8XM5=aggregated-and-analytics-reports h_01H9JNZFPSPYWBB2MCZV2R2KX1=raw-data h_01M4WW4PAZ64FXVR1QPKE53DS7=pull-api-raw-data-daily-quota h_01M4WW4PAZFMX9X0DFX1E6F9M0=note h_01H9JNZFPSYXZNW81BZTRDS576=ad-network-postback-reports-daily-quota h_01H9JNZFPT76RAV8JBTY2K75V4=faq h_01HE7SW3VWRNVY1WFB4YCSAVY6=see-also" />
