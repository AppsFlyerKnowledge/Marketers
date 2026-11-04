---
title: Liên kết Hàng loạt
metadata:
  keywords:
    - Marketers
    - bulk
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2023-04-13T11:31:43Z'
  edited_at: '2023-12-27T02:41:07Z'
  id: 14511403892369
  locale: vi
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/vi/articles/14511403892369
---
> **Tổng quan:** Trang liên kết hàng loạt OneLink cho phép bạn tạo ngay một số lượng lớn các liên kết tùy chỉnh OneLink và xem chúng ở một vị trí để sử dụng trong tương lai.

Liên kết hàng loạt cho phép bạn tạo và xem các liên kết được tạo hàng loạt. Các liên kết hàng loạt này được nhóm theo định dạng tập hợp thuận tiện cho phép bạn thực hiện các hành động trên toàn bộ tập hợp, chẳng hạn như thêm liên kết mới hoặc tải chúng xuống.

<div id="getting-started" />

## Bắt đầu

1. Trong AppsFlyer, đi tới **Experiences & Deep Linking** > **OneLink Bulk links**.
2. Bạn sẽ thấy một trang giới thiệu với một trong các nút sau:
   1. **Get Started** - (gửi để tạo tập hợp đầu tiên của bạn).
   2. **Create a OneLink template** - Cần có mẫu OneLink để tạo tập hợp. Xem <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template">các mẫu OneLink</Anchor>.
   3. **Upgrade** -  Liên kết hàng loạt không khả dụng với gói hiện tại của bạn. Liên hệ với CSM của bạn hoặc gửi thư đến [hello@appsflyer.com](mailto:hello@appsflyer.com) về việc nâng cấp gói của bạn.

<div id="creating-your-first-collection" />

## Tạo tập hợp đầu tiên của bạn

1. Nhấp vào **Get started.**
2. Nhập tên cho tập hợp của bạn.  
   Chọn tên phản ánh mục đích của tập hợp để bạn có thể dễ dàng xác định được nó sau này.
3. Chọn một mẫu OneLink  Lưu ý: tất cả các liên kết của tập hợp sẽ dựa trên mẫu này
4. Nhấp vào **Save & continue.**
5. Tải lên tệp CSV của bạn. Bạn có thể sử dụng <Anchor target="_blank" href="https://cdn.appsflyer.com/onelink-bulk-links-mgmt/sample_file.csv">Mẫu CSV</Anchor> sau làm hướng dẫn.  
   Xem [Định dạng tải lên](/docs/perform-onelink-bulk-actions-via-csv#upload-format) để đảm bảo CSV của bạn tương thích và tải lên thành công. Khi tệp CSV được tải lên, tệp sẽ được xác thực. Nếu có hàng không hợp lệ, CSV báo cáo tính hợp lệ sẽ có sẵn để tải xuống nhằm giúp khắc phục tệp của bạn. Làm theo hướng dẫn trong UI và tải tệp đã sửa lên.
6. Nhấp vào **Create collection.**

## Quản lý liên kết hàng loạt của bạn bằng các tập hợp

Liên kết hàng loạt được quản lý trong các tập hợp.

* Ở đầu trang, tiện ích **Sử dụng liên kết hàng loạt trong tháng này** hiển thị số lượng yêu cầu liên kết (bao gồm tạo và cập nhật liên kết) ngoài hạn mức hàng tháng cho tháng hiện tại.
  * Hiện tại, giới hạn mặc định là 20.000 lượt tạo liên kết mỗi tháng
* Phần **Collections** cho phép bạn tạo một tập hợp mới và thực hiện các hành động khác đối với các tập hợp liên kết hiện tại của bạn.
* Nếu có nhiều hơn bảy tập hợp, bạn có thể tìm kiếm và lọc danh sách tập hợp của mình.

<div id="other-actions" />

## Các hành động khác

Sau đây là các hành động khác có thể được thực hiện trên một tập hợp:

<div id="creating-a-new-collection" />

<Accordion title="Tạo tập hợp mới">

Có thể tạo tập hợp mới khi [mức sử dụng hàng tháng](/docs/perform-onelink-bulk-actions-via-csv#quản-lý-liên-kết-hàng-loạt-của-bạn-bằng-các-tập-hợp) không vượt quá hạn mức.

1. Nhấp vào **New collection**.
2. Làm theo chỉ dẫn.
   1. Quá trình này tuân theo các bước tương tự như [Tạo tập hợp đầu tiên của bạn](/docs/perform-onelink-bulk-actions-via-csv#tạo-tập-hợp-đầu-tiên-của-bạn).

</Accordion>

<div id="downloading-a-collection" />

<Accordion title="Tải xuống một tập hợp">

Tùy chọn tải xuống tập hợp khả dụng khi:

* Có các liên kết hoạt động trong tập hợp đó.
* Bạn có quyền truy cập ứng dụng vào ít nhất một trong các ứng dụng dành cho thiết bị di động của mẫu OneLink liên quan đến tập hợp.

Để Tải xuống tập hợp:

1. Nhấp vào biểu tượng tải xuống trên hàng tập hợp.
2. Chọn miền cho đầu ra URL rút gọn.
3. Nhấp vào **Download**.

> 🚧 **Quan trọng!**
>
> AppsFlyer đề nghị bạn nên sử dụng Miền có Gắn thương hiệu vì chúng có thể cải thiện hiệu suất chiến dịch bằng cách thúc đẩy niềm tin và nâng cao nhận thức thương hiệu. <Anchor target="_blank" href="/marketers/vi/docs/brand-onelink-with-your-domain">Tìm hiểu thêm tại đây.</Anchor>

</Accordion>

<div id="adding-links-to-a-collection" />

<Accordion title="Thêm liên kết vào tập hợp">

Tùy chọn thêm liên kết khả dụng khi:

* Bạn có quyền truy cập ứng dụng vào ít nhất một trong các ứng dụng dành cho thiết bị di động của mẫu OneLink liên quan đến tập hợp.
* Có dưới 2000 liên kết hoạt động trong tập hợp.
* [Mức sử dụng hàng tháng](/docs/perform-onelink-bulk-actions-via-csv#quản-lý-liên-kết-hàng-loạt-của-bạn-bằng-các-tập-hợp) không bị vượt quá.

Để thêm liên kết vào tập hợp, hãy nhấp vào **menu options** > **Add links to collection.**

* Các liên kết sẽ được thêm vào bằng cách sử dụng phương thức tương tự như được mô tả trong phần [Tạo tập hợp đầu tiên của bạn](/docs/perform-onelink-bulk-actions-via-csv#tạo-tập-hợp-đầu-tiên-của-bạn) từ điểm 5 trở đi.

</Accordion>

<div id="editing-links-in-a-collection" />

<Accordion title="Chỉnh sửa liên kết trong tập hợp">

Tùy chọn chỉnh sửa liên kết khả dụng khi:

* Có các liên kết hoạt động trong tập hợp đó.
* Bạn có quyền truy cập ứng dụng vào ít nhất một trong các ứng dụng dành cho thiết bị di động của mẫu OneLink liên quan đến tập hợp.
* [Mức sử dụng hàng tháng](/docs/perform-onelink-bulk-actions-via-csv#quản-lý-liên-kết-hàng-loạt-của-bạn-bằng-các-tập-hợp) chưa được vượt quá.

**Để chỉnh sửa liên kết trong tập hợp:**

1. Nhấp vào **menu options** > **Edit links**.
2. Tải xuống CSV cơ sở tập hợp. Tệp này chứa tất cả các liên kết trong tập hợp mà bạn có thể chỉnh sửa.
3. Thực hiện theo các hướng dẫn trong bước đầu tiên để chỉnh sửa các thông số liên kết. Đối với bất kỳ liên kết nào bạn muốn cập nhật, hãy đảm bảo rằng tùy chọn **Đánh dấu cập nhật** được đặt thành **true**.
4. Nhấp vào **Next** (Tiếp theo).
5. Tải lên CSV đã chỉnh sửa của bạn. Xem [Định dạng tải lên](/docs/perform-onelink-bulk-actions-via-csv#upload-format) để đảm bảo CSV của bạn tương thích và tải lên thành công.
   * Sau khi tệp CSV được tải lên, tệp sẽ được xác thực.
   * Nếu có hàng không hợp lệ, CSV báo cáo tính hợp lệ sẽ có sẵn để tải xuống nhằm giúp khắc phục tệp của bạn. Làm theo hướng dẫn trong UI và tải lên tệp đã sửa.
6. Nhấp vào **Update links**.

</Accordion>

<div id="viewing-the-collection-history" />

<Accordion title="Xem lịch sử của tập hợp">

Để xem lịch sử của một tập hợp, hãy nhấp vào **menu options** > **View collection history.**

Cửa sổ lịch sử sẽ hiển thị cho bạn các hành động sau đây cũng như ngày giờ hành động được thực hiện và người đã thực hiện hành động:

* **Name changes:** Thay đổi tên của tập hợp.
* **Links added:** Khi liên kết đã được thêm vào tập hợp.
* **Links updated**: Khi các liên kết trong tập hợp được chỉnh sửa và cập nhật.
* **Collection** **created**: Khi tập hợp được tạo.

<span id="page-components"></span>**Các liên kết được thêm và cập nhật** cũng cho bạn biết các thay đổi đã ảnh hưởng đến [mức sử dụng](/docs/perform-onelink-bulk-actions-via-csv#quản-lý-liên-kết-hàng-loạt-của-bạn-bằng-các-tập-hợp) của bạn như thế nào đồng thời cho phép bạn tải xuống báo cáo hành động về thay đổi đó.

* * Bạn chỉ có thể tải xuống báo cáo hành động nếu bạn có quyền truy cập ứng dụng vào ít nhất một trong các ứng dụng dành cho thiết bị di động của mẫu OneLink liên quan đến tập hợp.

</Accordion>

<div id="editing-the-collection-name" />

<Accordion title="Chỉnh sửa tên tập hợp">

Tùy chọn chỉnh sửa tên tập hợp khả dụng khi:

* Bạn có quyền truy cập ứng dụng vào ít nhất một trong các ứng dụng dành cho thiết bị di động của mẫu OneLink liên quan đến tập hợp.

Để chỉnh sửa tên tập hợp:

1. Di chuột qua tên tập hợp mà bạn muốn thay đổi.
2. Nhấp vào biểu tượng chỉnh sửa bên cạnh tên tập hợp.
3. Sau khi bạn đã chỉnh sửa tên, hãy nhấp vào enter hoặc nhấp vào bất kỳ nơi nào khác trên màn hình.

</Accordion>

<div id="deleting-empty-collections" />

<Accordion title="Xóa các tập hợp trống">

Nếu một tập hợp trống và bạn có quyền truy cập ứng dụng vào ít nhất một trong các ứng dụng dành cho thiết bị di động của mẫu OneLink liên quan đến tập hợp đó, thì bạn có thể xóa tập hợp đó bằng cách nhấp vào **menu options -> Delete collection**.

Tập hợp có thể trống do:

* <Anchor target="_blank" href="/marketers/vi/docs/bulletin-onelink-short-url-ttls-automatically-extend">TTL (thời gian tồn tại)</Anchor> của tất cả các liên kết trong tập hợp đã hết hạn.
* Quá trình tạo tập hợp mới đã bị hủy bỏ hoặc không thể hoàn thành trước khi liên kết được tạo. Trường hợp này sẽ tạo ra một tập hợp trống.

</Accordion>

<div id="general-information" />

## Thông tin chung

> 📘 **Lưu ý**
>
> Các liên kết hàng loạt được tạo trước tháng 4 năm 2023 sẽ không hiển thị hoặc không được quản lý trên trang liên kết hàng loạt.

<div id="upload-format" />

<Accordion title="Định dạng tải lên">

Để đảm bảo tệp CSV của bạn tải lên không có bất kỳ lỗi nào, hãy đảm bảo rằng tệp của bạn đáp ứng các tiêu chuẩn sau.

* Tệp phải ở định dạng CSV
* Tệp không thể lớn hơn 4 MB
* Tệp chỉ nên chứa nội dung cho các liên kết bạn đang tạo/cập nhật
* Mỗi liên kết nên ở trong hàng riêng của chúng
* Mỗi cột đại diện cho một thông số
  * Tối đa 35 cột thông số
* Chỉ chấp nhận mã hóa ký tự UTF-8
* Tối đa 2000 liên kết cho mỗi tập hợp

</Accordion>

<div id="csv-parameters" />

<Accordion title="Thông số CSV">

* Thông số trong CSV có thể là bất kỳ thông số nào được chấp nhận trong liên kết AppsFlyer. Đó có thể là thông số dành riêng cho việc phân bổ (ví dụ: c, af\_channel, af\_adset, v.v.), để chuyển hướng và liên kết sâu (ví dụ: af\_ios\_url, af\_dp, deep\_link\_value, v.v.) hoặc thông số tùy chỉnh.
* Thông số nguồn truyền thông (pid) là bắt buộc.
* Các đại lý cần thêm thông số `af_prt` vào liên kết của họ theo cách thủ công.
* Ngay cả khi lược đồ URI được thiết lập trong mẫu OneLink, đối với các liên kết được tạo hàng loạt, thông số af\_dp với lược đồ URI phải được chỉ định trong tệp CSV của bạn.

</Accordion>

<div data-zendesk-anchors="getting-started=b%E1%BA%AFt-%C4%91%E1%BA%A7u h_01HJJRRJCD2F57FE0A4Z5BCMTE=b%E1%BA%AFt-%C4%91%E1%BA%A7u creating-your-first-collection=t%E1%BA%A1o-t%E1%BA%ADp-h%E1%BB%A3p-%C4%91%E1%BA%A7u-ti%C3%AAn-c%E1%BB%A7a-b%E1%BA%A1n h_01HJJRRJCDSTTR2FQ53J86RGSJ=t%E1%BA%A1o-t%E1%BA%ADp-h%E1%BB%A3p-%C4%91%E1%BA%A7u-ti%C3%AAn-c%E1%BB%A7a-b%E1%BA%A1n collection-features=qu%E1%BA%A3n-l%C3%BD-li%C3%AAn-k%E1%BA%BFt-h%C3%A0ng-lo%E1%BA%A1t-c%E1%BB%A7a-b%E1%BA%A1n-b%E1%BA%B1ng-c%C3%A1c-t%E1%BA%ADp-h%E1%BB%A3p h_01HJJRRJCDCF830CCFCV3HQSJY=qu%E1%BA%A3n-l%C3%BD-li%C3%AAn-k%E1%BA%BFt-h%C3%A0ng-lo%E1%BA%A1t-c%E1%BB%A7a-b%E1%BA%A1n-b%E1%BA%B1ng-c%C3%A1c-t%E1%BA%ADp-h%E1%BB%A3p other-actions=c%C3%A1c-h%C3%A0nh-%C4%91%E1%BB%99ng-kh%C3%A1c h_01HJJRRJCD2XE454G11WMY5AK9=c%C3%A1c-h%C3%A0nh-%C4%91%E1%BB%99ng-kh%C3%A1c h_01HJJRRJCDZVFG9STE7PA38D4D=creating-a-new-collection h_01HJJRRJCDHMCWFBVRHYBS1D1N=downloading-a-collection h_01HJJRRJCDJ1201WPSMPMAJ6Q9=quan-tr%E1%BB%8Dng h_01HJJRRJCDPRV1DVSAGQRD4ANG=adding-links-to-a-collection h_01HJJRRJCDW88HYY4W7M2W5BD8=editing-links-in-a-collection h_01HJJRRJCDANN18DS1CEZS8001=viewing-the-collection-history h_01HJJRRJCDKAVCD4M8R187XER9=editing-the-collection-name h_01HJJRRJCD47RM4VYGN8TRJPHJ=deleting-empty-collections general-information=th%C3%B4ng-tin-chung h_01HJJRRJCDR7MA544ZX324B4Y2=th%C3%B4ng-tin-chung h_01HJJRRJCD2CHGKVSG22TKFMM9=l%C6%B0u-%C3%BD h_01HJJRRJCDCZ0ZBPZ2AH77JJTJ=upload-format h_01HJJRRJCDN5MWX72S9P37E69N=csv-parameters" />
