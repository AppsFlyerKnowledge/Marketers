---
title: Batch integration with AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Batch
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-01-28T10:06:24Z'
  edited_at: '2026-08-14T16:22:48Z'
  id: 360000833437
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360000833437-Batch-integration-with-AppsFlyer
---
> **At a glance:** Batch, an AppsFlyer integrated partner, is an app analytics, marketing automation and mobile CRM platform.

Batch allows advertisers to maximize user engagement while offering a personalized user experience. The Batch advanced user engagement platform lets you communicate with your smartphone users in a more personalized way, reduce your churn and boost your app ROI. AppsFlyer and Batch combined can help the advertiser to further customize user experience and engagement based on user journey. This means that the advertiser can send specific in-app messages and push notifications based on attribution data such as media source and campaign. Integrating Batch and AppsFlyer is simple and straightforward.

> 🚧 **Important**
>
> <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions#media-source-restrictions">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Integrating Batch and AppsFlyer

### Setting Customer User ID

In order for Batch to be able to match data from AppsFlyer with its own data, the advertiser must provide the same <Anchor target="_blank" href="/marketers/docs/customer-user-id-field-cuid">Customer User ID</Anchor> to both. The Customer User ID is set in the SDK.

It's important that you put a real Customer User ID, and not a placeholder value. A real Customer User ID is a user ID that you use to identify your customers in your own systems.

<Tabs>
<Tab title="Android">

#### Batch

Set Customer User ID in Batch SDK.

```java
Batch.User.editor()
    .setIdentifier("user@example.com")
    .save();
```

#### AppsFlyer

Set Customer User ID in AppsFlyer SDK.

```java
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>

<Tab title="iOS">

<Tabs>
<Tab title="Objective C">

#### Batch

Set Customer User ID in Batch SDK.

```objectivec
BatchUserDataEditor *editor = [BatchUser editor];
[editor setIdentifier:@"user@example.com"];
[editor save];
```

#### AppsFlyer

Set Customer User ID in AppsFlyer SDK.

```objectivec
[AppsFlyerTracker sharedTracker].customerUserID = @"user@example.com";
```

</Tab>

<Tab title="Swift">

#### Batch

Set Customer User ID in Batch SDK.

```swift
let editor = BatchUser.editor()
editor.setIdentifier("user@example.com")
editor.save()
```

#### AppsFlyer

Set Customer User ID in AppsFlyer SDK.

```swift
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>
</Tabs>

</Tab>
</Tabs>

### Setting Up Batch

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

The Batch configuration only requires the **Integration** tab. The other four tabs are inactive as they are not required in this integration.

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate Partner

On the **first visit** here, you will need to toggle ON the **Activate Partner** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

### General Settings

Before you can set up the integration with Batch, make sure to obtain your **Batch Rest API Key** and **Batch API Key**. If not sure, [contact Batch](mailto:hello@batch.com) for more information.  

Once you obtain the two keys, enter each in the relevant field. Under **General Settings**, put your **Batch Rest API Key** in the **BATCH\_REST\_API\_KEY** field and your **Batch API Key** in the **BATCH\_API\_KEY** field.

![batch-general-settings-keys.png](https://files.readme.io/fb165253ec81c0ad4ee9569ef928dc63fb476efe6da8fc7c9120d6619b3124c1-360001692717.png)

### Default Postbacks

Under **Default Postbacks**, in the **Sending Option** drop-down list, select **Events attributed to any partner or organic***.*

![batch-default-postbacks.png](https://files.readme.io/e3e84f990d7f05c94fb69195a7e57caeffcd1ca35a5fb0148fc6a81ab9816673-360001778958.png)

Click **Save** in the bottom right-hand corner of the screen.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for Batch.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions are not available for Batch.

</Accordion>

## Viewing AppsFlyer data in the Batch dashboard

Once AppsFlyer starts sending install postbacks to Batch, you can view the data in the Batch dashboard and start customizing user engagement according to attribution data.

You can see the data in the **Userbase** tab of your Batch dashboard.

![Userbase.png](https://files.readme.io/b0277dc43b81630d5b260273b208a5ab9b62e13c7caca08e8b631d73c8de3b2a-small-360001694717.png)

<div data-zendesk-anchors="h_01H9FK389GXG3CDFPNM5ASKJ3N=integrating-batch-and-appsflyer h_01H9FK389MPKFN8J74BX1E3MGG=setting-customer-user-id h_01H9FK389MK1HM1460VAT6X82Y=batch h_01H9FK389MPGNEX8B3923KYDB3=appsflyer batch::28a946d0=batch h_01H9FK389MC4K8PNVPAGC00TBW=batch appsflyer::3f0aa95b=appsflyer h_01H9FK389M7V83A66M6T9EV8QT=appsflyer batch::24c5c955=batch h_01H9FK389MRV4ARHMHXPAXVXQ9=batch appsflyer::deb78dd1=appsflyer h_01H9FK389MT6PD8FW21SYHBPCV=appsflyer setting-up-batch-in-appsflyer-dashboard=setting-up-batch h_01H9FK389MCSR5YDSF4RKFDSDZ=setting-up-batch h_01H9FK389MG9459909JZBDN77E=integration-tab h_01H9FK389M19AVM63DEX5JTTQK=activate-partner h_01H9FK389MN82EKHVGMM9Z6H58=general-settings h_01H9FK389MXA3DS403VXRRK5NX=default-postbacks h_01H9FK389MERP4XBF19T28E6DN=attribution-link-tab h_01H9FK389M3E05PVMNA83TBFJZ=cost-tab h_01H9FK389M06FEQ4RZJ04HTH33=ad-revenue-tab h_01H9FK389MB31S8BR8WX178GHX=permissions-tab h_01H9FK389M8BNRFECN0WG23BCD=viewing-appsflyer-data-in-the-batch-dashboard" />
