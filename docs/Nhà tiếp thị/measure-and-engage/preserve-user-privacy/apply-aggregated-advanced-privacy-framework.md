---
title: Khuôn khổ Aggregated Advanced Privacy
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2021-03-15T11:32:31Z'
  edited_at: '2023-11-16T10:20:04Z'
  id: 360018515798
  locale: vi
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/vi/articles/360018515798
---
> **Khái quát:** Bắt đầu với sự phát hành rộng rãi của iOS 14.5+ và việc thực thi ATT của Apple, nhà quảng cáo sử dụng khung Quyền riêng tư Nâng cao Hợp nhất (AAP) để kiểm soát tính khả dụng của dữ liệu phân bổ cấp người dùng từ nền tảng.

## Khung Quyền riêng tư Nâng cao Hợp nhất (AAP)

Khung Quyền riêng tư Nâng cao Hợp nhất (AAP) của AppsFlyer ngăn chặn việc theo dõi trên các ứng dụng và trang web thuộc sở hữu của các công ty khác nhau và khả năng nhận dạng duy nhất một người dùng hoặc thiết bị. AAP sử dụng các mức độ quyền riêng tư của Apple App Tracking Transparency làm điểm chuẩn tối thiểu cho các ngưỡng bảo vệ quyền riêng tư của mình.

Khuôn khổ này giúp cho các nhà quảng cáo khả năng kiểm soát tính khả dụng của dữ liệu phân bổ cấp người dùng thông qua nền tảng AppsFlyer.

Bắt đầu với  sự phát hành rộng rãi của iOS 14.5 và việc thực thi ATT của  Apple, nếu AAP được bật, dữ liệu phân bổ cấp người dùng cho những người dùng không đồng ý mà chạy iOS 14.5+ trở lên sẽ không có sẵn cho các nhà quảng cáo hoặc đối tác. 

AAP không ảnh hưởng đến tính khả dụng của dữ liệu phân bổ hợp nhất và báo cáo phân tích đối với các nhà quảng cáo và đối tác.

### Các tính năng bị ảnh hưởng bởi AAP

Nếu AAP được bật, dữ liệu do dữ liệu thô cung cấp sẽ bị ảnh hưởng và một số trường bị hạn chế hoặc không khả dụng. Điều này ảnh hưởng đến dữ liệu được các công cụ sau cung cấp:

* Data Locker
* API Pull dữ liệu thô
* API Push
* Trang xuất Bảng điều khiển
* Đăng lại đến các mạng
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/deferred-deep-linking">API Nhận dữ liệu chuyển đổi (GCD)</Anchor> trong ngữ cảnh của API dữ liệu ở mức người dùng phía máy khách.

Tính khả dụng của dữ liệu bị ảnh hưởng khi AAP được bật là như sau:

* **Dữ liệu phân bổ và gian lận (Protect360):** <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">Một số trường phân bổ bị hạn chế hoặc không khả dụng.</Anchor>
* **Dữ liệu về lượt nhấp chuột, lượt hiển thị và lượt nhấp chuột bị chặn (gian lận):** <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions#identifier-restriction">Các mã định danh liên quan đến thiết bị và người dùng</Anchor> sẽ không khả dụng.
* **Deferred deep linking**: Nếu bạn triển khai deferred deep linking trong truyền thông trả phí, hãy sử dụng <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unifieddeeplink">API liên kết sâu hợp nhất (UDL).</Anchor> Không thể sử dụng API cũ mà sử dụng GCD, trong bối cảnh người dùng không đồng ý. Trong trường hợp truyền thông sở hữu, deferred deep linking cho truyền thông sở hữu được hỗ trợ thông qua GCD và API deferred deep linking gần đây nhất.

## Các nguyên tắc về tính khả dụng của dữ liệu trong Quyền riêng tư Nâng cao Hợp nhất

Khi AAP áp dụng đối với dữ liệu của một người dùng nhất định, tính khả dụng của dữ liệu sẽ phụ thuộc vào trạng thái ATT của người dùng đó và nguồn truyền thông mang đến cho người dùng.

**Các định nghĩa:**

* **Dữ liệu phân bổ cấp người dùng:** Bản ghi dữ liệu chứa các mã định danh cấp thiết bị liên kết với dữ liệu phân bổ ở cấp người dùng
* **Dữ liệu phân bổ giới hạn cho các nhà quảng cáo:**

  * Khả dụng: Mã định danh cấp thiết bị. (IDFA khả dụng nếu người dùng đồng ý.)
  * Không khả dụng: Dữ liệu phân bổ nhận được qua đường dẫn phân bổ của nhà phát hành (ví dụ: nguồn truyền thông và chiến dịch). <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">Danh sách các trường bị hạn chế và không khả dụng đối với các nhà quảng cáo</Anchor> hay còn gọi là nguồn truyền thông bị hạn chế.
* **Dữ liệu phân bổ giới hạn cho các đối tác:**

  * Khả dụng: Chi tiết về chiến dịch hợp nhất.
  * Không khả dụng: Dữ liệu ở mức người dùng có thể giúp xác định người dùng như ID AppsFlyer, Dữ liệu tùy chỉnh, Customer User ID (CUID), ID lượt nhấp, IDFA, IDFV, IMEI, Tác nhân người dùng và địa chỉ IP.

Các thuật ngữ đã xác định được sử dụng trong hình và các phần tiếp theo để mô tả dữ liệu khả dụng đối với các nhà quảng cáo và đối tác.

![Advanced Privacy Framework - Advertisers (4).png](https://files.readme.io/0291fe2eea5f6efc41f2338824a0017be3e265f502e0d3999d52ac87b1ee7719-35847850634897.png)

Tính năng Bảo mật Nâng cao sẽ hoạt động khác khi được dùng trên web và phải sử dụng thông số af\_media\_type=web hoặc af\_media\_type=app. Xem <Anchor target="_blank" href="/partners/vi/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">tại đây</Anchor> để biết thêm thông tin chi tiết.

### Tính khả dụng của dữ liệu truyền thông sở hữu và trả phí

<div id="paid-media" />

<Accordion title="Truyền thông trả phí">

Truyền thông trả phí bao gồm các mạng quảng cáo trên điện thoại di động có tích hợp trong nền tảng AppsFlyer với mạng mà các nhà quảng cáo cùng chạy chiến dịch. 

#### Tính khả dụng của dữ liệu truyền thông trả phí theo trạng thái ATT

<table><tbody><tr><th rowspan="2"><p><span>Loại đa phương tiện</span></p></th><th colspan="2"><p><span>Trạng thái ATT</span></p></th><th colspan="2"><p><span>Dữ liệu khả dụng đối với:</span></p></th></tr><tr><th><p><span>Ứng dụng dành cho nhà phát hành</span></p></th><th><p><span>Ứng dụng dành cho nhà quảng cáo</span></p></th><th><p><span>Nhà quảng cáo</span></p></th><th><p><span>Mạng Quảng cáo</span></p></th></tr><tr><td rowspan="4"><p><span>Ứng dụng</span></p></td><td><p><span>Được cấp quyền</span></p></td><td><p><span>Được cấp quyền</span></p></td><td><p><span>Dữ liệu phân bổ cấp người dùng</span></p></td><td><p><span>Dữ liệu phân bổ cấp người dùng</span></p></td></tr><tr><td><p><span>Chưa được cấp quyền</span></p></td><td><p><span>Được cấp quyền</span></p></td><td><p><span>Dữ liệu phân bổ giới hạn cho các nhà quảng cáo </span></p></td><td><p><span>Dữ liệu phân bổ giới hạn cho các đối tác</span></p></td></tr><tr><td><p><span>Được cấp quyền</span></p></td><td><p><span>Chưa được cấp quyền</span></p></td><td><p><span>Dữ liệu phân bổ giới hạn cho các nhà quảng cáo </span></p></td><td><p><span>Dữ liệu phân bổ giới hạn cho các đối tác</span></p></td></tr><tr><td><p><span>Chưa được cấp quyền</span></p></td><td><p><span>Chưa được cấp quyền</span></p></td><td><p><span>Dữ liệu phân bổ giới hạn cho các nhà quảng cáo </span></p></td><td><p><span>Dữ liệu phân bổ giới hạn cho các đối tác</span></p></td></tr><tr><td rowspan="2"> <br/><p><span>Web</span></p></td><td><p><span>Không áp dụng</span></p></td><td><p><span>Được cấp quyền</span></p></td><td><p><span>Dữ liệu phân bổ cấp người dùng</span></p></td><td><p><span>Dữ liệu phân bổ cấp người dùng</span></p></td></tr><tr><td><p><span>Không áp dụng</span></p></td><td><p><span>Chưa được cấp quyền</span></p></td><td><p><span>Dữ liệu phân bổ giới hạn cho các nhà quảng cáo </span></p></td><td><p><span>Dữ liệu phân bổ giới hạn cho các đối tác</span></p></td></tr></tbody></table>

</Accordion>

<div id="owned-media" />

<Accordion title="Truyền thông Sở hữu">

Khuôn khổ AppTrackingTransparency của Apple chỉ áp dụng cho dữ liệu được thu thập từ các công ty khác nhau. Do đó, dữ liệu phân bổ cấp người dùng truyền thông sở hữu sẽ khả dụng cho các nhà quảng cáo bất kể trạng thái đồng ý ATT của người dùng là thế nào.

Truyền thông sở hữu bao gồm các chiến dịch tiếp thị kỹ thuật số được nhà quảng cáo sử dụng để tiếp cận khách hàng. Nội dung này bao gồm các chiến dịch email, quảng cáo chéo, thông báo đẩy, v.v. Trong AppsFlyer, các chiến dịch sử dụng mạng quảng cáo không được coi là truyền thông sở hữu.

</Accordion>

## Kiểm soát AAP

<div id="aap-central-switch" />

<Accordion title="Quyền riêng tư Nâng cao Hợp nhất—nút chuyển đổi cấp ứng dụng">

AAP là một nút chuyển đổi cấp ứng dụng kiểm soát cài đặt Quyền riêng tư Nâng cao đối với tất cả các đối tác của ứng dụng đã chọn. Nút chuyển đổi AAP nằm trên trang **App Settings**. Khi nút chuyển đổi AAP ở trạng thái bật, các nút chuyển đổi **Quyền riêng tư Nâng cao** đối với tất cả các đối tác của ứng dụng đã chọn sẽ tự động được bật và không sửa đổi được. Khi tắt, nhà quảng cáo có thể đi đến từng tích hợp đối tác riêng lẻ và bật **Quyền riêng tư Nâng cao**.

![AAPcontrol.png](https://files.readme.io/ddc8140ada9278eab447ecdfa4d88c56e07a0ed54b10b71de1cc2352f9590d40-35847850639121.png)

#### **AAP được bật**

* Có sẵn công cụ phân bổ hợp nhất. Điều này bao gồm, ví dụ: Bảng điều khiển tổng quan và các công cụ báo cáo như Nhóm người và API chính.
* [Nút chuyển đổi Quyền riêng tư Nâng cao của đối tác](/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch) đã được bật và không thể sửa đổi. Lưu ý! Những nút này bị khóa và không thể thay đổi.
* Tính khả dụng của dữ liệu cấp người dùng đối với các nhà quảng cáo và đối tác bị hạn chế, như đã định nghĩa trong [phần trước](/docs/apply-aggregated-advanced-privacy-framework#các-nguyên-tắc-về-tính-khả-dụng-của-dữ-liệu-trong-quyền-riêng-tư-nâng-cao-hợp-nhất).

**AAP bị vô hiệu hóa**

* Có sẵn công cụ phân bổ hợp nhất. Điều này bao gồm, ví dụ: Bảng điều khiển tổng quan và các công cụ báo cáo như Nhóm người và API chính.
* Dữ liệu phân bổ ở cấp người dùng khả dụng đối với các nhà quảng cáo.
* Cài đặt Quyền riêng tư Nâng cao cho mỗi đối tác có thể được đặt riêng.

*Trước khi tắt AAP, hãy cân nhắc xem nếu làm như vậy thì liệu bạn có cung cấp dữ liệu phân bổ cấp người dùng cho các bên thứ ba không và cách họ sẽ sử dụng dữ liệu. Bạn nên làm việc chặt chẽ với các cố vấn pháp lý và chuyên gia khác của mình liên quan đến cách Apple xác định về theo dõi. Không có gì được nêu ở đây là lời khuyên pháp lý. Nội dung này được cung cấp để đưa ra thông tin và thuận tiện cho bạn.*

**Để đặt cài đặt Quyền riêng tư Nâng cao Hợp nhất**:

1. Trong AppsFlyer, đi đến **Settings** (Cài đặt) > **App Settings** (Cài đặt của Ứng dụng).
2. Bật hoặc tắt **Quyền riêng tư Nâng cao Hợp nhất** theo yêu cầu.
3. Nhấp vào **Save** (Lưu).

</Accordion>

<div id="partner-advanced-privacy-switch" />

<Accordion title="Quyền riêng tư Nâng cao—nút chuyển đổi cấp đối tác">

Nếu AAP bị tắt, các nhà quảng cáo có thể đặt cài đặt Quyền riêng tư Nâng cao cho từng mạng quảng cáo riêng.

![APControl.png](https://files.readme.io/8e5a005cbadb5665cf255d39d6fa425298510f719b166c2013a2dfe57d4e982b-35847865312657.png)

**Để tắt Quyền riêng tư Nâng cao của đối tác:**

1. Xác minh đã tắt nút chuyển đổi trung tâm cho AAP trong trang **App Settings**.
2. Đi đến **Configuration** > **Active Integrations**. Chọn mạng quảng cáo.
3. Trong thẻ **Integration**, hãy tắt **Advanced Privacy.**

**Thay đổi cài đặt AAP và tác động đến cài đặt Quyền riêng tư Nâng cao của đối tác**

Như đã nêu trước đây, cài đặt AAP ghi đè cài đặt Quyền riêng tư Nâng cao (AP) ở cấp đối tác. Tuy nhiên, nếu sau đó bạn tắt AAP (nút chuyển đổi trung tâm), cài đặt Quyền riêng tư Nâng cao cấp đối tác riêng lẻ sẽ quay lại trạng thái trước đó. Có nghĩa là:

* Trước đây, bạn đã tắt AAP và tắt một số cài đặt AP của đối tác.
* Sau này, bạn bật AAP. Hãy nhớ rằng, khi AAP được bật, nó sẽ ghi đè cài đặt của đối tác và tất cả các đối tác được coi là đang bật.
* Bây giờ bạn tắt AAP một lần nữa. Có nghĩa là giờ sẽ áp dụng các cài đặt riêng của đối tác. Vì vậy, đối với một số đối tác, cài đặt này đã bị tắt.

</Accordion>

## Ý nghĩa của AAP đối với các đối tác của bạn

<div id="ad-networks" />

<Accordion title="Mạng quảng cáo">

#### **Đăng lại đến các đối tác mạng quảng cáo**

<Anchor target="_blank" href="/partners/vi/docs/advanced-privacy-guide-postback-macros-for-ad-networks">AAP ảnh hưởng đến mạng quảng cáo</Anchor> liên quan đến dữ liệu được chia sẻ với chúng và phù hợp với các nguyên tắc AAP áp dụng đối với nhà quảng cáo trong bối cảnh của mạng quảng cáo. Dữ liệu được chia sẻ với các mạng quảng cáo là thông qua đăng lại, khác nhau giữa mạng quảng cáo được phân bổ và mạng quảng cáo không được phân bổ.

Quy tắc chia sẻ dữ liệu được mô tả áp dụng cho một mạng quảng cáo cụ thể nếu một trong hai nút chuyển đổi dưới đây ở trạng thái bật:

* AAP: Chuyển đổi cấp ứng dụng
* AP: Chuyển đổi cấp độ đối tác

#### **Đăng lại đến các mạng quảng cáo được phân bổ**

Trong trường hợp mạng được phân bổ, loại đăng lại được sử dụng để chia sẻ dữ liệu phụ thuộc vào trạng thái đồng ý của người dùng như sau:

* **Người dùng đồng ý:** Đăng lại thông thường chứa dữ liệu phân bổ cấp người dùng bao gồm cả mã định danh.
* **Người dùng không đồng ý:** Đăng lại Quyền riêng tư Nâng cao (AP) có chứa dữ liệu phân bổ giới hạn. Loại đăng lại này chứa chi tiết về chiến dịch và không gồm mã định danh.
  * **Điều kiện tiên quyết:** Để một mạng quảng cáo nhận được đăng lại AP, họ phải tích hợp AP với AppsFlyer. Không có tích hợp thì sẽ không có đăng lại nào được gửi cho người dùng không đồng ý.
  * **Trường hợp ngoại lệ:** Đối với các lượt cài đặt được phân bổ cho Apple Search Ads (ASA), nếu một mạng quảng cáo không hỗ trợ Quyền riêng tư Nâng cao thiết lập đăng lại lượt cài đặt thành **All media sources, including organic**, Apple Search Ads (ASA) vẫn gửi đăng lại lượt cài đặt đến mạng quảng cáo đó bất kể trạng thái Quyền riêng tư Nâng cao ở phía nhà quảng cáo đó là gì.

Các tình huống khác nhau về sự đồng ý của người dùng và loại đăng lại được sử dụng được minh họa trong hình sau đây.

![AAP - Attributed ad networks.png](https://files.readme.io/d776c77115beb4c6b6ada1850077f186aa2feb809a8b69af8cf0ec760cd02b39-35847865314961.png)

Tính năng Bảo mật Nâng cao sẽ hoạt động khác khi được dùng trên web và phải sử dụng thông số af\_media\_type=web hoặc af\_media\_type=app. Xem <Anchor target="_blank" href="/partners/vi/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">tại đây</Anchor> để biết thêm thông tin chi tiết.

#### **Đăng lại cho các đối tác chưa được phân bổ**

Đăng lại không được phân bổ được gửi tới một mạng khi tùy chọn gửi trong tab tích hợp của đối tác tích hợp được đặt thành *tất cả các nguồn truyền thông, bao gồm cả nguồn tự nhiên* và đối tác đó không được phân bổ cho sự kiện như được minh họa trong hình bên dưới.

![InAppEventAll.png](https://files.readme.io/e24037f75b2b82797031eb13d5e063b8c2006812491e69674ff066ac830919f7-35847850644881.png)

Các tình huống khác nhau về sự đồng ý của người dùng và loại đăng lại được sử dụng được minh họa trong sơ đồ sau đây.

![AAP - Unattributed ad networks.png](https://files.readme.io/bb8a5d192e2120f8df90b9be044c0b4abf48c2250f5128fbbce76c60c89718cc-35847850645649.png)

Tính năng Bảo mật Nâng cao sẽ hoạt động khác khi được dùng trên web và phải sử dụng thông số af\_media\_type=web hoặc af\_media\_type=app. Xem <Anchor target="_blank" href="/partners/vi/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">tại đây</Anchor> để biết thêm thông tin chi tiết.

</Accordion>

<div id="analytics-partners" />

<Accordion title="Đối tác phân tích">

AAP ảnh hưởng đến các đối tác phân tích liên quan đến dữ liệu được chia sẻ với họ và phù hợp với các nguyên tắc AAP áp dụng đối với các nhà quảng cáo trong bối cảnh của đối tác phân tích.  Dữ liệu được chia sẻ với đối tác thông qua đăng lại.

Các quy tắc chia sẻ dữ liệu được mô tả áp dụng cho một đối tác cụ thể nếu một trong hai nút chuyển đổi dưới đây ở trạng thái bật:

* AAP: Chuyển đổi cấp ứng dụng
* AP: Chuyển đổi cấp độ đối tác

Đăng lại chứa dữ liệu phân bổ cấp người dùng bao gồm cả mã định danh người dùng được gửi đối với người dùng đồng ý. Không có đăng lại nào được gửi trong trường hợp người dùng không đồng ý.

Các tình huống khác nhau về sự đồng ý của người dùng và loại đăng lại được sử dụng được minh họa trong hình sau đây.

![AAP - Analytics partner.png](https://files.readme.io/4bb77720f9e0be093e325f989987f5b5ba2dba5aa26e2f32df5f1bd5b99161eb-35847865320593.png)

Tính năng Bảo mật Nâng cao sẽ hoạt động khác khi được dùng trên web và phải sử dụng thông số af\_media\_type=web hoặc af\_media\_type=app. Xem <Anchor target="_blank" href="/partners/vi/docs/advanced-privacy-guide-postback-macros-for-ad-networks#web-campaigns">tại đây</Anchor> để biết thêm thông tin chi tiết.

</Accordion>

<div id="agencies" />

<Accordion title="Đại lý">

**Tính khả dụng của dữ liệu**: Tác động của AAP đối với các đại lý cũng tương tự như đối với các nhà quảng cáo. Nếu dữ liệu thô khả dụng đối với đại lý cho một ứng dụng nhất định và AAP áp dụng cho dữ liệu nhất định của một người dùng, thì dữ liệu sẽ khả dụng theo các quy tắc về [dữ liệu phân bổ giới hạn đối với nhà quảng cáo](/docs/apply-aggregated-advanced-privacy-framework#các-nguyên-tắc-về-tính-khả-dụng-của-dữ-liệu-trong-quyền-riêng-tư-nâng-cao-hợp-nhất). 

**Đại lý thay đổi cài đặt Quyền riêng tư Nâng cao của mạng quảng cáo:**

* Nếu AAP bị tắt, đại lý có thể thiết lập cài đặt Quyền riêng tư Nâng cao của từng đối tác tích hợp.
* Theo mặc định, chỉ các nhà quảng cáo mới có thể thay đổi cài đặt Quyền riêng tư Nâng cao; tuy nhiên, nhà quảng cáo có thể cấp quyền cho đại lý một cách rõ ràng để thiết lập cài đặt Quyền riêng tư Nâng cao của các mạng quảng cáo do đại lý bật.

**Cấp quyền cho đại lý để thiết lập Quyền riêng tư Nâng cao**

![agency_advanced_privacy.png](https://files.readme.io/ac4a1aae41e9e39b9759006db84ea14df7495d0a14c02df7dbfb8dd93a2d2c23-35847865322129.png)

**Để cho phép một đại lý thiết lập Quyền riêng tư Nâng cao**:

1. Đi đến **Configuration** > **Active Integrations**. Chọn đại lý.
2. Trong thẻ **Permissions**, bật **Change the** **Advanced Privacy setting.**
3. Nhấp vào **Save** (Lưu).

</Accordion>

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/partners/vi/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Hướng dẫn Bảo mật Nâng cao và macro đăng lại cho mạng quảng cáo</Anchor>

<div data-zendesk-anchors="aggregated-advanced-privacy-framework=khung-quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao-h%E1%BB%A3p-nh%E1%BA%A5t-aap h_01HDPDE0H3SYFWBHK59HBV2P6N=khung-quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao-h%E1%BB%A3p-nh%E1%BA%A5t-aap aapimpacted-features=c%C3%A1c-t%C3%ADnh-n%C4%83ng-b%E1%BB%8B-%E1%BA%A3nh-h%C6%B0%E1%BB%9Fng-b%E1%BB%9Fi-aap h_01HDPDE0H339BPACN235V70MWW=c%C3%A1c-t%C3%ADnh-n%C4%83ng-b%E1%BB%8B-%E1%BA%A3nh-h%C6%B0%E1%BB%9Fng-b%E1%BB%9Fi-aap data-availability-principles-in-aggregated-advanced-privacy=c%C3%A1c-nguy%C3%AAn-t%E1%BA%AFc-v%E1%BB%81-t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u-trong-quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao-h%E1%BB%A3p-nh%E1%BA%A5t h_01HDPDE0H3QBE60DVBZ1MWNB9N=c%C3%A1c-nguy%C3%AAn-t%E1%BA%AFc-v%E1%BB%81-t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u-trong-quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao-h%E1%BB%A3p-nh%E1%BA%A5t paid-and-owned-media-data-availability=t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u-truy%E1%BB%81n-th%C3%B4ng-s%E1%BB%9F-h%E1%BB%AFu-v%C3%A0-tr%E1%BA%A3-ph%C3%AD h_01HDPDE0H326EXNCQHPVJWXK3H=t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u-truy%E1%BB%81n-th%C3%B4ng-s%E1%BB%9F-h%E1%BB%AFu-v%C3%A0-tr%E1%BA%A3-ph%C3%AD h_01HDPDE0H3TBDSXCNW5Q3E1Q7P=paid-media paid-media-data-availability-by-att-status=t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u-truy%E1%BB%81n-th%C3%B4ng-tr%E1%BA%A3-ph%C3%AD-theo-tr%E1%BA%A1ng-th%C3%A1i-att h_01HDPDE0H3SACYAV19WQD9TCQ3=t%C3%ADnh-kh%E1%BA%A3-d%E1%BB%A5ng-c%E1%BB%A7a-d%E1%BB%AF-li%E1%BB%87u-truy%E1%BB%81n-th%C3%B4ng-tr%E1%BA%A3-ph%C3%AD-theo-tr%E1%BA%A1ng-th%C3%A1i-att h_01HDPDE0H4M4XPE1C54K284BGW=owned-media controlling-aap=ki%E1%BB%83m-so%C3%A1t-aap h_01HDPDE0H4VQC2DWAV68Q9VDVQ=ki%E1%BB%83m-so%C3%A1t-aap h_01HDPDE0H4BHG114REGTWCDBP9=aap-central-switch aap-enabled=aap-%C4%91%C6%B0%E1%BB%A3c-b%E1%BA%ADt h_01HDPDE0H4SC810EBK7ZGQ02K0=aap-%C4%91%C6%B0%E1%BB%A3c-b%E1%BA%ADt h_01HDPDE0H4FRDXWRCYAWTPZZWE=partner-advanced-privacy-switch aap-implications-for-your-partners=%C3%BD-ngh%C4%A9a-c%E1%BB%A7a-aap-%C4%91%E1%BB%91i-v%E1%BB%9Bi-c%C3%A1c-%C4%91%E1%BB%91i-t%C3%A1c-c%E1%BB%A7a-b%E1%BA%A1n h_01HDPDE0H4GJG05FEJP1YM06AP=%C3%BD-ngh%C4%A9a-c%E1%BB%A7a-aap-%C4%91%E1%BB%91i-v%E1%BB%9Bi-c%C3%A1c-%C4%91%E1%BB%91i-t%C3%A1c-c%E1%BB%A7a-b%E1%BA%A1n h_01HDPDE0H4PDJ4TC02TED0DB8P=ad-networks postbacks-to-ad-network-partners=%C4%91%C4%83ng-l%E1%BA%A1i-%C4%91%E1%BA%BFn-c%C3%A1c-%C4%91%E1%BB%91i-t%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o h_01HDPDE0H47ENYTWRVFPX0VTZC=%C4%91%C4%83ng-l%E1%BA%A1i-%C4%91%E1%BA%BFn-c%C3%A1c-%C4%91%E1%BB%91i-t%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o postbacks-for-attributed-ad-networks=%C4%91%C4%83ng-l%E1%BA%A1i-%C4%91%E1%BA%BFn-c%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A2n-b%E1%BB%95 h_01HDPDE0H4B01YG577QZCG7TA7=%C4%91%C4%83ng-l%E1%BA%A1i-%C4%91%E1%BA%BFn-c%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A2n-b%E1%BB%95 postbacks-for-unattributed-partners=%C4%91%C4%83ng-l%E1%BA%A1i-cho-c%C3%A1c-%C4%91%E1%BB%91i-t%C3%A1c-ch%C6%B0a-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A2n-b%E1%BB%95 h_01HDPDE0H63ZMV255SN7EKDRMV=%C4%91%C4%83ng-l%E1%BA%A1i-cho-c%C3%A1c-%C4%91%E1%BB%91i-t%C3%A1c-ch%C6%B0a-%C4%91%C6%B0%E1%BB%A3c-ph%C3%A2n-b%E1%BB%95 h_01HDPDE0H67T1XFTEB2N0NN6YN=analytics-partners h_01HDPDE0H6AM91W49W2G2Z94DM=agencies h_01HDPDMX05ZZCAMW4TTWF4M4YN=xem-th%C3%AAm" />
