---
title: Phân bổ Mời người dùng
metadata:
  keywords:
    - OneLink
    - Advertisers
    - User invite
    - Developers
    - Marketers
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2017-08-30T12:13:45Z'
  edited_at: '2023-10-02T03:36:17Z'
  id: 115004480866
  locale: vi
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/vi/articles/115004480866
---
> **Tổng quan:** Phân bổ và ghi nhận các lượt cài đặt mới khi những người dùng hiện có mời người khác sử dụng ứng dụng của bạn.

[![Invite_Attribution_new.png](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)

<div id="about-user-invite-attribution" />

## Giới thiệu về phân bổ lời mời người dùng

Lời mời của người dùng có nghĩa là người dùng ứng dụng hiện tại của bạn chia sẻ các liên kết chuyển hướng người khác (ví dụ: bạn bè của họ) để họ tải xuống/mở ứng dụng của bạn.

Phân bổ lời mời người dùng có nghĩa là bạn phân bổ bất kỳ lượt cài đặt hoặc tương tác ứng dụng mới nào cho những người dùng đã gửi giới thiệu.

Phân bổ lời mời người dùng cho phép bạn:

* Phân tích chi phí và ROI của lời mời người dùng. Lời mời người dùng sử dụng hết không gian quảng cáo ứng dụng của bạn, mặt khác có thể được sử dụng để tạo doanh thu quảng cáo. Bạn có thể muốn xem liệu lời mời người dùng có mang lại ROI tốt hơn các lựa chọn thay thế hay không.
* Ghi lại thông tin về những người dùng của bạn, những người giới thiệu người khác nhiều nhất. Những người dùng mời người khác vào ứng dụng của bạn là người dùng tương tác, có giá trị cao, những người mà bạn có thể muốn nhắm mục tiêu lại hoặc khuyến khích.

Bạn cũng có thể sử dụng dữ liệu từ các đường liên kết để:

* Tùy chỉnh trải nghiệm của người dùng mới. Ví dụ, mở ứng dụng tới nội dung cụ thể hoặc thay vì tin nhắn chung chung, hãy cá nhân hóa tin nhắn chào mừng, chẳng hạn như "Xin chào John! Bạn của bạn, Maria muốn thách đấu một trò chơi với bạn. Hãy chơi ngay!"
* Tặng thưởng cho người dùng giới thiệu người khác. [Tìm hiểu thêm](/docs/user-invite-attribution#reward-referrers-for-user-invite-installs)

Liên kết lời mời người dùng mà người dùng chia sẻ với người khác thực chất là liên kết tùy chỉnh OneLink (URL rút gọn) mà SDK AppsFlyer tạo được tích hợp vào ứng dụng của bạn. Cài đặt OneLink của bạn đảm bảo rằng người dùng nhận được lời mời sẽ được chuyển hướng đến đúng nơi—đến đúng cửa hàng ứng dụng, vào ứng dụng của bạn hoặc được liên kết sâu/trì hoãn liên kết sâu đến một trang cụ thể trong ứng dụng của bạn. <Anchor target="_blank" href="/marketers/vi/docs/onelink-guide">Tìm hiểu thêm về OneLink</Anchor>

<div id="flow" />

### Quy trình

Quy trình hoạt động như sau:

1. Người dùng A nhấn từ trong ứng dụng của họ để chia sẻ ứng dụng với bạn bè. (Người dùng A đã cài đặt ứng dụng và đăng nhập.)
2. Thao tác nhấn sẽ tạo liên kết với thông số xác định Người dùng A trên đó.
3. Người dùng A gửi liên kết đến Người dùng B qua email/WhatsApp/SMS, v.v.
4. Nếu Người dùng B:
   * Đã cài đặt ứng dụng, ứng dụng sẽ mở ra. Người dùng B có thể được liên kết sâu đến một trang cụ thể trong ứng dụng và/hoặc được thưởng.
   * Chưa cài đặt ứng dụng, họ sẽ được gửi đến đúng cửa hàng ứng dụng. Người dùng B có thể được trì hoãn liên kết sâu đến một trang cụ thể trong ứng dụng sau khi khởi chạy ứng dụng lần đầu và/hoặc Người dùng A có thể được thưởng.
   * Thực hiện một sự kiện trong ứng dụng, Người dùng A có thể được thưởng.

<div id="viewing-data" />

## Xem dữ liệu

Dữ liệu lời mời người dùng có sẵn thông qua bảng điều khiển và báo cáo của AppsFlyer. Trong bảng điều khiển AppsFlyer, bạn có thể lọc phân bổ lời mời của người dùng theo:

* **Nguồn truyền thông**: Lời mời ứng dụng.
* **Kênh**: Theo quyết định của nhà tiếp thị.
* **Chiến dịch**: Theo quyết định của nhà tiếp thị.

Trong báo cáo, nguồn truyền thông (tham số `pid`) được SDK gửi với giá trị mặc định `af_app_invites`. 

<div id="procedures" />

## Quy trình

**Để tạo liên kết lời mời người dùng**:

1. Tạo <Anchor target="_blank" href="/marketers/vi/docs/create-a-onelink-template#quy-trình">mẫu OneLink</Anchor>.
2. Quyết định giá trị thông số kênh và chiến dịch. Xem [thông số](/docs/user-invite-attribution#parameters).
3. Quyết định trường hợp sử dụng nào bạn muốn cho các liên kết. Các trường hợp sử dụng phổ biến bao gồm:
   * Liên kết sâu người dùng mới tới một trang cụ thể trong ứng dụng.
   * Ghi lại những người dùng đã giới thiệu.
   * Thưởng cho người dùng mới.
4. Liên hệ với nhà phát triển Android và iOS của bạn để lên kế hoạch về những tham số nào sẽ đảm trách các trường hợp sử dụng mà bạn muốn đối với các liên kết. Xem [các thông số](/docs/user-invite-attribution#parameters) có sẵn.
5. Yêu cầu nhà phát triển <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">triển khai liên kết sâu</Anchor> (sử dụng hoạt động mong muốn của các tham số trong mã).
6. Yêu cầu nhà phát triển gửi lời mời người dùng trong các nền tảng sau:

   <Tabs>
   <Tab title="Android">

   Xem [Lời mời người dùng Android](https://dev.appsflyer.com/hc/docs/dl_android_user_invite) trong Trung tâm Nhà phát triển.

   </Tab>

   <Tab title="iOS">

   Xem [Lời mời người dùng iOS](https://dev.appsflyer.com/hc/docs/dl_ios_user_invite) trong Trung tâm Nhà phát triển.

   </Tab>

   <Tab title="Unity">

   Xem [Lời mời người dùng](https://dev.appsflyer.com/hc/docs/userinvite) trong Trung tâm Nhà phát triển.

   </Tab>
   </Tabs>

<div id="parameters" />

<Accordion title="Tham số">

<div id="parametersvalues-provided-to-the-developer-to-implement-in-the-sdk" />

#### Thông số/giá trị được cung cấp cho nhà phát triển để triển khai trong SDK

<table><thead><tr><th><span>Thông số/giá trị</span></th><th><span>Lưu ý</span></th><th><span>Ghi lại giá trị/trường hợp sử dụng mà nhà phát triển nên triển khai</span></th></tr></thead><tbody><tr><td><span>ID mẫu OneLink</span></td><td><p>ID của mẫu OneLink với các cài đặt cơ bản mà tất cả các liên kết mời của người dùng sẽ dựa vào đó. Ví dụ: H5hv</p></td><td></td></tr><tr><td><span>Kênh</span></td><td><p>Tên kênh. Điều này giúp bạn sắp xếp và xem các phân bổ theo kênh trong UI AppsFlyer.</p></td><td></td></tr><tr><td><span>Chiến dịch</span></td><td><p>Tên chiến dịch. Điều này giúp bạn sắp xếp và xem các phân bổ theo chiến dịch trong UI AppsFlyer.</p></td><td></td></tr><tr><td> <span>is_retargeting=true</span><span></span><br/> </td><td><p>Đã thêm nếu chiến dịch của bạn nhắm mục tiêu lại người dùng hiện tại.</p></td><td></td></tr><tr><td><span>deep_link_value</span></td><td><p>Một thông số được sử dụng trên thiết bị của người dùng được giới thiệu để cung cấp cho họ trải nghiệm cụ thể. Thông thường, điều này được sử dụng để <span>đặt tên cho trang cụ thể mà người dùng sẽ được chuyển hướng tới. Ví dụ, nếu ứng dụng của bạn bán trái cây, bạn có thể liên kết sâu người dùng với trang táo.</span></p></td><td></td></tr><tr><td><span>deep_link_sub1</span></td><td rowspan="10"><p>Một thông số được sử dụng trên thiết bị của người dùng được giới thiệu để cung cấp cho họ trải nghiệm cụ thể. Vì deep_link_value thường được sử dụng để đưa người dùng đến một trang cụ thể nên thông số này có thể được sử dụng cho bất kỳ chức năng mong muốn nào khác. Ví dụ: để thêm phần thưởng hoặc giảm giá hoặc ghi lại người dùng đã giới thiệu. </p></td><td></td></tr><tr><td><span>deep_link_sub2</span></td><td></td></tr><tr><td><span>deep_link_sub3</span></td><td></td></tr><tr><td><span>deep_link_sub4</span></td><td></td></tr><tr><td><span>deep_link_sub5</span></td><td></td></tr><tr><td><span>deep_link_sub6</span></td><td></td></tr><tr><td><span>deep_link_sub7</span></td><td></td></tr><tr><td><span>deep_link_sub8</span></td><td></td></tr><tr><td><span>deep_link_sub9</span></td><td></td></tr><tr><td><span>deep_link_sub10</span></td><td></td></tr><tr><td><span>[Tùy chọn] pid</span></td><td><p>Theo mặc định, các liên kết bạn tạo bao gồm<span> nguồn truyền thông (thông số <code>pid</code>) với giá trị <code>af_app_invites</code>. </span></p><p><span>Để thay đổi giá trị, nhà phát triển của bạn cần phải thêm một thông số tùy chỉnh gọi là <code>pid</code> với giá trị bạn muốn. <strong>Lưu ý</strong>: Đối với Android, điều này chỉ hoạt động đối với SDK V6.4.2 trở lên.</span></p></td><td></td></tr><tr><td><span>Tên gắn thương hiệu</span></td><td><p>Tên miền gắn thương hiệu. Điều này giúp bạn sắp xếp và xem các phân bổ theo miền gắn thương hiệu trong UI AppsFlyer.</p></td><td></td></tr></tbody></table>

</Accordion>

<div id="example" />

<Accordion title="Ví dụ:">

Mark, nhà tiếp thị, có một ứng dụng bán trái cây. Anh ấy muốn tạo một liên kết liên kết sâu người dùng đến một trang trái cây cụ thể, với tùy chọn mua một số lượng trái cây cụ thể.

Anh ấy muốn liên kết này có thể được gửi qua lời mời của người dùng và tặng thưởng cho những người giới thiệu mỗi khi lượt giới thiệu của họ đưa đến lượt cài đặt ứng dụng và lượt mua trái cây mới.

Để thực hiện được tất cả những điều này, Mark gửi cho nhà phát triển của mình danh sách các thông số và giá trị sau đây để được sử dụng khi triển khai các liên kết lời mời người dùng: nhà phát triển của anh ấy sẽ triển khai:

| Tham số | value | Lưu ý |
| --- | --- | --- |
| deep\_link\_value | fruit\_name | Để liên kết sâu bằng phương thức AppsFlyer UDL. |
| deep\_link\_sub1 | promo\_code | Để liên kết sâu bằng phương thức AppsFlyer UDL. |
| deep\_link\_sub2 | referrer\_id | Để tạo liên kết thông qua SDK. |
| param\_1 | referrer\_id | Đối với sự kiện trong ứng dụng ghi lại mỗi lượt mua hàng. |
| Kênh | mobile\_share | Để phân bổ và xem dữ liệu trong AppsFlyer. |
| Chiến dịch | summer\_sale | Để phân bổ và xem dữ liệu trong AppsFlyer. |

</Accordion>

<div id="additional-information" />

## Thông tin bổ sung

<div id="record-user-invites-as-inapp-events" />

<Accordion title="Ghi lại lời mời của người dùng dưới dạng sự kiện trong ứng dụng">

Việc ghi lại sự kiện trong ứng dụng sau khi người dùng gửi lời mời người dùng sẽ giúp bạn xác định những người dùng giới thiệu người khác, cũng như các nguồn truyền thông giúp bạn có được những người giới thiệu này.

**Để ghi lại sự kiện lời mời người dùng trong ứng dụng**:

* Gửi một <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-event-structure#invite-af_invite">sự kiện af\_invite.</Anchor> Nhà phát triển cần triển khai điều này theo hướng dẫn của trung tâm nhà phát triển của chúng tôi.

**Lưu ý**: Bạn có thể thêm nhiều thông số mà bạn muốn liên kết với sự kiện. Chọn các thông số sẽ cung cấp ngữ cảnh bổ sung cho sự kiện và làm phong phú dữ liệu. <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#thiết-lập-sự-kiện-trong-ứng-dụng">Tìm hiểu thêm</Anchor>

</Accordion>

<div id="reward-referrers-for-user-invite-installs" />

<Accordion title="Tặng thưởng người giới thiệu dẫn đến lượt cài đặt từ lời mời người dùng">

**Để tặng thưởng người giới thiệu cho lời mời người dùng dẫn đến lượt cài đặt**:

1. Đảm bảo ID người giới thiệu là giá trị của một trong [các thông số deep\_link\_sub1-10](/docs/user-invite-attribution#parameters).
2. Yêu cầu nhà phát triển ứng dụng của bạn <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">triển khai liên kết sâu</Anchor> (sử dụng hoạt động mong muốn của các thông số được chọn trong mã).
3. Yêu cầu nhà phát triển backend làm việc với các nhà phát triển ứng dụng của bạn để truy xuất ID người giới thiệu (từ báo cáo của AppsFlyer) và trao thưởng cho những người giới thiệu.

Ví dụ:

1. Người dùng A mời Người dùng B cài đặt ứng dụng của bạn.
2. Khi Người dùng B khởi chạy ứng dụng, ứng dụng sẽ nhận được ID người giới thiệu của Người dùng A.
3. Backend của bạn truy xuất ID người giới thiệu từ báo cáo của AppsFlyer.
4. Trong backend của bạn, hãy thêm ID người giới thiệu của Người dùng A vào danh sách người dùng sẽ được thưởng.
5. Khi Người dùng A khởi chạy ứng dụng, hãy kiểm tra xem ID người giới thiệu của họ có nằm trong danh sách người dùng được thưởng hay không và nếu có thì hãy thưởng cho họ.

</Accordion>

<div id="reward-referrers-for-referred-user-actions" />

<Accordion title="Tặng thưởng người giới thiệu cho các hành động người dùng được giới thiệu">

**Để tặng thưởng người giới thiệu cho lời mời của người dùng dẫn đến một sự kiện trong ứng dụng cụ thể**:

1. <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-overview#thiết-lập-sự-kiện-trong-ứng-dụng">Tạo sự kiện trong ứng dụng</Anchor> mà bạn muốn tặng thưởng.
2. Yêu cầu nhà phát triển thêm thông số (ví dụ: param\_1) vào sự kiện với giá trị là ID người giới thiệu. **Lưu ý**: ID người giới thiệu ban đầu được ghi lại trên lượt cài đặt ứng dụng bằng [thông số](/docs/user-invite-attribution#parameters) bạn đã chọn (deep\_link\_sub1-10).
3. Yêu cầu nhà phát triển backend làm việc với các nhà phát triển ứng dụng của bạn để truy xuất ID người giới thiệu (từ báo cáo của AppsFlyer) và trao thưởng cho những người giới thiệu.

Ví dụ:

1. Người dùng A mời Người dùng B thực hiện một hành động trong ứng dụng của bạn.
2. Khi Người dùng B thực hiện hành động, một sự kiện trong ứng dụng sẽ được ghi lại có chứa ID người giới thiệu của Người dùng A.
3. Backend của bạn truy xuất ID người giới thiệu từ báo cáo của AppsFlyer.
4. Trong backend của bạn, hãy thêm ID người giới thiệu của Người dùng A vào danh sách người dùng sẽ được thưởng.
5. Khi Người dùng A khởi chạy ứng dụng, hãy kiểm tra xem ID người giới thiệu của họ có nằm trong danh sách người dùng được thưởng hay không và nếu có thì hãy thưởng cho họ.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Mô tả |
| --- | --- |
| Phiên bản SDK | Phải có SDK AppsFlyer phiên bản 4.8.0+ và SDK Unity phiên bản 4.17.0+. |
| <Anchor target="_blank" href="/marketers/vi/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page"> Trang đích của ứng dụng mạng xã hội</Anchor> | Các liên kết được tạo từ lời mời của người dùng không thể triển khai các trang đích của ứng dụng mạng xã hội. |
| Thời gian tồn tại (TTL) | Thời gian tồn tại mặc định (TTL) cho các URL ngắn OneLink được tạo thông qua lời mời người dùng SDK là 60 ngày. Mỗi lần liên kết được nhấp thì thời gian được kéo dài thêm 60 ngày. |
| Giá | Miễn phí cho tất cả các gói tài khoản |
| iOS 14 trở lên | Phân bổ lời mời người dùng không sử dụng IDFA, vì vậy iOS 14 hoàn toàn không ảnh hưởng đến nó. |
| ID URL | Có thể chính sửa ID URL (hoặc ID liên kết rút gọn) để làm nổi bật dịch vụ cung cấp của chiến dịch. Ví dụ: https://myapp.onelink.me/abc123/apples.ID URL không được vượt quá 50 ký tự và có thể sử dụng kết hợp giữa chữ cái và số. Theo mặc định, ID này gồm 8 ký tự.<br /><br />**Lưu ý**: Bạn chỉ có thể chỉnh sửa ID URL nếu ID hiện tại chưa được sử dụng. |

</Accordion>

<div data-zendesk-anchors="about-user-invite-attribution=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-ph%C3%A2n-b%E1%BB%95-l%E1%BB%9Di-m%E1%BB%9Di-ng%C6%B0%E1%BB%9Di-d%C3%B9ng h_01H98E1CZ2AG8AW2H77SPPHFGR=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-ph%C3%A2n-b%E1%BB%95-l%E1%BB%9Di-m%E1%BB%9Di-ng%C6%B0%E1%BB%9Di-d%C3%B9ng flow=quy-tr%C3%ACnh h_01H98E1CZ234MRBWDEYGZFCDRE=quy-tr%C3%ACnh viewing-data=xem-d%E1%BB%AF-li%E1%BB%87u h_01H98E1CZ23FEAS8JJC7FFTFXD=xem-d%E1%BB%AF-li%E1%BB%87u procedures=quy-tr%C3%ACnh-1 h_01H98E1CZ2VBCG0RREERW8FNJE=quy-tr%C3%ACnh-1 h_01H98E1CZ2WE6DJW717C6AJWXD=parameters parametersvalues-provided-to-the-developer-to-implement-in-the-sdk=th%C3%B4ng-s%E1%BB%91gi%C3%A1-tr%E1%BB%8B-%C4%91%C6%B0%E1%BB%A3c-cung-c%E1%BA%A5p-cho-nh%C3%A0-ph%C3%A1t-tri%E1%BB%83n-%C4%91%E1%BB%83-tri%E1%BB%83n-khai-trong-sdk h_01H98E1CZ2CANBK1T55DD103JB=th%C3%B4ng-s%E1%BB%91gi%C3%A1-tr%E1%BB%8B-%C4%91%C6%B0%E1%BB%A3c-cung-c%E1%BA%A5p-cho-nh%C3%A0-ph%C3%A1t-tri%E1%BB%83n-%C4%91%E1%BB%83-tri%E1%BB%83n-khai-trong-sdk h_01H98E1CZ2NXCCYEV12JC6EMFG=example additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung h_01H98E1CZ28T2SJ3YNY8TNCAZY=th%C3%B4ng-tin-b%E1%BB%95-sung h_01H98E1CZ2172W6845K099F814=record-user-invites-as-inapp-events h_01H98E1CZ316WWYK55XTN4C8JE=reward-referrers-for-user-invite-installs h_01H98E1CZ330FXG06A4MVQ56PW=reward-referrers-for-referred-user-actions h_01H98E1CZ3SPASZDF5CCY3T3B3=traits-and-limitations" />
