---
title: オーディエンスのパートナー連携
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
  edited_at: '2026-10-14T09:33:39Z'
  id: 360013960577
  locale: ja
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ja/articles/360013960577
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：**  作成したオーディエンスを広告媒体などのパートナーに接続します。

<div id="about-partner-connections" />

## パートナー接続について

パートナー接続により、オーディエンスを簡単に継続的にパートナーに送ることができるため、カスタマイズされたキャンペーンを提供することができます。オーディエンスパートナーの一覧、連携に必要な要件、各パートナーでサポートされているユーザー識別子などを説明しています。

**パートナーと連携するには、以下の表から見つけ、以下の手順に従ってください。**

* 表に特定のパートナー向けのリンクが含まれている場合は、リンクをクリックし、提供される手順を用いて連携作業を進めてください。  
  **--または--**
* テーブルに必要な接続要件（資格情報）のリストが含まれている場合：
  1. パートナーから認証情報を取得してください。
  2. Audiencesで<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#create-a-new-connection">新しいパートナー接続を作成</Anchor>するための指示に従ってください。

**注記：** 1オーディエンスにつき、最大50のパートナー接続を推奨します。

| パートナー |  | 連携先の要件 | サポートされている識別子 |
| --- | --- | --- | --- |
| 530 Broadway Media | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/broadway89.png" width="143px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| RZR (formerly Aarki) | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/aarki.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li><li>IMEI</li><li>OAID</li><li>IDFV</li><li>CUID</li><li>メールアドレス（ハッシュ化）</li><li>電話番号 (ハッシュ化)</li><li>Braze外部ユーザーID</li></ul> |
| AccessTrade Vietnam | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/accesstradevn.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| AdAction Brazil | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adactionbr.png?v=1&" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Addons | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/addons.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| AdPacker | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adpacker.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| AdPiece | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adpiece.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Adikteev | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/trademob.png?v=1" width="71px" /> | API username, API password, Company ID | <ul><li>IDFA</li><li>GAID</li></ul> |
| AdiSON Offerwall | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adisonofferwall.png?v=1" width="111px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Adjoe | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adjoe.png?v=1" width="111px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Admile | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/admile.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Admuxer | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/admuxer.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Adobe Audience Manager | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adobemc.png" width="60px" /> | **注意：** 現在、Adobeへの新しい接続を作成することはできません。<br /><br />連携手順：[Adobe Audience Manager](/docs/audiences-partner-connections#adobe-audience-manager-aam) | <ul><li>IDFA</li><li>GAID</li></ul> |
| AdsForteMobi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/brighttecxf.png" width="98px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Adsgalaxy | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/nhmtgvm.png?v=1" width="98px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| ADSJOY | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adsjoy.png?v=1" width="98px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| AdTiming | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/adtiming.png?v=1" width="98px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Advolt | <Image alt="Advolt.jpg" src="https://files.readme.io/78f1eb00caacd45ec85aa24eecf48ad5bc18fa7b1d28fc6d2a4342b9f5f14f7d-31237653514129.jpg" width="122px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Affinity | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/affinity.png" width="70px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Affle | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/affle.png" width="70px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Amazon S3 | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/AmazonS3.png" width="134px" /> | 連携手順：[Amazon S3](/docs/audiences-partner-connections#amazon-s3) | <ul><li>IDFA</li><li>GAID</li><li>IMEI</li><li>OAID</li><li>IDFV</li><li>CUID</li><li>メールアドレス（ハッシュ化）</li><li>電話番号 (ハッシュ化)</li></ul> |
| Appgrowth | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appgrowth.png?v=1" width="104px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| AnyMind | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/anymindgroup.png?v=1" width="104px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Appier | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appier.png?v=1" width="104px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Applabs | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/applabs.png?v=1" width="104px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Appluton | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appluton.png" width="112px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Appnext | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appnext.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Appreciate | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appreciate.png" width="135px" /> | Buyer ID, API key | <ul><li>IDFA</li><li>GAID</li></ul> |
| Appsmob | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appsmob.png" width="113px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Arrivemoovit |  | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Atharvasai | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/atharvasa4f.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Autumnant | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/autumnant.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Beintoo | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/beintoo.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Betop | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/betop.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li><li>IDFV</li></ul> |
| Bidease | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/bidease.png" width="81px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| BidMatrix | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/bidmatrix.png" width="87px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Bigabid | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/bigabid.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Bigo Ads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/bigoads.png?v=1" width="106px" /> | Bigo Adsにログインして認証 | <ul><li>IDFA</li><li>GAID</li></ul> |
| Bluemediagroup | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/bluemediagroup.png?v=1" width="106px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Braze | <Image alt="Braze logo Nov 2023.jpg" src="https://files.readme.io/c84c2459ec87a3c3fef83e573ff4d43e45df8604223d53aaa989ad410d372d54-31237648110737.jpg" width="107px" /> | 連携手順：[Braze](/docs/audiences-partner-connections#braze) | <ul><li>Braze外部ユーザーID</li></ul> |
| c2c\_audience | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/click2commission.png" width="123px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Cecom | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/cecom.png?v=1" width="123px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Cherryonly | ![cherryonl4f (1).png](https://files.readme.io/ad4e693ada777a79cbcadc668a67c03272547e0641d3312349392a9ea34ffe64-35884799991185.png) | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Chartboost | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/chartboost.png?v=1" width="123px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Collectcent | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/collectcent.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| CRED | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/cred.png" width="62px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Criteo | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/criteo.png" width="135px" /> | 連携手順：[Criteo](/docs/audiences-partner-connections#criteo) | <ul><li>IDFA</li><li>GAID</li><li>メールアドレス（ハッシュ化）</li></ul> |
| CRONBID | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/cronbid.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Daangn | <Image alt="danggeunmx8 (1).png" src="https://files.readme.io/97d8be9cdb9f4f82efdd6ccf735c5a6f195f4d10868d107c6b29bfbe99880cbb-34192650411665.png" width="92px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Dataseat | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/dataseat.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Dealsnprice | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/dealsnprice.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| DemandScale | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/siftco.png?v=1" width="64px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Downstream | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/downstreamai.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Edge226 | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/edge226.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Exmox | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/exmox.png" width="92px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Facebook | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/facebook.png" width="135px" /> | 連携手順：[Facebook](/docs/audiences-partner-connections#facebook) | <ul><li>IDFA</li><li>GAID</li><li>メールアドレス（ハッシュ化）</li><li>電話番号 (ハッシュ化)</li></ul> |
| Filexmedia | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/filexmedia.png" width="120px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Freecash | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/freecash.png" width="71px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Funnetads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/funnetads.png" width="92px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Galaxyx | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/galaxyxtech.png" width="71px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Gameappzone | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/gameappzo45i.png" width="118px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Gamelight | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/thespotlight.png" width="71px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Glance | <Image alt="Screen_Shot_2022-08-02_at_10.26.22.png" src="https://files.readme.io/32870ef5ab9e2714b7cae55d87c843b7a39116c1b2c020b869b2595fcb256635-31237648111633.png" width="114px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Google Ads<br /><br />Google AdsとAudiencesの連携をご利用いただけるかどうかについては、担当のCSMまたは [hello@appsflyer.com](mailto:hello@appsflyer.com) までお問い合わせください。 | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png" width="67px" /> | 連携手順：[Google Ads](/docs/audiences-partner-connections#google-ads) | <ul><li>IDFA</li><li>GAID</li><li>メールアドレス（ハッシュ化）</li><li>電話番号 (ハッシュ化)</li></ul> |
| Gotripmobi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/gotripmob06.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Growone |  | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Hillsmobi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hillsmobi.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Hippoad | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hippoad.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Honeybutterr |  | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Httpool | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/httpool.png" width="135px" /> | 連携手順：[Httpool](/docs/audiences-partner-connections#httpool) | <ul><li>IDFA</li><li>GAID</li></ul> |
| Hybrid | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hybrid.png?v=1" width="96px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| iCubesWire | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/icubes.png?v=1" width="96px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| ImagePerfect | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/imageperfect.png?v=1" width="96px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Indus App Bazaar (Samsung Galaxy Store) | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/samsunggalaxystoreindusappbazaar.png?v=1" width="96px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| InMobi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/inmobi.png" width="135px" /> | property\_id | <ul><li>IDFA</li><li>GAID</li></ul> |
| Insider | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/useinsider.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Intentaiii5 | ![](https://cdn.appsflyer.com/marketplace/static/logo/intentaiii5.png) | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| ironSource | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ironsource.png" width="135px" /> | ironSource user ID, API key | <ul><li>IDFA</li><li>GAID</li></ul> |
| Jampp | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jampp.png" width="135px" /> | Client ID, Client secret, App ID | <ul><li>IDFA</li><li>GAID</li></ul> |
| JioAds | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jioads.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Join Ship Tech Limited | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/joinship.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Kakao | <Image alt="Kakao_Logo_Primary_Screen_V1.0.png" src="https://files.readme.io/62df88fab5301c8c6d0fc31b94456a79ea73c5195f37332ddd144e1259c9f9f4-37842576339729.png" width="116px" /> | 連携手順：[Kakao](/docs/audiences-partner-connections#Kakao) | <ul><li>IDFA</li><li>GAID</li></ul> |
| kakoads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/kakoads.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| KashKick | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/kashkick.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Kaden | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/kaden.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Kayzen | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/dataliftretargeting.png" width="60px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Kidult Media | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/kidult.png" width="82px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Kwai for business | <Image alt="Kwai_for_business_2.jpg" src="https://files.readme.io/0dece6ec834ff75ad53aae0932c873e9bb85ed9c42acdf5c84a896b7f50bccbc-31237648112913.jpg" width="53px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Leanplum | ![](https://cdn.appsflyer.com/marketplace/static/logo/leanplum.png?v=1) | [Leanplum](/docs/audiences-partner-connections#leanplum)の連携手順 | <ul><li>CUID</li></ul> |
| learnshapwm |  | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Lemmonet | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/lemmonet.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| LessMobi |  | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Lifestreet | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/lifestreet.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Liftoff | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/liftoff.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| LinkedBro | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/digmobiteqp.png" width="86px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Loopyapac | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/loopyapac6d.png" width="86px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Manage  <br />(Criteo が買収) | ![manage_logo.png](https://files.readme.io/0855ecfbf1c026fdedddbedeff95c4b3cbf3663d7cf1e224b6c3e92d35bb1705-31237653520145.png) | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Moiads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/moiads.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| mDSP | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mdsp.png" width="135px" /> | Organization ID | <ul><li>IDFA</li><li>GAID</li></ul> |
| MediaSmart | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mediasmart.png" width="135px" /> | Organization ID | <ul><li>IDFA</li><li>GAID</li></ul> |
| Mediasurfer | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mediasurfer.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| MinoAds | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/minoads.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| mInsights  <br />(GroupM) | ![m_insights_blue.png](https://files.readme.io/0ae9dd57d9692987ce3a6ebd09d9c09c1bd41e3cfe5846dbe8e0e09f83384ebe-31237653520913.png) | Access key ID, Secret access key, Path | <ul><li>IDFA</li><li>GAID</li></ul> |
| Mintegral | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mintegral.png" width="135px" /> | API key, App ID | <ul><li>IDFA</li><li>GAID</li></ul> |
| Mistplay | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mistplay.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Mobadbid | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobadbid68.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Mobavenue | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobavenue.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Mobisummer (Tec-Do) | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobisummer.png" width="103px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Moboost | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/moboostlt.png" width="103px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Mobusi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobusi.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Mobvista | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobvista.png" width="135px" /> | Advertiser ID, API key | <ul><li>IDFA</li><li>GAID</li></ul> |
| MobWonder | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobwonder.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| MobYoung | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobyoung.png?v=1" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| MoEngage | ![moengage_logo.png](https://files.readme.io/a1557a6521ad6c94d5972a08f540a40cc4ec53137eabe3b1848c3696ec7a9c5f-31237648114833.png) | [MoEngage](/docs/audiences-partner-connections#moengage)接続手順 | <ul><li>CUID</li></ul> |
| Moloco | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/moloco.png" width="135px" /> | APIキー<br /><br />**注：** これは、AppsFlyerのAudiences 連携専用の API キーです。Molocoの担当者から入手してください。 | <ul><li>IDFA</li><li>GAID</li></ul> |
| MoPub Acquire | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/crossinstall.png" width="60px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| MovableAD | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/movable.png" width="60px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| NAVER | <Image alt="Naver_Logotype.svg.png" src="https://files.readme.io/d236f0f4e89b68c3b4d6c085674cd2c98e397358f5e29f0f4de72b88fe3d1b12-33356334901905.png" width="131px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Novabeyond | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/novabeyond.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Olimob | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/olimob.png" width="95px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Opera Mobile | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/operamobile.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Palette Mobi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/palette.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Paytunes | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/paytunes.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| PerformanPBI | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/performanpbi.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Personaly | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/persona.ly.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Petal Ads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/huaweiadsglobal.png?v=1" width="100px" /> | Phone/email/login ID, password, Huawei ad account | <ul><li>IDFA</li><li>GAID</li></ul> |
| Pulsedrived | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/pulsedrivqw.png" width="100px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Pushwoosh | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/pushwoosh.png" width="52px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Radian | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/radianl5.png" width="52px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Recomob | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/recomob.png" width="111px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Remerge | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/remerge.png" width="135px" /> | Access key ID, Secret access key, Path | <ul><li>IDFA</li><li>GAID</li><li>IDFV</li></ul> |
| Resurgex | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/resurgexllh.png" width="102px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| RevX | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/revx.png?v=1" width="102px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| RTBHouse | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/rtbhouse.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Riversads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/riversads.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| SHAREit | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/shareit.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Shenzhen Fumao Technology Co.(Szfumaokeji) |  | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Sidetinads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/sidetinads.png" width="96px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Singumedia | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/singumediqv.png" width="96px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Slack | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/slack.png" width="104px" /> | 連携手順：[Slack](/docs/audiences-partner-connections#slack) | <ul><li>IDFA</li><li>GAID</li><li>IMEI</li><li>OAID</li><li>IDFV</li><li>CUID</li><li>Email</li><li>Phone</li></ul> |
| Smadex | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/smadex.png" width="85px" /> | Smadexログイン | <ul><li>IDFA</li><li>GAID</li></ul> |
| Snakzy by Eneba | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/helisplaynnf.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Snapchat | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/snapchat.png" width="60px" /> | 連携手順：[Snapchat](/docs/audiences-partner-connections#snapchat) | <ul><li>IDFA</li><li>GAID</li><li>メールアドレス（ハッシュ済み）</li><li>電話番号 (ハッシュ化)</li></ul> |
| Spotad | ![](https://cdn.appsflyer.com/marketplace/static/logo/spotad.png) | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| StackAdapt | ![](https://cdn.appsflyer.com/marketplace/static/logo/stackadapt.png) | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| StartApp | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/startapp.png" width="135px" /> | APIトークン | <ul><li>IDFA</li><li>GAID</li></ul> |
| Superads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/superads.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Surgex | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/surgex.png" width="114px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Taboola | ![](https://cdn.appsflyer.com/marketplace/static/logo/taboola.png?v=1) | Taboolaにログインして認証を行ってください | <ul><li>IDFA</li><li>GAID</li></ul> |
| Tapjoy | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tapjoy.png" width="135px" /> | 連携手順：[Tapjoy](/docs/audiences-partner-connections#tapjoy) | <ul><li>IDFA</li><li>GAID</li></ul> |
| TaurusX | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/taurus.png?v=1" width="85px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Teamob | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/teamob.png" width="85px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Tencent | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tencent.png?v=1" width="135px" /> | Tencentにログインして認証 | <ul><li>IDFA</li><li>IMEI</li><li>OAID</li><li>電話番号 (ハッシュ化)</li></ul> |
| TheTradeDesk | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/thetradedesk.png" width="135px" /> | Advertiser ID, Secret key | <ul><li>IDFA</li><li>GAID</li></ul> |
| TikTok For Business (Bytedance) | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tiktokglobal.png" width="135px" /> | 連携手順：[TikTok For Business](/docs/audiences-partner-connections#tiktok-for-business) | <ul><li>IDFA</li><li>GAID</li><li>IMEI</li><li>OAID</li></ul> |
| Togoha | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/togoha.png" width="96px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Toponad | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/toponad.png" width="87px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Truecaller | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/truecaller.png?v=1?" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| TTS Customer | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/waveads.png?v=1?" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Twinkleads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/twinkleads.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Tyrads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tyradscpl.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Unico Tech Limited | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/unico.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Unicorn DSP | ![Unicorndsp.jpg](https://files.readme.io/4f5917f0e15a37b1767aab744633e326e9cceefcb7cb3cd40fc1f8e0718f77cc-31237653524113.jpg) | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Unity | ![](https://cdn.appsflyer.com/marketplace/static/logo/unityads.png) | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Uplivo | ![](https://cdn.appsflyer.com/marketplace/static/logo/uplivo2wj.png) | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Upsflyer | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/upsflyer.png?v=1?" width="124px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Upyield | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/upyield.png?v=1?" width="81px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Vaca Mobiles | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/vacastudios.png?v=1?" width="124px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| VastMedia | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/vastmedia.png?v=1?" width="94px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Vidma recorder | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/vidmarecorder.png?v=1?" width="63px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Vivo | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/vivoglobal.png" width="100px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Vizury | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/revx.png" width="100px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| VK Ads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mail.ru.png" width="85px" /> | 連携手順：[VK Ads](/docs/audiences-partner-connections#mytarget) | <ul><li>IDFA</li><li>GAID</li></ul> |
| Vserv | ![Vserv.jpg](https://files.readme.io/6984558eed14f4137907b8ef8b4064dd415ed28dce3d0451279bc2a304cc00b4-31237653525137.jpg) | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| VYBS | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/vybsafl.png" width="111px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Whistle Feed | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/wvaluemarjqg.png" width="111px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Wider Planet | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/widerplanet.png" width="111px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| WingsApps | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/wingsapps.png?v=1" width="111px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| X Ads (formerly Twitter Ads) | <Image alt="x logo.png" src="https://files.readme.io/be1e5b0210a1d7d8aaef398b8a3a6e41ddfb6d66c4e360df6294c309fa507fec-44611769729809.png" width="113px" /> | 連携手順：[X Ads](/docs/audiences-partner-connections#x-formerly-twitter) | <ul><li>IDFA</li><li>GAID</li><li>メールアドレス（ハッシュ化）</li><li>電話番号 (ハッシュ化)</li></ul> |
| Xapads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/xapads.png?v=1" width="111px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Xiaomi Ads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/xiaomiglobal.png?v=1" width="85px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Xtend | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/xtendbw.png?v=1" width="111px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Xysea | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/xysea.png" width="111px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Yandex | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yandex.png" width="59px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li><li>電話番号 (ハッシュ化)</li><li>メールアドレス（ハッシュ化）</li></ul> |
| Yeahmobi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yeahmobi.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Yesokads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yesokads.png" width="135px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| YouAppi | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/youappi.png" width="118px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Youenads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/youenads.png" width="118px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Zhizhen | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/batcloud.png" width="118px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Zoneads | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zoneads.png" width="118px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |
| Zoomd DSP | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/zoomd.png" width="118px" /> | APIキー | <ul><li>IDFA</li><li>GAID</li></ul> |

<div id="we-love-working-with-new-audiences-partners" />

> 📘 **新しいオーディエンスパートナーを募集しています！**
>
> お探しのパートナーが上記リストに表示されていない場合は、お気軽にCSMまでお問い合わせください。連携の可能性についてパートナー様に確認させていただきます。

<div id="adobe-audience-manager-aam" />

<Accordion title="Adobe Audience Manager (AAM)">

AppsFlyerは **Traits** を作成し、AAMで選択した **Data Source**と同期します。

**オーディエンスをAAMへ連携**：

1. [Adobe Marketing Cloudダッシュボード](https://bank.demdex.com/portal/login/Logout.ddx)にログインしてください。
2. **Manage Data** > **Data Sources**へ進みます。
3. **Data Sources**画面にて、新しい**Data Source**を作成してください。

   [![](https://files.readme.io/4f9e3f508fb70287ba2c605ef9f8099f7151e7530ac3312e752b26130751e428-31237653528593.jpg)](https://files.readme.io/4f9e3f508fb70287ba2c605ef9f8099f7151e7530ac3312e752b26130751e428-31237653528593.jpg)
4. 以下のようにフォームを入力します。
   * ID Typeを **Device Advertising ID**に設定してください。
   * インバウンドデータソース設定にて、**Customer ID**を有効にしてください。
5. **保存**をクリックしてください。  
   **Data Sources**の選択肢が表示されます。
6. 後で使用するために、Data Source IDを記録します。
7. 左側のメニュー **Administration** > **Groups**へ進みます。
8. **権限**タブへ進んでください。

   [![](https://files.readme.io/b565e39220e13f58ee603ab2874bd4743b30f98f8395d1ad6b79f556b8fe3cd0-31237648132753.png)](https://files.readme.io/b565e39220e13f58ee603ab2874bd4743b30f98f8395d1ad6b79f556b8fe3cd0-31237648132753.png)
9. 新しいグループを作成します。
10. 作成した Data Source を選択します。
11. **Save Object**をクリックしてください。
12. **Admin** > **Users**へ進んでください。

    [![](https://files.readme.io/9167247d30e2aee69c891969e7aa56bbe2095cc8a7dd4bf3896cd563a00cac71-31237648134801.png)](https://files.readme.io/9167247d30e2aee69c891969e7aa56bbe2095cc8a7dd4bf3896cd563a00cac71-31237648134801.png)
13. AppsFlyerオーディエンスが使用する新しいユーザーを作成し、必要に応じて必須フィールドに入力します。
14. **Assigned Groups** にて、以前作成したグループを選択してください。
15. 作成したユーザーの**メールアドレス**と**パスワード**を記録してください。
16. **保存**をクリックしてください。
17. AppsFlyerにて**オーディエンス**を開きます。
18. 特定のオーディエンス **> Connect** タブを選択します。
19. **+ 新しい連携先**をクリックしてください。
20. 連携先の名前を入力してください。
21. **Adobe Marketing Cloud**を選択してください。  
    Adobe Marketing Cloud への連携画面が表示されます。
22. 前述の認証情報を使用して項目に入力します。
23. **保存**をクリックしてください。  
    オーディエンスデータは、24時間後に **Analytics** > **Onboarding Status** の下にあるAAMにて利用できます。

</Accordion>

<div id="amazon-s3" />

<Accordion title="Amazon S3">

S3連携を作成すると、AppsFlyerはオーディエンスのデバイスIDを直接S3バケットに送信できます。S3に送信されたファイルには、次の特徴があります：

* ファイル名：オーディエンス名と日付例：my\_audience\_2020-06-23.csv
* コンテンツ：1つのカラム、ヘッダーなし、デバイスIDを含む
* 追加ファイルが毎日書き込まれます。既存ファイルは削除されません。
* スプリットオーディエンスが送信されると、単一のZIPファイルが書き込まれ、これには各パートナーごとに個別のファイル（割り当て）が含まれています。

**Amazon S3にオーディエンスを連携する**：

1. AppsFlyerにて、**オーディエンス**を開き、オーディエンスを選択します。
2. **接続**タブをクリックします。
3. **+ 新しい連携先**をクリックします。
4. **連携名**を入力してください。
5. **Amazon S3**を選択してください。  
   **連携先の追加**画面が表示されます。

   ![image__9_.png](https://files.readme.io/790f8a50bf14fbb4065d9dcee05e31fa866bc73f236f439ec73f2bc833b31be6-31237653533201.png)
6. **クロスアカウントロールのARN**、**バケット名**、**リージョン名**を入力します。  
   **注：** 常にリージョン名を入力することをお勧めします。AWS でリージョン名がデフォルトで自動的に有効になっていない場合は、ここに入力しないと接続を作成できません。AWS コンソールのホームページでリージョンを見つけるには、ページの右上にある国のドロップダウンをクリックすると、リージョンが表示されます。 <Image alt="region_name.jpg" src="https://files.readme.io/a3b65660a638674cbbe0da2802b4f926929d167d0b528c25c12ded6a90b0e981-31237648137489.jpg" width="355px" />
7. 後ほど使用するために、**Account ID** と **External ID** を記録してください。
8. **AWS** コンソールにて、**IAM** > **Policies**へ進みます。
9. **Create Policy**をクリックしてください。
10. **JSON** をクリックしてください。
11. 次のポリシースニペットをJSON画面に貼り付けてください。

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
12. **BUCKET-NAME**を、AppsFlyerがオーディエンスをアップロードするバケットの名前に置き換えます。

    <div id="note" />

    > 📘 **注意**
    >
    > ポリシーには、ルートバケットのみを含め、パスに追加のディレクトリを含めないでください。例えば、リソース **arn：aws：s3 ::: BUCKET-NAME / Directory / \***はサポートされていません。ファイルを特定のディレクトリに転送する必要がある場合は、ステップ14を参照してください。


    アクション`PutObject`、`DeleteObject`、および`ListBucket`は、AppsFlyerがあなたのバケットで必要なアクションを実行するために必須です。
13. **Review policy**をクリックしてください。
14. ポリシーの**Name**を入力してください。
15. **Create Policy**をクリックしてください。
16. AWSコンソールで、**Access management** > **Roles** へ進んでください。

    [![](https://files.readme.io/85a4a81b5ebd131b6b3a20ca6ee136a0d10556363cff2deab96397ec889db141-31237648138513.png)](https://files.readme.io/85a4a81b5ebd131b6b3a20ca6ee136a0d10556363cff2deab96397ec889db141-31237648138513.png)
17. **Create role** をクリックしてください。
18. あなたのAWSアカウントとAppsFlyerのAWSアカウント間でクロスアカウントアクセスを提供する **Another AWS account** オプションを選択してください。

    [![](https://files.readme.io/1f8db2c84d1cbde4a88fd6d7dace3eb5cb65f8fc9608b0ec568921a2b7c85759-31237653535761.png)](https://files.readme.io/1f8db2c84d1cbde4a88fd6d7dace3eb5cb65f8fc9608b0ec568921a2b7c85759-31237653535761.png)
19. <strong>Account IDを入力してください。</strong>これはAppsFlyer管理画面から既にコピーしたAccount IDです。
20. **Require external ID**を選択してください。この外部IDはAppsFlyer管理画面から既にコピーしたものです。
21. AWSアカウントの既存のポリシーからポリシーを選択するように求められます。以前に作成したポリシーを選択してください。
22. 新しく作成されたロール名をクリックして、プロパティ画面を開きます。

    [![](https://files.readme.io/9b61cf2c8ec3efd9f6548e1ee6b6ca945dd1160901516f93cd16ac3544d3aade-31237648139793.png)](https://files.readme.io/9b61cf2c8ec3efd9f6548e1ee6b6ca945dd1160901516f93cd16ac3544d3aade-31237648139793.png)
23. **Role ARN**を記録してください。
24. AppsFlyer S3 連携画面にて、ARNとバケット名を適切な項目に入力します。

    ファイルをバケット内の特定のフォルダに転送する場合は、バケット名とその中にある後続のフォルダを「/」で区切って指定します。（bucketname/foldername/foldername）

    まだ存在しないフォルダ名を指定した場合は、アップロード処理中にAppsFlyerによって作成されます。
25. **接続の追加**をクリックします。  
    連携手順が完了したら、オーディエンスがアップロードされ、バケットにてデバイスIDを含むCSVが利用できるようになります。

</Accordion>

<div id="braze" />

<Accordion title="Braze">

<div id="prerequisite" />

> 🚧 **前提条件**
>
> アプリにBrazeとAppsFlyerの両方のSDKが実装されていることを確認してください。
>
> Brazeへの発信接続を作成するには、各ユーザーのBraze外部IDをAppsFlyerに渡すようにアプリ内のAppsFlyer SDKを設定する必要があります。これは、次のいずれかを使用して実行できます：
>
> * Braze External ID パラメータ
> * CUID項目
>
> #### <span id="using-a-braze-external-id-parameter"></span>Braze External ID パラメータの使用
>
> Brazeにオーディエンスをアップロードするには、AppsFlyer SDKの `setPartnerData` を使用して、各ユーザーのBraze External ID をAppsFlyerに渡す必要があります。使用例は以下の通りです：
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

#### CUID項目の使用

以下の場合、Braze外部ID専用のパラメータを設定する必要はありません：

* AppsFlyer に各ユーザーの CUID を送信するように SDKを構成している
* CUIDの値がBraze Enternal IDと同じである

**Brazeへのパートナー連携を作成する方法：**

1. Braze アカウントにて<strong>、Integrations > Technology Partners</strong>へ進み、AppsFlyerを選択してください。
2. **Data Import Using Cohort Import** セクションから、**Generate New Key** をクリックして**Data Import Key**を生成してください。
   * **注意：** ここにキーが既に表示されている場合は、新しいキーを生成する必要はありません。
   * <strong>重要！</strong>ページの**Data Import Using Cohort Import**セクションで（インストール計測セクションではなく）この作業を行っていることを確認してください。

     ![data_import_key.png](https://files.readme.io/4d288e6696da600d0e402b86a0986b3951f2cd35efd12084aa8feaeeb526fddf-31237653537681.png)
3. AppsFlyer管理画面で連携の設定をする際に使用するため、**Data Import Key** と **REST Endpoint** をコピーしてください。
4. AppsFlyerのオーディエンス画面にて、**連携先**タブへ進み、**+ 連携先**を追加をクリックしてください。
5. Brazeをパートナーとして選択し連携名を入力してください。
6. ステップ3でBrazeアカウントからコピーした Data Import Key と REST Endpoint を入力してください。

   ![braze_connection.png](https://files.readme.io/200d1a1bef906ea50e40b3d8113bb9fd72068b6fda25a2f70b95b4510bd992de-31237653538449.png)
7. 連携先を保存すると、新規または既存のオーディエンスを接続できるようになります。
8. AppsFlyerオーディエンスがBrazeにアップロードされると、Brazeでセグメントを定義する際にフィルタとして使用することができます。

   ![cohorts_as_filter.png](https://files.readme.io/eec9e014afcb488bb7ebe31167cd5871c38207c8f4542e20ea313b7019e8b43a-31237653538961.png)

</Accordion>

<div id="criteo" />

<Accordion title="Criteo">

**オーディエンスをCriteoに接続**：

1. Criteo 管理画面にて、**API User**を作成します。
2. API User Client ID と Secret を記録します。
3. AppsFlyerにて、**オーディエンス** > **連携先**へ進みます。
4. **+ 新しい連携先**をクリックします。
5. **連携名**を入力してください。
6. Criteoを選択してください。

   適切な項目に、以前記録した**API UserClient ID**と**Client Secret**を**Advertiser ID**と一緒に入力してください。
7. **保存**をクリックしてください。

**注記：** 関連するアプリが「Already granted」というメッセージでグレーになっているために接続することができない場合は、<Anchor target="_blank" href="https://consent.criteo.com">https://consent.criteo.com</Anchor> へ移動し、接続を取り消して、もう一度やり直してください。

</Accordion>

<div id="facebook" />

<Accordion title="Facebook">

**前提条件：**

Facebookビジネスマネージャーでの役割は、キャンペーン管理機能を含む管理者または広告主である必要があります。

**オーディエンスをFacebookへ接続**：

1. Facebookで**広告アカウント**を作成します。
2. AppsFlyerにて、**オーディエンス** > **連携先**へ進みます。
3. **+ 新しい連携先**をクリックします。
4. **連携名**を入力してください。
5. **Facebook**を選択します。
6. **Facebookにログイン** をクリックし、管理者または広告主としてログインします。
7. 必要な **広告アカウント** を選択します。  
   Facebookの権限ページが開きます。
8. Facebookインターフェイス上の手順に従ってください。
9. 設定を編集する場合は、**「広告を管理する」を有効にする必要があります。** これはデフォルト設定です。
10. Facebookユーザーインターフェイスを閉じるには、**完了**をクリックします。
11. **保存**をクリックしてください。  
    連携プロセスが完了しオーディエンスがアップロードされると、**Facebook カスタムオーディエンス** の管理画面で利用できるようになります。

**注記：** 広告アカウントから広告を作成できないというエラーが表示された場合は、 <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/audiences/reference/custom-audience-terms-of-service/">Metaカスタムオーディエンス利用規約</Anchor>に同意していることを確認してください。

</Accordion>

<div id="google-ads" />

<Accordion title="Google Ads">

AppsFlyerがオーディエンスをGoogle Adsに送信するためには、次のアクションを完了する必要があります。注意！全てのステップが完了した後にのみ、Googleにデータが送信されます。

**考慮事項：**

* 手順を完了すると、オーディエンスをGoogle Adsに接続してアップロードすることができます。入力されたリストがGoogle Adsに表示されるまで6&#126;12時間かかります。
* Googleのカスタマーマッチについて：
  * **サポート**：エンゲージメントのためのユニバーサルアプリキャンペーン（UACe）
  * **対応外**：  Universal App Campaigns

| アクション # | 説明 | 作業担当者 |
| --- | --- | --- |
| 1 | <ul><li>Google Adsアカウントにオーディエンスを連携します。</li><li>前提条件：Google広告のサインイン認証。</li></ul> | アカウントユーザー or アドミン |
| 2 | AppsFlyerプラットフォームのオーディエンスページにて、AppsFlyer Google Customer Matchの規約に署名（承認）します。 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) |
| 3 | Google Adsに問い合わせ、Google Adsアカウントで<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6379332?hl=en">カスタマーマッチ</Anchor>の使用を有効にするよう依頼します。 | アカウントユーザー |

**Google Adsにオーディエンスを連携する方法：**

1. AppsFlyerにて、[オーディエンス] を開き、オーディエンスを選択します。
2. **連携**タブに移動します。
3. **+パートナー接続を追加**をクリックしてください。
4. 連携先の名前を入力してください。
5. **Google Adsを選択してください。** Google Adsのアイコンが表示されない場合、担当CSM または [hello@appsflyer.com](mailto:hello@appsflyer.com) までお問合せいただき、Google Adwordsでのオーディエンスの利用を有効にするよう依頼してください。
6. ［**Google Adsでログイン**］ をクリックします。  
   **Googleのログイン画面**が開きます。
7. Googleのログインを完了し、Google Adsで選択肢を確認します。    
   画面が閉じます。
8. AppsFlyerプラットフォームで、**アカウントを選択します。**
9. **利用規約**をクリックしてください。  
   利用規約が表示されます。
10. もしあなたが管理者の場合：規約に同意される場合は、**同意する**をクリックしてください。
11. もしアドミン**でない**場合：
    1. **続行しあとで確認する**をクリックします。
    2. 管理者に、ログインし規約に同意するよう依頼します。次の手順を使用して実行します。
12. **保存**をクリックしてください。  
    Google Adsアカウントが連携されます。上記のチェックリストの全てのアクションが完了していることを確認し、連携を有効にします。

**規約に同意して連携を有効にするため、管理者は以下の手順を実行します。**

1. AppsFlyerにてオーディエンス画面を開きます。
2. **接続**タブに移動します。   
   オーディエンスパートナーの一覧が表示されます。
3. Google Adsにて、連携先の名前を選択してください。

   [![AcceptTermsAudiences_us-en.png](https://files.readme.io/511284f2e78963fe872af931c43f91a58295c67446e2cd35b7f148f6c9edbe90-31237648142993.png)](https://files.readme.io/511284f2e78963fe872af931c43f91a58295c67446e2cd35b7f148f6c9edbe90-31237648142993.png)
4. **利用規約**をクリックしてください。
5. 規約を確認し同意する場合は、**I accept**（同意）をクリックします。
6. **変更を保存** をクリックします。

</Accordion>

<div id="httpool" />

<Accordion title="Httpool">

**オーディエンスをHttpoolに接続**：

1. AppsFlyerにて、**オーディエンス** > **連携先**へ進みます。
2. **+ 新しい連携先**をクリックします。
3. **連携名**を入力してください。
4. **Httpool** を選択してください。
5. **Httpoolへログイン**をクリックします。  
   新しいタイムスタンプが表示されます。
6. **保存**をクリックしてください。

</Accordion>

<div id="Kakao" />

<Accordion title="Kakao">

**オーディエンスをKakaoへ接続：**

1. AppsFlyer管理画面 左メニュー **エンゲージメント** > **オーディエンス**へ移動します。
2. **+ 新しい接続**をクリックします。
3. Kakaoを検索し、パートナー名フィールドで選択します。
4. 連携先の名前を入力してください。以前にパートナー接続を作成する際に使用されていない新しい名前である必要があります。
5. **カカオでログイン**をクリックします。
6. ログインして、希望するビジネスアセットとKakaoモーメント広告アカウントを選択します。
7. カカオと共有するために承認したユーザー識別子を選択します。
8. **保存**をクリックしてください。  
   接続が追加され、接続状況とともに**接続**タブに表示されます。

</Accordion>

<div id="leanplum" />

<Accordion title="Leanplum">

<div id="prerequisite-1" />

> 🚧 **前提条件**
>
> オーディエンスをLeanplumに正常にアップロードする方法：
>
> * <Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">AppsFlyer にユーザーごとに顧客ユーザー ID (CUID) を送信する</Anchor>必要があります。
> * CUIDはユーザーの **Leanplum User ID** と一致している必要があります。

**Leanplumへのパートナー連携を作成する方法：**

1. Leanplumアカウントで、**Partner Integrations > AppsFlyer**へ移動してください。**Audiences**にて、新しい**Secret**を生成してください。

   [![audiences_leanplum_integration.png](https://files.readme.io/fb712c7cecacf6d80bf643f955ecc13d6c878a4db8b6fa5627f814ec659e6615-31237648144145.png)](https://files.readme.io/fb712c7cecacf6d80bf643f955ecc13d6c878a4db8b6fa5627f814ec659e6615-31237648144145.png)
2. **存在しないユーザー**のプロファイルを Leanplum で作成するかどうかを選択します。
   * 存在しないユーザー = AppsFlyerオーディエンスによって送信されたユーザーIDがLeanplumに存在しないユーザー
3. **App ID** と新しく生成された **Secret** をコピーして、AppsFlyer管理画面で連携先を作成する際に使用します。
4. AppsFlyerのオーディエンス画面にて、**連携先**タブへ進み、**+ 連携先を追加**をクリックしてください。
5. **Leanplum** をパートナーとして選択し連携名を入力してください。
6. 手順3で Leanplum アカウントからコピーした **App ID** と**Secret** を入力してください。

   [![leanplum_integration_af_dashboard.png](https://files.readme.io/def2f96ddade1e3dfb04cae1a379c66aa3501414cfd42d459b2adc53542fcfaa-31237653542673.png)](https://files.readme.io/def2f96ddade1e3dfb04cae1a379c66aa3501414cfd42d459b2adc53542fcfaa-31237653542673.png)
7. 連携先を保存すると、新規または既存のオーディエンスを接続できるようになります。

最大30分以内に、オーディエンスとそれに含まれるユーザーが Leanplum のオーディエンス管理画面に入力されます。

* AppsFlyerからLeanplumに同期されたオーディエンスは、Leanplumダッシュボードに接頭辞 **「APPSFLYER:」** が表示されます。

</Accordion>

<div id="moengage" />

<Accordion title="MoEngage">

<div id="prerequisite-2" />

> 🚧 **前提条件**
>
> オーディエンスをMoEngageに正常にアップロードするには：
>
> * <Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">AppsFlyer にユーザーごとに顧客ユーザー ID (CUID) を送信する</Anchor>必要があります。
> * CUID は、ユーザの**MoEngageユーザーID** と等しくなければなりません。

**MoEngageへのパートナー接続を作成するには：**

1. MoEngageダッシュボードにログインし、**設定 > API > 一般設定** に移動します。
2. **データAPI設定**セクションから、AppsFlyer オーディエンスで接続を構成するときに使用する次のキーをコピーします：

   * **データAPI ID**（<Image alt="A.png" src="https://files.readme.io/66b5bb0c4ea35f232f65dbc8dcbdfd6a91c12cf94915b19d33dae44834127058-31237653543313.png" width="16px" />は下の画像にあります）
   * **データAPIキー**（<Image alt="B.png" src="https://files.readme.io/f63914d3fefb55b627559c6e4c7d7cdef89239c0376a14c25c713a0a76dbad1b-31237653544337.png" width="16px" />は下の画像にあります）

   [![moengage_dashboard.png](https://files.readme.io/4c5acb849df14a4021c799d4bdb5ae49475446133068dd4fa6c7b00bef9b361b-31237653545617.png)](https://files.readme.io/4c5acb849df14a4021c799d4bdb5ae49475446133068dd4fa6c7b00bef9b361b-31237653545617.png)
3. ウェブブラウザのアドレスバーで、MoEngageダッシュボードのURLをチェックして、**MoEngageデータセンター**の番号を取得します。
   * MoEngage ダッシュボードのURLが https://dashboard-01.moengage.com の場合、アカウントがデータセンター1に割り当てられます。
   * URL が https://dashboard-02.moengage.com の場合、アカウントがデータセンター2に割り当てられます。
   * URL が https://dashboard-03.moengage.com の場合、アカウントがデータセンター3に割り当てられます。
4. AppsFlyerのオーディエンス画面にて、**連携先**タブへ進み、**+ 連携先を追加**をクリックしてください。
5. パートナーとして **MoEngage**を選択し、接続に名前を付けます。

   [![moengage_outgoing_connection.png](https://files.readme.io/fbeac3be05fd3a7f64db3992981e086de86954392f33a8331f09b320ce073718-31237648147089.png)](https://files.readme.io/fbeac3be05fd3a7f64db3992981e086de86954392f33a8331f09b320ce073718-31237648147089.png)
6. 手順 2 で MoEngage アカウントからコピーした**データAPI ID**と**データAPIキー**を入力します。
7. 手順 3 で決定した MoEngage **データセンター** を選択します。
8. 連携先を保存すると、新規または既存のオーディエンスを接続できるようになります。

AppsFlyerからMoEngageに同期されたオーディエンスは、MoEngageダッシュボードで <Anchor target="_blank" href="https://help.moengage.com/hc/en-us/articles/206528613-Custom-Segments">カスタムセグメント</Anchor> として利用できるようになります。

</Accordion>

<div id="slack" />

<Accordion title="Slack">

AppsFlyerは公開SlackチャンネルにデバイスIDのCSVファイルをアップロードします。

**オーディエンスをSlackに接続**：

1. AppsFlyerにて、**オーディエンス** > **連携先**へ進みます。
2. **+ 新しい連携先**をクリックします。
3. **連携名**を入力してください。
4. **Slack**を選択してください。
5. **Slackに追加**をクリックします。
6. Slackの認証画面にて、関連する**Slack Team**を選択します。
7. パブリック**チャネル**を選択します。
8. **保存**をクリックしてください。  
   連携プロセスが完了し、オーディエンスがアップロードされると、選択したチャンネルにデバイスIDを含むCSVファイルが表示されます。

</Accordion>

<div id="snapchat" />

<Accordion title="Snapchat">

**AudiencesをSnapchatに接続**

1. AppsFlyerにて、**オーディエンス** > **連携先**へ進みます。
2. **+ 新しい連携先**をクリックします。
3. **連携名**を入力してください。
4. **Snapchat**を選択します。
5. **Snapchatへログイン**をクリックします。
6. **Organization** と **Ad account**を選択します。
7. **保存**をクリックしてください。  
   オーディエンスはアップロード後24時間後にSnapchatの管理画面に表示されます。

<div id="note-1" />

> 📘 **注意**
>
> Snapchatは見慣れないデバイスIDを差し引くため、オーディエンス数が少なくなる可能性があります。

</Accordion>

<div id="tapjoy" />

<Accordion title="Tapjoy">

**Tapjoyにオーディエンスを連携：**

1. Tapjoyアカウントマネージャーから**パートナーID** を入手してください。
2. Tapjoyの **App Settings** ページから **Publisher Reporting API Key**を取得します。

   [![](https://files.readme.io/4aee504ce72061784c47b5bb84ac7e2bf73bf7c7dcb5b78ef83fb11e807a366a-31237653547665.png)](https://files.readme.io/4aee504ce72061784c47b5bb84ac7e2bf73bf7c7dcb5b78ef83fb11e807a366a-31237653547665.png)
3. AppsFlyerにて**オーディエンス**を開きます。オーディエンスを選択し、**連携先**タブへ進んでください。
4. **+パートナー接続を追加**をクリックしてください。
5. **連携名**を入力してください。
6. **Tapjoy**を選択してください。

   **Tapjoy Partner ID** と **Publisher Reporting API Key**を入力します。
7. Tapjoyのリストタイプを選択します：
   * Denylist
   * App suppression
8. 必要に応じて、**Tapjoy app ID** と **Tapjoy offer ID** を入力します。
9. **保存** をクリックしてください。

</Accordion>

<div id="tiktok-for-business" />

<Accordion title="TikTok for Business">

**前提条件：**

* <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=12791">TikTok for Business アカウント所有者、アドミン、またはアカウントオペレーター</Anchor> のTikTok広告アカウント権限が必要です。

**オーディエンスをTikTokに接続：**

1. TikTok for Businessログイン認証情報をTikTok アカウントマネージャーから取得します。
2. AppsFlyerにて、**オーディエンス** > **連携先**へ進みます。
3. **+ 新しい連携先**をクリックします。
4. **連携名**を入力してください。
5. **TikTok**を選択してください。
6. **Log in to TikTok For Business**をクリックしてください。  
   開発者向けの TikTok for Business 画面が開きます。
7. **TikTok for Business**にて、認証アカウントを選択します。
8. **同意する**をクリックします。  
   数秒後、AppsFlyer オーディエンス画面が表示されます。
9. **保存**をクリックしてください。

</Accordion>

<div id="mytarget" />

<Accordion title="VK Ads">

**オーディエンスをVK Adsに接続するには：**

1. AppsFlyerにて、**オーディエンス** > **連携先**へ進みます。
2. **+ 新しい連携先**をクリックします。
3. **連携名**を入力してください。
4. **VK Ads**を選択します。
5. **VK Adsにログイン**をクリックします。
6. 広告アカウントを選択します。
7. **保存**をクリックしてください。

</Accordion>

<div id="x-formerly-twitter" />

<Accordion title="X Ads (formerly Twitter Ads)">

**オーディエンスをX Adsへ接続するには：**

1.AppsFlyer管理画面 左メニュー **エンゲージメント** > **Audiences** > **接続**へ移動します。  
2.**+ 新しい接続**をクリックします。   
3.**X Ads**を検索し、パートナー名フィールドで選択します。  
4. 連携先の名前を入力してください。以前にパートナー接続を作成する際に使用されていない新しい名前である必要があります。  
5.**X Adsでログイン**をクリックしてください。  
6. ログインして、希望するビジネスアセットとXの広告アカウントを選択します。  
7. Xと共有するために承認したユーザー識別子を選択します。  
8. **保存**をクリックしてください。  
接続が追加され、接続状況とともに**接続**タブに表示されます。

</Accordion>

<div data-zendesk-anchors="connecting-to-audiences-partners=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E6%8E%A5%E7%B6%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H8H2SWZKEFQ75XS6VK8F10MW=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E6%8E%A5%E7%B6%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H8H2SWZNFBN32QEVG80EX1BT=%E6%96%B0%E3%81%97%E3%81%84%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E5%8B%9F%E9%9B%86%E3%81%97%E3%81%A6%E3%81%84%E3%81%BE%E3%81%99 Adobe_Marketing_Cloud=adobe-audience-manager-aam 01ECF4ZD12TS7QA0NWS44222SJ=adobe-audience-manager-aam 01ECF4ZD13JNGX7NRKFEPQJCSX=amazon-s3 01ECF4ZD13AEW3SQX80YQZ00NR=%E6%B3%A8%E6%84%8F 01H8H2SWZNVYXWPPWHBQBSVWFC=braze using-a-braze-external-id-parameter=braze-external-id-%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E4%BD%BF%E7%94%A8 01H8H2SWZNFFSD1HZTJV3V1AJJ=braze-external-id-%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E4%BD%BF%E7%94%A8 using-the-cuid-field=cuid%E9%A0%85%E7%9B%AE%E3%81%AE%E4%BD%BF%E7%94%A8 01H8H2SWZN9BNV35XHD5RBZZZN=cuid%E9%A0%85%E7%9B%AE%E3%81%AE%E4%BD%BF%E7%94%A8 01ECF4ZD13Q7QE5C9M8ZS4R8ZG=criteo facebook_audiences=facebook 01ECF4ZD14ZZ19RQDQ8JWH9RTZ=facebook 01H8H2SWZPP1MJXH9EHQXVW1CW=google-ads 01ECF4ZD14JMJVRATZSNC539DQ=httpool 01H8H2SWZP5QRV6VXB9KTEQSPT=Kakao h_01K0PVJZR5E6ZJEANYCEP5K22K=leanplum h_01K0PVJZR5CC8DV4XHH0C15EC7=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6-1 01H8H2SWZPN1N4X4H2TRJZHRKN=moengage 01H8H2SWZP91437F31Y79KZ7Y9=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6-2 01ECF4ZD15QDRGHCNEA2VGTXBN=slack 01ECF4ZD15KXPJHBYXK6AT9J4M=snapchat 01ECF4ZD15QDZJTFZS9GE9XG3Z=%E6%B3%A8%E6%84%8F-1 tapjoy_audiences=tapjoy 01ECF4ZD15P9DFQYHPAY92TFXH=tapjoy 01ECF4ZD16DHBG3VBT769ZYGV9=tiktok-for-business 01ECF4ZD142S55XVX1RS7H5FQ2=mytarget h_01KK93G2SGT60VM6DW27XB30AK=x-formerly-twitter" />
