---
title: Sự kiện phong phú trong ứng dụng—Tổng quan
metadata:
  keywords:
    - ios
    - Rich
    - In-App
    - android
    - Advertisers
    - In app events
    - Marketers
    - inapp events
    - attribution
    - inapp
    - inapp events attribution
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-11-02T08:12:51Z'
  edited_at: '2023-11-09T05:09:42Z'
  id: 115005544169
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/115005544169
---
> **Khái quát:** Ghi nhận các sự kiện phong phú trong ứng dụng hậu cài đặt (chẳng hạn như đăng nhập, đăng ký hoặc mua hàng trong ứng dụng) được phân bổ cho các nguồn truyền thông và chiến dịch.

<div id="why-record-in-app-events" />

## Tại sao phải ghi nhận các sự kiện trong ứng dụng?

Sự kiện trong ứng dụng cung cấp thông tin chi tiết về những gì đang diễn ra trong ứng dụng của bạn và là công cụ lý tưởng để xác định giá trị của người dùng ứng dụng và **chất lượng của lưu lượng truy cập bắt nguồn từ các nguồn truyền thông khác nhau**. Việc ghi nhận sự kiện trong ứng dụng cho phép bạn đo lường các KPI như ROI (Lợi tức Đầu tư) và LTV (Giá trị Vòng đời).

Khi người dùng thực hiện đăng ký, xem xong hướng dẫn, thêm các mặt hàng vào giỏ hàng hoặc thực hiện mua hàng, thì dữ liệu sự kiện trong ứng dụng có thể ghi nhận các sự kiện kèm theo thông tin chi tiết. Việc triển khai các sự kiện trong ứng dụng là bắt buộc đối với tất cả các mục đích phân tích hậu cài đặt.

<div id="about-in-app-events" />

## Giới thiệu về các sự kiện trong ứng dụng

Sự kiện trong ứng dụng bao gồm tên sự kiện và có thể gồm cả các thông số sự kiện. Khi bạn thêm thông số sự kiện vào một sự kiện trong ứng dụng thì nó được gọi là sự kiện phong phú trong ứng dụng. Các thông số sự kiện cung cấp cho bạn thêm ngữ cảnh và thông tin về sự kiện đang xảy ra. Ví dụ: mặc dù giúp bạn biết rằng một người dùng đã đặt trước, nhưng các thông số sự kiện có thể cung cấp cho bạn những thông chi tiết như loại giao dịch mua, điểm đến và doanh thu.

![travel.png](https://files.readme.io/0ebe64e7aa3ccc40ef014c55ee3a91edf678e21b2d00a7f8be1298d6b494e925-30858351609617.png)

<div id="tip" />

> 👍 **Lời khuyên**
>
> Bạn muốn biết thêm về các sự kiện trong ứng dụng? Hãy xem <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7774/play/18613/in-app-events-and-integrated-partners-part-1">khóa học ngắn, bổ ích</Anchor> này trên Cổng thông tin Học tập AppsFlyer.

<div id="predefined-and-custom-events" />

<Accordion title="Các sự kiện tùy chỉnh và xác định trước">

Các sự kiện trong ứng dụng mà bạn muốn gửi yêu cầu nhà phát triển của bạn phải triển khai mã, nếu có, trong ứng dụng của bạn. Tên sự kiện và thông số sự kiện được phân loại như sau:

* **Được xác định trước**: Đây là các tên sự kiện và thông số sự kiện thường được sử dụng giữa các ứng dụng khác nhau. Bạn thực sự nên sử dụng <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-event-structure#tên-sự-kiện-được-xác-định-trước">tên sự kiện được xác định trước</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-event-structure#các-thông-số-sự-kiện-được-xác-định-trước">thông số sự kiện</Anchor> nhiều nhất có thể vì những lý do sau:
  * Việc đặt tên được xác định trước cho phép ánh xạ tự động các sự kiện tới đối tác.
  * Nếu AppsFlyer quyết định thay đổi tên của bất kỳ sự kiện hoặc thông số sự kiện nào thì việc triển khai của bạn sẽ tương thích ngược.
* **Tùy chỉnh:** Đây là các tên sự kiện và thông số mà bạn xác định cho các tình huống người dùng cụ thể xảy ra trong ứng dụng của bạn. Bạn có thể sử dụng bất kỳ tên sự kiện tùy chỉnh hoặc chuỗi tên thông số nào, nhưng hãy nhớ rằng các sự kiện tùy chỉnh cần được duy trì bởi nhà phát triển của bạn. Xem [Lời khuyên](/docs/in-app-events-overview#tips) và [Hạn chế](/docs/in-app-events-overview#limitations).

</Accordion>

<div id="revenue-events" />

<Accordion title="Sự kiện doanh thu">

Bất cứ khi nào bạn gửi các sự kiện trong ứng dụng, chẳng hạn như mua hàng hoặc đặt vé máy bay, bạn sẽ gửi sự kiện đó cùng với doanh thu liên quan. Thông số duy nhất có chứa doanh thu trong các sự kiện trong ứng dụng là`af_revenue`

* <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#record-revenue">Ghi nhận doanh thu trong SDK</Anchor>
* Ghi nhận Doanh thu trong Unity

Bạn cũng có thể ghi nhận doanh thu âm trong trường hợp người dùng hủy giao dịch mua hàng hoặc nếu bạn hoàn lại tiền. Để ghi nhận doanh thu âm, bạn chỉ cần thêm dấu trừ (-) vào giá trị doanh thu mà bạn chuyển đến`af_revenue`

**af\_revenue** là giá trị duy nhất tích lũy doanh thu của những người dùng của bạn. Luôn sử dụng giá trị này với các sự kiện trong ứng dụng đại diện cho việc tạo doanh thu thực tế trong logic kinh doanh của bạn.

**af\_revenue** cũng có thể chứa các giá trị doanh thu âm nếu bạn cần ghi nhận các sự kiện như giao dịch bị hủy hoặc hoàn lại tiền.

Giá trị doanh thu chỉ được chứa số (và dấu thập phân, nếu cần):

* **Không** bao gồm bất kỳ ký tự nào khác hoặc định dạng giá trị doanh thu theo bất kỳ cách nào khác. Điều này có nghĩa là không có dấu phẩy, ký hiệu tiền tệ f(hoặc ví dụ $), ký tự đặc biệt hoặc văn bản.
* AppsFlyer cung cấp giá trị doanh thu với **độ chính xác lên đến năm chữ số sau dấu thập phân**.
* Phạm vi của giá trị này phải là -10.000 đến 10.000 đô la hoặc số tiền gốc tương đương. Các giá trị nằm ngoài phạm vi này sẽ được đưa vào báo cáo dữ liệu thô nhưng không có trong báo cáo hợp nhất.
* Ví dụ: 1234,56
* Khi gửi doanh thu dưới dạng chuỗi, giá trị bên trong dấu ngoặc kép phải hợp lệ. Ví dụ: "1234,56".

**Lưu ý**:

* AppsFlyer hiển thị các nguồn thu chính xác như được gửi từ SDK. Doanh thu không bao gồm tính toán thuế VAT hoặc hoa hồng của cửa hàng ứng dụng, v.v. trừ khi chúng được nhà phát triển phía bên SDK thêm vào trước khi được gửi đến AppsFlyer.

**af\_currency** đại diện cho đơn vị tiền tệ được thể hiện bằng af\_revenue (hoặc af\_price). Nếu thiếu af\_currency trong các thông số của sự kiện, thì AppsFlyer sẽ gửi bằng giá trị mặc định "USD".

Bạn có thể dùng **af\_price** như một thông số tiền tệ mà không tính là doanh thu (ví dụ như trong sự kiện “Thêm vào Giỏ hàng”). Thông số này đề cập đến giá của từng mặt hàng. Tổng số tiền của tất cả các giao dịch mua sẽ xuất hiện trong thông số af\_revenue.

### Tiền tệ doanh thu

Điều quan trọng là phải hiểu cách AppsFlyer xử lý cài đặt và quy đổi đơn vị tiền tệ.

AppsFlyer xử lý chênh lệch giữa đơn vị tiền tệ trong cài đặt ứng dụng và đơn vị tiền tệ của sự kiện trong ứng dụng bằng cách quy đổi đơn vị tiền tệ.

![revenue_normalization_flow.png](https://files.readme.io/f890d34168f92202c94da4bfa548bd0f471c98dec9c8d4282b2549f5878e9321-46334674326033.png)

Sơ đồ trên thể hiện quá trình sau đây:

1. Các sự kiện trong ứng dụng được gửi - đơn vị tiền tệ khác nhau đối với mỗi sự kiện
2. AppsFlyer tiêu chuẩn hóa tất cả các đơn vị tiền tệ thành USD
3. AppsFlyer xử lý dữ liệu doanh thu
4. Dữ liệu doanh thu trong bảng điều khiển được hiển thị bằng đơn vị tiền tệ trong cài đặt ứng dụng
5. AppsFlyer điền dữ liệu doanh thu vào báo cáo dữ liệu thô bằng cả đơn vị tiền tệ trong cài đặt ứng dụng và của sự kiện

AppsFlyer sử dụng <Anchor target="_blank" href="https://openexchangerates.org/">Tỷ giá Hối đoái Mở</Anchor> để quy đổi đơn vị tiền tệ. Tỷ giá hối đoái được cập nhật theo giờ. Bất cứ khi nào AppsFlyer thực hiện quy đổi đơn vị tiền tệ, nền tảng sẽ sử dụng tỷ giá hối đoái theo lần cập nhật theo giờ gần nhất.

<div id="currency-conversion" />

#### Quy đổi đơn vị tiền tệ

<div id="h_01HDBZW9XERK3VN1GS8GHM911W" />

> 📄 **Ví dụ**
>
> Trong cài đặt ứng dụng, bạn đặt đơn vị tiền tệ là GBP. Một người dùng ở Pháp mua sản phẩm bằng ứng dụng của bạn. Giá được báo bằng đơn vị EUR (€). Sự kiện trong ứng dụng mà bạn gửi tới AppsFlyer sẽ có dạng như sau:
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.REVENUE,200);
> eventValue.put(AFInAppEventParameterName.CONTENT_TYPE,"category_a");
> eventValue.put(AFInAppEventParameterName.CONTENT_ID,"1234567");
> eventValue.put(AFInAppEventParameterName.CURRENCY,"EUR");
> AppsFlyerLib.getInstance().trackEvent(getApplicationContext() , AFInAppEventType.PURCHASE , eventValue);
> ```
>
> Trong trường hợp này, AppsFlyer quy đổi doanh thu từ EUR sang USD và sau đó sang GBP. Giả sử tỷ giá hối đoái là €1 = $1,13. Vậy €200 sẽ thành $226,85. Tiếp theo, AppsFlyer sẽ quy đổi từ USD sang GBP. Giả sử tỷ giá hối đoái là $1 = £0,78. Vậy $226,85 sẽ thành £176,92.

<div id="currency-display" />

#### Hiển thị Tiền tệ

<Anchor target="_blank" href="/marketers/vi/docs/app-settings#localization-currency">Đơn vị tiền tệ được đặt trong cài đặt ứng dụng</Anchor>. Đơn vị tiền tệ mà bạn đặt trong cài đặt ứng dụng là đơn vị tiền tệ xuất hiện trong bảng điều khiển. Bất kể bạn gửi sự kiện trong ứng dụng bằng đơn vị tiền tệ nào, doanh thu trong bảng điều khiển luôn xuất hiện bằng đơn vị tiền tệ mà bạn đã đặt trong cài đặt ứng dụng.

<div id="h_01HDBZW9XEQNG1RDH7A8H002ZD" />

> 📄 **Ví dụ**
>
> Giả sử bạn gửi các sự kiện trong ứng dụng bằng đơn vị tiền tệ khác với đơn vị tiền tệ được đặt trong cài đặt ứng dụng hoặc hoàn toàn không chỉ định bất kỳ đơn vị tiền tệ nào. Trong ví dụ này, đơn vị tiền tệ trong cài đặt ứng dụng được đặt là **GBP**.
>
> Bạn gửi ba sự kiện trong ứng dụng tới AppsFlyer.
>
> 1. Sự kiện A có doanh thu là **234** và **GBP** là đơn vị tiền tệ
> 2. Sự kiện B có doanh thu là **171** và **EUR** là đơn vị tiền tệ
> 3. Sự kiện C có doanh thu là **171** nhưng **không chỉ định đơn vị tiền tệ**
>
> #### <span id="revenue-data-in-the-dashboard"></span>Dữ liệu doanh thu trong bảng điều khiển
>
> Doanh thu xuất hiện trong bảng điều khiển là **giá trị được quy đổi** từ đơn vị tiền tệ của sự kiện trong ứng dụng sang USD, sau đó sang đơn vị tiền tệ trong cài đặt ứng dụng.
>
> Nếu không có đơn vị tiền tệ nào được chỉ định trong sự kiện, **AppsFlyer sẽ mặc định là USD**. Bảng điều khiển hiển thị sự kiện và doanh thu như sau:
>
>
>
> | Sự kiện trong ứng dụng | Người dùng duy nhất | Số hành động | Doanh thu |
> | --- | --- | --- | --- |
> | A | 1 | 1 | £234 |
> | B | 1 | 1 | £149,4 - quy đổi từ EUR sang USD và sau đó sang GBP. |
> | C | 1 | 1 | £132,9 - mặc định là USD vì không có đơn vị tiền tệ nào được chỉ định. Quy đổi trực tiếp từ USD sang GBP. |
>
>
>
> #### <span id="revenue-data-in-raw-data-reports"></span>Dữ liệu doanh thu trong báo cáo dữ liệu thô
>
> Nếu bạn đặt đơn vị tiền tệ là **GBP** trong cài đặt ứng dụng nhưng lại gửi các sự kiện trong ứng dụng bằng các đơn vị tiền tệ khác, thì báo cáo dữ liệu thô sẽ hiển thị doanh thu bằng cả đơn vị tiền tệ của cài đặt ứng dụng và đơn vị tiền tệ của sự kiện trong ứng dụng.
>
> Nếu bạn đặt đơn vị tiền tệ là **GBP** trong cài đặt ứng dụng nhưng gửi các sự kiện trong ứng dụng không chỉ định đơn vị tiền tệ nào, thì báo cáo dữ liệu thô sẽ hiển thị doanh thu bằng cả đơn vị tiền tệ của cài đặt ứng dụng và bằng USD.
>
> Báo cáo dữ liệu thô về sự kiện trong ứng dụng hiển thị sự kiện và doanh thu như sau:
>
>
>
> | Sự kiện | Doanh thu sự kiện | Tiền tệ doanh thu sự kiện | Doanh thu Sự kiện bằng GBP |
> | --- | --- | --- | --- |
> | A | 234 | GBP | 234 |
> | B | 171 | EUR | 149,4 - được quy đổi từ EUR sang USD và sau đó sang GBP. |
> | C | 171 | USD | 132,9 mặc định là USD vì không có đơn vị tiền tệ nào được chỉ định. Quy đổi trực tiếp từ USD sang GBP. |

</Accordion>

<div id="sending-events" />

## Gửi sự kiện

Có một số cách để gửi các sự kiện trong ứng dụng tới AppsFlyer:

* <Anchor target="_blank" href="/marketers/vi/docs/sdk-integration-overview">**AppsFlyer SDK:**</Anchor> Đây là cách gửi sự kiện phổ biến nhất. Bạn có thể gửi các sự kiện phong phú trong ứng dụng ghi nhận hành động của người dùng trong ứng dụng bằng API sự kiện trong ứng dụng của AppsFlyer ở cấp SDK.
* **<Anchor target="_blank" href="/marketers/vi/docs/server-to-server-events-api-for-mobile-s2s-mobile">API máy chủ đến máy chủ:</Anchor>** Sử dụng API máy chủ đến máy chủ để gửi trực tiếp các sự kiện xảy ra bên ngoài ứng dụng dành cho thiết bị di động đến AppsFlyer. Ví dụ: nếu bạn có một người dùng đang hoạt động trên cả giao diện web và thiết bị di động, bạn có thể ghi nhận các sự kiện từ cả hai nguồn và phân bổ chúng cho cùng một người dùng trong AppsFlyer. Đó có thể là sự kiện trong ứng dụng hoặc các sự kiện khác, chẳng hạn như các sự kiện trang web, sự kiện tổng đài hoặc mua hàng tại cửa hàng thực tế.
* **<Anchor target="_blank" href="/marketers/vi/docs/legacy-receipt-validation-for-in-app-purchases">Xác thực biên nhận</Anchor>:** Đây là một cơ chế bảo mật trong đó nền tảng thanh toán, chẳng hạn như Apple và Google, xác nhận rằng giao dịch mua trong ứng dụng đã diễn ra như được báo cáo. Xác thực mua là công cụ chính để ngăn chặn các sự kiện doanh thu gian lận. Đồng thời, việc này cũng giúp bạn xem doanh thu thực tế và lọc ra các hoạt động mua hàng trong ứng dụng chưa hoàn tất.
* **<Anchor target="_blank" href="/marketers/vi/docs/in-app-events-for-hybrid-apps">Ứng dụng lai</Anchor>**: Các ứng dụng này kết hợp các chế độ xem gốc và nội dung HTML và cũng có thể ghi nhận các sự kiện trong ứng dụng. Tuy nhiên, vì SDK chỉ có thể gửi các sự kiện từ phía gốc nên các nhà phát triển phải chuyển tiếp tất cả dữ liệu sự kiện sang mã gốc.

<div id="setting-up-in-app-events" />

## Thiết lập sự kiện trong ứng dụng

Quá trình thiết lập sự kiện trong ứng dụng yêu cầu nhà tiếp thị và nhà phát triển làm việc cùng nhau như sau:

| Bước | Vai trò | Nhiệm vụ | Chi tiết |
| --- | --- | --- | --- |
| 1 | Nhà tiếp thị | Xác định các sự kiện trong ứng dụng mà bạn muốn đo lường. [Xác định](/docs/in-app-events-overview#defining-an-inapp-event) và thông báo <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-event-structure#tên-sự-kiện-được-xác-định-trước">tên sự kiện</Anchor> cũng như <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-event-structure#các-thông-số-sự-kiện-được-xác-định-trước">thông số sự kiện</Anchor> cho nhà phát triển của bạn. | Bạn nên bắt đầu với 3-5 sự kiện mà bạn có thể sử dụng làm KPI để đo lường chất lượng của người dùng (ví dụ: mua hàng, đăng ký và chia sẻ). Thông số sự kiện là không bắt buộc và bạn có thể sử dụng bất kỳ thông số sự kiện nào với tên sự kiện bất kỳ.<br /><br />Xem [Các sự kiện được đề xuất theo ngành kinh doanh](/docs/in-app-events-overview#recommended-events-by-business-vertical) để biết các sự kiện trong ứng dụng tiêu biểu. |
| 2 | Nhà phát triển | Triển khai mã trong ứng dụng của bạn nếu có. | Tài liệu dành cho nhà phát triển <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk">tại đây</Anchor>. |
| 3 [Tùy chọn] | Nhà tiếp thị | Làm việc với nhà phát triển của bạn để đặt trường <Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid">Customer User ID (CUID)</Anchor>. | Trường này giúp làm phong phú thêm dữ liệu sự kiện trong ứng dụng bằng cách tham chiếu chéo dữ liệu phân bổ AppsFlyer với dữ liệu khác của bạn bằng cách sử dụng CUID làm mã khóa. |
| 4 [Tùy chọn] | Nhà tiếp thị | <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#ánh-xạ-sự-kiện">Ánh xạ sự kiện</Anchor> cho các đối tác liên quan trong bảng điều khiển. | Đây là một công việc liên tục, tùy thuộc vào các đối tác mà bạn tích hợp. |

<div id="defining-an-inapp-event" />

<Accordion title="Xác định sự kiện trong ứng dụng">

Sau khi bạn xác định các sự kiện trong ứng dụng mà bạn muốn đo lường, hãy sử dụng <Anchor target="_blank" href="https://evgen.appsflyer.com/">Trình tạo sự kiện trong ứng dụng</Anchor> của chúng tôi để xác định các sự kiện và thông số như sau:

1. Chọn tên sự kiện phù hợp nhất với tình huống bạn muốn ghi nhận.
2. Chọn các thông số sự kiện mà bạn muốn liên kết với sự kiện. Chọn các thông số sẽ cung cấp ngữ cảnh bổ sung cho sự kiện và làm phong phú dữ liệu.
3. Tải xuống tệp tin đã hoàn thành từ trình tạo sự kiện trong ứng dụng, sau đó chia sẻ tệp tin đó với nhà phát triển của bạn.

<div id="h_01HDBZW9XFN2B8AC18VW99G8Z6" />

> 📄 **Ví dụ**
>
> Nhà tiếp thị cho ứng dụng Thương mại điện tử muốn ghi nhận loại nội dung mà người dùng xem để hiểu rõ hơn những danh mục nào phổ biến nhất và kết nối lượt xem sản phẩm với doanh số bán sản phẩm.
>
> Bảng sau đây thể hiện một ví dụ về cấu trúc sự kiện mà nhà tiếp thị chuyển cho nhà phát triển:
>
> <table><thead><tr><th>Tên của sự kiện</th><th>Thông số sự kiện</th><th>Giá trị thông số</th><th>Sự kiện được kích hoạt khi nào?</th></tr></thead><tbody><tr><td rowspan="3">af_content_view</td><td>af_price</td><td>Giá sản phẩm</td><td rowspan="3"><p><span>Thời điểm người dùng xem trang chi tiết của một sản phẩm cụ thể</span></p></td></tr><tr><td><span>af_content_type</span></td><td><span>Tên của danh mục sản phẩm, ví dụ: giày </span></td></tr><tr><td><span>af_content_id</span></td><td><p><span>ID sản phẩm, ví dụ: SKU</span></p></td></tr></tbody></table>

</Accordion>

<div id="recommended-events-by-business-vertical" />

<Accordion title="Các sự kiện được đề xuất theo ngành kinh doanh">

Bảng sau cung cấp đường liên kết đến các bài viết gồm các ví dụ và luồng của các sự kiện trong ứng dụng tiêu biểu mà chúng tôi đề xuất bạn nên ghi nhận theo ngành dọc.

| Ngành kinh doanh | Tiêu đề bài viết |
| --- | --- |
| <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="38px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-gaming-app-events">Các sự kiện ứng dụng trò chơi được đề xuất</Anchor> |
| <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="37px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-ecommerce-app-events">Các sự kiện ứng dụng Thương mại điện tử được đề xuất</Anchor> |
| <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="39px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-entertainment-app-events">Các sự kiện ứng dụng giải trí được đề xuất</Anchor> |
| <Image alt="banking.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="36px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-finance-and-banking-app-events">Các sự kiện ứng dụng tài chính và ngân hàng được đề xuất</Anchor> |
| <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="36px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-p2p-lending-app-events">Các sự kiện ứng dụng cho vay P2P được đề xuất</Anchor> |
| <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="37px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-online-education-app-events">Các sự kiện ứng dụng giáo dục trực tuyến được đề xuất</Anchor> |
| <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="37px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-ride-hailing-app-events">Các sự kiện trong ứng dụng gọi xe được đề xuất</Anchor> |
| <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="38px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-flight-booking-app-events">Các sự kiện ứng dụng đặt vé máy bay được đề xuất</Anchor> |
| <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="37px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-hotel-booking-app-events">Các sự kiện ứng dụng đặt phòng khách sạn được đề xuất</Anchor> |
| <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="37px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-healthcare-app-events">Các sự kiện ứng dụng chăm sóc sức khỏe được đề xuất</Anchor> |
| <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="39px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-telecommunication-app-events">Các sự kiện ứng dụng viễn thông được đề xuất</Anchor> |
| <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="39px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-ewallet-app-events">Các sự kiện ứng dụng eWallet được đề xuất</Anchor> |
| <Image alt="soccer_ball.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="39px" /> | <Anchor target="_blank" href="/marketers/vi/docs/recommended-sports-betting-events">Các sự kiện cá cược thể thao được đề xuất</Anchor> |

</Accordion>

<div id="view-inapp-event-data" />

<Accordion title="Xem dữ liệu sự kiện trong ứng dụng">

Các sự kiện trong ứng dụng được phân bổ cho nguồn truyền thông chịu trách nhiệm cài đặt trong suốt vòng đời của người dùng. Dữ liệu sự kiện được trình bày dưới dạng <Anchor target="_blank" href="/marketers/vi/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">dữ liệu Hoạt động hoặc Giá trị Trọn đời</Anchor>.

Bạn có thể xem dữ liệu sự kiện trong ứng dụng của mình ở các vị trí sau:

* Trang bảng điều khiển tổng quan: Hiển thị hiệu suất thu hút người dùng LTV (UA) theo thời gian thực. **Lưu ý**: Điều này bao gồm cả doanh thu được phân chia giữa người dùng tự nhiên và người dùng không tự nhiên được báo cáo thông qua các sự kiện trong ứng dụng và doanh thu nhắm mục tiêu lại được <Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">phân bổ kép.</Anchor>
* Trang sự kiện: Hiển thị hiệu suất LTV sự kiện trong ứng dụng trên các nguồn truyền thông
* <Anchor target="_blank" href="/marketers/vi/docs/activity-dashboard">Trang hoạt động</Anchor>: Hiển thị các hoạt động trong ứng dụng đối với phạm vi ngày đã chọn.
* <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">Báo cáo sự kiện trong ứng dụng dữ liệu thô</Anchor>: Hiển thị dữ liệu hoạt động, nghĩa là, một danh sách theo thứ tự thời gian về các hoạt động được thực hiện bởi toàn bộ cơ sở người dùng của bạn. Báo cáo này bao gồm các giá trị thông số sự kiện, ví dụ:

  ```json
  {
    "af_level":"10",
    "af_score":"3387",
    "arena":"7",
    "char_type":"paladin"
  }
  ```

  Lưu ý rằng báo cáo dữ liệu thô là một tính năng cao cấp.

</Accordion>

<div id="tips" />

<Accordion title="Lời khuyên">

Hãy lưu ý những chi tiết sau khi xác định tên và thông số sự kiện trong ứng dụng:

* Để có tính nhất quán về dữ liệu trong báo cáo dữ liệu thô thì bạn nên xác định và sử dụng cùng một cấu trúc và tên sự kiện trong ứng dụng trên tất cả các nền tảng.
* Sử dụng số lượng sự kiện tối thiểu để dễ dàng so sánh chất lượng của người dùng đến từ nhiều nguồn khác nhau.
* **Điều quan trọng là bạn phải đảm bảo quyền riêng tư của người dùng.** **Không điền các giá trị sự kiện trong ứng dụng cùng dữ liệu bị hạn chế có thể bị nhận dạng trực tiếp**. **Ví dụ: địa chỉ email, tên, mã số nhận dạng và mã bưu chính ở một số địa điểm. Để biết thêm thông tin về dữ liệu bị hạn chế, hãy đọc <Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">chính sách quyền riêng tư của dịch vụ</Anchor>.**
* AppsFlyer thu thập địa chỉ IP của thiết bị trong <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">quá trình tương tác</Anchor>. Trong một số khu vực pháp lý hoặc các trường hợp sử dụng, địa chỉ IP có thể được coi là PII. Chúng tôi sử dụng địa chỉ IP để lấy vị trí địa lý rộng (cấp thành phố, quận) của thiết bị nhưng không sử dụng địa chỉ cụ thể. Nếu cần, bạn có thể chọn <Anchor target="_blank" href="/marketers/vi/docs/apply-ip-masking-to-user-data">ẩn địa chỉ IP</Anchor> để chúng không xuất hiện trong báo cáo dữ liệu thô.
* Sự kiện trong ứng dụng là nguồn dữ liệu doanh thu duy nhất trên AppsFlyer. Bạn có thể gắn một giá trị doanh thu cụ thể cho từng sự kiện và xem nó trên bảng điều khiển của ứng dụng. Tìm hiểu thêm về các [thông số kiếm tiền](/docs/in-app-events-overview#revenue-events).

  ![revenue_data.png](https://support.appsflyer.com/hc/article_attachments/360020607037)

</Accordion>

<div id="limitations" />

<Accordion title="Điểm hạn chế">

Hãy lưu ý những chi tiết sau khi xác định tên và thông số sự kiện trong ứng dụng:

* Chúng tôi khuyến nghị bạn nên sử dụng các ký tự chữ và số viết thường (a-z và 0-9) cho tên sự kiện trong ứng dụng của mình. Tên sự kiện có phân biệt chữ hoa và chữ thường, nghĩa là af\_purchase và af\_PURCHASE là hai sự kiện khác nhau trong dữ liệu thô. Tuy nhiên, trong các báo cáo hợp nhất (ví dụ: Tổng quan hoặc Sự kiện), chúng có thể được hiển thị dưới dạng một sự kiện.
* Giới hạn số lượng giá trị trong một tập hợp là 300 sự kiện duy nhất trong một ngày. <Anchor target="_blank" href="/marketers/vi/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_events_limit">Tìm hiểu thêm</Anchor>
* Người dùng duy nhất chỉ được tính cho 100 sự kiện đầu tiên sau khi họ cài đặt ứng dụng.
* Tên sự kiện không được bắt đầu bằng các ký tự sau: " = + -
* Các giá trị sự kiện không được chứa ký tự +, ngoại trừ trong các URL được mã hóa hoặc được mã hóa theo <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">ASCII</Anchor>.
* Tên sự kiện không được chứa dấu cách. Bạn có thể sử dụng dấu cách gạch dưới (dấu gạch ngang dưới) trước hoặc sau tên của sự kiện.
* Các giá trị của sự kiện không được vượt quá 2000 ký tự vì chúng có thể bị rút gọn trong báo cáo dữ liệu thô.
* Nếu bạn thêm URL giới thiệu làm giá trị sự kiện, thì đó phải là <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">URL được mã hóa</Anchor>.
* Quảng cáo Meta có một số hạn chế về tên và thông số sự kiện. Đọc về những hạn chế đó <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#limits">tại đây</Anchor>.

</Accordion>

<div id="faq" />

## Câu hỏi thường gặp

Phần sau bao gồm các Câu hỏi thường gặp về sự kiện trong ứng dụng.

<div id="how-do-i-use-the-revenue-parameter" />

<Accordion title="Làm cách nào để sử dụng thông số doanh thu?">

Bạn có thể gửi giá trị doanh thu với bất kỳ tên thông số và sự kiện nào. Tuy nhiên, để đăng ký doanh thu (bao gồm [doanh thu âm](/docs/in-app-events-overview#revenue-events)) trong dữ liệu thô và hợp nhất của AppsFlyer, bạn PHẢI sử dụng thông số ***af\_revenue***. Luôn sử dụng giá trị này với các sự kiện trong ứng dụng đại diện cho việc tạo doanh thu thực tế trong logic kinh doanh của bạn.

**af\_currency** đại diện cho đơn vị tiền tệ được trình bày trong **af\_revenue** (hoặc **af\_price**). Nếu thiếu **af\_currency** trong các thông số của sự kiện, thì AppsFlyer sẽ gửi bằng giá trị mặc định "USD".

Để biết thêm thông tin về thông số ***af\_revenue***, hãy xem [hướng dẫn Phân bổ Doanh thu](/docs/in-app-events-overview#revenue-events).

</Accordion>

<div id="how-does-appsflyer-attribute-events" />

<Accordion title="AppsFlyer phân bổ sự kiện như thế nào?">

Các sự kiện trong ứng dụng được phân bổ cho nguồn truyền thông ban đầu của lượt cài đặt ứng dụng.

Khi cài đặt một ứng dụng (khởi chạy ứng dụng lần đầu) AppsFlyer sử dụng nhiều <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#phương-thức-phân-bổ">phương thức phân bổ</Anchor> khác nhau để xác định lượt cài đặt được phân bổ như thế nào. Đồng thời, SDK AppsFlyer tạo một <Anchor target="_blank" href="/marketers/vi/docs/about-device-identifiers#appsflyer-id">ID AppsFlyer</Anchor> mới duy nhất, được liên kết với các thông tin chi tiết về phân bổ.

Mọi sự kiện trong ứng dụng sau đó do cùng một thiết bị trong ứng dụng thực hiện đều có ID này. Điều này cho phép AppsFlyer phân bổ sự kiện cho nguồn truyền thông ban đầu. Các nhà quảng cáo có thể sử dụng điều này để theo dõi toàn bộ hành trình của người dùng trong ứng dụng của họ.

Sự kiện của những người dùng được nhắm mục tiêu lại gần đây có thể bị <Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">phân bổ hai lần</Anchor>.

AppsFlyer phân bổ các sự kiện lượt cài đặt được phân bổ là **tự nhiên** khi:

* Hơn 24 tháng sau ngày cài đặt
* Các điều khoản của nguồn truyền thông [quy định việc xóa dữ liệu ở mức người dùng](/docs/in-app-events-overview#how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations)
* Người dùng xóa dữ liệu được lưu trữ của ứng dụng trên thiết bị, buộc phải tạo ID AppsFlyer mới.

</Accordion>

<div id="are-events-recorded-if-a-device-is-offline" />

<Accordion title="Các sự kiện có được ghi nhận nếu thiết bị đang ngoại tuyến không?">

Nếu người dùng bắt đầu một sự kiện khi không có kết nối internet, Appsflyer vẫn có thể ghi nhận nó. Đây là cách thức hoạt động:

1. SDK gửi các sự kiện đến máy chủ AppsFlyer và chờ phản hồi thành công.
2. Nếu SDK không nhận được phản hồi thành công thì sự kiện sẽ được lưu trữ trong bộ nhớ đệm.
3. Khi nhận được phản hồi thành công tiếp theo thì sự kiện đã lưu trữ sẽ được gửi lại đến máy chủ.
4. Nếu có nhiều sự kiện trong bộ nhớ đệm thì chúng sẽ được gửi lần lượt đến máy chủ.

<div id="note-3" />

> 📘 **Lưu ý**
>
> Bộ nhớ đệm của SDK có thể lưu trữ tối đa 40 sự kiện, có nghĩa là chỉ lưu được 40 sự kiện đầu tiên xảy ra ngoại tuyến. Tất cả mọi thứ xảy ra sau đó, cho đến phản hồi thành công tiếp theo, sẽ bị loại bỏ.
>
> Thời gian sự kiện xuất hiện trong dữ liệu thô là thời gian mà sự kiện được gửi tới AppsFlyer sau khi thiết bị được kết nối internet trở lại. Đây không phải là thời gian thực tế mà sự kiện diễn ra.

</Accordion>

<div id="what-are-complex-inapp-events-and-how-do-i-set-them-up" />

<Accordion title="Các sự kiện phức tạp trong ứng dụng là gì và làm cách nào để thiết lập chúng?">

Sự kiện phức tạp trong ứng dụng cho phép gửi nhiều sự kiện trong một lệnh gọi API duy nhất.

Tính năng này rất hữu ích khi bạn muốn xem một số hoạt động của người dùng có liên quan chặt chẽ với nhau đã được nhóm cùng với nhau (ví dụ: thêm một vài sản phẩm vào giỏ trong một phiên duy nhất).  
Ví dụ:

```json
{
  "af_revenue":"50.87",
  "af_currency":"USD",
  "af_receipt_id":"57601333",
  "product":[ 
   { 
	 "af_content_id":"1164_8186",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"1164_8186",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"1164_8186",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"1177_8185",
	 "af_price":"8.97",
	 "af_quantity":"1"
   },
   { 
	 "af_content_id":"0153_9077",
	 "af_price":"14.99",
	 "af_quantity":"1"
   }
  ]
}
```

> ❗️ **Chú ý**
>
> Các sự kiện phức tạp trong ứng dụng gây ra các vấn đề về đăng lại với quảng cáo Meta và Criteo. Nếu cần sự kiện được ánh xạ đầy đủ với quảng cáo Meta và Criteo, bạn hãy gửi các sự kiện riêng lẻ cho từng hoạt động của người dùng (ví dụ: gửi sự kiện Thêm vào giỏ hàng cho từng mặt hàng được thêm). Sử dụng dữ liệu thô của sự kiện trong ứng dụng để nhóm các sự kiện này lại với nhau.

</Accordion>

<div id="can-i-add-multiple-items-to-a-single-transaction" />

<Accordion title="Tôi có thể thêm nhiều mặt hàng vào một giao dịch không?">

Bạn có thể thêm nhiều mục vào một giao dịch duy nhất. Thay vì các giá trị duy nhất cho mỗi thông số sự kiện, bạn có thể có nhiều mục mô tả giao dịch, được phân tách bởi dấu phẩy. Định dạng phải là một chuỗi JSON.

> 📄 **Ví dụ**
>
> Trong cùng một giao dịch, ông Smith mua hai chiếc áo sơ mi giống hệt nhau, một đôi giày và một chiếc mũ từ một cửa hàng trực tuyến tại Hoa Kỳ. Trình tự liệt kê từng mặt hàng phải giống hệt từng thông số.
>
> ```json
> "{\"af_content_id\": [\"123\",\"988\",\"399\"], \"af_quantity\": [\"2\",\"1\",\"1\"], \"af_price\": [\"25\",\"50\",\"10\"], \"af_revenue\": \"110\", \"af_currency\": \"USD\"}"
> ```
>
> Nhiều mục được gửi từ giờ về sau dưới dạng một mảng trong <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration">đăng lại</Anchor>. Hiện tại quảng cáo Meta và Twitter không thể phân tích các thông số mảng chính xác. Để hỗ trợ vấn đề này, AppsFlyer tổng hợp số lượng các mục (af\_quantity) thay vì gửi nó đến các SRN này dưới dạng một mảng. Trong ví dụ của chúng tôi, quảng cáo Meta sẽ nhận thông số **af\_quantity=4**.
>
> **Lưu ý**
>
> Nhiều mặt hàng có thể được dùng với các sự kiện trong ứng dụng sau:
>
> af\_add\_to\_cart, af\_add\_to\_wishlist, af\_tutorial\_completion, af\_initiated\_checkout, af\_purchase, af\_rate, af\_spent\_credits, af\_content\_view, af\_travel\_booking, af\_update



</Accordion>

<div id="how-does-appsflyer-handle-event-deduplication" />

<Accordion title="AppsFlyer xử lý sự kiện trùng lặp như thế nào?">

Chúng tôi có cơ chế loại bỏ trùng lặp sự kiện trong ứng dụng. Nó sẽ kiểm tra tất cả các sự kiện trong ứng dụng để xem có sự kiện trong ứng dụng giống hệt xuất phát từ cùng một appsflyer\_id ít hơn 10 giây trước hay không. Nếu tìm thấy sự kiện này, cơ chế đó sẽ loại bỏ trùng lặp.

Hai sự kiện được coi là giống hệt nhau nếu các trường sau đây trong cả hai sự kiện giống nhau:

* Tên của sự kiện
* Giá trị của sự kiện
* ID ứng dụng
* ID AppsFlyer

<div id="note-4" />

<div id="notes" />

> 📘 **Lưu ý**
>
> Hủy trùng lặp chỉ hoạt động với các sự kiện trong ứng dụng được gửi từ SDK.
>
> Các sự kiện trong ứng dụng S2S không được hủy trùng lặp.

</Accordion>

<div id="how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations" />

<Accordion title="AppsFlyer lưu giữ dữ liệu cấp người dùng trong bao lâu và nghĩa vụ xóa dữ liệu như thế nào?">

AppsFlyer lưu giữ (dữ liệu thô) cấp người dùng trong 24 tháng trừ trường hợp có chỉ dẫn, yêu cầu hoặc cho phép khác theo luật định. Một số SRN/đối tác yêu cầu nhà cung cấp phân bổ, bao gồm AppsFlyer, xóa SRN/dữ liệu cấp người dùng liên quan đến đối tác trước khi hết thời hạn 24 tháng.

Sau khi xóa, các sự kiện liên quan đến người dùng đã xóa hiển thị dưới dạng tự nhiên. Dữ liệu hợp nhất trong quá khứ không bị thay đổi. Để biết thêm thông tin, hãy xem phần <Anchor target="_blank" href="/marketers/vi/docs/user-level-data-retention#data-retention-and-deletion-obligations">Nghĩa vụ lưu giữ và xóa dữ liệu</Anchor>.

</Accordion>

<div id="do-i-need-to-add-the-os-operating-system-parameter-to-my-events" />

<Accordion title="Tôi có cần thêm thông số OS (hệ điều hành) vào các sự kiện của mình không?">

* SDK Android và SDK iOS tự động thêm thông số OS (hệ điều hành).
* Đối với <Anchor target="_blank" href="/marketers/vi/docs/server-to-server-events-api-for-mobile-s2s-mobile">API S2S</Anchor>, bắt đầu từ ngày 1 tháng 7 năm 2021, bạn phải gửi thông số OS (hệ điều hành) cho các ứng dụng iOS. Nếu bạn không gửi thông số này, dữ liệu được coi là đến từ người dùng iOS 14.5 và điều này ảnh hưởng đến phương thức <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">cung cấp dữ liệu thô</Anchor>.

</Accordion>

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration">Cấu hình đăng lại sự kiện trong ứng dụng</Anchor>

<div data-zendesk-anchors="why-record-inapp-events=t%E1%BA%A1i-sao-ph%E1%BA%A3i-ghi-nh%E1%BA%ADn-c%C3%A1c-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HDBZW9XEBTY13MG4AN93RNCD=t%E1%BA%A1i-sao-ph%E1%BA%A3i-ghi-nh%E1%BA%ADn-c%C3%A1c-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng about-inapp-events=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-c%C3%A1c-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HDBZW9XEBDSDA9T5X5B6KGTG=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-c%C3%A1c-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HDBZW9XE3Z40JE9576C4XSF4=l%E1%BB%9Di-khuy%C3%AAn h_01HDBZW9XEMV1EFY7CEE7N1GZV=predefined-and-custom-events h_01HDBZW9XEZWDDHFATKY6KDN25=revenue-events revenue-currency=ti%E1%BB%81n-t%E1%BB%87-doanh-thu h_01HDBZW9XEMPVG76PJQN7WDAT6=ti%E1%BB%81n-t%E1%BB%87-doanh-thu currency-conversion=quy-%C4%91%E1%BB%95i-%C4%91%C6%A1n-v%E1%BB%8B-ti%E1%BB%81n-t%E1%BB%87 h_01HDBZW9XEMGA5RAW0DBBPV3FQ=quy-%C4%91%E1%BB%95i-%C4%91%C6%A1n-v%E1%BB%8B-ti%E1%BB%81n-t%E1%BB%87 h_01HDBZW9XERK3VN1GS8GHM911W=v%C3%AD-d%E1%BB%A5 currency-display=hi%E1%BB%83n-th%E1%BB%8B-ti%E1%BB%81n-t%E1%BB%87 h_01HDBZW9XE85YC3JHG58YYAB8F=hi%E1%BB%83n-th%E1%BB%8B-ti%E1%BB%81n-t%E1%BB%87 h_01HDBZW9XEQNG1RDH7A8H002ZD=v%C3%AD-d%E1%BB%A5-1 revenue-data-in-the-dashboard=d%E1%BB%AF-li%E1%BB%87u-doanh-thu-trong-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n h_01HDBZW9XEVWB9045N0YEVWE6Z=d%E1%BB%AF-li%E1%BB%87u-doanh-thu-trong-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n revenue-data-in-raw-data-reports=d%E1%BB%AF-li%E1%BB%87u-doanh-thu-trong-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 h_01HDBZW9XEGYFD3W9FT1N3ZGQW=d%E1%BB%AF-li%E1%BB%87u-doanh-thu-trong-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 sending-events=g%E1%BB%ADi-s%E1%BB%B1-ki%E1%BB%87n h_01HDBZW9XFESG6MP9QF1XCJKE6=g%E1%BB%ADi-s%E1%BB%B1-ki%E1%BB%87n setting-up-inapp-events=thi%E1%BA%BFt-l%E1%BA%ADp-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HDBZW9XF13AGRCN2HJ18RHS2=thi%E1%BA%BFt-l%E1%BA%ADp-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HDBZW9XF6X9H4WCFWC28W1CD=defining-an-inapp-event h_01HDBZW9XFN2B8AC18VW99G8Z6=v%C3%AD-d%E1%BB%A5-2 h_01HDBZW9XFM33BYF90EJPQ35V9=recommended-events-by-business-vertical h_01HDBZW9XF6G2R6Y6S5GFNDM6W=view-inapp-event-data h_01HDBZW9XF1Q1NB1YS8Q0HKA6K=tips h_01HDBZW9XFFNWCJ18NETEM2287=limitations faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p h_01HDBZW9XF5H24H2HCJKKHCRTE=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p h_01HDBZW9XF5ZNGVEMND08137PR=how-do-i-use-the-revenue-parameter h_01HDBZW9XFZ144ND2FXW2AMGRW=how-does-appsflyer-attribute-events h_01HDBZW9XFDBFY580P939ZP0D4=are-events-recorded-if-a-device-is-offline h_01HDBZW9XFCDMKNWJ75AWHC2Y0=l%C6%B0u-%C3%BD h_01HDBZW9XF8Q57JZPD8J2Y25SB=what-are-complex-inapp-events-and-how-do-i-set-them-up h_01HDBZW9XF33FHR418MNVH6BS2=ch%C3%BA-%C3%BD h_01HDBZW9XFRAFSXJE5N5ZPRW2R=can-i-add-multiple-items-to-a-single-transaction h_01HDBZW9XFB9TAT8W4CGNP1892=v%C3%AD-d%E1%BB%A5-3 h_01HDBZW9XFJ68WSM3066NVRATS=l%C6%B0u-%C3%BD-1 h_01HDBZW9XFGMG5B5FG2785ERAM=how-does-appsflyer-handle-event-deduplication h_01HDBZW9XFWKN7W90PSVMX73FS=l%C6%B0u-%C3%BD-1 h_01HDBZW9XFFXXBYY14A3QGENSF=how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations h_01HDBZW9XFH80JK748PAPG09B5=do-i-need-to-add-the-os-operating-system-parameter-to-my-events h_01HDNZ708FN0N286R5HDQGMNGZ=xem-th%C3%AAm" />
