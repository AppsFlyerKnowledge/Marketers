---
title: "Vungle campaign configuration"
excerpt: "Learn how to configure Vungle integration in AppsFlyer to measure mobile attribution, cost, and view-through data."
---
Vungle, an AppsFlyer ad network integrated partner, offers an in-app video advertising platform for performance marketers. In addition to click-based mobile attribution, Vungle offers cost and view-through attribution, which can be recorded with AppsFlyer.

## Setting up Vungle

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

   ( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Important
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

> 👍 Tip
>
> - The [General Settings](https://support.appsflyer.com/hc/articles/4410395957521#d-general%20settings) step in the Integration tab is **mandatory** for all partners
> - All the rest of the steps are either descriptive or **optional**

### Integration tab

The Integration tab is divided into different sections as described below.

### Activate partners

Connect to Vungle by activating and setting parameters in the integration tab. Vungle must supply its unique network ID, _**app\_id**_; this is necessary in order to connect with AppsFlyer.

> 📘 Note
>
> As an all-installs network, Vungle prefers to receive postbacks for all new installs of your app from any source, and they recommend selecting **All media sources, including organic** to send all install postbacks to Vungle.

**To configure the integration**:

1. Enable _**Activate partner**_. See more information about [partner activation](https://support.appsflyer.com/hc/articles/360000844778).
2. **Under _General settings_ enable/disable _View-through attribution_:**
   - [Default] **Enable**: Activate to attribute view-through installs to Vungle. The length of the lookback window is configured in the Attribution link tab.
   - **Disable**: View-through installs from the partner are not attributed.
3. _**Default postbacks**_: Send postbacks to Vungle after user installs and re-engagements. Use this section to define users who are the source of these postbacks. Under _**Sending Option**_,
   - Select **Only events attributed to this partner** for events attributed to Vungle users.
   - Select **Events attributed to any partner or organic** to make your entire user available for reporting to Vungle.
4. **_In-app events settings_**: To send postbacks to Vungle, map in-app event IDs to Vungle’s. Configure the parameters as follows:
   - Enter the Vungle app\_id.
   - Enable **_In-app events postbacks_**.
   - Select a _**Sending Option**_.
   - Click **_Add event_** to add an SDK event to the list. Complete the parameters as described in the following table.

| Parameter Name | Description |
| --- | --- |
| **SDK event name** | Event name received by AppsFlyer from:<br>- SDK integrated in the app<br>- Server-to-server events<br>**Tip:** If a needed event isn’t on the list, perform a non-organic installation on a device, then check again. |
| **Partner event identifier** | Unique event name or ID as defined by Vungle.<br>Get from Vungleevent ID corresponding to your SDK event and insert it in the text field. |
| **Send revenue** | [Default] **Not enabled:** sends all the in-app parameters to Vungle, except for the revenue parameter (`af_revenue`).<br>**Enabled**: sends all the in-app parameters including, when available, the revenue amount. |

### Attribution link tab

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a [OneLink](https://support.appsflyer.com/hc/articles/115005248543-OneLink-overview).

[Learn more about attribution link structure and parameters](https://support.appsflyer.com/hc/articles/207447163).

**To generate an attribution link,** follow [these instructions](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab).

### Cost tab

AppsFlyer gets cost details by API. See the [ad network cost integration table](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

- Follow [these integration instructions](https://support.appsflyer.com/hc/articles/360008850257#enable-cost-api).

[View your cost API status](https://support.appsflyer.com/hc/articles/360008850257#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

### Ad revenue tab

This section is relevant if you are acting as a publisher, displaying ads of the partner to your users. As such, you would certainly like to measure the engagement of your users acquired from different sources, to find the most profitable sources for you.

**To enable the ad revenue API**:

- Follow [these integration instructions](https://support.appsflyer.com/hc/articles/217490046-Ad-revenue-attribution-guide#connect-to-ad-revenue-integrated-partners).

### Permissions tab

You can give Vungle permission to view information or configure changes in the integration. The type of permission varies according to the business relationship (ad network/ad agency) you have with Vungle.

> 📘 Note
>
> It is possible to give Vungle permissions even if there is no active integration with them.

### Ad network permissions

**To enable ad-network permissions:**

1. Enable _**Ad network permissions**_.
2. Give Vungle team members access to one or more of the following:

| Permission | Description |
| --- | --- |
| **Allow to configure integration** | Set up the integration tab (except in-app event postbacks). |
| **Allow to configure in-app event postbacks** | Set up in-app event postbacks that are mapped to Integration tab. |
| **Allow access to your retention report** | Partner’s retention data |
| **Allow access to your aggregate loyal users data** | Partner’s loyal-user data |
| **Allow access to your aggregate in-app events data** | Partner’s in-app events data |
| **Allow access to your aggregate revenue data** | Revenue data attributed to the partner. |
| **Allow spend ingestion** | Enable spend ingestion |
| **Allow access to your Protect360 dashboard** | [If enabled] Partner’s Protect360 data |

Learn more about giving [ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab).

### Agency permissions

You can allow Vungle to configure your app as an agency.

**To enable agency permissions:**

1. Enable _**Agency**_ **permissions**.
2. Give Vungle agency access to one or more of the following:

| Permission | Description |
| --- | --- |
| **Allow access to your Protect360 dashboard** | [If enabled for your account] Agency’s Protect360 data |
| **Allow access to your retention and cohort reports** | Agency’s retention and cohort data |
| **Allow access to aggregate organic data** | Agency’s aggregate organic data |
| **Allow to configure in-app event postbacks** | Set up in-app event postbacks that are mapped to the integration tab. |

Learn more about granting [agency permissions](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions).