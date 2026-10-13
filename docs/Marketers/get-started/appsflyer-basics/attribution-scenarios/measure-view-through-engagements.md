---
title: "Measure view-through engagements"
excerpt: "Learn how view-through attribution measures app installs, re-attributions, and re-engagements from users who viewed an ad without clicking."
x-zendesk:
  id: 210084473
  url: https://support.appsflyer.com/hc/en-us/articles/210084473-Measure-view-through-engagements
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Attribution scenarios
  section_id: 6551328497041
  position: 5
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-moran-davida, Marketers, Mobile Attribution]
  labels: [Advertisers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2016-04-20T07:38:24Z'
  edited_at: '2026-05-05T15:20:54Z'
---
**At a glance:** A user who views an ad (impression) and subsequently installs the app, is attributed by view-through attribution.

## Overview

View-through attribution measures installs, re-attributions, and re-engagements of users who viewed an ad but didn't click on it.

### View-through attribution flow

<Image src="https://files.readme.io/86d32778a8a0966499a0c5c91c1b2d8aed6d5bb24214b1a32fd484779c105a98-4412917609489.png" alt="Retargeting - View-through" />

### Terminology

- **Impression:** The display of an ad to a user regardless of any click or other user engagement.
- **Install**: In this article, means installs, re-attributions, and re-engagements.
- **View-through attribution:** Attributing installs to a media source after the user sees an impression.

### View-through attribution principles

- Both [device ID matching](/docs/appsflyer-attribution-model#device-id-matching) and [probabilistic modeling](/docs/appsflyer-attribution-model#probabilistic-modeling) are supported.
- Supported by partners listed in the [view-through attribution partner list](/docs/measure-view-through-engagements#view-vta-partner-list).

Impressions are candidates for view-through attribution using the following principles:

- The impression occurred within the view-through lookback window (default 24 hours).
- If multiple impressions are found, the most recent impression is considered.
- Clicks have priority over impressions. This means that if there are clicks in the click-through lookback window, the most recent click wins. The most recent impression is attributed as a contributor (assist).

### View-through lookback window

- For non-SRNs, the view-through attribution lookback window duration is 1-24 hours. For SRNs, the lookback window can be longer.
- To set the window:
  - **Non-SRNs:** Set the duration using impression attribution links by setting the `af_viewthrough_lookback` parameter. If the parameter isn't set, a default 24 hours window is used.
  - **SRNs**: The window is determined by the SRN. We recommend setting the same value as the SRN's in AppsFlyer.

### View-through attribution reporting and metrics

- **Aggregate data:** Ad networks report aggregate impression data to AppsFlyer via API, or on a per-impression basis. Consider that impression counting and reporting is defined by each partner individually. The related metrics are available in the Overview dashboard and via other reporting tools. The metrics available are:
  - Impressions: Number of impressions displayed during a given period.
  - View-throughs: The number of installs attributed using view-through attribution.
- **Raw-data**:
  - User-level data (raw data) of users attributed via view-through attribution is available and similar to that of users attributed by click. However, some partners restrict the availability of this data.
  - Impression data (similar to click data) is available.
  - The attributed_touch_type field contains the value _impression._

## View-through operations

### Set impression links

Ad networks send impression links to AppsFlyer populated with campaign and other details similar to those included in click-through [attribution links](/docs/about-link-structure-and-parameters).

The links are sent in real-time so that if an install follows an impression, it is attributed correctly.

Consider the following in preparing links:

- The base URL is `https://impression.appsflyer.com`.
- Use a GET request.
- Include device IDs where available: IDFA, GAID, IDFV, and so on.
- Include [probabilistic modeling](/docs/appsflyer-attribution-model#probabilistic-modeling-parameters-for-ad-networks) parameters.
- The device ID values can be hashed for better security using SHA1. The parameter name should begin with "sha1_" and be followed by the parameter name and the hashed value, for example, sha1_idfa, sha1_advertising_id, sha1_android_id, and sha1_imei.

Example

```auto
https://impression.appsflyer.com/{app-id}?c={campaign name}&pid={media source}
&af_viewthrough_lookback=1d&af_prt={agency_name}&af_siteid={site id value}
&af_sub1={free value}&idfa={idfa value}
```

### Set custom impression links

Advertisers utilize attribution impression links with their own custom media sources, for example, website banners.

When advertisers [create custom attribution links](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-onelink-link), they get full impression links, which can be fired every time a user engages with their owned ads.

Custom impression links (created via OneLink) can also be used to perform view-through attribution of mobile website visitors. Learn more about [creating custom impression URLs](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url).

### Turn off view-through-attribution

By default, view-through attribution is turned on. If AppsFlyer receives a valid impression attribution link, the impression participates in the attribution flow.

Since view-through attribution is enabled by default, it's important that advertisers contractually agree with the network in advance whether or not their view-through attribution should be enabled.

View-through attribution can be disabled per media source. However, if impressions are received, and view-through attribution is disabled:

- Impression metrics are available in the dashboard.
- The attribution process ignores these impressions.

**To turn off view-through-attribution:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.
2. Select the integrated partner.
3. In the Integration tab, turn off **Install view-through attribution**.
4. Click **Save integration**.

In regard to SRNs: Turning off view-through attribution in AppsFlyer doesn't do the same on the network side. Make sure that you align the view-through settings in both AppsFlyer and the networks to avoid discrepancies.