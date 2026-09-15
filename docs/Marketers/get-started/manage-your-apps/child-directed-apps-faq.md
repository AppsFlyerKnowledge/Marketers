---
title: "Child-directed apps—FAQ"
excerpt: "Get answers to frequently asked questions about privacy compliance, SDK tools, and attribution for apps directed towards children."
---
**At a glance:** Get answers to frequently asked questions about apps directed towards children.

## Overview

There are many policies, laws, and regulations on child-directed apps to protect children's privacy. The main ones are [COPPA](https://www.ftc.gov/legal-library/browse/rules/childrens-online-privacy-protection-rule-coppa) and [GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=EN#d1e2029-1-1). In recent years, platforms such as iOS and Android have implemented policies for improved privacy for children. When creating an app, one of the first things to do is determine whether it’s directed to children only or to a mixed audience (both children and adults). Learn from [this guide](https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf) how to implement a compliant attribution solution for apps directed to children.

## Adding a child-directed app

<Accordion title="What steps do I need to take when adding a child-directed app?">

1. [Follow the Add app wizard](/docs/adding-an-app-to-appsflyer).
2. For step 2 of the wizard, [see instructions about child-directed apps](/docs/adding-an-app-to-appsflyer#define-app-audience).
3. After the app is added:
   - Implement the [Dev key](/docs/basic-sdk-integration-guide#retrieving-the-dev-key) in the SDK
   - Include appropriate [privacy controls](https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf)

See more details about [implementing compliance tools with ad networks](/docs/child-directed-apps-faq#implementing-compliance-tools).

</Accordion>

<Accordion title="When adding a new app, what happens after marking it as directed towards children?">

Two weeks after adding the app, you'll get a notification asking you to confirm you've implemented privacy controls for your child-directed apps. After confirming, you'll get a confirmation message. You can always access the confirmation message from the Notification center or see the confirmation details in the [Audit log](/docs/audit-log).

</Accordion>

<Accordion title="Can I change my selection of an app that's directed toward children?">

At this stage, once you select whether an app is directed toward children or not, your selection can't be reversed. This option is only possible while adding the app.

</Accordion>

<Accordion title="How can I see if someone in my team marked an app as directed toward children?">

Once confirmed that an app is directed toward children, there are two ways you can see the confirmation:

- **Notification center:** From the menu bar, click the notification icon ![notificatin center icon.png](https://files.readme.io/5d0b4f1712ba0c05786025adf183e065a2144e1917542ebec0f302688dccb5eb-18473195561489.png) and find the confirmation notification.
- **Audit log:**  1. From the menu bar, access the user menu (email address drop-down).
2. Select **Security center.**
3. In the **Audit log** section, click **View audit log.** You can see the confirmation details under the **My apps** service.

</Accordion>

## Implementing AppsFlyer compliance tools

<Accordion title="How do I know which tool to use?">

When your app is intended for children or a mixed audience (children and adults), you can use any of the recommended tools from [this guide](https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf) that align with the legal requirements. See more SDK resources at the bottom of this page.

#### Examples of compliance tools and their use

| Tool | iOS | Android | Raw data availability |
| --- | --- | --- | --- |
| [Strict SDK](/docs/additional-sdk-integration-guide#strictmode-sdk): <br/>Ensures that the IDFA isn't sent to AppsFlyer. This is usually recommended for apps directed toward children. | **✓** | - | Available only to advertisers |
| Standard SDK using the [`setDisableAdvertisingIdentifiers` API](/docs/android-oaid-implementation-in-the-sdk#opting-out-of-oaid-collection):<br/>Ensures that AAID (Google’s Android advertising ID) isn’t sent to AppsFlyer. This is usually recommended for apps directed toward children. | - | **✓** | Available only to advertisers |
| Standard SDK with an age gate using the [`setSharingFilterForPartners` function](/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data) for **specific** ad networks: <br/>Prevents such ad networks from accessing data when users fall below the age gate\*. | **✓** | **✓** | Limited for specific ad networks |
| Standard SDK with an age gate using the [`setSharingFilterForPartners` function](/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data) for **all** ad networks:<br/>Prevents all ad networks from accessing data when users fall below the age gate\*. | **✓** | **✓** | Available only to advertisers |
| [SKAN only](/docs/skadnetwork-skan-solution-guide):<br/>Ensures the advertising ID isn't shared with other ad networks. | **✓** | - | Available only to advertisers |
| SDK-less solutions (less recommended):<br/>Configure your own servers to send data to AppsFlyer as an alternative to sending data via the SDK. | **✓** | **✓** | According to your configuration |
| [Aggregated Advanced Privacy framework](/docs/apply-aggregated-advanced-privacy-framework): <br/>Enforces Apple ATT privacy levels, making sure user-level data is unavailable to advertisers or ad networks. | **✓** | - | Not available to advertisers or to ad networks |
| \* When applying an age gate block, user-level data that doesn't fall under the age gate is available in raw data reports. |

</Accordion>

<Accordion title="How does using the tools in the guide affect attribution?">

[The AppsFlyer compliance solution guide](https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf) offers different tools, each with [different levels of control](/docs/child-directed-apps-faq#how-do-i-know-which-tool-to-use). The impact on attribution varies based on the specific tool you choose to implement.

When using a tool that limits the sending of user data, such as the device ID, other attribution methods are used, such as [probabilistic modeling](/docs/appsflyer-attribution-model#probabilistic-modeling) or [Install referrer (for Android)](/docs/appsflyer-attribution-model#install-referrer-android-only).

Tools that don’t send user-level data are considered privacy-preserving and enable receiving aggregated campaign data.

</Accordion>

<Accordion title="I don't know if the ad network I'm working with is compliant, what do I do?">

It's often unclear whether ad networks you collaborate with are compliant with relevant laws. You can refer this question to the ad network. If they aren't compliant or you're unsure, you can avoid sharing with them your data. You can use the **[`setSharingFilterForPartners` function](/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data)** to specify which ad networks to block from receiving your app data. You can also use this function to block all ad networks. See more [example compliance tools](/docs/child-directed-apps-faq#examples-of-compliance-tools-and-their-use).

</Accordion>

<Accordion title="Do I need to implement AppsFlyer compliance tools if the ad network is compliant?">

AppsFlyer compliance tools must always be implemented. Which ones are appropriate for your needs depends on the audience of your app. You may use **[`setSharingFilterForPartners` function](/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data)** (“MediaSourceName”) if the ad network you're working with has committed to treat the data you've shared with them solely as a data processor for limited purposes allowed under COPPA, GDPR, applicable laws and rules, or other platform rules that require it and with appropriate consent

This applies to each of the ad networks you're working with.

</Accordion>

<Accordion title="What data am I sharing with ad networks? What control do I have over this?">

Ad networks that aren't [SRNs](/docs/self-reporting-networks-srns) receive your data via postbacks. They can define which events to include in the postbacks. Install postbacks are sent by default for attribution, while in-app event postbacks are only sent if you've [configured specific events](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration) to be sent. As long as postbacks aren't blocked or restricted by the SDK, they may contain user-level data related to app user engagements (installs, in-app events, and re-engagements).

Except for postbacks, ad networks and agencies have [limited access to data via the platform](/docs/manage-data-access-permissions).

**To find out what data was sent to ad networks via postbacks:**

- Download [postback reports](/docs/raw-data-reporting-overview#postbacks) from the **Reports** > **Raw Data Export** menu

**To control what data you're sending:**

- Use any of the SDK-compliance tools, such as [`setSharingFilterForPartners`](/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data) to block or restrict certain data from being sent.
- Choose to whom you're sending [default postbacks](/docs/set-up-an-integrated-partner#default%20postbacks) and [in-app event postbacks](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration), either to the ad network to which the event is attributed or to all media sources, including organic.

**To control the availability of user-level attribution data for iOS users:**

- Use the [Aggregated Advanced Privacy framework](/docs/apply-aggregated-advanced-privacy-framework) to enforce Apple ATT privacy levels. This ensures that user-level data, although used for attribution, isn't available in AppsFlyer to advertisers or ad networks. Aggregated data is available without limitation.

</Accordion>

<Accordion title="Do I need the SDK if my app is child-directed and all ad networks are blocked?">

The SDK records your app events, such as installs, re-engagements, and in-app events. Without the SDK, there's no attribution. You can [preserve user privacy with the SDK](/docs/additional-sdk-integration-guide#user-privacy) and show just aggregate data.

</Accordion>

### See also

<Cards>
  <Card title="SDK integration overview" href="/docs/sdk-integration-overview" icon="fa-solid fa-code">
    Learn how to integrate the AppsFlyer SDK into your application.
  </Card>
  <Card title="SDK: Privacy preserving methods" href="/docs/apply-privacy-preserving-sdk-methods" icon="fa-solid fa-user-shield">
    Explore methods to preserve user privacy within the SDK.
  </Card>
  <Card title="SDK: User privacy settings" href="/docs/additional-sdk-integration-guide#user-privacy" icon="fa-solid fa-user-shield">
    Configure user privacy settings and compliance controls.
  </Card>
  <Card title="AppsFlyer's privacy measures" href="https://www.appsflyer.com/trust/privacy/" icon="fa-solid fa-user-shield">
    Read about AppsFlyer's commitment to security and privacy.
  </Card>
</Cards>