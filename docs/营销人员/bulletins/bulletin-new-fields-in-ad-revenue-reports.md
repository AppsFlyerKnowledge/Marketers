---
title: 公告：广告收入报告中的新增字段
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-07-22T13:25:32Z'
  edited_at: '2026-10-14T10:09:53Z'
  id: 26907692192273
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/26907692192273
---

<Table>
  <tbody>
    <tr>
      <td>
        **最新动态**
      </td>
      <td>
        广告收入报告中增加了新的字段。
      </td>
    </tr>
    <tr>
      <td>
        **生效日期**
      </td>
      <td>
        2024年9月19日
      </td>
    </tr>
    <tr>
      <td>
        **须知事项**
      </td>
      <td>
        下表列分报告类型列出了对应的新增字段。如需进一步了解各字段的定义和详细信息，请参阅<Anchor target="_blank" href="/marketers/zh/docs/raw-data-field-dictionary">原始数据字段释义</Anchor>。

        | 报告 | API字段名称 |
        | --- | --- |
        | <Anchor target="_blank" href="/marketers/zh/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">旧版广告收入【单一版本报告】</Anchor> | * {"engagement_type"}<br />* {"custom_data"}<br />* {"customer_user_id"}<br />* {"ad_revenue_ad_type"} |
        | <Anchor target="_blank" href="/marketers/zh/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">广告收入【版本化报告】</Anchor> | * {"engagement_type"}<br />* {"custom_data"}<br />* {"customer_user_id"}<br />* {"ad_revenue_ad_type"} |
        | <Anchor target="_blank" href="/marketers/zh/docs/revenue-etl-reports#impression-level-report">广告收入【SDK展示层级】</Anchor> | * {"engagement_type"}<br />* {"custom_data"}<br />* {"customer_user_id"}<br />* {"ad_revenue_ad_type"}<br />* {"ad_revenue_custom_parameters"}<br />* {"app_version"}<br />* {"sdk_version"} |
      </td>
    </tr>
    <tr>
      <td>
        **待办事项**
      </td>
      <td>
        * 进入<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers#set-up-data-locker">AppsFlyer后台的Data Locker设置</Anchor>部分，选择您需要的新增字段，以便在您的报告中查看相关数据。  
          **提示**：
        * 针对新增字段对您的BI系统进行相应的配置，以便导入相关数据。
      </td>
    </tr>
  </tbody>
</Table>
