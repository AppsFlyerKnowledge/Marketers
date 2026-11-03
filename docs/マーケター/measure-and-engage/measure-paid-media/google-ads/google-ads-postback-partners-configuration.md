---
title: Google Adsポストバックパートナーの設定
metadata:
  keywords:
    - postbacks
    - Integration
    - Advertisers
    - Agencies
    - google ads
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
  created_at: '2021-11-16T09:36:56Z'
  edited_at: '2026-10-28T09:15:36Z'
  id: 4411047077905
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/4411047077905
---
> **概要：** Google Adsキャンペーンの運用を支援するGoogle Adsポストバックパートナーを有効にします。

BidalgoやAdquantなど、**Google Adsポストバックパートナー**と呼ばれるパートナーは、代理店に似た役割を担います。広告主である顧客のGoogle Adsキャンペーンの運用を支援しますが、Google Adsのコンバージョンのポストバックを受信する必要があります。

これらのGoogle Adsポストバックパートナー（GAPP）は、広告主が直接獲得したGoogle Adsのインストールや、他の代理店が獲得したインストールのポストバックも受信できます（[ユースケース](/docs/google-ads-postback-partners-configuration#google-adsポストバックパートナーのユースケース)を参照）。 GAPPは、ポストバックの情報を使用して、そのアプリのGoogle Adsキャンペーンを最適化できます。

> 🚧 **重要！**
>
> AppsFlyerでは、インストールやイベントの成果がGoogle Adsポストバックパートナーに紐づくことは**ありません**。

ポストバックを送信するには、広告主がAppsFlyerで有効なGoogle Adsアカウントを<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers">設定</Anchor>し、さらに対象のGAPPもAppsFlyerで設定する必要があります。

AppsFlyerと連携しているその他のGAPP：Blackbox、Appreciate、Marin Software、Miramedia、Mpbisummer、Protonads、Springrain。

## Google Adsポストバックパートナーの設定

1. AppsFlyerのサイドメニューから、［**コラボレーション**>**アクティブな連携**］を選択します。

2. 利用するGAPPの名前を検索ボックスに入力し、ドロップダウンリストから選択します。

> 👍 **ヒント**
>
> 検索ボックスに「Google Ads」と入力してEnterキーを押すと、GAPPのリストが表示されます。

3. 対象のGAPPをクリックして連携設定を開きます。

4. **Google Ads**アカウントで、お客様IDをハイフンなしでコピーします。

![](https://files.readme.io/7afd536d06b1aca68744a83925ecac86fcef4cc47225826af20120f128da004f-21414601345681.png)

5. ［**Google Adsのお客様ID**］欄に、その番号を貼り付けます。

6. <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">アプリ内イベントポストバックのセクション</Anchor>を設定します。

7. ［**保存**］をクリックします。

> 📘 **重要な注意事項**
>
> * Google Adsの計測を無効にすると、GAPPへのポストバックの送信も停止します。
> * CIDをカンマで区切ることで、ポストバックの送信対象として複数の広告アカウント（CID）を設定できます（ステップ5）。
>
>   ![zds_Agency_multiple.png](https://files.readme.io/36112b9a08ca1e6a2150523e1ec39eda5c28a4be826e9f776f5dbd7b1d0c5378-21414553418897.png)
> * 複数のGAPPを利用するには、GAPPごとに別のGoogleアカウントでキャンペーンを配信してください。 GAPPを別のGAPPに切り替える場合は、AppsFlyerで以前のGAPPの設定を無効にしてください。

## Google Adsポストバックパートナーのユースケース

<div id="use-case-1-advertiser-postbacks-only" />

<Accordion title="ユースケース1：広告主のポストバックのみ">

広告主がGoogle Adsキャンペーンを配信しており、自社のGoogle AdsアカウントのトラフィックをGAPP Xに送信したい場合。

1. 広告主がGoogle Adsを<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers">設定</Anchor>します。
2. 広告主がGAPP X - Google Adsを[設定](/docs/google-ads-postback-partners-configuration#google-adsポストバックパートナーの設定)します。

広告主は、GAPP X - Google Adsの設定に、自社のすべてのCID（広告アカウントID）を入力する必要があります。

</Accordion>

<div id="use-case-2-active-agency-with-advertiser-postbacks-only" />

<Accordion title="ユースケース2：代理店も配信し、広告主のポストバックのみを送信">

広告主と代理店の両方がGoogle Adsキャンペーンを配信しており、広告主が自社のトラフィックのみをGAPP Xに送信したい場合。

1. 広告主がGoogle Adsを<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers">設定</Anchor>します。
2. 代理店がGoogle Adsを<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-agencies">設定</Anchor>します（自社のトラフィックを代理店の成果として計測するため）。
3. 広告主がGAPP X - Google Adsを[設定](/docs/google-ads-postback-partners-configuration#google-adsポストバックパートナーの設定)します。

広告主は、GAPP X - Google Adsの設定に、自社のCIDのみを入力する必要があります。

</Accordion>

<div id="use-case-3-active-advertiser-with-agency-postbacks-only" />

<Accordion title="ユースケース3：広告主も配信し、代理店のポストバックのみを送信">

広告主と代理店がGoogle Adsキャンペーンを配信しており、代理店が自社のトラフィックのみをGAPP Xに送信したい場合。

1. 広告主がGoogle Adsを<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers">設定</Anchor>します。
2. 代理店がGoogle Adsを<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-agencies">設定</Anchor>します。
3. 代理店がGAPP X - Google Adsを[設定](/docs/google-ads-postback-partners-configuration#google-adsポストバックパートナーの設定)します。

代理店は、GAPP X - Google Adsの設定に、自社のCIDのみを入力する必要があります。

</Accordion>

<div id="use-case-4-advertiser-agency-postbacks" />

<Accordion title="ユースケース4：広告主と代理店のポストバック">

広告主と代理店がGoogle Adsキャンペーンを配信しており、両者がそれぞれのトラフィックをGAPP Xに送信したい場合。

1. 広告主がGoogle Adsを<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers">設定</Anchor>します。
2. 代理店がGoogle Adsを<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-agencies">設定</Anchor>します。
3. 広告主が、自社のCIDについてGAPP X - Google Adsを[設定](/docs/google-ads-postback-partners-configuration#google-adsポストバックパートナーの設定)します。
4. 代理店が、自社のCIDについてGAPP X - Google Adsを[設定](/docs/google-ads-postback-partners-configuration#google-adsポストバックパートナーの設定)します。

広告主と代理店では、異なるCIDを使用する必要があります。

</Accordion>

## GAPPで利用可能なパラメータ

**ポストバックの内容は、GAPPとAppsFlyerとの初期連携に依存しており**、広告主の設定とは関係ありません。そのため、GAPPによってポストバックパラメータの定義が異なる場合があります。

たとえば、`campaign type`、`city`、`carrier`、`ad_type`などのパラメータが、GAPPのポストバックに含まれるかどうかはGAPPによって異なります。

GAPPのポストバックパラメータには、次の2つの情報源があります。

1. **AppsFlyerのマクロ**：AppsFlyerのポストバックで利用可能なすべてのマクロの詳細は、<Anchor target="_blank" href="/partners/ja/docs/postback-macros-for-ad-networks">こちら</Anchor>を参照してください。
2. **Googleのレスポンス**：Google Adsに成果が紐づくインストールが発生するたびに、AppsFlyerはGoogleから関連情報を受信します。以下は、AppsFlyerがGoogle Adsから受信し、GAPPのポストバックで利用可能なパラメータです（各パラメータの詳細は<Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs#sample_responses">こちら</Anchor>を参照）。
   * 広告イベントID
   * キャンペーンID
   * キャンペーン名
   * キャンペーンの種類
   * 外部お客様ID（CID）
   * ネットワークタイプ
   * ネットワークのサブタイプ
   * タイムスタンプ
   * 動画ID
   * 広告グループID
   * クリエイティブID
   * キーワード
   * マッチタイプ
   * プレースメント
   * インタラクションの種類
   * 広告タイプ
   * コンバージョン指標
   * 地域

> 📘 **注意**
>
> 利用できる情報は、GoogleからAppsFlyerに送信される情報のみです。何らかの理由でGoogleがインストールの情報を送信しない場合、AppsFlyerからGAPPにその情報を渡すことはできません。

<div data-zendesk-anchors="h_01HKA1HTJ4VW4YRXMSVG7WBTJM=%E9%87%8D%E8%A6%81 google-ads-postback-partner-setup=google-ads%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKA1HTJ5BE5EVQJ2T9HSHKQC=google-ads%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKA1HTJ5BJTTS15QC44M63B2=%E3%83%92%E3%83%B3%E3%83%88 h_01HKA1HTJ5KSD1CVJ4FKDSATJX=%E9%87%8D%E8%A6%81%E3%81%AA%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85 google-ads-postback-partners-use-cases=google-ads%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B9%E3%82%B1%E3%83%BC%E3%82%B9 h_01HKA1HTJ5DX0Z2ZCGX07EX15F=google-ads%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B9%E3%82%B1%E3%83%BC%E3%82%B9 h_01HKA1HTJ5T2XJJ4M9YZ1S52SF=use-case-1-advertiser-postbacks-only h_01HKA1HTJ5EFADYE33NQVP1NBQ=use-case-2-active-agency-with-advertiser-postbacks-only h_01HKA1HTJ5H4KK2M94QY0VFRSA=use-case-3-active-advertiser-with-agency-postbacks-only h_01HKA1HTJ537CYXEBQRCV5FSPK=use-case-4-advertiser-agency-postbacks available-parameters-for-gapps=gapp%E3%81%A7%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AA%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HKA1HTJ5H0SXEMBVB6K2EZ91=gapp%E3%81%A7%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AA%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HKA1HTJ55XWMX90KSYTGFB6C=%E6%B3%A8%E6%84%8F" />
