---
title: About Enriched Engagement Types
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-01-21T13:45:23Z'
  edited_at: '2026-07-09T14:27:40Z'
  id: 21837486015889
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/21837486015889-About-Enriched-Engagement-Types
---
> **At a glance:** While ad types have become sophisticated and complex, reporting has remained very narrow, focusing solely on view-through and click-through attribution. Enriched Engagement Types changes that by reflecting users' full spectrum of engagement and intentionality when viewing or interacting with an ad.

## Introduction

Over the past few years, new creative ad types, such as playable, skippable, and short-form video ads, have been introduced to the market, offering new ways to connect with users. These types of ads differ significantly from the static banners and lo-fi video units of the past and provide advertisers with broader capabilities and formats.

However, while ad types have become sophisticated, more complex, and more interactive, reporting has remained very narrow, focusing solely on view-through and click-through attribution. Different types of engagements hold different weights, levels of intent, and impact, but the current measurement methodologies have overlooked this new reality. Naturally, advertising networks want to ensure that the levels of intent and engagement are represented as best as possible, which has led to a lack of standardization across the ecosystem. This is ultimately causing advertisers to only gain a partial understanding of their ad spend performance.

In collaboration with leading networks, AppsFlyer is introducing a standard for engagements to deliver trust and transparency throughout the ecosystem. Enriched Engagement Types reflect users' full spectrum of engagement and intentionality when viewing or interacting with an ad, from momentary exposure to direct response. This framework ensures these standards are kept throughout AppsFlyer’s partner ecosystem and beyond. Through Enriched Engagement Types, advertisers can ensure they have a highly standard and rich picture of their ad spend performance and can leverage these insights to improve budget allocation and increase ROAS.

## What are Enriched Engagement Types

The Enriched Engagement Types (EET) framework provides visibility to the nuances of the user journey, by indicating when views were engaging (for example, when a user watches a skippable video ad for at least 5 seconds after the skip option appears) and when clicks led other than to app openings or app store. By doing so, marketers receive more insight into their users' actions, which in turn leads to smarter budget allocation and improved ROI.

The following is the list of the enriched engagement types:

| engagement\_type | Description |
| --- | --- |
| <span id="preload"></span>preload | The app is preloaded by the OEM at the factory or by the provider the first time the device is activated. Alternatively, a wizard prompts users to download the app when the device is first activated. |
| <span id="click_to_download"></span>click\_to\_download | When the user engages with an ad, the app is automatically downloaded and installed on the device without redirecting to an app store. |
| <span id="click_to_app"></span>click\_to\_app | An ad click, QR code scan, deep link, or any other click that redirects the user to the app or to the relevant app store to download the app. |
| <span id="engaged_click"></span>engaged\_click | A click that keeps the user in the same context, engaging with the ad, and does NOT direct that user to the app store or to launch the app. |
| <span id="engaged_view"></span>engaged\_view | An engaged view occurs when a meaningful view takes place within skippable videos, rewarded videos, or StoreKit-rendered ads. For example, when a user watches a skippable video ad for at least 5 seconds after the skip option appears. |
| <span id="view"></span>view | An ad view is when an ad is rendered, and an impression takes place. |
| <span id="listening"></span>listening | Listening is when a user listens to an audio ad, such as a podcast ad. |

## **EET Attribution priority and lookback window**

The Enriched Engagement Types framework does not impact the engagement type attribution priority. Hence, introducing EET is not expected to affect your install and conversion rate.

The table below specifies the <Anchor target="_blank" href="/marketers/id/docs/appsflyer-attribution-model#attribution-method-priorities-attribution-waterfall">attribution priority</Anchor> and <Anchor target="_blank" href="/marketers/id/docs/set-up-lookback-windows#jendela-lookback">lookback window</Anchor> of each engagement type:

<table><thead><tr><th>Engagement</th><th>Engagement type</th><th>Attribution priority\*</th><th>Lookback window\*\*</th></tr></thead><tbody><tr><td rowspan="2">Download</td><td>preload</td><td>1</td><td>1h-180d | default: 90d</td></tr><tr><td>click_to_download</td><td>2</td><td>1h-30d | default: 7d</td></tr><tr><td rowspan="2">Click</td><td>click_to_app</td><td>2</td><td>1h-30d | default: 7d</td></tr><tr><td>engaged_click</td><td>2</td><td>1h-7d | default: 2d </td></tr><tr><td rowspan="3">Impression</td><td>engaged_view</td><td>2</td><td>1h-7d | default: 2d</td></tr><tr><td>view</td><td>3</td><td>1h-24h | default: 24h</td></tr><tr><td>listening</td><td>3</td><td>1h-24h | default: 24h</td></tr></tbody></table>

*When an engagement type isn’t reported, the default priority is set (2 for clicks, 3 for impressions).

**Lookback windows for `engaged_click` and `engaged_view` can only be set for non-SRN networks. For SRNs, `engaged_click` and `engaged_view` share the same lookback window as clicks and are, therefore, set by the **Install Click-Through Attribution Lookback** sliders.

## Which networks can report engaged views and engaged clicks?

The table below lists networks that are qualified by AppsFlyer to report `engaged_clicks` and `engaged_views`.  Networks wishing to join this list should contact AppsFlyer support.

| **Ad Network** | **Engaged views** | **Engaged clicks** |
| --- | --- | --- |
| facebook\_int | Yes |  |
| googleadwords\_int | Yes |  |
| tiktokglobal\_int* | Yes | Yes |
| twitter\_int | Yes | Yes |
| snapchat\_int | Yes | Yes |
| bytedanceglobal\_int | Yes | Yes |
| aarki\_int | Yes | Yes |
| adjoe\_int |  | Yes |
| appier\_int | Yes | Yes |
| appnext\_int | Yes |  |
| bidease\_int | Yes | Yes |
| bigabid\_int | Yes | Yes |
| inmobidsp\_int | Yes | Yes |
| ironsource\_int | Yes |  |
| lap\_int | Yes |  |
| liftoff\_int | Yes | Yes |
| mdsp\_int | Yes | Yes |
| mintegral\_int | Yes | Yes |
| onedigitalturbine\_int | Yes |  |
| personalyrtb\_int | Yes | Yes |
| pinterest\_int | Yes |  |
| remerge\_int | Yes | Yes |
| revx\_int | Yes | Yes |
| rtbhouse\_int | Yes | Yes |
| smadex\_int | Yes | Yes |
| trademob\_int | Yes | Yes |
| unityads\_int | Yes | Yes |
| vungle\_int | Yes |  |
| yahoojapan\_int | Yes |  |
| yandexdirect\_int | Yes | Yes |
| youappi\_int | Yes | Yes |
| jampp\_int | Yes | Yes |

* TikTok supports the enriched engagement type, but their engaged views are currently not properly reflected in reporting. AppsFlyer is working with TikTok to resolve this issue.

> 📘 **Note**
>
> **Not all the listed eligible networks actually support engaged clicks and engaged views**. To find out if a particular eligible network supports `engaged_clicks` and `engaged_views` in practice. refer to the raw data report containing engagements reported by the network and see if the `engagement_type` parameter is populated with the above values.

## Set lookback windows for engaged clicks and engaged views

**To set the lookback windows for engaged clicks and engaged views:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.
2. Select the integrated partner.
3. Set the lookback windows for the engaged view-through and click-through attribution.

   > 📘 **Note**
   >
   > Engaged-click and engaged-view lookback windows are always set in the partner **Integration tab**, in contrast to view-through and click-through lookback windows, which can be set on the attribution links.
   >
   > For SRNs, setting the click-through lookback window also determines the engaged click and engaged view lookback windows.

4. Click **Save integration**.

## View and analyze EET data

### Raw data reports

`engagement_type` will be reported in raw data reports whenever reported by the ad network. It will also be available for contributors' data.

> 📘 **Note**
>
> Engaged views are always included in raw data reports, even when view-through attribution is turned off.

When there are no clicks recorded, such as in cases of preload or deep links, AppsFlyer will set the relevant value (preload or `click_to_app` for deep links) within the `engagement_type` field in the raw data reports.

The below scenarios will result in the `engagement_type` field in the raw data reports receiving the values `click_unspecified` and `impression_unspecified`.

* When there is a mismatch between the engagement (click/impression) and the engagement type.
* When `af_engagement_type` is not sent or sent with an empty value.

In order to see the engagement type in raw data reports, advertisers need to select these fields in the relevant raw data product (engagement type and contributors engagement type are not selected by default).

### Dashboards

Engagement type dimension is added in the dashboards.

<Image align="center" alt="eet-dashboard.png" src="https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png" />

> 📘 **Note**
>
> Engaged views are always visible in the dashboard, even when view-through attribution is turned off.

### How to calculate **Installs per Mille** (IPM)

Total impressions include both engaged views and regular views. To calculate the IPM, you must **subtract engaged views from total impressions** because engaged views are a subset of impressions, and double-counting them would inflate the impression count.

## FAQs

<div id="what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types" />

<Accordion title="What kinds of campaigns are relevant for Enriched Engagement Types?">

Enriched Engagement Types can apply to both UA and retargeting campaigns, depending on the particular network. To learn whether a network supports a retargeting campaign, refer to the network's raw data reports and check whether `engagement_type` is populated for the retargeting campaign.

</Accordion>

<div id="are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard" />

<Accordion title="Are engaged clicks and engaged views included in the aggregate numbers of clicks and impressions on the Overview dashboard?">

For non-SRNs, the numbers are included and counted according to the touch type (i.e., engaged clicks are counted as clicks, engaged views are counted as impressions). For SRNs, it’s currently not included and counted - pending support by the SRNs’ APIs.

</Accordion>

<div id="why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions" />

<Accordion title="Why can't I see the engagement type in Meta's gp_referrer conversions?">

Meta only reports engagement\_type=engaged\_view in its SRN API. There is no engagement\_type value available for other conversions, including gp\_referrer.

</Accordion>

<div id="why-cant-i-see-the-engagement-type-i2" />

<Accordion title="Why do I still see installs and re-engagements with attributed_touch_type = impression even after turning the view-through toggles off?">

Engaged views are measured and reported even if the **view-through** toggles are turned off. To identify those impressions as engaged views, use the `engagement_type = engaged_views` metric in dashboards and raw data reports instead of relying solely on `attributed_touch_type`.

</Accordion>

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| <span id="cross-platform-engaged-view-support"></span>Cross-platform engaged view support | Enhanced Engagement Types  are not yet supported in cross-platform use cases. Even when `engaged_view` is sent in the impression URL, partners and advertisers will see `view` in the attribution data. |
| <span id="owned-media-support"></span>Owned media support | Owned media is currently not supported. Links used in owned media must not include the `af_engagement_type` parameter. |

<div data-zendesk-anchors="h_01HNCNA03SZ0MJFQ9XHDFXNTA1=introduction enriched-engagement-types=what-are-enriched-engagement-types h_01HNCNBR7KMT1KQBG5CPZY8YQY=what-are-enriched-engagement-types h_01HNCVYDH17NGA8SH5XNWR4P9X=eet-attribution-priority-and-lookback-window allowed-networks=which-networks-can-report-engaged-views-and-engaged-clicks h_01J00XFV136HPEHVQNPD934409=which-networks-can-report-engaged-views-and-engaged-clicks 01JENXRAMPFXTMF7SKDN2Y0E5M=note set%C2%A0engaged-enrichment-attribution=set-lookback-windows-for-engaged-clicks-and-engaged-views h_01J5B6EVM9P3M1SVR3K7WWK02J=set-lookback-windows-for-engaged-clicks-and-engaged-views h_01J5B97RCQQG6GN4PCKTQWVF54=note-1 reporting=view-and-analyze-eet-data h_01J00XFV13YN8QNFZJTGM78EG2=view-and-analyze-eet-data raw-data=raw-data-reports h_01J00XFV132M8TM6EGFZ7A7C3A=raw-data-reports 01JFCPX6WKCWY9RM470H23EDQ0=note-2 h_01J00XFV13W0SD4MD7H4BT1RC9=dashboards 01JFCPX6WNCFC0R0N90G4HFYZX=note-3 h_01JHG3EQN6FNJAHX1S91JE3MPT=how-to-calculate-installs-per-mille-ipm 01JFCKK7FK0B5Z7QCZNSX14WF2=faqs h_01HNFTS74KF3YFA0SWRGEQAGYQ=what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types h_01HNYY1S6YQ6YNR6RSY7B8H4EM=are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard h_01HQG5Y4JVNCB60AXR9K2GGD0H=why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions h_01JJP3TT2QMH5Y94C4Q7V6HFP1=why-cant-i-see-the-engagement-type-i2 cross-platform-traits-limitations=traits-and-limitations" />
