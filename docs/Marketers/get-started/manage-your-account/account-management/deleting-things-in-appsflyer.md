---
title: "Deleting things in AppsFlyer"
excerpt: "Learn how advertisers can remove apps to stop attribution, remove media sources, or delete user-related data."
x-zendesk:
  id: 360000603117
  url: https://support.appsflyer.com/hc/en-us/articles/360000603117-Deleting-things-in-AppsFlyer
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Account management
  section_id: 6551191075473
  position: 5
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Advertisers, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2018-11-21T16:07:58Z'
  edited_at: '2026-07-15T08:29:57Z'
---
![shutterstock_699498934.jpg](https://files.readme.io/db2cd79f6da6de42042707fb2c8bbfe450a6cdc17a93f7a9dc9ea27d04716ef3-34228068995857.jpg)

## Delete user history

Some privacy regulations, such as GDPR or CCPA, give users a *right to erasure*.

**Scenario:** A user requests that you delete data related to them. GDPR requires that this be done within 30 days.

**Action required:** Use [OpenDSR API](/docs/send-opendsr-api-requests) to send an erasure request.

## Stop attributing installs to a media source

AppsFlyer collects install and event information for your configured media sources. If a media source is configured for attribution, new installs are attributed.

**Scenario:** If you stop running campaigns on a media source with no clicks, impressions, or installs, then attribution stops. However, the in-app events of existing users continue to be recorded and attributed.

**Action required to stop attributing installs to a media source:**

- **SKAN (for iOS apps):** 
  1. [Disable SKAN measurement](/docs/skan-conversion-studio#disable-skan-measurement).
  2. For [Google Ads](/docs/get-skan-postback-data-from-google-ads#turning-off-the-skan-integration) and [Meta ads](/docs/skadnetwork-skan-interoperation-with-meta-ads#turning-off-the-skan-integration), you must also remove the SKAN connections to stop SKAN data recording.
- **SRN:** [Deactivate the partner integration](/docs/partner-activation-deactivation#deactivated-partners).
- **Non-SRNs:**
  1. [Deactivate the partner integration](/docs/partner-activation-deactivation#deactivated-partners).
  2. Incoming clicks and installs from the AppsFlyer attribution link in your ads continue to be recorded and attributed. Make sure that ads displayed to leads no longer contain an AppsFlyer attribution link.
- **Owned media:**
  - Discontinue using relevant OneLink custom links.

## Remove or delete an app

You have the option to temporarily remove an app.

### Temporarily removing an app

When an app is temporarily removed, data recording stops, the app doesn't show on the dashboard, and it appears grayed out on the My Apps page. However, the app remains associated with the account and can be restored. Upon restoring the app, historical data such as app settings, approved agencies, and tokens are retained.

> 📘 Note
>
> Removing an app is done individually. However, you can [remove multiple apps via API](/docs/adding-an-app-to-appsflyer#manage-your-apps-in-bulk-via-api).

**To delete an app:**

1. From the top bar, click **My Apps**.
2. Select an app action menu.
3. Click **Remove**, then confirm.

The app is deleted and no longer displays in the app list.

**To restore an app that was removed:**

- Reach out to your CSM or email to [hello@appsflyer.com](mailto:hello@appsFlyer.com) to start the process. Once the CSM has restored the app, you can re-add it to your account.

## Transfer apps between accounts

See this guide for details: [Transferring apps between accounts](/docs/transferring-apps-between-accounts).

## Delete your account or downgrade your subscription plan

Reach out to your CSM or send an email to [hello@appsflyer.com](mailto:hello@appsFlyer.com).