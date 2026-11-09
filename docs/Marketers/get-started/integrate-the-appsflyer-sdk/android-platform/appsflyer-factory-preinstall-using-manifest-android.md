---
title: AppsFlyer factory preinstall using manifest (Android)
metadata:
  keywords:
    - Android
    - Pre-Install
    - Attribution
    - Metrics
    - Advertisers
    - Agencies
    - af_pre_install_name
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2014-10-13T11:14:04Z'
  edited_at: '2024-07-30T14:37:09Z'
  id: 207032166
  locale: en-us
  section: Android platform
  section_id: 6551190827921
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207032166-AppsFlyer-factory-preinstall-using-manifest-Android
---
> **At a glance:** Attribute app installs to device manufacturers for apps added to devices before leaving the factory. **Note**: See <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#preload-campaigns">all other preload attribution methods</Anchor>.

<Image align="center" alt="pre-install-intro-breakdown.png" src="https://files.readme.io/f14231089f68ffa90dc90700397463d363c08b8266e0d18677e9ccf3c28b0828-360002653365.png" />

<div id="introduction" />

## Introduction

<div id="what-is-a-pre-install-campaign" />

### What is a pre-install campaign?

Pre-install campaigns allow app owners to reach vast audiences without running online campaigns.

In pre-install campaigns, app owners can ask device manufacturers to **pre-install their apps on devices before they leave the factory**.

Pre-install campaigns can also be a collaboration with 3rd party media sources, which work with various manufacturers on behalf of app owners.

<div id="important" />

> 🚧 **Important!**
>
> AppsFlyer counts an install once an app launches for the first time. Therefore, the number of displayed pre-installs is the number of users launching your app, and not the number of devices that have the app pre-installed on.

<div id="benefits-of-recording-installs-from-pre-install-campaigns" />

### Benefits of recording installs from pre-install campaigns

By attributing pre-install campaigns you can measure the:

* number of users who launch your pre-installed app
* number of app users each manufacturer brings
* LTV of each user and determine which manufacturer brings high-value users

<div id="how-can-i-measure-pre-install-campaigns" />

### How can I measure pre-install campaigns?

There are four ways to measure pre-install campaigns. For more information, see the [Setup section](/docs/appsflyer-factory-preinstall-using-manifest-android#setup) in this article.

<div id="viewing-pre-install-data" />

### Viewing pre-install data

Pre-installs appear in the AppsFlyer dashboard under the attributed media source, just like any other install event. Their campaign name, however, is always **Pre-install**.

<div id="note" />

> 📘 **Note**
>
> You can specify different campaign names for pre-installs with the [SDK API Method](/docs/appsflyer-factory-preinstall-using-manifest-android#sdk-api-method).

<div id="note-1" />

> 📘 **Note**
>
> Starting May 24, 2022:
>
> * Match\_type for factory preinstall campaigns is displayed as `preload_conf` in raw data reports.
> * AppsFlyer displays in dashboards the ad network that drove the preload and ad networks that contributed to the first app launch. Learn more about <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#preload-campaigns">preload campaigns</Anchor>.

<div id="setup" />

## Setup

Select from one of the following methods to measure pre-install campaigns.

| Method Name | Requires Multiple APKs? | Guarantees Pre-install Attribution? | Requires Action from Media Source or Manufacturer? |
| --- | --- | --- | --- |
| System Properties | No | Yes | Yes |
| SDK API | Yes | No | No |
| Name in Manifest File | Yes | No | No |
| Path Way | No | No | Yes |

<div id="system-properties-method-recommended" />

<Accordion title="System properties method (recommended)">

Use SDK version `V4.0+`.

This method is recommended because it is the most robust of all; however, consider that for all subsequent app installs, the pre-install media source is always attributed. This is regardless of whether the install is new or a reinstall. 

The system properties method requires actions on both the developer and the manufacturer's side.

<div id="developer" />

#### Developer

You need to provide the manufacturer or media source with the APK. The default APK is provided. This method doesn't require a separate APK.

Create a file called `pre_install.appsflyer`. In the file, add a key-value pair:

`<package_name>=<media_source>`

For example:

`com.appsflyer.sampleapp=huawei`

**To specify additional pre-install parameters:**

In the **pre\_install.appsflyer** file, pass the additional parameters in JSON format. For example:

```json
com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
```

<div id="important-1" />

> 🚧 **Important!**
>
> It's important to note the following behavior when using this option:
>
> * In raw-data, it sets Channel to "Pre-install"
> * If the `pid` parameter is not present in the JSON, the Media Source appears as "None" in raw-data
> * In the JSON configuration, if the `c` parameter is not present then the campaign name is set to "Pre-install"
> * If the JSON is malformed, the passed string is treated as the Media Source name

Once you have the pre\_install.appsflyer file, give it to the media source or manufacturer together with the APK.

<div id="manufacturer" />

#### Manufacturer

The manufacturer places the ***pre\_install.appsflyer*** in a file path of its choosing. The **pre\_install.appsflyer** file permissions should be set to 744.

The manufacturer then edits the system properties file in order to point to the ***pre\_install.appsflyer*** file. To do so, the manufacturer needs to add a key-value pair to system properties.

<div id="note-2" />

> 📘 **Note**
>
> Root permissions are required for this step. Root permissions are also required when testing preinstall configuration. See the [Testing section](/docs/appsflyer-factory-preinstall-using-manifest-android#testing-pre-install-configuration) for more details.

**Adding a Key-Value Pair to Android System Properties:**

```bash
adb shell su
setprop ro.appsflyer.preinstall.path /data/pre_install.appsflyer
```

An alternative method is to retrieve the system-properties-file from the android file system, edit it, and push it back:

```bash
adb root
adb remount
adb pull /system/build.prop
echo ro.appsflyer.preinstall.path=/data/pre_install.appsflyer >> build.prop
adb push build.prop /system/build.prop
adb shell chmod 744 /system/build.prop
adb reboot
```

<div id="advantages" />

#### Advantages

No need to maintain different APKs for each media source or manufacturer. No need to make changes and add paths to the app on Google Play. Manufacturers can use custom paths and there are no dependencies between multiple preinstalled apps running on different devices.

This method ensures attribution to preinstall campaigns and media sources. Even if a user updates the app before launching it or installs the app after clicking an ad, the preinstall is still attributed to the preinstall media source or manufacturer.

<div id="disadvantages" />

#### Disadvantages

Some responsibility is transferred over to the media source or manufacturer. The developers need to be sure that the manufacturer or media source takes the necessary steps. Moreover, this method might be a little harder for the app developer to test.

</Accordion>

<div id="sdk-api-method" />

<Accordion title="SDK API method">

The SDK API method provides a native way to specify the manufacturer or media source name to which the pre-install is attributed.

To use this method, add the following method call in the AFApplication class before initializing the SDK:

`setPreinstallAttribution(String mediaSource, String campaign, String siteId)`

<div id="when-working-with-a-media-source" />

#### When working with a media source

```java
AppsFlyerLib.getInstance().setPreinstallAttribution("MEDIA_SOURCE_NAME", "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

<div id="when-working-with-a-manufacturer" />

#### When working with a manufacturer

```java
AppsFlyerLib.getInstance().setPreinstallAttribution(android.os.Build.MANUFACTURER, "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

<div id="note-3" />

> 📘 **Note**
>
> * The media source parameter is mandatory.
> * The `android.os.Build.MANUFACTURER` property holds the manufacturer name as configured by the operating system. Using this property doesn't guarantee that you get the manufacturer name in the same format across devices from that manufacturer. Make sure that this property holds the manufacturer name as expected.
> * The `campaign` and `siteId` parameters are optional but are required by the `setPreinstallAttribution` method. If you don't want to specify `campaign` and `siteId`, pass null in both.

<div id="advantages-1" />

#### Advantages

The SDK API method lets you retrieve the manufacturer name programmatically. No matter the manufacturer, the SDK method retrieves the name directly from the device. This means that you can maintain one APK for all manufacturers that you collaborate with.

The `setPreinstallAttribution` method allows you to specify the campaign name. You can separate each manufacturer or media source into different campaigns, rather than have all of them set under the "Pre-install" campaign.

<div id="disadvantages-1" />

#### Disadvantages

If you are working directly with manufacturers, you have to maintain two versions of your APK, one for manufacturers and another for Google play. In either case, more than one APK is required.

If you are working with several media sources that communicate with the manufacturer on your behalf, you need to maintain a separate APK for each media source.

In some cases, the install might not be attributed to the pre-install media source:

* A user with a new device updates the pre-installed app directly from Google Play without first launching it, the install is considered organic.
* A user with a new device updates the app from Google Play after clicking an ad, the install is attributed to the media source that serves the ad.

<div id="tip" />

> 👍 **Tip**
>
> You can implement logic in the app to make sure that the install is counted as pre-install, even if the scenarios above take place. Both the Play Store APK and the APK intended for Pre Install should contain that logic.
>
> **Example:**
>
> * You know that apps are pre-installed on devices of a given manufacturer and model. These devices are also running with a given carrier.
> * When the app launches, you can check for these conditions when the app launches. If these conditions are met, the install is recorded as pre-install. Since the logic also exists in the Play Store APK, the install is recorded as Pre Install even if the user updates the app before launching it.

</Accordion>

<div id="name-in-manifest-file-method" />

<Accordion title="Name in manifest file method">

The name in the manifest method requires you to add a metadata tag to the app's manifest file. You need to repeat this step for every media source or manufacturer that you collaborate with.

Add a metadata tag before the closing application tag:

```html Markup
...
    <meta-data android:name="AF_PRE_INSTALL_NAME" android:value="market_name"/>
  </application>
</manifest>
```

When the app launches for the first time, the AppsFlyer SDK detects this metadata tag in the manifest file and attributes the install accordingly.

<div id="advantages-2" />

#### Advantages

The name in the manifest method is considered an easy method for attributing pre-install campaigns. There is only one tag to add to the manifest. In addition, the media source or manufacturer doesn't have to do anything on their end in order to enable campaign measuring.

<div id="disadvantages-2" />

#### Disadvantages

Since the metadata tag specifies the media source or manufacturer name, you need to maintain different sets of APKs, one for each media source or manufacturer.

In some cases, the install might not be attributed to the pre-install media source:

* A user with a new device updates the pre-installed app directly from Google Play without first launching it, the install is considered organic.
* A user with a new device installs the app from Google Play after clicking an ad, the install is attributed to the media source that serves the ad.

</Accordion>

<div id="pathway-method" />

<Accordion title="Pathway method">

<div id="note-4" />

> 📘 **Note**
>
> Supported by SDK version 4.5.0 or later.

This method requires both the developer and the manufacturer to perform some actions on their end.

<div id="developer-1" />

#### Developer

The pathway method allows you to specify a path to a file that holds the name of the media source or manufacturer. There are three steps that you need to complete:

1. Create a file that contains a key-value pair. The file should be called ***pre\_install.appsflyer***. In the file, specify the key-value pair in the format of `<PACKAGE_NAME>`=`<MEDIA_SOURCE>` For example, `com.appsflyer.sampleapp=my_media_source`.  

   <div id="passing-additional-pre-install-parameters" />

   #### Passing additional pre-install parameters

   You can specify additional pre-install parameters in the file using JSON. For example, you can add the following key-value pair in the **pre\_install.appsflyer** file:

   ```json
   com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
   ```

   <div id="important-2" />

   > 🚧 **Important!**
   >
   > It's important to note the following behaviors when using this option:
   >
   > 1. It sets "Pre-install" as af\_channel
   > 2. If pid is not present in the JSON, the Media Source appears as "None".
   > 3. In the JSON configuration, if c is not present then the campaign name is set to "Pre-install"
   > 4. If the JSON is malformed, the passed string is treated as the Media Source name


   Once you have the pre\_install.appsflyer file, give it to the media source or manufacturer together with the APK.
2. Talk to the media source or manufacturer and agree with them on a path where they put the file. The recommended path is "/data/local/tmp/pre\_install.appsflyer".
3. Once a path is agreed upon, specify it in the manifest file. Place the following snippet before the closing application tag:  

   ```html Markup
   <meta-data android:name="AF_PRE_INSTALL_PATH" 
         android:value="/data/local/temp/pre_install.appsflyer" />
   ```

<div id="manufacturer-1" />

#### Manufacturer

The manufacturer needs to put the file in the path that is agreed upon. The pre\_install.appsflyer file permissions should be set to 744.

Once the app launches, the SDK looks inside the manifest file, sees the specified path and looks for the file there. When it finds it, it attributes the install according to the media source that is specified in it.

<div id="advantages-3" />

#### Advantages

AppsFlyer looks for the **pre\_install.appsflyer** file in two default paths:

```bash
/data/local/tmp/pre_install.appsflyer
OR 
/etc/pre_install.appsflyer
```

Some manufacturers prefer to put the file in a non-default path. In such case you can specify this non-default path in the manifest file.

<div id="important-3" />

> 🚧 **Important!**
>
> Non-default path requires SDK version 4.8 or later
>
> Although non-default paths are allowed, we recommend implementing the [System Properties method](/docs/appsflyer-factory-preinstall-using-manifest-android#system-properties-method-recommended) instead.

<div id="disadvantages-3" />

#### Disadvantages

You need to maintain separate ***pre\_install.appsflyer*** files for different media sources or manufacturers.

The manufacturer might want to put the ***pre\_install.appsflyer*** file in a non-default path. In this case, you need to maintain separate APKS for each non-default path.

If a **non-default path** is used, the install might not be attributed to the pre-install media source:

* A user with a new device updates the pre-installed app directly from Google Play without first launching it, the install is considered organic.
* A user with a new device installs the app from Google Play after clicking an ad, the install is attributed to the media source that serves the ad.

</Accordion>

<div id="testing-pre-install-configuration" />

## Testing pre-install configuration

This section demonstrates how to test and verify your pre-install configuration.

<div id="important-4" />

> 🚧 **Important!**
>
> Before you start testing, make sure to <Anchor target="_blank" href="/marketers/docs/registering-test-devices">allowlist the devices</Anchor> you are using for testing. Also, make sure to set the debug log to true in the AFApplication class.
>
> ```java
> AppsFlyerLib.getInstance().setDebugLog(true);
> ```

<div id="verifying-the-configuration-in-the-app" />

<Accordion title="Verifying the configuration in the app">

<div id="tip-1" />

> 👍 **Tip**
>
> To avoid caching issues and for best results, it is recommended that you clean the project before building it. In Android Studio, click on ***Build*** in the context menu and choose ***Clean Project***.

Build your application in Android Studio and install it on the test device. Once the application launches, open the Logcat in Android studio and filter by "AppsFlyer". You should see the attributed install with all the details. See the screenshots below for illustration:

<Image align="center" alt="pre_install_logcat.png" src="https://files.readme.io/f02d39fcb7b17654286b1d79670ef80060696e28918425c7893d392e479c5de1-360002653385.png" />

<Image align="center" alt="pre_install_logcat_2.png" src="https://files.readme.io/ce57427b0fb286e632d416378bb65f98370122e6d026ecba99e602524b8351d6-360002655609.png" />

</Accordion>

<div id="verifying-the-configuration-in-the-appsflyer-dashboard" />

<Accordion title="Verifying the configuration in the AppsFlyer dashboard">

If the configuration is successful, a non-organic install that is attributed to a manufacturer or media source appears in the dashboard. The install event is also listed under the "Pre-install" campaign.

Head over to your AppsFlyer account and open the dashboard for the app that you are testing. Follow the steps below:

1. In the overview page, filter by media sources and choose the media source:  

   <Image align="center" alt="choose_media_source.png" src="https://files.readme.io/6d9ac04a23b97e12c1103e1d8dd7976949485777a89b2545e2704803b486829e-360002655629.png" />
2. In the ***Breakdown By Campaign*** graph, you can see that the install that is attributed to "my media source" comes from a Pre-install campaign:  

    <Image align="center" alt="" src="https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png" />
   You can also verify that the install is attributed correctly by viewing the ***Aggregated Performance Report***. In it, you can see the media source and campaign. See the screenshot below where "My Media Source" is the media source and the campaign is Pre-install:  

    <Image align="center" alt="" src="https://files.readme.io/d02e89d215e864ad8e96fff97c9dd279d906486ed2036ed27dc5e229ff8935b3-360002653425.png" />
3. Repeat the process for all manufacturers or media sources that you collaborate with for pre-install campaigns.

</Accordion>

<div id="special-cases" />

## Special cases

<div id="multiple-preinstall-apps-on-the-same-device" />

<Accordion title="Multiple pre-install apps on the same device">

If you have campaigns for several apps that are installed on the same device, you can measure attribution using each of the four methods:

* Name in manifest method - for each app, specify the media source or manufacturer in the Manifest.xml of each app.
* SDK API method - for each app, specify the media source or manufacturer in the SDK API method for pre-install.
* For system properties or pathway methods - can specify the apps and their corresponding media source in the ***pre\_install.appsflyer*** file. Each app info should be added in a new line in the file. For example:

  ```bash
  com.appsflyer.tester=market_name
  com.newapp.newapp=market_name
  com.game.king=market_name
  ```

</Accordion>

<div id="sending-install-postbacks" />

<Accordion title="Sending install postbacks">

If the media source or manufacturer that you collaborate with is an <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#your-integrated-partners">AppsFlyer partner</Anchor>, you can enable postbacks for installs.

To do so, make sure that the media source name is equivalent to the media source pid as it is configured by AppsFlyer.

For example, if you are collaborating with market\_name, its pid is market\_name\_int. You can see the pid by examining the <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#click-through-attribution">attribution link of an integrated partner</Anchor>.

</Accordion>

<div id="agencies" />

<Accordion title="Agencies">

Currently, agencies cannot be attributed with pre-installs.

If the af\_prt (parameter for agency name) is a part of the pre-install data, and the user launches the pre-installed app:

* The user is attributed to the media source used by the agency (pid=).
* The client can access the full user-level data.
* The user is NOT attributed to the agency.
* The agency can't access the user-level data.

</Accordion>

<div data-zendesk-anchors="h_01J421581P06FTM7B3XG2GYB2P=introduction what-is-a-preinstall-campaign=what-is-a-pre-install-campaign h_01J421581P6GYK60D5JQ9PK93N=what-is-a-pre-install-campaign h_01J421581PBQQ5AS3S4JPX52CF=important benefits-of-recording-installs-from-preinstall-campaigns=benefits-of-recording-installs-from-pre-install-campaigns h_01J421581P5MS4X9BHSJ3TTWBF=benefits-of-recording-installs-from-pre-install-campaigns how-can-i-measure-preinstall-campaigns=how-can-i-measure-pre-install-campaigns h_01J421581PEZZW2R244ZX9HX0R=how-can-i-measure-pre-install-campaigns viewing-preinstall-data=viewing-pre-install-data h_01J421581PS1CEPK3NN7AZ0ZDE=viewing-pre-install-data h_01J421581PDE1CEXRS6BYTDV35=note h_01J421581PKQTX47GC62K4AB9A=note-1 h_01J421581P28NEVB44R3XTPY75=setup h_01J421581QNSQ7W3VYFDVZ1423=system-properties-method-recommended h_01J421581Q8ZAPZS12PEG4VW3N=developer h_01J421581QYRNXCP16GY8CJTKT=important-1 h_01J421581QF6Y6MY28N5MR5BTM=manufacturer h_01J421581QBFMVT3KPCPPFRX42=note-2 h_01J421581QEPAC0WZK93HH3QYP=advantages h_01J421581QCG3HARVZVECMHQ1K=disadvantages h_01J421581QQ3VJSSQ06DKZQ0BQ=sdk-api-method h_01J421581Q6F1AD0SYXEEJB8FB=when-working-with-a-media-source h_01J421581Q3YSNH7KXQXET7FD4=when-working-with-a-manufacturer h_01J421581QRYRWY2WJKCBHQBFG=note-3 advantages::d999b734=advantages-1 h_01J421581QWHP73CA7P13WAQ7Q=advantages-1 disadvantages::92772f7d=disadvantages-1 h_01J421581QRRFBJWZB5Z6M08BE=disadvantages-1 h_01J421581QF11R7ZXAXRP2YQYR=tip h_01J421581QJ2J54HJFTXF3G5S0=name-in-manifest-file-method advantages::3f0b06fb=advantages-2 h_01J421581Q8WFYYFQJ45KPWZWP=advantages-2 disadvantages::919cb3e3=disadvantages-2 h_01J421581QYC02EKB5P0FN5G3F=disadvantages-2 h_01J421581QNFT2E2P3A6MR3BB5=pathway-method h_01J421581QF43JW6A0B48SK9AE=note-4 developer::7c51f631=developer-1 h_01J421581QB4TH9DMA2ANHG7RD=developer-1 passing-additional-preinstall-parameters=passing-additional-pre-install-parameters h_01J421581Q45AEN4GEM5ZKPYRN=passing-additional-pre-install-parameters h_01J421581Q3MMTKPP3E8SZD13F=important-2 manufacturer::56d9649d=manufacturer-1 h_01J421581Q16AVHRCTHME67VHQ=manufacturer-1 advantages::1fb76031=advantages-3 h_01J421581QTRY13FVNQRMG0H2B=advantages-3 h_01J421581Q0P5VQJHQ9X3VRW8N=important-3 disadvantages::c9cae863=disadvantages-3 h_01J421581QSNNCHPC2VSF48FT3=disadvantages-3 testing-preinstall-configuration=testing-pre-install-configuration h_01J421581QYHRHF119J4YBZD23=testing-pre-install-configuration h_01J421581QW0XKZ635A194W80J=important-4 h_01J421581QPXQDFX5G11B7GSNA=verifying-the-configuration-in-the-app h_01J421581QSZPZVZ6GGQST5FWS=tip-1 h_01J421581Q7PGHJ2HBX1ZDNJS6=verifying-the-configuration-in-the-appsflyer-dashboard h_01J421581Q624TH08PX24B1P3X=special-cases h_01J421581QQHB8624SS6FSSA6D=multiple-preinstall-apps-on-the-same-device h_01J421581Q86AB5GTM91ARYJ23=sending-install-postbacks h_01J421581RD2WQ6SPES729GJEP=agencies" />
