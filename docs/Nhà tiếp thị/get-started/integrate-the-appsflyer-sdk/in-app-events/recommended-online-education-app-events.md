---
title: Các sự kiện ứng dụng giáo dục trực tuyến được đề xuất
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
  created_at: '2021-04-28T12:35:57Z'
  edited_at: '2022-01-25T17:24:21Z'
  id: 360019794378
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/360019794378
---
> **Khái quát:** Đo lường chất lượng của người dùng trong suốt hành trình người dùng của họ bằng cách ghi nhận các sự kiện trong ứng dụng được đề xuất này cho ứng dụng giáo dục trực tuyến của bạn.

## <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="100px" /> Đào tạo trực tuyến

Ứng dụng đào tạo trực tuyến cho phép người dùng học từ xa. Các sự kiện tiêu biểu mà chúng tôi khuyến khích bạn nên ghi nhận bao gồm đăng ký, hướng dẫn và các khóa học đã hoàn thành cũng như các chứng chỉ nhận được.

Việc ghi nhận các sự kiện có thể giúp bạn xác định:

* Những khóa học nào mà người dùng mong muốn nhất và cung cấp cho bạn các ý tưởng để nhắm mục tiêu
* Những người dùng nào có thể được nhắm mục tiêu lại và nhắc bạn rằng họ còn có các hướng dẫn khác để hoàn thành khóa học
* Những khóa học và chứng chỉ nào đang có nhu cầu nhiều nhất

Để biết thêm thông tin về cách ghi lại các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Hướng dẫn sự kiện phong phú trong ứng dụng</Anchor>.

[![Flowchart_for_recommended_events_online_education_app_user_journey](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)

## Cấu trúc đề xuất cho các sự kiện đã xác định trước

Phần sau đây cung cấp danh sách các cấu trúc sự kiện tiêu biểu cho ngành giáo dục trực tuyến. Mỗi cấu trúc bao gồm một tên sự kiện đã xác định trước và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Đăng nhập (af_login)">

**Mục đích**

Hiểu được việc giữ chân người dùng đã đăng ký của bạn

**Kích hoạt**

Mỗi khi người dùng đăng nhập thành công

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
Map<String, Object> eventValue = new HashMap<>();
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
Dictionary<string, string> CompleteRegistrationEvent = new Dictionary<string, string>();
CompleteRegistrationEvent.Add("af_registration_method", "Facebook");
AppsFlyer.sendEvent ("af_complete_registration", CompleteRegistrationEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Hoàn thành hướng dẫn (af_tutorial_completion)">

**Mục đích**

Việc ghi nhận sự kiện này có thể giúp bạn xác định:

* Những chủ đề nào mà người dùng có thể gặp khó khăn
* Những hướng dẫn nào không hoạt động tốt và cải thiện chúng
* Liên kết hoạt động tổng thể của người dùng với các thứ nguyên như doanh thu.

**Kích hoạt**

* Khi người dùng xem xong hướng dẫn.
* Khi người dùng bắt đầu xem hướng dẫn nhưng thoát ra và không hoàn thành.

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_success | Người dùng có hoàn thành hướng dẫn hay không | yes |
| af\_tutorial\_id | ID hướng dẫn | 3 |
| af\_content | Tên hướng dẫn | algebra |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();  
eventValue.put(AFInAppEventParameterName.SUCCESS, yes);  
eventValue.put(AFInAppEventParameterName.TUTORIAL_ID, "3");  
eventValue.put(AFInAppEventParameterName.CONTENT, "algebra");  
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.TUTORIAL_COMPLETION, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventTutorial_completion
withValues: @{
  AFEventParamSuccess: @YES,
  AFEventParamTutorialId: @"3",
  AFEventParamContent: @"algebra"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventTutorial_completion, 
withValues: [
  AFEventParamSuccess: YES,
  AFEventParamTutorialId: "3",
  AFEventParamContent: "algebra"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> TutorialCompletiondEvent = new Dictionary<string, string>();
TutorialCompletiondEvent.Add("af_success", "yes");
TutorialCompletiondEvent.Add("af_tutorial_id", "3");
TutorialCompletiondEvent.Add("af_tutorial_content", "algebra");
AppsFlyer.sendEvent ("af_tutorial_completion", TutorialCompletiondEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Mua hàng (af_purchase)">

**Mục đích**

Việc ghi nhận các giao dịch mua trong ứng dụng do người dùng thực hiện có thể giúp bạn:

* Xác định LTV của người dùng và ROI của các chiến dịch của bạn trên các mạng quảng cáo và các đại lý quảng cáo
* Xác định những ưu đãi nào được người dùng chọn nhiều nhất
* Chiến dịch tham chiếu chéo với các mặt hàng đã mua để tối ưu hóa nhắm mục tiêu chiến dịch

**Kích hoạt**

Thời điểm người dùng truy cập trang cảm ơn sau khi mua hàng thành công

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Doanh thu ước tính từ giao dịch mua | 250.99 |
| af\_currency | Mã tiền tệ | USD |
| af\_content\_id | ID của mục | 001, 092 |
| order\_id | ID đặt xe | 9277 |
| af\_receipt\_id | ID hóa đơn | 9277 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put(AFInAppEventParameterName.REVENUE, 250.99);
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "092");
eventValue.put("order_id", "9277");
eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "9277");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),AFInAppEventType.PURCHASE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventPurchase
withValues: @{
   AFEventParamRevenue: @250.99,
   AFEventParamCurrency: @"USD",
   AFEventParamContentId: @"092",
   @"order_id": @"9277",
   AFEventParamReceiptId: @"9277"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventPurchase, 
withValues: [
   AFEventParamRevenue: 250.99,
   AFEventParamCurrency: "USD",
   AFEventParamContentId: "092",
   "order_id": "9277",
   AFEventParamReceiptId: "9277"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> purchaseEvent = new Dictionary<string, string>();
purchaseEvent.Add("af_revenue", "250.99");
purchaseEvent.Add("af_currency", "USD");
purchaseEvent.Add("af_content_id", "001");
purchaseEvent.Add("order_id", "9277");
purchaseEvent.Add("af_receipt_id", "9277");
AppsFlyer.sendEvent ("af_purchase", purchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

## Cấu trúc đề xuất cho các sự kiện tùy chỉnh

Phần sau cung cấp danh sách các cấu trúc sự kiện bao gồm tên sự kiện tùy chỉnh và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Bài tập hoàn chỉnh (complete_excercise)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu số lượng người dùng bắt đầu nhưng không hoàn thành một bài tập.

**Kích hoạt**

Khi người dùng hoàn thành một bài tập

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| course\_name | Tên của khóa học | algebra |
| exercise\_name | Tên của bài tập | 2 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
              eventValue.put("course_name", "algebra");
              eventValue.put("exercise_name", "2");
              AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "complete_exercise", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"complete_exercise"
withValues: @{ 
  @"course_name": @"algebra",  
 @"exercise_name": @"2"  
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("complete_exercise",withValues: 
["course_name": "algebra","exercise_name": "2" ])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CompleteExerciseEvent = new Dictionary<string, string>();
CompleteExerciseEvent.Add("course_name", "algebra");  
CompleteExerciseEvent.Add("exercise_name", "2");
AppsFlyer.sendEvent ("complete_exercise", CompleteExerciseEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Khóa học đã hoàn thành (course_completed)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu số lượng người dùng bắt đầu nhưng không hoàn thành một khóa học.

**Kích hoạt**

Khi người dùng hoàn thành một khóa học

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| course\_name | Tên của khóa học | algebra |
| course\_completed | Người dùng đã hoàn thành khóa học hay chưa | yes |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("course_name", "algebra");
eventValue.put("course_completed", "yes");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "course_completed", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[AppsFlyerLib shared] logEvent:@"course_completed" withValues:@{ 
@"course_name": @"algebra", 
@"course_completed": @"yes"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("course_completed", withValues: 
[ "course_name": "algebra",
"course_completed": "yes"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CourseCompletedEvent = new Dictionary<string, string>();
CourseCompletedEvent.Add("course_name", "algebra");  
CourseCompletedEvent.Add("course_completed", "yes");
AppsFlyer.sendEvent ("course_completed", CourseCompletedEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Chứng chỉ đã được cấp (certificate_issued)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu số lượng người dùng hoàn thành một khóa học, sau đó nhắm mục tiêu lại họ cho khóa học tiếp theo.

**Kích hoạt**

Khi người dùng được cấp chứng chỉ

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| course\_name | Tên của khóa học | algebra |
| certificate\_received | Chứng chỉ đã được cấp hay chưa | yes |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("course_name", "algebra");
eventValue.put("certificate_received", "yes");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "certificate issued", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"course_completed" withValues: @{ 
@"course_name": @"algebra", 
@"certificate_received": @"yes"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("certificate issued", withValues: 
[ "course_name": "algebra",
"certificate_received": "yes"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CertificateIssuedEvent = new Dictionary<string, string>();
CertificateIssuedEvent.Add("course_name", "algebra");  
CertificateIssuedEvent.Add("certificate_received", "yes");
AppsFlyer.sendEvent ("certificate issued", CertificateIssuedEvent);
```

</Tab>
</Tabs>

</Accordion>
