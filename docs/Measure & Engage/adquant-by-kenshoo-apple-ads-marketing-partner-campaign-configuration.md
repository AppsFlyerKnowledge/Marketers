---
title: "Adquant by Kenshoo Apple Ads Campaign Configuration"
excerpt: "Optimize Apple Ads campaigns by configuring AppsFlyer to send postbacks to Adquant by Kenshoo."
---
Optimize Apple Ads campaigns by using Adquant by Kenshoo. When configured, AppsFlyer sends postbacks to Adquant.

## Enabling sending postbacks to Adquant (Apple Ads marketing partner)

Both advertisers and agencies can enable Attribution for Apple Ads.

> 🚧 Note
>
> If the advertiser or the agency disables attribution for Apple Ads, attribution for this app, including postback sending to Apple Ads Marketing Partners stops.

- **Advertisers:** follow the instructions below on how to enable attribution for Apple Ads.
- **Agencies:** [follow these instructions](https://support.appsflyer.com/hc/articles/213747963-Apple-Search-Ads-guide#agency-setup) to enable attribution for Apple Ads.

### Configuring Adquant by Kenshoo

**To set up Adquant:**

1. If required, activate **Apple Ads integration:**
   1. In AppsFlyer, from the side menu, select **Collaboration** > **Partner Marketplace**.
   2. Search for and select the partner. You're directed to the partner configuration page.
   3. From the **Integration** tab, turn on **Activate partner**.
   4. Click **Save Integration**.
2. **In your Apple Ads dashboard**: Get the Apple Ads Campaign Group ID parameter related to Adquant. Use the screenshot that follows as a guide to locating the ID.

![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)

3. **In AppsFlyer, configure Adquant:**
   1. In AppsFlyer, from the side menu, select **Collaboration** > **Active Integrations.**
   2. Search for Adquant by Kenshoo Apple Ads marketing partner.
      The list of marketing partners is displayed.
   3. Select Adquant by Kenshoo Apple Ads marketing partner.
   4. Turn on **Activate Partner**.
   5. Enter Adquant's **Apple Ads Campaign ID** that you retrieved in the earlier step. Enter the digits (numbers) only.
   6. In **action_identifier**, enter the domain used for postback delivery.
   7. [Optional] **Don't allow sharing of user geo location:** To stop sharing user geolocation, in **Disable_Country_Sending** type `1`.
   8. Click **Save**.

### Default postbacks

The displayed postbacks are sent automatically when the partner is activated.

### Configuring in-app events postback

**To configure in-app events postback:**

1. Enter the acion_identifier.
2. Turn on **In-app events postback**.
3. Click **Add Event** to add an SDK or server-to-server event to the list.
4. Complete the following parameters:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br><br>**Tip**: Don't see the event you're looking for?<br> - Make sure to activate the event on a device with a non-organic installation, and recheck.<br> - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](https://support.appsflyer.com/hc/articles/208439256#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. [Possible mapping configurations](/docs/in-app-event-postback-configuration#mapping-methods) are:<br> - **Text field:** Get the corresponding event ID from the partner.<br> - **Drop-down box:** Select the most suitable pre-defined partner event.<br> - **As is**: Send the events as they are, without mapping the event name. |
| **for users from** | Select the sending option for the event:<br> - **This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner.<br> - **All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, when the user who performed it came from any media source. |
| **including** | Select [which event data](https://support.appsflyer.com/hc/articles/208439256#data-to-include-in-the-postbacks) to share with the partner in the postback:<br> - **No values & no revenue**: Send just the event itself without any parameters (values or revenue).<br> - **Values & no revenue**: Send all the parameters **excluding** the revenue value.<br> - **Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event). |

5. Click **Save Integration**.