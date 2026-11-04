---
title: Web Performance Measurement向けのServer-to-Server（S2S）API
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
  created_at: '2026-04-12T15:09:07Z'
  edited_at: '2026-10-14T09:23:09Z'
  id: 45670116601617
  locale: ja
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ja/articles/45670116601617
---
> **概要：** Web Performance Measurement向けS2S APIを使用すると、広告ブロッカーやCookie制限などのブラウザによる制約を回避し、Webサイトへの訪問とイベントをサーバーからAppsFlyerへ直接送信できます。Web SDKと併用することも、単独で使用することもでき、より網羅的で品質の高いアトリビューションデータを取得できます。

<div id="about-the-s2s-api-for-web-attribution" />

## Webアトリビューション向けS2S APIについて

AppsFlyerでは、Webデータをアトリビューションのために送信する方法として、Web SDK（クライアントサイド）とS2S API（Server-to-Server）の2種類を提供しています。これらは、それぞれ単独で利用することも、運用環境や要件に応じて組み合わせて利用することもできます。

Web SDKはブラウザ上で動作します。一方、S2S APIでは同じデータをお客様のバックエンドから直接送信できます。この違いは非常に重要です。Safari ITP、Firefox ETP、Braveなどのプライバシー保護を重視したブラウザや広告ブロッカーは、ブラウザ上で行われる計測を制限またはブロックする場合があります。業界では、このようなブラウザレベルでの制限の影響を受けるユーザーはWebユーザー全体の25～40%程度と推定されています。S2S APIによるリクエストはお客様のサーバーから直接送信され、ブラウザを経由しないため、これらの制限の影響を受けません。

<div id="how-it-works" />

### 仕組み

1. ユーザーがウェブサイユーザーがWebサイトへアクセスする、またはブラウザ上でイベントを発生させます。
2. お客様のサーバーがそのイベントを受信します。
3. お客様のサーバーからAppsFlyerサーバーへイベントを直接送信し、アトリビューションを行います。

<div id="why-use-s2s" />

### S2Sを使用するメリット

S2S APIを利用することで、以下のようなメリットがあります：

* **サーバー側で発生するイベントを計測できる：** 一部のコンバージョンはブラウザを経由しません。例えば、バックエンドで処理されるサブスクリプション更新や、CRMシステムで発生するイベントなどが該当します。これらのイベントをAppsFlyerへ送信し、適切なキャンペーンへアトリビューションできるのは、S2S APIのみです。
* **計測対象を拡大できる：** S2S APIによるリクエストはブラウザではなくサーバーから送信されるため、広告ブロッカー、Safari ITPによるCookie制限、その他ブラウザレベルの制限の影響を受けません。その結果、クライアントサイド計測だけでは取得できない訪問やコンバージョンも計測できます。
* **バックエンドのデータを追加できる：** S2S APIでは、イベント送信前にバックエンド側で追加情報を付与できます。 例えば、以下の情報を追加できます： ・Customer User ID ・ハッシュ化したメールアドレス ・ハッシュ化した電話番号 ・CRM属性 ・サブスクリプションステータス ・社内システムの識別子これにより、ユーザー識別の精度が向上し、アトリビューションの品質も高まります。
* **セキュリティを強化できる：** Dev Key、ユーザー識別子、および追加したデータはすべてお客様のサーバー内で管理され、安全な通信を通じてAppsFlyerへ送信されます。そのため、お客様はインフラストラクチャの外部へ送信する情報を完全に管理できます。

<div id="api-specification" />

## API仕様

Base URL：`https://events.appsflyer.com`

<div id="authentication" />

### 認証

すべてのリクエストには、有効なS2S APIトークンおよび適切なContent-Typeをリクエストヘッダーに含める必要があります。

| Header | 型 | 説明 |
| --- | --- | --- |
| `Authorization` | APIトークン | S2S APIトークンを以下の形式で指定します。<br /><br />`Authorization: Bearer {s2s-token}` |
| `Content-Type` | string | `application/json`を指定します。すべてのリクエストで必要です。 |

<div id="note" />

> 📘 **注意**
>
> S2S APIトークンを作成するには、<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens#トークンの管理">AppsFlyerトークンの管理</Anchor>の手順を参照してください。

<div id="measure-an-event" />

### イベントの計測

`POST /v2.0/s2s/inapps/app/web/{appId}`

指定したアプリに対して、購入、会員登録、カスタムアクションなどのWebイベントを計測します。

<div id="path-parameter" />

<Accordion title="パスパラメータ">

| パラメータ | 必須 | 説明 |
| --- | --- | --- |
| `appId` | 必須 | AppsFlyerで定義されている`unified_app_id`。例：`website-www.example.com` |

</Accordion>

<div id="request-body" />

<Accordion title="リクエスト本文">

| 項目 | 型 | 必須 | 説明 |
| --- | --- | --- | --- |
| `user_id` | object | 必須 | ユーザー識別子。`customer_user_id`または`appsflyer_id`のいずれかを少なくとも1つ含める必要があります。 |
| `event_name` | string | 必須 | イベント名。1～64文字で指定します。`@ = + -`を含めることはできません。例：`af_purchase` |
| `event_revenue` | number（double） | 任意 | 購入イベントまたは収益化イベントの売上金額。 |
| `event_revenue_currency` | string (ISO-4217) | 任意 | 売上金額の通貨コード。例：`USD` , `EUR` |
| `event_value` | object | 任意 | 自由形式のイベントパラメータ。`custom_parameters` のサブオブジェクトに対応しています。 |
| `event_url` | string | 任意 | イベントが発生したページのURL。有効なHTTP URLで、最大4,096文字まで指定できます。 |
| `timestamp` | integer (int64) | 任意 | Unix時間（ミリ秒、UTC）。省略した場合、AppsFlyerは受信時刻を使用します。遅延イベントの受付期限：イベントは、アプリのタイムゾーンにおける翌暦日の00:30までに到着している必要があります。 |
| `ip` | string | 任意 | デバイスのIPアドレス（IPv4またはIPv6）。最大46文字まで指定できます。 |
| `user_agent` | string | 任意 | ブラウザから取得した完全なユーザーエージェント文字列。最大1,024文字まで指定できます。 |
| `http_referrer` | string | 任意 | 現在のページのリファラURL。 |
| `customer_dedup_id` | string | 任意 | お客様側で指定する重複排除用の識別子。 |
| `email_hashed` | string | 任意 | 正規化されたメールアドレス（小文字化・前後の空白削除済み）のSHA256ハッシュ値。64文字の16進数文字列である必要があります。 |
| `phone_number_hashed` | string | 任意 | 電話番号のSHA256ハッシュ値。64文字の16進数文字列である必要があります。 |
| `phone_number_e164_hashed` | string | 任意 | E.164形式の電話番号（例：`+14155552671`）のSHA256ハッシュ値。64文字の16進数文字列である必要があります。 |
| `first_name_hashed` | string | 任意 | 正規化された名のSHA256ハッシュ値。64文字の16進数文字列である必要があります。 |
| `last_name_hashed` | string | 任意 | 正規化された姓のSHA256ハッシュ値。64文字の16進数文字列である必要があります。 |

</Accordion>

<div id="example-request" />

<Accordion title="リクエスト例">

```json
{"user_id":{"customer_user_id":"15667737-366d-4994-ac8b-653fe6b2be4a"},"event_name":"af_purchase","event_revenue":49.99,"event_revenue_currency":"USD","event_value":{"af_content_id":"SKU-001","af_quantity":2,"custom_parameters":{"promo_code":"SUMMER10"}},"event_url":"https://example.com/checkout/success","timestamp":1712000000000,"ip":"35.244.183.10","user_agent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) ...","email_hashed":"a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2"}
```

</Accordion>

<div id="responses" />

<Accordion title="レスポンス">

| ステータス | 説明 |
| --- | --- |
| 202 Accepted | リクエストが受け付けられました。status、message、および任意で`messageId`が返されます。 |
| 400 Bad Request | フィールドが無効、または不足しています。 |
| 401 Unauthorized | アプリが存在しない、または認証に失敗しました。 |
| 403 Forbidden | アプリのトラフィックがブロックされています。 |
| 415 Unsupported Media Type | `Content-Type` は `application/json` である必要があります。 |

</Accordion>

<div id="measure-a-visit" />

### Web訪問の計測

`POST /v2.0/s2s/visits/app/web/{appId}`

指定したWebアプリのページ訪問を計測します。このエンドポイントは、イベント計測エンドポイントと共通の基本フィールドを使用しますが、以下の2点が異なります。 ・`event_url` は必須です。 ・event\_nameおよび収益関連のフィールドは使用しません。

<div id="path-parameter::d8a9ef62" />

<Accordion title="パスパラメータ">

| パラメータ | 必須 | 説明 |
| --- | --- | --- |
| `appId` | 必須 | AppsFlyerで定義されている`unified_app_id`。例：`website-www.example.com` |

</Accordion>

<div id="request-body::f7fb791b" />

<Accordion title="リクエスト本文">

| 項目 | 型 | 必須 | 説明 |
| --- | --- | --- | --- |
| `user_id` | object | 必須 | ユーザー識別子。`customer_user_id`または`appsflyer_id`のいずれかを少なくとも1つ含める必要があります。 |
| `event_url` | string | 必須 | 訪問したページのURL。有効なHTTP URLで、最大4,096文字まで指定できます。 |
| `timestamp` | integer (int64) | 任意 | Unix時間（ミリ秒、UTC）。省略した場合、AppsFlyerは受信時刻を使用します。遅延イベントの受付期限：訪問データは、アプリのタイムゾーンにおける翌日の00:30までに到着している必要があります。 |
| `ip` | string | 任意 | デバイスのIPアドレス（IPv4またはIPv6）。最大46文字まで指定できます。 |
| `user_agent` | string | 任意 | ブラウザから取得した完全なユーザーエージェント文字列。最大1,024文字まで指定できます。 |
| `http_referrer` | string | 任意 | 現在のページのリファラURL。 |
| `event_value` | object | 任意 | 自由形式のイベントパラメータ。`custom_parameters`のサブオブジェクトを含めることができます。 |
| `customer_dedup_id` | string | 任意 | お客様側で指定する重複排除用の識別子。 |
| `email_hashed` | string | 任意 | 正規化されたメールアドレスのSHA256ハッシュ値。64文字の16進数文字列である必要があります。 |
| `phone_number_hashed` | string | 任意 | 電話番号のSHA256ハッシュ値。64文字の16進数文字列である必要があります。 |
| `phone_number_e164_hashed` | string | 任意 | E.164形式の電話番号のSHA256ハッシュ値。64文字の16進数文字列である必要があります。 |
| `first_name_hashed` | string | 任意 | 正規化された名のSHA256ハッシュ値。64文字の16進数文字列である必要があります。 |
| `last_name_hashed` | string | 任意 | 正規化された姓のSHA256ハッシュ値。64文字の16進数文字列である必要があります。 |

</Accordion>

<div id="example-request::6283854b" />

<Accordion title="リクエスト例">

```json
{"user_id":{"appsflyer_id":"1234567890abcdef","customer_user_id":"15667737-366d-4994-ac8b-653fe6b2be4a"},"event_url":"https://example.com/products/sneakers","timestamp":1712000000000,"ip":"35.244.183.10","user_agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) ...","http_referrer":"https://www.google.com/","email_hashed":"a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4e5f6a1b2"}
```

</Accordion>

<div id="responses::5cfbc5cc" />

<Accordion title="レスポンス">

| ステータス | 説明 |
| --- | --- |
| 202 Accepted | リクエストが受け付けられました。status、message、および任意で`messageId`が返されます。 |
| 400 Bad Request | フィールドが無効、または不足しています。 |
| 401 Unauthorized | アプリが存在しない、または認証に失敗しました。 |
| 403 Forbidden | アプリのトラフィックがブロックされています。 |
| 415 Unsupported Media Type | `Content-Type` は `application/json` である必要があります。 |

</Accordion>

<div id="set-up-a-fully-server-side-integration" />

## 完全なサーバーサイド連携を設定する

Web SDKとS2Sを併用している場合は、このセクションではなく、[Web SDKのafUserIDを取得する](#extracting-the-web-sdk-afuserid)を参照してください。このセクションは、SDKを一切使用しない連携のみを対象としています。

WebサイトでWeb SDKをまったく使用しない場合は、通常Web SDKが処理するすべての作業を自社で行う必要があります。これには、ユーザーCookieの設定、適切な識別子の送信、各イベントペイロードに必要な情報を不足なく含めることが含まれます。正しく設定すれば、[S2Sを使用する理由](#s2sを使用するメリット)で説明したすべてのメリットを得られますが、そのためには以下の詳細を正しく設定する必要があります。

<div id="h_01KZS2SFULLSVR02" />

<Accordion title="イベントだけでなく訪問も送信する">

訪問データには、それ以降のすべてのイベントが参照するアトリビューションパラメーターが含まれています。また、システムでは、同じユーザーからイベントを受信する前に、訪問データを受信することを前提としています。訪問データより先にイベントを送信した場合、そのイベントはオーガニックとして分類されます。

</Accordion>

<div id="h_01KZS2SFULLSVR03" />

<Accordion title="HTTP経由でファーストパーティCookieを設定する">

`afUserId`を設定するWeb SDKがないため、Cookieを自社で設定して管理する必要があります。JavaScriptで書き込むクライアントサイドCookieではなく、`Set-Cookie`レスポンスヘッダーで設定するHTTP Cookieとして実装してください。

この違いが重要である理由は、クライアントサイドCookie（`document.cookie`を使用して設定したCookie）の有効期限が短いためです。Safariでは最短7日間、ITPの対象となるドメインでは24時間で期限切れになる場合があります。Cookieの有効期限が切れると識別子がリセットされるため、再訪問したユーザーが新規ユーザーとして認識されます。一方、サーバーで設定したCookieにはこの上限が適用されず、ブラウザが許容する最大期間まで保持できます。たとえば、Chromeでは最大400日間保持できます。また、`HttpOnly`を指定すれば、ページ上のスクリプトや広告ブロッカーによるCookieの読み取りや削除を防ぐことができます。さらに、ページ上でスクリプトを実行する必要もありません。

Cookieを設定して読み取る手順は、次のとおりです。

1. Cookieを持たない訪問者から最初のリクエストを受信した際に、サーバー側で永続的かつ一意のID（UUIDなど）を生成します。
2. そのIDをファーストパーティCookieとして返します：

   ```
   Set-Cookie: af_web_id=<generated-id>; Max-Age=34128000; Path=/; Secure; HttpOnly; SameSite=Lax
   ```
3. それ以降のすべてのリクエストでは、受信したCookieヘッダーから値を読み取り、同じ値を再利用します。新しい値を生成しないでください。
4. AppsFlyerへのすべてのリクエストで、その値をリクエスト内の`user_id`オブジェクトに`appsflyer_id`として含めて送信します。

Cookieには任意の名前を付けることができます。AppsFlyerが読み取るのは送信された値であり、Cookieの名前ではありません。ただし、必ず自社のファーストパーティドメインからCookieを設定してください。

</Accordion>

<div id="h_01KZS2SFULLSVR04" />

<Accordion title="各リクエストで適切な識別子を送信する">

すべてのリクエストに`user_id`オブジェクトを含め、少なくとも`appsflyer_id`（Cookieの値）または`customer_user_id`（自社の内部ユーザーID）のいずれかを指定する必要があります。両方の値を利用できる場合は、両方を送信することでユーザー識別の精度が向上します。

留意すべき点は、Webサイトへの訪問時点では、ほとんどのユーザーが匿名であるということです。そのため、訪問データには必ず`customer_user_id`の値を含めてください。Webサイト上で発生するイベントについては、ユーザーを識別できた時点でcustomer\_user\_idを追加し、それ以降もCookieの値と併せて送信してください。ブラウザ以外で発生するイベントについては、以前に識別済みのセッションを通じてAppsFlyerがそのユーザーをすでに認識している場合に限り、`customer_user_id`のみを送信することもできます。

</Accordion>

<div id="things-to-consider" />

## 考慮事項

<div id="user-identification" />

<Accordion title="ユーザー識別">

すべてのリクエストで`user_id`のオブジェクトを指定する必要があります。以下のいずれかの識別子を必ず含めてください。

| 項目 | 型 | 説明 |
| --- | --- | --- |
| `customer_user_id` | string（1～64文字） | お客様のシステムで設定している内部ユーザー識別子です。 |
| `appsflyer_id` | string（1文字以上） | AppsFlyerがWebユーザーに付与する内部識別子です。AppsFlyer Web SDKを利用している場合は、`appsflyer_id`はWeb SDKのCookieから取得できます。`afUserId`を参照してください。詳しくは「[Web SDKの afUserID の抽出](#extracting-the-web-sdk-afuserid)」を参照してください。 |

</Accordion>

<div id="late-acceptance-windows" />

<Accordion title="遅延イベントの受付期間">

イベントおよびWeb訪問は、アプリのタイムゾーンにおける翌日の00:30までにAppsFlyerへ到着する必要があります。この期限を過ぎて受信したイベントは、イベントに含まれるタイムスタンプではなく、AppsFlyerが受信した時刻が使用されます。

</Accordion>

<div id="hashed-pii-fields" />

<Accordion title="ハッシュ化された個人情報（PII）項目">

すべての個人情報（PII）項目は、送信前にSHA256でハッシュ化する必要があります。ハッシュ化する前に、文字列は小文字へ変換し、前後の空白を削除して正規化してください。各ハッシュ値は、大文字・小文字を区別しない64文字の16進数文字列である必要があります。

* すべてのハッシュフィールドで使用するパターンは以下のとおりです：`^[a-fA-F0-9]{64}$`
* `phone_number_e164_hashed` を使用する場合は、電話番号をE.164形式（例：`+14155552671`）へ変換してからハッシュ化してください。

</Accordion>

<div id="extracting-the-web-sdk-afuserid" />

<Accordion title="Web SDKの afUserID の抽出">

* `afUserId` は、ユーザーが初めてWebサイトへアクセスした際に、Web SDKによって設定される一意の識別子です。
* `afUserId` が必要な場合は、以下のいずれかの方法で取得できます。

<div id="h_01HKW2YAW5FK04C3AWCXGP1XAW" />

#### **HTTP CookieヘッダーからafUserIdを取得する**

* `afUserId`は、ユーザーのブラウザからWebサイトへ送信されるHTTP Cookieヘッダーに含まれています。
* 必要に応じてHTTP Cookieヘッダーから取得してください。

<div id="h_01HKW2YAW5CT2WZ229KJD2FWYK" />

#### **ブラウザでafUserIdを確認する**

* トラブルシューティングやデバッグを行う場合は、ブラウザ上で`afUserId`を確認できます。
* afUserIdを確認するには、ユーザーがWeb SDKを組み込んだページへ少なくとも1回アクセスしている必要があります。
* `afUserId` を含むCookieは、お客様のドメインに対するファーストパーティCookieとして保存されます。
* 以下の手順はChrome 81を使用して作成しています。ブラウザやOSによって表示や操作方法が異なる場合があります。

**ブラウザからafUserIdを取得する：**

1. ブラウザでWebサイトを開きます。
2. ページ上で右クリックし、***Inspect***を選択します。ブラウザの開発者ツールが表示されます。
3. (A) ***Application***タブを開きます。
4. サイドメニューにて、(B)［Cookie］を開きます。
5. お客様のWebサイトを選択します。表示されない場合はブラウザを更新してください。
6. (C) ***フィルター欄***に`afUserId`と入力すると、afUserIdの値が表示されます。

</Accordion>

<div data-zendesk-anchors="about-the-s2s-api-for-web-attribution=web%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E5%90%91%E3%81%91s2s-api%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KP13TF66KEZ7F1TGAA7RGQ6G=web%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E5%90%91%E3%81%91s2s-api%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 how-it-works=%E4%BB%95%E7%B5%84%E3%81%BF h_01KP13TF66W8V5A40YT2XYWQ5K=%E4%BB%95%E7%B5%84%E3%81%BF why-use-s2s=s2s%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 h_01KP13TF671CF85KMYXFZE6W9D=s2s%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 api-specification=api%E4%BB%95%E6%A7%98 h_01KP13TF67N1FVEAD1C7RV25TY=api%E4%BB%95%E6%A7%98 authentication=%E8%AA%8D%E8%A8%BC h_01KP13TF67MHPEQ5J3H69RTQH5=%E8%AA%8D%E8%A8%BC h_01KT98N5SBW812PVXP165FCWR3=%E6%B3%A8%E6%84%8F measure-an-event=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%88%E6%B8%AC h_01KP13TF67QQC3F1YP9RZRNMTK=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%88%E6%B8%AC h_01KP13TF67Z0TZVNYPDYR2SXA6=path-parameter h_01KP13TF67PVQFVAAG5SYP7DPG=request-body h_01KP13TF68J9BT3SFGQKXFSM60=example-request h_01KP13TF68PX70V0K94WSHCX76=responses measure-a-visit=web%E8%A8%AA%E5%95%8F%E3%81%AE%E8%A8%88%E6%B8%AC h_01KP13TF68HMD8GSR6GSY95WYF=web%E8%A8%AA%E5%95%8F%E3%81%AE%E8%A8%88%E6%B8%AC h_01KP13TF681639XH9DBQYVX7SS=path-parameter::d8a9ef62 h_01KP13TF68ETEEM3ZX7JMFRXSD=request-body::f7fb791b h_01KP13TF68CDH9MB888HWA11JC=example-request::6283854b h_01KP13TF68FCDABJC64XC4V6EG=responses::5cfbc5cc h_01KZS2SFULLSVR01=%E5%AE%8C%E5%85%A8%E3%81%AA%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E3%82%B5%E3%82%A4%E3%83%89%E9%80%A3%E6%90%BA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B set-up-a-fully-server-side-integration=%E5%AE%8C%E5%85%A8%E3%81%AA%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E3%82%B5%E3%82%A4%E3%83%89%E9%80%A3%E6%90%BA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B send-visits-not-just-events=h_01KZS2SFULLSVR02 assign-a-first-party-cookie-via-http=h_01KZS2SFULLSVR03 send-the-right-identifiers-on-each-call=h_01KZS2SFULLSVR04 things-to-consider=%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 h_01KP13TF68F2T3P7P56A5EG2HW=%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 h_01KP13TF68GMKHGV9A34D98SYH=user-identification h_01KP13TF68JP8MFSFTZ1RP2Q3N=late-acceptance-windows h_01KP13TF68VD15WYQHBQK4YS0X=hashed-pii-fields h_01HKW2YAW52T0KME7P2CRQ6WBR=extracting-the-web-sdk-afuserid get-afuserid-from-the-http-cookie-header=http-cookie%E3%83%98%E3%83%83%E3%83%80%E3%83%BC%E3%81%8B%E3%82%89afuserid%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B h_01HKW2YAW5FK04C3AWCXGP1XAW=http-cookie%E3%83%98%E3%83%83%E3%83%80%E3%83%BC%E3%81%8B%E3%82%89afuserid%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B viewing-afuserid-in-the-visitors-browser=%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%81%A7afuserid%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B h_01HKW2YAW5CT2WZ229KJD2FWYK=%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%81%A7afuserid%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B" />
