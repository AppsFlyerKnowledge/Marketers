---
title: Cấu hình chiến dịch Trade Desk
metadata:
  keywords:
    - Advertisers
    - The Trade Desk
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-05-13T07:34:13Z'
  edited_at: '2023-12-07T17:40:12Z'
  id: 360000894849
  locale: vi
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/vi/articles/360000894849
---
> **Khái quát:** The Trade Desk, một đối tác tích hợp mạng quảng cáo của AppsFlyer, sử dụng giải pháp quảng cáo di động nâng cao của mình để phát triển các chiến dịch chiến lược, thông minh và có khả năng mở rộng nhằm đáp ứng nhu cầu của người dùng sử dụng nhiều thiết bị. The Trade Desk cung cấp phân bổ di động dựa trên lượt nhấp, phân bổ di động lượt xem qua và nhắm mục tiêu lại dựa trên lượt nhấp, tất cả đều có thể được ghi nhận thông qua AppsFlyer.

## Thiết lập The Trade Desk (TTD)

Thực hiện theo các bước sau để bật tính năng đo lường chiến dịch AppsFlyer.

<div id="step-1-define-conversion-events-in-ttd" />

<Accordion title="Bước 1: Xác định sự kiện chuyển đổi trong TTD">

1. Trên menu bên trái của trang nhà quảng cáo TTD của bạn, hãy nhấp vào **DATA**.
2. Từ menu trên cùng, nhấp vào **Add App Data**.
3. Nhập các trường sau trên trang **Create App Data**:
   * **App Name:** Nhập tên của ứng dụng.
   * **Operating System:** Chọn **Android** hoặc **iOS**.   
     **Lưu ý:** TTD hỗ trợ CTV trong cả 2 tùy chọn Android và iOS.
   * **Tracking Vendor:** Chọn **AppsFlyer**.
   * **Events:** Nhấp vào **ADD EVENT** để thêm sự kiện chuyển đổi và nhập các trường:
     * **EVENT NAME**: Nhập tên sự kiện.  
       **Lưu ý:** Đảm bảo tên được viết giống hệt như trong AppsFlyer, bao gồm cả viết hoa, dấu cách và ký hiệu.
     * [Tùy chọn] **DESCRIPTION**: Thêm mô tả.
     * [Tùy chọn] **USAGE OF COLLECTED DATA**: Chọn **Attribution**. Tùy chọn này bao gồm cả phân bổ và nhắm mục tiêu lại.
     * Để thêm nhiều sự kiện hơn, hãy nhấp vào **ADD EVENT** và lặp lại quy trình.
   * **Conversion Credit Source**: Chọn nguồn để phân bổ chuyển đổi, tức là AppsFlyer hoặc The Trade Desk.   
     **Lưu ý:**
     * Để đo lường trên nhiều thiết bị và lượng mua TTD, hãy chọn **The Trade Desk**.   
       Để có cái nhìn tổng thể về đo lường không chỉ trong TTD, hãy chọn **AppsFlyer**.
     * Không bao giờ thay đổi lựa chọn này trong một chiến dịch.
     * Đảm bảo chọn đúng nguồn trước khi nhấp vào **CREATE APP DATA**. Bạn không thể thay đổi nguồn được tính lượt chuyển đổi của mình trong chiến dịch.
4. Nhấp vào **CREATE APP DATA**.

</Accordion>

<div id="step-2-define-conversion-events-in-appsflyer" />

<Accordion title="Bước 2: Xác định sự kiện chuyển đổi trong AppsFlyer">

Để AppsFlyer xác định các sự kiện chuyển đổi và cho phép bạn gửi bài đăng lại sự kiện tới TTD, trước tiên bạn phải [tích hợp TTD với AppsFlyer](/docs/the-trade-desk-campaign-configuration#tích-hợp-ttd-với-appsflyer) và thiết lập các cấu hình sau:

* Cài đặt tích hợp (bao gồm cả cấu hình đăng lại sự kiện)
* Đường dẫn phân bổ
* Quyền

</Accordion>

<div id="step-3-map-defined-conversion-events-from-appsflyer" />

<Accordion title="Bước 3: Ánh xạ các sự kiện chuyển đổi được xác định từ AppsFlyer">

1. Từ menu bên trái của TTD, hãy nhấp vào **CAMPAIGNS**.
2. Cuộn xuống đến **Campaigns** và chọn một chiến dịch từ danh sách.
3. Nhấp vào **Edit Reporting & Attribution**.
4. Nhấp vào **ADD CONVERSION DATA SOURCE**.
5. Trong **CONVERSION DATA SOURCE**, chọn hoặc nhập **AppsFlyer**. Các sự kiện AppsFlyer hiện được ánh xạ tới các sự kiện TTD.
6. **KHÁI NIỆM VỀ TRÊN NHIỀU THIẾT BỊ**:
   * Nếu bạn đã chọn ở [Bước 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) (Nguồn Được tính Lượt chuyển đổi) là để lượt chuyển đổi được TTD phân bổ, hãy chọn ở đây **Household** để xem lượt chuyển đổi trong tất cả các kênh có sẵn (chẳng hạn như trong ứng dụng dành cho thiết bị di động và CTV).
   * Nếu bạn đã chọn AppsFlyer ở [Bước 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd), hãy chọn ở đây **None**.
7. Nhấp vào **SAVE**.

</Accordion>

<div id="step-4-add-click-and-impression-trackers-to-campaign-creatives" />

<Accordion title="Bước 4: Thêm trình theo dõi lượt nhấp và lượt hiển thị vào quảng cáo chiến dịch">

Trong bước này, bạn sẽ thêm các trình theo dõi lượt nhấp và lượt hiển thị đã được tạo trong AppsFlyer vào từng quảng cáo trong TTD.

1. Trong **CAMPAIGNS** ở menu bên trái của TTD, hãy nhấp vào **CREATIVES** từ thẻ trên cùng.
2. Chọn một quảng cáo từ danh sách quảng cáo được liên kết với chiến dịch hiện tại.
3. Cuộn xuống đến **Tracking**.
4. Sao chép các [đường dẫn phân bổ](/docs/the-trade-desk-campaign-configuration#attribution-link-tab) (lượt nhấp và lượt xem) từ AppsFlyer và dán chúng vào từng trường **1x1 Pixel Impression Tracking URL**.
5. Nhấp vào **SAVE CHANGES**.
6. Lặp lại bước này cho từng quảng cáo được liên kết với chiến dịch.

</Accordion>

> 📘 **Lưu ý**
>
> Nếu bạn đã chọn để các lượt chuyển đổi sẽ do TTD phân bổ (ở [Bước 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd)), bạn có thể chỉnh sửa khung thời gian phân bổ:
>
> 1. Từ menu biểu tượng ở bên phải của bất kỳ trang TTD nào, hãy nhấp vào bánh răng để mở **Tùy chọn Nhà quảng cáo**.
> 2. Cuộn xuống đến **Attribution Windows** và nhấp vào nút chỉnh sửa ở bên phải.
> 3. Từ trang **Manage Attribution Windows**, hãy chỉnh sửa khung thời gian phân bổ:
>    * **De-duplication Windows:** Số lượt chuyển đổi bạn có thể thấy trong một khoảng thời gian nhất định.
>    * **Campaign Attribution Windows:** Khoảng thời gian từ khi hiển thị quảng cáo đến khi chuyển đổi.
> 4. Nhấp vào **SAVE**.

## Tích hợp TTD với AppsFlyer

Quá trình thiết lập được thực hiện từ trang **Active** **Integrations**, nhưng để tìm đối tác, trước tiên bạn phải truy cập vào <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations">marketplace</Anchor>.

**Để kích hoạt tích hợp:**

1. Truy cập Marketplace: Từ menu trên cùng của bất kỳ trang AppsFlyer nào, hãy nhấp vào **Marketplace**.
2. Tìm kiếm và chọn đối tác.
3. Nhấp vào **Set up integration**. Bạn được chuyển đến trang thiết lập tích hợp.
4. Trong tab **Integration**, bật tùy chọn **Activate partner**.  
   **Lưu ý:** Nút bật/tắt phải luôn ở trạng thái bật (<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">được kích hoạt</Anchor>) trong thời gian bạn làm việc với đối tác.
5. Hoàn thành cấu hình bằng cách sử dụng các tab có liên quan, như được mô tả bên dưới.

Cửa sổ cấu hình TTD bao gồm ba thẻ hoạt động: Integration, Attribution link và Permissions. Nhấp vào các mục bên dưới để đọc về thiết lập các tab.

Để biết mô tả chi tiết về Tiêu đề Cửa sổ Cấu hình Đối tác, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">đây</Anchor>.

<div id="integration-tab" />

<Accordion title="Tab tích hợp">

#### Kích hoạt đối tác

Trong lần truy cập đầu tiên, bạn sẽ cần bật nút bật/tắt **Activate partner** để thiết lập tích hợp. Nút chuyển đổi phải ở trạng thái bật trong thời gian bạn làm việc với TTD.  
Để biết thêm chi tiết về kích hoạt đối tác, vui lòng nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">đây</Anchor>.

#### Quyền riêng tư Nâng cao

Đối với các ứng dụng iOS, nút bật/tắt <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Enable Advance Privacy</Anchor> sẽ xuất hiện. Khi được bật, tính năng này sẽ giới hạn việc chia sẻ mã định danh người dùng với đối tác. Lưu ý rằng khi bật nút chuyển đổi <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Aggregated Advanced Privacy</Anchor> trong Cài đặt của Ứng dụng, **Enable Advanced Privacy** sẽ được bật và khóa theo mặc định. 

#### Cài đặt chung

**Trình theo dõi và ID nhà quảng cáo**

The Trade Desk kết nối với AppsFlyer thông qua ID mạng duy nhất. Nếu bạn chưa có Tracker\_ID và advertiserid, bạn phải lấy chúng từ The Trade Desk để tiếp tục quá trình tích hợp.

![TTD_General_Settings_.png](https://files.readme.io/f7f2b66556f2713ff56a3bd2fcfe6fe8fe8d346a9b322904f93670ee55cf94c3-50612291000849.png)

**Kích hoạt Phân bổ Lượt xem**

Bật **Enable View-Through attribution** để phân bổ lượt cài đặt lượt xem từ The Trade Desk. Thanh trượt xem lại lượt xem qua có sẵn trên thẻ đường dẫn phân bổ (mô tả dưới đây).

#### Postback Mặc định

![default_postbacks_en-us.png](https://files.readme.io/b291c9fd4ac858723f3071bf271a041403639d49bfb1984030fc7c7306c40c16-50612291002385.png)

Gửi bài đăng lại tự động đến The Trade Desk sau lượt cài đặt và thu hút lại của người dùng. Sử dụng phần này để xác định nguồn của người dùng cho phép gửi các bài đăng lại này:

* **This partner only**: chỉ dành cho các sự kiện đến từ người dùng được phân bổ đến The Trade Desk.
* **All media sources including organic**: để toàn bộ cơ sở người dùng của bạn được báo cáo cho The Trade Desks.

> 📘 **Lưu ý**
>
> Là một mạng cho tất cả các lượt cài đặt, The Trade Desk ưu tiên nhận bài đăng lại cho tất cả lượt cài đặt mới ứng dụng của bạn từ bất kỳ nguồn nào và họ khuyến khích chọn **All media sources including organic** để gửi mọi bài đăng lại lượt cài đặt đến The Trade Desk.

#### Thiết lập Sự kiện trong Ứng dụng

Ánh xạ các sự kiện AppsFlyer với TTD qua các bài đăng lại.Nếu bật tính năng gửi đăng lại, điều này bao gồm các sự kiện trong ứng dụng bị từ chối (các sự kiện bị Protect360 chặn hoặc các sự kiện bị phát hiện là không tuân thủ theo quy tắc xác thực mục tiêu).

![the_trade_desk_in_app_event_settings_en-us.png](https://files.readme.io/a72231e1f7d21eeb6ffd0b8e0ce056872ec7ef4670470a86e93eb7094ff9cea8-50612307447185.png)

**Để cấu hình đăng lại sự kiện trong ứng dụng**

1. Nhập **advertiserid** và **Tracker\_ID**.
2. Bật **In-app event postbacks**.
3. Thiết lập **Khung thời gian đăng lại sự kiện trong ứng dụng**, nếu cần (đọc thêm về<Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#khung-thời-gian-đăng-lại-sự-kiện-trong-ứng-dụng"> cấu hình khung thời gian đăng lại sự kiện trong ứng dụng</Anchor>).
4. Nếu có, hãy chọn gửi sự kiện theo cách tự động hoặc thủ công. Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">cách gửi tất cả các sự kiện nguyên trạng</Anchor>.
5. Nhấp vào **Add event** để thêm một SDK hoặc sự kiện từ máy chủ đến máy chủ vào danh sách.
6. Hoàn thành các thông số yêu cầu.
7. [Tùy chọn] Nhấp chuột<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />để đặt điều kiện gửi một số sự kiện trong ứng dụng tới TTD.  
   Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#đăng-lại-sự-kiện-trong-ứng-dụng-có-điều-kiện">bài đăng lại sự kiện trong ứng dụng có điều kiện</Anchor>.

| Tên thông số | Mô tả |
| --- | --- |
| **AppsFlyer event** | Tên của sự kiện mà AppsFlyer nhận được từ SDK sẽ được tích hợp vào ứng dụng của bạn hoặc từ các sự kiện máy chủ đến máy chủ.<br />**Mẹo**: Đừng xem sự kiện đang tìm kiếm?<ul><li>Hãy đảm bảo kích hoạt sự kiện trên thiết bị có cài đặt không tự nhiên và kiểm tra lại.</li><li>Nhập vào **Sự kiện AppsFlyer** (AppsFlyer event), sau đó nhấp vào **Tạo tùy chỉnh** (Create custom). Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">ánh xạ sự kiện tùy chỉnh.</Anchor></li></ul> |
| **for users from** | Chọn tùy chọn gửi cho sự kiện:<ul><li>**Chỉ đối tác này**: chỉ gửi đăng lại khi sự kiện này được phân bổ cho đối tác này.</li><li>**Tất cả các nguồn truyền thông bao gồm cả tự nhiên**: gửi đăng lại cho các sự kiện được phân bổ cho bất cứ đối tác cũng như các sự kiện tự nhiên.</li></ul> |
| **including** | <ul><li>**Không có dữ liệu (mặc định) (No data (default))**: chỉ gửi sự kiện mà không gửi giá trị sự kiện.</li><li>**Values and revenue**: gửi tất cả các thông số sự kiện, **bao gồm** cả giá trị doanh thu (nếu có trong sự kiện).</li><li>**Giá trị không có doanh thu (Values without revenue)**: gửi tất cả các thông số, **ngoại trừ** giá trị doanh thu.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab Liên kết Phân bổ">

Tạo và lưu đường dẫn phân bổ và gửi chúng cho TTD để phân bổ các chiến dịch, nhóm quảng cáo hoặc quảng cáo đơn lẻ cụ thể - cho cả chiến dịch UA và chiến dịch nhắm mục tiêu lại. Bạn có thể sử dụng liên kết một nền tảng hoặc <Anchor target="_blank" href="/marketers/vi/docs/onelink-guide">OneLink</Anchor>.

#### Thông số đường dẫn phân bổ

Việc thêm thông số vào đường dẫn phân bổ này cho phép bạn thực hiện việc phân tích truy cập sâu toàn diện. Các thông số đã được xác định trên đường dẫn phân bổ có thể được chỉnh sửa bằng cách thêm chúng và các giá trị mới của chúng ở đây. Khi lưu đường dẫn phân bổ, tất cả các thông số được cấu hình trong thẻ này cũng sẽ được lưu.

Chọn thông số bạn muốn thêm vào đường dẫn phân bổ.

![ttd_attribution_link_parameters_en-us.png](https://files.readme.io/2658797286fd7d922c68a9c2f1705166672066d4179d72cf4fe0039ac3ede212-50612291012625.png)

#### Thông số mặc định

| Tên | Mô tả | Tham số |
| --- | --- | --- |
| ID trang | Đặt ID trang web để phân bổ lượt cài đặt cho các nhà phát hành cụ thể. Nếu nhiều nhà phát hành tồn tại, chúng tôi khuyên bạn nên hạn chế số lượng ID trang web đã sử dụng và sử dụng thông số ID trang phụ, để tránh <Anchor target="_blank" href="/marketers/vi/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">vượt quá giới hạn ID trang web</Anchor>. | af\_siteid |
| Tên Chiến dịch | Thêm tên chiến dịch của bạn để so sánh các chiến dịch khác nhau đang chạy với TTD. | c |
| ID Chiến dịch | Thêm ID chiến dịch của bạn. | af\_c\_id |
| ID Bộ quảng cáo | Thêm ID bộ quảng cáo của bạn để so sánh hiệu suất của tất cả quảng cáo trên mỗi bộ quảng cáo. | af\_adset |
| ID Quảng cáo | Thêm ID quảng cáo của bạn. | af\_ad\_id |

Bạn có thể thêm nhiều thông số hơn cho đường dẫn phân bổ. Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#attribution-link-tab">cách thiết lập đường dẫn phân bổ</Anchor> và về <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">cấu trúc và thông số</Anchor> đường dẫn phân bổ .

#### Thông số đo lường CTV

Bạn có thể đo lưu lượng CTV với AppsFlyer bằng cách thêm các thông số và giá trị sau:

| Tham số | value | Nhận xét |
| --- | --- | --- |
| redirect | false |  |
| af\_xplatform\_vt\_lookback | 1h-72h | Có thể nhập bất kỳ giá trị nào trong khoảng từ 1 - 72 giờ |

#### Phân bổ lượt nhấp qua

![click-through_attribution_ttd_en-us.png](https://files.readme.io/9d8c4aed6aa5d8b3cba5b4e32a5245f4bd8b6d9cf50e8cc800dce66842487355-50612291014673.png)

Sử dụng thanh trượt để đặt thời gian tối đa từ khi nhấp đến lúc cài đặt. Chỉ các lượt cài đặt (lần khởi chạy đầu tiên) diễn ra trong khung thời gian xem lại mới được phân bổ.

Khung thời gian xem lại: 1-23 giờ hoặc 1-30 ngày.

Thông số đường dẫn phân bổ: af\_click\_lookback

Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">khung thời gian xem lại lượt nhấp</Anchor>.

**Đường dẫn phân bổ lượt nhấp qua:** Chứa tất cả các thông số bạn đã đưa vào thiết lập đường dẫn phân bổ. Bạn có thể sao chép liên kết và gửi cho đối tác để được kích hoạt khi khách hàng tiềm năng của bạn nhấp vào quảng cáo tương ứng. 

#### Phân bổ lượt xem qua

![view-through_attribution_ttd_en-us.png](https://files.readme.io/7435384719e46f0534149ef41612db6ee54c930bab8e8eadc1fd86ae84d5d777-50612307451921.png)

Thanh trượt này cho phép bạn đặt thời gian tối đa từ khi hiển thị tới cài đặt. Chỉ các lượt cài đặt (lần khởi chạy đầu tiên) diễn ra trong khung thời gian xem lại này, sau một lượt hiển thị quảng cáo, mới được phân bổ cho đối tác, miễn là không có lượt nhấp quảng cáo có liên quan khác.

Khung thời gian xem lại: 1-24 giờ.

Thông số đường dẫn phân bổ: af\_viewthrough\_lookback

Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows">phân bổ lượt xem qua</Anchor>.

**Đường dẫn phân bổ lượt xem qua:** Chứa tất cả các thông số bạn đã đưa vào thiết lập đường dẫn phân bổ. Bạn có thể sao chép đường dẫn và gửi cho đối tác để được kích hoạt khi khách hàng tiềm năng của bạn nhấp vào quảng cáo tương ứng.

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab Chi phí">

Tích hợp chi phí không khả dụng đối với The Trade Desk.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Doanh thu quảng cáo">

Doanh thu quảng cáo không khả dụng đối với The Trade Desk.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab quyền truy cập">

Trong thẻ này, bạn có thể chọn các quyền để cấp cho The Trade Desk, cho dù chúng hoạt động như một mạng quảng cáo, đại lý hay thậm chí cả hai. Lưu ý rằng ngay cả khi tính năng phân bổ bị vô hiệu hóa đối với The Trade Desk, thẻ quyền vẫn có thể hoạt động và bạn có thể cấp quyền kiểm soát cho The Trade Desk.

![](https://files.readme.io/8d8c3d5eb38384d92e52afdc01b0631d8fe5c9590dd618386cbf6ce90fc978f3-50612307452817.png)

Sử dụng các nút chuyển đổi này để cấp quyền cho mạng quảng cáo xử lý cấu hình riêng cho ứng dụng của bạn:

#### **Quyền truy cập mạng quảng cáo**

* **Allow to configure integration:** Cho phép TTD thiết lập thẻ tích hợp, ngoại trừ bài đăng lại sự kiện trong ứng dụng
* **Allow to configure in-app event postbacks:** Cho phép TTD thiết lập ánh xạ bài đăng lại sự kiện trong ứng dụng cho chính nó, trên thẻ tích hợp
* **Allow access to your retention report:** Chỉ dành cho dữ liệu chính TTD lưu giữ
* **Allow access to your aggregate loyal user data:** Chỉ dành cho dữ liệu người dùng trung thành của chính TTD
* **Allow access to your aggregate in-app events data:** Chỉ dành cho dữ liệu sự kiện trong ứng dụng của chính TTD
* **Allow access to your aggregate revenue data:** Chỉ dành cho dữ liệu doanh thu được phân bổ cho TTD
* **Allow access to your Protect360 dashboard:** Chỉ dành cho dữ liệu Protect360 của chính TTD và miễn là bạn đã bật tính năng này

Tìm hiểu thêm về việc cấp <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">quyền truy cập mạng quảng cáo</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-the-trade-desk-ttd=thi%E1%BA%BFt-l%E1%BA%ADp-the-trade-desk-ttd h_01HH2DHQWXTB9K2R07SJP1AXER=thi%E1%BA%BFt-l%E1%BA%ADp-the-trade-desk-ttd h_01HH2DHQWX9Y6R1J3HPYWTAC2Z=step-1-define-conversion-events-in-ttd h_01HH2DHQWXTZ5EMJNYRGJMY7QA=step-2-define-conversion-events-in-appsflyer h_01HH2DHQWXCWF0H1GJGJS2YYDA=step-3-map-defined-conversion-events-from-appsflyer step-4-add-click-and-impression-trackers%C2%A0to-campaign-creatives=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWX1Z10PTRM8S7538YX=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWXX1EEARNBC61W3CDK=l%C6%B0u-%C3%BD integrating-ttd-with-appsflyer=t%C3%ADch-h%E1%BB%A3p-ttd-v%E1%BB%9Bi-appsflyer h_01GFNDH51M6KYE39C7DJW3BJ8W=t%C3%ADch-h%E1%BB%A3p-ttd-v%E1%BB%9Bi-appsflyer h_01GF8CKQYVDW5Z7141MJDGGW4C=integration-tab activate-partner=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c h_01HH2DHQWYME21J7JV176N71P2=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c advanced-privacy=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao h_01HH2DHQWYFJB3ZCWVZZ048AQP=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao general-settings=c%C3%A0i-%C4%91%E1%BA%B7t-chung h_01HH2DHQWYN3CZZCFT9X2R2N9J=c%C3%A0i-%C4%91%E1%BA%B7t-chung default-postbacks=postback-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh h_01HH2DHQWY1GPVP5W5R4XV2H9C=postback-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh h_01HH2DHQWY284121FR8HSFGH45=l%C6%B0u-%C3%BD-1 inapp-events-settings=thi%E1%BA%BFt-l%E1%BA%ADp-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HH2DHQWY0XM70BPE7222XE78=thi%E1%BA%BFt-l%E1%BA%ADp-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HH2DHQWY7X522JKKC4A45BHN=attribution-link-tab attribution-link-parameters=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 h_01HH2DHQWY4GXPMCV5JEBFERG6=th%C3%B4ng-s%E1%BB%91-%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 default-parameters=th%C3%B4ng-s%E1%BB%91-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh h_01HH2DHQWYZSECQWRQEKDB9KZH=th%C3%B4ng-s%E1%BB%91-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh parameters-for-measuring-ctv=th%C3%B4ng-s%E1%BB%91-%C4%91o-l%C6%B0%E1%BB%9Dng-ctv h_01HH2DHQWYZPKCY947MWK7GEAP=th%C3%B4ng-s%E1%BB%91-%C4%91o-l%C6%B0%E1%BB%9Dng-ctv clickthrough-attribution=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-qua h_01HH2DHQWYCFGJK4ZT9CXFX3X3=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-nh%E1%BA%A5p-qua viewthrough-attribution=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua h_01HH2DHQWYP6S95MRAS39Q4RTT=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua h_01HH2DHQWYP5GYN2GH3C839P3N=cost-tab h_01HH2DHQWYG3KZTE0HH7QV4H6X=ad-revenue-tab h_01HH2DHQWYA9HAWT5PV092T6E9=permissions-tab ad-network-permissions=quy%E1%BB%81n-truy-c%E1%BA%ADp-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o h_01HH2DHQWYCWYQFBDA19Z9BA8W=quy%E1%BB%81n-truy-c%E1%BA%ADp-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o" />
