---
title: Persona.ly RTB campaign configuration
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
  created_at: '2023-09-20T07:13:43Z'
  edited_at: '2026-07-23T13:13:23Z'
  id: 18699025653265
  locale: en-us
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/18699025653265-Persona-ly-RTB-campaign-configuration
---
> **At a glance:** Persona.ly RTB (personalyrtb\_int), an AppsFlyer integrated partner, is a mobile-first DSP operating worldwide. Using proprietary bidder and machine-learning algorithms, Persona.ly offers transparent, performance-driven, highly targeted UA and retargeting solutions.

<Image alt="persona.ly_logo.png" src="https://files.readme.io/b0dacbdc4c2e884610a040b5049a1410a88214f8275320163764bcf09f90305b-18699636413969.png" width="234px" />

## Setting up Persona.ly RTB

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

The integration with Persona.ly RTB supports click-through and view-through attribution.  
The general configuration window includes the following tabs: Integration, Attribution link, Cost, Ad revenue, and Permissions. For Persona.ly RTB, the available tabs are Integration, Attribution link, Cost, and Permissions.

> 📘 **Note**
>
> * Some settings differ for iOS and Android devices
> * Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">setting up partner integrations</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

To configure the integration, you must first <Anchor target="_blank" href="/marketers/docs/amazon-ads-campaign-configuration#activate-partner">turn on</Anchor> the **Activate partner** toggle. Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation#activate-a-partner-integration">activating and deactivating partner integrations</Anchor>.

> 📘 **Note**
>
> As an all-install network, Persona.ly RTB prefers to receive postbacks for all new installs of your app from any source. To do so, select **All media sources, including organic** to send all install postbacks to Persona.ly RTB.

#### Advanced Privacy

For iOS apps only: Your control over data shared with the partner via postbacks and <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions">reports</Anchor> depends on the **Advanced Privacy (for iOS 14.5+ and later)** toggle state:

| Advanced Privacy: On | Advanced Privacy: Off |
| --- | --- |
| Postbacks are sent only for events attributed to the partner | Postbacks are sent according to your configuration:<ul><li>**All media sources, including organic**</li><li>**This partner only**</li></ul> |
| Postbacks are sent according to the <Anchor target="_blank" href="/partners/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Advanced Privacy template</Anchor> |  |
| <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">Aggregated and anonymous data</Anchor> is shared with the partner, meaning no user-level data (device ID) is shared. |  |

#### Transaction ID

For iOS apps only, when **Share SKAN transaction ID** is turned on, you're allowing AppsFlyer to <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">share the transaction ID of SKAdNetwork postbacks</Anchor> with Persona.ly RTB. By doing so, Persona.ly RTB could decode your SKAdNetwork Conversion Values.

#### Install attribution

To attribute view-through installs from Persona.ly RTB, turn on **Install view-through attribution**. The view-through lookback slider is available on the [Attribution link tab](#attribution-link-tab).

#### Default postbacks

Define the source of users for sending automatic postbacks to partners relating to user actions occurring before the app launch:

* For **Installs**, select one of the following:
  * **This partner only:** Send postbacks only when the install is attributed to this partner—meaning, the user who installed the app came from Persona.ly RTB.
  * **All media sources, including organic:** Send postbacks for installs attributed to any partner and for organic events—meaning, the user who installed the app came from any media source.
* For **Rejected installs** and **Re-engagements:** Postbacks are sent to Persona.ly RTB only.

#### In-app event postbacks

Configure mapping of in-app events with Persona.ly RTB events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation, and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#custom-events">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li><li>**As is**: Send the events as they are, without name mapping.</li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: Send postbacks only when this event is attributed to this partner.</li><li>**All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events.</li></ul> |
| **including** | <ul><li>**No data (default)**: Send only the event itself without any event values.</li><li>**Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: Send all the parameters **excluding** the revenue value.</li></ul> |

3. [Optional] Click the **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/c3a5830693fb1f7b48c4d44964365ec0f1da36884cef914e7ab2be011bc60044-18699057822865.png" width="30px" />icon to <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event.
4. Set the **In-app event postback window**, if required (read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#in-app-event-postback-window">in-app event postback window configuration</Anchor>).
5. Click **Save integration**.
6. [Optional]After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the <Anchor target="_blank" href="/marketers/docs/amazon-ads-campaign-configuration#integration-tab">integration steps</Anchor> for the selected app.

> 📘 **Note**
>
> For iOS apps only: Your control over data shared with the partner via postbacks and <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions">reports</Anchor> depends on the **Advanced Privacy (for iOS 14.5+ and later)** <Anchor target="_blank" href="/marketers/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">toggle state</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>. **To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

AppsFlyer gets cost details by API. See the <Anchor target="_blank" href="/marketers/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features. **Note**: Cost data requires an ROI360 subscription.

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue isn't available for Persona.ly RTB.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Select which <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">permissions to grant</Anchor> Persona.ly RTB to access your data and perform various actions.

> 📘 **Note**
>
> When the integration is <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">deactivated</Anchor> while the Permissions toggle is still turned on, permissions remain granted.

</Accordion>

<div data-zendesk-anchors="setting-up-amazon-dsp-integration=setting-up-personaly-rtb 01H88VAJH3VENKYVRQY5RXN63P=setting-up-personaly-rtb 01H88VAJH3BYZSXQGGZZJQ9N0C=note 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=activate-partner 01H88VAJH34GP7FK1KTJGRDPM7=activate-partner h_01HBB9EEMJ55BQDJ1ZEJT136ZF=note-1 01H88VAJH3G5FAR7RRNDEPNGME=advanced-privacy h_01HARQDVEDA206D0BBXBC6WEHH=transaction-id h_01HA6PNN6RJYTNXRAS3M9EA4M4=install-attribution 01H88VAJH3WE9Z0971WMBRBJRS=default-postbacks inapp-event-postbacks=in-app-event-postbacks 01H88VAJH3AS37MVF75GANWX4B=in-app-event-postbacks 01H88VAJH36MYZ9W1YPWA92Z1Z=note-2 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=note-3" />
