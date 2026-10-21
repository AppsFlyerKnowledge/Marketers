---
title: Bidease campaign configuration
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-13T13:17:18Z'
  edited_at: '2026-09-09T12:48:03Z'
  id: 20106343354129
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/20106343354129-Bidease-campaign-configuration
---
**At a glance:** Bidease (bidease\_int), an AppsFlyer integrated partner, is a fully transparent DSP for mobile marketers. Using proprietary programmatic advertising technology, machine learning, and first-party data, Bidease optimizes campaigns across all major mobile formats for desired post-install behaviors at no risk to their clients.

<Image alt="bidease.png" src="https://files.readme.io/4a3373c0fdb73190017601c374ca7634cc0feb1954b6e23fc1bd9693c60605f9-20106376017041.png" width="100px" />

## Setting up Bidease

The integration with Bidease supports click-through and view-through attribution.

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

The general configuration window includes the following tabs: Integration, Attribution link, Cost, Ad revenue, and Permissions. For Bidease, the available tabs are Integration, Attribution link, and Permissions.

> 📘 **Note**
>
> * Some settings differ for iOS and Android devices
> * Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">setting up partner integrations</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

Turn on the **Activate partner** toggle.  
**Note:** The toggle **must stay on (active) as long as you work with the partner.**

#### Advanced Privacy

**For iOS apps only:** Your control over data shared with the partner via postbacks and <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions">reports</Anchor> depends on the **Advanced Privacy (for iOS 14.5+ and later)** toggle state:

| Advanced Privacy: On | Advanced Privacy: Off |
| --- | --- |
| Postbacks are sent only for events attributed to the partner | Postbacks are sent according to your configuration:<ul><li>**All media sources, including organic**</li><li>**This partner only**</li></ul> |
| Postbacks are sent according to the <Anchor target="_blank" href="/partners/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Advanced Privacy template</Anchor> |  |
| <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">Aggregated and anonymous data</Anchor> is shared with the partner, meaning no user-level data (device ID) is shared. |  |

#### Transaction ID

**For iOS apps only:** When **Share SKAN transaction ID** is turned on, you're allowing AppsFlyer to <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">share the transaction ID of SKAdNetwork postbacks</Anchor> with Bidease. By doing so, Bidease could decode your SKAdNetwork Conversion Values.

#### Install attribution

To attribute view-through installs from Bidease, turn on **Install view-through attribution**. The view-through lookback slider is available on the [Attribution link tab](#attribution-link-tab).

#### Default postbacks

Define the source of users for sending automatic postbacks to partners relating to user actions occurring before the app launch:

* For **Installs**, select either of the following:
  * **This partner only:** Send postbacks only when the install is attributed to this partner—meaning, the user who installed the app came from Bidease.
  * **All media sources, including organic:** Send postbacks for installs attributed to any partner and for organic events—meaning, the user who installed the app came from any media source.
* For **Rejected installs** and **Re-engagements:** Postbacks are sent to Bidease only.

#### In-app event postbacks

Set the **In-app event postback window**, as required (read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#in-app-event-postback-window">in-app event postback window configuration</Anchor>).

Configure mapping of in-app events with Bidease events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation, and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#custom-events">custom event mapping.</Anchor></li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: Send postbacks only when this event is attributed to this partner.</li><li>**All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events.</li></ul> |
| **including** | <ul><li>**No data (default)**: Send only the event itself without any event values.</li><li>**Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: Send all the parameters **excluding** the revenue value.</li></ul> |

3. [Optional] Click the **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/f5a35c6e26ceef82e2850f5ff40c5985a48de5de57baed289e8cd05aac5427c1-20106422231953.png" width="30px" />icon to <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event.
4. Click **Save integration**.
5. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the <Anchor target="_blank" href="/marketers/docs/amazon-ads-campaign-configuration#integration-tab">integration steps</Anchor> for the selected app.

> 📘 **Note**
>
> **For iOS apps only:** Your control over data shared with the partner via postbacks and <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions">reports</Anchor> depends on the **Advanced Privacy (for iOS 14.5+ and later)** <Anchor target="_blank" href="/marketers/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">toggle state</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>.

**To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

<Anchor target="_blank" href="/marketers/docs/roi360-guide-cost-and-revenue-data">Cost data</Anchor> isn't available for Bidease.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

<Anchor target="_blank" href="/marketers/docs/roi360-guide-ad-revenue-attribution">Ad revenue</Anchor> isn't available for Bidease.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Select which <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">permissions you're granting</Anchor> Bidease to access your data and perform various actions.

> 📘 **Note**
>
> When the integration is <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">deactivated</Anchor> while the Permissions toggle is still turned on, permissions remain granted.

</Accordion>

<div data-zendesk-anchors="h_01HF4ED4B5QHY92B03426260QY=setting-up-bidease h_01HF4DWFAP55JRXTR8Z65YAR68=note h_01HF4DWFAP4S45241VR1PJ3RFC=integration-tab activate-partner::b746d215=activate-partner h_01HF4DWFAP9BS1G612WS5HNQ6S=activate-partner h_01HF4DWFAQHEJATJG6DRVMKA34=advanced-privacy h_01HF4DWFAQ1Y1AVQ0EV63H5YJ1=transaction-id h_01HF4DWFAQQRR8XH5S7NW2NCB6=install-attribution h_01HF4DWFAQG4YEEH3HMD61GEWE=default-postbacks inapp-event-postbacks=in-app-event-postbacks h_01HF4DWFAQQCM4TK3JJNMSM6RD=in-app-event-postbacks h_01HF4DWFAQQ3C7GBA4Q4SA6G0Y=note-1 h_01HF4DWFAQ9D9BV6PG4BEYX788=attribution-link-tab h_01HF4DWFAQT2PD4863N6EB7HHH=cost-tab h_01HF4DWFAQXMNDHWT0Y4C0M6EN=ad-revenue-tab h_01HF4DWFAQJWNFMFDEZ8XT0DM5=permissions-tab h_01HF4DWFAQJ9HRMD1FE717F1WK=note-2" />
