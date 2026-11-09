---
title: VK Ads (myTarget, Mail.ru) campaign configuration
metadata:
  keywords:
    - mytarget
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-28T11:53:13Z'
  edited_at: '2026-10-13T01:14:31Z'
  id: 209731913
  locale: ko
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ko/articles/209731913
---
> **At a glance:** VK Ads is a mobile advertising platform aimed at connecting advertisers with Russian-speaking mobile users. With VK Ads advertisers can place targeted advertising in social networks (Vkontakte, Odnoklassniki, Moi Mir) and the Mail.Ru Group. In addition to click-based mobile attribution, VK Ads also offers retargeting attribution.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mail.ru.png?v=1" />

## Setting up VK Ads

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

### Activate partners

On the **first visit** here, you will need to toggle ON the ***Activate Partner*** button to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.  
For more details about partner activation please click <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">here</Anchor>.

### General settings

The following general settings are available for VK Ads.

### App ID

This field is not mandatory, and its functionality is TBD. For any further questions, contact VK Ads.

### Enable view-through attribution

Activate, if you want to attribute view-through installs from VK Ads. The view-through lookback slider is available in the [***Attribution link***](/docs/vk-ads-mytarget-mail-ru-campaign-configuration#attribution-link-tab) tab.

### Default postbacks

Send automatic postbacks to VK Ads following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to VK Ads.  
Select **Events attributed to any partner or organic** to have your entire user base available to be reported to VK Ads.

### In-app events postbacks

In this section, you can configure in-app event postbacks that are sent to VK Ads.

1. Activate ***In-app event postbacks***
2. Choose whether to report **selected events** to the partner, or **all** of them.
   * Note: If you choose to report all events, the *af\_app\_opened* event is not reported.
3. If you choose to manually select events, click ***Add event*** to add an SDK Event to the list.
4. Complete the following parameters:

| Parameter name | Description |
| --- | --- |
| **SDK event name** *(required for manual selection only)* | The name of the event, as received by AppsFlyer either from the SDK or from server-to-server events.  <br />**Tip**: If you don't see the event you want in the list, activate this event on a device with a non-organic installation and recheck. |
| **Sending option** | Select the sending option for the event:  <br />**This partner only** for events coming **only** from users attributed to VK Ads.  <br />**All sources, including organic** to have your entire user base available to be reported to the partner |
| **Send event data** | <ul><li>**No values & no revenue:** sends only the event itself without the event value.</li><li>**Values & no revenue:** sends all the parameters excluding the revenue value.</li><li>**Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event).</li></ul> |

5. Click ***Save***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

**Note**: OneLinks are not supported by VK Ads. Use standard attribution links for retargeting.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">these integration instructions</Anchor>.

<div id="cost-data-sync-status" />

<Accordion title="Cost data sync status">

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="removing-connected-accounts" />

<Accordion title="Removing connected accounts">

**To delete a connected account:**

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">In the actions column, hover over an account, click ***Delete connection***</Anchor>

</Accordion>

> 📘 **Notes**
>
> 1. To support cost with VK Ads the advertiser must add the Campaign ID to the link **af\_c\_id=**.
> 2. Once you set VK Ads cost, do not change the name of any active campaign, asset, or single ad, nor use dynamic macros with the campaign name parameter, as they can cause serious discrepancies or missing cost data.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue data is not supported by VK Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant VK Ads, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for VK Ads, the permissions tab is active and you can grant control to VK Ads.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

* ***Allow to configure integration*** - permit the partner to set up the integration tab (except in-app event postbacks)
* ***Allow to configure in-app event postbacks*** - permit the partner to set up in-app event postbacks mapping to itself on the integration tab
* ***Allow access to your retention report*** - only to the partner's own retention data
* ***Allow access to your aggregate loyal user data*** - only to the partner's own loyal user data
* ***Allow access to your aggregate in-app events data** -* only to the partner's own in-app events data
* ***Allow access to your aggregate revenue dat*a** - only to the revenue data attributed to the partner
* ***Allow access to your Protect360 dashboard*** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJZV9DR3A3W91BQCE2548M0P=setting-up-vk-ads h_01HJZV9DR31B2EW88NG57XV2WH=integration-tab h_01HJZV9DR4A51AC03J82BMH8R0=activate-partners h_01HJZV9DR4WXN4985B5YYHN065=general-settings h_01HJZV9DR4RDFCE9FF8P61H5G7=app-id enable-viewthrough-attribution=enable-view-through-attribution h_01HJZV9DR4EFADPVTYYRT4ZYZD=enable-view-through-attribution h_01HJZV9DR408AXGRVRBV6KK9CJ=default-postbacks inapp-events-postbacks=in-app-events-postbacks h_01HJZV9DR43RZ5W4B71SASKY42=in-app-events-postbacks h_01HJZV9DR47N1SFC26DHT4BCCE=attribution-link-tab h_01HJZV9DR4G92S9CZZW3JE5HTS=cost-tab h_01HJZV9DR47Q48ZTJVK1M5DDM8=cost-data-sync-status h_01HJZV9DR5SHYA20GE711S6VT5=removing-connected-accounts h_01HJZV9DR5Q8W34HW2GRWCCMEB=notes h_01HJZV9DR5696R8NE7R5YYZ2JB=ad-revenue-tab h_01HJZV9DR5YQH7HF32M8R1YBKZ=permissions-tab" />
