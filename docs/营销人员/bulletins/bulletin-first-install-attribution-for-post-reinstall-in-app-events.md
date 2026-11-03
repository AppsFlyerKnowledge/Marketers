---
title: 公告：将重装激活后的应用内事件归因到初始激活
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-06-05T15:04:01Z'
  edited_at: '2026-10-14T10:04:23Z'
  id: 25676426941457
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/25676426941457
---
| **最新动态** | 我们对归因逻辑进行了优化，用户发生再互动或<Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls#reattribution">再归因</Anchor>后，所有后续的<Anchor target="_blank" href="/marketers/zh/docs/measure-reinstalls#应用内事件">应用内事件</Anchor>和应用打开（session）都将归因到初始带量渠道（即“first install”，初始激活），而不是将这些事件标记为“organic unattributed”（未归因的自然量）。<br /><br />![Screenshot 2024-06-11 at 8.44.30.png](https://files.readme.io/42a96ec533d217ee4dadad71592023d1fd0c977557308638f3553660a95fc7b5-25827620446353.png) |
| --- | --- |
| **生效日期** | 2024年7月31日。在该日期之后添加至AppsFlyer的所有新应用都将自动启用初始激活模式。如需为2024年7月31日前添加的应用启用该模式，请联系AppsFlyer客服团队。 |
| **前期准备** | 无 |
| **待办事项** | 无 |
| **须知要点** | 仅有当用户在初始激活和重装激活时均授权应用访问其设备标识符（如IDFA或GAID）时，AF才能够将其应用内事件归因到初始激活渠道。否则这些事件将被标记为“organic unattributed”（未归因的自然量）。 |
| **具体影响** | <ul><li>对于在**2024年7月31日之后**添加至AppsFlyer的应用程序：无影响</li><li>对于在**2024年7月31日之前**添加的应用程序，建议您联系AppsFlyer团队将应用迁移到初始激活模式。迁移后，可能会发生以下变化：<ul><li>对于重装激活后发生的应用内事件和应用打开（session），归因到初始激活的非自然量会有所提升，而自然量则会出现相应的下降。</li><li>对于获得初始激活归因的渠道，其MAU（月活用户）数量可能会出现提升，而自然量的MAU则会有所下降。</li><li>应用切换至初始激活模式的当天，应用打开数可能出现会翻倍，从而导致该日群组的D1留存率异常偏高。</li></ul></li></ul> |