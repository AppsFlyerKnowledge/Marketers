---
title: 公告：
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
  edited_at: '2026-10-14T10:09:03Z'
  id: 12399683708305
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/12399683708305
---
| **最新动态** | 为了提高API的安全性和可靠性，我们已将API URL中的API V1 token换成API V2 token。V2是一个基于JWT的token，通过请求头（header）传递，用于Bearer认证。<br /><br />2023年9月18日起，API V1 token及其API已停止使用。 |
| --- | --- |
| **生效日期** | 2023年9月18日 |
| **前期准备**： | 只有管理员用户才能从AppsFlyer面板中获取<Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens#token的获取方式">API V2 token</Anchor>。 |
| **影响范围** | 仍在使用API token V1广告主和代理都需要更新其token。 |
| **API V1 token的查找方式** | 您可以通过<Anchor target="_blank" href="/marketers/zh/docs/audit-log">审计日志</Anchor>来查找仍在使用中的API V1 token，然后以CSV格式下载该数据，具体方法如下：<ol><li>进入审计日志面板。</li><li>在搜索栏中输入“API Token V1“。</li><li>在**Service**筛选框中，仅选择**API calls**，然后筛选结果。</li><li>点击页面右上角的下载图标。<br />您下载的CSV文件中包括您的应用ID、所使用的服务以及相关的API调用链接。</li></ol> |
| **亟需处理** | **使用API V2 token更新以下API：**<ol><li>进入<Anchor target="_blank" href="https://hq1.appsflyer.com/account/api-tokens">API token页面</Anchor>。</li><li>在API token V2.0下，点击**复制到剪切板**图标。</li><li>逐一更新以下所有API：<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/master_api_get">Master API V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">汇总数据Pull API V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">原始数据Pull API V2</Anchor></li></ul><ol><li>将API V1 URL替换为以上链接文档中的URL。</li><li>将您刚刚复制的token粘贴到Bearer认证请求头中。<br />![token_v2_bearer.png](https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png)</li><li>`'Authorization': 'Bearer %AuthTokenV2%'`</li></ol></li></ol> |
| **API token详情** | **下列文档可帮助您进一步了解API token：**<ul><li>API token管理指南<ul><li>Master API</li><li>汇总数据Pull API</li><li><Anchor target="_blank" href="/marketers/zh/docs/pull-api-raw-data">原始数据</Anchor></li><li><Anchor target="_blank" href="/marketers/zh/docs/send-opendsr-api-requests#gdpr请求格式">OpenDSR API</Anchor></li></ul></li></ul> |