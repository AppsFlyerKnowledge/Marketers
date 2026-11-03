---
title: Google Ads Web—Integration for PC and console apps
metadata:
  keywords:
    - google ads configuration
    - google ads
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2024-01-18T11:04:33Z'
  edited_at: '2026-09-15T09:40:50Z'
  id: 21768823915665
  locale: en-us
  section: Google Ads
  section_id: 6551205645457
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/21768823915665-Google-Ads-Web-Integration-for-PC-and-console-apps
---
> **At a glance:** Use Google Ads web campaigns to promote your apps on PC and console platforms and enable attribution. AppsFlyer supports Google web-based campaigns using cross-platform landing pages or direct attribution links.

> 📘 **Note**
>
> This article focuses on web campaigns that promote PC or Console apps. If you want to create web campaigns that promote mobile apps, see <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-create-web-based-campaigns">Google Ads (AdWords) - Create web-based campaigns</Anchor>.

## Overview

This article contains information and steps on how to set up and use Google Ads Web for PC and console apps with AppsFlyer. This includes:

* [Activate the partner integration in AppsFlyer](/docs/google-ads-web-integration-for-pc-and-console-apps#activate-partner-in-appsflyer).
* [Set up Google Ads Web in AppsFlyer](/docs/google-ads-web-integration-for-pc-and-console-apps#setting-up-Googleadsweb-in-appsflyer).
* [Set up campaigns in Google Ads for PC and console apps](/docs/google-ads-web-integration-for-pc-and-console-apps#set-up-campaigns-in-google-ads-web-for-pc-and-console-apps).

### Prerequisites

Before activating the Google Ads Web integration, make sure you have:

* A PC or console app
* An AppsFlyer account
* A Google access token with the <Anchor target="_blank" href="https://developers.google.com/identity/protocols/oauth2/scopes">required OAuth scope</Anchor>. You can verify the scopes associated with your access token in the Google Developer Console.
* AppsFlyer <Anchor target="_blank" href="/marketers/fr/docs/user-management">users with appropriate roles/permissions</Anchor> and access to the relevant apps

## Activate partner in AppsFlyer

**To activate the partner integration:**

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Partner Integrations > Marketplace** tab.
2. Search for **Google Ads Web** and select it or click **Integrate**.
3. You’re directed to the setup page.
4. In the **Integration** tab, turn on **Activate partner**.  
   **Note:** The toggle must stay on (<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">activated</Anchor>) for as long as you work with the partner.
5. Complete the configuration using the relevant tabs, as described in the next section.

## Set up Google Ads Web in AppsFlyer

In this part of the setup, you can also set up postbacks to Google Ads. The Google Ads Web (googleads\_int) integration uses an API tool provided by Google Ads for advertisers to send data from their **PC and console apps** directly to Google's servers. Such data may include user actions, such as purchases, registrations, and other types of conversions performed on non-mobile platforms (websites or applications). The data is then used by Google Ads to optimize ad targeting, measure ad performance, and build custom audiences for retargeting.

The integration with Google Ads Web only supports sending postbacks for installs and in-app events.

<div id="integration-tab" />

<Accordion title="Integration tab">

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

To configure the integration, you must first turn on the **Activate partner** toggle.

#### General settings

> 📘 **Note**
>
> The **Missing token** error message will stop appearing once you’ll sign in with Google and allow AppsFlyer to fetch the token in the step below. If the error persists after you sign in, <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-create-web-based-campaigns#access-token-permissions">verify that your token has the required permissions</Anchor>.

1. **First open conversion ID**: Enter the ID of the `First open` conversion action you set in Google Ads. To find the ID:
   1. Go to the Google Ads platform and open the **Details tab** of the **First open** conversion action page.
   2. Copy the value of the `ctid=*` query parameter from the page URL. For example, if `ctid=123456789`, insert `123456789` to the **First open conversion action ID** box.
2. Enter your **Customer ID**. You can retrieve it from your Google Ads Manager:
   1. Sign in to your Google Ads account.
   2. In the top right corner, click the Google account icon and scroll down to where the Customer ID is displayed.
   3. If you have multiple Google Ads accounts running campaigns for your app, you must use the Customer ID from a manager (MCC) for cross-account conversion tracking. Paste the **MCC ID** (and not a specific account’s Customer ID) in the **Customer ID** text box and also in the **MCC Customer ID** text box (same ID in both boxes).   
      If you only use a single Google Ads account to run ads, simply paste the account ID in the **Customer ID** text box and leave the **MCC Customer ID** text box empty. See <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">Google instructions on configuring an MCC account</Anchor>.
3. To allow AppsFlyer to upload conversions to Google Ads, click **Sign in with Google**.
4. In Google, select the admin account of the MCC account from which you retrieved the Customer ID above.
5. Click **Allow**.

#### Enable view-through attribution

AppsFlyer supports view-through attribution for Google Web campaigns using a <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-create-web-based-campaigns#create-a-landing-page-with-onelink-smart-script">Smart Script</Anchor> or <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-create-web-based-campaigns#create-a-landing-page-with-onelink-smart-banners">Smart Banner</Anchor>-enabled landing page. This allows probabilistic modeling (PMOD) attribution of app installs triggered by ad impressions, even when users don’t click the ad directly.

When a user sees a Google ad and lands on a <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-create-web-based-campaigns#create-a-landing-page-with-onelink-smart-script">Smart Script</Anchor> or <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-create-web-based-campaigns#set-up-a-smart-banners-landing-page">Smart Banner</Anchor>-enabled landing page, AppsFlyer can attribute the resulting app install, including cross-platform, back to the original web impression.

When available, AppsFlyer includes the `gclid` in the postback to Google.

**To enable view-through attribution:**

1. In AppsFlyer, from the sidebar, open **Active Integrations** > **Google Ads Web**.
2. In the **Integration** tab, scroll to the **Install attribution** section.
3. Turn on **Install view-through attribution**.
4. **[optional]** Turn on **Cross-platform equal attribution priority** and set its lookback window. For more information, see <Anchor target="_blank" href="/marketers/fr/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Enable equal priority for cross-platform impressions</Anchor>.
5. Open the **Attribution** tab.
6. Scroll to the **View-through attribution** section and set the preferred **view-through lookback window** (up to 24 hours).
7. Click **Save integration** to apply the changes.

#### Default postbacks

Postbacks for installs are automatically sent only to Google Ads Web.

#### In-app event postbacks

Configure mapping of in-app event postbacks sent to Google Ads Web. These events can be viewed in the Google Ads Manager:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<ul><li>Click **Add item**, enter the event name, and click ![check.png](https://files.readme.io/e35a3abe980b27d52189e5d75abac298090f85030adf7bbb56590efcee82f172-21884077142033.png).</li></ul> |
| **mapped to partner event** | The Conversion Action ID of each event, as is defined on the partner's side.<ol><li>In Google Ads **Conversion Goals** page, click the conversion action you created.</li><li>In the Conversion Action **Details** page, copy the **Conversion Action ID** from the URL parameter `ctId=`.</li><li>Go back to AppsFlyer and paste it. For example if `ctid=123456789`, paste `123456789`.</li></ol> |
| **for users from** | **This partner only:** In-app event postbacks are sent only for events attributed to this partner—meaning, the user who performed it came from this partner. |
| **including** | **Values and revenue:** All event parameters, including the revenue value (if exists in the event), are sent in the postback. |

3. [Optional] Click the **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/80bb94ed7b843ce7a543390d831ddb09b161236f8aede0b053a32fc676524e5f-21884084481041.png" width="30px" />icon to <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event.
4. Set the **In-app event postback window**, if required (read more about <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#in-app-event-postback-window">in-app event postback window configuration</Anchor>).
5. Click **Save integration**.
6. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the integration steps for the selected app.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generating an attribution link in the AppsFlyer UI isn't currently available. However, you can either use a cross-platform landing page with SmartScript or create a direct attribution link for your app (see table below).

| Option | Actions | Who's involved |
| --- | --- | --- |
| Cross-platform landing page | **Recommended**: For when your campaign promotes an app that's also available on multiple platforms, like Epic and Steam.<br /><br /><Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Learn about cross-platform landing pages</Anchor><br /><br /><Anchor target="_blank" href="/marketers/fr/docs/cross-platform-landing-pages-with-smart-script">Learn how to set up a cross-platform landing page</Anchor><ul><li>Make sure all relevant URL parameters (that are later captured by the Smart Script) are appended to the ad URL</li><li>Make sure the script takes the GCLID from the incoming URL and adds it to the generated link. Meaning, map the outgoing GCLID URL param `gclid` to the incoming URL param `gclid`. **Note**! To display in AppsFlyer raw data reports, the incoming `gclid` param must also mapped to one of the outgoing params  `af_sub[1-5]`.</li></ul> | Marketer (may require developer assistance) |
| Direct attribution link | If you don't use a cross-platform landing page, because you only have 1 app on 1 platform, you can create direct attribution links to place behind ads.<br /><br /><Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-direct-attribution-links">Learn how to create direct attribution links</Anchor><ul><li>Make sure the following parameters are included in your link:<ul><li>af\_media\_source</li><li>af\_campaign\_id</li><li>af\_r<br />**Note**: The <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">Google click identifier (GCLID)</Anchor> parameter is automatically added by Google Ads to any outgoing click if you are using <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3095550?hl=en">auto-tagging</Anchor>. If auto-tagging is deactivated in your Google Ads account, add `gclid={gclid}` to the Google Ads tracking template URL.</li></ul></li><li>For af\_camapign\_id, af\_adset\_id and af\_ad\_id parameters, you can use Google’s [value track parameters](https://support.google.com/google-ads/answer/6305348) (dynamic URL parameter) macros. All other parameters should be set manually.</li><li>Don't include the af\_dp parameter.</li></ul>**Template to use for most platforms (Epic, Steam, Xbox, PlayStation, etc.)**:<br /><br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}? af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Sample link leading to Steam**: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Template to use for Google PC and Mac apps ONLY**:<br /><br />`https://app.appsflyer.com/{app_id}?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Sample link leading to Google PC**: `https://app.appsflyer.com/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}` | Marketer |

> 👍 **Tip**
>
> To simplify campaign analysis, include the campaign type, web or mobile, as a prefix or suffix in the campaign name (e.g., campaign-name\_web)

</Accordion>

## Set up campaigns in Google Ads Web for PC and console apps

When you set up a new campaign, you can either direct users to a:

* Cross-platform landing page: Recommended for when your campaign promotes an app that's also available on multiple platforms, like Epic and Steam.
* Single store: This uses a direct attribution link and should be used when you only have 1 app on 1 platform.

The instructions for setting up campaigns to redirect users to either of these options are detailed in the sections that follow.

**Note**: During campaign setup, you may want to configure your own conversion actions and goals. Instructions on how to do this are also detailed in the sections that follow.

<div id="campaigns-that-redirect-to-a-crossplatform-landing-page" />

<Accordion title="Campaigns that redirect to a cross-platform landing page">

**To set up a campaign that redirects users to a cross-platform landing page**:

1. Set up a cross-platform landing page as described in the [attribution link section](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab).
2. Log in to Google Ads and create a new campaign.
3. Select the campaign objective.  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * All objectives are applicable, except "App promotion" (which can only be used for mobile app campaigns).
   * We recommend setting the "Sales" campaign objective for optimization based on specific in-app events.
4. Select the conversion goals.  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * By default, you see the predefined account-level campaign goals. You can keep those, or remove ones that aren't relevant for your campaign.
   * If you don’t see the goal you want, [add the conversion action and conversion goal](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals).
   * You can also edit your predefined goals in the Conversions page.
5. Select the campaign type.  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * All campaign types are applicable, except "Shopping" which requires a product catalog and is limited to verified domains.
6. Enter the cross-platform landing page URL as Google's final URL.

</Accordion>

<div id="campaigns-that-redirect-to-a-single-app-store" />

<Accordion title="Campaigns that redirect to a single app store">

**To set up a campaign that redirects users to a single platform and app store**:

1. Set up a direct attribution link as described in the [attribution link section](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab).
2. Log in to Google Ads and create a new campaign.
3. Select the campaign objective.  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * All objectives are applicable, except "App promotion" (which can only be used for mobile app campaigns).
   * We recommend setting the "Sales" campaign objective for optimization based on specific in-app events.
4. Select the conversion goals.  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * By default, you see the predefined account-level campaign goals. You can keep those, or remove ones that aren't relevant for your campaign.
   * If you don’t see the goal you want, [add the conversion action and conversion goal](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals).
   * You can also edit your predefined goals in the Conversions page.
5. Select the campaign type.  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * All campaign types are applicable, except "Shopping" which requires a product catalog and is limited to verified domains.
6. Enter the link to be used as Google's final URL.
   * This must be the final web location you want to redirect your users to. It can be any web URL including a web landing page or store URL. For example: `https://store.steampowered.com/app/{appid}/{myapp}/`.
   * The final URL can't be an AppsFlyer URL, as this may cause your campaign to be rejected. Only use a direct web address that has no redirects.
7. Enter your AppsFlyer direct attribution link as Google's Tracking Template URL.
   * For parallel tracking to function as intended, the final URL must be placed in the `{lpurl}` ValueTrack parameter in Google’s Tracking Template URL as specified by Google.
   * Don't include the af\_dp parameter.

</Accordion>

<div id="creating-conversion-actions-and-goals" />

<Accordion title="Create conversion actions and goals">

In Google Ads, you can either select from the predefined list of conversion actions and goals or create your own.

**Important!** For AppsFlyer to send a "First Open" event postback, you need to create a conversion action and name it "First Open".

**To create your own Google Ads conversion actions and goals**:

1. In your Google Ads account overview page, from the side menu, select **Goals** > **Conversions** > **Summary**.
2. Click **+ New conversion action**.
3. Select **Conversions offline** as your conversion actions data source.
4. Select **Import** from the list of conversion types, then select **Manual import using API or uploads** > **Track conversions from clicks**.

   > 📘 **Note**
   >
   > If **Manual import using API or uploads** is not available:
   >
   > 1. Select **CRM, files, or other data sources** > **Track conversions from clicks.**
   > 2. In **Data source** select **Skip this step and set up data source later.**

5. Click **Continue**.  
   A form displays.
6. Fill out the form and click **Create and continue** to finish creating your conversion tracker.
7. For **Goal and action optimization**, select a category to map your conversion action into.  
   **Note**: Google ads campaign optimization is per category; not per specific action). If you only want your campaigns to optimize to a single action, make sure to map only that action to this category. For example, if you want your campaign to optimize towards the "install" action, make sure to map the "install" action to its own category, for example, “Other.” You’ll then be able to select this category as the campaign goal when creating the campaign.
8. Copy the conversion action ID from Google Ads and enter it in the **mapped to partner event** field. The **Conversion Action ID** is used as the partner event ID when mapping the AppsFlyer event name to the partner event ID  in the in-app event postbacks setup. To copy the conversion action ID from Google Ads perform the following:
   1. In Google Ads **Conversion Goals** page, click the conversion action you created.
   2. In the Conversion Action **Details** page, copy the **Conversion Action ID** from the URL parameter `ctId=` and paste it.
9. Click **Create and continue**.
10. Click **Finish**.

</Accordion>

## View web-to-app attribution data (from November 2, 2025)

Although web-based conversion events are sent to Google under the original `googleads_int` PID, they are reported in the AppsFlyer dashboard and raw data reports under the `googleadwords_int` PID. This applies both to primary conversion events and to conversion assist events.

This unified reporting view lets you analyze both web and app campaign performance in one place, including full mobile and web cost reporting.

### View in the dashboard

All Google web-to-app attributions appear under `googleadwords_int` in the Overview and Activity dashboards. This provides a single, consolidated view of campaign results across platforms. Use standard filters and breakdowns to compare app and web traffic within your Google Ads data.

### View in raw data and API reports

* **Raw data exports and API responses** include the `googleadwords_int` PID in the `media_source` field for Google web activity. To verify web campaign setup details, refer to the `original_url` field that shows `googleads_int` as the PID used during the creation of web campaigns.
* **Postback reports** show `googleads_int` as the original media source to which the postback was sent.

## Traits and limitations

| Trait | Description |
| --- | --- |
| Clicks and impressions (Temporary limitation) | Clicks and impressions for campaigns targeting PC & Console apps are temporarily not available from Google SRN (`googleadwords_int`). |

<div data-zendesk-anchors="h_01JP7SMGEPTQGHRYYCBWECH46X=note h_01HK4QHRJG6WTN9P6ZG83XQ6AY=overview h_01HFXV8HPGCRGYPEW0NPJ0NR0S=prerequisites activate-partner=activate-partner-in-appsflyer h_01HFXV8HPH3N4DBKKTQE6DK7FK=activate-partner-in-appsflyer setting-up-metaweb-in-appsflyer=set-up-google-ads-web-in-appsflyer 01H88VAJH3VENKYVRQY5RXN63P=set-up-google-ads-web-in-appsflyer 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=activate-partner h_01HFXV8HPH6X92YETNAGZ910AV=activate-partner transaction-id=general-settings h_01HARQDVEDA206D0BBXBC6WEHH=general-settings h_01JK8XJJWQK5MEJF7GTC5C1707=note-1 enable-viewthrough-attribution=enable-view-through-attribution h_01ZXVWB0GZKWB53KTBWJ51RMBM=enable-view-through-attribution 01H88VAJH3WE9Z0971WMBRBJRS=default-postbacks inapp-event-postbacks=in-app-event-postbacks 01H88VAJH3AS37MVF75GANWX4B=in-app-event-postbacks 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab h_01K88M617Q7SVMDEKP5HTKANJM=tip setting-up-campaigns-in-meta-web-for-pc-and-console-apps=set-up-campaigns-in-google-ads-web-for-pc-and-console-apps h_01HK4S03KVAN99YKXTHAKCT420=set-up-campaigns-in-google-ads-web-for-pc-and-console-apps h_01HMR6HVJF4QT1EZKYZKRVTWEE=campaigns-that-redirect-to-a-crossplatform-landing-page h_01HMR6HVJFMN1V7VM58ZMQFEXF=campaigns-that-redirect-to-a-single-app-store h_01HMTXEZB3W19TKK8ZR6JK2TPG=creating-conversion-actions-and-goals h_01HV6FR2TFYT11H9EVT9Y9TZ3S=note-2 google%20view-web-to-app=view-web-to-app-attribution-data-from-november-2-2025 view-webtoapp-attribution-data-from-november-2-2025=view-web-to-app-attribution-data-from-november-2-2025 h_01K88H6ETM23EV0PTR8GS13KRN=view-web-to-app-attribution-data-from-november-2-2025 h_01K88H6ETMG7007CJ0ADD8VQH4=view-in-the-dashboard h_01K88H6ETM502Z2XDC63602FGD=view-in-raw-data-and-api-reports h_01KB5085FX7G6Y5E200KVH0ABJ=traits-and-limitations" />
