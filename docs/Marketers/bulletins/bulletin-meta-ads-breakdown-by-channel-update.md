---
title: "Bulletin: Meta ads breakdown by channel update"
excerpt: "Learn about Meta's per-ad-account opt-in requirement for the impression device breakdown and how to ensure your channel-level cost data remains complete."
---
| Section | Details |
| --- | --- |
| **What's new** | Meta now requires per-ad-account opt-in for the `impression_device` breakdown, effective August 6, 2026. Because Meta's reporting API cannot return cost data broken down by both geo and channel in the same query, accounts without this opt-in will see incomplete data:<br />- Channel-level cost data may be missing from the default My Dashboards view<br />- Meta's data may be missing from Cost ETL<br />The same limitation also affects creative performance data broken down by channel. |
| **Effective date** | August 6, 2026 |
| **What you need to know** | Meta applies this opt-in automatically on AppsFlyer customer accounts. You do not need to take any action before August 6.<br />- If your cost data broken down by channel, or your creative performance data broken down by channel, is missing after August 6, the automatic opt-in has not yet applied to your account. |
| **What you need to do** | Take the following steps:<br />1. After August 6, check your cost data broken down by channel (My Dashboards) and your creative performance data broken down by channel.<br />2. If you notice a gap, contact Meta directly for guidance on enabling the opt-in, or reach out to your AppsFlyer representative for help.<br />3. Once the opt-in applies to your account, your data will catch up automatically through backfill shortly after.<br />4. You can also check directly in Ads Manager whether Impression Device is already enabled for the account. See [Check Impression Device in Ads Manager](#check-impression-device-in-ads-manager) below for the steps. |

## Check Impression Device in Ads Manager

To check whether Impression Device is already enabled for an ad account:

1. Go to [Ads Manager](https://adsmanager.facebook.com/) and select **Settings**.

<Image src="https://files.readme.io/64c9ac8d571e88bfd098b542456886cc64d6320bf3856721335a077c4f19e5b5-49469436208529.png" alt="Ads Manager toolbar showing the Settings button" />

3. In the Create view panel, select **Delivery**.
4. Under Delivery, find **Additional Breakdowns**.
5. Under Additional Breakdowns, check whether the plus symbol next to **Impression Device** (`impression_device`) is already selected. If it is, the opt-in is active for this account.

<Image src="https://files.readme.io/71eb7c75a3f49a82e98522fcf418acbc6ef378eeda5f093535a168aa8505ade1-49469462456081.png" alt="Additional Breakdowns panel in Ads Manager with plus icons for Time of Day, Impression Device, and Frequency Value" />