---
title: Audiences - Configure additional identifiers for partner audience creation
metadata:
  keywords:
    - Audiences
    - Advertisers
    - Developers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-02-14T16:23:45Z'
  edited_at: '2026-08-14T00:01:08Z'
  id: 360017807278
  locale: en-us
  section: Audiences
  section_id: 6551336428945
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360017807278-Audiences-Configure-additional-identifiers-for-partner-audience-creation
---
> **At a glance:** Configure additional user identifiers for sending custom audiences to advertising partners.

## About additional identifiers

AppsFlyer Audiences automatically supports the following device identifiers for sending custom audiences to <Anchor target="_blank" href="/marketers/docs/audiences-partner-connections">advertising partners</Anchor>:

* **iOS:** IDFA
* **Android (Google Play):** GAID
* **Android (3rd-party app stores):** <Anchor target="_blank" href="/marketers/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor> and IMEI

Some advertising partners also support custom audience matching based on additional user identifiers. Audiences offers you the option to use these identifiers if you specifically configure them through the AppsFlyer SDK or S2S-mobile API.

Such additional identifiers can include phone numbers and emails, but can **only be used if encrypted with SHA256 hashing**.  Your use of such additional identifiers is subject to the [Additional Identifiers Terms of Use](https://support.appsflyer.com/hc/article_attachments/16567368205201).

## Next steps

1. Select the additional identifiers you want to use (if any) from the [table of available identifiers](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting). Note that not all advertising partners support all identifiers.
2. Developers—Configure the selected identifiers, using:
   * Parameters and formatting requirements as appear in the [table of available identifiers](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)
   * The reference and code samples for [SDK](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#sdk-reference-and-code-samples) and [S2S](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#s2s-reference-and-code-samples)
3. In the Audiences dashboard:
   * Set your <Anchor target="_blank" href="/marketers/docs/audiences-user-identifier-policy">account-level user identifier policy</Anchor>
   * Select the identifiers to be uploaded in each of your <Anchor target="_blank" href="/marketers/docs/audiences-guide#manage-connections">partner connections</Anchor>

## Available identifiers

You can elect to configure one or more identifiers, shown in the table below.

<Accordion title="Additional identifiers — parameters and formatting">

<table><tbody><tr><td>Identifier</td><td>Parameter name</td><td>Format</td><td>Example value (before hashing)</td></tr><tr><td>Email address</td><td>email_sha256</td><td><p><strong>SDK v7.0.0 and earlier:</strong></p><ul><li>Lowercase</li><li>No white spaces</li><li>Client-hashed (SHA256) before passing in</li></ul><p><strong>SDK v7.0.1 and later:</strong> Plain text. The SDK normalizes and hashes it automatically.</p></td><td>name@domain.com</td></tr><tr><td>Phone number<br/>(see note below)</td><td><p><strong>v7.0.0 and earlier (or S2S):</strong> phone_number_sha256</p><p><strong>v7.0.1 and later:</strong> phone_number_hashed</p></td><td><p><strong>v7.0.0 and earlier (or S2S):</strong></p><ul><li>No symbols, letters, or leading zeroes</li><li>Include country code</li><li>SHA256 hashed</li></ul><p><strong>v7.0.1 and later:</strong> Plain text. The SDK concatenates the country code and number, normalizes, and hashes it automatically.</p></td><td>442070313000</td></tr><tr><td><p>Phone number E164</p><p>(see note below)</p></td><td><p><strong>v7.0.0 and earlier (or S2S):</strong> phone_number_e164_sha256</p><p><strong>v7.0.1 and later:</strong> phone_number_e164_hashed</p></td><td><p><strong>v7.0.0 and earlier (or S2S):</strong></p><ul><li>E164 phone number</li><li>SHA256 hashed</li></ul><p><strong>v7.0.1 and later:</strong> Plain text. The SDK concatenates the country code and number, normalizes, and hashes it automatically.</p></td><td>+442070313000</td></tr><tr><td colspan="4"><p><br /><br />**Note**<br /></p><p><strong><span id="h_01HNZNWZ9XSY47T58Z5YR7Q65S"></span>Note</strong></p><p>Different advertising partners support different phone number formats. So, if you choose to use phone number, configure both identifiers: <em>Phone number</em> and <em>Phone number E164.</em></p></td></tr></tbody></table>

</Accordion>

## SDK reference and code samples

When sending identifiers for Audiences via the SDK:

* For identifiers other than hashed *Email address* or *Phone number*, use `setAdditionalData`.
* For hashed *Email address*:
  * SDK v7.0.1 and later: use `setUserEmail`.
  * SDK v7.0.0 and earlier: use `setUserEmails`.
* For hashed *Phone number*:
  * SDK v7.0.1 and later: use `setUserPhone` (recommended).
  * SDK v7.0.0 and earlier: use `setAdditionalData` with custom data.

> 📘 **Note**
>
> Keep the following version-dependent changes in mind:
>
> * **Email:** As of SDK v7.0.1, setUserEmails (iOS/Android) has been fully removed and replaced by setUserEmail. This is a breaking change, not a deprecation. Apps on v7.0.0 and earlier must keep using setUserEmails. Apps on v7.0.1 and later must switch to setUserEmail. Check your integrated SDK version before choosing which sample to follow.
> * **Phone:** As of SDK v7.0.1, a dedicated setUserPhone API is available. It's the recommended way to send phone number identifiers for Advanced Matching. This isn't a breaking change: setAdditionalData still works. For new integrations, and for customers who upgrade to v7.0.1 and later, we recommend migrating to setUserPhone. Apps on v7.0.0 and earlier must continue using setAdditionalData, because setUserPhone doesn't exist in those SDK versions.

## iOS SDK configuration

To set hashed *Phone number* as an additional user identifier:

### **SDK v7.0.0 and earlier — setAdditionalData**

<Tabs>
<Tab title="Objective-C">

```objectivec
NSDictionary *customData = @{
  @"audiences": @{
    @"phone_number_sha256": @"6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37",
    @"phone_number_e164_sha256":@"F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E"
  }
};
[[AppsFlyerLib shared] setAdditionalData:customData];
```

</Tab>

<Tab title="Swift">

```swift
let customData: Dictionary = [
  "audiences" : [
    "phone_number_sha256":"6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37",
    "phone_number_e164_sha256":"F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E"
  ]
] 
AppsFlyerLib.shared().customData = customData
```

</Tab>
</Tabs>

> 📘 **Note**
>
> You must pre-hash both values (SHA-256) before passing them in.

### **SDK v7.0.1 and later — setUserPhone (recommended)**

#### Method signature

```objectivec
- (void) setUserPhone:(NSString *_Nonnull) countryCode
phoneNumber:(NSString *_Nonnull) phoneNumber;
```

#### Usage example

<Tabs>
<Tab title="Objective-C">

```objectivec
[[AppsFlyerLib shared] setUserPhone:@"1" phoneNumber:@"(650) 555-1212"];
```

</Tab>

<Tab title="Swift">

```swift
AppsFlyerLib.shared().setUserPhone(countryCode: "1", phoneNumber: "(650) 555-1212")
```

</Tab>
</Tabs>

> 📘 **Note**
>
> Pass the country dialing code and local number as plain text. Symbols and spaces are allowed in the local number. The SDK concatenates, normalizes, and hashes both values locally (SHA-256). Don't pre-hash.

To set hashed *Email address* as an additional user identifier:

### **SDK v7.0.0 and earlier**

#### Method signature

```objectivec
- (void) setUserEmails:(NSArray<NSString *> *_Nullable) userEmails 
withCryptType:(EmailCryptType) type;
```

#### Usage example

<Tabs>
<Tab title="Objective-C">

```objectivec
NSArray *emails = @[@"name@domain.com"];    
[[AppsFlyerLib shared] setUserEmails:emails withCryptType:EmailCryptTypeSHA256];
```

</Tab>

<Tab title="Swift">

```swift
let emails: Array = ["name@domain.com"]
AppsFlyerLib.shared().setUserEmails(emails, with: EmailCryptTypeSHA256)
```

</Tab>
</Tabs>

### **SDK v7.0.1 and later**

#### Method signature

```objectivec
- (void) setUserEmail:(NSString *_Nonnull) email;
```

#### Usage example

<Tabs>
<Tab title="Objective-C">

```objectivec
[[AppsFlyerLib shared] setUserEmail:@"name@domain.com"];
```

</Tab>

<Tab title="Swift">

```swift
AppsFlyerLib.shared().setUserEmail("name@domain.com")
```

</Tab>
</Tabs>

> 📘 **Note**
>
> Pass the plain-text email. The SDK normalizes and hashes it locally (SHA-256). Don't pre-hash. Only a single email is accepted per call: calling setUserEmail again overrides the previously set value rather than adding to it.

## Android SDK configuration

To set hashed *Phone number* as an additional user identifier:

### **SDK v7.0.0 and earlier — setAdditionalData**

<Tabs>
<Tab title="Java">

```java
HashMap<String, Object> audiences = new HashMap<>();
audiences.put("phone_number_sha256", "6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37");
audiences.put("phone_number_e164_sha256", "F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E");
HashMap<String, Object> customDataMap = new HashMap<>();
customDataMap.put("audiences", audiences);
AppsFlyerLib.getInstance().setAdditionalData(customDataMap);
```

</Tab>

<Tab title="Kotlin">

```java
val audiences = hashMapOf<String, Any>(
   "phone_number_sha256" to "6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37",
   "phone_number_e164_sha256" to "F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E"
)
val customDataMap = hashMapOf<String, Any>("audiences" to audiences)
AppsFlyerLib.getInstance().setAdditionalData(customDataMap)
```

</Tab>
</Tabs>

> 📘 **Note**
>
> You must pre-hash both values (SHA-256) before passing them in.

### **SDK v7.0.1 and later — setUserPhone (recommended)**

#### Method signature

```java
public abstract void setUserPhone(String countryCode, String phoneNumber);
```

#### Usage example

<Tabs>
<Tab title="Java">

```java
AppsFlyerLib.getInstance().setUserPhone("1", "(650) 555-1212");
```

</Tab>

<Tab title="Kotlin">

```java
AppsFlyerLib.getInstance().setUserPhone("1", "(650) 555-1212")
```

</Tab>
</Tabs>

> 📘 **Note**
>
> Pass the country dialing code and local number as plain text. The SDK concatenates, normalizes, and hashes both values locally (SHA-256). Don't pre-hash.

To set hashed *Email address* as an additional user identifier:

### **SDK v7.0.0 and earlier**

#### Method signature

```java
public abstract void setUserEmails(
  AppsFlyerProperties.EmailsCryptType cryptMethod,
  String... emails
);
```

#### Usage example

<Tabs>
<Tab title="Java">

```java
AppsFlyerLib.getInstance().setUserEmails(
  AppsFlyerProperties.EmailsCryptType.SHA256,
  "name@domain.com",
  "another_name@another_domain.com"
);
```

</Tab>

<Tab title="Kotlin">

```java
AppsFlyerLib.getInstance().setUserEmails(
  AppsFlyerProperties.EmailsCryptType.SHA256,
  "name@domain.com",
  "another_name@another_domain.com"
);
```

</Tab>
</Tabs>

### **SDK v7.0.1 and later**

#### Method signature

```java
public abstract void setUserEmail(String email);
```

#### Usage example

```java
AppsFlyerLib.getInstance().setUserEmail("name@domain.com");
```

> 📘 **Note**
>
> Only a single email is accepted per call in v7.0.1 and later. Multiple emails aren't supported: calling setUserEmail again overrides the previously set value rather than adding to it.

## S2S reference and code samples

When sending identifiers for Audiences via <Anchor target="_blank" href="/marketers/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>, use the `custom_data` parameter for **all identifiers (including hashed** ***Email address*).** You can send one or more identifiers.

<Accordion title="Sending identifiers via S2S">

Format:

* Nested JSON
* The key value must be `audiences`
* All values must be stringified as shown in the following code example
* Parameter names must match those listed in the [table of available identifiers](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting), above

Generic format:

```json
"custom_data" : { 
      \"audiences\" : { 
          \"parameter_name_a\" : \"hashed_identifer_a\",
          \"parameter_name_a\" : \"hashed_identifer_b\",
          \"parameter_name_c\" : \"hashed_identifer_c\" 
       }
 }
```

Populated example for hashed *Phone number* and hashed *Email address*:

```json
"custom_data" : {
     \"audiences\" : { 
         \"phone_number_sha256\" : \"6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37\",
         \"phone_number_e164_sha256\" : \"F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E\",
         \"email_sha256\"         : \"34D31BE18022626DE6B311D6A76E791176D2691B6EEF406F524D8F56364C187A\"
     }
}
```

</Accordion>

> 📘 **Note**
>
> **See also**
>
> * Audiences partner connections
> * Audiences user identifier policy

<div data-zendesk-anchors="background=about-additional-identifiers h_01HNZNWZ9WVH11NG94P5YX5CE0=about-additional-identifiers h_01HNZNWZ9WYWFE1TTS3CWEBS8N=next-steps h_01HNZNWZ9XG5P67Y8P08JGFWFD=available-identifiers h_01HNZNWZ9X0N0D3EF9HJ76EVNJ=sdk-reference-and-code-samples h_01HNZNWZ9XCZFWA7H8BN6J6485=ios-sdk-configuration sdk-v700-and-earlier-%E2%80%94-setadditionaldata=sdk-v700-and-earlier--setadditionaldata h_01KZXZHJZCZ8XNS5Z5JQFGABEJ=sdk-v700-and-earlier--setadditionaldata sdk-v701-and-later-%E2%80%94-setuserphone-recommended=sdk-v701-and-later--setuserphone-recommended h_01KZXZHSF8PCN9A4425217F4YP=sdk-v701-and-later--setuserphone-recommended h_01KZXZF3GX0HSY4BFYX4N4BTHD=method-signature h_01KZXZF3GXN55TJ078CJKMJGSY=usage-example h_01KZXZJ3MEQPEJ73798RY3S3R9=sdk-v700-and-earlier method-signature::a8fd9cf9=method-signature-1 h_01KZXZF3GX62EV1TTA689CK59F=method-signature-1 usage-example::5a156aca=usage-example-1 h_01KZXZF3GXB5VHHYT3SJ60F94V=usage-example-1 h_01KZXZJ98R1274HPDM9T4RTYDP=sdk-v701-and-later method-signature::6246e0dd=method-signature-2 h_01KZXZF3GX9R7J1VF0ZFMJKN4Q=method-signature-2 usage-example::b5bfcf61=usage-example-2 h_01KZXZF3GXQ22XRNRP1H0TX1HG=usage-example-2 h_01HNZNWZ9XAF2K6213ZMMGKQ7T=android-sdk-configuration sdk-v700-and-earlier-%E2%80%94-setadditionaldata::6dbf5d0c=sdk-v700-and-earlier--setadditionaldata-1 h_01KZXZJGMVJQAH5XC1BPJS1DGD=sdk-v700-and-earlier--setadditionaldata-1 sdk-v701-and-later-%E2%80%94-setuserphone-recommended::1b63a185=sdk-v701-and-later--setuserphone-recommended-1 h_01KZXZJX109FSKCCRPVAA1W2Y2=sdk-v701-and-later--setuserphone-recommended-1 method-signature::bf39fa28=method-signature-3 h_01KZXZF3GX3Q6MZX5KXQJSANVK=method-signature-3 usage-example::1515fa60=usage-example-3 h_01KZXZF3GXSXDP4BBFWM7WZ74M=usage-example-3 sdk-v700-and-earlier::5989d839=sdk-v700-and-earlier-1 h_01KZXZK2H50HJVZKF65H59XVXY=sdk-v700-and-earlier-1 method-signature::9b0b0248=method-signature-4 h_01KZXZF3GXZXD09H3T922TGM7N=method-signature-4 usage-example::2bb38341=usage-example-4 h_01KZXZF3GXB7V1YK1584H0NW1G=usage-example-4 sdk-v701-and-later::16b1fdb1=sdk-v701-and-later-1 h_01KZXZK8EXXVDY8P4TR2418FXH=sdk-v701-and-later-1 method-signature::852458c4=method-signature-5 h_01KZXZF3GXX4S3P8SE4SBY6WZ2=method-signature-5 usage-example::11baa27a=usage-example-5 h_01KZXZF3GXM9Q0MQNX2ASEZ2BJ=usage-example-5 h_01HNZNWZ9XKM53TJ9Z0FHWGCYC=s2s-reference-and-code-samples" />
