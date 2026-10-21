---
title: Tealium integration with AppsFlyer
metadata:
  keywords:
    - Marketers
    - TEST ID LOC
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-22T16:09:24Z'
  edited_at: '2024-02-14T06:58:32Z'
  id: 10820404821393
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/10820404821393-Tealium-integration-with-AppsFlyer
---
**At a glance:** Tealium, a Customer Data Platform (CDP), connects customer data across the web, mobile, IoT, and offline. Learn how to automatically share conversion data with Tealium.

<Image alt="Tealium_icon.png" src="https://files.readme.io/e3cc1f95e8ce2de6fa83df63ff78dd4f4f76aebe1acb8e9378aa5b6aa4134364-10820461521681.png" width="276px" />

## Overview

By integrating Tealium with AppsFlyer, mobile customers can leverage the AppsFlyer mobile attribution SDK and send attribution conversion data directly to their Tealium AudienceStream profile.

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions#media-source-restrictions">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Tealium

You can choose one of the following ways to integrate Tealium with AppsFlyer:

* Client-side integration
* Server-side integration

### Client-side integration

Use remote commands for iOS and Android libraries, allowing native code to be triggered in the AppsFlyer SDK.

**To integrate Tealium using client-side integration:**

* Follow the <Anchor target="_blank" href="https://docs.tealium.com/platforms/remote-commands/integrations/appsflyer/">remote command integration guide</Anchor>

### Server-side integration

Set up the AppsFlyer App Events connector in your Customer Data Hub account to transmit data between Tealium and AppsFlyer in real time.

**To integrate Tealium using server-side integration:**

* Follow the <Anchor target="_blank" href="https://docs.tealium.com/server-side-connectors/appsflyer-app-events-connector/">AppsFlyer App Events connector guide</Anchor>

<div data-zendesk-anchors="h_01H9HWK1ACY09ZVD7WHEQR4MR3=overview h_01H9HWK1ACA6A743PDY3Q1Y0KV=important h_01H9HWK1AC27GPZPZR13SFC3GM=setting-up-tealium clientside-integration=client-side-integration h_01H9HWK1ACH6K0FDTVCHAPSKME=client-side-integration serverside-integration=server-side-integration h_01H9HWK1ACDZQEYVRZ7QWQ4KY3=server-side-integration" />
