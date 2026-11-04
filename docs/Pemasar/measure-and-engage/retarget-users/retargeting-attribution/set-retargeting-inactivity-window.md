---
title: Set retargeting inactivity window
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2020-05-31T13:56:38Z'
  edited_at: '2026-09-15T11:14:51Z'
  id: 360009305817
  locale: en-us
  section: Retargeting attribution
  section_id: 6551326229265
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360009305817-Set-retargeting-inactivity-window
---
> **At a glance:** Increase incremental lift by retargeting inactive users. Set inactivity windows by media source.

<div id="inactivity-period" />

## Inactivity period

Advertisers regain inactive users by retargeting them. These campaigns usually have a good conversion rate and generate significant ROAS. However, many retargeting campaigns underperform as they don't filter out active users. To increase the incremental lift of retargeting campaigns, implement **minimum inactivity time** to filter out active users.

By setting a minimum inactivity time, Advertisers don't attribute active users. For example, if the minimum inactivity limit is 3 days, then users who were active in the previous 3 days aren't attributed. Users who are inactive for 4 or more days are attributed. The inactivity period applies to both re-attribution and re-engagement scenarios. In the case of re-attribution, the last activity is the last session before performing the uninstall.

**Inactivity rules**

* **Attributed:** Dormant users who haven't used the app for longer than the defined inactivity period. Retargeting re-engagements and reinstalls are attributed.
* **Not attributed**: Active users who open the app and don't exceed the minimum inactivity period are disregarded and not attributed to the retargeting campaign.

<div id="retargeting-inactivity-terminology" />

### Retargeting inactivity terminology

| Term | Definition |
| --- | --- |
| Maximum value | 30 days |
| Default value | 0 (none)  <br />The **Inactivity period** feature is not active by default for media sources. |
| User activity | Installs or sessions reported by the SDK or via S2S. |
| Migrated devices | Migration time is the last activity time. |

<div id="scenarios" />

## Scenarios

In the following retargeting scenarios, the inactivity period is defined for the media source.

<div id="reattribution" />

<Accordion title="Re-attribution">

The user scenario is depicted in the figure that follows. The user:

* uninstalls the app and is inactive
* engages with a retargeting campaign run by a media source
* reinstalls the app

[![re-attribution_1_en-us.png](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)

| Scenario | Inactivity threshold | User inactivity period | Result |
| --- | --- | --- | --- |
| A | 7 days | 8 days.<br /><br />**The user was inactive** for a period exceeding the inactivity threshold | <ul><li>**Re-attribution** (retargeting reinstall)</li><li>Attributed to retargeting media source A</li></ul> |
| B | 14 days | 5 days<br /><br />The user was active. | <ul><li>**Organic reinstall**</li><li>**Non-organic reinstall:** if the user engaged with a UA media source.</li><li>Retargeting media source A can't be attributed due to the user inactivity threshold.</li></ul> |

</Accordion>

<div id="reengagement" />

<Accordion title="Re-engagement">

The user scenario is depicted in the figure that follows. The user:

* installs the app
* is inactive for several days
* subsequently engages with a retargeting campaign. run by a media source, and launches the app

[![Re-engagement_scenarios_en-us.png](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)

| Scenario | Media source A inactivity threshold | User inactivity period | Result |
| --- | --- | --- | --- |
| A | 7 days | 8 days<br /><br />**The user was inactive** for a period exceeding the inactivity threshold | <ul><li>**Re-engagement** attributed to media source A</li></ul> |
| B | 7 days | 4 days<br /><br />**The user used the app** within the set inactivity period. | <ul><li>**Regular session**</li><li>Retargeting media source A is not attributed</li></ul> |

</Accordion>

<div id="partner-setup" />

## Partner setup

<div id="zd-srn" />

<Accordion title="SRN">

SRNs that support inactivity periods have this feature set up on their Integration tab.

**To define an inactivity period for Self-Reporting Networks (SRN) that support retargeting:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations.**
2. Select an SRN.
3. In the **Integration** tab, scroll down. Enable **Ignore active user for retargeting**
4. Set **Inactivity window.** (1-30 days.)
5. Click **Save integration.**

[![Inactivity_window_SRN.png](https://files.readme.io/a3a6dfb2270790a28b71581264c924ba1e4146d4975f64d3cee43a9e0ff3f172-36539146170897.png)](https://files.readme.io/a3a6dfb2270790a28b71581264c924ba1e4146d4975f64d3cee43a9e0ff3f172-36539146170897.png)

</Accordion>

<div id="nonsrn-click-ad-networks" />

<Accordion title="Non-SRN (click ad networks)">

**To define an inactivity period for non-SRNs that support retargeting:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations.**
2. Select an ad network.
3. Go to the **Attribution link** tab, scroll down, and enable **Ignore active user for retargeting**.
4. Set **Inactivity window.** (1-30 days.)  
   The **Inactivity period** parameter `af_inactivity_window`is added to the attribution link, for example, "&af\_inactivity\_window=7d". If the feature is disabled, it's not on the attribution link.

[![](https://files.readme.io/cec66a07874832ecd93d26a7275b81cd4cae2842b34d04c93427bb6344edd651-36538331525521.png)](https://files.readme.io/cec66a07874832ecd93d26a7275b81cd4cae2842b34d04c93427bb6344edd651-36538331525521.png)

</Accordion>

<div id="agencies" />

<Accordion title="Agencies">

<div id="srn" />

#### SRN

Agency (permission granted by the advertiser)

**To access the Inactivity period setup:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations.**
2. Select an SRN.
3. In the **Integration** tab, make settings as shown in the table that follows.

| SRN | Agency |
| --- | --- |
| DoubleClick | <ul><li>Enable/disable retargeting</li><li>Configure an inactivity period</li></ul> |
| Google Ads | <ul><li>Cannot enable/disable retargeting</li><li>If an agency has permissions, they can configure an inactivity period</li></ul> |
| Meta ads/X Ads/Snapchat | Can't access retargeting and **Inactivity period** setup |

<div id="non-srn" />

#### Non-SRN

Partner (supports retargeting)

**To define an inactivity period for non-SRNs that support retargeting:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations.**
2. Select a non-SRN Ad network > **Attribution link** tab.

</Accordion>

<div id="traits-and-limitations" />

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Testing links | When using a registered test device, make sure to remove the `af_inactivity_window` parameter from the testing link. Otherwise, the install may be incorrectly attributed as *Organic* instead of being attributed to the test link. |

<div data-zendesk-anchors="h_01H9JS3QKW5S7VP9YW05CB6STR=inactivity-period h_01H9JS3QKXMBS95RG06A9JXGT0=retargeting-inactivity-terminology h_01H9JS3QKXWDX8Y58GX1G5HNYY=scenarios h_01H9JS3QKXN0E0MGD35173C9FR=reattribution h_01H9JS3QKXNS77EFYBZP94YQMT=reengagement h_01H9JS3QKXGNFM8499G52458B2=partner-setup srn=zd-srn h_01H9JS3QKXCAHG91VS6VSVJTTT=zd-srn h_01H9JS3QKX8R8AXHQWKX7FR9GZ=nonsrn-click-ad-networks h_01H9JS3QKXSDXA5Z7TWN2A7S5K=agencies srn::bd853114=srn h_01H9JS3QKX88HQYJ5881W7VXF2=srn nonsrn=non-srn h_01H9JS3QKXRJ8W9H89JBVSZ3R3=non-srn h_01J6S6HS0H0M6GQ81WGZ3XT0P9=traits-and-limitations" />
