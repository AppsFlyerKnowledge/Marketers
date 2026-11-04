---
title: Mẫu OneLink
metadata:
  keywords:
    - template
    - Marketers
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2014-11-03T12:35:49Z'
  edited_at: '2023-11-15T15:36:40Z'
  id: 207032246
  locale: vi
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/vi/articles/207032246
---
> **Khái quát:** Tạo mẫu để tạo cơ sở logic chuyển hướng cho tất cả các liên kết OneLink mà bạn tạo cho các chiến dịch tiếp thị khác nhau của mình. Cần có mẫu để tạo liên kết và trải nghiệm người dùng cuối.

<div id="onelink-templates" />

## Mẫu OneLink

<Embed title="Trình phát video YouTube" typeOfEmbed="youtube" url="https://www.youtube.com/embed/d4AtCJ9122Q" providerUrl="https://www.youtube.com" />

Mẫu OneLink:

* Không phải là một liên kết có thể nhấp cho người dùng cuối của bạn; mà là nền tảng để tạo ra nhiều liên kết tùy chỉnh. Thông thường, bạn chỉ cần một mẫu cho mỗi ứng dụng (ngoài thử nghiệm) để tạo nhiều liên kết như mong muốn cho tất cả các chiến dịch quảng cáo khác nhau.
* Là nơi bạn ghi nhận các quyết định của mình về cách chuyển hướng người dùng dựa trên nền tảng thiết bị của họ và về việc họ đã cài đặt ứng dụng của bạn hay chưa.
* Trình bày logic định tuyến ở phần chính của tất cả các liên kết OneLink mà bạn tạo cho các chiến dịch tiếp thị khác nhau. Điều này bao gồm cài đặt chuyển hướng cho:
  * **Người dùng mới chưa cài đặt ứng dụng của bạn**: Vào đúng cửa hàng ứng dụng hoặc URL web
  * **Người dùng hiện có đã cài đặt ứng dụng của bạn**: Mở ứng dụng qua Liên kết Ứng dụng Android, Liên kết Chung iOS hoặc lược đồ URI. Điều này liên quan đến một số công việc cần nhà phát triển thiết lập.
  * **Lưu ý**: Cài đặt chuyển hướng cho trang web hoặc cửa hàng ứng dụng có thể bị ghi đè ở cấp liên kết.

<div id="create-a-onelink-template" />

## Quy trình

| **Đối tượng tham gia**<ul><li>Chỉ nhà tiếp thị mới phải thiết lập logic chuyển hướng cho những người dùng mới chưa cài đặt ứng dụng của bạn (ví dụ: đến đúng cửa hàng ứng dụng hoặc trang web).</li><li>Để thêm logic chuyển hướng cho những người dùng ứng dụng hiện có đã cài đặt ứng dụng của bạn (ví dụ: để mở ứng dụng), cần có cả nhà tiếp thị và nhà phát triển Android/iOS.</li></ul> |
| --- |
| **Điều kiện tiên quyết**<ul><li>Tài khoản AppsFlyer có ít nhất một ứng dụng.</li><li>Nhà tiếp thị phải là người dùng quản trị AppsFlyer hoặc có <Anchor target="_blank" href="/marketers/vi/docs/user-management">quyền thêm/chỉnh sửa mẫu OneLink</Anchor>.</li></ul> |
| **Thời gian cần thiết**<br /><br />Khoảng 1,5 giờ, làm việc cùng với các nhà phát triển Android/iOS của bạn. |
| **Kết quả**<ul><li>Mẫu mà từ đó bạn có thể tạo liên kết đưa người dùng đến đúng cửa hàng ứng dụng, trang web hoặc vào ứng dụng dựa trên thiết bị của họ.</li></ul> |

<div id="create-a-onelink-template-with-redirection-logic-for-new-app-users" />

<Accordion title="Tạo mẫu OneLink với logic chuyển hướng cho người dùng ứng dụng mới">

**Để tạo mẫu OneLink:**

1. Trong bảng điều khiển AppsFlyer, chuyển đến **Experiences & deep linking** > **OneLink management**.  
   Bộ ứng dụng OneLink là một tính năng cấp tài khoản, cho phép bạn tạo mẫu OneLink và các liên kết tùy chỉnh của chúng cho tất cả các ứng dụng của bạn.  

   [![](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)

   **Lưu ý**: Nếu bạn chưa tạo bất kỳ mẫu nào, một trình hướng dẫn làm quen sẽ mở ra. Làm theo hướng dẫn trong trình hướng dẫn và bỏ qua phần còn lại của quy trình này.
2. Nhấp vào biểu tượng menu > **Add OneLink template**.  
   Trang thiết lập mẫu OneLink sẽ được mở ra.  

   [![OneLink_template_page_en-us.png](https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png)](https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png)
3. Trong trường tên mẫu của **OneLink**, hãy nhập tên.  

   <div id="note" />

   > 📘 **Lưu ý**
   >
   > * Tên mẫu OneLink phù hợp cần phải chứa **tên của ứng dụng** (ví dụ: feed\_me) hoặc trường hợp sử dụng hoặc trải nghiệm có OneLink làm đại diện (ví dụ: pre\_launch\_landing\_page).
   > * Tên không nên bao gồm chiến dịch hoặc tên kênh hoặc nguồn truyền thông (vì đây không phải là liên kết người dùng cuối thực tế, mà chỉ là mẫu cơ bản để tạo nhiều liên kết), hoặc tên của nền tảng (Android, iOS, vì nhiều nền tảng thường là lý do ban đầu để sử dụng mẫu OneLink).
   > * Tên mẫu này chỉ được sử dụng nội bộ. Tên này không ảnh hưởng đến dữ liệu phân bổ tiếp thị của bạn và người dùng sẽ không nhìn thấy.

4. Trong trường **Subdomain** , nhập tên <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-knowledge-base-glossary#miền-phụ">miền phụ</Anchor> của bạn.
   * Chọn một miền phụ phù hợp với thương hiệu của bạn. Ví dụ: nếu trang web của bạn là www.abcd.com, hãy chọn abcd làm miền phụ.
   * Người dùng sẽ thấy miền phụ này trong URL liên kết. Ví dụ: `https://abcd.onelink.me/RPsv/37e5cd36`.
   * Không thể thay đổi miền phụ sau khi các liên kết tùy chỉnh được tạo dựa trên mẫu này.
   * Chỉ sử dụng chữ cái viết thường, chữ số hoặc dấu gạch nối (-).
   * OneLink cũng hỗ trợ các miền gắn thương hiệu đầy đủ, có thể giúp bạn cải thiện hiệu suất chiến dịch và tăng khả năng hiển thị thương hiệu. <Anchor target="_blank" href="/marketers/vi/docs/brand-onelink-with-your-domain">Tìm hiểu thêm</Anchor>
5. Chọn ứng dụng Android, ứng dụng iOS của bạn hoặc cả hai.
6. Đặt nơi chuyển hướng người dùng **Khi ứng dụng chưa được cài đặt**.

   * Nếu bạn đã chọn ứng dụng Android và ứng dụng iOS, thì mẫu được cấu hình theo mặc định để đưa người dùng ứng dụng mới đến đúng cửa hàng ứng dụng.
   * Nếu bạn chỉ chọn một ứng dụng, Android hoặc iOS, mẫu được cấu hình để chuyển TẤT CẢ người dùng (iOS và Android, mới và hiện có) đến một điểm đích được xác định duy nhất.
   * Nếu bạn chọn một ứng dụng Android không có trong Google Play, thì bạn phải nhập URL mà người dùng Android được chuyển hướng đến.
   * [Tùy chọn] **Chuyển hướng đến cửa hàng ứng dụng của bên thứ ba** nếu ứng dụng có trong các cửa hàng khác ngoài Google Play. Đảm bảo rằng ứng dụng trong các cửa hàng khác có cùng tên gói với ứng dụng Android được chọn trong mẫu OneLink của bạn.
   * [Tùy chọn] **Thay đổi thành một URL khác**: Trong một số trường hợp, bạn có thể muốn đưa người dùng mới đến với trải nghiệm web trên di động thay vì trực tiếp đến cửa hàng ứng dụng (hoặc ứng dụng của bạn có thể không được đưa lên cửa hàng). Để triển khai, hãy nhập URL đó vào trường URL. **Lưu ý**: Nếu bạn đặt cả chuyển hướng của bên thứ ba và một URL khác, thì chuyển hướng mặc định là tới cửa hàng ứng dụng của bên thứ ba.
   * [Tùy chọn] Bật **Display App Clip for users with Private Relay** (khả dụng trên iOS 14+). <Anchor target="_blank" href="/marketers/vi/docs/apple-app-clips-integration-guide">Tìm hiểu thêm về App Clips</Anchor>.
7. Bỏ qua **Khi ứng dụng được cài đặt**. Điều này sẽ được thảo luận trong [quy trình tiếp theo](/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users).
8. [Tùy chọn] Thay đổi điểm đến cho trường hợp **Khi liên kết được nhấp vào trên máy tính để bàn.**  
   * Trong một số trường hợp, có thể nhấp vào liên kết của bạn trên máy tính để bàn, đặc biệt nếu liên kết được gửi qua email hoặc mạng xã hội. Nếu hy vọng có nhiều lưu lượng từ máy tính để bàn đến liên kết của mình, bạn có thể sẽ muốn chuyển những người dùng đó đến trang đích hoặc trang chủ của trang web chính hoặc trang mà họ có thể yêu cầu gửi liên kết SMS đến điện thoại của họ, thay vì đúng cửa hàng ứng dụng.
   * Theo mặc định, người dùng máy tính để bàn được chuyển hướng đến trang App Store iOS của ứng dụng bạn hoặc đến trang ứng dụng của Google Play, nếu ứng dụng iOS không được xác định.
9. [Tùy chọn] **Chọn ứng dụng từ các nền tảng khác**  
   Nếu bạn có một phiên bản ứng dụng dành riêng cho các loại máy sau:
   * **Windows Phone**: Bật nút chuyển đổi và chọn ứng dụng hoặc **Thay đổi sang một URL khác**.
   * **iPad**: Bật chuyển đổi và chọn ứng dụng iPad
   * **Amazon Kindle Fire**: Bật nút chuyển và thêm ASIN cửa hàng Amazon hoặc URL trang ứng dụng.
10. Nhấp vào **Save OneLink template** (Cập nhật mẫu OneLink cho các mẫu đã chỉnh sửa).   
    Mẫu OneLink của bạn hiện đã được tạo và có thể được sử dụng để tạo nhiều liên kết có thể nhấp khác nhau (xem <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Liên kết và trải nghiệm OneLink</Anchor>).

</Accordion>

<div id="add-redirection-logic-for-existing-app-users" />

<Accordion title="Thêm logic chuyển hướng cho người dùng ứng dụng hiện có">

Người dùng ứng dụng hiện có thường mong đợi được chuyển hướng trực tiếp đến ứng dụng, không phải cửa hàng ứng dụng hoặc trang web. Có ba công nghệ sẵn có để mở ứng dụng trực tiếp bằng một cú nhấp chuột:

* **Liên kết chung iOS**: Hoạt động với iOS từ phiên bản 9 trở lên và chop trải nghiệm mượt mà, bảo mật khi mở ứng dụng của bạn.
* **Liên kết Ứng dụng Android**: Hoạt động với Android từ phiên bản 6 trở lên và cho trải nghiệm mượt mà, bảo mật khi mở ứng dụng. **Lưu ý**: Hệ điều hành Samsung không thể mở ứng dụng bằng Liên kết Ứng dụng Android.
* **Lược đồ URI**:  
  * Phương thức dự phòng:
    * Android: Lược đồ URI là một phương thức dự phòng hiệu quả khi Liên kết Ứng dụng Android không mở được ứng dụng vì chúng không hoạt động hoặc chưa được thiết lập
    * iOS: Khả năng dự phòng hạn chế khi Liên kết Chung không mở được ứng dụng vì chúng không hoạt động hoặc chưa được thiết lập. <Anchor target="_blank" href="/marketers/vi/docs/uri-scheme-fallback-for-ios">Tìm hiểu thêm</Anchor>
  * Phương thức chính để mở ứng dụng trên thiết bị Samsung.
  * Là một địa chỉ mà khi được truy cập thì sẽ mở ứng dụng của bạn nếu đã được cài đặt. Chúng tương tự như các liên kết trang web nhưng mở ứng dụng thay vì trang web.
  * Phải giống nhau đối với iOS và Android.

Để có trải nghiệm người dùng, khả năng bảo mật và phạm vi thiết bị tốt nhất, chúng tôi đề nghị bạn nên bật càng nhiều công nghệ càng tốt.Nếu bạn bật tất cả các công nghệ liên kết, OneLink sẽ tự động áp dụng phương pháp tốt nhất cho mỗi người dùng.

**Để thêm logic chuyển hướng cho người dùng ứng dụng hiện có vào mẫu OneLink:**

1. Trong trang tổng quan AppsFlyer, chuyển đến **Experiences & deep linking** > **OneLink management**.
2. Di chuột qua mẫu OneLink bạn muốn chỉnh sửa và nhấp vào biểu tượng **Edit**.
3. Cuộn xuống **When app is installed** (Khi ứng dụng được cài đặt).

   [![](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)
4. Thực hiện theo các hướng dẫn về thiết lập iOS, Android và dự phòng:  

   <Tabs>
   <Tab title="Liên kết Chung iOS">

   Liên kết Chung có định dạng như các liên kết web thông thường (ví dụ: https://yourbrand.onelink.me hoặc https://www.yourbrand.com) và do đó yêu cầu cài đặt miền phụ (được nêu trong [hướng dẫn trước](/docs/create-a-onelink-template#quy-trình)). OneLink cũng hỗ trợ đầy đủ <Anchor target="_blank" href="/marketers/vi/docs/brand-onelink-with-your-domain">miền gắn thương hiệu</Anchor>, nhưng không cần thiết phải hoàn thành hướng dẫn này.

   **Để khởi chạy ứng dụng bằng Liên kết Chung**:

   1. Liên hệ với nhà phát triển iOS của bạn:
      * Cung cấp cho họ miền phụ cho mẫu OneLink này.
      * Yêu cầu họ làm theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">các hướng dẫn này</Anchor>.
      * Nhà phát triển sẽ trả về cho bạn ID Nhóm (còn được gọi là Tiền tố ID Ứng dụng Apple, ví dụ: PF23MIWNTW).
      * Nếu ứng dụng chưa được phát hành, nhà phát triển cũng phải cung cấp cho bạn Mã định danh Gói (ví dụ: com.myapp.something).  

        [![](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)
   2. Trong trang mẫu OneLink, hãy nhấp vào **Change to launch the app using Universal Links** (Đổi thành khởi chạy ứng dụng bằng Liên kết Chung).
   3. Trong cửa sổ mới, chọn **Launch the app using Universal Links (Khởi chạy ứng dụng bằng Liên kết Chung)**.
   4. Trong trường **Team ID** (ID Nhóm), nhập ID nhóm do nhà phát triển cung cấp.
   5. Nếu ứng dụng chưa được phát hành, hãy nhập cả **Bundle Identifier** (Mã định danh Gói).
   6. Nhấp vào **Save changes** (Lưu thay đổi).

   </Tab>

   <Tab title="Liên kết Ứng dụng Android">

   Liên kết Ứng dụng có định dạng như các liên kết web thông thường (ví dụ: https://yourbrand.onelink.me hoặc https://www.yourbrand.com) và do đó yêu cầu phải cài đặt miền phụ (được nêu trong [hướng dẫn trước](/docs/create-a-onelink-template#quy-trình)). OneLink cũng hỗ trợ đầy đủ <Anchor target="_blank" href="/marketers/vi/docs/brand-onelink-with-your-domain">miền gắn thương hiệu</Anchor>, nhưng không cần thiết phải hoàn thành hướng dẫn này.

   **Trước khi bạn bắt đầu**:

   Ghi lại miền phụ bạn đã chọn cho mẫu OneLink này.

   **Để khởi chạy ứng dụng bằng Liên kết Ứng dụng Android**:

   1. Hãy liên hệ với nhà phát triển Android của bạn:   
       Yêu cầu họ tạo vân tay SHA256 bằng cách làm theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#generating-a-sha256-fingerprint">các hướng dẫn sau</Anchor>.  
       Nhà phát triển sẽ trả về cho bạn vân tay SHA256. Ví dụ: `DC:65:43:67:F3:BD:02:52:AC:B4:50:F1:74:54:23:49:4D:49:6C:E6:DF:56:BD:CB:53:06:11:5B:C9:4E:5D:0C`
   2. Trong trang mẫu OneLink, nhấp vào **Change to launch the app using App Links** (Đổi thành khởi chạy ứng dụng bằng Liên kết Ứng dụng).
   3. Trong cửa sổ mới, chọn **Launch the app using App Links (Khởi chạy ứng dụng bằng Liên kết Ứng dụng)**.
   4. Trong trường **SHA256 fingerprint**, nhập vân tay SHA256 do nhà phát triển cung cấp.  
      Mã bộ lọc ý định được tạo tự động sẽ xuất hiện.
   5. Liên hệ với nhà phát triển Android của bạn:   
      Cung cấp cho họ mã bộ lọc ý định được tạo tự động.  
      Yêu cầu họ làm theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">các hướng dẫn này</Anchor> và xác nhận hoàn thành.

   </Tab>

   <Tab title="Lược đồ URI">

   Lược đồ URI chủ yếu đóng vai trò làm dự phòng cho cả người dùng iOS và Android, và do đó phải giống nhau ở cả hai hệ điều hành này.

   **Để cài đặt dự phòng URI Android và iOS:**

   1. Liên hệ với nhà phát triển iOS VÀ Android của bạn và quyết định lược đồ URI. Ví dụ: `feedmeapp://`  

      <div id="h_01H9Q4E7VR4CAK0PJY269GQ9XJ" />

      > 👍 **Lời khuyên**
      >
      > * Cả Apple và Google đều không yêu cầu đặt tên duy nhất cho các lược đồ ứng dụng. **Hãy chọn tên lược đồ riêng cho nhãn hiệu của bạn** để tránh xung đột lược đồ ở các ứng dụng khác. Tên lược đồ phù hợp có thể là ID gói ứng dụng của bạn, ví dụ: **com.company.app**
      > * Để cho phép OneLink phân phối cả iOS và Android, điều quan trọng là phải xác định **cùng một lược đồ cho cả hai nền tảng**. Dưới đây là hướng dẫn dành cho <Anchor target="_blank" href="https://help.contrast.co/hc/vi/articles/200865293-URL-Scheme-Intro-for-App-Developers">iOS</Anchor> và <Anchor target="_blank" href="https://developer.android.com/training/app-links/deep-linking.html">Android</Anchor>.
      > * Lược đồ URI không nên bắt đầu bằng http hoặc https.

   2. Yêu cầu nhà phát triển iOS triển khai lược đồ URI trong ứng dụng của họ bằng cách làm theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-uri-scheme">các hướng dẫn sau</Anchor>.  
       **VÀ**Yêu cầu nhà phát triển Android triển khai lược đồ URI trong ứng dụng của họ bằng cách làm <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#procedures-for-uri-scheme">theo các hướng dẫn sau</Anchor>.
   3. Khi hoàn thành, nhà phát triển xác nhận giá trị của lược đồ URI được triển khai. Dự kiến lược đồ URI sẽ có dạng: `exampleapp://` hoặc `exampleapp://home` hoặc `exampleapp://main`, v.v.
   4. Trong trang mẫu OneLink, nhấp vào **Add URI scheme to launch the app** (Thêm lược đồ URI để khởi chạy ứng dụng).
   5. Chọn **Launch the app using URI scheme** (Khởi chạy ứng dụng bằng lược đồ URI).
   6. Nhập giá trị lược đồ URI.
   7. Nhấp vào **Save changes** (Lưu thay đổi).
   8. Thử nghiệm lược đồ URI (việc này có thể do bạn HOẶC nhà phát triển của bạn thực hiện):
      1. Truy cập <Anchor target="_blank" href="https://halgatewood.com/deeplink/">công cụ thử nghiệm công khai miễn phí này</Anchor> trên cả thiết bị iOS và Android đã cài đặt ứng dụng của bạn.
      2. Nhấn vào liên kết được tạo bởi công cụ này.  
          Nếu lược đồ URI là chính xác, ứng dụng sẽ được mở ra.

   </Tab>
   </Tabs>

5. Nhấp vào **Update OneLink template** (Cập nhật mẫu OneLink).

<div id="note-1" />

> 📘 **Lưu ý**
>
> * Khi bạn lưu hoặc cập nhật mẫu OneLink của mình, AppsFlyer sẽ tự động tạo tệp tin AASA và/hoặc Liên kết Tài sản Kỹ thuật số JSON để xác minh miền ứng dụng của bạn và lưu trữ miền ứng dụng đó cho bạn. Điều này rất quan trọng để Liên kết Chung và Liên kết Ứng dụng của bạn hoạt động đúng cách.
> * Thời gian để các cập nhật mẫu OneLink có hiệu lực có thể lên đến 1 giờ.

</Accordion>

<div id="customize-qr-codes" />

<Accordion title="Tùy chỉnh mã QR">

![OnelinkQRFinal__1_.gif](https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif)

Bạn có thể tùy chỉnh mã QR được tạo qua OneLink bằng cách:

* Thêm logo của bạn vào mã QR
* Thay đổi màu của mã QR.

**Lưu ý**: Việc tùy chỉnh mã QR diễn ra ở cấp mẫu; không phải ở cấp độ liên kết riêng lẻ. Do đó, các tùy chỉnh sẽ ảnh hưởng đến tất cả các mã QR dựa trên mẫu đã chỉnh sửa.

**Để tùy chỉnh mã QR**:

1. Trong bảng điều khiển AppsFlyer, đi đến **Experiences & deep linking** (Trải nghiệm & liên kết sâu) > **OneLink Custom Links** (Liên kết Tùy chỉnh OneLink).
2. Di chuột qua biểu tượng **Hành động** của mẫu bạn muốn chỉnh sửa và nhấp vào **Customize QR code** (Tùy chỉnh mã QR).  
   Trình chỉnh sửa mã QR sẽ mở ra.
3. Enter the URL where your logo is hosted. For example: https://yourbrand.com/logo.png.  

   Yêu cầu về logo:

   * Định dạng PNG hoặc JPG
   * Hình vuông hoặc hình tròn với nền trong suốt
   * Kích thước tối thiểu 400 x 400 px
   * Để in, hãy sử dụng độ phân giải hình ảnh tối đa
4. Đặt màu cho mã QR.
5. Nhấp vào **Save** (Lưu).

</Accordion>

<div id="key-traits-and-limitations" />

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Nhận xét |
| --- | --- |
| Đại lý | <ul><li>Các đại lý không thể tự tạo mẫu OneLink.</li><li>Các đại lý có thể sử dụng các mẫu OneLink hiện có để tạo đường dẫn phân bổ tùy chỉnh cho mình **nếu đại lý này là một đối tác của tất cả các ứng dụng trong mẫu**.</li></ul> |
| Thêm/chỉnh sửa mẫu OneLink | Người dùng tài khoản yêu cầu <Anchor target="_blank" href="/marketers/vi/docs/user-management">quyền</Anchor> thêm và chỉnh sửa mẫu OneLink. |
| Mẫu OneLink | Tối đa 600 mẫu OneLink cho mỗi tài khoản. |
| Máy tính để bàn | Khi bạn đặt URL hoặc mẫu OneLink để chuyển hướng người dùng máy tính để bàn đến một URL khác, URL web sẽ được thêm vào liên kết trong thông số `af_web_dp`. Khi liên kết chứa `af_web_dp`, AppsFlyer không đăng ký lượt nhấp khi lượt nhấp đó đến từ máy tính để bàn. |
| Chuyển hướng đến các cửa hàng ứng dụng của bên thứ ba | Chỉ có thể đặt nhiều cửa hàng ứng dụng trên mẫu OneLink nếu tên gói ứng dụng là giống nhau ở tất cả các cửa hàng ứng dụng.<br /><br />**Lưu ý**:<ul><li>Huawei sử dụng các tên gói khác nhau, vì vậy không thể sử dụng cùng một mẫu OneLink cho nhiều cửa hàng ứng dụng.</li><li>Nếu tên gói giống nhau, nhưng kênh khác nhau, thì tính năng chuyển hướng sẽ hoạt động, nhưng phân bổ thì không.</li><li><Anchor target="_blank" href="/marketers/vi/docs/set-up-multi-store-android-attribution">Tìm hiểu thêm</Anchor> về phân bổ và dữ liệu cửa hàng ứng dụng của bên thứ ba.</li></ul> |
| Cập nhật mẫu | Thời gian áp dụng thay đổi về định cấu hình mẫu OneLink tối đa là 1 giờ. |

</Accordion>

Bạn có câu hỏi về các mẫu OneLink? Hãy xem phần <Anchor target="_blank" href="/marketers/vi/docs/onelink-troubleshooting-and-faq#câu-hỏi-thường-gặp-về-mẫu-onelink">Câu hỏi thường gặp</Anchor> của chúng tôi!

<div id="next-step" />

## Bước tiếp theo

Làm theo hướng dẫn để <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">tạo liên kết OneLink</Anchor> dựa trên mẫu của bạn.

<div data-zendesk-anchors="onelink-templates=m%E1%BA%ABu-onelink h_01H9Q4E7VQ0GKZ9HFF88190TYN=m%E1%BA%ABu-onelink procedures=quy-tr%C3%ACnh h_01H9Q4E7VQYGZ1MH5SS3ZYZF1K=quy-tr%C3%ACnh h_01H9Q4E7VQ648CQ1VJTB1TC571=create-a-onelink-template-with-redirection-logic-for-new-app-users h_01H9Q4E7VQ15AAR1VXNKWR1XGT=l%C6%B0u-%C3%BD h_01H9Q4E7VQ4NEWYAD6AMR9YKGY=add-redirection-logic-for-existing-app-users h_01H9Q4E7VR8164HR6MD0EAV2SN=l%C6%B0u-%C3%BD-1 h_01H9Q4E7VR0F4B7CTF08YTG715=customize-qr-codes h_01H9Q4E7VR2B50EQE31DDG8GNZ=traits-and-limitations next-step=b%C6%B0%E1%BB%9Bc-ti%E1%BA%BFp-theo h_01H9Q4E7VRJK31P9CSGJFCKQQF=b%C6%B0%E1%BB%9Bc-ti%E1%BA%BFp-theo" />
