---
title: 产品线：对应用进行分组，实现跨平台归因
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2025-09-30T07:06:57Z'
  edited_at: '2026-10-30T12:20:59Z'
  id: 39524780935185
  locale: zh-cn
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/zh-cn/articles/39524780935185
---
> **核心要点：** 使用产品线，将不同平台的应用归入同一品牌。基于统一的客户用户 ID（CUID），实现跨平台归因，洞察用户在移动端、网页端和联网电视（CTV）应用中的完整旅程。

## 产品线简介

产品线可以将同一应用在不同平台上的版本（例如 Android、iOS、网页端和 CTV）归入同一品牌，简化应用管理，并基于客户用户标识符（CUID）实现无缝的跨平台归因。

使用产品线，您可以：

* 衡量用户在不同设备上的生命周期价值（LTV）。
* 分析用户在不同平台上的行为。
* 将同一品牌下的应用归为一组，便于内部管理。
* 选择启用跨平台再互动衡量。

  注意：跨平台再互动衡量为可选功能。启用后，AppsFlyer 可以将符合条件的回访用户活动归因于曾在不同平台上促使该用户重新互动的媒体渠道。详情请参阅<Anchor target="_blank" href="/marketers/zh/docs/beta-user-based-cross-platform-re-engagement-attribution">跨平台再互动衡量</Anchor>。

例如，用户先在 iOS 设备上安装您的应用，随后登录 PlayStation 应用，并通过 Samsung 电视观看内容。借助产品线，您可以将这些行为串联起来，查看该用户的完整旅程。

如需全面了解产品线，请参阅<Anchor target="_blank" href="/marketers/zh/docs/beta-user-based-cross-platform-attribution">基于用户的跨平台归因概述</Anchor>。

## 如何设置产品线

### 前提条件

* <strong>CUID（客户用户标识符）</strong>必须是在所有平台上保持一致的用户标识，例如登录 ID 或经过哈希处理的电子邮件地址。
* 完成 **CUID SDK 或** [**S2S 对接**](https://dev.appsflyer.com/hc/docs/set-customer-user-id)。
* 确保应用在每次启动时都设置 CUID，以便在不同设备和会话中识别同一用户。

### 如何创建产品线

1. 进入 **My Apps（我的应用）**。
2. 点击顶部栏中的 **Create Product Line（创建产品线）**。
3. 最多选择 30 个要纳入产品线的应用，然后点击 **Create（创建）**。
4. 在新窗口中：
   1. 输入**产品线名称**。
   2. 启用 **Start measuring and analyzing cross-platform（开始衡量和分析跨平台数据）**。  
      注意：如果未启用此选项，跨平台归因将无法生效。
   3. 选择**非活跃期窗口**。
   4. 选择是否启用跨平台再互动衡量。
      1. 选择**再互动窗口**。
      2. 选择**再互动非活跃期窗口**。
5. 在右侧查看产品线中包含的所有应用。
6. 点击 **Create（创建）**。
7. 将**CUID 实施说明**发送给开发人员。

**注意：** 跨平台再互动归因基于跨平台归因实现。启用再互动归因前，您必须先创建产品线、启用跨平台归因，并确保上报的事件包含有效的 CUID。有关跨平台再互动归因的工作原理，请参阅<Anchor target="_blank" href="/marketers/zh/docs/beta-user-based-cross-platform-re-engagement-attribution">跨平台再互动归因</Anchor>。

<div id="how-to-remove-an-app-from-a-product-line" />

<Accordion title="如何从产品线中移除应用">

> 🚧 **重要！**
>
> 不建议从产品线中移除应用。移除或迁移应用后，该应用的跨平台归因设置会被重置；在重新建立映射关系之前，其后续事件将无法参与跨平台归因。

1. 进入**My Apps（我的应用）**。
2. 在<strong>Product Lines（产品线）</strong>部分中，点击要编辑的产品线。
3. 在窗口右侧可以查看该产品线中包含的所有应用。
4. 将鼠标悬停在要移除的应用上，然后点击该应用上的**X**。
5. 移除应用后，点击窗口底部的**Update（更新）**。

</Accordion>

<div id="how-to-add-an-app-to-a-product-line" />

<Accordion title="如何向产品线添加应用">

1. 进入**My Apps（我的应用）**
2. 在<strong>All Apps（所有应用）</strong>部分中，将鼠标悬停在要添加的应用上，然后勾选对应的复选框。
3. 在顶部横幅中，选择**Add to Product Line（添加到产品线）**。
4. 选择要将该应用添加到的产品线。
5. 在产品线窗口中确认所有信息无误，然后点击窗口底部的**Update（更新）**。

</Accordion>

<div id="how-to-delete-a-product-line" />

<Accordion title="如何删除产品线">

> 🚧 **重要！**
>
> 不建议删除产品线。删除产品线后，相关的跨平台归因设置会被重置；在重新建立映射关系之前，后续事件将无法参与跨平台归因。

1. 进入**My Apps（我的应用）**。
2. 在<strong>Product Lines（产品线）</strong>部分中，点击要删除的产品线旁的三个点图标。
3. 选择**Delete product line（删除产品线）**。

</Accordion>

## 产品线的特点与限制

| 特点 | 说明 |
| --- | --- |
| 应用分组 | 应用必须属于同一品牌。 |
| 应用数量上限 | 每条产品线最多包含 30 个应用。 |
| 仅能加入一条产品线 | 同一应用在同一时间只能属于一条产品线。 |
| CUID 要求 | 仅在使用跨平台归因时需要。 |
| 非活跃期恢复窗口 | 14–390 天，默认值为 90 天。 |
| 移除应用的影响 | 移除应用会重置归因设置。<br /><br />从产品线中移除应用后，后续的跨平台归因将受到影响。<br /><br />• 被移除应用今后上报的应用内事件将不再符合该产品线的跨平台归因条件，因为只有来自产品线内应用的事件才能参与跨平台归因。<br /><br />• 历史结果不会追溯重新处理。 |

## 常见问题

**问：我可以只用产品线对应用进行分组管理吗？**  
可以。只需关闭跨平台衡量开关，即可仅将应用分组管理。

**问：从产品线中移除应用会有什么影响？**  
不建议从产品线中移除应用。移除应用或将其移至其他产品线时，该应用的跨平台归因设置会被重置。在重新建立映射关系之前，该应用后续上报的事件将无法参与跨平台归因。

**问：创建产品线会影响 AppsFlyer 传统的归因结果吗？**

不会。创建产品线不会影响 AppsFlyer 传统的设备级归因结果。

<div data-zendesk-anchors="about-product-line=%E4%BA%A7%E5%93%81%E7%BA%BF%E7%AE%80%E4%BB%8B h_01K6CQ3YXD9QGGMM08WJWNKX65=%E4%BA%A7%E5%93%81%E7%BA%BF%E7%AE%80%E4%BB%8B how-to-set-up-a-product-line=%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AE%E4%BA%A7%E5%93%81%E7%BA%BF h_01K6CQ3YXHBXVHE2V0WATR74T5=%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AE%E4%BA%A7%E5%93%81%E7%BA%BF prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01K6CQ3YXHXXYXKKQ3Q7B6N9JQ=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 how-to-create-a-product-line=%E5%A6%82%E4%BD%95%E5%88%9B%E5%BB%BA%E4%BA%A7%E5%93%81%E7%BA%BF h_01K6CQ3YXKBMS7NZSH0GSJMTBM=%E5%A6%82%E4%BD%95%E5%88%9B%E5%BB%BA%E4%BA%A7%E5%93%81%E7%BA%BF h_01K6CQ8MJFXS6WNWE0GPV18NPT=how-to-remove-an-app-from-a-product-line h_01K6CQPY31VW8BS7DR2TSKRPZZ=%E9%87%8D%E8%A6%81 h_01K6CQ8MJFRD9R9SNZ84D6QQB4=how-to-add-an-app-to-a-product-line h_01K6CQ8MJF61375RE001YMMS4E=how-to-delete-a-product-line h_01K6CQPY31DB9DKQJEBX1PXDPT=%E9%87%8D%E8%A6%81-1 traits-and-limitations=%E4%BA%A7%E5%93%81%E7%BA%BF%E7%9A%84%E7%89%B9%E7%82%B9%E4%B8%8E%E9%99%90%E5%88%B6 h_01K6CQ3YXZM5F0DVGTAQNHHN9B=%E4%BA%A7%E5%93%81%E7%BA%BF%E7%9A%84%E7%89%B9%E7%82%B9%E4%B8%8E%E9%99%90%E5%88%B6 faqs=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98 h_01K6CQD81T4VNMMNVH0X9SZ1TT=%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98" />
