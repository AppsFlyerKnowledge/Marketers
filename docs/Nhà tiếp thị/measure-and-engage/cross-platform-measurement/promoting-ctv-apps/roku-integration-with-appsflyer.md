---
title: Roku integration with AppsFlyer
metadata:
  keywords:
    - Advertisers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2021-07-19T09:00:10Z'
  edited_at: '2026-07-28T14:35:31Z'
  id: 4404257169169
  locale: en-us
  section: Promoting CTV apps
  section_id: 15328952633489
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4404257169169-Roku-integration-with-AppsFlyer
---
> **At a glance** Rokuads\_int is an SRN integration that allows advertisers to integrate their mobile or Roku CTV app with Roku Ads to receive attribution and event data for their campaigns on Roku Ads.

## About Roku Ads Attribution

Roku is a unique ad network that has ad inventory across both Connected TV (CTV) and mobile apps. The SRN integration between AppsFlyer and Roku Ads allows advertisers to measure multiple user journeys, including:

* CTV to CTV: CTV ads driving CTV app installs and events.
* Mobile to mobile: Mobile app ads driving mobile app installs and events.
* CTV to mobile and mobile to CTV: Ad impressions on one platform leading to installs and events on a different platform.

### Roku attribution flow

<Image align="center" alt="54525 inline.jpg" src="https://files.readme.io/5634ed65702e1d4c90250a7f7b4448c225d5f769936b2a120ddbac1a76752c09-39534517801617.jpg" width="895px" />

## Setting up Roku Ads integration for advertisers

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   **Note:** The toggle **must stay on (active) as long as you work with the partner**. <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">Learn more</Anchor>
5. Complete the configuration using the relevant tabs, as described below. Learn more about <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">partner integrations.</Anchor>

**Note:** There are some differences between iOS, Android, and Roku app settings.

<div id="integration-tab" />

<Accordion title="Integration tab">

#### General settings

* **Event Group ID:** Enter the Event Group ID to connect your app to AppsFlyer.
  * **Self-serve clients**: Obtain the Event Group ID from Roku Ads Manager. For more information, see <Anchor target="_blank" href="https://help.ads.roku.com/en/articles/11885912-setting-up-an-integration-with-appsflyer-a-mobile-measurement-partner-mmp">Roku ads documentation</Anchor>.
  * **Managed services clients**: Contact your Roku representative to obtain your Event Group ID.
* **Advanced Data Sharing:**  When ON, Roku will receive postbacks and event data with IP addresses for all devices, including those that have not made their Advertising ID (IDFA) available. Keeping Advanced Sharing OFF ensures this partner will only receive postbacks and event data for devices that have made the IDFA available.
* **Advanced Matching data sharing:** When on, Roku receives Advanced Matching fields, such as hashed email, hashed phone number, hashed first name, and hashed last name, if these fields are included in the event information sent to AppsFlyer. For more information, see: <Anchor target="_blank" href="/marketers/vi/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor>.
* **Limited Data Usage:** Turn ON to indicate that Roku Ads should limit its use of personal information for a given event, in specific US states. For more information, see <Anchor target="_blank" href="https://help.ads.roku.com/en/articles/8766138-limited-data-use">Roku ads documentation</Anchor>.

#### Install attribution

Set the different attribution windows to attribute new installs (first launches) of users who viewed, clicked, or engaged with your ad. **Note:** Attribution for reinstalls (any install that isn’t the initial setup on the device) isn’t supported.

* Set the **Install click-through lookback window** to either 1–23 hours or 1–14 days. **Note:** Roku Ads recommends setting this to 14 days.
* [Optional] Turn on **Install view-through attribution** and set the **Install view-through lookback window** to 1–23 hours or 1–14 days. **Note:** Roku Ads recommends 14 days.

#### Re-engagement attribution

* Set the **Re-engagement click-through lookback window** to either 1–23 hours or 1–14 days. **Note:** Roku Ads recommends 14 days.
* [Optional] Turn on **Re-engagement view-through attribution** and set the **Re-engagement view-through lookback window** to 1–23 hours or 1–14 days. **Note:** Roku Ads recommends 14 days.
* Set the **Re-engagement window** to either 1–23 hours, 1–90 days, or **Lifetime**.

[Learn more about re-engagement rules and windows](#).

#### Ignore active users for retargeting

Set a window timeframe to ignore re-engagements of users who launched your app within the timeframe. This means their activity during the window timeframe is not attributed. For more information, see <Anchor target="_blank" href="/marketers/vi/docs/set-retargeting-inactivity-window#inactivity-period">Inactivity period</Anchor>.

1. Turn on **Ignore active users for retargeting**.
2. Set the **Inactivity window**.

#### Cross-platform attribution

Cross-platform attribution is enabled by default for this integration.

* Set the **cross-platform lookback window** to 1–23 hours or 1–3 days.
* The Cross-platform equal priority window is set to 3 hours. During this period, cross-platform impressions reported by Roku are elevated to the same priority as clicks from other networks.

#### In-app events postbacks

Map AppsFlyer in-app events to Roku Ads events, sent via postbacks:

1. Turn on **In-app event postbacks**.
2. Click **Add event** to add an SDK or server-to-server event to the list. The following table describes the fields to complete:

| Parameter name | Description |
| --- | --- |
| **AppsFlyer event** | Name of the event, as received by AppsFlyer either from the SDK integrated into your app or from server-to-server events. |
| **Mapped to partner event** | Select from Roku’s pre-defined event list. See <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-event-structure#tên-sự-kiện-được-xác-định-trước">suggested mapping</Anchor> of Appsflyer events to Roku Ads events.  <br />**Note:** Roku does not support sending custom events. |
| **For users from** | <ul><li>**This partner only** (default): Send postbacks only when this event is attributed to this partner.<br />Or</li><li>**All media sources including organic:** Send postbacks for events attributed to any partner, as well as organic events.</li></ul> |
| **Including** | <ul><li>**No values & no revenue** (default): Send only the event itself without any event values.</li><li>**Values & no revenue:** Send all the parameters excluding the revenue value.</li><li>**Values & revenue:** Send all the event parameters, including the revenue value (if it exists in the event).</li></ul> |

* [Optional] Click the **Add condition** icon to set conditions for an event.
* Click **Save integration**.
* [Optional] To integrate more apps:
  1. Click the app name in the top-left corner, under the partner name, to open the list.
  2. Select another app from the list.
  3. Repeat the setup for the selected app.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution links aren't relevant for SRNs or Advanced SRNs.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab (for cost, clicks, and impressions)">

Cost integration is not available for Roku Ads at this phase.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad revenue is not available for Roku Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

In this tab, you can choose which permissions to grant Roku Ads—regardless of whether they act as an ad network, an agency, or both. Even if attribution is disabled for Roku Ads, the Permissions tab remains active, and you can still grant them access.

After enabling permissions for Roku Ads, you can add team members and assign them access based on the selected permissions. **Note:** Permissions can only be granted to Roku Ads employees who have an ad network team member account in AppsFlyer.

**To grant permissions to ad network team members, follow these steps:**

1. Click **Add team member**.
2. Enter the ad network team member's email.
3. Click **Add**.

> 🚧 **Important!**
>
> * When you give Roku Ads permissions to configure the integration and change in-app event postbacks, you allow them to potentially access all attribution events, including organic and non-organic traffic from all media sources.
> * Changes that Roku Ads makes override the current configuration, even if you (the advertiser) set them.

#### Types of permissions advertisers can grant to Roku Ads

| Permission | Capability granted |
| --- | --- |
| Configure integration | Allow the partner to set up the Integration tab, except for in-app event postbacks. |
| Configure in-app event postbacks | Allow the partner to set up in-app event postback.<br /><br />**Caution!** Combined with "Configure integration", this grants access to all attribution events, including organic and non-organic traffic from all media sources. |
| Access retention report | Allow access only to the partner's own retention data. |
| Access aggregate loyal user data | Allow the partner to access your loyal users metric. |
| Access aggregate conversion data | Allow access to metrics for installs, re-engagements, re-installs, and re-attributions. An example is <Anchor target="_blank" href="/partners/vi/docs/aggregated-campaign-performance-report-for-ad-networks">Aggregate campaign performance reports</Anchor>. |
| Access aggregate in-app events data | Grant the partner access to all in-app events data, including Protect360 data—not just the events configured in the postback mapping.  <br />This also includes access to ad monetization data, which may contain events from other media sources. |
| View validation rules | Allow the partner to view your validation rule details. |
| Access aggregate revenue data | Allow access to ad revenue data for UA optimization. |
| Use Cost Import | Allow the partner to upload cost data using Cost Import. |
| Access Protect360 dashboard & raw data | <ul><li>Raw data access is available only if your subscription includes Protect360, Validation Rules, or Raw Data.</li><li>Grants access to the Protect360 dashboard, including ProtectLITE.</li><li>**Note:** ProtectLITE includes dashboard access but does not provide raw data access.</li></ul> |

</Accordion>

## Setting up Roku Ads integration for agencies

Agencies working on behalf of advertisers can turn on the Roku Ads integration and start getting attribution for their campaigns. However, this integration has some limitations for agencies.

### Agency limitations

* An agency can access the Roku Ads integration only after the advertiser they work with has activated it on their side.
* Integration parameters showing on the agency's integration page are inherited from the advertiser's configuration in view-only mode.

**To set up Roku Ads for agencies:**

1. In AppsFlyer, from the sidebar, open <Image alt="collaborate.png" src="https://files.readme.io/70400e32ef967b981aabd47faf97880368585fdf52ad29c0d4c2d4c31751e6a3-37844129188753.png" width="2%" /> **Collaborate** > **Partner Integrations**.
2. Find **Roku Ads (rokuads\_int)** and select it.
3. Enter your agency **Roku Ads Account ID**. This identifies agency traffic and distinguishes it from the advertiser's.
4. Click **Save Integration**.

> ❗️ **Warning**
>
> Roku Ads account IDs MUST NOT be shared between the advertiser and the agency. If shared, ALL the advertiser's installs are automatically attributed to the agency's dashboard.

<div data-zendesk-anchors="overview=about-roku-ads-attribution 01H7Z13QPBTKZ9BVCMGASYEM0R=roku-attribution-flow setting-up-roku-ads=setting-up-roku-ads-integration-for-advertisers h_01K0P7PHA89T432XNW0C4BZ4VH=general-settings h_01K0P7PHA8X7E7MC7JNVG86JAV=install-attribution reengagement-attribution=re-engagement-attribution h_01K0P7PHA8GR0SYPNKSP4D90AF=re-engagement-attribution h_01K0P7PHA85619R1SM4SR49TQ3=ignore-active-users-for-retargeting crossplatform-attribution=cross-platform-attribution h_01K0P7PHA80KKG06719ZWE8JB0=cross-platform-attribution inapp-events-postbacks=in-app-events-postbacks h_01K0P7PHA89Y8W70NTF40S6PC4=in-app-events-postbacks cost-tab-for-cost-clicks-and-impressions=cost-tab h_01K0P7PHA840N225ABCSGTTCAN=important h_01K0P7PHA8D7WQR02129YADZZP=types-of-permissions-advertisers-can-grant-to-roku-ads setting-up-agencies=setting-up-roku-ads-integration-for-agencies h_01K0P7PHA8MSV6Q13P9ATAX8SJ=agency-limitations h_01K0P7PHA8KXP5H9WXJ1J2VFR2=warning" />
