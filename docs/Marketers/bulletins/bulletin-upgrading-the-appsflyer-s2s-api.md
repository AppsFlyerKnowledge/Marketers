---
title: "Bulletin: Upgrading the AppsFlyer S2S API"
excerpt: "AppsFlyer has upgraded its server-to-server (S2S) API for in-app events to provide a more secure experience and reduce fraud."
table_of_contents: false
x-zendesk:
  id: 20509378973457
  url: https://support.appsflyer.com/hc/en-us/articles/20509378973457-Bulletin-Upgrading-the-AppsFlyer-S2S-API
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 27
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2023-11-28T16:26:35Z'
  edited_at: '2024-04-14T07:07:17Z'
---
To provide a more secure experience for API usage and to reduce fraud, AppsFlyer has upgraded its server-to-server (S2S) API for in-app events. The existing endpoint will be deprecated in the future and we recommend to start planning the switch. AppsFlyer is working on a solution for third-party tech partners that send data on your behalf.

| | |
| --- | --- |
| **Effective date** | December 12, 2023 |
| **Prerequisites** | Only an admin can update the new S2S API. |
| **Action required** | Update the following fields for sending S2S in-app events to AppsFlyer:<br />1. Go to the [POST S2S in-app event API](https://dev.appsflyer.com/hc/reference/post_s2s_inappevent).<br />2. Replace the URL:<br /><br />From [https://api2.appsflyer.com/inappevent](https://api2.appsflyer.com/inappevent)<br /><br />To [https://api3.appsflyer.com/inappevent](https://api3.appsflyer.com/inappevent)<br />3. Update the Authorization Header: Replace the Dev key with the [**new S2S key**](/docs/managing-appsflyer-tokens).<br />4. If you are sending S2S events to AppsFlyer via an integrated partner (such as Segment, Tealium, Amplitude, mParticle, RevenueCat, or others) contact them to learn how to update the integration. |
| **Recommended action** | **Before updating the new API in all your production calls:**<br />We highly recommend sending a number of test in-app events to the new endpoint and **making sure no error is returned**. |
| **What you should know** | If you have any concerns regarding fraud events being sent to the old endpoint after you've updated the new API, please turn to your CSM or AppsFlyer support. Make sure to include the relevant app IDs.<br />After completing the production migration, AppsFlyer will block the old API endpoint for these apps so any fraud calls will be blocked. |
| **Who needs to update the new API?** | Only advertisers must update the new S2S API for in-app events. |
| **About the S2S API** | Learn more about [S2S and API tokens](/docs/managing-appsflyer-tokens). |