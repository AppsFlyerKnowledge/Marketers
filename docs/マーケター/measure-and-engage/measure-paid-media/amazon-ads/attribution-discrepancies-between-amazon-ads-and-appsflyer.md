---
title: Amazon 広告とAppsFlyerのアトリビューションの不一致
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-09-18T04:28:03Z'
  edited_at: '2026-10-14T09:20:50Z'
  id: 28461159218449
  locale: ja
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/ja/articles/28461159218449
---
> **概要:** Amazon 広告とAppsFlyerのアトリビューションモデルの違いについて説明します。

## 概要

モバイルユーザー獲得エコシステムにおける重要な2つのプレーヤーとして、Amazon 広告とAppsFlyerはそれぞれ異なるアトリビューションモデルを使用しています。これにより、Amazon 広告ダッシュボードとAppsFlyerダッシュボードの間に矛盾が生じる場合があります。私たちはこれらの不一致を最小限に抑えるためにAmazon 広告と緊密に連携していますが、広告主は潜在的な原因を認識しておく必要があります。

## アトリビューションモデルの違い

以下の表は、Amazon 広告とAppsFlyerダッシュボード間に不一致が生じる可能性のある理由を示しています。

| 原因 | Amazon 広告マネージャー | AppsFlyer |
| --- | --- | --- |
| <span id="clickthrough-attribution-lookback-window"></span>クリックスルーアトリビューションルックバック期間 | デフォルトの期間は14日間です。現在、この期間は設定できません。 | デフォルトの期間は7日間です。期間は1～30日間で設定できます。必ずAmazon 広告のアトリビューション期間に合わせてください。 |
| <span id="viewthrough-attribution-lookback-window"></span>ビュースルーアトリビューションルックバック期間 | デフォルトの期間は14日間です。現在、この期間は設定できません。 | デフォルトの期間は1日です。期間は1～30日間で設定できます。必ずAmazon 広告のアトリビューション期間に合わせてください。 |
| <span id="multichannel-source-attribution"></span>マルチチャネルソースアトリビューション | Amazon 広告は、他のメディアソースに関係なく、インストールを自己計測します。 | AppsFlyerはラストクリックアトリビューションを使用します。  <br /> <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">AppsFlyerアトリビューションモデル</Anchor>の詳細はこちらをご覧ください。 |
| <span id="different-timezones"></span>異なるタイムゾーン | Amazon 広告のタイムゾーン（日付範囲の横に表示）は調整できません。広告アカウント作成時に設定されました。 | AppsFlyerのデフォルトのアプリタイムゾーンはUTC+0です。Amazon 広告で定義されたタイムゾーンと一致させるには、<Anchor target="_blank" href="/marketers/ja/docs/app-settings#localization-time-zone">アプリ設定ページ</Anchor>でアプリに設定されているタイムゾーンを変更します。 |

## 不一致を減らす

アトリビューションモデルの違いがあるものの、場合によっては不一致を軽減できることがあります。

### クリックスルーとビュースルー計測

AppsFlyerはクリックスルーとビュースルーのアトリビューションをサポートしています。Amazon 広告とAppsFlyer間の不一致を減らすため、クリックスルーとビュースルールックバック期間がAmazon 広告で定義されているものと一致していることを確認してください。

> 📄 **例**
>
> 例えば、Amazon広告のクリック ルックバック期間が、AppsFlyerではアプリcom.greatappに対して1日に設定されているのに対し、Amazon広告ではデフォルトの7日に設定されているとします。Amazon広告でGreatappの広告をクリックしたユーザーが2〜7日後に初めてアプリを起動した場合、AppsFlyerではこれらのユーザーはオーガニックユーザーとして扱われますが、Amazon広告ではこれらのユーザーを自己レポートします。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01J81NN4J4A1KWBXJQD9SM2AWH=%E6%A6%82%E8%A6%81 differences-in-attribution-models=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%A2%E3%83%87%E3%83%AB%E3%81%AE%E9%81%95%E3%81%84 h_01J81NN4J4WSJBFHBARKTQ9JG5=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%A2%E3%83%87%E3%83%AB%E3%81%AE%E9%81%95%E3%81%84 reducing-discrepancies=%E4%B8%8D%E4%B8%80%E8%87%B4%E3%82%92%E6%B8%9B%E3%82%89%E3%81%99 h_01J81NN4J4EJQH47YJF0H5M97G=%E4%B8%8D%E4%B8%80%E8%87%B4%E3%82%92%E6%B8%9B%E3%82%89%E3%81%99 clickthrough-and-viewthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%81%A8%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC h_01J81NN4J4X6V3XWRZWNDJ14PV=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E3%81%A8%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC h_01J81NN4J4NC0SK4QRTQZRJS0F=%E4%BE%8B" />
