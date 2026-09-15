---
title: "Customer User ID field (CUID)"
excerpt: "Learn how the Customer User ID (CUID) enables you to group and analyze user events across different devices, media sources, and channels."
---
The CUID enables you to group events of the same user across different devices, media sources, or channels.

## What is CUID?

The Customer User ID (CUID) is a unique user identifier. The app owner usually generates and sets it at the time of user registration. The CUID lets app owners follow user journeys across different devices.

#### Example

A user with two or more devices has the same CUID across apps. Each time the user performs an event on a mobile or desktop device, the SDK captures the event along with the CUID. This enables the advertiser to combine the devices' data into a holistic user view.

A few use cases:

- In-app purchases made by the same user in the same app across multiple devices (phone, tablet, TV, desktop) can be combined into a single view.
- You can share user performance data across multiple platforms (desktop, mobile, TV) to achieve a holistic user experience.

## Setting the CUID

It's recommended to set the CUID as early as possible in the SDK initialization flow so that as many events as possible can be associated with a CUID.

<Tabs>
<Tab title="Android native">

Once the CUID is available, you can set it by calling `setCustomerUserID`. You can only associate the CUID with in-app events occurring after you set it. Therefore, the install event will not carry the CUID when you call `start` before `setCustomerUserID`.

### Associate the CUID with the install event

If you need to associate the install event to the CUID, we recommend setting it before calling `start`.

> ❗️ Important
>
> Remember that setting the CUID before `start` may block the SDK from sending the install event and thus prevent the attribution from happening. This can occur, for example, when the user launches the application for the first time and then exits before the SDK can set the CUID.

In Android, you can run the `start` method and CUID setup from either the global `Application` class or an `Activity` class, depending on the app implementation. For more information, see [Select in what class to start the SDK](/docs/basic-sdk-integration-guide#select-in-what-class-to-start-the-sdk).

#### If the SDK starts in the Application class

If you want to associate the CUID with the install event when starting from the global `Application` class, make sure to delay sending out the install event using the `waitForCustomerUserId` method. This method puts the SDK in waiting mode until the CUID is set.

Note: If, for some reason, setting the CUID fails, the SDK will remain in waiting mode and will not send any events.

#### If the SDK starts in an Activity class

If you want to associate the CUID with the install event when starting from an `Activity` class, you don't have to delay sending the install event. Simply call `setCustomerUserId` before calling `start`.

#### Developer instructions

Tell the developer the following:

- Use `waitForCustomerUserId` if the SDK starts in the global `Application` class
- Developer links:
  - If you want to associate the CUID with the install event, see [here](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#associate-the-cuid-with-the-install-event).

</Tab>
<Tab title="iOS native">

Use the `customerUserId` method to set the CUID. The location of `customerUserId` in relation to the `start` method determines which events you can associate with the CUID.

- If you call `customerUserId` before calling `start`, the SDK associates the CUID with the install and the following in-app events
- If you call it after `start`, the SDK only associates the CUID with events recorded after you set it.

#### Developer instructions

Refer your developer to [Setting the Customer User ID](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#setting-the-customer-user-id) in the Dev Hub.

</Tab>
<Tab title="Unity">

#### Developer instructions

Refer your developer to [Setting the Customer User ID](https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id) in the Dev Hub.

</Tab>
<Tab title="React Native">

#### Developer instructions

Refer your developer to [setCustomerUserId](https://dev.appsflyer.com/hc/docs/rn_api#setcustomeruserid) API reference in the Dev Hub.

</Tab>
<Tab title="Web">

For the full implementation walkthrough, see [Set customer user ID](/docs/integrate-appsflyer-web-sdk#h_01KGJCGCQ0RNBW7V5T4PXVXQW1) in Integrate AppsFlyer Web SDK.

</Tab>
</Tabs>

## CUID and privacy

AppsFlyer values and respects the privacy of your users and [doesn't permit the collection or transfer of sensitive personal data to the AppsFlyer platform.](https://www.appsflyer.com/services-privacy-policy/#engagementinformation)

To protect your users' privacy, you must not design the CUID to contain information that directly identifies the user. This includes social security or national identification numbers.

If the CUID contains a user's email address or phone number, you must hash it before sending it to AppsFlyer. Never send unhashed CUIDs containing personal data to AppsFlyer.

<Cards>
  <Card title="User journey reports" href="https://support.appsflyer.com/hc/articles/209680773#user-journey-reports">
    Learn more about the CUID in raw data reports.
  </Card>
  <Card title="Google best practices to avoid sending PII" href="https://support.google.com/analytics/answer/6366371?hl=en">
    Review Google's guidelines on avoiding the transmission of Personally Identifiable Information.
  </Card>
</Cards>