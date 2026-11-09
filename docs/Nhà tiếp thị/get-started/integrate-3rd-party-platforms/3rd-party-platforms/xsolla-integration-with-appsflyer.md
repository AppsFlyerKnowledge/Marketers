---
title: Xsolla integration with AppsFlyer
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
  created_at: '2024-03-25T06:20:28Z'
  edited_at: '2026-06-16T12:08:48Z'
  id: 23593013687185
  locale: en-us
  section: 3rd-party platforms
  section_id: 6551199962257
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/23593013687185-Xsolla-integration-with-AppsFlyer
---
> **At a glance:** Xsolla, an AppsFlyer integrated partner, is a gaming commerce tech partner specializing in payment processing outside of traditional app platforms. The integration between Xsolla and AppsFlyer enables Xsolla to automate Web Shop purchases and revenue to be sent to AppsFlyer, to present the full ROAS and LTV of the game, including purchases made in the Xsolla Web Shop.

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions#hạn-chế-nguồn-truyền-thông">Some media sources</Anchor> restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Integration types

There are two available integration methods with Xsolla:

* [Tech partner integration](#setting-up-the-tech-partner-integration): This integration enables Xsolla to send Web Shop purchases and revenue as mobile in-app events, thereby enhancing the mobile app campaign ROAS and LTV beyond the standard App store purchases.
* [PBA Web SDK integration](#setting-up-the-pba-web-sdk-integration): This integration enables Xsolla to send Web Shop purchases and revenue as web events, allowing AppsFlyer to measure the performance of web campaigns, sending game users directly to the Web Shop.

**Prerequisites:**

* Before setting up the integration, make sure you <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#liên-hệ-với-đối-tác">contact the partner</Anchor> and open an account with them.
* To enable the integration to function properly, make sure to share the Customer User ID (CUID) with AppsFlyer, and that it matches the user ID shared with Xsolla. This alignment allows users to log in to Xsolla's Web Shop and ensures that user data is accurately sent to AppsFlyer.

## Setting up the tech partner integration

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

The configuration window only uses the **Integration** tab.

<div id="integration-tab" />

<Accordion title="Integration tab">

#### Activate partner

On your first visit, you'll need to turn on the **Activate partner** toggle to set up the integration. The toggle must remain on for as long as you work with Xsolla. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">partner activation</Anchor>.

#### Advanced Privacy

For iOS apps, the <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Advance Privacy</Anchor> toggle appears. When turned on, it limits the sharing of user identifiers with the partner. Note that when the <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Aggregated Advanced Privacy</Anchor> toggle is turned on in the App Settings, **Advanced Privacy (for iOS 14.5+ and later)** is turned on and locked by default.

#### Default postbacks

AppsFlyer sends default postbacks to Xsolla following user installs. Use this section to <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#default-postbacks">define these postbacks</Anchor>.

* **Off:** Install postbacks aren't sent to Xsolla.  
  **Note:** Xsolla's integration with AppsFlyer doesn't require sending install postbacks. Therefore, it's recommended to set it to Off.
* **All media sources, including organic:** Install postbacks are sent for events attributed to any partner and for organic events.

<Image align="center" alt="default_postbacks.png" src="https://files.readme.io/e389805491550a494a4d65ae239604fb0210d7c89fce524adaa2ca7d3a3f8ae5-23593013683345.png" />

#### In-app event postbacks

In this section, you can map your AppsFlyer events with your partners via postbacks.

<Image align="center" alt="xsolla-af-login-3.jpg" src="https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg" />

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list.
3. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br /><br />**Note:**<ul><li>For Xsolla, make sure to add the `af_login` event or any other event that represents user login to the mobile app, as shown in the screenshot above.</li></ul> |
| **mapped to partner event** | Enter the corresponding event name you want to send to Xsolla. Xsolla's naming is flexible and any name can be used in this field. |
| **for users from** | Select **All media sources, including organic** to send postbacks for events attributed to any partner and for organic events. |
| **including** | <ul><li>**No values & no revenue**: Send just the event itself without any parameters (values or revenue).</li><li>**Values & no revenue**: Send all the parameters **excluding** the revenue value.</li><li>**Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li></ul>Note: Xsolla's integration with AppsFlyer doesn't require sending values or revenue. Therefore, any option selected is applicable. |

4. Click **Save Integration**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution links aren't available for Xsolla.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data isn't supported in the integration with Xsolla.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue data isn't supported in the integration with Xsolla.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions aren't available for Xsolla.

</Accordion>

## Setting up the PBA Web SDK integration

This integration enables present LTV (Lifetime Value) data and insights for analyzing app performance within the PBA dashboard.

**To set up the integration:**

1. **In AppsFlyer:** <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer?query=adding%20an%20app">Add the Xsolla app</Anchor>. Select <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer#web-pba">Web (PBA)</Anchor> as the platform, and enter the following details:
   * Use your Web Shop domain as the web app URL. For example, if your Web Shop domain is [www.webshop.com,](http://www.webshop.com,) use this as your web app URL.
   * Use any value as the app name.
2. **In AppsFlyer:** <Anchor target="_blank" href="/marketers/vi/docs/pba-brand-bundles-and-settings#add-brand-bundle">Add the Xsolla bundle</Anchor> with the following details:
   1. Enter any bundle name as the bundle name.
   2. Select the web app you created in the previous step as the web app of the bundle.
3. **In Xsolla:** Connect AppsFlyer with your Xsolla Publisher Account:
   1. Open your project in your <Anchor target="_blank" href="https://publisher.xsolla.com/">Publisher Account</Anchor>.
   2. Select your site and click **Configure**.
   3. On the **Site settings** tab, go to the **Apps** section.
   4. In the **AppsFlyer** block, click **Connect**.  
      <Image align="center" alt="xsolla-connect.jpg" src="https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg" />
   5. In the **AppsFlyer Dev Key** field, enter the AppsFlyer Web developer key. See below how to [find this key in AppsFlyer](/docs/xsolla-integration-with-appsflyer#finding-the-web-dev-key-in-appsflyer).
   6. Click **Connect**.

#### Finding the Web dev key in AppsFlyer

1. From the **My apps** page, click **View brand bundles**.
2. Click the Copy icon on the Xsolla bundle row.

<Image align="center" alt="xsolla-brand-bundle2.jpg" src="https://files.readme.io/9cb6a9e872e482f7e426aea7e615afb1f91017c569e7cd67286cdb946d9d2445-26923253273361.jpg" />

## Identifying Xsolla's events in AppsFlyer

### Tech partner (S2S) integration:

Xsolla sends AppsFlyer 2 in-app events:

* **xsolla-billing-payment** - Item purchased
* **xsolla-billing-refund** - Item purchase refund

Both events are part of the mobile app in-app events.

### Web SDK Integration:

Xsolla sends AppsFlyer multiple web events, customized to the specific advertiser activity. The most important one is named "PURCHASE" and contains revenue.  
Xsolla's web events will appear in PBA's web attribution and raw "Web events" DataLocker reports.

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

PC / Console support - the AppsFlyer integration with Xsolla does not support PC / Console Apps at this phase

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="https://developers.xsolla.com/solutions/web-shop/analytics/appsflyer/">Xsolla documentation</Anchor>

<div data-zendesk-anchors="h_01HST42K52VQDWCWGP7TQVFB2X=important h_01J3DB8MCNQKKKCV1M39KN7Q0H=integration-types setting-up-xsolla=setting-up-the-tech-partner-integration h_01HST42K52JKQ70F7Y5PHDZAZ5=setting-up-the-tech-partner-integration h_01HST42K52YZMTE3C2TBTK865M=integration-tab h_01HST42K52RCTSGRNRCJ1C70NP=activate-partner h_01HST42K52BBJ6JS5KM0WCN6CF=advanced-privacy h_01HST47F5BXWV5W8BNHS9M2MTN=default-postbacks inapp-event-postbacks=in-app-event-postbacks h_01H9FKEAV3GG6X17X3NCCSWJAS=in-app-event-postbacks h_01HST42K53GSMD91ACXY9DMP7S=attribution-link-tab h_01HST42K53D0PPXTM7MHBQ8P04=cost-tab h_01HST42K53YS8N6G2V0279F5GA=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab h_01J3DEZZHDPSRZRXDV6FD4HY6Q=setting-up-the-pba-web-sdk-integration h_01J3F247QEAFGRW7CEP941KZE9=finding-the-web-dev-key-in-appsflyer h_01JMHXRGB60RVZ399FNHS18ZHZ=identifying-xsollas-events-in-appsflyer h_01JMHXS5MZ7B781WNNVYMDGGFY=tech-partner-s2s-integration h_01JMHXX7VBPPS7GQ0VBGWRPT7X=web-sdk-integration h_01JN0HXSEJV9JPAXGSBM7B3X7X=traits-and-limitations h_01J1C78W0MP8KXFB4251FKWJBX=see-also" />
