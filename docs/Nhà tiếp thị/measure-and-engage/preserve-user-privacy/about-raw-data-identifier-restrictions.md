---
title: Hạn chế nội dung dữ liệu thô—nguồn truyền thông hoặc mã định danh người dùng
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2020-03-23T08:29:01Z'
  edited_at: '2023-11-29T02:18:02Z'
  id: 360006868017
  locale: vi
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/vi/articles/360006868017
---
> **Khái quát:** Các trường trong một số báo cáo dữ liệu thô bị hạn chế do các giới hạn về quyền riêng tư. Trong các trường hợp khác, đối tác yêu cầu biên tập lại nguồn truyền thông khi chia sẻ đăng lại lên nền tảng của bên thứ ba. Bài viết này mô tả các hạn chế và ý nghĩa của chúng.

<div id="raw-data-restriction" />

## Hạn chế dữ liệu thô

AppsFlyer hạn chế tính khả dụng của một số trường trong báo cáo dữ liệu thô để duy trì quyền riêng tư người dùng. Điều này phù hợp với cài đặt <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">AAP</Anchor> của nhà quảng cáo hoặc theo chính sách chia sẻ dữ liệu của các mạng quảng cáo để cung cấp dữ liệu. Các hạn chế khác nhau tùy thuộc vào loại báo cáo và lý do hạn chế. Các hạn chế ảnh hưởng đến dữ liệu thô được cung cấp bằng <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">các công cụ phân phối dữ liệu thô</Anchor>.

<div id="media-source-restrictions" />

### Hạn chế nguồn truyền thông

Bảng sau đây liệt kê các hạn chế đối với mỗi nguồn truyền thông.

<div id="note" />

> 📘 **Lưu ý**
>
> * Cung cấp không giới hạn dữ liệu phân tích và hợp nhất từ nền tảng AppsFlyer
> * <Anchor target="_blank" href="/marketers/vi/docs/discrepancies-between-appsflyer-and-third-party-platforms">Hạn chế đăng lại trên nền tảng của bên thứ ba:</Anchor>
>   * Theo mô tả trong bảng bên dưới, đăng lại cho các sự kiện bị hạn chế bởi các nguồn truyền thông **không được gửi tới nền tảng của bên thứ ba** (chẳng hạn như nền tảng phân tích và tiếp thị).
>   * Những hạn chế khác đối với đăng lại có thể áp dụng cho các sự kiện khác

| Nguồn truyền thông | Hạn chế loại phân bổ |
| --- | --- |
| <span id="meta-ads"></span>Quảng cáo Meta | <ul><li>Cho đến ngày 28 tháng 10 năm 2021: Lượt xem qua</li><li>Bắt đầu từ ngày 29 tháng 10 năm 2021: Lượt nhấp qua và lượt xem qua. Tuy nhiên, nếu bạn bật cơ chế Liên kết giới thiệu Cài đặt Google Play, bạn có thể được cung cấp một số dữ liệu lượt nhấp qua. Lưu ý rằng Liên kết giới thiệu Cài đặt Google Play không dành cho các chiến dịch nhắm mục tiêu lại và có sẵn mà không bị hạn chế.</li><li>**Trường hợp ngoại lệ:** Tất cả các dữ liệu từ <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-integration-setup#app-aem-for-reengagement">phân bổ thu hút lại bằng liên kết sâu</Anchor> có sẵn mà không có giới hạn báo cáo.</li></ul> |
| <span id="pinterest"></span>Pinterest | Bắt đầu từ ngày 4 tháng 9 năm 2023: Phân bổ lượt nhấp qua và lượt xem hết |
| <span id="roku-oneview"></span>Roku OneView | Lượt nhấp qua và lượt xem qua cho tất cả các nền tảng (CTV và thiết bị di động) |
| <span id="samsung-dsp"></span>Samsung DSP | Kể từ ngày 17 tháng 10 năm 2023, việc phân bổ lượt nhấp và lượt xem bị hạn chế. Dưới đây là các trường **được điền** vào các công cụ phân phối dữ liệu thô:<ul><li>Nguồn phương tiện (samsungdsp\_int)</li><li>Kênh</li><li>Kiểu tương tác được phân bổ</li><li>Thời gian chạm được phân bổ</li><li>Chi tiết chiến dịch: Tên chiến dịch, ID chiến dịch, tên nhóm quảng cáo, ID nhóm quảng cáo, tên quảng cáo và ID quảng cáo</li></ul> |
| <span id="snapchat"></span>Snapchat | <ul><li>Bắt đầu từ ngày 1 tháng 3 năm 2023, không đưa các lượt gỡ cài đặt Snapchat vào báo cáo dữ liệu thô</li><li>Kể từ ngày 13 tháng 9 năm 2023, phân bổ lượt xem hết bị hạn chế. Dưới đây là các trường **được điền** vào các công cụ phân phối dữ liệu thô:<ul><li>Nguồn truyền thông (snapchat\_int)</li><li>Kênh</li><li>Loại tương tác được phân bổ (lượt hiển thị)</li><li>Thời gian tương tác được phân bổ (chỉ được báo cáo dưới dạng ngày - "dd/mm/yyyy")</li><li>Chiến dịch được báo cáo là *"restricted"*</li></ul></li></ul> |
| <span id="tiktok-for-business"></span>TikTok dành cho Doanh nghiệp | <ul><li>Từ ngày 28 tháng 7 đến ngày 23 tháng 10 năm 2021, dữ liệu phân bổ lượt xem qua bị hạn chế.</li><li>Kể từ ngày 23 tháng 10 năm 2021, phân bổ lượt xem qua bị hạn chế. Dưới đây là các trường **được điền** vào các công cụ phân phối dữ liệu thô:<ul><li>Nguồn truyền thông (bytedanceglobal\_int và tiktokglobal\_int)</li><li>Kênh</li><li>Loại tương tác được phân bổ (lượt hiển thị)</li><li>Thời gian tương tác được phân bổ (chỉ được báo cáo dưới dạng ngày - "dd/mm/yyyy")</li><li>Chiến dịch được báo cáo là *"restricted"*</li></ul></li></ul> |
| <span id="twitter"></span>Twitter | Trong một số trường hợp, Twitter không cho phép cung cấp dữ liệu thô trên nền tảng AppsFlyer. Trong những trường hợp này, sự kiện không xuất hiện trong báo cáo dữ liệu thô. |

<div id="raw-data-context" />

### Ngữ cảnh dữ liệu thô

Các hạn chế cấp độ trường của dữ liệu thô phụ thuộc vào ngữ cảnh của dữ liệu, như được liệt kê trong bảng sau.

| Loại hạn chế | Báo cáo bị ảnh hưởng |
| --- | --- |
| [Nguồn truyền thông bị hạn chế](/docs/about-raw-data-identifier-restrictions#hạn-chế-nguồn-truyền-thông): Nguồn mang đến người dùng | <ul><li>Phân bổ: Lượt cài đặt, lượt chuyển đổi nhắm mục tiêu lại, lượt gỡ cài đặt</li><li>Sự kiện trong ứng dụng, phiên</li><li>Báo cáo Protect360</li></ul> |
| Bị hạn chế hoàn toàn | <ul><li>Lượt nhấp</li><li>Lượt hiển thị</li><li>Lượt nhấp bị chặn (Protect360)</li></ul> |

**Phân phối dữ liệu thô**

Dữ liệu phân bổ ở mức người dùng trong AppsFlyer có sẵn bằng cách sử dụng các công cụ phân phối dữ liệu thô sau:

* Data Locker
* API Pull dữ liệu thô
* API Push
* Trang xuất Bảng điều khiển
* Đăng lại đến các mạng
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">API nhận dữ liệu chuyển đổi (GCD)</Anchor> trong ngữ cảnh của API dữ liệu ở mức người dùng từ phía máy khách

<div id="unavailable-attribution-fields" />

<Accordion title="Các trường phân bổ không khả dụng">

Dưới đây là các trường không khả dụng khi nguồn truyền thông bị hạn chế:

| Tên hiển thị | Tên API |
| --- | --- |
| Quảng cáo | af\_ad |
| ID Quảng cáo | af\_ad\_id |
| Loại quảng cáo | af\_ad\_type |
| Bộ quảng cáo | af\_adset |
| ID Bộ quảng cáo | af\_adset\_id |
| Khung thời gian xem lại phân bổ | af\_attribution\_lookback |
| ID Chiến dịch | af\_c\_id |
| Kênh | af\_channel |
| Đơn vị tiền tệ của chi phí | af\_cost\_currency |
| Mô hình Chi phí | af\_cost\_model |
| Giá trị Chi phí | af\_cost\_value |
| Từ khóa | af\_keywords |
| Đối tác | af\_prt |
| ID trang | af\_siteid |
| ID Trang web phụ | af\_sub\_siteid |
| Thông số phụ [n] (n=1-5) | af\_sub[n] (n=1-5) |
| Thời gian chạm được phân bổ | attributed\_touch\_time |
| Kiểu tương tác được phân bổ | attributed\_touch\_type |
| Chiến dịch | chiến dịch |
| Người đóng góp [n] nguồn truyền thông (n=1-3) | contributor[n]\_media\_source (n=1-3) |
| Người đóng góp [n] đối tác (n=1-3) | contributor[n]\_af\_prt  <br />(n=1-3) |
| Người đóng góp [n] chiến dịch (n=1-3) | contributor[n]\_campaign  <br />(n=1-3) |
| Người đóng góp [n] kiểu khớp (n=1-3) | contributor[n]\_match\_type (n=1-3) |
| Người đóng góp [n] thời gian tương tác (n=1-3) | contributor[n]\_touch\_time  <br />(n=1-3) |
| Người đóng góp [n] kiểu tương tác (n=1-3) | contributor[n]\_touch\_type  <br />(n=1-3) |
| URL Liên kết sâu | deeplink\_url |
| Liên kết giới thiệu HTTP | http\_referrer |
| Cài đặt App Store | install\_app\_store |
| ID từ khóa | keyword\_id |
| Loại so khớp từ khóa | keyword\_match\_type |
| Loại so khớp | match\_type |
| ID tài khoản mạng | network\_account\_id |
| URL gốc | original\_url |
| Thời gian tương tác lại | af\_reengagement\_window |
| Trang sản phẩm của cửa hàng | store\_product\_page |

</Accordion>

<div id="identifier-restriction" />

<Accordion title="Hạn chế mã định danh">

Khi hạn chế mã định danh, các trường được liệt kê trong bảng sau đây là những trường duy nhất có trong báo cáo dữ liệu thô.

| Tên API |
| --- |
| <span id="event_time"></span>event\_time |
| <span id="event_name"></span>event\_name |
| <span id="event_revenue"></span>event\_revenue |
| <span id="event_revenue_currency"></span>event\_revenue\_currency |
| <span id="event_revenue_usd"></span>event\_revenue\_usd |
| <span id="af_cost_model"></span>af\_cost\_model |
| <span id="af_cost_value"></span>af\_cost\_value |
| <span id="af_cost_currency"></span>af\_cost\_currency |
| <span id="event_source"></span>event\_source |
| <span id="media_source"></span>media\_source |
| <span id="af_channel"></span>af\_channel |
| <span id="campaign"></span>chiến dịch |
| <span id="af_c_id"></span>af\_c\_id |
| <span id="af_adset"></span>af\_adset |
| <span id="af_adset_id"></span>af\_adset\_id |
| <span id="af_ad"></span>af\_ad |
| <span id="af_ad_id"></span>af\_ad\_id |
| <span id="af_ad_type"></span>af\_ad\_type |
| <span id="af_siteid"></span>af\_siteid |
| <span id="af_sub_siteid"></span>af\_sub\_siteid |
| <span id="app_id"></span>app\_id |
| <span id="app_name"></span>app\_name |
| <span id="bundle_id"></span>bundle\_id |
| <span id="is_retargeting"></span>is\_retargeting |
| <span id="retargeting_conversion_type"></span>retargeting\_conversion\_type |
| <span id="is_primary_attribution"></span>is\_primary\_attribution |
| <span id="af_attribution_lookback"></span>af\_attribution\_lookback |
| <span id="af_reengagement_window"></span>af\_reengagement\_window |
| <span id="country_code"></span>country\_code |
| <span id="blocked_reason"></span>blocked\_reason |
| <span id="blocked_reason_value"></span>blocked\_reason\_value |
| <span id="blocked_reason_rule"></span>blocked\_reason\_rule |
| <span id="blocked_sub_reason"></span>blocked\_sub\_reason |
| <span id="platform"></span>nền tảng |
| <span id="is_paid_media"></span>is\_paid\_media |

</Accordion>

<div id="faq" />

## Câu hỏi thường gặp

<div id="what-events-are-restricted" />

<Accordion title="Những sự kiện nào bị hạn chế?">

Các sự kiện bị hạn chế, như được nêu chi tiết trong [bảng ở trên](/docs/about-raw-data-identifier-restrictions#hạn-chế-nguồn-truyền-thông), có thể bao gồm các chuyển đổi (lượt cài đặt và tương tác lại) cũng như các sự kiện trong ứng dụng được liên kết mà mạng quảng cáo hạn chế được phân bổ.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-raw-data-reports" />

<Accordion title="Nguồn truyền thông bị hạn chế ảnh hưởng đến báo cáo dữ liệu thô như thế nào?">

* Trường *media source* được điền *có bị hạn chế*.
* Các trường phân bổ được liệt kê trong bài viết này bị trống hoặc được điền là *null*.

**Ví dụ về báo cáo:** <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv">Dữ liệu thô bị hạn chế lượt cài đặt</Anchor> trong tập tin CSV. Các báo cáo dữ liệu thô khác được điền theo cách tương tự.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-postbacks-sent-to-partners" />

<div id="what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted" />

<Accordion title="Nguồn truyền thông bị hạn chế ảnh hưởng như thế nào đến các bài đăng lại được gửi tới đối tác?">

Đăng lại được gửi cho đối tác không chứa các trường phân bổ.

</Accordion>

<div id="how-do-restricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="Các sự kiện bị hạn chế tác động như thế nào đến việc đăng lại lên nền tảng của bên thứ ba?">

Bài đăng lại cho các mạng quảng cáo được phân bổ được liệt kê trong [bảng ở trên](/docs/about-raw-data-identifier-restrictions#hạn-chế-nguồn-truyền-thông) không được gửi tới nền tảng của bên thứ ba.

</Accordion>

<div id="do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="Các sự kiện không bị hạn chế có ảnh hưởng đến việc đăng lại lên nền tảng của bên thứ ba không?">

[Trong một số trường hợp](/docs/about-raw-data-identifier-restrictions#media-source-sharing-limitations-on-thirdparty-platforms), bài đăng lại cho các sự kiện không bị hạn chế được gửi tới nền tảng của bên thứ ba không bao gồm nguồn truyền thông. Điều này có nghĩa là phân bổ được ghi nhận là tự nhiên.

</Accordion>

<div id="what-about-the-data-of-assists-that-form-part-of-the-attribution" />

<Accordion title="Còn dữ liệu về các lượt hỗ trợ tạo thành một phần phân bổ thì sao?">

Dữ liệu liên quan đến lượt hỗ trợ được coi là dữ liệu phân bổ và không có sẵn.

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> <Anchor target="_blank" href="/marketers/vi/docs/user-level-data-retention">Lưu giữ dữ liệu ở cấp độ người dùng</Anchor>

<div data-zendesk-anchors="raw-data-restriction=h%E1%BA%A1n-ch%E1%BA%BF-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 01H7WQHTV9RM2JF2BV45XF626H=h%E1%BA%A1n-ch%E1%BA%BF-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 media-source-restrictions=h%E1%BA%A1n-ch%E1%BA%BF-ngu%E1%BB%93n-truy%E1%BB%81n-th%C3%B4ng 01H7WQHTV9HJEHHH1N8VN6APX6=h%E1%BA%A1n-ch%E1%BA%BF-ngu%E1%BB%93n-truy%E1%BB%81n-th%C3%B4ng 01H7WQHTV90YFRP3Z9AEP7ACRD=l%C6%B0u-%C3%BD raw-data-context=ng%E1%BB%AF-c%E1%BA%A3nh-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 01H7WQHTVA8H9FTBJ1FB6BJQ2A=ng%E1%BB%AF-c%E1%BA%A3nh-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 01H7WQHTVA0XP6B2H95EEM7EYD=unavailable-attribution-fields 01H7WQHTVA7ERWW1PC3DF5H0NP=identifier-restriction faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p 01H7WQHTVA5439QPE6GNXNKJ63=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p h_01HDBND48E05P1WV51ZJGD072N=what-events-are-restricted 01H7WQHTVAHCK7QDZ5P25YRQ2D=how-does-the-restricted-media-source-impact-raw-data-reports 01H7WQHTVABKATP6B6XN4NRC54=what-is-the-impact-on-postbacks-to-partners-when-the-media-source-is-restricted h_01HDBND48EDTAFBFXTADGWJADM=how-do-restricted-events-impact-postbacks-to-thirdparty-platforms h_01HE5TK3WSNBPM6W5D1Y9S6PDX=do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms 01H7WQHTVA60PWZ017WJMRTKVP=what-about-the-data-of-assists-that-form-part-of-the-attribution h_01HE7SCVN3VJ4Y6KF2QZSNBEMZ=xem-th%C3%AAm" />
