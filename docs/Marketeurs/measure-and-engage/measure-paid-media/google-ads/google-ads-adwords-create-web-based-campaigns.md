---
title: Google Ads (AdWords)—Create web-based campaigns for mobile apps
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-05-16T09:12:15Z'
  edited_at: '2026-10-12T09:30:39Z'
  id: 25096718837137
  locale: en-us
  section: Google Ads
  section_id: 6551205645457
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/25096718837137-Google-Ads-AdWords-Create-web-based-campaigns-for-mobile-apps
---
> **At a glance:** Create web campaigns to attribute web-to-app conversions from Google Ads

> 📘 **Note**
>
> This article focuses on web campaigns that promote mobile apps. If you want to create campaigns that promote PC or Console apps, see Google Ads Web—Integration for PC and console apps.

## Overview

AppsFlyer supports integration with Google Ads (`googleads_int`) for web-based campaigns and reports the campaigns' attribution and conversion data through the Google Offline Conversion API (OCI).

In this article, you'll learn how to set up mobile web campaigns in AppsFlyer and Google Ads, targeting Web users who interact with Google ads.

The campaigns are based on a user journey that starts when a user clicks on an ad and is redirected to a landing page. This page includes AppsFlyer Smart Script or Smart Banners, which create attribution links.

Once clicked, these links take the user to the app store to download and install the app. The install and subsequent in-app events are recorded in AppsFlyer and reported to Google Ads via OCI.

Google uses this data to optimize ad targeting, measure performance, and build custom audiences.

### Prerequisite

Before activating the Google Ads integration for web campaigns, make sure you have the following:

* A mobile app
* An AppsFlyer account
* AppsFlyer <Anchor target="_blank" href="/marketers/fr/docs/user-management">users with appropriate roles or permissions</Anchor> and access to the relevant apps

### Create a Google Ads web campaign

This article contains information and steps to set up a web campaign in Google Ads for Mobile, PC, and console apps with AppsFlyer. The setup involves defining the integration between Google Ads and AppsFlyer and setting the campaign attribution links.

* [Set up Google Ads integration in AppsFlyer](#create-a-google-ads-integration-in-appsflyer) (Required)
* [Set up Google Ads integration in Google Ads](#create-a-web-campaign-in-google-ads) (Required)

After setting up the attribution links in step one through the Google Ads and AppsFlyer integration, step two focuses on creating the landing page. Here, OneLink Smart Script or Smart Banners will use the attribution links to generate call-to-action buttons, directing users to the app stores.

* [Create a landing page with OneLink Smart Script](#create-a-landing-page-with-onelink-smart-script) (Optional)
* [Create a landing page with OneLink Smart Banners](#create-a-landing-page-with-onelink-smart-banners) (Optional)

## Create a Google Ads integration in AppsFlyer

Start by activating the integration with Google Ads for web campaigns and setting the postbacks that AppsFlyer sends to the OCI.

<Accordion title="1. Activate the Google Ads for web campaigns integration">

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Partner Marketplace**.
2. Search for **Google Ads Web** and select it.
3. Click **Set up integration**. You’re directed to the **Active Integrations** setup page.
4. In the **Integration** tab, turn on **Activate Partner**. **Note:** The toggle must stay on (<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">activated</Anchor>) for as long as you work with your partner.
5. Turn off **Advanced Privacy** (if you are setting an iOS app integration).

> 📘 **Note**
>
> The **Missing token** error message will stop appearing once you sign in with Google and allow AppsFlyer to fetch the token in the step below. If the error persists after you sign in, verify that your token has the required permissions.

1. In **First open conversion ID**, enter the ID of the `First open` conversion action you set in Google Ads. To find the ID, go to Google Ads and open the **Details tab** of the **First open** conversion action page. Then, copy the value of the `ctid=*` query parameter from the page URL. For example, if `ctid=123456789`, insert `123456789` to the **First open conversion action ID** box.

   <Image align="center" alt="" src="https://files.readme.io/bbd7178f688b1844b925ca6f2ec5768a00b548f3ccba5928966278918966c501-26324098042513.png" />

> 👍 **Tip**
>
> If you still need to set the 'First open' action in Google Ads, you can enter a placeholder value temporarily until the action is fully set up.

1. Enter your **Customer ID**. You can retrieve it from your Google Ads Manager:
   1. <span class="af-ol-a"></span>Sign in to your Google Ads account.
   2. In the top right corner, click the Google account icon and scroll down to where the Customer ID is displayed.
2. If you have multiple Google Ads accounts running campaigns for your app, you must use the Customer ID from a manager (MCC) for cross-account conversion tracking. Paste the **MCC ID** (and not a specific account’s Customer ID) in the **Customer ID** text box and also in the **MCC Customer ID** text box (same ID in both boxes).   
   If you only use a single Google Ads account to run ads, simply paste the account ID in the **Customer ID** text box and leave the **MCC Customer ID** text box empty. See <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">Google instructions on configuring an MCC account</Anchor>.
3. Click **Allow**.

</Accordion>

<Accordion title="2. Enable view-through attribution">

AppsFlyer supports view-through attribution for Google Web campaigns using a [Smart Script](#set-up-a-smart-script-crossplatform-landing-page) or [Smart Banner](#set-up-a-smart-banners-landing-page)-enabled landing page. This allows probabilistic modeling (PMOD) attribution of app installs triggered by ad impressions, even when users don’t click the ad directly.

When a user sees a Google ad and lands on a [Smart Script](#set-up-a-smart-script-crossplatform-landing-page) or [Smart Banner](#set-up-a-smart-banners-landing-page)-enabled landing page, AppsFlyer can attribute the resulting app install, including cross-platform, back to the original web impression.

When available, AppsFlyer includes the `gclid` in the postback to Google.

**To enable view-through attribution:**

1. In AppsFlyer, from the sidebar, open **Collaborate** > **Partner Integrations > Active Integrations** > **Google Ads Web**
2. In the **Integration** tab, scroll to the **Install attribution** section.
3. Turn on **Install view-through attribution**.
4. **[optional]** Turn on **Cross-platform equal attribution priority** and set its lookback window. For more information, see <Anchor target="_blank" href="/marketers/fr/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Enable equal priority for cross-platform impressions</Anchor>.
5. Open the **Attribution** tab.
6. Scroll to the **View-through attribution** section and set the preferred **view-through lookback window** (up to 24 hours).
7. Click **Save integration** to apply the changes.

</Accordion>

<Accordion title="3. Turn on Advanced Matching data sharing">

Advanced Matching data sharing is controlled per partner and per app, and must be turned on separately for Google Ads Web.

When turned on, hashed identifiers, such as a hashed email address or hashed phone number, are shared with Google OCI if these fields are included in the event data you send. For more information, see <Anchor target="_blank" href="/marketers/fr/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor>.

To turn on Advanced Matching data sharing:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Partner Integrations** > **Active Integrations**.
2. Search for **Google Ads Web** and select it.
3. In the **Integration** tab, turn on **Advanced Matching Data Sharing**.
4. Click **Save integration**.

</Accordion>

<Accordion title="4. Set in-app event postbacks">

Installs are currently the only events that trigger automatic default postbacks to Google Ads for Web via the OCI API. For other event types, you can create custom postbacks by mapping AppsFlyer events to Google Ads conversion action IDs (“Conversion action” is the term Google Ads uses for attribution events.) Consult Google Ads Manager to learn about the Google Ads Web event you need to map to AppsFlyer events.

1. Turn on **In-app event postbacks**.
2. If required, set the In-app event postback window (read more about in-app event postback window configuration in general in <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#in-app-event-postback-window">this article</Anchor>).
3. Click **Add event** to add an SDK or server-to-server event to the list.
4. In the **AppsFlyer event** column, select the event name from the drop-down box. AppsFlyer receives the event's name from the SDK integrated into your app or server-to-server events.
5. In the **mapped to partner event** column, you must map the AppsFlyer event to a corresponding Google conversion action ID. Before you can do that, you need to set up the required Google conversion actions in Google Ads. To learn how to set conversion actions in Google Ads, see [create custom conversion actions.](#h_01J1MPPMW4KMSXAR903P534X65)

   **To find the conversion action ID in Google Ads:**

   1. <span class="af-ol-a"></span>Go to Google Ads.
   2. Open the page of the conversion action you want to map.
   3. Open the **Details** tab.
   4. From the page URL, copy the value of the `ctid=*` query parameter.
   5. Go back to AppsFlyer.
   6. Paste it into the **mapped to partner event** column. For example, if `ctid=123456789`, paste `123456789`.
6. In the **For Users From** column, select **This Partner Only** or **All media sources, including organic**. **Note:** unattributed events will be sent only if <Anchor target="_blank" href="/marketers/fr/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor> is turned ON and they include a hashed email or phone number.
7. In the **including** column, select whether all event parameters, including the revenue value (if it exists in the event), are sent in the postback.
8. [Optional] Click the **Add condition** icon to <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event.
9. Click **Save integration**.
10. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
    1. <span class="af-ol-a"></span>From the top-left corner, click the app name under the partner name to open the list of apps.
    2. Select a different app from the drop-down list.
    3. Repeat the integration steps for the selected app.

</Accordion>

<Accordion title="5. Configure the OneLink template">

Before creating a OneLink attribution link for your Google Ads campaign, you need to set its template. Then, you can create a OneLink attribution URL based on the template and use it as the Google Tracking template URL.

> 📘 **Note**
>
> The instructions below focus on creating a OneLink template for Google web campaigns with Smart Script. For a comprehensive guide on how to set up OneLink templates, see the How to create OneLink templates section of the OneLink templates article.

1. Under the **Redirection** section of the **New template** or **Edit template** page, configure the following settings:
   * **When app isn’t installed** > **Redirect to**: Select your preferred option. The redirection value you set here is overridden by the `{lpurl}` value of the redirection parameters ( <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#af_android_url">`af_android_url`</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#af_ios_url">`af_ios_url`</Anchor> ) you place in the Google Tracking Template; see [Set the Tracking Template URL](#set-the-tracking-template-url).
   * **When app is installed**: Make sure **not** to set up Universal Links, URI scheme, or All Links for launching the app because Google does not allow any redirection apart from the redirection to the Final URL.
   * **When link is clicked on desktop web page** > **Redirect to**: Select your preferred option. The redirection value you set here is overridden by the `{lpurl}` value of the redirection parameters (<Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#af_web_dp">`af_web_dp`</Anchor>) you place in the Google Tracking Template, see [Set the Tracking Template URL](#set-the-tracking-template-url).
2. Click **Create template**.

</Accordion>

## Create a web campaign in Google Ads

Perform the following steps in Google Ads.

<Accordion title="1. Set the campaign type, objective, and goals">

Google Ads uses the campaign type objective and goals you select here to set the right bidding strategy and optimize campaign performance.

1. Log in to Google Ads and create a campaign.
2. Select the campaign objective.

   <Image align="center" alt="" src="https://files.readme.io/90063f7fe5a363ed498271148c4165969cc63c708a73ab25363d2263a79b0828-26324053661201.png" />
   * All objectives are applicable, except "App promotion" (which can only be used for mobile app campaigns).
   * We recommend setting the "Sales" campaign objective for optimization based on specific in-app events.
3. Select the conversion goals.

   <Image align="center" alt="" src="https://files.readme.io/5ca0a0425af24d5926dc0a7a3529632e22bd140423e87c026ff1527e7a0341b3-26324096257169.png" />
   * By default, you see the predefined account-level campaign goals. You can keep those or remove ones that aren't relevant to your campaign.
   * If you don’t see the goal you want Google to optimize for,

     <Anchor target="_blank" href="/marketers/fr/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals">create a custom conversion action and goal</Anchor>.
   * You can also edit your predefined goals on the Conversions page.
4. Select the campaign type.

   <Image align="center" alt="" src="https://files.readme.io/14daea1c1edf92854e21d0a4c5d34372a4e062d68a4613967bb4f40d0d1e720f-26324053659281.png" />
   * All campaign types are applicable, except "Shopping," which requires a product catalog and is limited to verified domains.

</Accordion>

<Accordion title="2. Create custom conversion actions">

Next, for each [in-app event you set in AppsFlyer](#h_01J1MPPMW34GG0EPDWYXA7383C), you must create a corresponding conversion action in Google Ads. After you complete creating the conversion action, you will need to copy the ID of the newly created action and map it to the AppsFlyer in-app event.

To create custom Google Ads conversion actions and goals:

1. In your Google Ads account overview page, from the side menu, select **Goals > Conversions > Summary**.
2. Click **+ New conversion action**.
3. Select **Conversions offline** as your conversion actions data source.
4. Select **Import** from the list of conversion types, then select either:

   * **Manual import using API or uploads > Track conversions from clicks**.

   OR

   * **CRM, files, or other data sources > Track conversions from clicks,** and under **Data source,** select **Skip this step and set up data source later**.
5. Click **Continue**.
6. In **Conversion goal**, select a conversion action category.
7. In **Enter a conversion name**, type the name of the conversion action.

> ❗️ **Warning**
>
> To use the Offline Conversions API with GBRAID/WBRAID (in addition to GCLID), make sure the **Count** field in the conversion action is set to **Every** (default) and NOT **One.**

1. Enter a **Conversion name** and then click **Add**. **Note**: If you only want your campaigns to optimize to a single action, include only that action in this category. For example, if you want your campaign to optimize towards the **First open** conversion action, make sure that it is the only one in its category. You’ll then be able to select this category as the conversion goal for performance optimization when creating the campaign.
2. Click **Save and continue,** and then **Done** without setting up data sources. Your new conversion action may initially appear as “Inactive”, but it will change to “Active” once actual data is sent.
3. To map the new Conversion action to the AppsFlyer postback event, retrieve the new conversion action ID. In the conversion goals **Summary page,** click the conversion action you created and copy the value of the `ctid=*` query parameter from the conversion action page URL.

   <Image align="center" alt="" src="https://files.readme.io/0bbe655051204d8902b82f2f8d8b12f183ef40f9e84c542972db767707d75a9d-26324053660177.png" />
4. In AppsFlyer, paste the `ctid` value in the **mapped to partner event** column of the postback event you want Google to optimize for; see: [Set in-app event postbacks](#h_01J1MPPMW34GG0EPDWYXA7383C).

</Accordion>

<Accordion title="3. Set the campaign URLs">

Google Web Ads campaigns use two URLs for each engagement: the Final URL and the Tracking Template URL. These URLs are activated simultaneously when the ad is clicked, a feature Google refers to as Parallel Tracking. More information on Parallel Tracking is available in <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">the Google documentation</Anchor>.

#### Set the Final URL

Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">defines the Final URL</Anchor> as "the URL address of the webpage in your website that people reach after they click your ad. Also known as the 'landing page.'"

**To set the Final URL**

1. In Google Ads, open the **Campaigns** > **ads** page.
2. In the ad row, click the edit icon.

   <Image align="center" alt="" src="https://files.readme.io/e6b834a0e105324c5b9e4105a5ce7e1f47fa7c00fcf2aee29b6b0e96763150f1-26324098055057.png" />
3. In **Final URL,** enter the URL of the web landing page.

> ❗️ **Warning**
>
> The Final URL can't be an AppsFlyer URL (OneLink or a single platform attribution URL), as this may cause your campaign to be rejected. Only use a direct web address with no redirects, such as a web page URL, the Google Play store URL, or the App Store URL.

1. This must be the final web location to which you want to redirect your users. It can be either:
   * **A landing page URL** pointing to a page that prompts the user to click a CTA button to download the app from Google Play, App Store, or any other app store. The landing page includes Smart Script or Smart Banners, which automatically generate the CTA button URLs. To learn [how to create the landing page with Smart Script](#create-a-landing-page-with-onelink-smart-script) or [Smart Banners](#create-a-landing-page-with-onelink-smart-banners).

     You can add AF attribution parameters to the Final URL and map them to Google ValueTrack parameters, for example, `af_c_id={campaignid}`. Once the Google ad is clicked and the landing page is loaded, Smart Script or Smart Banners can copy the parameters to the landing page's outgoing URL. To learn about the available ValueTrack parameters, see the [Google documentation](https://support.google.com/google-ads/answer/6305348?sjid=9660882197247124000-EU#zippy=%2Cfinal-url-tracking-template-or-custom-parameter).

     For example,

     ```
     https://example.com?product=1234&af_c_id={campaignid}
     ```
   * **A store URL** such as the App Store or Google Play.

> ❗️ **Warning**
>
> Suppose you use the store URL as your Final URL. The only way to send attribution and custom parameter information to AppsFlyer is to insert and map AF parameters to the Tracking Template URL.

*
  ```
  https://play.google.com/store/apps/details?id=.com.app.id&hl=en&gl=US&referrer={gclid}&gclid={gclid}&campaignid={campaignid}
  ```
* **A direct download link to the app APK file** if you want users to download the app directly without being redirected to a store.

#### Set the Tracking Template URL

Because Google Ads, by default, uses Parallel Tracking, the Tracking Template URL (an AppsFlyer attribution link in this case) is loaded in the background, and the click is registered at AppsFlyer. It is not mandatory to use tracking template URLs, especially when using Smart Banners or Smart Script, see [Using the Tracking Template URL with Smart Script or Smart Banners](#using-the-tracking-template-url-with-smart-script-or-smart-banners) in this article.

1. In Google Ads, open the **Campaigns** > **Campaigns** page. In the campaign row, click the settings icon

   <Image align="center" alt="" src="https://files.readme.io/ec6503cfb3ff185448f13897240e0eadd7f10fc3678ffa85b4d52d2393b01ca4-26324098054033.png" />
2. Expand the **Settings** > **Additional Settings** > **Campaign URL options**

   <Image align="center" alt="" src="https://files.readme.io/4959b4129749ff282ee3818c3b5724ac2ed3b1d033d06f8557329cafa812720f-26324053658641.png" />
3. In **Tracking template,** use the following (BaseURL + Redirection parameters):
   * **Base URL**: Set the Base URL according to the ad click destination:
     * **Single platform attribution link** if the ad click destination is either Google Play or the App Store (see example below).
     * **A OneLink attribution link** if the ad click destination is a Web page (see example below).

> ❗️ **Warning**
>
> If your Final URL points directly to the Google Play store or the App Store (the user platform is known), use a single-platform attribution link in the Tracking Template URL. Using a OneLink URL in this scenario results in a "Tracking call unsuccessful" error from Google.

* **The PID parameter:** Add the mandatory <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#pid">`pid`</Anchor>`=googleads_int` parameter.

> 👍 **Tip**
>
> To simplify campaign analysis, include the campaign type, web or mobile, as a prefix or suffix in the campaign name, for example, campaign-name\_web

* **The site ID  parameter:** Add the mandatory <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> parameter. You can manually assign any value to it.
* **The campaign name parameter:** Add the mandatory <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#c">c</Anchor> parameter and manually assign its value (There is no ValueTrack parameter for this parameter).
* **The force transparent parameter**: Add the mandatory `af_force_transparent=true` parameter. This parameter is designed to enhance security in redirection behavior and make sure your setup complies with Google’s requirements. Please note that if you do not add the required parameter, Google may disapprove your ad.
* **Redirection parameters for a OneLink attribution link:** For parallel tracking to function as intended, set the AF redirection parameters in one of the following combinations:
  * The parameters `af_android_url`, `af_ios_url`, and `af_web_dp` must be set to the `{lpurl}` Google ValueTrack parameter. **Important:** Make sure all three are populated to guarantee the attribution link works in all scenarios.  
    **Or**
  * The `af_r` parameter must be set to the `{lpurl}` Google ValueTrack parameter.
* **Redirection parameter for a single platform attribution link:** For parallel tracking to function as intended, set the `af_r` parameter to the `{lpurl}` Google ValueTrack parameter.

> ❗️ **Warning**
>
> To comply with Google requirements, make sure that the \{lpurl\} value is a valid redirect URL:
>
> * It uses the HTTPS protocol.
> * It must be encoded.
> * The URL domain is included in your redirect allowlist.

* **AppsFlyer attribution parameters mapped to Google ValueTrack parameters**, for example, <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor>`={campaignid}`. To learn about the available ValueTrack parameters, see the [Google documentation](https://support.google.com/google-ads/answer/6305348?sjid=9660882197247124000-EU#zippy=%2Cfinal-url-tracking-template-or-custom-parameter).
* Don't include any of the following parameters. Requests that contain these parameters are not supported in the Parallel Tracking flow and will be rejected:
  * `af_dp`
  * `af_android_store_csl`
  * `af_ios_store_cpp`
  * `af_og_title`
  * `af_og_description`
  * `af_og_image`
* Don’t include any parameters that alter the value of the redirection parameter \{lpurl\}. This includes `af_base_params_forward` and `af_param_forwarding`.

> 📘 **Note**
>
> For additional limitations relating to the tracking template URL, see the Traits and limitations section in this document

#### Google Tracking Template URL examples

An example of **a** **OneLink** in a Google Tracking Template URL:

```
https://subdomain.onelink.me/aAB1?pid=googleads_int&af_force_transparent=true&af_android_url={lpurl}&af_ios_url={lpurl}&af_web_dp={lpurl}&c=summer_sale24&af_siteid=123456&af_c_id={campaignid}&af_adset=sum24A&af_adset_id={adgroupid}&af_sub1={gclid}&af_sub2={gbraid}
```

An example of **a single platform link** in a Google Tracking Template URL:

```
https://app.appsflyer.com/id1510557250?pid=googleads_int&af_force_transparent=true&c=examplecamp&af_siteid=123456&af_adset=exampleadset&af_adset_id={adgroupid}&af_c_id={campaignid}&af_ad_id={creative}&af_click_lookback=7d&af_r={lpurl}
```

#### Using the Tracking Template URL with Smart Script or Smart Banners

You don't need to populate the Tracking Template URL with an AppsFlyer attribution link when the ad redirects to a landing page that uses a Smart Script or Smart Banners. This is because these tools automatically create an attribution link that gets registered in AppsFlyer when the user clicks the landing page CTA button. However, there are considerations for and against leaving the Tracking Template URL field empty:

* If you **don’t populate** the Tracking Template URL with an attribution link, you run the risk of missing installs that occur when the user clicks the ad but does not click any of the landing page CTA buttons. If the user goes directly to the app store to download the app within the lookback window, the subsequent install will not be attributable.
* If you **populate** the Tracking Template URL with an attribution link and the user clicks the ad and subsequently clicks the landing-page CTA buttons, two clicks will be registered instead of one, which may impact conversion-rate data.

</Accordion>

## Create a landing page with OneLink Smart Script

**User journey:** The user clicks on a Google ad and is directed to your mobile website. They land on a page with CTA buttons urging them to download your app. Clicking the button will redirect the user to the store.

<Accordion title="End-to-end data flow">

The W2A Smart Script use case is comprised of the following phases:

<Image align="center" alt="" src="https://files.readme.io/719733ce8f5c4f0c5e2bae8a801bd10fed7223e25ddb797f35fa37f98bd978df-26324098052113.png" />

1. The user clicks on a Google ad, Google automatically appends to the Final URL the following:
   * a `gclid` parameter for Android devices and for consenting users on iOS devices.
   * a `gbraid` and `wbraid` for iOS device non-consenting users.
   * all the query parameters set in the ad Google Tracking Template URL, except the redirection parameters.
2. The Final URL redirects the user to the landing page.
3. Simultaneously, the ad Google Tracking Template URL which also contains the auto-appended `gclid`, `gbraid`, `wbraid`, and the `pid=googleads_int` parameters, is fired in the background, and the click is registered with AppsFlyer.
4. When the landing page loads, the Smart Script fires an impression event to AppsFlyer, which includes the incoming URL parameters. This impression enables view-through attribution for the landing page. To learn about impressions and view-through attribution, see <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">Create a custom impression URL</Anchor>.
5. Smart Script generates the outgoing URLs for the CTA buttons on the page based on the incoming URL parameters, including the `gclid`, `gbraid`, and `wbraid` parameters. The buttons can lead to:
   * Google Play and App Store via a OneLink attribution link.
   * Multiple platform stores (for example, CTV, Epic and Steam). In this use case, Smart Script generates an outgoing single platform attribution link for each platform, leading to the specified platform’s store.
   * Downloading an APK file to the user’s device.
6. When the user clicks the CTA button, the click is fired and registered in AppsFlyer.
7. The user is redirected to the store and downloads the app.
8. The install event is registered in AppsFlyer when the user opens the app.
9. AppsFlyer attributes the install based on probabilistic modeling or deterministically if an [install referrer](https://www.appsflyer.com/glossary/install-referrer/) is available.
10. A postback containing the `gclid` or the `gbraid` and `wbraid` and additional event parameters is generated and sent to Google Ads via the OCI API. Google Ads uses the `gclid` or `gbraid` and `wbraid` parameter to identify the specific click, while the other parameters help optimize the campaign.

</Accordion>

<Accordion title="Set up a Smart Script landing page">

To set up your Smart Script for Google web campaigns, perform the following steps:

1. Create a smart script.

> 📘 **Note**
>
> The instructions below focus on the steps needed to set up a Google web campaign with Smart Script. For a comprehensive guide on how to set up Smart Script campaigns, you can see the How to create a OneLink Smart Script section of the OneLink Smart Script V2 setup article.

1. Make sure all relevant URL parameters (that are later captured by the Smart Script) are appended to the incoming URL. To review the parameters appended to the incoming URL, open Google Ads and check the URL parameters set as part of creating the Final URL or Tracking Template URL; see: [Set the campaign URLs](#h_01J1MPPMW44NGXN55SFD16Z4HE).
2. Map the incoming URL parameters required for the campaign to the outgoing URL parameters that will be sent to AppsFlyer when the user clicks the CTA button:
   * **PID**: Make sure that Smart Script takes the `pid=googleads_int` parameter value from the incoming URL and maps it to the corresponding parameters in the outgoing URL.
   * **GCLID**: The `gclid` parameter is essential for successfully sending in-app events postbacks to Google Ads. The outgoing  URL GCLID  parameter mapping depends on your Smart Script version:
     * Version 2.8.1 and above: The `gclid` parameter is forwarded automatically to the outgoing URL parameter when present in the incoming URL, eliminating the need for manual mapping.
     * Version 2.8.0 and below: The `gclid` parameter must be mapped manually in the **URL parameter mapping** section of the **Smart Script** page:
       1. In **Mapping for**, select **Custom parameter**.
       2. In **Outgoing URL parameter** and **Incoming URL parameters** enter **gclid**.
   * **GBRAID** and **WBRAID**: The `gbraid` and `wbraid` parameters are essential for successfully sending in-app event postbacks to Google Ads for non-consenting iOS device users. The mapping of the `gbraid` and `wbraid` parameters in the outgoing URL depends on your Smart Script version:
     * Version 2.9.0 and above: The `wbraid` and `gbraid` parameters are forwarded automatically to the outgoing URL parameter when present in the incoming URL, eliminating the need for manual mapping.
     * Version 2.8.1 and below: The `wbraid` and `gbraid` parameters must be mapped manually in the **URL parameter mapping** section of the **Smart Script** page:
       1. In **Mapping for**, select **Custom parameter**.
       2. In **Outgoing URL parameter** and **Incoming URL parameters** enter **wbraid**.
       3. Repeat the above steps for the `wbraid` parameter.

> 📘 **Note**
>
> To display in AppsFlyer raw data reports, the incoming gclid, gbraid, and wbraid, parameters must each be mapped to a dedicated outgoing af\_sub[1-5] parameter (in addition to the outgoing URL gclid , gbraid, and wbraidparameters).

</Accordion>

<Accordion title="Set up a Smart Script cross-platform landing page">

For non-cross-platform landing pages, the marketer is typically responsible for auto-generating the Smart Script via the AppsFlyer Smart Script page. However, when it comes to cross-platform landing pages, the developer creates the script based on the parameters sent by the marketer.

To set up your Smart Script for Google web campaigns, perform the following steps:

1. Enable your OneLink template for cross-platform attribution; see <Anchor target="_blank" href="/marketers/fr/docs/set-up-cross-platform-links-for-multi-device-campaigns#create-a-onelink-templatefor-cross-platform-attribution">Create or edit a OneLink template for cross-platform attribution</Anchor>.
2. Make sure all relevant URL parameters are appended to the incoming URL. To review the parameters appended to the incoming URL, open Google Ads and check the URL parameters set as part of creating the Final URL or Tracking Template URL; see: [Set the campaign URLs](#h_01J1MPPMW44NGXN55SFD16Z4HE).
3. Decide for each incoming parameter the outgoing parameter to which it will be mapped. For example, `af_site_id` in the incoming URL will be mapped to `af_site_id` in the outgoing URL.
4. Decide the default value for the mandatory outgoing parameters that cannot be empty.
5. Send your developer the following information:
   * Your incoming - outgoing parameter mapping. The developer will create a script that generates an outgoing direct URL based on the incoming-outgoing parameter mapping.
   * The parameters' default values. The script will populate the outgoing URL parameters with the default values whenever there are no corresponding incoming URL parameter values.
   * If using a OneLink attribution link, send your developer the domain and template ID. The developer uses this to create the outgoing OneLink URL. For example: `your_brand.onelink.me/A1b2` or Branded domain example: `click.yourbrand.com/A1b2`
   * Send your developer the following Dev Hub links:
     * [Instruction and code examples](https://dev.appsflyer.com/hc/docs/create-direct-click-url) on how to create the outgoing direct URLs to the non-mobile platforms.
     * [A demo and instructions](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) for creating a cross-platform landing page.
   * When present in the incoming URL, the `gclid` parameter is forwarded automatically to the outgoing URL parameter, eliminating the need for manual mapping (Starting from Smart Script version 2.8.1). Your developer still has the option to map the `gclid` to one of the `af_sub` parameters, making it available in raw data reports; see Google Ads GCLID.

</Accordion>

## Create a landing page with OneLink Smart Banners

**User journey:** The user clicks on a Google ad and is directed to your mobile website. They land on a page, and a Smart Banner with a CTA to download the app from the app store is displayed.

<Accordion title="End-to-end data flow">

1. The user clicks on a Google ad, Google automatically appends to the Final URL the following:
   * a `gclid` parameter for Android devices and for consenting users on iOS devices.
   * a `gbraid` and `wbraid` for iOS device non-consenting users.
   * all the query parameters set in the ad Google Tracking Template URL, except the redirection parameters.
2. Simultaneously, the Google Tracking Template URL behind the ad, which contains the auto-appended `gclid` parameter and the `pid=googleads_int` parameter, is fired in the background, and the click is registered with AppsFlyer.
3. When the landing page loads, the Smart Banner fires an <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">impression</Anchor> event to AppsFlyer, which includes the incoming URL parameters. This impression enables view-through attribution for the landing page. To learn about impressions and view-through attribution, see <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">Create a custom impression URL</Anchor>.
4. The Smart Banner generates the outgoing URL for the CTA button on the banner based on the incoming parameters, including the `gclid` parameter. The Smart Banner can generate only OneLink-based links.
5. When the user clicks the Smart Banner CTA button, the click is fired and registered in AppsFlyer.
6. The user is redirected to the store and downloads the app.
7. The install event is registered in AppsFlyer when the user opens the app.
8. AppsFlyer attributes the install based on probabilistic modeling or deterministically if an [install referrer](https://www.appsflyer.com/glossary/install-referrer/) is available.
9. A postback containing the `gclid` and other event parameters is generated and sent to Google Ads via the OCI API. Google uses the `gclid` parameter to identify the specific click, while the other parameters help optimize the campaign.

</Accordion>

<Accordion title="Set up a Smart Banners landing page">

> 📘 **Note**
>
> The instructions below focus on the steps needed to set up a Google web campaign with Smart Banners. For a comprehensive guide on how to set up Smart Banners campaigns, see the setup section of the Smart Banners—mobile web-to-app (for marketers) article.

To set up your Smart Banners for Google web campaigns, perform the following:

1. Create a Smart Banner. For instructions, see the <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-mobile-web-to-app-for-marketers#configuration">setup section</Anchor> of the <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners—mobile web-to-app (for marketers)</Anchor> article.
2. Make sure that the incoming URL includes the following:
   * The `pid=googleads_int` is available in the incoming URL.
   * The `gclid` parameter is available in the incoming URL. Smart Banners automatically forwards `gclid` the parameter to the outgoing banner URL. The `gclid`parameter is necessary for the successful delivery of in-app postbacks to Google OCI.
   * The `gbraid` and `wbraid` parameters are available in the incoming URL when sending postbacks for non-consenting iOS device users. Smart Banners automatically forwards these parameters to the outgoing banner URL. In this case, the `gbraid` and `wbraid` parameters enable Google to get aggregated event data in the absence of the `gclid` parameter.
   * All relevant URL parameters are appended to the incoming URL. To review the parameters appended to the incoming URL, open Google Ads, and check the URL parameters set when creating the Final URL or Tracking Template URL; see: [Set the campaign URLs.](#h_01J1MPPMW44NGXN55SFD16Z4HE)
3. (Optional) In the banner group setting page under the **Dynamic attribution parameters** section, select the first checkbox. This setting makes sure all parameters on the incoming link are added to the link on the Smart Banner.

</Accordion>

## View web-to-app attribution data

Although web-based conversion events are sent to Google under the original `googleads_int` PID, they are reported in the AppsFlyer dashboard and raw data reports under the `googleadwords_int` PID. This applies both to primary conversion events and to conversion assist events.

This unified reporting view lets you analyze both web and app campaign performance in one place, including full mobile and web cost reporting.

### View in the dashboard

All Google web-to-app attributions appear under `googleadwords_int` in the Overview and Activity dashboards. This provides a single, consolidated view of campaign results across platforms. Use standard filters and breakdowns to compare app and web traffic within your Google Ads data.

### View in raw data and API reports

* **Raw data exports and API responses** include the `googleadwords_int` PID in the `media_source` field for Google web activity. To verify web campaign setup details, refer to the `original_url` field that shows `googleads_int` as the PID used during the creation of web campaigns.
* **Postback reports** show `googleads_int` as the original media source to which the postback was sent.

## Troubleshooting in-app events postbacks

If in-app event data is not displayed in Google Ads or Google Analytics, or if you get the Missing token error, make sure the following settings are correct before contacting support:

<Accordion title="Set token permissions">

In Google Ads, make sure that your access token has the necessary permissions to upload offline conversions:

1. Go to the Google Developers Console.
2. Make sure that `uploadClickConversions` has the following OAuth scope: [`https://www.googleapis.com/auth/adwords`](https://www.googleapis.com/auth/adwords)
3. In AppsFlyer in the integration tab, click **Sign in with Google**.
4. Select the admin account of the MCC account.
5. Click **Allow**.

</Accordion>

<Accordion title="MCC Customer ID">

If you have multiple Google Ads accounts running campaigns for your app, you must use the Customer ID of an MCC account. See [Google instructions on configuring an MCC account](https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC).

</Accordion>

<Accordion title="Conversion Action ID">

Make sure the postback in-app events are mapped to the correct conversion action ID. To find the conversion action ID in Google Ads, see [Find the conversion action ID in Google Ads](#to-find-the-conversion-action-id-in-google-ads).

</Accordion>

<Accordion title="GCLID, GBRAID, WBRAID parameters">

The Smart Script or Smart Banners outgoing URL must include either `gclid`, `wbraid`, or `gbraid` for the postback to Google OCI to register properly in Google Ads.

</Accordion>

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| <span id="dashboard"></span>Dashboard | Attribution data for Google web-based campaigns on iOS is viewed and analyzed in the AppsFlyer Classic Dashboard. In most cases, the SKAN Dashboard is not relevant for web-to-app campaigns. |
| <span id="reengagement-attribution"></span>Re-engagement attribution | Users may observe installs attributed to `googleads_int` and re-engagements attributed to `googleadwords_int`, even though both are driven by the same campaign. This behavior is expected and does not indicate a technical issue.   <br />  <br />It typically occurs when a`googleadwords_int` SRN integration is active alongside, allowing it to claim re-engagements from the same Google Ads web2app campaign. |
| <span id="cost-data"></span>Cost, clicks, and impressions data | Cost, clicks, and impressions data for Google Ads Web (`googleads_int`) is supported through the Google Ads integration (`googleadwords_int`).<ul><li>To get the data make sure to connect the ad network account to the main PID (`googleadwords_int`):<ul><li>ROI360 subscribers: in the **Cost Settings** page,</li><li>ROI360 non-subscribers: in the **Active Integration** page (**Cost** tab).</li></ul></li><li>To view cost, clicks, and impressions data for Google Ads Web campaigns, make sure the campaign ID (<Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>) is included in the attribution link.</li><li>The attribution link must include the full campaign hierarchy to view cost,  clicks, and impressions data tied to attribution at the most granular level.</li></ul> |
| <span id="tracking-template-urls"></span>Tracking template URLs | Tracking template URLs must comply with the limitations below. Failing to do so will result in a broken link.<ul><li>Links must not contain any duplicate parameters.</li><li>Links must not include invalid parameters such as:<ul><li>Parameters without values, broken parameters, or parameters that cannot be parsed. This includes parameters without values such as `key=` or `key`. For example: `pid=googleads_int&key&c=campaign` or `pid=googleads_int&key=&c=campaign`</li><li>Missing values in one of the ValueTrack parameters, for example `{placement}`. To avoid missing values make sure that Google Ads populates them by defining the tracking template correctly in Google Ads.</li></ul></li><li>If you have entered values for any parameters under the **Campaign URL option** in your Google Ads campaign setup, these must match the parameter values in the tracking template. If they do not match, please remove them from the tracking template to make sure it complies with the policy update.</li></ul> |
| <span id="unexpected-srn-attribution"></span>Unexpected SRN attribution | In some cases, installs from Google Ads web-based campaigns may be attributed to `googleadwords_int` via SRN (self-reporting network), even in web-based campaigns. This occurs when Google claims the install. AppsFlyer attributes the install accordingly when Google makes the claim. This behavior is expected and may become more common as Google expands support for web campaign install attribution. |
| <span id="agency-managed-campaigns"></span>Agency-managed campaigns | If the web campaign is managed solely by an agency, both the advertiser's and the agency's `googleads_int` integrations must be active for postbacks to reach Google Ads. The agency must also complete [Sign in with Google](#h_01J1MPPMW3G9B1G116B18CRYJB) to provision an OAuth token. If this step is skipped, the postback call fails and is not sent to Google. |
| <span id="plan-availability"></span>Plan availability | The `googleads_int` integration is only available for Growth and Enterprise plans. Customers on the Zero and Welcome plans cannot use this integration. |

<div data-zendesk-anchors="h_01J1MPPMW38A7EG2W8TJ8F6YQ3=overview h_01J1MPPMW3GWQKZVG2HAQA9H46=prerequisite how-to-create-a-google-ad-web-campaign=create-a-google-ads-web-campaign h_01J1MPPMW3ZYSPQHT4D2YAJ038=create-a-google-ads-web-campaign create-a-google-ad-for-web-integration-in-appsflyer=create-a-google-ads-integration-in-appsflyer h_01J1MPPMW3WTD63M686BHZNKDX=create-a-google-ads-integration-in-appsflyer h_01J1MPPMW4AQNQEKBN1VSPM4X7=create-a-web-campaign-in-google-ads h_01J1MPPMW48F7X2NYEA735BG51=set-the-final-url h_01J1MPPMW44596CZVKF9MGDTMP=set-the-tracking-template-url 01JCZQR9RJAZF4SJVVKYZNJNPY=google-tracking-template-url-examples 01JCZQR9RMAW9YP3T3679JAX45=using-the-tracking-template-url-with-smart-script-or-smart-banners h_01J1MPPMW4P7Q18JN7JS9ZXR23=create-a-landing-page-with-onelink-smart-script h_01J1MPPMW4CW8JMJK26PTEY74W=create-a-landing-page-with-onelink-smart-banners google-view-web-to-app=view-web-to-app-attribution-data view-webtoapp-attribution-data-from-november-2-2025=view-web-to-app-attribution-data h_01K88H6ETM23EV0PTR8GS13KRN=view-web-to-app-attribution-data h_01K88H6ETMG7007CJ0ADD8VQH4=view-in-the-dashboard h_01K88H6ETM502Z2XDC63602FGD=view-in-raw-data-and-api-reports troubleshooting-inapp-events-postbacks=troubleshooting-in-app-events-postbacks h_01J52V5G2DSF9PW9Z5GJHAD376=troubleshooting-in-app-events-postbacks 01JDW5XHD92VFJ93671YP4JMFQ=traits-and-limitations" />
