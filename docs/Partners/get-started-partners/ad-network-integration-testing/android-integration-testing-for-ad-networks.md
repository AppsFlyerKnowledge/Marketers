---
title: "Android integration testing for ad networks"
excerpt: "Test your AppsFlyer Android integration using the AppsFlyer Partner Integrations app to trigger postbacks and verify install and in-app event attribution."
x-zendesk:
  id: 4412945443857
  url: https://support.appsflyer.com/hc/en-us/articles/4412945443857-Android-integration-testing-for-ad-networks
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Ad network integration testing
  section_id: 6551070667537
  position: 13
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Mobile Attribution, Ad Networks]
  labels: [Ad Networks, Partners]
  promoted: false
  comments_disabled: true
  created_at: '2021-12-06T10:35:58Z'
  edited_at: '2024-01-04T10:46:04Z'
---
**At a glance:** Test your AppsFlyer Android integration using the AppsFlyer Partner Integrations app to trigger postbacks.

## Android integration testing

Testing consists of the following elements:

* Use the Android version of the AppsFlyer Partner Integrations app to generate test install and purchase in-app events. These tests, in turn, trigger postbacks sent to your endpoints. You also have the option to test login and registration in-app events.
* On receipt of the postbacks, verify that you are able to ingest them.

**Testing scope**

The following table lists test scenarios according to the setting combinations available.

For each scenario, you can test installs and in-app events. For in-app events, you can use [in-app event mapping](/docs/test-marketer-campaign-integration-with-the-ad-network#mapping-events) to map advertiser events to your events.

## Testing

Complete the prerequisites and then perform the test procedures in the sections that follow. The test sections each contain a table you can use to record your test results.

### Prerequisites

Complete the prerequisites before beginning to execute the test procedure.



| Prerequisites |
| --- |
| [Integrate the Android test app into your account.](/docs/turn-on-test-app-integration-for-ad-networks) |
| Verify that the test app is integrated into your account |
| [Map in-app events to your event names](/docs/test-marketer-campaign-integration-with-the-ad-network#mapping-events). Event names to be mapped: `purchase`, `login`, `registration` |
| [Prepare attribution link](/docs/ios-integration-testing-for-ad-networks#attribution-link) |
| Test install attribution using a device running Android |
| Test in-app event attribution using an Android device |
| Test retargeting attribution using an Android device |



### Test install attribution

**To trigger postbacks:**

1. Send the attribution link previously prepared to a test device.
2. Click on the link, install and then open the app.  
   The **Install Data** page displays.
3. Validate the attribution using the following parameters. If the validation fails, see [Troubleshooting](/docs/ios-integration-testing-for-ad-networks#troubleshooting).

   1. `install_time`: near the current time. Time is in UTC.
   2. `af_status: Non-organic` If this is not the case, the install was not attributed.
   3. `media_source`: your ad network
4. Tap **In-App Event Tests.**
5. Tap **Purchase Event.**  
   The Purchase Event confirmation displays.
6. Verify that:
   1. You received install and purchase postbacks.
   2. The event name is mapped correctly (if you mapped in-app events).
   3. You are able to ingest the postback.

## Supplementary information and procedures

### About the Partner Integrations test app

The Partner Integrations app is available in Google Play. The app sends install and in-app events to the AppsFlyer platform.

When the app is opened for the first time, the **Install Data** page displays the conversion data recorded in the AppsFlyer platform. Test in-app events are triggered in the user interface.

The following functions are available:

* **In-App Event Tests**Send `purchase`,`login`, and `registration` and in-app events. By mapping the app in-app event names to your event names, postbacks are populated using your event names.

### Attribution link

Prepare an attribution link in the AppsFlyer dashboard, using one of the following methods:

* Generate the link in the AppsFlyer dashboard.
* Edit the example link that follows.

**To generate a link in the dashboard:**

1. In AppsFlyer, from the top menu, select to **My Apps**.
2. Select **adNetworkTest**.
3. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations** > select your ad network > **Attribution link** tab.
4. In the Attribution link tab, set the parameters listed. You can add additional parameters if required. Link to attribution linkd
   

| Parameter | Example value | Remark |
| --- | --- | --- |
| Campaign | c-test-2020-12-20 | Set a value that is identifiable in your postbacks |
| PID | pitestap |  |


5. Copy the resulting link for later use.

**Example attribution link:**

```
https://app.appsflyer.com/com.appsflyer.adNetworkTest?pid=pitestap_int&c=c-test-2020-12-20
```

### Test app integrated in your account

**To verify that the test app is available in your account:**

1. In AppsFlyer, from the top menu, go to **My Apps**.
2. Verify that the app **Partner Integrations adNewtorkTest** displays under Available Apps. If this is not the case, contact your Partner Development Manager.

### Troubleshooting



| Symptom | Cause/corrective action |
| --- | --- |
| The install time is not the current time | The app was not deleted before the install.<br /><br />Delete the app and repeat the procedure. |
| The media source is not your media source | Verify that you have set the correct **pid** value on the attribution link. Verify that you are using the correct attribution link |
| af\_status is Organic | Check the format of the attribution link, especially the value of **pid**. |



### Test retargeting attribution

You can also test retargeting attribution. The process is almost the same except for one parameter that you add to the attribution link.

Generate a new attribution link and add the parameter `is_retargeting=true` to it.

```
https://app.appsflyer.com/com.appsflyer.adNetworkTest?pid=YOUR_PID&c=YOUR_CAMPAIGN&af_click_lookback=7d
          &clickid={clickid}&is_retargeting=true
```

Install the app using the retargeting link. The flow is the same as described in [testing install attribution](/docs/android-integration-testing-for-ad-networks#test-install-attribution).

### Viewing retargeted installs in the dashboard

Access your AppsFlyer dashboard and click on **Re-targeting** in the left-side menu. Allow up to 30 minutes for the retargeted install to appear in the dashboard.

[![com_appsflyer_adNetworkTest-retargeting.png](https://files.readme.io/e46789b004be2f4fc15f095ba11a0f3f5d03abb1240e54e4b534285e3e4efd8d-21266228899601.png)](https://files.readme.io/e46789b004be2f4fc15f095ba11a0f3f5d03abb1240e54e4b534285e3e4efd8d-21266228899601.png)

### Test view-through attribution

1. In AppsFlyer, go to **My Apps**.
2. Select **adNetworkTest**.
3. In AppsFlyer, from the side menu, select **Collaborate** > **Active Integrations** > select your ad network > **Integration** tab.
4. Make sure that **Enable view-through attribution** is ON.
5. Copy the Impression attribution link.

   ```
   https://impression.appsflyer.com/com.appsflyer.adNetworkTest?pid=YOUR_PID&c=YOUR_CAMPAIGN&af_viewthrough_lookback=24h&advertising_id=YOUR_GAID&af_siteid=YOUR_SITEID
   ```

   Replace the parameters as follows:

   * YOUR\_PID - your partner ID supplied by AppsFlyer (ending with *\_int*)
   * YOUR\_CAMPAIGN - any campaign name
   * YOUR\_GAID - your Google Advertising ID
   * YOUR\_SITEID - any site ID

   Note: the parameters in the link are the basic parameters used here for the purpose of testing. You can have other parameters in the view-through attribution link according to your requirements.
6. Send the view-through attribution link to the test device.
7. Open the link in the browser and install the app from the store.
8. Launch the app.  
   The following screen displays:

   ![vta-testing-postback.png](https://files.readme.io/88b6720928d7540eeb2fe8f42f39ecdccc04655aa49f95d08dba5741d5e39982-4831106525457.png)

   If you don't see this message, make sure that the view-through attribution link is formatted correctly. Uninstall the app and reinstall using the view-through attribution link with the new test device.

Tip

For more elaborate results, repeat the installation process using the view-through attribution link with the new test device. Uninstall the app, change the parameters in the link (the campaign name, af\_siteid, and advertising\_id), and install again by clicking the URL.

### View installs in the dashboard

Once you install and launch the app, you can see the results in your AppsFlyer dashboard.

Allow up to 30 minutes for the install to appear in the app dashboard.

### Raw data export

Data related to apps whose install is attributed to your ad network can be exported in CSV format.

The data includes the following:

* Installs
* In-app events
* Retargeting installs
* In-app events of apps installed from retargeting campaigns

**To export raw data**:

1. In AppsFlyer go to, **Report** > **Raw data export**.
2. Select the date range.
3. Select a report.  
   The report downloads within a few minutes.

### Verify postback data

Every install generates a postback that is sent to your servers. To verify the postback URL, its structure, and the parameters that are appended to it, export the **Installation postbacks** report.

The **Installation postbacks** report contains a column titled **Postback URL**. This column lists the postback URLs as generated for each and every install.

Review the data in that column to verify the following:

* The URL endpoint is the correct one
* The parameters appended to the URL correspond to those appended to the AppsFlyer attribution link
* The **Postback Error Message** column is empty