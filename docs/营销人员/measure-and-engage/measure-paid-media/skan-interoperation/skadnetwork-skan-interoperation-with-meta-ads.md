---
title: AppsFlyer与Meta ads的SKAN互通指南
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-01-17T10:08:28Z'
  edited_at: '2026-10-14T10:06:41Z'
  id: 360017095198
  locale: zh-cn
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/zh-cn/articles/360017095198
---
> **概要：** 启用AppsFlyer与Meta ads的SKAN互通设置后，一方面Meta ads可以向AppsFlyer发送解析后的SKAN数据，另一方面AppsFlyer也可以与Meta ads分享广告主的CV值映射构架。

<Embed title="AppsFlyer与Meta ads的SKAN互通指南" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/15jnbml3h7" providerUrl="https://fast.wistia.com" />

<div id="skan-interoperability-appsflyer---meta-ads" />

## SKAN互通：AppsFlyer &lt;-> Meta ads

如果您通过多个渠道投放广告，建议您在AppsFlyer后台完成互通设置。这样您就可以利用AppsFlyer平台上的其他可用指标（如成本等）来扩充SKAN的效果指标数据。

<div id="scope-of-skan-interoperability-with-meta-ads" />

#### AppsFlyer与Meta ads的SKAN互通作用范围

与Meta ads互通后可以实现以下功能：

* AppsFlyer和Meta ads会共享SKAN转化值（CV）的映射构架，这样广告主就能同时收到来自这两个平台的投放效果指标。
* AppsFlyer能支持Meta ads中的所有投放目标，从而推动广告优化。这些目标包括：
  * Mobile app install（应用安装，简称MAI）
  * Mobile app engagement（应用互动，简称MAE）
  * Value optimization（价值优化，简称VO）
* SKAN对接启用后，数据链路会发生以下变化：
  * Facebook的SDK停止对SKAN CV的更新（即通过*kill switch*来终止数据流）。
  * AppsFlyer的SDK更新CV值。
  * Meta ads共享SKAN回传数据，这些数据会包含在SKAN面板和汇总报告中。

其他注意事项：

* 在不启用SKAN渠道对接的情况下，SKAN面板会把来自Meta ads的激活计为自然量。
* 在AppsFlyer的归因模式下（即数据总览面板中）：
  * 可准确归因来自Meta ads的新增授权用户。
  * 拒绝授权的用户会归因为自然量。
* <Anchor target="_blank" href="/marketers/zh/docs/self-reporting-networks-srns#ios-145-srn-attribution">iOS 14.5对SRN数据上报的影响</Anchor>
* 我们与Meta Ads的MMP对接设置会默认打开*Advertiser Tracking Enabled*（启用广告主追踪）功能。（（基于2021年2月Meta ads移动广告规范中的iOS 14广告设置流程）

<div id="considerations" />

#### 注意事项

* 启用互通设置后，您更改衡量设置时无需再重复本指南中的MMP对接流程。也就是说，您无需再次复制相关MMP对接的URL。
* 如果您在AppsFlyer后台关闭了SKAN衡量开关，那么Meta ads就无法获得CV值的映射信息。
* AppsFlyer SDK与Facebook SDK的对比：Facebook SDK适用于仅使用Meta ads投放广告的场景。如果是多渠道投放，还是建议您使用AppsFlyer的SDK，因为这样您就可以查看所有渠道的数据。
* 关于可能出现的数据差异，请参阅本文中的[相关部分](/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq)。

<div id="meta-ads-app-install-ads-guidance" />

#### Meta ads中的应用激活广告配置指南

在Meta ads上配置iOS 14应用安装广告时，需特别注意<Anchor target="_blank" href="https://developers.facebook.com/blog/post/2020/10/29/preparing-our-partners-ios-14-latest-guidance-on-skadnetwork/">Meta ads投放指南</Anchor>中的以下几条规则：

* 每个应用最多可以有9个广告系列，每个广告系列下最多可以有5个广告组。
* 您无需专门为iOS 14的广告投放单独设置账户，可以直接通过现有账户投放iOS 14广告。
* 不同的AppsFlyer衡量类型适用于不同的Meta ads优化方式，具体的对应关系如下：
  * **启用收入衡量**：VO和AEO
  * **转化衡量：AEO——包括Meta ads的标准事件和购买事件。请确保将AppsFlyer中设置的事件准确映射到Meta ads。**

<div id="interoperation-procedures" />

## 互通设置流程

请按以下流程完成互通设置。

对于应用激活归因：

<div id="allow-facebook-to-share-skadnetwork-data-with-appsflyer" />

<Accordion title="让Meta ads将SKAN数据共享给AppsFlyer">

让Meta ads将SKAN数据共享给AppsFlyer。如果您不设置互通，就无法在AppsFlyer的SKAN面板中看到归因给Meta ads的SKAN激活。

针对每个应用只需完成一次互通设置。

**请按以下步骤为Meta ads开通与AppsFlyer的SKAN数据共享：**

1. 从AppsFlyer后台进入**协作** > **活跃对接**。
2. 搜索并选择Meta ads。
3. 进入**SKAN**标签页。

   <Image align="center" alt="skan_repprtiing_-_connected_accounts.png" src="https://files.readme.io/41514c220de398871292c990e448e2bc8ce450a17512649842cdb2bc4fd78846-40032591356817.png" />
4. 点击**f login**。您必须使用<Anchor target="_blank" href="https://www.facebook.com/business/help/155909647811305?id=829106167281625">具备以下权限</Anchor>的管理员或广告主账户登录：
   * Ads\_read权限。详见[如何确认广告读取权限](/docs/skadnetwork-skan-interoperation-with-meta-ads#verifying-the-ads_read-permission)。
   * 从Meta企业入口获取广告主应用ID的权限。
5. 请按照用户界面的说明进行操作。  
   Meta会生成一个<Anchor target="_blank" href="https://developers.facebook.com/docs/facebook-login/guides/access-tokens/get-long-lived/">access token</Anchor>（访问密钥），用于开放与AppsFlyer的数据共享。完成相关流程后，您会跳转到AppsFlyer。
6. 如果这是您首次设置该渠道的对接，请确认账户状态显示为**Waiting for sync**（等待同步）。  
   在AF成功从Meta ads获取数据之前都会显示这一状态。
7. 等到第二天的UTC时间02:00之后查看授权状态，并确认状态已变为**Data was pulled successfully**（数据拉取成功）。  
   SKAN控制面板中的数据会在每天UTC时间08:00前更新。
8. 关于可能存在的衡量差异，请参阅本文中的[相关部分](/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook)。

</Accordion>

对于应用内事件归因：

<div id="share-cv-schema-with-facebook" />

<Accordion title="与Meta ads分享CV值映射构架">

<Image align="center" alt="SKAdNetwork-Facebook-AppsFlyer_integration__5_.png" src="https://files.readme.io/f5965dc535a47b3d665a3cf1ae1df564a176ff9be76d5fb4a9f01d80b0e58994-40032652599953.png" />

<div id="enabling-appsflyer-skan-interoperation-with-meta-ads" />

#### AppsFlyer与Meta ads的SKAN互通启用方式

<Table>
  <thead>
    <tr>
      <th>
        步骤
      </th>
      <th>
        操作
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="1"></span>
        1
      </td>
      <td>
        应用侧的前期准备
      </td>
      <td>
        * 在应用中接入最新版本的AppsFlyer <Anchor target="_blank" href="/marketers/zh/docs/sdk-integration-overview">SDK</Anchor>。
      </td>
    </tr>
    <tr>
      <td><span id="2"></span>
        2
      </td>
      <td>
        检查SKAN设置
      </td>
      <td>
        确认已设置并启用AppsFlyer的<Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">SKAN方案</Anchor>，因为这样AppsFlyer的SDK才能调用SKAN API来设置CV。

        **请按以下方式查看SKAN设置**：

        1. 从AppsFlyer后台进入**配置** > **SKAN转化值操作台**。
        2. **点击选项图标⋮** ，确认SKAN衡量已开启。  
           [![Measurement_mode_on_facebook_ads.png](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)
        3. 选择适合您需求的衡量模式。  
           详情请见<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio">SKAN转化值操作台</Anchor>。
        4. 记下应用内事件的准确名称，在下一步流程中会用到。**请注意：** 事件名称区分大小写。
      </td>
    </tr>
    <tr>
      <td><span id="in-app-event-mapping"></span>
        3
      </td>
      <td>
        应用内事件映射
      </td>
      <td>
        检查应用内事件映射是否正确，并作必要的修改。

        **请按以下步骤查看并设置应用内事件映射**：

        1. 从AppsFlyer后台进入**协作** > **活跃对接**。
        2. 选择**Meta ads**。
        3. 【必要操作】打开**渠道对接**选项卡中的**应用内事件回传**开关。
           * 请务必根据当前选定的SKAN衡量模式进行映射。默认的衡量模式为收入模式。  
             ![in-app_events_fb_en-us.png](https://files.readme.io/98e2c8048444331c5d24343e683605e8388ee93bbfcb70aa5e8dad183c995859-40032591364241.png)
           * 请确认SKAN衡量模式中设置的应用内事件（即**AppsFlyer事件**）正确映射到Meta ads的事件标识符（即**渠道映射事件**）。若不设置事件映射，Meta ads就无法优化投放，仅能记录激活数。

             <div id="h_01H8XRMVR5GY77K7GJ4TXGWEHS" />

             > 📘 **注意**
             >
             > 在SKAN转化值操作台中添加、更改或删除转化值（CV）时，请确保相关事件已映射到**应用内事件回传**。否则Meta ads无法呈现CV值的更新。
             >
             > #### <span id="inapp-event-mapping-guide"></span>应用内事件映射指南


        | 衡量选项 | 映射条件 |
        | --- | --- |
        | <span id="custom"></span><Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio#custom">自定义</Anchor> | 把在自定义模式中设置的应用内事件映射到Meta ads。<br /><br />如需通过回传上报收入，必须把**Send revenue**（发送收入）设置为**Values & revenue**（发送值与收入）。<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue*用于总体收入的衡量，一般映射到Meta ads的*fb\_mobile\_purchase*收入事件。<br /><br />请注意：*fb\_mobile\_purchase*可以对应多个事件。 |
        | <span id="revenue"></span>收入 | 如果您想通过向广告平台回传数据来上报收入，请确保您已经在回传中设置了相关应用内收入事件的映射。<br /><br />*af\_skad\_revenue*用于总体收入的衡量，一般映射到Meta ads的*fb\_mobile\_purchase*收入事件。<br /><br />请注意：*fb\_mobile\_purchase*可以对应多个事件。 |
        | <span id="conversion"></span>转化 | 映射1–6个转化事件，与Meta ads的事件一一对应。 |

        4. 点击**保存对接**。
        5. 向下滚动到**SKAN配置**，点击**MMP连接URL**右侧的复制图标。在后续步骤中，您需要把这个URL粘贴到Meta后台，具体位置请见下一部分的说明。

           ![meta_ads_skan_configuration_mmp_url.png](https://files.readme.io/341918a757014d51a240898d157a6576b50cb269ad3bd0a574e4e6aef9d504ef-40032652607377.png)
      </td>
    </tr>
    <tr>
      <td><span id="4"></span>
        4
      </td>
      <td>
        将AppsFlyer连接到Meta ads
      </td>
      <td>
        1. 在Meta ads后台打开events manager（事件管理器），然后 进入**Settings**（设置）选项卡。

           [<Image alt="FacebookSkadNetworkSetup.jpg" src="https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg" width="503px" />](https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg)
        2. 点击“Settings”选项卡中的**Configure events**（配置事件）。

           [<Image alt="mceclip0.jpg" src="https://files.readme.io/208040fdd63fcd80ddc2cac6d0f49ff6b78f5f788f85a5022f5e3c747f268ef9-40032591379217.jpg" width="503px" />](https://files.readme.io/208040fdd63fcd80ddc2cac6d0f49ff6b78f5f788f85a5022f5e3c747f268ef9-40032591379217.jpg)
        3. 在Events Manager中选择**Import from Partner App**（导入MMP的CV映射构架） 。

           [<Image alt="mceclip1.png" src="https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png" width="503px" />](https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png)
        4. 界面会显示**MMP Connection URL**（MMP对接链接）字段，请将相关链接复制粘贴到该字段中。   
           这是为了向Meta发送CV映射信息，并**让广告主应用中的Facebook SDK停止设置CV**。如果“Import from partner app”（导入MMP的CV映射构架）显示为不可用，请参考[问题排查部分](/docs/skadnetwork-skan-interoperation-with-meta-ads#import-from-partner-app-is-disabled)。
        5. 请按照Meta用户界面中的说明进行操作。完成操作后会出现以下两种结果：
           1. **MMP对接URL**成功粘贴到Meta ads用户界面。完成上述操作后，您已顺利完成对接，可以继续完成剩下的步骤。
           2. **MMP对接URL**粘贴失败，Meta ads用户界面报错。如果出现这种情况：  
              - 等待24小时，然后重复以上步骤。  
              - 如果持续出现同样的错误（超过24小时），请联系AppsFlyer技术支持团队。

        说明

        * 该流程只需完成一次，也就是说在AppsFlyer后台更改衡量设置后无需再次复制粘贴对接URL。比如，如果您从收入模式切换到转化模式，Meta ads会使用现有的URL来获取现行的映射构架。
        * 完成该流程后，Meta ads就能通过其独有的随机化结构从AppsFlyer获得CV映射构架，这是广告主无法配置的。
        * 如果您在AF后台更改了衡量设置，新设置会在24小时内开始对Meta ads生效。
      </td>
    </tr>
    <tr>
      <td><span id="5"></span>
        5
      </td>
      <td>
        iOS 14投放设置
      </td>
      <td>
        确认Meta ads后台的iOS 14投放设置已开启。

        您可以在设置页面的**New App installs Campaign**（新建应用安装广告）部分查看该设置。

        [![FBiOS14.png](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="turning-off-the-skan-integration" />

<Accordion title="关闭SKAN对接">

关闭**Meta ads**对接时，不仅需要关闭启用该渠道按钮，还必须删除SKAN连接，才能停止SKAN数据的记录。

**请按以下步骤关闭SKAN对接：**

1. 从AppsFlyer后台进入**协作** > **活跃对接**。
2. 搜索并选择Meta ads。
3. 进入**SKAN**标签页。
4. 点击相关账户的删除图标。

</Accordion>

<div id="measurement-and-timing-differences-between-appsflyer-and-facebook" />

<Accordion title="Meta ads与AppsFlyer之间的衡量方式及时间安排差异">

| 注意事项 | 说明 |
| --- | --- |
| 应用内事件名称 | 2021年8月5日之前，面板沿用了Meta ads的事件名称，但之后不再使用这些事件名称。 |
| 收入模式中的用户转化指标 | 【2021年8月16日弃用】<br /><br />~~在收入模式中，出于收入命名惯例的原因，用户转化（即付费用户）指标不包含通过Meta ads广告系列上报收入的用户数。具体请见上一章节（应用内事件名称）。~~ |
| 数据可用日期 | 对接后每次同步数据时，AppsFlyer会接收最近7天的Meta ads数据。 |
| 激活日期 | AppsFlyer和Meta ads判断激活日期的方式不同，考虑：<ul><li>iOS SKAN回传中不包含激活实际发生的时间。</li><li>Meta ads将回传数据的接收时间作为激活时间，并根据Meta ads中对相关应用设置的时区来界定激活日期。</li><li>AppsFlyer会根据广告主所设置的<Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio#activity-window">用户行为窗口期</Anchor>来推算激活时间。此计算方法不考虑应用级别和Meta ads账户的时区设置。</li></ul> |
| 数据时效性 | <ul><li>AF会在UTC时间的01:00从Meta ads拉取SKAN数据。</li><li>面板和汇总数据会在7小时后更新。</li></ul> |

</Accordion>

<div id="verifying-the-ads_read-permission" />

<Accordion title="检查ads_read权限">

ads\_read权限允许Meta ads客户通过API拉取广告效果数据，用于自定义面板和数据分析。

**请按以下步骤检查您的Meta ads账户是否具有ads\_read权限：**

1. 登入您的<Anchor target="_blank" href="https://developers.facebook.com/apps">Meta ads开发者账户</Anchor>。
2. 选择一个Facebook App ID。
3. 转到 **使用案例 > 权限和功能**.
4. 搜索 `ads_read`.
5. 验证 `ads_read` 是否已准备好使用。如果具有，则无需采取进一步措施。
6. 如果 `ads_read` 未达到使用状态，请申请权限并提交请求。
7. Meta 批准请求后，返回 AppsFlyer 中的 Meta 广告集成页面，然后点击 **连接**.  
   **注意：** Meta 最近对该部分进行了重命名和重组。如果您没有看到 **应用审核**，这是正常的。请求权限的正确位置是 **用例 > 权限和功能**.

</Accordion>

<div id="troubleshooting-discrepancies-and-faq" />

<Accordion title="问题排查、数据差异及高频答疑">

| 操作 | 说明 |
| --- | --- |
| <span id="not-seeing-skan-inapp-events-from-meta"></span>看不到来自 Meta 的 SKAN 应用内事件？ | 如果您看到安装但没有来自 Meta SKAN 活动的应用内事件，此检查清单将帮助您找出缺少的内容。<br /><br />注意：如果您没有看到安装，请先完成安装检查清单。<br /><br />**<span id="quick-fix-checklist"></span>快速修复检查清单**<br /><br />第4步：<ol><li>确认 AppsFlyer 中的 SKAN 事件映射。</li><li>从后台进入**配置** > **SKAN转化值操作台**。</li><li>确保要衡量的应用内事件已正确映射。</li></ol>**第 2 步**<ol><li>检查 Meta 广告集成事件映射。</li><li>在 AppsFlyer 中，转到 **协作** > **活动中的集成** 然后选择 **Meta 广告**.</li></ol><ul><li>确保 SKAN 转换工作室中的相同事件名称（区分大小写）已映射到应用内事件回传到 Meta。</li><li>如果您正在衡量收入，请确保 af\_skad\_revenue 已包含并映射到 fb\_mobile\_purchase。</li></ul>**<span id="still-not-working"></span>仍然不行？**<br /><br />**>最低安装量检查**<ul><li>为了显示SKAN安装后数据，您需要Meta每天每项活动至少有XNUMX个安装。</li><li>低于此门槛的安装将显示为零转化值（CV），无法解码任何事件数据。</li></ul>Meta没有透露这个门槛，但您可以在SKAN仪表板中检查您活动中的零转化值率。如果它约为100%，则您需要增加安装量。根据目标用户群的过滤条件进行调整，或者增加活动安装量。 |
| <span id="facebook-cant-connect"></span>Meta ads无法连接 | **问题描述**<br /><br />在Meta ads后台收到以下报错消息：*we can't connect. Check that you're using the correct URL. If the problem continues, contact your partner app for help.（连接失败，请检查您使用的URL是否正确。如果持续出现该问题，请联您的MMP。）*<br /><br />**解决方式**<br /><br />在AppsFlyer后台确认是否已打开应用内事件映射，以及是否已将AppsFlyer事件映射到Meta ads。（应用内事件映射在上一部分有详细说明）<br /><br />【指南最近更新日期：2021年4月20日】 |
| <span id="event-priority"></span>事件优先级 | 问题：如何在Meta ads后台设置事件优先级？<br /><br />解答：您无需在Meta ads中设置优先级。因为只有使用Facebook SDK设置CV值时才会用到Meta ads的优先级设置功能，但由于您是通过AppsFlyer SDK设置的CV，因此不需要使用该选项。AppsFlyer在转化模式中衡量的6个事件是不分优先级的。<br /><br />【指南最近更新日期：2021年4月20日】 |
| <span id="event-occurrences"></span>事件次数 | 问题：为什么AppsFlyer后台显示的事件发生次数高于Meta ads后台的数据？<br /><br />解答：Meta ads仅统计0-1的事件发生次数。因此即使您界定了更高的事件发生次数范围，Meta ads也不会记录超过1的事件发生次数，只有AppsFlyer会记录超出的部分。 |
| <span id="import-from-partner-app-is-disabled"></span>“Import from partner app“（导入MMP的CV映射构架）不可用 | ![ImportFromPartnerApp.png](https://files.readme.io/c124696c4a8bca7c0d95d812f5390e9672adbfd6fc510a6fa573972f5441cd02-40032591386129.png)<br /><br />**问题描述**<br /><br />Meta ads后台的**Import from partner app**（导入MMP的CV映射构架）不可用，应用没有通过MMP SDK向Meta ads发送任何事件。<br /><br />**解决方式**<br /><br />根据是否使用智能横幅，执行以下步骤：<ul><li>尽快通过MMP SDK向Meta ads发送事件。</li><li>通过Facebook SDK或App Events API向Meta ads发送事件，并从其他两个模式中任选一个来设置转化值映射构架。</li></ul>在Facebook首次记录到事件后，你就可以配置Meta ads与AppsFlyer的对接。<br /><br />【指南最近更新日期：2021年4月25日】 |
| <span id="ranges-cant-overlap-and-must-be-in-consecutive-order"></span>范围之间不能重叠或跳数 | **问题描述**<br /><br />在AppsFlyer的SKAN自定义衡量模式下，在Meta ads中导入CV映射构架时界面显示以下消息：*Ranges can't overlap and must be in consecutive order.（范围之间不能重叠或跳数。）*<br /><br />**解决方式**<br /><br />自定义CV映射构架中的收入值必须设置为连续递增。<br /><br />【指南最近更新日期：2021年4月26日】 |
| <span id="sending-events-to-facebook"></span>向Meta ads发送事件 | **问题**：对于CV衡量选项中未选择的事件，是否有必要向Meta ads发送事件回传？<br /><br />**解答**：对于授权广告跟踪的用户，发送所有事件可提升Meta ads的投放优化能力。 |
| <span id="map-multiple-events-to-the-same-facebook-event"></span>将多个AppsFlyer事件映射到同一个Meta ads事件 | **问题**：是否能将多个AppsFlyer事件映射到同一个Meta ads事件？<br /><br />**解答**：多个事件同时映射到同一个Meta ads标准事件时，由于Meta ads无法区分这些事件，因而会仅针对Meta ads能够识别的某一个事件优化投放。 |
| <span id="no-data-to-pull"></span>没有可以拉取的数据 | **问：** 为什么连接状态显示为“No data to pull:Check your Meta data-sharing permissions”（没有可以拉取的数据：请检查您的Meta数据共享权限）？<br /><br />**解答**：此时可能尚无SKAN数据，或者您需要通过相关账户中的管理员用户角色登入Meta ads。<br /><br />**问：** 界面提示“没有可以拉取的数据：请检查您的Meta数据共享权限”，但我仍能看到Meta ads的数据，这种情况有问题吗？<br /><br />**解答**：区分。界面显示这条报错消息并不代表您的对接有问题，您的数据仍会照常拉取。 |
| <span id="facebook-data-is-not-in-the-dashboard"></span>面板中未呈现Meta ads数据 | **问题描述**<br /><br />在SKAN对接选项卡中，出现*failed to pull data*（无法拉取数据）的报错消息。<br /><br />![FacebookSKAdIntegration.png](https://files.readme.io/42538a59d27815b95b71ec136ebc45b8d918eebf6a2235c90fef59c467128fb2-40032591388177.png)<br /><br />**解决方式**<br /><br />请确认关联账户是否是具有ads\_read权限的Meta ads管理员账户或广告主账户。 |
| <span id="there-is-an-error-in-facebook-when-you-try-to-run-ios-14-campaigns"></span>投放iOS广告时Meta ads后台报错 | **问题描述**<br /><br />背景情况：<ul><li>投放iOS 14广告时Meta ads后台报错</li><li>最近在App Store上架了新应用或面向儿童的应用。</li></ul>出现这种情况是因为Meta ads不知道您使用的SDK适用于SKAN（也就是AppsFlyer SDK）。<br /><br />**解决方式**<ol><li>从AppsFlyer后台进入**协作** > **活跃对接**。</li><li>搜索并选择**Meta ads**。</li><li>关闭**渠道对接**选项卡中的**启用该渠道**开关。</li><li>点击**保存对接**。</li><li>等待15秒。</li><li>打开**激活渠道开关**。</li><li>点击**保存对接**。</li><li>等待Meta ads接收到信号，最长需要24小时。</li></ol> |
| <span id="revenue-reported-by-facebook"></span>由Meta ads上报的收入 | 【最近更新日期：2021年7月12日】<br /><br />Meta ads通过您的SKAN设置根据CV值推算出收入数据。但这不是通过计算公式直接得出的，而是通过Meta ads的算法判定的。<br /><br />因此即使您设置的收入衡量单位是整数，上报的收入数据中也会出现带小数点的值。 |
| <span id="retroactive-data-backfill"></span>回溯性数据补充 | 【最近更新日期：2021年12月23日】<br /><br />有时AF会因为登录失败等情况而无法连接到Meta ads并获取数据。遇到这种情况时您不需要担心，因为AF会在下次登录成功时自动补全前7天的数据缺漏。 |
| <span id="appsflyer-is-showing-significantly-more-installseventsrevenue-than-facebook"></span>AppsFlyer面板上显示的激活/事件/收入远高于Meta ads | 通常出现这样的数据差异是因为Meta ads面板默认只显示点击型激活或事件，而AppsFlyer面板则同时显示点击型和浏览型激活及事件。 |
| <span id="agency-integration"></span>代理对接 | 如果代理商在广告主的Meta ads账户中具有管理员用户的身份，那么他们可以直接代表广告主完成本文所述的SKAN互通操作。广告主也无需登录到其Meta ads账户，广告主账户会对代理登录进行标记。 |
| <span id="an-updated-cv-doesnt-appear-on-facebook"></span>CV更新后Meta As后台未显示 | 在SKAN转化值操作台中添加、更改或删除转化值（CV）时，请确保相关事件已映射到**应用内事件回传**。否则Meta ads无法呈现CV值的更新。 |
| <span id="modeled-data-differences-in-appsflyer-and-facebook-ads-manager"></span>AppsFlyer和Meta ads Manager中的模型推算数据差异 | AppsFlyer模型可以推算出基础SKAN归因无法提供的汇总数据。<Anchor target="_blank" href="/marketers/zh/docs/skan-modeled-data">了解详情</Anchor><br /><br />由于AppsFlyer仅取用已确认的、中立的数据，因此AF模型不使用Meta ads模型推算出来的数据。所以Meta ads Manager的报告和AppsFlyer的报告之间可能会有数据和颗粒度的差异。 |

</Accordion>

<div id="see-also" />

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide">AppsFlyer的SKANetwork解决方案指南</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-facebook=skan%E4%BA%92%E9%80%9Aappsflyer---meta-ads h_01H8XRMVR4JK6ZCGPQJE4D3T26=skan%E4%BA%92%E9%80%9Aappsflyer---meta-ads scope-of-skan-interoperability-with-meta-ads=appsflyer%E4%B8%8Emeta-ads%E7%9A%84skan%E4%BA%92%E9%80%9A%E4%BD%9C%E7%94%A8%E8%8C%83%E5%9B%B4 h_01H8XRMVR4Q7HAJV0B7QB5MDPH=appsflyer%E4%B8%8Emeta-ads%E7%9A%84skan%E4%BA%92%E9%80%9A%E4%BD%9C%E7%94%A8%E8%8C%83%E5%9B%B4 considerations=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 h_01H8XRMVR43KEGWARYMD45S0VY=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 facebook-app-install-ads-guidance=meta-ads%E4%B8%AD%E7%9A%84%E5%BA%94%E7%94%A8%E6%BF%80%E6%B4%BB%E5%B9%BF%E5%91%8A%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97 h_01H8XRMVR48NWM47043YWT63HK=meta-ads%E4%B8%AD%E7%9A%84%E5%BA%94%E7%94%A8%E6%BF%80%E6%B4%BB%E5%B9%BF%E5%91%8A%E9%85%8D%E7%BD%AE%E6%8C%87%E5%8D%97 interoperation-procedures=%E4%BA%92%E9%80%9A%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B h_01H8XRMVR4NVDZ23572F6KJTA9=%E4%BA%92%E9%80%9A%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B h_01H8XRMVR4D07SWXS1TWK42DS3=allow-facebook-to-share-skadnetwork-data-with-appsflyer h_01H8XRMVR5HKXWYB3XN11V48Y0=share-cv-schema-with-facebook enabling-appsflyer-skadnetwork-interoperation-with-facebook=appsflyer%E4%B8%8Emeta-ads%E7%9A%84skan%E4%BA%92%E9%80%9A%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F h_01H8XRMVR56T3X9MJ6KVJF0Z8W=appsflyer%E4%B8%8Emeta-ads%E7%9A%84skan%E4%BA%92%E9%80%9A%E5%90%AF%E7%94%A8%E6%96%B9%E5%BC%8F h_01H8XRMVR5GY77K7GJ4TXGWEHS=%E6%B3%A8%E6%84%8F inapp-event-mapping-guide=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84%E6%8C%87%E5%8D%97 h_01H8XRMVR5T28Q0E8KP6BZ6CGH=%E5%BA%94%E7%94%A8%E5%86%85%E4%BA%8B%E4%BB%B6%E6%98%A0%E5%B0%84%E6%8C%87%E5%8D%97 additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01H8XRMVR5WXZ88676PAW9BKC9=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01H8XRMVR5AW2HZD6JFDYJRNFJ=turning-off-the-skan-integration h_01H8XRMVR5HZ2BBP4XXDEFYT34=measurement-and-timing-differences-between-appsflyer-and-facebook h_01H8XRMVR58DFA2SX20ZEKZRC3=verifying-the-ads_read-permission h_01H8XRMVR5Z9H83X0TAYS50CJ9=troubleshooting-discrepancies-and-faq h_01K7P24YAYSPB84PV0ZGBJ0QB0=quick-fix-checklist h_01K7P2811MRTVRC0D6YGVSXY4C=still-not-working h_01HE7SMBXBCEQM7KF2RG3V16KV=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
