---
title: 'Bản tin: Thay đổi mã thông báo API'
metadata:
  keywords:
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2023-01-23T15:35:25Z'
  edited_at: '2023-10-02T03:37:09Z'
  id: 12399683708305
  locale: vi
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/vi/articles/12399683708305
---
| **Tính năng mới** | Để cung cấp trải nghiệm sử dụng API an toàn và đáng tin cậy hơn, token API V1 trong các URL API đã ngừng hoạt động và thay thế là token API V2, một token dựa trên JWT được truyền trong tiêu đề ủy quyền người mang.<br /><br />Token API V1 và các API sử dụng chúng không còn khả dụng từ ngày 18 tháng 9 năm 2023. |
| --- | --- |
| **Ngày có hiệu lực** | Ngày 18 tháng 9 năm 2023 |
| **Điều kiện tiên quyết** | Chỉ quản trị viên mới có thể <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens#truy-xuất-mã-thông-báo-api">truy xuất mã thông báo API V2</Anchor> từ bảng điều khiển AppsFlyer. |
| **Ai cần cập nhật mã thông báo API?** | Cả nhà quảng cáo và đại lý vẫn đang sử dụng mã thông báo API V1 đều cần cập nhật mã thông báo của họ. |
| **Cách tìm mã thông báo API V1** | Sử dụng <Anchor target="_blank" href="/marketers/vi/docs/audit-log">Audit log</Anchor> để lọc ra mọi mã thông báo API V1 vẫn đang được sử dụng. Sau đó, bạn có thể tải dữ liệu về tệp CSV:<ol><li>Đi đến [bảng điều khiển Audit log](https://hq1.appsflyer.com/audit-reader/dashboard).</li><li>Nhập "API Token V1" vào thanh tìm kiếm.</li><li>Trong bộ lọc**Service**, chỉ chọn **API calls**, và lọc kết quả.</li><li>Nhấp vào biểu tượng Tải xuống ở trên cùng bên phải của trang.<br />Tệp CSV của bạn được tải xuống, trong đó bao gồm ID ứng dụng, dịch vụ được sử dụng và URL lệnh gọi API.</li></ol> |
| **Hành động cần thiết** | **Cập nhật các API sau cho mã thông báo API V2:**<ol><li>Đi đến <Anchor target="_blank" href="https://hq1.appsflyer.com/account/api-tokens">trang mã thông báo API</Anchor>.</li><li>Ở phần mã thông báo API V2.0, nhấp vào biểu tượng **Sao chép vào khay nhớ tạm**.</li><li>Đối với mỗi API sau:<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/master_api_get">API chính V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">API Pull V2 Hợp nhất</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">API Pull V2 Dữ liệu Thô</Anchor></li></ul><ol><li>Thay thế URL API V1 bằng URL trong tài liệu ở trên.</li><li>Dán mã thông báo bạn đã sao chép vào tiêu đề Cấp quyền truy cập.<br />![token_v2_bearer.png](https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png)</li><li>Đối với **API OpenDSR**, hãy dán mã thông báo vào tiêu đề yêu cầu truy cập:<br />`'Authorization': 'Bearer %AuthTokenV2%'`</li></ol></li></ol> |
| **Giới thiệu về mã thông báo API** | **Tìm hiểu thêm về mã thông báo API:**<ul><li><Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">Quản lý mã thông báo API</Anchor><ul><li><Anchor target="_blank" href="/marketers/vi/docs/master-api-user-acquisition-metrics-via-api">API chính</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/pull-api-aggregate-data">API Pull Hợp nhất</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/pull-api-raw-data">Dữ liệu thô</Anchor></li><li><Anchor target="_blank" href="/marketers/vi/docs/send-opendsr-api-requests#định-dạng-yêu-cầu-gdpr">API OpenDSR</Anchor></li></ul></li></ul> |