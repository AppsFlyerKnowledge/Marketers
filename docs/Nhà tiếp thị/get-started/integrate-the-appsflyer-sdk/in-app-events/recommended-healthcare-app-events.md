---
title: Các sự kiện ứng dụng chăm sóc sức khỏe được đề xuất
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
  created_at: '2021-05-01T10:41:05Z'
  edited_at: '2022-01-25T17:23:38Z'
  id: 360019888518
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/360019888518
---
> **Khái quát:** Đo lường chất lượng của người dùng trong suốt hành trình người dùng của họ bằng cách ghi nhận các sự kiện trong ứng dụng được đề xuất này cho ứng dụng chăm sóc sức khỏe của bạn.

## <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="100px" /> Chăm sóc sức khỏe

Các ứng dụng chăm sóc sức khỏe cho phép người dùng thực hiện những thao tác như mua bảo hiểm y tế, đặt lịch hẹn và nhận tư vấn y tế. Các sự kiện tiêu biểu mà chúng tôi đề xuất ghi nhận bao gồm mua hàng và đặt trước.

Việc ghi nhận các sự kiện có thể giúp bạn xác định:

* Thuốc nào là cần thiết và có nhiều nhu cầu nhất
* Người dùng quan tâm đến gói nào
* Những vấn đề y tế nào mà người dùng quan tâm nhất

Để biết thêm thông tin về cách ghi lại các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Hướng dẫn sự kiện phong phú trong ứng dụng</Anchor>.

<Image align="center" alt="Flowchart_for_recommended_events healthcare_app_user_journey" src="https://files.readme.io/9ac30fd9bcc8a67e2eed66ae9786e581fa152deda67aca8f8b1f0394ccb16384-360020171758.png" />

## Cấu trúc đề xuất cho các sự kiện đã xác định trước

Phần sau đây cung cấp danh sách các cấu trúc sự kiện tiêu biểu cho ngành chăm sóc sức khỏe. Mỗi cấu trúc bao gồm một tên sự kiện đã xác định trước và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

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
eventValue.put(AFInAppEventParameterName.REGISTRATION_METHOD, "Facebook");
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
AppsFlyer.sendEvent ("af_complete_registration", CompleteRegistrationEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Thêm vào giỏ hàng (af_add_to_cart)">

**Mục đích**

Ghi nhận khi người dùng thêm một sản phẩm vào giỏ hàng của họ. Sự kiện này có thể giúp bạn xác định:

* Xem số lượng sản phẩm trung bình mà người mua thêm vào trong một lần mua hàng
* Khoảng thời gian giữa hai lần thêm vào sản phẩm khác nhau
* Số lượng người mua từ bỏ giỏ hàng của họ

**Kích hoạt**

Thời điểm người dùng thêm một sản phẩm vào giỏ hàng

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| tên thuốc | Tên của thuốc | rhinos |
| af\_quantity | Số lượng đặt hàng | 1 |
| af\_price | Giá của thuốc | 10 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("medicine name", "rhinos");
eventValue.put("quantity", "1");
eventValue.put("price", "10");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "add_to_cart", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"add_to_cart" withValues: @{ 
@"medicine name": @"rhinos", 
@"quantity": @"1", 
@"price": @"10"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("add_to_cart", withValues: 
[ "medicine name": "rhinos",
"quantity": "1",
"price": "10"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> AddToCartEvent= new Dictionary<string, string>();
AddToCartEvent.Add("medicine name", "rhinos");
AddToCartEvent.Add("quantity", "1");
AddToCartEvent.Add("price", "10");
AppsFlyer.sendEvent ("add_to_cart", AddToCartEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Mua hàng (af_purchase)">

**Mục đích**

Ghi nhận các giao dịch mua trong ứng dụng do người dùng thực hiện. Sự kiện này có thể giúp bạn:

* Xác định LTV của người dùng và ROI của các chiến dịch của bạn trên các mạng quảng cáo và các đại lý quảng cáo
* Xác định những ưu đãi nào được người dùng chọn nhiều nhất
* Chiến dịch tham chiếu chéo với các mặt hàng đã mua để tối ưu hóa nhắm mục tiêu chiến dịch

**Kích hoạt**

Thời điểm người dùng truy cập trang cảm ơn sau khi mua hàng thành công

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Doanh thu từ giao dịch mua | 50.55 |
| af\_currency | Mã tiền tệ | USD |
| af\_content\_type | Tên của giao dịch mua | phòng thí nghiệm |
| af\_order\_id | ID đặt xe | 9277 |
| payment\_method\_type | Phương thức thanh toán đã sử dụng | thẻ tín dụng, nội địa |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put(AFInAppEventParameterName.REVENUE, 50.55);
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "lab");
eventValue.put("AFInAppEventParameterName.ORDER_ID", "9277");
eventValue.put("payment_method_type", "credit card");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),AFInAppEventType.PURCHASE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventPurchase
withValues: @{
   AFEventParamRevenue: @50.55,
   AFEventParamCurrency: @"USD",
   AFEventParamContentType: @"lab",
   AFEventParamContentTypeOrderId: @"9277",
   @"payment_method_type": @"credit card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventPurchase, 
withValues: [
   AFEventParamRevenue: 50.55,
   AFEventParamCurrency: "USD",
   AFEventParamContentType: "lab",
   AFEventParamContentTypeOrderId: "9277",
   "payment_method_type": "credit card",
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> purchaseEvent = new Dictionary<string, string>();
purchaseEvent.Add("af_revenue", "50.55");
purchaseEvent.Add("af_currency", "USD");
purchaseEvent.Add("af_content_type", "lab");
purchaseEvent.Add("af_order_id", "9277");
purchaseEvent.Add("payment_method_type", "credit card");
AppsFlyer.sendEvent ("af_purchase", purchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Giao dịch nạp tiền thành công (af_top_up_success)">

**Mục đích**

Tiền nạp có thể được sử dụng để mua bất cứ gói hoặc dịch vụ nào được cung cấp bên trong ứng dụng. Bạn có thể ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu số tiền mà mọi người sẵn sàng nạp vào tài khoản của họ và sử dụng số tiền nạp để nhắm mục tiêu người dùng với các chiến dịch tùy chỉnh nằm trong khoảng ngân sách nạp của họ.

**Kích hoạt**

Thời điểm người dùng hoàn tất giao dịch nạp tiền

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Số tiền nạp | 2000.55 |
| top\_up\_id | ID giao dịch nạp tiền | 397 |
| payment\_method\_type | Phương thức thanh toán đã sử dụng | thẻ tín dụng, thanh toán nội địa |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();  
eventValue.put(AFInAppEventParameterName.REVENUE, 2000.55);
eventValue.put("TOP_UP_ID", "397");
eventValue.put("PAYMENT_METHOD_TYPE", "creditcard");  
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.AF_TOP_UP_SUCCESS, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventTopUpSuccess
withValues: @{
  AFEventParamRevenue: @2000.55,   
   @"top_up_id": @"397",
   @"payment_method_type": @"credit card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventTopUpSuccess, 
withValues: [
   AFEventParamRevenue: 2000.55,   
   "top_up_id": "397",
   "payment_method_type": "credit card",
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> TopUpSuccessEvent = new Dictionary<string, string>();
TopUpSuccessEvent.Add("af_revenue", "2000.55");
TopUpSuccessEvent.Add("top_up_id", "397");
TopUpSuccessEvent.Add("payment_method_type", "credit card");
AppsFlyer.sendEvent ("af_top_up_success", TopUpSuccessEvent);
```

</Tab>
</Tabs>

</Accordion>

## Cấu trúc đề xuất cho các sự kiện tùy chỉnh

Phần sau cung cấp danh sách các cấu trúc sự kiện bao gồm tên sự kiện tùy chỉnh và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Cuộc hẹn đã xác nhận (confirmed_appointment)">

**Mục đích**

Bằng cách ghi nhận sự kiện này, bạn có thể sử dụng dữ liệu để nhắm mục tiêu lại người dùng và gửi lời nhắc về việc kiểm tra sức khỏe định kỳ và các cuộc hẹn trong tương lai.

**Kích hoạt**

Khi người dùng đặt lịch hẹn

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| tên bác sĩ | Tên của bác sĩ | Robert James |
| số cuộc hẹn | Số của cuộc hẹn | 001 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("doctor name", "Robert James");
eventValue.put("appointment number", "001");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "confirmed_appointment", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"confirmed_appointment" withValues: @{ 
@"doctor name": @"Robert James", 
@"appointment number": @"001"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("confirmed_appointment", withValues: 
[ "doctor name": "Robert James",
"appointment number": "001"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ConfirmedAppointmentEvent= new Dictionary<string, string>();
ConfirmedAppointmentEvent.Add("doctor name", "Robert James");  
ConfirmedAppointmentEvent.Add("appointment number", "001");
AppsFlyer.sendEvent ("confirmed_appointment", ConfirmedAppointmentEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Cuộc hẹn đã hủy (canceled_appointment)">

**Mục đích**

Bằng cách ghi nhận sự kiện này, bạn có thể sử dụng dữ liệu để nhắm mục tiêu lại người dùng và gửi lời nhắc để lên lịch lại các cuộc hẹn.

**Kích hoạt**

Khi người dùng hủy cuộc hẹn

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| tên bác sĩ | Tên của bác sĩ | Robert James |
| số cuộc hẹn | Số của cuộc hẹn | 001 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("doctor name", "Robert James");
eventValue.put("appointment number", "001");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "canceled_appointment", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"canceled_appointment" withValues: @{ 
@"doctor name": @"Robert James", 
@"appointment number": @"001"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("canceled_appointment", withValues: 
[ "doctor name": "Robert James",
"appointment number": "001"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> CanceledAppointmentEvent= new Dictionary<string, string>();
CanceledAppointmentEvent.Add("doctor name", "Robert James");  
CanceledAppointmentEvent.Add("appointment number", "001");
AppsFlyer.sendEvent ("canceled_appointment", CanceledAppointmentEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đặt lịch hẹn đầu tiên với bác sĩ (doctor_first_booking)">

**Mục đích**

Bằng cách ghi nhận sự kiện này, bạn có thể sử dụng dữ liệu để gửi cho người dùng các chương trình khuyến mãi và nhắm mục tiêu lại quảng cáo.

**Kích hoạt**

Khi người dùng đặt lịch cho cuộc hẹn đầu tiên

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| tên bác sĩ | Tên của bác sĩ | Robert James |
| chuyên môn | Chuyên môn y tế | khoa thần kinh |
| thời lượng | Thời lượng của cuộc hẹn | trò chuyện 30 phút |
| price | Giá của cuộc hẹn | 50 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("doctor name", "Robert James");
eventValue.put("specialty", "neurology");
eventValue.put("duration", "30 min chat");
eventValue.put("price", "50");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "doctor_first_booking", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"doctor_first_booking" withValues: @{ 
@"doctor name": @"Robert James", 
@"specialty": @"neurology", 
@"duration": @"30 min chat", 
@"price": @"50"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("doctor_first_booking", withValues: 
[ "doctor name": "Robert James",
"specialty": "neurology",
"duration": "30 min chat",
"price": "50"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> DoctorFirstBookingEvent= new Dictionary<string, string>();
DoctorFirstBookingEvent.Add("doctor name", "Robert James");
DoctorFirstBookingEvent.Add("appointment number", "001");
DoctorFirstBookingEvent.Add("duration", "30 min chat");
DoctorFirstBookingEvent.Add("price", "50");
AppsFlyer.sendEvent ("doctor_first_booking", DoctorFirstBookingEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Cuộc hẹn xét nghiệm đầu tiên (lab_first_appointment)">

**Mục đích**

Bằng cách ghi nhận sự kiện này, bạn có thể sử dụng dữ liệu để gửi cho người dùng các chương trình khuyến mãi và nhắm mục tiêu lại quảng cáo.

**Kích hoạt**

Khi người dùng đặt lịch cho cuộc hẹn đầu tiên

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| lựa chọn phòng thí nghiệm | Tên xét nghiệm | khám toàn thân |
| quantity | Số lượng đặt hàng | 2 |
| price | Giá của phòng thí nghiệm | 500 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("lab selection", "full body checkup");
eventValue.put("quantity", "2");
eventValue.put("price", "500");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "lab_first_appointment", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"lab_first_appointment" withValues: @{ 
@"lab_selection": @"full body checkup", 
@"quantity": @"2", 
@"price": @"500"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("lab_first_appointment", withValues: 
[ "lab selection": "full body checkup",
"quantity": "2",
"price": "500"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LabFirstAppointmentEvent= new Dictionary<string, string>();
LabFirstAppointmentEvent.Add("lab selection", "full body checkup");
LabFirstAppointmentEvent.Add("quantity", "2");
LabFirstAppointmentEvent.Add("price", "500");
AppsFlyer.sendEvent ("lab_first_appointment", LabFirstAppointmentEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Lần mua thuốc đầu tiên (pharmacy_first_purchase)">

**Mục đích**

Bằng cách ghi nhận sự kiện này, bạn có thể sử dụng dữ liệu để gửi cho người dùng các chương trình khuyến mãi và nhắm mục tiêu lại quảng cáo.

**Kích hoạt**

Khi người dùng thực hiện giao dịch mua đầu tiên

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| tên thuốc | Tên của thuốc | rhinos |
| quantity | Số lượng đặt hàng | 1 |
| price | Giá của thuốc | 10 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("medicine name", "rhinos");
eventValue.put("quantity", "1");
eventValue.put("price", "10");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "pharmacy_first_purchase", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"pharmacy_first_purchase" withValues: @{ 
@"medicine name": @"rhinos", 
@"quantity": @"1", 
@"price": @"10"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("pharmacy_first_purchase", withValues: 
[ "medicine name": "rhinos",
"quantity": "1",
"price": "10"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> PharmacyFirstPurchaseEvent= new Dictionary<string, string>();
PharmacyFirstPurchaseEvent.Add("medicine name", "rhinos");
PharmacyFirstPurchaseEvent.Add("quantity", "1");
PharmacyFirstPurchaseEvent.Add("price", "10");
AppsFlyer.sendEvent ("pharmacy_first_purchase", PharmacyFirstPurchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đặt lịch hẹn với bác sĩ (doctor_booking)">

**Mục đích**

Tìm hiểu thêm thông tin về nhu cầu và sở thích của người dùng.

**Kích hoạt**

Khi người dùng đặt lịch hẹn trực tiếp

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| tên bác sĩ | Tên của bác sĩ | Robert James |
| chuyên môn | Chuyên môn y tế | khoa thần kinh |
| thời lượng | Khoảng thời gian tiến hành cuộc hẹn | trò chuyện 30 phút |
| price | Giá của cuộc hẹn | 50 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("doctor name", "Robert James");
eventValue.put("specialty", "neurology");
eventValue.put("duration", "30 min chat");
eventValue.put("price", "50");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "doctor_booking", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"doctor_booking" withValues: @{ 
@"doctor name": @"Robert James", 
@"specialty": @"neurology", 
@"duration": @"30 min chat", 
@"price": @"50"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("doctor_booking", withValues: 
[ "doctor name": "Robert James",
"specialty": "neurology",
"duration": "30 min chat",
"price": "50"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> DoctorBookingEvent= new Dictionary<string, string>();
DoctorBookingEvent.Add("doctor name", "Robert James");
DoctorBookingEvent.Add("appointment number", "001");
DoctorBookingEvent.Add("duration", "30 min chat");
DoctorBookingEvent.Add("price", "50");
AppsFlyer.sendEvent ("doctor_booking", DoctorBookingEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Trao đổi với bác sĩ (chat_doctor)">

**Mục đích**

Tìm hiểu thêm thông tin về nhu cầu và sở thích của người dùng.

**Kích hoạt**

Khi người dùng đặt trước

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| tên bác sĩ | Tên của bác sĩ | Robert James |
| chuyên môn | Chuyên môn y tế | khoa thần kinh |
| thời lượng | Khoảng thời gian tiến hành cuộc hẹn | trò chuyện 30 phút |
| price | Giá của cuộc hẹn | 50 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("doctor name", "Robert James");
eventValue.put("specialty", "neurology");
eventValue.put("duration", "30 min chat");
eventValue.put("price", "50");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "chat_doctor", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"chat_doctor" withValues: @{ 
@"doctor name": @"Robert James", 
@"specialty": @"neurology", 
@"duration": @"30 min chat", 
@"price": @"50"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("chat_doctor", withValues: 
[ "doctor name": "Robert James",
"specialty": "neurology",
"duration": "30 min chat",
"price": "50"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ChatDoctorEvent= new Dictionary<string, string>();
ChatDoctorEvent.Add("doctor name", "Robert James");
ChatDoctorEvent.Add("appointment number", "001");
ChatDoctorEvent.Add("duration", "30 min chat");
ChatDoctorEvent.Add("price", "50");
AppsFlyer.sendEvent ("chat_doctor", ChatDoctorEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Cuộc hẹn xét nghiệm (lab_appointment)">

**Mục đích**

Bằng cách ghi nhận sự kiện này, bạn có thể sử dụng dữ liệu để gửi cho người dùng các chương trình khuyến mãi và nhắm mục tiêu lại quảng cáo.

**Kích hoạt**

Khi người dùng đặt lịch hẹn xét nghiệm

Thông số sự kiện

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| lựa chọn phòng thí nghiệm | Tên của loại phòng thí nghiệm | khám toàn thân |
| quantity | Số lượng đặt hàng | 2 |
| price | Giá của phòng thí nghiệm | 500 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("lab selection", "full body checkup");
eventValue.put("quantity", "2");
eventValue.put("price", "500");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "lab_appointment", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"lab_appointment" withValues: @{ 
@"lab_selection": @"full body checkup", 
@"quantity": @"2", 
@"price": @"500"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("lab_appointment", withValues: 
[ "lab selection": "full body checkup",
"quantity": "2",
"price": "500"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> LabAppointmentEvent= new Dictionary<string, string>();
LabAppointmentEvent.Add("lab selection", "full body checkup");
LabAppointmentEvent.Add("quantity", "2");
LabAppointmentEvent.Add("price", "500");
AppsFlyer.sendEvent ("lab_appointment", LabAppointmentEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Mua thuốc (pharmacy_purchase)">

**Mục đích**

Bằng cách ghi nhận sự kiện này, bạn có thể sử dụng dữ liệu để gửi cho người dùng các chương trình khuyến mãi và nhắm mục tiêu lại quảng cáo.

**Kích hoạt**

Khi người dùng mua thuốc

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| tên thuốc | Tên của thuốc | rhinos |
| quantity | Số lượng đặt hàng | 1 |
| price | Giá của thuốc | 10 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("medicine name", "rhinos");
eventValue.put("quantity", "1");
eventValue.put("price", "10");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "pharmacy_purchase", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"pharmacy_purchase" withValues: @{ 
@"medicine name": @"rhinos", 
@"quantity": @"1", 
@"price": @"10"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("pharmacy_purchase", withValues: 
[ "medicine name": "rhinos",
"quantity": "1",
"price": "10"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> PharmacyPurchaseEvent= new Dictionary<string, string>();
PharmacyPurchaseEvent.Add("medicine name", "rhinos");
PharmacyPurchaseEvent.Add("quantity", "1");
PharmacyPurchaseEvent.Add("price", "10");
AppsFlyer.sendEvent ("pharmacy_purchase", PharmacyPurchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Tư cách thành viên bảo hiểm (insurance_membership)">

**Mục đích**

Tìm hiểu thêm về người dùng của bạn và sau đó nhắm mục tiêu lại họ cho phù hợp.

**Kích hoạt**

Khi người dùng đăng ký bảo hiểm

Thông số sự kiện

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| tên bảo hiểm | Tên công ty bảo hiểm | DavidShield |
| loại bảo hiểm | Loại chương trình bảo hiểm | cao cấp |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("insurance name", "DavidShield");
eventValue.put("insurance type", "premium");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "insurance_membership", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"insurance_membership" withValues: @{ 
@"insurance name": @"DavidShield", 
@"insurance type": @"premium"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("insurance_membership", withValues: 
[ "insurance name": "DavidShield",
"insurance type": "premium"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> InsuranceMembershipEvent= new Dictionary<string, string>();
InsuranceMembershipEvent.Add("insurance name", "DavidShield");  
InsuranceMembershipEvent.Add("insurance type", "premium");
AppsFlyer.sendEvent ("insurance_membership", InsuranceMembershipEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Phát hành biên lai (receipt_issuance)">

**Mục đích**

Người dùng có biên lai có thể yêu cầu công ty bảo hiểm thanh toán chi phí cho cuộc hẹn với bác sĩ, xét nghiệm hoặc thuốc men. Bằng cách ghi nhận sự kiện này, bạn có thể sử dụng dữ liệu cho các chiến dịch nhắm mục tiêu lại về bao trả bảo hiểm cá nhân.

**Kích hoạt**

Khi người dùng nhận được biên lai

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| tên ứng dụng | Tên ứng dụng của bạn | Ứng dụng Chăm sóc sức khỏe |
| tên bác sĩ | Tên của bác sĩ | Robert James |
| mô tả tư vấn | Mô tả tình trạng sức khỏe | sốt |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("app name", "Healthcare App");  
eventValue.put("doctor name", "Robert James");
eventValue.put("consultation description", "fever");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "receipt_issuance", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"receipt_issuance" withValues: @{ 
@"app name": @"Healthcare App",   
@"doctor name": @"Robert James", 
@"consultation description": @"fever"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("receipt_issuance", withValues: 
[ "app name": "Healthcare App",  
"insurance name": "Robert James",
"insurance type": "fever"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ReceiptIssuanceEvent= new Dictionary<string, string>();
ReceiptIssuanceEvent.Add("app name", "Healthcare App");  
ReceiptIssuanceEvent.Add("doctor name", "Robert James");  
ReceiptIssuanceEvent.Add("consultation description", "fever");
AppsFlyer.sendEvent ("receipt_issuance", ReceiptIssuanceEvent);
```

</Tab>
</Tabs>

</Accordion>
