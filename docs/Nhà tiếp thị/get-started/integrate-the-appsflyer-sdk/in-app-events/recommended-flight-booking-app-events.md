---
title: ' Các sự kiện ứng dụng đặt vé máy bay được đề xuất'
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-04-29T13:07:29Z'
  edited_at: '2022-01-25T17:24:27Z'
  id: 360019670857
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/360019670857
---
> **Khái quát:** Đo lường chất lượng của người dùng trong suốt hành trình người dùng của họ bằng cách ghi nhận các sự kiện trong ứng dụng được đề xuất này cho ứng dụng đặt vé máy bay của bạn.
>
> ## <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="100px" /> Đặt vé máy bay
>
> Ứng dụng đặt vé máy bay cho phép du khách dễ dàng đặt vé máy bay đồng thời lựa chọn từ các ưu đãi tốt nhất. Các sự kiện điển hình mà chúng tôi đề xuất ghi nhận là đặt vé máy bay, tìm kiếm chuyến bay và xem các chương trình ưu đãi.
>
> Ghi nhận sự kiện có thể giúp bạn:
>
> * Tìm hiểu về các điểm đến phổ biến.
> * Phân tích xu hướng theo mùa
> * Tìm hiểu về các hãng hàng không phổ biến mà người dùng thích sử dụng
>
> Để biết thêm thông tin về cách ghi lại các sự kiện trong ứng dụng, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Hướng dẫn sự kiện phong phú trong ứng dụng</Anchor>.
>
> <Image align="center" alt="Flowchart_for_recommended_events flight_booking_app_user_journey" src="https://files.readme.io/435378707a7299a8c98bc7490f0f1554b5f6c332a35c1546ce34feb1b6b86394-360020171258.png" />
>
> ## Cấu trúc đề xuất cho các sự kiện đã xác định trước
>
> Phần sau đây cung cấp danh sách các cấu trúc sự kiện điển hình cho ngành dịch vụ đặt vé máy bay. Mỗi cấu trúc bao gồm một tên sự kiện đã xác định trước và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.
>
>
> <Accordion title="Hoàn tất đăng ký (af_complete_registration)">
>
> **Mục đích**
>
> Tìm hiểu số lượng người dùng đã cài đặt ứng dụng và hoàn tất quá trình đăng ký, phương thức đăng ký nào mà người dùng yêu thích.
>
> **Kích hoạt**
>
> Thời điểm người dùng hoàn tất quá trình đăng ký
>
> Thông số sự kiện
>
>
>
> | Tên trường | Mô tả | Giá trị mẫu |
> | --- | --- | --- |
> | af\_registration\_method | Loại phương thức đăng ký | email, facebook |
>
>
>
> **Ví dụ**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.REGSITRATION_METHOD, "Facebook");
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.COMPLETE_REGISTRATION, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventCompleteRegistration
> withValues: @{ 
>   AFEventParamRegistrationMethod: @"Facebook" 
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventCompleteRegistration, 
> withValues: [
>   AFEventParamRegistrationMethod: "Facebook"
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> CompletedRegistrationEvent = new Dictionary<string, string>();
> CompletedRegistrationEvent.Add("af_registration_method", "Facebook");
> AppsFlyer.sendEvent ("af_complete_registration", CompletedRegistrationEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Đăng nhập (af_login)">
>
> **Mục đích**
>
> Hiểu được việc giữ chân người dùng đã đăng ký của bạn
>
> **Kích hoạt**
>
> Thời điểm người dùng đăng nhập thành công
>
> **Thông số sự kiện**
>
> Có thể được gửi mà không cần bất kỳ thông số bổ sung nào
>
> **Ví dụ**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(),   
> AFInAppEventType.LOGIN, null);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventLogin  
>  withValues: nil  
> ];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventLogin, withValues: nil);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> AppsFlyer.sendEvent ("af_login", null);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Đặt vé du lịch (af_travel_booking)">
>
> **Mục đích**
>
> Khả năng đặt vé máy bay là chức năng chính của ứng dụng. Sự kiện này có thể giúp bạn xác định:
>
> * Những điểm đến phổ biến
> * Các hãng hàng không phổ biến
> * Xu hướng theo mùa
>
> **Kích hoạt**
>
> Thời điểm người dùng đến trang cảm ơn sau khi đặt vé máy bay thành công
>
> **Thông số sự kiện**
>
>
>
> | Tên | Mô tả | Giá trị mẫu |
> | --- | --- | --- |
> | <Anchor target="_blank" href="/marketers/vi/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Doanh thu liên quan đến việc đặt vé | 647.99 |
> | af\_currency | Mã tiền tệ | SGD |
> | af\_price | Giá | 674 |
> | af\_content\_id | ID ưu đãi của chuyến bay | ODIRNH |
> | af\_departing\_departure\_date | Ngày đi | 2018-06-21 |
> | af\_returning\_departure\_date | Ngày về | 2018-06-26 |
> | af\_destination\_a | Điểm đến đầu tiên | BKK |
> | af\_destination\_b | Điểm đến thứ hai (nếu có) | SYD |
> | airline\_code | Mã của hãng hàng không | KLM |
> | af\_class | Hạng chuyến bay được đặt vé | phổ thông |
> | purchase\_method | Phương thức được sử dụng cho giao dịch mua | thẻ tín dụng |
>
>
>
> **Ví dụ**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.REVENUE, 647.99);
> eventValue.put(AFInAppEventParameterName.CURRENCY, "SGD");
> eventValue.put(AFInAppEventParameterName.PRICE, 674);
> eventValue.put(AFInAppEventParameterName.CONTENT_ID, "ODIRNH");
> eventValue.put(AFInAppEventParameterName.DEPARTING_DEPARTURE_DATE, "2018-06-21");
> eventValue.put(AFInAppEventParameterName.RETURNING_DEPARTURE_DATE, "2018-06-26");
> eventValue.put(AFInAppEventParameterName.DESTINATION_A, "BKK");
> eventValue.put(AFInAppEventParameterName.DESTINATION_B, "SYD");
> eventValue.put("airline_code", "KLM");
> eventValue.put(AFInAppEventParameterName.CLASS, "economy");
> eventValue.put("purchase_method", "credit card");
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.TRAVEL_BOOKING, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventTravelBooking
> withValues: @{
>  AFEventParamRevenue: @647.99,
>  AFEventParamCurrency: @"SGD",
>  AFEventParamPrice: @674,
>  AFEventParamContentId: @"ODIRNH",
>  AFEventParamDepartingDepartureDate: @"2018-21-06",
>  AFEventParamReturningDepartureDate: @"2018-26-06",
>  AFEventParamDestinationA: @"BKK",
>  AFEventParamDestinationB: @"SYD",
>  @"airline_code": @"KLM",
>  AFEventParamClass: @"economy",
>  @"purchase_method": @"credit card"
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventTravelBooking, 
> withValues: [
>  AFEventParamRevenue: 647.99,
>  AFEventParamCurrency: "SGD",
>  AFEventParamPrice: 674,
>  AFEventParamContentId: "ODIRNH",
>  AFEventParamDepartingDepartureDate: "2018-21-06",
>  AFEventParamReturningDepartureDate: "2018-26-06",
>  AFEventParamDestinationA: "BKK",
>  AFEventParamDestinationB: "SYD",
>  "airline_code": "KLM",
>  AFEventParamClass: "economy",
>  "purchase_method": "credit card"
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> TravelBookingEvent = new Dictionary<string, string>();
> TravelBookingEvent.Add("af_revenue", "647.99");
> TravelBookingEvent.Add("af_currency", "SGD");
> TravelBookingEvent.Add("af_price", "974");
> TravelBookingEvent.Add("af_content_id", "ODIRNH");
> TravelBookingEvent.Add("af_departing_departure_date", "2018-06-21");
> TravelBookingEvent.Add("af_returning_departure_date", "2018-06-26");
> TravelBookingEvent.Add("af_destination_a", "BKK");
> TravelBookingEvent.Add("af_destination_b", "SYD");
> TravelBookingEvent.Add("airline_code", "KLM");
> TravelBookingEvent.Add("af_class", "economy");
> TravelBookingEvent.Add("purchase_method", "credit card");
> AppsFlyer.sendEvent ("af_travel_booking", TravelBookingEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Khung hiển thị nội dung (af_content_view)">
>
> **Mục đích**
>
> Sự kiện này có thể giúp bạn xác định:
>
> * Ưu đãi chuyến bay nào hấp dẫn người dùng nhất
> * Liệu kết quả tìm kiếm có liên quan đến các câu hỏi tìm kiếm hay không
>
> **Kích hoạt**
>
> Thời điểm người dùng nhấp vào kết quả tìm kiếm
>
> **Thông số sự kiện**
>
>
>
> | Tên | Mô tả | Giá trị mẫu |
> | --- | --- | --- |
> | af\_departing\_departure\_date | Ngày đi | 2018-06-21 |
> | af\_returning\_departure\_date | Ngày về | 2018-06-26 |
> | af\_destination\_a | Điểm đến đầu tiên | BKK |
> | af\_destination\_b | Điểm đến thứ hai (nếu có) | SYD |
>
>
>
> **Ví dụ**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.DEPARTING_DEPARTURE_DATE, "2018-06-21");
> eventValue.put(AFInAppEventParameterName.RETURNING_DEPARTURE_DATE, "2018-06-26");
> eventValue.put(AFInAppEventParameterName.DESTINATION_A, "BKK");
> eventValue.put(AFInAppEventParameterName.DESTINATION_B, "SYD");
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.CONTENT_VIEW, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventContentView
> withValues: @{
>   AFEventParamDepartingDepartureDate: @"2018-21-06",
>   AFEventParamReturningDepartureDate: @"2018-26-06",
>   AFEventParamDestinationA: @"BKK",
>   AFEventParamDestinationB: @"SYD"
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventContentView, withValues: [
>  AFEventParamDepartingDepartureDate: "2018-21-06",
>  AFEventParamReturningDepartureDate: "2018-26-06",
>  AFEventParamDestinationA: "BKK",
>  AFEventParamDestinationA: "SYD"
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> ContentViewEvent = new Dictionary<string, string>();
> ContentViewEvent.Add("af_departing_departure_date", "2018-06-21");
> ContentViewEvent.Add("af_returning_departure_date", "2018-06-26");
> ContentViewEvent.Add("af_destination_a", "BKK");
> ContentViewEvent.Add("af_destination_b", "SYD");
> AppsFlyer.sendEvent ("af_content_view", ContentViewEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Tìm kiếm (af_search)">
>
> **Mục đích**
>
> Ứng dụng đặt vé máy bay cho phép người dùng tìm kiếm các chuyến bay và ưu đãi. Một cách để thu được thông tin về sở thích của người dùng là ghi lại các thông số tìm kiếm. Sự kiện này có thể giúp bạn:
>
> * Tìm hiểu những đối tượng tìm kiếm của người dùng
> * Biết được điểm đến nào là phổ biến nhất
> * Xem có bao nhiêu người dùng đưa con cùng đi du lịch
> * Xem thời điểm nào trong năm người dùng thích hoặc lên kế hoạch du lịch
>
> **Kích hoạt**
>
> Sau khi người dùng điền vào biểu mẫu tìm kiếm và nhấp vào nút tìm kiếm
>
> **Thông số sự kiện**
>
>
>
> | Tên | Mô tả | Giá trị mẫu |
> | --- | --- | --- |
> | af\_num\_children | Số trẻ em đi du lịch | 0 |
> | af\_destination\_a | Điểm đến đầu tiên | BKK |
> | af\_destination\_b | Điểm đến thứ hai (nếu có) | SYD |
> | af\_departing\_departure\_date | Ngày đi | 2018-06-21 |
> | af\_returning\_departure\_date | Ngày về | 2018-06-26 |
> | af\_num\_infants | Số trẻ sơ sinh đi du lịch | 0 |
> | af\_num\_adults | Số lượng  người lớn đi du lịch | 1 |
>
>
>
> **Ví dụ**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, 
> eventValue.put(AFInAppEventParameterName.NUM_CHILDREN, 0);
> eventValue.put(AFInAppEventParameterName.DESTINATION_A, "BKK");
> eventValue.put(AFInAppEventParameterName.DESTINATION_B, "SYD");
> eventValue.put(AFInAppEventParameterName.DEPARTING_DEPARTURE_DATE, "2018-06-21");
> eventValue.put(AFInAppEventParameterName.RETURNING_DEPARTURE_DATE, "2018-06-26");
> eventValue.put(AFInAppEventParameterName.NUM_INFANTS, 0);
> eventValue.put(AFInAppEventParameterName.NUM_ADULTS, 1);
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.SEARCH, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventSearch
> withValues: @{
>  AFEventParamNumChildren: @0,
>  AFEventParamDestinationA: @"BKK",
>  AFEventParamDestinationB: @"SYD",
>  AFEventParamDepartingDepartureDate: @"2018-21-06",
>  AFEventParamReturningDepartureDate: @"2018-26-06",
>  AFEventParamNumInfants: @0,
>  AFEventParamNumAdults: @1
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventSearch, withValues: [
>  AFEventParamNumChildren: 0,
>  AFEventParamDestinationA: "BKK",
>  AFEventParamDestinationB: "SYD",
>  AFEventParamDepartingDepartureDate: "2018-21-06",
>  AFEventParamReturningDepartureDate: "2018-26-06",
>  AFEventParamNumInfants: 0,
>  AFEventParamNumAdults: 1
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> SearchEvent = new Dictionary<string, string>();
> SearchEvent.Add("af_num_children", "0");
> SearchEvent.Add("af_destination_a", "BKK");
> SearchEvent.Add("af_destination_b", "SYD");
> SearchEvent.Add("af_departing_departure_date", "2018-06-21");
> SearchEvent.Add("af_returning_departure_date", "2018-06-26");
> SearchEvent.Add("af_num_infants", "0");
> SearchEvent.Add("af_num_adults", "0");
> AppsFlyer.sendEvent ("af_search", SearchEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Thêm thông tin thanh toán (af_add_payment_info)">
>
> **Mục đích**
>
> Ghi nhận những lần thành công và không thành công trong việc thêm thông tin thanh toán khi đặt vé máy bay.
>
> **Kích hoạt**
>
> Thời điểm người dùng nhấp vào nút đặt vé máy bay
>
> **Thông số sự kiện**
>
>
>
> | Tên | Mô tả | Giá trị mẫu |
> | --- | --- | --- |
> | af\_success | Thêm phương thức thanh toán có thành công hay không | true |
>
>
>
> **Ví dụ**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.SUCCESS, true);
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.ADD_PAYMENT_INFO, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventAddPaymentInfo
> withValues: @{
>   AFEventParamSuccess: @TRUE
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventAddPaymentInfo, 
> withValues: [
>   AFEventParamSuccess: true
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> AddPaymentInfoEvent = new Dictionary<string, string>();
> AddPaymentInfoEvent.Add("af_success", "true");
> AppsFlyer.sendEvent ("af_add_payment_info", AddPaymentInfoEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
>
> <Accordion title="Mua hàng (af_purchase)">
>
> **Mục đích**
>
> Tìm hiểu về xu hướng mua trong ứng dụng đặt vé máy bay của bạn. Sự kiện này có thể giúp bạn:
>
> * Xác định LTV của người dùng và ROI của các chiến dịch của bạn trên các mạng quảng cáo và các đại lý quảng cáo
> * Xác định những ưu đãi nào được người dùng chọn nhiều nhất
> * Chiến dịch tham chiếu chéo với các mặt hàng đã mua để tối ưu hóa nhắm mục tiêu chiến dịch
>
> **Kích hoạt**
>
> Thời điểm người dùng truy cập trang cảm ơn sau khi mua hàng thành công
>
> **Thông số sự kiện**
>
>
>
> | Tên | Mô tả | Giá trị mẫu |
> | --- | --- | --- |
> | <Anchor target="_blank" href="/marketers/vi/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Doanh thu ước tính từ giao dịch mua | 1205.99 |
> | af\_price | Tổng số tiền mua hàng | 4000 |
> | af\_content\_id | ID mặt hàng | 121 |
> | af\_content\_type | Danh mục mặt hàng | flight |
> | af\_currency | Mã tiền tệ | AUD |
> | af\_quantity | Tổng số mặt hàng trong giỏ hàng | 1 |
> | af\_order\_id | ID đơn đặt hàng được tạo sau khi mua. | X123ABC |
> | af\_receipt\_id | ID đơn đặt hàng,  bắt buộc để tích hợp nhắm mục tiêu lại cho CRITEO và Google Ads | X123ABC |
>
>
>
> **Ví dụ**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.PRICE, 4000);
> eventValue.put(AFInAppEventParameterName.CONTENT_ID, "121");
> // for multiple product categories, set the param value as: // new String {"121", "262"}
> eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "flight");
> // for multiple product categories,, set the param value as: new String {"flight", "meals"}
> eventValue.put(AFInAppEventParameterName.CURRENCY, "AUD");
> eventValue.put(AFInAppEventParameterName.QUANTITY, 2);
> // for multiple product categories, set the param value as: new int {2, 5}
> eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "X123ABC");
> eventValue.put("af_order_id", "X123ABC");
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), AFInAppEventType.PURCHASE, eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:AFEventPurchase
> withValues: @{
>   AFEventParamRevenue: @1205.99,
>   AFEventParamPrice: @4000,
>   AFEventParamContentId: @"121",
>   // for multiple product categories, set the param value as:   
>   // @[@"121", @"124"]
>   AFEventParamContentType: @"flight",
>   // for multiple product categories, set the param value as:   
>   // @[@"flight", @"meals"]
>   AFEventParamCurrency: @"AUD",
>   AFEventParamQuantity: @2,
>   // for multiple product categories, set the param value as:   
>   // @[@2, @5]
>   AFEventParamOrderId: @"X123ABC",
>   AFEventParamReceiptId: @"X123ABC"
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent(AFEventPurchase, withValues: [
>   AFEventParamRevenue: 1205.99,
>   AFEventParamPrice: 4000,
>   AFEventParamContentId: "121",
>   // for multiple product categories, set the param value as: ["221", "124"],
>   AFEventParamContentType: "flight",
>   // for multiple product categories, set the param value as: ["flight", "meals"] 
>   AFEventParamCurrency: "AUD",
>   AFEventParamQuantity: 2,
>   // for multiple product categories, set the param value as: [2, 5]
>   AFEventParamOrderId: "X123ABC", 
>   AFEventParamReceiptId: "X123ABC"
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> PurchaseEvent = new Dictionary<string, string>();
> PurchaseEvent.Add("af_revenue", "1205.99");
> PurchaseEvent.Add("af_price", "4000");
> PurchaseEvent.Add("af_content_id", "121");
> // for multiple product categories, set the param value as: ["121", "124"]
> PurchaseEvent.Add("af_content_type", "flight");
> // for multiple product categories, set the param value as: ["flight", "meals"]
> PurchaseEvent.Add("af_currency", "AUD");
> PurchaseEvent.Add("af_quantity", "2");
> // for multiple product categories, set the param value as: [2, 5] 
> PurchaseEvent.Add("af_order_id", "X123ABC");
> PurchaseEvent.Add("af_receipt_id", "X123ABC");
> AppsFlyer.sendEvent ("af_purchase", PurchaseEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>
>
> ## Cấu trúc đề xuất cho các sự kiện tùy chỉnh
>
> Phần sau cung cấp danh sách các cấu trúc sự kiện bao gồm tên sự kiện tùy chỉnh và các thông số sự kiện được đề xuất sử dụng. Lưu ý rằng sự kiện trong ứng dụng có thể bao gồm bất kỳ thông số sự kiện nào đáp ứng nhu cầu kinh doanh của bạn.
>
>
> <Accordion title="Lần mua đầu tiên (first_purchase)">
>
> **Mục đích**
>
> Tương tự như sự kiện [Mua hàng](/docs/recommended-flight-booking-app-events#purchase-af_purchase). Ngoài ra, sự kiện này có thể giúp bạn xác định:
>
> * Xem khoảng thời gian cần thiết để một người mua mới tiến hành giao dịch mua
> * Xem các chuyến bay mà người mua lần đầu muốn mua
> * Xem giá và doanh thu trung bình của giao dịch mua đầu tiên
>
> **Kích hoạt**
>
> Thời điểm người dùng hoàn tất giao dịch mua đầu tiên
>
> **Thông số sự kiện**
>
>
>
> | Tên | Mô tả | Giá trị mẫu |
> | --- | --- | --- |
> | <Anchor target="_blank" href="/marketers/vi/docs/roi360-revenue-attribution-overview#technical-aspects">af\_revenue</Anchor> | Doanh thu từ giao dịch mua | 1205.99 |
> | af\_price | Tổng số tiền mua hàng | 4000 |
> | af\_content\_id | ID mặt hàng | 121, 262 |
> | af\_content\_type | Danh mục mặt hàng | flight |
> | af\_currency | Tiền tệ | AUD |
> | af\_quantity | Số lượng mặt hàng trong giỏ hàng | 1 |
> | af\_order\_id | ID đơn đặt hàng được tạo sau khi mua | X123ABC |
> | af\_receipt\_id | ID đơn đặt hàng, bắt buộc để tích hợp nhắm mục tiêu lại cho CRITEO và Google AdWords | X123ABC |
>
>
>
> **Ví dụ**
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.PRICE, 4000);
> eventValue.put(AFInAppEventParameterName.CONTENT_ID, "221");
> // for multiple product categories, set the param value as: new String {"221", "124"}
> eventValue.put(AFInAppEventParameterName.CONTENT_TYPE, "flight");
> // for multiple product categories set the param value as: new String {"flight", "meal"}
> eventValue.put(AFInAppEventParameteName.CURRENCY, "USD");
> eventValue.put(AFInAppEventParameterName.QUANTITY, 2);
> // for multiple product categories, set the param value as: new int {1}
> eventValue.put(AFInAppEventParameterName.RECEIPT_ID, "X123ABC");
> eventValue.put("af_order_id", "X123ABC");
> AppsFlyerLib.getInstance().logEvent(getApplicationContext(), "first_purchase", eventValue);
> ```
>
> </Tab>
>
> <Tab title="iOS - Objective C">
>
> ```objectivec
> [[AppsFlyerLib shared] logEvent:("first_purchase")
> withValues: @{
>   AFEventParamRevenue: @1205.99,
>   AFEventParamPrice: @4000,
>   AFEventParamContentId: @"221",
>   // for multiple product categories, set the param value as: @[@"221", @"124"]
>   AFEventParamContentType: @"flight",
>   // for multiple product categories, set the param value as: @[@"flight" , @"meal"]
>   AFEventParamCurrency: @"USD",
>   AFEventParamQuantity: @2,
>   // for multiple product categories, set the param value as: @[@1]
>   AFEventParamOrderId: @"X123ABC",
>   AFEventParamReceiptId: @"X123ABC"
> }];
> ```
>
> </Tab>
>
> <Tab title="iOS - Swift">
>
> ```swift
> AppsFlyerLib.shared().logEvent("first_purchase", withValues: [ 
>   AFEventParamRevenue: 1205.99,
>   AFEventParamPrice: 4000,
>   AFEventParamContentId: "221",
>   // for multiple product categories, set the param value as: ["221", "124"]
>   AFEventParamContentType: "flight",
>   // for multiple product categories, set the param value as: ["flight", "meal"]
>   AFEventParamCurrency: "USD",
>   AFEventParamQuantity: 2,
>   // for multiple product categories, set the param value as: // [1]
>   AFEventParamOrderId: "X123ABC",
>   AFEventParamReceiptId: "X123ABC"
> ]);
> ```
>
> </Tab>
>
> <Tab title="Unity">
>
> ```csharp
> Dictionary<string, string> FirstPurchaseEvent = new Dictionary<string, string>();
> FirstPurchaseEvent.Add("af_revenue", "1205.99");
> FirstPurchaseEvent.Add("af_price", "4000");
> FirstPurchaseEvent.Add("af_content_id", "121");
> // for multiple product categories, set the param value as: ["221", "124"]
> FirstPurchaseEvent.Add("af_content_type", "flight");
> // for multiple product categories, set the param value as: ["flight", "meal"]
> FirstPurchaseEvent.Add("af_currency", "USD");
> FirstPurchaseEvent.Add("af_quantity", "2");
> // for multiple product categories, set the param value as: [1] 
> FirstPurchaseEvent.Add("af_order_id", "X123ABC");
> FirstPurchaseEvent.Add("af_receipt_id", "X123ABC");
> AppsFlyer.sendEvent ("first_purchase", FirstPurchaseEvent);
> ```
>
> </Tab>
> </Tabs>
>
>
> </Accordion>
>