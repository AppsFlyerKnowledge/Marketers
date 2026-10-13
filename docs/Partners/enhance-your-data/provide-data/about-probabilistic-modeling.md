---
title: "About probabilistic modeling"
excerpt: "Learn how AppsFlyer uses probabilistic modeling as a privacy-preserving statistical method to attribute campaigns when deterministic signals are unavailable."
x-zendesk:
  id: 40188089592209
  url: https://support.appsflyer.com/hc/en-us/articles/40188089592209-About-probabilistic-modeling
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Provide data
  section_id: 6551209900817
  position: 1
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-yael-sharabi, Marketers, Data Management]
  labels: []
  promoted: false
  comments_disabled: true
  created_at: '2025-10-21T14:32:11Z'
  edited_at: '2026-04-19T13:00:27Z'
---
AppsFlyer uses probabilistic modeling as a privacy-preserving statistical method to report on how app developers’ marketing campaigns are performing. It produces aggregate campaign-level performance reports for app developers.

**Implementation characteristics**

- Uses statistics and is not based on unique IDs.
- It is a fallback method used when a referer or advertising IDs are unavailable. Deterministic attribution methods, i.e., clicks with referrer or ID matching, are given priority if they occur within the lookback window.

### When is probabilistic modeling used?

Except where otherwise configured by the customer, probabilistic modeling will apply in cases where deterministic data is unavailable, including:

- Web-to-app conversions
- Cross-device experiences (for example, a desktop ad followed by a mobile install)
- CTV, PC, or console environments where deterministic attribution isn’t possible