---
title: Onboarding guide to People-Based Attribution
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-10-01T08:00:26Z'
  edited_at: '2024-08-11T06:45:49Z'
  id: 360013821097
  locale: en-us
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360013821097-Onboarding-guide-to-People-Based-Attribution
---
> **At a glance:** PBA setup checklist

## Setting up PBA

Setting up PBA consists of several action items described here and listed in the table that follows.

* Contact your AppsFlyer CSM or sales rep to enable PBA.
* Group brand digital properties into a brand bundle.
* Integrate the web SDK into your website and the mobile SDK into your app.
* AppsFlyer collects and attributes the data.
  * Data is collected from several different sources.
  * Recorded data is divided into touchpoints and events.
  * Events are attributed to the last non-direct web visit in the previous 30 days.
  * Advertisers can designate some events as conversion events. For example, purchases. Conversion events are analyzed in the dashboards.
  * Raw data is used to perform custom data analyses.
* Analyze customer journeys to optimize campaigns.

### PBA set-up steps

Before beginning, contact your AppsFlyer CSM or sales rep to enable PBA. Then begin setup. Setup tasks are detailed in the table. Download this <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQkYW2k1VUFugYLZ7Xv5esBL4kxfoNXMw0wyfRvoNGHdgiyZS5K5BE4seR2bjocK5HAArj97nlqF4By/pub?output=xlsx">spreadsheet</Anchor> to record your progress.

**Best practice:** Implement <Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid">CUID</Anchor> in the app and on your website. AppsFlyer will receive the CUID when a user registers or logs on.

<table><thead><tr><th> </th><th>Responsibility</th><th>Actions</th><th>Remarks</th></tr></thead><tbody><tr><td><span id="1"></span><p> 1</p></td><td><p>Advertiser </p></td><td><ul><li><span><a href="./adding-an-app-to-appsflyer" target="_blank">Add a web app</a> to your AppsFlyer account. The web app specifies the URL of the website for which you want to measure traffic and </span>it is used to prevent <a href="./pba-media-source-attribution-rules" target="_blank">self-attribution</a>.</li><li><span><a href="./pba-brand-bundles-and-settings" target="_blank">Set up brand bundles</a>; they combine a brand's digital properties (mobile apps and a web app).</span> </li><li>Specify additional <a href="./pba-brand-bundles-and-settings#domain-exclusion" target="_blank">excluded domains</a>.</li></ul></td><td><ul><li><span>Analyses and reports are aggregated within the brand.</span></li></ul></td></tr><tr><td><span id="2"></span><p> 2</p></td><td> Webmaster </td><td><ul><li>Install the <a href="./pba-web-sdk-integration-guide" target="_blank">Web SDK</a> on the website defined by the web app. </li><li>Configure the web SDK to: <ul><li>Record visits</li><li>Record events</li><li><mark> Set <a href="./pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid" target="_blank">CUID</a> </mark></li><li>Test implementation with the <a href="./test-pba-web-sdk-integration" target="_blank">SDK test tool</a></li></ul></li></ul></td><td><ul><li><span>SDK records visits and events.</span></li><li><span>Integration is fully supported through Google Tag Manager (GTM), Adobe, or Tealium.</span></li><li><strong>Mandatory:</strong>  Call SetCustomerUserID() immediately after a user registers or logs on. If you don't have a CUID, discuss alternatives with your CSM. </li></ul></td></tr><tr><td><span id="3"></span><p>3</p></td><td><p>Advertiser</p></td><td><p>Ensure that the webmaster used the <a href="./test-pba-web-sdk-integration" target="_blank">SDK test tool</a> to verify that the website the SDK is configured to:</p><ul><li>Record visits</li><li>Record events</li><li>Set the CUID</li></ul></td><td><p><mark> Advertiser! Don't proceed until this step is complete.  </mark></p></td></tr><tr><td><span id="4"></span><p>4 </p></td><td><p>Developer &amp; Advertiser</p></td><td><p>[Optional] <a href="./web-server-to-server-events-api-for-pba-web-s2s" target="_blank">Web server-to-server</a> API</p></td><td>Reports web-related events like automatic subscription renewal</td></tr><tr><td><span id="5"></span><p>5</p></td><td><p>Advertiser</p></td><td><ul><li><span>Mark </span>conversion events:<ul><li><span><a href="./pba-brand-bundles-and-settings#web-event-settings" target="_blank">Web events</a></span></li><li><span>[Optional] <a href="./pba-brand-bundles-and-settings#inapp-event-settings" target="_blank">Mobile in-app events</a>.</span></li></ul></li></ul></td><td><ul><li><span>Wait for daily\* processing to complete before doing so.</span></li></ul></td></tr><tr><td><span id="6"></span><p> 6</p></td><td><p>Advertiser</p></td><td><p>Begin to use the dashboards</p></td><td><ul><li><a href="./pba-website-attribution-dashboard" target="_blank">Website Attribution</a></li><li><a href="./pba-web-assisted-installs" target="_blank">Web-Assisted Installs</a></li></ul></td></tr><tr><td><span id="7"></span><p> 7</p></td><td>Advertiser</td><td><a href="./pba-raw-data-reports#setting-up-pba-reports-in-data-locker" target="_blank">Set up Data Locker</a></td><td><p>Provides access to PBA raw-data reports including touchpoints, standard and conversion events, and specialized reports for Web-Assisted Installs.</p></td></tr><tr><td><span id="8"></span><p>8</p></td><td><p>Advertiser</p></td><td><p>[Optional]<br/>Begin to use <a href="./pba-raw-data-reports" target="_blank">raw data</a></p></td><td><p>Data is available after daily\* processing.</p></td></tr><tr><td colspan="4"><span id="-due-to-processing-data-is-available-10-hours-after-midnight-utc-on-the-day-of-the-event-meaning-mondays-events-are-available-tuesday-1000-utc"></span>\* Due to processing, data is available 10 hours after midnight UTC on the day of the event. Meaning Monday's events are available Tuesday 10:00 UTC. </td></tr></tbody></table>

## PBA data-acquisition via SDK/API

|  | Web platform | Mobile (app) platform |
| --- | --- | --- |
| SDK | <Anchor target="_blank" href="/marketers/vi/docs/pba-web-sdk-integration-guide">Web</Anchor><ul><li>JavaScript tag SDK installed on the website</li><li>Reports website visits, and web events</li></ul> | <Anchor target="_blank" href="/marketers/vi/docs/integrate-the-appsflyer-sdk">Mobile</Anchor><ul><li>App SDK integrated into iOS, Android, Unity, etc.</li><li>Reports app installs and user actions occurring in the app</li></ul> |
| Server-to-server API | <Anchor target="_blank" href="/marketers/vi/docs/web-server-to-server-events-api-for-pba-web-s2s">Web server-to-server</Anchor><ul><li>Reports events occurring in backend servers (not the web)</li><li>Example: subscription renewal</li></ul> | <Anchor target="_blank" href="/marketers/vi/docs/server-to-server-events-api-for-mobile-s2s-mobile">Mobile server-to-server</Anchor><ul><li>Reports events occurring in backend servers (not the app)</li><li>Example: subscription renewal</li></ul> |

<div data-zendesk-anchors="01H8V1XPAHGFVJRKM56S2ZQTBD=setting-up-pba pba-setup-steps=pba-set-up-steps 01ECF26CMN668ZZV6XNZA3W692=pba-set-up-steps pba-dataacquisition-via-sdkapi=pba-data-acquisition-via-sdkapi 01H8V1XPAH23BV25ZCMFR7MM9Q=pba-data-acquisition-via-sdkapi" />
