---
title: PBA media source attribution rules
metadata:
  keywords:
    - media source
    - People Based Attribution
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-09-03T07:30:08Z'
  edited_at: '2024-08-11T07:07:06Z'
  id: 360002386997
  locale: en-us
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360002386997-PBA-media-source-attribution-rules
---
> **At a glance:** Measure the impact of marketing efforts to drive effective website traffic. Which media sources, types, and channels are responsible for visits and conversion events. Ad level metrics available.

![Touchpoints_us-en.png](https://files.readme.io/45c45c9a1b108ea31e450df4c2aaab20482c9829726d9860e55e2c9ca32c401a-360008629017.png)

## Website visits and web events

* **Recognizing a visit:** PBA records a visit according to [visit recognition rules.](/docs/pba-media-source-attribution-rules#visit-recognition-rules)
* **Visit attribution**
  * To determine the media source responsible for bringing a user to the website, PBA analyzes the query parameters on the URL and the HTTP document referrers collected by the web SDK.
  * Rules-based media source determination uses the data collected as detailed in this article. Similarly, media type and media channel are determined.
  * The visit is recorded in <Anchor target="_blank" href="/marketers/vi/docs/pba-raw-data-reports">PBA raw data</Anchor>.
* **Campaign** information is extracted from:
  * Query parameters using the media source
  * Gclid (if available) using <Anchor target="_blank" href="/marketers/vi/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Google ads integration</Anchor>
* **Web event**
  * A web event occurs when a visitor performs an action on the website, for example, product search, product selection, or purchase.
  * Events are attributed to the visit of the most recent non-direct web visit, occurring during a 30-day look-back window.
  * Events are sub-divided into:   
    * **Conversion events**: Significant events designated by the marketer. For example, purchase or registration.
    * **Standard events**: Other events.
  * Learn more about <Anchor target="_blank" href="/marketers/vi/docs/pba-website-attribution-url-best-practices">PBA website attribution URL best practices</Anchor>.

PBA dashboards and raw data reports make use of the attributed media sources, types, channels, and campaigns.

![MediaSource_us-en.png](https://files.readme.io/bcb3e471753809b0fdf1a0e1dc9783002004b1988f4701ab30524c1eb7b9fbfc-360008629057.png)

For ease of understanding, the table that follows contains examples of the determined media source with their type and channel.

| Media source | Media type | Media channel |
| --- | --- | --- |
| Direct | Earned | Direct |
| <ul><li>Social Facebook</li><li>Social X (formerly Twitter)</li></ul> | Owned | Social media |
| <ul><li>Meta ads</li><li>X Ads</li></ul> | Paid | Social media |
| Google search | Earned | Organic search |
| Email | Owned | Email |
| googleadwords\_int | Paid | Ad |
| usatoday.com | Earned | Referral |

## Determining the media source

PBA determines the media source, media type, and media channel in a hierarchical manner. This means determining the relevant media source rule and media source. Afterward, the media type and media channel are determined.

<div id="media-source-rules" />

<Accordion title="Media source rules">

Media source rules as shown in the following table are ranked from high to low priority:

<table><tbody><tr><th>Media source rule </th><th>Resolving the media source </th></tr><tr><td>Prevent self-attribution</td><td><p>To prevent attributing events to the website itself (self-attribution), and other related domains, a <a href="./pba-brand-bundles-and-settings#domain-exclusion" target="_blank">domain exclusion</a> list is used. The list consists of:</p><ul><li>Primary domain: Determined by the URL of the web app included in the brand bundle</li><li>Internal domains: Domains forming part of the brand</li><li>External domains: Payment gateways and payment processing sites set by you and some domains, like PayPal and Stripe, set by AppsFlyer are automatically excluded</li></ul></td></tr><tr><td>pid</td><td><p>Resolve to the pid value in the URL. For some SRNs, resolve the pid to the SRNs commercial name for consistency and clarity. For example, pid=facebook_int resolves to Facebook Ads, twitter_int resolves to Twitter.</p></td></tr><tr><td>Click IDs</td><td><p>Major ad networks, like Google, use click IDs to auto-tag campaigns. Click IDs resolve as follows:</p><ul><li><strong><span>gclid: </span></strong><a href="https://support.google.com/searchads/answer/7342044?hl=en" target="_blank"><span>Google click ID</span></a> resolves to <em>googleadwords_int</em><span>. Note! <em>The GCLID solution is not officially supported by Google, who may deprecate it in the future.</em></span></li><li><strong><span>dclid</span></strong><span>: DoubleClick click ID resolves to <em>doubleclick_int.</em></span></li><li><strong><span>msclkid: </span></strong><a href="http://help.ads.microsoft.com/apex/index/3/en/60000" target="_blank"><span>Bing click ID </span></a>resolves to<span> <em>bingsearch_int</em>.</span></li></ul></td></tr><tr><td>UTM parameters</td><td><strong>UTM custom rules</strong><table><tbody><tr><th>utm_source</th><th>utm_medium</th><th>Media source</th></tr><tr><td>\*</td><td><ul><li>email, mail, e-mail</li><li>Note! If utm_medium contains one of these values, the utm_source is ignored.</li></ul></td><td>Email</td></tr><tr><td>google</td><td>cpc/ppc/paidsearch/search</td><td>googleadwords_int</td></tr><tr><td>google</td><td>cpm/display/banner/video/listing</td><td>doubleclick_int</td></tr><tr><td>dfa / dbm</td><td>cpm</td><td>doubleclick_int</td></tr><tr><td><p>facebook</p></td><td>cpc/ppc/cpm/cpa/paidsocial/paid-social</td><td>Facebook Ads</td></tr><tr><td>bing</td><td>cpc</td><td>bingsearch_int</td></tr><tr><td>yahoo / gemini</td><td>cpc/display/listing</td><td>yahoogemini_int</td></tr><tr><td>twitter</td><td>cpc</td><td>X Ads</td></tr><tr><td>snapchat</td><td>swipe</td><td>snapchat_int</td></tr><tr><td>pinterest</td><td>cpc</td><td>pinterest_int</td></tr></tbody></table><p><span>If there is no custom rule match, the media source resolves to the value of the utm_source parameter.</span><span></span><span></span></p><p><a href="https://en.wikipedia.org/wiki/UTM_parameters" target="_blank"><span>Information about UTM parameters</span></a></p></td></tr><tr><td>Referrer</td><td><span>The referrer is the HTTP source that sent the user to the website. The media source is the domain name of the referrer.</span></td></tr></tbody></table>

</Accordion>

<div id="media-source-type" />

<Accordion title="Media source type">

Marketers usually segment web media sources into three types:

* **Paid:** ad campaigns like display banners, videos, and search ads.
* **Owned:** marketing campaigns that come from owned media meaning, email campaigns, social posts, blogs.
* **Earned:** direct or organic traffic from search engines, referrals, and actual direct traffic.

The media type is determined by referencing the media source rule used in combination with the media source/other parameters.

<table><thead><tr><th>Applicable media source rule</th><th>Media source</th><th>Media type</th></tr></thead><tbody><tr><td colspan="1" rowspan="2"><div>pid</div></td><td><p>The pid rule determined if the media source is: </p><ul><li>Social Facebook</li><li>Social X (formerly Twitter)</li><li>SMS</li><li>Blog</li><li>Email</li></ul></td><td>Owned</td></tr><tr><td>Any other media source</td><td>Paid</td></tr><tr><td>Click ID</td><td><p><span>Determined using a click ID:</span></p><ul><li>gclid</li><li>dclid</li><li>msclkid</li></ul></td><td>Paid</td></tr><tr><td colspan="1" rowspan="2"><div>UTM</div></td><td>UTM custom rules determine the media source</td><td>Paid</td></tr><tr><td>Any other media source</td><td>Owned</td></tr><tr><td rowspan="2">Referrer</td><td><p><span>Referrer domain value is one of the following:</span></p><ul><li>googleads.g.doubleclick.net </li><li>tpc.googlesyndication.com</li></ul></td><td><p>Paid</p></td></tr><tr><td><span>Any other media source </span></td><td><p>Earned</p></td></tr></tbody></table>

</Accordion>

<div id="media-source-channel" />

<Accordion title="Media source channel">

The media channel is determined by rules as listed here.

<table><thead><tr><th>Priority</th><th>Media channel rule</th><th>Values</th><th>Media channel</th></tr></thead><tbody><tr><td rowspan="4">Highest priority</td><td rowspan="4">The media source is one of the listed values</td><td>Direct</td><td>Direct</td></tr><tr><td><ul><li>Google Search</li><li>Yahoo Search</li><li>Bing Search</li></ul></td><td>Organic search</td></tr><tr><td><ul><li>facebook</li><li>twitter</li><li>snapchat</li><li>pinterest</li><li>linkedin</li><li>whatsapp</li></ul></td><td>Social media</td></tr><tr><td>Email</td><td>Email</td></tr><tr><td> </td><td>Media type is Paid</td><td> </td><td><div>Ad</div></td></tr><tr><td> </td><td>Media source determined by referrer</td><td> </td><td>Referral</td></tr><tr><td>Lowest priority</td><td>No other prior condition matched</td><td> </td><td>Other</td></tr></tbody></table>

</Accordion>

<div id="determine-the-campaign" />

<Accordion title="Determine the campaign">

* Campaigns are determined using: 
  * Campaign URL parameters, per media source URL parameters.
  * Gclid click ID and using <Anchor target="_blank" href="/marketers/vi/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Google Ads</Anchor> integration
* If the relevant campaign parameter is not found on the URL, then the campaign is not derived.

| Media source parameter used | Campaign parameter used |
| --- | --- |
| pid | AppsFlyer media source parameters available on the URL are used to populate raw data and the Website Attribution dashboard. Available parameters: af\_c\_id, af\_adset, af\_adset\_id, af\_ad\_id |
| Click ID—gclid | Get via API from Google Ads |
| utm\_source | utm\_campaign |

</Accordion>

## Additional attribution rules

<div id="visit-recognition-rules" />

<Accordion title="Visit recognition rules">

A visit to the website is recorded using the following rules and considering the current session status. An active session is a session having less than 30 minutes of inactivity.

* Don't record a visit if the user came from an <Anchor target="_blank" href="/marketers/vi/docs/pba-brand-bundles-and-settings#domain-exclusion">external excluded</Anchor> domain.
* During an active session: record a visit if the page load includes a media source.
* If there is no active session: record a visit.
* There is no minimum visit time.

**PBA visit recording rules**

![PBA_-_PBA-vist.png](https://files.readme.io/651c3ee4d39832297b7d6dc871aa281f1fa3219264ba264851ad0cc643b8baee-360015532817.png)

</Accordion>

<div id="data-finalization" />

<Accordion title="Data finalization">

* Data finalization:
  * For Web-Assisted Installs, Website Attribution, PBA identifies additional related events during the first 7 days after the conversion. This can change the media source identified as being ultimately responsible for driving the conversion.
  * In the related raw-data reports, the *final\_data* field is false during the initial 7-day period.

</Accordion>

<div data-zendesk-anchors="h_01H936NV7VP8CTE9BZP6D5E7NK=website-visits-and-web-events h_01H936NV7VZHWBDPHFJRFFCPSW=determining-the-media-source h_01H936NV7V6GMWSCHNDMJ205JS=media-source-rules h_01H936NV7W9ZFMET29GY6JTBGN=media-source-type h_01H936NV7W61DB43D3E1MNEJHN=media-source-channel h_01H936NV7WZYE3EKYZ9PX9ZJXW=determine-the-campaign h_01H936NV7WA9WZM4RTQZHD22VV=additional-attribution-rules h_01H936NV7W323HQMG5E6SQFQEN=visit-recognition-rules h_01H936NV7WSB2FMRBPDN936TWM=data-finalization" />
