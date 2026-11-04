---
title: Tải trọng dữ liệu chuyển đổi và các tình huống
metadata:
  keywords:
    - Conversion
    - Retargeting
    - Installs
    - Re-attribution
    - Re-engagement
    - Developers
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-31T13:05:33Z'
  edited_at: '2023-11-01T04:30:09Z'
  id: 360000726098
  locale: vi
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/vi/articles/360000726098
---
> **Khái quát:** Sử dụng <span id="tiktok-conversion-data"></span><span id="tiktok-for-business-conversion-data"></span><span id="x-ads-conversion-data"></span><span id="snapchat-conversion-data"></span><span id="twitter-conversion-data"></span>dữ liệu chuyển đổi để xác định các tình huống chuyển đổi khác nhau, tùy chỉnh trải nghiệm người dùng, v.v.

<div id="overview" />

## Tổng quan

Hướng dẫn sau đây có các tình huống chuyển đổi người dùng khác nhau và tải trọng dữ liệu chuyển đổi tương ứng:

* [Thu hút Người dùng (UA)](#dữ-liệu-chuyển-đổi-ua-với-srn)
* [Nhắm mục tiêu lại](#nhắm-mục-tiêu-lại-dữ-liệu-chuyển-đổi)

Dữ liệu chuyển đổi được cung cấp trong nền tảng bằng bất kỳ cách nào sau đây:

* <Anchor target="_blank" href="/marketers/vi/docs/raw-data-export-page">Báo cáo dữ liệu thô</Anchor>
* <Anchor target="_blank" href="/marketers/vi/docs/push-api-streaming-raw-data">API Push</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">SDK AppsFlyer</Anchor>

Do sự đánh đổi về độ chính xác/độ trễ nên dữ liệu chuyển đổi cho cùng một ID thiết bị có thể khác nhau giữa các API.

<div id="non-organic-conversion-data-payload-fields" />

### Các trường tải trọng dữ liệu chuyển đổi không tự nhiên

<div id="fields-always-available" />

#### Các trường luôn khả dụng

Bảng sau đây liệt kê các trường luôn tồn tại cho lượt chuyển đổi **không tự nhiên**, bất kể `media_source` của lượt chuyển đổi là gì.

| Tên trường tải trọng | Tên trường dữ liệu thô | Lưu ý |
| --- | --- | --- |
| `media_source` | Nguồn truyền thông | Nhà phát hành được phân bổ. Tương đương với thông số `pid` trong đường dẫn phân bổ |
| `install_time` | Thời gian cài đặt |  |
| `click_time` | Thời gian chạm được phân bổ | Thời gian xảy ra lượt nhấp hoặc lượt hiển thị theo giờ UTC |
| `is_first_launch` | Không áp dụng | `true`, `false` |
| `af_status` | Dữ liệu thô được chia thành các báo cáo riêng biệt: tự nhiên, không tự nhiên | `"Non-organic"` |
| `af_siteid` | ID trang |  |
| `adgroup_id` | ID Quảng cáo |  |
| `adset` | Bộ quảng cáo |  |
| `adset_id` | ID Bộ quảng cáo |  |
| `đại lý` | Đối tác | `null` hoặc tên đại lý (đối với các chiến dịch do đại lý triển khai) |
| `chiến dịch` | Chiến dịch |  |
| `campaign_id` | ID Chiến dịch |  |
| `http_referrer` | Liên kết giới thiệu HTTP |  |
| `retargeting_conversion_type` | Loại lượt chuyển đổi nhắm mục tiêu lại | "none" hoặc retargeting\_conversion\_type |
| `af_sub[n] (n=1—5)` | Thông số Phụ [n] (n=1–5) |  |

<div id="fields-available-in-some-cases" />

#### Các trường khả dụng trong một số trường hợp

Các trường trong bảng sau đây sẽ khả dụng trong một số trường hợp, tùy thuộc vào cách SRN điền vào mỗi sự kiện riêng.

<table><thead><tr><th>Tên trường tải trọng</th><th>Tên trường dữ liệu thô</th><th>Lưu ý</th></tr></thead><tbody><tr><td><code>af_channel</code></td><td>Kênh</td><td><p>SRN điền thông số này:</p><ul><li>AppLovin</li><li>Google Ads</li><li>Quảng cáo Meta</li><li>Snapchat</li><li>TikTok for Business</li><li>Twitter</li></ul><p>Ví dụ: Facebook—Instagram, Google—YouTube </p></td></tr><tr><td><code>orig_cost</code></td><td> </td><td><p>Lưu ý (1)</p></td></tr><tr><td><code>costs_cents_USD</code></td><td> </td><td><p>Lưu ý (1)</p></td></tr><tr><td><code>af_cpi</code></td><td> </td><td><p>Lưu ý (1)</p></td></tr></tbody><tbody><tr><td colspan="4"><p><strong>Lưu ý</strong></p><p>(1) Các trường chi phí được điền bằng các giá trị được mạng quảng cáo chia sẻ. Để mạng quảng cáo chia sẻ dữ liệu chi phí với AppsFlyer, bạn phải bật tích hợp chi phí trên trang <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank"><strong>Active integrations</strong></a>. Một số SRN hỗ trợ chia sẻ chi phí hàng loạt. Trong trường hợp này, các trường chi phí cấp sự kiện sẽ trả về 0. </p></td></tr></tbody></table>

<div id="additional-fields" />

### Các Trưởng Bổ Sung

* <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters#thông-số-đường-dẫn-phân-bổ">Danh sách thông số của AppsFlyer</Anchor>
* Bạn có thể thêm các thông số vào đường dẫn phân bổ, chúng có sẵn trong tải trọng

Xem <Anchor target="_blank" href="/marketers/vi/docs/raw-data-field-dictionary#data-fields-dictionary">từ điển trường dữ liệu thô</Anchor> để biết thêm thông tin.

<div id="limitations" />

### Điểm hạn chế

<div id="custom-parameter-names" />

<Accordion title="Tên thông số tùy chỉnh">

Không được đặt thông số tùy chỉnh là `name` (chữ thường "n". `Name` thì hợp lệ).

Nếu một thông số được đặt là `name`, thì thông số đó sẽ bị xóa khỏi tải trọng.

</Accordion>

---

<div id="ua-conversion-data-with-srns" />

## Dữ liệu chuyển đổi UA với SRN

<Anchor target="_blank" href="/marketers/vi/docs/self-reporting-networks-srns">Mạng tự báo cáo</Anchor> (SRN) là mạng quảng cáo triển khai các cơ chế phân bổ của riêng mình, chẳng hạn như Meta ads và Google.

SRN không sử dụng đường dẫn phân bổ. Có nghĩa là:

* Các trường tải trọng được xác định trước
* Bạn không thể thêm trường vào tải trọng bằng cách thêm các thông số vào đường dẫn phân bổ.

SRN báo cáo lượt chuyển đổi cho AppsFlyer. Dữ liệu chuyển đổi được cung cấp trong ứng dụng. Các trường khả dụng sẽ khác nhau tùy theo SRN và được trình bày chi tiết trong các tab SRN riêng lẻ theo sau.

<div id="a-note-about-meta-ads" />

#### Lưu ý về Meta ads

Nếu bạn chạy các chiến dịch trên Meta ads và không ký vào điều khoản dịch vụ của Meta, AppsFlyer sẽ ghi nhận lượt cài đặt. Tính khả dụng của báo cáo bị giới hạn như sau:

* **Khả dụng:** Bảng điều khiển và báo cáo hợp nhất và phân tích
* **Không khả dụng:** Dữ liệu thô

<Tabs>
<Tab title="Meta ads">

<div id="meta-ads-conversion-data" />

### Dữ liệu chuyển đổi Meta ads

| Tên trường | Lưu ý | Nguồn dữ liệu |
| --- | --- | --- |
| `match_type` | Luôn là `"srn"` | AppsFlyer |
| `media_source` | Luôn là `"Meta ads"` | AppsFlyer |
| `đại lý` | null hoặc giá trị thông số `af_prt` trong đường dẫn phân bổ | Quảng cáo Meta |
| `http_referrer` | Luôn là `null` | Quảng cáo Meta |
| `retargeting_conversion_type` |  | AppsFlyer |
| `af_channel` |  | Meta ads (publisher\_platform) |
| `af_status` | Luôn là `"Non-organic"` | AppsFlyer |
| `ad_id` | Chỉ sử dụng nội bộ cho Meta ads. | Meta ads (ad\_id) |
| `click_time` |  | AppsFlyer |
| `install_time` |  | AppsFlyer |
| `is_first_launch` | `true`, `false` | Thiết bị |
| `adset_id` | Có sẵn ở dạng dữ liệu thô: ID Bộ quảng cáo | Meta ads (campaign\_id) |
| `is_fb` | Luôn là `true` | AppsFlyer |
| `chiến dịch` | Có sẵn ở dạng dữ liệu thô: Tên Chiến dịch | Meta ads (campaign\_group\_name) |
| `campaign_id` | Có sẵn ở dạng dữ liệu thô: ID Chiến dịch | Meta ads (campaign\_group\_id) |
| `is_paid` | Luôn là `true` | Quảng cáo Meta |
| `adgroup` | Có sẵn ở dạng dữ liệu thô: Quảng cáo | Meta ads (adgroup\_name) |
| `adgroup_id` | Có sẵn ở dạng dữ liệu thô: ID Quảng cáo | Meta ads (adgroup\_id) |
| `adset` | Có sẵn ở dạng dữ liệu thô: Bộ quảng cáo | Meta ads (campaign\_name) |
| `af_siteid` | Luôn là `null` | Quảng cáo Meta |
| `af_sub[1-5]` | Luôn là `null` | Nhà quảng cáo |

**Lưu ý:** Các trường liên quan đến chi phí không khả dụng vì Meta ads không chia sẻ dữ liệu chi phí khi chuyển đổi. Nếu <Anchor target="_blank" href="/marketers/vi/docs/meta-ads-integration-setup#cost-clicks-and-impressions">chia sẻ chi phí</Anchor> được bật, Meta ads sẽ chia sẻ dữ liệu chi phí với AppsFlyer nhiều lần trong ngày.

</Tab>

<Tab title="Google">

<table><caption><h3><span id="google-ads-conversion-data"></span>Dữ liệu chuyển đổi Google Ads</h3></caption><thead><tr><th>Tên trường</th><th>Lưu ý</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Luôn là <code>"srn"</code> </td></tr><tr><td><code>media_source</code></td><td>Luôn là <code>"googleadwords_int"</code> </td></tr><tr><td><code>đại lý</code></td><td> <code>"none"</code> hoặc giá trị <code>af_prt</code> </td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td><code>af_channel</code></td><td><p>Lưu ý (1)</p></td></tr><tr><td><code>af_status</code></td><td>Luôn là <code>"Non-organic"</code> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>adgroup_name</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td>Luôn là <code>null</code> </td></tr><tr><td><code>chiến dịch</code></td><td>Lưu ý (3)</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>adset</code></td><td>Lưu ý (3)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>ad_event_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td>Chuỗi rỗng</td></tr><tr><td><code>af_ad_id</code></td><td>Chuỗi rỗng</td></tr><tr><td><code>af_ad_type</code></td><td><span>Loại quảng cáo AdWords</span></td></tr><tr><td><code>af_adset</code></td><td><span>Có sẵn ở dạng dữ liệu thô: Bộ quảng cáo</span></td></tr><tr><td><code>af_adset_id</code></td><td>Có sẵn ở dạng dữ liệu thô: ID Bộ quảng cáo</td></tr><tr><td><code>af_c_id</code></td><td>Có sẵn ở dạng dữ liệu thô: ID Chiến dịch</td></tr><tr><td><code>af_click_lookback</code></td><td></td></tr><tr><td><code>af_cpi</code></td><td>Lưu ý (2)</td></tr><tr><td><code>af_dp</code></td><td>Chỉ liên quan đến <a href="./google-ads-adwords-integration-setup-for-advertisers#sử-dụng-liên-kết-sâu-gián-tiếp-rong-chiến-dịch-ứng-dụng" target="_blank">Chiến dịch Ứng dụng Google trong Nguồn cấp dữ liệu</a>.</td></tr><tr><td><code>af_keywords</code></td><td>Có sẵn ở dạng dữ liệu thô: Từ khóa</td></tr><tr><td><code>af_prt</code></td><td> <code>"none"</code> hoặc giá trị <code>af_prt</code> </td></tr><tr><td><code>af_reengagement_window</code></td><td>Có sẵn ở dạng dữ liệu thô: Khung thời gian Thu hút lại </td></tr><tr><td><code>af_viewthrough_lookback</code></td><td>Có sẵn ở dạng dữ liệu thô: Khung thời gian Xem lại cho Phân bổ Lượt xem hết</td></tr><tr><td><code>click_url</code></td><td>Có sẵn ở dạng dữ liệu thô: Liên kết giới thiệu HTTP</td></tr><tr><td><code>click-timestamp</code></td><td>Nguồn: AppsFlyer</td></tr><tr><td><code>cost_cents_USD</code></td><td>Lưu ý (2)</td></tr><tr><td><code>external_account_id</code></td><td>ID tài khoản AdWords</td></tr><tr><td><code>gclid</code></td><td> </td></tr><tr><td><code>lat</code></td><td> </td></tr><tr><td><code>network</code></td><td>Lưu ý (1)</td></tr><tr><td><code>orig_cost</code></td><td>Lưu ý (2)</td></tr><tr><td><code>video_id</code></td><td>Luôn là <code>null</code> </td></tr><tr><td colspan="2"><p><strong>Ghi chú<br/></strong>(1) Google sử dụng nhiều mạng quảng cáo. Sử dụng <code>af_channel</code> kết hợp với <code>network</code> để lấy nguồn lượt cài đặt.<br/>(2) Các trường này trả về 0. Nếu nhà quảng cáo bật tính năng chia sẻ chi phí, thì Google sẽ gửi dữ liệu chi phí AppsFlyer nhiều lần trong ngày.(3) Sử dụng <code>campaign</code> và <code>adset</code> để cá nhân hóa nội dung người dùng.</p></td></tr></tbody></table>

</Tab>

<Tab title="ASA">

<table><caption><h3><span id="apple-search-ads-conversion-data"></span>Dữ liệu chuyển đổi của Apple Search Ads</h3></caption><thead><tr><th>Tên trường</th><th>Lưu ý</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Luôn là <code>"srn"</code> </td></tr><tr><td><code>media_source</code></td><td>Luôn là <code>"Apple Search Ads"</code> </td></tr><tr><td><code>{"<strike>adset</strike>"}</code></td><td>Lưu ý (2)</td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><code>{"<strike>af_adset</strike>"}</code></td><td>Lưu ý (2)</td></tr><tr><td><code>af_adset_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Lưu ý (1)</td></tr><tr><td><code>{"<strike>af_keywords</strike>"}</code></td><td><p>Lưu ý (2)—Sử dụng ID từ khóa</p></td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Luôn là <code>"Non-organic"</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>đại lý</code></td><td> <code>null</code> hoặc giá trị <code>af_prt</code> </td></tr><tr><td><code>{"<strike>chiến dịch</strike>"}</code></td><td>Lưu ý (2)</td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Lưu ý (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Lưu ý (1)</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr></tbody><tbody><tr><td colspan="3"><p><strong>Ghi chú<br/></strong>(1)  Apple Search Ads hỗ trợ chia sẻ chi phí hàng loạt, không hỗ trợ chia sẻ chi phí trong dữ liệu chuyển đổi.<br/>(2) Không còn được hỗ trợ kể từ ngày 15 tháng 2 năm 2021, do Apple Search Ads áp dụng AdServices AP.</p></td></tr></tbody></table>

</Tab>

<Tab title="Snap">

| Tên trường | Lưu ý |
| --- | --- |
| `match_type` | `"srn"` |
| `media_source` | `"snapchat_int"` |
| `adset` |  |
| `adset_id` |  |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_c_id` |  |
| `af_channel` |  |
| `af_cpi` |  |
| `af_siteid` |  |
| `af_status` | Luôn là `"Non-organic"` |
| `af_sub[1-5]` |  |
| `af_viewthrough_lookback` |  |
| `đại lý` |  |
| `chiến dịch` |  |
| `campaign_id` |  |
| `click_time` |  |
| `cost_cents_USD` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `orig_cost` |  |
| `retargeting_conversion_type` |  |

</Tab>

<Tab title="Twitter">

| Tên trường | Lưu ý |
| --- | --- |
| `match_type` | Luôn là `"srn"` |
| `media_source` | Luôn là `"Twitter"` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_channel` |  |
| `af_siteid` |  |
| `af_status` | Luôn là `"Non-organic"` |
| `af_sub[1-5]` |  |
| `đại lý` | Luôn là `null` |
| `chiến dịch` |  |
| `campaign_id` | `null` hoặc ID Chiến dịch |
| `click_time` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` | `true`, `false` |
| `adgroup` |  |
| `adgroup_id` |  |
| `retargeting_conversion_type` | Luôn là `"none"` |

**Ghi chú:** Các trường chi phí không xuất hiện trong tải trọng vì Twitter không hỗ trợ tính năng chia sẻ dữ liệu chi phí.

</Tab>

<Tab title="Oath">

<table><caption><h3><span id="oath-ad-platforms-conversion-data"></span>Dữ liệu chuyển đổi của các Nền tảng Quảng cáo Oath</h3></caption><thead><tr><th>Tên trường</th><th>Lưu ý</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Luôn là <code>"srn"</code> </td></tr><tr><td><code>media_source</code></td><td>Luôn là <code>"yahoogemini_int"</code> </td></tr><tr><td><code>adset</code></td><td> </td></tr><tr><td><code>adset_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td> </td></tr><tr><td><code>af_ad_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Lưu ý (1)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Luôn là <code>"Non-organic"</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>đại lý</code></td><td> </td></tr><tr><td><code>chiến dịch</code></td><td> </td></tr><tr><td><code>campaign_id</code></td><td> </td></tr><tr><td><code>campaign_type</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Lưu ý (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Lưu ý (1)</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td colspan="2"> <strong>Lưu ý</strong><br/>(1) Oath hỗ trợ tính năng chia sẻ chi phí nhưng gửi hàng loạt dữ liệu liên quan đến chi phí, mà không phải trong dữ liệu chuyển đổi.</td></tr></tbody></table>

</Tab>
</Tabs>

<div id="ua-conversion-with-other-ad-networks" />

## Chuyển đổi UA với các mạng quảng cáo khác

Đối với các mạng quảng cáo khác, dữ liệu trong tải trọng bị ảnh hưởng trực tiếp bởi <Anchor target="_blank" href="/marketers/vi/docs/about-link-structure-and-parameters">các thông số trong đường dẫn phân bổ</Anchor>.

Kiểm tra các tải trọng JSON sau đây.

**Lưu ý!** Dữ liệu chuyển đổi trả về dưới dạng cấu trúc dữ liệu giống như bản đồ. Nhà phát triển **không** tương tác với JSON thô.

<div id="applovin" />

<Accordion title="Applovin">

<div id="attribution-link" />

#### Đường dẫn phân bổ:

```http HTTPS
https://app.appsflyer.com/com.company.app?af_ad=ad_name&af_ad_type=INTER
  &af_channel=video&af_siteid=123_site_id&af_c_id=b8******************************&
  af_adset=_DEFAULT&pid=applovin_int&c=campaign_name
  &af_click_lookback=7d&clickid=10****************
  &advertising_id=50********************************&af_ip=
```

<div id="payload" />

#### Tải trọng:

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "applovin_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:49:54.186",
      "adgroup_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-24 14:29:33.738",
      "agency": null,
      "cost_cents_USD": "0",
      "af_ad_type": "INTER",
      "af_c_id": "b8******************************",
      "adset": null,
      "advertising_id": "50********************************",
      "af_sub1": null,
      "clickid": "10****************",
      "af_click_lookback": "7d",
      "af_siteid": "123_site_id",
      "af_ad": "ad_name",
      "http_referrer": null,
      "af_channel": "video",
      "af_adset": "_DEFAULT",
      "af_sub5": null,
      "af_sub4": null,
      "af_cpi": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* Các thông số trong đường dẫn phân bổ xuất hiện dưới dạng các trường trong tải trọng
* Các trường khác trong tải trọng **không có trong đường dẫn phân bổ** xuất hiện với giá trị null
* AppLovin hỗ trợ chia sẻ chi phí quảng cáo nhưng gửi hàng loạt dữ liệu chi phí tới AppsFlyer. Các trường liên quan đến chi phí sẽ trả về 0.

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

<div id="attribution-link-1" />

#### Đường dẫn phân bổ:

```http HTTPS
https://app.appsflyer.com/id123456789?
  af_ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &clickid=ab*******************&redirect=false
  &ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &af_lang=pt&imei=&af_sub1=&advertising_id=&af_ip=192.168.0.1&pid=ironsource_int
  &device_ip=192.168.0.1&c=campaign_name
  &idfa=01**********************************&af_siteid=123_site_id&
  af_enc_data=cN*********************************************************************
```

<div id="payload-1" />

#### Tải trọng:

```json
{
      "adgroup": null,
      "af_enc_data": "cN**************************************************************************************",
      "campaign": "campaign_name",
      "media_source": "ironsource_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:59:32.194",
      "adgroup_id": null,
      "redirect": "false",
      "orig_cost": "0.75",
      "click_time": "2018-12-30 23:58:54.517",
     "agency": null,
      "cost_cents_USD": "75",
      "adset": null,
      "advertising_id": "35**********************************",
      "af_sub1": null,
      "af_ip": "192.168.0.1",
      "clickid": "ab*******************",
      "af_sub3": null,
      "af_cost_value": "0.75",
      "af_ref": "ironsource_5f******************************************",
      "af_siteid": "123_site_id",
      "http_referrer": null,
      "af_cost_model": "cpi",
      "af_ua": "Mozilla/5.0 (Linux; Android 8.0.0; SM-N950F Build/R16NW; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/71.0.3578.99 Mobile Safari/537.36",
      "af_cost_currency": "USD",
      "af_sub5": null,
      "af_sub4": null,
      "af_lang": "en",
      "af_cpi": null,
      "af_click_lookback": "7d",
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

ironSource chia sẻ dữ liệu liên quan đến chi phí với AppsFlyer khi chuyển đổi bằng cách sử dụng các trường `orig_cost`, `costs_cents_USD` và `af_cost_value`.

Tuy nhiên, dữ liệu liên quan đến chi phí **không xuất hiện trong đường dẫn phân bổ**. ironSource mã hóa dữ liệu chi phí và lưu trữ dữ liệu đó trong trường `af_enc_data`.

</Accordion>

<div id="tip" />

<div id="retargeting-conversion-data" />

## Nhắm mục tiêu lại dữ liệu chuyển đổi

Nhắm mục tiêu lại bao gồm hai loại chuyển đổi, phân bổ lại hoặc thu hút lại.

> 👍 **Lời khuyên**
>
> Dữ liệu chuyển đổi dùng cho việc nhắm mục tiêu lại không phải lúc nào cũng đưa ra dấu hiệu rõ ràng về loại chuyển đổi. Xem [các nguồn dữ liệu chuyển đổi thay thế](#nguồn-dữ-liệu-chuyển-đổi-thay-thế).

<div id="note" />

<div id="re-attribution-with-srns" />

### Phân bổ lại với SRN

Khi người dùng được phân bổ lại thông qua SRN, tải trọng dữ liệu chuyển đổi không cho biết đây là chiến dịch nhắm mục tiêu lại. Vì SRN không sử dụng đường dẫn phân bổ nên không có cách nào để đặt thông số `is_retargeting=true` trong trường dẫn phân bổ. Đối với **các SRN hỗ trợ nhắm mục tiêu lại**, AppsFlyer xác định xem người dùng có nên được phân bổ lại hay không.

Điều này có nghĩa là không có cách nào để xác định, ở cấp độ SDK, lượt cài đặt có phải đến từ chiến dịch nhắm mục tiêu lại hay không. Cách duy nhất là đặt tên chiến dịch sao cho tên đó biểu thị chiến dịch nhắm mục tiêu lại.

> 📘 **Lưu ý**
>
> Việc đặt tên chiến dịch sao cho có thể chỉ ra việc nhắm mục tiêu lại **không phải là một cách lý tưởng**. Xem [các ví dụ để tìm hiểu thêm](#ví-dụ-về-thu-hút-người-dùng-và-phân-bổ-lại-kết-hợp).

<div id="re-attribution-with-regular-ad-networks" />

### Phân bổ lại với các mạng quảng cáo thông thường

Phân bổ cho các mạng quảng cáo dựa trên các đường dẫn phân bổ. Dù là đường dẫn phân bổ thông thường hay OneLink, với việc nhắm mục tiêu lại, đường dẫn phân bổ luôn có thông số `is_retargeting=true` được đặt trong đó.

<div id="retargeting-campaign-with-criteo" />

<Accordion title="Chiến dịch nhắm mục tiêu lại với Criteo">

<div id="attribution-link-2" />

#### Đường dẫn phân bổ

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

<div id="conversion-data-payload" />

#### Tải trọng dữ liệu chuyển đổi

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "criteo_int",
      "retargeting_conversion_type": "re-attribution",
      "adset_id": null,
      "campaign_id": null,
      "af_reengagement_window": "30d",
      "install_time": "2018-12-01 23:13:03.126",
      "adgroup_id": null,
      "redirect": "false",
      "af_sub5": null,
      "click_time": "2018-11-18 20:02:31.559",
      "agency": null,
      "cost_cents_USD": "0",
      "is_retargeting": "true",
      "af_cpi": null,
      "af_click_lookback": "30d",
      "af_siteid": null,
      "idfa": "68**********************************",
      "http_referrer": null,
      "orig_cost": "0.0",
      "af_sub4": null,
      "adset": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* Thông số `retargeting_conversion_type` - thông số này cho biết loại hình nhắm mục tiêu lại. Có thể là phân bổ lại, thu hút lại hoặc không.
* Thông số `is_retargeting: true` - thông số này cho biết rằng lượt cài đặt là lượt cài đặt được phân bổ lại
* `af_reengagement_window`: Khung thời gian phân bổ thu hút lại là số ngày mà một sự kiện có thể được phân bổ cho **người dùng được thu hút lại**. Vì đây là chuyển đổi phân bổ lại nên thông số này là không cần thiết.

</Accordion>

<div id="re-attribution-with-deferred-deep-linking" />

### Phân bổ lại với liên kết sâu bị trì hoãn

Thông thường, bạn muốn liên kết sâu với những người dùng được phân bổ lại, những người mà theo định nghĩa là được phân bổ lại, chưa cài đặt ứng dụng. Ví dụ: bạn đặt một chiến dịch nhằm mang lại những người dùng đã gỡ cài đặt ứng dụng quay lại. Chiến dịch quảng cáo một sản phẩm hoặc dịch vụ và bạn muốn cung cấp cho người dùng nội dung liên quan đến sản phẩm hoặc dịch vụ mà bạn quảng cáo.

Điều này được gọi là Liên kết Sâu bị Trì hoãn. Tải trọng dữ liệu chuyển đổi cho Liên kết Sâu bị Trì hoãn đến từ phương thức `onConversionDataSuccess`.

<div id="deferred-deep-linking-with-srns" />

<Accordion title="Liên kết sâu gián tiếp với SRN">

Thông số Liên kết sâu được xác định trong các chiến dịch SRN không có sẵn bên ngoài SRN. Điều này bao gồm thông số `af_dp`, chứa đường dẫn lược đồ trong ứng dụng. Ngoại lệ duy nhất cho điều này là khi sử dụng <Anchor target="_blank" href="/marketers/vi/docs/google-ads-adwords-integration-setup-for-advertisers#sử-dụng-liên-kết-sâu-gián-tiếp-rong-chiến-dịch-ứng-dụng">Chiến dịch ứng dụng của Google trong Nguồn cấp dữ liệu</Anchor>. Để triển khai liên kết sâu bị trì hoãn, logic bổ sung phải được áp dụng cho các chiến dịch SRN. Sử dụng dữ liệu trong phản hồi `onConversionSuccess`, chẳng hạn như chiến dịch, bộ quảng cáo, nhóm quảng cáo để chuyển hướng người dùng của bạn theo chương trình.

<div id="note-1" />

<div id="conversion-data-for-deferred-deep-linking-with-meta-ads" />

#### Dữ liệu chuyển đổi cho liên kết sâu bị trì hoãn với Meta ads

<Tabs>
<Tab title="Android">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"Non-organic",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

</Tab>

<Tab title="iOS">

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,  
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

</Tab>
</Tabs>

Bạn có thể sử dụng dữ liệu trong phản hồi getConversionData, chẳng hạn như chiến dịch, bộ quảng cáo, v.v. để chuyển hướng người dùng của bạn theo cách lập trình và cung cấp cho họ nội dung có liên quan.

> 📄 **Ví dụ**
>
> Ứng dụng này là một ứng dụng Thương mại điện tử chuyên về trang phục thể thao. Một người dùng chưa cài đặt ứng dụng tương tác với quảng cáo và cài đặt ứng dụng. Khi ứng dụng khởi chạy, SDK sẽ trả về dữ liệu chuyển đổi. Nhà phát triển làm cho ứng dụng mở hoạt động (chiến dịch) **bộ sưu tập giày chạy bộ mùa hè** trong cửa hàng và cung cấp danh mục (bộ quảng cáo) **giày chạy bộ dành cho nữ**.

</Accordion>

<div id="deferred-deep-linking-with-attribution-links" />

<Accordion title="Liên kết sâu bị trì hoãn với đường dẫn phân bổ">

Có ba cách để liên kết sâu người dùng:

<div id="uri-schemes" />

#### Lược đồ URI

Khi sử dụng Lược đồ URI, đối với cả đường dẫn phân bổ và OneLink, đường dẫn phân bổ và tải trọng sẽ như sau:

**Đường dẫn phân bổ**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**Tải trọng**

```json
{
      "af_deeplink": true,
      "campaign": "campaign_name",
      "media_source": "media_source_name",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-30 23:59:09",
      "install_time": "2018-12-30 23:59:39.330",
      "agency": null,
      "cost_cents_USD": "0",
      "adset": "AD_SET_NAME",
      "ad_id": "AD_ID",
      "af_siteid": null,
      "http_referrer": null,
      "af_cpi": null,
      "af_sub5": null,
      "af_sub4": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink: true` - khi thông số này xuất hiện và được đặt thành true, hãy tìm các trường `scheme` và `host`
* `scheme` và `host` - các trường này đến từ thông số `af_dp` trong đường dẫn phân bổ và cho biết lược đồ và hoạt động mà người dùng sẽ được liên kết sâu

<div id="note-2" />

<div id="important" />

<div id="ios-universal-links-and-android-app-links" />

#### Liên kết chung iOS và liên kết ứng dụng Android

Đây là hai trong số ba cách khác để thực hiện liên kết sâu.

Khi sử dụng liên kết chung hoặc liên kết ứng dụng, OneLink và tải trọng sẽ như sau:

**OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**Tải trọng**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "Non-organic",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* Trường `shortlink` - đây là trường cho biết OneLink cụ thể mang đến người dùng. Trường này giúp nhà phát triển biết cách tiến hành khởi chạy một hoạt động và cung cấp nội dung. Các trường khác như `campaign` cũng có thể được sử dụng cho mục đích này.

  > 🚧 **Quan trọng!**
  >
  > Trường `shortlink` không xuất hiện trong tải trọng khi sử dụng OneLink đầy đủ.
  >
  > Trong cả hai trường hợp (OneLink rút gọn hoặc đầy đủ), bạn nên thêm thông số tùy chỉnh cho biết hoạt động. Ví dụ `&deep_link_activity=shoes_cateogry`


> 📘 **Lưu ý**
>
> Chỉ có thể sử dụng các liên kết chung và liên kết ứng dụng với OneLink.

</Accordion>

<div id="re-engagement-with-srns" />

### Thu hút lại với SRN

Giống như các chiến dịch Phân bổ lại, khi người dùng được thu hút lại thông qua SRN, dữ liệu chuyển đổi không cho biết đây là chiến dịch thu hút lại. Bạn có thể đặt tên chiến dịch sao cho tên đó biểu thị là chiến dịch thu hút lại.

<div id="re-engagement-with-regular-ad-networks" />

### Thu hút lại bằng các mạng quảng cáo thông thường

Ở đây cũng vậy, tải trọng dữ liệu chuyển đổi không cho biết rằng người dùng đến từ một chiến dịch thu hút lại. Để khắc phục hạn chế này, bạn có thể đặt tên chiến dịch để biểu thị hoạt động thu hút lại.

<div id="re-engagement-with-deep-linking" />

### Thu hút lại bằng liên kết sâu

Một phần chính của việc Thu hút lại là đưa người dùng đến một hoạt động cụ thể. Ví dụ: nếu bạn quảng cáo một số sản phẩm hoặc đợt giảm giá. Trong những trường hợp như vậy, bạn sẽ muốn đưa những người dùng nhấp vào quảng cáo đến thẳng hoạt động của ứng dụng cho sản phẩm hoặc đợt giảm giá này.

Để thực hiện, bạn sử dụng Liên kết sâu. Dữ liệu chuyển đổi trong Liên kết sâu thực sự rất quan trọng. Dữ liệu này chứa thông tin cần thiết để nhà phát triển tùy chỉnh trải nghiệm người dùng và đưa họ đến đúng hoạt động.

<div id="reengagement-deep-linking-with-srns" />

<Accordion title="Thu hút lại: liên kết sâu với SRN">

Dữ liệu chuyển đổi không có sẵn khi người dùng được thu hút lại đến từ SRN. Nhà phát triển cần sử dụng các phương thức SRN để có được nó khi khởi chạy ứng dụng.

</Accordion>

<div id="reengagement-deep-linking-with-ad-networks" />

<Accordion title="Thu hút lại: liên kết sâu với mạng quảng cáo">

Khi người dùng được thu hút lại và ứng dụng khởi chạy, dữ liệu chuyển đổi sau sẽ có sẵn trong phương thức `onAppOpenAttribution`:

Đối với cả iOS và Android, khi dùng phiên bản rút gọn của OneLink, dữ liệu chuyển đổi sẽ là một bản đồ có cấu trúc chứa tất cả các thông số trong liên kết:

Ví dụ:

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* Nhà phát triển ứng dụng có thể sử dụng các thông số như vậy, như `af_dp` và tên chiến dịch, để đưa người dùng đến một hoạt động cụ thể và cung cấp nội dung có liên quan.

<div id="important-1" />

> 🚧 **Quan trọng!**
>
> Chúng tôi đề nghị bạn nên sử dụng phiên bản rút gọn của OneLink. Nhấp vào <Anchor target="_blank" href="/marketers/vi/docs/understand-onelink-short-vs-long-urls">đây</Anchor> để tìm hiểu thêm.

Một lý do khác để sử dụng phiên bản rút gọn của OneLink là cấu trúc dữ liệu chuyển đổi mà phiên bản đầy đủ trả về. Khi sử dụng phiên bản đầy đủ, dữ liệu chuyển đổi là một bản đồ với một trường duy nhất được gọi là `link` chứa toàn bộ OneLink đầy đủ.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

<div id="alternative-conversion-data-sources" />

### Nguồn dữ liệu chuyển đổi thay thế

* API Push cung cấp tải trọng chuyển đổi chi tiết cho biết đó là phân bổ lại hay thu hút lại. Tải trọng API Push bao gồm một trường được gọi là `re_targeting_conversion_type`. Trường này cho biết loại chuyển đổi, là phân bổ lại hay thu hút lại. Để tìm hiểu thêm, hãy xem phần <Anchor target="_blank" href="/marketers/vi/docs/push-api-streaming-raw-data">hướng dẫn API Push</Anchor> của chúng tôi.
* Báo cáo Dữ liệu Thô cũng chứa các chỉ số cho loại chuyển đổi. Trong báo cáo dữ liệu thô đối với chuyển đổi nhắm mục tiêu lại, có một cột được gọi là ***Event Name***. Giá trị trong cột này là ***lượt thu hút lại*** hoặc ***phân bổ lại*** theo loại chuyển đổi.

<div id="note-3" />

<div id="examples-of-mixed-user-acquisition-and-re-attribution" />

### Ví dụ về thu hút người dùng và phân bổ lại kết hợp

> 📄
>
> 1. Một người dùng cài đặt ứng dụng của bạn rồi gỡ cài đặt ứng dụng đó. Hành động cài đặt sẽ cho người dùng vào một <Anchor target="_blank" href="/marketers/vi/docs/set-up-re-attribution-window">khung thời gian phân bổ lại</Anchor>. Bạn đặt chiến dịch chuyển đổi người dùng (không nhắm mục tiêu lại) bằng Meta ads. Bạn cũng thiết lập tích hợp AppsFlyer với Meta ads để cho phép nhắm mục tiêu lại.
>
>    Khi vẫn trong khung thời gian phân bổ lại, người dùng sẽ nhìn thấy quảng cáo, nhấp vào quảng cáo đó và cài đặt lại ứng dụng. Theo nhận định của AppsFlyer, người dùng đó là người dùng được phân bổ lại.
>
>    Điều này là do hai yếu tố:
>    1. Cấu hình với Meta ads cho phép nhắm mục tiêu lại
>    2. Người dùng đang ở trong khung thời gian phân bổ lại
>    Trong trường hợp này, tên chiến dịch không biểu thị là phân bổ lại.
> 2. Hãy lấy ví dụ tương tự, chỉ là lần này người dùng không ở trong khung thời gian phân bổ lại. Trong trường hợp này, cài đặt là lượt cài đặt không tự nhiên mới.
> 3. Hãy xét một ví dụ khác. Bạn đặt chiến dịch nhắm mục tiêu lại trên Meta ads. Một số người dùng xem được chiến dịch và cài đặt ứng dụng. Tuy nhiên, đây là những người dùng cài đặt ứng dụng lần đầu. Những người dùng như vậy không được coi là người dùng được phân bổ lại. Thay vào đó, AppsFlyer coi họ là những người dùng đến từ chiến dịch thu hút người dùng.

<div data-zendesk-anchors="overview=t%E1%BB%95ng-quan h_01HCY86CKDJK9TNHPAZB0QX2ZX=t%E1%BB%95ng-quan nonorganic-conversion-data-payload-fields=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-t%E1%BA%A3i-tr%E1%BB%8Dng-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-kh%C3%B4ng-t%E1%BB%B1-nhi%C3%AAn h_01HCY86CKDEMB3428YHCNJQA5R=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-t%E1%BA%A3i-tr%E1%BB%8Dng-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-kh%C3%B4ng-t%E1%BB%B1-nhi%C3%AAn fields-always-available=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-lu%C3%B4n-kh%E1%BA%A3-d%E1%BB%A5ng h_01HCY86CKDBQRGAY7GHNBJE4WK=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-lu%C3%B4n-kh%E1%BA%A3-d%E1%BB%A5ng fields-available-in-some-cases=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-kh%E1%BA%A3-d%E1%BB%A5ng-trong-m%E1%BB%99t-s%E1%BB%91-tr%C6%B0%E1%BB%9Dng-h%E1%BB%A3p h_01HCY86CKDYQMYB9BQ4MXWP8A5=c%C3%A1c-tr%C6%B0%E1%BB%9Dng-kh%E1%BA%A3-d%E1%BB%A5ng-trong-m%E1%BB%99t-s%E1%BB%91-tr%C6%B0%E1%BB%9Dng-h%E1%BB%A3p additional-fields=c%C3%A1c-tr%C6%B0%E1%BB%9Fng-b%E1%BB%95-sung h_01HCY86CKD47M85AZVEA5C4JH7=c%C3%A1c-tr%C6%B0%E1%BB%9Fng-b%E1%BB%95-sung limitations=%C4%91i%E1%BB%83m-h%E1%BA%A1n-ch%E1%BA%BF h_01HCY86CKEFX646H9BSKSFGZ36=%C4%91i%E1%BB%83m-h%E1%BA%A1n-ch%E1%BA%BF h_01HCY86CKEZ2483XB461M2C9EC=custom-parameter-names ua-conversion-data-with-srns=d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-ua-v%E1%BB%9Bi-srn h_01EGKTQN6XDYHA60P2WKHBBVFT=d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-ua-v%E1%BB%9Bi-srn a-note-about-facebook=l%C6%B0u-%C3%BD-v%E1%BB%81-meta-ads h_01HCY86CKENFEGX53G9G4SGPSK=l%C6%B0u-%C3%BD-v%E1%BB%81-meta-ads facebook-conversion-data=d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-meta-ads h_01HCY86CKE658H36F3VJQMATQK=d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-meta-ads h_01HCY86CKF6FY96PAWB5Y7YXSQ=google-ads-conversion-data h_01HCY86CKFMNNNJZTPGK4870YN=apple-search-ads-conversion-data h_01HCY86CKF26JRT64JR9JZEAKJ=snapchat-conversion-data h_01HCY86CKFM94SQWYARCM0GEJ9=twitter-conversion-data h_01HCY86CKFS5SJBECSY42VRJWP=oath-ad-platforms-conversion-data ua-conversion-with-other-ad-networks=chuy%E1%BB%83n-%C4%91%E1%BB%95i-ua-v%E1%BB%9Bi-c%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o-kh%C3%A1c h_01HCY86CKFB0GEJRTYSXN9YZ08=chuy%E1%BB%83n-%C4%91%E1%BB%95i-ua-v%E1%BB%9Bi-c%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o-kh%C3%A1c h_01HCY86CKFY787RD4BHQDVEVFV=applovin attribution-link=%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 h_01HCY86CKFXM5XXJZSPXPB6397=%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95 payload=t%E1%BA%A3i-tr%E1%BB%8Dng h_01HCY86CKFDDXWT2KKFTKKBGHM=t%E1%BA%A3i-tr%E1%BB%8Dng h_01HCY86CKFV55GYY7C51D7F72S=ironsource attribution-link::a45a1b4a=%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95-1 h_01HCY86CKFYGEYR2TRPSD87KDA=%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95-1 payload::81867f5c=t%E1%BA%A3i-tr%E1%BB%8Dng-1 h_01HCY86CKFKKFQDG1P42R1FSDJ=t%E1%BA%A3i-tr%E1%BB%8Dng-1 retargeting-conversion-data=nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i h_01EHQ74JS84509GT6M93SZA4HX=nh%E1%BA%AFm-m%E1%BB%A5c-ti%C3%AAu-l%E1%BA%A1i-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i h_01HCY86CKFP0DWCFMKSB1V130D=l%E1%BB%9Di-khuy%C3%AAn reattribution-with-srns=ph%C3%A2n-b%E1%BB%95-l%E1%BA%A1i-v%E1%BB%9Bi-srn h_01HCY86CKFAVWP1W0ZNEN5P30A=ph%C3%A2n-b%E1%BB%95-l%E1%BA%A1i-v%E1%BB%9Bi-srn h_01HCY86CKF2QY9DV1J9MWHKJ5P=l%C6%B0u-%C3%BD reattribution-with-regular-ad-networks=ph%C3%A2n-b%E1%BB%95-l%E1%BA%A1i-v%E1%BB%9Bi-c%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o-th%C3%B4ng-th%C6%B0%E1%BB%9Dng h_01HCY86CKF1PV8MRR902RAHQGW=ph%C3%A2n-b%E1%BB%95-l%E1%BA%A1i-v%E1%BB%9Bi-c%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o-th%C3%B4ng-th%C6%B0%E1%BB%9Dng h_01HCY86CKF1RGK01VTV3EEHQVM=retargeting-campaign-with-criteo attribution-link::c16e96bb=%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95-2 h_01HCY86CKFSKBBMFKA8NN8XTPC=%C4%91%C6%B0%E1%BB%9Dng-d%E1%BA%ABn-ph%C3%A2n-b%E1%BB%95-2 conversion-data-payload=t%E1%BA%A3i-tr%E1%BB%8Dng-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i h_01HCY86CKG2YQQC629SC3RAFKE=t%E1%BA%A3i-tr%E1%BB%8Dng-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i reattribution-with-deferred-deep-linking=ph%C3%A2n-b%E1%BB%95-l%E1%BA%A1i-v%E1%BB%9Bi-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-b%E1%BB%8B-tr%C3%AC-ho%C3%A3n h_01HCY86CKGXV50H79R0YH1GB2C=ph%C3%A2n-b%E1%BB%95-l%E1%BA%A1i-v%E1%BB%9Bi-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-b%E1%BB%8B-tr%C3%AC-ho%C3%A3n h_01HCY86CKG12YRGFEEJ27DQART=deferred-deep-linking-with-srns conversion-data-for-deferred-deep-linking-with-facebook=d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-cho-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-b%E1%BB%8B-tr%C3%AC-ho%C3%A3n-v%E1%BB%9Bi-meta-ads h_01HCY86CKGX9VHSV3ASKXMFM0X=d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-cho-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u-b%E1%BB%8B-tr%C3%AC-ho%C3%A3n-v%E1%BB%9Bi-meta-ads h_01HCY86CKGHM9FKBEHMYBF4597=v%C3%AD-d%E1%BB%A5 h_01HCY86CKG3XWM4X0YH7WYCEH4=deferred-deep-linking-with-attribution-links uri-schemes=l%C6%B0%E1%BB%A3c-%C4%91%E1%BB%93-uri h_01HCY86CKGDM2NE1FCRC92K8R0=l%C6%B0%E1%BB%A3c-%C4%91%E1%BB%93-uri ios-universal-links-and-android-app-links=li%C3%AAn-k%E1%BA%BFt-chung-ios-v%C3%A0-li%C3%AAn-k%E1%BA%BFt-%E1%BB%A9ng-d%E1%BB%A5ng-android h_01HCY86CKGY1NE4214DES0Y2AV=li%C3%AAn-k%E1%BA%BFt-chung-ios-v%C3%A0-li%C3%AAn-k%E1%BA%BFt-%E1%BB%A9ng-d%E1%BB%A5ng-android h_01HCY86CKG1NGYR8WCS7NMM782=quan-tr%E1%BB%8Dng h_01HCY86CKG9VF8MBJQTWJGDJ6Z=l%C6%B0u-%C3%BD-1 reengagement-with-srns=thu-h%C3%BAt-l%E1%BA%A1i-v%E1%BB%9Bi-srn h_01HCY86CKG4TRYR6TWYYVB0FJE=thu-h%C3%BAt-l%E1%BA%A1i-v%E1%BB%9Bi-srn reengagement-with-regular-ad-networks=thu-h%C3%BAt-l%E1%BA%A1i-b%E1%BA%B1ng-c%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o-th%C3%B4ng-th%C6%B0%E1%BB%9Dng h_01HCY86CKGM2JS7C9T71R6GPH1=thu-h%C3%BAt-l%E1%BA%A1i-b%E1%BA%B1ng-c%C3%A1c-m%E1%BA%A1ng-qu%E1%BA%A3ng-c%C3%A1o-th%C3%B4ng-th%C6%B0%E1%BB%9Dng reengagement-with-deep-linking=thu-h%C3%BAt-l%E1%BA%A1i-b%E1%BA%B1ng-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u h_01HCY86CKG0NPQAA2ZRWWNKGQD=thu-h%C3%BAt-l%E1%BA%A1i-b%E1%BA%B1ng-li%C3%AAn-k%E1%BA%BFt-s%C3%A2u h_01HCY86CKGEBHQVFRGJH96KDFJ=reengagement-deep-linking-with-srns h_01HCY86CKGJ9HG7AGB5MFP33RK=reengagement-deep-linking-with-ad-networks h_01HCY86CKGC3AF6YDKTY95XMV5=quan-tr%E1%BB%8Dng-1 alternative-conversion-data-sources=ngu%E1%BB%93n-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-thay-th%E1%BA%BF h_01HCY86CKG3N6ZXV70G4VMZ0X5=ngu%E1%BB%93n-d%E1%BB%AF-li%E1%BB%87u-chuy%E1%BB%83n-%C4%91%E1%BB%95i-thay-th%E1%BA%BF examples-of-mixed-user-acquisition-and-reattribution=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-thu-h%C3%BAt-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-v%C3%A0-ph%C3%A2n-b%E1%BB%95-l%E1%BA%A1i-k%E1%BA%BFt-h%E1%BB%A3p h_01HCY86CKGK9DVVB7T6CVNB8ZN=v%C3%AD-d%E1%BB%A5-v%E1%BB%81-thu-h%C3%BAt-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-v%C3%A0-ph%C3%A2n-b%E1%BB%95-l%E1%BA%A1i-k%E1%BA%BFt-h%E1%BB%A3p" />
