---
title: Luna LabsとAppsFlyerの連携
metadata:
  keywords:
    - postbacks
    - integrated partner
    - Advertisers
    - Agencies
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
  created_at: '2021-04-21T15:51:20Z'
  edited_at: '2026-10-28T09:03:25Z'
  id: 360019465017
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/360019465017
---
> **概要：** Luna Labsは、プレイアブル広告と動画広告の作成、管理、最適化を一貫して行えるプラットフォームです。

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="setting-up-luna-labs" />

## Luna Labsの設定

**前提条件：** 連携の設定を始める前に、パートナーに問い合わせてアカウントを作成してください。

**新規の連携：**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。
2. 対象のアプリを選択します。
3. Luna Labsを検索し、<strong>［連携する］</strong>を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。 Luna Labsとの連携を利用している間は、オンにしておいてください。
5. 以下の説明に従い、該当するタブで設定を完了します。

**既存の連携の編集：**

AppsFlyerで、［**連携＞パートナー連携＞有効な連携**］タブに移動し、パートナーを検索して設定を変更します。

<div id="integration" />

## 連携

［連携］タブで設定します。その他のタブは無効です。

<div id="note" />

> 📘 **注意**
>
> Luna Labsは独自の計測リンクを使用しません。広告主のキャンペーンを配信しているアドネットワークからポストバックを受信します。 Luna Labsが受信するのは、自社のクリエイティブに関するポストバックのうち、パラメータと値`af_addpb=1`を含むものだけです。詳しくは、以下の説明を参照してください。

<div id="activate-partner" />

### パートナーを有効化

**初めて設定する場合**は、<strong>［パートナーを有効化］</strong>をオンにすると、［連携］タブのパラメータを設定できます。**パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります**。  
<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効化と無効化</Anchor>の詳細を確認してください。

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にLuna Labsへポストバックを自動送信できます。

**注意：** Luna Labsが受信できるのは、自社のクリエイティブに関するポストバックのみです。

**Luna Labsにポストバックを送信するには、次の設定を行います。**

1. Luna Labsと併せて利用しているアドネットワークが有効になっており、AppsFlyerと連携済みであることを確認します。
2. アドネットワークがAppsFlyerとLuna Labsに送信する計測リンクに、`af_addpb=1`パラメータを追加していることを確認します。  
   このパラメータにより、Luna Labsへのポストバック送信が有効になり、クリックがLuna Labsのクリエイティブから発生したことが伝わります。
3. <strong>［すべてのパートナーまたはオーガニックのイベント］</strong>を選択します。

たとえば、ad-network-Xが特定のアプリ（id1234567890）のキャンペーンを配信し、Luna Labsにポストバックを送信する場合、URLは次のようになります。

```http
https://app.appsflyer.com/id1234567890?pid=ad-network-X_int&af_siteid={ApplicationId}_{ApplicationName}&c={CampaignName}&af_adset={adgroup_name}&af_ad={CreativeName}&clickid={DynamicParameter}&af_addpb=1
```

<div data-zendesk-anchors="h_01H9FKCW1FJ2QCVVE6HEE640H9=%E9%87%8D%E8%A6%81 setting-up-luna-labs=luna-labs%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HJR5M5C0P759S4X5SSJCY501=luna-labs%E3%81%AE%E8%A8%AD%E5%AE%9A integration=%E9%80%A3%E6%90%BA h_01H9FKCW1FE6JCY5FAFF3Y4TGH=%E9%80%A3%E6%90%BA h_01H9FKCW1FNPCF1M7SRWTMNDCW=%E6%B3%A8%E6%84%8F activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FKCW1FV00605GYK498JZN9=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKCW1FGMA3FKAY5B9YCJVH=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF" />
