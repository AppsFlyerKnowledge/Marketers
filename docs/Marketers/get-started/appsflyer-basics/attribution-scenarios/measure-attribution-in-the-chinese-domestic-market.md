---
title: Measure attribution in the Chinese domestic market
metadata:
  keywords:
    - Advertisers
    - China
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2019-07-17T12:33:29Z'
  edited_at: '2025-04-05T12:56:57Z'
  id: 360002049858
  locale: en-us
  section: Attribution scenarios
  section_id: 6551328497041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360002049858-Measure-attribution-in-the-Chinese-domestic-market
---
**At a glance:** Attribution of Android devices without GAID by using OAID or IMEI. Best practice for viewing attribution data in AppsFlyer.

## Attribution Android apps in the Chinese domestic market

In China, there are several challenges that app owners face:

* Google Play Services (GPS) is not active in the majority of Android devices, meaning it has no GAID.
* The use of third-party Android app stores creates opportunities for store hijacking by device manufacturers.
* Attribution servers are inaccessible or slow to respond.
* Managing and viewing attribution data from Google Play and third-party Android app stores.

Using AppsFlyer, these challenges can be overcome by:

* Implementing attribution based on <Anchor target="_blank" href="/marketers/docs/appsflyer-knowledge-base-glossary#o">OAID</Anchor>
* Using device IMEI as an alternative to GAID in devices having Android version 28 or earlier
* Preparing APKs with unique identifiers to detect Android store hijacking
* Configuring attribution links that are recognized within China

## Preparing the App

Integrate the SDK in the app and prepare the APK using one of the methods according to the target devices Android version.

<div id="integrate-the-sdk-in-the-app" />

<Accordion title="Integrate the SDK in the app">

**Use IMEI and/or OAID instead of GAID**

In general, Google Play Services is not installed on Android devices supplied in China. This means that there is no GAID to use as a unique attribution identifier.

An alternative to using GAID is IMEI and/or OAID, where this is available, to enable attribution recording.

**OAID:**

* Is a user-resettable advertising ID similar to GAID and IDFA.
* Requires AppsFlyer Android SDK V5.1.0 and later.
* From AppsFlyer SDK V5.4.0, SDK will attempt to collect OAID automatically by default.
* Multiple manufacturers have completed OAID attribution interop testing with AppsFlyer. <Anchor target="_blank" href="/marketers/docs/android-oaid-implementation-in-the-sdk">Including Huawei, Lenovo, OPRO, Vivo, Samsung, and Xiaomi,</Anchor>

**IMEI**:

* AppsFlyer SDK prevents access to IMEI unless configured otherwise. The general assumption is that Google Play Services is active on the device and that IMEI is not needed. In China, this is not the case.
* When integrating the AppsFlyer SDK in your app, access to IMEI needs to be enabled.
* Where necessary, OAID and IMEI should be implemented simultaneously to ensure attribution irrespective of the Android version.
* This is because access to IMEI is restricted starting with <Anchor target="_blank" href="https://developer.android.com/training/articles/user-data-ids">Android 10 (API level 29)</Anchor>, released in late 2019. Neither your app nor the AppsFlyer SDK can collect these identifiers. Where no identifier is available AppsFlyer resorts to <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#probabilistic-modeling">attribution by Probabilistic modeling.</Anchor>

**Before you start**:

* AppsFlyer Android SDK V5.1.0 or later is required.

Use one of the following procedures:

<div id="oaid-starting-from-android-api-level-29" />

<Accordion title="OAID starting from Android API level 29">

There are two methods to collect OAID:

* setCollectOaid
* setOaidData

<Anchor target="_blank" href="/marketers/docs/android-oaid-implementation-in-the-sdk#msa-sdk">Instructions to enable the API methods</Anchor>

</Accordion>

<div id="imei-android-api-level-2328" />

<Accordion title="IMEI Android API level 23-28">

There are two methods to collect IMEI:

* setImeiData
* setCollectIMEI(true)

Use the following code example to integrate the SDK. This code example makes use of the method `onConversionDataSuccess`. This is the name of the method for getting conversion data starting from SDK V5.0. If you are using an SDK version prior to V5.0, the name of the method is `onInstallConversionDataLoaded`. We recommend that you upgrade to the SDK <Anchor target="_blank" href="/marketers/docs/sdk-integration-overview">current version.</Anchor>

**Note:** Android API level 23 or later requires user permission, using a prompt, to access the IMEI. This may result in the IMEI being retrieved after the activation of the StartTracking API. Starting from API level 29 access to the IMEI is restricted.

```java
Public class AFApplication extends Application {
   private static final String AF_DEV_KEY = "";
   private static AFApplication instance;
   @Override
   public void onCreate() {
      //If you want to show debug log.
      AppsFlyerLib.getInstance().setDebugLog(true); //Developer collect the imei and android id, then send them to AppsFlyer SDK.
	  AppsFlyerLib.getInstance().setImeiData("customer imei"); 
	  AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");
      //Or use the two APIs below let AppsFlyer SDK collect IMEI & android id
      //no matter if the Google Play Service exists or not.
      AppsFlyerLib.getInstance().setCollectIMEI(true);
      AppsFlyerLib.getInstance().setCollectAndroidID(true);
      //Configure the min time between two sessions, the recommendation is 2 seconds。
      AppsFlyerLib.getInstance().setMinTimeBetweenSessions(2);
      final AppsFlyerConversionListener conversionDataListener = new 
AppsFlyerConversionListener() {
       @Override
       public void onConversionDataSuccess(Map<String, Object=""> map) {}
       @Override
       public void onConversionDataFail(String error) {}
       @Override
       public void onAppOpenAttribution(Map<string, string=""> map) {}
       @Override
       public void onAttributionFailure(String s) {}
     }
     AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionDataListener);
     AppsFlyerLib.getInstance().startTracking(context, AF_DEV_KEY);
   }  
   @Override
     protected void attachBaseContext(Context base) {
        instance = this;
        super.attachBaseContext(base);
    }
  public static synchronized AFApplication getAppInstance() {
        return instance;
    }
}
```

On the first launch of the app, a READ\_PHONE\_STATE permission request is sent to the user in onResume() cal back of the MainActivity.

build.gradle in the app module****

```java
allprojects {
    repositories {
       ....
       maven { url 'https://jitpack.io'}
    }
}
dependencies {
    implementation 'com.github.tbruyelle:rxpermissions:0.10.2'
}
```

<Tabs>
<Tab title="MainActivity">

```java
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
   @Override
   protected void onCreate(Bundle savedInstanceState) {
       super.onCreate(savedInstanceState);
       startIMEILogic();
   }
   private void startIMEILogic() {
       SharedPreferences permissions_flags = getSharedPreferences("appsflyer-data", MODE_PRIVATE);
       if (!permissions_flags.contains(Manifest.permission.READ_PHONE_STATE)) {
           requestIMEIPermissions();
       }
   }
   private void requestIMEIPermissions() {
       if (ContextCompat.checkSelfPermission(this,
               Manifest.permission.READ_PHONE_STATE)
               != PackageManager.PERMISSION_GRANTED) {
           ActivityCompat.requestPermissions(this,
                   new String[]{Manifest.permission.READ_PHONE_STATE},
                   MY_PERMISSIONS_REQUEST_READ_PHONE_STATE);
       } else {
           //Permission was already granted
           SharedPreferences.Editor permissionsFlagsEditor = getSharedPreferences("appsflyer-data", MODE_PRIVATE).edit();
           permissionsFlagsEditor.putBoolean(Manifest.permission.READ_PHONE_STATE, true);
           permissionsFlagsEditor.apply();
       }
   }
   @Override
   public void onRequestPermissionsResult(int requestCode,
                                          String[] permissions, int[] grantResults) {
       if (requestCode == MY_PERMISSIONS_REQUEST_READ_PHONE_STATE) {
           SharedPreferences.Editor permissionsFlagsEditor = getSharedPreferences("appsflyer-data", MODE_PRIVATE).edit();
           boolean granted;
           // If request is cancelled, the result arrays are empty.
           if (grantResults.length > 0
                   && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
               // permission was granted!
               granted = true;
               AppsFlyerLib.getInstance().setCollectIMEI(true);
           } else {
               // permission denied!
               granted = false;
           }
           AppsFlyerLib.getInstance().setMinTimeBetweenSessions(0);
           AppsFlyerLib.getInstance().reportTrackSession(this);
           AppsFlyerLib.getInstance().setMinTimeBetweenSessions(5);
           permissionsFlagsEditor.putBoolean(Manifest.permission.READ_PHONE_STATE, granted);
           permissionsFlagsEditor.apply();
       }
   }
}
```

</Tab>

<Tab title="MainActivity (legacy)">

```java
public class MainActivity extends AppCompactActivity {
    @Override
    protected void onResume() {
        super.onResume();
        final RxPermissions rxPermissions = new RxPermissions(this);
         if(RxPreference.Instance().getBoolean(RxPreference.KEY_PERMISSION_DIALOG_HAS_SHOW, false){
          return;
         }
         if(rxPermissions.isGranted(Manifest.permission.READ_PHONE_STATE)) {
            return;
         }
          RxPreference.Instance().putBoolean(RxPreference.KEY_PERMISSION_DIALOG_HAS_SHOW, true);
        rxPermissions.request(Manifest.permission.READ_PHONE_STATE)
                .subscribe(granted -> {
                    if (granted) {  
AppsFlyerLib.getInstance().setImeiData("customer imei");  
AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");  
//or  
AppsFlyerLib.getInstance().setCollectIMEI(true);  
AppsFlyerLib.getInstance().setCollectAndroidID(true);  
//NOTE: Here the report session API is reportTrackSession() not the startTracking()
                        AppsFlyerLib.getInstance().reportTrackSession(AFApplication.getAppInstance());
                    } else {
                    }
                });
    }
}
```

</Tab>
</Tabs>

</Accordion>

There are two methods to collect IMEI:

* setImeiData
* setCollectIMEI(true)

Use the following code example to integrate the SDK. **Note:** The code example uses the method `onConversionDataSuccess` to get conversion data. This is the name of the method starting SDK V5. If you are using an SDK version earlier than 5.0.0, the name of the method is `onInstallConversionDataLoaded`. We recommend that you upgrade to SDK 5.0.0. To learn more, click <Anchor target="_blank" href="/marketers/docs/links-to-appsflyer-sdk-release-notes">here</Anchor>.

```java
 public class AFApplication extends Application {
    private static final String AF_DEV_KEY = "";
    private static AFApplication instance;
    @Override
    public void onCreate() {
      //If you want to show debug log.
      AppsFlyerLib.getInstance().setDebugLog(true);  
 //Developer collect the imei and android id, then send them to AppsFlyer SDK.  
 AppsFlyerLib.getInstance().setImeiData("customer imei");  
 AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");
      //Or use the two APIs below to let AppsFlyer SDK collect IMEI & android id no matter the 
      //Google Play Service is exist or not.
      AppsFlyerLib.getInstance().setCollectIMEI(true);
      AppsFlyerLib.getInstance().setCollectAndroidID(true);  
      final AppsFlyerConversionListener conversionDataListener = new AppsFlyerConversionListener() {
          @Override
          public void onConversionDataSuccess(Map<String, Object=""> map) {} 
    	  @Override
          public void onConversionDataFail(String error) {}    
    	  @Override
          public void onAppOpenAttribution(Map<string, string=""> map) {}
          @Override
          public void onAttributionFailure(String s) {}
  	};
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionDataListener);
      AppsFlyerLib.getInstance().startTracking(context, AF_DEV_KEY);
  }
    @Override
    protected void attachBaseContext(Context base) {
        instance = this;
        super.attachBaseContext(base);
    }
    public static synchronized AFApplication getAppInstance() {
        return instance;
    }
}
```


</Accordion>

<div id="preparing-the-apk" />

<Accordion title="Preparing the APK">

Select how attribution data displays in AppsFlyer from:

* (best practice) **Single app:** The data of all third-party Android app stores (China domestic) displays under a single but separate app. This means that you see all the domestic Chinese stores attribution data under one app in AppsFlyer. To use this method continue to [add the app in AppsFlyer](/docs/measure-attribution-in-the-chinese-domestic-market#adding-the-app-in-appsflyer) section that follows.
* **Single app consolidated with Google Play store:** The attribution of both the third-party app stores and Google Play store display as a single entity. This option requires that the package name of both the Google Play store and the third-party stores is identical. Using this option assume that the app is already defined in AppsFlyer. To use this method continue to [preparing the APK/manifest](/docs/measure-attribution-in-the-chinese-domestic-market#preparing-the-apkmanifest) in the section that follows.
* **Multiple apps** means that the attribution data of each store is shown under a separate app. For example, each of the following is shown separately, Google Play Store, third-party store A, third-party B, and so on. To use this method, see <Anchor target="_blank" href="/marketers/docs/set-up-multi-store-android-attribution">multiple apps</Anchor>.

### Adding the app in AppsFlyer

**To add the app in AppsFlyer**:

1. In AppsFlyer, click **My Apps**.
2. Click **Add App**.  
   The Add Your App window opens.
3. Select **Android out of store APK**.
4. Complete the following fields:  
   * **Android package name**: free text
   * **Channel name**: Must be identical to the channel name in the manifest as explained in the section that follows. Best practice is to set this field to **cn\_market**.
   * **App URL**

**Note**: You can create the app using the **Pending approval or unpublished** option, but this is not recommended. Consult with your CSM before using this method.

### Preparing the APK/manifest

**To prepare a separate APK/manifest for each third-party app store as follows:**

1. Add the following to the manifest to identify Chinese traffic:

   ```java
   < meta-data android:name="CHANNEL" android:value="cn_market">
   ```

   **Note:** Parameters are case sensitive. We recommend that you set the channel to **cn\_market**.
2. Choose one of the following methods to identify the store:
   * **Manifest method:** Add the following line to the AndoridManifest.xml file. The AF\_STORE value needs to be unique for each store.

     ```java
     <meta-data android:name="AF_STORE" android:value="example_store"/>
     ```

     **--OR--**
   * **API method:** Prepare a separate APK for each third-party app store. Call the setOutOfStore API to set the AF\_STORE value. Set a unique value for each store.  

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("example_store")
     ```

The methods described set the parameter AF\_STORE which in turn sets the install\_app\_store field in attribution data. This field is available in:

* Cohort analysis
* <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview">Raw data reports</Anchor>

</Accordion>

## Additional attribution considerations

<div id="workaround-for-stores-without-attribution-link-support" />

<Accordion title="Workaround for stores without attribution link support">

Many third-party Android app stores in China also sell traffic, meaning they are also an ad platform. In some cases, these stores do not support the use of attribution links. The following workaround solutions can be used as an alternative:

* install\_app\_store field: (recommended) When installation takes place without an attribution link, AppsFlyer attributes the installation to organic installs. By using the install\_app\_store field, you can identify the actual source of the install. Note: The install\_app\_store field is set using the AF\_STORE parameter described in the previous section.
* <Anchor target="_blank" href="/marketers/docs/appsflyer-factory-preinstall-using-manifest-android">Preinstall name</Anchor> in the manifest file. Using the preinstall name contained in the manifest. The disadvantage of this method is that where the preinstall APK is leaked to the market, attribution information will be incorrect. When using this method ensure that you have the appropriate commercial terms to protect your APK.

</Accordion>

<div id="china-domestic-attribution-links" />

<Accordion title="China domestic attribution links">

When preparing attribution links take into account the following:

**China-based links**

For media sources that only have domestic (Chinese) traffic, use the domain links detailed here. These links are recognized from within China and provide a superior user experience.

For regular attribution links use: https://app.aflink.com - (aflink.com)

For OneLink attribution links use: https://go.onelnk.com (onelnk.com) Note: Before using the onelnk.com domain, contact your AppsFlyer CSM.

Note that in weChat only **onelnk.com** is allowlisted whereas **onelink.me** is blocked

**Use af\_r**

Use af\_r to make sure users are redirected to either an APK download URL or an APK store, and not to Google Play Store.

Note: Frequently, China domestic integrated media sources have this parameter set as &redirect=false in the default attribution URL template. Meaning that redirection will be done by the ad platforms and not by AppsFlyer.

For more information about integrated media sources:  
<Anchor target="_blank" href="/marketers/docs/android-app-promotion-in-china">Android app promotion in China</Anchor>

</Accordion>

<div id="detecting-store-hijacking" />

<Accordion title="Detecting store hijacking">

In third-party app store scenarios, users first install the app from the media source's (ad networks) third-party store. In the case of an installation hijack, a warning pop-up suggests the user installs/updates the app directly from the device (phone) manufacturer's app store. Where the user agrees, the user is re-directed to download from the manufacturer's app store and the APK downloaded. Meaning that the device manufacturer has hijacked the install.

The following example illustrates both a legitimate flow and a hijacked flow:

**Legitimate flow**

An app user clicks on an ad displayed by media-example, and either immediately downloads the app or is redirected to the legitimate-app-store to download the APP. In AppsFlyer the following attribution information is recorded:

* **Media source**: media-example
* **Install app store**: legitimate-app-store

**Hijacked flow**

An app user clicks on an ad displayed by media-example. When the download is initiated, a warning pop-up appears, suggesting that the user downloads the app from the device manufacturer's app store. If the user agrees, they are redirected to the manufacturer's store and download the app. In AppsFlyer the following attribution information is recorded:

* **Media source:** media-example
* **Install-app-store**: manufacturer-store

**Identifying the hijack event in AppsFlyer**

To identify the hijacked install, you compare the media source and install-app-store fields. A mismatch between the expected install-app-store and the actual install-app-store indicates an installation hijack.

</Accordion>
