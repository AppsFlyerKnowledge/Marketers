---
title: Các sự kiện ứng dụng giải trí được đề xuất
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
  created_at: '2021-04-25T10:44:33Z'
  edited_at: '2022-01-25T17:24:23Z'
  id: 360019699898
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/360019699898
---
> **Khái quát:** Đo lường chất lượng của người dùng trong suốt hành trình người dùng của họ bằng cách ghi nhận các sự kiện trong ứng dụng được đề xuất này cho ứng dụng giải trí của bạn.

## <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="100px" /> Giải trí

Với yêu cầu ngày càng tăng cao của người dùng về nội dung theo yêu cầu, thị trường ứng dụng giải trí ngày càng cạnh tranh gay gắt. Các sự kiện tiêu biểu mà chúng tôi đề xuất ghi nhận là gói đăng ký của người dùng, nội dung phát trực tuyến, nội dung tải xuống và lưu.

Việc ghi nhận các sự kiện có thể giúp bạn xác định:

* Nội dung người dùng sử dụng
* Hiệu suất chiến dịch theo nội dung người dùng yêu cầu
* Mức độ tương tác và sử dụng của người dùng

Các sự kiện này cũng liên quan đến các ứng dụng giải trí chạy trên các tivi thông minh sau:

* TV thông minh Android
* Apple TV (tvOS)
* Amazon Fire TV

Để biết thêm thông tin về cách ghi lại các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Hướng dẫn sự kiện phong phú trong ứng dụng</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events entertainment_app_user_journey" src="https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png" />

## Cấu trúc đề xuất cho các sự kiện đã xác định trước

Phần sau đây cung cấp danh sách các cấu trúc sự kiện tiêu biểu cho ngành giải trí. Mỗi cấu trúc bao gồm một tên sự kiện đã xác định trước và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Hoàn tất đăng ký (af_complete_registration)">

**Mục đích**

Tìm hiểu số lượng người dùng đã cài đặt ứng dụng và hoàn tất quá trình đăng ký, cùng phương pháp đăng ký nào mà người dùng của bạn thích

**Kích hoạt**

Thời điểm người dùng hoàn tất quá trình đăng ký

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_registration\_method | Phương thức đăng ký mà người dùng chọn | Facebook, Google, email |

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
Dictionary<string, string> CompleteRegistrationEvent = new Dictionary<string, string>();
CompleteRegistrationEvent.Add("af_registration_method", "Facebook");
AppsFlyer.sendEvent("af_complete_registration", CompleteRegistrationEvent);
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

<Accordion title="Bắt đầu dùng thử (af_start_trial)">

**Mục đích**

Nhiều dịch vụ phát trực tuyến cung cấp cho người dùng thời gian dùng thử để khám phá các tính năng cao cấp. Sự kiện này có thể giúp bạn:

* Xem có bao nhiêu người dùng chọn tham gia thời gian dùng thử
* Việc dùng thử là một phần của chương trình khuyến mãi hay hợp tác với đối tác
* Chương trình khuyến mãi nào đã khuyến khích người dùng kích hoạt thời gian dùng thử

**Kích hoạt**

Khi người dùng chọn tham gia và kích hoạt thời gian dùng thử

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| trial\_method | Phương pháp kích hoạt bản dùng thử | Miễn phí với điện thoại mới, miễn phí với nhà cung cấp dịch vụ, khuyến mãi, mã giảm giá |
| trial\_method\_identifier | Mã định danh phương pháp dùng thử | Tên của nhà cung cấp dịch vụ, ví dụ: **Vodafone**<br /><br />Tên của đối tác, ví dụ: **Facebook**<br /><br />Mã phiếu giảm giá, ví dụ: **TRA123** |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("trial_method", "coupon code");
eventValue.put("trial_method_identifier", "TRA123");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.START_TRIAL, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventStartTrial
withValues: @{
  @"trial_method": @"coupon code",
  @"trial_method_identifier": @"TRA123"
}]
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventStartTrial,
withValues: [
  "trial_method": "coupon code",
  "trial_method_identifier": "TRA123"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubscriptionTrial = new Dictionary<string, string>();
SubscriptionTrial.Add("trial_method ", "coupon code");
SubscriptionTrial.Add("trial_method_identifier", "TRA123");
AppsFlyer.sendEvent("af_start_trial", SubscriptionTrial);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đăng ký (af_subscribe)">

**Mục đích**

Đăng ký là yếu tố chính của dịch vụ phát trực tuyến. Sự kiện này có thể giúp bạn:

* Xem chiến dịch nào mang đến những người dùng đăng ký
* So sánh lượng người dùng thử so với lượng người dùng đăng ký
* Xác định khoản doanh thu được tạo từ các gói đăng ký và phân bổ doanh thu cho chiến dịch và nguồn truyền thông

**Kích hoạt**

* Khi người dùng đăng ký thành công
* Khi đăng ký được gia hạn

Tham khảo Hướng dẫn ghi nhận đăng ký của chúng tôi để biết thêm thông tin.

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| new\_subscription | Cho dù đăng ký mới hay gia hạn | true / false |
| af\_coupon\_code | Mã phiếu giảm giá nếu có sử dụng trong quá trình đăng ký | 3MonthsSubscription |
| coupon\_code\_value | Phiếu giảm giá khấu trừ bao nhiêu tiền từ giá ban đầu | 10% |
| af\_revenue | Doanh thu liên quan tới đăng ký | 5 |
| af\_currency | Đơn vị tiền tệ thanh toán cho đăng ký | USD |
| subscription\_method | Phương thức thanh toán sử dụng trong đăng ký | thẻ tín dụng, ví điện tử, PayPal |
| expiration\_date | Ngày hết hạn của gói đăng ký | 2018/07/18 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put("new_subscription", true);
eventValue.put(AFInAppEventParameterName.COUPON_CODE, "3MonthsSubscription");
eventValue.put("coupon_code_value", "10%");
eventValue.put(AFInAppEventParameterName.REVENUE, 5);
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
eventValue.put("subscription_method", "");
eventValue.put("expiration_date", "2018/07/18");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.SUBSCRIBE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventSubscribe
withValues: @{
 @"new_subscription": @TRUE,
 AFEventParamCouponCode: @"3MonthsSubscription",
 @"coupon_code_value": @"10%",
 AFEventParamRevenue: @5,
 AFEventParamCurrency: @"USD",
 @"subscription_method": @"",
 @"expiration_date": @"2018/07/18"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventSubscribe, 
withValues: [
 "new_subscription": true,
 AFEventParamCouponCode: "3MonthsSubscription",
 "coupon_code_value": "10%",
 AFEventParamRevenue: 5,
 AFEventParamCurrency: "USD",
 "subscription_method": "",
 "expiration_date": "2018/07/18"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> Subscription = new Dictionary<string, string>();
Subscription.Add("new_subscription", "true");
Subscription.Add("af_coupon_code", "3MonthsSubscription");
Subscription.Add("coupon_code_value", "10%");
Subscription.Add("af_revenue", "5");
Subscription.Add("af_currency", "USD");
Subscription.Add("subscription_method", "");
Subscription.Add("expiration_date", "2018/07/18");
AppsFlyer.sendEvent("af_subscribe", Subscription);
```

</Tab>
</Tabs>

</Accordion>

## Cấu trúc đề xuất cho các sự kiện tùy chỉnh

Phần sau cung cấp danh sách các cấu trúc sự kiện bao gồm tên sự kiện tùy chỉnh và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Phát nội dung đa phương tiện (media_play)">

**Mục đích**

Ghi nhận các sự kiện mà người dùng phát nội dung đa phương tiện bạn cung cấp. Ví dụ: các nội dung đa phương tiện đó có thể là video, âm nhạc, chương trình truyền hình hoặc chương trình radio.

Việc ghi nhận sự kiện này có thể giúp bạn xác định:

* Theo dõi mức sử dụng nội dung đa phương tiện theo loại và nội dung
* Ngôn ngữ nội dung được truyền trực tuyến phổ biến nhất
* Thời lượng tối thiểu, tối đa và trung bình của nội dung được truyền trực tuyến

**Kích hoạt**

Sau một con số được xác định trước, chẳng hạn như 2 phút phát nội dung trực tuyến.

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_content\_type | Loại nội dung phát trực tuyến | chương trình truyền hình, âm nhạc |
| af\_content\_id | ID nội dung phát trực tuyến | 092, E34 |
| af\_content | Tiêu đề nội dung, tức là tên bài hát hoặc tiêu đề và tập của chương trình truyền hình | Tiêu đề nội dung |
| media\_duration | Thời gian chạy | 5 |
| language | Ngôn ngữ nội dung | en-us, fr, es |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "tv show");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "E34");
eventValue.put(AFInAppEventParameterName.CONTENT, "My Show");
eventValue.put("media_duration", 5);
eventValue.put("language", "en-us");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "media_play", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"media_play"
withValues: @{
	AFEventParamContentType: @"tv show",
	AFEventParamContentId: @"E34",
	AFEventParamContent: @"My Show",
	@"duration": @5,
	@"langague": @"en-us"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("media_play", 
withValues: [
AFEventParamContentType: "tv show",
AFEventParamContentId: "E34",
AFEventParamContent: "My Show",
"media_duration": 5,
"language": "en-us"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> MediaPlay = new Dictionary<string, string>();
MediaPlay.Add("af_content_type", "tv show");
MediaPlay.Add("af_content_id", "E34");
MediaPlay.Add("af_content", "My show");
MediaPlay.Add("media_duration", "5");
MediaPlay.Add("language", "en-us");
AppsFlyer.sendEvent("media_play", MediaPlay);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Số phút của nội dung đa phương tiện (media_minutes)">

**Mục đích**

Số phút của đa phương tiện là lượng thời gian mà người dùng sử dụng cho một mục nội dung nhất định. Sau chỉ số doanh thu, đây là chỉ số quan trọng nhất trong ngành phát trực tuyến vì chỉ số này cho phép bạn ước tính mức sử dụng dịch vụ của người dùng. Nó cũng cho phép bạn biết được tỷ lệ sử dụng tổng thể của dịch vụ là bao nhiêu và nội dung nào là phổ biến nhất. Sự kiện này có thể giúp bạn:

* Xem người dùng nào sử dụng nhiều dịch vụ của bạn
* Hiểu được loại nội dung đa phương tiện và nội dung nào là phổ biến

**Kích hoạt**

Một trong những thông tin sau:

* Khi người dùng kết thúc truyền trực tuyến một mục nội dung đa phương tiện
* Khi người dùng thoát truyền trực tuyến một mục nội dung đa phương tiện

**Thông số sự kiện**

| Tên | Mô tả | Giá trị  mẫu |
| --- | --- | --- |
| minutes\_consumed | Thời gian người dùng chạy nội dung đa phương tiện thực tế | 3 |
| af\_content\_type | Loại nội dung phát trực tuyến | chương trình truyền hình, âm nhạc |
| af\_content\_id | ID nội dung phát trực tuyến | 092, E34 |
| af\_content | Tiêu đề nội dung, chẳng hạn như tên bài hát hoặc tiêu đề và tập của chương trình truyền hình | Tiêu đề nội dung |
| media\_duration | Thời gian chạy | 5 |
| language | Ngôn ngữ nội dung | en-us, fr, es |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "tv show");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "E34");
eventValue.put(AFInAppEventParameterName.CONTENT, "My Show");
eventValue.put("media_duration", 5);
eventValue.put("language", "en-us");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),"media_minutes", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"media_minutes"
withValues: @{
 @"minutes_consumed": @3,
 AFEventParamContentType: @"tv show",
 AFEventParamContentId: @"E34",
 AFEventParamContent: @"My Show",
 @"duration": @5,
 @"langague": @"en-us"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("media_minutes", withValues: [
 "minutes_consumed": 3,
 AFEventParamContentType: "tv show",
 AFEventParamContentId: "E34",
 AFEventParamContent: "My Show",
 "media_duration": 5,
 "language": "en-us"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> MediaMinutes = 
		 new Dictionary<string, string>();
MediaMinutes.Add("minutes_consumed", "3");
MediaMinutes.Add("af_content_type", "tv show");
MediaMinutes.Add("af_content_id", "E34");
MediaMinutes.Add("af_content", "My show");
MediaMinutes.Add("media_duration", "5");
MediaMinutes.Add("language", "en-us");
AppsFlyer.sendEvent("media_minutes", MediaMinutes);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đã tải xuống nội dung đa phương tiện (media_downloaded)">

**Mục đích**

Làm nổi bật sở thích của người dùng bằng cách ghi nhận quá trình phát nội dung đa phương tiện, tải xuống nội dung đa phương tiện và so sánh cả hai. Bạn có thể xem người dùng thích phát loại nội dung đa phương tiện nào và muốn tải xuống loại nội dung đa phương tiện nào.

**Kích hoạt**

Khi người dùng bắt đầu tải xuống nội dung đa phương tiện

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_content\_type | Loại nội dung | chương trình truyền hình, âm nhạc |
| af\_content\_id | ID nội dung | 092, E34 |
| af\_content | Tiêu đề nội dung, tức là tên bài hát hoặc tiêu đề và tập của chương trình truyền hình | Tiêu đề nội dung |
| media\_duration | Thời gian chạy | 5 |
| language | Ngôn ngữ nội dung | en-us, fr, es |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "tv show");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "E34");
eventValue.put(AFInAppEventParameterName.CONTENT, "My Show");
eventValue.put("media_duration", 5);
eventValue.put("language", "en-us");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "media_downloaded", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"media_downloaded"
withValues: @{
	@"minutes_consumed": @3,
	AFEventParamContentType: @"tv show",
	AFEventParamContentId: @"E34",
	AFEventParamContent: @"My Show",
	@"duration": @5,
	@"langague": @"en-us"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("media_downloaded", 
withValues: [
	"minutes_consumed": 3,
	AFEventParamContentType: "tv show",
	AFEventParamContentId: "E34",
	AFEventParamContent: "My Show",
	"media_duration": 5,
	"language": "en-us"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> MediaDownloaded = new Dictionary<string, string>();
MediaDownloaded.Add("minutes_consumed", "3");
MediaDownloaded.Add("af_content_type", "tv show");
MediaDownloaded.Add("af_content_id", "E34");
MediaDownloaded.Add("af_content", "My show");
MediaDownloaded.Add("media_duration", "5");
MediaDownloaded.Add("language", "en-us");
AppsFlyer.sendEvent("media_downloaded", MediaDownloaded);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đã lưu nội dung đa phương tiện (media_saved)">

**Mục đích**

Giúp bạn làm nổi bật sở thích của người dùng

**Kích hoạt**

Bất cứ khi nào nội dung đa phương tiện được lưu trên thiết bị của người dùng

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_content\_type | Loại nội dung | chương trình truyền hình, âm nhạc |
| af\_content\_id | ID nội dung | 092, E34 |
| af\_content | Tiêu đề nội dung, chẳng hạn như tên bài hát hoặc tiêu đề và tập của chương trình truyền hình | Tiêu đề nội dung |
| media\_duration | Thời gian chạy | 5 |
| language | Ngôn ngữ nội dung | en-us, fr, es |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "tv show");
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "E34");
eventValue.put(AFInAppEventParameterName.CONTENT, "My Show");
eventValue.put("media_duration", 5);
eventValue.put("language", "en-us");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "media_saved", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"media_saved"
withValues: @{
	@"minutes_consumed": @3,
	 AFEventParamContentType: @"tv show",
	 AFEventParamContentId: @"E34",
	 AFEventParamContent: @"My Show",
	 @"duration": @5,
	 @"langague": @"en-us"  
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("media_saved", 
withValues: [  
 "minutes_consumed": 3,
	 AFEventParamContentType: "tv show",
	 AFEventParamContentId: "E34",
	 AFEventParamContent: "My Show",
	 "media_duration": 5,
	 "language": "en-us"]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> MediaSaved = new Dictionary<string, string>();
MediaSaved.Add("minutes_consumed", "3");
MediaSaved.Add("af_content_type", "tv show");
MediaSaved.Add("af_content_id", "E34");
MediaSaved.Add("af_content", "My show");
MediaSaved.Add("media_duration", "5");
MediaSaed.Add("language", "en-us");
AppsFlyer.sendEvent("media_saved", MediaSaved);
```

</Tab>
</Tabs>

</Accordion>
