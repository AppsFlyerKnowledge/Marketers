---
title: Các sự kiện ứng dụng viễn thông được đề xuất
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
  created_at: '2021-05-02T11:59:16Z'
  edited_at: '2022-01-25T17:23:34Z'
  id: 360019896558
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/360019896558
---
> **Khái quát:** Đo lường chất lượng của người dùng trong suốt hành trình người dùng của họ bằng cách ghi nhận các sự kiện trong ứng dụng được đề xuất này cho ứng dụng viễn thông của bạn.

## <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="100px" /> Viễn thông

Các ứng dụng viễn thông cho phép người dùng mua và quản lý các gói đăng ký điện thoại di động, gói dữ liệu và nhiều chức năng khác. Các sự kiện tiêu biểu mà chúng tôi đề xuất ghi nhận bao gồm mua hàng, nạp tiền và đăng ký.

Việc ghi lại các sự kiện này có thể giúp bạn xác định:

* Gói cổng mạng nào phổ biến nhất
* Những sản phẩm hoặc gói nào mà người dùng có thể mua được
* Những gói nào có nhiều khả năng nhận được cam kết lâu dài từ khách hàng

Để biết thêm thông tin về cách ghi lại các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Hướng dẫn sự kiện phong phú trong ứng dụng</Anchor>.

[![Flowchart_for_recommended_events_telecommunication_app_user_journey](https://files.readme.io/f5bff70207200a0ebfdc1d1250346091f58431b280a32105a469f9b35d1c39c8-360020171878.png)](https://files.readme.io/f5bff70207200a0ebfdc1d1250346091f58431b280a32105a469f9b35d1c39c8-360020171878.png)

## Cấu trúc đề xuất cho các sự kiện đã xác định trước

Phần sau đây cung cấp danh sách các cấu trúc sự kiện tiêu biểu cho ngành viễn thông. Mỗi cấu trúc bao gồm một tên sự kiện đã xác định trước và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn

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

<Accordion title="Khung hiển thị nội dung (af_content_view)">

**Mục đích**

Xác định tỷ lệ xem các sản phẩm cụ thể và:

* Liên hệ lượt xem sản phẩm với doanh số bán sản phẩm.
* Hiểu danh mục nào là phổ biến nhất theo lượt xem sản phẩm.
* Xem mối tương quan giữa đơn vị tiền tệ của người mua và các sản phẩm mà họ xem

**Kích hoạt**

Thời điểm người dùng xem trang chi tiết của một sản phẩm cụ thể

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Giá sản phẩm | 200 |
| af\_content\_id | ID sản phẩm | 102 |
| af\_content\_type | Danh mục sản phẩm | Gói Internet |
| af\_currency | Đơn vị tiền tệ trong trang chi tiết của sản phẩm | THB, USD |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 200);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "102";
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "Internet packages");
eventValue.put(AFInAppEventParameterName.CURRENCY, "USD");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.CONTENT_VIEW, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventContentView
withValues: @{
  AFEventParamPrice: @200,
  AFEventParamContentId: @"102",
  AFEventParamContentType: @"Internet packages",
  AFEventParamCurrency: @"USD"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventContentView,
withValues: [
 AFEventParamPrice: 200,
 AFEventParamContentId: "102",
 AFEventParamContentType: "Internet packages",
 AFEventParamCurrency: "USD"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ContentViewEvent = new Dictionary<string, string>();
ContentViewEvent.Add("af_price", "200");
ContentViewEvent.Add("af_content_type", "Internet packages");
ContentViewEvent.Add("af_currency", "USD");
AppsFlyer.sendEvent("af_content_view", ContentViewEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Xem danh sách (af_list_view)">

**Mục đích**

Ghi nhận danh sách nào (ví dụ: sản phẩm mới được thêm vào, sản phẩm có liên quan hoặc sản phẩm được đề xuất) mà người mua xem nhiều nhất.

**Kích hoạt**

Thời điểm người dùng xem một danh sách cụ thể

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_content\_type | Loại danh sách | Related, recommended, new arrivals |
| af\_content\_list | Danh sách ID nội dung từ danh mục | 001, 092 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "related products");
eventValue.put(AFInAppEventParameterName.CONTENT_LIST, new String[] {"001", "092"});
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "af_list_view", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventListView
withValues: @{
  AFEventParamContentType: @"related products",
  AFEventParamContentList: @[@"001", @"092"]
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventListView,
>withValues: [
  AFEventParamContentType: "related products",
  AFEventParamContentList: ["001", "092"]
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ListViewEvent = new Dictionary<string, string>();
ListViewEvent.Add("af_content_type", "related products");
ListViewEvent.Add("af_content_list", "['001', '092']");
AppsFlyer.sendEvent("af_list_view", ListViewEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Mua hàng (af_purchase)">

**Mục đích**

Nhiều ứng dụng viễn thông cho phép người dùng mua các mục hàng như dữ liệu bổ sung. Ghi nhận sự kiện này có thể giúp bạn:

* Xác định LTV của người dùng và ROI của các chiến dịch của bạn trên các mạng quảng cáo và các đại lý quảng cáo
* Xác định những ưu đãi nào được người dùng chọn nhiều nhất
* Chiến dịch tham chiếu chéo với các mặt hàng đã mua để tối ưu hóa nhắm mục tiêu chiến dịch

**Kích hoạt**

Thời điểm người dùng truy cập trang cảm ơn sau khi mua hàng thành công

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_revenue | Doanh thu ước tính từ giao dịch mua | 2000 |
| af\_currency | Mã tiền tệ | THB |
| af\_content\_type | Tên của gói đã mua | 5G |
| af\_order\_id | ID đặt xe | 9277 |
| payment\_method\_type | Loại phương thức thanh toán | thẻ tín dụng, thanh toán nội địa |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put(AFInAppEventParameterName.REVENUE, 2000);
eventValue.put(AFInAppEventParameterName.CURRENCY, "THB");
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "5G");
eventValue.put("AFInAppEventParameterName.ORDER_ID", "9277");
eventValue.put("payment_method_type", "credit_card");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),AFInAppEventType.PURCHASE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventPurchase
withValues: @{
   AFEventParamRevenue: @2000,
   AFEventParamCurrency: @"THB",
   AFEventParamContentType: @"5G",
   AFEventParamContentTypeOrderId: @"9277",
   @"payment_method_type": @"credit_card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventPurchase, 
withValues: [
   AFEventParamRevenue: 2000,
   AFEventParamCurrency: "THB",
   AFEventParamContentType: "5G",
   AFEventParamContentTypeOrderId: "9277",
   "payment_method_type": "credit_card",
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> purchaseEvent = new Dictionary<string, string>();
purchaseEvent.Add("af_revenue", "2000");
purchaseEvent.Add("af_currency", "THB");
purchaseEvent.Add("af_content_type", "5G");
purchaseEvent.Add("af_order_id", "9277");
purchaseEvent.Add("payment_method_type", "credit_card");
AppsFlyer.sendEvent ("af_purchase", purchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Giao dịch nạp tiền thành công (af_top_up_success)">

**Mục đích**

Tiền nạp có thể được sử dụng để mua bất kỳ gói nào hoặc bất kỳ dịch vụ nào khác được cung cấp bên trong ứng dụng. Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể tìm hiểu số tiền mà người dùng sẵn sàng nạp vào tài khoản của họ và sau đó sử dụng số tiền nạp vào để nhắm mục tiêu họ với các chiến dịch tùy chỉnh trong phạm vi ngân sách của họ.

**Kích hoạt**

Thời điểm người dùng hoàn tất giao dịch nạp tiền

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_revenue | Số tiền nạp | 2000 |
| top\_up\_id | ID giao dịch nạp tiền | 397 |
| payment\_method\_type | Loại phương thức thanh toán | thẻ tín dụng, thanh toán nội địa |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();  
eventValue.put(AFInAppEventParameterName.REVENUE, 2000);
eventValue.put("TOP_UP_ID", "397");
eventValue.put("PAYMENT_METHOD_TYPE", "credit_card");  
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.AF_TOP_UP_SUCCESS, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventTopUpSuccess
withValues: @{
  AFEventParamRevenue: @2000,   
   @"top_up_id": @"397",
   @"payment_method_type": @"credit_card"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventTopUpSuccess, tele
withValues: [
   AFEventParamRevenue: 2000,   
   "top_up_id": "397",
   "payment_method_type": "credit_card",
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> TopUpSuccessEvent = new Dictionary<string, string>();
TopUpSuccessEvent.Add("af_revenue", "2000");
TopUpSuccessEvent.Add("top_up_id", "397");
TopUpSuccessEvent.Add("payment_method_type", "credit_card");
AppsFlyer.sendEvent ("af_top_up_success", TopUpSuccessEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Nạp tiền không thành công (af_top_up_unsuccessful)">

**Mục đích**

Ghi nhận sự kiện này và so sánh với dữ liệu khác để tìm hiểu thêm về người dùng của mình. Ví dụ: bạn có thể biết được có bao nhiêu người dùng cố gắng nạp tiền nhưng không thành công.

**Kích hoạt**

Khi người dùng cố gắng nạp tiền nhưng thao tác không thành công

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| error\_reason | Lý do nạp tiền không thành công | exceeded\_daily\_limit |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
              eventValue.put("error_reason", "exceeded_daily_limit");
              AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "af_top_up_unsuccessful", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"af_top_up_unsuccessful" withValues: @{ 
              @"error_reason": @"exceeded_daily_limit"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("af_top_up_unsuccessful",withValues:
              ["error_reason": "exceeded_daily_limit" ])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> TopUpUnsuccessfulEvent = new Dictionary<string, string>();
ErrorReasonEvent.Add("error_reason", "exceeded_daily_limit");  
AppsFlyer.sendEvent ("af_top_up_unsuccessful", TopUpUnsuccessfulEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đăng ký hoàn tất (af_subscription_complete)">

**Mục đích**

Ghi nhận sự kiện này có thể giúp bạn:

* Xem chiến dịch nào mang đến những người dùng đăng ký
* Hãy so sánh số lượng người dùng đã đăng ký so với người dùng chưa đăng ký
* Ghi nhận doanh thu được tạo từ đăng ký và phân bổ doanh thu cho chiến dịch và nguồn truyền thông

**Kích hoạt**

* Khi người dùng đăng ký thành công
* Khi đăng ký được gia hạn

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_subscription\_type | Loại gói đăng ký | 30 GB hàng tháng |
| af\_revenue | Số gói đăng ký | 555 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("af_subscription_type", "Monthly 30 GB"); 
eventValue.put("af_revenue", "555"); 
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "af_subscription_complete", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[AppsFlyerLib shared] logEvent:@"af_subscription_complete" withValues:@{
              @"af_subscription_type": @"Monthly 30 GB", 
              @"af_revenue": @"555"}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
ApAppsFlyerLib.shared().logEvent("af_subscription_complete", withValues: 
[ "af_subscription_type": "Monthly 30 GB",  
 "af_revenue": "555"])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SubscriptionCompleteEvent = new Dictionary<string, string>();
SubscriptionCompleteEvent.Add("af_subscription_type", "Monthly 30 GB");  
SubscriptionCompleteEvent.Add("af_revenue", "555");   
AppsFlyer.sendEvent ("af_subscription_complete", SubscriptionCompleteEvent);
```

</Tab>
</Tabs>

</Accordion>

## Cấu trúc đề xuất cho các sự kiện tùy chỉnh

Phần sau cung cấp cấu trúc sự kiện bao gồm tên sự kiện tùy chỉnh và thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Chọn gói (select_package)">

**Mục đích**

Ghi nhận khi người dùng quyết định mua một gói nhưng chưa thực hiện thanh toán. Ví dụ: bạn có thể sử dụng dữ liệu này để nhắm mục tiêu lại người dùng và gửi cho họ ưu đãi về các dịch vụ khác.

**Kích hoạt**

Khi người dùng chọn một gói nhưng chưa hoàn tất thanh toán

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| price | Giá của gói đăng ký | 50000 |
| af\_content\_type | Loại nội dung mà người dùng đã chọn | 5 GB dữ liệu |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<>();
eventValue.put("price", "50000");
eventValue.put("af_content_type ", "Data 5 GB ");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "select_package", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:@"select_package" withValues: @{ 
@"price": @"50000", 
@"af_content_type ": @"Data 5 GB "}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("select_package", withValues: 
[ "price": "50000",
"af_content_type ": "Data 5 GB "])
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> SelectPackageEvent= new Dictionary<string, string>();
SelectPackageEvent.Add("price", "50000");  
SelectPackageEvent.Add("af_content_type ", "Data 5 GB ");
AppsFlyer.sendEvent ("select_package", SelectPackageEvent);
```

</Tab>
</Tabs>

</Accordion>
