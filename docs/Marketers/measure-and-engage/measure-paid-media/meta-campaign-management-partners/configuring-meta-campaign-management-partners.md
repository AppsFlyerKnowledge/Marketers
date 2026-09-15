---
title: "Configuring Meta campaign management partners"
excerpt: "Learn how to configure Meta campaign management partners to optimize your Meta ads campaigns and set up in-app event postbacks."
---
At a glance: Optimize Meta ads campaigns by using Meta campaign management partners (formerly known as Facebook Marketing Partners), such as Kenshoo, Bidalgo, and Smartly. When configured, AppsFlyer sends them the postbacks.

## Configure Meta campaign management partners

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

5. Complete the configuration as described below:

## In-app event postback setup

> 📘 Prerequisite
>
> In order for the partner to get postbacks, campaign names **must** be prefixed by the Meta campaign management partner name. For example, if the Meta campaign management partner name is _Mcmpexample_ and the segment is _Young_Segment,_ set the campaign name to _mcmpexample_Young_Segment_.

> 🚧 Note
>
> The Meta campaign management partner name is **case-sensitive.**

**To setup in-app event postbacks**:

![in-app_event_mapping.png](https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png)

1. Turn on **In-app event postbacks**.
2. Complete the required parameters according to the [mapping method](/docs/in-app-event-postback-configuration#mapping-methods):

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you're looking for?<br />   - Make sure to activate the event on a device with a non-organic installation, and recheck.<br />   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. [Possible mapping configurations](/docs/in-app-event-postback-configuration#mapping-methods) are:<br />   - **Text field:** Get the corresponding event ID from the partner.<br />   - **Drop-down box:** Select the most suitable pre-defined partner event.<br />   - **As is**: Send the events as they are, without mapping the event name. |
| **for users from** | Select the sending option for the event:<br />   - **This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner.<br />   - **All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, when the user who performed it came from any media source. |
| **including** | Select [which event data](/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks) to share with the partner in the postback:<br />   - **No values & no revenue**: Send just the event itself without any parameters (values or revenue).<br />   - **Values & no revenue**: Send all the parameters **excluding** the revenue value.<br />   - **Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event). |

3. [Optional] Click ![conditional-iae-postbacks-icon.png](https://files.readme.io/5345c5ebe95b3f1a0d0858b88ce29f9965178ce750df86c04cb131a93d006a5e-14050481317393.png) to [set conditions](/docs/in-app-event-postback-configuration#conditional-inapp-event-postbacks) for sending certain in-app events to the partner.
4. [Optional] Click **Add event** to add another SDK or server-to-server event to the list.
5. Click **Save Integration**.

#### Important Notes

- Disabling attribution for Meta ads prevents sending postbacks to Meta campaign management partners
- The in-app events mapping with the Meta campaign management partners, or lack of it, does not affect the sending of in-app events to Meta ads directly from the advertiser's account.
- In-app events mapping may require different setup parameters depending on the Meta campaign management partner.
- Meta ads and X Ads campaign names must start with the Meta campaign management partner account name, as defined in the AppsFlyer platform, followed by an underscore "_". When campaigns aren't named as mentioned, they're visible to the advertiser but not to the Meta campaign management partner. The Meta campaign management partner name is **case-sensitive**.