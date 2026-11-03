---
title: Các sự kiện ứng dụng cho vay P2P được đề xuất
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
  created_at: '2021-04-28T09:01:59Z'
  edited_at: '2022-01-25T17:24:53Z'
  id: 360019614017
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/360019614017
---
> **Khái quát:** Đo lường chất lượng của người dùng trong suốt hành trình người dùng của họ bằng cách ghi nhận các sự kiện trong ứng dụng được đề xuất này cho ứng dụng cho vay đồng đẳng (P2P) của bạn.

## <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="100px" /> Cho vay P2P

Cho vay P2P là một phương thức để các cá nhân và doanh nghiệp cho vay và vay tiền từ người khác. Các sự kiện điển hình mà chúng tôi đề xuất ghi nhận là hoạt động của người cho vay và người đi vay cá nhân, loại khoản vay được cung cấp, tỷ lệ chấp nhận và từ chối khoản vay.

Những dữ liệu bạn thu thập được từ việc ghi nhận sự kiện có thể thể hiện rõ những người vay đáng tin cậy và cung cấp cho họ mức lãi suất tốt hơn. Tương tự, bạn có thể xem ai là người cho vay tích cực nhất và đưa ra mức phí thấp hơn dành cho họ. Ngoài ra, khi bạn biết loại khoản vay nào phổ biến nhất với người dùng của mình, bạn có thể khởi chạy chiến dịch tiếp thị nhắm mục tiêu đến đối tượng này.

Để biết thêm thông tin về cách ghi lại các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Hướng dẫn sự kiện phong phú trong ứng dụng</Anchor>.

[![Flowchart_for_recommended_events P2P_lending_app_user_journey](https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png)](https://files.readme.io/597a98cf1df450e9e14eb32d8bdc14df647551ca91a2baca78895ca740eb805c-360020063617.png)

## Cấu trúc đề xuất cho các sự kiện đã xác định trước

Phần sau đây cung cấp danh sách các cấu trúc sự kiện tiêu biểu cho ngành cho vay P2P. Mỗi cấu trúc bao gồm một tên sự kiện đã xác định trước và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Hoàn tất đăng ký (af_complete_registration)">

**Mục đích**

Xác định xem có bao nhiêu người dùng thực sự xác minh danh tính của họ sau khi đăng ký. Bạn có thể phân bổ những người dùng này cho các chiến dịch và xem chiến dịch nào tạo ra những người dùng đang hoạt động.

**Kích hoạt**

Khi việc đăng ký của người dùng được phê duyệt

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_registration\_method | Loại phương thức đăng ký | email, facebook |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REGSITRATION_METHOD, "Facebook");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.COMPLETE_REGISTRATION, eventValue);
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
Dictionary<string, string> CompleteRegistration = new Dictionary<string, string>();
CompleteRegistration.Add("af_registration_method", "Facebook");
AppsFlyer.sendEvent("af_complete_registration", CompleteRegistration);
```

</Tab>
</Tabs>

</Accordion>

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
AppsFlyer.sendEvent("af_login", null);
```

</Tab>
</Tabs>

</Accordion>

## Cấu trúc đề xuất cho các sự kiện tùy chỉnh

Phần sau cung cấp danh sách các cấu trúc sự kiện bao gồm tên sự kiện tùy chỉnh và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Đã gửi đăng ký (registration_submitted)">

**Mục đích**

Bởi vì cho vay P2P dễ bị lạm dụng, nên trước tiên người dùng phải xác minh danh tính của họ. Họ xác minh danh tính bằng cách gửi yêu cầu đăng ký. Sự kiện này có thể giúp bạn:

* Xác định số lượng người dùng đăng ký nhưng không bao giờ xác minh tài khoản của họ
* Xem mối tương quan giữa các phương thức đăng ký, chẳng hạn như email, Facebook, Google và tỷ lệ xác minh

**Kích hoạt**

Sau khi người dùng gửi yêu cầu đăng ký

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_registration\_method | Loại phương thức đăng ký | email, facebook |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REGSITRATION_METHOD, "Facebook");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "registration_submitted", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"registration_submitted" 
withValues: @{
  AFEventParamRegistrationMethod: @"Facebook",
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("registration_submitted", 
withValues: [
  AFEventParamRegistrationMethod: "Facebook"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RegistrationSubmitted = new Dictionary<string, string>();
RegistrationSubmitted.Add("af_registration_method", "Facebook");
AppsFlyer.sendEvent("registration_submitted", RegistrationSubmitted);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Điền vào biểu mẫu cho vay (fill_loan_form_&lt;FORM_NAME>)">

**Mục đích**

Xác định tỷ lệ bỏ và nhắm mục tiêu lại những người vay không hoàn thành đơn xin vay của họ.

Lưu ý rằng khi bạn gửi sự kiện này, hãy bao gồm tên biểu mẫu trong tên sự kiện.

**Kích hoạt**

Khi người vay gửi biểu mẫu

**Thông số sự kiện**

Có thể được gửi mà không cần bất kỳ thông số bổ sung nào

> 📘 **Lưu ý**
>
> Chúng tôi khuyên bạn nên liên kết các khoản vay với người cho vay. Để thực hiện, hãy đảm bảo đặt Customer User ID. <Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid">Cài đặt Customer User ID</Anchor> là cách để so khớp người cho vay với người dùng ứng dụng của bạn khi họ xuất hiện trong AppsFlyer. Bằng cách cài đặt Customer User ID, bạn đảm bảo rằng mọi sự kiện đều được gửi cùng Customer User ID.
>
> **Ví dụ**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "fill_loan_form_FORM_NAME", null);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:@"fill_loan_formFORM_NAME" 
> withValues: nil];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent("fill_loan_form_FORM_NAME", 
> withValues: nil);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> AppsFlyer.sendEvent("fill_loan_form_FORM_NAME", null);
> ```
>
> </Tab>
> </Tabs>
>

<Accordion title="Nộp đơn đăng ký vay (submit_loan_application)">

**Mục đích**

Sự kiện này có thể giúp bạn :

* Xác định tổng số đơn đăng ký vay trong ứng dụng của bạn
* Tìm hiểu về số tiền tối đa, tối thiểu và trung bình trong các đơn xin vay tiền.
* Xác định loại khoản vay mà mọi người đăng ký

**Kích hoạt**

Thời điểm người dùng nộp đơn đăng ký vay thành công

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| loan\_id | ID của khoản vay | 1735102 |
| loan\_amount | Số tiền yêu cầu | 1000 |
| loan\_type | Thời hạn vay | 3 tháng |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("loam_amount", 1000);
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"submit_loan_application", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"submit_loan_application"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @1000,
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("submit_loan_applications", 
withValues: [
   "loan_id": "1735102",
   "loan_amount": 1000,
   "loan_type": "3 months"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubmitLoanApplication = new Dictionary<string, string>();
SubmitLoanApplication.Add("loan_id", "1735102");
SubmitLoanApplication.Add("loan_amount", "1000");
SubmitLoanApplication.Add("loan_type", "3 months");
AppsFlyer.sendEvent("submit_loan_application", SubmitLoanApplication);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Biểu mẫu cho vay (loan_form)">

**Mục đích**

Xem xét các đơn xin vay do người vay nộp

**Kích hoạt**

Khi người vay nộp đơn xin vay thành công

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| loan\_id | ID của khoản vay | 1735102 |
| loan\_amount | Số tiền yêu cầu | 1000 |
| loan\_type | Thời hạn vay | 3 tháng |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("loam_amount", 1000);
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"loan_form", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"loan_form"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @1000,
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("loan_form", 
withValues: [
   "loan_id": "1735102",
   "loan_amount": 1000,
   "loan_type": "3 months"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LoanForm = new Dictionary<string, string>();
SubmitLoanApplication.Add("loan_id", "1735102");
SubmitLoanApplication.Add("loan_amount", "1000");
SubmitLoanApplication.Add("loan_type", "3 months");
AppsFlyer.sendEvent("loan_form", LoanForm);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Gửi séc tín dụng (submit_credit_check)">

**Mục đích**

Kiểm tra lịch sử tài chính của người vay (ví dụ: khoản tín dụng trong quá khứ, thói quen thanh toán và các loại khoản vay) để đánh giá mức độ rủi ro.

**Kích hoạt**

Sau khi người cho vay nhận được yêu cầu cho vay

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| loan\_id | ID của khoản vay | 1735102 |
| loan\_amount | Số tiền yêu cầu | 1000 |
| loan\_type | Thời hạn vay | 3 tháng |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("loam_amount", 1000);
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"submit_credit_check", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"submit_credit_check"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @1000,
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("submit_credit_check", 
withValues: [
   "loan_id": "1735102",
   "loan_amount": 1000,
   "loan_type": "3 months"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubmitCreditCheck = new Dictionary<string, string>();
SubmitLoanApplication.Add("loan_id", "1735102");
SubmitLoanApplication.Add("loan_amount", "1000");
SubmitLoanApplication.Add("loan_type", "3 months");
AppsFlyer.sendEvent("submit_credit_check", SubmitCreditCheck);
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
| loan\_amount | Số tiền yêu cầu | 1000 |
| loan\_type | Thời hạn vay | 3 tháng |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("loam_amount", 1000);
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"loan_accepted" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"loan_accepted"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @1000,
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("loan_accepted", 
withValues: [
  "loan_id": "1735102",
  "loan_amount": 1000,
  "loan_type": "3 months"
]);
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

Hiểu lý do khoản vay bị từ chối. Bạn có thể thấy sự tương quan giữa số tiền khoản vay, thời gian vay và tỷ lệ từ chối. Bạn cũng có thể nhắm mục tiêu lại người dùng có khoản vay bị từ chối và đề nghị họ vay một khoản vay nhỏ hơn.

**Kích hoạt**

Thời điểm người cho vay từ chối khoản vay

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| load\_id | ID của khoản vay | 1735102 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("loam_amount", 1000);
eventValue.put("loan_type", "3 months");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),loan_rejected" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"loan_rejected"
withValues: @{
  @"loan_id": @"1735102",
  @"loan_amount": @1000,
  @"loan_type": @"3 months"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("loan_rejected", withValues: [
  "loan_id": "1735102",
  "loan_amount": 1000,
  "loan_type": "3 months"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LoanRejected = new Dictionary<string, string>();
LoanRejected.Add("loan_id", "1735102");
LoanRejected.Add("loan_amount", "1000");
LoanRejected.Add("loan_type", "3 months");
AppsFlyer.sendEvent("loan_rejected", LoanRejected);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Thanh toán (thanh toán)">

**Mục đích**

Giúp bạn đánh dấu người vay là đáng tin cậy. Những người vay đáng tin cậy là những người tuân thủ nghĩa vụ chi trả các khoản vay. Bạn có thể phân bổ những người vay cho các chiến dịch và hiểu chiến dịch nào đã tạo ra những người vay đáng tin cậy. Ngoài ra, sự kiện này cũng có thể giúp bạn thu thập dữ liệu về các khoản thanh toán tối thiểu, tối đa và trung bình.

**Kích hoạt**

Khi người vay thanh toán khoản vay của họ

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| loan\_id | ID của khoản vay | 1735102 |
| payment\_amount | Số tiền đã trả | 100 |
| payment\_id | ID của khoản thanh toán | AE12SF |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("payment_amount", 100);
eventValue.put("payment_id", "AE12SF");
AppsFlyerLib.getInstance().logEvent(
			  getApplicationContext(),
			 "payment" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"payment"
withValues: @{
  @"loan_id": @"1735102",
  @"payment_amount": @100,
  @"payment_id": @"AE12SF"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("payment", 
withValues: [
  "loan_id": "1735102",
  "payment_amount": 100,
  "payment_id": "AE12SF"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> Payment = new Dictionary<string, string>();
Payment.Add("loan_id", "1735102");
Payment.Add("payment_amount", "100");
Payment.Add("payment_id", "AE12SF");
AppsFlyer.sendEvent("payment", Payment);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Thanh toán đã hoàn tất (payment_completed)">

**Mục đích**

Thể hiện rõ người vay tuân thủ nghĩa vụ chi trả khoản vay. Bạn cũng có thể nhắm mục tiêu lại những người vay đó và cung cấp cho họ mức lãi suất thấp hơn hoặc các chương trình khuyến mãi khác.

**Kích hoạt**

Khi một khoản vay được trả đầy đủ

**Thông số sự kiện**

| Tên trường | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| loan\_id | ID của khoản vay | 1735102 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"payment_completed" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"payment_completed"
withValues: @{
   @"loan_id": @"1735102"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("payment_completed", 
withValues: [
   "loan_id": "1735102"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> PaymentCompleted = new Dictionary<string, string>();
PaymentCompleted.Add("loan_id", "1735102");
AppsFlyer.sendEvent("payment_completed", PaymentCompleted);
```

</Tab>
</Tabs>

</Accordion>

</Accordion>

<Accordion title="Khoản thanh toán đã nhận (payment_received)">

**Mục đích**

Xác minh rằng người vay đã hoàn tất việc thanh toán khoản vay theo các điều khoản của hợp đồng vay.

**Kích hoạt**

Khi người vay thanh toán khoản vay của họ

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| loan\_id | ID của khoản vay | 1735102 |
| payment\_amount | Số tiền đã trả | 100 |
| payment\_id | ID của khoản thanh toán | AE12SF |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("loan_id", "1735102");
eventValue.put("payment_amount", 100);
eventValue.put("payment_id", "AE12SF");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "payment_received" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"payment_received"
withValues: @{
  @"loan_id": @"1735102",
  @"payment_amount": @100,
  @"payment_id": @"AE12SF"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("payment_received", 
withValues: [
  "loan_id": "1735102",
  "payment_amount": 100,
  "payment_id": "AE12SF"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> PaymentReceived = new Dictionary<string, string>();
Payment.Add("loan_id", "1735102");
Payment.Add("payment_amount", "100");
Payment.Add("payment_id", "AE12SF");
AppsFlyer.sendEvent("payment_received", PaymentReceived);
```

</Tab>
</Tabs>

</Accordion>
