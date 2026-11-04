---
title: 从Firebase Dynamic Links迁移到AppsFlyer
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-06-19T09:27:37Z'
  edited_at: '2026-10-14T09:59:53Z'
  id: 16282289097105
  locale: zh-cn
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/zh-cn/articles/16282289097105
---
> **概要：**



<div id="migrate-from-firebase-to-appsflyer" />

<div id="about-the-migration" />

## 如何从Firebase迁移到AppsFlyer

**前期准备**

* 来自Firebase的动态链接
* 应用开发人员

迁移到 AppsFlyer：

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="第1步：创建一个AppsFlyer账号">

* <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">创建一个AppsFlyer账号</Anchor>。
* <Anchor target="_blank" href="/marketers/zh/docs/user-management">在账户下添加用户，并为其开放必要权限</Anchor>

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="第2步：添加您的应用">

* 在AppsFlyer后台<Anchor target="_blank" href="/marketers/zh/docs/adding-an-app-to-appsflyer">添加您的应用</Anchor>。
* 【可选】<Anchor target="_blank" href="/marketers/zh/docs/set-up-re-attribution-window">再归因窗口期</Anchor>默认为90天，您可以根据自己对活跃用户的定义来调整该窗口。

用于添加标识符

</Accordion>

<div id="step-3-create-a-onelink-template" />

<Accordion title="第3步：">

您必须先配置模板，然后才能创建链接并打造终端用户体验。

* <Anchor target="_blank" href="/marketers/zh/docs/create-a-onelink-template#创建onelink模板">创建一个OneLink模板</Anchor>
  * <Anchor target="_blank" href="/marketers/zh/docs/user-management">配置模板的市场人员必须具备AppsFlyer的管理员账户或OneLink</Anchor>模板的添加/修改权限。

</Accordion>

<div id="step-4-set-up-the-appsflyer-sdk" />

<Accordion title="第4步：">

在您的应用中接入AppsFlyer SDK是为了在该应用与AppsFlyer之间建立连接，实现以下功能：

* 深度链接 - SDK支持Unified Deep Linking（UDL）方案
* 归因 - SDK上报应用激活、应用打开、应用内事件等。

按照以下步骤将AppsFlyer SDK接入您的应用中。

<div id="appsflyer-sdk-integration-steps" />

#### AppsFlyer SDK对接流程

1. 将AppsFlyer SDK接入相关应用。  
   具体操作说明请参见<Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">安卓</Anchor>和iOS的SDK接入指南。
2. 使用AppsFlyer的推荐方案映射您想要记录的应用内事件。  
   您可以通过<Anchor target="_blank" href="/marketers/zh/docs/in-app-events-overview">SDK</Anchor>或<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>来完成映射。
3. 处理Firebase的SDK。  
   您可以删除其他SDK，直接切换到AppsFlyer，或将其他SDK保留数周，在过渡期间同时使用两个SDK。下表对这两种方法进行了分析对比。  

| 可选方案 | 后续任务  <br />发布更新后的应用版本 | 成效 |
| --- | --- | --- |
| 删除Firebase的SDK（推荐） | 仅AppsFlyer记录新增激活并更新用户记录。  <br />在所有用户都完成应用更新之前，Firebase仍会显示用户执行的事件。 | <ul><li>快速过渡。</li><li>无重复归因。</li><li>您可以查看是否仍然存在含有Firebase SDK的应用版本</li></ul> |
| 在过渡期间保留Firebase的SDK | AppsFlyer和Firebase同时对新增激活进行归因，并记录事件。过渡完毕后请务必移除Firebase的SDK。 | <ul><li>可以进行数据验证。也就是说，您可以比较AppsFlyer和Firebase提供的数据。</li><li>会产生重复归因，从而导致广告平台收取双重费用，</li><li>工作量更大。</li></ul> |

4. 完成配置流程中的所有待办事项后，请在商店中上线更新后的应用版本（即装有AppsFlyer SDK的应用）。这样，后续的新用户就会由AppsFlyer归因。   
   **请注意**：
   * 请确保在App Store、Google Play和其他第三方商店中上线更新后的应用。
   * 安卓应用可能会有非官方的APK下载渠道（请使用您的应用包名进行搜索，检查是否存在这种情况）。APK下载站点中的应用更新需要一定的时间，在此期间可能会有自然用户通过这些站点下载不带AppsFlyer SDK的旧版本应用。
   * 应用商店中的新版本上线可能需要几天时间才能全部完成，在此期间用户仍有可能下载到旧版本的应用。

</Accordion>

<div id="step-5-understand-parameter-mapping" />

<Accordion title="第5步：">

了解Firebase Dynamic Links参数如何映射到AppsFlyer的相应参数。

正确映射和理解相应的参数将确保您的链接可获得连贯一致的结果。

下表列出了Firebase的所有参数和对应的AppsFlyer参数。

迁移到AppsFlyer时，您可以参考此表，为当前所有现行参数进行映射。

<div id="note" />

> 📘 **注意**
>
> 若有未列出的Firebase参数，那是因为AppsFlyer已在 OneLink模板设置中涵盖了该参数，因而无需在链接中另行添加。

<table><thead><tr><th>分组</th><th>Firebase</th><th>AppsFlyer</th><th>说明</th></tr></thead><tbody><tr><td>移动端参数</td><td>链接</td><td><ul><li>af_dp</li><li>deep_link_value</li></ul></td><td><ul><li> <strong>af_dp - URI scheme，作为调起iOS和安卓应用时的备用方案。</strong> </li><li> <strong>deep_link_value</strong> - 是一个值的名称，指的是用户点击链接后跳转到应用中的哪个具体页面。</li></ul></td></tr><tr><td> <br/>安卓参数</td><td>afl</td><td>af_android_url</td><td></td></tr><tr><td rowspan="2">iOS参数<br/><br/> </td><td>ifl</td><td>af_ios_url</td><td></td></tr><tr><td>efr</td><td>af_force_deeplink</td><td>使用af_dp中的URI scheme强制打开iOS应用。若不添加此参数，系统不会使用URI scheme打开应用</td></tr><tr><td>其他平台的URL</td><td>OFL</td><td>af_web_dp</td><td></td></tr><tr><td rowspan="3"> <br/>社交媒体标签<br/><br/> </td><td>st</td><td>af_og_title</td><td>用于对社交媒体上共享内容的标题进行自定义</td></tr><tr><td>sd</td><td>af_og_description</td><td>用于对社交媒体上共享内容的描述进行自定义</td></tr><tr><td>si</td><td>af_og_image</td><td>用于对社交媒体上共享内容的图像进行自定义</td></tr><tr><td rowspan="5"><p>分析参数 <br/><br/><br/><br/> </p></td><td>utm_source</td><td>pid</td><td>Media Source（媒体渠道）</td></tr><tr><td>utm_medium</td><td>af_channel</td><td>用于标识分发广告的媒体渠道</td></tr><tr><td>utm_campaign</td><td>c</td><td>即广告系列的名称</td></tr><tr><td>utm_term</td><td>af_keywords</td><td>文本定向型广告的关键词列表</td></tr><tr><td>utm_content</td><td>af_adset</td><td>某个广告系列下的一系列相关广告</td></tr></tbody></table>

</Accordion>

<div id="step-6-create-onelink-links-with-mapped-parameters" />

<Accordion title="第6步：">

您可以使用已映射的参数，在OneLink模板中创建OneLink链接。

请参考下表信息，选择最贴合您需求的迁移方式。

| Firebase | AppsFlyer | 适用场景 | 说明 |
| --- | --- | --- | --- |
| Firebase面板 | <Anchor target="_blank" href="/marketers/zh/docs/onelink-guide">OneLink管理页面</Anchor> | 您想要逐个创建OneLink链接。该方式可帮助您充分利用OneLink的所有功能和可用场景 |  |
| Dynamic Link Builder API | <Anchor target="_blank" href="/marketers/zh/docs/user-invite-attribution">SDK</Anchor> | 您希望以程序化的方式生成链接，用于用户邀请和推荐等 | <ul><li>需要iOS或安卓开发人员</li></ul> |
| Firebase REST API | <Anchor target="_blank" href="/marketers/zh/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> | 您希望在移动端以外的环境中以程序化的方式创建链接 | <ul><li>需要开发人员</li><li>免费套餐不支持该功能</li></ul> |
| 手动创建链接 | <Anchor target="_blank" href="/marketers/zh/docs/understand-onelink-short-vs-long-urls">长链</Anchor> | 您希望使用查询参数手动创建链接。适用于不需要短链的场景（如CTA按钮或横幅背后的链接） |  |
|  | <Anchor target="_blank" href="/marketers/zh/docs/perform-onelink-bulk-actions-via-csv">批量链接</Anchor> | 您希望将所有Firebase动态链接批量迁移到AppsFlyer。<br /><br />建议您使用这种方式，因其可确保快速无误地迁移所有链接 | <ul><li>[需要完成前期准备：根据相应的Firebase参数映射链接参数的键值对](/docs/migrate-from-firebase-dynamic-links-to-appsflyer#map-parameters)</li><li>免费套餐不支持该功能</li></ul> |
|  | <Anchor target="_blank" href="/marketers/zh/docs/smart-banners-mobile-web-to-app-for-marketers">智能横幅</Anchor> |  |  |
|  | <Anchor target="_blank" href="/marketers/zh/docs/set-up-smart-script-to-convert-web-visitors">智能脚本</Anchor> | 如果您希望在网页中创建动态长链，用于网页到应用的用户体验 |  |

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/brand-onelink-with-your-domain">品牌域名</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/using-firebase-and-google-tag-manager-with-appsflyer-overview">结合使用Firebase和Google Tag Manager与AppsFlyer的对接 - 概述</Anchor>

<div data-zendesk-anchors="overview=%E5%A6%82%E4%BD%95%E4%BB%8Efirebase%E8%BF%81%E7%A7%BB%E5%88%B0appsflyer how-to-migrate-from-firebase-to-appsflyer=%E5%A6%82%E4%BD%95%E4%BB%8Efirebase%E8%BF%81%E7%A7%BB%E5%88%B0appsflyer h_01J7ZPPQ340PNQ70FZAQY4GBZ1=%E5%A6%82%E4%BD%95%E4%BB%8Efirebase%E8%BF%81%E7%A7%BB%E5%88%B0appsflyer 01H8K961JHRXNQHBVN930XW70Q=%E5%A6%82%E4%BD%95%E4%BB%8Efirebase%E8%BF%81%E7%A7%BB%E5%88%B0appsflyer 01H8K961JHCK0Z4GTTHCAKF98E=%E5%A6%82%E4%BD%95%E4%BB%8Efirebase%E8%BF%81%E7%A7%BB%E5%88%B0appsflyer h_01J5QWWGWGDBEF8RY3DZ5XAN3G=step-1-create-an-appsflyer-account h_01J5QWWGWGN17673GYFZWPNKQR=step-2-add-your-app h_01J5QWWGWGKJPRCG9N93B8KBYW=step-3-create-a-onelink-template h_01J5QWWGWGCQFHBQ9EC0QTPF4S=step-4-set-up-the-appsflyer-sdk appsflyer-sdk-integration-steps=appsflyer-sdk%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B h_01J5QXST2K890DV7QS6S9K3A01=appsflyer-sdk%E5%AF%B9%E6%8E%A5%E6%B5%81%E7%A8%8B h_01J5QWWGWGPRF5DRMMQ14BJCFA=step-5-understand-parameter-mapping 01H8K961JHBXVKXM0XQYY605EQ=%E6%B3%A8%E6%84%8F h_01J5QWWGWG3ST19WDRZXN8FK8Q=step-6-create-onelink-links-with-mapped-parameters h_01HE7SZPKKQETH260G45V0D0HN=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
