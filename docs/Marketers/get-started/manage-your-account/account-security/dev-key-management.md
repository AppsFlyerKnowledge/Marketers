---
title: "Dev Key management"
excerpt: "Learn how to view, generate, and update your app's Developer Key directly in the App Settings for greater flexibility and security."
x-zendesk:
  id: 37139123425809
  url: https://support.appsflyer.com/hc/en-us/articles/37139123425809-Dev-Key-management
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Account security
  section_id: 6551173202065
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2025-07-14T11:20:11Z'
  edited_at: '2026-10-07T07:41:56Z'
---
**At a glance:** Control and update your app’s Dev Key directly in the App Settings. Giving you greater flexibility and security.

## What is a Dev Key?

The Developer Key (Dev Key) is a unique identifier for your app, used to authenticate event data sent from the SDK and server-to-server (S2S) integrations to AppsFlyer. It’s essential for enabling attribution, sessions, and in-app event measurement.  
By default, all apps in your account share the same Dev Key. But if needed, you can create a unique Dev Key for each app.  
To give you greater control, the Dev Key Management tab in your app settings allows admin users to view and manage Dev keys, including updating or replacing an existing Dev Key.

## Where to find your Dev Keys

In AppsFlyer, from the side menu, select **Settings** > **App Settings**> **Dev Key Management**.

## Dev Key Management

Admins can use the Dev Key Management tab to:

* Generate a unique Dev Key for a specific app.
* Assign a Dev Key already in use by another app in the account.
* Enable default generation of unique Dev keys for new apps.

### Why you might need to change your Dev Key

You may want to change your Dev Key for several reasons:

* **Security**: Rotate the key if it has been exposed to prevent unauthorized access.
* **Account transfers**: Generate a new Dev Key after moving an app to a different account, to align it with the current account.
* **Granularity**: Assign unique keys per app to simplify monitoring, troubleshooting, or access control.

### How to set up and change a Dev Key

After you generate or assign a new Dev Key, it is important to:

* Update the SDK: Replace the Dev Key in your app’s SDK code.
* Release a new version: Submit a new app version with the updated key to the app store.
* Activate the key (required) - Activating the Dev Key is a **required step** for the change to take effect.
* After your developer updates the SDK with the new Dev Key and the new app version is live in the app store, return to the **Dev Key Management** section and click **Activate Dev Key**.
* Until you activate the Dev Key:
  * The existing Dev Key remains active
  * The new Dev Key will stay in a *Pending* state
  * No changes will apply to data collection

> 📘 **Important!**
>
> Activate the Dev Key only after the updated app version is live. Activating too early may cause in-app events and sessions from older app versions to stop being recorded.

1. In AppsFlyer, from the side menu, select Settings > App Settings > SDK authentication.
2. Click Manage Dev Key.
3. Review the impact of changing your Dev Key before continuing.
4. Choose how to set the new Dev Key:
   1. **Select an existing Dev Key** - Choose a Dev Key that already exists in your account (for example, a Dev Key used by another app).
      1. The selected Dev Key will be assigned to this app in a *Pending* state
      2. Your current Dev Key will remain active until you activate the new one
      3. **Activation is required** after the updated app version is live
   2. **Generate new Dev Key** - Create a brand-new, unique Dev Key for this app.

      1. The new Dev Key will be created in a *Pending* state
      2. Your current Dev Key will remain active until activation
      3. **Activation is required** after the updated app version is liveCALLSTART::Note::

      #### Important!

      Regardless of which option you choose, the Dev Key change only takes effect after you manually activate the Dev Key.

      CALLEND::
5. Click Next.
6. Copy and send the Dev key to your developer to they can implement your changes in your SDK and upload the new version of your app to the store.
7. The Dev Key will go into a pending state.
8. Click Activate Dev Key.
9. The Dev Key goes from pending to active.

> 📘 **Note**
>
> * Until users update to the latest app version, in-app events and sessions from earlier versions won’t be recorded. However, installs (attribution) will still be processed correctly.
> * If you're using the S2S API (API2), Dev Key changes may interrupt server-to-server events.
> * Once the Dev Key is activated, it can take up to 30 minutes for data to begin flowing into the system.

### How to set a unique Dev Key for future apps (coming soon - Q2, 2026)

1. In AppsFlyer, from the top right sidebar, click **Account settings.**
2. Click the **Account** tab.
3. Under **Security**, turn on Create unique Dev key per app (for future reference).
4. Note: When enabling unique Dev keys for future apps, existing apps are not affected.