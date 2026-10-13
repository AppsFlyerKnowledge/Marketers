---
title: "Smart Banners—mobile web-to-app (for marketers)"
excerpt: "Convert your website visitors into mobile app users and measure campaign performance with AppsFlyer Smart Banners."
x-zendesk:
  id: 360000764837
  url: https://support.appsflyer.com/hc/en-us/articles/360000764837-Smart-Banners-mobile-web-to-app-for-marketers
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Web-to-app attribution
  section_id: 6551240476177
  position: 1
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, Smart Banners and Scripts]
  labels: [Landing Page, Advertisers, Web Attribution, Developers, Smart Banner, sb, Marketers, Banner, Banners, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2019-01-14T12:33:07Z'
  edited_at: '2026-02-23T14:37:29Z'
---
**At a glance:** Convert your website visitors into mobile app users with Smart Banners.

[![](https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg)](https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg)

> 📘 **Note**
>
> AppsFlyer Smart Banner web SDK v1 was deprecated on Nov. 8th, 2023. To show Smart Banners on your website you need to upgrade to v2. [Learn more.](/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1)

## Smart Banners

Smart Banners:

* **Display on your brand's mobile website** to increase conversion rates for high-intent users.
* Measure the quality of app installs coming from visitors to the mobile website.
* Enables accurate web campaign-to-app mobile attribution for ALL media sources, including SRNs.
* Smart Banners can attribute using [view-through attribution, click-through attribution](/docs/appsflyer-attribution-model#user-engagement-attribution-types) and count impressions:
  * **Clicks:** A user clicks the Smart Banners and proceeds to install.
  * **Impressions:** When the banner loads (user sees the banner), it sends an impression count event to AppsFlyer.

The flow works as follows:

1. A user clicks on an ad and is directed to the advertiser’s mobile website.
2. A Smart Banner [displays](/docs/smart-banners-mobile-web-to-app-for-marketers#banner-group-display-logic) on the advertiser’s mobile website.
3. The user clicks on the Smart Banner and:
   * **If the app is not installed**, the user is directed to the app store to install the app.
   * **If the app is installed**, and Universal Links, App Links, and/or URI links are configured, the app is directly launched.
4. The user reaches in-app content, in the context of the promotion.
5. The user is attributed to the media source that showed the original ad.

**Who's involved**

* The website developer only needs to [enter a code snippet into the HTML of the website](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#installation).
* For all other actions, only the marketer is required.

---

**Prerequisites**

* An AppsFlyer account with at least one app
* [OneLink template](/docs/create-a-onelink-template) containing the app/s to be advertised using Smart Banners This is required by Smart Banners to direct your mobile web visitors to the correct app store pages according to the devices they use.

---

**Time required**

Approximately 20 minutes.

---

**Outcome**

* Website visitors clicking the CTA button are sent to the correct app store or web page based on their device.
* Mobile app users clicking the CTA button can be deep-linked into the app.
* Users are attributed from the click/install to the original media sources or to your owned media sources.
* Banner performance can be viewed in the performance page and cards.

---

---

> 📘 **Example**
>
> Mark is a marketer working for the successful food delivery service "Feed Me".
>
> Mark wants to convert Feed Me's mobile website visitors into app users.
>
> To do this Mark utilizes Smart Banners using his own visuals and texts.
>
> Smart Banners are powered by OneLink. When mobile website visitors click the CTA button, it **automatically directs them to the appropriate app store or landing page**, where it's easy for them to install the app. When existing mobile users click the CTA button, it launches the app.
>
> AppsFlyer then **attributes the click/install to Mark's defined media source and campaign**.

> 📘 **Important!**
>
> Use either AppsFlyer Smart Banner or iOS Safari smart app banner, but not both. Using both may cause display issues on your mobile website, and result in attribution discrepancies.

## Setup

Complete the following procedures to set up a Smart Banner that:

* Directs users from your mobile site, via a Smart Banner, to the correct app store or app page based on their device.
* Attributes the click/install to your owned media source using OneLink.

### 1. Website workplace setup

#### Prepare your mobile site to display Smart Banners for the first time

1. In AppsFlyer, from the side menu, select **Engage** > **Web-to-app** > **Smart Banners** > **Go to Smart Banners**.
2. Click **Get started**. The setup wizard will guide you through the required steps (following). To set up further Website workplaces see below.
3. Enter a website workplace name.
4. Click **Create**. The website workplace opens.
5. Copy the banner **Code snippet**.
6. Implement the code snippet on your website. This task is done only once per website.
   * To add the code to your website via Google Tag Manager, Adobe Tag Manager, Shopify, Wix, Squarespace, or WordPress, see [Smart Banners website code implementation for marketers](/docs/smart-banners-website-code-implementation-for-marketers).
   * To add the code via other platforms, or to make changes to the code based on need (including adding parameters, deep linking, hiding the banner, or integrating PBA with Smart Banners), see [Smart Banners website code implementation for developers](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2).
7. [optional] Copy **Web key**. (This key already exists as part of the code snippet.)
8. Click **Continue**.

#### To create Website Workplaces after the first time

1. In AppsFlyer, from the side menu, select **Engage** > **Web-to-app** > **Smart Banners** > **Studio**.
2. Click on the options menu
3. select **New website workplace**
4. Enter a website workplace name.
5. Click **Create**. The website workplace opens.
6. Copy the banner **Code snippet**.
7. Implement the code snippet on your website. This task is done only once per website.
   * To add the code to your website via Google Tag Manager, Adobe Tag Manager, Shopify, Wix, Squarespace, or WordPress, see [Smart Banners website code implementation for marketers](/docs/smart-banners-website-code-implementation-for-marketers).
   * To add the code via other platforms, or to make changes to the code based on need (including adding parameters, deep linking, hiding the banner, or integrating PBA with Smart Banners), see [Smart Banners website code implementation for developers](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2).
8. [optional] Copy **Web key**. (This key already exists as part of the code snippet.)
9. Click **Continue**.

### 2. Banner group setup

Banner groups contain one or more banners. Here you can:

* Select the OneLink template used by the banner group, which contains the mobile apps to redirect your website visitors to.
* Set a specific deep-linking scheme
* Define your targeting rules, scheduling, behavior, and attribution details used by all banners of the banner group.
* Set which pages activate the banner group's banners when visited.

**To set up or duplicate a banner group:**

1. In AppsFlyer, from the side menu, select **Engage** > **Web-to-app** > **Smart Banners.**
2. **To set up a banner group for the first time**
   1. On the left-hand side, click **Add banner group**.
   2. Follow steps 5 and onwards.
3. **To set up additional banner groups**
   1. Go to the **Studio** tab.
   2. Click on **+ New.**
   3. Follow steps 5 and onwards.
4. **To duplicate a banner group**
   1. Click on the **Duplicate** icon found next to the delete icon.
5. Enter a unique **Banner group name**. The name should reflect a general common theme between the Banners to be defined for the banner group (e.g., the advertised app).
6. Select the OneLink template for the banner group.
7. [optional] Set **URI scheme** for the banner group as a fallback for Universal Links and Android App Links users. This is rarely needed as, by default, the value is taken from the OneLink template. Set this for the banner group only if you need a different value than the one in the template.
8. Set the primary and fallback **Attributed sources** to be attributed with new installs coming from this banner group.   
     
   **Note on click ID forwarding:** FBCLID, GCLID, WBRAID, GBRAID, ttclid, twclid, and ScCid are automatically forwarded to the outgoing URL if available on the incoming URL. For the Google click IDs, if the “keyword” parameter is also found, it puts the keyword value in the outgoing URL as the value of af\_keywords.

   Use the following table to pick the best option for the custom link:

   

| Option | When to select | Comments |
| --- | --- | --- |
| **Use UTM parameters** | Select when most non-organic visitors get to the mobile website from sources with UTM parameters. | ◦ Media source name (pid) = UTM\_Source  <br />◦ Campaign (c) = UTM\_campaign  <br />◦ If the UTM\_source or UTM\_campaign are missing, the static names are used as a fallback. |
| **Use incoming attribution link parameters** | Select when most non-organic visitors get to the mobile website from click ad networks that use AppsFlyer attribution links. | ◦ All available parameters from the incoming AppsFlyer attribution link are added to the Smart Banner link.<br /><br />◦ If a parameter exists in both the incoming AppsFlyer attribution link and the Smart Banner, the incoming parameter takes precedence in the final custom link. |
| **Add another attribution parameter** | If you want, add additional website-related attribution data. This enables granular analysis of every install. | For example, for eCommerce sites create identical custom links for every product category type, that differ by af\_adset values (for example: "af\_adset=fruit") |
| **Use default attribution parameters** | ◦ Select when:   ▪ Most mobile website visitors are organic.   ▪ Non-organic visitors don't get to the website from click ad networks or from sources with UTM parameters. ◦ You can customize the parameter values. | **Important:** Best practice is to select UTM or incoming attribution link parameters, since the default Smart Banner attribution parameters are anyway used on the custom link as a fallback if the media source, campaign, or channel names are not available. |

9. [Recommended] Set the default attribution parameter **Channel name** to attribute all installs coming from the Smart Banner to the specified channel. This enables you to aggregate information from multiple media sources under the same channel in the **Cohort report**, **Overview dashboard**, **Retention report**, and more.
10. [Optional] Turn on **Retargeting** if you plan to use the banner group to record re-engagements performed by users clicking on the banner. To learn more on Retargeting see the [Retargeting attribution guide](/docs/retargeting-attribution-guide).

    CALLSTART::Note::

    #### ***Important***

    For retargeting to work, you also need to:

    * [Enable retargeting for the app](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#enable-retargeting-for-the-app) CALLEND::

    Existing users who click on OneLink-powered non-retargeting banner links (UA) also launch the app and have the same user experience. However, their re-engagements are recorded as regular sessions, which means it's impossible to measure the success of the owned media campaign.
11. [Optional] Turn on **Ignore active users for retargeting** and select the inactivity window. This adds the parameter af\_inactivity\_window=[number of days] to your smart banner group links, and all users active during the period are ignored for retargeting.
12. Set the re-engagement window to determine the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source.
    * You can set the value in days (1-90), hours (up to 23), or even lifetime.
    * The re-engagement window is added to the link in the af\_reengagement\_window parameter.
13. [Optional] Set the **Dismissal behavior**, that is, the minimum time allowed between a user dismissal of one banner in the group, until the same banner may be displayed again to the user. Select from one of the following:
    * By time: 1 hour, 1 day, or 1 week.
    * Next session: meaning the session that takes place in a different tab or window, after the user closes the banner.
    * Never: the banner is not shown again. **Note**:
      * If the user clears the browser cache or views the site in private browsing mode the Dismissal Behaviour setting is lost.
      * The dismissal behavior is applied to the banner the user dismisses; other banners in the banner group can still be displayed.
14. [Optional] Set **Frequency capping**.  Frequency capping determines the number of times each banner in a banner group is shown to a unique user. You can choose either **No limit** (where banners always display) or **Limit banner displays**.

    For instance, if a banner group consists of three banners and the frequency capping is set to one, each banner in the group will appear once per user. In this scenario, after three visits, the user will have seen all three banners within the group. However, starting from the fourth visit onwards, the user will no longer encounter any banners from the group. When the frequency capping is set to two, each banner in the group will be displayed twice per user, requiring a total of six visits to reach the group's capping limit.
15. [Optional] Set which **Operating system** to show the banners on:
    * All mobile operating systems.
    * Just Android or just iOS.
16. [Optional] **Schedule** the banner group's activation: start immediately (default) or set a time-limited campaign.
17. [Optional] Set **Locations** where the banner group is activated for.
    1. Select **Worldwide** to display this banner group to all users. If needed, exclude visitors coming from different regions, countries, or states.
    2. Select **Pick specific location** option to display this banner group to users from one or more specific locations.
18. [Optional] Set **Show on pages**, meaning, on which pages the banner group can be displayed to visitors:
    * [Default] **Show on all pages** of the website. **Note**: We recommend defining at least one banner group for all pages as a fallback.
    * **Show on specific pages**: Specify what the page or URL should or should not contain in order to display banners.
      * You can choose either:
        * **Specific page**: Specify the host and/or path of the page on which to display the banner. Any queries entered will be disregarded. Example: **http://www.example.com/path**?query
        * **URL path and query**: Enter the path and/or query that determines whether or not the banner displays. Example: path?query. **Note**: Don’t enter an entire URL, such as http://www.example.com/path?query. Only enter the path and/or query.

* Up to 15 conditions can be added using and/or.
* If there is a conflict between conditions, the banner will not display.

1. Click **Create Banner group**.
2. [Optional] To edit the banner group again, hover over **Targeting & behavior** and click **Edit**.

> 📘 **Example**
>
> Mark is the marketer for a food delivery service called "Feed Me". He decides to create a campaign for the app’s plum sale. Mark decides to use an SMS blast, as well as ad networks and Google for the campaign.
>
> In preparation for the campaign, Mark:
>
> * Selects to use both incoming link attribution parameters and UTM parameters (with default parameters as the fallback for clicks that come from neither an incoming link or a UTM campaign).
> * Gives the ad network a unique attribution link to use in the campaign to drive users to the plum sale page on the Feed Me mobile site. The link includes the Redirection URL (af\_r) parameter, with the URL to the plum sale page: `http://feedme.com/plums_link`.
> * Prepares a Google Ads campaign for users visiting pages in the mobile web containing "plums\_utm".
> * For SMS, adds unique attribution params to use in the campaign link to drive users to the plum sale page on the Feed Me mobile site. The link includes the pid parameter, with the URL to the plum sale page: `http://feedme.com/plums_link?pid=sms&c=plums`.
>
> The campaigns start running.
>
> The users:
>
> * See the ad for the plum sale and click through to the Feed Me mobile site.
> * Google Ads clicks and all other clicks arrive to the incoming link landing page and the matching Smart Banner is activated per page.
> * See the Smart Banner on the mobile site and click it.
> * Arrive at the Feed Me app, download, and install.
> * Get directed upon app launch to the plum sale.
> * Are attributed to the correct media sources that led them to the Feed Me mobile site.

#### Targeting & behavior

The Targeting & behavior panel shows you the settings you configured for that banner group. To edit these settings click on the edit icon.

### 3. Banner setup

**To create a banner in a banner group:**

1. Click **New banner** to enter the **Edit banners** page.
2. Set the **Name** of the banner.
3. Create a **Design creative**:
   1. Click **Design creative** to set the creative of the banner.

      A window to choose a banner template opens.

      [![](https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png)](https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png)
   2. Hover over a **Creative template**, and click **Create** to enter the **Build creative** setup page.
   3. Customize all the elements in the Smart Banner creative. To do so, select elements by name or click on them on the preview image. **Note:** Not all elements are available on every template.
      * Title
      * Description
      * Rating stars
      * Close button
      * Call to action
      * App logo
      * Background
      * Banner position
      * Banner padding (to adjust banner size)
      * Device transparency
      * For images, use one of the following file types: jpeg, jpg, png. **Note**: webp format is not supported.  The recommendations for the images are:

        

| Template type | Maximum image file size | Image ratio | Image height | Image width |
| --- | --- | --- | --- | --- |
| Minimal | 300 KB | 3:1 (width x height) | 70 px | Adjusted to fit device |
| Standard | 300 KB | 3:1 (width x height) | 70 px | Adjusted to fit device |
| Enhanced | 300 KB | 9:4 (width x height) | 110 px | Adjusted to fit device |
| Multi-choice | 300 KB | 9:4 (width x height) | 110 px | Adjusted to fit device |
| Promotional | 300 KB | 4:5 (width x height) | 300 px | Adjusted to fit device |
| Multi-choice overlay | 300 KB | 9:4 (width x height) | 110 px | Adjusted to fit device |
| Interstitial | 700 KB | 9:16 (width x height) | Adjusted to fit device | Adjusted to fit device |

   4. Click **Review** to review the banner creative and test its appearance on different devices. **Note**: Banners may appear slightly different in active campaigns compared to preview images.
   5. If changes are needed, click **Back to editor**.
   6. Click **Done** to go back to the banner setup page.
4. [Optional] Add custom attribution parameters. For example, `ad_adset` and `af_ad`. **Note**: The parameters `pid`, `c`, and `channel` cannot be added at the banner level, as they belong to the banner group level.
5. After finishing and saving the new creative, the banner's status becomes active. Use the **Status** toggle to switch between **Active** and **Paused** statuses.
6. Click **Save all** to save your work or **Save all and close** to save your work and close the banner setup page.

> 📘 **Example**
>
> For tips and tricks, see our [Smart Banners cheat sheet](https://drive.google.com/file/d/1mr6g3uNwlLw6UQ_WgtQZprJMhauw7Xi3/view?usp=sharing).

### 4. Testing

Once the creative is ready, it's time to put it to the test **before** setting it live and activating it for your users.

**To test a Smart Banner creative:**

**Prerequisite:**Make sure that the Smart Banner code snippet is integrated into your website.

1. In the **Test Creative** page, enter the link to your web page where the Smart Banner SDK is integrated (see [Smart Banners for developers](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2)).
2. Click **Generate**.
3. Copy the generated link and send it to your test device, or scan the QR code with the test device. **The link or QR should redirect you to the web page and display a banner with the creative.**
4. Click **Edit Creative** to return to the creative configuration, or click **Done** to save the creative.

## View banner performance

You can view and compare the performance of all your banners on the performance page.

You can get a quick view of the performance for specific banners on their individual performance cards.

Banner performance data includes:

* Impressions
* Banner closes
* Clicks
* Installs
* Re-engagements
* Re-attributions
* Click-through rate (CTR). Formula: Clicks/impressions * 100
* Conversion rate (CVR). Formula: Attributions/Clicks * 100

**Note**:

* Data is based on UTC timezone.
* Data freshness is [continuous](/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime).
* Data displayed is per banner and OneLink template. This means that if your banner and OneLink template are configured for more than one app (for example, both an Android and iOS app), the performance data that displays is for more than one app.
* CVR may be higher than expected, sometimes even above 100%, as both view-through attributions and click-through attributions are counted.

### Performance page

The performance page lets you view and compare the performance data of all your Smart Banners, up to the past 90 days.

**To view the performance page**:

1. In AppsFlyer, from the side menu, select **Engage** > **Web-to-app** > **Smart Banners** > **Performance**.
2. Select the date range for which you want to view performance. The default date range is the last 7 days.
3. [Optional] Turn on **Show only currently active banners**. If turned on, data for banners that are paused or aren't currently active don't display, even if they were active during the selected date range. The performance data displays for the selected date range.

### Performance cards

You can view performance data for the past 7 days for any given banner.

**To view banner performance**:

1. In AppsFlyer, from the side menu, selecto **Engage** > **Web-to-app** > **Smart Banners** > **Studio**.
2. Select the website workplace and banner group you want to view performance for.
3. Hover over any of the banners in the banner group. The performance data displays for the past week

## Additional information

### Banner group display logic

AppsFlyer takes the following into consideration when determining if/what Smart Banner to display:

* Are there rules (dismissal behavior, frequency capping, locations, show on pages, etc.) set for the banner groups?
* Does the end-user meet the rule conditions and qualify to see a banner?

If the answer to both questions is yes, meaning there are rules, and the user qualifies to see a banner, AppsFlyer chooses a banner to display as explained in the table that follows.

| Banner group setup | Which banners display | Example |
| --- | --- | --- |
| Single banner group | AppsFlyer evenly splits the display of all active banners in all your banner groups between all eligible users. | • Example 1: There is 1 active banner. It displays to all users.<br /><br />• Example 2: There are 2 banners. 50% of users see banner 1, and the other 50% see banner 2.<br /><br />• Example 3: There are 3 banners, 1/3 of eligible users see each banner.<br /><br />• Example 4: There are no active banners. Nothing displays. |
| Multiple banner groups with identical rules | AppsFlyer evenly splits the display of all active banners in all your banner groups between all eligible users. | There are 2 banner groups (A and B), each with 3 banners (for a total of 6 banners). 1/6 of eligible users see each banner. |
| Multiple banner groups with multiple rules | AppsFlyer evenly splits the display of all active banners *from the banner group with rules that most specifically describes and match the users*. If the banner groups are equally specific in different ways, banners from all these banner groups display. | • Example 1: There are 2 banner groups, A and B. Banner group A is set to show worldwide, and Banner group B is set to show in Japan. Banner group B is more specific, so only the banners from that group display to users in Japan. If the group has no active banners, nothing displays.<br /><br />• Example 2: There are 2 banner groups, A and B. Banner group A is set to show worldwide, and Banner group B is set to show everywhere except Ukraine. Banner group B is more specific, so only the banners from that group display to worldwide users (except users in Ukraine). If Banner group B has no active banners, nothing displays. Banner group A displays in Ukraine.<br /><br />• Example 3: There are 2 banner groups, A and B. Banner group A is set to show in Japan, and Banner group B is set to show in April. Both banner groups are equally specific, but in different ways. Therefore, in Japan, in April, banners from both banner groups display, as neither banner group has priority over the other. |

### A/B testing banner performance

You can A/B test banners by comparing their performance in the performance dashboard. For additional attribution-related data, it's recommended to add the `af_adset` , `af_ad` or other attribution parameters (except `pid`, `c`, and `channel`) with a unique value for each banner creative or banner group. Use those parameters to compare each banner group's performance when viewing data in AppsFlyer dashboards and reports.

## FAQ

### Why does my banner not display?

This is due to the frequency cap set in your banner group. Frequency capping determines how many times the banner is shown to a unique user. For example, if frequency capping is set to three, and a user visits the site four times, the user sees the banner on the first 3 visits but not on the fourth and onward. Frequency capping can be disabled. Select a frequency capping value or disable frequency capping.

### Can I use my own font for my banner?

Yes. you can set your own font used on your website for your banner using the [instructions on the developer hub](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#control-smart-banner-font).

* Requires a website developer to implement.
* The font will apply to all banners on the website and to all text elements inside the banner.
* The font can not be viewed in the creative editor.
* After implementing, [test your creative banner](/docs/smart-banners-mobile-web-to-app-for-marketers#4-testing).
* If the font doesn't display correctly, resave your banner in the [creative editor](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup).

### Can I add parameters to the URL of my Smart Banners?

Yes, by invoking the following two functions in your smart script:

* [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner)
* [updateParams](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams)

### Do Smart Banners support deep linking?

Yes. To do so, add the [deep\_link\_value parameter](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking) in one of the following ways:

* In the AppsFlyer UI, add a static custom attribution parameter during [banner setup](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup).
* Use additionalParams in the [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=) function to add the parameter to the URL prior to displaying the banner.
* Use the [updateParams](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams) function to add the parameter to the URL after the banner displays.

Make sure your developer implements the desired behavior of the deep\_link\_value.

### Can Smart Banners show different content based on whether or not users have the app installed?

No. If you don't know whether or not users have the app, we recommend you make your call to action applicable to both. For example: "Go to the app" or "open the app."

### Do original incoming URL parameters remain available for the Smart Banner URL when users navigate away from, and then return to, the banner's landing page?

Yes. If the original incoming URL contains a utm\_source or pid parameter, the original URL is saved for the duration of the browsing session and the parameters are applied to the outgoing banner URL.

### Can I set my banners to display on my mobile site but not on my wrapper/hybrid app?

Yes. To do so, when you implement Smart Banners in a wrapper/hybrid app and load the banner page from the app (and not from a web browser), don't use the [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=) function, as this displays the banner in the app. Alternatively, use the [hideBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#hidebanner) function.

### Do Smart Banners support web accessibility?

We are committed to ensuring that all of your users, including those with disabilities, can fully access and engage with Smart Banners.

As such, we try to make our Smart Banners web accessibility compatible and follow the WCAG 2.1 standard best practices by providing the relevant HTML attributes in the Smart Banner elements.

However, determining the relevant accessibility requirements for your own intended uses of such Smart Banners is your sole responsibility. You are solely responsible for ensuring that Smart Banners you use remain accessible to all users in accordance with relevant web-accessibility requirements.

Please note that various changes to the Smart Banner might impact its compatibility with the relevant accessibility requirements, including for example, by editing the colors and size of internal banner elements.

### If a smart banner is deleted from a banner group, will the data associated with that banner group also be removed?

No. Attribution data is not deleted if a smart banner is deleted.

## Troubleshooting & traits and limitations

| Trait | Remarks |
| --- | --- |
| Banner display split | AppsFlyer evenly splits the display of active banners to users. It’s not possible to select which specific banners to display more or less. For example, if there are 2 banners in a group, they each display to 50% of users. It can't be changed to a 70%-30% split. |
| Custom parameters | • The following special characters are not allowed in custom parameters: ;, *, !, @, #, ?, $, ^, :, &, ~, `, =, +, ’, >, &lt;, / • If you define a parameter using one of these special characters, the parameter is not saved. |
| Name change | Banner group names and banner names can be changed. Performance data isn't affected and carries over. |
| Number of button closes | Data is available as of February 17, 2026. Data is retained for 90 days. |
| Specific page | When you set up your banner group to display banners on a specific page, the banner rule applies only to the host/path you enter. If there is not a perfect match (for example, if your site page has additional strings not included in the rule setup), the rule doesn't apply. |
| Tablets | • Smart Banners are designed for mobile devices and their resolutions may not be optimized for tablets with large screens. • Browsers on tablets may not be recognized as mobile devices. |
| The banner displays alongside a vacant area | When encountering this behavior, assess its cause using the following criteria:<br /><br />* Verify that the SDK code snippet has not been implemented more than once on the webpage.<br />* Ensure that the [`showBanner`](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner) function has not been invoked multiple times. |