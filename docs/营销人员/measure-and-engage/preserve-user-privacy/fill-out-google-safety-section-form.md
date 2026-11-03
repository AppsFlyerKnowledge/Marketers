---
title: Google Play中数据安全部分的表单
metadata:
  keywords:
    - Google Play
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-19T15:00:21Z'
  edited_at: '2026-10-14T10:08:38Z'
  id: 4417197430289
  locale: zh-cn
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/zh-cn/articles/4417197430289
---
> **概要**：自2022年4月起，Google Play要求应用开发者在其“数据安全”部分（Data safety section）填写一个表单，并提供相关的隐私政策链接。即使应用开发者不收集任何Google要求披露的数据类型，也必须提供这些信息。本文旨在帮助您填写Google“数据安全”部分的表单。请注意，本文中的说明仅适用于AppsFlyer代替广告主处理的数据。

广告主必须与其法务团队及其他相关的专业顾问紧密合作，判断Google的政策具体会以何种方式影响到其业务经营，从而根据其实际配置和使用场景调整其应对方式。

#### **声明**

本文所提供的信息旨在帮助您填写Google“数据安全”部分的表单。请注意，本文中的说明**仅**适用于AppsFlyer代替广告主处理的数据。

本文内容仅供参考。广告主必须与其法务团队及其他相关的专业顾问紧密合作，判断Google的政策具体会以何种方式影响到其业务经营，从而根据其实际配置和使用场景调整其应对方式。

## 简介

自2022年4月起，Google Play要求应用开发者在“数据安全”部分（Data safety section）提供与其数据隐私措施相关的信息。具体来说，应用开发者必须就其收集的数据以及这些数据的处理和共享方式提供详细说明。如果应用开发者使用了任何第三方的SDK，还必须针对这些SDK收集的数据提供上述信息。

每个应用所提供的信息会呈现在Google Play中的商品详情页，便于终端用户了解相关应用的隐私保护措施。

## 适用对象

所有应用开发者都必须填写“数据安全”部分的表单，并发布相关的隐私政策链接。即使应用开发者不收集任何Google要求披露的数据类型，也必须提供这些信息。

## Google数据安全表单（问卷）

Google要求应用开发人员填写的表单（问卷）包含以下几个部分：

* 数据收集与数据安全
* 数据的使用和处理

应用开发者需要先评估其数据收集和处理方式，然后再填写该问卷。

就AppsFlyer的数据使用方式而言，应用开发者须知悉：他们对于AppsFlyer的部署和配置具有完全掌控权，包括通过AF收集的数据及其使用方式。因此，每个应用开发者根据其数据管控方式以及对AppsFlyer的使用方式不同，对于问卷中的问题会有不同的答案。

应用开发者必须按照其具体的使用场景、配置以及渠道对接来填写这个问卷。

### 数据收集与数据安全

在这个部分中，您会被问到几个较为笼统的是非题。

1. 您的应用是否收集或分享任何必须披露的数据类型？
2. 您的应用所收集的用户数据是否全部经过端到端加密？
3. 您是否为用户提供相关途径，以供用户申请删除自己的数据？

在您使用AppsFlyer时，AppsFlyer会对所有通过SDK传输的数据全部进行端到端加密。此外，AppsFlyer的客户还能够通过OpenGDPR框架删除特定的终端用户数据。另请参考[数据类型](/docs/fill-out-google-safety-section-form#data-types)部分的表格，其中列出了应用开发者对于其收集的各类数据需提供的信息。


<span id="data-types"></span>在这个部分中，您需要选择相关应用所收集的数据类型，并回答以下问题：

1. 这些数据是否会被分享
2. 是否对这些数据进行临时处理（ephemeral processing）
3. 终端用户是否必须提供这些数据，还是可以选择不提供
4. 数据的用途

下表所列的信息以AppsFlyer软件的默认配置为前提。应用开发者有责任自行调整表单的填写方式，确保填写的内容符合其实际配置和使用场景。

“收集”是指通过任何方式（比如webview网页视图或SDK）将数据传输到用户设备以外。  如果您使用了端到端加密，则不算做“收集”，因为这种情况下任何人都无法读取相关数据。

| 数据类型 | AppsFlyer默认的数据收集 | 说明 |
| --- | --- | --- |
| 位置信息<ul><li>大致位置</li><li>确切位置</li></ul> | 详见说明 -> | 确切位置：不收集<br /><br />大致位置：收集，接收到的IP地址会被关联到某个地区/城市。 |
| 个人信息<ul><li>名字</li><li>电子邮件地址</li><li>个人身份识别信息（帐号ID、帐号或帐号名称）</li><li>地址</li><li>电话号码</li><li>种族和民族</li><li>政治信仰或宗教信仰</li><li>性取向或性别认同</li><li>其他个人信息</li></ul> | 详见说明 -> | 个人信息不应被收集，且AppsFlyer限制姓名和地址等个人数据的收集。但如果应用开发者配置了邮件地址或电话号码的哈希加密传输，或者配置了客户用户账号ID（CUID），则必须据实填写。 |
| 财务信息<ul><li>信用卡、借记卡或银行账号</li><li>交易记录</li><li>信用评分</li><li>其他财务信息</li></ul> | 不收集  <br />  <br />可选<br /><br />不收集  <br />不收集 | 信用卡和信用评分等财务信息不应被收集。<br /><br />如果您衡量应用内购买（即交易记录），则必须回答**是** |
| 健康与健身<ul><li>健康信息</li><li>健身信息</li></ul> | 不收集 | 不应收集 |
| 信息<ul><li>电子邮件</li><li>短信或彩信</li><li>其他应用内消息</li></ul> | 不收集 | 不应收集 |
| <ul><li>视频</li></ul> | 不收集 | 不应收集 |
| 音频文件<ul><li>语音或声音的录音</li><li>音乐文件</li><li>其他音频文件</li></ul> | 不收集 | 不应收集 |
| 日历<ul><li>日历活动</li></ul> | 不收集 | 不应收集 |
| 应用活动<ul><li>应用内的页面访问及点按次数。</li><li>应用内搜索记录</li><li>已安装的应用</li><li>其他由用户生成的内容</li><li>其他操作</li></ul> | 详见说明 -> | AppsFlyer默认衡量应用打开，这类行为可能会被Google判定为页面访问或其他操作。<br /><br />另外，如果您为相关应用配置了某些具体应用内事件的衡量，必须根据您的实际配置回答“是”。 |
|  | 不收集 | 不应收集 |
| 应用信息和性能<ul><li>崩溃日志</li><li>诊断</li><li>其他应用性能数据</li></ul> | 不收集<br /><br />是<br /><br />收集 | 可能会接收应用启动时间或电池电量水平的数据，用于防作弊检测。 |
| 设备ID或其他ID<ul><li>设备ID或其他ID（如IMEI标识符、MAC地址和广告标识符）</li></ul> | 详见说明 -> | AppsFlyer Android SDK默认收集Google Advertising Identifier（即GAID）  <br />您可以关闭SDK中的Advertising ID收集，具体方式为：[撤销AD\_ID权限](https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission)并调用[setDisableAdvertisingIdentifiers](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib)。 |

“分享”是指将数据传输给第三方（无论第三方是在用户设备内还是在设备外）。

下列情况例外：

* 将用户数据传输给服务提供商，这些服务提供商根据开发者的指示代表开发者处理这些数据。
* 出于特定法律目的传输用户数据（例如为了响应政府要求）。
* 基于用户发起的操作，或基于醒目的应用内披露声明以及用户同意机制，将用户数据传输给第三方
* 匿名数据

这里请重点注意：虽然AppsFlyer仅作为服务提供商根据您的指示代表您完成相关工作，如果您与第三方平台分享数据（如通过回传、SRN或受众共享），这种情况仍会被Google视为“分享”。  因此，每个应用开发者都必须评估其实际配置以及渠道对接，并据实填写相关信息。

## 临时处理（Ephemeral processing）

“临时”处理数据是指数据仅存储在内存中，并且数据的保留期限不会超过实时处理特定请求所需的时间。鉴于AppsFlyer服务的性质，AppsFlyer代表您完成的数据处理并非临时处理。

## 用户选择

一般来说，相关应用所收集的数据对于该应用所提供的服务来说是必要的，但应用开发者仍然可以向用户提供“允许”或“拒绝” 任何数据收集的选项。

## 数据用途

应用开发者必须根据实际情况从Google提供的数据用途列表中选择相关选项，详见下表说明。

| 数据用途 | 说明 |
| --- | --- |
| 应用功能 | 如果您使用相关数据以提供应用内的功能，请选择该选项。 |
| 分析 | 是 |
| 开发者通讯 | 如果您使用相关数据向用户发送任何通知，请选择该选项。 |
| 广告和营销 | 如果您将相关类型的数据共享给第三方，用于展示第三方广告，或使用这些数据推广产品或发送推送通知，请选择该选项 |
| 欺诈（作弊）防范、安全和法规遵从 | 是 |
| 个性化 | 如果您将相关数据用于任何类型的产品个性化，请选择该选项 |
| 账户管理 | 如果您将相关数据用于用户账号的设置和管理，请选择该选项 |

> 📄 **相关文档**
>
> 如需进一步了解Google Play数据安全部分的应对方式以及相关表单的填写，请参考以下文档：
>
> * <Anchor target="_blank" href="https://android-developers.googleblog.com/2021/07/new-google-play-safety-section.html">对Google Play新推出的数据安全部分做好应对准备</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/10787469">为Google Play中的“数据安全”部分提供信息</Anchor>

<div data-zendesk-anchors="disclaimer=%E5%A3%B0%E6%98%8E h_01HDP3NTTKH3X3585J3DM6MCDC=%E5%A3%B0%E6%98%8E introduction=%E7%AE%80%E4%BB%8B h_01HDP3NTTK1BDTZTHNWRM3411D=%E7%AE%80%E4%BB%8B audience=%E9%80%82%E7%94%A8%E5%AF%B9%E8%B1%A1 h_01HDP3NTTKQE2N0HZDNGK2ZQPC=%E9%80%82%E7%94%A8%E5%AF%B9%E8%B1%A1 google-safety-form-questionnaire=google%E6%95%B0%E6%8D%AE%E5%AE%89%E5%85%A8%E8%A1%A8%E5%8D%95%E9%97%AE%E5%8D%B7 h_01HDP3NTTKK6DJSF49326V3BEG=google%E6%95%B0%E6%8D%AE%E5%AE%89%E5%85%A8%E8%A1%A8%E5%8D%95%E9%97%AE%E5%8D%B7 data-collection-and-security=%E6%95%B0%E6%8D%AE%E6%94%B6%E9%9B%86%E4%B8%8E%E6%95%B0%E6%8D%AE%E5%AE%89%E5%85%A8 h_01HDP3NTTK89K8YPT6C7S9QM3W=%E6%95%B0%E6%8D%AE%E6%94%B6%E9%9B%86%E4%B8%8E%E6%95%B0%E6%8D%AE%E5%AE%89%E5%85%A8 h_01HDP3NTTK9DYZTQ2B64QMKGX8=data-types ephemeral-processing=%E4%B8%B4%E6%97%B6%E5%A4%84%E7%90%86ephemeral-processing h_01HDP3NTTKT7C0TGVCZJ4GR9BF=%E4%B8%B4%E6%97%B6%E5%A4%84%E7%90%86ephemeral-processing user-choice=%E7%94%A8%E6%88%B7%E9%80%89%E6%8B%A9 h_01HDP3NTTK4CT8MJ1S84MAG8VD=%E7%94%A8%E6%88%B7%E9%80%89%E6%8B%A9 purpose=%E6%95%B0%E6%8D%AE%E7%94%A8%E9%80%94 h_01HDP3NTTKD3MND388MWCC6PAT=%E6%95%B0%E6%8D%AE%E7%94%A8%E9%80%94 h_01HDP3RBENN69F150ESQMSVP3Q=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
