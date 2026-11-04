---
title: Định mức tạo báo cáo (giới hạn lưu lượng)
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2014-05-01T12:55:30Z'
  edited_at: '2023-11-09T05:07:38Z'
  id: 207034366
  locale: vi
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/vi/articles/207034366
---
> **Khái quát:** Cơ chế định mức (giới hạn lưu lượng) giới hạn số lượng báo cáo có thể được tạo mỗi ngày bởi cả API Pull và các trang xuất dữ liệu.

<div id="rate-limits-for-reports" />

## Giới hạn lưu lượng cho các báo cáo

Định mức giới hạn số lượng báo cáo có thể được tạo mỗi ngày cho mỗi loại báo cáo. Định mức sẽ khác nhau tùy theo gói đăng ký của bạn.

**Nguyên tắc:**

* **Đại lý**: Báo cáo API Pull do đại lý tạo được tính vào định mức của nhà quảng cáo đối với báo cáo API Pull. Nếu bạn thường xuyên đạt đến giới hạn định mức, hãy liên hệ với Chuyên viên Quản lý Tài khoản của bạn. Đối với các báo cáo từ trang xuất dữ liệu, đại lý và nhà quảng cáo có định mức riêng.
* **Mạng quảng cáo**: Báo cáo do mạng quảng cáo tạo không được tính vào định mức của nhà quảng cáo.
* **Ngày**: Định mức theo ngày bắt đầu từ 00:00 UTC

<div id="aggregated-and-analytics-reports" />

### Báo cáo hợp nhất và phân tích

| Công cụ phân phối dữ liệu | Định mức |
| --- | --- |
| Hợp nhất API Pull | <ul><li>Tối đa 2 ngày trong phạm vi ngày:<ul><li>Tối đa 1 lệnh gọi/phút cho mỗi ứng dụng trên một báo cáo</li></ul></li><li>Phạm vi trên 3 ngày; lệnh gọi bị giới hạn như sau:<ul><li>Tối đa 120 lệnh gọi/ngày/tài khoản</li><li>24 lệnh gọi/ngày/ứng dụng</li></ul></li></ul> |
| Trang dữ liệu xuất hợp nhất | Không giới hạn |
| API chính | Không giới hạn |
| API Nhóm người | 60 lệnh gọi/phút/tài khoản |
| Báo cáo hợp nhất của SKAN | 10 lệnh gọi/phút/tài khoản |

<div id="raw-data" />

### Dữ liệu thô

* Một định mức riêng áp dụng cho từng công cụ báo cáo: API Pull và trang xuất dữ liệu thô.
* Đối với API Pull, các báo cáo do đại lý tạo được tính vào định mức của nhà quảng cáo. Đối với các báo cáo từ trang xuất dữ liệu, đại lý và nhà quảng cáo có định mức riêng.
* Định mức của API Pull được áp dụng theo:
  * Báo cáo
  * Ngày
  * Cấp ứng dụng
  * Cấp tài khoản
* Đối với các nhà quảng cáo, định mức phụ thuộc vào gói đăng ký AppsFlyer của bạn. **Lưu ý**: Định mức cũng áp dụng cho các báo cáo yêu cầu gói đăng ký trả phí.
* Các báo cáo do đại lý tạo có thể được tính vào định mức của nhà quảng cáo.
* Định mức hàng ngày của mạng quảng cáo như được thể hiện trong bảng sau.

Để cho dễ hiểu, hãy xem Câu hỏi thường gặp ở cuối các bảng.

<div id="ad-network-postback-reports-daily-quota" />

#### Định mức hàng ngày về dữ liệu thô của mạng quảng cáo

| Nhóm | Loại báo cáo  <br />(mỗi loại báo cáo có một định mức riêng) | Định mức cấp ứng dụng | Định mức cấp tài khoản |
| --- | --- | --- | --- |
| Phân bổ | <ul><li>Lượt cài đặt tự nhiên</li><li>Các lượt Cài đặt không tự nhiên</li><li>Nhắm lại mục tiêu Chuyển đổi</li><li>Gỡ cài đặt</li><li>Doanh thu quảng cáo được phân bổ</li><li>Doanh thu quảng cáo tự nhiên</li><li>Doanh thu quảng cáo nhắm mục tiêu lại</li></ul> | 24 | Không áp dụng |
| Sự kiện trong Ứng dụng | <ul><li>Lượt cài đặt tự nhiên</li><li>Các lượt Cài đặt không tự nhiên</li><li>Nhắm lại mục tiêu Chuyển đổi</li><li>Gỡ cài đặt</li></ul> | 12 | Không áp dụng |

<div id="faq" />

#### **Câu hỏi thường gặp**

* Hỏi: Đối với một ứng dụng cụ thể, tôi có thể tạo 24 báo cáo về lượt cài đặt tự nhiên bằng API Pull và 24 báo cáo khác thông qua trang xuất dữ liệu thô được không?  
  Đáp: Có thể. Định mức cho mỗi công cụ báo cáo là riêng biệt.
* Hỏi: Đối với một ứng dụng cụ thể, tôi có thể tạo 24 báo cáo về lượt cài đặt tự nhiên, 24 báo cáo về lượt cài đặt không tự nhiên và 24 báo cáo về lượt chuyển đổi nhắm mục tiêu lại thông qua trang xuất dữ liệu thô không?  
  Đáp: Có thể. Định mức cho mỗi loại báo cáo là riêng biệt.
* Hỏi: Tôi có 25 ứng dụng trong tài khoản của mình. Tôi có thể tạo 10 báo cáo về lượt cài đặt tự nhiên cho mỗi ứng dụng không?  
  Đáp: Không thể. Điều này dẫn đến tổng cộng có 250 báo cáo, vượt quá định mức cấp tài khoản là 120 báo cáo.

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/data-availability-windows">Khung thời gian dữ liệu khả dụng</Anchor>

<div data-zendesk-anchors="rate-limits-for-reports=gi%E1%BB%9Bi-h%E1%BA%A1n-l%C6%B0u-l%C6%B0%E1%BB%A3ng-cho-c%C3%A1c-b%C3%A1o-c%C3%A1o h_01H9JNZFPSVXPKMEVR1ZR6PSYG=gi%E1%BB%9Bi-h%E1%BA%A1n-l%C6%B0u-l%C6%B0%E1%BB%A3ng-cho-c%C3%A1c-b%C3%A1o-c%C3%A1o aggregated-and-analytics-reports=b%C3%A1o-c%C3%A1o-h%E1%BB%A3p-nh%E1%BA%A5t-v%C3%A0-ph%C3%A2n-t%C3%ADch h_01H9JNZFPS62A5CFWSXVPN8XM5=b%C3%A1o-c%C3%A1o-h%E1%BB%A3p-nh%E1%BA%A5t-v%C3%A0-ph%C3%A2n-t%C3%ADch raw-data=d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 h_01H9JNZFPSPYWBB2MCZV2R2KX1=d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 ad-network-raw-data-daily-quota=%C4%91%E1%BB%8Bnh-m%E1%BB%A9c-h%C3%A0ng-ng%C3%A0y-v%E1%BB%81-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-c%E1%BB%A7a-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o h_01H9JNZFPSYXZNW81BZTRDS576=%C4%91%E1%BB%8Bnh-m%E1%BB%A9c-h%C3%A0ng-ng%C3%A0y-v%E1%BB%81-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-c%E1%BB%A7a-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o faq=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p h_01H9JNZFPT76RAV8JBTY2K75V4=c%C3%A2u-h%E1%BB%8Fi-th%C6%B0%E1%BB%9Dng-g%E1%BA%B7p h_01HE7SW3VWRNVY1WFB4YCSAVY6=xem-th%C3%AAm" />
