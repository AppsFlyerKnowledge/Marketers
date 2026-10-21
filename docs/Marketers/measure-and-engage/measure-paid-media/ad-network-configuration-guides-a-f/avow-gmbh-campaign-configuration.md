---
title: Avow GmbH campaign configuration
metadata:
  keywords:
    - Agencies
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
  created_at: '2023-09-13T07:21:40Z'
  edited_at: '2026-06-16T12:14:26Z'
  id: 18523546870929
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/18523546870929-Avow-GmbH-campaign-configuration
---
**At a glance:** AVOW GmbH (avow1\_int) is an integrated partner with both ad network and agency accounts, that allows advertisers to run User Acquisition campaigns on mobile devices. In addition to click-based mobile attribution, Avow GmbH also offers view-through attribution, which advertisers can record with AppsFlyer.

![avow_icon.png](https://files.readme.io/f6dc549357d6c7a6ddaec67752570484289529f85defaf0316ccd925868deab7-18523559800465.png)

## Activate partner

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

## Setting up Avow GmbH

The integration with Avow GmbH supports click-through and view-through attribution. The general configuration window includes the following tabs: Integration, Attribution link, Cost, Ad revenue, and Permissions. For Avow GmbH, the available tabs are Integration, Attribution link, and Permissions.

> 📘 **Note**
>
> * Some settings differ for iOS and Android devices
> * Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">setting up partner integrations</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

To configure the integration, you must first <Anchor target="_blank" href="/marketers/docs/amazon-ads-campaign-configuration#activate-partner">turn on</Anchor> the **Activate partner** toggle. Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation#activate-a-partner-integration">activating and deactivating partner integrations</Anchor>.

#### Advanced Privacy

For iOS apps only: Your control over data shared with the partner via postbacks and <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions">reports</Anchor> depends on the **Advanced Privacy (for iOS 14.5+ and later)** toggle state:

| Advanced Privacy: On | Advanced Privacy: Off |
| --- | --- |
| Postbacks are sent only for events attributed to the partner | Postbacks are sent according to your configuration:<ul><li>**All media sources, including organic**</li><li>**This partner only**</li></ul> |
| Postbacks are sent according to the <Anchor target="_blank" href="/partners/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Advanced Privacy template</Anchor> |  |
| <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">Aggregated and anonymous data</Anchor> is shared with the partner, meaning no user-level data (device ID) is shared. |  |

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
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation, and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#custom-events">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li><li>**As is**: Send the events as they are, without name mapping.</li></ul> |
| **for users from** | **This partner only:** In-app event postbacks are sent only for events attributed to this partner—meaning, the user who performed it came from this partner. |
| **including** | <ul><li>**No data (default)**: Send only the event itself without any event values.</li><li>**Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: Send all the parameters **excluding** the revenue value.</li></ul> |

3. [Optional] Click the **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/ccd3619229eddf2c91979ab4b0531b95dc2fe1d8fffee5ba61ae965d68e9be99-18523570168081.png" width="30px" />icon to <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event.
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

Cost data isn't available for Avow GmbH.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue isn't available for Avow GmbH.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Select which permissions to grant Avow GmbH to access your data and perform various actions.

> 📘 **Note**
>
> * When the integration is <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">deactivated</Anchor> while the Permissions toggle is still turned on, permissions remain granted.
> * Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">granting permissions</Anchor>.

</Accordion>

<div data-zendesk-anchors="01H88VAJH3B5ESK12D3ATMMVZ8=activate-partner setting-up-amazon-dsp-integration=setting-up-avow-gmbh 01H88VAJH3VENKYVRQY5RXN63P=setting-up-avow-gmbh 01H88VAJH3BYZSXQGGZZJQ9N0C=note 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=activate-partner-1 01H88VAJH34GP7FK1KTJGRDPM7=activate-partner-1 01H88VAJH3G5FAR7RRNDEPNGME=advanced-privacy 01H88VAJH3F2FJK5YP3M2V7RWD=general-settings h_01HA6PNN6RJYTNXRAS3M9EA4M4=install-attribution 01H88VAJH3WE9Z0971WMBRBJRS=default-postbacks inapp-event-settings=in-app-event-settings h_01HA79D908WB6G9FFDKDJNVHEM=in-app-event-settings inapp-event-postbacks=in-app-event-postbacks 01H88VAJH3AS37MVF75GANWX4B=in-app-event-postbacks 01H88VAJH36MYZ9W1YPWA92Z1Z=note-1 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=note-2" />
