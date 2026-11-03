---
title: OpenDSR API
metadata:
  keywords:
    - Advertisers
    - GDPR
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2022-12-12T09:14:00Z'
  edited_at: '2026-10-14T09:32:52Z'
  id: 11332840660625
  locale: ja
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ja/articles/11332840660625
---
> **概要：** 概要：この記事は、アプリの使用状況と計測を記録するためにプラットフォームを使用しているAppsFlyerのクライアント（広告主、またはアプリ所有者）を対象としています。アプリ所有者は、GDPR（ヨーロッパ）、CCPA（カリフォルニア）、LGPD（ブラジル）、PDPA（タイ）、およびPIPA（韓国）などの適用されるデータ保護法に準拠するために、OpenDSR（データ主体リクエスト）APIを実装します。

弁護士からの一言： ここに記載されていることは、一切法的な助言ではありません。これらは情報提供と便宜上の目的でのみ提供されています。あなたは、GDPR、CCPA、またはその他の法律がどのように適用されるか、または適用されないかを正確に判断するために、法務およびその他の専門アドバイザーと密接に連携するべきです。 お客様とAppsFlyer 間のプライバシー事項については、<Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy">AppsFlyer Services Privacy Policy</Anchor>に準拠しています。本サービスのプライバシーポリシーに関するご質問、または当社のデータ保護責任者へのお問い合わせは、 privacy@appsflyer.comまでご連絡ください。一般データ保護規則第27条の目的上、AppsFlyerのEU域内の代表者は AppsFlyer Germany GmbH, Schönhauser Allee 180, 10119 Berlin, Germany（ご連絡先privacy@appsflyer.comまたは+49-30-166373500）です。

## プライバシー規制

この記事内のプライバシー規制には、次の表示に記載されている規制が含まれています。

| 規制 | ロゴ | 説明 |
| --- | --- | --- |
| GDPR | ![GDPR.png](https://files.readme.io/c3eb63a14b95bda24478f1d8fec75bcc59789157c4e53ffb44ab77ccd6dfe091-12830387561233.png) | 「一般データ保護規則（General Data Protection Regulation）」は、欧州連合（EU）における個人データ保護 およびプライバシーに関するEU規制です。 |
| CCPA | ![CCPA.png](https://files.readme.io/57988a70f4e8395b9562fce9e424348cd7d61401ec7ca0ff32de518a093eb4dc-12830389364241.png) | カリフォルニア州消費者プライバシー法（California Consumer Privacy Act） |
| LGPD | ![LGPD.png](https://files.readme.io/4e50bdc8e83db49b4eb0d84f757816ebc1d0e461ae8792af9ab48d7e51d20af3-12830406815633.png) | Lei Geral de Proteção de Dados |
| PDPA | ![6137_Privacy_Shield_Thailand-01.png](https://files.readme.io/90833957690e7a52eb43b330d34a85c67af7a6c071b8ac79dec0733ec9aafcfc-12830408352657.png) | Personal Data Protection Act |

プライバシー規制、GDPR、CCPA、LGPD、PDPAという用語は、この記事では同じ意味で使用されています。

### OpenDSR イニシアチブ

プライバシー規制の遵守に向けて、データ主体からのリクエストに対処し管理するために、AppsFlyerは mParticle、Amplitude、Braze の3社と連携して OpenDSR プロトコル (旧：OpenGDPR) を構築しました。

OpenDSR はオープンソース・フレームワークで、個人データの公平かつ透明性のある使用のために、テクノロジー企業間の連携をサポートします。データプライバシーに関するアクションを複数のシステムにて処理し、保管することで、データプライバシー対策を取ることができます。

<Anchor target="_blank" href="https://www.appsflyer.com/company/newsroom/pr/opengdpr-initiative/">OpenDSRイニシアチブの詳細については、こちらを参照してください</Anchor>。

### 定義

| DSR用語 | AppsFlyer 用語 | 説明 |
| --- | --- | --- |
| データ主体（Data Subject） | アプリユーザーまたはエンドユーザー | データが収集されるアプリユーザー |
| データ管理者（Data Controller） | アプリ所有者または広告主 | 個人データ処理の目的と手段を決定するアプリ所有者 |
| データ処理者（Data Processor） | AppsFlyerとそのパートナー | データ管理者に代わって個人データの処理を行う、AppsFlyerと連携済みパートナー。 |

### DSRの要件

DSRでは、データ主体（Data Subject）の義務と権利について詳細に定められており、アプリ所有者（Data Controller）はこれらを遵守しなければなりません。APIでは、これらの権利はリクエストタイプに変換されています。以下では、AppsFlyerがさまざまなリクエストタイプを処理する方法について詳しく説明します。

| **リクエストタイプ**<br /><br />**（権利）** | **GDPRの定義** | AppsFlyerによるリクエストの処理 |
| --- | --- | --- |
| **アクセス** | <ul><li>リクエストがあった場合、アプリユーザーはアプリ所有者が個人データを処理するかどうか、その理由と期間を知る権利があります。</li><li>データがAppsFlyerなどの第三者と共有された場合、アプリユーザーはこの第三者が誰なのかを知る権利があります。</li><li>データ主体はどんな種類のデータが処理されているのか知る権利を有します。</li><li>データ主体は、データに深刻な影響を生じ得るような自動処理が存在するかどうかを知る権利があります。</li></ul> | アプリ所有者は、アプリユーザーの処理された個人データのコピーを受信できます。 |
| **ポータビリティ** | アプリユーザーは自分の個人データのすべてを、構造化され、一般的に使用され、機械によって読み取り可能な形式（CSVファイルなど）で受け取る権利を有します。 | アプリ所有者はアプリユーザーの処理された個人データのコピーを受信できます。 |
| **訂正** | アプリユーザーは、自分の個人データが不正確であったり虚偽がある場合に訂正をリクエストできます。アプリ所有者は、不正確または不完全なデータを消去または修正する必要があります。 | <ul><li>AppsFlyerは、訂正リクエストがあった日付以前のアプリユーザーのデータ削除します。</li><li>その後受信したデータはAppsFlyerによって記録されます。</li></ul> |
| **削除** | 消去の権利により、アプリ所有者はリクエストを受けてから 14 日以内に個人データを削除する必要があります。 | データは削除されます。 |

## AppsFlyer の GDPR リクエスト API

このセクションで示すように GDPR Request API を使用して、DSR コンプライアンスを実装します。

* GDPRリクエスト GDPRリクエスト：次のリクエストタイプのいずれかを実行します：アクセス、ポータビリティ、削除、訂正。
* 2. Status（ステータス）リクエストGDPRリクエストの現在の状況を照会する。
* 4. Discovery（確認）リクエスト サポートされているAPIバージョンとデータフォーマットについて問い合わせる。
* キャンセル 保留中の段階でGDPRリクエストをキャンセルする。

アプリ所有者は、アプリユーザーがリクエストを送信できるように、アプリにUIの変更を実装する必要があります。注：GDPRリクエストは1回につき1人のユーザーを対象とします。

<div id="1-gdpr-request" />

<Accordion title="1.GDPRリクエスト">

### GDPRリクエストフロー

GDPRリクエストタイプ（アクセス、ポータビリティ、削除、訂正）は、同じフローで実行されます：

1. **アプリユーザー** がリクエストを提出します。
2. **アプリ所有者** がGDPRリクエストを作成し（下記参照）、AppsFlyerに送信します。
3. **AppsFlyer** がリクエストを受信し、リクエストが有効な場合は "201 OK" を返します。
4. アクセスとポータビリティのために：リクエストは即座に満たされます。  
   消去および訂正のために
   * その後48時間は、リクエストは ***pending（保留中）*** のステータスでキューに入ります。アプリユーザーはこの間はキャンセルできます。
   * 48時間後、リクエストステイタスは <strong><em>in\_progress（処理中）</em></strong>に変わります。AppsFlyerは ‘status change’（ステイタス変更） ポストバックを送信します。これ以降、リクエストをキャンセルすることはできません。
   * 14日以内（注記参照）に、AppsFlyerはリクエストに応え、リクエストのステータスは<strong><em>completed（完了）</em></strong>に更新されます。AppsFlyerは ‘status change'（ステイタス変更） ポストバックを送信します。

     * *削除* または *訂正* リクエストの場合、アプリユーザーのデータは削除されます。
     * *ポータビリティ*または*アクセス*リクエストの場合、アプリユーザーのデータはAppsFlyerの管理画面の **GDPR** セクション、またはリクエストAPI経由（下記参照）でアクセスできます。

     **注：この10日間の期間は、アプリ所有者がリクエストを提出したときに始まります。48時間後、リクエストのステータスは「進行中」に変更され、さらに8日以内に完了します。合計で10日です。**

### GDPRリクエストのフォーマット

GDPRリクエストAPIは、HTTP POST経由で次のエンドポイントに送信できます。

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests
```

API承認には、Pull APIと同じ V2 APIトークンを使用してください。アドミンユーザーは、管理画面のAPI トークンページから<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens#トークンの取得">トークンを取得できます</Anchor> 。リクエストヘッダーにトークンを次のように追加してください:

#### パラメーター

<table><thead><tr><th><strong>プロパティ名</strong></th><th><strong>必須</strong></th><th><strong>説明</strong></th></tr></thead><tbody><tr><td><strong>subject_request_id</strong></td><td>はい</td><td>UUID v4 文字列。データ管理者により、データ処理者へリクエストを送信する時に生成されます。その後、リクエストのステイタスを確認したり、更新またはキャンセルするために使用できます。</td></tr><tr><td><strong>subject_request_type</strong></td><td>はい</td><td>GDPRリクエストタイプを表す文字列値。 サポートされている値：<ul><li>erasure</li><li>portability</li><li>アクセス</li><li>rectification</li></ul></td></tr><tr><td><strong>subject_identities</strong></td><td>はい</td><td><ul><li>リクエストをした人のアイデンティティを定義するIDオブジェクトの配列（下記参照）。</li><li>各リクエストに含めることができるサブジェクトIDは1つだけです。</li></ul></td></tr><tr><td><strong>submitted_time</strong></td><td>はい</td><td><ul><li>RFC 3339日時形式の文字列。データ主体が送信した元のリクエストの時間を表します。</li><li>UTC時間のタイムスタンプ</li></ul></td></tr><tr><td><strong>property_id</strong></td><td>はい</td><td><p>このリクエストの調査対象のモバイルアプリを表す文字列です。</p><p><strong>例</strong>：</p><ul><li> iOS: id123456789 </li><li> <strong>Android</strong>: com.example, com.publishers.name  </li><li> <strong>Android ストア外</strong>: com.publisher.name-channel<br/><strong>注:</strong> アプリ所有者は、Android Google Play の名前を使用して、ストア外のアトリビューションを記録する場合があります。その場合、管理画面に表示される通常のアプリ名を使用します。</li></ul></td></tr><tr><td><strong>api_version</strong></td><td>いいえ</td><td>バージョン文字列。目的とするGDPRリクエストAPIのバージョンを表します。</td></tr><tr><td><strong>status_callback_urls</strong></td><td>いいえ、ただし推奨</td><td><ul><li>リクエストのステータス変更に続いて送信されるステータスコールバックのエンドポイントを最大3つまで指定した配列</li><li>https 形式のURLのみがサポートされています。</li><li>無効なURLは拒否されます。</li></ul></td></tr><tr><td rowspan="2"> <strong>platform</strong><br/><br/> </td><td>いいえ</td><td>価値はサポートされているDSRプラットフォームの1つです。<br/><code>android</code>, <code>ios</code>, <code>web</code>, <code>windowsphone</code> </td></tr><tr><td>はい</td><td><p>CTV、PCまたはコンソールプラットフォームリクエストの場合は、以下のいずれかのプラットフォームを含めます：  </p><p> <code>nativepc</code><code>playstation</code> <br/><code>vidaa</code><code>tizen</code> <br/><code>quest</code><code>switch</code></p></td></tr></tbody></table>

#### Subject\_identities オブジェクト

| オブジェクトタイプ | **必須** | **説明** |
| --- | --- | --- |
| identity\_type | はい | <ul><li>プラットフォームの文字列形式のアイデンティティタイプは、次のいずれかです:<ul><li>ios\_advertising\_id</li><li>android\_advertising\_id</li><li>fire\_advertising\_id</li><li>microsoft\_advertising\_id</li><li>appsflyer\_id</li><li>customer\_user\_id (CUID - カスタマーユーザーID)</li></ul></li></ul><ul><li>次のプラットフォームのみ:<ul><li>appsflyer\_id</li><li>customer\_user\_id (CUID - カスタマーユーザーID)</li></ul></li></ul><ul><li>例： `android_advertising_id`</li></ul>**<span id="01JFVT3ATDGJXBX4VN7BHX6JB8"></span>重要！**<br />OpenDSR APIを通じてCUIDを使用するには、アプリ内イベントでCUIDを/と共に送信する必要があります。 : または |
| identity\_value | はい | <ul><li>形式：文字列</li><li>例: "a7551968-d5d6-44b2-9831-815ac9017798"</li></ul> |
| identity\_format | はい | <ul><li>identity\_value をエンコードするために使用されるメソッド： `raw`rawraw のみがサポートされています。</li><li>例: "raw"</li></ul> |

### 例：GDPR消去要求

プラットフォームに対する削除リクエストの例：

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer %AuthTokenv2% \
--data-raw '{ 
 "subject_request_id":"f4e5a271-f25e-4107-b681-************",
 "subject_request_type":"erasure",
 "submitted_time":"2020-07-05T10:00:00Z",
 "platform": "android",
 "subject_identities":[ 
  { 
   "identity_type":"android_advertising_id",
   "identity_value":"55*****-****-****-************",
   "identity_format":"raw"
  }
 ],
 "api_version":"0.1",
 "property_id":"com.*********.*******.********",
 "status_callback_urls":[ 
  "https://examplecontroller.com/opengdpr_callbacks"
 ]
}'
```

プラットフォームに対する削除リクエストの例：

```bash
curl --location --request POST 'https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer %AuthTokenv2% \
--data-raw '
{"requester": "test@email.com",
"subject_request_id":"valid-uuid4-string",
"subject_request_type":"erasure",
"submitted_time":"2020-07-05T10:00:00Z",
"subject_identities":[ 
 { 
  "identity_type":"appsflyer_id",
  "identity_value":"valid-appsflyer-id-string",
  "identity_format":"raw"
 }
],
"api_version":"0.1",
"property_id":"app-id",
"platform": "roku",
"status_callback_urls":[ 
 "https://examplecontroller.com/opengdpr_callbacks"
 ]
}'
```

### GDPR 削除リクエストコードの例

<Tabs>
<Tab title="Java">

```java
/* 
using the okhttp package install from maven
https://mvnrepository.com/artifact/com.squareup.okhttp3/okhttp
 */

import okhttp3.*;
import java.io.IOException;

public class GdprSendRequest {
 public static void main(String[] args){

  OkHttpClient client = new OkHttpClient();
  RequestBody body = RequestBody.create(null, "" +
  "{\r\n\"subject_request_id\": \"\"," +
  "\r\n\"subject_request_type\": \"erasure\"," +
  "\r\n\"platform\": \"android\"," +
  "\r\n\"submitted_time\": \"2018-11-02T15:00:00Z\"," +
  "\r\n\"subject_identities\": [\r\n" +
  "{\r\n\"identity_type\": \"android_advertising_id\"," +
  "\r\n\"identity_value\": \"\"," +
  "\r\n\"identity_format\": \"raw\"\r\n}" +
   "\r\n]," +
   "\r\n\"property_id\": \"com.example.application\"}");

  Request request = new Request.Builder()
  .url("https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/opendsr_requests")
  .post(body)
  .addHeader("Content-Type", "application/json")
  .addHeader("Accept", "application/json")
  .addHeader("Authorization: Bearer", "")
  .build();

  try {
   Response response = client.newCall(request).execute();
   System.out.println(response.code());
   System.out.println(response.body().string());
   System.exit(0);
  } catch (IOException e) {
   e.printStackTrace();
   System.exit(1);
  }
 }
}
```

</Tab>

<Tab title="PythonNode.jsC#">

```python
""" using the requests python package, 
install using pip install requests """

import requests
import json
headers = {
 "Content-Type": "application/json",
 "Accept": "application/json",
 "Authorization: Bearer": ""
}

body = {
 "subject_request_id": "", 
 "subject_request_type": "erasure", 
 "submitted_time": "2018-10-02T15:00:00Z",
 "platform": "android", 
 "subject_identities": [
  { "identity_type": "android_advertising_id", 
   "identity_value": "", 
   "identity_format": "raw" }
  ], 
 "property_id": "com.example.application" 
} 
body = json.dumps(body) 
res = requests.request("POST", 
"https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests", 
headers=headers, data=body, params=params) 
print(res.text)
```

</Tab>
</Tabs>

</Accordion>

<div id="2-status-request" />

<Accordion title="2. 2. Status（ステータス）リクエスト">

`subject_request_id`subject\_request\_idsubject\_request\_idを指定すると、送信済みの各GDPRリクエストのステータスを後で問い合わせることができます。次の4種類のステータスがサポートされています。

1. ***pending***（保留中） - 有効なリクエストが受信され、キューに保存されています。
2. ***in\_progress***（処理中） - リクエストは現在処理中です。
3. ***completed***（完了） - リクエストは完了しています。
4. ***canceled***（キャンセル） - リクエストはキャンセルされました。

### Statusリクエストのフォーマット

StatusリクエストはHTTP GET経由で次のエンドポイントに送信できます。

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

### Statusレスポンスの例

```http
HTTP/1.1 200 OK
Content-Type: application/json
X-OpenGDPR-Processor Domain: example processor.com
X-OpenGDPR-Signature:
kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=
{
 "controller_id":"example_controller_id",
 "expected_completion_time":"2018-11-01T15:00:01Z",
 "subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
 "request_status":"pending",
}
```

### Statusポストバック

上記の GDPRリクエストフローのように、GDPRリクエストのステータスが ***pending***（保留中）から ***in\_progress***（処理中）、***completed***（完了）の順に変化するとき、AppsFlyerは **status\_callback\_urls** プロパティで指定された、リクエスト中のエンドポイントにGDPRポストバックを送信します。

Statusポストバックの例：

```http
POST /opengdpr_callbacks HTTP/1.1
Host: examplecontroller.com
Content-Type: application/json
X-OpenGDPR-Processor Domain: gdpr.appsflyer.com
X-OpenGDPR-Signature: kiGlog3PdQx+FQmB8wYwFC1fekbJG7Dm9WdqgmXc9uKkFRSM4uPzylLi7j083461xLZ+mUloo3tpsmyIZpt5eMfgo7ejXPh6lqB4ZgCnN6+1b6Q3NoNcn/+11UOrvmDj772wvg6uIAFzsSVSjMQxRs8LAmHqFO4cF2pbuoPuK2diHOixxLj6+t97q0nZM7u3wmgkwF9EHIo3C6G1SI04/odvyY/VdMZgj3H1fLnz+X5rc42/wU4974u3iBrKgUnv0fcB4YB+L6Q3GsMbmYzuAbe0HpVA17ud/bVoyQZAkrW2yoSy1x4Ts6XKba6pLifIHf446Bubsf5r7x1kg6Eo7B8zur666NyWOYrglkOzU4IYO8ifJFRZZXazOgk7ggn9obEd78GBc3kjKKZdwaCrLx7WV5y9TMDCf+2FILOJM/MwTUy1dLZiaFHhGdzld2AjbjK1CfVzyPssch0iQYYtbR49GhumvkYl11S4oDfu0c3t/xUCZWg0hoR3XL3B7NjcrlrQinB1KbyTNZccKR0F4Lk9fDgwTVkrAg152UqPyzXxpdzXjfkDkSEgAevXQwVJWBNf18bMIEgdH2usF/XauQoyrne7rcMIWBISPgtBPj3mhcrwscjGVsxqJva8KCVCKD/4Axmo9DISib5/7A6uczJxQG2Bcrdj++vQqK2succ=

{
"controller_id":"example controller id at the processor",
"expected_completion_time":"2018-11-01T15:00:01Z",
"status_callback_url":"https://examplecontroller.com/opengdpr_callbacks",
"Subject_request_id":"a7551968-d5d6-44b2-9831-815ac9017798",
"Request_status":"pending"
}
```

### ポストバックの検証

**受信ポストバックの信頼性を検証する**：

1. コールバックを許可するすべてのプロセッサドメインの許可リストを作成します。
2. ヘッダー値があなたの許可リストにある場合は、証明書を取得してください。
   * 証明書のURLは、レスポンスボディ内の値です。
   * アプリスフライヤーのエンドポイントから、V2 APIトークンをベアラートークンとして認証ヘッダーに使用して、証明書を直接取得することもできます。
3. ライブラリを使用して証明書を検証し、証明書で次の項目を確認します：
   1. 信頼された機関によって発行されている
   2. ヘッダー値に提供された同じ文字列に発行されます。
   3. 有効期限が切れていない
4. 証明書が有効であることを確認したら、それを使用して、ローリクエストボディに対する X-OpenDSR-Signatureヘッダーを検証します。AppsFlyerは、署名アルゴリズムとしてSHA256 RSAを使用しています。
5. ステータスヘッダーで応答を取得してください：
   1. 検証が成功した場合。
   2. `401 Unauthorized`401 Unauthorized - 署名の検証に失敗した場合、またはプロセッサドメインが許可リストにない場合

</Accordion>

<div id="3-report-request" />

<Accordion title="3.3. Report（レポート）リクエスト">

**Accessリクエスト**や **Portabilityリクエスト**が完了したら、次のエンドポイントにHTTP GET経由でレポートをダウンロードできます。

```http
https://hq1.appsflyer.com/api/gdpr/v1/download/[REQUEST_ID]
```

生成されたレポートは、完了から14日間利用可能です。

</Accordion>

<div id="4-discovery-requestin-process" />

<Accordion title="4. 4. ディスカバリーリクエスト処理">

AppsFlyerでサポートされているフォーマットを確認するには、HTTP GET経由で次のエンドポイントにDiscoveryリクエストを送信します。

```http
https://hq1.appsflyer.com/api/gdpr/v1/discovery
```

### Discoveryレスポンスの例

```http
HTTP/1.1 200 OK
Content-Type: application/json
{
 "api_version": "0.1",
 "supported_identities": [
 {
  "identity_type": "android_advertising_id",
  "identity_format": "raw"
 },
 ],
 "supported_subject_request_types": [
 "erasure", "access", "portability", "rectification"
 ],
 "processor_certificate": "https://exampleprocessor.com/cert.pem"
}
```

</Accordion>

<div id="5-cancellation-request" />

<Accordion title="5. 5. Cancellation（キャンセル）リクエスト">

GDPRリクエストは、その内容に基づいてキャンセルすることが可能ですが、保留中の段階でのみ可能です。

HTTP DELETEを送信するには:

```http
https://hq1.appsflyer.com/api/gdpr/v1/opendsr_requests/<req_id>
```

### Cancellationレスポンス

GDPRのCancellationリクエストを受信すると、AppsFlyerはステータスコード202のHTTPレスポンスをその他のパラメーターと一緒に返します。

Cancellationリクエストを実行後、AppsFlyerは***canceled***（キャンセル済み）のステータスでポストバックを送信します。

</Accordion>

<div id="6-gdpr-requests-test-api" />

<Accordion title="6. 6. GDPRリクエストのテストAPI">

このAPIは、AppsFlyerのGDPRリクエストAPIをテストします。

### 仕組み

テストAPIは次のように動作します。

1.1. GDPRリクエストが受け付けられると、リクエストはすぐに "Pending"（保留中）ステータスになります。テストのため、ステータスは30秒ごとに変わります。

2.GDPRリクエストにstatusポストバックのエンドポイントが指定されている場合、リクエストの直後に最初のポストバック（Pending）が送信され、続いて30秒間隔で2つのstatusポストバック（in\_progress、completed）が送信されます。

**GDPRリクエストのテストエンドポイント**:POST

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub
```

**Statusリクエストのテストエンドポイント**:GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**Discoveryリクエストのテストエンドポイント**:GET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/discovery
```

**Cancellationリクエストのテストエンドポイント**:削除

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/:requestId
```

**証明書テストエンドポイント：** GETGET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stubcertificate
```

**アクセス / ポータビリティレポートテストエンドポイント：** GETGET

```http
https://hq1.appsflyer.com/api/gdpr/v1/stub/download/:requestId
```

> 📘 **注意**
>
> * 有効なV2 APIトークンをリクエストヘッダーに次のように挿入する必要があります:
> * ”property\_id” プロパティでは、アプリIDはアカウント所有者（広告主）のアプリである必要があります（APIトークンに基づく）。

</Accordion>

<div id="7-request-logs" />

<Accordion title="7. リクエストのログ">

管理者ユーザーは、ログダッシュボードで送信された GDPRリクエストにアクセスできます。

完了したaccessおよびportabilityリクエストについては、この管理画面からレポートをダウンロードすることもできます。

Logs（ログ）管理画面へのアクセス：

1. 上部のバーから、アカウントメニュー（Eメールアドレスのドロップダウン） >  メニュー項目を開きます。
2. 次のウィンドウが開きます。：

![GDPR_Table.png](https://files.readme.io/5c2b2695b5c273e16a0396f0df2d227a0a0f61af6ad0626c0a911b77edc6a0d2-13949567038481.png)

</Accordion>

<div id="8-gdpr-api-return-codes-and-error-messages" />

<Accordion title="8.8. GDPR API のリターンコードとエラーメッセージ">

このセクションでは、GDPR API の HTTPリターンコードとエラーメッセージについて詳しく説明します。

#### GDPR API リターンコード

| リターンコード | 説明 |
| --- | --- |
| 201 | 作成されました |
| 202 | キャンセルリクエストを受信しました |
| 400 | Bad request。本文には、次の表に示すエラーコードとメッセージが含まれています。 |

### HTTPリターンコード 400 - bad request

リターンコード400のメッセージには、エラーコードとメッセージを含む JSON が含まれています。

`{ "error": { "code":400, "af_gdpr_code": "%AF error code%", "message":"%error message text%" } }`

#### リターンコード400 bad request のメッセージ

| エラーコード | エラーの説明（メッセージ） |
| --- | --- |
| e111 | Rate limit exceeded（レート上限を超えました） |
| e211 | Unable to cancel request with invalid status（ステイタスが無効なためリクエストをキャンセルできません） |
| e212 | Request not permitted（リクエストは許可されていません。）Erasure is in progress for the identifier（このIDの削除が処理中です） |
| e213 | Request already exists（リクエストが既に存在しています） |
| e214 | Request not found（リクエストが見つかりません） |
| e311 | Invalid request content-type（リクエストのcontent-typeが無効です） |
| e312 | Invalid API version（APIバージョンが無効です） |
| e313 | Invalid subject\_request\_id（ subject\_request\_id が無効です） |
| e314 | Invalid submitted\_time format（ submitted\_time format が無効です） |
| e315 | Invalid status\_callback\_url length（ status\_callback\_url の長さが無効です） |
| e316 | Invalid status\_callback\_url format（ status\_callback\_url の形式が無効です） |
| e317 | Invalid app\_id format（ app\_id の形式が無効です） |
| e318 | Invalid identity\_type（ identity\_type が無効です） |
| e319 | Application platform does not match identity types（アプリのプラットフォームがIDタイプと一致しません） |
| e320 | Invalid identity\_type（ identity\_type が無効です） |
| e321 | LAT users are not supported via api（LATユーザーはAPIでサポートされていません） |
| e322 | Invalid subject\_request\_type（ subject\_request\_type が無効です） |
| e323 | Invalid subject\_identities format（ subject\_identities の形式が無効です） |
| e324 | Invalid subject\_identities length（ subject\_identities の長さが無効です） |
| e325 | Invalid subject\_identities value（ subject\_identities の値が無効です） |
| e411 | AppID is incorrect or does not belong to your account（AppIDが正しくないかアカウントに属していません） |
| e412 | No permissions to cancel erasure request（削除リクエストをキャンセルする権限がありません） |
| e413 | No permissions to view request（リクエストを表示する権利がありません） |
| e511 | 内部で問題が発生しました。60分経ってから再度お試しください。問題が解決しない場合は、AppsFlyerサポートにお問い合わせください。support@AppsFlyer.com |

</Accordion>

## 特性と制限

* OpenDSR API レート制限:1分につき350リクエストこの制限を超えるとエラーが発生し、リクエストを再送信する必要があります。このレート制限内に留まることで、1日あたり最大504,000件のリクエストが可能になります。
* 60日以上前のリクエストステータスの確認：「リクエストが見つかりません」が返されます。

<div data-zendesk-anchors="privacy-regulations=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E8%A6%8F%E5%88%B6 h_01HB866TQ0AWHQ9659Q8Q4XMQM=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E8%A6%8F%E5%88%B6 the-opendsr-initiative=opendsr-%E3%82%A4%E3%83%8B%E3%82%B7%E3%82%A2%E3%83%81%E3%83%96 h_01HB866TQ0R18S4GCH3KPGNJHD=opendsr-%E3%82%A4%E3%83%8B%E3%82%B7%E3%82%A2%E3%83%81%E3%83%96 definitions=%E5%AE%9A%E7%BE%A9 h_01HB866TQ06XV2AJDMA3M5Q5KK=%E5%AE%9A%E7%BE%A9 dsr-requirements=dsr%E3%81%AE%E8%A6%81%E4%BB%B6 h_01HB866TQ0JNEZTHQ7BR1TMD5M=dsr%E3%81%AE%E8%A6%81%E4%BB%B6 appsflyer-gdpr-requests-api=appsflyer-%E3%81%AE-gdpr-%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88-api h_01HB866TQ0HNFGF9QTJNT792N7=appsflyer-%E3%81%AE-gdpr-%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88-api h_01HB866TQ0ATDT8B000Z70MBTH=1-gdpr-request gdpr-request-flow=gdpr%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%83%95%E3%83%AD%E3%83%BC h_01HB866TQ0FCZGQ1DWENVSWHSG=gdpr%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%83%95%E3%83%AD%E3%83%BC gdpr-request-format=gdpr%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%83%E3%83%88 h_01HB866TQ0GC7V1081GT53TWEZ=gdpr%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%83%E3%83%88 parameters=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC h_01HB866TQ0CFAC0X2Y98B4EE5Q=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC subject_identities-objects=subject_identities-%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88 h_01HB866TQ02HMKJMKKPHHR4CMN=subject_identities-%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88 example-gdpr-erasure-request=%E4%BE%8Bgdpr%E6%B6%88%E5%8E%BB%E8%A6%81%E6%B1%82 h_01HB866TQ1CT316PTFBJC59C79=%E4%BE%8Bgdpr%E6%B6%88%E5%8E%BB%E8%A6%81%E6%B1%82 gdpr-erasure-request-code-example=%E4%BE%8Bgdpr%E6%B6%88%E5%8E%BB%E8%A6%81%E6%B1%82 h_01HB866TQ1D7290A6G29Q4HDE7=gdpr-%E5%89%8A%E9%99%A4%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%82%B3%E3%83%BC%E3%83%89%E3%81%AE%E4%BE%8B h_01HB866TQ15M1897AV5W099SFV=2-status-request status-request-format=status%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%83%E3%83%88 h_01HB866TQ1YEZZ4M6QMHTKCEGX=status%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%81%AE%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%83%E3%83%88 status-response-example=status%E3%83%AC%E3%82%B9%E3%83%9D%E3%83%B3%E3%82%B9%E3%81%AE%E4%BE%8B h_01HB866TQ1M7G7JNH0V7TEVFYY=status%E3%83%AC%E3%82%B9%E3%83%9D%E3%83%B3%E3%82%B9%E3%81%AE%E4%BE%8B status-postbacks=status%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HB866TQ1109WJ2J13D8FM8KX=status%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF validate-postback=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E6%A4%9C%E8%A8%BC h_01HB866TQ1YG0B6JDEQ2KMFEN0=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E6%A4%9C%E8%A8%BC h_01HB866TQ1TYQWZ7492H0DKWB7=3-report-request h_01HB866TQ1CH06PRJ78MHE7ZG0=4-discovery-requestin-process discovery-response-example=discovery%E3%83%AC%E3%82%B9%E3%83%9D%E3%83%B3%E3%82%B9%E3%81%AE%E4%BE%8B h_01HB866TQ1AJCSS2442EEWA19X=discovery%E3%83%AC%E3%82%B9%E3%83%9D%E3%83%B3%E3%82%B9%E3%81%AE%E4%BE%8B h_01HB866TQ1R8C9G4VH085897ZQ=5-cancellation-request cancellation-response=cancellation%E3%83%AC%E3%82%B9%E3%83%9D%E3%83%B3%E3%82%B9 h_01HB866TQ1F72KP3S55ZJYC8Y7=cancellation%E3%83%AC%E3%82%B9%E3%83%9D%E3%83%B3%E3%82%B9 h_01HB866TQ1Y35SZVFSTPG3ZJDH=6-gdpr-requests-test-api how-does-it-work=%E4%BB%95%E7%B5%84%E3%81%BF h_01HB866TQ1KFRGX7NZCSJWVW0T=%E4%BB%95%E7%B5%84%E3%81%BF h_01HB866TQ1W6X6NSEA6ZXAE6AG=%E6%B3%A8%E6%84%8F h_01HB866TQ1H8BKVGP5PFQYVBAA=7-request-logs h_01HB866TQ139BREE45W1FGTT3K=8-gdpr-api-return-codes-and-error-messages gdpr-api-return-codes=gdpr-api-%E3%83%AA%E3%82%BF%E3%83%BC%E3%83%B3%E3%82%B3%E3%83%BC%E3%83%89 h_01HB866TQ128R2TSHS4JTCQK70=gdpr-api-%E3%83%AA%E3%82%BF%E3%83%BC%E3%83%B3%E3%82%B3%E3%83%BC%E3%83%89 http-return-code-400-bad-request=http%E3%83%AA%E3%82%BF%E3%83%BC%E3%83%B3%E3%82%B3%E3%83%BC%E3%83%89-400---bad-request h_01HB866TQ1A51STZQCJC5TV65X=http%E3%83%AA%E3%82%BF%E3%83%BC%E3%83%B3%E3%82%B3%E3%83%BC%E3%83%89-400---bad-request return-code-400-bad-request-messages=%E3%83%AA%E3%82%BF%E3%83%BC%E3%83%B3%E3%82%B3%E3%83%BC%E3%83%89400-bad-request-%E3%81%AE%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8 h_01HB866TQ10MAMTS9WB0CKN55V=%E3%83%AA%E3%82%BF%E3%83%BC%E3%83%B3%E3%82%B3%E3%83%BC%E3%83%89400-bad-request-%E3%81%AE%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8 limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HB866TQ1PXGRX5JRHRSCT0EN=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90" />
