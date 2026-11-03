---
title: About traffic source resolution
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T13:46:22Z'
  edited_at: '2026-10-15T07:23:49Z'
  id: 43518064765201
  locale: en-us
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/43518064765201-About-traffic-source-resolution
---
> **At a glance:** Use traffic source resolution to identify the initial media source, campaign, and channel for each web visit, using the URL parameters and referrer data available at landing page load. This gives attribution the traffic-source context it needs to attribute downstream web events, including the user-acquisition event, accurately.

## What is traffic source resolution?

For web attribution, the landing page load (**web visit**) is the user’s first engagement with the website. AppsFlyer relies on information available at the time, such as URL parameters and referrer data, to identify the user's media source, campaign, and channel.

This process, known as **traffic source resolution**, identifies and resolves media source and campaign information from URL parameters. AppsFlyer captures and prioritizes these parameters to determine the initial traffic source context for a visit.

Traffic source resolution is a **pre-attribution process**. The resolved parameters may be overridden later during <Anchor target="_blank" href="/marketers/id/docs/web-performance-measurement-overview#the-web-performance-measurement-flow">the attribution process</Anchor>.

The role of traffic source resolution does not end with the visit. Its outcome provides the traffic-source context that the attribution process later uses to attribute subsequent web events, including the user-acquisition event.

Understanding the mechanics of traffic source resolution is essential for constructing accurate URLs. To learn how to create a well-structured URL, see <Anchor target="_blank" href="/marketers/id/docs/choose-attribution-parameters-for-landing-page-urls">Choose attribution parameters for landing page URLs</Anchor>.

## The traffic source resolution flow

Traffic source resolution follows a structured, multi-step flow that progressively builds the attribution context for each web visit. Each step contributes a specific layer of information, from capturing the visit itself to classifying the traffic for reporting. The data used by the traffic source resolution flow is captured either by the web SDK or Web S2S.

The flow consists of the following steps:

1. [Visit recording](#step-1-visit-recording): Captures the user’s arrival on the website and logs a visit event, even when the traffic source is not yet known. This makes sure that all eligible user entries are measured before the attribution logic is applied.
2. [Media source resolution](#step-2-media-source-resolution): Analyzes URL parameters and referrer data to identify the platform or partner that drove the visit, or determines that the visit is organic.
3. [Campaign resolution](#step-3-campaign-resolution): Resolves granular campaign details associated with the identified media source, enabling detailed performance analysis.
4. [Channel classification](#step-4-channel-classification): Assigns each visit to a high-level traffic channel based on the resolved media source, providing a standardized view for reporting and analysis.

## Step 1: Visit recording

Visit recording is the initial step in the Web Performance Measurement flow. It happens before media source resolution and attribution, serving as a preprocessing layer that captures raw user activity.

The logic works in two stages. First, it classifies the **referrer** (the domain the user came from before landing on your site). Then, based on the referrer type, it evaluates the user's session state and the presence of media source information to decide whether to record the visit.

#### Stage 1: Referrer classification

AppsFlyer classifies the referrer into one of three types:

* **External excluded** (for example, a payment processor or any domain you've excluded)
* **Internal excluded** (for example, your own subdomains or login flows)
* **Else** (all other referrers)

#### Stage 2: Session evaluation and visit recording

Based on the referrer type, AppsFlyer evaluates the session state and decides whether to record the visit:

* **External excluded:** The visit is never recorded.
* **Internal excluded:** Referrer-based attribution is suppressed, because the referrer isn't a real acquisition source.
  * If there's an active session (a session is considered inactive after 30 minutes of inactivity; otherwise, it's active), the visit isn't recorded.
  * If there's no active session, the visit is recorded, but the referrer is treated as a self-referral and ignored. The visit is recorded as organic unless the URL includes attribution parameters (UTM, PID, click ID, etc.).
* **Else:**
  * If there's no active session, could you record the visit? A fresh session counts as a new visit, regardless of other conditions.
  * If there's an active session and a non-direct media source is present (UTM, PID, click ID, etc.), record the visit. This revisit may trigger a retargeting conversion (re-engagement), which is used to attribute subsequent events.
  * If there's an active session and no media source information is present, don't record a new visit within that session.

<Image alt="traffic resolution flow" src="https://files.readme.io/d5f807d5ced5ed9a90a41cda0f38fe7ffef0b81c321bae90ad410076b484c810-47195479783953.png" width="1494px" />

## Step 2: Media source resolution

The media source resolution process determines if a visit is:

* **Non-organic:** A specific attribution source is found.
* **Organic:** No attribution source is identified (for example, the user typed the URL directly or used a bookmark).

During the media source resolution process, AppsFlyer determines the origin of a web visit by evaluating parameters extracted from the landing page URL path and query string.

For best results, use AppsFlyer-specific parameters, such as `pid` and `af_campaign`, which provides the highest level of granularity and control. AppsFlyer also recognizes industry-standard parameters, such as UTM tags and click IDs, allowing you to get started immediately without changing your existing ad measurement setup.

AppsFlyer follows a priority order to resolve the media source. The process stops as soon as a source is successfully identified. The media source resolution process consists of the following steps:

<Accordion title="1. Exclude domains">

First, AppsFlyer checks if the visit comes from a domain on your **Exclude list**. If the domain is excluded (for example, your internal domain or a payment processor like PayPal), the visit is automatically ignored or classified as **Organic.**

For more information about how to specify the excluded domains when adding a web app to AppsFlyer, see <Anchor target="_blank" href="/marketers/id/docs/configure-web-performance-measurement-settings#excluded-domains">Excluded domains</Anchor>.

</Accordion>

<Accordion title="2. AppsFlyer PID (partner ID)">

If the domain is not excluded, AppsFlyer looks for the `pid=` parameter in the URL.

* If found, the media source is taken directly from this value.
* <span id="social-media-partners"></span>The following social media partners use specific display labels instead of the raw URL parameter value.

| URL parameter (PID) | Media source display name |
| --- | --- |
| `pid=iossearchads_int` | Apple Search Ads |
| `pid=facebook_int` | Facebook Ads |
| `pid=metaweb_int` | Facebook Ads |
| `pid=twitter_int` | Twitter |
| `pid=twitterweb_int` | Twitter |
| `pid=googleads_int` | googleadwords\_int |
| `pid=tiktokweb_int` | tiktokglobal\_int |
| `pid=snapweb_int` | snapchat\_int |

</Accordion>

<Accordion title="3. UTM parameters">

If no PID is found in the URL, AppsFlyer evaluates the `utm_source` and `utm_medium` parameters to identify the media source. The combination of these two fields determines the resulting resolution.

#### **How UTM logic works**

* In most cases, AppsFlyer determines the media source by extracting the raw value of `utm_source` and using it as the media source.
* If `utm_medium` is `email`, `mail`, or `e-mail`, the media source automatically resolves to `e-mail`.
* If `utm_medium` is present and is not an email value, AppsFlyer checks the value against specific custom mapping rules (see the mapping table below).
* If `utm_medium` is missing or doesn’t match any custom rule, AppsFlyer falls back to using `utm_source` as the media source.

#### **UTM mapping rules**

| utm\_source | utm\_medium | Media source |
| --- | --- | --- |
| Google, googleads\_int | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | googleadwords\_int |
| Google | cpm / display / banner / video / listing | dv360\_int |
| dfa / dbm / dcm / doubleclick | cpm | dv360\_int |
| Facebook / FB / Meta, metaweb\_int, facebook\_int | cpc / ppc / cpm / cpa / paidsocial / paid-social / paid\_social / paid | Facebook Ads |
| Bing / microsoft / ms | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | bingsearch\_int |
| Yahoo / gemini | cpm / display / listing | yahoogemini\_int |
| twitter, twitter\_int, twitterweb\_int | cpc / ppc / paid / paidsocial / paid-social / paid\_social | Twitter |
| Snapchat / snap, snapweb\_int | swipe / cpc / ppc / paid / paidsocial / paid-social / paid\_social | snapchat\_int |
| pinterest | cpc / ppc / paid / paidsocial / paid-social / paid\_social | pinterest\_int |
| tiktok, tiktokweb\_int | cpc / ppc / paid / paidsocial / paid-social / paid\_social | tiktokglobal\_int |
| iossearchads\_int | any / none | Apple Search Ads |
| chatgpt.com | paid: cpc / ppc / cpm / paid / paid\_search / paidsearch / display / banner / video | openai\_int |
| chatgpt.com | none of the above* | chatgpt\_organic\_aeo (channel: aeo) |
| perplexity | any / none | perplexity\_organic\_aeo (channel: aeo) |

*\*If an* `oppref` *click ID is present, AppsFlyer skips this row and resolves the visit from* `oppref` *instead (see Click IDs).*

</Accordion>

<Accordion title="4. Click IDs">

If neither a PID nor UTM parameters are present in the URL, AppsFlyer attempts to identify the media source using **Click IDs**. These are unique identifiers automatically appended to URLs by specific ad networks.

AppsFlyer uses the following Click ID mapping to attribute the visit:

| Click ID parameter | Resolved media source |
| --- | --- |
| `gclid`, `wbraid`, or `gbraid` | googleadwords\_int |
| `msclkid` | bingsearch\_int |
| `twclid` | Twitter |
| `vmcid` | yahoogemini\_int |
| `sccid` | snapchat\_int |
| `li_fat_id` | linkedin\_int |
| `ttclid` | tiktokglobal\_int |
| `tbclid` | taboola\_int |
| `ob_click_id` | outbrain\_int |
| `dicbo` | outbrain\_int |
| `yclid` | yandex\_int |
| `rdt_cid` | reddit\_int |
| `epik` | pinterest\_int |
| `oppref` | openai\_int |

> 📘 **Note**
>
> * AppsFlyer doesn’t use fbclid for traffic source resolution because Meta appends it to both paid and organic Facebook clicks. To attribute traffic to Meta, include pid=facebook\_int or set utm\_source to the relevant Meta source value.
> * The dclid parameter is not used for media source resolution. dclid is a Campaign Manager 360 (CM360) identifier that can appear alongside other click IDs, such as fbclid (Facebook) or ttclid (TikTok), when CM360 is used. Using dclid alone can result in the wrong resolution.

</Accordion>

<Accordion title="5. HTTP referrer">

If no query parameters (PID, UTMs, or Click IDs) are found in the URL, AppsFlyer uses the `http_referrer` to identify the traffic source. This relies on an internal parsing mechanism that extracts the domain host and maps it to a media source.

#### **The parsing mechanism**

To identify the source, AppsFlyer cleans the referrer string by:

1. Stripping the URL down to the **host**
2. Removing **domain suffixes** (top-level domains like `.com`, `.org`, or extensions like `.co.uk`)
3. Removing **domain prefixes** (such as `www.`, `m.`, `l.`, or `lm.`)

*Example: A referrer of* `www.mywebsite.com?param=example` *resolves to a media source of* `mywebsite`.

#### **Referrer mapping rules**

| If the domain host contains… | Resolved media source |
| --- | --- |
| `mail.` or `outlook.` | Email |
| `t.co` | twitter |
| `googleads.g.doubleclick.net` | googleadwords\_int |
| `tpc.googlesyndication.com` | dv360\_int |

#### **Search engine mapping**

| If the domain host contains… | Resolved media source |
| --- | --- |
| `google.` | google\_organic\_seo |
| `search.yahoo` | yahoo\_organic\_seo |
| `bing.com` | bing\_organic\_seo |
| `ask.com`, `de.ask.com`, `uk.ask.com` | ask\_organic\_seo |
| `duckduckgo.com` | duckduckgo\_organic\_seo |
| `yandex.com`, `yandex.ru` | yandex\_organic\_seo |
| `search.naver.com` | naver\_organic\_seo |
| `daum.net` | daum\_organic\_seo |
| `baidu.com` | baidu\_organic\_seo |
| `ecosia.org/search` | ecosia\_organic\_seo |
| `coccoc.com/search` | coccoc\_organic\_seo |
| `sogou.com` | sogou\_organic\_seo |
| `yahoo.co.jp` | yahoojapan\_organic\_seo |

All rows in this table resolve to channel `seo`.

#### **AI answer engine referrer mapping**

| If the domain host contains… | Media source | Channel |
| --- | --- | --- |
| `chatgpt.com`, `chat.openai.com` | chatgpt\_organic\_aeo | aeo |
| `perplexity.ai` | perplexity\_organic\_aeo | aeo |
| `gemini.google.com` | gemini\_organic\_aeo | aeo |
| `claude.ai` | claude\_organic\_aeo | aeo |
| `deepseek.com` | deepseek\_organic\_aeo | aeo |
| `manus.im` | manus\_organic\_aeo | aeo |
| `grok.com` | grok\_organic\_aeo | aeo |
| `copilot.microsoft.com` | copilot\_organic\_aeo | aeo |

#### **Android app referrers**

If the visit originates from an Android app, the referrer host is mapped as follows:

| App referrer string | Resolved media source |
| --- | --- |
| `com.google.android.googlequicksearchbox` | Google Search |
| `com.google.android.gm` | Email |
| `com.linkedin.android` | linkedin |
| `com.twitter.android` | twitter |
| `org.telegram.messenger` | telegram |

</Accordion>

## Step 3: Campaign resolution

Once the media source is confirmed in Step 2, AppsFlyer attempts to identify the specific campaign details.

AppsFlyer pulls campaign information from the following URL parameters, in order of priority:

| URL parameter(s) | Maps to | Priority order |
| --- | --- | --- |
| `c`, `af_campaign`, `utm_campaign` | Campaign name | <ol><li>`c`</li><li>`af_campaign`</li><li>`utm_campaign`</li></ol> |
| `af_c_id`, `af_campaign_id` | Campaign ID | <ol><li>`af_c_id`</li><li>`af_campaign_id`</li></ol> |
| `af_adset` | Ad set name | — |
| `af_adset_id` | Ad set ID | — |
| `af_ad` | Ad name | — |
| `af_ad_id` | Ad ID | — |
| `af_keywords` | Keywords | — |

## Step 4: Channel classification

In addition to identifying the media source, AppsFlyer classifies each visit into a channel. This classification provides a high-level view of traffic types in the raw data reports and on the dashboard.

### Overriding the channel with af\_channel

To assign a custom channel value, add the `af_channel` parameter to the landing page URL. For example, `af_channel=ig` sets the channel to `ig`, letting you break down traffic at a level the standard categories don't capture, such as by ad placement.

`af_channel` is resolved only when a media source is also identified for the visit. If the visit is organic (no media source identified), it always resolves to `Direct`, whether or not `af_channel` is present.

### Default channel classification

If `af_channel` isn't present, or the visit doesn't meet the condition above, AppsFlyer falls back to automatic classification based on the identified media source:

* **Direct:** The user typed the URL directly or used a bookmark. No attribution source is identified.
* **Social Media:** Traffic originating from the social platforms.
* **Email:** Traffic from email campaigns or email service providers.
* **Ad:** Traffic generated by paid advertising.
* **Referral:** Traffic from other websites, identified via the referrer.
* **Other:** Traffic that does not match any of the categories above.
* **seo:** Unpaid traffic from search engines.
* **aeo:** Traffic from AI answer engines.

**Note:** Every visit is assigned a channel. The classification is automatic and deterministic, based on the identified media source and attribution method, unless overridden by `af_channel`.

<div data-zendesk-anchors="h_01KGMEER6DX8W3ECBEBYP4DQV1=what-is-traffic-source-resolution h_01KGMEER6DA4HMSZ3TVEAG84WZ=the-traffic-source-resolution-flow h_01KGMEER6DV02F44C5ZPSBEQEX=step-1-visit-recording h_01KSSEM5P8RX29CD6C6ZD2DVAT=stage-1-referrer-classification h_01KSSEM5P8KBYDBCB7PAPGPX5M=stage-2-session-evaluation-and-visit-recording h_01KGMEER6D082QTZGZYEXT6726=step-2-media-source-resolution h_01KGMF0E1XBSJCVDWGC4R8XMPX=how-utm-logic-works h_01KGMF0JSBZ3WYM65R55BCDAMN=utm-mapping-rules h_01KGMEZA9ETGK6Z89GM111E64Z=the-parsing-mechanism h_01KGMEZESC451HVJT139BSXEA5=referrer-mapping-rules h_01KGMEZKCTASMNXZG13VTVECVH=search-engine-mapping h_01M2G7SJBDHFPEZ0WREHHD2YQF=ai-answer-engine-referrer-mapping h_01KGMEZQYCDS23MVW3MQH9Q5JQ=android-app-referrers h_01KGMEER6ES1AYT24MC4HZCX9X=step-3-campaign-resolution h_01KGMEER6ETWGFFM3E17KHMDAF=step-4-channel-classification h_01_overriding-the-channel-with-af-channel=overriding-the-channel-with-af_channel h_01_default-channel-classification=default-channel-classification" />
