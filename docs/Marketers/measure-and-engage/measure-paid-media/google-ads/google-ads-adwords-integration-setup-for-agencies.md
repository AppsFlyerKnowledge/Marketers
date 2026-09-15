---
title: "Google Ads (AdWords)—Integration setup for agencies"
excerpt: "Learn how to set up and configure Google Ads integration with AppsFlyer as an agency to measure and attribute mobile traffic."
---
**At a glance:** Setting up Google Ads integration with AppsFlyer — as an agency.

Both advertisers and agencies must actively configure the system. The following video shows the steps required by both the advertiser and agency to enable the agency to measure and attribute mobile traffic to the advertiser's app using Google Ads.

The configuration enables AppsFlyer to attribute conversions to an agency from within the AppsFlyer dashboard.

Before the Agency can begin the process, the Advertiser must first configure the Google Ads integration. For details, click [here](/docs/google-ads-adwords-integration-setup-for-advertisers).

## Enabling agency attribution of Google Ads

AppsFlyer supports agency configurations with Google Ads. It is essential that the advertiser and the agency have separate Google Ads accounts to enable AppsFlyer to correctly attribute the data.

## Setting up Google Ads attribution for agencies

To start agency attribution of Google Ads campaigns with AppsFlyer, follow these steps:

**Watch**

![](https://fast.wistia.com/embed/medias/fzihkki0qd/swatch)

**Read**

### Advertiser pre-step: enabling the agency access to Google Ads

**Prerequisites:**

* In AppsFlyer, grant the agency access to the app using the instructions [here](/docs/set-up-an-integrated-partner#agency-permissions).
* In AppsFlyer, [activate](/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory) the Google Ads partner.

**To share the advertiser's Link ID:**

1. In Google, go to the Google Ads Dashboard, click on the ***Tools*** icon

![Google_Ag_1.png](https://files.readme.io/48154772f2102eb84701768d93c9177898bd53503cf6f1140a497a3b3da3cfc1-360001061565.png)

2. Select ***Linked accounts***.

![Google_Ag_2.png](https://files.readme.io/b051c4efe2a4e9c6cfffdf1e379fcbe742b37a6582a8e931e6100fcabe98a502-360001061585.png)

3. Under App Analytics Provider, find AppsFlyer. Select Options.

4. Click ***Share with another account***.

![Google_Ag_3.png](https://files.readme.io/3c1146b8e9b2e2350c866f8435f9fc6e5a52ae4f82dc7f0e98582e946d4036da-360001060385.png)

5. Insert the **Agency’s Google Ads Customer ID**

![Google_Ag_4.png](https://files.readme.io/7a2118fc43974eab19cbd26a42015d8b311c26eaed346172cd82d9bfb00707a6-360001065949.png)

6. Click ***Next***. Click ***Send invite.***

![Google_Ag_5.png](https://files.readme.io/f48d92fd524f9c55fb6e9ff528c65ea87a213c71f10325e8badaebea7b526832-360001064709.png)

The advertiser can now see that the invitation request has been sent to the Agency. When the Agency accepts the invite, the status changes to Sharing.

For more details on sharing your Google Ads Link ID, click [here](https://support.google.com/adwords/answer/7365001).

![Google_Ag_6.png](https://files.readme.io/a56389a1ae01cc6e264dabe5caf2cdb6894ff9fe6217b9b4bcaf6abb26d885b0-360001064729.png)

### Agency step 1: accepting the Link ID

On the Google Ads Words dashboard, the Agency receives an Invite and must accept the link.

![Google_Ag_7.png](https://files.readme.io/ab7a41293b6c420a67f44a1930e0a21f19357a7d4f7b6d78872f4e26615fbd5e-360001064749.png)

The Agency can see the link status is now Active.

![Google_ag_8.png](https://files.readme.io/6fb01c60d9cd02f81fc40ea8bb4c7506a05aa4ef69bd7e32ad0644ed60b28510-360001064769.png)

### Agency step 2: setting up Google Ads on AppsFlyer

1. In AppsFlyer, from the side menu, select Collaborate > Active Integrations.
2. Search for and select **Google Ads**.

   ![gads-search.png](https://files.readme.io/419752e2ce5aee7864cc6e004e1cbb8356ce67f7adcbbc05582d04892c1fac40-360001810917.png)

   ***Activate partner*** should be ON and the ***Link ID*** set by the advertiser. These settings are grayed out to the agency.

   ![gads_agency-integration-link-id.png](https://files.readme.io/295cb0774749d4ba219e57a1950dfe32e32dde400f3c952b1a352e1116957be7-360004044538.png)
3. The Agency sets its Google Ads Customer ID.

   Enter **all** of the Google Ads Customer IDs (**Sub Accounts**) of the Google Ads accounts that the agency is running campaigns for the advertiser's app.

   You can find the Google Ads Customer ID by clicking on the arrow in the top left corner and thereby opening the Navigation Panel.

   [![](https://support.appsflyer.com/hc/article_attachments/115012232646)](https://support.appsflyer.com/hc/article_attachments/115012232646)
4. To measure running retargeting campaigns on Google Ads, ask the advertiser to activate **Google Ads Retargeting**. Once done, you can configure the **Re-Engagement Window**.

   ![gads-agency-retargeting.png](https://files.readme.io/73dcf4c36abc082a56c155b5fa4211339b856f24dabe078e4619873a470c3c80-360001811037.png)
5. We recommend setting the Click-Through Attribution Lookback Window to **30 days**, to match the Google Ads value.

   ![gads-click-through.png](https://files.readme.io/c4f09c47bae85388c58b56a9533844ad8cddc821dba0ffd2f8130006913f478d-360001901938.png)
6. The View-Through recommended is **1 day**, to match the Google Ads value. The scale allows you to customize the number of hours/days after an ad is viewed, during which the impression can be attributed to this partner.

   ![gads-view-through.png](https://files.readme.io/7a6a2e4a6abf6f2c799cef163c9b3affbcf93d1b950633ed1582348c1b15563f-360001811077.png)
7. ***Reinstall attribution***:
   * To enable reinstall attribution, switch it on.
   * No need to enable view-through attribution or configure lookback windows for reinstall attribution, as the values are taken from install attribution settings.
8. Click ***Save & Close*.**

An Agency can set up multiple Google Ads Customer IDs, if required.

### Agency step 3: mapping your in-app events

1. Click the **In-App Events** tab.

2. Select to either send In-App Events from Only Google Ads Installs or from All In-App Events to Google Ads.  
[![](https://support.appsflyer.com/hc/article_attachments/360002281289)](https://support.appsflyer.com/hc/article_attachments/360002281289)

3. Map all In-App Events you want to send to Google Ads, with the pre-defined Google Ads events.

[![](https://support.appsflyer.com/hc/article_attachments/360002259785)](https://support.appsflyer.com/hc/article_attachments/360002259785)

4. Click ***Save***.

> 📘 **Important!**
>
> Import the first-open and in-app actions to Google Ads to begin counting conversions in both Google Ads and your AppsFlyer dashboard.
>
> To be able to import, you must launch the app and perform your mapped in-app events at least once.

> 📘 **Note**
>
> * It may take up to 6 hours until the new conversions change status from No Recent Conversion to Recording Conversion.
> * If an agency works with an MCC account and the app is promoted via several MCC sub-accounts all sub-accounts must be configured in the **Google Ads Customer ID**field (as seen on above screenshot).
>   In such a case there is no need to configure the customer id of the MCC account.


### Agency step 4: Measure your app conversions (mandatory)

**(**Google Ads** admin only)**

> 📘 **Important!**
>
> For Google Ads to register your new conversions, you must**launch your app and perform your mapped in-app events** at least once. To test iOS apps, you must collect IDFA to see the event. It may take up to 6 hours until the event conversions are added to the queue. Once they are added you can import them, and the new conversions change status from “No recent conversion” to “recording conversion".


1. Return to your Google Ads account (**Overview** page and go to **TOOLS AND SETTINGS** > **Measurement** > **Conversions**.  
    [![conversions_overview_en-us__1_.png](https://files.readme.io/832681b46db39e8e4d60165b3e05377e70c332a0d20fad2113b3aac68a398688-15236233447697.png)](https://support.appsflyer.com/hc/article_attachments/15236233447697)
2. Click **+ New conversion action**.   
    [![New_conversion_action_en-us__2_.png](https://files.readme.io/162a57b453042a99f78f18cd663c0d25ac213a81e0c92114a82da180417d27c5-15236268311697.png)](https://support.appsflyer.com/hc/article_attachments/15236268311697)
3. Select **App** from the list of conversion types, then select **Third-party app analytics**, and click **Continue**.  
    [![select_app_en-us__3_.png](https://files.readme.io/b380648af91d736f6b6947b6f95cd0b0b6cf1a45f579f807da46a5f2280765fe-15236236777489.png)](https://support.appsflyer.com/hc/article_attachments/15236236777489)
4. Check the box next to **first\_open** of all your apps, and for each event you’d like to import.   
   CALLSTART::Note::

   #### Note

   You need to re-import if the **Partner Event identifier** in Google Ads is changed or if it's CUSTOM and the corresponding event name has changed in AppsFlyer.

   CALLEND::
   Click **Import and Continue**, then click **Done**.   
    [![select_events_to_import_en-us__4_.png](https://files.readme.io/8d0c88beff43eacac186216e5f67f008f930d211f24bd182d48d7a0513b1819e-15236288297105.png)](https://support.appsflyer.com/hc/article_attachments/15236288297105)
5. You can now see your third-party conversion events on the **Conversions** > **Summary** page. If an event doesn't appear in the list or it has been removed from the Google Ads conversion list, click **View all conversion actions**. The **Status** filter appears.   
    [![conversions_summary_en-us__5_.png](https://files.readme.io/4998e2a4ba7201ae9253aeb1d0beafed17ad817816d7e6f7ecae5cbcc7001274-15236289653393.png)](https://support.appsflyer.com/hc/article_attachments/15236289653393)
6. Click **Status** and select **All** to see all events, including disabled and removed events.  
    [![conversion_action_status__6_.png](https://files.readme.io/41b0b26a4c1ca00ba1292efc2e0a2aebd1a77d77d9f6523ac30401b9bd06ae36-15236323727633.png)](https://support.appsflyer.com/hc/article_attachments/15236323727633)
7. Congratulations! You're now measuring Google Ads mobile campaigns with AppsFlyer!

> 📘 **Note**
>
> Please ensure your "include in conversions" setup is aligned with your campaign goals in Google Ads. For more information, consult with your Google representative or refer to the Google documentation [here](https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false).


To watch the video "Setting-Up Google Ads Attribution for Advertisers" [click here](/docs/google-ads-adwords-integration-setup-for-advertisers#configuring-google-ads-attribution-for-advertisers).

For details of how advertisers can attribute multiple agencies/MCC Google Ads accounts, click [here](/docs/recording-multiple-agency-mcc-google-ads-accounts).

## Agencies: collecting cost, clicks, and impression data

Agencies can [retrieve cost data](/docs/set-up-an-integrated-partner#cost-tab) from Google Ads, which also includes the clicks and impressions data.

The cost data is displayed on both the agency and advertiser dashboards, at the campaign level.

If the agency is transparent, then in the advertiser's dashboard the cost data is displayed under Google Ads campaigns. If it isn't, the data is displayed under the agency's campaigns.