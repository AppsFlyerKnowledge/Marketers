---
title: Data Locker dành cho nhà tiếp thị
metadata:
  keywords:
    - Reports
    - Data Locker
    - Advertisers
    - Raw Data
    - Developers
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2019-02-03T12:20:08Z'
  edited_at: '2023-11-20T08:41:22Z'
  id: 360000877538
  locale: vi
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/vi/articles/360000877538
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Khái quát:** Data Locker gửi dữ liệu báo cáo vào kho lưu trữ đám mây để tải nạp vào hệ thống BI của bạn. Bạn có thể chọn giữa các điểm đích lưu trữ khác nhau: Bộ chứa do AppsFlyer sở hữu trong AWS hoặc kho lưu trữ do bạn sở hữu trong AWS, GCS, Yandex, BigQuery và Snowflake. Data Locker hỗ trợ [nhiều điểm đích](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination). Nghĩa là bạn có thể gửi tất cả dữ liệu đến nhiều điểm đích, phân chia dữ liệu theo điểm đích hoặc kết hợp cả hai.

## Data Locker

![6133DataLockerForAdvertisers.png](https://files.readme.io/820fee89515ccdcdfac2043bcb9fde722ddc8ec852a140ec250378c581d9c375-32966274469649.png)

Trong Data Locker, hãy chọn ứng dụng, nguồn truyền thông, sự kiện và báo cáo của bạn để đưa vào dữ liệu mà AppsFlyer cung cấp cho các tùy chọn lưu trữ đám mây bạn đã chọn. Sau đó, tải dữ liệu theo cách lập trình từ bộ lưu trữ vào hệ thống của bạn.

<div id="data-locker-features" />

<Accordion title="Tính năng—Data Locker">

| Tính năng | Mô tả |
| --- | --- |
| [Tùy chọn lưu trữ (đám mây)](/docs/data-locker-for-marketers#storage-options) | Data Locker có thể gửi dữ liệu của bạn đến bất cứ nhà cung cấp dịch vụ đám mây nào sau đây:<ul><li>Bộ lưu trữ do AppsFlyer sở hữu trên AWS</li><li><Anchor target="_blank" href="/marketers/vi/docs/data-locker-cloud-service-setup">Bộ lưu trữ do bạn sở hữu</Anchor> trên:<ul><li>AWS</li><li>GCS</li><li>[Beta] Azure Blob</li><li>[Thử nghiệm] Yandex</li><li>BigQuery</li><li>Snowflake</li></ul></li></ul>Bạn có thể đặt nhiều điểm đích trong Data Locker. Điều này có nghĩa là bạn có thể gửi tất cả hoặc một phần dữ liệu của mình đến [nhiều điểm đích](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination).<br /><br />**Ví dụ:**<ul><li>Phân tách dữ liệu theo loại báo cáo. Gửi dữ liệu thô tới GCS và hợp nhất dữ liệu vào Snowflake.</li><li>Phân tách dữ liệu theo ứng dụng và gửi dữ liệu theo mỗi nhóm ứng dụng đến các bộ chứa khác nhau.</li></ul> |
| Đa ứng dụng | Gửi dữ liệu của 1, nhiều hoặc tất cả các ứng dụng trong tài khoản của bạn. Khi bạn thêm ứng dụng vào tài khoản, chúng có thể tự động được đưa vào. |
| Khung thời gian khả dụng | 14 ngày |
| [Phân tách dữ liệu](/docs/data-locker-for-marketers#app-segregation) | Các tùy chọn phân tách dữ liệu có sẵn (thích hợp cho kho lưu trữ đám mây có bộ chứa):<ul><li>[Mặc định] **Hợp nhất:** Dữ liệu của tất cả các ứng dụng được kết hợp. Trường ID ứng dụng cấp hàng được sử dụng để xác định ứng dụng trong tệp dữ liệu.</li><li>**Phân tách theo ứng dụng:** Dữ liệu của mỗi ứng dụng nằm trong một thư mục riêng. Tên thư mục chứa ID ứng dụng.</li></ul> |
| Tùy chọn định dạng dữ liệu | <ul><li>Đối với kho lưu trữ đám mây có bộ chứa:<ul><li>CSV</li><li>Parquet</li><li><Anchor target="_blank" href="/marketers/vi/docs/adobe-experience-platform-aep-integration-with-appsflyer-data-locker">Adobe</Anchor></li></ul></li><li>Kho dữ liệu</li></ul> |
| Tính cập nhật của dữ liệu | Tính cập nhật tùy thuộc vào loại báo cáo<ul><li>**Hàng giờ:** Dữ liệu được tạo liên tục; ví dụ: lượt cài đặt và dữ liệu sự kiện trong ứng dụng được ghi trong vòng vài giờ sau khi sự kiện đến AppsFlyer.</li><li>**Hàng ngày:** Các báo cáo như lượt gỡ cài đặt, được tạo hàng ngày và sẵn sàng vào ngày hôm sau.</li><li>**Tạo phiên bản:** Nếu cùng một báo cáo được tạo nhiều lần trong cùng một khoảng thời gian, thì sẽ áp dụng một cơ chế tạo phiên bản.</li></ul> |

</Accordion>

<div id="reports-available-via-data-locker" />

<Accordion title="Báo cáo có sẵn qua Data Locker">

<Anchor target="_blank" href="/marketers/vi/docs/data-locker-advertiser-reports">Báo cáo có sẵn qua Data Locker</Anchor>

</Accordion>

## Kiến trúc lưu trữ dữ liệu

<div id="overview" />

<Accordion title="Tổng quan">

Cấu trúc dữ liệu của bạn trong kho lưu trữ phụ thuộc vào việc bạn gửi dữ liệu đến kho lưu trữ đám mây hay kho dữ liệu. Cấu trúc thư mục được mô tả ở đây áp dụng cho kho lưu trữ (bộ chứa). Trong trường hợp lưu trữ trong kho dữ liệu, xin lưu ý rằng có thể áp dụng tham chiếu đến thư mục cho các chế độ xem. Xem <Anchor target="_blank" href="/partners/vi/docs/data-locker-for-partners">Snowflake</Anchor>.

Dữ liệu được ghi vào tùy chọn lưu trữ bạn đã chọn. Trong trường hợp lưu trữ đám mây, lưu trữ này thuộc sở hữu của AppsFlyer trên AWS hoặc thuộc sở hữu của bạn trên AWS, GCS hoặc Yandex. Bạn có thể chuyển các tùy chọn lưu trữ bất kỳ lúc nào hoặc gửi một phần hoặc tất cả dữ liệu của mình sang nhiều tùy chọn lưu trữ.

Dữ liệu trong kho lưu trữ đám mây có bộ chứa được sắp xếp theo cấu trúc thư mục phân cấp dựa vào loại báo cáo, ngày và giờ. Hình sau đây là một ví dụ về cấu trúc này:

![DLFolderOVerview.png](https://files.readme.io/78f360ec1df72253e5b2cd725f3eecf4e17548a7f06b544a94a75a2c319d77a0-18107910420369.png)

Dữ liệu của một báo cáo nhất định được chứa trong các thư mục giờ (h) được liên kết với báo cáo đó:

* Số lượng thư mục giờ phụ thuộc vào tính cập nhật của dữ liệu báo cáo (hàng giờ, hàng ngày hoặc tạo phiên bản).
* Dữ liệu được cung cấp dưới dạng tệp nén Snappy hoặc GZIP hoặc tệp không nén, có định dạng Parquet hoặc CSV.
* Tệp tin dữ liệu bao gồm các cột (trường).
* Cấu trúc lược đồ (trường) của <Anchor target="_blank" href="/marketers/vi/docs/data-locker-advertiser-reports#user-journey">báo cáo hành trình của người dùng</Anchor> giống hệt nhau và phụ thuộc vào các trường bạn đã chọn. Các báo cáo khác đều có các trường cụ thể riêng, hay còn gọi là báo cáo không lược đồ. Xem <Anchor target="_blank" href="/marketers/vi/docs/data-locker-advertiser-reports#user-journey">báo cáo của nhà tiếp thị Data Locker</Anchor> về các báo cáo có sẵn và các liên kết đến thông số kỹ thuật của báo cáo.

</Accordion>

<div id="folder-structure" />

<Accordion title="Cấu trúc thư mục">

| Thư mục | Mô tả |
| --- | --- |
| ID Đăng ký | <Image alt="DataLockerFolders.png" src="https://files.readme.io/0cda5728e48dab772878cad13ed3b81168f152e1bf01604ac45b700af804dd16-32966264039185.png" width="439px" /><ul><li>Thư mục cấp cao nhất trong bộ chứa phụ thuộc vào chủ sở hữu và nhà cung cấp bộ lưu trữ. Nói chung, thư mục cấp cao nhất là ID Đăng ký của bạn nhưng trong một số trường hợp, ví dụ như nếu bạn sử dụng Cyberduck thì ID sẽ được đặt trong dấu trang và không hiển thị trong cấu trúc thư mục.</li><li>Thư mục *data-locker-hourly* chứa các chủ đề báo cáo. Các thư mục trên cấp độ này phụ thuộc vào quyền sở hữu bộ chứa và nhà cung cấp dịch vụ đám mây.</li></ul>**Ví dụ về cấu trúc thư mục dựa trên chủ sở hữu bộ chứa và nhà cung cấp đám mây**<ul><li>**Bộ chứa AppsFlyer**: &lt;af-ext-reports>/&lt;unique\_identifier>/&lt;data-locker-hourly></li><li>**Bộ chứa AWS của bạn**: *&lt;af-datalocker-your bucket prefix>/&lt;generated-home-folder>&lt;subscription-id>*</li><li>**Bộ chứa GCS của bạn:** &lt;your bucket name>/&lt;generated-home-folder>/&lt;subscription-id></li></ul> |
| Chủ đề (t) | Loại báo cáo liên quan đến chủ đề của báo cáo. |
| Ngày (dt) | Đây là ngày dữ liệu liên quan. Trong trường hợp dữ liệu thô, ngày này có nghĩa là ngày xảy ra sự kiện. Trong trường hợp dữ liệu hợp nhất, thì đây chính là ngày báo cáo. |
| Thời gian (h hoặc phiên bản) | Thư mục ngày được chia thành các thư mục **theo giờ (h)** hoặc **phiên bản** tùy thuộc vào loại báo cáo.<br /><br />**<span id="hourly-folders"></span>Thư mục theo giờ**<br /><br />Các thư mục h liên quan đến thời gian AppsFlyer nhận dữ liệu. Ví dụ: các sự kiện cài đặt nhận được trong khoảng thời gian từ 14:00-15:00 UTC được ghi vào tệp tin h=14. Lưu ý! Sẽ có độ trễ về thời gian, khoảng 1-3 giờ, từ khi dữ liệu đến AppsFlyer cho đến khi thư mục h được ghi vào Data Locker. Ví dụ: thư mục h=14 được ghi 1 giờ sau đó vào lúc 15:00 UTC.<br /><br />**Đặc điểm thư mục theo giờ**:<ul><li>Có các thư mục 24 h được đánh số từ 0–23. Ví dụ: h=0, h=1, v.v.</li><li>Thư mục đến trễ, h=late, chứa các sự kiện của ngày hôm trước đến sau nửa đêm. Có nghĩa là các sự kiện đến trong khoảng 00:00–02:00 UTC của ngày hôm sau. Ví dụ: nếu người dùng cài đặt một ứng dụng vào thứ Hai lúc 08:00 UTC và sự kiện đến vào thứ Ba lúc 01:00 UTC, thì sự kiện được ghi vào thư mục đến trễ của ngày thứ Hai.</li><li>Dữ liệu đến sau 02:00 UTC được ghi vào thư mục của ngày và giờ đến thực tế.</li><li>Đảm bảo rằng dữ liệu trong thư mục h=late được sử dụng. Dữ liệu không được chứa trong bất kỳ thư mục nào khác.</li><li>Thư mục \_temporary: Trong một số trường hợp, chúng tôi tạo một thư mục tạm thời trong một thư mục h. Bỏ qua các thư mục tạm thời và thư mục con. Ví dụ: /t=impressions/dt=2021-04-11/h=18/**\_temporary**.</li><li>**Lưu ý**:<ul><li>Các báo cáo dữ liệu thô cập nhật dữ liệu hàng ngày được lưu trữ trong thư mục h=23. Báo cáo lượt gỡ cài đặt thường nằm trong thư mục h=2 nhưng cũng có thể nằm trong bất kỳ thư mục nào.</li><li>Báo cáo Nhóm người và báo cáo Tính gia tăng được lưu trữ trực tiếp vào thư mục dt.</li><li>Các báo cáo tạo phiên bản tuân theo một quy ước khác được mô tả trong phần này.</li></ul></li></ul>**Những điều cần lưu ý về báo cáo theo giờ cho các ứng dụng không sử dụng thời gian UTC.**<br /><br />Để đảm bảo rằng bạn nhận được tất cả dữ liệu cho một ngày nhất định theo lịch, bạn phải sử dụng các thư mục theo ngày được xác định bằng múi giờ ứng dụng như được trình bày chi tiết sau đây:<ul><li>**Múi giờ ở bán cầu Đông**: Để nhận được tất cả dữ liệu của một ngày nhất định theo lịch, bạn phải sử dụng các thư mục theo ngày và giờ UTC. Ví dụ: Múi giờ ứng dụng của bạn là UTC+10 (Sydney, Úc). Để có được tất cả dữ liệu theo giờ liên quan đến ngày thứ Ba (Sydney), bạn phải sử dụng các thư mục sau: Thứ Hai h=14–23 và muộn hơn, thứ Ba h=0–13 và 14-15 Tại sao bạn phải sử dụng thứ Ba h=14-15? Một vài dữ liệu có thể đến muộn. Vì vậy, các thư mục h=14–15 có thể chứa các sự kiện đến muộn. Bạn phải lọc event\_time để phù hợp với ngày ứng dụng theo lịch so với UTC.</li><li>**Múi giờ ở bán cầu Tây**: Để nhận được tất cả dữ liệu của một ngày nhất định theo lịch, bạn phải sử dụng các thư mục theo ngày và giờ UTC. Ví dụ: Múi giờ ứng dụng của bạn là UTC- 7 (Los Angeles). Để nhận được tất cả dữ liệu theo giờ liên quan đến thứ Ba (Los Angeles), bạn phải sử dụng các thư mục sau: Thứ Ba h=7–23 và muộn hơn, thứ Tư h=0–6 và 7-8. Tại sao bạn phải sử dụng thứ Tư h=7-8? Một vài dữ liệu có thể đến muộn. Vì vậy, các thư mục h=7–8 có thể chứa các sự kiện đến muộn. Bạn phải lọc event\_time để phù hợp với ngày ứng dụng theo lịch so với UTC.</li></ul>**<span id="version-folders"></span>Thư mục phiên bản**<br /><br />Một số báo cáo có tùy chọn tạo phiên bản. Điều này có nghĩa là dữ liệu cập nhật mới nhất cho một ngày nhất định sẽ được cung cấp nhiều lần. Vì dữ liệu có thể tiếp tục cập nhật do dữ liệu đến muộn hoặc dữ liệu chính xác hơn nên cùng một báo cáo có nhiều phiên bản, trong đó phiên bản gần đây nhất sẽ là chính xác nhất.<br /><br />Các báo cáo cho một ngày nhất định được chứa trong thư mục phiên bản của ngày đó. Mỗi phiên bản được chứa trong một thư mục riêng biệt có tên được đặt bằng nhãn thời gian Epoch phân biệt từng báo cáo.<br /><br />Trong quy trình nhập dữ liệu, bạn cần lưu ý rằng dữ liệu có thể được ghi trở về trước. Ví dụ: vào ngày 14 tháng 1, dữ liệu có thể được ghi vào thư mục 1 tháng 1. Nếu bộ chứa do bạn sở hữu, hãy cân nhắc sử dụng thông báo dịch vụ đám mây để kích hoạt quy trình nhập của bạn (<Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/NotificationHowTo.html">AWS</Anchor> \| <Anchor target="_blank" href="https://cloud.google.com/storage/docs/pubsub-notifications">GCS</Anchor>) |

</Accordion>

<div id="app-segregation" />

<Accordion title="Phân tách ứng dụng">

Đối với kho lưu trữ đám mây có bộ chứa, dữ liệu được cung cấp trong các tệp dữ liệu hợp nhất chứa dữ liệu của tất cả các ứng dụng đã chọn hoặc được phân tách thành các thư mục theo loại ứng dụng. Việc phân tách sẽ nằm trong thư mục h như được mô tả trong bảng sau. 

| Loại phân tách | Mô tả |
| --- | --- |
| [Mặc định] Hợp nhất | Dữ liệu cho tất cả các ứng dụng được cung cấp trong các tệp dữ liệu thống nhất. Khi sử dụng dữ liệu, hãy sử dụng trường app\_id cấp hàng để phân biệt giữa các ứng dụng.<br /><br />**Ví dụ về tệp dữ liệu nằm trong thư mục h=2**<br /><br />![UnifiedByApp.png](https://files.readme.io/dbc39c2ce99c1ff607fd553b9c9034e55728c102f31fd18a501cc00910267b28-18107874522513.png)<br /><br />Quy ước đặt tên tệp tin dữ liệu là unique\_id.gz.<ul><li>Quy trình tải dữ liệu của bạn phải:<ul><li>Tải dữ liệu sau khi đã đặt cờ hiệu \_SUCCESS.</li><li>Tải tất cả các tệp tin trong thư mục có phần mở rộng *.gz*. Không xây dựng quy trình nhập của bạn bằng cách sử dụng logic đánh số bộ phận.</li></ul></li></ul> |
| Phân tách theo ứng dụng | Thư mục chứa các thư mục con cho mỗi ứng dụng. Các tệp tin dữ liệu cho một ứng dụng nhất định được chứa trong thư mục ứng dụng. Trong hình sau, thư mục h=19 chứa các thư mục ứng dụng. Mỗi thư mục ứng dụng chứa các tệp tin dữ liệu được liên kết. Lưu ý! Các tệp tin dữ liệu không chứa app\_id, nên bạn phải xác định app\_id bằng cách sử dụng thư mục.<br /><br />![DLSegregateByApp.png](https://files.readme.io/90639507da82f7dafacfa5bfb67fa96a8277747cd0eee226d74498bf5ff16869-32966264040977.png)<br /><br />Trong mỗi thư mục ứng dụng, quy ước đặt tên là unique\_id.gz:<ul><li>Quy trình tải dữ liệu của bạn phải:<ul><li>Tải dữ liệu sau khi đã đặt cờ hiệu \_SUCCESS.</li><li>Tải tất cả các tệp tin trong thư mục có phần mở rộng *.gz*. Không xây dựng quy trình nhập của bạn bằng cách sử dụng logic đánh số bộ phận.</li></ul></li></ul>Giới hạn: Tùy chọn này không có sẵn cho báo cáo Phân bổ trên cơ sở người dùng. |

</Accordion>

<div id="data-files" />

<Accordion title="Tệp dữ liệu">

Tệp tin dữ liệu phụ thuộc vào loại phân tách.

<table><thead><tr><th>Nội dung</th><th colspan="2">Chi tiết</th></tr></thead><tbody><tr><td>Cờ hiệu hoàn thành</td><td colspan="2"><p>Cờ hiệu tệp tin cuối cùng (hoàn thành) được đặt khi tất cả dữ liệu cho một thư mục h nhất định đã được ghi. </p><ul><li><p>Không đọc dữ liệu trong một thư mục trước khi xác minh sự tồn tại của cờ hiệu _SUCCESS.</p></li><li><p>Cờ hiệu _SUCCESS được đặt ngay cả trong trường hợp không có dữ liệu cần ghi vào một thư mục nhất định và thư mục đó trống. </p></li><li>Lưu ý! Trong tùy chọn phân tách theo ứng dụng, cờ hiệu được đặt trong thư mục h chứ không phải các thư mục ứng dụng riêng lẻ. Xem các số liệu trong phần trước. </li></ul></td></tr><tr><td>Loại tệp tin</td><td colspan="2"><ul><li>Dữ liệu được cung cấp dưới dạng tệp nén Snappy hoặc GZIP hoặc tệp không nén, có định dạng Parquet hoặc CSV.</li><li>Sau khi giải nén, các tệp tin dữ liệu sẽ có định dạng Parquet hoặc CSV tùy theo tùy chọn cài đặt của bạn.</li></ul></td></tr><tr><td>Thứ tự cột (tệp tin CSV) </td><td colspan="2"><p>Trong trường hợp tệp tin CSV, thứ tự các trường trong báo cáo luôn giống nhau. Khi chúng tôi thêm các trường mới, chúng sẽ được thêm vào bên phải các trường hiện có. </p><p>Về vấn đề này: </p><ul><li>Cấu trúc cột của báo cáo hành trình người dùng là giống hệt nhau. Điều này có nghĩa là bạn có thể có các quy trình tải dữ liệu tương tự cho các loại báo cáo khác nhau. Bạn chọn các trường có trong các báo cáo. Ý nghĩa của trường được trình bày chi tiết trong <a href="./raw-data-field-dictionary" target="_blank">từ điển dữ liệu thô</a>. </li><li>Các báo cáo có ký hiệu FF trong phần tính khả dụng của báo cáo không tuân theo cấu trúc cột chung. </li></ul></td></tr><tr><td>Những điều cần lưu ý khi điền trường</td><td colspan="2"><p><strong>Các trường rỗng hoặc trống:</strong> Một số trường được điền là <em>null</em> hoặc để trống. Điều này có nghĩa là trong trường hợp của một báo cáo nhất định, không có dữ liệu nào để báo cáo. Thông thường, <em>null</em> có nghĩa là trường này không được điền trong trường hợp của loại ứng dụng và báo cáo nhất định. Để trống "" có nghĩa là trường có liên quan theo trường hợp nhưng không tìm thấy dữ liệu nào để điền vào. </p><p>Trong trường hợp nguồn truyền thông bị hạn chế, thì nội dung của các trường bị hạn chế sẽ được đặt thành rỗng. </p><p>Về tổng thể, hai trạng thái rỗng và trống được coi là một và giống nhau; không có dữ liệu khả dụng. </p><p><strong>Múi giờ và Tiền tệ</strong></p><p>Cài đặt múi giờ và tiền tệ cụ thể cho ứng dụng không ảnh hưởng đến dữ liệu được ghi vào Data Locker. Áp dụng những điều sau: </p><ul><li> <strong>Múi giờ</strong>: Dữ liệu ngày và giờ tính theo UTC.</li><li> <strong>Tiền tệ</strong>: Trường event_revenue_usd có đơn vị là USD.</li></ul><p><strong>Giá trị có dấu phẩy</strong>: Các dấu phẩy này nằm giữa dấu ngoặc kép `"`, ví dụ: <code>`"iPhone6,1"`</code>.</p></td></tr></tbody></table>

</Accordion>

<div id="storage-options" />

<Accordion title="Tùy chọn lưu trữ">

> ❗️ **Chú ý!**
>
> Nếu bạn đang sử dụng tùy chọn bộ lưu trữ do nhà tiếp thị sở hữu:
>
> * Xác minh rằng bạn tuân thủ các quy định về quyền riêng tư của dữ liệu như GDPR và chính sách lưu giữ dữ liệu của mạng quảng cáo/SRN.
> * Không sử dụng giải pháp bộ lưu trữ do nhà tiếp thị sở hữu để gửi dữ liệu cho bên thứ ba.

* Dữ liệu được ghi cho chủ sở hữu bộ nhớ mà bạn chọn như sau:
  * Bộ nhớ của AppsFlyer
  * Bộ nhớ của khách hàng—AWS, GCS, Azure, Yandex, BigQuery và Snowflake
* Bạn có thể thay đổi lựa chọn bộ nhớ bất kỳ lúc nào.
* Nếu bạn thay đổi bộ nhớ, sẽ xảy ra các khả năng sau:
  * Chúng tôi bắt đầu ghi vào bộ nhớ mới được chọn trong vòng một giờ.
  * Chúng tôi tiếp tục ghi vào bộ nhớ hiện có trong giai đoạn chuyển tiếp là 7 ngày. Thời gian hết hạn của giai đoạn chuyển tiếp sẽ hiển thị trong giao diện người dùng. Sử dụng giai đoạn chuyển tiếp để cập nhật quy trình tải dữ liệu của bạn. Bạn có thể bắt đầu lại giai đoạn chuyển tiếp hoặc hoàn nguyên về bộ chứa AppsFlyer, nếu cần.
  * **Thay đổi bộ lưu trữ**: Bạn có thể di chuyển từ tùy chọn lưu trữ này sang tùy chọn lưu trữ khác bằng cách sử dụng tùy chọn đa bộ lưu trữ và gửi đồng thời dữ liệu đến nhiều điểm đích. Khi đã hoàn tất quá trình di chuyển và thử nghiệm, hãy xóa tùy chọn lưu trữ mà bạn không cần nữa.

|  | Bộ nhớ do AppsFlyer sở hữu (AWS) | Bộ nhớ thuộc sở hữu của nhà tiếp thị (GCS, AWS, Azure, Yandex, BigQuery, Snowflake) |
| --- | --- | --- |
| Tên bộ chứa | Do AppsFlyer đặt | <ul><li><Anchor target="_blank" href="/marketers/vi/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>: Không hạn chế</li><li><Anchor target="_blank" href="/marketers/vi/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>: Do bạn đặt. Phải chứa tiền tố af-.</li></ul>Ví dụ: `af-datalocker-your-bucket-name` |
| Quyền sở hữu bộ nhớ | AppsFlyer | Nhà tiếp thị |
| Nền tảng lưu trữ | AWS | AWS, GCS, Azure, Yandex, BigQuery, Snowflake |
| Thông tin đăng nhập để bạn truy cập dữ liệu | Có sẵn trong giao diện người dùng Data Locker cho quản trị viên tài khoản AppsFlyer của bạn | Chưa biết đến AppsFlyer. Sử dụng thông tin đăng nhập do nhà cung cấp đám mây cung cấp. |
| Lưu trữ dữ liệu | Dữ liệu sẽ bị xóa sau 14 ngày | Trách nhiệm của nhà tiếp thị |
| Yêu cầu xóa dữ liệu | Trách nhiệm của AppsFlyer | Trách nhiệm của nhà tiếp thị |
| Bảo mật | AppsFlyer kiểm soát bộ nhớ. Khách hàng có quyền truy cập đọc. | Nhà tiếp thị kiểm soát bộ lưu trữ.<ul><li>**AWS**: AppsFlyer yêu cầu quyền GetObject, ListBucket, DeleteObject, PutObject đối với bộ chứa. Bộ chứa phải dành riêng cho việc sử dụng AppsFlyer. Không sử dụng bộ chứa cho các mục đích khác.</li><li>**GCS**: Xem <Anchor target="_blank" href="/marketers/vi/docs/data-locker-cloud-service-setup">bài viết về cấu hình GCS</Anchor>.</li></ul> |
| Dung lượng lưu trữ | Do AppsFlyer quản lý | Do nhà tiếp thị quản lý |
| Kiểm soát truy cập bằng cách sử dụng điểm cuối VPC với chính sách cho bộ chứa | Không áp dụng | [Tùy chọn] Trong AWS, nếu bạn triển khai thao tác bảo mật điểm cuối VPC ở cấp độ bộ chứa thì bạn phải đưa các máy chủ AppsFlyer vào danh sách cho phép. |

#### **Thông báo cho nhân viên bảo mật trong trường hợp bộ nhớ do khách hàng kiểm soát**

Cân nhắc:

* Bộ chứa hoặc điểm đích chỉ phục vụ cho việc sử dụng AppsFlyer. Không nên ghi thực thể nào khác vào một điểm đích nhất định.
* Bạn có thể xóa dữ liệu trong điểm đích sau 25 giờ kể từ khi chúng tôi ghi dữ liệu.
* Dữ liệu được ghi vào điểm đích là bản sao dữ liệu đã có trong máy chủ của chúng tôi. Dữ liệu tiếp tục được lưu giữ trong máy chủ theo chính sách lưu giữ của chúng tôi.
* Vì lý do kỹ thuật nên đôi khi chúng tôi xóa và ghi lại dữ liệu. Do đó, chúng tôi cần quyền xóa và lên danh sách. Không có quyền nào gây rủi ro cho bạn về bảo mật. Trong trường hợp lên danh sách, chúng tôi là thực thể duy nhất ghi vào bộ chứa. Trong trường hợp xóa, chúng tôi có thể tạo lại dữ liệu.
* Để biết thêm thông tin, bạn có thể liên hệ với nhóm bảo mật của chúng tôi qua địa chỉ [hello@appsflyer.com](mailto:hello@appsflyer.com) hoặc CSM của bạn.

</Accordion>

<div id="multipleconnections-principles-more-than-one-destination" />

<Accordion title="Nguyên tắc đa kết nối (nhiều hơn một điểm đích)">

Trong Hộp khoá Dữ liệu, bạn có thể gửi một vài hoặc tất cả dữ liệu của mình tới 2 điểm đích (được xác định trong cài đặt kết nối). Ví dụ: bạn có thể gửi dữ liệu của Ứng dụng A tới AWS và dữ liệu của Ứng dụng B tới GCS.

Mỗi kết nối bao gồm một tập hợp đầy đủ các cài đặt Data Locker, bao gồm cả một điểm đích. Cài đặt kết nối độc lập với nhau.

Đối với việc quản lý các kết nối của bạn, hãy xem xét:

* Trong cài đặt Data Locker, các kết nối được hiển thị trong các tab. Mỗi kết nối có tab cài đặt riêng mà từ đó bạn có thể quản lý kết nối. Biểu tượng của mỗi tab đại diện cho loại lưu trữ.
* Để xem thông tin chi tiết của kết nối, nhân bản kết nối hoặc xóa kết nối, nhấp vào ⋮ (tùy chọn).

</Accordion>

## Quy trình

<div id="set-up-data-locker" />

<Accordion title="Thiết lập Hộp khóa Dữ liệu">

Sử dụng quy trình này để thiết lập Data Locker. Mọi thay đổi đối với cài đặt Data Locker cần tới 3 giờ để có hiệu lực.

**Điều kiện tiên quyết**

**Để thiết lập bộ lưu trữ do nhà tiếp thị sở hữu:**

Nếu bạn đang thiết lập Data Locker bằng dịch vụ lưu trữ đám mây do nhà tiếp thị sở hữu, hãy hoàn thành một hoặc nhiều quy trình sau ngay bây giờ.

* Thiết lập:
  * Bộ chứa <Anchor target="_blank" href="/marketers/vi/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>
  * Bộ chứa <Anchor target="_blank" href="/marketers/vi/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>
  * [Beta] <Anchor target="_blank" href="/marketers/vi/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor> Blob
  * [Thử nghiệm] Bộ chứa <Anchor target="_blank" href="/marketers/vi/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor>
  * Kho dữ liệu <Anchor target="_blank" href="/marketers/vi/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor>
  * Kho dữ liệu <Anchor target="_blank" href="/marketers/vi/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor>

**Lưu ý**! Nếu bạn không đăng ký Data Locker và muốn truy cập dữ liệu phân tích Nhóm người hoặc dữ liệu SKAN, bạn phải hoàn tất quy trình về dịch vụ lưu trữ đám mây do nhà tiếp thị sở hữu.

**![AppsFlyerAdmin_us-en.png](https://support.appsflyer.com/hc/article_attachments/16581340456849) Để thiết lập Data Locker:**

1. Quản trị viên cần thực hiện thiết lập.
2. Trong Appsflyer, đi đến **Tích hợp** > **Data Locker**.
3. [Tùy chọn] Nếu bạn đã có điểm đích đang hoạt động trên Data Locker và muốn thêm điểm đích khác, hãy nhấp vào **Thêm kết nối.** Đặt tên cho kết nối của bạn.
4. **Chọn một điểm đến dữ liệu dịch vụ đám mây**. Thực hiện một trong những thao tác sau:  
   * Chọn **Bộ chứa AWS của AppsFlyer** (tùy chọn này chỉ dành cho người đăng ký Data Locker). Nhấp vào **Lưu** và tiếp tục đến bước 5.
   * Chọn **S3**.
     1. Nhập tên bộ chứa AWS S3 của bạn. Bắt buộc chứa tiền tố `af-` và nhập tên thủ công.
     2. Nhấp vào **Test connection**.
     3. Xác minh rằng không hiển thị thông báo lỗi cho biết rằng đường dẫn bộ chứa không hợp lệ.
     4. Chọn **Tạo kết nối này tương thích với Adobe Experience Platform** nếu bạn muốn. Nếu đã chọn, nhấp vào **Lưu** và tiếp tục đến Bước 6.
     5. Nhấp vào **Save** (Lưu).
   * Chọn **GCS**.
     1. Nhập **tên bộ chứa GCS**.
     2. Nhấp vào **Test connection**.
     3. Xác minh rằng không hiển thị thông báo lỗi cho biết rằng đường dẫn bộ chứa không hợp lệ.
     4. Nếu muốn làm kết nối này tương thích với Adobe Experience Platform, chọn **Make this connection compatible with Adobe Experience Platform**. Nếu chọn, nhấp vào **Save** và tiếp tục đến Bước 6.
     5. Nhấp vào **Save** (Lưu).
   * [Beta] Chọn **Azure**.
     1. Nhập **Tên kết nối**, **Tên tài khoản lưu trữ** và **Mã khóa**.
     2. Xác minh rằng không hiển thị thông báo lỗi cho biết rằng đường dẫn bộ chứa không hợp lệ.
     3. Nếu muốn làm kết nối này tương thích với Adobe Experience Platform, chọn **Make this connection compatible with Adobe Experience Platform**. Nếu chọn, nhấp vào **Save** và tiếp tục đến Bước 6.
     4. Nhấp vào **Save** (Lưu).
   * [Thử nghiệm] Chọn **Yandex**.
     1. Nhập **tên Bộ chứa**, **Mã khóa truy cập** và **Mã khóa bí mật**.
     2. Xác minh rằng không hiển thị thông báo lỗi cho biết rằng đường dẫn bộ chứa không hợp lệ.
     3. Nếu muốn làm kết nối này tương thích với Adobe Experience Platform, chọn **Make this connection compatible with Adobe Experience Platform**. Nếu chọn, nhấp vào **Save** và tiếp tục đến Bước 6.
     4. Nhấp vào **Save** (Lưu).
   * Chọn **BigQuery**.
     1. Nhập ID dự án BigQuery và tên tệp dữ liệu của bạn.
     2. Nhấp vào **Test connection**.
     3. Xác minh rằng không hiển thị thông báo lỗi cho biết rằng đường dẫn bộ chứa không hợp lệ.
     4. Nhấp vào **Lưu** và tiếp tục đến Bước 6.
   * Chọn **Snowflake**.
     1. Nhập vùng Snowflake và ID tài khoản của bạn.
     2. Nhấp vào **Test connection**.
     3. Xác minh rằng không hiển thị thông báo lỗi cho biết rằng đường dẫn bộ chứa không hợp lệ.
     4. Nhấp vào **Lưu** và tiếp tục đến Bước 6.
5. Hoàn thành phần **Cài đặt dữ liệu**:
   1. Chọn định dạng tệp tin bạn muốn:
      * [Mặc định] **Parquet**
      * **CSV**
   2. Chọn kiểu nén tệp tin bạn muốn:
      * Snappy (chỉ khả dụng đối với các tệp tin Parquet)
      * GZIP
      * Không nén
   3. Chọn số hàng tối đa bạn muốn trong tập tin của mình: 10k, 25k, 50k, 100k, 200k hoặc 500k. Nhiều hàng hơn trong tập tin có nghĩa là ít tập tin hơn nhưng kích thước tập tin sẽ lớn hơn.
   4. Chọn cấu trúc thư mục ([phân tách dữ liệu](/docs/data-locker-for-marketers#app-segregation)):
      * [Mặc định] **Hợp nhất**
      * **Phân tách theo ứng dụng**
6. Hoàn thành phần **nội dung Data Locker**:
7. Chọn một hoặc nhiều **Ứng dụng** để đưa vào báo cáo. Chọn **tất cả** để tự động thêm cả các ứng dụng được thêm vào trong tương lai.
8. Nhấp vào **Apply** (Áp dụng).
9. [Tùy chọn] Chọn một hoặc nhiều **Nguồn Truyền thông** để đưa vào báo cáo.
   * Default=All (Mặc định=Tất cả). Điều này có nghĩa là các nguồn truyền thông được thêm vào trong tương lai sẽ tự động được thêm vào.
10. Nhấp vào **Apply** (Áp dụng).
11. [Tùy chọn] Chọn **các Trường** để đưa vào báo cáo. **Lưu ý**: Đôi khi chúng tôi có sẵn các trường bổ sung. Hãy cân nhắc điều này trong quá trình nhập dữ liệu.
12. Nhấp vào **Apply** (Áp dụng).
13. Chọn [các loại báo cáo](/docs/data-locker-for-marketers#data-locker). Bạn phải chọn ít nhất là 1.
14. [Tùy chọn] Đối với báo cáo **Sự kiện trong ứng dụng**, hãy chọn các sự kiện trong ứng dụng muốn đưa vào. Nếu bạn có hơn 100 loại sự kiện trong ứng dụng, bạn không thể tìm kiếm chúng. Nhập chính xác tên của sự kiện để chọn.
    * Default=All (Mặc định=Tất cả). Điều này có nghĩa là các sự kiện trong ứng dụng được thêm vào trong tương lai sẽ tự động được thêm vào.
15. Nhấp vào **Apply** (Áp dụng).
16. Nhấp vào **Lưu kết nối**. Một trong những điều sau đây có thể xảy ra:  
    * Nếu bạn đã chọn **bộ chứa AWS AppsFLyer:**
      * Bộ chứa AWS chuyên dụng được tạo. Thông tin đăng nhập bộ chứa sẽ hiển thị.
      * Có thể truy cập bộ chứa bằng thông tin đăng nhập. Thông tin đăng nhập cung cấp cho bạn quyền truy cập chỉ đọc vào bộ chứa.
    * Nếu bạn đã chọn một trong các dịch vụ lưu trữ đám mây: Dữ liệu sẽ được ghi vào dịch vụ của bạn trong vòng 3 giờ.

</Accordion>

<div id="reset-credentials" />

<Accordion title="Đặt lại thông tin đăng nhập">

Quản trị viên có thể đặt lại thông tin đăng nhập của bộ chứa AppsFlyer bất kỳ lúc nào. Lưu ý! Nếu bạn đặt lại thông tin đăng nhập, bạn phải cập nhật các tập lệnh nhập dữ liệu của mình bằng thông tin đăng nhập được cập nhật.

**![AppsFlyerAdmin_us-en.png](https://support.appsflyer.com/hc/article_attachments/16581340456849) Để đặt lại thông tin đăng nhập của bộ lưu trữ do AppsFlyer sở hữu:**

1. Trong Appsflyer, đi đến **Tích hợp** > **Data Locker**.
2. Hãy chọn điểm đích do AppsFlyer sở hữu.
3. Trong mục Credentials (Thông tin đăng nhập), nhấp vào **Reset credentials** (Đặt lại thông tin đăng nhập).  
   Một cửa sổ xác nhận sẽ hiển thị.
4. Nhấp vào **Reset** (Đặt lại).
5. Chờ (khoảng 20 giây) cho đến khi thông báo **Credentials successfully reset** (Đặt lại thành công thông tin đăng nhập) được hiển thị.  
   Có sẵn các thông tin đăng nhập cập nhật.

</Accordion>

## Thông tin bổ sung

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và Hạn chế">

| **Đặc điểm** | Nhận xét |
| --- | --- |
| Mạng quảng cáo | Không dành cho các mạng quảng cáo sử dụng |
| Đại lý | Không dành cho các đại lý sử dụng |
| Múi giờ cụ thể theo ứng dụng | Không áp dụng. Các thư mục Data Locker được chia theo giờ bằng giờ UTC. Các sự kiện thực tế chứa thời gian tính theo giờ UTC. Chuyển đổi thời gian sang bất kỳ múi giờ nào khác nếu cần. Bất kể múi giờ ứng dụng của bạn là gì, thì độ trễ từ khi sự kiện xảy ra cho đến khi sự kiện được ghi nhận trong Data Locker vẫn giữ nguyên. |
| Tiền tệ cụ thể theo ứng dụng | Không được hỗ trợ |
| Hạn chế về kích thước | Không áp dụng |
| Tính cập nhật của dữ liệu | Dữ liệu được cập nhật theo tần suất cập nhật dữ liệu báo cáo cụ thể được nêu chi tiết trong <Anchor target="_blank" href="/marketers/vi/docs/data-locker-advertiser-reports#báo-cáo-dữ-liệu-thô">bài viết này</Anchor>. |
| Dữ liệu lịch sử | Không được hỗ trợ. Nếu bạn cần dữ liệu lịch sử, một số báo cáo sẽ có sẵn thông qua API Pull, nhưng không phải tất cả. |
| Dữ liệu bị hạn chế | Các trường trong một số báo cáo bị hạn chế do giới hạn về quyền riêng tư. <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">Tìm hiểu thêm</Anchor> |
| Truy cập của người dùng | Chỉ <Anchor target="_blank" href="/marketers/vi/docs/user-management">những người dùng tài khoản có quyền cần thiết mới</Anchor> có thể cấu hình Data Locker. |
| Ứng dụng duy nhất/đa ứng dụng | Hỗ trợ đa ứng dụng. Data Locker ở cấp độ tài khoản |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Xử lý sự cố">

* **Dấu hiệu**: Không thể truy xuất dữ liệu bằng AWS CLI
* **Thông báo lỗi**: Đã xảy ra lỗi (AccessDenied) khi gọi thao tác ListObjectsV2: Truy cập bị Từ chối
* **Nguyên nhân**: Thông tin đăng nhập AWS đang được sử dụng không phải là thông tin đăng nhập chính xác cho bộ chứa AppsFlyer. Điều này có thể do trên máy của bạn có nhiều thông tin đăng nhập hoặc thông tin đăng nhập không hợp lệ.
* **Giải pháp**:
  1. Sử dụng một phương thức khác, như [Cyberduck](/docs/data-locker-for-marketers#cyberduck) để truy cập bộ chứa, nghĩa là không phải CLI. Thực hiện điều này để xác minh rằng thông tin đăng nhập bạn đang sử dụng vẫn hoạt động bình thường. Nếu bạn có thể kết nối bằng Cyberduck, điều này cho thấy có vấn đề với bộ nhớ đệm thông tin đăng nhập.
  2. <Anchor target="_blank" href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-role.html">Làm mới bộ nhớ đệm thông tin đăng nhập AWS</Anchor>.  
     **Ảnh chụp màn hình từ AWS**

     ![mceclip0.png](https://files.readme.io/e6608b196c39cb71e0a02e0eabe95378f24659a1578a16fd381bfd0053ca309e-32966264043537.png)

</Accordion>

## Truy xuất dữ liệu AWS

Sử dụng công cụ truy xuất dữ liệu AWS yêu thích của bạn, AWS CLI hoặc một trong những công cụ được mô tả trong các phần tiếp theo. Lưu ý! Các hướng dẫn chính xác phù hợp với các bộ chứa do AppsFlyer sở hữu. Điều chỉnh hướng dẫn, nếu cần, nếu bạn đang kết nối với bộ chứa của mình.

<div id="aws-cli" />

<Accordion title="AWS CLI">

**Trước khi bạn bắt đầu**:

* Cài đặt AWS CLI trên máy tính của bạn.
* Trong AppsFlyer, đi đến Data Locker, và truy xuất thông tin có trong bảng thông tin đăng nhập.

**Để sử dụng AWS CLI**:

1. Mở thiết bị đầu cuối. Để thực hiện trong Windows, bấm &lt;Windows>+&lt;R>, nhấp vào **OK**.  
   Cửa sổ dòng lệnh mở ra.
2. Nhập **cấu hình aws.**
3. Nhập Khóa Truy cập AWS như xuất hiện trong bảng thông tin đăng nhập.
4. Nhập Mã khóa Bí mật AWS của bạn như xuất hiện trong bảng thông tin đăng nhập.
5. Nhập **eu-west-1.**
6. Nhấn Enter (Không có).

Sử dụng các lệnh CLI sau đây khi cần thiết.

Trong các lệnh sau, có thể tìm thấy giá trị của `{home-folder}`

**Để liệt kê các thư mục trong bộ chứa của bạn:**

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/
```

### Liệt kê các tệp tin và thư mục

Có ba loại thư mục trong bộ chứa Data Locker của bạn:

* Loại Báo cáo `t=`
* Ngày `dt=`
* Giờ `h=`

Để liệt kê tất cả các báo cáo của một loại báo cáo cụ thể:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/
```

Để liệt kê tất cả các báo cáo của một loại báo cáo cụ thể cho một ngày cụ thể:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17
```

Để liệt kê tất cả các báo cáo của một báo cáo cụ thể, trong một giờ cụ thể của một ngày cụ thể:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17/h=23
```

Để tải xuống tệp tin cho một ngày cụ thể:

```bash
aws s3 cp s3://af-ext-reports/<home-folder>/data-locker-hourly/t=installs/dt=2020-08-01/h=9/part-00000.gz ~/Downloads/
```

</Accordion>

<div id="cyberduck" />

<Accordion title="Cyberduck">

**Trước khi bạn bắt đầu**:

* Cài đặt máy khách Cyberduck.
* Trong AppsFlyer, đi đến Data Locker và truy xuất thông tin có trong bảng thông tin đăng nhập.

**Để cấu hình Cyberduck**:

1. Trong Cyberduck, nhấp vào Action (Hành động).
2. Chọn **New Bookmark** (Dấu trang Mới). Sẽ có cửa sổ mở ra.
3. Trong trường đầu tiên, (được đánh dấu [1] trong ảnh chụp màn hình bên dưới), hãy chọn **Amazon S3.**

   [![DataDuckSmall2.png](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)
4. Điền vào các trường như sau:
   * **Biệt danh** : Văn bản tự do
   * **Server** (Máy chủ): s3.amazonaws.com
   * **ID khóa truy cập:** Sao chép Khóa truy cập AWS như khóa xuất hiện tại bảng thông tin đăng nhập trong AppsFlyer
   * **Khóa truy cập bí mật:** Sao chép khóa Bí mật của bộ chứa như xuất hiện tại bảng thông tin đăng nhập trong AppsFlyer.
   * **Đường dẫn**: `{Bucket Name}/{Home Folder}` Ví dụ: **af-ext-reports/1234-abc-ffffffff**
5. Đóng cửa sổ. Để thực hiện, hãy nhấp vào X ở góc trên bên phải của cửa sổ.
6. Chọn kết nối.  
   Các thư mục dữ liệu được hiển thị.

</Accordion>

<div id="amazon-s3-browser" />

<Accordion title="Trình duyệt Amazon S3">

**Trước khi bạn bắt đầu**:

* Cài đặt Trình duyệt Amazon S3.
* Trong AppsFlyer, đi đến Data Locker và truy xuất thông tin có trong bảng thông tin đăng nhập.

**Để cấu hình Trình duyệt Amazon S3**:

1. Trong trình duyệt S3, hãy nhấp vào **Accounts** (Tài khoản) > **Add** **New Account** (Thêm Tài khoản Mới).  
   Cửa sổ Thêm Tài khoản Mới sẽ mở ra.

   [![mceclip0.png](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)
2. Điền vào các trường như sau:
   * **Account Name** (Tên Tài khoản): văn bản tự do.
   * **Access Key ID** (ID Mã khóa Truy cập): sao chép Mã khóa Truy cập AWS như xuất hiện trong bảng thông tin đăng nhập.
   * **Secret Access Key** (Mã khóa Truy cập Bí mật): sao chép mã khóa Bí mật của Bộ chứa như xuất hiện trong bảng thông tin đăng nhập.
   * Chọn **Encrypt Access Keys** with a password (Mã hóa Mã khóa Truy cập bằng mật khẩu) và nhập mật khẩu. Ghi lại mật khẩu này.
   * Chọn **Use secure transfer** (Sử dụng phương thức truyền an toàn).
3. Nhấp vào **Save changes** (Lưu thay đổi).
4. Nhấp vào **Buckets** (Bộ chứa) > **Add External** **Bucket** (Thêm Bộ chứa Ngoài).  
   Cửa sổ Thêm Bộ chứa Ngoài sẽ mở ra.  

   <Image alt="mceclip2.png" src="https://files.readme.io/88dd43f62dbd68d0295b52a7f7b9b09449bd915e6a6d52703c24a50583e05a6e-32966264054929.png" width="433px" />
5. Nhập **Bucket name** (Tên Bộ chứa).Tên Bộ chứa có định dạng sau: `{Bucket Name}/{Home Folder}`. Các giá trị cần thiết cho tên bộ chứa và thư mục gốc hiện trong cửa sổ thông tin đăng nhập.
6. Nhấp vào **Add External bucket** (Thêm Bộ chứa Ngoài).Bộ chứa được tạo và xuất hiện trong bảng điều khiển bên trái của cửa sổ.  
   Bây giờ bạn có thể truy cập các tệp tin Data Locker.

</Accordion>

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/data-locker-advertiser-reports">Báo cáo có sẵn qua Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Chọn đúng công cụ phân phối dữ liệu thô</Anchor>

<div data-zendesk-anchors="h_01HE2S6FANNTNB580CMHNX34YA=data-locker data-locker%E2%80%94features=data-locker-features h_01HE2S6FANQH2GZ11S8S87H0YH=data-locker-features h_01HE2S6FAN6BFPJSZJBEE9P5VK=reports-available-via-data-locker data-storage-architecture=ki%E1%BA%BFn-tr%C3%BAc-l%C6%B0u-tr%E1%BB%AF-d%E1%BB%AF-li%E1%BB%87u h_01HE2S6FAN4H9DQ5HBTKSNJ72B=ki%E1%BA%BFn-tr%C3%BAc-l%C6%B0u-tr%E1%BB%AF-d%E1%BB%AF-li%E1%BB%87u h_01HE2S6FANY1FWEY6Y34T85GHM=overview h_01HE2S6FANDJ65MZ2H2FBAZYJR=folder-structure h_01HE2S6FAN7PBZ8M86FQVSN5KQ=hourly-folders h_01HE2S6FAN366V8HNCY4PFNTFG=version-folders h_01HE2S6FANHFZMCY3WZBZB9QMP=app-segregation h_01HE2S6FANVDFH9S9JN8E9J7ES=data-files h_01HE2S6FAN8ZDF5N4ECKKN1D1H=storage-options h_01HE2S6FAN2HY7V3G9NS9XCVE1=ch%C3%BA-%C3%BD notice-to-security-officers-in-the-case-of-customercontrolled-storage=th%C3%B4ng-b%C3%A1o-cho-nh%C3%A2n-vi%C3%AAn-b%E1%BA%A3o-m%E1%BA%ADt-trong-tr%C6%B0%E1%BB%9Dng-h%E1%BB%A3p-b%E1%BB%99-nh%E1%BB%9B-do-kh%C3%A1ch-h%C3%A0ng-ki%E1%BB%83m-so%C3%A1t h_01HE2S6FANRVGYPRWWFA50JAQ4=th%C3%B4ng-b%C3%A1o-cho-nh%C3%A2n-vi%C3%AAn-b%E1%BA%A3o-m%E1%BA%ADt-trong-tr%C6%B0%E1%BB%9Dng-h%E1%BB%A3p-b%E1%BB%99-nh%E1%BB%9B-do-kh%C3%A1ch-h%C3%A0ng-ki%E1%BB%83m-so%C3%A1t h_01HE2S6FANBRXA0NS4E8SP3618=multipleconnections-principles-more-than-one-destination procedures=quy-tr%C3%ACnh h_01HE2S6FANEGZC1SAPSEK0EJJQ=quy-tr%C3%ACnh h_01HE2S6FAN9ZQKVYH9PBN5GCB4=set-up-data-locker h_01HE2S6FANG1NGEDPXEKF5RNBD=reset-credentials additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HE2S6FAP4SA77B0SX7R8JMTY=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HE2S6FAP6FKAJCW92JVWD828=traits-and-limitations h_01HE2S6FAPJC20G7YZSRWP5E34=troubleshooting aws-data-retrieval=truy-xu%E1%BA%A5t-d%E1%BB%AF-li%E1%BB%87u-aws h_01HE2S6FAPJMKX567HSAR16TCN=truy-xu%E1%BA%A5t-d%E1%BB%AF-li%E1%BB%87u-aws h_01HE2S6FAPB5MW09Y4HKFV3RM8=aws-cli listing-files-and-folders=li%E1%BB%87t-k%C3%AA-c%C3%A1c-t%E1%BB%87p-tin-v%C3%A0-th%C6%B0-m%E1%BB%A5c h_01HE2S6FAP31H9NK6V870FGXZF=li%E1%BB%87t-k%C3%AA-c%C3%A1c-t%E1%BB%87p-tin-v%C3%A0-th%C6%B0-m%E1%BB%A5c h_01HE2S6FAP2E2TW4F5PJ4226Q0=cyberduck h_01HE2S6FAP74NG5VNEWKWXXJX2=amazon-s3-browser h_01HE7RB5N99WJ3XP69Z69H81AD=xem-th%C3%AAm" />
