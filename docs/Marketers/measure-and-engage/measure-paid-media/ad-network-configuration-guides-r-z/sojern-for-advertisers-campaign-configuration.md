---
title: "Sojern for Advertisers campaign configuration"
excerpt: "Configure your programmatic travel market campaigns with Sojern for Advertisers in AppsFlyer."
---
Sojern for Advertisers, an AppsFlyer ad network integrated partner, specializes in programmatic buying for the travel market.

To configure your campaigns with Sojern for Advertisers, follow the steps below.

## Setting up Sojern for Advertisers

> 📘 Prerequisite
>
> An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.

( **To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.

> 📘 Note
>
> The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)

5. Complete the configuration using the relevant tabs, as described below. Learn more about [partner integrations.](/docs/set-up-an-integrated-partner)

## Integration tab

The Integration Tab is divided into different sections as described below.

### Activate partner

On the **first visit** here, you'll need to turn on the _**Activate Partner**_ toggle to enable setup of the Integration parameters. The toggle MUST be ON for as long as you work with the partner.

For more details about partner activation please click [here](/docs/partner-activation-deactivation).

> 📘 Note
>
> As an ALL-Installs network, Sojern for Advertisers prefers to receive postbacks for all new installs of your app from ANY source, including organic. To do so, select **Events attributed to any partner** to send all install postbacks to Sojern for Advertisers.

### General settings

**Partner ID**

Sojern for Advertisers connects with AppsFlyer via a unique Partner ID. If you don't already have the Partner ID, you must obtain it from Sojern for Advertisers to continue with the integration.

<Image src="https://files.readme.io/35d02000642f8dc768c5bd1b0ca7846b9575900b2e9b3169673840f438815ef1-360002443905.png" alt="Sojern_msc_new_2.png" />

### Default postbacks

Send automatic postbacks to Sojern for Advertisers following user installs and re-engagements. Use this section to define the **source of the users** that allow sending these postbacks.

Select **Only events attributed to this partner** for events coming only from users attributed to Sojern for Advertisers.

Select **Events attributed to any partner or organic** to have your entire user base available to be reported to Sojern for Advertisers.

### In-app events settings

In this section, you can map your AppsFlyer events with Sojern for Advertisers via postbacks.

1. Enter the Sojern for Advertisers Partner ID again.
2. Toggle In-App Event Postbacks to ON.
3. Select the Sending Option for all SDK-defined events.

**- Only events attributed to this partner** for events coming **only** from users attributed to this partner

**- Events attributed to any partner or organic** to have your entire user base available to be reported to the partner
4. Click **Add Event** to add an SDK Event to the list.

For more details about Sojern for Advertisers In-App Events, click here.
5. Complete the following parameters:

| Parameter Name | Description |
| --- | --- |
| **SDK Event Name** | The name of the event, as received by AppsFlyer either from the SDK integrated in your app, or from server-to-server events.<br />**Tip** - If you don't see the event you want in the list, make sure to activate the event on a device with a non-organic installation and recheck. |
| **Partner Event Identifier** | The unique name or ID of each event as defined on Sojern for the Advertisers' side.<br />Obtain the corresponding Event ID from Sojern for Advertisers and set it in the text field. |
| **Send Revenue** | **When unchecked** - sends all the parameters of the rich in-app event to the partner, except for the revenue parameter, which is contained in the **af\_revenue** parameter.<br />**When checked** - sends all the parameters including the revenue value (if it exists in the event). |

### Event types

Sojern for Advertisers requires the implementation of the following events:

**Hotel**

| Type of Event | Sojern for Advertisers Events | SDK Event | Description |
| --- | --- | --- | --- |
| Homepage | HOME\_PAGE | af\_app\_opened | App open/brought to the foreground |
| Search Result | HOTEL\_SEARCH | af\_list\_view | Search result page showing a list of options |
| Product | HOTEL\_PRODUCT | af\_content\_view | View of a specific product/option from the search results |
| Confirmation | HOTEL\_CONFIRMATION | af\_purchase | Purchase of the item(s) |

**Flight**

| Type of Event | Sojern for Advertisers Events | SDK Event | Description |
| --- | --- | --- | --- |
| Homepage | HOME\_PAGE | af\_app\_opened | App open/brought to the foreground |
| Search Result | FLIGHT\_SEARCH | af\_list\_view | Search result page showing a list of options |
| Product | FLIGHT\_PRODUCT | af\_content\_view | View of a specific product/option from the search results |
| Confirmation | FLIGHT\_CONFIRMATION | af\_purchase | Purchase of the item(s) |

**Cruise**

| Type of Event | Sojern for Advertisers Events | SDK Event | Description |
| --- | --- | --- | --- |
| Homepage | HOME\_PAGE | af\_app\_opened | App open/brought to the foreground |
| Search Result | CRUISE\_SEARCH | af\_list\_view | Search result page showing a list of options |
| Product | CRUISE\_PRODUCT | af\_content\_view | View of a specific product/option from the search results |
| Confirmation | CRUISE\_CONFIRMATION | af\_purchase | Purchase of the item(s) |

**Car**

| Type of Event | Sojern for Advertisers Events | SDK Event | Description |
| --- | --- | --- | --- |
| Homepage | HOME\_PAGE | af\_app\_opened | App open/brought to the foreground |
| Search Result | CAR\_SEARCH | af\_list\_view | Search result page showing a list of options |
| Product | CAR\_PRODUCT | af\_content\_view | View of a specific product/option from the search results |
| Confirmation | CAR\_CONFIRMATION | af\_purchase | Purchase of the item(s) |

**Entertainment**

| Type of Event | Sojern for Advertisers Events | SDK Event | Description |
| --- | --- | --- | --- |
| Homepage | HOME\_PAGE | af\_app\_opened | App open/brought to the foreground |
| Search Result | ENTERTAINMENT\_SEARCH | af\_list\_view | Search result page showing a list of options |
| Product | ENTERTAINMENT\_PRODUCT | af\_content\_view | View of a specific product/option from the search results |
| Confirmation | ENTERTAINMENT\_CONFIRMATION | af\_purchase | Purchase of the item(s) |

**Train**

| Type of Event | Sojern for Advertisers Events | SDK Event | Description |
| --- | --- | --- | --- |
| Homepage | HOME\_PAGE | af\_app\_opened | App open/brought to the foreground |
| Search Result | RAIL\_SEARCH | af\_list\_view | Search result page showing a list of options |
| Product | RAIL\_PRODUCT | af\_content\_view | View of a specific product/option from the search results |
| Confirmation | RAIL\_CONFIRMATION | af\_purchase | Purchase of the item(s) |

**Vacation**

| Type of Event | Sojern for Advertisers Events | SDK Event | Description |
| --- | --- | --- | --- |
| Homepage | HOME\_PAGE | af\_app\_opened | App open/brought to the foreground |
| Search Result | VACATION\_SEARCH | af\_list\_view | Search result page showing a list of options |
| Product | VACATION\_PRODUCT | af\_content\_view | View of a specific product/option from the search results |
| Confirmation | VACATION\_CONFIRMATION | af\_purchase | Purchase of the item(s) |

#### Correct configuration of in-app events

It's important when configuring a campaign with Sojern for Advertisers that specific in-app events are set up.

When the AppsFlyer naming convention is not available, use the Sojern for Advertisers Param key.

Sojern for Advertisers has four types of in-app events:

- Confirmation
- Product
- Search
- Cart

Set out below is an example of the Search and Confirmation for the hotel and flight sector:

|  | Name | Param Key | AppsFlyer Rich In-App Event Name |
| --- | --- | --- | --- |
| **Flight Search** | Event Type | et | value 'fs' |
|  | Number of Travelers | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Number of adults | tad | af\_num\_adults |
|  | Numbers of children | tch | af\_num\_children |
|  | Service Class | fc | af\_class |
|  | One Way | fow | N/A |
|  | Multi-city | fmc | N/A |
|  | Website County Domain | dctry | N/A |
|  | Site Domain | domain | N/A |
|  | Origin Airport | fa1 | af\_destination\_a |
|  | Destination Airport | fa2 | af\_destination\_b |
|  | Destination City | fc1 | af\_city |
|  | Origination City | fc2 | N/A |
|  | Departure Date | fd1 | af\_departing\_departure\_date |
|  | Return Date | fd2 | af\_returning\_departure\_date |
| **Flight Confirmation** | Name | Param key |  |
|  | Event Type | et | value 'fc' |
|  | Number of Travelers | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Number of adults | tad | af\_num\_adults |
|  | Numbers of children | tch | af\_num\_children + af\_num\_infants |
|  | Service Class | fc | af\_class |
|  | Website County Domain | dctry | N/A |
|  | Site Domain | domain | N/A |
|  | Origin Airport | fa1 | af\_destination\_a |
|  | Destination Airport | fa2 | af\_destination\_b |
|  | Destination City | fc1 | af\_city |
|  | Origination City | fc2 | N/A |
|  | Departure Date | fd1 | af\_departing\_departure\_date |
|  | Return Date | fd2 | af\_returning\_departure\_date |
|  | Purchase Currency | fcu | af\_currency |
|  | Purchase Price | fp | af\_revenue |
| **Hotel Search** | Name | Param key |  |
|  | Event Type | et | value 'hs' |
|  | Website County Domain | dctry | af\_country |
|  | Destination City | hc1 | af\_city |
|  | Check-In Date | hd1 | af\_date\_a |
|  | Check-Out Date | hd2 | af\_date\_b |
|  | Number of Travelers | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Number of adults | tad | af\_num\_adults |
|  | Numbers of children | tch | af\_num\_children + af\_num\_infants |
|  | Site Domain | domain | N/A |
| **Hotel Confirmation** | Name | Param key |  |
|  | Event Type | et | value 'hc' |
|  | Website County Domain | dctry | N/A |
|  | Destination City | hc1 | af\_city |
|  | Check-In Date | hd1 | af\_date\_a |
|  | Check-Out Date | hd2 | af\_date\_b |
|  | Number of Travelers | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Number of adults | tad | af\_num\_adults |
|  | Numbers of children | tch | af\_num\_children + af\_num\_infants |
|  | Site Domain | domain | N/A |
|  | Destination Country | hn1 | af\_country |
|  | Purchase Price | hp | af\_revenue |
|  | Purchase Currency | hcu | af\_currency |

#### Example

Flight Search event values:

In-app event: af\_list\_view in-app event values: et=‘fs’&af\_num\_adults=`{number of adults}&af\_num\_children={number of children}&af\_class={service class}&fow={one way}&fmc={multi city}&dctry={website country domain}&af\_destination\_a={departure airport code}&af\_destination\_b={arrival airport code}&af\_city={destination city}&fc2={origin city}&af\_departing\_departure\_date={YYYY-MM-DD}&af\_returning\_departure\_date{YYYY-MM-DD}`

## Attribution link tab

In this tab, you can create the attribution links you want to send to Sojern for Advertisers for attributing campaigns, ad sets, or even single ads. Note that AppsFlyer DOES NOT save your generated partner's attribution links.

This tab is divided into different sections:

### Attribution link parameters

In this section, select which parameters you want to add to the attribution link.

Adding parameters to the attribution link here enables you to later perform thorough drill-down analyses. Parameters that are already defined on the attribution link can be edited by adding them and their new values here.

- **Campaign** - add it to compare different campaigns running with Sojern for Advertisers.

**Attribution link parameter:** c
- **Adset** - set ad set names to compare different ad sets within specific Sojern for Advertisers campaigns.

**Attribution link parameter:** af\_adset
- **Ad Name** - set ad set names to compare different creatives within specific ad sets within specific Sojern for Advertiser campaigns.

**Attribution link parameter:** af\_ad
- **Site ID** and **Sub Site ID** - set the Site ID parameter to attribute installs to specific publishers. If many publishers exist, we advise limiting the number of used site IDs and using the subsite ID parameter, to avoid [exceeding the site ID](/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit) limitations.

**Attribution link parameters:** af\_siteid and af\_sub\_siteid
- **Subscriber Parameters** - use any of the 5 subscriber parameters to insert useful values. Note that these parameters get parsed and appear in the raw data report, which makes them very handy for performing data aggregation or filtering.

**Attribution link parameters:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Add any other parameter to the attribution link simply by typing it in a new parameter box. For more information about [**AppsFlyer's Attribution Link Structure and Parameters**](/docs/about-link-structure-and-parameters) **.**

### Click-through attribution

This slider allows you to set the **maximum time from click to install**. Only installs (first launches) that take place within the lookback window may be attributed to Sojern for Advertisers.

**Attribution link parameter:** af\_click\_lookback

More details about the [click lookback window here](/docs/set-up-lookback-windows).

### Click attribution link

This is the attribution link that contains all the setup information you have set for it. Send it to Sojern for Advertisers to be activated when leads click on a corresponding ad.

## Cost tab

Cost integration is not available for Sojern for Advertisers.

## Ad revenue tab

Ad Revenue Tab integration is not available for Sojern for Advertisers.

## Permissions tab

No configuration of permissions is available for Sojern for Advertisers.