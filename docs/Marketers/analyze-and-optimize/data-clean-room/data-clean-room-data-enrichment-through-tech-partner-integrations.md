---
title: "Data Clean Room: Tech Partner Integrations"
excerpt: "Enrich your data and enhance your Data Clean Room (DCR) reports with data from our integrated tech partners."
---
> 📘 Try out this new feature!
>
> The tech partner integration feature is currently in open beta. If you are interested in activating any of the available integrations, just contact your CSM. We look forward to your feedback.

## Overview

While matching conversion data and custom source data is at the heart of the DCR, the possibilities don't end there. Available integrations with our tech partners allow you to sharpen your focus and improve campaign performance.

#### Cost considerations

Utilizing tech partner integrations involves 2 primary cost considerations:

- **Data access:** Charges vary by partner and are discussed in more detail in the tabs below. In many cases where data access involves additional charges, we offer free data-access trial periods so you can experiment.
- **DCR credits:**

While this feature is in beta, data utilized from tech partners will **not** be added to the number of processed rows for report runs and will not affect the calculation of used credits. Credits per report run will continue to be charged as normal (even during free data-access trial periods).

## Available integrations

Click the partner name for activation details.

| Partner | Data type and business value |
| --- | --- |
| [Braze](/docs/data-clean-room-data-enrichment-through-tech-partner-integrations#braze) | Braze allows advertisers to manage and measure user engagement and conversion after an app has been installed.<br>Connecting the DCR to your Braze data allows you to analyze the success of your campaigns in light of user interactions with owned-media channels such as emails, push notifications, and in-app messages.<br>For example, do the users acquired in a certain campaign go on to make purchases or become subscribers after receiving push notifications?<br>**Note:** We've opened our beta with support for the **push notification open** event, but we can immediately add support for any other Braze events you're measuring. Just let us know! |
| [Start.io](/docs/data-clean-room-data-enrichment-through-tech-partner-integrations#startio) | Start.io maintains a large database of user profiles with information about their interests.<br>Connecting the DCR to this database can provide you with valuable insights into the interests of your acquired users, allowing you to analyze the potential success of your running campaigns.<br>For example, do the users you acquired for a casino game app typically show interest in casino games? Or do they mostly show interest in role-playing games? If they're not heavy casino game users, will the campaign ROI meet your expectations?<br>**Notes:**<br>- Check out the [Start.io website](https://www.start.io/syndicated-segments/) for the types of user interest topics available.<br>- Start.io data is available only for users in the United States. |
| [Techsalerator](/docs/data-clean-room-data-enrichment-through-tech-partner-integrations#techsalerator) | Techsalerator maintains an extensive database of locally-sourced consumer data in 144 countries – including demographic profiles, lifestyles, and behaviors.<br>Connecting the DCR to this database can provide you with valuable insights about the users you've acquired or re-engaged through your campaigns. You can then use those insights to optimize the campaigns.<br>For example, do most of a campaign's acquired or re-engaged users fall into an age group different from the one the campaign was designed to reach? Are you interested in expanding the campaign's reach to target additional age groups?<br>**Notes:**<br>- For relevant available data fields, check out the **Individual** tab of Techsalerator's [data catalog](https://www.techsalerator.com/data-catalog).<br>- For data-field availability by country, take a look at their [country-based data marketplace](https://www.techsalerator.com/data-marketplace). |
| [Evorra](/docs/data-clean-room-data-enrichment-through-tech-partner-integrations#evorra) | Evorra is a cookieless data marketplace including the IDs of over 1 billion users from over 35 providers worldwide. All data is consented and privacy-compliant.<br>Evorra can return a high match rate based on hashed emails in most major geos – allowing you to enrich your user data with the following types of attributes: demographic, socioeconomic, retail, interest/intent, entertainment, sports, business, technology, automobiles, and more.<br>You can then utilize this user data to evaluate and optimize your campaigns based on whether they are reaching their intended audiences. For example: You ran a retargeting campaign directed to users intending to purchase flight tickets for family vacations. Did it actually engage those users? Or did it reach users intending to book singles cruises instead?<br>**Note:**<br>- Contact your CSM or [hello@appsflyer.com](mailto:hello@appsflyer.com) to find out more about the extensive list of user attributes available through Evorra. |

## Getting started

Follow the instructions in the tabs below for activating one or more of these integrations:

<Tabs>
<Tab title="Braze">

#### Prerequisites

The Braze integration makes use of data sharing through Snowflake. To utilize the integration, you must have:

- A Braze subscription that includes Secure Data Sharing with Snowflake
- Both the Braze and AppsFlyer SDKs integrated into your app

#### Activating the integration

**To activate the Braze integration:**

1. Coordinate with the Braze team (as detailed in the [Braze documentation](https://www.braze.com/docs/partners/data_and_infrastructure_agility/data_warehouses/snowflake/#integration)) to provision a data share from one or more Braze app groups to the AppsFlyer Snowflake account: `AEJUPNV.DCR_AWS_US_EAST_1_QA`.
2. Ensure that the AppsFlyer SDK is configured to send AppsFlyer a [CUID](https://support.appsflyer.com/hc/articles/207032016) for each user, or use the [S2S API](https://support.appsflyer.com/hc/articles/207034486) to send the CUID.
   - **Important!** The CUID must have the same value as the Braze `external_user_id`.
3. Contact your CSM or [hello@appsflyer.com](mailto:hello@appsflyer.com) to let us know that you want to activate the integration.
   - Provide us with the Braze `app_group_id` (one or more) from which the data share was provisioned.

Once you've made the necessary arrangements on the Braze side, there are no additional cost considerations charges from the AppsFlyer side.

</Tab>

<Tab title="Start.io">

#### Activating the integration

**To activate the Start.io integration, all you've got to do is let us know.**

- You have 30 days of free access to Start.io data from the date you first run a report that uses it.
- After 30 days, any reports that use this data will fail unless you arrange a subscription directly with Start.io. Contact your CSM or [hello@appsflyer.com](mailto:hello@appsflyer.com), and they'll help make this happen.

</Tab>

<Tab title="Techsalerator">

#### Activating the integration

**To activate the Techsalerator integration, just let us know.**

- To use Techsalerator data in your reports, you must first arrange a subscription directly with Techsalerator. Contact your CSM or [hello@appsflyer.com](mailto:hello@appsflyer.com), and they'll help make this happen.
  - There is no trial period available for access to Techsalerator data.
- Note that activating Techsalerator data within the DCR may take some time, so be sure to contact us at least one week prior to your projected start date.

</Tab>

<Tab title="Evorra">

#### Activating the integration

**To activate the Evora integration, just let us know.**

- To use Evorra data in your reports, you must first arrange a subscription directly with Evorra. Contact your CSM or [hello@appsflyer.com](mailto:hello@appsflyer.com), and they'll help make this happen.
  - There is no trial period available for access to Evorra data.
- Note that activating Evorra data within the DCR may take some time, so be sure to contact us at least one week prior to your projected start date.

</Tab>
</Tabs>