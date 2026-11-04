---
title: Mô hình tương tác phong phú
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-01-21T13:45:23Z'
  edited_at: '2024-11-11T15:12:36Z'
  id: 21837486015889
  locale: vi
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/vi/articles/21837486015889
---
> **Sơ lược:** Mặc dù các loại quảng cáo hiện nay đã trở nên tinh vi và phức tạp, nhưng phạm vi báo cáo vẫn rất hẹp, chỉ tập trung vào việc phân bổ lượt xem hết và lượt nhấp. Mô hình tương tác phong phú giúp thay đổi tình trạng đó bằng cách phản ánh toàn bộ mức độ tương tác và chủ ý của người dùng khi xem hoặc tương tác với một mục quảng cáo.

<div id="introduction" />

## Giới thiệu

Trong vài năm qua, các loại quảng cáo sáng tạo mới như quảng cáo video có thể phát, có thể bỏ qua và video dạng ngắn đã được giới thiệu ra thị trường, cung cấp những phương thức mới để kết nối với người dùng. Các loại quảng cáo mới này khác biệt đáng kể so với các biểu ngữ tĩnh và các đoạn video chất lượng thấp trước đây cũng như mang đến cho các nhà quảng cáo khả năng và định dạng rộng hơn.

Tuy nhiên, mặc dù các loại quảng cáo đã trở nên tinh vi, phức tạp hơn và độ tương tác cao hơn, nhưng phạm vi báo cáo vẫn rất hẹp, chỉ tập trung vào việc phân bổ lượt xem hết và lượt nhấp. Các loại tương tác khác nhau có trọng số, mức độ ý định và tác động khác nhau, nhưng các phương pháp đo lường hiện tại đã bỏ qua thực tế mới này. Đương nhiên, các mạng quảng cáo muốn đảm bảo rằng mức độ ý định và mức độ tương tác được thể hiện rõ nhất có thể, điều này đã dẫn đến việc thiếu tiêu chuẩn hóa trên toàn hệ sinh thái. Điều này cuối cùng khiến các nhà quảng cáo chỉ hiểu được một phần về hiệu suất chi tiêu cho quảng cáo của họ.

Phối hợp với các mạng hàng đầu, AppsFlyer đang giới thiệu một tiêu chuẩn tương tác mới để mang lại sự tin tưởng và minh bạch trong toàn bộ hệ sinh thái. Mô hình tương tác phong phú phản ánh toàn bộ mức độ tương tác và chủ ý của người dùng khi xem hoặc tương tác với một mục quảng cáo, từ tiếp xúc tạm thời đến phản hồi trực tiếp. Khuôn khổ giúp này đảm bảo các tiêu chuẩn này được lưu giữ trong toàn bộ hệ sinh thái đối tác của AppsFlyer và hơn thế nữa. Thông qua Mô hình tương tác phong phú, nhà quảng cáo có thể đảm bảo có được bức tranh tổng quan và tiêu chuẩn cao về hiệu suất chi tiêu cho quảng cáo, đồng thời có thể tận dụng những thông tin chi tiết này để cải thiện việc phân bổ ngân sách và tăng ROAS.

<div id="what-are-enriched-engagement-types" />

## Mô hình tương tác phong phú

Khuôn khổ Mô hình tương tác phong phú cung cấp khả năng hiển thị các sắc thái của hành trình người dùng, bằng cách cho biết thời điểm lượt xem được tương tác (ví dụ: lượt xem video có thể bỏ qua trong hơn 5 giây) và thời điểm số lượt nhấp đưa đến việc mở ứng dụng hoặc truy cập cửa hàng ứng dụng. Bằng cách đó, các nhà tiếp thị sẽ nhận được thông tin chi tiết về hành động của người dùng, từ đó giúp việc phân bổ ngân sách thông minh hơn cũng như cải thiện ROI.

Sau đây là danh sách các loại tương tác mới:

| engagement\_type | Mô tả |
| --- | --- |
| <span id="preload"></span>preload | Ứng dụng được tải trước bởi OEM tại nhà máy hoặc bởi nhà cung cấp trong lần đầu kích hoạt thiết bị. Ngoài ra, một trình hướng dẫn sẽ nhắc người dùng tải xuống ứng dụng khi thiết bị được kích hoạt lần đầu. |
| <span id="click_to_download"></span>click\_to\_download | Khi người dùng tương tác với một mục quảng cáo, ứng dụng sẽ được tự động tải xuống và cài đặt trên thiết bị mà không chuyển hướng đến cửa hàng ứng dụng. |
| <span id="click_to_app"></span>click\_to\_app | Việc nhấp vào quảng cáo, quét mã QR, liên kết sâu hoặc bất kỳ lượt nhấp nào khác đều chuyển hướng người dùng đến ứng dụng hoặc đến cửa hàng ứng dụng có liên quan để tải xuống ứng dụng. |
| <span id="engaged_click"></span>engaged\_click | Việc nhấp chuột sẽ duy trì người dùng trong cùng một ngữ cảnh, tương tác với quảng cáo và KHÔNG chuyển hướng người dùng đó đến cửa hàng ứng dụng hoặc để khởi chạy ứng dụng. |
| <span id="engaged_view"></span>engaged\_view | Chế độ xem được tương tác xảy ra khi một lượt xem có ý nghĩa diễn ra trong các video có thể bỏ qua, video kèm phần thưởng hoặc quảng cáo được hiển thị bởi StoreKit. Ví dụ: khi người dùng xem quảng cáo video có thể bỏ qua trong ít nhất 5 giây sau khi tùy chọn bỏ qua xuất hiện. |
| <span id="view"></span>view | Lượt xem quảng cáo là khi quảng cáo được hiển thị và lượt hiển thị diễn ra. |
| <span id="listening"></span>listening | Lượt nghe là khi người dùng nghe quảng cáo âm thanh, chẳng hạn như quảng cáo podcast. |

<div id="eet-attribution-priority-and-lookback-window" />

## **Ưu tiên phân bổ EET và khoảng thời gian xem lại**

Khung Loại tương tác phong phú không ảnh hưởng đến mức độ ưu tiên phân bổ loại tương tác. Do đó, tỷ lệ cài đặt và chuyển đổi của bạn dự kiến sẽ không bị ảnh hưởng khi giới thiệu EET.

Bảng dưới đây chỉ định <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#attribution-waterfall">Ưu tiên phân bổ</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows#khung-thời-gian-xem-lại">Cửa sổ lookback</Anchor> của từng loại tương tác:

<table><thead><tr><th>Tương tác</th><th>Loại tương tác</th><th>Ưu tiên phân bổ</th><th>Khoảng thời gian xem lại\*\*</th></tr></thead><tbody><tr><td rowspan="2">Tải xuống</td><td>preload</td><td>1</td><td>1h-180d | mặc định: 90d</td></tr><tr><td>click_to_download</td><td>2</td><td>1h-30d | mặc định: 7d</td></tr><tr><td rowspan="2">Lượt nhấp</td><td>click_to_app</td><td>2</td><td>1h-30d | mặc định: 7d</td></tr><tr><td>engaged_click</td><td>2</td><td>1h-7d | mặc định: 2d </td></tr><tr><td rowspan="3">Lượt hiển thị</td><td>engaged_view</td><td>2</td><td>1h-7d | mặc định: 2d</td></tr><tr><td>view</td><td>3</td><td>1h-24h | mặc định: 24 giờ</td></tr><tr><td>listening</td><td>3</td><td>1h-24h | mặc định: 24 giờ</td></tr></tbody></table>

Khi một loại tương tác không được báo cáo, mức độ ưu tiên mặc định sẽ được đặt (*click\_to\_app* cho lượt nhấp, *view* cho lượt hiển thị).

** Cửa sổ lookback cho `engaged_click` và `engaged_view` chỉ có thể được đặt cho các mạng không phải SRN.

<div id="note" />

<div id="which-networks-can-report-engaged-views-and-engaged-clicks" />

## Những mạng nào có thể báo cáo EET cho AppsFlyer?

Các mạng đáp ứng tiêu chí Premier, Advance hoặc Engage của Chương trình đối tác của AppsFlyer sẽ được hỗ trợ Mô hình tương tác phong phú. Các cấp độ này đề cập đến các mạng có thành tích đáng kể về việc cung cấp lưu lượng truy cập chất lượng cao nhất quán theo quy mô lớn cho khách hàng chung của chúng tôi, gửi dữ liệu tương tác một cách minh bạch và đáng tin cậy và được tích hợp với một loạt các dịch vụ của AppsFlyer.

Các mạng được phép có thể được phân thành hai nhóm:

* [Các mạng đủ điều kiện nhận hỗ trợ Enriched Engagement **Bao gồm** lượt nhấp tương tác và lượt xem tương tác.](#networks-that-report-engagement-types) Các mạng đó cần cấu hình đặc biệt trong AppsFlyer.
* [Các mạng đủ điều kiện nhận hỗ trợ Enriched Engagement **Loại trừ** nhấp chuột tương tác và lượt xem tương tác](#01JCAT81K2EJNH91YS6NJGMXMB-data-title). Để có thể báo cáo các nhấp chuột đã tham gia và lượt xem đã tương tác, hãy liên hệ với bộ phận hỗ trợ của AppsFlyer vì cần có cấu hình đặc biệt.

> ❗️ **Cảnh báo**
>
> Lượt nhấp và lượt hiển thị từ các mạng không được phép bao gồm thông số af\_engagement\_type sẽ bị từ chối và sẽ không được sử dụng để phân bổ.

<div id="networks-that-report-engagement-types" />

<Accordion title="Mạng hỗ trợ nhấp chuột tương tác và chế độ xem tương tác">

Bảng dưới đây liệt kê các mạng đủ điều kiện để AppsFlyer báo cáo `engaged_clicks` và `engaged_views`. Các mạng muốn báo cáo các số liệu này nên liên hệ với bộ phận hỗ trợ của AppsFlyer.

| **Mạng Quảng cáo** | **Hỗ trợ chế độ xem tương tác** | **Hỗ trợ nhấp chuột tương tác** |
| --- | --- | --- |
| facebook\_int | Có |  |
| tiktokglobal\_int | Có | Có |
| snapchat\_int | Có | Có |
| bytedanceglobal\_int | Có | Có |
| adjoe\_int |  | Có |
| appier\_int | Có | Có |
| appnext\_int | Có |  |
| inmobidsp\_int | Có | Có |
| ironsource\_int | Có |  |
| lap\_int | Có |  |
| liftoff\_int | Có | Có |
| mintegral\_int | Có | Có |
| moloco\_int | Có | Có |
| smadex\_int | Có | Có |
| trademob\_int | Có |  |
| unityads\_int | Có |  |
| vungle\_int | Có |  |
| yahoojapan\_int | Có |  |
| youappi\_int | Có | Có |

</Accordion>

<div id="01JCAT81K2EJNH91YS6NJGMXMB-data-title" />

<Accordion title="Danh sách mạng được phép">

Danh sách mạng được phép bao gồm các đối tác có thể báo cáo các sự kiện loại tương tác phong phú ngoại trừ các nhấp chuột đã tương tác và lượt xem tương tác. Các mạng được phép muốn báo cáo `engaged_clicks` và `engaged_views` nên liên hệ với bộ phận hỗ trợ của AppsFlyer. Xem [trên](#networks-that-report-engagement-types) Danh sách các mạng được phép đủ điều kiện để báo cáo `engaged_clicks` và `engaged_views`.

| Tên đối tác |
| --- |
| Jampp |
| Fluent |
| AWIN |
| Rakuten |
| OPPOPAI Pre-Install |
| VK Ads (ex. myTarget) |
| Vivo Preload |
| OPPO Global |
| Mistplay |
| Amazon DSP |
| Adikteev |
| Criteo |
| OPPO |
| Glance |
| OPPO Store Traffic (Global) |
| XiaomiPAI Pre-Install |
| YouAppi |
| Yandex Direct |
| vivo Global |
| Remerge |
| adjoe GmbH |
| Treasure Data |
| Xiaomi Global |
| Smadex |
| Bigo |
| Motorola Pre-Install |
| Amazon |
| Bidease |
| Yahoo Japan |
| Kakao |
| Line |
| Reddit |
| Trade Desk |
| OneView |
| Samsung |
| Adaction |
| Adaction3 |
| Stackadapt |
| Cauly |
| Naver |
| Hotstar |
| Truecaller |
| Josh |
| PayTM |
| Transsion |
| Huawei |
| Mintegral |
| Apple Search Ads |
| Quảng cáo Meta |
| Google Ads (Adwords) |
| X Ads (trước đây là Twitter Ads) |
| Snapchat |
| ByteDance Ads China |
| TikTok For Business - SRN Nâng cao |
| TikTok for Business - Legacy |
| Google Marketing Platform (DV360/CM360) |
| AdColony |
| Nền tảng On Device của Digital Turbine |
| Digital Turbine |
| Appreciate |
| Liftoff |
| Appnext |
| AppLovin |
| ironSource |
| Moloco |
| Unity Ads |
| Tapjoy |
| Vungle |
| Kuaishou |
| Aura từ Unity |
| Tencent AMS |
| Roku |
| TV Scientific |
| Chartboost |
| Appier |
| kwaiforbusiness |
| Mobupps |
| Kayzen |
| Vibe |
| InMobi DSP |

</Accordion>

<div id="set-lookback-windows-for-engaged-clicks-and-engaged-views" />

## Đặt khoảng thời gian xem lại cho các nhấp chuột tương tác và chế độ xem tương tác

**Để đặt khoảng thời gian xem lại cho các nhấp chuột đã tương tác và chế độ xem đã tương tác:**

1. Trong AppsFlyer, từ menu bên, chọn **Collaborate** > **Active Integrations**.
2. Chọn đối tác tích hợp.
3. Đặt khoảng thời gian xem lại cho việc phân bổ lượt xem hết và lượt nhấp đã tương tác.

   <div id="note-1" />

   > 📘 **Lưu ý:**
   >
   > Cửa sổ xem lại nhấp chuột và xem tương tác luôn được đặt trong đối tác **Tab Tích hợp**, trái ngược với cửa sổ xem qua và xem qua lookback, có thể được đặt trên các liên kết phân bổ.

4. Nhấp vào **Save integration**.

<div id="view-and-analyze-eet-data" />

## Xem và phân tích dữ liệu EET

<div id="note-2" />

<div id="raw-data-reports" />

### Báo cáo dữ liệu thô

`engagement_type` sẽ được báo cáo trong các báo cáo dữ liệu thô bất cứ khi nào được mạng quảng cáo báo cáo. Dữ liệu này cũng sẽ khả dụng cho dữ liệu của người đóng góp.

Khi không có lượt nhấp nào được ghi nhận, chẳng hạn như trong trường hợp tải trước hoặc liên kết sâu, AppsFlyer sẽ đặt giá trị liên quan (tải trước hoặc `click_to_app` cho liên kết sâu) trong trường mới trong các báo cáo dữ liệu thô.

Các trường hợp dưới đây sẽ dẫn đến trường mới trong các báo cáo dữ liệu thô vẫn trống:

* Khi có sự sai lệch giữa mức độ tương tác (lượt nhấp/lượt hiển thị) và loại tương tác, thì sẽ được báo cáo là trống.
* Khi `af_engagement_type` không được gửi hoặc gửi với giá trị trống.

Để xem loại tương tác trong báo cáo dữ liệu thô, các nhà quảng cáo cần chọn các trường này trong sản phẩm dữ liệu thô có liên quan (loại tương tác và loại tương tác của người đóng góp không được chọn theo mặc định).

<div id="owned-media-support" />

<div id="cross-platform-engaged-view-support" />

<div id="why-cant-i-see-the-engagement-type-i2" />

<div id="traits-and-limitations" />

<div id="faqs" />

<div id="how-to-calculate-installs-per-mille-ipm" />

<div id="note-3" />

<div id="dashboards" />

### Bảng điều khiển

Thứ nguyên loại tương tác được thêm vào bảng thông tin.

[![eet-dashboard.png](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)

## Chỉ dành cho Khách hàng Beta

Nội dung của phần này được cập nhật để phản ánh sự hỗ trợ và chức năng Loại tương tác phong phú (EET) chỉ dành cho khách hàng chọn tham gia BETA. Nếu bạn muốn tham gia chương trình BETA, hãy liên hệ với bộ phận hỗ trợ của AppsFlyer.

### **Ưu tiên phân bổ EET và khoảng thời gian xem lại** (Chỉ dành cho người tham gia BETA)

Khung Enriched Engagement Types giới thiệu cho khách hàng Beta logic phân bổ mới, dựa trên bản cập nhật <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#attribution-waterfall">Ưu tiên phân bổ</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/set-up-lookback-windows#khung-thời-gian-xem-lại">Cửa sổ lookback</Anchor>.

Bảng dưới đây chỉ định, đối với khách hàng Beta, mức độ ưu tiên phân bổ và khoảng thời gian xem lại của từng loại tương tác:

<table><thead><tr><th>Tương tác</th><th>Loại tương tác</th><th>Ưu tiên phân bổ</th><th>Khoảng thời gian xem lại\*\*</th></tr></thead><tbody><tr><td rowspan="2">Tải xuống</td><td>preload</td><td>1</td><td>1h-180d | mặc định: 90d</td></tr><tr><td>click_to_download</td><td>2</td><td>1h-30d | mặc định: 7d</td></tr><tr><td rowspan="2">Lượt nhấp</td><td>click_to_app</td><td>2</td><td>1h-30d | mặc định: 7d</td></tr><tr><td>engaged_click</td><td>3</td><td>1h-7d | mặc định: 2d</td></tr><tr><td rowspan="3">Lượt hiển thị</td><td>engaged_view</td><td>3</td><td>1h-7d | mặc định: 2d</td></tr><tr><td>view</td><td>4</td><td>1h-24h | mặc định: 24 giờ</td></tr><tr><td>listening</td><td>4</td><td>1h-24h | mặc định: 24 giờ</td></tr></tbody></table>

Khi một loại tương tác không được báo cáo, mức độ ưu tiên mặc định sẽ được đặt (*click\_to\_app* cho lượt nhấp, *view* cho lượt hiển thị).

** Cửa sổ lookback cho `engaged_click` và `engaged_view` chỉ có thể được đặt cho các mạng không phải SRN.

### Đặt phân bổ làm giàu theo cam kết cho những người không phải SRN (chỉ dành cho người tham gia BETA)

Theo mặc định, tính năng phân bổ cho lượt nhấp và lượt xem đã tương tác được bật trong tab Tích hợp dành cho các đối tác hỗ trợ tính năng này. Các nút chuyển đổi này sẽ có sẵn bắt đầu từ ngày 3 tháng 9 năm 2024.

**Để thiết lập phân bổ tương tác phong phú:**

1. Trong AppsFlyer, từ menu bên, chọn **Collaborate** > **Active Integrations**.
2. Chọn đối tác tích hợp.
3. Trong tab **Integration**, kích hoạt **Install engaged view-through attribution** hoặc **Install engaged click-through attribution**.

   Đặt khoảng thời gian xem lại cho việc phân bổ lượt xem hết và lượt nhấp đã tương tác.

   > 📘 **Lưu ý:**
   >
   > Cửa sổ xem lại nhấp chuột và xem tương tác luôn được đặt trong đối tác **Tab Tích hợp**, trái ngược với cửa sổ xem qua và xem qua lookback, có thể được đặt trên các liên kết phân bổ.

4. Nhấp vào **Save integration**.

> 📘 **Lưu ý:**
>
> * Bạn có thể tắt tính năng phân bổ lượt xem hết và lượt nhấp đã tương tác trên mỗi kênh truyền thông. Tuy nhiên, nếu nhận được lượt nhấp và lượt xem đã tương tác trong khi tính năng phân bổ đang tắt, thì số lượt nhấp và lượt xem vẫn có trong bảng điều khiển, mặc dù số lượt nhấp và lượt xem đó sẽ không được sử dụng để phân bổ.

## **CÂU HỎI THƯỜNG GẶP**

<div id="why-in-some-cases-engaged_clicks-and-engaged_views-get-equal-priority-to-clicks" />

<Accordion title="Tại sao trong một số trường hợp, engaged_clicks và engaged_views lại được ưu tiên như nhau đối với lượt nhấp chuột?">

Mạng gửi `af_engagement_type=engaged_view/engaged_click` sẽ được ưu tiên như nhau khi cạnh tranh với các mạng gửi nhấp chuột mà không có `af_engagement_type`. Tín dụng sẽ được gán cho điểm tiếp xúc cuối cùng, như được xác định bằng mô hình phân bổ lượt nhấp cuối cùng.

</Accordion>

<div id="is-owned-media-supported" />

<Accordion title="Phương tiện truyền thông sở hữu có được hỗ trợ không?">

Phương tiện truyền thông sở hữu hiện chưa được hỗ trợ. Các liên kết phương tiện được sở hữu không được bao gồm `af_engagement_type` thông số.

</Accordion>

<div id="what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types" />

<Accordion title="Các loại chiến dịch nào phù hợp với Mô hình tương tác phong phú?">

Mô hình tương tác phong phú áp dụng cho cả chiến dịch UA và nhắm mục tiêu lại.

</Accordion>

<div id="are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard" />

<Accordion title="Số lượt nhấp và lượt xem đã tương tác có được tính vào tổng số lượt nhấp và lượt hiển thị trên Bảng điều khiển tổng quan không?">

Nếu không phải SRN, các con số được đưa vào và tính theo loại tiếp xúc (tức là số lượt nhấp đã tương tác được tính là số lượt nhấp, lượt xem đã tương tác được tính là số lượt hiển thị). Đối với SRN, các giá trị đó hiện không được đưa vào và được tính - đang chờ API của SRN hỗ trợ.

</Accordion>

<div id="why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions" />

<Accordion title="Tại sao tôi không thấy loại tương tác trong các lượt chuyển đổi gp_referrer của Meta?">

Meta chỉ báo cáo engagement\_type=engaged\_view trong SRN API của họ. Đối với các lượt chuyển đổi khác, bao gồm cả gp\_referrer, loại tương tác sẽ không khả dụng.

</Accordion>

<div data-zendesk-anchors="introduction=gi%E1%BB%9Bi-thi%E1%BB%87u h_01HNCNA03SZ0MJFQ9XHDFXNTA1=gi%E1%BB%9Bi-thi%E1%BB%87u enriched-engagement-types=m%C3%B4-h%C3%ACnh-t%C6%B0%C6%A1ng-t%C3%A1c-phong-ph%C3%BA h_01HNCNBR7KMT1KQBG5CPZY8YQY=m%C3%B4-h%C3%ACnh-t%C6%B0%C6%A1ng-t%C3%A1c-phong-ph%C3%BA eet-attribution-priority-and-lookback-window=%C6%B0u-ti%C3%AAn-ph%C3%A2n-b%E1%BB%95-eet-v%C3%A0-kho%E1%BA%A3ng-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i h_01HNCVYDH17NGA8SH5XNWR4P9X=%C6%B0u-ti%C3%AAn-ph%C3%A2n-b%E1%BB%95-eet-v%C3%A0-kho%E1%BA%A3ng-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i allowed-networks=nh%E1%BB%AFng-m%E1%BA%A1ng-n%C3%A0o-c%C3%B3-th%E1%BB%83-b%C3%A1o-c%C3%A1o-eet-cho-appsflyer h_01J00XFV136HPEHVQNPD934409=nh%E1%BB%AFng-m%E1%BA%A1ng-n%C3%A0o-c%C3%B3-th%E1%BB%83-b%C3%A1o-c%C3%A1o-eet-cho-appsflyer h_01J00XFV133YYAB7YPQNXM5R37=c%E1%BA%A3nh-b%C3%A1o 01JCAT81K21T0D1KH9FZNSDK83=networks-that-report-engagement-types 01JCAT81K2EJNH91YS6NJGMXMB%20data-title%3D=01JCAT81K2EJNH91YS6NJGMXMB-data-title allowed-network-list=01JCAT81K2EJNH91YS6NJGMXMB-data-title set%C2%A0engaged-enrichment-attribution=%C4%91%E1%BA%B7t-kho%E1%BA%A3ng-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-cho-c%C3%A1c-nh%E1%BA%A5p-chu%E1%BB%99t-t%C6%B0%C6%A1ng-t%C3%A1c-v%C3%A0-ch%E1%BA%BF-%C4%91%E1%BB%99-xem-t%C6%B0%C6%A1ng-t%C3%A1c h_01J5B6EVM9P3M1SVR3K7WWK02J=%C4%91%E1%BA%B7t-kho%E1%BA%A3ng-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-cho-c%C3%A1c-nh%E1%BA%A5p-chu%E1%BB%99t-t%C6%B0%C6%A1ng-t%C3%A1c-v%C3%A0-ch%E1%BA%BF-%C4%91%E1%BB%99-xem-t%C6%B0%C6%A1ng-t%C3%A1c h_01J5B97RCQQG6GN4PCKTQWVF54=l%C6%B0u-%C3%BD reporting=xem-v%C3%A0-ph%C3%A2n-t%C3%ADch-d%E1%BB%AF-li%E1%BB%87u-eet h_01J00XFV13YN8QNFZJTGM78EG2=xem-v%C3%A0-ph%C3%A2n-t%C3%ADch-d%E1%BB%AF-li%E1%BB%87u-eet raw-data=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 h_01J00XFV132M8TM6EGFZ7A7C3A=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 dashboards=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n h_01J00XFV13W0SD4MD7H4BT1RC9=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n for-beta-customers-only=ch%E1%BB%89-d%C3%A0nh-cho-kh%C3%A1ch-h%C3%A0ng-beta attribution-model-with-enriched-engagement-types-beta=%C6%B0u-ti%C3%AAn-ph%C3%A2n-b%E1%BB%95-eet-v%C3%A0-kho%E1%BA%A3ng-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-ch%E1%BB%89-d%C3%A0nh-cho-ng%C6%B0%E1%BB%9Di-tham-gia-beta set-engaged-enrichment-attribution-for-nonsrns-beta-participants-only=%C4%91%E1%BA%B7t-ph%C3%A2n-b%E1%BB%95-l%C3%A0m-gi%C3%A0u-theo-cam-k%E1%BA%BFt-cho-nh%E1%BB%AFng-ng%C6%B0%E1%BB%9Di-kh%C3%B4ng-ph%E1%BA%A3i-srn-ch%E1%BB%89-d%C3%A0nh-cho-ng%C6%B0%E1%BB%9Di-tham-gia-beta h_01J5B6EVM98GVYNKYFW29PECPF=l%C6%B0u-%C3%BD-2 faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p h_01J00XFV13KSZTQEN3QXNJYACP=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p h_01J00XFV135A0ERGVTS0T81V54=why-in-some-cases-engaged_clicks-and-engaged_views-get-equal-priority-to-clicks h_01J00XFV13TG4776DCPHQKRA9E=is-owned-media-supported h_01HNFTS74KF3YFA0SWRGEQAGYQ=what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types h_01HNYY1S6YQ6YNR6RSY7B8H4EM=are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard h_01HQG5Y4JVNCB60AXR9K2GGD0H=why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions" />
