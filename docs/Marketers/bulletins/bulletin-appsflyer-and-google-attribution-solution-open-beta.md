---
title: 'Bulletin: AppsFlyer and Google attribution solution [Open BETA]'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-08-06T13:24:32Z'
  edited_at: '2026-08-05T06:01:40Z'
  id: 37857301293457
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/37857301293457-Bulletin-AppsFlyer-and-Google-attribution-solution-Open-BETA
---
<Embed title="YouTube video player" typeOfEmbed="youtube" url="https://www.youtube.com/embed/VilMr6T0Yd0?si=p7FezQwuKkBtwkaB" providerUrl="https://www.youtube.com" />

| Section | Details |
| --- | --- |
| **What's new** | Google’s Integrated Conversions Measurement (ICM) solution will be available to all clients using Google Ads to measure Installs and re-attributions. |
| **Estimated General availability (Open Beta) date:** | <ul><li>**iOS** – Open Beta (as of November 12) - open to all apps.</li><li>**Android** – Open Beta (as of December 5, 2025) - open to all Apps.</li></ul> |
| **What you need to know** | <ul><li>ICM enables AppsFlyer to attribute installs to Google Ads without needing device IDs, using privacy-preserving methods.</li><li>Google sends non-deterministic install claims to AppsFlyer.<br />If validated by AppsFlyer’s data, these claims are used for attribution. For more information see <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers#google-ads-attribution-flow-with-advanced-data-sharing">Google Ads attribution flow with Advanced Data Sharing</Anchor>.</li></ul> |
| **What you need to do** | <ul><li>**SDK Requirements:**<ul><li>**iOS:** Requires AppsFlyer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">iOS SDK version 6.17.9</Anchor> or later *and* either Google <Anchor target="_blank" href="https://github.com/firebase/firebase-ios-sdk/releases">Firebase SDK version 11.14.0</Anchor> or later, or the standalone <Anchor target="_blank" href="https://support.google.com/google-ads/answer/16384720">Google ODM SDK</Anchor>.</li><li>**Android:** No SDK update required.</li></ul></li><li>**Advanced Data Sharing toggle:** A new setting under both iOS and Android `googleadwords_int` integrations:<ul><li>When **enabled**: AppsFlyer will send all install events to Google, even without a device ID.</li><li>When **disabled**: Only install events with available device ID or GCLID will be shared, limiting ICM effectiveness.</li></ul></li><li>**Important (iOS only):** ICM is not available for traffic originating from users in the European Economic Area (EEA), the United Kingdom and Switzerland.</li></ul> |