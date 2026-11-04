---
title: AppsFlyerサーバーのIPアドレス範囲（許可リストへの登録）
metadata:
  keywords:
    - whitelisting
    - AppsFlyer
    - IPs
    - Advertisers
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Ad Networks
  created_at: '2015-12-24T11:30:11Z'
  edited_at: '2026-10-28T09:13:57Z'
  id: 207447093
  locale: ja
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ja/articles/207447093
---
> **概要：** AppsFlyerから外部へのAPIリクエストに使用するIPアドレスを説明します。

<div id="appsflyer-server-ip-address-ranges" />

## AppsFlyerサーバーのIPアドレス範囲

記載されているIPアドレスは、AppsFlyerが管理し、自社の用途に使用するものです。このリストは、処理能力や運用上の要件に応じて変更されることがあります。リストの変更頻度をできる限り抑えるよう努めています。

AppsFlyerのAPIは、広告主やパートナーにアトリビューションとレポートのサービスを提供します。これらのサービスには、次のものが含まれます。

* ポストバックの送信
* Push APIメッセージの送信

ファイアウォールやプロキシサーバーなど、ネットワーク境界の機器を使用している場合は、この<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTzJqwOhIkSV0Mbnu4DZOx2eWKAd8OPRUNCu2REjz9z9qonI5ZDlHl6kGd1KAXopaDbf1MzuNXjeVj-/pub?gid=0&single=true&output=csv">IP許可リストに記載されたAppsFlyerのIPアドレスを許可するよう、セキュリティチームに依頼してください。</Anchor>

2022年2月16日に、旧IPアドレスの使用を廃止し、許可リストから削除しました。

許可するアドレスは、次のCIDRブロックで指定されています。

* [45.92.116.0/22]
* [194.28.46.0/23]

<div id="uploading-audiences" />

### Audiencesのアップロード

ファイアウォールやプロキシサーバーなど、ネットワーク境界の機器を使用している場合は、この[AudiencesのIP許可リスト](https://support.appsflyer.com/hc/article_attachments/16888953497617)に記載されたAppsFlyerのIPアドレスを許可するよう、セキュリティチームに依頼してください。

<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide">Audiences</Anchor>の詳細を確認してください。

<div id="pull-api-and-server-to-server-s2s" />

### Pull APIとサーバー間（S2S）通信

Pull APIとS2Sは、この記事に記載されたIPアドレスの影響を受けません。ただし、*\*.appsflyer.com*ドメインが許可リストに登録され、ブロックされていないことを確認してください。

<div data-zendesk-anchors="appsflyer-server-ip-address-ranges=appsflyer%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E3%81%AEip%E3%82%A2%E3%83%89%E3%83%AC%E3%82%B9%E7%AF%84%E5%9B%B2 uploading-audiences=audiences%E3%81%AE%E3%82%A2%E3%83%83%E3%83%97%E3%83%AD%E3%83%BC%E3%83%89 pull-api-and-servertoserver-s2s=pull-api%E3%81%A8%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E9%96%93s2s%E9%80%9A%E4%BF%A1" />
