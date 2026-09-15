---
title: "Google Ads Web—Integration for PC and console apps"
excerpt: "Learn how to set up Google Ads Web campaigns to promote your PC and console apps, configure partner integration in AppsFlyer, and track web-to-app attributions."
---
Use Google Ads web campaigns to promote your apps on PC and console platforms and enable attribution. AppsFlyer supports Google web-based campaigns using cross-platform landing pages or direct attribution links.

> 📘 Note
>
> This article focuses on web campaigns that promote PC or Console apps. If you want to create web campaigns that promote mobile apps, see [Google Ads (AdWords) - Create web-based campaigns](/docs/google-ads-adwords-create-web-based-campaigns).

## Overview

This article contains information and steps on how to set up and use Google Ads Web for PC and console apps with AppsFlyer. This includes:

- [Activate the partner integration in AppsFlyer](https://support.appsflyer.com/hc/articles/21768823915665#activate-partner).
- [Set up Google Ads Web in AppsFlyer](https://support.appsflyer.com/hc/articles/21768823915665#setting-up-Googleadsweb-in-appsflyer).
- [Set up campaigns in Google Ads for PC and console apps](https://support.appsflyer.com/hc/articles/21768823915665#setting-up-campaigns-in-meta-web-for-pc-and-console-apps).

### Prerequisites

Before activating the Google Ads Web integration, make sure you have:

- A PC or console app
- An AppsFlyer account
- A Google access token with the [required OAuth scope](https://developers.google.com/identity/protocols/oauth2/scopes). You can verify the scopes associated with your access token in the Google Developer Console.
- AppsFlyer [users with appropriate roles/permissions](https://support.appsflyer.com/hc/articles/4409128270481) and access to the relevant apps

## Activate partner in AppsFlyer

**To activate the partner integration:**

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Partner Marketplace**.
2. Search for **Google Ads Web** and select it.
3. Click **Set up integration**. You’re directed to the **Active Integrations** setup page.
4. In the **Integration** tab, turn on **Activate partner**.

> 📘 Note
>
> The toggle must stay on ([activated](https://support.appsflyer.com/hc/articles/360000844778)) for as long as you work with the partner.

5. Complete the configuration using the relevant tabs, as described in the next section.

## Set up Google Ads Web in AppsFlyer

In this part of the setup, you can also set up postbacks to Google Ads. The Google Ads Web (googleads_int) integration uses an API tool provided by Google Ads for advertisers to send data from their **PC and console apps** directly to Google's servers. Such data may include user actions, such as purchases, registrations, and other types of conversions performed on non-mobile platforms (websites or applications). The data is then used by Google Ads to optimize ad targeting, measure ad performance, and build custom audiences for retargeting.

The integration with Google Ads Web only supports sending postbacks for installs and in-app events.

### Integration tab

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

To configure the integration, you must first turn on the **Activate partner** toggle.

#### General settings

> 📘 Note
>
> The **Missing token** error message will stop appearing once you’ll sign in with Google and allow AppsFlyer to fetch the token in the step below. If the error persists after you sign in, [verify that your token has the required permissions](/docs/google-ads-adwords-create-web-based-campaigns#access-token-permissions).

1. **First open conversion ID**: Enter the ID of the `First open` conversion action you set in Google Ads. To find the ID:
   1. Go to the Google Ads platform and open the **Details tab** of the **First open** conversion action page.
   2. Copy the value of the `ctid=*` query parameter from the page URL. For example, if `ctid=123456789`, insert `123456789` to the **First open conversion action ID** box.
2. Enter your **Customer ID**. You can retrieve it from your Google Ads Manager:
   1. Sign in to your Google Ads account.
   2. In the top right corner, click the Google account icon and scroll down to where the Customer ID is displayed.
   3. If you have multiple Google Ads accounts running campaigns for your app, you must use the Customer ID from a manager (MCC) for cross-account conversion tracking. Paste the **MCC ID** (and not a specific account’s Customer ID) in the **Customer ID** text box and also in the **MCC Customer ID** text box (same ID in both boxes).

      If you only use a single Google Ads account to run ads, simply paste the account ID in the **Customer ID** text box and leave the **MCC Customer ID** text box empty. See [Google instructions on configuring an MCC account](https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC).
3. To allow AppsFlyer to upload conversions to Google Ads, click **Sign in with Google**.
4. In Google, select the admin account of the MCC account from which you retrieved the Customer ID above.
5. Click **Allow**.

#### Enable view-through attribution

AppsFlyer supports view-through attribution for Google Web campaigns using a [Smart Script](/docs/google-ads-adwords-create-web-based-campaigns#create-a-landing-page-with-onelink-smart-script) or [Smart Banner](/docs/google-ads-adwords-create-web-based-campaigns#create-a-landing-page-with-onelink-smart-banners)-enabled landing page. This allows probabilistic modeling (PMOD) attribution of app installs triggered by ad impressions, even when users don’t click the ad directly.

When a user sees a Google ad and lands on a [Smart Script](/docs/google-ads-adwords-create-web-based-campaigns#create-a-landing-page-with-onelink-smart-script) or [Smart Banner](/docs/google-ads-adwords-create-web-based-campaigns#set-up-a-smart-banners-landing-page)-enabled landing page, AppsFlyer can attribute the resulting app install, including cross-platform, back to the original web impression.

When available, AppsFlyer includes the `gclid` in the postback to Google.

**To enable view-through attribution:**

1. In AppsFlyer, from the sidebar, open **Active Integrations** > **Google Ads Web**.
2. In the **Integration** tab, scroll to the **Install attribution** section.
3. Turn on **Install view-through attribution**.
4. **[optional]** Turn on **Cross-platform equal attribution priority** and set its lookback window. For more information, see [Enable equal priority for cross-platform impressions](/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions).
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
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br> - Click **Add item**, enter the event name, and click check icon. |
| **mapped to partner event** | The Conversion Action ID of each event, as is defined on the partner's side. <br> 1. In Google Ads **Conversion Goals** page, click the conversion action you created.<br> 2. In the Conversion Action **Details** page, copy the **Conversion Action ID** from the URL parameter `ctId=`.<br> 3. Go back to AppsFlyer and paste it. For example if `ctid=123456789`, paste `123456789`. |
| **for users from** | **This partner only:** In-app event postbacks are sent only for events attributed to this partner—meaning, the user who performed it came from this partner. |
| **including** | **Values and revenue:** All event parameters, including the revenue value (if exists in the event), are sent in the postback. |

3. [Optional] Click the **Add condition** icon to [set conditions](https://support.appsflyer.com/hc/articles/208439256#conditional-inapp-event-postbacks) for an event.
4. Set the **In-app event postback window**, if required (read more about [in-app event postback window configuration](https://support.appsflyer.com/hc/articles/208439256-In-App-Events-Postback-Configuration#inapp-event-postback-window)).
5. Click **Save integration**.
6. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the integration steps for the selected app.

### Attribution link tab

Generating an attribution link in the AppsFlyer UI isn't currently available. However, you can either use a cross-platform landing page with SmartScript or create a direct attribution link for your app (see table below).

| Option | Actions | Who's involved |
| --- | --- | --- |
| Cross-platform landing page | **Recommended**: For when your campaign promotes an app that's also available on multiple platforms, like Epic and Steam.<br>[Learn about cross-platform landing pages](https://support.appsflyer.com/hc/articles/4404083608849-Connected-TV-CTV-PC-and-console-platform-attribution-overview#landing-page)<br>[Learn how to set up a cross-platform landing page](https://support.appsflyer.com/hc/articles/18440789126289)<br>- Make sure all relevant URL parameters (that are later captured by the Smart Script) are appended to the ad URL<br>- Make sure the script takes the GCLID from the incoming URL and adds it to the generated link. Meaning, map the outgoing GCLID URL param `gclid` to the incoming URL param `gclid`. **Note**! To display in AppsFlyer raw data reports, the incoming `gclid` param must also mapped to one of the outgoing params `af_sub[1-5]`. | Marketer (may require developer assistance) |
| Direct attribution link | If you don't use a cross-platform landing page, because you only have 1 app on 1 platform, you can create direct attribution links to place behind ads.<br>[Learn how to create direct attribution links](https://support.appsflyer.com/hc/articles/15199908310801)<br>- Make sure the following parameters are included in your link:<br> - af\_media\_source<br> - af\_campaign\_id<br> - af\_r<br><br>**Note**: The [Google click identifier (GCLID)](https://support.google.com/google-ads/answer/9744275?hl=en) parameter is automatically added by Google Ads to any outgoing click if you are using [auto-tagging](https://support.google.com/google-ads/answer/3095550?hl=en). If auto-tagging is deactivated in your Google Ads account, add `gclid={gclid}` to the Google Ads tracking template URL.<br>- For af\_camapign\_id, af\_adset\_id and af\_ad\_id parameters, you can use Google’s [value track parameters](https://support.google.com/google-ads/answer/6305348) (dynamic URL parameter) macros. All other parameters should be set manually.<br>- Don't include the af\_dp parameter.<br>**Template to use for most platforms (Epic, Steam, Xbox, PlayStation, etc.)**:<br>`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br>**Sample link leading to Steam**: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br>**Template to use for Google PC and Mac apps ONLY**:<br>`https://app.appsflyer.com/{app_id}?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br>**Sample link leading to Google PC**: `https://app.appsflyer.com/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}` | Marketer |

> 👍 Tip
>
> To simplify campaign analysis, include the campaign type, web or mobile, as a prefix or suffix in the campaign name (e.g., campaign-name_web)

## Set up campaigns in Google Ads Web for PC and console apps

When you set up a new campaign, you can either direct users to a:

- Cross-platform landing page: Recommended for when your campaign promotes an app that's also available on multiple platforms, like Epic and Steam.
- Single store: This uses a direct attribution link and should be used when you only have 1 app on 1 platform.

The instructions for setting up campaigns to redirect users to either of these options are detailed in the sections that follow.

**Note**: During campaign setup, you may want to configure your own conversion actions and goals. Instructions on how to do this are also detailed in the sections that follow.

### Campaigns that redirect to a cross-platform landing page

**To set up a campaign that redirects users to a cross-platform landing page**:

1. Set up a cross-platform landing page as described in the [attribution link section](https://support.appsflyer.com/hc/articles/21768823915665#attribution-link-tab).
2. Log in to Google Ads and create a new campaign.
3. Select the campaign objective.
   - All objectives are applicable, except "App promotion" (which can only be used for mobile app campaigns).
   - We recommend setting the "Sales" campaign objective for optimization based on specific in-app events.
4. Select the conversion goals.
   - By default, you see the predefined account-level campaign goals. You can keep those, or remove ones that aren't relevant for your campaign.
   - If you don’t see the goal you want, [add the conversion action and conversion goal](https://support.appsflyer.com/hc/articles/21768823915665#creating-conversion-actions-and-goals).
   - You can also edit your predefined goals in the Conversions page.
5. Select the campaign type.
   - All campaign types are applicable, except "Shopping" which requires a product catalog and is limited to verified domains.
6. Enter the cross-platform landing page URL as Google's final URL.

### Campaigns that redirect to a single app store

**To set up a campaign that redirects users to a single platform and app store**:

1. Set up a direct attribution link as described in the [attribution link section](https://support.appsflyer.com/hc/articles/21768823915665#attribution-link-tab).
2. Log in to Google Ads and create a new campaign.
3. Select the campaign objective.
   - All objectives are applicable, except "App promotion" (which can only be used for mobile app campaigns).
   - We recommend setting the "Sales" campaign objective for optimization based on specific in-app events.
4. Select the conversion goals.
   - By default, you see the predefined account-level campaign goals. You can keep those, or remove ones that aren't relevant for your campaign.
   - If you don’t see the goal you want, [add the conversion action and conversion goal](https://support.appsflyer.com/hc/articles/21768823915665#creating-conversion-actions-and-goals).
   - You can also edit your predefined goals in the Conversions page.
5. Select the campaign type.
   - All campaign types are applicable, except "Shopping" which requires a product catalog and is limited to verified domains.
6. Enter the link to be used as Google's final URL.
   - This must be the final web location you want to redirect your users to. It can be any web URL including a web landing page or store URL. For example: `https://store.steampowered.com/app/{appid}/{myapp}/`.
   - The final URL can't be an AppsFlyer URL, as this may cause your campaign to be rejected. Only use a direct web address that has no redirects.
7. Enter your AppsFlyer direct attribution link as Google's Tracking Template URL.
   - For parallel tracking to function as intended, the final URL must be placed in the {lpurl} ValueTrack parameter in Google’s Tracking Template URL as specified by Google.
   - Don't include the af_dp parameter.

### Create conversion actions and goals

In Google Ads, you can either select from the predefined list of conversion actions and goals or create your own.

> ❗️ Important
>
> For AppsFlyer to send a "First Open" event postback, you need to create a conversion action and name it "First Open".

**To create your own Google Ads conversion actions and goals**:

1. In your Google Ads account overview page, from the side menu, select **Goals** > **Conversions** > **Summary**.
2. Click **+ New conversion action**.
3. Select **Conversions offline** as your conversion actions data source.
4. Select **Import** from the list of conversion types, then select **Manual import using API or uploads** > **Track conversions from clicks**.

   > 📘 Note
   >
   > If **Manual import using API or uploads** is not available:
   >
   > 1. Select **CRM, files, or other data sources** > **Track conversions from clicks.**
   > 2. In **Data source** select **Skip this step and set up data source later.**

5. Click **Continue**.
   A form displays.
6. Fill out the form and click **Create and continue** to finish creating your conversion tracker.
7. For **Goal and action optimization**, select a category to map your conversion action into.

   > 📘 Note
   >
   > Google ads campaign optimization is per category; not per specific action). If you only want your campaigns to optimize to a single action, make sure to map only that action to this category. For example, if you want your campaign to optimize towards the "install" action, make sure to map the "install" action to its own category, for example, “Other.” You’ll then be able to select this category as the campaign goal when creating the campaign.

8. Copy the conversion action ID from Google Ads and enter it in the **mapped to partner event** field. The **Conversion Action ID** is used as the partner event ID when mapping the AppsFlyer event name to the partner event ID in the in-app event postbacks setup. To copy the conversion action ID from Google Ads perform the following:
   1. In Google Ads **Conversion Goals** page, click the conversion action you created.
   2. In the Conversion Action **Details** page, copy the **Conversion Action ID** from the URL parameter `ctId=` and paste it.
9. Click **Create and continue**.
10. Click **Finish**.

## View web-to-app attribution data (from November 2, 2025)

Although web-based conversion events are sent to Google under the original `googleads_int` PID, they are reported in the AppsFlyer dashboard and raw data reports under the `googleadwords_int` PID. This applies both to primary conversion events and to conversion assist events.

This unified reporting view lets you analyze both web and app campaign performance in one place, including full mobile and web cost reporting.

### View in the dashboard

All Google web-to-app attributions appear under `googleadwords_int` in the Overview and Activity dashboards. This provides a single, consolidated view of campaign results across platforms. Use standard filters and breakdowns to compare app and web traffic within your Google Ads data.

### View in raw data and API reports

- **Raw data exports and API responses** include the `googleadwords_int` PID in the `media_source` field for Google web activity. To verify web campaign setup details, refer to the `original_url` field that shows `googleads_int` as the PID used during the creation of web campaigns.
- **Postback reports** show `googleads_int` as the original media source to which the postback was sent.

## Traits and limitations

| Trait | Description |
| --- | --- |
| Clicks and impressions (Temporary limitation) | Clicks and impressions for campaigns targeting PC & Console apps are temporarily not available from Google SRN (`googleadwords_int`). |