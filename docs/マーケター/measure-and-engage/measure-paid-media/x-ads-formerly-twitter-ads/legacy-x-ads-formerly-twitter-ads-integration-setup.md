---
title: '[Legacy] X Ads (formerly Twitter Ads) integration setup'
deprecated: true
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
  created_at: '2025-06-22T11:41:06Z'
  edited_at: '2026-10-01T00:33:25Z'
  id: 36433415114769
  locale: ja
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/ja/articles/36433415114769
---
> **At a glance:** Integrate your X Ads account with AppsFlyer to display attribution data of X Ads campaigns.

## Connecting your X Ads account to AppsFlyer

<Accordion title="Watch">

<Embed title="[Legacy] X Ads (formerly Twitter Ads) integration setup" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/a65pnqoyxw" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Read">

> 📘 **Before you begin**
>
> Make sure you've <Anchor target="_blank" href="https://business.twitter.com/en/help/account-setup/billing-basics.html">added a payment method</Anchor> to your X Ads account. Otherwise, you won't be able to activate the partner integration in AppsFlyer.

1. Log in to your X Ads Account at <Anchor target="_blank" href="https://ads.twitter.com">ads.twitter.com</Anchor>  
   If you're not automatically directed to the Ads page, click the Ads button at the top-left corner.
2. When prompted to select either a **Simple (NEW)** or **Advanced** campaign, select **Advanced**.
3. Under **Campaign objective**, select **App Installs** or **App re-engagements**, then click **Next**.

   ![twitter-campaign-objective.png](https://files.readme.io/44e5aca3895fc5aefa22f91542b9c23f9798b246ac8086e97a3994244fc2c5a8-36433415100561.png)
4. Choose your app, then click the **mobile measurement partner** link.
5. On the **Conversion tracking** page, click **Go to AppsFlyer**. 

   ![twitter-mmp-selection.png](https://files.readme.io/718bc93d2fcf606a8c165aed70364659ba23b74891b22775c5522ee9e4c7901a-36433422307345.png)
6. A notification displays informing you that you're about to leave X Ads to go to the AppsFlyer website. Click **Go to AppsFlyer** and log in to your Dashboard.

   <Image alt="twitter-go-to-appsflyer.png" src="https://files.readme.io/bca10eea5032a495fd38c996d0aa4a9f2db8a285211e6cf0860dd6f21bcfa670-36433422307601.png" width="576px" />
7. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations > Marketplace** tab.
8. Search for **X Ads** and select it.
9. In the **Integration** tab, accept the X Ads Terms and Conditions for Mobile App Conversion Recording (MACT), then click **Save integration**.
10. Turn on **Activate partner**, and click **Log in with X Ads**.
11. Authorize AppsFlyer to use your X Ads account by clicking **Authorize app**.

    [<Image alt="" src="https://support.appsflyer.com/hc/en-us/article_attachments/4411037924497/Twitter_Ads_6.png" width="476px" />](https://support.appsflyer.com/hc/en-us/article_attachments/4411037924497/Twitter_Ads_6.png)
12. Turn on **Activate Partner** again to display the **Integration** tab settings and enable attribution.  
    **Note:** The toggle must stay on (activated) for as long as you work with the partner. Learn more about <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">partner activation.</Anchor>
13. Select your X Ads accounts to activate them, then click **Save & Close**.

    ![twitter_account_name.png](https://files.readme.io/d74e9b3edd08c4ca3396b95ae20e20db99bcbe1a220318403bd6c9d6f9600282-36433415108497.png)

</Accordion>

## X Ads attribution setup

For a detailed description of the partner configuration page Header, click <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">here</Anchor>.

<div id="integration-tab" />

<Accordion title="Integration tab">

The **Integration Tab** is divided into different sections, as described below. <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">Partner must be activated</Anchor> on the first visit to enable its setup.

### Ad account connected

Select the accounts to enable attribution.

![Twitter_msc_new_4.png](https://files.readme.io/8b8ecdfd79bc87d4a65766ce67e48a06524d825e04d5e642eb5e9741069a2f6c-36433422308241.png)

### Click-through attribution

Use the slider to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to X Ads.

You can customize this value to 1-23 hours or 1-30 days. We recommend setting the click-through lookback window to 14 days, to align with X Ads.

![Twitter_msc_new_6.png](https://files.readme.io/359f6145751f45d38c151572f1ba0c525d232d16ffaee6b68453da0bc1826a69-36433422308369.png)

### View-through attribution lookback window

This slider allows you to set the **maximum time from impression to the install**. Only installs (first launches) that take place within this lookback window, following an ad impression, are attributed to X Ads, providing there was no other relevant ad click.

You can customize this value to 1-23 hours or 1-7 days. We recommend setting the View-through lookback window to 1 day, to align with X Ads.

![Twitter_msc_new_7.png](https://files.readme.io/15c9d815b05c03dfdf8578ed5af297c411991ab74accc5539fc1dbca178c3336-36433422308497.png)

### Re-engagement settings

For retargeting campaigns on X Ads, AppsFlyer supports **Re-engagement** measurement only. That is an engagement with a retargeting campaign by a user who already has the app installed at the time of engagement. **Currently, re-attribution measurement is not supported by X Ads.**

> 🚧 **Important!**
>
> Ensure Retargeting is enabled for the app on the App Settings page. For details, click <Anchor target="_blank" href="/marketers/ja/docs/app-settings#reengagement-attribution">here</Anchor>.

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

[![In-app_event_postbacks_en-us.png](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)

**To configure in-app event postbacks:**

1. Set the **Partner ID** (if required).
2. Enable **In-app event postback.**
3. Click **Add event** to add an SDK or server-to-server event to the list.
4. Complete the parameters required according to the table below.

| Parameter | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#イベントマッピング">mapping configurations</Anchor>:<ul><li>**Text field:** Get the corresponding event ID from the partner.</li><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li><li>**As is**: Send the events as they are, without name mapping.</li></ul> |
| **for users from** | Select the sending option for the event:<br /><br /><br /><br />**Note**<br />For X Ads to receive agency-attributed postbacks, you must select **All media sources, including organic**. Otherwise, X Ads won't receive such postbacks.<ul><li>**This partner only**: send postbacks only when this event is attributed to this partner.</li><li>**All media sources, including organic**: send postbacks for events attributed to any partner and organic events.</li></ul> |
| **including** | <ul><li>**No data (default)**: send only the event itself without the event value.</li><li>**Values and revenue**: send all the event parameters, **including** the revenue value (if exists in the event).</li><li>**Values without revenue**: send all the parameters **excluding** the revenue value.</li></ul> |

5. [Optional] Click <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> to set conditions for sending certain in-app events to the partner.  
   Learn more about <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">conditional in-app event postbacks</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

X Ads does not use attribution links for attribution.

> 📘 **Note**
>
> For all <Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">self-reporting networks (SRNs)</Anchor>, such as Meta ads, Apple Ads, Google Ads, X Ads, etc., this tab is not functional since they don't use external attribution links.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

The cost integration provides the following aggregated data:

* Cost data for your campaigns, adsets, ads, channel, and geo/countries. See the <Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network cost integration table</Anchor> for full details on the supported dimensions, metrics, and features.  
  **Note:** Cost data requires an <Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> subscription.
* Data on clicks, impressions, and enriched data (keywords, campaign names, and adset).

**To enable the cost API**:

* Follow <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">these integration instructions</Anchor>.

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">View your cost API status</Anchor> and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue is not currently available for X-Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can select the permissions to grant X Ads, whether the partner acts as an ad network, agency, or even both. Note that even if attribution is disabled for X Ads, the permissions tab is active and you can grant control to X Ads.

Use these toggles to give the ad network permissions to handle its own configuration for your app:

### Ad network permissions

* **Allow to configure integration** - permit the partner to set up the integration tab (except in-app event postbacks)
* **Allow to configure in-app event postbacks** - permit the partner to setup in-app event postbacks mapping to itself on the integration tab
* **Allow access to your retention report** - only to the partner's own retention data
* **Allow access to your aggregate loyal user data** - only to the partner's own loyal user data
* **Allow access to your aggregate in-app event data** - only to the partner's own in-app event data
* **Allow access to your aggregate revenue data** - only to the revenue data attributed to the partner
* **Allow access to your Protect360 dashboard** - only to the partner's own Protect360 data, and providing the feature is enabled for the advertiser

Learn more about granting <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">ad network permissions.</Anchor>

### Agency permissions

Learn about <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#代理店の許可">granting agency permissions</Anchor>.

</Accordion>

## Advanced X Ads setup video

<Accordion title="Watch">

<Embed title="[Legacy] X Ads (formerly Twitter Ads) integration setup" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/3ypfld8enr" providerUrl="https://fast.wistia.com" />

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Pre-roll attribution unsupported | X Ads doesn’t support MMP attribution for Pre-roll campaigns. |
| Names | The dashboard shows IDs instead of names for **line item names** (ad set names) and **post names** (ad names). This is because AppsFlyer receives from X Ads only the IDs for these elements and not their names. |
| Cost | For X Ads, cost data for SKAN-only campaigns (campaigns that only have SKAN installs and no "regular" installs) isn't available to agencies. The cost integration must be set up by the advertiser. And the data can only be viewed by the advertiser. |

Traits and limitations

</Accordion>

<div data-zendesk-anchors="connecting-your-twitter-ads-account-to-appsflyer=connecting-your-x-ads-account-to-appsflyer h_01HDJVCRYQESA17XZ83GS81YZ3=connecting-your-x-ads-account-to-appsflyer h_01HDJVBAEZXA0WJ94JYMK84MAX=before-you-begin twitter-ads-attribution-setup=x-ads-attribution-setup h_01HDJVBAEZ5W3JH1BN7WXJ08P6=x-ads-attribution-setup h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab h_01HDJVBAEZD89BSGHQTPR84HSC=ad-account-connected clickthrough-attribution=click-through-attribution h_01HDJVBAEZFJWQ6FD4Q4GSPD76=click-through-attribution viewthrough-attribution-lookback-window=view-through-attribution-lookback-window h_01HDJVBAEZ2H91WBHNSMRQYQ7H=view-through-attribution-lookback-window reengagement-settings=re-engagement-settings h_01HDJVBAEZZR1W06YH4XJSBKHV=re-engagement-settings h_01JV9YQ7ZHRDD2NA5ENQXJQ31V=important reengagement-clickthrough-lookback-window=re-engagement-click-through-lookback-window h_01HDJVBAEZ59ERYD2WQQYK6T37=re-engagement-click-through-lookback-window reengagement-viewthrough-lookback-window=re-engagement-view-through-lookback-window h_01HDJVBAEZSCK7430NJ8AMQYVY=re-engagement-view-through-lookback-window reengagement-window=re-engagement-window h_01HDJVBAEZCMWY5X47FEEFXTBX=re-engagement-window inapp-event-postback-settings=in-app-event-postback-settings h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=in-app-event-postback-settings h_01HDJVBAEZATGM580CNC7BCVTN=note h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=note h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab h_01HDJVBAF0VPBBAEHJPG40HJP8=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab h_01HDJVBAF0BMSCKF6J9NJ019YJ=ad-network-permissions h_01HDJVBAF0W3ZE7J93CRE8EBRP=agency-permissions advanced-twitter-ads-setup-video=advanced-x-ads-setup-video h_01HDJVBAF0SJ93TNQ8WSFVE91P=advanced-x-ads-setup-video h_01HGWGG2422VR9PFV88AMEHNT8=traits-and-limitations" />
