---
title: Báo cáo dữ liệu thô SKAN
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T20:54:55Z'
  edited_at: '2023-11-28T15:43:44Z'
  id: 360014261518
  locale: vi
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/vi/articles/360014261518
---
> **Tổng quan:** Báo cáo dữ liệu thô SKAN chứa dữ liệu cấp hàng được tạo sau khi dịch và giải mã đăng lại mà AppsFlyer nhận được từ iOS, cũng như các lượt đăng lại SKAN thô. Dữ liệu có sẵn thông qua <Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers">Data Locker</Anchor> và <Anchor target="_blank" href="/marketers/vi/docs/push-api-streaming-raw-data">API Push</Anchor>. Nếu gói đăng ký của bạn gồm dữ liệu thô thì không cần đăng ký Data Locker.

<div id="skan-raw-data-reports" />

## Báo cáo dữ liệu thô SKAN

Nguyên tắc: 

* **Dữ liệu được cung cấp bởi:**
  * **Data Locker**
    * **Lưu ý**! Có sẵn cho các tài khoản có đăng ký dữ liệu thô. Nghĩa là, không cần đăng ký Data Locker. Nếu bạn hiện không sử dụng Data Locker, người dùng quản trị phải định cấu hình Data Locker và bật báo cáo SKAN. Để thực hiện, đi đến **Integration** > **Data Locker**. Chọn các báo cáo SKAN.
    * **Tần suất cập nhật dữ liệu**: Hàng ngày. Dữ liệu được chứa trong thư mục h=23 kể từ ngày AppsFlyer nhận được đăng lại. Ví dụ: Nếu được nhận vào thứ Hai, thì lượt đăng lại sẽ được xử lý sau khi ngày đó kết thúc. Quá trình xử lý sẽ hoàn tất trước 12:00 UTC ngày thứ Ba, dữ liệu được ghi vào thư mục h=23 thứ Hai.
  * **API Đẩy**
    * Tính cập nhật của dữ liệu: Xem <Anchor target="_blank" href="/marketers/vi/docs/push-api-streaming-raw-data">API Push để lấy dữ liệu SKAN</Anchor>.
* **Ngày cài đặt**: Được AppsFlyer tính từ thời gian có bài đăng lại như sau:
  * Nếu bài đăng lại là SKAN V4 thì công thức ngày cài đặt là: Ngày cài đặt = thời gian có bài đăng lại - [độ dài khung thời gian tích lũy] - [độ trễ đăng lại trung bình].
    * Đăng lại 1: ngày cài đặt = thời gian có bài đăng lại - 48h - 36h
    * Đăng lại 2: ngày cài đặt = thời gian có bài đăng lại - 168h - 84h
    * Đăng lại 3: ngày cài đặt = thời gian có bài đăng lại - 840h - 84h
  * Nếu bài đăng lại là SKAN V3 thì công thức ngày cài đặt là: Ngày cài đặt = thời gian có bài đăng lại - 36 giờ - [phạm vi hoạt động lần cuối trung bình]. 
    * [Phạm vi hoạt động lần cuối trung bình] mặc định là 12 giờ.
    * Đối với giá trị chuyển đổi là 0, phạm vi hoạt động lần cuối trung bình được đặt thành 0.
  * Google tự ước tính thời gian cài đặt và AppsFlyer sử dụng thời gian cài đặt đó. **Lưu ý**: Có thể mất tới 13 ngày để Google báo cáo số lượt cài đặt. <Anchor target="_blank" href="/marketers/vi/docs/get-skan-postback-data-from-google-ads#nhận-dữ-liệu-đăng-lại-skan-từ-google-ads">Tìm hiểu thêm</Anchor>

Các loại báo cáo có sẵn là:

* **Đăng lại của thiết bị**: 1 đăng lại thiết bị cho mỗi lượt cài đặt hoặc tải xuống lại nhận được từ thiết bị iOS.
* **Dữ liệu thô SKAN**:
  * AppsFlyer giải mã và chuyển lượt đăng lại của thiết bị thành bản ghi dữ liệu thô.
  * Mỗi lượt đăng lại sẽ tạo ra một bản ghi cài đặt hoặc tải xuống lại và các bản ghi sự kiện trong ứng dụng.
  * Số lượng bản ghi sự kiện trong ứng dụng tùy thuộc vào giá trị chuyển đổi (CV) như sau:
    * CV = 0, blank hoặc null: Không có bản ghi trong ứng dụng nào được tạo.
    * Phạm vi CV:
      * 1-63: Đối với giá trị mịn của khung thời gian 1 SKAN 3 và SKAN 4, đây là số lượng bản ghi trong ứng dụng, tùy thuộc vào cài đặt đo lường của bạn.
      * Thấp, trung bình hoặc cao: Đối với giá trị thô SKAN 4, đây là số lượng bản ghi trong ứng dụng, tùy thuộc vào cài đặt đo lường của bạn.

**Tại sao có một số trường trống?** Điều này phát sinh là vì bất kỳ lý do nào sau đây:

* Các trường bổ sung không bắt buộc như campaign\_name, ad\_network\_campaign\_id, ip mà mạng quảng cáo không cung cấp.
* Apple đã giữ lại dữ liệu do chính sách ngưỡng áp dụng của Apple. Các trường như source\_app\_id, skad\_campaign\_id, skad\_conversion\_value.

<div id="decoded-event::5dac9cbb" />

<div id="decoded-event::b8f2b4a4" />

<div id="decoded-event::5c7e459f" />

<div id="decoded-event" />

<div id="postback::315d5a62" />

<div id="postback" />

<div id="skan-raw-data-report-format-and-content" />

## Định dạng và nội dung báo cáo dữ liệu thô SKAN

<div id="raw-data-report-types" />

<Accordion title="Các loại báo cáo dữ liệu thô">

<Table>
  <thead>
    <tr>
      <th>
        Loại báo cáo
      </th>
      <th>
        Tên báo cáo
      </th>
      <th>
        Mô tả
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Đăng lại
      </td>
      <td>
        Đăng lại
      </td>
      <td>
        Lượt đăng lại được iOS gửi tới mạng quảng cáo. Bài đăng lại, sau khi được mạng quảng cáo làm phong phú, sẽ được chuyển tiếp đến AppsFlyer. [Tải xuống ví dụ đăng lại](https://docs.google.com/spreadsheets/d/e/2PACX-1vRfFFmj1YV1c73Wbar2VOiKWml6VmsyFvQuydXTPUOO4zXVKmwtw6nup9vKNtNwou2z8IqNpcF4yP6c/pub?gid=1225544365&single=true&output=csv) (CSV).

        Lưu ý: Đăng lại không được đưa vào khi did\_win=false.

        **Tên chủ đề trong Data Locker**: skad\_postbacks
      </td>
    </tr>
    <tr>
      <td>
        Đăng lại
      </td>
      <td>
        Bản sao đăng lại (trực tiếp từ Apple)
      </td>
      <td>
        Đăng lại được iOS gửi trực tiếp tới AppsFlyer.

        Có sẵn bắt đầu từ iOS 15 trở lên và yêu cầu nhà quảng cáo định cấu hình ứng dụng để <Anchor target="_blank" href="/marketers/vi/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">gửi bài đăng lại thành công</Anchor> tới AppsFlyer. [Tải xuống ví dụ bản sao đăng lại](https://docs.google.com/spreadsheets/d/e/2PACX-1vSu0c3gYoIHe2k6_M3cngSFzc-txQvEN38X7Ig7qhXYPg8uBUzyyPqlSwDMugvZS_tUrFjtY8AGYKrh/pub?gid=1225544365&single=true&output=csv) (CSV).

        Lưu ý: Chủ đề này chỉ chứa các bài đăng lại thành công.

        **Tên chủ đề trong Data Locker**: skad\_postbacks\_copy
      </td>
    </tr>
    <tr>
      <td>
        Sự kiện được giải mã
      </td>
      <td>
        Lượt cài đặt
      </td>
      <td>
        **Lượt cài đặt ứng dụng lần đầu**

        SKAN đã báo cáo *reddownload=false*. Có nghĩa rằng đây là lần đầu tiên người dùng, được đại diện bởi ID Apple, tải xuống ứng dụng.  
        [Tải xuống ví dụ lượt cài đặt](https://docs.google.com/spreadsheets/d/e/2PACX-1vS4rNJAio8Ub2cffUEiYhzdavVfXaJAD6OpjhRBjVpGQsAlibOWCkZpfLl29n1OCDBZ2eToO4_gOvbl/pub?gid=1472391837&single=true&output=csv) (CSV).

        **Tên chủ đề trong Data Locker**: skad\_installs
      </td>
    </tr>
    <tr>
      <td>
        Sự kiện được giải mã
      </td>
      <td>
        Tải lại
      </td>
      <td>
        **Lượt cài đặt ứng dụng không phải là lượt cài đặt lần đầu**

        SKAN đã báo cáo *reddownload=true*. Có nghĩa rằng đây không phải là lần đầu tiên người dùng, được đại diện bởi ID Apple, tải xuống ứng dụng. Báo cáo này có cấu trúc tương tự như lượt cài đặt.

        **Tên chủ đề trong Data Locker**: skad\_redownloads
      </td>
    </tr>
    <tr>
      <td>
        Sự kiện được giải mã
      </td>
      <td>
        Sự kiện trong ứng dụng
      </td>
      <td>
        **Sự kiện trong ứng dụng**

        Kể từ ngày 21 tháng 7 năm 2021, sẽ có những thay đổi về cách chúng tôi cung cấp dữ liệu thô về sự kiện trong ứng dụng như được nêu chi tiết trong bảng.

        Số lượng bản ghi sự kiện trong ứng dụng tùy thuộc vào cài đặt đo lường của bạn.

        [Tải xuống ví dụ về sự kiện trong ứng dụng](https://docs.google.com/spreadsheets/d/e/2PACX-1vRwhxOmZwTkOr9uNFN0d4Rk2jFpipONoB8KzIZI5Tw12IvoLirj07QUdI9RJoL9rZYFSN1PvT-W6vP0/pub?gid=1454741057&single=true&output=csv) (CSV).

        **Tên chủ đề trong Data Locker**: skad\_inapps

        Hợp lệ đối với các bài đăng lại trên iOS nhận được kể từ ngày 21 tháng 7 năm 2021:

        | Kiểu đo lường | Mô tả |
        | --- | --- |
        | Doanh thu | * Doanh thu của một người dùng nhất định. Nếu doanh thu > 0, bản ghi chứa các trường skad\_revenue và event\_name.<br />* Các trường min\_revenue và max\_revenue được điền với các giá trị phạm vi chuyển đổi tùy chỉnh của bạn. |
        | Chuyển đổi trong ứng dụng và sự kiện kênh | * Bản ghi cho mỗi sự kiện chuyển đổi duy nhất được thực hiện. Trường event\_name được điền tương ứng. Nếu không có sự kiện nào được thực hiện thì sẽ không có bản ghi.<br />* Sự kiện chuyển đổi có min\_event\_counter = 0 và max\_event\_counter = 1. |
        | Tương tác trong ứng dụng | Để xác định số lần người dùng đã thực hiện một sự kiện trong ứng dụng nhất định, hãy sử dụng công thức`[làm tròn (min_event_counter + max_event_counter) / 2]` |

        Hợp lệ đối với các bài đăng lại trên iOS nhận được cho đến ngày 20 tháng 7 năm 2021:

        | Kiểu đo lường | Số bản ghi | Mô tả |
        | --- | --- | --- |
        | Doanh thu | 0-1 | Nếu doanh thu > 0, bản ghi chứa các trường skad\_revenue và event\_name. |
        | Lượt chuyển đổi | 0-6 | Bản ghi cho mỗi sự kiện chuyển đổi duy nhất được thực hiện. Trường event\_name được điền tương ứng. Nếu không có sự kiện nào được thực hiện thì sẽ không có bản ghi. |
        | Tương tác | 0-63 | Số bản ghi biểu thị số lần người dùng thực hiện sự kiện tương tác. Nếu người dùng không tương tác thì sẽ không có bản ghi tương tác. |
        | Tùy chỉnh | 0-không giới hạn | Theo lược đồ chuyển đổi tùy chỉnh của bạn. |
      </td>
    </tr>
    <tr>
      <td>
        Sự kiện được giải mã
      </td>
      <td>
        Phương diện quảng cáo SRN
      </td>
      <td>
        * Báo cáo chứa các sự kiện của Meta ads với chiến dịch, bộ quảng cáo và mức độ chi tiết của quảng cáo. Mỗi dòng trong báo cáo có thể là một sự kiện cài đặt hoặc sự kiện trong ứng dụng.
        * Bộ quảng cáo và mức độ chi tiết của quảng cáo không được đưa vào lượt đăng lại SKAN từ Meta ads. Dữ liệu này là duy nhất cho báo cáo này và không hiển thị trong bảng điều khiển SKAN, API Hiệu suất và các báo cáo SKAN Data Locker khác.
        * Báo cáo không có lược đồ. Các tùy chọn lựa chọn trường Data Locker không được áp dụng.
        * Phương pháp hay nhất: Không kết hợp hoặc so sánh dữ liệu từ báo cáo này với các báo cáo SKAN khác vì có thể có sự khác biệt giữa báo cáo này sử dụng dữ liệu được giải mã bởi SRN và các báo cáo khác sử dụng dữ liệu được giải mã bởi AppsFlyer. Những khác biệt này có thể là do sự khác biệt về múi giờ, sự khác biệt về lược đồ SRN hoặc sự kiện trong ứng dụng được ánh xạ không chính xác đến CV trong quá trình tích hợp SRN.
        * <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTZjIpqZJxHY9WpIdf9OeDCVQYzM_fLmrpB1oAt3S-MbJTKueOJODwwl6Pz3M0SCAbCFIdMlshOayrw/pub?output=xlsx">Tải xuống ví dụ phương diện quảng cáo SRN</Anchor> (CSV).

        **Tên chủ đề trong Data Locker**: skad\_srn\_advertising\_dimensions
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-field-format-types" />

<Accordion title="Các loại định dạng trường dữ liệu thô">

<div id="field-formats" />

#### Định dạng trường

| Tên định dạng | Mô tả |
| --- | --- |
| Chuỗi [n] | Độ dài tối đa của chuỗi. Chúng tôi thường không thực thi các giới hạn độ dài trường khi nhận dữ liệu nhưng về sau dữ liệu có thể bị cắt ngắn. |
| Chuỗi thời gian | Chuỗi có định dạng `yyyy-mm-dd hh:mm:ss`. Ví dụ, `2019-09-17 00:09:25` |
| Enum [n] | Các trường Enum chỉ có thể chứa các giá trị cụ thể. Ví dụ, Tiền tệ chi phí có 3 ký tự và chỉ có thể chứa mã tiền tệ như được chỉ định. |
| Nhãn thời gian | Nhãn thời gian UNIX 10 chữ số. Ví dụ:<br /><br />Ngày 4 tháng 8 năm 2020, 07:25 UTC dịch thành `"timestamp": "1596525944"` |
| Boolean | Giá trị của trường có thể là `TRUE` hoặc `FALSE` |
| Số nguyên | Số nguyên |
| Float | Số thực dấu phẩy động có thể có dấu thập phân và các giá trị sau dấu thập phân. |

</Accordion>

<div id="fields-available-in-postback-and-postback-copy-reports" />

<Accordion title="Các trường có sẵn trong báo cáo đăng lại và bản sao đăng lại">

<table><thead><tr><th>Tên trường</th><th>Nguồn hoặc phiên bản bắt đầu SKAN iOS</th><th>Mô tả</th><th>Định dạng</th><th>Có sẵn trong bản sao đăng lại </th></tr></thead><tbody><tr><td><p>ad_network_campaign_id</p></td><td>Mạng quảng cáo</td><td>ID chiến dịch được mạng quảng cáo báo cáo cho AppsFlyer</td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>ad_network_campaign</p><p>_name</p></td><td>Mạng quảng cáo</td><td><p>Tên chiến dịch được mạng quảng cáo báo cáo cho AppsFlyer.</p></td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>ad_network_timestamp</p></td><td>Mạng quảng cáo</td><td><p>Thời gian mạng quảng cáo nhận được bài đăng lại.</p><p>Trong trường hợp Google Ads, thời gian được lấy từ thời gian nhấp chuột cuối cùng do Google báo cáo.</p></td><td>Nhãn thời gian</td><td>Không</td></tr><tr><td><p>app_id</p></td><td>AppsFlyer</td><td>ID ứng dụng (ứng dụng của nhà quảng cáo) có ID tiền tố.</td><td>Chuỗi</td><td>Có</td></tr><tr><td><p>city</p></td><td>AppsFlyer</td><td>Bắt đầu từ ngày 30 tháng 8 năm 2021, giá trị luôn là null </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>country_code</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td>dma</td><td> </td><td>Bắt đầu từ ngày 30 tháng 8 năm 2021, giá trị luôn là null </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>postal_code</p></td><td> </td><td>Bắt đầu từ ngày 30 tháng 8 năm 2021, giá trị luôn là null  </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>region</p></td><td>AppsFlyer</td><td>Theo country_code được báo cáo</td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>skad_ad_network_id</p></td><td>1.0 </td><td><p>Một số SRN không chia sẻ ID của họ, và trường này để trống. Ví dụ, Twitter. </p></td><td>Chuỗi</td><td><p>Có </p></td></tr><tr><td><p>skad_attribution_signature</p></td><td>1.0</td><td> </td><td>Chuỗi</td><td>Có</td></tr><tr><td>skad_campaign_id</td><td>1.0</td><td>ID Chiến dịch được sử dụng để đăng quảng cáo. Phạm vi 0-100</td><td>Chuỗi</td><td>Có</td></tr><tr><td>skad_conversion_value</td><td>2.0 </td><td><p>Giá trị chuyển đổi do iOS báo cáo. Phạm vi 0-63.</p><p>Nếu là null thì iOS sẽ không điền vào trường này\*\* </p></td><td>Số nguyên</td><td>Có</td></tr><tr><td>skad_redownload</td><td>2.0</td><td>Nếu là true, ứng dụng đã được tải xuống lại</td><td><p>Boolean</p></td><td><p>Có</p></td></tr><tr><td>skad_source_app_id</td><td>2.0</td><td><p>ID trang web. Ứng dụng đăng quảng cáo. Trường này giống hệt với source_app_id.</p><p>Trường có được điền hay không phụ thuộc vào ngưỡng quyền riêng tư\*\*</p></td><td>Chuỗi</td><td>Có</td></tr><tr><td>skad_transaction_id</td><td>1.0</td><td> </td><td>Chuỗi</td><td>Có</td></tr><tr><td>skad_version</td><td>2.0</td><td> </td><td>Chuỗi</td><td>Có</td></tr><tr><td>timestamp</td><td>Mạng quảng cáo</td><td><p>Thời gian AppsFlyer nhận được đăng lại SKAN. </p></td><td>Chuỗi thời gian</td><td>Có</td></tr><tr><td>ad_network_name</td><td>Mạng quảng cáo</td><td><p>Tên mạng quảng cáo được mạng quảng cáo báo cáo cho AppsFlyer. </p><ul><li>Nếu trường này trống, thì mạng quảng cáo đã không (không thể) nhập vào trường đó.</li><li>Bạn có thể phân giải tên mạng quảng cáo bằng cách sử dụng skad_ad_network_id. Sử dụng <a href="./skan-integrated-partners-list#zd-apple-skadnetwork-ids-of-ad-networks" target="_blank">bảng</a> này để thực hiện như vậy. </li></ul></td><td>Chuỗi</td><td>Không</td></tr><tr><td>ip</td><td> </td><td><p>Địa chỉ IP trong thông báo HTTP của thiết bị iOS gửi bài đăng lại.</p><p>Trường này sẽ được nhập nếu mạng quảng cáo cung cấp địa chỉ cho chúng tôi.</p><p>Lưu ý! SDK không liên quan đến việc lấy địa chỉ.</p></td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>skad_app_id</p></td><td>1.0</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>source_app_id</p></td><td>AppsFlyer</td><td>ID Trang web. Ứng dụng đăng quảng cáo. Trường này giống với skad_source_app_id</td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>ad_network_adset_id</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>ad_network_adset_name</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>ad_network_ad_name</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>ad_network_ad_id</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>did_win</p></td><td>3.0 (iOS 14.6)</td><td><p>Được sử dụng để phân biệt giữa các chiến dịch <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">đóng góp cho hoặc được phân bổ</a> bằng lượt cài đặt. </p><ul><li>Nếu là true, thì chiến dịch được phân bổ vì đã mang đến lượt cài đặt.</li><li>Nếu là false, chiến dịch được công nhận là góp phần vào lượt cài đặt nhưng chiến dịch này không được đưa vào bất kỳ bảng điều khiển hoặc báo cáo SKAN nào.</li><li>Nếu là null thì iOS sẽ không điền vào trường này do <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">dùng phiên bản iOS hoặc SKAdNetwork đã cũ</a>.</li></ul></td><td>Boolean</td><td>Có</td></tr><tr><td><p>fidelity_type</p></td><td>2.2 (iOS 14.5)</td><td><p><span>Phân biệt giữa các tùy chọn <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">trình bày quảng cáo</a> ảnh hưởng đến phân bổ. Được biểu thị bằng cách sử dụng các giá trị 0 và 1 như sau: </span></p><ul><li><span>Quảng cáo xem hết (0)</span></li><li><span>Quảng cáo do StoreKit hiển thị (1)</span></li></ul><p>Bỏ qua giá trị trường nếu phiên bản SKAN là phiên bản trước 2.2</p></td><td>Số nguyên</td><td>Có</td></tr><tr><td><p>ad_network_source_app_id</p></td><td>Mạng quảng cáo</td><td><span>ID ứng dụng của nhà phát hành được mạng quảng cáo báo cáo. Sử dụng để giúp đối chiếu chi phí do mạng quảng cáo báo cáo. Ứng dụng của nhà phát hành cung cấp cơ sở cho dữ liệu này. </span></td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>ad_network_channel</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>af_prt</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p><span>skad_postback_sequence_index</span></p></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Giá trị thể hiện khung thời gian SKAN, là <code>0</code>, <code>1</code> hoặc <code>2</code>. </span></li><li><span>Đối với SKAN 3, giá trị sẽ là<code>0</code></span></li></ul></td><td><span>Số nguyên</span></td><td><span>Có</span></td></tr><tr><td><span>skad_coarse_conversion_value</span></td><td><p><span>4.0 (iOS 16.2)</span></p></td><td><ul><li><span>Giá trị có thể là<code>thấp</code>,<code>trung bình</code> hoặc<code>cao</code>. </span></li><li><span>Đối với SKAN 3, giá trị sẽ là<code>null</code>.</span></li></ul></td><td><span>Chuỗi</span></td><td><span>Có</span></td></tr><tr><td><span>skad_source_identifier</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Giá trị có thể lên đến 4 chữ số. </span></li><li><span>Đối với SKAN 3, giá trị sẽ là<code>null</code>. </span></li></ul></td><td><span>Chuỗi</span></td><td><span>Có</span></td></tr><tr><td><span>skad_source_domain</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Giá trị thể hiện nguồn quảng cáo trên web có thể phân bổ. </span></li><li><span>Đối với SKAN 3, giá trị sẽ là<code>null</code>.</span></li></ul></td><td><span>Chuỗi</span></td><td><span>Có</span></td></tr><tr><td><span>ad_network_creative</span></td><td><span>Mạng quảng cáo</span></td><td><ul><li><span>Giá trị dựa trên việc làm phong phú dữ liệu nhận được từ mạng quảng cáo. </span></li><li><span>Đối với SKAN 3, giá trị sẽ là<code>null</code>.</span></li></ul></td><td><span>Chuỗi</span></td><td><span>Không</span></td></tr></tbody><tfoot><tr><td colspan="4"><p>\*\* Apple xác định xem trường này có được điền bằng cơ chế ngưỡng quyền riêng tư hay không </p></td><td></td></tr></tfoot></table>

</Accordion>

<div id="fields-available-in-decoded-event-reports" />

<Accordion title="Các trường có sẵn trong báo cáo sự kiện được giải mã">

<table><thead><tr><th>Tên trường</th><th>Nguồn</th><th>Mô tả</th><th>Định dạng</th><th>Được đưa vào báo cáo phương diện quảng cáo SRN</th></tr></thead><tbody><tr><td>ad_network_campaign_id</td><td>Mạng quảng cáo</td><td>ID chiến dịch được mạng quảng cáo báo cáo cho AppsFlyer</td><td>Chuỗi</td><td>Có</td></tr><tr><td>ad_network_campaign<br/>_name</td><td>Mạng quảng cáo</td><td>Tên chiến dịch được mạng quảng cáo báo cáo cho AppsFlyer</td><td>Chuỗi</td><td>Có</td></tr><tr><td>ad_network_timestamp</td><td>Mạng quảng cáo</td><td><p>Thời gian mạng quảng cáo nhận được bài đăng lại</p><p>Trong trường hợp của Google Ads, trường này không được điền. </p></td><td><p>Nhãn thời gian</p><p>(chuỗi thời gian cho báo cáo phương diện quảng cáo SRN)</p></td><td>Có</td></tr><tr><td>app_id</td><td>iOS</td><td>ID ứng dụng (ứng dụng của nhà quảng cáo)</td><td>Chuỗi</td><td>Có</td></tr><tr><td>city</td><td> </td><td>Bắt đầu từ ngày 30 tháng 8 năm 2021, giá trị luôn là null </td><td>Chuỗi</td><td>Không</td></tr><tr><td>country_code</td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td>dma</td><td> </td><td>Bắt đầu từ ngày 30 tháng 8 năm 2021, giá trị luôn là null </td><td>Chuỗi</td><td>Không</td></tr><tr><td>event_name</td><td>AppsFlyer</td><td><p>Tên sự kiện trong ứng dụng như được định cấu hình trong AppsFlyer.</p><p>Đối với báo cáo ___SRN, đây là tên sự kiện trong ứng dụng như được cấu hình trong Meta ads.</p></td><td>Chuỗi</td><td>Có</td></tr><tr><td>event_uuid</td><td>AppsFlyer</td><td>Một mã định danh ngẫu nhiên duy nhất cho phép các đối tác xác định các bài đăng lại trùng lặp</td><td>Chuỗi</td><td>Không</td></tr><tr><td>install_date</td><td>iOS</td><td>Ước tính bởi AppsFlyer dựa trên thời gian đến của bài đăng lại.</td><td>Chuỗi thời gian</td><td>Không</td></tr><tr><td>install_type</td><td>iOS</td><td>Lượt cài đặt mới</td><td>Chuỗi</td><td>Không</td></tr><tr><td>ip</td><td>iOS</td><td><p>Địa chỉ IP trong thông báo HTTP của thiết bị iOS gửi bài đăng lại.</p><p>Trường này sẽ được nhập nếu mạng quảng cáo cung cấp địa chỉ cho chúng tôi.</p><p>Lưu ý! SDK không liên quan đến việc lấy địa chỉ. </p></td><td>Chuỗi</td><td>Không</td></tr><tr><td>media_source</td><td>iOS</td><td>Mạng quảng cáo được phân bổ bằng cách sử dụng tên mạng AppsFlyer</td><td>Chuỗi</td><td>Có</td></tr><tr><td>postal_code</td><td> </td><td>Bắt đầu từ ngày 30 tháng 8 năm 2021, giá trị luôn là null </td><td>Chuỗi</td><td>Không</td></tr><tr><td>region</td><td>AppsFlyer</td><td>Được xác định theo country_code</td><td>Chuỗi</td><td>Không</td></tr><tr><td>skad_ad_network_id</td><td>iOS</td><td>ID của mạng quảng cáo đã được gửi bài đăng lại</td><td>Chuỗi</td><td>Không</td></tr><tr><td>skad_ambiguous_event</td><td>AppsFlyer</td><td>Nếu là true, đăng lại trên iOS đã được nhận trong 72 giờ đầu tiên sau khi nhà quảng cáo thay đổi cài đặt SKAN trong bảng điều khiển. Do SKAN sử dụng nhiều bộ đếm thời gian khác nhau, AppsFlyer không thể ánh xạ sự kiện một cách chính xác.</td><td>Boolean</td><td>Không</td></tr><tr><td>skad_attribution_signature</td><td>iOS</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td>skad_campaign_id</td><td>iOS</td><td>ID Chiến dịch được sử dụng để đăng quảng cáo. Phạm vi 0-100</td><td>Số nguyên</td><td>Không</td></tr><tr><td>skad_conversion_value</td><td>iOS</td><td><p>Giá trị chuyển đổi do iOS báo cáo. Phạm vi 0-63.</p><p>Nếu là null thì iOS sẽ không nhập vào trường này\*\*</p></td><td>Số nguyên</td><td>Không</td></tr><tr><td>skad_mode</td><td>AppsFlyer</td><td><p>Chế độ đo lường chuyển đổi được sử dụng để giải mã đăng lại của iOS. Tùy chọn:</p><ul><li>custom_decode</li><li>revenue</li><li>events</li><li>skan4</li><li>custom_encode</li><li>engagement</li></ul></td><td>Chuỗi</td><td>Không</td></tr><tr><td>skad_redownload</td><td>iOS</td><td>Nếu là true, ứng dụng đã được tải xuống lại</td><td>Boolean</td><td>Không</td></tr><tr><td>skad_revenue</td><td>iOS</td><td>Số tiền doanh thu sự kiện tính bằng USD.</td><td>Float</td><td>Không</td></tr><tr><td>skad_source_app_id</td><td>iOS</td><td><p>ID Trang web - ứng dụng đăng quảng cáo.</p><p>Trường có được điền hay không phụ thuộc vào ngưỡng quyền riêng tư\*\*</p></td><td>Chuỗi</td><td>Không</td></tr><tr><td>skad_transaction_id</td><td>iOS</td><td>-</td><td>Chuỗi</td><td>Không</td></tr><tr><td>skad_version</td><td>iOS</td><td>-</td><td>Chuỗi</td><td>Không</td></tr><tr><td>timestamp</td><td>iOS</td><td><p><span>Thời gian AppsFlyer nhận được đăng lại SKAN</span>.</p><p>Đối với Google Ads và Meta ads, đây là lúc AppsFlyer lần lượt lấy dữ liệu từ API Google và Meta ads.</p></td><td><p>Nhãn thời gian</p><p>(chuỗi thời gian cho báo cáo phương diện quảng cáo SRN)</p></td><td>Có</td></tr><tr><td>event_value</td><td>S2S</td><td><p>Giá trị mặc định: null</p><p>Chứa một chuỗi do ứng dụng triển khai giải mã tùy chỉnh đặt.</p><p>Các nhà quảng cáo sử dụng giá trị này trong hệ thống của họ. Còn AppsFlyer thì không sử dụng giá trị đó. </p></td><td>String (JSON)</td><td>Không</td></tr><tr><td><p>ad_network_adset_id</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Có</td></tr><tr><td><p>ad_network_adset_name</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Có</td></tr><tr><td><p>ad_network_ad_name</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Có</td></tr><tr><td><p>ad_network_ad_id</p></td><td>Mạng quảng cáo</td><td></td><td>Chuỗi</td><td>Có</td></tr><tr><td><p>skad_did_win (1)</p></td><td>3.0 (iOS 14.6)</td><td><p>Được sử dụng để phân biệt giữa các chiến dịch <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">đóng góp cho hoặc được phân bổ</a> bằng lượt cài đặt. </p><ul><li>Nếu là true, thì chiến dịch được phân bổ vì đã mang đến lượt cài đặt.</li><li>Nếu là false, chiến dịch được ghi nhận là góp phần mạng đến lượt cài đặt nhưng chiến dịch này không được đưa vào bất kỳ bảng điều khiển hoặc báo cáo SKAN nào.</li><li>Nếu là null thì iOS sẽ không điền vào trường này do <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">dùng phiên bản iOS hoặc SKAdNetwork đã cũ</a>.</li></ul></td><td>Boolean</td><td>Không</td></tr><tr><td><p>skad_fidelity_type (1)</p></td><td>2.2 (iOS 14.5)</td><td><p><span>Phân biệt giữa các tùy chọn <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">trình bày quảng cáo</a> ảnh hưởng đến phân bổ. Được biểu thị bằng cách sử dụng các giá trị 0 và 1 như sau: </span></p><ul><li><span>Quảng cáo xem hết (0)</span></li><li><span>Quảng cáo do StoreKit hiển thị (1)</span></li></ul><p>Bỏ qua giá trị trường nếu phiên bản SKAN là phiên bản trước 2.2</p></td><td>Số nguyên</td><td>Có</td></tr><tr><td><p>ad_network_source_app_id (1)</p></td><td>Mạng quảng cáo</td><td><span>ID ứng dụng của nhà phát hành được báo cáo bởi mạng quảng cáo. Sử dụng để giúp điều hòa chi phí; được báo cáo bởi mạng quảng cáo. Ứng dụng của nhà phát hành cung cấp cơ sở cho dữ liệu này.</span></td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>ad_network_channel (1)</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>af_prt (1)</p></td><td>Mạng quảng cáo</td><td> </td><td>Chuỗi</td><td>Không</td></tr><tr><td><p>min_revenue </p></td><td>AppsFlyer</td><td>Xem lưu ý (4)</td><td>Số thực</td><td>Không</td></tr><tr><td><p>max_revenue </p></td><td>AppsFlyer</td><td>Xem lưu ý (4)</td><td>Số thực</td><td>Không</td></tr><tr><td><p>event_revenue</p></td><td>AppsFlyer</td><td><p>Công thức: [tổng giá trị cho sự kiện cụ thể bằng USD]/[Số lượng sự kiện đã diễn ra trong một ngày cụ thể]</p></td><td>Float</td><td>Có</td></tr><tr><td><p>min_event_counter</p></td><td>AppsFlyer</td><td>Dùng để tính số lần người dùng thực hiện một sự kiện. Xem lưu ý (3)</td><td>Số nguyên</td><td>Không</td></tr><tr><td><p>max_event_counter</p></td><td>AppsFlyer</td><td>Xem ghi chú (3)</td><td>Số nguyên</td><td>Không</td></tr><tr><td><p>min_time_post_install</p></td><td>AppsFlyer</td><td>Xem lưu ý (5)</td><td>Số nguyên</td><td>Không</td></tr><tr><td><p>max_time_post_install</p></td><td>AppsFlyer</td><td>Xem lưu ý (5)</td><td>Số nguyên</td><td>Không</td></tr><tr><td><p>af_attribution_flag</p></td><td>AppsFlyer</td><td><p>Khi cơ chế Nguồn dữ liệu Tin cậy Duy nhất (SSOT) được bật: Nếu là true, thì lượt cài đặt được phân bổ cho cả AppsFlyer và SKAN. Nếu là false, lượt cài đặt không được phân bổ bởi AppsFlyer. Nếu skad_conversion_value là null thì cờ báo là true hoặc false (dựa trên <a href="./skan-modeled-data#null-conversion-values" target="_blank">mô hình</a>).</p></td><td>Boolean</td><td>Không</td></tr><tr><td><p>measurement_window</p></td><td>AppsFlyer</td><td>Thời lượng của khung thời gian hoạt động. Mặc định là 24 giờ. </td><td>Số nguyên</td><td>Không</td></tr><tr><td><p>interval</p></td><td>AppsFlyer</td><td>Khoảng thời gian của khung thời gian hoạt động. </td><td>Số nguyên</td><td>Không</td></tr><tr><td><p>user_agent</p></td><td>AppsFlyer</td><td>Tác nhân người dùng thiết bị</td><td>Chuỗi</td><td>Không</td></tr><tr><td><p><span>skad_postback_sequence_index</span></p></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Giá trị thể hiện khung thời gian SKAN, là <code>0</code>, <code>1</code> hoặc <code>2</code>. </span></li><li><span>Đối với SKAN 3, giá trị sẽ là<code>0</code></span></li></ul></td><td><span>Số nguyên</span></td><td><span>Có</span></td></tr><tr><td><span>skad_coarse_conversion_value</span></td><td><p><span>4.0 (iOS 16.2)</span></p></td><td><ul><li><span>Giá trị có thể là<code>thấp</code>,<code>trung bình</code> hoặc<code>cao</code>. </span></li><li><span>Đối với SKAN 3, giá trị sẽ là<code>null</code>.</span></li></ul></td><td><span>Chuỗi</span></td><td><span>Có</span></td></tr><tr><td><span>skad_source_identifier</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Giá trị có thể lên đến 4 chữ số. </span></li><li><span>Đối với SKAN 3, giá trị sẽ là<code>null</code>. </span></li></ul></td><td><span>Chuỗi</span></td><td><span>Có</span></td></tr><tr><td><span>skad_source_domain</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>Giá trị thể hiện nguồn quảng cáo trên web có thể phân bổ. </span></li><li><span>Đối với SKAN 3, giá trị sẽ là<code>null</code>.</span></li></ul></td><td><span>Chuỗi</span></td><td><span>Có</span></td></tr><tr><td><span>ad_network_creative</span></td><td><span>Mạng quảng cáo</span></td><td><ul><li><span>Giá trị dựa trên việc làm phong phú dữ liệu nhận được từ mạng quảng cáo. </span></li><li><span>Đối với SKAN 3, giá trị sẽ là<code>null</code>.</span></li></ul></td><td><span>Chuỗi</span></td><td><span>Không</span></td></tr></tbody><tfoot><tr><td colspan="4"><p>\*\* Apple xác định xem trường này có được điền bằng cơ chế ngưỡng quyền riêng tư hay không</p><p>(1) Bắt đầu từ ngày 2 tháng 6 năm 2021, trường này sẽ được thêm vào báo cáo nhưng không nhất thiết phải được điền.</p><p>(3) Để xác định số lần người dùng thực hiện một sự kiện trong ứng dụng cụ thể, hãy sử dụng công thức: <code>[làm tròn (min_event_counter + max_event_counter) / 2]</code> . Lưu ý! <mark> Bạn phải làm tròn số nguyên gần nhất.</mark><br/>Ví dụ:<br/>A. Nếu min = 0 và max = 1 thì trung bình là 0,5; làm tròn lên sẽ trả về kết quả là 1.<br/>B. Nếu min = 5 và max = 10 thì trung bình là 7,5; làm tròn lên sẽ trả về kết quả là 8.</p><p>(4) Doanh thu luôn được cung cấp trong trường <code>skad_revenue</code>. Nếu bạn sử dụng<span> SKAN 4 hoặc </span><span><a href="./skan-conversion-studio" target="_blank">chế độ Tùy chỉnh</a></span>, phạm vi bộ chứa được liên kết với sự kiện và được sử dụng để tính skad_revenue sẽ được mô tả bằng min_revenue và max_revenue.</p><p>(5)</p><ul><li>Trong Chuyển đổi tùy chỉnh: AppsFlyer tính thời gian cài đặt là thời gian đến của bài đăng lại - 36 giờ - trung bình (min_time_post_install + max_time_post_install). Tuy nhiên, nếu CV=0 thì trung bình (min_time_post_install + max_time_post_install) được coi là 0. </li><li>Trong Chuyển đổi giải mã: min_time_post_install ít hơn một giờ so với thời gian được đặt trong max_time_post_install, tương đương với <a href="./skan-cv-decode-map-your-cv-to-events#zd-decode-csv-file-specification" target="_blank">hours_from_install</a> do bạn đã đặt trong ánh xạ Chuyển đổi giải mã. </li></ul></td><td></td></tr></tfoot></table>

</Accordion>

<div id="additional-information" />

## Thông tin bổ sung

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Nhận xét |
| --- | --- |
| Truy cập mạng quảng cáo | Các mạng quảng cáo được cung cấp các bài đăng lại |
| Truy cập đại lý | Không có sẵn |
| Tính minh bạch của đại lý | Không áp dụng |
| Múi giờ | UTC |
| Tiền tệ | USD |
| Dữ liệu tự nhiên | Dựa trên dữ liệu sự kiện SDK. Ví dụ, số liệu về lượt cài đặt tự nhiên được tính như sau: Dữ liệu của tất cả các lượt cài đặt do SDK báo cáo trừ số lượt cài đặt không tự nhiên do SKAN báo cáo. |
| Dữ liệu không tự nhiên | Dựa trên các bài đăng lại của SKAN |
| Tính cập nhật của dữ liệu | Hằng ngày. Thời gian SKAN có nghĩa là iOS báo cáo về lượt cài đặt 24-48 giờ sau khi thời hạn đóng. |
| Dữ liệu lịch sử | Giới hạn trong cửa sổ khả dụng của Data Locker. |
| Quyền truy cập tài khoản của người dùng | Có sẵn. Theo quyền tài khoản |

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#reporting-options">Các báo cáo SKAN có sẵn (hướng dẫn giải pháp SKAN)</Anchor>

<div data-zendesk-anchors="skan-raw-data-reports=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-skan 01H8XHATZB2G6YZ9AJNPRZS59Y=b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-skan skan-raw-data-report-format-and-content=%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-v%C3%A0-n%E1%BB%99i-dung-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-skan 01H8XHATZCJQZTZF0Y5P18XMEA=%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-v%C3%A0-n%E1%BB%99i-dung-b%C3%A1o-c%C3%A1o-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4-skan 01H8XHATZCR5BC2P5TSQTMDY5Q=raw-data-report-types 01H8XHATZC0MST5ASGWDGGK2R8=raw-data-field-format-types field-formats=%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-tr%C6%B0%E1%BB%9Dng 01H8XHATZCZMNGK72DDE5HS6E9=%C4%91%E1%BB%8Bnh-d%E1%BA%A1ng-tr%C6%B0%E1%BB%9Dng 01H8XHATZC24DH4AYB2C523JDH=fields-available-in-postback-and-postback-copy-reports 01H8XHATZCNXVG0E3MZ9H68AA1=fields-available-in-decoded-event-reports additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung 01H8XHATZD9D7JBHTFZ095EBD5=th%C3%B4ng-tin-b%E1%BB%95-sung 01H8XHATZDMV0VN4BDTECGF91K=traits-and-limitations h_01HDNYQBVZP0A6SQASGDRFVFGP=xem-th%C3%AAm" />
