---
title: ローデータ項目の手引き
metadata:
  keywords:
    - raw reports
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2016-03-10T14:37:44Z'
  edited_at: '2026-10-14T09:26:29Z'
  id: 208387843
  locale: ja
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/ja/articles/208387843
---
> **At a glance:** この記事では、データフィールド（ローデータ項目の仕様）を説明します。この辞書は、フィールドの意味、フォーマット、利用可能なタイミングを理解するために支援します。

<div id="overview" />

## 概要

ローデータ項目のディクショナリテーブルには、AppsFlyerの各種レポートで利用できるローデータ項目が一覧表示されます。AppsFlyerでローデータ項目が追加されるたびに、テーブルは常に更新されます。

辞書表の列は以下の通りです：

* **フィールドグループ：** フィールドの利用に基づく論理的なグループ化。**注意**！広告収益グループのフィールドは、ローデータレポートで独自の列として表示されるか、**イベント値**の一部として扱われます。
* **名前：**
  * Data LockerおよびPush APIレポートで表示されるフィールド名。
  * [n] という表記は、同じフィールドの複数のインスタンスが存在し、そのインスタンス番号が異なることを意味します。例えば、Sub Param [n] は、Sub Param 1, Subparam 2, ..., Sub Param5を意味します。n 値の範囲は (n=1-5) として表記します。
* **フィールド名**：
  * データ出力画面およびPull APIから提供されるレポートで使用されるフィールド名。
  * [n] という表記は、同じフィールドの複数のインスタンスが存在し、そのインスタンス番号が異なることを意味します。例えば、Sub Param [n] は、Sub Param 1, Subparam 2, ..., Sub Param5を意味します。n 値の範囲は (n=1-5) として表記します。
* **ソース**：フィールド内容の元のソースの場所。例えば：
  * **リンク**：計測リンク（<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">AppsFlyerアトリビューション計測リンクの構造とパラメーター</Anchor>を参照）や、関連する場合はSRNからのAPIレスポンス。
  * **SDK**：アプリ内のSDKを通じて収集されます。
  * **AF**：AppsFlyerによって生成されます。
  * その他多数
* **説明**
  * 一部のフィールドは、イベントのコンテキスト、例えばユーザー獲得やリターゲティングキャンペーンの結果に応じて異なる意味を持ちます。
* **フォーマット：** フィールドタイプと長さ。
  * **文字列**：文字列の最大長。長さ1024文字を超えることや、<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#計測リンクのパラメータuaとリターゲティング">こちら</Anchor>に記載されているフィールドの長さ制限を超えることは推奨しません。
  * **日時**：
    * 形式が `yyyy-mm-dd hh:mm:ss` の文字列。例：`2019-09-17 00:09:25` （データの表示に使用されるタイムゾーンは、利用するデータ配信ツールにより異なります）
      * データ出力画面：アプリで選択されたタイムゾーン。
      * Push API：時間フィールドには、アプリ固有のタイムゾーンを意味する *selected\_time\_zone*オプションがあります。それ以外はUTCです。
      * Master API：デフォルトはアプリで選択可能なタイムゾーンです。
      * Data Locker：UTC
    * CSVファイルの中の日付フィールドは yyyy-mm-dd 形式です。CSVファイルをExcelで開くと、日付フィールドはコンピュータの日時設定を使用してフォーマットされます。[Excel](https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows)で表示形式を変更できます。フォーマットされていない値を見るには、エディターでファイルを開きます。
    * Push API：
      * UTCでのタイムスタンプフィールドの形式： `yyyy-mm-dd hh:mm:ss.sss` /  例： `2019-09-17 00:09:25.123`
      * 選択したタイムゾーンのタイムスタンプフィールドの形式： `yyyy-mm-dd hh:mm:ss.sss±th:tm` / 例： `2019-01-20 04:51:16.000+0000`
  * **列挙型 n 文字**：列挙フィールドには特定の値のみを含めることができます。例えば、コスト通貨は3文字で、指定された通貨コードのみを含めることができます。
  * **列挙型 5 文字ブール値：** フィールドの値は `TRUE` または `FALSE` のいずれかです。

> 👍 **Tip**
>
> * 表を並べ替えるには、列名をクリックします。
> * 表をダウンロードすることもできます。
> * ダウンロードしたCSVには、上記のフィールドに加えて追加のフィールドが含まれます：
<div id="Ao" />

>   * **AppsFlyerのメインレポートスキーマの一部**：
>     * AppsFlyerレポートは大部分が同じスキーマから構築され、同じフィールドが含まれています。
>     * レポートや、データがアドネットワーク、広告主、デバイスプラットフォームから収集されたかどうかに応じて、一部のフィールドにはnullまたは空の値が設定されることがあります。
>     * ビジネスインテリジェンスシステムを設定する際、特定のレポートが常にnullまたは空の値を返す場合でも、すべての主要なAppsFlyerスキーマフィールドを設定することをお勧めします。これにより、データが利用可能になったとき簡単に取り込むことができます。
>     * フィールドがメインのAppsFlyerレポートスキーマの一部でない場合は、特定のレポートにのみ含まれます。例：SKANレポート
>   * **レポート取得方法**：特定のフィールドがPush API、データ出力 / Pull API、およびData Locker経由で利用可能かどうかを示します。**注釈**：フィールドがメインのAppsFlyerレポートスキーマの一部であっても、特定の方法で取得するレポートの一部ではない場合があります。たとえば、配置フィールドはメインのAppsFlyerスキーマの一部ですが、Data Locker、Pull API、またはデータ出力画面経由で配信されるレポートにのみ表示され、Push API経由では表示されません。

| フィールドグループ | 名前 | フィールド名 | ソース | 説明 | 形式 |
| --- | --- | --- | --- | --- | --- |
| <span id="attribution::xde448d77"></span>アトリビューション | ad\_id | Ad id | リンク | 特定の広告に割り当てられた一意の識別子<ul><li>[af\_ad\_id](#attribution::de448d77)と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="attribution::b19119e4"></span>アトリビューション | {"ad_id__assist_[n]"} (n=1-3) |  | AF | 最初のアシストアトリビューションから発生した特定の広告に割り当てられた一意の識別子<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="xattribution"></span>アトリビューション | ad\_name | 広告名 | リンク | 広告に割り当てられた説明ラベル<ul><li>[af\_ad](#attribution)と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="attribution::ce2d519c"></span>アトリビューション | {"ad_name__assist_[n]"} (n=1-3) |  | AF | 最初のアシストアトリビューションから発生した広告に割り当てられた名称<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="skan"></span>SKAN | ad\_network\_ad\_id | 広告ID | アドネットワーク | 広告ID | String |
| <span id="skan::2fb2335a"></span>SKAN | ad\_network\_ad\_name | 広告名 | アドネットワーク | 広告名 | 文字列 |
| <span id="skan::5dca70a1"></span>SKAN | ad\_network\_adset\_id | Adset ID | アドネットワーク | Adset ID | String |
| <span id="skan::d952fce5"></span>SKAN | ad\_network\_adset\_name | Adset name | アドネットワーク | Adset name | String |
| <span id="skan::6f93cee6"></span>SKAN | ad\_network\_campaign\_id | Campaign ID | アドネットワーク | アドネットワークからAppsFlyerにレポートされたキャンペーンID | String |
| <span id="skan::ccaf995e"></span>SKAN | ad\_network\_campaign\_name | Campaign | アドネットワーク | アドネットワークからAppsFlyerにレポートされたキャンペーン名 | String |
| <span id="skan::5fe116d5"></span>SKAN | ad\_network\_channel | Channel | アドネットワーク | フィールドはレポートに追加されますが、必ず値が入るわけではありません。 | String |
| <span id="skan::5125d426"></span>SKAN | ad\_network\_creative | Creative | アドネットワーク | <ul><li>値はアドネットワークから取得したデータの拡充に基づいています。</li><li>SKAN 3 の場合、値はnullです。</li></ul> | 文字列 |
| <span id="skan::5a2fa279"></span>SKAN | ad\_network\_name | Ad network name | アドネットワーク | アドネットワークからAppsFlyerにレポートされたアドネットワーク名。<ul><li>この項目が空白の場合、アドネットワークがそれを入力しなかった（できなかった）ことを意味します。</li><li>[skad\_ad\_network\_id](#skan::70c7a914)を使用してアドネットワーク名を判定できます。これを行うには、<Anchor target="_blank" href="/marketers/ja/docs/skan-integrated-partners-list#apple-skadnetwork-ids-of-ad-networks">この表</Anchor>を使用します。</li></ul> | 文字列 |
| <span id="skan::39724216"></span>SKAN | ad\_network\_source\_app\_id | Ad network source app ID | アドネットワーク | アドネットワークによって報告された媒体アプリID。コストの調整を支援するために使用します - アドネットワークによってレポートされます。パブリッシャーアプリがこのデータの情報源を提供します。 | String |
| <span id="skan::11414be7"></span>SKAN | ad\_network\_timestamp | Ad network timestamp | アドネットワーク | <ul><li>アドネットワークがポストバックを受け取った時刻。</li><li>Google広告の場合、このフィールドは入力されません。</li></ul> | タイムスタンプ |
| <span id="device-info::e7dfb109"></span>デバイス情報 | ad\_personalization\_enabled | Ad personalization enabled | SDK | ユーザーが、Googleによるパーソナライズ広告でのユーザレベルのデータ使用に同意しているか（true）、否か（false）を示します。 | ブール値 |
| <span id="attribution::7ea87d9e"></span>アトリビューション | ad\_placement | Ad placement | リンク | CTV広告の配置に入力 | 文字列 |
| <span id="ad-revenue::a77b252f"></span>広告収益 | ad\_revenue\_ad\_type | Ad revenue ad type | 広告収益SDK | 表示された広告の種類 | 文字列 |
| <span id="ad-revenue::e2b62d09"></span>広告収益 | ad\_revenue\_custom\_parameters | Ad revenue custom parameters | 広告収益SDK | アプリ内に表示される広告に対して広告主が広告収益SDK経由で提供するカスタムパラメーター。 | 文字列 |
| <span id="attribution::x5954755967"></span>アトリビューション | 広告タイプ | Ad type | リンク | 広告タイプは、エンゲージメントを生成した広告の種類を定義します<ul><li>[af\_ad\_type](#attribution::59547559)と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="ad-revenue"></span>広告収益 | ad\_unit | Ad unit | 広告収益API | A/Bテスト実施時の広告収益広告セグメント名 | 文字列 |
| <span id="device-info::ce4bb08e"></span>デバイス情報 | ad\_user\_data\_enabled | Ad user data enabled | SDK | ユーザーが、計測およびパーソナライズされた広告にGoogleがユーザーレベルのデータを使用できるようにすることに同意したか（true）、否か（false）を示します。 | ブール値 |
| <span id="attribution::x9b2f9ab6"></span>アトリビューション | adset\_id | Adset id | リンク | キャンペーン内の広告セットの一意の識別子<ul><li>[af\_adset\_id](#attribution::9b2f9ab6) と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="attribution::9964905a"></span>アトリビューション | {"adset_id__assist_[n]"} (n=1-3) |  | AF | 最初のアシストアトリビューションから発生したキャンペーン内の広告セットの一意の識別子です。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="attribution::x5209dd66"></span>アトリビューション | adset\_name | Adset name | リンク | キャンペーン内の広告のグループ化<ul><li>[af\_adset](#attribution::5209dd66)と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="attribution::f348c026"></span>アトリビューション | {"adset_name__assist_[n]"} (n=1-3) |  | AF | n番目のアシストアトリビューションから発生したキャンペーン内のアドセット名<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="device-info-advertising-id"></span>デバイス情報 | advertising\_id | Advertising ID for Android devices | SDK | <ul><li>ユーザーがリセット可能なデバイスID（別名GAID）。</li><li>CTVの場合、これはCTV IDです（例: RIDAまたはVIDA）。</li></ul> | String |
| <span id="attribution::929faa8"></span>アトリビューション | advertising\_id\_type | Advertising ID type | リンク | <ul><li>ユーザーがリセットできるデバイス固有の識別子タイプ</li><li>[advertising\_id\_value](#attribution::be9cb893) フィールドに提供される広告IDのタイプを指定します。一般的なタイプには、IDFA（iOS）とGAID（Android）があります。</li></ul> | String |
| <span id="attribution::be9cb893"></span>アトリビューション | advertising\_id\_value | Advertising ID value | リンク | ユーザーがリセットできるデバイス固有の識別子の値。<ul><li>[advertising\_id](#device-info-advertising-id)、[idfa](#device-info::e0372922)、[oaid](#device-info::4afa15f) と同じです。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="attribution"></span>アトリビューション | af\_ad | Ad | リンク | 広告名 | String |
| <span id="attribution::de448d77"></span>アトリビューション | af\_ad\_id | 広告ID | リンク | 広告ID | 文字列/整数 |
| <span id="attribution::59547559"></span>アトリビューション | af\_ad\_type | Ad type | リンク | <ul><li>例: バナー、フッター</li></ul> | String |
| <span id="attribution::5209dd66"></span>アトリビューション | af\_adset | Adset | リンク | 広告セット名。1つ以上の広告を含むグループを識別します。 | 文字列 |
| <span id="attribution::9b2f9ab6"></span>アトリビューション | af\_adset\_id | Adset ID | リンク | 広告セットIDは、1つ以上の広告を含むグループを識別します。 | 文字列 |
| <span id="skan::1e316e1d"></span>SKAN | af\_attribution\_flag | AF attribution flag | AF | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#null-conversion-values">シングルソースオブトゥルース（SSOT）メカニズム</Anchor>が有効の場合：trueであれば、インストールはAppsFlyerとSKANの両方によって帰属されます。false：インストールはAppsFyer計測でオーガニックとして計測されていることを示します。[skad\_conversion\_value](#skan::41d3b405)がnullの場合：フラグはtrueまたはfalseのいずれかになります（<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#null-conversion-values">推定値</Anchor> に基づきます）。</li></ul> | Boolean |
| <span id="attribution::acbd5bea"></span>アトリビューション | af\_attribution\_lookback | Attribution lookback window | リンク | <ul><li>インストールが特定の広告に帰属する可能性がある最大期間。</li><li>UA：クリックアトリビューションの場合、af\_click\_lookbackアトリビューションリンクパラメータで設定します。</li><li>リターゲティング:アプリ設定で<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window#リアトリビューション期間の設定方法">リターゲティングクリックスルールックバック</Anchor>を設定します。</li></ul> | 文字列 |
| <span id="attribution::75430560"></span>アトリビューション | af\_c\_id | Campaign ID | リンク | Campaign ID | String |
| <span id="iap::a1f84da0"></span>アプリ内課金 | af\_cancelation\_date\_ms |  | AppsFlyerの購入検証 | キャンセルの日付 |  |
| <span id="attribution::1d1e08b5"></span>アトリビューション | af\_channel | Channel | リンク | メディアソースチャネル。例:Googleの例ではYouTube、Meta広告の例ではInstagram。 | 動的列挙文字列 |
| <span id="attribution::8c179e3b"></span>アトリビューション | af\_cost\_currency | Cost Currency | リンク | <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217に準拠した3文字の通貨コード(USD、EUR)</Anchor>。デフォルトはUSD。 | String |
| <span id="attribution::8733a05b"></span>アトリビューション | af\_cost\_model | Cost model | リンク | コストモデルはアトリビューションリンクで報告されます。CPC/CPI/CPM/その他。現在、この値に関係なく、すべてのコストはCPIに基づいて計算されます。 | String |
| <span id="attribution::5647f309"></span>アトリビューション | af\_cost\_value | Cost value | リンク | コスト通貨の金額。小数点以下４桁まで許可されます。例:320.5095 | String |
| <span id="subscription"></span>Subscription | af\_cuids | CUIDs | AppsFlyerの購入検証 | <ul><li>ARSのコンテキストでは、このパラメータにはすべてのCUIDを含む配列が含まれます。</li><li>CUIDの配列はデバイスIDに関係なく表示されます。したがって、同じCUIDが複数のデバイスIDで表示されることがあります。</li></ul> |  |
| <span id="iapsubscription"></span>IAPサブスクリプション | af\_discount\_id | Discount ID | AppsFlyerの購入検証 | 初回購入時にユーザーに提示されるオファーID。割引コードがある場合にのみIDが提供されます。 |  |
| <span id="subscription::83d8905f"></span>Subscription | af\_discount\_type | Discount type | AppsFlyerの購入検証 | ユーザーが利用した割引の種類想定値:<ul><li>iOS:<ul><li>introductory (初回特典)</li><li>subscription (サブスクリプション)</li></ul></li><li>Android:<ul><li>intro price (導入価格)</li><li>one\_time\_code（ワンタイムコード）</li><li>vanity\_code (カスタム／任意文字列の割引コード)</li></ul></li></ul> |  |
| <span id="attribution::4c444ee7"></span>アトリビューション | af\_engagement\_destination | Engagement destination | AF | **Web**ランディングページ、**モバイル**アプリ（ディープリンクまたはアプリストア経由）、その他の遷移先タイプ（**CTV**、**PC**、**コンソール**など）など、広告からリンクされる遷移先のカテゴリを示します。 | String |
| <span id="iapsubscription::6b5c7f1f"></span>IAPサブスクリプション | af\_environment | Environment | AppsFlyerの購入検証 | データが受信された環境（本番またはサンドボックス） |  |
| <span id="subscription::9d10090e"></span>Subscription | af\_expires\_date\_ms | Subscription expiration date |  | 現在のサブスクリプション請求サイクルの有効期限 |  |
| <span id="attribution::9dd48973"></span>アトリビューション | af\_keywords | Keywords | リンク | ユーザーのオンライン検索で使用された単語。アドネットワークの報告によると | String |
| <span id="iapsubscription::ebbabfd3"></span>IAPサブスクリプション | af\_net\_revenue | Net revenue | True Revenue API | すべての要因を考慮して計算された純収益。詳細は [af\_net\_revenue\_factors](#iapsubscription::398dcab) を参照してください。 |  |
| <span id="iapsubscription::d4d47a47"></span>IAPサブスクリプション | af\_net\_revenue\_country | Net revenue country | True Revenue API | 税金が適用される2文字のISO国コード。<ul><li>例:GB</li></ul> |  |
| <span id="iapsubscription::398dcab"></span>IAPサブスクリプション | af\_net\_revenue\_factors | Net revenue factors | True Revenue API | 報告された[af\_net\_revenue](#iapsubscription::ebbabfd3)の金額を算出する際に考慮された、すべての要因を表す配列データです。<ul><li>例：[store\_commission](#iapsubscription::bd419a23)</li></ul> |  |
| <span id="iapsubscription::45acb981"></span>IAPサブスクリプション | af\_net\_revenue\_postal\_code | Net revenue postal code | True Revenue API | 英数字の文字列<ul><li>例:L4J8E3</li></ul> |  |
| <span id="iapsubscription::e1bc387a"></span>IAPサブスクリプション | af\_net\_revenue\_subdivision | Net revenue subdivision | True Revenue API | 国によっては、追加の州や区分が存在する場合があります。これはISO 3166-2の区分コードに従って処理されます。<ul><li>国コードと区分コードが含まれます。</li><li>例:US-CA</li></ul> |  |
| <span id="iapsubscription::9767b912"></span>IAPサブスクリプション | af\_net\_revenue\_tax\_exclusive | Net revenue tax exclusive | True Revenue API | <ul><li>ブール型パラメータ、trueまたはfalse。</li><li>Falseは、税が全体の収益に含まれていることを意味します。</li><li>Trueは、税が全体の収益に追加されることを意味します。たとえば、アメリカやカナダでは、表示価格に消費税が含まれていません。</li></ul> |  |
| <span id="iapsubscription::60f8530"></span>IAPサブスクリプション | af\_net\_revenue\_tax\_name | Net revenue tax name | True Revenue API | 顧客請求書に表示される特定の税金タイプの名称。<ul><li>例:Sales, VAT, GST</li></ul> |  |
| <span id="iapsubscription::e9ec3c4c"></span>IAPサブスクリプション | af\_net\_revenue\_tax\_rate | Net revenue tax rate | True Revenue API | 4桁までの小数で表される税率。<ul><li>例:7.25</li></ul> |  |
| <span id="iapsubscription::ddec7a40"></span>IAPサブスクリプション | af\_offer\_id | Offer ID | AppsFlyerの購入検証 | 割引価格やプロモーション価格など、関連する取引に適用されるオファーID。 | String |
| <span id="iapsubscription::6a1d1d2a"></span>IAPサブスクリプション | af\_original\_transaction\_id | Original transaction ID | AppsFlyerの購入検証 | <ul><li>元の取引ID</li><li>iOSのみ</li></ul> |  |
| <span id="subscription::b4ee3dae"></span>Subscription | af\_period\_type | Subscription period type | AppsFlyerの購入検証 | <ul><li>サブスクリプションまたはトライアル期間の種類。</li></ul>想定される値：<ul><li>trial, intro, normal</li></ul> |  |
| <span id="iapsubscription::bb6f0cb2"></span>IAPサブスクリプション | af\_product\_id | Product ID | AppsFlyerの購入検証 | サブスクリプションプロダクトID |  |
| <span id="attribution::9067a60e"></span>アトリビューション | af\_prt | Partner | リンク | 代理店識別子。SKANの場合、入力されない可能性があります | String |
| <span id="iapsubscription::a48bb9e9"></span>IAPサブスクリプション | af\_purchase\_date\_ms | Purchase date | AppsFlyerの購入検証 | レポートされたプロダクトIDのアプリ内イベントの購入日 |  |
| <span id="iapsubscription::a56bb9e9"></span>アプリ内課金 | af\_purchase\_option\_id | Purchase option ID | AppsFlyerの購入検証 | トランザクションに関連付けられた購入オプションID。 | String |
| <span id="iapsubscription::a49872e9"></span>アプリ内課金 | af\_purchase\_option\_type | Purchase option type | AppsFlyerの購入検証 | 取引の購入オプションタイプ。設定可能な値 (Android): buy, rent | String |
| <span id="iap"></span>アプリ内課金 | af\_purchase\_state | Purchase state | AppsFlyerの購入検証 | 想定される値：<ul><li>Purchased (購入済み)</li><li>Canceled (キャンセル)</li><li>Pending (保留中)</li></ul> |  |
| <span id="iapsubscription::4d962f68"></span>IAPサブスクリプション | af\_purchase\_token | Purchase token | AppsFlyerの購入検証 | <ul><li>取引の購入トークン</li><li>Androidのみ</li></ul> |  |
| <span id="iapsubscription::b0119997"></span>IAPサブスクリプション | af\_reason | Reason | AppsFlyerの購入検証 | キャンセルまたは解約関連のイベントで、ユーザーが解約またはキャンセルした理由。想定される値：<ul><li>iOS：<ul><li>cancel\_intent</li><li>billing\_issue</li><li>declined\_price\_increase</li><li>product\_unavailable</li></ul></li><li>Android：<ul><li>I don't use this service enough（このサービスを利用していません）</li><li>Technical issues（テクニカル問題）</li><li>Cost-related reasons（コスト問題）</li><li>I found a better app（他に良いアプリを見つけた）</li><li>その他</li></ul></li><li>サブスクリプション再開イベントで、ユーザーがサブスクリプションを再開した理由。可能な値: Android: 一時停止および再開<br />自動更新を無効または有効にする</li><li>払い戻し関連のイベントにおける、ユーザーが払い戻しを受けた理由です。可能な値: iOS: 1: アプリの問題<br />0: 別の理由</li></ul> |  |
| <span id="attribution::15cc3657"></span>アトリビューション | af\_reengagement\_window | Reengagement window | リンク | リターゲティング:イベントがリターゲティングキャンペーンに起因する期間<ul><li>注記：リターゲティングキャンペーンではこのフィールドには値が入力されません。</li></ul> | String |
| <span id="iapsubscription::d5fc1fe4"></span>IAPサブスクリプション | af\_refunded\_transaction\_ids | Refund ransaction ID | AppsFlyerの購入検証 | <ul><li>返金されたすべてのトランザクションIDの配列</li><li>iOSのみ</li></ul> |  |
| <span id="attribution::e9b53459"></span>アトリビューション | af\_siteid | Site ID | リンク | 媒体ID | String |
| <span id="iapsubscription::22a14b24"></span>IAPサブスクリプション | af\_store | Store | AppsFlyerの購入検証 | サブスクリプション製品を購入したアプリストア |  |
| <span id="attribution::eaeca85c"></span>アトリビューション | af\_sub[n] (n=1-5) | Sub param [n] | リンク | 広告主によってアトリビューションリンクに設定されたパラメータ | String |
| <span id="attribution::9fdff16d"></span>アトリビューション | af\_sub\_siteid | Subsite ID | リンク | サブパブリッシャーID | String |
| <span id="subscription::6f140cd3"></span>Subscription | af\_subscription\_ownership\_type | Subscription ownership type | AppsFlyerの購入検証 | FAMILY\_SHARED は、ユーザーがファミリー共有でアクセスできることを意味します。PURCHASED：有料ユーザーが購入を行ったことを意味します。 |  |
| <span id="iapsubscription::4571d5da"></span>IAPサブスクリプション | af\_transaction\_id | Transaction ID | AppsFlyerの購入検証 | <ul><li>トランザクションのID</li><li>iOSのみ</li></ul> |  |
| <span id="attribution::x9067a60e"></span>アトリビューション | agency | Agency | リンク | 代理店識別子<ul><li>[af\_prt](#attribution::9067a60e)と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="attribution::ba8e1da9"></span>アトリビューション | {"agency__assist_[n]"} (n=1-3) |  | AF | 最初のアシストアトリビューションから取得した代理店識別子<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="device-info::a9ae30bc"></span>デバイス情報 | amazon\_aid | Amazon Fire ID | SDK | Amazonデバイス上のユーザーがリセット可能な広告ID。 | String |
| <span id="device-info::3a055021"></span>デバイス情報 | android\_id | Android ID | SDK | 永続的デバイスID | String |
| <span id="attribution::fbb2666c"></span>アトリビューション | app\_group\_id | App group ID | AF | クロスプラットフォーム計測用のOneLinkテンプレートに属する関連アプリ | String |
| <span id="app"></span>アプリ | app\_id | アプリID | SDK | AppsFlyer内の一意のアプリ識別子。例:<ul><li>iOS: id123456789</li><li>Android: com.appsflyer.referrersender</li></ul> | String |
| <span id="app::38720e5d"></span>アプリ | app\_name | App name | SDK | 公開アプリストアおよびHQ1に表示される、アプリの正式名称です。この値はユーザー向けに表示される名称であり、内部識別子やバンドルIDとは異なる場合があります。表示やレポートに使用されます。<ul><li>広告主が設定</li></ul> | String |
| <span id="attribution::b4bcbe76"></span>アトリビューション | app\_store\_id | App store ID | AF | アプリストアに表示されるアプリID | String |
| <span id="app::5a1697f1"></span>アプリ | app\_type | App type | アプリクリップ | 値：<ul><li>app\_clip, full\_app</li></ul> | String |
| <span id="app::f992fbe9"></span>アプリ | app\_version | App version | SDK | 顧客のSDK、またはAppsFlyerのS2S APIを通じて報告されたアプリのバージョンです。<ul><li>広告主が設定</li></ul> | 文字 |
| <span id="app::avc00001"></span>アプリ | app\_version\_\_conversion | コンバージョン発生時のアプリバージョン | SDK | コンバージョン発生時に、顧客のSDKまたはAppsFlyerのS2S APIを通じて報告されたアプリのバージョンです。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="device-info::98b3ecc7"></span>デバイス情報 | appsflyer\_id | AppsFlyer ID | SDK | <ul><li>アプリがデバイスにインストールされたときにSDKによって生成される一意のID。このIDは、LTVフローでアプリ内イベントを関連付けたり、コンバージョンデータを取得したり、アプリ内イベントをアフィリエイトするために使用されます。</li><li>アプリを削除して再インストールすると、新しいIDが生成されます。iCloudバックアップからアプリを復元しても、インストールとはみなされません。</li><li>CTVの場合、このフィールドにはcustom\_device\_id（広告主が管理するデバイスID）が入力されます。</li></ul> | String |
| <span id="device-info"></span>デバイス情報 | appsflyer\_id\_type | AppsFlyer ID Type | SDK | [appsflyer\_id\_value](#device-info::b482a05)のデータ取得元を示します（モバイルSDK、Web SDKなど）。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能</li></ul> | String |
| <span id="device-info::b482a05"></span>デバイス情報 | appsflyer\_id\_value | AppsFlyer ID Value | SDK | 単一のコンテキスト（モバイルアプリインストールまたはWebセッション）を表すために使用されるプラットフォームスコープの識別子。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-info::dd85d811"></span>デバイス情報 | att | ATT | SDK | <ul><li>ATT（別名att\_status）はiOS 14以降で利用可能で、次のいずれかの値が設定されます。<Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor>によって返され、S2Sで送信され、AppsFlyerによって決定されます。</li><li>ATT <Anchor target="_blank" href="/marketers/ja/docs/att-implications-ios-14-and-deprecation-of-lat">価値</Anchor>は次のいずれかです: not\_determined、restricted、denied、authorized、af\_unknown、af\_authorized、af\_unavailable。</li></ul> | String |
| <span id="attribution::46498f6f"></span>アトリビューション | attributed\_touch\_time | Attributed touch time | AF | <ul><li>ユーザー獲得: 帰属したタッチの時間。</li><li>リターゲティング: 帰属エンゲージメントの時間。</li></ul> | 日付と時間 |
| <span id="attribution::65deebe6"></span>アトリビューション | attributed\_touch\_type | Attributed touch type | AF | エンゲージメントを分類します。エンゲージメントがインストールと一致した後、AppsFlyerによって設定されます。<ul><li>UA：可能な値：クリック、ダウンロード、インプレッション、プレインストール</li><li>リターゲティング：クリック、インプレッション</li></ul> | 列挙型 |
| <span id="protect360"></span>Protect360 | blocked\_reason | Blocked reason | AF | Protect360:インストールがブロックされる理由。例: install\_hijacking、ボット | String |
| <span id="protect360::e47c57b1"></span>Protect360 | blocked\_reason\_rule | Blocked reason rule (非推奨) | AF | 非推奨 | String |
| <span id="protect360::ecb2f1e5"></span>Protect360 | blocked\_reason\_value | Blocked reason value | AF | Protect360:ブロックに関する追加情報。例:サイトID、検証ルール名 | String |
| <span id="protect360::e5842829"></span>Protect360 | blocked\_sub\_reason | Blocked sub reason | AF | Protect360:インストールがブロックされる特定のサブ理由。例:理由: install\_hijacking。サブ理由: リファラハイジャック、CTIT\_anomalies、validation\_rules | String |
| <span id="app::d66d86c7"></span>アプリ | bundle\_id | Bundle ID | SDK | <Anchor target="_blank" href="https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids">iOS:単一のアプリまたはiOS内のアプリ群を識別するID（Apple開発者バンドルID</Anchor>を参照）<ul><li>Android：アプリID</li><li>注記：このフィールドはAppsFlyer PBAとは関係ありません。</li></ul> | String |
| <span id="attribution::274e74d5"></span>アトリビューション | campaign | Campaign | リンク | キャンペーン名 | String |
| <span id="attribution::x75430560"></span>アトリビューション | campaign\_id | Campaign id | リンク | 特定の広告キャンペーンの一意の識別子です。<ul><li>[af\_c\_id](#attribution::75430560)と同様です。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::f8b1a2e"></span>アトリビューション | {"campaign_id__assist_[n]"} (n=1-3) |  | AF | 最初のアシストアトリビューションから発生した特定の広告キャンペーンの一意の識別子<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::x274e74d5"></span>アトリビューション | campaign\_name | キャンペーン名 | リンク | 広告キャンペーンに割り当てられたキャンペーンの内容を説明するラベルです。<ul><li>[キャンペーン](#attribution::274e74d5)と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::64d77c36"></span>アトリビューション | {"campaign_name__assist_[n]"} (n=1-3) |  | AF | 最初のアシストアトリビューションから発生した広告キャンペーンに割り当てられた名称<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::d8d5132b"></span>アトリビューション | campaign\_type | Campaign type | AF | キャンペーンがユーザー獲得、リターゲティング、またはその他のタイプのいずれに該当するかを示します。AppsFlyerがキャンペーンの目的に基づいて分類した値です。<ul><li>ユーザー獲得（UA）</li><li>オーガニック</li><li>リターゲティング</li><li>不明：メディアソースに紐づかないアプリ内イベント / セッションもしくは、プライバシーポリシーまたはGDPRのリクエストによりデータを削除します。</li></ul> | String |
| <span id="attribution::76ae00fe"></span>アトリビューション | campaign\_type\_\_assist\_3 |  | AF | 3番目のアシストアトリビューションから発生したキャンペーンタイプ<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-info::5ba059c9"></span>デバイス情報 | carrier | Carrier | SDK | Androidが提供するキャリア名は <Anchor target="_blank" href="https://developer.android.com/reference/android/telephony/TelephonyManager#getSimCarrierIdName()">getSimCarrierIdName()</Anchor> を使用しています。<Anchor target="_blank" href="https://android.googlesource.com/platform/packages/providers/TelephonyProvider/+/master/assets/carrier_list.textpb">キャリアマッピング</Anchor>も参照。 | String |
| <span id="attribution::x1d1e08b5"></span>アトリビューション | channel | Channel | リンク | メディアソースチャネル<ul><li>[af\_channel](#attribution::1d1e08b5) と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::760ee8ed"></span>アトリビューション | {"channel__assist_[n]"} (n=1-3) |  | AF | 最初のアシストアトリビューションから発生したメディアソースのチャネル名。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-location"></span>デバイスの位置情報 | city | City | AF | デバイスの所在地の都市。通常、価値には都市名が含まれますが、より正確な地区や自治区の場合もあります。 | String |
| <span id="device-location::ctc00001"></span>デバイスの位置情報 | city\_\_conversion | コンバージョン計測時の都市 | AF | コンバージョン計測時のデバイス所在地の都市です。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::cit00001"></span>アトリビューション | click\_id\_type | クリックIDタイプ | リンク | ネットワーククリックIDタイプ。クリックIDは、広告のクリックURLに付加される一意の英数字識別子で、どの特定の広告、キャンペーン、またはキーワードがクリックを生成したかを追跡することで、正確なアトリビューションを可能にします。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::civ00001"></span>アトリビューション | click\_id\_value | クリックID値 | リンク | ランディングURLからの実際のクリックID値で、シグナルの送信やパートナーAPIを介した完全なキャンペーン階層の解決に使用されます。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-location::11aea02f"></span>デバイスの位置情報 | continent | Continent | AF | 大陸名の2文字の短縮形<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::f1c497c7"></span>アトリビューション | contributor[n]\_af\_prt(n=1-3) | Contributor[n] partner | AF | 代理店またはPMD - 常に小文字に変換されます | String |
| <span id="attribution::860c6c0d"></span>アトリビューション | contributor[n]\_campaign(n=1-3) | Contributor[n] campaign | AF | コントリビューターキャンペーン | String |
| <span id="attribution::contributor_engagement_type"></span>アトリビューション | contributor[n]\_engagement\_type (n=1-3) | Contributor[n] engagement type | AF | 想定される値：<ul><li>可能な値: preload、click\_to\_download、click\_to\_app、engaged\_click、engaged\_view、view、listening、click\_unspecified、 impression\_unspecified</li></ul> | 列挙型 |
| <span id="attribution::daff87fa"></span>アトリビューション | contributor[n]\_match\_type(n=1-3) | Contributor[n] match type | AF | 可能な価値は一致タイプと同じです。 | String |
| <span id="attribution::78fcf7ca"></span>アトリビューション | Contributor [n] media source (n=1-3) | Contributor[n] media source | AF | コントリビューターのメディアソース | String |
| <span id="attribution::d7d270cf"></span>アトリビューション | contributor[n]\_touch\_time(n=1-3) | Contributor[n] touch time | AF | コントリビューターの広告接触時刻 | 日時 |
| <span id="attribution::43d06f64"></span>アトリビューション | contributor[n]\_touch\_type(n=1-3) | Contributor[n] touch type | AF | 想定される値：<ul><li>click, impression</li></ul> | 列挙型 |
| <span id="attribution::afacec40"></span>アトリビューション | contributor\_[n]\_engagement\_type | Contributor[n] engagement type | AF | コントリビューターのエンゲージメントタイプ | 列挙型 |
| <span id="attribution::942d31ab"></span>アトリビューション | conversion\_name | Conversion Name | AF | ユーザーアクティビティによりAppsFlyerシステムで作成されたコンバージョン名。この項目は conversion\_type に関係しています。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::40c20c30"></span>アトリビューション | conversion\_type | Conversion type | AF | コンバージョンの種類:<ul><li>ユーザーのアクションに関連して、AppsFlyerのシステムに記録されたコンバージョン種別です。 [conversion\_name](#attribution::942d31ab).</li><li>インストール</li><li>再インストール (1)</li><li>リエンゲージメント</li><li>不明 (2)</li></ul>[(1) conversion\_type= reinstall で campaign\_type=retargeting である場合、retargeting\_conversion\_type=re-attribution と同等です。](#attribution::40c20c30)<br /><br />(2) メディアソースに帰属しないアプリ内イベント/セッション。 | String |
| <span id="attribution::x8c179e3b"></span>アトリビューション | cost\_currency | Cost Currency | リンク | コストの通貨 -- 参照 [cost\_value](#attribution::x5647f309)<ul><li>[af\_cost\_currency](#attribution::8c179e3b) と同様。</li></ul> | String |
| <span id="attribution::x8733a05b"></span>アトリビューション | cost\_model | Cost model | リンク | 広告の課金モデル（例：CPC、CPM）<ul><li>[af\_cost\_model](#attribution::8733a05b) と同じ</li></ul> | String |
| <span id="attribution::x5647f309"></span>アトリビューション | cost\_value | Cost value | リンク | キャンペーンに関連する費用については、こちらをご覧ください -- [cost\_model](#attribution::x8733a05b) そして [cost\_currency](#attribution::x8c179e3b)<ul><li>[af\_cost\_value](#attribution::5647f309) と同様。</li></ul> | 金額 |
| <span id="device-location::4a3ca194"></span>デバイスの位置情報 | country\_code | Country code | AF | <ul><li>国コードは<Anchor target="_blank" href="https://www.iso.org/iso-3166-country-codes.html">ISO 3166 (alpha-2)</Anchor>を使用します。例:米国、中国。</li><li>英国のコードはGBではなくUKです。</li></ul> | 列挙型 |
| <span id="device-location::ccc00001"></span>デバイスの位置情報 | country\_code\_\_conversion | コンバージョン時の国コード | AF | コンバージョン発生時の国を示すISO 3166（alpha-2）形式の国コードです。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="monetary"></span>金額関連 | currency\_customer | Currency Customer | N/A | 広告主が指定している場合、<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="monetary::rco00001"></span>金額関連 | revenue\_currency\_original | 収益通貨（原文） | SDK | イベントで報告された原文の収益通貨。参照: [`{b:収益額{u:オリジナル}` revenue\_value\_original](#monetary::rvo00001).<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::36c62977"></span>アトリビューション | custom\_data | Custom data | SDK | 広告主がSDKまたはS2Sで設定したデータは、サードパーティやオーディエンスとの連携に最もよく利用されます。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">Android</Anchor>および<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">iOS</Anchor>を参照してください。 | 文字列 \| オブジェクト |
| <span id="attribution::dc3d05d"></span>アトリビューション | custom\_dimension | Custom dimension | SDK | AppsFlyerの将来の使用のために予約済み | String |
| <span id="device-info::40b02bb7"></span>デバイス情報 | customer\_user\_id | Customer user ID | SDK | カスタマーユーザーID（CUID）は、 一位のユーザー識別子です。通常、ユーザー登録時にアプリの所有者によって生成および採番されます。CUIDを使用すると、アプリの所有者はさまざまなデバイス間でユーザージャーニーを追跡できます。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | 文字列 \| 整数 |
| <span id="device-info::ed856308"></span>デバイス情報 | deeplink\_url | Deeplink URL | SDK | ユーザーがディープリンクされているアプリ内の内部アクティビティのパス。ディープリンクおよびディファードディープリンクに使用する。  <br />これには、アトリビューションリンク上のaf\_dp値が含まれます。 | String |
| <span id="protect360::8cb25250"></span>Protect360 | detection\_date | Detection date | AF | アトリビューション不正が検出された日付。 | String |
| <span id="protect360::detstate"></span>Protect360 | protect\_detection\_state | 保護検出状態 | AF | <ul><li>Protect360 によってイベント（例: エンゲージメント、コンバージョン、エンドユーザーイベント）に割り当てられた不正検出結果を示します。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-info::1fd8f0c4"></span>デバイス情報 | device\_category | Device category | 報告されたユーザーエージェント | <ul><li>デバイスのカテゴリ（例：MOBILE\_PHONE、TV）</li><li>使用されたデバイスの種類：タブレット、mobile\_phone、デスクトップ、tv、セットトップボックス、ゲーム機、メディアプレイヤー、unknown\_device\_category。'unknown\_device\_category'の値は、AppsFlyerがデバイスのユーザーエージェントを検出できない場合に生成されます。これは、AppsFlyerがデバイスの特性を特定しようとしたが、既知のカテゴリーに分類できなかったことを示しています。</li></ul> | String |
| <span id="device-info::dfd9504e"></span>デバイス情報 | device\_download\_time | Device download Time | SDK | デバイスの<Anchor target="_blank" href="https://developer.android.com/reference/android/content/pm/PackageInfo#firstInstallTime">Android</Anchor>／<Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=occ">iOS</Anchor>クロックを使用してUTCに変換されたアプリのダウンロード完了時間。値は常にUTC時間として表示されます。  <br />形式: yyyy-mm-dd hh:mm:ss.sss | 日時 |
| <span id="device-info::4a5568db"></span>デバイス情報 | device\_id\_type | Device ID type | SDK | CTVの場合は、CTVプラットフォームIDタイプが入力されます。例えば、Roku用のRIDAなどです。 | 列挙型 |
| <span id="device-info::716c46bf"></span>デバイス情報 | device\_model | Device model | SDK | デバイスの商用モデル名。例: xiaomi::RedmiまたはiPhone7 | String |
| <span id="device-info::2be6278"></span>デバイス情報 | device\_type | Device Type | SDK | デバイスの商用モデル名。<ul><li>[2022年2月2日以降、このフィールドは入力されなくなりました]</li><li>このフィールドの代わりに、同様に設定されるデバイスモデルを使用してください。</li><li>例:<ul><li>デバイスモデル: xiaomi::Redmi Note 8</li><li>デバイスタイプ: xiaomi-Redmi Note 8</li><li>デバイスモデル: iPhone7</li><li>デバイスタイプ: iPhone 7</li></ul></li></ul> | String |
| <span id="skan::d5ea0b47"></span>SKAN | did\_win |  | iOS | インストールに<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">貢献または帰属</Anchor>したキャンペーンを区別するために使用されます。<ul><li>trueの場合：キャンペーンはインストールに貢献したとみなされます（ラストタッチアトリビューション獲得）。</li><li>false の場合、キャンペーンはインストールに貢献していると認識されますが、SKAN ダッシュボードやレポートには含まれません。</li><li>null の場合、<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">以前のiOSまたは SKAdNetwork バージョン</Anchor>のため、 iOS はフィールドに値を入力しませんでした。</li></ul> | Boolean |
| <span id="device-location::e6a26925"></span>デバイスの位置情報 | dma | DMA | AF | 指定市場エリアまたは地理的エリア。<Anchor target="_blank" href="https://www.nielsen.com/us/en/solutions/nielsen-global-connect/">ニールセン企業</Anchor>によって定義されます。<Anchor target="_blank" href="/marketers/ja/docs/determine-user-location">ユーザーの位置を特定する</Anchor>。 | String |
| <span id="device-location::dmac0001"></span>デバイスの位置情報 | dma\_\_conversion | コンバージョン時のDMA | AF | コンバージョン時の指定市場地域。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="lifetime-value-events"></span>顧客生涯価値イベント | end\_user\_event\_type | End User Event Type | N/A | エンドユーザーイベントの種類を識別します。現在の値には、ユーザーの操作によってトリガーされるアプリ内イベントの「IN\_APP」、アプリの起動を表すアプリセッションの「SESSION」、アプリのアンインストールイベントの「UNINSTALL」が含まれます。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | 列挙型 |
| <span id="attribution::8aab1f4d"></span>アトリビューション | engagement\_destination | Engagement Destination | AF | 広告のリンク先となるプラットフォームグループ。例えば、ウェブランディングページ（WEBSITE）や、ディープリンクまたはアプリストア経由のモバイルアプリ（MOBILE）などです。リンク先が不明な場合や指定されていない場合は、空にすることができます。 |  |
| <span id="attribution::engcat"></span>アトリビューション | engagement\_category | エンゲージメントカテゴリ | AF | ユーザーが広告とどのように対話したかを記述する上位グルーピング。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::isintegrated"></span>アトリビューション | is\_integrated | 統合されていますか | AF | メディアソースは統合されていますか？<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | Boolean |
| <span id="attribution::8cea583a"></span>アトリビューション | engagement\_subtype | Engagement Subtype | AF | engagement\_type よりも細かい粒度の広告とのインタラクション<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::f7713604"></span>アトリビューション | {"engagement_subtype__assist_[n]"} (n=1-3) |  | AF | engagement\_type よりも細かい粒度の広告とのインタラクション<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::engagement_type"></span>アトリビューション | engagement\_type | Engagement type | AF | <ul><li>engagement\_type よりも細かい粒度の広告とのインタラクション</li></ul>想定される値：<ul><li>可能な値: preload、click\_to\_download、click\_to\_app、engaged\_click、engaged\_view、view、listening、click\_unspecified、 impression\_unspecified</li></ul> | String |
| <span id="attribution::18bbe871"></span>アトリビューション | {"engagement_type__assist_[n]"} (n=1-3) |  | AF | 最初の支援アトリビューションに由来する、engagement\_categoryよりも詳細な、ユーザーが広告とやり取りした具体的な方法。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="event::13df6252"></span>イベント | event\_name | イベント名 | AF/SDK | <ul><li>アプリが送信したアトリビューションイベントタイプまたはアプリ内イベント名。アトリビューションイベントタイプの例: インストール、リエンゲージメントなど。</li><li>Data Lockerでは、リターゲティングレポートのコンテキストでイベント名は次のように設定されます。リターゲティングはリエンゲージメント、インストールは再アトリビューションを意味します。SKAN レポートでは、アプリ内イベント名はAppsFlyerで設定されたものです。</li><li>SKAN SRNレポートでは、これはMeta広告で設定されたアプリ内イベント名です。</li></ul> | String |
| <span id="event::2f7f426"></span>イベント | event\_revenue | Event revenue | SDK | <ul><li>イベント収益通貨を使用した収益の値。</li><li>範囲外の金額（$-1,000,000 ～ $+1,000,000）はローデータレポートに表示されますが、集計レポートには表示されません。</li></ul> | String |
| <span id="skan::eb2c0d57"></span>SKAN | event\_revenue | Event revenue | AF | 計算式: [特定のイベントの価値の合計（USD）] / [特定の日に発生したイベントの数] | Float |
| <span id="event::78cfad98"></span>イベント | event\_revenue\_currency | Event revenue currency | SDK | SDKに報告されるイベント収益通貨コード。 | String |
| <span id="event::f6999087"></span>イベント | event\_revenue\_usd* | Event revenue USD | AF | <ul><li>収益額。通貨は使用するレポートツールによって異なります。</li><li>優先または選択されたものは、アプリ設定で決定されたアプリ固有の通貨を意味します。</li><li>Data Locker: 常にUSD</li><li>エクスポートページ: 選択通貨</li><li>プルAPI選択可能:USDまたは&currency=preferredを使用して選択します。</li><li>プッシュAPI: 常にUSDと選択通貨の両方を含みます</li></ul> | 文字列 \| 十進数 |
| <span id="event::6b26cc93"></span>イベント | event\_revenue\_xxx | Event revenue selected currency |  | <ul><li>収益額。通貨は使用するレポートツールによって異なります。</li><li>優先または選択されたものは、アプリ設定で決定されたアプリ固有の通貨を意味します。</li><li>Data Locker: 常にUSD</li><li>エクスポートページ: 選択通貨</li><li>プルAPI選択可能:USDまたは&currency=preferredを使用して選択します。</li><li>プッシュAPI: 常にUSDと選択通貨の両方を含みます</li></ul> | String |
| <span id="attribution::eb80c5ea"></span>アトリビューション | event\_source | Event source | AF | 可能な値はエンゲージメントの種類によって異なります。<ul><li>クリック<ul><li>`s2s` （リンクに redirect=false がある場合）</li><li>そうでない場合：</li></ul></li><li>インプレッション<ul><li>`s2s` `s2s`when there is `af_ua` or `af_ip`,</li><li>そうでない場合：</li></ul></li><li>クロスプラットフォームのインプレッション<ul><li>値なし</li></ul></li></ul> | 列挙型 |
| <span id="event"></span>イベント | event\_time | Event time | ポストバック | イベント時間は最も近い時間に切り捨てられます | 日時 |
| <span id="event::b3d24688"></span>イベント | event\_time | Event time | SDK | イベントが発生した時間 | 日時 |
| <span id="event::devevttime"></span>イベント | device\_event\_time | デバイスイベント時間 | AF | イベントが生成され、SDKキャッシュに追加されたときに記録されるデバイス側イベントタイムスタンプ(`af_timestamp`)。AppsFlyer SDKは、Unixエポックからのミリ秒単位の時刻として送信します。Androidでは`System.currentTimeMillis()`を使用して生成され、iOSでは同等のシステムAPIを使用して生成されます。値はサーバー側で正規化され、GMTタイムスタンプとして保存されます。注:これはクライアント側の時間であり、デバイスの時計が不正確であるか、意図的に変更されている可能性があるため、完全に信頼できるものではありません。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | タイムスタンプ |
| <span id="event::origevttime"></span>イベント | original\_event\_time | 元のイベント時間 | AF | カットオフロジックが適用される前のイベント発生の元の時間。非常に遅いイベントに関連する<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | タイムスタンプ |
| <span id="event::556034db"></span>イベント | {"event_time__assist_[n]"} (n=1-3) |  | AF | 最初のアシストアトリビューションから発生したイベント発生時刻<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | TIMESTAMP |
| <span id="event::55b76d8f"></span>イベント | event\_time\_\_attribution |  | AF | アトリビューション（エンゲージメント）イベントから発生したイベント発生時刻<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | TIMESTAMP |
| <span id="time"></span>時間 | event\_time\_\_conversion |  | N/A | イベントタイムスタンプ（コンバージョン、アトリビューション、セッション、アプリ内イベント）*注*：event\_time\_\_conversion はコンテキストエイリアスです。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | 日時 |
| <span id="event::94d6064c"></span>イベント | event\_type | Event type | AF/SDK | アトリビューション イベントの種類。アトリビューションイベントタイプの例: インストール、リエンゲージメントなど。 | String |
| <span id="pba-event"></span>PBAイベント | event\_url | Event URL | Web SDK | イベントが発生したウェブページのURL (元のURLはウェブサイト訪問時と同じ) | String |
| <span id="skan::ed9e6b7a"></span>SKAN | event\_uuid |  | AF | 重複ポストバックを識別するためのユニークなランダム識別子 | String |
| <span id="event::819be544"></span>イベント | event\_value | Event value | SDK | イベント内容は一般的にAppsFlyer SDKから送信されます。JSONとして保存されます。値がJSONとして解析できない場合、\_\_unparseable\_\_というキーを使用してラップされます。値が3000文字を超える場合、3000文字に切り捨てられ、JSONに is\_truncated = true が追加されます | String |
| <span id="event::evtorder"></span>イベント | event\_order | イベント順序 | AF | イベントが生成された時点でのデバイスに記録されたイベント順序カウンター。AppsFlyer SDKで使用される形式です。SDK名: iaecounter これは、アプリ内イベントごとに増加し続け、アプリの再インストール時にリセットされるカウンターです。値は文字列としてSDKから送信されます。【重要】このフィールドはデバイス上で生成され、不正行為者によって改ざんされる可能性があります。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | Long |
| <span id="skan::b328108"></span>SKAN | event\_value | Event value | S2S | <ul><li>デフォルト値： null</li><li>カスタムデコードまたは<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>でイベント送信を実装するアプリによって設定された文字列が含まれます。</li><li>広告主はこれを自社のシステムで使用します。AppsFlyerはこれを利用しません。</li></ul> | 文字列 (JSON) |
| <span id="skan::15ab0ab2"></span>SKAN | fidelity\_type | Fidelity type |  | <ul><li>アトリビューションに影響を与える<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">広告表示</Anchor>オプションを区別します。次のように0と1の値を使用して示されます：<ul><li>ビュースルー広告(0)</li><li>StoreKitでレンダリングされた広告(1)</li><li>SKANバージョンが2.2より前の場合は項目値を無視します。</li></ul></li></ul> | 整数 |
| <span id="protect360::e2ef1cd4"></span>Protect360 | fraud\_reason | Fraud reason | AF | Protect360:ブロックされた理由を参照してください。 | String |
| <span id="protect360::f3bc9fc2"></span>Protect360 | fraud\_sub\_reason | Fraud sub reason | AF | Protect360:ブロックされたサブ理由を参照してください。 | String |
| <span id="device-info::e7bb2cb9"></span>デバイス情報 | gdpr\_applies | GDPR applies | SDK | ユーザがDMA管轄に該当するか（true）、否か（false）を示します。 | ブール値 |
| <span id="attribution::169162d3"></span>アトリビューション | gp\_broadcast\_referrer | Google Play broadcast referrer | Google Playストア | Google Play ブロードキャストリファラー | String |
| <span id="attribution::2ad3d84b"></span>アトリビューション | gp\_click\_time | Google Play click time | Google Play フィールド | 広告クリック後、Google Playでアプリページが読み込まれるまでの時間。<ul><li>時間ソース：Google API</li><li>Android SDKバージョン4.8.5以降で利用可能</li><li>例:install\_timeとgp\_click\_timeを比較します。これにより、アプリをダウンロードしてからユーザーが開くまでの時間を把握できます。</li></ul> | タイムスタンプ |
| <span id="attribution::d8bdd9fe"></span>アトリビューション | gp\_install\_begin | Google Play install begin time | Google Playストア | インストール開始時間<ul><li>時間ソース：Google API</li><li>Android SDK V4.8.5から利用可能</li></ul> | タイムスタンプ |
| <span id="attribution::67a30c47"></span>アトリビューション | gp\_referrer | Google Play referrer | Google Playストア | インストールされたパッケージのリファラーURL。<ul><li>Android SDK V4.8.5から利用可能</li></ul> | String |
| <span id="attribution::fe9e4cb0"></span>アトリビューション | hardware\_id\_type | Hardware id type |  | ユーザーがリセットできないデバイス固有の識別子タイプです。 | String |
| <span id="attribution::6bcef26e"></span>アトリビューション | hardware\_id\_value | Hardware id value |  | ユーザーがリセットできないデバイスレベルの一意の識別子（例：Android ID、IMEI）。値は、hardware\_id\_type フィールドで指定されたタイプに対応します。<ul><li>android\_id および imei と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::2191a08e"></span>アトリビューション | http\_referrer | HTTP referrer | AF | 顧客のウェブサイトに直接リンクされている直前のウェブページのURLです。訪問URLに特定の属性パラメータ（PID、UTM、またはクリックID）が存在しない場合に、属性のフォールバックとして使用されます。 | String |
| <span id="device-info::e0372922"></span>デバイス情報 | idfa | IDFA | SDK | iOSデバイスでユーザーがリセット可能な広告IDが見つかりました。IDFAが利用できない場合は、通常はゼロが入力されます。 | 文字列 |
| <span id="device-info::8471310d"></span>デバイス情報 | idfv | IDFV | SDK | iOSが提供するベンダーID | 文字列 |
| <span id="device-info::d4bf0a30"></span>デバイス情報 | imei | IMEI | SDK | 永続的デバイスID | 文字列 |
| <span id="ad-revenue::5406d519"></span>広告収益 | impressions | Impressions | 広告収益API | ユーザーが広告を見た回数 | String |
| <span id="attribution::instappdl"></span>アトリビューション | install\_app\_store | Install App Store | AF | アプリがインストールされたアプリストア（例：Google Play、Samsung Galaxy Store、Xiaomi Marketplace、Huawei AppGallery）。このフィールドはAndroidにのみ関連しており、アプリ開発者によって入力されます。KBで詳細を確認する — <Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation">マルチストアAndroidアトリビューションの設定</Anchor><ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="skan::913c6896"></span>SKAN | install\_date | インストール日 | iOS | ポストバック到着時刻をもとにAppsFlyerが推定します。 | 時間文字列(Time String) |
| <span id="attribution::15b5bb86"></span>アトリビューション | install\_time | Install time | ポストバック | <ul><li>UA：インストール後の初回起動。</li><li>リターゲティング:リエンゲージメント\/リアトリビューション後の初回起動</li></ul> | 日時 |
| <span id="skan::84c4214f"></span>SKAN | install\_type | Install type | iOS | 新規インストール | String |
| <span id="skan::576274f5"></span>SKAN | interval | Interval | AF | アクティビティ期間の間隔。 | 整数 |
| <span id="device-location::f8003308"></span>デバイスの位置情報 | ip | IP | AF | <Anchor target="_blank" href="/marketers/ja/docs/determine-user-location">IPアドレス</Anchor>はIPV4またはIPV6です。AppsFlyerはIPアドレスを使用してユーザーの所在地を特定します。必要に応じて、広告主はレポートやポストバックから<Anchor target="_blank" href="/marketers/ja/docs/apply-ip-masking-to-user-data">IPアドレスをマスク</Anchor>することができます。 | String |
| <span id="attribution::869dd814"></span>アトリビューション | ip\_address\_type | Ip address type |  | ip\_address\_value 項目で指定された IP アドレスのフォーマットを指定します（例：IPv4、IPv6）。<ul><li>IPマスキングが有効な場合、タイプは「MD5\_HASH」になります。中国PIPLソリューションの場合、タイプは「SHA256\_PIPL\_HASH」になります。</li></ul> | String |
| <span id="device-location::xf8003308"></span>アトリビューション | ip\_address\_value | Ip address value | AF | デバイスのIPv4またはIPv6アドレス値。MD5またはSHA256ハッシュにすることができます。<ul><li>ip と同じです。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-info::e79f7a7b"></span>デバイス情報 | is\_lat | Limit ad tracking | SDK | 追跡型広告の制限（LAT）:<ul><li>iOS:iOS 14以降、LATはAppleによって非推奨となります。ATTを使用してユーザーのプライバシーステータスを決定します。またその場合、is\_latの値は無視してください。<br />iOS 14より前は、true の場合 IDFA は利用できず、値は0に設定されます。</li><li><Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/identifier/AdvertisingIdClient.Info#public-constructor-summary">Android</Anchor>:trueの場合、ユーザーは興味に基づく広告をオプトアウトしています。GAIDはデータを収集せず、代わりにゼロを表示します。</li></ul> | 列挙型ブール値 |
| <span id="protect360::d8a27dfc"></span>Protect360 | is\_organic | Is organic | AF | アプリ内イベントがオーガニックインストールに関連付けられているかを示します。 | String |
| <span id="attribution::8aef34c8"></span>アトリビューション | is\_primary\_attribution | Is primary attribution | AF | UA：TRUE  <br />  <br />リターゲティング:リエンゲージメント期間中は、元のメディアソース（リエンゲージメント前）と、リエンゲージメントメディアソースの両方にアトリビューションします。イベントがリエンゲージメント期間内にある場合。元のメディアソースはFALSE（プライマリアトリビューションではない）になります。リエンゲージメントメディアソースはTRUEになります。<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">詳細はこちら</Anchor> | 列挙型ブール値 |
| <span id="event::isa00001"></span>イベント | is\_attributed | が評価される | AF | <ul><li>エンドユーザーイベントがアトリビューションレコードに接続されているかどうかを示します。アトリビューションレコードに接続されている場合（オーガニックまたは非オーガニック）は「True」です。アトリビューションレコードが利用できない場合（例：GDPRにより削除された、期限切れ、またはその他の理由で利用できない）は偽。これらのイベントはオーガニックと見なされます。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | ブール値 |
| <span id="event::ife00001"></span>イベント | is\_first\_event | 最初のイベントか | AF | <ul><li>これは、ユーザーがコンバージョン後に初めて関連するアプリ内イベントを実行したことを示します。これを指標として蓄積することで、特定のアプリ内イベントを実行した一意のユーザー数を測定できます。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | ブール値 |
| <span id="event::3177f2dd"></span>イベント | is\_receipt\_validated | Is receipt validated | AF | SDKに実装されている場合はTRUE\/FALSE\/NULL、それ以外の場合は空 | 列挙型ブール値 |
| <span id="attribution::e433456e"></span>アトリビューション | is\_retargeting | Is retargeting | リンク | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports#ブロック理由">ユーザー獲得：false</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports#ブロック理由">リターゲティング：</Anchor>リターゲティングコンバージョンおよびイベントの場合はTRUE</li></ul> | 列挙型ブール値 |
<span id="d-Y"></span>| <span id="protect360::1e7f166b"></span>Protect360 | <span id="K-gt-FI"></span>is\_tagged |  | AppsFlyer | <span id="YPo"></span>検知がタグ付けされたかどうかを示します。 | <span id="wYXz"></span>String |
| <span id="attribution::1fb276b0"></span>アトリビューション | keyword\_id | キーワードID | リンク | アドネットワークから返されたキーワードID。これはaf\_keywordのIDです。 | String |
| <span id="attribution::dc04765b"></span>アトリビューション | keyword\_match\_type | Keyword match type | AF | <ul><li>キーワードマッチタイプはGoogle AdWordsでのみ提供されます。</li><li>2021年2月15日以降、Apple Search Adsに関連してこのフィールドは入力されなくなります。</li></ul> | String |
| <span id="attribution::x9dd48973"></span>アトリビューション | keywords | Keywords | リンク | ユーザーがオンライン検索の際に使用した単語。<ul><li>[af\_keywords](#attribution::9dd48973) と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::80f36786"></span>アトリビューション | keywords\_id |  | リンク | アドネットワークから返されたKeywordのID。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-info::5d72ff40"></span>デバイス情報 | language | Language | SDK | デバイスによって報告され、デバイスOSによって設定された言語（ロケール）(IETF BCP 47言語タグ)。通常、形式はll-DDです。ここで、llは言語、DDは方言です。たとえば、en-ZAは南アフリカで使用されている英語を意味します。 | String |
| <span id="attribution::cecc12c5"></span>アトリビューション | match\_type | Match type | AF | <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#アトリビューション方法">アトリビューション方法のタイプ</Anchor>。可能な価値は次のとおりです:<ul><li>SRN</li><li>id\_matching</li><li>probabilistic</li><li>deeplink</li><li>preinstall</li><li>[gp\_referrer](#attribution::67a30c47) (Google Playリファラーの文字列)</li><li>fb\_referrer、ig\_referrer (Meta インストールリファラ)</li><li><Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">Third-party Android app store referrer</Anchor></li></ul> | String |
| <span id="skan::ae39e2c4"></span>SKAN | max\_event\_counter | Max event counter | AF | ユーザーが特定のアプリ内イベントを実行した回数を決定するために次の式を使用します: [(min\_event\_counter + max\_event\_counter) ／ 2 を切り上げ]。注記!最も近い整数に切り上げてください。  <br />例:  <br />A. min = 0 で max = 1 の場合：平均は 0.5 です。切り上げると結果は 1 です。  <br />B. min = 5 で max = 10 の場合、平均は 7.5 として切り上げると結果は 8 になります。 | 整数 |
| <span id="skan::11f44c7e"></span>SKAN | max\_revenue | Max revenue | AF | 収益は常に項目 [skad\_revenue](#skan::d831aefd) で提供されます。SKAN 4 またはCustomモードを使用する場合、イベントに関連付けられ、skad\_revenue の計算に使用されるバケットの範囲は、min\_revenue と max\_revenue で記述されます。 | 実数 |
| <span id="skan::61d427e9"></span>SKAN | max\_time\_post\_install | Max time post-install | AF | <ul><li>カスタムコンバージョン:AppsFlyer は、ポストバック到着時間から36時間を引いたものと (min\_time\_post\_install + max\_time\_post\_install) の平均でインストール時間を計算します。ただし、CV=0 の場合、平均 (min\_time\_post\_install + max\_time\_post\_install) は0と見なされます。</li><li>デコードコンバージョンにおいて:min\_time\_post\_install は max\_time\_post\_install より1時間少なく、この時間はあなたがデコードコンバージョンマッピングに設定した hours\_from\_install と同じです。</li></ul> | 整数 |
| <span id="skan::8c407dd5"></span>SKAN | measurement\_window | SKAN measurement window | AF | アクティビティ期間の長さ。デフォルト：24時間 | 整数 |
| <span id="pba-attribution"></span>PBA アトリビューション | media\_channel | Media channel | Web SDK | ウェブサイト訪問に帰属したメディアチャネル | String |
| <span id="attribution::83b91456"></span>アトリビューション | media\_source | Media source | リンク | <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">イベントが紐づけられたメディアソース名、もしくはrestricted</Anchor> | String |
| <span id="attribution::41d00e54"></span>アトリビューション | {"media_source__assist_[n]"} (n=1-3) |  | AF | 最初のアシスト計測から発生したイベントに紐づくメディアソース<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::929e716c"></span>アトリビューション | media\_type | Media type | AF | リンクを含む広告の配置は次の通りです。<ul><li>アプリ：リンクはアプリ内で利用可能です</li><li>ウェブ：リンクはモバイルウェブサイト内で利用可能です</li></ul> | String |
| <span id="ad-revenue::63a5ea9a"></span>広告収益 | mediation\_network | Mediation Network | 広告収益API | 広告収益のメディエーションネットワークがAppsFlyerにイベントをレポーティング | String |
| <span id="skan::f2af60ce"></span>SKAN | min\_event\_counter | Min event count | AF | イベントをユーザーが実行した回数を計算するために使用する。ユーザーが特定のアプリ内イベントを実行した回数を決定するために次の式を使用します: [(min\_event\_counter + max\_event\_counter) ／ 2 を切り上げ]。注記!最も近い整数に切り上げてください。  <br />例:  <br />A. min = 0 で max = 1 の場合：平均は 0.5 です。切り上げると結果は 1 です。  <br />B. min = 5 で max = 10 の場合、平均は 7.5 として切り上げると結果は 8 になります。 | 整数 |
| <span id="skan::224372e8"></span>SKAN | min\_revenue | Min revenue | AF | 収益は常に項目 [skad\_revenue](#skan::d831aefd) で提供されます。SKAN 4 またはCustomモードを使用する場合、イベントに関連付けられ、skad\_revenue の計算に使用されるバケットの範囲は、min\_revenue と max\_revenue で記述されます。 | 実数 |
| <span id="skan::2c7e94a3"></span>SKAN | min\_time\_post\_install | Min time post-install | AF | <ul><li>カスタムコンバージョン:AppsFlyer は、ポストバック到着時間から36時間を引いたものと (min\_time\_post\_install + max\_time\_post\_install) の平均でインストール時間を計算します。ただし、CV=0 の場合、平均 (min\_time\_post\_install + max\_time\_post\_install) は0と見なされます。</li><li>デコードコンバージョンにおいて:min\_time\_post\_install は max\_time\_post\_install より1時間少なく、この時間はあなたがデコードコンバージョンマッピングに設定した hours\_from\_install と同じです。</li></ul> | 整数 |
| <span id="ad-revenue::90d3bcb3"></span>広告収益 | monetization\_network | Monetization network | 広告収益API | 広告を送信するアドネットワーク | String |
| <span id="attribution::7160d53a"></span>アトリビューション | network\_account\_id | Network account ID | リンク | アドネットワークの広告主アカウントID | 文字列 \| 整数 |
| <span id="device-info::4afa15f"></span>デバイス情報 | oaid | <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-knowledge-base-glossary#o">OAID</Anchor> | SDK | 一部のAndroidデバイスでユーザーがリセット可能なIDで、通常GAIDの代替として使用されます。 | 文字列 |
| <span id="device-info::44749108"></span>デバイス情報 | operator | Operator | SDK | <Anchor target="_blank" href="https://developer.android.com/reference/android/telephony/TelephonyManager#getNetworkOperatorName()">SIM MCCMNCから取得されたモバイルオペレーター名。ユーザーがAndroidのgetNetworkOperatorName()を使用したネットワークに登録している場合に利用できます。</Anchor> | String |
| <span id="attribution::2e20e418"></span>アトリビューション | original\_url | Original URL | リンク | <ul><li>UA：クリック／インプレッションURLが使用されました。リンクがブランドリンクの場合：フィールドはブランドリンクを用いて入力されます。</li><li>リターゲティング：次のいずれかを含みます。リターゲティングリンク、ディープリンクデータ、SRNの場合は空です。</li></ul> | 文字列（URL） |
| <span id="attribution::rlw00001"></span>アトリビューション | requested\_lookback\_window | リクエス卜されたルックバックウィンドウ | リンク | エンゲージメントURLで指定された生の未解析値。クリックまたはインプレッションがコンバージョンに帰因できる期間を決定する際に使用されます。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-info::c9430692"></span>デバイス情報 | os\_version | OSバージョン | SDK | デバイス上のオペレーティングシステムのバージョン | String |
| <span id="device-info::ovc00001"></span>デバイス情報 | os\_version\_\_conversion | コンバージョン時のOSバージョン | AF | コンバージョン時のデバイス上のオペレーティングシステムのバージョン。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="ad-revenue::88ea46f4"></span>広告収益 | placement | Placement | 広告収益API | アプリ内で広告が表示される場所 | String |
| <span id="device-info::858b3f6a"></span>デバイス情報 | platform | Platform | SDK | アプリケーションが動作するオペレーティングシステムまたはエコシステム | 列挙型 |
| <span id="app::1f608704"></span>アプリ | platform\_group | Platform Group | AF | 複数のプラットフォーム値をより広いバケットにグループ化し、有意義なレポートを作成できるようにするビジネスレベルのグループ化。これにより、チームは、「モバイルアプリ」、「ウェブ」、「CTVアプリ」などのグループ別にパフォーマンスを分析でき、イベントが発生したプラットフォームのカテゴリを反映できます。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-info::3d0f4698"></span>デバイス情報 | platform\_user\_id\_type |  | SDK | プラットフォームによって生成されたユーザーの一意の識別子タイプ。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-info::bbda346b"></span>デバイス情報 | platform\_user\_id\_value |  | SDK | プラットフォームによって生成されたユーザーの一意の識別子の値。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-location::9d71ef7e"></span>デバイスの位置情報 | postal\_code | Postal code | AF | デバイスの所在地の郵便番号またはZIPコード | String |
| <span id="product-line"></span>プロダクトライン | product\_line\_id | Product Line ID | N/A | AppsFlyerのプロダクトラインの一意の識別子です。クロスプラットフォームで統一された計測を行うために、プラットフォーム間で類似のアプリをグループ化します。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="product-line::d5e0225b"></span>プロダクトライン | product\_line\_name | Product Line Name | N/A | プラットフォーム間で同様のアプリをグループ化するプロダクトラインの名前。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="pba"></span>PBA | query\_params | Query params | リンク | リダイレクトURLのクエリパラメータ（? の後）  <br />例: <Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">https://www.brandpitt.com/signin?utm_source=Google</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&utm\_term=shoes</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&utm\_campaign=cool</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&c=summer</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&af\_siteid=publisher</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&af\_sub1=helloworld</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&af\_keyword=shoes</Anchor><br /><br />URLにクエリパラメータがない場合、値はnullです。 | String |
| <span id="device-info::195c85df"></span>デバイス情報 | raw\_consent\_data | Raw consent data | SDK | 広告主からAppsFlyerに送信された完全な未処理の同意 DMA データを持つJSON オブジェクトを返します。 | 文字列 \| オブジェクト |
| <span id="device-location::1720981c"></span>デバイスの位置情報 | region | Region | AF | SDKが報告したデバイスのIPアドレスを使用します。SKANでは、country\_codeに基づいて決定されます | String |
| <span id="protect360::d685b64e"></span>Protect360 | rejected\_reason | Rejected reason | AF | Protect360:廃止予定。現在はブロックされた理由が含まれています。 | String |
| <span id="protect360::440536f1"></span>Protect360 | rejected\_reason\_value | Rejected reason value | AF | <ul><li>Protect360:ポストアトリビューションでハイジャックされたインストール\/アプリ内イベントの有効な寄与者 (メディアソース) を表示します。貢献者[1-3]またはオーガニックが設定されます。</li><li>Data Locker では、これは validation\_reason\_value として表示されます。</li></ul> | String |
| <span id="attribution::eecda2a2"></span>アトリビューション | retargeting\_conversion\_type | Retargeting conversion type | AF | <ul><li>UA：再インストール</li><li>リターゲティング ：リエンゲージメント、リアトリビューション</li></ul> | 列挙型 |
| <span id="monetary::cf660373"></span>金額関連 | revenue\_usd | Revenue USD | N/A | イベント収益がUSドルに変換されます。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | 数値 |
| <span id="monetary::1248941c"></span>金額関連 | revenue\_value\_customer | Revenue Value Customer | N/A | イベント収益が顧客の希望する通貨に変換されます — currency\_customer を参照してください。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | 数値 |
| <span id="monetary::nrvcust"></span>金額関連 | net\_revenue\_value\_customer | Revenue Value Customer | AF | イベントの純収益（購入やサブスクリプションなど）。顧客が希望する通貨に換算されます。[currency\_customer](#monetary)を参照してください。これは、アプリストア/プラットフォームの手数料および適用される税金（付加価値税/物品サービス税、売上税）を差し引いた総額（event\_revenue\_value\_customer）に相当します。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | Decimal（少数） |
| <span id="monetary::nrusd"></span>金額関連 | net\_revenue\_usd | net\_revenue\_usd | AF | イベントの純収益（購入やサブスクリプションなど）。米ドルに換算されます。総額に相当します（[event\_revenue\_usd](#event::f6999087))アプリストア/プラットフォームの手数料および適用される税金（付加価値税/物品サービス税、消費税）を除いた金額です。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | Decimal（少数） |
| <span id="monetary::rvo00001"></span>金額関連 | revenue\_value\_original | 収益額 (原文) | SDK | イベントで報告された元の収益額（元の通貨建て）。参照: [revenue\_currency\_original](#monetary::rco00001).<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | 数値 |
| <span id="app::89931c41"></span>アプリ | sdk\_version | SDK version | SDK | AppsFlyer SDKバージョン | String |
| <span id="ad-revenue::ae2875be"></span>広告収益 | segment | Segment | 広告収益API | 広告収益セグメント名 | String |
| <span id="attribution::xe9b53459"></span>アトリビューション | site\_id | Site id | リンク | <ul><li>発行者IDを表します。メディアソースは、それぞれ異なるサイトIDで識別されるさまざまな発行者で広告を配信することがあります。</li><li>[af\_siteid](#attribution::e9b53459)と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::b09cbd8f"></span>アトリビューション | {"site_id__assist_[n]"} (n=1-3) |  | AF | <ul><li>最初のアシストアトリビューションから発生したパブリッシャーIDを表します。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="skan::70c7a914"></span>SKAN | skad\_ad\_network\_id | Ad network ID | iOS | ポストバックが送信されたアドネットワークのID | String |
| <span id="skan::85b51b68"></span>SKAN | {"skad_ambiguous"} {"_event"} | Ambiguous event | AF | true の場合、広告主が管理画面で SKAN の設定を変更してから最初の 72 時間以内にiOSポストバックが受信されました。  <br />SKANが採用しているさまざまなタイマーのため、AppsFlyerはイベントを正確にマッピングできません。 | Boolean |
| <span id="skan::89c88e44"></span>SKAN | skad\_app\_id | アプリID | iOS | アプリID | String |
| <span id="skan::95b0801d"></span>SKAN | skad\_attribution\_signature | Attribution signature | iOS | アドネットワークによってSKANポストバックに追加された署名 | String |
| <span id="skan::9c8a097a"></span>SKAN | skad\_campaign\_id | Campaign ID | iOS | 広告を掲載するために使用されるキャンペーンID。範囲 0～100 | 整数 \| 文字列 |
| <span id="skan::275a8850"></span>SKAN | skad\_coarse\_conversion\_value | Coarse conversion value | iOS | <ul><li>値はlow、medium、highのいずれかになります。</li><li>SKAN 3 の場合、値はnullです。</li></ul> | String |
| <span id="skan::41d3b405"></span>SKAN | skad\_conversion\_value | Conversion value | iOS | iOSによりレポートされたコンバージョン値。範囲は0〜63です。<ul><li>nullの場合、iOSはフィールドを記入しませんでした。</li></ul> | 整数型(Integer) |
| <span id="skan::accd42a5"></span>SKAN | skad\_did\_win | Did win | iOS | インストールに<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">貢献または帰属</Anchor>したキャンペーンを区別するために使用されます。<ul><li>trueの場合：キャンペーンはインストールに貢献したとみなされます（ラストタッチアトリビューション獲得）。</li><li>false の場合、キャンペーンはインストールに貢献していると認識されますが、SKAN ダッシュボードやレポートには含まれません。</li><li>null の場合、<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">以前のiOSまたは SKAdNetwork バージョン</Anchor>のため、 iOS はフィールドに値を入力しませんでした。</li></ul> | Boolean |
| <span id="skan::3b4ad54f"></span>SKAN | skad\_fidelity\_type | Fidelity type | iOS | <ul><li>アトリビューションに影響する<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">広告表示</Anchor>オプションを区別します。次のように0と1の値を使用して示されます。<ul><li>ビュースルー広告(0)</li><li>StoreKitでレンダリングされた広告(1)</li><li>SKANバージョンが2.2より前の場合は、フィールド値を無視します。フィールドはレポートに追加されますが、必ずしも入力されるわけではありません。</li></ul></li></ul> | 整数型(Integer) |
| <span id="skan::a36c9f3c"></span>SKAN | skad\_mode | SKAN mode | AF | iOSポストバックをデコードするために使用されるコンバージョン計測モード。含まれる値：<ul><li>custom\_decode</li><li>revenue</li><li>events</li><li>skan4</li><li>custom\_encode</li><li>engagement</li></ul> | String |
| <span id="skan::546f8b91"></span>SKAN | skad\_postback\_sequence\_index | Postback sequence index | iOS | <ul><li>値はSKAN期間を（0、1、または2）を表します。</li><li>SKAN 3の場合、値は0です。</li></ul> | 整数型(Integer) |
| <span id="skan::8e4acd4"></span>SKAN | skad\_redownload | Redownload | iOS | trueの場合：アプリは再ダウンロードであることを指します。 | Boolean |
| <span id="skan::d831aefd"></span>SKAN | skad\_revenue | Revenue | iOS | イベント収益額（USD） | Float型(Float) |
| <span id="skan::6d2ea88c"></span>SKAN | skad\_source\_app\_id | Source app ID | iOS | <ul><li>サイトID - 広告を配信するアプリです。</li><li>フィールドの入力はプライバシーしきい値に依存します。</li></ul> | String |
| <span id="skan::3dbc953"></span>SKAN | skad\_source\_domain | Source domain | iOS | <ul><li>値は、帰属可能なウェブ広告のソースを示します。</li><li>SKAN 3 の場合、値はnullです。</li></ul> | String |
| <span id="skan::19de61ba"></span>SKAN | skad\_source\_identifier | Source identifier | iOS | <ul><li>値は最大4桁です。</li><li>SKAN 3の場合、値はnullです。</li></ul> | String |
| <span id="skan::b186321d"></span>SKAN | skad\_transaction\_id | SKAN transaction ID | iOS | Appleから付与されたポストバックID | String |
| <span id="skan::3f316453"></span>SKAN | skad\_version | SKAN transaction ID | iOS | SKAN transaction ID | String |
| <span id="skan::3cd1002"></span>SKAN | source\_app\_id |  | AF | サイトID。広告が配信されたアプリのID。[skad\_source\_app\_id](#skan::6d2ea88c)と同様。 | String |
| <span id="device-location::6ae9b695"></span>デバイスの位置情報 | state | 州 | AF | デバイスの所在地の州または県 | String |
| <span id="device-location::stc00001"></span>デバイスの位置情報 | state\_\_conversion | 変換時の状態 | AF | 変換時のデバイス所在地の州または県。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="iapsubscription::bd419a23"></span>IAPサブスクリプション | store\_commission | Store commission | True Revenue API | 購入された製品からストアが得る手数料の計算された割合です。<ul><li>小数として表示されます。</li><li>例:30</li></ul> |  |
| <span id="attribution::4c11e393"></span>アトリビューション | store\_product\_page | Store product page | AF | ユーザーがリダイレクトされたAndroidまたはAppleアプリストア(iOS 15+)のカスタム商品ページ。 | String |
| <span id="attribution::b75cae23"></span>アトリビューション | store\_product\_page\_id |  | リンク | ユーザーがリダイレクトされたAndroidまたはAppleアプリストア(iOS 15+)のカスタムプロダクトページのID。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-info::2dc09e38"></span>デバイス情報 | store\_reinstall | Store reinstall | SDK | Appleアプリストアは、AppleユーザーIDを使用して、Apple Search Adsで誘導されたユーザーが再インストールかどうかを判断します。<ul><li>新規ユーザー: false</li><li>既存のユーザーによる再インストール: true</li></ul> | Boolean \| String |
| <span id="attribution::ef045054"></span>アトリビューション | Sub param [n] (n=1-5) |  | リンク | アトリビューションに使用される追加のトラッキングパラメーター<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::subp4"></span>アトリビューション | sub\_param\_4 |  | AF | アトリビューションに使用される追加のトラッキングパラメーター<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::subp5"></span>アトリビューション | sub\_param\_5 |  | AF | アトリビューションに使用される追加のトラッキングパラメーター<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::x9fdff16d"></span>アトリビューション | sub\_site\_id | Sub site id | リンク | サブパブリッシャーに割り当てられた識別子<ul><li>[af\_sub\_siteid](#attribution::9fdff16d) と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="protect360::3b89b7c1"></span>Protect360 | tagged\_additional\_data |  | AF | タグ付きタイプごとに関連するデータが入力される動的フィールド。例：タグ付けされた理由が「new release」の場合、関連するリリースパッケージのパッケージ番号が反映されます。 | String |
| <span id="protect360::d46f7957"></span>Protect360 | tagged\_type |  | AF | 検知フラグを立てたタグの種類を表します。タグ付けタイプの例：新規リリース、アプリ評価など | String |
| <span id="protect360::c64c1afb"></span>Protect360 | tagged\_validation\_reason\_value |  | AF | 検知が実装モードかつリアルタイムの場合に、アトリビューションを受け取る正当なコントリビューターを記載します。 | String |
| <span id="skan::c7910cfb"></span>SKAN | timestamp | Timestamp | アドネットワーク | ポストバックがAppsFlyerに到達した時間  <br />Google広告とMeta広告の場合、これはそれぞれのAPIからAppsFlyerがデータを取得する時間です。 | Timestamp |
| <span id="time::tzc00001"></span>時間 | timezone\_customer | タイムゾーン（顧客） | AF | アプリ所有者が希望するタイムゾーン（IANA形式、例：Europe/Paris、America/Sao\_Paulo）。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="time::tzcc0001"></span>時間 | timezone\_customer\_\_conversion | タイムゾーン（顧客）変換時 | AF | 変換時点でアプリ所有者が希望するタイムゾーン（IANA形式、例：Europe/Paris、America/Sao\_Paulo）。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="attribution::a543f19e"></span>アトリビューション | total\_candidates | Total Candidates | AF | コンバージョン時に特定のデバイスで評価されたエンゲージメント（クリック、インプレッション、その他のエンゲージメントタイプ）の総数を表します。 | String |
| <span id="xapp"></span>アトリビューション | unified\_app\_id | Unified app id | SDK | AppsFlyer内の一意のアプリ識別子。生の [app\_id](#app) は、プラットフォーム内のアプリの識別子です。 [unified\_app\_id](#xapp) は、プラットフォーム間の衝突を防ぐために、プラットフォーム全体でそれを正規化します。構築ルール： - モバイルプラットフォーム（android、ios）の場合、[unified\_app\_id](#xapp)は生の[app\_id](#app)と等しくなります。 - その他のすべてのプラットフォーム（web、CTVなど）の場合、[unified\_app\_id](#xapp)は生の[app\_id](#app)の先頭にプラットフォームとハイフンを付加したものになります（例：「&lt;platform>-&lt;[app\_id](#app)>」）。<ul><li>[app\_id](#app)と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="device-info::a74b0cd"></span>デバイス情報 | user\_agent | User Agent | リンク | リクエストを行うブラウザ、オペレーティングシステム、デバイスの種類、アプリケーションのバージョンを識別する文字列。 | String |
| <span id="attribution::32f28e6f"></span>アトリビューション | vendor\_id\_type | Vendor id type |  | デバイス+アプリベンダーの固有の識別子タイプ。 | String |
| <span id="device-info::x8471310d"></span>アトリビューション | vendor\_id\_value | Vendor id value | SDK | デバイス+アプリベンダーの固有の識別子値。<ul><li>[idfv](#device-info::8471310d) と同様。</li><li><Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports">アドバンスレポート</Anchor>でのみ利用可能です。</li></ul> | String |
| <span id="pba-event::c1d28dd1"></span>PBAイベント | web\_event\_type | Web event type | Web SDK | Webイベントの種類（訪問、イベントなど） | String |
| <span id="device-info::fdb1b524"></span>デバイス情報 | Wi-Fi | WIFI | SDK | TRUE または FALSE に設定 | 列挙型ブール値 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01JYP22DSGHFMRW5JXDWH6YZZQ=%E6%A6%82%E8%A6%81 d%3FY%3D=d-Y K%26gt%3BFI=K-gt-FI Ao%3B%7C=Ao YPo%5B=YPo" />
