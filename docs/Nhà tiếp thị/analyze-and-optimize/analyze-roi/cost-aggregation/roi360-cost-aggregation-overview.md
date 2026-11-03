---
title: ROI360—tổng quan về tổng hợp chi phí
metadata:
  keywords:
    - Advertisers
    - Agencies
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
    - Agencies
    - ROI360
  created_at: '2015-12-24T10:45:16Z'
  edited_at: '2023-11-17T02:10:07Z'
  id: 207040526
  locale: vi
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/vi/articles/207040526
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Khái quát:** Tìm hiểu về các phương thức để nhà quảng cáo tổng hợp và xem dữ liệu về chi phí tiếp thị.

![roi360_image.png](https://files.readme.io/1eaf922de9a1174c1971582dd32f53b995de014c8c2bf288b52a93c83334374e-11245891045777.png)

## Tổng hợp chi phí

**ROI360**:

* Cung cấp dữ liệu chi phí quảng cáo hợp nhất và số liệu về hiệu suất LTV liên quan đến chi phí. Các số liệu này có sẵn qua bảng điều khiển và báo cáo hiệu suất. Các số liệu liên quan đến chi phí có sẵn bao gồm ROI, ROAS, lượt nhấp, lượt hiển thị, ROI của chiến dịch và chi phí hiệu quả trung bình trên mỗi lượt cài đặt (eCPI) theo thời gian.
* Hỗ trợ các mô hình chi phí khác nhau được đối tác sử dụng, chẳng hạn như CPI, CPA, CPC và CPM.
* Ghi nhận chi phí quảng cáo theo API, nhập chi tiêu quảng cáo (tải lên tệp tin CSV) và <Anchor target="_blank" href="/marketers/vi/docs/view-aggregated-cost-data-for-attribution-links">chi phí theo lượt nhấp</Anchor>.
* Đại lý có thể truy cập dữ liệu chi phí ROI360 cho các nhà quảng cáo có đăng ký ROI360.

Các số liệu sau được cung cấp cho các nhà quảng cáo không đăng ký ROI360:

* <Anchor target="_blank" href="/marketers/vi/docs/view-aggregated-cost-data-for-attribution-links">Dữ liệu chi phí theo lượt nhấp</Anchor>.
* Dữ liệu về lượt nhấp và lượt hiển thị SRN, được cấu hình qua tab **Cost** (Chi phí) của đối tác tích hợp SRN.

## Nguyên tắc tổng hợp dữ liệu chi phí

Phần này mô tả các nguyên tắc chính của việc tổng hợp dữ liệu chi phí chiến dịch.

<div id="cost-aggregation-methods" />

<Accordion title="Các phương pháp tổng hợp chi phí">

Dữ liệu chi phí được thu thập từ các đối tác bằng một hoặc nhiều phương pháp. Nếu chi phí được báo cáo bằng nhiều phương pháp, thì [cơ chế ưu tiên chi phí](/docs/roi360-cost-aggregation-overview#cost-prioritization-mechanism) sẽ xác định dữ liệu nào được sử dụng. Điều này đảm bảo rằng dữ liệu chi phí không phải là tăng giả.

Sau khi AppsFlyer xử lý dữ liệu, nó sẽ hiển thị theo múi giờ UTC (mặc định) hoặc theo cài đặt <Anchor target="_blank" href="/marketers/vi/docs/changing-app-time-zone-settings">múi giờ cụ thể cho ứng dụng của bạn.</Anchor>

<table><thead><tr><th>Phương pháp tổng hợp chi phí</th><th>Các mô hình chi phí được hỗ trợ</th><th>Tính chi tiết của dữ liệu</th><th>Tính cập nhật của dữ liệu</th><th>Lưu ý</th></tr></thead><tbody><tr><td> <a href="./set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api" target="_blank">API</a>\*</td><td>Tất cả</td><td><p>Mức độ phụ thuộc vào tích hợp</p></td><td><a href="./about-data-freshness-and-timezone-support#intraday-during-the-day" target="_blank">Trong ngày</a></td><td>Dữ liệu có thể thay đổi sau sự kiện chi phí vì chúng tôi cố gắng nhận dữ liệu cho đến 30 ngày trở lại (tùy thuộc vào mạng quảng cáo). Nhờ đó, chúng tôi có thể tính đến những thay đổi có hiệu lực trở về trước do mạng quảng cáo thực hiện. </td></tr><tr><td><a href="./import-cost-data" target="_blank">Nhập chi tiêu quảng cáo (tải tệp)</a></td><td>Tất cả</td><td> <span>Mức độ </span><span>phụ thuộc vào tệp tin được tải lên</span> </td><td>Lên đến 4 giờ sau khi nhập</td><td>Chi phí đã báo cáo có thể được hoàn nguyên lại và gửi dữ liệu đã sửa trong tối đa 90 ngày.</td></tr><tr><td> <a href="./view-aggregated-cost-data-for-attribution-links" target="_blank">Lượt nhấp</a> (đường dẫn phân bổ)</td><td>CPI</td><td>Cấp người dùng</td><td><p>Tối thiểu: thời gian thực</p><p>Tối đa: Lên đến 4 giờ sau khi nhấp chuột</p></td><td>Không thể thay đổi</td></tr><tr><td colspan="5">\* Tích hợp API giữa các đối tác và AppsFlyer bằng API Chi phí hoặc API InCost (không bao giờ áp dụng cả hai). API được sử dụng và tính chi tiết của dữ liệu được cung cấp phụ thuộc vào đối tác.</td></tr></tbody></table>

</Accordion>

<div id="cost-data-availability-and-reports" />

<Accordion title="Tính khả dụng của dữ liệu chi phí và các báo cáo">

Bảng sau đây cho biết nơi có sẵn dữ liệu chi phí.

Nhằm mục đích hiểu rõ bảng này, các nội dung giải thích sau đây sẽ được áp dụng, trừ khi có quy định khác trong phần ghi chú của bảng:

* UA: Dữ liệu chi phí cho các chiến dịch chuyển đổi người dùng có ít nhất 1 lượt cài đặt được ghi nhận gần đây (nghĩa là trong khoảng 7 ngày qua).
* Hợp nhất: Dữ liệu chi phí của tất cả các chiến dịch, bao gồm cả những chiến dịch không có bất kỳ lượt cài đặt nào được ghi nhận gần đây (nghĩa là trong khoảng 7 ngày qua). Bảng cho biết thời điểm dữ liệu chỉ có sẵn cho các chiến dịch có ít nhất 1 lượt cài đặt được ghi nhận gần đây.
* Nếu việc thay đổi tên chiến dịch không được hỗ trợ thì cả hai tên chiến dịch đều hiển thị, một tên có dữ liệu phân bổ và một tên có dữ liệu chi phí. Cả hai tên chiến dịch được hiển thị đều sẽ không bao gồm hình ảnh dữ liệu đầy đủ.

#### Tính khả dụng của dữ liệu chi phí và các báo cáo

| Phương thức báo cáo | Dạng xem/dữ liệu | Hỗ trợ đổi tên chiến dịch | Lưu ý |
| --- | --- | --- | --- |
| Bảng điều khiển tổng quan | <ul><li>UA</li><li>Hợp nhất</li></ul> | Có | Chế độ xem nhắm mục tiêu lại không hiển thị chi phí. Chi phí nhắm mục tiêu lại hiển thị trong chế độ xem hợp nhất. |
| Bảng điều khiển hoạt động | UA | Có |  |
| Bảng điều khiển nhóm người | <ul><li>UA</li><li>Hợp nhất</li></ul> | Có | <ul><li>Chế độ xem nhắm mục tiêu lại không hiển thị chi phí</li><li>Dữ liệu hợp nhất này chỉ dành cho các chiến dịch có ít nhất 1 lượt cài đặt được ghi nhận gần đây.</li></ul> |
| API Nhóm người | <ul><li>UA</li><li>Hợp nhất</li></ul> | Có | Dữ liệu hợp nhất này chỉ dành cho các chiến dịch có ít nhất 1 lượt cài đặt được ghi nhận gần đây. |
| Bảng điều khiển SKAN | SKAN | Không | Số lượt cài đặt SKAN hiển thị, cùng với dữ liệu chi phí cho **tất cả** các lượt cài đặt (bao gồm cả các lượt cài đặt không phải SKAN). |
| API Hiệu suất Hợp nhất SKAN | SKAN | Không | Số lượt cài đặt SKAN hiển thị, cùng với dữ liệu chi phí cho **tất cả** các lượt cài đặt (bao gồm cả các lượt cài đặt không phải SKAN). |
| Bảng điều khiển Pivot | UA | Không |  |
| API chính | UA | Không |  |
| Bảng điều khiển tùy chỉnh | UA | Không |  |
| ETL chi phí | Hợp nhất | Có | Tất cả các hiển thị dữ liệu chi phí có sẵn. |
| API Pull Hợp nhất | UA | Không |  |
| API Push | Dữ liệu lượt nhấp chuột thô (không được tổng nhất) | Không phù hợp |  |
| API Pull dữ liệu thô | Dữ liệu lượt nhấp chuột thô (không được tổng nhất) | Không phù hợp |  |
| Data Locker | Dữ liệu lượt nhấp chuột thô (không được tổng nhất) | Không phù hợp | Nhóm người của Data Locker không hỗ trợ chi phí. |

**Lưu ý**:

* Mức độ chi tiết của dữ liệu có thể khác nhau tùy theo loại bảng thông tin/báo cáo. Công cụ báo cáo <Anchor target="_blank" href="/marketers/vi/docs/set-up-and-use-roi360-cost-etl-reports">ETL Chi phí</Anchor> chứa tập hợp dữ liệu hoàn chỉnh. Điều này bao gồm chi tiết thứ bậc chiến dịch (nguồn phương tiện, tên chiến dịch, nhóm quảng cáo và thứ nguyên được mạng quảng cáo cung cấp, bao gồm địa lý, kênh, ID trang web và từ khóa).
* Dữ liệu chi phí theo lượt nhấp có sẵn trong báo cáo dữ liệu thô.

</Accordion>

<div id="cost-prioritization-mechanism" />

<Accordion title="Cơ chế ưu tiên chi phí">

Đối với một nguồn truyền thông nhất định, chi phí có thể được cung cấp bằng nhiều phương thức tổng hợp. Để tránh tăng giả chi phí, cơ chế ưu tiên chi phí chiến dịch quyết định dữ liệu chi phí nào được cung cấp trong nền tảng. Ưu tiên được xác định theo phương thức tổng hợp. Mức độ ưu tiên từ cao nhất đến thấp nhất là: API > Nhập Chi tiêu Quảng cáo > Lượt nhấp. Nếu có, hãy sử dụng API, vì đây là công cụ chính xác nhất.

**Ưu tiên phương pháp tổng hợp chi phí chiến dịch**

![CostPriority.jpg](https://support.appsflyer.com/hc/article_attachments/360014470078)

* Cơ chế này tác động đến các báo cáo dữ liệu hợp nhất và trang tổng quan.
* Dữ liệu chi phí nhấp chuột có trong báo cáo dữ liệu thô không bị tác động bởi cơ chế ưu tiên.

> 📄 **Ví dụ**
>
> **Kịch bản:** Một mạng quảng cáo báo cáo chi phí mỗi lần nhấp chuột, nhưng bạn quyết định kích hoạt API chi phí của mạng quảng cáo.
>
> **Kết quả:** Chi phí được tổng hợp bởi cả lần nhấp chuột và API chi phí. Vì API chi phí được ưu tiên, chi phí nhấp chuột bị bỏ qua.
>
> **Kết quả:**
>
> * Có thể thực hiện nhiều phương thức tổng hợp chi phí. Chi phí thực tế được báo cáo bị ảnh hưởng bởi các **quy tắc ưu tiên của phương thức tổng hợp chi phí** được nêu trong bảng dưới đây.
> * Sự thay đổi ảnh hưởng đến lưu lượng truy cập do đại lý tạo ra theo cách tương tự. Trong đó bao gồm cả đại lý minh bạch và không minh bạch.
> * Sự thay đổi có tác động hồi tố. Dữ liệu chi phí hợp nhất cũ có thể thay đổi.

#### Quy tắc ưu tiên phương pháp tổng hợp chi phí

| Phương thức | Mô tả |
| --- | --- |
| API | <ul><li>Mức độ ưu tiên cao nhất</li><li>Chính xác nhất [phương pháp hiệu quả nhất]</li><li>API chi phí so với Nhập Chi tiêu Quảng cáo: Nếu một đối tác tích hợp có API tổng hợp chi phí quảng cáo, thì Nhập Chi tiêu Quảng cáo sẽ bị tắt. **Lưu ý!** Điều này xảy ra ngay cả khi API không được kích hoạt.</li><li>Bật API:<ul><li>Mỗi khi API chi phí được kích hoạt, chi phí nhấp chuột sẽ bị bỏ qua.</li><li>Vào ngày bạn bật API, công cụ này sẽ nhận được dữ liệu chi phí cho cả ngày; bất kể được kích hoạt vào thời gian nào trong ngày. Chi phí cho mỗi lượt nhấp bị bỏ qua cho cả ngày.</li><li>Có thể sẽ mất vài giờ để dữ liệu khả dụng sau khi bạn kích hoạt API.</li></ul></li><li>Tắt API: Vào ngày bạn tắt API, chi phí cho mỗi lượt nhấp sẽ bị bỏ qua cho đến đầu ngày hôm sau. **Ví dụ**: Vào thứ Hai lúc 14:00 theo giờ Tokyo, API bị tắt. Vào thứ Ba, từ 00:00 theo giờ Tokyo, các lượt nhấp sẽ không bị bỏ qua nữa.</li></ul> |
| Nhập chi tiêu quảng cáo | <ul><li>Ở cấp độ từ khóa và ID trang web, có mức độ ưu tiên so với dữ liệu chi phí theo lượt nhấp.</li><li>Nhập chi tiêu quảng cáo so với chi phí nhấp chuột vào ngày chiến dịch nhất định:<ul><li>Ưu tiên đối với chi phí được ghi lại bằng cách nhập cho ngày đó; chi phí nhấp chuột sẽ bị bỏ qua.</li><li>**Ví dụ: chiến dịch abc vào ngày 5 và ngày 10 tháng 12**<ul><li>Ghi lại chi phí chiến dịch đã nhập.</li><li>Chi phí nhấp chuột bị bỏ qua.</li><li>Không có chiến dịch hoặc ngày nào khác bị tác động.</li></ul></li></ul></li><li>Nếu mạng quảng cáo có API tổng hợp chi phí quảng cáo, thì tính năng Nhập Chi tiêu Quảng cáo sẽ bị tắt cho cùng mạng quảng cáo đó.</li></ul> |
| Lượt nhấp | Mức độ ưu tiên thấp nhất |

</Accordion>

## Danh sách các mạng quảng cáo

<div id="ad-networks-supporting-cost-api" />

<Accordion title="Các mạng quảng cáo hỗ trợ API chi phí">

Bảng sau liệt kê tất cả mạng quảng cáo hỗ trợ API Chi phí, với tính chi tiết về dữ liệu có sẵn cho từng mạng:

* Phương diện
* Các tính năng được hỗ trợ và đặc điểm của chúng
* Số liệu (theo báo cáo của mạng quảng cáo)

Tải xuống tệp tin: [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=csv), <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=xlsx">XLS</Anchor>

<Embed title="ROI360—tổng quan về tổng hợp chi phí" typeOfEmbed="iframe" url="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pubhtml?widget=true&amp;headers=false" providerUrl="https://docs.google.com" height="500px" />

</Accordion>

## Đặc điểm và hạn chế

| Đặc điểm | Lưu ý |
| --- | --- |
| Đại lý | <ul><li>Đại lý có thể truy cập dữ liệu chi phí ROI360 cho các nhà quảng cáo có đăng ký ROI360.</li><li>Khi các đại lý minh bạch chạy chiến dịch, nhà quảng cáo có thể thấy chi phí được hiển thị trong trang tổng quan và báo cáo hỗ trợ chế độ xem thống nhất. [Tìm hiểu thêm](/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports)</li><li>Nếu nhà quảng cáo chấm dứt mối quan hệ của họ với một đại lý và vô hiệu hóa các quyền của đại lý ở cấp ứng dụng, nếu đại lý đã định cấu hình chi phí cho ứng dụng thì dữ liệu chi phí vẫn được lấy. Nếu nhà quảng cáo muốn chặn không cho lấy dữ liệu này, họ phải yêu cầu đại lý vô hiệu hóa tính năng tích hợp chi phí của họ trong AppsFlyer.</li><li>Đối với một số mạng quảng cáo, đại lý phải liên hệ với nhà quảng cáo để kích hoạt tính năng tích hợp và được nhắc trong UI AppsFlyer thực hiện việc đó. Đối với các mạng này, đại lý và nhà quảng cáo phải đảm bảo rằng khi mạng quảng cáo gửi dữ liệu, dữ liệu đó sẽ bao gồm thông số `af_prt`, bắt buộc để phân bổ chi phí đại lý.</li></ul> |
| Tính cập nhật của dữ liệu API | <ul><li><Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Trong ngày</Anchor> (trừ Moloco)</li><li>Dữ liệu Mintegral có sẵn qua API vào ngày hôm sau, khoảng 4 giờ sau khi ngày hôm trước kết thúc (tùy thuộc vào chế độ cài đặt múi giờ Mintegral của bạn). Có nghĩa là, nếu sự kiện xảy ra vào Ngày 1, thì dữ liệu chi phí sẽ có sẵn vào khoảng lúc 4:00 của Ngày 2.</li></ul> |
| Thay đổi tên chiến dịch | Dữ liệu chi tiêu quảng cáo hiển thị bằng cách sử dụng tên chiến dịch được báo cáo gần đây nhất. **Lưu ý:** Điều này là để hiển thị dữ liệu hợp nhất; không phải là dữ liệu thô. |
| Múi giờ | Nếu mạng quảng cáo chỉ hỗ trợ một múi giờ và có sự khác biệt giữa múi giờ mà mạng quảng cáo hỗ trợ và múi giờ được đặt trong cài đặt ứng dụng của bạn thì múi giờ mà mạng quảng cáo hỗ trợ sẽ được sử dụng. |
| Nền tảng CTV, PC và console | Đối với các ứng dụng trên các nền tảng này, dữ liệu chi phí phải được gửi qua <Anchor target="_blank" href="/marketers/vi/docs/import-cost-data">Ad Spend Ingestion</Anchor> bằng cách sử dụng tệp tải lên qua email. |

<div data-zendesk-anchors="cost-aggregation=t%E1%BB%95ng-h%E1%BB%A3p-chi-ph%C3%AD h_01HC7K2Y627P56F5JH9QT47GB2=t%E1%BB%95ng-h%E1%BB%A3p-chi-ph%C3%AD principles-of-cost-data-aggregation=nguy%C3%AAn-t%E1%BA%AFc-t%E1%BB%95ng-h%E1%BB%A3p-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD h_01HC7K2Y62ZC932EDX00YP7DAW=nguy%C3%AAn-t%E1%BA%AFc-t%E1%BB%95ng-h%E1%BB%A3p-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD h_01HC7K2Y62K78M02ZN034N99T0=cost-aggregation-methods h_01HC7K2Y62YPM3A6Z0HBY58J00=cost-data-availability-and-reports cost-data-availability-and-reports::865c5bcd=t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD-v%C3%A0-c%C3%A1c-b%C3%A1o-c%C3%A1o h_01HC7K2Y62ZY6HWG5TJDEPHZKH=t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u-chi-ph%C3%AD-v%C3%A0-c%C3%A1c-b%C3%A1o-c%C3%A1o h_01HC7K2Y62112X308A0Y7DDDRM=cost-prioritization-mechanism h_01HC7K2Y62SZKXD4W0EJGYF6RS=v%C3%AD-d%E1%BB%A5 cost-aggregation-method-priority-rules=quy-t%E1%BA%AFc-%C6%B0u-ti%C3%AAn-ph%C6%B0%C6%A1ng-ph%C3%A1p-t%E1%BB%95ng-h%E1%BB%A3p-chi-ph%C3%AD h_01HC7K2Y62ZW7QEGM5BCATF4Q7=quy-t%E1%BA%AFc-%C6%B0u-ti%C3%AAn-ph%C6%B0%C6%A1ng-ph%C3%A1p-t%E1%BB%95ng-h%E1%BB%A3p-chi-ph%C3%AD list-of-ad-networks=danh-s%C3%A1ch-c%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o h_01HC7K2Y63T9GK0WW95YM39B5C=danh-s%C3%A1ch-c%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o h_01HC7K2Y63MG10M4Z66VHY5WYW=ad-networks-supporting-cost-api traits-and-limitations=%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF h_01HC7K2Y63798GYV1M0VQMFDJV=%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF" />
