---
title: Child-directed apps—FAQ
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2023-09-05T19:02:32Z'
  edited_at: '2024-01-18T11:25:52Z'
  id: 18324823209745
  locale: en-us
  section: Manage your apps
  section_id: 6551015977105
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/18324823209745-Child-directed-apps-FAQ
---
> **At a glance:** Get answers to frequently asked questions about apps directed towards children.

<div id="overview" />

## Overview

There are many policies, laws, and regulations on child-directed apps to protect children's privacy. The main ones are [COPPA](https://www.ftc.gov/legal-library/browse/rules/childrens-online-privacy-protection-rule-coppa) and [GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=EN#d1e2029-1-1). In recent years, platforms such as iOS and Android have implemented policies for improved privacy for children. When creating an app, one of the first things to do is determine whether it’s directed to children only or to a mixed audience (both children and adults). Learn from <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">this guide</Anchor> how to implement a compliant attribution solution for apps directed to children.

<div id="adding-a-child-directed-app" />

## Adding a child-directed app

<div id="what-steps-do-i-need-to-take-when-adding-a-childdirected-app" />

<Accordion title="What steps do I need to take when adding a child-directed app?">

1. <Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer">Follow the Add app wizard</Anchor>.
2. For step 2 of the wizard, <Anchor target="_blank" href="/marketers/docs/adding-an-app-to-appsflyer#define-app-audience">see instructions about child-directed apps</Anchor>.
3. After the app is added:
   * Implement the <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#implementing-the-dev-key-in-your-app">Dev key</Anchor> in the SDK
   * Include appropriate <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">privacy controls</Anchor>

 See more details about [implementing compliance tools with ad networks](#implementing-appsflyer-compliance-tools).

</Accordion>

<div id="when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children" />

<Accordion title="When adding a new app, what happens after marking it as directed towards children?">

Two weeks after adding the app, you'll get a notification asking you to confirm you've implemented privacy controls for your child-directed apps. After confirming, you'll get a confirmation message. You can always access the confirmation message from the Notification center or see the confirmation details in the <Anchor target="_blank" href="/marketers/docs/audit-log">Audit log</Anchor>.

</Accordion>

<div id="if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later" />

<Accordion title="Can I change my selection of an app that's directed toward children?">

At this stage, once you select whether an app is directed toward children or not, your selection can't be reversed. This option is only possible while adding the app.

</Accordion>

<div id="how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps" />

<Accordion title="How can I see if someone in my team marked an app as directed toward children?">

Once confirmed that an app is directed toward children, there are two ways you can see the confirmation:

* **Notification center:** From the menu bar, click the notification icon![notificatin center icon.png](https://files.readme.io/5d0b4f1712ba0c05786025adf183e065a2144e1917542ebec0f302688dccb5eb-18473195561489.png) and find the confirmation notification.
* **Audit log:**
  1. From the menu bar, access the user menu (email address drop-down).
  2. Select **Security center.**
  3. In the **Audit log** section, click **View audit log.** You can see the confirmation details under the **My apps** service.

</Accordion>

<div id="implementing-appsflyer-compliance-tools" />

## Implementing AppsFlyer compliance tools

<div id="how-do-i-know-which-tool-to-use" />

<Accordion title="How do I know which tool to use?">

When your app is intended for children or a mixed audience (children and adults), you can use any of the recommended tools from <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">this guide</Anchor> that align with the legal requirements. See more SDK resources at the bottom of this page. 

<div id="examples-of-compliance-tools-and-their-use" />

#### Examples of compliance tools and their use

<table><thead><tr><th>Tool</th><th>iOS</th><th>Android</th><th>Raw data availability</th></tr></thead><tbody><tr><td><span id="strict-sdk"></span><p><a href="./additional-sdk-integration-guide#strictmode-sdk" target="_blank">Strict SDK</a>: </p><p>Ensures that the IDFA isn't sent to AppsFlyer. This is usually recommended for apps directed toward children.</p></td><td><span><span>✓</span></span></td><td>- </td><td>Available only to advertisers</td></tr><tr><td><span id="standard-sdk-using-the-setdisableadvertisingidentifiers-api"></span><p>Standard SDK using the <a href="./android-oaid-implementation-in-the-sdk#opting-out-of-oaid-collection" target="_blank"><kbd>setDisableAdvertisingIdentifiers</kbd> API</a>:</p><p>Ensures that AAID (Google’s Android advertising ID) isn’t sent to AppsFlyer. This is usually recommended for apps directed toward children.</p></td><td>- </td><td><span><span>✓</span></span></td><td>Available only to advertisers</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-specific-ad-networks"></span><p>Standard SDK with an age gate using the <a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank"><kbd>setSharingFilterForPartners</kbd> function</a> for <strong>specific</strong> ad networks: </p><p>Prevents such ad networks from accessing data when users fall below the age gate\*.</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>Limited for specific ad networks</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks"></span><p>Standard SDK with an age gate using the <a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank"><kbd>setSharingFilterForPartners</kbd> function</a> for <strong>all</strong> ad networks:</p><p>Prevents all ad networks from accessing data when users fall below the age gate\*.</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>Available only to advertisers</td></tr><tr><td><span id="skan-only"></span><p><a href="./skadnetwork-skan-solution-guide" target="_blank">SKAN only</a>:</p><p>Ensures the advertising ID isn't shared with other ad networks.</p></td><td><span><span>✓</span></span></td><td>- </td><td>Available only to advertisers</td></tr><tr><td><span id="sdkless-solutions-less-recommended"></span><p>SDK-less solutions (less recommended):</p><p><span>Configure your own servers to send data to AppsFlyer as an alternative to sending data via </span><span>the SDK.</span></p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>According to your configuration</td></tr><tr><td><span id="aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners"></span><p><a href="./apply-aggregated-advanced-privacy-framework" target="_blank">Aggregated Advanced Privacy framework</a>: </p><p>Enforces Apple ATT privacy levels, making sure user-level data is un<span>available </span><span>to advertisers or ad networks.</span></p></td><td><span><span>✓</span></span></td><td>- </td><td>Not available to advertisers or to ad networks</td></tr><tr><td colspan="4"><span id="-when-applying-an-age-gate-block-userlevel-data-that-doesnt-fall-under-the-age-gate-is-available-in-raw-data-reports"></span><p>\* When applying an age gate block, user-level data that doesn't fall under the age gate is available in raw data reports.</p></td></tr></tbody></table>

</Accordion>

<div id="how-does-using-the-tools-in-the-guide-affect-attribution" />

<Accordion title="How does using the tools in the guide affect attribution?">

<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">The AppsFlyer compliance solution guide</Anchor> offers different tools, each with [different levels of control](#how-do-i-know-which-tool-to-use). The impact on attribution varies based on the specific tool you choose to implement.

When using a tool that limits the sending of user data, such as the device ID, other attribution methods are used, such as <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#probabilistic-modeling">probabilistic modeling</Anchor> or <Anchor target="_blank" href="/marketers/docs/appsflyer-attribution-model#install-referrer-android-only">Install referrer (for Android)</Anchor>.

Tools that don’t send user-level data are considered privacy-preserving and enable receiving aggregated campaign data.

</Accordion>

<div id="i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do" />

<Accordion title="I don't know if the ad network I'm working with is compliant, what do I do?">

It's often unclear whether ad networks you collaborate with are compliant with relevant laws. You can refer this question to the ad network. If they aren't compliant or you're unsure, you can avoid sharing with them your data. You can use the **<Anchor target="_blank" href="/marketers/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners` function</Anchor>** to specify which ad networks to block from receiving your app data. You can also use this function to block all ad networks. See more [example compliance tools](#examples-of-compliance-tools-and-their-use).

</Accordion>

<div id="do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant" />

<Accordion title="Do I need to implement AppsFlyer compliance tools if the ad network is compliant?">

AppsFlyer compliance tools must always be implemented. Which ones are appropriate for your needs depends on the audience of your app. You may use  **<Anchor target="_blank" href="/marketers/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners` function</Anchor>** (“MediaSourceName”) if the ad network you're working with has committed to treat the data you've shared with them solely as a data processor for limited purposes allowed under COPPA, GDPR, applicable laws and rules, or other platform rules that require it and with appropriate consent

This applies to each of the ad networks you're working with.

</Accordion>

<div id="what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this" />

<Accordion title="What data am I sharing with ad networks? What control do I have over this?">

Ad networks that aren't <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns">SRNs</Anchor> receive your data via postbacks. They can define which events to include in the postbacks.  Install postbacks are sent by default for attribution, while in-app event postbacks are only sent if you've <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">configured specific events</Anchor> to be sent. As long as postbacks aren't blocked or restricted by the SDK, they may contain user-level data related to app user engagements (installs, in-app events, and re-engagements).

Except for postbacks, ad networks and agencies have <Anchor target="_blank" href="/marketers/docs/manage-data-access-permissions">limited access to data via the platform</Anchor>.

**To find out what data was sent to ad networks via postbacks:**

* Download <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview#postbacks">postback reports</Anchor> from the **Reports** > **Raw Data Export** menu

**To control what data you're sending:**

* Use any of the SDK-compliance tools, such as <Anchor target="_blank" href="/marketers/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners`</Anchor> to block or restrict certain data from being sent.
* Choose to whom you're sending <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#default-postbacks">default postbacks</Anchor> and <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">in-app event postbacks</Anchor>, either to the ad network to which the event is attributed or to all media sources, including organic.

**To control the availability of user-level attribution data for iOS users:**

* Use the <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework">Aggregated Advanced Privacy framework</Anchor> to enforce Apple ATT privacy levels. This ensures that user-level data, although used for attribution, isn't available in AppsFlyer to advertisers or ad networks. Aggregated data is available without limitation.

</Accordion>

<div id="do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked" />

<Accordion title="Do I need the SDK if my app is child-directed and all ad networks are blocked?">

The SDK records your app events, such as installs, re-engagements, and in-app events. Without the SDK, there's no attribution. You can <Anchor target="_blank" href="/marketers/docs/additional-sdk-integration-guide#user-privacy">preserve user privacy with the SDK</Anchor> and show just aggregate data.

</Accordion>

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/sdk-integration-overview">SDK integration overview</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/apply-privacy-preserving-sdk-methods">SDK: Privacy preserving methods</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/additional-sdk-integration-guide#user-privacy">SDK: User privacy settings</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/trust/privacy/">AppsFlyer's privacy measures</Anchor>

<div data-zendesk-anchors="h_01HA20EGWDBSNAFZ7WNXJFFRRV=overview general-questions=adding-a-child-directed-app h_01H9ZK2THJVFYQ49HHRYKZZNEK=adding-a-child-directed-app h_01HHCE11YQX4DKV5BEW6QHKN55=what-steps-do-i-need-to-take-when-adding-a-childdirected-app when-adding-a-new-app-what-happens-after-i%E2%80%99ve-indicated-my-app-is-directed-towards-children=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children h_01H9ZK2THJ225P38Q9CHQSTNY4=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children if-ive-added-an-app-and-didn%E2%80%99t-define-it-as-directed-towards-children-can-i-change-this-later=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01HGZ5VAJHNW2K62ARTK43SG19=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01H9ZK2THJK5Q5EE3K38GTCCT7=how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps implementing-compliance-tools=implementing-appsflyer-compliance-tools h_01HGZ5VAJHNJVM2ENFZ3DEAK42=implementing-appsflyer-compliance-tools h_01HGZ4VWDBZJE8RWM05EJNH0S9=how-do-i-know-which-tool-to-use h_01HHEED2AQTW7G0MJJZDZV2B09=examples-of-compliance-tools-and-their-use standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function%C2%A0for-all-ad-networks=standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks aggregated-advanced-privacy-framework%C2%A0%0Aenforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners=aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners h_01HKHX0GBS9EWMXMY387FQ95X1=how-does-using-the-tools-in-the-guide-affect-attribution h_01HH9EAB8T4Z6RMT8MVS77Q6BP=i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do h_01HKHWSQQKEDZBCDH0P8H760K6=do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant h_01HHEEQ4AAEZSA0YB6V2DSRYXK=what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this h_01HKJ843208PMQF1MCYCWMJC3H=do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked h_01HE7TQV7VDSEX3E7RTKAHBMNN=see-also" />
