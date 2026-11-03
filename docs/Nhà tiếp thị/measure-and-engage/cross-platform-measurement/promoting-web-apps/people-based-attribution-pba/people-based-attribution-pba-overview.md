---
title: Phân bổ trên Cơ sở Người dùng (PBA)—Tổng quan
metadata:
  keywords:
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-08-19T11:53:56Z'
  edited_at: '2024-02-22T07:54:54Z'
  id: 360002274017
  locale: vi
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/vi/articles/360002274017
---
> **Khái quát:** Phân bổ trên Cơ sở Người dùng (PBA) cung cấp giao diện tổng hợp về hành trình của khách hàng trên các kênh, nền tảng và thiết bị.

![PBANoSilos_us-en.gif](https://files.readme.io/1ac3614eb1b9d4c01bffbe904f1a060d1facd681ff32c274b12f0a15612a2e4a-360009359798.gif)

## Nguyên tắc PBA

* PBA hợp nhất dữ liệu trang web và ứng dụng dành cho thiết bị di động để cung cấp cái nhìn tổng thể về hiệu suất chiến dịch về các thuộc tính kỹ thuật số của thương hiệu. Các nhà quảng cáo sử dụng PBA để hiểu hành trình của khách hàng về khía cạnh người dùng, thay vì thiết bị.
* Dữ liệu PBA—trên bảng điều khiển PBA và trong báo cáo dữ liệu thô—được sử dụng để phân tích tiếp thị và tối ưu hóa chiến dịch.
* Dữ liệu bao gồm lượt truy cập trang web và các sự kiện của người dùng được thu thập bằng cách sử dụng <Anchor target="_blank" href="/marketers/vi/docs/pba-web-sdk-integration-guide">SDK và/hoặc API.</Anchor>
* Đối với mỗi lượt truy cập vào trang web: nguồn truyền thông chịu trách nhiệm đưa đến lượt truy cập sẽ được xác định. Mọi sự kiện kết quả (chuyển đổi) đều được <Anchor target="_blank" href="/marketers/vi/docs/pba-media-source-attribution-rules">phân bổ</Anchor> cho nguồn truyền thông gây ra lượt truy cập.

### Bảng điều khiển phân tích PBA và dữ liệu thô

* Dữ liệu PBA được trình bày qua các báo cáo và bảng điều khiển phân tích:
  * Phân bổ Trang web
  * Lượt cài đặt được Web Hỗ trợ
  * Đường dẫn Chuyển đổi
  * Báo cáo dữ liệu thô
* Dữ liệu trong bảng điều khiển <Anchor target="_blank" href="/marketers/vi/docs/using-pba-dashboards">được lọc và nhóm lại</Anchor> bằng cách sử dụng các phương diện như nền tảng di động, kênh truyền thông và loại truyền thông, Điều này cho phép bạn truy cập sâu và phân tích dữ liệu.

### <Anchor target="_blank" href="/marketers/vi/docs/pba-website-attribution-dashboard">Phân bổ Trang web</Anchor>

[![WebsiteAttributionTable_us-en.jpg](https://files.readme.io/327a4830ca20ba9067bb9f7a5e5264908fd918ada9462261befcef2f48fd0fd0-360013135398.jpg)](https://files.readme.io/327a4830ca20ba9067bb9f7a5e5264908fd918ada9462261befcef2f48fd0fd0-360013135398.jpg)

Phân tích các nguồn lưu lượng truy cập web và các chiến dịch tiếp thị thúc đẩy lượt truy cập và chuyển đổi của người dùng trên trang web của bạn. Khám phá sự khác biệt về hiệu suất chi tiết đến cấp quảng cáo. Hỗ trợ tất cả các thông số truy vấn AppsFlyer trong liên kết mà không cần chuyển hướng người dùng đến máy chủ AppsFlyer.

### <Anchor target="_blank" href="/marketers/vi/docs/pba-web-assisted-installs">Lượt cài đặt được Web Hỗ trợ</Anchor>

[![AppsFlyer-Web-to-App_us.en.gif](https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif)](https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif)

Sử dụng Lượt cài đặt được Web Hỗ trợ để kiểm tra tác động và kết quả của các nỗ lực tiếp thị web của bạn đối với việc thúc đẩy lượt cài đặt ứng dụng dành cho thiết bị di động.

* Có được thông tin chi tiết về việc các loại truyền thông khác nhau (trả phí, sở hữu, lan truyền), các kênh truyền thông (trực tiếp, mạng xã hội, tìm kiếm tự nhiên) và các nguồn truyền thông tương tác và đóng góp ra sao vào nỗ lực thu hút người dùng tổng thể của bạn.
* Phân bổ lượt cài đặt tự nhiên do nỗ lực web của bạn thúc đẩy.
* Kiểm tra sự tương tác giữa các nỗ lực web và các lượt cài đặt không tự nhiên.

### <Anchor target="_blank" href="/marketers/vi/docs/pba-raw-data-reports">Dữ liệu thô</Anchor>

Dữ liệu thô cung cấp thông tin chi tiết chuyên sâu và bao gồm nguồn truyền thông được phân bổ/chịu trách nhiệm đưa người dùng đến trang web.

* **Lượt truy cập web:** lượt truy cập vào trang web
* **Sự kiện web**: các hành động được thực hiện trên trang web như đăng ký hoặc mua hàng
* **Lượt cài đặt được Web Hỗ trợ** và hành trình **đường dẫn Chuyển đổi** được cung cấp đầy đủ.
* Các công cụ BI được sử dụng để phân tích dữ liệu để có thêm thông tin chi tiết.

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/onboarding-guide-to-people-based-attribution">Giới thiệu về PBA dành cho người mới</Anchor>

<div data-zendesk-anchors="pba-principles=nguy%C3%AAn-t%E1%BA%AFc-pba 01ECF26CMJ8TB4ADT6VN277EMQ=nguy%C3%AAn-t%E1%BA%AFc-pba pba-analytics-dashboards-and-raw-data=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-ph%C3%A2n-t%C3%ADch-pba-v%C3%A0-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 01ECF26CMJDA1HBC22DGRWY2EA=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-ph%C3%A2n-t%C3%ADch-pba-v%C3%A0-d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 website-attribution=ph%C3%A2n-b%E1%BB%95-trang-web 01ECF26CMK0T5C9JKQ0SYMXQVM=ph%C3%A2n-b%E1%BB%95-trang-web webassisted-installs=l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-%C4%91%C6%B0%E1%BB%A3c-web-h%E1%BB%97-tr%E1%BB%A3 01ECF26CMKDS16XWRBQ1SDAX2Q=l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t-%C4%91%C6%B0%E1%BB%A3c-web-h%E1%BB%97-tr%E1%BB%A3 raw-data=d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 01ECF26CMM4KHX9W94DND4BY8C=d%E1%BB%AF-li%E1%BB%87u-th%C3%B4 h_01HE0Y2KTXS06WHN57MQ91AD09=xem-th%C3%AAm" />
