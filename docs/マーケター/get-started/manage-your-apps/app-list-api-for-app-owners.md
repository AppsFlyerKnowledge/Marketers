---
title: アプリ所有者向けアプリリスト API
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-08-17T18:07:10Z'
  edited_at: '2026-10-14T09:34:07Z'
  id: 360011999877
  locale: ja
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ja/articles/360011999877
---
> **概要：** AppsFlyer アカウントに関連付けられているアクティブなアプリと保留中のアプリを取得します。

![mceclip0.png](https://files.readme.io/34b4b3d56ca5d7419830ba26701483f64ebb0a908e1e8e7ed65779bb89a14c67-24507752775313.png)

アドネットワークの場合は、<Anchor target="_blank" href="/partners/ja/docs/app-list-api-for-ad-networks">アドネットワーク用アプリリストAPIを使用してください</Anchor>。

**参考記事**：<Anchor target="_blank" href="/marketers/ja/docs/about-advertiser-apis">広告主向け API リスト</Anchor>

## アプリリストの取得API

以下のセクションに、API を使用するために必要な情報を記載しています。

アプリリスト基本情報の取得

<div id="get-api-list-basics" />

<Accordion title="API リストの基本情報を取得">

<table><thead><tr><th>カテゴリ</th><th>アイテム</th><th><p><span>説明</span></p></th></tr></thead><tbody><tr><td rowspan="3">リクエスト</td><td>HTTP メソッド</td><td><code>GET</code></td></tr><tr><td>経路</td><td><p><span>https://hq1.appsflyer.com/api/mng/apps</span></p></td></tr><tr><td>認証ヘッダー  </td><td><ul><li>認証ヘッダーには、Bearerトークンを含める必要があります。  </li><li>管理者ユーザーは、次のようにダッシュボードでトークンを取得します。<a href="./managing-appsflyer-tokens" target="_blank">管理者はメールドロップダウンリスト &gt; API トークンの順で移動し、V2.0 トークンを取得します</a> </li></ul></td></tr><tr><td rowspan="3"><p> レスポンス</p></td><td><p>結果</p></td><td><p>JSON 形式で返されます</p></td></tr><tr><td>リクエスト制限</td><td><ul><li>20リクエスト / 分</li><li>100リクエスト / 日</li></ul></td></tr><tr><td>レコード数の制限</td><td><p>1リクエストにつき、1,000レコードまで取得可能です。1,000以上のレコードが返される場合には、この記事内で紹介されているページネーションのリクエストを使用してください。</p></td></tr></tbody></table>

</Accordion>

<div id="api-request" />

<Accordion title="API リクエスト">

API リクエストは、メソッド、経路、必須の機能パラメーター、オプションのページネーションパラメーターで構成されています。また、API トークンは認証ヘッダーに含まれます。

**メソッド**

```http
GET https://hq1.appsflyer.com/api/mng/apps
```

アプリリストの必須パラメーターの取得：

| クエリパラメーター | 説明 |
| --- | --- |
|  | この API には必須のクエリパラメーターはありません |

#### **ページネーションの仕組みについて**

随時機能するページネーションの仕組みが実装されています。

**ページネーションの仕様：**

* リクエスト(ページ)毎に最大1,000レコードまで返します。
* レスポンスJSON には、以下のページネーション関連のキーが含まれています：
  * **meta.total\_items**:全ページ合算でのレコード数です。これは、照会されている*機能*が付与されているアプリの数を表します。
  * ページネーションリンク(下記 JSON を参照)には、以下のキーが含まれます：  
    * **links.prev**：それよりも前のリクエストがあった場合 - 前のページを生成するために使用されたリクエストが入ります。
    * **links.self**:現在のリクエスト：現在の JSON （ページ）を生成するために使用されたリクエスト
    * **links.next**:次のページを取得するためのリクエストです。*次へ*のキーがない場合は、これが最終ページです。

**次のいずれかのページネーションの制御方法を使用してください。**

* [ベストプラクティス] JSON *内のリンクを使用する*：*links.next* キーが存在する場合は、それを使用して次のページを取得するリクエストを作成します。*links.next* のキーがないJSON を受け取るまでは、この作業を続けてください。
* *limit*と*offset* のパラメーターを*total\_items*のキーを組み合わせたプログラムを実装してください。

**ページネーションリンク JSON の例**

* 次の例には、データセクションの2つのレコードで構成される2回目のリクエストの結果が含まれています (表示されていません)。
* 返されるレコードの総数は6です。
* **links.next** キーには、2ページ目 (レコード5と6) を返すリクエストが含まれています。

```json
{                                                                                         
    "data": {[...]},   
    "meta": {
        "total_items": 6
    },
    "links": {
        "prev": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=2",
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=2&limit=2",
        "next": "https://hq1.appsflyer.com/api/mng/apps?offset=4&limit=2"
    }
}
```

ページネーション機能のパラメーター（任意）：

| クエリパラメーター | 説明 |
| --- | --- |
| limit | コール毎に返されるレコード数<ul><li>最大値：2024-02-26</li><li>`limit`を送信しない場合、自動的に1,000に設定されます。</li><li>例： `limit=2`</li><li>必須：いいえ</li></ul> |
| offset | コールで返される最初のレコードです。レコード番号は0から始まります。<ul><li>`offset`を送信しない場合、自動的に0に設定されます。</li><li>例：`offset=2`</li><li>必須：いいえ</li></ul> |

</Accordion>

<div id="json-response" />

<Accordion title="JSON レスポンス">

| **キー** | **説明** |
| --- | --- |
| id | アプリ ID (例:`id123456789`, `com.myapp.com` |
| type | 常に戻る `app` |
| name | App name |
| platform | iOS or Android が返されます。 |
| currency | アプリ固有の通貨コード |
| time\_zone | アプリ固有のタイムゾーン |
| total\_items | アカウントに格納されているアプリの数 |
| links | ページネーション機能（パラメーターのセクションを参照してください）<ul><li>prev: 前のページを生成するために使用されたコールが返されます。</li><li>self: そのページを生成するために使用されたコールが返されます。</li><li>next: 次のページを生成するために使用するコールが返されます。</li></ul> |

</Accordion>

<div id="get-app-list-curl-example-and-response" />

<Accordion title="アプリリスト取得の cURL の例とそのレスポンス">

**Curl リクエスト**

この例は、任意のページネーションパラメーターを含む完全なコール内容が記載されています。

```bash
cURL --location --request GET 'https://hq1.appsflyer.com/api/mng/apps?limit=1000&offset=0' \
-H 'Authorization: Bearer {API V2.0 token having more than 700 characters available to the admin in the dashboard.}' \
```

**JSON レスポンス**

```json
{
    "data": [
        {
            "id": "com.appsflyer.xpend_qa1",
            "type": "app",
            "attributes": {
                "name": "com.appsflyer.xpend_qa1",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC"
            }
        },
        {
            "id": "com.abc.app",
            "type": "app",
            "attributes": {
                "name": "com.abc.app",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC",
                "enable_retargetting": true
            }
        },
        {
            "id": "com.def.app",
            "type": "app",
            "attributes": {
                "name": "com.def.app",
                "platform": "android",
                "currency": "JPY",
                "time_zone": "UTC"
            }
        }
    ],
    "meta": {
        "total_items": 6
    },
    "links": {
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=1000"
           }
}
```

</Accordion>

<div id="http-response-codes" />

<Accordion title="HTTP のレスポンスコード">

| コード | メッセージ | 備考 / トラブルシューティング |
| --- | --- | --- |
| 200 | OK | 有効なデータが返されました |
| 200 | OK | **症状**：データ返却なし<br /><br />**アクション**：bearer ヘッダー内に認証トークンがあることを確認してください。 |
| 400 | Bad request | JSON内に含まれているメッセージを確認してください。 |
| 401 | Unauthorized | **メッセージ**：認証トークンの形式が正しくありません<br /><br />正しいトークンであることを確認してください。トークン文字数は700字以上です。 |
| 404 | Not found | <ul><li>ネットワークやファイアウォールに関する問題を処理してください。</li><li>AppsFlyer の<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-server-ip-address-ranges-allowlisting">IP アドレスが許可リストに登録されていること</Anchor>を確認してください</li><li>必ず直近に発行された最新のトークンを使用してください。</li><li>データが見つかりませんでした：アプリが見つかりません。</li></ul> |
| 429 | Too many requests | レート制限を超えました |

</Accordion>

<div data-zendesk-anchors="get-app-list-api=%E3%82%A2%E3%83%97%E3%83%AA%E3%83%AA%E3%82%B9%E3%83%88%E3%81%AE%E5%8F%96%E5%BE%97api pagination-mechanism=%E3%83%9A%E3%83%BC%E3%82%B8%E3%83%8D%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6" />
