---
title: X Ads（旧Twitter Ads）設定ガイド—概要
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:31:36Z'
  edited_at: '2026-10-14T09:26:47Z'
  id: 4410464316049
  locale: ja
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/ja/articles/4410464316049
---
> **概要：** X AdsアカウントとAppsFlyerを連携する背景について説明します。

<Image alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="167px" />

## X広告を使用したモバイルアプリのプロモーション

X広告モバイルアプリプロモーションは、X上でアプリの広告を掲載する方法です。広告主は、インストールやアプリエンゲージメント、ディープリンクを促す魅力的なデザインのアプリカードを使用して、モバイルアプリをプロモーションできます。アプリユーザーは、Xタイムラインから直接手軽にアプリをインストールし、使い始めることができます。

## X広告のエンドユーザープライバシー

Twitterユーザーは広告主との共有する情報をコントロールできます。

* 広告主へのエンゲージメント情報の共有を無効に設定しているユーザーは、Twitter広告経由のインストールやアプリ内イベントは、ローデータから除外されますが、Twitterへの成果は計測されます。
* 集計アトリビューションデータは、AppsFlyerに正しく反映され、X Adsポリシーには影響されません。
* その結果、Twitterの集計データとローデータレポートは相関しません。

2021年7月31日より、Twitter Advanced Mobile Measurement（AMM）プログラムに参加していない広告主は、全てのTwitter MACTユーザーレベルデータの受信を停止します。

AMMプログラムを通じて、広告主は、データが測定目的にのみ使用されていることを確認する監査を行う権利をTwitterに付与することで、より完全なユーザーレベルのデータを受け取ることができます。これは、適用されるデータ保護法および業界の一般的な慣行に沿ったものです。  
**AMMプログラムに参加するには：** > Mobile App, Conversion Tracking & Audience Manager へ進み、**Advanced Mobile Measurement Program Agreement Form**を選択してください。

なお、AMMプログラムに参加する前に受け取ったユーザーレベルのデータは、エクスポートできません。

より詳細な情報については、Twitterアカウントマネージャーにお問い合わせください。

## X広告とAppsFlyerのSKAN相互運用

X Adsは、SKAdNetworkのポストバックデータを専用のAPIで送信します。X AdsからのSKANデータは<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN計測数値</Anchor>に表示されます。

X Adsは、次のデータ項目を使用してSKANポストバックを強化します。

* Campaign name
* Campaign ID
* Adset name
* Adset ID

<div data-zendesk-anchors="mobile-app-promotion-on-twitter=x%E5%BA%83%E5%91%8A%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01H9QR6TH7M0H5YMXRWVVAYRK9=x%E5%BA%83%E5%91%8A%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 twitter-user-privacy=x%E5%BA%83%E5%91%8A%E3%81%AE%E3%82%A8%E3%83%B3%E3%83%89%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC h_01H9QR6TH74R50K00H7FYN61KC=x%E5%BA%83%E5%91%8A%E3%81%AE%E3%82%A8%E3%83%B3%E3%83%89%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC twitter-ads-and-appsflyer-skan-interoperation=x%E5%BA%83%E5%91%8A%E3%81%A8appsflyer%E3%81%AEskan%E7%9B%B8%E4%BA%92%E9%81%8B%E7%94%A8 h_01H9QR6TH74PKBGM5RC4M118GE=x%E5%BA%83%E5%91%8A%E3%81%A8appsflyer%E3%81%AEskan%E7%9B%B8%E4%BA%92%E9%81%8B%E7%94%A8" />
