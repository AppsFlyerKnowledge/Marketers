---
title: "Medialyzer integration with AppsFlyer"
excerpt: "Medialyzer, an AppsFlyer integrated partner, develops and markets the software as a service solution. The solution allows media planners to optimize their TV campaigns for online businesses based on immediately generated visits and conversions per TV ad airing."
x-zendesk:
  id: 14963611180689
  url: https://support.appsflyer.com/hc/en-us/articles/14963611180689-Medialyzer-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 19
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2023-05-01T11:43:34Z'
  edited_at: '2026-06-16T09:51:58Z'
---
> ❗️ Important!
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Medialyzer

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle must stay on (active) as long as you work with the partner. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below.

For a detailed description of the Partner Configuration Window Header, click [here](/docs/set-up-an-integrated-partner#about-the-integrated-partner-page).

### Integration tab

#### Activate partner

On your first visit, you'll need to turn on the **Activate partner** toggle to set up the integration. The toggle must remain on for as long as you work with Medialyzer. Learn more about [partner activation](/docs/partner-activation-deactivation).

#### Advanced Privacy

For iOS apps, the [Advance Privacy](/docs/apply-aggregated-advanced-privacy-framework) toggle appears. When turned on, it limits the sharing of user identifiers with the partner. Note that when the [Aggregated Advanced Privacy](/docs/apply-aggregated-advanced-privacy-framework) toggle is turned on in the App Settings, **Advanced Privacy (for iOS 14.5+ and later)** is turned on and locked by default.

#### Default postbacks

AppsFlyer sends default postbacks to Medialyzer following user installs. Use this section to [define these postbacks](/docs/set-up-an-integrated-partner#default%20postbacks).

- **Off**: Install postbacks aren't sent to Medialyzer.
- **All media sources, including organic**: Install postbacks are sent for events attributed to any partner and for organic events.

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

#### In-app event postbacks

In this section, you can map your AppsFlyer events with your partners via postbacks.

![app_event_postbacks.JPG](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list.
3. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<br />   - Make sure to activate the event on a device with a non-organic installation and recheck.<br />   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](/docs/in-app-event-postback-configuration#custom-events) |
| **mapped to partner event** | Enter the corresponding event name or ID of each event, as defined in BPM, or send the events as they are without name mapping. |
| **for users from** | Select **All media sources, including organic** to send postbacks for events attributed to any partner and for organic events. |
| **including** | - **No values & no revenue**: Send just the event itself without any parameters (values or revenue).<br />   - **Values & no revenue**: Send all the parameters **excluding** the revenue value.<br />   - **Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event). |

4. Click **Save Integration**.

### Attribution link tab

Attribution links aren't available for Medialyzer.

### Cost tab

Cost data isn't supported in the integration with Medialyzer.

### Ad revenue tab

Ad revenue data isn't supported in the integration with Medialyzer.

### Permissions tab

Permissions aren't available for Medialyzer.