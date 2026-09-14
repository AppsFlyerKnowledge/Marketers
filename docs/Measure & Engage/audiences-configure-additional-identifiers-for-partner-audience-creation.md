---
title: "Audiences - Configure additional identifiers for partner audience creation"
excerpt: "Configure additional user identifiers for sending custom audiences to advertising partners."
---
## About additional identifiers

AppsFlyer Audiences automatically supports the following device identifiers for sending custom audiences to [advertising partners](/docs/audiences-partner-connections):

- **iOS**:
 IDFA
- **Android (Google Play):** GAID
- **Android (3rd-party app stores):** [OAID](https://support.appsflyer.com/hc/articles/360006278797) and IMEI

Some advertising partners also support custom audience matching based on additional user identifiers. Audiences offers you the option to use these identifiers if you specifically configure them through the AppsFlyer SDK or S2S-mobile API.

Such additional identifiers can include phone numbers and emails, but can **only be used if encrypted with SHA256 hashing**. Your use of such additional identifiers is subject to the [Additional Identifiers Terms of Use](https://support.appsflyer.com/hc/article_attachments/16567368205201).

## Next steps

1. Select the additional identifiers you want to use (if any) from the [table of available identifiers](https://support.appsflyer.com/hc/articles/360017807278#additional-identifiers%E2%80%94parameters-and-formatting). Note that not all advertising partners support all identifiers.
2. Developers—Configure the selected identifiers, using:
   - Parameters and formatting requirements as appear in the [table of available identifiers](https://support.appsflyer.com/hc/articles/360017807278#additional-identifiers%E2%80%94parameters-and-formatting)
   - The reference and code samples for [SDK](https://support.appsflyer.com/hc/articles/360017807278#sdk-reference-and-code-samples) and [S2S](https://support.appsflyer.com/hc/articles/360017807278#s2s-reference-and-code-samples)
3. In the Audiences dashboard:
   - Set your [account-level user identifier policy](/docs/audiences-user-identifier-policy)
   - Select the identifiers to be uploaded in each of your [partner connections](/docs/audiences-guide#manage-connections)

## Available identifiers

You can elect to configure one or more identifiers, shown in the table below.

### Additional identifiers—parameters and formatting

| Identifier | Parameter name | Format | Example value (before hashing) |
| --- | --- | --- | --- |
| Email address | email\_sha256 | **SDK v7.0.0 and earlier:**<br/>- Lowercase<br/>- No white spaces<br/>- Client-hashed (SHA256) before passing in<br/>**SDK v7.0.1 and later:** Plain text. The SDK normalizes and hashes it automatically. | name@domain.com |
| Phone number | **v7.0.0 and earlier (or S2S):** phone\_number\_sha256<br/>**v7.0.1 and later:** phone\_number\_hashed | **v7.0.0 and earlier (or S2S):**<br/>- No symbols, letters, or leading zeroes<br/>- Include country code<br/>- SHA256 hashed<br/>**v7.0.1 and later:** Plain text. The SDK concatenates the country code and number, normalizes, and hashes it automatically. | 442070313000 |
| Phone number E164 | **v7.0.0 and earlier (or S2S):** phone\_number\_e164\_sha256<br/>**v7.0.1 and later:** phone\_number\_e164\_hashed | **v7.0.0 and earlier (or S2S):**<br/>- E164 phone number<br/>- SHA256 hashed<br/>**v7.0.1 and later:** Plain text. The SDK concatenates the country code and number, normalizes, and hashes it automatically. | +442070313000 |

> 📘 Note
>
> Different advertising partners support different phone number formats. So, if you choose to use phone number, configure both identifiers: *Phone number* and *Phone number E164.*

## SDK reference and code samples

When sending identifiers for Audiences via the SDK:

- For identifiers other than hashed *Email address* or *Phone number*, use `setAdditionalData`.
- For hashed *Email address*:
  - SDK v7.0.1 and later: use `setUserEmail`.
  - SDK v7.0.0 and earlier: use `setUserEmails`.
- For hashed *Phone number*:
  - SDK v7.0.1 and later: use `setUserPhone` (recommended).
  - SDK v7.0.0 and earlier: use `setAdditionalData` with custom data.

> 📘 Note
>
> Keep the following version-dependent changes in mind:
>
> - **Email:** As of SDK v7.0.1, setUserEmails (iOS/Android) has been fully removed and replaced by setUserEmail. This is a breaking change, not a deprecation. Apps on v7.0.0 and earlier must keep using setUserEmails. Apps on v7.0.1 and later must switch to setUserEmail. Check your integrated SDK version before choosing which sample to follow.
> - **Phone:** As of SDK v7.0.1, a dedicated setUserPhone API is available. It's the recommended way to send phone number identifiers for Advanced Matching. This isn't a breaking change: setAdditionalData still works. For new integrations, and for customers who upgrade to v7.0.1 and later, we recommend migrating to setUserPhone. Apps on v7.0.0 and earlier must continue using setAdditionalData, because setUserPhone doesn't exist in those SDK versions.

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

> 📘 Note
>
> You must pre-hash both values (SHA-256) before passing them in.

### **SDK v7.0.1 and later — setUserPhone (recommended)**

#### Method signature

```objectivec
- (void)setUserPhone:(NSString *_Nonnull)countryCode
phoneNumber:(NSString *_Nonnull)phoneNumber;
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

> 📘 Note
>
> Pass the country dialing code and local number as plain text. Symbols and spaces are allowed in the local number. The SDK concatenates, normalizes, and hashes both values locally (SHA-256). Don't pre-hash.

To set hashed *Email address* as an additional user identifier:

### **SDK v7.0.0 and earlier**

#### Method signature

```objectivec
- (void)setUserEmails:(NSArray<NSString *> *_Nullable)userEmails
withCryptType:(EmailCryptType)type;
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
- (void)setUserEmail:(NSString *_Nonnull)email;
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

> 📘 Note
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

> 📘 Note
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

> 📘 Note
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

> 📘 Note
>
> Only a single email is accepted per call in v7.0.1 and later. Multiple emails aren't supported: calling setUserEmail again overrides the previously set value rather than adding to it.

## S2S reference and code samples

When sending identifiers for Audiences via [S2S](https://support.appsflyer.com/hc/articles/207034486-Server-to-server-events-API-for-mobile-S2S-mobile-), use the `custom_data` parameter for **all identifiers (including hashed *Email address*).** You can send one or more identifiers.

### Sending identifiers via S2S

Format:
- Nested JSON
- The key value must be `audiences`
- All values must be stringified as shown in the following code example
- Parameter names must match those listed in the [table of available identifiers](#additional-identifiers%E2%80%94parameters-and-formatting), above

Generic format:

```json
"custom_data" : {
      "audiences" : {
          "parameter_name_a" : "hashed_identifer_a",
          "parameter_name_a" : "hashed_identifer_b",
          "parameter_name_c" : "hashed_identifer_c"
       }
 }
```

Populated example for hashed *Phone number* and hashed *Email address*:

```json
"custom_data" : {
     "audiences" : {
         "phone_number_sha256" : "6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37",
         "phone_number_e164_sha256" : "F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E",
         "email_sha256"         : "34D31BE18022626DE6B311D6A76E791176D2691B6EEF406F524D8F56364C187A"
     }
}
```

<Cards>
  <Card title="Audiences partner connections" href="/docs/audiences-partner-connections">
    Learn how to connect and send custom audiences to advertising partners.
  </Card>
  <Card title="Audiences user identifier policy" href="/docs/audiences-user-identifier-policy">
    Configure account-level user identifier policies for your audiences.
  </Card>
</Cards>