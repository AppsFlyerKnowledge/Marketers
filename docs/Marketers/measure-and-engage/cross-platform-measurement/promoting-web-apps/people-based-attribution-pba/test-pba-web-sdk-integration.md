---
title: Test PBA web SDK integration
metadata:
  keywords:
    - Developers
    - PBA
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-09-01T19:09:41Z'
  edited_at: '2024-01-11T11:04:05Z'
  id: 360012729178
  locale: en-us
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360012729178-Test-PBA-web-SDK-integration
---
> **At a glance:** Test the Web SDK PBA plugin integration.

## Test PBA web events

**Principles of using the test page**

Web SDK sends web events to PBA, which are made available via PBA dashboards and raw data reports, after daily processing. To enable an efficient testing process, you send test events without waiting for daily processing. Test events are:

* Parsed and validated on receipt.
* Made available to you in the user interface. This includes processing errors. If they exist, send corrected events again to make sure they are processed correctly.
* Are processed like any other event during daily processing. This means they are added to the dashboards and raw data.

#### Web SDK integration test page

<div id="page-main-view" />

<table><tbody><tr><td><p><strong>Page main view</strong></p><p><a href="https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg"><img alt="TestScreen_us-en.jpg" src="https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg"/></a></p><ul><li>The most recent events appear first.</li><li><strong>Event cache</strong>:<ul><li>Contains up to 100 events</li><li>Older events are deleted to make way for newer events</li><li>Cached events are deleted after 24 hours</li></ul></li><li><strong>Page controls</strong>:<ul><li><strong>Refresh rate indicator</strong>: The page refreshes automatically every 5 seconds.</li><li><strong>Clear all</strong>: Clears events from the cache permanently. <strong>Note!</strong> The cache is common to websites sharing the same web dev key. Thus, if another developer is using the test page, it will clear for them as well. </li><li><strong>Pause/start</strong>: Pauses automatic refresh. New events don't display until you click start. </li></ul></li></ul><p><strong>Event table columns</strong></p><table><thead><tr><th>Field</th><th>Description</th></tr></thead><tbody><tr><td>Time (UTC)</td><td>Event time</td></tr><tr><td>Event type</td><td><p>Event types are as follows:</p><ul><li>Events sent by you:<ul><li><code>EVENT</code></li><li><code>setCustomerUserId</code></li><li><code>pageLoad</code>: Sent by the web SDK each time a page is loaded/refreshed on your website</li></ul></li></ul></td></tr><tr><td>Event content</td><td><p>The event payload, as recorded by PBA.</p></td></tr><tr><td>Comments</td><td><ul><li><strong><span>Valid</span></strong>: PBA received and recorded the event. No further action is required.</li><li><strong>Invalid</strong>: List of errors requiring corrective action. The error message format is:<br/>event field name: error description </li><li>Hover over error messages to see details:<br/><p><img alt="PBAWebSDKTestingErrorMessagesPopup_en-us.png" src="https://files.readme.io/0e050e60dbf9f1289880b5d58c4885d4be66392265986eaf4b2f76876697e429-360011317358.png"/></p></li></ul></td></tr></tbody></table></td></tr><tr><td><p><strong>Drill-down view<br/><br/></strong><a href="https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png"><img alt="mceclip0.png" src="https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png"/></a></p><p>Click an event row to display its contents after processing. See <a href="./pba-web-sdk-integration-guide#web-sdk-event-parameters" target="_blank">Web SDK event parameters</a> for additional information</p></td></tr></tbody></table>

## Procedures

Complete the procedures that follow.

<div id="enable-test-mode" />

<Accordion title="Enable test mode">

**Prerequisites**

Before testing, <Anchor target="_blank" href="/marketers/docs/pba-web-sdk-integration-guide#installation-and-integration">the web SDK must be implemented on your website</Anchor> or on a test website.

**Browser limitation**

If test mode is enabled on a given browser, irrespective of the tab; the browser can only be used to connect to the website specified and not to any other website. Use a different browser, for example, Safari instead of Chrome, to connect from the same machine to a different website.

**To enable test mode:**

1. **Verify that the SDK is loaded:**
   1. In AppsFlyer, from the top menu, select **My Apps** > **View brand** **bundles**.
   2. Select the required **Web SDK integration test.** The integration page opens. The web dev key is displayed.  

      [![pba_web_sdk_integration_test_web_dev_key_en-us.png](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)
   3. In a new browser tab, go to your website (that has the Web SDK installed).
   4. Right-click and select inspect to open the browser developer tools.
   5. Go to the **Console** tab.
   6. In the console, enter:  

      ```javascript
      window.AF_SDK.initPluginsConfig.pba.webAppId
      ```

      The webAppID displays.

      [![testing_pba_integration_webappid_check_en-us.png](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)
   7. Verify that the webAppID is identical to the web dev key in the **Web SDK integration test** page.
2. **Enable test mode**:
   1. In the website browser tab, go to the **Console** tab.
   2. Enter:

      ```javascript
      window.AF_SDK.PLUGINS.PBA.turnOnDevMode()
      ```

      The function returns `undefined`.

      [![testing_pba_integration_turnondevmode.png](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)
3. **Verify that test mode is enabled:**
   * In **Console** tab, Enter:  

     ```javascript
     window.AF_SDK.PLUGINS.PBA.isDevModeOn()
     ```

     The return value is `true`. This indicates that test mode is active.   
     [![PBATestingWebSDKIntegrationIsDevModeOn_en-us.png](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)

</Accordion>

<div id="send-test-events" />

<Accordion title="Send test events">

* In test mode, events that you send are displayed in the test integration page
* Note! Test events are processed and subsequently will be included in PBA reports. To avoid distorting reports, populate `eventRevenue` with low (small) values. If no value is sent, PBA populates it with 0.

Send example events of each of the types described.

| Step | Action<br /><br />(Enter commands) | Web SDK test integration page<br /><br />(Expected result) |
| --- | --- | --- |
| 1 | Open a new tab in the browser and browse to any page on your website. | PBA registers a `'pageLoad'` event whenever your website opens/refreshes:<br /><br />[<Image alt="PBATestingWebSDKPageLoadEvent_en-us.png" src="https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png" width="226px" />](https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png) |
| 2 | Login/register to your website as a user <Anchor target="_blank" href="/marketers/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">to trigger a setCustomerUserId event</Anchor>. | [<Image alt="mceclip3.png" src="https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png" width="226px" />](https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png) |
| 3 | <Anchor target="_blank" href="/marketers/docs/pba-web-sdk-integration-guide#recording-event-scenarios">Start sending web events</Anchor> to verify PBA processes them correctly.<br /><br />**Note:**<br /><br />If not specified, `eventRevenue` and `eventRevenueCurrency` are populated with default values:<ul><li>`eventRevenueCurrency: "USD"`</li><li>`eventRevenue: 0`</li></ul>[<Image alt="PBAWebSDKTestEventEVENT_en-us.png" src="https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png" width="233px" />](https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png)<br /><br />See <Anchor target="_blank" href="/marketers/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">Web SDK event parameters for additional details.</Anchor> | [<Image alt="mceclip5.png" src="https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png" width="226px" />](https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png) |

</Accordion>

## Troubleshooting

<div id="events-do-not-display-in-the-test-page" />

<Accordion title="Events do not display on the test page">

1. In the browser developer tools, go to **Network** tab.
2. In the filter field, enter "websdk."
3. Based on the HTTP response code, proceed as follows:
   * 200: Reach out to AppsFlyer technical support.
   * 400: Check that all parameters are enclosed in " ".

</Accordion>

<div data-zendesk-anchors="h_01HKW32BE04AKHFMY853211C1A=test-pba-web-events h_01HKW32BE0Z2ZKTBHSCSWVT04N=web-sdk-integration-test-page h_01HKW32BE0VA0X9ZX4Z26EY6CZ=procedures h_01HKW32BE08Z9CCMBPK4Z0854C=enable-test-mode h_01HKW32BE0E4A1W221FKY97EZB=send-test-events h_01HKW32BE1HFV0NM64QMASBCCT=troubleshooting h_01HKW32BE1QHV0W6ZDYHG94RQA=events-do-not-display-in-the-test-page" />
