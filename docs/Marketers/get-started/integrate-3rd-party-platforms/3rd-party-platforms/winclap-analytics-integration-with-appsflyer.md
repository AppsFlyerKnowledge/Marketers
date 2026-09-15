---
title: "Winclap Analytics integration with AppsFlyer"
excerpt: "Learn how to set up the Winclap Analytics integration with AppsFlyer to share attribution data for BI and post-attribution analytics."
---
<Cards>
  <Card title="Setting up Winclap" href="#setting-up-winclap" />
  <Card title="Integration tab" href="#integration-tab" />
  <Card title="Attribution link tab" href="#attribution-link-tab" />
  <Card title="Cost tab" href="#cost-tab" />
  <Card title="Ad revenue tab" href="#ad-revenue-tab" />
  <Card title="Permissions tab" href="#permissions-tab" />
</Cards>

**At a glance:** Winclap Analytics, an AppsFlyer integrated partner, uses AppsFlyer attribution data for BI and post-attribution analytics.

> ❗️ Important!
>
> [Some media sources](https://support.appsflyer.com/hc/articles/360006868017-Raw-data-content-restriction-media-source-or-user-identifiers#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Winclap

The setup is done from the **Active Integrations** page, but to find the partner you must first go to the [marketplace](https://support.appsflyer.com/hc/articles/9960361873809).

> 📘 Note
>
> Before setting up an integration, make sure you [contact the partner](https://support.appsflyer.com/hc/articles/9960361873809#contact-details) and open an account with them.

**To activate the integration:**

1. From the top menu of any AppsFlyer page, click **Marketplace**.
2. Search for the partner and select it.
3. Click **Set up integration**. You’re directed to the integration setup page.
4. In the **Integration** tab, select the app for the integration and turn **Activate partner** on.

**Note:** The toggle must be on [(activated)](https://support.appsflyer.com/hc/articles/360000844778) for as long as you work with the partner.
5. Complete the configuration using the relevant tabs, as described below.

Winclap Analytics configuration makes use of the _**Integration**_ tab only.

For a detailed description of the Partner Configuration Window Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521#about-the-integrated-partner-page).

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you must toggle ON the _**Activate Partner**_ toggle to enable the setup of the integration tab's parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](https://support.appsflyer.com/hc/articles/360006091197).

### Default postbacks

AppsFlyer can send automatic postbacks to Winclap Analytics user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

<Image src="https://files.readme.io/e94eb0f90b15d03406df7f9de78c0ac7e6de3303ad5a073a96c17dab0b89a410-360008532978.png" alt="winclap analytics integration - default postbacks" />

For **installs**, select:

- (Default) _**This partner only**_ for events coming only from users attributed to Winclap.
- **_All media sources, including organic_** to send postbacks for any user that downloads the app to Winclap.

For **reengagements**, the postbacks can be sent for _**This partner only**_.

Once this configuration is saved, AppsFlyer sends the following data to Winclap Analytics for each install, both organic and non-organic:

- Click ID
- Campaign name
- User-agent
- Click time
- IP
- Country
- City
- Sub publisher
- Device ID for Android & iOS
- Carrier
- Language
- App ID
- App version
- App name
- Install time

### In-app events settings

In this section, you can map which in-app events to send to Winclap Analytics using postbacks:

<Image src="https://files.readme.io/6a67cceaafd0592ffed76c77ed20c8c382f8e5ff1a8b8f1909feb2e2372ff251-360008437297.png" alt="winclap analytics - in-app event postback configuration" />

1. Switch the _**In-App Event Postbacks**_ toggle to ON.
2. Set the _**In-app event postback window**_, if required (read more about [in-app event postback window configuration](https://support.appsflyer.com/hc/articles/208439256-In-App-Events-Postback-Configuration#inapp-event-postback-window)).
3. Click _**Add Event**_ to add an SDK Event to the list.
4. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK event name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server to server events.<br>**Tip**: Don't see the event you are looking for? Type in its SDK Event Name, click **Create custom**, and map normally. Read more about [custom event mapping](https://support.appsflyer.com/hc/articles/208439256#custom-events). |
| **Partner event identifier** | The unique name or ID of each event as defined by Winclap.<br>Get from Winclap the corresponding ID for each of the events you want to report to them, and enter in this field. |
| **Sending option** | Select the sending option for the event:<br>**This partner only** for events coming **only** from users attributed to this partner<br>**All media sources, including organic** to have your entire user base available to be reported to the partner |
| **Send event data** | - **No values & no revenue:** sends only the event itself without the event value.<br> - **Values & no revenue:** sends all the parameters excluding the revenue value.<br> - **Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event). |

5. Click **_Save_.**

Once this configuration is saved, AppsFlyer sends the following data to Winclap Analytics for each non-organic event:

- Click ID
- Event name
- Event value
- Event revenue
- Event currency
- Event revenue in USD
- Campaign name
- User-agent
- Click time
- IP
- Country
- City
- Sub publisher
- Device ID for Android & iOS
- Carrier
- Language
- App ID
- App version
- App name
- Install time

## Attribution link tab

Attribution Links are not available for Winclap Analytics.

## Cost tab

Cost data is not supported in the integration with this partner.

## Ad revenue tab

Ad Revenue is not supported in the integration with this partner.

## Permissions tab

Permissions are not available for Winclap Analytics.