---
title: "PBA media source attribution rules"
excerpt: "Learn how AppsFlyer People-Based Attribution (PBA) determines the media source, type, and channel responsible for website visits and conversion events."
---
Measure the impact of marketing efforts to drive effective website traffic. Which media sources, types, and channels are responsible for visits and conversion events. Ad level metrics available.

![Touchpoints_us-en.png](https://files.readme.io/45c45c9a1b108ea31e450df4c2aaab20482c9829726d9860e55e2c9ca32c401a-360008629017.png)

## Website visits and web events

- **Recognizing a visit:** PBA records a visit according to [visit recognition rules.](https://support.appsflyer.com/hc/articles/360002386997#visit-recognition-rules)
- **Visit attribution**  - To determine the media source responsible for bringing a user to the website, PBA analyzes the query parameters on the URL and the HTTP document referrers collected by the web SDK.
  - Rules-based media source determination uses the data collected as detailed in this article. Similarly, media type and media channel are determined.
  - The visit is recorded in [PBA raw data](https://support.appsflyer.com/hc/articles/360001917778).
- **Campaign** information is extracted from:
  - Query parameters using the media source
  - Gclid (if available) using [Google ads integration](https://support.appsflyer.com/hc/articles/360011487937)
- **Web event**
  - A web event occurs when a visitor performs an action on the website, for example, product search, product selection, or purchase.
  - Events are attributed to the visit of the most recent non-direct web visit, occurring during a 30-day look-back window.
  - Events are sub-divided into:
    - **Conversion events**: Significant events designated by the marketer. For example, purchase or registration.
    - **Standard events**: Other events.
  - Learn more about [PBA website attribution URL best practices](https://support.appsflyer.com/hc/articles/6313062676497).

PBA dashboards and raw data reports make use of the attributed media sources, types, channels, and campaigns.

![MediaSource_us-en.png](https://files.readme.io/bcb3e471753809b0fdf1a0e1dc9783002004b1988f4701ab30524c1eb7b9fbfc-360008629057.png)

For ease of understanding, the table that follows contains examples of the determined media source with their type and channel.

| Media source | Media type | Media channel |
| --- | --- | --- |
| Direct | Earned | Direct |
| - Social Facebook<br />- Social X (formerly Twitter) | Owned | Social media |
| - Meta ads<br />- X Ads | Paid | Social media |
| Google search | Earned | Organic search |
| Email | Owned | Email |
| googleadwords\_int | Paid | Ad |
| usatoday.com | Earned | Referral |

## Determining the media source

PBA determines the media source, media type, and media channel in a hierarchical manner. This means determining the relevant media source rule and media source. Afterward, the media type and media channel are determined.

### Media source rules

Media source rules as shown in the following table are ranked from high to low priority:

| Media source rule | Resolving the media source |
| --- | --- |
| Prevent self-attribution | To prevent attributing events to the website itself (self-attribution), and other related domains, a [domain exclusion](https://support.appsflyer.com/hc/articles/360000646498#domain-exclusion) list is used. The list consists of:<br />- Primary domain: Determined by the URL of the web app included in the brand bundle<br />- Internal domains: Domains forming part of the brand<br />- External domains: Payment gateways and payment processing sites set by you and some domains, like PayPal and Stripe, set by AppsFlyer are automatically excluded |
| pid | Resolve to the pid value in the URL. For some SRNs, resolve the pid to the SRNs commercial name for consistency and clarity. For example, pid=facebook\_int resolves to Facebook Ads, twitter\_int resolves to Twitter. |
| Click IDs | Major ad networks, like Google, use click IDs to auto-tag campaigns. Click IDs resolve as follows:<br />- **gclid:** [Google click ID](https://support.google.com/searchads/answer/7342044?hl=en) resolves to _googleadwords\_int_. Note! _The GCLID solution is not officially supported by Google, who may deprecate it in the future._<br />- **dclid**: DoubleClick click ID resolves to _doubleclick\_int._<br />- **msclkid:** [Bing click ID](http://help.ads.microsoft.com/apex/index/3/en/60000) resolves to _bingsearch\_int_. |
| UTM parameters | **UTM custom rules**<br /><br />\| utm\_source \| utm\_medium \| Media source \|<br />\| --- \| --- \| --- \|<br />\| \* \| - email, mail, e-mail<br />- Note! If utm\_medium contains one of these values, the utm\_source is ignored. \| Email \|<br />\| google \| cpc/ppc/paidsearch/search \| googleadwords\_int \|<br />\| google \| cpm/display/banner/video/listing \| doubleclick\_int \|<br />\| dfa / dbm \| cpm \| doubleclick\_int \|<br />\| facebook \| cpc/ppc/cpm/cpa/paidsocial/paid-social \| Facebook Ads \|<br />\| bing \| cpc \| bingsearch\_int \|<br />\| yahoo / gemini \| cpc/display/listing \| yahoogemini\_int \|<br />\| twitter \| cpc \| X Ads \|<br />\| snapchat \| swipe \| snapchat\_int \|<br />\| pinterest \| cpc \| pinterest\_int \|<br /><br />If there is no custom rule match, the media source resolves to the value of the utm\_source parameter.<br /><br />[Information about UTM parameters](https://en.wikipedia.org/wiki/UTM_parameters) |
| Referrer | The referrer is the HTTP source that sent the user to the website. The media source is the domain name of the referrer. |

### Media source type

Marketers usually segment web media sources into three types:

- **Paid:** ad campaigns like display banners, videos, and search ads.
- **Owned:** marketing campaigns that come from owned media meaning, email campaigns, social posts, blogs.
- **Earned:** direct or organic traffic from search engines, referrals, and actual direct traffic.

The media type is determined by referencing the media source rule used in combination with the media source/other parameters.

| Applicable media source rule | Media source | Media type |
| --- | --- | --- |
| pid | The pid rule determined if the media source is:<br />- Social Facebook<br />- Social X (formerly Twitter)<br />- SMS<br />- Blog<br />- Email | Owned |
| Any other media source | Paid |
| Click ID | Determined using a click ID:<br />- gclid<br />- dclid<br />- msclkid | Paid |
| UTM | UTM custom rules determine the media source | Paid |
| Any other media source | Owned |
| Referrer | Referrer domain value is one of the following:<br />- googleads.g.doubleclick.net<br />- tpc.googlesyndication.com | Paid |
| Any other media source | Earned |

### Media source channel

The media channel is determined by rules as listed here.

| Priority | Media channel rule | Values | Media channel |
| --- | --- | --- | --- |
| Highest priority | The media source is one of the listed values | Direct | Direct |
| | | - Google Search<br />- Yahoo Search<br />- Bing Search | Organic search |
| | | - facebook<br />- twitter<br />- snapchat<br />- pinterest<br />- linkedin<br />- whatsapp | Social media |
| | | Email | Email |
| | Media type is Paid | | Ad |
| | Media source determined by referrer | | Referral |
| Lowest priority | No other prior condition matched | | Other |

### Determine the campaign

- Campaigns are determined using:
  - Campaign URL parameters, per media source URL parameters.
  - Gclid click ID and using [Google Ads](https://support.appsflyer.com/hc/articles/360011487937) integration
- If the relevant campaign parameter is not found on the URL, then the campaign is not derived.

| Media source parameter used | Campaign parameter used |
| --- | --- |
| pid | AppsFlyer media source parameters available on the URL are used to populate raw data and the Website Attribution dashboard. Available parameters: af\_c\_id, af\_adset, af\_adset\_id, af\_ad\_id |
| Click ID—gclid | Get via API from Google Ads |
| utm\_source | utm\_campaign |

## Additional attribution rules

### Visit recognition rules

A visit to the website is recorded using the following rules and considering the current session status. An active session is a session having less than 30 minutes of inactivity.

- Don't record a visit if the user came from an [external excluded](https://support.appsflyer.com/hc/articles/360000646498#domain-exclusion) domain.
- During an active session: record a visit if the page load includes a media source.
- If there is no active session: record a visit.
- There is no minimum visit time.

**PBA visit recording rules**

![PBA_-_PBA-vist.png](https://files.readme.io/651c3ee4d39832297b7d6dc871aa281f1fa3219264ba264851ad0cc643b8baee-360015532817.png)

### Data finalization

- Data finalization:
  - For Web-Assisted Installs, Website Attribution, PBA identifies additional related events during the first 7 days after the conversion. This can change the media source identified as being ultimately responsible for driving the conversion.
  - In the related raw-data reports, the _final\_data_ field is false during the initial 7-day period.