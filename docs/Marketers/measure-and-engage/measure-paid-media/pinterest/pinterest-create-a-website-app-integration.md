---
title: Pinterest—Create a website app integration
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-06-14T13:07:07Z'
  edited_at: '2026-08-30T15:36:14Z'
  id: 47721580892433
  locale: en-us
  section: Pinterest
  section_id: 6551388216337
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/47721580892433-Pinterest-Create-a-website-app-integration
---
**At a glance:** Set up a Pinterest integration for your website app to send web conversion events to Pinterest for campaign optimization and reporting.

## **Set up integration**

**Prerequisites:**

* An account with Pinterest
* A website app set up in AppsFlyer. <Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer#web">Learn more</Anchor>
* The AppsFlyer <Anchor target="_blank" href="/marketers/docs/integrate-appsflyer-web-sdk">Web SDK</Anchor> or <Anchor target="_blank" href="/marketers/docs/server-to-server-s2s-api-for-web-performance-measurement">Server-to-Server (S2S) API</Anchor> for web attribution

**To activate or edit the integration:**

1. **To activate:** In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Marketplace** tab.  
   **To edit:** In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active integrations** tab.
2. Select your website app from the dropdown menu above.
3. Search for Pinterest and click **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.  
   **Note:** The toggle must remain on <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">(activated)</Anchor> for as long as you work with Pinterest.
5. Complete the configuration in the **Integration** tab as described below.

## **Integration tab**

### **Activate partner**

On the **first visit**, turn on the **Activate Partner** toggle to enable setup of the integration tab's parameters. The toggle must remain on for as long as you work with Pinterest.

Learn more about <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">partner activation</Anchor>.

### **In-app event settings**

To send in-app event postbacks to Pinterest, provide the following Pinterest credentials. These credentials are included in the event postbacks sent to Pinterest.

* **Ad Account ID** - The unique identifier of your Pinterest ad account.
* **Access Token** - An access token generated in Pinterest.

You can find your Ad Account ID and Access Token in the Pinterest Ads Manager UI (see the <Anchor target="_blank" href="https://developers.pinterest.com/docs/api-features/tracking-conversions/#getting-your-access-token-and-ad-account-id">Pinterest documentation</Anchor>). Contact Pinterest support if you need assistance.

**To set the Pinterest credentials:**

1. In AppsFlyer, on the Pinterest **Active integration** page > **Integration** tab, scroll to **In-app event settings**.
2. Enter the Ad Account ID and Access Token values in their respective fields.

### **In-app event postbacks**

In this section, you map your AppsFlyer web events to Pinterest events via postbacks.

1. In the Pinterest integration settings, scroll to
   **In-app event postbacks**.
2. Turn on **In-app event postbacks**.
3. Set the in-app event postback window.
4. Select the postback settings and mappings for events.

| **Parameter name** | **Description** |
| --- | --- |
| **AppsFlyer event name** | The name of the web event, as received by AppsFlyer from either the Web SDK integrated on your website or from server-to-server events.<br /><br />**Note:** If you don't see the event you want in the list, make sure the event has been activated and recheck. |
| **Partner event name** | The Pinterest event to map to, selected from Pinterest's predefined event list. For Pinterest event names, see the <Anchor target="_blank" href="https://developers.pinterest.com/docs/api-features/track-conversion-events/#understand-conversion-events">Pinterest documentation</Anchor>. |
| **To users from** | **This partner only:** Events coming only from users attributed to Pinterest.<br /><br />**All media sources, including organic:** Your entire user base is available to be reported to the partner. |
| **Including** | Select whether event revenue or parameter values are sent to the partner in the postback. AppsFlyer can send all parameters of the rich web event except the revenue parameter (contained in **af\_revenue**), or all parameters including the revenue value (if present). |

> 📘 **Note**
>
> If you also run the Pinterest Tag on your website, send the same event ID to both AppsFlyer and Pinterest so AppsFlyer can deduplicate the events:
>
> * Include af\_customer\_event\_id in the event payload you send to AppsFlyer, inside eventValue for the Web SDK or event\_value for the S2S (server-to-server) API.
> * Send the same value in the corresponding Tag event.
>
> AppsFlyer forwards this value to Pinterest as the event ID. Pinterest then uses it to deduplicate the server-side event it receives from AppsFlyer against the Tag event, so AppsFlyer counts the conversion once.
>
> If you don't send af\_customer\_event\_id, AppsFlyer generates an event ID automatically. This ID won't match your Tag events.
>
> For more information, see Integrate AppsFlyer Web SDK.

5. Click **Add Event** to add an event to the list.

<div data-zendesk-anchors="set-up-pinterest=set-up-integration h_01KV339A5ZGK96JNCNR78PDMNH=set-up-integration h_01KV339A67N4436STPW1VJR585=integration-tab h_01KV339A67H0DSSJ3P84PXGQ2F=activate-partner inapp-event-settings=in-app-event-settings h_01KV339A68YZBZZ73T8XTBE6BR=in-app-event-settings inapp-event-postbacks=in-app-event-postbacks h_01KV339A6BN0CWYX7GCJ19RN0J=in-app-event-postbacks" />
