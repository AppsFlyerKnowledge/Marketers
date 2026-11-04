---
title: Creative Optimization｜ETLレポート
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-10-10T14:33:17Z'
  edited_at: '2026-10-28T08:56:00Z'
  id: 19253873174801
  locale: ja
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/ja/articles/19253873174801
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** Creative Optimization ETLは、クリエイティブのパフォーマンスデータを毎日クラウドストレージへ配信し、手動でエクスポートすることなく、ビジネスインテリジェンス（BI）システムへ直接取り込めるようにします。固定されたレポート構成を提供する**標準クリエイティブETL**と、含めるディメンション、指標、イベントを自由に選択できる**カスタムクリエイティブETL**の2種類から選択できます。

<div id="about-creative-optimization-etl-reporting" />

## Creative Optimization ETLレポートについて

Creative Optimization ETLは、クリエイティブのパフォーマンスデータを毎日クラウドストレージへ自動的に配信し、BIシステムからプログラムによって取り込めるようにします。ニーズやご契約プランに応じて、2つのオプションを利用できます。

**標準クリエイティブETL**はData Lockerから設定し、主要なクリエイティブディメンションとパフォーマンス指標を含む、固定形式の日次レポートを提供します。すべてのCreative Optimizationのお客様が利用できます。

**カスタムクリエイティブETL**では、レポートのスキーマ（レポートを構成するディメンション、指標、イベント、およびそれらの表示順）を自由に設定できます。 Creative ETLのUIでレポート構成を直接設定し、リターゲティングや統合アトリビューションの内訳も含め、必要なディメンション、指標、AIディメンション、アプリ内イベントを選択できます。 Creative Optimization Premiumプランをご契約のお客様が利用できます。

<div id="standard-creative-etl" />

<Accordion title="標準クリエイティブETL">

Creative Optimization ETLは、データアナリストがクリエイティブのパフォーマンス分析に必要な情報を提供します。 Creative Optimizationのレポートデータをクラウドストレージへ自動的に配信し、BIシステムからプログラムによって取り込めるようにします。

主要なパフォーマンス指標（KPI）、ファネル上部・下部のKPI、アトリビューションデータ、クリエイティブアセットデータを含む、アセット単位の包括的なパフォーマンスレポートを利用できます。

標準クリエイティブETLでは、Data Lockerを使用してレポートデータをクラウドストレージへ送信します。保存先として、Amazon Web Services（AWS）上のAppsFlyerが所有するバケットのほか、お客様自身のAWS、Google Cloud Storage（GCS）、Yandex、BigQuery、Snowflakeなど、さまざまなストレージを選択できます。 Data Lockerは複数の保存先に対応しているため、すべてのデータを1つまたは複数の保存先へ送信したり、特定のデータを特定の保存先へ振り分けたりするなど、ニーズに合わせて配信方法をカスタマイズできます。

<div id="note" />

> 📘 **注意**
>
> 標準クリエイティブETLのスキーマは固定されており、アプリ内イベント、AIディメンション、リターゲティング／統合アトリビューションの内訳には対応していません。スキーマを自由にカスタマイズしたい場合は、以下の[カスタムクリエイティブETL](#custom-creative-etl)を参照してください。

<div id="get-started" />

#### まずはじめに

このセクションでは、Creative Optimizationレポート向けにData Lockerを設定する方法について説明します。

**前提条件**

* Creative Optimization Premiumの契約（AppsFlyerのカスタマーサクセスマネージャーにお問い合わせください）

**Data Lockerを設定するには：**

1. <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup">Data Lockerの設定手順</Anchor>に従います。
2. Data Lockerの設定時に、Data Locker設定ページの**レポートを選択**で**Creative Optimization**を選択します。

<div id="edit-data-locker-configuration" />

#### Data Locker設定を編集する

このセクションでは、既存のData Locker設定にCreative Optimizationレポートを追加する方法について説明します。

**Data LockerにCreative Optimizationレポートを追加するには：**

1. AppsFlyerで、**レポート出力** > **Data Locker**に移動します。
2. Data Locker設定ページの**レポートを選択**で、**Creative Optimization**を選択します。

<div id="data-freshness" />

#### データの更新頻度

設定後、Creative Optimizationレポートは1日1回Data Lockerへ配信されます。各配信には過去30日分のデータが含まれ、毎日UTC＋12に配信されます。実際の現地時刻はタイムゾーンによって異なります。

* ニューヨーク：UTC+12 − 5 ＝午前7:00
* ベルリン：UTC+12 ＋ 1 ＝午後1:00
* 上海：UTC＋12＋8＝午後8:00

<div id="available-data" />

#### 利用可能なデータ

Data Lockerでは、以下のクリエイティブデータを利用できます。

| フィールド | データの型 |
| --- | --- |
| date | String |
| asset\_link | String |
| creative | String |
| media\_source | String |
| campaign | String |
| campaign\_id | String |
| ad | String |
| ad\_id | String |
| adset | String |
| adset\_id | String |
| app\_name | String |
| app\_id | String |
| creative\_first\_seen | String |
| creative\_age | String |
| creative\_type | String |
| duration | String |
| end\_card\_type | String |
| geo | String |
| platform | String |
| orientation | String |
| resolution | String |
| impressions | String |
| clicks | String |
| installs | String |
| ctr | String |
| cvr | String |
| ipm | String |
| cost | String |
| ecpi | String |
| reattributions | String |
| reengagements | String |
| cpm | String |
| roas\_d1 | String |
| roas\_d7 | String |
| roas\_d14 | String |
| roas\_d30 | String |
| roas\_d60 | String |
| roas\_d90 | String |
| retention\_d1 | String |
| retention\_d7 | String |
| retention\_d14 | String |
| retention\_d30 | String |
| retention\_d60 | String |
| retention\_d90 | String |
| revenue\_d1 | String |
| revenue\_d7 | String |
| revenue\_d14 | String |
| revenue\_d30 | String |
| revenue\_d60 | String |
| revenue\_d90 | String |
| partner\_cpm | String |
| partner\_ctr | String |
| partner\_cvr | String |
| partner\_clicks | String |
| partner\_cost | String |
| partner\_ipm | String |
| partner\_impressions | String |
| partner\_installs | String |
| partner\_ecpi | String |

標準指標およびCreative Optimization固有の指標については、<Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-guide#standard-metrics-and-dimensions">標準指標とCreative Optimization固有の指標の定義</Anchor>を参照してください。

<div id="note-1" />

> 📘 **注意**
>
> 広告のプレビューを利用できない場合、`asset_link`および`creative`カラムには値が入力されません。

標準クリエイティブETLでは、以下のデータは**利用できません。**

* カスタムディメンション
* カスタム指標
* アプリ内イベント
* AIデータ(要素およびシーン)
* リターゲティングデータ

</Accordion>

<div id="custom-creative-etl" />

<Accordion title="カスタムクリエイティブETL">

カスタムクリエイティブETLでは、レポートのスキーマを自由に設定できます。 Creative ETLのUIから直接レポートを設定し、ディメンション、指標、AIディメンション、アトリビューションタイプ別の内訳、アプリ内イベントを選択できます。データは毎日Data Lockerの保存先へ配信されます。

固定スキーマを使用する標準クリエイティブETLとは異なり、カスタムクリエイティブETLでは、必要な形式に合わせてレポートを柔軟に構成できます。

* **アプリ内イベントの詳細データ**：1つのレポートにつき最大30件のアプリ内イベントを追加でき、イベント数、ユニークユーザー数、収益、アクション単価（CPA）の各サブ指標も含められます。
* **アトリビューションタイプ別の内訳**－ユーザー獲得、リターゲティング、または両者を組み合わせた統合ビューでレポートできます。
* **AIディメンション**：標準のパフォーマンスデータとあわせて、AIが生成したクリエイティブタグ（自動タグおよびカスタムディメンション）を含められます。
* **セルフサービスでの設定**：バックエンドでの設定やカスタマーサクセスマネージャーへの依頼は不要で、Creative ETLのUIから直接レポートの作成、編集、管理を行えます。

<div id="before-you-begin" />

#### 始める前に

カスタムクリエイティブETLを設定する前に、以下の条件を満たしていることを確認してください。

* <strong>Creative Optimization Premiumの契約。</strong>カスタムクリエイティブETLは、Premiumプランでのみ利用できます。契約内容については、AppsFlyerの担当者にお問い合わせください。
* **管理者権限。** ETLレポート設定の作成・編集・削除を行えるのは、管理者ユーザーのみです。
* <strong>Data Lockerの保存先。</strong>カスタムクリエイティブETLは、Data Lockerの接続先へデータを配信します。少なくとも1つの接続先があらかじめ設定されている必要があります。または、レポート設定時に新しく作成することもできます（以下のステップ1を参照）。対応する保存先には、AWS S3、GCS、BigQuery、Snowflake、Azure Blob［ベータ］、Yandex［ベータ］があります。 <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup">Data Locker接続の設定を参照してください。</Anchor>

<div id="set-up-custom-creative-etl" />

#### カスタムクリエイティブETLを設定する

カスタムクリエイティブETLの設定は、データの保存先を設定し、レポートの詳細を定義し、スキーマ（レポート出力に含まれるカラム）を選択する、3つのステップで行います。

**カスタムクリエイティブETLを設定するには：**

1. AppsFlyerで、**レポート出力** > **Creative ETL**に移動します。
2. **レポートの作成**をクリックします。

<div id="step-1---destination" />

##### ステップ1：保存先

レポートの配信先となるData Locker接続を選択または設定します。

3. **Data Locker接続**ドロップダウンで、既存の接続を選択します。
   * 接続がまだない場合は、**＋ Data Lockerで新しい接続を作成**をクリックします。 Data Lockerの設定ページが開きます。接続を作成したらCreative ETLに戻り、ドロップダウンから選択します。
   * 同じレポートを複数の保存先に配信する場合は、複数の接続を選択できます。
4. **次へ**をクリックします。

<div id="step-2---details" />

##### ステップ2：詳細

レポート名とレポートタイプを設定します。

5. **レポート名**を入力します。この名前はレポート一覧でレポートを識別するために使用され、保存後は変更できません。

   <div id="note-2" />

   > 📘 **注意**
   >
   > 使用できるのは英字、数字、アンダースコアのみです。 2〜80文字で入力してください。

6. **レポートタイプ**を選択します：

| レポートタイプ | 説明 |
| --- | --- |
| ユーザー獲得 | 有料メディアにアトリビューションされた新規ユーザーのインストール |
| リターゲティング | リエンゲージメントおよびリアトリビューションのアクティビティ |
| 統合 | ユーザー獲得とリターゲティングを1つのレポートにまとめた統合ビュー |

7. **次へ**をクリックします。

<div id="step-3---schema" />

##### ステップ3：スキーマ

レポート出力に含めるディメンション、指標、AIディメンション、アプリ内イベントを選択します。

<div id="what-is-a-schema" />

> 📘 **スキーマとは**
>
> スキーマは、レポートに含まれるカラムを定義するものです。キャンペーン、地域、クリエイティブタイプなどのディメンションと、インストール、CTR、ROASなどのパフォーマンス指標のうち、どれを含めるか、またどの順番で表示するかを指定します。 UIでフィールドを選択した順番が、出力ファイルのカラム順になります。

9. **ディメンション**で、含めるクリエイティブおよびキャンペーンのディメンションを選択します。

   <div id="note-3" />

   > 📘 **注意**
   >
   > （イベントのアトリビューション日）、**アプリID**、**クリエイティブ**、**アセットリンク**の各フィールドは必須で、削除できません。また、`dt`（パーティション日）と`version`（バックフィル時の実行バージョン）の2項目もすべてのレポートに必ず含まれますが、UI上には表示されません。

10. **AIディメンション**で、含める自動タグまたはカスタムディメンションのフィールドを選択します。これらのフィールドは、AppsFlyerのAIクリエイティブ分析パイプラインによって生成されます。

    <div id="note-4" />

    > 📘 **注意**
    >
    > AIディメンションに値が入るのは、AIタグ付けパイプラインで処理済みのクリエイティブのみです。最近アップロードされたクリエイティブでは、AIタグが利用可能になるまで時間がかかる場合があります。

11. **指標**で、含めるパフォーマンスKPIを選択します。
12. **アプリ内イベント**で、含めるイベントを選択します。選択した各イベントには、イベント数、ユニークユーザー数、収益、CPAの4つのサブ指標が自動的にレポート出力へ追加されます。

    <div id="important" />

    > 🚧 **重要**
    >
    > 1つのレポートに含められるのは、最大**30件のアプリ内イベント**です。

13. **保存**をクリックしてレポートを有効化します。

これでレポートの設定は完了です。初回の配信は、次回の日次実行時に行われます。

<div id="edit-an-existing-report" />

#### 既存のレポートを編集する

既存のカスタムクリエイティブETLレポートは、スキーマ、レポートタイプ、データ接続先などを変更できます。レポート名は、保存後に変更することはできません。

**レポートの編集：**

1. AppsFlyerで、**レポート出力** > **Creative ETL**に移動します。
2. レポート一覧で、変更するレポートの**編集**（鉛筆）アイコンをクリックします。
3. 3つの設定ステップで必要な変更を行います。
4. **変更を保存**をクリックします。

<div id="note-5" />

> 📘 **注意**
>
> スキーマの変更は、今後実行されるレポートにのみ適用されます。すでに配信済みのファイルがさかのぼって更新されることはありません。
>
> **イベント日**、**アプリID**、**アセットリンク**、**クリエイティブ**の各ディメンションは必須で、削除できません。

各行のアクションアイコンから、レポートを**複製**または**削除**することもできます。

<div id="important-1" />

> 🚧 **重要**
>
> レポートを削除すると、レポート設定と関連するすべての実行履歴が完全に削除されます。この操作は取り消せません。

<div id="report-management" />

#### レポート管理

Creative ETLページには、アカウントに設定されているすべてのカスタムクリエイティブETLレポートが表示されます。各レポートでは、レポート名、レポートタイプ、直近で正常に配信された日時を確認できます。

各レポート行のアクションアイコンから、以下の操作を行えます。

* **表示**（目のアイコン）：レポート設定全体を読み取り専用で表示します。
* **編集**（鉛筆アイコン）：レポートを編集モードで開きます。
* **複製**（コピーアイコン）：レポート設定のコピーを作成します。
* **削除**（ゴミ箱アイコン）：レポートとその実行履歴を完全に削除します。

<div id="note-6" />

> 📘 **注意**
>
> 1つのアカウントで**有効化できるカスタムクリエイティブETLレポートは、最大5件**です。

Data Locker経由で標準クリエイティブETLレポートを設定している場合、Creative ETLページの上部に通知バナーが表示されます。このバナーをクリックすると、Standardレポートを設定しているData Lockerへ移動します。

<div id="data-delivery" />

#### データ配信

**配信スケジュール**

カスタムクリエイティブETLレポートは1日1回配信されます。配信状況を確認するには、Creative ETLのレポート一覧で**最終配信成功日時**を確認してください。

**ルックバック期間**

各日次配信には、過去30日間のルックバック期間のデータが含まれます。各ファイルには、直近1日分だけでなく、更新される対象期間全体のデータが含まれます。 BIシステムへデータを取り込む際は、最新日の行のみを追記するのではなく、配信対象期間内のすべての日付のデータを置き換えてください。

**フォルダ構成**

データファイルは、Data Locker接続設定で選択した設定に基づいて、配信先フォルダ内に整理されます。

* **統合（デフォルト）：** すべてのアプリが統合されたデータファイルに含まれます。データを利用する際は、行単位の`app_id`フィールドを使用してアプリを識別してください。
* **アプリ別：** データはアプリごとに1つずつサブフォルダへ分けて保存されます。

詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#app-segregation">Data Lockerのアプリ別データ分割</Anchor>を参照してください。

<div id="schema-reference" />

#### スキーマのリファレンス

<div id="mandatory-fields" />

##### 必須フィールド

以下のフィールドは、すべてのカスタムクリエイティブETLレポートに必ず含まれ、削除できません。

| フィールド | データの型 | 説明 |
| --- | --- | --- |
| `event_date` | String | イベントまたはインストールがアトリビューションされた日付 |
| `app_id` | String | AppsFlyerアプリID |
| `creative` | String | クリエイティブ名 |
| `asset_link` | String | クリエイティブアセットのプレビューURL。プレビューが利用できない場合は値が入りません |
| `dt` | String（YYYY-MM-DD） | パーティション日。レポートデータがストレージに書き込まれた日付 |
| `version` | String | 実行バージョンの識別子。同じ`dt`に対してバックフィルを再実行した場合に値が増加します |

<div id="dimensions" />

##### ディメンション

以下のディメンションから、任意の組み合わせを選択してレポートに含めることができます。

| フィールド | データの型 | 説明 |
| --- | --- | --- |
| `app_name` | String | アプリ名 |
| `ad` | String | 広告名 |
| `ad_id` | String | 広告ID |
| `adset` | String | 広告セット名 |
| `adset_id` | String | 広告セットID |
| `agency` | String | 広告掲載を担当する代理店 |
| `campaign` | String | キャンペーン名 |
| `campaign_id` | String | キャンペーンID |
| `channel` | String | メディアソース階層内のチャネル |
| `creative_age` | String | クリエイティブが配信されている日数。AppsFlyerが最初のインプレッション、クリック、またはインストールを受信した時点から算出 |
| `creative_similarity` | String | 同じビジュアルテーマやコンセプトを持つ画像および動画クリエイティブをグループ化 |
| `creative_type` | String | アセットタイプ（例：画像、動画、プレイアブル） |
| `duration` | String | 動画の長さ（秒）（動画クリエイティブの場合） |
| `end_card` | String | エンドカード名 |
| `end_card_duration` | String | エンドカードの表示時間（秒） |
| `end_card_orientation` | String | エンドカードの向き（縦向きまたは横向き） |
| `end_card_resolution` | String | エンドカードの解像度 |
| `end_card_type` | String | エンドカードの種類 |
| `first_seen` | String | AppsFlyerがそのクリエイティブのパフォーマンスデータを初めて受信した日付 |
| `geo` | String（ISO 3166-1 alpha-2） | 国コード |
| `media_source` | String | メディアソース（アドネットワーク） |
| `orientation` | String | クリエイティブの向き（縦向きまたは横向き） |
| `platform` | String | デバイスプラットフォーム（iOSまたはAndroid） |
| `resolution` | String | クリエイティブの解像度 |
| `text_type` | String | クリエイティブのテキストタイプ分類 |

<div id="ai-dimensions" />

##### AIディメンション

AIディメンションは、AppsFlyerのAIクリエイティブ分析エンジンによって生成され、自動タグ、スマートタグ、カスタムディメンションが含まれます。

| グループ | フィールドのプレフィックス（先頭文字列） | 説明 |
| --- | --- | --- |
| 自動タグ | `at_` | クリエイティブ内の要素、シーン、感情、ストーリー上の特徴に対してAIが生成するタグ。利用可能なタグはアカウントごとに異なります |
| スマートタグ | `cd_ai_label` | AIが生成するスマートタグ |
| カスタムディメンション | `cd_` | アカウント向けに設定された、ユーザー定義のクリエイティブ属性 |

<div id="note-7" />

> 📘 **注意**
>
> AIディメンションに値が入るのは、AIタグ付けの工程で処理済みのクリエイティブのみです。新しくアップロードされたクリエイティブでは、AIタグがすぐに利用できない場合があります。

<div id="metrics" />

##### 指標

| フィールド | データの型 | 説明 |
| --- | --- | --- |
| `impressions` | Integer | 広告のインプレッション数 |
| `clicks` | Integer | 広告のクリック数 |
| `installs` | Integer | クリエイティブにアトリビューションされたインストール数 |
| `reattributions` | Integer | リアトリビューション数（リターゲティング） |
| `reengagements` | Integer | リエンゲージメント数（リターゲティング） |
| `cost` | Decimal | 広告費の合計 |
| `ctr` | Decimal | クリック率（クリック数/インプレッション数） |
| `cvr` | Decimal | コンバージョン率（インストール数/クリック数） |
| `ipm` | Decimal | IPM（1,000インプレッションあたりのインストール数） |
| `cpm` | Decimal | CPM（1,000インプレッションあたりのコスト） |
| `ecpi` | Decimal | 実効インストール単価 |
| `roas_d0` | Decimal | Day 0時点の広告費用対効果（ROAS） |
| `roas_d1` | Decimal | Day 1時点の広告費用対効果（ROAS） |
| `roas_d3` | Decimal | Day 3時点の広告費用対効果（ROAS） |
| `roas_d7` | Decimal | Day 7時点の広告費用対効果（ROAS） |
| `roas_d14` | Decimal | Day 14時点の広告費用対効果（ROAS） |
| `roas_d30` | Decimal | Day 30時点の広告費用対効果（ROAS） |
| `roas_d60` | Decimal | Day 60時点の広告費用対効果（ROAS） |
| `roas_d90` | Decimal | Day 90時点の広告費用対効果（ROAS） |
| `retention_d0` | Decimal | Day 0のリテンション率 |
| `retention_d1` | Decimal | Day 1のリテンション率 |
| `retention_d3` | Decimal | Day 3のリテンション率 |
| `retention_d7` | Decimal | Day 7のリテンション率 |
| `retention_d14` | Decimal | Day 14のリテンション率 |
| `retention_d30` | Decimal | Day 30のリテンション率 |
| `retention_d60` | Decimal | Day 60のリテンション率 |
| `retention_d90` | Decimal | Day 90のリテンション率 |
| `unique_users_0` | Integer | Day 0のユニークユーザー数 |
| `unique_users_1` | Integer | Day 1のユニークユーザー数 |
| `unique_users_3` | Integer | Day 3のユニークユーザー数 |
| `unique_users_7` | Integer | Day 7のユニークユーザー数 |
| `unique_users_14` | Integer | Day 14のユニークユーザー数 |
| `unique_users_30` | Integer | Day 30のユニークユーザー数 |
| `unique_users_60` | Integer | Day 60のユニークユーザー数 |
| `unique_users_90` | Integer | Day 90のユニークユーザー数 |
| `revenue_d0` | Decimal | Day 0時点の総収益 |
| `revenue_d1` | Decimal | Day 1時点の総収益 |
| `revenue_d3` | Decimal | Day 3時点の総収益 |
| `revenue_d7` | Decimal | Day 7時点の総収益 |
| `revenue_d14` | Decimal | Day 14時点の総収益 |
| `revenue_d30` | Decimal | Day 30時点の総収益 |
| `revenue_d60` | Decimal | Day 60時点の総収益 |
| `revenue_d90` | Decimal | Day 90時点の総収益 |
| `ad_revenue_d0` | Decimal | Day 0時点の広告収益 |
| `ad_revenue_d1` | Decimal | Day 1時点の広告収益 |
| `ad_revenue_d3` | Decimal | Day 3時点の広告収益 |
| `ad_revenue_d7` | Decimal | Day 7時点の広告収益 |
| `ad_revenue_d14` | Decimal | Day 14時点の広告収益 |
| `ad_revenue_d30` | Decimal | Day 30時点の広告収益 |
| `ad_revenue_d60` | Decimal | Day 60時点の広告収益 |
| `ad_revenue_d90` | Decimal | Day 90時点の広告収益 |
| `partner_impressions` | Integer | メディアソースからレポートされたインプレッション数 |
| `partner_clicks` | Integer | メディアソースからレポートされたクリック数 |
| `partner_installs` | Integer | メディアソースからレポートされたインストール数 |
| `partner_cost` | Decimal | メディアソースからレポートされたコスト |
| `partner_cpm` | Decimal | メディアソースからレポートされたCPM |
| `partner_ctr` | Decimal | メディアソースからレポートされたCTR |
| `partner_cvr` | Decimal | メディアソースからレポートされたCVR |
| `partner_ipm` | Decimal | メディアソースからレポートされたIPM |
| `partner_ecpi` | Decimal | メディアソースからレポートされたeCPI |
| `partner_video_viewed_2s` | Integer | 動画の2秒再生数（メディアソースからのレポート値） |
| `partner_video_viewed_3s` | Integer | 動画の3秒再生数（メディアソースからのレポート値） |
| `partner_video_viewed_6s` | Integer | 動画の6秒再生数（メディアソースからのレポート値） |
| `partner_engaged_views_6s` | Integer | 6秒時点のエンゲージドビュー数（メディアソースからのレポート値） |
| `partner_engaged_views_15s` | Integer | 15秒時点のエンゲージドビュー数（メディアソースからのレポート値） |
| `partner_video_started` | Integer | 動画の再生開始数（パートナーからのレポート値） |
| `partner_video_25p_views` | Integer | 動画を25%まで再生した回数（メディアソースからのレポート値） |
| `partner_video_50p_views` | Integer | 動画を50%まで再生した回数（メディアソースからのレポート値） |
| `partner_video_75p_views` | Integer | 動画を75%まで再生した回数（メディアソースからのレポート値） |
| `partner_video_completions` | Integer | 動画の完全再生数（パートナーからのレポート値） |

<div id="in-app-events" />

##### アプリ内イベント

アプリ内イベントは、`{event_name}.{sub_metric}`の形式で指標カラムとしてレポートに表示されます。イベントを選択すると、4つのサブ指標がすべて自動的に追加されます。たとえば、`af_purchase`を選択すると、`af_purchase.event_count`、`af_purchase.unique_users`、`af_purchase.revenue`、`af_purchase.cpa`のカラムが生成されます。

| サブ指標 | 説明 |
| --- | --- |
| `event_count` | イベントが発生した合計回数 |
| `unique_users` | イベントを発生させたユニークユーザー数 |
| `revenue` | イベントにアトリビューションされた総収益 |
| `cpa` | アクション単価（コスト/イベント数） |

制限：

* 1つのレポートに含められるアプリ内イベントは**最大30件**です。
* 利用可能なイベントはアカウントごとに異なり、アプリからAppsFlyerへ実際に送信されているイベントが表示されます。

<div id="limitations" />

#### 制限事項

| 制限事項 | 詳細 |
| --- | --- |
| アカウントあたりのレポート数 | 1アカウントにつき有効なレポートは最大5件 |
| レポートあたりのアプリ内イベント数 | 1レポートにつき最大30イベント |
| レポートあたりの総カラム数 | 最大150カラム（ディメンション＋指標＋アプリ内イベントのサブ指標の合計） |
| データ対象期間 | 過去30日間のルックバック期間のデータを利用できます。この期間より前の履歴データは利用できません。 |
| 配信頻度 | 1日1回。日中の追加配信には対応していません。 |
| AIディメンションの利用可否 | AIタグ付け工程で処理されたクリエイティブにのみAIディメンションの値が入ります。新しくアップロードされたクリエイティブでは、反映までに時間がかかる場合があります。 |
| カスタム指標 | 現在は対応していません。 |
| コンバージョンアクション（Web） | 現在は対応していません。 |
| アプリの選択 | 各レポートには、アカウント内のすべてのアプリが含まれます。特定のアプリのみを対象にフィルターする機能は、今後のリリースで対応予定です。 |

</Accordion>

<div id="faq" />

## よくある質問

ETLレポートに関するよくある質問をまとめています。

<div id="whats-the-difference-between-standard-creative-etl-and-custom-creative-etl" />

<Accordion title="標準クリエイティブETLとカスタムクリエイティブETLの違いは何ですか？">

**標準クリエイティブETL**は、Data Lockerのレポートを選択ページから設定し、固定されたフィールド一式（スキーマ）を1日1回配信します。アプリ内イベント、リターゲティング／統合の内訳、AIディメンションには対応していません。

**カスタムクリエイティブETL**はAppsFlyerのUIから直接設定でき、含めるフィールドを自由にカスタマイズできます。最大30件のアプリ内イベント、AIディメンション、ユーザー獲得・リターゲティング・統合の内訳を含めることができ、バックエンドでの設定やカスタマーサクセスマネージャーへの依頼は不要です。

</Accordion>

<div id="can-i-run-both-standard-creative-etl-and-custom-creative-etl-at-the-same-time" />

<Accordion title="標準クリエイティブETLとカスタムクリエイティブETLを同時に利用できますか？">

はい。両方を並行して利用できます。標準クリエイティブETLレポートが有効になっている場合、Creative ETLページに通知バナーが表示され、Data Locker設定へのリンクから移動できます。

</Accordion>

<div id="can-i-have-multiple-custom-creative-etl-reports-with-different-report-types" />

<Accordion title="レポートタイプが異なる複数のカスタムクリエイティブETLレポートを作成できますか？">

はい。各レポートには1つのレポートタイプ（ユーザー獲得、リターゲティング、統合）を設定でき、1アカウントにつき最大5件のレポートを作成できます。

</Accordion>

<div id="how-do-i-add-new-inapp-events-to-an-existing-custom-creative-etl-report" />

<Accordion title="既存のカスタムクリエイティブETLレポートに新しいアプリ内イベントを追加するにはどうすればよいですか？">

**レポート出力** > **Creative ETL**に移動し、対象レポートの**編集**アイコンをクリックして、<strong>ステップ3（スキーマ）</strong>で新しいイベントを追加します。変更内容は、次回の日次配信から反映されます。

</Accordion>

<div id="what-happens-if-a-report-runs-more-than-once-on-the-same-day" />

<Accordion title="同じ日にレポートが複数回実行された場合はどうなりますか？">

レポートが再実行された場合（通常はバックフィル時）、実行ごとに`version`の値が増加します。同じ`dt`パーティションについて複数のバージョンがある場合は、常に最も大きいversionのデータを使用してください。

</Accordion>

<div id="see-also" />

> 📄 **関連記事**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-guide">Creative Optimizationガイド</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/data-locker-advertiser-reports">Data Lockerの広告主向けレポート</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup">Data Locker接続の設定</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports">ROI360：コストETLレポートの設定と利用</Anchor>

<div data-zendesk-anchors="about-creative-optimization-etl-reporting=creative-optimization-etl%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KW7A0CWMCFQA7K6YE909BVW4=creative-optimization-etl%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KW7A0CWMH2SCPQ917TKASCC7=standard-creative-etl h_01KW7A0CWMJDR014M6JSA2HBHY=%E6%B3%A8%E6%84%8F get-started=%E3%81%BE%E3%81%9A%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01KW7A0CWM2SPE4RYFJKZBDKJG=%E3%81%BE%E3%81%9A%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB edit-data-locker-configuration=data-locker%E8%A8%AD%E5%AE%9A%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B h_01KW7A0CWMAR0E52M7T6PXMCKT=data-locker%E8%A8%AD%E5%AE%9A%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B data-freshness=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%9B%B4%E6%96%B0%E9%A0%BB%E5%BA%A6 h_01KW7A0CWM9K9J7X64S14TX2AE=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%9B%B4%E6%96%B0%E9%A0%BB%E5%BA%A6 available-data=%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AA%E3%83%87%E3%83%BC%E3%82%BF h_01KW7A0CWM1JYVQXKBDH06X1BA=%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AA%E3%83%87%E3%83%BC%E3%82%BF h_01KW7A0CWMT7Q8BFTB8WAT7M0W=%E6%B3%A8%E6%84%8F-1 h_01KW7A0CWNZMPD7RSX41VNGSCF=custom-creative-etl before-you-begin=%E5%A7%8B%E3%82%81%E3%82%8B%E5%89%8D%E3%81%AB h_01KW7A0CWNK0R6XAB37E5ZP7KG=%E5%A7%8B%E3%82%81%E3%82%8B%E5%89%8D%E3%81%AB set-up-custom-creative-etl=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%AF%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96etl%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KW7A0CWN2DZFZP3YK23ZW9EH=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%AF%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96etl%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KW7A0CWNQJT83A9KAE8E7XHD=%E3%82%B9%E3%83%86%E3%83%83%E3%83%971%E4%BF%9D%E5%AD%98%E5%85%88 h_01KW7A0CWNH69H47EF7FAV1FRF=%E3%82%B9%E3%83%86%E3%83%83%E3%83%972%E8%A9%B3%E7%B4%B0 h_01KW7A0CWN0M4ZFRPQ7BN9TRTC=%E6%B3%A8%E6%84%8F-2 h_01KW7A0CWNG5PVQNC8ED1RXV28=%E3%82%B9%E3%83%86%E3%83%83%E3%83%973%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%9E h_01KW7A0CWNER5KD46VJHE1X0VH=%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%9E%E3%81%A8%E3%81%AF h_01KW7A0CWNJYPD5TXZ301PMF7S=%E6%B3%A8%E6%84%8F-3 h_01KW7A0CWN4NWNP10TAYD26GCQ=%E6%B3%A8%E6%84%8F-4 h_01KW7A0CWNFWY5BYGVPPXTYQ1X=%E9%87%8D%E8%A6%81 edit-an-existing-report=%E6%97%A2%E5%AD%98%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B h_01KW7A0CWNVJJTVW1MP0V25ZC5=%E6%97%A2%E5%AD%98%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B h_01KW7A0CWNFZCW1NNBY2H0BSDS=%E6%B3%A8%E6%84%8F-5 h_01KW7A0CWNY50EV4EDS3BWGP6S=%E9%87%8D%E8%A6%81-1 report-management=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E7%AE%A1%E7%90%86 h_01KW7A0CWNRKGS9TJ4Y2H7JD5S=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E7%AE%A1%E7%90%86 h_01KW7A0CWNN3MN0S8Z563BYQ97=%E6%B3%A8%E6%84%8F-6 data-delivery=%E3%83%87%E3%83%BC%E3%82%BF%E9%85%8D%E4%BF%A1 h_01KW7A0CWNS62EYWZ8V41E7RRY=%E3%83%87%E3%83%BC%E3%82%BF%E9%85%8D%E4%BF%A1 schema-reference=%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%9E%E3%81%AE%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9 h_01KW7A0CWNWM3JTMEFF8B3SPXG=%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%9E%E3%81%AE%E3%83%AA%E3%83%95%E3%82%A1%E3%83%AC%E3%83%B3%E3%82%B9 h_01KW7A0CWNP32RKD6YW1GNPNEE=%E5%BF%85%E9%A0%88%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 h_01KW7A0CWNJRT87NYJQ19YHSSG=%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3 h_01KW7A0CWNTSGC4BPEBME4WWNC=ai%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3 h_01KW7A0CWNNA03BG2BAQ4MGGMX=%E6%B3%A8%E6%84%8F-7 h_01KW7A0CWN6H39Q9D7SX2TFXAF=%E6%8C%87%E6%A8%99 h_01KW7A0CWP4JQSDP8E2BQESE2A=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 limitations=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KW7A0CWPJ8W3ZE2JZ9YTZFQF=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01KW9K4YXMJ14TX6FMGYY4811K=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01KW9K4YXM8E6ZF226DTTVZHK8=whats-the-difference-between-standard-creative-etl-and-custom-creative-etl h_01KW9K4YXMNDT73BPAV1CC5JZ5=can-i-run-both-standard-creative-etl-and-custom-creative-etl-at-the-same-time h_01KW9K4YXM3F3W45MTNDHS9DM9=can-i-have-multiple-custom-creative-etl-reports-with-different-report-types h_01KW9K4YXMVH2NSM46S63EVX01=how-do-i-add-new-inapp-events-to-an-existing-custom-creative-etl-report h_01KW9K4YXMDQZHF5TZGQE1NR0P=what-happens-if-a-report-runs-more-than-once-on-the-same-day h_01KW7A0CWP90HES8D1S2A1PF6X=%E9%96%A2%E9%80%A3%E8%A8%98%E4%BA%8B" />
