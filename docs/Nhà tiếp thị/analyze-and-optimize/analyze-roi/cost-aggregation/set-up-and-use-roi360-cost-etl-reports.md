---
title: ETL Chi phí—chi phí chiến dịch chi tiết trong một bộ chứa
metadata:
  keywords:
    - Campaign
    - eCPI
    - clicks
    - Impressions
    - ROI
    - cost
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2020-05-17T15:36:41Z'
  edited_at: '2024-07-09T08:45:32Z'
  id: 360008849238
  locale: vi
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/vi/articles/360008849238
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sơ lược:** ETL Chi phí, một phần của AppsFlyer ROI360, cung cấp cho nhà quảng cáo dữ liệu chi phí chiến dịch có độ chi tiết tốt nhất hiện có trên mỗi nguồn truyền thông. Dữ liệu, được cập nhật 4 lần mỗi ngày, được cung cấp vào bộ chứa AWS S3 hoặc GCS của bạn để sẵn sàng tải vào các hệ thống BI của nhà quảng cáo.

<Image align="center" alt="5896_CostETL_graphic__2_.png" src="https://files.readme.io/3c9b8721fa4aba170c1ed7b7b365b4a5fe1cd74080469b3020d395352cede674-11178721788817.png" />

## Nguyên tắc của ETL Chi phí

Dữ liệu chi phí chiến dịch được viết:

* Vào bộ chứa của bạn để xem, chuyển và tải dữ liệu chi phí vào các hệ thống của bạn.
* Vào bộ chứa bốn lần mỗi ngày (độ mới của dữ liệu: <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">trong ngày)</Anchor>.
* Cho ngày hiện tại và 6 ngày trước đó (được gọi là 7 ngày trong bài viết này), cũng như các ngày 14, 29 và 88. Dữ liệu hồi tố cho phép cập nhật và chỉnh sửa trong việc báo cáo dữ liệu chi phí.
* Đối với chi phí được đối sánh với phân bổ, lượt nhấp chuột hoặc lượt hiển thị.  
  **Lưu ý**:
  * Dữ liệu trong 7 ngày qua được lấy lại từ các nguồn truyền thông. Dữ liệu cho các ngày 14, 29 và 88 được xử lý lại.
  * Chỉ dữ liệu chi phí mới được cập nhật hồi tố; không phải dữ liệu phân bổ.

Dữ liệu được cung cấp với các phương diện chính được đảm bảo:

* Địa lý: phân tích theo quốc gia
* Kênh: kênh nguồn truyền thông, chẳng hạn như trong trường hợp của Google—YouTube

Bạn có thể tùy chỉnh các phương diện và số liệu khác có trong các báo cáo theo nhu cầu của mình.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRqyHRTiLq8KUtELHqdaF6yVTfNE22X5UmUqXX89oOK5ZpS6lksXD0401G8MFmsaEzg2Csvf-d3y08Z/pub?output=xlsx">Xem tệp tin mẫu</Anchor>. **Lưu ý**: Mẫu được cung cấp là tệp tin Excel có phân tích dữ liệu theo kênh; các tệp tin ETL Chi phí được gửi tới bộ chứa của bạn dưới dạng tệp tin parquet.

## Thực hiện

<div id="report-dimensions" />

<Accordion title="Phương diện báo cáo">

* Báo cáo dành cho tất cả ứng dụng có trong ETL Chi phí, theo ngày, theo loạt.
* Mỗi lần dữ liệu được ghi vào bộ chứa, nghĩa là 4 lần một ngày, tất cả dữ liệu có sẵn sẽ được ghi, bao gồm lịch sử, cập nhật và chỉnh sửa của 6 ngày trước đó và các ngày 14, 29 và 88. Hãy cân nhắc điều này trong quá trình tải dữ liệu của bạn.
* Cấu trúc báo cáo được trình bày chi tiết trong[bảng trường tệp tin](/docs/set-up-and-use-roi360-cost-etl-reports#file-fields). Các cấu trúc là:
  * **Báo cáo tóm lược**: Ít chi tiết hơn để cho phép tiêu thụ dễ dàng hơn và nhanh hơn.
  * **Báo cáo phương diện**: Có phương diện chính được đảm bảo. Điều này có nghĩa là phương diện có sẵn cho tất cả các nguồn truyền thông có trong báo cáo đó. Ngược lại, nếu nguồn truyền thông không cung cấp dữ liệu phương diện chính thì dữ liệu đó sẽ không được đưa vào báo cáo phương diện cụ thể. Phương diện phụ được bao gồm khi có sẵn. Chúng không được đảm bảo.
  * Các phương diện chính (được đảm bảo) có sẵn là:  
    * Địa lý: Dữ liệu được gộp nhóm theo quốc gia
    * Kênh: Kênh nguồn truyền thông, ví dụ: YouTube trong trường hợp Google và Instagram trong trường hợp Meta ads.
  * Bạn nên sử dụng các phương diện và số liệu phù hợp nhất với nhu cầu kinh doanh của mình. Điều này có thể khác biệt tùy thuộc vào nguồn truyền thông.
  * [Beta kín] **Báo cáo tất cả chi phí**: Dựa trên phương diện địa lý. Bao gồm dữ liệu chi phí cho tất cả hoạt động tiếp thị trên tất cả các nền tảng, bao gồm cả các ứng dụng/nền tảng không được thêm vào AppsFlyer (trong những trường hợp này, ID ứng dụng được đánh dấu là không xác định.

</Accordion>

<div id="directory-and-filename-structure" />

<Accordion title="Cấu trúc thư mục và tên tệp tin">

* Dữ liệu được ghi vào bộ chứa có cấu trúc thư mục và tệp tin được mô tả. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRqyHRTiLq8KUtELHqdaF6yVTfNE22X5UmUqXX89oOK5ZpS6lksXD0401G8MFmsaEzg2Csvf-d3y08Z/pub?output=xlsx">Xem tệp tin mẫu</Anchor>. **Lưu ý**: Mẫu được cung cấp là tệp tin Excel có phân tích dữ liệu theo kênh; các tệp tin ETL Chi phí được gửi tới bộ chứa của bạn dưới dạng tệp tin parquet.
* Khi ETL Chi phí hoàn tất việc ghi vào thư mục, cờ sẽ được đặt bằng cách tạo tệp tin *thành công*. Đây luôn là dấu thời gian gần đây nhất trong thư mục.
* Mỗi lần dữ liệu được ghi, nó bao gồm dữ liệu cho ngày hiện tại và 6 ngày trước đó (được gọi là 7 ngày trong bài viết này), cũng như các ngày 14, 29 và 88.
* Số lượng thư mục/tệp tin như sau:  
  * Tóm lược: 4 thư mục hàng loạt mỗi ngày.
    * Mỗi thư mục lô chứa các tệp tin parquet với 7 ngày dữ liệu.
  * Phương diện: Mỗi phương diện được đảm bảo chứa 4 thư mục hàng loạt mỗi ngày.
    * Mỗi thư mục hàng loạt chứa các tệp tin parquet chứa dữ liệu được đánh số bắt đầu từ 1.
  * [Beta kín] Toàn bộ chi phí: Dựa trên phương diện địa lý, chứa 4 thư mục hàng loạt mỗi ngày.

**Cấu trúc thư mục ví dụ**

<Image align="center" alt="cost_etl_structure_4.jpg" src="https://support.appsflyer.com/hc/article_attachments/360019240077" />

**Cấu trúc thư mục**

```
/<advertiser bucket name>/cost_etl/version/dt=<yyyy-mm-dd>/b=<n>/
<dimension>/<file name>
```

#### Cấu trúc thư mục

| **Biến** | **Nội dung** |
| --- | --- |
| advertiser\_bucket\_name | Như được xác định trong cấu hình ETL Chi phí: af-xpend-cost-etl-&lt;af-account-id>-[hậu tố tên bộ chứa của bạn] |
| cost\_etl | Luôn luôn cost\_etl |
| version | Phiên bản ETL Chi phí |
| ngày | Ngày chi phí<br /><br />Định dạng: yyyy-mm-dd |
| loạt | Số 1-4 |
| phương diện | Phương diện dữ liệu:<ul><li>geo</li><li>kênh</li></ul> |
| file\_name | <ul><li>summary</li><li>all-cost</li></ul> |
| Số tệp tin parquet | <ul><li>Được đánh số bắt đầu từ 00000</li><li>Ví dụ: `part-`</li></ul> |

**Cấu trúc tên tệp tin**

```
part-<number>
```

> 📄 **Ví dụ**
>
> Đối với lần lấy dữ liệu đầu tiên vào ngày 23 tháng 6 năm 2020, cấu trúc tên thư mục và tệp tin như sau:
>
> `/bucket-name/cost_etl/v1/dt=2020-06-23/b=1/geo/part-00001`

</Accordion>

<div id="file-fields" />

<Accordion title="Trường tệp">

<div id="fieldsdimensions" />

#### Trường/Phương diện

| **Trường** | **Lưu ý** | **Luôn được điền** | **Định dạng** | **Có trong tệp tin tóm lược** |
| --- | --- | --- | --- | --- |
| ngày | Ngày chi phí phát sinh được báo cáo bởi nguồn truyền thông | Có | Chuỗi yyyy-mm-dd | ✓ |
| app\_id | Id ứng dụng trong nền tảng AppsFlyer | Có | Chuỗi | ✓ |
| media\_source | Nguồn truyền thông chịu trách nhiệm hiển thị quảng cáo | Có | Chuỗi | ✓ |
| os | Hệ điều hành của thiết bị. Những giá trị có thể có:<ul><li>Android</li><li>windowsphone</li><li>ios</li></ul> | Có | Chuỗi | - |
| đại lý | Đại lý chịu trách nhiệm đặt quảng cáo | Không | Chuỗi | - |
| chiến dịch | Thành phần của hệ thống phân cấp quảng cáo | Không | Chuỗi | - |
| campaign\_id | Thành phần của hệ thống phân cấp quảng cáo | Không | Chuỗi | - |
| bộ quảng cáo | Thành phần của hệ thống phân cấp quảng cáo | Không | Chuỗi | - |
| adset\_id | Thành phần của hệ thống phân cấp quảng cáo | Không | Chuỗi | - |
| quảng cáo | Thành phần của hệ thống phân cấp quảng cáo | Không | Chuỗi | - |
| ad\_id | Thành phần của hệ thống phân cấp quảng cáo | Không | Chuỗi | - |
| ad\_account | <ul><li>Tài khoản quảng cáo mà dữ liệu chi phí được lấy từ đó</li><li>Có liên quan đến các mạng nơi kết nối được thực hiện bằng oAuth (đăng nhập bằng thông tin đăng nhập của bạn), ví dụ như trong Google hoặc Meta ads</li></ul> | Không | Chuỗi | - |
| tiền tệ | Đơn vị tiền tệ chi tiêu của nhà quảng cáo như được xác định cho ứng dụng trong AppsFlyer | Có | Chuỗi 3 ký tự tuân thủ ISO-4217 | ✓ |
| original\_currency | Đơn vị tiền tệ của chi phí do mạng báo cáo trước bất kỳ chuyển đổi nào | Có | Chuỗi 3 ký tự tuân thủ ISO-4217 | - |
| múi giờ | <ul><li>Múi giờ của dữ liệu khi được lưu trữ trong AppsFlyer</li><li>Đôi khi các mạng báo cáo dữ liệu ở múi giờ khác so với múi giờ được xác định trong AppsFlyer. Điểm dữ liệu này giúp giải thích sự khác biệt về chi phí giữa AppsFlyer và các mạng</li></ul> | Có | Chuỗi | - |
| geo | Phương diện trong hệ thống phân cấp quảng cáo | Không | Chuỗi 2 ký tự tuân thủ ISO 3166 | ✓ |
| kênh | Phương diện trong hệ thống phân cấp quảng cáo | Không | Chuỗi | - |
| keyword\_term | (Các) từ được người dùng sử dụng để tìm kiếm trực tuyến | Có | Chuỗi | - |
| keyword\_id | ID của các thuật ngữ từ khóa ASA | Có | Chuỗi | - |
| site\_id | ID Nhà phát hành | Không | Chuỗi | - |
| campaign\_objective | Thành phần của thuộc tính chiến dịch. <Anchor target="_blank" href="/marketers/vi/docs/campaign-properties-in-cost-etl-reports">Tìm hiểu thêm</Anchor> | Không | Chuỗi | - |
| cost\_model | Thành phần của thuộc tính chiến dịch. <Anchor target="_blank" href="/marketers/vi/docs/campaign-properties-in-cost-etl-reports">Tìm hiểu thêm</Anchor> | Không | Chuỗi | - |
| af\_cost\_model | Mô hình chi phí được AppsFlyer ánh xạ và chuẩn hóa. Thành phần của thuộc tính chiến dịch. <Anchor target="_blank" href="/marketers/vi/docs/campaign-properties-in-cost-etl-reports">Tìm hiểu thêm</Anchor> | Không | Chuỗi | - |
| bid\_strategy | Thành phần của thuộc tính chiến dịch. <Anchor target="_blank" href="/marketers/vi/docs/campaign-properties-in-cost-etl-reports">Tìm hiểu thêm</Anchor> | Không | Chuỗi | - |
| af\_bid\_strategy | Chiến lược đấu thầu được AppsFlyer ánh xạ và chuẩn hóa. Thành phần của thuộc tính chiến dịch. <Anchor target="_blank" href="/marketers/vi/docs/campaign-properties-in-cost-etl-reports">Tìm hiểu thêm</Anchor> | Không | Chuỗi | - |
| bid\_amount | Thành phần của thuộc tính chiến dịch. <Anchor target="_blank" href="/marketers/vi/docs/campaign-properties-in-cost-etl-reports">Tìm hiểu thêm</Anchor> | Không | Số nguyên | - |
| original\_bid\_amount | Thành phần của thuộc tính chiến dịch. <Anchor target="_blank" href="/marketers/vi/docs/campaign-properties-in-cost-etl-reports">Tìm hiểu thêm</Anchor> | Không | Số nguyên | - |

<div id="edit-or-change-connection" />

<div id="set-up-cost-etl" />

<div id="change-from-cost-etl-to-data-locker-connection" />

<div id="change-data-locker-connection" />

<div id="edit-connection" />

<div id="procedures" />

<div id="metrics" />

#### Số liệu

<table><thead><tr><th><p><strong>Trường</strong></p></th><th><p><strong>Lưu ý</strong></p></th><th><p><strong>Luôn được điền</strong></p></th><th><p><strong>Định dạng</strong></p></th><th><p><strong>Có trong tệp tin tóm lược</strong></p></th></tr></thead><tbody><tr><td><p><span>lượt hiển thị</span></p></td><td><ul><li><span>Được tính bởi AppsFlyer.</span></li><li><span>Bao gồm cả UA và nhắm mục tiêu lại.</span></li></ul></td><td rowspan="13"><p>Có.</p><p>Nếu không có giá trị nào cho một số liệu cụ thể thì số liệu đó sẽ được điền bằng 0.</p></td><td><p><span>Số nguyên</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>lượt nhấp</span></p></td><td><ul><li><span>Được tính bởi AppsFlyer.</span></li><li><span>Bao gồm cả UA và nhắm mục tiêu lại.</span></li></ul></td><td><p><span>Số nguyên</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>reported_impressions</span></p></td><td><p><span>Được tính bởi Nguồn truyền thông</span></p></td><td><p><span>Số nguyên</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>reported_clicks</span></p></td><td><p><span>Được tính bởi Nguồn truyền thông</span></p></td><td><p><span>Số nguyên</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>installs</span></p></td><td><p><span>Được tính bởi AppsFlyer</span></p></td><td><p><span>Số nguyên</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>reported_conversions</span></p></td><td><p><span>Được tính bởi Nguồn truyền thông</span></p></td><td><p><span>Số nguyên</span></p></td><td></td></tr><tr><td><p><span>re_engagements</span></p></td><td><p><span>Được tính bởi AppsFlyer</span></p></td><td><p><span>Số nguyên</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>re_attributions</span></p></td><td><p><span>Được tính bởi AppsFlyer</span></p></td><td><p><span>Số nguyên</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>cost</span></p></td><td><p><span>Số tiền chi tiêu (bao gồm phí đại lý nếu có liên quan)</span></p></td><td><p><span>Giá trị</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>original_cost</span></p></td><td><p><span>Chi phí do mạng báo cáo, bằng đơn vị tiền tệ được mạng báo cáo trước khi có bất kỳ chuyển đổi tiền tệ nào (có thêm phí đại lý do AppsFlyer tính nếu có liên quan)</span></p></td><td>Giá trị </td><td><p><span>-</span></p></td></tr><tr><td><p><span>impressions_discrepancy</span></p></td><td><ul><li><span>Sự khác biệt giữa số liệu được mạng quảng cáo và AppsFlyer tính</span></li><li> <span>Bỏ qua số liệu này nếu:</span><ul><li><span>Không có sự trùng khớp giữa chi phí và phân bổ.</span></li><li><span>Mạng quảng cáo không hỗ trợ <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank">số lần hiển thị được báo cáo.</a></span></li></ul></li></ul></td><td><span>Số nguyên</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>clicks_discrepancy</span></p></td><td><ul><li><span> Sự khác biệt giữa số liệu được mạng quảng cáo và AppsFlyer tính</span></li><li> <span>Bỏ qua số liệu này nếu:</span><ul><li><span>Không có sự trùng khớp giữa chi phí và phân bổ.</span></li><li><span>Mạng quảng cáo không hỗ trợ <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank">số lượt nhấp chuột được báo cáo.</a></span></li></ul></li></ul></td><td><span>Số nguyên</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>installs_discrepancy</span></p></td><td><ul><li><span> Sự khác biệt giữa số liệu được mạng quảng cáo và AppsFlyer tính</span></li><li> <span>Bỏ qua số liệu này nếu:</span><ul><li><span>Không có sự trùng khớp giữa chi phí và phân bổ.</span></li><li><span>Mạng quảng cáo không hỗ trợ <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank">số lượt chuyển đổi được báo cáo.</a></span></li></ul></li></ul></td><td><span>Số nguyên</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>fees</span></p></td><td><p><span>Phí mà đại lý tính ngoài chi phí quảng cáo thông thường. </span><span></span><span><span>Được tính bởi AppsFlyer</span></span></p></td><td><p>Có</p></td><td><p><span>Số nguyên</span></p></td><td><p><span>-</span></p></td></tr><tr><td><p><span>cost_without_fees</span></p></td><td><p><span>Chi phí trừ đi phí đại lý. Được tính bởi AppsFlyer</span><span></span></p></td><td><p>Có</p></td><td><p><span>Số nguyên</span></p></td><td><p><span><span><span>-</span></span></span></p></td></tr><tr><td><p><span>original_cost_without_fees</span></p></td><td>Chi phí gốc theo báo cáo của mạng quảng cáo, không tính phí đại lý</td><td><p>Có</p></td><td><p><span>Số nguyên</span></p></td><td><p><span><span><span>-</span></span></span></p></td></tr><tr><td><p><span>ctr</span></p></td><td><ul><li><span>Tỷ lệ nhấp. Được tính bởi AppsFlyer</span></li><li><span>Công thức: Số lượt nhấp chuột / số lượt hiển thị</span></li></ul></td><td rowspan="12"><p>Không</p></td><td><span>Số nguyên</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>cvr</span></p></td><td><ul><li><span>Tỷ lệ chuyển đổi. Được tính bởi AppsFlyer</span></li><li><span>Công thức: Số lượt cài đặt / số lượt nhấp chuột</span></li></ul></td><td><span>Số nguyên </span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>ecpm</span></p></td><td><ul><li><span>Được tính bởi AppsFlyer</span></li><li><span>Công thức: (Chi phí / số lượt hiển thị) \* 1000 </span></li></ul></td><td><span> Số nguyên</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>cpi</span></p></td><td><ul><li><span>Được tính bởi AppsFlyer</span></li><li><span>Công thức: Chi phí / Số lượt cài đặt</span></li></ul></td><td><span> Số nguyên</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>ccvr</span></p></td><td><ul><li><span>Chi phí mỗi lượt chuyển đổi</span></li><li><p><span>Công thức: Chi phí / (lượt cài đặt + phân bổ lại + tương tác lại)</span></p></li></ul></td><td><span> Số nguyên</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>cvvr</span></p></td><td><ul><li><span>Tỷ lệ xem video hoàn thành. Được tính bởi AppsFlyer</span></li><li><span>Công thức: Số lượt hoàn thành video / số lượt hiển thị</span></li></ul></td><td><span> Số nguyên</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>reported_cvr</span></p></td><td><ul><li><span>Tỷ lệ chuyển đổi được báo cáo</span></li><li><span>Công thức: Số lượt chuyển đổi được báo cáo / số lượt nhấp chuột được báo cáo</span></li></ul></td><td><span> Số nguyên</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>ecpc</span></p></td><td><ul><li><span>Được tính bởi AppsFlyer</span></li><li><span>Công thức: Chi phí / số nhấp chuột</span></li></ul></td><td><span> Số nguyên</span></td><td><p><span>-</span></p></td></tr><tr><td><p><span>video_25p_views</span></p></td><td><p><span>Video đã phát 25%. Được báo cáo bởi mạng quảng cáo</span></p></td><td><span> Số nguyên</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>video_50p_views</span></p></td><td><p><span>Video đã phát 50%. Được báo cáo bởi mạng quảng cáo</span></p></td><td><span> Số nguyên</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>video_75p_views</span></p></td><td><p><span>Video đã phát 75%. Được báo cáo bởi mạng quảng cáo</span></p></td><td><span> Số nguyên</span></td><td><p><span>- </span></p></td></tr><tr><td><p><span>video_completions</span></p></td><td><p><span>Được báo cáo bởi mạng quảng cáo</span></p></td><td><span> Số nguyên</span></td><td><p><span>- </span></p></td></tr></tbody></table>

</Accordion>

<div id="set-up-cost-etl-for-aws-s3" />

<Accordion title="Thiết lập ETL Chi phí cho AWS S3">

Quy trình cấu hình này phải được thực hiện bởi người dùng quản trị.

**Trước khi bắt đầu, bạn phải**:

* Thiết lập ETL Chi phí bao gồm thiết lập bộ chứa AWS của bạn (và cấp cho AppsFlyer quyền ghi dữ liệu vào đó) cũng như thiết lập ETL Chi phí trong AppsFlyer.
* Bạn sẽ cần cả đặc quyền quản trị viên AWS và quyền truy cập vào UI AppsFlyer để hoàn tất thiết lập ETL Chi phí.
* Luôn mở các tab của AWS và AppsFlyer trong quá trình thiết lập.
* **Lưu ý**: Hỗ trợ mã hóa bộ chứa KMS hiện đang ở giai đoạn Beta.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/4256ee1b617bf6f8fe1597e3a0d194b2d20b85b4cb8be41e0c9dee9396710605-4404934404753.png) Để thiết lập bộ chứa AWS và ETL Chi phí của bạn:**

1. Đăng nhập vào giao diện điều khiển AWS.
2. Đi tới dịch vụ S3.
3. Tạo bộ chứa:
   1. Nhấp vào **Create bucket** (Tạo bộ chứa).
   2. Hoàn thành**tên Bộ chứa** như sau: Bắt đầu với tiền tố bắt buộc `af-xpend-cost-etl-acc--` rồi thêm hậu tố dưới dạng văn bản tự do.
      * `af-account-id` của bạn có thể được tìm thấy trong UI AppsFlyer như chỉ ra trong các bước 7-9 sau.
      * Xem <Anchor target="_blank" href="https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html">yêu cầu đặt tên bộ chứa Amazon S3</Anchor>.
   3. Nhấp vào **Create bucket** (Tạo bộ chứa).
4. Trong AppsFlyer, từ menu bên cạnh, chọn **Export** (Xuất) > **Cost ETL** (ETL Chi phí).
5. Bật **Cost ETL** (ETL Chi phí).
6. Trong phần **Lịch báo cáo**, chọn thời điểm bạn muốn nhận báo cáo đầu tiên. Các báo cáo tiếp theo sẽ được gửi cách nhau khoảng 6 giờ.
7. Đi tới **cài đặt Amazon S3**.  

   <Image align="center" alt="" src="https://support.appsflyer.com/hc/article_attachments/360019202837" />
8. Chọn vùng bộ chứa S3 của bạn từ danh sách thả xuống.  
   Nếu khu vực của bạn không được hiển thị, hãy liên hệ với CSM của bạn.
9. Nhập tên bộ chứa Amazon S3 của bạn.
10. Nhấp vào **Next** (Tiếp theo).  
    Đoạn mã chính sách bộ chứa sẽ hiển thị.  

    <Image align="center" alt="" src="https://support.appsflyer.com/hc/article_attachments/360019263058" />
11. Sao chép đoạn mã chính sách bộ chứa và dán vào cài đặt AWS của bạn.
    1. Trong AWS, Chọn bộ chứa bạn đã tạo cho ETL Chi phí.
    2. Đi tới tab **Permissions** (Quyền).
    3. Trong phần **Bucket policy** (Chính sách bộ chứa), hãy nhấp vào **Edit** (Chỉnh sửa).
    4. Cửa sổ Chính sách bộ chứa sẽ mở ra.
    5. Dán đoạn chính sách bộ chứa vào cửa sổ.
12. Trong cài đặt ETL Chi phí AppsFlyer của bạn, hãy nhấp vào **Next** (Tiếp theo).  
    Bước **Validate bucket** (Xác thực bộ chứa) sẽ hiển thị.
13. Nhấp vào **Validate** (Xác thực).  
    Xác minh rằng **Validation successful** (Xác thực thành công) hiển thị.
14. Nhấp vào **Next** (Tiếp theo).
15. Chọn một hoặc nhiều hoặc tất cả các ứng dụng.   Chọn **all** (tất cả) để tự động thêm các ứng dụng bạn thêm vào trong tương lai.
16. Nhấp vào **Apply** (Áp dụng).
17. Chọn ít nhất một **Phương diện được đảm bảo**: Kênh và/hoặc Địa lý.
18. Chọn ít nhất một phương diện bổ sung.  

    <Image align="center" alt="" src="https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png" />
19. Chọn ít nhất một chỉ số để đưa vào báo cáo.   

    <Image align="center" alt="" src="https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg" />
20. Nhấp vào **Apply** (Áp dụng).

</Accordion>

<div id="set-up-cost-etl-for-gcs" />

<Accordion title="Thiết lập ETL Chi phí cho GCS">

Quy trình cấu hình này phải được thực hiện bởi người dùng quản trị.

**Trước khi bắt đầu, bạn phải**:

* Thiết lập ETL Chi phí bao gồm thiết lập bộ chứa GCS của bạn (và cấp cho AppsFlyer quyền ghi dữ liệu vào đó) cũng như thiết lập ETL Chi phí trong AppsFlyer.
* Bạn sẽ cần cả đặc quyền quản trị viên GCS và quyền truy cập vào UI AppsFlyer để hoàn tất thiết lập ETL Chi phí.
* Luôn mở các tab của GCS và AppsFlyer trong quá trình thiết lập.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/4256ee1b617bf6f8fe1597e3a0d194b2d20b85b4cb8be41e0c9dee9396710605-4404934404753.png) Để thiết lập bộ chứa GCS và ETL Chi phí của bạn:**

1. Đăng nhập vào giao diện điều khiển AWS.
2. Tạo một bộ chứa.  
   Đặt tên cho bộ chứa như sau:
   * Bắt đầu với tiền tố bắt buộc `af-xpend-cost-etl-acc--` rồi thêm hậu tố dưới dạng văn bản tự do.
   * `af-account-id` của bạn có thể được tìm thấy trong UI AppsFlyer như chỉ ra trong các bước 6-8 sau.
   * Xem <Anchor target="_blank" href="https://cloud.google.com/storage/docs/naming-buckets">các yêu cầu đặt tên bộ chứa GCS</Anchor>.
3. Trong AppsFlyer, từ menu bên cạnh, chọn **Export** (Xuất) > **Cost ETL** (ETL Chi phí).
4. Bật **Cost ETL** (ETL Chi phí).
5. Trong phần **Lịch báo cáo**, chọn thời điểm bạn muốn nhận báo cáo đầu tiên. Các báo cáo tiếp theo sẽ được gửi cách nhau khoảng 6 giờ.
6. Đi đến **Data destination** (Đích dữ liệu) và chọn **bộ chứa Google Cloud Storage (GCS)**.
7. Nhập tên bộ chứa GCS.
8. Nhấp vào **Next** (Tiếp theo).  
   Tài khoản dịch vụ AppsFlyer sẽ hiển thị, được sử dụng để đặt quyền GCS.
9. Trong giao diện điều khiển GCS của bạn, hãy đặt <Anchor target="_blank" href="https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-iam">quyền IAM</Anchor> cho bộ chứa:
   1. Thêm tài khoản dịch vụ AppsFlyer làm tài khoản chính cho bộ chứa ETL Chi phí.
   2. Gán vai trò Quản trị viên Đối tượng Lưu trữ.
10. Trong cài đặt ETL Chi phí AppsFlyer của bạn, hãy nhấp vào **Next** (Tiếp theo).  
    Bước **Validate bucket** (Xác thực bộ chứa) sẽ hiển thị.
11. Nhấp vào **Validate** (Xác thực).  
    Xác minh rằng **Validation successful** (Xác thực thành công) hiển thị.
12. Nhấp vào **Next** (Tiếp theo).
13. Chọn một hoặc nhiều hoặc tất cả các ứng dụng.   Chọn **all** (tất cả) để tự động thêm các ứng dụng bạn thêm vào trong tương lai.
14. Nhấp vào **Apply** (Áp dụng).
15. Chọn ít nhất một **Phương diện được đảm bảo**: Kênh và/hoặc Địa lý.
16. Chọn ít nhất một phương diện bổ sung.  

    <Image align="center" alt="" src="https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png" />
17. Chọn ít nhất một chỉ số để đưa vào báo cáo.   

    <Image align="center" alt="" src="https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg" />
18. Nhấp vào **Apply** (Áp dụng).

</Accordion>

<div id="aws-object-ownership" />

<Accordion title="Quyền sở hữu đối tượng AWS">

Trong AWS, theo mặc định, khi AppsFlyer ghi đối tượng vào bộ chứa của bạn, chủ sở hữu đối tượng là AppsFlyer. Tùy thuộc vào quá trình tải dữ liệu của bạn, bạn có thể phải thay đổi quyền sở hữu mặc định cho mình—chủ sở hữu bộ chứa.

**Để thay đổi quyền sở hữu các đối tượng trong bộ chứa của bạn**:

1. Đăng nhập vào Giao diện điều khiển Quản lý AWS và mở giao diện điều khiển Amazon S3 tại <Anchor target="_blank" href="https://console.aws.amazon.com/s3/">https://console.aws.amazon.com/s3/</Anchor>.
2. Trong danh sách **Bộ chứa** , chọn tên của bộ chứa mà bạn muốn bật Quyền sở hữu Đối tượng S3.
3. Đi tới tab **Permissions** (Quyền).
4. Trong **Object Ownership** (Quyền sở hữu Đối tượng), nhấp vào **Edit** (Chỉnh sửa).
5. Chọn **Bucket owner preferred** (Ưu tiên chủ sở hữu bộ chứa).
6. Nhấp vào **Save**.

</Accordion>

<div id="combine-cost-etl-and-cohort-reports" />

<div id="combine-geo-report-and-all-cost-report" />

<div id="report-schedule" />

<div id="best-practices" />

## Phương pháp thực hành tốt nhất

<div id="override-data" />

<Accordion title="Ghi đè dữ liệu">

Khi lấy và phân tích dữ liệu của bạn, bạn nên lấy dữ liệu cho một ngày và loạt cụ thể hoặc ghi đè tất cả dữ liệu trước đó cho những ngày mà loạt hiện tại cung cấp. Nếu không, bạn có thể thấy dữ liệu tương tự được lặp lại.

Ví dụ: loạt 1 vào ngày 20 tháng 2 chứa dữ liệu cho ngày 14-20 tháng 2. Tuy nhiên, các loạt được viết vào ngày 19 tháng 2 cũng chứa dữ liệu từ ngày 14 tháng 2 đến ngày 19 tháng 2. Ghi đè dữ liệu của những ngày trước đó nhận được vào ngày 19 tháng 2 bằng dữ liệu nhận được trong đợt ngày 20 tháng 2 gần đây nhất.

</Accordion>

<div id="geo-versus-channel" />

<Accordion title="Địa lý so với kênh">

Không phải tất cả các mạng đều cung cấp dữ liệu cho tất cả các phương diện cùng nhau. Dữ liệu địa lý và kênh trong Meta ads là những ví dụ phổ biến nhất. Đây là lý do tại sao hai bộ dữ liệu riêng biệt được cung cấp. Bộ dữ liệu địa lý được đảm bảo có dữ liệu địa lý và bộ dữ liệu kênh được đảm bảo có dữ liệu kênh.

Trong nhiều trường hợp và đối với nhiều nguồn truyền thông, dữ liệu trong nhóm địa lý và kênh sẽ giống hệt nhau. Do đó, hãy sử dụng một trong các bộ dữ liệu (địa lý hoặc kênh), tùy theo những gì phù hợp nhất với nhu cầu của bạn.

Nếu thỏa thuận tích hợp với một nguồn truyền thông nhất định không bao gồm kênh, do đó kênh đó trống, chúng tôi sẽ xử lý dữ liệu đó như thể nó chứa kênh đó.

</Accordion>

<div id="aggregate-data" />

<Accordion title="Dữ liệu hợp nhất">

ETL Chi phí cung cấp dữ liệu linh hoạt và chi tiết sâu nhất có thể được trích xuất từ ​​mạng quảng cáo. Để rút ra thông tin chi tiết hữu ích từ lượng dữ liệu khổng lồ tiềm năng như vậy, bạn nên tổng hợp dữ liệu theo cách phù hợp nhất với nhu cầu kinh doanh của mình. Ví dụ: nếu bạn cần hiểu dữ liệu chi phí ở cấp chiến dịch và cấp quốc gia, hãy sử dụng các phương diện đó.

</Accordion>

<div id="standardization-across-networks" />

<Accordion title="Tiêu chuẩn hóa trên các mạng">

Không phải tất cả các mạng đều cung cấp dữ liệu với mức độ chi tiết như nhau. Ví dụ: Meta ads không cung cấp dữ liệu chi phí ID trang web, trong khi X Ads không cung cấp dữ liệu chi phí địa lý. Hãy lưu ý những trường hợp như vậy khi bạn tổng hợp dữ liệu ETL Chi phí và đảm bảo bạn xem xét dữ liệu tương tự khi so sánh các mạng.

</Accordion>

<div id="compare-data" />

<Accordion title="So sánh dữ liệu">

ETL Chi phí cung cấp thông tin liên quan đến tất cả dữ liệu chi phí của bạn. Một số chiến dịch được cung cấp trong ETL Chi phí không xuất hiện trong một số giao diện điều khiển AppsFlyer, ví dụ: dữ liệu của các chiến dịch không hoạt động, nghĩa là các chiến dịch không có bất kỳ lượt cài đặt nào được ghi lại. Để so sánh dữ liệu, hãy tìm ID chiến dịch cụ thể trong trang tổng quan và so sánh nó với dữ liệu chi phí trong ETL Chi phí. <Anchor target="_blank" href="/marketers/vi/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">Tìm hiểu thêm về tính khả dụng của dữ liệu chi phí</Anchor>

</Accordion>

<div id="additional-information" />

## Thông tin bổ sung

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Lưu ý |
| --- | --- |
| Múi giờ | Nếu múi giờ được thay đổi, dữ liệu chi phí sẽ bị nhân bản trong ngày và ngày sau khi thay đổi. <Anchor target="_blank" href="/marketers/vi/docs/changing-app-time-zone-settings">Tìm hiểu thêm</Anchor> |
| Tính cập nhật của dữ liệu | <Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Trong ngày</Anchor>. Trong quá trình thiết lập ETL Chi phí, bạn đặt lịch báo cáo, nghĩa là thời điểm bạn muốn nhận báo cáo. **Lưu ý**: Sau khi dữ liệu chi phí đến bộ chứa của bạn, việc truyền dữ liệu tiếp theo tới hệ thống BI của bạn có thể khác nhau rất nhiều, tùy thuộc vào kích thước báo cáo và tệp tin parquet, có thể từ vài KB đến nhiều GB. |

</Accordion>

<div data-zendesk-anchors="cost-etl-principles=nguy%C3%AAn-t%E1%BA%AFc-c%E1%BB%A7a-etl-chi-ph%C3%AD h_01HA29GW8PVZJ8MP23K7QVR40J=nguy%C3%AAn-t%E1%BA%AFc-c%E1%BB%A7a-etl-chi-ph%C3%AD implementation=th%E1%BB%B1c-hi%E1%BB%87n h_01HA29GW8PZPME9GVCFDW4YJA6=th%E1%BB%B1c-hi%E1%BB%87n h_01HA29GW8PBGSNK06ATZMRRV2K=report-dimensions h_01HA29GW8PWN30BCQCK29V0FTA=directory-and-filename-structure directory-structure=c%E1%BA%A5u-tr%C3%BAc-th%C6%B0-m%E1%BB%A5c h_01HA29GW8P99TFVPPXECB3NA2F=c%E1%BA%A5u-tr%C3%BAc-th%C6%B0-m%E1%BB%A5c h_01HA29GW8P0B1JJTGYDW863D7Z=file-fields fieldsdimensions=tr%C6%B0%E1%BB%9Dngph%C6%B0%C6%A1ng-di%E1%BB%87n h_01HA29GW8PQATB4K5VJP1HD4NW=tr%C6%B0%E1%BB%9Dngph%C6%B0%C6%A1ng-di%E1%BB%87n metrics=s%E1%BB%91-li%E1%BB%87u h_01HA29GW8PZTS7XDWGYWXFZPYG=s%E1%BB%91-li%E1%BB%87u h_01HA29GW8QJ13G4FX7PD3WXXCQ=set-up-cost-etl-for-aws-s3 h_01HA29GW8QYD8WST6NVG5AS298=set-up-cost-etl-for-gcs h_01HA29GW8Q6D630E8SDVSFYVG7=aws-object-ownership best-practices=ph%C6%B0%C6%A1ng-ph%C3%A1p-th%E1%BB%B1c-h%C3%A0nh-t%E1%BB%91t-nh%E1%BA%A5t h_01HA29GW8QKPQXE4GHECAC5R5X=ph%C6%B0%C6%A1ng-ph%C3%A1p-th%E1%BB%B1c-h%C3%A0nh-t%E1%BB%91t-nh%E1%BA%A5t h_01HA29GW8QHX8AMK4T7E85H7RS=override-data h_01HA29GW8QT5FNNYSWHCT99D68=geo-versus-channel h_01HA29GW8QA3FP46EMZVYDEZF3=aggregate-data h_01HA29GW8QPW0NXEMF1WGJMKSF=standardization-across-networks h_01HA29GW8Q3FNS0W7SKTG7S9R1=compare-data additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HA286GA6WPYVNN7KCXK7DGFM=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HA282W8WHHNDG75XZNSV2QQF=traits-and-limitations" />
