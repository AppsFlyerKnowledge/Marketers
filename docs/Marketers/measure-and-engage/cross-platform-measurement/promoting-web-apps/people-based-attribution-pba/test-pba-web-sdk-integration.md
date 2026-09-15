---
title: "Test PBA web SDK integration"
excerpt: "Learn how to test the Web SDK PBA plugin integration, send test events, and troubleshoot common issues."
---
Test the Web SDK PBA plugin integration. 

## Test PBA web events

**Principles of using the test page**

Web SDK sends web events to PBA, which are made available via PBA dashboards and raw data reports, after daily processing. To enable an efficient testing process, you send test events without waiting for daily processing. Test events are:

- Parsed and validated on receipt.
- Made available to you in the user interface. This includes processing errors. If they exist, send corrected events again to make sure they are processed correctly.
- Are processed like any other event during daily processing. This means they are added to the dashboards and raw data.

#### Web SDK integration test page

| **Page main view** |
| --- |
| <Image src="https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg" alt="TestScreen_us-en.jpg" /> |

- **Event cache**:
  - Contains up to 100 events
  - Older events are deleted to make way for newer events
  - Cached events are deleted after 24 hours
- **Page controls**:
  - **Refresh rate indicator**: The page refreshes automatically every 5 seconds.
  - **Clear all**: Clears events from the cache permanently. 
    > 📘 Note
    >
    > The cache is common to websites sharing the same web dev key. Thus, if another developer is using the test page, it will clear for them as well.
  - **Pause/start**: Pauses automatic refresh. New events don't display until you click start.

**Event table columns**

| Field | Description |
| --- | --- |
| Time (UTC) | Event time |
| Event type | Event types are as follows:<br>- Events sent by you:<br>  - `EVENT`<br>  - `setCustomerUserId`<br>  - `pageLoad`: Sent by the web SDK each time a page is loaded/refreshed on your website |
| Event content | The event payload, as recorded by PBA. |
| Comments | - **Valid**: PBA received and recorded the event. No further action is required.<br>- **Invalid**: List of errors requiring corrective action. The error message format is:<br>  <br>  event field name: error description <br>- Hover over error messages to see details:<br>  <br>  <br>  <Image src="https://files.readme.io/0e050e60dbf9f1289880b5d58c4885d4be66392265986eaf4b2f76876697e429-360011317358.png" alt="PBAWebSDKTestingErrorMessagesPopup_en-us.png" /> |
| **Drill-down view** | <Image src="https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png" alt="mceclip0.png" /><br>Click an event row to display its contents after processing. See [Web SDK event parameters](https://support.appsflyer.com/hc/articles/360001610038-New-Web-SDK#web-sdk-event-parameters) for additional information |

## Procedures

Complete the procedures that follow.

### Enable test mode

**Prerequisites**

Before testing, [the web SDK must be implemented on your website](https://support.appsflyer.com/hc/articles/360001610038-PBA-web-SDK-integration-guide#installation-and-integration) or on a test website.

**Browser limitation**

If test mode is enabled on a given browser, irrespective of the tab; the browser can only be used to connect to the website specified and not to any other website. Use a different browser, for example, Safari instead of Chrome, to connect from the same machine to a different website.

**To enable test mode:**

1. **Verify that the SDK is loaded:**
   1. In AppsFlyer, from the top menu, select **My Apps** > **View brand** **bundles**.
   2. Select the required **Web SDK integration test.** The integration page opens. The web dev key is displayed.
      
      <Image src="https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png" alt="pba_web_sdk_integration_test_web_dev_key_en-us.png" />
      
   3. In a new browser tab, go to your website (that has the Web SDK installed).
   4. Right-click and select inspect to open the browser developer tools.
   5. Go to the **Console** tab.
   6. In the console, enter:
      
      ```javascript
      window.AF_SDK.initPluginsConfig.pba.webAppId
      ```
      
      The webAppID displays.
      
      <Image src="https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png" alt="testing_pba_integration_webappid_check_en-us.png" />
      
   7. Verify that the webAppID is identical to the web dev key in the **Web SDK integration test** page.
2. **Enable test mode**:
   1. In the website browser tab, go to the **Console** tab.
   2. Enter:
      
      ```javascript
      window.AF_SDK.PLUGINS.PBA.turnOnDevMode()
      ```
      
      The function returns `undefined`.
      
      <Image src="https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png" alt="testing_pba_integration_turnondevmode.png" />
3. **Verify that test mode is enabled:**
   - In **Console** tab, Enter:
     
     ```javascript
     window.AF_SDK.PLUGINS.PBA.isDevModeOn()
     ```
     
     The return value is `true`. This indicates that test mode is active.
     
     <Image src="https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png" alt="PBATestingWebSDKIntegrationIsDevModeOn_en-us.png" />

### Send test events

- In test mode, events that you send are displayed in the test integration page
- > 🚧 Warning
  >
  > Test events are processed and subsequently will be included in PBA reports. To avoid distorting reports, populate `eventRevenue` with low (small) values. If no value is sent, PBA populates it with 0.

Send example events of each of the types described.

| Step | Action<br>(Enter commands) | Web SDK test integration page<br>(Expected result) |
| --- | --- | --- |
| 1 | Open a new tab in the browser and browse to any page on your website. | PBA registers a `'pageLoad'` event whenever your website opens/refreshes:<br><Image src="https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png" alt="PBATestingWebSDKPageLoadEvent_en-us.png" /> |
| 2 | Login/register to your website as a user [to trigger a setCustomerUserId event](https://support.appsflyer.com/hc/articles/360001610038-PBA-web-SDK-integration-guide#setting-customer-user-id-after-signup). | <Image src="https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png" alt="mceclip3.png" /> |
| 3 | [Start sending web events](https://support.appsflyer.com/hc/articles/360001610038-PBA-web-SDK-integration-guide#recording-event-scenarios) to verify PBA processes them correctly.<br>**Note:**<br>If not specified, `eventRevenue` and `eventRevenueCurrency` are populated with default values:<br>- `eventRevenueCurrency: "USD"`<br>- `eventRevenue: 0`<br><Image src="https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png" alt="PBAWebSDKTestEventEVENT_en-us.png" /><br>See [Web SDK event parameters for additional details.](https://support.appsflyer.com/hc/articles/360001610038-PBA-web-SDK-integration-guide#web-sdk-event-parameters) | <Image src="https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png" alt="mceclip5.png" /> |

## Troubleshooting

### Events do not display on the test page

1. In the browser developer tools, go to **Network** tab.
2. In the filter field, enter "websdk."
3. Based on the HTTP response code, proceed as follows:
   - 200: Reach out to AppsFlyer technical support.
   - 400: Check that all parameters are enclosed in " ".