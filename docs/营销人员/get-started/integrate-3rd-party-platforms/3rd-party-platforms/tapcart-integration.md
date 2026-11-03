---
title: Tapcart对接
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-24T09:21:54Z'
  edited_at: '2026-10-14T10:06:29Z'
  id: 4411720533905
  locale: zh-cn
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/zh-cn/articles/4411720533905
---
> **概要：** 通过Tapcart对接AppsFlyer功能，全面提升您的应用表现

## 简介

Tapcart可以帮助您轻松将数据传送至AppsFlyer，并充分利用其各项功能。在使用Tapcart构建应用时，会默认在应用中设置AppsFlyer SDK。通过Tapcart采集的数据，包括自然激活与非自然激活，都将同步展示在AppsFlyer平台上。

## 将Tapcart对接至AppsFlyer

AppsFlyer的SDK支持多种功能，包括：追踪激活与卸载、referral、用户与推送通知的交互、深度链接跳转、处理用户隐私场景等。

您可以参考<Anchor target="_blank" href="https://tapcart.com/integrations/appsflyer">Tapcart的官方说明</Anchor>，了解如何将Tapcart对接至AppsFlyer。

## AppsFlyer SDK中预设的应用内事件

通过Tapcart完成应用与AppsFlyer SDK的对接后，用户每次执行以下操作，系统都会自动记录对应的应用内事件：

* 完成注册
* 登陆
* 搜索
* 内容视图
* 列表视图
* 添加到心愿单
* 添加到购物车
* 发起的结账
* 下单购买
* 已完成购买
* 从购物车移除
* 首次购买

## 启用与AppsFlyer的深度链接

**要启用与 AppsFlyer 的深度链接，您需要向Tapcart提供以下参数：**

1. **Dev key：** 用于配置SDK的唯一标识符和身份验证令牌，同时用于加密信息、验证客户端账号或调用API程序。  
   同一账户下多个应用的dev key通常相同。了解更多关于<Anchor target="_blank" href="/marketers/zh/docs/app-settings#sdk-authentication-dev-key">dev key</Anchor>的信息。
2. **OneLink template ID：** 用于生成OneLink链接的模板ID。了解更多关于<Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">创建OneLink模板</Anchor>的信息。  
   **要获取特定模板的ID，请按以下步骤操作：**  
   1. 从AppsFlyer后台进入**用户体验与深度链接** > **OneLink 自定义链接。**
   2. 在**OneLink 模板**菜单中，选择所需的模板。
   3. 复制右侧显示的ID。   
       [![OneLink-template-id.png](https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png)](https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png)
3. **OneLink URL：** 在AppsFlyer中为某一特定广告活动生成的专属OneLink链接。了解更多关于<Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">生成OneLink</Anchor>的信息。

<div data-zendesk-anchors="introduction=%E7%AE%80%E4%BB%8B h_01JQ6D9NCM8K3E6GS12V2CR1CH=%E7%AE%80%E4%BB%8B integrating-tapcart-with-appsflyer=%E5%B0%86tapcart%E5%AF%B9%E6%8E%A5%E8%87%B3appsflyer h_01JQ6D9NCM95VJB19G2F7SDRG1=%E5%B0%86tapcart%E5%AF%B9%E6%8E%A5%E8%87%B3appsflyer default-inapp-events-configured-in-the-appsflyer-sdk=appsflyer-sdk%E4%B8%AD%E9%A2%84%E8%AE%BE%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 h_01JQ6D9NCMYBNJ6WJ09R1EHXH4=appsflyer-sdk%E4%B8%AD%E9%A2%84%E8%AE%BE%E7%9A%84%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6 enable-deep-linking-with-appsflyer=%E5%90%AF%E7%94%A8%E4%B8%8Eappsflyer%E7%9A%84%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5 h_01JQ6D9NCMC97JQ759B44M9TDJ=%E5%90%AF%E7%94%A8%E4%B8%8Eappsflyer%E7%9A%84%E6%B7%B1%E5%BA%A6%E9%93%BE%E6%8E%A5" />
