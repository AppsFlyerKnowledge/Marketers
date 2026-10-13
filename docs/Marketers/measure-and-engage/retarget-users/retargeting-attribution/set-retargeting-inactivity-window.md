---
title: "Set retargeting inactivity window"
excerpt: "Increase incremental lift by retargeting inactive users and setting inactivity windows by media source."
---
**At a glance:** Increase incremental lift by retargeting inactive users. Set inactivity windows by media source.

## Inactivity period

Advertisers regain inactive users by retargeting them. These campaigns usually have a good conversion rate and generate significant ROAS. However, many retargeting campaigns underperform as they don't filter out active users. To increase the incremental lift of retargeting campaigns, implement **minimum inactivity time** to filter out active users.

By setting a minimum inactivity time, Advertisers don't attribute active users. For example, if the minimum inactivity limit is 3 days, then users who were active in the previous 3 days aren't attributed. Users who are inactive for 4 or more days are attributed. The inactivity period applies to both re-attribution and re-engagement scenarios. In the case of re-attribution, the last activity is the last session before performing the uninstall.

**Inactivity rules**

* **Attributed:** Dormant users who haven't used the app for longer than the defined inactivity period. Retargeting re-engagements and reinstalls are attributed.
* **Not attributed**: Active users who open the app and don't exceed the minimum inactivity period are disregarded and not attributed to the retargeting campaign.

### Retargeting inactivity terminology

| Term | Definition |
| --- | --- |
| Maximum value | 30 days |
| Default value | 0 (none)  <br />The **Inactivity period** feature is not active by default for media sources. |
| User activity | Installs or sessions reported by the SDK or via S2S. |
| Migrated devices | Migration time is the last activity time. |

## Scenarios

In the following retargeting scenarios, the inactivity period is defined for the media source.

### Re-attribution

The user scenario is depicted in the figure that follows. The user:

* uninstalls the app and is inactive
* engages with a retargeting campaign run by a media source
* reinstalls the app

[![re-attribution_1_en-us.png](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)](https://support.appsflyer.com/hc/article_attachments/10298371408017)

| Scenario | Inactivity threshold | User inactivity period | Result |
| --- | --- | --- | --- |
| A | 7 days | 8 days.<br /><br />**The user was inactive** for a period exceeding the inactivity threshold | * **Re-attribution** (retargeting reinstall)<br />* Attributed to retargeting media source A |
| B | 14 days | 5 days<br /><br />The user was active. | * **Organic reinstall**<br />* **Non-organic reinstall:** if the user engaged with a UA media source.<br />* Retargeting media source A can't be attributed due to the user inactivity threshold. |

### Re-engagement

The user scenario is depicted in the figure that follows. The user:

* installs the app
* is inactive for several days
* subsequently engages with a retargeting campaign. run by a media source, and launches the app

[![Re-engagement_scenarios_en-us.png](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)](https://support.appsflyer.com/hc/article_attachments/10124778806929)

| Scenario | Media source A inactivity threshold | User inactivity period | Result |
| --- | --- | --- | --- |
| A | 7 days | 8 days<br /><br />**The user was inactive** for a period exceeding the inactivity threshold | * **Re-engagement** attributed to media source A |
| B | 7 days | 4 days<br /><br />**The user used the app** within the set inactivity period. | * **Regular session**<br />* Retargeting media source A is not attributed |

## Partner setup

### SRN

SRNs that support inactivity periods have this feature set up on their Integration tab.

**To define an inactivity period for Self-Reporting Networks (SRN) that support retargeting:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations.**
2. Select an SRN.
3. In the **Integration** tab, scroll down. Enable **Ignore active user for retargeting**
4. Set **Inactivity window.** (1-30 days.)
5. Click **Save integration.**

[![Inactivity_window_SRN.png](https://files.readme.io/a3a6dfb2270790a28b71581264c924ba1e4146d4975f64d3cee43a9e0ff3f172-36539146170897.png)](https://support.appsflyer.com/hc/article_attachments/36539146170897)

### Non-SRN (click ad networks)

**To define an inactivity period for non-SRNs that support retargeting:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations.**
2. Select an ad network.
3. Go to the **Attribution link** tab, scroll down, and enable **Ignore active user for retargeting**.
4. Set **Inactivity window.** (1-30 days.)  
   The **Inactivity period** parameter `af_inactivity_window`is added to the attribution link, for example, "&af\_inactivity\_window=7d". If the feature is disabled, it's not on the attribution link.

[![](https://files.readme.io/cec66a07874832ecd93d26a7275b81cd4cae2842b34d04c93427bb6344edd651-36538331525521.png)](https://support.appsflyer.com/hc/article_attachments/36538331525521)

### Agencies

#### SRN

Agency (permission granted by the advertiser)

**To access the Inactivity period setup:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations.**
2. Select an SRN.
3. In the **Integration** tab, make settings as shown in the table that follows.

| SRN | Agency |
| --- | --- |
| DoubleClick | * Enable/disable retargeting<br />* Configure an inactivity period |
| Google Ads | * Cannot enable/disable retargeting<br />* If an agency has permissions, they can configure an inactivity period |
| Meta ads/X Ads/Snapchat | Can't access retargeting and **Inactivity period** setup |

#### Non-SRN

Partner (supports retargeting)

**To define an inactivity period for non-SRNs that support retargeting:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations.**
2. Select a non-SRN Ad network > **Attribution link** tab.

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Testing links | When using a registered test device, make sure to remove the `af_inactivity_window` parameter from the testing link. Otherwise, the install may be incorrectly attributed as *Organic* instead of being attributed to the test link. |