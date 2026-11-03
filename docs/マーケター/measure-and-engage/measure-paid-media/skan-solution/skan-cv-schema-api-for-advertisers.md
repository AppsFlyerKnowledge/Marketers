---
title: 広告主向けSKAN CVスキーマAPI
metadata:
  keywords:
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-08-24T12:59:10Z'
  edited_at: '2026-10-28T09:17:46Z'
  id: 8610329713553
  locale: ja
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ja/articles/8610329713553
---
> **概要：** AppsFlyer Conversion Studioに設定されている、現在のSKAdNetwork（SKAN）のコンバージョン値（CV）スキーマを確認できます。

## SKANコンバージョン値スキーマAPI

<div id="api-basics" />

<Accordion title="APIの基本情報">

| 概要 | AppsFlyer Conversion Studioに設定されている、現在のSKAdNetwork（SKAN）のCVスキーマを確認します。<br /><br />**注意**：<ul><li>過去のSKAN CVスキーマは取得できません。</li><li>Conversion StudioからCSVマッピングファイルをダウンロードして、SKANスキーマを確認することもできます。</li></ul> |
| --- | --- |
| パス | `https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>` |
| パスパラメータ（必須） | `<app_id>`：AppsFlyerのダッシュボードに表示されるアプリ識別子。ダッシュボードの表示どおりに入力します。例：id123456789 |
| HTTPメソッド | `GET` |
| レスポンスのコンテンツタイプ | `text/plain` |
| 認証 | API V2.0トークン（Bearerトークン）を含む`Authorization` HTTPヘッダーが必要です。<br /><br />![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)管理者ユーザーが<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">ダッシュボードでV2トークンを取得</Anchor>します。画面上部のアカウントメニュー（メールアドレスのドロップダウン）を開き、**［セキュリティセンター］**＞<strong>［AppsFlyer APIおよびS2Sトークン］</strong>に移動します。 |
| レート制限 | <ul><li>1回のクエリで最大50,000行を返します。</li><li>1分あたり10回の呼び出し</li></ul> |
| 最終設定変更日 | <ul><li>デコードモードでは、ファイル名に日付が表示されます。</li><li>ほかのすべてのモードでは、last\_config\_change列に日付が表示されます。</li></ul> |

### リクエスト例（cURL）

```shell
curl --request \
GET 'https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>' \
--header 'Authorization: Bearer <V2_AUTH_TOKEN_HERE (700+ characters string)>'
```

</Accordion>

<div id="report-name" />

<Accordion title="レポート名">

APIは、以下の規則で名前を付けたCSVファイルを返します。

デコードモード：`conversion_value_mapping_<date of last schema configuration change>`

ほかのすべてのモード：`conversion_schema_report_custom_encode`

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| アドネットワークのアクセス | 分析パートナーの場合は、広告主に権限の付与を依頼してください。 |
| 代理店のアクセス | 利用不可 |
| アカウントユーザーのアクセス | 認証トークンは、管理者ユーザーがダッシュボードで取得できます。 |

</Accordion>

<div id="http-response-codes-and-troubleshooting" />

<Accordion title="HTTPレスポンスコードとトラブルシューティング">

| HTTP | レスポンス | 補足 |
| --- | --- | --- |
| 200 | OK | 有効なデータを返しました（CSV）。 |
| 400 | 不正なリクエスト | 無効なリクエストです。 |
| 401 | 認証エラー | 認証トークンがないか、無効です。<br /><br />トークンを正しく使用していることを確認してください。 |
| 401 | リクエスト数が多すぎます | レート制限を超えました。 |
| 403 | 権限がありません | このレポートにアクセスする権限がありません。分析パートナーの場合は、広告主に権限の付与を依頼してください。 |
| 404 | 見つかりません | <ul><li>ネットワークやファイアウォールに関する問題を解消してください。</li><li>AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-server-ip-address-ranges-allowlisting">IPアドレスが許可リストに登録されている</Anchor>ことを確認してください。</li></ul> |

</Accordion>

<div data-zendesk-anchors="skan-conversion-value-schema-api=skan%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E5%80%A4%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%9Eapi h_01HKW1B4XQH2JCJ3T0M1D6W7EM=skan%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E5%80%A4%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%9Eapi h_01HKW1B4XQCZPQBQFADGNTZDC3=api-basics request-example-curl=%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E4%BE%8Bcurl h_01HKW1B4XQXQW0Z0G8ZF9EE8AZ=%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E4%BE%8Bcurl h_01HKW1B4XQ6ZD45YPHKHDHAZX0=report-name h_01HKW1B4XQVFNM33WV73BA5QXG=traits-and-limitations h_01HKW1B4XQY0V30B4BYCRF9HP5=http-response-codes-and-troubleshooting" />
