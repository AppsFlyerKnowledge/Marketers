---
title: "Set up cross-platform links for multi-device campaigns"
excerpt: "Learn how to promote, attribute, and measure app installs on platforms to ad views on other platforms using AppsFlyer cross-platform attribution links."
---
**At a glance:** How to promote, attribute, and measure app installs on platforms to ad views on other platforms. For example, mobile app installs to ads viewed on CTV devices, game console app installs to ads viewed on mobile or desktops (web), and CTV app installs to ads viewed on mobile or desktop (web).

## Overview

With AppsFlyer cross-platform attribution links (impression URLs), you can attribute installs from one platform to ad views displayed on another platform. Multiple installs within the same household can be attributed to the same cross-platform ad impression.

### How does the attribution logic work?

* Impressions are identified in AppsFlyer by their OneLink template ID and are assigned to each platform set in the template.
* Installs are identified by their app and platform.
* Matching logic: Template-level impressions are matched to the specific app launch through probabilistic attribution. Any app variant in the group can be matched.

## Create a OneLink template for cross-platform attribution

A single template supports your app across multiple platforms (meaning one template works across all platforms). In the template, you set all platform variants of your app (mobile, CTV, desktop, console) bundled together.

1. Create or edit a [OneLink template](/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users) for cross-platform attribution.
2. In the **Cross-platform attribution** section, click the **edit button ->** **Enable cross-platform attribution**
3. From the relevant platform drop-downs, select the relevant app. **Note**: Each app can only be added to one OneLink template with cross-platform attribution enabled. [![Cross-platform attribution.png](https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png)](https://support.appsflyer.com/hc/article_attachments/24170762165521)

## Set up cross-platform partner integration

To set up cross-platform attribution using cross-platform impression URLs, configure the partner integration for each targeted app.

> 📘 **Important!**
>
> Make sure to enable the partner integration by performing the steps below for all targeted apps that you selected in the OneLink template (see the [section above](#step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution)). If the integration is disabled for one of the targeted apps,  cross-platform attribution will not occur.

### Step 1: Select the targeted app of the partner integration

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations**
2. Select the integrated partner.
3. In the **Integration** tab, from the **App** drop-down box, select the targeted app.

### Step 2: Enable view-through attribution

For links to be used by integrated partners, enable view-through attribution.

1. In the **Integration** tab, turn on **Install view-through attribution**.
2. Click **Save integration**.

### Step 3: Create an attribution link (cross-platform impression URL)

To Create an [attribution link](/docs/set-up-an-integrated-partner#attribution-link-tab) (cross-platform impression URL) for integrated networks

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations** and select the integrated partner.
2. In the **Attribution link** tab, when creating a [OneLink link](/docs/set-up-an-integrated-partner#attribution-link-tab), select Use OneLink.
3. In the **Select OneLink template** list, select the [OneLink template you created for cross-platform](#step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution) attribution.
4. Scroll down to **View-through attribution**.[![](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)](https://support.appsflyer.com/hc/article_attachments/12602245845649)
5. Turn on **Cross-platform attribution**. This adds the `af_xplatform=true` parameter to the impression attribution link and gives the link cross-platform attribution capabilities. Without this parameter, the URL functions as a regular impression URL that can't attribute multiple installs to the same impression.
6. Set the **Cross-platform view-through attribution lookback window**. This adds the `af_xplatform_vt_lookback` parameter to the impression attribution link and indicates the number of hours (up to 72) following the impression during which the app install can be attributed to the impression.
7. Add any additional attribution parameters as needed. Use naming conventions that identify your cross-platform app campaign. [Learn more](/docs/about-link-structure-and-parameters) about the parameters you can add for additional data and metrics. Sample link:

   ```
   https://impressions.onelink.me/{template_id}?pid=__media_source__&af_xplatform=true&af_xplatform_vt_lookback=24h&af_siteid=__CSITE__&c=__ctv_to_mobile__&af_channel=__PLACEMENT__&af_c_id=__CAMPAIGN_ID__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_source_platform=__source_platform__&af_source_device_category=__device_category__&af_ad_type=__CTYPE__&redirect=false
   ```
8. Give the link to the ad network to place behind the ad displayed on CTV, PC, or console platforms.

> 📘 **Important!**
>
> For owned media and non-integrated partners add parameters as needed.  [Learn more](/docs/about-link-structure-and-parameters) about the parameters you can add for additional data and metrics.

### Advanced: Equal priority setting (optional)

You can optionally assign **equal priority** to clicks and impressions in cross-platform attribution. This advanced setting lets AppsFlyer treat impressions (for example, in CTV or consoles) as having the same attribution priority as clicks. For more information, see [Attribution method priorities](/docs/appsflyer-attribution-model#attribution-waterfall).

**To enable equal priority:**

1. In the Cross-platform setup section, select the **Equal priority** checkbox.
2. Click **Save**.

> 📘 **Note**
>
> Enabling equal priority may cause AppsFlyer to prioritize its own attribution over other sources. Use this setting with caution and only if it aligns with your overall attribution strategy.

## Traits and limitations

| Trait | Remarks |
| --- | --- |
| Attribution window | Between 1-72 hours, depending on the lookback window parameter `af_xplatform_vt_lookback`(default is 24 hours). |
| Retargeting | * Re-attribution: Supported for cross-platform-to-mobile. Not for other platforms.<br />* Re-engagement: Not supported |
| Attribution method | View-through attribution using probabilistic modeling |
| Household attribution | Supported. Meaning multiple installs within the same household can be attributed to the same cross-platform ad impression. |
| Reporting | * Cross-platform installs are available in regular AppsFlyer dashboards and reports:<br />  * Aggregate data [dashboards](/docs/getting-started-with-appsflyer-dashboards) and [reports](/docs/aggregated-and-analytics-reporting-overview)<br />  * Raw data [reports](/docs/raw-data-reporting-overview)<br />* Cross-platform impressions don't display in app-level dashboards. However, they are available in the [Cross-platform engagements report](/docs/data-locker-advertiser-reports#user-journey) via Data Locker.<br />* Make sure you use parameter naming conventions that easily identify your cross-platform campaign. |
| IP masking | IP masking for cross-platform engagements is not supported since it is an app-level trait. If `ip_masking` is configured, the install won't be attributed to the cross-platform engagement. |
| CTV-to mobile | CTV-to-mobile attribution flows are available only to [integrated partners](/docs/set-up-cross-platform-links-for-multi-device-campaigns#list-of-ad-networks) who have the authorization to conduct cross-platform campaigns. |
| Cross-platform attribution links in mobile devices | When a cross-platform attribution link is viewed on a mobile device, attribution is determined by the standard mobile probabilistic modeling logic, not by the cross-platform attribution flow designed for [CTV](/docs/ctv-pc-and-console-platform-attribution-concepts#tv-screens), PC, and consoles. Consequently, mobile impressions will not be eligible for the [equal priority](#step-3-enable-equal-priority-for-crossplatform-impressions), [extended lookback window](#attribution-window), or [household attribution](#household-attribution) that is available for genuine cross-platform impressions. |
| Agency permissions | Agencies cannot toggle “Cross-platform equal attribution priority” on their end. This configuration is directly copied from the advertiser’s settings for the specific ad network. |

## Discrepancies

AppsFlyer and tvScientific differ in their attribution models. This may cause discrepancies between the tvScientific and AppsFlyer dashboards. See the reasons for discrepancies in the table below:

| Cause | tvScientific | AppsFlyer |
| --- | --- | --- |
| Baseline model | Shared-credit attribution model | Last touch attribution model |
| Lookback window | Up to 30 days | Up to 72 hours |
| Retargeting | Attribution of both new users (installs) and returning users (re-engagements) | Attribution of new users (installs) only |
| Cost assignment | Cost is assigned to the impression regardless of the operating system | Cost is assigned to the impression on separate systems for iOS and Android |

## FAQ

### Does Enable view-through attribution via probabilistic modeling need to be turned on?

No. The Enable view-through attribution via probabilistic modeling toggle in your app settings doesn't need to be turned on for cross-platform view-through attribution to work.

### Why don’t I see impressions for my cross-platform campaigns in the dashboard?

Cross-platform impressions don’t appear in app-level dashboards. This is because one CTV impression can lead to multiple conversions across different apps, and there’s no accurate way to allocate impressions to each app. You can access impression data in the [Cross-platform engagements report in Data Locker](/docs/ctv-pc-and-console-data-via-data-locker#report-types-and-availability).