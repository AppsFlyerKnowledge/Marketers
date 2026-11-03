---
title: Các sự kiện ứng dụng tài chính và ngân hàng được đề xuất
metadata:
  keywords:
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
  created_at: '2021-04-27T12:58:44Z'
  edited_at: '2022-01-25T17:21:41Z'
  id: 360019598337
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/360019598337
---
> **Khái quát:** Đo lường chất lượng của người dùng trong suốt hành trình người dùng của họ bằng cách ghi nhận các sự kiện trong ứng dụng được đề xuất này cho ứng dụng tài chính và ngân hàng của bạn.

## <Image alt="banking.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="100px" /> Tài chính và ngân hàng

Các ứng dụng tài chính và ngân hàng cung cấp cho người dùng khả năng thực hiện nhiều mục tiêu liên quan đến tài chính, chẳng hạn như đăng ký thẻ tín dụng mới hoặc đăng ký vay. Các sự kiện tiêu biểu mà chúng tôi đề xuất ghi nhận bao gồm mở tài khoản, đăng ký thẻ tín dụng và đơn xin vay.

Việc ghi lại các sự kiện này có thể giúp bạn xác định:

* Những tài khoản nào người dùng cần nhất và cung cấp cho bạn các ý tưởng để nhắm mục tiêu lại
* Những lợi ích mà người dùng tìm kiếm ở thẻ tín dụng
* Người dùng cần hỗ trợ tài chính để làm gì và họ muốn được hỗ trợ bao nhiêu

Để biết thêm thông tin về cách ghi lại các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Hướng dẫn sự kiện phong phú trong ứng dụng</Anchor>.

[![Flowchart_for_recommended_events finance_banking_app_user_journey](https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png)](https://files.readme.io/722d2a3df606df1c61f86c7e8e1524566de8fbfd0ceb48e4cd5913a0b3ac9283-360020063337.png)

## Cấu trúc đề xuất cho các sự kiện đã xác định trước

Phần sau đây cung cấp danh sách các cấu trúc sự kiện tiêu biểu cho ngành tài chính và ngân hàng. Mỗi cấu trúc bao gồm một tên sự kiện đã xác định trước và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Đăng nhập (af_login)">

**Mục đích**

Hiểu được việc giữ chân người dùng đã đăng ký của bạn

**Kích hoạt**

Thời điểm người dùng đăng nhập thành công

**Thông số sự kiện**

Có thể được gửi mà không cần bất kỳ thông số bổ sung nào

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.LOGIN, null);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventLogin withValues: nil];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventLogin, withValues: nil);
```

</Tab>

<Tab title="Unity">

```csharp
AppsFlyer.sendEvent ("af_login", null);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Hoàn tất đăng ký (af_complete_registration)">

**Mục đích**

Tìm hiểu số lượng người dùng đã cài đặt ứng dụng và hoàn tất quá trình đăng ký, cùng phương pháp đăng ký nào mà người dùng của bạn thích

**Kích hoạt**

Thời điểm người dùng hoàn tất quá trình đăng ký

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_registration\_method | Loại phương thức đăng ký | email, facebook |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.registration_method, "Facebook");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.complete_registration, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventCompleteRegistration 
withValues: @{ 
  AFEventParamRegistrationMethod: @"Facebook" 
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventCompleteRegistration, 
withValues: [
  AFEventParamRegistrationMethod: "Facebook"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CompletedRegistrationEvent = new Dictionary<string, string>();
CompletedRegistrationEvent.Add("af_registration_method", "Facebook");
AppsFlyer.sendEvent ("af_complete_registration", CompletedRegistrationEvent);
```

</Tab>
</Tabs>

</Accordion>

## Cấu trúc đề xuất cho các sự kiện tùy chỉnh

Phần sau cung cấp danh sách các cấu trúc sự kiện bao gồm tên sự kiện tùy chỉnh và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Đăng ký đã được xác minh (registration_verified)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu số lượng người dùng đăng ký nhưng không được chấp nhận. 

**Kích hoạt**

Khi lượt đăng ký được xác minh

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| submit\_registration | Đã xác minh loại phương thức đăng ký. Không nhập thông tin nhận dạng cá nhân (PII). | email, facebook |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("submit_registration", "facebook");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "registration_verified", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"registration_verified" 
withValues: @{ 
  @"submit_registartion": @"facebook" 
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("registration_verified", 
withValues: [
  "submit_registration": "facebook"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RegistrationVerifiedEvent = new Dictionary<string, string>();
RegistrationVerifiedEvent.Add("submit_registration", "facebook");
AppsFlyer.sendEvent ("registration_verified", RegistrationVerifiedEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Gửi đơn đăng ký tài khoản (submit_account_application)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu số lượng người dùng đăng ký nhưng không xin mở tài khoản.

**Kích hoạt**

Khi người dùng hoàn tất quy trình đăng ký tài khoản

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| account\_type | Loại tài khoản được nộp đơn đăng ký | tiết kiệm |
| application\_method | Nơi thực hiện đơn đăng ký | ứng dụng |
| PII\_type | Loại ID được sử dụng trong quá trình đăng ký | hộ chiếu |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("account_type", "savings");  
eventValue.put("application_method", "app");
eventValue.put("PII_type", "passport");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "submit_account_application", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"submit_account_application" 
withValues: @{ 
  @"account_type": @"savings",   
 @"application_method": @"app",   
 @"PII_type": @"passport" 
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("submit_account_application",   
withValues: [   
"account_type": "savings",  
"application_method": "app",   
"PII_type": "passport"   
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubmitAccountApplicationEvent = new Dictionary<string, string>();
SubmitAccountApplicationEvent.Add("account_type", "savings");  
SubmitAccountApplicationEvent.Add("application_method", "app");
SubmitAccountApplicationEvent.Add("PII_type", "passport");
AppsFlyer.sendEvent ("submit_account_applicationn", SubmitAccountApplicationEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Mở tài khoản thành công (open_account_success)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu xem có bao nhiêu người dùng đăng ký tài khoản và được chấp nhận và sau đó cố gắng cải thiện kênh hoặc nhắm mục tiêu lại những người dùng đó sau.

**Kích hoạt**

Khi đơn đăng ký của người dùng được chấp nhận và tài khoản được mở

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| account\_type | Loại tài khoản đã mở | tiết kiệm |
| application\_method | Nơi thực hiện đơn đăng ký | ứng dụng |
| PII\_type | Loại ID được sử dụng trong quá trình đăng ký | thẻ căn cước |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("account_type", "savings");  
eventValue.put("application_method", "app");
eventValue.put("PII_type", "identification card");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "open_account_suucess", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"open_account_success" 
withValues: @{ 
    @"account_type": @"savings",   
 @"application_method": @"app",   
 @"PII_type": @"identification card"   
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("open_account_success", 
withValues: [
"account_type": "savings",  
"application_method": "app",   
"PII_type": "identification card"   
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> OpenAccountSuccessEvent = new Dictionary<string, string>();
OpenAccountSuccessEventEvent.Add("account_type", "savings");  
OpenAccountSuccessEventEvent.Add("application_method", "app");
OpenAccountSuccessEventEvent.Add("PII_type", "identification_card");
AppsFlyer.sendEvent ("open_account_success", OpenAccountSuccessEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Tài khoản mở bị từ chối (open_account_rejected)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu xem có bao nhiêu người dùng đăng ký tài khoản nhưng không được chấp nhận và sau đó cố gắng cải thiện kênh hoặc nhắm mục tiêu lại những người dùng đó sau.

**Kích hoạt**

Thời điểm người dùng hoàn tất quá trình đăng ký

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| account\_type | Loại tài khoản được nộp đơn đăng ký | tiết kiệm |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("account_type", "savings");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "open_account_rejected", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"open_account_rejected"
withValues: @{ 
  @"account_type": @"savings" 
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("open_account_rejected", 
withValues: [
  "account_type": "savings"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> OpenAccountRejectedEvent = new Dictionary<string, string>();
OpenAccountRejectedEvent.Add("account_type", "savings");
AppsFlyer.sendEvent ("open_account_rejected", OpenAccountRejectedEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đơn đăng ký thẻ tín dụng (submit_credit_card_app)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu xem có bao nhiêu người dùng đăng ký thẻ tín dụng nhưng không được chấp nhận và sau đó cố gắng cải thiện kênh hoặc nhắm mục tiêu lại những người dùng đó sau.

**Kích hoạt**

Khi người dùng gửi đơn đăng ký thẻ tín dụng mới

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| credit\_card\_type | Loại thẻ tín dụng được đăng ký | thẻ vàng |
| application\_method | Nơi thực hiện đơn đăng ký | ứng dụng |
| PII\_type | Loại ID được sử dụng trong quá trình đăng ký | hộ chiếu |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("credit_card_type", "gold card");
eventValue.put("application_method", "app");
eventValue.put("PII_type", "passport");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "submit_credit_card_application", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"submit_credit_card_application"
withValues: @{
   @"credit_card_type": @"gold_card",
   @"application_method": @"app",
   @"PII_type": @"passport"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("submit_credit_card_application", 
withValues: [
   "credit_card_type": "gold_card",
   "application_method": "app",
   "PII_type": "passport"
   ])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubmitCreditCardApplicationEvent = new Dictionary<string, string>();
SubmitCreditCardApplicationEvent.Add("credit_card_type", "gold_card");
SubmitCreditCardApplicationEvent.Add("application_method", "app");
SubmitCreditCardApplicationEvent.Add("PII_type", "passport");
AppsFlyer.sendEvent ("submit_credit_card_application", SubmitCreditCardApplicationEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đăng ký thẻ tín dụng thành công (credit_card_application_success)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu có bao nhiêu người dùng đăng ký thẻ tín dụng và được chấp nhận và sau đó sử dụng thông tin này để cải thiện kênh của bạn hoặc nhắm mục tiêu lại những người dùng được chấp nhận cho các thẻ tín dụng khác.

**Kích hoạt**

Khi đơn đăng ký thẻ tín dụng của người dùng được chấp nhận

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| credit\_card\_type | Loại thẻ tín dụng được đăng ký | thẻ vàng |
| application\_method | Nơi thực hiện đơn đăng ký. | ứng dụng |
| PII\_type | Loại ID được sử dụng trong quá trình đăng ký | thẻ căn cước |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("credit_card_type", gold card);
eventValue.put("application_method", app);  
eventValue.put("PII_type", identification card);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "credit_card_application_success", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"credit_card_application_success"
withValues: @{
  @"credit_card_type": @"gold card",
  @"application_method": @"app",  
  @"PII_type": @"identification card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("credit_card_application_success",
withValues: [
 "credit_card_type": "gold card",
  "application_method": "app",  
  "PII_type": "identification card"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CreditCardApplicationSuccessEvent = new Dictionary<string, string>();
CreditCardApplicationSuccessEvent.Add("redit_card_type", "gold card");
CreditCardApplicationSuccessEvent.Add("application_method", "app");
CreditCardApplicationSuccessEvent.Add("PII_type", "identificationcard");
AppsFlyer.sendEvent ("credit_card_application_success", CreditCardApplicationSuccessEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đơn đăng ký thẻ tín dụng bị từ chối (credit_card_application_rejected)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu xem có bao nhiêu người dùng đăng ký thẻ tín dụng nhưng không được chấp nhận và sau đó sử dụng thông tin này để cải thiện kênh của bạn hoặc nhắm mục tiêu lại những người dùng cho các thẻ tín dụng khác.

**Kích hoạt**

Khi đơn đăng ký thẻ tín dụng của người dùng bị từ chối

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| credit\_card\_type | Loại thẻ tín dụng được đăng ký | thẻ vàng |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("credit_card_type", "gold card");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "credit_card_application_rejected", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent: @"credit_card_application_rejected"
withValues: @{
  "credit_card_type: @"gold card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("credit_card_application_rejected", 
withValues: [
  "credit_card_type: "gold card"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CreditCardApplicationRejectedEvent = new Dictionary<string, string>();
CreditCardApplicationRejectedEvent.Add("credit_card_type", "gold card");
AppsFlyer.sendEvent ("credit_card_application_rejected", CreditCardApplicationRejectedEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Kích hoạt thẻ tín dụng (credit_card_activation)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu xem có bao nhiêu người dùng có thẻ tín dụng nhưng không kích hoạt thẻ đó và sau đó sử dụng thông tin này để cải thiện kênh của bạn hoặc nhắm mục tiêu lại người dùng.

**Kích hoạt**

Khi người dùng kích hoạt thẻ tín dụng mới của họ

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| credit\_card\_type | Loại thẻ tín dụng được đăng ký | thẻ vàng |
| application\_method | Nơi thực hiện đơn đăng ký | ứng dụng |
| PII\_type | Loại ID được sử dụng trong quá trình đăng ký | thẻ căn cước |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("credit_card_type", gold card);
eventValue.put("application_method", app);  
eventValue.put("PII_type", identification card);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "credit_card_activation", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent: @"credit_card_activation"
withValues: @{
  @"credit_card_type": @"gold card",
  @"application_method: @"app",  
  @"PII_type": @"identification card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("credit_card_activation", 
withValues: [
 "credit_card_type": "gold card",
  "application_method": "app",  
  "PII_type": "identification card"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CreditCardActivationEvent = new Dictionary<string, string>();
CreditCardActivationEvent.Add("credit_card_type", "gold card");
CreditCardActivationEvent.Add(application_method", "app");  
CreditCardActivationEvent.Add(PII_type", "identification_card");
AppsFlyer.sendEvent ("credit_card_activation", CreditCardActivationEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Nộp đơn đăng ký vay (submit_loan_application)">

**Mục đích**

Sự kiện này có thể giúp bạn:

* Xác định tổng số đơn đăng ký vay trong ứng dụng của bạn
* Tìm hiểu về số tiền tối đa, tối thiểu và trung bình trong các đơn xin vay tiền.
* Xác định loại khoản vay mà mọi người đăng ký

**Kích hoạt**

Thời điểm người dùng nộp đơn đăng ký vay thành công

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| loan\_id | ID của khoản vay | 1735102 |
| loan\_type | Mục đích của khoản vay | nhà ở |
| loan\_amount | Số tiền yêu cầu | 1000 |
| loan\_period | Thời hạn vay | 3 tháng |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("loan_id", "1735102");  
eventValue.put("loan_type", "housing");
eventValue.put("loam_amount", "1000");
eventValue.put("loan_period", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"submit_loan_application", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent: @"submit_loan_application"
withValues: @{
  @"loan_id": @"1735102",  
@"loan_type": @"housing",
  @"loan_amount": @"1000",
  @"loan_period": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("submit_loan_application", 
withValues: [
   "loan_id": "1735102",  
"loan_type": "housing",
   "loan_amount": "1000",
   "loan_period": "3 months"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubmitLoanApplication = new Dictionary<string, string>();
SubmitLoanApplication.Add("loan_id", "1735102");  
SubmitLoanApplication.Add("loan_type", "housing");
SubmitLoanApplication.Add("loan_amount", "1000");
SubmitLoanApplication.Add("loan_period", "3 months");
AppsFlyer.sendEvent("submit_loan_application", SubmitLoanApplication);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Khoản vay được chấp nhận (loan_accepted)">

**Mục đích**

Tìm hiểu về các xu hướng cho vay và các số liệu khác. Sự kiện này có thể giúp bạn xác định:

* Loại khoản vay nào được chấp nhận
* Số tiền yêu cầu trong các khoản vay đã được phê duyệt
* Những người cho vay nào chấp nhận nhiều khoản vay nhất, loại khoản vay và số tiền được yêu cầu

**Kích hoạt**

Thời điểm một khoản vay được chấp nhận

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| loan\_id | ID của khoản vay | 1735102 |
| loan\_type | Mục đích của khoản vay | nhà ở |
| loan\_amount | Số tiền yêu cầu | 1000 |
| loan\_period | Thời hạn vay | 3 tháng |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("loam_amount", "1000");
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"loan_accepted" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent: @"loan_accepted"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @"1000",
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("loan_accepted", 
withValues: [
  "loan_id": "1735102",
  "loan_amount": "1000",
  "loan_type": "3 months"
])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LoanAccepted = new Dictionary<string, string>();
LoanAccepted.Add("loan_id", "1735102");
LoanAccepted.Add("loan_amount", "1000");
LoanAccepted.Add("loan_type", "3 months");
AppsFlyer.sendEvent("loan_accepted", LoanAccepted);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Khoản vay bị từ chối (loan_rejected)">

**Mục đích**

Hiểu lý do khoản vay bị từ chối. Bạn có thể thấy sự tương quan giữa số tiền và thời gian vay và tỷ lệ từ chối. Bạn cũng có thể nhắm mục tiêu lại người dùng có khoản vay bị từ chối và đề nghị họ vay một khoản vay nhỏ hơn.

**Kích hoạt**

Thời điểm người cho vay từ chối khoản vay

**Thông số sự kiện**  

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| loan\_id | ID của khoản vay | 1735102 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("loan_id", "1735102");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "loan_rejected" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"loan_rejected"
withValues: @{
  @"loan_id": @"1735102",
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("loan_rejected",   
withValues: [
  "loan_id": "1735102",
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LoanRejected = new Dictionary<string, string>();
LoanRejected.Add("loan_id", "1735102");
AppsFlyer.sendEvent("loan_rejected", LoanRejected);
```

</Tab>
</Tabs>

</Accordion>
