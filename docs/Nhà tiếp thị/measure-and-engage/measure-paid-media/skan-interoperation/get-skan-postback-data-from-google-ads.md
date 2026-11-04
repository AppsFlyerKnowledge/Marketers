---
title: 'Nhận dữ liệu đăng lại SKAN từ Google Ads '
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-28T19:34:39Z'
  edited_at: '2023-12-21T14:09:32Z'
  id: 4403215779857
  locale: vi
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/vi/articles/4403215779857
---
> **Sơ lược:** Cho phép Google chia sẻ nội dung đăng lại iOS của ứng dụng SKAdNewtork (SKAN) của bạn với AppsFlyer.

<div id="get-skan-postback-data-from-google-ads" />

## Nhận dữ liệu đăng lại SKAN từ Google Ads

Nếu bạn làm việc với nhiều đối tác mạng quảng cáo, cách tốt nhất là thiết lập nó trong AppsFlyer. Bằng cách đó, số liệu hiệu suất SKAN cho tất cả đối tác mạng quảng cáo của bạn, được bổ sung thêm các số liệu khác như chi phí, sẽ có sẵn thông qua nền tảng AppsFlyer.

**Phạm vi báo cáo SKAN với Google Ads**

* Google Ads chia sẻ số lượt đăng lại SKAN iOS tổng hợp mà họ nhận được với AppsFlyer trong bối cảnh chiến dịch ứng dụng iOS. Những lượt đăng lại này thể hiện số lượt cài đặt từ nhiều kênh như hiển thị và YouTube, nhưng thường loại trừ hầu hết lượt tìm kiếm vì SKAN không hỗ trợ theo dõi ứng dụng web->tại thời điểm này.
* AppsFlyer giải mã lượt đăng lại, sau đó cập nhật bảng điều khiển và báo cáo SKAN (bao gồm cả báo cáo dữ liệu thô đăng lại).
* <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#ios-145-srn-attribution">Ý nghĩa của iOS 14.5 đối với báo cáo SRN</Anchor>

**Những điều cần lưu ý**:

Khi nhận được bài đăng lại trên iOS, Google xác định thời gian nhấp chuột cuối cùng bằng cách sử dụng tín hiệu phân phối quảng cáo. Tuy nhiên, AppsFlyer coi thời gian nhấp chuột là thời gian cài đặt. Điều này có thể dẫn đến sự sai khác giữa bảng điều khiển của AppsFlyer và của Google.

Do phương thức báo cáo lượt nhấp chuột của Google và cập nhật dữ liệu hàng ngày trở về trước, AppsFlyer lấy dữ liệu trong 45 ngày trước đó và hiển thị lượt cài đặt theo lượt nhấp chuột gần nhất trước ngày cài đặt.  Ví dụ, một lượt nhấp chuột vào ngày 1 tháng 7 có thể được báo cáo cho AppsFlyer cho đến  ngày 15 tháng 8. AppsFlyer hiển thị lượt cài đặt này theo ngày nhấp chuột được Google báo cáo. Điều này tác động đến <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#reporting-options">các báo cáo</Anchor> như sau:

* Báo cáo tổng hợp và bảng điều khiển cập nhật trở về trước.
* <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports">Báo cáo dữ liệu thô</Anchor> không thay đổi hồi tố. Dữ liệu (được cung cấp qua Data Locker) được cung cấp trong các thư mục theo ngày Google cung cấp dữ liệu cho AppsFlyer (ngày đến dữ liệu).

<div id="set-up-interoperation" />

## Thiết lập hoạt động tương tác

Để thiết lập hoạt động tương tác với Google Ads, hãy hoàn thành các bước trong các tab sau.

<div id="set-up-postbacks" />

<Accordion title="Thiết lập đăng lại">

**Để thiết lập gửi đăng lại:**

| Bước | Thao tác | Chi tiết |
| --- | --- | --- |
| <span id="1"></span>1 | Xem lại cài đặt SKAN | Kiểm tra đảm bảo rằng <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide">giải pháp SKAN</Anchor> của AppsFlyer đã được thiết lập và bật. Làm như vậy sẽ cho phép SDK AppsFlyer gọi ra API SKAN và đặt giá trị chuyển đổi.<br /><br />**Để xem lại cài đặt SKAN**:<ol><li>Trong AppsFlyer, đi đến **Configuration** > **SKAN Conversion Studio**.</li><li>Nhấp vào tùy chọn (⋮) và kiểm tra đảm bảo rằng **phép đo SKAN** đã được bật.</li></ol>![skan-settings.png](https://files.readme.io/5602fded7e030177bb921ff83ff1e6dad7a230a87825e112314935a4c3dd83dd-4406452045457.png)<ol><li>Chọn chế độ đo ưu tiên của bạn.<br />Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Ghi lại tên sự kiện chính xác đã đặt. Bạn sẽ cần chúng trong bước tiếp theo. **Lưu ý!** Tên có phân biệt chữ hoa chữ thường.</li></ol> |
| <span id="2"></span>2 | Ánh xạ sự kiện trong ứng dụng trong AppsFlyer | **Để xem và thiết lập ánh xạ sự kiện trong ứng dụng**:<ol><li>Trong AppsFlyer, đi đến **Configuration** > **Active integrations**.</li><li>Chọn **Google Ads**.</li><li>Từ tab **Integration**, hãy kiểm tra đảm bảo rằng **Activate Partner** đã được bật. Nếu không, trước tiên bạn phải hoàn tất <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers">quy trình tích hợp với Google Ads</Anchor>.</li><li>Trong **phần Đăng lại sự kiện trong ứng dụng**:<ol><li>Nếu chưa bật, hãy bật tùy chọn **In-app events postback**.</li><li>Cách tốt nhất là ánh xạ các sự kiện liên quan đến loại phép đo hiện được chọn. Lưu ý! Trong trường hợp đo lường doanh thu, hãy liên kết af\_skad\_revenue với sự kiện doanh thu thích hợp trên Google</li></ol></li><li>Cuộn xuống cuối trang.</li><li>Nhấp vào **Save integration**.</li></ol> |

</Accordion>

<div id="allow-google-ads-to-share-skan-data-with-appsflyer" />

<Accordion title="Cho phép Google Ads chia sẻ dữ liệu SKAN với AppsFlyer">

Để xem số lượt cài đặt SKAN được phân bổ cho Google Ads trong bảng điều khiển SKAN của AppsFlyer, bạn phải cho phép Google Ads chia sẻ dữ liệu SKAN với AppsFlyer.

**Để cấp cho Google Ads quyền chia sẻ dữ liệu SKAN với AppsFlyer:**

1. Quy trình sau đây phải được thực hiện bởi nhà quảng cáo, đại lý hoặc cả hai.
2. Trong AppsFlyer, đi đến **Configuration** > **Active integrations**.
3. Tìm kiếm và chọn **Google Ads**.
4. Chuyển đến tab **SKAN** .

   <Image alt="mceclip0.png" src="https://files.readme.io/ba8d881ca8430bfdcf67a37e862ad3e31a9af522f2f877d3fba30bc2e13006a6-4404428381457.png" width="309px" />
5. Nếu **thông báo tạm thời không khả dụng xuất hiện**, đa phần các trường hợp đó có nghĩa là trình chặn quảng cáo đang hoạt động. Nếu vậy, hãy tắt trình chặn quảng cáo và tải lại trang. Nếu không, hãy liên hệ với bộ phận hỗ trợ của AppsFlyer.

   ![mceclip1.png](https://files.readme.io/e86b868f71e11ad347ff7557a793090d9d6adb8fe4df4f9010c8d770b373ac6a-4404428420497.png)
6. Nhấp vào **Google Ads login**.
   * Bạn phải đăng nhập vào Google Ads với vai trò người dùng Quản trị viên trên tài khoản.
   * Nếu tài khoản Google được liên kết với nhiều ứng dụng, hãy đăng nhập một lần và tất cả các ứng dụng đều được cấp quyền. Nói cách khác, không cần phải cấp quyền trên cơ sở từng ứng dụng.
   * AppsFlyer lấy dữ liệu cho tất cả ứng dụng iOS của AppsFlyer mà tài khoản Google của bạn được liên kết, bất kể cài đặt đối tác kích hoạt của ứng dụng hay không.
7. Thực hiện theo các hướng dẫn trong giao diện người dùng.
8. Trong một số trường hợp, bạn có thể được nhắc cấp cho AppsFlyer quyền **Quản lý chiến dịch AdWords.** Nếu vậy, bạn phải kích hoạt quyền. Đừng lo lắng, chúng tôi sẽ không thực hiện thay đổi đối với tùy chọn cài đặt chiến dịch của bạn.

   [<Image alt="GoogleManageAdWords.png" src="https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png" width="182px" />](https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png)
9. Kiểm tra đảm bảo rằng trạng thái tài khoản **waiting for sync** hiển thị.  
   Thông báo này vẫn tồn tại cho đến khi chúng tôi nhận được dữ liệu từ Google Ads (tối đa 24 giờ.)
10. Đợi đến sau 02:00 UTC ngày hôm sau, sau đó xác minh rằng trạng thái chuyển sang **active.**  
    Dữ liệu trong bảng điều khiển SKAN cập nhật hàng ngày trước 08:00 UTC. **Lưu ý**! Như được mô tả trong phần những điều cần lưu ý, Google có thể cập nhật dữ liệu trở về trước 45 ngày.
11. Đọc về [sự sai khác về đo lường](/docs/get-skan-postback-data-from-google-ads#measurement-and-timing-differences-between-appsflyer-and-google-ads).

</Accordion>

<div id="additional-information" />

## Thông tin bổ sung

<div id="turning-off-the-skan-integration" />

<Accordion title="Tắt tích hợp SKAN">

Khi tắt tính năng tích hợp Google Ads, việc tắt nút chuyển đổi **Activate partner** là chưa đủ, bạn phải xóa riêng các kết nối SKAN để dừng việc ghi dữ liệu SKAN.

**Để tắt tích hợp SKAN:**

1. Trong AppsFlyer, đi đến **Configuration** > **Active integrations**.
2. Tìm kiếm và chọn Google Ads.
3. Chuyển đến tab **SKAN**.
4. Nhấp vào biểu tượng xóa cho tài khoản bạn muốn xóa.

</Accordion>

<div id="measurement-and-timing-differences-between-appsflyer-and-google-ads" />

<Accordion title="Sự sai khác về đo lường và thời gian giữa AppsFlyer và Google Ads">

| Mục | Chi tiết |
| --- | --- |
| <span id="earliest-data-availability"></span>Tính sẵn có sớm nhất của dữ liệu | Dữ liệu sẽ sẵn có kể từ ngày bạn bật tính năng tích hợp theo giờ UTC. Vì Google sử dụng thời gian nhấp chuột nên số lượt cài đặt trước ngày bắt đầu có thể hiển thị hồi tố. |
| <span id="install-date"></span>Ngày cài đặt | Google đặt thời gian cài đặt thành thời gian nhấp chuột cuối cùng ước tính trước lượt cài đặt. Chính Google xác định thời gian nhấp chuột bằng tín hiệu phân phối quảng cáo.<br /><br />Cần xét đến những mục sau đây khi so sánh các nguồn phương tiện và bảng điều khiển trong AppsFlyer:<ul><li>AppsFlyer không xét đến múi giờ của ứng dụng hoặc múi giờ của tài khoản quảng cáo Google Ads.</li><li>Google có thể báo cáo số lượt cài đặt trở về trước trong 45 ngày sau ngày cài đặt.</li><li>Trong trường hợp các nguồn phương tiện khác, chúng tôi tính thời gian cài đặt bằng cách sử dụng thời gian gửi lại.</li></ul> |
| <span id="installs"></span>Lượt cài đặt | Từ Google Ads API V10+, AppsFlyer chỉ hiển thị các lượt cài đặt từ các lượt đăng lại với did\_win=TRUE. Do đó, số lượt cài đặt trong AppsFlyer có thể thấp hơn so với số lượt trong bảng điều khiển Google Ads. |

</Accordion>

<div id="troubleshooting-and-faq" />

<Accordion title="Khắc phục sự cố và Câu hỏi thường gặp">

| Mục | Chi tiết |
| --- | --- |
| <span id="sending-events-to-google-ads"></span>Gửi sự kiện tới Google Ads | **Hỏi**: Việc gửi các lượt đăng lại sự kiện bổ sung tới Google Ads cho những sự kiện không được chọn trong tùy chọn đo lường giá trị chuyển đổi có hợp lý không?<br /><br />**Đáp**: Đối với những người dùng đồng ý, hãy gửi đầy đủ các sự kiện để tối đa hóa khả năng tối ưu hóa của Google Ads. |
| <span id="map-multiple-events-to-the-same-google-ads-event"></span>Ánh xạ nhiều sự kiện với cùng một sự kiện Google Ads | **Hỏi**: Tôi có thể liên kết nhiều sự kiện trong ứng dụng với một sự kiện Google Ads không?<br /><br />**Đáp**: Nếu nhiều sự kiện được ánh xạ tới một sự kiện tiêu chuẩn của Google Ads, thì Google Ads không thể phân biệt giữa các sự kiện. Vì vậy, Google Ads sẽ tối ưu hóa theo một sự kiện mà họ ghi nhận. |
| <span id="campaign-types-supported"></span>Các loại chiến dịch được hỗ trợ | **Hỏi:** Những loại chiến dịch Google Ads nào được hỗ trợ?<br /><br />**Đáp**: Chiến dịch iOS giữa Web và ứng dụng và Giữa các ứng dụng bao gồm tìm kiếm, video, v.v. |
| <span id="no-data-to-pull"></span>Không có dữ liệu để tải về | **Hỏi:** Tại sao trạng thái kết nối hiển thị "Không có dữ liệu để tải về: Kiểm tra quyền chia sẻ dữ liệu Google của bạn"?<br /><br />**Đáp**: Chưa có dữ liệu SKAN hoặc bạn cần đăng nhập vào Google Ads bằng vai trò người dùng Quản trị viên trên tài khoản. |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Thông số và hạn chế">

| Thông số | Mô tả |
| --- | --- |
| <span id="engaged-views"></span>Lượt xem có tương tác | Lượt xem có tương tác được tính là lượt nhấp chuột và đăng lại được gửi cho chúng giống như đối với bất kỳ phân bổ lượt nhấp qua nào. |
| <span id="data-freshness"></span>Tính cập nhật của dữ liệu | <ul><li>Chúng tôi thu thập dữ liệu SKAN từ Google Ads hàng ngày bắt đầu từ 01:00 UTC.</li><li>Bảng điều khiển và dữ liệu tổng hợp cập nhật 7 giờ sau.</li></ul> |
| <span id="reports-available"></span>Các báo cáo có sẵn | Dữ liệu Google Ads có sẵn trong trang tổng quan SKAN, báo cáo dữ liệu tổng hợp và dữ liệu thô. Xem <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide#reporting-options">các tùy chọn báo cáo SKAN.</Anchor> |
| <span id="agencies"></span>Đại lý | Nếu đại lý có vai trò người dùng Quản trị viên trong tài khoản Google Ads của nhà quảng cáo thì họ có thể thực hiện quy trình trong bài viết này và thay mặt nhà quảng cáo cho phép hoạt động tương tác Google SKAN. Nhà quảng cáo cũng không cần phải đăng nhập vào Google Ads của mình. Thông tin đăng nhập của đại lý được chỉ định trong tài khoản của nhà quảng cáo. |

</Accordion>

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-solution-guide">Hướng dẫn giải pháp SKAN của AppsFlyer</Anchor>

<div data-zendesk-anchors="get-skan-postback-data-from-google-ads=nh%E1%BA%ADn-d%E1%BB%AF-li%E1%BB%87u-%C4%91%C4%83ng-l%E1%BA%A1i-skan-t%E1%BB%AB-google-ads h_01HCHYGCVJA3C8WJS8JH7BG0CD=nh%E1%BA%ADn-d%E1%BB%AF-li%E1%BB%87u-%C4%91%C4%83ng-l%E1%BA%A1i-skan-t%E1%BB%AB-google-ads set-up-interoperation=thi%E1%BA%BFt-l%E1%BA%ADp-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-t%C6%B0%C6%A1ng-t%C3%A1c h_01HCHYGCVJY5KT4J6RQS0BJ90G=thi%E1%BA%BFt-l%E1%BA%ADp-ho%E1%BA%A1t-%C4%91%E1%BB%99ng-t%C6%B0%C6%A1ng-t%C3%A1c h_01HCHYGCVJKHF0NFJSAZMMKZ7Z=set-up-postbacks h_01HCHYGCVJEA39W87MWXF7P018=allow-google-ads-to-share-skan-data-with-appsflyer additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HCHYGCVJTS53PCGK21BEZB2T=th%C3%B4ng-tin-b%E1%BB%95-sung h_01HCHYGCVJCSGKYQD3EH0GKZVS=turning-off-the-skan-integration h_01HCHYGCVJE80JX9BKE8NFMA45=measurement-and-timing-differences-between-appsflyer-and-google-ads h_01HCHYGCVJX832CCX87JHGD50W=troubleshooting-and-faq h_01HCHYGCVJ1D32JW8G9YSR27PN=specifications-and-limitations h_01HE7RMSECNDW9VD9XY6H01H55=xem-th%C3%AAm" />
