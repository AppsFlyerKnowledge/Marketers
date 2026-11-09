---
title: Google Marketing Platform - Display & Video 360 (DV360) integration
metadata:
  keywords:
    - Advertisers
    - Agencies
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
  created_at: '2021-02-02T17:40:13Z'
  edited_at: '2026-09-09T13:14:48Z'
  id: 360017595598
  locale: en-us
  section: Google Marketing Platform (GMP)
  section_id: 6551212604305
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360017595598-Google-Marketing-Platform-Display-Video-360-DV360-integration
---
> **At a glance:** Google Marketing Platform - Display & Video 360 (GMP-DV360) is an AppsFlyer self-reporting network (SRN) partner combining advertising and analytics. The GMP-DV360 integration  (dv360\_int) combines advertising and analytics to enhance customer connections, reveal insights, and improve marketing outcomes.

> 🚧 **Important!**
>
> See the bulletin about <Anchor target="_blank" href="/marketers/vi/docs/bulletin-supporting-the-new-google-eu-consent-policy">supporting the new Google EU consent policy</Anchor>.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png" width="121px" />

## Overview

The GMP-DV360 integration uses the link ID for conversion measurement. You can work directly with GMP-DV360, via an agency, or both, using the following integrations:

* [DV360 for advertisers](#setting-up-gmp-dv360-for-advertisers): Complete once—mandatory
* [DV360 for agencies](#setting-up-gmp-dv360-for-agencies): Optional per agency

> 📘 **Note**
>
> Keep the following in mind:
>
> * The GMP-DV360 integration is designed to replace the Legacy GMP DV360/CM (doubleclick\_int) integration, which will be deprecated by the end of Q2, 2024.
> * To use the API, contact your GMP-DV360 account manager.

The table below describes GMP integration solutions:

| GMP solution | Description | Action required to integration |
| --- | --- | --- |
| DV360 | Integrate DV360 with AppsFlyer to measure dv360\_int attribution | Complete the [advertiser integration](#setting-up-gmp-dv360-for-advertisers) |
| CM360 & DV360 | Buy DV360 traffic via CM360, measured as dv360\_int attribution in AppsFlyer. | Complete the [advertiser integration](#setting-up-gmp-dv360-for-advertisers) |
| CM360 & non-DV360 third-party media source | Buy traffic from third-party media sources and measure mobile app conversions originating from this traffic in CM360. | <Anchor target="_blank" href="/marketers/vi/docs/gmp-use-case-of-traffic-measurement-from-3rd-parties-in-cmp360">Measure 3rd party traffic using CM360</Anchor> |

### Data sharing between AppsFlyer and GMP - DV360

**Data provided by AppsFlyer:** AppsFlyer sends postbacks to GMP-DV360 relating to conversions and in-app events.

**Data provided to AppsFlyer:** When GMP-DV360 claims a conversion, they provide AppsFlyer with the media source parameters. These parameters populate analytics and raw data reports. The table below shows the mapping parameters for GMP-DV360 and AppsFlyer.

| GMP | AppsFlyer |
| --- | --- |
| `interaction type` | `attributed_touch_type` |
| `timestamp` | `attributed_touch_time` |
| `line_item_id` | `campaign_id` |
| `line_item_name` | `campaign_name` |
| `creative_id` | `ad_id` |
| `product_type` | `af_channel` |
| `external_customer_id` | `network_account_id` |
| `site_id` | `af_siteid` |
| `insertion_order_id` | `af_sub4` |

## Setting up GMP-DV360 for advertisers

**Prerequisites**

Before setting up the integration, make sure to:

* <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#liên-hệ-với-đối-tác">Contact the partner</Anchor> and open an account with them.
* <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/10956727">Get the GMP-DV360 link ID</Anchor>.

  > 📘 **Note**
  >
  > The link ID from DV360 must comply with the following:
  >
  > * It must contain numbers and letters.
  > * It must be longer than 20 characters.
  > * Android and iOS must each use a different link ID.


**To set up a new integration:**  
  
**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

<div id="integration-tab" />

<Accordion title="Integration tab">

When AppsFlyer queries GMP-DV360, they return the parameters listed in their response. These are mapped to AppsFlyer parameters and raw data as detailed in the table that follows.

| GMP - legacy parameter | GMP-DV360 parameter | AppsFlyer parameter | URL parameter |
| --- | --- | --- | --- |
| Placement ID | Line Item Name | Campaign name | c |
| Placement ID | Line Item ID | Campaign ID | af\_c\_id |
| Site ID | Site ID | Site ID | af\_siteid |
| Creative ID | Creative ID | Ad ID | af\_ad\_id |

<span id="activate-partner::e4f2f638"></span>The **Integration** tab includes a number of sections, as described below.

#### Activate partner

To configure the integration, you must first turn on the **Activate partner** toggle. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation#activate-a-partner-integration">activating and deactivating partner</Anchor> integrations.

#### General settings

**Link ID:** Enter the link ID mentioned in the prerequisites.

**Non EU Users:** Decide whether or not to turn on <Anchor target="_blank" href="/marketers/vi/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**Non EU users**</Anchor>.

<Image align="center" alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="536px" />

#### Install attribution

Set the different attribution windows to attribute new installs (first launches) of users who viewed or clicked your ad. This means the maximum time from click/view to the install. Only installs within the lookback window may be attributed to Google Marketing Platform - Display & Video 360 (DV360).

1. Set the **Install click-through lookback window** to either 1-23 hours or 1-30 days.
2. [Optional] Turn on **Install view-through attribution** and set the lookback window to either 1-23 hours or 1-7 days.

#### Re-engagement attribution

Set the different attribution windows to attribute re-engagements of your existing users who viewed or clicked your ad. Note that only re-engagements within the lookback window may be attributed to GMP-DV360.

1. Set the **Re-engagement click-through lookback window** to either 1-23 hours or 1-30 days.
2. [Optional] Turn on **Re-engagement view-through attribution** and set the lookback windows to either 1-23 hours or 1-7 days.

> 📘 **Note**
>
> Re-attribution is not supported for DV360 campaigns

Learn more about re-engagement <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide#reengagement-rules-and-windows">rules and windows</Anchor>.

#### Re-engagement window

Set the time window during which in-app events are primarily attributed to the re-engagement conversion. <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide#setup-reengagement-window">Learn more</Anchor>.

* Set the **Re-engagement window** to either 1-23 hours, 1-90 days, or **Lifetime**.

#### Ignore active users for retargeting

Set a window timeframe to <Anchor target="_blank" href="/marketers/vi/docs/set-retargeting-inactivity-window#inactivity-period">ignore re-engagements</Anchor> of users who launched your app. This means their activity during the window timeframe isn't recorded in AppsFlyer.

> 📘 **Note**
>
> Re-engagement conversions of users who were **dormant** in the set timeframe **are recorded**.

1. Turn on **Ignore active users for retargeting**.
2. Set the Inactivity window.

#### In-app event postbacks

Configure mapping of in-app events with GMP-DV360 events sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | The name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events.<br />**Tip**: Don't see the event you are looking for?<ul><li>Make sure to activate the event on a device with a non-organic installation, and recheck.</li><li>Type it in **AppsFlyer event**, then click **Create custom**. Read more about <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">custom event mapping.</Anchor></li></ul> |
| **mapped to partner event** | The unique name or ID of each event, as defined on the partner's side. Possible mapping configurations are:<ul><li>**Drop-down box:** Select the most suitable pre-defined AppsFlyer event.</li></ul>**Note:**<ul><li>It's best practice to select a standard event from the list. However, for multiple CUSTOM events, it's best to specify them uniquely, such as CUSTOM\_1 and CUSTOM\_2. This will help distinguish between events on DV360/CM360.</li><li>AppsFlyer events (such as `af_purchase`, etc.) are always sent with `u` variables, for example, `u24=`. This helps you identify them on CM360, even when sent as custom.</li><li>CM360 allows a maximum of 10 custom events, on top of all standard events</li></ul> |
| **for users from** | Select the sending option for the event:<ul><li>**This partner only** (default): Send postbacks only when this event is attributed to GMP-DV360.</li><li>**All media sources including organic**: Send postbacks for events attributed to any partner, as well as organic events.</li></ul> |
| **including** | <ul><li>**No values & no revenue** (default): Send only the event itself without any event values.</li><li>**Values & no revenue**: Send all the parameters **excluding** the revenue value.</li><li>**Values & revenue**: Send all the event parameters, **including** the revenue value (if exists in the event).</li></ul> |

3. [Optional] Click the **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/adc9e4826101d528a07ea04b88c323030258dcf891d9ba419baed60e662cdda1-22715359959697.png" width="30px" />icon to <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#conditional-in-app-event-postbacks">set conditions</Anchor> for an event.
4. Click **Save integration**.
5. [Optional] After saving the integration, while remaining on the configuration page, you can integrate more of your apps with GMP-DV360:
   1. From the top-left corner, under the partner name, click the app name to open the list of apps.
   2. Select a different app from the drop-down list.
   3. Repeat the integration steps for the selected app.

> 📘 **Note**
>
> For iOS apps only: Your control over data shared with the partner via postbacks and <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">reports</Anchor> depends on the **Advanced Privacy (for iOS 14.5+ and later)** [toggle state](#advanced-privacy).

#### U parameter mapping

AppsFlyer supports sending additional parameters (u parameters), limited up to u26. The U parameters are pre-mapped and fixed on AppsFlyer's end. Take the following into consideration:

* Because these parameters are pre-mapped, no additional custom U parameters can be configured.
* If data is missing for a specific U parameter, AppsFlyer won't send it. For example, when the carrier data is missing, AppsFlyer doesn't send U5.

| U parameter | Name | Example value |
| --- | --- | --- |
| u1= | af device id | 1540995037437-2811776739500410055 |
| u2= | customer user id | eaf8a5f2.1836.4686 |
| u3= | **Android**:  <br />Advertising id  <br />**iOS**: idfa | 9d9d03ab-f211-4e17-994e-d0afdf23ac01 |
| u4= | wifi | true |
| u5= | carrier | Jio%204G |
| u6= | country code | IN |
| u7= | Region | HR |
| u8= | city | Gurgaon |
| u9= | device type | motorola::Moto G (4) |
| u10= | os version | 7 |
| u11= | sdk version | v4.8.18 |
| u12= | app version | 3.31.1 |
| u13= | install timestamp | 1540995041 |
| u14= | click time | 1546441586 |
| u15= | impression time | 1546441586 |
| u16= | campaign name* | Appinstall\_campaign |
| u17= | campaign id | 12345ABC |
| u18= | adset name* | Appinstall\_adset |
| u19= | adset id | 12345ABC |
| u20= | ad name* | Appinstall\_ad |
| u21= | ad id | 1234567ABCDE |
| u22= | site id | site\_id\_123456 |
| u23= | event time | 2019-01-04 12:56:35.707 |
| u24= | event name | af\_purchase |
| u25= | event value | `{"af_price":459,"af_content_id":"77147","af_revenue":4.59,"af_currency":"EUR"}` |
| u26= | currency | EUR |

* If AppsFlyer doesn't receive this parameter name in the response from GMP-DV360,  it populates the field with the corresponding ID. For example, the Adset name will show the Adset ID, which is `12345ABC`.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

You can **use AppsFlyer attribution links with DV360 for impressions and click recording only**. These links are NOT used for attribution, and any additional information contained within them is not parsed or used for any purpose.

If you want to be able to measure the number of clicks from DV360 on AppsFlyer, we recommend adding an AppsFlyer attribution URL on your DV360 dashboard, via CM360. When doing so, make sure the campaign name in the attribution URL **is identical** to the **line item name** on GMP (if possible) so that AppsFlyer can retrieve and append the click data for the correct campaigns.

> 🚧 **Important!**
>
> Using attribution links for DV360 is not mandatory.
>
> **Limitation:** Attribution links for DV360 that include the `af_prt` parameter are currently **not supported for agency accounts**.

If you want to count **clicks** in AppsFlyer, use this link:

```http
https://app.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=${UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

If you want to count **impressions** in AppsFlyer use this link:

```http
https://impression.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=%24{UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="Cost tab (for cost, clicks, and impressions)">

Cost, clicks, and impressions are supported for this integration through ROI360.

ROI360 customers can create and edit cost integrations in the **Cost tab** and in **Cost settings**. See <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">how to enable cost integration</Anchor>.

Starting September 7, 2026, clicks and impressions will no longer be reported through attribution. To keep receiving these metrics, set up the DV360 SRN/Cost integration.

> 📘 **Note**
>
> Clicks and impressions for this integration are reported in:
>
> * Dashboards
> * Cost ETL reports (ROI360 customers only)
> * AppsFlyer's aggregated APIs
>
> Depending on when DV360 integration activation takes place, a temporary discrepancy may occur in each of the above:
>
> * Activation on or before September 6: clicks and impressions are reported twice during this period, once from AppsFlyer attribution and once from the DV360 API, so a temporary discrepancy is expected.
> * Activation up to September 12: a discrepancy is expected on some dates, due to DV360's last-7-days auto-backfill.
> * Activation after September 12: no discrepancy is expected.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue isn't supported for this integration.

</Accordion>

## Setting up GMP-DV360 for agencies

Agencies are able to run campaigns with GMP-DV360 on your behalf.

#### Agency setup

| Procedure performed by | Procedure |
| --- | --- |
| Advertiser | <ol><li>Verify that you've completed advertiser GMP-DV360 integration.</li><li>In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.</li><li>Select an agency.</li><li>Go to the **Permissions** tab, and turn on **Agency permissions**.</li><li>[Optional] In the **Integration** tab turn on **In-app event postback**. This enables the agency to turn on or off postbacks on their end.</li></ol> |
| Agency | <ol><li>In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations**.</li><li>Select **Google Marketing Platform - Display & Video 360 (DV360).**</li><li>Go to the **Integration tab**.<br />The integration status with GMP displays. [![mceclip2.png](https://files.readme.io/153226084274c9e2bf0c5cfdca65f7d36076a2020c605e21177c8c71613b69f6-360017196637.png)](https://files.readme.io/153226084274c9e2bf0c5cfdca65f7d36076a2020c605e21177c8c71613b69f6-360017196637.png)</li><li>Verify that **Activate Partner** is **On.** If this is not the case, the advertiser must complete [Advertiser GMP-DV360 integration.](#setting-up-gmp-dv360-for-advertisers)</li><li>Verify that the remaining settings, such as the lookback windows and in-app event mapping, are correct. If necessary, ask the advertiser to make changes.</li><li>Enter one or more **DBM Advertiser ID**s. The ID is available in your <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/11415707?hl=en">GMP dashboard.</Anchor></li><li>Click **Save**.</li></ol> |

## GMP-DV360 discrepancies

See possible reasons for discrepancies and how to minimize them:

| Cause | Description | AppsFlyer tip |
| --- | --- | --- |
| View-through attribution window | View-through in the GMP-DV360 attribution window is 14 days, while the AppsFlyer default window is 1 day. | To reduce the discrepancy, set the view-through window in AppsFlyer to the maximum 7-day window. |
| Incorrect mapping | Mapping between AppsFlyer and GMP-DV360 isn't correct | <ul><li>Verify the link ID</li><li>Verify that the in-app events are correctly mapped</li></ul> |

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/set-up-roi360-cost-api-to-measure-cost-data">Set up ROI360 cost API to measure cost data</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">AppsFlyer's Retargeting Attribution</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration">Custom event mapping</Anchor>

<div data-zendesk-anchors="h_01HMEH8VW3PYCZ6GC4T5BYBS3V=important 01H8E4ZJNRMXY183TQCPW15ZQB=overview 01H8DYEV7JPV80T3YAJQQHBA6C=note data-sharing-between-appsflyer-and-gmp=data-sharing-between-appsflyer-and-gmp---dv360 h_01HQ0QJJRMYP3E6B5FVA0V6861=data-sharing-between-appsflyer-and-gmp---dv360 advertiser-gmp-integration=setting-up-gmp-dv360-for-advertisers 01H8DYEV7KYNB2FJG7N1CTEE86=setting-up-gmp-dv360-for-advertisers h_01KC714WNQWGCM1C1MC8S2PZXH=note-1 h_01HPYMRJ1WVVKCHKKEA6WD0XZP=integration-tab 01H8VVCC8G0KR4AA2HD9S8QBKD=activate-partner 01H8VVCC8GSDPSNN0AJPVZPR8P=general-settings 01H8VVCC8GK8VFPBEPAMVHCAWM=install-attribution reengagement-attribution=re-engagement-attribution 01H8VVCC8HHG5290PYF0BT29QA=re-engagement-attribution h_01K4AFW71RG9YE5EJE1FQCN4SE=note-2 reengagement-window=re-engagement-window h_01HQ06JCJZD6AMFR2B6GTMSM9S=re-engagement-window h_01HNWSTJZPFQVQ5C8M0JA1J0T5=ignore-active-users-for-retargeting h_01HMXNJVHK9C3FT8E04RE0TH99=note-3 inapp-event-postbacks=in-app-event-postbacks 01H8VVCC8HHZRFQ2T1X478YZMP=in-app-event-postbacks 01H8VVCC8HDMTY1P2SG31HD61K=note-4 parameter-mapping=u-parameter-mapping h_01HBBJQZSTT1HFENXNACMHFC18=u-parameter-mapping 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab h_01HBBJQZSW45X3SM92H4FS94HM=important-1 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions h_01_dv360_cutover_discrepancy=note-5 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab 01H8VVCC8HVNNQ9PJS4ZQCVDNS=setting-up-gmp-dv360-for-agencies 01H8DYEV7MNFFY9ESFF2S3ETEB=agency-setup gmp-discrepancies=gmp-dv360-discrepancies 01H8DYEV7MTPJMY12AVHX45YFF=gmp-dv360-discrepancies h_01KYS9JJ9RSTDPHRZWW47DN438=see-also" />
