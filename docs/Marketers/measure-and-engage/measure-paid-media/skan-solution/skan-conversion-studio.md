---
title: SKAN Conversion Studio
excerpt: >-
  Use SKAN Conversion Studio to set which user engagements in the app to
  measure, and for how long. Measure revenue, conversion, engagement, and
  retention during a limited post-install period. By adding the Single Source of
  Truth measurement we can let you know if the user was attributed by both
  AppsFlyer and SKAN.
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2021-07-08T09:26:58Z'
  edited_at: '2026-04-26T06:04:28Z'
  id: 4403727223185
  locale: en-us
  section: SKAN solution
  section_id: 6552135379985
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4403727223185-SKAN-Conversion-Studio
---
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
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Best practice]<br /><br />[Default] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows.<br /><br />The 3 windows measure 3 different, non-overlapping, post-install time periods. Meaning, window 2 measures days 3-7 post-install, not days 0-7. | <ul><li>Window 1: 1-2 days</li><li>Window 2: 3-7 days</li><li>Window 3: 8-35 days</li></ul> |
| Flexible | Custom | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12-1512h (default is up to 72 hours, but can be extended) |
| Fixed* | Revenue<br /><br />[Legacy] | Measure revenue using one of the following ranges:<ul><li>$1-$630 in steps of $10</li><li>$1-$63 in steps of $1</li><li>$0.01-$0.63 in steps of $0.01</li></ul> | 24h |
| Fixed* | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed* | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | [Decode](/docs/skan-cv-decode-map-your-cv-to-events) | <ul><li>Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**.</li></ul> | 12-1512h (63 days) |

*Fixed modes are unavailable for new apps starting from 23/06/2024.  All functionalities are supported in the Custom and SKAN4 modes.

**Tip!** Experiment with Conversion Studio. In AppsFlyer go to > **Settings** > **SKAN Conversion Studio**.

<div id="measurement-principles-and-definitions" />

<Accordion title="Measurement principles and definitions">

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

* **![Admin.png](https://files.readme.io/74a71649d541921d2b61425323cc4cf5b669cd4d5665294d0813a3e9230bd11d-4405725144977.png) Admin only:** Only an admin can save Conversion Studio settings. Account users can view the settings.
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

</Accordion>

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

<div id="skan-4" />

<Accordion title="SKAN 4">

In SKAN 4, you use different measurement components like revenue, in-app events, priority, and Single Source of Truth, to determine what is measured during each of the three measurement windows. Together the components create your SKAN 4 measurement mode.

If you’re upgrading to SKAN 4 from a previous SKAN mode, your current schema mapping is carried over for the window 1 fine configuration. AppsFlyer automatically maps the coarse values for you for windows 1-3.

To manually set SKAN 4, experiment with different options. As you make changes, the **Conversion-value capacity** summary updates. Optimize your settings to capture the data most valuable to you without exceeding the capacity. See [Conversion value capacity calculation.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**Note: If you’re upgrading to SKAN 4 from a previous SKAN mode, your current schema mapping is carried over for fine measurements and AppsFlyer automatically maps the coarse values for you. And if you’re new to SKAN, AppsFlyer provides an initial default mapping.**

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) To manually set conversion values in Conversion Studio using SKAN 4 mode:**

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

</Accordion>

<div id="custom" />

<Accordion title="Custom">

In Custom, you use different measurement components like revenue, in-app events, priority, and Single Source of Truth, to determine what is measured and set an activity window to determine for how long and at what intervals measurement occurs. Together, the components create your Custom measurement mode.

To set Custom, experiment with different options. As you make changes, the **Conversion-value capacity** summary updates. Optimize your settings to capture the data most valuable to you without exceeding the capacity. See [Conversion value capacity calculation.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

Note: By default, AppsFlyer displays SKAN 4 on the Conversion Studio. To revert to a previous mode, click options **(⋮)** to display the options menu and select Revert to the previous SKAN version.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) To manually set conversion values in Conversion Studio using Custom mode:**

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

</Accordion>

<div id="fixed-modes" />

<Accordion title="[Legacy] Fixed modes">

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

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) To manually set conversion values in Conversion Studio using a fixed mode:**

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
| Revenue | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Revenue generated during the 24-hour activity window.**<br /><br />Select a unit-to-USD rate from one of the following:<ul><li>$0.01 to measure up to $0.63</li><li>$1 to measure up to $63</li><li>$10 to measure up to $630</li></ul>AppsFlyer automatically populates 63 revenue measurement ranges. Ensure that the event name `af_skad_revenue` is correctly mapped for partners. In the dashboard, revenue is recorded as the maximum of the range. For example, if the range is $60-$61, the revenue recorded is $61. Note! Custom revenue uses a different method to calculate revenue.<br /><br />**Metrics available:**<ul><li>Revenue<ul><li>ROI</li><li>ROAS</li><li>ARPU: Revenue/users installing the app</li><li>Rate of users converting: Users making a purchase/users installing the app</li><li>eCPA</li></ul></li></ul> |
| Conversion | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**In-app events performed one or more times during the 24-hour activity window**<br /><br />**Settings**:<ul><li>Select 1-6 in-app events to measure from the drop-down list. Limitation: The list is limited to the top 300 events during the previous 30 days.</li><li>In the SKAdNetwork dashboard, select a given event as the [conversion event](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings).</li></ul>**Metrics per in-app event:**<ul><li>Count of users performing an event<ul><li>Conversion rate: Users performing the Conversion Event/users installing the app</li><li>eCPA</li><li>Sessions (uses the *af\_app\_opened* event)</li></ul></li></ul>Example of user counts:<ul><li>Completed registration</li><li>Made a purchase</li><li>Reached a game level</li></ul>**Clarification!** Use conversion measurement to count **if** a user performed an event. To count how many times a user performs an event use engagement measurement. |
| Engagement | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Number of times the user performed a specified in-app event during the Activity Window**<br /><br />**Settings:**<ul><li>Select an in-app event from the drop-down list.</li><li>The in-app selection is also designated as the Conversion Event.</li><li>Value range: 0-63</li></ul>**Metrics for the in-app event**:<ul><li>Count of users performing the event<ul><li>Average number of events per user</li><li>Conversion rate</li><li>eCPA</li><li>Sessions</li></ul></li></ul>Examples:<ul><li>Measure the number of times:<ul><li>a user opened the app</li><li>the user viewed an ad</li></ul></li></ul> |

</Accordion>

<div id="decode" />

<Accordion title="Decode">

Create your own CV-to-event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app.

**To use Decode**:

1. In the AppsFlyer dashboard, go to **Settings** > **SKAN Conversion Studio.**
2. Click options **(⋮)** to display the options menu and:
   * Make sure **SKAN measurement** is turned on. **Note**! If off, the SDK does not call iOS SKAN functions like *registerAppForAdNetworkAttribution*, *updateConversionValue.*
   * Upload your Decode mapping file.
3. Click **Save**.
4. Verify that your partner in-app event postback mappings map the events you have configured.

</Accordion>

## Measurement components

<div id="single-source-of-truth" />

<Accordion title="Single Source of Truth">

<table><tbody><tr><td colspan="2"><p><img alt="SSOTControl.png" src="https://files.readme.io/77570ca922d33a0ef3df4b5a42904452c07b9b472ea4c68c8390155ed2bc53ed-4458326657553.png"/></p><p><a href="./single-source-of-truth-ssot-guide-for-ios-attribution">Single Source of Truth (SSOT)</a> mechanism flags (and deduplicates) installs reported by more than one attribution matching method. In other words, SKAN and another method. The flag is available in SKAN raw data reports and is considered in calculating metrics in the Overview dashboard <a href="./single-source-of-truth-ssot-guide-for-ios-attribution#overview-dashboard-single-source-of-truth-view">SSOT view</a>. </p></td></tr><tr><td>Mandatory</td><td>No</td></tr><tr><td>Multiple-use permitted</td><td>No</td></tr><tr><td>Setting options</td><td><p>if SSOT is on, the CV is set so that it can flag if a user is attributed by SKAN and another attribution-matching method. </p><p>Where is the SSOT flag used?</p><ul><li>AppsFlyer Overview dashboard SSOT view</li><li>SKAN raw data reports have the <em>af_attribution_flag</em> field. If true, the user was attributed by both SKAN and another method. </li><li>SKAN aggregated attribution API reports.</li></ul></td></tr></tbody></table>

</Accordion>

<div id="inapp-event-component" />

<Accordion title="In-app event component">

<table><tbody><tr><td colspan="2"><img alt="ConversionStudioIn-app-event.png" src="https://files.readme.io/7b110093a72b13c0750ccb66da5efe737b8f83c0adcb95eb35185a4dc77bad6c-4406051824657.png"/></td></tr><tr><td>Mandatory</td><td>No</td></tr><tr><td>Multiple-use permitted</td><td>Yes</td></tr><tr><td>Setting options</td><td><p>Select an in-app event; then setup ranges according to your measurement goal as follows: </p><ul><li><strong>Conversion only: </strong>Configure one range with a range of 0–1</li><li><strong>Engagement and conversion: </strong>Configure multiple ranges with your selected ranges</li></ul></td></tr><tr><td>Ranges for engagement</td><td><p>To measure engagement, you must create occurrence ranges. When an occurrence of the selected engagement event is reported, SKAN associates it with the appropriate range according to the number of event occurrences.</p><p><strong>Characteristics</strong></p><ul><li>Each range contains an occurrence range consisting of a <strong>from</strong> value and a <strong>to</strong> value. The lower value isn't included in the range, and the upper value is. For example, 5–10 means greater than 5 up to and including 10.</li><li>The range with the lowest value always starts at 0 (but doesn't include 0 itself). </li><li>You can create as many ranges as you wish, but keep in mind that each range affects your conversion value capacity. </li><li>Ranges must be sequential (without gaps between ranges).</li></ul><p><strong>Measuring engagement using ranges</strong></p><ul><li>When an event occurrence is reported, SKAN associates the occurrence with the appropriate range. Occurrences recorded are derived from the average of the range. The value is rounded up to the nearest integer. For example, 5.7 is rounded up to 6. </li><li>If the number of occurrences exceeds the maximum value of the highest-value range, the occurrences are associated with the highest-value range. The number of occurrences recorded is the average value of the highest-value range’s range. In other words, the actual number of occurrences is disregarded. </li><li>In raw data, both the actual number of occurrences and ranges are available.</li></ul><p><strong>Example:</strong></p><p>In the image, the following occurrence ranges are depicted:</p><p>The occurrence ranges set are:</p><ul><li>A: 0-5</li><li>B: 5-10</li><li>C: 10-20</li></ul><p>Number of occurrences are recorded using the ranges as follows:</p><figure><table><thead><tr><th>Example</th><th>Number of occurrences reported by the SDK</th><th>Associated range</th><th>Number of occurrences reported</th></tr></thead><tbody><tr><td>1</td><td>5</td><td>A </td><td>3</td></tr><tr><td>2</td><td>6</td><td>B</td><td>8</td></tr><tr><td>3</td><td>10</td><td>B</td><td>8</td></tr><tr><td>4</td><td>125</td><td>C</td><td>15</td></tr></tbody></table></figure></td></tr><tr><td>Limitation</td><td>A given in-app event can be associated once with this component.</td></tr></tbody></table>

</Accordion>

<div id="revenue-component" />

<Accordion title="Revenue component">

<table><tbody><tr><td colspan="2"><img alt="ConversionStudioRevenue.png" src="https://files.readme.io/202c258f11cd93248f8aceff410126efc02ced11e9a9b159bac8ba81cbc8d9fe-4406075612305.png"/></td></tr><tr><td>Mandatory</td><td>No</td></tr><tr><td>Multiple-use permitted</td><td>Yes, if using the in-app event revenue source. </td></tr><tr><td>Setting options</td><td><p>Overall revenue from all revenue streams can be recorded using a single event or by individual streams by selecting specific in-app events that generate revenue. </p><p>The following revenue source options are supported: </p><ul><li><strong>Overall revenue</strong><ul><li>Overall revenue which includes revenue from all in-app events and ad revenue (when relevant), can be measured using a single <code>af_skad_revenue</code>  event. Ensure that the <code>af_skad_revenue</code> event name is correctly mapped for partners.</li><li>The component can be included once. </li></ul></li><li><strong>In-app event</strong><ul><li>Measuring different revenue streams can be done by selecting specific in-app events in the SKAN schema. After adding revenue measurement, select "in-app event" in the revenue source selection. Make sure all the events are mapped properly to ad networks.<br/>Note: When measuring revenue from specific in-app events,  <code>af_skad_revenue</code> shouldn't be mapped.</li><li>The component can be used multiple times.</li><li><mark>If you report revenue by postback to ad networks, verify that your in-app event postback mappings include the in-app revenue events set by you.</mark></li></ul></li></ul></td></tr><tr><td>Ranges</td><td><p>To measure revenue, you must create revenue ranges. When revenue is reported, SKAN associates the reported revenue with the appropriate range.</p><p><strong>Characteristics</strong></p><ul><li>Each range contains a revenue range consisting of a <strong>from</strong> value and a <strong>to</strong> value. The lower value isn't included in the range; however, the upper value is included. For example, 5–10 means greater than 5 up to and including 10. </li><li>The range with the lowest value always starts at 0 (but doesn't include 0 itself). </li><li>You can create as many ranges as you wish, but keep in mind that each range affects your conversion value capacity.</li><li>Ranges must be sequential (without gaps between them.)</li><li>Amounts are in USD</li><li>If you run campaigns on Meta ads, you must have 4 or more ranges. </li><li>Range values can have up to 4 digits after the decimal point.</li></ul><p><strong>Recording revenue using ranges</strong></p><ul><li>When revenue is reported, SKAN associates the revenue with the appropriate range. The revenue recorded equals the average value of the range. </li><li>If the revenue reported exceeds the average value of the highest-value range, the revenue is associated with the highest-value range. <strong>Note</strong>! <mark>The revenue recorded is the average value of this range.</mark> In other words, the actual revenue amount is disregarded.</li><li>In raw data, the revenue recorded and the associated range are available. </li></ul><p><strong>Example:</strong></p><p>In the image, the following revenue ranges are depicted:</p><ul><li>A: 0-5</li><li>B: 5-10</li><li>C: 10-20</li></ul><p>Revenue is recorded using the ranges as follows: </p><figure><table><thead><tr><th>Example</th><th>Revenue reported by the SDK</th><th>Associated range</th><th>Revenue recorded</th></tr></thead><tbody><tr><td>1</td><td>5</td><td>A </td><td>$2.5</td></tr><tr><td>2</td><td>6</td><td>B</td><td>$7.5</td></tr><tr><td>3</td><td>10</td><td>B</td><td>$7.5</td></tr><tr><td>4</td><td>125</td><td>C</td><td>$15</td></tr></tbody></table></figure></td></tr></tbody></table>

</Accordion>

<div id="funnel-component" />

<Accordion title="Funnel component">

<table><tbody><tr><td colspan="2"><img alt="ConversionValueFunnel.png" src="https://files.readme.io/b43b5db0cee11c9addd50fb56af1ac6d3221e1956e2ee3c4c21a6940e9dfe61b-4406051997969.png"/> </td></tr><tr><td>Mandatory</td><td>No</td></tr><tr><td>Multiple-use permitted</td><td>No</td></tr><tr><td>Setting options</td><td>List a sequential set of events in a funnel. Since the occurrence of a single event is treated as the occurrence of all preceding events, the order in which you list the events is highly important, as illustrated in the example that follows.</td></tr><tr><td>Example</td><td><p>A funnel contains the events a, f, b, k, and z, as illustrated in the preceding image.</p><figure><table><thead><tr><th>Example</th><th>Event performed</th><th>Events recorded</th></tr></thead><tbody><tr><td>1</td><td>a</td><td>a</td></tr><tr><td>2</td><td>b</td><td>a, f, b</td></tr><tr><td>3</td><td>z</td><td>a, f, b, k, z</td></tr></tbody></table></figure></td></tr></tbody></table>

</Accordion>

<div id="priority-measurement-component" />

<Accordion title="Priority measurement component">

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
   [![Priority1.png](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)
5. Select a measurement component from:
   * Revenue
   * In-app event
6. Complete the fields according to the user interface.
   * Consider that a priority can consist of revenue, in-app event, or both.
   * Range values of event occurrences and revenue can be of ascending (increasing) or descending (decreasing) order but must be continuous. For example, the following ranges are continuous: 1-5, 5-8, 8-10, and so on. A given range can be used more than once (repeated) if the second time it's used is part of a unique combination and is the same range as the last priority with a range. For example, 1-5, 1-5 + add to cart.  
     **Example of increasing and decreasing revenue**

| Event | Occurrence | Revenue |
| --- | --- | --- |
| P1 event\_a | 2-3 | $5 - $50 |
| P2 event\_a | 2-3 | $0 - $5 |
| P3 event\_a | 1-2 | $5 - $50 |
| P4 event\_a | 1-2 | $0 - $5 |
| P5 event\_a | 0-1 | $5 - $50 |
| P6 event\_a | 0-1 | $0 - $5 |

7. Click **Validate.**  
   The **Priority is valid message** displays. If this isn't the case, correct your priority before you continue.
8. Do one of the following:
   * To add a priority, click **+ Add priority.** The existing priority 1 is shifted down and becomes priority 2. Complete the priority settings as previously described.
   * To delete a priority, click **…** > **Delete.**
   * To change the priority level, click **Options** (**⋮**), and select either **Change order** or **Make lowest priority**.
   * To duplicate a priority, click **Options** (**⋮**), and select **Duplicate**.
   * Click **Save**, to complete setting priorities.

</Accordion>

<div id="lock-window" />

<Accordion title="Lock window">

**Note**: Lock window is only relevant for SKAN 4 and above.

<table><tbody><tr><td colspan="2"><img alt="lock_window.png" src="https://files.readme.io/d9db51890a5d589b7343ed389d55af0c4181b249a2c5e970b9a5e1244c489abc-14240675527057.png"/></td></tr><tr><td>Use</td><td>SKAN windows by default measure user value for specific times post-install. You can lock the windows early and have postbacks sent with all available data. To do so, set the conditions for when to lock the windows.</td></tr><tr><td>Mandatory</td><td>No</td></tr><tr><td>Multiple-use permitted</td><td>Yes, one for each SKAN window</td></tr><tr><td>Condition options</td><td><p>The Lock window consists of two options for locking the SKAN window early:</p><ul><li>Time: You must then choose a time post-install (before the default time) to lock the window. <strong>Note</strong>: The lock based on time doesn't take effect unless the user opens the app.</li><li>High coarse value: As soon as the high coarse value is reached, the window closes.</li></ul></td></tr><tr><td>Impact of using lock window</td><td>SKAN postbacks don't contain information on when a window closes, so the lock window status isn't taken into consideration when estimating install time. Therefore, locking the window early could affect the precision of install time estimates.</td></tr></tbody></table>

</Accordion>

<div id="activity-window" />

<Accordion title="Activity window">

**Note**:

* Activity window is only relevant for SKAN 3 and below (meaning Custom and fixed modes).
* If you're using SKAN 4+, but user devices or ad networks don't support SKAN 4 yet, the Activity Window is 48 hours.

<table><tbody><tr><td colspan="2"><img alt="flex_activity_window.jpg" src="https://files.readme.io/ac51126eda5b9d319ccdd90adb936baaa512dcd844ad191cac6c20a45cd4aae8-6390396808081.jpg"/></td></tr><tr><td>Mandatory</td><td>Yes </td></tr><tr><td>Multiple-use permitted</td><td>No</td></tr><tr><td>Time characteristics</td><td><ul><li>The timer has a fixed duration, set by you, and runs in parallel to the iOS timer.</li><li>In contrast, the iOS timer has an initial duration of 24 hours. Each time the conversion value increases, the timer is reset.</li><li>Default duration 24 hours.</li><li>Measurement stops when either timer reaches 0. </li></ul></td></tr><tr><td>Timer duration</td><td><ul><li>Range: 12-72 hours. For more options, see <strong>Flexible measurement</strong> in this table.  </li><li>When the timer ends, AppsFlyer stops measuring.</li><li>If the timer duration is more than 24 hours, the user must be active in the app at least once per interval. If not, measurement can end prematurely because AppsFlyer can't prevent the iOS timer from reaching 0; meaning iOS ends measurement. </li></ul></td></tr><tr><td>Interval</td><td><p>12 or 24 hours. Intervals affect the precision of the last-active time range and install time. For more options, see <strong>Flexible measurement</strong> in this table. </p><p>The last-active time range is available in raw data reports in the <em>min_install_time</em> and <em>max_install_time</em> columns and is used to determine the install time as described in this section.</p><p>Example:</p><ul><li>The timer duration is set to 48 hours</li><li>The user was last active during hour 40</li><li>Depending on the interval setting, the last-active time range is: <br/> <ul><li>12-hour interval: 36–48h</li><li>24-hour interval: 24–48h</li></ul></li></ul></td></tr><tr><td>Install time</td><td><p>Install time is derived as follows:</p><p><code>Install time = Postback arrival time - [Average last-active range] - [iOS postback delay]</code></p><ul><li><code>Postback arrival time</code>:  Time the iOS postback was first received directly from the device; usually by the ad network. </li><li><code>Average last-active range</code> considers the CV and is calculated as follows:<ul><li>If CV = 0  last-active range is assumed to be 0. </li><li>If CV &gt; 1 or CV = null: Using the min_install_time and max_install time these are set based on the interval and the last time the user was seen active in the app.  For example, If the interval is 12, as the user was last seen 25 hours post-install, the result is [24 + 36] / 2 = 30. </li></ul></li><li><code>iOS postback delay</code>: [24 + 48 ] / 2 = 36. Consider that the iOS timer ends 24 hours after the last change to the CV and the postback is sent 0–24 hours after that. <strong>36 hours is a constant</strong>. </li></ul></td></tr><tr><td>Setting options</td><td><p>The Activity window consists of two settings duration and intervals. </p><ul><li>Duration: 24–72 hours with intervals of 24 hours. Maximum 3 intervals.</li><li>Duration: 12–72 hours with intervals of 12 hours. Maximum 6 intervals.</li></ul></td></tr><tr><td>Impact of changing the activity window duration</td><td><ul><li>The postback is sent 0-24 hours after the iOS timer expires. </li><li>Initially, the iOS timer is fixed to end after 24 hours. </li><li>If you set the activity window to more than 24 hours, the user must be active at least once per interval to assure that the iOS timer doesn't expire.</li></ul></td></tr><tr><td><p>Considerations relating to ad networks</p></td><td><ul><li>The default timer duration is 24 hours.</li><li>You can set a different duration, but before doing so, verify with your ad network partners if they support a period that differs from the default. </li><li><span>When using the 24-hour window, you can enhance your metrics by splitting the 24-hour period into 2 intervals, each of 12 hours. By doing so, you'll know if the user continued using the app after the first 12 hours. </span></li></ul></td></tr><tr><td>Example range capacity requirements</td><td>The image in this section shows a timer of 60 hours with a 12-hour interval. </td></tr><tr><td>Flexible activity window options</td><td><p>Flexible measurement lets you set a longer activity window and having hourly granularity. Similarly so for the intervals setting. The settings have the following characteristics:</p><ul><li>Activity window:<ul><li>Range: 12-1512 hours (63 days)  </li><li>Granularity: 1 hour</li></ul></li><li>Intervals:<ul><li>Range: <span>Minimum 1 hour and any other multipliers of the activity window</span></li><li>Granularity 1 hour</li></ul></li></ul><p>Consideration: The ratio of the activity window to intervals must be a whole number.</p><p>Best practice: Don't set the interval to more than 24 hours, as this decreases install time estimation precision.</p></td></tr></tbody></table>

</Accordion>

## Additional information

<div id="view-cv-mapping" />

<Accordion title="View CV mapping">

* View the events mapped to a CV by selecting the CV. The mapped events display below the table.
* Download the CV mapping table as a CSV file from the **Conversion value summary** pane. Click **Download mapping file.**
* Get the CV mapping using the [SKAN CV schema API for advertisers](/docs/skan-cv-schema-api-for-advertisers).

![SKAN_download_mapping.png](https://files.readme.io/62dc60da0001c0eccc96791f3f3320f8ea0bc24db3977af4390643c5a95a5ad3-46095838352401.png)

#### CSV mapping file columns

| Column | Description |
| --- | --- |
| app\_id |  |
| conversion\_value | CV value:<ul><li>0-63</li><li>Low, medium, or high</li></ul> |
| event\_name |  |
| min\_event\_counter | The lower bound of the event counter range |
| max\_event\_counter | <ul><li>The upper bound of the event counter range.</li><li>In reports generated by AppsFlyer, the number of events is calculated using the following formula: Roundup ([min\_event\_counter + max\_event\_counter]) / 2</li></ul> |
| min\_event\_revenue | The lower bound of the event revenue range in USD |
| max\_event\_revenue | <ul><li>The upper bound of the event revenue range in USD</li><li>In reports generated by AppsFlyer, the revenue is calculated using the following formula: ([min\_event\_revenue + max\_event\_revenue]) / 2)</li></ul> |
| min\_time\_post\_install | The lower bound, hours post-install, indicating when the user was last active in the app. |
| max\_time\_post\_install | The upper bound, hours post-install, indicating when the user was last active in the app. |
| last\_config\_change | The date you saved the configuration in the SKAN Conversion Studio. |

</Accordion>

<div id="conversion-value-capacity-formula" />

<Accordion title="Conversion value capacity formula">

As previously explained, the maximum number of available conversion values is 64. The following formula calculates how many of the available conversion values are used by the mode.

```
(activity time duration in hours / interval size in hours) * 
(number of revenue ranges + 1 ) * 
(number of in-app event ranges + 1 ) * 
(number of steps in a funnel + 1)
```

Adjust the formula to include all measurement components

</Accordion>

<div id="maximized-custom-cv-examples" />

<Accordion title="Maximized Custom CV examples">

#### Example 1

| Component | Description |
| --- | --- |
| Activity window | <ul><li>Duration: 24 hours</li><li>Interval: 24 hours being 1 interval</li></ul> |
| Revenue | <ul><li>Revenue is reported using a single in-app event (overall)</li><li>Revenue ranges: 15</li></ul> |
| In-app | None |
| Funnel | 3 in-app events |

#### Example 2

| Component | Description |
| --- | --- |
| Activity window | <ul><li>Duration: 24 hours</li><li>Interval: 12 hours being 2 intervals</li></ul> |
| Revenue | <ul><li>Revenue is reported allocated by type using 2 different in-app events</li><li>Revenue ranges: 3 (per in-app event)</li></ul> |
| In-app set for conversion | 1 in-app event to measure conversion; each in-app requires 1 range |
| Funnel | None |

#### Example 3

| Component | Description |
| --- | --- |
| Activity window | <ul><li>Duration: 24 hours</li><li>Interval: 24 hours being 1 interval</li></ul> |
| Revenue | <ul><li>Revenue is reported using a single in-app event (overall)</li><li>Revenue ranges: 3</li></ul> |
| In-app set for engagement | <ul><li>2 in-app events to measure engagement occurrences</li><li>Occurrence ranges: 3 per in-app event</li></ul> |
| Funnel | None |

#### Example 4

| Component | Description |
| --- | --- |
| Activity window | <ul><li>Duration: 48 hours</li><li>Interval: 12 hours being 4 intervals</li></ul> |
| Revenue | <ul><li>Revenue is reported using a single in-app event (overall)</li><li>Revenue ranges: 7</li></ul> |
| In-app set for conversion | 1 in-app event to measure conversion; requires 1 range |
| Funnel | None |

</Accordion>

<div id="priority-measurement-detailed-example" />

<Accordion title="Priority measurement detailed example">

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

<table><thead><tr><th>Priority #</th><th>Revenue range</th><th>In-app event</th></tr></thead><tbody><tr><td>1 [Highest priority]</td><td>$5-$10</td><td>send_recommendation</td></tr><tr><td>2</td><td>$5-$10</td><td>--</td></tr><tr><td>3</td><td>$0-$5</td><td>send_recommendation</td></tr><tr><td>4</td><td>$0-$5</td><td>--</td></tr><tr><td>5</td><td>--</td><td>send_recommendation<br/>add_to_cart</td></tr><tr><td>6</td><td>--</td><td>send_recommendation</td></tr><tr><td>7 [Lowest priority]</td><td>--</td><td>add_to_cart</td></tr><tr><td colspan="3">-- No value set</td></tr></tbody></table>

The table that follows contains user journey scenarios. Each scenario contains the list of actions performed by the user during their journey and the priority determined by AppsFlyer.

In the table:

* Multiple actions are separated using **>**
* The value in brackets (), is the priority determined by AppsFlyer set after the user completes the action. Using the priority AppsFlyer update the CV in the app.

#### User journey scenarios

| User journey scenario | User actions and priority |
| --- | --- |
| A | add\_to cart (7) |
| B | add\_to\_cart (7) > send\_recommendation (5) |
| C | Purchase $3 (4) |
| D | Purchase $6 (2) |
| E | Purchases $6 (2) > send\_recommendation (1) |

</Accordion>

<div id="fixed-mode-examples" />

<Accordion title="[Legacy] Fixed mode examples">

> 📘 **Note**
>
> Fixed modes are unavailable for new apps starting from 23/06/2024. All functionalities are supported in the Custom and SKAN4.

#### Example A: Revenue measurement

| Factor | Remarks |
| --- | --- |
| Scenario | <ul><li>20 users install the app and perform the following purchases:<ul><li>9 users, each make a purchase of $10</li><li>5 users, each make a purchase of $5</li><li>1 user makes a purchase of $1, then $3, then $5, and finally $1. In total $10.</li></ul></li><li>Cost data provided by API from the ad network: $30</li></ul> |
| SKAN configuration | <ul><li>Select measurement type: revenue</li><li>Set conversion factor: 1 conversion unit = $1</li><li>Designated conversion event: In the SDK, you must send revenue using the *af\_revenue* parameter.</li></ul> |
| Selected metrics | Revenue related metrics available<ul><li>Installs: 20</li><li>Revenue: $125</li><li>Conversions:15</li><li>ARPU: $6.25</li><li>ROI: 316%</li></ul> |
| Number of raw data rows per report | [Raw data reports are available via Data Locker](/docs/skan-raw-data-reports)<ul><li>Device postbacks: 20 rows</li><li>Installs: 20 rows</li><li>In-app events: 15 rows. Note! The user making multiple purchases is represented by a single row of $10.</li></ul> |
| Developer considerations | Events carrying revenue are recognized |

#### Example B: Conversion measurement

<table><thead><tr><th>Factor</th><th>Remarks</th></tr></thead><tbody><tr><td>Example</td><td><ul><li>5 users (A-E) install the app</li><li>They perform 0-3 different in-app events, as depicted in the table</li><li>Cost data provided by API from the ad network: $30</li></ul><h4><span id="inapp-events-performed-by-users"></span>In-app events performed by users</h4><figure><table><thead><tr><th> </th><th>in-app-1</th><th>in-app-2</th><th>in-app-3</th></tr></thead><tbody><tr><td>User A</td><td>Performed</td><td>Performed</td><td>-</td></tr><tr><td>User B</td><td>Performed</td><td>-</td><td>Performed</td></tr><tr><td>User C</td><td>Performed</td><td>Performed</td><td>-</td></tr><tr><td>User D</td><td>Performed</td><td>Performed</td><td>-</td></tr><tr><td>User E</td><td>-</td><td>-</td><td>-</td></tr></tbody></table></figure></td></tr><tr><td>SKAdNetwork Attribution Configuration</td><td><p>Select measurement type: Conversion</p><ul><li>Select in-app events: in-app-1, in-app-2, in-app-3</li><li>In the SKAdNetwork <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">dashboard</a>, you select one of the events to calculate the converted users metric. You can change the selected event as needed. </li></ul></td></tr><tr><td>Selected metrics</td><td><h4><span id="inapp-related-metrics-available"></span>In-app related metrics available</h4><figure><table><thead><tr><th>Metric </th><th>App </th><th>in-app-1</th><th>in-app -2</th><th>in-app- 3</th></tr></thead><tbody><tr><td>Installs</td><td>5</td><td> </td><td> </td><td> </td></tr><tr><td>Conversions</td><td>4</td><td> </td><td> </td><td> </td></tr><tr><td>Unique users</td><td> </td><td>4</td><td>3</td><td>1</td></tr><tr><td>eCPA</td><td>$ 7.5</td><td> </td><td> </td><td> </td></tr></tbody></table></figure><p><strong>Note! </strong>Because the designated Conversion Event is in-app 1, the value 4 is used to calculate app-level metrics and for in-app-1 metrics. </p></td></tr><tr><td> </td><td><p><a href="./skan-raw-data-reports">Raw data reports are available via Data Locker</a></p><ul><li>Device postbacks:5 rows</li><li>Installs: 5 rows</li><li>In-app events: 8 rows</li></ul></td></tr><tr><td>Developer considerations</td><td><ul><li>Make sure you send in-app events users perform.</li><li>SKAdNetwork Solution disregards event values (except in relation to revenue measurement.</li></ul></td></tr></tbody></table>

#### Example C: Engagement measurement

| Factor | Remarks |
| --- | --- |
| Example | 5 users install the app and open the app the number of times listed in the table.<br /><br />**<span id="app-opens"></span>App opens**<table><thead><tr><th></th><th>Number of times the event is performed</th></tr></thead><tbody><tr><td>User A</td><td>63</td></tr><tr><td>User B</td><td>10</td></tr><tr><td>User C</td><td>5</td></tr><tr><td>User D</td><td>1</td></tr><tr><td>User E</td><td>-</td></tr></tbody></table> |
|  | Number of times the event is performed |
| User A | 63 |
| User B | 10 |
| User C | 5 |
| User D | 1 |
| User E | - |
| SKAdNetwork Attribution Configuration | <ul><li>Select measurement type: Engagement</li><li>Designated conversion event: af\_app\_opened Note! You can use any event available.</li></ul> |
| Selected metrics | Sample metrics available<ul><li>Installs: 5</li><li>Conversions: 4</li><li>Sessions: 79</li></ul> |
| Number of raw data rows per report | [Raw data reports are available via Data Locker](/docs/skan-raw-data-reports)<ul><li>Device postbacks:5 rows</li><li>Installs: 5 rows</li><li>In-app events: 4 rows; a row is equivalent to a single session<br />Note: In this example, there are four different rows as four different unique users made this event.<br />To count and calculate the number of actual event occurrences, the rows will have a minimum and a maximum event count attached to them.</li></ul> |
| Developer considerations | On each occasion the user performs the selected engagement event: send the in-app event. SKAdNetwork counts the number of times you send the event. |

<div id="skan-conversion-studio-api" />

<Accordion title="SKAN Conversion Studio API">

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

</Accordion>

<div id="skan-schema-analysis" />

<Accordion title="SKAN schema analysis">

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

</Accordion>

</Accordion>

## Additional procedures

<div id="change-skan-measurement-mode" />

<Accordion title="Change SKAN measurement mode">

Consider:

* Once you start using SKAN 4 measurement mode, it isn't recommended to change back to an earlier mode.
* When you make settings change, they begin to take effect from 00:00 AM UTC and a transition period begins. During this period we decode the conversion value using the most recently selected settings. However, a postback arriving now relates to an install that occurred sometime in the past.
* The number of installs reported is not related to the settings change and is accurate.

</Accordion>

<div id="disable-skan-measurement" />

<Accordion title="Disable SKAN measurement">

To turn off SKAdNetwork measurement:

1. In AppsFlyer, go to **Settings** > **SKAN Conversion Studio.**
2. Click **⋮** .
3. Turn off **SKAdNetwork measurement.**  
   Among other things, the SDK stops calling SKAN functions like *registerAppForAdNetworkAttribution*, *updateConversionValue.*
4. Click **Save changes.**

</Accordion>

<div id="report-events-by-servertoserver-api" />

<Accordion title="Report events by server-to-server API">

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

</Accordion>

<div id="add-ssot-to-fixed-mode-measurements" />

<Accordion title="Add SSOT to fixed mode measurements">

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

<div id="conversion-value-decrease" />

<Accordion title="Conversion value decrease">

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

| CV | Revenue | In-app event |
| --- | --- | --- |
| 3 | $20 - $30 |  |
| 2 | $10 - $20 | af\_add\_to\_cart |
| 1 | $0 - $10 |  |
| 0 | NA | install |

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

| CV | In-app event |
| --- | --- |
| 3 | af\_purchase |
| 2 | af\_add\_to\_cart |
| 1 | session |
| 0 | install |

**Example**

User did a session event - you will see an increase to CV 1  
User then made a purchase event - you will see an increase to CV 3  
User then did another session event - it will remain on CV 3

</Accordion>

<div id="support-anonymized-users" />

<Accordion title="Support Anonymized Users">

Enabling the **Support anonymized users** toggle ensures that SKAN conversion values are accurately updated for [anonymized users](/docs/apply-privacy-preserving-sdk-methods#anonymize-user-information), while still protecting their privacy.

> 📘 **Important!**
>
> This feature is relevant only for apps that call the [anonymize user method](/docs/apply-privacy-preserving-sdk-methods#anonymize-user-information) to remove and hash all user-identifying information. To ensure accurate reporting by SKAN, these apps must activate the **Support anonymized users** toggle.

Why is it needed?  
SKAN uses identifiers to update conversion values based on post-install activity. When an app calls the **anonymize user method** after calling the start method, the system may not be able to link some post-install events to the original install, leading to inaccurate conversion value updates.  
By activating the **Support anonymized users** toggle, the system creates hashed identifiers for all users upon installation. This allows the app to properly link user activity to the original install, even if the user becomes anonymized at a later point, ensuring accurate reporting.

</Accordion>

</Accordion>

<div id="ssot-mapping-patterns" />

<Accordion title="SSOT mapping patterns">

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

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Specifications and limitations">

| Spec | Remarks |
| --- | --- |
| Agencies | Agencies have [limited access to advertisers' SKAN Conversion Studio](/appsflyer-partners/docs/getting-started-agency-onboarding#access-to-skan-conversion-studio). |
| Coarse values | <ul><li>Up to 10 measurement components.</li><li>When using more than one measurement, all events must happen for course value to be encoded.</li></ul> |
| Organic in-app events | In SKAN 4, Custom and Decode modes, organic metrics for in-app events and overall revenue aren't available. |
| Ambiguous data | After changing the SKAN configuration for the next 48-72 hours, data in the dashboard and raw data reports is ambiguous. Due to iOS timer issues, it is uncertain if the configuration used to decode the postbacks matches the configuration used to encode them before. |
| Geo restrictions | Users whose access is limited to specific media sources and geos may not be able to see or access the SKAN Conversion Studio. |

</Accordion>

<div data-zendesk-anchors="01H7Z08MFDASBCBJD18QTXYSXK=skan-conversion-studio-basics 01H7Z08MFDX3VYJTSWXQ5HQ7BZ=measurement-principles-and-definitions 01H7Z08MFDWRGVNXB62Z6CT1G7=s2s-principles 01H7Z08MFDB76C6Z5SSXHFT71P=setting-up-conversion-values-in-skan-conversion-studio 01H7Z08MFDEAYHJAG9XA2TGBWV=important 01H7Z08MFD7VY1QP85W0YPK8RC=skan-4 01H7Z08MFD3SWVZK68K45NYDP8=custom 01H7Z08MFDZ1EKDQNZWGF7DHK9=fixed-modes h_01J14HX28C9TFDP0MDRYWFV6Q3=note 01H7Z08MFDAYVJKJBT08R82N26=fixed-mode-measurement 01H7Z08MFDCJGZGQR2JR4WQVHR=decode 01H7Z08MFDFE345QWHF77RGTD7=measurement-components 01H7Z08MFE5G01NGY5EFTAW93M=single-source-of-truth 01H7Z08MFERDJHSD8NT5KN7DKN=inapp-event-component 01H7Z08MFETMGAE67X499V4092=revenue-component 01H7Z08MFEQG2HRJBWBYFTW3ZK=funnel-component 01H7Z08MFE22J8DDBDNJ18KBEJ=priority-measurement-component 01H7Z08MFES844SS08HS17Y29R=lock-window 01H7Z08MFE61QCC0MZW5RJ910B=activity-window 01H7Z08MFET64PSAVMREQ4HP4S=additional-information 01H7Z08MFEKP9WNGJD2GBVKB0P=view-cv-mapping 01H7Z08MFETCB428W1TXTH2HJ8=csv-mapping-file-columns 01H7Z08MFE5CBQK024CF8FARJ9=conversion-value-capacity-formula 01H7Z08MFETZVQSNWX639E56SK=maximized-custom-cv-examples 01H7Z08MFEXME7RV67XTZRDWJE=example-1 01H7Z08MFEHRF4656X5AR301D8=example-2 01H7Z08MFEK0725CN35TP3MPYT=example-3 01H7Z08MFES7W3EF2JJ8B75K99=example-4 01H7Z08MFF2JXA0BFNKCW3ZCZ7=priority-measurement-detailed-example 01H7Z08MFFXAAC37MBV0ES6ADQ=measurement-priorities-setting-example 01H7Z08MFFJ9TQMH0Q93B7N1A8=user-journey-scenarios 01H7Z08MFFNBXECB8A5Y0KH9C8=fixed-mode-examples h_01JJH6WZY2QMKAR1C7B5JTMMKE=note-1 01H7Z08MFFVKZN3Y2R1ZEVEW4D=example-a-revenue-measurement 01H7Z08MFFNBA5786R5XZDA5FG=example-b-conversion-measurement 01H7Z08MFFA7C6HWQPADZXQQNC=inapp-events-performed-by-users 01H7Z08MFF1PEE91J5CJN1GC7V=inapp-related-metrics-available 01H7Z08MFF8V718C23PQ2NG3C3=example-c-engagement-measurement 01H7Z08MFF4PRHSR8NCJ1Q78WM=app-opens 01H7Z08MFFVS6MYC9EB3KP0H2Y=skan-conversion-studio-api h_01K15P5NJ4CGSH4YR9JXD93PD9=skan-schema-analysis h_01K15P7QQSDHNY1ZN3FC37XTHP=conversion-values-tab 01K15PMAQGDZ4SFKEERXVRR0C2=revenue-tab 01K15PZK56TVQ6WHGYCA54AA4Q=events-tab 01H7Z08MFFPZ4GKM5GFMAE2HDJ=additional-procedures 01H7Z08MFFPKCX5TFQQTMYJEGW=change-skan-measurement-mode 01H7Z08MFF78F9NMWJATYE2YFE=disable-skan-measurement 01H7Z08MFFD4T3D71A6R9K83A3=report-events-by-servertoserver-api 01H7Z08MFFFAEW6NP0YAX773B3=add-ssot-to-fixed-mode-measurements h_01JJH6WZY2R2H1F9ZBGTR0FDNM=note-2 h_01HKVT9N2KFJQGCWVMGP59YWRH=conversion-value-decrease h_01HM3C8BEG5Z7ZRY12MF3Q4W4K=examples 01JCWF4HM4KKB0WC8MN00SV4XK=support-anonymized-users 01JCWFY9RZ7JSC63TVBTPRCYHH=important-1 h_01JRFAN7GT7K18ADDAYGVQ4GGT=ssot-mapping-patterns h_01JRFB0793MK8H75T7CGTNPDCK=half-and-half h_01JRFB1B9A44CRYVBRTK4CRQGP=pairing h_01JRFBAGEZP2GT3XZW4RT255M3=how-to-configure-mapping-patterns h_01JRFBBYER8QMW5XMBBCWFGDP1=faq 01H7Z08MFFG9EQFVEKN3AXE9DD=specifications-and-limitations" />
