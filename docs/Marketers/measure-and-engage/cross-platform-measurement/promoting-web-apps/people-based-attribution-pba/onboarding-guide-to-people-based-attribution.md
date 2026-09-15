---
title: "Onboarding guide to People-Based Attribution"
excerpt: "Learn how to set up AppsFlyer's People-Based Attribution (PBA) to measure and analyze customer journeys across web and mobile properties."
---
## Setting up PBA

Setting up PBA consists of several action items described here and listed in the table that follows.

- Contact your AppsFlyer CSM or sales rep to enable PBA.
- Group brand digital properties into a brand bundle.
- Integrate the web SDK into your website and the mobile SDK into your app.
- AppsFlyer collects and attributes the data.  - Data is collected from several different sources.
  - Recorded data is divided into touchpoints and events.
  - Events are attributed to the last non-direct web visit in the previous 30 days.
  - Advertisers can designate some events as conversion events. For example, purchases. Conversion events are analyzed in the dashboards.
  - Raw data is used to perform custom data analyses.
- Analyze customer journeys to optimize campaigns.

### PBA set-up steps

Before beginning, contact your AppsFlyer CSM or sales rep to enable PBA. Then begin setup. Setup tasks are detailed in the table. Download this [spreadsheet](https://docs.google.com/spreadsheets/d/e/2PACX-1vQkYW2k1VUFugYLZ7Xv5esBL4kxfoNXMw0wyfRvoNGHdgiyZS5K5BE4seR2bjocK5HAArj97nlqF4By/pub?output=xlsx) to record your progress.

> 👍 Best practice
>
> Implement [CUID](https://support.appsflyer.com/hc/articles/207032016-Customer-user-ID-field-CUID-) in the app and on your website. AppsFlyer will receive the CUID when a user registers or logs on.

|  | Responsibility | Actions | Remarks |
| --- | --- | --- | --- |
| 1 | Advertiser | - [Add a web app](https://support.appsflyer.com/hc/articles/207377436-Adding-a-new-app) to your AppsFlyer account. The web app specifies the URL of the website for which you want to measure traffic and it is used to prevent [self-attribution](https://support.appsflyer.com/hc/articles/360002386997).<br>- [Set up brand bundles](https://support.appsflyer.com/hc/articles/360000646498); they combine a brand's digital properties (mobile apps and a web app).<br>- Specify additional [excluded domains](https://support.appsflyer.com/hc/articles/360000646498#domain-exclusion). | - Analyses and reports are aggregated within the brand. |
| 2 | Webmaster | - Install the [Web SDK](https://support.appsflyer.com/hc/articles/360001610038) on the website defined by the web app. <br>- Configure the web SDK to: <br> - Record visits<br> - Record events<br> - Set [CUID](https://support.appsflyer.com/hc/articles/360001610038#identifying-users-using-customer-user-id-cuid)<br> - Test implementation with the [SDK test tool](/docs/test-pba-web-sdk-integration) | - SDK records visits and events.<br>- Integration is fully supported through Google Tag Manager (GTM), Adobe, or Tealium.<br>- **Mandatory:** Call SetCustomerUserID() immediately after a user registers or logs on. If you don't have a CUID, discuss alternatives with your CSM. |
| 3 | Advertiser | Ensure that the webmaster used the [SDK test tool](/docs/test-pba-web-sdk-integration) to verify that the website the SDK is configured to:<br>- Record visits<br>- Record events<br>- Set the CUID | Advertiser! Don't proceed until this step is complete. |
| 4 | Developer & Advertiser | [Optional] [Web server-to-server](https://support.appsflyer.com/hc/articles/360006997298-Web-Server-to-server-events-API-for-PBA-Web-S2S-) API | Reports web-related events like automatic subscription renewal |
| 5 | Advertiser | - Mark conversion events:<br> - [Web events](https://support.appsflyer.com/hc/articles/360000646498#web-event-settings)<br> - [Optional] [Mobile in-app events](https://support.appsflyer.com/hc/articles/360000646498#inapp-event-settings). | - Wait for daily\* processing to complete before doing so. |
| 6 | Advertiser | Begin to use the dashboards | - [Website Attribution](https://support.appsflyer.com/hc/articles/360000654377)<br>- [Web-Assisted Installs](https://support.appsflyer.com/hc/articles/360002669837) |
| 7 | Advertiser | [Set up Data Locker](https://support.appsflyer.com/hc/articles/360001917778-Raw-data-reports-for-PBA#setting-up-pba-reports-in-data-locker) | Provides access to PBA raw-data reports including touchpoints, standard and conversion events, and specialized reports for Web-Assisted Installs. |
| 8 | Advertiser | [Optional]<br>Begin to use [raw data](https://support.appsflyer.com/hc/articles/360001917778-Raw-data-reports-for-PBA) | Data is available after daily\* processing. |
| \* Due to processing, data is available 10 hours after midnight UTC on the day of the event. Meaning Monday's events are available Tuesday 10:00 UTC. | | | |

## PBA data-acquisition via SDK/API

|  | Web platform | Mobile (app) platform |
| --- | --- | --- |
| SDK | [Web](https://support.appsflyer.com/hc/articles/360001610038-PBA-web-SDK-integration-guide)<br>- JavaScript tag SDK installed on the website<br>- Reports website visits, and web events | [Mobile](https://support.appsflyer.com/hc/sections/6551164458257-Integrate-the-AppsFlyer-SDK)<br>- App SDK integrated into iOS, Android, Unity, etc. <br>- Reports app installs and user actions occurring in the app |
| Server-to-server API | [Web server-to-server](https://support.appsflyer.com/hc/articles/360006997298-Web-Server-to-server-events-API-for-PBA-Web-S2S-)<br>- Reports events occurring in backend servers (not the web)<br>- Example: subscription renewal | [Mobile server-to-server](https://support.appsflyer.com/hc/articles/207034486)<br>- Reports events occurring in backend servers (not the app)<br>- Example: subscription renewal |