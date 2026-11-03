---
title: Use the Web SDK Test page
metadata:
  keywords:
    - SDK Test
    - Web Attribution
    - Web Attribution SDK
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-08-23T16:04:12Z'
  edited_at: '2026-10-01T00:42:14Z'
  id: 50118956978577
  locale: ja
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ja/articles/50118956978577
---
> **At a glance:** Use the Web SDK Test page to validate the Web SDK installation and event recording in real time. Run it when you first integrate the SDK and whenever you add or change an event.

## Overview

The Web SDK Test page opens your website in a new browser tab with a dedicated test session. Every Web SDK activity in that tab, including page loads, events, and identity calls, streams live into the test page, where you can inspect each event and its properties. This lets you verify your implementation in minutes, without waiting for data to appear in reports.

Use it to check that:

* The Web SDK loads on the intended pages.
* Your events fire with the correct name, revenue, and properties.
* The customer user ID (CUID) is set after login or signup.

Run a test whenever you first integrate the SDK or change your event setup.

## Prerequisites

Before you run a test, make sure you have:

* A web app in AppsFlyer. For more information, see <Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#web">Create a web app in AppsFlyer</Anchor> in Onboard Web Performance Measurement.
* The AppsFlyer Web SDK is deployed on the pages you want to test. For more information, see the <Anchor target="_blank" href="/marketers/ja/docs/integrate-appsflyer-web-sdk">Integrate AppsFlyer Web SDK</Anchor> section.

## Run a test

Once your prerequisites are in place, run a test as follows:

1. In AppsFlyer, from the side menu, go to **Settings** > **SDK Integration Tests**.
2. Select **Web SDK Test**.
3. In the **Test your Web SDK** dialog:
   * Select your web app.
   * The **URL** field is pre-filled with the app's configured website URL. The test runs on this URL by default. Change it to test a specific page.
4. Click **Start test**. Your website opens in a new browser tab with a dedicated test session. You don't need to do anything there.
5. Return to the Web SDK Test page. Events from the test tab appear automatically in the **Live events** table as you browse and interact with your website.

> 📘 **Note**
>
> The test captures only activity from the browser tab it opens. Visiting your website directly without starting a test doesn't display events on this page.

## View the Live events table

Each row in the **Live events** table shows the event timestamp, type, name, and validation status.

| Event type | What it means |
| --- | --- |
| `pageLoad` | The Web SDK loaded and recorded a visit on a page. |
| `setCustomerUserId` | The SDK sets the customer user ID (CUID). |
| `EVENT` | AppsFlyer recorded an event you defined. The **Event name** column shows the event name, for example, purchase. |

The **Live events** table also supports:

* **Event details:** Click a row to open the Event details panel, to view every property the event includes, for example, revenue and event values.
* **Search:** Use the search box to find a specific event.
* **Export:** Click **Export CSV** to download the results.

## Restart or clear a test

Use one of these options to restart or clear a test:

* **Restart test:** Clears the event list and opens a new browser tab with a new test session. You can use this to start a clean run.
* **Restart with new app / URL:** Reopens the setup dialog to test a different web app or page.
* **Clear logs:** Clears only the event list. The current test session and browser tab stay active, so new events keep streaming in.

## Common testing scenarios

You can just run a test after every change to your Web SDK setup or events. It's the fastest way to catch issues before they affect your data. Common scenarios include:

* **First Web SDK integration:** Browse the pages where you installed the SDK and verify that a `pageLoad` event appears for each one.
* **Adding or changing an event:** Trigger the event on your website, for example, complete a purchase. Then verify that an EVENT row appears with the correct event name, revenue, and properties in the event details.
* **Implementing customer user ID:** Sign up or log in on your website and verify that a `setCustomerUserId` event appears. Setting the CUID improves attribution accuracy and unifies user journeys across platforms.

<div data-zendesk-anchors="h_01WSDKTP0000000000OVRVW=overview h_01WSDKTP0000000000PREQ1=prerequisites h_01WSDKTP0000000000RUNT1=run-a-test h_01WSDKTP0000000000REVW1=view-the-live-events-table h_01WSDKTP0000000000RSTR1=restart-or-clear-a-test h_01WSDKTP0000000000WHEN1=common-testing-scenarios" />
