---
title: >-
  Bản tin: Hành động cần thiết—Nhận dữ liệu thô của Meta ads bằng cách sử dụng
  Liên kết giới thiệu Cài đặt Google
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-21T07:02:51Z'
  edited_at: '2023-11-30T14:24:36Z'
  id: 4409322107537
  locale: vi
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/vi/articles/4409322107537
---

<Table>
  <tbody>
    <tr>
      <td>
        **Tính năng mới**
      </td>
      <td>
        Nhận dữ liệu thô thuộc chiến dịch Meta ads của các quảng cáo hướng đến Google Play Store bằng cách sử dụng Liên kết giới thiệu Cài đặt.
      </td>
    </tr>
    <tr>
      <td>
        **Phần nào sẽ thay đổi**

        **![Information_icon.png](https://files.readme.io/cc1ff74668360a2be64ec90db8f771d751b0a95847ecaee582c2e31c60e310cf-20445036062993.png)**
      </td>
      <td>
        Bắt đầu từ ngày 29 tháng 10 năm 2021, dữ liệu phân bổ cấp người dùng (dữ liệu thô) của người dùng do Meta ads mang đến **sau** ngày này sẽ bị hạn chế. Meta ads cung cấp dữ liệu này cho các MMP như AppsFlyer, nhưng không cung cấp cho nhà quảng cáo.

        Tuy nhiên, nếu quảng cáo hướng người dùng đến Google Play Store, các trường phân bổ sẽ có sẵn cho nhà quảng cáo trong Liên kết giới thiệu Cài đặt Google. Trường này phải được <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">tích hợp vào ứng dụng của bạn.</Anchor> Các trường được cung cấp qua người giới thiệu sẽ nhập các báo cáo dữ liệu thô AppsFlyer được cung cấp cho bạn và cho phép AppsFlyer phân bổ người dùng không có ID quảng cáo (Bật LAT).

        Việc sử dụng cơ chế liên kết giới thiệu yêu cầu AppsFlyer SDK V5.4 trở lên

        **Lưu ý:** Dữ liệu liên kết giới thiệu được ưu tiên hơn dữ liệu do API cung cấp và không bị hạn chế.

        Dữ liệu trong liên kết giới thiệu được Meta ads mã hóa và được giải mã bằng cách sử dụng khóa được cung cấp cho bạn trong tài khoản nhà phát triển Meta ads. Bạn phải cung cấp cho chúng tôi khóa giải mã được mô tả trong hàng hành động cần thiết.

        **Các trường phân bổ chiến dịch được cung cấp qua người giới thiệu:**

        * ID Quảng cáo
        * Tên quảng cáo
        * ID Bộ quảng cáo
        * Tên bộ quảng cáo
        * ID Chiến dịch
        * Tên chiến dịch
        * ID tài khoản
        * Kênh
        * Loại quảng cáo (trường này chưa khả dụng)

        **Lưu ý**:

        * Không có trường nào khác có sẵn thông qua liên kết giới thiệu.
        * Giải pháp này áp dụng để phân bổ lượt nhấp qua và không áp dụng cho phân bổ lượt xem hết.
        * Dữ liệu liên kết giới thiệu không áp dụng cho các chiến dịch tương tác lại vì người dùng không đi qua cửa hàng.

        **Khi nào AppsFlyer sẽ triển khai thay đổi này?**

        * Bắt đầu từ ngày 29 tháng 10 năm 2021:
          * Các hạn chế của Meta ads đối với dữ liệu nhấp qua (nói cách khác là dữ liệu thô phân bổ) được triển khai.
          * Nhà quảng cáo có thể cập nhật khóa giải mã liên kết giới thiệu trong AppsFlyer.
        * Bắt đầu từ ngày 3 tháng 11 năm 2021:
          * AppsFlyer điền dữ liệu thô và phân bổ bằng cách sử dụng dữ liệu do cơ chế giới thiệu cung cấp.
      </td>
    </tr>
    <tr>
      <td>
        **Tóm tắt tính sẵn có của dữ liệu**
      </td>
      <td>
        <table><tbody><tr><th rowspan="2">Cách phân bổ</th><th rowspan="2">Nguồn dữ liệu phân bổ</th><th colspan="2">Dữ liệu có sẵn cho nhà quảng cáo </th><th>Lưu ý</th></tr><tr><th>Dữ liệu thô</th><th>Dữ liệu hợp nhất</th><th> </th></tr><tr><td>Lượt nhấp</td><td>Liên kết giới thiệu (áp dụng cho các ứng dụng Android được tải xuống từ Google Play Store)</td><td>Có sẵn</td><td>Có sẵn</td><td><ul><li>Dữ liệu phân bổ người dùng LAT có sẵn.</li><li>Liên kết giới thiệu được ưu tiên hơn dữ liệu MMP nếu cả hai đều có sẵn.</li><li>Không áp dụng cho các chiến dịch tương tác lại.</li></ul></td></tr><tr><td>Lượt nhấp</td><td>API MMP</td><td>Hạn chế\*</td><td>Có sẵn</td><td> </td></tr><tr><td>Lượt xem qua</td><td>API MMP</td><td>Hạn chế\*</td><td>Có sẵn</td><td>Cơ chế liên kết giới thiệu không được hỗ trợ.</td></tr><tr><td colspan="5"><p><strong>Lưu ý:</strong> Khi tính khả dụng của dữ liệu bị hạn chế:</p><ul><li><ul><li>Lượt cài đặt và đăng lại sự kiện trong ứng dụng chỉ được gửi đến các mạng quảng cáo hạn chế. Các đối tác bên thứ ba, chẳng hạn như đối tác phân tích, không nhận được phản hồi do hạn chế phân bổ. </li><li>Các lượt đăng lại không được phân bổ (không chứa trường phân bổ) được gửi đến các mạng quảng cáo đã được định cấu hình để nhận tất cả các sự kiện (bao gồm cả tự nhiên và không được phân bổ). Điều này bao gồm các đối tác quản lý chiến dịch Meta.</li></ul></li></ul></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        **Hành động cần thiết**
      </td>
      <td>
        **Để nhận khóa giải mã của bạn từ Meta ads:**

        [Thông tin sau đây dựa trên thông tin do Facebook cung cấp cho chúng tôi]

        1. Hãy đăng nhập vào cổng thông tin nhà phát triển Meta của bạn.
        2. Điều hướng đến **My Apps** ở góc trên bên phải.
        3. Chọn ứng dụng mà bạn muốn truy cập khóa giải mã của mình.
        4. Điều hướng đến **Settings** > **Basic** ở bên trái trang.

           [![FBUIforKey.png](https://files.readme.io/7581629ac17217154300bc796fd54416c1b04c08353b21ae7b93662fe182f694-4409669308049.png)](https://files.readme.io/7581629ac17217154300bc796fd54416c1b04c08353b21ae7b93662fe182f694-4409669308049.png)
        5. Cuộn xuống đến mục **Android** và bạn sẽ thấy khóa giải mã của mình được ghi nhãn **Install Referrer decryption key** bên dưới trường **Package Names**. **Lưu ý**: Đây là mục tương tự mà bạn đã cấu hình tên gói của mình và Google Play Store.

        **Để kích hoạt cơ chế liên kết giới thiệu trong AppsFlyer.**

        1. [Bắt buộc] Xác minh rằng ứng dụng của bạn đang sử dụng SDK AppsFlyer phiên bản 5.4 trở lên. Không phụ thuộc vào các phiên bản cũ hơn.
        2. Thực hiện một trong những việc sau:
           1. [Sắp ra mắt] Đặt khóa giải mã qua API.
           2. Để đặt khóa giải mã thông qua giao diện người dùng:
              1. Trong AppsFlyer, đi đến **Configuration** > **Active Integrations.**
              2. Chọn quảng cáo Meta.  

                 ![meta-ads-install-referrer-decryption-key.png](https://files.readme.io/adf6caa8d7cee493695eb8fb7db1b61c60e6a1cef0273e615c43a05ad8a9485d-13963525463825.png)
           3. Trong tab **Integration**, hãy dán khóa trong **Install Referrer** **Decryption Key**.
           4. Nhấp vào **Save integration** (Lưu tích hợp).
      </td>
    </tr>
    <tr>
      <td>
        **Cập nhật khóa giải mã qua API**
      </td>
      <td>
        **[Sắp ra mắt]**

        Chúng tôi sẽ phát hành API cập nhật khóa giải mã.
      </td>
    </tr>
    <tr>
      <td>
        **Tính sẵn có của dữ liệu thô trong tương lai**
      </td>
      <td>
        * Nếu dữ liệu phân bổ được lấy thông qua cơ chế liên kết giới thiệu thì dữ liệu đó không bị hạn chế và có sẵn thông qua báo cáo dữ liệu thô.
        * Nếu dữ liệu phân bổ được lấy qua API thì dữ liệu thô của người dùng do Meta ads mang lại sẽ được gán cho nguồn phương tiện *bị hạn chế*
        * Thay đổi này không ảnh hưởng đến dữ liệu thô của người dùng được cung cấp trước khi thay đổi. Nói cách khác là trước ngày 29 tháng 10 năm 2021, 08:00 UTC.
      </td>
    </tr>
    <tr>
      <td>
        **Phần nào sẽ vẫn giữ nguyên**
      </td>
      <td>
        AppsFlyer tiếp tục nhận dữ liệu cấp thiết bị từ Meta ads, có nghĩa là khả năng phân bổ và báo cáo của chúng ta (bao gồm phân bổ đa điểm chạm, LTV, ROI, nhóm người, báo cáo giữ chân người dùng, bảo vệ chống gian lận, Đối tượng và các dịch vụ khác) vẫn không thay đổi. Xem <Anchor target="_blank" href="/marketers/vi/docs/aggregated-and-analytics-reporting-overview">các công cụ báo cáo hợp nhất và phân tích</Anchor>.

        **Lưu ý**: Nếu bạn cung cấp cho chúng tôi khóa giải mã, chúng tôi có thể phân bổ những người dùng không có ID quảng cáo (bật LAT). Điều này cải thiện độ chính xác của phân bổ.
      </td>
    </tr>
    <tr>
      <td>
        **Thay đổi về phân bổ**
      </td>
      <td>
        Liên kết sâu bị trì hoãn qua GCD sẽ khả dụng cho các ứng dụng Android sử dụng cơ chế Liên kết giới thiệu Cài đặt Google. Tùy chọn này không có sẵn cho các ứng dụng iOS.
      </td>
    </tr>
    <tr>
      <td>
        **Câu hỏi thường gặp**
      </td>
      <td>
        * **Khóa giải mã liên kết giới thiệu cài đặt có cần được cập nhật không?**  
          Sau khi gửi, khóa giải mã không cần phải cập nhật.
        * **Khi nào tôi có thể xem dữ liệu cấp người dùng trong báo cáo dữ liệu thô?**  
          Dữ liệu cấp người dùng được hiển thị trong báo cáo ngày thô sau khi khóa giải mã liên kết giới thiệu cài đặt hợp lệ được gửi và lượt cài đặt được tính cho Meta ads.
        * **Dữ liệu phân bổ cấp người dùng có sẵn cho các lượt cài đặt xảy ra trong khoảng thời gian từ ngày 29 tháng 10 năm 2021 đến ngày 3 tháng 11 năm 2021 không?**  
          Rất tiếc là dữ liệu này không có sẵn.
      </td>
    </tr>
  </tbody>
</Table>
