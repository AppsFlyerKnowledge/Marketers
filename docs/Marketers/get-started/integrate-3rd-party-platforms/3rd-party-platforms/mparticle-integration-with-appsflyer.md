---
title: mParticle integration with AppsFlyer
excerpt: >-
  mParticle, an AppsFlyer integrated partner, collects customer data and sends
  it to different analytics, marketing, and data warehousing platforms.
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - mParticle
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-04-03T05:31:23Z'
  edited_at: '2026-08-14T16:22:58Z'
  id: 209787323
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/209787323-mParticle-integration-with-AppsFlyer
---
**Important!**

[Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Event integrations

The purpose of this document is to provide you with details of how to activate event data from mParticle to AppsFlyer.

1. mParticle customers must integrate the AppsFlyer kit into their application. The mParticle SDK will initialize AppsFlyer’s SDK and will also forward all required lifecycle events to the AppsFlyer SDK.

2. Refer to the [iOS](https://github.com/mParticle/mParticle-apple-SDK) and [Android](https://github.com/mParticle/mparticle-android-sdk) SDK GitHub repositories for details on how to configure the AppsFlyer kit with the mParticle SDK into your app.

### Configure the AppsFlyer event integration

1. From the mParticle dashboard ([https://app.mparticle.com](https://app.mparticle.com)), select your App (aka Workspace)

2. Click **Directory** from the left navigation

3. Click the AppsFlyer tile to display the integration details which provide information regarding the integration such as Categories, Available Platforms, Minimum mParticle SDK versions (if any), Data Types, User IDs, Device IDs and Available events, User IDs, Device IDs, and Available Configurations.

![AppsFlyer tile in the mParticle Directory](https://files.readme.io/afa886e48f2cddde39007275a72ce03c4a6c4182408bb2ad4c8c183b1591b47d-115015666683.png)

4. Click **Add AppsFlyer to Setup**.

The **Add to Setup** window opens:

![mParticle Add to Setup window](https://files.readme.io/1eccc4ea365d41d4228eb07f4df88641458244b303ac8805932bf42ef4df5a74-115015476946.png)

5. Select the Output Event Integration Type and click **Add to Setup** to open the Event Configuration Setup screen where you can continue the configuration process.

![mParticle Event Configuration Setup screen](https://files.readme.io/9a4720fef99a21a67fd017f4485e73765ebcb7aeb126f5342cc911aff4a345d2-115015476966.png)

6. Enter the AppsFlyer configuration settings and click **Save**:

* Configuration Name
* User same settings for Development and Production
* Dev Key
* The configuration you just created is shown under the AppsFlyer Default Group

![AppsFlyer configuration shown under the AppsFlyer Default Group](https://files.readme.io/4d82533f311b93373152f046e92fe46c5e515cb8f5084bb89e81bfcae608172c-115015666803.png)

The next step is to establish a connection between your input platforms to the AppsFlyer output event configuration.

7. Click **Connections**.

8. Select the Input (iOS in this example) and then click **Connect Output**.

9. Select the AppsFlyer tile and then select the AppsFlyer configuration created above.

10. Enter the AppsFlyer Connection settings:  
Apple App ID (enter the number only and not the ID prefix. For example, if your App ID is **id123456789** enter **123456789**)

![AppsFlyer Connection settings screen](https://files.readme.io/2fb4c7480c5813bf7d893318de5c4a8edfe3649293bf51c8dae422be65db726e-115015477066.png)

11. Click **Add Connection**.

AppsFlyer is now shown as a Connected Output Further options, such as Custom Mappings, may be available. See [mParticle’s documentation](https://docs.mparticle.com/guides/getting-started/connect-an-event-output#outputs) for more.

![AppsFlyer shown as a Connected Output](https://files.readme.io/53ea474eeb94c551677dd7a4ce190d6ed5972d65eafacd773b61d4ebd954fe2c-115015667883.png)

## Feed integrations

This section helps you understand how to connect a data feed from AppsFlyer to mParticle.

General integration information for AppsFlyer can be found at [https://docs.mparticle.com/integrations/appsflyer/feed/](https://docs.mparticle.com/integrations/appsflyer/feed/).

1. From the mParticle Dashboard ([https://app.mparticle.com](https://app.mparticle.com)), select your App (aka Workspace)

2. Click **Directory** from the left navigation

3. Click the AppsFlyer tile to display the integration details which provide information regarding the integration.

![AppsFlyer tile in the mParticle Directory](https://files.readme.io/53ea474eeb94c551677dd7a4ce190d6ed5972d65eafacd773b61d4ebd954fe2c-115015667883.png)
![AppsFlyer integration details in mParticle](https://files.readme.io/afa886e48f2cddde39007275a72ce03c4a6c4182408bb2ad4c8c183b1591b47d-115015666683.png)

4. Click **Add AppsFlyer to Setup**.

5. Select the Input Feed Integration Type and click **Add to Setup**.

You are now taken to the Setup screen, where you can continue the configuration process.

6. Enter the AppsFlyer configuration settings and click **Create**:

* Configuration Name
* Act as Application

![AppsFlyer feed configuration settings](https://files.readme.io/b27aff8223a98b0bf4bd73b6a7a04dc73bc245fa062ac9dd47ed6f4bbeece3f2-115015668703.png)

7. Complete the setup in the AppsFlyer dashboard using the authentication information provided.

![AppsFlyer dashboard authentication setup](https://files.readme.io/3c751a38c3891f73485375d75eacde3e07f86969a7d44cd33bf29ace6bfa1875-115015478566.png)

## Deferred deep linking

AppsFlyer allows you to access the user attribution data in real-time directly at the SDK level. It enables you to customize the landing page a user sees on the very first app open after a fresh app install. This is commonly referred to as “deferred” deep linking.

For more details of deferred deep linking, click [here](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink).

AppsFlyer conversion data contains a parameter called `is_First_Launch`. The value of `is_First_Launch` is 'true' on first launches only, and 'false' on all following launches. You can use this parameter to determine on every launch if the app should defer deep link to the user or not.

```
af_dp → $deeplink_path
```

**Example**

```
$deeplink_path=product/Banana-Pet-Costume/dd67268672b345e491656c871af8aa29
```

`af_dp` includes the encoded URI scheme and pathway

`af_dp` →

`%20jet%3A%2F%2Fproduct%2FBanana-Pet-Costume%2Fdd67268672b345e491656c871af8aa29`

<Accordion title="Android">

For Android: Perform this with Shared Preferences: [here.](https://developer.android.com/reference/android/content/SharedPreferences.html)

```
AttributionListener myListener = new AttributionListener() {
  @Override
  public void onResult(@NonNull AttributionResult attributionResult) {
   if (attributionResult.getServiceProviderId() == MParticle.ServiceProviders.APPSFLYER) {
    JSONObject attributionParams = attributionResult.getParameters();
    if (attributionParams != null && attributionParams.has(AppsFlyerKit.INSTALL_CONVERSION_RESULT)) {
     Log.d("Conversion result", attributionParams.toString());
    } else if (attributionParams != null && attributionParams.has(AppsFlyerKit.APP_OPEN_ATTRIBUTION_RESULT)) {
     Log.d("App open result", attributionParams.toString());
    }
   }
  }

  @Override
  public void onError(@NonNull AttributionError attributionError) {
   Log.d("Attribution Data Error", attributionError.toString());
  }
 };

 MParticleOptions options = MParticleOptions.builder(this)
  .credentials("replaceWithAPIKey", "replace-withAPISecret")
  .attributionListener(myListener)
  .build();

 MParticle.start(options);
```

</Accordion>

<Accordion title="iOS">

For iOS: Perform this in UserDefaults: [here](https://developer.apple.com/documentation/foundation/userdefaults)

```
- (BOOL) application:(UIApplication *) application didFinishLaunchingWithOptions:(NSDictionary *) launchOptions {
 MParticleOptions *options = [MParticleOptions optionsWithKey:@"<>" secret:@"<>"];
 options.onAttributionComplete = ^void (MPAttributionResult *_Nullable attributionResult, NSError * _Nullable error) {
  if (error) {
   NSLog(@"Attribution fetching for kitCode=%@ failed with error=%@", error.userInfo[mParticleKitInstanceKey], error);
   return;
  }
  NSLog(@"Attribution fetching for kitCode=%@ completed with linkInfo: %@", attributionResult.kitCode, attributionResult.linkInfo);
 }
 [[MParticle sharedInstance] startWithOptions:options];
 return YES;
}
```

</Accordion>

### AppsFlyer/mparticle use cases

| Use Case | Platform | AppsFlyer SDK Method | mParticle-AF Kit Method |
| --- | --- | --- | --- |
| Deferred Deep Llinking | iOS | onConversionDataSuccess | checkForDeferredDeepLinkWithCompletionHandler |
| Universal Links | iOS | continueUserActivity | continueUserActivity |
| App Open | iOS | onAppOpenAttribution | checkForDeferredDeepLinkWithCompletionHandler |
| Deferred Deep Linking | Android | onConversionDataSuccess | checkForDeepLink |
| Android App Links | Android |  | continueUserActivity |
| App Open | Android | onAppOpenAttribution | checkForDeepLink |

### Handling user flags

AppsFlyer also enables you to serve personalized content or send existing users to specific locations in the app AFTER the initial launch. When existing users are deep linked into the app, the app opens from `onOpenAttribution` method, which returns the referring URL data.

```
 if let conversionData = params?[MPKitAppsFlyerConversionResultKey] as? [AnyHashable: Any], !alreadyLoggedAppsflyerConversionData {
   logAppsflyerConversionData(conversionData: conversionData)
   alreadyLoggedAppsflyerConversionData = true
   if let onelinkURL = (conversionData["af_dp"] as? String).flatMap(URL.init) {
    UIApplication.appDelegate._linkController.handle(onelinkURL, source: .appsflyer)
   }
  } else if let appOpenData = params?[MPKitAppsFlyerAppOpenResultKey] as? [AnyHashable: Any] {
   logAppsflyerAppOpenData(appOpenData: appOpenData as? [String: Any])
  }
```

AppsFlyer uses iOS ***UserDefaults*** and Android ***Shared Preferences*** to indicate whether the user is opening the app for the first time and should be redirected to the appropriate page, or if the app has already been opened and the user has already been directed to that page. To do this, the `alreadyLoggedAppsflyerConversionData` value is read and written to UserDefaults/ SharedPreferences, so that the value ***af\_dp*** is not looked at on the first launch.

For more details about serving personalized content on deep linking [click here](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink).

## Enabling AppsFlyer uninstall measurement in mParticle

AppsFlyer uninstall measurement isn't automatically enabled with the mParticle-AppsFlyer SDK kit. To measure app uninstalls, call the AppsFlyer methods directly by following the AppsFlyer uninstall measurement documentation.

**To implement uninstall measurement for either iOS or Android:**

* Call AppsFlyer methods directly by following our uninstall measurement documentation

<div data-zendesk-anchors="h_01H9HWJRM2612MBM2Y7C5YZ2YY=event-integrations h_01H9HWJRM2BJATV1QHS382J0ZN=configure-the-appsflyer-event-integration h_01H9HWJRM2YV3CEH7J7EMA8E3Y=feed-integrations h_01H9HWJRM2SZYRXFTSZPM1JHCJ=deferred-deep-linking h_01H9HWJRM2HCB4YF2BP9RPK2RP=appsflyermparticle-use-cases h_01H9HWJRM3HAGGWHF4YTQTTS2X=handling-user-flags known-mparticle-integration-limitation=enabling-appsflyer-uninstall-measurement-in-mparticle h_01H9HWJRM321PSNQ480R96BN12=enabling-appsflyer-uninstall-measurement-in-mparticle" />
