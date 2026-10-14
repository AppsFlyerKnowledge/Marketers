---
title: "Configuring Meta campaign management partners"
excerpt: "Optimize Meta ads campaigns by using Meta campaign management partners (formerly known as Facebook Marketing Partners), such as Kenshoo, Bidalgo, and Smartly. When configured, AppsFlyer sends them the postbacks."
x-zendesk:
  id: 360000562569
  url: https://support.appsflyer.com/hc/en-us/articles/360000562569-Configuring-Meta-campaign-management-partners
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Meta campaign management partners
  section_id: 6551188365457
  position: 4
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: [Facebook, FMP, Advertisers, Partners, facebook marketing partner, Facebook Marketing Partner, Developers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2018-03-18T12:43:51Z'
  edited_at: '2026-06-16T09:57:20Z'
---
## Configure Meta campaign management partners

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration as described below:

## In-app event postback setup

**Prerequisite**:

In order for the partner to get postbacks, campaign names **must** be prefixed by the Meta campaign management partner name. For example, if the Meta campaign management partner name is *Mcmpexample* and the segment is *Young\_Segment,* set the campaign name to *mcmpexample\_Young\_Segment*.  
**Note:** The Meta campaign management partner name is **case-sensitive.**

**To setup in-app event postbacks**:

[![in-app_event_mapping.png](https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png)](https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png)

1. Turn on **In-app event postbacks**.
2. Complete the required parameters according to the [mapping method](/docs/in-app-event-postback-configuration#mapping-methods):

   

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you're looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation, and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events)</li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. [Possible mapping configurations](/docs/in-app-event-postback-configuration#mapping-methods) are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined partner event.</li><li>**As is**: Send the events as they are, without mapping the event name.</li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner.</li><li>**All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, when the user who performed it came from any media source.</li></ul> |
| **including** | Select [which event data](/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks) to share with the partner in the postback:<ul><li>**No values & no revenue**: Send just the event itself without any parameters (values or revenue).</li><li>**Values & no revenue**: Send all the parameters **excluding** the revenue value.</li><li>**Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li></ul> |

3. [Optional] Click ![conditional-iae-postbacks-icon.png](https://files.readme.io/5345c5ebe95b3f1a0d0858b88ce29f9965178ce750df86c04cb131a93d006a5e-14050481317393.png) to [set conditions](/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks) for sending certain in-app events to the partner.
4. [Optional] Click **Add event** to add another SDK or server-to-server event to the list.
5. Click **Save Integration**.

> 📘 **Important Notes**
>
> * Disabling attribution for Meta ads prevents sending postbacks to Meta campaign management partners
> * The in-app events mapping with the Meta campaign management partners, or lack of it, does not affect the sending of in-app events to Meta ads directly from the advertiser's account.
> * In-app events mapping may require different setup parameters depending on the Meta campaign management partner.
> * Meta ads and X Ads campaign names must start with the Meta campaign management partner account name, as defined in the AppsFlyer platform, followed by an underscore "\_". When campaigns aren't named as mentioned, they're visible to the advertiser but not to the Meta campaign management partner. The Meta campaign management partner name is **case-sensitive**.