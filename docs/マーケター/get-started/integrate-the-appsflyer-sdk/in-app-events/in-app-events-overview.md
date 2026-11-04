---
title: アプリ内イベントの概要
metadata:
  keywords:
    - ios
    - Rich
    - In-App
    - android
    - Advertisers
    - In app events
    - Marketers
    - inapp events
    - attribution
    - inapp
    - inapp events attribution
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-11-02T08:12:51Z'
  edited_at: '2026-10-29T07:44:28Z'
  id: 115005544169
  locale: ja
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ja/articles/115005544169
---
> **At a glance:** ログイン、登録、アプリ内購入など、インストール後に発生するアプリ内イベントを記録し、メディアソースやキャンペーンに紐づけます。

<div id="why-record-in-app-events" />

## アプリ内イベントを記録する目的

アプリ内イベントを使うと、アプリ内で何が起きているかを把握でき、アプリユーザーの価値や**各メディアソースからの流入の質**を評価できます。アプリ内イベントを記録することで、ROI（投資対効果）やLTV（顧客生涯価値）などの主要業績評価指標（KPI）を計測できます。

ユーザーの登録、チュートリアルの完了、カートへの商品追加、購入などを、詳細情報とともにアプリ内イベントとして記録できます。インストール後の分析を行うには、アプリ内イベントの実装が必要です。

<div id="about-in-app-events" />

## アプリ内イベントについて

アプリ内イベントはイベント名で構成され、イベントパラメータを含めることもできます。イベントパラメータを含む場合も、呼び方はアプリ内イベントです。イベントパラメータを使うと、イベントの背景や詳細情報を取得できます。たとえば、ユーザーが予約したことはイベントから分かりますが、イベントパラメータを使うと、購入の種類、目的地、収益などの詳細も把握できます。

![travel.png](https://files.readme.io/0ebe64e7aa3ccc40ef014c55ee3a91edf678e21b2d00a7f8be1298d6b494e925-30858351609617.png)

<div id="tip" />

> 👍 **ヒント**
>
> アプリ内イベントについて、さらに詳しく知りたいですか？ <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7774/play/18613/in-app-events-and-integrated-partners-part-1">AppsFlyer Learning Portalのコース</Anchor>で、短時間で分かりやすく学べます。

<div id="predefined-and-custom-events" />

### 定義済みイベントとカスタムイベント

アプリ内イベントを送信するには、開発者がアプリ内の該当箇所にコードを実装する必要があります。イベント名とイベントパラメータは、次のように分類されます。

* **定義済み**：さまざまなアプリで共通して使われるイベント名とイベントパラメータです。次の理由から、できるだけ<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#定義済みのイベント名">定義済みのイベント名</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#定義済みのイベントパラメータ">イベントパラメータ</Anchor>を使用することを強く推奨します。
  * 定義済みの名称を使うと、AppsFlyerのイベントをパートナー側のイベントにスムーズに対応付けられます。
  * AppsFlyerがイベント名やイベントパラメータ名を変更しても、既存の実装との後方互換性が保たれます。
* **カスタム：** アプリ内の特定の利用シーンに合わせて、独自に定義するイベント名とパラメータです。イベント名やパラメータ名には任意の文字列を使用できますが、カスタムイベントは開発者による保守が必要です。[ヒント](/docs/in-app-events-overview#tips)と[制限事項](/docs/in-app-events-overview#limitations)を参照してください。

<div id="revenue-in-in-app-events" />

## アプリ内イベントの収益

以下のセクションでは、収益イベントをAppsFlyerに送信し、イベントに含まれるパラメータを対応付ける方法を説明します。 ROI360を契約すると、アプリ内購入、サブスクリプション、広告による収益を含め、最も正確かつ最新のコスト・収益データを取得できます。 <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-cost-and-revenue-data">ROI360の詳細はこちら</Anchor>

<Accordion title="イベント収益">

`af_revenue`は、収益を送信するための標準パラメータです。 `af_revenue`で送信された収益は、AppsFlyer製品全体の収益指標（ダッシュボード、LTV、コホート、ROAS、ROI）に反映され、パートナーへのポストバックにも含まれます。自社のビジネスロジック上、実際に収益が発生するアプリ内イベントでは、必ずこのパラメータを使用してください。

アプリストアの手数料や税金を差し引いた金額など、独自のロジックを適用した収益も送信したい場合は、`af_net_revenue`を追加で送信できます。これは`af_revenue`に追加するものであり、置き換えるものではありません。後述の[純収益](#net-revenue)を参照してください。

* <Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#record-revenue">SDKでの収益の記録</Anchor>
* Unityでの収益の記録

ユーザーが購入をキャンセルした場合や、返金を行った場合は、マイナスの収益も記録できます。マイナスの収益を記録するには、`af_revenue`に渡す収益値の先頭にマイナス記号（-）を付けます。

収益値には、数字と、必要に応じて小数点のみを含めてください。

* 他の文字を含めたり、別の書式を適用したり**しないでください**。カンマ、通貨記号（$など）、特殊文字、テキストは使用できません。
* AppsFlyerは、収益値を**小数点以下最大5桁の精度**で提供します。
* 値の範囲は、米ドルで-1,000,000～1,000,000、または元の通貨でこれに相当する金額としてください。この範囲外の値は、ローデータレポートには含まれますが、集計レポートには含まれません。
* 例：1234.56
* 収益を文字列として送信する場合は、引用符内の値が有効である必要があります。例："1234.56"

<div id="note" />

> 📘 **注意**
>
> AppsFlyerは、SDKから`af_revenue`で送信された収益をそのまま表示します。 VAT（付加価値税）やアプリストアの手数料などは、開発者がSDK側で計算して送信する金額に反映しない限り、AppsFlyer側では計算しません。これらを差し引いた収益を送信する場合は、`af_net_revenue`で追加送信してください（[純収益](#net-revenue)を参照）。

`af_currency`は、`af_revenue`（または`af_price`）で指定する金額の通貨を表します。イベントのパラメータに`af_currency`が含まれていない場合、AppsFlyerはデフォルト値の「USD」を設定して送信します。

`af_price`は、収益に計上しない金額を送信するパラメータとして使用できます（「カートへの追加」イベントなど）。このパラメータは、個々の商品の価格を示します。購入全体の合計金額は、`af_revenue`パラメータで示します。

</Accordion>

<Accordion title="純収益">

`af_net_revenue`は、任意で追加できる収益パラメータです。アプリストアの手数料や税金を差し引いた収益、売上総利益、サービス手数料を差し引いた収益など、独自のロジックを適用した金額を送信できます。

`af_net_revenue`**は、**`af_revenue`**を置き換えるものではありません。** `af_revenue`は通常どおり送信し、純収益を確認したい場合は`af_net_revenue`も追加してください。

* 通貨は`af_revenue`と同様に、`af_currency`で指定した通貨になります（デフォルトはUSD）。
* `af_net_revenue`には定義済みのSDK定数がないため、キーを`af_net_revenue`とするカスタムパラメータとして送信する必要があります。
* 純収益は、<Anchor target="_blank" href="/marketers/ja/docs/my-dashboards#metrics">マイダッシュボード</Anchor>の純収益ベースの指標（純収益［Net revenue］、純収益ベースのROI［Net ROI］・ROAS［Net ROAS］・ARPU［Net ARPU］、純利益［Net profit］）に使用されます。

<div id="note-1" />

> 📘 **注意**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-roi360-store-revenue">ROI360のストア収益</Anchor>を利用している場合、アプリ内購入とサブスクリプションのイベントには`af_net_revenue`が自動で設定されるため、それらのイベントで`af_net_revenue`を送信する必要はありません。純収益は、総収益からアプリストアの手数料と税金を差し引いた金額です。

</Accordion>

<Accordion title="収益の通貨">

AppsFlyerが通貨設定と通貨換算をどのように処理するかを理解しておくことが重要です。

AppsFlyerは、アプリ内イベントの通貨がアプリ設定の通貨と異なる場合、通貨換算を行います。

![revenue_normalization_flow.png](https://files.readme.io/f890d34168f92202c94da4bfa548bd0f471c98dec9c8d4282b2549f5878e9321-46334674326033.png)

上の図は、次の処理を示しています。

1. アプリ内イベントを送信（イベントごとに通貨が異なる場合あり）
2. AppsFlyerがすべての通貨を米ドルに換算
3. AppsFlyerが収益データを処理
4. ダッシュボードの収益データをアプリ設定の通貨で表示
5. ローデータレポートに、イベントの通貨とアプリ設定の通貨の両方で収益データを記載

AppsFlyerは、通貨換算に<Anchor target="_blank" href="https://openexchangerates.org/">Open Exchange Rates</Anchor>を使用します。為替レートは1時間ごとに更新されます。通貨換算の際は、その時点で最新の為替レートを使用します。

<div id="currency-conversion" />

#### 通貨換算

<span id="h_01HDBZW9XERK3VN1GS8GHM911W"></span>**例**

アプリ設定で通貨をGBPに設定したとします。フランスのユーザーがアプリで商品を購入します。価格はEUR（€）で表示されています。 AppsFlyerへ送信するアプリ内イベントの例：

```java
Map<String, Object> eventValue = new HashMap<String, Object>();
eventValue.put(AFInAppEventParameterName.REVENUE,200);
eventValue.put(AFInAppEventParameterName.CONTENT_TYPE,"category_a");
eventValue.put(AFInAppEventParameterName.CONTENT_ID,"1234567");
eventValue.put(AFInAppEventParameterName.CURRENCY,"EUR");
AppsFlyerLib.getInstance().trackEvent(getApplicationContext() , AFInAppEventType.PURCHASE , eventValue);
```

この場合、AppsFlyerは収益をEURからUSDに換算し、その後GBPに換算します。為替レートを€1＝$1.13とします。すると、€200は$226.85になります。次に、AppsFlyerはUSDからGBPに換算します。為替レートを$1＝£0.78とします。すると、$226.85は£176.92になります。

<div id="currency-display" />

#### 通貨の表示

<Anchor target="_blank" href="/marketers/ja/docs/app-settings#localization-currency">通貨はアプリ設定で指定します</Anchor>。アプリ設定で指定した通貨が、ダッシュボードに表示される通貨です。アプリ内イベントをどの通貨で送信しても、ダッシュボードの収益は常にアプリ設定の通貨で表示されます。

<span id="h_01HDBZW9XEQNG1RDH7A8H002ZD"></span>**例**

アプリ設定とは異なる通貨で、または通貨を指定せずにアプリ内イベントを送信したとします。この例では、アプリ設定の通貨は**GBP**です。

AppsFlyerに3件のアプリ内イベントを送信します。

1. イベントAの収益は**234**、通貨は**GBP**です。
2. イベントBの収益は**171**、通貨は**EUR**です。
3. イベントCの収益は**171**ですが、**通貨は指定されていません**。

<div id="revenue-data-in-the-dashboard" />

#### ダッシュボードの収益データ

ダッシュボードに表示される収益は、アプリ内イベントの通貨からUSDに換算し、さらにアプリ設定の通貨に**換算した値**です。

イベントに通貨を指定していない場合、**AppsFlyerはデフォルトでUSDを使用します**。ダッシュボードでは、イベントと収益が次のように表示されます。

| アプリ内イベント | ユニークユーザー数 | アクション数 | 収益 |
| --- | --- | --- | --- |
| A | 1 | 1 | £234 |
| B | 1 | 1 | £149.4 - EURからUSDに換算し、さらにGBPに換算。 |
| C | 1 | 1 | £132.9 - 通貨の指定がないため、デフォルトのUSDを使用。 USDからGBPに直接換算。 |

<div id="revenue-data-in-raw-data-reports" />

#### ローデータレポートの収益データ

アプリ設定の通貨を**GBP**にして、別の通貨でアプリ内イベントを送信した場合、ローデータレポートにはアプリ設定の通貨とアプリ内イベントの通貨の両方で収益が表示されます。

アプリ設定の通貨を**GBP**にして、通貨を指定せずにアプリ内イベントを送信した場合、ローデータレポートにはアプリ設定の通貨とUSDの両方で収益が表示されます。

アプリ内イベントのローデータレポートでは、イベントと収益が次のように表示されます。

| イベント | イベント収益 | イベント収益の通貨 | イベント収益（GBP） |
| --- | --- | --- | --- |
| A | 234 | GBP | 234 |
| B | 171 | EUR | 149.4 - EURからUSDに換算し、さらにGBPに換算。 |
| C | 171 | USD | 132.9 - 通貨の指定がないため、デフォルトのUSDを使用。 USDからGBPに直接換算。 |

</Accordion>

<div id="sending-events" />

## イベントの送信

AppsFlyerにアプリ内イベントを送信するには、いくつかの方法があります。

* <Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">**AppsFlyer SDK：**</Anchor>最も一般的なイベント送信方法です。 SDKのAppsFlyerアプリ内イベントAPIを使ってアプリ内でのユーザー操作を記録し、アプリ内イベントとして送信できます。
* <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">**サーバー間（S2S）API：**</Anchor>モバイルアプリ外で発生するイベントを、サーバー間（S2S）APIでAppsFlyerに直接送信します。たとえば、Webとモバイルの両方を利用しているユーザーについて、両方で発生したイベントを記録し、AppsFlyerで同一ユーザーに紐づけられます。アプリ内イベントだけでなく、Webサイトやコールセンターで発生するイベント、実店舗での購入なども対象にできます。
* <Anchor target="_blank" href="/marketers/ja/docs/purchase-and-subscription-validation-overview">**レシート検証**</Anchor>：AppleやGoogleなどの決済プラットフォームが、報告されたアプリ内購入が実際に行われたかを検証する安全な仕組みです。購入の検証は、不正な収益イベントを防止するための主要な手段です。実際の収益を把握し、未完了のアプリ内購入を除外することにも役立ちます。
* <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-for-hybrid-apps">**ハイブリッドアプリ：**</Anchor>ネイティブ画面とHTMLコンテンツを組み合わせたアプリでも、アプリ内イベントを記録できます。ただし、SDKがイベントを送信できるのはネイティブ側のみのため、開発者はすべてのイベントデータをネイティブコードに渡す必要があります。

<div id="setting-up-in-app-events" />

## アプリ内イベントの設定

アプリ内イベントの設定では、マーケターと開発者が次のように連携する必要があります。

| 手順 | 役割 | タスク | 詳細 |
| --- | --- | --- | --- |
| 1 | マーケター | 計測するアプリ内イベントを決定します。<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#定義済みのイベント名">イベント名</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure#定義済みのイベントパラメータ">イベントパラメータ</Anchor>を[定義](/docs/in-app-events-overview#defining-an-inapp-event)し、開発者に伝えます。 | 購入、登録、共有など、ユーザーの質を評価するKPIとして利用できる3～5個のイベントから始めることを推奨します。イベントパラメータは任意で、どのイベント名にも任意のイベントパラメータを使用できます。<br /><br />代表的なアプリ内イベントについては、[業種別の推奨イベント](/docs/in-app-events-overview#recommended-events-by-business-vertical)を参照してください。 |
| 2 | 開発者 | アプリ内の該当箇所にコードを実装します。 | 開発者向けドキュメントは<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk">こちら</Anchor>です。 |
| 3（任意） | マーケター | 開発者と協力して、<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">カスタマーユーザーID（CUID）フィールド</Anchor>を設定します。 | CUIDをキーとしてAppsFlyerのアトリビューションデータと他のデータを照合することで、アプリ内イベントデータに情報を補足できます。 |
| 4（任意） | マーケター | ダッシュボードで、AppsFlyerのイベントを該当するパートナー側のイベントに<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#イベントマッピング">対応付けます</Anchor>。 | 連携するパートナーに応じて、継続的に行う作業です。 |

<Accordion title="アプリ内イベントの定義">

計測するアプリ内イベントを決めたら、<Anchor target="_blank" href="https://evgen.appsflyer.com/">アプリ内イベント生成ツール</Anchor>を使い、次のようにイベントとパラメータを定義します。

1. 記録する利用シーンに最も適したイベント名を選択します。
2. イベントに紐づけるイベントパラメータを選択します。イベントの背景情報を補足し、データを充実させられるパラメータを選んでください。
3. アプリ内イベント生成ツールから完成したファイルをダウンロードし、開発者に共有します。

<span id="h_01HDBZW9XFN2B8AC18VW99G8Z6"></span>**例**

eコマースアプリのマーケターが、人気のある商品カテゴリを把握し、商品の閲覧と購入の関係を分析するために、ユーザーが閲覧したコンテンツの種類を記録したいとします。

次の表は、マーケターから開発者に渡すイベント構造の例です。

<table><thead><tr><th>イベント名</th><th>イベントパラメータ</th><th>パラメータの値</th><th>イベントの発生タイミング</th></tr></thead><tbody><tr><td rowspan="3">af_content_view</td><td>af_price</td><td>商品価格</td><td rowspan="3"><span>ユーザーが特定の商品の詳細ページを閲覧したとき</span></td></tr><tr><td><span>af_content_type</span></td><td><span>商品のカテゴリ名（例：shoes）</span></td></tr><tr><td><span>af_content_id</span></td><td><span>商品ID（例：SKU）</span></td></tr></tbody></table>

</Accordion>

<Accordion title="業種別の推奨イベント">

次の表に、業種別の推奨アプリ内イベントと、その発生の流れを紹介する記事へのリンクをまとめています。

| 業種 | 記事タイトル |
| --- | --- |
| <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="38px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-gaming-app-events">ゲームアプリの推奨イベント</Anchor> |
| <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="37px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-ecommerce-app-events">eコマースアプリの推奨イベント</Anchor> |
| <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="39px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-entertainment-app-events">エンターテインメントアプリの推奨イベント</Anchor> |
| <Image alt="banking.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="36px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-finance-and-banking-app-events">金融・銀行アプリの推奨イベント</Anchor> |
| <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="36px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-p2p-lending-app-events">P2Pレンディングアプリの推奨イベント</Anchor> |
| <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="37px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-online-education-app-events">オンライン教育アプリの推奨イベント</Anchor> |
| <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="37px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-ride-hailing-app-events">配車アプリの推奨イベント</Anchor> |
| <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="38px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-flight-booking-app-events">フライト予約アプリの推奨イベント</Anchor> |
| <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="37px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-hotel-booking-app-events">ホテル予約アプリの推奨イベント</Anchor> |
| <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="37px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-healthcare-app-events">ヘルスケアアプリの推奨イベント</Anchor> |
| <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="39px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-telecommunication-app-events">通信サービスアプリの推奨イベント</Anchor> |
| <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="39px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-ewallet-app-events">電子ウォレットアプリの推奨イベント</Anchor> |
| <Image alt="soccer_ball.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="39px" /> | <Anchor target="_blank" href="/marketers/ja/docs/recommended-sports-betting-events">スポーツベッティングの推奨イベント</Anchor> |

</Accordion>

<Accordion title="アプリ内イベントデータの確認">

アプリ内イベントは、ユーザーの利用期間全体を通じて、インストールに貢献したメディアソースに紐づけられます。イベントデータは、<Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTVデータまたはアクティビティデータ</Anchor>として表示されます。

アプリ内イベントデータは、次の場所で確認できます。

* Overview dashboard：ユーザー獲得（UA）のLTVベースの成果をリアルタイムで表示します。**注意**：アプリ内イベントで報告されたオーガニック・非オーガニックユーザー別の収益と、<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">二重アトリビューション</Anchor>の対象となるリターゲティング収益が含まれます。
* イベントページ：メディアソースごとのアプリ内イベントの成果をLTVベースで表示します。
* <Anchor target="_blank" href="/marketers/ja/docs/activity-dashboard">アクティビティページ</Anchor>：選択した期間のアプリ内のアクティビティを表示します。
* <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">アプリ内イベントのローデータレポート</Anchor>：アクティビティデータ、つまり全ユーザーの操作を時系列で並べた一覧を表示します。このレポートには、次のようなイベントパラメータの値が含まれます。

  ```json
  {
    "af_level":"10",
    "af_score":"3387",
    "arena":"7",
    "char_type":"paladin"
  }
  ```

  ローデータレポートは、有料オプション機能です。

<div id="note-2" />

> 📘 **注意**
>
> アプリ内イベントのパラメータ値を確認できるのは、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview#アプリ内イベント">アプリ内イベントのローデータレポート</Anchor>のみです。 Overview dashboard、イベントダッシュボード、アクティビティダッシュボードや、集計データレポートには表示されません。

</Accordion>

<Accordion title="ヒント">

アプリ内でイベント名やパラメータを定義する際は、次の点に注意してください。

* ローデータレポートの一貫性を保つため、すべてのプラットフォームで同じアプリ内イベント名と構造を定義・使用することを推奨します。
* 異なる流入元のユーザーの質を比較しやすくするため、計測するイベントの種類は必要最小限にしてください。
* **ユーザーのプライバシーを保護することが重要です。ユーザーを直接特定できる、収集・送信が制限されたデータをアプリ内イベント値に含めないでください**。**たとえば、メールアドレス、氏名、識別番号、一部の地域では郵便番号が該当します。制限対象のデータについては、**<Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">**サービスのプライバシーポリシー**</Anchor>**を参照してください。**
* AppsFlyerは、<Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">広告接触</Anchor>時のデバイスのIPアドレスをデータに含めます。国・地域や利用シーンによっては、IPアドレスが個人を特定できる情報（PII）とみなされる場合があります。 IPアドレスは、デバイスのおおまかな位置（市区町村レベル）の特定に使用しますが、具体的な住所の特定には使用しません。必要に応じて<Anchor target="_blank" href="/marketers/ja/docs/apply-ip-masking-to-user-data">IPアドレスをマスキング</Anchor>し、ローデータレポートに表示されないように設定できます。
* AppsFlyerにおける収益データの取得元は、アプリ内イベントのみです。各イベントに収益値を設定し、アプリのダッシュボードで確認できます。詳細は、[収益関連のパラメータ](/docs/in-app-events-overview#revenue-events)を参照してください。 ![revenue_data.png](https://files.readme.io/9ada01568583ef5eb7d39ca09b2ae9dd68afb9415859574f35c477cf46d6272c-46334666577425.png)

</Accordion>

<Accordion title="制限事項">

アプリ内でイベント名やパラメータを定義する際は、次の点に注意してください。

* アプリ内イベント名には、小文字の英数字（a～z、0～9）のみを使用することを推奨します。イベント名は大文字と小文字を区別するため、ローデータではaf\_purchaseとaf\_PURCHASEは別のイベントです。ただし、集計レポートやダッシュボード（Overview dashboardやイベントダッシュボードなど）では小文字のみが認められるため、1つのイベントとして表示される場合があります。
* 1日に扱えるイベント名の種類数の上限は300です。<Anchor target="_blank" href="/marketers/ja/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_events_limit">詳細はこちら</Anchor>
* ユニークユーザー数は、アプリのインストール後、最初の100イベントについてのみカウントされます。
* イベント名の先頭に使用できない文字：" = + -
* イベント値に+を含めないでください。ただし、URL内でエンコードされている場合や、<Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">ASCII</Anchor>に従ってエンコードされている場合を除きます。
* イベント名に空白は使用できません。イベント名の前後にアンダースコア（\_）を使用することはできます。
* ローデータレポートで値が切り詰められないよう、イベント値は2,000文字以内にしてください。ただし、SDKから送信する場合は、HTTPリクエストの送信データが切り詰められないよう、イベント値を1,000文字未満にすることを推奨します。
* 参照元URLをイベント値に含める場合は、<Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">URLエンコード</Anchor>する必要があります。
* Meta adsには、イベント名とパラメータに関する制限があります。制限の詳細は<Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#limits">こちら</Anchor>を参照してください。

</Accordion>

<div id="faq" />

## よくある質問

以下では、アプリ内イベントに関するよくある質問に回答します。

<Accordion title="収益パラメータの使用方法">

任意のパラメータ名とイベントで収益値を送信できます。ただし、AppsFlyerのローデータと集計データに収益（[マイナスの収益](/docs/in-app-events-overview#revenue-events)を含む）を記録するには、`af_revenue`パラメータを使用する必要があります。自社のビジネスロジック上、実際に収益が発生するアプリ内イベントでは、必ずこのパラメータを使用してください。

`af_currency`は、`af_revenue`（または`af_price`）で指定する金額の通貨を表します。イベントのパラメータに`af_currency`が含まれていない場合、AppsFlyerはデフォルト値の「USD」を設定して送信します。 `af_revenue`パラメータの詳細は、[収益アトリビューションガイド](/docs/in-app-events-overview#revenue-events)を参照してください。

手数料や税金を差し引いた金額など、独自のロジックを適用した収益も送信する場合は、`af_revenue`とともに`af_net_revenue`をカスタムパラメータとして送信してください。 `af_net_revenue`は、`af_revenue`を置き換えるものではありません。詳細は、[純収益](#net-revenue)を参照してください。

</Accordion>

<Accordion title="AppsFlyerによるイベントのアトリビューション">

アプリ内イベントは、アプリのインストール時のメディアソースに紐づけられます。

アプリのインストール時（初回起動時）に、AppsFlyerはさまざまな<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#アトリビューション方法">アトリビューション手法</Anchor>を使って、インストールのアトリビューション先を判断します。同時に、AppsFlyer SDKは新しい一意の<Anchor target="_blank" href="/marketers/ja/docs/about-device-identifiers#appsflyer-id">AppsFlyer ID</Anchor>を生成し、アトリビューション情報に紐づけます。

同じデバイスで、その後アプリ内で実行されるすべてのアプリ内イベントには、このIDが含まれます。これにより、AppsFlyerはイベントを元のメディアソースに紐づけられます。広告主は、この仕組みによって、アプリ内でのユーザーの一連の行動を追跡できます。

最近リターゲティングされたユーザーのイベントは、<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">二重アトリビューション</Anchor>の対象になる場合があります。

AppsFlyerは、インストールがアトリビューションされていても、次の場合には、その後のイベントを**オーガニック**として扱います。

* メディアソースの規約により、[ユーザーレベルデータの削除が義務付けられている場合](/docs/in-app-events-overview#how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations)
* ユーザーがデバイスに保存されたアプリのデータを削除したため、新しいAppsFlyer IDが生成された場合

</Accordion>

<Accordion title="デバイスがオフラインでもイベントは記録されますか？">

インターネットに接続していない状態でユーザーがイベントを実行した場合も、AppsFlyerはイベントを記録できます。処理の流れは以下のとおりです。

1. SDKはAppsFlyerのサーバーにイベントを送信し、成功応答を待ちます。
2. 成功応答を受信しなかった場合、イベントはキャッシュに保存されます。
3. 次に成功応答を受信すると、保存されたイベントをサーバーに再送信します。
4. キャッシュに複数のイベントがある場合は、1件ずつ順番に送信します。

<div id="note-3" />

> 📘 **注意**
>
> SDKのキャッシュに保存できるのは最大40イベントで、オフライン中に発生したイベントのうち、最初の40件のみが保存されます。それ以降、次の成功応答を受信するまでに発生したイベントは破棄されます。
>
> ローデータに表示されるイベント時刻は、デバイスが再びオンラインになった後、イベントがAppsFlyerに送信された時刻です。イベントが実際に発生した時刻ではありません。

</Accordion>

<Accordion title="複数の商品情報を含むアプリ内イベントとは何ですか？設定方法は？">

複数の商品情報を含むアプリ内イベントでは、1回のAPI呼び出しで複数の商品情報を送信できます。たとえば、1回のセッションで複数の商品をカートに追加するなど、密接に関連するユーザー操作をまとめたい場合に役立ちます。

対応するアドネットワークに複数の商品情報を含むアプリ内イベントを送信するには、`af_order_info`オブジェクトを使用することを推奨します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/item-level-order-data-for-ad-networks-af-order-info">アドネットワーク向けの商品単位の注文データ（af\_order\_info）</Anchor>を参照してください。

**例**（推奨形式：フィールドごとに、各商品の値を配列で指定）：

```json
{
  "af_order_info": {
    "sku": ["ID1", "ID2", "ID3"],
    "revenue": [4.99, 9.99, 2.50],
    "qty": [1, 1, 2]
  }
}
```

フィールドの全一覧（商品あたり最大7フィールド）と、商品ごとに1つのオブジェクトを使用する別の形式については、<Anchor target="_blank" href="/marketers/ja/docs/item-level-order-data-for-ad-networks-af-order-info">アドネットワーク向けの商品単位の注文データ（af\_order\_info）</Anchor>を参照してください。

別の方法として、従来どおり`af_content`をJSON配列として使い、イベントを構成することもできます。配列内の各オブジェクトには、`id`と`quantity`を含める必要があります。 `af_content_list`は任意で、省略できます。

<span id="h_01KSMX2ECGTDXQP3G9PZW1PFQD"></span>**例**

```json
{
  "af_revenue": 4.99,
  "af_currency": "USD",
  "af_order_id": "12345",
  "af_content": "[{\"id\":\"ID1\",\"quantity\":\"1\"},{\"id\":\"ID2\",\"quantity\":\"1\"},{\"id\":\"ID3\",\"quantity\":\"2\"}]"
}
```

<div id="important" />

> 🚧 **重要**
>
> `af_content`の文字列が1,000文字を超えると、AppsFlyerは`fb_content`パラメータを含めずにMetaにイベントを送信する場合があります。このとき`af_content_list`も含まれていないと、Metaは商品を識別するデータを受信できません。商品数の多いイベントでは、`af_content`を1,000文字未満にしてください。

Metaへの複数の商品情報を含むアプリ内イベントの送信については、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-in-app-event-mapping#複数の商品を含むアプリ内イベントのmeta広告への送信">Meta adsへの複数の商品情報を含むアプリ内イベントの送信</Anchor>を参照してください。

**注意：** AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#limitations">Audiences</Anchor>では、イベント属性で配列はサポートされておらず、数値または文字列のみを使用できます。

</Accordion>

<Accordion title="1回の取引に複数の商品を含められますか？">

1回の取引に複数の商品を含めることができます。各イベントパラメータに単一の値を指定する代わりに、取引に含まれる各商品の値をカンマで区切った配列として指定できます。形式はJSON文字列にしてください。

<span id="h_01HDBZW9XFB9TAT8W4CGNP1892"></span>**例**

スミスさんが、米国のオンラインストアで同じシャツを2枚、靴を1足、帽子を1個、1回の取引で購入したとします。すべてのパラメータで、商品の並び順を揃える必要があります。

```json
"{\"af_content_id\": [\"123\",\"988\",\"399\"], \"af_quantity\": [\"2\",\"1\",\"1\"], \"af_price\": [\"25\",\"50\",\"10\"], \"af_revenue\": \"110\", \"af_currency\": \"USD\"}"
```

複数の商品は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration">ポストバック</Anchor>内の配列として転送されます。現在、Meta adsとX Adsは、配列パラメータを正しく解析できません。この問題に対応するため、AppsFlyerは、これらのSelf-Reporting Network（SRN）に商品数（`af_quantity`）を配列で送信せず、合計値を送信します。この例では、Meta adsに`af_quantity=4`が送信されます。

<div id="notes" />

> 📘 **注意**
>
> * AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#limitations">Audiences</Anchor>では、イベント属性で配列はサポートされておらず、数値または文字列のみを使用できます。
> * 次のアプリ内イベントで複数の商品を使用できます：
>   `af_add_to_cart`、`af_add_to_wishlist`、`af_tutorial_completion`、`af_initiated_checkout`、`af_purchase`、`af_rate`、`af_spent_credits`、`af_content_view`、`af_travel_booking`、`af_update`

</Accordion>

<Accordion title="AppsFlyerはイベントの重複をどのように排除しますか？">

AppsFlyerには、アプリ内イベントの重複を排除する仕組みがあります。各アプリ内イベントについて、同じappsflyer\_idから、過去10秒未満の間に同一のアプリ内イベントが送信されていないかを確認します。同一イベントが見つかった場合は、重複するイベントを除外します。

両方のイベントで、次のフィールドがすべて同じ場合に、同一イベントとみなされます。

* イベント名
* イベントの値
* アプリID
* AppsFlyer ID

<div id="note-4" />

> 📘 **注意**
>
> 重複排除の対象は、SDKから送信されたアプリ内イベントのみです。
>
> S2Sアプリ内イベントの重複排除は行われません。

</Accordion>

<Accordion title="ユーザーレベルのデータの保持期間と削除義務は？">

AppsFlyerは、連携の種類とパートナーの要件に基づいて、ユーザーレベルのローデータを保持します。集計データは、最大5年間保持される場合があります。

保持期間は、メディアソースや配信方法（Data Locker、Pull APIなど）によって異なり、法律、契約、パートナーに対する義務により変更される場合があります。

ユーザーレベルデータの削除後は、そのユーザーに関連するイベントがオーガニックとして表示されます。過去の集計データは変更されません。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/user-level-data-retention#データの保持および削除に関する義務">データの保持と削除義務</Anchor>を参照してください。

</Accordion>

<Accordion title="イベントにOS（オペレーティングシステム）パラメータを追加する必要はありますか？">

* Android SDKとiOS SDKは、OS（オペレーティングシステム）パラメータを自動で追加します。
* <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API</Anchor>では、2021年7月1日以降、iOSアプリのOS（オペレーティングシステム）パラメータを送信する必要があります。このパラメータを送信しない場合、iOS 14.5のユーザーからのデータとみなされ、<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">ローデータの提供方法</Anchor>に影響します。

</Accordion>

<Accordion title="パートナー側でイベントの重複を排除するには？">

同じイベントをアドネットワークにも直接送信している場合（自社でパートナーのコンバージョンAPIに対応する処理を開発した場合など）、CAPIでの直接連携とAppsFlyer経由の両方で同じ`event_id`を送信することで、パートナーがイベントの重複を排除できるようにします。そのためには、`event_value`フィールド内に「af\_customer\_event\_id」というフィールドを含め、広告主側からパートナーに直接送信する`event_id`フィールドにも同じ値を設定してください。

この方法は、`metaweb_int`、`tiktokweb_int`、`snapweb_int`、`pinterest_int`、`pinterest_int`でサポートされています。

</Accordion>

<div id="see-also" />

## 関連情報

* <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration">アプリ内イベントのポストバック設定</Anchor>

<div data-zendesk-anchors="why-record-inapp-events=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E8%A8%98%E9%8C%B2%E3%81%99%E3%82%8B%E7%9B%AE%E7%9A%84 h_01HDBZW9XEBTY13MG4AN93RNCD=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E8%A8%98%E9%8C%B2%E3%81%99%E3%82%8B%E7%9B%AE%E7%9A%84 about-inapp-events=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HDBZW9XEBDSDA9T5X5B6KGTG=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HDBZW9XE3Z40JE9576C4XSF4=%E3%83%92%E3%83%B3%E3%83%88 predefind-and-custom-events=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A8%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 01J9XGXGC7R9B19MMX4CQV7DAY=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A8%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 revenue-in-inapp-events=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E5%8F%8E%E7%9B%8A 01J9XGXGC990R3AG0R0XT9E5Y7=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E5%8F%8E%E7%9B%8A h_01M43GXKW5NCRE5MJG45EG9AYX=%E6%B3%A8%E6%84%8F h_NETREVENUE0002=%E6%B3%A8%E6%84%8F-1 currency-conversion=%E9%80%9A%E8%B2%A8%E6%8F%9B%E7%AE%97 h_01HDBZW9XEMGA5RAW0DBBPV3FQ=%E9%80%9A%E8%B2%A8%E6%8F%9B%E7%AE%97 currency-display=%E9%80%9A%E8%B2%A8%E3%81%AE%E8%A1%A8%E7%A4%BA h_01HDBZW9XE85YC3JHG58YYAB8F=%E9%80%9A%E8%B2%A8%E3%81%AE%E8%A1%A8%E7%A4%BA revenue-data-in-the-dashboard=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E5%8F%8E%E7%9B%8A%E3%83%87%E3%83%BC%E3%82%BF h_01HDBZW9XEVWB9045N0YEVWE6Z=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E5%8F%8E%E7%9B%8A%E3%83%87%E3%83%BC%E3%82%BF revenue-data-in-raw-data-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%8F%8E%E7%9B%8A%E3%83%87%E3%83%BC%E3%82%BF h_01HDBZW9XEGYFD3W9FT1N3ZGQW=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%8F%8E%E7%9B%8A%E3%83%87%E3%83%BC%E3%82%BF sending-events=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1 h_01HDBZW9XFESG6MP9QF1XCJKE6=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E9%80%81%E4%BF%A1 setting-up-inapp-events=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDBZW9XF13AGRCN2HJ18RHS2=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A 01JEWW8YB6A91VT8Z4PM9NCV00=%E6%B3%A8%E6%84%8F-2 faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HDBZW9XF5H24H2HCJKKHCRTE=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HDBZW9XFCDMKNWJ75AWHC2Y0=%E6%B3%A8%E6%84%8F-3 h_01KSMX2ECGNMX39RD2F6ZHQEK4=%E9%87%8D%E8%A6%81 h_01HDBZW9XFJ68WSM3066NVRATS=%E6%B3%A8%E6%84%8F-4 h_01HDBZW9XFWKN7W90PSVMX73FS=%E6%B3%A8%E6%84%8F-5 h_01HDNZ708FN0N286R5HDQGMNGZ=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
