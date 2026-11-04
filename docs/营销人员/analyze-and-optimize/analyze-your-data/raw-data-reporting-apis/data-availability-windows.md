---
title: 数据可用期限
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2022-01-04T03:33:13Z'
  edited_at: '2026-10-14T10:05:51Z'
  id: 4415473374865
  locale: zh-cn
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/zh-cn/articles/4415473374865
---
> **概要：** 数据可用性取决于报告类型和定义的可用性窗口。

<div id="data-availability-windows" />

## 数据可用期限

* **可用性窗口**和**数据保留**这两个术语的含义不同。<Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">数据保留</Anchor>是指原始数据在服务器上保留的时间，其时长超过可用窗口期。
* 窗口期时长取决于您的套餐。
* 本文不适用于<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">Data Locker</Anchor>。

<div id="raw-data-availability-window" />

### 数据可用期限

可用性窗口限制了Pull API和原始数据导出页面提供的原始数据。窗口期的时长取决于报告类型，详见下表。

| 报告事件类型 | 报告类型示例 | 默认可用窗口 |
| --- | --- | --- |
| 归因到的转化 | 自然激活、非自然激活、再营销转化、卸载 | 在过去的 90 天中有 60 天 |
| 应用内事件 | 自然应用内事件、非自然应用内事件、再营销应用内事件 | 在过去的 90 天中有 31 天 |

<div id="aggregated-data-availability-window" />

### 汇总数据可用性窗口

Pull API和汇总数据导出页面的数据可用性窗口期有限。窗口期的时长取决于报告类型，详见下表。

| 报告 | 可用窗口期 |
| --- | --- |
| 汇总报告 | 25个月（2年+1个月），<Anchor target="_blank" href="/marketers/zh/docs/bulletin-aggregated-ltv-data-availability">从首次安装</Anchor>应用开始 |

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/report-generation-quotas-rate-limitations">报告生成限额</Anchor>

<div data-zendesk-anchors="data-availability-windows=%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%9C%9F%E9%99%90 h_01HE0FT9CNECNKYMVX9ZJJ9DNV=%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%9C%9F%E9%99%90 raw-data-availability-window=%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%9C%9F%E9%99%90-1 h_01HE0FT9CNS4N1GD1AYRBSRWPF=%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%9C%9F%E9%99%90-1 aggregated-data-availability-window=%E6%B1%87%E6%80%BB%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7%E7%AA%97%E5%8F%A3 h_01HE0FT9CPW91ASDH9MEW083ZH=%E6%B1%87%E6%80%BB%E6%95%B0%E6%8D%AE%E5%8F%AF%E7%94%A8%E6%80%A7%E7%AA%97%E5%8F%A3 h_01HE7S7VH4PC6FQAYKP6A0G4YY=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
