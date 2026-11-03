---
title: データコラボレーションプラットフォーム（DCP） - コラボレーション計測の準備
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2025-01-27T08:47:05Z'
  edited_at: '2026-10-14T09:27:44Z'
  id: 32144170371985
  locale: ja
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/ja/articles/32144170371985
---
> **概要：** 計測データソースの作成方法と、アトリビューションジョブが処理できる形式でそれらにアクセスする方法を学びます。

## 概要

計測プロセスを設定する最初のステップは、コンバージョン、エンゲージメント、キャンペーンマッピングという、測定プロセスに必要な3つの入力データを準備することです。これらの入力データは、データ提供モード（アプリ内イベントまたはカスタムソースファイル）に応じて、事前に定義されたスキーマまたはイベント構造に基づいて準備する必要があります。

プロビジョニングモードがカスタムソースファイルの場合、必要なコンバージョンとエンゲージメントレコードのフォルダがクラウドにアップロードされると、アトリビューションジョブが自動的にトリガーされます。アプリ内のイベントモードでは、関連するアプリ内イベントが選択されたときにジョブがトリガーされます。

## アプリ内イベントを準備する

アプリに統合されたAppsFlyer SDKによって送信されるアプリ内イベントを介して、コンバージョンとエンゲージメントデータを送信できます。

> 📘 **注意**
>
> 既にAppsFlyerのアプリ内イベントをSDK経由またはサーバー間リクエスト経由で送信している場合は、カスタムソースファイルオプションよりもこのオプションの方が実装が容易かもしれません。

<div id="prepare-conversion-inapp-events" />

<Accordion title="アプリ内イベントコンバージョンイベントを準備する">

アプリ内のコンバージョンイベントには、ネストされたSKU情報を含める必要があります。`af_order_info`鍵。

```
"event_value": {
    "event_id": "<event_id>",
    "af_content": "retail",
    "af_order_id": "637f7c400f0e3fddd9e5bcbc",
    "af_order_info": [
        {
            "sku": "a",
            "revenue": 1.1,
            "qty": 2
        },
        {
            "sku": "b",
            "revenue": 100.5,
            "qty": 1
        }
    ]
}
```

アプリ内イベントの準備方法については、下記の[「アプリ内イベントの作成」](#create-inapp-events)セクションをご覧ください。

</Accordion>

<div id="prepare-engagement-inapp-events" />

<Accordion title="リエンゲージメントアプリ内イベント">

<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#onsite-and-offsite-campaign-measurement">オンサイトキャンペーンは、</Anchor>アプリ内イベントを通じてエンゲージメントを獲得できます。エンゲージメントアプリ内のイベントには、アトリビューションデータを含める必要があります。`event_value`鍵。例えば、以下をご覧ください。`event_value` JSON構造：

```
"event_value": {
    "ad_name": "Spring_Sale_Ad_01",
    "ad_id": "ad_123456",
    "ad_type": "video",
    "adset_name": "Spring_Sale_Set_A",
    "adset_id": "adset_7890",
    "campaign_name": "Spring_2025_Promo",
    "campaign_id": "camp_456123",
    "channel": "facebook",
    "media_source": "meta_ads",
    "engagement_type": "click",
    "event_id": "evt_20250410_001"
}
```

以下のフィールドをご使用いただけます`evant_value`JSONキー：

| **フィールド** | **説明** | **必須** | **アプリ内のイベントスキーマ内で利用可能** | **タイプ** |
| --- | --- | --- | --- | --- |
| `campaign_id` | Campaign ID | はい | いいえ | `string` |
| `campaign_name` | キャンペーン名 | いいえ | いいえ | `string` |
| `engagement_type` | クリック数とインプレッション数を区別する | はい | いいえ | `string` |
| `media_source` | <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">イベントに帰属または制限されたメディアソース</Anchor> | はい | いいえ | `string` |
| `ad_id` | Ad ID | いいえ | いいえ | `string` |
| `ad_name` | 広告名 | いいえ | いいえ | `string` |
| `ad_type` | 例: バナー、フッター | いいえ | いいえ | `string` |
| `adset_id` | 広告セットIDは、1つ以上の広告を含むグループを識別します。 | いいえ | いいえ | `string` |
| `adset_name` | 広告セット名。1つ以上の広告を含むグループを識別します。 | いいえ | いいえ | `string` |
| `channel` | メディアソースチャネル。例:Googleの例ではYouTube、Meta広告の例ではInstagram。 | いいえ | いいえ | `string` |

アプリ内イベントの準備方法の詳細については、以下の「アプリ内イベントの作成」セクションをご覧ください。

</Accordion>

<div id="create-inapp-events" />

<Accordion title="アプリ内イベントを作成する">

アプリ内イベントを通じてコンバージョンとエンゲージメントデータを取得するには、アプリに統合されたAppsFlyer SDKを設定してください。アプリ内イベントの作成に関する詳細については、以下を参照してください。

* <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">アプリ内イベントの概要</Anchor>
* <Anchor target="_blank" href="http://dev.appsflyer.com/hc/docs/in-app-events-sdk">デベロッパー向けAppsFlyer SDKでアプリ内イベントを実装する</Anchor>

</Accordion>

## カスタムソースファイルを準備する

[オンサイトキャンペーンを](#onsite-and-offsite-campaign-measurement)実行中いる場合は、以下の表に示されているスキーマに従って、カスタムソースファイルをコンバージョンとエンゲージメントのソースとして使用できます。

<div id="the-conversion-source-scheme" />

<Accordion title="コンバージョンカスタムソースを準備する">

コンバージョンのカスタムソースファイルを作成するには、以下の表のスキームを使用する。   
コンバージョンスキームは、オフサイトキャンペーンとオンサイトキャンペーンの種類、および異なるメディアパートナーに対して統一されています。

#### メディアパートナー：

GGoogle

百万Meta

#### 背景色

こちらは必須項目です。

推奨項目

      選択されたフィールドのいずれかが必須です

      フィールドはSRNで規定されたルールに従ってハッシュ化されます。

<table><colgroup><col/><col/><col/><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th>カテゴリ</th><th>パラメータ</th><th>説明</th><th>データの型</th><th>CMN</th><th colspan="4">メディアパートナー</th></tr><tr><th></th><th></th><th></th><th></th><th></th><th colspan="2">App</th><th colspan="2">Web</th></tr><tr><th></th><th></th><th></th><th></th><th></th><th>G</th><th>百万</th><th>G</th><th>百万</th></tr></thead><tbody><tr><td>Event</td><td>event_id</td><td>イベントの一意の識別子。</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>event_name</td><td>イベントの名前または種類（例：「購入」、「クリック」）。</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>event_time</td><td>イベントが発生した時刻のタイムスタンプ。</td><td>日時</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>アプリ情報</td><td>app_id</td><td>アプリケーションの一意の識別子。</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>app_name</td><td>アプリの名前</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>app_version</td><td>アプリケーションのバージョン番号。</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td>アトリビューションデータ</td><td>facebook_browser_id</td><td>Facebookブラウザトラッキング用の固有識別子。</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_cookie</td><td>Facebook広告のアトリビューションのためのクリック識別子。</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>gbraid</td><td>Google広告アトリビューション識別子。</td><td>string</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td> </td><td>google_click_id</td><td>Google広告のクリックトラッキング用の固有ID 。</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>wbraid</td><td>Googleの Web ベースのアトリビューション識別子。</td><td>string</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td> </td><td>tiktok_id</td><td>TikTokトラッキング用の固有識別子。</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>キャンペーンデータ</td><td>campaign_id</td><td>マーケティングキャンペーンの固有識別子。</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>install_id</td><td>アプリインストールイベントの識別子。</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td>Conversion Data</td><td>SKU</td><td>コンバージョンに関係する製品のSKU。</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>sku_quantity</td><td>製品の固有識別子（SKU）。</td><td>整数</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>sku_revenue</td><td>購入または関連するSKUの数量。</td><td>Decimal（少数）</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>event_revenue</td><td>イベントによって生み出された収益。</td><td>Decimal（少数）</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>event_revenue_currency</td><td>収益金額の通貨。</td><td>Decimal（少数）</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Device info</td><td>client_ip</td><td>ユーザーまたはデバイスのIPアドレス。</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>client_user_agent</td><td>ユーザーのデバイス/ブラウザから取得したユーザーエージェント文字列。</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>device_category</td><td>ユーザーのデバイスのカテゴリ（例：モバイル、デスクトップ）。</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>プラットフォーム（OS？）</td><td>ユーザーのデバイスのオペレーティングシステム（例： iOS、 Android）。</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>os_version</td><td>デバイスのオペレーティングシステムのバージョン。</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td>ユーザーID</td><td>advertising_id</td><td>広告目的で使用される固有識別子（例：IDFA）。</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>appsflyer_id</td><td>Appsflyer経由でトラッキングための固有ID 。</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>android_id</td><td>Android端末固有の識別子。</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>idfa</td><td>IDFA（広告用識別子）</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>idfv</td><td>ベンダー識別子（iOS）。</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>client_id</td><td>固有のクライアント識別子（システムによって生成されるものなど）。</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_client_id</td><td>ルールは指定されていません</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>tiktok_hashed_client_id</td><td>トリム、小文字</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>Cookie</td><td>ユーザー/セッショントラッキングのためのブラウザクッキーデータ。</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>first_name</td><td>ユーザーのファーストネーム。</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>last_name</td><td>ユーザーの姓。</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>phone_number</td><td>ユーザーの電話番号。</td><td>整数</td><td></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>date_of_birth</td><td>ユーザーの生年月日。</td><td>日時</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>性別：</td><td>ユーザーの性別。</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>language</td><td>ユーザーが希望する言語または地域。</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>メール</td><td>ユーザーのメールアドレス。</td><td>string</td><td></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>tiktok_hashed_email</td><td>Googleメールアドレスの文字をトリミング、小文字化、ドット削除する</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>tiktok_hashed_phone</td><td>E164</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>google_hashed_email</td><td>Googleメールアドレスの文字をトリミング、小文字化、ドット削除する</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>google_hashed_phone</td><td>E164</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>google_hashed_first_name</td><td>トリム、小文字</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>google_hashed_last_name</td><td>トリム、小文字</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>facebook_hashed_email</td><td>トリム、小文字</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_phone</td><td>カスタムフォーマット（+?なし）</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_first_name</td><td>小文字、句読点なし</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_last_name</td><td>小文字、句読点なし</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_date_of_birth</td><td>YYYYMMDD</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_gender</td><td>f/m が推奨されますが、ハッシュ値であればどれでも構いません。</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td>ユーザー属性</td><td>att_status</td><td>ユーザーの同意に関するApp Tracking Transparency (ATT)ステータス。</td><td>string</td><td></td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td>Device location</td><td>region</td><td>ユーザーの地理的地域。</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>city</td><td>ユーザーに関連付けられている都市。</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>州</td><td>ユーザーの州または県。</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>country_code</td><td>ユーザーの国のISOコード。</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>zip_code</td><td>ユーザーの郵便番号。</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>通り</td><td>利用者の住所（利用可能な場合）。</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>google_hashed_street</td><td>トリム、小文字</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>facebook_hashed_city</td><td>小文字、句読点なし、スペースなし</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_state</td><td>米国規格ANSI、小文字、句読点なし、スペースなし</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_zip_code</td><td>米国/英国向けの特別なルール：小文字、句読点なし、スペースなし</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_country_code</td><td>ISO 3166-1 alpha-2 の 2 文字国コード（小文字）</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td>紹介/トラフィックデータ</td><td>referrer_url</td><td>ユーザーを現在のページに誘導したサイトのURL 。</td><td>string</td><td></td><td></td><td></td><td></td><td>✓</td></tr><tr><td> </td><td>source_url</td><td>ユーザーが最初にキャンペーンに接触した際のソースURL 。</td><td>string</td><td></td><td></td><td></td><td></td><td>✓</td></tr></tbody></table>

</Accordion>

<div id="the-engagement-source-scheme" />

<Accordion title="エンゲージメントのカスタムソースを準備します">

以下のスキーマを使用する、エンゲージメントデータソースを作成します。

> 📘 **注意**
>
> エンゲージメントソーススキームにマッピングされた個人識別情報（PII）フィールドは、上記のコンバージョンソーススキームにマッピングされたPIIと重複しない共通部分を持つ必要があります。

| **フィールド** | **説明** | 必須 | **期待値タイプ** |
| --- | --- | --- | --- |
| `appsflyer_id` | アプリがデバイスにインストールされたときにSDKによって生成される一意のID。 | 個人情報（PII）の入力欄（任意）。個人情報欄のうち、いずれか1つは必須項目です。 | `string` |
| `cuid` | アプリ所有者によって設定される一意のアプリユーザーID。 | 個人情報（PII）の入力欄（任意）。個人情報欄のうち、いずれか1つは必須項目です。 | `string` |
| `idfa` | iOSデバイス向け、ユーザーがリセット可能な広告ID 。利用できない場合は、ゼロが入力されます。 | 個人情報（PII）の入力欄（任意）。個人情報欄のうち、いずれか1つは必須項目です。 | `string` |
| `idfv` | iOSが提供するベンダーID | 個人情報（PII）の入力欄（任意）。個人情報欄のうち、いずれか1つは必須項目です。 | `string` |
| `app_id` | AppsFlyer内の一意のアプリ識別子。例： iOS：`id123456789` 、 Android： `com.appsflyer.referrersender` | オプション | `string` |
| `campaign_id` | Campaign ID | 必須 | `string` |
| `campaign_name` | キャンペーン名 | オプション | `string` |
| `media_source` | <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">イベントに帰属または制限されたメディアソース</Anchor> | 必須 | `string` |
| `engagement_type` | クリック数とインプレッション数を区別する | 必須 | `string` |
| `event_name` | 広告主が設定 | 必須 | `string` |
| `event_time` | イベント時間は最も近い時間に切り捨てられます | 必須 | `datetime` |
| `app_name` | 広告主が設定 | オプション | `string` |
| `app_version` | 広告主が設定 | オプション | `string` |
| `ad_id` | Ad ID | オプション | `string` |
| `ad_name` | 広告名 | オプション | `string` |
| `ad_type` | 例: バナー、フッター | オプション | `string` |
| `adset_id` | 広告セットIDは、1つ以上の広告を含むグループを識別します。 | オプション | `string` |
| `adset_name` | 広告セット名。1つ以上の広告を含むグループを識別します。 | オプション | `string` |
| `channel` | メディアソースチャネル。例:Googleの例ではYouTube、Meta広告の例ではInstagram。 | オプション | `string` |
| `platform` | デバイスプラットフォーム：iOS、Android、またはWindows Mobile | オプション | `string` |

</Accordion>

データソースの準備方法やクラウドサービスへのアップロード方法の詳細については、このドキュメントの[「カスタムデータソースの作成と接続」](#カスタムデータソースを作成して接続する)セクションを参照してください。

## キャンペーンマッピングソースを準備する

キャンペーンマッピングデータのソースは、以下の表に示すスキーマを持つカスタムデータソースファイルです。

> 📘 **注意**
>
> メンテナンスや更新が容易になるため、すべてのコラボレーションに単一のマッピングファイルを使用することをお勧めします。

<div id="the-campaign-mapping-scheme" />

<Accordion title="キャンペーンマッピング計画">

以下のスキーマを使用する、キャンペーンマッピングソースを作成します。

| **フィールドタイプ** | （必須） | **期待値** | **説明** |
| --- | --- | --- | --- |
| collaborator\_name | はい | string | 一緒に作業する共同作業者の名前。 |
| collaborator\_id | はい | string | 共同作業者固有の識別子。 |
| campaign\_id | はい | string | キャンペーンの固有識別子。 |
| conversion\_targets | はい | 文字列配列 | キャンペーン対象のSKUをカンマ区切りで指定したいパラメータです（例：sku1、sku2など）。 |
| campaign\_name | いいえ | string | キャンペーン名 |

</Accordion>

ソースファイルの作成方法とクラウドサービスへのアップロード方法の詳細については、このドキュメントの[「カスタムデータソースの作成と接続」](#カスタムデータソースを作成して接続する)セクションを参照してください。

## アトリビューションジョブの取り込みフロー

各アトリビューションジョブは1日専用で、その日の終了後に実行されます。このプロセスの開始時に、ジョブはクラウドサービスまたはアプリ内イベントから関連するコンバージョン、エンゲージメント、およびキャンペーンマッピングデータを取り込みます。

<div id="campaign-mapping-source-ingestion" />

<Accordion title="キャンペーンマッピングソースの取り込み">

各アトリビューション実行するの前に、DCPはカスタムソースからキャンペーンマッピングレコードを読み込みます。これらのレコードを読み込むには、次の2つのモードから選択できます。

* **最新戦略**：DCPは、記録のアップロード日を基準に、最新の記録を取得します。

  例えば、ソースに1月18日、1月17日、または12月29日のアップロード日を持つレコードが含まれている場合、システムは1月18日の日付を持つレコードを選択します。
* **日々の戦略**：DCPは、アップロード日が帰属実行する日と一致するレコードのみを取り扱います。例えば、実行するが1月19日の午前0時に行われた場合、システムは1月19日にアップロードされたキャンペーン記録のみを選択します。

</Accordion>

<div id="conversion-source-ingestion" />

<Accordion title="変換ソースの取り込み">

DCP は、その日の終了時に、<strong>その日専用のフォルダとその中のコンバージョンレコードにアクセスできる場合にのみ、</strong>その日のアトリビューション ジョブを実行します。ただし、特定の日付のフォルダは後日アップロードすることも可能です。例えば、1月17日のフォルダを1月22日にアップロードすることができます。

* DCPは毎日終業時に、その日のアトリビューション処理を実行します。<strong>DCPがその日のフォルダを見つけることができた場合にのみ、</strong>ジョブが実行するます。フォルダ名は日付名と同じです。
* 日別フォルダには、フォルダ作成日から遡って30日間のイベント記録を含めることができます。例えば、1月17日のフォルダでは、ジョブは12月18日から1月17日までのレコードを処理します。
* 特定の日付にフォルダのアップロードをスキップした場合、30日以内にアップロードする必要があります。例えば、1月17日のフォルダのアップロードをスキップした場合、2月17日までアップロードすることができます。ただし、フォルダ作成日にできるだけ近い時期にアップロードすることをお勧めします。
* DCPが当日のフォルダを見つけられない場合、次の7日間は10分ごとにフォルダの検索を続けます。

</Accordion>

<div id="engagement-source-ingestion" />

<Accordion title="エンゲージメントソースの取り込み">

DCPは、各コンバージョンレコードについて、そのレコードをトリガーしたエンゲージメントイベントを検索します。

* エンゲージメント記録は日付入りのファイルに保管されています。ただし、毎日エンゲージメントフォルダをアップロードする必要はありません。例えば、1月14日のフォルダをアップロードせずに、1月13日と1月15日のフォルダをアップロードすることができます。この例では、1月15日のフォルダから1月14日の記録が取得されます。
* <strong>特定のコンバージョンフォルダに対するアトリビューションジョブは、そのコンバージョンフォルダと同じ日付、またはそれ以降の日付のエンゲージメントフォルダが存在する場合にのみ開始されます。</strong>例えば、1月17日の**コンバージョン**フォルダのアトリビューションジョブは、1月17日のエンゲージメントフォルダ、または1月18日などのそれ以降の日付のフォルダが存在する場合にのみ開始されます。
* アトリビューションジョブは、エンゲージメントルックバック期間内に該当するすべてのエンゲージメントイベントを収集します。

</Accordion>

<div id="inapp-data-ingestion" />

<Accordion title="アプリ内データ取り込み">

コンバージョンデータとエンゲージメントデータは、アプリ内イベント、カスタムソース、またはその両方の組み合わせから取得できます。DCPでは、単一のモードを使用するか、複数のモードを組み合わせるかを選択できます。これにより、コンバージョンはアプリ内イベントから発生させ、エンゲージメントはカスタムファイルから取得する、あるいはその逆も可能です。

コンバージョン、エンゲージメント、またはその両方に関するアプリ内イベントを設定する際には、アプリIDとコンバージョンまたはエンゲージメントイベント名を指定する必要があります。最終的に、アトリビューションジョブは、指定された名前とアプリIDを持ち、かつコンバージョン日と同じイベント日付を持つすべてのイベントを選択します。

</Accordion>

## カスタムデータソースを作成して接続する

カスタムソースを介してデータを接続するには、まず以下のDCPナレッジベース記事の手順に従う必要があります。

* <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">データコラボレーションプラットフォーム — クラウドサービスの設定</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-add-connections">データコラボレーションプラットフォーム — 接続を追加する</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources">データコラボレーションプラットフォーム - ソースの作成と管理</Anchor>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01JJKFW5Z2D7Y1MM5A7YR0TY0T=%E6%A6%82%E8%A6%81 prepare-inapp-events-for-conversions-and-engagements=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E6%BA%96%E5%82%99%E3%81%99%E3%82%8B h_01JJKFW5Z22DG4CKFMXPGR3BW0=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E6%BA%96%E5%82%99%E3%81%99%E3%82%8B h_01JJKFW5Z2NP9187GYHS0YEXED=%E6%B3%A8%E6%84%8F h_01JJKFW5Z2AX7SHHZ23P0KDQJY=prepare-conversion-inapp-events h_01JJKFW5Z2YD0B151VSR3TG6SP=prepare-engagement-inapp-events h_01JJKFW5Z3QES9BAZX7KNSPCM8=create-inapp-events prepare-custom-source-files-for-engagements-and-conversions=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%82%92%E6%BA%96%E5%82%99%E3%81%99%E3%82%8B h_01JJKFW5Z3QX33NK3XP452AAFB=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%82%92%E6%BA%96%E5%82%99%E3%81%99%E3%82%8B h_01JK3QFQCK30A7SSPWXSH3VP0D=the-conversion-source-scheme media-partners=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC h_01K399C7NME67HQGJKRG1A5JB2=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC background-colors=%E8%83%8C%E6%99%AF%E8%89%B2 h_01K399DC8ZAEA86DD4W0181EM6=%E8%83%8C%E6%99%AF%E8%89%B2 h_01JK3QFQCKD1TV5G4N0KP85AWS=the-engagement-source-scheme h_01JK3QFQCK6C16SCW8EYQNS47F=%E6%B3%A8%E6%84%8F-1 prepare-campaign-mapping-source=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E6%BA%96%E5%82%99%E3%81%99%E3%82%8B h_01JJKFW5Z3QR107P3M111P4STG=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E6%BA%96%E5%82%99%E3%81%99%E3%82%8B h_01JJKFW5Z3ZSYET4HMWD7TWSD8=%E6%B3%A8%E6%84%8F-2 h_01JJKFW5Z3Q6F3DP0EMTNQRD8R=the-campaign-mapping-scheme prepare-data-for-attribution-job-ingestion=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%B8%E3%83%A7%E3%83%96%E3%81%AE%E5%8F%96%E3%82%8A%E8%BE%BC%E3%81%BF%E3%83%95%E3%83%AD%E3%83%BC h_01JJKFW5Z38W581F4CBW3T4CPZ=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%B8%E3%83%A7%E3%83%96%E3%81%AE%E5%8F%96%E3%82%8A%E8%BE%BC%E3%81%BF%E3%83%95%E3%83%AD%E3%83%BC h_01JK5R1VPJ0WAF3WX4R1ECE0R7=campaign-mapping-source-ingestion h_01JK5R1VPJT41RF2EN8806ZY5C=conversion-source-ingestion h_01JK5R1VPJN8KTFTN21DA3619Y=engagement-source-ingestion h_01JK5R1VPJV6F5Y5JB3Q45R89B=inapp-data-ingestion create-and-connect-custom-data-sources=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E4%BD%9C%E6%88%90%E3%81%97%E3%81%A6%E6%8E%A5%E7%B6%9A%E3%81%99%E3%82%8B h_01JJKFW5Z3NKB0MB7GN2FC87H5=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E4%BD%9C%E6%88%90%E3%81%97%E3%81%A6%E6%8E%A5%E7%B6%9A%E3%81%99%E3%82%8B" />
