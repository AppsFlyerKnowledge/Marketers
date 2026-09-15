---
title: "Test marketer campaign integration with the ad network"
excerpt: "Learn how to test your ad network integration using marketer apps, including testing live apps, apps in development, and verifying postback data."
---
At a glance: Test ad network integration using marketer apps.

## Prerequisites

Before you can start testing the marketer's integration with your ad network, there are a few requirements:

- Allowlist devices: you need to ask the marketer to [allowlist](https://support.appsflyer.com/hc/articles/207031996--Whitelisting-a-Test-Device) any devices that you use for testing
- The app should include the AppsFlyer SDK
- If the app is not live on Google Play or the iOS App Store, you need to ask the marketer to provide you with the app
- Whether or not the app is live, it must be [in the marketer's AppsFlyer account](https://support.appsflyer.com/hc/articles/207377436-Adding-a-New-App-to-the-AppsFlyer-Dashboard)

## Getting started

Open your AppsFlyer Dashboard. In the **App search** screen, enter the marketer's app ID:

#### Example

Android - **com.example.app**

iOS- **id1234123412**

Once the green tick appears in the input field, click on the blue arrow. Clicking the arrow opens the app's dashboard.

![partner-app-search.png](https://files.readme.io/9fb3454de2eb7ea1cc7015151d75a9ae0835a60134b244227bf4da7f614a2a37-21414453165457.png)

## Testing live apps

In the AppsFlyer dashboard for your app, from the side menu, select, **Active integrations**. Choose your ad network and click on **Attribution link**.

> ❗️ Important!
>
> If the options under **Attribution link** are grayed out, ask the marketer to [enable ad network permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab). The required permissions are **Allow to configure integration** and **Allow to configure in-app events postbacks**.

Alternatively, you can ask the marketer to provide you with the attribution link.

### Installing the app through the attribution link

Now you can generate an attribution Link to test install attribution.

Add parameters to the attribution link according to your requirements and the data that you want to record.

![partner-configure-attribution-link.png](https://files.readme.io/9402ab5b3d1750ffd3ae8a2867c751545bdfd5b79202e09c8c90b9bc0bbbef95-21414453180817.png)

> 👍 Tip
>
> To learn more about the parameters that you can add to the attribution link, see [AppsFlyer attribution link structure and parameters](https://support.appsflyer.com/hc/articles/207447163).

### Testing install attribution

Send the attribution link to the test device. Open the link in the browser, install the app, and launch.

Launching the app is crucial for the attribution flow. If the app is not launched, no attribution is recorded.

You can then [view the install in your dashboard](https://support.appsflyer.com/hc/articles/4413093220113#viewing-installs-in-the-dashboard).

## Testing apps in development

You can test a marketer's campaign integration with your ad network even if the app is not live. However, you need to ask the marketer to provide you with the app (an .apk or .ipa file) so you can install it on your test devices.

### Generate an attribution link

Generate an attribution link. You can use the [same instructions as listed above](https://support.appsflyer.com/hc/articles/4413093220113#installing-the-app-through-the-attribution-link). Send the attribution link to the test device and navigate to it using the device's browser.

The following screen appears:

![app-not-available.png](https://files.readme.io/fda6290e4f0f995dbf04966c0a36b24fb246c4665ec367907178ed1d04edcf0c-21414453195921.png)

This is the expected result. Since the app is not live, the attribution link doesn't lead to any app store. However, the attribution link is still valid for attribution purposes. the attribution link and its parameters are recorded by AppsFlyer servers and the data is used for attribution.

### Installing the app

Install the app on the test device using the file that the marketer provides you and then launch the app. Delete the app and repeat the process (to generate several installs). You can then [view the installs in your dashboard](https://support.appsflyer.com/hc/articles/4413093220113#viewing-installs-in-the-dashboard).

## Testing in-app events

> 📘 Note
>
> You can test in-app events postbacks for both live apps and apps in development.

Before you can test in-app event postbacks, you should contact the marketer to learn about the type of in-app events that they record and how you can trigger them from the app.

### Mapping events

If the marketer has enabled the permission [**Configure in-app event postbacks**](https://support.appsflyer.com/hc/articles/4410395957521#g-in-app-event-postback-configuration) in its integration settings for your ad network, you can map AppsFlyer events to the events that you log in your servers.

In your app's AppsFlyer dashboard, from the side menu, select **Active integrations** and choose your ad network. Under the **Integration** tab scroll down to **In-app event settings**. Choose the in-app event and map it to the corresponding event:

![partner-in-app-events-postbacks-mapping.png](https://files.readme.io/2fe64793de5946d457a8fcb567db761c539755bdbe4cf910953b178eca84d841-21414453211793.png)

### Triggering in-app events

Once you know which in-app events the marketer records, and event mapping is in place, trigger a few events from the installed app.

> 📘 Note
>
> Ad networks don’t have access to the Events Dashboard and can see in-app events on Overview Dashboard only after the advertiser enables the **Access aggregate in-app events data** [ad network permission](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab). However, you can export in-app event-related data from the [In-app events postback](https://support.appsflyer.com/hc/articles/4413093220113#verifying-postback-data) report.

In the in-app events postback report, you can find data such as the postback URL and mapped parameters. Use the data in the report and compare it with the data in your servers (from the postback) to make sure that data from postbacks is accurate and properly recorded by your servers.

After exporting the in-app events postbacks report, you can look into the report to verify the following:

1. The event is attributed to you as an ad network, under the field **Media source**
2. The event name is correct, under the **Event name** field
3. The postback, if enabled, contains the event name and value, under the **Postback URL** field
4. In-app events are mapped correctly under the **Postback URL** field

## Viewing installs in the dashboard

Once you install and launch the app, you can see the results in your dashboard.

> ❗️ Important!
>
> In order to generate several installs, [the device must be allowlisted](https://support.appsflyer.com/hc/articles/4413093220113#prerequisites).

Access your AppsFlyer dashboard and from the side menu, select **Analyze** > **Overview**.

Filter by your ad network. You can see the number of clicks and installs that are attributed to your ad network.

Data related to clicks and installs appears at the top of the **Overview** screen. The **Overview** screen also includes **Breakdown by campaign** and **Aggregated performance report**. Verify that campaigns that appear in these sections correspond with the campaign parameter in the attribution link.

## Verifying postback data

Every install that is attributed to your ad network generates an install postback. If in-app events postbacks are enabled, events that come from an app whose install is attributed to your ad network, also generate postbacks.

Open the [Raw data export page](https://support.appsflyer.com/hc/articles/360008613838) and generate 2 postback reports:

1. **Installs**
2. **In-app events**

Both reports contain a column titled **Postback URL**. This column lists postback URLs for installs or in-app events (depending on the type of report).

Review the data in that column to verify the following:

- The URL endpoint is the correct one
- The parameters appended to the URL correspond to those appended to the AppsFlyer attribution link
- For in-app events postbacks, the events are correctly mapped i.e.

`sdk_event=af_purchase&mapped-event=purchase`

`sdk_event=af_login&mapped-event=login`
- The **Postback Error Message** column is empty