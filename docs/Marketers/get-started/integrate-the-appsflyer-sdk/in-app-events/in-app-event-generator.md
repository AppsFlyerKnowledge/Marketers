---
title: "In-app event generator"
excerpt: "Automatically create the app code (native Android and iOS, Unity) for sending in-app events by defining the event names and content according to your business needs."
x-zendesk:
  id: 10457123447953
  url: https://support.appsflyer.com/hc/en-us/articles/10457123447953-In-app-event-generator
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: In-app events
  section_id: 6551285343761
  position: 3
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-guy-sarfatty, Marketers, Mobile Attribution]
  labels: [Developers, Marketers]
  promoted: true
  comments_disabled: true
  created_at: '2022-11-08T12:47:30Z'
  edited_at: '2023-11-02T10:46:46Z'
---
## Introduction

In-app events are a major tool for **app owners to measure the quality of their users coming from different sources** based on the actions they take after app installation. Events are also often used for performing CPA-based marketing campaigns.

However, more than one person is often involved in the definition and integration of in-app events into the apps. While the marketer/product manager defines the event set content according to business needs, one or more mobile developers are generally required to implement the in-app events API in their apps.

AppsFlyer's [In-app event generator](https://evgen.appsflyer.com/) **solves the challenges inherent in this essential collaboration between marketer and developer**.

By using the In-app event generator marketers can:

* Use a pre-defined **recommended set of events** and parameters for their vertical.
* Add or remove pre-defined or customized events/parameters, descriptions, triggers, and examples for reference.
* **Send auto-generated code** to their Android and iOS mobile developers – **saving days of work,** redundant communication, and potential errors.
* **Re-use their work** if they later update events, add new events, or add new apps.

## Using the In-app event generator

**Use the In-app event generator to create an event set for a new app, or to update an existing set.**

### Creating a new event set

**To create a new event set:**

1. Go to the [In-app event generator](https://evgen.appsflyer.com/) and enter the name of your app.
2. Select a vertical or import the event set of a similar app that was previously exported to a JSON file.
3. Add or remove events and parameters, according to your business needs.
4. Click the **`</>` Code** button to view and copy the generated code for your developers: Java (native Android), Obj-C/Swift (native iOS), or C# (Unity).
5. Click **Download .zip** to save the event set for future use or for collaborating with devs and colleagues.

### Updating an existing event set

**To update an existing event set:**

1. Go to the [In-app event generator](https://evgen.appsflyer.com/).
2. Import an event set of your app that was previously exported to a JSON file.
3. Add or remove events and parameters, according to your business needs.
4. Click the **`</>` Code** button to view and copy the generated code for your developers: Java (native Android), Obj-C/Swift (native iOS), or C# (Unity).
5. Click **Download .zip** to save the event set for future use or for collaborating with devs and colleagues.

### Adding events

**To add a new event to the event set:**

1. Click the **+ Event** button. The new event appears at the bottom of the event set.
2. Select a **predefined** event from the suggested list of events (recommended), or click **Custom** to define your own event name. Verify that the event name doesn't already exist in the event set.
3. Enter the purpose of the event, describing the business scenario.
4. Enter the trigger action for the event, explaining the time in the user journey that the event should be sent. This explanation is added as a comment in the generated code for quick reference by the developers.
5. [Optional] Add one or more parameters to the event.

### Adding parameters

**To add a new parameter to the event set:**

1. Click the **+ Add parameter** button for the relevant event.
2. Select a **predefined** parameter from the suggested list of parameters (recommended).
3. Otherwise, click **Custom** to define your own parameter name and press **Enter**.
4. Type one or more typical parameter values for reference.
5. To help your developers, type a general description, field type, or the corresponding source for the parameter value in your app. This appears as a comment for each event parameter in the generated code.

**Note**: [Predefined naming](/docs/in-app-events-overview#predefined-and-custom-events) allows automatic mapping of events and parameters to partners and is the recommended method.

> 📘 **See also**
>
> * Events dashboard