---
title: 广告主的回传问题排查指南
metadata:
  keywords:
    - Postback
    - Partner
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-04-04T07:09:26Z'
  edited_at: '2026-10-14T10:10:57Z'
  id: 14272573202833
  locale: zh-cn
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/zh-cn/articles/14272573202833
---
> **概要：** 概要：如果您的合作渠道无法正常接收回传，本文可帮助您排查具体的问题成因和解决方案。请根据您遇到的问题对照以下各章节的主题，找到适用于该问题的内容。

<div id="check-the-integration-toggles" />

## 检查对接开关

对接配置中的各种功能分别有其对应的开关，这些开关的使用状态可能会影响回传的接收。

<div id="the-activate-partner-toggle-was-turned-off" />

<Accordion title="“启用该渠道”开关未打开">

启用该渠道开关

![integration_turned_off.png](https://files.readme.io/d43b4f465749e343d9523e90e87e43b77a85cdd920f0c0770a94bcb7a585d920-14979273403793.png)

**请按以下步骤激活对接：**

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接。**
2. 点击该渠道的“管理对接”图标。
3. 激活合作伙伴开关

启用该渠道开关

* <span id="1703758710.321359"></span>进入 邮箱地址

</Accordion>

<div id="1703760110.503549" />

<div id="the-inapp-event-postbacks-toggle-was-turned-off" />

<Accordion title="“应用内事件回传”开关未打开">

Meta install referrer与 AppsFlyer就不会向渠道发送事件回传。

**请按以下步骤开启应用内事件回传：**

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接。**
2. 点击该渠道的“管理对接”图标。
3. 进入**渠道对接**选项卡，向下滚动页面。   

   ![integration-in_app_event_postbacks_toggle.png](https://files.readme.io/20dadaa71b8b54c4512e74a925e66cec9da5e8138bb28a545c5452eef2d38304-14627453566737.png)

</Accordion>

<div id="check-the-event-configuration" />

## 检查事件配置

事件配置方式可能会影响部分回传的发送。

<div id="the-event-wasnt-configured" />

<Accordion title="未配置事件">

请检查您配置的应用内事件列表中是否已包含需要回传的事件。对于未配置的事件，AppsFlyer不会发送回传。

[![list_of_in_app_events.png](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 点击该渠道的“管理对接”图标。
3. 进入**渠道对接**选项卡，向下滚动到**应用内事件回传**部分，检查相关事件的名称是否已在列表中。

</Accordion>

<div id="the-event-was-configured-incorrectly" />

<Accordion title="事件配置有误">

检查<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#事件映射">事件映射</Anchor>是否正确无误。请确保AppsFlyer事件<strong>（即AppsFlyer通过S2S或从您的应用侧接收到的事件名称）与渠道映射事件（即渠道对该事件使用的名称）之间的对应关系正确无误。</strong>

[![in_app_event_postback_mapping_2.png](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)

</Accordion>

<div id="the-event-was-configured-correctly-but-with-a-condition" />

<Accordion title="事件配置正确但带有回传条件">

如果您为某个事件设置了回传条件，那么AppsFlyer就会根据这个条件来发送回传。请检查您是否设置了可能会限制事件回传的条件。

[![in_app_event_condition__1_.png](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)

</Accordion>

<div id="the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner" />

<Accordion title="该事件配置为仅向带量渠道发送回传">

检查相关回传的事件来源是否配置为<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#回传中的事件来源选项">**仅该合作渠道**还是**所有媒体渠道，包括自然流量**</Anchor>。如果是仅该合作渠道，那么AppsFlyer仅发送归因到该渠道的事件回传。

[![in_app_event_sending_options.png](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)

</Accordion>

<div id="the-event-occurred-outside-of-the-configuration-window" />

<Accordion title="事件发生在回传窗口期之外">

AppsFlyer会根据您设置的<Anchor target="_blank" href="/marketers/zh/docs/in-app-event-postback-configuration#应用内事件回传窗口期">回传窗口期</Anchor>来发送回传数据。对于在窗口期结束后发生的事件，AppsFlyer仍会进行记录，但不会向相关渠道发送其回传。

![in_app_event_postback_window.png](https://files.readme.io/21cae7825d557c1ee89c890ec64c922cb36e31be882850a26bfdc4e5595773f0-14661845664401.png)

请注意，在<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns">SRN</Anchor>对接中，应用内事件的回传<Anchor target="_blank" href="/marketers/zh/docs/user-level-data-retention#渠道的数据保留期限">期限</Anchor>为相关SRN的数据保留期限。

</Accordion>

<div id="the-attribution-link-was-configured-not-to-send-postbacks-for-installs" />

<Accordion title="归因链接配置为不发送激活回传">

如果归因链接中包含参数`af_installpostback=false`，则AppsFlyer仅记录激活，而不向渠道发送激活回传。

**请按以下方式检查您的归因链接：**

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 进入**归因链接**选项卡，向下滚动到归因链接部分。

</Accordion>

<div id="privacy-restrictions" />

## 隐私限制

在以下情况中，AppsFlyer会受到隐私政策的限制而不发送回传。

<div id="the-partner-didnt-set-up-advanced-privacy" />

<Accordion title="渠道不支持高级隐私模式或未设置">

如果您启用了<Anchor target="_blank" href="/marketers/zh/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch">高级隐私模式</Anchor>（Advanced Privacy），但渠道侧不支持或未配置高级隐私，他们就无法接收到<Anchor target="_blank" href="/partners/zh/docs/advanced-privacy-guide-postback-macros-for-ad-networks#用于发送回传的各类模版">高级隐私汇总回传</Anchor>。

![partner_not_supporting_ap_postbacks.png](https://files.readme.io/1d8784e8994eba5c403ac706673490b91b7b34ed4d5dbea8c3fe58f227d382c5-15140294126353.png)

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms" />

<Accordion title="媒体渠道对于第三方平台的限制">

部分渠道限制第三方的数据共享。这种情况下，由这些渠道带来的激活全部都会上报为自然量。

</Accordion>

<div id="the-sdk-was-set-not-to-share-information-with-the-partner" />

<Accordion title="SDK设置为不与相关渠道共享信息">

SDK中部署了数据共享的筛选条件，阻止相关渠道接收信息。用户可在相关应用生命周期内的任何时间点明确拒绝数据收集，从而触发该筛选条件生效。

详情请见

</Accordion>

<div id="miscellaneous" />

## 其他

<div id="the-postback-was-sent-but-doesnt-show-on-the-partners-platform" />

<Accordion title="回传已发送，但未在渠道后台显示">

有时虽然AppsFlyer侧已经向渠道发送了回传，但渠道侧却没有显示。发生这种情况时，请联系该渠道。

**请按以下方式确认AppsFlyer侧是否已发送回传：**

1. 从A**ppsFlyer后台的侧边栏中选择报告** > 原始数据导出。
2. 在**回传**部分查看相关报告（激活、应用内事件、再营销转化、应用内事件再营销）。

[![postback_reports.JPG](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)

</Accordion>

<div id="the-event-didnt-occur" />

<Accordion title="事件未发生或未发送到AppsFlyer">

所有已发生的事件都会出现在<Anchor target="_blank" href="/marketers/zh/docs/activity-dashboard">**活跃数据面板**</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/raw-data-reporting-overview?query=raw%20data%20reports">原始数据报告</Anchor>中。如果这两处没有显示某个事件，就说明该事件没有发生，或没有发送到AppsFlyer。

如果您没有在SDK中定义某个事件，就无法在AppsFlyer中看到该事件。

请按以下方式在活跃数据面板或原始数据报告中确认事件是否发生：

**如需在活跃数据面板中查看：**

**如需在原始数据报告中查看：**

1. 从A**ppsFlyer后台的侧边栏中选择报告** > 原始数据导出。
2. 点击**创建报告**。
3. 选择相关报告。
4. 设定日期范围以及其他必要字段，然后点击创建。
5. 下载报告并在其中查看相关事件。

</Accordion>

<div id="differences-in-time-zones" />

<Accordion title="时区差异">

如果AppsFlyer和相关渠道之间的时区设置不同，可能会使回传接收时间有所差异。AppsFlyer的面板和报告会按照您选定的时区来展示数据。

**请按以下方式检查您在AppsFlyer中为相关应用设置的时区：**

1. 从AppsFlyer后台的侧边栏中选择**配置** > **应用配置**。
2. 在**本地化**部分下查看该应用的时区设置。

</Accordion>

<div id="srns-missing-advertising-ids-idfagaid" />

<Accordion title="SRN投放中缺失广告ID（IDFA/GAID）">

在部分<Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid">SRN投放场景</Anchor>中，AppsFlyer不发送激活、应用打开或应用内事件的回传。

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms::40092c14" />

<Accordion title="媒体渠道对于第三方平台的限制">

部分渠道限制第三方的数据共享。对于通过这些渠道获得的用户设备级别数据，AppsFlyer无法将其分享给第三方平台或服务商。这种情况下，由这些渠道带来的激活全部都会上报为自然量。请注意，Meta ads不与第三方平台共享任何数据。

</Accordion>

<div id="advanced-privacy-postbacks" />

<Accordion title="高级隐私保护（AP）回传。">

根据<Anchor target="_blank" href="/partners/zh/docs/advanced-privacy-guide-postback-macros-for-ad-networks#用于发送回传的各类模版">高级隐私模板</Anchor>发送回传

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> <Anchor target="_blank" href="/partners/zh/docs/postback-troubleshooting-for-ad-networks">广告平台的回传问题排查指南</Anchor>

<div data-zendesk-anchors="activation-toggles=%E6%A3%80%E6%9F%A5%E5%AF%B9%E6%8E%A5%E5%BC%80%E5%85%B3 h_01H9FT385FY1QJC6M2YVMZF2NC=%E6%A3%80%E6%9F%A5%E5%AF%B9%E6%8E%A5%E5%BC%80%E5%85%B3 h_01H9FT385FJ0W62NB6FBB6ASKP=the-activate-partner-toggle-was-turned-off h_01H9FT385FKK7VQ293HH9RANBP=the-inapp-event-postbacks-toggle-was-turned-off event-configuration-issues=%E6%A3%80%E6%9F%A5%E4%BA%8B%E4%BB%B6%E9%85%8D%E7%BD%AE h_01H9FT385FW71JV2KKZ22TP6TN=%E6%A3%80%E6%9F%A5%E4%BA%8B%E4%BB%B6%E9%85%8D%E7%BD%AE h_01H9FT385FHFX4PNRQVRXX8A5X=the-event-wasnt-configured h_01H9FT385FE4GCP9D5XCNZ1FAR=the-event-was-configured-incorrectly h_01H9FT385FTT97PJ9NN09K0X9F=the-event-was-configured-correctly-but-with-a-condition h_01H9FT385FDEC21CAZ7V9BBT7M=the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner h_01H9FT385G8HSVJWWGKSRKT381=the-event-occurred-outside-of-the-configuration-window h_01H9FT385GDDV1D6X69JQWPN02=the-attribution-link-was-configured-not-to-send-postbacks-for-installs privacy-restrictions=%E9%9A%90%E7%A7%81%E9%99%90%E5%88%B6 h_01H9FT385G84E2A1J64VWG8H4Z=%E9%9A%90%E7%A7%81%E9%99%90%E5%88%B6 h_01H9FT385G3ECF0PXCE6S2GD5A=the-partner-didnt-set-up-advanced-privacy h_01H9FT385G9YMX9BAEYY0XQR4C=media-source-restrictions-on-thirdparty-platforms h_01HG0YAHWJ565C7BAXAXT75ACB=the-sdk-was-set-not-to-share-information-with-the-partner miscellaneous=%E5%85%B6%E4%BB%96 h_01H9FT385GSWRPKEHKJ4HXCX01=%E5%85%B6%E4%BB%96 h_01H9FT385GTSH1K93WNCARY2BA=the-postback-was-sent-but-doesnt-show-on-the-partners-platform h_01H9FT385G5HK6N2JEE8C6S245=the-event-didnt-occur h_01H9FT385GPVT9WAC6ZTPK6D10=differences-in-time-zones h_01H9FT385G8RXJD25KAQJ28TF6=srns-missing-advertising-ids-idfagaid h_01H9FT385GAYCY615W7M88XJT3=media-source-restrictions-on-thirdparty-platforms::40092c14 h_01JK86ZFXJGPVYJCAAVAY6F4YD=advanced-privacy-postbacks h_01HE7R6G699RG30ZSSQF02AK5Y=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
