---
title: "deltaDNA integration with AppsFlyer"
excerpt: "deltaDNA, an AppsFlyer integrated partner, is the leading real-time analytics and marketing platform for mobile gaming. The combination of market-leading deep data functionality, ultra-high performance and a flexible, open environment allows users to maximize engagement and lifetime value through player segmentation, predictive modeling and real-time targeted interventions."
x-zendesk:
  id: 212247706
  url: https://support.appsflyer.com/hc/en-us/articles/212247706-deltaDNA-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 8
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [deltaDNA, Advertisers, Ad Networks, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-09-04T06:41:51Z'
  edited_at: '2026-09-09T13:22:45Z'
---
**Important!**

[Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Integrating with deltaDNA

**Important!**

The deltaDNA SDK userID, whether auto-generated or provided by the game, must be set as the customer user id in the AppsFlyer SDK to ensure the attribution data received from AppsFlyer is applied to the correct user. This must only be done on builds of the game integrated against the LIVE environment on the deltaDNA side.

1. If you are using a propriety user id and populating this id both in AppsFlyer custom\_user\_id parameter and in deltaDNA user parameter – No additional code implementation is needed.
2. If you are not using a propriety user id, you must take your userID property from deltaDNA and implement it in the AppsFlyer SDK under the **customer\_user\_id** parameter. The following code should be implemented after both SDKs are initiated.

<Accordion title="Android">

```
AppsflyerLib.getInstance().setCustomerUserId(DDNA.instance().getUserId())
```

</Accordion>

<Accordion title="iOS">

```
[AppsFlyerTracker sharedTracker].customerUserID = [DDNASDK sharedInstance].userID;
```

</Accordion>

<Accordion title="Unity">

```
AppsFlyer.setCustomerUserID (DDNA.Instance.UserID)
```

</Accordion>

Follow the instructions below to configure the integration with deltaDNA

**In deltaDNA:**

1. Create an AppsFlyerAttribution event in deltaDNA with the Event Management tool

![Delta DNA 1](https://files.readme.io/e5224bbaa730d997699e1a930425946f69a2b86ef94e241b4ba6fdb9ad978c66-206781083.png)

2. Get the Live environment key on the Game Details page in deltaDNA dashboard:

![Delta DNA 2](https://files.readme.io/6b28184264dfd695000e8bfae9538862a3e17ea6f9d355af0996ccf107b4e6c2-206768886.png)

**In AppsFlyer, activate or edit the integration:**

1. **To activate:** In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations > Marketplace** tab.  
   **To edit**: In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations > Active Integrations** tab.
2. Search for **deltaDNA** and select it.
3. Click **Set up integration**. You’re directed to the integration setup page.
4. In the **Integration** tab, select the app for the integration and turn **Activate partner** on.  
   **Note:** The toggle must be on [(activated)](/docs/partner-activation-deactivation) for as long as you work with the partner.
5. Insert the Enviorment\_key taken from deltaDNA console (see Section 2).
6. Set the **Sending option** to **All media sources, including organic**.
7. Click **Save Integration**.

Once you have saved the configuration, AppsFlyer sends the following data to deltaDNA for every organic and non-organic install:

* Environment key
* User ID
* Install Time
* Media Source
* Campaign name

**Note**

deltaDNA rejects install postbacks from AppsFlyer if there is no Customer User ID or UserID defined.

## Viewing the attribution data in the deltaDNA console

Attribution data received from AppsFlyer can be used to:

* Filter Measure charts
* Build custom dashboards and reports
* Run detailed analysis
* Create custom player segments to target players with personalized campaigns and offers.

The Acquisition Channel filter at the top of all the Measure charts, the retention Matrices, LTV and Retention Predictors uses and is based on the AppsFlyer Media Source.

![Delta DNA 3](https://files.readme.io/21cf4f1c8641351a1ecc200d8b95d7558b92f4daf38f49975601d996a0fcfb86-206781123.png)

There are 8 attribution parameters that AppsFlyer can send to deltaDNA for use in your analysis, reports and queries. They are all prefixed with the letters **afAttr.**  
*E.g. afAttrCampaign, afAttrAgency, afAttrMediaSource for the campaign, agency, and media source respectively.*

All attribution parameters are listed within the **appsFlyerAttribution** added to your Event Management screen.

![Delta DNA 4](https://files.readme.io/e0af8513fdda3268ab799a6ef08396c03970bd0850bde851f07649e459a8b20e-206781143.png)

Use them to build custom analysis queries and reports in any of the deltaDNA Analyze tools.

![Delta DNA 5](https://files.readme.io/f4b9d0320feb3990182a0c9a835a18565ba959fabf7269c45a4651506666f941-206768946.png)