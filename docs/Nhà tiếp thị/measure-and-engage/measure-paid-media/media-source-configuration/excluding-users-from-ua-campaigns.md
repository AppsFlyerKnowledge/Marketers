---
title: Loại trừ người dùng khỏi chiến dịch UA
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2020-05-03T10:11:31Z'
  edited_at: '2021-03-27T23:41:09Z'
  id: 360007949158
  locale: vi
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/vi/articles/360007949158
---
> **Khái quát:** Loại trừ người dùng hiện có khỏi chiến dịch thu hút người dùng (UA) để có được nhiều lượt cài đặt hơn với cùng ngân sách và cải thiện ROAS.

## Vấn đề và hậu quả

Nếu ứng dụng của bạn nhận được lưu lượng truy cập từ nhiều nguồn truyền thông thì những nguồn này có thể nhắm mục tiêu vào người dùng hiện có của bạn trong các chiến dịch UA của nguồn đó.

Hiệu suất chiến dịch có thể bị ảnh hưởng vì những lý do sau:

| Thanh toán gấp đôi | Trả tiền cho các lượt hiển thị/nhấp mà bạn đã trả trước đó. |
| --- | --- |
| Sai lệch tỷ lệ chuyển đổi | Các chiến dịch UA dường như kém thành công hơn. Số lượt cài đặt ít hơn do lượt hiển thị bị lãng phí cho người dùng hiện có. |
| Mất người dùng thay thế | Những người không phải người sử dụng có thể đã xem quảng cáo và trở thành người dùng di động của bạn. |

<Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#what-is-srn-mistargeting">Nhắm sai mục tiêu SRN</Anchor> là một vấn đề tương tự và rất phổ biến về hiệu suất. Vấn đề quan trọng này có thể xảy ra nếu cả chiến dịch UA và nhắm mục tiêu lại của bạn đều có cùng SRN. <Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns#việc-nhắm-sai-mục-tiêu-có-phải-là-vấn-đề">Tìm hiểu thêm</Anchor>

## Giải pháp

Các giải pháp này đưa ra cách cập nhật mạng quảng cáo để loại trừ người dùng hiện có khỏi các chiến dịch UA.

### Cập nhật thủ công

Thu thập dữ liệu thô về lượt cài đặt cấp người dùng của bạn từ AppsFlyer để xây dựng danh sách ID thiết bị. Sau đó, gửi danh sách này đến các mạng quảng cáo để đảm bảo việc loại trừ người dùng.

Để thêm dữ liệu thô này vào hệ thống BI của bạn, có một số cách sau:

* Tải xuống báo cáo dữ liệu thô
* Sử dụng Yêu cầu API Pull dữ liệu thô định kỳ
* Sử dụng API Push để tiến hành thu thập theo thời gian thực
* Nhận dữ liệu chuyển đổi từ SDK

> 📘 **Lưu ý**
>
> Trong khoảng thời gian từ lúc gửi thủ công danh sách tiếp theo đến các mạng quảng cáo, các chiến dịch UA có thể nhắm mục tiêu vào người dùng ứng dụng mới nhất của bạn.

### AUDIENCES

**<Anchor target="_blank" href="/marketers/vi/docs/audiences-guide">Đối tượng</Anchor>** là một tính năng cao cấp của AppsFlyer. Mỗi ngày, các phân đoạn được chọn của cơ sở người dùng của bạn sẽ được gửi tự động đến nhiều mạng quảng cáo do bạn chọn.

**Đối tượng** rất hữu ích trong việc duy trì danh sách loại trừ:

| Ít tốn sức | Bạn hoặc mạng quảng cáo không bắt buộc phải thực hiện công tác phát triển hoặc bảo trì. |
| --- | --- |
| Thân thiện với người dùng | Sau khi thực hiện thiết lập ngắn ban đầu, bạn có thể bắt đầu tải lên đối tượng. |
| Hiệu quả | Các phân đoạn được gửi tự động đến các mạng quảng cáo cứ sau mỗi 24 giờ. |