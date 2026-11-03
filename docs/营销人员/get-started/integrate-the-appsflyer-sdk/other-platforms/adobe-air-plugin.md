---
title: Adobe AIR plugin
metadata:
  keywords:
    - github
    - Adobe
    - Air
    - Advertisers
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
  created_at: '2013-12-09T11:32:45Z'
  edited_at: '2026-10-13T00:38:01Z'
  id: 207032226
  locale: zh-cn
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/zh-cn/articles/207032226
---
> **At a glance:** Integrate AppsFlyer SDK into iOS/Android apps developed with Adobe AIR development platform to measure installs, in-app events, media sources, and more.

## Plugin information

Supported platforms:

* Android
* iOS 6+

Based on:

* iOS AppsFlyer SDK V6.0.3
* Android AppsFlyer SDK V5.4.1

## Installation and implementation

<div id="installation" />

<Accordion title="Installation">

Download the <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/blob/master/bin/AppsFlyerAIRExtension.ane">AppsFlyerAIRExtension.ane</Anchor> file from the bin folder Add the ANE to your project and make sure the IDE is marked to package it.

If the following was not added automatically, add it to the APP\_NAME-app.xml:

```html Markup
<extensions>
  <extensionID>com.appsflyer.adobeair</extensionID>
</extensions>
```

> 📘 **Notes for Android apps**
>
> * In the AppsFlyer dashboard you will need to add "air." prefix to the package name as this is added automatically by Air. For example - an app with the package name "**com.test.android**", should set the app id in the AppsFlyer Dashboard as "**air.com.test.android**".
> * Add the following permissions to Android Manifest (in the app description `APP_NAME-app.xml`):
>
>   ```html Markup
>   <uses-permission android:name="android.permission.INTERNET"/>
>   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
>   <uses-permission android:name="com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE" />
>   ```
> * Add the following metatag to Android Manifest within the application tag (in the app description `APP_NAME-app.xml`):
>
>
>   ```html Markup
>   meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />
>   ```
>
> As a result, you should see your Manifest like this:
>
> [![](https://files.readme.io/b50aa4f38d258eb2f6a01017da248fdf8a9fd21c3d83aae8bf4928094b8094b8-360010932998.png)](https://files.readme.io/b50aa4f38d258eb2f6a01017da248fdf8a9fd21c3d83aae8bf4928094b8094b8-360010932998.png)
>
> **Important:** Due to some limitations in the <Anchor target="_blank" href="https://help.adobe.com/en_US/air/build/WS5b3ccc516d4fbf351e63e3d118666ade46-7fd9.html">ADT</Anchor>, after the APK is built, it is missing some important files.
>
> To add those files (with the help of **automated** script):
>
> 1. Place into single directory of your choice:
>    * APK file
>    * Keystore that was used to sign the APK
>    * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AdobeAirExtension-AppsFlyer/blob/master/bin/af_apk_fix.sh">af\_apk\_fix.sh script</Anchor>
> 2. Run `./af_apk_fix.sh` and enter requested info when prompted.
>
> Here is what the script is doing. In case of any issues, you can perform those steps manually:
>
> 1. Decode the APK using <Anchor target="_blank" href="https://ibotpeaches.github.io/Apktool/">apktool</Anchor>. This will create app\_name folder.
>    `apktool d app_name.apk`
> 2. Download the [AppsFlyer SDK jar/aar](https://repo.maven.apache.org/maven2/com/appsflyer/af-android-sdk/5.4.1/af-android-sdk-5.4.1.aar) of the same version that was used in the APK.
> 3. Extract files `a-` and `b-` from the jar (by renaming jar into a zip) and place them into the folder with the decompiled apk to `app_name/unknown/com/appsflyer/internal`
> 4. Edit `apktool.yml` by adding these lines under `unknownFiles:`
>
>    ```
>    com/appsflyer/internal/b-: '0'
>    com/appsflyer/internal/a-: '0'
>    ```
>
>    See sample screenshot that follows.
>
>    [![](https://files.readme.io/6bacbb55e5b1a7739034db8cc03313459ad6d048313a51ef6bf1e07500165cc0-360010933018.png)](https://files.readme.io/6bacbb55e5b1a7739034db8cc03313459ad6d048313a51ef6bf1e07500165cc0-360010933018.png)
> 5. Build the APK.back (will appear under `app_name/dist` folder).
>    `apktool b app`
> 6. Sign the APK.
>
>    ```html Markup
>    jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore myKeystore.keystore app_name/dist/app_name.apk myKey
>    ```
> 7. Zipalign the apk (to be able to upload to Google Play)
>
>    ```html Markup
>    zipalign -f -v 4 app_name/dist/app_name.apk app_name/dist/zipalign_app_name.apk
>    ```
> 8. Verify zipalignment
>
>    ```html Markup
>    zipalign -c -v 4 app_name/dist/zipalign_app_name.apk
>    ```
> 9. Your apk `zipalign_app_name.apk` is ready to use!

</Accordion>

<div id="implementation" />

<Accordion title="Implementation">

Import the AppsFlyer Extension into your project:

```html Markup
import AppsFlyerInterface;
```

Construct the AppsFlyer interface:

```html Markup
private static var appsFlyer:AppsFlyerInterface; 
appsFlyer = new AppsFlyerInterface();
```

[Optional] If you want to perform deep linking or access AppsFlyer conversion data from the application, register Conversion Listener:

```html Markup
appsFlyer.registerConversionListener();
```

Set the Developer key and iOS app ID (optional) and Initialise the SDK:

```html Markup
appsFlyer.appsFlyer.init("DevKey", "iOSAppID");
```

Initialize session logging (automatically log app launches and background-to-foreground transitions) with DevKey and iOS app ID (optional):

```html Markup
appsFlyer.start("DevKey", "iOSAppID");
```

</Accordion>

<div id="deep-linking" />

<Accordion title="Deep linking">

In order to receive the relevant AppsFlyer information from the deep link used:

1. Register the following event listeners:

   ```html Markup
   appsFlyer.addEventListener(AppsFlyerEvent.APP_OPEN_ATTRIBUTION, eventHandler); // success 
   appsFlyer.addEventListener(AppsFlyerEvent.ATTRIBUTION_FAILURE, eventHandler); // error
   ```
2. Handle the response in a corresponding event handler:

   ```html Markup
   private function eventHandler(event:AppsFlyerEvent):void {
   	log("AppsFlyer event: " + event.type + "; \nData: " + event.data);
   }
   ```

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Deferred deep linking">

In order to receive the conversion data for the current install:

1. Register the following event listeners:

   ```html Markup
   appsFlyer.addEventListener(AppsFlyerEvent.INSTALL_CONVERSATION_DATA_LOADED, eventHandler); // success
   appsFlyer.addEventListener(AppsFlyerEvent.INSTALL_CONVERSATION_FAILED, eventHandler); //error
   ```
2. Handle the response in a corresponding event handler:

   ```html Markup
   private function eventHandler(event:AppsFlyerEvent):void {
   	log("AppsFlyer event: " + event.type + "; \nData: " + event.data);
   }
   ```

</Accordion>

<div id="imei-and-android-id-collection-android-only" />

<Accordion title="IMEI and Android ID collection (Android only)">

**Important**! Apps with Google play services should avoid IMEI collection as this is in violation of the Google Play policy.

By default, IMEI and Android ID are not collected by the SDK if the OS version is higher than KitKat (4.4) and the device contains Google Play Services.

To explicitly send these IDs to AppsFlyer, developers can use the following APIs and place them before initializing the SDK.

If the app does NOT contain Google Play Services, the IMEI and Android ID are collected by the SDK.

**Enable/disable IMEI collection (disabled by default)**

```html Markup
appsFlyer.setCollectIMEI(bool);
```

**Manually set IMEI Data**

```html Markup
appsFlyer.setImeiData("imeiString");
```

**Enable/disable Android ID collection (disabled by default)**

```html Markup
appsFlyer.setCollectAndroidID(bool);
```

**Manually set Android ID data**

```html Markup
appsFlyer.setAndroidIdData("AndroidIDString");
```

</Accordion>

## API reference

<div id="api-methods" />

<Accordion title="API methods">

<Table>
  <thead>
    <tr>
      <th>
        Name
      </th>
      <th>
        Description
      </th>
      <th>
        Signature/example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        logEvent
      </td>
      <td>
        Log in-app events.
      </td>
      <td>
        ```html Markup
        var param:String = "Deposit";
        var value:String = '{"amount":10, "FTDLevel":"-"}';
        appsFlyer.logEvent(param, value);
        ```
      </td>
    </tr>
    <tr>
      <td>
        start
      </td>
      <td>
        Send a session logging event, regardless of app state.
      </td>
      <td>
        ```html Markup
        appsFlyer.start();
        ```
      </td>
    </tr>
    <tr>
      <td>
        setAppUserId
      </td>
      <td>
        Get the user ID as used in the app.
      </td>
      <td>
        ```html Markup
        appsFlyer.setAppUserId("user_id_as_used_in_the_app");
        ```
      </td>
    </tr>
    <tr>
      <td>
        setUserEmails
      </td>
      <td>
        Get user email.
      </td>
      <td>
        ```html Markup
        appsFlyer.setUserEmails("example@example.com");
        ```
      </td>
    </tr>
    <tr>
      <td>
        setCurrency
      </td>
      <td>
        Set the currency for logging revenue events, for example, USD.
      </td>
      <td>
        ```html Markup
        appsFlyer.setCurrency("USD");
        ```
      </td>
    </tr>
    <tr>
      <td>
        stop
      </td>
      <td>
        Used when you want want to shut down all SDK logging due to legal and privacy compliance. Once this API is invoked, our SDK no longer communicates with our servers.
      </td>
      <td>
        ```html Markup
        appsFlyer.stop();
        ```
      </td>
    </tr>
    <tr>
      <td>
        setDebug
      </td>
      <td>
        Enable/disable AppsFlyer debug logs.

        **Important:** Do not release the app to app stores with debug logs enabled.
      </td>
      <td>
        ```html Markup
        appsFlyer.setDebug(bool);
        ```
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>
