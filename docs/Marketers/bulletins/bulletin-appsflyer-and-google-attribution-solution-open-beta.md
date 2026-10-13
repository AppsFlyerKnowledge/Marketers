---
title: "Bulletin: AppsFlyer and Google attribution solution [Open BETA]"
table_of_contents: false
x-zendesk:
  id: 37857301293457
  url: https://support.appsflyer.com/hc/en-us/articles/37857301293457-Bulletin-AppsFlyer-and-Google-attribution-solution-Open-BETA
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: []
  promoted: false
  comments_disabled: false
  created_at: '2025-08-06T13:24:32Z'
  edited_at: '2026-08-05T06:01:40Z'
---
<Embed title="Enable AppsFlyer enhanced attribution with Google ICM" typeOfEmbed="youtube" url="https://www.youtube.com/embed/VilMr6T0Yd0" />

| Section | Details |
| --- | --- |
| **What's new** | Google’s Integrated Conversions Measurement (ICM) solution will be available to all clients using Google Ads to measure Installs and re-attributions. |
| **Estimated General availability (Open Beta) date:** | - **iOS** – Open Beta (as of November 12) - open to all apps.<br />- **Android** – Open Beta (as of December 5, 2025) - open to all Apps. |
| **What you need to know** | - ICM enables AppsFlyer to attribute installs to Google Ads without needing device IDs, using privacy-preserving methods.<br />- Google sends non-deterministic install claims to AppsFlyer. <br />  <br />  If validated by AppsFlyer’s data, these claims are used for attribution. For more information see [Google Ads attribution flow with Advanced Data Sharing](/docs/google-ads-adwords-integration-setup-for-advertisers#google-icm-attribution-flow-with-advanced-data-sharing). |
| **What you need to do** | - **SDK Requirements:**  - **iOS:** Requires AppsFlyer [iOS SDK version 6.17.9](https://dev.appsflyer.com/hc/docs/ios-release-notes) or later _and_ either Google [Firebase SDK version 11.14.0](https://github.com/firebase/firebase-ios-sdk/releases) or later, or the standalone [Google ODM SDK](https://support.google.com/google-ads/answer/16384720).<br />  - **Android:** No SDK update required.<br />- **Advanced Data Sharing toggle:** A new setting under both iOS and Android `googleadwords_int` integrations:  - When **enabled**: AppsFlyer will send all install events to Google, even without a device ID.<br />  - When **disabled**: Only install events with available device ID or GCLID will be shared, limiting ICM effectiveness.<br />- **Important (iOS only):** ICM is not available for traffic originating from users in the European Economic Area (EEA), the United Kingdom and Switzerland. |