---
title: Configuring Meta campaign management partners
metadata:
  keywords:
    - Facebook
    - FMP
    - Advertisers
    - Partners
    - facebook marketing partner
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2018-03-18T12:43:51Z'
  edited_at: '2026-06-16T09:57:20Z'
  id: 360000562569
  locale: en-us
  section: Meta campaign management partners
  section_id: 6551188365457
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360000562569-Configuring-Meta-campaign-management-partners
---
> **At a glance:** Optimize Meta ads campaigns by using Meta campaign management partners (formerly known as Facebook Marketing Partners), such as Kenshoo, Bidalgo, and Smartly. When configured, AppsFlyer sends them the postbacks.

<div id="configure-meta-campaign-management-partners" />

## Configure Meta campaign management partners

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration as described below:

<div id="in-app-event-postback-setup" />

## In-app event postback setup

**Prerequisite**:

In order for the partner to get postbacks, campaign names **must** be prefixed by the Meta campaign management partner name. For example, if the Meta campaign management partner name is *Mcmpexample* and the segment is *Young\_Segment,* set the campaign name to *mcmpexample\_Young\_Segment*.  
**Note:** The Meta campaign management partner name is **case-sensitive.**

**To setup in-app event postbacks**:

[![in-app_event_mapping.png](https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png)](https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png)

1. Turn on **In-app event postbacks**.
2. Complete the required parameters according to the <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#mapping-methods">mapping method</Anchor>:

   

| Parameter name | Description |
| --- | --- |
| <span id="appsflyer-event"></span>**AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you're looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation, and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#custom-events">custom event mapping.</Anchor></li></ul> |
| <span id="mapped-to-partner-event"></span>**mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#mapping-methods">Possible mapping configurations</Anchor> are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined partner event.</li><li>**As is**: Send the events as they are, without mapping the event name.</li></ul> |
| <span id="for-users-from"></span>**for users from** | Select the sending option for the event:<ul><li>**This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner.</li><li>**All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, when the user who performed it came from any media source.</li></ul> |
| <span id="including"></span>**including** | Select <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks">which event data</Anchor> to share with the partner in the postback:<ul><li>**No values & no revenue**: Send just the event itself without any parameters (values or revenue).</li><li>**Values & no revenue**: Send all the parameters **excluding** the revenue value.</li><li>**Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li></ul> |

3. [Optional] Click ![conditional-iae-postbacks-icon.png](https://files.readme.io/5345c5ebe95b3f1a0d0858b88ce29f9965178ce750df86c04cb131a93d006a5e-14050481317393.png) to <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for sending certain in-app events to the partner.
4. [Optional] Click **Add event** to add another SDK or server-to-server event to the list.
5. Click **Save Integration**.

<div id="important-notes" />

> 📘 **Important Notes**
>
> * Disabling attribution for Meta ads prevents sending postbacks to Meta campaign management partners
> * The in-app events mapping with the Meta campaign management partners, or lack of it, does not affect the sending of in-app events to Meta ads directly from the advertiser's account.
> * In-app events mapping may require different setup parameters depending on the Meta campaign management partner.
> * Meta ads and X Ads campaign names must start with the Meta campaign management partner account name, as defined in the AppsFlyer platform, followed by an underscore "\_". When campaigns aren't named as mentioned, they're visible to the advertiser but not to the Meta campaign management partner. The Meta campaign management partner name is **case-sensitive**.

<div data-zendesk-anchors="configuring-facebook-marketing-partners=configure-meta-campaign-management-partners h_01HGFQCBT217ZV0R6E2YHTV88N=configure-meta-campaign-management-partners inapp-event-postback-setup=in-app-event-postback-setup h_01HGFQCBT3R7HH8M5SQJK1EPSP=in-app-event-postback-setup h_01HGFQCBT3HGZVFHCC1S04MVQW=important-notes" />
