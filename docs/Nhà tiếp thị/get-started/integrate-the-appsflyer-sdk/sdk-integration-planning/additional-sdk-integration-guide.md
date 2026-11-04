---
title: Tích hợp SDK bổ sung
metadata:
  keywords:
    - iOS
    - Android
    - Integration
    - Advertisers
    - firetv
    - Advertiser
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2021-10-10T11:54:14Z'
  edited_at: '2023-11-02T10:23:51Z'
  id: 4408735106193
  locale: vi
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/vi/articles/4408735106193
---
> **Khái quát:** Xem xét các chức năng SDK bổ sung có sẵn và làm việc với nhà phát triển ứng dụng để triển khai các API như đo lường lượt gỡ cài đặt, phân bổ lời mời người dùng, thông báo đẩy và cài đặt quyền riêng tư.

<div id="additional-attribution-methods" />

## Các phương thức phân bổ bổ sung

Xem xét các phương thức phân bổ bổ sung này nếu bạn định đo lường TV, số lượt gỡ cài đặt hoặc ứng dụng được cài đặt sẵn.

**Tất cả các nền tảng**

<div id="tv-attribution" />

<Accordion title="Phân bổ Truyền hình">

Phân bổ <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">người dùng di động vào các quảng cáo truyền hình</Anchor> được phát ở các vị trí cụ thể và vào thời điểm cụ thể.

</Accordion>

<div id="measure-uninstalls" />

<Accordion title="Đo lường lượt Gỡ cài đặt">

Đo tỷ lệ gỡ cài đặt của người dùng đến từ các nguồn khác nhau. Đo lường lượt gỡ cài đặt có thể giúp bạn phân tích và tối ưu hóa các chiến dịch của bạn theo những tỷ lệ KPI quan trọng này.

<Anchor target="_blank" href="/marketers/vi/docs/measure-uninstalls">Tìm hiểu cách thiết lập đo lường lượt gỡ cài đặt</Anchor>.

</Accordion>

**Chỉ dành cho Android**

<div id="preinstalled-apps" />

<Accordion title="Ứng dụng được cài đặt sẵn">

Trong <Anchor target="_blank" href="/marketers/vi/docs/appsflyer-factory-preinstall-using-manifest-android">chiến dịch cài đặt sẵn</Anchor>, chủ sở hữu ứng dụng ký hợp đồng với nhà sản xuất thiết bị (OEM) để cài đặt sẵn ứng dụng của họ.

Với AppsFlyer, bạn có thể dễ dàng phân bổ lượt cài đặt các ứng dụng được cài đặt sẵn. Khi người dùng khởi chạy lần đầu ứng dụng của bạn, AppsFlyer sẽ phân bổ lượt cài đặt đến đối tác tải trước làm nguồn truyền thông.

</Accordion>

<div id="sessions" />

## Các phiên

Đo lường mức độ tương tác của người dùng với ứng dụng bằng cách đếm số lượng phiên của người dùng trong một khoảng thời gian nhất định. 

**Tất cả các nền tảng**

<div id="custom-time-between-sessions" />

<Accordion title="Tùy chỉnh thời gian giữa các phiên">

Theo mặc định, phải mất ít nhất 5 giây giữa hai lần khởi chạy ứng dụng để được tính là hai phiên riêng biệt. Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/measure-sessions#session-reporting-by-the-app-sdk">đếm số phiên</Anchor>.

Việc đặt **giá trị cao cho thời gian tùy chỉnh giữa các lần khởi chạy có thể làm ảnh hưởng đến các API**dựa vào dữ liệu phiên, chẳng hạn như liên kết sâu.

</Accordion>

**Chỉ dành cho Android**

<div id="background-sessions-for-utility-apps" />

<Accordion title="Phiên chạy nền cho ứng dụng tiện ích">

Bạn có thể <Anchor target="_blank" href="/marketers/vi/docs/measure-sessions#session-reporting-by-the-app-sdk">báo cáo phiên người dùng theo cách thủ công</Anchor>. Điều này có thể hữu ích đối với các ứng dụng tiện ích chạy nền.

</Accordion>

<div id="owned-media" />

## Truyền thông Sở hữu

Sử dụng OneLink để phân bổ các nguồn truyền thông sở hữu của bạn, chẳng hạn như trang web, mạng xã hội và lời mời người dùng.

**Tất cả các nền tảng**

<div id="resolve-wrapped-deep-link-urls" />

<Accordion title="Giải quyết các URL liên kết sâu được gói">

Một số dịch vụ của bên thứ 3 như <Anchor target="_blank" href="/marketers/vi/docs/email-service-provider-esp-integration-guide">nhà cung cấp dịch vụ email</Anchor> gói liên kết trong email với tên miền ghi nhận click của riêng họ. Một số dịch vụ thậm chí cho phép bạn thiết lập các miền ghi nhận nhấp chuột của riêng bạn. Nếu OneLink được gói trong các miền như vậy, điều này có thể giới hạn chức năng của nó.

Để khắc phục sự cố này, nhà phát triển ứng dụng của bạn cần định cấu hình ứng dụng bằng các API sau:

<Tabs>
<Tab title="AndroidNative">

Xem [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setresolvedeeplinkurls) trong tham chiếu SDK Android

</Tab>

<Tab title="iOSNative">

Xem [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#resolvedeeplinkurls) trong tham chiếu SDK iOS

</Tab>

<Tab title="Unity">

Xem [`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/api#setresolvedeeplinkurls) trong tham chiếu SDK Unity

</Tab>
</Tabs>

</Accordion>

<div id="record-push-notifications" />

<Accordion title="Ghi nhận thông báo đẩy">

AppsFlyer hỗ trợ đo lường các chiến dịch thông báo đẩy từ tất cả các nhà cung cấp, bao gồm Google Cloud Messaging và các dịch vụ thông báo đẩy của Apple.

<Anchor target="_blank" href="/marketers/vi/docs/measuring-push-notification-re-engagement-campaigns">Tìm hiểu thêm về đo lường thông báo đẩy</Anchor>.

</Accordion>

<div id="user-invite-attribution" />

<Accordion title="Phân bổ Mời người dùng">

Việc cho phép người dùng hiện tại mời bạn bè và những mối liên hệ của họ sử dụng ứng dụng có thể là một yếu tố tăng trưởng then chốt với ứng dụng của bạn. Với AppsFlyer, bạn có thể phân bổ và ghi nhận lượt cài đặt bắt nguồn từ lời mời của người dùng trong ứng dụng của bạn.

<Anchor target="_blank" href="/marketers/vi/docs/user-invite-attribution">Tìm hiểu thêm về phân bổ lời mời người dùng</Anchor>.

</Accordion>

<div id="crosspromotion-attribution" />

<Accordion title="Phân bổ quảng cáo chéo">

Ứng dụng quảng cáo chéo có thể là một yếu tố tăng trưởng chính trong việc thúc đẩy các lượt cài đặt thêm cho ứng dụng của bạn. AppsFlyer cho phép bạn phân bổ và ghi nhận các lượt cài đặt bắt nguồn từ quảng cáo chéo từ ứng dụng mà người đang có, với một ứng dụng khác của bạn.  

<Anchor target="_blank" href="/marketers/vi/docs/cross-promotion-attribution-for-marketers">Tìm hiểu thêm về phân bổ quảng cáo chéo</Anchor>.

</Accordion>

<div id="attribute-app-sessions-initiated-from-owned-websites-domains" />

<Accordion title="Phân bổ các phiên ứng dụng bắt nguồn từ các trang web sở hữu (miền)">

Chủ sở hữu ứng dụng sử dụng Liên kết Ứng dụng hoặc Liên kết Chung để liên kết sâu (không có OneLink), có thể định cấu hình SDK để phân bổ các phiên được khởi tạo thông qua miền được liên kết với ứng dụng của họ (<Anchor target="_blank" href="https://developer.android.com/studio/write/app-link-indexing#associatesite">Android</Anchor>/<Anchor target="_blank" href="https://developer.apple.com/documentation/xcode/supporting-associated-domains?preferredLanguage=occ">iOS</Anchor>).

Ví dụ:

* Người dùng tìm kiếm trên Google và nhấp vào tên miền của bạn, **www.example.com**.
* Nếu người dùng chưa cài đặt ứng dụng, họ sẽ được chuyển hướng đến trang web (www.example.com).
* Nếu người dùng đã cài đặt ứng dụng trên thiết bị của họ, họ sẽ được liên kết sâu vào ứng dụng được liên kết với www.example.com. Phiên được phân bổ cho nguồn truyền thông (thông số `pid`) được định cấu hình trong SDK.

Tài liệu dành cho nhà phát triển có sẵn như sau:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Tham chiếu SDK Android</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Tham chiếu SDK iOS</Anchor>

**Mẹo!** <Anchor target="_blank" href="/marketers/vi/docs/convert-your-mobile-web-visitors-to-app-users#attribution-solutions">OneLink Smart Script</Anchor> có thể giúp chủ sở hữu ứng dụng chuyển đổi khách truy cập trang web thành người dùng ứng dụng.

</Accordion>

<div id="user-privacy" />

## Quyền riêng tư của người dùng

Xem xét các quy định như GDPR và CCPA và các yêu cầu kinh doanh của bạn, đồng thời cân nhắc các chính sách chọn tham gia và không tham gia nào cần thực hiện.

**Tất cả các nền tảng**

<div id="optout-policy" />

<Accordion title="Chính sách chọn không tham gia">

Trong một số trường hợp, bạn có thể cần hướng dẫn nhà phát triển của mình đặt SDK AppsFlyer để dừng hoặc giới hạn việc thu thập dữ liệu, (ví dụ: để tuân thủ các quy định về GDPR và CCPA). Việc chọn không tham gia có thể diễn ra ở một số cấp khác nhau tùy thuộc vào yêu cầu của cơ quan quản lý và người dùng. Để biết thêm thông tin về các tình huống khác nhau, hãy xem phần <Anchor target="_blank" href="/marketers/vi/docs/apply-privacy-preserving-sdk-methods#scenarios">Người dùng chọn không tham gia</Anchor>.

</Accordion>

<div id="exclude-partners-from-getting-data" />

<Accordion title="Loại trừ các đối tác không được lấy dữ liệu">

Trong một số trường hợp, nhà quảng cáo có thể muốn ngừng chia sẻ dữ liệu cấp người dùng với các mạng/đối tác quảng cáo cho những người dùng cụ thể. Lý do cho điều này bao gồm: 

* Các chính sách bảo mật như CCPA hoặc GDPR
* Cơ chế chọn lựa không tham gia của người dùng
* Cạnh tranh với một số đối tác (mạng quảng cáo, bên thứ ba)

Chia sẻ dữ liệu với đối tác được kiểm soát thông qua phương thức `setSharingFilterForPartners`:

<Tabs>
<Tab title="Gốc Android">

Xem [`setSharingFilterForPartners`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners) trong tham chiếu SDK Android

</Tab>

<Tab title="Gốc iOS">

Xem [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners) trong tham chiếu SDK iOS

</Tab>

<Tab title="Unity">

Xem [`setSharingFilterForPartners`](https://dev.appsflyer.com/hc/docs/api#setsharingfilterforpartners) trong tham chiếu SDK Unity

</Tab>
</Tabs>

</Accordion>

**Chỉ dành cho iOS**

<div id="strictmode-sdk" />

<Accordion title="SDK chế độ nghiêm ngặt">

Sử dụng SDK chế độ nghiêm ngặt để loại bỏ hoàn toàn chức năng thu thập IDFA và các phần phụ thuộc của khung AdSupport (ví dụ: khi phát triển <Anchor target="_blank" href="https://developer.apple.com/app-store/review/guidelines/#kids-category">ứng dụng dành cho trẻ em</Anchor>).

Nếu bạn đưa ra thị trường ứng dụng dành cho trẻ em, nhà phát triển của bạn cần cài đặt <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK chế độ nghiêm ngặt</Anchor> thay vì SDK thông thường. **Lưu ý:** IDFV vẫn có sẵn.

</Accordion>

<div id="disable-ad-frameworks" />

<Accordion title="Vô hiệu hóa các khung quảng cáo">

Để vô hiệu hóa các khung AdSupport và iAd, SDK cung cấp các bộ thiết lập sau:

<Tabs>
<Tab title="Gốc iOS">

* [`disableCollectASA`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disablecollectasa) để lựa chọn không tham gia phân bổ Apple Search Ads.
* [`disableAdvertisingIdentifier`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) để không thu thập `advertisingIdentifier` của Apple

</Tab>

<Tab title="Unity">

* [`setDisableCollectIAd`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectiad) để lựa chọn không tham gia phân bổ Apple Search Ads.
* [`setDisableCollectAppleAdSupport`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectappleadsupport) để không thu thập `advertisingIdentifier` của Apple

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="additional-attribution-methods=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-ph%C3%A2n-b%E1%BB%95-b%E1%BB%95-sung 01H8W01DRHQHJKNMJA24PR5S2T=c%C3%A1c-ph%C6%B0%C6%A1ng-th%E1%BB%A9c-ph%C3%A2n-b%E1%BB%95-b%E1%BB%95-sung 01H8W01DRHXR0BRCB9RECH7KS1=tv-attribution 01H8W01DRHMZN2P0FKADM0NQ96=measure-uninstalls 01H8W01DRH2HM3N06YAGRZ030F=preinstalled-apps sessions=c%C3%A1c-phi%C3%AAn 01H8W01DRHD3EZBQT0ZKDMM1QB=c%C3%A1c-phi%C3%AAn 01H8W01DRH2SR3NBQSMSQ6QR6K=custom-time-between-sessions 01H8W01DRH4NGYYABE274DJ1A5=background-sessions-for-utility-apps owned-media=truy%E1%BB%81n-th%C3%B4ng-s%E1%BB%9F-h%E1%BB%AFu 01H8W01DRHV8H3QFJX5QKABK5E=truy%E1%BB%81n-th%C3%B4ng-s%E1%BB%9F-h%E1%BB%AFu 01H8W01DRHJS8MM3ZQX2RX4JJG=resolve-wrapped-deep-link-urls 01H8W01DRHHDEEXP8GDFX9134R=record-push-notifications 01H8W01DRHZDB82AB63JKE1B6V=user-invite-attribution 01H8W01DRHVR8JHZCJ6SW8TAA6=crosspromotion-attribution 01H8W01DRHXSYWCS6RW2ZVDKXT=attribute-app-sessions-initiated-from-owned-websites-domains user-privacy=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng 01H8W01DRHJFB71DVJ64QWJME4=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng 01H8W01DRHD7FDERJZFJP9GG0T=optout-policy 01H8W01DRHYNYYFTF82XZ21J3P=exclude-partners-from-getting-data 01H8W01DRJD0XRX4VX03T3YEKX=strictmode-sdk 01H8W01DRJKJFFMBMJ4KNTXPXE=disable-ad-frameworks" />
