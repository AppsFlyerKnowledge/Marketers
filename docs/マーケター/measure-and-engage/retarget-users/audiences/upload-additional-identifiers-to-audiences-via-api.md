---
title: オーディエンス—追加識別子API
metadata:
  keywords:
    - Advertisers
    - Developers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-22T14:05:51Z'
  edited_at: '2026-10-14T09:39:36Z'
  id: 4411552670993
  locale: ja
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ja/articles/4411552670993
---
> **概要:** Audiences追加識別子APIを使用して、社内システム（ビジネスインテリジェンスやCRMなど）からAppsFlyerオーディエンスにユーザー識別子を一括アップロードし、これらの識別子に基づいてより幅広いオーディエンスコミュニケーションを関連パートナーに提供します。

## APIについて

Audiences追加識別子APIを利用することで、社内システムから以下のユーザー識別子をAppsFlyerオーディエンスに追加できます。

* ハッシュ化されたメールアドレス（最大2つ）
* ハッシュ化された電話番号
* ハッシュ化されたE164電話番号

後にこれらの識別子をオーディエンスパートナーに送信することを選択できます（<Anchor target="_blank" href="/marketers/ja/docs/audiences-user-identifier-policy">アカウントレベルのユーザー識別子ポリシー</Anchor>に従って）、これによりパートナーはターゲットオーディエンスをより正確に識別できます。すべての広告パートナーがすべての識別子をサポートするわけではないことに注意してください。

### このAPIはいつ使用するべきですか？

このAPIは、大量の識別子データをアップロードする際に使用するよう設計されています。これは通常、時間の経過と共に収集されたデータを指します（例：過去12か月間にアプリのすべてのユーザーから収集されたハッシュ化されたメール）。特定のデバイスからの識別子をリアルタイムに個別更新するには、AppsFlyer SDKまたはS2SモバイルAPIで<Anchor target="_blank" href="/marketers/ja/docs/audiences-configure-additional-identifiers-for-partner-audience-creation">追加識別子を設定</Anchor>してください。

> 🚧 **重要！**
>
> すべての追加識別子値は、SHA256ハッシュで暗号化する必要があります。暗号化されていない識別子は処理されません。
>
> **タイミング:** 識別子の正確な一致を保証するため、Audiences追加識別子APIは、AppsFlyer SDKによって主要な識別子がレポートされた**翌日からすぐに**使用できます（UTC）。例えば、2022年1月3日（UTC）に報告された識別子は、2022年1月4日（UTC）以降にこのAPIを通じて更新できます。

## アクション

* [識別子の追加／変更](/docs/upload-additional-identifiers-to-audiences-via-api#addmodify-identifiers-put)
* [識別子の削除](/docs/upload-additional-identifiers-to-audiences-via-api#remove-identifiers-delete)

## 認証

リクエストには、アカウントの<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">AppsFlyer V2.0 APIトークンを含むHTTPヘッダーが含まれている必要があります。アカウント管理者に、AppsFlyer管理画面からこのトークンを取得するよう依頼してください。</Anchor>

## API仕様およびサンプルコード

<div id="addmodify-identifiers-put" />

<Accordion title="識別子の追加／変更（PUT）">

<span id="01ECF4ZD0T03JBV8DDH25MM01W"></span>**APIリクエストURL**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| パラメーター | 説明 | 必須 |
| --- | --- | --- |
| `{アプリID}` | 識別子が収集されたアプリのアプリID（AppsFlyer管理画面に表示されるもの） | はい |

<span id="01ECF4ZD0TWPH3DXV2YKN7G9B0"></span>**APIリクエスト本文**

```json
{
  "key_type": "<key_type>",
  "action": "add",
  "data": [
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    },
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    }
  ]
}
```

| パラメーター | 説明 | 必須 |
| --- | --- | --- |
| `{キータイプ}` | リクエストの各データ行でユーザーを表現する唯一の値として用いられる識別子。<br /><br />ここで指定された値は、リクエスト内のすべての行に適用されます。<br /><br />可能な値：<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_id</li><li>imei</li><li>oaid</li></ul> | はい |
| `{アクション}` | add | いいえ<br /><br />デフォルト値：追加 |
| `{キー値}` | 指定されたkey\_typeの有効な識別子の値 | はい |
| \{識別子\} | 追加する識別子の名前と値を含むオブジェクト：<ul><li>\{ハッシュ化されたメール\}</li><li>\{電話番号\_sha256\}</li><li>\{電話番号\_e164\_sha256\}</li></ul> | はい<ul><li>これら3つの識別子のうち少なくとも1つの値を含める必要があります。</li></ul> |
| `{ハッシュ化されたメール}` | 最大2つのハッシュ化されたメールアドレスの配列<br /><br />形式：<ul><li>小文字</li><li>空白なし</li><li>SHA256ハッシュ済み</li></ul>ハッシュ化前の値の例：name@domain.com | いいえ |
| `{電話番号_sha256}` | 電話番号（下記注記参照）<br /><br />形式：<ul><li>記号、文字、先頭のゼロを含めない</li><li>国コードを含める</li><li>SHA256ハッシュ済み</li></ul>ハッシュ化前の値の例：<br /><br />442070313000 | いいえ |
| `{電話番号_e164_sha256}` | E164形式の電話番号（下記の注記を参照）<br /><br />形式<ul><li>E164電話番号</li><li>SHA256ハッシュ済み</li></ul>ハッシュ化前の値の例：<br /><br />+442070313000 | いいえ |

> 📘 **注**
>
> 異なる広告パートナーは異なる電話番号形式をサポートしています。したがって、電話番号を追加する場合は、両方の識別子を送信することをおすすめします：*phone\_number\_sha256* と *phone\_number\_e164\_sha256。*

**制限事項**

**識別子の追加/変更リクエストには次の制限が適用されます。**

* 以前に存在していた値（ある場合）は、リクエストで送信された値によって上書きされます。
* `{data}`オブジェクトには、リクエストごとに最大4,000行（key\_values）を含めることができます。

**識別子を追加するためのサンプルリクエスト**

```json
HTTP PUT
body:
{
  "key_type": "idfv",
  "action": "add",
  "data": [
    {
      "key_value": "CDDA802e-AAAA-BBBB-CCCC-DDDDDDDDDDDD",
      "identifiers": {
        "hashed_emails": [
          "34d31be18022626de6b311d6a76e791176d2691b6eef406f524d8f56364c187a",
          "d8c2aec999baad2464e521873ee4465caaf7ff6db8c8b4a25b09ca07694e4dee"
        ],
        "phone_number_sha256": "6c91c4c640f6ef0162833260db4f13dec0df2b683092f4dba7e874bef1acea37",
        "phone_number_e164_sha256": "f3d7e96c73fb0de1b66acfce541d7af758fbd4f3fa3af0ea4e10110000d3625e"
      }
    }
  ]
}
```

</Accordion>

<div id="remove-identifiers-delete" />

<Accordion title="識別子を削除する（PUT）">

**APIリクエストURL**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| パラメーター | 説明 | 必須 |
| --- | --- | --- |
| `{アプリID}` | 識別子が収集されたアプリのアプリID（AppsFlyer管理画面に表示されるもの） | はい |

**APIリクエスト本文**

```json
{
  "key_type": "<key_type>",
  "action": "remove",
  "data": [
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    },
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

| パラメーター | 説明 | 必須 |
| --- | --- | --- |
| `{キータイプ}` | リクエストの各データ行でユーザーを表現する唯一の値として用いられる識別子。<br /><br />ここで指定された値は、リクエスト内のすべての行に適用されます。<br /><br />可能な値：<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_id</li><li>imei</li><li>oaid</li></ul> | はい |
| `{キー値}` | 指定されたkey\_typeの有効な識別子の値 | はい |
| `{アクション}` | 削除 | いいえ<br /><br />デフォルト値：追加 |
| \{識別子\} | 削除したい識別子の名前を含む配列：<ul><li>\{ハッシュ化されたメール\}</li><li>\{電話番号\_sha256\}</li><li>\{電話番号\_e164\_sha256\}</li></ul> | はい<ul><li>これら3つの識別子のうち少なくとも1つを含める必要があります。</li></ul> |

**制限事項**

`{data}`オブジェクトには、リクエストごとに最大4,000行（key\_values）を含めることができます。

**識別子を削除するためのサンプルリクエスト**

```json
HTTP PUT
body:
{
  "key_type": "gaid",
  "action": "remove",
  "data": [
    {
      "key_value": "cdda802e-aaaa-bbbb-cccc-dddddddddddd",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

</Accordion>

<div id="responses" />

<Accordion title="応答">

| コード | メッセージ | 説明 |
| --- | --- | --- |
| 202 | 処理が受け入れられました | リクエストは次の処理期間中に適用されます。 |
| 400 | リクエスト本文には有効なkey\_typeが必要です | 以下のkey\_typesがサポートされています:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_id</li><li>imei</li><li>oaid</li></ul> |
| 400 | リクエストには少なくとも1つの要素を持つ「データ」が必要です | データリストは空にできません。 |
| 400 | リクエストの「データ」は1回のリクエストで4000を超えてはいけません | データリストには最大4,000行含めることができます。 |
| 400 | リクエストデータに無効な「データ」要素が多すぎます | 変更するデータの10%以上が仕様に従って有効ではありません。 |
| 404 | AppsFlyer - ページが見つかりません | 次の点を確認してください:<ul><li>APIリクエストURLで指定された`{app-id}`が正しいことを確認してください。</li><li>HTTPヘッダーには正しい<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">AppsFlyer V2.0 APIトークン</Anchor>が含まれていることを確認してください。アカウントの管理者は、このトークンをAppsFlyer管理画面から取得することができます。</li></ul> |

**応答例**

```json
{
"message": "Accepted for processing",
"received": 1000,"invalid": 2,
"trace-id": "698ed323-c787-45b5-b792-463c67c94064"
}
```

```json
{
"error": "Request body must have a valid key_type",
"trace-id": "18a5f685-ea4d-4ca9-beab-a542a3786d12"
}
```

```json
{
"error": "Request must have 'data' with at least 1 element",
"trace-id": "c155a7fa-b573-4efe-9bfb-5ae7de40e7fd"
}
```

```json
{
"error": "Request 'data' should not exceeds the size of 4000 in a single request”,
"trace-id": "b325a7fa-b573-4efe-9bfb-5ae7de40e72c"
}
```

```json
{
"error": "Request data has too many invalid 'data' elements",
"valid": 2,
"invalid": 30,
"trace-id": "33551c1d-5682-405e-a959-c8729ca74735"
}
```

</Accordion>

<div id="rate-limitations" />

<Accordion title="レート制限">

* 1秒につき5リクエスト
* 1分につき350リクエスト

</Accordion>

<div data-zendesk-anchors="api-overview=api%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HNZP1Y2MQ8W25SNP2XVNZ7WW=api%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 when-should-i-use-this-api=%E3%81%93%E3%81%AEapi%E3%81%AF%E3%81%84%E3%81%A4%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B%E3%81%B9%E3%81%8D%E3%81%A7%E3%81%99%E3%81%8B h_01HNZP1Y2MJY56TMN6QH4BVRPA=%E3%81%93%E3%81%AEapi%E3%81%AF%E3%81%84%E3%81%A4%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B%E3%81%B9%E3%81%8D%E3%81%A7%E3%81%99%E3%81%8B h_01HNZP1Y2MX414NJ49BCVW7KZC=%E9%87%8D%E8%A6%81 methods=%E3%82%A2%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 h_01HNZP1Y2MS5V43XS008GG4S32=%E3%82%A2%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 authentication=%E8%AA%8D%E8%A8%BC h_01HNZP1Y2MH2Y4P8ZT4SVM5GM2=%E8%AA%8D%E8%A8%BC api-specifications-and-sample-code=api%E4%BB%95%E6%A7%98%E3%81%8A%E3%82%88%E3%81%B3%E3%82%B5%E3%83%B3%E3%83%97%E3%83%AB%E3%82%B3%E3%83%BC%E3%83%89 h_01HNZP1Y2MR0GCCA1916RMB6GJ=api%E4%BB%95%E6%A7%98%E3%81%8A%E3%82%88%E3%81%B3%E3%82%B5%E3%83%B3%E3%83%97%E3%83%AB%E3%82%B3%E3%83%BC%E3%83%89 h_01HNZP1Y2M1N548KSMA6MQ601W=addmodify-identifiers-put h_01HNZP1Y2P2VVV4WT88D82QXJ4=%E6%B3%A8 h_01HNZP1Y2Q0FAQQE3MTZ8B3FFS=remove-identifiers-delete h_01HNZP1Y2QK2J8ERP1SQTYB20C=responses h_01HNZP1Y2Q1WZCN2TCEAS6HB2X=rate-limitations" />
