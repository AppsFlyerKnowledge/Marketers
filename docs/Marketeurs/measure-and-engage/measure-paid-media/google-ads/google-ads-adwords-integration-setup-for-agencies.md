---
title: Google Ads (AdWords)—Integration setup for agencies
metadata:
  keywords:
    - Google
    - AdWords
    - Advertisers
    - Agencies
    - (AdWords)
    - google ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2017-07-23T11:26:20Z'
  edited_at: '2026-09-15T09:37:15Z'
  id: 115003669983
  locale: en-us
  section: Google Ads
  section_id: 6551205645457
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115003669983-Google-Ads-AdWords-Integration-setup-for-agencies
---
> **At a glance:** Setting up Google Ads integration with AppsFlyer — as an agency.

Both advertisers and agencies must actively configure the system. The following video shows the steps required by both the advertiser and agency to enable the agency to measure and attribute mobile traffic to the advertiser's app using Google Ads.

The configuration enables AppsFlyer to attribute conversions to an agency from within the AppsFlyer dashboard.

Before the Agency can begin the process, the Advertiser must first configure the Google Ads integration. For details, click <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers">here</Anchor>.

## Enabling agency attribution of Google Ads

AppsFlyer supports agency configurations with Google Ads. It is essential that the advertiser and the agency have separate Google Ads accounts to enable AppsFlyer to correctly attribute the data.

## Setting up Google Ads attribution for agencies

To start agency attribution of Google Ads campaigns with AppsFlyer, follow these steps:

<Accordion title="Watch">

<Embed title="Google Ads (AdWords)—Integration setup for agencies" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/fzihkki0qd" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Read">

<div id="advertiser-prestep-enabling-the-agency-access-to-google-ads" />

<Accordion title="Advertiser pre-step: enabling the agency access to Google Ads">

**Prerequisites:**

* In AppsFlyer, grant the agency access to the app using the instructions <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#autorisations-pour-lagence">here</Anchor>.
* In AppsFlyer, <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">activate</Anchor> the Google Ads partner.

**To share the advertiser's Link ID:**

1. In Google, go to the Google Ads Dashboard, click on the ***Tools*** icon

<Image align="center" alt="Google_Ag_1.png" src="https://files.readme.io/3a1188bc11e09779076c880c1b4d5e933845ee642393ff1367b2368c1199d8a2-50897694578449.png" />

2. Select ***Linked accounts***.

<Image align="center" alt="Google_Ag_2.png" src="https://files.readme.io/5bf0fb06df3263bc65a4e7e78539c06f2fce552b24b2913c18e155eff56f18ad-50897658813841.png" />

3. Under App Analytics Provider, find AppsFlyer. Select Options.

4. Click ***Share with another account***.

<Image align="center" alt="Google_Ag_3.png" src="https://files.readme.io/0659fc1f193ffc668f18f13641d07e085c94a97fb9e5c6c0f35188e1c18c632b-50897694583441.png" />

5. Insert the **Agency’s Google Ads Customer ID**

<Image align="center" alt="Google_Ag_4.png" src="https://files.readme.io/cce6c7aa387f354c004682c6d46b804897654c99b3346ce6c27a2bcf43259c2e-50897694584849.png" />

6. Click ***Next***. Click ***Send invite.***

<Image align="center" alt="Google_Ag_5.png" src="https://files.readme.io/d3da1850913f2c2a9b9125460cebd7e61922a177178c48cf23904d5a42445972-50897658822801.png" />

The advertiser can now see that the invitation request has been sent to the Agency. When the Agency accepts the invite, the status changes to Sharing.

For more details on sharing your Google Ads Link ID, click <Anchor target="_blank" href="https://support.google.com/adwords/answer/7365001">here</Anchor>.

<Image align="center" alt="Google_Ag_6.png" src="https://files.readme.io/b205e5b2771a128846b22d653998da09f8d600b6b60efb6ca1e90042ffba5ee7-50897694593041.png" />

</Accordion>

<div id="agency-step-1-accepting-the-link-id" />

<Accordion title="Agency step 1: accepting the Link ID">

On the Google Ads Words dashboard, the Agency receives an Invite and must accept the link.

<Image align="center" alt="Google_Ag_7.png" src="https://files.readme.io/f64942b5f67d9cb3ce692380626d9b87fb43a98ce825544b84e49c36162e349d-50897694593937.png" />

The Agency can see the link status is now Active.

<Image align="center" alt="Google_ag_8.png" src="https://files.readme.io/e44b590d4720accfde2ac95b97b18250ba2aab07f12651749592d4ad5aa8c947-50897658832017.png" />

</Accordion>

<div id="agency-step-2-setting-up-google-ads-on-appsflyer" />

<Accordion title="Agency step 2: setting up Google Ads on AppsFlyer">

An Agency can set up multiple Google Ads Customer IDs, if required.

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations**.
2. Search for and select **Google Ads**.

   <Image align="center" alt="gads-search.png" src="https://files.readme.io/97f9abe0e6bf4e07b81341f1c0a9978f6387747b412c53f7755c53a76ba0eaeb-50897694596881.png" />

   ***Activate partner*** should be ON and the ***Link ID*** set by the advertiser. These settings are grayed out to the agency.

   <Image align="center" alt="gads_agency-integration-link-id.png" src="https://files.readme.io/6d59ccad7fb3a4a0269b9e868e30b0b87eb23a83e07e6ef1d2603815352786bf-50897658836625.png" />
3. The Agency sets its Google Ads Customer ID.

   Enter **all** of the Google Ads Customer IDs (**Sub Accounts**) of the Google Ads accounts that the agency is running campaigns for the advertiser's app.

   You can find the Google Ads Customer ID by clicking on the arrow in the top left corner and thereby opening the Navigation Panel.

   <Image align="center" alt="" src="https://files.readme.io/5cc63138208e0ba55a59b4c2514dff373e45a25f50d92f9e6d8316356d078ed3-50897658839185.png" />
4. To measure running retargeting campaigns on Google Ads, ask the advertiser to activate **Google Ads Retargeting**. Once done, you can configure the **Re-Engagement Window**.

   <Image align="center" alt="gads-agency-retargeting.png" src="https://files.readme.io/42008f063585b0a1dff553b8391b9dca48c2a3657786c263459c717cc94b5b19-50897658842385.png" />
5. We recommend setting the Click-Through Attribution Lookback Window to **30 days**, to match the Google Ads value.

   <Image align="center" alt="gads-click-through.png" src="https://files.readme.io/9bf0456ecb003e4b2750e4e5c1455d4418de00b8815ae08e9e580763948e3721-50897694603025.png" />
6. The View-Through recommended is **1 day**, to match the Google Ads value. The scale allows you to customize the number of hours/days after an ad is viewed, during which the impression can be attributed to this partner.

   <Image align="center" alt="gads-view-through.png" src="https://files.readme.io/c26b18ff2d51ade48a9e57e0bb5097e4a0671f0ba78583cfeaa17848bebf9a34-50897658845969.png" />
7. ***Reinstall attribution***:
   * To enable reinstall attribution, switch it on.
   * No need to enable view-through attribution or configure lookback windows for reinstall attribution, as the values are taken from install attribution settings.
8. Click ***Save & Close***.

</Accordion>

<div id="agency-step-3-mapping-your-inapp-events" />

<Accordion title="Agency step 3: mapping your in-app events">

1. Click the **In-App Events** tab.

2. Select to either send In-App Events from Only Google Ads Installs or from All In-App Events to Google Ads.  
<Image align="center" alt="" src="https://files.readme.io/c2d22406f549db47de21beb54b7f9c8f94419702d0f78f46b2dbf0785e2ba94a-50897694609297.png" />

3. Map all In-App Events you want to send to Google Ads, with the pre-defined Google Ads events.

<Image align="center" alt="" src="https://files.readme.io/036b4f1cef8fa9b537b3aeaaab3f4072a099f94b3a8bbc539838d7898185a1ad-50897694610065.png" />

4. Click ***Save***.

> 🚧 **Important!**
>
> Import the first-open and in-app actions to Google Ads to begin counting conversions in both Google Ads and your AppsFlyer dashboard.
>
> To be able to import, you must launch the app and perform your mapped in-app events at least once.

> 📘 **Note**
>
> * It may take up to 6 hours until the new conversions change status from No Recent Conversion to Recording Conversion.
> * If an agency works with an MCC account and the app is promoted via several MCC sub-accounts all sub-accounts must be configured in the **Google Ads Customer ID** field (as seen on above screenshot). In such a case there is no need to configure the customer id of the MCC account.

</Accordion>

<div id="step-4-measure-your-app-conversions-mandatory" />

<Accordion title="Agency step 4: Measure your app conversions (mandatory)">

(**Google Ads** **admin only)**

> 🚧 **Important!**
>
> For Google Ads to register your new conversions, you must **launch your app and perform your mapped in-app events** at least once. To test iOS apps, you must collect IDFA to see the event. It may take up to 6 hours until the event conversions are added to the queue. Once they are added you can import them, and the new conversions change status from “No recent conversion” to “recording conversion".

1. Return to your Google Ads account (**Overview** page and go to **TOOLS AND SETTINGS** > **Measurement** > **Conversions**.  
   <Image align="center" alt="conversions_overview_en-us__1_.png" src="https://files.readme.io/8e4217e0fc2d9696b9aaee3e247ce38fbd5bafd70f05101b31b4ab8de524b3cb-50897694610833.png" />
2. Click **+ New conversion action**.   
   <Image align="center" alt="New_conversion_action_en-us__2_.png" src="https://files.readme.io/e4140f9a279c53bed9f0b576cc006bccd30fe737ea791ade47cd4d42c3e2074b-50897694612113.png" />
3. Select **App** from the list of conversion types, then select **Third-party app analytics**, and click **Continue**.  
   <Image align="center" alt="select_app_en-us__3_.png" src="https://files.readme.io/60d68af7588d5840bd478f2d6c7513f3a93fd2c409f780e13049cc5e639f2e98-50897658853137.png" />
4. Check the box next to **first\_open** of all your apps, and for each event you’d like to import.

   > 📘 **Note**
   >
   > You need to re-import if the **Partner Event identifier** in Google Ads is changed or if it's CUSTOM and the corresponding event name has changed in AppsFlyer.


   Click **Import and Continue**, then click **Done**.   
   <Image align="center" alt="select_events_to_import_en-us__4_.png" src="https://files.readme.io/efe5458d26e6085aa0c228b98f63d37ef932e672e83ebc9050437b3b1259eea1-50897658853905.png" />
5. You can now see your third-party conversion events on the **Conversions** > **Summary** page. If an event doesn't appear in the list or it has been removed from the Google Ads conversion list, click **View all conversion actions**. The **Status** filter appears.   
   <Image align="center" alt="conversions_summary_en-us__5_.png" src="https://files.readme.io/406121cc793f06d778192f8c8b191d7db0f11f91614cc4cf411a940ea176cd95-50897694614801.png" />
6. Click **Status** and select **All** to see all events, including disabled and removed events.  
   <Image align="center" alt="conversion_action_status__6_.png" src="https://files.readme.io/f1294f57798cb4222775678a496be20b57238316b03a11e9a390b5362d1878c8-50897694615313.png" />
7. Congratulations! You're now measuring Google Ads mobile campaigns with AppsFlyer!

> 📘 **Note**
>
> Please ensure your "include in conversions" setup is aligned with your campaign goals in Google Ads. For more information, consult with your Google representative or refer to the Google documentation <Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">here</Anchor>.

</Accordion>

</Accordion>

To watch the video "Setting-Up Google Ads Attribution for Advertisers" <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#configuration-de-lattribution-de-google-ads-pour-les-annonceurs">click here</Anchor>.

For details of how advertisers can attribute multiple agencies/MCC Google Ads accounts, click <Anchor target="_blank" href="/marketers/fr/docs/recording-multiple-agency-mcc-google-ads-accounts">here</Anchor>.

## Agencies: collecting cost, clicks, and impression data

Agencies can <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#cost-tab">retrieve cost data</Anchor> from Google Ads, which also includes the clicks and impressions data.

The cost data is displayed on both the agency and advertiser dashboards, at the campaign level.

If the agency is transparent, then in the advertiser's dashboard the cost data is displayed under Google Ads campaigns. If it isn't, the data is displayed under the agency's campaigns.

<div data-zendesk-anchors="h_01HKA1J5ES5T65NT5QMY5ZGXP6=enabling-agency-attribution-of-google-ads h_01HKA1J5ESJYS902S9Z3YY5FV9=setting-up-google-ads-attribution-for-agencies h_01HKA1J5ESF3ZK9E9PKM9AN8C8=advertiser-prestep-enabling-the-agency-access-to-google-ads h_01HKA1J5ETKV3H3KYBEYQZMSXA=agency-step-1-accepting-the-link-id h_01HKA1J5ET2BV8GHXZS5T8KCGZ=agency-step-2-setting-up-google-ads-on-appsflyer h_01HKA1J5ETH4TTVDSP0HNK6F0Q=agency-step-3-mapping-your-inapp-events h_01HKA1J5ETK5PXYFPXPBVH0HJQ=important h_01HKA1J5ETNQ1FCBMVTQED74HG=note h_01HKA1J5ETKH9GKAX3HZMA7W57=step-4-measure-your-app-conversions-mandatory h_01HKA1J5ET210B40MPFQ79PPSN=important-1 h_01HKA1J5ETNTFKKDF6NC635H3W=note-1 h_01HKA1J5ETEWJN8MH9NPWTWX0F=note-2 h_01HKA1J5ETPYE7B2NFPFHA05YT=agencies-collecting-cost-clicks-and-impression-data" />
