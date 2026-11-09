---
title: Awin campaign configuration
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
  created_at: '2023-09-13T11:50:38Z'
  edited_at: '2026-09-09T12:39:48Z'
  id: 18532554968849
  locale: en-us
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/18532554968849-Awin-campaign-configuration
---
> **At a glance:** Awin (affiliatewindow\_int) is an integrated partner that allows advertisers to run UA and retargeting campaigns. Awin's marketing platform helps connect merchants (advertisers) with affiliates (publishers).

<Image align="center" alt="awin icon.png" src="https://files.readme.io/2a7f22084586fec820c0bfab7f3a256259c43d37f14d6fed8e8db3d2e9905947-18533392495377.png" />

## Activate partner

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

## Setting up Awin

The integration with Awin supports click-through attribution.

The general configuration window includes the following tabs: Integration, Attribution link, Cost, Ad revenue, and Permissions. For Awin, the available tabs are Integration, Attribution link, and Permissions.

> 📘 **Note**
>
> * Some settings differ for iOS and Android devices
> * Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">setting up partner integrations</Anchor>

### Prerequisite

Before setting up the integration, make sure to implement the required "commission group" parameters in the SDK, as specified in <Anchor target="_blank" href="https://help.awin.com/docs/appsflyer">Awin documentation</Anchor>.

<div id="integration-tab" />

<Accordion title="Integration tab">

The **Integration** tab includes a number of sections, as described below.

#### Activate partner

To configure the integration, you must first <Anchor target="_blank" href="/marketers/vi/docs/amazon-ads-campaign-configuration#kích-hoạt-đối-tác">turn on</Anchor> the **Activate partner** toggle. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation#activate-a-partner-integration">activating and deactivating partner integrations</Anchor>. For additional information, you can reference the <Anchor target="_blank" href="https://developer.awin.com/docs/appsflyer">Awin integration page</Anchor>.

#### Advanced Privacy

For iOS apps only: Your control over data shared with the partner via postbacks and <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">reports</Anchor> depends on the **Advanced Privacy (for iOS 14.5+ and later)** toggle state:

| Advanced Privacy: On | Advanced Privacy: Off |
| --- | --- |
| Postbacks are sent only for events attributed to the partner | Postbacks are sent according to your configuration:<ul><li>**All media sources, including organic**</li><li>**This partner only**</li></ul> |
| Postbacks are sent according to the <Anchor target="_blank" href="/partners/vi/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Advanced Privacy template</Anchor> |  |
| <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Aggregated and anonymous data</Anchor> is shared with the partner, meaning no user-level data (device ID) is shared. |  |

#### General settings

**Awin advertiser ID**

Add your Awin advertiser (or merchant) ID.

> 📘 **Note**
>
> An advertiser ID identifies your advertiser account on the partner’s side and is necessary for AppsFlyer attribution and postbacks. The ID must appear in the attribution link.

#### Default postbacks

Install postbacks are sent to this partner only.

#### In-app event settings

**Awin advertiser ID**

Add your Awin merchant ID.

#### In-app event postbacks

Configure mapping of in-app events with Awin events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation, and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li><li>**As is**: Send the events as they are, without name mapping.</li></ul> |
| **for users from** | **This partner only:** You can send in-app event postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner. |
| **including** | <ul><li>**No data (default)**: Send only the event itself without any event values.</li><li>**Values and revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: Send all the parameters **excluding** the revenue value.</li></ul> |

3. [Optional] Click the **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/c95f88d3e2fce153d0a04390fcbca5dabdb97f93ee700f0d69feb568169fddf0-18532570767761.png" width="30px" />icon to <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event.
4. Set the **In-app event postback window**, if required (read more about <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#in-app-event-postback-window">in-app event postback window configuration</Anchor>).
5. Click **Save integration**.
6. [Optional]After saving the integration, while remaining on the configuration page, you can integrate more of your apps with the partner:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the <Anchor target="_blank" href="/marketers/vi/docs/amazon-ads-campaign-configuration#integration-tab">integration steps</Anchor> for the selected app.

> 📘 **Note**
>
> For iOS apps only: Your control over data shared with the partner via postbacks and <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">reports</Anchor> depends on the **Advanced Privacy (for iOS 14.5+ and later)** <Anchor target="_blank" href="/marketers/vi/docs/tiktok-for-business-advanced-srn-integration-setup#quyền-riêng-tư-nâng-cao">toggle state</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Generate and save attribution links and send them to the partner for attributing specific campaigns, ad sets, or single ads - both for UA and retargeting campaigns. You can use either a single-platform link or a <Anchor target="_blank" href="/marketers/vi/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">Learn more about attribution link structure and parameters</Anchor>. **To generate an attribution link,** follow <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#attribution-link-tab">these instructions</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data isn't available for Awin.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue isn't available for Awin.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Select which permissions to grant Awin to access your data and perform various actions.

> 📘 **Note**
>
> * When the integration is <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">deactivated</Anchor> while the Permissions toggle is still turned on, permissions remain granted.
> * Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">granting permissions</Anchor>.

</Accordion>

## Deep linking and deferred deep linking using OneLink

AWIN wraps any link used in their platform so that they can provide analytics data to their customers. This means the link will be redirected to AWIN’s site before sending users to their final destination. <Anchor target="_blank" href="https://www.appsflyer.com/blog/mobile-marketing/universal-links-app-links/#:~:text=%231%3A%20Link%20wrapping%20and%20Universal%20Links">Learn more about link wrapping</Anchor>.  
AWIN as a platform supports a URI scheme but **doesn’t support** handling the iOS Universal links and Android app link methods of deep linking. This applies to any link used within AWIN.

To deep link with OneLink via AWIN:

* <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">Setup your OneLink URL with a URI scheme</Anchor>

> 📘 **Note**
>
> For iOS apps, use the `af_force_deeplink=true` parameter on the OneLink URL to activate the deep link <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">URI scheme</Anchor>.

<div data-zendesk-anchors="01H88VAJH3B5ESK12D3ATMMVZ8=activate-partner setting-up-amazon-dsp-integration=setting-up-awin 01H88VAJH3VENKYVRQY5RXN63P=setting-up-awin 01H88VAJH3BYZSXQGGZZJQ9N0C=note h_01HFPEEW4FXS9AFQTTEF2ZBDZW=prerequisite 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=activate-partner-1 01H88VAJH34GP7FK1KTJGRDPM7=activate-partner-1 01H88VAJH3G5FAR7RRNDEPNGME=advanced-privacy 01H88VAJH3F2FJK5YP3M2V7RWD=general-settings h_01K4VVB00RYB0XRANWQ29M6P36=note-1 01H88VAJH3WE9Z0971WMBRBJRS=default-postbacks inapp-event-settings=in-app-event-settings h_01HA77JYAR06HA5FZGSRQJATHF=in-app-event-settings inapp-event-postbacks=in-app-event-postbacks 01H88VAJH3AS37MVF75GANWX4B=in-app-event-postbacks 01H88VAJH36MYZ9W1YPWA92Z1Z=note-2 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=note-3 h_01HA77Q9RWZ3FRE5KEN854ZZ78=deep-linking-and-deferred-deep-linking-using-onelink h_01HA78QWQVXEWHPEQE6XWBB64M=note-4" />
