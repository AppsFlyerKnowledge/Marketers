---
title: Partner activation/deactivation
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2019-01-29T08:53:31Z'
  edited_at: '2021-01-13T10:58:36Z'
  id: 360000844778
  locale: vi
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/vi/articles/360000844778
---
> **At a glance:** By activating partner integration, advertisers allow AppsFlyer to attribute conversions and send postbacks to partners. When an advertiser stops running campaigns with a given partner, they should deactivate the integration to prevent inadvertent data sharing and conversion recording. Similarly, agencies must be activated and deactivated.

## Partners

The **Activate partner** setting determines if conversions are attributed to integrated partners and if postbacks are sent to them. Advertisers should also take note of how the platform handles partner deactivation in certain scenarios. Similarly, marketing and analytics partners that require postbacks must be activated.

<Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#ad-networks-providing-cost-information">Cost</Anchor> and <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution">ad revenue</Anchor> integrations (APIs) aren't governed by this setting and must be explicitly disabled to stop data collection.

<Accordion title="Activate partner integration">

The **Activate partner** setting controls attribution and postback sending according to the scenarios listed in the following table. When the setting is off, meaning deactivated, partners aren't attributed and postbacks aren't sent to them.

The **Activate partner** control is located on the partner **Integration** tab.

<div id="deactivating-a-partner" />

<div id="example-2" />

<div id="example-1" />

<div id="disabled-agency-permissions" />

<div id="note" />

<div id="agency-permissions" />

<div id="partner-visibility" />

<div id="partner-and-agency-access-to-dashboards" />

<div id="deactivate-a-partner-integration" />

<div id="who-can-activate-an-integration" />

> ❗️ **Caution**
>
> Don't use the **Activate partner** setting to pause or end campaigns. Doing so could cause irreversible damage to active campaign measurement.

| Scenario | On | [Default] Off |
| --- | --- | --- |
| New installs:<ul><li>Attribute installs</li><li>Send postbacks</li></ul> | Yes | No |
| Events from new conversions (installs, re-engagements, and re-attributions)<ul><li>Attribute installs</li><li>Send postbacks</li></ul> | Yes | No (exception: non-SRNs with engagements prior to deactivation, as documented later in this table) |
| Events from conversions (installs, re-engagements, and re-attributions) prior to deactivation | Not applicable | <ul><li>Attribution: Yes</li><li>Postbacks: No</li></ul> |
| Ad clicks | Display under the partner's name in aggregate data but aren't used as a basis for attribution | Display under the partner's name in aggregate data but aren't used as a basis for attribution |
| Engagement (click) and install occurs after deactivation | Not applicable | Attributed either to:<ul><li>Tự nhiên</li><li>To a prior engagement if it is within the <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">lookback window</Anchor></li></ul> |
| Engagement (click) occurs before deactivation; install occurs after deactivation | Not applicable | <ul><li>**<Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns">SRN partners</Anchor>** (such as Facebook or Google Ads): the deactivated partner is not attributed</li><li>**Non-SRN partners:** install and post-install events are attributed to the partner. No postbacks are sent.<br />In the days following deactivation, the number of attributed installs from the partner drops sharply, but may not stop completely until the end of the partner lookback window (usually 7 days.</li></ul> |

Ad networks can be activated by advertisers and agencies in accordance with the table that follows.

| Activated by | SRN | Non-SRN |
| --- | --- | --- |
| Advertiser | Activates for self-use and at on behalf of agencies | Activates for self-use |
| Agency | Can't activate | Activates agency appointed non-SRNs |

</Accordion>

<Accordion title="Deactivate unused integrations">

Partners whose **Activate partner** setting remains on after you stop running campaigns with them continue to receive postbacks containing campaign data. This can cause data privacy issues.

To help you identify these partners and remind you to deactivate them, a notification displays at the top of the **Configuration > Integrated Partners** page. This message indicates the number of partners that have had no recent conversions. Team members can only see this message for partners they are allowed to edit.

No recent conversions means:

* No conversions have been attributed to the partner for more than 30 days.
* The partner integration was saved 30 or more days ago, and since then no conversions have been attributed to them.

Note that deactivation only impacts postbacks. Cost and Revenue, if configured, continue to work.

**To view the list of unused partners and deactivate selected partners:**

1. In the warning message, click **Review and deactivate**.  
   The list of partners displays.   

   <Image align="center" alt="partner-bulk-deactivation-en_us.png" src="https://files.readme.io/bb414bc6a92149adc0904fee4c1b0b97aea5605ad0ef0eb8b0321f1db1ececca-360015159897.png" />
2. Select the partners to deactivate.
3. Click **Deactivate**.

Alternatively, a partner can be deactivated by turning off **Activate partner** on its Integration tab.

#### **Ad network and agency view**

* Ad networks that have permissions to configure integrations do not see the deactivation message.
* Agencies see the message but can only deactivate their own integrations.

</Accordion>

<Accordion title="Partner dashboard">

* Partners view the **Activate partner** setting in read-only mode. This is the case even if the partner has permission to configure the integration.
* Visibility of partner settings depends on whether it was the advertiser or the agency that configured the integration, as detailed in the following table:

| Integration configured by | Setup visible to ad network |
| --- | --- |
| Advertiser | Yes |
| Agency | No |

</Accordion>

## Agencies

<Accordion title="Activate agency integration">

App owners grant permission to agencies to enable the agency to work with an app. This is similar to activating ad networks.

**To grant agency permissions to an app:**

1. In AppsFlyer, go to **Configuration** > **Integrated Partners**.
2. Select the agency.
3. Go to the **Permissions** tab.
4. Enable **Agency Permissions.**
5. [Optional] Grant the agency additional permissions.
6. The agency is able to activate media sources as follows:   
   * **Non-SRNs:** the **agency** can set the Activate Partner setting in the integration tab.
   * **SRNs:** the **advertiser** activates the Activate Partner setting in the integration tab. If the advertiser deactivates the SRN, installs aren't attributed to the agency from that SRN.

</Accordion>

<Accordion title="Inactive agency traffic">

Traffic can't be attributed to an agency unless the advertiser grants it access.

If access is disabled for an agency:

* The agency can't access the app in its AppsFlyer dashboard.
* New installs and events are not attributed to the agency.
* Postbacks are not sent to the media sources used by the agency.
* New events from conversions prior to disabling the agency are attributed and displayed in the advertiser’s dashboard, but postbacks are not sent to the media sources.

**Inactive agency examples**

The following examples describe what happens to traffic that continues to be sent after an advertiser removes an agency's access:

**Example 1: Agency campaign with a non-SRN (attribution link partner)**

The traffic is attributed to organic, or to a prior engagement if still within its lookback window. The agency is not attributed.

**Example 2: Agency campaign with an SRN**

The traffic is attributed to the SRN on the advertiser's dashboard, but not attributed to the agency.

**Example 3: Agency campaign in Tencent or Google Ads iOS Search**

(This example is applicable to scenarios in which AppsFlyer receives click-through attribution links as well as querying the partner’s API.)

The traffic is attributed to organic, or to a prior engagement, if still within its lookback window. The agency is not attributed.

</Accordion>
