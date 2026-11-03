---
title: 广告系列名称变更
metadata:
  keywords:
    - Aggregated Data
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2023-03-26T10:56:19Z'
  edited_at: '2026-10-14T10:15:46Z'
  id: 14038324952465
  locale: zh-cn
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/zh-cn/articles/14038324952465
---
> **概要：**

## 广告系列名称变更

AppsFlyer显示广告系列数据时以广告系列ID为标识。

|  |  |
| --- | --- |
| 数据总览面板 |  |
| 活跃数据面板 | 是 |
| 群组面板 | 是 |
| Cohort API | 是 |
| Pull API |  |
| 数据透视表 | 否 |
| 自定义面板 | 否 |
| 留存面板 | 否 |
| 事件面板 | 否 |
| Protect360面板 | 否 |
| Cost ETL | 是 |
| SKAN总览面板 | 否 |

> 📄 **示例**
>
> ####
>
>
>
> | <span id="example-campaign-data"></span>Date | 即广告系列的名称 | 即广告系列的ID | 激活假量 | 广告消耗数据 |
> | --- | --- | --- | --- | --- |
> | 1月1日 | example\_a1 | 123 | 100 | $100 |
> | 1月2日 | example\_a2 | 123 | 200 | $200 |
>
>
>
> ####
>
>
>
> <table><tbody><tr><th><p><span><span id="overview-dashboard-display-before-the-behavior-change"></span>Campaign</span></p></th><th><p><span>即广告系列的ID</span></p></th><th><p><span>激活假量</span></p></th><th><p><span>广告消耗数据</span></p></th></tr><tr><td><p><span>example_a2</span></p></td><td><p><span>123</span></p></td><td><p><span>300</span></p></td><td><p><span>$300</span></p></td></tr><tr><td colspan="4"><p>结果：</p></td></tr></tbody></table>

### 【推荐方式】：

* 请勿对同一个广告系列名称使用不同的广告系列ID。

<div data-zendesk-anchors="rollout-details=%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E5%90%8D%E7%A7%B0%E5%8F%98%E6%9B%B4 h_01HW896QQ2T4J0N5PDY6YFTJ49=%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E5%90%8D%E7%A7%B0%E5%8F%98%E6%9B%B4 h_01HW896QQ34YVGF6P212ZHAQHG=%E7%A4%BA%E4%BE%8B h_01HW896QQ3G07XM06HR2CRXA3G=example-campaign-data h_01HW896QQ3J9NE9GZRKKAPX46B=overview-dashboard-display-before-the-behavior-change best-practice=%E6%8E%A8%E8%8D%90%E6%96%B9%E5%BC%8F h_01HW896QQ4RAQ51GPD17YYZBJF=%E6%8E%A8%E8%8D%90%E6%96%B9%E5%BC%8F" />
