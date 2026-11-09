---
title: 对Google欧盟意见征求政策的支持
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2024-02-07T07:28:17Z'
  edited_at: '2026-10-14T10:07:18Z'
  id: 22310731147153
  locale: zh-cn
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/zh-cn/articles/22310731147153
---
> **概要：** AppsFlyer旨在帮助广告主根据《数字市场法案》（DMA）的要求完成合规工作，并提升其Google广告的价值。本文解答了与DMA合规以及广告价值优化相关的常见问题。

<div id="overview" />

## 简要说明

为了应对即将生效的欧盟<Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">《数字市场法案》</Anchor>（DMA），Google正在对其<Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">欧盟用户意见征求政策</Anchor>进行更新。作为Google的<Anchor target="_blank" href="https://ads.google.com/lp/appcampaigns/attribution/">App Attribution Partner</Anchor>（应用归因合作伙伴），AppsFlyer也在做必要调整，以支持Google的政策更新，同时帮助广告主充分发掘其Google广告的价值。新政策自2024年3月6日起生效。

<div id="relevant-integrations-and-continued-use-of-google-features" />

## 相关对接及Google功能的持续使用

<div id="which-integrations-are-involved" />

<Accordion title="此次政策更新涉及哪些对接？">

Google的欧盟用户意见征求新政会影响到以下对接：

* Google Ads（`googleadwords_int`）
* GMP DV360（`dv360_int`）

如果您的应用通过这些对接收集欧洲经济区（EEA）境内终端用户的数据，请务必采取必要措施，以确保您符合Google欧盟用户意见征求新政的规定。

<div id="note" />

> 📘 **注意**
>
> Google Marketing Platform DV360/CM历史对接（`doubleclick_int`）将被弃用，Google推行欧盟意见征求新政后不再支持该对接。如果您目前正在使用这个对接，建议您<Anchor target="_blank" href="/marketers/zh/docs/bulletin-google-marketing-platform-gmp-integration-transition">迁移到新的DV360对接（dv360\_int）</Anchor>。

</Accordion>

<div id="what-must-i-do-to-continue-using-googles-features" />

<Accordion title="如要继续使用Google的各项功能，需符合什么条件？">

广告主必须取得EEA境内终端用户的授权（即用户允许广告主使用其个人数据）后，才能继续使用Google Ads以及GMP DV360中与效果衡量、个性化广告以及再营销相关的功能。

</Accordion>

<div id="updating-the-appsflyer-sdk" />

## 更新AppsFlyer SDK

<div id="what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk" />

<Accordion title="通过AppsFlyer SDK接入授权数据所需的步骤">

AppsFlyer SDK（Android - v6.13.0+, iOS - v6.13.1+）可在每个事件中发送必要的授权数据，以符合Google的要求。

* 请将您的<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">SDK升级</Anchor>至最新版本（Android - v6.13.0+, iOS - v6.13.1+），我们提供用于安卓和iOS应用的SDK。
* SDK升级完毕后，请参考适用于DMA合规的<Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">SDK接入说明</Anchor>。

</Accordion>

<div id="sending-consent-data" />

## 发送授权数据

<div id="how-do-i-send-consent-data-to-appsflyer" />

<Accordion title="如何将授权数据发送到AppsFlyer">

广告主可以通过以下两种方式将必要的授权数据发送给AppsFlyer：

* [**通过SDK**](#更新appsflyer-sdk)**或S2S API直接发送：** 广告主可以使用SDK将授权数据直接发送到AppsFlyer。这一方式适用于安卓或iOS应用。
* **通过TCF字符串发送：** 正在使用或计划使用同意管理平台（Consent Management Platform，简称CMP）的广告主可以通过标准IAB TCF字符串（TCF V2.2）发送相关数据字段。请确保授权服务商列表中包含Google的服务商ID（755）。

然后广告主可以通过AppsFlyer向Google发送授权信号（consent signals）。请注意，AppsFlyer不对终端用户的授权数据进行任何采集、更改或控制。与Google合作的广告主须全权负责必要授权字段的采集。

请参见<Anchor target="_blank" href="https://appsflyer.wistia.com/medias/0tnlyre8ai">此视频</Anchor>了解如何将授权数据发送到AppsFlyer。

</Accordion>

<div id="which-consent-values-does-appsflyer-send-to-google" />

<Accordion title="AppsFlyer向Google发送哪些授权数据？">

在相关的AppsFlyer对接（`googleadwords_int`和`dv360_int`）中，终端用户的授权数据会通过以下字段发送到Google：

| AppsFlyer字段 | Google字段（1） | 值 | 字段用途 |
| --- | --- | --- | --- |
| <span id="gdpr_applies"></span>gdpr\_applies | eea | true/false（2） | DMA是否适用于此用户 |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true/false | 用于说明该用户是否允许Google将其数据用于个性化广告 |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true/false | 用于说明该用户是否同意将其数据发送到Google |

1. 请参见<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">Google对各字段的定义</Anchor>。
2. 如DMA不适用于某一用户，建议不要发送除`gdpr_applies=false`以外的授权字段

</Accordion>

<div id="sending-consent-datafaq" />

### 发送授权数据 - 常见问题解答

<div id="do-i-have-control-over-consent-data-for-nonue-users" />

<Accordion title="能否不向Google发送授权数据？">

如果广告主认为DMA的规定不适用于其终端用户（比如其应用仅面向欧盟境外的用户），可以在AppsFlyer后台的相关对接页面中打开相应的开关，避免向Google发送授权数据。

<div id="important" />

> 🚧 **重要提示！**
>
> 在启用此选项之前，建议请法务与隐私团队先对此决定进行审批，以确保该操作符合其政策要求。如需进一步了解相关概念的定义，请参见<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">Google的意见征求模式说明文档</Anchor>。

**如需避免与Google共享授权数据，请按以下方式操作：**

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 搜索合作渠道并点击**管理对接**。
3. 在对接设置选项卡中，打开**非欧盟用户**开关。

<Image align="center" alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="595px" />

</Accordion>

<div id="is-consent-needed-for-mobile-web-events" />

<Accordion title="我需要为移动网页事件获取用户同意吗？">

在当前阶段，AppsFlyer仅与Google共享移动应用事件，因此无需向AppsFlyer提供网页事件的用户同意信息。如果用户从网页跳转进入您的应用，其同意信息仍会在应用内的后续阶段中被收集。

</Accordion>

<div id="which-countries-does-googles-eu-consent-policy-cover" />

<Accordion title="谷歌DMA意见征求政策适用于哪些国家？">

《数字市场法案》（DMA）适用于欧盟及欧洲经济区（EEA）内的用户，因此这些国家会<Anchor target="_blank" href="https://www.gov.uk/eu-eea">受到该政策的影响</Anchor>。虽然**英国和瑞士**不属于欧盟国健，谷歌已单方面将其同意政策扩展至这些国家。

</Accordion>

<div id="whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way" />

<Accordion title="如何以合规的方式征求用户同意？">

AppsFlyer建议您咨询法务团队，确保以符合DMA要求的方式获取用户同意。虽然Google提供了一些通用指引，但并未就提示语的具体措辞给出明确建议。

</Accordion>

<div id="how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags" />

<Accordion title="AppsFlyer如何将TCF字符串转换为Google的DMA授权标识？">

当AppsFlyer从您的CMP（无论是通过AppsFlyer SDK还是S2S方式）接收到TCF字符串后，会在AppsFlyer服务器上对这些信息进行处理和转换。根据Google的建议，AppsFlyer会将以下映射结果发送给Google：

| AppsFlyer收集的字符串 | Google授权标识 | 说明 |
| --- | --- | --- |
| `gdpr_applies=1/0` | `eea=1/0` | 确定DMA是否适用于相关用户 |
| `ad_user_data` | `ad_user_data=1` | 用户同意将信息授权给Google用于目的1，并且同意将信息/合法利益授权给Google用于目的7 |
| `ad_user_data` | `ad_user_data=0` | 用户未同意将信息授权给Google用于目的1，**并且/或**未同意将信息/合法利益授权给Google用于目的7 |
| `ad_personalization` | `ad_personalization=1` `ad_personalization=0` | 用户同意将信息授权给Google用于目的3和4用户为同意将信息授权给Google用于目的3和4 |

</Accordion>

<div id="if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk" />

<Accordion title="为发送同意数据，我需要更新AppsFlyer和Firebase SDK吗？">

是Google要求通过AppsFlyer发送的每个事件中都包含用户同意数据，因为Google不会将Firebase中的用户同意数据与来自AppsFlyer的数据合并处理。因此，同意数据必须被发送给AppsFlyer，由其转发至Google。同样，仅向AppsFlyer共享同意数据也无法满足Firebase SDK的要求。也就是说，您需要同时将同意数据发送给AppsFlyer和Firebase。

</Accordion>

<div id="preparing-for-the-upcoming-changes" />

## 如何为应对新政做好准备？

<div id="how-can-i-prepare-for-the-upcoming-changes" />

<Accordion title="建议您做好如下准备工作：">

<div id="address-user-consent-in-the-european-economic-area-eea" />

#### 探讨欧洲经济区（EEA）境内用户授权事宜的处理方式

与贵司法务沟通，向其咨询欧洲用户意见征求政策对您与Google等合作渠道共享的数据有何影响。如果该政策适用于您的应用，请在其中部署“隐私设置”（Privacy Settings）或“隐私选项”（Privacy Choices）等隐私配置弹窗，从应用用户侧采集营销和广告相关的用户授权信号（consent signals）。

<div id="verify-cmp-compliance-and-tcf-2223-support" />

#### 检验CMP合规性以及TCF 2.2支持

请确保您使用的CMP支持TCF2.2，即最新版的透明度和同意框架（Transparency and Consent Framework，简称TCF）。此外还请确保您的CMP通晓Google欧盟意见征求新规，并能够指导您通过TCF达到其要求。

<div id="implement-the-newest-sdkserver-to-server-s2s-apis" />

#### 接入最新版本的SDK/服务器到服务器（S2S）API

您可以通过SDK或S2S API发送新的授权字段，具体方式如下：

* **通过SDK发送数据：**
  * 在您的iOS或安卓应用中接入最新版本的AppsFlyer SDK（Android - v6.13.0+, iOS - v6.13.1+）
  * 选择<Anchor target="_blank" href="/marketers/zh/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">授权数据的发送方式</Anchor>
* **通过<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile?">S2S</Anchor> API发送数据：**
  * 向AppsFlyer发送应用内事件之前，请先更新您的API，为每个事件都添加`consent_data`对象。详细操作说明请见<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">此文档</Anchor>。

<div id="transition-from-the-legacy-gmp-integration-doubleclick" />

#### 从GMP历史对接（DoubleClick）迁移到新对接

如果您仍在使用AppsFlyer的GMP历史对接（doubleclick\_int），请在2024年Q1结束前迁移到新对接（dv360\_int）。历史对接**不符合欧盟意见征求政策**的规定，即将下线。如需了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/bulletin-google-marketing-platform-gmp-integration-transition">此文档</Anchor>。

</Accordion>

<div id="impact-on-advertising-activityfaq" />

## 对广告活动的影响 - 常见问题解答

<div id="how-will-the-upcoming-change-impact-my-remarketing-campaigns" />

<Accordion title="此次政策更新对广告归因有何影响？">

如果欧盟境内的用户拒绝Google将其数据用于广告投放，Google Ads和DV360就不会认领这些用户的归因。也就是说，AppsFlyer无法对这类用户进行归因。  
根据Google对《数字市场法案》（DMA）的解释，在某些边缘场景下，即使ad\_user\_data=0，Google和AppsFlyer仍可能执行归因操作。

</Accordion>

<div id="how-will-the-upcoming-change-affect-my-audiences" />

<Accordion title="此次政策更新对受众共享（Audiences）有何影响？">

此次政策更新会影响到Google再营销广告的受众人群以及您人群包中的EEA用户数量。EEA境内的用户与Google共享其信息之前需要先同意授权。拒绝授权的用户会被排除在Google的定向投放人群之外，不会向其投放您的广告。这里涉及到获取用户授权的方式及其对您业务及营销工作的影响。如需进一步了解受众共享工具的相应更新，请参考<Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy#eu-digital-markets-act">此文档</Anchor>。

</Accordion>

<div id="see-also" />

<div id="further-information-and-contact-details" />

## 更多信息和联系方式

如果您还有其他问题或顾虑，请通过以下方式获取资讯：

* 若您对Google新规有任何疑问，或需要了解其政策更新对您的Google数据有何影响，请参阅<Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy-help/">Google的说明文档</Anchor>，或直接联系您在Google的客户经理。
* 如需了解AppsFlyer对于欧盟终端用户授权字段的支持方式，请联系您的AppsFlyer CSM或发送邮件至[hello@appsflyer.com](mailto:hello@appsflyer.com)。
* 如需进一步了解相关概念的定义，请参见<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">Google的意见征求模式说明文档</Anchor>。

<div data-zendesk-anchors="overview=%E7%AE%80%E8%A6%81%E8%AF%B4%E6%98%8E h_01HP195KV35FD6X67WTMXJWWSZ=%E7%AE%80%E8%A6%81%E8%AF%B4%E6%98%8E relevant-integrations-and-continued-use-of-google-features=%E7%9B%B8%E5%85%B3%E5%AF%B9%E6%8E%A5%E5%8F%8Agoogle%E5%8A%9F%E8%83%BD%E7%9A%84%E6%8C%81%E7%BB%AD%E4%BD%BF%E7%94%A8 h_01HP1M37V1CYW5T5E4K1ES3NQA=%E7%9B%B8%E5%85%B3%E5%AF%B9%E6%8E%A5%E5%8F%8Agoogle%E5%8A%9F%E8%83%BD%E7%9A%84%E6%8C%81%E7%BB%AD%E4%BD%BF%E7%94%A8 01HP1KN2H7NTS2V1S2PGF0C41N=which-integrations-are-involved h_01HP2HRPJR72Z0R5VEG5N36CN2=%E6%B3%A8%E6%84%8F h_01HP1K1088SJK60QRSTQF4WF6S=what-must-i-do-to-continue-using-googles-features updating-the-appsflyer-sdk=%E6%9B%B4%E6%96%B0appsflyer-sdk h_01HP1Z2G2M56DDQS9T47GMCFHJ=%E6%9B%B4%E6%96%B0appsflyer-sdk h_01HP1ZASRQGABCEFV67P961XAV=what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk how-consent-data-is-sent=%E5%8F%91%E9%80%81%E6%8E%88%E6%9D%83%E6%95%B0%E6%8D%AE h_01HP1KPSMCH3EG373BWVQZM4ZT=%E5%8F%91%E9%80%81%E6%8E%88%E6%9D%83%E6%95%B0%E6%8D%AE h_01HP1JJ2AYHYJET9GYMXA93E86=how-do-i-send-consent-data-to-appsflyer h_01HP1JJ2AYWRBREW5GD0KPDF1R=which-consent-values-does-appsflyer-send-to-google sending-consent-data%E2%80%94faq=%E5%8F%91%E9%80%81%E6%8E%88%E6%9D%83%E6%95%B0%E6%8D%AE---%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HR1X08VZ5MEAV01E9X54KAQS=%E5%8F%91%E9%80%81%E6%8E%88%E6%9D%83%E6%95%B0%E6%8D%AE---%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HP1JJ2AYZ57G0GMR8QRDTEZ7=do-i-have-control-over-consent-data-for-nonue-users h_01HP2MRPFA2ECJGAZ93NQHVD2J=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA 01HVE9TVZWTRW3VQ8TSXWA13QM=is-consent-needed-for-mobile-web-events h_01JVYS49FCZT3Z91KNACNR6GET=which-countries-does-googles-eu-consent-policy-cover h_01HRXZYZJBDTP8CHJDHQ187CTN=whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way 01HR6SD3PBWN5X9AHT66ZADQ3R=how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags 01J2V4XRKRSEPA6KPJFMSTHE1F=if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk what-i-can-do-on-my-side=%E5%A6%82%E4%BD%95%E4%B8%BA%E5%BA%94%E5%AF%B9%E6%96%B0%E6%94%BF%E5%81%9A%E5%A5%BD%E5%87%86%E5%A4%87 01HR1XYXRDVEW6H9Q3WP17E2N3=%E5%A6%82%E4%BD%95%E4%B8%BA%E5%BA%94%E5%AF%B9%E6%96%B0%E6%94%BF%E5%81%9A%E5%A5%BD%E5%87%86%E5%A4%87 h_01HP1JJ2AYFHRRDYZS8YFYE6WP=how-can-i-prepare-for-the-upcoming-changes address-user-consent-in-the-european-economic-area-eea-and-in-the-uk=%E6%8E%A2%E8%AE%A8%E6%AC%A7%E6%B4%B2%E7%BB%8F%E6%B5%8E%E5%8C%BAeea%E5%A2%83%E5%86%85%E7%94%A8%E6%88%B7%E6%8E%88%E6%9D%83%E4%BA%8B%E5%AE%9C%E7%9A%84%E5%A4%84%E7%90%86%E6%96%B9%E5%BC%8F h_01HPGNBQCTJFVZR99BY6E5J2JF=%E6%8E%A2%E8%AE%A8%E6%AC%A7%E6%B4%B2%E7%BB%8F%E6%B5%8E%E5%8C%BAeea%E5%A2%83%E5%86%85%E7%94%A8%E6%88%B7%E6%8E%88%E6%9D%83%E4%BA%8B%E5%AE%9C%E7%9A%84%E5%A4%84%E7%90%86%E6%96%B9%E5%BC%8F verify-cmp-compliance-and-tcf-22-support=%E6%A3%80%E9%AA%8Ccmp%E5%90%88%E8%A7%84%E6%80%A7%E4%BB%A5%E5%8F%8Atcf-22%E6%94%AF%E6%8C%81 h_01HPGNC0HAMA7Z0B4DNV2QSFYG=%E6%A3%80%E9%AA%8Ccmp%E5%90%88%E8%A7%84%E6%80%A7%E4%BB%A5%E5%8F%8Atcf-22%E6%94%AF%E6%8C%81 implement-the-newest-sdkservertoserver-s2s-apis=%E6%8E%A5%E5%85%A5%E6%9C%80%E6%96%B0%E7%89%88%E6%9C%AC%E7%9A%84sdk%E6%9C%8D%E5%8A%A1%E5%99%A8%E5%88%B0%E6%9C%8D%E5%8A%A1%E5%99%A8s2sapi h_01HPGNCAG3M9XPHDTP03WHQQ9F=%E6%8E%A5%E5%85%A5%E6%9C%80%E6%96%B0%E7%89%88%E6%9C%AC%E7%9A%84sdk%E6%9C%8D%E5%8A%A1%E5%99%A8%E5%88%B0%E6%9C%8D%E5%8A%A1%E5%99%A8s2sapi transition-from-the-legacy-gmp-integration-doubleclick=%E4%BB%8Egmp%E5%8E%86%E5%8F%B2%E5%AF%B9%E6%8E%A5doubleclick%E8%BF%81%E7%A7%BB%E5%88%B0%E6%96%B0%E5%AF%B9%E6%8E%A5 h_01HPGNCHP6SSFCVZ3P4AG0N1FB=%E4%BB%8Egmp%E5%8E%86%E5%8F%B2%E5%AF%B9%E6%8E%A5doubleclick%E8%BF%81%E7%A7%BB%E5%88%B0%E6%96%B0%E5%AF%B9%E6%8E%A5 impact-on-my-advertising-activity=%E5%AF%B9%E5%B9%BF%E5%91%8A%E6%B4%BB%E5%8A%A8%E7%9A%84%E5%BD%B1%E5%93%8D---%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HP1PKNZN32TQYHGJNNM3JFVZ=%E5%AF%B9%E5%B9%BF%E5%91%8A%E6%B4%BB%E5%8A%A8%E7%9A%84%E5%BD%B1%E5%93%8D---%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E8%A7%A3%E7%AD%94 h_01HP1PKNZN0VJGYAPFHR5JVV5H=how-will-the-upcoming-change-impact-my-remarketing-campaigns h_01HP4K2ZJW11BFSKNPRH7FA092=how-will-the-upcoming-change-affect-my-audiences further-information-and-contact-details=%E6%9B%B4%E5%A4%9A%E4%BF%A1%E6%81%AF%E5%92%8C%E8%81%94%E7%B3%BB%E6%96%B9%E5%BC%8F h_01HQ2VJES04CYF4J8YBB4GQS73=%E6%9B%B4%E5%A4%9A%E4%BF%A1%E6%81%AF%E5%92%8C%E8%81%94%E7%B3%BB%E6%96%B9%E5%BC%8F" />
