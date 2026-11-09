---
title: Tại sao ứng dụng của tôi vẫn đang ở trạng thái chờ xử lý?
metadata:
  keywords:
    - Google Play
    - App Store
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2018-10-14T07:22:04Z'
  edited_at: '2021-12-08T05:03:42Z'
  id: 360001533885
  locale: vi
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/vi/articles/360001533885
---
> **Sơ lược:** Theo dõi trạng thái của các ứng dụng đang chờ phát hành sang các cửa hàng ứng dụng từ bảng điều khiển AppsFlyer.

Khi bạn <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">thêm ứng dụng mới</Anchor> vào bảng điều khiển AppsFlyer, trước tiên bạn cần chọn ứng dụng đang chờ phát hành hay đã có trên thị trường.

Các ứng dụng đang chờ xử lý trong AppsFlyer sẽ trông giống như các ứng dụng đang hoạt động. Chúng có các bảng điều khiển có thể truy cập và tất cả các phép do phân bổ. Sự khác biệt duy nhất là logo của ứng dụng hiển thị logo của AppsFlyer thay vì logo ứng dụng thực tế.

<Image align="center" alt="Pending_App.png" src="https://files.readme.io/fd280ea8dbcd280aae0a1328d1523f52c51d2f30dc163e7a62deb424ae5bc8ed-360001789338.png" />

<div id="whats-happening" />

## Điều gì sẽ xảy ra?

AppsFlyer tự động kiểm tra trạng thái của ứng dụng vài lẫn mỗi ngày.

Nếu ứng dụng vẫn chưa tồn tại trên cửa hàng khi AppsFlyer kiểm tra trạng thái ứng dụng, thì ứng dụng sẽ xuất hiện ở trạng thái đang chờ phát hành trong bảng điều khiển. Sau khi ứng dụng được gửi đến iTunes hoặc Google, trạng thái được cập nhật thành đang hoạt động và logo ứng dụng sẽ thay đổi thành logo gốc của ứng dụng.

Trạng thái ứng dụng trong bảng điều khiển không ảnh hưởng đến việc thu thập dữ liệu và đo lường. Nếu ứng dụng ra mắt trên Google Play hoặc App Store và người dùng cài đặt ứng dụng cũng như tương tác với ứng dụng đó, dữ liệu cài đặt và sự kiện trong ứng dụng sẽ hiển thị tương tự trong bảng điều khiển.

<div id="refreshing-the-app-status" />

## Làm mới trạng thái ứng dụng

Để trạng thái ứng dụng thay đổi thành đang hoạt động, AppsFlyer sẽ kiểm tra trạng thái ứng dụng trên cửa hàng. Nếu bạn chắc chắn rằng ứng dụng đã được phát hành trong Google Play hoặc iTunes, nhưng ứng dụng vẫn xuất hiện ở trạng thái đang chờ xử lý trong bảng điều khiển, thì quản trị viên có thể kiểm tra trạng thái ứng dụng theo cách thủ công.

**Điều kiện tiên quyết**: Khả dụng cho quản trị viên tài khoản.

**Để cập nhật trạng thái ứng dụng theo cách thủ công:**

1. Trong bảng điều khiển, nhấp vào **My Apps** (Ứng dụng của tôi) ở góc phía trên bên phải.  
   <Image align="center" alt="app-refersh-status.png" src="https://files.readme.io/d995ea3ee3523a8f0d4854f9ec116efc33c892694d56334c483b7d9fa6da8d64-360001704577.png" />
2. Cạnh ứng dụng đang chờ xử lý, nhấp vào **Refresh Status (Làm mới Trạng thái).**  
   Nếu trạng thái ứng dụng không thay đổi, thì ứng dụng vẫn hiển thị ở trạng thái Đang chờ xử lý. Nếu ứng dụng đã được cập nhật, trạng thái được hiển thị là Đang hoạt động và logo được cập nhật.

<div id="store-country" />

## Quốc gia của cửa hàng ứng dụng

Một số ứng dụng chỉ khả dụng trên Google Play hoặc iTunes ở một số quốc gia. **Điều quan trọng là cần thiết lập đúng quốc gia cho ứng dụng** để AppsFlyer có thể kiểm tra và cập nhật trạng thái ứng dụng.

### iOS

Khi bạn <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">thêm ứng dụng iOS</Anchor> vào bảng điều khiển AppsFlyer, bạn sẽ chọn quốc gia Apple Store mà ứng dụng được phát hành. Nếu chọn sai quốc gia, AppsFlyer sẽ không thể cập nhật trạng thái ứng dụng ngay cả khi ứng dụng đã được phát hành.

Để thay đổi quốc gia cho Apple Store:

1. Trong bảng điều khiển của ứng dụng, nhấp vào **App Settings** (Cài đặt Ứng dụng) trong menu bên trái
2. Chọn đúng quốc gia trong mục **Quốc gia của Cửa hàng Ứng dụng**
3. Cuộn xuống và nhấp vào **Save Settings** (Lưu Cài đặt)
4. Nếu ứng dụng vẫn xuất hiện ở trạng thái đang chờ xử lý, [nhấp vào **Refresh Status**](/docs/why-is-my-app-still-pending#refreshing-the-app-status) (Làm mới Trạng thái).

### Android

Khi bạn <Anchor target="_blank" href="/marketers/vi/docs/adding-an-app-to-appsflyer">thêm ứng dụng Android</Anchor> vào bảng điều khiển AppsFlyer, không có tùy chọn nào để chọn quốc gia Google Play và quốc gia được chọn mặc định là Hoa Kỳ. Nếu ứng dụng của bạn không được phát hành tại cửa hàng Google Play Hoa Kỳ, điều quan trọng là cần thiết lập đúng cửa hàng cho ứng dụng để AppsFlyer có thể kiểm tra và cập nhật trạng thái ứng dụng.

Để thay đổi quốc gia cho Google Play:

1. Trong bảng điều khiển của ứng dụng, nhấp vào **App Settings** (Cài đặt Ứng dụng) trong menu bên trái
2. Chọn đúng quốc gia trong mục **Quốc gia của Cửa hàng Ứng dụng**
3. Cuộn xuống và nhấp vào **Save Settings** (Lưu Cài đặt)
4. Nếu ứng dụng vẫn xuất hiện ở trạng thái đang chờ xử lý, [nhấp vào **Refresh Status**](/docs/why-is-my-app-still-pending#refreshing-the-app-status) (Làm mới Trạng thái).