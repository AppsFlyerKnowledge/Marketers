---
title: "Bulletin: Adding a priority queue to the Android SDK"
table_of_contents: false
x-zendesk:
  id: 6971914107025
  url: https://support.appsflyer.com/hc/en-us/articles/6971914107025-Bulletin-Adding-a-priority-queue-to-the-Android-SDK
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 47
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-06-19T13:46:02Z'
  edited_at: '2026-08-18T09:13:22Z'
---
| **What's new** | In version 6.7.0 we introduced some changes to the way the SDK is handling the various requests to the AppsFlyer servers.<br /><br />We've noticed that there are apps that try and send in-app events before they have started the SDK. By introducing this change, we're making sure things are executed in the right order. |
| --- | --- |
| **What's changing** | **Before the change**: In earlier versions of the SDK, the app could send in-app events to AppsFlyer before calling the SDK’s `start` method (which means before the conversion was sent to the server).<br /><br />**After the change**: Starting with this version, the conversion request is prioritized and all the in-app events that take place before calling `start` are stored and wait for the conversion request to be sent. |