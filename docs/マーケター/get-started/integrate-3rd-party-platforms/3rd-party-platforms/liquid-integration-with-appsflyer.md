---
title: LiquidとAppsFlyerの連携
metadata:
  keywords:
    - Liquid
    - attribution data
    - integrated partner
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:36:06Z'
  edited_at: '2026-10-28T09:03:20Z'
  id: 207040626
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/207040626
---
> **概要：** AppsFlyerの連携済みパートナーであるLiquidは、IT部門に依頼することなく、キャンペーンや業務プロセスを自動化できます。高度なルールエンジンが、ユーザー行動と詳細な分析結果に基づいて処理を実行します。

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

## Liquidの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

### パートナーを有効化

**初めてこの画面を開いたとき**は、下にあるトグルをオンにする必要があります。［***パートナーを有効化***］をオンにすると、［連携］タブのパラメータを設定できるようになります。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>を参照してください。

### 一般設定

**APIトークン**

LiquidとAppsFlyerの接続には、固有のAPIトークンを使用します。まだ取得していない場合は、連携の設定を進める前にLiquidから取得するか、以下の手順で取得してください。

[![](https://files.readme.io/1479b1569af7d8fb95c9efd7beddf169369d92790721ad9f15f3fd1615973e0d-360002201405.png)](https://files.readme.io/1479b1569af7d8fb95c9efd7beddf169369d92790721ad9f15f3fd1615973e0d-360002201405.png)

### APIトークンの取得

Liquid管理画面にログインすると、APIトークンを確認できます。

* **Settings**アイコンをクリックします。
* 本番環境のAPIトークンをコピーします。
* Liquidから取得したAPP\_TOKENを入力します。

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にLiquidへポストバックを自動送信できます。このセクションで、ポストバックの送信を設定します。

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

アプリをダウンロードしたすべてのユーザーのポストバックをLiquidに送信するには、<strong>［すべてのパートナーまたはオーガニックのイベント］</strong>を選択します。送信しない場合は、<strong>［オフ］</strong>を選択します。

［**保存**］をクリックします。

この設定を保存すると、AppsFlyerはオーガニックと非オーガニックのすべてのインストールについて、次のデータをLiquidに送信し始めます。

* アプリトークン
* SDKで設定したcustomer\_user\_id
* メディアソース
* キャンペーン名

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Liquidでは、計測リンクは利用できません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

このパートナーとの連携では、コストデータには対応していません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益データには対応していません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

Liquidでは、権限の設定は利用できません。

</Accordion>

<div data-zendesk-anchors="h_01H9FKBW5QYQGZ7PNEJMHZ6H2R=%E9%87%8D%E8%A6%81 setting-up-liquid=liquid%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKBW5QMJTARZ6KZ41QT1BN=liquid%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKBW5QM601CMQ6Y2PNJ1HQ=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FKBW5RRYW1JTK2S9V4V6SA=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FKBW5RB52QQKVF5TMFVKKT=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A obtaining-the-api-token=api%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E5%8F%96%E5%BE%97 h_01H9FKBW5RCGHVJRJEBQW4KNGD=api%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E5%8F%96%E5%BE%97 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKBW5RVYXPEEFDG948P1XV=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKBW5RNH2BRV8S31DT8SWA=attribution-link-tab h_01H9FKBW5RRQZZC4YQNWGHQTW6=cost-tab h_01H9FKBW5R7TNN5YA5YP36EJ63=ad-revenue-tab h_01H9FKBW5RC55F56K3EMQBJGEK=permissions-tab" />
