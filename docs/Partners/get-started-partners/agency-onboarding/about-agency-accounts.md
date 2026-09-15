---
title: "About agency accounts"
excerpt: "Learn how to make the most of your AppsFlyer Agency account to measure and analyze app marketing campaigns run on behalf of marketer clients."
---
Make the most of your AppsFlyer Agency account with advanced configuration.

## About agency accounts

Agency accounts are used by agency teams to measure app marketing campaigns run by the agency on behalf of marketer clients (app owners).

- Key pre-install and post-install metrics are available to ensure that agencies are delivering optimal performance across their client portfolio.
- Agency account dashboards provide similar capabilities and content to that of marketer dashboards. This includes the following dashboards:
  - Lifetime value overview
  - In-app events
  - Retargeting
- KPIs available include impressions, clicks, installs, user loyalty, cost, and ROI. About the [dashboard.](https://support.appsflyer.com/hc/articles/209680753-Introduction-to-the-AppsFlyer-Dashboard)

### Agency access to marketer data

Agencies always have access to data of traffic attributed to the agency. Marketers can [grant agencies access to](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions) additional data, for example, organic aggregate data. See [access to data by different types of users.](https://support.appsflyer.com/hc/articles/115005972889-Access-to-data-by-advertisers-agencies-and-ad-networks)

### Agency access to ad network integrations

To enable access to ad network integrations and have your campaigns measured, your agency must be pre-approved by the ad network. This is done by having your agency ID (af_prt) included in the ad network's list of authorized agencies. Contact the partner to ensure your agency is included. [See here](/docs/about-agency-accounts#af_prt-parameter) how to find your agency ID.

> 📘 Note
>
> - Applies also to empty af_prt parameters on attribution links
> - Doesn't apply to agencies working with [SRNs](/docs/self-reporting-networks-srns)

### Agency transparency

Agency traffic is set by default to be transparent. [Learn more](https://support.appsflyer.com/hc/articles/360002381617#transparency)

## Comparing different types of accounts

### Agency versus marketer accounts

- **Marketer accounts** are geared towards serving the app and data-owner. Marketers add apps to their accounts and determine the data-access permissions.
- **Agency accounts** are purpose-built for agency teams. They include tools for efficient measurement and analysis of marketing campaigns across their client portfolio.

Account structures permit knowledge-sharing between global agency teams and enable group-level ROI measurement, calculations, reporting, and optimization.

#### Differences between Marketer and Agency accounts

|  | Marketer | **Agency** |
| --- | --- | --- |
| Code-level implementation | Yes | No; only promotion of the app |
| Account-level settings | Team members, team member permissions, settings, payment preferences | Agency team members and their permissions. |
| App-level settings | Reattribution window, OneLink configuration, time zone, currency | Settings are according to those set by the marketer |
| Integrated-partner-level configuration | - Agency permissions<br/>- All non-SRN (attribution-link-based ad networks) configurations<br/>- SRN configurations<br/>- Link management | - All non-SRN configurations<br/>- Some SRN configurations that require minimum intervention from the marketer's side:<br/><br/><br/>- Google Doubleclick<br/>- Snapchat<br/>- Tencent<br/>Other SRNs must be configured by the marketer in order for the agency to use them.<br/>- Link management (using templates defined by Marketers) |
| Additional features | Yes (some, if part of the subscription plan) | As per marketer subscription and [permissions](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions) given to the agency (see the table below) |

### Features available to agencies

| Available by default | Not available | Requires marketer permission |
| --- | --- | --- |
| - Lifetime value overview dashboard<br/>- In-app events dashboard<br/>- Retargeting dashboard<br/>- Active integrations<br/>- [SSOT dashboard](/docs/getting-started-agency-onboarding#single-source-of-truth-ssot-for-agencies)\*\*<br/>\\*\\* Available only after the marketer has enabled this option. | - Activity dashboard<br/>- Custom dashboard<br/>- People-based analytics<br/>- Audiences<br/>- Pivot report<br/>- Push API<br/>- Data locker<br/>\*Only cohort reports are available upon marketer permission | - Retention report<br/>- Cohort dashboard report<br/>- [Cohort report from Data Locker](https://support.appsflyer.com/hc/articles/4543231254417)<br/>- Protect360<br/>- Raw-data export<br/>- Aggregate organic data<br/>- Pull API |

### Agency vs. ad network account

#### Differences between Ad network and Agency accounts

| Ad network | Agency |
| --- | --- |
| Attribution link parameter for identification: `pid` | Attribution link parameter for identification: `af_prt` |
| Places app ads on its own platform | Promotes the app via multiple media sources |
| Sees only traffic from ads placed on its platform | Sees only traffic from media sources it advertises on |
| Can receive real-time information about installs and in-app events via postbacks | Cannot receive real-time information about installs and in-app events via postbacks |
| Can configure in-app event postbacks for any traffic from itself\* | Can configure in-app event postbacks to some of the partners it brings traffic from\* |
| \* Requires marketer permission | |

## Agency accounts—campaigns and reporting

### Agency: setting up campaigns

Agencies can measure the following main traffic types:

- [Self-reporting ad networks (SRNs)](https://support.appsflyer.com/hc/articles/207034106#selfreporting-ad-networks)
- [Non-SRNs (ad networks using attribution links)](/docs/about-agency-accounts#nonsrns)

> ❗️ Important!
>
> When working with agencies, turning off an integrated partner does not automatically disable certain attribution capabilities for the agencies linked to that partner:
>
> To fully deactivate these capabilities for agencies, the advertiser must manually turn off the following settings before deactivating the partner:
>
> 1. Install view-through attribution
> 2. Cross-platform equal attribution priority
>
> Only after disabling these toggles should the advertiser proceed to deactivate the partner.
>
> **Note:** If the advertiser deactivates the partner without first turning off these settings, the agencies may continue to use these attribution capabilities.

### Self-reporting ad networks

Self-reporting networks, such as Meta ads, Google Ads, or X Ads don't use external attribution links. Instead, each network has its own methods and APIs that AppsFlyer uses to communicate new installs, in-app events, etc.

#### SRN configurations

| SRN | Marketer to perform initial SRN setup | Details |
| --- | --- | --- |
| Apple Search Ads | Yes | For details of agency configuration for Apple Search Ads campaigns, click [here](https://support.appsflyer.com/hc/articles/213747963#configuring-agencies-and-marketing-partners). |
| Google Ads | Yes | For details of agency configuration for Google Ads campaigns, click [here](https://support.appsflyer.com/hc/articles/115003669983-Agency-Configuration-for-the-New-Google-AdWords-Integration). |
| Google Marketing Platform (GMP) | No | GMP has two different APIs. Learn more about the [differences between the two](https://support.appsflyer.com/hc/articles/360017595598-Google-Marketing-Platform-App-Attribution-Integration-DV360-#comparing-the-legacy-and-new-integrations), and choose the one relevant to you. |
| Meta ads<br/>and<br/>X Ads | Yes | **Note:** This section refers to Meta ads. For attribution of Facebook Social (posts), read about [Owned Media](https://support.appsflyer.com/hc/articles/207034106#owned-media%E2%80%94onelink-and-custom-links).<br/>**All Meta ads and X Ads campaigns must start with the Agency account name followed by "_".** The name is defined in the AppsFlyer platform.<br/>Campaigns that aren't named correctly are visible to the marketer but remain invisible to the agency account.<br/>**Note:**<br/>- The agency name is CASE SENSITIVE.<br/>- See more details about [Meta ads](https://support.appsflyer.com/hc/articles/4410472805649#attributing-agencies-with-facebook) and [X Ads](https://support.appsflyer.com/hc/articles/4410464352017#any-special-instructions-for-agencies) setup for agencies.<br/>- Contact [agency@appsflyer.com](mailto:agency@appsflyer.com) if you have any questions about this.<br/>#### Example<br/>agencyx runs a Meta ads campaign called agencyx_brilliantcampaign, which is visible to it.<br/>agencyz runs an X Ads campaign called AgencyZ_whathaveidonewrong, but doesn't see any results. This happens because the agency name part of the campaign is different to the defined agency name (capital A and Z). |
| Snapchat | No | For details of agency configuration for Snapchat campaigns, click [here](https://support.appsflyer.com/hc/articles/211011983). |
| TikTok for Business | Yes | For details of agency configuration for TikTok for Business campaigns, click [here](/docs/tiktok-for-business-advanced-srn-integration-setup#setting-up-tiktok-for-business-for-agencies). |
| Yahoo (Oath: Ad Platforms / Yahoo Gemini) | Yes | For details of agency configuration for Yahoo campaigns, [click here](https://support.appsflyer.com/hc/articles/212067546#agency-configuration). |

### Non-SRNs

Unlike SRNs, the vast majority of ad networks use attribution links for attribution purposes. [These attribution links are already provided](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab) in each network's settings on AppsFlyer and can be simply copied from there directly.

For agencies, the process is almost identical to that of the marketers. Upon going to the setup window of any regular ad networks the attribution link is already there. The only difference is the automatic addition of the `af_prt` parameter to the attribution link.

#### Ad network configuration visibility

Ad network setup is visible to ad networks themselves only when the marketer (app owner) configures it. When an agency activates and configures ad network integration, the network sees this section as inactive.

#### af_prt parameter

The value of the `af_prt` parameter is the agency name. When the agency name is passed in the `af_prt` parameter, it's converted to lowercase letters.

When `af_prt` with your agency name is part of the attribution link, new installs can be attributed to your agency account. Otherwise, new installs are attributed directly to the ad network.

<Image src="https://files.readme.io/61559e2e1628e9411665b7e8d3d3d440a55effb3bccda79c7fe1ee02fd43fb8c-32355631649937.png" alt="agency-af-prt.png" />

**Do not use links received from the marketer**: make sure to use the links from your own account to prevent wrong attribution.

#### Special case: All-installs and all-launches networks

Some non-SRNs require (or allow) marketers to send them postbacks **for devices that aren't attributed to them**.

- **All-installs network**: The network accepts a postback for every new app install, from any source
- **All-launches network**: The network accepts a postback for every new app launch, from any source

Some examples for all-installs networks are Vungle, Wechat, Startapp, Unity Ads, and more.

The following table shows the full list of the all-launches networks:

| Network Name | Network PID (on AF attribution links) |
| --- | --- |
| Supersonicads (a legacy network of ironSource) | supersonicads_int |
| Adelphic Remarketing | adelphicremarketing_int |
| Grow Mobile | growmobile_int |
| ONE by AOL | advertising.com_int |
| Lemmonet Mobile | lemmonetmobile_int |
| Clickky | clickky_int |
| Remerge | remerge_int |
| MyThings | mythings_int |
| TikTok for Business | bytedanceglobal_int |

#### How to setup agency attribution with all installs/launches networks?

Working with these networks entails sending information from installs that are not brought by the agency. Therefore, these networks require the marketer to configure them BEFORE the **agency**.

##### Example

Let's use agency attribution setup with Tapjoy as an example:

1. Marketer goes to Tapjoy setup window on the marketer's dashboard.
2. Marketer enters the Tapjoy App ID, given to the **marketer** by Tapjoy, in the **app_id** text field.
3. Under the **Integration** tab > Default postbacks, the marketer selects **All media sources, including organic**.
4. Agency goes to Tapjoy setup window on the agency's dashboard.
5. Agency enters the Tapjoy App ID, given to the **agency** by Tapjoy, in the **app_id** text field.

### Deep linking

Deep linking is the launch of a mobile app when opening personalized content and/or sending the users to specific activities within the app. This can provide your users with superior user experience and enhance their engagement.

For deep linking to work, the mobile app MUST be developed with deep linking capabilities and infrastructure. Contact the app owner to find out whether the app is suitable for deep linking, before setting up the campaigns.

### Retargeting

- [Retargeting attribution](https://support.appsflyer.com/hc/articles/207033786) allows you to target existing or past users in your campaigns. Retargeting campaigns often require deep linking capabilities to work correctly.

### In-app events

App owners can have various events in their apps (e.g. purchase, watching a tutorial, passing a level, etc), that they can record and analyze in AppsFlyer. Agencies can see data of events attributed to them on the [Events](https://support.appsflyer.com/hc/articles/208151306) page in their account.

#### In-app event postbacks

Agencies can be given permission to configure [in-app event postbacks](https://support.appsflyer.com/hc/articles/208439256)(including the [af_app_opened event](https://support.appsflyer.com/hc/articles/360000520785)) to ad networks, upon receipt of permission from the Marketer.

Agencies can give the ad networks permission to configure in-app postbacks to themselves. [Permission is granted](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions) by marketers in the agency permission tab.

### Reporting for agencies

- Traffic statistics are viewed and downloaded directly from the AppsFlyer dashboard.
- Reports are accessed via the [Export Data](https://support.appsflyer.com/hc/articles/209680773-Export-Data-Reports) page in the AppsFlyer dashboard. You can also access Cohort reports via [Data Locker](https://support.appsflyer.com/hc/articles/4543231254417).
- The following reports types are available:
  - Aggregate
  - Raw data
- Marketers and agencies mostly cannot access the same data in the dashboard, reports, and so on.
- Agencies are usually responsible for only a part of the marketer's traffic, so the agencies' access to the data is limited in comparison to that of marketers.
- [This article](https://support.appsflyer.com/hc/articles/115005972889-Advertisers-Agencies-and-Ad-Networks) breaks down these differences. The following sections highlight them

> 📘 Note
>
> Due to Meta ads and X Ads terms of service, **agencies**, who are considered 3rd parties, **do not have access to raw data reports traffic, originating from either Meta ads or X Ads**.

### Access to aggregate data

- Performance reports also referred to as aggregate data reports, are available by default to agency accounts. Related reading: [Aggregate performance reports](https://support.appsflyer.com/hc/articles/360005437257)
- Access to aggregate organic data reports requires marketer [permission](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions).
- Agencies can receive access to Retention and Cohort reports, and Protect360 dashboard. This requires that the marketer enable [**Allow access to your retention and cohort reports**](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions) or [**Allow access to your Protect360 dashboard**](https://support.appsflyer.com/hc/articles/4410395957521#agency-permissions), respectively, in the **Permissions** tab of **Active integrations**.

### Access to raw data

[Raw data reports](https://support.appsflyer.com/hc/articles/209680773) (user-level data reports) contain attribution information and are divided into topics.

### Time zone and currency

Agencies see apps in the app-defined time zone and currency, but these settings can be changed only by marketers.

### Cost reporting

Agencies can enable **Get cost data** when configuring an integrated partner that [supports cost data](https://support.appsflyer.com/hc/articles/207040526#ad-networks-supporting-cost-api).

**To enable Get cost data:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Active integrations**.
2. Filter the partners by the Cost: From the top of the **Active integrations** page, select **Supported features** > **Cost**.
3. Select the partner. You're directed to the **Integration** tab. Select Go to the **Cost** tab.
4. Turn on **Get cost data.**
5. Enter the API key for this partner.
6. Click **Save**.

#### Accessing and viewing cost data

Cost data is available to the agency in the following data sources:

- **Overview** page: cost data is visible in the **Aggregated performance report** in the Overview page.
- **Reports**: cost data is available in exported reports such as **Installations** under **Raw data reports** and **Partners (Media sources)** under **Performance reports**

### Hybrid account data access

Hybrid accounts are agency accounts that manage some of the apps as an Agency (app partner), and some as a Marketer (app owner).

The following account-level features have limited availability:

- [Custom dashboard](https://support.appsflyer.com/hc/articles/212750286): not available for agencies and hybrid accounts.
- Cohort report: available upon marketer's permission.
- Protect360: available upon marketer's permission.

If you have a hybrid account, they may appear on your dashboard, but you will get a 404 error when trying to open them.

If you would like to use these features, it's recommended to open a new Marketer account and separate your Marketer and Agency apps. The features mentioned above will be available in your Marketer account if you have them enabled.