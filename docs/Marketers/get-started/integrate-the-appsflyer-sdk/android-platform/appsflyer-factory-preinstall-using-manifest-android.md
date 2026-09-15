---
title: "AppsFlyer factory preinstall using manifest (Android)"
excerpt: "Learn how to attribute app installs to device manufacturers for apps added to Android devices before leaving the factory."
---
At a glance: Attribute app installs to device manufacturers for apps added to devices before leaving the factory. 

> 📘 Note
>
> See [all other preload attribution methods](https://support.appsflyer.com/hc/articles/207447053#preload-campaigns).

![pre-install-intro-breakdown.png](https://files.readme.io/f14231089f68ffa90dc90700397463d363c08b8266e0d18677e9ccf3c28b0828-360002653365.png)

## Introduction

### What is a pre-install campaign?

Pre-install campaigns allow app owners to reach vast audiences without running online campaigns.

In pre-install campaigns, app owners can ask device manufacturers to **pre-install their apps on devices before they leave the factory**.

Pre-install campaigns can also be a collaboration with 3rd party media sources, which work with various manufacturers on behalf of app owners.

> ❗️ Important!
>
> AppsFlyer counts an install once an app launches for the first time. Therefore, the number of displayed pre-installs is the number of users launching your app, and not the number of devices that have the app pre-installed on.

### Benefits of recording installs from pre-install campaigns

By attributing pre-install campaigns you can measure the:

- number of users who launch your pre-installed app
- number of app users each manufacturer brings
- LTV of each user and determine which manufacturer brings high-value users

### How can I measure pre-install campaigns?

There are four ways to measure pre-install campaigns. For more information, see the [Setup section](https://support.appsflyer.com/hc/articles/207032166#setup) in this article.

### Viewing pre-install data

Pre-installs appear in the AppsFlyer dashboard under the attributed media source, just like any other install event. Their campaign name, however, is always **Pre-install**.

> 📘 Note
>
> You can specify different campaign names for pre-installs with the [SDK API Method](https://support.appsflyer.com/hc/articles/207032166#sdk-api-method).

> 📘 Note
>
> Starting May 24, 2022:
>
> - Match_type for factory preinstall campaigns is displayed as `preload_conf` in raw data reports.
> - AppsFlyer displays in dashboards the ad network that drove the preload and ad networks that contributed to the first app launch. Learn more about [preload campaigns](https://support.appsflyer.com/hc/articles/207447053#preload-campaigns).

## Setup

Select from one of the following methods to measure pre-install campaigns.

| Method Name | Requires Multiple APKs? | Guarantees Pre-install Attribution? | Requires Action from Media Source or Manufacturer? |
| --- | --- | --- | --- |
| System Properties | No | Yes | Yes |
| SDK API | Yes | No | No |
| Name in Manifest File | Yes | No | No |
| Path Way | No | No | Yes |

### System properties method (recommended)

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

In the **pre_install.appsflyer** file, pass the additional parameters in JSON format. For example:

```json
com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
```

> ❗️ Important!
>
> It's important to note the following behavior when using this option:
>
> - In raw-data, it sets Channel to "Pre-install"
> - If the `pid` parameter is not present in the JSON, the Media Source appears as "None" in raw-data
> - In the JSON configuration, if the `c` parameter is not present then the campaign name is set to "Pre-install"
> - If the JSON is malformed, the passed string is treated as the Media Source name

Once you have the pre_install.appsflyer file, give it to the media source or manufacturer together with the APK.

#### Manufacturer

The manufacturer places the _**pre_install.appsflyer**_ in a file path of its choosing. The **pre_install.appsflyer** file permissions should be set to 744.

The manufacturer then edits the system properties file in order to point to the _**pre_install.appsflyer**_ file. To do so, the manufacturer needs to add a key-value pair to system properties.

> 📘 Note
>
> Root permissions are required for this step. Root permissions are also required when testing preinstall configuration. See the [Testing section](https://support.appsflyer.com/hc/articles/207032166#testing-preinstall-configuration) for more details.

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

### SDK API method

The SDK API method provides a native way to specify the manufacturer or media source name to which the pre-install is attributed.

To use this method, add the following method call in the AFApplication class before initializing the SDK:

`setPreinstallAttribution(String mediaSource, String campaign, String siteId)`

#### When working with a media source

```java
AppsFlyerLib.getInstance().setPreinstallAttribution("MEDIA_SOURCE_NAME", "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

#### When working with a manufacturer

```java
AppsFlyerLib.getInstance().setPreinstallAttribution(android.os.Build.MANUFACTURER, "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

> 📘 Note
>
> - The media source parameter is mandatory.
> - The `android.os.Build.MANUFACTURER` property holds the manufacturer name as configured by the operating system. Using this property doesn't guarantee that you get the manufacturer name in the same format across devices from that manufacturer. Make sure that this property holds the manufacturer name as expected.
> - The `campaign` and `siteId` parameters are optional but are required by the `setPreinstallAttribution` method. If you don't want to specify `campaign` and `siteId`, pass null in both.

#### Advantages

The SDK API method lets you retrieve the manufacturer name programmatically. No matter the manufacturer, the SDK method retrieves the name directly from the device. This means that you can maintain one APK for all manufacturers that you collaborate with.

The `setPreinstallAttribution` method allows you to specify the campaign name. You can separate each manufacturer or media source into different campaigns, rather than have all of them set under the "Pre-install" campaign.

#### Disadvantages

If you are working directly with manufacturers, you have to maintain two versions of your APK, one for manufacturers and another for Google play. In either case, more than one APK is required.

If you are working with several media sources that communicate with the manufacturer on your behalf, you need to maintain a separate APK for each media source.

In some cases, the install might not be attributed to the pre-install media source:

- A user with a new device updates the pre-installed app directly from Google Play without first launching it, the install is considered organic.
- A user with a new device updates the app from Google Play after clicking an ad, the install is attributed to the media source that serves the ad.

> 👍 Tip
>
> You can implement logic in the app to make sure that the install is counted as pre-install, even if the scenarios above take place. Both the Play Store APK and the APK intended for Pre Install should contain that logic.
>
> **Example:**
>
> - You know that apps are pre-installed on devices of a given manufacturer and model. These devices are also running with a given carrier.
> - When the app launches, you can check for these conditions when the app launches. If these conditions are met, the install is recorded as pre-install. Since the logic also exists in the Play Store APK, the install is recorded as Pre Install even if the user updates the app before launching it.

### Name in manifest file method

The name in the manifest method requires you to add a metadata tag to the app's manifest file. You need to repeat this step for every media source or manufacturer that you collaborate with.

Add a metadata tag before the closing application tag:

```xml
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

- A user with a new device updates the pre-installed app directly from Google Play without first launching it, the install is considered organic.
- A user with a new device installs the app from Google Play after clicking an ad, the install is attributed to the media source that serves the ad.

### Pathway method

> 📘 Note
>
> Supported by SDK version 4.5.0 or later.

This method requires both the developer and the manufacturer to perform some actions on their end.

#### Developer

The pathway method allows you to specify a path to a file that holds the name of the media source or manufacturer. There are three steps that you need to complete:

1. Create a file that contains a key-value pair. The file should be called _**pre_install.appsflyer**_. In the file, specify the key-value pair in the format of `<PACKAGE_NAME>=<MEDIA_SOURCE>`. For example, `com.appsflyer.sampleapp=my_media_source`.

##### Passing additional pre-install parameters

You can specify additional pre-install parameters in the file using JSON. For example, you can add the following key-value pair in the **pre_install.appsflyer** file:

```json
com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
```

##### Important!

It's important to note the following behaviors when using this option:

1. It sets "Pre-install" as af_channel
2. If pid is not present in the JSON, the Media Source appears as "None".
3. In the JSON configuration, if c is not present then the campaign name is set to "Pre-install"
4. If the JSON is malformed, the passed string is treated as the Media Source name

Once you have the pre_install.appsflyer file, give it to the media source or manufacturer together with the APK.

2. Talk to the media source or manufacturer and agree with them on a path where they put the file. The recommended path is "/data/local/tmp/pre_install.appsflyer".
3. Once a path is agreed upon, specify it in the manifest file. Place the following snippet before the closing application tag:

```xml
<meta-data android:name="AF_PRE_INSTALL_PATH"
         android:value="/data/local/temp/pre_install.appsflyer" />
```

#### Manufacturer

The manufacturer needs to put the file in the path that is agreed upon. The pre_install.appsflyer file permissions should be set to 744.

Once the app launches, the SDK looks inside the manifest file, sees the specified path and looks for the file there. When it finds it, it attributes the install according to the media source that is specified in it.

#### Advantages

AppsFlyer looks for the **pre_install.appsflyer** file in two default paths:

```bash
/data/local/tmp/pre_install.appsflyer
OR
/etc/pre_install.appsflyer
```

Some manufacturers prefer to put the file in a non-default path. In such case you can specify this non-default path in the manifest file.

> ❗️ Important!
>
> Non-default path requires SDK version 4.8 or later
>
> Although non-default paths are allowed, we recommend implementing the [System Properties method](#system-properties-method-recommended) instead.

#### Disadvantages

You need to maintain separate _**pre_install.appsflyer**_ files for different media sources or manufacturers.

The manufacturer might want to put the _**pre_install.appsflyer**_ file in a non-default path. In this case, you need to maintain separate APKS for each non-default path.

If a **non-default path** is used, the install might not be attributed to the pre-install media source:

- A user with a new device updates the pre-installed app directly from Google Play without first launching it, the install is considered organic.
- A user with a new device installs the app from Google Play after clicking an ad, the install is attributed to the media source that serves the ad.

## Testing pre-install configuration

This section demonstrates how to test and verify your pre-install configuration.

> ❗️ Important!
>
> Before you start testing, make sure to [allowlist the devices](https://support.appsflyer.com/hc/articles/207031996--Whitelisting-a-Test-Device) you are using for testing.
>
> Also, make sure to set the debug log to true in the AFApplication class.

```java
AppsFlyerLib.getInstance().setDebugLog(true);
```

### Verifying the configuration in the app

> 👍 Tip
>
> To avoid caching issues and for best results, it is recommended that you clean the project before building it. In Android Studio, click on _**Build**_ in the context menu and choose _**Clean Project**_.

Build your application in Android Studio and install it on the test device. Once the application launches, open the Logcat in Android studio and filter by "AppsFlyer". You should see the attributed install with all the details. See the screenshots below for illustration:

![pre_install_logcat.png](https://files.readme.io/f02d39fcb7b17654286b1d79670ef80060696e28918425c7893d392e479c5de1-360002653385.png)

![pre_install_logcat_2.png](https://files.readme.io/ce57427b0fb286e632d416378bb65f98370122e6d026ecba99e602524b8351d6-360002655609.png)

### Verifying the configuration in the AppsFlyer dashboard

If the configuration is successful, a non-organic install that is attributed to a manufacturer or media source appears in the dashboard. The install event is also listed under the "Pre-install" campaign.

Head over to your AppsFlyer account and open the dashboard for the app that you are testing. Follow the steps below:

1. In the overview page, filter by media sources and choose the media source:

![choose_media_source.png](https://files.readme.io/6d9ac04a23b97e12c1103e1d8dd7976949485777a89b2545e2704803b486829e-360002655629.png)

2. In the _**Breakdown By Campaign**_ graph, you can see that the install that is attributed to "my media source" comes from a Pre-install campaign.

You can also verify that the install is attributed correctly by viewing the _**Aggregated Performance Report**_. In it, you can see the media source and campaign. See the screenshot where "My Media Source" is the media source and the campaign is Pre-install.

3. Repeat the process for all manufacturers or media sources that you collaborate with for pre-install campaigns.

## Special cases

### Multiple pre-install apps on the same device

If you have campaigns for several apps that are installed on the same device, you can measure attribution using each of the four methods:

- Name in manifest method - for each app, specify the media source or manufacturer in the Manifest.xml of each app.
- SDK API method - for each app, specify the media source or manufacturer in the SDK API method for pre-install.
- For system properties or pathway methods - can specify the apps and their corresponding media source in the _**pre_install.appsflyer**_ file. Each app info should be added in a new line in the file. For example:

```bash
com.appsflyer.tester=market_name
com.newapp.newapp=market_name
com.game.king=market_name
```

### Sending install postbacks

If the media source or manufacturer that you collaborate with is an [AppsFlyer partner](https://support.appsflyer.com/hc/articles/4410395957521#your-integrated-partners), you can enable postbacks for installs.

To do so, make sure that the media source name is equivalent to the media source pid as it is configured by AppsFlyer.

For example, if you are collaborating with market_name, its pid is market_name_int. You can see the pid by examining the [attribution link of an integrated partner](https://support.appsflyer.com/hc/articles/4410395957521#clickthrough-attribution).

### Agencies

Currently, agencies cannot be attributed with pre-installs.

If the af_prt (parameter for agency name) is a part of the pre-install data, and the user launches the pre-installed app:

- The user is attributed to the media source used by the agency (pid=).
- The client can access the full user-level data.
- The user is NOT attributed to the agency.
- The agency can't access the user-level data.