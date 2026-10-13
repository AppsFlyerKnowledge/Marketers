---
title: "In-app event postback configuration"
excerpt: "Measure app engagement and quality of your users, and optimize campaigns using in-app events data."
x-zendesk:
  id: 208439256
  url: https://support.appsflyer.com/hc/en-us/articles/208439256-In-app-event-postback-configuration
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Media source configuration
  section_id: 6551067072785
  position: 3
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [In-App Events, Advertisers, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-04-11T08:47:14Z'
  edited_at: '2026-09-27T06:37:38Z'
---
## Overview

In-app events enable marketers to measure app engagement and user quality from different sources and to build an appropriate user acquisition strategy. Ad networks use in-app event information to optimize campaigns and run cost-per-action/event campaigns. Ad networks receive in-app event data via postbacks, which are sent in real time. [Learn more about rich in-app events](/docs/in-app-events-overview).

## Postback in-app event selection

Marketers can select which in-app events they want to send postbacks to ad networks, using the settings described in this article.

> 📘 **Note**
>
> * In-app events include **rejected events**, meaning in-app events blocked by Protect360 or events found to be non-compliant with target validation rules.
> * If the **In-app event postbacks** section doesn't appear in the **Integration** tab, it means the partner hasn't yet set up in-app event recordings with AppsFlyer during its preliminary configuration. The partner can contact AppsFlyer using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif) to finish the integration.

## In-app event postback window

The in-app event postback window allows marketers who work with networks on a [CPA (cost-per-action)](/docs/appsflyer-knowledge-base-glossary#cpa) basis to configure post-conversion windows after which event postbacks are no longer sent.

For example, if you're charged for events happening within 15 days of a user install, set the window as follows:

![In-app event postback window set to 15 days](https://files.readme.io/6ffcd335b85334015f518895b317d3a5e273f4e00c31e3694c0f95a22ba6d4fb-33379700644497.png)

Postbacks after this period are not sent, and the network is not notified, but AppsFlyer still records the events and attributes them to the network.

The postbacks are always sent based on the **current** window setting. See the following example:

| January 1 | The window is 15 days.<br /><br />A user installs an app. |
| --- | --- |
| January 2 | The window is changed to 10 days. |
| January 14 | The user makes a purchase.<br /><br />The postback isn't sent to the ad network because the event doesn't fall within the current window (10 days). |
| January 15 | The window is changed to 20 days. |
| January 18 | The user makes another purchase.<br /><br />This time the postback is sent, because the event falls within the current window (20 days). |

> 📘 **Note**
>
> When you select the [**All media sources, including organic** setting](#options-for-sending-postbacks), the partner who configured it receives a postback for every conversion event the advertiser receives. This happens even if the advertiser attributed the event to another partner, as long as the event occurred within the postback window that AppsFlyer defines for the partner who configured the setting.

### Default postback window

When starting to set up in-app event postbacks, the default window is automatically set to six months.

> 📘 **Note**
>
> If you started using in-app event postbacks with a specific partner before July 30, 2019, the default window is Lifetime. This means that in-app event postbacks are always sent.

### Who can configure postback windows

The following roles can configure postback windows:

* Marketers
* Agencies, if they're given the **Allow to configure in-app event postbacks** [permissions](/docs/set-up-an-integrated-partner#agency-permissions).  
  **Note:** A marketer and an agency working with the same ad network can configure postback windows separately, based on their contracts with the network.
* Partners, if they're given the **Allow to configure in-app event postbacks** [permissions](/docs/set-up-an-integrated-partner#permissions-tab).

## Event mapping

Each marketer can give a different name to an event of the same type. Such event names might also differ from the partner names.

For example, when a user purchases something through an app, one marketer may name it `purchase`, or a less informative ID, such as `event5`, and a partner may name it `purchase_event`.

To make sure that the marketer's events match the same events as the partners', event names must be mapped.

> 📘 **Note**
>
> Events mapped in the Integration tab for a specific partner apply to both standard and [SKAdNetwork (SKAN) postbacks.](/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners)

### Mapping methods

Each partner decides which of the following methods are to be used for mapping their in-app events:

* [Enter the partner event ID](/docs/in-app-event-postback-configuration#enter-the-partner-event-id)
* [Select the event ID from the list](/docs/in-app-event-postback-configuration#select-an-event-id-from-the-list)
* [Send events as they are (unmapped)](/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped)

> 📘 **Note**
>
> * Not all mapping methods appear for all partners
> * You can [give the partner permission](/docs/in-app-event-postback-configuration#event-mapping-by-ad-networks) to do the mapping itself

<Accordion title="Enter the partner event ID">

* **AppsFlyer event**: From the list of your app events, select an event.
* **mapped to partner event**: In the text field, enter the event ID as received from the partner that corresponds to your app event (AppsFlyer event)

> 📘 **Note**
>
> * Event names are case-sensitive. To avoid discrepancies, make sure you use the correct event name for all media sources and app versions.
> * When typing an event name, you can use underlined spaces (low dashes) before or after the event name. Make sure to use underlined spaces only when the event name being sent from AppsFlyer has the exact same underlined spaces.

![Entering an event ID in the mapped-to-partner-event text field](https://files.readme.io/b9d65d3a6b4c1ab4d3f7e83cc2226af5c5a83e1e83cfbfa3df36d295ae568a45-33379700646545.png)

</Accordion>

<Accordion title="Select an event ID from the list">

* **AppsFlyer event**: From the list of your app events, select an event.
* **mapped to partner event**: From the list of predefined partner events, select the event that corresponds to your app event (AppsFlyer event).

![Selecting a predefined partner event from the event ID dropdown](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

</Accordion>

<Accordion title="Send events as they are (unmapped)">

Some partners prefer to receive unmapped in-app event postbacks, meaning the event names are sent as they're named in your app. It doesn't matter if the event is called `purchase`, `acquisition`, or `event5`.

You can choose which unmapped events to send to the partner:

* **Add manually:** Select specific events.
* **Send all events (excluding uninstalls and sessions)**. This doesn't include uninstalls, sessions (app launches), and the `af_app_opened` event.

> 📘 **Note**
>
> To prevent advertisers from unintentionally sharing too much information with third-party Analytics platforms, we've removed the **Send all events (excludes uninstalls and sessions)** option for these platforms as of March 2019. Analytics platforms configured before this date still retain this setup option.

**To manually add events:**

1. Click **Add event**.
2. Select the postback options:
   * **AppsFlyer event**: From the list of your app events, select an event.
   * **for users from**: Select the [sending option](/docs/in-app-event-postback-configuration#options-for-sending-postbacks) for the event.
   * **including**: Select [which data to include](/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks) in the postback.
3. Repeat this procedure for more events.

![Manually adding unmapped events with sending and data-inclusion options](https://files.readme.io/cc6b2bb1a381d88add035b9f369b0ba68dee8744aa3c2ee2f8f6f054b365a0dd-33379684962705.png)

**To send all events:**

1. Select **Send all events (excludes uninstalls and sessions)**.
2. Select the postback options:  
   * **for users from**: Select the [sending option](/docs/in-app-event-postback-configuration#options-for-sending-postbacks) for all events.
   * **including**: Select [which data to include](/docs/in-app-event-postback-configuration#data-to-include-in-the-postbacks) for all events in the postback.

![Sending all unmapped events without individual event mapping](https://files.readme.io/458ca832d4176ccd306236cf10f211499e841dc9f550558987dff3ee683bd2d1-33379700651665.png)

</Accordion>

For more information on mapping events, see [in-app event postbacks](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration).

### Options for sending postbacks

For each event, you can choose in which case to send the postbacks (within the postback window):

* **This partner only**: Send postbacks only when the event is attributed to this partner, meaning the user who performed it came from this partner.
* **All media sources including organic**: Send postbacks to all media sources for events attributed to any partner and for organic events, meaning when the user who performed it came from any media source. **Note**: When **All media sources including organic** is selected, postbacks for other partners don't contain attribution data.

### Data to include in the postbacks

You can choose which kind of event data to share with the partner in the postback. Select one of the following options:

* **No values & no revenue**: Send just the event itself without any parameters (values or revenue).
* **Values & no revenue**: Send all the parameters **excluding** the revenue value.
* **Values & revenue**: Send all the event parameters, **including** the revenue value (if it exists in the event).
* **Values, revenue & net revenue**: Send all event parameters, including the revenue and net revenue values (if they exist in the event).

> 📘 **Note**
>
> The **Values, revenue & net revenue** option requires an **ROI360 Advanced** subscription and is available only for `af_purchase*` and `af_ars_*` events.

We recommend sharing revenue if you want ad networks to optimize your campaigns and improve campaign results. However, sharing revenue is not mandatory. Make sure to enable revenue sharing only for events that have `af_revenue` or `af_projected_revenue` defined in their event value. Otherwise, ad networks get events with an empty revenue value.

#### Share revenue

In postbacks, `af_revenue` and `af_currency` are written outside of the `event_value` JSON as **monetary** and **currency** and can be sent separately. Example postback structure:

```
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&content_id=(af_content_id)
```

When the **Values, revenue & net revenue** option is selected, `af_net_revenue` can also be written outside of the `event_value` JSON as **net-monetary** and sent separately. Example postback structure:

```
https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&net-monetary=(net-monetary)&content_id=(af_content_id)
```

> 📘 **Note**
>
> When choosing **No values & no revenue** or **Values & no revenue**, the respective parameters are masked with N/A.

> 📘 **Tip**
>
> You can also configure your in-app event postbacks to send net revenue in place of gross revenue in the standard revenue (monetary**)** parameter. To get access to this configuration, contact your Customer Success Manager (CSM).

**Example**

A marketer sends a purchase event with the following `event_value`:

```json
{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_content_type":"category_a"}
```

The table below shows how the parameters are sent:

| Field name | event\_value | monetary | currency | net-monetary |
| --- | --- | --- | --- | --- |
| **No values & no revenue** | N/A | N/A | N/A | N/A |
| **Values & no revenue** | `{"af_currency":"N/A","af_content_id":"1234567","af_revenue":"N/A","af_content_type":"category_a"}&monetary=N/A&content_id=1234567` | N/A | N/A | N/A |
| **Values & revenue** | `{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_content_type":"category_a"}&monetary=50.87&content_id=1234567` | 50.87 | USD | N/A |
| **Values, revenue & net revenue** | `{"af_currency":"USD","af_content_id":"1234567","af_revenue":50.87,"af_net_revenue":35.61,"af_content_type":"category_a"}&monetary=50.87&net-monetary=35.61&content_id=1234567` | 50.87 | USD | 35.61 |

### Conditional in-app event postbacks

Filter in-app event postbacks using multiple conditions that can be mapped to different events. Only events meeting the filter conditions are sent to partners, including self-reporting networks (SRNs) and Analytics partners. Use this feature for:

* Optimizing user segmentation, personalization, and retention
* Minimizing data
* Protecting user privacy

**Example**

A marketer with a gaming app wants to optimize campaigns running through an ad network, but only for users who pass level 10 or level 50, or for users who spend $3 on in-app purchases.

![Example in-app event postback conditions for reaching level 10, level 50, or a $3 purchase](https://files.readme.io/9226101e635b847ca605579aa9d5ae910ccb9869655a622d2db95e50c845e5e1-33379700654737.png)

**This is how conditions for this event are set:**

* When ***level*** equals ***10***, map to *`fb_mobile_level_acheived`*  
  Otherwise (**OR**),
* When ***level*** equals ***50***, map to *`fb_mobile_level_acheived`*  
  Otherwise (**OR**),
* When ***cost*** equals ***3***, map to *`fb_mobile_purchase`*

**To set up conditions for an event:**

1. On the partner integration page, [define and map](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration) the required in-app events to send to the partner.
2. Click the Add condition![Add condition icon](https://files.readme.io/5e8fda784fcb306b07c9dd549abd608bdb23d0028fbeade731039e6e91dd44e4-33379700656401.png) icon of the required event.
3. Enter the condition fields, as they appear in the [event value](/docs/raw-data-reporting-overview#event-values):
   * Property name
   * Value
   * Partner event to map the condition to (using any of these [mapping options](/docs/in-app-event-postback-configuration#mapping-methods))
4. You can add more conditions, just make sure you enter all the fields of the existing condition first.
5. Click **Save integration**.

#### Considerations

When configuring conditions, make sure the following considerations are met for the event to be sent to the partner:

<Accordion title="Condition structure">

* Both the property and the value in the condition must match the data on the event.
* Currently, conditions can only be set to “equal”.
* Complex structures such as arrays are not supported.

</Accordion>

<Accordion title="Multiple conditions for an event">

* The maximum number of conditions per event is 5.
* At least one condition must be met for the postback to be sent, but only one condition is executed.
* Each condition is checked by order of appearance, and the first condition to be met is executed.
* Each condition is mapped separately. The partner event name is changed to **Based on conditions**.
* More than one condition can have the same property or the same value, but no two conditions can have both the same property and value.
* More than one condition can be mapped to the same event.

</Accordion>

> 📘 **Note**
>
> * It's recommended to test this feature with a test app or for minor events to understand its impact on campaign optimization.
> * To see the [postback content](/docs/raw-data-reporting-overview), you can download the raw data postback report.

### Editing multiple events

While mapping events, values in the fields **for users from** and **including** can be edited across multiple events in a single action.

**To edit multiple events:**

1. Select the events to update.
2. Click **Bulk actions.**
3. Select the new setting to apply to all selected events:
   * **for users from** (choose one option only)
     * This partner only
     * All media sources, including organic
   * **including** (choose one option only)
     * No data (default)
     * Values without revenue
     * Values and revenue

![Bulk actions panel for editing the for-users-from and including settings across multiple events](https://files.readme.io/559265d0e12e9e2ef62e0a19c5833465ee758821654877cffa4e75f6ff3f99b9-33379700657169.png)

### Custom events

The list of events available for mapping shows only the events already reported by the SDK or from server-to-server events sent to AppsFlyer. If the event you want to map doesn't appear in the dropdown list, this can happen for the following reasons:

* No user has performed the event yet
* The last time the event occurred was over two weeks ago
* You have a large list of active events

**In either of these cases, to map the event to the partner ID:**

1. From the dropdown list, click **+ Add item**.
2. In the text box, type the name of the event you want to add.
3. Click the checkmark to confirm. The event you've added now appears in the list and you can select it. ![Confirming a new custom event name](https://files.readme.io/cab91e281e863e7bbe0e3a96392552a149f7ccccd41695f2e4579089256e8dd1-33379684971793.jpg)
4. Map the event to the partner identifier.
5. Click **Save Integration** to make sure the mapping is recorded.

> 📘 **Note**
>
> * Adding custom events on the postback page doesn't automatically pull them from your app. Events must be configured in the SDK or S2S for proper functionality. See [how to send events to AppsFlyer](/docs/in-app-events-overview#sending-events).
> * When a custom event is added under a specific partner, it is added to the list of events for all partners, so you can see it in any partner's event dropdown.
> * See [tips](/docs/in-app-events-overview#tips) and [limitations](/docs/in-app-events-overview#limitations) for defining event names and parameters.

**Agencies and ad networks:**

* Can't add custom events
* Can only view and/or map events after the marketer added the event and granted the necessary [permissions](/docs/set-up-an-integrated-partner#permissions-tab).

## Event mapping by ad networks

Marketers can allow ad networks to map the events on their own. To do so, a marketer must give relevant permissions to the ad network:

1. On the **Active Integrations** page, find the partner you want to give permission.
2. Under the Permissions tab switch the **Allow to configure in-app event postbacks** toggle to **ON**.

![Allow to configure in-app event postbacks permission toggle for an ad network](https://files.readme.io/f8369f6a0a60d3c48ef66b51f61b3c81f00f6c88511f5f69b2c927788a64f018-33379700661265.png)

Once the ad network has received the permissions, it can map the events by following the instructions in the[Type Event ID Into Text Field](#h_01HBZCRNKG4EF9MSY696SD5VQ9).

## Event mapping by agencies

Marketers can allow agencies to configure in-app event postbacks.

> 📘 **Note**
>
> If both the advertiser and the agency enable the same in-app event postback to the same ad network, AppsFlyer sends the postback only once. This prevents duplicate reporting of the event.

**To grant the agency permission to configure in-app postbacks:**

1. Find the agency on the **Active integrations** page.
2. Select whether the agency can share all events or only those attributed to the specific ad network.
3. Select whether the agency is allowed to send event revenues.
4. Select the specific events the agency is allowed to share.

![Agency event-sharing and revenue permission settings](https://files.readme.io/194b9a18f7721d4cc159f6385140cbb989108b70110e2e0d0f29f90d6115b10a-33379684973969.png)

**See also**

* [Rich in-app events, Overview](/docs/in-app-events-overview)
* [Rich in-app events, Event structure](/docs/in-app-events-event-structure)