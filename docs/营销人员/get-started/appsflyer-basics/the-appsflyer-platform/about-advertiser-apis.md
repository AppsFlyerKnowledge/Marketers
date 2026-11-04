---
title: 关于广告主API
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-05-24T15:14:53Z'
  edited_at: '2026-10-14T10:14:34Z'
  id: 360009122638
  locale: zh-cn
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/zh-cn/articles/360009122638
---
> **概要：** 本文介绍了广告主可访问或更新数据的API接口。

<div id="advertiser-api-list-and-interfaces" />

## 广告主API清单和接口说明

<span id="01EEQJERAWW3HY59HVPY3YWA0B"></span>有关数据报告和API接口信息，请查看：

* <span id="01EEQJERAW2ZTBWBQKBCDSC76Z"></span><span id="01EEQJERAWQ2WCPV0207XM6FR4"></span><Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview"><span id="01EEQJERAX0W7RCYQWVM2M5S13"></span>原始数据报告/API</Anchor>
* <span id="01EEQJERAWA09P200SGR985846"></span><span id="01EEQJERAW6AC6WR7E46T5DMHW"></span><Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview">汇总数据和分析数据报告/API</Anchor>

<div id="interfaces-for-advertisers" />

#### 广告主可用接口

| 功能领域 | API 名称 | ![af_premium.png](https://files.readme.io/ad0c279c48242ea25529f1bc386ee2c747bcd332f5fb1eb2fc26dd378a257f6e-4403570953105.png)<br /><br />高级功能 | 说明 | 身份验证  <br />token/key | 接口类型 |
| --- | --- | --- | --- | --- | --- |
| 移动归因 | <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">服务器到服务器事件</Anchor> | 否 | 记录在移动应用外部发生的应用内事件 | <Anchor target="_blank" href="/marketers/zh/docs/app-settings#sdk-authentication-dev-key">SDK开发者密钥</Anchor> | REST API |
| 基于用户的归因（PBA） | <Anchor target="_blank" href="/marketers/zh/docs/web-server-to-server-events-api-for-pba-web-s2s">服务器到服务器web</Anchor> | 否 | 上报后台发生的PBA事件 | <Anchor target="_blank" href="/marketers/zh/docs/pba-brand-bundles-and-settings#管理品牌套件">PBA密钥</Anchor> | REST API |
| 广告交互 | <Anchor target="_blank" href="/marketers/zh/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink</Anchor> | 是 | 管理OneLinks：创建、更新、查询、删除 | <Anchor target="_blank" href="/marketers/zh/docs/app-settings#sdk-authentication-dev-key">SDK开发者密钥</Anchor> | REST API |
| 再营销 | <Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#import-an-audience">受众共享</Anchor> | 是 | 将用户列表上传到受众共享 | <Anchor target="_blank" href="/marketers/zh/docs/audiences-import-audience-segments-from-internal-systems">导入密钥</Anchor> | REST API |
| 隐私管理 | <Anchor target="_blank" href="/marketers/zh/docs/send-opendsr-api-requests">openDSR请求</Anchor> | 否 | 提交数据删除请求并查看状态 | <Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 报告功能 | <Anchor target="_blank" href="/marketers/zh/docs/master-api-user-acquisition-metrics-via-api">主绩效KPI</Anchor> | 是 | 以CSV文件导出多个应用的广告绩效指标 | <Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 报告功能 | <Anchor target="_blank" href="/marketers/zh/docs/pull-api-aggregate-data">拉取汇总报告</Anchor> | 否 | 以CSV文件获取汇总报告 | <Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 报告功能 | <Anchor target="_blank" href="/marketers/zh/docs/pull-api-raw-data">拉取原始数据</Anchor> | 是 | 以CSV文件获取原始数据报告 | <Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 报告功能 | <Anchor target="_blank" href="/marketers/zh/docs/cohort-api">群组分析</Anchor> | 是 | JSON或CSV文件中的群组指标 | <Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 报告功能 | <Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">Data Locker</Anchor> | 是 | 原始和汇总数据报告 | N/A | 云存储 |
| 移动归因 | <Anchor target="_blank" href="/marketers/zh/docs/push-api-streaming-raw-data">推送</Anchor> | 是 | 将实时激活与应用内事件推送至广告主服务器 | N/A | REST API |
| 广告成本 | <Anchor target="_blank" href="/partners/zh/docs/cost-import-for-ad-networks">成本导入</Anchor> | 否 | 上报活动成本数据 | N/A | 文件上传 |
| 账户管理 | <Anchor target="_blank" href="/marketers/zh/docs/app-list-api-for-app-owners">获取应用列表</Anchor> | 否 | 获取账户中的应用列表 | <Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| 报告功能 | <Anchor target="_blank" href="/marketers/zh/docs/set-up-and-use-roi360-cost-etl-reports">ETL成本</Anchor> | 是 | 细颗粒度ETL成本数据 | N/A | 云存储 |
| 报告功能 | <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#reporting-options">SKAN数据上报</Anchor> | 否 | SKAN汇总报告 | V2.0 | REST API |
| 合作渠道管理 | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-copy">复制渠道对接设置</Anchor> | 否 | 将对接配置参数从一个应用复制到另一个应用 | V2.0 | REST API |
| 合作渠道管理 | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">设置Install Referrer Decryption Key</Anchor> | 否 | 设置从Meta Ads 获取的Install Referrer Decryption Key | V2.0 | REST API |

<div data-zendesk-anchors="advertiser-api-list-and-interfaces=%E5%B9%BF%E5%91%8A%E4%B8%BBapi%E6%B8%85%E5%8D%95%E5%92%8C%E6%8E%A5%E5%8F%A3%E8%AF%B4%E6%98%8E h_01HX9638DX6EHR4ETMSH10K68F=%E5%B9%BF%E5%91%8A%E4%B8%BBapi%E6%B8%85%E5%8D%95%E5%92%8C%E6%8E%A5%E5%8F%A3%E8%AF%B4%E6%98%8E interfaces-for-advertisers=%E5%B9%BF%E5%91%8A%E4%B8%BB%E5%8F%AF%E7%94%A8%E6%8E%A5%E5%8F%A3 h_01HX9638DXNJM3A968A2PSRRKS=%E5%B9%BF%E5%91%8A%E4%B8%BB%E5%8F%AF%E7%94%A8%E6%8E%A5%E5%8F%A3" />
