---
title: "Getting started—agency onboarding"
excerpt: "Start measuring the campaigns of your clients by setting up an Agency account."
---
**At a glance:** Start measuring the campaigns of your clients by setting up an Agency account.

<Embed title="Getting started—agency onboarding" typeOfEmbed="wistia" url="https://fast.wistia.com/embed/iframe/54qzpj1lm7" providerUrl="https://fast.wistia.com" />

## 

## AppsFlyer attribution model

Before you proceed, it’s essential to understand how AppsFlyer’s attribution works. This section explains what happens along the way from the first click or impression to the attribution of an install or an event — and beyond.

[![ua-agency-flow.png](https://files.readme.io/09b001f7b5395ffa9c6e7f5abf4e7df5919fd9964ea17fa2934579f513fdb615-360004474817.png)](https://support.appsflyer.com/hc/article_attachments/360004474817)

1. A marketer or an agency on behalf of the marketer configures a campaign with a certain ad network, using AppsFlyer attribution links.
2. A user clicks on one of their ads – for example, a banner or an offer link.
3. AppsFlyer attribution link behind the ad is then populated with information collected during the click. We gather the information from the attribution link and store it in our database.
4. The user is redirected to an app store.
5. The user installs the app and opens it for the first time. The AppsFlyer SDK inside the app calls our servers with the information about the device that the app is installed on.
6. We match this data to our click database using our [Attribution methods](/docs/appsflyer-attribution-model).
7. If we find a match, we attribute the install to the click. If not, we attribute the install to an organic download.
8. Once the install is attributed, we show it on marketer and agency dashboards and reports ([except Meta ads and X Ads](/docs/about-agency-accounts#selfreporting-ad-networks)).
9. Then, we send a postback with the conversion details to the ad network, who can use this information for further optimization.

## Agency role in mobile attribution chain

A marketer, who owns the app, integrates AppsFlyer SDK inside it in order to quantify their marketing effort.

Some app owners choose to hire marketing agencies to run advertising campaigns on their behalf. To do so, the agency should have an AppsFlyer account, and marketers should give the agency [access to their apps](/docs/set-up-an-integrated-partner#agency-permissions).

Agency, therefore, doesn’t technically own the apps but only promotes them on the marketing channels it works with, without the technical involvement, such an SDK integration. Depending on the set of permissions given by a marketer, an agency can have control over a range of functions.

When an install is attributed to an ad placed by an agency, it is displayed on agency's dashboard. The app owner will see it too, and will know that it's attributed to the agency.

Note: if your organization owns the app, or handles its development as well as marketing, you should open a marketer account.

## Pricing

The scope of an agency account functionality depends on the permissions provided by the app owner for each app. Therefore, agency accounts are offered **for free**, and only app owners are charged for attribution. App owners and agencies can use AppsFlyer attribution data for compensation purposes.

## Getting started

To set up a new agency account:

1. Complete the [registration form](https://www.appsflyer.com/start/agencies/).
   * Use your company email domain for registration.
   * Use an email address that is not associated with an existing AppsFlyer account.
2. A member of the AppsFlyer agency team may contact you with further information required to complete the registration.
3. Once your account is activated, you get notified and can start using AppsFlyer.

## Adding team members

When your account is up and running, the account admin (the person who opened the account) can add more team members, who can get access to some or all of the apps managed by the agency. For the details of how to add new team members, click here.

## Adding apps to your account

When you first create your account, it has no apps associated with it:

![agency-start.png](https://files.readme.io/b536dde5f7cc886e7fc6ff22f15c402cea5cf68824fd92f242d13037824072d5-360003986997.png)

Any agency individual or team requires permission from the app owner to:

* gain access to the app dashboard
* make configuration changes
* run campaigns

Marketers [provide access to any agency](/docs/set-up-an-integrated-partner#agency-permissions) directly through the platform. Once your account is set up and you've received access to the apps, you can start running campaigns using AppsFlyer features.

### What does it mean to get permission from a marketer

When you get permission from a marketer:

* The app appears in your account.
* You can set up integrations with ad networks for the app (with the exception
  of some networks that require configuration by the app owner).
* You can create attribution links to use in your campaigns.
* You can set up cost integrations with partners (that allow it).
* You can see the app data.
* You can grant permission for ad networks and their team members to view
  basic information about the app.  

  CALLSTART::Note::

  #### Note

  The agency gains control over the main toggle for ad network permissions and the individual permissions nested under it. Both the agency and the advertiser can change these settings, and the most recent change by either party determines the current state.

  CALLEND::

Additional permissions include access to the Cohort report, the Protect360 dashboard, and aggregate organic data. See a [description of the different ad network permissions](/docs/set-up-an-integrated-partner#agency-permissions).

### App list

Once you got permission from the marketer, the app appears on the app's page.

The apps page in your account lists up to 1000 apps. If the list of apps you have permissions for exceeds 1000, some apps are not shown on the list. You can still find them using the search.

![agency-apps.png](https://files.readme.io/6ec28125c938a5fb90d6a5bfe80ef40225432c222dcd4fafd747eeba529f1c49-360003722277.png)

#### Searching for apps

1. In your account, from the top menu, select **My Apps.**
2. In the search field, enter the search term, for example:
   * App Name
   * App ID
   * App Owner Email

## Agency dashboard

Click any app in the list of apps to access its [dashboard](/docs/getting-started-with-appsflyer-dashboards). When you start running campaigns, the aggregate data attributed to you is displayed here.

![agency-dashboard.png](https://files.readme.io/5f541770f60ba7d212c9f18e3a14d625758c5d8911997ce4cc39333ee7530244-360003815398.png)

The Agency account dashboard includes default access to:

* Lifetime value overview dashboard
* In-app events dashboard
* Retargeting dashboard

## Running campaigns

### Self-reporting networks (SRNs)

SRNs, also knows as Self-attributing networks (SANs), are networks that don’t require AppsFlyer’s attribution link in order to report clicks and other data, and use direct integration with AppsFlyer instead. Among these networks are [Meta ads](/docs/meta-ads-faq#attributing-agencies-with-facebook), [X Ads](/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies#any-special-instructions-for-agencies), [Google Ads](/docs/google-ads-adwords-integration-setup-for-agencies), [Snapchat](/docs/snapchat-advanced-srn-integration-setup), DoubleClick, [Apple Ads Search](/docs/apple-ads-integration-setup), [Yahoo](/docs/yahoo-integration-setup), and [Yahoo! JAPAN](/docs/yahoo-japan-search-ads-campaign-configuration#agency-integration).

A majority of these networks require special setup for agencies. For example, since Meta ads and X Ads integration can only be configured by an app owner, the agency campaign names MUST begin with the agency's name to make sure that the installs are eventually correctly attributed to the agency.

Click the links above to read network guides and specific instructions for agency settings.

### Non-SRNs

Most ad networks need attribution links that are placed behind an ad. Read more about running campaigns with them [here](/docs/about-agency-accounts#nonsrns).

### Sandbox attribution agency campaigns

Sandbox attribution infrastructure, part of Android by Google, lets marketers measure campaign success without advertising ID. Although Google doesn't include agencies as part of the Sandbox attribution process, and AppsFlyer can't attribute agencies directly, AppsFlyer still has the ability to provide attribution data for agency campaigns running on Sandbox.

#### Campaign naming

To view your campaigns in the AppsFlyer Sandbox dashboard, the names of campaigns that you configure, should include your partner identifier and be structured as follows:

* your af\_prt ([What's your af\_prt and where to find it](/docs/about-agency-accounts#af_prt-parameter)),
* underscore,
* your actual campaign name that follows your agency’s naming convention.

For example, if your af\_prt is AgencyX, your campaign name may look like this:

`AgencyX_SummerSale`

> 📘 **Note**
>
> #### Note
>
> * Agency campaigns in Sandbox attribution are also transparent and the identity of the ad network running the campaign is not masked from the marketer.


### SKAdNetwork agency campaigns

SKAdNetwork infrastructure, part of iOS by Apple, lets marketers measure campaign success without IDFA or advertising ID. Although Apple doesn't include agencies as part of the SKAdNetwork attribution process, and AppsFlyer can't attribute agencies directly, AppsFlyer still has the ability to provide attribution data for agency campaigns running on SKAdNetworks.

#### Campaign naming

To view your campaigns in the AppsFlyer SKAdNetwork dashboard, the names of campaigns that you configure with the SKAdNetwork, should include your partner identifier and be structured as follows:

* your af\_prt ([What's your af\_prt and where to find it](/docs/about-agency-accounts#af_prt-parameter)),
* underscore,
* your actual campaign name that follows your agency’s naming convention.

For example, if your af\_prt is AgencyX, your campaign name may look like this:

`AgencyX_SummerSale`

> 📘 **Note**
>
> #### Note
>
> * Agency campaigns in SKAdNetwork are also transparent and the identity of the ad network running the campaign is not masked from the marketer. Consider that starting iOS 15, the marketer (app owner) can [opt-in to directly receive a copy of the postback.](https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions_and_postbacks)
> * Make sure the marketer activates the ad network **Partner activation** setting in the Integration tab. Failure to do so will prevent AppsFlyer from sharing decoded postback data with networks, impacting their ability to use it for reporting and optimization. This is in addition to the Partner activation setting that you can access in the user interface.


#### Access to SKAN Conversion Studio

Agencies can [view and download](/docs/skan-conversion-studio#view-cv-mapping) a marketer's SKAN CV mapping configuration in [Conversion Studio](/docs/skan-conversion-studio#skan-conversion-studio-basics), but they can't configure or edit the settings.

#### SKAdNetwork Dashboard

<Embed title="Getting started—agency onboarding" typeOfEmbed="wistia" url="https://fast.wistia.com/embed/iframe/jkm7se0jym" providerUrl="https://fast.wistia.com" />

**Further reading:**

* [SKAdNetwork Quickstart guide](/docs/about-att-and-skan)
* [SKAdNetwork Dashboard](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer)
* [SKAdNetwork Solution](/docs/skadnetwork-skan-solution-guide)

### Single Source of Truth (SSOT) for agencies

SSOT unifies all attribution methods by combining attribution data from different models and removing duplicate installs and the associated cost and revenue-related metrics. This way, eCPI, ROI, and ROAS, for example, are calculated correctly.

Agencies can access SSOT data in the Overview dashboard, but not via API.

To include the SSOT flag in your overview dashboard, the marketer must turn on SSOT in the Conversion Studio.

**Further reading:**

* [Single Source of Truth (SSOT) guide for iOS attribution](/docs/single-source-of-truth-ssot-guide-for-ios-attribution)

## What else you can do

* Measure user retention
* Use in-app events to optimize your campaigns
* Run [retargeting](/docs/retargeting-attribution-guide) campaigns
* Export your [data](/docs/manage-data-access-permissions)
* [Register your test device](/docs/registering-test-devices)
* and more.

You can find more information about advanced Agency account use [here](/docs/about-agency-accounts#agency-setting-up-campaigns).

Stumbled upon an unfamiliar term? Find it in our [Glossary](/docs/appsflyer-knowledge-base-glossary).

Got an urgent technical question? Search our Help Center: we probably have an answer. If we don't, contact our support team via the bottom right corner of your dashboard.