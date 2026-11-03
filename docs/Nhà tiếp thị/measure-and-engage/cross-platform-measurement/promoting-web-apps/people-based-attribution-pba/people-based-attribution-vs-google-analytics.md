---
title: Phân bổ trên Cơ sở Người dùng so với Google Analytics
metadata:
  keywords:
    - Google Analytics
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
  created_at: '2019-03-28T07:22:04Z'
  edited_at: '2023-02-15T13:15:05Z'
  id: 360001305617
  locale: vi
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/vi/articles/360001305617
---
> **Khái quát**: Sự khác nhau giữa Phân bổ trên cơ sở Người dùng (PBA) và Google Analytics

## PBA so với Google Analytics

PBA và Google Analytics là các giải pháp đo lường lượt chuyển đổi và phân tích trang web. Mỗi một giải pháp tập trung vào các khía cạnh đo lường khác nhau. Ngoài ra, PBA cũng mang đến những lợi ích bổ sung.

* PBA là một cơ quan phân bổ độc lập, khách quan, tập trung vào hoạt động đo lường phân bổ. PBA phân bổ lượt chuyển đổi và doanh thu cho các nguồn và chiến dịch truyền thông đưa người dùng đến trang web của bạn.
* Google Analytics tập trung nhiều hơn vào hoạt động phân tích trang web. Giải pháp này thu thập, phân tích và hợp nhất dữ liệu liên quan đến hành vi của người dùng. Với Google Analytics, bạn có thể phân tích những yếu tố như hành vi người dùng, kênh, sự kiện web.

### Lợi ích của PBA so với Google Analytics

Sau đây là những lợi ích của PBA so với Google Analytics:

* PBA bao gồm:
  * Đo lường chuyển đổi web sang ứng dụng. Phép đo này cho bạn biết có bao nhiêu người dùng chuyển từ trang web của bạn sang ứng dụng của bạn. Giải pháp cũng cho bạn biết các nguồn truyền thông và chiến dịch nào đưa người dùng đến trang web, rồi cuối cùng là cài đặt ứng dụng của bạn.
  * <Anchor target="_blank" href="/marketers/vi/docs/pba-raw-data-reports">Dữ liệu thô về lượt chuyển đổi và sự kiện</Anchor> mà bạn có thể kéo vào các hệ thống BI của riêng mình. Điều này giúp bạn có khả năng và năng lực để chạy phân tích của mình.

### Nguyên nhân dẫn đến sự khác biệt

Nếu bạn so sánh dữ liệu từ PBA và Google Analytics, hãy tham khảo các nguyên nhân dẫn đến sự khác biệt về dữ liệu như sau.

#### Thực hiện SDK

Cách bạn triển khai PBA và Google Analytics có thể ảnh hưởng đến việc thu thập dữ liệu.

<div id="google-analytics-shows-more-sessions-and-visitors" />

<Accordion title="Google Analytics hiển thị nhiều phiên và lượt khách truy cập hơn">

#### Nguyên nhân

Nếu Google Analytics tải trước khi người dùng SDK Web thoát trang hoặc người dùng dành thời gian trên trang web của bạn ngắn hơn sẽ không được tính vào PBA. Điều này dẫn đến sự khác nhau về dữ liệu phiên và lượt khách truy cập.

#### Giải pháp

Tốt nhất bạn nên định vị SDK Web sao cho nó có thể tải càng sớm càng tốt.

Cho dù bạn tải <Anchor target="_blank" href="/marketers/vi/docs/pba-web-sdk-integration-guide#tích-hợp-sdk-web-vào-trang-web">SDK trực tiếp hay thông qua Trình quản lý Thẻ của Google</Anchor>, việc tải SDK trễ có thể gây ra những sai khác đáng kể.

</Accordion>

<div id="google-analytics-shows-more-data-for-sessions-campaign-and-conversions" />

<Accordion title="Google Analytics hiển thị nhiều dữ liệu hơn cho các phiên, chiến dịch và lượt chuyển đổi">

#### Nguyên nhân

SDK Web chỉ hiện diện trên một số trang nhất định. Google Analytics có mặt trên tất cả các trang. Do đó, Google Analytics thu thập dữ liệu từ tất cả các trang web của bạn trong khi SDK Web chỉ thu thập dữ liệu từ một số trang nhất định. Điều này dẫn đến sự khác nhau về dữ liệu phiên, lượt khách truy cập, chiến dịch và lượt chuyển đổi.

#### Giải pháp

Triển khai SDK Web trên tất cả các trang của trang web của bạn.

</Accordion>

### Cài đặt bảng điều khiển

Cài đặt bảng điều khiển như múi giờ và bộ lọc dữ liệu có thể ảnh hưởng đến cách dữ liệu được hiển thị cho bạn.

<div id="timezone-settings-discrepancies-in-data" />

<Accordion title="Cài đặt múi giờ - khác nhau về dữ liệu">

#### Nguyên nhân

Nếu thông số cài đặt múi giờ trong Google Analytics khác với cài đặt trong bảng điều khiển của PBA thì có thể sẽ có sự sai lệch.

> 📄 **Ví dụ:**
>
> Bảng điều khiển AppsFlyer của bạn được cấu hình thành UTC và bảng điều khiển GA của bạn được cấu hình thành UTC +13. Điều này có nghĩa là thời gian của bảng điều khiển GA sẽ trước một ngày so với thời gian của bảng điều khiển AppsFlyer.
>
> Do đó, dữ liệu xuất hiện trong bảng điều khiển AppsFlyer cho ngày 2 tháng 3 chỉ xuất hiện trong bảng điều khiển GA nếu bạn chọn ngày 3 tháng 3 trong bộ lọc phạm vi ngày.

#### Giải pháp

Đảm bảo cài đặt múi giờ trong cả AppsFlyer và Google Analytics là giống nhau.

</Accordion>

<div id="data-filters--discrepancies-in-data" />

<Accordion title="Bộ lọc dữ liệu - khác nhau về dữ liệu">

#### Vấn đề

Cả AppsFlyer và Google Analytics đều cho phép bạn lọc dữ liệu theo ngày, nguồn truyền thông, chiến dịch và sự kiện được phân bổ. Các bộ lọc khác nhau trong AppsFlyer và Google Analytics có thể tạo các chế độ xem khác nhau cho cùng một dữ liệu.

#### Giải pháp

Khi bạn so sánh dữ liệu từ hai bảng điều khiển, hãy đảm bảo không áp dụng bộ lọc nào cho tập dữ liệu.

</Accordion>

### Lượt chuyển đổi và sự kiện

Các mô hình phân bổ, khung thời gian xem lại, cách bạn gửi sự kiện cũng như cài đặt cookie khác nhau đều có thể ảnh hưởng đến việc thu thập và xử lý dữ liệu.

<div id="lookback-window-discrepancies-in-conversion-measurement" />

<Accordion title="Khung thời gian xem lại - khác nhau về đo lường lượt chuyển đổi">

#### Nguyên nhân

Nếu khung thời gian xem lại của bạn trong Google Analytics và PBA là khác nhau thì có thể có sự khác nhau về dữ liệu phân bổ.

#### Giải pháp

Khung thời gian xem lại của PBA luôn là 30 ngày. Bạn phải đảm bảo đặt khung thời gian xem lại là 30 ngày trong Google Analytics khi <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189">chọn mô hình phân bổ</Anchor>.

</Accordion>

<div id="attribution-model--discrepancies-in-conversion-measurement" />

<Accordion title="Mô hình phân bổ - khác nhau về đo lường lượt chuyển đổi">

#### Nguyên nhân

Các mô hình phân bổ trong PBA và Google Analytics khác nhau có thể dẫn đến sự khác nhau về dữ liệu phân bổ.

#### Giải pháp

Google Analytics cung cấp <Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189?hl=en">mô hình phân bổ mặc định</Anchor> mà bạn có thể chọn. Tuy nhiên, PBA hoạt động theo mô hình phân bổ tương tác không trực tiếp sau cùng, với khung thời gian xem lại là 30 ngày. Đảm bảo chọn mô hình phân bổ tương tác không trực tiếp sau cùng trong Google Analytics.

</Accordion>

<div id="sending-events" />

<Accordion title="Gửi sự kiện">

#### Vấn đề

Cả SDK Google Analytics và SDK Web đều cho phép bạn gửi sự kiện. Nếu bạn thực thi một logic để gửi sự kiện tới Google Analytics và một logic khác để gửi sự kiện tới PBA, thì có thể phát sinh sự sai khác.

#### Giải pháp

Khi bạn gửi sự kiện, hãy xác minh như sau:

* Đảm bảo áp dụng cùng một kích hoạt cho cả hai
* Đảm bảo bạn gửi sự kiện tới cả Google Analytics và PBA

Nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/pba-web-sdk-integration-guide#nguyên-tắc-ghi-nhận-sự-kiện">đây</Anchor> để tìm hiểu cách gửi sự kiện bằng SDK Web.

</Accordion>

<div id="cookies" />

<Accordion title="Cookie">

Cả PBA và Google Analytics đều sử dụng cookie để nhận dạng người dùng.

#### Cài đặt cookie trong Google Analytics

Mặc dù nên để SDK Google Analytics tự động xử lý cài đặt cookie, nhưng bạn vẫn có thể <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/analyticsjs/cookies-user-id">cấu hình và thay đổi cài đặt cookie</Anchor>. Mọi thay đổi về cài đặt cookie đều có thể là nguyên nhân dẫn đến sự sai khác.

#### Cài đặt thời gian hết hạn của cookie

Google Analytics cho phép bạn đặt thời gian hết hạn của cookie. Nếu bạn đặt cookie Google Analytics hết hạn trước khi cookie SDK Web hết hạn thì hiện tượng sai khác có thể xảy ra.

> 📄 **Ví dụ**
>
> Mark là một khách truy cập trung thành vào trang web của bạn trong hơn một năm nay và cân nhắc đăng ký nội dung cao cấp.
>
> Nhà phát triển của bạn đã đặt thời gian hết hạn của cookie Google Analytics sau một năm. Tuy nhiên, SDK Web đặt thời gian hết hạn của cookie là sau hai năm.
>
> Cuối cùng, khi Mark đăng ký và lượt chuyển đổi được ghi nhận thì cookie Google Analytics không còn hợp lệ và một cookie khác được đặt thay cho cookie đó.
>
> Kết quả cuối cùng là Google Analytics hiển thị hai người dùng, cả hai đều là Mark, với chỉ một trong số họ có liên kết lượt chuyển đổi. Tuy nhiên, PBA hiển thị một người dùng cho Mark và cùng một người dùng có liên kết lượt chuyển đổi.
>
> Điều này có nghĩa là tỷ lệ chuyển đổi của bạn trong Google Analytics thấp hơn so với trong PBA.

#### Đặt Miền phụ của Cookie

Google Analytics cho phép bạn đặt cookie cho miền phụ trong khi PBA chỉ đặt cookie trên miền cấp cao nhất.

> 📄 **Ví dụ**
>
> Bạn đặt cookie về miền phụ **store.mywebsite.com**. Sharon truy cập trang web của bạn và sau đó chuyển đến cửa hàng trực tuyến của bạn tại **store.mywebsite.com**. Google Analytics coi cô **là hai người dùng khác nhau**.
>
> Vì PBA chỉ đặt cookie trên miền cấp cao nhất **mywebsite.com**, nên sẽ coi Sharon trên **mywebsite.com** và **store.mywebsite.com** là cùng một người dùng.
>
> Kết quả cuối cùng là trong Google Analytics thì là hai người dùng, trong khi trong PBA thì chỉ là một người dùng.

</Accordion>

<div data-zendesk-anchors="pba-compared-to-google-analytics=pba-so-v%E1%BB%9Bi-google-analytics benefits-of-pba-over-google-analytics=l%E1%BB%A3i-%C3%ADch-c%E1%BB%A7a-pba-so-v%E1%BB%9Bi-google-analytics reasons-for-differences=nguy%C3%AAn-nh%C3%A2n-d%E1%BA%ABn-%C4%91%E1%BA%BFn-s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t sdk-implementation=th%E1%BB%B1c-hi%E1%BB%87n-sdk cause=nguy%C3%AAn-nh%C3%A2n solution=gi%E1%BA%A3i-ph%C3%A1p cause::49d3e519=nguy%C3%AAn-nh%C3%A2n-1 solution::447e7ac9=gi%E1%BA%A3i-ph%C3%A1p-1 dashboard-settings=c%C3%A0i-%C4%91%E1%BA%B7t-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n cause::30244d2c=nguy%C3%AAn-nh%C3%A2n-2 solution::f1a0e066=gi%E1%BA%A3i-ph%C3%A1p-2 data-filters-%C2%A0discrepancies-in-data=data-filters--discrepancies-in-data issue=v%E1%BA%A5n-%C4%91%E1%BB%81 solution::df8f3921=gi%E1%BA%A3i-ph%C3%A1p-3 conversions-and-events=l%C6%B0%E1%BB%A3t-chuy%E1%BB%83n-%C4%91%E1%BB%95i-v%C3%A0-s%E1%BB%B1-ki%E1%BB%87n cause::b346571c=nguy%C3%AAn-nh%C3%A2n-3 solution::4bb14ac9=gi%E1%BA%A3i-ph%C3%A1p-4 attribution-model%C2%A0-discrepancies-in-conversion-measurement=attribution-model--discrepancies-in-conversion-measurement cause::2296f6c1=nguy%C3%AAn-nh%C3%A2n-4 solution::b2be4a33=gi%E1%BA%A3i-ph%C3%A1p-5 issue::b412f5ba=v%E1%BA%A5n-%C4%91%E1%BB%81-1 solution::39b4d7d6=gi%E1%BA%A3i-ph%C3%A1p-6 cookie-settings-in-google-analytics=c%C3%A0i-%C4%91%E1%BA%B7t-cookie-trong-google-analytics setting-cookie-expiration=c%C3%A0i-%C4%91%E1%BA%B7t-th%E1%BB%9Di-gian-h%E1%BA%BFt-h%E1%BA%A1n-c%E1%BB%A7a-cookie setting-cookie-subdomain=%C4%91%E1%BA%B7t-mi%E1%BB%81n-ph%E1%BB%A5-c%E1%BB%A7a-cookie" />
