---
title: "Google Ads (AdWords)—Cost and ad revenue"
excerpt: "Learn how to enable and configure Google Ads cost and ad revenue data integration in AppsFlyer."
---
Enable Google Ads cost and ad revenue data in AppsFlyer.

## Cost, clicks, and impressions

The cost integration provides the following aggregated data:

- Cost data for your campaigns, adsets, geos/countries, and channel levels. See the [ad network cost integration table](https://support.appsflyer.com/hc/articles/207040526-Ad-cost-measurement-guide#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features.

> 📘 Note
>
> Cost data requires an [ROI360](/docs/roi360-cost-aggregation-overview) subscription.

- Data on clicks, impressions, and enriched data (keywords, campaign names, and adset).
- MCC Accounts are supported.
- Make sure your campaign setup in Google Ads is for either an iOS or Android app; not both. If the campaign is for both apps, AppsFlyer can't break down the cost per app, and displays the combined cost for both apps.
- Data on cost, clicks, and impressions is currently not available for pre-registration campaigns due to limitations in Google Ads API.

To view Google Ads cost, click and impression data within the AppsFlyer dashboard, connect via your Google Ads configuration page. Once the connection is complete, AppsFlyer begins to query your Google Ads cost amounts, clicks, and impressions for all of your existing campaigns.

Read more about [setting up cost in Google Ads](https://support.appsflyer.com/hc/articles/115002504686#step-2-set-up-google-ads-on-appsflyer-mandatory).

Read more about [how Google defines clicks and views](https://support.appsflyer.com/hc/articles/360002190997-Click-and-view-definitions-by-major-integrated-partners#google).

Read more about [Google Ads limitations](https://support.google.com/google-ads/answer/6163740).

**After the setup, data should come through within a few hours**.

Users can confirm they are logged in with the correct Google Ads account by checking the email address, which appears on the top right corner of the Google Ads dashboard.

If the Google Ads account is a sub-account of an MCC account, then the top right ID is the MCC's, and the sub-account's ID is on the top left corner.

If it is not the correct account, sign out of the account and sign in again using the email address for a different Google account.

### Cost data sync status

[View your cost API status](https://support.appsflyer.com/hc/articles/360008850257#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard.

Google Ads allows you to sync several accounts for pulling cost data. For each synced account, AppsFlyer shows the status of cost integration and the last time AppsFlyer managed to pull matching cost data.

### Stopping Google cost sync

**To stop syncing Google cost, delete the Google account connection:**

- [Go to the cost tab, in the actions column, hover over an account, click Delete connection.](https://support.appsflyer.com/hc/articles/360008850257#deleting-connected-accounts-in-the-cost-tab) Once deleted, AppsFlyer stops getting the cost. Deleting the connection does not impact historical data.

## Recording ad revenue with Google Ads

Google Ads (AdWords) revenue integration is deprecated as of November 30, 2020. For ad revenue data, AdWords customers need to migrate to [Google AdMob](https://support.appsflyer.com/hc/articles/360006951817-Google-AdMob-ad-revenue-attribution-configuration).

## FAQ

<Accordion title="Why can't I see my cost data?">

There are several possible reasons why you don't see the data:

- When logging in, it is important to verify the right Google account is used.

If you log in using the wrong Google account, no cost is pulled or displayed. In such a situation, you must remove the app from Google apps permissions and login with the correct account. To do so, follow these steps:
1. Click on the following URL: [https://myaccount.google.com/permissions](https://myaccount.google.com/permissions)
2. Remove AppsFlyer Cost on Google and login again.
- In some cases, the agency cost integration is turned on but doesn't pull cost because the agency user who logged in doesn't have access to the correct Google ads customer ID. This results in the advertiser seeing incomplete cost data.

Make sure the agency user who logs into the Cost tab has access to the Google ads customer ID set up in the Integration tab.
- Using spaces or special characters in iOS Search or Android Landing Page campaigns may cause issues with matching cost data to click data and leading to missing cost reporting.
- When an agency disables a cost integration after cost is already collected, but the advertiser still has an active cost integration, the data is associated with the advertiser only from the day the agency disables the integration.

</Accordion>

<Accordion title="Where is my geo-based click data?">

In some cases, AppsFlyer receives partial Geo clicks data from Google. When this occurs AppsFlyer completes the missing clicks information from other Google sources, which lack the Geo data. Therefore, when grouping by Geo, the total number of clicks from Google's campaigns, may not match with the same number with another grouping dimension.

</Accordion>

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Inactive and active campaigns | The Google integration supports cost data (cost, clicks, and impressions) for **inactive campaigns** (campaigns for which no installs or conversions were recorded in AppsFlyer) in the following cases:<br>- App campaigns for installs (ACI campaign type)<br>- App campaigns for engagements (ACE campaign type)<br>- App campaigns for pre-registrations (ACPRE campaign type)<br>For those app campaigns, AppsFlyer breaks down cost data by channel aligned to the attribution data. For example, ACI\_Display, ACI\_Youtube, ACI\_Search.<br>For non-ACI and non-ACE campaigns, AppsFlyer reports cost data (cost, clicks, and impressions) for **active campaigns** only, meaning at least one conversion or install is recorded in AppsFlyer. Cost data is reported for the 7 day-window of the conversion/install. |
| Performance Max campaigns | Performance Max campaigns don't support cost data breakdown by country/geo. |

<Cards>
  <Card title="Google Ads SKAdNetwork interoperability with AppsFlyer" href="https://support.appsflyer.com/hc/articles/4403215779857">
    For iOS 14-related considerations, see Google Ads SKAdNetwork interoperability with AppsFlyer.
  </Card>
</Cards>