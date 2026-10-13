---
title: "Onboarding guide to People-Based Attribution"
excerpt: "PBA setup checklist"
x-zendesk:
  id: 360013821097
  url: https://support.appsflyer.com/hc/en-us/articles/360013821097-Onboarding-guide-to-People-Based-Attribution
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  position: 1
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, Cross-Platform Measurement]
  labels: [Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2020-10-01T08:00:26Z'
  edited_at: '2024-08-11T06:45:49Z'
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
> Implement [CUID](/docs/customer-user-id-field-cuid) in the app and on your website. AppsFlyer will receive the CUID when a user registers or logs on.

|  | Responsibility | Actions | Remarks |
| --- | --- | --- | --- |
| 1 | Advertiser | - [Add a web app](/docs/adding-an-app-to-appsflyer) to your AppsFlyer account. The web app specifies the URL of the website for which you want to measure traffic and it is used to prevent [self-attribution](/docs/pba-media-source-attribution-rules).<br />- [Set up brand bundles](/docs/pba-brand-bundles-and-settings); they combine a brand's digital properties (mobile apps and a web app).<br />- Specify additional [excluded domains](/docs/pba-brand-bundles-and-settings#domain-exclusion). | - Analyses and reports are aggregated within the brand. |
| 2 | Webmaster | - Install the [Web SDK](/docs/pba-web-sdk-integration-guide) on the website defined by the web app. <br />- Configure the web SDK to: <br /> - Record visits<br /> - Record events<br /> - Set [CUID](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid)<br /> - Test implementation with the [SDK test tool](/docs/test-pba-web-sdk-integration) | - SDK records visits and events.<br />- Integration is fully supported through Google Tag Manager (GTM), Adobe, or Tealium.<br />- **Mandatory:** Call SetCustomerUserID() immediately after a user registers or logs on. If you don't have a CUID, discuss alternatives with your CSM. |
| 3 | Advertiser | Ensure that the webmaster used the [SDK test tool](/docs/test-pba-web-sdk-integration) to verify that the website the SDK is configured to:<br />- Record visits<br />- Record events<br />- Set the CUID | Advertiser! Don't proceed until this step is complete. |
| 4 | Developer & Advertiser | [Optional] [Web server-to-server](/docs/web-server-to-server-events-api-for-pba-web-s2s) API | Reports web-related events like automatic subscription renewal |
| 5 | Advertiser | - Mark conversion events:<br /> - [Web events](/docs/pba-brand-bundles-and-settings#web-event-settings)<br /> - [Optional] [Mobile in-app events](/docs/pba-brand-bundles-and-settings#inapp-event-settings). | - Wait for daily\* processing to complete before doing so. |
| 6 | Advertiser | Begin to use the dashboards | - [Website Attribution](/docs/pba-website-attribution-dashboard)<br />- [Web-Assisted Installs](/docs/pba-web-assisted-installs) |
| 7 | Advertiser | [Set up Data Locker](/docs/pba-raw-data-reports#setting-up-pba-reports-in-data-locker) | Provides access to PBA raw-data reports including touchpoints, standard and conversion events, and specialized reports for Web-Assisted Installs. |
| 8 | Advertiser | [Optional]<br />Begin to use [raw data](/docs/pba-raw-data-reports) | Data is available after daily\* processing. |
| \* Due to processing, data is available 10 hours after midnight UTC on the day of the event. Meaning Monday's events are available Tuesday 10:00 UTC. | | | |

## PBA data-acquisition via SDK/API

|  | Web platform | Mobile (app) platform |
| --- | --- | --- |
| SDK | [Web](/docs/pba-web-sdk-integration-guide)<br />- JavaScript tag SDK installed on the website<br />- Reports website visits, and web events | [Mobile](/docs/integrate-the-appsflyer-sdk)<br />- App SDK integrated into iOS, Android, Unity, etc. <br />- Reports app installs and user actions occurring in the app |
| Server-to-server API | [Web server-to-server](/docs/web-server-to-server-events-api-for-pba-web-s2s)<br />- Reports events occurring in backend servers (not the web)<br />- Example: subscription renewal | [Mobile server-to-server](/docs/server-to-server-events-api-for-mobile-s2s-mobile)<br />- Reports events occurring in backend servers (not the app)<br />- Example: subscription renewal |