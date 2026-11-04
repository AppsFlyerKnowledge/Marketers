---
title: Thuộc tính của chiến dịch
metadata:
  keywords:
    - cost
    - Advertisers
    - Xpend
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2021-06-02T17:21:22Z'
  edited_at: '2023-09-11T01:51:31Z'
  id: 360020994977
  locale: vi
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/vi/articles/360020994977
---
> **Khái quát:** Tìm hiểu về các thuộc tính của chiến dịch và cách chúng hiển thị trong dữ liệu ETL Chi phí của AppsFlyer.

<div id="about-campaign-properties" />

## Giới thiệu về thuộc tính của chiến dịch

Thuộc tính của chiến dịch là một nhóm các phương diện đặc biệt đại diện cho các tùy chọn cài đặt khác nhau của một chiến dịch quảng cáo, bao gồm mục tiêu chiến dịch, loại hình đấu thầu và số tiền đấu thầu. Đây là các tùy chọn cài đặt bạn thường xem và chỉnh sửa trong bảng điều khiển mạng quảng cáo của mình, nhưng AppsFlyer kéo các phương diện thuộc tính chiến dịch và cung cấp dữ liệu trong ETL Chi phí, giống như bạn xem các phương diện khác.

Với dữ liệu thuộc tính của chiến dịch, bạn có thể:

* Xem tất cả các thay đổi về đấu thầu do nhóm UA của bạn thực hiện.
* Đo lường và phân tích tính hiệu quả của việc thay đổi đấu thầu và liệu điều đó có mang lại hiệu quả mong muốn hay không.

Dữ liệu thuộc tính chiến dịch AppsFlyer có sẵn cho quảng cáo Meta và Google. Xem các dữ liệu AppsFlyer kéo và cách dữ liệu được chuẩn hóa và ánh xạ tới từng mạng quảng cáo trong các phần tiếp theo.

<div id="facebook" />

<Accordion title="Quảng cáo Meta">

Xem các dữ liệu AppsFlyer kéo và cách dữ liệu được chuẩn hóa và ánh xạ tới quảng cáo Meta trong bảng tiếp theo.

<Table>
  <thead>
    <tr>
      <th>
        Phương diện
      </th>
      <th>
        Mô tả
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Mục tiêu chiến dịch
      </td>
      <td>
        Kéo từ: [campaign.objective](https://developers.facebook.com/docs/marketing-api/reference/ad-campaign-group/insights)
      </td>
    </tr>
    <tr>
      <td>
        Mô hình Chi phí
      </td>
      <td>
        Kéo từ: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview#opt">adset.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Ánh xạ mô hình chi phí chuẩn hóa của AppsFlyer
      </td>
      <td>
        | Mô hình Chi phí | Mô hình chi phí chuẩn hóa |
        | --- | --- |
        | * {"LINK_CLICKS"}<br />* {"POST_ENGAGEMENT"}<br />* REPLIES<br />* {"LANDING_PAGE_VIEWS"} | CPC |
        | * {"OFFSITE_"} CONVERSIONS<br />* {"DERIVED_EVENTS"}<br />* {"LEAD_GENERATION"} | CPA |
        | APP\_INSTALLS | CPI |
        | VALUE | ROI |
        | * REACH<br />* IMPRESSIONS<br />* SOCIAL\_IMPRESSIONS | CPM |
        | * THRUPLAY<br />* VIDEO\_VIEWS<br />* TWO\_SECOND\_CONTINUOUS\_VIDEO\_VIEWS | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        Chiến lược đấu thầu
      </td>
      <td>
        Kéo từ: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">adset.bid\_strategy</Anchor>

        Nếu không có bid\_strategy ở cấp độ bộ quảng cáo thì: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">campaign.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Chiến lược đấu thầu chuẩn hóa của AppsFlyer
      </td>
      <td>
        | Chiến lược đấu thầu | Chiến lược đấu thầu chuẩn hóa |
        | --- | --- |
        | * {"LOWEST_COST_"} {"WITHOUT_CAP"}<br />* {"COST_CAP"}<br />* {"LOWEST_COST_"} {"WITH_MIN_ROAS"} | Đấu thầu tự động |
        | TARGET\_COST | Đấu thầu mục tiêu |
        | Mọi thứ khác | Không xác định |
      </td>
    </tr>
    <tr>
      <td>
        Số tiền đấu thầu
      </td>
      <td>
        Số tiền đấu thầu bằng tiền tệ của nhà quảng cáo
      </td>
    </tr>
    <tr>
      <td>
        Số tiền đấu thầu gốc
      </td>
      <td>
        Kéo từ: adset.bid\_amount
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="google" />

<Accordion title="Google">

Xem các dữ liệu AppsFlyer kéo và cách dữ liệu được chuẩn hóa và ánh xạ tới Google trong bảng tiếp theo.

<Table>
  <thead>
    <tr>
      <th>
        Phương diện
      </th>
      <th>
        Mô tả
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Mục tiêu chiến dịch
      </td>
      <td>
        Kéo từ: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.advertising_channel_sub_type">campaign.advertising\_channel\_sub\_type</Anchor>

        Lưu ý: Việc điền vào các trường sau phụ thuộc vào channel\_sub\_type:

        * AC: APP\_CAMPAIGN hoặc APP\_CAMPAIGN\_FOR\_ENGAGEMENT
        * Không phải AC: Mọi giá trị khác cho channel\_sub\_type
      </td>
    </tr>
    <tr>
      <td>
        Mô hình Chi phí
      </td>
      <td>
        * Đối với AC, kéo từ: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type">Campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type</Anchor>
        * Đối với không phải AC, kéo từ: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type">Campaign.bidding\_strategy\_type</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Ánh xạ mô hình chi phí chuẩn hóa của AppsFlyer
      </td>
      <td>
        <table><thead><tr><th colspan="2">Mô hình Chi phí</th><th>Mô hình chi phí chuẩn hóa</th></tr></thead><tbody><tr><td rowspan="4"> <span>AC</span><span><br/></span> </td><td><ul><li>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</li><li>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</li></ul></td><td><span>CPI</span></td></tr><tr><td><p>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</p></td><td><span>CPA</span></td></tr><tr><td>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</td><td><span>ROI</span></td></tr><tr><td><ul><li>UNKNOWN</li><li>UNSPECIFIED</li></ul></td><td><span>Khác</span></td></tr><tr><td>Không phải AC</td><td><ul><li>REACH</li><li>ENHANCED_CPC</li><li>MANUAL_CPC</li><li>PERCENT_CPC</li><li>TARGET_SPEND</li></ul></td><td><span>CPC</span></td></tr><tr><td> </td><td><ul><li>MANUAL_CPM</li><li>TARGET_CPM</li><li>TARGET_IMPRESSION_SHARE</li></ul></td><td><span>CPM</span></td></tr><tr><td> </td><td>MANUAL_CPV</td><td><span>CPCV</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSIONS</li><li>TARGET_CPA</li></ul></td><td><span>CPA</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSION_VALUE</li><li>TARGET_ROAS</li></ul></td><td><span>ROI</span></td></tr><tr><td><span> </span></td><td><ul><li>COMMISSION</li><li>PAGE_ONE_PROMOTED</li><li>TARGET_OUTRANK_SHARE</li><li>UNKNOWN</li><li>UNSPECIFIED</li></ul></td><td><span>Khác</span></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        Chiến lược đấu thầu
      </td>
      <td>
        * Đối với AC, kéo từ: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type">Campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type</Anchor>
        * Đối với không phải AC, kéo từ: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type">Campaign.bidding\_strategy\_type</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Chiến lược đấu thầu chuẩn hóa của AppsFlyer
      </td>
      <td>
        <table><thead><tr><th colspan="2"><font> <span>Chiến lược đấu thầu</span> </font></th><th><font> <span>Chiến lược đấu thầu chuẩn hóa</span> </font></th></tr></thead><tbody><tr><td rowspan="3"><font><span>AC</span> </font></td><td><ul><li><font> <span>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</span> </font></li></ul></td><td><font> <span>Đấu thầu tối đa</span> </font></td></tr><tr><td><ul><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</span> </font></li></ul></td><td><font> <span>Đấu thầu mục tiêu</span> </font></td></tr><tr><td><ul><li><font> <span>UNKNOWN</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Khác</span> </font></td></tr><tr><td rowspan="5"><font> <span>Không phải AC</span> </font></td><td><ul><li><font> <span>ENHANCED_CPC</span> </font></li><li><font> <span>MANUAL_CPC</span> </font></li><li><font> <span>MANUAL_CPM</span> </font></li><li><font> <span>MANUAL_CPV</span> </font></li></ul></td><td><font> <span>Đấu thầu thủ công</span> </font></td></tr><tr><td><ul><li><font> <span>MAXIMIZE_CONVERSIONS</span> </font></li><li><font> <span>MAXIMIZE_CONVERSION_VALUE</span> </font></li><li><font> <span>PAGE_ONE_PROMOTED</span> </font></li><li><font> <span>TARGET_IMPRESSION_SHARE</span> </font></li><li><font> <span>TARGET_OUTRANK_SHARE</span> </font></li><li><font> <span>TARGET_SPEND</span> </font></li></ul></td><td><font> <span>Đấu thầu tự động</span> </font></td></tr><tr><td><ul><li><font> <span>PERCENT_CPC</span> </font></li><li><font> <span>TARGET_CPA</span> </font></li><li><font> <span>TARGET_CPM</span> </font></li><li><font> <span>TARGET_ROAS</span> </font></li></ul></td><td><font> <span>Đấu thầu mục tiêu</span> </font></td></tr><tr><td><ul><li><font> <span>COMMISSION</span> </font></li><li><font> <span>UNKNOWN</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Khác</span> </font></td></tr><tr><td><font> <span>Mọi thứ khác</span> </font></td><td><font> <span>Không xác định</span> </font></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        Số tiền đấu thầu
      </td>
      <td>
        Số tiền đấu thầu bằng tiền tệ của nhà quảng cáo
      </td>
    </tr>
    <tr>
      <td>
        Số tiền đấu thầu gốc
      </td>
      <td>
        Kéo từ:    <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.target_cpa.target_cpa_micros">campaign.target\_cpa.target\_cpa\_micros</Anchor>
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="about-campaign-properties=gi%E1%BB%9Bi-thi%E1%BB%87u-v%E1%BB%81-thu%E1%BB%99c-t%C3%ADnh-c%E1%BB%A7a-chi%E1%BA%BFn-d%E1%BB%8Bch" />
