---
title: "Google Analytics integration—Custom dimensions"
excerpt: "Set up the integration with Google Analytics using custom dimensions."
x-zendesk:
  id: 4413033740817
  url: https://support.appsflyer.com/hc/en-us/articles/4413033740817-Google-Analytics-integration-Custom-dimensions
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Google Analytics
  section_id: 6551226043793
  position: 2
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Analytics, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-12-07T13:34:54Z'
  edited_at: '2026-08-14T16:22:39Z'
---
## Custom dimensions on Google Analytics

There is another method for sending AppsFlyer's attribution data to Google analytics, that is set up on GA and not on AppsFlyer's dashboard.

> ❗️ Important!
>
> The Custom Dimensions method **IS NOT RECOMMENDED** due to the following:
>
> - Integrating Google Analytics through AppsFlyer dashboard is simple, quick and easy
> - Integrating Google Analytics using Custom Dimensions is complicated and error-prone
> - Using Custom Dimensions requires you to use both AppsFlyer SDK and Google Analytics SDK
> - Using Custom Dimensions has a greater potential of causing discrepancies

Advertisers that use the new [integration with Google Analytics](/docs/google-analytics-ga4-integration) don't need to use the custom dimensions method.

> 📘 Note
>
> This method requires you to integrate GA SDK into your app.
>
> - [GA SDK for Android](https://developers.google.com/analytics/devguides/collection/android/v4/)
> - [GA SDK for iOS](https://developers.google.com/analytics/devguides/collection/ios/v3/)

### Setting media source as a custom dimension on Google Analytics

Google Analytics has a powerful tool to create user-level segmentation called custom dimensions. The custom dimension values are sent from mobile devices and your reports are generated, based on these dimensions from your Google Analytics dashboard.

### Step 1: Define it on Google Analytics

1. Select your app from the GA menu
2. Select _**Admin**_ at the top bar on GA dashboard
3. On the _**PROPERTY**_ column select _**Custom Definition**_
4. Select **_Custom Dimensions_**

<Image src="https://files.readme.io/e475ad1eda5b6338825b712e6c8254f245d5339f50ae40e723f465207e124262-4413121542033.png" alt="Custom Dimensions option in the Google Analytics Admin panel" />

5. Create a new dimension. Call it **AppsFlyer Media Source** and make sure you select _**User**_ scope. This ensures the data is saved over multiple sessions.

<Image src="https://files.readme.io/b2d85fd068e5523265a2b49b4218234fc77d5896ad41801cbe0e017752763cf2-4413121449873.png" alt="ga2.png" />

Each dimension is created with an index that you must remember so you can later use it in the GA API from your app. In this example, the index of the new dimension is 10.

<Image src="https://files.readme.io/6efc2249ede92291a2aadd16eccbc5b38b580723c6277e3746bdd467de29764a-11179413394193.png" alt="ga3" />

Repeat this step and create another dimension and call it **AppsFlyer Campaign**

### Step 2: Setting and sending the data from the app

First, you need to get the media source value from AppsFlyer SDK. You can do this using the method `onConversionDataSuccess`.

> 📘 Note
>
> Starting SDK V5, `onConversionDataSuccess` is the name of the method for getting conversion data. If you are using an SDK version lower than 5.0.0, the name of the method is ` onInstallConversionDataLoaded` in Android and `onConversionDataReceived` in iOS. We recommend that you upgrade to SDK 5.0.0. To learn more, click [here](/docs/links-to-appsflyer-sdk-release-notes).

Then, you can set the media source as custom dimension using Google Analytics SDK. See the following code samples to learn how to do it:

<Tabs>
<Tab title="Android">

```objectivec
Objective-Cprivate static Tracker sTracker;
@Override
public void onConversionDataSuccess(Map<String, String> conversionData)
{
  if (conversionData.get("af_status") == "Non-organic")
  {
    String mediaSource = conversionData.get("media_source");
    String campaign = conversionData.get("campaign");
    sTracker.set(Fields.customDimension(10), mediaSource);
    sTracker.set(Fields.customDimension(1), campaign);
  }
  else if (conversionData.get("af_status") == "Organic")
  {
    sTracker.set(Fields.customDimension(10), "Organic");
  }
}
```

</Tab>
<Tab title="iOS">

```objectivec
Objective-C-(void)onConversionDataSuccess:(NSDictionary*) installData {
  id status = [installData objectForKey:@"af_status"];
  if([status isEqualToString:@"Non-organic"]) {
		id mediaSource = [installData objectForKey:@"media_source"];
		id campaign = [installData objectForKey:@"campaign"];
		[[[GAI sharedInstance] defaultTracker] set:[\
				GAIFields customDimensionForIndex:10\
			] value: mediaSource];
    [[[GAI sharedInstance] defaultTracker] set:[\
				GAIFields customDimensionForIndex:1\
			]\
			value: campaign];
   }
	 else if([status isEqualToString:@"Organic"]) {
    [[[GAI sharedInstance] defaultTracker] set:[\
				GAIFields customDimensionForIndex:10\
			]\
			value: "Organic"];
   }
}
```

</Tab>
</Tabs>

### Step 3: See the results in Google Analytics

Most GA reports have a drill-down option called _**Custom Dimensions**_. You can select the dimensions _**AppsFlyer Media Source**_ or _**AppsFlyer Campaign**_ ([set in step 1](/docs/google-analytics-integration-custom-dimensions#step-1-define-it-on-google-analytics)) to see which media sources and campaigns bring users that install your app.

<Image src="https://files.readme.io/dde9219a7a8eec5c861b5031ad741ff7377d85ba9c3693bcbc455fd735f8af2d-4413121449617.png" alt="G_analytics1.png" />