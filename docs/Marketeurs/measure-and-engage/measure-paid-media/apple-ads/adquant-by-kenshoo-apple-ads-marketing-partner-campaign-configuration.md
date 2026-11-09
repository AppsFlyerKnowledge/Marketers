---
title: Adquant by Kenshoo Apple Ads marketing partner—campaign configuration
metadata:
  keywords:
    - kenshoo
    - Advertisers
    - apple search ads
    - Agencies
    - adquant
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2018-09-20T07:53:06Z'
  edited_at: '2026-09-15T10:57:30Z'
  id: 360001491269
  locale: en-us
  section: Apple Ads
  section_id: 6551310453393
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360001491269-Adquant-by-Kenshoo-Apple-Ads-marketing-partner-campaign-configuration
---
> **At a glance:** Optimize Apple Ads campaigns by using Adquant by Kenshoo. When configured, AppsFlyer sends postbacks to Adquant.

## Enabling sending postbacks to Adquant (Apple Ads marketing partner)

Both advertisers and agencies can enable Attribution for Apple Ads.

> 📘 **Note**
>
> If the advertiser or the agency disables attribution for Apple Ads, attribution for this app, including postback sending to Apple Ads Marketing Partners stops.

* **Advertisers:** follow the instructions below on how to enable attribution for Apple Ads.
* **Agencies:** <Anchor target="_blank" href="/marketers/fr/docs/apple-ads-integration-setup#agency-setup">follow these instructions</Anchor> to enable attribution for Apple Ads.

### Configuring Adquant by Kenshoo

**To set up Adquant:**

1. If required, activate **Apple Ads integration:**
   1. In AppsFlyer, from the side menu, select **Collaboration** > **Partner Marketplace**.
   2. Search for and select the partner. You're directed to the partner configuration page.
   3. From the **Integration** tab, turn on **Activate partner**.
   4. Click **Save Integration**.
2. **In your Apple Ads dashboard**: Get the Apple Ads Campaign Group ID parameter related to Adquant. Use the screenshot that follows as a guide to locating the ID.

   <Image align="center" alt="ASACGroupID.png" src="https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png" />
3. **In AppsFlyer, configure Adquant:**
   1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations.**
   2. Search for Adquant by Kenshoo Apple Ads marketing partner.  
      The list of marketing partners is displayed.
   3. Select Adquant by Kenshoo Apple Ads marketing partner.
   4. Turn on **Activate Partner**.
   5. Enter Adquant's **Apple Ads Campaign ID** that you retrieved in the earlier step. Enter the digits (numbers) only.
   6. In **action\_identifier**, enter the domain used for postback delivery.
   7. [Optional] **Don't allow sharing of user geo location:** To stop sharing user geolocation, in **Disable\_Country\_Sending** type `1`.
   8. Click **Save**.

### Default postbacks

The displayed postbacks are sent automatically when the partner is activated.

### Configuring in-app events postback

**To configure in-app events postback:**

1. Enter the acion\_identifier.
2. Turn on **In-app events postback**.
3. Click **Add Event** to add an SDK or server-to-server event to the list.
4. Complete the following parameters:

   

| Parameter name | Description |
| --- | --- |
| <span id="appsflyer-event"></span>**AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you're looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation, and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">custom event mapping.</Anchor></li></ul> |
| <span id="mapped-to-partner-event"></span>**mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#les-méthodes-de-mappage">Possible mapping configurations</Anchor> are:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined partner event.</li><li>**As is**: Send the events as they are, without mapping the event name.</li></ul> |
| <span id="for-users-from"></span>**for users from** | Select the sending option for the event:<ul><li>**This partner only**: Send postbacks only when the event is attributed to this partner—meaning, the user who performed it came from this partner.</li><li>**All media sources including organic**: Send postbacks for events attributed to any partner and for organic events—meaning, when the user who performed it came from any media source.</li></ul> |
| <span id="including"></span>**including** | Select <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#données-à-inclure-dans-les-postbacks">which event data</Anchor> to share with the partner in the postback:<ul><li>**No values & no revenue**: Send just the event itself without any parameters (values or revenue).</li><li>**Values & no revenue**: Send all the parameters **excluding** the revenue value.</li><li>**Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li></ul> |

5. Click **Save Integration**.

<div data-zendesk-anchors="enabling-sending-postbacks-to-adquant-apple-search-ads-marketing-partner=enabling-sending-postbacks-to-adquant-apple-ads-marketing-partner h_01HKW0AW61TW7TGPB4KX4XYVCB=enabling-sending-postbacks-to-adquant-apple-ads-marketing-partner h_01HKW0AW61RDVXCB37PAFKAXW3=note h_01HKW0AW61QT8823TXVYB7JWTC=configuring-adquant-by-kenshoo h_01HKW0AW61EKKGK1NSKBDXSDJC=default-postbacks configuring-inapp-events-postback=configuring-in-app-events-postback h_01HKW0AW6184ZH4H6JEJPBNXSH=configuring-in-app-events-postback" />
