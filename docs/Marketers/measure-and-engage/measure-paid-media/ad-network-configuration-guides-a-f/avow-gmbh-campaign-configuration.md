---
title: "Avow GmbH campaign configuration"
excerpt: "AVOW GmbH (avow1_int) is an integrated partner with both ad network and agency accounts, that allows advertisers to run User Acquisition campaigns on mobile devices. In addition to click-based mobile attribution, Avow GmbH also offers view-through attribution, which advertisers can record with AppsFlyer."
x-zendesk:
  id: 18523546870929
  url: https://support.appsflyer.com/hc/en-us/articles/18523546870929-Avow-GmbH-campaign-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  position: 13
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Agencies]
  labels: [Agencies, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2023-09-13T07:21:40Z'
  edited_at: '2026-06-16T12:14:26Z'
---
![avow_icon.png](https://files.readme.io/f6dc549357d6c7a6ddaec67752570484289529f85defaf0316ccd925868deab7-18523559800465.png)

## Activate partner

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

## Setting up Avow GmbH

The integration with Avow GmbH supports click-through and view-through attribution. The general configuration window includes the following tabs: Integration, Attribution link, Cost, Ad revenue, and Permissions. For Avow GmbH, the available tabs are Integration, Attribution link, and Permissions.

> 📘 Note
>
> * Some settings differ for iOS and Android devices
> * Learn more about [setting up partner integrations](/docs/set-up-an-integrated-partner)

### Integration tab

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

To configure the integration, you must first [turn on](/docs/amazon-ads-campaign-configuration#activate-partner) the **Activate partner** toggle. Learn more about [activating and deactivating partner integrations](/docs/partner-activation-deactivation#activating-a-partner).

#### Advanced Privacy

For iOS apps only: Your control over data shared with the partner via postbacks and [reports](/docs/about-raw-data-identifier-restrictions) depends on the **Advanced Privacy (for iOS 14.5+ and later)** toggle state:

| Advanced Privacy: On | Advanced Privacy: Off |
| --- | --- |
| Postbacks are sent only for events attributed to the partner | Postbacks are sent according to your configuration:<br />- **All media sources, including organic**<br />- **This partner only** |
| Postbacks are sent according to the [Advanced Privacy template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks) |  |
| [Aggregated and anonymous data](/docs/apply-aggregated-advanced-privacy-framework) is shared with the partner, meaning no user-level data (device ID) is shared. |  |

#### General settings

**token**

Add the verification token provided by the AVOW Specialist (AM/BDM).

#### Install attribution

To attribute view-through installs from Avow GmbH, turn on **Install view-through attribution** . The view-through lookback slider is available on the Attribution link tab (described below).

#### Default postbacks

Postbacks for installs and rejected installs are sent to this partner only.

#### In-app event settings

**token**

Add the verification token provided by the AVOW Specialist (AM/BDM).

#### In-app event postbacks

Configure mapping of in-app events with Avow GmbH events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<br />   - Make sure to activate the event on a device with a non-organic installation, and recheck.<br />   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<br />   - **Text field:** Get the corresponding event ID from the partner.<br />   - **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br />   - **As is**: Send the events as they are, without name mapping. |
| **for users from** | **This partner only:** In-app event postbacks are sent only for events attributed to this partner—meaning, the user who performed it came from this partner. |
| **including** | - **No data (default)**: Send only the event itself without any event values.<br />   - **Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).<br />   - **Values without revenue**: Send all the parameters **excluding** the revenue value. |

3. [Optional] Click the **Add condition**  ![conditional-iae-postbacks-icon.png](https://files.readme.io/ccd3619229eddf2c91979ab4b0531b95dc2fe1d8fffee5ba61ae965d68e9be99-18523570168081.png) icon to [set conditions](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) for an event.
4. Set the **In-app event postback window**, if required (read more about [in-app event postback window configuration](/docs/in-app-event-postback-configuration#inapp-event-postback-window)).
5. Click **Save integration**.
6. [Optional]After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
1. From the top-left corner, under the partner name, click the app name to open the list of apps.
2. Select a different app from the drop-down list.
3. Repeat the [integration steps](/docs/amazon-ads-campaign-configuration#integration-tab) for the selected app.

> 📘 Note
>
> For iOS apps only: Your control over data shared with the partner via postbacks and [reports](/docs/about-raw-data-identifier-restrictions) depends on the **Advanced Privacy (for iOS 14.5+ and later)** [toggle state](/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy).

### Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](/docs/onelink-guide). [Learn more about attribution link structure and parameters](/docs/about-link-structure-and-parameters). **To generate an attribution link,** follow [these instructions](/docs/set-up-an-integrated-partner#attribution-link-tab).

### Cost tab

Cost data isn't available for Avow GmbH.

### Ad revenue tab

Ad revenue isn't available for Avow GmbH.

### Permissions tab

Select which permissions to grant Avow GmbH to access your data and perform various actions.

> 📘 Note
>
> * When the integration is [deactivated](/docs/partner-activation-deactivation) while the Permissions toggle is still turned on, permissions remain granted.
> * Learn more about [granting permissions](/docs/set-up-an-integrated-partner#permissions-tab).