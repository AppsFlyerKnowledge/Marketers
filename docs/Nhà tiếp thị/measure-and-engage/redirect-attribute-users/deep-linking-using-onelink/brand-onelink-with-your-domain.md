---
title: Tên miền có Thương hiệu
metadata:
  keywords:
    - Marketers
    - cname
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-08-26T09:00:09Z'
  edited_at: '2023-08-20T13:09:04Z'
  id: 360002329137
  locale: vi
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/vi/articles/360002329137
---
> **Khái quát:** Các nhà quảng cáo sử dụng liên kết OneLink có thể dùng tên miền của riêng họ để gắn thương hiệu vào liên kết này. Điều này cải thiện hiệu suất chiến dịch và tăng khả năng hiển thị thương hiệu.

<Image align="center" alt="Branded_1__3_.jpg" src="https://files.readme.io/20d0a59aa3e896960c9a0faaacad51a58e314073368452e07a7507e0770ca817-30192959736465.png" />

<div id="branded-domains" />

## Tên miền có thương hiệu

* Tên miền có Thương hiệu được sử dụng để gắn thương hiệu trong các đường dẫn phân bổ bằng thương hiệu và tên miền của bạn. Ví dụ như được minh họa trong hình trước:
  * OneLink: abcdef.onelink.me
  * Thương hiệu abcdef.com
  * Tên miền phụ: Ví dụ như ứng dụng
  * Triển khai Tên miền có Thương hiệu và sử dụng miền đầy đủ của bạn với đường dẫn phân bổ là click.abcdef.com
* Tên miền có Thương hiệu cải thiện hiệu suất chiến dịch vì miền:
  * Thúc đẩy niềm tin: Tận dụng thương hiệu của bạn, đảm bảo nhận dạng nhất quán, loại bỏ rào cản khỏi hành trình của người dùng và cải thiện tỷ lệ CTR.
  * Cho phép liên kết sâu sử dụng thương hiệu của bạn.
  * Đơn giản để triển khai và hoạt động giống như OneLink.
  * Đẩy mạnh nhận diện thương hiệu: Thương hiệu của bạn đánh dấu các chiến dịch của bạn, thay vì một liên kết chung.
  * Cho phép các email tránh bị gắn cờ là thư rác do liên kết không khớp với email người gửi.

<div id="principles-of-implementation" />

### Nguyên tắc thực hiện

Triển khai Tên miền có Thương hiệu bằng cách liên kết tên miền đầy đủ được xác định trong Hệ thống Tên Miền (DNS) của bạn với tên miền phụ OneLink (đích đến CNAME của AppsFlyer). Quá trình này được thực hiện bằng cách sử dụng cài đặt tiêu chuẩn trong DNS của bạn và thiết lập Tên miền có Thương hiệu trong AppsFlyer. Ngoài ra, bạn sẽ cần thực hiện một số thay đổi nhỏ trong ứng dụng của mình để hỗ trợ Tên miền có Thương hiệu.

Bạn sẽ cần sự hỗ trợ từ quản trị viên DNS, thường là thành viên trong nhóm CNTT hoặc nhà cung cấp dịch vụ lưu trữ DNS của bạn và nhà phát triển ứng dụng.

Nhiều tên miền đầy đủ có thể được liên kết với một tên miền phụ OneLink. Điều này có nghĩa là bạn có thể có nhiều thương hiệu sử dụng cùng một tên miền phụ OneLink.

<div id="setting-up-branded-domains" />

### Thiết lập Tên miền có Thương hiệu

Hoàn thành danh sách hành động để thiết lập Tên miền có Thương hiệu.

|  | Trách nhiệm | Thao tác | Lưu ý |
| --- | --- | --- | --- |
| 1 | Nhà tiếp thị được hỗ trợ bởi quản trị viên DNS | [Thiết lập Liên kết có Thương hiệu trong AppsFlyer](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) | Quản trị viên DNS, thường là thành viên trong nhóm CNTT hoặc nhà cung cấp dịch vụ lưu trữ DNS của bạn, cần xác định tên miền đầy đủ (còn gọi là máy chủ lưu trữ) và đặt bản ghi CNAME như được mô tả trong quy trình. |
| 2 | Nhà phát triển | [Thiết lập Tên miền có Thương hiệu trong ứng dụng](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app) | Thực hiện những thay đổi nhỏ đối với mã ứng dụng. |
| 3 | Nhà tiếp thị | [Sử dụng và thử nghiệm Tên miền có Thương hiệu](/docs/brand-onelink-with-your-domain#using-and-testing-branded-domains) |  |
| Khi cần thiết | Nhà tiếp thị | [Chỉnh sửa và xóa Tên miền có Thương hiệu](/docs/brand-onelink-with-your-domain#editing-and-deleting-branded-domains) |  |

<div id="custom-ssl-certificate-optional" />

<div id="note-3" />

<div id="note-2" />

<div id="renew-the-7-day-period-for-mapping-the-cname-record" />

<div id="note-1" />

<div id="note" />

<div id="procedures" />

<div id="editing-verifying-and-deleting-branded-domains" />

<div id="delete-a-branded-domain-mapping" />

<div id="domain-cname-record-no-longer-pointing-to-appsflyer" />

<div id="note-5" />

<div id="verify-a-branded-domain-mapping" />

<div id="important" />

<div id="edit-a-branded-domain-mapping" />

<div id="note-4" />

### Quy trình

<div id="set-up-a-branded-domain-in-appsflyer" />

<Accordion title="Thiết lập Tên miền có Thương hiệu trong AppsFlyer">

Thiết lập Tên miền có Thương hiệu bao gồm liên kết bộ tên miền đầy đủ trong DNS của bạn với tên miền phụ OneLink trong AppsFlyer như được mô tả trong hình sau.

**Tên miền có Thương hiệu trỏ đến các máy chủ AppsFlyer**

<Image align="center" alt="Branded2__3_.jpg" src="https://files.readme.io/43bcdbe50ec58af434f404f0216f90ad345b7b1e034cb7d7c80e3c3c4307c1d2-30192946333713.png" />

**Trước khi bạn bắt đầu:**

* Chọn một tên miền đầy đủ, ví dụ như app.abcdef.com, trong đó abcdef.com là thương hiệu của bạn.
  * Bạn còn có thể tùy chỉnh tên miền phụ, chẳng hạn như ứng dụng.
* Yêu cầu quản trị viên DNS tạo tên miền đầy đủ (còn gọi là máy chủ lưu trữ).
* Yêu cầu quản trị viên DNS đặt một bản ghi CNAME sao cho tên miền đầy đủ (Tên miền có thương hiệu) trỏ đến URL được chỉ định (còn gọi là máy chủ lưu trữ AppsFlyer). Điều này được mô tả trong hình Tên miền có Thương hiệu trỏ đến máy chủ AppsFlyer (ở trên).

**Cách ánh xạ tên miền đầy đủ của bạn tới tên miền phụ OneLink**:

1. Đi đến **Experiences & Deep Linking** > **Branded Domains**.
2. Nhấp vào **+ New Branded Domain**.
3. Trong trường **Brand Domain**, hãy nhập tên miền đầy đủ như đã đặt trong DNS. Ví dụ như **click.abcdef.com**  
   Không đặt dấu chấm sau tên miền.
4. Chọn tên miền phụ OneLink từ danh sách được hiển thị. Nếu không có danh sách nào được hiển thị, bạn cần tạo một mẫu OneLink để cung cấp tên miền phụ mặc định.
5. Nhấp vào **Next.**
6. Đặt bản ghi CNAME:
   * Nếu tên miền của bạn được trỏ đúng tới đích đến CNAME trên AppsFlyer, thì "AppsFlyer CNAME was found" sẽ được hiển thị.
   * Nếu không tìm thấy CNAME, hãy sao chép đích đến CNAME trên AppsFlyer và gửi cho quản trị viên DNS của bạn, yêu cầu họ đảm bảo tên miền đầy đủ của bạn trỏ tới đích đến CNAME. Bạn phải trỏ tên miền đầy đủ tới đích đến CNAME trên AppsFlyer. Nếu không, tên miền có thương hiệu sẽ được tạo nhưng không hoạt động.  Nếu bạn đang sử dụng tên miền có thương hiệu cho ESP, trước khi sao chép đích đến CNAME, hãy chọn **Use branded domain for an ESP configuration**.
7. Nhấp vào **Finish**.  
   Giờ đây, bạn có thể tạo các liên kết mới dựa trên mẫu OneLink bằng tên miền có thương hiệu của mình.

**Lưu ý**:

* Nếu bạn đã tạo các liên kết dựa trên mẫu OneLink của mình mà không có tên miền có thương hiệu, các liên kết này vẫn hoạt động.
* Thời gian để tên miền có thương hiệu mới bắt đầu hoạt động có thể lên đến 24 giờ.
* Nếu bạn không đặt bản ghi CNAME trong vòng 7 ngày, thì tên miền có thương hiệu của bạn sẽ hết hạn. Sau đó, bạn cần làm mới tên miền có thương hiệu trước khi có thể sử dụng. Cách làm mới: 
  1. Đi đến **Experiences & Deep Linking** > **Branded Domains.**
  2. Truy cập tên miền có thương hiệu mà bạn muốn làm mới.
  3. Nhấp vào **Refresh.**
  4. Đặt bản ghi CNAME.

</Accordion>

<div id="set-up-branded-domains-in-the-app" />

<Accordion title="Thiết lập Tên miền có Thương hiệu trong ứng dụng">

* Sử dụng các phiên bản SDK sau:  
  * Android V4.10.1 trở lên
  * iOS V4.10.1 trở lên
  * Lượt giới thiệu/lời mời của người dùng (mời bạn bè) yêu cầu SDK phiên bản V5.2.0 trở lên cho cả iOS và Android

**Những điều cần lưu ý khi triển khai SDK của Tên miền có Thương hiệu**

* Khi liên kết sâu diễn ra bằng cách sử dụng Tên miền có Thương hiệu, SDK của AppsFlyer không lấy được dữ liệu chuyển đổi cho các lượt cài đặt và liên kết sâu.
* Để khắc phục điều này, nhà phát triển sử dụng API SDK `setOneLinkCustomDomain` và `oneLinkCustomDomains`, tương ứng cho Android và iOS.
* API này truy vấn tên miền có thương hiệu, lấy tên miền OneLink mà tên miền có thương hiệu được ánh xạ tới và hoàn thành OneLink.

<Tabs>
<Tab title="Android">

Đảm bảo rằng bạn cập nhật <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">bộ lọc ý định</Anchor> của tập tin kê khai để bao gồm tên miền thương hiệu của mình bằng cách đặt android:host.

Sử dụng API này trước khi khởi tạo SDK trong <Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">lớp ứng dụng chung của Android.</Anchor>

**Ví dụ:**

```java
public class AFApplication extends Application {

    @Override
    public void onCreate() {
    super.onCreate();

      // Set branded link domain. Don't include https:// as part of the domain. 
      AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com");
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionListener, this);
      AppsFlyerLib.getInstance().start(this, AF_DEV_KEY);

    }
}
```

Nếu bạn có nhiều tên miền có thương hiệu, hãy chuyển tất cả tên miền đó cho API để đảm bảo rằng bạn luôn lấy được dữ liệu chuyển đổi và có thể liên kết sâu vào ứng dụng.

**Ví dụ:**

```java
AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com", 
                                                        "click.greatapp.com", 
                                                        "deals.greatapp.com");
```

</Tab>

<Tab title="iOS">

<Tabs>
<Tab title="Objective C">

Sử dụng API trong AppDelegate.m, bên trong phương thức didFinishLaunchingWithOptions:

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    /** APPSFLYER INIT **/
    [AppsFlyerLib shared].appsFlyerDevKey = @"SED_DEV_KEY";
    [AppsFlyerLib shared].appleAppID = @"123456789";
    [AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com"];
    //...
    //...
  }
```

Nếu bạn có nhiều tên miền có thương hiệu, hãy chuyển tất cả tên miền đó cho API để đảm bảo rằng bạn luôn lấy được dữ liệu chuyển đổi và có thể liên kết sâu vào ứng dụng.

**Ví dụ:**

```objectivec
[AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com", @"click.greatapp.com"];
```

</Tab>

<Tab title="Swift">

Nên sử dụng API trong AppDelegate.swift, bên trong phương thức didFinishLaunchingWithOptions:

```swift
   func application(_ application: UIApplication, didFinishLaunchingWithOptions 
        launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
          AppsFlyerLib.shared().appsFlyerDevKey = "6CQi4Be6Zs9oNLsCusPbUL"
          AppsFlyerLib.shared().appleAppID = "340954504"
          AppsFlyerLib.shared().oneLinkCustomDomains = ["example.com"]
          //...
          //...
   }
```

Nếu bạn có nhiều tên miền có thương hiệu, bạn có thể chuyển chúng tới API dưới dạng một mảng chuỗi. Điều này đảm bảo rằng bất kể liên kết có thương hiệu nào được sử dụng, bạn luôn lấy được dữ liệu chuyển đổi và có thể liên kết sâu vào ứng dụng.

**Ví dụ:**

```objectivec
AppsFlyerLib.shared().oneLinkCustomDomains = ["promotion.greatapp.com", "click.greatapp.com"]
```

</Tab>
</Tabs>

</Tab>
</Tabs>

</Accordion>

<div id="using-and-testing-branded-domains" />

<Accordion title="Sử dụng và thử nghiệm Tên miền có Thương hiệu">

**Điều kiện tiên quyết**:

Trước khi sử dụng và thử nghiệm, Tên miền có Thương hiệu hoàn thành các bước trong [quy trình Tên miền có Thương hiệu](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app).

**Cách tạo và thử nghiệm các tên miền có thương hiệu:**

1. <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#tạo-liên-kết-onelink">Tạo liên kết OneLink</Anchor> bằng cách sử dụng mẫu OneLink được ánh xạ tới tên miền có thương hiệu.
2. Sao chép đường dẫn phân bổ tùy chỉnh vào trình soạn thảo văn bản.
3. Đường dẫn phân bổ tùy chỉnh được tạo thành từ một tên miền phụ OneLink, ID OneLink và ID Liên kết tùy chỉnh. Thay thế tên miền phụ OneLink bằng tên miền đầy đủ của Tên miền có Thương hiệu. Ví dụ:  

| Đường dẫn phân bổ tùy chỉnh | Tên miền có Thương hiệu |
| --- | --- |
| **abcdef.onelink.me**/A1bc/dc1234ef | **click.abcdef.com**/A1bc/dc1234ef |

4. Sử dụng liên kết có thương hiệu để <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">thử nghiệm lượt cài đặt và liên kết sâu</Anchor>.
5. Nếu bạn sử dụng các báo cáo dữ liệu thô trong quá trình thử nghiệm, trường URL Gốc sẽ được điền bởi liên kết có thương hiệu.

</Accordion>

<div id="editing-and-deleting-branded-domains" />

<Accordion title="Chỉnh sửa và xóa Tên miền có Thương hiệu">

Việc chỉnh sửa cho phép bạn thay đổi ánh xạ của một tên miền đầy đủ hiện có sang một tên miền phụ OneLink khác. Không cần đặt CNAME.

> ❗️ **Chú ý**
>
> Việc sửa đổi Tên miền có Thương hiệu của các chiến dịch đang hoạt động có thể thay đổi hoặc vô hiệu hóa chức năng của liên kết.

**Cách chỉnh sửa ánh xạ tên miền có thương hiệu:**

1. Đi đến **Experiences & Deep Linking** > **Branded Domains.**
2. Đi đến tên miền có thương hiệu mà bạn muốn chỉnh sửa.
3. Nhấp vào **Edit**.

**Cách xóa ánh xạ tên miền có thương hiệu:**

* Liên hệ với CSM AppsFlyer của bạn hoặc <Anchor target="_blank" href="hello@appsflyer.com">hello@appsflyer.com</Anchor>.

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## Khắc phục sự cố, đặc điểm và hạn chế

<div id="troubleshooting" />

<Accordion title="Xử lý sự cố">

| Dấu hiệu | Nguyên nhân/giải pháp |
| --- | --- |
| Tên miền có Thương hiệu không được ánh xạ tới mẫu OneLink | <ul><li>**Tên miền không hợp lệ:** Khi ánh xạ Tên miền có Thương hiệu tới mẫu OneLink, AppsFlyer cố gắng xác minh rằng liên kết có thương hiệu có tên miền hợp lệ. Một tên miền hợp lệ sẽ có định dạng click.abdef.com</li><li>**Tên miền có Thương hiệu đã được ánh xạ**: Chỉ có thể ánh xạ một tên miền đầy đủ một lần.</li></ul> |
| Tên miền có Thương hiệu không liên kết sâu vào ứng dụng | <ul><li>[Xác minh rằng Tên miền có Thương hiệu đang hoạt động](/docs/brand-onelink-with-your-domain#troubleshooting)</li><li>**Xác minh CNAME**: Đảm bảo rằng bản ghi CNAME trỏ từ Tên miền có Thương hiệu của bạn đến AppsFlyer.</li><li>**Xác minh cài đặt liên kết sâu cho mẫu OneLink**: Có thể xảy ra sự cố với cài đặt liên kết sâu OneLink. Đảm bảo thiết lập liên kết sâu với OneLink.</li><li>**Ánh xạ OneLink đã thay đổi**: Bạn có thể chỉnh sửa Tên miền có Thương hiệu và ánh xạ tới một OneLink khác. Nếu OneLink mới ánh xạ có cài đặt liên kết sâu khác hoặc không có cài đặt liên kết sâu, thì liên kết sâu có thể không hoạt động.</li></ul> |
| Không có lượt cài đặt nào được đo lường từ Tên miền có Thương hiệu | <ul><li>**Kiểm tra cài đặt mẫu OneLink**: Đảm bảo rằng tên miền phụ OneLink đã sử dụng để ánh xạ tới tên miền có thương hiệu được liên kết với đúng ứng dụng.</li><li>**Tên miền phụ OneLink đã thay đổi:** Nếu bạn ánh xạ một tên miền có thương hiệu tới mẫu OneLink và tên miền phụ OneLink thay đổi, quá trình phân bổ có thể bị ảnh hưởng.</li><li>**Đảm bảo triển khai:** Của API setOneLinkCustomDomain trong ứng dụng.</li></ul> |
| Không có lượt thu hút nào được ghi nhận từ các tên miền có thương hiệu | Đảm bảo rằng các mục sau đang hoạt động và được cấu hình:<ul><li>Cấu hình liên kết sâu bằng OneLink.</li><li>Ứng dụng sẽ sử dụng [SDK API setOneLinkCustomDomain](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) dành riêng.</li><li><Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide#retargeting-settings">Tính năng Nhắm mục tiêu lại được bật trong cài đặt ứng dụng</Anchor>.</li></ul> |
| Trong quá trình thiết lập Tên miền có Thương hiệu, thông báo **Domain doesn't exist** sẽ được hiển thị | <ol><li>Liên hệ với quản trị viên DNS của bạn và yêu cầu họ điều tra.</li><li>Chờ quản trị viên DNS xác nhận rằng tên miền đã được đăng ký.</li><li>Nhấp vào **Reverify**.</li></ol> |
| Trong quá trình thiết lập Tên miền có Thương hiệu, thông báo **AppsFlyer CNAME not found** sẽ được hiển thị | <ol><li>Yêu cầu quản trị viên DNS đặt một bản ghi CNAME sao cho tên miền đầy đủ (Tên miền có thương hiệu) trỏ đến URL được chỉ định (còn gọi là máy chủ lưu trữ AppsFlyer). Điều này được mô tả trong hình Liên kết có Thương hiệu trỏ đến các máy chủ AppsFlyer trong phần này.</li><li>Chờ quản trị viên DNS xác nhận rằng CNAME đang hoạt động.</li></ol> |
| Lỗi **route\_not\_found** khi sử dụng liên kết tên miền có thương hiệu | Tên miền có thương hiệu không bao gồm mẫu này hoặc bất kỳ thông số nào. Khi sử dụng một tên miền có thương hiệu, bạn phải thêm mẫu hoặc thông số vào cuối URL của tên miền có thương hiệu đó.<br /><br />Ví dụ như nếu "click.abcdef.com" là tên miền có thương hiệu của bạn, chỉ sử dụng "**click.abcdef.com"**, sẽ dẫn đến **route\_not\_found\_error**.<br /><br />Bạn phải thêm các thông số hoặc mẫu vào cuối. Ví dụ như click.abcdef.com **/A1bc/dc1234ef** |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Có ✓ / Không **x** | Nhận xét |
| --- | --- | --- |
| Truy cập mạng quảng cáo | **x** |  |
| Truy cập đại lý | **x** | Các đại lý không thể truy cập phần Tên miền có Thương hiệu để tạo Tên miền có Thương hiệu. Tuy nhiên, họ có thể tạo liên kết OneLink tùy chỉnh bằng một tên miền phụ Tên miền có Thương hiệu. |
| Tính minh bạch của agency | **x** |  |
| Múi giờ cụ thể theo ứng dụng | Không áp dụng |  |
| Tiền tệ cụ thể theo ứng dụng | Không áp dụng |  |
| Giới hạn ký tự | Không áp dụng | Khi nhập tên miền có thương hiệu của bạn, ký tự cuối cùng không được là dấu chấm ("."). |
| Hạn chế về kích thước | Không áp dụng |  |
| Giới hạn tỷ lệ | ✓ | Chứng chỉ SSL/HTTP trong Tên miền có Thương hiệu được AppsFlyer sắp xếp bằng cách sử dụng <Anchor target="_blank" href="https://letsencrypt.org/">Let's Encrypt</Anchor>, với giới hạn đăng ký là 50 chứng chỉ mới mỗi tuần cho mỗi tên miền. |
| Dữ liệu tự nhiên | ✓ |  |
| Dữ liệu không tự nhiên | ✓ |  |
| Tính cập nhật của dữ liệu | Không áp dụng |  |
| Dữ liệu lịch sử | ✓ |  |
| Quyền truy cập tài khoản của người dùng | ✓ |  |
| HTTP | **x** | Giao thức HTTP không được hỗ trợ bởi các liên kết có thương hiệu. Phải sử dụng HTTPS. |

</Accordion>

<div data-zendesk-anchors="branded-domains=t%C3%AAn-mi%E1%BB%81n-c%C3%B3-th%C6%B0%C6%A1ng-hi%E1%BB%87u principles-of-implementation=nguy%C3%AAn-t%E1%BA%AFc-th%E1%BB%B1c-hi%E1%BB%87n setting-up-branded-domains=thi%E1%BA%BFt-l%E1%BA%ADp-t%C3%AAn-mi%E1%BB%81n-c%C3%B3-th%C6%B0%C6%A1ng-hi%E1%BB%87u procedures=quy-tr%C3%ACnh troubleshooting-traits-and-limitations=kh%E1%BA%AFc-ph%E1%BB%A5c-s%E1%BB%B1-c%E1%BB%91-%C4%91%E1%BA%B7c-%C4%91i%E1%BB%83m-v%C3%A0-h%E1%BA%A1n-ch%E1%BA%BF" />
