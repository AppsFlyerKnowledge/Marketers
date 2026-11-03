---
title: Các sự kiện ứng dụng đặt phòng khách sạn được đề xuất
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
  created_at: '2021-04-29T14:49:54Z'
  edited_at: '2022-01-25T17:23:42Z'
  id: 360019843558
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/360019843558
---
> **Khái quát:** Đo lường chất lượng của người dùng trong suốt hành trình người dùng của họ bằng cách ghi nhận các sự kiện trong ứng dụng được đề xuất này cho ứng dụng đặt phòng khách sạn của bạn.

## <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="100px" /> Đặt phòng khách sạn

Ứng dụng đặt phòng khách sạn cho phép du khách dễ dàng đặt phòng khách sạn đồng thời lựa chọn từ các ưu đãi tốt nhất. Các sự kiện điển hình mà chúng tôi đề xuất ghi nhận là tìm kiếm, mua, đặt vé du lịch và thêm vào danh sách yêu thích.

Việc ghi nhận các sự kiện có thể giúp bạn xác định:

* Những chiến dịch và nguồn truyền thông nào mang đến người dùng thực sự đặt chỗ cho kỳ nghỉ
* Những chiến dịch và nguồn truyền thông nào mang đến người dùng đặt phòng nhiều nhất và tạo ra nhiều doanh thu hơn

Bạn có thể phân bổ các ưu tiên như điểm số khách sạn, mùa, quốc gia và số lượng trẻ em đi cùng từ những người dùng đến từ các nguồn truyền thông nhất định. Sau đó, bạn có thể tối ưu hóa các chiến dịch của mình bằng cách nhắm mục tiêu các ưu tiên của người dùng này.

Để biết thêm thông tin về cách ghi lại các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Hướng dẫn sự kiện phong phú trong ứng dụng</Anchor>.

[![Flowchart_for_recommended_events_hotel_booking_app_user_journey](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)](https://files.readme.io/f425bc8865d731eb4934b6f32123156c7016ea1f75472e8878e76636aa593073-4402679204241.png)

## Cấu trúc đề xuất cho các sự kiện đã xác định trước

Phần sau đây cung cấp danh sách các cấu trúc sự kiện điển hình cho ngành dịch vụ đặt phòng khách sạn. Mỗi cấu trúc bao gồm một tên sự kiện đã xác định trước và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Hoàn tất đăng ký (af_complete_registration)">

**Mục đích**

Tìm hiểu xem có bao nhiêu người dùng đã cài đặt ứng dụng và hoàn tất quá trình đăng ký, phương thức đăng ký nào người dùng yêu thích và nguồn truyền thông nào mang đến người dùng đăng ký thực sự.

**Kích hoạt**

Thời điểm người dùng hoàn tất quá trình đăng ký

Thông số sự kiện

| Tên trường | Mô tả | Giá trị mẫu |
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
Dictionary<string, string> CompletedRegistrationEvent = new Dictionary<string, string>();
CompletedRegistrationEvent.Add("af_registration_method", "Facebook");
AppsFlyer.sendEvent ("af_complete_registration", CompletedRegistrationEvent);
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
AppsFlyerLib.getInstance().logEvent(getApplicationContext(),   
AFInAppEventType.LOGIN, null);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventLogin  
 withValues: nil  
];
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

<Accordion title="Tìm kiếm (af_search)">

**Mục đích**

Tìm hiểu những đối tượng tìm kiếm của người dùng,  và kết quả tìm kiếm nào phù hợp nhất và dẫn đến giao dịch hành mua. Ngoài ra, bạn có thể xem được người dùng ở một số vị trí địa lý nhất định đang tìm kiếm những gì và nhắm mục tiêu vào những điều đó một cách phù hợp trên các nguồn truyền thông.

**Kích hoạt**

Thời điểm người dùng thực hiện tìm kiếm

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_date\_a | Ngày nhận phòng | 2018/07/26 |
| af\_date\_b | Ngày trả phòng | 2018/08/01 |
| af\_destination\_a | Vị trí của người dùng | London |
| af\_destination\_b | Vị trí khách sạn | Madrid |
| af\_num\_adults | Số lượng khách | 2 |
| af\_num\_children | Số lượng trẻ em | 0 |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.DATE_A, "2018/07/26");
eventValue.put(AFInAppEventParameterName.DATE_B, "2018/08/01");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "London");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Madrid");
eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 2);
eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.SEARCH, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventSearch
withValues: @{
  AFEventParamDateA: @"2018/07/26",
  AFEventParamDateB: @"2018/08/01",
  AFEventParamDestinationA: @"London",
  AFEventParamDestinationB: @"Madrid",
  AFEventParamNumAdults: @2,
  AFEventParamNumChildren: @0
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventSearch, withValues: [
  AFEventParamDateA: "2018/07/26",
  AFEventParamDateB: "2018/08/01",
  AFEventParamDestinationA: "London",
  AFEventParamDestinationB: "Madrid",
  AFEventParamNumAdults: 2,
  AFEventParamNumChildren: 0
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> Search = 
			new Dictionary<string, string>();
Search.Add("af_date_a", "2018/07/26");
Search.Add("af_date_b", "2018/08/01");
Search.Add("af_destination_a", "London");
Search.Add("af_destination_b", "Madrid");
Search.Add("af_num_adults", "2");
Search.Add("af_num_children", "0");
AppsFlyer.sendEvent("af_add_to_wish_list", Search);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Khung hiển thị nội dung (af_content_view)">

**Mục đích**

Sự kiện này có thể giúp bạn xác định:

* Liệu kết quả tìm kiếm có liên quan đến các câu hỏi tìm kiếm hay không
* Người dùng đang tìm kiếm loại khách sạn nào
* Xu hướng theo mùa
* Các địa điểm nổi tiếng
* Nguồn truyền thông nào mang đến người dùng và sau đó nhắm mục tiêu lại những người dùng này trong các quảng cáo và khuyến mãi

**Kích hoạt**

Thời điểm người dùng đang xem một khách sạn

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Bảng giá của khách sạn | 674 |
| af\_content\_id | ID của khách sạn | ODIRNH |
| af\_date\_a | Ngày nhận phòng | 2018/07/26 |
| af\_date\_b | Ngày trả phòng | 2018/08/01 |
| af\_destination\_a | Vị trí của người dùng | London |
| af\_destination\_b | Vị trí khách sạn | Madrid |
| af\_class | Loại phòng | Phòng hạng sang |
| af\_num\_adults | Số lượng khách | 2 |
| af\_num\_children | Số lượng trẻ em | 0 |
| af\_hotel\_score | Điểm số khách sạn theo đánh giá | 9.6 |
| af\_preferred\_star\_ratings | Xếp hạng sao khách sạn được yêu thích | 5 |
| af\_preferred\_neighborhoods | Khu vực vị trí của khách sạn | Centro |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CURRENCY, "GBP");
eventValue.put(AFInAppEventParameterName.PRICE, 674);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "ODIRNH");
eventValue.put(AFInAppEventParameterName.DATE_A, "2018/07/26");
eventValue.put(AFInAppEventParameterName.DATE_B, "2018/08/01");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "London");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Madrid");
eventValue.put(AFInAppEventParameterName.CLASS, "Deluxe");
eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 2);
eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
eventValue.put(AFInAppEventParameterName.HOTEL_SCORE, 9.6);
eventValue.put(AFInAppEventParameterName.PREFERRED_STAR_RATINGS, 5);
eventValue.put(AFInAppEventParameterName.PREFERRED_NEIGHBORHOODS, "Centro");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.CONTENT_VIEW, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventContentView
withValues: @{
  AFEventParamCurrency: @"GBP",
  AFEventParamPrice: @674,
  AFEventParamContentId: @"ODIRNH",
  AFEventParamDateA: @"2018/07/26",
  AFEventParamDateB: @"2018/08/01",
  AFEventParamDestinationA: @"London",
  AFEventParamDestinationB: @"Madrid",
  AFEventParamClass: @"Deluxe",
  AFEventParamNumAdults: @2,
  AFEventParamNumChildren: @0,
  AFEventParamHotelScore: @9.6,
  AFEventParamPreferredStarRatings: @5,
  AFEventParamPreferredNeighborhoods: @"Centro"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventContentView, withValues: [
  AFEventParamCurrency: "GBP",
  AFEventParamPrice: 674,
  AFEventParamContentId: "ODIRNH",
  AFEventParamDateA: "2018/07/26",
  AFEventParamDateB: "2018/08/01",
  AFEventParamDestinationA: "London",
  AFEventParamDestinationB: "Madrid",
  AFEventParamClass: "Deluxe",
  AFEventParamNumAdults: 2,
  AFEventParamNumChildren: 0,
  AFEventParamHotelScore: 9.6,
  AFEventParamPreferredStarRatings: 5,
  AFEventParamPreferredNeighborhoods: "Centro"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> ContentView = 
			new Dictionary<string, string>();
ContentView.Add("af_currency", "GBP");
ContentView.Add("af_price", "674");
ContentView.Add("af_content_id", "ODIRNH");
ContentView.Add("af_date_a", "2018/07/26");
ContentView.Add("af_date_b", "2018/08/01");
ContentView.Add("af_destination_a", "London");
ContentView.Add("af_destination_b", "Madrid");
ContentView.Add("af_class", "Deluxe");
ContentView.Add("af_num_adults", "2");
ContentView.Add("af_num_children", "0");
ContentView.Add("af_hotel_score", "9.6");
ContentView.Add("af_preferred_star_ratings", "5");
ContentView.Add("af_preferred_neighborhoods", "Centro");
AppsFlyer.sendEvent("af_content_view", ContentView);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Thêm vào danh sách yêu thích (af_add_to_wishlist)">

**Mục đích**

Ghi nhận những khách sạn và điểm đến mà người dùng quan tâm khi đặt phòng. Ví dụ, khi bạn biết khách sạn, khu vực và xếp hạng sao mà người dùng đang tìm kiếm, bạn có thể sử dụng dữ liệu này để nhắm mục tiêu lại người dùng.

**Kích hoạt**

Thời điểm người dùng thêm một danh sách vào danh sách yêu thích của họ

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Bảng giá của khách sạn | 674 |
| af\_content\_id | ID của khách sạn | ODIRNH |
| af\_date\_a | Ngày nhận phòng | 2018/07/26 |
| af\_date\_b | Ngày trả phòng | 2018/08/01 |
| af\_destination\_a | Vị trí của người dùng | London |
| af\_destination\_b | Vị trí khách sạn | Madrid |
| af\_class | Loại phòng | Phòng hạng sang |
| af\_num\_adults | Số lượng khách | 2 |
| af\_num\_children | Số lượng trẻ em | 0 |
| af\_hotel\_score | Điểm số khách sạn theo đánh giá | 9.6 |
| af\_preferred\_star\_ratings | Xếp hạng sao khách sạn được yêu thích | 5 |
| af\_preferred\_neighborhoods | Khu vực vị trí của khách sạn | Centro |
| purchase\_method | Phương thức mua hàng | Thẻ tín dụng |
| af\_coupon\_code | Mã khuyến mại hoặc điểm thưởng khách hàng thân thiết | SUM2018 |
| property\_type | Loại khách sạn | Khách sạn |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CURRENCY, "GBP");
eventValue.put(AFInAppEventParameterName.PRICE, 674);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "ODIRNH");
eventValue.put(AFInAppEventParameterName.DATE_A, "2018/07/26");
eventValue.put(AFInAppEventParameterName.DATE_B, "2018/08/01");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "London");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Madrid");
eventValue.put(AFInAppEventParameterName.CLASS, "Deluxe");
eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 2);
eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
eventValue.put(AFInAppEventParameterName.HOTEL_SCORE, 9.6);
eventValue.put(AFInAppEventParameterName.PREFERRED_STAR_RATINGS, 5);
eventValue.put(AFInAppEventParameterName.PREFERRED_NEIGHBORHOODS, "Centro");
eventValue.put("purchase_method", "credit card");
eventValue.put(AFInAppEventParameterName.COUPON_CODE, "SUM2018");
eventValue.put("property_type", "hotel");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.ADD_TO_WISH_LIST, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventAddToWishlist
withValues: @{
  AFEventParamCurrency: @"GBP",
  AFEventParamPrice: @674,
  AFEventParamContentId: @"ODIRNH",
  AFEventParamDateA: @"2018/07/26",
  AFEventParamDateB: @"2018/08/01",
  AFEventParamDestinationA: @"London",
  AFEventParamDestinationB: @"Madrid",
  AFEventParamClass: @"Deluxe",
  AFEventParamNumAdults: @2,
  AFEventParamNumChildren: @0,
  AFEventParamHotelScore: @9.6,
  AFEventParamPreferredStarRatings: @5,
  AFEventParamPreferredNeighborhoods: @"Centro",
  @"purchase_method": @"credit card",
  AFEventParamCouponCode: @"SUM2018",
  @"property_type": @"hotel"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventAddToWishlist, withValues: [
  AFEventParamCurrency: "GBP",
  AFEventParamPrice: 674,
  AFEventParamContentId: "ODIRNH",
  AFEventParamDateA: "2018/07/26",
  AFEventParamDateB: "2018/08/01",
  AFEventParamDestinationA: "London",
  AFEventParamDestinationB: "Madrid",
  AFEventParamClass: "Deluxe",
  AFEventParamNumAdults: 2,
  AFEventParamNumChildren: 0,
  AFEventParamHotelScore: 9.6,
  AFEventParamPreferredStarRatings: 5,
  AFEventParamPreferredNeighborhoods: "Centro",
  "purchase_method": "credit card",
  AFEventParamCouponCode: "SUM2018",
  "property_type": "hotel"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> AddToWishList = 
			new Dictionary<string, string>();
AddToWishList.Add("af_currency", "GBP");
AddToWishList.Add("af_price", "674");
AddToWishList.Add("af_content_id", "ODIRNH");
AddToWishList.Add("af_date_a", "2018/07/26");
AddToWishList.Add("af_date_b", "2018/08/01");
AddToWishList.Add("af_destination_a", "London");
AddToWishList.Add("af_destination_b", "Madrid");
AddToWishList.Add("af_class", "Deluxe");
AddToWishList.Add("af_num_adults", "2");
AddToWishList.Add("af_num_children", "0");
AddToWishList.Add("af_hotel_score", "9.6");
AddToWishList.Add("af_preferred_star_ratings", "5");
AddToWishList.Add("af_preferred_neighborhoods", "Centro");
AddToWishList.Add("purchase_method", "credit card");
AddToWishList.Add("af_coupon_code", "SUM2018");
AddToWishList.Add("af_property_type", "hotel");
AppsFlyer.sendEvent("af_add_to_wish_list", AddToWishList);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Bắt đầu thanh toán (af_initiated_checkout)">

**Mục đích**

Hiểu hành vi của người mua khi họ tiến hành thanh toán. Sự kiện này có thể giúp bạn xác định:

* Phương thức mua hàng nào đã được sử dụng, ví dụ, thẻ tín dụng hoặc ví điện tử
* Người dùng có hoàn tất quá trình thanh toán hay không

**Kích hoạt**

Thời điểm người dùng thêm thông tin thẻ tín dụng hoặc kết nối ví điện tử của họ

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| af\_price | Bảng giá của khách sạn | 674 |
| af\_content\_id | ID của khách sạn | ODIRNH |
| af\_date\_a | Ngày nhận phòng | 2018/07/26 |
| af\_date\_b | Ngày trả phòng | 2018/08/01 |
| af\_destination\_a | Vị trí của người dùng | London |
| af\_destination\_b | Vị trí khách sạn | Madrid |
| af\_class | Loại phòng | Phòng hạng sang |
| af\_num\_adults | Số lượng khách | 2 |
| af\_num\_children | Số lượng trẻ em | 0 |
| af\_hotel\_score | Điểm số khách sạn theo đánh giá | 9.6 |
| af\_preferred\_star\_ratings | Xếp hạng sao khách sạn được yêu thích | 5 |
| af\_preferred\_neighborhoods | Khu vực vị trí của khách sạn | Centro |
| purchase\_method | Phương thức mua hàng | Thẻ tín dụng |
| af\_coupon\_code | Mã khuyến mại hoặc điểm thưởng khách hàng thân thiết | SUM2018 |
| property\_type | Loại khách sạn | Khách sạn |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.CURRENCY, "GBP");
eventValue.put(AFInAppEventParameterName.PRICE, 674);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "ODIRNH");
eventValue.put(AFInAppEventParameterName.DATE_A, "2018/07/26");
eventValue.put(AFInAppEventParameterName.DATE_B, "2018/08/01");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "London");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Madrid");
eventValue.put(AFInAppEventParameterName.CLASS, "Deluxe");
eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 2);
eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
eventValue.put(AFInAppEventParameterName.HOTEL_SCORE, 9.6);
eventValue.put(AFInAppEventParameterName.PREFERRED_STAR_RATINGS, 5);
eventValue.put(AFInAppEventParameterName.PREFERRED_NEIGHBORHOODS, "Centro");
eventValue.put("purchase_method", "credit card");
eventValue.put(AFInAppEventParameterName.COUPON_CODE, "SUM2018");
eventValue.put("property_type", "hotel");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.INITIATED_CHECKOUT, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventInitiatedCheckout
withValues: @{
  AFEventParamCurrency: @"GBP",
  AFEventParamPrice: @674,
  AFEventParamContentId: @"ODIRNH",
  AFEventParamDateA: @"2018/07/26",
  AFEventParamDateB: @"2018/08/01",
  AFEventParamDestinationA: @"London",
  AFEventParamDestinationB: @"Madrid",
  AFEventParamClass: @"Deluxe",
  AFEventParamNumAdults: @2,
  AFEventParamNumChildren: @0,
  AFEventParamHotelScore: @9.6,
  AFEventParamPreferredStarRatings: @5,
  AFEventParamPreferredNeighborhoods: @"Centro",
  @"purchase_method": @"credit card",
  AFEventParamCouponCode: @"SUM2018",
  @"property_type": @"hotel"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventInitiatedCheckout, withValues: [
  AFEventParamCurrency: "GBP",
  AFEventParamPrice: 674,
  AFEventParamContentId: "ODIRNH",
  AFEventParamDateA: "2018/07/26",
  AFEventParamDateB: "2018/08/01",
  AFEventParamDestinationA: "London",
  AFEventParamDestinationB: "Madrid",
  AFEventParamClass: "Deluxe",
  AFEventParamNumAdults: 2,
  AFEventParamNumChildren: 0,
  AFEventParamHotelScore: 9.6,
  AFEventParamPreferredStarRatings: 5,
  AFEventParamPreferredNeighborhoods: "Centro",
  "purchase_method": "credit card",
  AFEventParamCouponCode: "SUM2018",
  "property_type": "hotel"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> InitiatedCheckout = 
			new Dictionary<string, string>();
InitiatedCheckout.Add("af_currency", "GBP");
InitiatedCheckout.Add("af_price", "674");
InitiatedCheckout.Add("af_content_id", "ODIRNH");
InitiatedCheckout.Add("af_date_a", "2018/07/26");
InitiatedCheckout.Add("af_date_b", "2018/08/01");
InitiatedCheckout.Add("af_destination_a", "London");
InitiatedCheckout.Add("af_destination_b", "Madrid");
InitiatedCheckout.Add("af_class", "Deluxe");
InitiatedCheckout.Add("af_num_adults", "2");
InitiatedCheckout.Add("af_num_children", "0");
InitiatedCheckout.Add("af_hotel_score", "9.6");
InitiatedCheckout.Add("af_preferred_star_ratings", "5");
InitiatedCheckout.Add("af_preferred_neighborhoods", "Centro");
InitiatedCheckout.Add("purchase_method", "credit card");
InitiatedCheckout.Add("af_coupon_code", "SUM2018");
InitiatedCheckout.Add("af_property_type", "hotel");
AppsFlyer.sendEvent("af_initiated_chekcout", InitiatedCheckout);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Mua hàng (af_purchase)">

**Mục đích**

Tìm hiểu về xu hướng mua hàng trong ứng dụng đặt phòng khách sạn của bạn. Sự kiện này có thể giúp bạn:

* Xác định LTV của người dùng và ROI của các chiến dịch của bạn trên các mạng quảng cáo và các đại lý quảng cáo
* Xác định những ưu đãi nào được người dùng chọn nhiều nhất
* Chiến dịch tham chiếu chéo với các mặt hàng đã mua để tối ưu hóa nhắm mục tiêu chiến dịch

**Kích hoạt**

Thời điểm người dùng truy cập trang cảm ơn sau khi mua hàng thành công

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Doanh thu ước tính từ giao dịch mua | 1205.99 |
| af\_price | Tổng số tiền mua hàng | 4000 |
| af\_content\_id | ID mặt hàng | 121 |
| af\_content\_type | Danh mục mặt hàng | hotel |
| af\_currency | Mã tiền tệ | AUD |
| af\_quantity | Tổng số mặt hàng trong giỏ hàng | 1 |
| af\_order\_id | ID đơn đặt hàng được tạo sau khi mua. | X123ABC |
| af\_receipt\_id | ID đơn đặt hàng,  bắt buộc để tích hợp nhắm mục tiêu lại cho CRITEO và Google Ads | X123ABC |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 4000);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "121");
// for multiple product categories, set the param value as: // new String {"121", "262"}
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "hotel");
// for multiple product categories,, set the param value as: new String {"hotel", "meals"}
eventValue.put(AFInAppEventParameterName.CURRENCY, "AUD");
eventValue.put(AFInAppEventParameterName.QUANTITY, 2);
// for multiple product categories, set the param value as: new int {2, 5}
eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "X123ABC");
eventValue.put("af_order_id", "X123ABC");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.PURCHASE, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventPurchase
withValues: @{
  AFEventParamRevenue: @1205.99,
  AFEventParamPrice: @4000,
  AFEventParamContentId: @"121",
  // for multiple product categories, set the param value as:   
  // @[@"121", @"124"]
  AFEventParamContentType: @"hotel",
  // for multiple product categories, set the param value as:   
  // @[@"hotel", @"meals"]
  AFEventParamCurrency: @"AUD",
  AFEventParamQuantity: @2,
  // for multiple product categories, set the param value as:   
  // @[@2, @5]
  AFEventParamOrderId: @"X123ABC",
  AFEventParamReceiptId: @"X123ABC"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventPurchase, withValues: [
  AFEventParamRevenue: 1205.99,
  AFEventParamPrice: 4000,
  AFEventParamContentId: "121",
  // for multiple product categories, set the param value as: ["221", "124"],
  AFEventParamContentType: "hotel",
  // for multiple product categories, set the param value as: ["hotel", "meals"] 
  AFEventParamCurrency: "AUD",
  AFEventParamQuantity: 2,
  // for multiple product categories, set the param value as: [2, 5]
  AFEventParamOrderId: "X123ABC", 
  AFEventParamReceiptId: "X123ABC"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> PurchaseEvent = new Dictionary<string, string>();
PurchaseEvent.Add("af_revenue", "1205.99");
PurchaseEvent.Add("af_price", "4000");
PurchaseEvent.Add("af_content_id", "121");
// for multiple product categories, set the param value as: ["121", "124"]
PurchaseEvent.Add("af_content_type", "hotel");
// for multiple product categories, set the param value as: ["hotel", "meals"]
PurchaseEvent.Add("af_currency", "AUD");
PurchaseEvent.Add("af_quantity", "2");
// for multiple product categories, set the param value as: [2, 5] 
PurchaseEvent.Add("af_order_id", "X123ABC");
PurchaseEvent.Add("af_receipt_id", "X123ABC");
AppsFlyer.sendEvent ("af_purchase", PurchaseEvent);
```

</Tab>
</Tabs>

</Accordion>

<Accordion title="Đặt vé du lịch (af_travel_booking)">

**Mục đích**

Xác định tỷ lệ đặt phòng tổng thể trong ứng dụng của bạn. Sự kiện này có thể giúp bạn:

* Ghi nhận doanh thu tạo ra từ hoạt động đặt phòng
* Xác định số lượng người dùng đặt phòng khách sạn có trẻ em
* Hiểu được những xu hướng theo mùa
* Xác định các khách sạn được nhiều người ưa chuộng

**Kích hoạt**

Thời điểm người dùng đến trang cảm ơn sau khi đặt phòng khách sạn

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Doanh thu từ đặt phòng | 647.95 |
| af\_currency | Mã tiền tệ | GBP |
| af\_price | Bảng giá của khách sạn | 674 |
| af\_content\_id | ID của khách sạn | ODIRNH |
| af\_date\_a | 2018/07/26 | Ngày nhận phòng |
| af\_date\_b | Ngày trả phòng | 2018/08/01 |
| af\_destination\_a | Vị trí của người dùng | London |
| af\_destination\_b | Vị trí khách sạn | Madrid |
| af\_class | Loại phòng | Phòng hạng sang |
| af\_num\_adults | Số lượng khách | 2 |
| af\_num\_children | Số lượng trẻ em | 0 |
| af\_hotel\_score | Điểm số khách sạn theo đánh giá | 9.6 |
| af\_preferred\_star\_ratings | Xếp hạng sao khách sạn được yêu thích | 5 |
| af\_preferred\_neighborhoods | Khu vực vị trí của khách sạn | Centro |
| purchase\_method | Phương thức mua hàng | Thẻ tín dụng |
| af\_coupon\_code | Mã khuyến mại hoặc điểm thưởng khách hàng thân thiết | SUM2018 |
| property\_type | Loại khách sạn | Khách sạn |
| new\_booking | Lần đặt phòng đầu tiên của người dùng | true |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REVENUE, 647.95);
eventValue.put(AFInAppEventParameterName.CURRENCY, "GBP");
eventValue.put(AFInAppEventParameterName.PRICE, 674);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "ODIRNH");
eventValue.put(AFInAppEventParameterName.DATE_A, "2018/07/26");
eventValue.put(AFInAppEventParameterName.DATE_B, "2018/08/01");
eventValue.put(AFInAppEventParameterName.DESTINATION_A, "London");
eventValue.put(AFInAppEventParameterName.DESTINATION_B, "Madrid");
eventValue.put(AFInAppEventParameterName.CLASS, "Deluxe");
eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 2);
eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
eventValue.put(AFInAppEventParameterName.HOTEL_SCORE, 9.6);
eventValue.put(AFInAppEventParameterName.PREFERRED_STAR_RATINGS, 5);
eventValue.put(AFInAppEventParameterName.PREFERRED_NEIGHBORHOODS, "Centro");
eventValue.put("purchase_method", "credit card");
eventValue.put(AFInAppEventParameterName.COUPON_CODE, "SUM2018");
eventValue.put("property_type", "hotel");
eventValue.put("new_booking", true);
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.TRAVEL_BOOKING, eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:AFEventTravelBooking
withValues: @{
  AFEventParamRevenue: @647.95,
  AFEventParamCurrency: @"GBP",
  AFEventParamPrice: @674,
  AFEventParamContentId: @"ODIRNH",
  AFEventParamDateA: @"2018/07/26",
  AFEventParamDateB: @"2018/08/01",
  AFEventParamDestinationA: @"London",
  AFEventParamDestinationB: @"Madrid",
  AFEventParamClass: @"Deluxe",
  AFEventParamNumAdults: @2,
  AFEventParamNumChildren: @0,
  AFEventParamHotelScore: @9.6,
  AFEventParamPreferredStarRatings: @5,
  AFEventParamPreferredNeighborhoods: @"Centro",
  @"purchase_method": @"credit card",
  AFEventParamCouponCode: @"SUM2018",
  @"property_type": @"hotel",
  @"new_booking": @TRUE
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent(AFEventTravelBooking, withValues: [
  AFEventParamRevenue: 647.95,
  AFEventParamCurrency: "GBP",
  AFEventParamPrice: 674,
  AFEventParamContentId: "ODIRNH",
  AFEventParamDateA: "2018/07/26",
  AFEventParamDateB: "2018/08/01",
  AFEventParamDestinationA: "London",
  AFEventParamDestinationB: "Madrid",
  AFEventParamClass: "Deluxe",
  AFEventParamNumAdults: 2,
  AFEventParamNumChildren: 0,
  AFEventParamHotelScore: 9.6,
  AFEventParamPreferredStarRatings: 5,
  AFEventParamPreferredNeighborhoods: "Centro",
  "purchase_method": "credit card",
  AFEventParamCouponCode: "SUM2018",
  "property_type": "hotel",
  "new_booking": true
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> TravelBooking = 
new Dictionary<string, string>();
TravelBooking.Add("af_revenue", "647.95");
TravelBooking.Add("af_currency", "GBP");
TravelBooking.Add("af_price", "674");
TravelBooking.Add("af_content_id", "ODIRNH");
TravelBooking.Add("af_date_a", "2018/07/26");
TravelBooking.Add("af_date_b", "2018/08/01");
TravelBooking.Add("af_destination_a", "London");
TravelBooking.Add("af_destination_b", "Madrid");
TravelBooking.Add("af_class", "Deluxe");
TravelBooking.Add("af_num_adults", "2");
TravelBooking.Add("af_num_children", "0");
TravelBooking.Add("af_hotel_score", "9.6");
TravelBooking.Add("af_preferred_star_ratings", "5");
TravelBooking.Add("af_preferred_neighborhoods", "Centro");
TravelBooking.Add("purchase_method", "credit card");
TravelBooking.Add("af_coupon_code", "SUM2018");
TravelBooking.Add("af_property_type", "hotel");
TravelBooking.Add("af_new_booking", "true");
AppsFlyer.sendEvent("af_travel_booking", TravelBookingEvent);
```

</Tab>
</Tabs>

</Accordion>

## Cấu trúc đề xuất cho các sự kiện tùy chỉnh

Phần sau cung cấp danh sách các cấu trúc sự kiện bao gồm tên sự kiện tùy chỉnh và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.

<Accordion title="Lần mua đầu tiên (first_purchase)">

**Mục đích**

Tương tự như sự kiện [Mua hàng](/docs/recommended-hotel-booking-app-events#purchase-af_purchase). Ngoài ra, sự kiện này có thể giúp bạn xác định:

* Khoảng thời gian cần thiết để một người mua mới thực hiện mua hàng
* Những sản phẩm nào mà người mua lần đầu muốn mua
* Giá và doanh thu trung bình của giao dịch mua lần đầu

**Kích hoạt**

Thời điểm người dùng hoàn tất giao dịch mua lần đầu

**Thông số sự kiện**

| Tên | Mô tả | Giá trị mẫu |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/vi/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Doanh thu từ giao dịch mua | 1205.95 |
| af\_price | Tổng số tiền mua hàng | 4000 |
| af\_content\_id | ID mặt hàng | 121, 262 |
| af\_content\_type | Danh mục mặt hàng | hotel |
| af\_currency | Tiền tệ | AUD |
| af\_quantity | Số lượng mặt hàng trong giỏ hàng | 1 |
| af\_order\_id | ID đơn đặt hàng được tạo sau khi mua | X123ABC |
| af\_receipt\_id | ID đơn đặt hàng, bắt buộc để tích hợp nhắm mục tiêu lại cho CRITEO và Google AdWords | X123ABC |

**Ví dụ**

<Tabs>
<Tab title="Android">

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.PRICE, 4000);
eventValue.put(AFInAppEventParameterName.CONTENT_ID, "221");
// for multiple product categories, set the param value as: new String {"221", "124"}
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "hotel");
// for multiple product categories set the param value as: new String {"hotel", "meals"}
eventValue.put(AFInAppEventParameteName.CURRENCY, "USD");
eventValue.put(AFInAppEventParameterName.QUANTITY, 2);
// for multiple product categories, set the param value as: new int {1}
eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "X123ABC");
eventValue.put("af_order_id", "X123ABC");
AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "first_purchase", eventValue);
```

</Tab>

<Tab title="iOS - Objective C">

```objectivec
[[AppsFlyerLib shared] logEvent:("first_purchase")
withValues: @{
  AFEventParamRevenue: @1205.95,
  AFEventParamPrice: @4000,
  AFEventParamContentId: @"221",
  // for multiple product categories, set the param value as: @[@"221", @"124"]
  AFEventParamContentType: @"hotel",
  // for multiple product categories, set the param value as: @[@"hotel", @"meals"]
  AFEventParamCurrency: @"USD",
  AFEventParamQuantity: @2,
  // for multiple product categories, set the param value as: @[@1]
  AFEventParamOrderId: @"X123ABC",
  AFEventParamReceiptId: @"X123ABC"
}];
```

</Tab>

<Tab title="iOS - Swift">

```swift
AppsFlyerLib.shared().logEvent("first_purchase", withValues: [ 
  AFEventParamRevenue: 1205.95,
  AFEventParamPrice: 4000,
  AFEventParamContentId: "221",
  // for multiple product categories, set the param value as: ["221", "124"]
  AFEventParamContentType: "hotel",
  // for multiple product categories, set the param value as: ["hotel", "meals"]
  AFEventParamCurrency: "USD",
  AFEventParamQuantity: 2,
  // for multiple product categories, set the param value as: // [1]
  AFEventParamOrderId: "X123ABC",
  AFEventParamReceiptId: "X123ABC"
]);
```

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> FirstPurchaseEvent = new Dictionary<string, string>();
FirstPurchaseEvent.Add("af_revenue", "1205.95");
FirstPurchaseEvent.Add("af_price", "4000");
FirstPurchaseEvent.Add("af_content_id", "121");
// for multiple product categories, set the param value as: ["221", "124"]
FirstPurchaseEvent.Add("af_content_type", "hotel");
// for multiple product categories, set the param value as: ["hotel", "meals"]
FirstPurchaseEvent.Add("af_currency", "USD");
FirstPurchaseEvent.Add("af_quantity", "2");
// for multiple product categories, set the param value as: [1] 
FirstPurchaseEvent.Add("af_order_id", "X123ABC");
FirstPurchaseEvent.Add("af_receipt_id", "X123ABC");
AppsFlyer.sendEvent ("first_purchase", FirstPurchaseEvent);
```

</Tab>
</Tabs>

</Accordion>
