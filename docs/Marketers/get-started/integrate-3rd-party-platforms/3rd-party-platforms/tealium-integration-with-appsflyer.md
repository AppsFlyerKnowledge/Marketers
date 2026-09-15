---
title: "Tealium integration with AppsFlyer"
excerpt: "Learn how to integrate Tealium with AppsFlyer using client-side or server-side methods to automatically share conversion data."
---
**At a glance:** Tealium, a Customer Data Platform (CDP), connects customer data across the web, mobile, IoT, and offline. Learn how to automatically share conversion data with Tealium.

![Tealium_icon.png](https://files.readme.io/e3cc1f95e8ce2de6fa83df63ff78dd4f4f76aebe1acb8e9378aa5b6aa4134364-10820461521681.png)

## Overview

By integrating Tealium with AppsFlyer, mobile customers can leverage the AppsFlyer mobile attribution SDK and send attribution conversion data directly to their Tealium AudienceStream profile.

> 🚧 Important!
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Tealium

You can choose one of the following ways to integrate Tealium with AppsFlyer:

- Client-side integration
- Server-side integration

### Client-side integration

Use remote commands for iOS and Android libraries, allowing native code to be triggered in the AppsFlyer SDK.

**To integrate Tealium using client-side integration:**

- Follow the [remote command integration guide](https://docs.tealium.com/platforms/remote-commands/integrations/appsflyer/)

### Server-side integration

Set up the AppsFlyer App Events connector in your Customer Data Hub account to transmit data between Tealium and AppsFlyer in real time.

**To integrate Tealium using server-side integration:**

- Follow the [AppsFlyer App Events connector guide](https://docs.tealium.com/server-side-connectors/appsflyer-app-events-connector/)