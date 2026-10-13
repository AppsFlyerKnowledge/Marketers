---
title: "Google Ads (AdWords)—Cost and ad revenue"
excerpt: "Enable Google Ads cost and ad revenue data in AppsFlyer."
x-zendesk:
  id: 4417309205521
  url: https://support.appsflyer.com/hc/en-us/articles/4417309205521-Google-Ads-AdWords-Cost-and-ad-revenue
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Google Ads
  section_id: 6551205645457
  position: 7
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-michael-talapov, Marketers, ROI360]
  labels: [Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-01-20T10:01:42Z'
  edited_at: '2026-08-19T06:49:25Z'
---
## Cost, clicks, and impressions

The cost integration provides the following aggregated data:

* Cost data for your campaigns, adsets, geos/countries, and channel levels. See the [ad network cost integration table](/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api) for full details on the supported dimensions, metrics, and features.  
  **Note:** Cost data requires an [ROI360](/docs/roi360-cost-aggregation-overview?query=xpend) subscription.
* Data on clicks, impressions, and enriched data (keywords, campaign names, and adset).

* MCC Accounts are supported.
* Make sure your campaign setup in Google Ads is for either an iOS or Android app; not both. If the campaign is for both apps, AppsFlyer can't break down the cost per app, and displays the combined cost for both apps.
* Data on cost, clicks, and impressions is currently not available for pre-registration campaigns due to limitations in Google Ads API.

To view Google Ads cost, click and impression data within the AppsFlyer dashboard, connect via your Google Ads configuration page. Once the connection is complete, AppsFlyer begins to query your Google Ads cost amounts, clicks, and impressions for all of your existing campaigns.

Read more about [setting up cost in Google Ads](/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory).

Read more about how Google defines clicks and views.

Read more about [Google Ads limitations](https://support.google.com/google-ads/answer/6163740).

**After the setup, data should come through within a few hours**.

Users can confirm they are logged in with the correct Google Ads account by checking the email address, which appears on the top right corner of the Google Ads dashboard.

If the Google Ads account is a sub-account of an MCC account, then the top right ID is the MCC's,  and the sub-account's ID is on the top left corner.

If it is not the correct account, sign out of the account and sign in again using the email address for a different Google account.

### Cost data sync status

[View your cost API status](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status) and the last time AppsFlyer managed to pull matching cost data in either the cost (and ad revenue) integration status dashboard, or in the individual ad network dashboard. 

Google Ads allows you to sync several accounts for pulling cost data. For each synced account, AppsFlyer shows the status of cost integration and the last time AppsFlyer managed to pull matching cost data.

### Stopping Google cost sync

**To stop syncing Google cost, delete the Google account connection:**

* [Go to the cost tab, in the actions column, hover over an account, click Delete connection.](/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab) Once deleted, AppsFlyer stops getting the cost. Deleting the connection does not impact historical data.

## Recording ad revenue with Google Ads

Google Ads (AdWords) revenue integration is deprecated as of November 30, 2020. For ad revenue data, AdWords customers need to migrate to [Google AdMob](/docs/google-admob-ad-revenue-attribution-configuration).

<Accordion title="FAQ">


Q. Why can't I see my cost data?
A. There are several possible reasons why you don't see the data:

When logging in, it is important to verify the right Google account is used.`<br/>`If you log in using the wrong Google account, no cost is pulled or displayed. In such a situation, you must remove the app from Google apps permissions and login with the correct account. To do so, follow these steps:
Click on the following URL: `[`https://myaccount.google.com/permissions](https://myaccount.google.com/permissions)

Remove AppsFlyer Cost on Google and login again.


In some cases, the agency cost integration is turned on but doesn't pull cost because the agency user who logged in doesn't have access to the correct Google ads customer ID. This results in the advertiser seeing incomplete cost data.
Make sure the agency user who logs into the Cost tab has access to the Google ads customer ID set up in the Integration tab.
`![](https://files.readme.io/2d17b3dad78e02c76253f30db0c15c18eb837b531becabc07ccad274258c2c61-49938966132753.png)`

Using spaces or special characters in iOS Search or Android Landing Page campaigns may cause issues with matching cost data to click data and leading to missing cost reporting.
When an agency disables a cost integration after cost is already collected, but the advertiser still has an active cost integration, the data is associated with the advertiser only from the day the agency disables the integration.

Q. Where is my geo-based click data?
A. In some cases, AppsFlyer receives partial Geo clicks data from Google. When this occurs AppsFlyer completes the missing clicks information from other Google sources, which lack the Geo data. Therefore, when grouping by Geo, the total number of clicks from Google's campaigns, may not match with the same number with another grouping dimension.

</Accordion>
<Accordion title="Traits and limitations">

``

| Trait | Remarks |
| --- | --- |
| Inactive and active campaigns | The Google integration supports cost data (cost, clicks, and impressions) for **inactive campaigns** (campaigns for which no installs or conversions were recorded in AppsFlyer) in the following cases:<br /><br />* App campaigns for installs (ACI campaign type)<br />* App campaigns for engagements (ACE campaign type)<br />* App campaigns for pre-registrations (ACPRE campaign type)<br /><br />For those app campaigns, AppsFlyer breaks down cost data by channel aligned to the attribution data. For example, ACI\_Display, ACI\_Youtube, ACI\_Search.<br /><br />For non-ACI and non-ACE campaigns, AppsFlyer reports cost data (cost, clicks, and impressions) for **active campaigns** only, meaning at least one conversion or install is recorded in AppsFlyer. Cost data is reported for the 7 day-window of the conversion/install. |
| Performance Max campaigns | Performance Max campaigns don't support cost data breakdown by country/geo. |

</Accordion>

**See also**

* For iOS 14-related considerations, see [Google Ads SKAdNetwork interoperability with AppsFlyer](/docs/get-skan-postback-data-from-google-ads).