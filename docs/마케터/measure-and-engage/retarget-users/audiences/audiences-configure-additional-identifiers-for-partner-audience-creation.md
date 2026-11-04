---
title: 오디언스 - 파트너 오디언스 생성을 위한 투가 식별자 설정
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
  edited_at: '2026-10-22T14:22:27Z'
  id: 360017807278
  locale: ko
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ko/articles/360017807278
---
> **At a glance:** 광고 파트너에게 맞춤 오디언스를 전송하기 위한 추가 사용자 식별자를 구성합니다.

<div id="about-additional-identifiers" />

## 추가 식별자에 대하여

앱스플라이어 오디언스는 <Anchor target="_blank" href="/marketers/ko/docs/audiences-partner-connections">광고 파트너</Anchor>에게 맞춤 오디언스를 전송하기 위해 다음 디바이스 식별자를 자동으로 지원합니다.

* **iOS** **: IDFA**
* **Android(Google Play):** GAID
* **Android(타사 앱 스토어):** <Anchor target="_blank" href="/marketers/ko/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor> 및 IMEI

일부 광고 파트너는 추가 사용자 식별자를 기반으로 한 커스텀 오디언스 매칭도 지원합니다. 오디언스에서는 앱스플라이어 SDK 또는 S2S-mobile API를 통해 특별히 설정하는 경우 이러한 식별자를 활용할 수 있는 옵션을 제공합니다.

이러한 추가 식별자에는 전화번호와 이메일이 포함될 수 있으며, **SHA256 해싱으로 암호화된 경우에만** 사용할 수 있습니다.  이러한 추가 식별자를 사용할 때는 [추가 식별자 이용약관](https://support.appsflyer.com/hc/article_attachments/16567368205201)의 적용을 받습니다.

<div id="next-steps" />

## 다음 단계

1. [사용 가능한 식별자 표](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)에서 사용하려는 추가 식별자를 선택하세요. 모든 광고 파트너가 모든 식별자를 지원하는 것은 아닙니다.
2. 개발자 — 다음을 사용하여 선택한 식별자를 사용하세요.
   * 사용 가능한 식별자의 [표에 나타난 파라미터 및 형식 요구 사항](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)
   * [SDK](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#sdk-참조-및-코드-샘플) 및 [S2S](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#s2s-참조-및-코드-샘플) 참조 및 코드 샘플
3. 오디언스 대시보드에서:
   * <Anchor target="_blank" href="/marketers/ko/docs/audiences-user-identifier-policy">계정 수준의 유저 식별자 정책</Anchor>을 설정하세요.
   * 각 <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#manage-connections">파트너 연결</Anchor>에 업로드할 식별자를 선택하세요.

<div id="available-identifiers" />

## 사용 가능한 식별자

아래 표에 표시된 대로, 하나 이상의 식별자를 구성할 수 있습니다.

<Accordion title="추가 식별자 — 파라미터 및 형식">

<table><tbody><tr><td>식별자</td><td>파라미터 이름</td><td>형식</td><td>예시 값(해싱 전)</td></tr><tr><td>이메일 주소</td><td>email_sha256</td><td><p><strong>SDK v7.0.0 이전</strong></p><ul><li>소문자</li><li>공백 없음</li><li>전달하기 전에 클라이언트 측에서 해시 처리(SHA256)함</li></ul><p><strong>SDK v7.0.1 이후:</strong> 일반 텍스트 SDK가 이 데이터를 자동으로 정규화 및 해시 처리합니다.</p></td><td>name@domain.com</td></tr><tr><td>전화번호<br/>(아래 참고사항 참조)</td><td><p><strong>v7.0.0 이전(또는 S2S):</strong> phone_number_sha256</p><p><strong>v7.0.1 이후:</strong> phone_number_hashed</p></td><td><p><strong>v7.0.0 이전(또는 S2S):</strong></p><ul><li>기호, 문자 또는 선행 0 없음</li><li>국가 코드 포함</li><li>SHA256 해시됨</li></ul><p><strong>SDK v7.0.1 이후:</strong> 일반 텍스트 SDK가 국가 코드와 번호를 연결하고, 자동으로 정규화 및 해시 처리합니다.</p></td><td>442070313000</td></tr><tr><td><p>전화번호 E164</p><p>(아래 참고사항 참조)</p></td><td><p>v7.0.0 이전(또는 S2S): phone_number_e164_sha256</p><p><strong>v7.0.1 이후:</strong> phone_number_e164_hashed</p></td><td><p><strong>v7.0.0 이전(또는 S@S):</strong></p><ul><li>E164 전화번호</li><li>SHA256 해시됨</li></ul><p><strong>v7.0.1 이후</strong> 일반 텍스트 SDK가 국가 코드와 번호를 연결하고, 자동으로 정규화 및 해시 처리합니다.</p></td><td>+442070313000</td></tr><tr><td colspan="4"><p><br /><br /><strong>Note</strong><br /></p><p><strong><span id="h_01HNZNWZ9XSY47T58Z5YR7Q65S"></span>참고사항</strong></p><p>광고 파트너마다 지원하는 전화번호 형식이 다릅니다. 따라서 전화번호를 사용하기로 선택한 경우 <em>전화번호</em> 및 <em>전화번호 E164</em> 두 식별자를 모두 설정하세요. </p></td></tr></tbody></table>

</Accordion>

<div id="sdk-reference-and-code-samples" />

## SDK 참조 및 코드 샘플

SDK를 통해 오디언스 식별자를 발송할 때:

* 해시 처리된 *이메일 주소* 또는 *전화번호* 이외의 식별자에는 `setAdditionalData`를 사용하세요.
* 해시된 *이메일 주소*:
  * SDK v7.0.1 이후: `setUserEmail` 사용
  * SDK v7.0.0 이전: `setUserEmails` 사용
* 해시된 *전화번호*:
  * SDK v7.0.1 및 이후: `setUserPhone` 사용(권장)
  * SDK v7.0.0 및 이전: 사용자 정의 데이터와 함께 `setAdditionalData` 사용

> 📘 **Note**
>
> **참고사항**
>
> 다음 버전별 변경 사항을 확인해 주세요.
>
> * **이메일: SDK v7.0.1부터 setUserEmails(iOS/Android)가 완전히 제거되었으며 setUserEmail로 대체되었습니다. 이는 기능 제공 중단(Deprecation)이 아닌 단절적 변경 사항(Breaking change)입니다. v7.0.0 및 이전 버전을 사용하는 앱은 setUserEmails를 계속 사용해야 합니다. v7.0.1 및 이후 버전을 사용하는 앱은 setUserEmail로 전환해야 합니다. 참조할 예제 코드를 선택하기 전에 연동된 SDK 버전을 확인하세요.**
> * **전화**: SDK v7.0.1부터 전용 setUserPhone API를 사용할 수 있습니다. 이는 고급 매칭을 위해 전화번호 식별자를 전송하는 권장 방식입니다. 이는 단절적 변경 사항(Breaking change)이 아닙니다. setAdditionalData는 여전히 작동합니다. 신규 연동의 경우 및 v7.0.1 및 이후 버전으로 업그레이드하는 고객의 경우 setUserPhone으로 전환하는 것을 권장합니다. v7.0.0 및 이전 버전을 사용하는 앱은 해당 SDK 버전에 setUserPhone이 존재하지 않으므로 setAdditionalData를 계속 사용해야 합니다.

<div id="ios-sdk-configuration" />

## iOS SDK 설정

추가 유저 식별자로 해시된 *전화번호*를 설정하려면:

<div id="sdk-v700-and-earlier--setadditionaldata" />

### **SDK v7.0.0 이전 — setAdditionalData**

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
> **Java Kotlin**
>
> 전달하기 전에 두 값을 모두 미리 해시 처리(SHA-256)해야 합니다.

<div id="sdk-v701-and-later--setuserphone-recommended" />

### **SDK v7.0.1 및 이후 — setUserPhone(권장)**

<div id="method-signature" />

#### 메소드 시그니처

```objectivec
- (void)setUserPhone:(NSString *_Nonnull)countryCode
phoneNumber:(NSString *_Nonnull)phoneNumber;
```

<div id="usage-example" />

#### 사용 예시

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
> **참고사항**
>
> 국가번호와 지역번호를 일반 텍스트로 전달하세요. 지역번호에는 기호와 공백이 허용됩니다. SDK는 두 값을 로컬에서 결합, 정규화 및 해시 처리(SHA-256)합니다. 사전 해시 처리를 하지 마세요.

추가 유저 식별자로 해시된 *이메일 주소*를 설정하려면:

<div id="sdk-v700-and-earlier" />

### **SDK v7.0.0 이전**

<div id="method-signature-1" />

#### 메소드 시그니처

```objectivec
- (void)setUserEmails:(NSArray<NSString *> *_Nullable)userEmails 
withCryptType:(EmailCryptType)type;
```

<div id="usage-example-1" />

#### 사용 예시

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

<div id="sdk-v701-and-later" />

### **SDK v7.0.1 이후**

<div id="method-signature-2" />

#### 메소드 시그니처

```objectivec
- (void)setUserEmail:(NSString *_Nonnull)email;
```

<div id="usage-example-2" />

#### 사용 예시

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
> **참고사항**
>
> 일반 텍스트 형태의 이메일을 전달하세요. SDK는 해당 값을 로컬에서 정규화 및 해시 처리(SHA-256)합니다. 사전 해시 처리를 하지 마세요. 호출당 단 하나의 이메일만 허용됩니다. setUserEmail을 다시 호출하면 기존에 설정된 값을 추가하는 대신 덮어씁니다.

<div id="android-sdk-configuration" />

## 안드로이드 SDK 설정

추가 유저 식별자로 해시된 *전화번호*를 설정하려면:

<div id="sdk-v700-and-earlier--setadditionaldata-1" />

### **SDK v7.0.0 및 이전 — setAdditionalData**

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

```kotlin
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
> **참고사항**
>
> 전달하기 전에 두 값을 모두 사전 해시 처리(SHA-256)해야 합니다.

<div id="sdk-v701-and-later--setuserphone-recommended-1" />

### **SDK v7.0.1 및 이후 — setUserPhone(권장)**

<div id="method-signature-3" />

#### 메소드 시그니처

```java
public abstract void setUserPhone(String countryCode, String phoneNumber);
```

<div id="usage-example-3" />

#### 사용 예시

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
> **참고사항**
>
> 국가번호와 지역번호를 일반 텍스트로 전달하세요. SDK는 두 값을 로컬에서 결합, 정규화 및 해시 처리(SHA-256)합니다. 사전 해시 처리를 하지 마세요.

추가 유저 식별자로 해시된 *이메일 주소*를 설정하려면:

<div id="sdk-v700-and-earlier-1" />

### **SDK v7.0.0 이전**

<div id="method-signature-4" />

#### 메소드 시그니처

```java
public abstract void setUserEmails(
  AppsFlyerProperties.EmailsCryptType cryptMethod,
  String... emails
);
```

<div id="usage-example-4" />

#### 사용 예시

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

<div id="sdk-v701-and-later-1" />

### **SDK v7.0.1 이후**

<div id="method-signature-5" />

#### 메소드 시그니처

```java
public abstract void setUserEmail(String email);
```

<div id="usage-example-5" />

#### 사용 예시

```java
AppsFlyerLib.getInstance().setUserEmail("name@domain.com");
```

> 📘 **Note**
>
> **참고 사항**
>
> v7.0.1 및 이후 버전에서는 호출당 단 하나의 이메일만 허용됩니다. 다중 이메일은 지원되지 않습니다. setUserEmail을 다시 호출하면 기존에 설정된 값을 추가하는 대신 덮어씁니다.

<div id="s2s-reference-and-code-samples" />

## S2S 참조 및 코드 샘플

<Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>를 통해 오디언스용 식별자를 전송할 때, 해시된 <strong><em>이메일 주소</em>를 포함한 </strong>모든 식별자에 `custom_data` 파라미터를 사용하세요. <strong>하나 이상의 식별자를 발송할 수 있습니다.</strong>

<Accordion title="S2S를 통한 식별자 발송">

형식:

* 중첩된 JSON
* 키 값은 `audiences`이어야 합니다.
* 모든 값은 다음 코드 예제에 표시된 대로 문자열로 변환되어야 합니다.
* 파라미터 이름은 위의 [사용 가능한 식별자 테이블](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)에 나열된 이름과 일치해야 합니다.

일반 형식:

```json
"custom_data" : { 
      \"audiences\" : { 
          \"parameter_name_a\" : \"hashed_identifer_a\",
          \"parameter_name_a\" : \"hashed_identifer_b\",
          \"parameter_name_c\" : \"hashed_identifer_c\" 
       }
 }
```

해시된 *전화번호* 및 해시된 *이메일 주소*에 대한 예시:

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
> **참고 문서**
>
> * 오디언스 파트너 연결
> * 오디언스 사용자 식별자 정책

<div data-zendesk-anchors="background=%EC%B6%94%EA%B0%80-%EC%8B%9D%EB%B3%84%EC%9E%90%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HNZNWZ9WVH11NG94P5YX5CE0=%EC%B6%94%EA%B0%80-%EC%8B%9D%EB%B3%84%EC%9E%90%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC next-steps=%EB%8B%A4%EC%9D%8C-%EB%8B%A8%EA%B3%84 h_01HNZNWZ9WYWFE1TTS3CWEBS8N=%EB%8B%A4%EC%9D%8C-%EB%8B%A8%EA%B3%84 available-identifiers=%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EC%8B%9D%EB%B3%84%EC%9E%90 h_01HNZNWZ9XG5P67Y8P08JGFWFD=%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EC%8B%9D%EB%B3%84%EC%9E%90 sdk-reference-and-code-samples=sdk-%EC%B0%B8%EC%A1%B0-%EB%B0%8F-%EC%BD%94%EB%93%9C-%EC%83%98%ED%94%8C h_01HNZNWZ9X0N0D3EF9HJ76EVNJ=sdk-%EC%B0%B8%EC%A1%B0-%EB%B0%8F-%EC%BD%94%EB%93%9C-%EC%83%98%ED%94%8C ios-sdk-configuration=ios-sdk-%EC%84%A4%EC%A0%95 h_01HNZNWZ9XCZFWA7H8BN6J6485=ios-sdk-%EC%84%A4%EC%A0%95 sdk-v700-and-earlier-%E2%80%94-setadditionaldata=sdk-v700-%EC%9D%B4%EC%A0%84--setadditionaldata h_01KZXZHJZCZ8XNS5Z5JQFGABEJ=sdk-v700-%EC%9D%B4%EC%A0%84--setadditionaldata sdk-v701-and-later-%E2%80%94-setuserphone-recommended=sdk-v701-%EB%B0%8F-%EC%9D%B4%ED%9B%84--setuserphone%EA%B6%8C%EC%9E%A5 h_01KZXZHSF8PCN9A4425217F4YP=sdk-v701-%EB%B0%8F-%EC%9D%B4%ED%9B%84--setuserphone%EA%B6%8C%EC%9E%A5 method-signature=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98 h_01KZXZF3GX0HSY4BFYX4N4BTHD=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98 usage-example=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C h_01KZXZF3GXN55TJ078CJKMJGSY=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C sdk-v700-and-earlier=sdk-v700-%EC%9D%B4%EC%A0%84 h_01KZXZJ3MEQPEJ73798RY3S3R9=sdk-v700-%EC%9D%B4%EC%A0%84 method-signature::a8fd9cf9=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98-1 h_01KZXZF3GX62EV1TTA689CK59F=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98-1 usage-example::5a156aca=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C-1 h_01KZXZF3GXB5VHHYT3SJ60F94V=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C-1 sdk-v701-and-later=sdk-v701-%EC%9D%B4%ED%9B%84 h_01KZXZJ98R1274HPDM9T4RTYDP=sdk-v701-%EC%9D%B4%ED%9B%84 method-signature::6246e0dd=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98-2 h_01KZXZF3GX9R7J1VF0ZFMJKN4Q=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98-2 usage-example::b5bfcf61=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C-2 h_01KZXZF3GXQ22XRNRP1H0TX1HG=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C-2 android-sdk-configuration=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-sdk-%EC%84%A4%EC%A0%95 h_01HNZNWZ9XAF2K6213ZMMGKQ7T=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-sdk-%EC%84%A4%EC%A0%95 sdk-v700-and-earlier-%E2%80%94-setadditionaldata::6dbf5d0c=sdk-v700-%EB%B0%8F-%EC%9D%B4%EC%A0%84--setadditionaldata h_01KZXZJGMVJQAH5XC1BPJS1DGD=sdk-v700-%EB%B0%8F-%EC%9D%B4%EC%A0%84--setadditionaldata sdk-v701-and-later-%E2%80%94-setuserphone-recommended::1b63a185=sdk-v701-%EB%B0%8F-%EC%9D%B4%ED%9B%84--setuserphone%EA%B6%8C%EC%9E%A5-1 h_01KZXZJX109FSKCCRPVAA1W2Y2=sdk-v701-%EB%B0%8F-%EC%9D%B4%ED%9B%84--setuserphone%EA%B6%8C%EC%9E%A5-1 method-signature::bf39fa28=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98-3 h_01KZXZF3GX3Q6MZX5KXQJSANVK=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98-3 usage-example::1515fa60=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C-3 h_01KZXZF3GXSXDP4BBFWM7WZ74M=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C-3 sdk-v700-and-earlier::5989d839=sdk-v700-%EC%9D%B4%EC%A0%84-1 h_01KZXZK2H50HJVZKF65H59XVXY=sdk-v700-%EC%9D%B4%EC%A0%84-1 method-signature::9b0b0248=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98-4 h_01KZXZF3GXZXD09H3T922TGM7N=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98-4 usage-example::2bb38341=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C-4 h_01KZXZF3GXB7V1YK1584H0NW1G=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C-4 sdk-v701-and-later::16b1fdb1=sdk-v701-%EC%9D%B4%ED%9B%84-1 h_01KZXZK8EXXVDY8P4TR2418FXH=sdk-v701-%EC%9D%B4%ED%9B%84-1 method-signature::852458c4=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98-5 h_01KZXZF3GXX4S3P8SE4SBY6WZ2=%EB%A9%94%EC%86%8C%EB%93%9C-%EC%8B%9C%EA%B7%B8%EB%8B%88%EC%B2%98-5 usage-example::11baa27a=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C-5 h_01KZXZF3GXM9Q0MQNX2ASEZ2BJ=%EC%82%AC%EC%9A%A9-%EC%98%88%EC%8B%9C-5 s2s-reference-and-code-samples=s2s-%EC%B0%B8%EC%A1%B0-%EB%B0%8F-%EC%BD%94%EB%93%9C-%EC%83%98%ED%94%8C h_01HNZNWZ9XKM53TJ9Z0FHWGCYC=s2s-%EC%B0%B8%EC%A1%B0-%EB%B0%8F-%EC%BD%94%EB%93%9C-%EC%83%98%ED%94%8C" />
