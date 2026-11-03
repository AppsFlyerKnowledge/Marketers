---
title: PBA向け Web Server-to-ServerイベントAPI（Web-S2S）
metadata:
  keywords:
    - SDK
    - Developers
    - pba
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-03-23T23:59:00Z'
  edited_at: '2026-10-14T09:31:48Z'
  id: 360006997298
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/360006997298
---
> **概要：** Web Server-to-Server（Web-S2S）イベントAPIを使用すると、Web SDKでは送信されないイベントやコンバージョンをPBAへ送信できます。

[![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)

## PBA向け Web Server-to-ServerイベントAPI

People-Based Attribution（PBA）向けのWeb-S2S APIは、<Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide">Web SDK</Anchor>を補完する仕組みであり、マーケターがWeb SDKの対象外となるウェブサイト上のイベントをレポートできるようにします。たとえば、Webサイト訪問者（Webユーザー）がオンライン決済イベントを発生させ、その処理がバックエンドシステムで行われる場合、処理完了後にバックエンドはS2S APIを使用して、そのイベントをAppsFlyerへ送信します。

S2S APIで送信されたイベントは以下のように扱われます。

* Web SDKから送信されたイベントと同様に記録される
* コンバージョンイベントとして設定されている場合、PBAダッシュボードに表示される
* PBA Raw Dataに記録され、*event\_sourceのフィールド*には web S2S として設定される

## API利用手順

以下のセクションを参考にAPIコールを作成してください。

| No. | 項目 | 備考 |
| --- | --- | --- |
| 1 | ユニークユーザーID | <ul><li>可能な限り最も適切なユーザーIDを送信してください。これはデータ分析に大きく影響します。</li><li>ベストプラクティスは customerUserId の送信です。利用できない場合は afUserId（Web SDKが設定するCookie ID） を送信してください。</li><li>顧客ユーザーID（<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">CUID</Anchor>）と[afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid)を関連付ける場合は、両方のIDを含めて setCuID() メッセージを送信します。</li></ul> |
| 2 | タイムスタンプ | <ul><li>AppsFlyerはイベントのタイムスタンプに対して厳格な検証を行います。</li></ul><ul><li>**遅れて到着したイベント：** イベントは、本来の発生日から24時間以内に送信された場合、元のタイムスタンプで記録されます。**たとえば**、月曜日 23:59（UTC）のイベントは**火曜日 23:59:59（UTC）まで**に送信すれば元の時間を保持しますが、火曜日 23:59:59 UTC 以降に送信された場合にはサーバー受信時間に上書きされます。</li><li>**未来のタイムスタンプ：** 実際の受信時間より未来のタイムスタンプは許可されません。この場合もサーバー受信時間に上書きされます。</li></ul><ul><li>※タイムスタンプはUTCベースです。 必要に応じてローカル時間からUTCへ変換してからパラメータに記載してください。</li></ul> |
| 3 | 収益金額と通貨設定 | *eventRevenueCurrency* と *eventRevenue* は、eventValue 内に含まれている場合でも必ず送信してください。これらの情報が管理画面上で使用されます。 |

<div id="api-basics" />

<Accordion title="API基本情報">

APIの実装には、管理画面から取得できる以下の認証情報が必要です。

* Bundle ID（Brand Bundle ID）
* Web Dev key

**認証情報の取得方法：**

1. AppsFlyerの上部メニューから**マイアプリ** > **ブランドバンドルを表示*を選択します。***バンドルの一覧が表示されます。
2. 適切な内容をコピーして記録します：
   * ***Brand bundle ID***
   * ***Web dev key***

#### Web S2S API 基本仕様

| エンドポイント | `https://webs2s.appsflyer.com/v1/bundleId/method`<ul><li>`bundleId`：ダッシュボードに表示されるアプリのBundle ID</li><li>`method` 次のいずれかを実行してください：<ul><li>[event：](/docs/web-server-to-server-events-api-for-pba-web-s2s#event-method)バックエンドイベント送信用</li><li>[setCuId：](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method) afUserIdとCUIDを関連付ける場合</li></ul></li></ul> |
| --- | --- |
| HTTP method | `POST` |
| Content Type | `application/json` |
| JSON payload 制限 | 最大サイズ：1KB |
| レート制限 | POSTリクエスト上限：1分あたり60,000リクエストまで上限を増やしたい場合はCSMへ連絡してください。 |
| TLS | <ul><li>TLS 1.2以上</li><li><Anchor target="_blank" href="/marketers/ja/docs/appsflyer-https-ssl-encryption-policy-support#送信メッセージappsflyerがクライアントとなる場合">Ciphersもサポートしています</Anchor></li></ul> |

</Accordion>

<div id="setcuid-method" />

<Accordion title="setCuId メソッド">

| メソッド名 | setCuId |
| --- | --- |
| ユースケース | CUIDをWeb訪問者に紐づける場合に使用します。Webの `afUserId` と自社の customerUserId を紐づける場合が該当し、これによりPBAは複数データソース間のデータをマッチングできます。これはWebサイトで使用する <Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">setCustomerUserId</Anchor> と同様の仕組みです。 |
| メソッドパス | `https://webs2s.appsflyer.com/v1/bundleId/setcuid` |
| Payload | JSON payloadはこちらに記載されたパラメータで構成され、すべてのパラメーターは必須です。<ul><li>[customerUserID](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method)</li><li>[afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid)</li><li>[webDevKey](/docs/web-server-to-server-events-api-for-pba-web-s2s#webdevkey)</li></ul> |

#### setCuIdの Curl サンプル

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/setcuid' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
        "webDevKey" : "99999999-9999-9999-9999-999999999999"}
```

</Accordion>

<div id="event-method" />

<Accordion title="Event メソッド">

| メソッド名 | event |
| --- | --- |
| ユースケース | 送信 |
| メソッドパス | `https://webs2s.appsflyer.com/v1/bundleId/event` |
| 詳細情報 | この記事の[イベントメソッドの詳細](/docs/web-server-to-server-events-api-for-pba-web-s2s#event-メソッドの詳細)セクションには、Payloadの詳細、Curlの例、Pythonの例、およびテストに関する推奨事項が含まれています。 |

</Accordion>

## Event メソッドの詳細

<div id="payload-parameters" />

<Accordion title="Payload パラメータ">

Payload パラメーターは、ユーザー識別子とイベントパラメータに分かれています。

* User ID：少なくとも1つのユーザーIDパラメータを送信する必要があります。
* Event：必須パラメータと、必要に応じてオプションのパラメータを送信してください。

#### ユーザーIDパラメータ（少なくとも1つのパラメータを送信）

| ユーザーIDパラメータ | 説明 |
| --- | --- |
| <span id="customeruserid"></span>customerUserID | <Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">顧客ユーザーID (CUID)</Anchor> はお客様が設定した一意の識別子です。<ul><li>AppsFlyerに送信するすべてのイベントで同一IDを使用する必要があります。つまり、同じIDが Web SDK、モバイル SDK、および S2S API で使用されています。</li><li><Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">Web SDKの顧客ユーザーID</Anchor></li><li>形式：文字列</li><li>例：`"customerUserId" : "663274"`</li><li>ローデータで入力される項目：`customer_user_id`</li></ul> |
| <span id="afuserid"></span>afUserId | Web SDKがユーザーのサイト訪問時に付与するユーザーIDです。このCookie値をバックエンドサーバーへ送信する必要があります。<ul><li>Cookie の詳細：<ul><li>名称：afUserId</li><li>値：*afUserId* をこの値に設定してください。</li><li>ドメイン：website-domain</li></ul></li><li>例： `"afUserId" : "unique_cookie_uuid"`</li><li>ローデータで入力される項目：`af_web_id`</li></ul> |

#### イベントパラメーター

| パラメータ名 | 必須 | 説明 |
| --- | --- | --- |
| <span id="webdevkey"></span>webDevKey | 必須 | 管理画面から取得できる [Web Dev Key](/docs/web-server-to-server-events-api-for-pba-web-s2s#getting-the-web-dev-key) を使用して入力してください。<ul><li>例：`"webDevKey" : "ffffffff-ffff-ffff-ffff-ffffffffffff"`</li></ul> |
| <span id="eventtype"></span>eventType | 必須 | AppsFlyerが内部で使用するイベント属性の識別子です。常に *EVENT* で設定してください。<ul><li>例：`"eventType" : "EVENT"`</li></ul> |
| <span id="eventname"></span>eventName | 必須 | <ul><li>このパラメータは、PBA設定でマーケティング担当者が設定した<Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings#web-event-settings">イベントコンバージョンリスト</Anchor>を使用して、コンバージョンとコンバージョンでないイベントを区別するために使用されます。</li><li>マーケティング担当者のコンバージョンロジックと一致する値を入力してください。</li><li>形式：文字列</li><li>例：`"eventName" : "web_purchase"`</li><li>ローデータで入力される項目：`event_name`</li></ul> |
| <span id="timestamp"></span>timestamp | 任意 | イベントが発生した時間（ミリ秒単位）です。13桁の <Anchor target="_blank" href="https://www.unixtimestamp.com/">Unix タイムスタンプ</Anchor>として送信してください。<ul><li>タイムスタンプが送信されない場合は、サーバー時刻が使用・設定されます。</li><li>**遅れて到着したイベントには、現在のサーバ時刻がタイムスタンプとしてが使用されます** これは、イベントが発生した翌日の午前0時（UTC）よりも後にデータが届いた場合に適用されます。例えば、月曜日に発生したイベントは、UTCタイムゾーンで火曜日の深夜までに処理される**必要があります**。</li><li>未来のタイムスタンプ（現在のサーバー時刻との比較）を持つイベントはサーバー時刻でタイムスタンプが記録されます。</li><li>形式：Int</li><li>例：`"timestamp" : 1584835200123`</li><li>ローデータで入力される項目：`event_time`</li></ul> |
| <span id="eventvalue"></span>eventValue | 任意 | イベントの詳細を説明する、イベントパラメータの一覧です。このパラメーターを使用して、製品、アイテム価格などの情報をアプリ内イベントで送信してください。<ul><li>**収益に関する注意点**：このパラメーターに収益の詳細データを入力してください。さらに、*eventRevenue* と *eventRevenueCurrency* を入力する必要があります。</li></ul><ul><li>形式：JSON</li><li>例： SKU ABC123を送信するために、青色で単価が$3.99のイベント値を設定する場合：<br />`{"Purchase": {"sku" : "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}}`</li><li>制限： 1000文字を超えないようにしてください。超過したものは切り捨てられます。</li><li>ローデータで入力される項目：`event_value`</li></ul> |
| <span id="eventrevenuecurrency"></span>eventRevenueCurrency | 任意 | 収益イベントの通貨コードです。3文字で構成されている <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> 通貨コードを設定してください。<ul><li>デフォルト：USD</li><li>形式：文字列</li><li>例：  `"eventRevenueCurrency" : "EUR"`</li><li>ローデータで入力される項目：`event_revenue_currency`</li></ul> |
| <span id="eventrevenue"></span>eventRevenue | 任意 | イベントに紐づく収益額（通貨値）です。<br /><br />**注意：** 収益が *eventValue* でレポートされている場合は、*eventRevenue* でも値を送信し、eventRevenueCurrency を添えてください。<ul><li>負の値も入力できます。（例：ユーザーによる返金など）</li><li>形式：Float</li><li>値の例：`1``1.2``1234.20``-1234.20`</li><li>ローデータで入力される項目：`event_revenue`</li></ul> |
| <span id="eventcategory"></span>eventCategory | 任意 | このパラメーターは非推奨で、廃止日以降（今後発表予定）に削除されます。代わりに eventValue を使用してください。 |
| <span id="eventlabel"></span>eventLabel | 任意 | このパラメーターは非推奨で、廃止日以降（今後発表予定）に削除されます。代わりに eventValue を使用してください。 |
| <span id="referrer"></span>referrer | 任意 | HTTP referrer<ul><li>形式：文字列</li><li>例：`"referrer" : "https://www.google.com/"`</li><li>ローデータで入力される項目：`http_referrer`</li></ul> |
| <span id="useragent"></span>userAgent | 任意 | ブラウザからサーバーに送信される <Anchor target="_blank" href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent">User-agent リクエスト</Anchor> です。<ul><li>デバイスタイプを判断するのに役立ちますので、できる限りこの値を送信してください。</li><li>形式：文字列</li><li>例：`"userAgent" : "Chrome/80.0.3987"`</li><li>ローデータで入力される項目：`user_agent`</li></ul> |
| <span id="ip"></span>ip | 任意 | ユーザーのIPアドレスです。<ul><li>可能な限り、この項目の値を送信してください。これは、ユーザーの<Anchor target="_blank" href="/marketers/ja/docs/determine-user-location">地理情報</Anchor> を決定するのに役立ちます。</li></ul><ul><li>形式：文字列</li><li>例： `"ip": "192.0.2.1"`</li><li>ローデータで入力される項目：`ip`</li></ul> |

</Accordion>

<div id="curl-example" />

<Accordion title="Curl サンプル">

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/event' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey" : "99999999-9999-9999-9999-999999999999",
    "ip" : "192.0.2.1",
	"eventType":"EVENT",
	"timestamp" : 1234567890123,
	"eventName":"my_web_event",
	"eventRevenueCurrency" : "EUR",
	"eventRevenue" : 1234.56,

		"eventValue": {
		"purchase":{
		 "shoes": "color",
		 "quantity" : "3",
		 "Revenue" : "1234.56",
		 "Currency" : "ZAR"
		}
	}

}'
```

</Accordion>

<div id="python-example" />

<Accordion title="Python サンプル">

```python
''' using the requests python package, install using pip install requests  '''
import requests
url = "https://webs2s.appsflyer.com/v1/bundleId/event"
payload = {
    "customerUserId": "1234567890abcdef",
    "afUserId": "9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey": "99999999-9999-9999-9999-999999999999",
    "ip": "192.0.2.1",
    "eventType": "EVENT",
    "timestamp": 1234567890123,
    "eventName": "my_web_event",
    "eventRevenenuCurrency": "EUR",
    "eventRevenue": 1234.56,
    "eventValue":
        {
            "purchase":
            {
                "shoes": "color",
                "quantity": "3",
                "Revenue": "1234.56",
                "Currency": "ZAR"
            }
        }
    }
headers = {
    'Accept-Encoding': 'application/json',
    'Content-Type': 'application/json'
}
response = requests.request("POST", url, headers=headers, json=payload)
print(response.text.encode('utf8'))
```

</Accordion>

<div id="testing" />

<Accordion title="テスト">

テスト時は以下の手順でイベントを送信してください。

1. イベントを送信する
2. HTTPレスポンス 200 OK を確認 / エラーがあればメッセージに従い修正
3. UTCタイムゾーンの午前0時のあと数時間待機し、PBA Raw Dataにイベントが表示されるまで待つ（PBAデータの処理は1日1回のみのため）

</Accordion>

## 追加情報

<div id="getting-the-web-dev-key" />

<Accordion title="Web Dev Key の取得">

**Web Dev Key の取得方法：**

1. AppsFlyerの管理画面内で、[ ***My Apps*** ]のタブに移動してください。
2. [ブランドバンドルを表示]をクリックします。

   [![GetWebDevKeyPba_us-en.pn](https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png)](https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png)
3. 必要な ***Web Dev Key*** をコピーしてください。

</Accordion>

<div id="extracting-the-web-sdk-afuserid" />

<Accordion title="Web SDKの afUserID の抽出">

* `afUserId`は、ユーザーが最初にウェブサイトを訪問した際に Web SDK によって割り当てられる一意の識別子です。
* `afUserId`が必要な場合は、以下の方法のいずれかを使用してください。

#### **HTTP CookieヘッダーからafUserIdを取得**

* `afUserId`は、ユーザーがサイトへアクセスする際に訪問者のブラウザから送信されます。
* 必要に応じてHTTP cookie ヘッダーから抽出してください。

#### **訪問者のブラウザでafUserIdを確認**

* トラブルシューティングやデバッグの目的で、訪問者のブラウザ上で`afUserId`を確認できます。
* afUserIdを確認するには、訪問者がWeb SDKが実装されたページを少なくとも一度訪問している必要があります。
* `afUserId`を含むCookieは、自社ドメインに対するファーストパーティCookieです。
* 以下の手順はChrome 81を使用して作成されています。ブラウザやOSによって手順が多少異なる場合があります。

**訪問者のブラウザから afUserId を取得する方法：**

1. ブラウザで自社Webサイトを開きます。
2. 右クリックし、***Inspect（検証）を選択します。***ブラウザの検査ウィンドウが開きます。

   [![S2S_inspect.jpg](https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg)](https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg)
3. (A) ***Application***タブを開きます。
4. サイドメニューにて、(B) [Cookie] を展開します。
5. 自社Webサイトを選択します。表示されない場合は、ブラウザをリフレッシュしてください。
6. (C) ***filter***フィールドに、`afUserId`を入力します。  
   すると afUserIdの値が表示されます。

</Accordion>

<div id="response-codes" />

<Accordion title="レスポンスコード">

| レスポンスコード | メッセージ | 処理方法 |
| --- | --- | --- |
| 200 | OK |  |
| 404 | Not found | <ul><li>エンドポイントを確認してください。</li><li>正しい Bundle ID が設定されているか確認してください。</li></ul> |
| 400 | Bad request | <ul><li>JSON にエラーがあります。詳細についてはエラーメッセージをご覧ください。</li></ul> |

</Accordion>

<div id="troubleshooting" />

<Accordion title="トラブルシューティング">

* 症状：HTTPのリターンコードが返されない  
  ソリューション： AppsFlyerサーバーを<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-server-ip-address-ranges-allowlisting">許可リスト</Anchor>に追加してください

</Accordion>

<div id="release-notes" />

<Accordion title="リリースノート">

<table><caption>Web SDKリリースノート</caption><thead><tr><th>日付 </th><th>エンドポイントバージョン\*</th><th>備考</th></tr></thead><tbody><tr><td>2020-05-12</td><td>1</td><td> 初期リリース</td></tr><tr><td>2020-05-24</td><td>1</td><td> </td></tr></tbody><tfoot><tr><td colspan="3">\* バージョン番号は、エンドポイントのバージョン番号に紐づいています。<code>https://webs2s.appsflyer.com/v1/<var>method</var></code> </td></tr></tfoot></table>

</Accordion>

<div data-zendesk-anchors="web-servertoserver-events-api-for-pba=pba%E5%90%91%E3%81%91-web-server-to-server%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88api h_01HKW2YAW4HHYK27F41HC3B24Y=pba%E5%90%91%E3%81%91-web-server-to-server%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88api api-use-instructions=api%E5%88%A9%E7%94%A8%E6%89%8B%E9%A0%86 h_01HKW2YAW4DCESP3MNY9D4GTFK=api%E5%88%A9%E7%94%A8%E6%89%8B%E9%A0%86 h_01HKW2YAW4Z6G8HEVJJHCVG9G3=api-basics web-s2s-api-basics=web-s2s-api-%E5%9F%BA%E6%9C%AC%E4%BB%95%E6%A7%98 h_01HKW2YAW4XDKZ3YGAHAP3AG2T=web-s2s-api-%E5%9F%BA%E6%9C%AC%E4%BB%95%E6%A7%98 h_01HKW2YAW4YFK2WWKM0VB8AGNN=setcuid-method curl-example-setcuid=setcuid%E3%81%AEcurl-%E3%82%B5%E3%83%B3%E3%83%97%E3%83%AB h_01HKW2YAW5SJFKGTNRGRKN6NCJ=setcuid%E3%81%AEcurl-%E3%82%B5%E3%83%B3%E3%83%97%E3%83%AB h_01HKW2YAW5A9TJGZG08K4ZW69C=event-method event-method-details=event-%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E8%A9%B3%E7%B4%B0 h_01HKW2YAW53H43SCYTDXAYBDHX=event-%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AE%E8%A9%B3%E7%B4%B0 h_01HKW2YAW5WDPMXDKA3X4HZBD2=payload-parameters user-identifier-parameters-send-at-least-one-parameter=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCid%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E5%B0%91%E3%81%AA%E3%81%8F%E3%81%A8%E3%82%821%E3%81%A4%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%82%92%E9%80%81%E4%BF%A1 h_01HKW2YAW5RR4Q2PCWC9717ACG=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCid%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E5%B0%91%E3%81%AA%E3%81%8F%E3%81%A8%E3%82%821%E3%81%A4%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%82%92%E9%80%81%E4%BF%A1 event-parameters=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01HKW2YAW5G46ZV4Z0CYEWB011=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01HKW2YAW56HZ0WYRWNBATB8WR=curl-example h_01HKW2YAW5A78VREGZEZ12XMPE=python-example h_01HKW2YAW59JSCCACGD2H153M5=testing additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HKW2YAW5D4N3SYA625F10YFW=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HKW2YAW5HV506YV5328ME236=getting-the-web-dev-key h_01HKW2YAW52T0KME7P2CRQ6WBR=extracting-the-web-sdk-afuserid get-afuserid-from-the-http-cookie-header=http-cookie%E3%83%98%E3%83%83%E3%83%80%E3%83%BC%E3%81%8B%E3%82%89afuserid%E3%82%92%E5%8F%96%E5%BE%97 h_01HKW2YAW5FK04C3AWCXGP1XAW=http-cookie%E3%83%98%E3%83%83%E3%83%80%E3%83%BC%E3%81%8B%E3%82%89afuserid%E3%82%92%E5%8F%96%E5%BE%97 viewing-afuserid-in-the-visitors-browser=%E8%A8%AA%E5%95%8F%E8%80%85%E3%81%AE%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%81%A7afuserid%E3%82%92%E7%A2%BA%E8%AA%8D h_01HKW2YAW5CT2WZ229KJD2FWYK=%E8%A8%AA%E5%95%8F%E8%80%85%E3%81%AE%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%81%A7afuserid%E3%82%92%E7%A2%BA%E8%AA%8D h_01HKW2YAW5HTV9N4ZEJJ99RBN0=response-codes h_01HKW2YAW6MG7VNQJAB1Q37K6T=troubleshooting h_01HKW2YAW6RM6VJKFECT0ETGTG=release-notes" />
