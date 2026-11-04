---
title: Báo cáo nhà quảng cáo Data Locker
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-11-11T09:48:51Z'
  edited_at: '2023-11-08T10:05:02Z'
  id: 4410643856657
  locale: vi
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/vi/articles/4410643856657
---
> **Tổng quan:** Báo cáo dữ liệu thô và hợp nhất có sẵn qua Data Locker

<div id="reports-available-via-data-locker-for-advertisers" />

## Báo cáo có sẵn qua Data Locker dành cho nhà quảng cáo

<table><thead><tr><th>Loại dữ liệu</th><th>Nhóm báo cáo</th><th>Cần đăng ký Data Locker</th></tr></thead><tbody><tr><td>Thô</td><td>Hành trình của người dùng—dữ liệu thô</td><td>Có (2)</td></tr><tr><td>Thô</td><td>Protect360</td><td>Có</td></tr><tr><td>Thô</td><td>Phân bổ trên cơ sở người dùng (PBA) </td><td>Không (1)</td></tr><tr><td>Thô</td><td>Tính gia tăng</td><td>Không (1)</td></tr><tr><td>Thô</td><td>SKAN</td><td>Không (1)</td></tr><tr><td>Thô</td><td>Doanh thu Quảng cáo</td><td>Có</td></tr><tr><td>Thô</td><td>CTV</td><td>Có</td></tr><tr><td>Đã hợp nhất</td><td>Phân tích nhóm người</td><td>Không (1)</td></tr><tr><td colspan="3"><p>(1) Nếu không đăng ký Data Locker, bạn phải cung cấp <a href="./data-locker-for-marketers#storage-options" target="_blank">bộ nhớ lưu trữ do bạn sở hữu</a>.</p><p>(2) Ngoại trừ tương tác Đa nền tảng</p></td></tr></tbody></table>

<div id="data-freshness-explanations" />

<Accordion title="Diễn giải về tính cập nhật của dữ liệu">

Dưới đây là phần giải thích về các thuật ngữ về tính cập nhật của dữ liệu được tham chiếu trong phần nội dung của bài viết. 

| Thuật ngữ | Chi tiết |
| --- | --- |
| 1-3 giờ | <ul><li>Tính sẵn sàng của báo cáo:<ul><li>95% báo cáo đã sẵn sàng và có sẵn trong bộ chứa trong vòng 1 giờ kể từ thời điểm xảy ra sự kiện.</li><li>99% báo cáo đã sẵn sàng và có sẵn trong bộ chứa trong vòng 3 giờ kể từ thời điểm xảy ra sự kiện.</li></ul></li></ul> |
| Lượt gỡ cài đặt hàng ngày | <ul><li>Dữ liệu gỡ cài đặt được lập hàng ngày.</li><li>Thường có sẵn vào lúc 10:00-12:00 UTC.</li><li>Thường được ghi vào thư mục h=2. Có nghĩa là thư mục h=2 chứa các lượt gỡ cài đặt được báo cáo vào ngày hôm trước. Tuy nhiên, dữ liệu có thể được truyền trực tuyến vào một thư mục sau đó; do đó, quá trình nhập của bạn phải đọc dữ liệu của tất cả thư mục trong thư mục gỡ cài đặt. Nghĩa là h=1–24 và h=late. Ví dụ, báo cáo đối với dữ liệu đã tạo trong ngày thứ Hai sẽ nằm trong thư mục h=2 của ngày thứ Ba. Dữ liệu sẽ có sẵn sau 10:00 UTC vào ngày thứ Ba.</li></ul> |
| Hàng ngày+1 | Dữ liệu doanh thu quảng cáo sẽ có sau 1 ngày, nghĩa là dữ liệu được tạo vào ngày thứ Hai sẽ có trong thư mục h=23 thứ Hai sau 20:00 UTC vào thứ Ba. Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#data-freshness">tính cập nhật của dữ liệu doanh thu quảng cáo</Anchor> |

</Accordion>

<div id="h_01K9CROSSPLATFORMREPORT" />

<div id="conversion-report" />

<div id="advanced-reports" />

<div id="note-1" />

<div id="note" />

<div id="advanced-raw-data-reports-beta" />

<div id="raw-data-reports" />

## Báo cáo dữ liệu thô

<div id="user-journey" />

<Accordion title="Hành trình của người dùng">

Để biết mô tả về các loại báo cáo, hãy xem phần <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">báo cáo hành trình của người dùng</Anchor>.

| Danh mục | Loại báo cáo (chủ đề) | Tính cập nhật của dữ liệu | Tự nhiên/Không tự nhiên | Là đặc biệt đối với Data Locker |
| --- | --- | --- | --- | --- |
| Thu hút người dùng | Lượt nhấp | 1-3 giờ | Không áp dụng | ✓ |
| Nhắm mục tiêu lại | Lượt nhấp | 1-3 giờ | Không áp dụng | ✓ |
| Thu hút người dùng | Lượt hiển thị | 1-3 giờ | Không áp dụng | ✓ |
| Nhắm mục tiêu lại | Lượt hiển thị | 1-3 giờ | Không áp dụng | ✓ |
| Thu hút người dùng | Lượt cài đặt | 1-3 giờ | Cả hai |  |
| Thu hút người dùng | Sự kiện trong ứng dụng | 1-3 giờ | Cả hai |  |
| Thu hút người dùng | Doanh thu quảng cáo được phân bổ | Hàng ngày+1 | Không tự nhiên |  |
| Thu hút người dùng | Doanh thu quảng cáo tự nhiên | Hàng ngày+1 | Tự nhiên |  |
| Nhắm mục tiêu lại | Doanh thu quảng cáo nhắm mục tiêu lại | Hàng ngày+1 | Không tự nhiên |  |
| Nhắm mục tiêu lại | Lượt chuyển đổi | 1-3 giờ | Không tự nhiên |  |
| Nhắm mục tiêu lại | Sự kiện trong Ứng dụng | 1-3 giờ | Không tự nhiên |  |
| Nhắm mục tiêu lại | Các phiên | 1-3 giờ | Cả hai | ✓ |
| Thu hút người dùng | Các phiên | 1-3 giờ | Cả hai | ✓ |
| Thu hút người dùng | Gỡ cài đặt | Lượt gỡ cài đặt hàng ngày | Không tự nhiên |  |
| Thu hút người dùng | Các lượt gỡ cài đặt tự nhiên | Lượt gỡ cài đặt hàng ngày | Tự nhiên |  |
| Lượt cài đặt lại | Lượt cài đặt lại | 1-3 giờ | Không tự nhiên |  |
| Lượt cài đặt lại | Lượt cài đặt lại tự nhiên | 1-3 giờ | Tự nhiên |  |
| Thu hút người dùng | Tương tác đa nền tảng | Hàng giờ | Cả hai | ✓ |

</Accordion>

<div id="protect360" />

<Accordion title="Protect360">

Xem phần <Anchor target="_blank" href="/marketers/vi/docs/protect360-raw-data-reports">giới thiệu về báo cáo Protect360</Anchor>

| Loại báo cáo (chủ đề) | Tính cập nhật của dữ liệu |
| --- | --- |
| Lượt cài đặt bị chặn | 1-3 giờ |
| Các sự kiện trong ứng dụng bị chặn | 1-3 giờ |
| Lượt nhấp bị chặn | 1-3 giờ |
| Lượt cài đặt hậu phân bổ | Hàng ngày<br /><br />Báo cáo của mỗi ngày chứa các lượt cài đặt sau phân bổ được báo cáo vào ngày hôm trước. Ví dụ: báo cáo cho dữ liệu được tạo vào ngày thứ Hai sẽ nằm trong báo cáo ngày thứ Ba. |

</Accordion>

<div id="peoplebased-attribution" />

<Accordion title="Phân bổ trên cơ sở người dùng">

**Tính cập nhật của dữ liệu**

Có sẵn hàng ngày 10-12 giờ sau khi kết thúc ngày hôm trước UTC. Ví dụ, dữ liệu nhận được vào thứ Hai sẽ được xử lý sau khi kết thúc ngày đó và có sẵn trong thư mục h=23 thứ Hai. Dữ liệu có sẵn trước 12:00 UTC vào thứ Ba

**Những điều cần lưu ý**

* Dữ liệu của tất cả các gói thương hiệu PBA trong tài khoản luôn được cung cấp mà không cần xem xét bộ lọc ứng dụng.
* Phân tách dữ liệu theo ứng dụng không khả dụng.

| Loại báo cáo (chủ đề) |
| --- |
| <Anchor target="_blank" href="/marketers/vi/docs/pba-raw-data-reports#website-visits-and-website-events">Lượt truy cập trang web</Anchor> |
| <Anchor target="_blank" href="/marketers/vi/docs/pba-raw-data-reports#website-visits-and-website-events">Sự kiện trang web</Anchor> |
| <Anchor target="_blank" href="/marketers/vi/docs/pba-raw-data-reports#websiteassisted-installs::7e12586d">Lượt cài đặt được trang web hỗ trợ</Anchor> |
| <Anchor target="_blank" href="/marketers/vi/docs/pba-raw-data-reports#conversion-paths">Lộ trình chuyển đổi</Anchor> |

</Accordion>

<div id="incrementality" />

<Accordion title="Tính gia tăng">

Xem <Anchor target="_blank" href="/marketers/vi/docs/incrementality-for-remarketing-overview#available-reports">Báo cáo gia tăng</Anchor>

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

Giới thiệu về <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports">báo cáo dữ liệu thô SKAN</Anchor>

**Tính cập nhật của dữ liệu**

* Dữ liệu có sẵn vào ngày tiếp theo sau ngày AppsFlyer nhận được đăng lại hoặc dữ liệu được API báo cáo cho AppsFlyer
* Dữ liệu được chứa trong thư mục h=23 kể từ ngày AppsFlyer nhận được dữ liệu. Ví dụ: Nếu được nhận vào thứ Hai, thì được đăng sẽ được xử lý sau khi kết thúc ngày. Quá trình xử lý sẽ hoàn tất trước 12:00 UTC ngày thứ Ba, dữ liệu sẽ có sẵn trong thư mục h=23 thứ Hai.

| Loại báo cáo (chủ đề) |
| --- |
| Đăng lại |
| Bản sao đăng lại (được iOS gửi trực tiếp tới AppsFlyer) |
| Lượt cài đặt |
| Tải lại |
| Sự kiện trong ứng dụng |
| Phương diện quảng cáo SRN |

</Accordion>

<div id="ad-revenue" />

<Accordion title="Doanh thu Quảng cáo">

Xem <Anchor target="_blank" href="/marketers/vi/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">dữ liệu thô về doanh thu quảng cáo</Anchor>

</Accordion>

<div id="ctv" />

<Accordion title="Dữ liệu nền tảng CTV, PC và bảng điều khiển">

Xem <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-data-via-data-locker">dữ liệu nền tảng CTV, PC và console thông qua Data Locker</Anchor>

</Accordion>

<div id="creative-optimization-etl" />

<div id="advanced-aggregated-reports" />

<div id="aggregated-reports" />

## Báo cáo tổng hợp

<div id="cohort-analytics" />

<Accordion title="Phân tích nhóm người">

**Tính cập nhật của dữ liệu**

* Các báo cáo được ghi vào thư mục h=23.
* Các báo cáo này thường có sẵn vào lúc 10:00-12:00 UTC trong thư mục h=23 của ngày trước đó.
* Quá trình xử lý sẽ được hoàn tất trước 12:00 UTC ngày thứ Ba, dữ liệu được có sẵn trong thư mục thứ Hai và không được đặt trong thư mục h

| Loại báo cáo (chủ đề) |
| --- |
| <Anchor target="_blank" href="/marketers/vi/docs/cohort-analytics-via-data-locker">Nhóm người thống nhất</Anchor> |
| <Anchor target="_blank" href="/marketers/vi/docs/cohort-analytics-via-data-locker">Thu hút người dùng theo nhóm người</Anchor> |
| <Anchor target="_blank" href="/marketers/vi/docs/cohort-analytics-via-data-locker">Nhắm mục tiêu lại theo nhóm người</Anchor> |

</Accordion>

<div data-zendesk-anchors="reports-available-via-data-locker-for-advertisers=b%C3%A1o-c%C3%A1o-c%C3%B3-s%E1%BA%B5n-qua-data-locker-d%C3%A0nh-cho-nh%C3%A0-qu%E1%BA%A3ng-c%C3%A1o 01H7WFZN6P1S49NYX8Q0W55P0B=b%C3%A1o-c%C3%A1o-c%C3%B3-s%E1%BA%B5n-qua-data-locker-d%C3%A0nh-cho-nh%C3%A0-qu%E1%BA%A3ng-c%C3%A1o 01H7WFZN6PQWASTMXM9V72QZER=data-freshness-explanations raw-data-reports=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 01H7WFZN6P94YW1V79NT3HV5G4=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 01H7WFZN6PD75S557PDB5PSFFR=user-journey 01H7WFZN6QY2GV69N464EE196M=protect360 01H7WFZN6QW72FDBTMW2ZD7NZQ=peoplebased-attribution 01H7WFZN6QZ1B7BS6E59RVAF30=incrementality 01H7WFZN6Q0P99DCFA7MZQTVSX=skan 01H7WFZN6Q717F9Z1HG38JVBG3=ad-revenue 01H7WFZN6QMJGSAJR00MHYJB6Z=ctv aggregated-reports=b%C3%A1o-c%C3%A1o-t%E1%BB%95ng-h%E1%BB%A3p 01H7WFZN6Q90AT8N0VY5PKQ407=b%C3%A1o-c%C3%A1o-t%E1%BB%95ng-h%E1%BB%A3p 01H7WFZN6QNKXTRM7G6VFANSZ7=cohort-analytics" />
