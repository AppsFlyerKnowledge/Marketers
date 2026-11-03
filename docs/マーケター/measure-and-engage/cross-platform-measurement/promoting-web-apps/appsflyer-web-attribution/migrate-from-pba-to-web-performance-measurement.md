---
title: PBAからWeb Performance Measurementへの移行
metadata:
  keywords:
    - Developers
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
  created_at: '2026-07-26T11:53:06Z'
  edited_at: '2026-10-21T19:06:13Z'
  id: 49156441281425
  locale: ja
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ja/articles/49156441281425
---
> **At a glance:** People-Based Attribution（PBA）は、AppsFlyerのWeb計測を強化したソリューションであるWeb Performance Measurementに置き換えられます。この記事では、変更点、移行手順、レポートおよびサーバー側の連携における全フィールドの対応関係を説明します。

## Web計測を強化する背景

Web計測の重要性は、これまで以上に高まっています。 Webサイトは、多くのユーザーがコンバージョンに至る場所であり、モバイルアプリへの導線の出発点でもあります。 Webサイトの役割は、ランディングページだけにとどまりません。質問への回答に応じた案内、ユーザーに合わせた利用開始の案内、有料コンテンツへのアクセス制限、オンラインストアなど、ユーザー獲得に至る一連の仕組みを備えています。こうした仕組みにより、利用や購入への意欲が高いユーザーを、より低いコストで獲得できることも少なくありません。

AppsFlyerは、Web計測をモバイル計測と同じ水準に引き上げます。従来のWeb向け製品であるPeople-Based Attribution（PBA）は、AppsFlyerの基幹アトリビューションエンジンと統一されたデータモデルを基盤とするWeb Performance Measurementに置き換えられます。 Web Performance Measurementは、現在のPBAの全機能に加え、以下を提供します。

* **Webとアプリの計測データを一元管理**：Webとモバイルアプリの計測をまとめ、コスト集計、広告最適化用のポストバック、クリエイティブの最適化も一元化します。
* **予算配分の判断を改善**：ビジネスに合った柔軟なアトリビューションにより、実際に効果のあるキャンペーンに予算を重点的に配分できます。
* **ROASを改善**：アドネットワークへの広告最適化用ポストバックの情報を充実させます。また、サーバー側だけで計測する構成により、より多くのコンバージョンを計測し、アドネットワークがより精度の高い情報を使って広告を最適化できます。
* **プラットフォームを横断してROIを把握**：Web、アプリ、その他のあらゆるプラットフォームにまたがるユーザー行動の流れを計測します。
* **シンプルで統一されたレポート**：すべてのプラットフォームで共通のダッシュボードとデータレポートを利用でき、データは1時間ごとに更新されます。

> 📘 **Note**
>
> Web SDKを置き換える必要はありません。 Web Performance Measurementは同じSDKを使用するため、Webサイトのコード変更は不要です。それ以外の移行に必要な作業は、現在のデータ取得方法がダッシュボード、Data Locker、サーバー間（S2S）APIのいずれであるかによって異なります。

## PBAとWeb Performance Measurementの比較

このセクションでは、全体的な機能と流入元の判定の2つの観点から、PBAとWeb Performance Measurementを比較します。

### Web Performance MeasurementとPBAの機能比較

以下の表では、データ、レポート、アトリビューションに関するPBAとWeb Performance Measurementの機能を比較しています。

<table><tbody><tr><td>機能</td><td>説明</td><td>PBA</td><td>Web Performance Measurement</td></tr><tr><td colspan="4"><strong>データ</strong></td></tr><tr><td>データ反映までの時間</td><td>データがレポートで利用可能になるまでの時間</td><td> <span>✗</span> 日次</td><td> <span>✓</span> 1時間ごとのレポート。データ反映まで約2時間</td></tr><tr><td>データモデル</td><td>モバイルのアトリビューションデータとのスキーマの共通化</td><td> <span>✗</span> モバイルとは異なる</td><td> <span>✓</span> モバイルと共通化され、データの結合・分析が容易</td></tr><tr><td colspan="4"><strong>レポート</strong></td></tr><tr><td>アクティビティダッシュボード</td><td>イベント発生時刻に基づくダッシュボード</td><td> <span>✓</span> 対応</td><td> <span>✓</span> 対応</td></tr><tr><td>コホートダッシュボード</td><td>獲得時期などで分類したユーザーグループごとに、成果の推移を分析</td><td> <span>✗</span> 非対応</td><td> <span>✓</span> 対応</td></tr><tr><td>Data Lockerローデータ</td><td>Data Lockerからの出力によるアトリビューションのローデータ取得</td><td> <span>✓</span> 対応</td><td> <span>✓</span> 対応</td></tr><tr><td>広告単位の詳細データ</td><td>キャンペーン単位から広告単位までのレポート内訳</td><td> <span>✗</span> ダッシュボードのみ対応。ローデータは非対応</td><td> <span>✓</span> ダッシュボードとローデータの両方で、キャンペーンの詳細な内訳に対応</td></tr><tr><td>クロスプラットフォームLTV</td><td>Webとモバイルでのユーザー行動を紐付け、統合したLTVを算出</td><td> <span>✗</span> 非対応</td><td> <span>✓</span> 対応</td></tr><tr><td colspan="4"><strong>コストと最適化用データ</strong></td></tr><tr><td>Web広告コスト</td><td>Webキャンペーンの広告費を取り込み、レポートに表示</td><td> <span>✗</span> 非対応</td><td> <span>✓</span> 対応</td></tr><tr><td>広告最適化用ポストバック</td><td>広告最適化に使用するデータをアドネットワークに送信</td><td> <span>✗</span> 非対応</td><td> <span>✓</span> 対応</td></tr><tr><td colspan="4"><strong>実装</strong></td></tr><tr><td>Web SDK（ピクセル）</td><td>Webサイトへの訪問とイベントを計測するクライアント側のSDK</td><td> <span>✓</span> 対応</td><td> <span>✓</span> 同じSDKを使用。コード変更は不要</td></tr><tr><td>S2S対応</td><td>訪問とイベントをサーバー側だけで計測</td><td> <span>✗</span> イベントのみ</td><td> <span>✓</span> イベントと訪問に対応。サーバー側だけでの実装に対応しています。</td></tr><tr><td colspan="4"><strong>アトリビューションエンジン</strong></td></tr><tr><td>アトリビューション関連の期間設定</td><td>ルックバック期間、アトリビューション期間、リエンゲージメント期間、非アクティブ期間を設定可能</td><td> <span>✗</span> クリックルックバック期間のみ</td><td> <span>✓</span> 5種類の期間を設定可能（すべて調整可能）</td></tr><tr><td>新規ユーザー獲得イベントのカスタマイズ</td><td>初回訪問以外のイベントを、新規ユーザー獲得（UA）とみなすイベントとして定義</td><td> <span>✗</span> 初回訪問のみ</td><td> <span>✓</span> 任意のカスタムイベント（登録、購入など）</td></tr><tr><td>新規ユーザー獲得とリターゲティング</td><td>新規ユーザー獲得とリエンゲージメントの成果を別々に紐付け</td><td> <span>✗</span> 新規ユーザー獲得の概念はなく、イベントは最後の接触先に紐付け</td><td> <span>✓</span> 新規ユーザー獲得とリターゲティングそれぞれの表示に対応し、両方に成果を紐付け</td></tr></tbody></table>

### PBAとWeb Performance Measurementの流入元判定の比較

メディアソース、チャネル、キャンペーンの値がPBAのレポートと異なる場合、その理由は以下のとおりです。どちらも基本的な仕組みは同じです。Webサイト訪問時のURLパラメータとリファラを優先順位に沿って確認し、最初に条件が一致したものからメディアソースを判定します。ただし、いくつかのルールが変更されたため、レポートに表示される値も変わります。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/pba-media-source-attribution-rules">PBAのメディアソースアトリビューションルール</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/about-traffic-source-resolution">流入元の判定について</Anchor>を参照してください。

<Accordion title="メディアソースの値の変更">

| 判定条件 | PBAでの値 | 新しい値 |
| --- | --- | --- |
| Googleのディスプレイ広告・動画広告（utm\_source=Google + utm\_medium= cpm / display/banner/video/listing） | `doubleclick_int` | `dv360_int` |
| UTMによるTwitterの判定（twitter + cpc） | X Ads | Twitter |

Web Performance Measurementでは、さらに多くのPIDの値を表示名などに変換します。たとえば、`iossearchads_int`はApple Search Ads、`metweb_int`はFacebook Ads、`twitterweb_int`はTwitter、`tiktokweb_int`は`tiktokglobal_int`、`snapweb_int`は`snapchat_int`になります。従来の値に基づいて作成したレポートは、新しい値に対応させる必要があります。

</Accordion>

<Accordion title="対応するクリックIDの拡大とdclid単独での判定の廃止">

PBAは、3種類のクリックIDからメディアソースを判定していました。`gclid`は`googleadwords_int`、`dclid`は`doubleclick_int`、`msclkid`は`bingsearch_int`に対応していました。

Web Performance Measurementでは、さらに多くのクリックIDに対応しています。`gclid`/`wbraid`/`gbraid`は`googleadwords_int`、`msclkid`は`bingsearch_int`、`twclid`はTwitter、`vmcid`は`yahoogemini_int`、`sccid`は`snapchat_int`、`li_fat_id`は`linkedin_int`、`ttclid`は`tiktokglobal_int`、`tbclid`は`taboola_int`、`ob_click_id`/`dicbo`は`outbrain_int`、`yclid`は`yandex_int`、`rdt_cid`は`reddit_int`に対応します。

> 🚧 **Important**
>
> 動作上の変更は2点あります。dclid単独での判定は行われなくなりました（PBAではdoubleclick\_intと判定していました）。また、fbclidは判定に使用しません。

</Accordion>

<Accordion title="UTMのカスタムルールの拡大">

Web Performance Measurementでは、`utm_source`と`utm_medium`の組み合わせに対するカスタムの対応ルールが拡大されています。PBAでは限定的な単一のmedium値にしか対応していませんでしたが、paid、paid\_search、paid-searchなど、同じ意味を持つより多くのmedium値に対応し、TikTok、Snapchat、Pinterestも対象に追加されました。カスタムルールに一致しない場合は、どちらも`utm_source`の値をそのまま使用します。

</Accordion>

<Accordion title="チャネル">

チャネルの**値**の表記も変わります。PBAのDirect / Organic search / Social media / Email / Ad / Referral / Otherは、新しいDIRECT / ORGANIC\_SEARCH / SOCIAL\_MEDIA / EMAIL / AD / REFERRAL / OTHERになります。従来の値に基づくフィルターやグループ化の設定は、更新が必要です。

</Accordion>

## Web Performance Measurementへの移行

移行には、すべての方に共通する必須の手順が1つあります。その後は、ご利用のPBAの構成に該当する手順を実施してください。

> 📘 **Note**
>
> **移行前後で数値が変わることへの留意（すべての方が対象）**
>
> PBAでの数値と、移行後の数値は完全には一致しません。 Web Performance Measurementのアトリビューションロジックは、より高度で柔軟です。 PBAは独自のメディアソースアトリビューションルールを適用していましたが、Web Performance Measurementは改良された流入元判定を使用します。値の変更については、前述の「PBAとWeb Performance Measurementの流入元判定の比較」を参照してください。セッションの記録ロジック自体は変わりません。引き続き、業界標準である30分間のアクティビティを1セッションとして扱います。

### 手順1. Webアプリの作成（すべての方に必須）

1. <Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#web">新しいWebアプリを作成</Anchor>し、**Web SDK ID**フィールドで既存のWeb Dev Keyを選択します。これにより、現在のWebサイトのコードを変更せずに、そのまま利用できます。
2. 新しいアプリの<Anchor target="_blank" href="/marketers/ja/docs/configure-web-performance-measurement-settings">アトリビューション設定を行います</Anchor>。

### 手順2. S2S APIでイベントを送信している場合

新しいS2S APIに移行します。

1. [PBA Web-S2Sから新しいS2S APIへの移行](#pba-web-s2sから新しいs2s-apiへの移行)を参照し、エンドポイント、認証、送信データのフィールドについて、現在のPBA S2S連携との違いを確認します。
2. Web Performance Measurementの<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-s2s-api-for-web-performance-measurement">新しいS2S API</Anchor>を設定します。
3. サーバー側の連携を更新し、新しいエンドポイントに送信するようにします。

### 手順3. PBAのローデータレポートを利用している場合

新しいData Lockerレポートに移行します。エンドユーザーイベントレポートが、<Anchor target="_blank" href="/marketers/ja/docs/pba-raw-data-reports">PBAのWebサイト訪問レポートとWebサイトイベントレポート</Anchor>に置き換わります。

1. Data Lockerを利用できることを確認します。利用できない場合は、アカウントへの追加または購入が必要です。
2. [ローデータフィールドの対応表](#ローデータフィールドの対応表)で、名称変更、定義変更、廃止されたフィールドを含め、すべてのフィールドの対応関係を確認します。
3. <Anchor target="_blank" href="/marketers/ja/docs/export-web-performance-measurement-report-data-from-data-locker">Data LockerからのAppsFlyer Webアトリビューションレポートデータの出力</Anchor>に従い、新しいレポートを有効にします。
4. BIツールやETL処理の参照先を、新しいレポートの保存先とフィールドに変更します。これは、イベントの送信元がSDKかS2Sかにかかわらず必要です。どちらも同じローデータレポートに格納されます。

### 手順4. クロスプラットフォームレポートにPBAのブランドバンドルを使用している場合

1. <Anchor target="_blank" href="/marketers/ja/docs/product-line-group-apps-for-cross-platform-attribution">プロダクトラインを作成します</Anchor>。
2. Webアプリと他のアプリを同じプロダクトラインにまとめると、<Anchor target="_blank" href="/marketers/ja/docs/beta-user-based-cross-platform-attribution">クロスプラットフォームのユーザーLTVレポート</Anchor>を利用できます。

## 提供が終了する機能

| 機能 | 変更内容 | 詳細 |
| --- | --- | --- |
| コンバージョン経路 | すでに廃止されています。 | 該当なし |
| Web広告が貢献したアプリインストール（後のモバイルアプリインストールにつながったWebキャンペーンに成果を紐付ける機能） | 「Web広告が貢献したアプリインストール」専用の表示はありません。 | Webからアプリへのユーザー行動は、Smart ScriptとSmart Bannerで計測します。クロスプラットフォームレポートでは、完全に同じではありませんが、類似の分析が可能です。 PBAと同様に、カスタマーユーザーID（CUID）に基づいています。<ul><li>従来、オーガニックとして報告されるインストールに貢献していたWebキャンペーンは、非オーガニックの新規ユーザー獲得として表示されるようになります。これらのWebキャンペーンは、補助的な貢献ではなく、ユーザーの獲得元として扱われます。</li><li>非オーガニックインストールに貢献していたWebキャンペーンの場合、Webキャンペーンを新規ユーザー獲得、モバイルアプリのインストールをクロスプラットフォームのリターゲティングとして扱います。</li></ul> |
| 過去のアトリビューション結果の再計算 | デフォルトの30分間の待機時間を過ぎると、過去のアトリビューション結果は再計算されません。 | アトリビューションは、30分間の待機時間後に確定します。この間にユーザーが自身を識別できる情報を提供できます。 |
| ローデータフィールド | Web向けレポートでは、モバイル関連のフィールドが廃止されます。名称が変更されるフィールドや、値が変更されるフィールドもあります。 | すべてのフィールドの対応関係は、[ローデータフィールドの対応表](#ローデータフィールドの対応表)を参照してください。 |
| 到着が遅れたS2Sイベント | イベントが発生したUTC日付の終了から30分を過ぎて到着したイベントも受け付けられますが、イベント時刻はAppsFlyerが受信した時刻に置き換えられます。 | イベントを1日分まとめて送信するのではなく、発生時にリアルタイムで、できれば発生から30分以内に送信してください。正確なアトリビューションには、イベントの発生時刻に近いタイミングで受信することが必要です。これにより、Webでの動作が既存のモバイルでの動作と統一されます。 |

## ローデータフィールドの対応表

PBAのWebサイト訪問およびWebサイトイベントのローデータレポートをすでに利用している場合、以下の変更が適用されます。レポートの提供先はData Lockerに移ります。以下に、<Anchor target="_blank" href="/marketers/ja/docs/pba-raw-data-reports">PBAのローデータレポート</Anchor>に基づく、新しいエンドユーザーイベントレポートとの全フィールドの対応関係を示します。

> 📘 **Note**
>
> 各プラットフォームのローデータとクロスプラットフォームレポートは、Data Lockerでのみ利用できます。 Data Lockerをまだ利用していない場合は、前述の手順3または手順4を参照してください。

* **変更なし**：フィールド名とデータは同じです。
* **名称変更**：データは同じですが、列名が変わります。
* **定義変更**：名称は同じか類似していますが、データまたは値の形式が変わります（再利用する前に注意が必要です）。
* **廃止**：新しいレポートに対応するフィールドはありません。

| フィールド名 | 説明 | ステータス | 新しいフィールド／注意事項 |
| --- | --- | --- | --- |
| `advertising_id` | 広告ID（GAID） | 廃止 | モバイル／デバイスの広告ID。PBAではプラットフォームを横断した紐付けに使用されていました。クロスプラットフォームのLTVレポートとユーザー行動レポートはCUIDに基づいており、このフィールドは使用しません。 |
| `af_web_id` | Web SDKから送信されるCookie ID | 名称変更 | `appsflyer_id_value`。同じWeb Cookieです。 |
| `amazon_aid` | Amazon Fire TVの広告ID | 廃止 | モバイル／デバイスのID。Webには該当しません。 |
| `android_id` | AndroidデバイスID | 廃止 | モバイル／デバイスのID。Webには該当しません。 |
| `app_id` | 最後にインストールしたアプリのID | 廃止 | クロスプラットフォームで使用するモバイル関連のフィールドです。新しいレポートのWebアプリ識別子は`unified_app_id`（"website-`{domain}`"）であり、別の概念です。 |
| `app_name` | 直近のアプリ名 | 変更なし | &lt;0>app\_name0>. |
| `app_version` | 直近のアプリバージョン | 廃止 | クロスプラットフォームで使用するモバイル関連のフィールドであり、Webには該当しません。 |
| `appsflyer_id` | AppsFlyer（インストール）ID | 廃止 | モバイルアプリのインストールIDです。新しい`appsflyer_id_value`はWeb Cookie（`af_web_id`）であり、別の識別子です。 |
| `attributed_touch_time` | アトリビューションが紐付けられたWebサイト訪問のタイムスタンプ | 名称変更 | `event_time__attribution`。成果が紐付けられた接触（エンゲージメント）の時刻です。 |
| `attributed_touch_type` | 接触の種類。常に"web visit" | 廃止 | PBAでは固定値でした。訪問とイベントの区別には、`end_user_event_type`（SESSION / IN\_APP）を使用します。 |
| `bundle_id` | PBAのバンドルID | 廃止 | クロスプラットフォームレポートでは、プロダクトラインによるグループ化（Web＋モバイルアプリ）に置き換えられます。 |
| `campaign` | Webサイト訪問に紐付けられた値 | 名称変更 | &lt;0>campaign\_name0>. |
| `campaign_id` | Webサイト訪問に紐付けられた値 | 変更なし | &lt;0>campaign\_id0>. |
| `city` | IPアドレスから判定 | 変更なし | &lt;0>city0>. |
| `country_code` | IPアドレスから判定 | 変更なし | &lt;0>country\_code0>. |
| `customer_user_id` | カスタマーユーザーID（CUID） | 変更なし | &lt;0>customer\_user\_id0>. |
| `device_type` | デバイスの種類 | 名称変更 | `device_category`。値が異なります（"Desktop"と"MOBILE\_PHONE" / "TV"など）。 |
| `dma` | IPアドレスから判定 | 変更なし | &lt;0>dma0>. |
| `event_name` | 訪問：常に"website visit"。イベント：送信されたイベント名 | 定義変更 | 訪問では空になります（PBAでは"website visit"が記録されていました）。イベントでは変更ありません。 |
| `event_revenue` | 購入時の通貨でのイベント収益額 | 名称変更 | &lt;0>revenue\_value\_original0>. |
| `event_revenue_currency` | `event_revenue`の3文字の通貨コード | 名称変更 | &lt;0>revenue\_currency\_original0>. |
| `event_revenue_usd` | `event_revenue`を米ドルに換算した値 | 名称変更 | &lt;0>revenue\_usd0>. |
| `event_source` | Web SDKまたはサーバー間通信 | 変更なし | &lt;0>event\_source0>. |
| `event_time` | 訪問：訪問時刻。イベント：イベント発生時刻 | 変更なし | &lt;0>event\_time0>. |
| `event_type` | 標準イベント／コンバージョンイベント／Webサイト訪問 | 定義変更 | コンバージョンイベントとしての区分は廃止されます。訪問とイベントの区別には、`end_user_event_type`（SESSION / IN\_APP）を使用します。 |
| `event_url` | イベントが発生したWebページのURL（訪問では元のURLと同じ） | 変更なし | `event_url`。URLクエリパラメータ（UTMなど）の主な取得元にもなります。 |
| `event_value` | イベント：JSON形式のイベント詳細。訪問：null | 変更なし | &lt;0>event\_value0>. |
| `idfa` | 広告識別子 | 廃止 | モバイル／デバイスのID。Webには該当しません。 |
| `idfv` | 広告識別子 | 廃止 | モバイル／デバイスのID。Webには該当しません。 |
| `imei` | デバイス識別子 | 廃止 | モバイル／デバイスのID。Webには該当しません。 |
| `install_time` | 直近のアプリインストール時刻 | 廃止 | クロスプラットフォームで使用するモバイル関連のフィールドです。 Webでのユーザー獲得（コンバージョン）の時刻は`event_time__conversion`であり、別の概念です。 |
| `ip` | 訪問者のIPアドレス | 名称変更 | `ip_address_value`。値は同じです。ハッシュ化方式を示す`ip_address_type`も追加されます。 |
| `language` | ユーザーエージェントから取得（例："English"） | 定義変更 | `language`。値の形式がISO 639-1と国コードの組み合わせに変わります。 |
| `media_channel` | Webサイト訪問に紐付けられた値（"Ad"） | 廃止 | 必要に応じて、`sub_param_1-5`で代用できます。 |
| `media_source` | Webサイト訪問に紐付けられた値 | 変更なし | &lt;0>media\_source0>. |
| `media_type` | Webサイト訪問に紐付けられた値（"Paid"） | 廃止 | Webでは空です。オーガニックと有料広告の区別には、真偽値の`is_organic`を使用するようになります。 |
| `oaid` | 広告識別子 | 廃止 | モバイル／デバイスのID。Webには該当しません。 |
| `original_url` | 成果が紐付けられた訪問時に、ユーザーをリダイレクトしたURL | 名称変更 | `event_url`に統合されます（訪問では、`event_url`は元のURLと同じです）。独立した列は廃止されます。 |
| `platform` | プラットフォーム（"macOS"、"Windows"） | 定義変更 | プラットフォームの値は常に"WEBSITE"です。 OSの情報は`os_version` / `user_agent`に移ります。 |
| `postal_code` | IPアドレスから判定 | 変更なし | &lt;0>postal\_code0>. |
| `query_params` | リダイレクト元URLのクエリパラメータ（JSON形式） | 廃止 | 未解析のクエリ文字列は`event_url`に含まれます。解析済みのJSONを格納する列は廃止されます。 |
| `referrer` | 成果が紐付けられたWebサイト訪問のHTTPリファラ | 名称変更 | &lt;0>http\_referrer0>. |
| `region` | IPアドレスから判定（"NA"） | 名称変更 | `continent`。大陸コード（例："NA"）です。 |
| `state` | IPアドレスから判定 | 変更なし | &lt;0>state0>. |

<Accordion title="Data LockerのETL移行：AIコーディングツールにそのまま使える指示文">

移行を容易にするため、AIコーディングツール（Claude Code、Cursorなど）にそのまま使える指示文を用意しました。ツールに既存のETLコードへのアクセスを許可し、以下の指示文を貼り付けてください。すべてのフィールドの対応関係と、動作上の違いを網羅しています。この指示文に沿って、ツールが現在のデータ処理の流れを把握し、新しいレポートに対応するように再構築します。

```
AppsFlyerの従来のPBA Data Lockerローデータレポート（Webサイト訪問＋Webサイトイベント）から、Web Performance MeasurementのData Lockerレポート（エンドユーザーイベント）へETL処理を移行してください。この指示文には、構造の変更、すべてのフィールドの対応関係、検証手順など、必要な情報がすべて含まれています。ここに記載されていない内容を推測しないでください。不明な点があれば、私に確認してください。

## 手順1：現在のデータ処理の流れを把握

コードを書く前に、既存のコードを調べ、以下を一覧にまとめてください。
1. 利用しているPBAレポート（Webサイト訪問、Webサイトイベント、または両方）と、その取り込み先。
 読み込んでいるすべてのPBAフィールドと、それぞれの後続処理での用途（変換、結合、ダッシュボード、アラート、データ出力）。
 読み込み頻度とスケジュールに関する前提（PBAは日次で提供）。
 訪問行とイベント行を分離または結合するロジック。
 PBAフィールドの値に基づくフィルター、グループ化、コードに直接記述された値（media_sourceの名称、チャネル名、event_type、platformの値など）。

一覧を私に提示し、確認を得てから次に進んでください。

## 手順2：以下を私に確認

1. 新しいエンドユーザーイベントレポートは、Data Lockerですでに有効になっていますか（AppsFlyerの管理画面で有効化）？まだの場合は、私が先に有効にする必要があります。
 新しいWebアプリの統合アプリID（Unified App ID）は何ですか？形式："website-{domain}"（例：website-www.example.com）。分からない場合は、続行する前にAppsFlyerのダッシュボードで確認します。
 旧処理と新処理を並行して実行し、結果を比較する期間を設けますか？ それとも直接切り替えますか？並行稼働を推奨してください。
 新しい処理では、コンバージョンレポート（重複行のない、一意のアトリビューション記録）またはクロスプラットフォームのエンドユーザーイベントレポート（CUIDで重複を排除した、Webとモバイルのユーザー単位のデータ）も取り込みますか？デフォルトの対象範囲は、PBAレポートを直接置き換える、プラットフォーム単位のエンドユーザーイベントレポートです。

## 設計に反映する構造の変更

1. **2つのレポートを1つに統合。** PBAでは訪問とイベントが別々のレポートでした。新しいエンドユーザーイベントレポートには両方が含まれます。訪問行はend_user_event_type = 'SESSION'、イベント行はend_user_event_type = 'IN_APP'です。有効なevent_nameが入るのはIN_APP行のみです。SESSION行のevent_nameは空になります（PBAでは"website visit"が記録されていました）。
 **すべてのプラットフォームでスキーマを共通化。** Webサイト、モバイル、CTV、PCで同じレポートを使用します。 Webデータだけを抽出するため、必ずplatform = 'WEBSITE'でフィルタリングしてください。
 **両方への成果の紐付けに伴う重複を排除。** 同じ行動が、主たる成果の紐付け先を示す行と、副次的な紐付け先を示す行（新規ユーザー獲得ビューのLTVに使用する、元の獲得元）の2行で記録される場合があります。二重計上を防ぐため、デフォルトでis_primary_attribution = trueのフィルターを適用してください。このフィルターを外すのは、conversion_typeを使って新規ユーザー獲得ビューとリターゲティングビューを個別に分析する場合だけにしてください。
 **日次から1時間ごとの提供に変更。** 新しいレポートは1時間ごとに提供され、データ反映までの時間は約2時間です。増分データの読み込みは、1日分の一括取り込みではなく、1時間ごとの処理を前提に再設計してください。
 **オーガニックと有料広告の区別。** PBAのmedia_type（"Paid"）は廃止されます。真偽値のis_organicを使用してください。media_sourceからオーガニックか有料広告かを推測しないでください。
 **ユーザー数の集計。** COALESCE(customer_user_id, appsflyer_id_value)を使ってユーザーを集計・結合してください。安定したカスタマーユーザーIDを優先し、それがない場合はCookieベースのIDを使用します。
 **空の値。** STRINGフィールドは''、NUMERICフィールドはNULLです。

## フィールドごとの対応関係（PBA → エンドユーザーイベント）

ステータスの意味：変更なし＝名称とデータが同じ。名称変更＝データは同じで、列名が変更。定義変更＝データまたは値の形式が変更（取り扱いに注意）。廃止＝対応するフィールドなし。

| PBAのフィールド | ステータス | 新しいフィールド／対応方法 |
|---|---|---|
| advertising_id | 廃止 | モバイル／デバイスのID。クロスプラットフォームレポートはCUIDに基づくため、このフィールドは使用しないでください。 |
| af_web_id | 名称変更 | appsflyer_id_value。同じWeb Cookie。 |
| amazon_aid | 廃止 | モバイル／デバイスのID。Webには該当しません。 |
| android_id | 廃止 | モバイル／デバイスのID。Webには該当しません。 |
| app_id | 廃止 | クロスプラットフォームで使用するモバイル関連のフィールド。新しいWebアプリ識別子はunified_app_id（"website-{domain}"）です。単なる名称変更ではなく、別の概念です。 |
| app_name | 変更なし | app_name。 |
| app_version | 廃止 | クロスプラットフォームで使用するモバイル関連のフィールド。 |
| appsflyer_id | 廃止 | モバイルアプリのインストールID。注意：新しいappsflyer_id_valueはWeb Cookie（PBAのaf_web_id）であり、このフィールドとは異なります。 |
| attributed_touch_time | 名称変更 | event_time__attribution。 |
| attributed_touch_type | 廃止 | 従来は固定値。訪問とイベントの区別には、end_user_event_typeを使用します。 |
| bundle_id | 廃止 | クロスプラットフォームレポートでは、プロダクトラインによるグループ化に置き換わります。 |
| campaign | 名称変更 | campaign_name。 |
| campaign_id | 変更なし | campaign_id。 |
| city | 変更なし | city。 |
| country_code | 変更なし | country_code。 |
| customer_user_id | 変更なし | customer_user_id。 |
| device_type | 名称変更＋値の変更 | device_category。値が異なります（例："Desktop" → "MOBILE_PHONE" / "TV"のような形式の値）。値に基づくロジックをすべて更新してください。 |
| dma | 変更なし | dma。 |
| event_name | 定義変更 | イベント：変更なし。訪問：空になります（PBAでは"website visit"が記録されていました）。訪問の識別には、end_user_event_type = 'SESSION'を使用してください。 |
| event_revenue | 名称変更 | revenue_value_original。 |
| event_revenue_currency | 名称変更 | revenue_currency_original。 |
| event_revenue_usd | 名称変更 | revenue_usd。 |
| event_source | 変更なし | event_source。 |
| event_time | 変更なし | event_time。 |
| event_type | 定義変更 | "Conversion event"としての区分は廃止されます。訪問とイベントの区別には、end_user_event_type（SESSION / IN_APP）を使用します。 |
| event_url | 変更なし | event_url。URLクエリパラメータ（UTMなど）の主な取得元にもなります。 |
| event_value | 変更なし | event_value。 |
| idfa / idfv / imei / oaid | 廃止 | モバイル／デバイスのID。Webには該当しません。 |
| install_time | 廃止 | モバイル関連のフィールド。 Webでのユーザー獲得時刻はevent_time__conversionであり、別の概念です。 |
| ip | 名称変更 | ip_address_value（ハッシュ化方式を示すip_address_typeも追加）。 |
| language | 定義変更 | language。形式がISO 639-1＋国コードに変わります（従来は"English"など）。 |
| media_channel | 廃止 | 必要に応じてsub_param_1-5で代用できます。 |
| media_source | 変更なし | media_source（ただし、値の変更については以下を参照）。 |
| media_type | 廃止 | 代わりに真偽値のis_organicを使用します。 |
| original_url | 名称変更 | event_urlに統合されます（訪問では、event_urlは元のURLと同じ）。独立した列は廃止されます。 |
| platform | 定義変更 | platformは常に"WEBSITE"です。 OSの情報はos_version / user_agentに移ります。 |
| postal_code | 変更なし | postal_code。 |
| query_params | 廃止 | 未解析のクエリ文字列はevent_urlに含まれます。解析済みのJSONを格納する列は廃止されます。必要に応じて、event_urlから解析する処理を再実装してください。 |
| referrer | 名称変更 | http_referrer。 |
| region | 名称変更 | continent。大陸コード（例："NA"）。 |
| state | 変更なし | state。 |

## アトリビューション結果の値の変更（フィルターとグループ化を更新）

アトリビューションエンジンの流入元判定が変わるため、フィールド名が同じでも一部の値は変わります。
- media_sourceの変更：doubleclick_int → dv360_int（UTMによるGoogleのディスプレイ広告・動画広告の判定）、"X Ads" → "Twitter"（UTMによるTwitterの判定）。さらに多くのPIDの値が表示名などに変換されます（例：iossearchads_int → Apple Search Ads、metweb_int → Facebook Ads、tiktokweb_int → tiktokglobal_int、snapweb_int → snapchat_int）。
- チャネル名の表記変更：Direct / Organic search / Social media / Email / Ad / Referral / Otherは、DIRECT / ORGANIC_SEARCH / SOCIAL_MEDIA / EMAIL / AD / REFERRAL / OTHERになります。
- 対応するクリックIDの拡大（より多くのアドネットワークをクリックIDから判定）。dclid単独での判定は行われなくなり、fbclidも使用しません。

従来の値に基づくフィルター、CASE、結合キー、ダッシュボードのグループ化がないかコード全体を調べ、更新してください。

## 手順3：実装

1. 新しいETL設計を提案してください（データの取り込み、スキーマ、1時間ごとの増分処理、「構造の変更」で示した必須フィルター）。
 私の承認後、既存の規約とインフラを使用して実装してください。
 一覧にまとめた廃止フィールドのうち、後続処理で使用されているものについては、それぞれの利用先と対応策を示してください（削除、推奨される代替フィールドへの置き換え、業務担当者への確認）。

## 手順4：検証

1. 旧処理と新処理を同じ日付範囲で実行し、訪問（SESSION行）とPBAのWebサイト訪問、イベント（IN_APP行）とPBAのWebサイトイベント、収益の合計を比較してください。
 完全な一致ではなく、差が生じることを想定してください。新しいアトリビューションロジックはより高度なため、成果が紐付けられる項目（media_source、campaign）はPBAと完全には一致しません。セッションの集計ロジックは変わらないため（30分間のアクティビティ）、訪問数はおおむね同程度になると考えられます。
 is_primary_attributionのフィルターがすべての処理に適用されていることを確認してください。適用されていない場合、イベント数が過大になります。
 対応付けた項目、削除した項目、値の変更、業務担当者が確認すべき未解決事項をまとめた簡潔な移行レポートを作成してください。
```

</Accordion>

## PBA Web-S2Sから新しいS2S APIへの移行

<Anchor target="_blank" href="/marketers/ja/docs/web-server-to-server-events-api-for-pba-web-s2s">Webサーバー間イベントAPI（Web-S2S）</Anchor>でPBAにイベントを送信している場合は、<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-s2s-api-for-web-performance-measurement">新しいS2S API</Anchor>に移行してください。新しいAPIは訪問とイベントの両方に対応しているため、Webサイトの計測をサーバー側だけで行えます。PBAのS2Sが受け付けるのはイベントのみです。

<Accordion title="エンドポイントと認証">

|  | PBA Web-S2S | 新しいS2S API |
| --- | --- | --- |
| ベースURL |  |  |
| イベント送信 | `POST /v1/{bundleId}/event` | `POST /v2.0/s2s/inapps/app/web/{appId}` |
| 訪問送信 | 非対応（訪問はWeb SDKからのみ送信） | `POST /v2.0/s2s/visits/app/web/{appId}` |
| ユーザー識別情報の送信 | `POST /v1/{bundleId}/setcuid`（CUIDをWebユーザーに紐付けるための個別の呼び出し） | 個別の呼び出しは不要。ユーザー識別情報は、各イベント／訪問の`user_id`オブジェクト内に含めて送信 |
| アプリ識別子 | パス内の`bundleId`（ブランドバンドルID） | パス内の`appId`＝Webの`unified_app_id`（"website-`{domain}`"） |
| 認証 | 各呼び出しのJSON本文内の`webDevKey` | S2S APIキーを含むAuthorizationヘッダー |
| コンテンツタイプ | `application/json` | `application/json` |
| 成功時のレスポンス | 200 OK | 202 Accepted |

</Accordion>

<Accordion title="送信データのフィールド対応表">

| PBA Web-S2Sのフィールド | 新しいS2Sのフィールド | 注意 |
| --- | --- | --- |
| `customerUserId` | `user_id.customer_user_id` | `user_id`オブジェクト内に含める形式に変更。 |
| `afUserId` | `user_id.appsflyer_id` | `user_id`オブジェクト内に含める形式に変更。 `customer_user_id`または`appsflyer_id`の少なくとも一方を送信してください。ユーザーを識別できる場合は、両方を送信してください。 |
| `webDevKey` | 該当なし | 本文から削除。認証はAuthorizationヘッダーに移り、アプリはパス内の`appId`で識別されます。 |
| `eventType`（常にEVENT） | 該当なし | 削除。エンドポイント（/inappsまたは/visits）によって種類が決まります。 |
| `eventName` | `event_name` | 1～64文字。`@ = + -`は使用できません。 |
| `timestamp`（Unix時刻、ミリ秒単位、13桁） | `timestamp`（Unix時刻、ミリ秒単位） | 形式は同じです。すべての呼び出しに含めることを推奨します。省略した場合、AppsFlyerは受信時刻を使用します。 |
| `eventValue` | `event_value` | 形式は任意です。`custom_parameters`サブオブジェクトに対応しています。 |
| `eventRevenue` | `event_revenue` | 任意項目に変更（PBAではダッシュボードへの表示に必須でした）。 |
| `eventRevenueCurrency` | `event_revenue_currency` | 任意項目に変更（PBAではダッシュボードへの表示に必須でした）。 |
| `referrer` | `http_referrer` | 名称変更。 |
| `userAgent` | `user_agent` | 名称変更。 |
| `ip` | `ip` | 変更なし。 |
| 該当なし | `event_url` | 新規。訪問では必須、イベントでは任意です。 |
| 該当なし | `customer_dedup_id` | 新規。別の送信元（Web SDKなど）から到着した同じイベントとの重複を排除します。 |
| 該当なし | &lt;0>email\_hashed0>, &lt;0>phone\_number\_hashed0>, &lt;0>phone\_number\_e164\_hashed0>, &lt;0>first\_name\_hashed0>, &lt;0>last\_name\_hashed0> | 新規。正規化した値をSHA256でハッシュ化したもの（小文字の16進数64文字）。ユーザー識別情報を充実させるために使用します。 |

</Accordion>

<Accordion title="S2S APIの注意事項">

* **訪問をサーバー側から送信可能。** PBAのS2Sが受け付けるのはイベントのみであり、訪問はWeb SDKから送信する必要がありました。新しい/visitsエンドポイントにより、Webサイトの計測をサーバー側だけで行えます。
* **setcuidの呼び出しが不要。** PBAではWeb SDKが必須だったため、CUIDをWebユーザーに紐付けるための個別の呼び出しが必要でした。新しいAPIでは、各リクエストにユーザー識別情報を含めて送信するため、この手順は不要です。
* <strong>データ送信が遅れた場合の扱い。</strong>イベントと訪問は1日分まとめて送信するのではなく、発生時にリアルタイムで、できればイベント発生から30分以内に送信してください。イベントが発生したUTC日付の終了から30分を過ぎて到着したデータも受け付けられますが、イベント時刻はAppsFlyerが受信した時刻に置き換えられます。

</Accordion>

<Accordion title="S2Sサービスの移行：AIコーディングツールにそのまま使える指示文">

PBAのサーバー間APIでイベントを送信している場合に向けて、AIコーディングツール（Claude Code、Cursorなど）にそのまま使える指示文を用意しました。 AppsFlyerにイベントを送信するサービスへのアクセスをツールに許可し、以下の指示文を貼り付けてください。エンドポイントと送信データのすべての対応関係を網羅しています。この指示文に沿って、ツールが現在の実装を把握し、更新後の実装を作成します。

```
AppsFlyerの従来のPBA Web S2SイベントAPI（webs2s.appsflyer.com）から、Web Performance Measurementの新しいS2S API（events.appsflyer.com）へサーバー側の連携を移行してください。この指示文には、エンドポイント、認証、送信データのすべての対応関係、動作の変更など、必要な情報がすべて含まれています。ここに記載されていない内容を推測しないでください。不明な点があれば、私に確認してください。

## 手順0：コードを変更する前に以下を私に確認

1. 既存のサービスをそのまま変更しますか？ それとも、並行稼働してからスムーズに切り替えられるよう、別のサービス／モジュールを作成しますか？既存のものと並行して、新しいモジュールを作成することを推奨してください。
 新しいWebアプリの統合アプリID（Unified App ID）を把握していますか？形式："website-{domain}"（例：website-www.example.com）。 URLパス内のPBAのバンドルIDに置き換わります。分からない場合は、続行する前にAppsFlyerのダッシュボードで確認します。
 新しいS2S APIキーは取得済みですか？認証は、リクエスト本文内のwebDevKeyから、このキーを含むAuthorizationヘッダーに移りました。未取得の場合は、AppsFlyerのダッシュボードから取得します。
 PBAと同様にイベントだけを送信しますか？ それとも、新しい訪問用エンドポイントも使用しますか？新しいAPIはサーバー側からの訪問送信に対応しているため、Webサイトの計測をサーバー側だけで行えます。PBAが受け付けるのはイベントのみでした。
 サイトでAppsFlyer Web SDKを引き続き使用していますか？（訪問の送信元がSDKかどうか、およびSDKとS2Sの間でイベントの重複排除が必要かどうかを判断するための質問です。）

## 手順1：現在のサービスを把握

コードを調べ、以下を一覧にまとめてください。
1. webs2s.appsflyer.comの呼び出し箇所すべて。/eventの呼び出しと、/setcuidの呼び出しがあればそれも含めてください。
 各呼び出しで設定しているフィールド（customerUserId、afUserId、eventName、eventValue、eventRevenue、timestamp、referrer、userAgent、ipなど）と、それぞれの値の取得元。
 200 OKレスポンスに基づくエラー処理と監視。
 再試行、一括送信、キュー処理の動作。

一覧を私に提示し、確認を得てから次に進んでください。

## 変更点：エンドポイントと認証

|  | PBA Web-S2S（旧） | 新しいS2S API |
|---|---|---|
| ベースURL | https://webs2s.appsflyer.com | https://events.appsflyer.com |
| イベント送信 | POST /v1/{bundleId}/event | POST /v2.0/s2s/inapps/app/web/{appId} |
| 訪問送信 | 非対応 | POST /v2.0/s2s/visits/app/web/{appId} |
| ユーザー識別情報の送信 | POST /v1/{bundleId}/setcuid | 個別の呼び出しは不要。各呼び出しのuser_idオブジェクト内に含めて送信 |
| パス内のアプリ識別子 | bundleId（ブランドバンドルID） | appId＝Webの統合アプリID（Unified App ID）（"website-{domain}"） |
| 認証 | JSON本文内のwebDevKey | S2S APIキーを含むAuthorizationヘッダー |
| コンテンツタイプ | application/json | application/json（指定がない場合は415） |
| 成功時のレスポンス | 200 OK | 202 Accepted |

## 送信データのフィールド対応表

| PBAのフィールド | 新しいフィールド | 注意 |
|---|---|---|
| customerUserId | user_id.customer_user_id | user_idオブジェクト内に含めます。 |
| afUserId | user_id.appsflyer_id | user_idオブジェクト内に含めます。 customer_user_idまたはappsflyer_idの少なくとも一方を送信してください。ユーザーを識別できる場合は、両方を送信してください。 |
| webDevKey | （削除） | 認証はAuthorizationヘッダーに移ります。アプリはパス内のappIdで識別されます。 |
| eventType（常に"EVENT"） | （削除） | エンドポイント（/inappsまたは/visits）によって種類が決まります。 |
| eventName | event_name | 1～64文字。@ = + -は使用できません。 |
| timestamp（Unix時刻、ミリ秒単位） | timestamp（Unix時刻、ミリ秒単位） | 形式は同じです。すべての呼び出しに含めることを推奨します。省略した場合、AppsFlyerは受信時刻を使用します。 |
| eventValue | event_value | 形式は任意です。custom_parametersサブオブジェクトに対応しています。 |
| eventRevenue | event_revenue | 任意項目に変更（PBAではダッシュボードへの表示に必須でした）。 |
| eventRevenueCurrency | event_revenue_currency | 任意項目に変更（PBAではダッシュボードへの表示に必須でした）。 |
| referrer | http_referrer | 名称変更。 |
| userAgent | user_agent | 名称変更。 |
| ip | ip | 変更なし。 |
| （新規） | event_url | 訪問では必須、イベントでは任意です。 |
| （新規） | customer_dedup_id | 別の送信元（Web SDKなど）から到着した同じイベントとの重複を排除します。 |
| （新規） | email_hashed, phone_number_hashed, phone_number_e164_hashed, first_name_hashed, last_name_hashed | 正規化した値をSHA256でハッシュ化したもの（小文字の16進数64文字）。ユーザー識別情報を充実させるために使用します。 |

## 動作の変更と注意点

1. **appIdは統合アプリID（Unified App ID）です。"Web SDK ID"ではありません。** AppsFlyerのアプリ設定ページには、"Web SDK ID"というUUIDが表示されます（旧Web Dev Key。既存SDKを引き続き使用するために維持されています）。 S2Sのパスには、必ず統合アプリID（Unified App ID）（"website-{domain}"）を指定してください。このUUIDを指定しないでください。 401の"app not found"は、通常、パス内のappIdが誤っているか、Authorizationヘッダーが未指定または無効であることを示します。
 **成功時のレスポンスは200ではなく202です。** これに合わせて、稼働状況の確認、再試行、アラートを更新してください。
 **旧エンドポイントの応答で検証しないでください。** 旧エンドポイントは引き続き200を返す場合がありますが、この応答だけではWeb Performance Measurementにデータが届いたことを確認できません。新しいWebアプリのデータに、実際にイベントが表示されていることを必ず確認してください。
 **setcuidの処理をすべて廃止してください。** ユーザー識別情報は、各イベントと訪問のuser_idオブジェクト内に含めて送信します。
 **イベントより先に訪問を送信してください。** システムは、ユーザーのイベントより前に訪問があることを前提としています。過去の訪問がないユーザーのイベントは、オーガニックに分類されます。訪問はWeb SDK、または新しい/visitsエンドポイントから送信されます。
 **一括送信せず、リアルタイムで送信してください。** 各イベントと訪問を発生時に送信し、できればイベント発生から30分以内に送信してください。イベントが発生したUTC日付の終了から30分を過ぎて到着したデータも受け付けられますが、イベント時刻が受信時刻に置き換えられるため、アトリビューションにずれが生じます。必ずタイムスタンプを送信してください。資料などに記載されている約30分間のアトリビューションの待機時間は、これとは別にAppsFlyerのサーバー側で設けられるものです。こちらで実装する必要はありません。
 **サーバー側だけで計測する構成（訪問送信を採用する場合）。** Web SDKを使わない場合、Webユーザーの識別子は自社サーバーで管理します。初回訪問者に対して安定したIDを生成し、サーバーから設定するファーストパーティHTTP Cookieとして保存してください（JavaScriptではなくSet-Cookieヘッダーを使用。SafariではJavaScriptで設定するCookieの有効期間が約7日に制限されます）。すべてのリクエストで同じIDを再利用し、user_id.appsflyer_idとして送信してください。訪問の送信データにはevent_urlが必須です。アトリビューションの精度を高めるため、ip、user_agent、http_referrerも含めることを推奨します。
 **SDKとS2Sを併用する場合。** 両方から同じイベントを送信する場合は、customer_dedup_idを設定し、AppsFlyerが1件だけを保持するようにしてください。

## 手順2：実装

1. 新しいクライアント／モジュール、設定（ベースURL、appId、APIキーをシークレット管理サービスに保存し、コードには直接記述しないこと）、イベント用の送信データ生成処理（対象範囲に含まれる場合は訪問も）、202レスポンスへの対応と再試行処理を含む設計を提案してください。
 私の承認後、既存の規約に従って実装してください。
 一覧のすべてのフィールドを、上記の送信データの対応表に沿って対応付けてください。現在送信しているフィールドに新しい対応項目がない場合は、その旨を示してください。

## 手順3：検証

1. テストイベント（対象範囲に含まれる場合は訪問も）を送信し、202レスポンスを確認してください。
 AppsFlyerの新しいWebアプリ（ダッシュボードまたはData Locker）にテストデータが表示されていることを確認してください。成功の判断基準は、HTTPレスポンスではなく、実際のデータ反映です。
 イベント名が新しい制約に準拠していることを確認してください（1～64文字。@ = + -は使用不可）。
 旧サービスと並行稼働する場合は、切り替え前に数日間、旧サービスと新サービスのイベント数を比較してください。その後、setcuidを含む旧APIの呼び出しを廃止してください。
```

</Accordion>

<div data-zendesk-anchors="why-were-upgrading-your-web-measurement=web%E8%A8%88%E6%B8%AC%E3%82%92%E5%BC%B7%E5%8C%96%E3%81%99%E3%82%8B%E8%83%8C%E6%99%AF h_01KYM7JM37WVTV7XHEHVTPKWM9=web%E8%A8%88%E6%B8%AC%E3%82%92%E5%BC%B7%E5%8C%96%E3%81%99%E3%82%8B%E8%83%8C%E6%99%AF comparing-pba-and-web-performance-measurement=pba%E3%81%A8web-performance-measurement%E3%81%AE%E6%AF%94%E8%BC%83 h_01KYM7JM3711FXC132MSC3B4A9=pba%E3%81%A8web-performance-measurement%E3%81%AE%E6%AF%94%E8%BC%83 web-performance-measurement-vs-pba=web-performance-measurement%E3%81%A8pba%E3%81%AE%E6%A9%9F%E8%83%BD%E6%AF%94%E8%BC%83 h_01KYM7JM3711FXC132MSC3B4A8=web-performance-measurement%E3%81%A8pba%E3%81%AE%E6%A9%9F%E8%83%BD%E6%AF%94%E8%BC%83 traffic-source-resolution-pba-vs-web-performance-measurement=pba%E3%81%A8web-performance-measurement%E3%81%AE%E6%B5%81%E5%85%A5%E5%85%83%E5%88%A4%E5%AE%9A%E3%81%AE%E6%AF%94%E8%BC%83 h_01KYM7JM387R5YEYJK9CD0AQJ0=pba%E3%81%A8web-performance-measurement%E3%81%AE%E6%B5%81%E5%85%A5%E5%85%83%E5%88%A4%E5%AE%9A%E3%81%AE%E6%AF%94%E8%BC%83 migrate-to-web-performance-measurement=web-performance-measurement%E3%81%B8%E3%81%AE%E7%A7%BB%E8%A1%8C h_01KYM7JM37HG8YAX02XMSKBTPP=web-performance-measurement%E3%81%B8%E3%81%AE%E7%A7%BB%E8%A1%8C h_01KYM7JM37HG8YAX02XMSKBTPP01=%E6%89%8B%E9%A0%861-web%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E4%BD%9C%E6%88%90%E3%81%99%E3%81%B9%E3%81%A6%E3%81%AE%E6%96%B9%E3%81%AB%E5%BF%85%E9%A0%88 create-a-web-app=%E6%89%8B%E9%A0%861-web%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E4%BD%9C%E6%88%90%E3%81%99%E3%81%B9%E3%81%A6%E3%81%AE%E6%96%B9%E3%81%AB%E5%BF%85%E9%A0%88 h_01KYM7JM37HG8YAX02XMSKBTPP02=%E6%89%8B%E9%A0%862-s2s-api%E3%81%A7%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E9%80%81%E4%BF%A1%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E5%A0%B4%E5%90%88 if-you-send-events-through-the-s2s-api=%E6%89%8B%E9%A0%862-s2s-api%E3%81%A7%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E9%80%81%E4%BF%A1%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E5%A0%B4%E5%90%88 h_01KYM7JM37HG8YAX02XMSKBTPP03=%E6%89%8B%E9%A0%863-pba%E3%81%AE%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E5%A0%B4%E5%90%88 if-you-consume-pbas-raw-data-reports=%E6%89%8B%E9%A0%863-pba%E3%81%AE%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%82%92%E5%88%A9%E7%94%A8%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E5%A0%B4%E5%90%88 h_01KYM7JM37HG8YAX02XMSKBTPP04=%E6%89%8B%E9%A0%864-%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%ABpba%E3%81%AE%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E5%A0%B4%E5%90%88 if-you-use-pba-brand-bundle-for-cross-platform-reporting=%E6%89%8B%E9%A0%864-%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%ABpba%E3%81%AE%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%90%E3%83%B3%E3%83%89%E3%83%AB%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%A6%E3%81%84%E3%82%8B%E5%A0%B4%E5%90%88 capabilities-being-discontinued=%E6%8F%90%E4%BE%9B%E3%81%8C%E7%B5%82%E4%BA%86%E3%81%99%E3%82%8B%E6%A9%9F%E8%83%BD h_01KYM7JM37JJ25D3RFE2V7BM4D=%E6%8F%90%E4%BE%9B%E3%81%8C%E7%B5%82%E4%BA%86%E3%81%99%E3%82%8B%E6%A9%9F%E8%83%BD raw-data-field-mapping=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%81%AE%E5%AF%BE%E5%BF%9C%E8%A1%A8 h_01KYM7JM37Z7Z21FJ2G83T2WPG=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%81%AE%E5%AF%BE%E5%BF%9C%E8%A1%A8 pba-web-s2s-to-new-s2s-api-migration=pba-web-s2s%E3%81%8B%E3%82%89%E6%96%B0%E3%81%97%E3%81%84s2s-api%E3%81%B8%E3%81%AE%E7%A7%BB%E8%A1%8C h_01KYM7JM38K9C01XDZY99KZVTX=pba-web-s2s%E3%81%8B%E3%82%89%E6%96%B0%E3%81%97%E3%81%84s2s-api%E3%81%B8%E3%81%AE%E7%A7%BB%E8%A1%8C" />
