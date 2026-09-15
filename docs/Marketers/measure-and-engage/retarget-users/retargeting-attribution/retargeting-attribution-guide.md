---
title: "Retargeting attribution guide"
excerpt: "Retargeting campaigns motivate users to open and re-engage with an app, or cause users who deleted the app to reinstall it."
---
**At a glance:** Retargeting (remarketing) campaigns motivate users to open and re-engage with the app or cause users who deleted the app to reinstall it.

## Retargeting fundamentals

Retargeting attribution occurs when a user engages with a retargeting campaign by clicking on a [retargeting attribution link](/docs/retargeting-attribution-guide#retargeting-attribution-links) or [deep link](/docs/create-a-onelink-template). This results in one of the following attribution events:

* **Re-engagement:** If the app is on the device, the media source motivating the user to open the app is credited with a re-engagement.
* **Re-attribution (AKA retargeting reinstall)**: If the app is not on the user device (meaning the user uninstalled the app), then engaging with the retargeting campaign causes the user to reinstall and open the app. If this happens during a [re-attribution window:](/docs/set-up-re-attribution-window) the retargeting media source is credited with the re-attribution. Related reading: [Reinstalls.](/docs/appsflyer-attribution-model#reinstalls)

![](https://support.appsflyer.com/hc/article_attachments/33563511574673)

Before running retargeting campaigns, review the re-engagement rules and example cases in the sections that follow, then set up retargeting as described in the retargeting procedures section. For ease of understanding, you should be familiar with the AppsFlyer [attribution model](/docs/appsflyer-attribution-model) and the associated attribution windows.

> 📘 **Note**
>
> #### Tip
>
> Want to know more about retargeting? Check out this short, informative [course on the AppsFlyer Learning Portal](https://elevate.appsflyer.com/pages/142/remarketing).


### Re-engagement rules and windows

* Retargeting attribution rules determine if an event is a retargeting event and attributed to the retargeting media source.
* Similar to user acquisition attribution campaigns, SRN retargeting re-engagements are reported by API and those of non-SRNs by attribution link.
* The rules, based on the user journey, consist of :
  * [Inclusion windows](/docs/retargeting-attribution-guide#inclusion-windows), a period of time during which a re-engagement can take place.
  * [Exclusion windows](/docs/retargeting-attribution-guide#exclusion-windows), a period of time during which a re-engagement can't take place.
* If a re-engagement is attributed, in-app events for the duration of the re-engagement window are [double attributed.](/docs/resolve-retargeting-double-attribution) This means it's attributed to both the retargeting media source and to the original UA media source, if known.

The diagram that follows contains the set of re-engagement rules. Use it as a guide to determine if an interaction with a retargeting campaign will be attributed as a re-engagement.

**Re-engagement rules**

![](https://support.appsflyer.com/hc/article_attachments/33563511578513) **Reference—inclusion and exclusion windows**

The tables that follow contain reference information related to windows related to retargeting attribution.

#### Inclusion windows



| Window type | Description |
| --- | --- |
| View-through | The maximum duration from the time the user views an ad until they open an app.<br /><br />**Where configured:** Attribution link<br /><br />**Duration**:<br /><br />* Default: 1 day<br />* Range: 1-23 hours/1-7 days |
| Click lookback | The maximum duration from the time a user clicks on an ad until they open an app.<br /><br />**Where configured**: Attribution link<br /><br />**Duration** :<br /><br />* Default: 7 days<br />* Range: 1-23 hours/1-30 days<br /><br />**SRN remarks:** Check with the SRN what their specific lookback window policy is. |
| Re-engagement | Consider the following in regards to the re-engagement window:<br /><br />* The window begins when the user opens the app for the first time after engaging with the retargeting media source.<br />* In-app events are [double attributed](/docs/resolve-retargeting-double-attribution) to the retargeting and user acquisition media sources for the duration of the window<br />* Window duration is determined by the app setting or by the SRN.<br />* If the user engages with another retargeting campaign during the re-engagement window, that is not blocked by an exclusion window, the current re-engagement window ends immediately and a new re-engagement window begins.<br />* In the context of a re-attribution: The **attribution window** duration is unlimited in time (similar to installs). However, this window ends in the case of a new install, reinstall, or due to data retention limitations.<br /><br />**Where set:** Attribution link<br /><br />* Default: 30 days<br />* Range: 1-23 hour/1-90 days/lifetime<br /><br />**SRN remarks**: Configurable for SRNs<br /><br />If you change the window setting, the change impacts re-engagements going forward. It has no impact on existing re-engagements. |



#### Exclusion windows



| Window type | Description |
| --- | --- |
| Minimum time between re-engagement conversions | Don't record a re-engagement during the exclusion window.<br /><br />**Minimum time between re-engagement conversions**<br /><br />* On re-engagement, a window during which in-app events are attributed to both the retargeting (primary) and UA (non-primary) campaigns is opened.<br />* This enables the measurement of retargeting campaign performance.<br />* If another network or campaign brings a re-engagement during this window:<br />  * [Default] the existing re-engagement window is closed, another re-engagement recorded, and subsequent in-app events are attributed to the most recent re-engagement.<br />  * To prevent this,set the Minimum time between re-engagement conversions. In this case, only after the minimum elapsed time can a further re-engagement be recorded.<br />* This setting has no impact in cases where the re-engagement window is shorter than the duration of this setting. Example: If the re-engagement window is 1 day, and this setting is 4 days then this setting has no impact whatsoever.<br />* These settings do not affect the duration between install and re-engagement.<br /><br />**Where set**: App settings page<br /><br />**Duration**:<br /><br />* Default: None<br />* Range: 1-23 hours/1-30 days |
| [Minimum inactivity period](/docs/set-retargeting-inactivity-window) | Don't record a re-engagement or re-attribution during the exclusion window.<br /><br />**Where set:** Integrated partners settings page in the Integration tab.<br /><br />**Duration**:<br /><br />* Default: None<br />* 0-30 days<br /><br />**SRN remarks**: Consider that SRNs usually have their own inactivity period rules. If your setting differs from that of the SRN this can cause discrepancies. |
| [Re-attribution](/docs/set-up-re-attribution-window) | The re-attribution window impacts re-attributions but not re-engagements.<br /><br />Users reinstalling during the re-attribution window after engaging with a retargeting campaign are attributed to the retargeting media sources. Related reading: [Reinstalls](/docs/appsflyer-attribution-model#reinstalls)<br /><br />**Where set:** App settings |



#### **Example flow implementing the rules**

![](https://support.appsflyer.com/hc/article_attachments/33563511579537)

Re-engagement rules checklist for click-through and view-through attribution:



| Rule | Rule |
| --- | --- |
| A | The user engaged with a retargeting campaign, meaning the user viewed or clicked on an ad defined as a retargeting ad. |
| B | The engagement occurred **during** a click-lookback or view-through window. |
| C | The user was inactive for longer than the minimum inactivity period. |
| D | In the case of in-app events, they take place during the re-engagement window. |
| E | The period between the previous re-engagement is greater than the minimum time between re-engagements. |



### Example retargeting scenarios



| **Scenario 1: Purchases before, during, and after the re-engagement window**<br /><br />User journey:<br /><br />* Engage with an ad from network Z, install the app, and make a purchase (A).<br />* Engage with a retargeting ad from network Y, open the app, and make a purchase (B).<br />* Make a purchase (C).<br /><br />![](https://support.appsflyer.com/hc/article_attachments/33563511579537)<br /><br />P/S column: Primary or Secondary described in [double attribution of retargeting events](/docs/resolve-retargeting-double-attribution) |
| --- |
| **Scenario 2: Multiple conversions during the re-engagement attribution window**<br /><br />User journey:<br /><br />* Engage with an ad from network Z, install the app, and make a purchase (A).<br />* Engage with a retargeting ad from network Y, open the app, and make a purchase (B).<br />* Make a purchase (C).<br /><br />![](https://support.appsflyer.com/hc/article_attachments/33563474530321)<br /><br />P/S column: Primary or Secondary described in [double attribution of retargeting events](/docs/resolve-retargeting-double-attribution) |



## Retargeting operations

### Retargeting settings

The following settings are required depending on the scenario.



| Conversion type | SRN | Non-SRN |
| --- | --- | --- |
| Re-engagement | 1. In AppsFlyer, from the side menu, select **Settings** > **App settings**.<br />2. Verify that **Re-engagement attribution** is on.<br />3. Per SRN:<br />4. From the side menu, select **Collaborate** > **Active integrations**, and select the SRN.<br />5. Turn on **Re-engagement attribution**. | 1. In AppsFlyer, from the side menu, select **Settings** > **App settings**.<br />2. Verify that **Re-engagement attribution**is on.<br />3. Per non-SRN: Append the retargeting parameter to attribution links as detailed in this section |
| Re-attribution | 1. From the side menu, select **Collaborate** > **Active integrations**, and<br />2. Turn on **Reinstall attribution**. | 1. No explicit settings are required.<br />2. Append the retargeting parameter to attribution links as detailed in this section. |



#### **Non-SRN settings**

**To set up an ad network (non-SRN) retargeting partner**:

1. From the side menu, select **Collaborate** > **Active integrations**.
2. Select the ad network.
3. Turn on **Enable** **retargeting settings**. This modifies the attribution link to a retargeting URL, by appending `is_retargeting=true` to the link.

   [![](https://support.appsflyer.com/hc/article_attachments/33563511582609)](https://support.appsflyer.com/hc/article_attachments/33563511582609)
4. Select one of the following:
   * **Use a standard attribution link** for single-platform (app-specific) links.
   * **Use OneLink**.
     * Enter a **Deep link URL**, if needed (see [Deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink) guide).
5. Copy the URL generated and give it to the ad network to use with your retargeting campaign.  
   **Note**: The URL does not persist and can't be saved.

### Retargeting dashboard

The [Overview dashboard](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv) contains retargeting metrics as well as user acquisition metrics. The metrics are LTV-based and relate to users who engage with a retargeting campaign.

**To view retargeting data**:

1. From the side menu, select **Analyze** > **Overview**.
2. Click **View type**, then select **Retargeting**.  
   Retargeting data displays.  
   **Note**: You can also view retargeting data in the unified view. See [Dashboard view types](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#view-types).

### Retargeting attribution links

* Retargeting links are similar to regular user acquisition links.
* Create them for:
  * Non-SRNs that support retargeting.
  * Owned media, using the [link management](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings) page.

Retargeting attribution link parameters



| Parameter | Descriptions | Required |
| --- | --- | --- |
| `is_retargeting` | Set to: `is_retargeting=true` | Yes |
| Advertising ID | Where possible send an advertising ID like IDFA, OAID, IDFV, and so on. [Probabilistic Modeling limitations for iOS apps.](/docs/appsflyer-attribution-model#probabilistic-modeling) | No |
| Retargeting click lookback-window | * The retargeting [click lookback window](/docs/set-up-lookback-windows) works like that of user acquisition campaigns.<br />* It defines the maximum period that can elapse between a user clicking on an ad until the user is attributed.<br />* The lookback window is set using the using `&af_click_lookback` parameter.<br />* The default setting is 7 days.<br /><br />CALLSTART::Note::<br /><br />#### Example<br /><br />To set a 14-day click-through lookback window, add the following to the retargeting campaign's attribution link: `&af_click_lookback=14d`<br /><br />CALLEND:: | No |
| Retargeting view-through lookback timer | * The retargeting [view-through lookback window](/docs/set-up-lookback-windows) works like that of user acquisition campaigns.<br />* It defines the maximum period that can elapse after a user views an ad until the user is attributed.<br />* The default is 1 day.<br />* The lookback window is set using<br /><br />`af_viewthrough_lookback={time}`<br /><br />CALLSTART::Note::<br /><br />#### Example<br /><br />To set a 5-hour view-through lookback window, add the following to the retargeting campaign's attribution link: `&af_viewthrough_lookback=5h`<br /><br />CALLEND:: | No |
| Re-engagement window | * The **re-engagement window** can be set in the attribution link user interface. This sets the **af\_reengagement\_window** parameter on to the attribution link. The parameter can be added manually.<br />* The default is 30 days.<br />* The following re-engagement window values are available:<br />* Hours:1- 23 hours<br />* Days: 1-90 days<br />* Lifetime: Persists until the user either uninstall or performs another re-engagement, for example, af\_reengagement\_window=lifetime<br /><br />For example, **af\_reengagement\_window=60d** means that events reported within 60 days of the re-engagement are attributed to the retargeting media source. | No |



#### Retargeting view-through lookback period

```
https://app.appsflyer.com/id123456789?pid=remerge_int&af_dp=mydeeplink%3A%2F%2F&
clickid={clickid}&af_siteid={publisher}&idfa={device_id_raw}&sha1_idfa={device_id}
&af_sub1={creative_name}&is_retargeting=true&af_reengagement_window=60d
```

### Retargeting reports and raw data

* Retargeting reports, similar to the UA [aggregate](/docs/aggregated-and-analytics-reporting-overview) and [raw data](/docs/raw-data-reporting-overview) reports, are available using the reporting tools.
* Retargeting in-app events and sessions are [double attributed.](/docs/resolve-retargeting-double-attribution)

**Retargeting conversions report**

* The Retargeting conversions report contains raw data of re-engagements and re-attributions.
* Some fields have a different meaning in the context of retargeting to those used in user acquisition reports.

Interpretation of raw data reports in the context of retargeting



| Column | **Description** |
| --- | --- |
| Event name | * Field population depends on the report type.<br />* In-app event reports: The in-app event name.<br />* Retargeting conversion reports: re-engagement or re-attribution. **Note**! In the case of Data Locker values are as follows:<br />  * install means re-attribution<br />  * retargeting means re-engagement |
| Attributed touch type | Engagement type:<br /><br />* Click<br />* Impression |
| Attributed touch time | Retargeting engagement time |
| Install time | The first app launch after the re-engagement or re-attribution. |
| Event time | The time the event occurred |
| AppsFlyer ID | * Re-attributions: A new AppsFlyer ID<br />* Re-engagement: Remains unchanged |
| Is retargeting | TRUE for retargeting conversions and events |
| Is primary attribution | TRUE for retargeting conversions and events |
| Retargeting conversion type | * Re-engagement<br />* Re-attribution |
| Conversion type | The type of conversion:<br /><br />* Install<br />* Reinstall (1)<br />* Re-engagement<br />* Unknown (2)<br /><br />(1) If conversion\_type= reinstall and campaign\_type=retargeting is equivalent to retargeting\_conversion\_type=re-attribution<br /><br />(2) In-app events/sessions not attributed to any media source. |
| Campaign type | The source bringing the user:<br /><br />* UA<br />* Organic<br />* Retargeting<br />* Unknown |
| Attribution lookback | Retargeting click-through lookback window |
| Original URL | Contains one of the following:<br /><br />* Retargeting link<br />* Deep linking data<br />* Empty for SRNs |
| Contributor fields | Unavailable for re-engagements |



## Additional information

### App requirements

To run retargeting campaigns the app must meet the following minimum requirements.

* iOS
  * In addition to the standard AppsFlyer SDK integration, you must add additional code to the app delegate, see the [SDK Integration](/docs/basic-sdk-integration-guide#deep-linking-with-onelink) article (attribution links section).
  * For iOS 9, Universal Link App Open code must be implemented. [Universal links with iOS 9](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings).
* Android:
  * If the deep link opens an activity other than the main activity, see the [SDK Integration](/docs/basic-sdk-integration-guide#deep-linking) article (attribution links section).

### Retargeting limitations

* Starting February 17, 2021, retargeting supports Probabilistic Modeling.
* Campaign cost data for retargeting is available in Overview and Cohort dashboards and reports in the unified view.

### FAQ



| **What constitutes retargeting clicks?**<br /><br />* Retargeting clicks include retargeted users engaging with an AppsFlyer attribution link.<br />* Clicks from SRNs or from [push notifications](/docs/measuring-push-notification-re-engagement-campaigns) are not included in the count.<br />* Some clicks result in new installs which are attributed as user acquisition. This happens when non-users, or past users after the expiry of the [re-attribution window](/docs/set-up-re-attribution-window), engage with a retargeting link and install.<br />* If a retargeting click leads to an app open via Universal Links or Android App Links, but the re-engagement is not counted due to reasons such as inactivity windows, the click will not be measured. |
| --- |
| **When is the attributed touch time identical to the install time?**<br /><br />* When users of universal links, or Android app links, perform deep linking, they are directed into the app without going through AppsFlyer first.<br />* When the app launches and the SDK reports a new re-engagement, AppsFlyer reproduces the click data using the same timestamp of the launch. This makes engagement and launch time identical. |



> 📘 **Note**
>
> #### See also
>
> * [AppsFlyer attribution model](/docs/appsflyer-attribution-model)
> * [Audiences guide](/docs/audiences-guide)