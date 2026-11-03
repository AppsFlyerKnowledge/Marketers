---
title: 'Product Line: Group apps for cross-platform attribution'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2025-09-30T07:06:57Z'
  edited_at: '2026-10-13T00:45:43Z'
  id: 39524780935185
  locale: ko
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ko/articles/39524780935185
---
> **At a glance:** Group platform-specific apps under a single brand using Product Line. Unlock cross-platform attribution and user journey insights across mobile, web, and CTV apps using a unified Customer User ID (CUID).

## About Product Line

Product Line lets you organize different platform versions of the same app (like Android, iOS, web, and CTV) under one brand umbrella. This simplifies app management and enables seamless cross-platform attribution based on a customer user identifier (CUID).

With Product Lines, you can:

* Measure user Lifetime Value (LTV) across devices
* Analyze behavior across platforms
* Internally group apps under the same brand
* Opt in to cross-platform re-engagement measurement

  Note: Cross-platform re-engagement measurement is optional. When you opt in, AppsFlyer can attribute eligible returning-user activity to the media source that re-engaged the user across platforms. For more information, see <Anchor target="_blank" href="/marketers/ko/docs/beta-user-based-cross-platform-re-engagement-attribution">Cross-platform re-engagement measurement</Anchor>.

For example, if a user installs your app on iOS, logs in on the PlayStation app, and streams content via their Samsung TV, you can view their full journey as a single user.

For a more complete overview of Product Lines, see <Anchor target="_blank" href="/marketers/ko/docs/beta-user-based-cross-platform-attribution">User-based cross-platform attribution</Anchor>.

## How to set up a Product Line

### Prerequisites

* The **CUID (Customer User Identifier)** must be a consistent identifier (like a login ID or hashed email) across all platforms.
* Implement the **CUID SDK or** [**s2s**](https://dev.appsflyer.com/hc/docs/set-customer-user-id) **setup.**
* Ensure the app sets the CUID at every launch used to recognize the same user across devices and sessions.

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

**Note:** Cross-platform re-engagement attribution works on top of cross-platform attribution. Before you can opt in to re-engagement, you must create a Product Line, activate cross-platform attribution, and send events with a valid CUID.To learn how re-engagement attribution works across platforms, see <Anchor target="_blank" href="/marketers/ko/docs/beta-user-based-cross-platform-re-engagement-attribution">Cross-platform re-engagement attribution</Anchor>.

<div id="how-to-remove-an-app-from-a-product-line" />

<Accordion title="How to remove an app from a Product Line">

> 🚧 **Important!**
>
> It is not recommended to remove an app from a Product Line. When an app is removed or moved, its cross-platform attribution settings are reset, and future events will not be eligible for cross-platform attribution until a new mapping is created.

1. Go to **My Apps**.
2. Under the **Product Lines** section, click the Product Line you want to edit.
3. On the right-hand side of the window, you will see all the apps in the Product Line.
4. Hover over the app you want to remove, and then click the **X** on that app.
5. After removing the app, click **Update** at the bottom of the window.

</Accordion>

<div id="how-to-add-an-app-to-a-product-line" />

<Accordion title="How to add an app to a Product Line">

1. Go to **My Apps**
2. Under the **All Apps** section, hover over the app you want to add, and then select the checkbox.
3. On the top banner ribbon, select **Add to Product Line**.
4. Select the Product Line you want to add the app to.
5. Confirm everything is correct in the Product Line window, and then click **Update** at the bottom of the window.

</Accordion>

<div id="how-to-delete-a-product-line" />

<Accordion title="How to delete a Product Line">

> 🚧 **Important!**
>
> It is not recommended to delete a Product Line. When a Product Line is removed, its cross-platform attribution settings are reset, and future events will not be eligible for cross-platform attribution until a new mapping is created.

1. Go to **My Apps**.
2. Under the **Product Lines** section, click the three dots on the Product Line you want to remove.
3. Select **Delete product line**.

</Accordion>

## Traits and limitations

| Trait | Description |
| --- | --- |
| App grouping | Apps must belong to the same brand |
| Maximum apps | Up to 30 apps per Product Line |
| One Product Line only | An app can belong to only one Product Line at a time |
| CUID requirement | Required only for cross-platform attribution |
| Inactivity restoration window | 14–390 days (default: 90 days) |
| App removal impact | Removing an app resets attribution settings<br /><br />Removing an app from a Product Line affects cross-platform attribution from that point forward.<br /><br />• Future in-app events from the removed app are not eligible for cross-platform attribution under that Product Line, because events must come from apps that belong to the Product Line.<br /><br />• Historical results aren’t retroactively reprocessed |

## FAQs

**Can I use Product Lines just for organizing apps?**  
Yes. Leave the cross-platform toggle **off** to group apps for management only.

**What happens if I remove an app from a Product Line?**  
It is not recommended to remove an app from a Product Line. When an app is removed or moved, its cross-platform attribution settings are reset, and future events will not be eligible for cross-platform attribution until a new mapping is created.

**Does creating a Product Line have any impact about classic AppsFlyer attribution results?**

No, creating a Product Line does not impact classic AppsFlyer device-level attribution results

<div data-zendesk-anchors="h_01K6CQ3YXD9QGGMM08WJWNKX65=about-product-line h_01K6CQ3YXHBXVHE2V0WATR74T5=how-to-set-up-a-product-line h_01K6CQ3YXHXXYXKKQ3Q7B6N9JQ=prerequisites h_01K6CQ3YXKBMS7NZSH0GSJMTBM=how-to-create-a-product-line h_01K6CQ8MJFXS6WNWE0GPV18NPT=how-to-remove-an-app-from-a-product-line h_01K6CQPY31VW8BS7DR2TSKRPZZ=important h_01K6CQ8MJFRD9R9SNZ84D6QQB4=how-to-add-an-app-to-a-product-line h_01K6CQ8MJF61375RE001YMMS4E=how-to-delete-a-product-line h_01K6CQPY31DB9DKQJEBX1PXDPT=important-1 h_01K6CQ3YXZM5F0DVGTAQNHHN9B=traits-and-limitations h_01K6CQD81T4VNMMNVH0X9SZ1TT=faqs" />
