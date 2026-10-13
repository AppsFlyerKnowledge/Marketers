---
title: "Why is my app still pending?"
excerpt: "Follow the status of apps pending publishing to app stores from the AppsFlyer dashboard."
x-zendesk:
  id: 360001533885
  url: https://support.appsflyer.com/hc/en-us/articles/360001533885-Why-is-my-app-still-pending
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Manage your apps
  section_id: 6551015977105
  position: 6
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Google Play, App Store, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2018-10-14T07:22:04Z'
  edited_at: '2024-01-11T12:45:23Z'
---
When you [add your new app](/docs/adding-an-app-to-appsflyer) to the AppsFlyer dashboard, you first choose whether the app is pending or already in the market.

Pending apps in AppsFlyer look the same as live apps. They have accessible dashboards and all attribution measurement works for them. The only difference is the logo of the app which displays with the AppsFlyer logo instead of the actual app logo.

![Pending_App.png](https://files.readme.io/fd280ea8dbcd280aae0a1328d1523f52c51d2f30dc163e7a62deb424ae5bc8ed-360001789338.png)

## What's happening?

AppsFlyer automatically checks the status of the apps several times a day.

If the app is still not live in the store when AppsFlyer checks the status of the app, the app appears as pending in the dashboard. Once the app is finally submitted to iTunes or Google, it updates to active and the app logo changes to the app's original logo.

The status of the app in the dashboard has no effect on data collection and measurement. If the app is live on Google Play or App Store and users install the app and interact with it, install and in-app event data displays in the dashboard just the same.

## Refreshing the app status

For the status of the app to change to active, AppsFlyer checks its status in the store. If you are certain that the app is published in Google Play or iTunes, but it still appears as pending in the dashboard, an admin can manually check its status.

> 📘 Prerequisite
>
> Available to account admin.

**To manually update the app status:**

1. From the top menu bar, click **My Apps**.
2. Next to the pending app, click **Refresh Status.** If the status of the app is unchanged, the app is still displayed as Pending. If it has been updated, the status is shown as Live, and the logo is updated.
![app-refersh-status.png](https://files.readme.io/d995ea3ee3523a8f0d4854f9ec116efc33c892694d56334c483b7d9fa6da8d64-360001704577.png)

## Store country

Some apps are only available in Google Play or iTunes for certain countries. **It is important that the correct country is set for an app** in order for AppsFlyer to be able to check and update its status.

<Tabs>
<Tab title="iOS">

When you [add an iOS app](/docs/adding-an-app-to-appsflyer) to your AppsFlyer dashboard, you choose the Apple Store country in which the app is published. If the wrong country is chosen, AppsFlyer is unable to update the status of the app even if it is published.

To change the Apple Store country:

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings.**
2. Under **App Store Country** choose the correct country
3. Scroll down and click **Save Settings**
4. If the app still appears as pending, [click **Refresh Status**](/docs/why-is-my-app-still-pending#refreshing-the-app-status).

</Tab>
<Tab title="Android">

When you [add an Android app](/docs/adding-an-app-to-appsflyer) to your AppsFlyer dashboard, there is no option to choose a Google Play country and it is set to US by default. If your app is not published in the US Google Play store, it is important that the correct store is set for the app in order for AppsFlyer to be able to check and update the status of the app.

To change the Google Play country:

1. In AppsFlyer, from the side menu, select **Settings** > **App Settings.**
2. Under **App Store Country** choose the correct country
3. Scroll down and click **Save Settings**
4. If the app still appears as pending, [click **Refresh Status**](/docs/why-is-my-app-still-pending#refreshing-the-app-status).

</Tab>
</Tabs>