---
title: 公告：重要公告：如何通过Google Install Referrer获取Meta ads原始数据
metadata:
  keywords:
    - Advertisers
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
  created_at: '2021-10-21T07:02:51Z'
  edited_at: '2026-10-14T10:13:31Z'
  id: 4409322107537
  locale: zh-cn
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/zh-cn/articles/4409322107537
---

<Table>
  <tbody>
    <tr>
      <td>
        **最新动态**
      </td>
      <td>
        对于点击后跳转到Google Play Store的Meta ads广告，您可以使用Install Referrer获取其原始数据。
      </td>
    </tr>
    <tr>
      <td>
        **更新内容**

        **![Information_icon.png](https://files.readme.io/cc1ff74668360a2be64ec90db8f771d751b0a95847ecaee582c2e31c60e310cf-20445036062993.png)**
      </td>
      <td>
        在2021年10月29日**之后**，Meta ads不再向广告主开放其流量的用户级别归因数据（即原始数据），但Meta ads仍会向AppsFlyer等MMP开放此类数据。

        但如果用户点击广告后跳转到Google Play Store，广告主就可以获取Google Install Referrer中的归因字段，前提是<Anchor target="_blank" href="/marketers/zh/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">应用中已接入Referrer</Anchor>。AppsFlyer会用Referrer中的字段填充原始数据报告并呈现给广告主，同时使用该数据对没有设备ID（即启用了LAT）的用户进行归因。

        如需使用Referrer机制，必须接入AppsFlyer SDK V5.4+

        **请注意：** Referrer数据的优先级高于API数据，且不受限。

        Referrer中的数据是由Meta ads加密的，可以通过您Meta ads开发者账户中的密钥解密。您需要向AppsFlyer提交该密钥，具体步骤请见下文说明。

        **由Referrer提供的广告系列归因字段如下：**

        * 即相关广告的ID
        * Ad name（广告名称）
        * Adset ID（广告组ID）
        * Adset name（广告组名称）
        * Campaign ID（广告系列ID）
        * Campaign name（广告系列名称）
        * Account ID（账户ID）
        * 流量入口（Channel）
        * Ad type（广告类型，该字段尚未上线）

        **请注意**：

        * 除上述字段外，Referrer中再无其他可用字段。
        * 该解决方案适用于点击型归因，不适用于浏览型归因。
        * Referrer数据不适用于拉活广告（用户点击广告后直接打开应用），因为在拉活场景下用户不会进入应用商店。

        **AppsFlyer何时做出相应的更新？**

        * 自2021年10月29日起：
          * Meta ads点击数据（即归因原始数据）受限。
          * 广告主可以在AppsFlyer后台更新相关的Referrer解密密钥。
        * 自2021年11月3日起：
          * AppsFlyer使用Referrer机制填充原始数据并进行归因。
      </td>
    </tr>
    <tr>
      <td>
        **数据可用性总结**
      </td>
      <td>
        <table><tbody><tr><th rowspan="2">归因类型</th><th rowspan="2">归因数据来源</th><th colspan="2">广告主的数据可用性 </th><th>说明</th></tr><tr><th>原始数据</th><th>汇总数据</th><th> </th></tr><tr><td>点击型归因</td><td>Referrer（适用于从Google Play Store下载的安卓应用）</td><td>可用</td><td>可用</td><td><ul><li>LAT用户的归因数据可用。</li><li>如果Referrer数据和MMP数据都可用，Referrer数据的优先级更高。</li><li>不适用于拉活广告。</li></ul></td></tr><tr><td>点击型归因</td><td>MMP API</td><td>受限\*</td><td>可用</td><td> </td></tr><tr><td>浏览型归因</td><td>MMP API</td><td>受限\*</td><td>可用</td><td>不支持Referrer机制。</td></tr><tr><td colspan="5"><p><strong>请注意：</strong>注意：数据可用性受限时：</p><ul><li><ul><li>激活和应用内事件的回传仅发送到实施限制的广告平台。数据分析平台等第三方合作伙伴不会收到受限归因的回传。 </li><li>未归因（即不含归因字段）的回传会发送到接收所有事件（包括自然量和未归因量）的广告平台，这些平台包括Meta广告投放管理合作平台。</li></ul></li></ul></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        **亟需处理**
      </td>
      <td>
        **请按以下步骤获取Meta ads账户中的解密密钥：**

        【以下信息由Facebook提供，由AppsFlyer整理】

        1. 登录Meta开发者平台。
        2. 进入右上角的**My Apps**板块。
        3. 选择相关应用，获取其解密密钥。
        4. 从页面左侧进入**Settings** > **Basic**。

           [![FBUIforKey.png](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)
        5. 向下滚动至**Android**板块，您就会在**Package Names**字段下的**Install Referrer decryption key**中看到您的解密密钥。**请注意**： 这个板块就是您之前配置包名和Google Play Store的地方。

        **请按以下步骤在AppsFlyer后台启用Referrer机制：**

        1. 【必须完成】确认您应用中接入的AppsFlyer SDK是V5.4或以上版本。切勿使用之前的版本。
        2. 完成以下任一操作：
           1. 【即将上线】通过API设置解密密钥。
           2. 在面板中设置解密密钥：
              1. 从AppsFlyer后台进入**配置** > **活跃对接**。
              2. 选择Meta ads。  

                 ![meta-ads-install-referrer-decryption-key.png](https://files.readme.io/adf6caa8d7cee493695eb8fb7db1b61c60e6a1cef0273e615c43a05ad8a9485d-13963525463825.png)
           3. 进入**对接**选项卡，将密钥粘贴到**Install Referrer** **Decription Key**字段框中。
           4. 点击**保存对接**。
      </td>
    </tr>
    <tr>
      <td>
        **通过API更新解密密钥**
      </td>
      <td>
        **【即将上线】**

        我们将推出一个用于更新解密密钥（decryption key）的API。
      </td>
    </tr>
    <tr>
      <td>
        **未来的原始数据可用性**
      </td>
      <td>
        * 通过Referrer机制获取的归因数据在原始数据报告中不受限。
        * 对于通过API获取的归因数据，Meta ads流量的原始数据会归到*受限*媒体渠道下。
        * 这一更新对UTC时间2021年10月29日08:00之前产生的历史原始数据没有影响。
      </td>
    </tr>
    <tr>
      <td>
        **保留内容**
      </td>
      <td>
        AppsFlyer仍会从Meta ads接收设备层级的数据，也就是说我们的归因和报告功能（包括包括多触点归因、LTV、ROI、群组、留存报告、防作弊、受众共享等解决方案）不受影响。详情请见<Anchor target="_blank" href="/marketers/zh/docs/aggregated-and-analytics-reporting-overview">汇总与分析报告工具</Anchor>。

        **请注意**：注意：如果您向AppsFlyer提供了解密密钥，我们就能对没有设备ID（即启用了LAT）的用户进行归因，从而提高归因准确性。
      </td>
    </tr>
    <tr>
      <td>
        **归因变更**
      </td>
      <td>
        GCD延迟深度链接将支持使用Google Install Referrer机制的安卓应用，但这种方式不适用于iOS应用。
      </td>
    </tr>
    <tr>
      <td>
        **常见问题解答**
      </td>
      <td>
        * **Install Referrer解密密钥是否需要更新？**  
          解密密钥一经提交便无需更新。
        * **什么情况下可以在原始数据报告中看到用户级别数据？**  
          当您提交了有效的Install Referrer解密密钥，且有激活归因到Meta ads时，您就可以看到这些激活的用户级别数据。
        * **对于在2021年10月29日到2021年11月3日之间发生的激活，其用户级别归因数据是否可用？**  
          该数据不可用。
      </td>
    </tr>
  </tbody>
</Table>
