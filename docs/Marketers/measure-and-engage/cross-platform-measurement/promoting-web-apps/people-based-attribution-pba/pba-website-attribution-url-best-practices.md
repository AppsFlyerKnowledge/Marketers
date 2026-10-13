---
title: "PBA website attribution URL best practices"
excerpt: "Learn the best practices for structuring website attribution URLs to achieve optimal campaign granularity and accurate reporting in AppsFlyer."
x-zendesk:
  id: 6313062676497
  url: https://support.appsflyer.com/hc/en-us/articles/6313062676497-PBA-website-attribution-URL-best-practices
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  position: 12
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, Cross-Platform Measurement]
  labels: [Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2022-05-23T05:29:27Z'
  edited_at: '2026-05-05T06:53:16Z'
---
Best practices to attribute your website attribution campaigns with the best campaign granularity available.

## PBA website attribution URLs

To get the best campaign granularity results combined with the most accurate attribution in your website attribution data, populate URLs (links), bringing users to your website using the practices detailed in this article.

### URL parameters—group and priority

The AppsFlyer website attribution solution supports several campaign parameter classes. The classes are ranked in priority as follows:

- [Highest priority] PID
- Click IDs from specific channels like Google, DoubleClick, and Microsoft
- [Lowest priority] UTM

The [PBA media source attribution rules](/docs/pba-media-source-attribution-rules) determine how a given user is attributed. Parameter classes are ranked by priority. If more than one parameter class is found on a link, the class having the highest priority is awarded the attribution.

#### Supported parameters

| # | Parameter | Used for | Parameter class | Available in the Dashboard | PBA raw data field |
| --- | --- | --- | --- | --- | --- |
| 1 | pid | Media source | PID | Y | media\_source |
| 2 | c | Campaign name | PID | Y | campaign |
| 3 | af\_c\_id | Campaign ID | PID | Y | campaign\_id |
| 4 | af\_adset | Adset name | PID | Y | Extract from query\_params |
| 5 | af\_adset\_id | Adset ID | PID | Y | Extract from query\_params |
| 6 | af\_ad | Ad name | PID | Y | Extract from query\_params |
| 7 | af\_ad\_id | Ad ID | PID | Y | Extract from query\_params |
| 8 | utm\_source | Media source | UTM | Y | media\_source |
| 9 | utm\_medium | Media type | UTM | Y | media\_type |
| 10 | utm\_campagin | Campaign | UTM | Y | campaign |

## URL parameter best practices

### Selecting URL parameters

Each parameter class functions in the context of a silo. As such, if you need URLs with multiple classes, the URL must have the relevant parameters of each class. By doing so, your reporting granularity is optimized.

The use of parameters of multiple classes is illustrated in the context of Meta ads as follows:

- **PID group**:  `www.website.com?pid=facebook_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}`
- **UTM group**: `www.website.com?utm_source=facebook&utm_medium=paidsocial&utm_campaign={{campaign.name}}`
- If you combine classes but include only some of the required parameters, AppsFlyer might not provide the full granularity. For example, if you use `www.website.com?utm_source=facebook&c={{campaign.name}}` the following occurs:
  - AppsFlyer uses the UTM class because there is no PID class and determines the media source using utm\_source.
  - However, the campaign can't be determined since _c=_ is part of the PID class, but pid isn't included.
  - To solve this, assuming you need the utm\_source for other purposes, consider this option: `www.website.com?pid=facebook_int&c={{campaign.name}}&utm_source=facebook`. With this structure, AppsFlyer uses the PID class to identify the media source. Other PID parameters, such as c=, can be included and the utm\_source is disregarded because it has a lower priority.

### Implement dynamic URLs using ad network macros

Use network macros (AKA valuetrack params) to save time when building templates and applying URL parameters for paid campaigns.

Networks use different macros to populate the parameters in the URL. Consequently, you must check ad network documentation to verify that you use the macros correctly. For example, if you want to pass the campaign ID in the af\_c\_id, you can avoid hard-coding the actual campaign ID for each URL, and just use the macros:

- Google Adwords: `www.website.com?af_c_id={campaignid}`
- Meta ads: `www.website.com?af_c_id={{campaign.id}}`
- Pinterest ads: `www.website.com?af_c_id={campaignid}`
- Snapchat ads: `www.website.com?af_c_id={{campaign.id}}`
- Microsoft ads (Bing): `www.website.com?af_c_id={campaignid}`

### Consistent case within parameters

Parameter values are case-sensitive. For example, utm\_source=channel1 and utm\_source=CHANNEL1 are regarded as different media sources. As such, verify that you are consistent with regard to the letter case.

### Use Google Ads integration to automate granularity

In the case of Google Ads campaigns, you can get campaign granularity by integrating PBA with your [Google Ads](/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba) account. This ensures that your data is populated with all campaign hierarchy data without the need for PID or UTM parameters on the URL.

## Common URL parameter mistakes to avoid

### Question marks

- Use only one question mark between the URL landing page and the parameters
- There should be no other question marks used in the URL

For example,  `www.website.com?parameters`

Example **incorrect** uses:

`www.website.com??parameters`

`www.website.com?parameter1?parameter2`

### Anchor signs

Anchor signs (#) should not be used in the URL. Use of an anchor sign in a URL can result in the parameters after the sign form not loading and not being collected by our web SDK.