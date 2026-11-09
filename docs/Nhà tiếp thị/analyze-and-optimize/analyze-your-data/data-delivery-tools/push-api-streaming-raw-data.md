---
title: Dữ liệu thô truyền trực tuyến API Push
metadata:
  keywords:
    - Push API
    - Real-time
    - Installation and Conversion
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:19:42Z'
  edited_at: '2023-11-20T08:40:21Z'
  id: 207034356
  locale: vi
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/vi/articles/207034356
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Khái quát:** Truyền trực tuyến các sự kiện phân bổ dữ liệu thô tới các điểm cuối phía máy chủ của bạn.

<Image align="center" alt="6970_Push_API_image.png" src="https://files.readme.io/0bb5747a65a6ca6ed8f55f72f189b92e780649d55b766c5d295f5602745f04f5-4405028260241.png" />

<div id="push-api" />

## API Push

API Push truyền trực tiếp dữ liệu thô được tạo bởi quá trình phân bổ AppsFlyer và phân bổ SKAdNetwork (SKAN) dưới dạng thông báo tới máy chủ của bạn. Bạn có thể chọn loại và nội dung thông báo và đặt các điểm cuối đích.

Các loại thông báo có sẵn, tính cập nhật của dữ liệu và các trường phụ thuộc vào khung phân bổ (AppsFlyer hoặc SKAN) như được mô tả trong các phần tiếp theo.

<div id="appsflyer-attribution-messages" />

<Accordion title="Thông báo phân bổ AppsFlyer">

Đặc tính thông báo

| Đặc điểm | Chi tiết |
| --- | --- |
| Phân tách loại thông báo | <ul><li>Thông báo có thể được phân tách theo điểm cuối (tối đa 6 điểm cuối cho mỗi ứng dụng) hoặc bạn có thể xác định loại thông báo bằng cách kiểm tra giá trị của các trường được liệt kê:<ul><li>event\_name</li><li>conversion\_type</li><li>campaign\_type</li></ul></li><li>Giá trị của các trường cho mỗi loại thông báo được cho biết trong bảng sau.</li></ul>**Ví dụ:**<br /><br />Thông báo có nội dung sau:<ul><li>conversion\_type=install</li><li>campaign\_type=organic</li><li>event\_name=install</li></ul>Sử dụng bảng để xác định rằng sự kiện này là sự kiện cài đặt của người dùng tự nhiên. |
| Độ mới của dữ liệu | Thông báo được gửi ngay sau khi sự kiện được ghi nhận trên nền tảng AppsFlyer. Hoạt động này thường trong vòng vài phút. |
| Nội dung thông báo (trường) | <ul><li>Thông báo có cấu trúc `key:value`.</li><li>Xem các trường <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary#field-availability-by-reporting-tool">Push API</Anchor> phân bổ có sẵn của AppsFlyer.</li><li>Mỗi mã khóa đại diện cho một trường dữ liệu thô. Xem <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary#data-fields-dictionary">mô tả về các trường dữ liệu thô trong AppsFlyer</Anchor>.</li><li>Các mã khóa trống hoặc rỗng hoàn toàn sẽ không được gửi đi.</li><li>Ví dụ này chứa cả trường rỗng và trường trống. Các đăng lại thực không có trường trống hoặc rỗng. Ví dụ được cung cấp có định dạng JSON.<ul><li>[iOS](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=0&single=true&output=csv)</li><li>[Android](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=233131974&single=true&output=csv)</li></ul></li></ul> |
| Định dạng của trường nhãn thời gian | <ul><li>Nhãn thời gian UTC: `yyyy-mm-dd hh:mm:ss.sss`. Ví dụ: hiển thị là`2019-09-17 00:09:00.123`. Một sự kiện diễn ra lúc 18:00 theo giờ Tokyo. Thời gian sự kiện được chuyển đổi thành UTC, tức là 09:00. Thời gian được ghi nhận là thời gian UTC.</li><li>Nhãn thời gian đã chọn của múi giờ (cụ thể cho ứng dụng): `yyyy-mm-dd hh:mm:ss.sss±th:tm`. Ví dụ: `2019-09-17 18:00:16.000+0900`. Một sự kiện diễn ra lúc 18:00 theo giờ Tokyo. Thời gian sự kiện hiển thị được ghi nhận là 18:00+09:00. 09:00 là múi giờ Tokyo.</li></ul> |

<div id="available-message-types" />

#### Các loại thông báo khả dụng

<table><tbody><tr><th>Bối cảnh phân bổ</th><th>Loại thông báo</th><th>trường conversion_type</th><th>Trường campaign_type</th><th>Trường event_name</th><th>trường event_type</th></tr><tr><td>Thu hút người dùng</td><td>Lượt cài đặt\*</td><td><span>Cài đặt</span></td><td><p>Không tự nhiên: UA</p><p>Tự nhiên: organic</p></td><td><p>Cài đặt</p></td><td><ul><li><p>Cài đặt</p></li><li><p>organic-install</p></li></ul></td></tr><tr><td>Thu hút người dùng </td><td>Cài đặt các sự kiện trong ứng dụng</td><td><span>Cài đặt</span></td><td><p>Không tự nhiên: UA</p><p>Tự nhiên: organic</p></td><td><p>Tên sự kiện do nhà quảng cáo xác định</p></td><td><ul><li><p>install-in-app-event</p></li><li><p>organic-install-in-app-event</p></li></ul></td></tr><tr><td><p>Nhắm mục tiêu lại</p></td><td>Thu hút lại (Re-engagement) </td><td><span>Thu hút lại</span></td><td>nhắm mục tiêu lại</td><td>Thu hút lại</td><td><p>Thu hút lại</p></td></tr><tr><td>Tái xác định mục tiêu </td><td>Sự kiện trong ứng dụng tương tác lại (Re-engagement in-app events)</td><td>Thu hút lại</td><td>nhắm mục tiêu lại</td><td>Tên sự kiện do nhà quảng cáo xác định</td><td><p>re-engagement-in-app-event</p></td></tr><tr><td>Tái xác định mục tiêu </td><td>Tái phân bổ </td><td>cài đặt lại</td><td>nhắm mục tiêu lại</td><td>Ghi công lại</td><td><p>Ghi công lại</p></td></tr><tr><td>Thu hút người dùng </td><td>Lượt cài đặt lại</td><td>cài đặt lại</td><td><p>Không tự nhiên: UA</p><p>Tự nhiên: organic</p></td><td><p>cài đặt lại</p></td><td><ul><li><p>cài đặt lại</p></li><li><p>organic-reinstall</p></li></ul></td></tr><tr><td>Nhắm mục tiêu lại</td><td>Sự kiện trong ứng dụng phân bổ lại</td><td>cài đặt lại</td><td>nhắm mục tiêu lại</td><td>Tên sự kiện do nhà quảng cáo xác định</td><td><p>re-attribution-in-app-event</p></td></tr><tr><td colspan="6">\* Một số lượt cài đặt liên quan đến phân bổ lượt xem hết được phân bổ cho <a href="./about-raw-data-identifier-restrictions" target="_blank">nguồn truyền thông bị hạn chế.</a> </td></tr></tbody></table>

<div id="unique-fields" />

#### Các trường duy nhất

<table><tbody><tr><th>Tên hiển thị</th><th>Tên API Push</th></tr><tr><td>Đơn vị tiền tệ đã chọn\*</td><td>selected_currency</td></tr><tr><td>Doanh thu bằng loại tiền đã chọn</td><td>doanh_thu_bằng_loại_tiền_<br/>đã_chọn</td></tr><tr><td>Chi phí bằng loại tiền tệ đã chọn</td><td>chi_phí_bằng_loại_tiền_<br/>đã_chọn</td></tr><tr><td>Múi giờ thời gian tải xuống thiết bị đã chọn</td><td>device_download_time_selected_timezone</td></tr><tr><td>Múi giờ thời gian tiếp xúc được phân bổ đã chọn</td><td>attributed_touch_time_selected_timezone</td></tr><tr><td>Múi giờ thời gian cài đặt đã chọn</td><td>múi_giờ_thời_gian_cài_đặt_<br/>đã_chọn</td></tr><tr><td>Múi giờ thời gian diễn ra sự kiện đã chọn</td><td>múi_giờ_thời_gian_sự_<br/>kiện_đã_chọn</td></tr><tr><td><p>Múi giờ đã chọn (\*)</p></td><td>múi_giờ_đã_chọn</td></tr></tbody><tbody><tr><td colspan="2">\* Đây là cài đặt cấp ứng dụng có hiệu lực tại thời điểm thông báo API được gửi.</td></tr></tbody></table>

</Accordion>

<div id="skan-attribution-messages" />

<Accordion title="Thông báo phân bổ SKAN">

Phần này mô tả các thông báo (loại báo cáo) có sẵn cho SKAN và cách xác định thông báo. Đọc phần này, sau đó [Thiết lập điểm cuối phân bổ SKAN.](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)

Đọc liên quan: <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports">Các trường dữ liệu thô SKAN</Anchor>. Thông báo API Push có cấu trúc và trường tương đương.

Đặc tính thông báo:

| Đặc điểm | Chi tiết |
| --- | --- |
| Phân tách loại thông báo | <ul><li>Tất cả các thông báo đều được gửi đến 1 điểm cuối do bạn thiết lập.</li><li>Để xác định loại thông báo, hãy sử dụng các trường sau:<ul><li>event\_name</li><li>skad\_redownload</li></ul></li><li>Giá trị của các trường cho mỗi loại thông báo được cho biết trong bảng sau</li></ul>Ví dụ:<br /><br />Thông báo có nội dung sau:<ul><li>event\_name: install</li><li>skad\_redownload: true</li></ul>Vì skad\_redownload: true, bạn xác định rằng đây là một sự kiện tải xuống lại. |
| Độ mới của dữ liệu | <ul><li>Lượt cài đặt, lượt tải xuống lại và sự kiện trong ứng dụng:<ul><li>Xử lý hàng ngày</li><li>Được gửi tới điểm cuối của bạn vào ngày sau khi AppsFlyer nhận được đăng lại iOS</li><li>Dự kiến nhận được thông báo sự kiện từ 05:00–08:00 UTC (thời gian chính xác có thể thay đổi)</li><li>Ví dụ: Các đăng lại nhận được vào Thứ Hai được bắt đầu gửi từ Thứ Ba 05:00 UTC</li></ul></li><li>Đăng lại từ iOS và bản sao Đăng lại: Thông báo được gửi ngay sau khi chúng đến AppsFlyer</li></ul> |
| Ví dụ về thông báo | Bảng tính chứa các ví dụ về thông báo. Ví dụ cung cấp có định dạng JSON. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vS0CO6W7jgx6zxMeSGIo-hbqLbFh3AO0OT6qp4cWmgdbWVMjLJ-2dermVz49jmAXexewiOGzR1YjGzu/pub?output=xlsx">Thông báo ví dụ SKAN</Anchor>. |

<div id="message-types-for-skan-attribution" />

#### Các loại thông báo cho phân bổ SKAN

| Loại thông báo | Trường event\_name | Trường skad\_redownload | trường event\_type |
| --- | --- | --- | --- |
| Lượt cài đặt | Cài đặt | <ul><li>Các giá trị có thể có: false, trống, rỗng.</li><li>Nếu trường không có trong thông báo, hãy coi giá trị đó là false.</li></ul> | skad-installs |
| Lượt tải xuống lại | Cài đặt | đúng | skad-re-downloads |
| Sự kiện trong ứng dụng | Tên sự kiện do nhà quảng cáo đặt | Tên sự kiện do nhà quảng cáo đặt | skad-in-app-events |
| Đăng lại từ iOS | Không bao giờ có trong thông báo này | Đôi khi có sẵn | skad-postbacks |
| <Anchor target="_blank" href="/marketers/vi/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">Bản sao đăng lại</Anchor> | Không bao giờ có trong thông báo này | Đôi khi có sẵn | skad-postbacks-copy |

**Xác định loại thông báo phân bổ SKAN**

**Lưu ý:** Điều này không áp dụng cho các thông báo sao chép đăng lại đến trực tiếp từ iOS.

<Image align="center" alt="PushAPI-2_en-us.png" src="https://files.readme.io/7a3ede8da87e48cc640e6e61d8f42011174122140ca63ace37c1d5c25ceadc19-20274836865809.png" />

</Accordion>

<div id="set-up-push-api-endpoints" />

## Thiết lập điểm cuối API Push

<div id="caution" />

> ❗️ **Chú ý**
>
> Không sử dụng API Push để gửi dữ liệu được phân bổ AppsFlyer đến các bên thứ ba vì các lý do sau:
>
> * Bạn có thể vi phạm các quy định về quyền riêng tư, như CCPA, nếu người dùng lựa chọn không gửi dữ liệu của họ cho bên thứ ba.
> * Một số nguồn truyền thông hạn chế cách sử dụng, chia sẻ với bên thứ ba hoặc cả hai, những dữ liệu cấp người dùng do họ cung cấp. Đảm bảo rằng bạn tuân thủ các điều khoản sử dụng của nguồn truyền thông đó.
>   Ví dụ: [Twitter,](https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html) [Snapchat,](https://www.snap.com/en-US/privacy/privacy-policy/) [Pinterest.](https://policy.pinterest.com/en/privacy-policy)
>
> Lưu ý:  Chú ý này không áp dụng cho dữ liệu SKAN. Sử dụng API Push để gửi dữ liệu SKAN tới các điểm cuối của bên thứ ba.

Để thiết lập API Push, hãy hoàn thành danh sách hành động sau.

<div id="push-api-setup-checklist" />

#### Danh sách kiểm tra thiết lập API Push

<table><tbody><tr><th>Số bước </th><th>Phân bổ AppsFlyer</th><th>Phân bổ SKAdNetwork </th></tr><tr><td>1</td><td colspan="2"><p>Nếu đã có một điểm cuối API Push đang hoạt động, bạn có thể bỏ qua bước này. </p><p>Hoàn thành các <a href="./push-api-streaming-raw-data#serverside-requirements-your-server">yêu cầu phía máy chủ</a>.</p></td></tr><tr><td>2</td><td><p>Đối với phân bổ AppsFlyer, hãy lập kế hoạch cài đặt điểm cuối bằng cách sử dụng <a href="./push-api-streaming-raw-data#push-api-planning-checklist-for-appsflyer-attribution">danh sách kiểm tra lập kế hoạch API Push.</a></p></td><td><p>Không áp dụng</p></td></tr><tr><td>3</td><td><p><a href="./push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">Thiết lập điểm cuối phân bổ AppsFlyer</a></p></td><td><p><a href="./push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint">Thiết lập điểm cuối phân bổ SKAdNetwork</a></p></td></tr></tbody></table>

<div id="serverside-requirements-your-server" />

<Accordion title="Yêu cầu phía máy chủ (máy chủ của bạn)">

Đảm bảo rằng máy chủ của bạn tuân thủ các yêu cầu sau:

<div id="server-side-requirements" />

#### Yêu cầu phía máy chủ

| URL điểm cuối | <ul><li>Tên miền hợp lệ</li><li>Số lượng điểm cuối duy nhất tối đa cho mỗi ứng dụng:<ul><li>AppsFlyer: 6 điểm cuối</li><li>SKAdNetwork: 3 điểm cuối</li></ul></li></ul> |
| --- | --- |
| Mã trả về điểm cuối | Khi nhận được thông báo, điểm cuối của bạn phải trả về mã trạng thái HTTP 200. |
| Đưa máy chủ AppsFlyer vào danh sách cho phép | Đưa <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-server-ip-address-ranges-allowlisting">các địa chỉ IP</Anchor> của máy chủ AppsFlyer vào danh sách cho phép trong tường lửa và hệ thống bảo mật của bạn để đảm bảo giao tiếp với điểm cuối. |
| Phiên bản TLS | <ul><li>TLS 1.1</li><li>TLS 1.2+ Xem các <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-https-ssl-encryption-policy-support#outgoing-messages-appsflyer-as-client">thuật toán mã hóa được hỗ trợ</Anchor></li></ul> |
| Cổng | Cổng: 80, 443 |

</Accordion>

<div id="push-api-planning-checklist-for-appsflyer-attribution" />

<Accordion title="Danh sách kiểm tra lập kế hoạch API Push để phân bổ AppsFlyer">

* Sử dụng danh sách kiểm tra đó để lập kế hoạch cài đặt điểm cuối phân bổ AppsFlyer của bạn. Các số trong hình khớp với các số hàng trong danh sách kiểm tra.
* Phần này không liên quan đến phân bổ SKAdNetwork. Xem [Thiết lập phân bổ SKAdNetwork.](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)

**Điểm cuối**

<Image align="center" alt="PushAPI_us-en.png" src="https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png" />

<div id="configure-authentication-token" />

<div id="test-the-endpoint" />

<div id="add-an-appsflyer-attribution-endpoint" />

<div id="endpoint-planning-table" />

#### Bảng kế hoạch điểm cuối

| Số thứ tự | Cài đặt | Chi tiết | Sử dụng cột này để ghi nhận các cài đặt bạn đã lên kế hoạch |
| --- | --- | --- | --- |
| 1 | Phương thức | POST hoặc GET |  |
| 2 | URL điểm cuối | - |  |
| 3 | Các loại thông báo sự kiện | <ul><li>Chọn ít nhất một loại thông báo sự kiện.</li><li>Để chọn thông báo sự kiện trong ứng dụng, bạn cần ghi nhận sự kiện trong ứng dụng. Bạn không thể chọn thông báo sự kiện trong ứng dụng cho đến khi thực hiện điều đó.</li></ul>[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png) |  |
| 4 | <ul><li>Các trường</li><li>Danh sách các trường là chung cho tất cả các loại thông báo</li></ul> | **<span id="01H8E8DET2PBGQAKHJY40R1P9Z"></span>Cảnh báo**<br />Nếu bạn đánh dấu **Select all** thì các trường mới thêm cũng sẽ được tự động chọn. Hãy đảm bảo rằng bạn có thể hỗ trợ tất cả các trường mới được tự động thêm vào lược đồ để tránh sự cố.<br /><br /><br /><br />Chọn các trường cần thiết.<ul><li>Các trường phổ biến nhất được chọn trước theo mặc định.</li><li>Chúng tôi không gửi các trường trống/rỗng</li></ul> |  |
| 5 | Loại Sự kiện trong Ứng dụng | Lọc theo các sự kiện trong ứng dụng để giảm lưu lượng truy cập gửi đến điểm cuối của bạn.<ul><li>Chọn một hoặc nhiều hoặc tất cả các sự kiện trong ứng dụng. Lưu ý! Nếu sự kiện không hiển thị trong danh sách, hãy tìm kiếm sự kiện đó.</li><li>Nếu bạn chọn tất cả, thì các sự kiện trong ứng dụng mới sẽ tự động được thêm vào.</li><li>Bạn chỉ có thể chọn sự kiện trong ứng dụng sau khi sự kiện đó đã được ghi nhận ít nhất một lần. Nếu cần, hãy sử dụng <Anchor target="_blank" href="/marketers/vi/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> để kích hoạt sự kiện.</li><li>[![mceclip1.png](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)</li></ul> |  |

</Accordion>

<div id="set-up-appsflyer-attribution-endpoint" />

<Accordion title="Thiết lập điểm cuối phân bổ AppsFlyer">

**Lưu ý:** Chỉ [chủ sở hữu tài khoản](/docs/push-api-streaming-raw-data#specifications-and-limitations) AppsFlyer mới có thể thực hiện thay đổi đối với các tùy chọn cài đặt API Push. Những người dùng tài khoản khác có thể xem các tùy chọn cài đặt.

**Để thêm một điểm cuối phân bổ của AppsFlyer:**

1. Đi đến **Integration** > **API Access**(Tích hợp > Truy cập API).Cuộn xuống phần API Push.
2. Nhấp vào **Thêm Điểm cuối.**
3. Chọn một phương thức HTTP: **POST** hoặc **GET**
4. Nhập **URL Điểm cuối**. Nếu bạn nhận được thông báo *this URL is not safe* (URL này không an toàn), hãy liên hệ với bộ phận hỗ trợ của AppsFlyer.
5. Chọn một hoặc nhiều loại sự kiện. **Lưu ý**: Nếu thông báo sự kiện trong ứng dụng bị tắt, điều đó có nghĩa là không có sự kiện trong ứng dụng nào được ghi nhận cho đến thời điểm này.
6. Chọn các trường để điền vào thông báo API Push. Lưu ý:  
   * Các trường bắt buộc luôn được gửi đi, đó là: ID ứng dụng, Tên sự kiện, Thời gian sự kiện, IDFA (iOS) hoặc ID quảng cáo (Android)
   * Sử dụng các tùy chọn kiểm soát được mô tả trong hình dưới đây để chọn các trường tùy chọn.

     <Image align="center" alt="PushAPIFieldSelect1.jpg" src="https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg" />

     * Các trường phổ biến nhất được chọn trước theo mặc định. Bạn có thể hủy các lựa chọn đó.
     * Chọn các trường tùy chọn khi cần.
     * Sử dụng nút **Clear all** (Xóa tất cả) để xóa tất cả các trường không bắt buộc.
     * Chúng tôi không gửi các trường rỗng/trống và mã khóa liên kết. Hãy tính đến điều này khi bạn lập kế hoạch cho quy trình nhập/phân tích.
7. Chọn một hoặc nhiều (tối đa 52 sự kiện) hoặc **Tất cả** sự kiện trong ứng dụng.  
   * Danh sách này được điền bằng các loại sự kiện đã được ghi nhận. Nếu có một sự kiện bị thiếu, hãy gửi một sự kiện có cùng loại này bằng thiết bị thử nghiệm.
8. Nhấp vào **Save**.  
   API Push hiện đang hoạt động. Dữ liệu chuyển đổi được gửi đến điểm cuối.
9. Kiểm tra điểm cuối bằng cách sử dụng quy trình sau.

**Để kiểm tra điểm cuối:**

1. Nhấp vào **Send Test.** Một thông báo kết quả thử nghiệm sẽ hiển thị bên dưới nút **Send Test**.   
   Một thông báo thử nghiệm được gửi đến điểm cuối. Nếu thử nghiệm không thành công, hãy đảm bảo rằng bạn đã <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-server-ip-address-ranges-allowlisting">đưa các địa chỉ IP AppsFlyer vào danh sách cho phép</Anchor>.   
   **Lưu ý**! Cơ chế thời gian chờ được sử dụng có thời lượng 2 giây. Nếu AppsFlyer không nhận được thông báo OK trong thời gian này thì AppsFlyer coi đây là gửi thông báo không thành công.
2. Xác minh rằng điểm cuối của bạn đã nhận được thông báo thử nghiệm.  
   [Xem bản sao của thông báo đã gửi.](https://docs.google.com/spreadsheets/d/e/2PACX-1vScQf189h3Ry0BU-ejbZYkMZCJRdXXYeOwuNxPEHwY77vCVYWW9P9xCTUSJKmTvVbp_yzLidXD0WGLm/pub?gid=0&single=true&output=csv)

</Accordion>

<div id="set-up-skadnetwork-attribution-endpoint" />

<Accordion title="Thiết lập điểm cuối phân bổ SKAdNetwork">

**Lưu ý:** Chỉ [chủ sở hữu tài khoản](/docs/push-api-streaming-raw-data#specifications-and-limitations) AppsFlyer mới có thể thực hiện thay đổi đối với các tùy chọn cài đặt API Push. Những người dùng tài khoản khác có thể xem các tùy chọn cài đặt.

**Để thêm điểm cuối API Push SKAdNetwork:**

1. Đi đến **Integration** > **API Access**(Tích hợp > Truy cập API).Cuộn xuống phần API Push.
2. Chọn **SKAdNetwork** làm thực thể phân bổ.
3. Nhấp vào Add Endpoint.   
   Lưu ý: Bạn có thể xác định 1-3 điểm cuối SKAdNetwork cho mỗi ứng dụng.
4. Chọn một phương thức HTTP: **POST** hoặc **GET**
5. Nhập **URL** **Điểm cuối**. Nếu bạn nhận được thông báo *this URL is not safe* (URL này không an toàn), hãy liên hệ với bộ phận hỗ trợ của AppsFlyer.
6. Chúng tôi không gửi các trường rỗng/trống và mã khóa liên kết. Hãy tính đến điều này khi bạn lập kế hoạch cho quy trình nhập/phân tích.
7. Nhấp vào **Save** (Lưu).  
   Push API hiện đang hoạt động. Dữ liệu được gửi tới điểm cuối.

</Accordion>

<div id="additional-proceduresmanaging-endpoints" />

## Các quy trình bổ sung—quản lý điểm cuối

<div id="change-an-endpoint" />

<Accordion title="Thay đổi điểm cuối">

**Lưu ý:** Chỉ [chủ sở hữu tài khoản](/docs/push-api-streaming-raw-data#specifications-and-limitations) AppsFlyer mới có thể thực hiện thay đổi đối với các tùy chọn cài đặt API Push. Những người dùng tài khoản khác có thể xem các tùy chọn cài đặt.

**Để sửa đổi tùy chọn cài đặt điểm cuối:**

1. Đi đến **Integration** > **API Access** (Tích hợp > Truy cập API).Cuộn xuống phần API Push.
2. Xác định vị trí điểm cuối cần sửa đổi.
3. Thực hiện sửa đổi.
4. Nhấp vào **Lưu**.

</Accordion>

<div id="delete-an-endpoint" />

<Accordion title="Xóa điểm cuối">

**Lưu ý:** Chỉ [chủ sở hữu tài khoản](/docs/push-api-streaming-raw-data#specifications-and-limitations) AppsFlyer mới có thể thực hiện thay đổi đối với các tùy chọn cài đặt API Push. Những người dùng tài khoản khác có thể xem các tùy chọn cài đặt.

**Để xóa điểm cuối**:

1. Đi đến **Integration** > **API Access**. Cuộn xuống phần truy cập API Push.
2. Nhấp vào **Delete endpoint** (Xóa điểm cuối).
3. Nhấp vào **Save** (Lưu).  
    Điểm cuối đã bị xóa.

</Accordion>

<div id="authentication-token-in-test-messages" />

<div id="can-i-include-custom-headers-with-the-push-api-request" />

<div id="troubleshooting-traits-and-limitations" />

## Khắc phục sự cố, đặc điểm và hạn chế

<div id="test-message-fails" />

<Accordion title="Thông báo thử nghiệm không thành công">

Nếu bạn không nhận được thông báo thử nghiệm và bạn hạn chế quyền truy cập vào máy chủ của mình bằng địa chỉ IP: hãy đảm bảo rằng bạn đã đưa <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-server-ip-address-ranges-allowlisting">tất cả các địa chỉ IP của AppsFlyer vào danh sách cho phép</Anchor>.

</Accordion>

<div id="duplicate-retargeting-inapp-events" />

<Accordion title="Các sự kiện nhắm lại mục tiêu trùng lặp trong ứng dụng">

Các sự kiện nhắm lại mục tiêu trong ứng dụng bị trùng lặp khi một sự kiện mua diễn ra như một phần của chiến dịch nhắm lại mục tiêu trong khung thời gian thu hút lại UA. Điều này được thực hiện để phân bổ doanh thu cho cả nguồn truyền thông UA và nguồn truyền thông nhắm lại mục tiêu.

Bạn sẽ chỉ nhận được sự kiện trùng lặp nếu đã bật cả:

* Cài đặt các sự kiện trong ứng dụng
* Nhắm lại mục tiêu Sự kiện trong Ứng dụng

<Anchor target="_blank" href="/marketers/vi/docs/resolve-retargeting-double-attribution">Xác định và loại bỏ các sự kiện trong ứng dụng trùng lặp</Anchor>

</Accordion>

<div id="inapp-event-message-selection-is-disabled" />

<Accordion title="Chức năng chọn thông báo sự kiện trong ứng dụng bị tắt">

<Image align="center" alt="InappSelectionDisabled_us-en.png" src="https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png" />

* Chỉ có thể chọn thông báo sự kiện trong ứng dụng sau khi có một sự kiện trong ứng dụng được ghi nhận.
* Sử dụng thiết bị thử nghiệm để tạo sự kiện trong ứng dụng hoặc sử dụng <Anchor target="_blank" href="/marketers/vi/docs/server-to-server-events-api-for-mobile-s2s-mobile">API S2S</Anchor> để thực hiện theo cách thủ công.

</Accordion>

<div id="missing-push-messages-and-cloudfront" />

<Accordion title="Thiếu tin nhắn đẩy và CloudFront">

Bạn có đang sử dụng Amazon CloudFront làm điểm cuối của mình không? Nếu vậy, hãy kiểm tra xem CloudFront có từ chối thông báo với mã từ chối 421 hay không. Nếu đúng như vậy, hãy xem <Anchor target="_blank" href="https://docs.aws.amazon.com/en_pv/AmazonCloudFront/latest/DeveloperGuide/cnames-https-dedicated-ip-or-sni.html">Chọn Cách Phân phối Yêu cầu HTTPS của CloudFront</Anchor>.

</Accordion>

<div id="endpoint-error-messages" />

<Accordion title="Thông báo lỗi điểm cuối">

**Dấu hiệu:** Thông báo *this URL is not safe* (URL này không an toàn) hiển thị khi bạn đặt URL điểm cuối.

**Hành động cần thiết**: Liên hệ với bộ phận hỗ trợ của AppsFlyer; kèm theo cả ID ứng dụng, URL điểm cuối và ảnh chụp màn hình của thông báo lỗi.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Thông số và hạn chế">

| **Thông số kỹ thuật** | Nhận xét |
| --- | --- |
| <span id="ad-networks"></span>Mạng quảng cáo | Không có sẵn |
| <span id="agencies"></span>Đại lý | Không có sẵn |
| <span id="appspecific-time-zone"></span>Múi giờ riêng cho ứng dụng | Được hỗ trợ |
| <span id="appspecific-currency"></span>Tiền tệ dành riêng cho ứng dụng | Được hỗ trợ |
| <span id="size-limitations"></span>Hạn chế về kích thước | Không áp dụng |
| <span id="organic"></span>Tự nhiên | Có |
| <span id="nonorganic"></span>Không tự nhiên | Có |
| <span id="data-freshness"></span>Độ mới của dữ liệu | Liên tục |
| <span id="historical-data"></span>Dữ liệu lịch sử | Không được hỗ trợ. Nếu bạn đang thiếu dữ liệu, hãy sử dụng API Pull để lấy dữ liệu. Trong trường hợp đối với SKAN, bạn có thể lấy một số dữ liệu lịch sử thông qua Data Locker (bị giới hạn bởi khung thời gian khả dụng của Data Locker). |
| <span id="account-owneruser-access"></span>Quyền truy cập của chủ sở hữu tài khoản/người dùng | Chỉ **chủ sở hữu tài khoản** AppsFlyer mới có thể thực hiện thay đổi đối với các tùy chọn cài đặt API Push.<ul><li>Mỗi tài khoản AppsFlyer **chỉ có một** chủ sở hữu tài khoản. Đây là người dùng AppsFlyer đầu tiên (được tạo vào thời điểm tài khoản được mở).</li></ul>Những người dùng tài khoản khác có thể xem các tùy chọn cài đặt API Push nhưng không thể thay đổi. |

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">So sánh các công cụ phân phối dữ liệu thô</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_app-app-id">Thiết lập API Đẩy bằng API</Anchor>

<div data-zendesk-anchors="push-api=api-push 01H89PJFBPXVKJGGH18CJBJ41W=api-push 01H89PJFBP45FQDHT4YGS58NP8=appsflyer-attribution-messages available-message-types=c%C3%A1c-lo%E1%BA%A1i-th%C3%B4ng-b%C3%A1o-kh%E1%BA%A3-d%E1%BB%A5ng 01H89PJFBP9DEX520BDGC5PANQ=c%C3%A1c-lo%E1%BA%A1i-th%C3%B4ng-b%C3%A1o-kh%E1%BA%A3-d%E1%BB%A5ng unique-fields=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-duy-nh%E1%BA%A5t 01H89PJFBPBK09Q7CRPMM4G7PJ=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-duy-nh%E1%BA%A5t 01H89PJFBQM4NKFSFF8XGMX9XT=skan-attribution-messages message-types-for-skan-attribution=c%C3%A1c-lo%E1%BA%A1i-th%C3%B4ng-b%C3%A1o-cho-ph%C3%A2n-b%E1%BB%95-skan 01H89PJFBQBFCK5QVWW2X09H28=c%C3%A1c-lo%E1%BA%A1i-th%C3%B4ng-b%C3%A1o-cho-ph%C3%A2n-b%E1%BB%95-skan set-up-push-api-endpoints=thi%E1%BA%BFt-l%E1%BA%ADp-%C4%91i%E1%BB%83m-cu%E1%BB%91i-api-push 01H89PJFBQZ2FW3ST5V4FW91GS=thi%E1%BA%BFt-l%E1%BA%ADp-%C4%91i%E1%BB%83m-cu%E1%BB%91i-api-push 01H89PJFBQ6WP7ERP0DJ69QZ1G=ch%C3%BA-%C3%BD push-api-setup-checklist=danh-s%C3%A1ch-ki%E1%BB%83m-tra-thi%E1%BA%BFt-l%E1%BA%ADp-api-push 01H89PJFBQ625A7G3QT5HQJXMW=danh-s%C3%A1ch-ki%E1%BB%83m-tra-thi%E1%BA%BFt-l%E1%BA%ADp-api-push 01H89PJFBQGW8ZV76Z0HTNX2AB=serverside-requirements-your-server serverside-requirements=y%C3%AAu-c%E1%BA%A7u-ph%C3%ADa-m%C3%A1y-ch%E1%BB%A7 01H89PJFBQ2BC5GHX403RD2RAT=y%C3%AAu-c%E1%BA%A7u-ph%C3%ADa-m%C3%A1y-ch%E1%BB%A7 01H89PJFBQ4FXB7ABMFVHX326H=push-api-planning-checklist-for-appsflyer-attribution endpoint-planning-table=b%E1%BA%A3ng-k%E1%BA%BF-ho%E1%BA%A1ch-%C4%91i%E1%BB%83m-cu%E1%BB%91i 01H89PJFBQJXWWPQDKZ387VYX3=b%E1%BA%A3ng-k%E1%BA%BF-ho%E1%BA%A1ch-%C4%91i%E1%BB%83m-cu%E1%BB%91i 01H89PJFBQZE6KJDHXRB8GK7TF=set-up-appsflyer-attribution-endpoint 01H89PJFBQQS31C6AF245SSJ61=set-up-skadnetwork-attribution-endpoint additional-procedures%E2%80%94managing-endpoints=c%C3%A1c-quy-tr%C3%ACnh-b%E1%BB%95-sungqu%E1%BA%A3n-l%C3%BD-%C4%91i%E1%BB%83m-cu%E1%BB%91i 01H89PJFBQ7WV3NM7JR5Z9QEFB=c%C3%A1c-quy-tr%C3%ACnh-b%E1%BB%95-sungqu%E1%BA%A3n-l%C3%BD-%C4%91i%E1%BB%83m-cu%E1%BB%91i 01H89PJFBQ9RZXNHGNNYV5MP7P=change-an-endpoint 01H89PJFBQGE1WESD7ZEMBEFNE=delete-an-endpoint troubleshooting-traits-and-limitations=kh%E1%BA%AFc-ph%E1%BB%A5c-s%E1%BB%B1-c%E1%BB%91-%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF 01H89PJFBQJDGT1FVHKG9DETHJ=kh%E1%BA%AFc-ph%E1%BB%A5c-s%E1%BB%B1-c%E1%BB%91-%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF 01H89PJFBQAAZYF7YWKC7TP884=test-message-fails 01H89PJFBQHQJSHE09GC599AQ6=duplicate-retargeting-inapp-events 01H89PJFBRDET8T8CTAP1GW0J9=inapp-event-message-selection-is-disabled 01H89PJFBRH58FX1FTH37DP3HC=missing-push-messages-and-cloudfront 01H89PJFBR3CJSR2AEFP3HT5JE=endpoint-error-messages 01H89PJFBRZXXEMPBGBPB35MQ9=specifications-and-limitations h_01HE7SH7XFMPJ13DKCZ04RCJDD=xem-th%C3%AAm" />
