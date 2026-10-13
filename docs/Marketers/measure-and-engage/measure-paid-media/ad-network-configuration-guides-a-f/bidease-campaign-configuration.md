---
title: "Bidease campaign configuration"
excerpt: "Bidease (bidease_int), an AppsFlyer integrated partner, is a fully transparent DSP for mobile marketers. Using proprietary programmatic advertising technology, machine learning, and first-party data, Bidease optimizes campaigns across all major mobile formats for desired post-install behaviors at no risk to their clients."
x-zendesk:
  id: 20106343354129
  url: https://support.appsflyer.com/hc/en-us/articles/20106343354129-Bidease-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  position: 15
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2023-11-13T13:17:18Z'
  edited_at: '2026-09-09T12:48:03Z'
---
![bidease.png](https://files.readme.io/4a3373c0fdb73190017601c374ca7634cc0feb1954b6e23fc1bd9693c60605f9-20106376017041.png)

## Setting up Bidease

The integration with Bidease supports click-through and view-through attribution.

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

The general configuration window includes the following tabs: Integration, Attribution link, Cost, Ad revenue, and Permissions. For Bidease, the available tabs are Integration, Attribution link, and Permissions.

> 📘 Note
>
> - Some settings differ for iOS and Android devices
> - Learn more about [setting up partner integrations](/docs/set-up-an-integrated-partner)

### Integration tab

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

Turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle **must stay on (active) as long as you work with the partner.**

#### Advanced Privacy

**For iOS apps only:** Your control over data shared with the partner via postbacks and [reports](/docs/about-raw-data-identifier-restrictions) depends on the **Advanced Privacy (for iOS 14.5+ and later)** toggle state:

| Advanced Privacy: On | Advanced Privacy: Off |
| --- | --- |
| Postbacks are sent only for events attributed to the partner | Postbacks are sent according to your configuration:<br />- **All media sources, including organic**<br />- **This partner only** |
| Postbacks are sent according to the [Advanced Privacy template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks) |  |
| [Aggregated and anonymous data](/docs/apply-aggregated-advanced-privacy-framework) is shared with the partner, meaning no user-level data (device ID) is shared. |  |

#### Transaction ID

**For iOS apps only:** When **Share SKAN transaction ID** is turned on, you're allowing AppsFlyer to [share the transaction ID of SKAdNetwork postbacks](/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners) with Bidease. By doing so, Bidease could decode your SKAdNetwork Conversion Values.

#### Install attribution

To attribute view-through installs from Bidease, turn on **Install view-through attribution**. The view-through lookback slider is available on the [Attribution link tab](/docs/bidease-campaign-configuration#attribution-link-tab).

#### Default postbacks

Define the source of users for sending automatic postbacks to partners relating to user actions occurring before the app launch:

- For **Installs**, select either of the following:
  - **This partner only:** Send postbacks only when the install is attributed to this partner—meaning, the user who installed the app came from Bidease.
  - **All media sources, including organic:** Send postbacks for installs attributed to any partner and for organic events—meaning, the user who installed the app came from any media source.
- For **Rejected installs** and **Re-engagements:** Postbacks are sent to Bidease only.

#### In-app event postbacks

Set the **In-app event postback window**, as required (read more about [in-app event postback window configuration](/docs/in-app-event-postback-configuration#inapp-event-postback-window)).

Configure mapping of in-app events with Bidease events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<br />   - Make sure to activate the event on a device with a non-organic installation, and recheck.<br />   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **for users from** | Select the sending option for the event:<br />   - **This partner only**: Send postbacks only when this event is attributed to this partner.<br />   - **All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events. |
| **including** | - **No data (default)**: Send only the event itself without any event values.<br />   - **Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).<br />   - **Values without revenue**: Send all the parameters **excluding** the revenue value. |

3. [Optional] Click the **Add condition** ![conditional-iae-postbacks-icon.png](https://files.readme.io/f5a35c6e26ceef82e2850f5ff40c5985a48de5de57baed289e8cd05aac5427c1-20106422231953.png) icon to [set conditions](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) for an event.
4. Click **Save integration**.
5. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
1. From the top-left corner, under the partner name, click the app name to open the list of apps.
2. Select a different app from the drop-down list.
3. Repeat the [integration steps](/docs/amazon-ads-campaign-configuration#integration-tab) for the selected app.

> 📘 Note
>
> **For iOS apps only:** Your control over data shared with the partner via postbacks and [reports](/docs/about-raw-data-identifier-restrictions) depends on the **Advanced Privacy (for iOS 14.5+ and later)** [toggle state](/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy).

### Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide). [Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters).

**To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

### Cost tab

Cost data isn't available for Bidease.

### Ad revenue tab

Ad revenue isn't available for Bidease.

### Permissions tab

Select which [permissions you're granting](/docs/set-up-an-integrated-partner#permissions-tab) Bidease to access your data and perform various actions.

> 📘 Note
>
> When the integration is [deactivated](/docs/partner-activation-deactivation) while the Permissions toggle is still turned on, permissions remain granted.