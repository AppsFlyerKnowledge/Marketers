---
title: "Insider integration with AppsFlyer"
excerpt: "Insider, an AppsFlyer integrated partner, is a marketing and analytics platform for mobile and web apps. Insider delivers real-time predictive segmentation and personalization across web, mobile web, mobile app and ad channels."
x-zendesk:
  id: 360016827838
  url: https://support.appsflyer.com/hc/en-us/articles/360016827838-Insider-integration-with-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: 3rd-party platforms
  section_id: 6551199962257
  position: 12
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-01-03T11:23:45Z'
  edited_at: '2026-06-16T09:42:07Z'
---
![rockerbox-logo_en-us.png](https://cdn.appsflyer.com/marketplace/static/logo/useinsider.png?v=1)

> 📘 **Important!**
>
> [Some media sources](/docs/about-raw-data-identifier-restrictions#media-source-restrictions) restrict sharing data with third parties. Therefore, postbacks for restricted events won't be sent to this partner, regardless of the configured selection for sending postbacks.

## Setting up Insider

**Prerequisite:** An account with the partner. If you don't have an account, contact the partner to open one before setting up the integration.

**To set up a new integration:**

1. In AppsFlyer, go to **Collaborate > Partner Integrations > Marketplace** tab.  
   (**To edit an existing integration:** Go to **Collaborate > Partner Integrations > Active integrations** tab.)
2. Select the relevant app.
3. Search for the partner and select **Integrate**.
4. In the **Integration** tab, turn on the **Activate partner** toggle.   
   Note: The toggle **must stay on (active) as long as you work with the partner**. [Learn more](/docs/partner-activation-deactivation)
5. Complete the configuration using the relevant tabs, as described below.

<div id="integration-tab" />

<Accordion title="Integration tab">

The Integration Tab is divided into different sections as described below.

### Activate partner

This toggle must be enabled for as long as you work with the partner.  
Learn more about [partner activation](/docs/partner-activation-deactivation#activate-a-partner-integration).

### General settings

Insider connects with AppsFlyer via a unique partner identifier.

**To obtain your identifier,** log in to the **Insider** platform, and copy your identifier in the upper right corner of the dashboard.

![insider-partner-ID_en-us.png](https://files.readme.io/5755dcc63db5714eb651c74b89e24bee769f792190d9aad0bfc0a742d321eb47-360015601658.png)

### Default postbacks

AppsFlyer can send automatic postbacks to Insider following user installs. Use this section to define the source of the users that the postbacks are sent to for each event. Learn more about [default postbacks](/docs/set-up-an-integrated-partner#default-postbacks).

**To send postbacks for any user that downloads the app to Insider**, select **All media sources, including organic**.

### In-app events settings

![insider-partner-field.png](https://files.readme.io/ad4b4a5e9d688be93b20ccf645c779c361390cc95e2a2acbab7299408b7478bf-4403354160785.png)

In this section, you map AppsFlyer events with the partner via postbacks. Learn more about [in-app event postbacks.](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration)

**To configure in-app events postbacks:**

1. Enter the **Insider partner**, found in the upper right corner of the **Insider** dashboard.

   ![insider-partner-ID_en-us.png](https://files.readme.io/5755dcc63db5714eb651c74b89e24bee769f792190d9aad0bfc0a742d321eb47-360015601658.png)
2. In AppsFlyer, Enable **In-app event postback.**
3. Click **Add Event** to add an SDK Event to the list.
4. Select the **SDK event name** from the dropdown menu.
5. Enter the **Partner Event Identifier**.
6. Select the **Sending option**.
7. Select the required option from the Send revenue dropdown menu:
   * **No values & no revenue:** sends only the event itself without the event value.
   * **Values & no revenue:** sends all the parameters excluding the revenue value.
   * **Values & revenue**: sends all the event parameters, including the revenue value (if exists in the event).
8. To complete the integration configuration, click **Save Integration**.

> 📘 **Note**
>
> To enable postbacks, set the InsiderID as the CUID.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Attribution link tab">

Attribution Links are not available for this partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Cost tab">

Cost data is not applicable in the integration with this partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Ad revenue tab">

Ad Revenue is not applicable in the integration with this partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Permissions tab">

Permissions are not available for this partner.

</Accordion>

<div data-zendesk-anchors="h_01H9FK8YZMFS4XHX69CG90A18K=important h_01H9FK8YZM63N7HF514RVFPMJY=setting-up-insider h_01H9FK8YZN7D4R6TBABMDB3K3K=integration-tab h_01H9FK8YZNMN9QBRS33WPZQWPB=activate-partner h_01H9FK8YZNAFP5G2B277YPNY68=general-settings h_01H9FK8YZNZWSD64K3R2TVHCE2=default-postbacks inapp-events-settings=in-app-events-settings h_01H9FK8YZN15KPHHA58XRABRD4=in-app-events-settings h_01K88DMNP3SKDE93SXGXJXTE0C=note h_01H9FK8YZNJ86KQT59H9RD5CJA=attribution-link-tab h_01H9FK8YZN99ZBQQFBZF26HJZJ=cost-tab h_01H9FK8YZNAJ1XW7TSQWT7PYPW=ad-revenue-tab h_01H9FK8YZQTKN1SFMN9M0CKVYM=permissions-tab" />
