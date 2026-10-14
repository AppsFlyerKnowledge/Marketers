---
title: Implement validation rules to prevent fraud
excerpt: >-
  Validation rules add a custom layer of protection against incorrectly targeted
  campaigns and fraud. The rules enable app owners to control which installs and
  in-app event attributions get blocked, or attributed to the last valid source.
metadata:
  keywords:
    - Advertisers
    - validation rule
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2017-09-14T14:43:46Z'
  edited_at: '2026-09-09T07:57:33Z'
  id: 115004703926
  locale: en-us
  section: Protect your traffic
  section_id: 6551015912465
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115004703926-Implement-validation-rules-to-prevent-fraud
---
![5906_animation-750x330__1_.gif](https://files.readme.io/2a5fbee83bdbc342c744f8079b743f06cb3205697bd9caa183593c411ae03d08-360014483338.gif)

## Overview

* Validation rules are defined in the rule builder using customized conditions and logic that filter and select which app installs or in-app event attributions to keep or block.
* Rules are based on a variety of parameters for multiple use cases, including:
  * Untargeted installs for your campaign (wrong geo, OS version, etc.)
  * Installs that do not meet the insertion order signed with the ad network
  * Hijacked installs by fraudulent networks
  * Fake installs or in-app events sent from bots, emulators, or device farms
* Rules defined for in-app events only take effect on in-app events associated with installs that were not previously blocked.
* Rules that include an ad network are visible to that ad network's personnel (but they cannot see other ad networks included in the rule). This is in the interest of transparency, and to help ad networks better understand the performance of the traffic they provide.
* The rules run in realtime and take immediate action. Learn more in the [outcome](/docs/implement-validation-rules-to-prevent-fraud#outcomes) section.
* Tagged mode lets you test validation rules against live traffic before blocking attribution. When a rule is set to Tagged, AppsFlyer flags matching installs and in-app events for reporting and analysis, but attribution isn’t affected. Use Tagged mode to monitor rule behavior, identify possible false positives, and confirm the rule’s impact before changing the rule status to Implemented. See more in [VR tagged mode](/docs/implement-validation-rules-to-prevent-fraud#view-validation-rule-impact).
* Additional validation rule options are available to [Protect360](/docs/protect360-anti-fraud-guide) customers, on top of the automatic Protect360 fraud blocking and detection. These conditions are known to help in the detection of various install-hijacking, fake install, and fake in-app event fraud types.  
  **Note**: Validation Rules only validate installs/in-app events that were not identified as fraud by Protect360.

<Accordion title="Outcomes">

* For installs: Validation rules, depending on the selected action, either block the attribution and correct to the last valid media source, or block the attribution completely.
* For in-app events: Validation rules block the attribution of the in-app event.
* See the following table showing the validation rule block type outcomes.

<table><thead><tr><th> </th><th>Block type</th><th>Description</th><th>Where install data can be viewed</th><th>In-app events that follow</th></tr></thead><tbody><tr><td rowspan="2"><strong>Installs</strong></td><td>Block attribution and correct to last valid media source</td><td><ul><li><span>Selected when you consider the install real, but your conditions determine which sources should or shouldn’t be attributed for it.</span></li><li><span>Attribution is corrected, and the install is attributed to the last valid media source.</span></li><li><span>If no valid media source is identified, the install is marked as organic.</span></li></ul></td><td><ul><li>AppsFlyer dashboards and raw data reports as a regular install (attributed to the last valid media source)</li><li>With Protect360 Premium plan:<ul><li><a href="./protect360-dashboard#installs-dashboard">Protect 360 installs dashboard</a></li><li>Protect360 installs raw data report (<span>with the blocked media source)</span></li></ul></li><li>Without Protect360 Premium plan:<ul><li>Protect360 installs raw data report (<span>with the blocked media source)</span></li></ul></li></ul></td><td><ul><li>Has the same corrected attribution as the install</li><li>Data available with Protect360 Premium plan:<ul><li>With corrected attribution in AppsFlyer dashboards and reports as a regular IAE</li><li>With blocked media source in the Protect360 IAE dashboard and Protect360 blocked IAE raw data report</li></ul></li></ul></td></tr><tr><td>Mark installs as invalid and don't attribute them</td><td><ul><li><span>Selected when installs that are invalid based on the rule’s conditions are considered fake.</span></li><li><span>The install is not attributed at all (neither as non-organic nor organic)</span></li></ul></td><td><ul><li>With Protect360 Premium plan:<ul><li><a href="./protect360-dashboard#installs-dashboard">Protect 360 installs dashboard</a></li><li>Protect360 installs raw data report (<span>with the blocked media source)</span></li></ul></li><li>Without Protect360 Premium plan:<ul><li>Protect360 installs raw data report (<span>with the blocked media source)</span></li></ul></li></ul></td><td><ul><li><span>Blocked</span></li><li><span>Data available with Protect360 Premium plan in Protect360 IAE dashboard and blocked IAE raw data report</span></li></ul></td></tr><tr><td rowspan="2"><strong>In-app events</strong></td><td>Block attribution </td><td><ul><li><span>Selected when in-app events that are invalid based on the rule’s conditions are considered fake.</span></li></ul></td><td><ul><li><span>With Protect360 Premium plan:</span><ul><li><a href="./protect360-dashboard#in-app-events-dashboard">Protect360 IAE dashboard</a></li><li>Protect360 in-app events raw data report</li></ul></li><li>Without Protect360 Premium plan: N/A</li></ul></td><td><ul><li><span>Data available with Protect360 Premium plan in Protect360 </span><a href="./protect360-dashboard#in-app-events-dashboard"><span>IAE dashboard</span></a><span> and blocked in-app events raw data report</span></li></ul></td></tr><tr><td>Remove from AppsFlyer entirely</td><td><ul><li><span>Recommended for use when there are in-app events that you don't need any data for.</span></li><li><span>AppsFlyer does not record these events at all. </span></li></ul></td><td><span></span></td><td><span></span></td></tr></tbody></table>

* Ad networks and agencies can only view data if the advertiser gives them the required [permissions](/docs/raw-data-reporting-overview#protect360-fraud-and-validation-rules).
* When an install attribution is blocked or attributed to a valid media source in real-time, a rejected postback is instantly sent to the blocked ad network, to streamline your reconciliation flow. When attribution is blocked and corrected to the last valid media source, a postback is also sent to the last valid ad network.
* When an in-app event attribution is blocked, a rejection postback is instantly sent to the blocked ad network.  
  **Note**:
  * A postback is only sent if the ad network set to receive it is integrated with AppsFlyer to receive postbacks.
  * Postbacks and rejected postbacks reports are available on the export page.
  * Learn more about [postbacks](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration) and [rejected postbacks](/docs/rejected-attribution-postbacks-to-integrated-partners).
* Install and IAE attribution blocking, only affects how and where data is reported in AppsFlyer. They do not prevent app usage by your end-users.
  * If needed, you can use the [blocked install and blocked IAE raw data reports](/docs/protect360-raw-data-reports) (available via export, pull API, and data locker), to get the list of app users to be disabled.
* Blocked installs/IAE reports and rejected postbacks contain the name of the rules that blocked the installs/IAE under the block reason. See the [multiple rules](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules) section if there is more than one rule.
  * When installs/in-app events are blocked by the Protect360 anti-fraud engine, even if there is also a validation rule, the Protect360 reasons are displayed.
* Rules can result in reporting discrepancies between AppsFlyer and SRNs like [Meta ads](/docs/meta-ads-discrepancies) and [Google Adwords](/docs/google-ads-adwords-faq-and-discrepancies) as they deploy their own logic to validate installs.

</Accordion>

<Accordion title="Multiple rules">

* Multiple validation rules can run on the same install/IAE. This happens when the install meets the conditions of multiple rules.
* The install/IAE is classified as invalid when it does not comply with the conditions of any of the rules separately.
* In raw data reports and rejected postbacks, the **block reason value** field contains the names of all the rules that classify the install or in-app event as invalid.
* Multiple rules for the same install are sequenced to run in the following order, based on the block types of the rules:

| Rule/block types | Order |
| --- | --- |
| Block installs | Random |
| Block attribution | Random |
| Block in-app event | Random |
| Remove from AppsFlyer entirely and anything else | Removed from AppsFlyer. Other rules are ignored. |
| Block installs and block attribution | <ol><li>Block install rules (in random order)</li><li>Block attribution rules (in random order)</li></ol> |
| Block installs and block attribution with Protect360 engine and validation rules | <ol><li>Block installs from Protect360 engine</li><li>Block install from validation rules</li><li>Block attribution from Protect360 engine</li><li>Block attribution from validation rules</li></ol> |
| Block in-app events with Protect360 engine and validation rules | <ol><li>Block IAE from Protect360 engine</li><li>Block IAE from validation rules</li></ol> |

</Accordion>

## Rule builder

The rule builder user interface is designed for interactive rule building. **Tip!** Familiarize and experiment with the rule builder before reviewing this article in detail.

### Use categorized dimensions

When adding rule conditions, parameters are grouped into categories to make rule setup easier. Categories and parameters are shown based on the selected event type and your account permissions.

You can search across all categories simultaneously. Matching categories expand automatically.

Parameters that aren’t relevant to the selected event type, or aren’t included in your permissions, are hidden.

| Category | Parameters |
| --- | --- |
| Campaign & source | Media source, Campaign, Campaign ID, Site ID, Ad set name, Ad set ID, Ad ID, AF Sub 1-5 |
| Geography & device | Geo, Platform, OS version, Device model, Carrier, User agent |
| Attribution | CTIT, Lookback days, Lookback hours, Attribution touch type |
| Identity | Customer user ID, IDFA, Advertiser ID, IP address |
| App & SDK | App version, SDK version, Installer/Store, Custom Installer/Store, Is preinstalled, Is Deeplink |
| End-user event | Event name, Event value, Install to event time, Event source, Currency, Revenue |
| Engagements | Engagement |

![New Validation Rule page.jpg](https://files.readme.io/23875c647c24226c09f5aa2f4dbb85264f95b09e867a053ee55bc2d3ebbc9895-21855980276753.png)

The rule builder contains the following sections:

| Section | Remarks |
| --- | --- |
| General details | <ul><li>**Rule name -** Enter a name for the new rule.</li><li>**Rule type -** Select the rule type, **Real time**, or **Post attribution**.</li><li>**Events** - Select the event type for which the rule is applied, **Installs** or **In-app events**.</li><li>**App selection -** Select **Selected apps**, or **All apps.**<ul><li>If **Selected apps** is selected:<br />**Select apps -** Select the apps for which the rule is applied: A single app, multiple apps, or all apps in the account.</li><li>If **All apps** is selected:<br />Option to check **Include future apps -** This allows future apps to be included in this rule.</li></ul></li></ul>The selections affect the options available in the following sections (agency, media source, campaign, etc.)<br /><br /><br /><br />**Note**<br />App version must only contain numbers. For example 2.2.1<br /><br />Note:<br /><br />Numeric app versions (for example, 2.2.1) supports all operators (equals, greater than, lower than, etc.).<br /><br />If the app version is custom text (for example, version123 or our\_latest\_version), only the "equals" or "doesn't equal" operators work; "greater than" or "lower than" won't apply. |
| Traffic sources | Traffic source for which the rule is applied. [See also Protect360 sources](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) |
| Conditions | Choose whether you want to block installs/in-app events that "Match" or "Don't match" the defined conditions.<ul><li>**Match conditions -** Attribution will be blocked for installs/in-app events that match the defined conditions, and the action you select below will apply to all of these.</li><li>**Do not match conditions -** Attribution will be blocked for installs/in-app events that don’t match the following conditions, and the action you select below will apply to all the rest.</li></ul>See also Protect360 conditions for [installs](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions) and [in-app events](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions). |
| Actions | For installs, select what to do with the installs meeting the specified conditions:<ul><li>**Mark installs as invalid and don’t attribute them**. Installs won’t appear in AppsFlyer dashboards except Protect360 and reports.</li><li>**Block attribution and correct to last valid media source**. If no valid media source is identified, the install is considered organic.</li></ul>For in-app events, select what to do with the installs meeting the specified conditions:<ul><li>**Block attribution, but show in Protect360 data**. Events aren’t attributed but show in the Protect360 dashboard and raw data.</li><li>**Remove from AppsFlyer**. Events will not show in the AppsFlyer platform at all.</li></ul>See [Outcomes](/docs/implement-validation-rules-to-prevent-fraud#outcomes) for more information. |

## Validation rule examples

<Accordion title="Install sources">

The **Sources** section is where you define the traffic sources of the installs the rule applies to.

There are three primary options:

* **All traffic:** Includes both organic and non-organic installs. Source information is unavailable for organic installs. This option includes all media sources, including those added in the future.  
  *Example*: Apply a rule to all traffic with app version lower than X.
* **All traffic of Non-organic:** Applies to all agency and non-agency non-organic traffic sources, including new sources added later.  
  *Example*: Block non-organic traffic from a specific geo where you don’t run UA or retargeting campaigns.
* **Selected traffic of Non-organic:** Applies the rule to specific agencies or media sources only. You must manually select or add media sources when editing the rule.  
  *Example*: Block installs from a specific media source if the CTIT is longer than X days.

Additional source options are available for Protect360 customers for [installs](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) and [in-app events](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions).

<table><thead><tr><th>Field</th><th>Operator</th><th>Value</th><th>Remarks</th></tr></thead><tbody><tr><td>Agency</td><td><ul><li>In</li></ul></td><td><ul><li>Agency and non-agency traffic</li><li>Non-agency traffic</li><li>Transparent agencies (menu)</li></ul></td><td><p><span>Transparent agencies:</span></p><ul><li>These are agencies that specify their media sources.</li><li>Agencies that are transparent for only some of your selected apps, display in the non-transparent agencies menu.</li><li>All agencies are required to share their media sources.&lt;/li&gt;&lt;li&gt;Agencies that share media sources for only some of your selected apps appear in the Transparent agencies menu.&lt;/li&gt;&lt;/ul&gt;</li></ul></td></tr><tr><td>Media source</td><td><ul><li><span>In list</span></li><li><span>Not in list</span></li><li><span>Equals</span></li><li><span>Doesn't equal</span></li><li><span>Contains</span></li><li><span>Doesn't contain</span></li><li><span>Starts with</span></li><li><span>Ends with</span></li><li><span>Matches regular expression</span><span></span></li></ul></td><td><ul><li><span>Search for desired value.</span></li><li><span>Select from menu.</span></li><li><span>Free text (for values that don’t exist in your search results).</span></li></ul></td><td rowspan="6"><ul><li><span>Menu is based on:</span><ul><li>Selected apps and agencies.</li><li>Traffic of the past 30 days, ordered by traffic volume.</li></ul></li><li><span>Free text must be typed exactly as it appears in raw data.</span></li></ul></td></tr><tr><td>Campaign</td><td rowspan="5"><ul><li><span>In list</span></li><li><span>Not in list</span></li><li><span>Equals</span></li><li><span>Doesn't equal</span></li><li><span>Contains</span></li><li><span>Doesn't contain</span></li><li><span>Starts with</span></li><li><span>Ends with</span></li><li><span>Is empty</span></li><li><span>Isn't empty</span></li><li><span>Matches regular expression</span></li></ul></td><td><ul><li>Search for desired value.</li><li>Select value from menu.</li><li>Free text (for values that don’t exist in your search results).</li></ul></td></tr><tr><td>Campaign ID</td><td rowspan="4"><ul><li><span>Free text only.</span></li><li><span>Possible to add multiple values separated by spaces.</span></li></ul></td></tr><tr><td>Ad ID</td></tr><tr><td>Ad set ID</td></tr><tr><td>Ad set name</td></tr></tbody></table>

</Accordion>

<Accordion title="Install conditions">

The **Conditions** section is where you define the conditions that determine when install attributions are blocked, or attributed to the last valid source.

You can add multiple conditions, and groups of conditions to every rule.

Conditions are defined as per the conditions, operators, and values outlined in the table that follows.

#### Bulk upload

When selecting the operators **In list** or **not in list** inside of conditions that support it, you have the option to bulk upload a CSV file when adding new items.

To do this:

1. Select a condition with an **In list** or **not in list** operator.
2. Select **In list** or **not in list** from the operator dropdown list.
3. Select **Upload CSV file** from the **Add new items** box.

Note: The CSV file can contain up to 17K values.

Additional condition options are available for Protect360 customers, for [installs](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions) and [in-app events](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions).

<table><thead><tr><th><span>Condition</span></th><th><span>Operator</span></th><th><span>Value</span></th><th><span>Remarks</span></th></tr></thead><tbody><tr><td><span>Campaign</span></td><td rowspan="6"><ul><li><span>Equals</span></li><li><span>Doesn't equal</span></li><li><span>Doesn't contain</span></li><li><span>Contains</span></li><li><span>Starts with</span></li><li><span>Ends with</span></li><li><span>In list</span></li><li><span>Not in list</span></li><li><span>Matches regular expression</span></li><li><span>Is empty</span></li><li><span>Isn't empty</span></li></ul></td><td><ul><li>Search for desired value.</li><li>Select value from menu.</li><li>Free text (for values that don’t exist in your search results).</li></ul></td><td rowspan="11"><ul><li><span>Menu is based on:</span><ul><li>Selected apps and agencies.</li><li>Traffic of the past 30 days, ordered by traffic frequency.</li></ul></li><li><span>Free text must be typed exactly as it appears in raw data.</span></li></ul></td></tr><tr><td><span>Campaign ID</span></td><td rowspan="5"><ul><li><span>Free text only.</span></li><li><span>Possible to add multiple values separated by spaces.</span></li></ul></td></tr><tr><td><span>Ad ID</span></td></tr><tr><td><span>Ad set ID</span></td></tr><tr><td><span>Ad set name</span></td></tr><tr><td><span>Device type</span></td></tr><tr><td><span>Geo</span></td><td rowspan="3"><ul><li><span>In list</span></li><li><span>Not in list</span></li><li><span>Equals</span></li><li><span>Doesn't equal</span></li></ul></td><td><ul><li><span>Search required value (based on country name, country code, state, or city).</span></li><li><span>Select value from menu.</span></li></ul></td></tr><tr><td><span>Platform</span></td><td><span>Select value from menu.</span></td></tr><tr><td><span>Currency</span></td><td><p>Currency only. Possible values:</p><p>USD, NZD, SGD, IMP, ANG, MNT, BIF, BBD, HUF, ERN, AZN, AOA, PYG, MYR, GYD, VUV, SLL', FKP, DJF, GNF, LVL, MMK, MRO, RSD, CLF, XDR, ZAR, TND, PHP, KGS, XPD, RON, RUB, KMF, SCR, GIP, TRY, JEP, UYU, XCD, FJD, GHS, MVR, AWG, UGX, TOP, CVE, MKD, COP, CUC, GTQ, KZT, MXN, MGA, AUD, BDT, ISK, KRW, DZD, GGP, OMR, ZMW, MOP, CUP, JPY, SHP, LSL, ETB, BWP, MAD, AED, NGN, BRL, GEL, IDR, EUR, GBP, WST, XAF, SZL, XOF, SEK, UZS, KES, KYD, ILS, KWD, NPR, BZD, QAR, UAH, BTN, HTG, DKK, VND, SBD, JMD, IQD, LBP, XPT, HRK, HKD, JOD, PAB, CDF, VEF, XAU, BAM, CNY, SOS, XPF, GMD, DOP, XAG, KPW, BOB, BHD, BYN, BYR, LRD, BGN, AMD, CZK, CAD, LAK, EEK, MTL, PLN, LKR, BTC, MWK, LTL, ZMK, PGK, YER, PEN, KHR, RWF, BSD, AFN, ZWL, LYD, TMT, HNL, TWD, IRR, MUR, THB, ALL, TJS, SDG, BMD, CRC, NOK, SRD, MZN, CLP, STD, SYP, TZS, EGP, ARS, MDL, INR, SAR, PKR, TTD, NIO, BND, NAD, SVC, CHF</p></td></tr><tr><td><span>Revenue</span></td><td><ul><li><span>Lower then</span></li><li><span>Lower than or equals</span></li><li><span>Greater than</span></li><li><span>Greater than or equals</span></li><li><span>Is between</span></li><li><span>Equals</span></li><li><span>Doesn't equal</span></li></ul></td><td><ul><li><span>Free text only.</span></li></ul></td></tr><tr><td><span>OS version</span></td><td><ul><li><span>Lower than</span></li><li><span>Lower than or equals</span></li><li><span>Greater than</span></li><li><span>Greater than or equals</span></li><li><span>Equals</span></li><li><span>Doesn't equal</span></li><li><span>Is between</span></li><li><span>In list</span></li><li><span>Not in list</span></li><li><span>Is empty</span></li><li><span>Isn’t empty</span></li></ul></td><td><ul><li><span>Search for desired value.</span></li><li><span>Select from menu.</span></li><li><span>Free text (for values that don’t exist in your search results).</span></li></ul></td></tr><tr><td><span>App version</span></td><td><ul><li><span>Lower than</span></li><li><span>Lower than or equals</span></li><li><span>Greater than</span></li><li><span>Greater than or equals</span></li><li><span>Equals</span></li><li><span>Doesn't equal</span></li><li><span>Is Between</span></li><li><span>In list</span></li><li><span>Not in list</span></li><li><span>Not in last</span></li><li><span>Not in last (major)</span></li><li><span>Is empty</span></li><li><span>Isn’t empty</span></li></ul></td><td><ul><li>Search for desired value.</li><li>Select value from menu.</li><li>Free text (for values that don’t exist in your search results).</li></ul></td><td><ul><li><span>Menu is based on t</span>raffic of the past 30 days, ordered by traffic frequency.</li><li><span>Free text must be typed exactly as it appears in raw data.</span></li><li><span>For "Not in last," if you have more than one series of versions, select "Not in last (major)". </span><a href="./implement-validation-rules-to-prevent-fraud#how-do-the-not-in-last-conditions-work"><span>Learn more</span></a></li></ul></td></tr><tr><td><span>Lookback days</span></td><td><ul><li><span>Lower than</span></li><li><span>Greater than or equals</span></li><li><span>Is between</span></li></ul></td><td><ul><li><span>Free text: A single numeric value.</span></li></ul></td><td><ul><li><span>Refers to the impression/click lookback window in days.</span></li><li><span>Ensures you don’t pay for installs with an attribution link that was modified to allow a longer attribution period.</span></li><li><span>Does not replace the configuration of the lookback window in your attribution link.</span></li><li><span>[Recommended] Use in combination with the attribution touch type condition (</span><a href="./implement-validation-rules-to-prevent-fraud#protect360-install-conditions"><span>available with Protect360</span></a><span>)</span></li></ul></td></tr><tr><td><span>Is preinstalled</span></td><td rowspan="2"><ul><li><span>Yes</span></li><li><span>No</span></li></ul></td><td rowspan="2"><ul><li>No value (operator is the value)</li></ul></td><td><ul><li><span>Validates all types of preinstalls:</span><ul><li><span>Factory preinstalls, meaning an app that comes on the device as part of the OS.</span></li><li><span>Offered preinstalls, meaning an app promoted and offered to users as soon as the device is initialized. This is done by media sources designated for preinstalls.</span></li></ul></li><li>For installs with multiple clicks/ sources, this condition validates whether one of the sources is a preinstall.</li></ul></td></tr><tr><td><span>Is deeplink</span></td><td><span>An empty deep link field in raw data is considered to be Is deeplink = No</span></td></tr></tbody></table>

> 📘 **Note**
>
> Organic installs have no associated campaign or media source, so fields like **Campaign** and **Ad set name** are always **null** for them, not empty strings. A rule that uses **Match conditions** with an **Is empty** operator on these fields won't match organic installs, so it won't block them.
>
> To also catch organic traffic, configure the rule with **Don't match conditions** instead, combining your conditions with **Or**, using **Isn't empty** on the same fields (for example, **Campaign isn't empty** **Or** **Ad set name isn't empty**, plus any other conditions the rule needs). Inverting the logic this way lets the rule match null values along with empty strings.

</Accordion>

<Accordion title="In-app event sources">

When **In-app events** is selected in the **Events** section, then in addition to the [regular source options](/docs/implement-validation-rules-to-prevent-fraud#install-sources), customers have another source option to define which in-app events their rule applies to. 

The source is defined as per the field, operators, and values outlined in the table that follows.

**Note**: All other in-app events sources are based on the source of the install the IAE is associated with (for example, agency, media source, campaign, campaign ID, site ID, etc.).

| Field | Operator | Value | Remarks |
| --- | --- | --- | --- |
| Event name | <ul><li>In list</li><li>Not in list</li><li>Equals</li><li>Doesn’t equal</li><li>Contains</li><li>Doesn’t contain</li><li>Starts with</li><li>Ends with</li><li>Is empty</li><li>Isn’t empty</li><li>Matches regular expression</li></ul> | <ul><li>Search for desired value.</li><li>Select value from menu.</li><li>Free text (for values that don’t exist in your search results).</li></ul> | <ul><li>Free text must be typed exactly as it appears in raw data.</li></ul> |

</Accordion>

<Accordion title="In-app event conditions">

When **In-app events** is selected in the **Events** section, customers have additional condition options to define which in-app events their rule applies to. These conditions can be mixed and matched with any of the non-Protect360 conditions [listed previously](/docs/implement-validation-rules-to-prevent-fraud#install-conditions).

Protect360 conditions are defined as per the conditions, operators, and values outlined in the table that follows.

| Condition | Operator | Value | Remarks |
| --- | --- | --- | --- |
| Event name | <ul><li>In list</li><li>Not in list</li><li>Equals</li><li>Doesn’t equal</li><li>Contains</li><li>Doesn’t contain</li><li>Starts with</li><li>Ends with</li><li>Is empty</li><li>Isn’t empty</li><li>Matches regular expression</li></ul> | <ul><li>Search for desired value.</li><li>Select value from menu.</li><li>Free text (for values that don’t exist in your search results).</li></ul> | <ul><li>Free text must be typed exactly as it appears in raw data.</li></ul> |
| App version | <ul><li>Lower than</li><li>Lower than or equals</li><li>Greater than</li><li>Greater than or equals</li><li>Equals</li><li>Doesn't equal</li><li>Is Between</li><li>In list</li><li>Not in list</li><li>Not in last</li><li>Not in last (major)</li><li>Is empty</li><li>Isn’t empty</li></ul> | <ul><li>Search for desired value.</li><li>Select value from menu.</li><li>Free text (for values that don’t exist in your search results).</li></ul> | <ul><li>Menu is based on traffic of the past 30 days, ordered by traffic frequency.</li><li>Free text must be typed exactly as it appears in raw data.</li><li>For "Not in last," if you have more than one series of versions, select "Not in last (major)". [Learn more](/docs/implement-validation-rules-to-prevent-fraud#how-do-the-not-in-last-conditions-work)</li></ul> |

> 📘 **Note**
>
> Event name conditions are not case sensitive. All event names are automatically converted to lowercase before evaluation. For example, if you enter **Submit Form**, the system treats it as **submit form**.

</Accordion>

<Accordion title="Protect360 install and in-app event sources">

In addition to the [regular source options](/docs/implement-validation-rules-to-prevent-fraud#install-sources), Protect360 customers have another source option to define which installs their rule applies to. The source is defined as per the field, operators, and values outlined in the table that follows.

| Field | Operator | Value | Remarks |
| --- | --- | --- | --- |
| Site ID | <ul><li>In list</li><li>Not in list</li><li>Equals</li><li>Doesn’t equal</li><li>Contains</li><li>Doesn’t contain</li><li>Starts with</li><li>Ends with</li><li>Is empty</li><li>Isn’t empty</li><li>Matches regular expression</li></ul> | <ul><li>Free text only.</li><li>Possible to add multiple values separated by spaces.</li></ul> | <ul><li>Free text must be typed exactly as it appears in raw data.</li></ul> |

</Accordion>

<Accordion title="Protect360 install conditions">

Protect360 customers have an additional set of conditions to validate their installs. These conditions can be mixed and matched with any of the non-Protect360 conditions [listed previously](/docs/implement-validation-rules-to-prevent-fraud#install-conditions).

Protect360 conditions are defined as per the conditions, operators, and values outlined in the table that follows.

<table><thead><tr><th><span>Condition</span></th><th><span>Operator</span></th><th><span>Value</span></th><th><span>Remarks</span></th></tr></thead><tbody><tr><td><span>CTIT (Click Time to Install Time)</span></td><td><ul><li><span>Lower than</span></li><li><span>Greater than or equals</span></li><li><span>Is between</span></li></ul></td><td><ul><li><span>Free text: A single numeric value.</span></li></ul></td><td><ul><li><span>Only use this field if you are certain of a specific CTIT (usually in a specific geo). Otherwise, you may cause false-positive blocked installs.</span><br/><span><strong>Note</strong>: The Protect360 anti-fraud engine has built-in sophisticated ways to identify complex CTIT anomalies due to attribution hijacking, click flooding, fake installs by bots, and more.</span></li><li><span>Consider using this field together with the following fields:</span><ul><li>Is pre-installed</li><li>Is deeplink</li><li>Geo</li></ul></li></ul><p>Note: The CTIT install condition does not support blocking installs attributed to engaged click engagement type, only 'regular' clicks.</p></td></tr><tr><td><span>Customer user ID (CUID)</span></td><td><ul><li><span>Equals</span></li><li><span>Doesn't equal</span></li><li><span>Doesn't contain</span></li><li><span>Contains</span></li><li><span>Starts with</span></li><li><span>Ends with</span></li><li><span>In list</span></li><li><span>Not in list</span></li><li><span>Matches regular expression</span></li><li><span>Is empty</span></li><li><span>Isn't empty</span></li></ul></td><td><ul><li><span>Free text only.</span></li><li><span>Possible to add multiple values separated by spaces.</span></li></ul></td><td><ul><li><span>Menu is based on t</span>raffic of the past 30 days, ordered by traffic frequency.</li><li><span>Free text must be typed exactly as it appears in raw data.</span></li></ul></td></tr><tr><td><span>SDK version</span></td><td><ul><li><span>Lower than</span></li><li><span>Lower than or equals</span></li><li><span>Greater than</span></li><li><span>Greater than or equals</span></li><li><span>Equals</span></li><li><span>Doesn't equal</span></li><li><span>Is Between</span></li><li><span>In list</span></li><li><span>Not in list</span></li></ul></td><td><ul><li>Search for desired value.</li><li>Select value from menu.</li><li>Free text (for values that don’t exist in your search results).</li></ul></td><td><ul><li><span>Menu is based on t</span>raffic of the past 30 days, ordered by traffic frequency.</li><li><span>Free text must be typed exactly as it appears in raw data.</span></li></ul></td></tr><tr><td><span>Installer/Store</span></td><td rowspan="3"><ul><li>In list</li><li>Not in list</li><li>Equals</li><li>Doesn’t equal</li></ul></td><td><p><span>Select value from menu:</span></p><ul><li>Google Play</li><li>Other stores</li><li>Out of store</li></ul></td><td><ul><li>Google Play: AppsFlyer identifies that the install package is <code>com.android.vending</code>.</li><li>Other stores: AppsFlyer identifies that the install is from a third-party Android store.</li><li>Out of store: AppsFlyer identifies an APK that is not in any Android store.</li></ul><p><span>In the event that a user's device does not provide the installer/store parameter to AppsFlyer, the rule does not take effect.</span></p></td></tr><tr><td>Custom Installer/Store</td><td>Free text (for values that don’t exist in your search results).</td><td><ul><li>If the client picked a condition of "other" AND also a condition of custom installer=X - the bocking will be only for installer X</li><li>If the client picked a condition of "other" OR  a condition of custom installer=X - the bocking will be for ALL "other" installers / stores - and X is a part of that group</li></ul></td></tr><tr><td><span>Attribution touch type</span></td><td><ul><li><span>Click</span></li><li><span>Impression</span></li></ul></td><td><ul><li>[Recommended] Use in combination with the lookback days condition.</li><li>To simply not attribute for impressions, you can <a href="./measure-view-through-engagements#turn-off-viewthroughattribution">turn off view-through attribution</a>.</li></ul></td></tr><tr><td><span>Carrier</span></td><td><ul><li>In list</li><li>Not in list</li><li>Equals</li><li>Doesn't equal</li></ul></td><td><ul><li><span>Free text only</span></li></ul></td><td> </td></tr><tr><td><span>User agent</span></td><td><ul><li>Contains</li><li>Doesn't contain</li></ul></td><td><ul><li><span>Free text only</span></li></ul></td><td> </td></tr><tr><td><span>IP address</span></td><td><ul><li>In list</li><li>Not in list</li><li>Equals</li><li>Doesn't equal</li></ul></td><td><ul><li><span>Free text only</span></li></ul></td><td> </td></tr></tbody></table>

</Accordion>

<Accordion title="Protect360 in-app event conditions">

When **In-app events** is selected in the **Events** section, Protect360 customers have additional condition options to define which in-app events their rule applies to. These conditions can be mixed and matched with any of the non-Protect360 conditions [listed previously](/docs/implement-validation-rules-to-prevent-fraud#install-conditions).

Protect360 conditions are defined as per the conditions, operators, and values outlined in the table that follows.

| Condition | Operator | Value | Remarks |
| --- | --- | --- | --- |
| Event source | <ul><li>In list</li><li>Not in list</li><li>Equals</li><li>Doesn’t equal</li></ul> | <ul><li>Search for desired value.</li><li>Select value from menu.</li></ul> | Select either SDK or Server-to-server. |
| Event value | <ul><li>In list</li><li>Not in list</li><li>Equals</li><li>Doesn’t equal</li><li>Contains</li><li>Doesn’t contain</li><li>Starts with</li><li>Ends with</li><li>Is empty</li><li>Isn’t empty</li><li>Matches regular expression</li></ul> | <ul><li>Free text only.</li><li>Possible to add multiple values separated by spaces.</li></ul> | <ul><li>Select your preferred values.</li></ul> |
| Install to event time (in seconds) | <ul><li>Lower than</li><li>Greater than or equals</li><li>Is between</li></ul> | Free text. A single numeric value. | <ul><li>Based on your app’s flow, you decide the valid time to pass between the app install and an IAE.<ul><li>Example: Time to reach level 5, time to first-time-deposit (FTD), time to checkout, etc.</li></ul></li><li>Time is in seconds, but you can validate minutes, hours, or days using the seconds equivalent.</li></ul> |

</Accordion>

<Accordion title="Logic between conditions and condition groups">

If you add multiple conditions or condition groups to a rule, select the logical relation between them using either: 

* **And**: Meaning the install complies with all the defined conditions.
* **Or**: Meaning the install complies with at least one of the defined conditions.

For example, if you want to validate installs based on both platform and OS, you must select **and**. That way, the defined platform must always accompany the defined OS. If you want to validate installs based on either platform or OS, you must select **or**.

</Accordion>

## Additional features

<Accordion title="View rule list">

**To view all the rules created in your account**:

1. In AppsFlyer, go to **Settings** > **Validation Rules.**  
   The Validation Rules window opens, with the list of validation rules.
2. Select your preferred table view using the **List view/Details view** toggle.
3. Filter the rules in the list using the search and the filter options.
   * You can search by rule name, source, condition name, and value.
   * For example, type **7** to find all rules defined for an OS version that contains 7. (e.g.: “2.7.4”, “7.1”, etc.). Or type **Canada** to find rules defined with Canada in the Geo condition.

The Validation Rules table shows 25 rules per page by default. You can change the number of rules shown per page to 10, 25, or 50.

Search and filters apply to the full rule set, regardless of the page you’re viewing.

</Accordion>

<Accordion title="Add rule">

**To set up a new rule**:

1. In AppsFlyer, go to **Settings** > **Validation Rules.**  
   The Validation Rules window opens.
2. Click **Add Rule.**  
   The Add new rule window opens.
3. Insert a **rule name**. Use a unique name that:
   * accurately describes the rule.
   * is not offensive to ad networks, as it displays in the blocked installs report, as well as in the rejected postbacks to ad networks.
4. Complete the [rule builder sections](/docs/implement-validation-rules-to-prevent-fraud#rule-builder).
5. [Optional] Add conditions and/or condition groups, as required. Make sure to select the relevant [logic between conditions/condition groups](/docs/implement-validation-rules-to-prevent-fraud#logic-between-conditions-and-condition-groups).
6. [Optional] Click **Estimate traffic impact** to [see how your rule will affect traffic](/docs/implement-validation-rules-to-prevent-fraud#view-validation-rule-impact).
7. Click **Save**.

> 📘 **Note**
>
> App version must only contain numbers. For example 2.2.1
>
> Note:
>
> Numeric app versions (for example, 2.2.1) supports all operators (equals, greater than, lower than, etc.).
>
> If the app version is custom text (for example, version123 or our\_latest\_version), only the "equals" or "doesn't equal" operators work; "greater than" or "lower than" won't apply.

</Accordion>

<Accordion title="VR tagged mode">

Use Tagged mode to test validation rules on live traffic before blocking attribution. Tagged rules flag installs and in-app events that match the rule conditions, but attribution isn’t affected.

Tagged mode supports installs and in-app events only.

Use Tagged mode to:

* Test complex rules on live traffic before blocking attribution.
* Identify possible false positives.
* Review why a rule would have triggered before you enforce the rule.
* Understand the real traffic impact before changing the rule status to Implemented.

Best practice: Create the rule in Tagged mode first, review the flagged traffic in Data Locker, and change the rule status to Implemented when you’re confident in the rule accuracy. Aim to complete this review in less than 7 days to maintain active protection.

#### How Tagged mode works

When you create or edit a validation rule, select the Detection status in the Rule outcome section.

* Tagged: The rule flags matching data for reporting and analysis. Attribution isn’t affected.
* Implemented: The rule actively blocks attribution according to the selected rule outcome.

Note: Tagged mode applies only to live traffic from the moment the rule is saved. It doesn’t tag historical data.

#### Rule outcome configuration

The Rule outcome section, formerly Action, defines how AppsFlyer handles traffic that matches the rule conditions. It also provides a high-level summary of the rule configuration so you can verify the expected impact before saving the rule.

| Detection status | Effect on attribution | Data availability |
| --- | --- | --- |
| Tagged | No impact. Traffic is attributed normally. | Visible in Data Locker and raw data export reports. |
| Implemented | Active block. Attribution is blocked according to the selected rule outcome. | Visible in Protect360 dashboards and export reports. |

#### What to expect when configuring a rule

As you configure the rule, a dynamic info panel shows the expected rule behavior based on:

* Match or Do not match logic
* App selection
* Detection status

When Detection status is set to Tagged, the rule acts as a discovery tool. AppsFlyer shows a notification confirming that matching data is flagged in export reports, including Data Locker, but isn’t blocked from attribution.

When Detection status is set to Implemented, installs or in-app events that match the rule criteria are blocked from attribution or reattributed according to the selected rule outcome. The info panel summarizes the active outcome before you save the rule.

#### Example: Match logic

For detected installs that meet the rule conditions for the selected apps, the info panel can indicate that the installs are:

* Blocked from attribution or detected as post-attribution.
* Reattributed to the last valid non-organic or organic source.
* Visible in export reports.

#### Example: Do not match logic

For detected installs that don’t meet the rule conditions for the selected apps, including future apps, the info panel can indicate that the installs are:

* Blocked from attribution or detected as post-attribution.
* Marked as fraud without attribution correction.
* Visible in export reports.

All other installs that meet the rule conditions within these apps aren’t blocked.

#### Set a rule to Tagged mode

To test a validation rule with Tagged mode:

1. In AppsFlyer, go to Settings > Validation Rules.
2. Select an existing rule or click Add Rule.
3. Complete the rule details, traffic sources, and conditions.
4. In the Rule outcome section, set Detection status to Tagged.
5. Click Save.

After the rule is saved, AppsFlyer flags matching live traffic for reporting and analysis. Attribution continues as usual.

#### Analyze tagged data

Tagged validation rule data isn’t visible in the Protect360 dashboard or Fraud Protection Suite.

To analyze the impact of tagged rules, use Data Locker or raw data export reports. Tagged data is available for installs and in-app events, so you can compare tagged traffic with valid attributions.

**Tagged data mapping:**

| Tagged data | Data Locker | Raw data report |
| --- | --- | --- |
| Tagged installs | Installs report | Tagged Installs |
| Tagged in-app events | In-app Events report | Tagged In-app Events report |

**Tagged data fields**

Use the following columns in Data Locker and Raw data exports to identify traffic flagged by validation rules:

| Column | Description |
| --- | --- |
| Rule name<br /><br />(Raw data reports) | The name of the validation rule that flagged the record. |
| Rule ID<br /><br />(Raw data reports) | The unique ID of the validation rule that flagged the record. |
| detected\_rule\_name<br /><br />(Data Locker) | The name of the validation rule that flagged the record. |
| detected\_rule\_id<br /><br />(Data Locker) | The unique ID of the validation rule that flagged the record. |

#### Change a tagged rule to Implemented

After you review the tagged data and confirm that the rule works as expected, change the rule status to Implemented.

To change a rule from Tagged to Implemented:

1. In AppsFlyer, go to Settings > Validation Rules.
2. Select the rule.
3. In the Rule outcome section, set Detection status to Implemented.
4. Click Save.

From the moment the rule is saved, AppsFlyer actively blocks matching traffic according to the selected rule outcome.

</Accordion>

<Accordion title="Edit or delete a rule">

**To edit, delete, enable, or disable a rule**:

* In the [rule list](/docs/implement-validation-rules-to-prevent-fraud), select the action you want to perform for a specific rule.
  * Under **Active**: enable or disable the rule.
  * Under **Action**: edit or delete the rule.

</Accordion>

## FAQ

<Accordion title="What is a 'regular expression'?">

A regular expression pattern is composed of characters for which you want to find a match. Simple patterns are constructed with characters for which you want to find a direct match. When the search for a match requires something more than a direct match, you can include special characters in the pattern.

**Examples**:

| **Regular expression** | **Description** |
| --- | --- |
| ^abc | Starts with abc |
| xyz$ | Ends with xyz |
| ^abc.*xyz$ | Starts with abc and ends with xyz |
| ^abc.*(?&lt;xyz)$ | Starts with abc and doesn’t end with xyz |
| ^([0-9]`{2}`) | Starts with 2 digits |
| "example\_param":"[5\|6] | Specified parameter's value begins with 5 or 6. |
| ^.\{0\}$\|^\{\}$ | Is empty, or is only \{\} |

</Accordion>

<Accordion title="Why doesn't the source or condition display as a suggested value when I search for it?">

There are two possible reasons:

* Make sure the relevant app/s are selected. If the app isn't selected, values don't display in search results.
* Results display only if the value you are searching for appeared in your traffic during the past 30 days. Additionally, there is a lag of up to 1 day between when the conversion occurs, and when the source or condition displays as a menu option.

If the value does not appear as a search result, you can type the value as free text and press the Enter key on your keyboard.

</Accordion>

<Accordion title="Why do my media source options only include Meta ads and X Ads?">

The Media Sources field options are affected by your Agency selection.

</Accordion>

<Accordion title="Is it necessary to have 'and/or' both within specific conditions and between condition groups?">

It depends on your use case. Sometimes either option achieves the same results. Other times, both options are necessary.

For example, if in USA you support installs only on OS V10 or later, but in Brazil, you support from V7 and later, you'll need a rule like:

`{[Geo = US] and [OS version = 10]} OR {[Geo = Brazil] and [OS version = 7]}`

</Accordion>

<Accordion title="Do validation rules block clicks?">

No. Validation rules can block installs, block attribution to an install’s sources (that prevents the media source of a click/impression from receiving attribution), or block in-app events. However, none of these options blocks the actual click, and click KPIs are not affected by executing validation rules.

</Accordion>

<Accordion title="Looking at the raw data, I see that installs I expected to be blocked by validation rules have a different block reason than my rule name. Why is that?">

This means the block was due to the [Protect360 engine](/docs/protect360-raw-data-reports#blocked-reasons) and not a validation rule. See also [multiple rules](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules).

</Accordion>

<Accordion title="Do existing rules automatically apply for newly-integrated agency traffic?">

This depends on your **Source** settings, as described in the table below.

If the rule is not automatically applied, you must edit the rule:

* Change the Agency field to either **Agency and non-agency traffic**, or select the specific agency.

<table><thead><tr><th>Source setting</th><th>Agency field selection</th><th>Is rule applied if rule was created before any agency integration with one of your apps?</th><th>Is rule applied if rule was created after at least one agency integration with one of your apps?</th></tr></thead><tbody><tr><td>All traffic</td><td>N/R</td><td>Yes</td><td>Yes</td></tr><tr><td rowspan="3">Non-organic only</td><td>N/R</td><td>No</td><td>N/R</td></tr><tr><td>Agency and non-agency traffic</td><td>N/R</td><td>Yes</td></tr><tr><td><p>Non-agency traffic and/or</p><p>specific agencies</p></td><td>N/R</td><td>No</td></tr></tbody></table>

</Accordion>

<Accordion title="How do the 'not in last' conditions work?">

Use **Not in last** to allow installs from your **most recent app versions** and block installs from **older versions**.

* **Not in last** ***X*** **versions**: Allows installs from the **last X versions** of the selected app, and **blocks** installs from **all earlier versions**.
* **Not in last (major)** ***X*** **versions**: Use when your versioning includes **multiple major version series** (for example, 1.x and 2.x). This condition allows the **last X versions within each major series**, and blocks earlier versions in each series.

##### Example: Not in last

You have these existing app versions:

* 1.0.01
* 1.0.02
* 1.0.03
* 2.0.01
* 2.0.02
* 2.0.03

A rule defined with **Not in last 2 versions**:

* **Allows**:
  * 2.0.02
  * 2.0.03
* **Blocks**:
  * 1.0.01
  * 1.0.02
  * 1.0.03
  * 2.0.01

##### Example: Not in last (major)

Using the same versions list above, a rule defined with **Not in last (major) 2 versions**:

* **Allows**:
  * 1.0.02
  * 1.0.03
  * 2.0.02
  * 2.0.03
* **Blocks**:
  * 1.0.01
  * 2.0.01

##### **Understand how the condition works with multiple apps**

If you select **multiple apps** in the rule, AppsFlyer evaluates the **Not in last** condition **separately for each app**.

For example, if you set **Not in last 3 versions** and select App A, App B, and App C:

* App A allows its **last 3 versions** based on **App A’s** version history.
* App B allows its **last 3 versions** based on **App B’s** version history.

App C allows its **last 3 versions** based on **App C’s** version history.

</Accordion>

<Accordion title="How do I block attribution for installs or in-app events from impressions?">

Use a validation rule when you want to prevent attribution from impression-based engagements and keep attribution only for valid clicks. If no valid click-based media source is found, the install is attributed as organic. This setup can help address attribution scenarios related to install hijacking.

To configure the rule:

* Under **Traffic sources**, select **All non-organic traffic.**
* Under **Conditions**, select **Attribution touch type**.
  * Set the operator to **In list**.
  * Select **Impression**.
* Under **Action**, select **Block attribution and correct to last valid media source**.

Don’t select **Mark installs as invalid and don’t attribute them** for this use case. That action is intended for installs you consider invalid or fake. If the install is real, but you don’t want to attribute it to impression-based engagement, use **Block attribution and correct to last valid media source** instead.

</Accordion>

<Accordion title="Does Tagged mode support all condition types?">

Yes. Tagged mode supports all validation rule operators and fields, including And/Or logic, Geo, OS version, SDK version, and Event value.

</Accordion>

<Accordion title="Will tagged data appear in blocked reports?">

No. Tagged data isn’t classified as blocked traffic. Tagged traffic maps as Tagged and is considered a subset of valid traffic. It’s visible in valid reports in Data Locker.

</Accordion>

<Accordion title="Where can I view tagged data?">

Use Data Locker or raw data export reports to view tagged validation rule data. Tagged installs are available in tagged installs reports, and tagged in-app events are available in tagged in-app events reports.

Tagged data isn’t visible in the Protect360 dashboard or Fraud Protection Suite.

</Accordion>

<Accordion title="Can I change a rule from Tagged to Implemented at any time?">

Yes. After you review the export data and confirm that the rule works as expected, edit the rule, set Detection status to Implemented, and save the rule. From that moment, the rule actively blocks matching traffic according to the selected rule outcome.

</Accordion>

<Accordion title="Is there a limit to how many rules can be set to Tagged?">

Tagged mode is available for Premium customers. There is no strict limit to the number of rules that can be set to Tagged. As a best practice, review tagged rules and change them to Implemented when you’re confident in the rule accuracy.

</Accordion>

<Accordion title="Traits and limitations">

| Trait | Description |
| --- | --- |
| Account user access | Only account users with [appropriate permissions](/docs/user-management) can view, add, and edit Validation Rules. |
| User acquisition | Validation rules apply to installs, re-installs, and re-attributions (when the app was removed from the device). They do not apply in cases of re-engagement, meaning when the app is still on the device. |
| Automatic rule deactivation | If you create rules:<ul><li>using Protect360 sources or conditions, and then your Protect360 license or trial expires, the rules are automatically deactivated.</li></ul> |
| Ad networks | Require advertiser permission to **View validation rules** to view rule details. **Note**: Rule names are always visible (including in raw data).<br /><br />[Learn more about validation rules for ad networks](/docs/validation-rules-for-ad-networks-and-agencies) |
| Agencies | Require advertiser permission to:<ul><li>**View validation rules** to view rule details. **Note**: Rule names are always visible (including in raw data).</li><li>**Add validation rules** to add and edit rules. **Note**: Agencies can't edit rules created by advertisers.</li><li>**Access Protect360 dashboard & raw data** to view and add rules with Protect360 conditions.</li></ul>[Learn more about validation rules for agencies](/docs/validation-rules-for-ad-networks-and-agencies) |
| Unique users | If you have more than 100 in-app events configured, then even if you use Validation Rules to invalidate certain in-app events, the [limitation for unique users count](/docs/in-app-events-overview#limitations) still applies. Meaning events over 100 don't have unique users counted, even if they are invalidated by Validation Rules. |
| SKAN | Not supported |
| Engagement condition | The **Engagement** condition supports blocking only the **click\_to\_app** and **view** engagement types. Other engagement types aren't supported. |

</Accordion>

<div data-zendesk-anchors="01H8VFA2ADGT4AMC0NGDFXRB6Z=overview 01H8VFA2ADQVCR8RYV9SBG52R7=rule-builder h_01KTHT74EKM95D26AJJNCFG0XZ=use-categorized-dimensions h_01JK5G66CM9TCDK6GATNZC4QMW=note-2 h_01KQER0NTPGGC7RYVBGKTZP02S=validation-rule-examples h_01J4HRXAH6DEXXQZZ3YAWHY4TP=bulk-upload h_01M22JGTYB4YJXBRVWB8RDBK86=note h_01JWX0RVRCNAQ0SVRDMAJ5HPW1=note-1 procedures=additional-features 01H8VFA2AF6M84FKKVDTCXJEFR=additional-features h_01JK5GDDGAZRKBVXZCCZ0RRB56=note-2 h_01KQERXDE5SPB182AFA2CM2C78=how-tagged-mode-works h_01KQERXDE6668BR0EFDX9F5CYZ=rule-outcome-configuration h_01KQERXDE9AM8TWAAQK6XHETSA=what-to-expect-when-configuring-a-rule h_01KQERXDEAQHC3SVFRT8V5X5S3=example-match-logic h_01KQERXDEA63J9ST9YSF27JKRD=example-do-not-match-logic h_01KQERXDEBEKF59KBVYTBWS471=set-a-rule-to-tagged-mode h_01KQERXDEC1574K0V677N6ZGSY=analyze-tagged-data h_01KQERXDEG3ZQPEYTSXAMMJNYC=change-a-tagged-rule-to-implemented 01H8VFA2AG5DW5Z9G9FPSWM464=faq h_01KHRB9CBYYPK73K7SVC3N4B6A=example-not-in-last h_01KHRB9CC3BBTC41SXC482S7EY=example-not-in-last-major h_01KHRB9CC6GJDNH97N0GSHDNKE=understand-how-the-condition-works-with-multiple-apps" />
