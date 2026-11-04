---
title: Pinterest—Create a mobile app integration
metadata:
  keywords:
    - Pinterest
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-11-09T12:51:03Z'
  edited_at: '2026-09-09T13:05:01Z'
  id: 216912786
  locale: en-us
  section: Pinterest
  section_id: 6551388216337
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/216912786-Pinterest-Create-a-mobile-app-integration
---
> **At a glance:** Pinterest, an AppsFlyer integrated partner, is one of the top contributors of traffic for bloggers and brands. Pinterest offers both click-based and view-through mobile attribution. In addition, Pinterest also offers click-based retargeting which you can record with AppsFlyer.

<div id="note" />

> 📘 **Note**
>
> * After accepting Pinterest Ad Terms, accept Pinterest Mobile Measurement Terms & Conditions <Anchor target="_blank" href="https://ads.pinterest.com/terms/app_install/">here</Anchor>.
> * Pinterest requires attribution providers to delete their user-level data <Anchor target="_blank" href="/marketers/docs/user-level-data-retention#partner-data-retention-periods">6 months after the install</Anchor>. This means that the events performed by these users 6 months after they install the app are counted as organic. Past aggregate data remains the same.
> * Effective September 4, 2023, Pinterest requires attribution providers to <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions#media-source-restrictions">restrict the availability of some fields in raw data reports</Anchor> to preserve user privacy and ensure regulation compliance.

<div id="set-up-pinterest" />

## Set up Pinterest

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

<div id="activate-partner" />

### Activate partner

On the **first visit**, you will need to turn on the **Activate Partner** button to enable setup of the integration tab's parameters. The toggle must be on for as long as you work with the partner.  
For more details about partner activation click <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">here</Anchor>.

<div id="general-settings" />

### General settings

The following are the general settings for the integration tab of Pinterest.

**Enable View-Through attribution**

Turn this on if you want to attribute view-through installs from Pinterest. The view-through lookback slider is available on the attribution link tab (described below).

**Advanced Matching data sharing**

Turn this on to share Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, and hashed last name, with Pinterest, if these fields are included in the event information sent to AppsFlyer. For more information, see: <Anchor target="_blank" href="/marketers/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor>.

<div id="in-app-events-settings" />

### In-app events settings

To be able to send in-app event postbacks to Pinterest, you must provide the following Pinterest credentials. These credentials will be included in the event postbacks sent to Pinterest.

* **Ad account ID** - The unique identifier of your Pinterest account.
* **Access token** - An access token generated in Pinterest.

You can find your Ad Account ID and Access Token directly within the Pinterest Ad Manager UI (See the [Pinterest documentation](https://developers.pinterest.com/docs/api-features/tracking-conversions/#getting-your-access-token-and-ad-account-id)).  Please reach out to the Pinterest team if assistance is needed.

**Set the Pinterest credentials:**

1. In AppsFlyer, in the Pinterest **Active integration** page > **Integration** tab, scroll to **In-app event settings.**
2. Enter the Ad account ID and Access token values in their respective fields.

<div id="legacy-set-tag-id" />

#### [Legacy] Set Tag ID

**To get the Tag ID and set in-app event postbacks:**

1. In your Pinterest Business Account, go to Ads > Conversions and copy the Tag ID.  
   If you don't have a tag yet, click Create Tag and complete the creation process. Copy the new tag.
2. In AppsFlyer, in the Pinterest **Active integration** page > **Integration** tab, scroll to **In-app event settings** and enter the Pinterest Tag ID.

<div id="in-app-event-postbacks" />

### In-app event postbacks

In this section, you can map your AppsFlyer events with Pinterest via postbacks.

1. In AppsFlyer, in the Pinterest integration settings, scroll to **In-app event postbacks.**
2. Turn on **In-App Event Postbacks**.
3. Set the in-app event postback window.
4. Select the postback settings and mappings for events.

| Parameter Name | Description |
| --- | --- |
| <span id="appsflyer-event-name"></span>**AppsFlyer event name** | The name of the event, as received by AppsFlyer, either from the SDK integrated with your app or from server-to-server events.   <br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| <span id="partner-event-name"></span>**Partner event name** | The unique name of the event, as defined on Pinterest's side. For the Pinterest event names, see the <Anchor target="_blank" href="https://developers.pinterest.com/docs/api-features/track-conversion-events/#understand-conversion-events">Pinterest documentation.</Anchor> |
| <span id="to-users-from"></span>**To users from** | <ul><li>**This partner only:** For events coming **only** from users attributed to this partner.</li><li>**All media sources including organic:** To have your entire user base available to be reported to the partner.</li></ul> |
| <span id="including"></span>**Including** | Select if event revenue or parameter values are sent to the partner in the postback, or if this data isn’t included.<br /><br />AppsFlyer can send all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter. Or, AppsFlyer can send all the parameters including the revenue value (if it exists in the event). |

5. Click **Add Event** to add an SDK Event to the list.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

<div id="attribution-link-for-retargeting-campaign" />

#### Attribution link for retargeting campaign

Pinterest advises using OS-specific attribution links for retargeting campaigns. Select the **Use a single-platform link** option and add the necessary parameters to the retargeting attribution link.

<div id="deep-link-url" />

#### Deep Link URL

<div id="note-1" />

> 📘 **Note**
>
> Deep linking from within a pin will work correctly only when your app is allowlisted by Pinterest. Contact your Pinterest representative or email [apps@pinterest.com](mailto:apps@pinterest.com) to be allowlisted for deep linking.

Use this field if the link is meant to deep link users to any specific activity within your app.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Once you set Pinterest's cost, don't change the name of any running campaign, ad set, or single ad, nor use dynamic macros with the campaign name parameter, as they may cause serious discrepancies or missing cost data.

<div id="enabling-and-testing-pinterest-integration" />

### Enabling and testing Pinterest integration

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<div id="cost-data-sync-status" />

### Cost data sync status

<Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

<div id="stop-pinterest-cost-sync" />

### Stop Pinterest cost sync

**To delete a connected account:**

* <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">In the actions column, hover over an account, click ***Delete connection***</Anchor>. Once deleted, AppsFlyer stops getting the cost. Deleting the connection doesn't impact historical data.

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue data is not supported by this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant Pinterest. Note that even if attribution is disabled for Pinterest, the permissions tab is active and you can grant control to Pinterest.

Learn more about the <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">permissions you can grant Pinterest</Anchor>.

</Accordion>

</Accordion>

<div id="troubleshooting" />

## Troubleshooting

Cost tab error message: *No matching data* means that the Pinterest account that you connected to AppsFlyer is not the correct Pinterest account. No data was found that matches the app. You should log in to Pinterest with different credentials

<div data-zendesk-anchors="h_01H95QTA3ZZ9GJW9EN1VZ01TH2=note h_01H95QTA3Z5HXW39AHAF8FMFWH=set-up-pinterest h_01H95QTA3ZNQWBRA86E6TRQ46Y=integration-tab h_01H95QTA3ZGEM34HY1A7NC8NX7=activate-partner h_01H95QTA3Z0NW9V51D8J7MHEX0=general-settings inapp-events-settings=in-app-events-settings h_01JTDP2T0BFP5WP03X5EMXVAWA=in-app-events-settings %5Blegacy%5D-set-tag-id=legacy-set-tag-id h_01JTMX6DD0G101KC0HQ0D34S48=legacy-set-tag-id inapp-event-postbacks=in-app-event-postbacks h_01JTDP2T0BTW986GN5HSWPR3JH=in-app-event-postbacks h_01H95QTA3ZT7PVGAJW5AKPC186=attribution-link-tab attribution-link-for-retargeting-campaigns=attribution-link-for-retargeting-campaign h_01H95QTA3ZPQZ422AB2JBZAS07=attribution-link-for-retargeting-campaign h_01H95QTA3ZT23CYTCE2V3728MD=deep-link-url h_01H95QTA3ZYHQED2T5B2FA5PV8=note-1 h_01H95QTA3Z3XJDM5YRXFK7DA0E=cost-tab h_01H95QTA3ZZ56R8EZBJY1ESX5W=enabling-and-testing-pinterest-integration h_01H95QTA3ZST8WS3TAR79H06FM=cost-data-sync-status h_01H95QTA3ZFCJ82E3YDMP7S716=stop-pinterest-cost-sync h_01H95QTA3ZM2REWR2A5DHK1DSA=ad-revenue-tab h_01H95QTA3ZM4WPHV3MB00WZXSB=permissions-tab h_01H95QTA3ZP20DSJQGY4QQX0Z7=troubleshooting" />
