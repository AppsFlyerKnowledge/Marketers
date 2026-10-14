---
title: "Batch integration with AppsFlyer"
excerpt: "Batch, an AppsFlyer integrated partner, is an app analytics, marketing automation and mobile CRM platform."
x-zendesk:
  id: 360000833437
  url: https://support.appsflyer.com/hc/en-us/articles/360000833437-Batch-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 4
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Advertisers, Batch, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2019-01-28T10:06:24Z'
  edited_at: '2026-08-14T16:22:48Z'
---
Batch allows advertisers to maximize user engagement while offering a personalized user experience. The Batch advanced user engagement platform lets you communicate with your smartphone users in a more personalized way, reduce your churn and boost your app ROI. AppsFlyer and Batch combined can help the advertiser to further customize user experience and engagement based on user journey. This means that the advertiser can send specific in-app messages and push notifications based on attribution data such as media source and campaign. Integrating Batch and AppsFlyer is simple and straightforward.

**Important!**

[Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Integrating Batch and AppsFlyer

### Setting Customer User ID

In order for Batch to be able to match data from AppsFlyer with its own data, the advertiser must provide the same [Customer User ID](/docs/customer-user-id-field-cuid) to both. The Customer User ID is set in the SDK.

It's important that you put a real Customer User ID, and not a placeholder value. A real Customer User ID is a user ID that you use to identify your customers in your own systems.

<Accordion title="Android">

#### Batch

Set Customer User ID in Batch SDK.

```
Batch.User.editor()
    .setIdentifier("user@example.com")
    .save();
```

#### AppsFlyer

Set Customer User ID in AppsFlyer SDK.

```
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Accordion>

<Accordion title="iOS">

<Accordion title="Objective C">

#### Batch

Set Customer User ID in Batch SDK.

```
BatchUserDataEditor *editor = [BatchUser editor];
[editor setIdentifier:@"user@example.com"];
[editor save];
```

#### AppsFlyer

Set Customer User ID in AppsFlyer SDK.

```
[AppsFlyerTracker sharedTracker].customerUserID = @"user@example.com";
```

</Accordion>

<Accordion title="Swift">

#### Batch

Set Customer User ID in Batch SDK.

```javascript
let editor = BatchUser.editor()
editor.setIdentifier("user@example.com")
editor.save()
```

#### AppsFlyer

Set Customer User ID in AppsFlyer SDK.

```
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Accordion>

</Accordion>

### Setting Up Batch

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

The Batch configuration only requires the **Integration** tab. The other four tabs are inactive as they are not required in this integration.

<Accordion title="Integration tab">

### Activate Partner

On the **first visit** here, you will need to toggle ON the **Activate Partner** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click [here](/docs/partner-activation-deactivation).

### General Settings

Before you can set up the integration with Batch, make sure to obtain your **Batch Rest API Key** and **Batch API Key**. If not sure, [contact Batch](mailto:hello@batch.com) for more information.  

Once you obtain the two keys, enter each in the relevant field. Under **General Settings**, put your **Batch Rest API Key** in the **BATCH\_REST\_API\_KEY** field and your **Batch API Key** in the **BATCH\_API\_KEY** field.

![batch-general-settings-keys.png](https://files.readme.io/fb165253ec81c0ad4ee9569ef928dc63fb476efe6da8fc7c9120d6619b3124c1-360001692717.png)

### Default Postbacks

Under **Default Postbacks**, in the **Sending Option** drop-down list, select **Events attributed to any partner or organic***.*

![batch-default-postbacks.png](https://files.readme.io/e3e84f990d7f05c94fb69195a7e57caeffcd1ca35a5fb0148fc6a81ab9816673-360001778958.png)

Click **Save** in the bottom right-hand corner of the screen.

</Accordion>

<Accordion title="Attribution link tab">

Attribution Links are not available for Batch.

</Accordion>

<Accordion title="Cost tab">

Cost data is not supported in the integration with this partner.

</Accordion>

<Accordion title="Ad revenue tab">

Ad Revenue is not supported in the integration with this partner.

</Accordion>

<Accordion title="Permissions tab">

Permissions are not available for Batch.

</Accordion>

## Viewing AppsFlyer data in the Batch dashboard

Once AppsFlyer starts sending install postbacks to Batch, you can view the data in the Batch dashboard and start customizing user engagement according to attribution data.

You can see the data in the **Userbase** tab of your Batch dashboard.

![Userbase.png](https://files.readme.io/b0277dc43b81630d5b260273b208a5ab9b62e13c7caca08e8b631d73c8de3b2a-small-360001694717.png)