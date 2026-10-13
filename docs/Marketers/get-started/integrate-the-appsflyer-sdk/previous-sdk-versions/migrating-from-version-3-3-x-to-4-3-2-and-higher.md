---
title: "Migrating from Version 3.3.X to 4.3.2 and Higher"
excerpt: "Considerations for migrating versions of the AppsFlyer Android SDK."
x-zendesk:
  id: 207606796
  url: https://support.appsflyer.com/hc/en-us/articles/207606796-Migrating-from-Version-3-3-X-to-4-3-2-and-Higher
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Previous SDK versions
  section_id: 6551300280977
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Advertisers, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-02-03T10:37:42Z'
  edited_at: '2026-08-18T09:07:24Z'
---
Major changes have been made to the Android SDK integration.

The main changes are:

- The SDK is now a singleton, meaning that every call to the APIs should be called as follows:

```java
JavaAppsFlyerLib.getInstance().setCustomerUserId("myId");
```

- **SetAppsFlyerKey()**– this method was removed; as a result, we expect to receive the dev key using the new init method: AppsFlyerLib.getInstance().startTracking (this,"YOUR_APPSFLYER_DEV_KEY")
- **sendTracking()**, **onActivityPause()**, **onActivityResume()** were removed. The SDK detects launches automatically
- **Deep Link** - for activities that support deep linking the developer should call:

```java
JavaAppsFlyerLib.getInstance().sendDeepLinkData(this) from the onCreate()
```

of the displayed activity.

This is necessary only if the app is not running in the background.

- **Logging** - The logging flag default value has been changed to false. In addition, if the flag is turned off, no logs are printed (bug fix). To activate the logging flag, the developer should call:

AppsFlyerLib.getInstance().setDebugLog(true);

To view the AppsFlyer SDK Integration Guide for Android, click [here](/docs/sdk-integration-overview).

### Migrating to 4.4.0 and higher

The AppsFlyer Android SDK v4.4.0 **no longer supports the following receiver** in the manifest:

```markup
<receiver android:name="com.appsflyer.AppsFlyerLib">
  <intent-filter>
    <action android:name="android.intent.action.PACKAGE_REMOVED"/>
    <data android:scheme="package"/>
  </intent-filter>
</receiver>
```

If you are using version 4.4.0+, **remove this receiver from your manifest file**.

The only **mandatory** receiver for the SDK is as follows:

```markup
<receiver
  android:name="com.appsflyer.MultipleInstallBroadcastReceiver"
  android:exported="true">
    <intent-filter>
      <action android:name="com.android.vending.INSTALL_REFERRER" />
    </intent-filter>
</receiver>
```