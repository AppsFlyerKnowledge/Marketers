---
title: IDFV attribution and test-device registration
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-08-15T13:44:35Z'
  edited_at: '2026-08-12T11:20:39Z'
  id: 17798709514001
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/17798709514001-IDFV-attribution-and-test-device-registration
---
> **At a glance:** IDFV is a unique identifier assigned by iOS to apps of the same vendor. You can use it to attribute installs that originated in cross-promotion campaigns and register test devices.

IDFV (Identifier for Vendor) is a unique identifier iOS generates while installing the first app the vendor owns. When another vendor app is installed on the same device, it is assigned the same IDFV. If all the vendor apps are deleted from the device, the IDFV is deleted, too, and a different one is generated when the vendor apps are installed again.

According to Apple: "The ID for Vendors (IDFV) may be used for analytics across apps from the same content provider. In this case, the use of the [ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) framework is not required. The IDFV may not be combined with other data to track a user across apps and websites owned by other companies. You remain fully responsible to ensure that your collection and use of the IDFV complies with applicable law."

IDFV has the following uses in AppsFlyer:

* [Cross-promotion attribution](/docs/idfv-attribution-and-test-device-registration#idfv-in-cross-promotion-attribution)
* [Test device registration](/docs/idfv-attribution-and-test-device-registration#idfv-for-test-device-registration)

<div id="idfv-in-cross-promotion-attribution" />

## IDFV in cross-promotion attribution

IDFV can be used for matching in a cross-promotion attribution scenario. In this scenario, the user is served an ad within an app your company owns. The ad is promoting another app also owned by your company.

<div id="how-does-crosspromotion-attribution-using-idfv-work" />

<Accordion title="How does cross-promotion attribution using IDFV work?">

1. An ad for the promoted app is displayed within one of the vendor's apps. The same vendor also owns the promoted app.
2. Upon clicking or viewing the advertisement, the SDK notifies AppsFlyer about the corresponding click or impression event. The SDK associates the **promoting** app's IDFV with the event (The SDK automatically collected the IDFV when the promoting app was initially launched).
3. After the promoted app is installed and opened, the SDK notifies AppsFlyer about the installation event. This event includes the IDFV of the **promoted** app.
4. Upon receiving the installation event, AppsFlyer attempts to match it with the corresponding click or impression engagement. If both events share the same IDFV, the install event is attributed to the cross-promotion campaign.

</Accordion>

<div id="a-few-examples-of-idfv-attribution" />

<Accordion title="A few examples of IDFV cross-promotion attribution">

IDFV matching is employed for cross-promotion attribution in the following scenarios:

* **Owned E-mail and SMS campaigns:** An email or SMS message is sent to users of other apps owned by the same vendor as the promoted app. This message includes an attribution link that carries the IDFV collected from the install event of the original vendor app. AppsFlyer then matches this IDFV to the IDFV assigned to the install event of the promoted app.
* **Push notifications campaigns:** A Push notification triggered by the SDK of an app owned by the same vendor as the promoted app contains an attribution link embedded with the IDFV. AppsFlyer matches the IDFV on the push notification to the IDFV associated with the install event of the promoted app.

</Accordion>

<div id="idfv-for-test-device-registration" />

## IDFV for test device registration

Advertisers conduct tests during the AppsFlyer onboarding process to verify their app can successfully record and send install events. The IDFV serves as a unique identifier that allows AppsFlyer to recognize the devices used for testing.

<div id="why-identify-devices-as-test-devices" />

<Accordion title="Why identify devices as test devices?">

AppsFlyer treats install events that originate from test devices differently to accommodate multiple installations of the same app. This is often necessary for integration testing purposes. To enable AppsFlyer to recognize these events as coming from test devices, the test device IDFV is registered on the **Test Device** page accessible through the **User Account** menu.

</Accordion>

<div id="why-use-idfv-as-an-identifier-in-test-device-registration" />

<Accordion title="Why use IDFV as an identifier in test device registration?">

Test device registration can also be done with IDFA. However, an iOS app does not have access to the IDFA when the app does not implement App Tracking Transparency (ATT) or when the user does not consent to share personal data. In these cases, we can use IDFV access to identify the test device because it is not dependent on ATT.

</Accordion>

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/cross-promotion-attribution-for-marketers">Cross-promotion attribution for marketers</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/registering-test-devices#how-to-register-your-device-with-idfv">How to register your test device with IDFV</Anchor>

<div data-zendesk-anchors="idfv-in-crosspromotion-attribution=idfv-in-cross-promotion-attribution h_01H9041HQ7H18541W83A72B85B=idfv-in-cross-promotion-attribution h_01H9041HQ7JE11FTWTD0XYQWRS=how-does-crosspromotion-attribution-using-idfv-work a-few-examples-of-idfv-attribution%E2%80%A6=a-few-examples-of-idfv-attribution h_01H9041HQ7YDCTJQYBYDVJZPW0=a-few-examples-of-idfv-attribution h_01H9041HQ8ZC679PX7HWRMG1YC=idfv-for-test-device-registration h_01H9041HQ8K76JD72VR4EXCEZB=why-identify-devices-as-test-devices h_01H9041HQ8WS1GEAY6RGV10PF5=why-use-idfv-as-an-identifier-in-test-device-registration h_01HG809S72YC5W61GGN0CE6TP1=see-also" />
