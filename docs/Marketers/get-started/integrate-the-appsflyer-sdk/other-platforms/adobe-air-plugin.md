---
title: "Adobe AIR plugin"
excerpt: "Integrate the AppsFlyer SDK into iOS and Android apps developed with the Adobe AIR platform to measure installs, in-app events, and media sources."
---
At a glance: Integrate AppsFlyer SDK into iOS/Android apps developed with Adobe AIR development platform to measure installs, in-app events, media sources, and more.

## Plugin information

Supported platforms:

- Android
- iOS 6+

Based on:

- iOS AppsFlyer SDK V6.0.3
- Android AppsFlyer SDK V5.4.1

## Installation and implementation

### Installation

Download the [AppsFlyerAIRExtension.ane](https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/blob/master/bin/AppsFlyerAIRExtension.ane "AppsFlyerAIRExtension.ane") file from the bin folder Add the ANE to your project and make sure the IDE is marked to package it.

If the following was not added automatically, add it to the APP_NAME-app.xml:

```markup
<extensions>
  <extensionID>com.appsflyer.adobeair</extensionID>
</extensions>
```

#### Notes for Android apps

- In the AppsFlyer dashboard you will need to add "air." prefix to the package name as this is added automatically by Air. For example - an app with the package name " **com.test.android**", should set the app id in the AppsFlyer Dashboard as " **air.com.test.android**".

- Add the following permissions to Android Manifest (in the app description`APP_NAME-app.xml`):

```markup
<uses-permission android:name=