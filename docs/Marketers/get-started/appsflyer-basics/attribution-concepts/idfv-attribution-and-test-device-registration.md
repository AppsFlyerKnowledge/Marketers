---
title: "IDFV attribution and test-device registration"
excerpt: "Learn how IDFV (Identifier for Vendor) is used in AppsFlyer for cross-promotion attribution and registering iOS test devices."
---
IDFV is a unique identifier assigned by iOS to apps of the same vendor. You can use it to attribute installs that originated in cross-promotion campaigns and register test devices.

IDFV (Identifier for Vendor) is a unique identifier iOS generates while installing the first app the vendor owns. When another vendor app is installed on the same device, it is assigned the same IDFV. If all the vendor apps are deleted from the device, the IDFV is deleted, too, and a different one is generated when the vendor apps are installed again.

According to Apple: "The ID for Vendors (IDFV) may be used for analytics across apps from the same content provider. In this case, the use of the [ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) framework is not required. The IDFV may not be combined with other data to track a user across apps and websites owned by other companies. You remain fully responsible to ensure that your collection and use of the IDFV complies with applicable law."

IDFV has the following uses in AppsFlyer:

- [Cross-promotion attribution](#idfv-in-cross-promotion-attribution)
- [Test device registration](#idfv-for-test-device-registration)

## IDFV in cross-promotion attribution

IDFV can be used for matching in a cross-promotion attribution scenario. In this scenario, the user is served an ad within an app your company owns. The ad is promoting another app also owned by your company.

### How does cross-promotion attribution using IDFV work?

1. An ad for the promoted app is displayed within one of the vendor's apps. The same vendor also owns the promoted app.
2. Upon clicking or viewing the advertisement, the SDK notifies AppsFlyer about the corresponding click or impression event. The SDK associates the **promoting** app's IDFV with the event (The SDK automatically collected the IDFV when the promoting app was initially launched).
3. After the promoted app is installed and opened, the SDK notifies AppsFlyer about the installation event. This event includes the IDFV of the **promoted** app.
4. Upon receiving the installation event, AppsFlyer attempts to match it with the corresponding click or impression engagement. If both events share the same IDFV, the install event is attributed to the cross-promotion campaign.

### A few examples of IDFV cross-promotion attribution

IDFV matching is employed for cross-promotion attribution in the following scenarios:

- **Owned E-mail and SMS campaigns:** An email or SMS message is sent to users of other apps owned by the same vendor as the promoted app. This message includes an attribution link that carries the IDFV collected from the install event of the original vendor app. AppsFlyer then matches this IDFV to the IDFV assigned to the install event of the promoted app.
- **Push notifications campaigns:** A Push notification triggered by the SDK of an app owned by the same vendor as the promoted app contains an attribution link embedded with the IDFV. AppsFlyer matches the IDFV on the push notification to the IDFV associated with the install event of the promoted app.

## IDFV for test device registration

Advertisers conduct tests during the AppsFlyer onboarding process to verify their app can successfully record and send install events. The IDFV serves as a unique identifier that allows AppsFlyer to recognize the devices used for testing.

### Why identify devices as test devices?

AppsFlyer treats install events that originate from test devices differently to accommodate multiple installations of the same app. This is often necessary for integration testing purposes. To enable AppsFlyer to recognize these events as coming from test devices, the test device IDFV is registered on the **Test Device** page accessible through the **User Account** menu.

### Why use IDFV as an identifier in test device registration?

Test device registration can also be done with IDFA. However, an iOS app does not have access to the IDFA when the app does not implement App Tracking Transparency (ATT) or when the user does not consent to share personal data. In these cases, we can use IDFV access to identify the test device because it is not dependent on ATT.

<Cards>
  <Card title="Cross-promotion attribution for marketers" href="https://support.appsflyer.com/hc/articles/115004481946">
    Learn how to set up and measure cross-promotion campaigns.
  </Card>
  <Card title="How to register your test device with IDFV" href="https://support.appsflyer.com/hc/articles/207031996#how-to-register-your-device-with-idfv">
    Step-by-step instructions on registering iOS devices for testing.
  </Card>
</Cards>