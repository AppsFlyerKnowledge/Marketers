---
title: Biểu mẫu mục an toàn của Google
metadata:
  keywords:
    - Google Play
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-19T15:00:21Z'
  edited_at: '2023-11-01T10:22:05Z'
  id: 4417197430289
  locale: vi
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/vi/articles/4417197430289
---
> **Khái quát**: Kể từ tháng 4 năm 2022, nhà phát triển ứng dụng cần phải hoàn thành biểu mẫu mục An toàn dữ liệu của Google Play và đăng liên kết đến chính sách quyền riêng tư, ngay cả khi họ không thu thập bất kỳ loại dữ liệu nào do Google chỉ định. Trang này nhằm cung cấp thông tin để hỗ trợ bạn việc trả lời Bảng câu hỏi An toàn của Google, chỉ liên quan đến những gì AppsFlyer xử lý thay mặt khách hàng.

Khách hàng cần hợp tác chặt chẽ với các cố vấn pháp lý và chuyên gia khác để xác định chính xác cách các chính sách Google sẽ được áp dụng với họ và nên điều chỉnh câu trả lời của họ phù hợp với cấu hình và mục đích sử dụng cụ thể của họ.

#### **Tuyên bố từ chối trách nhiệm**

Thông tin trong bài viết này nhằm mục đích hỗ trợ trả lời Bảng câu hỏi Mục An toàn của Google **chỉ** liên quan đến những gì AppsFlyer xử lý thay mặt khách hàng.

Bài viết chỉ nhằm mục đích cung cấp thông tin và tăng tính thuận tiện. Khách hàng cần hợp tác chặt chẽ với các cố vấn pháp lý và chuyên gia khác để xác định chính xác cách các chính sách Google sẽ được áp dụng với họ và nên điều chỉnh câu trả lời của họ phù hợp với cấu hình và mục đích sử dụng cụ thể của họ.

## Giới thiệu

Kể từ tháng 4 năm 2022, nhà phát triển ứng dụng cần phải cung cấp thông tin liên quan đến các phương thức bảo vệ quyền riêng tư của họ thông qua mục an toàn riêng của Google. Cụ thể, nhà phát triển ứng dụng sẽ cần cung cấp thông tin chi tiết về dữ liệu họ thu thập, cách xử lý và chia sẻ dữ liệu đó, bao gồm cả việc họ sử dụng bất kỳ SDK bên thứ ba nào.

Thông tin do mỗi ứng dụng cung cấp sẽ được hiển thị trong trang thông tin cửa hàng Google, giúp người dùng cuối hiểu rõ hơn về các phương thức bảo vệ quyền riêng tư của ứng dụng.

## Đối tượng

Tất cả các nhà phát triển ứng dụng sẽ cần phải hoàn thành bảng câu hỏi mục an toàn và đăng liên kết đến chính sách quyền riêng tư ngay cả khi họ không thu thập bất kỳ loại dữ liệu nào do Google chỉ định.

## Biểu mẫu an toàn của Google (bảng câu hỏi)

Google đã đăng một biểu mẫu (bảng câu hỏi) mà các nhà phát triển ứng dụng cần phải hoàn thành. Bảng câu hỏi bao gồm các mục sau:

* Thu thập và bảo mật dữ liệu
* Loại dữ liệu
* Sử dụng và xử lý dữ liệu

Trước tiên, các nhà phát triển ứng dụng sẽ cần đánh giá các phương thức thu thập và xử lý dữ liệu của họ trước khi trả lời bảng câu hỏi.

Liên quan đến việc sử dụng AppsFlyer, các nhà phát triển ứng dụng được nhắc rằng họ có toàn quyền kiểm soát cách họ triển khai và cấu hình AppsFlyer, bao gồm cả dữ liệu được thu thập và cách sử dụng dữ liệu đó. Do đó, mỗi nhà phát triển ứng dụng sẽ có thể có các câu trả lời khác nhau cho bảng câu hỏi dựa trên phương thức của họ đối với dữ liệu và cách họ sử dụng AppsFlyer.

Các nhà phát triển ứng dụng phải trả lời bảng câu hỏi tùy theo các trường hợp sử dụng, cấu hình và tích hợp đối tác cụ thể của họ.

### Thu thập và bảo mật dữ liệu

Trong mục này, sẽ có một số câu hỏi có/không chung chung:

1. Ứng dụng của bạn có thu thập hoặc chia sẻ bất kỳ loại dữ liệu bắt buộc nào không?
2. Tất cả các dữ liệu người dùng mà ứng dụng của bạn thu thập có được mã hóa khi chuyển tiếp không?
3. Bạn có nêu rõ cách để người dùng yêu cầu xóa dữ liệu của họ không?

Đối với việc bạn sử dụng AppsFlyer, AppsFlyer mã hóa tất cả dữ liệu trong quá trình chuyển tiếp được truyền qua SDK. AppsFlyer cũng cho phép khách hàng xóa dữ liệu người dùng cuối cụ thể thông qua khung OpenGDPR của mình. Đối với các loại dữ liệu được thu thập, hãy xem bảng trong mục [Loại dữ liệu](/docs/fill-out-google-safety-section-form#loại-dữ-liệu).

### Loại dữ liệu

Trong mục này, bạn sẽ được yêu cầu chọn các loại dữ liệu thu thập và trả lời những thông tin sau:

1. Dữ liệu được chia sẻ không
2. Dữ liệu có được xử lý ngắn hạn không
3. Dữ liệu có bắt buộc không hay người dùng cuối có thể lựa chọn không tham gia
4. Mục đích

Bảng sau giả định cấu hình mặc định của phần mềm AppsFlyer. Các nhà phát triển ứng dụng chịu trách nhiệm đảm bảo điều chỉnh phù hợp với cấu hình và mục đích sử dụng cụ thể của họ.

“Được thu thập” nghĩa là dữ liệu được truyền ra ngoài thiết bị bằng bất kỳ cách thức nào (ví dụ: chế độ xem web hoặc SDK).  Một trường hợp ngoại lệ là, nếu có sử dụng phương thức mã hóa đầu cuối thì không ai có thể đọc được dữ liệu.

| Loại dữ liệu | Thu thập dữ liệu mặc định của AppsFlyer | Lưu ý |
| --- | --- | --- |
| Thông tin Vị trí<ul><li>Vị trí Ước chừng</li><li>Vị trí Chính xác</li></ul> | Xem ghi chú | Vị trí Chính xác: Không<br /><br />Vị trí Ước chừng: Có, địa chỉ IP được ánh xạ tới cấp khu vực/thành phố. |
| Thông tin Cá nhân<ul><li>Tên</li><li>Địa chỉ Email</li><li>Mã định danh cá nhân (ID tài khoản, mã số hoặc tên)</li><li>Địa chỉ</li><li>Số Điện thoại</li><li>Chủng tộc và dân tộc</li><li>Chính trị hoặc tôn giáo</li><li>Xu hướng tình dục hoặc bản dạng giới</li><li>Thông tin cá nhân khác</li></ul> | Xem ghi chú | Không nên thu thập thông tin cá nhân, và AppsFlyer hạn chế việc thu thập các dữ liệu cá nhân đó như tên và địa chỉ. Tuy nhiên, nếu các nhà phát triển ứng dụng đã cấu hình để truyền email hoặc số điện thoại đã băm hoặc họ đã cấu hình ID tài khoản người dùng của khách hàng (CUID) thì họ sẽ cần trả lời tương ứng theo. |
| Thông tin Tài chính<ul><li>Số thẻ tín dụng, thẻ ghi nợ hoặc số tài khoản ngân hàng</li><li>Lịch sử mua hàng</li><li>Thông tin tín dụng</li><li>Thông tin tài chính khác</li></ul> | Không  <br />  <br />Không bắt buộc<br /><br />Không  <br />Không | Không nên thu thập thông tin tài chính như thẻ tín dụng và thông tin tín dụng.<br /><br />Nếu đang đo lường các giao dịch mua hàng trong ứng dụng (lịch sử mua hàng), bạn nên trả lời **Có** |
| Sức khỏe và Thể dục<ul><li>Thông tin sức khỏe</li><li>Thông tin thể dục</li></ul> | Không | Không nên được thu thập |
| Tin nhắn<ul><li>Email</li><li>Tin nhắn SMS hoặc MMS</li><li>Các tin nhắn trong ứng dụng khác</li></ul> | Không | Không nên được thu thập |
| Ảnh hoặc Video<ul><li>Ảnh</li><li>Video</li></ul> | Không | Không nên được thu thập |
| Tệp tin Âm thanh<ul><li>Bản ghi âm giọng nói hoặc âm thanh</li><li>Tệp tin âm nhạc</li><li>Các tệp tin âm thanh khác</li></ul> | Không | Không nên được thu thập |
| Lịch<ul><li>Sự kiện trong lịch</li></ul> | Không | Không nên được thu thập |
| Hoạt động trong ứng dụng<ul><li>Số lượt xem trang và lần nhấn trong ứng dụng</li><li>Lịch sử tìm kiếm trong ứng dụng</li><li>Ứng dụng đã cài đặt</li><li>Nội dung khác do người dùng tạo</li><li>Các hành động khác</li></ul> | Xem ghi chú | Theo mặc định, AppsFlyer đo lường các lượt khởi chạy ứng dụng, đó có thể được coi là lượt xem trang hoặc các hành động khác.<br /><br />Hơn nữa, nếu bạn cấu hình ứng dụng để đo lường các sự kiện trong ứng dụng cụ thể, bạn nên trả lời Có theo cấu hình bạn đã cài đặt. |
| Duyệt web | Không | Không nên được thu thập |
| Thông tin ứng dụng và hiệu suất<ul><li>Nhật ký sự cố</li><li>Chẩn đoán</li><li>Dữ liệu khác về hiệu suất của ứng dụng</li></ul> | Không<br /><br />Có<br /><br />Có | Có thể nhận số lần khởi chạy hoặc mức pin cho mục đích phát hiện gian lận |
| Thiết bị hoặc các mã định danh khác<ul><li>Thiết bị hoặc các mã định danh khác (ví dụ: IMEI, MAC và ID Quảng cáo)</li></ul> | Tùy chọn | ID Quảng cáo được thu thập khi có thể truy cập được |

## Chia sẻ dữ liệu

“Được chia sẻ” có nghĩa là việc chuyển dữ liệu cho bên thứ ba (dù chuyển ra ngoài hay trên thiết bị).

Các trường hợp ngoại lệ bao gồm:

* Trường hợp chuyển cho các nhà cung cấp dịch vụ xử lý dữ liệu thay mặt bạn và theo chỉ thị của bạn
* Trường hợp chuyển do cần thiết để phục vụ mục đích pháp lý (ví dụ: theo yêu cầu của chính phủ)
* Hành động của người dùng cuối hoặc dựa trên quyết định đồng ý và tiết lộ trong ứng dụng được thông báo rõ ràng
* Dữ liệu ẩn danh

Điều quan trọng cần lưu ý là mặc dù AppsFlyer chỉ hoạt động như một nhà cung cấp dịch vụ thay mặt bạn và theo chỉ thị của bạn, nhưng nếu bạn đang chia sẻ dữ liệu với các mạng bên thứ ba (ví dụ: thông qua đăng lại, SRN và đối tượng) thì đây sẽ được coi là hành động chia sẻ.  Do đó, mỗi nhà phát triển ứng dụng sẽ cần đánh giá cấu hình và tích hợp đối tác của mình và trả lời tương ứng theo.

## Xử lý ngắn hạn

Xử lý ngắn hạn là việc dữ liệu được xử lý trong bộ nhớ, chỉ trong khoảng thời gian cần thiết để xử lý một hành động cụ thể theo thời gian thực và không nhằm mục đích nào khác. Do bản chất của các dịch vụ AppsFlyer, dữ liệu do AppsFlyer thay mặt bạn xử lý sẽ không được xử lý ngắn hạn.

## Lựa chọn của người dùng

Nói chung, dữ liệu được thu thập là bắt buộc để thực hiện các dịch vụ. Vì thế, nhà phát triển ứng dụng có thể đưa hoạt động thu thập dữ liệu vào cài đặt kiểm soát việc lựa chọn tham gia hoặc lựa chọn không tham gia.

## Mục đích

Google đã cung cấp danh sách các mục đích mà các nhà phát triển ứng dụng phải chọn, chi tiết trong bảng sau. Bạn phải xác định mục đích thích hợp.

| Mục đích | Lưu ý |
| --- | --- |
| Chức năng ứng dụng | Hãy chọn nếu bạn sử dụng dữ liệu để kích hoạt bất kỳ tính năng nào trong ứng dụng |
| Phân tích | Có |
| Thông tin liên lạc của nhà phát triển | Hãy chọn nếu bạn sử dụng dữ liệu để gửi bất kỳ thông báo nào cho người dùng |
| Quảng cáo và tiếp thị | Hãy chọn nếu bạn chia sẻ loại dữ liệu với bên thứ ba nhằm mục đích hiển thị quảng cáo của bên thứ ba hoặc nếu sử dụng để quảng bá sản phẩm hoặc gửi thông báo đẩy |
| Gian lận, phòng ngừa, bảo mật và tuân thủ | Có |
| Cá nhân hóa | Hãy chọn nếu bạn sử dụng dữ liệu cho bất kỳ loại cá nhân hóa sản phẩm nào |
| Quản lý tài khoản | Hãy chọn nếu bạn sử dụng dữ liệu để thiết lập và quản lý tài khoản người dùng |

> 📄 **Xem thêm**
>
> Để tìm hiểu thêm về cách chuẩn bị cho phần an toàn của Google Play và cách hoàn thành biểu mẫu bắt buộc, hãy đọc các bài viết sau:
>
> * <Anchor target="_blank" href="https://android-developers.googleblog.com/2021/07/new-google-play-safety-section.html">Chuẩn bị cho phần an toàn mới của Google Play</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/10787469">Cung cấp thông tin cho phần An toàn dữ liệu của Google Play</Anchor>

<div data-zendesk-anchors="disclaimer=tuy%C3%AAn-b%E1%BB%91-t%E1%BB%AB-ch%E1%BB%91i-tr%C3%A1ch-nhi%E1%BB%87m h_01HDP3NTTKH3X3585J3DM6MCDC=tuy%C3%AAn-b%E1%BB%91-t%E1%BB%AB-ch%E1%BB%91i-tr%C3%A1ch-nhi%E1%BB%87m introduction=gi%E1%BB%9Bi-thi%E1%BB%87u h_01HDP3NTTK1BDTZTHNWRM3411D=gi%E1%BB%9Bi-thi%E1%BB%87u audience=%C4%91%E1%BB%91i-t%C6%B0%E1%BB%A3ng h_01HDP3NTTKQE2N0HZDNGK2ZQPC=%C4%91%E1%BB%91i-t%C6%B0%E1%BB%A3ng google-safety-form-questionnaire=bi%E1%BB%83u-m%E1%BA%ABu-an-to%C3%A0n-c%E1%BB%A7a-google-b%E1%BA%A3ng-c%C3%A2u-h%E1%BB%8Fi h_01HDP3NTTKK6DJSF49326V3BEG=bi%E1%BB%83u-m%E1%BA%ABu-an-to%C3%A0n-c%E1%BB%A7a-google-b%E1%BA%A3ng-c%C3%A2u-h%E1%BB%8Fi data-collection-and-security=thu-th%E1%BA%ADp-v%C3%A0-b%E1%BA%A3o-m%E1%BA%ADt-d%E1%BB%AF-li%E1%BB%87u h_01HDP3NTTK89K8YPT6C7S9QM3W=thu-th%E1%BA%ADp-v%C3%A0-b%E1%BA%A3o-m%E1%BA%ADt-d%E1%BB%AF-li%E1%BB%87u data-types=lo%E1%BA%A1i-d%E1%BB%AF-li%E1%BB%87u h_01HDP3NTTK9DYZTQ2B64QMKGX8=lo%E1%BA%A1i-d%E1%BB%AF-li%E1%BB%87u data-sharing=chia-s%E1%BA%BB-d%E1%BB%AF-li%E1%BB%87u h_01HDP3NTTKF5PQ1N8VBTMB1W2Z=chia-s%E1%BA%BB-d%E1%BB%AF-li%E1%BB%87u ephemeral-processing=x%E1%BB%AD-l%C3%BD-ng%E1%BA%AFn-h%E1%BA%A1n h_01HDP3NTTKT7C0TGVCZJ4GR9BF=x%E1%BB%AD-l%C3%BD-ng%E1%BA%AFn-h%E1%BA%A1n user-choice=l%E1%BB%B1a-ch%E1%BB%8Dn-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng h_01HDP3NTTK4CT8MJ1S84MAG8VD=l%E1%BB%B1a-ch%E1%BB%8Dn-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng purpose=m%E1%BB%A5c-%C4%91%C3%ADch h_01HDP3NTTKD3MND388MWCC6PAT=m%E1%BB%A5c-%C4%91%C3%ADch h_01HDP3RBENN69F150ESQMSVP3Q=xem-th%C3%AAm" />
