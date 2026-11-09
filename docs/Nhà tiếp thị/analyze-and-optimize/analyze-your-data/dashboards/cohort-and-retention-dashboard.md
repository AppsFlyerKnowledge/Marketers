---
title: Bảng điều khiển nhóm người
metadata:
  keywords:
    - Cohort
    - Cohort Report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2015-12-24T10:20:01Z'
  edited_at: '2023-11-02T10:24:06Z'
  id: 207040496
  locale: vi
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/vi/articles/207040496
---
> **Khái quát**: Bảng điều khiển nhóm người sẽ nhóm người dùng ứng dụng theo ngày thu hút. Thực hiện phân tích hiệu suất trong vòng đời của người dùng. Sử dụng bảng điều khiển để hiểu rõ hơn về việc sự khác biệt của chiến dịch thay đổi các số liệu của chiến dịch như thế nào.

**Doanh thu theo ngày sau cài đặt được chia ra theo nguồn truyền thông**

<Image align="center" alt="Full_cohort2_us-en.png" src="https://files.readme.io/b60e18dcd68ca4b1831c56b69ad667931ca52610a456f8612f44d4fac51150f6-14583921567377.png" />

<div id="tip" />

<div id="cohort-and-retention-dashboard" />

## Bảng điều khiển nhóm người

Để sử dụng Nhóm người, hãy chọn người dùng từ một hoặc nhiều ứng dụng và tạo phân khúc theo thời gian chuyển đổi. Có sẵn các số liệu nhóm người như doanh thu, ROI và tỷ lệ chuyển đổi sự kiện. Chia nhỏ nhóm người, cho mục đích so sánh, thành các phương diện như chiến dịch hoặc nguồn truyền thông. Điều này có thể giúp biết rõ được các dạng hoặc thay đổi về hiệu suất của người dùng hoặc chu kỳ hoạt động của chiến dịch. Xem phần <Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">Các trường hợp sử dụng theo nhóm người</Anchor>.

> 👍 **Mách nhỏ**
>
> Bạn muốn biết thêm về các báo cáo nhóm người? Hãy xem khóa học ngắn, bổ ích này trên <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7804/play/18625/your-users-journey-with-retention-and-cohort-reports">Cổng thông tin Học tập AppsFlyer</Anchor>.

<div id="cohort-principles" />

<div id="view-types" />

<Accordion title="Nguyên tắc nhóm người">

<Image align="center" alt="OV.png" src="https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png" />

* **Loại nhóm người**
  * **Thống nhất**:
    * Hiệu suất kết hợp của các chiến dịch thu hút người dùng và nhắm mục tiêu lại (bao gồm cả chi phí và doanh thu).
    * Nếu một sự kiện được phân bổ cho cả hai loại lượt chuyển đổi, thì chỉ sự kiện nhắm mục tiêu lại được bao gồm. Có nghĩa là, báo cáo được tạo bằng cách sử dụng nguồn truyền thông tương tác cuối cùng thực tế. Nếu bạn đã quen với dữ liệu thô, nó có nghĩa là các sự kiện trong đó <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor>.
  * **Thu hút người dùng:** dữ liệu hiệu suất từ lượt cài đặt (không bao gồm cài đặt lại trừ khi <Anchor target="_blank" href="/marketers/vi/docs/measure-reinstalls#attributed-to-the-first-install">được bật riêng</Anchor>)
  * **Nhắm mục tiêu lại:** dữ liệu về hiệu suất từ các lượt phân bổ lại hoặc thu hút lại
* **Loại xu hướng**
  * **Hiệu suất vòng đời của người dùng:** Người dùng được nhóm theo **thời gian** chuyển đổi. Chức năng này cho phép bạn so sánh hiệu suất sau chuyển đổi của người dùng, bắt đầu từ ngày chuyển đổi, được gọi là ngày nhóm người 0. Nhóm người bỏ qua giờ sự kiện và chỉ sử dụng ngày sự kiện. Xu hướng này thường được sử dụng để đánh giá hiệu suất của người dùng so với nguồn truyền thông.
    * Đối với độ chi tiết của giờ, số giờ tối đa là 72.
    * Đối với độ chi tiết theo ngày, số ngày tối đa là 180.
    * Đối với độ chi tiết theo tuần, số tuần tối đa là 156
    * Đối với độ chi tiết theo tháng, số tháng tối đa là 36

* * **KPI theo thời gian phân bổ:** Người dùng được nhóm theo **thời gian** chuyển đổi. Điều này cho phép bạn đánh giá hiệu suất chiến dịch theo thời gian và xem KPI của chiến dịch liên quan đến thời gian chuyển đổi.
* **Các số liệu liên quan đến chi phí:** Dữ liệu chi phí trong Nhóm người chỉ được đưa vào nếu có một phân bổ liên quan (lượt cài đặt, lượt thu hút lại hoặc phân bổ lại). Nói cách khác, nếu một chiến dịch phát sinh chi phí dựa trên lượt nhấp và lượt hiển thị nhưng không có lượt phân bổ thì chi phí đó sẽ không được đưa vào báo cáo nhóm người. Nguyên tắc này đúng với tất cả các cấp trong hệ thống phân cấp quảng cáo.
* **Tùy chọn mức độ chi tiết**

| Loại mức độ chi tiết | Thời gian cho phép | Nhận xét |
| --- | --- | --- |
| Ngày | Chọn 1–60 ngày |  |
| Giờ | Chọn 1–72 giờ trong số 72 giờ trước đó | Các số liệu liên quan đến chi phí không có sẵn |
| Tuần | Lên đến 26 tuần |  |
| Tháng | Lên đến 12 tháng |  |

</Accordion>

<div id="example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend" />

<Accordion title="Ví dụ: Xu hướng hiệu suất vòng đời của người dùng so với KPI theo xu hướng thời gian phân bổ">

Trong ví dụ này, cùng một dữ liệu thô được sử dụng để tạo ra hai loại xu hướng nhóm người. Bảng dữ liệu thô chứa các sự kiện phân bổ liên quan đến những người dùng khác nhau A, B, C và D. Người dùng tương tác với cùng một quảng cáo, cài đặt ứng dụng và hậu chuyển đổi đã thực hiện một hoặc nhiều giao dịch mua. Ngày nhóm người 0 là ngày cài đặt.

<Image align="center" alt="CohortExample_en-us.jpg" src="https://files.readme.io/7542605e2bb3972dc90fb12c9d6a328ff52ec65f0694a79752380d548e72e286-32127949500817.jpg" />

</Accordion>

<div id="metrics-available" />

<Accordion title="Các số liệu có sẵn">

<table><thead><tr><th> </th><th> </th><th colspan="6">Hàm</th></tr><tr><th rowspan="2">Luôn luôn/ Tùy chọn </th><th rowspan="2"><p>Số liệu</p></th><th>Số đếm</th><th>cvr (tỷ lệ chuyển đổi)</th><th>Xếp hạng</th><th>Tổng</th><th>Người dùng duy nhất</th><th>eCPA</th></tr><tr><th>Số</th><th>Tỷ lệ phần trăm</th><th>Tỷ lệ phần trăm</th><th>Số</th><th>Số</th><th>Số</th></tr></thead><tbody><tr><td>Luôn luôn</td><td>Người dùng (4)</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td><td><span>-</span></td><td><span>-</span></td></tr><tr><td>Luôn luôn</td><td>Chi phí (3)</td><td><span>-</span></td><td><span>-</span></td><td>-</td><td><span>✓</span></td><td>-</td><td><span>-</span></td></tr><tr><td>Luôn luôn</td><td>eCPI trung bình</td><td><span>-</span></td><td><span>-</span></td><td><span>✓</span></td><td><span>-</span></td><td><span>-</span></td><td><span>-</span></td></tr><tr><td>Tùy chọn</td><td><code>"event_name"</code></td><td> </td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td> <span>✓</span><span><span>(5)</span></span> </td></tr><tr><td>Tùy chọn</td><td>Doanh thu</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td><span>-</span></td></tr><tr><td>Tùy chọn</td><td>ROAS (3)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td></tr><tr><td>Tùy chọn</td><td>ROI (3)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td></tr><tr><td>Tùy chọn</td><td>Phiên (2)</td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td><td> <span>✓</span><span>(1)</span> </td><td><span><span>-</span></span></td></tr><tr><td>Tùy chọn</td><td>Lượt gỡ cài đặt (3)</td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td><td><span>-</span></td></tr></tbody><tfoot><tr><td colspan="8"><p>(1) Các phiên độc nhất trả về khi aggregation_type=on_day<br/>(2) Các phiên nhắm mục tiêu lại (thu hút lại và phân bổ lại) có sẵn cho các phiên diễn ra bắt đầu từ ngày 13 tháng 7 năm 2020. Điều này có nghĩa là các phiên diễn ra cho đến ngày 12 tháng 7 năm 2020 sẽ không được hiển thị. <br/>(3) Không áp dụng trong các trường hợp sau:</p><ul><li>Dạng xem được thống nhất</li><li>Mức độ chi tiết tính theo giờ. Được tính toán hàng ngày theo giờ UTC. </li></ul><p>(4) Số liệu <em>Người dùng</em> tính số lượt phân bổ (lượt cài đặt, thu hút lại, phân bổ lại) diễn ra trong khoảng thời gian đã chọn.   </p><p>(5) Chi phí hiệu quả trên mỗi hành động (eCPA): Chi phí / Số lượng người dùng duy nhất tích lũy thực hiện sự kiện.</p></td></tr></tfoot></table>

</Accordion>

<div id="trend-types" />

<div id="cohort-periods" />

<div id="kpi-by-attribution-time" />

<div id="user-lifetime-performance" />

<div id="cohort-concepts" />

<div id="using-cohort" />

## Sử dụng Nhóm người

<div id="setting-up-an-analysis" />

<Accordion title="Thiết lập phân tích">

1. Đi tới **Dashboard** (Bảng điều khiển) > **Cohort** (Nhóm người).  
   Bảng điều khiển Nhóm người sẽ mở ra. Mức độ chi tiết và phạm vi ngày chuyển đổi được hiển thị.  
   <Image align="center" alt="mceclip0__1_.png" src="https://files.readme.io/4113fd619422979d6a26004a55c009ebc48eef59d10ddc7c3e5becd2a758e6d4-32127949494417.png" />
2. Chọn mức độ chi tiết.
3. Đặt khoảng thời gian phân bổ (thu hút người dùng hoặc thu hút nhắm mục tiêu lại). Dữ liệu liên quan đến các ngày gần đây nhất có thể dẫn đến [dữ liệu không hoàn chỉnh](/docs/cohort-and-retention-dashboard#partial-data) được biểu thị bằng dấu gạch ngang trong biểu đồ và bảng.
4. Nhấp vào **Edit Cohort** (Chỉnh sửa Nhóm người).  
   Cửa sổ thiết lập Nhóm người sẽ mở ra.  

   <Image align="center" alt="CohortSetup.jpg" src="https://files.readme.io/f09cc190770d16a2ddf60e1f210f458114ac43d4c19fc5507fb50b0d1d2f5c77-32127949495825.jpg" width="365px" />
5. Hoàn thành các trường sau:
   * **Loại nhóm người:**
     * **Thu hút người dùng**
     * **Nhắm mục tiêu lại**
     * **Thống nhất:** bao gồm các sự kiện trong ứng dụng của cả phân bổ người dùng và phân bổ nhắm mục tiêu lại. **Lưu ý**: sự kiện nhắm mục tiêu lại được ưu tiên hơn so với sự kiện thu hút người dùng, nghĩa là báo cáo có chứa các sự kiện trong đó <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor>.
   * Chọn loại Xu hướng:
     * **Hiệu suất vòng đời của người dùng**.
     * **KPI theo thời gian phân bổ**.
   * **Người dùng ứng dụng**: Chọn 1–nhiều hoặc **tất cả** (nghĩa là 100 ứng dụng đứng đầu trong tài khoản của bạn). **Lưu ý**: Đại lý chỉ có thể chọn một ứng dụng.
   * **Nhóm theo**: Chọn một hoặc nhiều [phương diện](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) [Mặc định: Nguồn Truyền thông].
   * **Quy mô nhóm người tối thiểu**: Đặt quy mô nhóm người tối thiểu. Điều này tránh làm lộn xộn báo cáo của bạn với các nhóm người (nhỏ) không đáng kể. [Mặc định=1]
   * Các trường tùy chọn:
     * **Filtered by** (Lọc theo): Chọn một hoặc nhiều [phương diện](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) để lọc. Không có bộ lọc mặc định.
6. Nhấp vào **Apply changes** (Áp dụng thay đổi).  
   Báo cáo sẽ hiển thị.
7. Để hoàn thành thiết lập nhóm người, hãy hoàn thành một trong các quy trình loại xu hướng sau đây.
8. [Tùy chọn] [Quản lý báo cáo nhóm người đã lưu](/docs/cohort-and-retention-dashboard#using-my-reports-save-and-select-reports).

</Accordion>

<div id="trend-type-user-lifetime-performance" />

<Accordion title="Kiểu xu hướng—Hiệu suất vòng đời của người dùng">

Người dùng được nhóm thành các nhóm người theo **ngày** sau chuyển đổi. Ngày chuyển đổi được gọi là ngày sau chuyển đổi 0. Tiếp theo là ngày sau chuyển đổi 1, v.v.

* Đối với độ chi tiết theo ngày, số ngày tối đa là 180.
* Đối với độ chi tiết theo tuần, số tuần tối đa là 156
* Đối với độ chi tiết theo tháng, số tháng tối đa là 36

<Image align="center" alt="DaysPost.jpg" src="https://files.readme.io/dbeb30f800b198ea0ce2c7b69f2d3652f54384630dab9e8e77a7960a3d9471fb-360005455377.jpg" />

* **Chọn số liệu, hàm và mỗi người dùng**: **Lưu ý:** Không phải tất cả các giá trị kết hợp số liệu, hàm và mỗi người dùng đều có sẵn.
  * Số liệu: Doanh thu, <Anchor target="_blank" href="/marketers/vi/docs/measure-sessions">Phiên</Anchor>, Lượt gỡ cài đặt, ROI, Sự kiện trong ứng dụng, ROAS.
  * Hàm: Số liệu được tính bằng các hàm. Danh sách hàm khác nhau tùy thuộc vào số liệu.
    * **Sum** (Tổng): tổng doanh thu vào một ngày của nhóm người.
    * **Count** (Số lượng): số sự kiện. Ví dụ: số phiên, số sự kiện doanh thu, số lượt gỡ cài đặt, v.v.
    * **Unique users** (Người dùng duy nhất): số lượng người dùng duy nhất đã thực hiện một sự kiện. Điều đó có nghĩa là, ví dụ, nếu người dùng mở ứng dụng 10 lần vào một ngày cụ thể thì kết quả hiển thị sẽ là 1.
    * **Chuyển đổi trong ứng dụng**: tỷ lệ chuyển đổi từ cài đặt/nhắm mục tiêu lại sang sự kiện trong ứng dụng. Số lượng người dùng duy nhất thực hiện một sự kiện cụ thể trong ứng dụng **lần đầu** **được** chia cho số lượng người dùng duy nhất trong nhóm người. Ví dụ: số người dùng [duy nhất] trong một nhóm người là 100. Trong số này, 20 người lần đầu tiên thực hiện một sự kiện trong ứng dụng cụ thể. Tỷ lệ chuyển đổi trong ứng dụng là 20/100=20%.
  * **Mỗi người dùng**: khi được chọn, tổng hoặc số đếm được chia cho số người dùng ứng dụng.
* **Thời gian hiển thị**: Số ngày nhóm người hiển thị sau chuyển đổi. Ngày 0 là ngày chuyển đổi, Ngày 1 là ngày sau chuyển đổi, v.v. Lưu ý: Thời gian hiển thị bị rút ngắn nếu kết quả là một ngày trong tương lai.
* **Bảng** hoặc **Biểu đồ:**
  * Biểu đồ hiển thị top 5 hoặc 10 được xếp hạng theo số lượng người dùng ứng dụng trong nhóm người. Bất kể phương diện được hiển thị.
  * Bảng hiển thị lên đến 50 hàng. Người dùng, chi phí và ecpi (chi phí hiệu quả trên mỗi lượt cài đặt) trung bình luôn hiển thị bất kể số liệu được chọn là gì.
* **Theo ngày** hoặc **Tích lũy**:
  * On day nghĩa là giá trị của số liệu dành riêng cho ngày đó.
  * On day không cung cấp các số liệu liên quan đến Chi phí.
  * Cumulative (Tích lũy) có nghĩa là tổng tích lũy hoặc tổng lũy kế của số liệu. Lưu ý! Trong trường hợp số liệu người dùng duy nhất, thuật ngữ này có nghĩa là số lượng người dùng duy nhất đã thực hiện một sự kiện nhất định cho đến một ngày nhóm người nhất định. Đây không phải là tổng số người dùng duy nhất của những ngày trước đó.

</Accordion>

<div id="trend-type-kpi-by-attribution-time" />

<Accordion title="Kiểu xu hướng—KPI theo thời gian phân bổ">

Người dùng được nhóm thành các nhóm người theo **thời gian phân bổ.**

<Image align="center" alt="KPIdays.jpg" src="https://files.readme.io/dfac4a4f84aad39d6526cdb416e8a2ec6c9e95dd6a2ca06e3c7fd10d31b76272-360005458837.jpg" />

* **Chọn số liệu, hàm, ngày KPI và mỗi người dùng**:   
  **Lưu ý:** Không phải tất cả các giá trị kết hợp số liệu, hàm và mỗi người dùng đều có sẵn.
  * Số liệu: Doanh thu, Phiên (không có sẵn trong chế độ xem thống nhất), Lượt gỡ cài đặt, ROI, Sự kiện trong ứng dụng, ROAS.
  * Hàm: Số liệu được tính bằng các hàm. Danh sách hàm khác nhau tùy thuộc vào số liệu.
    * **Sum** (Tổng): tổng doanh thu vào một ngày của nhóm người.
    * **Số đếm**
    * **Unique users** (Người dùng duy nhất): số lượng người dùng duy nhất đã thực hiện một sự kiện. Điều đó có nghĩa là, ví dụ, nếu người dùng mở ứng dụng 10 lần vào một ngày cụ thể thì kết quả hiển thị sẽ là 1.
    * **Chuyển đổi trong ứng dụng**: tỷ lệ chuyển đổi từ cài đặt/nhắm mục tiêu lại sang sự kiện trong ứng dụng. Số lượng người dùng duy nhất thực hiện một sự kiện cụ thể trong ứng dụng **lần đầu** **được** chia cho số lượng người dùng duy nhất trong nhóm người. Ví dụ: số người dùng [duy nhất] trong một nhóm người là 100. Trong số này, 20 người lần đầu tiên thực hiện một sự kiện trong ứng dụng cụ thể. Tỷ lệ chuyển đổi trong ứng dụng là 20/100=20%.
  * **Thời gian phân bổ KPI:** Chọn từ Ngày 0, Ngày 3, Ngày 7, v.v. Ngày 0 phải là ngày chuyển đổi. Ngày 3 là ngày chuyển đổi cộng ba ngày tiếp theo, tổng là bốn ngày; diễn giải tương tự cho các ngày còn lại. Giá trị KPI được tính tổng cho khoảng thời gian được chọn.
  * **Mỗi người dùng**: khi được chọn, tổng hoặc số đếm được chia cho số người dùng ứng dụng.
  * **Bảng** hoặc **Biểu đồ:** Biểu đồ hiển thị top 5 hoặc top 10 được xếp hạng theo số lượng người dùng ứng dụng trong nhóm người. Ở đây không tính đến phương diện được hiển thị trong biểu đồ. Bảng hiển thị lên đến 50 hàng.
  * **Vào ngày:** Giá trị chỉ vào Ngày nhóm người được chỉ định. Ví dụ: Trong trường hợp của Ngày 7, điều này có nghĩa là giá trị vào ngày 7 sau chuyển đổi.
  * **Tích lũy** trong đó: Giá trị kết hợp của tất cả các ngày được chỉ định trong Ngày. Ví dụ: trong trường hợp của Ngày 7, điều này có nghĩa là tổng số ngày chuyển đổi và 7 ngày tiếp theo.  Lưu ý! Trong bối cảnh của người dùng độc nhất, nó có nghĩa là số lượng người dùng tích lũy độc nhất.

</Accordion>

<div id="list-of-dimensions-for-grouping-and-filtering" />

<Accordion title="Danh sách các phương diện nhóm và lọc">

| Phương diện | Nhận xét | Nhóm theo | Lọc theo |
| --- | --- | --- | --- |
| <span id="ad"></span>Quảng cáo |  | ✓ | ✓ |
| <span id="ad-id"></span>ID Quảng cáo |  | ✓ | ✓ |
| <span id="adset"></span>Bộ quảng cáo |  | ✓ | ✓ |
| <span id="adset-id"></span>ID Bộ quảng cáo |  | ✓ | ✓ |
| <span id="agency"></span>Đại lý |  | ✓ | ✓ |
| <span id="apps"></span>Ứng dụng | Có liên quan khi báo cáo chứa nhiều ứng dụng | ✓ | **x** |
| <span id="attributed-touchtype"></span>Kiểu tương tác được phân bổ | Giá trị: Lượt nhấp, hiển thị hoặc NA (tự nhiên) | ✓ | ✓ |
| <span id="campaign"></span>Chiến dịch |  | ✓ | ✓ |
| <span id="campaign-id"></span>ID Chiến dịch |  | ✓ | ✓ |
| <span id="channel"></span>Kênh |  | ✓ | ✓ |
| <span id="conversion-type"></span>Loại chuyển đổi | Giá trị phụ thuộc theo loại nhóm người:<ul><li>**Thu hút người dùng**: Cài đặt</li><li>**Nhắm mục tiêu lại**: Thu hút lại, phân bổ lại</li></ul> | ✓ | ✓ |
| <span id="country-geo"></span>Quốc gia (Địa lý) | Dựa trên địa chỉ IP của người dùng | ✓ | ✓ |
| <span id="time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year"></span>Thời gian. Trong trường hợp:<ul><li>Độ chi tiết hàng ngày là ngày</li><li>Độ chi tiết hàng giờ là giờ trong ngày</li><li>Độ chi tiết hàng tuần là tuần trong năm</li><li>Độ chi tiết hàng tháng là tháng trong năm</li></ul> | Giá trị phụ thuộc theo loại nhóm người:<ul><li>**Thu hút người dùng và thống nhất**: Thời gian ứng dụng được khởi chạy lần đầu.</li><li>**Nhắm mục tiêu lại**: Thời gian ứng dụng được khởi chạy lần đầu sau khi thu hút lại.</li></ul> | ✓ | **x** |
| <span id="install-app-store"></span>Cài đặt App Store | Thích hợp với các ứng dụng triển khai <Anchor target="_blank" href="/marketers/vi/docs/set-up-multi-store-android-attribution">phân bổ nhiều cửa hàng Android.</Anchor> Liên hệ với CSM của bạn để kích hoạt phương diện này. | ✓ | ✓ |
| <span id="keywords"></span>Từ khóa | Từ khóa tìm kiếm được đối tác tích hợp cung cấp | ✓ | ✓ |
| <span id="media-source"></span>Nguồn truyền thông |  | ✓ | ✓ |
| <span id="revenue-type"></span>Loại Doanh thu | Thường xuyên, kiếm tiền từ quảng cáo | **x** | ✓ |
| <span id="site-id"></span>ID trang |  | ✓ | ✓ |
| <span id="sub-param-1"></span>Thông số phụ 1 |  | ✓ | ✓ |

</Accordion>

<div id="using-my-reports-save-and-select-reports" />

<Accordion title="Sử dụng Báo cáo của tôi—Lưu và chọn báo cáo">

* Báo cáo của tôi cho phép bạn lưu cài đặt bảng điều khiển hiện tại để sử dụng trong tương lai.
* Chọn một báo cáo đã lưu để hiển thị dữ liệu nhóm người mới nhất sẵn có.
* Bạn có thể lưu một hoặc nhiều báo cáo.
* Chỉ bạn mới có thể truy cập My reports (Báo cáo của tôi).

| Tính năng | Mô tả |
| --- | --- |
| Báo cáo của tôi | ![MyReports.png](https://files.readme.io/8f49c0e6dee55427bf3a64149ac48f67547967b8cd24aa8de3e34b760708f992-32127933340305.png)<br /><br />Chọn một báo cáo để hiển thị dữ liệu mới nhất hiện có. |
| Lưu thay đổi | Lưu báo cáo. Lưu ý: Báo cáo hiện đang được chọn sẽ bị ghi đè. |
| Tùy chọn hành động (![Elipse.png](https://files.readme.io/14b74dc6e733867bd16b6a3594f5f0856d7437462b2e0cf7c12adf11cfa295b3-32127949499409.png)) | <ul><li>**Lưu như mới**<ul><li>Lưu báo cáo bằng một tên báo cáo khác</li><li>[Tùy chọn] Đặt báo cáo này thành báo cáo mặc định</li></ul></li><li>**Rename** (Đặt làm mặc định): Thay đổi tên báo cáo</li><li>**Set as default** (Đặt làm mặc định): Đặt báo cáo làm báo cáo mặc định. Khi bạn mở Nhóm người, đây là báo cáo hiển thị ban đầu</li><li>**Delete**: Xóa báo cáo</li></ul> |

</Accordion>

<div id="partial-data" />

<Accordion title="Dữ liệu không hoàn chỉnh">

Sử dụng nút điều khiển **Nhóm người theo thời gian thực** để chọn chế độ hiển thị dữ liệu:

* [Mặc định] **Thời gian thực:**
  * Dữ liệu phân bổ được cập nhật liên tục theo thời gian thực bao gồm cả doanh thu.
  * Dữ liệu chi phí cập nhật trung bình 6 lần một ngày sau mỗi bốn giờ.
  * Bao gồm dữ liệu không hoàn chỉnh (được biểu thị bằng dấu gạch ngang trong báo cáo và biểu đồ)
* **Hàng ngày:** Dữ liệu được cập nhật hàng ngày và có sẵn vài phút sau nửa đêm. Dữ liệu của các ngày không hoàn chỉnh sẽ không hiển thị.

Dữ liệu không hoàn chỉnh là gì?

Đối với một ngày cụ thể trong phạm vi dữ liệu chuyển đổi, nếu số ngày đã trôi qua kể từ ngày chuyển đổi nhỏ hơn ngày nhóm người, thì ngày nhóm người đó chứa dữ liệu không hoàn chỉnh. Nghĩa là dữ liệu không hoàn chỉnh xảy ra vào bất kỳ ngày nào nếu ngày nhóm người &lt; ngày hiện tại - ngày chuyển đổi.

</Accordion>

<div id="export-the-cohort-to-a-csv-file" />

<Accordion title="Xuất nhóm người sang tệp tin CSV">

* Có thể xuất báo cáo nhóm người sang tệp tin CSV.
* Tệp tin CSV được giới hạn tối đa 10.000 hàng.
* Hàm xuất CSV được giới hạn trong các báo cáo **Hiệu suất vòng đời của người dùng** .
* Tên cột có hậu tố [một phần tương đương với dấu gạch ngang hiển thị trong biểu đồ và bảng ở giao diện người dùng.](/docs/cohort-and-retention-dashboard#partial-data)

**Để xuất báo cáo nhóm người sang tệp tin CSV:**

* Ở phía trên bên phải của cửa sổ báo cáo Nhóm người, nhấp vào <Image alt="Download.png" src="https://files.readme.io/50af9c6cde00dada58a1bb89a9eb3e566f316c0e7336af68f4ce403584047a5b-32127933341969.png" width="21px" />(export [xuất]).  
   Tệp tin CSV báo cáo nhóm người được tải xuống.

</Accordion>

<div id="additional-information" />

## Thông tin

<div id="cohort-for-agencies" />

<Accordion title="Nhóm người cho các đại lý">

* Nhà quảng cáo cần cấp cho đại lý quyền để sử dụng Nhóm người.
  * Để cấp quyền cho một đại lý, nhà quảng cáo:
    * Đi đến **Configuration** > **Active Integrations.**
    * Chọn đại lý.
    * Chuyển đến tab quyền, bật **Allow access to your retention and cohort reports** (Cho phép truy cập vào báo cáo giữ lại người dùng và nhóm người của bạn).
* Đại lý chỉ được truy cập dữ liệu về lưu lượng truy cập do đại lý tạo ra. Họ không thể xem dữ liệu liên quan đến lưu lượng truy cập tự nhiên hoặc lưu lượng truy cập không tự nhiên do người khác tạo ra.

</Accordion>

<div id="use-cases" />

<Accordion title="Các trường hợp sử dụng">

<div id="revenue-sum-by-geo" />

#### Tổng doanh thu theo quốc gia

**Biểu đồ: Doanh thu tích lũy trên mỗi người dùng**

<Image align="center" alt="CohortGraph.png" src="https://files.readme.io/1142844a9312498e4fc229502cbdf86d46bd61007d62837d38ba1b66fb2e00aa-360003206697.png" />

**Bảng: Doanh thu mỗi ngày**

<Image align="center" alt="CohortTable.png" src="https://files.readme.io/9181e589fc99e48e360fe9361b15fd59ec498b9fa99c31b43e6832aac25376da-360003206717.png" />

<div id="in-app-event-conversion" />

#### Chuyển đổi sự kiện trong ứng dụng

Nhà quảng cáo định nghĩa một sự kiện trong ứng dụng af\_purchase. Biểu đồ nhóm người hiển thị tỷ lệ phần trăm người dùng ứng dụng trong nhóm người đã mua hàng trên thiết bị di động. Ví dụ: chúng ta có thể thấy vào ngày 10 có gần 30% (11,11%+9.71%+7,47%) trong số những người dùng thuộc nhóm người đã thực hiện mua hàng trên thiết bị di động

[.![Nhóm người trong ứng dụng](https://files.readme.io/e365c6b930d765d97155b1fd4384a608cb7eb0339b2b61e4598ee2d5d17d3249-32127949502481.png)](https://files.readme.io/e365c6b930d765d97155b1fd4384a608cb7eb0339b2b61e4598ee2d5d17d3249-32127949502481.png)

</Accordion>

<div id="faq" />

<Accordion title="Câu hỏi thường gặp">

| Câu hỏi | Câu trả lời |
| --- | --- |
| <span id="can-i-view-apple-search-ads-keyword-cost-and-roi"></span>Tôi có thể xem <Anchor target="_blank" href="/marketers/vi/docs/apple-ads-integration-setup#analyze-keyword-cost">Chi phí và ROI của từ khóa</Anchor> trên Apple Search Ads không? | Có, bạn có thể.  <br />Apple Search Ads cung cấp cho chúng tôi chi phí cho mỗi từ khóa mỗi ngày được chia ra theo Chiến dịch/Bộ quảng cáo/Quảng cáo. **Lưu ý:** Không hỗ trợ phân tích theo Địa lý/quốc gia. |
| <span id="for-a-given-media-source-why-does-the-same-campaign-name-display-more-than-once"></span>Đối với một nguồn truyền thông nhất định, tại sao cùng một tên chiến dịch lại hiển thị nhiều lần? | <ul><li>Nếu bạn sử dụng một tên chiến dịch với các chiến dịch có ID chiến dịch khác nhau thì tên đó sẽ hiển thị nhiều lần.</li><li>Bạn nên phân bổ tên duy nhất ID chiến dịch</li><li>Khi thay đổi tên chiến dịch, dữ liệu được điều chỉnh theo tên được sử dụng lần cuối cùng.</li></ul> |
| <span id="can-i-view-organic-users"></span>Tôi có thể xem người dùng tự nhiên không? | Người dùng tự nhiên, theo mặc định, được đưa vào trong báo cáo Nhóm người.<br /><br />**Để giới hạn báo cáo Nhóm người chỉ cho người dùng tự nhiên:**<ol><li>Trong **Bảng điều khiển Nhóm người**, hãy nhấp vào nút **Edit cohort** (Chỉnh sửa nhóm người).</li><li>Trong cửa sổ thiết lập Nhóm người, hãy đặt **Filter by** (Lọc theo) > **Media source** (Nguồn truyền thông) là **Organic** (Tự nhiên):</li></ol>[![cohort_setup_filtered_by_media_source_is_organic.png](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)<ol><li>Nhấp vào **Apply changes** (Áp dụng thay đổi)</li></ol> |
| <span id="can-i-see-data-from-deleted-installs"></span>Tôi có thể xem dữ liệu từ các lượt cài đặt đã xóa không? | Không xem được các lượt cài đặt đã xóa, chẳng hạn như các lượt cài đặt từ SRN đã bị xóa do chính sách lưu trữ dữ liệu hoặc các lượt cài đặt đã xóa theo GDPR, trong bảng điều khiển nhóm người.<br /><br />Để biết thêm thông tin chi tiết, <Anchor target="_blank" href="/marketers/vi/docs/user-level-data-retention#partner-data-retention-periods">nhấp vào đây.</Anchor> |
| <span id="can-i-compare-data-for-daily-view-to-data-in-weekly-or-monthly-views"></span>Tôi có thể so sánh dữ liệu ở chế độ xem hàng ngày với dữ liệu ở chế độ xem hàng tuần hoặc hàng tháng không? | Không dễ để so sánh dữ liệu từ mức độ chi tiết hàng ngày với mức độ chi tiết hàng tuần hoặc hàng tháng, bởi vì LTV của nhóm người không phù hợp. <br /><br />Khi xem các nhóm người ở mức độ chi tiết hàng ngày, **Ngày 0** hiển thị dữ liệu của ngày cài đặt. Ngày 1 là ngày sau ngày cài đặt, Ngày 2 là 2 ngày sau ngày cài đặt, v.v. <br /><br />Khi xem các nhóm người ở mức độ chi tiết hàng tuần, dữ liệu sẽ hiển thị tất cả các lượt cài đặt được thực hiện trong **cả Tuần 0**. Tuần 1 là tuần sau tuần cài đặt, Tuần 2 là 2 tuần sau tuần cài đặt, v.v. <br /><br />Khi xem các nhóm người ở mức độ chi tiết hàng tháng, dữ liệu sẽ hiển thị tất cả các lượt cài đặt được thực hiện trong **cả Tháng 0**. Tháng 1 là tháng sau tháng cài đặt, Tháng 2 là 2 tháng sau tháng cài đặt, v.v. <br /><br />Điều này có nghĩa là dòng thời gian của LTV không phù hợp. Ví dụ như bạn xem dữ liệu từ ngày 9-15 tháng 1: Nếu bạn sử dụng mức độ chi tiết hàng ngày, **Ngày 0** chứa dữ liệu ngày đầu tiên của tất cả **các lượt cài đặt được thực hiện từ ngày 9-15 tháng 1.** Và **Ngày 6** chứa dữ liệu trong 6 ngày đầu tiên sau ngày cài đặt của tất cả các lượt cài đặt được thực hiện **từ ngày 9-15 tháng 1**. Trong khi đó, ở **mức độ chi tiết hàng tuần**, **Tuần 0** chứa dữ liệu của **toàn bộ khoảng thời gian** cho tất cả các lượt cài đặt **được thực hiện từ ngày 9-15 tháng 1**. Vì vậy, đối với các lượt cài đặt được thực hiện vào **ngày 9 tháng 1**, dữ liệu giống **Ngày 6**. Nhưng đối với các lượt cài đặt được thực hiện vào **ngày 15 tháng 1**, dữ liệu giống **Ngày 0**. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Đặc điểm và hạn chế">

| Đặc điểm | Nhận xét |
| --- | --- |
| Mạng quảng cáo truy cập vào Nhóm người | Không có sẵn |
| Truy cập đại lý | Có sẵn:<ul><li>Giới hạn chỉ một ứng dụng.</li><li>Tài khoản kết hợp không thể truy cập Nhóm người.</li><li>Yêu cầu quyền truy cập đối với từng ứng dụng.</li><li>Không thể chọn nhiều ứng dụng.</li><li>Không thể truy cập dữ liệu tự nhiên.</li></ul> |
| Tính minh bạch của agency | Có sẵn từ ngày 10 tháng 1 năm 2021 |
| Múi giờ riêng cho ứng dụng | <ul><li>Có sẵn</li><li>Ngoại lệ: Trong tất cả các trường hợp sau, AppsFlyer bỏ qua múi giờ riêng cho ứng dụng và sử dụng múi giờ mặc định là UTC +0:<ul><li>Báo cáo nhóm người chứa dữ liệu từ nhiều ứng dụng và các ứng dụng có nhiều múi giờ khác nhau.</li><li>Tất cả các ứng dụng có cùng múi giờ và múi giờ cho ít nhất một trong số các ứng dụng đã thay đổi trong khoảng thời gian báo cáo nhóm người. Để xác định thời gian báo cáo:<ul><li>Ngày bắt đầu: Ngày đầu tiên trong phạm vi ngày chuyển đổi</li><li>Ngày kết thúc: Được tính bằng cách cộng số ngày của khoảng thời gian hiển thị với ngày cuối cùng trong phạm vi ngày chuyển đổi. Ví dụ: Ngày cuối cùng: ngày 1 tháng 1 năm 2019. Khoảng thời gian báo cáo: 30 ngày. Ngày kết thúc: ngày 31 tháng 1 năm 2019</li></ul></li><li>Dữ liệu hàng tuần và hàng tháng sẽ được hiển thị theo giờ UTC</li></ul></li></ul> |
| Tiền tệ dành riêng cho ứng dụng | <ul><li>Có sẵn</li><li>Ngoại lệ: Tất cả các ứng dụng cần sử dụng cùng loại tiền tệ. Nếu không, đồng USD sẽ được sử dụng.</li></ul> |
| Điểm hạn chế | <ul><li>Tệp tin tải xuống CSV:<ul><li>Tối đa 10.000 hàng.</li><li>Không khả dụng cho KPI theo xu hướng thời gian phân bổ.</li></ul></li><li>Biểu đồ: hiển thị 5 hoặc 10 hàng được sắp xếp theo số lượng người dùng nhiều nhất trong nhóm người.</li><li>Bảng: Hiển thị 50 hàng đầu tiên được sắp xếp theo số lượng người dùng trong nhóm người.</li><li>Lượt cài đặt lại: Nếu cân nhắc đến các sự kiện sau cài đặt lại. Lượt cài đặt lại tự nhiên không phân bổ sẽ không nằm trong Nhóm người. Nếu được phân bổ cho lượt cài đặt đầu tiên, chúng sẽ được tính. <Anchor target="_blank" href="/marketers/vi/docs/measure-reinstalls#sự-kiện-trong-ứng-dụng-và-cách-chúng-được-phân-bổ">Tìm hiểu thêm</Anchor></li><li>Chi phí: AppsFlyer không báo cáo dữ liệu chi phí cho các từ khóa chứa chữ hoa trong báo cáo nhóm người hoặc API nhóm người.</li><li>Giới hạn 10 tệp xuất CSV/phút và 100 phút/ngày (mỗi người dùng).</li><li>Giới hạn 20 truy vấn dữ liệu/phút và 500 phút/ngày (mỗi người dùng). Thay đổi khoảng thời gian, gộp nhóm, KPI, v.v. được coi là truy vấn mới.</li></ul> |
| Dữ liệu tự nhiên | Đã bao gồm |
| Dữ liệu không tự nhiên | Đã bao gồm |
| Độ mới của dữ liệu | <ul><li><Anchor target="_blank" href="/marketers/vi/docs/about-data-freshness-and-timezone-support#eod">Thời gian thực</Anchor></li><li>Ngoại lệ:<ul><li>Nhóm người hàng ngày:<ul><li>Cập nhật hàng ngày số liệu chi phí, doanh thu quảng cáo và lượt gỡ cài đặt.</li><li>Số lượt gỡ cài đặt được tính một lần mỗi ngày bằng đồng hồ UTC.</li></ul></li><li>Nhóm người hàng tuần và hàng tháng:<ul><li>Dữ liệu thời gian thực không có sẵn. Dữ liệu sẽ chỉ hiển thị sau khi được hoàn thành (nghĩa là vào cuối tuần hoặc tháng).<br />Tuy nhiên, dữ liệu khi một phần dữ liệu cài đặt đã hoàn thành, ví dụ như khi một số dữ liệu đã hoàn thành (sau thời gian cài đặt) và một số khác chưa bắt đầu, sẽ được hiển thị.</li></ul></li></ul></li></ul> |
| Dữ liệu lịch sử | <ul><li>Nhóm người hàng ngày: 2 năm</li><li>Nhóm người hàng tuần/hàng tháng: 3 năm</li></ul> |
| Địa lý/quốc gia | <ul><li>Có sẵn</li><li>Nếu địa lý là không xác định (N/A), dữ liệu doanh thu quảng cáo sẽ không hiển thị khi nhóm theo địa lý.</li></ul> |
| Số phiên | Số phiên cho Ngày 0 trong chế độ xem Nhắm mục tiêu lại có thể thấp hơn số lượng người dùng.<br />Có một vài lý do dẫn đến điều này. Lý do phổ biến nhất là:<ul><li>Phiên thu hút lại đã được phân bổ trước khi ghi nhận lượt thu hút lại. Trong trường hợp này, lượt thu hút lại sẽ không được phân bổ cho phiên nhắm mục tiêu lại</li><li>Lọc theo các cài đặt khác, chẳng hạn như **Thời gian tối thiểu giữa các phiên**. Trong trường hợp này, lượt thu hút lại được ghi nhận. Tuy nhiên, các phiên được lọc và sẽ không được ghi nhận</li></ul> |
| Dữ liệu Nhắm mục tiêu lại và Dữ liệu Hợp nhất | Dữ liệu phiên hàng tháng chỉ có sẵn từ ngày đầu tiên của tháng 9 năm 2021 trở đi |
| Doanh thu Quảng cáo | <ul><li>Không khả dụng khi xem nhóm người với mức độ chi tiết theo giờ.</li><li>Có thể có sự không nhất quán giữa số tiền doanh thu quảng cáo được hiển thị trong bảng điều khiển Nhóm người và Tổng quan. Điều này xảy ra khi các mạng báo cáo doanh thu theo giờ UTC, trong khi các ứng dụng có cài đặt múi giờ khác.</li><li>Đối với sự kiện af\_ad\_revenue, số liệu người dùng duy nhất không khả dụng khi loại dữ liệu hợp nhất là:<ul><li>"Cumulative".</li><li>"On day" cho các ngày từ ngày 5 tháng 10 năm 2022 đến ngày 16 tháng 2 năm 2023.</li></ul></li></ul> |
| Tính chi tiết tuần và tháng | <ul><li>Tính chi tiết tuần và tháng chỉ có sẵn trên bảng điều khiển Nhóm người.</li><li>Các phép đo **người dùng duy nhất** và **tỷ lệ chuyển đổi** không có sẵn nếu dữ liệu bao gồm lượt cài đặt từ trước tháng 11 năm 2022.</li><li>Các phép đo liên quan đến chi phí không có sẵn khi gộp nhóm theo Tuần hoặc Tháng. Các thông số này bao gồm:</li></ul><ul><li>Chi phí</li><li>eCPI</li><li>ROI</li><li>ROAS</li></ul><ul><li>Dữ liệu lịch sử chỉ có sẵn từ năm 2021 trở đi.</li></ul> |
| Giai đoạn nhóm người | <ul><li>Giai đoạn chuyển đổi được gọi là 0 (Giờ 0, Ngày 0, Tuần 0 hoặc Tháng 0). Giai đoạn tiếp theo sau chuyển đổi được gọi là 1 (Giờ 1, Ngày 1, Tuần 1 hoặc Tháng 1), v.v.</li><li>Trong AppsFlyer, giai đoạn thuần tập không tính đến nhãn thời gian lượt cài đặt cụ thể. Thay vào đó, số giờ của nhóm người được làm tròn xuống giờ gần nhất và ngày, tuần và tháng của nhóm người được dựa trên ngày, tuần hoặc tháng theo lịch. Điều này có thể gây ra sự khác biệt khi so sánh dữ liệu nhóm người AppsFlyer với dữ liệu nhóm người của các mạng khác, trong đó tất cả khoảng thời gian của nhóm người được xác định theo nhãn thời gian cài đặt cụ thể (có nghĩa là một giờ là nhãn thời gian sau khi cài đặt 60 phút, một ngày là nhãn thời gian sau khi cài đặt khoảng thời gian 24 giờ sau cài đặt, v.v.).</li></ul> |

</Accordion>

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/aggregated-and-analytics-reporting-overview#cohort-flavors">Điểm khác biệt giữa các biến thể của Nhóm người</Anchor>

<div data-zendesk-anchors="cohort-dashboard=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-nh%C3%B3m-ng%C6%B0%E1%BB%9Di 01H7WE9R0CX9C2MQHNK1MB15AM=b%E1%BA%A3ng-%C4%91i%E1%BB%81u-khi%E1%BB%83n-nh%C3%B3m-ng%C6%B0%E1%BB%9Di 01H7WE9R0DSQ4E0WTXPTF43S08=m%C3%A1ch-nh%E1%BB%8F 01H7WE9R0D15RA4F3ZN6Y1Q30N=cohort-principles 01H7WE9R0DJA1ZNDR265WEWVKH=example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend 01H7WE9R0DTNKK17Y0XXZQRXD0=metrics-available using-cohort=s%E1%BB%AD-d%E1%BB%A5ng-nh%C3%B3m-ng%C6%B0%E1%BB%9Di 01H7WE9R0DZDRBYYCM3ACSHXMS=s%E1%BB%AD-d%E1%BB%A5ng-nh%C3%B3m-ng%C6%B0%E1%BB%9Di 01H7WE9R0DRV7CENP28NB0TNDK=setting-up-an-analysis trend-type%E2%80%94user-lifetime-performance=trend-type-user-lifetime-performance 01H7WE9R0D76VN0K95BF3ZBTH6=trend-type-user-lifetime-performance trend-type%E2%80%94kpi-by-attribution-time=trend-type-kpi-by-attribution-time 01H7WE9R0DN3ZPVTDGJ72QWEV0=trend-type-kpi-by-attribution-time 01H7WE9R0DSFAXSK2C1BBSJJCC=list-of-dimensions-for-grouping-and-filtering time-in-the-case-of%0A%0Adaily-granularity-is-the-date%0Ahourly-granularity-is-the-hour-of-the-day%0Aweekly-granularity-is-the-week-of-the-year%0Amonthly-granularity-is-the-month-of-the-year=time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year using-my-reports%E2%80%94save-and-select-reports=using-my-reports-save-and-select-reports 01H7WE9R0ERMN0ZNN1RDBD7SYA=using-my-reports-save-and-select-reports 01H7WE9R0E6BPEKRQKAMZVD12Y=partial-data 01H7WE9R0EMP5YPK4RSF06PP3B=export-the-cohort-to-a-csv-file information=th%C3%B4ng-tin 01H7WE9R0ETQW8WCRW8Q2NSNFF=th%C3%B4ng-tin 01H7WE9R0E8JHK7J4RZB50TAHE=cohort-for-agencies 01H7WE9R0E153RM1BE5BWZ7XEE=use-cases revenue-sum-by-country=t%E1%BB%95ng-doanh-thu-theo-qu%E1%BB%91c-gia 01H7WE9R0FNZC0QWNDNCR1CKH2=t%E1%BB%95ng-doanh-thu-theo-qu%E1%BB%91c-gia inapp-event-conversion=chuy%E1%BB%83n-%C4%91%E1%BB%95i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H7WE9R0FC8BV8F2STR6P9J3M=chuy%E1%BB%83n-%C4%91%E1%BB%95i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H7WE9R0FYH0CMQ3E6KMT5EKH=faq 01H7WE9R0F4GZ3WA21N1YF4AAG=traits-and-limitations h_01HE0CSHCJRXXG8WXRBHCWN7AC=xem-th%C3%AAm" />
