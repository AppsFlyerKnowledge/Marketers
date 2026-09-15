---
title: "Bulletin: Apple Ads adds timestamps to all attribution claims"
excerpt: "Apple's AdServices API now includes engagement timestamps for all iOS attribution claims, improving lookback window accuracy, while ad groups with age or gender targeting will return false payloads."
---
| Section | Details |
| --- | --- |
| What's new | As of September 1, 2026:<br />- Apple's AdServices API adds an engagement timestamp to all iOS attribution claims, including those that previously lacked one. AppsFlyer uses this timestamp to apply your configured lookback window and last-touch attribution rules to these claims.<br />- For ad groups with age or gender targeting, Apple will return an attribution payload of false, and these engagements cannot be attributed to Apple Ads in AppsFlyer. |
| Effective date | September 1, 2026 |
| What you should know | - For most Apple Ads campaigns, attribution accuracy improves because engagements are now evaluated against your advertiser-defined lookback window rather than the previous default windows, including engagements from non-consenting users who previously were claimed without timestamps.<br />- Separately, ad groups with age or gender targeting will return a false attribution payload. Engagements from those ad groups are not claimed by Apple Ads and therefore cannot be attributed to them. |
| What you should do | No action is required. Your Apple Ads integration reflects this change automatically. If you run age or gender targeted ad groups, review your Apple Ads reporting after September 1 to understand any change in attributed conversions. |

<Cards>
  <Card title="Apple Ads integration setup" href="/docs/apple-ads-integration-setup">
    Learn how to set up and configure your Apple Ads integration in AppsFlyer.
  </Card>
</Cards>