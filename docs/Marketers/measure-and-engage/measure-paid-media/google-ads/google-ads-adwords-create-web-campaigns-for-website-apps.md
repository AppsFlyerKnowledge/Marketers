---
title: Google Ads (AdWords)—Create web campaigns for website apps
metadata:
  keywords:
    - Advertisers
    - Agencies
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
  created_at: '2026-04-07T12:46:10Z'
  edited_at: '2026-10-16T09:34:25Z'
  id: 45498975339537
  locale: en-us
  section: Google Ads
  section_id: 6551205645457
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/45498975339537-Google-Ads-AdWords-Create-web-campaigns-for-website-apps
---
> **At a glance:** Set up a Google Ads integration for your website app to send web conversion signals to Google via the Offline Conversion API (OCI).

<div id="overview" />

## Overview

AppsFlyer supports integration with Google Ads (`googleads_int`) for website app campaigns and reports conversion data through the Google Offline Conversion API (OCI).

In this article, you'll learn how to set up web campaigns in AppsFlyer and Google Ads, targeting users who interact with Google Ads and convert on your website.

The campaign flow starts when a user clicks a Google ad and lands on your website. When the user completes a website event (for example, a purchase or sign-up), AppsFlyer sends the conversion signal to Google Ads via OCI. Google uses this data to optimize ad targeting and measure campaign performance.

<div id="prerequisites" />

### Prerequisites

Before activating the Google Ads integration for website app campaigns, make sure you have:

* A website app set up in AppsFlyer
* Either the AppsFlyer Web SDK deployed on your website, or a fully server-side integration using the server-to-server (S2S) API. For more information, see <Anchor target="_blank" href="/marketers/docs/server-to-server-s2s-api-for-web-performance-measurement#set-up-a-fully-server-side-integration">Set up a fully server-side integration</Anchor>
* An AppsFlyer account with appropriate roles or permissions

<div id="how-to-set-up-a-google-ads-web-campaign" />

### How to set up a Google Ads web campaign

The setup has two parts:

1. Set up the Google Ads integration in AppsFlyer (required)
2. Set up the campaign in Google Ads (required)

<div id="set-up-the-google-ads-integration-in-appsflyer" />

## Set up the Google Ads integration in AppsFlyer

Start by activating the Google Ads integration for web campaigns and setting up the postbacks that AppsFlyer sends to OCI.

<div id="step-1-activate-the-integration" />

<Accordion title="Step 1: Activate the integration">

1. In AppsFlyer, from the side menu, open **Collaborate > Partner Marketplace**.
2. Search for **Google Ads Web** and select it.
3. Click **Set up integration**. You are directed to the **Active Integrations** setup page.
4. In the app dropdown, select the web app.
5. In the **Integration** tab, turn on **Activate Partner**.

   <div id="note" />

   > 📘 **Note**
   >
   > The toggle must stay on (activated) for as long as you work with this partner.

6. Enter your **Customer ID**. You can retrieve it from your Google Ads Manager:
   1. <span class="af-ol-a"></span>Log in to your Google Ads account.
   2. In the top-right corner, click the Google account icon and scroll down to where the Customer ID is displayed.
   3. Perform one of the following:
      * If you have multiple Google Ads accounts running campaigns for your app, use the Customer ID from a Manager (MCC) account for cross-account conversion tracking. Paste the MCC ID (and not a specific account’s Customer ID) in the Customer ID field and also in the MCC Customer ID text box (same ID in both boxes).  For more information, see <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">Google's instructions on configuring an MCC account</Anchor>.
      * If you only use a single Google Ads account to run ads, paste the account ID in the Customer ID text box. Leave the MCC Customer ID text box empty.
7. To allow AppsFlyer to upload conversions to Google Ads, click **Sign in with Google**.
8. Select the admin account of the MCC account from which you retrieved the Customer ID.
9. Click **Allow**.

   <div id="note-1" />

   > 📘 **Note**
   >
   > The **Missing token** error message will stop appearing once you sign in with Google and allow AppsFlyer to fetch the token. If the error persists after sign-in, verify that your token has the required permissions.


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="Step 2: Set in-app event postbacks">

Map your website events to Google Ads conversion actions. AppsFlyer sends these events to Google via OCI to power conversion-based optimization.

<div id="note-2" />

> 📘 **Note**
>
> For website apps, all events are web events. There are no install events. Each event you want Google to optimize for must be mapped to a corresponding Google Ads conversion action ID.

1. Turn on **In-app event postbacks**.
2. Set the **In-app event postback window** if needed. The window is opened at the time of the user's first website conversion event (the web equivalent of the mobile install date).
3. Click **Add event**.
4. In the **AppsFlyer event** column, select the website event you want to send (for example, `purchase`, `sign_up`).

   <div id="note-3" />

   > 📘 **Note**
   >
   > Visit events are excluded. Only custom web events are available in this dropdown.

5. In the **Mapped to partner event** column, enter the Google Ads **conversion action ID**. Before you can do this, you need to create the conversion action in Google Ads (see [Step 2: Create conversion actions](#step-2-create-conversion-actions)). To find the conversion action ID:
   * In Google Ads, open the conversion action page.
   * Open the **Details** tab.
   * From the page URL, copy the value of the `ctid=*` query parameter. For example, if `ctid=123456789`, enter `123456789`.
6. In the **For users from** column, select **This partner only**, to send events attributed to Google Ads only.
7. In the **Including** column, select whether to include revenue values in the postback.
8. Click **Save integration**.

<div id="note-4" />

> 📘 **Note**
>
> If you send S2S events and want AppsFlyer to send postbacks for them to Google Ads, make sure each event has at least one Google click ID: `gclid`, `gbraid`, or `wbraid`. If an event has none, AppsFlyer doesn't send the postback. For all supported event fields, see <Anchor target="_blank" href="/marketers/docs/server-to-server-s2s-api-for-web-performance-measurement#measure-an-event">Server-to-Server (S2S) API for Web Performance Measurement</Anchor>.

</Accordion>

<div id="set-up-a-web-conversion-campaign-in-google-ads" />

## Set up a web conversion campaign in Google Ads

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="Step 1: Set the campaign type, objective, and goals">

1. Log in to Google Ads and create a campaign.
2. Select the **campaign objective**:
   * All objectives are applicable except **App promotion**, which is for mobile app campaigns only.
   * We recommend **Sales** or **Leads** for optimization based on specific website conversion events.
3. Select your **conversion goals**. By default, you see the account-level goals. You can keep those or remove ones that are not relevant.
   * If the goal you want to optimize for is not listed, create a custom conversion action (see [Step 2: Create conversion actions](#step-2-create-conversion-actions)).
4. Select the **campaign type**:
   * All types are applicable except **Shopping**, which requires a product catalog and a verified domain.

</Accordion>

<div id="step-2-create-conversion-actions" />

<Accordion title="Step 2: Create conversion actions">

For each website event you mapped in AppsFlyer, create a corresponding conversion action in Google Ads. After creating it, copy the conversion action ID and paste it into the AppsFlyer event mapping in the previous section.

1. In Google Ads, from the side menu, open **Goals > Conversions > Summary**.
2. Click **+ New conversion action**.
3. Select **Import** as the conversion data source, then select either:
   * **Manual import using API or uploads > Track conversions from clicks**, OR
   * **CRM, files, or other data sources > Track conversions from clicks**, and under Data source, select **Skip this step and set up data source later**.
4. Click **Continue**.
5. In **Conversion goal**, select a conversion action category.
6. Enter a **Conversion name** and click **Add**.

   <div id="important" />

   > 🚧 **Important!**
   >
   > To use the Offline Conversions API with GBRAID/WBRAID (in addition to GCLID), make sure the **Count** field in the conversion action is set to **Every** (default) and not **One**.


   <div id="note-5" />

   > 📘 **Note**
   >
   > If you only want your campaigns to optimize to a single action, include only that action in this category. For example, if you want your campaign to optimize toward a purchase conversion action, make sure that it is the only one in its category. You can then select this category as the conversion goal for performance optimization when creating the campaign.

7. Click **Save and continue**, then **Done** without setting up data sources. Your new conversion action might initially appear as **Inactive**. It will change to **Active** once actual data is sent.
8. To map the new conversion action to the AppsFlyer postback event, retrieve the conversion action ID: In the conversion goals **Summary** page, click the conversion action you created and copy the value of the `ctid=*` query parameter from the page URL.
9. In AppsFlyer, paste the `ctid` value into the **Mapped to partner event** column of the postback event you want Google to optimize for. See [Step 2: Set in-app event postbacks](#step-2-set-inapp-event-postbacks).

</Accordion>

<div id="step-3-set-the-campaigns-final-url" />

<Accordion title="Step 3: Set the campaign's Final URL">

Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">defines the Final URL</Anchor> as "the URL address of the webpage in your website that people reach after they click your ad, also known as the 'landing page.'"

1. In Google Ads, open the **Campaigns > Ads** page.
2. In the ad row, click the edit icon.
3. In the **Final URL field**, enter the URL of your landing page.

   <div id="important-1" />

   > 🚧 **Important!**
   >
   > The Final URL cannot be an AppsFlyer URL (OneLink or a single-platform attribution URL), as this might cause your campaign to be rejected. Only use a direct web address with no redirects.
   >
   > You can add AF attribution parameters to the Final URL and map them to Google ValueTrack parameters, for example, `af_c_id={campaignid}`. Once the Google ad is clicked and the landing page is loaded, these parameters are available on the page. To learn about the available ValueTrack parameters, see the <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348">Google documentation</Anchor>.
   >
   > For example:
   >
   > ```http
   > https://example.com?product=1234&af_c_id={campaignid}
   > ```


<div id="note-6" />

> 📘 **Note**
>
> Google Web Ads campaigns can use two URLs per engagement: the Final URL and the Tracking Template URL. However, the Tracking Template URL is not required for website app campaigns where the ad destination is a website. A Tracking Template URL might be needed only when the campaign goal is web-to-mobile. For more information, see the <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-create-web-based-campaigns">Google Ads web-to-app campaign article</Anchor>.

</Accordion>

<div id="view-web-performance-measurement-data" />

## View Web Performance Measurement data

Web attribution data for Google Ads campaigns is available in the cross-platform dashboard and in raw data exports:

* **Dashboard:** In <Anchor target="_blank" href="/marketers/docs/my-dashboards#crossplatform-dashboard">the cross-platform dashboard</Anchor>, web and app data are displayed side by side, giving you a unified view of campaign performance across platforms.
* **Raw data exports:** Web attribution data is also available in the <Anchor target="_blank" href="/marketers/docs/raw-data-export-page">Raw data exports page</Anchor>.
  * The `media_source` field shows `googleadwords_int` for web events attributed to Google Ads.

<div id="note-7" />

> 📘 **Note**
>
> This unified reporting view lets you analyze both web and app campaign performance in one place, including full mobile and web cost reporting.

<div id="measure-web-performance-data-with-web-cost" />

## Measure web performance data with web cost

You can get a complete performance view of web attribution data and web cost data from Google Ads in the dashboard and in <Anchor target="_blank" href="/marketers/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">Cost ETL reports</Anchor>. To do this, make sure you have <Anchor target="_blank" href="/marketers/docs/roi360-onboarding-guide#about-roi360">the ROI360 package</Anchor> and complete the following setup:

1. Connect the cost to your website app via  `googleadwords_int` (not via `googleads_int`)  from the **Cost** tab or the **Cost Settings** page. For more information about how to connect to cost, see <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Set up ROI360 cost API to measure cost data</Anchor>.
2. Include the campaign ID (`af_c_id`) in the landing page URL. Make sure the URL includes the full campaign hierarchy to view cost, clicks, and impressions matched to web attribution at the most granular level.

<div id="troubleshooting-in-app-event-postbacks" />

## Troubleshooting in-app event postbacks

If event data is not appearing in Google Ads, check the following before contacting support.

<div id="set-token-permissions" />

<Accordion title="Set token permissions">

In Google Ads, make sure that your access token has the necessary permissions to upload offline conversions:

1. Go to the Google Developers Console.
2. Make sure that `uploadClickConversions` has the following OAuth scope: `https://www.googleapis.com/auth/adwords`
3. In AppsFlyer, in the Integration tab, click **Sign in with Google**.
4. Select the admin account of the MCC account.
5. Click **Allow**.

</Accordion>

<div id="mcc-customer-id" />

<Accordion title="MCC customer ID">

If you have multiple Google Ads accounts running campaigns for your app, you must use the Customer ID of an MCC account. See <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186">Google's instructions on configuring an MCC account</Anchor>.

</Accordion>

<div id="conversion-action-id" />

<Accordion title="Conversion action ID">

Make sure the postback in-app events are mapped to the correct conversion action ID. To find the conversion action ID in Google Ads, see [Step 2: Create conversion actions](#step-2-create-conversion-actions).

</Accordion>

<div id="traits-and-limitations" />

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Clicks and impressions | Clicks and impressions for web campaigns require an <Anchor target="_blank" href="/marketers/docs/roi360-onboarding-guide">ROI360 subscription</Anchor>. |

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/web-performance-measurement-overview">Web Performance Measurement - Overview</Anchor>

<div data-zendesk-anchors="h_01KNM00RR7V9BAA2BSPDECHC9F=overview h_01KNM00RR7H7A9CE06APEZSXKR=prerequisites h_01KNM00RR77P8VD2YJ2R7DZBVX=how-to-set-up-a-google-ads-web-campaign h_01KNM00RR7E8MFSTGYKFEJDS1C=set-up-the-google-ads-integration-in-appsflyer h_01KNM00RR71ZXB72H8X1YXWKED=step-1-activate-the-integration h_01KNM00RR84CCGBR3T5WG7C5VW=note h_01KNM00RR86C5VKBVTA9X6QRAS=note-1 h_01KNM00RR8BCJTMPZ29C841BY1=step-2-set-inapp-event-postbacks h_01KNM00RR8PSJ7FEAP7MMEJ1XG=note-2 h_01KNM00RR89XJ0BZKFDXVC4860=note-3 h_01M520ZTQ1QT2F03TMY9TZBPSY=note-4 h_01KNM00RR8SAS3TM1NG5DC58TF=set-up-a-web-conversion-campaign-in-google-ads h_01KNM00RR8S24AG7FMN6067PZ2=step-1-set-the-campaign-type-objective-and-goals h_01KNM00RR8H1ZFSHFT0DVB11GN=step-2-create-conversion-actions h_01KNM00RR8EV8XY02YJFV5XSX8=important h_01KNM00RR8N96SNP1YK0CTN6YZ=note-5 h_01KNM00RR82NZSKB7K06HCP1VE=step-3-set-the-campaigns-final-url h_01KNM00RR8EP6J43G29Q8VVA5B=important-1 h_01KNM00RR8A704MKGVVC6MQ2KN=note-6 view-web-attribution-data=view-web-performance-measurement-data h_01KNM00RR8EYJAX2KRGCM65E9M=view-web-performance-measurement-data h_01KNM00RR86Q2GTHVNC505KCXZ=note-7 measure-web-attribution-data-with-web-cost=measure-web-performance-data-with-web-cost h_01KNM00RR9TF8JRTJXWN23MF1S=measure-web-performance-data-with-web-cost h_01KNM00RR9Z0BM5EE62M17EE0F=troubleshooting-in-app-event-postbacks h_01KNM00RR9CJJQAP4GAXZ9KK8N=set-token-permissions h_01KNM00RR9215H3KB024BBFZX2=mcc-customer-id h_01KNM00RR9DBR5979GA0FVD5AK=conversion-action-id h_01KQAE3JKMQ6ZEATDAEXBC4PT6=traits-and-limitations h_01KQC2B644Y44631ZQKC1HPEF4=see-also" />
