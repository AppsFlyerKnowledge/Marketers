---
title: TikTok for Business与AppsFlyer的SKAN互通性
metadata:
  keywords:
    - Advertisers
    - ios14
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-03-14T12:05:58Z'
  edited_at: '2026-10-14T10:12:20Z'
  id: 360018499098
  locale: zh-cn
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/zh-cn/articles/360018499098
---
> **概要：** 启用AppsFlyer与TT4B的SKAN互通设置后，TikTok就能向AppsFlyer发送SKAN回传，同时AppsFlyer也能与TikTok分享广告主的CV值映射构架。

<div id="skan-interoperability-appsflyer---tiktok" />

## SKAN互通：AppsFlyer &lt;-> TikTok

如果您与多个广告平台合作，建议您在AppsFlyer后台设置您与这些渠道的SKAN互通，这样您就可以利用AppsFlyer平台上的其他可用指标（如成本等）来扩充SKAN的效果指标数据。

<div id="scope-of-skan-interoperability-with-tiktok" />

### AppsFlyer与TikTok的SKAN互通作用范围

AppsFlyer和TikTok会共享SKAN转化值（CV）的映射信息（在AppsFlyer后台设置），这样广告主就能同时收到来自这两个平台的投放效果指标。在启用TikTok for Business对接时（无论是历史对接还是<Anchor target="_blank" href="/marketers/zh/docs/tiktok-for-business-advanced-srn-integration-setup">Advanced SRN</Anchor>对接），AppsFlyer将向TikTok提供数据事件用于广告优化。详情请见TikTok支持的<Anchor target="_blank" href="/marketers/zh/docs/skan-integrated-partners-list">扩展字段列表</Anchor>。

<div id="tiktok-for-business-guidance" />

### TikTok for Business投放配置

在配置您的TT4B广告时，请参考TikTok的说明文档<Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10000858">《iOS14的影响及指南》</Anchor>，并注意以下几点：

* 确保您使用的<Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">AppsFlyer SDK</Anchor>已更新至最新版本。
* 请为每一个通过TT4B推广的应用都[配置一个TikTok App ID](https://ads.tiktok.com/help/article?aid=10001060)。
  * TikTok App ID是在TikTok Ads Manager（TikTok广告管理平台）中生成的专属代号，TikTok通过该代号来确认广告主对其应用的所有权。
  * 虽然TikTok App ID不是必填项，但仍建议您输入所有应用的ID。  
    这有助于您更好地掌握TikTok For Business数据并解锁其他产品。
  * **请按以下步骤添加多个TikTok App ID：**
    1. 请输入您的第一个TikTok App ID。
    2. 按**回车键**。
    3. 输入下一个TikTok App ID。
  * 配置TikTok App ID不影响您在AppsFlyer中的数据。
  * 详情请见[iOS 14中与TikTok App ID相关的注意事项](https://ads.tiktok.com/help/article?aid=10001070)。
* 将[转化事件映射](/docs/skan-interoperation-with-tiktok-for-business#3)到bytedanceglobal\_int和tiktokglobal\_int。
* 查看投放限制以及合并账户/广告系列相关的指南。

请直接与您的TT4B客户经理沟通SKAN配置和策略规划事宜。

TikTok支持的SKAN功能如下：

* 通过转化衡量API对广告投放进行监测和优化。
* 上报TT4B中iOS专用广告系列的数据。

<div id="campaign-limits-for-dedicated-ios-14-campaigns" />

### iOS 14专用广告系列的投放限制

由于SKAN API的限制，专用于iOS 14的TT4B广告（包括用于拉新的App Install应用安装广告以及Dynamic Product Ads动态展示广告）具有以下局限性：

* ​​每个iOS应用仅限投放15个广告系列，每个广告系列仅能包含5个广告组。
* iOS专用广告系列：
  * 可以由多个广告账户创建，但在投的广告系列总数不能超过15个。
  * 所有相关目标下的广告系列都会计入该投放额度（15个），且达到上限后，广告主必须先停投、关闭或删除一个/多个在投的广告系列以空出相应的额度，然后等待至少72个小时，才能开始投放新的广告系列。

<div id="enabling-interoperation" />

### 启用互通设置

您需要在AppsFlyer和TikTok后台都完成相关设置，才能实现SKAN互通，但无需对应用本身做任何修改或互通设置。

**请按以下方式启用AppsFlyer与TikTok For Business之间的SKAN互通设置**：

| 步骤 | 操作 | 说明 |
| --- | --- | --- |
| <span id="1"></span>1 | 应用侧的前期准备 | <ul><li>在您的应用中接入最新版本的AppsFlyer SDK。</li></ul> |
| <span id="2"></span>2 | 检查SKAN设置 | 设置并启用AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">SKAN解决方案</Anchor>。<br /><br />**请按以下方式查看SKAN设置**：<ol><li>从AF后台进入**配置** > **SKAN转化值操作台**。</li><li>点击选项图标（⋮），并确认**SKAN衡量**开关已打开。<br />![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)</li><li>选择适合您需求的衡量模式。<br />详情请见<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">SKAN转化值操作台</Anchor>。</li><li>记下应用内事件的准确名称，在下一步流程中会用到。</li></ol> |
| <span id="3"></span>3 | 应用内事件映射 | 检查TT4B的应用内事件映射是否正确，并做必要修改。<br /><br />**请按以下步骤查看并设置应用内事件映射**：<ol><li>从AppsFlyer后台进入**配置** > **活跃对接**。</li><li>搜索并选择**TikTok For Business**。</li><li>确保**渠道对接**选项卡中TikTok for Business的对接已启用且已配置完毕。</li><li>在**应用内事件回传**板块：<ol><li>【必要设置】确保**应用内事件回传**开关已打开。</li><li>确认您在<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">SKAN转化值操作台</Anchor>中的应用内事件已映射到TT4B事件或您<Anchor target="_blank" href="/marketers/zh/docs/skan-cv-decode-map-your-cv-to-events">自定义转化架构</Anchor>中的事件。<br />**请注意：** 仅当您的SKAN转化模型用于衡量整体收入时，才能将`af_skad_revenue`映射到TikTok的`Purchase`事件。<br />[![](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)</li></ol></li><li>点击**保存对接**。</li></ol> |

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">AppsFlyer的SKAN解决方案指南</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-tiktok=skan%E4%BA%92%E9%80%9Aappsflyer---tiktok h_01HDNYZ0CT1MGCRSSP3MXTJK5V=skan%E4%BA%92%E9%80%9Aappsflyer---tiktok scope-of-skan-interoperability-with-tiktok=appsflyer%E4%B8%8Etiktok%E7%9A%84skan%E4%BA%92%E9%80%9A%E4%BD%9C%E7%94%A8%E8%8C%83%E5%9B%B4 h_01HDNYZ0CT5NZHDHDBDSCFG911=appsflyer%E4%B8%8Etiktok%E7%9A%84skan%E4%BA%92%E9%80%9A%E4%BD%9C%E7%94%A8%E8%8C%83%E5%9B%B4 tiktok-for-business-guidance=tiktok-for-business%E6%8A%95%E6%94%BE%E9%85%8D%E7%BD%AE 01HR1TPFCSXRGYC610AR7KMTS5=tiktok-for-business%E6%8A%95%E6%94%BE%E9%85%8D%E7%BD%AE campaign-limits-for-dedicated-ios-14-campaigns=ios-14%E4%B8%93%E7%94%A8%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E7%9A%84%E6%8A%95%E6%94%BE%E9%99%90%E5%88%B6 h_01HDNYZ0CT7RNDAEWYKBHS6PET=ios-14%E4%B8%93%E7%94%A8%E5%B9%BF%E5%91%8A%E7%B3%BB%E5%88%97%E7%9A%84%E6%8A%95%E6%94%BE%E9%99%90%E5%88%B6 enabling-interoperation=%E5%90%AF%E7%94%A8%E4%BA%92%E9%80%9A%E8%AE%BE%E7%BD%AE h_01HDNYZ0CTJGY3GPC9F907NEPT=%E5%90%AF%E7%94%A8%E4%BA%92%E9%80%9A%E8%AE%BE%E7%BD%AE h_01HDNZ1BW5EBP0JCX84MTYPQ6K=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
