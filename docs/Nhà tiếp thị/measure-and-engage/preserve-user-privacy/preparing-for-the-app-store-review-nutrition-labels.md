---
title: Chuẩn bị cho việc duyệt xét trên App Store—nhãn dinh dưỡng
metadata:
  keywords:
    - iOS
    - iTunes
    - Apple
    - IDFA
    - Guidelines
    - IFA
    - Ad Tracking
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-04-12T13:28:26Z'
  edited_at: '2023-11-09T05:06:58Z'
  id: 207032086
  locale: vi
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/vi/articles/207032086
---
> **Khái quát**: Kể từ phiên bản iOS 14, các Nhà phát triển ứng dụng phải cung cấp thông tin App Store liên quan đến Nguyên tắc quyền riêng tư của họ khi gửi ứng dụng. App Store sẽ đăng các nguyên tắc đó theo định dạng *nhãn dinh dưỡng.*

**Tuyên bố của luật sư chúng tôi:** *Không nội dung nào được nêu ở đây là thông tin tư vấn pháp lý. Những nội dung này chỉ nhằm cung cấp thông tin và sự tiện lợi cho bạn. Bạn nên hợp tác chặt chẽ với các cố vấn pháp lý và cố vấn chuyên môn khác để xác định chính xác cách thức mà các chính sách của Apple áp dụng đối với bạn.*

## Nhãn dinh dưỡng và duyệt xét trên App Store

* Để tạo nhãn quyền riêng tư, nhà phát triển ứng dụng phải trả lời bảng câu hỏi khi gửi ứng dụng của họ đến App Store Connect bao gồm các phần sau:
  * Các loại dữ liệu đã thu thập
  * [Mục đích thu thập dữ liệu](/docs/preparing-for-the-app-store-review-nutrition-labels#mục-đích-sử-dụng-dữ-liệu)
  * [Nếu loại dữ liệu có liên hệ với danh tính](/docs/preparing-for-the-app-store-review-nutrition-labels#dữ-liệu-liên-kết-với-danh-tính)
  * Nếu dữ liệu được sử dụng để theo dõi (kể cả liên quan đến bất kỳ dịch vụ hoặc SDK nào của bên thứ ba được có trong một ứng dụng).
* Nhà phát triển ứng dụng:
  * Có toàn quyền kiểm soát cách triển khai và cấu hình phần mềm AppsFlyer, dữ liệu nào cần thu thập và cách dữ liệu được sử dụng.
  * Có thể có nhiều câu trả lời rất khác nhau cho bảng câu hỏi dựa trên cách họ cấu hình phần mềm AppsFlyer và các điểm dữ liệu họ chọn để thu thập.
* Theo hiểu biết của AppsFlyer về chính sách của Apple, AppsFlyer không *theo dõi.* Tuy nhiên, các nhà phát triển Ứng dụng phải trả lời bảng câu hỏi phù hợp với mục đích sử dụng cụ thể và tích hợp đối tác của họ.
* Nếu bạn sử dụng dữ liệu đã thu thập cho mục đích theo dõi, bạn phải triển khai lời nhắc ATT.
* Phần sau giả định cấu hình mặc định của phần mềm AppsFlyer. Các nhà phát triển ứng dụng chịu trách nhiệm đảm bảo các ứng dụng điều chỉnh phù hợp với cấu hình và mục đích sử dụng cụ thể của họ.

#### Các loại dữ liệu đã thu thập

| **Loại dữ liệu** | **Thu thập dữ liệu AppsFlyer** | **Nhận xét** |
| --- | --- | --- |
| **Thông tin liên lạc**<ul><li>Tên</li><li>Địa chỉ email (bao gồm dạng đã băm)</li><li>Số điện thoại (bao gồm dạng đã băm)</li><li>Địa chỉ vật lý</li><li>Thông tin liên hệ của người dùng khác</li></ul> | Không | Không nên thu thập thông tin liên lạc. Tuy nhiên, nếu bạn đã cấu hình ứng dụng của mình để truyền email hoặc số điện thoại đã băm, hãy trả lời tương ứng trong bảng câu hỏi của App Store. |
| **Thể chất** | Không | Không thu thập |
| **Thông tin tài chính**<ul><li>Thông tin Thanh toán</li><li>Thông tin tín dụng</li><li>Thông tin tài chính khác</li></ul> | Không | Không thu thập |
| **Thông tin vị trí**<ul><li>Vị trí chính xác</li><li>Vị trí tương đối</li></ul> | Xem nhận xét | <ul><li>Vị trí chính xác: Không</li><li>Vị trí tương đối: Có. Hệ thống đã lấy và ánh xạ địa chỉ IP tới vị trí địa lý tương đối.</li></ul> |
| **Thông tin nhạy cảm** | Không | Không thu thập |
| **Thông tin liên lạc** | Không | Không thu thập |
| **Nội dung của người dùng**<ul><li>Email hoặc tin nhắn văn bản</li><li>Ảnh hoặc video</li><li>Dữ liệu âm thanh</li></ul> | Không | Không thu thập |
| **Lịch sử duyệt web** | Không | Không thu thập |
| **Lịch sử tìm kiếm** | Không | Không thu thập |
| **Mã định danh**<ul><li>ID người dùng</li><li>ID thiết bị (IDFA)</li></ul> | Tùy chọn | <ul><li>ID người dùng: Nhà phát triển ứng dụng có thể đặt và truyền ID người dùng (CUID)</li><li>ID thiết bị: ID Quảng cáo (IDFA) chỉ được thu thập khi có thể truy cập được.</li></ul> |
| **Mua hàng**<ul><li>Lịch sử mua hàng</li></ul> | Tùy chọn | Các nhà phát triển ứng dụng có thể chọn định cấu hình các sự kiện mua hàng trong ứng dụng nhất định để đo lường. |
| **Dữ liệu sử dụng**<ul><li>Tương tác sản phẩm</li><li>Dữ liệu quảng cáo</li><li>Dữ liệu sử dụng khác</li></ul> | <ul><li>Có</li><li>Tùy chọn</li><li>Không</li></ul> | <ul><li>Tương tác với sản phẩm: Số lần khởi chạy ứng dụng được đo lường, cũng như mọi tương tác khác của người dùng do nhà phát triển ứng dụng cấu hình.</li><li>Dữ liệu quảng cáo: được nhận nếu nhà phát triển ứng dụng sử dụng mô-đun doanh thu quảng cáo AppsFlyer.</li></ul> |
| **Dữ liệu chẩn đoán**<ul><li>Dữ liệu sự cố</li><li>Dữ liệu hiệu suất</li><li>Dữ liệu chẩn đoán khác</li></ul> | <ul><li>Không</li><li>Có</li><li>Không</li></ul> | Có thể nhận thông tin thời gian khởi động và/hoặc mức pin để phát hiện gian lận. |
| **Dữ liệu khác**<ul><li>Các loại dữ liệu khác</li><li>IDFV</li></ul> | Có | <ul><li>Thông tin thiết bị kỹ thuật (ví dụ: hệ điều hành, loại thiết bị, ngôn ngữ, kích thước màn hình, v.v.) hoặc thông tin mạng (ví dụ: địa chỉ IP, tác nhân người dùng HTTP) được AppsFlyer nhận.</li><li>AppsFlyer áp dụng ID cài đặt cho mỗi lượt cài đặt ứng dụng được gọi là ID AF.</li><li>IDFV được thu thập</li></ul> |

### Mục đích sử dụng dữ liệu

Apple có một danh sách các mục đích mà các nhà phát triển ứng dụng phải chọn, như được nêu chi tiết trong bảng sau. Bạn phải xác định các mục đích liên quan cho từng loại dữ liệu liên quan đến mục đích sử dụng cụ thể của mình.

| Mục đích của dữ liệu | Lựa chọn dựa trên cách sử dụng dữ liệu lấy từ AppsFlyer |
| --- | --- |
| Quảng cáo của bên thứ ba | Chọn nếu bạn chia sẻ loại dữ liệu với bên thứ ba nhằm mục đích hiển thị quảng cáo của bên thứ ba trong ứng dụng của bạn. |
| Quảng cáo hoặc tiếp thị của nhà phát triển | Chọn nếu bạn sử dụng để hiển thị quảng cáo của bên thứ nhất trong ứng dụng của mình (bao gồm cả việc chia sẻ với bên thứ ba để hiển thị quảng cáo của bạn) hoặc cho các mục đích tiếp thị khác. |
| Phân tích | Có |
| Cá nhân hóa sản phẩm | Chọn nếu bạn sử dụng dữ liệu cho bất kỳ mục đích cá nhân hóa sản phẩm nào. |
| Chức năng ứng dụng | Có |
| Các mục đích khác | Chọn nếu bạn sử dụng dữ liệu cho bất kỳ mục đích nào khác không được đề cập. |

### Dữ liệu liên kết với danh tính

Các loại dữ liệu được thu thập thông qua AppsFlyer thường được liên kết với một mã định danh như ID thiết bị (nếu có) hoặc các mã định danh khác như ID do khách hàng cấp khi được cấu hình.

Do đó, các nhà phát triển ứng dụng nên chọn **Yes** (Có) khi được hỏi liệu dữ liệu có được liên kết với danh tính hay không.

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/">Chính sách Quyền riêng tư về Dịch vụ của AppsFlyer</Anchor>: Cách AppsFlyer xử lý và sử dụng dữ liệu.
> * <Anchor target="_blank" href="https://developer.apple.com/app-store/app-privacy-details/">Chi tiết về quyền riêng tư của ứng dụng trên App Store của Apple</Anchor>.

<div data-zendesk-anchors="nutrition-labels-and-the-app-store-review=nh%C3%A3n-dinh-d%C6%B0%E1%BB%A1ng-v%C3%A0-duy%E1%BB%87t-x%C3%A9t-tr%C3%AAn-app-store h_01HE7T7J409620K5KX5XKPEQVZ=nh%C3%A3n-dinh-d%C6%B0%E1%BB%A1ng-v%C3%A0-duy%E1%BB%87t-x%C3%A9t-tr%C3%AAn-app-store data-types-collected=c%C3%A1c-lo%E1%BA%A1i-d%E1%BB%AF-li%E1%BB%87u-%C4%91%C3%A3-thu-th%E1%BA%ADp h_01HE7T7J4004XVJTMF6S964DVB=c%C3%A1c-lo%E1%BA%A1i-d%E1%BB%AF-li%E1%BB%87u-%C4%91%C3%A3-thu-th%E1%BA%ADp data-use-purposes=m%E1%BB%A5c-%C4%91%C3%ADch-s%E1%BB%AD-d%E1%BB%A5ng-d%E1%BB%AF-li%E1%BB%87u h_01HE7T7J4098NNW8D0BCD3EFBJ=m%E1%BB%A5c-%C4%91%C3%ADch-s%E1%BB%AD-d%E1%BB%A5ng-d%E1%BB%AF-li%E1%BB%87u data-linked-to-an-identity=d%E1%BB%AF-li%E1%BB%87u-li%C3%AAn-k%E1%BA%BFt-v%E1%BB%9Bi-danh-t%C3%ADnh h_01HE7T7J41BJG9GTBWMVKG7031=d%E1%BB%AF-li%E1%BB%87u-li%C3%AAn-k%E1%BA%BFt-v%E1%BB%9Bi-danh-t%C3%ADnh h_01HE7TES34MEF1XR4B6BDEMJW4=xem-th%C3%AAm" />
