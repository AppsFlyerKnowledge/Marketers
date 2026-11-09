---
title: サーバー間イベントAPI for モバイル (S2S-mobile)
metadata:
  keywords:
    - iOS
    - Android
    - API
    - In-App
    - S2S
    - HTTP API
    - appsflyer_id
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-05-21T17:47:21Z'
  edited_at: '2026-10-14T09:13:22Z'
  id: 207034486
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/207034486
---
> **概要:** アプリ外で発生するモバイルイベントを測定するために、サーバーからAppsFlyerにイベントを送信します。

<Image align="center" alt="S2S_us-en.png" src="https://files.readme.io/2f228a03ca00df529e42bd033825a0dca595e99a537cadcfd5419754a29b5490-35863179575441.png" />

<div id="server-to-server-events-api-for-mobile" />

## サーバー間イベントAPI for モバイル

iOSアプリの場合、iOS 14以降では、os (オペレーティングシステム) のパラメーターを送信する必要があります。

AppsFlyerプラットフォームは、AppsFlyer SDKおよびAPIによって送信されたモバイルアプリイベントをアトリビューションして記録します。S2S APIを使用して、アプリ外で発生するイベントをレポートできます。例えば、ユーザーがWebインターフェースを使ってサブスクリプションを更新するなどです。S2Sイベントは一旦記録されると、ダッシュボードやローデータ、分析を含むプラットフォーム全体で活用可能になります。PBAのWebイベントについては、<Anchor target="_blank" href="/marketers/ja/docs/web-server-to-server-events-api-for-pba-web-s2s">PBA向けWeb S2S</Anchor>をご参照ください。

AppsFlyerはS2Sイベントに以下の情報を設定します。

* S2Sメッセージで送信された値
* AppsFlyerの一部のインストールアトリビューション値、例えばインストール時間やメディアソースなど。

API経由でイベントを送信するには、開発者に<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">サーバー間イベントAPIの手順</Anchor>に従うよう指示してください。

<div id="populating-parameters" />

## パラメーターの設定

<div id="difference-between-organic-and-nonorganic" />

<Accordion title="オーガニックと非オーガニックの違い">

AppsFlyerがS2Sアプリ内イベントを処理する際、アトリビューションフィールドはAppsFlyer IDを用いて入力され、アプリ内イベントより前の関連するインストールイベントを識別します。

つまり、AppsFlyerが非オーガニックS2Sアプリ内イベントに関連付けるデータの一部は、オーガニックS2Sアプリ内イベントには関連付けられないということです。

<div id="h_01_including-user-agent-and-ip-address-in-s2s-events" />

<div id="note" />

> 📄 **例**
>
> たとえば、非オーガニックとオーガニックのS2Sアプリ内イベントのローデータレポートを比較すると、非オーガニックイベントにはオーガニックアプリ内イベントにはないデータが含まれます。
>
> 非オーガニックアプリ内イベントには、メディアソース、キャンペーン、アトリビュートされたタッチタイプ、アトリビュートされたタッチ時間に関するデータが含まれます。
>
> 一方、オーガニックアプリ内イベントはオーガニックインストールに基づいています。オーガニックインストールには、キャンペーン、メディアソース、アトリビューションされたタッチタイプ、インストール時間に関連するデータは含まれません。

</Accordion>

<div id="mapping-appsflyer-id-with-customer-user-id-cuid" />

<Accordion title="AppsFlyer IDとカスタマーユーザーID(CUID)のマッピング">

パラメーターを入力するための値を取得するには、バックエンドロジックが必要です。次に、AppsFlyer IDの取得方法を説明します。

* AppsFlyer IDは必須で、イベントを紐付けるために使用されます。
* これは、ユーザーがモバイルアプリを初めてインストールしたときに生成されます。
* CUIDをAppsFlyer IDにマッピングするには、アプリでCUIDを設定する必要があります。

どのユーザーがどのイベントを実行したかを簡単に把握できるようにするため、以下のフローを実装してください。

* <Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">ユーザーがアプリをインストールするときにカスタマーユーザーID</Anchor>を設定してください。
* AppsFlyerのローデータレポートにはCUIDとAppsFlyer IDが含まれています。データ配信ツールのいずれかを利用するか、AppsFlyerプッシュAPIを使用してください。
* ローデータレポートを使用して、CUIDをAppsFlyer IDと一致させてください。
* AppsFlyer IDは、アプリに統合されたSDK（Android/iOS）で利用可能です。
* AppsFlyer IDをカスタマーユーザーIDに社内システムでマッピングしてください（将来の利用に重要です）。

AppsFlyer IDをCUIDとマッピングすると、ユーザーと実行されたイベントを結び付けることができます。その後、他の値（イベントの価値、イベント通貨、イベント時間など）を取得し、サーバー間でアプリ内イベントを送信できます。

</Accordion>

<div id="fetching-the-appsflyer-id" />

<Accordion title="AppsFlyer IDの取得">

`appsflyer_id`は、サーバー間イベントメッセージにおける必須パラメーターです。AppsFlyerは、このパラメーターを使用して、イベントを元のデバイスと関連付けられたメディアソースに紐付けます。次のいずれかの方法でIDを取得できます。

* モバイルデバイスからAppsFlyer SDK APIを呼び出して取得:

  <Tabs>
  <Tab title="Androidネイティブ">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerUIDを取得</Anchor>

  </Tab>

  <Tab title="iOSネイティブ">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerUIDを取得</Anchor>

  </Tab>

  <Tab title="Unity">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#getappsflyerid">getAppsFlyerIdを取得</Anchor>

  </Tab>

  <Tab title="React Native">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#getappsflyeruid">getAppsFlyerUIDを取得</Anchor>

  </Tab>
  </Tabs>

* AppsFlyerプラットフォームから次のいずれかを使用して取得してください:<Anchor target="_blank" href="/marketers/ja/docs/pull-api-raw-data?query=pull">プルAPI,</Anchor> <Anchor target="_blank" href="/marketers/ja/docs/push-api-streaming-raw-data">プッシュAPI,</Anchor> エクスポート <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ローデータインストール。</Anchor>

</Accordion>

<div id="time-stamping-s2s-events" />

<Accordion title="タイムスタンプ S2S イベント">

[altタイムスタンプロジック図alt](https://support.appsflyer.com/hc/article_attachments/30447054736145)

S2SイベントがAppsFlyerに一括で到着すると、`eventTime`プロパティの値と到着時間に基づいてタイムスタンプが付与されます。`eventTime`プロパティはアプリ内イベントの発生時間を示します。

到着すると、イベントには以下のようにタイムスタンプが付けられます。

* `eventTime`パラメータがイベントレコードに含まれていない場合、イベントの時間はHTTPメッセージの到着時間に設定されます。
* 02:00 UTCより前に到着したイベントには`eventTime`値がスタンプされます。つまり、イベントに`eventTime`のスタンプが付けられるためには、イベント当日か翌日02:00 UTCまでに報告される必要があります。
* 前日またはそれ以前に発生したイベントで02:00 UTC以降に到着した場合、到着時刻（APIコールの時間）でスタンプされます。
* 将来の`eventTime`値で到着するイベント（イベント時間が到着時間を超える場合）：
  * 報告された`eventTime`時間と到着時間が同じ日付である場合、イベントは`eventTime`値でタイムスタンプされます。
  * 報告された`eventTime`が次の日付である場合、イベントは到着時間でタイムスタンプされます。
* 無効な`eventTime`値を持つイベントはHTTPメッセージの到着時間でスタンプされます。

**例**

* `eventTime` = 月曜日の21:00でイベントが送信されます。

| AppsFlyerに到着 | AppsFlyerのタイムスタンプ | 注釈 |
| --- | --- | --- |
| 火曜日01:00 | 月曜日21:00 | 営業終了前に到着。時間は`eventTime`値に設定されています。 |
| 水曜日09:00 | 水曜日09:00 | 営業終了後に到着。時間は到着時間に設定されます。 |

</Accordion>

<div id="sending-negative-revenue" />

<Accordion title="マイナス収益の送信">

収益値がマイナスのイベントは送信可能です。たとえば、購入がキャンセルされた場合です。これを記録するために、パラメータ`af_revenue`に負の値を設定できます。

`af_quantity`を設定する場合、システムロジックに応じて負の値を設定することを検討してください。AppsFlyer は`af_quantity` を使用していません。

</Accordion>

<div id="note-1" />

> 📘 **注意**
>
> <Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview">Incrementalityで計測されるには</Anchor>、S2Sイベントのペイロードに広告IDが含まれている必要があります（iOSの場合はIDFA、Android の場合はGAID）。

<div id="increasing-the-volume-of-data-transactions" />

## データトランザクション量を増加させる方法

段階的スケーリングを使用すると、AppsFlyerは自動スケーリングソリューションにより、1秒あたりの大量トランザクション（TPS）をサポートすることが可能です。例えば：

* 1秒あたり10,000トランザクション（TPS）から始め、最小1分間隔で徐々にスケールしていきます。
  * 00:00:00 - 10K TPS を送信 (ベースライン)
  * 00:01:00 - 12K TPS に増加
  * 00:02:00 - 14K TPS に増加
  * 00:03:00 - 16K TPS に増加
  * 00:04:00 - 18K TPS に増加
* エラーを受信した場合に使用するリトライメカニズムを実装します。

<div id="troubleshooting" />

## トラブルシューティング

<div id="events-arent-displaying-in-the-dashboard" />

<Accordion title="管理画面にイベントが表示されない">

* エンドポイント：利用しているエンドポイントが正しいことを確認してください。
* ペイロードに必須パラメーターが含まれていることを確認してください。[こちら](/docs/server-to-server-events-api-for-mobile-s2s-mobile#mapping-appsflyer-id-with-customer-user-id-cuid)をご覧ください。
* イベントの起動に使用しているAppsFlyer IDが実際のappsflyer\_idであり、実際のアプリインストールに関連していることを確認します。[こちら](/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id)をご覧ください。
* S2Sイベントは、1つのS2Sリクエストでマルチイベントをサポートしません。各イベントは個別のイベントとして送信する必要があります。
  * 応答時間を短縮するため、非同期方式でイベントを送信することができます。
* 概要管理画面では、日付範囲はアプリインストール日（LTV）に関連付けられ、イベントの日付ではありません。
  * 正しい日付範囲を選択するようにしてください。
  * 管理画面の日付範囲が、イベントの日付ではなく、デバイスのインストール日（appsflyer\_id）に対応していることを確認してください。
* イベントローデータレポート：日付範囲はイベントの日付に関連し、インストール日ではありません。

</Accordion>

<div id="events-dont-contain-revenue" />

<Accordion title="イベントには収益は含まれていません">

もしS2Sイベントを送信しても収益が記録されない場合は、送信するJSONが文字列化されていることを確認してください。最も重要な部分は、JSON内のイベント値パラメーターです。次の例に示すように、文字列化する必要があります。

```json
"{\"af_revenue\":\"6\" ,\"af_content_type\":\"wallets\"}"
```

文字列化されていない場合、イベント価値が正しく処理されず、収益が記録されません。

収益の値はいかなる形式でもフォーマットしないでください。小数点を含めることができます。通貨記号やコード、`,` 区切り文字を含めないでください。収益には`-`のプレフィックスを付けることができます。

* 有効な値の例: `123`、`-123.45`、`123.456`
* 無効な値の例: `1,234.56`、`1,234`

</Accordion>

<div id="not-all-fields-are-populated-in-s2s-events" />

<Accordion title="S2Sイベントではすべてのフィールドが入力されるわけではありません。">

S2Sイベントの生データフィールドは、S2Sコールで送信された値のみで構成されています。次のフィールドは S2S APIを通じて報告できないため、ローデータレポートの S2S イベントには入力されません。

* WIFI
* オペレーター
* 言語
* デバイスモデル
* デバイスカテゴリ
* アプリバージョン`app_version_name`を利用できます
* アプリ名

</Accordion>

<div id="S2S_in-app_events_are_wrongly_attributed_as_organic" />

<Accordion title="S2Sアプリ内イベントが誤ってオーガニックと分類される">

S2Sイベント（ログインイベントなど）は、アプリがインストールされてSDKが起動されるとすぐにAppsFlyerに届きます。しかし、AppsFlyerがインストールイベントの処理を完了する前に、これらのS2Sアプリ内イベントが到着した場合（通常20〜30秒以上かかります）、それらは非アトリビュートのオーガニックイベントとしてマークされることがあります。

インストール直後に発生するS2Sアプリ内のイベントをサーバーに報告する前に、短い遅延を設けることをお勧めします。

</Accordion>

<div data-zendesk-anchors="servertoserver-events-api-for-mobile=%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E9%96%93%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88api-for-%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB h_01H9Q8KBYGXAA8H4AKKXP8T8DY=%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E9%96%93%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88api-for-%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB populating-parameters=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9Q8KBYGHY1SDSMSFZRT2JXZ=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9Q8KBYG6W4TERWHARZZZASZ=difference-between-organic-and-nonorganic h_01H9Q8KBYG0JCCGTEJW3GXZMF1=%E4%BE%8B h_01H9Q8KBYG6EBKPS5Y2KC1QT7G=mapping-appsflyer-id-with-customer-user-id-cuid h_01H9Q8KBYGR26VMQR9Y0CK85F6=fetching-the-appsflyer-id h_01H9Q8KBYG8ASB1WB9X4XM3CYZ=time-stamping-s2s-events h_01H9Q8KBYG63SZWNM4GWSJG605=sending-negative-revenue h_01JWV0HR3P78NFBHWY1KM97M98=%E6%B3%A8%E6%84%8F increasing-the-volume-of-data-transactions=%E3%83%87%E3%83%BC%E3%82%BF%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E9%87%8F%E3%82%92%E5%A2%97%E5%8A%A0%E3%81%95%E3%81%9B%E3%82%8B%E6%96%B9%E6%B3%95 h_01HX77GDZ1CCWN48CN616P860D=%E3%83%87%E3%83%BC%E3%82%BF%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E9%87%8F%E3%82%92%E5%A2%97%E5%8A%A0%E3%81%95%E3%81%9B%E3%82%8B%E6%96%B9%E6%B3%95 troubleshooting=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01H9Q8KBYGYR9Y7DPCNWSB4QY0=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01H9Q8KBYGYHCWAPPNMG9WB8QN=events-arent-displaying-in-the-dashboard h_01H9Q8KBYGDC68637RH4DE2FZX=events-dont-contain-revenue h_01H9Q8KBYGDQKZF90EJAXRTMF3=not-all-fields-are-populated-in-s2s-events h_01JWV0CS5BFBXDT333794BHFER=S2S_in-app_events_are_wrongly_attributed_as_organic" />
