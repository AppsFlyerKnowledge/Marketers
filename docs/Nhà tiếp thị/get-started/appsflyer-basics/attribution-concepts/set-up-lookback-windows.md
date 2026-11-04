---
title: Giải thích về khung thời gian xem lại
metadata:
  keywords:
    - Advertisers
    - look back
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-07T09:27:55Z'
  edited_at: '2023-08-21T08:02:59Z'
  id: 208338403
  locale: vi
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/vi/articles/208338403
---
> **Khái quát:** Tùy chỉnh khung thời gian xem lại lượt nhấp và lượt xem, dựa trên thỏa thuận của bạn với các nguồn truyền thông.

<div id="lookback-windows" />

## Khung thời gian xem lại

Khung thời gian xem lại phân bổ có thể cấu hình cho phép bạn tùy chỉnh khoảng thời gian phân bổ dựa trên thỏa thuận của bạn với các nguồn truyền thông.

Bằng cách đặt khung thời gian xem lại phân bổ cho mỗi nguồn truyền thông, AppsFlyer phân bổ theo các điều khoản đã thỏa thuận.

**Các loại khung thời gian xem lại**:

* **Khung thời gian xem lại lượt nhấp**: Khoảng thời gian tối đa sau khi một quảng cáo được nhấp vào, trong thời gian đó lượt cài đặt có thể được phân bổ cho quảng cáo. Các lượt cài đặt diễn ra sau khung thời gian xem lại được coi là Tự nhiên.
* **Khung thời gian xem lại lượt xem**: Khoảng thời gian tối đa sau khi một quảng cáo được xem, trong thời gian đó lượt cài đặt có thể được phân bổ cho quảng cáo.Các lượt cài đặt diễn ra sau khung thời gian xem lại được coi là Tự nhiên.

<div id="configurable-lookback-windows-per-attribution-type" />

#### Khung thời gian xem lại có thể cấu hình cho mỗi loại phân bổ

<table><thead><tr><th rowspan="2"><p><strong>Loại ghi công</strong></p></th><th rowspan="2"><p><strong>Phương thức phân bổ</strong></p></th><th colspan="2"><p><strong>Khung thời gian xem lại lượt nhấp</strong> </p></th></tr><tr><th><p><strong>Phạm vi</strong></p></th><th><p><strong><strong>Mặc định</strong></strong></p></th></tr></thead><tbody><tr><td rowspan="2"><p>Lượt nhấp</p><p>(Tất cả các nguồn truyền thông)</p></td><td><p>Liên kết giới thiệu, khớp ID</p></td><td><p>1-30 ngày HOẶC<br/>1-23 giờ</p></td><td><p>7 ngày</p></td></tr><tr><td><p>Mô hình xác suất</p></td><td><p><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Thích ứng</a></p></td><td><p>Lên đến 24 giờ</p></td></tr><tr><td rowspan="3"><p>Lượt xem qua</p><p>(<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">Nguồn truyền thông</a> được chọn)</p></td><td><p>Khớp ID</p></td><td><p>1-24 giờ</p><p>[Cho đến ngày 15 tháng 12 năm 2021, giới hạn tối đa là 7 ngày]</p></td><td><p>24 giờ</p></td></tr><tr><td><p>Mô hình xác suất</p></td><td><p><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Thích ứng</a></p></td><td><p>Lên đến 24 giờ</p></td></tr><tr><td><p>Mô hình xác suất (đa nền tảng)</p></td><td><p>1-72 giờ</p></td><td><p>24 giờ</p></td></tr></tbody></table>

<div id="probabilistic-modeling-lookback-window" />

### Khung thời gian xem lại mô hình xác suất

Khung thời gian xem lại mô hình xác suất, được sử dụng để duy trì độ chính xác của phân bổ, có các đặc điểm sau:

* Áp dụng cho cả lượt nhấp và lượt hiển thị
* Có thời lượng thích ứng lên tới 24 giờ
* Bỏ qua cài đặt thời lượng của khung thời gian được gửi trên đường dẫn phân bổ
* Có thời lượng ngắn hơn các khung thời gian mà các mô hình xác định sử dụng

Để tìm hiểu thêm, hãy đọc về <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#probabilistic-modeling">phương thức mô hình xác suất của AppsFlyer</Anchor>.

<div id="lookback-window-setup" />

## Thiết lập khung thời gian xem lại

Sau đây, chúng tôi liệt kê quy trình thiết lập khung thời gian xem lại cho SRN và Đường dẫn Phân bổ

<Tabs>
<Tab title="Khung thời gian Xem lại cho SRN">

<div id="attribution-lookback-window-for-srns" />

### Khung thời gian xem lại phân bổ cho SRN

> 🚧 **Quan trọng!**
>
> Mỗi SRN có khung thời gian xem lại mặc định riêng. Chúng tôi khuyên bạn nên khớp giá trị khung thời gian xem lại trong AppsFlyer với giá trị của SRN để giảm thiểu tình trạng không nhất quán. Thay đổi giá trị đó có thể dẫn đến tình trạng không nhất quán. Để tìm hiểu thêm, hãy xem [ví dụ về tình trạng không nhất quán với SRN](#các-tình-huống-và-ví-dụ).

1. Từ bảng điều khiển AppsFlyer của bạn, đi đến **Active Integrations.**
2. Tìm kiếm và chọn SRN - xem <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#srn-được-tích-hợp-với-appsflyer">danh sách các SRN được hỗ trợ</Anchor>.
3. Phân bổ lượt xem được bật theo mặc định.
4. Trong thẻ **Integration**, cuộn xuống đến cấu hình **Click-through attribution** và **View-through attribution**.
5. Sử dụng thanh trượt để đặt khung thời gian phân bổ

Xem từng khung thời gian xem lại cho SRN bên dưới:

| SRN | Khung thời gian Xem lại Lượt nhấp mặc định (ngày) | Khung thời gian Xem lại Lượt xem mặc định (giờ) |
| --- | --- | --- |
| Google | 30 | 24 |
| Quảng cáo Meta | 7 | 24 |
| Snapchat | 28 | 24 |
| Twitter | 14 | 24 |
| Apple Search Ads | 30 | Không áp dụng |
| Oath (YahooGemini) | 7 | 24 |

</Tab>

<Tab title="Khung thời gian Xem lại cho Đường dẫn Phân bổ">

<div id="attribution-lookback-window-with-attribution-links" />

### Khung thời gian xem lại phân bổ với các đường dẫn phân bổ

1. Từ bảng điều khiển AppsFlyer của bạn, đi đến **Active Integrations.**
2. Tìm kiếm và lựa chọn đối tác.
3. Phân bổ lượt xem được bật theo mặc định.
4. Nhấp vào thẻ **Attribution link**.
5. Chọn nếu bạn muốn đặt thời gian theo ngày hoặc giờ.
6. Sử dụng các thanh trượt bên dưới **Click-through attribution** (thông số `af_click_lookback`) và **View-through attribution** (thông số `af_viewthrough_lookback`) để đặt khung thời gian phân bổ.  
   Thời gian đã chọn sẽ tự động được phản ánh trong đường dẫn phân bổ.
7. Chọn các thông số tương ứng với chiến dịch, tức là tên chiến dịch, bộ quảng cáo, v.v.
8. Sao chép và lưu liên kết - đây là liên kết mà bạn cung cấp cho mạng quảng cáo.

> 👍 **Lời khuyên**
>
> * Bạn muốn biết một số gợi ý và thủ thuật để cấu hình khung thời gian xem lại? Hãy xem <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">khóa học ngắn, bổ ích</Anchor> này trên Cổng thông tin Học tập AppsFlyer.
> * [Nhấp vào đây](/docs/set-up-lookback-windows#lookback-in-hours-for-flash-campaigns) để tìm hiểu trường hợp bạn nên sử dụng số giờ cho khung thời gian phân bổ.

<div id="lookback-window-in-onelink" />

### Khung thời gian xem lại trong OneLink™

Bạn cũng có thể đặt khung thời gian xem lại trong OneLink.

1. <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template">Cấu hình OneLink</Anchor>
2. <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#tạo-liên-kết-onelink">Tạo Đường dẫn Phân bổ Tùy chỉnh</Anchor>
3. Trong **Advanced**, bật **Customize Lookback Window** và đặt khung thời gian xem lại.

</Tab>
</Tabs>

<div id="distribution-of-first-app-launches" />

## Phân bổ các lần khởi chạy ứng dụng đầu tiên

Dưới đây là biểu đồ thể hiện sự phân bổ các lần khởi chạy ứng dụng đầu tiên kể từ ngày tương tác.

[![](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)

Biểu đồ có thể giúp bạn hiểu rõ hơn về số lượng người dùng cài đặt ứng dụng. Đây là một phần chức năng của khung thời gian xem lại.

Phần lớn người dùng, hơn 97%, khởi chạy ứng dụng đã làm điều đó trong vòng 7 ngày kể từ khi tương tác với quảng cáo. 2% còn lại đã làm điều đó trong khoảng thời gian từ ngày 7 đến cuối khung thời gian xem lại (ngày 30).

Trên thực tế, gần 62% số người dùng khởi chạy ứng dụng đã làm điều đó trong vòng 15 phút sau khi tương tác với quảng cáo. 72% người dùng đã làm điều đó trong vòng một giờ đầu tiên.

<div id="scenarios-and-examples" />

## Các tình huống và ví dụ

Dưới đây là danh sách các tình huống có thể xảy ra và ví dụ về việc sử dụng khung thời gian xem lại.

<div id="srn-discrepancy-srn-lookback-longer-than-appsflyer" />

<Accordion title="Sự không nhất quán với SRN: Khung thời gian xem lại của SRN lâu hơn AppsFlyer">

Bạn đặt một chiến dịch trên Twitter và cấu hình khung thời gian xem lại lượt nhấp thành 7 ngày. Mặt khác, Twitter có khung thời gian xem lại mặc định là 14 ngày.

[![srn-discrepancy-srn-lookback-larger-than-appsflyer.png](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)

</Accordion>

<div id="srn-lookback-smaller-than-appsflyer" />

<Accordion title="Khung thời gian xem lại của SRN ít hơn AppsFlyer">

Bạn đặt một chiến dịch trên Twitter và cấu hình khung thời gian xem lại lượt nhấp thành 28 ngày. Mặt khác, Twitter có khung thời gian xem lại mặc định là 14 ngày.

[![srn-lookback-smaller-than-appsflyer.png](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)

</Accordion>

<div id="attribution-link-without-a-lookback-window-parameter" />

<Accordion title="Đường dẫn phân bổ không có thông số khung thời gian xem lại">

Có thể có một đường dẫn phân bổ không có thông số khung thời gian xem lại. Trong những trường hợp đó, AppsFlyer mặc định đặt khung thời gian xem lại là 7 ngày đối với lượt nhấp và đặt khung thời gian xem lại là 1 ngày đối với lượt hiển thị.

</Accordion>

<div id="lookback-in-hours-for-flash-campaigns" />

<Accordion title="Xem lại sau vài giờ đối với các chiến dịch chớp nhoáng">

Chiến dịch chớp nhoáng là những chiến dịch có mục đích nhắc nhở người dùng cài đặt ứng dụng càng nhanh càng tốt và trong khung thời gian khuyến mãi ngắn.

Một ứng dụng thương mại điện tử có tên SuperShopping chạy một chiến dịch chớp nhoáng. Trong chiến dịch này, người dùng cài đặt ứng dụng trong vòng một giờ sẽ nhận được ưu đãi đặc biệt.

Johnny, nhà tiếp thị chính của SuperShopping, tạo Đường dẫn phân bổ và đặt khung thời gian xem lại thành 1 giờ. Bằng cách này, Johnny biết được số lượng người dùng hưởng ứng chiến dịch.

Ngoài ra, nhà phát triển ứng dụng có thể xác định người dùng đến từ chiến dịch chớp nhoáng này và cung cấp các chương trình khuyến mãi mà chiến dịch quảng cáo.

</Accordion>

> 👍 **Lời khuyên**
>
> Bạn muốn biết một số gợi ý và thủ thuật về khung thời gian xem lại và phân bổ? Hãy xem <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">khóa học ngắn, bổ ích này trên Cổng thông tin Học tập AppsFlyer</Anchor>.

<div data-zendesk-anchors="lookback-windows=khung-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i configurable-lookback-windows-per-attribution-type=khung-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-c%C3%B3-th%E1%BB%83-c%E1%BA%A5u-h%C3%ACnh-cho-m%E1%BB%97i-lo%E1%BA%A1i-ph%C3%A2n-b%E1%BB%95 probabilistic-modeling-lookback-window=khung-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-m%C3%B4-h%C3%ACnh-x%C3%A1c-su%E1%BA%A5t lookback-window-setup=thi%E1%BA%BFt-l%E1%BA%ADp-khung-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i attribution-lookback-window-for-srns=khung-th%E1%BB%9Di-gian-xem-l%E1%BA%A1i-ph%C3%A2n-b%E1%BB%95-cho-srn lookback-window-in-onelink%E2%84%A2=lookback-window-in-onelink distribution-of-first-app-launches=ph%C3%A2n-b%E1%BB%95-c%C3%A1c-l%E1%BA%A7n-kh%E1%BB%9Fi-ch%E1%BA%A1y-%E1%BB%A9ng-d%E1%BB%A5ng-%C4%91%E1%BA%A7u-ti%C3%AAn scenarios-and-examples=c%C3%A1c-t%C3%ACnh-hu%E1%BB%91ng-v%C3%A0-v%C3%AD-d%E1%BB%A5" />
