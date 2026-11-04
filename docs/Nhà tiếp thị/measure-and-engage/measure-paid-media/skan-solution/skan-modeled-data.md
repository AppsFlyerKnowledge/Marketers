---
title: Dữ liệu theo mô hình SKAN
metadata:
  keywords:
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T12:02:02Z'
  edited_at: '2023-10-26T14:41:21Z'
  id: 7086372479505
  locale: vi
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/vi/articles/7086372479505
---
> **Khái quát**: Mô hình AppsFlyer hợp nhất dữ liệu mà báo cáo SKAdNetwork cơ bản không thể cung cấp.

<div id="overview" />

## Tổng quan

Báo cáo SKAdNetwork (SKAN) có thể bị hạn chế bởi vì:

* SKAN dựa trên các giá trị chuyển đổi (CV) được giới hạn chỉ 6 bit, nghĩa là có thể có 64 giá trị (0-63).
* Apple đôi khi giữ lại CV thực (và trả về dữ liệu "null") để bảo vệ quyền riêng tư của người dùng.
* Dữ liệu chỉ khả dụng trong khung thời gian hoạt động từ 12-72 giờ và không xác định được giá trị vòng đời (LTV) đầy đủ.

Dữ liệu theo mô hình SKAN giải quyết các vấn đề sau:

* AppsFlyer sử dụng máy học, số liệu thống kê Bayesian, dữ liệu do AppsFlyer báo cáo và dữ liệu SKAN để lập mô hình các điểm dữ liệu ẩn.
* Nhà quảng cáo sẽ có được bức tranh toàn cảnh hơn về hiệu suất LTV của ứng dụng và chiến dịch

**Lưu ý**: Khi thay đổi lược đồ giá trị chuyển đổi, bạn phải mất 2 ngày mới có dữ liệu được lập mô hình.

<div id="modeled-data-types-and-availability" />

## Loại dữ liệu được lập mô hình và tính có sẵn

| Loại dữ liệu | Tính khả dụng | Lưu ý |
| --- | --- | --- |
| Giá trị chuyển đổi null | <ul><li>Chế độ xem Nguồn dữ liệu tin cậy duy nhất trên Bảng điều khiển tổng quan</li><li>Bảng điều khiển SKAN</li><li>API báo cáo hiệu suất hợp nhất của SKAN</li><li>API vào ngày đến của đăng lại hợp nhất của SKAN</li></ul> |  |
| LTV doanh thu | Chế độ xem Nguồn dữ liệu tin cậy duy nhất trên Bảng điều khiển tổng quan | Tính năng Lập mô hình LTV doanh thu hiện bị giới hạn chỉ 7 ngày |
| Địa lý | Chế độ xem Nguồn dữ liệu tin cậy duy nhất trên Bảng điều khiển tổng quan |  |

<div id="null-conversion-values" />

<Accordion title="Giá trị chuyển đổi null">

Đôi khi, giá trị chuyển đổi (CV) có giá trị null vì Apple giữ lại CV thực để bảo vệ quyền riêng tư của người dùng. Trong AppsFlyer, một CV null được tính là một lượt cài đặt. Lưu ý:

* Giá trị null và 0 mang ý nghĩa khác nhau:
  * Giá trị 0: Người dùng đã cài đặt ứng dụng nhưng không thực hiện bất kỳ hành động có thể đo lường nào trong khung thời gian hoạt động. Do đó, số liệu là chính xác và không được lập mô hình.
  * Giá trị null: Chúng tôi không biết người dùng đã làm gì; Apple đã giữ lại CV.
* CV null có thể làm sai lệch số liệu hiệu suất của bạn. Để khắc phục tình trạng sai lệch và cung cấp thước đo chính xác hơn về hiệu suất của ứng dụng, các giá trị chuyển đổi null được lập mô hình thành các giá trị chuyển đổi từ 0-63.

Giá trị chuyển đổi được lập mô hình:

* Sử dụng phân phối lượt cài đặt SKAN với các giá trị chuyển đổi để lập mô hình lượt cài đặt null. Thuật toán được dùng để lập mô hình dữ liệu là thuật toán động và có tính đến một vài biến số. Xem ví dụ dưới đây về cách hoạt động:
  * Có 100 lượt cài đặt, 60 lượt cài đặt null, 10 lượt cài đặt có CV = 1, 5 lượt cài đặt có CV = 3 và 25 lượt cài đặt có CV = 5.
  * Điều này có nghĩa là trong số 40 lượt cài đặt có giá trị chuyển đổi, 25% có CV = 1, 12,5% có CV = 3 và 62,5% có CV = 5.
  * 60 lượt cài đặt null có phân phối được lập mô hình như nhau: 15 lượt cài đặt có CV = 1, 7 lượt cài đặt có CV = 3 và 38 lượt cài đặt có CV = 5.
* Nằm trong bảng điều khiển SKAN và số liệu API. Các số liệu ban đầu, không thay đổi, không bao gồm dữ liệu được lập mô hình, sẽ được cung cấp cùng với các số liệu này và được đánh dấu là *chưa được lập mô hình*.
* Sử dụng dữ liệu từ các cấp độ chi tiết sau: Ứng dụng, nguồn truyền thông, chiến dịch và bộ quảng cáo. Nếu không có dữ liệu được lập mô hình sử dụng các cấp độ này, thì giá trị N/A sẽ được hiển thị.

Các số liệu được lập mô hình có sẵn dựa trên giá trị chuyển đổi:

* Doanh thu
* Số lần xảy ra sự kiện
* eCPA
* ARPU
* ROI
* ROAS

</Accordion>

<div id="revenue-ltv" />

<Accordion title="LTV doanh thu">

[![modeled_d7.png](https://files.readme.io/ec175800b52164844c56743a33fe412eef02c3b76975ca572819535bb5e5eff9-12183780248081.png)](https://files.readme.io/ec175800b52164844c56743a33fe412eef02c3b76975ca572819535bb5e5eff9-12183780248081.png)

Bản thân báo cáo SKAN chỉ có thể cung cấp doanh thu dựa trên khung thời gian đo lường SKAN và cấu hình CV cho doanh thu trong Conversion Studio. Tính năng Lập mô hình SKAN có thể lập mô hình doanh thu trong tối đa 7 ngày (168 giờ) sau khi cài đặt.

**Lợi ích**:

Đối với SKAN phiên bản 3 trở về trước, dữ liệu được lập mô hình vượt ngoài khung thời gian hoạt động.

Đối với SKAN phiên bản 4+:

* Tính cập nhật của dữ liệu: LTV doanh thu có sẵn trước khi đăng lại SKAN thứ hai đến (độ trễ đăng lại là từ 24-144 giờ).
* Đo lường nhiều hơn: Bạn có thể sử dụng cấu hình giá trị thô của đăng lại thứ hai và thứ ba cho các số liệu khác, như sự kiện và tỷ lệ giữ lại, đồng thời vẫn nhận được dữ liệu LTV doanh thu bằng cách lập mô hình.
* Làm giàu dữ liệu: Nếu bạn sử dụng đăng lại thứ hai để đo lường doanh thu, thì dữ liệu từ đăng lại sẽ được sử dụng để cải thiện dữ liệu LTV doanh thu được lập mô hình và cung cấp dữ liệu doanh thu ở cấp độ chi tiết lớn hơn 3 cấp độ mà đăng lại cung cấp.

**Những điều cần lưu ý**:

* Số liệu LTV doanh thu hiển thị cho các ứng dụng với cấu hình tổng doanh thu trong SKAN Conversion Studio, đối với doanh thu đến từ các giao dịch mua trong ứng dụng và doanh thu quảng cáo.
* LTV doanh thu yêu cầu dữ liệu doanh thu của ít nhất 14 ngày. Có nghĩa là nếu bạn cấu hình Tổng doanh thu vào ngày 1 tháng 11 năm 2022, thì ngày cài đặt đầu tiên có dữ liệu được lập mô hình là ngày 14 tháng 11 năm 2022. Dữ liệu hiển thị trong 8 ngày sau đó (ngày 22 tháng 11 năm 2022).
* LTV doanh thu (hiện bị giới hạn chỉ 7 ngày) và các số liệu có được khác có sẵn trong bảng điều khiển SSOT (trong các widget, biểu đồ và bảng) vào ngày thứ 8 sau khi cài đặt như sau:
  * Doanh thu D7
  * ARPU D7
  * Lợi nhuận gộp D7
  * ROI D7
  * ROAS D7

</Accordion>

<div id="geo" />

<Accordion title="Địa lý">

Đăng lại SKAN không có trong phương diện địa lý. Do đó, không theo gộp nhóm theo địa lý đối với các dữ liệu SKAN thông qua đăng lại SKAN. Tuy nhiên, AppsFlyer có thể lập mô hình địa lý lượt cài đặt SKAN để cung cấp phương diện địa lý và gộp nhóm đối với dữ liệu SKAN.

Địa lý được lập mô hình:

* Sử dụng các công cụ học máy có tính đến phân phối theo địa lý cho các lượt cài đặt trong chiến dịch được phân bổ thông qua các phương thức khác của AppsFlyer.
* Có sẵn thông qua Phương diện địa lý trong bảng điều khiển SSOT.  
  **Lưu ý**: Nếu gộp nhóm dữ liệu theo Địa lý và phương thức phân bổ, bạn có thể xem dữ liệu cho từng phân chia địa lý giữa mô hình AF và phương thức phân bổ chỉ bằng SKAN. Phương thức phân bổ chỉ bằng SKAN được mô hình hóa.

Những điều cần lưu ý:

* Độ chính xác của mô hình theo địa lý AppsFlyer là xấp xỉ 90%. Nếu địa lý không thể lập mô hình được, lượt cài đặt SKAN được nhóm theo None. None có nghĩa là địa lý không xác định.

</Accordion>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan 01H8TZR38AC6P264CGF4PX4SJ5=t%E1%BB%95ng-quan modeled-data-types-and-availability=lo%E1%BA%A1i-d%E1%BB%AF-li%E1%BB%87u-%C4%91%C6%B0%E1%BB%A3c-l%E1%BA%ADp-m%C3%B4-h%C3%ACnh-v%C3%A0-t%C3%ADnh-c%C3%B3-s%E1%BA%B5n 01H8TZR38A2V9ZSSGKHF3XCX0P=lo%E1%BA%A1i-d%E1%BB%AF-li%E1%BB%87u-%C4%91%C6%B0%E1%BB%A3c-l%E1%BA%ADp-m%C3%B4-h%C3%ACnh-v%C3%A0-t%C3%ADnh-c%C3%B3-s%E1%BA%B5n 01H8TZR38A4RDX42B7J5X9SPMQ=null-conversion-values 01H8TZR38BG9XEM2FTJADJ27VK=revenue-ltv 01H8TZR38BSFVDSQCH915ACSYH=geo" />
