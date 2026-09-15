---
title: "SKAN Conversion Studio"
excerpt: "Configure and optimize your SKAdNetwork conversion values to measure post-install user revenue, engagement, and retention."
---
**At a glance**: Use SKAN Conversion Studio to set which user engagements in the app to measure, and for how long. Measure revenue, conversion, engagement, and retention during a limited post-install period. By adding the Single Source of Truth measurement we can let you know if the user was attributed by both AppsFlyer and SKAN.

<Embed title="SKAN 4 Conversion Studio (including lock window)" typeOfEmbed="vimeo" url="https://player.vimeo.com/video/810457121?h=a3acc3ee41&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" providerUrl="https://player.vimeo.com" />

## SKAN Conversion Studio basics

Within the SKAdNetwork (SKAN) attribution flow, an iOS device sends SKAN postbacks containing the most recent conversion values (CV) after each measurement window.

For SKAN 3 and below, there is 1 postback that arrives after the initial Activity Window ends. The Activity Window can be 12 hours-63 days. The CV is limited to 6 bits, resulting in 64 possible values (0-63).

For SKAN 4, there are 3 postbacks that arrive after each of the 3 windows ends, after days 2, 7, and 35, respectively. For:

* Window 1, the fine CV is limited to 6 bits, resulting in 64 possible values (0-63).
* Windows 1-3, the coarse CV is limited to a CV of low, medium, or high. (Windows 2 and 3 don't have fine CVs).

These CV limitations mean you may need to make some hard choices about how to use those 64 possible values for fine CVs and 3 possible values for coarse CVs.

Conversion Studio provides you with maximum flexibility to make every possible value and bit count. You determine precisely what measurement data should be encoded within the CV—including what activity and for how long to measure during the post-install period. There are several measurement modes you can use to configure your CV settings.



| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | * Window 1: 1-2 days<br />* Window 2: 3-7 days<br />* Window 3: 8-35 days |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<br /><br />* $1-$630 in steps of $10<br />* $1-$63 in steps of $1<br />* $0.01-$0.63 in steps of $0.01 | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | * Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**. | 12-1512h (63 days) |



*Fixed modes are unavailable for new apps starting from 23/06/2024.  All functionalities are supported in the Custom and SKAN4 modes.

**Tip!** Experiment with Conversion Studio. In AppsFlyer go to > **Settings** > **SKAN Conversion Studio**.

### Measurement principles and definitions

**Definitions**

* **SKAN measurement window**: Relevant for SKAN 4+. There are 3 time periods (windows) during which user post-install activity is measured:
  * Window 1: 1-2 days
  * Window 2: 3-7 days
  * Window 3: 8-35 days
  * The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7.
* **Activity Window:** Relevant for SKAN 3 and below. Has a set duration, default of 24 hours, starting with the first app open. If you're using SKAN 4+, but user devices or ad networks don't support SKAN 4 yet, the Activity Window is 48 hours.
* **Conversion Value (CV)**: The measure of user quality reported in the postbacks sent by iOS at the end of the SKAN 4 windows or, for SKAN 3 and below, at the end of the Activity Window. The AppsFlyer SDK sets the CVs for you. However, if you want to set the CV use [Decode](/docs/skan-cv-decode-map-your-cv-to-events) to upload your CV mapping file.
  * For SKAN 4+, there are both fine and coarse conversion values.
* **Conversion-value capacity:** The number of CVs required to map your setting. The more components and measurement elements you select, the more conversion-value capacity is required. Each range or setting element selected consumes conversion-value capacity. (And each additional setting unit included in a single component consumes it exponentially!) [Examples of maximized CV usage.](/docs/skan-conversion-studio#maximized-custom-cv-examples)
* **Single Source of Truth (SSOT):** [Mechanism to flag](/docs/single-source-of-truth-ssot-guide-for-ios-attribution) if the user was attributed by SKAN and another attribution matching method. The flag is used to eliminate duplicate install data in SKAN raw data and to calculate true performance metrics.
* **Measurement components**:  
  * **Revenue:** Measures revenue generated
  * **In-app event**: Measure conversion (number of unique users performing an event),  
    engagement (number of times an event was performed), or both.
  * **Funnel**: Measures the occurrence of in-app events based on a list of sequential events in a funnel. A user performing any event in the funnel is regarded as having performed all the events preceding that event.
  * **Priority**: A component that contains revenue, in-app event, or both.

**Principles**

* **![Admin.png](https://support.appsflyer.com/hc/article_attachments/4405725144977) Admin only:** Only an admin can save Conversion Studio settings. Account users can view the settings.
* At any given time, only one mode is active.
* For a given mode, AppsFlyer maps the combinations defined by your settings to CVs. You can [view and download the mapping table](/docs/skan-conversion-studio#view-cv-mapping).
* In the app, AppsFlyer sets the CV after each measurable user action using the measurement mode active when a user launches the app for the first time.
* iOS considers [Apple crowd anonymity](https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows) before populating the CV in the postback.
* User actions occurring after the end of a window are disregarded.
* SKAN dashboard and reports:
  * The SKAN dashboard layout and metrics depend on the mode and configuration.
  * The layout updates daily based on the mode active at midnight UTC. Expect the updated layout to be available by 05:00 UTC.
  * In SKAN 4, Custom and Decode, organic data for in-app events and overall revenue aren't available.

#### **S2S principles**

Measurable actions can be reported by [server-to-server (S2S)](/docs/skan-conversion-studio#report-events-by-servertoserver-api) API. Consider the following per mode:

* SKAN 4 and Custom: S2S is always on.
* Decode: S2S isn't suited to decode mode and isn't available. AppsFlyer doesn't set the CV in this mode.
* [Legacy] Revenue, conversion, and engagement modes: You must turn on [S2S event recording](/docs/skan-conversion-studio#report-events-by-servertoserver-api) before sending events.

## Setting up conversion values in SKAN Conversion Studio

There are several modes available in SKAN Conversion Studio to set conversion values:

* SKAN 4: Use different measurement components like revenue, in-app events, priority, and Single Source of Truth, to determine what is measured during each of the three measurement windows.
* Custom: Use different measurement components like revenue, in-app events, priority, and Single Source of Truth, to determine what is measured during the Activity Window.
* [Legacy] Fixed modes: Measure user value using one of the following measurements:
  * Revenue
  * Conversion
  * Engagement

Learn more about the different measurement modes in the sections that follow.

> 📘 **Important!**
>
> Setting conversion values in SKAN Conversion Studio must be performed by an admin or an account user with the **Manage*** permissions in **SKAN Conversion Studio**.
>
> **To view or change user permissions:**
>
> 1. In AppsFlyer, in the upper-right click on your email address.
> 2. Select **User Management** > Select the user.
> 3. If required, grant the user with the **Manage** permissions in **SKAN Conversion Studio**. For more about permissions, see [User Management](/docs/user-management).
>
> *Note: Users whose access is limited to specific media sources and geos may not be able to see or access the SKAN Conversion Studio.


### SKAN 4

In SKAN 4, you use different measurement components like revenue, in-app events, priority, and Single Source of Truth, to determine what is measured during each of the three measurement windows. Together the components create your SKAN 4 measurement mode.

If you’re upgrading to SKAN 4 from a previous SKAN mode, your current schema mapping is carried over for the window 1 fine configuration. AppsFlyer automatically maps the coarse values for you for windows 1-3.

To manually set SKAN 4, experiment with different options. As you make changes, the **Conversion-value capacity** summary updates. Optimize your settings to capture the data most valuable to you without exceeding the capacity. See [Conversion value capacity calculation.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**Note: If you’re upgrading to SKAN 4 from a previous SKAN mode, your current schema mapping is carried over for fine measurements and AppsFlyer automatically maps the coarse values for you. And if you’re new to SKAN, AppsFlyer provides an initial default mapping.**

**![AppsFlyerAdmin_us-en.png](https://support.appsflyer.com/hc/article_attachments/16281491712785) To manually set conversion values in Conversion Studio using SKAN 4 mode:**

1. In the AppsFlyer dashboard, go to **Settings** > **SKAN Conversion Studio.**
2. Click options **(⋮)** to display the options menu and make sure **SKAN measurement** is turned on. **Note**! If off, the SDK does not call iOS SKAN functions like *registerAppForAdNetworkAttribution*, *updateConversionValue.*
3. Select the **SKAN 4.0** measurement mode.
4. Click **Continue**.  
   The settings for **Window 1 (1-2 days) fine** CV opens.
5. [Optional] Turn on **Single Source of Truth (SSOT)**.  
   The SSOT mechanism flags (and deduplicates) installs reported by more than one attribution matching method. [Learn more](/docs/single-source-of-truth-ssot-guide-for-ios-attribution)
6. Click **+ Add measurement** to add different [measurement components](/docs/skan-conversion-studio#measurement-components).  
   The following sections detail the setting options and components. Use them as guides as you experiment with the different SKAN measurement settings:
   * Revenue
   * In-app event
   * Funnel
   * Priority
7. Click **Coarse** and repeat Steps 6-7 to set the **Window 1 (1-2 days) coarse** CV.   
   **Note**:
   * Only Revenue and In-app event measurement components are available.
   * Low CV must be a user session to ensure the postback is sent.
8. [Optional] Turn on **Lock window**and set the condition (either time or coarse conversion value) for locking the SKAN window earlier than the default. [Learn more](/docs/skan-conversion-studio#lock-window)
9. Click **Window 2 (3-7 days)** and repeat Steps 6-8 to set the window 2 CV.   
   **Note**:
   * Only Revenue and In-app event measurement components are available.
   * [Recommended] Low CV should be a user session.
10. Click **Window 3 (8-35 days)** and repeat Steps 6-8 to set the window 3 CV.   
    **Note**:
    * Only Revenue and In-app event measurement components are available.
    * [Recommended] Low CV should be a user session.
11. Click **Save**.
12. Verify that your partner in-app event postback mappings map the events you have configured.

### Custom

In Custom, you use different measurement components like revenue, in-app events, priority, and Single Source of Truth, to determine what is measured and set an activity window to determine for how long and at what intervals measurement occurs. Together, the components create your Custom measurement mode.

To set Custom, experiment with different options. As you make changes, the **Conversion-value capacity** summary updates. Optimize your settings to capture the data most valuable to you without exceeding the capacity. See [Conversion value capacity calculation.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

Note: By default, AppsFlyer displays SKAN 4 on the Conversion Studio. To revert to a previous mode, click options **(⋮)** to display the options menu and select Revert to the previous SKAN version.

**![AppsFlyerAdmin_us-en.png](https://support.appsflyer.com/hc/article_attachments/16281491712785) To manually set conversion values in Conversion Studio using Custom mode:**

1. In the AppsFlyer dashboard, go to **Settings** > **SKAN Conversion Studio.**
2. Click options **(⋮)** to display the options menu and make sure **SKAN measurement** is turned on. **Note**! If off, the SDK does not call iOS SKAN functions like *registerAppForAdNetworkAttribution*, *updateConversionValue.*
3. Select the **Custom** measurement mode.
4. Click **Continue**.
5. [Optional] Turn on **Single Source of Truth (SSOT)**.  
   The SSOT mechanism flags (and deduplicates) installs reported by more than one attribution matching method. [Learn more](/docs/single-source-of-truth-ssot-guide-for-ios-attribution)
6. Click **+ Add measurement** to add different measurement components.  
   The following sections detail the setting options and components. Use them as guides as you experiment with the different SKAN measurement settings:
   * Revenue
   * In-app event
   * Funnel
   * Priority
7. Set the Activity window duration (12 hours-63 days) during which you want to measure user activity.  
   The default **Activity timer** allows you to set the window to 24-72 hours. And the default **Interval** setting lets you set 12 or 24 hours. Use **Custom window** to extend the activity window to up to 63 days and set longer intervals.
8. Click **Save**.
9. Verify that your partner in-app event postback mappings map the events you have configured.

### [Legacy] Fixed modes

> 📘 **Note**
>
> Fixed modes are unavailable for new apps starting from 23/06/2024.  All functionalities are supported in the Custom and SKAN4.


Using fixed modes, you can measure user value using one of the following measurements:

* * Revenue
  * Conversion
  * Engagement

As you make changes to the mode settings, the **Conversion-value capacity** summary updates. Optimize your settings to capture the data most valuable to you without exceeding the capacity. See [Conversion value capacity calculation.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**Note!**

* Fixed mode measurement is for a 24-hour activity window starting with the first app open.
* If you want to send events using S2S, you must explicitly enable [SKAN S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api)

**![AppsFlyerAdmin_us-en.png](https://support.appsflyer.com/hc/article_attachments/16281491712785) To manually set conversion values in Conversion Studio using a fixed mode:**

1. In the AppsFlyer dashboard, go to **Settings** > **SKAN Conversion Studio.**
2. Click options **(⋮)** to display the options menu and:
   * Make sure **SKAN measurement** is turned on. **Note**! If off, the SDK does not call iOS SKAN functions like *registerAppForAdNetworkAttribution*, *updateConversionValue.*
   * [Optional] [Enable sending events by S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api). Available if the selected mode is revenue, conversion, or engagement.
3. Select a fixed measurement mode.
4. Follow the information and instructions in the table that follows for your selected fixed measurement mode.
5. Click **Save**.
6. Verify that your partner in-app event postback mappings map the events you have configured.

#### Fixed mode measurement



| Measurement mode | Description |
| --- | --- |
| Revenue | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Revenue generated during the 24-hour activity window.**<br /><br />Select a unit-to-USD rate from one of the following:<br /><br />* $0.01 to measure up to $0.63<br />* $1 to measure up to $63<br />* $10 to measure up to $630<br /><br />AppsFlyer automatically populates 63 revenue measurement ranges. Ensure that the event name `af_skad_revenue` is correctly mapped for partners. In the dashboard, revenue is recorded as the maximum of the range. For example, if the range is $60-$61, the revenue recorded is $61. Note! Custom revenue uses a different method to calculate revenue.<br /><br />**Metrics available:**<br /><br />* * Revenue<br />  * ROI<br />  * ROAS<br />  * ARPU: Revenue/users installing the app<br />  * Rate of users converting: Users making a purchase/users installing the app<br />  * eCPA |
| Conversion | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**In-app events performed one or more times during the 24-hour activity window**<br /><br />**Settings**:<br /><br />* Select 1-6 in-app events to measure from the drop-down list. Limitation: The list is limited to the top 300 events during the previous 30 days.<br />* In the SKAdNetwork dashboard, select a given event as the [conversion event](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings).<br /><br />**Metrics per in-app event:**<br /><br />* * Count of users performing an event<br />  * Conversion rate: Users performing the Conversion Event/users installing the app<br />  * eCPA<br />  * Sessions (uses the *af\_app\_opened* event)<br /><br />Example of user counts:<br /><br />* Completed registration<br />* Made a purchase<br />* Reached a game level<br /><br />**Clarification!**Use conversion measurement to count **if** a user performed an event. To count how many times a user performs an event use engagement measurement. |
| Engagement | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Number of times the user performed a specified in-app event during the Activity Window**<br /><br />**Settings:**<br /><br />* Select an in-app event from the drop-down list.<br />* The in-app selection is also designated as the Conversion Event.<br />* Value range: 0-63<br /><br />**Metrics for the in-app event**:<br /><br />* * Count of users performing the event<br />  * Average number of events per user<br />  * Conversion rate<br />  * eCPA<br />  * Sessions<br /><br />Examples:<br /><br />* Measure the number of times:<br />  * a user opened the app<br />  * the user viewed an ad |



### Decode

Create your own CV-to-event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app.

**To use Decode**:

1. In the AppsFlyer dashboard, go to **Settings** > **SKAN Conversion Studio.**
2. Click options **(⋮)** to display the options menu and:
   * Make sure **SKAN measurement** is turned on. **Note**! If off, the SDK does not call iOS SKAN functions like *registerAppForAdNetworkAttribution*, *updateConversionValue.*
   * Upload your Decode mapping file.
3. Click **Save**.
4. Verify that your partner in-app event postback mappings map the events you have configured.

## Measurement components

### Single Source of Truth



<table><tbody><tr><td colspan="2"><p><img alt="SSOTControl.png" src="https://files.readme.io/77570ca922d33a0ef3df4b5a42904452c07b9b472ea4c68c8390155ed2bc53ed-4458326657553.png"/></p><p><a href="/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Single Source of Truth (SSOT)</a> mechanism flags (and deduplicates) installs reported by more than one attribution matching method. In other words, SKAN and another method. The flag is available in SKAN raw data reports and is considered in calculating metrics in the Overview dashboard <a href="/docs/single-source-of-truth-ssot-guide-for-ios-attribution#overview-dashboard-single-source-of-truth-view">SSOT view</a>. </p></td></tr><tr><td>Mandatory</td><td>No</td></tr><tr><td>Multiple-use permitted</td><td>No</td></tr><tr><td>Setting options</td><td><p>if SSOT is on, the CV is set so that it can flag if a user is attributed by SKAN and another attribution-matching method. </p><p>Where is the SSOT flag used?</p><ul><li>AppsFlyer Overview dashboard SSOT view</li><li>SKAN raw data reports have the <em>af_attribution_flag</em> field. If true, the user was attributed by both SKAN and another method. </li><li>SKAN aggregated attribution API reports.</li></ul></td></tr></tbody></table>



### In-app event component



<table><tbody><tr><td colspan="2"><img alt="ConversionStudioIn-app-event.png" src="https://files.readme.io/7b110093a72b13c0750ccb66da5efe737b8f83c0adcb95eb35185a4dc77bad6c-4406051824657.png"/></td></tr><tr><td>Mandatory</td><td>No</td></tr><tr><td>Multiple-use permitted</td><td>Yes</td></tr><tr><td>Setting options</td><td><p>Select an in-app event; then setup ranges according to your measurement goal as follows: </p><ul><li><strong>Conversion only: </strong>Configure one range with a range of 0–1</li><li><strong>Engagement and conversion: </strong>Configure multiple ranges with your selected ranges</li></ul></td></tr><tr><td>Ranges for engagement</td><td><p>To measure engagement, you must create occurrence ranges. When an occurrence of the selected engagement event is reported, SKAN associates it with the appropriate range according to the number of event occurrences.</p><p><strong>Characteristics</strong></p><ul><li>Each range contains an occurrence range consisting of a <strong>from</strong> value and a <strong>to</strong> value. The lower value isn't included in the range, and the upper value is. For example, 5–10 means greater than 5 up to and including 10.</li><li>The range with the lowest value always starts at 0 (but doesn't include 0 itself). </li><li>You can create as many ranges as you wish, but keep in mind that each range affects your conversion value capacity. </li><li>Ranges must be sequential (without gaps between ranges).</li></ul><p><strong>Measuring engagement using ranges</strong></p><ul><li>When an event occurrence is reported, SKAN associates the occurrence with the appropriate range. Occurrences recorded are derived from the average of the range. The value is rounded up to the nearest integer. For example, 5.7 is rounded up to 6. </li><li>If the number of occurrences exceeds the maximum value of the highest-value range, the occurrences are associated with the highest-value range. The number of occurrences recorded is the average value of the highest-value range’s range. In other words, the actual number of occurrences is disregarded. </li><li>In raw data, both the actual number of occurrences and ranges are available.</li></ul><p><strong>Example:</strong></p><p>In the image, the following occurrence ranges are depicted:</p><p>The occurrence ranges set are:</p><ul><li>A: 0-5</li><li>B: 5-10</li><li>C: 10-20</li></ul><p>Number of occurrences are recorded using the ranges as follows:</p><figure><table><thead><tr><th>Example</th><th>Number of occurrences reported by the SDK</th><th>Associated range</th><th>Number of occurrences reported</th></tr></thead><tbody><tr><td>1</td><td>5</td><td>A </td><td>3</td></tr><tr><td>2</td><td>6</td><td>B</td><td>8</td></tr><tr><td>3</td><td>10</td><td>B</td><td>8</td></tr><tr><td>4</td><td>125</td><td>C</td><td>15</td></tr></tbody></table></figure></td></tr><tr><td>Limitation</td><td>A given in-app event can be associated once with this component.</td></tr></tbody></table>



### Revenue component



<table><tbody><tr><td colspan="2"><img alt="ConversionStudioRevenue.png" src="https://files.readme.io/202c258f11cd93248f8aceff410126efc02ced11e9a9b159bac8ba81cbc8d9fe-4406075612305.png"/></td></tr><tr><td>Mandatory</td><td>No</td></tr><tr><td>Multiple-use permitted</td><td>Yes, if using the in-app event revenue source. </td></tr><tr><td>Setting options</td><td><p>Overall revenue from all revenue streams can be recorded using a single event or by individual streams by selecting specific in-app events that generate revenue. </p><p>The following revenue source options are supported: </p><ul><li><strong>Overall revenue</strong><ul><li>Overall revenue which includes revenue from all in-app events and ad revenue (when relevant), can be measured using a single <code>af_skad_revenue</code>  event. Ensure that the <code>af_skad_revenue</code> event name is correctly mapped for partners.</li><li>The component can be included once. </li></ul></li><li><strong>In-app event</strong><ul><li>Measuring different revenue streams can be done by selecting specific in-app events in the SKAN schema. After adding revenue measurement, select "in-app event" in the revenue source selection. Make sure all the events are mapped properly to ad networks.<br/>Note: When measuring revenue from specific in-app events,  <code>af_skad_revenue</code> shouldn't be mapped.</li><li>The component can be used multiple times.</li><li><mark>If you report revenue by postback to ad networks, verify that your in-app event postback mappings include the in-app revenue events set by you.</mark></li></ul></li></ul></td></tr><tr><td>Ranges</td><td><p>To measure revenue, you must create revenue ranges. When revenue is reported, SKAN associates the reported revenue with the appropriate range.</p><p><strong>Characteristics</strong></p><ul><li>Each range contains a revenue range consisting of a <strong>from</strong> value and a <strong>to</strong> value. The lower value isn't included in the range; however, the upper value is included. For example, 5–10 means greater than 5 up to and including 10. </li><li>The range with the lowest value always starts at 0 (but doesn't include 0 itself). </li><li>You can create as many ranges as you wish, but keep in mind that each range affects your conversion value capacity.</li><li>Ranges must be sequential (without gaps between them.)</li><li>Amounts are in USD</li><li>If you run campaigns on Meta ads, you must have 4 or more ranges. </li><li>Range values can have up to 4 digits after the decimal point.</li></ul><p><strong>Recording revenue using ranges</strong></p><ul><li>When revenue is reported, SKAN associates the revenue with the appropriate range. The revenue recorded equals the average value of the range. </li><li>If the revenue reported exceeds the average value of the highest-value range, the revenue is associated with the highest-value range. <strong>Note</strong>! <mark>The revenue recorded is the average value of this range.</mark> In other words, the actual revenue amount is disregarded.</li><li>In raw data, the revenue recorded and the associated range are available. </li></ul><p><strong>Example:</strong></p><p>In the image, the following revenue ranges are depicted:</p><ul><li>A: 0-5</li><li>B: 5-10</li><li>C: 10-20</li></ul><p>Revenue is recorded using the ranges as follows: </p><figure><table><thead><tr><th>Example</th><th>Revenue reported by the SDK</th><th>Associated range</th><th>Revenue recorded</th></tr></thead><tbody><tr><td>1</td><td>5</td><td>A </td><td>$2.5</td></tr><tr><td>2</td><td>6</td><td>B</td><td>$7.5</td></tr><tr><td>3</td><td>10</td><td>B</td><td>$7.5</td></tr><tr><td>4</td><td>125</td><td>C</td><td>$15</td></tr></tbody></table></figure></td></tr></tbody></table>



### Funnel component



<table><tbody><tr><td colspan="2"><img alt="ConversionValueFunnel.png" src="https://files.readme.io/b43b5db0cee11c9addd50fb56af1ac6d3221e1956e2ee3c4c21a6940e9dfe61b-4406051997969.png"/> </td></tr><tr><td>Mandatory</td><td>No</td></tr><tr><td>Multiple-use permitted</td><td>No</td></tr><tr><td>Setting options</td><td>List a sequential set of events in a funnel. Since the occurrence of a single event is treated as the occurrence of all preceding events, the order in which you list the events is highly important, as illustrated in the example that follows.</td></tr><tr><td>Example</td><td><p>A funnel contains the events a, f, b, k, and z, as illustrated in the preceding image.</p><figure><table><thead><tr><th>Example</th><th>Event performed</th><th>Events recorded</th></tr></thead><tbody><tr><td>1</td><td>a</td><td>a</td></tr><tr><td>2</td><td>b</td><td>a, f, b</td></tr><tr><td>3</td><td>z</td><td>a, f, b, k, z</td></tr></tbody></table></figure></td></tr></tbody></table>



### Priority measurement component

Use the priority measurement component, part of Custom mode, to rank user action journeys in the app based on your business logic so that high priority measurements override low priority ones. This enables you to choose what to measure in each step of the conversion funnel.

Each priority (maximum 63) can contain revenue, in-app event, or both. When a user performs events in the app, AppsFlyer determines which priority fits the actions performed by the users and sets the CV accordingly.

For ease of understanding, let's compare using Custom with and without the priority component. **Without** priority, AppsFlyer maps all possible measurement combinations to CVs. Whereas **with** priority only measurement combinations explicitly set by you are mapped to CVs.

Priority is best explained in the [detailed example](/docs/skan-conversion-studio#priority-measurement-detailed-example) in this article.

**Priority principles**

* You can set 1-63 priorities. The number available depends on your activity window and Single Source of Truth settings.
* Priority 1 always has the highest priority. The priority with the biggest number has the lowest priority.
* A priority consists of [revenue](/docs/skan-conversion-studio#revenue-component) or i[n-app event,](/docs/skan-conversion-studio#inapp-event-component) or both components. A given priority can contain multiple in-app events and revenue streams.
* Funnel isn't available in priority. However, set multiple in-app events in a priority to measure user conversion in a funnel.
* To use the priority measurement component, you can't have other components, such as in-app events or revenue configured.

**To set measurement using priority:**

1. In AppsFlyer, go to **SKAN Conversion Studio.**
2. Select **Custom**, click **Continue**.
3. If necessary, click **Delete**, to remove the current settings.
4. Click **+ Add measurement**. Select **Priority**.   
   Priority 1 displays.  
   [![Priority1.png](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)](https://support.appsflyer.com/hc/article_attachments/4756458366865)
5. Select a measurement component from:
   * Revenue
   * In-app event
6. Complete the fields according to the user interface.
   * Consider that a priority can consist of revenue, in-app event, or both.
   * Range values of event occurrences and revenue can be of ascending (increasing) or descending (decreasing) order but must be continuous. For example, the following ranges are continuous: 1-5, 5-8, 8-10, and so on. A given range can be used more than once (repeated) if the second time it's used is part of a unique combination and is the same range as the last priority with a range. For example, 1-5, 1-5 + add to cart.  
     **Example of increasing and decreasing revenue**

     

| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | * Window 1: 1-2 days<br />* Window 2: 3-7 days<br />* Window 3: 8-35 days |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<br /><br />* $1-$630 in steps of $10<br />* $1-$63 in steps of $1<br />* $0.01-$0.63 in steps of $0.01 | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | * Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**. | 12-1512h (63 days) |

0
7. Click **Validate.**  
   The **Priority is valid message** displays. If this isn't the case, correct your priority before you continue.
8. Do one of the following:
   * To add a priority, click **+ Add priority.**The existing priority 1 is shifted down and becomes priority 2. Complete the priority settings as previously described.
   * To delete a priority, click **…** > **Delete.**
   * To change the priority level, click **Options** (**⋮**), and select either **Change order** or **Make lowest priority**.
   * To duplicate a priority, click **Options** (**⋮**), and select **Duplicate**.
   * Click **Save**, to complete setting priorities.

### Lock window

**Note**: Lock window is only relevant for SKAN 4 and above.



| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | * Window 1: 1-2 days<br />* Window 2: 3-7 days<br />* Window 3: 8-35 days |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<br /><br />* $1-$630 in steps of $10<br />* $1-$63 in steps of $1<br />* $0.01-$0.63 in steps of $0.01 | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | * Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**. | 12-1512h (63 days) |

1

### Activity window

**Note**:

* Activity window is only relevant for SKAN 3 and below (meaning Custom and fixed modes).
* If you're using SKAN 4+, but user devices or ad networks don't support SKAN 4 yet, the Activity Window is 48 hours.



| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | * Window 1: 1-2 days<br />* Window 2: 3-7 days<br />* Window 3: 8-35 days |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<br /><br />* $1-$630 in steps of $10<br />* $1-$63 in steps of $1<br />* $0.01-$0.63 in steps of $0.01 | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | * Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**. | 12-1512h (63 days) |

2

## Additional information

### View CV mapping

* View the events mapped to a CV by selecting the CV. The mapped events display below the table.
* Download the CV mapping table as a CSV file from the **Conversion value summary** pane. Click **Download mapping file.**
* Get the CV mapping using the [SKAN CV schema API for advertisers](/docs/skan-cv-schema-api-for-advertisers).

![SKAN_download_mapping.png](https://files.readme.io/62dc60da0001c0eccc96791f3f3320f8ea0bc24db3977af4390643c5a95a5ad3-46095838352401.png)

#### CSV mapping file columns



| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | * Window 1: 1-2 days<br />* Window 2: 3-7 days<br />* Window 3: 8-35 days |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<br /><br />* $1-$630 in steps of $10<br />* $1-$63 in steps of $1<br />* $0.01-$0.63 in steps of $0.01 | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | * Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**. | 12-1512h (63 days) |

3

### Conversion value capacity formula

As previously explained, the maximum number of available conversion values is 64. The following formula calculates how many of the available conversion values are used by the mode.

```
(activity time duration in hours / interval size in hours) * 
(number of revenue ranges + 1 ) * 
(number of in-app event ranges + 1 ) * 
(number of steps in a funnel + 1)
```

Adjust the formula to include all measurement components

### Maximized Custom CV examples

#### Example 1



| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | * Window 1: 1-2 days<br />* Window 2: 3-7 days<br />* Window 3: 8-35 days |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<br /><br />* $1-$630 in steps of $10<br />* $1-$63 in steps of $1<br />* $0.01-$0.63 in steps of $0.01 | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | * Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**. | 12-1512h (63 days) |

4

#### Example 2



| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | * Window 1: 1-2 days<br />* Window 2: 3-7 days<br />* Window 3: 8-35 days |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<br /><br />* $1-$630 in steps of $10<br />* $1-$63 in steps of $1<br />* $0.01-$0.63 in steps of $0.01 | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | * Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**. | 12-1512h (63 days) |

5

#### Example 3



| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | * Window 1: 1-2 days<br />* Window 2: 3-7 days<br />* Window 3: 8-35 days |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<br /><br />* $1-$630 in steps of $10<br />* $1-$63 in steps of $1<br />* $0.01-$0.63 in steps of $0.01 | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | * Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**. | 12-1512h (63 days) |

6

#### Example 4



| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | * Window 1: 1-2 days<br />* Window 2: 3-7 days<br />* Window 3: 8-35 days |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<br /><br />* $1-$630 in steps of $10<br />* $1-$63 in steps of $1<br />* $0.01-$0.63 in steps of $0.01 | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | * Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**. | 12-1512h (63 days) |

7

### Priority measurement detailed example

In a shopping app, the advertiser wants to focus measurement on the:

* Actions of **non-paying** users
* Revenue of **paying** users

By doing so, the advertiser uses CVs to more precisely record revenue. These measurement requirements translate to a set of measurement priorities as set out in the table that follows.

Consider:

* The highest priority is always 1. **Note**! Priority numbers don't directly map to CVs. CV mappings display in the user interface.
* The maximum number of priorities is 63. The actual number available depends on the activity window and if Single Source of Truth is on.
* Each priority consists of either a revenue range or in-app event occurrences range, or both.
* Range values: The lower value of the bound isn't included in the range but the higher bound value is included. For example, the range $5-$10 doesn't include the value 5 but does include the value 10.

#### Measurement priorities setting example



| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | * Window 1: 1-2 days<br />* Window 2: 3-7 days<br />* Window 3: 8-35 days |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<br /><br />* $1-$630 in steps of $10<br />* $1-$63 in steps of $1<br />* $0.01-$0.63 in steps of $0.01 | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | * Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**. | 12-1512h (63 days) |

8

The table that follows contains user journey scenarios. Each scenario contains the list of actions performed by the user during their journey and the priority determined by AppsFlyer.

In the table:

* Multiple actions are separated using **>**
* The value in brackets (), is the priority determined by AppsFlyer set after the user completes the action. Using the priority AppsFlyer update the CV in the app.

#### User journey scenarios



| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | * Window 1: 1-2 days<br />* Window 2: 3-7 days<br />* Window 3: 8-35 days |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<br /><br />* $1-$630 in steps of $10<br />* $1-$63 in steps of $1<br />* $0.01-$0.63 in steps of $0.01 | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | * Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**. | 12-1512h (63 days) |

9

### [Legacy] Fixed mode examples

> 📘 **Note**
>
> Fixed modes are unavailable for new apps starting from 23/06/2024. All functionalities are supported in the Custom and SKAN4.


#### Example A: Revenue measurement



| Measurement mode | Description |
| --- | --- |
| Revenue | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Revenue generated during the 24-hour activity window.**<br /><br />Select a unit-to-USD rate from one of the following:<br /><br />* $0.01 to measure up to $0.63<br />* $1 to measure up to $63<br />* $10 to measure up to $630<br /><br />AppsFlyer automatically populates 63 revenue measurement ranges. Ensure that the event name `af_skad_revenue` is correctly mapped for partners. In the dashboard, revenue is recorded as the maximum of the range. For example, if the range is $60-$61, the revenue recorded is $61. Note! Custom revenue uses a different method to calculate revenue.<br /><br />**Metrics available:**<br /><br />* * Revenue<br />  * ROI<br />  * ROAS<br />  * ARPU: Revenue/users installing the app<br />  * Rate of users converting: Users making a purchase/users installing the app<br />  * eCPA |
| Conversion | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**In-app events performed one or more times during the 24-hour activity window**<br /><br />**Settings**:<br /><br />* Select 1-6 in-app events to measure from the drop-down list. Limitation: The list is limited to the top 300 events during the previous 30 days.<br />* In the SKAdNetwork dashboard, select a given event as the [conversion event](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings).<br /><br />**Metrics per in-app event:**<br /><br />* * Count of users performing an event<br />  * Conversion rate: Users performing the Conversion Event/users installing the app<br />  * eCPA<br />  * Sessions (uses the *af\_app\_opened* event)<br /><br />Example of user counts:<br /><br />* Completed registration<br />* Made a purchase<br />* Reached a game level<br /><br />**Clarification!**Use conversion measurement to count **if** a user performed an event. To count how many times a user performs an event use engagement measurement. |
| Engagement | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Number of times the user performed a specified in-app event during the Activity Window**<br /><br />**Settings:**<br /><br />* Select an in-app event from the drop-down list.<br />* The in-app selection is also designated as the Conversion Event.<br />* Value range: 0-63<br /><br />**Metrics for the in-app event**:<br /><br />* * Count of users performing the event<br />  * Average number of events per user<br />  * Conversion rate<br />  * eCPA<br />  * Sessions<br /><br />Examples:<br /><br />* Measure the number of times:<br />  * a user opened the app<br />  * the user viewed an ad |

0

#### Example B: Conversion measurement



| Measurement mode | Description |
| --- | --- |
| Revenue | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Revenue generated during the 24-hour activity window.**<br /><br />Select a unit-to-USD rate from one of the following:<br /><br />* $0.01 to measure up to $0.63<br />* $1 to measure up to $63<br />* $10 to measure up to $630<br /><br />AppsFlyer automatically populates 63 revenue measurement ranges. Ensure that the event name `af_skad_revenue` is correctly mapped for partners. In the dashboard, revenue is recorded as the maximum of the range. For example, if the range is $60-$61, the revenue recorded is $61. Note! Custom revenue uses a different method to calculate revenue.<br /><br />**Metrics available:**<br /><br />* * Revenue<br />  * ROI<br />  * ROAS<br />  * ARPU: Revenue/users installing the app<br />  * Rate of users converting: Users making a purchase/users installing the app<br />  * eCPA |
| Conversion | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**In-app events performed one or more times during the 24-hour activity window**<br /><br />**Settings**:<br /><br />* Select 1-6 in-app events to measure from the drop-down list. Limitation: The list is limited to the top 300 events during the previous 30 days.<br />* In the SKAdNetwork dashboard, select a given event as the [conversion event](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings).<br /><br />**Metrics per in-app event:**<br /><br />* * Count of users performing an event<br />  * Conversion rate: Users performing the Conversion Event/users installing the app<br />  * eCPA<br />  * Sessions (uses the *af\_app\_opened* event)<br /><br />Example of user counts:<br /><br />* Completed registration<br />* Made a purchase<br />* Reached a game level<br /><br />**Clarification!**Use conversion measurement to count **if** a user performed an event. To count how many times a user performs an event use engagement measurement. |
| Engagement | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Number of times the user performed a specified in-app event during the Activity Window**<br /><br />**Settings:**<br /><br />* Select an in-app event from the drop-down list.<br />* The in-app selection is also designated as the Conversion Event.<br />* Value range: 0-63<br /><br />**Metrics for the in-app event**:<br /><br />* * Count of users performing the event<br />  * Average number of events per user<br />  * Conversion rate<br />  * eCPA<br />  * Sessions<br /><br />Examples:<br /><br />* Measure the number of times:<br />  * a user opened the app<br />  * the user viewed an ad |

1

#### Example C: Engagement measurement



| Measurement mode | Description |
| --- | --- |
| Revenue | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Revenue generated during the 24-hour activity window.**<br /><br />Select a unit-to-USD rate from one of the following:<br /><br />* $0.01 to measure up to $0.63<br />* $1 to measure up to $63<br />* $10 to measure up to $630<br /><br />AppsFlyer automatically populates 63 revenue measurement ranges. Ensure that the event name `af_skad_revenue` is correctly mapped for partners. In the dashboard, revenue is recorded as the maximum of the range. For example, if the range is $60-$61, the revenue recorded is $61. Note! Custom revenue uses a different method to calculate revenue.<br /><br />**Metrics available:**<br /><br />* * Revenue<br />  * ROI<br />  * ROAS<br />  * ARPU: Revenue/users installing the app<br />  * Rate of users converting: Users making a purchase/users installing the app<br />  * eCPA |
| Conversion | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**In-app events performed one or more times during the 24-hour activity window**<br /><br />**Settings**:<br /><br />* Select 1-6 in-app events to measure from the drop-down list. Limitation: The list is limited to the top 300 events during the previous 30 days.<br />* In the SKAdNetwork dashboard, select a given event as the [conversion event](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings).<br /><br />**Metrics per in-app event:**<br /><br />* * Count of users performing an event<br />  * Conversion rate: Users performing the Conversion Event/users installing the app<br />  * eCPA<br />  * Sessions (uses the *af\_app\_opened* event)<br /><br />Example of user counts:<br /><br />* Completed registration<br />* Made a purchase<br />* Reached a game level<br /><br />**Clarification!**Use conversion measurement to count **if** a user performed an event. To count how many times a user performs an event use engagement measurement. |
| Engagement | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Number of times the user performed a specified in-app event during the Activity Window**<br /><br />**Settings:**<br /><br />* Select an in-app event from the drop-down list.<br />* The in-app selection is also designated as the Conversion Event.<br />* Value range: 0-63<br /><br />**Metrics for the in-app event**:<br /><br />* * Count of users performing the event<br />  * Average number of events per user<br />  * Conversion rate<br />  * eCPA<br />  * Sessions<br /><br />Examples:<br /><br />* Measure the number of times:<br />  * a user opened the app<br />  * the user viewed an ad |

4

### SKAN Conversion Studio API

If you have many apps for which you want similar SKAN conversion value configurations, it may be time-consuming and challenging to design the schema for each app separately in the Conversion Studio UI. To save time and effort, you can configure your SKAN schema in the UI once, and then use the SKAN Conversion Studio API to use that same schema in multiple apps. **Note**: The API only supports schemas configured in the UI using SKAN 4 or custom measurement modes.

**To use the SKAN Conversion Studio API**:

1. Get the [API token](/docs/managing-appsflyer-tokens). An admin needs to retrieve the token.
2. Give your developer the API token to be used in the authentication header.
3. Give your developers the app IDs of:
   * The app for which the SKAN schema is configured in the UI (meaning the app from which you want to copy the SKAN schema).
   * All the apps that you want to have the same schema.
4. Tell your developer to follow their [SKAN Conversion Studio API instructions](https://dev.appsflyer.com/hc/reference/skan-studio-config-overview-1) in the developer hub.

**Note**:

* The API can be used to copy the schema to one app per API call. However, your developer can then create a script to copy the required schema to multiple apps.
* SKAN Conversion Studio API isn't available for agencies.

### SKAN schema analysis

Understand how your conversion values are being used, identify underperforming schema configurations, and refine your SKAN measurement setup based on real usage data.

Conversion value distribution insights are made up of three tabs that help you optimize different aspect of your SKAN schema:

* Conversion Values tab
* Revenue tab
* Events tab

#### **Conversion Values tab**

See which conversion values are actually being used, and which are not.

A balanced conversion value distribution ensures your SKAN schema effectively captures user behavior. Unused conversion values signal underutilized measurement combinations, leading to wasted SKAN capacity and missed optimization opportunities.

* Displays the frequency of each conversion value over the last 7 days of postbacks.
* Highlights values that received 0 postbacks.
* Helps optimize value allocation and avoid wasted measurement capacity.
* Especially useful for apps using priority-based schemas.

**Threshold for identifying unused values**  
✅ All CVs are used  
⚠️ If at least one CV has no postbacks at all, then this error symbol is shown.

#### **Revenue tab**

Check whether your defined revenue buckets match real user spend.

Revenue accuracy can be improved by optimizing SKAN's predefined revenue ranges. SKAN reports the average value of each range, which may not reflect actual user spending. Misaligned ranges create discrepancies, leading to inaccurate revenue reporting and affecting ROAS and budget allocation.

The chart displays the distribution of paying users across your defined revenue buckets. When there’s a mismatch between actual user spend and the reported average revenue per paying user (ARPPU), a recommendation is provided to revise the schema.

* Shows if your schema includes revenue mapping.
* Shows how paying users are distributed across revenue ranges.
* Identifies discrepancies between average revenue per paying user (ARPPU) and actual spend.
* Suggests schema updates to improve revenue accuracy.
* If your app is eligible for the Revenue Recommendation Model, a customized ARPPU accuracy calculation based on your schema will also be shown.

**Threshold for reporting error**

✅ Revenue error ≤ 3%

⚠️ Revenue error > 3%

#### **Events tab**

Ensure your SKAN-mapped events occur frequently enough to provide value.

This tab shows if at least one in-app event is mapped to SKAN.

The chart shows the percentage of installs that triggered each mapped event during the first activity window. Events with low frequency or no occurrence are highlighted, helping you ensure optimal usage of your conversion schema.

Ensuring that all selected events occur within the first activity window prevents unused measurement capacity and helps make the most of the available conversion values.

* Appears if at least one event is mapped in the schema.
* Hidden if no mapped events recorded installs in the last 7 days.
* Displays the percentage of installs that triggered each mapped event during the first activity window.
* Highlights events that occur rarely or not at all.
* Helps avoid underused events that waste schema potential.

**Threshold for event frequency**

✅ All events ≥ 3 % of installs

⚠️ One or more events < 3 %

## Additional procedures

### Change SKAN measurement mode

Consider:

* Once you start using SKAN 4 measurement mode, it isn't recommended to change back to an earlier mode.
* When you make settings change, they begin to take effect from 00:00 AM UTC and a transition period begins. During this period we decode the conversion value using the most recently selected settings. However, a postback arriving now relates to an install that occurred sometime in the past.
* The number of installs reported is not related to the settings change and is accurate.

### Disable SKAN measurement

To turn off SKAdNetwork measurement:

1. In AppsFlyer, go to **Settings** > **SKAN Conversion Studio.**
2. Click **⋮** .
3. Turn off **SKAdNetwork measurement.**  
   Among other things, the SDK stops calling SKAN functions like *registerAppForAdNetworkAttribution*, *updateConversionValue.*
4. Click **Save changes.**

### Report events by server-to-server API

![SKAdNetwork_-_S2S__2_.png](https://files.readme.io/ed55e5c10184afcc27ce7e414a3213f69d2c20bd70d38f78be338f1b17254ee2-16281446657937.png)

Both the SDK and [server-to-server API (S2S)](/docs/server-to-server-events-api-for-mobile-s2s-mobile) can send in-app events to AppsFlyer servers.

The S2Sflow is as follows:

* An event occurs related to the user in the advertiser's servers. The app may be open or closed at this time.
* Advertiser servers report the event to AppsFlyer by S2S.
* AppsFlyer calculates the updated conversion value and then:
  * If the app is open on the user device: the SDK is notified of the updated value. The SDK updates the iOS conversion value on the device.
  * If the app isn't open on the user device: the server waits until the app is opened to notify the SDK of the conversion value. This must occur before the expiry of the Activity Window. If notification fails, the event is disregarded.

**SDK version required**

* Adopt the latest SDK version in the app. **Note!** No additional action is required by the developer.

**To implement in-app event sending by server-to-server API:**

1. Do one of the following:
   * If your selected mode is SKAN 4 or Custom:
     * No settings changes are required.
   * If your selected mode is revenue, conversion, or engagement:
     1. In AppsFlyer, go to **Settings** > **SKAN Conversion Studio.**
     2. Click options (⋮).
     3. Turn on **Record in-app events sent by server-to-server API**.
2. Send events by S2S.

**Limitation**

* If you implement *user anonymization* for a given user then you can't send events by S2S for that user.

### Add SSOT to fixed mode measurements

> 📘 **Note**
>
> Fixed modes are unavailable for new apps starting from 23/06/2024. All functionalities are supported in the Custom and SKAN4.


If you have the Revenue or Engagement measurement mode set up, Single Source of Truth (SSOT, which deduplicates and accurately reports iOS data), isn't supported. [Learn more about SSOT](/docs/single-source-of-truth-ssot-guide-for-ios-attribution)

**To enable SSOT when you have Revenue or Engagement mode set up**:

1. In AppsFlyer, go to **Settings** > **SKAN Conversion Studio**.
2. Scroll down to your active measurement mode.
3. Click **+ Add Single Source of Truth**.
   * The Single Source of Truth toggle is automatically turned on.
   * Your fixed mode measurement ranges are minimally changed, to allow SSOT some conversion value space.
4. Click **Save.**

### Conversion value decrease

In [SKAN 4](/docs/skan-conversion-studio#skan-4) mode, you have the ability to increase or decrease the conversion value (CV). By default, CV is set to increase. By enabling conversion values to decrease, the postback will contain the latest value in the window when sending negative revenue, even if it was higher before. This capability is relevant for fine and coarse conversion values across all [three windows.](/docs/skan-conversion-studio#measurement-principles-and-definitions)   
**Note:** The Ad-revenue value will never go in the negative.

To enable conversion value decrease:

1. In AppsFlyer, go to **Settings** > **SKAN Conversion Studio**.
2. Select the **SKAN 4.0** measurement mode.
3. Click options **(⋮)** to display the options menu and:
   * Make sure **Allow conversion decrease** is turned on.   
     **Note**! This will only be available to:
     * Apps that have been previously saved in SKAN 4 mode in conversion studio.
     * Users with edit access

#### Examples

**Examples with negative revenue**



| Measurement mode | Description |
| --- | --- |
| Revenue | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Revenue generated during the 24-hour activity window.**<br /><br />Select a unit-to-USD rate from one of the following:<br /><br />* $0.01 to measure up to $0.63<br />* $1 to measure up to $63<br />* $10 to measure up to $630<br /><br />AppsFlyer automatically populates 63 revenue measurement ranges. Ensure that the event name `af_skad_revenue` is correctly mapped for partners. In the dashboard, revenue is recorded as the maximum of the range. For example, if the range is $60-$61, the revenue recorded is $61. Note! Custom revenue uses a different method to calculate revenue.<br /><br />**Metrics available:**<br /><br />* * Revenue<br />  * ROI<br />  * ROAS<br />  * ARPU: Revenue/users installing the app<br />  * Rate of users converting: Users making a purchase/users installing the app<br />  * eCPA |
| Conversion | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**In-app events performed one or more times during the 24-hour activity window**<br /><br />**Settings**:<br /><br />* Select 1-6 in-app events to measure from the drop-down list. Limitation: The list is limited to the top 300 events during the previous 30 days.<br />* In the SKAdNetwork dashboard, select a given event as the [conversion event](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings).<br /><br />**Metrics per in-app event:**<br /><br />* * Count of users performing an event<br />  * Conversion rate: Users performing the Conversion Event/users installing the app<br />  * eCPA<br />  * Sessions (uses the *af\_app\_opened* event)<br /><br />Example of user counts:<br /><br />* Completed registration<br />* Made a purchase<br />* Reached a game level<br /><br />**Clarification!**Use conversion measurement to count **if** a user performed an event. To count how many times a user performs an event use engagement measurement. |
| Engagement | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Number of times the user performed a specified in-app event during the Activity Window**<br /><br />**Settings:**<br /><br />* Select an in-app event from the drop-down list.<br />* The in-app selection is also designated as the Conversion Event.<br />* Value range: 0-63<br /><br />**Metrics for the in-app event**:<br /><br />* * Count of users performing the event<br />  * Average number of events per user<br />  * Conversion rate<br />  * eCPA<br />  * Sessions<br /><br />Examples:<br /><br />* Measure the number of times:<br />  * a user opened the app<br />  * the user viewed an ad |

6

**Example 1**

User made a $5 purchase - you will see an increase to CV 1  
User then made a $20 purchase - you will see an increase to CV 3  
User then had a  -$10 purchase - you will see a decrease to CV 1  
User then made an add\_to\_cart event - you will see an increase to CV 2

**Example 2**

User made a $25 purchase - you will see an increase to CV 3  
User then triggered af\_add\_to\_cart - it will remain on CV 3  
User then had a -$20 purchase - you will see a decrease to CV 1

**Example of an in-app schema**



| Measurement mode | Description |
| --- | --- |
| Revenue | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Revenue generated during the 24-hour activity window.**<br /><br />Select a unit-to-USD rate from one of the following:<br /><br />* $0.01 to measure up to $0.63<br />* $1 to measure up to $63<br />* $10 to measure up to $630<br /><br />AppsFlyer automatically populates 63 revenue measurement ranges. Ensure that the event name `af_skad_revenue` is correctly mapped for partners. In the dashboard, revenue is recorded as the maximum of the range. For example, if the range is $60-$61, the revenue recorded is $61. Note! Custom revenue uses a different method to calculate revenue.<br /><br />**Metrics available:**<br /><br />* * Revenue<br />  * ROI<br />  * ROAS<br />  * ARPU: Revenue/users installing the app<br />  * Rate of users converting: Users making a purchase/users installing the app<br />  * eCPA |
| Conversion | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**In-app events performed one or more times during the 24-hour activity window**<br /><br />**Settings**:<br /><br />* Select 1-6 in-app events to measure from the drop-down list. Limitation: The list is limited to the top 300 events during the previous 30 days.<br />* In the SKAdNetwork dashboard, select a given event as the [conversion event](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings).<br /><br />**Metrics per in-app event:**<br /><br />* * Count of users performing an event<br />  * Conversion rate: Users performing the Conversion Event/users installing the app<br />  * eCPA<br />  * Sessions (uses the *af\_app\_opened* event)<br /><br />Example of user counts:<br /><br />* Completed registration<br />* Made a purchase<br />* Reached a game level<br /><br />**Clarification!**Use conversion measurement to count **if** a user performed an event. To count how many times a user performs an event use engagement measurement. |
| Engagement | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Number of times the user performed a specified in-app event during the Activity Window**<br /><br />**Settings:**<br /><br />* Select an in-app event from the drop-down list.<br />* The in-app selection is also designated as the Conversion Event.<br />* Value range: 0-63<br /><br />**Metrics for the in-app event**:<br /><br />* * Count of users performing the event<br />  * Average number of events per user<br />  * Conversion rate<br />  * eCPA<br />  * Sessions<br /><br />Examples:<br /><br />* Measure the number of times:<br />  * a user opened the app<br />  * the user viewed an ad |

7

**Example**

User did a session event - you will see an increase to CV 1  
User then made a purchase event - you will see an increase to CV 3  
User then did another session event - it will remain on CV 3

### Support Anonymized Users

Enabling the **Support anonymized users** toggle ensures that SKAN conversion values are accurately updated for [anonymized users](/docs/apply-privacy-preserving-sdk-methods#anonymize-user-information), while still protecting their privacy.

> 📘 **Important!**
>
> This feature is relevant only for apps that call the [anonymize user method](/docs/apply-privacy-preserving-sdk-methods#anonymize-user-information) to remove and hash all user-identifying information. To ensure accurate reporting by SKAN, these apps must activate the **Support anonymized users** toggle.


Why is it needed?  
SKAN uses identifiers to update conversion values based on post-install activity. When an app calls the **anonymize user method** after calling the start method, the system may not be able to link some post-install events to the original install, leading to inaccurate conversion value updates.  
By activating the **Support anonymized users** toggle, the system creates hashed identifiers for all users upon installation. This allows the app to properly link user activity to the original install, even if the user becomes anonymized at a later point, ensuring accurate reporting.

### SSOT mapping patterns

When Single Source of Truth (SSOT) is enabled in your SKAN schema, you can configure how conversion values are structured. This allows for better alignment with your reporting goals and strategic attribution needs.

Mapping patterns define how conversion values (CVs) are organized to represent different install types. These include installs attributed via AppsFlyer’s classic attribution methods and non-attributed installs.  
AppsFlyer supports two mapping patterns:

#### **Half and half**

* Divides CVs into two halves:
  * The lower half represents increasing engagement levels.
    * Logic: CVs with `af_attribution_flag=false`
  * The upper half duplicates the lower half but explicitly marks values as attributed via AppsFlyer’s classic attribution methods.
    * Logic: Duplicates of lower CVs with `af_attribution_flag=true`

#### **Pairing**

* Groups CVs in pairs.
  * Each CV is immediately followed by another that represents the same engagement level but is explicitly marked and attributed via classic attribution.
  * Ensures ascending CV order, consistently represents increasing user engagement levels
  * Logic: Each CV is followed by its duplicate marked with `af_attribution_flag=true`

#### How to configure mapping patterns

To use Mapping Patterns:

1. Enable SSOT in your SKAN schema.
2. In the schema editor, click the **More options** (three dots) menu.
3. Select **Mapping pattern**.
4. Choose your preferred pattern:
   * **Half-and-half** (default)
   * **Pairing**
5. Review the updated schema preview and calendar view.
6. Save your schema.

#### **FAQ**

**Q: What happens if SSOT is disabled?**  
A: The Mapping Pattern selector is unavailable when SSOT is turned off.

**Q: Can I revert to the default pattern?**  
A: Yes. **Half-and-half** is the default and can be reselected anytime.

**Q: Are these changes reflected in the schema APIs?**  
A: Yes. All selected patterns are reflected in SKAN schema APIs for both marketers and networks.

**Q: Can two CVs have the same event but different SSOT flags?**  
A: Yes. That is now considered valid behavior under the updated validation logic.

## Specifications and limitations



| Measurement mode | Description |
| --- | --- |
| Revenue | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Revenue generated during the 24-hour activity window.**<br /><br />Select a unit-to-USD rate from one of the following:<br /><br />* $0.01 to measure up to $0.63<br />* $1 to measure up to $63<br />* $10 to measure up to $630<br /><br />AppsFlyer automatically populates 63 revenue measurement ranges. Ensure that the event name `af_skad_revenue` is correctly mapped for partners. In the dashboard, revenue is recorded as the maximum of the range. For example, if the range is $60-$61, the revenue recorded is $61. Note! Custom revenue uses a different method to calculate revenue.<br /><br />**Metrics available:**<br /><br />* * Revenue<br />  * ROI<br />  * ROAS<br />  * ARPU: Revenue/users installing the app<br />  * Rate of users converting: Users making a purchase/users installing the app<br />  * eCPA |
| Conversion | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**In-app events performed one or more times during the 24-hour activity window**<br /><br />**Settings**:<br /><br />* Select 1-6 in-app events to measure from the drop-down list. Limitation: The list is limited to the top 300 events during the previous 30 days.<br />* In the SKAdNetwork dashboard, select a given event as the [conversion event](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings).<br /><br />**Metrics per in-app event:**<br /><br />* * Count of users performing an event<br />  * Conversion rate: Users performing the Conversion Event/users installing the app<br />  * eCPA<br />  * Sessions (uses the *af\_app\_opened* event)<br /><br />Example of user counts:<br /><br />* Completed registration<br />* Made a purchase<br />* Reached a game level<br /><br />**Clarification!**Use conversion measurement to count **if** a user performed an event. To count how many times a user performs an event use engagement measurement. |
| Engagement | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Number of times the user performed a specified in-app event during the Activity Window**<br /><br />**Settings:**<br /><br />* Select an in-app event from the drop-down list.<br />* The in-app selection is also designated as the Conversion Event.<br />* Value range: 0-63<br /><br />**Metrics for the in-app event**:<br /><br />* * Count of users performing the event<br />  * Average number of events per user<br />  * Conversion rate<br />  * eCPA<br />  * Sessions<br /><br />Examples:<br /><br />* Measure the number of times:<br />  * a user opened the app<br />  * the user viewed an ad |

8