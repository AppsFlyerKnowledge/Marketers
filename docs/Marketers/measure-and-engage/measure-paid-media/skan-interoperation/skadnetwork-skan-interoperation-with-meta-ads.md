---
title: "SKAdNetwork (SKAN) interoperation with Meta ads"
excerpt: "Interoperability enables Meta ads to share decoded SKAN data with AppsFlyer and enables AppsFlyer to share your CV measurement bits with Meta ads."
---
**At a glance:** Interoperability enables Meta ads to share decoded SKAN data with AppsFlyer and enables AppsFlyer to share your CV measurement bits (mapping) with Meta ads.

![](https://fast.wistia.com/embed/medias/15jnbml3h7/swatch)

## SKAN interoperability: AppsFlyer &lt;-> Meta ads

If you work with multiple ad network partners, it is best to set it up in AppsFlyer. By doing so, SKAN performance metrics, enriched with other metrics like cost, are available via the AppsFlyer platform.

#### Scope of SKAN interoperability with Meta ads

The interoperation with Meta ads allows the following:

* AppsFlyer and Meta ads share the SKAN conversion value (CV) schema, enabling both to provide you with performance metrics.
* AppsFlyer supports all Meta ads campaign objectives which enable campaign optimization:
  * Mobile app install (MAI)
  * Mobile app engagement (MAE)
  * Value optimization (VO)
* After enabling SKAN integration the following occurs:
  * Facebook SDK stops updating SKAN CV (*kill switch)*.
  * AppsFlyer SDK updates the CV.
  * Meta ads shares SKAN postback data for inclusion in the SKAN dashboard and aggregated reports.

Other considerations:

* If you don't enable SKAN partner integration, in the SKAN dashboard, installs brought by Meta ads are counted as organic installs.
* In the context of AppsFlyer attribution (Overview dashboard):
  * Consenting user installs brought by Meta ads are attributed correctly.
  * Non-consenting users are attributed to organic.
* [iOS 14.5 implications on SRN reporting](/docs/self-reporting-networks-srns#ios-145-srn-attribution)
* Our MMP integration with Meta ads always implements the *Advertiser Tracking Enabled* flag. (This information is provided according to the Meta ads app guidance iOS 14 checklist from February 2021).

#### Considerations

* Once interoperability is enabled each time you change measurement settings, you don't need to repeat the MMP integration procedure in this article. Meaning you don't need to copy the MMP connection URL again.
* In AppsFlyer, if you turn SKAN measurement off, Meta ads can no longer get CV mapping.
* AppsFlyer SDK vs. Facebook SDK: The Facebook SDK is suited if you run campaigns only with Meta ads. If you run campaigns with multiple partners, by using the AppsFlyer SDK you can view data of all partners.
* Review the [discrepancies](/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq) section in this article.

#### Meta ads app install ads guidance

In configuring your Meta ads iOS 14 app install campaigns, take into account the following [Meta ads guidance](https://developers.facebook.com/blog/post/2020/10/29/preparing-our-partners-ios-14-latest-guidance-on-skadnetwork/):

* A maximum of 18 campaigns per app, each having 5 ad sets is allowed.
* You don't need a separate account for iOS 14 campaigns. You can run iOS 14 campaigns from existing accounts.
* There is a relationship between the Meta ads optimization method and the measurement type you select in AppsFlyer as follows:
  * **Revenue measurement**: VO and AEO
  * **Conversion measurement**: AEO— Includes Meta ads standard events and purchase event. You must map the app event in AppsFlyer to the relevant Meta ads event.

## Interoperation procedures

Complete the procedures that follow to enable interoperation.

For app install attribution:

### Allow Meta ads to share SKAN data with AppsFlyer

Allow Meta ads to share SKAN data with AppsFlyer. If you don't do so, you won't see SKAN installs attributed to Meta ads in the AppsFlyer SKAN dashboard.

This procedure needs to be performed once per app.

**To grant Meta ads permission to share SKAN data with AppsFlyer:**

1. In AppsFlyer, go to **Collaborate** > **Active Integrations**.
2. Search for and select Meta ads.
3. Go to the **SKAN** tab.

   ![skan_repprtiing_-_connected_accounts.png](https://support.appsflyer.com/hc/article_attachments/40032591356817)
4. Click **f login**. The account you use must be an Admin or Advertiser account [with the following permissions](https://www.facebook.com/business/help/155909647811305?id=829106167281625):
   * Ads\_read permission. See [verify that you have ads read permission](/docs/skadnetwork-skan-interoperation-with-meta-ads#verifying-the-ads_read-permission).
   * Access to the advertised app ID in the Meta Business Partner settings.
5. Follow the instructions in the user interface.  
   Meta generates an [access token](https://developers.facebook.com/docs/facebook-login/guides/access-tokens/get-long-lived/) that permits data sharing with AppsFlyer. After you complete the process, you are returned to AppsFlyer.
6. If this is your first time setting up this integration, verify that the account status **Waiting for sync** displays.  
   This message persists until we get data from Meta ads.
7. Wait until after 02:00 UTC of the next day, then verify that the status changes to **Data was pulled successfully.**  
   Data in the SKAN dashboard updates daily by 08:00 UTC.
8. Read the section about [measurement differences](/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook).

For in-app events attribution:

### Share CV schema with Meta ads

![SKAdNetwork-Facebook-AppsFlyer_integration__5_.png](https://files.readme.io/f5965dc535a47b3d665a3cf1ae1df564a176ff9be76d5fb4a9f01d80b0e58994-40032652599953.png)

#### Enabling AppsFlyer SKAN interoperation with Meta ads

| Step | Action | Details |
| --- | --- | --- |
| 1 | App prerequisites | * Adopt the most recent AppsFlyer [SDK](/docs/sdk-integration-overview) into your app. |
| 2 | SKAN settings review | Verify that AppsFlyer [SKAN Solution](/docs/skadnetwork-skan-solution-guide) is set up and is on. Doing so allows the AppsFlyer SDK to call SKAN APIs and set the CV.  **To view SKAN settings**:   1. In AppsFlyer, go to **Settings** > **SKAN Conversion Studio**. 2. Click the options **⋮** icon, and verify that **SKAN measurement** is on. [![Measurement_mode_on_facebook_ads.png](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)](https://support.appsflyer.com/hc/article_attachments/40032652602257) 3. Select your preferred measurement mode. Learn more about [SKAN Conversion Studio](/docs/skan-conversion-studio). 4. Make a note of the exact event names set. You need them in the next step. **Note:** Names are case-sensitive. |
| 3 | In-app event mapping | Review, and if necessary, make changes to your in-app event mappings.  **To view and set in-app event mappings**:   1. In AppsFlyer, go to **Collaborate** > **Active Integrations**. 2. Select **Meta ads**. 3. [Mandatory] From the **Integration** tab, turn on **In-app event postbacks**.    * You must map the currently selected SKAN measurement type. The default measurement type is revenue. ![in-app_events_fb_en-us.png](https://files.readme.io/98e2c8048444331c5d24343e683605e8388ee93bbfcb70aa5e8dad183c995859-40032591364241.png)    * Verify that the in-app events you set in SKAN measurement (**AppsFlyer event**) are mapped to Meta ads event identifiers (**mapped to partner event**). If you don't map the events, Meta ads can't optimize and will only count installs. CALLSTART::Note::Note When adding, changing, or removing a conversion value (CV) in the SKAN Conversion Studio, make sure that the event is mapped in the **In-app event postbacks**. Otherwise, the CV won't be updated on Meta ads. In-app event mapping guideCALLEND::       | Measurement type | Mapping requirement |      | --- | --- |      | [Custom](/docs/skan-conversion-studio#custom) | Map the in-app events you set in Custom to the corresponding Meta ads events.  To report revenue by postback you must set **Send revenue** to **Values & revenue**.  ![SendValueandRevenue.png](https://support.appsflyer.com/hc/article_attachments/40032652605713)  *af\_skad\_revenue* is used for overall revenue and mapped to the Meta ads revenue event, usually *fb\_mobile\_purchase.*  Note! It's OK to map more than one event to *fb\_mobile\_purchase*. |      | Revenue | If you report revenue by postback to ad networks, verify that your in-app event postback mappings include the in-app revenue events set by you.  *af\_skad\_revenue* is used for overall revenue and mapped to the Meta ads revenue event, usually *fb\_mobile\_purchase.*  Note! It's OK to map more than one event to *fb\_mobile\_purchase*. |      | Conversion | Map 1–6 conversion events to the corresponding Meta ads events. | |
Click Save integration.Scroll down to SKAN configuration, and click on the MMP connection URL to copy it. In the next section, we'll tell you where in Meta to paste the URL.![meta_ads_skan_configuration_mmp_url.png](https://files.readme.io/341918a757014d51a240898d157a6576b50cb269ad3bd0a574e4e6aef9d504ef-40032652607377.png)4Connect AppsFlyer to Meta adsOn Meta ads, open the events manager and go to the Settings tab. [![FacebookSkadNetworkSetup.jpg](https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg)](https://support.appsflyer.com/hc/article_attachments/40032652609297)In settings, click Configure events.[![mceclip0.jpg](https://files.readme.io/208040fdd63fcd80ddc2cac6d0f49ff6b78f5f788f85a5022f5e3c747f268ef9-40032591379217.jpg)](https://support.appsflyer.com/hc/article_attachments/40032591379217)In the Events Manager, select Import from Partner App. <br/> [![mceclip1.png](https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png)](https://support.appsflyer.com/hc/article_attachments/40032652611729)A field to paste the MMP Connection URL is displayed. <br/>This updates Meta with the CV mapping and instructs the Facebook SDK in your app to stop setting the CV. If import from partner app is disabled—[Troubleshoot](/docs/skadnetwork-skan-interoperation-with-meta-ads#import-from-partner-app-is-disabled).Follow the instructions in the Meta ads user interface. One of the following occurs:You successfully paste the MMP Connection URL into the Meta ads user interface. Congratulations! You have completed the integration. Read the notes that follow. Pasting the MMP connection URL fails, and an error message displays in the Meta ads user interface. If so:<br/>- Wait 24 hours, then repeat this procedure.<br/>- If the error persists (more than 24 hours), contact AppsFlyer support. NotesYou need to perform this procedure once. Meaning, there's no need to copy and paste the connection URL after changing the measurement settings in AppsFlyer. For example, if you switch from revenue measurement to conversion measurement, Meta ads uses the existing URL to get the current schema. Completing the procedure enables Meta ads to get the CV schema from AppsFlyer using a proprietary randomized structure. There is no way for you to configure this.It takes up to 24 hours for updated measurement settings to take effect in Meta ads. 5iOS 14 campaign settingIn Meta ads, verify that the iOS 14 campaign setting is on. This setting is found in the New App installs Campaign settings page. [![FBiOS14.png](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)](https://support.appsflyer.com/hc/article_attachments/40032652616209)

## Additional information

### Turning off the SKAN integration

When turning off your Meta ads integration, it's not enough to turn off the **Activate partner** toggle, you must separately remove the SKAN connections to stop SKAN data recording.

**To turn off the SKAN integration:**

1. In AppsFlyer, go to **Collaborate** > **Active** **Integrations**.
2. Search for and select Meta ads.
3. Go to the **SKAN** tab.
4. Click the delete icon for the account you want to remove.

### Measurement and timing differences between AppsFlyer and Meta ads

| Item | Details |
| --- | --- |
| In-app event names | Until August 15, 2021, event names in the dashboard used the Meta ads event names. Going forward, this is no longer true. |
| Revenue mode converted users metrics | [Deprecated August 16, 2021]<br /><br />~~In revenue mode, the converted users (paying users) metric doesn't consider the number of users reporting revenue via Meta ads campaigns dues to the revenue naming convention. mentioned in the previous section (in-app event names)~~ |
| Earliest data availability | In the first data sync after integration, as well as subsequent syncs, AppsFlyer receives Meta ads data for up to the last 7 days retroactively. |
| Install date | AppsFlyer and Meta ads differ in the way they determine the install date. Consider:<br /><br />* iOS SKAN postbacks don't contain an actual install timestamp.<br />* Meta ads regards the postback arrival time as the install time and considers the app timezone in Meta ads in setting the date.<br />* AppsFlyer derives the install time according to the [activity window settings](/docs/skan-conversion-studio#activity-window). Neither the app time zone nor the Meta ads Ad Account time zone are considered in the calculation. |
| Data freshness | * We collect SKAN data from Meta ads at 01:00 UTC<br />* Dashboards and aggregate data update 7 hours later. |

### Verifying the ads\_read permission

ads\_read permission provides Meta ads customers API access to ad performance data for use in custom dashboards and data analytics.

**To verify your Meta ads account has ads\_read permission:**

1. Go to your [Meta ads developer account.](https://developers.facebook.com/apps)
2. Select a Facebook App ID.
3. Go to **Use Cases > Permissions and Features**.
4. Search for `ads_read`.
5. Verify that `ads_read` has the ready for use status. If it does, no further action is required.
6. If `ads_read` doesn’t have the ready for use status, request the permission and submit the request.
7. After Meta approves the request, return to the Meta ads integration page in AppsFlyer and click **Connect**.  
   **Note:** Meta recently renamed and reorganized this section. If you don’t see **App Review**, this is expected. The correct location for requesting permissions is **Use Cases > Permissions and Features**.

### Troubleshooting, discrepancies, and FAQ

| Action | Details |
| --- | --- |
| Not Seeing SKAN In-app events from Meta? | If you're seeing installs but no in-app events from Meta SKAN campaigns, this checklist will help pinpoint what’s missing.<br /><br />Note: If you are not seeing installs, go through the install checklist first.<br /><br />#### **Quick Fix Checklist**<br /><br />**Step 1**<br /><br />1. Confirm SKAN Event Mapping in AppsFlyer.<br />2. Go to **Settings** > **SKAN Conversion Studio**.<br />3. Make sure the in-app events you want to measure are correctly mapped.<br /><br />**Step 2**<br /><br />1. Check Meta Ads Integration Event Mapping.<br />2. In AppsFlyer, go to **Collaborate** > **Active Integrations** and select **Meta ads**.<br /><br />* Ensure that the same event names (case-sensitive) from the SKAN Conversion Studio are mapped under In-app Event Postbacks to Meta.<br />* If you're measuring revenue, ensure af\_skad\_revenue is included and mapped to fb\_mobile\_purchase.<br /><br />#### Still not working?<br /><br />**>Minimum Install Volume Check**<br /><br />* You need a minimum number of installs per campaign per day from Meta for SKAN post-install data to show.<br />* Installs below this threshold show up with null Conversion Values (CVs), no event data can be decoded.<br /><br />This threshold is not revealed by Meta, but you can check the Null Conversion value rate in the SKAN dashboard for your campaign. If it is ~100%, then you need to boost the install number. Either adjust the filters of the target user base or increase campaign installs. |
| Meta ads can't connect | **Symptom**<br /><br />In Meta ads, if you get the message, *we can't connect. Check that you're using the correct URL. If the problem continues, contact your partner app for help.*<br /><br />**Corrective action**<br /><br />In AppsFlyer, verify that you have turned in-app event mapping and mapped your AppsFlyer events to your Meta ads events. (Described in the in-app event mapping described in the preceding section)<br /><br />[Guidance updated April 20, 2021] |
| Event priority | Q: How do I set the event priority in Meta ads?<br /><br />A: There is no need to set priority in Meta ads. This priority feature relates to apps that use the Facebook SDK to set the CV. In your case, the AppsFlyer SDK is setting the CV. Disregard the priority option in Meta ads. AppsFlyer measures 6 events in conversion without priority.<br /><br />[Guidance updated April 20, 2021] |
| Event occurrences | Q: Why do I have more event occurrences displaying in AppsFlyer than in Meta ads?<br /><br />A: Meta ads only counts 0-1 event occurrences. Therefore, even if you define more occurrences as part of a range, the additional occurrences are only counted by AppsFlyer. |
| Import from partner app is disabled | ![ImportFromPartnerApp.png](https://files.readme.io/c124696c4a8bca7c0d95d812f5390e9672adbfd6fc510a6fa573972f5441cd02-40032591386129.png)<br /><br />**Symptom**<br /><br />In Meta ads, if **import from partner app** is disabled**,** the app has never sent an event to Meta ads using an MMP SDK.<br /><br />**Corrective action**<br /><br />Do one of the following:<br /><br />* Start passing events to Meta ads using the MMP SDK as soon as possible.<br />* Start passing events to Meta ads using the Facebook SDK or App Events API and use one of the other flows to set up the conversion schema.<br /><br />Having done so, after the first events are recorded in Meta ads, configure the integration with AppsFlyer.<br /><br />[Guidance updated April 25, 2021] |
| Ranges can't overlap and must be in consecutive order | **Symptom**<br /><br />You use AppsFlyer SKAN custom measurement mode. When importing the measurement schema to Meta ads the following message display: *Ranges can't overlap and must be in consecutive order.*<br /><br />**Corrective action**<br /><br />Revenue values in the custom conversion schema must be in consecutive ascending order.<br /><br />[Guidance updated April 26, 2021] |
| Sending events to Meta ads | **Q**: Does it make sense to send additional event postbacks for events not selected in the CV measurement option to Meta ads?<br /><br />**A**: For consenting users, send the full range of events to maximize Meta ad's ability to optimize. |
| Map multiple events to the same Meta ads event | **Q**: Can I map multiple in-app events to one Meta ads event?<br /><br />**A**: If multiple events are mapped to one Meta ads standard event, Meta ads will not be able to differentiate between the events. So, Meta ads will optimize toward the one event they recognize. |
| No data to pull | **Q:**Why does the connection status display "No data to pull: Check your Meta data-sharing permissions"?<br /><br />**A**: Either there is no SKAN data yet or you need to log into Meta Ads using an Administrator user role on the account.<br /><br />**Q:**I got a "No data to pull: Check your Meta data-sharing permissions". Even though I see Meta Ads details, is everything ok?<br /><br />**A**: Yes. Although this error message may display, everything is fine and your data will get pulled. |
| Meta ads data is not in the dashboard | **Symptom**<br /><br />In the SKAN integration tab, the message *failed to pull data* displays.<br /><br />![FacebookSKAdIntegration.png](https://files.readme.io/42538a59d27815b95b71ec136ebc45b8d918eebf6a2235c90fef59c467128fb2-40032591388177.png)<br /><br />**Corrective action**<br /><br />Verify that the connected account is either a Facebook admin or a Meta ads Advertiser account having ads\_read permission. |
| There is an error in Meta ads when you try to run iOS 14 campaigns | **Symptom**<br /><br />All of the following are true:<br /><br />* You get an error message on Meta ads when you try to run an iOS 14 campaign<br />* You recently added a new App or a child-directed app to the App Store.<br /><br />This occurs because Meta ads isn't aware that you are using an SDK that includes SKAN support. Meaning the AppsFlyer SDK.<br /><br />**Corrective action**<br /><br />1. In AppsFlyer, go to **Collaborate** > **Active integrations**.<br />2. Search for and select **Meta ads**.<br />3. From the **Integration** tab, turn off **Activate partner.**<br />4. Click **Save Integration.**<br />5. Wait 15 seconds.<br />6. Turn on **Activate partner.**<br />7. Click **Save Integration.**<br />8. Wait up to 24 hours for Meta ads to get the signal. |
| Revenue reported by Meta ads | [Updated July 12, 2021]<br /><br />Meta ads derives revenue from the CV using your SKAN settings. However, this is not a direct calculation, and Meta ads uses algorithms in determining the revenue.<br /><br />A symptom of this is revenue having unrounded values even if you measure revenue in complete dollars. |
| Retroactive data backfill | [Updated December 23, 2021]<br /><br />Sometimes we aren't able to connect to Meta ads to get the data, for example, due to login failures. No need to worry. We'll fill in reporting gaps of the previous 7 days the next time we are able to log in. |
| AppsFlyer is showing significantly more installs/events/revenue than Meta ads | In many cases, this discrepancy occurs because Meta ads dashboard displays only click-through installs or events by default, while AppsFlyer dashboard display both click and view-through installs and events. |
| Agency integration | If the agency has an Administrator user role in the advertiser's Meta ads account, then they can perform the procedure in this article to enable SKAN interoperation on the behalf of the advertiser. Advertisers don't need to log in to their Meta ads account as well. The agency login will be indicated in the advertiser's account. |
| An updated CV doesn't appear on Meta ads | When adding, changing, or removing a conversion value (CV) in the SKAN Conversion Studio, make sure that the event is mapped in the **In-app event postbacks**. Otherwise, the CV won't be updated on Meta ads. |
| Modeled data differences in AppsFlyer and Meta ads Manager | AppsFlyer models aggregate data that basic SKAN reporting is unable to provide. [Learn more](/docs/skan-modeled-data)<br /><br />When AppsFlyer models data, data that is modeled by Meta ads isn’t taken into consideration, as AppsFlyer relies solely on confirmed, impartial data. Therefore, there may be data and granularity discrepancies between Meta ads Manager reports and AppsFlyer reports. |

> 📘 **Note**
>
> #### See also
>
> * [AppsFlyer SKANetwork Solution guide](/docs/skadnetwork-skan-solution-guide)