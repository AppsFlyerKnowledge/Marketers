---
title: "Implement validation rules to prevent fraud"
excerpt: "Validation rules add a custom layer of protection against incorrectly targeted campaigns and fraud by enabling app owners to control which installs and in-app event attributions get blocked."
x-zendesk:
  id: 115004703926
  url: https://support.appsflyer.com/hc/en-us/articles/115004703926-Implement-validation-rules-to-prevent-fraud
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Protect your traffic
  section_id: 6551015912465
  position: 9
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 27439133508369
  content_tags: [pm-roy-yanai, Marketers, Protect360]
  labels: [Advertisers, validation rule, Marketers, Localize, Loc In Prog, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2017-09-14T14:43:46Z'
  edited_at: '2026-09-09T07:57:33Z'
---
Validation rules add a custom layer of protection against incorrectly targeted campaigns and fraud. The rules enable app owners to control which installs and in-app event attributions get blocked, or attributed to the last valid source.

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

``
````For installs: Validation rules, depending on the selected action, either block the attribution and correct to the last valid media source, or block the attribution completely.
````For in-app events: Validation rules block the attribution of the in-app event. 
``
``See the following table showing the validation rule block type outcomes.`<br/>` 
``

|  | Block type | Description | Where install data can be viewed | In-app events that follow |
| --- | --- | --- | --- | --- |
| **Installs** | Block attribution and correct to last valid media source | * Selected when you consider the install real, but your conditions determine which sources should or shouldn’t be attributed for it. * Attribution is corrected, and the install is attributed to the last valid media source. * If no valid media source is identified, the install is marked as organic. | * AppsFlyer dashboards and raw data reports as a regular install (attributed to the last valid media source) * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Has the same corrected attribution as the install * Data available with Protect360 Premium plan:   * With corrected attribution in AppsFlyer dashboards and reports as a regular IAE   * With blocked media source in the Protect360 IAE dashboard and Protect360 blocked IAE raw data report |
| Mark installs as invalid and don't attribute them | * Selected when installs that are invalid based on the rule’s conditions are considered fake. * The install is not attributed at all (neither as non-organic nor organic) | * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Blocked * Data available with Protect360 Premium plan in Protect360 IAE dashboard and blocked IAE raw data report |
| **In-app events** | Block attribution | * Selected when in-app events that are invalid based on the rule’s conditions are considered fake. | * With Protect360 Premium plan:   * [Protect360 IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard)   * Protect360 in-app events raw data report * Without Protect360 Premium plan: N/A | * Data available with Protect360 Premium plan in Protect360 [IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard) and blocked in-app events raw data report |
| Remove from AppsFlyer entirely | * Recommended for use when there are in-app events that you don't need any data for. * AppsFlyer does not record these events at all. |  |  |

``
``Ad networks and agencies can only view data if the advertiser gives them the required `[```permissions](/docs/raw-data-reporting-overview#protect360-fraud-and-validation-rules)``.

````When an install attribution is blocked or attributed to a valid media source in real-time, a rejected postback is instantly sent to the blocked ad network, to streamline your reconciliation flow. When attribution is blocked and corrected to the last valid media source, a postback is also sent to the last valid ad network.
``
``When an in-app event attribution is blocked, a rejection postback is instantly sent to the blocked ad network.`<br/>```Note:
``A postback is only sent if the ad network set to receive it is integrated with AppsFlyer to receive postbacks.
``Postbacks and rejected postbacks reports are available on the export page.
``Learn more about `[`postbacks](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration) and `[`rejected postbacks](/docs/rejected-attribution-postbacks-to-integrated-partners).

``
``Install and IAE attribution blocking, only affects how and where data is reported in AppsFlyer. They do not prevent app usage by your end-users.``If needed, you can use the `[`blocked install and blocked IAE raw data reports](/docs/protect360-raw-data-reports) (available via export, pull API, and data locker), to get the list of app users to be disabled.

``
``Blocked installs/IAE reports and rejected postbacks contain the name of the rules that blocked the installs/IAE under the block reason. See the `[```multiple rules](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules)`` section if there is more than one rule.``When installs/in-app events are blocked by the Protect360 anti-fraud engine, even if there is also a validation rule, the Protect360 reasons are displayed.

``Rules can result in reporting discrepancies between AppsFlyer and SRNs like `[`Meta ads](/docs/meta-ads-discrepancies) and `[`Google Adwords](/docs/google-ads-adwords-faq-and-discrepancies) as they deploy their own logic to validate installs.

</Accordion>
<Accordion title="Multiple rules">

``

````Multiple validation rules can run on the same install/IAE. This happens when the install meets the conditions of multiple rules.
````The install/IAE is classified as invalid when it does not comply with the conditions of any of the rules separately.
``
``In raw data reports and rejected postbacks, the block reason value`` field contains the names of all the rules that classify the install or in-app event as invalid.

````Multiple rules for the same install are sequenced to run in the following order, based on the block types of the rules:

``

| Rule/block types | Order |
| --- | --- |
| Block installs | Random |
| Block attribution | Random |
| Block in-app event | Random |
| Remove from AppsFlyer entirely and anything else | Removed from AppsFlyer. Other rules are ignored. |
| Block installs and block attribution | 1. Block install rules (in random order)<br />2. Block attribution rules (in random order) |
| Block installs and block attribution with Protect360 engine and validation rules | 1. Block installs from Protect360 engine<br />2. Block install from validation rules<br />3. Block attribution from Protect360 engine<br />4. Block attribution from validation rules |
| Block in-app events with Protect360 engine and validation rules | 1. Block IAE from Protect360 engine<br />2. Block IAE from validation rules |

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
| General details | * **Rule name -** Enter a name for the new rule.<br />* **Rule type -** Select the rule type, **Real time**, or **Post attribution**.<br />* **Events** - Select the event type for which the rule is applied, **Installs** or **In-app events**.<br />* **App selection -** Select **Selected apps**, or **All apps.**<br />  * If **Selected apps** is selected:  <br />    **Select apps -** Select the apps for which the rule is applied: A single app, multiple apps, or all apps in the account.<br />  * If **All apps** is selected:  <br />    Option to check **Include future apps -**This allows future apps to be included in this rule.<br /><br />The selections affect the options available in the following sections (agency, media source, campaign, etc.)<br /><br />CALLSTART::Note::<br /><br />#### Note<br /><br />App version must only contain numbers. For example 2.2.1<br /><br />Note:<br /><br />Numeric app versions (for example, 2.2.1) supports all operators (equals, greater than, lower than, etc.).<br /><br />If the app version is custom text (for example, version123 or our\_latest\_version), only the "equals" or "doesn't equal" operators work; "greater than" or "lower than" won't apply.<br /><br />CALLEND:: |
| Traffic sources | Traffic source for which the rule is applied. [See also Protect360 sources](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) |
| Conditions | Choose whether you want to block installs/in-app events that "Match" or "Don't match" the defined conditions. <br /><br />* **Match conditions -** Attribution will be blocked for installs/in-app events that match the defined conditions, and the action you select below will apply to all of these.<br />* **Do not match conditions -** Attribution will be blocked for installs/in-app events that don’t match the following conditions, and the action you select below will apply to all the rest.<br /><br />See also Protect360 conditions for [installs](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions) and [in-app events](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions). |
| Actions | For installs, select what to do with the installs meeting the specified conditions:<br /><br />* **Mark installs as invalid and don’t attribute them**. Installs won’t appear in AppsFlyer dashboards except Protect360 and reports.<br />* **Block attribution and correct to last valid media source**. If no valid media source is identified, the install is considered organic.<br /><br />For in-app events, select what to do with the installs meeting the specified conditions:<br /><br />* **Block attribution, but show in Protect360 data**. Events aren’t attributed but show in the Protect360 dashboard and raw data.<br />* **Remove from AppsFlyer**. Events will not show in the AppsFlyer platform at all.<br /><br />See [Outcomes](/docs/implement-validation-rules-to-prevent-fraud#outcomes) for more information. |

## Validation rule examples
<Accordion title="Install sources">

``
The Sources section is where you define the traffic sources of the installs the rule applies to.
There are three primary options: 

``````All traffic: Includes both organic and non-organic installs. Source information is unavailable for organic installs. This option includes all media sources, including those added in the future.`<br/>```Example: Apply a rule to all traffic with app version lower than X.
``````All traffic of Non-organic: Applies to all agency and non-agency non-organic traffic sources, including new sources added later.`<br/>```Example: Block non-organic traffic from a specific geo where you don’t run UA or retargeting campaigns.
``````Selected traffic of Non-organic: Applies the rule to specific agencies or media sources only. You must manually select or add media sources when editing the rule.`<br/>```Example: Block installs from a specific media source if the CTIT is longer than X days.

Additional source options are available for Protect360 customers for `[`installs](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) and `[`in-app events](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions). 
``

| Field | Operator | Value | Remarks |
| --- | --- | --- | --- |
| Agency | * In | * Agency and non-agency traffic * Non-agency traffic * Transparent agencies (menu) | Transparent agencies:   * These are agencies that specify their media sources. * Agencies that are transparent for only some of your selected apps, display in the non-transparent agencies menu. * All agencies are required to share their media sources.Agencies that share media sources for only some of your selected apps appear in the Transparent agencies menu. |
| Media source | * In list * Not in list * Equals * Doesn't equal * Contains * Doesn't contain * Starts with * Ends with * Matches regular expression | * Search for desired value. * Select from menu. * Free text (for values that don’t exist in your search results). | * Menu is based on:   * Selected apps and agencies.   * Traffic of the past 30 days, ordered by traffic volume. * Free text must be typed exactly as it appears in raw data. |
| Campaign | * In list * Not in list * Equals * Doesn't equal * Contains * Doesn't contain * Starts with * Ends with * Is empty * Isn't empty * Matches regular expression | * Search for desired value. * Select value from menu. * Free text (for values that don’t exist in your search results). |
| Campaign ID | * Free text only. * Possible to add multiple values separated by spaces. |
| Ad ID |
| Ad set ID |
| Ad set name |

</Accordion>
<Accordion title="Install conditions">

``
The Conditions section is where you define the conditions that determine when install attributions are blocked, or attributed to the last valid source. 
You can add multiple conditions, and groups of conditions to every rule.
Conditions are defined as per the conditions, operators, and values outlined in the table that follows.
``Bulk upload
When selecting the operators In list or not in list inside of conditions that support it, you have the option to bulk upload a CSV file when adding new items.
To do this:

``Select a condition with an In list or not in list operator.
``Select In list or not in list from the operator dropdown list.
``Select Upload CSV file from the Add new items box. 

Note: The CSV file can contain up to 17K values.
 
Additional condition options are available for Protect360 customers, for `[`installs](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions) and `[`in-app events](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions). 
``

| Condition | Operator | Value | Remarks |
| --- | --- | --- | --- |
| Campaign | * Equals * Doesn't equal * Doesn't contain * Contains * Starts with * Ends with * In list * Not in list * Matches regular expression * Is empty * Isn't empty | * Search for desired value. * Select value from menu. * Free text (for values that don’t exist in your search results). | * Menu is based on:   * Selected apps and agencies.   * Traffic of the past 30 days, ordered by traffic frequency. * Free text must be typed exactly as it appears in raw data. |
| Campaign ID | * Free text only. * Possible to add multiple values separated by spaces. |
| Ad ID |
| Ad set ID |
| Ad set name |
| Device type |
| Geo | * In list * Not in list * Equals * Doesn't equal | * Search required value (based on country name, country code, state, or city). * Select value from menu. |
| Platform | Select value from menu. |
| Currency | Currency only. Possible values:  USD, NZD, SGD, IMP, ANG, MNT, BIF, BBD, HUF, ERN, AZN, AOA, PYG, MYR, GYD, VUV, SLL', FKP, DJF, GNF, LVL, MMK, MRO, RSD, CLF, XDR, ZAR, TND, PHP, KGS, XPD, RON, RUB, KMF, SCR, GIP, TRY, JEP, UYU, XCD, FJD, GHS, MVR, AWG, UGX, TOP, CVE, MKD, COP, CUC, GTQ, KZT, MXN, MGA, AUD, BDT, ISK, KRW, DZD, GGP, OMR, ZMW, MOP, CUP, JPY, SHP, LSL, ETB, BWP, MAD, AED, NGN, BRL, GEL, IDR, EUR, GBP, WST, XAF, SZL, XOF, SEK, UZS, KES, KYD, ILS, KWD, NPR, BZD, QAR, UAH, BTN, HTG, DKK, VND, SBD, JMD, IQD, LBP, XPT, HRK, HKD, JOD, PAB, CDF, VEF, XAU, BAM, CNY, SOS, XPF, GMD, DOP, XAG, KPW, BOB, BHD, BYN, BYR, LRD, BGN, AMD, CZK, CAD, LAK, EEK, MTL, PLN, LKR, BTC, MWK, LTL, ZMK, PGK, YER, PEN, KHR, RWF, BSD, AFN, ZWL, LYD, TMT, HNL, TWD, IRR, MUR, THB, ALL, TJS, SDG, BMD, CRC, NOK, SRD, MZN, CLP, STD, SYP, TZS, EGP, ARS, MDL, INR, SAR, PKR, TTD, NIO, BND, NAD, SVC, CHF |
| Revenue | * Lower then * Lower than or equals * Greater than * Greater than or equals * Is between * Equals * Doesn't equal | * Free text only. |
| OS version | * Lower than * Lower than or equals * Greater than * Greater than or equals * Equals * Doesn't equal * Is between * In list * Not in list * Is empty * Isn’t empty | * Search for desired value. * Select from menu. * Free text (for values that don’t exist in your search results). |
| App version | * Lower than * Lower than or equals * Greater than * Greater than or equals * Equals * Doesn't equal * Is Between * In list * Not in list * Not in last * Not in last (major) * Is empty * Isn’t empty | * Search for desired value. * Select value from menu. * Free text (for values that don’t exist in your search results). | * Menu is based on traffic of the past 30 days, ordered by traffic frequency. * Free text must be typed exactly as it appears in raw data. * For "Not in last," if you have more than one series of versions, select "Not in last (major)". [Learn more](/docs/implement-validation-rules-to-prevent-fraud#how-do-the-not-in-last-conditions-work) |
| Lookback days | * Lower than * Greater than or equals * Is between | * Free text: A single numeric value. | * Refers to the impression/click lookback window in days. * Ensures you don’t pay for installs with an attribution link that was modified to allow a longer attribution period. * Does not replace the configuration of the lookback window in your attribution link. * [Recommended] Use in combination with the attribution touch type condition ([available with Protect360](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions)) |
| Is preinstalled | * Yes * No | * No value (operator is the value) | * Validates all types of preinstalls:   * Factory preinstalls, meaning an app that comes on the device as part of the OS.   * Offered preinstalls, meaning an app promoted and offered to users as soon as the device is initialized. This is done by media sources designated for preinstalls. * For installs with multiple clicks/ sources, this condition validates whether one of the sources is a preinstall. |
| Is deeplink | An empty deep link field in raw data is considered to be Is deeplink = No |

> 📘 **Note**
>
> ``Note
> Organic installs have no associated campaign or media source, so fields like Campaign and Ad set name are always null for them, not empty strings. A rule that uses Match conditions with an Is empty operator on these fields won't match organic installs, so it won't block them.
> To also catch organic traffic, configure the rule with Don't match conditions instead, combining your conditions with Or, using Isn't empty on the same fields (for example, Campaign isn't empty Or Ad set name isn't empty, plus any other conditions the rule needs). Inverting the logic this way lets the rule match null values along with empty strings.

</Accordion>
<Accordion title="In-app event sources">

``
``When In-app events is selected in the Events section, then in addition to the `[```regular source options](/docs/implement-validation-rules-to-prevent-fraud#install-sources)``, customers have another source option to define which in-app events their rule applies to. 
``The source is defined as per the field, operators, and values outlined in the table that follows.
``Note: All other in-app events sources are based on the source of the install the IAE is associated with (for example, agency, media source, campaign, campaign ID, site ID, etc.).
``

| Field | Operator | Value | Remarks |
| --- | --- | --- | --- |
| Event name | * In list<br />* Not in list<br />* Equals<br />* Doesn’t equal<br />* Contains<br />* Doesn’t contain<br />* Starts with<br />* Ends with<br />* Is empty<br />* Isn’t empty<br />* Matches regular expression | * Search for desired value.<br />* Select value from menu.<br />* Free text (for values that don’t exist in your search results). | * Free text must be typed exactly as it appears in raw data. |

</Accordion>
<Accordion title="In-app event conditions">

``
``When In-app events is selected in the Events section, customers have additional condition options to define which in-app events their rule applies to. These conditions can be mixed and matched with any of the non-Protect360 conditions `[```listed previously](/docs/implement-validation-rules-to-prevent-fraud#install-conditions)``.
Protect360 conditions are defined as per the conditions, operators, and values outlined in the table that follows.
``

| Condition | Operator | Value | Remarks |
| --- | --- | --- | --- |
| Event name | * In list<br />* Not in list<br />* Equals<br />* Doesn’t equal<br />* Contains<br />* Doesn’t contain<br />* Starts with<br />* Ends with<br />* Is empty<br />* Isn’t empty<br />* Matches regular expression | * Search for desired value.<br />* Select value from menu.<br />* Free text (for values that don’t exist in your search results). | * Free text must be typed exactly as it appears in raw data. |
| App version | * Lower than<br />* Lower than or equals<br />* Greater than<br />* Greater than or equals<br />* Equals<br />* Doesn't equal<br />* Is Between<br />* In list<br />* Not in list<br />* Not in last<br />* Not in last (major)<br />* Is empty<br />* Isn’t empty | * Search for desired value.<br />* Select value from menu.<br />* Free text (for values that don’t exist in your search results). | * Menu is based on traffic of the past 30 days, ordered by traffic frequency.<br />* Free text must be typed exactly as it appears in raw data.<br />* For "Not in last," if you have more than one series of versions, select "Not in last (major)". [Learn more](/docs/implement-validation-rules-to-prevent-fraud#how-do-the-not-in-last-conditions-work) |

> 📘 **Note**
>
> ``Note
> Event name conditions are not case sensitive. All event names are automatically converted to lowercase before evaluation. For example, if you enter Submit Form, the system treats it as submit form.

</Accordion>
<Accordion title="Protect360 install and in-app event sources">

``
``In addition to the `[```regular source options](/docs/implement-validation-rules-to-prevent-fraud#install-sources)``, Protect360 customers have another source option to define which installs their rule applies to. The source is defined as per the field, operators, and values outlined in the table that follows.
``

| Field | Operator | Value | Remarks |
| --- | --- | --- | --- |
| Site ID | * In list<br />* Not in list<br />* Equals<br />* Doesn’t equal<br />* Contains<br />* Doesn’t contain<br />* Starts with<br />* Ends with<br />* Is empty<br />* Isn’t empty<br />* Matches regular expression | * Free text only.<br />* Possible to add multiple values separated by spaces. | * Free text must be typed exactly as it appears in raw data. |

</Accordion>
<Accordion title="Protect360 install conditions">

``
``Protect360 customers have an additional set of conditions to validate their installs. These conditions can be mixed and matched with any of the non-Protect360 conditions `[```listed previously](/docs/implement-validation-rules-to-prevent-fraud#install-conditions)``.
Protect360 conditions are defined as per the conditions, operators, and values outlined in the table that follows.
``

|  | Block type | Description | Where install data can be viewed | In-app events that follow |
| --- | --- | --- | --- | --- |
| **Installs** | Block attribution and correct to last valid media source | * Selected when you consider the install real, but your conditions determine which sources should or shouldn’t be attributed for it. * Attribution is corrected, and the install is attributed to the last valid media source. * If no valid media source is identified, the install is marked as organic. | * AppsFlyer dashboards and raw data reports as a regular install (attributed to the last valid media source) * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Has the same corrected attribution as the install * Data available with Protect360 Premium plan:   * With corrected attribution in AppsFlyer dashboards and reports as a regular IAE   * With blocked media source in the Protect360 IAE dashboard and Protect360 blocked IAE raw data report |
| Mark installs as invalid and don't attribute them | * Selected when installs that are invalid based on the rule’s conditions are considered fake. * The install is not attributed at all (neither as non-organic nor organic) | * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Blocked * Data available with Protect360 Premium plan in Protect360 IAE dashboard and blocked IAE raw data report |
| **In-app events** | Block attribution | * Selected when in-app events that are invalid based on the rule’s conditions are considered fake. | * With Protect360 Premium plan:   * [Protect360 IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard)   * Protect360 in-app events raw data report * Without Protect360 Premium plan: N/A | * Data available with Protect360 Premium plan in Protect360 [IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard) and blocked in-app events raw data report |
| Remove from AppsFlyer entirely | * Recommended for use when there are in-app events that you don't need any data for. * AppsFlyer does not record these events at all. |  |  |

0

</Accordion>
<Accordion title="Protect360 in-app event conditions">

``
``When In-app events is selected in the Events section, Protect360 customers have additional condition options to define which in-app events their rule applies to. These conditions can be mixed and matched with any of the non-Protect360 conditions `[```listed previously](/docs/implement-validation-rules-to-prevent-fraud#install-conditions)``.
Protect360 conditions are defined as per the conditions, operators, and values outlined in the table that follows.
``

|  | Block type | Description | Where install data can be viewed | In-app events that follow |
| --- | --- | --- | --- | --- |
| **Installs** | Block attribution and correct to last valid media source | * Selected when you consider the install real, but your conditions determine which sources should or shouldn’t be attributed for it. * Attribution is corrected, and the install is attributed to the last valid media source. * If no valid media source is identified, the install is marked as organic. | * AppsFlyer dashboards and raw data reports as a regular install (attributed to the last valid media source) * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Has the same corrected attribution as the install * Data available with Protect360 Premium plan:   * With corrected attribution in AppsFlyer dashboards and reports as a regular IAE   * With blocked media source in the Protect360 IAE dashboard and Protect360 blocked IAE raw data report |
| Mark installs as invalid and don't attribute them | * Selected when installs that are invalid based on the rule’s conditions are considered fake. * The install is not attributed at all (neither as non-organic nor organic) | * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Blocked * Data available with Protect360 Premium plan in Protect360 IAE dashboard and blocked IAE raw data report |
| **In-app events** | Block attribution | * Selected when in-app events that are invalid based on the rule’s conditions are considered fake. | * With Protect360 Premium plan:   * [Protect360 IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard)   * Protect360 in-app events raw data report * Without Protect360 Premium plan: N/A | * Data available with Protect360 Premium plan in Protect360 [IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard) and blocked in-app events raw data report |
| Remove from AppsFlyer entirely | * Recommended for use when there are in-app events that you don't need any data for. * AppsFlyer does not record these events at all. |  |  |

1

</Accordion>
<Accordion title="Logic between conditions and condition groups">

``
``If you add multiple conditions or condition groups to a rule, select the logical relation between them using either: 

````And: Meaning the install complies with all the defined conditions.
````Or: Meaning the install complies with at least one of the defined conditions.

``For example, if you want to validate installs based on both platform and OS, you must select and. That way, the defined platform must always accompany the defined OS. If you want to validate installs based on either platform or OS, you must select or.

</Accordion>

## Additional features
<Accordion title="View rule list">

``
To view all the rules created in your account:

``
``In AppsFlyer, go to Settings`` &gt; Validation Rules.`<br/>```The Validation Rules window opens, with the list of validation rules.

``
``Select your preferred table view using the List view/Details view`` toggle.

``
``Filter the rules in the list using the search and the filter options.
``You can search by rule name, source, condition name, and value.
``For example, type 7 to find all rules defined for an OS version that contains 7. (e.g.: “2.7.4”, “7.1”, etc.). Or type Canada to find rules defined with Canada in the Geo condition. 

``The Validation Rules table shows 25 rules per page by default. You can change the number of rules shown per page to 10, 25, or 50.
``Search and filters apply to the full rule set, regardless of the page you’re viewing.

</Accordion>
<Accordion title="Add rule">

``
To set up a new rule:

``
``In AppsFlyer, go to Settings`` &gt; Validation Rules.`<br/>```The Validation Rules window opens.

``
``Click Add Rule.`<br/>```The Add new rule window opens.

``Insert a rule name. Use a unique name that:
``accurately describes the rule.
``is not offensive to ad networks, as it displays in the blocked installs report, as well as in the rejected postbacks to ad networks.

``Complete the `[`rule builder sections](/docs/implement-validation-rules-to-prevent-fraud#rule-builder).
``[Optional] Add conditions and/or condition groups, as required. Make sure to s``elect the relevant `[```logic between conditions/condition groups](/docs/implement-validation-rules-to-prevent-fraud#logic-between-conditions-and-condition-groups)``.

``
``[Optional] Click Estimate traffic impact to `[`see how your rule will affect traffic](/docs/implement-validation-rules-to-prevent-fraud#view-validation-rule-impact).
``Click Save.

> 📘 **Note**
>
> ``Note
> App version must only contain numbers. For example 2.2.1
> Note: 
> Numeric app versions (for example, 2.2.1) supports all operators (equals, greater than, lower than, etc.).
> If the app version is custom text (for example, version123 or our_latest_version), only the "equals" or "doesn't equal" operators work; "greater than" or "lower than" won't apply.

</Accordion>
<Accordion title="VR tagged mode">

``
Use Tagged mode to test validation rules on live traffic before blocking attribution. Tagged rules flag installs and in-app events that match the rule conditions, but attribution isn’t affected.
``Tagged mode supports installs and in-app events only.
``Use Tagged mode to:
``
``Test complex rules on live traffic before blocking attribution.
``Identify possible false positives.
``Review why a rule would have triggered before you enforce the rule.
``Understand the real traffic impact before changing the rule status to Implemented.

``Best practice: Create the rule in Tagged mode first, review the flagged traffic in Data Locker, and change the rule status to Implemented when you’re confident in the rule accuracy. Aim to complete this review in less than 7 days to maintain active protection.
``How Tagged mode works
``When you create or edit a validation rule, select the Detection status in the Rule outcome section.
``
``Tagged: The rule flags matching data for reporting and analysis. Attribution isn’t affected.
``Implemented: The rule actively blocks attribution according to the selected rule outcome.

``Note: Tagged mode applies only to live traffic from the moment the rule is saved. It doesn’t tag historical data.
``Rule outcome configuration
``The Rule outcome section, formerly Action, defines how AppsFlyer handles traffic that matches the rule conditions. It also provides a high-level summary of the rule configuration so you can verify the expected impact before saving the rule.
``

|  | Block type | Description | Where install data can be viewed | In-app events that follow |
| --- | --- | --- | --- | --- |
| **Installs** | Block attribution and correct to last valid media source | * Selected when you consider the install real, but your conditions determine which sources should or shouldn’t be attributed for it. * Attribution is corrected, and the install is attributed to the last valid media source. * If no valid media source is identified, the install is marked as organic. | * AppsFlyer dashboards and raw data reports as a regular install (attributed to the last valid media source) * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Has the same corrected attribution as the install * Data available with Protect360 Premium plan:   * With corrected attribution in AppsFlyer dashboards and reports as a regular IAE   * With blocked media source in the Protect360 IAE dashboard and Protect360 blocked IAE raw data report |
| Mark installs as invalid and don't attribute them | * Selected when installs that are invalid based on the rule’s conditions are considered fake. * The install is not attributed at all (neither as non-organic nor organic) | * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Blocked * Data available with Protect360 Premium plan in Protect360 IAE dashboard and blocked IAE raw data report |
| **In-app events** | Block attribution | * Selected when in-app events that are invalid based on the rule’s conditions are considered fake. | * With Protect360 Premium plan:   * [Protect360 IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard)   * Protect360 in-app events raw data report * Without Protect360 Premium plan: N/A | * Data available with Protect360 Premium plan in Protect360 [IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard) and blocked in-app events raw data report |
| Remove from AppsFlyer entirely | * Recommended for use when there are in-app events that you don't need any data for. * AppsFlyer does not record these events at all. |  |  |

2``What to expect when configuring a rule
``As you configure the rule, a dynamic info panel shows the expected rule behavior based on:
``
``Match or Do not match logic
``App selection
``Detection status

``When Detection status is set to Tagged, the rule acts as a discovery tool. AppsFlyer shows a notification confirming that matching data is flagged in export reports, including Data Locker, but isn’t blocked from attribution.
``When Detection status is set to Implemented, installs or in-app events that match the rule criteria are blocked from attribution or reattributed according to the selected rule outcome. The info panel summarizes the active outcome before you save the rule.
``Example: Match logic
``For detected installs that meet the rule conditions for the selected apps, the info panel can indicate that the installs are:
``
``Blocked from attribution or detected as post-attribution.
``Reattributed to the last valid non-organic or organic source.
``Visible in export reports.

``Example: Do not match logic
``For detected installs that don’t meet the rule conditions for the selected apps, including future apps, the info panel can indicate that the installs are:
``
``Blocked from attribution or detected as post-attribution.
``Marked as fraud without attribution correction.
``Visible in export reports.

``All other installs that meet the rule conditions within these apps aren’t blocked.
``Set a rule to Tagged mode
``To test a validation rule with Tagged mode:
``
``In AppsFlyer, go to Settings &gt; Validation Rules.
``Select an existing rule or click Add Rule.
``Complete the rule details, traffic sources, and conditions.
``In the Rule outcome section, set Detection status to Tagged.
``Click Save.

``After the rule is saved, AppsFlyer flags matching live traffic for reporting and analysis. Attribution continues as usual.
``Analyze tagged data
``Tagged validation rule data isn’t visible in the Protect360 dashboard or Fraud Protection Suite.
``To analyze the impact of tagged rules, use Data Locker or raw data export reports. Tagged data is available for installs and in-app events, so you can compare tagged traffic with valid attributions.
``Tagged data mapping:
``

|  | Block type | Description | Where install data can be viewed | In-app events that follow |
| --- | --- | --- | --- | --- |
| **Installs** | Block attribution and correct to last valid media source | * Selected when you consider the install real, but your conditions determine which sources should or shouldn’t be attributed for it. * Attribution is corrected, and the install is attributed to the last valid media source. * If no valid media source is identified, the install is marked as organic. | * AppsFlyer dashboards and raw data reports as a regular install (attributed to the last valid media source) * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Has the same corrected attribution as the install * Data available with Protect360 Premium plan:   * With corrected attribution in AppsFlyer dashboards and reports as a regular IAE   * With blocked media source in the Protect360 IAE dashboard and Protect360 blocked IAE raw data report |
| Mark installs as invalid and don't attribute them | * Selected when installs that are invalid based on the rule’s conditions are considered fake. * The install is not attributed at all (neither as non-organic nor organic) | * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Blocked * Data available with Protect360 Premium plan in Protect360 IAE dashboard and blocked IAE raw data report |
| **In-app events** | Block attribution | * Selected when in-app events that are invalid based on the rule’s conditions are considered fake. | * With Protect360 Premium plan:   * [Protect360 IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard)   * Protect360 in-app events raw data report * Without Protect360 Premium plan: N/A | * Data available with Protect360 Premium plan in Protect360 [IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard) and blocked in-app events raw data report |
| Remove from AppsFlyer entirely | * Recommended for use when there are in-app events that you don't need any data for. * AppsFlyer does not record these events at all. |  |  |

3````Tagged data fields
``Use the following columns in Data Locker and Raw data exports to identify traffic flagged by validation rules:
``

|  | Block type | Description | Where install data can be viewed | In-app events that follow |
| --- | --- | --- | --- | --- |
| **Installs** | Block attribution and correct to last valid media source | * Selected when you consider the install real, but your conditions determine which sources should or shouldn’t be attributed for it. * Attribution is corrected, and the install is attributed to the last valid media source. * If no valid media source is identified, the install is marked as organic. | * AppsFlyer dashboards and raw data reports as a regular install (attributed to the last valid media source) * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Has the same corrected attribution as the install * Data available with Protect360 Premium plan:   * With corrected attribution in AppsFlyer dashboards and reports as a regular IAE   * With blocked media source in the Protect360 IAE dashboard and Protect360 blocked IAE raw data report |
| Mark installs as invalid and don't attribute them | * Selected when installs that are invalid based on the rule’s conditions are considered fake. * The install is not attributed at all (neither as non-organic nor organic) | * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Blocked * Data available with Protect360 Premium plan in Protect360 IAE dashboard and blocked IAE raw data report |
| **In-app events** | Block attribution | * Selected when in-app events that are invalid based on the rule’s conditions are considered fake. | * With Protect360 Premium plan:   * [Protect360 IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard)   * Protect360 in-app events raw data report * Without Protect360 Premium plan: N/A | * Data available with Protect360 Premium plan in Protect360 [IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard) and blocked in-app events raw data report |
| Remove from AppsFlyer entirely | * Recommended for use when there are in-app events that you don't need any data for. * AppsFlyer does not record these events at all. |  |  |

4``Change a tagged rule to Implemented
``After you review the tagged data and confirm that the rule works as expected, change the rule status to Implemented.
``To change a rule from Tagged to Implemented:
``
``In AppsFlyer, go to Settings &gt; Validation Rules.
``Select the rule.
``In the Rule outcome section, set Detection status to Implemented.
``Click Save.

``From the moment the rule is saved, AppsFlyer actively blocks matching traffic according to the selected rule outcome.

</Accordion>
<Accordion title="Edit or delete a rule">

``
To edit, delete, enable, or disable a rule:
``In the `[`rule list](/docs/implement-validation-rules-to-prevent-fraud), select the action you want to perform for a specific rule.
``Under Active: enable or disable the rule.
``Under Action: edit or delete the rule.

</Accordion>

## FAQ
<Accordion title="What is a 'regular expression'?">

``
A regular expression pattern is composed of characters for which you want to find a match. Simple patterns are constructed with characters for which you want to find a direct match. When the search for a match requires something more than a direct match, you can include special characters in the pattern.
Examples:
``

|  | Block type | Description | Where install data can be viewed | In-app events that follow |
| --- | --- | --- | --- | --- |
| **Installs** | Block attribution and correct to last valid media source | * Selected when you consider the install real, but your conditions determine which sources should or shouldn’t be attributed for it. * Attribution is corrected, and the install is attributed to the last valid media source. * If no valid media source is identified, the install is marked as organic. | * AppsFlyer dashboards and raw data reports as a regular install (attributed to the last valid media source) * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Has the same corrected attribution as the install * Data available with Protect360 Premium plan:   * With corrected attribution in AppsFlyer dashboards and reports as a regular IAE   * With blocked media source in the Protect360 IAE dashboard and Protect360 blocked IAE raw data report |
| Mark installs as invalid and don't attribute them | * Selected when installs that are invalid based on the rule’s conditions are considered fake. * The install is not attributed at all (neither as non-organic nor organic) | * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Blocked * Data available with Protect360 Premium plan in Protect360 IAE dashboard and blocked IAE raw data report |
| **In-app events** | Block attribution | * Selected when in-app events that are invalid based on the rule’s conditions are considered fake. | * With Protect360 Premium plan:   * [Protect360 IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard)   * Protect360 in-app events raw data report * Without Protect360 Premium plan: N/A | * Data available with Protect360 Premium plan in Protect360 [IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard) and blocked in-app events raw data report |
| Remove from AppsFlyer entirely | * Recommended for use when there are in-app events that you don't need any data for. * AppsFlyer does not record these events at all. |  |  |

5

</Accordion>
<Accordion title="Why doesn't the source or condition display as a suggested value when I search for it?">

``
``There are two possible reasons:

````Make sure the relevant app/s are selected. If the app isn't selected, values don't display in search results.
````Results display only if the value you are searching for appeared in your traffic during the past 30 days. Additionally, there is a lag of up to 1 day between when the conversion occurs, and when the source or condition displays as a menu option.

``If the value does not appear as a search result, you can type the value as free text and press the Enter key on your keyboard.

</Accordion>
<Accordion title="Why do my media source options only include Meta ads and X Ads?">

````The Media Sources field options are affected by your Agency selection.

</Accordion>
<Accordion title="Is it necessary to have 'and/or' both within specific conditions and between condition groups?">

``
It depends on your use case. Sometimes either option achieves the same results. Other times, both options are necessary.
For example, if in USA you support installs only on OS V10 or later, but in Brazil, you support from V7 and later, you'll need a rule like:
```{[Geo = US] and [OS version = 10]} OR {[Geo = Brazil] and [OS version = 7]}`

</Accordion>
<Accordion title="Do validation rules block clicks?">

``No. Validation rules can block installs, block attribution to an install’s sources (that prevents the media source of a click/impression from receiving attribution), or block in-app events. However, none of these options blocks the actual click, and click KPIs are not affected by executing validation rules.

</Accordion>
<Accordion title="Looking at the raw data, I see that installs I expected to be blocked by validation rules have a different block reason than my rule name. Why is that?">

``This means the block was due to the `[`Protect360 engine](/docs/protect360-raw-data-reports#blocked-reasons) and not a validation rule. See also `[`multiple rules](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules).

</Accordion>
<Accordion title="Do existing rules automatically apply for newly-integrated agency traffic?">

``
This depends on your Source settings, as described in the table below.
If the rule is not automatically applied, you must edit the rule:
``Change the Agency field to either ``Agency and non-agency traffic, or select the specific agency.

``

|  | Block type | Description | Where install data can be viewed | In-app events that follow |
| --- | --- | --- | --- | --- |
| **Installs** | Block attribution and correct to last valid media source | * Selected when you consider the install real, but your conditions determine which sources should or shouldn’t be attributed for it. * Attribution is corrected, and the install is attributed to the last valid media source. * If no valid media source is identified, the install is marked as organic. | * AppsFlyer dashboards and raw data reports as a regular install (attributed to the last valid media source) * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Has the same corrected attribution as the install * Data available with Protect360 Premium plan:   * With corrected attribution in AppsFlyer dashboards and reports as a regular IAE   * With blocked media source in the Protect360 IAE dashboard and Protect360 blocked IAE raw data report |
| Mark installs as invalid and don't attribute them | * Selected when installs that are invalid based on the rule’s conditions are considered fake. * The install is not attributed at all (neither as non-organic nor organic) | * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Blocked * Data available with Protect360 Premium plan in Protect360 IAE dashboard and blocked IAE raw data report |
| **In-app events** | Block attribution | * Selected when in-app events that are invalid based on the rule’s conditions are considered fake. | * With Protect360 Premium plan:   * [Protect360 IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard)   * Protect360 in-app events raw data report * Without Protect360 Premium plan: N/A | * Data available with Protect360 Premium plan in Protect360 [IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard) and blocked in-app events raw data report |
| Remove from AppsFlyer entirely | * Recommended for use when there are in-app events that you don't need any data for. * AppsFlyer does not record these events at all. |  |  |

6

</Accordion>
<Accordion title="How do the 'not in last' conditions work?">

``
Use Not in last to allow installs from your most recent app versions and block installs from older versions.

``
Not in last X versions: Allows installs from the last X versions of the selected app, and blocks installs from all earlier versions.`<br/>` 
``
Not in last (major) X versions: Use when your versioning includes multiple major version series (for example, 1.x and 2.x). This condition allows the last X versions within each major series, and blocks earlier versions in each series.

``Example: Not in last
You have these existing app versions:

``1.0.01
``1.0.02
``1.0.03
``2.0.01
``2.0.02
``2.0.03

A rule defined with Not in last 2 versions:

``
Allows: 
``2.0.02
``2.0.03`<br/>` 

``
Blocks: 
``1.0.01
``1.0.02
``1.0.03
``2.0.01

``Example: Not in last (major)
Using the same versions list above, a rule defined with Not in last (major) 2 versions:

``
Allows: 
``1.0.02
``1.0.03
``2.0.02
``2.0.03`<br/>` 

``
Blocks: 
``1.0.01
``2.0.01

``Understand how the condition works with multiple apps
If you select multiple apps in the rule, AppsFlyer evaluates the Not in last condition separately for each app.
For example, if you set Not in last 3 versions and select App A, App B, and App C:

``App A allows its last 3 versions based on App A’s version history.
``App B allows its last 3 versions based on App B’s version history.

App C allows its last 3 versions based on App C’s version history.

</Accordion>
<Accordion title="How do I block attribution for installs or in-app events from impressions?">

``
Use a validation rule when you want to prevent attribution from impression-based engagements and keep attribution only for valid clicks. If no valid click-based media source is found, the install is attributed as organic. This setup can help address attribution scenarios related to install hijacking.
To configure the rule:

``Under Traffic sources, select All non-organic traffic.

``Under Conditions, select Attribution touch type.
``Set the operator to In list.
``Select Impression.

``Under Action, select Block attribution and correct to last valid media source.

Don’t select Mark installs as invalid and don’t attribute them for this use case. That action is intended for installs you consider invalid or fake. If the install is real, but you don’t want to attribute it to impression-based engagement, use Block attribution and correct to last valid media source instead.

</Accordion>
<Accordion title="Does Tagged mode support all condition types?">

``Yes. Tagged mode supports all validation rule operators and fields, including And/Or logic, Geo, OS version, SDK version, and Event value.

</Accordion>
<Accordion title="Will tagged data appear in blocked reports?">

``No. Tagged data isn’t classified as blocked traffic. Tagged traffic maps as Tagged and is considered a subset of valid traffic. It’s visible in valid reports in Data Locker.

</Accordion>
<Accordion title="Where can I view tagged data?">

``
Use Data Locker or raw data export reports to view tagged validation rule data. Tagged installs are available in tagged installs reports, and tagged in-app events are available in tagged in-app events reports.
Tagged data isn’t visible in the Protect360 dashboard or Fraud Protection Suite.

</Accordion>
<Accordion title="Can I change a rule from Tagged to Implemented at any time?">

``Yes. After you review the export data and confirm that the rule works as expected, edit the rule, set Detection status to Implemented, and save the rule. From that moment, the rule actively blocks matching traffic according to the selected rule outcome.

</Accordion>
<Accordion title="Is there a limit to how many rules can be set to Tagged?">

``Tagged mode is available for Premium customers. There is no strict limit to the number of rules that can be set to Tagged. As a best practice, review tagged rules and change them to Implemented when you’re confident in the rule accuracy.

</Accordion>
<Accordion title="Traits and limitations">

````

|  | Block type | Description | Where install data can be viewed | In-app events that follow |
| --- | --- | --- | --- | --- |
| **Installs** | Block attribution and correct to last valid media source | * Selected when you consider the install real, but your conditions determine which sources should or shouldn’t be attributed for it. * Attribution is corrected, and the install is attributed to the last valid media source. * If no valid media source is identified, the install is marked as organic. | * AppsFlyer dashboards and raw data reports as a regular install (attributed to the last valid media source) * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Has the same corrected attribution as the install * Data available with Protect360 Premium plan:   * With corrected attribution in AppsFlyer dashboards and reports as a regular IAE   * With blocked media source in the Protect360 IAE dashboard and Protect360 blocked IAE raw data report |
| Mark installs as invalid and don't attribute them | * Selected when installs that are invalid based on the rule’s conditions are considered fake. * The install is not attributed at all (neither as non-organic nor organic) | * With Protect360 Premium plan:   * [Protect 360 installs dashboard](/docs/protect360-dashboard#installs-dashboard)   * Protect360 installs raw data report (with the blocked media source) * Without Protect360 Premium plan:   * Protect360 installs raw data report (with the blocked media source) | * Blocked * Data available with Protect360 Premium plan in Protect360 IAE dashboard and blocked IAE raw data report |
| **In-app events** | Block attribution | * Selected when in-app events that are invalid based on the rule’s conditions are considered fake. | * With Protect360 Premium plan:   * [Protect360 IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard)   * Protect360 in-app events raw data report * Without Protect360 Premium plan: N/A | * Data available with Protect360 Premium plan in Protect360 [IAE dashboard](/docs/protect360-dashboard#inapp-events-dashboard) and blocked in-app events raw data report |
| Remove from AppsFlyer entirely | * Recommended for use when there are in-app events that you don't need any data for. * AppsFlyer does not record these events at all. |  |  |

7

</Accordion>