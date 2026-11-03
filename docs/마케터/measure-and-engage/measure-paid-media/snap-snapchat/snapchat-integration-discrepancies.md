---
title: Snapchat integration discrepancies
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-24T08:57:20Z'
  edited_at: '2023-11-02T10:20:16Z'
  id: 4417686973841
  locale: en-us
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4417686973841-Snapchat-integration-discrepancies
---
> **At a glance:** Learn about the different discrepancies between Snapchat and AppsFlyer dashboards and reposts.

In certain instances, advertisers can see fewer installs on AppsFlyer dashboard than on the Snapchat Ads Manager dashboard. Sometimes, the discrepancy can be addressed by making changes to the settings in the AppsFlyer dashboard or Snapchat Ads Manager (e.g timezone settings, attribution windows etc.). However, a discrepancy between the two dashboards is expected. Advertisers should rely on the AppsFlyer dashboard as the source of truth when evaluating CPI and performance.

Advertisers should be aware of the following causes and consider taking the necessary actions.

## Source of discrepancies and solutions

Set out below are a number of causes of discrepancies and possible solutions.

### Different lookback windows

By default, Snapchat Ads Manager and AppsFlyer have different attribution windows.

| Lookback Window | Snapchat Ads Manager | AppsFlyer |
| --- | --- | --- |
| Click Attribution Lookback Window | 28 days | 7 days by default (can be configured to be 1-30 days) |
| View-Through Attribution Lookback Window | 1 day | 1 day by default (can be configured to be 1-48 hours) |

> 👍 **Solutions**
>
> 1. Configure the attribution window in AppsFlyer to match Snapchat’s default values.
> 2. Advertisers can select attribution windows in the Ads Manager dashboard to match what they have set as default in their attribution partner (MMP) dashboard. Contact your Snapchat CSM to have your account allowlisted to activate this feature.

### Time zone differences

By default, Ads Manager uses PST timezone whereas AppsFlyer uses UTC +0 by default. As a result, for example, Snapchat might attribute an install to Friday while AppsFlyer attributes it to Saturday.

> 👍 **Solution**
>
> Configure PST as the timezone for each app in AppsFlyer. Click <Anchor target="_blank" href="/marketers/ko/docs/changing-app-time-zone-settings">here</Anchor> for details of how to change the time zone for existing apps.

### Multi-channel source attribution

A user might engage with an ad for the same app on multiple platforms, especially with very large multi-platform campaigns. When the user installs the app, multiple platforms may take credit for the install.

Snapchat Ads Manager:

* Counts each install occurring within the attribution window as an install attributed to Snapchat.
* Attributes in-app events up to 28 days after install.

AppsFlyer:

* Applies last touch attribution and credits only the last platform to show the user an ad that led to an install.
* Attributes in-app events to the source of the install up to 180 days.

This can lead to discrepancies as high as 40% between AppsFlyer and Snapchat Ads Manager.

> 👍 **Solution**
>
> Snapchat is just one mobile application, whereas other platforms own multiple mobile applications or mobile ad networks/exchanges. Due to their additional reach across multiple properties, it is possible that competitors might win the last touch, yet Snapchat is still driving significant value.
>
> Ultimately, AppsFlyer should be the dashboard used to evaluate eCPI and performance. When there is a discrepancy, default to AppsFlyer as the source of truth. Keep in mind that to fully evaluate the impact of your Snapchat campaigns, you should work with AppsFlyer to keep a record of the volume of conversions where Snapchat was a contributor to the conversion but was not the last touch. There is value to understanding this even if you attribute based on the last touch.
>
> To manage the discrepancy, advertisers should keep records of the approximate percentage of total conversions for which Snapchat was a contributor but not the last contributor and as such create a new eCPI goal for Snapchat based on this approximate delta.

### Fewer installs in raw data

In certain instances, due to raw data restrictions from Snapchat, installs via <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-knowledge-base-glossary?query=glossary#aggregated-advancedprivacy">Aggregated Advanced Privacy</Anchor> won't show in raw data reports. This means that advertisers may see on the AppsFlyer platform fewer installs in raw data than in aggregated data.

> 📄 **See also**
>
> <Anchor target="_blank" href="/marketers/ko/docs/skan-interoperation-with-snapchat">Snapchat and AppsFlyer SKAdNetwork interoperation</Anchor>

<div data-zendesk-anchors="h_01HE7RM7ME5JTFFC2MYSBG6SWC=source-of-discrepancies-and-solutions h_01HE7RM7MEYAZ42A1Y7X8J008Q=different-lookback-windows h_01HE7RM7ME31WACZRZDXRW5CNR=solutions h_01HE7RM7METGPE38QV8FAMW9WA=time-zone-differences h_01HE7RM7MEC91WZDZQMXZ4Q7DV=solution multichannel-source-attribution=multi-channel-source-attribution h_01HE7RM7ME2NAB9ET38P5JD82E=multi-channel-source-attribution h_01HE7RM7MFP65KYHFDZZTC8K3J=solution-1 h_01HE7RM7MFR4CSEK2HCZWB8BT9=fewer-installs-in-raw-data h_01HE7RP6VPPAY2CCSNTJ0RVSXM=see-also" />
