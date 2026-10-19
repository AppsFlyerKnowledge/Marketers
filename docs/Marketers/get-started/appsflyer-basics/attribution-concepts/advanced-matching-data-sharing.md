---
title: Advanced-Matching Data Sharing
excerpt: >-
  Advanced-Matching Data Sharing enables hashed user identifiers, such as email
  and phone number, to be forwarded from AppsFlyer to selected ad networks,
  allowing partners to attribute events to ad engagements without a device ID.
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-06-18T14:23:54Z'
  edited_at: '2026-10-16T08:51:29Z'
  id: 47876839961489
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/47876839961489-Advanced-Matching-Data-Sharing
---
## About Advanced-Matching Data Sharing

As device identifiers become less available, ad networks increasingly rely on first-party data to match ad engagements. Advanced-Matching Data Sharing addresses this gap by forwarding hashed identifiers to supported partners in a privacy-compliant format.

The feature is optional and configured per partner. When enabled on a supported network, AppsFlyer forwards hashed identifiers alongside event data for installs, re-engagements, and in-app events.

All identifiers must be hashed with SHA-256 before reaching AppsFlyer, either on-device via the SDK or server-side via the server-to-server (S2S) API. Plain-text data is never received, stored, or forwarded, and any value that fails validation is dropped at ingestion.

### Supported partners

Advanced-Matching Data Sharing is available for the following networks:

| Partner | Partner ID (PID) | Supported fields |
| --- | --- | --- |
| Bliss Point Media | blisspointmedia\_int | Hashed email |
| Google | googleads\_int | Hashed email, hashed phone number |
| Meta | facebook\_int | Hashed email, hashed phone number, hashed first name, hashed last name |
| Meta | metweb\_int | Hashed email, hashed phone number, hashed first name, hashed last name, Facebook login ID |
| Moloco | moloco\_int | Hashed email, hashed phone number, hashed first name, hashed last name |
| ChatGPT Ads | openai\_int | Hashed email, hashed phone number, hashed first name, hashed last name |
| Pinterest | pinterest\_int | Hashed email, hashed phone number, hashed first name, hashed last name |
| Snapchat | snapchat\_int | Hashed email, hashed phone number |
| Snapchat | snapweb\_int | Hashed email, hashed phone number, hashed first name, hashed last name |
| TikTok | tiktokglobal\_int | Hashed email, hashed phone number, hashed first name, hashed last name |
| TikTok | tiktokweb\_int | Hashed email, hashed phone number, hashed first name, hashed last name |
| Reddit | reddit\_int | Hashed email, hashed phone number |
| Rokt | roktv2\_int | Hashed email, hashed phone number, hashed first name, hashed last name |
| Roku | rokuads\_int | Hashed email, hashed phone number |
| Smadex | smadex\_int | Hashed email, hashed phone number, hashed first name, hashed last name |

## The end-to-end flow

Here's what happens from the moment an identifier is retrieved to the moment it reaches a partner:

1. The app or backend retrieves an identifier (email address, phone number, or other supported type).
2. The AppsFlyer SDK automatically normalizes and hashes the identifier using SHA-256, or the server does so before sending it via the S2S API.
3. The SDK or server sends the hashed identifier to AppsFlyer alongside the event (install, reinstall, re-engagement, or in-app event).
4. If Advanced-Matching Data Sharing is enabled for the partner, AppsFlyer forwards the hash alongside the event payload.
5. The partner uses the hash to match the event to a known user, improving attribution accuracy and match quality.

Hashed identifiers are only forwarded to partners where Advanced-Matching Data Sharing is enabled. When the setting is turned off for a partner, no hashed data is shared with that partner, even if identifiers are present on the event.

## How hashed user identifiers reach AppsFlyer

Hashed identifiers reach AppsFlyer via two methods: the SDK or the S2S API. In both cases, only properly hashed values are accepted. The sections below describe each method.

<div id="send-hashed-identifiers-with-the-sdk" />

<Accordion title="Send hashed identifiers with the SDK">

SDK V7.0.1 introduces methods for passing raw identifiers to the AppsFlyer Android and iOS SDKs. The SDK normalizes and hashes the input before sending it to AppsFlyer.

The SDK performs the following steps in sequence:

1. Normalizes the input according to each partner's requirements.
2. Hashes the normalized value using SHA-256.
3. Sends only the hashed value to AppsFlyer. The raw input never leaves the device.

The SDK rejects invalid values with an error and doesn't send them to AppsFlyer.

Android and iOS support is available starting with SDK V7.0.1.

The following methods are available in the AppsFlyer SDK for passing identifiers:

* `setUserEmail` ([Android](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuseremail), [iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuseremail))
* `setUserFbLoginId` ([Android](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserfbloginid), [iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserfbloginid))
* `setUserFirstName` ([Android](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserfirstname), [iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserfirstname))
* `setUserLastName` ([Android](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserlastname), [iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserlastname))
* `setUserPhone` ([Android](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserphone), [iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserphone))

For implementation details, see the [Android SDK methods](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib) and [iOS SDK methods](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib).

</Accordion>

<div id="send-hashed-identifiers-with-the-s2s-api" />

<Accordion title="Send hashed identifiers with the S2S API">

When sending events via the S2S in-app events API, identifiers must be normalized and hashed on the server before submission. The API accepts the following fields:

| Field | Description |
| --- | --- |
| `email_hashed` | Hashed email address |
| `phone_number_hashed` | Hashed phone number, digits only |
| `phone_number_e164_hashed` | Hashed phone number in E.164 format |
| `first_name_hashed` | Hashed first name |
| `last_name_hashed` | Hashed last name |
| `fb_login_id` | Facebook login ID (not hashed; passed as-is) |

Every field in this table (except `fb_login_id`) is validated against the SHA-256 format. AppsFlyer silently drops values that don't match and doesn't forward them to any partner. It processes the other fields in the event normally.

</Accordion>

### Why are there two phone number fields?

Networks match events by comparing the hash that AppsFlyer forwards to their own stored hash of the user's phone number. Because the same number normalized in a different format produces a different hash, both sides must hash from the same format to get a match. Because networks normalize phone numbers differently and AppsFlyer receives already-hashed values, both versions must be sent to cover all supported partners.

* `phone_number_hashed`: for Meta and Snapchat. Normalization format before hashing: `16501234567`
* `phone_number_e164_hashed`: for Google and TikTok. Normalization format before hashing: `+16501234567`

## Normalize and hash identifiers

Normalize the raw value exactly as described below, then hash using SHA-256 and send the lowercase hex digest.

<div id="email-emailhashed" />

<Accordion title="Email (email_hashed)">

Normalize and hash the email address as follows:

1. Remove all whitespace.
2. Convert to lowercase.
3. Hash with SHA-256.

**Example:**

`User@Example.COM` → `user@example.com` → SHA-256 hash

</Accordion>

<div id="phone-number-digits-only-phonenumberhashed" />

<Accordion title="Phone number, digits only (phone_number_hashed)">

Use this for Meta, Reddit, Pinterest, and Snapchat. Normalize and hash the phone number as follows:

1. Prepend the country code.
2. Remove all symbols, letters, and leading zeros.
3. Hash with SHA-256.

**Example:**

`+1 (650) 123-4567` → `16501234567` → SHA-256 hash

</Accordion>

<div id="phone-number-e164-phonenumbere164hashed" />

<Accordion title="Phone number, E.164 (phone_number_e164_hashed)">

Use this for Google, TikTok, and Roku. Normalize and hash the phone number as follows:

1. Prepend the country code.
2. Remove all symbols, letters, and leading zeros.
3. Prepend a `+` sign.
4. Hash with SHA-256.

**Example:**

`+1 (650) 123-4567` → `+16501234567` → SHA-256 hash

</Accordion>

<div id="first-name-firstnamehashed-and-last-name-lastnamehashed" />

<Accordion title="First name (first_name_hashed) and last name (last_name_hashed)">

Normalize and hash the name as follows:

1. Remove all whitespace.
2. Convert to lowercase.
3. Hash with SHA-256.

</Accordion>

<div id="facebook-login-id-fbloginid" />

<Accordion title="Facebook login ID (fb_login_id)">

Send the raw Facebook login ID as provided by the Facebook Login SDK. This field is not hashed.

</Accordion>

## Turn on Advanced-Matching Data Sharing

Advanced-Matching Data Sharing is controlled per partner and per app and must be explicitly enabled for each network.

**To turn on Advanced-Matching Data Sharing:**

1. In AppsFlyer, from the side menu, select **Collaborate > Active Integrations**.
2. Search for the partner and select it.
3. Turn on **Advanced-Matching Data Sharing**.
4. Click **Save integration**.

When Advanced-Matching Data Sharing is turned on, any event that includes one or more supported identifier fields will have those fields forwarded to the partner.

Turning off Advanced-Matching Data Sharing immediately stops hashed data sharing with that partner. Other integration settings, including postbacks and event data, are not affected.

## Privacy and data handling

When Advanced-Matching Data Sharing is enabled for a partner, AppsFlyer begins forwarding hashed user identifiers to that network along with event data. Before turning it on, confirm the following:

* A lawful basis exists (under applicable privacy laws, such as the General Data Protection Regulation (GDPR) or the California Consumer Privacy Act (CCPA)) to share this data with the partner.
* You've updated your privacy policy and, where required, obtained user consent.
* Your data-sharing practices align with the partner's terms.

AppsFlyer does not process or store plain-text Personally Identifiable Information (PII). All identifier fields are validated at ingestion: values that don't conform to the SHA-256 format are dropped and never forwarded to any partner.

## FAQ

<div id="is-advancedmatching-data-sharing-the-same-as-the-audiences-hashed-email-and-phone-feature" />

<Accordion title="Is Advanced-Matching Data Sharing the same as the Audiences' hashed email and phone feature?">

No. These are separate mechanisms. Audiences build user lists for ad targeting. Advanced-Matching Data Sharing forwards hashed identifiers with individual events to improve match rates at the partner level. AppsFlyer plans to consolidate both methods, using the new data retrieval method for both Advanced-Matching Data Sharing and Audiences.

</Accordion>

<div id="what-happens-if-i-send-an-invalid-hash-value" />

<Accordion title="What happens if I send an invalid hash value?">

AppsFlyer drops the field at ingestion and doesn't forward it to any partner. It processes the other fields in the event normally.

</Accordion>

<div id="do-i-need-to-send-all-supported-fields" />

<Accordion title="Do I need to send all supported fields?">

No. Only the identifiers available and relevant to the configured partners need to be included. Missing fields are not forwarded.

</Accordion>

<div id="will-advancedmatching-data-sharing-improve-install-attribution" />

<Accordion title="Will Advanced-Matching Data Sharing improve install attribution?">

Most partners don't use hashed email or hashed phone for install, re-engagement, or reinstall matching. Sending these fields mostly helps partners better match in-app events on their end. It doesn't affect AppsFlyer attribution.

</Accordion>

<div id="does-appsflyer-ever-receive-plaintext-user-identifiers" />

<Accordion title="Does AppsFlyer ever receive plain-text user identifiers?">

No. Identifiers are always hashed before they reach AppsFlyer, whether on-device via the SDK or server-side via the S2S API. AppsFlyer only accepts hashed values.

</Accordion>

<div data-zendesk-anchors="about-advancedmatching-data-sharing=about-advanced-matching-data-sharing h_01KVFJHWK1TYAPPMZDYFAP0RX0=about-advanced-matching-data-sharing h_01KVFJHWK1VTJZH53FKNE8NZ59=supported-partners the-endtoend-flow=the-end-to-end-flow h_01KVFJHWK1JQ7J838YNDTYDD4A=the-end-to-end-flow h_01KVFJHWK197KW8YBQ1NBD9XT1=how-hashed-user-identifiers-reach-appsflyer h_01M4ZE5P7QWCWP3FMXPM572R3R=send-hashed-identifiers-with-the-sdk h_01M4ZE5P7Q6W3G4JPQKRSSWSX6=send-hashed-identifiers-with-the-s2s-api h_why-two-phone-fields=why-are-there-two-phone-number-fields h_01KVFJHWK16KQ1X1WFTTTFFND3=normalize-and-hash-identifiers h_01M4ZE5P7Q0NJXDVM5MP0S2SKC=email-emailhashed h_01M4ZE5P7QDR4PVS9XZ68J6KW5=phone-number-digits-only-phonenumberhashed h_01M4ZE5P7Q2Z4APXNAWVJ8FES9=phone-number-e164-phonenumbere164hashed h_01M4ZE5P7Q98VNS456PMVXQQXC=first-name-firstnamehashed-and-last-name-lastnamehashed h_01M4ZE5P7QEXVV2EPX3Q550586=facebook-login-id-fbloginid turn-on-advancedmatching-data-sharing=turn-on-advanced-matching-data-sharing h_01KVFJHWK27C5FA358M526EJED=turn-on-advanced-matching-data-sharing h_01KVFJHWK2BN2T7BTXANAWAX4B=privacy-and-data-handling h_01KVFJHWK2XB5VF8V2KPG62QYV=faq h_01M4ZE5P7Q0NE2H8D3N7AX5301=is-advancedmatching-data-sharing-the-same-as-the-audiences-hashed-email-and-phone-feature h_01M4ZE5P7QCKZYS7399QED62F5=what-happens-if-i-send-an-invalid-hash-value h_01M4ZE5P7QT2SG5DBKZ3GTTZ8S=do-i-need-to-send-all-supported-fields h_01M4ZE5P7QZQJA45VV4XV00VAD=will-advancedmatching-data-sharing-improve-install-attribution h_01M4ZE5P7QVF3HQ2Q8HKAB7W98=does-appsflyer-ever-receive-plaintext-user-identifiers" />
