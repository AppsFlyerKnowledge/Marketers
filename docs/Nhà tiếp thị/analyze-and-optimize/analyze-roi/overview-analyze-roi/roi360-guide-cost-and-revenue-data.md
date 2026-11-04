---
title: ROI360—dữ liệu chi phí và doanh thu
metadata:
  keywords:
    - cost
    - Advertisers
    - Premium
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-11-10T13:52:03Z'
  edited_at: '2023-04-02T14:40:02Z'
  id: 10515748254609
  locale: vi
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/vi/articles/10515748254609
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sơ lược**: Nhận dữ liệu chi phí và doanh thu để hiểu tổng ROI và ROAS của bạn.

![M_emptyState.png](https://files.readme.io/5eec5be77bf0b72afdd95b1957642cc67ba509000bc756ac68d87da5e96ed08e-11832563913489.png)

<div id="overview" />

## Tổng quan

ROI360 là một bộ công cụ báo cáo chi phí và doanh thu độc đáo cung cấp cho bạn dữ liệu chính xác nhất trong thời gian nhanh nhất có thể.

Với thông tin chi tiết về chi phí và doanh thu tổng hợp, bạn sẽ có được thông tin tổng quan đầy đủ về lợi tức trên chi tiêu quảng cáo (ROAS) và lợi tức đầu tư (ROI) của mình.

<div id="cost-tools" />

### Công cụ tính chi phí

Trước đây được gọi là Xpend, công cụ tính chi phí ROI360 tổng hợp và báo cáo dữ liệu chi phí. Bộ công cụ và tính năng chi phí đày đủ được nêu trong bảng sau. Nhấp vào liên kết này để tìm hiểu thêm về từng tính năng.

<table><thead><tr><th>Công cụ</th><th>Mô tả</th></tr></thead><tbody><tr><td><a href="./roi360-cost-aggregation-overview" target="_blank">Chi phí phân bổ</a></td><td><p><span>Dữ liệu chi phí có liên quan đến sự phân bổ, số lượt truy cập và số lần hiển thị ở mức tiết nhất hiện có.</span></p><p><span>Trong đó bao gồm quyền truy cập vào hơn 80 tích hợp API, cho phép bạn dễ dàng kết nối với các mạng quảng cáo toàn cầu hoặc địa phương.</span></p></td></tr><tr><td><a href="./import-cost-data" target="_blank">Nhập tệp tin</a></td><td><p><span>Nhập chi tiêu quảng cáo để ghi lại dữ liệu chi phí không nhận được qua API.</span></p></td></tr><tr><td><a href="./incorporate-agency-fees-into-campaign-costs" target="_blank">Phí đại lý</a></td><td><p><span>Tính toán phí đại lý được bao gồm trong chi phí của bạn.</span></p></td></tr><tr><td><a href="./set-up-and-use-roi360-cost-etl-reports" target="_blank">ETL Chi phí\*</a></td><td><span>Cung cấp dữ liệu chi phí chiến dịch, được cập nhật 4 lần mỗi ngày, vào bộ chứa AWS S3 hoặc GCS của bạn để sẵn sàng tải vào hệ thống BI của nhà quảng cáo.</span></td></tr><tr><td colspan="2"><span>\* Có sẵn với gói ROI360 nâng cao</span></td></tr></tbody></table>

**Lưu ý**: Bạn cũng có thể tổng hợp <Anchor target="_blank" href="/marketers/vi/docs/view-aggregated-cost-data-for-attribution-links">dữ liệu chi phí theo lượt truy cập</Anchor> mà không cần ROI360. Tuy nhiên, phương pháp này chỉ dành cho mô hình chi phí CPI, không dành cho các mô hình khác như CPA, CPC và CPM.

<div id="revenue-tools" />

### Công cụ tính doanh thu

Công cụ tính doanh thu ROI360 tổng hợp và báo cáo dữ liệu doanh thu, cân nhắc mua hàng trong ứng dụng, đăng ký và doanh thu quảng cáo. Thuế và hoa hồng từ cửa hàng ứng dụng cũng được bao gồm trong số liệu doanh thu. Bộ công cụ và tính năng tính doanh thu đầy đủ được nêu trong bảng sau. Nhấp vào các liên kết để tìm hiểu thêm về từng tính năng.

<table><thead><tr><th>Công cụ</th><th>Mô tả</th></tr></thead><tbody><tr><td>Mua hàng trong ứng dụng</td><td><p><span>Tự động báo cáo các giao dịch mua hàng trong ứng dụng đã được xác thực, bao gồm dữ liệu cho các giao dịch tiếp theo như hoàn tiền hoặc hủy bỏ.</span></p></td></tr><tr><td>Doanh thu đăng ký</td><td><p><span>Tự động báo cáo các đăng ký, bao gồm các thay đổi, hủy bỏ và chia sẻ trong gia đình.</span></p></td></tr><tr><td><a href="./roi360-guide-ad-revenue-attribution" target="_blank">Doanh thu quảng cáo</a></td><td><p>Truy cập hơn 20 đối tác doanh thu quảng cáo kết nối qua API hoặc SDK mang lại độ chính xác cao và dữ liệu cập nhật.</p></td></tr><tr><td>[Sắp ra mắt] ETL Doanh thu\*</td><td><span>Cung cấp dữ liệu doanh thu vào bộ chứa AWS S3 hoặc GCS của bạn để sẵn sàng tải vào hệ thống BI của nhà quảng cáo.</span></td></tr><tr><td colspan="2"><span>\* Có sẵn với gói ROI360 nâng cao</span></td></tr></tbody></table>

**Lưu ý**: Cũng có một số công cụ tính toán doanh thu cơ bản không có trong ROI360. Khác với các công cụ có trong ROI360, các công cụ này yêu cầu nhà phát triển của bạn phải thực hiện một vài cấu hình đáng kể:

* <Anchor target="_blank" href="/marketers/vi/docs/legacy-receipt-validation-for-in-app-purchases">Xác thực biên lai mua hàng trong ứng dụng</Anchor>
* Tính toán doanh thu đăng ký
* <Anchor target="_blank" href="/marketers/vi/docs/roi360-revenue-attribution-overview">Ghi lại doanh thu qua sự kiện trong ứng dụng tùy chỉnh</Anchor>

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan cost-tools=c%C3%B4ng-c%E1%BB%A5-t%C3%ADnh-chi-ph%C3%AD revenue-tools=c%C3%B4ng-c%E1%BB%A5-t%C3%ADnh-doanh-thu" />
