---
title: Trình tạo sự kiện trong ứng dụng
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-08T12:47:30Z'
  edited_at: '2023-11-09T05:06:53Z'
  id: 10457123447953
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/10457123447953
---
> **Khái quát:** Tự động tạo mã ứng dụng (Android và iOS gốc, Unity) để gửi các sự kiện trong ứng dụng bằng cách xác định tên và nội dung sự kiện theo nhu cầu kinh doanh của bạn.

## Giới thiệu

Sự kiện trong ứng dụng là công cụ chính để **chủ sở hữu ứng dụng đo lường chất lượng người dùng của họ đến từ các nguồn khác nhau** dựa trên hành động họ thực hiện sau khi cài đặt ứng dụng. Các sự kiện cũng thường được sử dụng để thực hiện các chiến dịch tiếp thị dựa trên CPA.

Tuy nhiên, việc xác định và tích hợp các sự kiện trong ứng dụng vào ứng dụng thường liên quan đến nhiều người. Mặc dù nhà tiếp thị/người quản lý sản phẩm xác định nội dung nhóm sự kiện theo nhu cầu kinh doanh, nhưng thường thì một hoặc nhiều nhà phát triển di động phải triển khai API sự kiện trong ứng dụng ở trong ứng dụng của họ.

<Anchor target="_blank" href="https://evgen.appsflyer.com/">Trình tạo sự kiện trong ứng dụng</Anchor> của AppsFlyer **giải quyết những thách thức cố hữu trong việc hợp tác thiết yếu giữa nhà tiếp thị và nhà phát triển này**.

Bằng cách sử dụng Trình tạo sự kiện trong ứng dụng, nhà tiếp thị có thể:

* Sử dụng **tập hợp các sự kiện** và thông số được đề xuất đã được xác định trước cho ngành dọc của họ.
* Thêm hoặc xóa các sự kiện/thông số, mô tả, trình kích hoạt và ví dụ đã được xác định trước hoặc tùy chỉnh để tham chiếu.
* **Gửi mã được tạo tự động** cho các nhà phát triển ứng dụng di động trên Android và iOS của họ – **rút ngắn số ngày làm việc,** những cuộc trao đổi liên lạc dư thừa và các lỗi tiềm ẩn.
* **Sử dụng lại sản phẩm của họ** nếu sau này họ cập nhật sự kiện, thêm sự kiện mới hoặc thêm ứng dụng mới.

## Sử dụng Trình tạo sự kiện trong ứng dụng

**Sử dụng Trình tạo sự kiện trong ứng dụng để tạo một nhóm sự kiện cho một ứng dụng mới hoặc để cập nhật một nhóm hiện có.**

### Tạo một nhóm sự kiện mới

**Để tạo một nhóm sự kiện mới:**

1. Chuyển đến <Anchor target="_blank" href="https://evgen.appsflyer.com/">Trình tạo sự kiện trong ứng dụng</Anchor> và nhập tên ứng dụng của bạn.
2. Chọn một ngành dọc hoặc nhập nhóm sự kiện của một ứng dụng tương tự đã được xuất trước đó sang tệp JSON.
3. Thêm hoặc xóa các sự kiện và thông số, theo nhu cầu kinh doanh của bạn.
4. Nhấp vào nút **`</>` Code** để xem và sao chép mã được tạo cho nhà phát triển của bạn: Java (Android gốc), Obj-C/Swift (iOS gốc) hoặc C# (Unity).
5. Nhấp vào **Download .zip** để lưu nhóm sự kiện nhằm sử dụng trong tương lai hoặc cộng tác với các nhà phát triển và đồng nghiệp.

### Cập nhật một nhóm sự kiện hiện có

**Để cập nhật một nhóm sự kiện hiện có:**

1. Chuyển đến <Anchor target="_blank" href="https://evgen.appsflyer.com/">Trình tạo sự kiện trong ứng dụng</Anchor>.
2. Nhập nhóm sự kiện của ứng dụng đã được xuất trước đây sang tệp JSON.
3. Thêm hoặc xóa các sự kiện và thông số, theo nhu cầu kinh doanh của bạn.
4. Nhấp vào nút **`</>` Code** để xem và sao chép mã được tạo cho nhà phát triển của bạn: Java (Android gốc), Obj-C/Swift (iOS gốc) hoặc C# (Unity).
5. Nhấp vào **Download .zip** để lưu nhóm sự kiện nhằm sử dụng trong tương lai hoặc cộng tác với các nhà phát triển và đồng nghiệp.

### Thêm sự kiện

**Để thêm một sự kiện mới vào nhóm sự kiện:**

1. Nhấp vào nút **+ Event**. Sự kiện mới sẽ xuất hiện ở cuối nhóm sự kiện.
2. Chọn một sự kiện **được xác định trước** từ danh sách sự kiện được đề xuất (được khuyến nghị) hoặc nhấp vào **Custom** để xác định tên sự kiện của riêng bạn. Xác minh rằng tên sự kiện chưa tồn tại trong nhóm sự kiện.
3. Nhập mục đích của sự kiện, mô tả tình huống kinh doanh.
4. Nhập hành động kích hoạt cho sự kiện, giải thích thời gian trong hành trình của người dùng mà sự kiện sẽ được gửi. Giải thích này được thêm vào dưới dạng nhận xét trong mã được tạo để các nhà phát triển tham khảo nhanh.
5. [Tùy chọn] Thêm một hoặc nhiều thông số vào sự kiện.

### Thêm thông số

**Để thêm một thông số mới vào nhóm sự kiện:**

1. Nhấp vào nút **+ Add parameter** cho sự kiện liên quan.
2. Chọn một thông số **được xác định trước** từ danh sách thông số được đề xuất (được khuyến nghị).
3. Nếu không, hãy nhấp vào **Custom** để xác định tên thông số của riêng bạn và nhấn **Enter**.
4. Nhập một hoặc nhiều giá trị thông số điển hình để tham khảo.
5. Để trợ giúp nhà phát triển của bạn, hãy nhập một mô tả chung, loại trường hoặc nguồn tương ứng cho giá trị thông số trong ứng dụng của bạn. Những nội dung này xuất hiện dưới dạng nhận xét cho từng thông số sự kiện trong mã được tạo.

**Lưu ý**: <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#predefined-and-custom-events">Đặt tên được xác định trước</Anchor> cho phép tự động ánh xạ các sự kiện và thông số tới các đối tác và là phương pháp nên thực hiện.

> 📄 **Xem thêm**
>
> * Bảng điều khiển sự kiện

<div data-zendesk-anchors="introduction=gi%E1%BB%9Bi-thi%E1%BB%87u h_01HE7T0ZA12E7KHS7WBQ757KF1=gi%E1%BB%9Bi-thi%E1%BB%87u using-the-inapp-event-generator=s%E1%BB%AD-d%E1%BB%A5ng-tr%C3%ACnh-t%E1%BA%A1o-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HE7T0ZA2A1KS4NF43GRZB87X=s%E1%BB%AD-d%E1%BB%A5ng-tr%C3%ACnh-t%E1%BA%A1o-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng creating-a-new-event-set=t%E1%BA%A1o-m%E1%BB%99t-nh%C3%B3m-s%E1%BB%B1-ki%E1%BB%87n-m%E1%BB%9Bi h_01HE7T0ZA2KQ44P40Y028VVA4K=t%E1%BA%A1o-m%E1%BB%99t-nh%C3%B3m-s%E1%BB%B1-ki%E1%BB%87n-m%E1%BB%9Bi updating-an-existing-event-set=c%E1%BA%ADp-nh%E1%BA%ADt-m%E1%BB%99t-nh%C3%B3m-s%E1%BB%B1-ki%E1%BB%87n-hi%E1%BB%87n-c%C3%B3 h_01HE7T0ZA2P2WZ07CT880ZSK0Z=c%E1%BA%ADp-nh%E1%BA%ADt-m%E1%BB%99t-nh%C3%B3m-s%E1%BB%B1-ki%E1%BB%87n-hi%E1%BB%87n-c%C3%B3 adding-events=th%C3%AAm-s%E1%BB%B1-ki%E1%BB%87n h_01HE7T0ZA2Z3D3J014E7E0T13X=th%C3%AAm-s%E1%BB%B1-ki%E1%BB%87n adding-parameters=th%C3%AAm-th%C3%B4ng-s%E1%BB%91 h_01HE7T0ZA2KAH7N44EQ9W5BH5G=th%C3%AAm-th%C3%B4ng-s%E1%BB%91 h_01HE7T4ZR4AY2J71B3PJKJP490=xem-th%C3%AAm" />
