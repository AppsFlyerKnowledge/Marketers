---
title: "Preload attribution for partners"
excerpt: "Attribute mobile app installs to campaigns that preload the app at the Original Equipment Manufacturer (OEM) or when the device is first turned on by the user."
---
## Overview

By supporting AppsFlyer preload attribution solutions, preload partners can have app installs attributed to preload campaigns. Preload campaigns are for when an app is installed on a device by a preload partner either at the factory or upon device activation (when the device is first turned on).

Preload partners are:

- Original Equipment Manufacturers (OEMs)
- App discovery platforms
- Mobile carriers

There are 3 ways to attribute preload campaigns:

- [Recommended] AppsFlyer referrer
- Google Play auto-install (PAI)
- [Legacy] Preload in factory via System Property

Postbacks are sent to you after each conversion.

[Learn more about the preload campaign attribution methods](/docs/appsflyer-attribution-model#preload-campaigns)

## Set up preload attribution

To set up preload attribution:

1. Make sure you're an [AppsFlyer integrated partner](https://support.appsflyer.com/hc/articles/360001300998).
2. Choose the preload attribution solutions to integrate (based on advertiser needs).
   > 📘 Note
   >
   > Each integration needs an independent PID with an AppsFlyer Partner Account. Reach out to your partner solutions team via the support widget.
   
   - [Recommended] [AppsFlyer referrer](https://support.appsflyer.com/hc/articles/4543811207313): Contact your PDM for integration instructions.
   - [Google Play auto-install (PAI)](https://support.appsflyer.com/hc/articles/4404557237649): Configure the media source information in the Google Play Referrer API for PAI campaigns using the following UTM parameters: `utm_source=play-auto-installs&utm_medium=preload&utm_campaign=brandnamepai_int`. For example: `utm_source=play-auto-installs&utm_medium=preload&utm_campaign=xiaomipai_int`.
3. Contact the AppsFlyer partner solutions team via the support widget to complete the integration and optionally set up postbacks.

> 📘 Note
>
   > See which postback macros are supported for the preload method of [Google PAI](https://support.appsflyer.com/hc/articles/4404557237649-Preinstall-attribution-using-Google-Play-Auto-Install#postbacks-for-preload-partners) and [AppsFlyer referrer/Android manifest file](https://support.appsflyer.com/hc/articles/207273946).