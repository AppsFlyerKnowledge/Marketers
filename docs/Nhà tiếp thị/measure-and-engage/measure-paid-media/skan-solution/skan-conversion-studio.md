---
title: SKAN Conversion Studio
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
  created_at: '2021-07-08T09:26:58Z'
  edited_at: '2023-10-26T14:42:46Z'
  id: 4403727223185
  locale: vi
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/vi/articles/4403727223185
---
> **Khái quát**: Sử dụng SKAN Conversion Studio để thiết lập lượt tương tác người dùng trong ứng dụng cần đo lường và thời gian thực hiện. Đo lường doanh thu, lượt chuyển đổi, lượt tương tác và tỷ lệ giữ chân người dùng trong khoảng thời gian sau cài đặt giới hạn. Bằng cách thêm đo lường Nguồn dữ liệu tin cậy duy nhất, chúng tôi có thể cho bạn biết liệu người dùng có được phân bổ cho cả AppsFlyer và SKAN hay không.

<Embed title="SKAN 4 Conversion Studio (bao gồm cả khóa khung thời gian)" typeOfEmbed="iframe" url="https://player.vimeo.com/video/810457121?h=a3acc3ee41&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" providerUrl="https://player.vimeo.com" />

<div id="skan-conversion-studio-basics" />

## Các khái niệm cơ bản về SKAN Conversion Studio

Trong luồng phân bổ SKAdNetwork (SKAN), thiết bị iOS gửi các postback SKAN chứa giá trị chuyển đổi (CV) gần đây nhất sau mỗi cửa sổ đo lường.

Từ SKAN 3 trở xuống, sẽ có 1 postback sau khi Cửa sổ hoạt động ban đầu kết thúc. Cửa sổ hoạt động có thể từ 12 giờ đến 63 ngày. CV này bị giới hạn đến 6 bit, dẫn đến có 64 giá trị hợp lý (0 - 63).

Đối với SKAN 4, có 3 lượt đăng lại xuất hiện sau khi mỗi trong số 3 khung thời gian kết thúc, tương ứng sau ngày 2, 7 và 35. Đối với:

* Cửa sổ 1, CV mịn giới hạn đến 6 bit, dẫn đến 64 giá trị hợp lý (0 - 63).
* Cửa sổ 1 - 3, CV thô giới hạn đến CV thấp, trung bình hoặc cao. (Cửa sổ 2 và 3 không có CV mịn).

Các giới hạn CV này có nghĩa là bạn có thể cần phải đưa ra một vài lựa chọn khó khăn về cách dùng 64 giá trị hợp lý cho CV mịn và 3 giá trị hợp lý cho CV thô.

Conversion Studio mang lại cho bạn sự linh hoạt tối đa để tận dụng đến từng giá trị và bit. Bạn xác định chính xác dữ liệu đo lường nào cần được mã hóa trong CV—bao gồm loại hoạt động và thời gian đo lường trong thời gian sau cài đặt. Có một vài chế độ đo lường bạn có thể sử dụng để cấu hình cài đặt CV của mình.

| Loại | Chế độ đo lường | Mô tả | Khung thời gian hoạt động |
| --- | --- | --- | --- |
| Linh hoạt | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Phương pháp thực hành tốt nhất] | Thiết lập một tổ hợp các chỉ số đo lường về doanh thu, loại chuyển đổi (sự kiện trong ứng dụng) và lượt tương tác trong 3 cửa sổ đo lường có thể cấu hình.<br /><br />3 cửa sổ đo lường 3 khoảng thời gian sau cài đặt khác nhau và không chồng chéo. Tức là cửa sổ 2 đo lường các ngày 3 - 7 sau cài đặt, không phải các ngày 0 - 7. | <ul><li>Khung thời gian 1: 1-2 ngày</li><li>Cửa sổ 2: 3 - 7 ngày</li><li>Cửa sổ 3: 8 - 35 ngày</li></ul> |
| Linh hoạt | Tùy chính | Đặt kết hợp các chỉ số đo lường doanh thu, lượt chuyển đổi (sự kiện trong ứng dụng) và mức độ thu hút trong khung thời gian hoạt động có thể cấu hình. | 12-1512h (mặc định lên đến 72 giờ, nhưng có thể kéo dài) |
| Cố định | Doanh thu<br /><br />[Mặc định]<br /><br />[Cũ] | Đo lường doanh thu bằng cách sử dụng một trong các khoảng sau:<ul><li>$1-$630 gia số $10</li><li>$1-$63 gia số $1</li><li>$0,01-$0,63 gia số $0,01</li></ul> | 24 giờ |
| Cố định | Chuyển đổi<br /><br />[Cũ] | Chọn 1-6 sự kiện trong ứng dụng. | 24 giờ |
| Cố định | Tương tác<br /><br />[Cũ] | Số lần người dùng thực hiện một sự kiện | 24 giờ |
| Linh hoạt | <Anchor target="_blank" href="/marketers/vi/docs/skan-cv-decode-map-your-cv-to-events">Giải mã</Anchor> | <ul><li>Tạo CV của riêng bạn để ánh xạ sự kiện và tự đặt CV trong ứng dụng. Sử dụng tùy chọn này nếu bạn không thể tích hợp SDK AppsFlyer vào ứng dụng của mình. Để sử dụng Giải mã, hãy đi đến **SKAN Conversion Studio,** nhấp vào tùy chọn (⋮), chọn **Tải lên tệp tin ánh xạ giải mã tùy chỉnh**.</li></ul> | 12-1512 giờ (63 ngày) |

**Mẹo!** Thử nghiệm với Conversion Studio. Trong AppsFlyer, đi tới > **Configuration** (Cấu hình) > **SKAN Conversion Studio**.

<div id="measurement-principles-and-definitions" />

<Accordion title="Các nguyên tắc đo lường và định nghĩa">

**Các định nghĩa**

* **Cửa sổ đo lường SKAN**: Phù hợp cho SKAN 4+. Có 3 khoảng thời gian (cửa sổ) trong đó hoạt động sau cài đặt của người dùng được đo lường:
  * Khung thời gian 1: 1-2 ngày
  * Cửa sổ 2: 3 - 7 ngày
  * Cửa sổ 3: 8 - 35 ngày
  * 3 cửa sổ đo lường 3 khoảng thời gian sau cài đặt khác nhau và không chồng chéo. Tức là cửa sổ 2 đo lường các ngày 3 - 7 sau cài đặt, không phải các ngày 0 - 7.
* **Cửa sổ hoạt động:** Phù hợp cho SKAN 3 trở xuống. Đặt thời lượng, mặc định là 24 giờ, bắt đầu khi mở ứng dụng đầu tiên. Nếu bạn sử dụng SKAN 4+, nhưng thiết bị người dùng hoặc mạng quảng cáo chưa hỗ trợ SKAN 4, Cửa sổ hoạt động là 48 giờ.
* **Giá trị chuyển đổi (CV)**: Thước đo chất lượng người dùng được báo cáo trong postback do thiết bị iOS gửi ở cuối cửa sổ SKAN 4 hoặc, đối với SKAN 3 trở xuống, ở cuối Cửa sổ hoạt động. SDK AppsFlyer thiết đặt các CV cho bạn. Tuy nhiên, nếu bạn muốn đặt CV, hãy sử dụng chế độ <Anchor target="_blank" href="/marketers/vi/docs/skan-cv-decode-map-your-cv-to-events">Giải mã</Anchor> để tải lên tệp tin ánh xạ CV của bạn.
  * Đối với SKAN 4+, có cả giá trị chuyển đổi mịn và thô.
* **Dung lượng giá trị chuyển đổi:** Số lượng CV cần thiết để ánh xạ cài đặt của bạn. Bạn chọn càng nhiều thành phần và phần tử đo lường, thì cần càng nhiều dung lượng giá trị chuyển đổi. Mỗi phạm vi hoặc phần tử cài đặt được chọn đều sử dụng dung lượng giá trị chuyển đổi. (Và mỗi đơn vị cài đặt bổ sung có trong một thành phần duy nhất sẽ sử dụng nó theo cấp số nhân!) [Ví dụ về việc sử dụng CV tối đa.](/docs/skan-conversion-studio#maximized-custom-cv-examples)
* **Nguồn dữ liệu tin cậy duy nhất (SSOT):** <Anchor target="_blank" href="/marketers/vi/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Cơ chế gắn cờ</Anchor> nếu người dùng được phân bổ bởi SKAN và một phương thức khớp phân bổ khác. Cờ được sử dụng để xoá dữ liệu lượt cài đặt trùng lặp trong dữ liệu thô SKAN và tính toán các phép đo hiệu suất thực.
* **Thành phần đo lường**:  
  * **Doanh thu:** Đo lường doanh thu tạo ra
  * **Sự kiện trong ứng dụng**: Đo lường chuyển đổi (số lượng người dùng duy nhất thực hiện một sự kiện),  
     lượt tương tác (số lần một sự kiện được thực hiện) hoặc cả hai.
  * **Kênh**: Đo lường số lần xuất hiện của các sự kiện trong ứng dụng dựa trên danh sách các sự kiện tuần tự trong kênh. Người dùng thực hiện bất kỳ sự kiện nào trong kênh sẽ được coi là đã thực hiện tất cả các sự kiện ở trước sự kiện đó.
  * **Ưu tiên**: Thành phần chứa doanh thu, sự kiện trong ứng dụng hoặc cả hai.
  * **Dự đoán:** Sử dụng các thuật toán máy học nâng cao để cung cấp các dự đoán chính xác dựa trên LTV về tỷ lệ thành công của chiến dịch. KPI cấp độ người dùng được dự đoán (bao gồm doanh thu và tỷ lệ giữ chân người dùng được dự đoán) được mã hóa và truyền tới SKAN dưới dạng một giá trị chuyển đổi duy nhất; sau đó, SKAN sẽ báo cáo dưới dạng postback, cùng với ID chiến dịch và nguồn phân bổ.

**Nguyên tắc**

* **![Admin.png](https://files.readme.io/74a71649d541921d2b61425323cc4cf5b669cd4d5665294d0813a3e9230bd11d-4405725144977.png) Admin only:** Chỉ quản trị viên mới có thể lưu cài đặt Conversion Studio. Người dùng tài khoản có thể xem các cài đặt.
* Tại bất kỳ thời điểm nào, chỉ có một chế độ đang hoạt động.
* Đối với một chế độ nhất định, AppsFlyer ánh xạ các kết hợp được xác định bởi các tùy chọn cài đặt của bạn vào CV. Bạn có thể [xem và tải xuống bảng ánh xạ](/docs/skan-conversion-studio#view-cv-mapping).
* Trong ứng dụng, AppsFlyer đặt CV sau mỗi hành động có thể đo lường được của người dùng bằng cách sử dụng chế độ đo lường hoạt động khi người dùng khởi chạy ứng dụng lần đầu.
* iOS xem xét <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">cấp mạng ẩn danh của Apple</Anchor> trước khi điền CV vào postback.
* Các hành động của người dùng xảy ra sau khi kết thúc một cửa sổ sẽ bị bỏ qua.
* Bảng điều khiển và báo cáo SKAN:
  * Bố cục và số liệu của bảng điều khiển SKAN phụ thuộc vào chế độ và cấu hình.
  * Bố cục cập nhật hàng ngày dựa trên chế độ hoạt động vào lúc nửa đêm, theo giờ UTC. Theo dự kiến, bố cục cập nhật sẽ có trước 05:00 UTC.
  * Trong SKAN 4, chế độ Tùy chỉnh và Giải mã, dữ liệu tự nhiên cho các sự kiện trong ứng dụng và doanh thu tổng không có sẵn.

<div id="s2s-principles" />

#### **Nguyên tắc S2S**

API [máy chủ đến máy chủ (S2S)](/docs/skan-conversion-studio#report-events-by-servertoserver-api) có thể báo cáo những hành động có thể đo lường. Hãy xem xét các mục sau cho mỗi chế độ:

* SKAN 4 và chế độ Tùy chỉnh: S2S luôn bật.
* Giải mã: S2S không phù hợp với S2S và không có sẵn. AppsFlyer không đặt CV ở chế độ này.
* Các chế độ doanh thu, lượt chuyển đổi và lượt tương tác: Bạn phải bật [S2S event recording](/docs/skan-conversion-studio#report-events-by-servertoserver-api) trước khi gửi sự kiện.

</Accordion>

<div id="setting-up-conversion-values-in-skan-conversion-studio" />

## Cài đặt giá trị chuyển đổi trong SKAN Conversion Studio

Có một số chế độ có sẵn trong SKAN Conversion Studio để đặt giá trị chuyển đổi:

* SKAN 4: Sử dụng các thành phần đo lường khác nhau như doanh thu, sự kiện trong ứng dụng, mức độ ưu tiên và Nguồn dữ liệu tin cậy duy nhất để xác định đối tượng cần đo lường trong mỗi ba cửa sổ đo lường.
* Chế độ Tùy chỉnh: Sử dụng các thành phần đo lường khác nhau như doanh thu, sự kiện trong ứng dụng, mức độ ưu tiên và Nguồn dữ liệu tin cậy duy nhất để xác định đối tượng cần đo lường trong Cửa sổ hoạt động.
* Chế độ Cố định: Đo lường giá trị người dùng bằng cách sử dụng một trong các thành phần đo lường sau:
  * Doanh thu
  * Chuyển đổi
  * Tương tác

Tìm hiểu thêm về các chế độ đo lường khác trong các phần tiếp theo.

<div id="important" />

> 🚧 **Quan trọng!**
>
> Việc đặt giá trị chuyển đổi trong SKAN Converter Studio phải được thực hiện bởi quản trị viên hoặc người dùng tài khoản có quyền **Quản lý** trong **SKAN Converter Studio**.
>
> **Để xem hoặc thay đổi các quyền người dùng:**
>
> 1. Trong AppsFlyer, ở phía trên bên phải, nhấp vào địa chỉ email của bạn.
> 2. Chọn **User Management** > Chọn người dùng.
> 3. Nếu được yêu cầu, hãy cấp cho người dùng quyền **Quản lý** trong **SKAN Converter Studio**. Để tìm hiểu thêm về các quyền, xem <Anchor target="_blank" href="/marketers/vi/docs/user-management">User Management</Anchor>.

<div id="skan-4" />

<Accordion title="SKAN 4">

Trong SKAN 4, bạn sử dụng các thành phần đo lường khác nhau như doanh thu, sự kiện trong ứng dụng, mức độ ưu tiên và Nguồn dữ liệu tin cậy duy nhất để xác định đối tượng cần đo lường trong mỗi ba cửa sổ đo lường. Tổ hợp của các thành phần trên tạo nên chế độ đo lường SKAN 4 của bạn.

Nếu bạn đang nâng cấp lên SKAN 4 từ chế độ SKAN trước đó, ánh xạ lược đồ hiện tại của bạn sẽ được mang sang cấu hình mịn của cửa sổ 1. AppsFlyer tự động ánh xạ các giá trị thô cho bạn trên cửa sổ 1 - 3.

Để cài chế độ SKAN 4 thủ công, hãy thử nghiệm với các tùy chọn khác nhau. Khi bạn thực hiện các thay đổi, tóm tắt **Conversion-value capacity** sẽ cập nhật. Hãy tối ưu hóa cài đặt của bạn để thu thập dữ liệu có giá trị nhất mà không vượt quá dung lượng. Xem phần [Conversion value capacity calculation.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

Lưu ý: **Nếu bạn đang nâng cấp lên SKAN 4 từ chế độ SKAN trước đó, ánh xạ lược đồ hiện tại của bạn sẽ được mang sang các phép đo lường mịn và AppsFlyer tự động ánh xạ các giá trị thô cho bạn. Và nếu bạn mới sử dụng SKAN, AppsFlyer sẽ cung cấp ánh xạ mặc định ban đầu.**

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Cách đặt giá trị chuyển đổi thủ công trong Conversion Studio bằng chế độ SKAN 4:**

1. Trong bảng điều khiển AppsFlyer, đi đến **Configurations** > **SKAN Conversion Studio.**
2. Nhấp vào tùy chọn (⋮) để hiển thị menu tùy chọn và đảm bảo đã bật **SKAN measurement**. **Lưu ý**! Nếu tắt, SDK sẽ không gọi các hàm SKAN iOS như *registerAppForAdNetworkAttribution*, *updateConversionValue.*
3. Chọn chế độ đo lường **SKAN 4.0**.
4. Nhấp vào **Continue**.  
   Cài đặt cho CV mịn **Window 1 (1-2 days)** sẽ mở.
5. [Tùy chọn] Bật **Nguồn dữ liệu tin cậy duy nhất (SSOT)**.  
   Cơ chế SSOT gắn cờ (và loại bỏ trùng lặp) các lượt cài đặt được báo cáo bằng nhiều phương thức khớp phân bổ. <Anchor target="_blank" href="/marketers/vi/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Tìm hiểu thêm</Anchor>
6. Nhấp **+ Add measurement** để thêm [các thành phần đo lường](/docs/skan-conversion-studio#thành-phần-đo-lường) khác nhau.  
   Các phần sau ghi rõ các tùy chọn cài đặt và thành phần đo lường. Sử dụng chúng làm hướng dẫn khi bạn thử nghiệm với các cài đặt đo lường SKAN khác nhau:
   * Doanh thu
   * Sự kiện trong Ứng dụng
   * Kênh
   * Mức độ ưu tiên
   * Dự đoán
7. Nhấp vào **Coarse** và lặp lại Bước 6-7 để đặt CV **Khung thời gian 1 (1-2 ngày) tương đối**.   
   **Lưu ý**: 
   * Chỉ có các thành phần đo lường Doanh thu và Sự kiện trong ứng dụng.
   * CV thấp phải là phiên người dùng để đảm bảo postback được gửi đi.
8. [Tùy chọn] Bật **Lock window** và đặt điều kiện (thời gian hoặc giá trị chuyển đổi tương đối) để khóa khung thời gian SKAN sớm hơn mặc định. [Tìm hiểu thêm](/docs/skan-conversion-studio#lock-window)
9. Nhấp vào **Window 2 (3-7 days)** và lặp lại Bước 6-8 để đặt CV của khung thời gian 2.   
   **Lưu ý**: 
   * Chỉ có các thành phần đo lường Doanh thu và Sự kiện trong ứng dụng.
   * [Khuyến nghị] CV thấp nên là phiên người dùng.
10. Nhấp vào **Window 3 (8-35 days)** và lặp lại Bước 6-8 để đặt CV của khung thời gian 3.   
    **Lưu ý**: 
    * Chỉ có các thành phần đo lường Doanh thu và Sự kiện trong ứng dụng.
    * [Khuyến nghị] CV thấp nên là phiên người dùng.
11. Nhấp vào **Save** (Lưu).
12. Xác minh rằng ánh xạ đăng lại sự kiện trong ứng dụng đối tác của bạn ánh xạ các sự kiện bạn đã cấu hình.

</Accordion>

<div id="custom" />

<Accordion title="Tùy chính">

Trong Tuỳ chỉnh, bạn sử dụng các thành phần đo lường khác nhau như doanh thu, sự kiện trong ứng dụng, ưu tiên và Nguồn dữ liệu tin cậy duy nhất để xác định đối tượng cần đo lường và đặt một khung thời gian hoạt động để xác định thời gian và khoảng thời gian đo lường sẽ diễn ra. Cùng nhau, các thành phần tạo ra chế độ đo lường Tuỳ chỉnh của bạn. 

Để đặt chế độ Tùy chỉnh, hãy thử nghiệm với các tùy chọn khác nhau. Khi bạn thực hiện các thay đổi, tóm tắt **Conversion-value capacity** sẽ cập nhật. Hãy tối ưu hóa cài đặt của bạn để thu thập dữ liệu có giá trị nhất mà không vượt quá dung lượng. Xem phần [Conversion value capacity calculation.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Cách đặt giá trị chuyển đổi thủ công trong Conversion Studio bằng chế độ Tùy chỉnh:**

1. Trong bảng điều khiển AppsFlyer, đi đến **Configurations** > **SKAN Conversion Studio.**
2. Nhấp vào tùy chọn (⋮) để hiển thị menu tùy chọn và đảm bảo đã bật **SKAN measurement**. **Lưu ý**! Nếu tắt, SDK sẽ không gọi các hàm SKAN iOS như *registerAppForAdNetworkAttribution*, *updateConversionValue.*
3. Chọn chế độ đo lường **Custom**.
4. Nhấp vào **Continue**.
5. [Tùy chọn] Bật **Nguồn dữ liệu tin cậy duy nhất (SSOT)**.  
   Cơ chế SSOT gắn cờ (và loại bỏ trùng lặp) các lượt cài đặt được báo cáo bằng nhiều phương thức khớp phân bổ. <Anchor target="_blank" href="/marketers/vi/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Tìm hiểu thêm</Anchor>
6. Nhấp **+ Add measurement** để thêm các thành phần đo lường khác nhau.  
   Các phần sau ghi rõ các tùy chọn cài đặt và thành phần đo lường. Sử dụng chúng làm hướng dẫn khi bạn thử nghiệm với các cài đặt đo lường SKAN khác nhau:
   * Doanh thu
   * Sự kiện trong Ứng dụng
   * Kênh
   * Mức độ ưu tiên
   * Dự đoán
7. Chọn thời lượng của Khung thời gian hoạt động (12 giờ - 63 ngày) mà bạn muốn để đo lường hoạt động người dùng.  
   **Activity timer** mặc định cho phép bạn đặt khung thời gian thành 24-72 giờ. Và cài đặt **Interval** mặc định cho phép bạn đặt 12 hoặc 24 giờ. Sử dụng **Custom window** để kéo dài khung thời gian hoạt động lên tối đa 63 ngày và đặt khoảng thời gian dài hơn.
8. Nhấp vào **Save** (Lưu).
9. Xác minh rằng ánh xạ đăng lại sự kiện trong ứng dụng đối tác của bạn ánh xạ các sự kiện bạn đã cấu hình.

</Accordion>

<div id="fixed-modes" />

<Accordion title="Chế độ cố định">

Trong chế độ cố định, bạn có thể đo lường giá trị người dùng bằng cách sử dụng một trong các thành phần đo lường sau:

* * Doanh thu
  * Chuyển đổi
  * Tương tác

Khi bạn thay đổi các cài đặt chế độ, tóm tắt **Conversion-value capacity** sẽ cập nhật. Hãy tối ưu hóa cài đặt của bạn để thu thập dữ liệu có giá trị nhất mà không vượt quá dung lượng. Xem phần [Conversion value capacity calculation.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**Lưu ý!**

* Đo lường trong chế độ cố định dành cho cửa sổ hoạt động 24 giờ, bắt đầu từ lần mở ứng dụng đầu tiên.
* Nếu muốn gửi các sự kiện bằng S2S, bạn phải bật [SKAN S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api)

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Cách đặt giá trị chuyển đổi thủ công trong Conversion Studio bằng chế độ cố định:**

1. Trong bảng điều khiển AppsFlyer, đi đến **Configurations** > **SKAN Conversion Studio.**
2. Nhấp vào tùy chọn (⋮) để hiển thị menu tùy chọn và:
   * Đảm bảo đã bật **SKAN measurement**. **Lưu ý**! Nếu tắt, SDK sẽ không gọi các hàm SKAN iOS như *registerAppForAdNetworkAttribution*, *updateConversionValue.*
   * [Tùy chọn] [Cho phép gửi sự kiện bằng S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api). Khả dụng nếu chế độ đã chọn là doanh thu, lượt chuyển đổi hoặc lượt tương tác.
3. Chọn một chế độ đo lường cố định.
4. Làm theo thông tin và hướng dẫn trong bảng theo sau đối với chế độ đo lường cố định bạn đã chọn.
5. Nhấp vào **Save**.
6. Xác minh rằng ánh xạ đăng lại sự kiện trong ứng dụng đối tác của bạn ánh xạ các sự kiện bạn đã cấu hình.

<div id="fixed-mode-measurement" />

#### Đo lường ở chế độ cố định

| Chế độ đo lường | Mô tả |
| --- | --- |
| [Mặc định] Doanh thu | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Doanh thu được tạo ra trong khung thời gian hoạt động 24 giờ.**<br /><br />Chọn tỷ giá đơn vị sang USD từ một trong các tùy chọn sau:<ul><li>$0,01 để đo lên đến $0,63</li><li>$1 để đo lên đến $63</li><li>$10 để đo lên đến $630</li></ul>AppsFlyer tự động điền 63 phạm vi đo lường doanh thu. `af_skad_revenue` phải được ánh xạ. Trong bảng điều khiển, doanh thu được ghi nhận là giá trị tối đa của phạm vi. Ví dụ: nếu phạm vi là từ 60 USD - 61 USD, doanh thu được ghi nhận là 61 USD. Lưu ý! Doanh thu trong Custom sử dụng một phương thức khác để tính toán.<br /><br />**Các số liệu có sẵn:**<ul><li>Doanh thu</li><li>ROI</li><li>ROAS</li><li>ARPU: Doanh thu/người dùng cài đặt ứng dụng</li><li>Tỷ lệ người dùng chuyển đổi: Người dùng mua hàng/người dùng cài đặt ứng dụng</li><li>eCPA</li></ul> |
| Chuyển đổi | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**Các sự kiện trong ứng dụng được thực hiện một hoặc nhiều lần trong khung thời gian hoạt động 24 giờ**<br /><br />**Cài đặt**:<ul><li>Chọn 1-6 sự kiện trong ứng dụng để đo lường từ danh sách thả xuống. Giới hạn: Danh sách được giới hạn chỉ 300 sự kiện hàng đầu trong 30 ngày trước đó.</li><li>Trong bảng điều khiển SKAdNetwork, hãy chọn một sự kiện nhất định làm <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">sự kiện chuyển đổi</Anchor>.</li></ul>**Số liệu cho mỗi sự kiện trong ứng dụng:**<ul><li>Số lượng người dùng thực hiện một sự kiện</li><li>Tỷ lệ chuyển đổi: Người dùng thực hiện Sự kiện Chuyển đổi/người dùng cài đặt ứng dụng</li><li>eCPA</li><li>Phiên (sử dụng sự kiện *af\_app\_opened)*</li></ul>Ví dụ về số lượng người dùng:<ul><li>Hoàn tất đăng ký</li><li>Đã mua hàng</li><li>Đã đạt đến cấp độ trò chơi</li></ul>**Diễn giải!** Sử dụng phép đo chuyển đổi để tính **xem** người dùng có thực hiện sự kiện hay không. Để đếm số lần người dùng thực hiện một sự kiện, hãy sử dụng phép đo mức độ thu hút. |
| Tương tác | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Số lần người dùng thực hiện một sự kiện trong ứng dụng cụ thể trong Khung thời gian Hoạt động**<br /><br />**Cài đặt:**<ul><li>Chọn một sự kiện trong ứng dụng từ danh sách thả xuống.</li><li>Lựa chọn trong ứng dụng cũng được chỉ định là Sự kiện Chuyển đổi.</li><li>Phạm vi giá trị: 0-63</li></ul>**Các số liệu cho sự kiện trong ứng dụng**:<ul><li>Số lượng người dùng thực hiện sự kiện</li><li>Số sự kiện trung bình trên mỗi người dùng</li><li>Tỷ lệ chuyển đổi</li><li>eCPA</li><li>Các phiên</li></ul>Ví dụ:<ul><li>Đo số lần:<ul><li>một người dùng đã mở ứng dụng</li><li>người dùng đã xem một quảng cáo</li></ul></li></ul> |

</Accordion>

<div id="decode" />

<Accordion title="Giải mã">

Tạo ánh xạ CV tới sự kiện của riêng bạn và tự đặt CV trong ứng dụng. Sử dụng tùy chọn này nếu bạn không thể tích hợp SDK AppsFlyer vào ứng dụng của mình.

**Cách sử dụng chế độ Giải mã**:

1. Trong bảng điều khiển AppsFlyer, đi đến **Configurations** > **SKAN Conversion Studio.**
2. Nhấp vào tùy chọn (⋮) để hiển thị menu tùy chọn và:
   * Đảm bảo đã bật **SKAN measurement**. **Lưu ý**! Nếu tắt, SDK sẽ không gọi các hàm SKAN iOS như *registerAppForAdNetworkAttribution*, *updateConversionValue.*
   * Tải lên tệp tin Ánh xạ giải mã của bạn.
3. Nhấp vào **Save**.
4. Xác minh rằng ánh xạ đăng lại sự kiện trong ứng dụng đối tác của bạn ánh xạ các sự kiện bạn đã cấu hình.

</Accordion>

<div id="measurement-components" />

## Thành phần đo lường

<div id="single-source-of-truth" />

<Accordion title="Nguồn dữ liệu tin cậy duy nhất">

<table><tbody><tr><td colspan="2"><p><img alt="SSOTControl.png" src="https://files.readme.io/77570ca922d33a0ef3df4b5a42904452c07b9b472ea4c68c8390155ed2bc53ed-4458326657553.png"/></p><p>Cơ chế <a href="./single-source-of-truth-ssot-guide-for-ios-attribution" target="_blank">Nguồn dữ liệu tin cậy duy nhất (SSOT)</a> gắn cờ (và loại bỏ trùng lặp) các lượt cài đặt được báo cáo bằng nhiều phương thức khớp phân bổ. Nói cách khác, SKAN và một phương thức khác. Cờ có sẵn trong báo cáo dữ liệu thô SKAN và được xem xét khi tính toán phép đo trong <a href="./single-source-of-truth-ssot-guide-for-ios-attribution#chế-độ-xem-nguồn-dữ-liệu-tin-cậy-duy-nhất-trên-bảng-điều-khiển-tổng-quan" target="_blank">chế độ xem SSOT</a> của bảng điều khiển Tổng quan. </p></td></tr><tr><td><p>Bắt buộc</p></td><td>Không</td></tr><tr><td><p>Được phép sử dụng nhiều lần</p></td><td>Không</td></tr><tr><td><p>Tùy chọn cài đặt</p></td><td><p>nếu bật SSOT, hãy đặt CV sao cho CV có thể gắn cờ nếu một người dùng được phân bổ bởi SKAN và một phương thức so khớp phân bổ khác. </p><p>Cờ SSOT được sử dụng trong trường hợp nào?</p><ul><li>Chế độ xem SSOT của bảng điều khiển Tổng quan về AppsFlyer</li><li>Các báo cáo dữ liệu thô SKAN có trường <em>af_attribution_flag</em>. Nếu là true, người dùng được phân bổ bởi cả SKAN và một phương thức khác. </li><li>Báo cáo API phân bổ hợp nhất của SKAN.</li></ul></td></tr></tbody></table>

</Accordion>

<div id="predict-component" />

<Accordion title="Thành phần Dự đoán">

<table><tbody><tr><td colspan="2"><p><img alt="Predict-SKAN_Conversion_Studio__1_.png" src="https://support.appsflyer.com/hc/article_attachments/7742007538065"/></p></td></tr><tr><td><p>Bắt buộc</p></td><td><p>Không</p></td></tr><tr><td><p>Được phép sử dụng nhiều lần</p></td><td><p>Không</p></td></tr><tr><td><p>Tùy chọn cài đặt</p></td><td><ul><li><span>Chỉ đọc</span></li><li><span>Khung thời gian hoạt động được đặt thành 24 giờ</span></li><li><span>Các cài đặt khác đều dựa trên cài đặt Dự đoán</span></li></ul></td></tr><tr><td><p>Tính khả dụng</p></td><td><ul><li>Có sẵn cho người đăng ký Dự đoán</li><li>Để nhận quyền truy cập Dự đoán, liên hệ với CSM của bạn</li></ul></td></tr></tbody></table>

</Accordion>

<div id="inapp-event-component" />

<Accordion title="Thành phần sự kiện trong ứng dụng">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioIn-app-event.png](https://files.readme.io/7b110093a72b13c0750ccb66da5efe737b8f83c0adcb95eb35185a4dc77bad6c-4406051824657.png)
      </td>
    </tr>
    <tr>
      <td>
        Bắt buộc
      </td>
      <td>
        Không
      </td>
    </tr>
    <tr>
      <td>
        Được phép sử dụng nhiều lần
      </td>
      <td>
        Yes
      </td>
    </tr>
    <tr>
      <td>
        Tùy chọn cài đặt
      </td>
      <td>
        Chọn một sự kiện trong ứng dụng; sau đó thiết lập phạm vi theo mục tiêu đo lường của bạn như sau:

        * **Chỉ chuyển đổi:** Cấu hình một phạm vi với phạm vi từ 0–1
        * **Mức độ thu hút và chuyển đổi:** Cấu hình nhiều phạm vi với các phạm vi bạn đã chọn
      </td>
    </tr>
    <tr>
      <td>
        Phạm vi thu hút
      </td>
      <td>
        Để đo lường mức độ thu hút, bạn phải tạo phạm vi xảy ra. Khi việc xuất hiện một sự kiện thu hút đã chọn được báo cáo, thì SKAN sẽ liên kết sự kiện đó với phạm vi thích hợp theo số lần xuất hiện sự kiện.

        **Đặc điểm**

        * Mỗi phạm vi chứa một phạm vi xuất hiện bao gồm giá trị **bắt đầu** và giá trị **kết thúc**. Giá trị thấp hơn sẽ không được đưa vào phạm vi, trong khi giá trị cao hơn sẽ thuộc phạm vi. Ví dụ, 5–10 có nghĩa là lớn hơn 5 đến bằng 10.
        * Phạm vi có giá trị thấp nhất luôn bắt đầu từ 0 (nhưng không bao gồm bằng 0).
        * Bạn có thể tạo bao nhiêu phạm vi tùy thích, nhưng hãy nhớ rằng mỗi phạm vi ảnh hưởng đến dung lượng giá trị chuyển đổi của bạn.
        * Phạm vi phải tuần tự (không có khoảng cách giữa các phạm vi).

        **Đo lường mức độ thu hút bằng cách sử dụng phạm vi**

        * Khi việc xuất hiện sự kiện được báo cáo, thì SKAN sẽ liên kết sự kiện đó với phạm vi thích hợp. Số lần xuất hiện được ghi nhận sẽ được tính từ giá trị trung bình của phạm vi. Giá trị được làm tròn đến số nguyên gần nhất. Ví dụ: 5,7 được làm tròn thành 6.
        * Nếu số lần xuất hiện vượt quá giá trị tối đa của phạm vi có giá trị cao nhất, thì các lần xuất hiện được liên kết với phạm vi giá trị cao nhất. Số lần xuất hiện được ghi nhận là giá trị trung bình của phạm vi có giá trị cao nhất. Nói cách khác, số lần xuất hiện thực tế được bỏ qua.
        * Trong dữ liệu thô, cả số lần xuất hiện và phạm vi thực tế đều có sẵn.

        **Ví dụ:**

        Trong hình ảnh, các phạm vi xuất hiện sau đây sẽ được mô tả:

        Các phạm vi xuất hiện được đặt là:

        * A: 0-5
        * B: 5-10
        * C: 10-20

        Số lần xuất hiện được ghi nhận bằng cách sử dụng các phạm vi như sau:

        | Ví dụ: | Số lần xuất hiện được SDK báo cáo | Phạm vi được liên kết | Số lần xuất hiện được báo cáo |
        | --- | --- | --- | --- |
        | 1 | 5 | A | 3 |
        | 2 | 6 | B | 8 |
        | 3 | 10 | B | 8 |
        | 4 | 125 | C | 15 |
      </td>
    </tr>
    <tr>
      <td>
        Mức giới hạn
      </td>
      <td>
        Một sự kiện trong ứng dụng nhất định có thể được liên kết một lần với thành phần này.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="revenue-component" />

<Accordion title="Thành phần doanh thu">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioRevenue.png](https://files.readme.io/202c258f11cd93248f8aceff410126efc02ced11e9a9b159bac8ba81cbc8d9fe-4406075612305.png)
      </td>
    </tr>
    <tr>
      <td>
        Bắt buộc
      </td>
      <td>
        Không
      </td>
    </tr>
    <tr>
      <td>
        Được phép sử dụng nhiều lần
      </td>
      <td>
        Có, nếu sử dụng nguồn doanh thu sự kiện trong ứng dụng.
      </td>
    </tr>
    <tr>
      <td>
        Tùy chọn cài đặt
      </td>
      <td>
        Doanh thu có thể được ghi nhận bằng cách sử dụng một sự kiện hoặc bạn có thể liên kết doanh thu theo luồng bằng các sự kiện trong ứng dụng đã chọn.

        Các tùy chọn nguồn doanh thu sau được hỗ trợ:

        * **Tổng doanh thu**
          * Mọi doanh thu đều được SKAN ghi nhận bằng cách sử dụng sự kiện `af_skad_revenue`. `af_skad_revenue` phải được ánh xạ.
          * Thành phần có thể được đưa vào một lần.
        * **Sự kiện trong Ứng dụng**
          * Doanh thu được báo cáo theo loại được phân bổ cho một sự kiện trong ứng dụng được chọn và được SKAN ghi nhận bằng cách sử dụng sự kiện trong ứng dụng đã chọn. Phải ánh xạ sự kiện; không nên ánh xạ `af_skad_revenue`.
          * Thành phần có thể được sử dụng nhiều lần.
          * Nếu bạn báo cáo doanh thu bằng đăng lại đến các mạng quảng cáo, hãy xác minh rằng ánh xạ đăng lại sự kiện trong ứng dụng của bạn bao gồm các sự kiện doanh thu trong ứng dụng do bạn đặt.
      </td>
    </tr>
    <tr>
      <td>
        Phạm vi
      </td>
      <td>
        Để đo lường doanh thu, bạn phải tạo phạm vi doanh thu. Khi doanh thu được báo cáo, SKAN sẽ liên kết doanh thu được báo cáo với phạm vi thích hợp.

        **Đặc điểm**

        * Mỗi phạm vi chứa một phạm vi doanh thu bao gồm giá trị **bắt đầu** và giá trị **kết thúc**. Giá trị thấp hơn sẽ không thuộc trong phạm vi; tuy nhiên, giá trị cao sẽ nằm trong phạm vi. Ví dụ: 5–10 có nghĩa là lớn hơn 5 đến bằng 10.
        * Phạm vi có giá trị thấp nhất luôn bắt đầu từ 0 (nhưng không bao gồm bằng 0).
        * Bạn có thể tạo bao nhiêu phạm vi tùy thích, nhưng hãy nhớ rằng mỗi phạm vi ảnh hưởng đến dung lượng giá trị chuyển đổi của bạn.
        * Các phạm vi phải tuần tự (không có khoảng cách giữa chúng.)
        * Số tiền tính bằng USD
        * Nếu chạy chiến dịch trên quảng cáo Meta, bạn phải có từ 4 phạm vi trở lên.
        * Giá trị phạm vi có thể có tối đa 4 chữ số sau dấu thập phân.

        **Ghi nhận doanh thu bằng cách sử dụng phạm vi**

        * Khi doanh thu được báo cáo, SKAN sẽ liên kết doanh thu với phạm vi thích hợp. Doanh thu được ghi nhận bằng giá trị trung bình của phạm vi.
        * Nếu doanh thu được báo cáo vượt quá giá trị trung bình của phạm vi giá trị cao nhất, thì doanh thu sẽ được liên kết với phạm vi giá trị cao nhất. **Lưu ý**! Doanh thu được ghi nhận là giá trị trung bình của phạm vi này. Nói cách khác, số tiền doanh thu thực tế sẽ được bỏ qua.
        * Trong dữ liệu thô, doanh thu được ghi nhận và phạm vi được liên kết sẽ có sẵn.

        **Ví dụ:**

        Trong hình ảnh, các phạm vi doanh thu sau được mô tả:

        * A: 0-5
        * B: 5-10
        * C: 10-20

        Doanh thu được ghi nhận bằng cách sử dụng các phạm vi như sau:

        | Ví dụ: | Doanh thu do SDK báo cáo | Phạm vi được liên kết | Doanh thu được ghi nhận |
        | --- | --- | --- | --- |
        | 1 | 5 | A | $2,5 |
        | 2 | 6 | B | $7,5 |
        | 3 | 10 | B | $7,5 |
        | 4 | 125 | C | 15 USD |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="funnel-component" />

<Accordion title="Thành phần kênh">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        <Image alt="ConversionValueFunnel.png" src="https://files.readme.io/b43b5db0cee11c9addd50fb56af1ac6d3221e1956e2ee3c4c21a6940e9dfe61b-4406051997969.png" width="674px" />
      </td>
    </tr>
    <tr>
      <td>
        Bắt buộc
      </td>
      <td>
        Không
      </td>
    </tr>
    <tr>
      <td>
        Được phép sử dụng nhiều lần
      </td>
      <td>
        Không
      </td>
    </tr>
    <tr>
      <td>
        Tùy chọn cài đặt
      </td>
      <td>
        Liệt kê một tập hợp các sự kiện tuần tự trong một kênh. Vì sự xuất hiện của một sự kiện đơn lẻ được coi là sự xuất hiện của tất cả các sự kiện trước đó, nên thứ tự mà bạn liệt kê các sự kiện là rất quan trọng, như được minh họa trong ví dụ sau.
      </td>
    </tr>
    <tr>
      <td>
        Ví dụ:
      </td>
      <td>
        Một kênh chứa các sự kiện a, f, b, k và z, như được minh họa trong hình trước.

        | Ví dụ: | Sự kiện được thực hiện | Sự kiện được ghi nhận |
        | --- | --- | --- |
        | 1 | a | a |
        | 2 | b | a, f, b |
        | 3 | z | a, f, b, k, z |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="priority-measurement-component" />

<Accordion title="Thành phần đo lường ưu tiên">

Sử dụng thành phần đo lường ưu tiên, nằm trong chế độ Tuỳ chỉnh, để xếp hạng hành trình hành động của người dùng trong ứng dụng dựa trên logic kinh doanh của bạn để các đo lường có mức ưu tiên cao ghi đè các đo lường có mức ưu tiên thấp. Điều này cho phép bạn chọn đối tượng cần đo lường trong mỗi bước của kênh chuyển đổi. 

Mỗi ưu tiên (tối đa 63) có thể chứa doanh thu, sự kiện trong ứng dụng hoặc cả hai. Khi người dùng thực hiện các sự kiện trong ứng dụng, AppsFlyer sẽ xác định ưu tiên nào phù hợp với các hành động do người dùng thực hiện và đặt CV sao cho phù hợp.

Để dễ hiểu, hãy so sánh bằng cách sử dụng Tuỳ chọn có và không có thành phần ưu tiên. **Không có** thành phần ưu tiên, AppsFlyer ánh xạ tất cả các kết hợp đo lường có thể có vào CV. Trong khi với **có** thành phần ưu tiên, chỉ các kết hợp đo lường do bạn đặt rõ ràng mới được ánh xạ tới CV.

Ưu tiên được giải thích rõ nhất tại [ví dụ chi tiết](/docs/skan-conversion-studio#priority-measurement-detailed-example) trong bài viết này. 

**Nguyên tắc ưu tiên**

* Bạn có thể đặt từ 1-63 ưu tiên. Số có sẵn tùy thuộc vào khung thời gian hoạt động và cài đặt Nguồn dữ liệu tin cậy duy nhất của bạn.
* Ưu tiên 1 luôn có mức ưu tiên cao nhất. Ưu tiên có số lớn nhất là ưu tiên có mức thấp nhất.
* Một ưu tiên bao gồm [doanh thu](/docs/skan-conversion-studio#revenue-component) hoặc s[ự kiện trong ứng dụng](/docs/skan-conversion-studio#inapp-event-component) hoặc cả hai thành phần. Một ưu tiên nhất định có thể chứa nhiều luồng sự kiện trong ứng dụng và doanh thu.
* Kênh không có sẵn trong ưu tiên. Tuy nhiên, hãy đặt nhiều sự kiện trong ứng dụng ở một ưu tiên để đo lường lượt chuyển đổi của người dùng trong một kênh.
* Để sử dụng thành phần đo lường ưu tiên, bạn không thể cấu hình các thành phần khác, chẳng hạn sự kiện trong ứng dụng hoặc doanh thu.

**Cách thiết đặt phép đo dựa vào mức độ ưu tiên:**

1. Trong AppsFlyer, đi đến **SKAN Conversion Studio.**
2. Chọn **Custom**, nhấp vào **Continue**.
3. Nếu cần, nhấp vào **Delete** để xóa cài đặt hiện tại.
4. Nhấp vào **+ Add measurement**. Chọn **Priority**.   
   Ưu tiên 1 hiển thị.  

   [![Priority1.png](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)
5. Chọn một thành phần đo lường từ:
   * Doanh thu
   * Sự kiện trong Ứng dụng
6. Điền đầy đủ các trường theo giao diện người dùng.
   * Lưu ý rằng một ưu tiên có thể bao gồm doanh thu, sự kiện trong ứng dụng hoặc cả hai.
   * Giá trị phạm vi của số lần xuất hiện sự kiện và doanh thu phải xếp theo thứ tự gia tăng (tăng dần) và liên tục. Ví dụ: sau đây là các phạm vi tăng liên tục: 1-5, 5-8, 8-10, v.v. Một phạm vi nhất định có thể được sử dụng nhiều lần (lặp lại) nếu ở lần thứ hai, phạm vi đó nằm trong một kết hợp duy nhất và có cùng một phạm vi như ưu tiên cuối cùng với một phạm vi. Ví dụ: 1-5, 1-5 + thêm vào giỏ hàng.
7. Nhấp vào Validate.  
   Priority is valid message sẽ hiển thị. Nếu không đúng như vậy, sửa đúng ưu tiên của bạn trước khi tiếp tục.
8. Thực hiện một trong những việc sau:
   * Để thêm một ưu tiên, nhấp vào **+ Add priority.** Ưu tiên hiện tại 1 được chuyển xuống thành ưu tiên 2. Hoàn thành các cài đặt ưu tiên như đã mô tả trước đó.
   * Để xoá một ưu tiên, nhấp vào … > **Delete.**
   * Để thay đổi mức độ ưu tiên, nhấp vào **Options** (⋮), sau đó chọn **Change order** hoặc **Make lowest priority**.
   * Để sao chép một ưu tiên, nhấp vào **Options** (⋮) và chọn **Duplicate**.
   * Nhấp vào **Save** để hoàn tất các ưu tiên cài đặt.

</Accordion>

<div id="lock-window" />

<Accordion title="Khóa khung thời gian">

**Lưu ý**: Khóa khung thời gian chỉ phù hợp với SKAN 4 trở lên.

<table><tbody><tr><td colspan="2"><p><img alt="lock_window.png" src="https://files.readme.io/d9db51890a5d589b7343ed389d55af0c4181b249a2c5e970b9a5e1244c489abc-14240675527057.png"/></p></td></tr><tr><td><p>Sử dụng</p></td><td><span>Khung thời gian SKAN theo mặc định đo lường giá trị người dùng cho các thời điểm cụ thể sau khi cài đặt. Bạn có thể khóa khung thời gian sớm và gửi đăng lại với tất cả dữ liệu có sẵn. Để thực hiện, hãy đặt các điều kiện về thời điểm khóa các khung thời gian.</span></td></tr><tr><td><p>Bắt buộc</p></td><td>Không</td></tr><tr><td><p>Được phép sử dụng nhiều lần</p></td><td>Có, một cho mỗi khung thời gian SKAN</td></tr><tr><td><p>Tùy chọn điều kiện</p></td><td><p>Khóa khung thời gian bao gồm hai tùy chọn cho khóa sớm khung thời gian SKAN:</p><ul><li>Thời gian: Sau đó, bạn phải chọn thời gian sau khi cài đặt (trước thời gian mặc định) để khóa khung thời gian. <strong>Lưu ý</strong>: Khóa dựa trên thời gian không có hiệu lực trừ khi người dùng mở ứng dụng.</li><li>Giá trị có tính tương đối cao: Ngay khi đạt đến giá trị có tính tương đối cao, khung thời gian sẽ đóng lại.</li></ul></td></tr><tr><td><p>Tác động của việc sử dụng khóa khung thời gian</p></td><td><p>Bài đăng lại SKAN không chứa thông tin về thời điểm kết thúc khung thời gian, vì vậy trạng thái khung thời gian khóa không được cân nhắc khi ước tính thời gian cài đặt. Do đó, việc khóa khung thời gian sớm có thể ảnh hưởng đến độ chính xác của ước tính thời gian cài đặt.</p></td></tr></tbody></table>

</Accordion>

<div id="activity-window" />

<Accordion title="Khung thời gian hoạt động">

**Lưu ý**:

* Cửa sổ hoạt động chỉ phù hợp cho SKAN 3 trở xuống (nghĩa là các chế độ Tùy chỉnh và cố định).
* Nếu bạn sử dụng SKAN 4+, nhưng thiết bị người dùng hoặc mạng quảng cáo chưa hỗ trợ SKAN 4, Cửa sổ hoạt động là 48 giờ.

<table><tbody><tr><td colspan="2"><p><img alt="flex_activity_window.jpg" src="https://files.readme.io/ac51126eda5b9d319ccdd90adb936baaa512dcd844ad191cac6c20a45cd4aae8-6390396808081.jpg"/></p></td></tr><tr><td><p>Bắt buộc</p></td><td>Có </td></tr><tr><td><p>Được phép sử dụng nhiều lần</p></td><td>Không</td></tr><tr><td><p>Đặc điểm thời gian</p></td><td><ul><li>Bộ đếm thời gian này có thời lượng cố định, do bạn đặt và chạy song song với bộ đếm thời gian trên iOS.</li><li>Ngược lại, bộ đếm thời gian trên iOS có thời lượng ban cố định là 24 giờ. Mỗi khi giá trị chuyển đổi tăng lên, bộ đếm thời gian sẽ được chạy lại.</li><li>Thời lượng mặc định là 24 giờ.</li><li>Phép đo dừng khi một trong hai bộ đếm thời gian về 0. </li></ul></td></tr><tr><td>Thời lượng bộ đếm thời gian</td><td><ul><li>Phạm vi: 12-72 giờ. Để biết thêm về các tuỳ chọn, xem <strong>Flexible measurement</strong> trong bảng này.  </li><li>Khi bộ đếm thời gian kết thúc, AppsFlyer sẽ ngừng đo.</li><li>Nếu thời lượng bộ đếm thời gian kéo dài hơn 24 giờ, thì người dùng phải có hoạt động trong ứng dụng ít nhất một lần trong mỗi quãng (interval). Nếu không, quá trình đo (activity timer) có thể kết thúc sớm hơn thời lượng đề ra ban đầu vì ở trường hợp này bộ đếm của iOS đã dừng.</li></ul></td></tr><tr><td><p>Khoảng thời gian</p></td><td><p>12 hoặc 24 giờ. Khoảng thời gian ảnh hưởng đến độ chính xác của phạm vi thời gian hoạt động cuối cùng và thời gian cài đặt. Để biết thêm về các tuỳ chọn, xem <strong>Flexible measurement</strong> trong bảng này. </p><p>Phạm vi thời gian hoạt động cuối cùng có sẵn trong báo cáo dữ liệu thô trong cột <em>min_install_time</em> và <em>max_install_time</em> và được sử dụng để xác định thời gian cài đặt như được mô tả trong phần này.</p><p>Ví dụ:</p><ul><li>Thời lượng bộ đếm thời gian được đặt thành 48 giờ</li><li>Người dùng hoạt động lần cuối trong giờ 40</li><li>Tùy thuộc vào tùy chọn cài đặt khoảng thời gian, phạm vi thời gian hoạt động cuối cùng là: <br/><ul><li>Khoảng thời gian 12 giờ: 36–48 giờ</li><li>Khoảng thời gian 24 giờ: 24–48 giờ</li></ul></li></ul></td></tr><tr><td><p>Thời gian cài đặt</p></td><td><p>Thời gian cài đặt được tính như sau:</p><p><code>Thời gian cài đặt = Thời gian đến của đăng lại - [Phạm vi hoạt động cuối cùngtrung bình] - [Độ trễ đăng lại trên iOS]</code></p><ul><li> <code>Thời gian đến của đăng lại</code>:  Thời gian mà lần đầu tiên đăng lại iOS được nhận trực tiếp từ thiết bị; thường do mạng quảng cáo tiếp nhận. </li><li> <code>Phạm vi hoạt động cuối cùng trung bình</code> cân nhắc CV và được tính như sau: <ul><li>Nếu CV = 0  phạm vi hoạt động cuối cùng được giả định bằng 0. </li><li>Nếu CV &gt; 1 hoặc CV = null: Sử dụng min_install_time và max_install_time. Các thông số này được đặt dựa trên khoảng thời gian và lần cuối cùng người dùng được xác định đang hoạt động trên ứng dụng.  Ví dụ: Nếu khoảng thời gian là 12 khi lần cuối cùng người dùng được xác định đang hoạt động là 25 giờ sau khi cài đặt, kết quả là [24 + 36]/2 = 30. </li></ul></li><li> <code>Độ trễ đăng lại trên iOS</code>: [24 + 48] / 2 = 36. Hãy để ý rằng bộ đếm thời gian trên iOS kết thúc 24 giờ sau lần thay đổi cuối cùng đối với CV và đăng lại được gửi trong 0–24 giờ sau đó. <strong>36 giờ là một hằng số</strong>. </li></ul></td></tr><tr><td><p>Tùy chọn cài đặt</p></td><td><p>Khung thời gian Hoạt động bao gồm hai tùy chọn cài đặt thời lượng và khoảng thời gian. </p><ul><li>Thời lượng: 24–72 giờ với khoảng thời gian là 24 giờ. Tối đa 3 khoảng thời gian.</li><li>Thời lượng: 12–72 giờ với khoảng thời gian 12 giờ. Tối đa 6 khoảng thời gian.</li></ul></td></tr><tr><td><p>Tác động của việc thay đổi thời lượng của khung thời gian hoạt động</p></td><td><ul><li>Đăng lại được gửi trong 0-24 giờ sau khi bộ đếm thời gian trên iOS kết thúc. </li><li>Ban đầu, bộ đếm thời gian trên iOS được ấn định sẽ kết thúc sau 24 giờ. </li><li>Nếu bạn đặt khung thời gian hoạt động hơn 24 giờ, thì người dùng phải hoạt động ít nhất một lần mỗi khoảng thời gian để đảm bảo rằng bộ đếm thời gian trên iOS không kết thúc.</li></ul></td></tr><tr><td><p>Những điều cần lưu ý liên quan đến mạng quảng cáo</p></td><td><ul><li>Thời lượng bộ đếm thời gian mặc định là 24 giờ.</li><li>Bạn có thể đặt một khoảng thời gian khác, nhưng trước khi thực hiện, hãy xác minh với các đối tác mạng quảng cáo của bạn xem họ có hỗ trợ khoảng thời gian khác với tùy chọn mặc định hay không. </li><li><span>Khi sử dụng cửa sổ 24 giờ, bạn có thể củng cố phép đo của bạn bằng cách chia khung thời gian 24 giờ thành 2 khoảng, mỗi khoảng 12 giờ. Khi đó, bạn sẽ biết liệu người dùng có tiếp tục sử dụng ứng dụng sau 12 giờ đầu tiên hay không. </span></li></ul></td></tr><tr><td><p>Ví dụ về yêu cầu dung lượng phạm vi</p></td><td><p><span>Hình ảnh trong phần này hiển thị bộ đếm thời gian 60 giờ với khoảng thời gian 12 giờ. </span></p></td></tr><tr><td><p>Tùy chọn khung thời gian hoạt động linh hoạt</p></td><td><p>Tính năng đo lường linh hoạt cho phép bạn đặt khung thời gian hoạt động dài hơn và có tính chi tiết hàng giờ. Cài đặt khoảng thời gian cũng tương tự như thế. Các cài đặt có các đặc điểm sau:</p><ul><li>Khung thời gian hoạt động: <ul><li>Phạm vi: 12-1512 giờ (63 ngày)  </li><li>Tính chi tiết: 1 giờ</li></ul></li><li>Khoảng thời gian: <ul><li>Phạm vi: <span>Tối thiểu 1 giờ và bất kỳ số nhân nào khác của khung thời gian hoạt động</span> </li><li>Tính chi tiết là 1 giờ</li></ul></li></ul><p>Điều cần lưu ý: Tỷ lệ của khung thời gian hoạt động và các khoảng thời gian phải là một số nguyên.</p><p>Phương pháp thực hành tốt nhất: Không đặt khoảng thời gian lớn hơn 24 giờ, vì điều này làm giảm độ chính xác trong ước tính thời gian cài đặt.</p></td></tr></tbody></table>

</Accordion>

<div id="additional-information" />

## Thông tin bổ sung

<div id="view-cv-mapping" />

<Accordion title="Xem ánh xạ CV">

* Xem các sự kiện được ánh xạ với CV bằng cách chọn CV. Các sự kiện được ánh xạ hiển thị bên dưới bảng.
* Tải xuống bảng ánh xạ CV dưới dạng tệp tin CSV. Nhấp vào **Download mapping file.**
* Nhận ánh xạ CV bằng <Anchor target="_blank" href="/marketers/vi/docs/skan-cv-schema-api-for-advertisers">API lược đồ SKAN CV dành cho nhà quảng cáo</Anchor>.

![CVmapping.png](https://files.readme.io/97ec2570636897a6274f7750c7f77c92d8457cab51660de496bec6cb7504c4a3-4407788932113.png)

<div id="csv-mapping-file-columns" />

#### Các cột tệp tin ánh xạ CSV

| Cột | Mô tả |
| --- | --- |
| app\_id |  |
| conversion\_value | Giá trị CV:<ul><li>0 - 63</li><li>Thấp, trung bình hoặc cao</li></ul> |
| event\_name |  |
| min\_event\_counter | Giới hạn dưới của phạm vi bộ đếm sự kiện |
| max\_event\_counter | <ul><li>Giới hạn trên của phạm vi bộ đếm sự kiện.</li><li>Trong các báo cáo do AppsFlyer tạo, số lượng sự kiện được tính bằng công thức sau: Giá trị làm tròn ([min\_event\_counter + max\_event\_counter]) / 2</li></ul> |
| min\_event\_revenue | Giới hạn dưới của phạm vi doanh thu sự kiện tính bằng USD |
| max\_event\_revenue | <ul><li>Giới hạn trên của phạm vi doanh thu sự kiện tính bằng USD</li><li>Trong các báo cáo do AppsFlyer tạo, doanh thu được tính theo công thức sau: ([min\_event\_revenue + max\_event\_revenue]) / 2)</li></ul> |
| min\_time\_post\_install | Giới hạn dưới, số giờ sau khi cài đặt, cho biết thời điểm người dùng hoạt động lần cuối trong ứng dụng. |
| max\_time\_post\_install | Giới hạn trên, số giờ sau khi cài đặt, cho biết thời điểm người dùng hoạt động lần cuối trong ứng dụng. |
| last\_config\_change | Ngày bạn lưu cấu hình trong SKAN Conversion Studio. |

</Accordion>

<div id="conversion-value-capacity-formula" />

<Accordion title="Công thức dung lượng giá trị chuyển đổi">

Như đã giải thích trước đây, số giá trị chuyển đổi hiện có tối đa là 64. Công thức sau đây sẽ tính toán chế độ sử dụng bao nhiêu giá trị chuyển đổi khả dụng.

```http
(activity time duration in hours / interval size in hours) * 
(number of revenue ranges + 1 ) * 
(number of in-app event ranges + 1 ) * 
(number of steps in a funnel + 1)
```

Điều chỉnh công thức để đưa vào tất cả các thành phần đo lường

</Accordion>

<div id="maximized-custom-cv-examples" />

<Accordion title="Các ví dụ về CV Tùy chỉnh được Tối đa hóa">

<div id="example-1" />

#### Ví dụ 1

| Thành phần | Mô tả |
| --- | --- |
| Khung thời gian hoạt động | <ul><li>Thời lượng: 24 giờ</li><li>Khoảng thời gian: 24 giờ là 1 khoảng thời gian</li></ul> |
| Doanh thu | <ul><li>Doanh thu được báo cáo bằng cách sử dụng một sự kiện trong ứng dụng (tổng thể)</li><li>Phạm vi doanh thu: 15</li></ul> |
| Trong ứng dụng | Không |
| Kênh | 3 sự kiện trong ứng dụng |

<div id="example-2" />

#### Ví dụ 2

| Thành phần | Mô tả |
| --- | --- |
| Khung thời gian hoạt động | <ul><li>Thời lượng: 24 giờ</li><li>Khoảng thời gian: 12 giờ là 2 khoảng thời gian</li></ul> |
| Doanh thu | <ul><li>Doanh thu được báo cáo phân bổ theo loại bằng cách sử dụng 2 sự kiện trong ứng dụng khác nhau</li><li>Phạm vi doanh thu: 3 (mỗi sự kiện trong ứng dụng)</li></ul> |
| Sự kiện trong ứng dụng được đặt để đo lượt chuyển đổi | 1 sự kiện trong ứng dụng để đo lường lượt chuyển đổi; mỗi sự kiện trong ứng dụng yêu cầu 1 phạm vi |
| Kênh | Không |

<div id="example-3" />

#### Ví dụ 3

| Thành phần | Mô tả |
| --- | --- |
| Khung thời gian hoạt động | <ul><li>Thời lượng: 24 giờ</li><li>Khoảng thời gian: 24 giờ là 1 khoảng thời gian</li></ul> |
| Doanh thu | <ul><li>Doanh thu được báo cáo bằng cách sử dụng một sự kiện trong ứng dụng (tổng thể)</li><li>Phạm vi doanh thu: 3</li></ul> |
| Sự kiện trong ứng dụng được đặt để đo mức độ thu hút | <ul><li>2 sự kiện trong ứng dụng để đo lường số lần xuất hiện tương tác</li><li>Phạm vi xuất hiện: 3 lần cho mỗi sự kiện trong ứng dụng</li></ul> |
| Kênh | Không |

<div id="example-4" />

#### Ví dụ 4

| Thành phần | Mô tả |
| --- | --- |
| Khung thời gian hoạt động | <ul><li>Thời lượng: 48 giờ</li><li>Khoảng thời gian: 12 giờ là 4 khoảng thời gian</li></ul> |
| Doanh thu | <ul><li>Doanh thu được báo cáo bằng cách sử dụng một sự kiện trong ứng dụng (tổng thể)</li><li>Phạm vi doanh thu: 7</li></ul> |
| Sự kiện trong ứng dụng được đặt để đo lượt chuyển đổi | 1 sự kiện trong ứng dụng để đo lường chuyển đổi; yêu cầu 1 phạm vi |
| Kênh | Không |

</Accordion>

<div id="priority-measurement-detailed-example" />

<Accordion title="Ví dụ chi tiết về đo lường ưu tiên">

Trong một ứng dụng mua sắm, nhà quảng cáo muốn tập trung đo lường:

* Hành động của người dùng **không thanh toán**
* Doanh thu của người dùng **thanh toán**

Bằng cách đó, nhà quảng cáo sử dụng CV để ghi nhận doanh thu một cách chính xác hơn. Các yêu cầu đo lường này chuyển thành một tập hợp các ưu tiên đo lường như được nêu trong bảng sau đây. 

Cân nhắc:

* Ưu tiên cao nhất luôn là ưu tiên 1. **Lưu ý**! Số ưu tiên không trực tiếp ánh xạ tới CV. Ánh xạ CV hiển thị trong giao diện người dùng.
* Số ưu tiên cao nhất là 63. Số thực tế có sẵn tùy thuộc vào khung thời gian hoạt động và nếu Nguồn dữ liệu tin cậy duy nhất được bật.
* Mỗi ưu tiên bao gồm phạm vi doanh thu hoặc phạm vi số lần xuất hiện sự kiện trong ứng dụng hoặc cả hai.
* Giá trị phạm vi: Giá trị thấp hơn của giới hạn không thuộc phạm vi nhưng giá trị giới hạn cao hơn lại thuộc phạm vi. Ví dụ: phạm vi 5 USD - 10 USD không bao gồm giá trị 5 nhưng bao gồm giá trị 10.

<div id="measurement-priorities-setting-example" />

#### Ví dụ về thiết lập các ưu tiên đo lường

<table><tbody><tr><th><p>Số Ưu tiên</p></th><th><p>Phạm vi doanh thu</p></th><th>Sự kiện trong Ứng dụng</th></tr><tr><td>1 [Ưu tiên cao nhất]</td><td>5 USD - 10 USD</td><td>send_recommendation</td></tr><tr><td>2</td><td>5 USD - 10 USD</td><td>--</td></tr><tr><td>3</td><td>0 USD - 5 USD</td><td>send_recommendation</td></tr><tr><td>4</td><td>0 USD - 5 USD</td><td>--</td></tr><tr><td>5</td><td>--</td><td>send_recommendation<br/>add_to_cart</td></tr><tr><td>6</td><td>--</td><td><p>send_recommendation</p></td></tr><tr><td>7 [Ưu tiên thấp nhất]</td><td>--</td><td>add_to_cart</td></tr><tr><td colspan="3">-- Không có giá trị được đặt</td></tr></tbody></table>

Bảng sau đây chứa các tình huống trong hành trình người dùng. Mỗi tình huống chứa một danh sách các hành động mà người dùng thực hiện trong suốt hành trình của họ và ưu tiên được AppsFlyer xác định.

Trong bảng:

* Hành động nhiều hơn một sẽ được phân tách bằng >
* Giá trị trong ngoặc đơn () là ưu tiên do AppsFlyer xác định được đặt sau khi người dùng hoàn thành hành động. Sử dụng ưu tiên mà AppsFlyer cập nhật CV trong ứng dụng.

<div id="user-journey-scenarios" />

#### Các tình huống trong hành trình của người dùng

| Tình huống trong hành trình của người dùng | Hành động của người dùng và ưu tiên |
| --- | --- |
| A | add\_to cart (7) |
| B | add\_to\_cart (7) > send\_recommendation (5) |
| C | Mua hàng trị giá 3 USD (4) |
| D | Mua hàng trị giá 6 USD (2) |
| E | Mua hàng trị giá 6 USD (2) > send\_recommendation (1) |

</Accordion>

<div id="fixed-mode-examples" />

<Accordion title="Ví dụ về chế độ cố định">

<div id="example-a-revenue-measurement" />

#### Ví dụ A: Đo lường doanh thu

| Yếu tố | Lưu ý |
| --- | --- |
| Tình huống | <ul><li>20 người dùng cài đặt ứng dụng và thực hiện các giao dịch mua sau:<ul><li>9 người dùng, mỗi người mua với giá $10</li><li>5 người dùng, mỗi người mua với giá $5</li><li>1 người dùng mua hàng với giá $1, tiếp đó là $3, rồi $5 và cuối cùng là $1. Tổng cộng là $10.</li></ul></li><li>Dữ liệu chi phí do API cung cấp từ mạng quảng cáo: $30</li></ul> |
| Cấu hình SKAN | <ul><li>Chọn loại đo lường: doanh thu</li><li>Đặt hệ số chuyển đổi: 1 đơn vị chuyển đổi = $1</li><li>Sự kiện chuyển đổi được chỉ định: Trong SDK, bạn phải gửi doanh thu bằng cách sử dụng thông số *af\_revenue*.</li></ul> |
| Các số liệu đã chọn | Các số liệu liên quan đến doanh thu có sẵn<ul><li>Số lượt cài đặt: 20</li><li>Doanh thu: $125</li><li>Số lượt chuyển đổi: 15</li><li>ARPU: $6,25</li><li>ROI: 316%</li></ul> |
| Số hàng dữ liệu thô trên mỗi báo cáo | <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports">Báo cáo dữ liệu thô có sẵn qua Data Locker</Anchor><ul><li>Đăng lại trên thiết bị: 20 hàng</li><li>Số lượt cài đặt: 20 hàng</li><li>Số sự kiện trong ứng dụng: 15 hàng. Lưu ý! Người dùng thực hiện nhiều giao dịch mua được biểu thị bằng một hàng duy nhất là $10.</li></ul> |
| Cân nhắc của nhà phát triển | Các sự kiện có doanh thu được ghi nhận |

<div id="example-b-conversion-measurement" />

#### Ví dụ B: Đo lường lượt chuyển đổi

<Table>
  <thead>
    <tr>
      <th>
        Yếu tố
      </th>
      <th>
        Lưu ý
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Ví dụ:
      </td>
      <td>
        * 5 người dùng (AE) cài đặt ứng dụng
        * Họ thực hiện 0-3 sự kiện khác nhau trong ứng dụng, như được mô tả trong bảng sau
        * Dữ liệu chi phí do API cung cấp từ mạng quảng cáo: $30

        <div id="inapp-events-performed-by-users" />

        #### Sự kiện trong ứng dụng do người dùng thực hiện

        |  | trong-ứng-dụng-1 | trong-ứng-dụng-2 | trong-ứng-dụng-3 |
        | --- | --- | --- | --- |
        | Người dùng A | Đã thực hiện | Đã thực hiện | - |
        | Người dùng B | Đã thực hiện | - | Đã thực hiện |
        | Người dùng C | Đã thực hiện | Đã thực hiện | - |
        | Người dùng D | Đã thực hiện | Đã thực hiện | - |
        | Người dùng E | - | - | - |
      </td>
    </tr>
    <tr>
      <td>
        Cấu hình Phân bổ SKAdNetwork
      </td>
      <td>
        Chọn loại đo lường: Chuyển đổi

        * Chọn các sự kiện trong ứng dụng: trong-ứng-dụng-1, trong-ứng-dụng-2, trong-ứng-dụng-3
        * Trong <Anchor target="_blank" href="/marketers/vi/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">bảng điều khiển</Anchor> SKAdNetwork, bạn chọn một trong các sự kiện để tính số liệu người dùng được chuyển đổi. Bạn có thể thay đổi sự kiện đã chọn nếu cần.
      </td>
    </tr>
    <tr>
      <td>
        Các số liệu đã chọn
      </td>
      <td>
        <div id="inapp-related-metrics-available" />

        #### Các số liệu liên quan trong ứng dụng có sẵn

        | Số liệu | Ứng dụng | trong-ứng-dụng-1 | trong-ứng-dụng -2 | trong-ứng-dụng -3 |
        | --- | --- | --- | --- | --- |
        | Lượt cài đặt | 5 |  |  |  |
        | Lượt chuyển đổi | 4 |  |  |  |
        | Người dùng duy nhất |  | 4 | 3 | 1 |
        | eCPA | $ 7,5 |  |  |  |

        **Lưu ý!** Vì Sự kiện Chuyển đổi được chỉ định là trong-ứng-dụng-1, nên giá trị 4 được sử dụng để tính toán các số liệu cấp ứng dụng và cho các số liệu trong-ứng-dụng-1.
      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports">Báo cáo dữ liệu thô có sẵn qua Data Locker</Anchor>

        * Đăng lại trên thiết bị: 5 hàng
        * Số lượt cài đặt: 5 hàng
        * Sự kiện trong ứng dụng: 8 hàng
      </td>
    </tr>
    <tr>
      <td>
        Cân nhắc của nhà phát triển
      </td>
      <td>
        * Đảm bảo bạn gửi các sự kiện trong ứng dụng mà người dùng thực hiện.
        * Giải pháp SKAdNetwork bỏ qua các giá trị sự kiện (ngoại trừ liên quan đến đo lường doanh thu.
      </td>
    </tr>
  </tbody>
</Table>

<div id="example-c-engagement-measurement" />

#### Ví dụ C: Đo lường mức độ thu hút

<Table>
  <thead>
    <tr>
      <th>
        Yếu tố
      </th>
      <th>
        Lưu ý
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Ví dụ:
      </td>
      <td>
        5 người dùng cài đặt ứng dụng và mở ứng dụng với số lần được liệt kê trong bảng.

        <div id="app-opens" />

        #### Ứng dụng mở ra

        |  | Số lần sự kiện được thực hiện |
        | --- | --- |
        | Người dùng A | 63 |
        | Người dùng B | 10 |
        | Người dùng C | 5 |
        | Người dùng D | 1 |
        | Người dùng E | - |
      </td>
    </tr>
    <tr>
      <td>
        Cấu hình Phân bổ SKAdNetwork
      </td>
      <td>
        * Chọn loại đo lường: Mức độ thu hút
        * Sự kiện chuyển đổi được chỉ định: af\_app\_opened Lưu ý! Bạn có thể sử dụng bất kỳ sự kiện có sẵn nào.
      </td>
    </tr>
    <tr>
      <td>
        Các số liệu đã chọn
      </td>
      <td>
        Các số liệu mẫu có sẵn

        * Số lượt cài đặt: 5
        * Số lượt chuyển đổi: 4
        * Số phiên: 79
      </td>
    </tr>
    <tr>
      <td>
        Số hàng dữ liệu thô trên mỗi báo cáo
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/vi/docs/skan-raw-data-reports">Báo cáo dữ liệu thô có sẵn qua Data Locker</Anchor>

        * Đăng lại trên thiết bị: 5 hàng
        * Số lượt cài đặt: 5 hàng
        * Sự kiện trong ứng dụng: 79 hàng; một hàng tương đương với một phiên duy nhất
      </td>
    </tr>
    <tr>
      <td>
        Cân nhắc của nhà phát triển
      </td>
      <td>
        Vào mỗi lần người dùng thực hiện sự kiện thu hút đã chọn: gửi sự kiện trong ứng dụng. SKAdNetwork đếm số lần bạn gửi sự kiện.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="skan-conversion-studio-api" />

<Accordion title="API SKAN Conversion Studio">

Nếu bạn có nhiều ứng dụng mà bạn muốn cấu hình giá trị chuyển đổi SKAN tương tự, thì việc thiết kế lược đồ cho từng ứng dụng riêng biệt trong Giao diện người dùng của Conversion Studio có thể sẽ tốn thời gian và khó khăn. Để tiết kiệm thời gian và công sức, bạn có thể cấu hình lược đồ SKAN của mình trong giao diện người dùng một lần, rồi sau đó sử dụng API SKAN Conversion Studio để sử dụng cùng lược đồ đó trong nhiều ứng dụng. **Lưu ý**: API chỉ hỗ trợ các lược đồ được cấu hình trong giao diện người dùng sử dụng SKAN 4 hoặc các chế độ đo lường tùy chỉnh (và trong các chế độ này, thành phần đo lường Dự đoán không được hỗ trợ.

**Để sử dụng API SKAN Conversion Studio**:

1. Nhận <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">mã thông báo API</Anchor>. Quản trị viên cần truy xuất mã thông báo.
2. Cung cấp cho nhà phát triển của bạn mã thông báo API cần dùng trong tiêu đề xác thực.
3. Cung cấp cho nhà phát triển của bạn ID ứng dụng của:
   * Ứng dụng mà lược đồ SKAN được cấu hình trong giao diện người dùng (có nghĩa là ứng dụng mà bạn muốn sao chép lược đồ SKAN).
   * Tất cả các ứng dụng mà bạn muốn có cùng một lược đồ.
4. Yêu cầu nhà phát triển của bạn làm theo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-studio-config-overview-1">hướng dẫn về API SKAN Conversion Studio</Anchor> của họ trong trung tâm nhà phát triển.

**Lưu ý**:

* Có thể sử dụng API để sao chép lược đồ vào một ứng dụng theo lệnh gọi API. Tuy nhiên, sau đó, nhà phát triển của bạn có thể tạo một tập lệnh để sao chép lược đồ cần thiết sang nhiều ứng dụng.
* API SKAN Conversion Studio không khả dụng đối với các đại lý.

</Accordion>

<div id="additional-procedures" />

## Các quy trình bổ sung

<div id="change-skan-measurement-mode" />

<Accordion title="Thay đổi chế độ đo lường SKAN">

Cân nhắc:

* Khi bạn bắt đầu sử dụng chế độ đo lường SKAN 4, bạn không thể đổi lại về chế độ trước đó.
* Khi bạn thực hiện thay đổi cài đặt, các thay đổi này sẽ bắt đầu có hiệu lực từ 00:00 sáng theo giờ UTC và khoảng thời gian chuyển tiếp bắt đầu. Trong khoảng thời gian này, chúng tôi sẽ giải mã giá trị chuyển đổi bằng các cài đặt mới chọn gần đây nhất. Tuy nhiên, một postback đang đến sẽ liên quan đến một lượt cài đặt đã xảy ra trong quá khứ.
* Số lượt cài đặt được báo cáo không liên quan đến thay đổi cài đặt và là giá trị chính xác.

</Accordion>

<div id="disable-skan-measurement" />

<Accordion title="Tắt chế độ đo lường SKAN">

Để tắt chế độ đo lường SKAdNetwork:

1. Trong AppsFlyer, đi tới **Configuration** (Cấu hình) > **SKAN Conversion Studio.**
2. Nhấp vào ⋮.
3. Tắt **SKAdNetwork measurement.**   
   Ngoài những thứ khác, SDK ngừng gọi các hàm SKAN như *registerAppForAdNetworkAttribution*, *updateConversionValue.*
4. Nhấp vào **Save changes** (Lưu thay đổi).

</Accordion>

<div id="report-events-by-servertoserver-api" />

<Accordion title="Báo cáo sự kiện bằng API từ máy chủ đến máy chủ">

![SKAdNetwork_-_S2S__2_.png](https://files.readme.io/ed55e5c10184afcc27ce7e414a3213f69d2c20bd70d38f78be338f1b17254ee2-16281446657937.png)

Cả SDK và <Anchor target="_blank" href="/marketers/vi/docs/server-to-server-events-api-for-mobile-s2s-mobile">API từ máy chủ đến máy chủ (S2S)</Anchor> đều có thể gửi các sự kiện trong ứng dụng đến máy chủ AppsFlyer. 

Quy trình S2S như sau:

* Một sự kiện xảy ra liên quan đến người dùng trong máy chủ của nhà quảng cáo. Ứng dụng có thể đang mở hoặc đóng tại thời điểm này.
* Máy chủ của nhà quảng cáo báo cáo sự kiện cho AppsFlyer bằng S2S.
* AppsFlyer tính toán giá trị chuyển đổi được cập nhật và sau đó: 
  * Nếu ứng dụng đang mở trên thiết bị người dùng: SDK sẽ được thông báo về giá trị được cập nhật. SDK cập nhật giá trị chuyển đổi iOS trên thiết bị.
  * Nếu ứng dụng không mở trên thiết bị người dùng: máy chủ đợi cho đến khi ứng dụng được mở để thông báo cho SDK về giá trị chuyển đổi. Điều này phải xảy ra trước khi Khung thời gian Hoạt động kết thúc. Nếu thông báo không thành công, sự kiện sẽ bị bỏ qua.

**Phiên bản SDK bắt buộc**

* Áp dụng phiên bản SDK mới nhất trong ứng dụng. **Lưu ý!** Nhà phát triển không cần thực hiện thêm bất kỳ hành động nào.

**Để triển khai tính năng gửi sự kiện trong ứng dụng bằng API từ máy chủ đến máy chủ:**

1. Thực hiện một trong những việc sau:
   * Nếu chế độ bạn chọn là SKAN 4 hoặc Tùy chỉnh:
     * Không cần thay đổi cài đặt.
   * Nếu chế độ bạn đã chọn là doanh thu, chuyển đổi hoặc thu hút:
     1. Trong AppsFlyer, đi tới **Configuration** (Cấu hình) > **SKAN Conversion Studio.**
     2. Nhấp vào tùy chọn (⋮).
     3. Bật **Record in-app events sent by server-to-server API**.
2. Gửi sự kiện bằng S2S.

**Mức giới hạn**

* Nếu bạn triển khai tính năng *ẩn danh người dùng* đối với một người dùng nhất định thì bạn không thể gửi sự kiện bằng S2S cho người dùng đó.

</Accordion>

<div id="add-ssot-to-fixed-mode-measurements" />

<Accordion title="Thêm SSOT vào các đo lường chế độ cố định">

Nếu bạn đã thiết lập chế độ đo lường Doanh thu hoặc Tương tác, thì Nguồn dữ liệu tin cậy duy nhất (SSOT, loại bỏ trùng lặp và báo cáo chính xác dữ liệu iOS), sẽ không được hỗ trợ. <Anchor target="_blank" href="/marketers/vi/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Tìm hiểu thêm về SSOT</Anchor>

**Để kích hoạt SSOT khi bạn đã cài đặt chế độ Doanh thu hoặc Lượt tương tác**:

1. Trong AppsFlyer, đi đến **Configuration** > **SKAN Conversion Studio**.
2. Cuộn xuống chế độ đo lường đang kích hoạt của bạn.
3. Nhấp vào **+ Add Single Source of Truth**.
   * Công tắc Nguồn dữ liệu tin cậy duy nhất được bật tự động.
   * Phạm vi đo lường trong chế độ cố định của bạn bị thay đổi tối thiểu để cho phép SSOT có một số chỗ dành cho giá trị chuyển đổi.
4. Nhấp vào **Save** (Lưu).

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Thông số và hạn chế">

| Thông số | Lưu ý |
| --- | --- |
| Đại lý | Các đại lý có <Anchor target="_blank" href="/partners/vi/docs/getting-started-agency-onboarding#access-to-skan-conversion-studio">quyền truy cập hạn chế vào SKAN Conversion Studio của nhà quảng cáo</Anchor>. |
| Giá trị thô | Tối đa 10 thành phần đo lường. |
| Sự kiện trong ứng dụng  <br /> tự nhiên | Trong SKAN 4, chế độ Tùy chỉnh và Giải mã, chỉ số tự nhiên cho các sự kiện trong ứng dụng và doanh thu tổng không có sẵn. |

</Accordion>

<div data-zendesk-anchors="skan-conversion-studio-basics=c%C3%A1c-kh%C3%A1i-ni%E1%BB%87m-c%C6%A1-b%E1%BA%A3n-v%E1%BB%81-skan-conversion-studio 01H7Z08MFDASBCBJD18QTXYSXK=c%C3%A1c-kh%C3%A1i-ni%E1%BB%87m-c%C6%A1-b%E1%BA%A3n-v%E1%BB%81-skan-conversion-studio 01H7Z08MFDX3VYJTSWXQ5HQ7BZ=measurement-principles-and-definitions s2s-principles=nguy%C3%AAn-t%E1%BA%AFc-s2s 01H7Z08MFDWRGVNXB62Z6CT1G7=nguy%C3%AAn-t%E1%BA%AFc-s2s setting-up-conversion-values-in-skan-conversion-studio=c%C3%A0i-%C4%91%E1%BA%B7t-gi%C3%A1-tr%E1%BB%8B-chuy%E1%BB%83n-%C4%91%E1%BB%95i-trong-skan-conversion-studio 01H7Z08MFDB76C6Z5SSXHFT71P=c%C3%A0i-%C4%91%E1%BA%B7t-gi%C3%A1-tr%E1%BB%8B-chuy%E1%BB%83n-%C4%91%E1%BB%95i-trong-skan-conversion-studio 01H7Z08MFDEAYHJAG9XA2TGBWV=quan-tr%E1%BB%8Dng 01H7Z08MFD7VY1QP85W0YPK8RC=skan-4 01H7Z08MFD3SWVZK68K45NYDP8=custom 01H7Z08MFDZ1EKDQNZWGF7DHK9=fixed-modes fixed-mode-measurement=%C4%91o-l%C6%B0%E1%BB%9Dng-%E1%BB%9F-ch%E1%BA%BF-%C4%91%E1%BB%99-c%E1%BB%91-%C4%91%E1%BB%8Bnh 01H7Z08MFDAYVJKJBT08R82N26=%C4%91o-l%C6%B0%E1%BB%9Dng-%E1%BB%9F-ch%E1%BA%BF-%C4%91%E1%BB%99-c%E1%BB%91-%C4%91%E1%BB%8Bnh 01H7Z08MFDCJGZGQR2JR4WQVHR=decode measurement-components=th%C3%A0nh-ph%E1%BA%A7n-%C4%91o-l%C6%B0%E1%BB%9Dng 01H7Z08MFDFE345QWHF77RGTD7=th%C3%A0nh-ph%E1%BA%A7n-%C4%91o-l%C6%B0%E1%BB%9Dng 01H7Z08MFE5G01NGY5EFTAW93M=single-source-of-truth 01H7Z08MFEZRQ9NA2KTJW0PSST=predict-component 01H7Z08MFERDJHSD8NT5KN7DKN=inapp-event-component 01H7Z08MFETMGAE67X499V4092=revenue-component 01H7Z08MFEQG2HRJBWBYFTW3ZK=funnel-component 01H7Z08MFE22J8DDBDNJ18KBEJ=priority-measurement-component 01H7Z08MFES844SS08HS17Y29R=lock-window 01H7Z08MFE61QCC0MZW5RJ910B=activity-window additional-information=th%C3%B4ng-tin-b%E1%BB%95-sung 01H7Z08MFET64PSAVMREQ4HP4S=th%C3%B4ng-tin-b%E1%BB%95-sung 01H7Z08MFEKP9WNGJD2GBVKB0P=view-cv-mapping csv-mapping-file-columns=c%C3%A1c-c%E1%BB%99t-t%E1%BB%87p-tin-%C3%A1nh-x%E1%BA%A1-csv 01H7Z08MFETCB428W1TXTH2HJ8=c%C3%A1c-c%E1%BB%99t-t%E1%BB%87p-tin-%C3%A1nh-x%E1%BA%A1-csv 01H7Z08MFE5CBQK024CF8FARJ9=conversion-value-capacity-formula 01H7Z08MFETZVQSNWX639E56SK=maximized-custom-cv-examples example-1=v%C3%AD-d%E1%BB%A5-1 01H7Z08MFEXME7RV67XTZRDWJE=v%C3%AD-d%E1%BB%A5-1 example-2=v%C3%AD-d%E1%BB%A5-2 01H7Z08MFEHRF4656X5AR301D8=v%C3%AD-d%E1%BB%A5-2 example-3=v%C3%AD-d%E1%BB%A5-3 01H7Z08MFEK0725CN35TP3MPYT=v%C3%AD-d%E1%BB%A5-3 example-4=v%C3%AD-d%E1%BB%A5-4 01H7Z08MFES7W3EF2JJ8B75K99=v%C3%AD-d%E1%BB%A5-4 01H7Z08MFF2JXA0BFNKCW3ZCZ7=priority-measurement-detailed-example measurement-priorities-setting-example=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-thi%E1%BA%BFt-l%E1%BA%ADp-c%C3%A1c-%C6%B0u-ti%C3%AAn-%C4%91o-l%C6%B0%E1%BB%9Dng 01H7Z08MFFXAAC37MBV0ES6ADQ=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-thi%E1%BA%BFt-l%E1%BA%ADp-c%C3%A1c-%C6%B0u-ti%C3%AAn-%C4%91o-l%C6%B0%E1%BB%9Dng user-journey-scenarios=c%C3%A1c-t%C3%ACnh-hu%E1%BB%91ng-trong-h%C3%A0nh-tr%C3%ACnh-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng 01H7Z08MFFJ9TQMH0Q93B7N1A8=c%C3%A1c-t%C3%ACnh-hu%E1%BB%91ng-trong-h%C3%A0nh-tr%C3%ACnh-c%E1%BB%A7a-ng%C6%B0%E1%BB%9Di-d%C3%B9ng 01H7Z08MFFNBXECB8A5Y0KH9C8=fixed-mode-examples example-a-revenue-measurement=v%C3%AD-d%E1%BB%A5-a-%C4%91o-l%C6%B0%E1%BB%9Dng-doanh-thu 01H7Z08MFFVKZN3Y2R1ZEVEW4D=v%C3%AD-d%E1%BB%A5-a-%C4%91o-l%C6%B0%E1%BB%9Dng-doanh-thu example-b-conversion-measurement=v%C3%AD-d%E1%BB%A5-b-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-chuy%E1%BB%83n-%C4%91%E1%BB%95i 01H7Z08MFFNBA5786R5XZDA5FG=v%C3%AD-d%E1%BB%A5-b-%C4%91o-l%C6%B0%E1%BB%9Dng-l%C6%B0%E1%BB%A3t-chuy%E1%BB%83n-%C4%91%E1%BB%95i inapp-events-performed-by-users=s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng-do-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-th%E1%BB%B1c-hi%E1%BB%87n 01H7Z08MFFA7C6HWQPADZXQQNC=s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng-do-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-th%E1%BB%B1c-hi%E1%BB%87n inapp-related-metrics-available=c%C3%A1c-s%E1%BB%91-li%E1%BB%87u-li%C3%AAn-quan-trong-%E1%BB%A9ng-d%E1%BB%A5ng-c%C3%B3-s%E1%BA%B5n 01H7Z08MFF1PEE91J5CJN1GC7V=c%C3%A1c-s%E1%BB%91-li%E1%BB%87u-li%C3%AAn-quan-trong-%E1%BB%A9ng-d%E1%BB%A5ng-c%C3%B3-s%E1%BA%B5n example-c-engagement-measurement=v%C3%AD-d%E1%BB%A5-c-%C4%91o-l%C6%B0%E1%BB%9Dng-m%E1%BB%A9c-%C4%91%E1%BB%99-thu-h%C3%BAt 01H7Z08MFF8V718C23PQ2NG3C3=v%C3%AD-d%E1%BB%A5-c-%C4%91o-l%C6%B0%E1%BB%9Dng-m%E1%BB%A9c-%C4%91%E1%BB%99-thu-h%C3%BAt app-opens=%E1%BB%A9ng-d%E1%BB%A5ng-m%E1%BB%9F-ra 01H7Z08MFF4PRHSR8NCJ1Q78WM=%E1%BB%A9ng-d%E1%BB%A5ng-m%E1%BB%9F-ra 01H7Z08MFFVS6MYC9EB3KP0H2Y=skan-conversion-studio-api additional-procedures=c%C3%A1c-quy-tr%C3%ACnh-b%E1%BB%95-sung 01H7Z08MFFPZ4GKM5GFMAE2HDJ=c%C3%A1c-quy-tr%C3%ACnh-b%E1%BB%95-sung 01H7Z08MFFPKCX5TFQQTMYJEGW=change-skan-measurement-mode 01H7Z08MFF78F9NMWJATYE2YFE=disable-skan-measurement 01H7Z08MFFD4T3D71A6R9K83A3=report-events-by-servertoserver-api 01H7Z08MFFFAEW6NP0YAX773B3=add-ssot-to-fixed-mode-measurements 01H7Z08MFFG9EQFVEKN3AXE9DD=specifications-and-limitations" />
