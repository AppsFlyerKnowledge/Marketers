---
title: "Xsolla integration with AppsFlyer"
excerpt: "Learn how to integrate Xsolla with AppsFlyer to automate Web Shop purchases and revenue tracking, presenting the full ROAS and LTV of your game."
---
Xsolla, an AppsFlyer integrated partner, is a gaming commerce tech partner specializing in payment processing outside of traditional app platforms. The integration between Xsolla and AppsFlyer enables Xsolla to automate Web Shop purchases and revenue to be sent to AppsFlyer, to present the full ROAS and LTV of the game, including purchases made in the Xsolla Web Shop.

> ❗️ Important!
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Integration types

There are two available integration methods with Xsolla:

- [Tech partner integration](/docs/xsolla-integration-with-appsflyer#setting-up-xsolla): This integration enables Xsolla to send Web Shop purchases and revenue as mobile in-app events, thereby enhancing the mobile app campaign ROAS and LTV beyond the standard App store purchases.
- [PBA Web SDK integration](/docs/xsolla-integration-with-appsflyer#setting-up-the-pba-web-sdk-integration): This integration enables Xsolla to send Web Shop purchases and revenue as web events, allowing AppsFlyer to measure the performance of web campaigns, sending game users directly to the Web Shop.

**Prerequisites:**

- Before setting up the integration, make sure you [contact the partner](/docs/partner-integrations#contact-details) and open an account with them.
- To enable the integration to function properly, make sure to share the Customer User ID (CUID) with AppsFlyer, and that it matches the user ID shared with Xsolla. This alignment allows users to log in to Xsolla's Web Shop and ensures that user data is accurately sent to AppsFlyer.

## Setting up the tech partner integration

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

The configuration window only uses the **Integration** tab.

### Integration tab

#### Activate partner

On your first visit, you'll need to turn on the **Activate partner** toggle to set up the integration. The toggle must remain on for as long as you work with Xsolla. Learn more about [partner activation](/docs/partner-activation-deactivation).

#### Advanced Privacy

For iOS apps, the [Advance Privacy](/docs/apply-aggregated-advanced-privacy-framework) toggle appears. When turned on, it limits the sharing of user identifiers with the partner. Note that when the [Aggregated Advanced Privacy](/docs/apply-aggregated-advanced-privacy-framework) toggle is turned on in the App Settings, **Advanced Privacy (for iOS 14.5+ and later)** is turned on and locked by default.

#### Default postbacks

AppsFlyer sends default postbacks to Xsolla following user installs. Use this section to [define these postbacks](/docs/set-up-an-integrated-partner#default%20postbacks).

- **Off:** Install postbacks aren't sent to Xsolla.

> 📘 Note
>
> Xsolla's integration with AppsFlyer doesn't require sending install postbacks. Therefore, it's recommended to set it to Off.

- **All media sources, including organic:** Install postbacks are sent for events attributed to any partner and for organic events.

<Image src="https://files.readme.io/e389805491550a494a4d65ae239604fb0210d7c89fce524adaa2ca7d3a3f8ae5-23593013683345.png" alt="default_postbacks.png" />

#### In-app event postbacks

In this section, you can map your AppsFlyer events with your partners via postbacks.

<Image src="https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg" alt="xsolla-af-login-3.jpg" />

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list.
3. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Note:**<br />   - For Xsolla, make sure to add the `af_login` event or any other event that represents user login to the mobile app, as shown in the screenshot above. |
| **mapped to partner event** | Enter the corresponding event name you want to send to Xsolla. Xsolla's naming is flexible and any name can be used in this field. |
| **for users from** | Select **All media sources, including organic** to send postbacks for events attributed to any partner and for organic events. |
| **including** | - **No values & no revenue**: Send just the event itself without any parameters (values or revenue).<br />   - **Values & no revenue**: Send all the parameters **excluding** the revenue value.<br />   - **Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).<br />Note: Xsolla's integration with AppsFlyer doesn't require sending values or revenue. Therefore, any option selected is applicable. |

4. Click **Save Integration**.

### Attribution link tab

Attribution links aren't available for Xsolla.

### Cost tab

Cost data isn't supported in the integration with Xsolla.

### Ad revenue tab

Ad revenue data isn't supported in the integration with Xsolla.

### Permissions tab

Permissions aren't available for Xsolla.

## Setting up the PBA Web SDK integration

This integration enables present LTV (Lifetime Value) data and insights for analyzing app performance within the PBA dashboard.

**To set up the integration:**

1. **In AppsFlyer:** [Add the Xsolla app](/docs/adding-an-app-to-appsflyer). Select [Web (PBA)](/docs/adding-an-app-to-appsflyer#web-pba) as the platform, and enter the following details:
   - Use your Web Shop domain as the web app URL. For example, if your Web Shop domain is [www.webshop.com,](http://www.webshop.com/) use this as your web app URL.
   - Use any value as the app name.
2. **In AppsFlyer:** [Add the Xsolla bundle](/docs/pba-brand-bundles-and-settings#add-brand-bundle) with the following details:
   1. Enter any bundle name as the bundle name.
   2. Select the web app you created in the previous step as the web app of the bundle.
3. **In Xsolla:** Connect AppsFlyer with your Xsolla Publisher Account:
   1. Open your project in your [Publisher Account](https://publisher.xsolla.com/).
   2. Select your site and click **Configure**.
   3. On the **Site settings** tab, go to the **Apps** section.
   4. In the **AppsFlyer** block, click **Connect**.

      <Image src="https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg" alt="xsolla-connect.jpg" />
   5. In the **AppsFlyer Dev Key** field, enter the AppsFlyer Web developer key. See below how to [find this key in AppsFlyer](/docs/xsolla-integration-with-appsflyer#finding-the-web-dev-key-in-appsflyer).
   6. Click **Connect**.

#### Finding the Web dev key in AppsFlyer

1. From the **My apps** page, click **View brand bundles**.
2. Click the Copy icon on the Xsolla bundle row.

<Image src="https://files.readme.io/9cb6a9e872e482f7e426aea7e615afb1f91017c569e7cd67286cdb946d9d2445-26923253273361.jpg" alt="xsolla-brand-bundle2.jpg" />

## Identifying Xsolla's events in AppsFlyer

### Tech partner (S2S) integration:

Xsolla sends AppsFlyer 2 in-app events:

- **xsolla-billing-payment** - Item purchased
- **xsolla-billing-refund** - Item purchase refund

Both events are part of the mobile app in-app events.

### Web SDK Integration:

Xsolla sends AppsFlyer multiple web events, customized to the specific advertiser activity. The most important one is named "PURCHASE" and contains revenue.

Xsolla's web events will appear in PBA's web attribution and raw "Web events" DataLocker reports.

### Traits and limitations

PC / Console support - the AppsFlyer integration with Xsolla does not support PC / Console Apps at this phase

<Cards>
  <Card title="Xsolla documentation" href="https://developers.xsolla.com/solutions/web-shop/analytics/appsflyer/">
    View the official integration guide on Xsolla's developer portal.
  </Card>
</Cards>