---
title: 受众共享渠道连接
metadata:
  keywords:
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-10-05T06:49:59Z'
  edited_at: '2026-10-14T10:10:20Z'
  id: 360013960577
  locale: zh-cn
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/zh-cn/articles/360013960577
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：**  与合作渠道共享受众。

<div id="about-partner-connections" />

## 渠道连接简介

您可以通过渠道连接快捷且持续地向您的合作渠道发送人群包，用于相关广告的定向投放。下文表格中列出了支持受众共享的渠道及其人群包连接要求和适用的用户标识符。

**如需将您的人群包连接到某个渠道，请先通过下表确认该渠道是否支持受众共享，然后按以下方式操作：**

* 如果表格中提供了该渠道的专用说明链接，请点击该链接，然后根据文档中的说明进行操作。  
  **--或者--**
* 如果表格中列出了必须填写的证书信息：
  1. 请从渠道侧获取相应的证书信息。
  2. 按照<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#create-a-new-connection">相关说明</Anchor>在受众共享面板中创建新的渠道连接。

**请注意：** 建议每个人群包关联的渠道数量最好不要超过50个。

| 适用渠道 |  | 连接要求 | 适用标识符 |
| --- | --- | --- | --- |
| Aarki | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/aarki.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li><li>IMEI（哈希）</li><li>OAID（哈希）</li><li>IDFV（哈希）</li><li>CUID（哈希）</li><li>电子邮件（哈希加密）</li><li>电话号码（哈希加密）</li><li>Braze external user ID</li></ul> |
| Accesstrade Vietnam | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/accesstradevn.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| AdAction Brazil | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adactionbr.png?v=1&" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| AdPacker | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adpacker.png?v=1" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| AdPiece | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adpiece.png?v=1" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Adikteev | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/trademob.png?v=1" width="71px" /> | API用户名、API密码、Company ID | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| AdiSON Offerwall | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adisonofferwall.png?v=1" width="111px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Adjoe | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adjoe.png?v=1" width="111px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Admile | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/admile.png" width="151px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Admuxer | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/admuxer.png" width="151px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Adobe Audience Manager | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adobemc.png" width="60px" /> | **请注意：** 目前尚不支持创建新的Adobe连接。<br /><br />[Adobe Audience Manager](/docs/audiences-partner-connections#adobe-audience-manager-aam)连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| ADSJOY | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adsjoy.png?v=1" width="98px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| AdTiming | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adtiming.png?v=1" width="98px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Advolt | <Image alt="Advolt.jpg" src="https://files.readme.io/78f1eb00caacd45ec85aa24eecf48ad5bc18fa7b1d28fc6d2a4342b9f5f14f7d-31237653514129.jpg" width="122px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| 亲和力 | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/affinity.png" width="70px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Affle | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/affle.png" width="70px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Amazon S3 | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/AmazonS3.png" width="128px" /> | [Amazon S3](/docs/audiences-partner-connections#amazon-s3)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li><li>IMEI（哈希）</li><li>OAID（哈希）</li><li>IDFV（哈希）</li><li>CUID（哈希）</li><li>电子邮件（哈希加密）</li><li>电话号码（哈希加密）</li></ul> |
| Appgrowth | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appgrowth.png?v=1" width="104px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| AnyMind | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/anymindgroup.png?v=1" width="104px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Appier | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appier.png?v=1" width="104px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Applabs | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/applabs.png?v=1" width="104px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Appluton | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appluton.png" width="112px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Appnext | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appnext.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Appreciate | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appreciate.png" width="128px" /> | Buyer ID、API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Arrivemoovit |  | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Autumnant | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/autumnant.png?v=1" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Beintoo | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/beintoo.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Betop | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/betop.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Bidease | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/bidease.png" width="81px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Bigabid | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/bigabid.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Bigo Ads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/bigoads.png?v=1" width="106px" /> | 登入Bigo Ads进行身份验证 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Braze | <Image alt="Braze logo Nov 2023.jpg" src="https://files.readme.io/c84c2459ec87a3c3fef83e573ff4d43e45df8604223d53aaa989ad410d372d54-31237648110737.jpg" width="107px" /> | [Braze](/docs/audiences-partner-connections#braze)的连接说明 | <ul><li>Braze external user ID</li></ul> |
| c2c\_audience | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/click2commission.png" width="123px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Cecom | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/cecom.png?v=1" width="123px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Cherryonly | ![cherryonl4f (1).png](https://files.readme.io/ad4e693ada777a79cbcadc668a67c03272547e0641d3312349392a9ea34ffe64-35884799991185.png) | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Chartboost | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/chartboost.png?v=1" width="123px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Collectcent | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/collectcent.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| CRED | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/cred.png" width="62px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Criteo | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/criteo.png" width="128px" /> | [Criteo](/docs/audiences-partner-connections#criteo)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li><li>电子邮件（哈希加密）</li></ul> |
| Daangn | <Image alt="danggeunmx8 (1).png" src="https://files.readme.io/97d8be9cdb9f4f82efdd6ccf735c5a6f195f4d10868d107c6b29bfbe99880cbb-34192650411665.png" width="92px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Dataseat | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/dataseat.png?v=1" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| DemandScale | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/siftco.png?v=1" width="64px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Downstream | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/downstreamai.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Edge226 | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/edge226.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Facebook | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/facebook.png" width="128px" /> | [Facebook](/docs/audiences-partner-connections#facebook)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li><li>电子邮件（哈希加密）</li><li>电话号码（哈希加密）</li></ul> |
| Filexmedia | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/filexmedia.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Freecash | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/freecash.png" width="71px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Gamelight | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/thespotlight.png" width="71px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| GetLoyal | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/getloyal.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Glance | <Image alt="Screen_Shot_2022-08-02_at_10.26.22.png" src="https://files.readme.io/32870ef5ab9e2714b7cae55d87c843b7a39116c1b2c020b869b2595fcb256635-31237648111633.png" width="114px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Google Ads<br /><br />\*\*请联系您的CSM或发送邮件至[hello@appsflyer.com](mailto:hello@appsflyer.com)，确认您的账户是否可以使用Google Ads的受众共享对接。 | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png" width="67px" /> | [Google Ads](/docs/audiences-partner-connections#google-ads)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Growone |  | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Hippoad | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hippoad.png?v=1" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Httpool | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/httpool.png" width="128px" /> | [Httpool](/docs/audiences-partner-connections#httpool)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Hybrid | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hybrid.png?v=1" width="96px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| iCubesWire | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/icubes.png?v=1" width="96px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Indus App Bazaar（Samsung Galaxy Store） | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/samsunggalaxystoreindusappbazaar.png?v=1" width="96px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| InMobi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/inmobi.png" width="128px" /> | Property ID | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Insider | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/useinsider.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Intentaiii5 | ![](https://cdn.appsflyer.com/marketplace/static/logo/intentaiii5.png) | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| ironSource | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ironsource.png" width="128px" /> | ironSource user ID、API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Jampp | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jampp.png" width="128px" /> | Client ID、Client secret、App ID | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| JioAds | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jioads.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Join Ship Tech Limited | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/joinship.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Kakao | <Image alt="Kakao_Logo_Primary_Screen_V1.0.png" src="https://files.readme.io/62df88fab5301c8c6d0fc31b94456a79ea73c5195f37332ddd144e1259c9f9f4-37842576339729.png" width="116px" /> | [Kakao](/docs/audiences-partner-connections#Kakao)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| KashKick | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/kashkick.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Kaden | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/kaden.png?v=1" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Kayzen | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/dataliftretargeting.png" width="60px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Kwai for business（快手出海平台） | <Image alt="Kwai_for_business_2.jpg" src="https://files.readme.io/0dece6ec834ff75ad53aae0932c873e9bb85ed9c42acdf5c84a896b7f50bccbc-31237648112913.jpg" width="53px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Leanplum | ![](https://cdn.appsflyer.com/marketplace/static/logo/leanplum.png?v=1) | [Leanplum](/docs/audiences-partner-connections#leanplum)的连接说明 | <ul><li>CUID（哈希）</li></ul> |
| learnshapwm |  | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Lemmonet | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/lemmonet.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| LessMobi |  | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Lifestreet | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/lifestreet.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Liftoff | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/liftoff.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| LinkedBro | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/digmobiteqp.png" width="86px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| 管理方式  <br />（由Criteo收购） | ![manage_logo.png](https://files.readme.io/0855ecfbf1c026fdedddbedeff95c4b3cbf3663d7cf1e224b6c3e92d35bb1705-31237653520145.png) | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| mDSP | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mdsp.png" width="128px" /> | Organization ID | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| MediaSmart | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mediasmart.png" width="128px" /> | Organization ID | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Mediasurfer | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mediasurfer.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| MinoAds | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/minoads.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| mInsights  <br />（GroupM） | ![m_insights_blue.png](https://files.readme.io/0ae9dd57d9692987ce3a6ebd09d9c09c1bd41e3cfe5846dbe8e0e09f83384ebe-31237653520913.png) | Access key ID、Secret access key、path | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Mintegral | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mintegral.png" width="128px" /> | API key、App ID | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Mistplay | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mistplay.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Mobavenue | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobavenue.png?v=1" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Mobisummer（Tec-Do） | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobisummer.png" width="103px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Moboost | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/moboostlt.png" width="103px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Mobusi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobusi.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Mobvista | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobvista.png" width="128px" /> | Advertiser ID、API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| MobWonder | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobwonder.png?v=1" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| MobYoung | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobyoung.png?v=1" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| MoEngage | ![moengage_logo.png](https://files.readme.io/a1557a6521ad6c94d5972a08f540a40cc4ec53137eabe3b1848c3696ec7a9c5f-31237648114833.png) | [MoEngage](/docs/audiences-partner-connections#moengage)的连接说明 | <ul><li>CUID（哈希）</li></ul> |
| Moloco | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/moloco.png" width="128px" /> | API key<br /><br />**请注意：** 这是AppsFlyer受众共享对接专用的API Key。请咨询您的Moloco客户经理，获取该密钥信息。 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| MoPub Acquire | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/crossinstall.png" width="60px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| myTarget | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mail.ru.png" width="87px" /> | [MyTarget](/docs/audiences-partner-connections#mytarget)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| NAVER | <Image alt="Naver_Logotype.svg.png" src="https://files.readme.io/d236f0f4e89b68c3b4d6c085674cd2c98e397358f5e29f0f4de72b88fe3d1b12-33356334901905.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Olimob | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/olimob.png" width="95px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Opera Mobile | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/operamobile.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Oracle | <Image alt="oracle.png" src="https://files.readme.io/c983f213b498b82cf51a73d0e69fb74bf9bddf50d599c45756c88dae87a6567d-51911738711313.png" width="128px" /> | [Oracle](/docs/audiences-partner-connections#oracle-data-cloud)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Paytunes | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/paytunes.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| PerformanPBI | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/performanpbi.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Personaly | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/persona.ly.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Petal Ads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/huaweiadsglobal.png?v=1" width="100px" /> | 电话/邮箱/登录ID、密码、华为广告账号 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Pulsedrived | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/pulsedrivqw.png" width="100px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| PushSpring | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/pushspring.png" width="128px" /> | [PushSpring](/docs/audiences-partner-connections#pushspring)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Pushwoosh | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/pushwoosh.png" width="52px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Radian | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/radianl5.png" width="52px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Recomob | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/recomob.png" width="111px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Remerge | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/remerge.png" width="128px" /> | Access key ID、Secret access key、Path | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| RevX | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/revx.png?v=1" width="102px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| RTBHouse | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/rtbhouse.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| SHAREit | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/shareit.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Shenzhen Fumao Technology Co.（Szfumaokeji） |  | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Sidetinads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/sidetinads.png" width="96px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Singumedia | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/singumediqv.png" width="96px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Slack | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/slack.png" width="104px" /> | [Slack](/docs/audiences-partner-connections#slack)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li><li>IMEI（哈希）</li><li>OAID（哈希）</li><li>IDFV（哈希）</li><li>CUID（哈希）</li><li>电子邮件（哈希加密）</li><li>电话号码（哈希加密）</li></ul> |
| Smadex | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/smadex.png" width="85px" /> | Smadex登录信息 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Snakzy by Eneba | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/helisplaynnf.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Snapchat | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/snapchat.png" width="60px" /> | [Snapchat](/docs/audiences-partner-connections#snapchat)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li><li>电子邮件（哈希加密）</li><li>电话号码（哈希加密）</li></ul> |
| Spotad | ![](https://cdn.appsflyer.com/marketplace/static/logo/spotad.png) | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| StackAdapt | ![](https://cdn.appsflyer.com/marketplace/static/logo/stackadapt.png) | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| StartApp | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/startapp.png" width="128px" /> | API令牌 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Superads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/superads.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Taboola | ![](https://cdn.appsflyer.com/marketplace/static/logo/taboola.png?v=1) | 登入Taboola进行身份验证 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Tapjoy | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tapjoy.png" width="128px" /> | [Tapjoy](/docs/audiences-partner-connections#tapjoy)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| TaurusX | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/taurus.png?v=1" width="85px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| 腾讯 | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tencent.png?v=1" width="128px" /> | 登入腾讯进行身份验证 | <ul><li>IDFA（哈希加密）</li><li>IMEI（哈希）</li><li>OAID（哈希）</li><li>电话号码（哈希加密）</li></ul> |
| TheTradeDesk | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/thetradedesk.png" width="128px" /> | Advertiser ID、Secret key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| TikTok For Business（字节跳动） | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/bytedanceglobal.png" width="128px" /> | [TikTok For Business](/docs/audiences-partner-connections#tiktok-for-business)的连接说明 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li><li>IMEI（哈希）</li><li>OAID（哈希）</li></ul> |
| Toponad | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/toponad.png" width="87px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Truecaller | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/truecaller.png?v=1?" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Tyrads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tyradscpl.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Unicorn DSP | ![Unicorndsp.jpg](https://files.readme.io/4f5917f0e15a37b1767aab744633e326e9cceefcb7cb3cd40fc1f8e0718f77cc-31237653524113.jpg) | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| 优普利沃 | ![](https://cdn.appsflyer.com/marketplace/static/logo/uplivo2wj.png) | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Upsflyer | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/upsflyer.png?v=1?" width="124px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| VastMedia | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/vastmedia.png?v=1?" width="94px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Vidma recorder | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/vidmarecorder.png?v=1?" width="63px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Vivo | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/vivoglobal.png" width="100px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Vizury | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/revx.png" width="100px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Vserv | ![Vserv.jpg](https://files.readme.io/6984558eed14f4137907b8ef8b4064dd415ed28dce3d0451279bc2a304cc00b4-31237653525137.jpg) | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| VYBS | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/vybsafl.png" width="111px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Wider Planet | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/widerplanet.png" width="111px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| WingsApps | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/wingsapps.png?v=1" width="111px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Xapads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/xapads.png?v=1" width="111px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Xysea | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/xysea.png" width="111px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Yahoo!Gemini | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yahoogemini.png" width="128px" /> | Yahoo登录信息 | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li><li>电子邮件（哈希加密）</li></ul> |
| Yeahmobi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yeahmobi.png" width="128px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| YouAppi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/youappi.png" width="118px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |
| Zoomd DSP | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zoomd.png" width="118px" /> | API key | <ul><li>IDFA（哈希加密）</li><li>GAID（哈希加密）</li></ul> |

<div id="we-love-working-with-new-audiences-partners" />

> 📘 **除了上述渠道之外，AppsFlyer也竭诚欢迎其他渠道加入受众共享对接。**
>
> 如果您需要的渠道不在上述列表中，请随时联系您的CSM。我们会与这些渠道沟通相关事宜，确认可用方案。

<div id="adobe-audience-manager-aam" />

<Accordion title="Adobe Audience Manager（AAM）">

AppsFlyer会通过您在AAM中选定的**数据源**（Data Source）创建**用户特征**（Traits）并同步数据。

**请按以下方式将人群包关联到AAM**：

1. 登入[Adobe Marketing Cloud面板](https://bank.demdex.com/portal/login/Logout.ddx)
2. 进入**Manage Data** > **Data Sources**。
3. 在**Data Sources**页面中创建一个新的**Data Source**。

   <Image align="center" alt="" src="https://files.readme.io/4f9e3f508fb70287ba2c605ef9f8099f7151e7530ac3312e752b26130751e428-31237653528593.jpg" />
4. 请按以下方式填写表格：

   * 将**ID Type**设置为Device Advertising ID 。
   * 在“Inbound Data Source”设置部分打开**Customer ID**开关。
5. 点击**Save**。  
   界面会显示**Data Sources**选项。
6. 记录Data Source ID，以备后用。
7. 点击左侧菜单中的**Administration**  > **Groups**。
8. 进入**Permissions**选项卡。

   <Image align="center" alt="" src="https://files.readme.io/b565e39220e13f58ee603ab2874bd4743b30f98f8395d1ad6b79f556b8fe3cd0-31237648132753.png" />
9. 创建一个新的分组。
10. 选择您创建的Data Source。
11. 点击**Save Object** 。
12. 进入**Admin** > **Users**。

    <Image align="center" alt="" src="https://files.readme.io/9167247d30e2aee69c891969e7aa56bbe2095cc8a7dd4bf3896cd563a00cac71-31237648134801.png" />
13. 创建新用户，专供AppsFlyer受众共享使用，并填写必填字段。
14. 在**Assigned Groups**中选择您之前创建的分组。
15. 记录该新建用户的**邮箱**和**密码**。
16. 点击**Save**。
17. 从AppsFlyer后台进入**受众共享**。
18. 选择一个具体的人群包，然后进入**连接**选项卡。
19. 点击 **+添加新连接**。
20. 输入连接名称。
21. 选择**Adobe Marketing Cloud**。  
    界面会显示“连接到Adobe Marketing Cloud”的窗口。
22. 使用您先前记录的证书信息填写相关字段。
23. 点击**保存**。  
    24小时后，您就可以在AAM中的**Analytics** > **Onboarding Status**下看到该人群包的数据。

</Accordion>

<div id="amazon-s3" />

<Accordion title="Amazon S3">

创建S3对接后，AppsFlyer就可以将相关人群包中的设备ID直接发送到您的S3存储桶。发送到S3的文件具有以下特征：

* 文件名：由人群包名称和日期组成，如：my\_audience\_2020-06-23.csv
* 内容：一列设备ID，无表头
* 每天都会新写入一个文件，不会将之前已有的文件删除。
* 发送拆分人群包时，会将按渠道拆分的多个人群包文件压缩在一个ZIP文件里。

**请按以下方式将人群包连接到Amazon S3**：

1. 从AppsFlyer后台进入**受众共享**并选择所需人群包。
2. 点击**连接**选项卡。
3. 点击 **+ 添加新连接**。
4. 输入**连接名称**。
5. 选择 **Amazon S3**。  
   界面会打开**添加连接**的窗口。

   <Image align="center" alt="image__9_.png" src="https://files.readme.io/790f8a50bf14fbb4065d9dcee05e31fa866bc73f236f439ec73f2bc833b31be6-31237653533201.png" />
6. 输入**Cross-account role ARN**（跨账号角色的Amazon资源名称）、**Bucket name**（存储桶名称）以及**Region name**（地区名称）。  
   **请注意：** 建议总是输入Region name（地区名称）。如果AWS中没有默认自动使用地区名称，则必须在此处手动输入，否则无法创建该连接。如需在AWS面板主页中查找地区名称，请点击页面右上方的国家下拉菜单，其中会显示地区选项。<Image alt="region_name.jpg" src="https://files.readme.io/a3b65660a638674cbbe0da2802b4f926929d167d0b528c25c12ded6a90b0e981-31237648137489.jpg" width="355px" />
7. 记录**Account ID**和**External ID**，留待后用。
8. 从**AWS**面板进入**IAM** > **Policies**。
9. 点击**Create Policy**。
10. 点击**JSON**。
11. 将以下代码片段粘贴到JSON窗口中。  

    ```json
    {
    							"Version": "2012-10-17",
    							"Statement": [
    							{
    							"Effect": "Allow",
    							"Action": "s3:*",
    							"Resource": "arn:aws:s3:::BUCKET-NAME/*"
    							}
    							]
    }
    ```
12. 更改**BUCKET-NAME**（存储桶名称）。AppsFlyer会将相关人群包上传到具有该名称的存储桶中。

    <div id="note" />

    > 📘 **注意事项**
    >
    > 存储桶策略中必须仅包含根目录，切勿在路径中加入其他目录，例如像**arn:aws:s3:::BUCKET-NAME/Directory/\***这样的资源是不支持的。如果需要将文件传输到特定目录，请参考第14步的说明。


    如需确保AppsFlyer在您的存储桶中完成必要的数据传输工作，必须配置`PutObject`、`DeleteObject`和`ListBucket`这三个操作。
13. 点击**Review policy**（查看策略）。
14. 输入策略**名称**。
15. 点击**Create policy**（创建策略）。
16. 从AWS面板进入 **Access management** > **Roles**。

    <Image align="center" alt="" src="https://files.readme.io/85a4a81b5ebd131b6b3a20ca6ee136a0d10556363cff2deab96397ec889db141-31237648138513.png" />
17. 点击 **+Create role**（创建角色）。
18. 选择**Another AWS account**，提供您的AWS账号与AppsFlyer AWS账号之间的跨账号权限。

    <Image align="center" alt="" src="https://files.readme.io/1f8db2c84d1cbde4a88fd6d7dace3eb5cb65f8fc9608b0ec568921a2b7c85759-31237653535761.png" />
19. 输入**Account ID**（即您从AppsFlyer面板中复制的Account ID）。
20. 选择**Require external ID** （即您从AppsFlyer面板中复制的External ID）。
21. 当界面提示您从AWS账户中选择一个现有存储桶策略时，请选择您之前创建的策略。
22. 点击新创建的角色名称，打开其属性窗口。

    <Image align="center" alt="" src="https://files.readme.io/9b61cf2c8ec3efd9f6548e1ee6b6ca945dd1160901516f93cd16ac3544d3aade-31237648139793.png" />
23. 记录这个角色的**Role ARN**。
24. 在AppsFlyer S3对接窗口的对应字段内输入该ARN和存储桶名称。

    如果您想要将文件传输到存储桶的特定文件夹中，请提供相关存储桶及其下级文件夹的名称，并以“/”分隔，比如：bucketname/foldername/foldername。

    如果您提供的文件夹名称不存在，AppsFlyer会在上传过程中创建该文件夹。
25. 点击**添加连接**。  
    对接完成且人群包上传完毕后，该存储桶中就会出现含有相关设备ID的CSV文件。

</Accordion>

<div id="braze" />

<Accordion title="Braze">

<div id="prerequisite" />

> 🚧 **前期准备**
>
> 请确保您的应用中已同时接入Braze和AppsFlyer的SDK。
>
> 如需创建指向Braze的传出连接（用于向Braze发送人群包），必须让相关应用中的AppsFlyer SDK将每个用户的Braze External ID发送到AppsFlyer。您可以通过以下任一方式完成该配置：
>
> * Braze External ID参数
> * CUID字段
>
> #### <span id="using-a-braze-external-id-parameter"></span>使用BRAZE EXTERNAL ID参数
>
> 您可以使用AppsFlyer SDK的`setPartnerData`函数将每个用户的Braze External ID发送到AppsFlyer，从而将人群包上传到Braze。用法示例如下：
>
>
> <Tabs>
> <Tab title="Android">
>
> ```java
> Map<String, Object> brazeData = new HashMap<>();
> partnerData.put("external_user_id", "some-braze-external-id-value");
> AppsFlyerLib.getInstance().setPartnerData("braze_int", brazeData);
> ```
>
> </Tab>
>
> <Tab title="iOS">
>
> ```objectivec
> NSDictionary *brazeInfo = @{
> @"external_user_id":@"some-braze-external-id-value"
> };
> [[AppsFlyerLib shared] setPartnerDataWithPartnerId:@"braze_int"
> partnerInfo:brazeInfo];
> ```
>
> </Tab>
> </Tabs>
>

<div id="using-the-cuid-field" />

#### 使用CUID字段

符合以下条件时，无需为Braze External ID配置专用参数：

* 您已将SDK配置为向AppsFlyer发送每个用户的CUID
* CUID的值与Braze External ID一致

**Braze的渠道连接创建方法如下：**

1. 登录到您的Brazez账号，进入**Integrations > Technology Partners**，然后选择AppsFlyer。
2. 在**Data Import Using Cohort Import**部分中，点击**Generate New Key**，生成您的**Data Import Key**。
   * **请注意：** 如果此界面中显示了密钥，则无需在生成新的密钥。
   * <strong>重要提示！</strong>请务必在该页面中的**Data Import Using Cohort Import**部分进行操作（切勿在“install attribution”部分中操作）。

     <Image align="center" alt="data_import_key.png" src="https://files.readme.io/4d288e6696da600d0e402b86a0986b3951f2cd35efd12084aa8feaeeb526fddf-31237653537681.png" />
3. 复制**Data Import Key**和**REST Endpoint** ，之后在AppsFlyer面板中配置连接时会用到这些信息。
4. 从AppsFlyer后台的受众共享面板进入**连接**选项卡，并点击 **+ 添加新连接**。
5. 在“合作伙伴名称”中选择Braze，并为该连接命名。
6. 输入您在第3步中从Braze后台复制的Data Import Key和REST Endpoint。

   <Image align="center" alt="braze_connection.png" src="https://files.readme.io/200d1a1bef906ea50e40b3d8113bb9fd72068b6fda25a2f70b95b4510bd992de-31237653538449.png" />
7. 该连接保存完毕后即可用于任何新建或现存人群包。
8. AppsFlyer侧的人群包上传到Braze后，您就可以在Braze中使用该人群包作为筛选条件，来定义人群分组。

   <Image align="center" alt="cohorts_as_filter.png" src="https://files.readme.io/eec9e014afcb488bb7ebe31167cd5871c38207c8f4542e20ea313b7019e8b43a-31237653538961.png" />

</Accordion>

<div id="criteo" />

<Accordion title="Criteo">

**Criteo的受众共享连接方式如下：**

1. 在Criteo面板中创建一个**API User**。
2. 记录该API User Client ID 和Secret。
3. 从AppsFlyer后台进入**受众共享** > **连接**。
4. 点击 **+ 添加新连接**。
5. 输入**连接名称**。
6. 选择Criteo。

   在相应的字段中输入之前记录的**API User** **Client ID**、**Client Secret**以及您的**Advertiser ID**。
7. 点击**Save**。

**请注意：** 如果相关应用显示为灰色且提示“Already granted”（已授权），因而无法为其创建连接，请前往<Anchor target="_blank" href="https://consent.criteo.com">https://consent.criteo.com</Anchor>，撤销该连接并重试。

</Accordion>

<div id="facebook" />

<Accordion title="Facebook">

**前期准备：**

请确保您在Facebook Business Manager中的角色是管理员或具有投放管理权限的广告主。

**Facebook的受众共享连接方式如下：**

1. 在Facebook上创建一个**广告账号**
2. 从AppsFlyer后台进入**受众共享** > **连接**。
3. 点击 **+ 添加新连接**。
4. 输入**连接名称**。
5. 选择**Facebook**。
6. 点击**登入Facebook**，然后以管理员或广告主的角色登录。
7. 选择所需的**广告账号**。  
   界面会打开“Facebook权限”页面。
8. 请按照Facebook界面中的说明进行操作。
9. 如需修改设置，必须打开**Manage your ads** 开关（默认打开）。
10. 点击**完成**，关闭Facebook界面。
11. 点击**保存**。  
    对接完成且人群包上传完毕后，该人群包就会出现在您的**Facebook Custom Audiences**面板中。

**请注意：** 如果您收到报错，无法在相关广告账户中创建广告，请检查您是否已接受<Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/audiences/reference/custom-audience-terms-of-service/">《Meta自定义受众服务条款》</Anchor>（Meta Custom Audience Terms Of Service）。

</Accordion>

<div id="google-ads" />

<Accordion title="Google Ads">

如需让AppsFlyer向Google Ads发送人群包，请务必完成以下操作。请注意：仅当所有操作都执行完毕后，AppsFlyer才会向Google发送数据。

**注意事项：**

* 您完成该流程后，我们就能将相关人群包关联并上传到Google Ads。但Google Ads侧的数据处理需要6-12小时，然后才会在后台显示该人群列表。
* 目标客户匹配（Google Customer Match）：
  * **支持**：以互动为目标的通用应用广告（Universal App Campaigns for Engagement，简称UACe）
  * **不支持**：  通用应用广告（Universal App Campaigns，简称UAC）

| 需完成的操作 | 说明 | 涉及人员 |
| --- | --- | --- |
| 1 | <ul><li>将人群包关联到您的Google Ads账号。</li><li>前期准备：Google Ads登录证书。</li></ul> | 账号用户或管理员 |
| 2 | 在AppsFlyer后台的受众共享页面中，签署（同意）AppsFlyer针对Google Customer Match的服务条款。 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) |
| 3 | 让Google Ads侧的客户经理为您的Google Ads账户启用<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6379332?hl=en">Customer Match</Anchor>。 | 账户用户 |

**请按以下方式将人群包连接到Google Ads：**

1. 从AppsFlyer后台进入受众共享，然后选择所需人群包。
2. 进入**连接**选项卡。
3. 点击**添加渠道连接**。
4. 输入连接名称。
5. 选择**Google Ads。** 如果界面未显示Google Ads图标，请联系您的CSM，或发送邮件至[hello@appsflyer.com](mailto:hello@appsflyer.com)，让相关团队为您的受众共享开通Google Adwords。
6. 点击<strong>登入Google Ads。</strong>界面会打开**通过Google登录**的窗口。
7. 完成Google登录，并在Google Ads中确认配置。   
   完成后，界面会关闭该窗口。
8. 在AppsFlyer后台**选择一个账号**。
9. 点击<strong>服务条款。</strong>界面会显示相关服务条款。
10. 如果您是管理员：如果您同意这些条款，请点击“**我接受**”。
11. 如果您**不是**管理员：
    1. 点击**继续并稍后查看**。
    2. 让管理员登录并接受条款。按照下文流程完成必要操作。
12. 点击**保存**。  
    保存后即表示Google Ads账户关联已完成。请务必完成下表所列的全部操作，以确保该连接能正常使用。

**如需接受相关条款并启用该连接，须由账户管理员完成以下流程：**

1. 从AppsFlyer后台进入受众共享。
2. 进入**连接**选项卡。   
   界面会显示受众共享渠道列表。
3. 在Google Ads部分中选择一个连接名称。

   <Image align="center" alt="AcceptTermsAudiences_us-en.png" src="https://files.readme.io/511284f2e78963fe872af931c43f91a58295c67446e2cd35b7f148f6c9edbe90-31237648142993.png" />
4. 点击**服务条款**。
5. 查看相关条款，若同意条款内容，请点击**我接受**。
6. 点击**保存更改**。

</Accordion>

<div id="httpool" />

<Accordion title="Httpool">

**Httpool的受众共享连接方式如下：**

1. 从AppsFlyer后台进入**受众共享** > **连接**选项卡。
2. 点击 **+ 添加新连接**。
3. 输入**连接名称**。
4. 选择**Httpool**。
5. 点击**登入Httpool**。  
   界面会显示一个新的时间戳。
6. 点击**Save**。

</Accordion>

<div id="Kakao" />

<Accordion title="Kakao">

**Kakao的受众共享连接方式如下：**

1. 从AppsFlyer后台进入**互动** > **受众共享** > **连接**。
2. 点击 **+ 新连接**
3. 在渠道名称中搜索并选择Kakao。
4. 输入连接名称 (**注意：** 请务必使用新名称，不可与此前创建的合作渠道连接名称重复。
5. 点击**使用Kakao登录**
6. 登录并选择所需的素材和Kakao Moment广告账号。
7. 选择您授权与Kakao共享的用户标识符。
8. 点击**Save**。  
   连接将被添加并显示在**连接**标签中，同时会显示连接状态。

</Accordion>

<div id="leanplum" />

<Accordion title="Leanplum">

<div id="prerequisite-1" />

> 🚧 **前期准备：**
>
> 如需向Leanplum上传人群包，须符合以下条件：
>
> * 必须<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">向AppsFlyer发送每个用户的客户用户ID</Anchor>（Customer User ID，简称CUID）。
> * CUID的值必须与用户的**Leanplum User ID**一致。

**Leanplum的渠道连接创建方法如下：**

1. 从您的Leanplum账户进入**Partner Integrations > AppsFlyer**。在**Audiences**下生成一个新的**Secret**。

   <Image align="center" alt="audiences_leanplum_integration.png" src="https://files.readme.io/fb712c7cecacf6d80bf643f955ecc13d6c878a4db8b6fa5627f814ec659e6615-31237648144145.png" />
2. 选择是否要在Leanplum中为**非现有用户**创建画像。
   * 非现有用户 = 由AppsFlyer受众共享发送的用户ID在 Leanplum中不存在
3. 复制**App ID**和新生成的**Secret**，在AppsFlyer面板中配置相关连接时会用到这些信息。
4. 从AppsFlyer后台的受众共享面板进入**连接**选项卡，并点击**添加新连接**。
5. 在“合作伙伴名称”中选择**Leanplum**，并为该连接命名。
6. 将您在第3步中从相关Leanplum账号复制的**App ID**和**Secret**粘贴到对应的字段。

   <Image align="center" alt="leanplum_integration_af_dashboard.png" src="https://files.readme.io/def2f96ddade1e3dfb04cae1a379c66aa3501414cfd42d459b2adc53542fcfaa-31237653542673.png" />
7. 该连接保存完毕后即可用于任何新建或现存人群包。

相关人群包将在30分钟内出现在Leanplum的Audiences面板中。

* 从AppsFlyer同步到Leanplum的人群包在Leanplum面板中以 **"APPSFLYER:"** 为前缀。

</Accordion>

<div id="moengage" />

<Accordion title="MoEngage">

<div id="prerequisite-2" />

> 🚧 **前期准备：**
>
> 如需向MoEngage上传人群包，须符合以下条件：
>
> * 必须<Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">向AppsFlyer发送每个用户的客户用户ID</Anchor>（Customer User ID，简称CUID）。
> * CUID的值必须与用户的**MoEngage User ID**一致。

**MoEngage的渠道连接创建方法如下：**

1. 登录到您的MoEngage面板，进入**Settings > APIs > General Settings**。
2. 在**Data API Settings**部分复制以下密钥，之后在AppsFlyer受众共享中配置相关连接时会用到这些信息：
   * **Data API ID**（即下图中的<Image alt="A.png" src="https://files.readme.io/66b5bb0c4ea35f232f65dbc8dcbdfd6a91c12cf94915b19d33dae44834127058-31237653543313.png" width="16px" />）
   * **Data API Key** （即下图中的<Image alt="B.png" src="https://files.readme.io/f63914d3fefb55b627559c6e4c7d7cdef89239c0376a14c25c713a0a76dbad1b-31237653544337.png" width="16px" />）

   <Image align="center" alt="moengage_dashboard.png" src="https://files.readme.io/4c5acb849df14a4021c799d4bdb5ae49475446133068dd4fa6c7b00bef9b361b-31237653545617.png" />
3. 在网页浏览器的地址栏中查看MoEngage面板的地址，从中获取**MoEngage Data Center**的编号：
   * 如果您MoEngage面板的地址是[https://dashboard-01.moengage.com](https://dashboard-01.moengage.com)，表示您的账户被分配到Data Center 1。
   * 如果该地址是[https://dashboard-02.moengage.com](https://dashboard-02.moengage.com)，表示您的账户被分配到Data Center 2。
   * 如果该地址是[https://dashboard-03.moengage.com](https://dashboard-03.moengage.com)，表示您的账户被分配到Data Center 3。
4. 从AppsFlyer后台的受众共享面板进入**连接**选项卡，并点击**添加新连接**。
5. 在“合作伙伴名称”中选择**MoEngage**，并为该连接命名。

   <Image align="center" alt="moengage_outgoing_connection.png" src="https://files.readme.io/fbeac3be05fd3a7f64db3992981e086de86954392f33a8331f09b320ce073718-31237648147089.png" />
6. 将您在第2步中从相关MoEngage账号复制的**Data API ID**和**Data API Key**填入相关字段。
7. 根据您在第3步中查到的编号选择相应的**Data Center**。
8. 该连接保存完毕后即可用于任何新建或现存人群包。

从AppsFlyer同步到MoEngage面板的人群包会以<Anchor target="_blank" href="https://help.moengage.com/hc/en-us/articles/206528613-Custom-Segments">custom segments</Anchor>的形式呈现。

</Accordion>

<div id="mytarget" />

<Accordion title="MyTarget">

**MyTarget的受众共享连接方式如下：**

1. 从AppsFlyer后台进入**受众共享** > **连接**。
2. 点击 **+ 添加新连接**。
3. 输入**连接名称**。
4. 选择**MyTarget**。
5. 点击**登录到MyTarget**。
6. 选择一个广告账号。
7. 点击**Save**。

</Accordion>

<div id="oracle-data-cloud" />

<Accordion title="Oracle Data Cloud">

1. 添加新的Oracle Data Cloud连接, 如下图所示:

   <Image align="center" alt="" src="https://files.readme.io/cbb2cbc3559d73c2446da2a59cfdedb1ee631165c189d2bf87e8ef4c625914f6-51911738713233.png" />
2. 复制**AppsFlyer的Seat ID**，然后请您的Oracle Data Cloud客户经理将其列入白名单。加白后，AppsFlyer就可以代您创建对应的类别。
3. 添加**Seat ID**和**Site ID** （您可以咨询Oracle Data Cloud客户经理获取这两个ID）。
4. 验证您的**SeatID**之后 ，下拉列表中会显示所有的**Parent Categories**：

   <Image align="center" alt="" src="https://files.readme.io/a91a14c8d37b8ec399c58722e3083d6f6c050699352b58e6db5255894a0d84a2-51911721849745.png" />
5. 选择一个**Parent Category**，在其中创建所需的子类别。
6. 点击**Add Connection**。

</Accordion>

<div id="pushspring" />

<Accordion title="PushSpring">

**PushSpring的受众共享连接方式如下：**

1. 从AppsFlyer后台进入**受众共享** > **连接**选项卡。
2. 点击 **+ 添加新连接**。
3. 输入**连接名称**。
4. 选择**PushSpring**。
5. 点击**登录到PushSpring**。  
   界面会显示一个新的时间戳。
6. 点击**Save**。  
   对接完成并且上传受众之后，它就会显示在您的 PushSpring**Imported Audiences**面板中。

</Accordion>

<div id="slack" />

<Accordion title="Slack">

AppsFlyer会以CSV文件的形式将设备ID上传到您的Slack公共频道（Public Channel）。

**Slack的受众共享连接方式如下：**

1. 从AppsFlyer后台进入**受众共享** > **连接**选项卡。
2. 点击 **+ 添加新连接**。
3. 输入**连接名称**。
4. 选择**Slack**。
5. 点击**添加到Slack**。
6. 在Slack身份验证页面中，选择相关的**Slack Team**。
7. 选择一个**Public Channel**。
8. 点击**Save**。  
   对接完成且人群包上传完毕后，您选定的Slack频道中就会出现带有相关设备ID的CSV文件。

</Accordion>

<div id="snapchat" />

<Accordion title="Snapchat">

**Snapchat的受众共享连接方式如下：**

1. 从AppsFlyer后台进入**受众共享** > **连接**选项卡。
2. 点击 **+ 添加新连接**。
3. 输入**连接名称**。
4. 选择**Snapchat**。
5. 点击**登录到Snapchat**。
6. 选择您的**公司**和**广告账号** 。
7. 点击**Save**。  
   人群包上传完毕后，Snapchat面板会在24小时内呈现相关信息。

<div id="x-formerly-twitter" />

<div id="note-1" />

> 📘 **注意事项**
>
> Snapchat会移除无法匹配的设备ID，因此人群包中的用户数量可能会变少。

</Accordion>

<div id="tapjoy" />

<Accordion title="Tapjoy">

**请按以下方式将人群包关联到Tapjoy：**

1. 让您的Tapjoy客户经理提供相关**Partner ID**。
2. 从Tapjoy后台的**App Settings**页面中获取您的**Publisher Reporting API Key**。

   <Image align="center" alt="" src="https://files.readme.io/4aee504ce72061784c47b5bb84ac7e2bf73bf7c7dcb5b78ef83fb11e807a366a-31237653547665.png" />
3. 从AppsFlyer后台进入**受众共享**。选择一个人群包，然后进入**连接**选项卡。
4. 点击**添加渠道连接**。
5. 输入**连接名称**。
6. 选择**Tapjoy**。

   输入**Tapjoy Partner ID**和**Publisher Reporting API Key**。
7. 选择一个Tapjoy列表类型：   
   * Denylist
   * App suppression
8. 根据需要输入**Tapjoy app ID**和**Tapjoy offer ID** 。
9. 点击**Save**。

</Accordion>

<div id="tiktok-for-business" />

<Accordion title="TikTok for Business">

**前期准备**：

* 需具备<Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=12791">TikTok for Business帐户所有者、管理员或运营人员</Anchor>的TT广告账户权限。

**TikTok的受众共享连接方式如下：**

1. 让您的TT客户经理提供相关的TT4B登录证书。
2. 从AppsFlyer后台进入**受众共享** > **连接**选项卡。
3. 点击 **+ 添加新连接**。
4. 输入**连接名称**。
5. 选择**TikTok**。
6. 点击**登录到TikTok For Business**。  
   界面会打开开发人员专用的TikTok for Business窗口。
7. 在**TikTok for Business**后台选择一个授权帐户。
8. 点击**同意授权**。  
   数秒后，界面会显示AppsFlyer受众共享窗口。
9. 点击**Save**。

</Accordion>

<div data-zendesk-anchors="connecting-to-audiences-partners=%E6%B8%A0%E9%81%93%E8%BF%9E%E6%8E%A5%E7%AE%80%E4%BB%8B 01H8H2SWZKEFQ75XS6VK8F10MW=%E6%B8%A0%E9%81%93%E8%BF%9E%E6%8E%A5%E7%AE%80%E4%BB%8B 01H8H2SWZNFBN32QEVG80EX1BT=%E9%99%A4%E4%BA%86%E4%B8%8A%E8%BF%B0%E6%B8%A0%E9%81%93%E4%B9%8B%E5%A4%96appsflyer%E4%B9%9F%E7%AB%AD%E8%AF%9A%E6%AC%A2%E8%BF%8E%E5%85%B6%E4%BB%96%E6%B8%A0%E9%81%93%E5%8A%A0%E5%85%A5%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB%E5%AF%B9%E6%8E%A5 Adobe_Marketing_Cloud=adobe-audience-manager-aam 01ECF4ZD12TS7QA0NWS44222SJ=adobe-audience-manager-aam 01ECF4ZD13JNGX7NRKFEPQJCSX=amazon-s3 01ECF4ZD13AEW3SQX80YQZ00NR=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9 01H8H2SWZNVYXWPPWHBQBSVWFC=braze using-a-braze-external-id-parameter=%E4%BD%BF%E7%94%A8braze-external-id%E5%8F%82%E6%95%B0 01H8H2SWZNFFSD1HZTJV3V1AJJ=%E4%BD%BF%E7%94%A8braze-external-id%E5%8F%82%E6%95%B0 using-the-cuid-field=%E4%BD%BF%E7%94%A8cuid%E5%AD%97%E6%AE%B5 01H8H2SWZN9BNV35XHD5RBZZZN=%E4%BD%BF%E7%94%A8cuid%E5%AD%97%E6%AE%B5 01ECF4ZD13Q7QE5C9M8ZS4R8ZG=criteo facebook_audiences=facebook 01ECF4ZD14ZZ19RQDQ8JWH9RTZ=facebook 01H8H2SWZPP1MJXH9EHQXVW1CW=google-ads 01ECF4ZD14JMJVRATZSNC539DQ=httpool 01H8H2SWZP5QRV6VXB9KTEQSPT=Kakao h_01K0PVJZR5E6ZJEANYCEP5K22K=leanplum h_01K0PVJZR5CC8DV4XHH0C15EC7=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87-1 01H8H2SWZPN1N4X4H2TRJZHRKN=moengage 01H8H2SWZP91437F31Y79KZ7Y9=%E5%89%8D%E6%9C%9F%E5%87%86%E5%A4%87-2 01ECF4ZD142S55XVX1RS7H5FQ2=mytarget Oracle_BlueKai=oracle-data-cloud 01ECF4ZD14R3R19N2V8ES1W4YQ=oracle-data-cloud 01ECF4ZD142Z40SY6G21034E1Y=pushspring 01ECF4ZD15QDRGHCNEA2VGTXBN=slack 01ECF4ZD15KXPJHBYXK6AT9J4M=snapchat 01ECF4ZD15QDZJTFZS9GE9XG3Z=%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A1%B9-1 tapjoy_audiences=tapjoy 01ECF4ZD15P9DFQYHPAY92TFXH=tapjoy 01ECF4ZD16DHBG3VBT769ZYGV9=tiktok-for-business" />
