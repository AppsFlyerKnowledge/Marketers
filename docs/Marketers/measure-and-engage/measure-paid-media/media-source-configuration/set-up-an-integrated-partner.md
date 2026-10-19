---
title: Set up an integrated partner
excerpt: >-
  Enable attribution measurement, send postbacks to partners, and enable other
  integration features by setting up the partner connection with AppsFlyer.
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2021-11-08T08:02:46Z'
  edited_at: '2026-08-31T11:29:22Z'
  id: 4410395957521
  locale: en-us
  section: Media source configuration
  section_id: 6551067072785
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4410395957521-Set-up-an-integrated-partner
---
## Overview

Partners, media sources, and third-party platforms integrate with AppsFlyer by API. This article contains the generic instructions to activate and set up the integration, including generating attribution links for non-SRN ad networks.

* This guide isn't applicable to SRNs. Use the [SRN](/docs/self-reporting-networks-srns) explicit article.
* Some ad networks have dedicated articles.
* Before setting up the configuration, contact the partner and open an account with them.

<div id="partner-types-in-the-ecosystem" />

<Accordion title="Partner types in the ecosystem">

The image below contains the different partner types that form the attribution ecosystem.

[![Ecosystem.jpg](https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg)](https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg)

**Related reading**: [AppsFlyer Performance Index](https://www.appsflyer.com/performance-index/) ranks mobile media sources by category and region.

| Partner type | Description |
| --- | --- |
| Ad networks | Run campaigns on your behalf. |
| Agencies | Use their expertise to get high-quality users by running campaigns on your behalf. Learn more about [agency data](/docs/view-agency-data). |
| Marketing partners | Marketing partners specialize in working with specific ad networks. Examples: Meta campaign management partners, Apple Ads marketing partners, X marketing partners. |
| Retargeting networks | Ad networks specializing in running retargeting campaigns. |
| Third-party platforms | Provide BI-related services like analytics and marketing automation platforms. |
| Fraud detection | External third-party anti-fraud systems which are not part of the AppsFlyer Protect360 anti-fraud solution. |

</Accordion>

<div id="partners-in-the-marketplace" />

<Accordion title="Partners in Partner Integrations">

All partners, media sources, and other platforms integrated with AppsFlyer are found on the Partner Integrations page. You can find both your [active and inactive](/docs/partner-activation-deactivation) partners, and search for new partners to connect with.

**To search and filter all partners, media sources, or other platforms in Partner Integrations:**

* In AppsFlyer, from the side menu, select**Collaboration**> **Partner** **Integrations**. You can use the various search filters.

#### Invite new partners to AppsFlyer

If the partner you're working with isn't yet integrated with AppsFlyer, you can [send them an invitation link](/docs/partner-integrations#invite-new-partners-to-appsflyer).

</Accordion>

<div id="your-integrated-partners" />

<Accordion title="Your active integrated partners">

The Active Integrations tab in Partner Integrations shows all your [active](/docs/partner-activation-deactivation) integrated partners. From this tab, you can learn about the partner and manage the integration.

> 📘 **Note**
>
> The list of partners shown on the **Active integrations** tab varies according to the selected app. You can see which partners are connected to other apps by clicking the app from the top-left corner and selecting a different app.

**To see all your active partners:**

* In AppsFlyer, from the side menu, select**Collaborate**> **Partner Integrations >** **Active integrations** tab.

</Accordion>

<div id="about-the-integrated-partner-page" />

<Accordion title="About the partner configuration page">

The page is structured as follows:

* **Header**, containing:
  * Partner name
  * Link to a dedicated partner article. If no dedicated article exists, this article displays.
  * Integration status
  * Selected app
* **Settings tabs**: The tabs available depend on the partner type and supported features.
* **Footer**:
  * **Back to list**: Return to the Active Integrations list using the filtering options selected previously.
  * **Status message:** Current status of the tab data (for example, saving, saved, error, there are unsaved changes).
  * **Discard Changes:** Undo the last changes without saving.
  * **Save:** Save the settings of the current tab only.

#### Applicable settings tabs per partner type

<table><thead><tr><th> </th><th colspan="2">Settings tab</th><th> </th></tr><tr><th>Partner type</th><th>Integration </th><th>Permissions</th><th>Remarks</th></tr></thead><tbody><tr><td>Media source</td><td>Y</td><td>Y</td><td><p><strong>Additional tabs available</strong>: Cost, ad revenue, attribution link</p><p>Includes ad networks, affiliate networks, direct publishers, programmatic advertising, China domestic ad networks, and retargeting Networks.<br/>For SRNs the attribution link tab is non-applicable.</p></td></tr><tr><td>Agency </td><td>N</td><td>Y</td><td>Stand-alone agencies that don't function as ad networks</td></tr><tr><td>Third-party platform</td><td>Y</td><td>N</td><td>Analytics or marketing automation platforms</td></tr><tr><td>Marketing partner </td><td>Y</td><td>N</td><td> </td></tr></tbody></table>

</Accordion>

## Set up a partner (non-SRN)

> 📘 **Important!**
>
> When enabling a partner integration, certain data, including personal information (e.g., Advertising ID, IP address), will, by default, be shared with them by you. Please ensure you have the appropriate legal basis and rights to share this data. You can limit data sharing with a partner by following the instructions provided in the [Aggregated Advanced Privacy framework](/docs/apply-aggregated-advanced-privacy-framework) and [Privacy preserving methods in the SDK](/docs/apply-privacy-preserving-sdk-methods) articles.

**To access the settings and configure your campaigns with the partner:**

Search for and select your partner, [from Partner Integrations.](/docs/set-up-an-integrated-partner#partners-in-the-marketplace)

> 📘 **Note**
>
> The [General settings](#d-general-settings) step in the **Integration** tab is mandatory for all partners. You must also complete the **Attribution link** tab for non-SRN ad networks. The remaining tabs are optional.

<div id="integration-tab" />

<Accordion title="Integration tab">

Partner integrations differ in their requirements and can contain a subset of all possible options described in this section. There are some differences between iOS and Android settings.

![set_up_an_integrated_partner.png](https://files.readme.io/441ddfcd784a000099ae75acdb234d32bfe75ab598a34a88c7f9ed651fe8f7ec-15520850610449.png)

Complete the sections as required.

#### Integration sections

The following table includes different sections of the integration page. Some sections are available to all, others are specific per integration.

| Section | Description |
| --- | --- |
| <span id="a-activate-partner"></span>Activate partner | Before sharing attribution links with a partner, you must enable **Activate partner** and complete the remaining sections of the Integration tab.<ul><li>Don't use **Activate partner** to pause or turn off campaign attribution</li><li>Disabling partner integration **can cause irreversible damage to active campaigns**.</li><li>Learn more about [partner activation](/docs/partner-activation-deactivation) and the impact of deactivating a partner.</li></ul>**To activate an integrated partner**:<ol><li>In AppsFlyer, from the side menu, select**Collaborate**> **Partner Integrations**.</li><li>Search for and select the partner. You're directed to the partner configuration page.</li><li>Turn on [**Activate partner**](/docs/partner-activation-deactivation).</li><li>Click **Save Integration.**</li><li>[Optional] To allow the partner to [view the data attributed to them](/docs/manage-data-access-permissions), make sure to turn [Ad network permissions](/docs/set-up-an-integrated-partner#ad-network-permissions) in the [Permissions](/docs/set-up-an-integrated-partner#permissions-tab) tab.</li></ol> |
| <span id="b-advanced-privacy"></span>Advanced Privacy | For iOS apps only:  <br />When**Advanced Privacy (for iOS 14.5+ and later)** is turned on, you can [control what data to share](/docs/apply-aggregated-advanced-privacy-framework) with the partner via postbacks and reports. This limits the sharing of user identifiers with the partner. Note that when [Aggregated Advanced Privacy](/docs/apply-aggregated-advanced-privacy-framework) toggle is turned on in App Settings, **Advanced Privacy (for iOS 14.5+ and later)** is turned on and locked. |
| <span id="c-transaction-id"></span>Transaction ID | For iOS apps only:  <br />When **Share SKAN transaction ID** is turned on, you're [sharing the transaction ID of SKAdNetwork postbacks](/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners) with the partner. By doing so, the partner could decode your SKAdNetwork Conversion Values. |
| <span id="d-general-settings"></span>General settings | **Partner ID—Credentials**  <br />Some partners require credentials for AppsFlyer to integrate with them. Partners refer to this ID as app ID, account ID, user ID, or network ID. If this field displays, get the ID from the partner dashboard and enter it in the field. |
| <span id="non-eu-users"></span>Non EU Users | Decide whether or not to turn on [**Non EU users**](/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users). |
| <span id="e-install-attribution"></span>Install attribution | Set attribution windows to attribute new installs (first launches) of users who viewed or clicked your ad. The attribution lookback window is the maximum time from a click or a view of your ad to the install for which installs may be attributed to the partner.<ul><li>**Install click-through lookback window:** Set the maximum time after a click-to-app that an install can be attributed to the click.</li></ul>**Install view-through attribution: Turn on to start attributing new installs by users who viewed your ad but didn't click it.**<ul><li>**Install view-through lookback window:** Set the maximum time after a view-to-app that an install can be attributed to the view.</li></ul>[Learn more about lookback windows](/docs/set-up-lookback-windows). |
| <span id="e-re-engagement-attribution"></span>Re-engagement attribution | Turn on and set the lookback windows to start attributing re-engagements of your existing users. For non-SRNs, this setting is available either in the Integration tab or in the [attribution link](/docs/set-up-an-integrated-partner#retargeting-settings) tab.<ul><li>**Re-engagement click-through lookback window:** Set the maximum time after a click-to-app that the app launch can be attributed to the click as a re-engagement.</li></ul>**Re-engagement view-through attribution:** Turn on to start attributing re-engagements of your existing users who viewed your ad but didn't click it.<ul><li>**Re-engagement view-through lookback window:** Set the maximum time after a view-to-app that an app launch can be attributed to the view as a re-engagement.</li></ul>[Learn more about lookback windows](/docs/set-up-lookback-windows). |
| <span id="reengagement-window"></span>Re-engagement window | Set the time window during which in-app events are primarily attributed to the re-engagement conversion. [Learn more](/docs/retargeting-attribution-guide#setup-reengagement-window). |
| <span id="ignore-active-users"></span>Ignore active users for retargeting | Set an inactivity window period to prevent recording retargeting conversions for active users within the specified time frame. See more about the [Retargeting inactivity period](/docs/set-retargeting-inactivity-window).<br /><br />**For** [**SRNs**](/docs/self-reporting-networks-srns):<ol><li>From the Integration tab, turn on **Re-engagement attribution**.</li><li>Turn on **Ignore active users for retargeting**.</li><li>Set the **Inactivity window**.</li></ol>**For non-SRNs:**<ol><li>From the Attribution link tab, turn on **Retargeting settings**.</li><li>Turn on **Ignore active users for retargeting**.</li><li>Set the **Inactivity window**.</li></ol> |
| <span id="e-cross-platform-attribution"></span>Cross-platform attribution | When **Cross-platform equal attribution priority** is turned on, cross-platform impressions during the selected time frame have equal priority for attribution. |
| <span id="f-preload-attribution"></span>Preload attribution | When **Preload attribution** is turned on, installs are attributed to [preload campaigns](/docs/measure-preload-campaigns-with-google-play-install). Set the **Preload lookback window** to determine how long after device activation a preload install can be attributed to the partner. |
| <span id="f-preload-equal-attribution-priority"></span>Preload equal attribution priority | When **Preload equal attribution priority** is turned on, preload engagement during the selected lookback window has equal [attribution priority](/docs/appsflyer-attribution-model#attribution-methods) as deterministic clicks. |
| <span id="advanced-data-sharing"></span>Advanced Data Sharing | When **Advanced Data Sharing** is turned on, additional data is shared with the partner via the attribution link.  <br />**Note:** This sharing option is different from the [Meta ads AEM Advanced data sharing](/docs/meta-ads-aggregate-event-measurement-aem-for-ios#aem-data-sharing). |
| <span id="default-postbacks"></span>Default postbacks | When the partner integration is turned on, default postbacks are sent to partners relating to user actions occurring before the app launch, such as installs, rejected installs, and re-engagements.<br /><br /><br /><br />**<span id="01H80XGTBQ4MPGGKSZW0D9GG9H"></span>Note**<ul><li>Rejected events are in-app events blocked by [Protect360](/docs/protect360-anti-fraud-guide) or events found to be non-compliant by target validation. In the case of rejected events, confirm with the partner that they have enabled reject event integration with AppsFlyer.</li><li>Tech partners can receive Default postbacks for installs and re-engagements. In some cases, they can also receive in-app event postbacks.</li></ul>**To configure default postbacks for the partner**, define the source of users for sending postbacks:<ul><li>**This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner.<br />**Note:** In the following cases, default postbacks are always defined as **This partner only**:<ul><li>Rejected installs</li><li>Agencies (with [permissions](/docs/set-up-an-integrated-partner#agency-permissions))</li></ul></li><li>**All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, the user who performed it came from any media source.</li><li>**Off**: Don't send default postbacks to this partner.</li></ul> |
| <span id="g-in-app-event-postback-configuration"></span>[In-app event postbacks](/docs/in-app-event-postback-configuration) | [Map](/docs/in-app-event-postback-configuration#event-mapping) AppsFlyer events with the partner's events via postbacks. If postback sending is enabled, this includes rejected in-app events (events blocked by Protect360 or events found to be non-compliant with target validation rules).<br /><br />**To configure in-app event postbacks:**<ol><li>Set the **Partner ID** (if required).</li><li>Enable **In-app event postbacks**.</li><li>Set the **In-app event postback window**, if required (read more about [in-app event postback window configuration](/docs/in-app-event-postback-configuration#in-app-event-postback-window)).</li><li>Click **Add event** to add an SDK or server-to-server event to the list.</li><li>Complete the required parameters according to the [mapping method](/docs/in-app-event-postback-configuration#mapping-methods).</li><li>[Optional] Click![conditional-iae-postbacks-icon.png](https://files.readme.io/e2543cb26e0cc02f4840040721376ae88a4015a24ac1fc271264e3965560c1f9-4413022777105.png)to [set conditions](/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks) for sending certain in-app events to the partner.</li></ol><table><thead><tr><th>Parameter name</th><th>Description</th></tr></thead><tbody><tr><td><span id="appsflyer-event"></span>**AppsFlyer event**</td><td>The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events. **Tip**: Don't see the event you're looking for?   \* Make sure to activate the event on a device with a non-organic installation, and recheck. \* Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events)</td></tr><tr><td><span id="mapped-to-partner-event"></span>**mapped to partner event**</td><td>The unique name or ID of each event, as defined on the partner's side. [Possible mapping configurations](/docs/in-app-event-postback-configuration#mapping-methods) are:   \* **Text field:** Get the corresponding event ID from the partner. \* **Drop-down box:** Select the most suitable pre-defined partner event. \* **As is**: Send the events as they are, without mapping the event name.</td></tr><tr><td><span id="for-users-from"></span>**for users from**</td><td>Select the sending option for the event:   \* **This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner. \* **All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, when the user who performed it came from any media source.</td></tr><tr><td><span id="including"></span>**including**</td><td>Select [which event data](/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks) to share with the partner in the postback:   \* **No values & no revenue**: Send just the event itself without any parameters (values or revenue). \* **Values & no revenue**: Send all the parameters **excluding** the revenue value. \* **Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</td></tr></tbody></table><br />Remarks:<ul><li>Events mapped in the Integration tab for a specific partner are applicable both for standard and [SKAN postbacks](/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners).</li><li>Postbacks are sent to partners in real-time.</li><li>The AppsFlyer event name can either be selected or typed in.<br />Typed values are permitted to have underlined spaces (low dashes) before or after the name of the event. Use underlined spaces only if the event name being sent from AppsFlyer has the same underlined spaces.</li><li>**Important:** Event names are case-sensitive. To avoid discrepancies, make sure you use the correct event name for all media sources and app versions.</li><li>If the **In-app event postbacks** section doesn't exist in the **Integration** tab, it means that the partner has not yet set up in-app event recording with AppsFlyer in its preliminary configuration. The partner can contact AppsFlyer using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif) to finish the integration.</li><li>To prevent advertisers from sharing too much information with third-party platforms unintentionally, we have removed the **Send all events (excludes uninstalls, sessions, and af\_ad\_revenue)** option for third-party platforms, as of March 2019. Third-party platforms configured before this, still retain this setup option.</li></ul>Related reading:<ul><li>[In-app event postback](/docs/in-app-event-postback-configuration) configuration</li><li>[Ad revenue event postback](/docs/share-ad-revenue-data-with-partners#ad-revenue-event-postbacks-for-ad-networks) configuration</li></ul> |
| Parameter name | Description |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you're looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation, and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events)</li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. [Possible mapping configurations](/docs/in-app-event-postback-configuration#mapping-methods) are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined partner event.</li><li>**As is**: Send the events as they are, without mapping the event name.</li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner.</li><li>**All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, when the user who performed it came from any media source.</li></ul> |
| **including** | Select [which event data](/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks) to share with the partner in the postback:<ul><li>**No values & no revenue**: Send just the event itself without any parameters (values or revenue).</li><li>**Values & no revenue**: Send all the parameters **excluding** the revenue value.</li><li>**Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li></ul> |
| <span id="h"></span>Save integration | Click **Save Integration** after making the changes. |
| <span id="i-connect-more-apps-optional"></span>Connect more apps (optional) | After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner.<ol><li>From the top-left corner, under the partner name, click the app name to open the list of apps.</li><li>Select a different app from the drop-down list.</li><li>Repeat the integration steps for the selected app.</li></ol> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links for the use of click (non-SRN) ad networks, and send the attribution link to the partner to attribute specific campaigns, ad sets, or single ads.

**Note:** SRNs don't implement advertiser-generated attribution links so this tab isn't relevant to SRN campaigns.

**To generate an attribution link**:

1. Select either **Use a single-platform link** or **Use OneLink**.

   Select **Use a single-platform link** if any of the following apply:

   * You plan to use only [URI schemes](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page) to open the app.
   * You don't need to deep link with the URL.

   Select **Use OneLink** if any of the following apply:

   * You want a single link for both Android and iOS apps.
   * You want to use Android App Links or iOS Universal Links to open the app.
   * You want deep linking capabilities.

   **Note**: Selecting OneLink changes the click recording link from app specific to a [OneLink URL](/docs/onelink-guide).
2. If you selected **Use OneLink**:
   1. Select which OneLink template you want to use to open the app (and potentially deep link).
   2. [Optional] Enter the **Deep link value**.
   3. [Optional] Enter the **Additional deep link value**.
3. Add parameters for [Android](/docs/about-link-structure-and-parameters#android-specific-parameters) and [iOS](/docs/about-link-structure-and-parameters#ios-specific-parameters), as needed.
4. [Optional] Select additional attribution parameters.

#### Attribution link parameters

[![attribution-link-parameters-en_us.png](https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png)](https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png)

Adding parameters to the attribution link enables you to perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here. When saving the attribution link, all the parameters configured in this tab are saved.

Select which parameters you want to add to the attribution link.

#### Attribution link parameters

| Name | Description | Attribution link parameter |
| --- | --- | --- |
| Campaign | **Required parameter.**  <br />Compare different campaigns running with the media source. | c |
| Adset | Compare different ad sets within specific campaigns of the media source. | af\_adset |
| Ad Name | Compare different creatives within specific ad sets within specific campaigns of the media source. | af\_ad |
| Site ID and Sub Site ID | **Required parameter.**<br /><br />Set Site ID to attribute installs to specific publishers.<br /><br />The site ID must be passed to AppsFlyer in the attribution link because it:<ul><li>Provides clarity and transparency about the publisher</li><li>Is used by AppsFlyer to identify and eliminate fraudulent publishers, and other traffic clusters.</li></ul>Note that a missing Site ID won't affect attribution. Learn more about the [Site ID parameter](/docs/about-link-structure-and-parameters#site-id-parameter).<br /><br />If there are many publishers, we advise limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations. | af\_siteid and af\_sub\_siteid |
| Subscriber Parameters | Use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |

You can add other parameters to the attribution link by typing it in a new parameter box. You can use all [AppsFlyer available URL parameters.](/docs/about-link-structure-and-parameters) Note that only URI scheme and OneLink parameters are encoded on the attribution link.

#### Retargeting settings

**When retargeting is on**: AppsFlyer recognizes a link as a [retargeting](/docs/retargeting-attribution-guide) attribution link, rather than a user acquisition link, by adding the `&is_retargeting=true` to the attribution link.  
**Attribution link parameter:** is\_retargeting

To use your link for retargeting:

1. Turn on **Retargeting settings**.
2. [Optional] Enter a URI scheme if you want a URI scheme to open the app.  
   **Note**:
   * URI schemes are recommended as a fallback method to open the app if Universal Links or App Links fail.
   * If you add a URI scheme here, it overrides any other URI schemes already in your OneLink template settings.
   * URI scheme is added to the link in the af\_dp parameter.
3. [Optional] Turn on **Ignore active users for retargeting**.
4. Set the inactive window to determine which users are considered active and inactive.
5. Set the re-engagement window to determine the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source.
   * You can set the value in days (1-90), hours (up to 23), or even lifetime.
   * The re-engagement window is added to the link in the af\_reengagement\_window parameter.

#### Click-through attribution

Use the setting to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window are attributed.

Permitted range: 1-23 hours or 1-30 days.

**Attribution link parameter:** af\_click\_lookback

Learn more about the [click lookback window](/docs/set-up-lookback-windows).

**Click attribution link**

[![click-through-attribution-link_en-us.png](https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png)](https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png)

This is the attribution link that contains all the set up information you have set for it. You can save the link for future reference by clicking **Save attribution link**.

**To copy the click attribution link:**

1. Click **Save attribution link.**
2. Copy the generated link.

Send the link to the partner to be activated when your leads click on a corresponding ad.

#### View-through attribution lookback window

Set the **maximum time from impression to install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to the partner, providing there was no other relevant ad click.

You can customize this value to 1-24 hours.

**Attribution link parameter:** af\_viewthrough\_lookback

Learn more about [view-through attribution](/docs/set-up-lookback-windows).

**Impressions attribution link**

[![impressions-attribution-link_en-us.png](https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png)](https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png)

The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). You can save the link for future reference by clicking **Save attribution link**.

Click Save attribution link and then copy the generated link.

**To copy the impressions attribution link:**

1. Click **Save attribution link.**
2. Copy the generated link.

Send it to the partner to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

* Cost data is reported by your integrated partners on the click or by Cost API.
* The best practice is to implement Cost API (ROI360 subscription required).
* Cost API includes clicks and impressions reports. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features.

> 📘 **Note**
>
> If an advertiser uses an agency to run their campaigns, the agency, and not the advertiser, should integrate with the relevant partners. Otherwise, if both the advertiser and agency integrate with a partner using the same credentials for the same app, cost data is duplicated.

#### Enabling cost data by API

**To enable the cost API**:

* Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

#### Cost data sync status

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

If you act as a publisher displaying ads in your app, the ad revenue function enables you to attribute ad revenue to the media source that brought the user. [About ad revenue attribution.](/docs/roi360-guide-ad-revenue-attribution)

#### Enable ad revenue attribution

1. Check to see which method, [aggregate or user-level attribution](/docs/roi360-guide-ad-revenue-attribution#list-of-ad-revenue-integrated-partners), the partner supports.
2. Follow the appropriate method in the [ad revenue integration guide.](/docs/roi360-guide-ad-revenue-attribution#implementation)

#### Ad revenue API status messages

| Status | Remarks/action required |
| --- | --- |
| Active | The connection is live and pulling data. |
| No data to pull was found. | The connection was successful. The partner did not have any data related to this app. |
| Partner API not responding. Contact AppsFlyer support. | The partner's server isn't responding to AppsFlyer. |
| Invalid credentials. Enter updated credentials. |  |
| Something went wrong. Contact AppsFlyer support. | There is a technical problem. |
| Partner data not yet ready. If the problem persists, contact AppsFlyer support. |  |
| Data is being processed and will be available soon. | We are currently processing the data received from the partner. The data will be available in the dashboards and reports. |
| Data was never successfully pulled | If this status persists for a further hour contact AppsFlyer support. |

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Grant ad networks and agencies specific permissions to access your data and perform various actions.

* You don't need the integration with a partner to be turned on to grant them permissions.
* **Ad network set up by an agency:** When partner setup is performed by an agency, the advertiser can view neither the ad network activation status nor the permissions granted.
* If your association with the partner is solely as an agency, use the **Agency permissions** instead of the **Ad network permissions**. By turning on the Agency permissions toggle, you allow the agency to control the Ad network permissions. For more information, see the note in [What does it mean to get permission from a marketer](/appsflyer-partners/docs/getting-started-agency-onboarding#what-does-it-mean-to-get-permission-from-a-marketer).
* Permissions are granted for the currently selected app.

#### Ad network permissions

Turning on **Ad network permissions** allows the ad network access to your dashboard and enables granting additional permissions, as detailed in the table below.

> 📘 **Note**
>
> Any access permissions are restricted to data owned by the ad network.

**To grant permissions to an ad network and their team members:**

1. Turn on **Ad network permissions**.

   * Your app appears on the ad network's dashboard.
   * The ad network admin has permissions to [see basic data about the app.](/docs/manage-data-access-permissions)

   **Note:** Ad network team members are managed directly by the ad network. If you want a specific team member to have access, please contact your ad network. [Learn more](/appsflyer-partners/docs/user-management-for-ad-networks#creating-a-user)
2. Select additional permissions to grant to the ad network:

| **Permission** | **Capability granted** |
| --- | --- |
| <span id="configure-integration"></span>Configure integration | The ad network can change parameters in the integration tab, except for configuring in-app event postbacks. |
| <span id="configure-inapp-event-postbacks"></span>Configure in-app event postbacks | The ad network can configure in-app event postbacks. This means they can create, define (map), and change postback settings.<br /><br />**Caution**! When both this permission and **Configure integration** are enabled simultaneously, the ad network has access to all events. This includes organic traffic and non-organic traffic from all media sources. |
| <span id="access-retention-report"></span>Access retention and cohort reports | The ad network can access retention/cohort data created by the users brought by the ad network only. |
| <span id="access-aggregate-loyal-users-data"></span>Access aggregate loyal users data | The ad network can access its own [loyal users](/docs/about-a-loyal-user) metric. |
| <span id="access-aggregate-conversions-data"></span>Access aggregate conversions data | The ad network can access their aggregate conversion events metric reports. This includes installs, re-engagements, re-installs, and re-attributions. Example: [Aggregated campaign performance for ad networks report](/appsflyer-partners/docs/aggregated-campaign-performance-report-for-ad-networks). |
| <span id="access-aggregate-inapp-events-data"></span>Access aggregate in-app events data | The ad network can:<ul><li>Access in-app event data aggregate reports. The access includes all in-app events data of the selected app, including Protect360 in-app events data. This means they can access not just the events mapped in the postback configuration.</li><li>Access ad monetization data aggregate reports,  which may include ad monetization events from other media sources.</li></ul> |
| <span id="view-validation-rules"></span>View validation rules | The ad network can view [validation rule](/docs/implement-validation-rules-to-prevent-fraud) details. |
| <span id="access-aggregate-revenue-data"></span>Access aggregate revenue data | The ad network can access aggregate reports of in-app and ad revenue data attributed to users brought by the ad network. **Note:** This permission doesn't directly identify the ad revenue partner. However, if you've set the monetization event name to include the partner name, you may inadvertently disclose the identity of the monetization network. |
| <span id="use-ad-spend-ingestion"></span>Use ad spend ingestion | The ad network can:<ul><li>Access the [Ad Spend Ingestion](/docs/import-cost-data) window. This window displays only the apps they have permissions for.</li><li>Send ad spend files for ingestion.</li></ul> |
| <span id="access-protect360-dashboard-raw-data"></span>Access Protect360 dashboard & raw data | The ad network can:<ul><li>Access their Protect360 dashboard (including [ProtectLITE](/docs/basic-fraud-detection-and-insights-with-protectlite-dashboard-and-reporting)).</li><li>Access Protect360, Validation Rules, and raw data if they are part of the subscription plan. ProtectLITE doesn't include access to raw data.</li></ul>**Note:** When you have a [Protect360](/docs/protect360-anti-fraud-guide) subscription, the ad network can see the full dashboard. Without a Protect360 subscription, they can see the lite dashboard. |
| <span id="access-ad-revenue-raw-data"></span>Access ad revenue raw data | The ad network can access their [ad revenue data to use for UA optimization](/appsflyer-partners/docs/ad-revenue-signals-for-ua-ad-networks).   <br />**Note:** This permission is only available for apps with an [ROI360](/docs/roi360-cost-aggregation-overview?query=xpend) subscription. |

#### Agency permissions

Read all about [what agencies can do](/appsflyer-partners/docs/getting-started-agency-onboarding#what-does-it-mean-to-get-permission-from-a-marketer) when granted permissions.

> 📘 **Important!**
>
> When working with agencies, turning off an integrated partner does not automatically disable certain attribution capabilities for the agencies linked to that partner:
>
> To fully deactivate these capabilities for agencies, the advertiser must manually turn off the following settings before deactivating the partner:
>
> 1. Install view-through attribution
> 2. Cross-platform equal attribution priority
>
> Only after disabling these toggles should the advertiser proceed to deactivate the partner.
>
> **Note:** If the advertiser deactivates the partner without first turning off these settings, the agencies may continue to use these attribution capabilities.

**Caution:** Agency installs occurring while the control is disabled are not attributed to the agency and don't show up on the agency's dashboard and data. Learn more about [agency activation](/docs/partner-activation-deactivation#agency-permissions).

**To grant permissions to an agency:**

1. Turn on **Agency permissions**.
2. Select the permissions to grant to the agency:

| **Permission** | **Capability granted** |
| --- | --- |
| <span id="change-advanced-privacy-configuration"></span>Change Advanced Privacy configuration | The agency can change an ad network's[Advanced Privacy data sharing](/docs/apply-aggregated-advanced-privacy-framework) setting.   <br />**Note:** This permission isn't applicable to TikTok for Business and Snapchat. For these integrations, the Advanced Privacy setting is grayed out, reflecting the advertiser's setting. |
| <span id="access-retention-and-cohort-reports"></span>Access retention and cohort reports | The agency can access retention/cohort data created by the users brought by the agency only. |
| <span id="access-aggregate-organic-data"></span>Access aggregate organic data | The agency can access aggregate organic data |
| <span id="view-validation-rules::6872643b"></span>View validation rules | The agency can view validation rule details. |
| <span id="add-validation-rules"></span>Add validation rules | The agency can add and edit validation rules. Available when **View validation rules** is turned on.   <br />**Note**: Agencies can't edit rules created by advertisers. |
| <span id="access-rawdata-reports"></span>Access raw-data reports | The agency can access raw data reports for traffic attributed to the agency. Advertisers can't limit events an agency can view in the reports. |
| <span id="access-protect360-dashboard-raw-data::dd9829fd"></span>Access Protect360 dashboard & raw data | The agency can:<ul><li>Access your Protect360 aggregate dashboard</li><li>Access Protect360, Validation Rules, and raw data if they are part of the subscription plan</li></ul>**Note:** For advertisers that work with ad networks through an agency, in order for both the ad network and agency to access data, the advertiser must integrate both the agency and ad network in AppsFlyer and grant them both permission to access data. If only the agency is integrated and granted permission, the ad network does not have access to the data. |
| <span id="configure-inapp-event-postbacks::8743ba60"></span>Configure in-app event postbacks | The agency can configure in-app event postbacks of specific events you select:<ul><li>**Add event:** From the drop-down menu, select events you approve granting the agency permission.</li></ul>The following options apply to the events you selected:<ul><li>**Send events revenue:** When turned on, the agency can configure sending events including their monetary value.</li><li>**Sending option:**<ul><li>**This partner only:** When selected, the agency can configure sending postbacks only for events attributed to their own brought traffic</li><li>**All media sources, including organic:** When selected, the agency can configure sending postbacks for events attributed to all other media sources, agencies, and organic users.</li></ul></li></ul> |

Learn more about [working with agencies](/appsflyer-partners/docs/about-agency-accounts#agency-access-to-marketer-data).

</Accordion>

## Test the integration

After completing the partner integration, and before you start running campaigns with the newly added partner, it's important to test the integration. Mistakes are most likely to occur during setup. Testing in advance avoids the risk of spending considerable resources, only to discover your attribution data is missing or wrong. 

> 📘 **Note**
>
> Before testing the integration, make sure to first [test the app for basic SDK integration,](/docs/testing-the-sdk-integration-for-marketers) including organic and non-organic installs.

<div id="test-the-attribution-link-for-nonsrns" />

<Accordion title="Test the attribution link for non-SRNs">

Non-SRN ad networks, which consist of 99.5% of integrated ad networks, use AppsFlyer attribution links. Similarly, owned media attribution is performed by using AppsFlyer [OneLink links](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink).

Since correct attribution depends on the parameters of the attribution links, test these links before you start to run a campaign with a non-SRN ad network or a custom attribution link.

**To test attribution links:**

1. Create an [attribution link](/docs/set-up-an-integrated-partner#attribution-link-tab).
2. Send the new attribution link to your [registered](/docs/registering-test-devices) test device (via email or QR code).
3. Click on the link, make sure you're redirected to the app store.
4. Install the app.
5. Launch the app.
6. Check if the install appears in the AppsFlyer dashboard under the partner's media source name. Allow up to 30 minutes for the install to appear in the dashboard.
7. Drill down to the campaign level (by selecting the partner in the **Media source filter** on the top of the overview page) to check the install appears under the correct campaign name.
8. If necessary, continue to drill down and check the ad set and single ad levels too.

</Accordion>

<div id="test-the-srn-integration" />

<Accordion title="Test the SRN integration">

SRNs such as Meta ads, Apple Ads, and Google Ads don't rely on external attribution links for attribution purposes. Instead, SRNs receive queries from AppsFlyer, attribute themselves, and return the answer. Therefore, it isn't feasible to test the integration separately from the network's system as with regular ad networks. You must separately test the integration with each SRN you work with.

**To test SRN integration**[:](/docs/set-up-an-integrated-partner)

1. Perform the full SRN setup on AppsFlyer in accordance with the [specific SRN setup guide](/docs/self-reporting-networks-srns#srns-integrated-with-appsflyer).
2. Run a new low-budget campaign with the SRN partner.
3. When the partner dashboard displays new installs check if they appear in the AppsFlyer dashboard under the partner's media source name.
4. In the Overview dashboard, drill down to the campaign level, by selecting the partner in the **Media source filter**, to check that the install appears under the correct campaign name. Allow up to 30 minutes for the install to appear in the dashboard.
5. If necessary, continue to drill down to check the adset and single ad levels.

If all is well you can start running new high-budget campaigns with the partner. It is sufficient to test integration once per SRN partner. Meaning, there's no need to test on a per campaign basis.

</Accordion>

<div id="test-the-raw-data" />

<Accordion title="Test the raw data">

If your subscription plan with AppsFlyer includes access to raw data, you should test raw data.

**To test raw data**:

1. After performing the test mentioned previously, go to **Reports** > [**Export Data**](/docs/raw-data-reporting-overview).
2. Select the tested media source.
3. Allow up to 15 minutes from the install and then download the Installs report.
4. Check the install records from the partner exist and include parameters such as the media source, campaign name, touch time and type, device ID (if applicable), agency name (called "Partner" in the report), and so on.

> 📘 **Important!**
>
> Some ad networks require special actions to enable the collection of raw user-level data.
>
> If you see a new install on the dashboard but don't see it in the raw data, consult the specific Help Center guide for the ad network, for example - [X Ads](/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies#do-you-make-twitters-raw-data-available-to-agencies).

</Accordion>

<div data-zendesk-anchors="01H80XGTBQ6MAK3VG0X6QMAYMP=overview 01H80XGTBQPPZV7WR5JBHQFB0B=partner-types-in-the-ecosystem 01H80XGTBQ4CPMBRVSMM7TD4VD=partners-in-the-marketplace 01H80XGTBQRJ78XCGNZBTJVYEQ=invite-new-partners-to-appsflyer 01H80XGTBQ8VF6V9WARZRECWVR=your-integrated-partners 01H80XGTBQJQYD3R46H95WVVM0=note 01H80XGTBQ5BE24X219BVZBMDG=about-the-integrated-partner-page 01H80XGTBQPP74G38YNNYVXWP2=applicable-settings-tabs-per-partner-type set-up-a-partner-nonsrn=set-up-a-partner-non-srn 01H80XGTBQXNQ7SFXZ5PBQGS1V=set-up-a-partner-non-srn 01JDM949M75Q3BAG6M65DYMHZT=important 01H80XGTBQZXZARZCM61CMG0K3=note-1 01H80XGTBQB9T22GQ7CSHS2S1X=integration-tab integration-tab-sections=integration-sections 01H80XGTBQ0531M2RS3DH7E4Z0=integration-sections d-general%20settings=d-general-settings default%20postbacks=default-postbacks 01H80XGTBRT41FGP5107G96TWC=attribution-link-tab 01H80XGTBRPENCTCRK8PPYSCGX=attribution-link-parameters attribution-link-parameters::3874dfb8=attribution-link-parameters-1 01H80XGTBR8630SEV80K9RD6V9=attribution-link-parameters-1 01H80XGTBRT57QMPRENYSS81Z3=retargeting-settings clickthrough-attribution=click-through-attribution 01H80XGTBREZTJ6B0Y08JCKN1E=click-through-attribution viewthrough-attribution-lookback-window=view-through-attribution-lookback-window 01H80XGTBRXC1YYX4FW94NDR2Z=view-through-attribution-lookback-window 01H80XGTBRERTJ9XHGDV416T7V=cost-tab 01H80XGTBR54TQ0DNY1JR36GXN=note-2 01H80XGTBRV6BHWS76HWHK933M=enabling-cost-data-by-api 01H80XGTBRPWREFYFXA0A6VD47=cost-data-sync-status 01H80XGTBRJ1AKX2Q7WPXFVA49=ad-revenue-tab 01H80XGTBRHE9PPRA9X46M4TGZ=enable-ad-revenue-attribution 01H80XGTBRNT4K4ZNPKVV25ESJ=ad-revenue-api-status-messages 01H80XGTBRGXS97JMG45QR4BEQ=permissions-tab 01H80XGTBRS9BTT2F8F95BCE9Z=ad-network-permissions h_01HGFD78GRX9P2G58W21QZN4X7=note-3 01H80XGTBRTVP407AAA77N090E=agency-permissions h_01KC9MDDRPTB05PV6NCGZVFRMJ=important-1 01H80XGTBSEWPHCPQF29XD6Y4W=test-the-integration 01H80XGTBSTHG2FC2M31F83RGK=note-4 01H80XGTBS4P06757QXHDKYAHT=test-the-attribution-link-for-nonsrns 01H80XGTBS2K9SPQ1MTAV7GP2H=test-the-srn-integration 01H80XGTBSTBV4RC3V279WNNB1=test-the-raw-data 01H80XGTBSN0VAX76XW9Y77T04=important-2" />
