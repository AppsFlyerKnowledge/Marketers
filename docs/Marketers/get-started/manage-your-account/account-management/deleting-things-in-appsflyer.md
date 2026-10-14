---
title: Deleting things in AppsFlyer
excerpt: >-
  Learn how advertisers can remove apps to stop attribution, remove media
  sources, or delete user-related data.
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2018-11-21T16:07:58Z'
  edited_at: '2026-07-15T08:29:57Z'
  id: 360000603117
  locale: en-us
  section: Account management
  section_id: 6551191075473
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360000603117-Deleting-things-in-AppsFlyer
---
![shutterstock_699498934.jpg](https://files.readme.io/db2cd79f6da6de42042707fb2c8bbfe450a6cdc17a93f7a9dc9ea27d04716ef3-34228068995857.jpg)

## Delete user history

Some privacy regulations, such as GDPR or CCPA, give users a *right to erasure*.

**Scenario:** A user requests that you delete data related to them. GDPR requires that this be done within 30 days.

**Action required:** Use [OpenDSR API](/docs/send-opendsr-api-requests) to send an erasure request.

## Stop attributing installs to a media source

AppsFlyer collects install and event information for your configured media sources. If a media source is configured for attribution, new installs are attributed.

**Scenario:** If you stop running campaigns on a media source with no clicks, impressions, or installs, then attribution stops. However, the in-app events of existing users continue to be recorded and attributed.

**Action required to stop attributing installs to a media source:**

* **SKAN (for iOS apps):**
  1. [Disable SKAN measurement](/docs/skan-conversion-studio#disable-skan-measurement).
  2. For [Google Ads](/docs/get-skan-postback-data-from-google-ads#turning-off-the-skan-integration) and [Meta ads](/docs/skadnetwork-skan-interoperation-with-meta-ads#turning-off-the-skan-integration), you must also remove the SKAN connections to stop SKAN data recording.
* **SRN:** [Deactivate the partner integration](/docs/partner-activation-deactivation#deactivate-a-partner-integration).
* **Non-SRNs:**  
  1. [Deactivate the partner integration](/docs/partner-activation-deactivation#deactivate-a-partner-integration).
  2. Incoming clicks and installs from the AppsFlyer attribution link in your ads continue to be recorded and attributed. Make sure that ads displayed to leads no longer contain an AppsFlyer attribution link.
* **Owned media:**
  * Discontinue using relevant OneLink custom links.

## Remove or delete an app

You have the option to temporarily remove an app.

#### Temporarily removing an app

When an app is temporarily removed, data recording stops, the app doesn't show on the dashboard, and it appears grayed out on the My Apps page. However, the app remains associated with the account and can be restored. Upon restoring the app, historical data such as app settings, approved agencies, and tokens are retained.

> 📘 **Note**
>
> Removing an app is done individually. However, you can [remove multiple apps via API](/docs/adding-an-app-to-appsflyer#manage-your-apps-in-bulk-via-api).

**To delete an app:**

1. From the top bar, click **My Apps*.***
2. Select an app action menu.
3. Click **Remove*,***then confirm.  
   The app is deleted and no longer displays in the app list.

**To restore an app that was removed:**

* Reach out to your CSM or email to [hello@appsflyer.com](mailto:hello@appsFlyer.com) to start the process. Once the CSM has restored the app, you can re-add it to your account.

## Transfer apps between accounts

See this guide for details: [Transferring apps between accounts](/docs/transferring-apps-between-accounts).

## Delete your account or downgrade your subscription plan

Reach out to your CSM or send an email to [hello@appsflyer.com](mailto:hello@appsFlyer.com).

<div data-zendesk-anchors="h_01HNZ7TNZM4P5APM2B1WQ4X7S5=delete-user-history h_01HNZ7VPA16065PGCSZDMQZ3ZC=stop-attributing-installs-to-a-media-source delete-an-app=remove-or-delete-an-app h_01HNZ7XKEFRNEWGQZ58T7H0KDH=remove-or-delete-an-app removing-an-app=temporarily-removing-an-app h_01J52J31FDKSPNWSD5J2V5BYTW=temporarily-removing-an-app h_01HYJ5EPX4B1G1SAF6XGZ7ADWZ=note h_01HNZ7ZW7ZKDSD2TTEX55PYB91=transfer-apps-between-accounts h_01HNZ81GQ8Z6R8DV8Z6SAXYRB9=delete-your-account-or-downgrade-your-subscription-plan" />
