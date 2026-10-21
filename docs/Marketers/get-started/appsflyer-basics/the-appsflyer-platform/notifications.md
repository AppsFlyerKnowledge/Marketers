---
title: Notifications
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
  created_at: '2025-03-24T10:10:37Z'
  edited_at: '2026-01-25T14:51:04Z'
  id: 33732395637905
  locale: en-us
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/en-us/articles/33732395637905-Notifications
---
**At a glance:** Manage critical AppsFlyer account notifications from the platform.

You can select to receive notifications from AppsFlyer when certain events occur in your account. In your **notification preferences**, you can opt in or out of receiving these notifications.

## Accessing and configuring notification preferences

### To access notifications

* From the top bar, open the account menu (email address dropdown) > **Notifications.**
* From the bell icon within the platform > **Setting icon.**

### Configuring notifications

To opt in to receive a notification, turn it on from the list of available notifications.

To stop receiving it, turn it off.

Note: Some notifications are available only via email. The Email-only Notification tab contains these [notification](/docs/notifications#email-only-notifications) settings. 

## What notifications can I receive?

The following notification categories are available:

* Account and plan management
* Billing or transactional issues
* Privacy related alerts
* Insights and configurations
* Collaborative features
* AI capabilities

Note: Some notifications are available for email only. More information can be found [here](/docs/notifications#email-notification).

To opt in to a particular notification, it must be:

* **Available in your company's AppsFlyer account.** If a notification is not available in your company's account, the switch to turn it on is not visible.
  * For example, if your company does not subscribe to the AppsFlyer Push API feature, the switch related to this feature is not visible.
* **Available to you, based on your user permissions.** If a notification is related to a capability or feature to which you have not been assigned permissions, the switch to turn it on and off is disabled.
  * For example, if you do not have permission to add or edit integrated partners, the switch to turn on or off a notification related to integrated partner configuration is disabled.

## When will I receive notifications?

If you have opted in to receive a particular notification, you will receive a notification when the trigger event for that notification occurs, but **only when** that trigger event is applicable to **apps and media sources** to which you have permissions.

<div id="example" />

<Accordion title="Example">

Consider the following scenario:

* Your company has 3 apps in AppsFlyer: App A, App B, and App C.
* Each app has active integrations with 2 media sources (integrated partners): Google Ads and TikTok.
* Your AppsFlyer user has permission to:
  * Add or edit integrated partners
  * Access data for App C
  * Access data for Google Ads
* You have opted in to receive a notification when there are changes to integrated partner configurations.

Result:

* You **won't** receive notifications when there are integrated partner configuration changes for Apps A and B.
* You **won't** receive notifications when there are TikTok configuration changes for App C.
* You **will** receive notifications when there are Google Ads configuration changes for App C.

</Accordion>

## Where will I receive notifications?

Notifications can be received via the [bell](/docs/notifications#bell-notification) icon, [email](/docs/notifications#email-notification), or [Slack](/docs/notifications#slack-notification) integration. 

<div id="bell-notification" />

<Accordion title="Bell notification">

The bell icon notification can be found in the top bar to the left of your account menu (email address dropdown).

Clicking on the gear icon takes you to the [notification preferences](/docs/notifications#accessing-and-configuring-notification-preferences).

</Accordion>

<div id="email-notification" />

<Accordion title="Email notification">

Email notifications are sent to the email address associated with your AppsFlyer account.

Some notifications are available only via email. These notification settings can be found in the **Email-only Notification** tab.

> 📘 **Note**
>
> All AppsFlyer notification emails are sent from [notifications@appsflyer.com](mailto:notifications@appsflyer.com)

#### Email-only notifications

The following table lists available **email-only notifications** and the events that trigger them:

| Notification | Trigger event |
| --- | --- |
| Integrated partner configuration changes | <ul><li>A new integrated partner is activated</li><li>An existing integrated partner is deactivated</li><li>A change is made to the settings of an existing integrated partner</li></ul> |
| Push API failures | 5% or more of an app's Push API messages fail within a 12-hour period |
| Audiences connection failures | There are audience partner connection failures that require your attention |
| Ad revenue suspended integrations | An ad revenue integration is suspended after having a warning status for more than 30 days |
| Ad revenue data failure | An ad revenue integration isn't receiving data |
| Integrated partner cost configuration changes | A team member changes cost integration settings |
| SKAN connection failures | There is an issue with your Google Ads or Meta SKAN integration with AppsFlyer that requires your attention. You may need to delete the current integration and log in again. |

</Accordion>

<div id="slack-notification" />

<Accordion title="Slack notification">

**Set up Slack notifications**

To set up Slack notifications, Slack first has to be connected:

1. In the notification preference page, click the **Integrations** button at the top right of the page.
2. Click **Connect** by the Slack notification connector.
3. Review and approve the permissions request.
   1. **If you are the Slack admin**.
      1. In Slack, click on the Slack Workspace.  
         <Image alt="" src="https://a.slack-edge.com/8e8e4/helpcenter/img/workspace-picker@2x.jpg" width="263px" />  
         Note: Make sure the Slack Workspace shown is the correct one you want to connect to.
      2. Go to **Tools & settings** -> **Manage apps**
      3. In the **Admin panel**, select **Requests**.
      4. In the **Needs review** tab, click the three dots next to the AppsFlyer app request.
      5. Click **Approve** and then Approve the following pop-up.
      6. Go back to the **AppsFlyer integration page** and click the **Allow** button.
   2. **If you are not the Slack admin**.
      1. Request permission from your Slack admin to connect Slack to AppsFlyer.
      2. The Slack admin **must** perform all the steps above. In the meantime:
      3. The Slack connector goes into a pending status.
      4. When your Slack admin approves the connection, click **Connect** to start the integration and go from pending to connected.

</Accordion>

<div data-zendesk-anchors="accessing-email-notifications=accessing-and-configuring-notification-preferences h_01HKA254W4XDVNP816N46N59ZV=accessing-and-configuring-notification-preferences h_01JQ66J4YSCSX7ZGG81XHGJ3MM=to-access-notifications h_01HKA254W497H0SKTZ33CVSA4P=configuring-notifications h_01HKA254W47XRG1D3HZ6VBZ2BH=what-notifications-can-i-receive h_01JQ66BX52MV5WQ7RXH6SY3QHK=when-will-i-receive-notifications h_01JQ6EYTZ13FHYERT48K3J25SV=example h_01HKA254W4Z95M335V7KWAJA6N=where-will-i-receive-notifications h_01JQ667RAW19658DVMZNFXNAJK=bell-notification h_01JQ667RAWCAVYBZD3J0T8XH2G=email-notification h_01JJGTDQFM1WE9G3XWSN9S7Z02=note emailonly-notifications=email-only-notifications h_01JQ6EQR8JRBZ2ECJ7SHHWDWFC=email-only-notifications h_01JQ667RAW48YQ64VXW899EW3X=slack-notification" />
