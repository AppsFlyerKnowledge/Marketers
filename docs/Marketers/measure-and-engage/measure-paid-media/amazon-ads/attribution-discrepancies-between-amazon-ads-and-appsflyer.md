---
title: "Attribution discrepancies between Amazon Ads and AppsFlyer"
excerpt: "Understand the differences in attribution models and timezone configurations that can cause reporting discrepancies between Amazon Ads and AppsFlyer."
---
As two major players in the mobile user acquisition ecosystem, Amazon Ads and AppsFlyer use distinct attribution models. This may cause discrepancies between Amazon Ads and AppsFlyer dashboards. While we work closely with Amazon Ads to minimize these discrepancies, advertisers need to be aware of potential causes.

## Differences in attribution models

The table below describes possible reasons for discrepancies between the Amazon Ads and the AppsFlyer dashboards:

| Cause | Amazon Ads Manager | AppsFlyer |
| --- | --- | --- |
| Multi-channel source attribution | Amazon Ads self-attributes installs regardless of other media sources. | AppsFlyer uses last-click attribution.<br>Learn more about the [AppsFlyer attribution model](https://support.appsflyer.com/hc/articles/207447053-What-is-AppsFlyer-s-Attribution-Model-). |
| Different timezones | Amazon Ads timezone (displayed next to the date range) can't be adjusted. It was configured while creating the ad account. | The AppsFlyer default app timezone is UTC+0. To match the timezone defined in the Amazon Ads, change the timezone set for the app on the [app settings page](https://support.appsflyer.com/hc/articles/211719806-App-settings-#localization-time-zone). |