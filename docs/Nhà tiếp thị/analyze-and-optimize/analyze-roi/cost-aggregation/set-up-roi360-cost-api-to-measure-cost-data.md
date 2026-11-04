---
title: Set up ROI360 cost API to measure cost data
metadata:
  keywords:
    - ROI
    - cost
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-19T12:50:13Z'
  edited_at: '2026-10-22T11:50:52Z'
  id: 360008850257
  locale: en-us
  section: Cost aggregation
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360008850257-Set-up-ROI360-cost-API-to-measure-cost-data
---
> **At a glance:** Get aggregate marketing cost data, including cost-related LTV (Lifetime Value) performance metrics, using Cost API at the media source account level.

<div id="overview" />

## Overview

ROI360 provides aggregate marketing cost data, including cost-related LTV performance metrics, at the ad account level.

Cost integrations are configured in **Cost settings**, where each integration connects to one media source account and measures the cost of all the apps you select. Depending on the ad network, this can include mobile, CTV, PC and console, and web apps. Connect each media source account once to enable cost for multiple apps.

Cost integrations can also be created and edited from the **Cost** tab in Partner Marketplace. Either entry point produces the same account-level integration.

<div id="note" />

> 📘 **Note**
>
> Access to **Cost settings** is controlled by role permissions. If you can't open **Cost settings**, ask your administrator to update your role permissions on the **User Management** page. The relevant capability is **Cost Connections**.

<div id="create-a-new-api-cost-integration" />

## Create a new API cost integration

Every cost integration follows the same two steps: authenticate with the media source, then name the integration and select the apps it covers. Some media sources require one additional step so AppsFlyer can match your apps to the identifiers used in their system.

After initial configuration, cost data appears in the dashboard with the next data pull, scheduled every four hours, six times a day.

<div id="h_01M43Y9WQ8WCXWQ0S9ZAT59CWW" />

<Accordion title="Step 1: Provide credentials">

1. In AppsFlyer, from the side menu, select **Settings** > **ROI360** > **Cost settings**.
2. Click **+ New integration**, select the media source, then click **Next**.
3. Depending on the media source, you'll see one of the following:
   * **Login:** log in with your ad network account and complete the authentication flow. AppsFlyer validates the connection and names the integration after the account you connected.
   * **Credentials:** provide static credentials, complete the fields shown for that media source, for example a username and password, or an API key. Field names vary by media source. Static credentials aren't validated at setup.
4. Rename the integration if you'd like something different, or keep the default name. The name has a 50-character maximum, and it's a label that helps you identify the integration later, which matters if you create more than one for the same media source.

</Accordion>

<div id="h_01M43Y9WQ8HK1N0GJNW5BH4MPZ" />

<Accordion title="Step 2: Select apps">

Click **Select apps** and choose the apps this integration covers. You can select any app you have permission to access, mobile, web, CTV, or any other platform you use to run your campaigns. Click **Apply**, then **Next**.

If the media source requires an additional step, continue to [Step 3](#additional-steps-specific-media-sources-only) below. Otherwise, click **Save integration**.

</Accordion>

<div id="additional-steps-specific-media-sources-only" />

<Accordion title="Step 3: Additional steps (specific media sources only)">

Some media sources require one additional step after you select apps. Add either mapping to package names and bundle IDs, or to site IDs.

<div id="map-apps-to-package-names-or-bundle-ids" />

#### Map apps to package names or bundle IDs

There are media sources that identify apps by Android package name or iOS bundle ID, for example, AppLovin.

As part of the cost configuration, after you select your apps, enter the exact package name or bundle ID for each app, as it appears in the media source's system. Every app requires a mapping value. Click **Save integration**.

<div id="map-apps-to-site-ids" />

#### Map apps to site IDs

For media sources that identify apps by site ID, for example, Liftoff.

After you select your apps, choose a default site ID parameter. It applies to every app in the integration. Available patterns:

* `${APP_ID}`
* `${APP_NAME}`
* `${APP_ID}_${APP_NAME}`
* `${APP_NAME}_${APP_ID}`

To override the default for a specific app, select a different parameter from that app's **Site ID** dropdown. Use this when an app's site ID is formatted differently in the media source's system. Click **Save integration**.

<div id="note-1" />

> 📘 **Note**
>
> Site ID mapping makes sure the AppsFlyer attribution link site ID macros match the value the media source expects. If your attribution link uses macros that differ from the mapping you select, site ID data won't populate correctly.

<div id="select-which-ad-account-to-pull-cost-from" />

#### Select which ad account to pull cost from

For some media sources, like TikTok, one login can have access to several ad accounts. After you log in to the media source, you need to select the specific ad account yourself.

</Accordion>

<div id="edit-and-delete-an-integration" />

## Edit and delete an integration

This works the same way for every integration, regardless of which entry point, **Cost settings** or the **Cost** tab, you used to create it.

<div id="h_01M43Y9WQ804YMN8TZ7HGYSQH7" />

<Accordion title="Edit a cost integration">

1. In AppsFlyer, from the side menu, select **Settings** > **ROI360** > **Cost settings**.
2. Click the media source you want to edit.
3. In the media source page, click the specific account you want to edit.
4. On the **Apps** tab, click **Edit** to add or remove apps, then save your changes.

Apps added to an integration that uses an additional step must be mapped before you can save the changes. The **Integration details** tab shows the connection settings.

</Accordion>

<div id="h_01M43Y9WQ89XKB2CN2EY4TG2AD" />

<Accordion title="Delete a cost integration">

1. In AppsFlyer, from the side menu, select **Settings** > **ROI360** > **Cost settings**.
2. Click the media source you want to delete from.
3. In the media source page, in the **Action** column, click the delete icon for the specific account you want to remove.
4. In the confirmation dialog, click **Yes, delete**.

Cost data collection stops immediately. Historical cost data isn't affected.

</Accordion>

<div id="h_01M43Y9WQ8ANZY2KNHKMV67YNY" />

<Accordion title="Transfer an app to another account">

Cost integrations are disconnected automatically when an app is transferred to a different account.

</Accordion>

<div id="view-cost-api-status" />

## View Cost API status

Cost integration status is reported at two levels.

* **App level:** every app included in an integration has its own status. This is where the actual state of data collection is reported.
* **Connection level:** each integration shows a single status, derived from the statuses of the apps within it. When all apps share the same status, the connection shows that status. When apps have different statuses, the connection shows **Mixed**. Mixed doesn't indicate a problem with the connection itself, it means the apps aren't in a uniform state. Open the integration to see which apps are affected.

Status is available in the following places:

| Where | Level shown |
| --- | --- |
| Cost settings | Both connection level and app level |
| Cost (and ad revenue) integration status dashboard | App level, across all media sources with cost integration enabled in your account and the agency account you work with. Mixed status isn't shown. |
| Cost tab | App level, for one app and one media source at a time |

<div id="view-status-in-cost-settings" />

<Accordion title="View status in Cost settings">

1. In AppsFlyer, from the side menu, select **Settings** > **ROI360** > **Cost settings**.
2. Select the relevant media source. The **Status** column shows the connection-level status for each integration.
3. To see app-level status, click the integration row to open the **Cost integration** page, then view the status of each app in the list.

</Accordion>

<div id="view-status-in-cost-tab" />

<Accordion title="View status in Cost tab">

Relevant for media sources that support getting cost data via API. This view shows the status for the selected app, along with the last time AppsFlyer successfully pulled matching cost data for it.

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Active integrations**.
2. Select the media source.
3. From the App list above the tab bar, select the app whose cost status you want to view.
4. Click the **Cost** tab to see the status and last sync time.

</Accordion>

<div id="h_01M43Y9WQ8H8ANPDEGYCH0T0MF" />

<Accordion title="Status table">

The following table lists every cost integration status and what it means.

| Status | Remarks/action required |
| --- | --- |
| Active | Integration is enabled and successfully connected to the media source. AppsFlyer is pulling cost data. |
| Advertiser account not enabled | The connected ad account isn't enabled for cost data collection on the media source side. Contact the media source to enable API access for the account, then reconnect the integration. |
| General error | An unexpected failure occurred during the pull. AppsFlyer retries on the next scheduled pull. If the status persists, contact AppsFlyer support. |
| Invalid credentials | AppsFlyer can't get data via the API because the credentials aren't valid. Reconnect using the correct credentials. |
| Missing credentials | You haven't configured credentials for this integration. Add the required credentials in Cost settings or in the partner's Cost tab. |
| No active campaigns | Usually, the integration pulls the cost of only campaigns that have conversions in AppsFlyer. In this pull, no such campaigns were found during the selected period. No action is required. AppsFlyer reports this as a successful pull. |
| No data | The partner API responded but returned no data. This usually happens because your campaigns are paused and there's no data to pull. No action is required unless you expect campaigns to be running. If they are, review the integration. |
| Partner API is not responding | The integrated partner's server isn't responding to AppsFlyer, or the partner API rate-limited the request. AppsFlyer retries on the next scheduled pull. Wait six hours. If the status persists, contact AppsFlyer support. |
| The partner API is not returning data for the information provided. Check the configuration | The media source didn't return data despite active campaigns (campaigns with conversions in AppsFlyer), which points to a misconfiguration at the media source level. Reconnect the account via OAuth and verify the right ad account was selected. |
| Waiting for sync | The account or app is still syncing with the ad network. Wait for the sync to complete. |
| Mixed | Shown in Cost settings > Media source page only, when the apps in an integration have different statuses. Open the Integration page to view the status of each app. Not displayed on the status dashboard. |

</Accordion>

<div id="cost-integration-and-agencies" />

## Cost integration and agencies

If an advertiser uses an agency to run their campaigns, we recommend that the agency, and not the advertiser, integrate with the relevant partners. Otherwise, cost data is duplicated if both the advertiser and agency integrate with a media source using the same credentials for the same app.

If an advertiser stops working with an agency, cost data is still pulled if the agency still has cost configured for the app. The advertiser must ask the agency to delete their cost integration to stop this data from being pulled.

<div id="traits-and-limitations" />

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Agencies | Agencies can't use Cost settings to perform cost integrations across multiple apps simultaneously, but can use the Cost tab in Partner Marketplace to do so. |
| Future apps automatically inherit the cost settings feature in account-level Cost settings | Currently not supported. |
| Cost data behavior when the advertiser and agency connect to the same ad network | If both an advertiser and an agency connect to cost integration for the same ad network account (for example, Google Ads), cost data is pulled from the account that receives attribution. Example: the advertiser connects using advertiser credentials, the agency connects using agency credentials, and attribution is assigned to the agency account. Result: ROI360 pulls cost data from the agency connection, and the advertiser connection shows as No data. |
| Google cost integration automatic disconnection | Cost integrations that show a No data or Invalid credentials status for more than 365 consecutive days are automatically disconnected. This currently applies only to Google cost integrations. |
| TikTok advertiser ID list configuration | Configure the advertiser ID list at the account level using only advertiser IDs connected to the TikTok user in the ad network. Advertiser IDs added to the list that aren't aligned with the user in the ad network don't return cost data. |

<div data-zendesk-anchors="h_01K9S0A1PRMX3VBGHTNQ8C5FJW=overview h_01M43Y9WQ83AK0KTKB9XM8FGM6=note h_01K9S0A1PTQW9YJM3C4LKZRHFB=create-a-new-api-cost-integration h_01K9S0A1PVCXZ3NQ7MWFKTJRH8=additional-steps-specific-media-sources-only h_01M43Y9WQ8HNRN4ZKWRBT9QY9G=map-apps-to-package-names-or-bundle-ids site-id-mapping=map-apps-to-site-ids h_01K3DGA6SKDTTPY8Q1JBTCTY7H=map-apps-to-site-ids h_01M43Y9WQ8V94HB74M6CAKC9PB=note-1 h_01M43Y9WQ8P3XATJS0TBB27ZPQ=select-which-ad-account-to-pull-cost-from deleting-cost-integrations=edit-and-delete-an-integration h_01K3DGA6SKF8ZA5M9AW6DA0V3J=edit-and-delete-an-integration h_01K9S0A1PWRNK08ZQXCF5V3YTM=view-cost-api-status h_01K9S0A1PXJQF2NVC9ZRMLK6HT=view-status-in-cost-settings h_01K9S0A1PYMBX4RQJZC8TNVK3F=view-status-in-cost-tab h_01K9S0A1PZQXN4RTC7VWBLKM9H=cost-integration-and-agencies specification-and-limitation=traits-and-limitations h_01K3DGA6SKVZ347ZDY599S0Y7Y=traits-and-limitations" />
