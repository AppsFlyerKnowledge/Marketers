---
title: RZR (formerly Aarki) campaign configuration
metadata:
  keywords:
    - Advertisers
    - aarki
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-03-12T06:15:54Z'
  edited_at: '2026-10-13T01:08:18Z'
  id: 360000423105
  locale: zh-cn
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/zh-cn/articles/360000423105
---
> **At a glance:** RZR, an AppsFlyer ad network integrated partner, is a well-known mobile DSP. RZR offers both click-based and view-through mobile attribution. In addition, RZR also offers click-based retargeting which you can record with AppsFlyer.

<Image align="center" alt="RZR Logo Horizontal gradient black wordmark (3).png" src="https://files.readme.io/b1064bdec0e836399c583c3f55e5e79a81380a9a8d86eeaee19391b6d09f2bbd-small-46161100230545.png" width="58.83%" />

## Setting up RZR

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/zh/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partner

<span id="01ECJ9TJKEFXN53XDEBJ5Z92SS"></span>On the **first visit**, you will need to toggle ON the ***Activate Partner*** button to enable setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner. For more details about partner activation please click <Anchor target="_blank" href="/marketers/zh/docs/user-level-data-retention"><span id="01ECJ9TJKFY5Q8P4QS57HD44T3"></span>here</Anchor>.

> 📘 **Note**
>
> As an ALL-Installs network, RZR prefers to receive postbacks for all new installs of your app from ANY source, including organic. It is recommended to select **Events attributed to any partner** to send all install postbacks to RZR.

### General settings

<span id="01ECJ9TJKF9QBT98Z7XJM3H8F1"></span>**Partner ID**

<span id="01ECJ9TJKF6R5F2K8VGMR7KFHN"></span>RZR connects with AppsFlyer via a unique network ID. If you don't already have the Network ID, you must obtain it from RZR to continue with the integration.

<span id="01ECJ9TJKFZN0WVXXS0B89CMBY"></span>**Enable View-Through attribution**

<span id="01ECJ9TJKFE4E8GZQ2EN3Z1SM4"></span>Toggle this to ON if you want to attribute view-through installs from RZR. The view-through lookback slider is available on the attribution link tab (described below).

### Default postbacks

<span id="01ECJ9TJKFT13WB1T328ET3PGC"></span>Send automatic postbacks to RZR following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

<span id="01ECJ9TJKFQH37DQZ3V3NAESRF"></span>Select **Only events attributed to this partner** for events coming only from users attributed to RZR. Select **Events attributed to any partner or organic** to have your entire user base available to be reported to RZR.

### In-app events settings

<span id="01ECJ9TJKF6QKF23NRTA5VS8Y9"></span>In this section you can map your AppsFlyer events with RZR via postbacks.

**To configure in-app event postbacks:**

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation, and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#自定义事件">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li><li>**As is**: Send the events as they are, without name mapping.</li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: Send postbacks only when this event is attributed to this partner.</li><li>**All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events.</li></ul> |
| **including** | <ul><li>**No data (default)**: Send only the event itself without any event values.</li><li>**Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: Send all the parameters **excluding** the revenue value.</li></ul> |

3. [Optional] Click the **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />icon to <Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#带条件的应用内事件回传">set conditions</Anchor> for an event.
4. Click **Save integration**.
5. [Optional]After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the <Anchor target="_blank" href="/marketers/zh/docs/amazon-ads-campaign-configuration#integration-tab">integration steps</Anchor> for the selected app.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

<span id="01ECSMR3VTP3SVSP9YXGW526PA"></span>In this tab, you can create the attribution links you want to send to RZR for attributing RZR's campaigns, ad sets or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

<span id="01ECJ9TJKFTGNEZ68AR6DGXJNA"></span>This tab is divided into different sections:

### Attribution link parameters

<span id="01ECJ9TJKFJRJ2BYN069CK80C8"></span>In this section, select which parameters you want to add to the attribution link.

<span id="01ECJ9TJKG144FJ8R72S2XDKQS"></span>Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

* <span id="01ECJ9TJKGTPN4NF8CC66XBRRS"></span>**<span id="01ECJ9TJKGZP0D1TYCB5R8XJ80"></span>Campaign** - add it to compare different campaigns running with Aarki. **Attribution link parameter:** c
* <span id="01ECJ9TJKGSVH0XGW2R8HRDA4T"></span>**Adset** - set ad set names to compare different ad sets within specific Aarki campaigns. **Attribution link parameter:** af\_adset
* <span id="01ECJ9TJKGC25XCE8GEB04ZE0P"></span>**Ad Name** - set ad set names to compare different creatives within specific ad sets within specific campaigns Aarki. **Attribution link parameter:** af\_ad
* <span id="01ECJ9TJKGWG1QBKJ9MVW4Q5FG"></span>**Site ID** and **Sub Site ID** - set Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise on limiting the number of used site IDs and using the sub site ID parameter, to avoid <Anchor target="_blank" href="/marketers/zh/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit"><span id="01ECJ9TJKGEPHEXZ60NAN9JPWG"></span>exceeding the site ID</Anchor> limitations. **Attribution link parameters:** af\_siteid and af\_sub\_siteid
* <span id="01ECJ9TJKGQPS0GAY5SY562VFS"></span>**Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering. **Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<span id="01ECJ9TJKGQN0Y1H6F2WNHRBCV"></span>Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">**<span id="01ECJ9TJKG3AQCMW2FDDZ7HWWB"></span>about AppsFlyer's Attribution Link Structure and Parameters**</Anchor>.

### Retargeting settings

<span id="01ECJ9TJKG820HKXXZTS89ES65"></span>When enabled, AppsFlyer recognizes a link as a <Anchor target="_blank" href="/marketers/zh/docs/retargeting-attribution-guide"><span id="01ECJ9TJKGRTSNR53S5XX76K61"></span>retargeting</Anchor> attribution link, rather than a user acquisition link, by adding the &is\_retargeting=true to the click recording link. Note that retargeting is currently only supported for click-through and not view-through attribution.**Attribution link parameter:** is\_retargeting.

<span id="01ECJ9TJKGPRH6P36208EH0C44"></span>The following setup below is displayed when retargeting is enabled.

<span id="01ECJ9TJKH63B6KS5WE93F0SMM"></span>1. Standard Link vs. OneLink

<span id="01ECJ9TJKHH7YZCNS0P0TT0B45"></span>Select ***standard attribution link*** option if:

* <span id="01ECJ9TJKHCZFTSWGGC2XHW6N5"></span><span id="01ECJ9TJKHP90T48TJPV80AP2T"></span>You don't need to deep link with the URL or
* <span id="01ECJ9TJKHYPT6RQ5NTVPV8FA2"></span>Plan to use only <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page"><span id="01ECSNC07ND552HVWJD2GF8YSD"></span>URI schemes</Anchor> for deep linking

<span id="01ECJ9TJKH6GTCN390D87MYPHV"></span>Select ***Use OneLink*** for:

* <span id="01ECJ9TJKHVJCE2XM6X6AJS4YY"></span><span id="01ECJ9TJKHSJAC8HW8YERAKDVC"></span>Using a single link for both Android and iOS apps or
* <span id="01ECJ9TJKH0W7PXF4EJKM20ZRQ"></span>Deep linking using Universal or app links

<span id="01ECJ9TJKHEDATPHFM1EN5NZFQ"></span>Note that selecting OneLink changes the click recording link from app specific to a <Anchor target="_blank" href="/marketers/zh/docs/onelink-guide"><span id="01ECJ9TJKHQTEYP3PPXHVWYF9V"></span>OneLink URL</Anchor>.

<span id="01ECJ9TJKH59CKTD3ZNMZ37W09"></span>2. Deep Link URL

<span id="01ECJ9TJKHKQMJFN1Z3G7JTN5V"></span>Use this field if the link is meant to deep link users to any specific activity within your app.**Attribution link parameter:** af\_dp You can find more information about AppsFlyer's <Anchor target="_blank" href="/marketers/zh/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink"><span id="01ECJ9TJKHK7S19JDRMS3Z318C"></span>deep linking solution in this guide.</Anchor>

<span id="01ECJ9TJKH1QVW9NG1P4JY165N"></span>3. Re-engagement Window

<span id="01ECJ9TJKHAZ5N1Y7NACJPMT4S"></span>Set the time period following the re-engagement, where the user's in-app events are attributed to the retargeting media source. You can set the value in days (1-90), hours (up to 23), or even lifetime.

<span id="01ECJ9TJKH449C02X1Y3ESR48Y"></span>**Attribution link parameter:** af\_reengagement\_window

### Click-through attribution

<span id="01ECJ9TJKHGWANE9EGZZ0KKEX9"></span>This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to RZR.

<span id="01ECJ9TJKHF1JQM37P7SAYP8G6"></span>**Attribution link parameter:** af\_click\_lookback

<span id="01ECJ9TJKHY557S7J91YTE5VH8"></span>More details about the <Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows"><span id="01ECJ9TJKHWEDC7RP2ZHHPFDNV"></span>click lookback window here</Anchor>.

### Click attribution link

<span id="01ECJ9TJKJ6TJBPEP5JNEPYTVB"></span>This is the attribution link that contains all the setup information you have set for it. Send it to RZR to be activated when leads click on a corresponding ad.

### View-through attribution lookback window

<span id="01ECJ9TJKJVDX13ZVFH8T5BVG7"></span>This slider allows you to set the **maximum time from impression to install**. Only installs (first launches) that occur within this lookback window following an ad impression are attributed to RZR, provided there was no other relevant ad click.

<span id="01ECJ9TJKJ1JEA3HME63V9EWA0"></span>You can customize this value to 1-23 hours or 1-7 days.

<span id="01ECJ9TJKJB20VJH63A8NK3KGB"></span>**Attribution link parameter:** af\_viewthrough\_lookback

<span id="01ECJ9TJKJNTQ7AJVYKVWYMJNZ"></span>More details about the <Anchor target="_blank" href="/marketers/zh/docs/set-up-lookback-windows"><span id="01ECJ9TJKJX8GHDCAW0QQYD4BV"></span>view-through attribution here</Anchor>.

### Impressions attribution link

<span id="01ECJ9TJKJ34K4MSK1BK687Q9Y"></span>The impression attribution link contains similar attribution data to the click recording link (besides the different lookback window). Send it to RZR to be activated when a corresponding ad is watched, usually for 1 second or more.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/zh/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/zh/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api状态">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard. 

#### Warning

<span id="01ECJ9TJKQX7K80360QJ9RACV1"></span>Once you set RZR cost do not change the name of any running campaign, ad set or single ad as it may cause serious discrepancies or missing cost data.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

<span id="01ECJ9TJKQNQBY77FTTFRZ0PGS"></span>Ad Revenue data is not supported by RZR.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

<span id="01ECJ9TJKQ8FK7KPD84RHW11HQ"></span>In this tab, you can select the permissions to grant RZR, whether the partner acts as an ad network, agency or even both. Note that even if attribution is disabled for RZR, the permissions tab is active and you can grant control to RZR.

<span id="01ECJ9TJKQFJM45QTAMC6AJQW3"></span>Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* <span id="01ECJ9TJKQAHY9CZ2H3W09GQPZ"></span>***<span id="01ECJ9TJKQXT4HNE0HKH13F4SX"></span>Allow to configure integration*** - permit the partner to setup the integration tab (except in-app event postbacks)
* <span id="01ECJ9TJKQKZVDT6A960BMPW5Q"></span>***Allow to configure in-app event postbacks*** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* <span id="01ECJ9TJKQYN16W3C8YYFM14XP"></span>***Allow access to your retention report*** - only to the partner's own retention data
* <span id="01ECJ9TJKQQSP4G7H71AZBQMXW"></span>***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* <span id="01ECJ9TJKQXG55YJGYJV9AZFNH"></span>***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* <span id="01ECJ9TJKQ9809CG0G2QK43RGQ"></span>***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* <span id="01ECJ9TJKQZJGSVZMKFDHE2ACJ"></span>***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

<span id="01ECJ9TJKQJ0Y1QQK4EM92C06V"></span>Learn more about granting <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#permissions-tab"><span id="01ECJ9TJKQZ5ADC4QSTHP0KN95"></span>ad network permissions</Anchor>.

<div id="01ECJ9TJKRMD549KXA59E682CH" />

### Agency permissions

<span id="01ECJ9TJKRNETK1FH4ZRSNE1V4"></span>Use these toggles to give the agency permissions to handle its own configuration for your app:

* <span id="01ECJ9TJKRADJZ8B7KNZH0HSQQ"></span>***<span id="01ECJ9TJKR3ZRZX5W0KD91BFV3"></span>Main toggle*** - Set to On to reveal the agency permissions options
* <span id="01ECJ9TJKRMQDVQV6EJAEC8DPG"></span>***Allow to configure in-app event postbacks*** - permit the agency to setup in-app event postbacks mapping to itself on the integration tab
* <span id="01ECJ9TJKRF7NMH6E1NDZ57S0E"></span>***Allow access to aggregate organic data***
* <span id="01ECJ9TJKRKVWZG0WYVK1533A9"></span>***Allow access to your retention report*** - only to the agency's own retention data

<span id="01ECJ9TJKRS878CPXQYSBAJCA1"></span>Learn more about granting <Anchor target="_blank" href="/marketers/zh/docs/set-up-an-integrated-partner#代理权限">agency permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-aarki=setting-up-rzr h_01HJR5M5C0P759S4X5SSJCY501=setting-up-rzr h_01J4KVYPZMZWJKV6KZQHNBZV0T=integration-tab 01ECJ9TJKE15MJE7WS26VP52A0=activate-partner h_01J4KWRE6ECKEWEG4WP10N3BF7=note 01ECJ9TJKFGQQVWA7SA3PRS690=general-settings 01ECJ9TJKF7G9KMGMGMAD414ZF=default-postbacks inapp-events-settings=in-app-events-settings 01ECJ9TJKFWH38NKYPDEZR4FRV=in-app-events-settings h_01J4KVYPZMF0CZMR1PTS97JNNJ=attribution-link-tab 01ECJ9TJKFD91X9DQXB8PV3840=attribution-link-parameters 01ECJ9TJKGJF1FS642MEM6WX4A=retargeting-settings clickthrough-attribution=click-through-attribution 01ECJ9TJKHWMXAZYWNMVPDS8NY=click-through-attribution 01ECJ9TJKJ0EQE45TB9S0WS2ZB=click-attribution-link viewthrough-attribution-lookback-window=view-through-attribution-lookback-window 01ECJ9TJKJ72AN26F2FQ8VVKQ4=view-through-attribution-lookback-window 01ECJ9TJKJZV9PADNEETA6GFRZ=impressions-attribution-link h_01J4KVYPZMEDPXBXYFVT85AJ67=cost-tab 01ECJ9TJKQ8A7BFZR3MJ5H35CA=warning h_01J4KVYPZMQHGHDPEE1Q5M1KX8=ad-revenue-tab h_01J4KVYPZMRFMNCR61M4Z4388Y=permissions-tab 01ECJ9TJKQ9E3A5863Z3TRVAWZ=ad-network-permissions 01ECJ9TJKQ0SAV4ZJB8DFRTE5C=agency-permissions" />
