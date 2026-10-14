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
<Embed title="YouTube video player" typeOfEmbed="youtube" url="https://www.youtube.com/embed/VilMr6T0Yd0?si=p7FezQwuKkBtwkaB" providerUrl="https://www.youtube.com" />

| Section | Details |
| --- | --- |
| **What's new** | Google’s Integrated Conversions Measurement (ICM) solution will be available to all clients using Google Ads to measure Installs and re-attributions. |
| **Estimated General availability (Open Beta) date:** | <ul><li>**iOS** – Open Beta (as of November 12) - open to all apps.</li><li>**Android** – Open Beta (as of December 5, 2025) - open to all Apps.</li></ul> |
| **What you need to know** | <ul><li>ICM enables AppsFlyer to attribute installs to Google Ads without needing device IDs, using privacy-preserving methods.</li><li>Google sends non-deterministic install claims to AppsFlyer.<br />If validated by AppsFlyer’s data, these claims are used for attribution. For more information see [Google Ads attribution flow with Advanced Data Sharing](/docs/google-ads-adwords-integration-setup-for-advertisers#google-ads-attribution-flow-with-advanced-data-sharing).</li></ul> |
| **What you need to do** | <ul><li>**SDK Requirements:**<ul><li>**iOS:** Requires AppsFlyer [iOS SDK version 6.17.9](https://dev.appsflyer.com/hc/docs/ios-release-notes) or later *and* either Google [Firebase SDK version 11.14.0](https://github.com/firebase/firebase-ios-sdk/releases) or later, or the standalone [Google ODM SDK](https://support.google.com/google-ads/answer/16384720).</li><li>**Android:** No SDK update required.</li></ul></li><li>**Advanced Data Sharing toggle:** A new setting under both iOS and Android `googleadwords_int` integrations:<ul><li>When **enabled**: AppsFlyer will send all install events to Google, even without a device ID.</li><li>When **disabled**: Only install events with available device ID or GCLID will be shared, limiting ICM effectiveness.</li></ul></li><li>**Important (iOS only):** ICM is not available for traffic originating from users in the European Economic Area (EEA), the United Kingdom and Switzerland.</li></ul> |