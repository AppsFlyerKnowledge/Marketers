---
title: "Product Line: Group apps for cross-platform attribution"
excerpt: "Group platform-specific apps under a single brand using Product Line. Unlock cross-platform attribution and user journey insights across mobile, web, and CTV apps using a unified Customer User ID (CUID)."
x-zendesk:
  id: 39524780935185
  url: https://support.appsflyer.com/hc/en-us/articles/39524780935185-Product-Line-Group-apps-for-cross-platform-attribution
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Manage your apps
  section_id: 6551015977105
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-moran-davida, Marketers, Cross-Platform Measurement]
  labels: []
  promoted: false
  comments_disabled: true
  created_at: '2025-09-30T07:06:57Z'
  edited_at: '2026-09-09T08:00:03Z'
---
## About Product Line

Product Line lets you organize different platform versions of the same app (like Android, iOS, web, and CTV) under one brand umbrella. This simplifies app management and enables seamless cross-platform attribution based on a customer user identifier (CUID).

With Product Lines, you can:

- Measure user Lifetime Value (LTV) across devices
- Analyze behavior across platforms
- Internally group apps under the same brand
- Opt in to cross-platform re-engagement measurement

> 📘 Optional cross-platform re-engagement
>
> Cross-platform re-engagement measurement is optional. When you opt in, AppsFlyer can attribute eligible returning-user activity to the media source that re-engaged the user across platforms. For more information, see [Cross-platform re-engagement measurement](/docs/beta-user-based-cross-platform-re-engagement-attribution).

For example, if a user installs your app on iOS, logs in on the PlayStation app, and streams content via their Samsung TV, you can view their full journey as a single user.

For a more complete overview of Product Lines, see [User-based cross-platform attribution](/docs/beta-user-based-cross-platform-attribution).

## How to set up a Product Line

### Prerequisites

- The **CUID (Customer User Identifier)** must be a consistent identifier (like a login ID or hashed email) across all platforms.
- Implement the **CUID SDK or** [**s2s**](https://dev.appsflyer.com/hc/docs/set-customer-user-id) **setup.**
- Ensure the app sets the CUID at every launch used to recognize the same user across devices and sessions.

### How to create a Product Line

1. Go to **My Apps**.
2. From the top bar, click **Create Product Line**.
3. Select up to 30 apps to include -> **Create**.
4. In the new window:
   1. Add a **Product Line name.**
   2. Enable **Start measuring and analyzing cross-platform.**
      
      Note: without this enabled, cross-platform attribution won't work.
   3. Select the **Inactivity window.**
   4. Select if you want Re-engagement cross-platform measurement on.
      1. Select the **Re-engagement window**.
      2. Select the **Inactivity window for re-engagement.**
5. On the right-hand side, you will see all the apps in the Product Line.
6. Click **Create**.
7. Send the **CUID implementation instructions** to your developer.

> 📘 Note
>
> Cross-platform re-engagement attribution works on top of cross-platform attribution. Before you can opt in to re-engagement, you must create a Product Line, activate cross-platform attribution, and send events with a valid CUID.To learn how re-engagement attribution works across platforms, see [Cross-platform re-engagement attribution](/docs/beta-user-based-cross-platform-re-engagement-attribution).

### How to remove an app from a Product Line

> 🚧 Important!
>
> It is not recommended to remove an app from a Product Line. When an app is removed or moved, its cross-platform attribution settings are reset, and future events will not be eligible for cross-platform attribution until a new mapping is created.

1. Go to **My Apps**.
2. Under the **Product Lines** section, click the Product Line you want to edit.
3. On the right-hand side of the window, you will see all the apps in the Product Line.
4. Hover over the app you want to remove, and then click the **X** on that app.
5. After removing the app, click **Update** at the bottom of the window.

### How to add an app to a Product Line

1. Go to **My Apps**
2. Under the **All Apps** section, hover over the app you want to add, and then select the checkbox.
3. On the top banner ribbon, select **Add to Product Line**.
4. Select the Product Line you want to add the app to.
5. Confirm everything is correct in the Product Line window, and then click **Update** at the bottom of the window.

### How to delete a Product Line

> 🚧 Important!
>
> It is not recommended to delete a Product Line. When a Product Line is removed, its cross-platform attribution settings are reset, and future events will not be eligible for cross-platform attribution until a new mapping is created.

1. Go to **My Apps**.
2. Under the **Product Lines** section, click the three dots on the Product Line you want to remove.
3. Select **Delete product line**.

## Traits and limitations

| Trait | Description |
| --- | --- |
| App grouping | Apps must belong to the same brand |
| Maximum apps | Up to 30 apps per Product Line |
| One Product Line only | An app can belong to only one Product Line at a time |
| CUID requirement | Required only for cross-platform attribution |
| Inactivity restoration window | 14–390 days (default: 90 days) |
| App removal impact | Removing an app resets attribution settings<br />Removing an app from a Product Line affects cross-platform attribution from that point forward.<br />• Future in-app events from the removed app are not eligible for cross-platform attribution under that Product Line, because events must come from apps that belong to the Product Line.<br />• Historical results aren’t retroactively reprocessed |

## FAQs

<Accordion title="Can I use Product Lines just for organizing apps?">

Yes. Leave the cross-platform toggle **off** to group apps for management only.

</Accordion>

<Accordion title="What happens if I remove an app from a Product Line?">

It is not recommended to remove an app from a Product Line. When an app is removed or moved, its cross-platform attribution settings are reset, and future events will not be eligible for cross-platform attribution until a new mapping is created.

</Accordion>

<Accordion title="Does creating a Product Line have any impact about classic AppsFlyer attribution results?">

No, creating a Product Line does not impact classic AppsFlyer device-level attribution results

</Accordion>