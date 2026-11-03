---
title: SKAN原始数据报告
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T20:54:55Z'
  edited_at: '2026-10-14T10:13:56Z'
  id: 360014261518
  locale: zh-cn
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/zh-cn/articles/360014261518
---
> **概要：** AppsFlyer通过iOS回传以及SKAN原始数据回传接收到相关数据后，对其进行解析并生成设备级数据，然后将这些设备级数据呈现在SKAN原始数据报告中。您可以通过<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">Data Locker</Anchor>和<Anchor target="_blank" href="/marketers/zh/docs/push-api-streaming-raw-data">Push API</Anchor>获取相关数据。如果您订购的套餐中已包含原始数据权限，则无需再单独购买Data Locker。

## SKAN原始数据报告

原理：

* **AppsFlyer通过以下工具提供SKAN原始数据：**
  * **Data Locker**
    * **请注意**：购买了原始数据产品的客户即可使用该功能，无需再另外购买Data Locker。如果您目前尚未使用Data Locker，必须让您账户的管理员配置Data Locker并启用SKAN报告。启用方法为：从AppsFlyer面板进入**报告** > **Data Locker**，然后选择相关的SKAN报告。
    * **数据时效性**：每天更新一次， 数据存储位置：AppsFlyer回传接收日期下的h=23文件夹。
  * **Push API**
    * 数据时效性：请参见<Anchor target="_blank" href="/marketers/zh/docs/push-api-streaming-raw-data">SKAN数据的Push API</Anchor>。
* 激活日期:**由AppsFlyer根据回传接收时间判定，具体如下：**
  * 根据SKAN 4的回传推算激活日期的方式如下：激活日期 = 回传送达时间 - [累计窗口期时长] - [平均回传延时]。
    * 第1次回传：激活日期 = 回传接收时间 - 48h - 36h
    * 第2次回传：激活日期 = 回传接收时间 - 168h - 84h
    * 第3次回传：激活日期 = 回传接收时间 - 840h - 84h
  * 根据SKAN 3的回传推算激活日期的方式如下：激活日期 = 回传送达时间 - 36小时 - [用户上次打开应用的时间距激活的平均小时数]。 
    * 上述公式中的平均激活后小时数默认为12小时。
    * 对于转化值为0的事件（即激活），则平均激活后小时数为0。
  * Google根据自己的逻辑来估算激活时间，AppsFlyer会取用Google得出的激活时间。**请注意**：Google上报激活最长需要45天时间。<Anchor target="_blank" href="/marketers/zh/docs/get-skan-postback-data-from-google-ads#从google-ads拉取skan回传数据">了解详情</Anchor>

可用的报告类型如下：

* **设备回传**：每次发生激活或重新下载（redownload）时AF会收到一次来自相关iOS设备的设备回传。
* **SKAN原始数据**：
  * AppsFlyer会将设备回传解析为原始数据记录。
  * 每次回传都会生成一条激活或重新下载（redownload）记录以及应用内事件记录。
  * 应用内事件记录的数量取决于转化值（CV），具体如下：
    * CV = 0、空值或null值时：不生成应用内事件记录。
    * CV值范围：
      * 1-63:适用于SKAN 3以及SKAN 4窗口1精细值，代表应用内事件记录的条数，具体取决于您的衡量设置。
      * Low、medium、high：适用于SKAN 4粗略值，代表应用内事件记录的条数，具体取决于您的衡量设置。

<strong>为什么有些字段是空的？</strong>以下任一情况都会导致字段出现空值：

* 广告平台未提供campaign\_name（广告系列名称）、ad\_network\_campaign\_id（广告系列ID）、ip等非必要的数据扩充字段。
* 受Apple的阈值规定限制，该数据不开放。受影响的字段包括source\_app\_id、skad\_campaign\_id、skad\_conversion\_value。

## SKAN原始数据报告格式及内容

<div id="raw-data-report-types" />

<Accordion title="原始数据报告类型">

<Table>
  <thead>
    <tr>
      <th>
        报告类型
      </th>
      <th>
        报告名称
      </th>
      <th>
        说明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="postback"></span>
        回传
      </td>
      <td>
        数据回传
      </td>
      <td>
        iOS向广告平台发送回传，广告平台对该回传进行扩充后再发送给AppsFlyer。详情请见[可下载的回传示例](https://docs.google.com/spreadsheets/d/e/2PACX-1vRfFFmj1YV1c73Wbar2VOiKWml6VmsyFvQuydXTPUOO4zXVKmwtw6nup9vKNtNwou2z8IqNpcF4yP6c/pub?gid=1225544365&single=true&output=csv)（CSV格式）。

        请注意：did\_win=false时不包含回传数据。

        **Data Locker中的主题名称**：skad\_postbacks
      </td>
    </tr>
    <tr>
      <td><span id="postback::315d5a62"></span>
        回传
      </td>
      <td>
        回传备份（从Apple侧直接发送）
      </td>
      <td>
        从iOS直接发送到AppsFlyer的回传。

        对iOS 15及以上版本的系统可用，需要广告主进行相关的配置，让应用<Anchor target="_blank" href="/marketers/zh/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">将获得归因的回传发送</Anchor>到AppsFlyer。详情请见[可下载的回传示例](https://docs.google.com/spreadsheets/d/e/2PACX-1vSu0c3gYoIHe2k6_M3cngSFzc-txQvEN38X7Ig7qhXYPg8uBUzyyPqlSwDMugvZS_tUrFjtY8AGYKrh/pub?gid=1225544365&single=true&output=csv)（CSV格式）。

        请注意：该主题仅包含获得归因的回传。

        **Data Locker中的主题名称**：skad\_postbacks\_copy
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event"></span>
        解析后的事件
      </td>
      <td>
        激活假量
      </td>
      <td>
        **首次应用激活**

        SKAN上报*redownload=false*,代表该用户（以Apple ID表示）首次下载相关应用。 *详情请见[可下载的激活报告示例](https://docs.google.com/spreadsheets/d/e/2PACX-1vS4rNJAio8Ub2cffUEiYhzdavVfXaJAD6OpjhRBjVpGQsAlibOWCkZpfLl29n1OCDBZ2eToO4_gOvbl/pub?gid=1472391837&single=true&output=csv)（CSV格式）。*

        **Data Locker中的主题名称**：skad\_installs
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5c7e459f"></span>
        解析后的事件
      </td>
      <td>
        重新下载（Redownloads）
      </td>
      <td>
        **非首次激活的应用激活**

        SKAN上报*redownload=true*。也就是说，该用户（以Apple ID表示）并非首次下载相关应用。该报告的结构与激活报告相同。

        **Data Locker中的主题名称**：skad\_redownloads
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::b8f2b4a4"></span>
        解析后的事件
      </td>
      <td>
        应用内事件
      </td>
      <td>
        **应用内事件**

        2021年7月21日起，AF提供应用内事件原始数据的方式有所变化，具体请见下表。

        应用内事件记录的数量取决于具体的衡量设置。

        详情请见[可下载的应用内事件报告示例](https://docs.google.com/spreadsheets/d/e/2PACX-1vRwhxOmZwTkOr9uNFN0d4Rk2jFpipONoB8KzIZI5Tw12IvoLirj07QUdI9RJoL9rZYFSN1PvT-W6vP0/pub?gid=1454741057&single=true&output=csv)（CSV格式）。

        **Data Locker中的主题名称**：skad\_inapps

        对于2021年7月21日之后接收到的iOS回传：

        | 衡量选项 | 说明 |
        | --- | --- |
        | 收入 | * 具体某个用户的收入。如果收入> 0，会生成一条带有skad\_revenue和event\_name字段的记录。<br />* min\_revenue和max\_revenue字段根据您的自定义转化范围值填充。 |
        | 应用内转化以及漏斗事件 | * 用户每完成一个独立的转化事件即生成一条记录，并在event\_name字段中填充相应的值。如果用户没有完成事件，则不生成记录。<br />* min\_event\_counter = 0且max\_event\_counter = 1的转化事件。 |
        | 应用内互动 | 用于判断某用户完成特定应用内事件的次数，计算方法为`[round up (min_event_counter + max_event_counter) / 2]` |

        对于2021年7月20日及之前接收到的iOS回传：

        | 衡量选项 | 记录条数 | 说明 |
        | --- | --- | --- |
        | 收入 | 0-1 | 如果收入> 0，会生成一条带有skad\_revenue和event\_name字段的记录。 |
        | 转化 | 0-6 | 用户每完成一个独立的转化事件即生成一条记录，并在event\_name字段中填充相应的值。如果用户没有完成事件，则不生成记录。 |
        | 广告交互 | 0-63 | 记录的条数代表用户完成互动事件的次数。如果用户没有互动，则不会生成互动记录。 |
        | 自定义 | 0-无限 | 取决于您的自定义转化构架。 |
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5dac9cbb"></span>
        解析后的事件
      </td>
      <td>
        SRN广告维度
      </td>
      <td>
        * 该报告中包含广告系列、广告组和广告维度的Meta ads事件。报告中的每一行代表一次激活或一个应用内事件。
        * Meta ads发送的SKAN回传中不包含广告组和广告维度的数据。该数据只在该报告中呈现，且不会出现在SKAN面板、Performance API或其他SKAN Data Locker报告中。
        * 该报告无固定结构（schemaless）。Data Locker字段选项不适用于此报告。
        * 推荐方法：请勿将本报告中的数据与其他SKAN报告合并或对比，因为本报告使用的数据由SRN解码，而其他报告数据可能由AppsFlyer解码，二者之间可能存在差异。这些差异可能源自时区、SRN架构差异，或SRN中应用内事件与CV的不准确映射等。
        * 详情请见<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTZjIpqZJxHY9WpIdf9OeDCVQYzM_fLmrpB1oAt3S-MbJTKueOJODwwl6Pz3M0SCAbCFIdMlshOayrw/pub?output=xlsx">可下载的SRN广告维度示例</Anchor>（CSV格式）。

        **Data Locker中的主题名称**：skad\_srn\_advertising\_dimensions
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-field-format-types" />

<Accordion title="原始数据字段格式类别">

#### 字段格式

| 格式名称 | 说明 |
| --- | --- |
| 字符串 [n] | 字符串的长度上限。AF接收数据时并不会对字段长度做出硬性限制，但超过上限的字段可能会被截断。 |
| 时间字符串 | 字符串的格式为`yyyy-mm-dd hh:mm:ss`。使用场景示例：`2019-09-17 00:09:25` |
| 枚举 [n] | 枚举字段仅可包含特定的值。比如成本的货币单位只能由指定的3字符货币代码组成。 |
| 时间戳 | 10位UNIX时间戳。举例来说，<br /><br />UTC时间2020年8月4日07:25的时间戳为： |
| 布尔 | 这类字段的值只有`TRUE`或`FALSE`两种。 |
| 整数 | 整数 |
| 浮点数 | 浮点数（实型）中可以带小数点，且小数点后可以有值。 |

</Accordion>

<div id="fields-available-in-postback-and-postback-copy-reports" />

<Accordion title="回传及回传备份报告中的可用字段">

<table><thead><tr><th>字段名称</th><th>来源或iOS SKAN起始版本</th><th>说明</th><th>格式</th><th>回传备份中是否可用 </th></tr></thead><tbody><tr><td>ad_network_campaign_id</td><td>广告平台</td><td>广告平台上报给AppsFlyer的广告系列ID</td><td>字符串</td><td>否</td></tr><tr><td><p>ad_network_campaign</p><p>_name</p></td><td>广告平台</td><td><p>广告平台上报给AppsFlyer的广告系列名称</p></td><td>字符串</td><td>否</td></tr><tr><td>ad_network_timestamp</td><td>广告平台</td><td><p>广告平台接收到回传的时间</p><p>在Google Ads中，该时间信息是根据Google上报的末次点击时间得出的。</p></td><td>时间戳</td><td>否</td></tr><tr><td>app_id</td><td>AppsFlyer</td><td>以“ID”开头的App ID（广告主应用）。</td><td>字符串</td><td>是</td></tr><tr><td>city</td><td>AppsFlyer</td><td>从2021年8月30日开始，该值总是为null </td><td>字符串</td><td>否</td></tr><tr><td>country_code</td><td>广告平台</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>dma</td><td> </td><td>从2021年8月30日开始，该值总是为null </td><td>字符串</td><td>否</td></tr><tr><td>postal_code</td><td> </td><td>从2021年8月30日开始，该值总是为null  </td><td>字符串</td><td>否</td></tr><tr><td>region</td><td>AppsFlyer</td><td>基于上报的country_code得出</td><td>字符串</td><td>否</td></tr><tr><td>skad_ad_network_id</td><td>1.0 </td><td>X Ads等一部分SRN不共享其ID，这时该字段显示为空。例如，X Ads。 </td><td>字符串</td><td>是 </td></tr><tr><td>skad_attribution_signature</td><td>1.0</td><td> </td><td>字符串</td><td>是</td></tr><tr><td>skad_campaign_id</td><td>1.0</td><td>用于发布该则广告的广告系列ID，范围为0-100。</td><td>字符串</td><td>是</td></tr><tr><td>skad_conversion_value</td><td>2.0 </td><td><p>iOS上报的转化值，范围为0-63。</p><p>若该字段的值为null，则表示iOS未填充该字段\*\* </p></td><td>整数</td><td>是</td></tr><tr><td>skad_redownload</td><td>2.0</td><td>如果该参数的值为true，则表示用户重新下载（redownload）了相关应用</td><td>布尔</td><td>是</td></tr><tr><td>skad_source_app_id</td><td>2.0</td><td><p>子渠道ID，即发布该广告的应用。该字段与source_app_id完全一致。</p><p>字段填充方式取决于隐私阈值\*\*</p></td><td>字符串</td><td>是</td></tr><tr><td>skad_transaction_id</td><td>1.0</td><td> </td><td>字符串</td><td>是</td></tr><tr><td>skad_version</td><td>2.0</td><td> </td><td>字符串</td><td>是</td></tr><tr><td>timestamp</td><td>广告平台</td><td>AppsFlyer接收到SKAN回传的时间 </td><td>时间字符串</td><td>是</td></tr><tr><td>ad_network_name</td><td>广告平台</td><td>广告平台向AppsFlyer上报的广告平台名称。 <ul><li>如果该字段为空，则表示广告平台没有（无法）填充该字段。</li><li>您可以通过skad_ad_network_id来解析广告平台的名称。请使用<a href="./skan-integrated-partners-list#apple-skadnetwork-ids-of-ad-networks" target="_blank">此处表格</a>进行解析。 </li></ul></td><td>字符串</td><td>否</td></tr><tr><td>ip</td><td> </td><td><p>发送回传的iOS设备的HTTP消息中的IP地址</p><p>如果广告平台向AF提供该地址，则该字段中会填充相应的值。</p><p>请注意：该地址信息的获取与SDK无关。</p></td><td>字符串</td><td>否</td></tr><tr><td>skad_app_id</td><td>1.0</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>source_app_id</td><td>AppsFlyer</td><td>子渠道ID，即发布该广告的应用。该字段与skad_source_app_id完全一致。</td><td>字符串</td><td>否</td></tr><tr><td>ad_network_adset_id</td><td>广告平台</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>ad_network_adset_name</td><td>广告平台</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>ad_network_ad_name</td><td>广告平台</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>ad_network_ad_id</td><td>广告平台</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>did_win</td><td>3.0（iOS 14.6）</td><td>用于区分<a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">助攻和获得激活归因</a>的广告系列。 <ul><li>如果该字段值为true，则表示该广告系列获得了此次激活的归因</li><li>如果该字段值为false，则表示该广告系列在此次激活中形成助攻，但不会呈现在任何SKAN面板或报告中。</li><li>如果该字段值为null，则表示<a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">iOS或SKAN版本过低</a>，因此iOS未填充该字段。</li></ul></td><td>布尔</td><td>是</td></tr><tr><td>fidelity_type</td><td>2.2（iOS 14.5）</td><td><p>用于区分<a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">广告呈现</a>方式，这会影响到归因结果。通过0和1来表达，具体如下： </p><ul><li>浏览型广告（View-though Ads）：0</li><li>渲染型广告（StoreKit-rendered Ads）：1</li></ul><p>如果SKAN版本低于2.2，请忽略该字段值。</p></td><td>整数</td><td>是</td></tr><tr><td>ad_network_source_app_id</td><td>广告平台</td><td><span>广告平台上报的流量侧应用（Publisher App）ID，用于核对成本。该数据基于流量侧应用提供的信息得出。</span></td><td>字符串</td><td>否</td></tr><tr><td>ad_network_channel</td><td>广告平台</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>af_prt</td><td>广告平台</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>skad_postback_sequence_index</td><td>4.0（iOS 16.2）</td><td><ul><li>该字段代表SKAN窗口，可能出现的值为<code>0</code>、<code>1</code>或<code>2</code>。</li><li>在SKAN 3中，该字段的值为<code>0</code>。 </li></ul></td><td>整数</td><td>是</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0（iOS 16.2）</p></td><td><ul><li>值可以是<code>low</code>、<code>medium</code>、或<code>high</code>。</li><li>在SKAN 3中，该字段的值为<code>null</code>。</li></ul></td><td>字符串</td><td>是</td></tr><tr><td>skad_source_identifier</td><td>4.0（iOS 16.2）</td><td><ul><li>该字段的值最多可有四位数</li><li>在SKAN 3中，该字段的值为<code>null</code>。 </li></ul></td><td>字符串</td><td>是</td></tr><tr><td>skad_source_domain</td><td>4.0（iOS 16.2）</td><td><ul><li>该字段的值代表可归因的网页广告来源</li><li>在SKAN 3中，该字段的值为<code>null</code>。</li></ul></td><td>字符串</td><td>是</td></tr><tr><td>ad_network_creative</td><td>广告平台</td><td><ul><li>该字段的值基于广告平台提供的扩充数据得出</li><li>在SKAN 3中，该字段的值为<code>null</code>。</li></ul></td><td>字符串</td><td>否</td></tr><tr><td colspan="4">\*\* Apple通过隐私阈值机制来判断是否填充该字段 </td><td> </td></tr></tbody></table>

</Accordion>

<div id="fields-available-in-decoded-event-reports" />

<Accordion title="解析后的事件报告中可用的字段">

<table><thead><tr><th>字段名称</th><th>流量来源</th><th>说明</th><th>格式</th><th>SRN广告维度报告中是否呈现</th></tr></thead><tbody><tr><td>ad_network_campaign_id</td><td>广告平台</td><td>广告平台上报给AppsFlyer的广告系列ID</td><td>字符串</td><td>是</td></tr><tr><td>ad_network_campaign<br/>_name</td><td>广告平台</td><td>广告平台上包给AppsFlyer的广告系列名称</td><td>字符串</td><td>是</td></tr><tr><td>ad_network_timestamp</td><td>广告平台</td><td><p>广告平台接收到回传的时间</p><p>在Google Ads的投放场景中，该字段不填充。 </p></td><td><p>时间戳</p><p>(时间字符串，用于SRN投放维度报告）</p></td><td>是</td></tr><tr><td>app_id</td><td>iOS</td><td>App ID（广告主应用）</td><td>字符串</td><td>是</td></tr><tr><td>city</td><td> </td><td>从2021年8月30日开始，该值总是为null </td><td>字符串</td><td>否</td></tr><tr><td>country_code</td><td>广告平台</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>dma</td><td> </td><td>从2021年8月30日开始，该值总是为null </td><td>字符串</td><td>否</td></tr><tr><td>event_name</td><td>AppsFlyer</td><td><p>在AppsFlyer中配置的应用内事件名称</p><p>在SRN ___report中，该字段为Meta ads中配置的应用内事件。</p></td><td>字符串</td><td>是</td></tr><tr><td>event_uuid</td><td>AppsFlyer</td><td>具有唯一性的随机标识符，便于渠道识别重复的回传</td><td>字符串</td><td>否</td></tr><tr><td>install_date</td><td>iOS</td><td>由AppsFlyer根据回传接收时间估算得出</td><td>时间字符串</td><td>否</td></tr><tr><td>install_type</td><td>iOS</td><td>新增激活</td><td>字符串</td><td>否</td></tr><tr><td>ip</td><td>iOS</td><td><p>发送回传的iOS设备的HTTP消息中的IP地址。</p><p>如果广告平台向AF提供该地址，则该字段中会填充相应的值。</p><p>请注意：该地址信息的获取与SDK无关。 </p></td><td>字符串</td><td>否</td></tr><tr><td>media_source</td><td>iOS</td><td>通过AppsFlyer平台名称获得归因的广告平台</td><td>字符串</td><td>是</td></tr><tr><td>postal_code</td><td> </td><td>从2021年8月30日开始，该值总是为null </td><td>字符串</td><td>否</td></tr><tr><td>region</td><td>AppsFlyer</td><td>根据country_code（国家代码）判定</td><td>字符串</td><td>否</td></tr><tr><td>skad_ad_network_id</td><td>iOS</td><td>接收回传的广告平台的ID</td><td>字符串</td><td>否</td></tr><tr><td>skad_ambiguous_event（SKAN 4+已弃用）</td><td>AppsFlyer</td><td>如果该参数的值为true，则表示iOS回传的接收时间在广告主在面板中更改SKAN设置后的最初72小时内。由于SKAN使用的计时器过多，因此AppsFlyer无法准确地映射该事件。<ul><li>在SKAN 4以上版本中不可用</li></ul></td><td>布尔</td><td>否</td></tr><tr><td>skad_attribution_signature</td><td>iOS</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>skad_campaign_id</td><td>iOS</td><td>用于发布该则广告的广告系列ID，范围为0-100。</td><td>整数</td><td>否</td></tr><tr><td>skad_conversion_value</td><td>iOS</td><td><p>iOS上报的转化值，范围为0-63。</p><p>若该字段的值为null，则表示iOS未填充该字段\*\*</p></td><td>整数</td><td>否</td></tr><tr><td>skad_mode</td><td>AppsFlyer</td><td>用于解析iOS回传的转化衡量模式，可用值包括：<ul><li>custom_decode</li><li>revenue</li><li>events</li><li>skan4</li><li>custom_encode</li><li>engagement</li></ul></td><td>字符串</td><td>否</td></tr><tr><td>skad_redownload</td><td>iOS</td><td>如果该字段的值为true，则表示用户重新下载了相关应用</td><td>布尔</td><td>否</td></tr><tr><td>skad_revenue</td><td>iOS</td><td>以USD为单位的事件收入金额。</td><td>浮点数</td><td>否</td></tr><tr><td>skad_source_app_id</td><td>iOS</td><td><p>子渠道ID，即发布相关广告的应用。</p><p>字段填充方式取决于隐私阈值\*\*</p></td><td>字符串</td><td>否</td></tr><tr><td>skad_transaction_id</td><td>iOS</td><td>-</td><td>字符串</td><td>否</td></tr><tr><td>skad_version</td><td>iOS</td><td>-</td><td>字符串</td><td>否</td></tr><tr><td>timestamp</td><td>iOS</td><td><p>AppsFlyer接收到SKAN回传的时间</p><p>在Google Ads和Meta ads投放场景中，该字段代表AppsFlyer从Google和Meta ads API接收到数据的时间</p></td><td><p>时间戳</p><p>(时间字符串，用于SRN投放维度报告）</p></td><td>是</td></tr><tr><td>event_value</td><td>S2S</td><td><p>默认值为null</p><p>包含一个字符串。该字符串的设置取决于使用自定义解析（custom decode）模式的应用。</p><p>该数据供广告主在其内部系统中使用，AppsFlyer不会使用该数据。 </p></td><td>字符串（JSON）</td><td>否</td></tr><tr><td>ad_network_adset_id</td><td>广告平台</td><td> </td><td>字符串</td><td>是</td></tr><tr><td>ad_network_adset_name</td><td>广告平台</td><td> </td><td>字符串</td><td>是</td></tr><tr><td>ad_network_ad_name</td><td>广告平台</td><td> </td><td>字符串</td><td>是</td></tr><tr><td>ad_network_ad_id</td><td>广告平台</td><td> </td><td>字符串</td><td>是</td></tr><tr><td>skad_did_win (1)</td><td>3.0（iOS 14.6）</td><td>用于区分<a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">助攻和获得激活归因</a>的广告系列。 <ul><li>如果该字段值为true，则表示该广告系列获得了此次激活的归因</li><li>如果该字段值为false，则表示该广告系列在此次激活中形成助攻，但不会呈现在任何SKAN面板或报告中。</li><li>如果该字段值为null，则表示<a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">iOS或SKAN版本过低</a>，因此iOS未填充该字段。</li></ul></td><td>布尔</td><td>否</td></tr><tr><td>skad_fidelity_type (1)</td><td>2.2（iOS 14.5）</td><td><p>用于区分<a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">广告呈现</a>方式，这会影响到归因结果。通过0和1来表达，具体如下： </p><ul><li>浏览型广告（View-though Ads）：0</li><li>渲染型广告（StoreKit-rendered Ads）：1</li></ul><p>如果SKAN版本低于2.2，请忽略该字段值。</p></td><td>整数</td><td>是</td></tr><tr><td>ad_network_source_app_id (1)</td><td>广告平台</td><td><span>广告平台上报的流量侧应用（Publisher App）ID，用于核对成本。该数据基于流量侧应用提供的信息得出。</span></td><td>字符串</td><td>否</td></tr><tr><td>ad_network_channel (1)</td><td>广告平台</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>af_prt (1)</td><td>广告平台</td><td> </td><td>字符串</td><td>否</td></tr><tr><td>min_revenue </td><td>AppsFlyer</td><td>参见脚注（4）</td><td>实数</td><td>否</td></tr><tr><td>max_revenue  </td><td>AppsFlyer</td><td>参见脚注（4）</td><td>实数</td><td>否</td></tr><tr><td>event_revenue</td><td>AppsFlyer</td><td>计算方式：[以USD为单位的具体事件值总和]/[在指定日期中的事件发生数量]</td><td>浮点数</td><td>是</td></tr><tr><td>min_event_counter</td><td>AppsFlyer</td><td>用于计算用户完成某一事件的次数。参见脚注（3）</td><td>整数</td><td>否</td></tr><tr><td>max_event_counter</td><td>AppsFlyer</td><td>参见脚注（3）</td><td>整数</td><td>否</td></tr><tr><td>min_time_post_install</td><td>AppsFlyer</td><td>参见脚注（5）</td><td>整数</td><td>否</td></tr><tr><td>max_time_post_install</td><td>AppsFlyer</td><td>参见脚注（5）</td><td>整数</td><td>否</td></tr><tr><td>af_attribution_flag</td><td>AppsFlyer</td><td>单一可信数据源（SSOT）机制启用时：如果该字段的值为true，则表示该次激活同时被AppsFlyer和SKAN归因。如果该值为false，则表示该次激活没有被AppsFlyer归因。即使skad_conversion_value的值为null，该参数的值仍为true或false（取决于<a href="./skan-modeled-data#null-conversion-values" target="_blank">模型推算</a>）。</td><td>布尔</td><td>否</td></tr><tr><td>measurement_window</td><td>AppsFlyer</td><td>用户行为窗口期的时长。默认情况下，该字段的值为24h（即窗口期默认为24小时）。 </td><td>整数</td><td>否</td></tr><tr><td>interval</td><td>AppsFlyer</td><td>用户行为窗口期间隔时长。 </td><td>整数</td><td>否</td></tr><tr><td>user_agent</td><td>AppsFlyer</td><td>设备用户代理（User Agent）</td><td>字符串</td><td>否</td></tr><tr><td>skad_postback_sequence_index</td><td>4.0（iOS 16.2）</td><td><ul><li>该字段代表SKAN窗口，可能出现的值为<code>0</code>、<code>1</code>或<code>2</code>。</li><li>在SKAN 3中，该字段的值为<code>0</code>。 </li></ul></td><td>整数</td><td>是</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0（iOS 16.2）</p></td><td><ul><li>值可以是<code>low</code>、<code>medium</code>、或<code>high</code>。</li><li>在SKAN 3中，该字段的值为<code>null</code>。</li></ul></td><td>字符串</td><td>是</td></tr><tr><td>skad_source_identifier</td><td>4.0（iOS 16.2）</td><td><ul><li>该字段的值最多可有四位数</li><li>在SKAN 3中，该字段的值为<code>null</code>。 </li></ul></td><td>字符串</td><td>是</td></tr><tr><td>skad_source_domain</td><td>4.0（iOS 16.2）</td><td><ul><li>该字段的值代表可归因的网页广告来源</li><li>在SKAN 3中，该字段的值为<code>null</code>。</li></ul></td><td>字符串</td><td>是</td></tr><tr><td>ad_network_creative</td><td>广告平台</td><td><ul><li>该字段的值基于广告平台提供的扩充数据得出</li><li>在SKAN 3中，该字段的值为<code>null</code>。</li></ul></td><td>字符串</td><td>否</td></tr><tr><td colspan="4"><p>\*\* Apple通过隐私阈值机制来判断是否填充该字段</p><p>（1）从2021年6月2日开始，报告中增加了这个字段。但不一定带有值。</p><p>（3）用于判断某用户完成特定应用内事件的次数，计算方法为：<code>[round up (min_event_counter + max_event_counter) / 2]</code>请注意： <mark>必须四舍五入取整。</mark><br/>举例来说，<br/>A. 如果min = 0，max = 1，则平均值为0.5；取整后得到的结果为1。<br/>B. 如果min = 5，max = 10，则平均值为7.5；取整后得到的结果为8。</p><p>(4) 收入数据总是呈现在字段<code>skad_revenue</code>中。如果您使用SKAN 4或<a href="./skan-conversion-studio" target="_blank">自定义模式（Custom Mode）</a>，则用于计算skad_revenue的范围（即关联到相关事件的范围）通过min_revenue 和max_revenue表达。</p><p>（5）</p><ul><li>在自定义模式（Custom）中：AppsFlyer对于激活时间的计算方式为回传接收时间 - 36h - (min_time_post_install + max_time_post_install)的平均值。但如果CV = 0，则(min_time_post_install + max_time_post_install)的平均值视为0。 </li><li>在解析模式（Decode）中：min_time_post_install比max_time_post_install中设置的值少一小时，max值等于您在解析模式的转化映射中设置的<a href="./skan-cv-decode-map-your-cv-to-events#decode-csv-file-specification" target="_blank">hours_from_install</a>。 </li></ul></td><td> </td></tr></tbody></table>

</Accordion>

## 其他相关信息

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 渠道权限 | 向广告平台提供回传数据 |
| 代理访问权限 | 不可用 |
| 代理数据透明化 | 不适用 |
| 时区 | UTC |
| 货币 | USD |
| 自然量数据 | 基于SDK事件数据得出。比如，自然激活指标的计算方式如下：由SDK上报的所有激活减去由SKAN上报的非自然激活。 |
| 非自然量数据 | 基于SKAN回传得出 |
| 数据时效性 | 每天更新一次，SKAN时效：iOS会在窗口期结束后的24-28小时内上报相关激活。 |
| 历史数据 | 受Data Locker数据可用期限的限制。 |
| 相关账户下的用户权限 | 可用。具体取决于账户授权。 |

</Accordion>

> 📄 **相关文档**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-solution-guide#reporting-options">可用的SKAN报告（SKAN解决方案指南）</Anchor>

<div data-zendesk-anchors="skan-raw-data-reports=skan%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A 01H8XHATZB2G6YZ9AJNPRZS59Y=skan%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A skan-raw-data-report-format-and-content=skan%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E6%A0%BC%E5%BC%8F%E5%8F%8A%E5%86%85%E5%AE%B9 01H8XHATZCJQZTZF0Y5P18XMEA=skan%E5%8E%9F%E5%A7%8B%E6%95%B0%E6%8D%AE%E6%8A%A5%E5%91%8A%E6%A0%BC%E5%BC%8F%E5%8F%8A%E5%86%85%E5%AE%B9 01H8XHATZCR5BC2P5TSQTMDY5Q=raw-data-report-types 01H8XHATZC0MST5ASGWDGGK2R8=raw-data-field-format-types field-formats=%E5%AD%97%E6%AE%B5%E6%A0%BC%E5%BC%8F 01H8XHATZCZMNGK72DDE5HS6E9=%E5%AD%97%E6%AE%B5%E6%A0%BC%E5%BC%8F 01H8XHATZC24DH4AYB2C523JDH=fields-available-in-postback-and-postback-copy-reports 01H8XHATZCNXVG0E3MZ9H68AA1=fields-available-in-decoded-event-reports additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H8XHATZD9D7JBHTFZ095EBD5=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF 01H8XHATZDMV0VN4BDTECGF91K=traits-and-limitations h_01HDNYQBVZP0A6SQASGDRFVFGP=%E7%9B%B8%E5%85%B3%E6%96%87%E6%A1%A3" />
