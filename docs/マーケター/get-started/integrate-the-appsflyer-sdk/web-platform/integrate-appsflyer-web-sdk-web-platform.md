---
title: AppsFlyer Web SDKの実装
deprecated: false
hidden: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-15T09:07:44Z'
  edited_at: '2026-10-28T09:12:33Z'
  id: 50896216552337
  locale: ja
  section: Web platform
  section_id: 50896333547281
  url: https://support.appsflyer.com/hc/ja/articles/50896216552337
---
**概要：** WebサイトにAppsFlyer Web SDK（ピクセルとも呼ばれます）を実装すると、ユーザーの訪問やイベントをAppsFlyerに送信できます。また、継続して使用するカスタマーユーザーID（CUID）を設定することで、複数のプラットフォームにまたがるユーザーの行動を紐づけられます。

<div id="overview" />

## 概要

Web SDKは、訪問者によるWebサイト上の操作を記録し、その情報をAppsFlyerに送信します。 Webサイト上のユーザーの訪問や操作をAppsFlyerに送信する、サイズが40～60 KBのプラグインモジュールです。

<div id="integrate-the-sdk-manually" />

### SDKの手動実装

 以下の手順に沿って、Web SDKの実装、動作確認、プライバシー設定を行ってください。

1. [キーの取得](#1-キーの取得) Web SDK ID（Web Dev Keyとも呼ばれます）を取得します。
2. [コードスニペットの選択](#2-コードスニペットの選択)実装方式とセキュリティ要件に合ったコードスニペットを選択します。
3. [Web SDKの設置](#3-コードスニペットの設置) Webサイトに直接コードスニペットを追加するか、GoogleタグマネージャーまたはAdobe Launch Tag Managerを使用してSDKを設置します。
4. [SDKの動作確認](#4-sdkの動作確認)ブラウザの開発者ツールでネットワーク通信を確認し、SDKがリクエストを送信していることを検証します。
5. [イベントの設定と記録](#5-イベントの設定と記録) JavaScriptで直接実装するか、Googleタグマネージャーを使用して、ページの読み込み時やユーザーの操作時に送信するカスタムイベントを定義します。
6. [カスタマーユーザーIDの設定](#6-カスタマーユーザーidの設定)継続して使用するCUIDを設定し、Web上の行動を他のプラットフォームでの行動と紐づけます。
7. [プライバシーの管理](#7-プライバシーの管理)計測の有効・無効を制御し、セキュリティとデータの除外設定（コンテンツセキュリティポリシーとクエリパラメータの除外）を行います。
8. [Web SDKのCookie一覧](#web-sdkのcookie一覧) Web SDKが設定または使用するCookieの目的、有効期間、適用範囲を確認します。

<div id="integrate-the-sdk-with-an-ai-coding-agent" />

#### AIコーディングエージェントを使用したSDKの実装

Web SDKを手動で実装する代わりに（手順は以下を参照）、AIコーディングツール（Cursor、Claude Code、Codex、Copilot）に実装全体を任せることもできます。プロンプトをコピーし、2つのプレースホルダーを置き換えて、AIコーディングツールに貼り付けてください。

この方法では、以下のすべての手順をまとめて効率的に進められます。ただし、実装後にはSDKが正しく動作することを確認し、プライバシー設定を見直す必要があります。

プロンプトをコピーする前に、次の値を置き換えてください。

* `<WEB_SDK_ID>`：AppsFlyerで**アプリ設定**を開き、Webアプリ（Webサイトのドメインに「website-」という接頭辞が付いたもの）を選択し、**Web SDK ID**を**SDK認証**からコピーしてください。
* `<PRODUCTION_URL>`：本番のWebサイトのURLです。本番環境への反映後の動作確認に使用します。

> 📘 **Note**
>
> AIツールは、コードベースからイベントの実装計画を作成し、承認を得てから実装に進みます。計画を確認し、収益と通貨の値が実際に確定した収益を伴うイベントにのみ設定されていることを確認してください。その後、プロンプト内の本番環境への反映後の検証手順に沿って、実装結果を検証してください。

<Accordion title="AI実装用プロンプト">

```markdown
# **AppsFlyer Web SDK：AI実装用プロンプト**

以下のプロンプトを、プロジェクトを編集できるAIコーディングツール（Cursor、Claude Code、Codex、Copilot）にコピーしてください。コピーする前に、2つのプレースホルダーを置き換えてください。

  - <WEB_SDK_ID>：AppsFlyerでマイアプリを開き、Webアプリ（ドメインにwebsite-という接頭辞が付いたもの）を選択し、SDK認証からWeb SDK ID（Web Dev Keyとも呼ばれます）をコピーしてください。
  - <PRODUCTION_URL>：本番のWebサイトのURLです。本番環境への反映後の動作確認に使用します。

このWebサイトにAppsFlyer Web SDK（Webアトリビューション用ピクセル）を実装してください。マーケティングの成果計測に必要なイベントも実装対象に含めてください。

Web SDK ID：<WEB_SDK_ID>

本番環境のURL：<PRODUCTION_URL>

## ステップ0：設定値の確認

上記のWeb SDK IDが未入力、またはプレースホルダーのままの場合は、IDの提供を求める短いメッセージだけを返し、作業を停止してください（AppsFlyerでの確認場所：マイアプリ > 「website-」で始まるアプリ > SDK認証 > Web SDK ID）。 IDが提供されるまで、コードは一切記述しないでください。本番環境のURLが未入力の場合は、同じメッセージで提供を求めてください。本番環境への反映後の動作確認に必要です。

変更は最小限にしてください。リポジトリからファイルの場所を判断し、この実装に必要な箇所だけを変更して、プロジェクトの既存の実装方針を維持してください。

## ステップ1：最初にサイトを分析

コードを記述する前に、コードベースを確認し、イベントの実装計画を自分で作成してください。私にイベントの一覧を求めないでください。

1. 使用しているフレームワーク（通常のHTML、React、Next.js、Vueなど）と、ドキュメントの<head>を管理している箇所を特定してください。

2. コードから、コンバージョンにあたる操作を特定してください。信頼性の高い順に、次の箇所を確認してください。

   - 既存の分析ツールの呼び出し：gtag()/GA4イベント、Segmentのanalytics.track()、fbq('track')、dataLayer.push（EC関連のオブジェクトを含む）。これらから、操作の内容と、金額・通貨・注文IDの値がどこに格納されているかを把握できます。

   - EC関連の処理：購入手続きやカートのモジュール、注文確認ページや完了ページとそのルート、決済成功時のコールバック。

   - 認証関連の処理：会員登録やログインのフロー、およびクライアント側のコードで内部ユーザーIDを取得できるようになる箇所。

   - フォームと行動を促すボタンなど：見込み顧客の情報を取得するフォーム、サブスクリプションやトライアルの開始、ダウンロード。

   - EC以外のサービスやツール：購入、カート、購入手続き、会員登録、ログインのフローがない場合は、EC関連や認証関連のイベントを勝手に作らないでください。代わりに、生成、コピー、出力、ダウンロード、共有、テンプレート選択、パラメータ編集など、実際に製品で行われる操作を特定し、内容が分かるカスタムイベント名を割り当ててください。

3. 特定した各操作を、AppsFlyerの標準イベント名に対応付けてください。

   - 注文完了 / "Order Completed" / purchase_success -> af_purchase（eventRevenueを設定）

   - 会員登録 / 登録 / アカウント作成 -> af_complete_registration

   - ログイン / サインイン -> af_login

   - カートへの追加 / "Product Added" -> af_add_to_cart（af_priceを設定し、eventRevenueは設定しない）

   - 購入手続きの開始 / "Checkout Started" -> af_initiated_checkout（af_priceを設定し、eventRevenueは設定しない）

   - 商品またはコンテンツの閲覧 -> af_content_view

   - サブスクリプションの開始 -> af_subscribe、無料トライアルの開始 -> af_start_trial

   - 検索 -> af_search

   対応する標準イベントがない場合は、内容が分かるカスタム名を維持してください。

4. 各イベントについて、実際に請求された金額（af_purchaseの場合）、通貨、注文IDまたは取引ID、ユーザーIDの正確な取得元をコード内で特定してください。既存の分析ツールが参照しているデータの取得元を、そのまま使用してください。

5. OneTrustやDidomiなどの同意管理プラットフォーム（CMP）がすでに導入されているか確認してください。サイト独自の同意切り替え機能や、サイトに保存されているプライバシー設定も確認してください。それらに応じて計測をどう制御するかは、自分で決めず、私に確認してください。

注意：既存の分析ツールは、イベントを特定するための参考情報としてのみ使用してください。AppsFlyerのイベントはAF()を直接呼び出して実装し、SegmentやGA4を経由して、それらのイベント名のまま転送しないでください。

その後、イベントの実装計画を表で提示してください（AppsFlyerのイベント名、発生条件とファイル、収益またはaf_priceの取得元、重複排除用IDの取得元）。実装に進む前に、私の承認を待ってください。値の取得元が見つからないイベントは、推測で補わず、その旨を明示してください。

## ステップ2：SDKのコードスニペットを設置

Web SDK IDを設定し、すべてのページの<head>内の先頭に近い位置に、このコードスニペットを追加してください。

<script>

!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){

(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},

t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,

o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),

p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "<WEB_SDK_ID>"}})

</script>

必ず守るルール：

- コードスニペットは、書き換えずにそのまま使用してください。独自のコンポーネントやラッパーモジュールに書き換えないでください。 SDKをラッパーで包むと、カスタムイベントは送信できても、訪問を自動記録するSDKのLOADイベントが発生しない場合があります。その場合、サイトの訪問数は0となり、アトリビューションも行われません。

- SDKは、ページを読み込むたびに必ず1回だけ読み込んでください。 ReactやNext.jsでは、再レンダリングや二重マウントを防いでください。例えば、再マウントされるコンポーネント内ではなく、ルートのHTMLやドキュメントテンプレートで読み込んでください。複数回読み込むと、SDKが動作しなくなる場合があります。

- タグマネージャー（GTM）ですでにAppsFlyer SDKを読み込んでいる場合は、コードにも追加しないでください。読み込み処理は1つにしてください。既存のAppsFlyerタグが見つかった場合は、私に報告してください。

- ページビューや訪問のイベントを手動で実装しないでください。 SDKは読み込み時に訪問を自動で記録します。独自に実装した"page_view"イベントは、訪問としてはカウントされません。

- 設定キーはwebAppIdです。appIdではありません。

- サイトがnonceを使用する厳格なコンテンツセキュリティポリシーを適用している場合は、インラインのコードスニペットのタグにnonceを追加し、ポリシーに'strict-dynamic'が含まれていることも確認してください。コードスニペットはSDKのスクリプトを動的に挿入するため、'strict-dynamic'がない場合、nonceのみのポリシーでは読み込みがブロックされます。

## ステップ3：イベントを実装

イベントの呼び出し形式：

AF('pba', 'event', {

  eventType: 'EVENT',            // always the literal string 'EVENT'

  eventName: 'af_purchase',

  eventRevenue: 49.99,           // top level - only on realized revenue

  eventRevenueCurrency: 'USD',   // top level - 3-letter ISO code, defaults to USD if omitted

  eventValue: {                  // JSON metadata, max 1000 characters

    "af_order_id": "TXN-12345",

    "af_customer_event_id": "evt-abc-001"

  }

});

イベントのルール：以下を厳守してください。

1. プラットフォーム間でレポートやファネルを揃えるため、AppsFlyerの標準イベント名を使用してください：af_purchase、af_complete_registration、af_login、af_add_to_cart、af_initiated_checkout、af_content_view、af_subscribe。モバイルアプリがある場合は、モバイルSDKと同じイベント名を使用してください。 "_web"など、プラットフォームを示す接尾辞は追加しないでください。

   例外：購入するプランやカテゴリが明確に分かれており、ダッシュボードで個別に集計する必要がある場合（例えば、2種類のサブスクリプション商品）は、汎用的なイベント名1つにまとめず、実装計画で個別のイベント名（af_purchase_<tier>）を提案し、その理由を説明してください。 eventValueだけで分類しても、標準のダッシュボード表示には反映されません。同じ購入に対して、プラン別のイベントと汎用のイベントの両方を送信しないでください。データが重複します。

2. 収益は、最上位のeventRevenueフィールドにのみ設定してください。また、実際に金銭の授受が発生したイベント（購入完了、サブスクリプションの契約完了、予約確定）にのみ設定してください。 eventValue内の値（af_revenue、revenue、price、amount、total）は、収益としてはカウントされません。ここに収益を設定することは、最も多い実装ミスであり、すべての購入の収益が0ドルとなります。

3. 通貨がUSD以外の場合は、eventRevenueとともに必ずeventRevenueCurrencyを送信してください。送信しないと、すべての金額がUSDとして記録されます。

4. 1回の取引で実際に発生した金額を、数値だけで送信してください。通貨記号を付ける、セント単位で送る、カートの合計金額と各商品の金額を重複して計上する、LTVを送る、といった処理は行わないでください。

5. 実際に確定した収益ではない金額（カートへの追加時の金額、購入手続き開始時の金額、閲覧した商品の価格）には、eventRevenueを設定しないでください。 eventValue内の"af_price"に金額を、"af_currency"に通貨を設定してください。 af_initiated_checkoutとaf_purchaseの両方でeventRevenueを送信すると、収益が二重に計上されます。

6. 購入時には、eventValue内に"af_order_id"（取引ID）を含めてください。その時点でコードベースに実際の取引IDがない場合は、プレースホルダーで代用せず、実装計画でその旨を説明してください。

7. すべてのコンバージョンイベントのeventValue内に、一意の"af_customer_event_id"を含めてください。同じイベント名で、同じIDを使ったイベントを2回発生させないでください。操作ごとにIDを生成し、SPAの再レンダリングによってハンドラーが2回呼び出されることを防いでください。これにより、同じコンバージョンをサーバー間（S2S）でも送信している場合の重複も排除できます。

8. ユーザーの1回の操作につき、イベントは1つにしてください。同じ操作に対して2つの名前でイベントを送信しないでください。また、同じ操作をAppsFlyerと転送用の仕組みの両方を通じて、異なる名前で送信しないでください。

9. 複数の商品が入ったカートでは、eventValue内に"af_order_info"配列を追加してください。商品ごとに1つのオブジェクトを作成し、sku、revenue（単価）、qty、content_name、content_type、content_category、brandをキーとして含めてください。購入時には、この場合も最上位のeventRevenueに注文の合計金額を設定してください。

10. イベントは、ページにSDKのコードスニペットが読み込まれてから発生させてください。確認ページや完了ページで終了するコンバージョンでは、そのページの読み込み時にイベントを発生させてください。ページ内の操作（SPAでのボタンクリックなど）では、操作のハンドラーから発生させてください。

11. 送信データには必要なフィールドだけを含めてください。

    - イベントで実際に金銭の授受が発生していない場合は、eventRevenueとeventRevenueCurrencyを含めないでください。「念のため」といった理由でeventRevenue: 0やデフォルトの通貨を送信しないでください。

    - eventCategory、eventLabel、その他のGAやSegmentで使用する形式のフィールドを含めないでください。これらはAppsFlyer Web SDKのイベントAPIには含まれません。

    - eventValue内では、値が空文字列、null、undefined、falseのキーは省略してください。ただし、そのプロパティでfalseという値自体に意味がある場合は除きます。

    - そのイベントに関係のないパラメータは、送信データに含めないでください。必要なフィールドだけを持つ、最小限のオブジェクトにしてください。

    - AppsFlyerのレポートで収益や通貨の列が空欄でも、クライアント側で0やデフォルト値を送信する必要はありません。そのフィールドは設定せずに送信してください。

## ステップ4：カスタマーユーザーID（CUID）を設定

ユーザーのログインや会員登録の直後、および認証済みのユーザーがページを読み込んだ際に、次のメソッドを呼び出してください。

AF('pba', 'setCustomerUserId', '<the user's internal ID, as a string>');

ルール：

- モバイルアプリがある場合は、モバイルアプリでsetCustomerUserIdに渡しているものと同じ識別子を使用してください。これにより、同じユーザーのWebとモバイルでの一連の行動を紐づけられます。

- 値そのものから個人の情報を読み取れない内部IDを使用してください。メールアドレス、電話番号、その他の個人を特定できる情報（PII）は使用しないでください。

- できるだけ早く呼び出してください。それより前に発生したイベントには、CUIDが含まれません。

- setCustomerUserIdを呼び出すだけでは、レポートに表示されるイベントは作成されません。会員登録時にはaf_complete_registration、ログイン時にはaf_loginも発生させてください。CUIDを設定した後に発生させることで、これらのイベントにCUIDが含まれます。

## ステップ5：同意に応じた制御（CMPがある場合のみ）

サイトに同意管理プラットフォームがある場合：

- 計測を無効にした状態でSDKを初期化： {pba: {webAppId: "<WEB_SDK_ID>", measurementStatus: false}}

- 同意が得られたとき： window.AF_SDK.PLUGINS.PBA.enableMeasurement()

- 同意が撤回されたとき： window.AF_SDK.PLUGINS.PBA.disableMeasurement()

注意：

- これらのプラグインメソッドは、SDKのスクリプトの読み込みが完了するまで使用できません。呼び出しをキューに格納する仮の関数としてすぐに使用できるAF()とは異なります。この読み込み順序を考慮して実装してください。

- 初期状態で計測を無効にした場合、同意が得られるまで訪問は記録されません。実装する前に、この点を明確に説明してください。

CMPがない場合は、通常のコードスニペットを使用してください。計測はデフォルトで有効です。

## ステップ6：検証

### 6a. ローカル環境での検証（実装中）

プロジェクトを実行し、ブラウザを操作してください（PlaywrightやPuppeteer、または利用できるブラウザツールを使用）。AppsFlyerのドメインへのすべてのリクエストについて、送信データとHTTPレスポンスのステータスの両方を記録してください。次の項目を検証してください。

- SDKの読み込みリクエストが200を返し、ページの読み込みごとに1回だけ発生すること。ページ間の遷移やコンポーネントの再レンダリングを行い、二重に読み込まれないことを確認してください。

- ページの読み込み時に、eventTypeが"LOAD"で、afWebUserIdに値が設定されたリクエストが発生し、レスポンスが2xxであること。これが訪問の記録です。このリクエストがないと、アトリビューションは行われません。

- 実装した各コンバージョンで、イベントのリクエストが1回だけ発生し、2xxが返されること。購入時にはeventRevenueとeventRevenueCurrencyが最上位にあり、af_customer_event_idが設定され、その値が一意であること。

- ログインを模擬的に行った後、その後のリクエストにカスタマーユーザーIDが含まれること。

リクエストを記録できただけでは、成功した証拠にはなりません。レスポンスが4xxのイベントは拒否されており、レポートには表示されません。発生させたすべてのイベントのステータスコードを報告し、ステータスコードを確認していないイベントを検証済みと記載しないでください。

ブラウザを実行できない場合は、コードを確認して静的に検証してください。コードスニペットの挿入箇所が1つだけで二重にマウントされないこと、各イベントハンドラーが1回の操作につき1回だけ実行されること、収益と通貨が最上位のフィールドにあること、認証済みのユーザーが利用を開始するすべての経路でsetCustomerUserIdが呼び出されることを確認してください。レスポンスのステータスを確認できていないことを、明確に記載してください。

### 6b. 本番ドメインでの反映後の検証（必須）

ローカル環境での実行で確認できるのは、コードの処理経路です。本番ページの動作は確認できません。ビルドパイプラインやアセットの処理によって、インラインスクリプトが削除されたり、実行が遅延されたり、配置場所が変更されたりする場合があります。ソースファイルの確認だけでは不十分です。本番環境への反映後：

- 本番環境のURLにアクセスしてHTMLを取得し、実際に配信されるHTMLにコードスニペットが含まれていることを確認してください。

- ブラウザで本番ページを開き、6aのすべての検証項目を本番ページでも確認してください。

- 送信されるリクエストのaf_idクエリパラメータが、Web SDK IDと完全に一致していることを確認してください。IDが間違っている、または途中で切れている場合は、私のアカウントに存在しないIDでイベントが送信され、エラーの通知もなく記録されません。

- QA専用のカスタマーユーザーID（例：qa_<yyyymmdd>_01）を使用し、後からローデータで検証時のデータを特定できるようにしてください。

まだ本番環境に反映していない場合は、6bが未完了であると伝え、反映後に実行する具体的なコマンドと検証項目を提示してください。

### 6c. QAの記録

後からAppsFlyerのローデータと照合できるように、検証結果を表で作成してください。イベントごとに1行とし、UTCのタイムスタンプ、イベント名、CUID、af_order_id、af_customer_event_id、HTTPステータスを含めてください。検証全体の開始日時と終了日時をUTCで記載してください。本番環境への反映日時が分かる場合は、それもUTCで記載してください。

## ステップ7：取得したデータの確認

訪問とコンバージョンは異なる種類のレコードであり、混同しやすいため、AppsFlyerでイベントを確認する具体的な手順を報告に含めてください。

- 訪問は自動で記録され、イベント単位のデータでは、イベント名が空欄で収益が0のSESSION行として表示されます。これはデータ形式上の仕様であり、不具合ではありません。初回訪問と再訪問は、名前付きのイベントではなく、コンバージョン単位のデータ（FIRST_VISIT / REVISIT）に表示されます。実装が正しくても、セッションを対象とした出力データにアプリ内イベントが含まれることはありません。

- 実装したコンバージョンは、イベント名（af_purchase、af_loginなど）が入力された別の行として表示されます。収益が含まれるのは購入の行のみです。

- 本番環境への反映前の期間のデータには、新しいイベントは含まれません。本番環境への反映日時をUTCで提示し、その日時以降のデータだけを取得するよう私に案内してください。アトリビューションの日時を示すフィールドは、イベントの日時よりかなり前の値である場合があり、今回の検証ではなく過去の訪問を指すことを説明してください。

- レポートに反映されるまでの想定時間を示し、その時間内にレポートが空でも、失敗と判断しないよう案内してください。

- 6cの検証時のデータを特定するための具体的なフィルタ（期間とQA用CUID）と、正常な場合にどのような結果が表示されるかを説明してください。

- イベントに2xxが返されていても、想定される反映時間を過ぎても表示されない場合は、コードの不具合ではなく、アカウント側の問題（Webアプリでイベントが有効になっていない、レポートの対象範囲、データへのアクセス権など）であると明確に説明し、AppsFlyerの管理画面で確認すべき項目を示してください。

## 最終報告

作業が完了したら、以下を提示してください。

- 実装したすべてのイベントの表：イベント名、発生箇所（ファイル）、収益の扱い、重複排除用ID。

- コードスニペットを設置した場所と、1回だけ読み込まれることを保証する方法。

- setCustomerUserIdを呼び出す場所。

- 6cのQA記録表。また、自分で検証した内容（レスポンスのステータスを含む）と、私が手動で確認する必要のあるQA項目（開くページ、実行する操作、想定されるリクエストとステータス）を明確に分けて提示してください。

- ステップ7のデータ確認手順。

- 実装できなかったことや、私からの情報提供が必要なこと。例えば、ユーザーIDの保存場所、実際の請求総額に対応する購入金額のフィールド、推測で補わなかった値の取得元など。

ここに記載したAppsFlyer Web SDKの実装範囲を超える作業は行わないでください。
```

</Accordion>

<div id="1-obtain-your-keys" />

## 1. キーの取得

**Web SDK ID（Web Dev Keyとも呼ばれます）を取得します。**

1. AppsFlyerの上部メニューから、**アプリ設定**を開きます。
2. ページ上部のアプリ選択欄で、Webアプリ（Webサイトのドメインに「website-」という接頭辞が付いたもの）を選択します。
3. **SDK認証**で、**Web SDK ID**をコピーします。

**必要に応じて、Smart Banner Keyを取得します。**

1. AppsFlyerのサイドメニューから、**Engage** > **Web to App** > **Smart Banners**を開きます。
2. 使用するSmart Banner Keyをコピーします。

<div id="2-select-a-code-snippet" />

## 2. コードスニペットの選択

実装方式とセキュリティ要件に合ったコードスニペットを選択します。次の2つの方式があります。

* [標準Web SDK](#標準web-sdk)：標準の実装方式です。
* [Advanced SDK Verification](#advanced-sdk-verification)：Web SDKの配信経路での改ざん対策を追加した実装方式です。 CDNの侵害、DNSの乗っ取り、中間者攻撃に対する保護を強化できます。

> ❗️ **Warning**
>
> 標準Web SDKからAdvanced SDK Verificationに移行する場合は、既存のコードスニペットを新しいものに置き換えてください。既存のコードスニペットを残したまま、新しいものを追加しないでください。

<div id="standard-web-sdk" />

### 標準Web SDK

標準Web SDKの実装には、このコードスニペットを使用します。 SDKを読み込むすべてのページで、`<head>`タグ内の先頭に近い位置に貼り付けてください。

<Accordion title="Smart Bannersを使用しない場合">

```javascript
<0>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  // Replace WEB_DEV_KEY with your Web SDK ID
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
0>
```

</Accordion>

<Accordion title="Smart Bannersを使用する場合">

```javascript
<0>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  // Replace WEB_DEV_KEY with your Web SDK ID
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba,banners&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
  AF('banners', 'showBanner');
0>
```

</Accordion>

### Advanced SDK Verification

Advanced SDK Verification（SDKコードの改ざん検証機能）は、Web SDKの配信経路での改ざん対策を追加します。ユーザーのブラウザで実行されるコードが、AppsFlyerが公開したコードと完全に一致することを確認します。 SDKのソースコード自体は標準の実装方式と同じです。異なるのは、配信と検証の仕組みだけです。

Advanced SDK Verificationには、次の特徴があります。

* CDNの侵害、DNSの乗っ取り、中間者攻撃に対する保護を強化します。
* SDKの読み込み時間が約250ミリ秒長くなります。

Advanced SDK Verificationの使用は任意です。標準の実装方式も引き続き全面的にサポートされており、外部の分析用ピクセルで一般的に採用されている方式です。 Advanced SDK Verificationは、その標準方式に加えて、さらに保護を強化するものです。

Webサイトでnonceを使用するコンテンツセキュリティポリシー（CSP）を適用している場合は、「プライバシーの管理」の[コンテンツセキュリティポリシー（CSP）](#コンテンツセキュリティポリシーcsp)を参照し、このコードスニペットのnonce対応版を使用してください。

<Accordion title="Smart Bannersを使用しない場合">

```javascript
<0>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
0>
```

</Accordion>

<Accordion title="Smart Bannersを使用する場合">

```javascript
<0>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
0>
```

</Accordion>

<div id="3-deploy-the-snippet" />

## 3. コードスニペットの設置

ステップ2で選択したコードスニペットを、次のいずれかの方法で設置します。 SDKがページの読み込みごとに1回だけ読み込まれるようにしてください。

<Accordion title="方法A：Webサイトに直接追加">

すべてのページで、次の操作を行います。

1. ステップ2のコードスニペットで、`WEB_DEV_KEY`をWeb SDK IDに置き換えます。Smart Bannersを使用する場合は、`YOUR_BANNER_KEY`も置き換えます。
2. Webサイトの`<head>`タグ内の先頭に近い位置に、コードスニペットを貼り付けます。

</Accordion>

<Accordion title="方法B：Googleタグマネージャー（GTM）を使用して設置">

SDKがページの読み込みごとに1回だけ読み込まれるようにしてください。また、GTMの優先順位設定を使用し、ページの読み込み後すぐにSDKが読み込まれるように設定してください。

1. Googleタグマネージャーを開きます。
2. AppsFlyer Web SDK用の新しいタグを作成します。
3. タグの種類として<strong>Custom HTML（カスタムHTML）</strong>を選択します。
4. 用途が分かるタグ名を付けます。
5. <strong>Tag Configuration（タグの設定）</strong>に、ステップ2のコードスニペットを貼り付けます。
6. <strong>Save（保存）</strong>をクリックします。
7. トリガーを追加します。
   * すべてのページを対象にする場合：
     1. <strong>Add Trigger（トリガーを追加）</strong>をクリックします。
     2. <strong>All Pages（すべてのページ）</strong>を選択します。
     3. <strong>Save（保存）</strong>をクリックします。
     4. タグ名を入力し、<strong>Save（保存）</strong>をクリックします。
   * 特定のページを対象にする場合：
     1. <strong>Save Tag（タグを保存）</strong>をクリックします。
     2. GTMのメイン画面で、<strong>Triggers（トリガー）</strong>を選択します。 <strong>New（新規）</strong>をクリックします。
     3. 鉛筆アイコンをクリックします。
     4. トリガーの種類として<strong>Page View（ページビュー）</strong>を選択します。
     5. <strong>Some Page Views（一部のページビュー）</strong>を選択します。
     6. 対象のページとトリガーの条件を設定します。
     7. <strong>Save（保存）</strong>をクリックします。
     8. トリガーをAppsFlyer Web SDKのタグに関連付けます。
        1. <span class="af-ol-a"></span> **GTM**のメイン画面で、<strong>Tags（タグ）</strong>を選択します。
        2. 先ほど作成したタグを選択します。
        3. トリガーの設定パネルで、鉛筆アイコンをクリックします。
        4. 先ほど作成したページビューのトリガーを選択します。
        5. <strong>Save（保存）</strong>をクリックします。

> 📘 **Note**
>
> GTMのカスタムテンプレートは、Advanced SDK Verificationに対応していません。カスタムテンプレートのサンドボックス環境では、検証に必要なintegrity属性を設定できないためです。代わりに、タグの種類として<strong>Custom HTML（カスタムHTML）</strong>を使用してください。

</Accordion>

<Accordion title="方法C：Adobe Launch Tag Managerを使用して設置">

<div id="create-a-property-in-adobe-experience-cloud" />

#### Adobe Experience Cloudでプロパティを作成

1. Adobe Experience Cloud > Launchを開きます。
2. Adobe Experience Cloud Launchで、<strong>Go to Launch（Launchを開く）</strong>をクリックします。
3. <strong>New Property（新しいプロパティ）</strong>をクリックします。
4. プロパティ名を入力します。
5. <strong>Platform（プラットフォーム）</strong>で、**Web**を選択します。
6. Webサイトのドメインを入力します。
7. <strong>Save（保存）</strong>をクリックします。

<div id="add-the-snippet-to-the-adobe-launch-property" />

#### Adobe Launchのプロパティにコードスニペットを追加

1. <strong>My web property（Webプロパティ）</strong>ページで、<strong>Rules（ルール）</strong>タブを選択します。
2. ルール名を入力します。推奨する名前は「Load web SDK」です。
3. <strong>IF（条件）</strong>セクションの<strong>Events（イベント）</strong>で、<strong>Add（追加）</strong>をクリックします。
   * <strong>Event Type（イベントの種類）</strong>で、<strong>Core – DOM Ready（Core：DOMの準備完了）</strong>を選択します。
   * <strong>Keep Changes（変更を保持）</strong>をクリックします。
4. <strong>THEN（実行内容）</strong>セクションの<strong>Actions（アクション）</strong>で、<strong>Add（追加）</strong>をクリックします。
   * <strong>Action Type（アクションの種類）</strong>で、<strong>Custom Code（カスタムコード）</strong>を選択します。
   * **JavaScript** > <strong>Open Editor（エディタを開く）</strong>を選択し、ステップ2のコードスニペットを貼り付けます。コードを囲むラッパーの行は含めないでください。
   * <strong>Keep Changes（変更を保持）</strong>をクリックして、コードエディタを閉じます。
5. <strong>Save（保存）</strong>をクリックします。

<div id="add-the-adobe-launch-tag-to-the-website" />

#### WebサイトにAdobe Launchのタグを追加

1. <strong>My web property（Webプロパティ）</strong>ページで、<strong>Environments（環境）</strong>タブを選択します。
2. 公開する環境（開発環境または本番環境）の行を探します。
3. 該当する行の<strong>Install（インストール）</strong>列で、ボックスアイコンをクリックします。
4. <strong>Web Install Instructions（Webへの設置手順）</strong>ダイアログで、スクリプトのコードスニペットをコピーし、ダイアログを閉じます。
5. Webサイトのheadセクションに、コードスニペットを貼り付けます。

<div id="publish-the-adobe-launch-environment" />

#### Adobe Launchの環境を公開

1. <strong>My web property（Webプロパティ）</strong>ページで、<strong>Publishing（公開）</strong>タブを開きます。
2. <strong>Development（開発）</strong>セクションで、<strong>Add New Library（新しいライブラリを追加）</strong>をクリックします。
   * ライブラリ名を入力し、環境を選択します。
   * <strong>RESOURCE CHANGES（リソースの変更）</strong>で、<strong>Add a Resource（リソースを追加）</strong>をクリックします。
   * **Rules（ルール）** > **Load web SDK** > **Latest（最新）** > <strong>Select & Create a New Revision（選択して新しいリビジョンを作成）</strong>をクリックします。
   * <strong>Save（保存）</strong>をクリックします。
3. <strong>Development（開発）</strong>セクションで、次の操作を行います。
   * 新しく作成したライブラリの横にあるアクションメニュー（3点アイコン）をクリックし、<strong>Build for Development（開発環境用にビルド）</strong>を選択します。
   * 再度アクションメニューをクリックし、<strong>Submit for Approval（承認を申請）</strong>を選択します。
4. <strong>Submitted（申請済み）</strong>セクションで、次の操作を行います。
   * アクションメニューをクリックし、<strong>Build for Staging（ステージング環境用にビルド）</strong>を選択します。
   * 再度アクションメニューをクリックし、<strong>Approve for Publishing（公開を承認）</strong>を選択します。
5. <strong>Approved（承認済み）</strong>セクションで、次の操作を行います。
   * アクションメニューをクリックし、<strong>Build & Publish to Production（ビルドして本番環境に公開）</strong>を選択します。

</Accordion>

<div id="4-make-sure-the-sdk-is-working" />

## 4. SDKの動作確認

実装後、ブラウザの開発者ツールでネットワークリクエストを確認し、SDKがリクエストを送信していることを検証します。

[<Image alt="開発者ツールの画面" src="https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png" width="1015px" />](https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png)

**SDKの動作を確認するには、次の手順を実行します。**

1. Webサイトを開きます。
2. ブラウザの開発者ツールを開きます。
3. （A）<strong>Network（ネットワーク）</strong>タブを開きます。
4. ページを再読み込みします。
5. （B）`appsflyer`で絞り込みます。次の2つのリクエストが表示される場合があります。
   * **SDKの読み込み**：リクエストURLが`https://websdk.appsflyersdk.com`で始まります。これにより、SDKのスクリプトが正しく読み込まれたことを確認できます。
   * **イベントデータ**：リクエストURLが`https://wa.appsflyer.com/events`で始まります。これにより、SDKがAppsFlyerにイベントデータを送信していることを確認できます。
6. （C）**events**の通信（`wa.appsflyer.com`へのリクエスト）を選択します。
7. Headers（ヘッダー）で、（D）次の項目を確認します。
   * リクエストURLが`https://wa.appsflyer.com/events?site-id=`で始まっていること。
   * `site_id`クエリパラメータが`WEB_DEV_KEY`と等しいこと。
   * ステータスコードが200であること。
8. `site_id`が`WEB_DEV_KEY`と一致することを確認します。キーは、AppsFlyerの上部メニュー > **マイアプリ**で確認できます。
9. SDKが1回だけ読み込まれることを確認します。 SDKを複数回読み込むと、動作しなくなる場合があります。

> 📘 **Note**
>
> Web SDKの実装とイベントの正常な発生をリアルタイムで視覚的に確認するには、Web SDK Testページを使用してください。

<div id="5-set-and-record-events" />

## 5. イベントの設定と記録

Web SDKを初期化すると、基本的な訪問の計測に加えて、ユーザーの具体的な操作を記録できます。このセクションでは、**JavaScriptで直接実装する方法**、または**Googleタグマネージャー**を使用して、購入や会員登録などのカスタムイベントを定義し、記録する方法を説明します。

<Accordion title="イベントの設定">

イベントはWeb計測の基本となるもので、ビジネス上の価値を持つユーザーの具体的な操作を表します。これらの操作を記録するには、イベントごとの処理とパラメータを定義し、収益やカスタムメタデータなどの適切なイベントパラメータをAppsFlyerに送信する必要があります。

**イベントの例（収益を伴う購入イベント）**

```javascript
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name", "af_customer_event_id": "evt-abc-001"}});
```

<div id="web-sdk-event-parameters-table" />

<Accordion title="Web SDKのイベントパラメータ一覧">

| パラメータ名 | 必須 | 説明 |
| --- | --- | --- |
| `eventType` | はい | イベントの種類です。形式：文字列。このパラメータには、必ず`EVENT`を設定してください。例：`eventType: "EVENT"` |
| `eventName` | はい | イベント名です。形式：文字列。例：Purchase、Subscription |
| `eventRevenue` | いいえ | コンバージョンイベントに紐づける収益です。形式：浮動小数点数。 |
| `eventRevenueCurrency` | いいえ | 収益の通貨です。 ISO 4217に準拠した3文字の通貨コードです。デフォルト：USD。形式：文字列。 |
| `eventValue` | いいえ | イベントの内容を示すパラメータを、キーと値の組み合わせで格納したマップです。このパラメータを使用すると、商品のSKUや商品ごとの価格など、詳細情報を含むアプリ内イベントを送信できます。形式：JSON。例：`{"sku": "ABC123", "color": "blue", "unit_price": 3.99, "currency": "USD"}` 上限：3,000文字（超過した部分は切り捨てられます）。 |

</Accordion>

</Accordion>

<Accordion title="ページの読み込み時にイベントを記録">

これは、**完了ページ**や確認ページへのリダイレクトで終了するコンバージョンを記録する、標準的な方法です。

**JavaScriptで直接実装する場合**はウィンドウの読み込み時に実行する処理を追加し、**Googleタグマネージャー**を使用する場合はページビューのトリガーを設定することで実装できます。

> 🚧 **Important**
>
> 以下のコードは、説明用の例です。**このコードをそのまま使用せず**、Webサイトの構造に合わせて調整してください。

<div id="example-record-event-via-af-web-sdk" />

<Accordion title="例：AppsFlyer Web SDKでイベントを記録">

この方法は、メールマガジンの購読登録後に表示される完了ページなど、リダイレクトを伴うコンバージョンの記録に適しています。

**利用例：** ユーザーがメールマガジンの購読登録を完了し、確認ページにリダイレクトされます。そのページが表示された時点で、購読登録イベントを記録します。

**JavaScriptで直接実装する場合のページ読み込み時のコード例：**

```javascript
window.onload = function(){
  AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion'}, eventName: 'subscription'});
}
```

**処理の流れ：**

1. ページで必要なコンテンツが読み込まれます。
2. ウィンドウ全体の読み込みが完了すると（`window.onload`）、スクリプトが自動的に`AF()`メソッドを呼び出します。
3. **subscription**イベントが、関連するメタデータ（カテゴリとラベル）とともにAppsFlyerに直接送信されます。

</Accordion>

<div id="example-record-event-via-gtm" />

<Accordion title="例：GTMでイベントを記録">

この方法では、完了ページの読み込み時にタグを発火させることで、メールマガジンの購読登録など、完了したコンバージョンを記録します。

<div id="1-set-up-a-thank-you-page" />

#### 1. 完了ページの作成

次のHTMLではGTMが読み込まれ、GTMによってWeb SDKが読み込まれます。また、関数や`localStorage`を使用して、GTMからデータを参照できるようにする方法も示しています。

```javascript
<0>
<1>
    <2>
        // Google Tag Manager loads the Web SDK
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-XXXX');
    2>
    <2>
        function getResponseFromServer() {
            return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
        }
        localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
    2>
1>
<3>
    <4>Thank You for Subscribing to Our Newsletter4>
3>
0>
```

<div id="2-configure-the-gtm-tag" />

#### 2. GTMタグの設定

1. GTMで新しいタグを作成し、タグの種類として<strong>Custom HTML（カスタムHTML）</strong>を選択します。
2. 他のタグと区別できる名前（例：「AF Subscription Event」）を付けます。
3. HTMLのテキスト欄に、次のスクリプトを貼り付けます。

   ```javascript
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'});
   ```
4. **Advanced Settings（詳細設定）** > <strong>Tag Sequencing（タグの順序付け）</strong>を展開します。 Web SDKの初期化を行うメインのタグの後に発火するように設定します。
5. 完了ページの<strong>Page View（ページビュー）</strong>でこのタグを発火させるトリガーを設定します。

</Accordion>

</Accordion>

<Accordion title="ユーザーの操作時にイベントを記録">

ページの再読み込みを伴わない操作（ボタンクリック、ダウンロード、カートへの追加）を計測する場合に使用します。

これらの操作は通常、**HTML要素**にクリックリスナーを設定するか、**Googleタグマネージャー**の変数を使用して特定の要素IDやCSSセレクタを識別し、計測します。

> 🚧 **Important**
>
> 以下のコードは、説明用の例です。**このコードをそのまま使用せず**、Webサイトの構造に合わせて調整してください。

<div id="example-record-event-via-af-web-sdk-interaction" />

<Accordion title="例：AppsFlyer Web SDKでイベントを記録">

この方法は、<strong>Checkout（購入手続き）</strong>ボタンや<strong>Download（ダウンロード）</strong>ボタンのクリックなど、ページ上のユーザーの具体的な操作を計測するために使用します。

**利用例：** ECサイトで、**checkout**イベントを記録したいとします。ユーザーがショッピングカートの<strong>Checkout（購入手続き）</strong>ボタンをクリックした時点で記録します。

**JavaScriptで直接実装する場合のユーザー操作時のコード例：**

```javascript
<0>
<1>
    <2>
        window.onload = function () {
            document.getElementById('checkout').addEventListener('click', function () {
                AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
            });
        }
    2>
1>
<3>
    <4>Shopping Cart4>
    <5>Checkout5>
3>
0>
```

**処理の流れ：**

1. ページの読み込み時に、スクリプトが**click**イベントのリスナーをIDが`checkout`の要素に設定します。
2. ユーザーがボタンをクリックすると、コールバック関数が呼び出されます。
3. この関数は、例えば`localStorage`から関連するデータを取得し、`AF()`メソッドに渡すことができます。
4. SDKが**checkout**イベントをAppsFlyerに送信します。

</Accordion>

<div id="example-record-event-via-gtm-interaction" />

<Accordion title="例：GTMでイベントを記録">

この方法は、GTMの組み込み変数とトリガーを使用して、<strong>Checkout（購入手続き）</strong>ボタンのクリックなど、特定の操作を記録します。

<div id="1-set-up-a-checkout-page" />

#### 1. 購入手続きページの作成

```javascript
<0>
<1>
    <2>
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-XXXX');
    2>
1>
<3>
    <4>Shopping Cart4>
    <5>Checkout5>
3>
0>
```

<div id="2-configure-gtm-variables-and-triggers" />

#### 2. GTMの変数とトリガーの設定

1. <span class="af-ol-a"></span>GTMで**Variables（変数）** > <strong>Configure（設定）</strong>をクリックし、Built-In Variables（組み込み変数）の一覧で<strong>Click Element（クリック要素）</strong>を有効にします。
2. 新しいユーザー定義変数を作成します（種類：**All Elements（すべての要素）**）。
3. 新しい<strong>Trigger（トリガー）</strong>を作成します。
   * トリガーの種類：**Click - All Elements（クリック：すべての要素）**。
   * トリガーの発火条件：**Some Clicks（一部のクリック）**。
   * 条件：<strong>Click Element（クリック要素）</strong>がCSSセレクタ`#checkout`に一致すること。

<div id="3-create-the-interaction-tag" />

#### 3. ユーザー操作用のタグの作成

1. <span class="af-ol-a"></span>購入手続きの操作用に、新しい<strong>Custom HTML（カスタムHTML）</strong>タグを作成します。
2. 操作時に実行するスクリプトを貼り付けます。

   ```javascript
   <0>
     AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
   0>
   ```
3. 前の手順で作成した「Checkout Click」トリガーを割り当てます。

</Accordion>

</Accordion>

<Accordion title="イベント実装時の推奨事項">

データを正確に記録し、正常に送信するため、次の技術的な要件に注意してください。

* **読み込み順序：** イベントを呼び出す前に、Web SDKの関数を定義するタグがページ内で完全に読み込まれていることを確認してください。
* **データ形式：** イベントの値に特殊文字を含めないでください。例えば、収益には通貨記号を付けず、数値を使用してください（`10.50`を使用し、`$10.50`は使用しないでください）。
* **文字数上限：**`eventValue`の文字列は簡潔にしてください。3,000文字を超えた部分は切り捨てられます。
* **イベントの重複排除：**`af_customer_event_id`を`eventValue`内で送信し、イベントごとに一意の値を設定することを推奨します。これは、Web SDKとサーバー間（S2S）APIの両方で同じイベントを送信する場合に、特に重要です。 AppsFlyerはこの値をアドネットワークに転送します。アドネットワークは、この値を使用して、AppsFlyerから受信したサーバー側のイベントと、自社のピクセルから受信した同じイベントの重複を排除します。
* **収益の設定先：**`eventRevenue`は、購入やサブスクリプションの契約確定など、実際に金銭の授受が発生したイベントにのみ設定してください。金額を伴っていても、実際に確定した収益ではないイベント（カートへの追加、購入手続きの開始、コンテンツの閲覧など）には、代わりにeventValue内のaf\_priceとaf\_currencyを使用してください。購入手続きと購入の両方で`eventRevenue`を送信すると、すべてのレポートで収益が二重に計上されます。
* **イベント名：** イベント名に`_web`などのプラットフォームを示す接尾辞を追加しないでください。プラットフォームは、ダッシュボードとローデータですでに分析軸として用意されています。プラットフォーム間でレポートを統一するため、モバイルアプリと同じイベント名を使用してください。

</Accordion>

<div id="6-set-customer-user-id" />

## 6. カスタマーユーザーIDの設定

イベント計測の実装後、`setCustomerUserId`を使用して、継続して使用する識別子を設定します。これにより、Web上の行動を他のプラットフォーム（モバイル、PC、CTV）での行動と紐づけ、プラットフォームをまたぐユーザーの一連の行動をまとめて把握できます。

**主なルール**

* **一貫性：** モバイルアプリの実装と同じCUIDの値を使用してください。モバイルの`setCustomerUserId`については、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk">iOS</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-android-sdk#setting-the-customer-user-id">Android</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id">Unity</Anchor>をご覧ください。
* **タイミング：** CUIDは、ログイン後や会員登録後など、どの段階でも送信できます。 CUIDを取得できたら、できるだけ早く設定してください。多くの場合、ログインや会員登録によってユーザーを識別できるようになるまで待つ必要があります。
* **記述方法：** 値は、引用符で囲んだ文字列として送信してください。**例：**`AF('pba', 'setCustomerUserId', '663274')`
* **プライバシー：** メールアドレスや電話番号など、個人を特定できる情報（PII）を含めないでください。

<Accordion title="例：会員登録後のCUID設定（JavaScriptで直接実装）">

これらのコード例は、参考用です。このコードをそのまま使用しないでください。使い方が分からない場合は、Web開発者に相談してください。

前提：イベントを送信する前に、ページにWeb SDKが読み込まれていること。SDKを再度読み込まないでください。

ユーザーの操作と処理の流れ：

* ユーザーがWebサイトで会員登録します。
* Webサイトのコードがユーザーの情報を取得し、サーバーに送信します。
* サーバーが、そのユーザーに一意のCUIDを生成します。
* 会員登録後の完了ページで、サーバーに問い合わせて新しいCUIDを取得します。
* サーバーの応答を使用し、Web SDKの`setCustomerUserId()`メソッドでAppsFlyerのCUIDを設定します。

<div id="a-sign-up-form-example" />

#### 会員登録フォームの例

以下のコードは、シンプルな会員登録フォームです。フォームが送信されると、メールアドレスが`localStorage`に保存されます。ユーザーが完了ページに移動すると、そのメールアドレスがサーバーに送信され、対応する一意のCUIDが取得されます。

```javascript
<0>
<1>
    <2>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    2>
    <2>
        function storeUserEmail() {
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    2>
1>
<3>
    <4>Sign Up4>
    <5>
        <6><7>Name7><8>6>
        <9/>
        <6><7>Email7><10>6>
        <9/>
        <11>
    5>
3>
0>
```

<div id="a-thank-you-page-example" />

#### 完了ページの例

このコードでは、Fetch APIを使用します。ユーザーが入力したメールアドレスをサーバーに送信します。会員登録時にサーバーが一意のCUIDを持つユーザーを作成していることを前提に、メールアドレスをサーバーに送信すると、一意のCUIDが返されます。サーバーが返した一意のCUIDを、`setCustomerUserId`メソッドに渡します。

```javascript
<0>
<1>
    <2>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    2>
    <2>
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }
    2>
1>
<3>
    <4>Thank You for Signing Up!4>
3>
0>
```

</Accordion>

<Accordion title="例：会員登録後のCUID設定（Googleタグマネージャー）">

1. 会員登録ページを作成します。

   以下のコード例は、シンプルな会員登録フォームです。フォームが送信されると、メールアドレスが`localStorage`に保存されます。ユーザーが完了ページに移動すると、そのメールアドレスがサーバーに送信され、対応する一意のCUIDが取得されます。

   ```javascript
   <0>
   <1>
       <2>
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({ 'gtm.start': new Date().getTime(), event: 'gtm.js' });
               var f = d.getElementsByTagName(s)[0], j = d.createElement(s),
                   dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true;
               j.src = 'https://www.googletagmanager.com/gtm.js?id=' + i + dl;
               f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');
           function storeUserEmail() {
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       0>
   1>
   <2>
       <3>Sign Up3>
       <4>
           <5><6>Name6><7>5>
           <8/>
           <5><6>Email6><9>5>
           <8/>
           <10>
       4>
   2>
   11>
   ```
2. 会員登録したユーザー向けの完了ページを作成します。以下のコードは、GTMのトリガーを使用する完了ページです。ユーザーが会員登録フォームに入力したメールアドレスを、サーバーに送信します。会員登録時にサーバーが一意のCUIDを持つユーザーを作成していることを前提に、メールアドレスをサーバーに送信すると、一意のCUIDが返されます。サーバーが返した一意のCUIDを、`setCustomerUserId()`メソッドで送信します。

   ```javascript
   <0>
       window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
               res.text().then(function (id) {
                   console.log(id);
                   AF('pba', 'setCustomerUserId', id);
               });
           });
       }
   0>
   ```
3. 完了ページの読み込み後に購読登録をアトリビューションするための、新しいタグを追加します。

   [![CUIDのコンバージョンイベント用に新しいGTMタグを追加する画面](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. 他のタグと区別できる名前を付け、タグの種類として<strong>Custom HTML（カスタムHTML）</strong>を選択します。

   [![GTMでタグ名を設定し、Custom HTML（カスタムHTML）を選択する画面](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

   ```javascript
   <0>
       var userEmail = localStorage.getItem('user_email');
       fetch('users/' + userEmail).then(function (res) {
           res.text().then(function (id) {
               console.log(id);
               AF('pba', 'setCustomerUserId', id);
           });
       });
   0>
   ```
5. テキスト欄の下にある**Advanced Settings（詳細設定）**、続いて<strong>Tag Sequencing（タグの順序付け）</strong>を展開し、このタグの実行後にコンバージョンのタグが発火するように設定します。

   [![コンバージョンのタグに対してGTMのTag Sequencing（タグの順序付け）を設定する画面](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. コンバージョンのタグを発火させるタイミングを指定するトリガーを設定します。以下の例では、完了ページの読み込み時に発火します。

   [![完了ページの読み込み時にコンバージョンのタグを発火させるGTMトリガーの設定画面](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Accordion>

<div id="7-manage-privacy" />

## 7. プライバシーの管理

イベント計測の実装後、組織や地域の基準に対応するため、セキュリティやプライバシーに関する制限を適用する必要がある場合があります。

<Accordion title="イベント送信の有効化・無効化">

計測は、次の2つの方法で制御できます。

<div id="sdk-initial-state-setting-in-the-snippet" />

#### SDKの初期状態の設定（コードスニペット内）

Webページの初回読み込み時にSDKがイベントを送信するか、明示的に送信開始を指示するまで待機するかを指定します。この設定は、Webのコードスニペット内で定義します。

* イベントを送信する：`{pba: {webAppId: "...", measurementStatus:true}}`
* イベントを送信しない：`{pba: {webAppId: "...", measurementStatus:false}}`

> 📘 **Note**
>
> measurementStatusが空、またはNULLの場合、AppsFlyerはmeasurementStatus:trueと同じように扱います。

<div id="explicit-control" />

#### メソッドによる明示的な制御

明示的な制御は初期状態の設定より優先され、永続的なファーストパーティCookieを使用します。このCookieには、次の特徴があります。

* Webサイトのドメインに設定されます。
* Web SDKまたはブラウザが定める期間の経過後に、有効期限が切れます。
* ブラウザのCookie設定による制限が常に適用されます。

**コマンド**

* イベントの送信を開始する（オプトイン）：`window.AF_SDK.PLUGINS.PBA.enableMeasurement()`
* イベントの送信を停止する（オプトアウト）：`window.AF_SDK.PLUGINS.PBA.disableMeasurement()`

</Accordion>

<Accordion title="データの保護と除外設定">

Webサイトで厳格なセキュリティやデータプライバシーの要件を満たす必要がある場合は、以下の仕組みを使用して、Web SDKの動作やデータの扱いを設定してください。

<div id="content-security-policy-csp" />

#### コンテンツセキュリティポリシー（CSP）

WebサイトでCSPによってJavaScriptの安全性を確保する必要がある場合、Web SDKでは、CSPの設定とステップ2で選択したコードスニペットに応じて、2つの方法に対応しています。

* **selfを使用するCSP**：`https://websdk.appsflyersdk.com`を`script-src`の許可リストに追加してください。この方法は、標準Web SDKとAdvanced SDK Verificationのどちらでも使用できます。
* **nonceを使用するCSP**：ポリシーで`script-src 'nonce-...'`を使用する場合は、以下のAdvanced SDK Verificationのnonce対応版を使用してください。これにより、検証処理に必要な3つのスクリプトタグすべてにnonceが渡されます。 `{{CSP_NONCE}}`を、サーバーでリクエストごとに生成したnonceの値に置き換えてください。

以下の表は、nonce対応版で使用できるCSPポリシーを示しています。

| ポリシー | 動作可否 | 注意 |
| --- | --- | --- |
| `script-src 'self'` | いいえ | 外部CDNのオリジンが許可されず、インラインスクリプトもブロックされます。 |
| `script-src 'self' https://websdk.appsflyersdk.com` | 一部のみ | ローダーとSDKは許可されますが、初期設定用のインラインスクリプトはブロックされます。 |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | はい | nonceによってインラインスクリプトとローダーが許可され、ローダーからSDKのタグにもnonceが渡されます。 |
| `script-src 'nonce-...' 'strict-dynamic'` | はい（推奨） | nonceによってインラインスクリプトとローダーが許可され、`strict-dynamic`によって動的に挿入されるSDKのタグにも信頼が引き継がれます。許可リストにCDNのオリジンを追加する必要はありません。 |

CSPポリシーとの互換性

<div id="advanced-sdk-verification-with-csp-nonce-snippets" />

#### CSPのnonceに対応したAdvanced SDK Verificationのコードスニペット

<div id="nonce-without-smart-banners" />

<Accordion title="Smart Bannersを使用しない場合">

```javascript
<0>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <1> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
1>
```

</Accordion>

<div id="nonce-with-smart-banners" />

<Accordion title="Smart Bannersを使用する場合">

```javascript
<0>
  // Queue — buffers AF() calls until the SDK is ready
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <1> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
1>
```

</Accordion>

<div id="discard-query-parameters" />

#### クエリパラメータの除外

URLのクエリパラメータに機密情報が含まれる場合は、AppsFlyerでそれらを除外するように設定してください。URL、リファラ、`header_referer`が対象です。

* **すべて**のクエリパラメータを除外する：`af_url=true`を追加します。
* **特定**のパラメータを除外する：`af_url_mask=param`を使用します。複数のパラメータを指定する場合は、`;`で区切ります。

例：

* 除外前：`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`
* 除外後：`param1=value1&af_url_mask=param2;param3`

</Accordion>

<div id="web-sdk-cookies-reference" />

## Web SDKのCookie一覧

Web SDKは、次のCookieを設定または使用します。

| Cookie名 | ドメイン | 有効期間 | 使用条件 | 詳細 |
| --- | --- | --- | --- | --- |
| afUserid | Webサイトのドメイン | 395日 | AMP以外のページ | Webページの読み込みや画面遷移のイベントで、ユーザーを識別します。 |
| AF\_SYNC | Webサイトのドメイン | 1週間 | AMP以外のページ | 最終的なユーザー識別子が設定されていることを示します。サイトの読み込み時間を短縮するために使用します。 |
| af\_id | <Anchor target="_blank" href="http://appsflyer.com/">appsflyer.com</Anchor> | 395日 | サードパーティCookieが許可されている場合の、AMP以外のページ | アプリの起動や画面遷移のイベントで、ユーザーを識別します。 |
| af\_id | <Anchor target="_blank" href="http://onelink.me/">onelink.me</Anchor> | 395日 | サードパーティCookieが許可されている場合の、AMP以外のページ | リンクバナー、OneLink、またはその両方でのエンゲージメントを、アプリの起動イベントに紐づけます。 |
| amp-afUserid | AMPのCDN、またはWebサイトのドメイン | 1年 | AMP（Accelerated Mobile Pages） |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | Webサイトのドメイン | 395日 | AMP以外のページ | 同意の状態を保存します。ユーザーの同意が得られるまで、SDKの動作を停止します。デフォルトでは設定されません。<Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#sending-events-optinoptout">ユーザーの同意に応じた計測の制御</Anchor>を設定した場合にのみ使用します。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01KGJCGCPZDJ446QHW80H9Z4C3=%E6%A6%82%E8%A6%81 h_01M11M9ZXB0PFFPKVDCGVD0RFT=sdk%E3%81%AE%E6%89%8B%E5%8B%95%E5%AE%9F%E8%A3%85 ai-prompt=ai%E3%82%B3%E3%83%BC%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%A8%E3%83%BC%E3%82%B8%E3%82%A7%E3%83%B3%E3%83%88%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9Fsdk%E3%81%AE%E5%AE%9F%E8%A3%85 h_01UJZDE8GXD6NCF10EPF91DH=ai%E3%82%B3%E3%83%BC%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%A8%E3%83%BC%E3%82%B8%E3%82%A7%E3%83%B3%E3%83%88%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9Fsdk%E3%81%AE%E5%AE%9F%E8%A3%85 step-1-obtain-your-keys=1-%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 h_01KP11XJV8B56W7FK2KAAFH0NE=1-%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 step-2-select-a-code-snippet=2-%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%81%AE%E9%81%B8%E6%8A%9E h_01KP11XJV8RDV378GMFF0DVZ8V=2-%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%81%AE%E9%81%B8%E6%8A%9E standard=%E6%A8%99%E6%BA%96web-sdk h_01KP11XJV8MN64YV17D1M0T5B9=%E6%A8%99%E6%BA%96web-sdk h_01KP11XJV8ZGF4SDXJH6FKX18E=advanced-sdk-verification step-3-deploy-the-snippet=3-%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%81%AE%E8%A8%AD%E7%BD%AE h_01KP11XJV8JQ5S2BBS18RV2H2R=3-%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%81%AE%E8%A8%AD%E7%BD%AE create-a-property-in-adobe-experience-cloud=adobe-experience-cloud%E3%81%A7%E3%83%97%E3%83%AD%E3%83%91%E3%83%86%E3%82%A3%E3%82%92%E4%BD%9C%E6%88%90 h_01KP11XJV9RWY4TTWACW69YGJH=adobe-experience-cloud%E3%81%A7%E3%83%97%E3%83%AD%E3%83%91%E3%83%86%E3%82%A3%E3%82%92%E4%BD%9C%E6%88%90 add-the-snippet-to-the-adobe-launch-property=adobe-launch%E3%81%AE%E3%83%97%E3%83%AD%E3%83%91%E3%83%86%E3%82%A3%E3%81%AB%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%82%92%E8%BF%BD%E5%8A%A0 h_01KP11XJV9ZHMP9M85S3KG0V6R=adobe-launch%E3%81%AE%E3%83%97%E3%83%AD%E3%83%91%E3%83%86%E3%82%A3%E3%81%AB%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E3%82%92%E8%BF%BD%E5%8A%A0 add-the-adobe-launch-tag-to-the-website=web%E3%82%B5%E3%82%A4%E3%83%88%E3%81%ABadobe-launch%E3%81%AE%E3%82%BF%E3%82%B0%E3%82%92%E8%BF%BD%E5%8A%A0 h_01KP11XJVBV5J9E0HV5DM9HS7B=web%E3%82%B5%E3%82%A4%E3%83%88%E3%81%ABadobe-launch%E3%81%AE%E3%82%BF%E3%82%B0%E3%82%92%E8%BF%BD%E5%8A%A0 publish-the-adobe-launch-environment=adobe-launch%E3%81%AE%E7%92%B0%E5%A2%83%E3%82%92%E5%85%AC%E9%96%8B h_01KP11XJVB0Y4RCBS9QCFBAKRD=adobe-launch%E3%81%AE%E7%92%B0%E5%A2%83%E3%82%92%E5%85%AC%E9%96%8B 2-make-sure-the-sdk-is-working=4-sdk%E3%81%AE%E5%8B%95%E4%BD%9C%E7%A2%BA%E8%AA%8D h_01KGJCGCPZ38XZAY8SXB48YWBD=4-sdk%E3%81%AE%E5%8B%95%E4%BD%9C%E7%A2%BA%E8%AA%8D 3-set-and-record-events=5-%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%A8%E8%A8%98%E9%8C%B2 h_01KGJCGCPZMPX1FH58MVGM9VQS=5-%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%A8%E8%A8%98%E9%8C%B2 h_01KP3CJBZXV66CCP4N0482DG1N=web-sdk-event-parameters-table h_01KP3CJBZXB328CABH2QCRXTHX=example-record-event-via-af-web-sdk h_01KP3CJBZXM3WK0JYB6S8P6SMQ=example-record-event-via-gtm 1-set-up-a-thank-you-page=1-%E5%AE%8C%E4%BA%86%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01KGJCGCPZQDP9KVBSE1Z1GT48=1-%E5%AE%8C%E4%BA%86%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 2-configure-the-gtm-tag=2-gtm%E3%82%BF%E3%82%B0%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KGJCGCPZ2YVRY6VYJ0BTC14N=2-gtm%E3%82%BF%E3%82%B0%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KP3CJBZXD6MPTQ0KCPMTM1Y9=example-record-event-via-af-web-sdk-interaction h_01KP3CJBZX53G1HABG3TKN2X6S=example-record-event-via-gtm-interaction 1-set-up-a-checkout-page=1-%E8%B3%BC%E5%85%A5%E6%89%8B%E7%B6%9A%E3%81%8D%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01KGJCGCQ0858AAJC82Y2G0GNP=1-%E8%B3%BC%E5%85%A5%E6%89%8B%E7%B6%9A%E3%81%8D%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 2-configure-gtm-variables-and-triggers=2-gtm%E3%81%AE%E5%A4%89%E6%95%B0%E3%81%A8%E3%83%88%E3%83%AA%E3%82%AC%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KGJCGCQ0GGYDQBP9CJNM9AXQ=2-gtm%E3%81%AE%E5%A4%89%E6%95%B0%E3%81%A8%E3%83%88%E3%83%AA%E3%82%AC%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A 3-create-the-interaction-tag=3-%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%93%8D%E4%BD%9C%E7%94%A8%E3%81%AE%E3%82%BF%E3%82%B0%E3%81%AE%E4%BD%9C%E6%88%90 h_01KGJCGCQ0EV557QF3CGZ6YB4X=3-%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%93%8D%E4%BD%9C%E7%94%A8%E3%81%AE%E3%82%BF%E3%82%B0%E3%81%AE%E4%BD%9C%E6%88%90 4-set-customer-user-id=6-%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%83%BC%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCid%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KGJCGCQ0RNBW7V5T4PXVXQW1=6-%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%9E%E3%83%BC%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BCid%E3%81%AE%E8%A8%AD%E5%AE%9A a-sign-up-form-example=%E4%BC%9A%E5%93%A1%E7%99%BB%E9%8C%B2%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AE%E4%BE%8B h_01KGJCGCQ0M0ESXFMK45PJ3SX9=%E4%BC%9A%E5%93%A1%E7%99%BB%E9%8C%B2%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%AE%E4%BE%8B a-thank-you-page-example=%E5%AE%8C%E4%BA%86%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BE%8B h_01KGJCGCQ0FMKFKM2SWV2794T5=%E5%AE%8C%E4%BA%86%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BE%8B 5-manage-privacy=7-%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%AE%E7%AE%A1%E7%90%86 h_01KGJCGCQ01PQWT44ZWE329DWX=7-%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%AE%E7%AE%A1%E7%90%86 sdk-initial-state-setting-in-the-snippet=sdk%E3%81%AE%E5%88%9D%E6%9C%9F%E7%8A%B6%E6%85%8B%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E5%86%85 h_01KGJCGCQ0AQM3Y9NNCJF2XP9G=sdk%E3%81%AE%E5%88%9D%E6%9C%9F%E7%8A%B6%E6%85%8B%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88%E5%86%85 explicit-control=%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AB%E3%82%88%E3%82%8B%E6%98%8E%E7%A4%BA%E7%9A%84%E3%81%AA%E5%88%B6%E5%BE%A1 h_01KGJCGCQ07KKYGN5JZF41A6W7=%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89%E3%81%AB%E3%82%88%E3%82%8B%E6%98%8E%E7%A4%BA%E7%9A%84%E3%81%AA%E5%88%B6%E5%BE%A1 content-security-policy-csp=%E3%82%B3%E3%83%B3%E3%83%86%E3%83%B3%E3%83%84%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%83%9D%E3%83%AA%E3%82%B7%E3%83%BCcsp h_01KGJCGCQ0QB7NK6YNZT5XJVJY=%E3%82%B3%E3%83%B3%E3%83%86%E3%83%B3%E3%83%84%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E3%83%9D%E3%83%AA%E3%82%B7%E3%83%BCcsp advanced-sdk-verification-with-csp-nonce-snippets=csp%E3%81%AEnonce%E3%81%AB%E5%AF%BE%E5%BF%9C%E3%81%97%E3%81%9Fadvanced-sdk-verification%E3%81%AE%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88 h_01KP11XJV88YB2NSBZJTX9K7ZQ=csp%E3%81%AEnonce%E3%81%AB%E5%AF%BE%E5%BF%9C%E3%81%97%E3%81%9Fadvanced-sdk-verification%E3%81%AE%E3%82%B3%E3%83%BC%E3%83%89%E3%82%B9%E3%83%8B%E3%83%9A%E3%83%83%E3%83%88 h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners discard-query-parameters=%E3%82%AF%E3%82%A8%E3%83%AA%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E9%99%A4%E5%A4%96 h_01KGJCGCQ010K4RMFMGHD5NDC3=%E3%82%AF%E3%82%A8%E3%83%AA%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E9%99%A4%E5%A4%96 web-sdk-cookies-reference=web-sdk%E3%81%AEcookie%E4%B8%80%E8%A6%A7 h_01KGJCGCQ03A1H7NA5ZGPSGKP3=web-sdk%E3%81%AEcookie%E4%B8%80%E8%A6%A7" />
