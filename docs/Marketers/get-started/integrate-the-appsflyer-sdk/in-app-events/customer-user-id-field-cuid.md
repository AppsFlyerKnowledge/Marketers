---
title: Customer User ID field (CUID)
metadata:
  keywords:
    - ID
    - Customer User ID
    - User
    - Mixpanel
    - Swrve
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-11-18T11:55:22Z'
  edited_at: '2026-09-10T17:02:50Z'
  id: 207032016
  locale: en-us
  section: In-app events
  section_id: 6551285343761
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207032016-Customer-User-ID-field-CUID
---
> **At a glance:** The CUID enables you to group events of the same user across different devices, media sources, or channels.

<div id="what-is-cuid" />

## What is CUID?

The Customer User ID (CUID) is a unique user identifier. The app owner usually generates and sets it at the time of user registration. The CUID lets app owners follow user journeys across different devices.

<div id="example" />

> 📘 **Example**
>
> A user with two or more devices has the same CUID across apps. Each time the user performs an event on a mobile or desktop device, the SDK captures the event along with the CUID. This enables the advertiser to combine the devices' data into a holistic user view.
>
> A few use cases:
>
> * In-app purchases made by the same user in the same app across multiple devices (phone, tablet, TV, desktop) can be combined into a single view.
> * You can share user performance data across multiple platforms (desktop, mobile, TV) to achieve a holistic user experience.

<div id="setting-the-cuid" />

## Setting the CUID

It's recommended to set the CUID as early as possible in the SDK initialization flow so that as many events as possible can be associated with a CUID.

<Tabs>
<Tab title="Android native">

Once the CUID is available, you can set it by calling `setCustomerUserID`. You can only associate the CUID with in-app events occurring after you set it. Therefore, the install event will not carry the CUID when you call `start` before `setCustomerUserID`.

<div id="associate-the-cuid-with-the-install-event" />

### Associate the CUID with the install event

If you need to associate the install event to the CUID, we recommend setting it before calling `start`.

**Important:** Remember that setting the CUID before `start` may block the SDK from sending the install event and thus prevent the attribution from happening. This can occur, for example, when the user launches the application for the first time and then exits before the SDK can set the CUID.

In Android, you can run the `start` method and CUID setup from either the global `Application` class or an `Activity` class, depending on the app implementation. For more information, see <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#select-in-what-class-to-start-the-sdk">Select in what class to start the SDK</Anchor>.

<div id="if-the-sdk-starts-in-the-application-class" />

#### If the SDK starts in the Application class

If you want to associate the CUID with the install event when starting from the global `Application`class, make sure to delay sending out the install event using the `waitForCustomerUserId` method. This method puts the SDK in waiting mode until the CUID is set.

Note: If, for some reason, setting the CUID fails, the SDK will remain in waiting mode and will not send any events.

<div id="if-the-sdk-starts-in-an-activity-class" />

#### If the SDK starts in an Activity class

If you want to associate the CUID with the install event when starting from an `Activity` class, you don't have to delay sending the install event. Simply call `setCustomerUserId` before calling `start`.

<div id="developer-instructions" />

#### Developer instructions

Tell the developer the following:

* Use `waitForCustomerUserId` if the SDK starts in the global `Application` class
* Developer links:
  * If you want to associate the CUID with the install event, see <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-android-sdk#associate-the-cuid-with-the-install-event">here</Anchor>.

</Tab>

<Tab title="iOS native">

Use the `customerUserId` method to set the CUID. The location of `customerUserId`  in relation to the `start` method determines which events you can associate with the CUID.

* If you call `customerUserId` before calling `start`, the SDK associates the CUID with the install and the following in-app events
* If you call it after `start`, the SDK only associates the CUID with events recorded after you set it.

<div id="developer-instructions-1" />

#### Developer instructions

Refer your developer to <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#setting-the-customer-user-id">Setting the Customer User ID</Anchor> in the Dev Hub.

</Tab>

<Tab title="Unity">

<div id="developer-instructions-2" />

#### Developer instructions

Refer your developer to <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id">Setting the Customer User ID</Anchor> in the Dev Hub.

</Tab>

<Tab title="React Native">

<div id="developer-instructions-3" />

#### Developer instructions

Refer your developer to <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcustomeruserid">setCustomerUserId</Anchor> API reference in the Dev Hub.

</Tab>

<Tab title="Web">

For the full implementation walkthrough, see <Anchor target="_blank" href="/marketers/docs/integrate-appsflyer-web-sdk#6-set-customer-user-id">Set customer user ID</Anchor> in Integrate AppsFlyer Web SDK.

</Tab>
</Tabs>

<div id="cuid-and-privacy" />

## CUID and privacy

AppsFlyer values and respects the privacy of your users and <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">doesn't permit the collection or transfer of sensitive personal data to the AppsFlyer platform.</Anchor>

To protect your users' privacy, you must not design the CUID to contain information that directly identifies the user. This includes social security or national identification numbers.

If the CUID contains a user's email address or phone number, you must hash it before sending it to AppsFlyer. Never send unhashed CUIDs containing personal data to AppsFlyer.

<div id="see-also" />

> 📘 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview#user-journey-reports">User journey reports</Anchor> (for more about the CUID in raw data reports)
> * <Anchor target="_blank" href="https://support.google.com/analytics/answer/6366371?hl=en">Google best practices to avoid sending PII</Anchor>

<div data-zendesk-anchors="h_01HAJ00DVHRSDBS4FFKM16JFER=what-is-cuid h_01HAJ00DVHZ8V8MRAXN2W3T8DS=example h_01HAJ00DVHDGM133A72HD5JXER=setting-the-cuid h_01HAJ00DVHDE9V2MT6JQF8SAH3=associate-the-cuid-with-the-install-event h_01HAJ00DVH746B6YJVF70PMZJ8=if-the-sdk-starts-in-the-application-class h_01HAJ00DVHYZBER40RJH0GM8KF=if-the-sdk-starts-in-an-activity-class developer-instructions-android=developer-instructions h_01HAJ00DVHZBZCRA1VGYJY44VY=developer-instructions developer-instructions::31dbab4b=developer-instructions h_01HAJ00DVH2RV902D6G224A4QY=developer-instructions developer-instructions-unity=developer-instructions h_01HCT1MKQWSJZ9MQTA9B1GJFWQ=developer-instructions developer-instructions-react=developer-instructions h_01M25Y3EFC7BJAYE9YEJYA4S5A=developer-instructions h_01HAJ00DVH4987JGZZVDA1NB29=cuid-and-privacy h_01HE7RXTEPQAWV03276TDEPG0V=see-also" />
