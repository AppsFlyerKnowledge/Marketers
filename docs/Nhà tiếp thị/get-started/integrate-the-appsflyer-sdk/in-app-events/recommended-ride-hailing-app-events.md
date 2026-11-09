---
title: Các sự kiện trong ứng dụng gọi xe được đề xuất
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
  created_at: '2021-04-29T08:42:34Z'
  edited_at: '2022-01-25T17:24:50Z'
  id: 360019651957
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/360019651957
---
> **Khái quát:** Đo lường chất lượng của người dùng trong suốt hành trình người dùng của họ bằng cách ghi nhận các sự kiện trong ứng dụng được đề xuất này cho ứng dụng gọi xe của bạn.

## <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="100px" /> Gọi xe

Ứng dụng gọi xe ngày càng trở nên phổ biến trong thời gian gần đây, đặc biệt là ở các khu vực đô thị, nơi hầu hết người dân không sở hữu xe hơi. Các sự kiện điển hình mà chúng tôi đề xuất ghi nhận là yêu cầu gọi xe và đặt xe.

Việc ghi nhận các sự kiện có thể giúp bạn xác định:

* Cách mà hành khách và lái xe tương tác với nhau
* Các quốc gia nơi có nhiều người sử dụng dịch vụ gọi xe của bạn hơn
* Số liệu về giá, các chuyến đi và quãng đường của chuyến đi

Để biết thêm thông tin về cách ghi lại các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Hướng dẫn sự kiện phong phú trong ứng dụng</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events_ride_hailing_app_user_journey" src="https://files.readme.io/0224faa0b16301b04b33ae308e8e18e8cb5eb90aa12ff5cf76d819e80587e224-360020064517.png" />

## Cấu trúc đề xuất cho các sự kiện đã xác định trước

Phần sau đây cung cấp danh sách các cấu trúc sự kiện điển hình cho ngành dịch vụ gọi xe. Mỗi cấu trúc bao gồm một tên sự kiện đã xác định trước và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Hoàn tất đăng ký (af_complete_registration)">

**Mục đích**

Sự kiện này có thể giúp bạn:

* Tìm hiểu những phương thức đăng ký mà người dùng của bạn ưa thích
* Biết được số lượng người dùng thực sự đăng ký sau khi tải xuống và cài đặt ứng dụng
* Xem xu hướng đăng ký ở các quốc gia để xác định các quốc gia có số lượng người dùng có nhiều khả năng sử dụng ứng dụng của bạn nhiều nhất.

**Kích hoạt**

Thời điểm người dùng hoàn tất quá trình đăng ký

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_registration\_method | Nền tảng hoặc phương thức mà người dùng đăng ký | Facebook |
| country\_code | Mã quốc gia (mã điện thoại) | 66 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REGSITRATION_METHOD, "shoes");
eventValue.put("country_code", "66");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.COMPLETE_REGISTRATION, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventCompleteRegistration
withValues: @{
  AFEventParamRegistrationMethod: @"Facebook",
  @"country_code": @"66",
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventCompleteRegistration, 
withValues: [
  AFEventParamRegistrationMethod: "Facebook",
	  "country_code": "66"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CompleteRegistrationEvent = new Dictionary<string, string>();
CompleteRegistrationEvent.Add("af_registration_method", "Facebook");
CompleteRegistrationEvent.Add("country_code", "66");
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

<Accordion title="Thêm thông tin thanh toán (af_add_payment_info)">

**Mục đích**

Giúp bạn phân loại người dùng. Bạn có thể:

* Tìm hiểu thời gian cần thiết để người dùng thêm thông tin thanh toán của họ
* Phương thức thanh toán nào phổ biến nhất, ví dụ, thẻ tín dụng hoặc Ví điện tử
* Thiết lập chiến dịch và cộng tác với các nhà cung cấp phương thức thanh toán phổ biến

**Kích hoạt**

Thời điểm người dùng thêm thành công thông tin thanh toán vào tài khoản của họ

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_success | Phương thức thanh toán có thành công hay không | true |
| credit\_card\_type | Loại thẻ tín dụng (tùy chọn) | Visa, Mastercard |
| payment\_method\_type | Loại phương thức thanh toán | thẻ tín dụng, ví điện tử |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.SUCCESS, true);
eventValue.put("credit_card_type", "Visa");
eventValue.put("payment_method_type", true);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.ADD_PAYMENT_INFO, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventAddPaymentInfo
withValues: @{
  AFEventParamSuccess: @TRUE,
	  @"credit_card_type": @"Visa",
	  @"payment_method_type": @"credit card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventAddPaymentInfo, withValues: [
  AFEventParamSuccess: true,
	  "credit_card_type": "Visa",
	  "payment_method_type": "credit card"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> AddPaymentInfoEvent = new Dictionary<string, string>();
AddPaymentInfoEvent.Add("af_success", "true");
AddPaymentInfoEvent.Add("credit_card_type", "Visa");
AddPaymentInfoEvent.Add("payment_method_type", "credit card");
AppsFlyer.sendEvent("af_add_payment_info", AddPaymentInfoEvent);
```

</Tab>
</Tabs>

</Accordion>

## Cấu trúc đề xuất cho các sự kiện tùy chỉnh

Phần sau cung cấp danh sách các cấu trúc sự kiện bao gồm tên sự kiện tùy chỉnh và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Đã yêu cầu đặt xe (ride_booking_requested)">

**Mục đích**

Sự kiện này có thể giúp bạn:

* Tìm hiểu về các điểm đến phổ biến.
* Tìm hiểu về các xu hướng, điểm đến và điểm xuất phát
* Xem quãng đường trung bình của một chuyến đi
* Xem hầu hết người dùng đến từ những thành phố, vùng và quốc gia nào

Ngoài ra, việc ghi nhận sự kiện này cùng với các sự kiện khác liên quan đến đặt xe có thể giúp bạn ghi nhận các giao dịch thành công. Sau đó, bạn có thể so sánh giao dịch thành công với giao dịch không thành công. Ví dụ, bạn có thể xem số lượt đặt chuyến đi được yêu cầu và số lượt đặt chuyến đi hoàn thành hoặc bị hủy.

**Kích hoạt**

Thời điểm hành khách tạo yêu cầu đặt xe

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Giá công bố cho chuyến đi | 22.4 |
| af\_currency | Tiền tệ | SGD |
| af\_destination\_a | Điểm khởi hành | Plaza Singapura |
| af\_destination\_b | Điểm đến | Marina Bay Sands |
| distance | Khoảng cách giữa hai điểm đến | 5.2 |
| af\_content\_type | Loại phương tiện | Taxi |
| payment\_method\_type | Loại phương thức thanh toán | thẻ tín dụng, ví điện tử |
| af\_city | Thành phố nơi hành khách đặt chuyến xe | Singapore |
| af\_region | Khu vực nơi hành khách đặt chuyến xe | SFA |
| af\_country | Quốc gia nơi hành khách đặt chuyến xe | Singapore |
| order\_id | ID đặt xe | 135790 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 22.4);
eventValue.put(AFInAppEventParameterName.CURRENCY, "SGD");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "Plaza Singapura");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Marina Bay Sands");
eventValue.put("distance", 5.2);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "Taxi");
eventValue.put("payment_method_type", "credit card");
eventValue.put("notes", "Taxi stand");
eventValue.put(AFInAppEventParameterName.CITY, "Singapore");
eventValue.put(AFInAppEventParameterName.REGION, "SFA");
eventValue.put(AFInAppEventParameterName.COUNTRY, "Singapore");
eventValue.put("af_order_id", "135790");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "ride_booking_requested", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"ride_booking_requested"
withValues: @{
  AFEventParamPrice: @22.4,
  AFEventParamCurrency: @"SGD",
  AFEventParamDestinationA: @"Plaza Singapura",
  AFEventParamDestinationB: @"Marina Bay Sands",
  @"distance": @5.2,
  AFEventParamContentType: @"Taxi",
  @"payment_method_type": @"credit card",
	  @"notes": @"Taxi stand",
  AFEventParamCity: @"Singapore",
  AFEventParamRegion: @"SFA",
  AFEventParamCountry: @"Singapore",
  AFEventParamOrderId: @"135790"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("ride_booking_requested", 
withValues: [
 AFEventParamPrice: 22.4,
	 AFEventParamCurrency: "SGD",
	 AFEventParamDestinationA: "Plaza Singapura",
	 AFEventParamDestinationB: "Marina Bay Sands",
	 "distance": 5.2,
	 AFEventParamContentType: "Taxi",
	 "payment_method_type": "credit card",
	 "notes": "Taxi stand",
	 AFEventParamCity: "Singapore",
	 AFEventParamRegion: "SFA",
	 AFEventParamCountry: "Singapore",
	 AFEventParamOrderId: "135790"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RideBookingRequestedEvent = new Dictionary<string, string>();
RideBookingRequestedEvent.Add("af_price", "22.4");
RideBookingRequestedEvent.Add("af_currency", "SGD");
RideBookingRequestedEvent.Add("af_destination_a", "Plaza Singapura");
RideBookingRequestedEvent.Add("af_destination_b", "Marina Bay Sands");
RideBookingRequestedEvent.Add("distance", "5.2");
RideBookingRequestedEvent.Add("af_content_type", "Taxi");
RideBookingRequestedEvent.Add("payment_method_type", "credit card");
RideBookingRequestedEvent.Add("notes", "Taxi stand");
RideBookingRequestedEvent.Add("af_city", "Singapore");
RideBookingRequestedEvent.Add("af_region", "SFA");
RideBookingRequestedEvent.Add("af_country", "Singapore");
RideBookingRequestedEvent.Add("af_order_id", "135790");
AppsFlyer.sendEvent("ride_booking_requested", RideBookingRequestedEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đã xác nhận đặt xe (ride_booking_confirmed)">

**Mục đích**

Sự kiện này có thể giúp bạn:

* Tìm hiểu xem ai là những người lái xe tích cực nhất
* Xem những điểm đến phổ biến với các lái xe
* Xem giá chuyến đi trung bình và giá tổng thể đối với mỗi người lái xe

Ngoài ra, việc ghi nhận sự kiện này cùng với ba sự kiện khác liên quan đến đặt xe có thể giúp bạn hiểu rõ hơn về hoạt động của người lái xe. Ví dụ, bạn có thể xem tài xế nào xác nhận nhiều yêu cầu đặt xe nhất và tài xế nào chọn chuyến ngắn thay vì chuyến dài.

#### **Kích hoạt**

Thời điểm lượt đặt xe được tài xế chấp nhận

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Giá công bố cho chuyến đi | 22.4 |
| af\_currency | Tiền tệ | SGD |
| af\_destination\_a | Điểm khởi hành | Plaza Singapura |
| af\_destination\_b | Điểm đến | Marina Bay Sands |
| distance | Khoảng cách giữa hai điểm đến | 5.2 |
| af\_content\_type | Loại phương tiện | Taxi |
| driver\_id | ID của tài xế xác nhận thực hiện chuyến đi | 1706 |
| payment\_method\_type | Loại phương thức thanh toán | thẻ tín dụng, ví điện tử |
| af\_city | Thành phố nơi hành khách đặt chuyến xe | Singapore |
| af\_region | Khu vực nơi hành khách đặt chuyến xe | SFA |
| af\_country | Quốc gia nơi hành khách đặt chuyến xe | Singapore |
| af\_order\_id | ID đặt xe | 135790 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 22.4);
eventValue.put(AFInAppEventParameterName.CURRENCY, "SGD");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "Plaza Singapura");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Marina Bay Sands");
eventValue.put("distance", 5.2);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "Taxi");
eventValue.put("driver_id", "1706");
eventValue.put("payment_method_type", "credit card");
eventValue.put("notes", "Taxi stand");
eventValue.put(AFInAppEventParameterName.CITY, "Singapore");
eventValue.put(AFInAppEventParameterName.REGION, "SFA");
eventValue.put(AFInAppEventParameterName.COUNTRY, "Singapore");
eventValue.put("af_order_id", "135790");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "ride_booking_confirmed", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"ride_booking_confirmed"
withValues: @{
 AFEventParamPrice: @22.4,
 AFEventParamCurrency: @"SGD",
 AFEventParamDestinationA: @"Plaza Singapura",
 AFEventParamDestinationB: @"Marina Bay Sands",
 @"distance": @5.2,
 AFEventParamContentType: @"Taxi",
	 @"driver_id": @"1706",
 @"payment_method_type": @"credit card",
	 @"notes": @"Taxi stand",
 AFEventParamCity: @"Singapore",
 AFEventParamRegion: @"SFA",
 AFEventParamCountry: @"Singapore",
 AFEventParamOrderId: @"135790"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("ride_booking_confirmed", 
withValues: [
 AFEventParamPrice: 22.4,
 AFEventParamCurrency: "SGD",
 AFEventParamDestinationA: "Plaza Singapura",
 AFEventParamDestinationB: "Marina Bay Sands",
 "distance": 5.2,
 AFEventParamContentType: "Taxi",
 "driver_id": "1706",
 "payment_method_type": "credit card",
 "notes": "Taxi stand",
 AFEventParamCity: "Singapore",
 AFEventParamRegion: "SFA",
 AFEventParamCountry: "Singapore", 
 AFEventParamOrderId: "135790"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RideBookingConfirmedEvent = new Dictionary<string, string>();
RideBookingConfirmedEvent.Add("af_price", "22.4");
RideBookingConfirmedEvent.Add("af_currency", "SGD");
RideBookingConfirmedEvent.Add("af_destination_a", "Plaza Singapura");
RideBookingConfirmedEvent.Add("af_destination_b", "Marina Bay Sands");
RideBookingConfirmedEvent.Add("distance", "5.2");
RideBookingConfirmedEvent.Add("af_content_type", "Taxi");
RideBookingConfirmedEvent.Add("driver_id", "1706");
RideBookingConfirmedEvent.Add("payment_method_type", "credit card");
RideBookingConfirmedEvent.Add("notes", "Taxi stand");
RideBookingConfirmedEvent.Add("af_city", "Singapore");
RideBookingConfirmedEvent.Add("af_region", "SFA");
RideBookingConfirmedEvent.Add("af_country", "Singapore");
RideBookingConfirmedEvent.Add("af_order_id", "135790");
AppsFlyer.sendEvent("ride_booking_confirmed", RideBookingConfirmedEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đã hủy đặt xe (ride_booking_canceled)">

**Mục đích**

Sự kiện này có thể giúp bạn:

* Ghi lại những lái xe hoặc hành khách thường xuyên hủy chuyến
* Tìm hiểu xem có bao nhiêu chuyến đi bị hủy
* Liên hệ tỷ lệ hủy với các thuộc tính như giá, điểm đến, quãng đường và thành phố
* Tìm hiểu lý do tại sao chuyến đi bị hủy

**Kích hoạt**

Thời điểm lượt đặt xe bị hủy

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Giá công bố cho chuyến đi | 22.4 |
| af\_currency | Tiền tệ | SGD |
| af\_destination\_a | Điểm khởi hành | Plaza Singapura |
| af\_destination\_b | Điểm đến | Marina Bay Sands |
| distance | Khoảng cách giữa hai điểm đến | 5.2 |
| af\_content\_type | Loại phương tiện | Taxi |
| driver\_id | ID của tài xế xác nhận thực hiện chuyến đi | 1706 |
| cancelation\_reason | Lý do chuyến đi bị hủy | giá quá cao, tài xế không xuất hiện, hành khách không xuất hiện |
| payment\_method\_type | Loại phương thức thanh toán | thẻ tín dụng, ví điện tử |
| af\_city | Thành phố nơi hành khách đặt chuyến xe | Singapore |
| af\_region | Khu vực nơi hành khách đặt chuyến xe | SFA |
| af\_country | Quốc gia nơi hành khách đặt chuyến xe | Singapore |
| order\_id | ID đặt xe | 135790 |
| canceled\_by | Chuyến đi bị hủy bởi hành khách hay lái xe | Hành khách |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 22.4);
eventValue.put(AFInAppEventParameterName.CURRENCY, "SGD");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "Plaza Singapura");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Marina Bay Sands");
eventValue.put("distance", 5.2);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "Taxi");
eventValue.put("driver_id", "1706");
eventValue.put("cancellation_reason", "driver didn't show up");
eventValue.put("payment_method_type", "credit card");
eventValue.put("notes", "Taxi stand");
eventValue.put(AFInAppEventParameterName.CITY, "Singapore");
eventValue.put(AFInAppEventParameterName.REGION, "SFA");
eventValue.put(AFInAppEventParameterName.COUNTRY, "Singapore");
eventValue.put("af_order_id", "135790");
eventValue.put("canceled_by", "passenger");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "ride_booking_canceled", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"ride_booking_canceled"
withValues: @{
 AFEventParamPrice: @22.4,
 AFEventParamCurrency: @"SGD",
 AFEventParamDestinationA: @"Plaza Singapura",
 AFEventParamDestinationB: @"Marina Bay Sands",
 @"distance": @5.2,
 AFEventParamContentType: @"Taxi",
 @"driver_id": @"1706",
 @"cancelation_reason": @"driver didn't show up",
 @"payment_method_type": @"credit card",
 @"notes": @"Taxi stand",
 AFEventParamCity: @"Singapore",
 AFEventParamRegion: @"SFA",
 AFEventParamCountry: @"Singapore",
 AFEventParamOrderId: @"135790",
 @"canceled_by": @"passenger"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("ride_booking_canceled", 
withValues: [
 AFEventParamPrice: 22.4,
 AFEventParamCurrency: "SGD",
 AFEventParamDestinationA: "Plaza Singapura",
 AFEventParamDestinationB: "Marina Bay Sands",
 "distance": 5.2,
	 AFEventParamContentType: "Taxi",
 "driver_id": "1706",
 "cancelation_reason": "driver didn't show up",
 "payment_method_type": "credit card",
	 "notes": "Taxi stand",
 AFEventParamCity: "Singapore",
 AFEventParamRegion: "SFA",
 AFEventParamCountry: "Singapore",
 AFEventParamOrderId: "135790",
 "canceled_by": "passenger"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RideBookingCanceledEvent = new Dictionary<string, string>();
RideBookingCanceledEvent.Add("af_price", "22.4");
RideBookingCanceledEvent.Add("af_currency", "SGD");
RideBookingCanceledEvent.Add("af_destination_a", "Plaza Singapura");
RideBookingCanceledEvent.Add("af_destination_b", "Marina Bay Sands");
RideBookingCanceledEvent.Add("distance", "5.2");
RideBookingCanceledEvent.Add("af_content_type", "Taxi");
RideBookingCanceledEvent.Add("driver_id", "1706");
RideBookingCanceledEvent.Add("cancelation_reason", "driver didn't show up");
RideBookingCanceledEvent.Add("payment_method_type", "credit card");
RideBookingCanceledEvent.Add("notes", "Taxi stand");
RideBookingCanceledEvent.Add("af_city", "Singapore");
RideBookingCanceledEvent.Add("af_region", "SFA");
RideBookingCanceledEvent.Add("af_country", "Singapore");
RideBookingCanceledEvent.Add("af_order_id", "135790");
RideBookingCanceledEvent.Add("canceled_by", "passenger");
AppsFlyer.sendEvent("ride_booking_cancelled", RideBookingCanceledEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đã hoàn tất đặt xe (ride_booking_completed)">

**Mục đích**

Sự kiện này có thể giúp bạn:

* Tìm hiểu về số tiền hành khách đã trả và thu nhập của lái xe
* Liên hệ các chuyến đi đã hoàn thành với các thuộc tính như điểm đến, quãng đường, loại hình thanh toán và ID lái xe
* Xem quãng đường trung bình và quãng đường tổng thể của lái xe và hành khách
* So sánh các chuyến đi đã hoàn thành với các chuyến đi bị hủy
* Ghi lại và ghi nhận điểm số của tài xế

**Kích hoạt**

Thời điểm hành trình được hoàn thành

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Giá công bố cho chuyến đi | 22.4 |
| af\_currency | Tiền tệ | SGD |
| af\_destination\_a | Điểm khởi hành | Plaza Singapura |
| af\_destination\_b | Điểm đến | Marina Bay Sands |
| distance | Khoảng cách giữa hai điểm đến | 5.2 |
| af\_content\_type | Loại phương tiện | Taxi |
| driver\_id | ID của tài xế xác nhận thực hiện chuyến đi | 1706 |
| payment\_method\_type | Loại phương thức thanh toán | thẻ tín dụng, ví điện tử |
| af\_city | Thành phố nơi hành khách đặt chuyến xe | Singapore |
| af\_region | Khu vực nơi hành khách đặt chuyến xe | SFA |
| af\_country | Quốc gia nơi hành khách đặt chuyến xe | Singapore |
| order\_id | ID đặt xe | 135790 |
| credits\_earned | Điểm hành khách nhận được khi hoàn thành chuyến đi | 248 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 22.4);
eventValue.put(AFInAppEventParameterName.CURRENCY, "SGD");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "Plaza Singapura");
eventValue.put(AFInAppEventParameterName.DESTINATION_B,"Marina Bay Sands");
eventValue.put("distance", 5.2);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "Taxi");
eventValue.put("driver_id", "1706");
eventValue.put("payment_method_type", "credit card");
eventValue.put("notes", "Taxi stand");
eventValue.put(AFInAppEventParameterName.CITY, "Singapore");
eventValue.put(AFInAppEventParameterName.REGION, "SFA");
eventValue.put(AFInAppEventParameterName.COUNTRY, "Singapore");
eventValue.put("af_order_id", "135790");
eventValue.put("credits_earned", 248);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "ride_booking_completed" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"ride_booking_completed"
withValues: @{
  AFEventParamPrice: @22.4,
  AFEventParamCurrency: @"SGD",
  AFEventParamDestinationA: @"Plaza Singapura",
  AFEventParamDestinationB: @"Marina Bay Sands",
  @"distance": @5.2,
  AFEventParamContentType: @"Taxi",
  @"driver_id": @"1706",
  @"payment_method_type": @"credit card",
  @"notes": @"Taxi stand",
  AFEventParamCity: @"Singapore",
  AFEventParamRegion: @"SFA",
  AFEventParamCountry: @"Singapore",
  AFEventParamOrderId: @"135790",
  @"credits_earned": @248
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("ride_booking_completed", 
withValues: [
  AFEventParamPrice: 22.4,
  AFEventParamCurrency: "SGD",
  AFEventParamDestinationA: "Plaza Singapura",
  AFEventParamDestinationB: "Marina Bay Sands",
  distance": 5.2,
  AFEventParamContentType: "Taxi",
  "driver_id": "1706",
  "payment_method_type": "credit card",
  "notes": "Taxi stand",
  AFEventParamCity: "Singapore",
  AFEventParamRegion: "SFA",
  AFEventParamCountry: "Singapore",
  AFEventParamOrderId: "135790",
  "credits_earned": 248
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> RideBookingCompletedEvent = new Dictionary<string, string>();
RideBookingCompletedEvent.Add("af_price", "22.4");
RideBookingCompletedEvent.Add("af_currency", "SGD");
RideBookingCompletedEvent.Add("af_destination_a", "Plaza Singapura");
RideBookingCompletedEvent.Add("af_destination_b", "Marina Bay Sands");
RideBookingCompletedEvent.Add("distance", "5.2");
RideBookingCompletedEvent.Add("af_content_type", "Taxi");
RideBookingCompletedEvent.Add("driver_id", "1706");
RideBookingCompletedEvent.Add("payment_method_type", "credit card");
RideBookingCompletedEvent.Add("notes", "Taxi stand");
RideBookingCompletedEvent.Add("af_city", "Singapore");
RideBookingCompletedEvent.Add("af_region", "SFA");
RideBookingCompletedEvent.Add("af_country", "Singapore");
RideBookingCompletedEvent.Add("af_order_id", "135790");
AppsFlyer.sendEvent("ride_booking_completed", RideBookingCompletedEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Số điểm đã sử dụng (used_credits)">

**Mục đích**

[Sự kiện hoàn tất đặt xe](/docs/recommended-ride-hailing-app-events#ride-booking-completed-ride_booking_completed) bao gồm một thông số có tên là `credits_earned`. Thông số này ghi lại các số điểm mà hành khách kiếm được cho mỗi chuyến đi. Hành khách có thể đổi điểm để lấy phiếu giảm giá và chiết khấu.

Sự kiện này có thể giúp bạn:

* Xem có bao nhiêu hành khách đổi điểm lấy phiếu giảm giá
* Xem loại phiếu giảm giá và chiết khấu mà hành khách yêu thích

**Kích hoạt**

Thời điểm hành khách sử dụng điểm

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_content | loại phiếu giảm giá hoặc chiết khấu | Vé xem phim một người |
| credits\_used | Số điểm đã sử dụng | 1000 |
| credits\_remaining | Số điểm còn lại trong tài khoản | 2090 |
| invoice\_id | ID hóa đơn của hóa đơn được tạo khi sử dụng điểm | KO215123SD |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT, "Single movie ticket");
eventValue.put("credits_used", 1000);
eventValue.put("invoice_id", "");
eventValue.put("credits_remaining", "KO215123SD");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "spent_credits" , eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"spent_credits"
withValues: @{
 AFEventParamContent: @"Single movie ticket",
 @"credits_used": @1000,
 @"credits_remaining": @2090,
 @"invoice_id": @"KO215123SD"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("spent_credits", 
withValues: [
 AFEventParamContent: "Single movie ticket",
 "credits_used": 1000,
 "credits_remaining": 2090,
 "invoice_id": "KO215123SD"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CreditsSpent = new Dictionary<string, string>();
CreditsSpent.Add("af_content", "Single movie ticket");
CreditsSpent.Add("credits_used", "1000");
CreditsSpent.Add("credits_remaining", "2090");
CreditsSpent.Add("invoice_id", "KO215123SD");
AppsFlyer.sendEvent("af_content_view", CreditsSpent);
```

</Tab>
</Tabs>

</Accordion>
