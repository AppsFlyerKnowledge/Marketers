---
title: '[封闭测试版] 验证规则 API'
metadata:
  keywords:
    - Marketers
    - Closed beta
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2026-07-02T09:03:27Z'
  edited_at: '2026-10-22T08:44:42Z'
  id: 48341412127249
  locale: zh-cn
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/zh-cn/articles/48341412127249
---
<span class="af-tag af-tag--closed-beta">Closed beta</span>

> **At a glance:** 自动创建和管理验证规则。验证规则 API 支持技术团队通过程序创建、更新、局部修改和删除规则，不受 UI 中规则值数量限制的约束，同时减少手动管理规则所需的工作量。

> 📘 **注意**
>
> 验证规则 API 面向 Protect360 客户开放。目前，该功能处于封闭测试阶段，仅限部分账户使用，需要单独开通。如需申请使用权限，请联系您的客户成功经理（CSM）。

## 验证规则 API 概述

此前，验证规则只能通过 AppsFlyer UI 进行管理，因此存在两项限制：

* 每条规则最多只能包含约 17,000 个值。对于需要维护大规模企业级拦截列表的场景，这一上限难以满足需求。
* 每次更新都需要手动操作 UI。对于需要频繁调整规则的团队，这种方式既耗时，也会增加运营成本。

验证规则 API 解决了上述两项限制。技术团队可以通过程序全面管理验证规则。对于大型规则，每条规则最多支持 300,000 个值；同时，团队还可以自动执行高频更新，无需手动操作 UI。

通过 API 创建的规则会标记为由 API 管理，并在 AppsFlyer UI 中以只读形式显示。通过 UI 创建的现有规则不受影响。同一账户可以同时包含由 UI 管理和由 API 管理的规则。

<Accordion title="适用场景">

验证规则 API 主要面向特定使用场景，并非旨在取代所有客户使用的 UI 管理方式。如果您符合以下任一情况，可以考虑使用 API：

* 您需要管理的拦截列表或允许列表已超过或即将达到 UI 支持的约 17,000 个值的上限。
* 您希望将验证规则管理整合到自己的系统、脚本或自动化流程中。
* 您的反作弊逻辑或流量拦截规则经常变化，手动通过 UI 更新规则已成为工作瓶颈。

如果您只需管理少量规则，且规则很少变动，继续使用验证规则 UI 会是最简单的选择。

</Accordion>

<Accordion title="使用权限与资格要求">

验证规则 API 面向 Protect360 客户开放。目前，该功能处于封闭测试阶段，需要为每个账户单独开通使用权限。

* 订阅要求： 您需要订阅 Protect360。
* 功能开通： 此功能通过功能开关控制。请联系您的客户成功经理（CSM），申请开通使用权限并激活功能。
* 大型规则： 如果需要使用每条规则最多支持 300,000 个值的大型规则功能，除了标准 API 使用权限外，还需要单独申请开通。请联系您的 CSM 进行配置。

</Accordion>

## 工作原理

<Accordion title="身份验证">

该 API 使用 Bearer 令牌（JWT）进行身份验证。

1. 在您的 AppsFlyer 账户中，进入 **Security Center**（安全中心） > **API tokens**（API 令牌）。
2. 生成一个令牌。
3. 在 API 请求的 **Authorization** 请求头中附带该令牌。

> 📘 **注意**
>
> 必须先为账户开通 API 访问权限，令牌才能生效。请联系您的 CSM 进行激活。

</Accordion>

<Accordion title="可执行的操作">

| 操作 | 说明 |
| --- | --- |
| 获取规则列表 | 检索账户中所有处于活跃状态的规则（包括已启用和已禁用的规则）。 |
| 创建规则 | 以程序化方式创建新规则。 |
| 查看规则详情 | 获取规则的完整详情，包括所有条件。 |
| 更新规则 | 用新的配置覆盖现有规则。 |
| 启用/禁用规则 | 在不删除规则的情况下，开启或关闭该规则。 |
| 删除规则 | 永久移除某条规则。 |
| 局部修改规则 | 针对单个维度新增、移除或替换数值，而无需重写整条规则。 |

局部修改（Patch）接口在高频更新场景中尤为实用。您只需更新发生变化的部分，而无需重写整条规则。这种方式非常适合诸如“每日更新作弊流量来源拦截列表”这类工作流程。

</Accordion>

## 适用范围与支持的配置

验证规则 API 目前仅支持 UI 规则构建器中部分功能的子集。

* 仅适用于安装（install）事件。此版本尚不支持应用内事件。
* 支持的维度：
  * 流量来源（受众范围）：Site ID、Media Source、Agency、Campaign、Campaign ID、Ad Set ID 以及 Ad ID
  * 条件：Geo（地区）、Platform（平台）
* 支持的运算符：包含于列表中（Is in list）、不包含于列表中（Is not in list）。
* 维度之间的逻辑关系：仅支持 AND（且），不支持 OR（或）。
* 规则类型：匹配（Match，拦截符合条件的流量）或不匹配（Do not match，拦截不符合条件的流量）。
* 来源类型：所有流量、所有非自然流量，或来自特定代理商的非自然流量。
* 支持的拦截操作：
  * 拦截归因，并校正至最后一个有效媒体渠道。
  * 拦截归因，并将安装标记为无效。这些安装不会出现在 Protect360 面板中。

<Accordion title="规则规模与限制">

|  | 标准规则 | 大型规则 |
| --- | --- | --- |
| 所有条件下的数值总数 | 最多 17,000 个 | 最多 300,000 个 |
| 是否需要单独开通 | 是 | 是 |
| 每个账户的最大规则数 | 100 | 最多 5 条 |

其他限制：

* 每条规则最多包含 2,000 个 App ID。
* 每次 API 调用最大为 2MB。超出此限制的请求（通常为约 50,000 个数值以上）必须拆分为多次调用。
* 每条大型规则所有维度合计最多可包含 300,000 个数值，无论操作类型（创建、更新还是局部修改）如何，该上限均适用。

超出任一限制时，系统将返回错误信息，指明具体触发了哪项限制。

</Accordion>

<Accordion title="获取已拦截流量数据">

通过 API 管理的规则所拦截的流量，其上报方式与通过 UI 创建的规则所拦截的流量完全一致。

| 报告 | 位置 |
| --- | --- |
| 原始数据导出 | Protect360 & Validation Rules（验证规则） > Installs（安装） |
| Data Locker | Protect360 reports（报告） > blocked\_installs 报告 |
| Pull API | 原始数据导出 |

</Accordion>

<Accordion title="技术文档">

如需了解完整的技术细节，包括接口参考、请求与响应结构以及错误代码，请参阅<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/updaterule">验证规则 API 参考文档</Anchor>。

</Accordion>

<Accordion title="功能特性与限制">

| 特性 | 说明 |
| --- | --- |
| 事件支持 | 仅支持安装事件。此版本尚不支持应用内事件。 |
| 逻辑关系 | 维度之间仅支持 AND（且）逻辑，不支持 OR（或）逻辑。 |
| 与 UI 的交互 | 通过 API 创建的规则在 UI 中显示为只读，需使用 API 对其进行编辑。 |
| 调用大小 | 每次 API 调用最大为 2MB（约相当于 50,000 个数值）。更大规模的更新必须拆分为多次调用。 |

</Accordion>

## 常见问题

<Accordion title="谁可以使用验证规则 API？">

验证规则 API 面向 Protect360 客户开放。目前该功能处于封闭测试阶段，访问权限需按账户单独开通。请联系您的 CSM 申请使用权限。

</Accordion>

<Accordion title="通过 API 管理的规则会显示在 UI 中吗？">

会。通过 API 创建的规则会显示在 AppsFlyer UI 中，但会被标记为由 API 管理，并以只读形式呈现。

</Accordion>

<Accordion title="我可以一部分规则通过 API 管理，另一部分通过 UI 管理吗？">

可以。 API 管理的规则与 UI 创建的规则可以在同一账户中共存。 API 管理的规则在 UI 中显示为只读； UI 创建的规则则无法通过 API 访问。

</Accordion>

<Accordion title="我可以在 UI 中编辑由 API 管理的规则吗？">

不可以，该规则会显示为只读，您必须使用 API 对其进行更新。

</Accordion>

<Accordion title="“更新（Update）”和“局部修改（Patch）”有什么区别？">

更新（Update）会覆盖整条规则；局部修改（Patch）仅更新单个维度，可以新增、移除或替换数值，而无需重写整条规则。如需进行频繁的针对性更新，建议使用局部修改（Patch）。

</Accordion>

<Accordion title="超出限制会发生什么？">

API 会返回错误信息，指明具体触发了哪项限制。请将大规模更新拆分为多次 API 调用，以符合每次调用 2MB 的限制。

</Accordion>

<Accordion title="我最多可以创建多少条规则？">

每个账户最多可创建 100 条标准规则和 5 条大型规则。标准规则和大型规则均需要单独开通权限，请联系您的 CSM 进行激活。

</Accordion>

<Accordion title="是否支持 OR 逻辑？">

不支持。维度之间仅支持 AND（且）逻辑。

</Accordion>

<Accordion title="支持哪些事件类型？">

仅支持安装事件，此版本尚不支持应用内事件。

</Accordion>

> 📄 **另请参阅**
>
> * 实施验证规则以防止作弊

<div data-zendesk-anchors="h_01KWH1NW583T8SPZFF5REMQC6V=%E6%B3%A8%E6%84%8F about-the-validation-rules-api=%E9%AA%8C%E8%AF%81%E8%A7%84%E5%88%99-api-%E6%A6%82%E8%BF%B0 h_01KWH1NW58A3YK7FKR1C4WBRF3=%E9%AA%8C%E8%AF%81%E8%A7%84%E5%88%99-api-%E6%A6%82%E8%BF%B0 how-it-works=%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 h_01KWH1NW58P5AB47847E99YG6G=%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86 h_01KWH1NW594YT5S9FT8VWX77SG=%E6%B3%A8%E6%84%8F-1 scope-and-supported-configurations=%E9%80%82%E7%94%A8%E8%8C%83%E5%9B%B4%E4%B8%8E%E6%94%AF%E6%8C%81%E7%9A%84%E9%85%8D%E7%BD%AE h_01KWH1NW594XM03VQKNJPY37B7=%E9%80%82%E7%94%A8%E8%8C%83%E5%9B%B4%E4%B8%8E%E6%94%AF%E6%8C%81%E7%9A%84%E9%85%8D%E7%BD%AE faq=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98 h_01KWH1NW59J9QHP37KMMK18JBG=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98 h_01KWH1NW59G3WG3KHVRGY9TMV4=%E5%8F%A6%E8%AF%B7%E5%8F%82%E9%98%85" />
