---
title: "[Legacy] X Ads (formerly Twitter Ads) integration setup"
excerpt: "Integrate your X Ads account with AppsFlyer to display attribution data of X Ads campaigns."
---
## Connecting your X Ads account to AppsFlyer

![Connecting your X Ads account to AppsFlyer](https://files.readme.io/2927a35278e64d1d1b44981e81dcc3daf3f739d5bb8edf918b244b75ccb3d883-ac3b44eea6daf9920ca857ad176d1d0d.webp)

### Before you begin

Make sure you've [added a payment method](https://business.twitter.com/en/help/account-setup/billing-basics.html) to your X Ads account. Otherwise, you won't be able to activate the partner integration in AppsFlyer.

1. Log in to your X Ads Account at [ads.twitter.com](https://ads.twitter.com/)

   If you're not automatically directed to the Ads page, click the Ads button at the top-left corner.

2. When prompted to select either a **Simple (NEW)** or **Advanced** campaign, select **Advanced**.
3. Under **Campaign objective**, select **App Installs** or **App re-engagements**, then click **Next**.

   ![twitter-campaign-objective.png](https://files.readme.io/44e5aca3895fc5aefa22f91542b9c23f9798b246ac8086e97a3994244fc2c5a8-36433415100561.png)

4. Choose your app, then click the **mobile measurement partner** link.
5. On the **Conversion tracking** page, click **Go to AppsFlyer**.

   ![twitter-mmp-selection.png](https://files.readme.io/718bc93d2fcf606a8c165aed70364659ba23b74891b22775c5522ee9e4c7901a-36433422307345.png)

6. A notification displays informing you that you're about to leave X Ads to go to the AppsFlyer website. Click **Go to AppsFlyer** and log in to your Dashboard.

   ![twitter-go-to-appsflyer.png](https://files.readme.io/bca10eea5032a495fd38c996d0aa4a9f2db8a285211e6cf0860dd6f21bcfa670-36433422307601.png)

7. In AppsFlyer, from the side menu, select **Collaboration** > **Active Integrations.**
8. Search for **X Ads** and select it.
9. In the **Integration** tab, accept the X Ads Terms and Conditions for Mobile App Conversion Recording (MACT), then click **Save integration**.
10. Turn on **Activate partner**, and click **Log in with X Ads**.
11. Authorize AppsFlyer to use your X Ads account by clicking **Authorize app**.
12. Turn on **Activate Partner** again to display the **Integration** tab settings and enable attribution.

    > 📘 Note
    >
    > The toggle must stay on (activated) for as long as you work with the partner. Learn more about [partner activation.](https://support.appsflyer.com/hc/articles/360000844778)

13. Select your X Ads accounts to activate them, then click **Save & Close**.

    ![twitter_account_name.png](https://files.readme.io/d74e9b3edd08c4ca3396b95ae20e20db99bcbe1a220318403bd6c9d6f9600282-36433415108497.png)

## X Ads attribution setup

For a detailed description of the partner configuration page Header, click [here](https://support.appsflyer.com/hc/articles/4410395957521).

## Integration tab

The **Integration Tab** is divided into different sections, as described below. [Partner must be activated](https://support.appsflyer.com/hc/articles/360000844778) on the first visit to enable its setup.

### Ad account connected

Select the accounts to enable attribution.

![Twitter_msc_new_4.png](https://files.readme.io/8b8ecdfd79bc87d4a65766ce67e48a06524d825e04d5e642eb5e9741069a2f6c-36433422308241.png)

### Click-through attribution

Use the slider to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to X Ads.

You can customize this value to 1-23 hours or 1-30 days. We recommend setting the click-through lookback window to 14 days, to align with X Ads.

![Twitter_msc_new_6.png](https://files.readme.io/359f6145751f45d38c151572f1ba0c525d232d16ffaee6b68453da0bc1826a69-36433422308369.png)

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to the install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to X Ads, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days. We recommend setting the View-through lookback window to 1 day, to align with X Ads.

![Twitter_msc_new_7.png](https://files.readme.io/15c9d815b05c03dfdf8578ed5af297c411991ab74accc5539fc1dbca178c3336-36433422308497.png)

### Re-engagement settings

For retargeting campaigns on X Ads, AppsFlyer supports **Re-engagement** measurement only. That is an engagement with a retargeting campaign by a user who already has the app installed at the time of engagement. **Currently, re-attribution measurement is not supported by X Ads.**

> 📘 Important!
>
    > Ensure Retargeting is enabled for the app on the App Settings page. For details, click [here](https://support.appsflyer.com/hc/articles/211719806-App-settings-#reengagement-attribution).

#### Re-engagement click-through lookback window

Set the duration of the **Re-engagement click-through lookback window** (the maximum period of time after an ad is clicked, within which a retargeted user can be attributed to the ad). You can set the value in hours (up to 23) or days (1-30).

![twitter-reengagement-activate.png](https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png)

#### Re-engagement view-through lookback window

To start attributing impressions of retargeting ads, activate **Re-engagement view-through attribution**.

Then, set the duration of the **Re-engagement view-through lookback window** (the maximum period of time after an ad is viewed, within which a retargeted user can be attributed to the ad). You can set the value in hours (up to 23) or days (1-7):

![twitter-reengagement-view-through.png](https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png)

#### Re-engagement window

Set the duration of the **Re-engagement window** (the period when the user's in-app events are attributed to the retargeting media source). You can set the value in days (1-90), hours (up to 23), or even lifetime:

![Twitter-reengagement-window.png](https://files.readme.io/5bc42bd967929a88fd38f8bdd9cc36046a6f0381d1883ab1f26f5c680185a74c-36433415113105.png)

### In-app event postback settings

In this section, you can map your AppsFlyer events with your partners via postbacks.

![In-app_event_postbacks_en-us.png](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)

**To configure in-app event postbacks:**

1. Set the **Partner ID** (if required).
2. Enable **In-app event postback.**
3. Click **Add event** to add an SDK or server-to-server event to the list.
4. Complete the parameters required according to the table below.

| Parameter | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br>**Tip**: Don't see the event you are looking for?<br>   - Make sure to activate the event on a device with a non-organic installation and recheck.<br>   - Type it in **AppsFlyer event**, then click **Create custom**. Read more about [custom event mapping.](https://support.appsflyer.com/hc/articles/208439256#custom-events) |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible [mapping configurations](https://support.appsflyer.com/hc/articles/208439256#event-mapping):<br>   - **Text field:** Get the corresponding event ID from the partner.<br>   - **Drop-down box:** Select the most suitable pre-defined AppsFlyer event.<br>   - **As is**: Send the events as they are, without name mapping. |
| **for users from** | Select the sending option for the event:<br>#### Note<br>For X Ads to receive agency-attributed postbacks, you must select **All media sources, including organic**. Otherwise, X Ads won't receive such postbacks. <br>   - **This partner only**: send postbacks only when this event is attributed to this partner.<br>   - **All media sources, including organic**: send postbacks for events attributed to any partner and organic events. |
| **including** | - **No data (default)**: send only the event itself without the event value.<br>   - **Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event).<br>   - **Values without revenue**: send all the parameters **excluding** the revenue value. |

5. [Optional] Click ![conditional-iae-postbacks-icon.png](https://files.readme.io/9649c58fb3f46bbb89605e274623e80fbae8d31417694961f0035b7b50276aa9-36433422313105.png) to set conditions for sending certain in-app events to the partner.

Learn more about [conditional in-app event postbacks](https://support.appsflyer.com/hc/articles/208439256#conditional-inapp-event-postbacks).

## Attribution link tab

X Ads does not use attribution links for attribution.

> 📘 Note
>
> For all [self-reporting networks (SRNs)](https://support.appsflyer.com/hc/articles/360001546905-About-self-reporting-networks-SRNs-), such as Meta ads, Apple Ads, Google Ads, X Ads, etc., this tab is not functional since they don't use external attribution links.

## Cost tab

The cost integration provides the following aggregated data:

- Cost data for your campaigns, adsets, ads, channel, and geo/countries. See the [ad network cost integration table](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features.

> 📘 Note
>
> Cost data requires an [ROI360](/docs/roi360-cost-aggregation-overview) subscription.

- Data on clicks, impressions, and enriched data (keywords, campaign names, and adset).

**To enable the cost API**:

- Follow [these integration instructions](https://support.appsflyer.com/hc/articles/360008850257#enable-cost-api).

[View your cost API status](https://support.appsflyer.com/hc/articles/360008850257#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

## Ad revenue tab

Ad revenue is not currently available for X-Ads.

## Permissions tab

In this tab, you can select the permissions to grant X Ads, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for X Ads, the permissions tab is active and you can grant control to X Ads.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

- **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks)
- **Allow to configure in-app event postbacks** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
- **Allow access to your retention report** - only to the partner's own retention data
- **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data
- **Allow access to your aggregate in-app event data** - only to the partner's own in-app event data
- **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner
- **Allow access to your Protect360 dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting [ad network permissions.](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab)

### Agency permissions

Learn about [granting agency permissions](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions).

## Advanced X Ads setup video

![Advanced X Ads setup video](https://files.readme.io/7ee818fcf30290507df5c7140162c0ece46ccf5bae00ad400eabfe22e246434e-4462b8cb8cf072b015f7d74cf52e529f.webp)

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Pre-roll attribution unsupported | X Ads doesn’t support MMP attribution for Pre-roll campaigns. |
| Names | The dashboard shows IDs instead of names for **line item names** (ad set names) and **post names** (ad names). This is because AppsFlyer receives from X Ads only the IDs for these elements and not their names. |
| Cost | For X Ads, cost data for SKAN-only campaigns (campaigns that only have SKAN installs and no "regular" installs) isn't available to agencies. The cost integration must be set up by the advertiser. And the data can only be viewed by the advertiser. |