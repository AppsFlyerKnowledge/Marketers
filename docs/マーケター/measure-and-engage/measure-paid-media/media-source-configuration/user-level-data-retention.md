---
title: ユーザーレベルデータの保持
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - SRN
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
    - Ad Networks
  created_at: '2020-02-23T15:35:57Z'
  edited_at: '2026-10-14T09:22:12Z'
  id: 360006091197
  locale: ja
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ja/articles/360006091197
---
> **概要：** データの保持期間およびユーザーレベルデータ（ローデータ）の利用に関するポリシーは、AppsFlyer、関連法令、およびSRN（以下「**パートナー**」）の利用規約に基づいて決定されます。

<div id="caution" />

> ❗️ **注意**
>
> 本記事に記載されているデータ制限に関する説明は、情報提供のみを目的としています。  *本記事の内容は、いかなる意味でも法的助言を構成するものではありません。お客様の参考および利便性のために提供される情報です。*

<div id="data-retention-and-deletion-obligations" />

## データの保持および削除に関する義務

AppsFlyerは、アプリ、パートナー、その他のソースからユーザーレベルデータを受信します。

<div id="availability-of-user-level-data-to-advertisers" />

### 広告主が利用できるユーザーレベルデータ

通常、契約しているパッケージにローデータが含まれている場合、ユーザーレベルデータはローデータレポートツールを通じて広告主に提供され、90日間アクセスできます（<Anchor target="_blank" href="/marketers/ja/docs/data-availability-windows">データの利用可能期間</Anchor>を参照）。また、場合によっては<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">ローデータに制限が適用</Anchor>されることがあります。

<div id="data-retention" />

### データ保持期間

AppsFlyerがユーザーレベルデータを保持する期間には制限があります。ローデータの保持期間は、データの提供方法やパートナー側の要件によって異なります。一般的な保持期間は以下のとおりです：

* **ユーザーレベルのローデータ**： 連携タイプおよびパートナー側の要件に基づいて保持期間を決定
* **集計データ**： 最長25か月間保持

保持期間が終了するまでは、ユーザーのイベントは、そのユーザーを獲得したメディアソースに紐づけてアトリビューションされます。保持期間の終了後は、ユーザーのイベントは**オーガニックとして計測されます。**

保持期間は、以下に基づいて決定されます。

* <Anchor target="_blank" href="https://www.appsflyer.com/legal/processing-customer-data/">AppsFlyerサービスプライバシーポリシー</Anchor>
* 法令上の指示、要件、または許可
* パートナーの利用規約、および以下の表に記載されている保持期間

以下の点にご注意ください。

* データへのアクセス可能期間とデータ保持期間は、異なる場合があります。
* AppsFlyerは、場合によってアクセス可能期間を延長することがあります。
* データ保持期間は、ユーザーを獲得したメディアソースごとに異なる場合があります。
* 一部のユーザーレベルデータは、<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">制限付きメディアソース（restricted）</Anchor>にアトリビューションされる場合があります。この場合、ローデータにはアトリビューションデータが含まれません。主に以下の場合に該当します。
  * パートナーのデータ共有ポリシーによる制限
  * <Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">高プライバシー一括設定</Anchor>が有効になっている場合

<div id="partner-data-retention-periods" />

#### パートナー別のデータ保持期間

| SRN / パートナー | パートナーID (PID) | インストール後、データを削除するまでの期間（月） |
| --- | --- | --- |
| Amazon広告 | amazondsp\_int | 12 |
| Apple Search Ads | Apple Search Ads | 制限なし |
| Discord | discord\_int | 6 |
| DV360 | dv360\_int と doubleclick\_int | 6 |
| Google広告* | googleadwords\_int（すべてのチャネル） | 6 |
| Hotstar | hotstar\_int | 6 |
| Meta広告* | facebook\_int（すべてのチャネル） | 6 |
| Microsoft | microsoftdisplay\_int, bingsearch\_int | 13 |
| Pinterest | pinterest\_int | 6 |
| Samsung DSP | samsungdsp\_int | 3 |
| Snapchat* (<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">TOS</Anchor>) | snapchat\_int | 6 |
| TikTok for Business* | tiktokglobal\_int | 13 |
| X広告（旧：Twitter広告） | twitter\_int | 3 |

<div id="note" />

> 📘 **注意*：**
>
> SRNについて、上記の表に記載されている保持期間が適用されるのは、SRNから直接提供されたデータのみです。AppsFlyerのW2Aアトリビューションリンク（`googleads_int`、`metaweb_int`、`tiktokweb_int`、`snapweb_int`）を介して行われたアトリビューションには適用されません。

<div data-zendesk-anchors="h_01H95FY07TRAAD3K0A0TSG3RB6=%E6%B3%A8%E6%84%8F data-retention-and-deletion-obligations=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E4%BF%9D%E6%8C%81%E3%81%8A%E3%82%88%E3%81%B3%E5%89%8A%E9%99%A4%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E7%BE%A9%E5%8B%99 h_01H95FY07TABPC769R7TYGY5DD=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E4%BF%9D%E6%8C%81%E3%81%8A%E3%82%88%E3%81%B3%E5%89%8A%E9%99%A4%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E7%BE%A9%E5%8B%99 availability-of-userlevel-data-to-advertisers=%E5%BA%83%E5%91%8A%E4%B8%BB%E3%81%8C%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%83%AC%E3%83%99%E3%83%AB%E3%83%87%E3%83%BC%E3%82%BF h_01H95FY07T2Q9QAGW5A5S6KP6J=%E5%BA%83%E5%91%8A%E4%B8%BB%E3%81%8C%E5%88%A9%E7%94%A8%E3%81%A7%E3%81%8D%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%83%AC%E3%83%99%E3%83%AB%E3%83%87%E3%83%BC%E3%82%BF data-retention=%E3%83%87%E3%83%BC%E3%82%BF%E4%BF%9D%E6%8C%81%E6%9C%9F%E9%96%93 h_01H95FY07TXS63FVDJC2NEFXYC=%E3%83%87%E3%83%BC%E3%82%BF%E4%BF%9D%E6%8C%81%E6%9C%9F%E9%96%93 partner-data-retention-periods=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E5%88%A5%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E4%BF%9D%E6%8C%81%E6%9C%9F%E9%96%93 h_01H95FY07TZ4N0RRJRGJ6FN2EK=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E5%88%A5%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E4%BF%9D%E6%8C%81%E6%9C%9F%E9%96%93 h_01KRKAWSHH2WFZT9Q5M0FSBBAB=%E6%B3%A8%E6%84%8F-1" />
