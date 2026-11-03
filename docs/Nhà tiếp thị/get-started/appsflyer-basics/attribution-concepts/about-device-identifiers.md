---
title: Mã định danh của thiết bị
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
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
    - Ad Networks
  created_at: '2021-10-12T14:16:09Z'
  edited_at: '2023-11-27T09:37:31Z'
  id: 4408847686161
  locale: vi
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/vi/articles/4408847686161
---
> **Khái quát:** Hiểu rõ các mã định danh thiết bị được hỗ trợ trong SDK AppsFlyer.

## Tổng quan

SDK AppsFlyer thu thập các mã định danh thiết bị cho <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#phân-bổ">các mục đích phân bổ</Anchor>. Mã định danh có thể giúp bạn ánh xạ hành trình của người dùng và hiểu được sở thích của họ.

SDK tự động thu thập các mã định danh như ID AppsFlyer và ID Quảng cáo Google (GAID). Việc thu thập các mã định danh khác cho ứng dụng của bạn tùy thuộc vào nhu cầu của bạn (ví dụ: thu thập các cửa hàng ứng dụng Android của bên thứ ba hoặc ứng dụng được tiếp thị tại Trung Quốc).

## Mã định danh cho mọi nền tảng

SDK hỗ trợ các mã định danh thiết bị sau cho mọi nền tảng:

| Mã định danh của thiết bị | Mục đích |
| --- | --- |
| <span id="appsflyer-id"></span>ID AppsFlyer | ID AppsFlyer được tạo tự động cho mọi lượt cài đặt ứng dụng. Bạn có thể sử dụng mã định danh này để thực hiện các hoạt động sau:<ul><li>Gửi <Anchor target="_blank" href="/marketers/vi/docs/server-to-server-events-api-for-mobile-s2s-mobile">các sự kiện trong ứng dụng máy chủ đến máy chủ</Anchor>.</li><li>Khớp ID AppsFlyer với hồ sơ người dùng trong các hệ thống backend của bạn.</li><li>Ánh xạ các mục nhập khi hợp nhất dữ liệu từ API kéo và đẩy.</li></ul> |
| <span id="customer-user-id"></span>Customer User ID | Trường <Anchor target="_blank" href="/marketers/vi/docs/customer-user-id-field-cuid">Customer user ID (CUID)</Anchor> là một mã định danh người dùng duy nhất do chủ sở hữu ứng dụng và trang web thiết lập. Đặt CUID của riêng bạn vào SDK AppsFlyer cho phép bạn tham chiếu chéo ID duy nhất của mình với ID AppsFlyer và các mã định danh khác. CUID có sẵn trong các báo cáo <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary">dữ liệu thô</Anchor> của AppsFlyer. Bạn cũng có thể sử dụng CUID này trong API đăng lại để tham chiếu chéo với ID nội bộ của bạn. |

## Mã định danh thiết bị Android

SDK hỗ trợ các mã định danh thiết bị sau cho các nền tảng Android:

#### Các ứng dụng được phát hành trên Google Play

| Mã định danh của thiết bị | Mục đích |
| --- | --- |
| <span id="gaid"></span>GAID | Mã định danh **có thể được người dùng đặt lại** dành cho người dùng Google Play Android.<br /><br />Kể từ phiên bản SDK V4.8.0, AppsFlyer sẽ tự động thu thập mã nhận dạng thiết bị này. |

#### Ứng dụng được phát hành trong cửa hàng ứng dụng của bên thứ ba

| Mã định danh của thiết bị | Mục đích |
| --- | --- |
| <span id="amazon-advertising-id"></span>ID Quảng cáo Amazon | Mã định danh duy nhất **có thể được người dùng đặt lại** được Amazon Fire TV sử dụng. <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">Xem phần tổng quan về CTV</Anchor> |
| <span id="oaid"></span>OAID | Mã định danh **có thể được người dùng đặt lại** được một số thị trường Android ngoài cửa hàng sử dụng.  Để biết thêm thông tin, hãy xem <Anchor target="_blank" href="/marketers/vi/docs/android-oaid-implementation-in-the-sdk">Hướng dẫn triển khai OAID</Anchor>. |
| <span id="imei"></span>IMEI | Mã định danh thiết bị di động duy nhất, **không thể đặt lại** được sử dụng ở các thị trường không sử dụng Google Play. SDK không tự động thu thập IMEI. Tuy nhiên, nếu có nhu cầu cần thu thập các mã định danh này, nhà phát triển của bạn có thể triển khai việc thu thập.<br /><br />**Lưu ý:**<ul><li>Bắt đầu từ Android 10, quyền truy cập vào IMEI bị <Anchor target="_blank" href="https://developer.android.com/about/versions/10/privacy/changes#non-resettable-device-ids">hạn chế</Anchor>.</li><li>Không thể sử dụng IMEI cùng với GAID.</li></ul> |
| <span id="android-id"></span>ID Android | Mã định danh thiết bị di động duy nhất, **không thể đặt lại** được sử dụng ở các cửa hàng ứng dụng của bên thứ ba. SDK không tự động thu thập ID Android. Tuy nhiên, nếu có nhu cầu cần thu thập các mã định danh này, nhà phát triển của bạn có thể triển khai việc thu thập.<br /><br />**Lưu ý:** Không thể sử dụng ID Android cùng với GAID. |

## Mã định danh thiết bị Apple

SDK hỗ trợ các mã định danh thiết bị sau cho các nền tảng iOS:

| Mã định danh của thiết bị | Mục đích |
| --- | --- |
| <span id="idfa"></span>IDFA | Mã định danh duy nhất **có thể được người dùng đặt lại** dành cho người dùng Apple iOS hoặc tvOS (Apple TV). Kể từ khi phát hành iOS 14.5, IDFA chỉ khả dụng nếu người dùng đồng ý thông qua <Anchor target="_blank" href="/marketers/vi/docs/about-att-and-skan#att-principles">lời nhắc ATT</Anchor>. |
| <span id="idfv"></span>IDFV | Mã định danh thiết bị được chia sẻ bởi tất cả các ứng dụng từ **cùng một nhà cung cấp** trên thiết bị. Sau khi ứng dụng đầu tiên được cài đặt, ID sẽ được gán cho ứng dụng đó và các ứng dụng khác từ cùng một nhà cung cấp sẽ được gán cùng một IDFV. Ứng dụng từ các nhà cung cấp khác được gán một IDFV khác.<br /><br />Ngoài ra, khi tất cả các ứng dụng từ một nhà cung cấp cụ thể bị xóa, IDFV cho nhà cung cấp đó sẽ bị xóa và sau khi có cài đặt mới, IDFV mới sẽ được chỉ định. |

## Mã định danh thiết bị CTV

SDK hỗ trợ các mã định danh thiết bị sau cho các nền tảng CTV:

| Mã định danh của thiết bị | Mục đích |
| --- | --- |
| <span id="rida"></span>RIDA | Dành cho thiết bị CTV của Roku. <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">Xem phần tổng quan về CTV</Anchor> |
| <span id="vida"></span>VIDA | Dành cho thiết bị CTV của Vizio. <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">Xem phần tổng quan về CTV</Anchor> |
| <span id="tifa"></span>TIFA | Dành cho thiết bị CTV của Samsung. <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">Xem phần tổng quan về CTV</Anchor> |
| <span id="lgudid"></span>LGUDID | Dành cho thiết bị CTV của LG. <Anchor target="_blank" href="/marketers/vi/docs/ctv-pc-and-console-platform-attribution-concepts">Xem phần tổng quan về CTV</Anchor> |

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan h_01H9YXEYC3PA271B3G3Y3GM9PS=t%E1%BB%95ng-quan device-identifiers-for-all-platforms=m%C3%A3-%C4%91%E1%BB%8Bnh-danh-cho-m%E1%BB%8Di-n%E1%BB%81n-t%E1%BA%A3ng h_01H9YXEYC3RCB3RDBKRW19WYQD=m%C3%A3-%C4%91%E1%BB%8Bnh-danh-cho-m%E1%BB%8Di-n%E1%BB%81n-t%E1%BA%A3ng android-device-identifiers=m%C3%A3-%C4%91%E1%BB%8Bnh-danh-thi%E1%BA%BFt-b%E1%BB%8B-android h_01H9YXEYC3D95A6G70EGNR8ENK=m%C3%A3-%C4%91%E1%BB%8Bnh-danh-thi%E1%BA%BFt-b%E1%BB%8B-android apps-published-on-google-play=c%C3%A1c-%E1%BB%A9ng-d%E1%BB%A5ng-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A1t-h%C3%A0nh-tr%C3%AAn-google-play h_01H9YXEYC3RG2XCVVW8MJ5VZSC=c%C3%A1c-%E1%BB%A9ng-d%E1%BB%A5ng-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A1t-h%C3%A0nh-tr%C3%AAn-google-play apps-published-in-thirdparty-app-stores=%E1%BB%A9ng-d%E1%BB%A5ng-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A1t-h%C3%A0nh-trong-c%E1%BB%ADa-h%C3%A0ng-%E1%BB%A9ng-d%E1%BB%A5ng-c%E1%BB%A7a-b%C3%AAn-th%E1%BB%A9-ba h_01H9YXEYC3JA3DPN6P43J1ZXR9=%E1%BB%A9ng-d%E1%BB%A5ng-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A1t-h%C3%A0nh-trong-c%E1%BB%ADa-h%C3%A0ng-%E1%BB%A9ng-d%E1%BB%A5ng-c%E1%BB%A7a-b%C3%AAn-th%E1%BB%A9-ba apple-device-identifiers=m%C3%A3-%C4%91%E1%BB%8Bnh-danh-thi%E1%BA%BFt-b%E1%BB%8B-apple h_01H9YXEYC3733B1A85TEF35EAY=m%C3%A3-%C4%91%E1%BB%8Bnh-danh-thi%E1%BA%BFt-b%E1%BB%8B-apple ctv-device-identifiers=m%C3%A3-%C4%91%E1%BB%8Bnh-danh-thi%E1%BA%BFt-b%E1%BB%8B-ctv h_01H9YXEYC3DFPWVXA5Y3XANQ3P=m%C3%A3-%C4%91%E1%BB%8Bnh-danh-thi%E1%BA%BFt-b%E1%BB%8B-ctv" />
