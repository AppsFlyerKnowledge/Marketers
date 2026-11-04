---
title: 基于用户的归因（PBA）入门指南
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-10-01T08:00:26Z'
  edited_at: '2026-10-14T10:13:40Z'
  id: 360013821097
  locale: zh-cn
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/zh-cn/articles/360013821097
---
> **概要：**

<div id="setting-up-pba" />

## PBA设置流程

下文和下表中分别说明并列出了设置PBA时需要完成的事项。

* 如需启用PBA，请联系您的AppsFlyer CSM或商务。
* 将品牌的数字资产组合成一个品牌套件。
* 将网页SDK接入您的网站，并将移动SDK接入您的应用。
* AppsFlyer收集数据并对其进行归因。
  * AF从多种不同来源收集数据。
  * AF将记录到的数据分为触点和事件。
  * AF将事件归因到过去30天内的末次间接网页访问。
  * 广告主可将某些事件（如购买）指定为转化事件。转化事件会包含在面板的分析报告中。
  * 原始数据会用于自定义的数据分析。
* 分析用户链路，推动投放优化。

<div id="pba-set-up-steps" />

### PBA设置流程

您需要先联系您的AppsFlyer CSM或商务，以启用PBA，然后才能开始设置流程。下表中列出了设置PBA时需要完成的工作。建议下载<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQkYW2k1VUFugYLZ7Xv5esBL4kxfoNXMw0wyfRvoNGHdgiyZS5K5BE4seR2bjocK5HAArj97nlqF4By/pub?output=xlsx">任务清单</Anchor>，以便记录您的完成进度。

**建议您**

<table><thead><tr><th> </th><th>负责人员</th><th>可用操作</th><th>说明</th></tr></thead><tbody><tr><td><span id="1"></span><p> 1</p></td><td><p>广告主 </p></td><td><ul><li> </li><li> <span><a href="./pba-brand-bundles-and-settings" target="_blank">设置品牌套件</a>；品牌套件由品牌方的各种数字资产组成（多个移动应用和一个网页端）。</span> </li><li>指定其他<a href="./pba-brand-bundles-and-settings#domain-exclusion" target="_blank">要排除的域名</a>。</li></ul></td><td><ul><li><span>AF会将分析和报告会汇总在该品牌下。</span></li></ul></td></tr><tr><td><span id="2"></span><p> 2</p></td><td> 网站管理员 </td><td><ul><li>在网页端所定义的网站中接入<a href="./pba-web-sdk-integration-guide" target="_blank">网页SDK</a>。 </li><li>配置网页SDK以实现以下功能：  <ul><li>记录访问</li><li>记录事件</li><li>设置<mark>CUID</mark> </li><li>使用<a href="./test-pba-web-sdk-integration" target="_blank">SDK测试工具</a>测试SDK是否成功接入 </li></ul></li></ul></td><td><ul><li><span>SDK会记录访问和事件。</span></li><li><span>支持通过Google Tag Manager (GTM)、Adobe或Tealium接入SDK。</span></li><li> 必须配置必须设置：在用户注册或登录后立即调用SetCustomerUserID()。如果没有CUID，请与您的CSM讨论备选方案。 </li></ul></td></tr><tr><td><span id="3"></span><p>3</p></td><td><p>广告主</p></td><td><p>请确保让网站管理员使用<a href="./test-pba-web-sdk-integration" target="_blank">SDK测试工具</a>来验证网页SDK的配置可实现以下功能：</p><ul><li>记录访问</li><li>记录事件</li><li>设置CUID</li></ul></td><td><p>广告主</p></td></tr><tr><td><span id="4"></span><p>4 </p></td><td><p>开发人员及广告主</p></td><td><p>【可选】<a href="./web-server-to-server-events-api-for-pba-web-s2s" target="_blank">网页端S2S</a> API</p></td><td>上报自动续费等网页相关事件</td></tr><tr><td><span id="5"></span><p>5</p></td><td><p>广告主</p></td><td><ul><li> <span>标记</span>转化事件： <ul><li>网页事件</li><li> </li></ul></li></ul></td><td><ul><li><span>请等每天一次\*的数据处理完毕后再执行该操作</span></li></ul></td></tr><tr><td><span id="6"></span><p> 6</p></td><td><p>广告主</p></td><td><p>开始使用面板</p></td><td><ul><li><a href="./pba-website-attribution-dashboard" target="_blank">网页广告归因</a></li><li><a href="./pba-web-assisted-installs" target="_blank">网页助攻激活</a></li></ul></td></tr><tr><td><span id="7"></span><p> 7</p></td><td>广告主</td><td><a href="./pba-raw-data-reports#setting-up-pba-reports-in-data-locker" target="_blank">设置Data Locker</a></td><td><p>用于拉取PBA原始数据报告，包括触点、标准事件和转化事件的信息，以及网页助攻激活和转化路径的专项报告。</p></td></tr><tr><td><span id="8"></span><p>8</p></td><td><p>广告主</p></td><td><p>可选<br/></p></td><td><p>数据每天\*处理一次，处理完毕后会在原始数据报告中更新</p></td></tr><tr><td colspan="4"><span id="-due-to-processing-data-is-available-10-hours-after-midnight-utc-on-the-day-of-the-event-meaning-mondays-events-are-available-tuesday-1000-utc"></span>\*事件数据会在事件发生次日的UTC时间十点处理完毕。也就是说，您可以在星期二的UTC时间10:00看到星期一发生的事件。 </td></tr></tbody></table>

<div id="pba-data-acquisition-via-sdkapi" />

## 通过SDK/API获取PBA数据

|  | 网页平台 | 移动（应用）平台 |
| --- | --- | --- |
| SDK | <Anchor target="_blank" href="/marketers/zh/docs/pba-web-sdk-integration-guide">网页</Anchor><ul><li>在网站中安装JavaScript标签SDK</li><li>上报网站访问和网页事件</li></ul> | <Anchor target="_blank" href="/marketers/zh/docs/integrate-the-appsflyer-sdk">移动端</Anchor><ul><li>将应用SDK接入iOS、安卓、Unity等</li><li>上报应用激活和用户在应用中的行为</li></ul> |
| 服务器对服务器API | <Anchor target="_blank" href="/marketers/zh/docs/web-server-to-server-events-api-for-pba-web-s2s">网页端S2S</Anchor><ul><li>上报后端服务器（非网页）中的事件</li><li>比如续费事件</li></ul> | <Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">移动端S2S</Anchor><ul><li>上报后端服务器（非应用）中的事件</li><li>比如续费事件</li></ul> |

<div data-zendesk-anchors="setting-up-pba=pba%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B 01H8V1XPAHGFVJRKM56S2ZQTBD=pba%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B pba-setup-steps=pba%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B-1 01ECF26CMN668ZZV6XNZA3W692=pba%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B-1 pba-dataacquisition-via-sdkapi=%E9%80%9A%E8%BF%87sdkapi%E8%8E%B7%E5%8F%96pba%E6%95%B0%E6%8D%AE 01H8V1XPAH23BV25ZCMFR7MM9Q=%E9%80%9A%E8%BF%87sdkapi%E8%8E%B7%E5%8F%96pba%E6%95%B0%E6%8D%AE" />
