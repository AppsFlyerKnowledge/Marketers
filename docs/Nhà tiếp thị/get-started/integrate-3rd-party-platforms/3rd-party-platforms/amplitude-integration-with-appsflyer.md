---
title: Tích hợp Amplitude với AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Amplitude
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-08-02T05:18:03Z'
  edited_at: '2023-10-08T11:40:02Z'
  id: 211200306
  locale: vi
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/vi/articles/211200306
---
> **Khái quát:** Amplitude, một đối tác tích hợp của AppsFlyer, cung cấp các dịch vụ phân tích sản phẩm để giúp các công ty web và di động hiểu rõ hành vi của người dùng. Các nhóm sản phẩm, tiếp thị và phát triển sử dụng Amplitude để khám phá và chia sẻ thông tin chi tiết về việc thu hút, giữ chân người dùng và doanh thu.

> 🚧 **Quan trọng!**
>
> <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions#hạn-chế-nguồn-truyền-thông">Một số nguồn truyền thông</Anchor> hạn chế chia sẻ dữ liệu với các bên thứ ba. Do đó, đăng lại cho các sự kiện bị hạn chế sẽ không được gửi tới đối tác này, bất kể lựa chọn đã định cấu hình để gửi đăng lại là gì.

## Thiết lập Amplitude

Quá trình thiết lập được thực hiện từ trang **Tích hợp hoạt động** (Active Integrations),nhưng để tìm đối tác, trước tiên bạn phải truy cập vào <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations">thị trường</Anchor> (marketplace).

> 📘 **Lưu ý**
>
> Trước khi thiết lập tích hợp, hãy nhớ <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#liên-hệ-với-đối-tác">liên hệ với đối tác</Anchor> và mở tài khoản với họ.

**Để kích hoạt tích hợp:**

1. Từ menu trên cùng của bất kỳ trang AppsFlyer nào, hãy nhấp vào **Marketplace**.
2. Tìm kiếm và chọn đối tác.
3. Nhấp vào **Set up integration**. Bạn được chuyển đến trang thiết lập tích hợp.
4. Trong thẻ **Integration**, chọn ứng dụng cho tích hợp và bật **Activate partner**.  
   **Lưu ý:** Nút bật/tắt phải luôn ở trạng thái bật <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">(được kích hoạt)</Anchor> trong thời gian bạn làm việc với đối tác.
5. Hoàn thành cấu hình bằng cách sử dụng các tab có liên quan, như được mô tả bên dưới.

Để biết mô tả chi tiết về Tiêu đề Cửa sổ Cấu hình Đối tác, hãy nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">đây</Anchor>.

<div id="integration-tab" />

<Accordion title="Tab tích hợp">

Thẻ Integration được chia thành các phần khác nhau như được mô tả dưới đây.

<div id="activate-partner" />

### Kích hoạt đối tác

Trong **lần đầu truy cập** tại đây, bạn sẽ cần phải bật **Activate Partner** để kích hoạt việc thiết lập các thông số của thẻ tích hợp. Nút bật/tắt phải luôn ở trạng thái bật trong thời gian bạn làm việc với đối tác.  
Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">kích hoạt đối tác</Anchor>.

<div id="general-settings" />

### Cài đặt chung

<div id="advanced-data-sharing" />

#### Chia sẻ dữ liệu nâng cao

Để chia sẻ thông tin cài đặt bổ sung với Amplitude, hãy bật **Advanced data sharing**. Sau khi bật, Amplitude nhận được dữ liệu sau cho các lượt cài đặt (không phải sự kiện trong ứng dụng) được ánh xạ tới Thuộc tính Amplitude được liệt kê:

| Thuộc tính Amplitude | Điểm Dữ liệu AppsFlyer |
| --- | --- |
| sub\_publisher | af\_siteid |
| network\_name | pid |
| adgroup\_name | af\_adset |
| creative\_name | af\_ad\_id |
| installed\_at | install\_timestamp |
| search\_term | af\_keywords |
| kênh | af\_channel |
| user\_id | af\_customer\_user\_id |
| af\_sub1 | af\_sub1 |
| af\_sub2 | af\_sub2 |
| app\_version | app\_version |

<div id="amplitude-eu-data-center" />

#### Trung tâm Dữ liệu Liên minh Châu Âu của Amplitude

Khi **Amplitude EU Data Center** ở trạng thái tắt, bài đăng lại lượt cài đặt sẽ được gửi đến trung tâm dữ liệu của Hoa Kỳ.  
Để gửi các bài đăng lại lượt cài đặt tới trung tâm dữ liệu Liên minh Châu Âu của Amplitude, hãy bật Amplitude EU Data Center.

<div id="api-key" />

#### Mã khóa API

Amplitude kết nối với AppsFlyer thông qua Mã khóa API duy nhất. Nếu chưa có, bạn phải lấy mã khóa này từ Amplitude để tiếp tục tiến hành tích hợp hoặc làm theo các bước bên dưới.

<span id="obtaining-the-api-key-from-amplitude"></span>**Nhận mã khóa API từ Amplitude**

**Lưu ý**: Chỉ những người dùng có vai trò Quản trị viên hoặc Người quản lý trên Amplitude mới có thể truy cập Mã khóa API.

1. Đăng nhập vào tài khoản Amplitude của bạn.
2. Từ trên cùng bên phải của trang, nhấp vào biểu tượng cài đặt > **Organization Settings**.  

   <Image align="center" alt="Amplitude" src="https://files.readme.io/214df773c045239924b65a4a1e6b0a1957f6b7ea09e225af80d83ffa0a469c26-16258070772625.png" width="240px" />
3. Nhấp vào **Projects** và chọn dự án để gửi dữ liệu đến AppsFlyer từ dự án đó.   

   <Image align="center" alt="amplitude" src="https://files.readme.io/eaf158e4505f47f8da0fdae4f97be773ab32910352b50cab5ca5d4de3e8782ac-16335170399505.png" />
4. Từ thẻ **Project**, sao chép mã khóa API của bạn.  

   <Image align="center" alt="Amplitude" src="https://files.readme.io/cf65648a9a8c122febe2b36fd4bd0b9f7f436cac49cfeec7f41870f614a16c6c-16258070773649.png" width="648px" />
5. Tiếp tục cấu hình Amplitude trong Bảng điều khiển AppsFlyer.

<div id="default-postbacks" />

### Postback Mặc định

AppsFlyer chỉ gửi các đăng lại tự động tới các lượt cài đặt của người dùng Amplitude khi chúng được phân bổ cho Amplitude.

<div id="in-app-event-settings" />

### Cài đặt sự kiện trong ứng dụng

* Nhập Mã khóa API.
* Khi **Amplitude Data Center** ở trạng thái tắt, đăng lại sự kiện trong ứng dụng sẽ được gửi đến trung tâm dữ liệu của Hoa Kỳ.  
  **Để gửi các đăng lại sự kiện trong ứng dụng tới trung tâm dữ liệu Liên minh Châu Âu của Amplitude, hãy bật Amplitude Data Center.**

Khi bạn đã lưu cấu hình, AppsFlyer sẽ gửi dữ liệu sau tới Amplitude:

* ID Thiết bị (IDFV/ID Quảng cáo của Google)
* Nguồn truyền thông
* Tên chiến dịch

Gửi IDFA cho các thiết bị iOS phải tuân theo <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">quyết định có đồng ý ATT hay không của người dùng và cài đặt Quyền riêng tư Nâng cao</Anchor>.

<div id="in-app-event-postbacks" />

### Đăng lại sự kiện trong ứng dụng

<Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#g">Định cấu hình gửi đăng lại sự kiện trong ứng dụng</Anchor> tới Amplitude.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Tab Liên kết Phân bổ">

Đường dẫn phân bổ không khả dụng đối với Amplitude.

</Accordion>

<div id="cost-tab" />

<Accordion title="Tab Chi phí">

Dữ liệu chi phí không được hỗ trợ khi tích hợp với đối tác này.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Tab Doanh thu quảng cáo">

Doanh thu quảng cáo không được hỗ trợ khi tích hợp với đối tác này.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Tab quyền truy cập">

Quyền không khả dụng đối với Amplitude.

</Accordion>

<div id="sending-amplitude-events-to-appsflyer" />

<div id="important-1" />

<div id="viewing-attribution-data-in-the-amplitude-console" />

## Xem dữ liệu phân bổ trong bảng điều khiển của Amplitude

Dữ liệu phân bổ được gửi từ AppsFlyer đến Amplitude được hiển thị trong bảng điều khiển của bạn dưới dạng các sự kiện và thuộc tính có tiền tố là **[AppsFlyer]**:

<Image align="center" alt="amplitude-properties.png" src="https://files.readme.io/bf52831ea6060172ce251136f47962ffb7f1ec9ffce13b9e35c614c4178e77f1-360009623597.png" />

> 🚧 **Quan trọng!**
>
> * Để ngăn ngừa sự cố khớp với lượt cài đặt và sự kiện trong ứng dụng, hãy bật **Amplitude HTTP API** cho các đăng lại lượt cài đặt. Nếu không, nếu sự kiện trong ứng dụng đầu tiên sau quá trình cài đặt xảy ra 72 giờ sau khi cài đặt, Amplitude sẽ không khớp lượt cài đặt với các sự kiện trong ứng dụng sau. Trong trường hợp này, Amplitude sẽ loại bỏ sự kiện cài đặt nhưng hiển thị các sự kiện trong ứng dụng (tất cả diễn ra sau 72 giờ).
> * Trong một số trường hợp, Amplitude hiển thị dữ liệu đến từ AppsFlyer là "Bị chặn". Nếu bạn không thể thấy dữ liệu AppsFlyer trong Amplitude, hãy kiểm tra xem dữ liệu đó có được xác định là sự kiện bị chặn hay không.![amplitude-blocked-data.png](https://files.readme.io/61312c421d4baff8126676f7b579489a6ba7580f7cdff71020c1bc68cf71fe42-4409532783889.png)

<div data-zendesk-anchors="01H8KPA9JJDP2945TQJT1Z3EY2=quan-tr%E1%BB%8Dng setting-up-amplitude=thi%E1%BA%BFt-l%E1%BA%ADp-amplitude 01H8KPA9JJXHMEYD8HD9DKK6D1=thi%E1%BA%BFt-l%E1%BA%ADp-amplitude 01H8KPA9JJG0MNK2EK75XVZBHX=l%C6%B0u-%C3%BD 01H8KPA9JK6XTFR0XW91XZB5XR=integration-tab activate-partner=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c 01H8KPA9JKDRA680Y0WPZ172EM=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c general-settings=c%C3%A0i-%C4%91%E1%BA%B7t-chung 01H8KPA9JKF4VCA4S22SYT40WT=c%C3%A0i-%C4%91%E1%BA%B7t-chung advanced-data-sharing=chia-s%E1%BA%BB-d%E1%BB%AF-li%E1%BB%87u-n%C3%A2ng-cao 01H8KPA9JKJ2XN1AEPV74QVJYZ=chia-s%E1%BA%BB-d%E1%BB%AF-li%E1%BB%87u-n%C3%A2ng-cao amplitude-data-center=trung-t%C3%A2m-d%E1%BB%AF-li%E1%BB%87u-li%C3%AAn-minh-ch%C3%A2u-%C3%A2u-c%E1%BB%A7a-amplitude 01H8KPA9JKP0T0FDND97VA23EY=trung-t%C3%A2m-d%E1%BB%AF-li%E1%BB%87u-li%C3%AAn-minh-ch%C3%A2u-%C3%A2u-c%E1%BB%A7a-amplitude api-key=m%C3%A3-kh%C3%B3a-api 01H8KPA9JKDYDPDGRXZSH2BAV8=m%C3%A3-kh%C3%B3a-api 01H8KPA9JK510YKV47816DT7E7=obtaining-the-api-key-from-amplitude default-postbacks=postback-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh 01H8KRBGYQ973CT3H8GHZ8R0BH=postback-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh inapp-event-settings=c%C3%A0i-%C4%91%E1%BA%B7t-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H8KPA9JKM4S79160BEYN3B6V=c%C3%A0i-%C4%91%E1%BA%B7t-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng inapp-event-postbacks=%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H8KSQ76XE9Z191P1RMANF6EQ=%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H8KPA9JK4D6XX55Q55TBF4QN=attribution-link-tab 01H8KPA9JKK04NNDZA0XTSSWM5=cost-tab 01H8KPA9JK6X04T661D6YBHTVC=ad-revenue-tab 01H8KPA9JKG1VQJJBNFM6Q985X=permissions-tab viewing-attribution-data-in-the-amplitude-console=xem-d%E1%BB%AF-li%E1%BB%87u-ph%C3%A2n-b%E1%BB%95-trong-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-c%E1%BB%A7a-amplitude 01H8KPA9JK75TA0H8T4P65BMSE=xem-d%E1%BB%AF-li%E1%BB%87u-ph%C3%A2n-b%E1%BB%95-trong-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-c%E1%BB%A7a-amplitude 01H8KPA9JK2B4MR26GJZEZJSVT=quan-tr%E1%BB%8Dng-1" />
