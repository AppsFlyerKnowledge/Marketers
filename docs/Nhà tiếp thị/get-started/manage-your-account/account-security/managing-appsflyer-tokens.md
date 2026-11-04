---
title: Quản lý mã thông báo API
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-01-01T09:50:22Z'
  edited_at: '2023-11-16T11:41:08Z'
  id: 360004562377
  locale: vi
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/vi/articles/360004562377
---
> **![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Khái quát:** Quản trị viên cấp mã thông báo API để cho phép người dùng truy cập dữ liệu thông qua API AppsFlyer.

> 🚧 **Quan trọng!**
>
> * Để đảm bảo an toàn cho dữ liệu, chỉ quản trị viên mới có thể xem trang mã thông báo API. Điều này có nghĩa là người dùng tài khoản và đối tác không có quyền truy cập vào trang này.
> * Giữ an toàn cho mã thông báo của bạn vì với mã này thì có thể truy cập được dữ liệu của bạn. Không cho mã thông báo vào kho lưu trữ mã công khai.
> * Nên đặt lại mã thông báo API sau mỗi 180 ngày.

<div id="retrieve-tokens" />

## Truy xuất mã thông báo API

**Để truy xuất mã thông báo API:**

1. Từ thanh menu, truy cập menu người dùng (danh sách địa chỉ email thả xuống ở góc trên cùng bên phải).
2. Chọn **Security center.**
3. Trong phần **AppsFlyer API tokens**, hãy nhấp vào **Manage your AppsFlyer API tokens.**
4. Mã thông báo có sẵn (V2.0) được hiển thị.
5. Sao chép mã thông báo cần thiết.

## Đặt lại mã thông báo API

> ❗️ **Chú ý**
>
> Nếu bạn đặt lại mã thông báo thì mã thông báo hiện tại sẽ không hợp lệ và bạn sẽ được cấp mã thông báo thay thế. Để tránh mất dữ liệu, hãy nhúng ngay mã thông báo thay thế vào tập lệnh và quy trình tự động của bạn.

**Để đặt lại mã thông báo API:**

1. Từ thanh menu, truy cập menu người dùng (danh sách địa chỉ email thả xuống).
2. Chọn **Security center.**
3. Trong phần **AppsFlyer API tokens**, hãy nhấp vào **Manage your AppsFlyer API tokens.**
4. Mã thông báo có sẵn (V2.0) được hiển thị.
5. Xác định mã thông báo nào cần đặt lại và nhấp vào liên kết **Reset** **token.**
6. Nếu bạn muốn tiếp tục, hãy nhấp vào **Reset token** trong hộp thoại.
7. Sao chép mã thông báo mới.
8. Nhúng mã thông báo thay thế vào tập lệnh và quy trình tự động yêu cầu mã thông báo.

## Loại mã thông báo được yêu cầu cho mỗi API

<div id="advertiser" />

### Mã thông báo V2.0—API của nhà quảng cáo

| API |
| --- |
| <Anchor target="_blank" href="/marketers/vi/docs/pull-api-aggregate-data">Dữ liệu thô API Pull</Anchor> |
| <Anchor target="_blank" href="/marketers/vi/docs/pull-api-aggregate-data">Dữ liệu hợp nhất API Pull</Anchor> |
| <Anchor target="_blank" href="/marketers/vi/docs/app-list-api-for-app-owners">Nhận danh sách ứng dụng</Anchor> |
| <Anchor target="_blank" href="/marketers/vi/docs/cohort-api">Nhóm người</Anchor> |
| <Anchor target="_blank" href="/marketers/vi/docs/skan-aggregated-performance-report-api">Báo cáo hợp nhất SKAdNetwork</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_copy">Sao chép cài đặt tích hợp đối tác</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Đặt khóa giải mã liên kết giới thiệu cài đặt</Anchor> |
| API thuế doanh thu thực |
| <Anchor target="_blank" href="/marketers/vi/docs/send-opendsr-api-requests">API OpenDSR</Anchor> |
| <Anchor target="_blank" href="/marketers/vi/docs/master-api-user-acquisition-metrics-via-api">API chính</Anchor> |

<div id="ad-network" />

### Mã thông báo V2.0—API mạng quảng cáo

| API |
| --- |
| <Anchor target="_blank" href="/partners/vi/docs/app-list-api-for-ad-networks">Danh sách ứng dụng cho mạng quảng cáo</Anchor> |
| <Anchor target="_blank" href="/partners/vi/docs/access-to-aggregated-analytics-tools-for-api-partners">Tích hợp với các nền tảng quản lý chiến dịch</Anchor> |
| <Anchor target="_blank" href="/partners/vi/docs/protect360-for-integrated-partners#protect360-ad-network-reporting-api">Báo cáo Protect360 cho các đối tác tích hợp</Anchor> |
| <Anchor target="_blank" href="/partners/vi/docs/incost-api-for-ad-networks">InCost</Anchor> |

<div data-zendesk-anchors="h_01HBQN3T2HQKXZ0RC31DG28D6X=quan-tr%E1%BB%8Dng retrieving-api-tokens=truy-xu%E1%BA%A5t-m%C3%A3-th%C3%B4ng-b%C3%A1o-api h_01HBQN3T2HKEMNC8MSR0THYW2S=truy-xu%E1%BA%A5t-m%C3%A3-th%C3%B4ng-b%C3%A1o-api resetting-api-tokens=%C4%91%E1%BA%B7t-l%E1%BA%A1i-m%C3%A3-th%C3%B4ng-b%C3%A1o-api h_01HBQN3T2HM6NV4NW723YMNQ48=%C4%91%E1%BA%B7t-l%E1%BA%A1i-m%C3%A3-th%C3%B4ng-b%C3%A1o-api h_01HBQN3T2H58T5E075CZ14S9B9=ch%C3%BA-%C3%BD token-type-required-per-api=lo%E1%BA%A1i-m%C3%A3-th%C3%B4ng-b%C3%A1o-%C4%91%C6%B0%E1%BB%A3c-y%C3%AAu-c%E1%BA%A7u-cho-m%E1%BB%97i-api h_01HBQN7TBA4DX7HYMVK84SSNCP=lo%E1%BA%A1i-m%C3%A3-th%C3%B4ng-b%C3%A1o-%C4%91%C6%B0%E1%BB%A3c-y%C3%AAu-c%E1%BA%A7u-cho-m%E1%BB%97i-api v20-token%E2%80%94advertiser-apis=m%C3%A3-th%C3%B4ng-b%C3%A1o-v20api-c%E1%BB%A7a-nh%C3%A0-qu%E1%BA%A3ng-c%C3%A1o h_01HBQN7TBASK192P8D7AEWM9P6=m%C3%A3-th%C3%B4ng-b%C3%A1o-v20api-c%E1%BB%A7a-nh%C3%A0-qu%E1%BA%A3ng-c%C3%A1o v20-token%E2%80%94ad-network-apis=m%C3%A3-th%C3%B4ng-b%C3%A1o-v20api-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o h_01HBQN7TBAWAHEQXMYK9V14G0M=m%C3%A3-th%C3%B4ng-b%C3%A1o-v20api-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o" />
