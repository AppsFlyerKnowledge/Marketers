---
title: Cấu hình đăng lại sự kiện trong ứng dụng
metadata:
  keywords:
    - In-App Events
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-11T08:47:14Z'
  edited_at: '2024-01-16T11:42:05Z'
  id: 208439256
  locale: vi
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/vi/articles/208439256
---
> **Tổng quan:** Đo lường mức độ tương tác với ứng dụng và chất lượng của người dùng, đồng thời tối ưu hóa các chiến dịch bằng cách sử dụng dữ liệu sự kiện trong ứng dụng.

<div id="overview" />

## Tổng quan

Sự kiện trong ứng dụng cho phép các nhà tiếp thị đo lường lượt tương tác với ứng dụng và chất lượng của người dùng từ các nguồn khác nhau, đồng thời xây dựng chiến lược thu hút người dùng phù hợp. Mạng quảng cáo sử dụng thông tin của sự kiện trong ứng dụng để tối ưu hóa chiến dịch và chạy chiến dịch trả phí cho mỗi hành động/sự kiện. Mạng quảng cáo nhận dữ liệu về các sự kiện trong ứng dụng thông qua đăng lại—được gửi theo thời gian thực. <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Tìm hiểu thêm về các sự kiện phong phú trong ứng dụng</Anchor>.

<div id="postback-in-app-event-selection" />

## Đăng lại lựa chọn sự kiện trong ứng dụng

Nhà tiếp thị có thể chọn các sự kiện trong ứng dụng mà họ muốn gửi đăng lại đến các mạng quảng cáo, bằng cách sử dụng các tùy chọn cài đặt được mô tả trong bài viết này.

<div id="note" />

> 📘 **Lưu ý**
>
> * Các sự kiện trong ứng dụng bao gồm **các sự kiện bị từ chối**, nghĩa là các sự kiện trong ứng dụng bị Protect360 chặn hoặc các sự kiện được phát hiện là không tuân thủ các quy tắc xác thực mục tiêu.
> * Nếu phần **In-app event postbacks** không tồn tại trong tab **Integration**, thì có nghĩa là đối tác chưa thiết lập ghi nhận sự kiện trong ứng dụng với AppsFlyer trong cấu hình sơ bộ. Đối tác có thể liên hệ với AppsFlyer bằng <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">tiện ích trợ lý đối tác</Anchor> để hoàn tất quá trình tích hợp.

<div id="note-1" />

<div id="in-app-event-postback-window" />

## Khung thời gian đăng lại sự kiện trong ứng dụng

Khoảng thời gian đăng lại sự kiện trong ứng dụng cho phép các nhà tiếp thị làm việc với các mạng trên cơ sở CPA (chi phí mỗi hành động) để định cấu hình khoảng thời gian sau chuyển đổi mà sau đó, các bài đăng lại sự kiện không còn được gửi nữa.

Ví dụ: nếu bạn bị tính phí cho các sự kiện xảy ra trong vòng 15 ngày kể từ thời điểm người dùng cài đặt, hãy đặt khoảng thời gian như sau:

<Image align="center" alt="15-day_in_app_event_postback_setting.png" src="https://files.readme.io/6ffcd335b85334015f518895b317d3a5e273f4e00c31e3694c0f95a22ba6d4fb-33379700644497.png" width="529px" />

Các đăng lại sau khoảng thời gian này sẽ không được gửi đi và mạng không được thông báo, nhưng các sự kiện vẫn được ghi nhận trong AppsFlyer và được phân bổ cho mạng.

Các đăng lại luôn được gửi dựa trên phần cài đặt khung thời gian **hiện tại**. Xem ví dụ sau:

| Ngày 1 tháng 1 | Khung thời gian là 15 ngày.<br /><br />Người dùng cài đặt một ứng dụng. |
| --- | --- |
| Ngày 2 tháng 1 | Khung thời gian được thay đổi thành 10 ngày. |
| Ngày 14 tháng 1 | Người dùng mua hàng.<br /><br />Đăng lại sẽ không được gửi đến mạng quảng cáo vì sự kiện không nằm trong khoảng thời gian hiện tại (10 ngày). |
| Ngày 15 tháng 1 | Khung thời gian được thay đổi thành 20 ngày. |
| Ngày 18 tháng 1 | Người dùng thực hiện một giao dịch mua khác.<br /><br />Lần này, đăng lại được gửi đi—vì sự kiện diễn ra trong khoảng thời gian hiện tại (20 ngày). |

<div id="default-postback-window" />

### Thời gian đăng lại mặc định

Khi bắt đầu thiết lập đăng lại sự kiện trong ứng dụng, thời gian mặc định sẽ tự động được đặt thành sáu tháng.

<div id="note-2" />

> 📘 **Lưu ý**
>
> Nếu bạn đã bắt đầu sử dụng đăng lại sự kiện trong ứng dụng với một đối tác cụ thể trước ngày 30 tháng 7 năm 2019, thì cài đặt mặc định cho khoảng thời gian là Trọn đời. Điều này có nghĩa là các đăng lại sự kiện trong ứng dụng luôn được gửi.

<div id="who-can-configure-postback-windows" />

### Ai có thể định cấu hình khung thời gian đăng lại

* Nhà tiếp thị
* Đại lý, nếu họ được cấp quyền **Cho phép định cấu hình đăng lại sự kiện trong ứng dụng**<Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#cấp-quyền-cho-đại-lý">.</Anchor>  
  **Lưu ý:** Nhà tiếp thị và đại lý làm việc với cùng một mạng quảng cáo có thể định cấu hình các khung thời gian đăng lại riêng biệt với nhau, dựa trên hợp đồng của họ với mạng.
* Đối tác, nếu họ được cấp quyền **Cho phép định cấu hình đăng lại sự kiện trong ứng dụng**.

<div id="event-mapping" />

## Ánh xạ sự kiện

Mỗi nhà tiếp thị có thể đặt tên khác nhau cho một sự kiện cùng loại. Tên sự kiện đó cũng có thể khác với tên đối tác.

Ví dụ, khi người dùng mua thứ gì đó thông qua một ứng dụng, một nhà tiếp thị có thể đặt tên cho sự kiện đó là `purchase` hoặc một ID ít thông tin hơn, chẳng hạn như `event5` và một đối tác có thể đặt tên là `purchase_event`.

Để đảm bảo rằng các sự kiện của nhà tiếp thị khớp với các sự kiện giống như các sự kiện của đối tác thì tên sự kiện phải được ánh xạ.

<div id="note-3" />

> 📘 **Lưu ý**
>
> Các sự kiện được ánh xạ trong tab Integration cho một đối tác cụ thể có thể áp dụng cho cả đăng lại tiêu chuẩn và <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAN</Anchor>.

<div id="mapping-methods" />

### Phương thức ánh xạ

Mỗi đối tác sẽ tự quyết định sử dụng phương thức nào trong số các phương thức sau đây để ánh xạ các sự kiện trong ứng dụng của họ:

* [Nhập ID sự kiện của đối tác](/docs/in-app-event-postback-configuration#h_c513e6d4-d46f-4070-a98d-1888a5ea939d)
* [Chọn ID sự kiện từ danh sách](/docs/in-app-event-postback-configuration#select-an-event-id-from-the-list)
* [Gửi các sự kiện như vốn có (chưa được ánh xạ)](/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped)

<div id="note-4" />

> 📘 **Lưu ý**
>
> * Không phải mọi đối tác đều có thể sử dụng được mọi phương thức ánh xạ
> * Bạn có thể [cấp quyền cho đối tác](/docs/in-app-event-postback-configuration#ánh-xạ-sự-kiện-theo-mạng-quảng-cáo) tự thực hiện ánh xạ

<div id="h_c513e6d4-d46f-4070-a98d-1888a5ea939d" />

<Accordion title="Nhập ID sự kiện của đối tác">

* **Sự kiện AppsFlyer**: Từ danh sách các sự kiện trong ứng dụng của bạn, hãy chọn một sự kiện.
* **được ánh xạ tới sự kiện đối tác**: Trong trường văn bản, hãy nhập ID sự kiện nhận được từ đối tác, tương ứng với sự kiện trong ứng dụng của bạn (sự kiện AppsFlyer)

<div id="note-5" />

> 📘 **Lưu ý**
>
> * Tên sự kiện có phân biệt chữ hoa và chữ thường. Để tránh sai lệnh, hãy đảm bảo bạn sử dụng chính xác tên sự kiện cho tất cả các nguồn truyền thông và phiên bản ứng dụng.
> * Khi nhập tên sự kiện, bạn có thể sử dụng các khoảng trắng được gạch chân (dấu gạch ngang dưới) trước hoặc sau tên sự kiện. Đảm bảo chỉ sử dụng khoảng trắng được gạch chân khi tên sự kiện được gửi từ AppsFlyer có cùng khoảng trắng được gạch chân.

<Image align="center" alt="enter_event_name.png" src="https://files.readme.io/b9d65d3a6b4c1ab4d3f7e83cc2226af5c5a83e1e83cfbfa3df36d295ae568a45-33379700646545.png" />

</Accordion>

<div id="select-an-event-id-from-the-list" />

<Accordion title="Chọn một ID sự kiện từ danh sách">

* **Sự kiện AppsFlyer**: Từ danh sách các sự kiện trong ứng dụng của bạn, hãy chọn một sự kiện.
* **được ánh xạ tới sự kiện đối tác**: Từ danh sách các sự kiện đối tác được xác định trước, hãy chọn sự kiện tương ứng với sự kiện trong ứng dụng của bạn (sự kiện AppsFlyer).

<Image align="center" alt="In-app_event_postbacks_en-us.png" src="https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png" />

</Accordion>

<div id="send-events-as-they-are-unmapped" />

<Accordion title="Gửi các sự kiện như vốn có (chưa được ánh xạ)">

Một số đối tác muốn nhận đăng lại sự kiện trong ứng dụng chưa được ánh xạ—nghĩa là tên sự kiện được gửi giống như tên trong ứng dụng của bạn. Không quan trọng nếu sự kiện được gọi là `purchase`, `acquisition` hoặc `event5`.

Bạn có thể chọn những sự kiện chưa được ánh xạ để gửi cho đối tác:

* **Thêm theo cách thủ công:** Chọn các sự kiện cụ thể.
* **Gửi tất cả sự kiện (không bao gồm lượt gỡ cài đặt và phiên)**: Gửi tất cả sự kiện của bạn. Điều này không bao gồm lượt gỡ cài đặt, phiên (lượt khởi chạy ứng dụng) và sự kiện `af_app_opened` .

<div id="note-6" />

> 📘 **Lưu ý**
>
> Để ngăn các nhà quảng cáo vô tình chia sẻ quá nhiều thông tin với nền tảng Analytics của bên thứ ba, kể từ tháng 3 năm 2019, chúng tôi đã xóa tùy chọn **Gửi tất cả các sự kiện (không bao gồm lượt gỡ cài đặt và phiên)** cho các nền tảng này. Nền tảng Analytics được định cấu hình trước đó sẽ vẫn giữ tùy chọn cài đặt này.

**Để thêm sự kiện theo cách thủ công:**

1. Nhấp vào **Add event**.
2. Chọn các tùy chọn đăng lại:
   * **Sự kiện AppsFlyer**: Từ danh sách các sự kiện trong ứng dụng của bạn, hãy chọn một sự kiện.
   * **đối với người dùng nguồn**: Chọn <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#for-users-from">tùy chọn gửi</Anchor> cho sự kiện.
   * **bao gồm**: Chọn [dữ liệu cần đưa](/docs/in-app-event-postback-configuration#dữ-liệu-cần-đưa-vào-đăng-lại) vào đăng lại.
3. Lặp lại quy trình này cho nhiều sự kiện hơn.

<Image align="center" alt="send_postbacks_as_is_en-us.png" src="https://files.readme.io/cc6b2bb1a381d88add035b9f369b0ba68dee8744aa3c2ee2f8f6f054b365a0dd-33379684962705.png" />

**Để gửi tất cả các sự kiện:**

1. Chọn **Send all events (excludes uninstalls and sessions)**.
2. Chọn các tùy chọn đăng lại:  
   * **đối với người dùng nguồn**: Chọn [tùy chọn gửi](/docs/in-app-event-postback-configuration#tùy-chọn-để-gửi-đăng-lại) cho tất cả các sự kiện.
   * **bao gồm**: Chọn [dữ liệu cần đưa vào](/docs/in-app-event-postback-configuration#dữ-liệu-cần-đưa-vào-đăng-lại) cho tất cả các sự kiện trong đăng lại.

<Image align="center" alt="send_postbacsk_as_is_no_mapping.png" src="https://files.readme.io/458ca832d4176ccd306236cf10f211499e841dc9f550558987dff3ee683bd2d1-33379700651665.png" />

</Accordion>

Để biết thêm thông tin về các sự kiện ánh xạ, hãy xem phần <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">đăng lại sự kiện trong ứng dụng</Anchor>.

<div id="options-for-sending-postbacks" />

### Tùy chọn để gửi đăng lại

Đối với mỗi sự kiện, bạn có thể chọn trường hợp nào cần gửi đăng lại (trong khoảng thời gian đăng lại):

* **Chỉ đối tác này**: Chỉ gửi đăng lại khi sự kiện được phân bổ cho đối tác này—nghĩa là người dùng thực hiện sự kiện đến từ đối tác này.
* **All media sources including organic**: Gửi đăng lại tới tất cả các nguồn truyền thông cho các sự kiện được phân bổ cho bất kỳ đối tác nào và cho các sự kiện không phải trả tiền—nghĩa là khi người dùng thực hiện sự kiện đến từ bất kỳ nguồn truyền thông nào.

<div id="tip" />

<div id="note-8" />

<div id="share-revenue" />

<div id="note-7" />

<div id="data-to-include-in-the-postbacks" />

### Dữ liệu cần đưa vào đăng lại

Bạn có thể chọn loại dữ liệu sự kiện mà bạn có thể chia sẻ với đối tác trong đăng lại. Chọn một trong các tùy chọn sau:

* **Không có giá trị & không có doanh thu**: Chỉ gửi bản thân sự kiện mà không kèm bất kỳ thông số nào (giá trị hoặc doanh thu).
* **Không có giá trị & không có doanh thu**: Gửi tất cả các thông số, **ngoại trừ** giá trị doanh thu.
* **Giá trị & doanh thu**: Gửi tất cả các thông số sự kiện, **bao gồm** cả giá trị doanh thu (nếu có trong sự kiện).

Bạn nên chia sẻ doanh thu nếu muốn mạng quảng cáo tối ưu hóa chiến dịch và cải thiện kết quả chiến dịch. Tuy nhiên, việc chia sẻ doanh thu là không bắt buộc. Đảm bảo chỉ bật chia sẻ doanh thu cho các sự kiện đã xác định `af_revenue` trong giá trị sự kiện của chúng. Nếu không, các mạng quảng cáo sẽ nhận được các sự kiện có giá trị doanh thu trống.

Trong các lần gửi lại, `af_revenue` và `af_currency` được ghi bên ngoài JSON event\_value dưới dạng **tiền tệ** và **đơn vị tiền tệ** và có thể được gửi riêng. Cấu trúc đăng lại ví dụ: `https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&content_id=(af_content_id)`

**Lưu ý**: Khi chọn các tùy chọn có **Không có giá trị & không có doanh thu** hoặc **Có giá trị & không có doanh thu**, thì các thông số tương ứng được ẩn bằng N/A.

<div id="h_01HBZCRNKGBEDSBZEY87KYQ60G" />

> 📄 **Ví dụ**
>
> Nhà quảng cáo gửi sự kiện mua hàng với event\_value sau:
> `{af_revenue: 50.87, af_currency: USD, af_level=2,af_receipt_id=57601333}`
>
> Bảng dưới đây trình bày cách gửi thông số:
>
>
>
> | Tên trường | event\_value | tiền tệ | tiền tệ |
> | --- | --- | --- | --- |
> | **Không có giá trị và không có doanh thu** | N/A | Không áp dụng | Không áp dụng |
> | **Có giá trị và không có doanh thu** | `{"af_currency":"N/A","af_content_id":"1234567",`<br /><br />`"af_revenue":"N/A","af_content_type":"category_a"}`<br /><br />`&monetary=N/A&content_id=1234567` | Không áp dụng | Không áp dụng |
> | **Có giá trị và doanh thu** | `"af_currency":"USD","af_content_id":"1234567",`<br /><br />`"af_revenue":200,"af_content_type":"category_a"}`<br /><br />`&monetary=1.856918&content_id=1234567` | 50,87 | USD |

<div id="conditional-in-app-event-postbacks" />

### Đăng lại sự kiện trong ứng dụng có điều kiện

Lọc đăng lại sự kiện trong ứng dụng bằng nhiều điều kiện có thể được ánh xạ tới các sự kiện khác nhau. Chỉ những sự kiện đáp ứng các điều kiện của bộ lọc mới được gửi tới các đối tác, bao gồm cả SRN và đối tác Analytics. Sử dụng tính năng này cho:

* Tối ưu hóa phân khúc người dùng, cá nhân hóa và giữ chân người dùng
* Giảm thiểu dữ liệu
* Bảo vệ quyền riêng tư của người dùng

<div id="h_01HBZCRNKHRTMHP3JPFVCS8D6N" />

> 📄 **Ví dụ**
>
> Một nhà tiếp thị có ứng dụng trò chơi muốn tối ưu hóa các chiến dịch chạy qua mạng quảng cáo, nhưng chỉ dành cho người dùng vượt qua cấp 10 hoặc cấp 50 hoặc cho người dùng chi 3 đô la để mua ứng dụng.
>
> <Image align="center" alt="in_app_event_condition__1_.png" src="https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png" />
>
> **Đây là cách thiết lập các điều kiện cho sự kiện này:**
>
> * Khi ***cost*** bằng ***10***, ánh xạ tới ***`fb_mobile_level_acheived`***
>   Nếu không (**HOẶC**),
> * Khi ***level*** bằng ***50***, ánh xạ tới ***`fb_mobile_level_acheived`***
>   Nếu không (**HOẶC**),
> * Khi ***cost*** bằng ***3***, ánh xạ tới ***`fb_mobile_purchase`***

**Để thiết lập điều kiện cho một sự kiện:**

1. Trên trang tích hợp đối tác, <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">hãy xác định và ánh xạ</Anchor> các sự kiện trong ứng dụng bắt buộc để gửi cho đối tác.
2. Nhấp vào biểu tượng Add condition![image.png](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png) của sự kiện bắt buộc.
3. Nhập các trường điều kiện, khi chúng xuất hiện trong <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview#event-values">giá trị sự kiện</Anchor>:
   * Tên thuộc tính
   * value
   * Sự kiện đối tác cần ánh xạ điều kiện tới (sử dụng bất kỳ [tùy chọn ánh xạ](/docs/in-app-event-postback-configuration#phương-thức-ánh-xạ) nào trong số này)
4. Bạn có thể thêm nhiều điều kiện hơn, trước tiên chỉ cần đảm bảo rằng bạn nhập tất cả các trường của điều kiện hiện có.
5. Nhấp vào **Save integration** (Lưu tích hợp).

<div id="considerations" />

#### Những điều cần lưu ý

Khi định cấu hình các điều kiện, hãy đảm bảo đáp ứng các cân nhắc sau để gửi sự kiện tới đối tác:

<div id="condition-structure" />

<Accordion title="Cấu trúc điều kiện">

* Cả thuộc tính và giá trị trong điều kiện phải khớp với dữ liệu về sự kiện.
* Hiện tại, các điều kiện chỉ có thể được đặt thành “equal”.
* Các cấu trúc phức tạp như các mảng không được hỗ trợ.

</Accordion>

<div id="multiple-conditions-for-an-event" />

<Accordion title="Nhiều điều kiện cho một sự kiện">

* Số điều kiện tối đa cho mỗi sự kiện là 5.
* Ít nhất một điều kiện phải được đáp ứng để gửi đăng lại, nhưng chỉ có một điều kiện được thực thi.
* Mỗi điều kiện được kiểm tra theo thứ tự xuất hiện—điều kiện đầu tiên đáp ứng sẽ được thực thi.
* Mỗi điều kiện được ánh xạ riêng. Tên sự kiện đối tác được đổi thành **Based on conditions**.
* Nhiều điều kiện có thể có cùng một thuộc tính hoặc cùng một giá trị, nhưng không có hai điều kiện nào có thể có cùng một thuộc tính và giá trị.
* Nhiều điều kiện có thể được ánh xạ tới cùng một sự kiện.

</Accordion>

<div id="note-9" />

> 📘 **Lưu ý**
>
> * Bạn nên thử nghiệm tính năng này với một ứng dụng thử nghiệm hoặc cho các sự kiện nhỏ để hiểu rõ tác động của nó đối với việc tối ưu hóa chiến dịch.
> * Để xem <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">nội dung đăng lại</Anchor>, bạn có thể tải xuống báo cáo đăng lại dữ liệu thô.

<div id="editing-multiple-events" />

### Chỉnh sửa nhiều sự kiện

Trong khi ánh xạ các sự kiện, giá trị trong các trường **dành cho người dùng nguồn** và **bao gồm** có thể được chỉnh sửa cho nhiều sự kiện trong một hành động.

**Để chỉnh sửa nhiều sự kiện:**

1. Chọn các sự kiện cần cập nhật.
2. Nhấp vào **Bulk actions.**
3. Chọn tùy chọn cài đặt mới để áp dụng cho tất cả các sự kiện đã chọn:
   * **đối với người dùng nguồn** (chỉ chọn một tùy chọn)
     * Chỉ đối tác này
     * Tất cả các nguồn truyền thông, bao gồm nguồn tự nhiên
   * **bao gồm** (chỉ chọn một tùy chọn)
     * Không có dữ liệu (mặc định)
     * Giá trị không có doanh thu
     * Giá trị và doanh thu

<Image align="center" alt="In-app_event_postbacks_en-us.png" src="https://files.readme.io/559265d0e12e9e2ef62e0a19c5833465ee758821654877cffa4e75f6ff3f99b9-33379700657169.png" />

<div id="custom-events" />

### Sự kiện tùy chỉnh

Danh sách các sự kiện có sẵn để ánh xạ chỉ hiển thị các sự kiện đã được SDK báo cáo hoặc các sự kiện từ máy chủ đến máy chủ đến AppsFlyer. Nếu sự kiện bạn muốn ánh xạ không xuất hiện trong danh sách thả xuống, thì có thể do những nguyên nhân sau:

* Chưa có người dùng nào thực hiện sự kiện
* Lần gần nhất sự kiện xảy ra là hơn hai tuần trước
* Bạn có một danh sách lớn các sự kiện đang hoạt động

**Trong cả hai trường hợp này, để ánh xạ sự kiện tới ID đối tác:**

1. Nhập tên của sự kiện.
2. Nhấp vào **Create custom**

   <Image align="center" alt="In-app_event_postbacks_en-us.png" src="https://files.readme.io/73ad7c6a34a292056ddd750901ce1e0a2975d6ce6f235610f0bee28aecd05d53-7901768117905.png" />
3. Ánh xạ sự kiện với mã định danh đối tác.
4. Hãy nhấp vào **Save Integration** để đảm bảo ánh xạ được ghi lại.

<div id="note-10" />

> 📘 **Lưu ý**
>
> * Khi một sự kiện tùy chỉnh được thêm vào theo một đối tác nhất định, thì sự kiện đó sẽ được thêm vào danh sách sự kiện cho tất cả các đối tác. Có nghĩa là bạn có thể thấy sự kiện này trong bất kỳ danh sách sự kiện thả xuống nào của đối tác.
> * Xem <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#tips">các mẹo</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#limitations">giới hạn</Anchor> trong việc xác định tên và thông số sự kiện.

**Các đại lý và mạng quảng cáo:**

* Không thể thêm sự kiện tùy chỉnh
* Chỉ có thể xem và/hoặc ánh xạ sự kiện sau khi nhà tiếp thị đã thêm sự kiện và cấp <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">các quyền</Anchor> cần thiết

<div id="event-mapping-by-ad-networks" />

## Ánh xạ sự kiện theo mạng quảng cáo

Nhà tiếp thị có thể tự cho phép các mạng quảng cáo ánh xạ các sự kiện và tự vô hiệu hóa đăng lại. Để thực hiện, nhà quảng cáo nên cấp các quyền có liên quan cho mạng quảng cáo:

1. Trên trang **Active Integration**, hãy tìm đối tác mà bạn muốn cấp quyền.
2. Trong tab Quyền, hãy chuyển nút chuyển đổi **Cho phép định cấu hình đăng lại sự kiện trong ứng dụng** thành **BẬT**.

<Image align="center" alt="adnetwork-permissions-postbacks.png" src="https://files.readme.io/f8369f6a0a60d3c48ef66b51f61b3c81f00f6c88511f5f69b2c927788a64f018-33379700661265.png" />

Khi đã được cấp quyền, mạng quảng cáo có thể ánh xạ các sự kiện theo hướng dẫn trong phần [Nhập ID sự kiện vào trường văn bản](/docs/in-app-event-postback-configuration#phương-thức-ánh-xạ).

<div id="event-mapping-by-agencies" />

## Ánh xạ sự kiện theo đại lý

Nhà tiếp thị có thể cho phép các đại lý định cấu hình đăng lại sự kiện trong ứng dụng.

**Để cấp cho đại lý quyền định cấu hình đăng lại trong ứng dụng:**

1. Tìm đại lý trên trang **Active integrations**.
2. Chọn xem đại lý có thể chia sẻ tất cả sự kiện hay chỉ những sự kiện được phân bổ cho mạng quảng cáo cụ thể.
3. Chọn xem đại lý có được phép gửi doanh thu sự kiện hay không.
4. Chọn các sự kiện cụ thể mà đại lý được phép chia sẻ.

<Image align="center" alt="agency-events.png" src="https://files.readme.io/194b9a18f7721d4cc159f6385140cbb989108b70110e2e0d0f29f90d6115b10a-33379684973969.png" />

<div id="h_01HDP3XHBPA5GZEVERMBN43JH0" />

<div id="note-11" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview">Sự kiện phong phú trong ứng dụng—Tổng quan</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-event-structure">Sự kiện phong phú trong ứng dụng—Cấu trúc sự kiện</Anchor>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan h_01HE0FQ1AB6NQCTKFTDW22SRYC=t%E1%BB%95ng-quan postback-inapp-event-selection=%C4%91%C4%83ng-l%E1%BA%A1i-l%E1%BB%B1a-ch%E1%BB%8Dn-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HBZCRNKGH1PAK8RC846PPRTS=%C4%91%C4%83ng-l%E1%BA%A1i-l%E1%BB%B1a-ch%E1%BB%8Dn-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HBZCRNKGQTJ4VJ00TVTS14N2=l%C6%B0u-%C3%BD inapp-event-postback-window=khung-th%E1%BB%9Di-gian-%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HBZCRNKGS71QGK5506N07K84=khung-th%E1%BB%9Di-gian-%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng default-postback-window=th%E1%BB%9Di-gian-%C4%91%C4%83ng-l%E1%BA%A1i-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh h_01HBZCRNKGV5CREN5K0RBDMBH6=th%E1%BB%9Di-gian-%C4%91%C4%83ng-l%E1%BA%A1i-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh h_01HBZCRNKGVXN233AFFHG42NW9=l%C6%B0u-%C3%BD-1 who-can-configure-postback-windows=ai-c%C3%B3-th%E1%BB%83-%C4%91%E1%BB%8Bnh-c%E1%BA%A5u-h%C3%ACnh-khung-th%E1%BB%9Di-gian-%C4%91%C4%83ng-l%E1%BA%A1i h_01HBZCRNKG7AECFSBXV2WDD9AR=ai-c%C3%B3-th%E1%BB%83-%C4%91%E1%BB%8Bnh-c%E1%BA%A5u-h%C3%ACnh-khung-th%E1%BB%9Di-gian-%C4%91%C4%83ng-l%E1%BA%A1i event-mapping=%C3%A1nh-x%E1%BA%A1-s%E1%BB%B1-ki%E1%BB%87n h_01HBZCRNKG7SZ4T41BY60BAJZN=%C3%A1nh-x%E1%BA%A1-s%E1%BB%B1-ki%E1%BB%87n h_01HBZCRNKGT64TE2XYK9VS4ATD=l%C6%B0u-%C3%BD-2 mapping-methods=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C3%A1nh-x%E1%BA%A1 h_01HBZCRNKG4EF9MSY696SD5VQ9=ph%C6%B0%C6%A1ng-th%E1%BB%A9c-%C3%A1nh-x%E1%BA%A1 h_01HBZCVAGPSNDJMWRWENEP45N7=l%C6%B0u-%C3%BD-3 enter-the-partner-event-id=h_c513e6d4-d46f-4070-a98d-1888a5ea939d h_01HBZCRNKG1E63DZRSDWTB8CJN=l%C6%B0u-%C3%BD-4 h_01HBZCRNKGWQBNY8RP4MTW3DXV=select-an-event-id-from-the-list h_01HBZCRNKG4981T00N70X2GP0J=send-events-as-they-are-unmapped h_01HBZCRNKGXJ683VHFTE277ER9=l%C6%B0u-%C3%BD-5 options-for-sending-postbacks=t%C3%B9y-ch%E1%BB%8Dn-%C4%91%E1%BB%83-g%E1%BB%ADi-%C4%91%C4%83ng-l%E1%BA%A1i h_01HBZCRNKG1VN7E6TVCPDW7M73=t%C3%B9y-ch%E1%BB%8Dn-%C4%91%E1%BB%83-g%E1%BB%ADi-%C4%91%C4%83ng-l%E1%BA%A1i data-to-include-in-the-postbacks=d%E1%BB%AF-li%E1%BB%87u-c%E1%BA%A7n-%C4%91%C6%B0a-v%C3%A0o-%C4%91%C4%83ng-l%E1%BA%A1i h_01HBZCRNKGESY50NSZGTVPT25M=d%E1%BB%AF-li%E1%BB%87u-c%E1%BA%A7n-%C4%91%C6%B0a-v%C3%A0o-%C4%91%C4%83ng-l%E1%BA%A1i h_01HBZCRNKGBEDSBZEY87KYQ60G=v%C3%AD-d%E1%BB%A5 conditional-inapp-event-postbacks=%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng-c%C3%B3-%C4%91i%E1%BB%81u-ki%E1%BB%87n h_01HBZCRNKG5X3B2NJZZP6ER2CX=%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng-c%C3%B3-%C4%91i%E1%BB%81u-ki%E1%BB%87n h_01HBZCRNKHRTMHP3JPFVCS8D6N=v%C3%AD-d%E1%BB%A5-1 considerations=nh%E1%BB%AFng-%C4%91i%E1%BB%81u-c%E1%BA%A7n-l%C6%B0u-%C3%BD h_01HBZCRNKHBR57YVHZQP7NJBAP=nh%E1%BB%AFng-%C4%91i%E1%BB%81u-c%E1%BA%A7n-l%C6%B0u-%C3%BD h_01HBZCRNKHJGBYNP9JN24CQ3CC=condition-structure h_01HBZCRNKH1R0FR61C6TA0MCTN=multiple-conditions-for-an-event h_01HBZCRNKHF6TFP0N302D7DCMD=l%C6%B0u-%C3%BD-6 editing-multiple-events=ch%E1%BB%89nh-s%E1%BB%ADa-nhi%E1%BB%81u-s%E1%BB%B1-ki%E1%BB%87n h_01HBZCRNKHHD3WC4GTJT9NSJ4C=ch%E1%BB%89nh-s%E1%BB%ADa-nhi%E1%BB%81u-s%E1%BB%B1-ki%E1%BB%87n custom-events=s%E1%BB%B1-ki%E1%BB%87n-t%C3%B9y-ch%E1%BB%89nh h_01HBZCRNKH754PANWSZ4FMXJVQ=s%E1%BB%B1-ki%E1%BB%87n-t%C3%B9y-ch%E1%BB%89nh h_01HBZCRNKH4PVR3FEMTMERW3M1=l%C6%B0u-%C3%BD-7 event-mapping-by-ad-networks=%C3%A1nh-x%E1%BA%A1-s%E1%BB%B1-ki%E1%BB%87n-theo-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o h_01HBZCRNKH1GCZY17R04WTZ0MQ=%C3%A1nh-x%E1%BA%A1-s%E1%BB%B1-ki%E1%BB%87n-theo-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o event-mapping-by-agencies=%C3%A1nh-x%E1%BA%A1-s%E1%BB%B1-ki%E1%BB%87n-theo-%C4%91%E1%BA%A1i-l%C3%BD h_01HBZCRNKHHF3E6CZNQQG0Q4VS=%C3%A1nh-x%E1%BA%A1-s%E1%BB%B1-ki%E1%BB%87n-theo-%C4%91%E1%BA%A1i-l%C3%BD h_01HDP3XHBPA5GZEVERMBN43JH0=xem-th%C3%AAm" />
