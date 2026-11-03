---
title: Tối ưu hóa Quảng cáo—Báo cáo ETL
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-10-10T14:33:17Z'
  edited_at: '2023-12-11T08:22:20Z'
  id: 19253873174801
  locale: vi
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/vi/articles/19253873174801
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Sơ lược:** Sử dụng Hộp khóa Dữ liệu để truyền trực tuyến báo cáo Tối ưu hóa Quảng cáo một cách tự động và liên tục tới bộ lưu trữ đám mây để tải theo chương trình một cách hiệu quả vào hệ thống BI của bạn.

## Giới thiệu về ETL Tối ưu hóa Quảng cáo

Tải Chuyển đổi Trích xuất (ETL) Tối ưu hóa Sáng tạo trang bị cho các nhà phân tích dữ liệu của bạn tất cả thông tin họ cần để phân tích hiệu suất sáng tạo. Công cụ giúp đạt được điều này bằng cách tự động truyền trực tuyến báo cáo Tối ưu hóa Quảng cáo vào bộ lưu trữ đám mây để tải theo chương trình vào hệ thống BI của bạn.

Báo cáo hiệu suất cấp nội dung đầy đủ được cung cấp, bao gồm tất cả các chỉ số hiệu suất chủ chốt (KPI), KPI kênh trên và dưới, dữ liệu phân bổ và dữ liệu nội dung quảng cáo.

ETL Tối ưu hóa Quảng cáo sử dụng <Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers">Hộp khóa Dữ liệu</Anchor> để gửi dữ liệu báo cáo Tối ưu hóa Quảng cáo của bạn tới bộ lưu trữ đám mây. Bạn có thể chọn từ nhiều đích lưu trữ khác nhau, chẳng hạn như bộ chứa thuộc sở hữu của AppsFlyer trong Amazon Web Services (AWS) hoặc bộ lưu trữ của riêng mình trong AWS, GCS, Yandex, BigQuery, Snowflake, v.v. Hộp khóa Dữ liệu hỗ trợ nhiều đích, nghĩa là bạn có thể gửi tất cả dữ liệu đến một hoặc nhiều đích, gửi dữ liệu cụ thể đến một số đích nhất định và tùy chỉnh hoạt động phân phối dữ liệu theo nhu cầu của bạn. ETL Tối ưu hóa Sáng tạo **có sẵn với gói đăng ký Tối ưu hóa Sáng tạo Premium.**

## Bắt đầu

Phần này mô tả cách thiết lập Khóa dữ liệu cho báo cáo Tối ưu hóa quảng cáo.

<div id="set-up-data-locker" />

<Accordion title="Thiết lập Hộp khóa Dữ liệu">

Trước tiên, bạn sẽ cần đăng ký cả gói Creative Optimization Premium và Data Locker thông qua AppsFlyer CSM của mình. Sau khi đăng ký, bạn có thể thiết lập Data Locker.

**Để thiết lập Hộp khóa Dữ liệu:**

1. Thực hiện theo <Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers#set-up-data-locker">các hướng dẫn</Anchor> sau.

2. Khi thiết lập Hộp khóa Dữ liệu, hãy chọn **Creative** (ở phần **Select reports**), trên trang cấu hình Hộp khóa Dữ liệu.

![Data Locker - select Creative.jpg](https://files.readme.io/bd1528ac5419f1bbf033a4a96c028f5a1bf7ff798c452371ac906ea650255d31-19276693230353.jpg)

</Accordion>

<div id="edit-data-locker-configuration" />

<Accordion title="Chỉnh sửa cấu hình Hộp khóa Dữ liệu">

Phần này mô tả cách chỉnh sửa cấu hình Hộp khóa Dữ liệu hiện có của bạn để thêm báo cáo Tối ưu hóa  Quảng cáo.

**Để thêm báo cáo Tối ưu hóa Quảng cáo vào Hộp khóa Dữ liệu:**

1. Từ phần **Integrations** trên menu bên AppsFlyer chính, hãy nhấp vào **Data Locker**.

<Image alt="from Integration select Data Locker.jpg" src="https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg" width="200px" />

2. Chọn **Creative** (ở phần **Select reports**) trên trang cấu hình Hộp khóa Dữ liệu.

![Data Locker - select Creative.jpg](https://files.readme.io/bd1528ac5419f1bbf033a4a96c028f5a1bf7ff798c452371ac906ea650255d31-19276693230353.jpg)

</Accordion>

## Dữ liệu

Phần này mô tả tính khả dụng của dữ liệu trong ETL Tối ưu hóa Quảng cáo.

<div id="data-freshness" />

<Accordion title="Tính cập nhật của dữ liệu">

Sau khi cấu hình, báo cáo Tối ưu hóa  Quảng cáo sẽ được truyền trực tuyến tới Hộp khóa Dữ liệu hàng ngày, cung cấp dữ liệu trong 30 ngày qua. Xuất dữ liệu sẽ khả dụng hàng ngày vào lúc UTC + 12. <Anchor target="_blank" href="/marketers/vi/docs/data-locker-advertiser-reports#data-freshness-explanations">Tìm hiểu thêm</Anchor>

</Accordion>

<div id="available-data" />

<Accordion title="Dữ liệu khả dụng">

Dữ liệu Quảng cáo sau đây khả dụng trong Hộp khóa Dữ liệu.

| Trường | Loại |
| --- | --- |
| ngày | chuỗi |
| asset\_link | chuỗi |
| quảng cáo | chuỗi |
| media\_source | chuỗi |
| chiến dịch | chuỗi |
| campaign\_id | chuỗi |
| quảng cáo | chuỗi |
| ad\_id | chuỗi |
| bộ quảng cáo | chuỗi |
| adset\_id | chuỗi |
| app\_name | chuỗi |
| app\_id | chuỗi |
| creative\_first\_seen | chuỗi |
| creative\_type | chuỗi |
| thời lượng | chuỗi |
| end\_card\_type | chuỗi |
| địa lý | chuỗi |
| nền tảng | chuỗi |
| hướng | chuỗi |
| độ phân giải | chuỗi |
| lượt hiển thị | chuỗi |
| lượt nhấp | chuỗi |
| lượt cài đặt | chuỗi |
| ctr | chuỗi |
| cvr | chuỗi |
| ipm | chuỗi |
| chi phí | chuỗi |
| ecpi | chuỗi |
| phân bổ lại | chuỗi |
| tương tác lại | chuỗi |
| cpm | chuỗi |
| roas\_d1 | chuỗi |
| roas\_d7 | chuỗi |
| roas\_d14 | chuỗi |
| roas\_d30 | chuỗi |
| roas\_d60 | chuỗi |
| roas\_d90 | chuỗi |
| retention\_d1 | chuỗi |
| retention\_d7 | chuỗi |
| retention\_d14 | chuỗi |
| retention\_d30 | chuỗi |
| retention\_d60 | chuỗi |
| retention\_d90 | chuỗi |
| revenue\_d1 | chuỗi |
| revenue\_d14 | chuỗi |
| revenue\_d30 | chuỗi |
| revenue\_d60 | chuỗi |
| revenue\_d7 | chuỗi |
| Revenue\_d90 | chuỗi |
| partner\_cpm | chuỗi |
| partner\_ctr | chuỗi |
| partner\_cvr | chuỗi |
| partner\_clicks | chuỗi |
| partner\_cost | chuỗi |
| partner\_ipm | chuỗi |
| partner\_impressions | chuỗi |
| partner\_installs | chuỗi |
| partner\_ecpi | chuỗi |
| partner\_ecpi | chuỗi |

> 📘 **Lưu ý**
>
> **Các dữ liệu sau đây không khả dụng:**
>
> * Phương diện tùy chỉnh
> * Phép đo tùy chỉnh
> * Sự kiện trong ứng dụng
> * Dữ liệu AI (thành phần và cảnh)
> * Dữ liệu nhắm mục tiêu lại

</Accordion>

<div data-zendesk-anchors="about-creative-etl=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-etl-t%E1%BB%91i-%C6%B0u-h%C3%B3a-qu%E1%BA%A3ng-c%C3%A1o h_01HCF5ZDDGTN52MZ9DX2MDKJV7=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-etl-t%E1%BB%91i-%C6%B0u-h%C3%B3a-qu%E1%BA%A3ng-c%C3%A1o get-started=b%E1%BA%AFt-%C4%91%E1%BA%A7u h_01HCF65RS2NKHEDHFE9TN78ES8=b%E1%BA%AFt-%C4%91%E1%BA%A7u h_01HCFF8BWHGFX5KEZWKVDYXKKA=set-up-data-locker h_01HCFF8BWJCQHNN17N8G555FP9=edit-data-locker-configuration data=d%E1%BB%AF-li%E1%BB%87u h_01HCF8C8S392WJMYYHV6ECMNCW=d%E1%BB%AF-li%E1%BB%87u h_01HCFC87EDDD3X0ZXNCAQAHTZB=data-freshness h_01HCFBYBBMNZ52TH4M3G3YB3YM=available-data h_01HF44ZFSHJ8MX9ZNBF7SWB5JN=l%C6%B0u-%C3%BD" />
