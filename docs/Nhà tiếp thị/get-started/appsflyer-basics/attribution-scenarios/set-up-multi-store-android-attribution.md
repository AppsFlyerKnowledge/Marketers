---
title: 'Thiết lập phân bổ Android nhiều cửa hàng '
metadata:
  keywords:
    - Android
    - Google
    - Google Play
    - Add App
    - amazon
    - Advertisers
    - Agencies
    - baidu
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-12-24T10:48:17Z'
  edited_at: '2023-08-10T20:37:49Z'
  id: 207447023
  locale: vi
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/vi/articles/207447023
---
> **Khái quát:** Phân bổ ứng dụng của bạn trong nhiều cửa hàng Android và xem dữ liệu trong một bảng điều khiển ứng dụng duy nhất hoặc trong một bảng điều khiển ứng dụng cho mỗi cửa hàng.

## Phân bổ Android nhiều cửa hàng

AppsFlyer phân bổ ứng dụng, không phân biệt cửa hàng ứng dụng. Điều này có nghĩa là cửa hàng Google Play và các cửa hàng ứng dụng Android của bên thứ ba như Amazon, Opera, GetJar, Baidu và Huawei. (Hay còn gọi là cửa hàng ngoài thị trường hoặc cửa hàng ứng dụng Android thay thế.) Chủ sở hữu ứng dụng, người tiếp thị ứng dụng qua nhiều cửa hàng, có thể chọn một **bảng điều khiển** **duy nhất** chứa dữ liệu của tất cả cửa hàng hoặc một **bảng điều khiển cho mỗi cửa hàng.**

> 📘 **Lưu ý**
>
> * Mô hình phân bổ Android của AppsFlyer hỗ trợ tất cả các loại mã định danh thiết bị bao gồm GAID và <Anchor target="_blank" href="/marketers/vi/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor>
> * Đối với các ứng dụng được tiếp thị tại Trung Quốc, hãy xem phần <Anchor target="_blank" href="/marketers/vi/docs/measure-attribution-in-the-chinese-domestic-market">Phân bổ ứng dụng Android tại thị trường nội địa Trung Quốc</Anchor>

![DashboardType_us-en-new.jpg](https://files.readme.io/10fdd08c4e57f799756f46922b5f8dc45c67f7550f9105e65076652f459c98f7-9545756936593.jpg)

### Bảng điều khiển duy nhất so với bảng điều khiển cho mỗi cửa hàng

* **Bảng điều khiển duy nhất:** Một bảng điều khiển kết hợp dữ liệu từ tất cả cửa hàng, bao gồm cả Cửa hàng Google Play
* **Bảng điều khiển cho mỗi cửa hàng:** Nhiều bảng điều khiển—mỗi cửa hàng có bảng điều khiển riêng. Điều này có nghĩa là số lượng bảng điều khiển bằng số lượng cửa hàng cung cấp ứng dụng.

<table><thead><tr><th> </th><th><p>Bảng điều khiển duy nhất<br/> [Phương pháp thực hành tốt nhất]</p></th><th> Bảng điều khiển cho mỗi cửa hàng</th></tr></thead><tbody><tr><td><span id="android-package-name"></span>Tên gói Android</td><td colspan="2">Sử dụng cùng tên gói (giống hệt nhau) bất kể tùy chọn đã chọn là gì. </td></tr><tr><td><span id="channel-name"></span>Tên kênh</td><td>Không có gì để thiết lập</td><td><ul><li><span>Khi thêm Ứng dụng vào bảng điều khiển AppsFlyer bằng tùy chọn <strong>APK ngoài cửa hàng Android</strong>, hãy đặt kênh.</span></li><li><span>Kênh xác định cửa hàng. </span></li><li>Sự kết hợp giữa tên gói Android và kênh đặc biệt xác định mỗi bảng điều khiển AppsFlyer. </li><li>Ví dụ: Tên gói Android là com.abc.def và kênh là xyz_device_store. Mã định danh bảng điều khiển duy nhất là com.abc.def-xyz_device_store. </li><li>Nếu APK có cài đặt kênh nhưng không có ứng dụng nào có cài đặt này, lưu lượng truy cập được phân bổ cho ứng dụng mặc định, là ứng dụng có cài đặt kênh trống là Cửa hàng Google Play. </li></ul></td></tr><tr><td><span id="populating-the-install_app_store-field"></span>Điền trường install_app_store</td><td><ul><li>Xác định đặc biệt cửa hàng cung cấp ứng dụng bằng cách tải xuống.</li><li>Trong trường hợp đối với Google Play Store, đây sẽ để trống. </li><li>Tên cửa hàng được đặt trong <a href="./set-up-multi-store-android-attribution#single-dashboard-apk-preparation">tệp tin kê khai/APK</a>.</li></ul></td><td><p>Không áp dụng</p></td></tr><tr><td><span id="onelink-template"></span><a href="./create-a-onelink-template#quy-trình" target="_blank">Mẫu OneLink</a></td><td>Nên sử dụng phương thức này khi làm việc với OneLink. </td><td>Không áp dụng </td></tr><tr><td><span id="measurementattribution-links"></span>Đo lường/Đường dẫn phân bổ </td><td><ul><li>Liên kết là giống nhau bất kể là cửa hàng nào.</li><li>Để chuyển hướng đến đúng cửa hàng, hãy sử dụng <a href="./set-up-multi-store-android-attribution#single-dashboard-attribution-links">af_r</a> để đặt URL chuyển hướng</li></ul></td><td><ul><li>Cần có một liên kết đặc biệt cho mỗi cửa hàng.</li><li>Tạo các đường dẫn này thông qua trang <strong>Active integrations</strong>.</li><li>ID ứng dụng là tên kênh được nối với tên gói android. Ví dụ: com.abc.def-def_store.<br/>Do đó các đường dẫn phân bổ sẽ khác nhau.</li></ul></td></tr><tr><td><span id="reporting-options-available-having-install_app_store-field"></span>Tùy chọn báo cáo có sẵn có trường install_app_store</td><td><p>Các báo cáo Tổng quan, Nhóm người và dữ liệu thô đều chứa trường này. Liên hệ với CSM của bạn để yêu cầu thêm cờ tính năng SFDC cần thiết. </p></td><td>Không áp dụng </td></tr><tr><td><span id="considerations"></span><p>Những điều cần lưu ý</p></td><td><ul><li>Độ chính xác phân bổ: Các lượt cài đặt lại từ các cửa hàng khác nhau không dẫn đến số lượt cài đặt tăng đột biến. </li><li><span>Lượt cài đặt tự nhiên sẽ phản ánh các lượt cài đặt tự nhiên của APK từ tất cả các cửa hàng trong một bảng điều khiển.</span></li><li><span>Hiện tại, các tùy chọn báo cáo được tách theo từng cửa hàng bị giới hạn chỉ có báo cáo Tổng quan, Nhóm người và dữ liệu thô.</span></li></ul></td><td><ul><li>Độ chính xác phân bổ: Các lượt cài đặt lại cũng được tính, dẫn đến phân bổ kém chính xác hơn.</li><li> <span>Xem </span>dữ liệu lượt cài đặt <span>tự nhiên</span><span> và </span><span>không tự nhiên</span><span> và sự kiện trong ứng dụng cho mỗi cửa hàng (kênh) trên bảng điều khiển ứng dụng riêng trong AppsFlyer.</span> </li><li><span>Sử dụng Nhóm người để hiển thị các báo cáo kết hợp của tất cả các cửa hàng</span></li><li>Đảm bảo rằng các đối tác mà bạn hợp tác <strong>đang hoạt động</strong> (bật tính năng <a href="./partner-activation-deactivation" target="_blank">Activate partner</a>) trên <strong>mọi</strong> bảng điều khiển. Điều này <span>nhằm tránh tình trạng không nhất quán (xuất hiện phổ biến hơn khi so sánh dữ liệu với SRN).</span><span></span> </li></ul></td></tr></tbody></table>

## Công việc thiết lập

Quy trình công việc dưới dây liệt kê các hoạt động cần thiết để thiết lập tùy chọn mong muốn. Các công việc được phân ra giữa nhà tiếp thị và nhà phát triển.

Đối với tùy chọn Bảng điều khiển cho mỗi cửa hàng, hãy lặp lại các công việc cho mỗi cửa hàng.

Trước khi bạn bắt đầu:

* Quyết định về quy ước đặt tên cho các thông số channel và install\_app\_store.
* Sử dụng bảng đặt tên dưới đây để ánh xạ các kênh và cửa hàng.
* Bảng này được nhà phát triển sử dụng để chuẩn bị APK.

<table><thead><tr><th>Tham số</th><th><p>Hướng dẫn</p></th><th><p>Bảng điều khiển duy nhất<br/> [Phương pháp thực hành tốt nhất]</p></th><th>Bảng điều khiển cho mỗi cửa hàng</th></tr></thead><tbody><tr><td>Tên gói Android</td><td>Tên gói giống hệt nhau cho tất cả các tùy chọn bảng điều khiển</td><td colspan="2">Nếu ứng dụng đã có trong Cửa hàng Google Play, hãy sử dụng tên gói hiện tại. Ví dụ: comb.abc.def</td></tr><tr><td>Tên kênh</td><td>Một giá trị duy nhất cho mỗi cửa hàng.</td><td><p>Chưa được thiết lập. Để trống. </p></td><td><p>Duy nhất cho mỗi cửa hàng. Đặt giá trị trong APK được chuẩn bị riêng cho cửa hàng và khi thêm ứng dụng vào AppsFlyer. </p><p>Không cài đặt kênh cho APK Cửa hàng Google Play. </p></td></tr><tr><td>Cài đặt cửa hàng ứng dụng AF_STORE</td><td>Một giá trị duy nhất xác định cửa hàng</td><td><p><span>Duy nhất cho mỗi cửa hàng. Đặt trong APK thông qua tệp tin kê khai. Mỗi cửa hàng sẽ có APK riêng. </span></p></td><td> Chưa được thiết lập</td></tr></tbody></table>

Công việc

| Bước | Trách nhiệm | Bảng điều khiển duy nhất | Bảng điều khiển cho mỗi cửa hàng |
| --- | --- | --- | --- |
| 1 | Nhà phát triển | [Chuẩn bị APK](/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation) | [Chuẩn bị APK](/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation) |
| 2 | Nhà tiếp thị | Không yêu cầu hành động. Giả định ứng dụng đã hoạt động trong AppsFlyer. | [Thêm ứng dụng](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app) trong AppsFlyer. |
| 3 | Nhà tiếp thị | [Chuẩn bị đường dẫn phân bổ](/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links) | Chuẩn bị đường dẫn phân bổ kèm theo ID ứng dụng đã kết hợp với tên kênh. Thực hiện điều này thông qua trang **Active integrations** như thông thường. |
| 4 | Nhà phát triển và nhà tiếp thị | [Thử nghiệm](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) | [Thử nghiệm](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) |

## Quy trình

<div id="single-dashboard-apk-preparation" />

<Accordion title="Bảng điều khiển duy nhất—Chuẩn bị APK">

Tên gói Android xác định bảng điều khiển nào sẽ chứa dữ liệu phân bổ. Trong phương thức bảng điều khiển duy nhất, tất cả các cửa hàng có tên gói Android giống hệt nhau. Không có khái niệm về thông số kênh ở đây.

Việc xác định cửa hàng tải xuống là bằng thông số AF\_STORE được đặt trong SDK, như được mô tả trong phần này.  Thông số AF\_STORE không phân biệt chữ hoa chữ thường. Ví dụ: ABC, abc, Abc.

**Để chuẩn bị APK:**

1. Tạo một bản sao của bản dựng Ứng dụng. **Lưu ý**: Không thay đổi tên gói Android.
2. Để xác định cửa hàng riêng lẻ, hãy sử dụng một trong các phương thức sau:
   * **Phương thức tập tin kê khai:** Thêm nội dung sau vào thẻ `<application>` của AndroidManifest.xml để xác định cửa hàng. Đặt thông số AF\_STORE thành tên cửa hàng ứng dụng.

     ```xml
     <application>
        ...
        <meta-data android:name="AF_STORE" android:value="enter_store_name_here"/>
        ...
     </application>
     ```

     **--HOẶC--**
   * **Phương thức API:** Chuẩn bị một APK riêng cho từng cửa hàng ứng dụng thay thế. Gọi API setOutOfStore để cài đặt giá trị AF\_STORE. Cài đặt một giá trị duy nhất cho mỗi cửa hàng.  

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("enter_store_name_here")
     ```

Giá trị được đặt ở đây xuất hiện trong trường install\_app\_store dữ liệu thô của AppsFlyer. Trường này có sẵn trong:

* Bảng điều khiển tổng quan
* Bảng điều khiển nhóm người
* <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Báo cáo dữ liệu thô</Anchor> (Báo cáo dữ liệu thô là một tính năng cao cấp của AppsFlyer)

</Accordion>

<div id="single-dashboard-attribution-links" />

<Accordion title="Bảng điều khiển duy nhất—đường dẫn phân bổ">

1. Đi đến **Configuration** > **Active Integrations** và chọn mạng quảng cáo.
2. Trong thẻ **Attribution Link**, đặt thông số **Out-of-store URL**. Thao tác này sẽ điền macro `af_r` trên đường dẫn phân bổ để chuyển hướng người dùng đến đúng trang đích của cửa hàng ứng dụng. Ví dụ, `&af_r=http://www.destinationurl.com` URL mặc định được đặt trong trang <Anchor target="_blank" href="/marketers/vi/docs/app-settings">App Settings</Anchor>. Nếu tùy chọn này không khả dụng trong trang App Settings, hãy yêu cầu CSM bật cho bạn.
3. Điền macro af\_r với URL trang đích của cửa hàng.
4. Đặt <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#thông-số-đường-dẫn-phân-bổ">thông số đường dẫn phân bổ</Anchor> bổ sung.
5. Các nguồn truyền thông ngoài cửa hàng **sử dụng khớp ID để phân bổ** và <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-attribution-model#probabilistic-modeling">mô hình Xác suất</Anchor> AppsFlyer đóng vai trò là một phương thức dự phòng.
6. Thêm một hoặc nhiều phần giữ chỗ ID người dùng vào URL liên kết:
   * android\_id
   * advertising\_id
   * OAID
7. Sao chép đường dẫn phân bổ và cung cấp cho đối tác mạng quảng cáo.

</Accordion>

<div id="dashboard-per-store-apk-preparation" />

<Accordion title="Bảng điều khiển cho mỗi cửa hàng—Chuẩn bị APK">

Tên gói Android kết hợp với thông số kênh được đặt trong tệp tin kê khai xác định bảng điều khiển cửa hàng nào sẽ chứa dữ liệu phân bổ.

**Để chuẩn bị một APK/tệp tin kê khai riêng cho mỗi cửa hàng:**

* Thêm nội dung sau vào thẻ `<application>` của AndroidManifest.xml để xác định cửa hàng. Đặt thông số CHANNEL thành tên cửa hàng ứng dụng.

  ```xml
  <application>
       ...
       <meta-data android:name="CHANNEL" android:value="enter_store_name_here"/>
       ...
  </application>
  ```

  **Lưu ý:** Thông số có phân biệt chữ hoa chữ thường.

</Accordion>

<div id="dashboard-per-store-adding-the-app" />

<Accordion title="Bảng điều khiển cho mỗi cửa hàng—thêm ứng dụng">

Thêm bảng điều khiển (ứng dụng) được xác định bằng cách kết hợp tên gói Android và kênh được đặt trong APK/tệp tin kê khai. Ví dụ: Tên gói Android là com.myapp và tên kênh là abcstore thì tên bảng điều khiển duy nhất là com.myapp—abcstore.

**Để thêm bảng điều khiển cho mỗi cửa hàng trong AppsFlyer**:

1. Đi đến **My apps** và nhấp vào **Add app**.
2. Chọn **Android > In 3rd-party store.**
3. Hoàn thành:
   * **Android package name:** Tên gói đúng như tên được hiển thị trong gói ứng dụng.
   * **Channel name:** Mã định danh duy nhất (tên cửa hàng) để phân biệt giữa các bảng điều khiển trùng tên gói. Xác minh rằng bạn sử dụng cùng giá trị trong APK được chuẩn bị cho cửa hàng.  
     **Lưu ý:** Đối với tên kênh, bạn chỉ được sử dụng chữ hoa hoặc chữ thường (a-z hoặc A-Z). Không sử dụng các ký tự khác, chẳng hạn như dấu gạch ngang (-) hoặc dấu gạch dưới (\_).
   * **App URL:**
     * Chứa địa chỉ tải xuống URL mặc định mà sẽ điền macro af\_r trên các đường dẫn phân bổ. Nhập URL lưu trữ APK hoặc URL trang đích của APK.
     * Bạn có thể thay đổi địa chỉ này theo từng đường dẫn phân bổ khi tạo.
     * Nếu để trống trường này, bạn sẽ không thể thiết lập trang mặc định trong tương lai.
4. Nhấp vào **Next**.
5. Làm theo các hướng dẫn trong giao diện để hoàn tất việc thêm ứng dụng.

</Accordion>

<div id="testing-both-dashboard-options" />

<Accordion title="Thử nghiệm—cả hai tùy chọn bảng điều khiển">

#### **Các lượt Cài đặt không tự nhiên**

**Để thử nghiệm lượt cài đặt không tự nhiên:**

1. Sử dụng một thiết bị Android chưa cài đặt ứng dụng của bạn hoặc <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices">đăng ký thiết bị</Anchor>.
2. Tạo đường dẫn phân bổ thử nghiệm bằng <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">liên kết OneLink</Anchor>. Dùng test làm tên Nguồn truyền thông ("&pid=test").
3. Thêm ID quảng cáo là GAID, OAID hoặc ID Android vào URL nhấp.

   ```http
   http://app.appsflyer.com/com.greatapp?pid=test
   &af_r=http://www.destinationurl.com&advertising_id=b5a3-78d9b5-0f12345-xxxx
   ```

   Gửi liên kết phân bổ cho chính bạn qua email và nhấp vào liên kết. **Sau khi được chuyển hướng, không cài đặt từ cửa hàng**. Thay vào đó, hãy cài đặt ứng dụng phiên bản beta được cập nhật với SDK phân bổ của AppsFlyer được nhúng và khởi chạy nó.

| Bảng điều khiển duy nhất | Bảng điều khiển cho mỗi cửa hàng |
| --- | --- |
| <ol><li>Kiểm tra báo cáo dữ liệu thô cho cài đặt của ứng dụng của bạn trong trang Xuất Dữ liệu.</li><li>Bạn sẽ thấy một lượt chuyển đổi cài đặt với nguồn truyền thông thử nghiệm. Trong cột có tiêu đề **Install App Store** (Cài đặt Cửa hàng Ứng dụng), bạn sẽ thấy tên của cửa hàng như tên xuất hiện ở tệp tin manifest.xml.</li><li>Bạn cũng có thể thấy thông số "af\_installstore": "STORE\_NAME" trong nhật ký cài đặt.</li></ol> | <ol><li>Đi đến ứng dụng cần thiết cho mỗi bảng điều khiển cửa hàng.</li><li>Kiểm tra báo cáo dữ liệu thô cho cài đặt của ứng dụng của bạn trong trang Xuất Dữ liệu hoặc xem trang tổng quan của ứng dụng.</li><li>Bạn sẽ thấy một lượt chuyển đổi cài đặt với nguồn truyền thông "thử nghiệm".</li></ol> |

#### **Lượt cài đặt tự nhiên**

**Để thử nghiệm lượt cài đặt tự nhiên:**

1. Sử dụng một thiết bị Android chưa cài đặt ứng dụng của bạn hoặc chưa được <Anchor target="_blank" href="/marketers/vi/docs/registering-test-devices">đăng ký</Anchor>.
2. Cài đặt ứng dụng phiên bản beta được cập nhật có nhúng SDK phân bổ của AppsFlyer và khởi chạy nó.
3. Kiểm tra kết quả:

#### Kết quả mong đợi

| Bảng điều khiển duy nhất | Bảng điều khiển cho mỗi cửa hàng |
| --- | --- |
| Kiểm tra trang tổng quan của ứng dụng của bạn xem có lượt cài đặt tự nhiên mới không (trong nguồn truyền thông "organic"). Hiện tại, với phương thức ứng dụng duy nhất, không có dấu hiệu nào cho thấy nguồn gốc của cài đặt tự nhiên. | <ol><li>Chuyển đến bảng điều khiển và trang tổng quan của ứng dụng dành riêng cho cửa hàng được thử nghiệm.</li><li>Bạn sẽ thấy một lượt chuyển đổi cài đặt trong phần nguồn truyền thông "tự nhiên".</li></ol> |

</Accordion>

## Tính năng bổ sung

<div id="migrating-from-dashboard-per-store-to-single-dashboard" />

<Accordion title="Di chuyển từ Bảng điều khiển cho mỗi cửa hàng sang bảng điều khiển duy nhất">

**Để di chuyển từ nhiều bảng điều khiển sang bảng điều khiển duy nhất**:

Chuẩn bị APK mới cho các cửa hàng bằng cách sử dụng các hướng dẫn phương thức bảng điều khiển duy nhất có trong bài viết này.

</Accordion>

<div id="driving-users-to-the-amazon-app-store-from-facebook" />

<Accordion title="Hướng người dùng từ Facebook đến cửa hàng ứng dụng của Amazon">

1. Cấu hình liên kết URL tới ứng dụng trong mục cài đặt của ứng dụng Meta, trong phần **Android**.
2. Đăng nhập vào Meta với tư cách là quản trị viên ứng dụng, đi đến <Anchor target="_blank" href="https://developers.facebook.com/apps/">https://developers.facebook.com/apps/</Anchor> và chọn ứng dụng.
3. Chuyển đến cài đặt và tìm cài đặt Android của bạn hoặc nếu bạn chưa định cấu hình Android, hãy thêm nền tảng.
4. Điền vào các chi tiết cần thiết, bao gồm URL cửa hàng ứng dụng amazon dành riêng cho ứng dụng của bạn.   

    [![outofstore_1.png](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)
5. Trong bảng điều khiển AppsFlyer, bên dưới Active Integrations, chọn Meta ads và nhập cùng một ID Ứng dụng Facebook mà bạn sử dụng khi ghi lại Quảng cáo Cài đặt Ứng dụng Di động Trong Cửa hàng của Meta với AppsFlyer.

</Accordion>

<div id="getting-the-data-appsflyer-reports" />

<Accordion title="Lấy dữ liệu - Báo cáo bổ sung của AppsFlyer">

Ngoài bảng điều khiển Tổng quan, bạn có thể sử dụng các phương thức báo cáo sau trong AppsFlyer.

* Nhóm người:
  * Kết hợp nhiều bảng điều khiển (ứng dụng) trong một báo cáo duy nhất
  * Xem hiệu suất của mỗi bảng điều khiển bằng cách phân tích theo install\_app\_store
* API Pull (đối với phương thức ứng dụng duy nhất): Dữ liệu thô lượt cài đặt <Anchor target="_blank" href="/marketers/vi/docs/pull-api-aggregate-data">API Pull</Anchor> không chứa **Install App Store** (Cài đặt Cửa hàng Ứng dụng) theo mặc định. Để bao gồm cột, hãy thêm dòng sau vào lệnh gọi API Pull: `&additional_fields=install_app_store`
* Bảng điều khiển tùy chỉnh (đối với phương thức nhiều ứng dụng): Nếu bạn sử dụng phương pháp nhiều bảng điều khiển, hãy sử dụng <Anchor target="_blank" href="/marketers/vi/docs/custom-dashboards">bảng điều khiển tùy chỉnh</Anchor> để kết hợp dữ liệu hiệu suất từ nhiều ứng dụng vào một nơi.

</Accordion>

<div id="referrer-implementation-thirdparty-android-app-stores" />

<Accordion title="Thực hiện liên kết giới thiệu—cửa hàng ứng dụng Android của bên thứ ba">

* Phân bổ liên kết giới thiệu được hỗ trợ liên quan đến Google Play và các cửa hàng bên thứ ba được liệt kê tại đây.
* Hầu hết cửa hàng ứng dụng của bên thứ ba không cần bất kỳ cài đặt hoặc cấu hình nào khác. Đối với Xiaomi, cần cấu hình bổ sung phần phụ thuộc. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#xiaomi-getapps-store-referrer">Tìm hiểu thêm</Anchor>
* Phân bổ theo liên kết giới thiệu cửa hàng của bên thứ ba được phản ánh trong báo cáo dữ liệu thô như sau:
  * Loại so khớp: tên của cửa hàng bên thứ ba được phân bổ. Ví dụ: huawei\_referrer.
  * Người đóng góp: Nếu người dùng tương tác với nhiều cửa hàng ứng dụng trước khi cài đặt ứng dụng thì AppsFlyer sẽ coi những lượt tương tác này là người đóng góp. Lượt cài đặt này sẽ được ghi nhận cho lượt tương tác nhấp chuột gần cuối cùng. Ví dụ:
    * Người dùng nhấp vào một quảng cáo do Google phân bổ và được chuyển hướng đến Cửa hàng Play. Người dùng không tải xuống ứng dụng.
    * Người dùng nhấp vào một quảng cáo khác và được chuyển hướng đến cửa hàng Samsung Galaxy. Người dùng tải xuống và cài đặt ứng dụng.
    * Phân bổ được tính cho mạng quảng cáo chuyển hướng người dùng đến cửa hàng Samsung Galaxy; Google được ghi nhận là người đóng góp.

Cửa hàng Android bên thứ ba có tích hợp phân bổ người giới thiệu với AppsFlyer

| Cửa hàng ứng dụng của bên thứ ba | Bắt đầu từ | Phiên bản SDK |
| --- | --- | --- |
| <span id="huawei-app-store"></span>Cửa hàng ứng dụng của Huawei | Tháng 7 năm 2020 | 5.4.6+, 6.1.1 + |
| <span id="samsung-galaxy-store"></span>Cửa hàng Samsung Galaxy | Tháng 12 năm 2020 | 6.1.1 + |
| <span id="xiaomi-getapps-store"></span>Cửa hàng Xiaomi GetApps | Tháng 9 năm 2022 | 6.9.0 + |

<div id="troubleshooting" />

<Accordion title="Xử lý sự cố">

### Các lượt cài đặt được phân bổ cho ứng dụng mặc định

Nếu bạn tạo một APK ứng dụng với cài đặt kênh nhưng không tạo bảng điều khiển cho APK ứng dụng trong tài khoản AppsFlyer: Lượt cài đặt được phân bổ cho ứng dụng mặc định, thường là ứng dụng Google Play Store trong tài khoản của bạn. Nếu không có ứng dụng mặc định thì sẽ không có dữ liệu nào được ghi nhận cho ứng dụng.

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Lưu ý |
| --- | --- |
| Chuyển hướng OneLink đến nhiều cửa hàng ứng dụng | Bạn có thể đặt nhiều cửa hàng ứng dụng trên <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template#quy-trình">mẫu OneLink</Anchor> nếu tên gói ứng dụng giống nhau trong tất cả các cửa hàng ứng dụng và triển khai tùy chọn bảng điều khiển duy nhất. |
| Cài đặt cửa hàng ứng dụng | Thông số này không dành cho các đại lý hoặc mạng quảng cáo. |

</Accordion>

<div data-zendesk-anchors="multistore-android-attribution=ph%C3%A2n-b%E1%BB%95-android-nhi%E1%BB%81u-c%E1%BB%ADa-h%C3%A0ng single-dashboard-vs-dashboard-per-store=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-duy-nh%E1%BA%A5t-so-v%E1%BB%9Bi-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-cho-m%E1%BB%97i-c%E1%BB%ADa-h%C3%A0ng reporting-options-available-having%C2%A0install_app_store-field=reporting-options-available-having-install_app_store-field setup-tasks=c%C3%B4ng-vi%E1%BB%87c-thi%E1%BA%BFt-l%E1%BA%ADp procedures=quy-tr%C3%ACnh single-dashboard%E2%80%94apk-preparation=single-dashboard-apk-preparation single-dashboard%E2%80%94attribution-links=single-dashboard-attribution-links dashboard-per-store%E2%80%94apk-preparation=dashboard-per-store-apk-preparation dashboard-per-store%E2%80%94adding-the-app=dashboard-per-store-adding-the-app testing%E2%80%94both-dashboard-options=testing-both-dashboard-options nonorganic-installs=c%C3%A1c-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-kh%C3%B4ng-t%E1%BB%B1-nhi%C3%AAn organic-installs=l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-t%E1%BB%B1-nhi%C3%AAn expected-results=k%E1%BA%BFt-qu%E1%BA%A3-mong-%C4%91%E1%BB%A3i additional-features=t%C3%ADnh-n%C4%83ng-b%E1%BB%95-sung referrer-implementation%E2%80%94thirdparty-android-app-stores=referrer-implementation-thirdparty-android-app-stores installs-attributed-to-the-default-app=c%C3%A1c-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A2n-b%E1%BB%95-cho-%E1%BB%A9ng-d%E1%BB%A5ng-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh" />
