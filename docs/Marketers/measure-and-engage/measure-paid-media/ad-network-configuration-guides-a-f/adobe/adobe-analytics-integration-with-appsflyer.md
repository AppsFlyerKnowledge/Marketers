---
title: "Adobe Analytics Integration"
excerpt: "Learn how to set up the two-way data flow between AppsFlyer and Adobe Analytics to automatically transfer attribution data."
---
The integration with [Adobe Analytics](http://www.adobe.com/marketing-cloud/web-analytics.html) (formerly Omniture) consists of a two-way data flow between Adobe and AppsFlyer. For the integration to be successful, this integration requires code implementation in your app. Both AppsFlyer and Adobe requirements must be met for the integration to be fully successful. This integration enables the automatic transfer of attribution data from AppsFlyer to Adobe to help you achieve your goals.

## Setting up Adobe Analytics integration

### Prerequisites:

- Setting up [Adobe Experience Platform mobile SDK docs](https://developer.adobe.com/client-sdks/documentation/)
- [Marketing Cloud Visitor ID](https://marketing.adobe.com/resources/help/en_US/mcvid/) or Experience cloud ID service
- Three eVars in each report suite that can be used for the sole purpose of this integration

### Step 1: Share Adobe Experience Cloud ID (ECID, Marketing Cloud ID, or Visitor ID) with AppsFlyer.

To extract and share Adobe Experience Cloud ID:

1. [Update the application and extract the Marketing Cloud Visitor ID](https://developer.adobe.com/client-sdks/documentation/mobile-core/identity/api-reference/#getexperiencecloudid) using the Adobe SDK method right after the Adobe SDK is initialized.
2. Use one of the following AppsFlyer SDK methods to set the Adobe Marketing Cloud Visitor ID:

### setAdditionalData

<Tabs>
<Tab title="Android">

Learn more about [the setAdditionalData method](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata).

```java
JavaHashMap<String, Object> customData = new HashMap<String,Object>();
customData .put(