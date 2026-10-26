---
title: Aura from Unity campaign configuration
metadata:
  keywords:
    - Campaign
    - Advertisers
    - Agencies
    - aura
    - ironsource
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2020-01-27T11:23:49Z'
  edited_at: '2026-06-16T12:13:38Z'
  id: 360005208578
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360005208578-Aura-from-Unity-campaign-configuration
---
> **At a glance:** Aura from Unity, an AppsFlyer ad network integrated partner, is a platform that allows advertisers to connect with users when they set up a new device.

![aura_logo.png](https://files.readme.io/83bca93f3dfe8f6ce9bd74b9141b8c3b4dc01cfcf8f1904c0f992346beee5014-17313206447889.png)

## Aura from Unity integration in AppsFlyer

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

Connect to Aura from Unity by activating and setting parameters in the Integration tab.

**To configure the integration**:

1. Enable **Activate partner**.
2. Under **General settings** enable/disable **View-through attribution**:
   * [Default] **Enable**: Activate to attribute view-through installs to Aura from Unity . The lookback window is configured in the **Attribution link** tab.
   * **Disable**: View-through installs from the partner are not attributed.
3. **Default postbacks** are sent to Aura from Unity for:
   * **Installs**: Postbacks are sent every time a user installs the app. Choose if you want to send postbacks for users attributed to Aura from Unity or all users, including organic installs.
   * **Rejected installs**: With **Protect360**, postbacks are sent when an <Anchor target="_blank" href="/partners/docs/rejected-attribution-postbacks-to-integrated-partners">install is rejected due to fraud</Anchor>. Only users attributed to Aura from Unity are reported.
4. **In-app events settings**: To send postbacks, map your in-app event IDs to Aura from Unity's in-app IDs. Configure the parameters as follows:
   * Enable **In-app event postbacks**.
   * Sending option: Select if you want to send **Only events attributed to this partner** or **Events attributed to any partners**, including organic installs.
   * Click **Add event** to add an SDK event to the list. Complete the parameters described in the following table.

| Setting name | Description |
| --- | --- |
| SDK event name | Event name received by AppsFlyer from:<ul><li>SDK integrated into the app</li><li>Server-to-server events</li></ul>**Tip:** If a needed event isn't on the list, perform a non-organic installation on a device, then check again. |
| Partner event identifier | Unique event name or ID as defined by Aura from Unity.<br /><br />Choose an event name (from the drop-down list) that most closely matches the event. |
| Send revenue | [Default] **Not enabled:** sends all in-app parameters to Aura from Unity, except the revenue parameter (`af_revenue`).<br /><br />**Enabled**: sends all in-app parameters including, when available, the revenue amount. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>. **To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard. 

For the full list of partners supporting cost data <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">go here</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue attribution is not available for this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

You can give Aura from Unity permission to view information or configure changes in the integration. The type of permission varies according to the business relationship (ad network/ad agency) you have with Aura from Unity.

**Note!** It is possible to give Aura from Unity permissions even if there is no active integration with them.

<div id="ad-network-permissions" />

<Accordion title="Ad network permissions">

**To enable ad network permissions**:

1. Enable **Ad network permissions**.
2. Give Aura from Unity team members access to one or more of the following:
   * **Allow to configure integration**: Permit the partner to set up the integration tab (except in-app event postbacks).
   * **Allow to configure in-app event postbacks**: Permit the partner to map in-app event postbacks to itself on the integration tab.
   * **Allow access to your retention report**: Only permit access to the partner's own retention data.
   * **Allow access to your aggregate loyal user data**: Only permit access to the partner's own loyal user data.
   * **Allow access to your aggregate in-app events data***: O*nly permit access to the partner's own in-app events data.
   * **Allow access to your aggregate revenue data:** Only permit access to the revenue data attributed to the partner.
   * **Allow spend ingestion**: Permit the partner to upload ad spend data for this app.
   * **Allow access to your Protect360 dashboard**: Only to the partner's own **Protect360** data if the feature is enabled for the advertiser.

</Accordion>

</Accordion>

<div data-zendesk-anchors="aura-integration-in-appsflyer=aura-from-unity-integration-in-appsflyer h_01HKW9GGARZY4X1FAA6BD89K5N=aura-from-unity-integration-in-appsflyer h_01HKW9GGAR9CWWYGRH6C1EMFVM=integration-tab h_01HKW9GGAR9CVKH192FN4P9YND=attribution-link-tab h_01HKW9GGARNCSQ0TAV69550BS8=cost-tab h_01HKW9GGAR0TET4Q5284NHFM7R=ad-revenue-tab h_01HKW9GGAR5ZTPA9R49WN5P7P4=permissions-tab h_01HKW9GGAREEN9YQ065D1ZX1AQ=ad-network-permissions" />
