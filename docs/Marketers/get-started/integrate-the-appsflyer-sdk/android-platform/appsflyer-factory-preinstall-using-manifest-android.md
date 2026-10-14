---
title: "AppsFlyer factory preinstall using manifest (Android)"
x-zendesk:
  id: 207032166
  url: https://support.appsflyer.com/hc/en-us/articles/207032166-AppsFlyer-factory-preinstall-using-manifest-Android
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Android platform
  section_id: 6551190827921
  position: 3
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution, Agencies]
  labels: [Android, Pre-Install, Attribution, Metrics, Advertisers, Agencies, af_pre_install_name, Developers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2014-10-13T11:14:04Z'
  edited_at: '2024-07-30T14:37:09Z'
---
**At a glance:** Attribute app installs to device manufacturers for apps added to devices before leaving the factory. **Note**: See [all other preload attribution methods](/docs/appsflyer-attribution-model#preload-campaigns).

![pre-install-intro-breakdown.png](https://files.readme.io/f14231089f68ffa90dc90700397463d363c08b8266e0d18677e9ccf3c28b0828-360002653365.png)

## Introduction

### What is a pre-install campaign?

Pre-install campaigns allow app owners to reach vast audiences without running online campaigns.

In pre-install campaigns, app owners can ask device manufacturers to **pre-install their apps on devices before they leave the factory**.

Pre-install campaigns can also be a collaboration with 3rd party media sources, which work with various manufacturers on behalf of app owners.

> 📘 **Important!**
>
> AppsFlyer counts an install once an app launches for the first time. Therefore, the number of displayed pre-installs is the number of users launching your app, and not the number of devices that have the app pre-installed on.

### Benefits of recording installs from pre-install campaigns

By attributing pre-install campaigns you can measure the:

* number of users who launch your pre-installed app
* number of app users each manufacturer brings
* LTV of each user and determine which manufacturer brings high-value users

### How can I measure pre-install campaigns?

There are four ways to measure pre-install campaigns. For more information, see the [Setup section](/docs/appsflyer-factory-preinstall-using-manifest-android#setup) in this article.

### Viewing pre-install data

Pre-installs appear in the AppsFlyer dashboard under the attributed media source, just like any other install event. Their campaign name, however, is always **Pre-install**.

> 📘 **Note**
>
> You can specify different campaign names for pre-installs with the [SDK API Method](/docs/appsflyer-factory-preinstall-using-manifest-android#sdk-api-method).

> 📘 **Note**
>
> Starting May 24, 2022:
>
> * Match\_type for factory preinstall campaigns is displayed as `preload_conf` in raw data reports.
> * AppsFlyer displays in dashboards the ad network that drove the preload and ad networks that contributed to the first app launch. Learn more about [preload campaigns](/docs/appsflyer-attribution-model#preload-campaigns).

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

#### Developer

You need to provide the manufacturer or media source with the APK. The default APK is provided. This method doesn't require a separate APK.

Create a file called `pre_install.appsflyer`. In the file, add a key-value pair:

`<package_name>=<media_source>`

For example:

`com.appsflyer.sampleapp=huawei`

**To specify additional pre-install parameters:**

In the **pre\_install.appsflyer** file, pass the additional parameters in JSON format. For example:

```
com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
```

> 📘 **Important!**
>
> It's important to note the following behavior when using this option:
>
> * In raw-data, it sets Channel to "Pre-install"
> * If the `pid` parameter is not present in the JSON, the Media Source appears as "None" in raw-data
> * In the JSON configuration, if the `c` parameter is not present then the campaign name is set to "Pre-install"
> * If the JSON is malformed, the passed string is treated as the Media Source name

Once you have the pre\_install.appsflyer file, give it to the media source or manufacturer together with the APK.

#### Manufacturer

The manufacturer places the ***pre\_install.appsflyer*** in a file path of its choosing. The **pre\_install.appsflyer** file permissions should be set to 744.

The manufacturer then edits the system properties file in order to point to the ***pre\_install.appsflyer***file. To do so, the manufacturer needs to add a key-value pair to system properties.

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

#### Advantages

No need to maintain different APKs for each media source or manufacturer. No need to make changes and add paths to the app on Google Play. Manufacturers can use custom paths and there are no dependencies between multiple preinstalled apps running on different devices.

This method ensures attribution to preinstall campaigns and media sources. Even if a user updates the app before launching it or installs the app after clicking an ad, the preinstall is still attributed to the preinstall media source or manufacturer.

#### Disadvantages

Some responsibility is transferred over to the media source or manufacturer. The developers need to be sure that the manufacturer or media source takes the necessary steps. Moreover, this method might be a little harder for the app developer to test.

</Accordion>

<div id="sdk-api-method" />

<Accordion title="SDK API method">

The SDK API method provides a native way to specify the manufacturer or media source name to which the pre-install is attributed.

To use this method, add the following method call in the AFApplication class before initializing the SDK:

`setPreinstallAttribution(String mediaSource, String campaign, String siteId)`

#### When working with a media source

```
AppsFlyerLib.getInstance().setPreinstallAttribution("MEDIA_SOURCE_NAME", "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

#### When working with a manufacturer

```
AppsFlyerLib.getInstance().setPreinstallAttribution(android.os.Build.MANUFACTURER, "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

> 📘 **Note**
>
> * The media source parameter is mandatory.
> * The `android.os.Build.MANUFACTURER` property holds the manufacturer name as configured by the operating system. Using this property doesn't guarantee that you get the manufacturer name in the same format across devices from that manufacturer. Make sure that this property holds the manufacturer name as expected.
> * The `campaign` and `siteId` parameters are optional but are required by the `setPreinstallAttribution` method. If you don't want to specify `campaign` and `siteId`, pass null in both.

#### Advantages

The SDK API method lets you retrieve the manufacturer name programmatically. No matter the manufacturer, the SDK method retrieves the name directly from the device. This means that you can maintain one APK for all manufacturers that you collaborate with.

The `setPreinstallAttribution` method allows you to specify the campaign name. You can separate each manufacturer or media source into different campaigns, rather than have all of them set under the "Pre-install" campaign.

#### Disadvantages

If you are working directly with manufacturers, you have to maintain two versions of your APK, one for manufacturers and another for Google play. In either case, more than one APK is required.

If you are working with several media sources that communicate with the manufacturer on your behalf, you need to maintain a separate APK for each media source.

In some cases, the install might not be attributed to the pre-install media source:

* A user with a new device updates the pre-installed app directly from Google Play without first launching it, the install is considered organic.
* A user with a new device updates the app from Google Play after clicking an ad, the install is attributed to the media source that serves the ad.

> 📘 **Tip**
>
> You can implement logic in the app to make sure that the install is counted as pre-install, even if the scenarios above take place. Both the Play Store APK and the APK intended for Pre Install should contain that logic.
>
> **Example:**
>
> * You know that apps are pre-installed on devices of a given manufacturer and model. These devices are also running with a given carrier.
> * When the app launches, you can check for these conditions when the app launches. If these conditions are met, the install is recorded as pre-install. Since the logic also exists in the Play Store APK, the install is recorded as Pre Install even if the user updates the app before launching it.

</Accordion>

<Accordion title="Name in manifest file method">

The name in the manifest method requires you to add a metadata tag to the app's manifest file. You need to repeat this step for every media source or manufacturer that you collaborate with.

Add a metadata tag before the closing application tag:

```
...
    <meta-data android:name="AF_PRE_INSTALL_NAME" android:value="market_name"/>
  </application>
</manifest>
```

When the app launches for the first time, the AppsFlyer SDK detects this metadata tag in the manifest file and attributes the install accordingly.

#### Advantages

The name in the manifest method is considered an easy method for attributing pre-install campaigns. There is only one tag to add to the manifest. In addition, the media source or manufacturer doesn't have to do anything on their end in order to enable campaign measuring.

#### Disadvantages

Since the metadata tag specifies the media source or manufacturer name, you need to maintain different sets of APKs, one for each media source or manufacturer.

In some cases, the install might not be attributed to the pre-install media source:

* A user with a new device updates the pre-installed app directly from Google Play without first launching it, the install is considered organic.
* A user with a new device installs the app from Google Play after clicking an ad, the install is attributed to the media source that serves the ad.

</Accordion>

<Accordion title="Pathway method">

> 📘 **Note**
>
> Supported by SDK version 4.5.0 or later.

This method requires both the developer and the manufacturer to perform some actions on their end.

#### Developer

The pathway method allows you to specify a path to a file that holds the name of the media source or manufacturer. There are three steps that you need to complete:

1. Create a file that contains a key-value pair. The file should be called ***pre\_install.appsflyer***. In the file, specify the key-value pair in the format of `<PACKAGE_NAME>`=`<MEDIA_SOURCE>` For example, `com.appsflyer.sampleapp=my_media_source`.  

   #### Passing additional pre-install parameters

   You can specify additional pre-install parameters in the file using JSON. For example, you can add the following key-value pair in the **pre\_install.appsflyer** file:

   ```
   com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
   ```

   <br /><br />**Note**<br />#### Important!

   It's important to note the following behaviors when using this option:

   1. It sets "Pre-install" as af\_channel
   2. If pid is not present in the JSON, the Media Source appears as "None".
   3. In the JSON configuration, if c is not present then the campaign name is set to "Pre-install"
   4. If the JSON is malformed, the passed string is treated as the Media Source name

   Once you have the pre\_install.appsflyer file, give it to the media source or manufacturer together with the APK.
2. Talk to the media source or manufacturer and agree with them on a path where they put the file. The recommended path is "/data/local/tmp/pre\_install.appsflyer".
3. Once a path is agreed upon, specify it in the manifest file. Place the following snippet before the closing application tag:  

   ```xml
   <meta-data android:name="AF_PRE_INSTALL_PATH" 
         android:value="/data/local/temp/pre_install.appsflyer" />
   ```

#### Manufacturer

The manufacturer needs to put the file in the path that is agreed upon. The pre\_install.appsflyer file permissions should be set to 744.

Once the app launches, the SDK looks inside the manifest file, sees the specified path and looks for the file there. When it finds it, it attributes the install according to the media source that is specified in it.

#### Advantages

AppsFlyer looks for the **pre\_install.appsflyer** file in two default paths:

```
/data/local/tmp/pre_install.appsflyer
OR 
/etc/pre_install.appsflyer
```

Some manufacturers prefer to put the file in a non-default path. In such case you can specify this non-default path in the manifest file.

> 📘 **Important!**
>
> Non-default path requires SDK version 4.8 or later
>
> Although non-default paths are allowed, we recommend implementing the [System Properties method](/docs/appsflyer-factory-preinstall-using-manifest-android#system-properties-method-recommended) instead.

#### Disadvantages

You need to maintain separate ***pre\_install.appsflyer*** files for different media sources or manufacturers.

The manufacturer might want to put the ***pre\_install.appsflyer*** file in a non-default path. In this case, you need to maintain separate APKS for each non-default path.

If a **non-default path** is used, the install might not be attributed to the pre-install media source:

* A user with a new device updates the pre-installed app directly from Google Play without first launching it, the install is considered organic.
* A user with a new device installs the app from Google Play after clicking an ad, the install is attributed to the media source that serves the ad.

</Accordion>

## Testing pre-install configuration

This section demonstrates how to test and verify your pre-install configuration.

> 📘 **Important!**
>
> Before you start testing, make sure to [allowlist the devices](/docs/registering-test-devices) you are using for testing.
> Also, make sure to set the debug log to true in the AFApplication class.
>
> ```
> AppsFlyerLib.getInstance().setDebugLog(true);
> ```

<Accordion title="Verifying the configuration in the app">

> 📘 **Tip**
>
> To avoid caching issues and for best results, it is recommended that you clean the project before building it. In Android Studio, click on ***Build*** in the context menu and choose ***Clean Project***.

Build your application in Android Studio and install it on the test device. Once the application launches, open the Logcat in Android studio and filter by "AppsFlyer". You should see the attributed install with all the details. See the screenshots below for illustration:

![pre_install_logcat.png](https://files.readme.io/f02d39fcb7b17654286b1d79670ef80060696e28918425c7893d392e479c5de1-360002653385.png)

![pre_install_logcat_2.png](https://files.readme.io/ce57427b0fb286e632d416378bb65f98370122e6d026ecba99e602524b8351d6-360002655609.png)

</Accordion>

<Accordion title="Verifying the configuration in the AppsFlyer dashboard">

If the configuration is successful, a non-organic install that is attributed to a manufacturer or media source appears in the dashboard. The install event is also listed under the "Pre-install" campaign.

Head over to your AppsFlyer account and open the dashboard for the app that you are testing. Follow the steps below:

1. In the overview page, filter by media sources and choose the media source:  

   ![choose_media_source.png](https://files.readme.io/6d9ac04a23b97e12c1103e1d8dd7976949485777a89b2545e2704803b486829e-360002655629.png)
2. In the ***Breakdown By Campaign*** graph, you can see that the install that is attributed to "my media source" comes from a Pre-install campaign:  

    [![](https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png)](https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png)  
   You can also verify that the install is attributed correctly by viewing the ***Aggregated Performance Report***. In it, you can see the media source and campaign. See the screenshot below where "My Media Source" is the media source and the campaign is Pre-install:  

    [![](https://files.readme.io/d02e89d215e864ad8e96fff97c9dd279d906486ed2036ed27dc5e229ff8935b3-360002653425.png)](https://files.readme.io/d02e89d215e864ad8e96fff97c9dd279d906486ed2036ed27dc5e229ff8935b3-360002653425.png)
3. Repeat the process for all manufacturers or media sources that you collaborate with for pre-install campaigns.

</Accordion>

## Special cases

<Accordion title="Multiple pre-install apps on the same device">

If you have campaigns for several apps that are installed on the same device, you can measure attribution using each of the four methods:

* Name in manifest method - for each app, specify the media source or manufacturer in the Manifest.xml of each app.
* SDK API method - for each app, specify the media source or manufacturer in the SDK API method for pre-install.
* For system properties or pathway methods - can specify the apps and their corresponding media source in the ***pre\_install.appsflyer*** file. Each app info should be added in a new line in the file. For example:

  ```
  com.appsflyer.tester=market_name
  com.newapp.newapp=market_name
  com.game.king=market_name
  ```

</Accordion>

<Accordion title="Sending install postbacks">

If the media source or manufacturer that you collaborate with is an [AppsFlyer partner](/docs/set-up-an-integrated-partner#your-integrated-partners), you can enable postbacks for installs.

To do so, make sure that the media source name is equivalent to the media source pid as it is configured by AppsFlyer.

For example, if you are collaborating with market\_name, its pid is market\_name\_int. You can see the pid by examining the [attribution link of an integrated partner](/docs/set-up-an-integrated-partner#click-through-attribution).

</Accordion>

<Accordion title="Agencies">

Currently, agencies cannot be attributed with pre-installs.

If the af\_prt (parameter for agency name) is a part of the pre-install data, and the user launches the pre-installed app:

* The user is attributed to the media source used by the agency (pid=).
* The client can access the full user-level data.
* The user is NOT attributed to the agency.
* The agency can't access the user-level data.

</Accordion>
