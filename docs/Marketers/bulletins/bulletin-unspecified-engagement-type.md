---
title: "Bulletin: Unspecified engagement type"
excerpt: "To standardize reporting when engagement type is missing or mismatched, AppsFlyer is introducing default values in raw data reports and dashboards starting December 9, 2024."
---
To standardize reporting when `engagement_type` is missing or mismatched, we are introducing `click_unspecified` or `impression_unspecified` as the default values in raw data reports and dashboards.

### What’s the impact

* **Conversions**:
  Starting from the effective date, the `engagement_type` will no longer be reported as empty but will default to `click_unspecified` or `impression_unspecified`, depending on the touch type (i.e., click or impression).
* **In-app events and sessions**:
  The new values will apply only to in-app events and sessions attributed to conversion events recorded after the effective date. Those attributed to conversion events recorded before the effective date will remain unaffected.

### Effective date

December 9, 2024

### What you should know

All information relating to EET can be found in the KB:
- [Enriched Engagement Types](https://support.appsflyer.com/hc/articles/21837486015889-Enriched-Engagement-Types)
- [Enriched engagement types guide for partners](https://support.appsflyer.com/hc/articles/29221265052433-Enriched-engagement-types-guide-for-partners)

For immediate impact of the introduction of EET see the bulletin:
- [Enhanced engagement types visibility](https://support.appsflyer.com/hc/articles/29614354758545-Enhanced-engagement-types-visibility)