---
title: Retargeting attribution guide
metadata:
  keywords:
    - Attribution
    - Re-targeting
    - retargeting
    - Advertisers
    - reatribution
    - re-atribution
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-30T13:18:26Z'
  edited_at: '2026-03-28T16:48:19Z'
  id: 207033786
  locale: en-us
  section: Retargeting attribution
  section_id: 6551326229265
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207033786-Retargeting-attribution-guide
---
> **At a glance:** Retargeting (remarketing) campaigns motivate users to open and re-engage with the app or cause users who deleted the app to reinstall it.

<div id="retargeting-fundamentals" />

## Retargeting fundamentals

Retargeting attribution occurs when a user engages with a retargeting campaign by clicking on a [retargeting attribution link](/docs/retargeting-attribution-guide#retargeting-attribution-links) or <Anchor target="_blank" href="/marketers/docs/create-a-onelink-template">deep link</Anchor>. This results in one of the following attribution events:

* **Re-engagement:** If the app is on the device, the media source motivating the user to open the app is credited with a re-engagement.
* **Re-attribution (AKA retargeting reinstall)**: If the app is not on the user device (meaning the user uninstalled the app), then engaging with the retargeting campaign causes the user to reinstall and open the app. If this happens during a <Anchor target="_blank" href="/marketers/docs/set-up-re-attribution-window">re-attribution window:</Anchor> the retargeting media source is credited with the re-attribution. Related reading: <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#reinstalls">Reinstalls.</Anchor>

<Image align="center" alt="" src="https://files.readme.io/6558ed1ef0596e0cf99deb3c3c5b77eee8506b257ec65d3ad9cc653bc82aa7d9-33563511574673.png" />

Before running retargeting campaigns, review the re-engagement rules and example cases in the sections that follow, then set up retargeting as described in the retargeting procedures section. For ease of understanding, you should be familiar with the AppsFlyer <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model">attribution model</Anchor> and the associated attribution windows.

<div id="tip" />

> 👍 **Tip**
>
> Want to know more about retargeting? Check out this short, informative <Anchor target="_blank" href="https://elevate.appsflyer.com/pages/142/remarketing">course on the AppsFlyer Learning Portal</Anchor>.

<div id="reengagement-rules-and-windows" />

<Accordion title="Re-engagement rules and windows">

* Retargeting attribution rules determine if an event is a retargeting event and attributed to the retargeting media source.
* Similar to user acquisition attribution campaigns, SRN retargeting re-engagements are reported by API and those of non-SRNs by attribution link.
* The rules, based on the user journey, consist of :
  * [Inclusion windows](/docs/retargeting-attribution-guide#inclusion-windows), a period of time during which a re-engagement can take place.
  * [Exclusion windows](/docs/retargeting-attribution-guide#exclusion-windows), a period of time during which a re-engagement can't take place.
* If a re-engagement is attributed, in-app events for the duration of the re-engagement window are <Anchor target="_blank" href="/marketers/docs/resolve-retargeting-double-attribution">double attributed.</Anchor> This means it's attributed to both the retargeting media source and to the original UA media source, if known.

The diagram that follows contains the set of re-engagement rules. Use it as a guide to determine if an interaction with a retargeting campaign will be attributed as a re-engagement.

**Re-engagement rules**

![](https://files.readme.io/e6643112f3e9969242c0dd394f6401406fbc837a9494cc4bb3825cff6365f36d-33563511578513.png) **Reference—inclusion and exclusion windows**

The tables that follow contain reference information related to windows related to retargeting attribution.

<div id="inclusion-windows" />

#### Inclusion windows

| Window type | Description |
| --- | --- |
| View-through | The maximum duration from the time the user views an ad until they open an app.<br /><br />**Where configured:** Attribution link<br /><br />**Duration**:<ul><li>Default: 1 day</li><li>Range: 1-23 hours/1-7 days</li></ul> |
| Click lookback | The maximum duration from the time a user clicks on an ad until they open an app.<br /><br />**Where configured**: Attribution link<br /><br />**Duration** :<ul><li>Default: 7 days</li><li>Range: 1-23 hours/1-30 days</li></ul>**SRN remarks:** Check with the SRN what their specific lookback window policy is. |
| Re-engagement | Consider the following in regards to the re-engagement window:<ul><li>The window begins when the user opens the app for the first time after engaging with the retargeting media source.</li><li>In-app events are <Anchor target="_blank" href="/marketers/docs/resolve-retargeting-double-attribution">double attributed</Anchor> to the retargeting and user acquisition media sources for the duration of the window</li><li>Window duration is determined by the app setting or by the SRN.</li><li>If the user engages with another retargeting campaign during the re-engagement window, that is not blocked by an exclusion window, the current re-engagement window ends immediately and a new re-engagement window begins.</li><li>In the context of a re-attribution: The **attribution window** duration is unlimited in time (similar to installs). However, this window ends in the case of a new install, reinstall, or due to data retention limitations.</li></ul>**Where set:** Attribution link<ul><li>Default: 30 days</li><li>Range: 1-23 hour/1-90 days/lifetime</li></ul>**SRN remarks**: Configurable for SRNs<br /><br />If you change the window setting, the change impacts re-engagements going forward. It has no impact on existing re-engagements. |

<div id="exclusion-windows" />

#### Exclusion windows

| Window type | Description |
| --- | --- |
| Minimum time between re-engagement conversions | Don't record a re-engagement during the exclusion window.<br /><br />**Minimum time between re-engagement conversions**<ul><li>On re-engagement, a window during which in-app events are attributed to both the retargeting (primary) and UA (non-primary) campaigns is opened.</li><li>This enables the measurement of retargeting campaign performance.</li><li>If another network or campaign brings a re-engagement during this window:<ul><li>[Default] the existing re-engagement window is closed, another re-engagement recorded, and subsequent in-app events are attributed to the most recent re-engagement.</li><li>To prevent this, set the Minimum time between re-engagement conversions. In this case, only after the minimum elapsed time can a further re-engagement be recorded.</li></ul></li><li>This setting has no impact in cases where the re-engagement window is shorter than the duration of this setting. Example: If the re-engagement window is 1 day, and this setting is 4 days then this setting has no impact whatsoever.</li><li>These settings do not affect the duration between install and re-engagement.</li></ul>**Where set**: App settings page<br /><br />**Duration**:<ul><li>Default: None</li><li>Range: 1-23 hours/1-30 days</li></ul> |
| <Anchor target="_blank" href="/marketers/docs/set-retargeting-inactivity-window">Minimum inactivity period</Anchor> | Don't record a re-engagement or re-attribution during the exclusion window.<br /><br />**Where set:** Integrated partners settings page in the Integration tab.<br /><br />**Duration**:<ul><li>Default: None</li><li>0-30 days</li></ul>**SRN remarks**: Consider that SRNs usually have their own inactivity period rules. If your setting differs from that of the SRN this can cause discrepancies. |
| <Anchor target="_blank" href="/marketers/docs/set-up-re-attribution-window">Re-attribution</Anchor> | The re-attribution window impacts re-attributions but not re-engagements.<br /><br />Users reinstalling during the re-attribution window after engaging with a retargeting campaign are attributed to the retargeting media sources. Related reading: <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#reinstalls">Reinstalls</Anchor><br /><br />**Where set:** App settings |

<div id="example-flow-implementing-the-rules" />

#### **Example flow implementing the rules**

<Image align="center" alt="" src="https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png" />

Re-engagement rules checklist for click-through and view-through attribution:

| Rule | Rule |
| --- | --- |
| A | The user engaged with a retargeting campaign, meaning the user viewed or clicked on an ad defined as a retargeting ad. |
| B | The engagement occurred **during** a click-lookback or view-through window. |
| C | The user was inactive for longer than the minimum inactivity period. |
| D | In the case of in-app events, they take place during the re-engagement window. |
| E | The period between the previous re-engagement is greater than the minimum time between re-engagements. |

</Accordion>

<div id="example-retargeting-scenarios" />

<Accordion title="Example retargeting scenarios">

| **Scenario 1: Purchases before, during, and after the re-engagement window**<br /><br />User journey:<ul><li>Engage with an ad from network Z, install the app, and make a purchase (A).</li><li>Engage with a retargeting ad from network Y, open the app, and make a purchase (B).</li><li>Make a purchase (C).</li></ul>![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)<br /><br />P/S column: Primary or Secondary described in <Anchor target="_blank" href="/marketers/docs/resolve-retargeting-double-attribution">double attribution of retargeting events</Anchor> |
| --- |
| **Scenario 2: Multiple conversions during the re-engagement attribution window**<br /><br />User journey:<ul><li>Engage with an ad from network Z, install the app, and make a purchase (A).</li><li>Engage with a retargeting ad from network Y, open the app, and make a purchase (B).</li><li>Make a purchase (C).</li></ul>![](https://files.readme.io/bf57f8a9597bd56a89bb3f1be3700195e1b153b548cb11ee3d37c65d5382e711-33563474530321.png)<br /><br />P/S column: Primary or Secondary described in <Anchor target="_blank" href="/marketers/docs/resolve-retargeting-double-attribution">double attribution of retargeting events</Anchor> |

</Accordion>

<div id="retargeting-operations" />

## Retargeting operations

<div id="retargeting-settings" />

<Accordion title="Retargeting settings">

The following settings are required depending on the scenario.

| Conversion type | SRN | Non-SRN |
| --- | --- | --- |
| Re-engagement | <ol><li>In AppsFlyer, from the side menu, select **Settings** > **App settings**.</li><li>Verify that **Re-engagement attribution** is on.</li><li>Per SRN:</li><li>From the side menu, select **Collaborate** > **Active integrations**, and select the SRN.</li><li>Turn on **Re-engagement attribution**.</li></ol> | <ol><li>In AppsFlyer, from the side menu, select **Settings** > **App settings**.</li><li>Verify that **Re-engagement attribution** is on.</li><li>Per non-SRN: Append the retargeting parameter to attribution links as detailed in this section</li></ol> |
| Re-attribution | <ol><li>From the side menu, select **Collaborate** > **Active integrations**, and</li><li>Turn on **Reinstall attribution**.</li></ol> | <ol><li>No explicit settings are required.</li><li>Append the retargeting parameter to attribution links as detailed in this section.</li></ol> |

<div id="non-srn-settings" />

#### **Non-SRN settings**

**To set up an ad network (non-SRN) retargeting partner**:

1. From the side menu, select **Collaborate** > **Active integrations**.
2. Select the ad network.
3. Turn on **Enable** **retargeting settings**. This modifies the attribution link to a retargeting URL, by appending `is_retargeting=true` to the link.

   <Image align="center" alt="" src="https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png" />
4. Select one of the following:
   * **Use a standard attribution link** for single-platform (app-specific) links.
   * **Use OneLink**.
     * Enter a **Deep link URL**, if needed (see <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Deep linking</Anchor> guide).
5. Copy the URL generated and give it to the ad network to use with your retargeting campaign.  
   **Note**: The URL does not persist and can't be saved.

</Accordion>

<div id="retargeting-dashboard" />

<Accordion title="Retargeting dashboard">

The Overview dashboard contains retargeting metrics as well as user acquisition metrics. The metrics are LTV-based and relate to users who engage with a retargeting campaign.

**To view retargeting data**:

1. From the side menu, select **Analyze** > **Overview**.
2. Click **View type**, then select **Retargeting**.  
   Retargeting data displays.  
   **Note**: You can also view retargeting data in the unified view. See Dashboard view types.

</Accordion>

<div id="retargeting-attribution-links" />

<Accordion title="Retargeting attribution links">

* Retargeting links are similar to regular user acquisition links.
* Create them for:
  * Non-SRNs that support retargeting.
  * Owned media, using the <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">link management</Anchor> page.

Retargeting attribution link parameters

| Parameter | Descriptions | Required |
| --- | --- | --- |
| `is_retargeting` | Set to: `is_retargeting=true` | Yes |
| Advertising ID | Where possible send an advertising ID like IDFA, OAID, IDFV, and so on. <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#probabilistic-modeling">Probabilistic Modeling limitations for iOS apps.</Anchor> | No |
| Retargeting click lookback-window | <ul><li>The retargeting <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">click lookback window</Anchor> works like that of user acquisition campaigns.</li><li>It defines the maximum period that can elapse between a user clicking on an ad until the user is attributed.</li><li>The lookback window is set using the using `&af_click_lookback` parameter.</li><li>The default setting is 7 days.</li></ul>**<span id="01ECF12NKTFH6Q2NH4B1WKSYF9"></span>Example**<br />To set a 14-day click-through lookback window, add the following to the retargeting campaign's attribution link: `&af_click_lookback=14d` | No |
| Retargeting view-through lookback timer | <ul><li>The retargeting <Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">view-through lookback window</Anchor> works like that of user acquisition campaigns.</li><li>It defines the maximum period that can elapse after a user views an ad until the user is attributed.</li><li>The default is 1 day.</li><li>The lookback window is set using</li></ul>`af_viewthrough_lookback={time}`<br /><br /><br /><br />**<span id="01ECF12NKTE8W4K72VATN9RM2X"></span>Example**<br />To set a 5-hour view-through lookback window, add the following to the retargeting campaign's attribution link: `&af_viewthrough_lookback=5h` | No |
| Re-engagement window | <ul><li>The **re-engagement window** can be set in the attribution link user interface. This sets the **af\_reengagement\_window** parameter on to the attribution link. The parameter can be added manually.</li><li>The default is 30 days.</li><li>The following re-engagement window values are available:</li><li>Hours:1- 23 hours</li><li>Days: 1-90 days</li><li>Lifetime: Persists until the user either uninstall or performs another re-engagement, for example, af\_reengagement\_window=lifetime</li></ul>For example, **af\_reengagement\_window=60d** means that events reported within 60 days of the re-engagement are attributed to the retargeting media source. | No |

<div id="retargeting-view-through-lookback-period" />

#### Retargeting view-through lookback period

```http
https://app.appsflyer.com/id123456789?pid=remerge_int&af_dp=mydeeplink%3A%2F%2F&
clickid={clickid}&af_siteid={publisher}&idfa={device_id_raw}&sha1_idfa={device_id}
&af_sub1={creative_name}&is_retargeting=true&af_reengagement_window=60d
```

</Accordion>

<div id="retargeting-reports-and-raw-data" />

<Accordion title="Retargeting reports and raw data">

* Retargeting reports, similar to the UA <Anchor target="_blank" href="/marketers/docs/aggregated-and-analytics-reporting-overview">aggregate</Anchor> and <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview">raw data</Anchor> reports, are available using the reporting tools.
* Retargeting in-app events and sessions are <Anchor target="_blank" href="/marketers/docs/resolve-retargeting-double-attribution">double attributed.</Anchor>

**Retargeting conversions report**

* The Retargeting conversions report contains raw data of re-engagements and re-attributions.
* Some fields have a different meaning in the context of retargeting to those used in user acquisition reports.

Interpretation of raw data reports in the context of retargeting

| Column | **Description** |
| --- | --- |
| Event name | <ul><li>Field population depends on the report type.</li><li>In-app event reports: The in-app event name.</li><li>Retargeting conversion reports: re-engagement or re-attribution. **Note**! In the case of Data Locker values are as follows:<ul><li>install means re-attribution</li><li>retargeting means re-engagement</li></ul></li></ul> |
| Attributed touch type | Engagement type:<ul><li>Click</li><li>Impression</li></ul> |
| Attributed touch time | Retargeting engagement time |
| Install time | The first app launch after the re-engagement or re-attribution. |
| Event time | The time the event occurred |
| AppsFlyer ID | <ul><li>Re-attributions: A new AppsFlyer ID</li><li>Re-engagement: Remains unchanged</li></ul> |
| Is retargeting | TRUE for retargeting conversions and events |
| Is primary attribution | TRUE for retargeting conversions and events |
| Retargeting conversion type | <ul><li>Re-engagement</li><li>Re-attribution</li></ul> |
| Conversion type | The type of conversion:<ul><li>Install</li><li>Reinstall (1)</li><li>Re-engagement</li><li>Unknown (2)</li></ul>(1) If conversion\_type= reinstall and campaign\_type=retargeting is equivalent to retargeting\_conversion\_type=re-attribution<br /><br />(2) In-app events/sessions not attributed to any media source. |
| Campaign type | The source bringing the user:<ul><li>UA</li><li>Organic</li><li>Retargeting</li><li>Unknown</li></ul> |
| Attribution lookback | Retargeting click-through lookback window |
| Original URL | Contains one of the following:<ul><li>Retargeting link</li><li>Deep linking data</li><li>Empty for SRNs</li></ul> |
| Contributor fields | Unavailable for re-engagements |

</Accordion>

<div id="additional-information" />

## Additional information

<div id="app-requirements" />

<Accordion title="App requirements">

To run retargeting campaigns the app must meet the following minimum requirements.

* iOS
  * In addition to the standard AppsFlyer SDK integration, you must add additional code to the app delegate, see the <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#deep-linking-with-onelink">SDK Integration</Anchor> article (attribution links section).
  * For iOS 9, Universal Link App Open code must be implemented. <Anchor target="_blank" href="/marketers/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">Universal links with iOS 9</Anchor>.
* Android:
  * If the deep link opens an activity other than the main activity, see the <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#deep-linking">SDK Integration</Anchor> article (attribution links section).

</Accordion>

<div id="retargeting-limitations" />

<Accordion title="Retargeting limitations">

* Starting February 17, 2021, retargeting supports Probabilistic Modeling.
* Campaign cost data for retargeting is available in Overview and Cohort dashboards and reports in the unified view.

</Accordion>

<div id="faq" />

<Accordion title="FAQ">

| **What constitutes retargeting clicks?**<ul><li>Retargeting clicks include retargeted users engaging with an AppsFlyer attribution link.</li><li>Clicks from SRNs or from <Anchor target="_blank" href="/marketers/docs/measuring-push-notification-re-engagement-campaigns">push notifications</Anchor> are not included in the count.</li><li>Some clicks result in new installs which are attributed as user acquisition. This happens when non-users, or past users after the expiry of the <Anchor target="_blank" href="/marketers/docs/set-up-re-attribution-window">re-attribution window</Anchor>, engage with a retargeting link and install.</li><li>If a retargeting click leads to an app open via Universal Links or Android App Links, but the re-engagement is not counted due to reasons such as inactivity windows, the click will not be measured.</li></ul> |
| --- |
| **When is the attributed touch time identical to the install time?**<ul><li>When users of universal links, or Android app links, perform deep linking, they are directed into the app without going through AppsFlyer first.</li><li>When the app launches and the SDK reports a new re-engagement, AppsFlyer reproduces the click data using the same timestamp of the launch. This makes engagement and launch time identical.</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model">AppsFlyer attribution model</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/audiences-guide">Audiences guide</Anchor>

<div data-zendesk-anchors="h_01HCFJHC85VK0A05X5F69E2WKT=retargeting-fundamentals h_01HCFJHC851PV0VR42H07VQAXF=tip h_01HCFJHC85EW8MBQ8MBXBVPF03=reengagement-rules-and-windows h_01HCFJHC85FRFJ531Y08DW03Y2=inclusion-windows h_01HCFJHC85ECS3PJV80D943TVY=exclusion-windows h_01HCFJHC8529NW0ABMQ0RB3E8R=example-flow-implementing-the-rules h_01HCFJHC85E1SWGYN0BH603BV9=example-retargeting-scenarios h_01HCFJHC863XPHNWRHJ60JPSRF=retargeting-operations h_01HCFJHC86XNCT5AQP48R9ZDC4=retargeting-settings nonsrn-settings=non-srn-settings h_01HCFJHC865V36R3H58D5PWXYY=non-srn-settings h_01HCFJHC860BS9YJM99G437G24=retargeting-dashboard h_01HCFJHC860Y5HZN66DRNN2Q89=retargeting-attribution-links retargeting-viewthrough-lookback-period=retargeting-view-through-lookback-period h_01HCFJHC863CSP03AYBXFSNC37=retargeting-view-through-lookback-period h_01HCFJHC86MNFRGYMN776FYHJV=retargeting-reports-and-raw-data h_01HCFJHC86RKKPPMBYEZV4Q3X9=additional-information h_01HCFJHC862E6C46Q7645VJ6CZ=app-requirements h_01HCFJHC86SMKZ1HT5KHQNQS1N=retargeting-limitations h_01HCFJHC86BVSVRNAGJEKZFCJP=faq h_01HE7TPR7928SF2W8ZJS55Y5BG=see-also" />
