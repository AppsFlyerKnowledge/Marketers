---
title: 'Bản tin: Hỗ trợ SKAN 4 trong AppsFlyer'
metadata:
  keywords:
    - iOS
    - Marketers
    - SKAN
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2023-01-05T12:36:02Z'
  edited_at: '2023-08-30T15:43:56Z'
  id: 11938810583825
  locale: vi
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/vi/articles/11938810583825
---
| **Tiêu đề** | Giải pháp SKAdNetwork của AppsFlyer hiện hỗ trợ SKAN 4. Điều này bao gồm các thay đổi lớn đối với SKAN Conversion Studio cũng như bảng điều khiển và báo cáo SKAN. |
| --- | --- |
| **Ngày có Hiệu lực** | <ul><li>Ngày 15 tháng 2 năm 2023: Với SDK iOS tự nhiên V6.10 trở lên</li><li>Từ tháng 2, chúng tôi khuyến khích cập nhật lên phiên bản mới nhất V6.12 trở lên kể cả nếu bạn đang dùng V6.10<ul><li>Bạn có thể xem danh sách thay đổi <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-ios-sdk-release-notes">tại đây</Anchor></li></ul></li><li>Sắp tới: Hỗ trợ cho các SDK và trình cắm AppsFlyer khác</li></ul> |
| **Điều kiện tiên quyết** | Để có thể ghi lại dữ liệu iOS SKAN 4 đúng cách, cần những điều kiện sau:<ul><li><Anchor target="_blank" href="/marketers/vi/docs/appsflyer-ios-sdk-release-notes">SDK AppsFlyer phiên bản V6.12.1 trở lên</Anchor></li><li>Mạng quảng cáo phải tạo chữ ký quảng cáo cho SKAdNetwork V4.</li><li>Đối với các quảng cáo hiển thị trong ứng dụng, ứng dụng phải được dựng bằng SDK iOS 16.1 trở lên.</li><li>Đối với quảng cáo mạng, quảng cáo cần Safari 16.1 trở lên.</li><li>Ứng dụng được quảng cáo phải được App Store ký nhận và chạy trên thiết bị có iOS 16.1 trở lên.</li></ul> |
| **Hành động yêu cầu** | <ul><li>Cập nhật <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-ios-sdk-release-notes">SDK AppsFlyer của bạn lên V6.12.1 trở lên</Anchor></li><li>Trong AppsFlyer SKAN Conversion Studio, nâng cấp lên <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio#skan-4">chế độ đo lường SKAN 4</Anchor> và cấu hình các CV cho 3 khung thời gian SKAN (hoặc giữ cài đặt mặc định).</li></ul>**Lưu ý:** Khi bạn nâng cấp lên SKAN 4:<ul><li>Bộ đếm thời gian hoạt động cho các lượt cài đặt trước SKAN 4 là 48 giờ.</li><li>Bạn không thể quay lại phiên bản SKAN trước đó.</li></ul> |
| **Những thay đổi trong <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio#skan-4">SKAN Conversion Studio</Anchor>** | Chế độ đo lường SKAN 4 mới để cấu hình 3 khung thời gian SKAN |
| **Những thay đổi trong <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">bảng điều khiển</Anchor>** | <ul><li>Bảng điều khiển tổng quan SKAN bao gồm các trường mới (có sẵn trong cài đặt bảng) cho số sự kiện và doanh thu trong 3 khung thời gian SKAN:<ul><li>Số sự kiện D0-D2</li><li>Số sự kiện D0-D2 (đã được mô hình hóa)</li><li>Số sự kiện D3-D7</li><li>Số sự kiện D8-D35</li><li>Doanh thu D0-D2 ($)</li><li>Doanh thu D0-D2 ($) (đã được mô hình hóa)</li><li>Doanh thu D3-D7 ($)</li><li>Doanh thu D8-D35 ($)</li></ul></li><li>Chế độ xem bảng điều khiển SSOT hiển thị các trường dữ liệu D2, thay vì Khung thời gian hoạt động (AW). Đối với dữ liệu SKAN 3, trường này hiển thị tất cả dữ liệu khung thời gian hoạt động, ngay cả khi khung thời gian dài hơn hoặc ngắn hơn 2 ngày.</li></ul> |
| **Những thay đổi trong <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports">báo cáo</Anchor>** | <ul><li>Báo cáo SKAdNetwork bao gồm các trường mới sau để hỗ trợ SKAN 4:<ul><li>**skad\_postback\_sequence\_index**: Giá trị là một số nguyên đại diện cho khung thời gian SKAN, là`0`,`1` hoặc`2`. Đối với SKAN 3, giá trị sẽ là`0`.</li><li>**skad\_coarse\_conversion\_value**: Giá trị có thể là`low`,`medium` hoặc`high`. Đối với SKAN 3 giá trị là`null`.</li><li>**skad\_source\_identifier**: Giá trị là một chuỗi có tối đa 4 chữ số. Đối với SKAN 3, giá trị sẽ là`null`.</li><li>**skad\_source\_domain**: Giá trị là một chuỗi thể hiện nguồn quảng cáo trên web có thể phân bổ. Đối với SKAN 3, giá trị sẽ là`null`.</li><li>**ad\_network\_creative**: Giá trị là một chuỗi dựa trên việc làm phong phú dữ liệu nhận được từ mạng quảng cáo. Đối với SKAN 3, giá trị này trống.</li></ul></li><li>Các báo cáo Data Locker và API Push sau đây bị ảnh hưởng:</li></ul><ul><li>**skad\_installs** (thông qua Data Locker và API Push)</li><li>**skad\_redownloads** (thông qua Data Locker và API Push)</li><li>**skad\_inapps** (thông qua Data Locker và API Push)</li><li>**skad\_postbacks** (thông qua Data Locker)</li><li>**skad\_postbacks\_copy** (không bao gồm trường ad\_network\_creative) (thông qua Data Locker)</li><li><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx">Xem lược đồ báo cáo mẫu</Anchor></li></ul><ul><li>API ngày đến của đăng lại hợp nhất SKAN và API báo cáo hiệu suất hợp nhất SKAN chứa các trường SKAN 4. **Lưu ý**: Bạn phải dùng đường dẫn cho token API V2 cho SKAN 4.</li></ul> |