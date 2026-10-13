---
title: "Aura from Unity campaign configuration"
excerpt: "Aura from Unity, an AppsFlyer ad network integrated partner, is a platform that allows advertisers to connect with users when they set up a new device."
x-zendesk:
  id: 360005208578
  url: https://support.appsflyer.com/hc/en-us/articles/360005208578-Aura-from-Unity-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  position: 12
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Agencies]
  labels: [Campaign, Advertisers, Agencies, aura, ironsource, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2020-01-27T11:23:49Z'
  edited_at: '2026-06-16T12:13:38Z'
---
![aura_logo.png](https://files.readme.io/83bca93f3dfe8f6ce9bd74b9141b8c3b4dc01cfcf8f1904c0f992346beee5014-17313206447889.png)

## Aura from Unity integration in AppsFlyer

> 📘 Prerequisite
>
> An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

### Integration tab

Connect to Aura from Unity by activating and setting parameters in the Integration tab.

**To configure the integration**:

1. Enable **Activate partner**.
2. Under **General settings** enable/disable **View-through attribution**:
   - [Default] **Enable**: Activate to attribute view-through installs to Aura from Unity . The lookback window is configured in the **Attribution link** tab.
   - **Disable**: View-through installs from the partner are not attributed.
3. **Default postbacks** are sent to Aura from Unity for:
   - **Installs**: Postbacks are sent every time a user installs the app. Choose if you want to send postbacks for users attributed to Aura from Unity or all users, including organic installs.
   - **Rejected installs**: With **Protect360**, postbacks are sent when an [install is rejected due to fraud](/docs/rejected-attribution-postbacks-to-integrated-partners). Only users attributed to Aura from Unity are reported.
4. **In-app events settings**: To send postbacks, map your in-app event IDs to Aura from Unity's in-app IDs. Configure the parameters as follows:
   - Enable **In-app event postbacks**.
   - Sending option: Select if you want to send **Only events attributed to this partner** or **Events attributed to any partners**, including organic installs.
   - Click **Add event** to add an SDK event to the list. Complete the parameters described in the following table.

| Setting name | Description |
| --- | --- |
| SDK event name | Event name received by AppsFlyer from:<br />- SDK integrated into the app<br />- Server-to-server events<br />**Tip:** If a needed event isn't on the list, perform a non-organic installation on a device, then check again. |
| Partner event identifier | Unique event name or ID as defined by Aura from Unity.<br />Choose an event name (from the drop-down list) that most closely matches the event. |
| Send revenue | [Default] **Not enabled:** sends all in-app parameters to Aura from Unity, except the revenue parameter (`af_revenue`).<br />**Enabled**: sends all in-app parameters including, when available, the revenue amount. |

### Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide). [Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters). **To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

### Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

- Follow [these integration instructions](/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api).

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

For the full list of partners supporting cost data [go here](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api).

### Ad revenue tab

Ad revenue attribution is not available for this partner.

### Permissions tab

You can give Aura from Unity permission to view information or configure changes in the integration. The type of permission varies according to the business relationship (ad network/ad agency) you have with Aura from Unity.

> 🚧 Note!
>
> It is possible to give Aura from Unity permissions even if there is no active integration with them.

### Ad network permissions

**To enable ad network permissions**:

1. Enable **Ad network permissions**.
2. Give Aura from Unity team members access to one or more of the following:
   - **Allow to configure integration**: Permit the partner to set up the integration tab (except in-app event postbacks).
   - **Allow to configure in-app event postbacks**: Permit the partner to map in-app event postbacks to itself on the integration tab.
   - **Allow access to your retention report**: Only permit access to the partner's own retention data.
   - **Allow access to your aggregate loyal user data**: Only permit access to the partner's own loyal user data.
   - **Allow access to your aggregate in-app events data**: Only permit access to the partner's own in-app events data.
   - **Allow access to your aggregate revenue data**: Only permit access to the revenue data attributed to the partner.
   - **Allow spend ingestion**: Permit the partner to upload ad spend data for this app.
   - **Allow access to your Protect360 dashboard**: Only to the partner's own **Protect360** data if the feature is enabled for the advertiser.