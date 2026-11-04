---
title: ユーザーの所在地の判定
metadata:
  keywords:
    - IPs
    - Advertisers
    - Agencies
    - Ad Networks
    - ip
    - digital element
    - zip
    - dim
    - zip code
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2019-01-29T12:52:11Z'
  edited_at: '2026-10-28T09:07:47Z'
  id: 360000847378
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/360000847378
---
> **概要：** ユーザーの所在地は、デバイスのIPアドレスを、市区町村、州・都道府県、国などのおおよその所在地に対応付けて判定します。ユーザーの所在地は、クリエイティブの選択、キャンペーンのコスト、エンゲージメント、ユーザーの質に影響します。

![5888ResolveIpAddress_us-en.png](https://files.readme.io/166e48fb0bb90b627bc51e29b53a556b71939749ab3e5eadff7d6edf0f0dfd25-360011758517.png)

<div id="determining-user-location" />

## ユーザーの所在地の判定方法

デバイス上のユーザーの行動が、AppsFlyerに報告されます。これらの行動（イベント）には、デバイスのIPアドレスなど、さまざまなデータフィールドが含まれます。

VPN、iOS 15のプライベートリレーなどの仕組み、SKANポストバックのプロキシサーバーによって、デバイスの実際のIPアドレスが隠される場合があります。その場合、本記事で説明するIPアドレスから所在地への変換結果が不正確になったり、誤解を招いたりする可能性があります。 AppsFlyer側でこれを制御することはできません。

AppsFlyerは、IP位置情報の世界的な大手企業である<Anchor target="_blank" href="http://www.digitalelement.com/">Digital Element</Anchor>のデータを使用して、IPアドレスを所在地の情報に変換します。

* 所在地の情報には、以下が含まれる場合があります。
  * 国・地域：ISO 3166の2文字コード（alpha-2）を使用します。国・地域を特定できない場合は、EU（ヨーロッパ）またはAS（アジア）を使用します。
  * 市区町村：市内の地区や近隣エリアに対応する場合があり、実際の市の行政区域と直接一致するとは限りません。
  * DMA：<Anchor target="_blank" href="https://www.nielsen.com/us/en/solutions/nielsen-global-connect/">Nielsen</Anchor>がテレビ視聴者数を計測するために定める市場地域や地理的エリアです。<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012539677">都市圏コードのCSVファイル。</Anchor>
  * 地域：地理的な地域または大陸です。
  * 州・都道府県：<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012615238">各地域の州名をまとめたCSVファイル</Anchor>を参照してください。この表のregionフィールドを使用します。最大3文字の英字または数字で構成されます。
  * 郵便番号。
* IPアドレスと所在地の対応表は、定期的に更新されます。通常は週次で更新されます。

**例：IPアドレスから所在地への変換**![IPTables_us-en.png](https://files.readme.io/0d7d4d4190face77e18476bdb9e47fdd26ed62ab91cd641f76f728d9a7c8d005-360011787798.png)

<div id="note-regarding-the-united-kingdom-uk" />

> 📘 **英国（UK）に関する注意**
>
> <Image alt="blobid0.png" src="https://files.readme.io/33ed45ea49e3308e17a237400ea6c6e9d33c495a9c83197041fdae282f9c65a4-360006637538.png" width="62px" />
>
> * 管理画面では、英国をUKというコードで表します。
> * 英国のISO 3166コードはGBです。 UKは、ISOによって英国用に予約されていますが、正式に割り当てられたコードではありません。

<div id="location-discrepancies" />

### 所在地の判定結果の差異

他のプラットフォームもDigital Elementを使ってIPアドレスから所在地を判定していても、AppsFlyerとは異なる結果になる場合があります。差異が生じる主な理由は以下のとおりです。

* **データベースの更新：** アトリビューションを高速に処理するため、AppsFlyerは自社システム内でIPアドレスを所在地データに変換しています。 AppsFlyerはDigital Elementから世界全体の対応データを定期的に取得しており、リアルタイムでは取得していません。 AppsFlyerと他のプラットフォームでDigital Elementのデータを取得するタイミングが異なると、判定結果に差異が生じる場合があります。
* **ISPによる変更：** インターネットサービスプロバイダー（ISP）がIPアドレスの割り当てを変更するため、Digital Elementのデータベースも頻繁に変わります。
* **プランや方法の違い：** Digital Elementは、位置情報をどこまで細かく特定する必要があるかに応じて、複数のプランを提供しています。他のプラットフォームが異なるDigital Elementのプランや、異なるデバイスIDの判定方法を使用していると、結果が異なる場合があります。
* **プロキシやVPN：** ユーザーがVPNやプロキシを使用している場合、実際のIPアドレスは把握できません。 VPNやプロキシのアドレスに基づいて所在地が判定されます。
* **詳しく見る：** <Anchor target="_blank" href="https://www.digitalelement.com/blog/the-tricky-science-behind-ip-geolocation/">IP位置情報の判定を支える複雑な技術</Anchor>

<div data-zendesk-anchors="determining-user-location=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E6%89%80%E5%9C%A8%E5%9C%B0%E3%81%AE%E5%88%A4%E5%AE%9A%E6%96%B9%E6%B3%95 h_01HDP1SA5YV96YMPPFGN9H6RGE=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E6%89%80%E5%9C%A8%E5%9C%B0%E3%81%AE%E5%88%A4%E5%AE%9A%E6%96%B9%E6%B3%95 h_01HDP1SA5YR7JWDHX2BNXXTKT9=%E8%8B%B1%E5%9B%BDuk%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E6%B3%A8%E6%84%8F location-discrepancies=%E6%89%80%E5%9C%A8%E5%9C%B0%E3%81%AE%E5%88%A4%E5%AE%9A%E7%B5%90%E6%9E%9C%E3%81%AE%E5%B7%AE%E7%95%B0 h_01HDP1SA5YNA9N4P9AD4RHWS0J=%E6%89%80%E5%9C%A8%E5%9C%B0%E3%81%AE%E5%88%A4%E5%AE%9A%E7%B5%90%E6%9E%9C%E3%81%AE%E5%B7%AE%E7%95%B0" />
