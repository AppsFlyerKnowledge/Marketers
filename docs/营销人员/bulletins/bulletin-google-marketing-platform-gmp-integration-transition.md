---
title: 公告：迁移到新的GMP对接
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-12-18T11:43:04Z'
  edited_at: '2026-10-14T10:10:06Z'
  id: 21035061438737
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/21035061438737
---

<Table>
  <tbody>
    <tr>
      <td>
        **最新动态**
      </td>
      <td>
        为了应对即将生效的欧盟<Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">《数字市场法案》</Anchor>（DMA），Google对其<Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">欧盟用户意见征求政策</Anchor>进行了更新。AppsFlyer正在进行必要调整，以支持Google的政策规定。

        目前可用的Google Marketing Platform（谷歌营销平台，简称GMP）对接如下：

        * 【历史对接】CM360（DoubleClick）`doubleclick_int`
        * <Anchor target="_blank" href="/marketers/zh/docs/google-marketing-platform-display-video-360-dv360-integration">【新对接】DV360</Anchor> `dv360_int`

        截至2024年7月，遗留的doubleclick\_int集成即将进入弃用模式，并将很快被弃用（最终日期将另行通知）。如果您正在使用该对接，请务必迁移到新的DV360对接，以确保您能持续连贯地使用GMP进行广告投放及其归因衡量时。
      </td>
    </tr>
    <tr>
      <td>
        **亟需处理**
      </td>
      <td>
        请尽快迁移到DV360的新对接`dv360_int`。
      </td>
    </tr>
    <tr>
      <td>
        **操作流程**
      </td>
      <td>
        请确保在GMP和AppsFlyer两个平台中都完成相关配置：

        **GMP中的配置**

        1. 登入您的CM360或DV360帐户。  
           **请注意：** 在CM360中完成这些步骤后，无需在DV360中重复该流程。
        2. 请按照<Anchor target="_blank" href="https://support.google.com/displayvideo/answer/10956727">相关说明</Anchor>创建新的渠道归因链接（Link ID）或重复利用现有链接。

        **AppsFlyer中的配置**

        1. 请按照<Anchor target="_blank" href="/marketers/zh/docs/google-marketing-platform-display-video-360-dv360-integration#integration-procedures">相关说明</Anchor>在AppsFlyer中完成DV360的对接配置。   
           **请注意：** 为了保证数据的连贯性，新对接的配置（包括回溯窗口、应用内事件回传等）必须与历史对接保持一致。
        2. **测试新对接：**  
           等待大约一天以确认新的集成数据。您可以然后禁用旧版集成。
      </td>
    </tr>
    <tr>
      <td>
        **重要须知**
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <table><thead><tr><th><strong>注意事项</strong></th><th>可用方案</th></tr></thead><tbody><tr><td colspan="2"><span id="media-source-pid"></span><p><strong>媒体渠道PID</strong></p></td></tr><tr><td><span id="after-completing-the-migration-the-dv360-media-source-pid-changes-from-doubleclick_int-to-dv360_int"></span><p>迁移完毕后，DV360的媒体渠道PID将从<kbd>doubleclick_int</kbd>变为<kbd>dv360_int</kbd>。</p></td><td>如果您需要将AppsFlyer侧的原始数据拉取到您的BI或任何第三方分析工具中，请注意这里的媒体渠道名称变化。</td></tr><tr><td colspan="2"><span id="outofstore-apps"></span><p><strong>第三方商店中的应用</strong></p></td></tr><tr><td><span id="apps-from-unofficial-app-stores-arent-supported-in-the-dv360-integration-the-integration-relies-on-a-link-id-which-is-generated-for-apps-obtained-through-official-app-stores"></span><p>来自非官方应用商店的应用程序在DV360集成中不受支持。该集成依赖于链接 ID，该 ID 是为通过官方应用商店获取的应用生成的。</p></td><td>如果您的应用程序是从官方应用商店以外的来源下载的，请联系您的客户成功经理或发送电子邮件至 hello@appsflyer.com。</td></tr><tr><td colspan="2"><span id="attribution-data-duplication"></span><p>归因数据分发</p></td></tr><tr><td colspan="2"><span id="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span>当两个集成都处于活动状态并对安装进行归因时，归因在它们之间随机分配，一个作为主要来源，另一个作为贡献者。这确保数据不会被重复.例如，如果DV360负责100个安装，您可能会看到来自传统集成的70个安装和来自DV360的30个安装，或者来自DV360的80个安装和来自传统集成的20个安装。</td></tr><tr><td colspan="2"><span id="inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span><span>对于归因到历史对接的激活/再互动，其后续产生的应用内事件仍会归因到历史对接。</span></td></tr><tr><td colspan="2"><span id="reengagement-reengagement-attribution-is-supported-in-the-dv360-integration"></span><p><strong>Re-engagement（再互动）</strong></p><p>再参与归因在DV360集成中得到支持。</p></td></tr></tbody></table>

        字段差异

        由于旧版和更新版API中可用数据字段的差异，您可能会看到某些AppsFlyer字段的差异，如下所示：

        | AppsFlyer字段 | 遗留字段 (doubleclick\_int) | DV360字段（dv360\_int） |
        | --- | --- | --- |
        | 即广告系列的名称 | placement\_id | line\_item\_name |
        | 即广告系列的ID | placement\_id | line\_item\_id |
        | 即广告组的名称 | ad\_id | 这样的资源是不支持的。 |
        | 即广告组的ID | ad\_id | 这样的资源是不支持的。 |
        | 即相关广告的名称 | creative\_id | 这样的资源是不支持的。 |
        | 即相关广告的ID | creative\_id | creative\_id |
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected%0Ainapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly=while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly reengagement%0Areengagement-attribution-is-supported-in-the-dv360-integration=reengagement-reengagement-attribution-is-supported-in-the-dv360-integration" />
