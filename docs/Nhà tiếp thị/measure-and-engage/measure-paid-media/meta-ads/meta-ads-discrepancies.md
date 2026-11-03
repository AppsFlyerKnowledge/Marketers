---
title: Những khác biệt của quảng cáo Meta
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-09T10:10:54Z'
  edited_at: '2023-12-31T08:41:45Z'
  id: 4410481130641
  locale: vi
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/vi/articles/4410481130641
---
> **Khái quát:** Tìm hiểu điểm khác biệt trong các mô hình phân bổ giữa Meta ads và AppsFlyer.

## Không nhất quán giữa Meta ads và AppsFlyer

Tương tự như bất kỳ 2 đơn vị tham gia chính nào trong hệ sinh thái thu hút người dùng di động, AppsFlyer và Meta ads đều khác nhau trong mô hình phân bổ của họ. Điều này có thể dẫn đến sự không nhất quán giữa các bảng điều khiển của Meta ads và AppsFlyer.

Mặc dù chúng tôi hợp tác chặt chẽ với Meta ads để giảm thiểu tình trạng không nhất quán này, nhưng các nhà quảng cáo nên nắm được các nguyên nhân dưới đây.

### Phát hiện sự không nhất quán giữa AppsFlyer và Meta ads

So sánh các sự kiện được liệt kê trong **Event Manager** của Meta ads với các sự kiện trong báo cáo của AppsFlyer. Nếu số lượng sự kiện khác nhau nhiều thì có thể xuất hiện tình trạng không nhất quán.

## Sự khác biệt trong mô hình phân bổ

<table><thead><tr><th>Nguyên nhân</th><th>Quảng cáo Meta</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><p><strong>Cửa sổ xem lại phân bổ lượt clicks</strong></p></td><td><p>7 ngày (Lưu ý rằng <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">có một số trường hợp cụ thể mà giá trị mặc định sẽ khác</a>).</p></td><td><p>1-30 ngày. Đảm bảo đặt thành 7 ngày đối với Meta ads.</p></td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><p><strong>Cửa sổ xem lại phân bổ lượt xem qua</strong></p></td><td><p>1 ngày (Lưu ý rằng <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">có một số trường hợp cụ thể mà giá trị mặc định sẽ khác</a>).</p></td><td><p>Mặc định 1 ngày, nhưng  có thể được định cấu hình là 1-48 giờ (giữ giá trị mặc định này)</p></td></tr><tr><td><span id="multichannel-sourceattribution"></span><p><strong>Phân bổ<br/>Nguồn đa kênh</strong></p></td><td><p>Meta ads tự phân bổ lượt cài đặt bất kể các nguồn truyền thông khác.</p></td><td><p>AppsFlyer sử dụng phân bổ lượt nhấp chuột cuối cùng (thông tin thêm về phân bổ AppsFlyer có sẵn <a href="./appsflyer-attribution-model" title="Mô hình Phân bổ của AppsFlyer" target="_blank">tại đây</a>)</p></td></tr><tr><td><span id="crossdevice-attribution"></span><p><strong>Phân bổ trên nhiều thiết bị</strong></p></td><td><p>Meta ads phân bổ người dùng đã nhấp và cài đặt trên các thiết bị khác nhau, ví dụ như iOS/Android/máy tính để bàn.</p></td><td><p>AppsFlyer phân bổ các thiết bị đơn, thực hiện cả thu hút lẫn cài đặt</p></td></tr><tr><td><span id="different-time-zones"></span><p><strong>Múi giờ Khác nhau</strong></p></td><td><p>Múi giờ báo cáo mặc định trong Meta ads là PST. Đảm bảo <a href="https://www.facebook.com/business/help/754049591334898" target="_blank">đổi múi giờ trong Meta ads Manager</a> để khớp với múi giờ trên ứng dụng được xác định trong cài đặt của ứng dụng tại AppsFlyer.</p></td><td><p>Múi giờ mặc định trên ứng dụng của AppsFlyer là UTC+0. Bạn có thể đổi múi giờ được đặt cho ứng dụng tại <a href="./app-settings#localization-time-zone" target="_blank">trang cài đặt của ứng dụng</a> để khớp với múi giờ được xác định trong Meta ads Manager.</p></td></tr><tr><td><span id="google-install-referrer"></span><p><strong>Liên kết giới thiệu cài đặt của Google</strong></p></td><td colspan="2"><p>Khi một lượt cài đặt không có ID nhà quảng cáo được phân bổ cho Meta ads bằng cách sử dụng liên kết giới thiệu cài đặt của Google Play, AppsFlyer sẽ không báo cáo lại lượt cài đặt đó cho Meta ads. Điều này sẽ dẫn đến tình trạng không nhất quán vì lượt cài đặt sẽ hiển thị trong AppsFlyer chứ không phải trong Meta ads.  </p></td></tr><tr><td><span id="AEM-for-data-sharing"></span><p><strong>AEM cho chia sẻ dữ liệu</strong></p></td><td colspan="2"><p><span>Đối với <a href="./meta-ads-aggregate-event-measurement-aem-for-ios#aem-data-sharing" target="_blank">chia sẻ dữ liệu AEM</a>, quảng cáo Meta nhận tất cả các sự kiện chuyển đổi. Phân bổ bổ sung này không hiển thị trong AppsFlyer. Do đó, sẽ có hiện tượng tăng mức độ sai lệch dữ liệu giữa cả hai nền tảng về lượt cài đặt (trong hầu hết các trường hợp) và sự kiện trong ứng dụng, bao gồm cả phiên</span>.</p></td></tr></tbody></table>

## Phân bổ lượt Xem qua và Clicks qua

AppsFlyer hỗ trợ phân bổ lượt nhấp qua và lượt xem hết. Để giảm thiểu những điểm khác biệt giữa Meta ads và AppsFlyer, hãy đảm bảo rằng khung thời gian Xem lại lượt nhấp qua và lượt xem hết đều nhất quán với khung thời gian mặc định do Meta ads xác định.

Khung thời gian xem lại lượt nhấp qua mặc định của Meta ads được xác định là 7 ngày. Mặc dù [có một số trường hợp cụ thể mà giá trị mặc định sẽ khác](https://www.facebook.com/business/help/395050428485124?id=428636648170202), bạn nên đặt khung thời gian xem lại lượt nhấp qua trong AppsFlyer thành 7 ngày để bao gồm tất cả tùy chọn mặc định của Meta ads.

Để so sánh khung thời gian phân bổ lượt nhấp qua và lượt xem hết trên Meta ads với các khung thời gian trên AppsFlyer, hãy truy cập Meta ads. Bạn nên cấu hình khung thời gian phân bổ trên AppsFlyer theo các giá trị của Meta ads như được hiển thị trong ảnh chụp màn hình sau:

![Facebook_Discrepancies.png](https://files.readme.io/e8caa7986ffa66c5bfdbef7457de5630899043256ca484f0cfdfdda8ac481c7e-4411036047505.png)

> 📄 **Ví dụ**
>
> Giả sử rằng khung thời gian xem lại lượt nhấp của Meta ads được cấu hình trên AppsFlyer là 1 ngày đối với ứng dụng com.greatapp, trong khi trên Meta ads, khung thời gian này mặc định là 7 ngày. Người dùng nhấp vào quảng cáo của Greatapp trên Facebook, nhưng khởi chạy ứng dụng lần đầu tiên sau 2-7 ngày sẽ được phân bổ là người dùng tự nhiên trên AppsFlyer, trong khi Meta ads tự báo cáo những người dùng này.

## Sự khác biệt về phương tiện truyền thông bị hạn chế

Cho đến ngày 28/10/2021, dữ liệu phân bổ của người dùng bắt nguồn từ phân bổ lượt xem hết (VTA) bị <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">hạn chế và không khả dụng cho các nhà quảng cáo</Anchor>.  
Bắt đầu từ ngày 29/10/2021, các hạn chế được áp dụng cho người dùng nhận được phân bổ lượt xem hết và lượt nhấp qua. Điều này không ảnh hưởng đến báo cáo hợp nhất.

Do Meta ads không gửi dữ liệu ở mức người dùng nên AppsFlyer có thể không phân bổ lượt hiển thị và nhấp chuột hỗ trợ lượt chuyển đổi cho Meta ads.

> 📄 **Ví dụ**
>
> * Người dùng nhìn thấy hoặc nhấp vào quảng cáo trên Facebook cho AwesomeApp. Sau đó, họ nhìn thấy và nhấp vào quảng cáo GreatAdNetwork cho AwesomeApp và cài đặt ứng dụng.
> * Meta ads được tính lượt chuyển đổi này vì thời điểm xảy ra vẫn trong khung thời gian xem lại.
> * AppsFlyer phân bổ lượt chuyển đổi cho GreatAdNetwork vì họ có tương tác cuối cùng trước khi cài đặt.
> * AppsFlyer sẽ không coi Meta ads là mạng hỗ trợ lượt chuyển đổi vì dữ liệu thô của Meta ads bị hạn chế.

Tuy nhiên, đối với phân bổ lượt nhấp qua, nếu mục quảng cáo chuyển hướng người dùng đến Google Play Store, các trường phân bổ khả dụng cho các nhà quảng cáo trong Google Install Referrer. Các trường được cung cấp qua người giới thiệu sẽ nhập các báo cáo dữ liệu thô AppsFlyer được cung cấp cho bạn và cho phép AppsFlyer phân bổ người dùng không có ID quảng cáo (Bật LAT).

## Những sự khác biệt của sự kiện trong ứng dụng

Những điểm khác biệt giữa các nền tảng cũng có thể xuất hiện cùng với các sự kiện sau khi cài đặt (ví dụ: mua hàng trong ứng dụng), được hiển thị trên Meta ads và AppsFlyer. Bảng sau mô tả các lý do phổ biến nhất đối với những điểm khác biệt này và đưa ra lời khuyên để giảm thiểu những điểm khác biệt đó:

| Nguyên nhân | Mô tả | Mẹo AppsFlyer |
| --- | --- | --- |
| <span id="selfattribution"></span>**Tự phân bổ** | Meta ads luôn phân bổ sự kiện cho các chiến dịch của mình mà đã thúc đẩy sự kiện đó, trong khi AppsFlyer phân bổ các sự kiện này cho nguồn thu hút. | Các lượt cài đặt và sự kiện mà Meta ads tự phân bổ không chính xác được chỉ định làm <Anchor target="_blank" href="/marketers/vi/docs/measure-assisted-installs#báo-cáo-lượt-cài-đặt-được-hỗ-trợ">lượt hỗ trợ trong AppsFlyer</Anchor>.  <br />Kết hợp dữ liệu thô về lượt chuyển đổi được phân bổ của Meta ads với dữ liệu thô mà Meta ads là người đóng góp. |
| <span id="different-lifetime-definition"></span>**Định nghĩa "vòng đời" khác nhau** | Vòng đời của người dùng trên Meta ads được xác định là tối đa 7 ngày, nghĩa là Meta ads không hiển thị các sự kiện đã xảy ra quá 7 ngày sau khi nhấp vào quảng cáo.  <br />Trong AppsFlyer, vòng đời của người dùng trên Meta ads được xác định là tối đa 180 ngày. | Khi đánh giá giá trị của người dùng từ các chiến dịch của Meta ads diễn ra sau 7 ngày, hãy sử dụng dữ liệu của AppsFlyer để có bức tranh toàn cảnh hơn. |
| <span id="unmapped-events"></span>**Các sự kiện không được nối** | AppsFlyer nhận các sự kiện mà SDK tạo ra, nhưng không được ánh xạ tới Meta ads, do đó không được gửi đi. | Đảm bảo <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-in-app-event-mapping">ánh xạ với Meta ads</Anchor> tất cả sự kiện trong ứng dụng biểu thị chất lượng của người dùng. |
| <span id="unsent-revenue"></span>**Doanh thu chưa gửi** | AppsFlyer nhận doanh thu từ các sự kiện mà SDK tạo ra, nhưng các sự kiện này không được gửi tới Meta ads. | Đảm bảo luôn đánh dấu vào các ô **Send Revenue** (Gửi Doanh thu) của sự kiện trong ứng dụng, ví dụ: sự kiện mua hàng trong ảnh chụp bên dưới. |
| <span id="missing-event-values-on-facebook"></span>**Thiếu các giá trị sự kiện trên Meta ads** | AppsFlyer gửi các thông số và giá trị cho Meta ads như nằm trong quá trình ánh xạ sự kiện, nếu thông số và giá trị này có cấu trúc chính xác. | Tạo các sự kiện trong ứng dụng SDK của bạn theo <Anchor target="_blank" href="/marketers/vi/docs/in-app-events-event-structure">cấu trúc được đề xuất của AppsFlyer</Anchor> để ánh xạ đầy đủ các giá trị sự kiện với Meta ads. |

## Cài đặt từ các chiến dịch Thu hút lại trong Bảng điều khiển UA của tôi?

Chiến dịch thu hút lại có thể khiến người dùng mở ứng dụng đã được cài đặt (**thu hút lại**). Cách khác, khi AppsFlyer nhận ra một lượt cài đặt ứng dụng trước đó đã tồn tại trên cùng một thiết bị, AppsFlyer có thể tham khảo chuyển đổi đó dưới dạng **phân bổ lại**.

Trong một chiến dịch thu hút lại, nếu Meta ads nhắm mục tiêu **người dùng mới** hoặc người dùng đã cài đặt ứng dụng lần đầu tiên **vượt** **quá <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window">khung thời gian phân bổ lại</Anchor>** đã đặt sau lần cài đặt ban đầu, những người dùng này được ghi nhận là **các lượt cài đặt thu hút người dùng mới trên AppsFlyer**, nằm trong chiến dịch thu hút lại trên Meta ads.

Mặt khác, các lượt cài đặt diễn ra **trong khung thời gian phân bổ lại đã đặt** sau lần cài đặt ban đầu được coi là lượt phân bổ lại và hiển thị trên trang nhắm mục tiêu lại của AppsFlyer, trong khi các lượt cài đặt có thể xuất hiện dưới dạng lượt cài đặt mới của Meta ads.

> 📘 **Lưu ý**
>
> Mặc dù Meta ads hiển thị tất cả lượt cài đặt của một chiến dịch nhắm mục tiêu lại ở cùng một nơi, trên bảng điều khiển của AppsFlyer, các lượt cài đặt được chia ra giữa trang Tổng quan (lượt cài đặt mới) và trang Nhắm mục tiêu lại (phân bổ lại và thu hút lại).

## Phân bổ trên nhiều thiết bị

Các báo cáo của Meta ads về phân bổ trên nhiều thiết bị. Điều này đôi khi có thể gây ra sự cố khiến một chiến dịch cho một nền tảng (iOS/Android) hiển thị lượt cài đặt trên một nền tảng khác.

> 📄 **Ví dụ**
>
> Linda nhấp vào quảng cáo trên điện thoại di động của GreatApp trên Facebook thông qua điện thoại Android của cô ấy. Meta ads ghi nhận lượt nhấp do Linda thực hiện trong chiến dịch được nhắm mục tiêu ban đầu của Android "Android Females". Linda quyết định cài đặt GreatApp trên iPad của mình. Khi khởi chạy lần đầu tiên, AppsFlyer truy vấn Meta ads về nguồn gốc của lượt cài đặt trên iOS này và Meta ads trả lời là chiến dịch "Android Females".

## Quy tắc xác thực và Protect360

Nếu bạn sử dụng <Anchor target="_blank" href="/marketers/vi/docs/implement-validation-rules-to-prevent-fraud">Quy tắc Xác thực của AppsFlyer</Anchor>, kết quả có thể khác nhau giữa AppsFlyer và Meta ads khi có lượt cài đặt từ Meta ads bị từ chối. Trong những trường hợp này, Meta ads sẽ tự báo cáo lượt cài đặt cho mình, trong khi AppsFlyer từ chối những lượt cài đặt này.

Tương tự, nếu bạn sử dụng giải pháp chống gian lận của AppsFlyer, Protect360, có thể có các lượt cài đặt vì Meta ads sẽ tự báo cáo trong khi AppsFlyer từ chối.

> 📄 **Ví dụ**
>
> Jeff, người quản lý UA của GreatApp, tạo ra chiến dịch SPNA để chỉ nhắm mục tiêu đến người nói tiếng Tây Ban Nha ở Bắc Mỹ. Để xác minh điều này, Jeff xác định một quy tắc xác thực chỉ chấp nhận người dùng từ Canada và Hoa Kỳ.
> Khi người dùng Meta ads đến từ Tây Ban Nha nhấp vào và cài đặt ứng dụng, Meta ads sẽ tự báo cáo lượt cài đặt, trong khi AppsFlyer từ chối lượt cài đặt đó vì không vượt qua quy tắc xác thực.

## Sự không nhất quán liên quan đến SDK

Có thể có <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-faq#who-needs-facebooks-sdk">một số trường hợp các nhà quảng cáo triển khai SDK của cả AppsFlyer và Facebook</Anchor>. Điều này có thể làm xuất hiện tình trạng không nhất quán giữa các sự kiện trong ứng dụng. Meta ads không loại bỏ các sự kiện trong ứng dụng trùng lặp được báo cáo từ cả hai SDK. Điều này có nghĩa là Meta ads có thể báo cáo sai doanh thu và các sự kiện khác.

* Sử dụng một trong hai phương thức sau để tránh báo cáo sự kiện trong ứng dụng bị trùng lặp trong Meta ads:
  * Không cấu hình các sự kiện trong SDK của Facebook.
  * Tắt tùy chọn <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-in-app-event-mapping">Meta ads in-app events mapping</Anchor> từ AppsFlyer.

<div data-zendesk-anchors="facebook-ads-discrepancies-with-appsflyer=kh%C3%B4ng-nh%E1%BA%A5t-qu%C3%A1n-gi%E1%BB%AFa-meta-ads-v%C3%A0-appsflyer 01H890CZSXPMK0BDMC4202HNYM=kh%C3%B4ng-nh%E1%BA%A5t-qu%C3%A1n-gi%E1%BB%AFa-meta-ads-v%C3%A0-appsflyer detect-a-discrepancy-between-appsflyer-and-facebook=ph%C3%A1t-hi%E1%BB%87n-s%E1%BB%B1-kh%C3%B4ng-nh%E1%BA%A5t-qu%C3%A1n-gi%E1%BB%AFa-appsflyer-v%C3%A0-meta-ads 01H890CZSXGHVBH21SQA0671JQ=ph%C3%A1t-hi%E1%BB%87n-s%E1%BB%B1-kh%C3%B4ng-nh%E1%BA%A5t-qu%C3%A1n-gi%E1%BB%AFa-appsflyer-v%C3%A0-meta-ads differences-in-attribution-models=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-trong-m%C3%B4-h%C3%ACnh-ph%C3%A2n-b%E1%BB%95 01H890CZSX8M6VGGREYX4W2X37=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-trong-m%C3%B4-h%C3%ACnh-ph%C3%A2n-b%E1%BB%95 clickthrough-and-viewthrough-attribution=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua-v%C3%A0-clicks-qua 01H890CZSX40JDGY8P8AQ4CYGS=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-xem-qua-v%C3%A0-clicks-qua 01H890CZSXRD7PCZBK52GW7QE9=v%C3%AD-d%E1%BB%A5 restricted-media-discrepancies=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-v%E1%BB%81-ph%C6%B0%C6%A1ng-ti%E1%BB%87n-truy%E1%BB%81n-th%C3%B4ng-b%E1%BB%8B-h%E1%BA%A1n-ch%E1%BA%BF 01H890CZSX5WFX5Q0RNSG01GFH=s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-v%E1%BB%81-ph%C6%B0%C6%A1ng-ti%E1%BB%87n-truy%E1%BB%81n-th%C3%B4ng-b%E1%BB%8B-h%E1%BA%A1n-ch%E1%BA%BF 01H890CZSX567CQ3ZWZS5F05XW=v%C3%AD-d%E1%BB%A5-1 inapp-events-differences=nh%E1%BB%AFng-s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-c%E1%BB%A7a-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H890CZSXKC5JKK9051MC0VY6=nh%E1%BB%AFng-s%E1%BB%B1-kh%C3%A1c-bi%E1%BB%87t-c%E1%BB%A7a-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng installs-from-reengagement-campaigns-in-my-ua-dashboard=c%C3%A0i-%C4%91%E1%BA%B7t-t%E1%BB%AB-c%C3%A1c-chi%E1%BA%BFn-d%E1%BB%8Bch-thu-h%C3%BAt-l%E1%BA%A1i-trong-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-ua-c%E1%BB%A7a-t%C3%B4i 01H890CZSYE21K7PBQK4PNMGJR=c%C3%A0i-%C4%91%E1%BA%B7t-t%E1%BB%AB-c%C3%A1c-chi%E1%BA%BFn-d%E1%BB%8Bch-thu-h%C3%BAt-l%E1%BA%A1i-trong-b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-ua-c%E1%BB%A7a-t%C3%B4i 01H890CZSY7TRCA4NVKSVPY7DB=l%C6%B0u-%C3%BD crossdevice-attribution::77a37a1f=ph%C3%A2n-b%E1%BB%95-tr%C3%AAn-nhi%E1%BB%81u-thi%E1%BA%BFt-b%E1%BB%8B 01H890CZSYS8QKEAF6799SBS8J=ph%C3%A2n-b%E1%BB%95-tr%C3%AAn-nhi%E1%BB%81u-thi%E1%BA%BFt-b%E1%BB%8B 01H890CZSY2Z3S6E9R5MYC1CHX=v%C3%AD-d%E1%BB%A5-2 validation-rules-and-protect360=quy-t%E1%BA%AFc-x%C3%A1c-th%E1%BB%B1c-v%C3%A0-protect360 01H890CZSYDHZE4V0ZWTT8V0EJ=quy-t%E1%BA%AFc-x%C3%A1c-th%E1%BB%B1c-v%C3%A0-protect360 01H890CZSYCTQZCAYAZP9TCBBF=v%C3%AD-d%E1%BB%A5-3 sdk-related-discrepancies=s%E1%BB%B1-kh%C3%B4ng-nh%E1%BA%A5t-qu%C3%A1n-li%C3%AAn-quan-%C4%91%E1%BA%BFn-sdk 01H890CZSYVFPQP0SKNPWMPB1R=s%E1%BB%B1-kh%C3%B4ng-nh%E1%BA%A5t-qu%C3%A1n-li%C3%AAn-quan-%C4%91%E1%BA%BFn-sdk" />
