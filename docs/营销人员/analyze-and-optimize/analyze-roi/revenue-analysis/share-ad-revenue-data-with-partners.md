---
title: 与UA渠道共享广告收入数据
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-04-11T11:04:45Z'
  edited_at: '2026-10-14T10:03:34Z'
  id: 24100803679761
  locale: zh-cn
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/zh-cn/articles/24100803679761
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 允许UA渠道接收来自聚合平台的广告收入信息，以优化他们的获客活动。**请注意**：需要购买ROI360 Advanced进阶功能。

<div id="about-sharing-ad-revenue-data-with-partners" />

## 与UA渠道共享广告收入数据

您可以授权负责用户获取（UA）的广告平台从聚合平台获取广告收入数据。UA渠道可据此优化其广告投放活动，实现更高效的转化和更高回报。

UA合作渠道可通过以下两种方式接收广告收入数据：

* [广告平台的UA信号](/docs/share-ad-revenue-data-with-partners#ua-signals-for-ad-networks)
* [广告平台的广告收入回传](/docs/share-ad-revenue-data-with-partners#ad-revenue-event-postbacks-for-ad-networks)

下表将对这两种广告收入数据共享方式进行了对比：

| 广告收入数据共享解决方案 | 数据时效性 | 使用场景 | 所需的对接类型 | 所需的订阅类型 |
| --- | --- | --- | --- | --- |
| UA信号 | 每日更新 | 准确完整的数据，通常用于D3和D7优化。 | <ul><li>展示级或设备级</li><li>如果两者都已配置，则会发送设备级数据</li></ul> | ROI360 高级 |
| 数据回传 | 实时 | 最新数据，通常用于D0和D1优化。 | 展示级 | ROI360 高级 |

<div id="procedures" />

## 配置流程

<div id="ua-signals-for-ad-networks" />

<Accordion title="广告平台的UA（拉新）信号">

有些广告平台可以接收到UA信号，建议广告主首选与这类平台合作。也就是说，UA平台可以从聚合平台接收广告收入数据，并使用这些数据来优化广告主的获客投放。

**请按以下方式向广告平台发送UA signals**：

1. 从AppsFlyer的侧边栏中选择**协作** > **活跃对接**。
2. 选择相关的对接渠道。
3. 进入**对接**选项卡。
4. 确认**启用该渠道**开关已开启。如果未开启，数据就不会被共享。
5. 进入**Permissions**选项卡。
6. 打开**广告平台权限**开关。
7. 打开<strong>访问广告收入原始数据（UA signals）</strong>开关。
8. **发送选项**部分有两种发送方式可选：若选择**仅该合作渠道**，则仅发送该渠道带来的广告收入数据；若选择**所有媒体渠道，包括自然流量**，则发送来自所有媒体渠道的广告收入。**请注意**：选择“所有媒体渠道，包括自然流量”时，归因到其他渠道的事件中不包含归因数据。
9. 点击**保存设置**。
10. 联系相关广告平台：
    1. 告知相关人员您已授予该平台必要权限。
    2. 让相关人员按照<Anchor target="_blank" href="/partners/zh/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">这些说明</Anchor>进行操作，以便接收报告。

**可向UA平台发送UA signals的聚合平台包括：**

* Applovin Max
* Google Admob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Unity LevelPlay聚合平台（前身为ironSource）
* Admost
* Tradplusad
* Yandex
* Custom Mediation

</Accordion>

<div id="ad-revenue-event-postbacks-for-ad-networks" />

<Accordion title="广告平台的广告收入事件回传">

您可以配置广告平台的广告收入回传。也就是说，拉新平台可以接收到聚合平台的实时广告收入数据，并使用这些数据来优化广告主的拉新投放。

<div id="important" />

> 🚧 **重要提示！**
>
> * 仅可通过展示级别的SDK对接和设备级别的S2S API<Anchor target="_blank" href="/marketers/zh/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">对接</Anchor>向广告平台发送广告收入事件回传。请让您的开发人员在相关应用中接入<Anchor target="_blank" href="/marketers/zh/docs/integrate-the-roi360-ad-revenue-sdk-api">AppsFlyer的广告收入SDK API</Anchor>。
> * 您可以向具体渠道发送广告收入回传，但在启用广告收入回传之前，请先确认该渠道对相关数据的使用方式符合政策规定。

**请按以下方式设置广告收入事件回传**：

1. 搜索并选择相关渠道，可以从<Anchor target="_blank" href="/marketers/zh/docs/partner-integrations#管理现有对接">Marketplace渠道平台</Anchor>或进入**协作** > **活跃对接**页面。
2. 在**渠道对接**选项卡中，向下滚动到**应用内事件回传**，打开此开关。
3. 在“AppsFlyer事件”列表中选择af\_ad\_revenue。**请注意**：部分广告平台对接提供**全选所有事件**的选项。请勿使用此选项，否则af\_ad\_revenue事件会被排除在外。
4. 将该事件映射到相关UA广告平台中的对应事件，具体如下：

| UA广告平台 | af\_ad\_revenue的渠道映射事件 | 截屏 |
| --- | --- | --- |
| ironSource | adRevenue | [![](https://files.readme.io/c7e01c7c83a955fca0479d3b5f9ab3c781d0ecdf3cfaf2757e861013eb39f149-51911214455953.png)](https://files.readme.io/c7e01c7c83a955fca0479d3b5f9ab3c781d0ecdf3cfaf2757e861013eb39f149-51911214455953.png) |
| Unity Ads | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Moloco | 无需映射 |  |
| Mintegral | 无需映射 |  |
| Smadex | 无需映射 |  |
| Mistplay | 无需映射 |  |
| Meta Ads | fb\_mobile\_purchase—for iOS apps  <br />或  <br />Adimpression—for Android apps  <br />如需了解详情，请参阅<Anchor target="_blank" href="/marketers/zh/docs/meta-ads-in-app-event-mapping#mapping-ad-revenue-data-for-campaign-optimization">此文档</Anchor>。 | [<Image alt="revenue-mapping-meta2.jpg" src="https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg" width="230px" />](https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg) |
| TikTok For Business - 高级SRN | ImpressionLevelAdRevenue | [![](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png)](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png) |
| Aura from Unity | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Digital Turbine的SingleTap | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Persona.ly RTB | ad-revenue | [![](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png)](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png) |
| Bigo | ad\_watch | [![](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png)](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png) |
| Appier | 无需映射 |  |
| Bidease | 无需映射 |  |
| MAF | 无需映射 |  |

5. 为事件选择一个**发送选项**的用户：
   * **仅该合作渠道**：仅回传归因到该渠道的事件，也就是说完成这些事件的用户来自该渠道。
   * **所有媒体渠道，包括自然流量**：回传归因到任何渠道以及自然量的事件，也就是说完成这些事件的用户来自各个渠道。**请注意**：选择“所有媒体渠道，包括自然流量”时，对于归因到其他渠道的事件，其回传中不包含归因数据。
6. 点击**保存对接**。

**可向UA平台发送展示级别广告收入事件的聚合平台包括：**

* Applovin Max
* Google Admob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* ironSource
* Admost
* Tradplusad
* Yandex
* Custom mediation

</Accordion>

<div id="additional-information" />

## 其他相关信息

<div id="list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks" />

<Accordion title="可收到UA信号和回传的UA平台列表：">

下表列出了可以接收聚合平台广告收入UA信号和回传的广告平台。

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th rowspan="2">广告平台（合作伙伴）</th><th colspan="2">支持</th></tr><tr><th>UA信号</th><th>数据回传</th></tr></thead><tbody><tr><td>Aarki</td><td>-</td><td><span>✓</span></td></tr><tr><td>AdAction</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adaction3</td><td>-</td><td><span>✓</span></td></tr><tr><td>Adamobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adikteev (Trademob)</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adjoe</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Adonco</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adshow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Almedia GmbH</td><td>-</td><td><span>✓</span></td></tr><tr><td>Appgrowth</td><td>-</td><td><span>✓</span></td></tr><tr><td>Appier</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Apprainbow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Aura from Unity</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Avow OEM</td><td> </td><td><span>✓</span></td></tr><tr><td>ayeT-Studios</td><td>-</td><td><span>✓</span></td></tr><tr><td>Betop</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidswave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidease</td><td>-</td><td><span>✓</span></td></tr><tr><td>Bigo</td><td>-</td><td><span>✓</span></td></tr><tr><td>Brandscale</td><td><span>✓</span></td><td>-</td></tr><tr><td>Buzzvil</td><td>-</td><td><span>✓</span></td></tr><tr><td>Chameleostudios</td><td><span>✓</span></td><td>-</td></tr><tr><td>Chartboost</td><td><span>✓</span></td><td>-</td></tr><tr><td>Churney</td><td>-</td><td><span>✓</span></td></tr><tr><td>Datawave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Digital Turbine</td><td>-</td><td><span>✓</span></td></tr><tr><td>DLab</td><td><span>✓</span></td><td>-</td></tr><tr><td>Ecomonline</td><td><span>✓</span></td><td>-</td></tr><tr><td>Etusdigital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Exmox</td><td>-</td><td><span>✓</span></td></tr><tr><td>Fluent</td><td><span>✓</span></td><td>-</td></tr><tr><td>Foregon</td><td><span>✓</span></td><td>-</td></tr><tr><td>GNA Company</td><td><span>✓</span></td><td>-</td></tr><tr><td>Greedygame</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Happimobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Hybrid</td><td><span>✓</span></td><td>-</td></tr><tr><td>Inflecto</td><td><span>✓</span></td><td>-</td></tr><tr><td>Irismedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>ironSource</td><td>-</td><td><span>✓</span></td></tr><tr><td>Kashkick</td><td>-</td><td><span>✓</span></td></tr><tr><td>Kwai ads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Lacuna</td><td>-</td><td><span>✓</span></td></tr><tr><td>Lambadapp</td><td><span>✓</span></td><td>-</td></tr><tr><td>Leadidadmonster</td><td><span>✓</span></td><td>-</td></tr><tr><td>Lifestreet</td><td><span>✓</span></td><td>-</td></tr><tr><td>Liftoff</td><td><span>✓</span></td><td>-</td></tr><tr><td>MAF</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Melodong</td><td><span>✓</span></td><td>-</td></tr><tr><td>Meta Ads</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Miniclip</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mintegral</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mistplay</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Mobrand</td><td><span>✓</span></td><td>-</td></tr><tr><td>Moloco</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Motive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Mpnd</td><td><span>✓</span></td><td>-</td></tr><tr><td>Msla</td><td><span>✓</span></td><td>-</td></tr><tr><td>Muvmobile</td><td><span>✓</span></td><td>-</td></tr><tr><td>NewsBreak</td><td>-</td><td><span>✓</span></td></tr><tr><td>Nexamob</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nftdroper</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nsofmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>Performadlive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Persona.ly RTB</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Pitatroas</td><td><span>✓</span></td><td>-</td></tr><tr><td>Playgap</td><td>-</td><td><span>✓</span></td></tr><tr><td>Rebornads</td><td><span>✓</span></td><td>-</td></tr><tr><td>RTBhouse</td><td><span>✓</span></td><td>-</td></tr><tr><td>Runfuns</td><td><span>✓</span></td><td>-</td></tr><tr><td>SayGames LTD</td><td>-</td><td><span>✓</span></td></tr><tr><td>Scmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shalltry</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shareit</td><td><span>✓</span></td><td>-</td></tr><tr><td>Digital Turbine的SingleTap</td><td>-</td><td><span>✓</span></td></tr><tr><td>Smadex</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Surgex</td><td>-</td><td><span>✓</span></td></tr><tr><td>Tapjoy</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Targetmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>TaurusX</td><td>-</td><td><span>✓</span></td></tr><tr><td>Thepurpleline</td><td><span>✓</span></td><td>-</td></tr><tr><td>TikTok for Business</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Trade Desk</td><td> </td><td><span>✓</span></td></tr><tr><td>Transsion</td><td>-</td><td><span>✓</span></td></tr><tr><td>Truemoney</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tyrads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Unity Ads</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Unity CTV</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Voodoo</td><td>-</td><td><span>✓</span></td></tr><tr><td>Vungle</td><td><span>✓</span></td><td>-</td></tr><tr><td>VYBS</td><td>-</td><td><span>✓</span></td></tr><tr><td>Yandex</td><td><span>✓</span></td><td>-</td></tr><tr><td>Yeahmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>YouAppi</td><td>-</td><td><span>✓</span></td></tr><tr><td>Xiaomi Global</td><td>-</td><td><span>✓</span></td></tr><tr><td>YSO Network</td><td>-</td><td><span>✓</span></td></tr><tr><td>Z2A Digital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Zoyo</td><td><span>✓</span></td><td>-</td></tr></tbody></table>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 转化类型 | <ul><li>UA信号支持所有转化类型的数据，包括激活、再归因、再互动和重装激活。</li><li>回传仅支持激活相关的数据。</li></ul> |
| 代商回传权限 | 代理无法配置广告收入回传 |

</Accordion>

<div data-zendesk-anchors="about-sharing-ad-revenue-data-with-ua-partners=%E4%B8%8Eua%E6%B8%A0%E9%81%93%E5%85%B1%E4%BA%AB%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE h_01HV6CW4SAF23TT5XZF1SGPVQH=%E4%B8%8Eua%E6%B8%A0%E9%81%93%E5%85%B1%E4%BA%AB%E5%B9%BF%E5%91%8A%E6%94%B6%E5%85%A5%E6%95%B0%E6%8D%AE procedures=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B h_01HVEEMGMEWDKAXVNHR8C0AHPQ=%E9%85%8D%E7%BD%AE%E6%B5%81%E7%A8%8B 01H8V10BKM7MMM63JHGCF2DYMC=ua-signals-for-ad-networks 01H8V10BKMED8J73G22CFVH6GJ=ad-revenue-event-postbacks-for-ad-networks h_01HFAAC1J9KQ6ZNSCRSRKE9GA3=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA additional-information=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HVE6AREZBPH751WFW70Q7X66=%E5%85%B6%E4%BB%96%E7%9B%B8%E5%85%B3%E4%BF%A1%E6%81%AF h_01HVE6AREZBCAJPVYSF43JWNJZ=list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks h_01HTM0KJA8TB44TSV5N2151N4N=traits-and-limitations" />
