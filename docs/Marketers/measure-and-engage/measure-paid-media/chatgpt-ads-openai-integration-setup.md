---
title: ChatGPT Ads (OpenAI) integration setup
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-07-05T13:42:23Z'
  edited_at: '2026-10-29T13:37:02Z'
  id: 48439655791249
  locale: en-us
  section: Measure paid media
  section_id: 6550990672401
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/48439655791249-ChatGPT-Ads-OpenAI-integration-setup
---
> **At a glance:** ChatGPT Ads, an AppsFlyer integrated partner, is OpenAI's advertising platform. Set up the integration to measure and attribute mobile app installs, in-app events, and website conversions driven by your ChatGPT Ads campaigns.

<div id="about-the-integration-with-chatgpt-ads" />

## About the integration with ChatGPT Ads

The AppsFlyer integration with ChatGPT Ads (OpenAI) enables you to measure and attribute app installs, in-app events, and website conversions driven by your ChatGPT Ads campaigns. It supports both mobile app and website measurement.

* **Mobile app** - AppsFlyer attributes installs and re-engagements to your ChatGPT Ads campaigns, and sends in-app event postbacks.
* **Website** - AppsFlyer forwards web events, such as page views, content views, and purchases, captured by the AppsFlyer Web SDK to ChatGPT Ads' Conversions API (CAPI), in addition to (or instead of) the ChatGPT Ads JavaScript pixel.

If you also run the ChatGPT Ads pixel on your website, ChatGPT Ads deduplicates the server-side events (sent via the Conversions API, or CAPI) against the pixel events using a shared event ID, so you can run CAPI and the pixel in parallel without inflating your conversion counts.

Include that shared ID as `af_customer_event_id` in the event payload you send to AppsFlyer. See [Integrate your website](#integrate-your-website) below.

<div id="set-up-the-integration" />

## Set up the integration

Set up the integration separately for each mobile app and website you want to measure. You'll need a Pixel ID and API key from your ChatGPT Ads (OpenAI) Ads Manager account for each one.

**Prerequisites:**

* Before setting up the integration, open an account with ChatGPT Ads.
* Your mobile and website apps are set in AppsFlyer. <Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer">Learn more</Anchor>

**To set up the integration:**

1. **To activate:** In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Marketplace** tab.  
   **To edit:** In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active integrations** tab.
2. Set up the integration for your:

* [**Mobile app**](#integrate-your-mobile-app) - attribute installs, re-engagements, and in-app events to ChatGPT Ads campaigns.
* [**Website**](#integrate-your-website) - forward web conversion events to ChatGPT Ads' Conversions API, with deduplication against the ChatGPT Ads pixel.

<div id="integrate-your-mobile-app" />

## Integrate your mobile app

Use the following steps to set up attribution and in-app event postbacks for ChatGPT Ads on your mobile app.

**To integrate your mobile app:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Marketplace** tab.
2. Select your mobile app from the drop-down menu.  
   **Note:** You'll need to repeat these steps for each platform your app runs on, such as your Android and iOS apps.
3. Search for **ChatGPT Ads (OpenAI)** and click **Integrate**.
4. Complete the configuration in the tabs as described below.

<div id="integration-tab" />

<Accordion title="Integration tab">

<div id="activate-partner" />

#### Activate partner

**To activate the integration:**

Turn on the **Activate partner** toggle.

**Important note:** The toggle **must remain on** as long as you work with ChatGPT Ads. Deactivating the integration will turn off attribution and postbacks for your campaigns.  
Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">partner activation</Anchor>.

<div id="general-settings" />

#### General settings

Enter the following credentials:

* **Pixel ID** - A Pixel is created in your ChatGPT Ads Manager. Get it from the conversions tab in your Ads Manager account.
* **API key** - An API key is required to authenticate Events API calls. Get it from the conversions tab in your ChatGPT Ads Manager account.   
  **Note:** Make sure to use the conversions API key and not the ads management API key, since the required permissions require the CAPI key.

<div id="advanced-privacy" />

##### **Advanced Privacy**

The Advanced Privacy (AP) toggle controls how events are sent to OpenAI for iOS users (14.5 and above) who have not made their IDFA available (on the advertiser or publisher side):

* Advanced Privacy **Disabled**: Events are sent with all available user identifiers (IPs, user agent, etc.) even when IDFA isn't available.
* Advanced Privacy **Enabled**: Only events that are attributed to `openai_int` are sent, and these postbacks only include attribution data. All user-level identifiers are removed from the postback before it is sent.

<div id="note" />

> 📘 **Note**
>
> OpenAI doesn’t collect or share IDFA on iOS devices, so the only way to ensure unattributed postbacks are being sent is to turn advanced privacy OFF.

<div id="advanced-matching-data-sharing" />

##### **Advanced Matching Data Sharing**

Turn on to share Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, and hashed last name, with ChatGPT Ads, if these fields are included in the event information sent to AppsFlyer. For more information, see: <Anchor target="_blank" href="/marketers/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor>.

<div id="default-postbacks" />

#### Default postbacks

A postback is a server-to-server notification that AppsFlyer sends to ChatGPT Ads to report an attributed event (like an install or in-app action). This section displays your postbacks. Learn how to <Anchor target="_blank" href="/marketers/docs/set-up-re-attribution-window">set install and re-attribution postbacks</Anchor>.

Learn more about the <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#default-postbacks">default postbacks setting</Anchor>.

<div id="in-app-event-settings" />

#### In-app event settings

To be able to send in-app event postbacks to ChatGPT Ads, enter the required credentials:

* Pixel ID
* API key

For details, see [General settings](#general-settings) above.

<div id="in-app-event-postbacks" />

#### In-app event postbacks

Configure in-app event postbacks to send to ChatGPT Ads. <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration">Learn more</Anchor>

**To enable in-app event postbacks:**

Turn on the **In-app event postbacks** toggle.

**In-app event postback window**

Define the period after an install, re-attribution, or re-engagement, during which AppsFlyer sends in-app event postbacks to ChatGPT Ads. <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration">Learn more</Anchor>

**Map your events**

To ensure your events match the corresponding events in ChatGPT Ads, map your event names. <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#event-mapping">Learn more</Anchor>

ChatGPT Ads supports the following standard events, plus a **Custom** fallback for any event not covered below:

| ChatGPT Ads event name | When to use |
| --- | --- |
| page\_viewed | User lands on or views an important page. |
| contents\_viewed | User views a specific product, listing, article, or content unit. |
| items\_added | User adds one or more items to a cart, bundle, or selection. |
| checkout\_started | User starts checkout. |
| order\_created | Purchase completed. |
| registration\_completed | User finishes account or event registration. |
| lead\_created | User submits a lead form or requests contact. |
| appointment\_scheduled | User books a meeting, demo, or consultation. |
| trial\_started | Free trial starts. |
| subscription\_created | Paid subscription starts. |
| app\_opened | Mobile app open. |
| custom | Any event not covered by the standard taxonomy. |

**Event deduplication**

If you also run the ChatGPT Ads pixel on your website, send the same event ID to both AppsFlyer and ChatGPT Ads so AppsFlyer can deduplicate the events:

* Include `af_customer_event_id` in the event payload you send to AppsFlyer, inside eventValue for the Web SDK or event\_value for the S2S (server-to-server) API.
* Send the same value in the corresponding Pixel event.

AppsFlyer forwards this value to ChatGPT Ads as the event ID. ChatGPT Ads then uses it to deduplicate the server-side event it receives from AppsFlyer against the Pixel event, so AppsFlyer counts the conversion once.

If you don't send `af_customer_event_id`, AppsFlyer generates an event ID automatically. This ID won't match your Pixel events.

For more information, see Integrate AppsFlyer Web SDK.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

ChatGPT Ads (OpenAI) supports attribution links.

<div id="choose-your-attribution-type" />

#### Choose your attribution type

Decide whether you want to:

1. Send users directly to the app store. If so, you'll need to create either a single-platform attribution link or a <Anchor target="_blank" href="/marketers/docs/onelink-guide">OneLink</Anchor> as your final URL, based on your campaign needs and targeting settings.   

   OR
2. Use a landing page as your ad destination, and then use <Anchor target="_blank" href="/marketers/docs/onelink-smart-script-overview">Smart Script</Anchor> or <Anchor target="_blank" href="/marketers/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner</Anchor> to route the user to the App Store or Google Play (while creating a link that will allow attribution).

<div id="select-parameters" />

#### Select parameters

Select the attribution link parameters you want to include.

* Select the attribution link parameters you want to include (for example, **Campaign Name** and **Site ID**) and set your **click-through lookback window** (7 days is the AppsFlyer-recommended default). AppsFlyer generates your attribution link automatically for use in your ChatGPT Ads campaigns.
* The following URL parameters can be automatically populated by ChatGPT using these dynamic URL macros:
  * `af_partner_account_id={ad_account_id}`
  * `af_c_id={campaign_id}`
  * `af_adset_id={ad_group_id}`
  * `af_ad_id={ad_id}`
  * `clickid={oppref}`
* Name field macros aren't supported.

<div id="important" />

> 🚧 **Important**
>
> * For AppsFlyer to capture ChatGPT Ads' click ID and send it back to ChatGPT Ads, make sure to use `clickid={oppref}` if your ads lead directly to the App Store or Google Play. When the ad destination is a landing page with Smart Script, make sure to capture the incoming `oppref` parameter and map it to `clickid` in the outgoing URL.
> * ChatGPT Ads only resolves macros (such as `{campaign_id}`) when the corresponding parameters are placed in the **Tracking parameters** field, not the **Ad destination URL** field. Paste your query parameters (for example, `af_c_id={campaign_id}`) into the **Tracking parameters** field, and use the **Ad destination URL** field only for the destination URL itself.

**Note:** Your generated link includes `openai_int` (ChatGPT Ads' integration ID in AppsFlyer).

Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#attribution-link-tab">attribution links</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

There is currently no cost API integration for ChatGPT Ads.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue data can't be pulled from ChatGPT Ads. Use postbacks or UA signals to share ad revenue data for campaign optimization.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Turn on **Ad network permissions** to grant ChatGPT Ads team members access to your data. Once enabled, select which individual permissions to grant, such as configuring the integration, accessing retention and cohort reports, or viewing aggregate conversion and revenue data. Note that even if attribution is disabled for ChatGPT Ads, you can still grant permissions.

Learn more about <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#permissions-tab">permissions</Anchor>.

</Accordion>

<div id="integrate-your-website" />

## Integrate your website

Use the following steps to set up server-side event forwarding to ChatGPT Ads for your website.

**To integrate your website:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Marketplace** tab.
2. Select your website app from the drop-down menu.
3. Search for **ChatGPT Ads (OpenAI)** and click **Integrate**.
4. Complete the configuration in the integration tab as described below.

<div id="integration-tab::2739744d" />

<Accordion title="Integration tab">

<div id="activate-partner-1" />

#### Activate partner

**To activate the integration:**

Turn on the **Activate partner** toggle.

**Important note:** The toggle **must remain on** as long as you work with ChatGPT Ads. Deactivating the integration will turn off event forwarding for your website.  
Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">partner activation</Anchor>.

<div id="in-app-event-settings-1" />

#### In-app event settings

To be able to send event postbacks to ChatGPT Ads, enter the following credentials:

* **Pixel ID** - A Pixel is created in your ChatGPT Ads Manager. Get it from the conversions tab in your Ads Manager account.
* **API key** - An API key is required to authenticate Events API calls. Get it from the conversions tab in your ChatGPT Ads Manager account.

**Advanced Matching Data Sharing:** Turn on to share Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, and hashed last name, with ChatGPT Ads, if these fields are included in the event information sent to AppsFlyer. For more information, see: <Anchor target="_blank" href="/marketers/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor>.

<div id="in-app-event-postbacks-1" />

#### In-app event postbacks

Configure event postbacks to send to ChatGPT Ads. <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration">Learn more</Anchor>

**To enable event postbacks:**

Turn on the **In-app event postbacks** toggle.

**Map your events**

To make sure your events match the equivalent events in ChatGPT Ads, map your event names. See the standard event table above for the events ChatGPT Ads supports. <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#event-mapping">Learn more</Anchor>

</Accordion>

<div id="h_01KWVSPJ9WATTRLNK" />

<Accordion title="Attribution link tab">

ChatGPT Ads (OpenAI) doesn't use external attribution links for website integrations. The AppsFlyer Web SDK measures web events and forwards them directly to ChatGPT Ads' Conversions API, so no link-based attribution setup is needed.

</Accordion>

<div id="h_01KWVSPJ9WCOST" />

<Accordion title="Cost tab">

Cost data isn't available for website integrations with ChatGPT Ads.

</Accordion>

<div id="h_01KWVSPJ9WADREV" />

<Accordion title="Ad revenue tab">

Ad revenue data isn't available for website integrations with ChatGPT Ads.

</Accordion>

<div id="h_01KWVSPJ9WPERM" />

<Accordion title="Permissions tab">

Permissions aren't available for website integrations with ChatGPT Ads.

</Accordion>

<div id="traits-and-limitations" />

## Traits and limitations

| Trait | Description |
| --- | --- |
| Supported countries | <Anchor target="_blank" href="https://help.openai.com/en/articles/20001245-ads-manager-availability">List of countries</Anchor> where ChatGPT Ads Manager is available. |

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner">Partner integrations</Anchor>

<div data-zendesk-anchors="about-the-integration=about-the-integration-with-chatgpt-ads h_01KWS8SS8RE2VQ275MFB7CT39J=about-the-integration-with-chatgpt-ads set-up-the%20integration=set-up-the-integration h_01H95QTA3Z5HXW39AHAF8FMFWH=set-up-the-integration h_01KWVBQG0G85W6QJ8AT2520GTX=integrate-your-mobile-app h_01KWVK5J7FBA81238JD4AD0219=integration-tab h_01H95QTA3ZGEM34HY1A7NC8NX7=activate-partner h_01KWVKHV36H34XCHYBFRHNF8TB=general-settings h_01M39MMERMEBK470T0NDCVRN2E=advanced-privacy h_01M39MP266X5KME19RBVQZRDE6=advanced-matching-data-sharing h_01KWVKZJ7AZ8Z4CFM8J0PV071A=default-postbacks inapp-event-settings=in-app-event-settings h_01JTDP2T0BFP5WP03X5EMXVAWA=in-app-event-settings inapp-event-postbacks=in-app-event-postbacks h_01KWVMZC74AQSN7BDQP2QQWBT4=in-app-event-postbacks h_01KWVK5J7FE0ZF74NGXKSASMBV=attribution-link-tab h_01_choose-your-attribution-type=choose-your-attribution-type h_01_select-parameters=select-parameters h_01M254BFC0V68RJ6B903D8XKD3=important h_01KWVK5J7FK8BAQKEMNA35ABPY=cost-tab h_01KWVK5J7FQRYXQ9FGCWHWY16T=ad-revenue-tab h_01KWVK5J7G3E8NSNDG4CR9FA7N=permissions-tab h_01KWVSJRYSQEH12C5RH7BN4CC2=integrate-your-website h_01KWVSPJ9WJERF84ZNGTS7P0HZ=integration-tab::2739744d activate-partner::3c5a91e7=activate-partner-1 h_01KWVSPJ9WBQ2AS5JZPTJZPTRG=activate-partner-1 inapp-event-settings::a3adef08=in-app-event-settings-1 h_01KWVSPJ9WV7ZQZD00ZB7T639X=in-app-event-settings-1 inapp-event-postbacks::c3d06354=in-app-event-postbacks-1 h_01KWVSPJ9WA7Q1M281Q5NBYHV7=in-app-event-postbacks-1 attribution-link-tab::3e2b1646=h_01KWVSPJ9WATTRLNK cost-tab::c486dc3c=h_01KWVSPJ9WCOST ad-revenue-tab::84884d8a=h_01KWVSPJ9WADREV permissions-tab::6f805250=h_01KWVSPJ9WPERM h_01KX3DAS0FBTKGKE7CZJTDTY2X=traits-and-limitations h_01KWVT1XJ2FKP1CACRV24C1R8E=see-also" />
