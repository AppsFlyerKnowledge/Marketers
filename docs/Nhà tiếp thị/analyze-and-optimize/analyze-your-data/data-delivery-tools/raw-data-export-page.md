---
title: Trang xuất dữ liệu thô
metadata:
  keywords:
    - ad networks
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
    - Ad Networks
  created_at: '2020-05-11T22:25:33Z'
  edited_at: '2024-09-18T17:32:47Z'
  id: 360008613838
  locale: vi
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/vi/articles/360008613838
---
> **Sơ lược:** Tải xuống báo cáo dữ liệu thô trong các tệp CSV. Tối đa 1 triệu hàng cho mỗi lần tải xuống. Giới hạn báo cáo theo dữ liệu bạn cần bằng cách sử dụng bộ lọc.

Hình ảnh sau đây hiển thị lần đầu tiên bạn đi đến trang **Raw data export** (Xuất dữ liệu thô); trang **My reports** (Báo cáo của tôi) hiển thị nếu bạn có báo cáo sẵn sàng để tải xuống hoặc sao chép.

[![RawDataSplash.png](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)

**Báo cáo của tôi**

Trang **My reports** (Báo cáo của tôi) liệt kê các báo cáo được tạo trước đó và sẵn sàng tải xuống, sao chép hoặc cả hai. Các báo cáo được liệt kê đã được tạo trong 90 ngày trước đó; thời gian tải xuống của các báo cáo là 7 ngày. Sau 7 ngày, nếu bạn vẫn cần báo cáo, bạn phải tạo lại.

Để xem mô tả về báo cáo dữ liệu thô, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">Tổng quan về báo cáo dữ liệu thô</Anchor>

Để tạo hoặc tải xuống báo cáo, hãy xem phần quy trình của bài viết này.

[![MyReportsRawDataExport.png](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)

<div id="raw-data-export-page-features-and-filter-options" />

<Accordion title="Các tính năng trang xuất dữ liệu thô và tùy chọn bộ lọc">

Trang xuất dữ liệu thô cung cấp các báo cáo có các tính năng được liệt kê trong bảng sau.

<Table>
  <thead>
    <tr>
      <th>
        Tính năng
      </th>
      <th>
        Lưu ý
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-categories"></span>
        Danh mục báo cáo
      </td>
      <td>
        Khác nhau tùy theo gói đăng ký của bạn
      </td>
    </tr>
    <tr>
      <td><span id="date-range"></span>
        Phạm vi ngày
      </td>
      <td>
        Báo cáo dữ liệu thô được lọc theo ngày hoạt động (xuất hiện sự kiện). Bạn cũng có thể thêm bộ lọc cho ngày cài đặt. Xem danh sách các tùy chọn bộ lọc trong bảng tiếp theo.
      </td>
    </tr>
    <tr>
      <td><span id="maximum-number-of-rows"></span>
        Số hàng tối đa
      </td>
      <td>
        1 triệu hàng
      </td>
    </tr>
    <tr>
      <td><span id="rate-limitation"></span>
        Giới hạn tỷ lệ
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/vi/docs/report-generation-quotas-rate-limitations">Cơ chế hạn mức</Anchor> giới hạn số lượng báo cáo có thể được tạo mỗi ngày.
      </td>
    </tr>
    <tr>
      <td><span id="retentionreport-window"></span>
        Khoảng thời gian lưu giữ/báo cáo
      </td>
      <td>
        Báo cáo liên quan đến cài đặt (lượt cài đặt, bài đăng lại cài đặt) **60** trong số 90 ngày trước đó trong một lần tải xuống.

        Báo cáo liên quan đến sự kiện trong ứng dụng: 31 trong số 90 ngày trước đó trong một lần tải xuống.
      </td>
    </tr>
    <tr>
      <td><span id="filter-options"></span>
        Tùy chọn bộ lọc
      </td>
      <td>
        Các bộ lọc được liệt kê có sẵn để sử dụng. Trong một số trường hợp, tùy thuộc vào bộ lọc, các tùy chọn bộ lọc được điền. Ví dụ: khi lọc theo Địa lý, danh sách các quốc gia có sẵn được liệt kê.
      </td>
    </tr>
    <tr>
      <td><span id="field-selection"></span>
        Lựa chọn trường
      </td>
      <td>
        Các trường quan trọng nhất được chọn trước. Bạn có thể thêm/xóa các trường chọn lọc trong tab **Report fields** (Trường báo cáo). Một số trường có thể không liên quan đến một báo cáo nhất định. Tuy nhiên, bạn có thể chọn trường. Chúng tôi làm điều này để bạn có thể có các định dạng báo cáo (cột) nhất quán

        Ví dụ: việc chọn các trường liên quan đến gian lận (Protect360) trong báo cáo sự kiện trong ứng dụng thu về người dùng sẽ trả về các cột trống. Các trường này chỉ được điền trong ngữ cảnh báo cáo Protect360 rõ ràng.
      </td>
    </tr>
    <tr>
      <td><span id="report-csv-field-order"></span>
        Thứ tự trường báo cáo (CSV)
      </td>
      <td>
        Các cột trong báo cáo được sắp xếp theo cài đặt thứ tự trường. Trình tự cột [được liệt kê trong bảng tính](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) chứa các tab riêng biệt cho các tùy chọn kế thừa và mặc định.

        | Cài đặt | Cho phép lựa chọn trường | Lưu ý |
        | --- | --- | --- |
        | <span id="default"></span>Mặc định | Có | * Các trường đã chọn được sắp xếp theo mẫu AppsFlyer.<br />* Trong tương lai, trình tự sẽ được giữ nguyên. Các trường trong tương lai sẽ được nối vào bên phải của các trường hiện có. |
        | <span id="alphabetical-az"></span>Bảng chữ cái (A-Z) | Có | Các trường đã chọn được sắp xếp theo thứ tự bảng chữ cái (tăng dần). |
        | <span id="alphabetical-za"></span>Bảng chữ cái (Z-A) | Có | Các trường đã chọn được sắp xếp theo thứ tự bảng chữ cái ngược (giảm dần). |
        | <span id="legacy"></span>Kế thừa | Không | * Các trường được sắp xếp theo trình tự các cột trong báo cáo được chuẩn bị bằng phiên bản trước của trang dữ liệu xuất.<br />* Lựa chọn trường là cố định và không thể thay đổi.<br />* Có một số biến thể của các báo cáo cho mỗi trường tùy thuộc vào báo cáo thực tế |
      </td>
    </tr>
  </tbody>
</Table>

> 📘 **Lưu ý**
>
> Nếu bạn sử dụng cả bộ lọc đại lý và bộ lọc nguồn truyền thông, bộ lọc nguồn truyền thông không áp dụng cho các đại lý không minh bạch. Điều này có nghĩa là đối với các đại lý không minh bạch, tất cả dữ liệu đều được đưa vào; không chỉ dữ liệu từ các nguồn truyền thông được lọc

| Bộ lọc | Nhà quảng cáo | Mạng quảng cáo | Đại lý |
| --- | --- | --- | --- |
| Nguồn truyền thông | Có | Không | Có |
| Phạm vi ngày hoạt động | Có | Có | Có |
| Phạm vi ngày cài đặt | Có | Có | Có |
| Đại lý | Có | Không | Không |
| Địa lý (lãnh thổ/quốc gia) | Có | Có | Có |
| Sự kiện trong ứng dụng (có sẵn cho báo cáo sự kiện trong ứng dụng) | Có | Không | Có |

</Accordion>

<div id="procedures" />

## Quy trình

<div id="create-a-default-report" />

<Accordion title="Tạo báo cáo mặc định">

Bạn có thể tạo báo cáo với cài đặt mặc định mà không cần tùy chỉnh các trường hoặc bộ lọc của báo cáo.

**Để tạo báo cáo mặc định:**

1. Trong AppsFlyer, từ menu bên cạnh, chọn **Export** (Xuất) > **Raw Data Export** (Xuất Dữ liệu Thô)
2. Nhấp vào + **New report** (Báo cáo mới)
3. Di chuột vào loại báo cáo bạn muốn tạo và nhấp vào **Create** (Tạo).
4. Chọn **Generate now** (Tạo ngay) từ menu thả xuống.
5. Trên cửa sổ bật lên, nhấp vào **Generate now (Tạo ngay).** Thao tác tạo có thể kéo dài lên tới 10 phút.
   * Trong quá trình tạo báo cáo, bạn có thể tiếp tục làm việc, tạo báo cáo bổ sung hoặc điều hướng đến các trang khác.

**Cài đặt bộ lọc báo cáo mặc định:**

| Bộ lọc | Cài đặt mặc định |
| --- | --- |
| Ngày hoạt động | 7 ngày qua |
| Số hàng tối đa trên mỗi tệp | 200,000 |
| Nguồn truyền thông | Tất cả các nguồn truyền thông |
| Đại lý | Tất cả các đại lý |
| Địa lý | Tất cả các khu vực địa lý |

</Accordion>

<div id="create-a-custom-report" />

<Accordion title="Tạo báo cáo tùy chỉnh">

Bạn có thể tạo báo cáo tùy chỉnh bằng cách đặt bộ lọc và trường của báo cáo.

**Để tạo báo cáo tùy chỉnh:**

1. Trong AppsFlyer, từ menu bên cạnh, chọn **Export** (Xuất) > **Raw Data Export** (Xuất Dữ liệu Thô)
2. Nhấp vào + **New report** (Báo cáo mới)
3. Di chuột vào loại báo cáo bạn muốn tạo và nhấp vào **Create** (Tạo).
4. Lựa **Tùy chỉnh** từ menu thả xuống.
5. Đặt bộ lọc báo cáo
   * **Dữ liệu hoạt động:** Chọn phạm vi ngày Hoạt động. Bạn có thể đặt ngày cụ thể hoặc chọn từ các tùy chọn như tùy chỉnh, hôm qua, 7 ngày qua, v.v.
   * **Số hàng tối đa trên mỗi tệp:** [Tùy chọn] Đặt số hàng tối đa mà tệp có thể bao gồm. Chọn từ các lựa chọn 100, 200 nghìn, 500 nghìn hoặc 1 triệu hàng.
   * **Nguồn truyền thông:** [Tùy chọn] Chỉ những sự kiện được quy cho các nguồn truyền thông được chọn mới được đưa vào báo cáo. Bạn có thể thêm nguồn truyền thông vào danh sách bằng cách nhấp vào **Add item** (Thêm mục).
   * **Đại lý:** [Tùy chọn] Chỉ những sự kiện được phân bổ cho các đại lý được chọn mới được đưa vào báo cáo. Bạn có thể thêm đại lý vào danh sách bằng cách nhấp vào **Add item** (Thêm mục).
   * **Địa lý:** [Tùy chọn] Chỉ những sự kiện được phân bổ cho các khu vực địa lý được chọn mới được đưa vào báo cáo.
   * **Bộ lọc cụ thể theo loại báo cáo**: Mỗi loại báo cáo có thể có bộ lọc riêng mà từ đó bạn có thể chọn tiêu chí lọc.
6. [Tùy chọn]: Báo cáo được điền tự động với các trường cần thiết. Bạn có thể thêm hoặc xóa các trường như sau:
   1. Đi tới tab **Report fields** (Trường báo cáo). Danh sách các trường đã chọn sẽ hiển thị. Bạn không thể thay đổi lựa chọn các trường bắt buộc.
   2. Chọn hoặc xóa các trường chọn lọc theo yêu cầu.
   3. [Tùy chọn] Đặt **Thứ tự trường báo cáo (CSV)** để đặt trình tự các cột.
   4. [Tùy chọn] Nhấp **Restore defaults** (Khôi phục mặc định) nếu cần.
7. Nhấp vào **Create** (Tạo).
   * Trang **My reports** (Báo cáo của tôi) hiển thị. Ban đầu, trạng thái cho biết rằng báo cáo đang được tạo.
   * Thao tác tạo có thể kéo dài lên tới 10 phút.
   * Trong quá trình tạo báo cáo, bạn có thể tiếp tục làm việc, tạo báo cáo bổ sung hoặc điều hướng đến các trang khác.

</Accordion>

<div id="download-report" />

<Accordion title="Tải báo cáo xuống">

**Để tải xuống báo cáo**:

1. Xác minh rằng bạn đang ở trên trang **Raw Data Export** (Xuất dữ liệu thô). Nếu cần, hãy điều hướng đến **Reports** (Báo cáo) > **Raw Data Export** (Xuất dữ liệu thô).
2. Nhấp vào ![DownloadIcon.png](https://files.readme.io/6c00f4922fc3a835a856d7fdf527aa32d2f50570710c1527b039f43a7acbba79-41225791763217.png) (tải xuống), để tải xuống báo cáo. Báo cáo đã tạo có sẵn để tải xuống trong 7 ngày.

</Accordion>

<div id="duplicate-and-edit-report-settings" />

<Accordion title="Sao chép và chỉnh sửa cài đặt báo cáo">

**Để sao chép và chỉnh sửa cài đặt báo cáo:**

1. Xác minh rằng bạn đang ở trên trang **Raw Data Export** (Xuất dữ liệu thô).
2. Nhấp vào ![Duplicate.png](https://files.readme.io/f745081f1bf0c4f5861e275a29048fe84e8020f8b3bf4ebe4ad6a8d9254ab4b5-41225784681233.png), để sao chép cài đặt báo cáo rồi chỉnh sửa cài đặt.
3. Nhấp vào **Create** (Tạo). Báo cáo được tạo có sẵn trong 7 ngày.   
   * Trang **My reports** (Báo cáo của tôi) hiển thị. Ban đầu, trạng thái cho biết rằng báo cáo đang được tạo.
   * Thao tác tạo có thể kéo dài lên tới 10 phút.
   * Trong quá trình tạo báo cáo, bạn có thể tiếp tục làm việc, tạo báo cáo bổ sung hoặc điều hướng đến các trang khác.

</Accordion>

<div id="additional-information" />

## Thông tin bổ sung

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Lưu ý |
| --- | --- |
| Truy cập mạng quảng cáo | Có |
| Truy cập đại lý | Có |
| Tính minh bạch của đại lý | Có. Tuy nhiên, xin lưu ý rằng nếu bạn sử dụng cả bộ lọc đại lý và bộ lọc nguồn truyền thông, bộ lọc nguồn truyền thông không áp dụng cho các đại lý không minh bạch. Điều này có nghĩa là đối với các đại lý không minh bạch, tất cả dữ liệu đều được đưa vào; không chỉ dữ liệu từ các nguồn truyền thông được lọc. |
| Múi giờ cụ thể theo ứng dụng | Có |
| Tiền tệ dành riêng cho ứng dụng | Có |
| Điểm hạn chế | Tối đa 1 triệu bản ghi cho mỗi lượt tải xuống |
| Dữ liệu tự nhiên | Có sẵn |
| Dữ liệu không tự nhiên | Có sẵn |
| Tính cập nhật của dữ liệu | Phụ thuộc báo cáo |
| Dữ liệu lịch sử | 90 ngày trước |
| Quyền truy cập tài khoản của người dùng | Người dùng trong <Anchor target="_blank" href="/marketers/vi/docs/user-management">vai trò có quyền bắt buộc</Anchor> |
| Gửi email | Không được hỗ trợ |
| Phạm vi ngày cài đặt | Phạm vi ngày cài đặt phải sớm hơn phạm vi ngày hoạt động. |
| Báo cáo đăng lại dữ liệu thô | Các bài đăng lại được gửi cho đối tác do các sự kiện được phân bổ cho các đại lý không minh bạch không được bao gồm trong báo cáo Đăng lại dữ liệu thô của nhà quảng cáo. |

</Accordion>

<div id="field-sequence-templates" />

<Accordion title="Mẫu trình tự trường">

Cài đặt Thứ tự trường báo cáo cho phép bạn chỉ định chuỗi cột trong báo cáo và trong một số trường hợp gồm cả các trường.

| Cài đặt | Cho phép lựa chọn trường | Lưu ý |
| --- | --- | --- |
| <span id="default::b7bb6355"></span>Mặc định | Có | <ul><li>Các trường đã chọn được sắp xếp theo mẫu AppsFlyer.</li><li>Trong tương lai, trình tự sẽ được giữ nguyên. Các trường trong tương lai sẽ được nối vào bên phải của các trường hiện có.</li></ul> |
| <span id="alphabetical-az::b08af6b3"></span>Bảng chữ cái (A-Z) | Có | Các trường đã chọn được sắp xếp theo thứ tự bảng chữ cái. |
| <span id="alphabetical-za::f0b3beb8"></span>Bảng chữ cái (Z-A) | Có | Các trường đã chọn được sắp xếp theo thứ tự bảng chữ cái ngược |
| <span id="legacy::fb5fd8ec"></span>Kế thừa | Không | <ul><li>Các trường được sắp xếp theo trình tự các cột trong báo cáo được chuẩn bị bằng phiên bản trước của trang dữ liệu xuất.</li><li>Lựa chọn trường là cố định và không thể thay đổi.</li><li>Có một số biến thể của các báo cáo cho mỗi trường tùy thuộc vào báo cáo thực tế.</li></ul> |

[Trang tính](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) này chứa cả trang tính Mặc định và Kế thừa. Mỗi trang chứa danh sách thứ tự trường có liên quan.

**Để thay đổi thứ tự trường:**

1. Trong tab Report fields (Trường báo cáo), hãy chọn tùy chọn **Report field order** (Thứ tự trường báo cáo).
2. Nếu cần, hãy thay đổi các trường đã chọn bằng cách chọn hoặc xóa chọn các trường cần thiết.

</Accordion>

<div data-zendesk-anchors="h_01HA28AT6QRSG68NBFYHH5SQY8=raw-data-export-page-features-and-filter-options h_01HA28CJ4W692V6EVC7XTQEZG6=l%C6%B0u-%C3%BD procedures=quy-tr%C3%ACnh h_01HA28AT6Q9PV3M55C1YM3XN2E=quy-tr%C3%ACnh h_01HZY1HQ9AVH6Q9QAQB4SM1VPX=create-a-default-report h_01HZY1HQ9ACEMZ4N8WPYNHZQP7=create-a-custom-report h_01HA28AT6QV1XP4N952PAEGSSG=download-report h_01HA28AT6QFT88RHJ3M05MV3B3=duplicate-and-edit-report-settings additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HA28AT6Q4DXKCZ22R9XEN2RR=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HA28AT6Q6SE8CB3EEXFMAN0H=traits-and-limitations h_01HA28AT6RW8C99ZGEBTN5E44R=field-sequence-templates" />
