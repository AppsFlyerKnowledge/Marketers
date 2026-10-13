---
title: "Integrated partners—FAQ"
excerpt: "Find answers to frequently asked questions and troubleshooting tips for integrated partners, covering account setup, permissions, postbacks, and anti-fraud."
x-zendesk:
  id: 4406549295249
  url: https://support.appsflyer.com/hc/en-us/articles/4406549295249-Integrated-partners-FAQ
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Learn more
  section_id: 6551121200017
  position: 2
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Advertisers, Ad Networks, Partners, Localize]
  promoted: false
  comments_disabled: true
  created_at: '2021-09-02T09:33:34Z'
  edited_at: '2026-01-14T08:33:02Z'
---
FAQ and integration troubleshooting for integrated partners.

## Account and dashboard

### I want to become an integrated partner

An advertiser should invite you to be onboarded with us.

Share [this invitation procedure](/docs/set-up-an-integrated-partner#invite-new-partners-to-appsflyer) with the advertiser. After the advertiser invites you, you will receive an email with a form to fill out.

Once the form is filled out, we will let you know the next steps.

> ❗️ Important
>
> Use an email that has never been used before to create an account in AppsFlyer. Make sure the advertiser uses the same email in the invitation.

### How can I update my integration?

Take a look at the required update [here](/docs/integration-requests-for-partners) and follow the instructions provided.

If your update isn't listed, contact AppsFlyer using the [partner assistant widget](https://files.readme.io/abd47a9d733ee12aaeef473b3e243f2063034bae8919dc671e4a85e97edb0ab8-42824303168657.gif), include your integration PID, and describe your request.

### How do I change the login email of the account?

Follow [these instructions](/docs/integration-requests-for-partners#create-update-partner-dashboard-login-email).

### I can't find or add an app to the dashboard

If you can't add an app to the **App search** screen, verify that:

- The advertiser has added the app to their dashboard
- The advertiser has activated the app integration with your network and given you [relevant permissions](/docs/set-up-an-integrated-partner#ad-network-permissions).

### The integration with the app isn't active in the dashboard when it definitely should be active

| Reason | Solution |
| --- | --- |
| The integration was activated by an agency and not by the advertiser. Ad network setup is visible to ad networks only when the advertiser (app owner) configures it. | No further action is required. Once the agency activates the integration, attribution and postbacks work normally. |

### I'm not receiving password recovery emails

1. Check your spam folder.
2. Clear the browser cache or open AppsFlyer in a different browser.
3. Try to reset your password again (wait at least 20 minutes after the previous request).
4. If you still don't receive password recovery emails, use the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif) to check the status of your email.

### How do I enable the AppsFlyer Audience integration?

1. Get approval from the advertiser to implement the Audience integration.
2. Email the advertiser's CSM (ask the advertiser for the correct email) **and** contact AppsFlyer Partner Solutions using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).
3. Once the request is approved, we will proceed with the integration.

### How do I enable Advanced Privacy postbacks?

Follow [these instructions](/docs/self-serve-integration-management-for-ad-networks#advanced-privacy-and-skan-postbacks).

### Why can't advertisers find my account?

If your ad network account doesn't show on the Partner Marketplace, it could be due to incomplete integration or because the integration is still under its validation period. For additional details, review the following articles:

- [Self-serve integration management for ad networks](/docs/self-serve-integration-management-for-ad-networks) (for an incomplete integration)
- [Integration validation period](/docs/getting-started-onboarding-guide-for-ad-networks#integration-validation-period)

For agency accounts seeking further assistance, contact AppsFlyer via the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).

### Why don’t I see event data on the dashboard?

To view event data on the dashboard, the advertiser must grant you permission to access aggregated in-app event data. If this permission hasn’t been enabled, event data won’t be displayed.

<Image src="https://files.readme.io/3a0c4a4f28c27479b0927ab33c97a46f1ad58963424c2368fd002af38f22ae81-42824303171601.png" alt="Event data permission screenshot" />

## Partner permissions

### What are the partner permissions?

An advertiser can grant permission to a partner to configure the integration with that partner.

Partners can test the campaign configuration when they have permission to edit and change the partner integration that the advertiser set up.

The permissions are (depending on the advertiser account):

- Integration parameter configurations
- In-app event postback configuration
- Retention reports
- Protect360 dashboard

For more information, visit the [Providing permissions to ad networks](/docs/set-up-an-integrated-partner#permissions-tab) guide.

### I can't configure the integration with the advertiser

| Reason | Solution |
| --- | --- |
| The advertiser did not grant you permission to configure the integration. | Request from the advertiser to make sure that the following permissions are granted to you:<br/>- Ad network permissions (the main toggle)<br/>- Configure integration<br/>- Configuring in-app event postbacks |

### What about agency permissions?

[Read here](/docs/getting-started-agency-onboarding#what-does-it-mean-to-get-permission-from-a-marketer) about agency permissions given by a marketer.

### Why can’t I redirect users to a designated landing page?

The user journey prior to installing an advertised app can impact how users perceive the advertiser’s brand. For this reason, redirection to landing pages is restricted to domains that appear on the advertiser’s [domain redirect allowlist](/docs/set-up-your-domain-redirect-allowlist).

The allowlist is managed by the advertiser. To use a specific landing page, share the page URL with your advertiser and ask them to add its domain to their allowlist.

## Data - postbacks and reports

### How long does it take for results to appear in the dashboard?

Installs appear in the dashboard within two minutes from the moment of an install.

Install and in-app data appears in reports within 15 minutes.

### There are missing dashboard parameters in the postback

| Reason | Solution |
| --- | --- |
| The advertiser didn't define any value for the dashboard parameters. | - If you have access to the application setup,<br/>  1. In the AppsFlyer Dashboard, go to **Active integrations**, and click on your logo.<br/>  2. Under the **Integration** tab, find the relevant parameter and check its value.<br/>  3. If it's not defined, contact the Advertiser and ask to fill in the value.<br/>- If you don't have the application setup, ask the Advertiser to [enable Ad Network Permissions](/docs/set-up-an-integrated-partner#ad-network-permissions) |

### Server-to-Server event data from the advertiser is missing or incorrect

| Reason | Solution |
| --- | --- |
| The Advertiser didn't correctly configure sending S2S data to AppsFlyer. | Contact the advertiser and ask to verify the configuration. |

### I'm not receiving re-engagement postbacks

| Reason | Solution |
| --- | --- |
| Re-engagement postback is disabled in AppsFlyer backend | Use the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif) and ask to verify that re-engagement postback is enabled in AppsFlyer backend. |
| Your postback template doesn't have re-engagement identifier flag. | Use the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif) and ask to add the identifier if it's missing. |
| Retargeting parameter isn't included in a click attribution URL, and therefore re-attribution cannot get recorded in AppsFlyer. | Make sure the parameter `is_retargeting=true` is added to the click attribution URL. |

### I'm not receiving re-attribution postbacks

| Reason | Solution |
| --- | --- |
| Your postback template doesn't have the re-attribution identifier flag. | Use the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif) and ask to add the re-attribution identifier. |
| Retargeting parameter isn't included in a click attribution URL, and therefore reattribution cannot get recorded in AppsFlyer. | Make sure the parameter `is_retargeting=true` is added to the click attribution URL. |

### I'm not receiving correct event identifiers on event postbacks

| Reason | Solution |
| --- | --- |
| Macro `(mapped-iae)` isn't integrated in the in-app event postback. | Use the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif) and request to integrate the macro. Include the following information:<br/>- pid or ad network email<br/>- receiving parameter of partner event identifier<br/>[More on postback macros](/docs/postback-macros-for-ad-networks#postback-macros). |
| Advertiser or agency didn't configure the partner event identifier correctly or at all. | If the click attribution URL contains `af_prt`<br/>ask the agency to check if the partner event identifier is correctly configured on their dashboard.<br/>If not,<br/>ask the advertiser to check if the partner event identifier is correctly configured on their dashboard. |

### I can't see campaign-level data for non-attributed traffic on postbacks

Even if the Advertiser allows sending you postbacks for traffic attributed to all sources, AppsFlyer doesn't share with the partners the campaign-level data attributed to other partners.

### I can't export reports

| Reason | Solution |
| --- | --- |
| The larger the specified date range, the larger the generated file. Large files may require more time to download. | Specify a shorter time range for the report. |
| Too much browser cache can prevent the request from sending out. | Clear the browser cache and try again, or export the report from a different browser. |

### Test installs don't appear in the dashboard

To correctly perform integration tests using test apps, follow the relevant platform guide:

- [Android integration testing for ad networks](/docs/android-integration-testing-for-ad-networks)
- [iOS integration testing for ad networks](/docs/ios-integration-testing-for-ad-networks)

To perform an integration test with an advertised app, follow these [guidelines](/docs/test-marketer-campaign-integration-with-the-ad-network) and make sure the advertiser has allowlisted the device used for testing.

### Install postbacks aren't sent to my servers

If you believe that postbacks aren't sent to your servers:

- Make sure that the postback endpoint is active
- For iOS users, ensure you’ve completed the [Advanced Privacy postback integration](/docs/advanced-privacy-guide-postback-macros-for-ad-networks).

### In-app event postbacks aren't sent to my servers

If you believe postbacks aren’t being sent to your servers, verify the following:

- The postback endpoint is active and reachable.
- For iOS users, ensure you’ve completed the [Advanced Privacy postback integration](/docs/advanced-privacy-guide-postback-macros-for-ad-networks).

### I can't see the in-app events postback setup of agencies

Ad networks get visibility to their setup done by advertisers, **but not when it's done by agencies**. Therefore, when an agency maps in-app events for postbacks to a network, although it's active for the agency, the ad network sees this section as inactive.

#### Example

Yuval is the marketer of the **com.fused** app, which is a client app of the **Sonnet** ad network. Yuval maps the **af\_purchase** event to be sent as a postback to Sonnet when an attributed user to Sonnet performs a purchase.

**Sava**, an agency permitted to work with **com.fused**, also configures **Sonnet** and maps the **af\_completeregistration** event to be sent as postback.

When **Sonnet** logs into the dashboard of **com.fused**, they see only the **af\_purchase** event mapped with them, but not the **af\_completeregistration** event. However, when users attributed to **Sava** perform registrations, the **af\_completeregistration** event is sent to **Sonnet.**

### Click data is missing

If click data is missing from postbacks, make sure that the AppsFlyer link has all the data you want to return to you in the postbacks. See our [attribution link guide](/docs/about-link-structure-and-parameters) for more information.

If the advertiser configured the ad network to receive all postbacks, postbacks for events not attributed to the ad network don't contain click data.

### Revenue data is missing

If revenue data is missing or appears as N/A in the advertiser postbacks, there could be two possible reasons:

- The advertiser has decided not to share revenue data.
- The advertiser has defined the in-app event incorrectly.

### Dashboard data is missing

If your network requires credentials or keys for integration and the advertiser doesn't provide them, postbacks from AppsFlyer are rejected by your servers. Data can't be posted to your server and is therefore missing.

In this case, you'll see data in the dashboard but not in your servers. The advertiser should add any credentials, keys, or tokens in the **General Settings** section of the **Integration** tab.

Verify that the advertiser provided the necessary credentials or keys when configuring the integration with your ad network.

### Data from the advertiser is missing or incorrect

If you test integration with an advertiser and no data (installs, in-app events) is available, follow the suggestions below:

- If the issue happens with any advertiser, contact your PDM
- If the issue happens with only one advertiser or a few advertisers:
  - verify with the advertiser that they implemented the AppsFlyer SDK in their app
  - verify with the advertiser that the SDK implementation is correct

### My agency account doesn't show SKAN data

**Confirm that your campaign name is correct.** To view your campaigns in the Agency SKAdNetwork dashboard, campaign names configured with the SKAdNetwork should include your agency identifier, and should be structured as follows:

your _af\_prt_ \+ underscore (\_) + your actual campaign name that follows your agency’s naming convention.

For example, if your _af\_prt_ is _greatagency_, your campaign name may look like this: _greatagency\_StreamKarxxxxxx._

[More information on SKAN campaigns.](/docs/getting-started-agency-onboarding#skadnetwork-agency-campaigns)

## Anti-fraud (Protect360)

### How can I investigate fraud from AppsFlyer dashboard?

You can check blocked data only if the advertiser gives you access to Protect360 and Raw Data reports.

1. Once the advertiser gives you the P360 access, you can download the blocked install/in-app events reports from the Export Data page of the dashboard. [More about report types](/docs/protect360-raw-data-reports#report-types).
2. In Raw Data reports you can:
   - check the blocking reasons/sub-reasons
   - filter down by Site to see which SiteIDs deliver high numbers of fraud results

You can further investigate this with the publishers that deliver fraudulent traffic and make educated decisions about working with such publishers.

Learn more about [fraud](/docs/protect360-anti-fraud-guide).

### Why are impressions/clicks being capped?

AppsFlyer Protect360 evaluates multiple parameters when determining whether to apply ad engagement capping. These include, but are not limited to, the volume of impressions and clicks, conversion rate (CVR), detected anomaly rates, expected normal fluctuations in activity, and industry- and geography-specific benchmarks. The capping algorithm is dynamic and recalculated on an hourly basis to account for changing trends.

When the capping mechanism is triggered, Protect360 blocks the ad network’s impressions or clicks for the affected app for the remainder of the current 24-hour cycle. Any impressions or clicks generated after the threshold is reached are not recorded by AppsFlyer and are not eligible for attribution.

To avoid reaching the capping threshold, ad networks should pause campaigns or publishers that generate unusually high volumes of ad engagements without a corresponding impact on performance.

For more information, see:

- [Impression and Click Capping](/docs/protect360-for-integrated-partners#impression-and-click-capping)
- [Capping FAQ](/docs/protect360-for-integrated-partners#faq)

### Why was my test install rejected from attribution?

AppsFlyer’s anti-fraud system evaluates installs using multiple protection layers, including analysis of individual installs and install clusters. Install clusters are reviewed across different aggregations—such as by publisher, media source, app, and are assessed using statistical models and machine-learning algorithms.

Each cluster is evaluated as a whole. If a cluster is identified as fraudulent with high statistical confidence, all installs within that cluster are classified as fraudulent, including installs that may otherwise appear legitimate. This approach is necessary because a common fraud tactic is to mix valid installs into large volumes of fraudulent activity in an attempt to dilute detection signals and bypass blocking mechanisms.

By default, all incoming installs are treated as live traffic. To prevent test installs from being evaluated by Protect360 anti-fraud algorithms, you must register your device as a test device before performing the test install.

For instructions, see [Registering test devices](/docs/registering-test-devices).

### What detection methods are used to detect install rejections?

Review the fraud sub-reason associated with the rejection to better understand why the event was blocked. This information is also available in Protect360 reports and on the Protect360 dashboard, subject to the advertiser’s access permissions.

For more details, see [Protect360 blocked reasons](/docs/protect360-raw-data-reports#blocked-reasons).