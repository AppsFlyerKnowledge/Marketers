---
title: Deleting things in AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2018-11-21T16:07:58Z'
  edited_at: '2026-07-15T08:29:57Z'
  id: 360000603117
  locale: en-us
  section: Account management
  section_id: 6551191075473
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360000603117-Deleting-things-in-AppsFlyer
---
> **At a glance:** Learn how advertisers can remove apps to stop attribution, remove media sources, or delete user-related data.

<Image alt="shutterstock_699498934.jpg" src="https://files.readme.io/db2cd79f6da6de42042707fb2c8bbfe450a6cdc17a93f7a9dc9ea27d04716ef3-34228068995857.jpg" width="363px" />

## Delete user history

Some privacy regulations, such as GDPR or CCPA, give users a *right to erasure*.

**Scenario:** A user requests that you delete data related to them. GDPR requires that this be done within 30 days.

**Action required:** Use <Anchor target="_blank" href="/marketers/fr/docs/send-opendsr-api-requests">OpenDSR API</Anchor> to send an erasure request.

## Stop attributing installs to a media source

AppsFlyer collects install and event information for your configured media sources. If a media source is configured for attribution, new installs are attributed.

**Scenario:** If you stop running campaigns on a media source with no clicks, impressions, or installs, then attribution stops. However, the in-app events of existing users continue to be recorded and attributed.

**Action required to stop attributing installs to a media source:**

* **SKAN (for iOS apps):**
  1. <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#disable-skan-measurement">Disable SKAN measurement</Anchor>.
  2. For <Anchor target="_blank" href="/marketers/fr/docs/get-skan-postback-data-from-google-ads#turning-off-the-skan-integration">Google Ads</Anchor> and <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-interoperation-with-meta-ads#turning-off-the-skan-integration">Meta ads</Anchor>, you must also remove the SKAN connections to stop SKAN data recording.
* **SRN:** <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation#deactivate-a-partner-integration">Deactivate the partner integration</Anchor>.
* **Non-SRNs:**  
  1. <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation#deactivate-a-partner-integration">Deactivate the partner integration</Anchor>.
  2. Incoming clicks and installs from the AppsFlyer attribution link in your ads continue to be recorded and attributed. Make sure that ads displayed to leads no longer contain an AppsFlyer attribution link.
* **Owned media:**
  * Discontinue using relevant OneLink custom links.

## Remove or delete an app

You have the option to temporarily remove an app.

#### Temporarily removing an app

When an app is temporarily removed, data recording stops, the app doesn't show on the dashboard, and it appears grayed out on the My Apps page. However, the app remains associated with the account and can be restored. Upon restoring the app, historical data such as app settings, approved agencies, and tokens are retained.

> 📘 **Note**
>
> Removing an app is done individually. However, you can <Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer#manage-your-apps-in-bulk-via-api">remove multiple apps via API</Anchor>.

**To delete an app:**

1. From the top bar, click **My Apps**.
2. Select an app action menu.
3. Click **Remove**, then confirm.  
   The app is deleted and no longer displays in the app list.

**To restore an app that was removed:**

* Reach out to your CSM or email to [hello@appsflyer.com](mailto:hello@appsFlyer.com) to start the process. Once the CSM has restored the app, you can re-add it to your account.

## Transfer apps between accounts

See this guide for details: <Anchor target="_blank" href="/marketers/fr/docs/transferring-apps-between-accounts">Transferring apps between accounts</Anchor>.

## Delete your account or downgrade your subscription plan

Reach out to your CSM or send an email to [hello@appsflyer.com](mailto:hello@appsFlyer.com).

<div data-zendesk-anchors="h_01HNZ7TNZM4P5APM2B1WQ4X7S5=delete-user-history h_01HNZ7VPA16065PGCSZDMQZ3ZC=stop-attributing-installs-to-a-media-source delete-an-app=remove-or-delete-an-app h_01HNZ7XKEFRNEWGQZ58T7H0KDH=remove-or-delete-an-app removing-an-app=temporarily-removing-an-app h_01J52J31FDKSPNWSD5J2V5BYTW=temporarily-removing-an-app h_01HYJ5EPX4B1G1SAF6XGZ7ADWZ=note h_01HNZ7ZW7ZKDSD2TTEX55PYB91=transfer-apps-between-accounts h_01HNZ81GQ8Z6R8DV8Z6SAXYRB9=delete-your-account-or-downgrade-your-subscription-plan" />
