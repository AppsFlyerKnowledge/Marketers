---
title: Medialyzer integration with AppsFlyer
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
  created_at: '2023-05-01T11:43:34Z'
  edited_at: '2026-06-16T09:51:58Z'
  id: 14963611180689
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/14963611180689-Medialyzer-integration-with-AppsFlyer
---
> **At a glance:** Medialyzer, an AppsFlyer integrated partner, develops and markets the software as a service solution. The solution allows media planners to optimize their TV campaigns for online businesses based on immediately generated visits and conversions per TV ad airing.

<div id="important" />

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/docs/about-raw-data-identifier-restrictions#media-source-restrictions">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

<div id="setting-up-medialyzer" />

## Setting up Medialyzer

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below.

For a detailed description of the Partner Configuration Window Header, click <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">here</Anchor>.

<div id="integration-tab" />

<Accordion title="Integration tab">

<div id="activate-partner" />

#### Activate partner

On your first visit, you'll need to turn on the **Activate partner** toggle to set up the integration. The toggle must remain on for as long as you work with Medialyzer. Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">partner activation</Anchor>.

<div id="advanced-privacy" />

#### Advanced Privacy

For iOS apps, the <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">Advance Privacy</Anchor> toggle appears. When turned on, it limits the sharing of user identifiers with the partner. Note that when the <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">Aggregated Advanced Privacy</Anchor> toggle is turned on in the App Settings, **Advanced Privacy (for iOS 14.5+ and later)** is turned on and locked by default.

<div id="default-postbacks" />

#### Default postbacks

AppsFlyer sends default postbacks to Medialyzer following user installs. Use this section to <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#default-postbacks">define these postbacks</Anchor>.

* **Off**: Install postbacks aren't sent to Medialyzer.
* **All media sources, including organic**: Install postbacks are sent for events attributed to any partner and for organic events.

<Image align="center" alt="default_postbacks.png" src="https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png" />

<div id="in-app-event-postbacks" />

#### In-app event postbacks

In this section, you can map your AppsFlyer events with your partners via postbacks.

<Image align="center" alt="app_event_postbacks.JPG" src="https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png" />

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list.
3. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#custom-events">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | Enter the corresponding event name or ID of each event, as defined in BPM, or send the events as they are without name mapping. |
| **for users from** | Select **All media sources, including organic** to send postbacks for events attributed to any partner and for organic events. |
| **including** | <ul><li>**No values & no revenue**: Send just the event itself without any parameters (values or revenue).</li><li>**Values & no revenue**: Send all the parameters **excluding** the revenue value.</li><li>**Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li></ul> |

4. Click **Save Integration**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution links aren't available for Medialyzer.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data isn't supported in the integration with Medialyzer.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue data isn't supported in the integration with Medialyzer.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions aren't available for Medialyzer.

</Accordion>

<div data-zendesk-anchors="h_01H9FKEAV2225HM5CQAGWS2K99=important setting-up-spoteffects=setting-up-medialyzer h_01H9FKEAV37AT3VTZ5WV1YMWC2=setting-up-medialyzer h_01H9FKEAV3YQY124TSZ5Q7VHAY=integration-tab h_01H9FKEAV3DW2A6RQ1NS44FT5F=activate-partner h_01H9FKEAV3T3YCPBYW70QVF540=advanced-privacy h_01H9FKEAV3Z1Y09P6E18J8AVX2=default-postbacks inapp-event-postbacks=in-app-event-postbacks h_01H9FKEAV3GG6X17X3NCCSWJAS=in-app-event-postbacks h_01H9FKEAV3ZEF1AHRTQGEGYFSJ=attribution-link-tab h_01H9FKEAV3ERXQ98BJGKBQRGP2=cost-tab h_01H9FKEAV32MB7M2Q1ASDAE6RM=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab" />
