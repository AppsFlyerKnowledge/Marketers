---
title: 'Bulletin: Adding a priority queue to the Android SDK'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-06-19T13:46:02Z'
  edited_at: '2026-08-18T09:13:22Z'
  id: 6971914107025
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/6971914107025-Bulletin-Adding-a-priority-queue-to-the-Android-SDK
---
| **What's new** | In version 6.7.0 we introduced some changes to the way the SDK is handling the various requests to the AppsFlyer servers.<br /><br />We've noticed that there are apps that try and send in-app events before they have started the SDK. By introducing this change, we're making sure things are executed in the right order. |
| --- | --- |
| **What's changing** | **Before the change**: In earlier versions of the SDK, the app could send in-app events to AppsFlyer before calling the SDK’s `start` method (which means before the conversion was sent to the server).<br /><br />**After the change**: Starting with this version, the conversion request is prioritized and all the in-app events that take place before calling `start` are stored and wait for the conversion request to be sent. |