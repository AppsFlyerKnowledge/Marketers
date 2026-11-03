---
title: Data Collaboration Platform（DCP）｜取り込み用ソースデータの準備
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
  created_at: '2026-01-26T12:08:32Z'
  edited_at: '2026-10-19T18:51:49Z'
  id: 43205325114897
  locale: ja
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ja/articles/43205325114897
---
> **概要：** コラボレーター間のデータセットのマッチ率を最大化し、コラボレーションの成果を高めるために、ソースデータを適切に準備します。

## データ準備について

AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-guide">Data Collaboration Platform（DCP）</Anchor>は、複数のコラボレーターから提供される大規模なトランザクションデータ、ユーザーレベルデータ、またはその両方を取り込み・処理できるよう設計されています。データを取り込むと、DCPは共通の識別子（ハッシュ化されたメールアドレスや電話番号など）を使用してデータセット間でユーザーを照合し、そのデータに基づくコラボレーションのワークフローを実行できます。

この記事では、以下について説明します。

* DCPで処理できるデータの種類（トランザクションデータ、ユーザーレベルデータ、またはその組み合わせ）
* コラボレーター間のマッチ率を最大化し、アクティベーションパートナー側でも最適に照合できるようにするためのデータ構造
* 推奨されるデータ構造と、推奨されないデータ構造
* CSVファイルで複数値の識別子を扱う方法

## データタイプの理解

コラボレーションで使用する多くのソースには、以下のいずれか、または両方のデータタイプが含まれます。

* **ユーザーレベルデータ（識別子データ）**
  * **目的：** 各ユーザーと、照合に使用する識別子を表現する
  * **推奨構造：** 1ユーザーにつき1行
* **トランザクションデータ（イベントデータ）**
  * **目的：** ユーザーの行動（購入、訪問、取引など）を表現する
  * **一般的な構造：** 1ユーザーにつき複数行（1人のユーザーが複数のトランザクションを持つ場合があるため）

## データ構造のガイドライン

このセクションでは、DCPでのデータ構造に関するガイドラインとベストプラクティスについて説明します。

<div id="workflow-and-structuring-guidelines" />

<Accordion title="推奨されるデータ構造">

**DCPへ効率的に取り込み、最大限の成果を得られるようソースデータを構成するには：**

1. <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#ソースデータの要件">ソースデータの形式要件</Anchor>を満たしていることを確認します。
2. 最良の結果を得るため、<strong>識別子データは1ユーザーにつき1行で構成し、そのユーザーについて利用可能な識別子をすべて含めてください。</strong>詳細は、[推奨される識別子の構造](#推奨される識別子の構造)を参照してください。
   * ユーザーが複数のメールアドレスや電話番号を持つ場合は、配列に対応した形式（Parquet、BigQuery、Snowflakeなど）を使用します。
3. [ハッシュ化のガイドライン](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-e-hashed-data-formatting-guidelines-by-media-partner)に従っていることを確認します。
4. トランザクションデータセット（および該当するその他のデータタイプ）では、**DCPのData Viewツールを使用**して、コラボレーションに適した、ビジネス用途を意識したプライバシー保護済みのデータサブセットを作成し、ローテーブルではなくそのData Viewを共有してください。 [Data Viewが推奨される理由](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-c-why-dataviews-matter-and-recommended)

他の構造も使用できますが、DCPを最大限に活用するうえでは最適でない場合があります。[推奨されないデータ構造](#data-structures-that-arent-recommended)を参照してください。

#### 推奨される識別子の構造

マッチ率を最大化するには、可能な限りユーザーレベルの識別子データを1ユーザーにつき1行で送信し、実際のユーザー情報の持ち方を正確に反映した構造で、利用可能な識別子をすべて含めることを推奨します。

**オプション1：1ユーザーにつき1行、識別子タイプごとに1つの値**

**シンプルで効果的な構造です。**

各ユーザーが、ハッシュ化されたメールアドレス、ハッシュ化された電話番号などをそれぞれ最大1つしか持たない場合に使用します。

**例**

| ユーザーID | ハッシュ化されたメールアドレス | ハッシュ化された電話番号 |
| --- | --- | --- |
|  | 5d41402 | 152d234b70 |
|  | 7d793037 |  |
|  |  | 0e6e5414 |

**この構造が推奨される理由**

* 準備と取り込みが最もシンプル
* 検証やトラブルシューティングが容易
* 識別子が完全かつ一貫している場合、コラボレーターのデータセットとの照合やアクティベーション先のメディアパートナーとの照合で高いマッチ率が期待できる

**適したケース**

* CSVベースのアップロードに最適
* Parquet／BigQuery／Snowflakeでも利用可能

**オプション2：複数値フィールドで識別子の配列（リスト）を使用**

**ユーザーが複数のメールアドレスや電話番号を持つ場合に、精度を高めるのに最適な構造です。**

1人のユーザーが同じ識別子タイプの値を複数持つ場合に使用します。例：

* 複数のハッシュ化メールアドレス
* 複数のハッシュ化電話番号

この構造は**ネイティブ配列**として表現してください。

**例**

| ユーザーID | ハッシュ化されたメールアドレス | ハッシュ化された電話番号 | MAID |
| --- | --- | --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] | [p1q2 · r3s4] | m001 |
| u\_0002 | [z9y8 · x7w6] |  | m002 |
| u\_0003 |  | [t1u2 · v3w4 · x5y6] |  |

**この構造が推奨される理由**

* 識別子データが社内で実際に保存されている構造を反映しやすい
* 必要となる「メールアドレス列」の数を事前に想定する必要がない
* 継続的なスキーマ変更を避けられる
* 1ユーザーにつき複数の識別子を持たせることで、コラボレーターのデータセットやアクティベーション先のメディアパートナーとのマッチ可能性を最大化できる

**適したケース**

* Parquet（S3／GCS）
* BigQuery
* Snowflake

</Accordion>

<div id="practical-checklist-for-dcp-collaborators" />

<Accordion title="データ構造の実践チェックリスト">

#### 識別子データ（ユーザーレベルデータ）のチェックリスト

* 1行が1ユーザーを表していること。
* 利用可能な識別子（ハッシュ化メールアドレス、ハッシュ化電話番号、MAIDなど）をすべて含めること。
* 複数の値（複数のメールアドレスなど）がある場合は、可能な限りネイティブ配列を使用すること。
* セル内のリスト、「email\_1/email\_2/email\_3」のような複数列、複数行にまたがる識別子データの構造は避けること。

#### トランザクションデータ（イベントデータ）のチェックリスト

* イベント／トランザクションの行は、元の構造のまま保持します。[トランザクションデータの例](#appendix-a-transactional-data-examples)を参照してください。
* 必要に応じて[Data View](#appendix-c-why-dataviews-matter-and-recommended)を使用し、コラボレーションに適したユーザーレベルのサマリーを作成します。

#### Data Viewのチェックリスト

* ビジネス用途を意識した[Data View](#appendix-c-why-dataviews-matter-and-recommended)を作成します（オーディエンス作成に適した、集約・標準化済みの構造）。
* 可能な限り、機密性の高いローデータのテーブルではなくData Viewを共有します。
* 共有するフィールドは、プライバシー保護とビジネス上の情報保護の観点から、必要なものだけに絞ります。
* 機密データへのアクセスを減らし、効率を高めるため、集約処理の活用を検討します。

</Accordion>

<div id="supported-ingestion-cloud-services-and-formats" />

<Accordion title="対応する取り込み用クラウドサービスと形式">

DCPでは、以下を含む複数のクラウドサービスからデータを取り込めます。

* AWS S3
* GCS（Google Cloud Storage）
* BigQuery
* Snowflake

#### 形式に関するガイドライン

* 各ユーザーが識別子タイプごとに**1つの値**（メールアドレス1つ、電話番号1つなど）を持つ場合は、<strong>CSV（カンマ区切り）</strong>を使用します。
* ユーザーが同じ識別子タイプの**複数の値**（複数のハッシュ化メールアドレスなど）を持つ場合は、**配列に対応した形式**を推奨します。
  * Parquet（ビッグデータで一般的）
  * BigQuery（配列を標準サポート）
  * Snowflake（配列を標準サポート）

**注意：**

* 「配列（Array）」とは、複数の値を1つのリストとして持つことを意味します。
* ParquetやBigQuery／Snowflakeの配列は標準的な機能であり、多くのデータチームで無理なく対応できます。

[コネクタ別のサンプル（AWS S3、GCS、BigQuery、Snowflake）](#appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake)を参照してください。

<div id="data-structures-that-arent-recommended" />

<Accordion title="推奨されないデータ構造">

DCPへの取り込みに適したデータ構造もあれば、適していない構造もあります。以下は、**推奨されない**データ構造です。

#### 避けるべき構造：同じ識別子タイプに複数の列を使用

「メイン／サブ／3つ目のメールアドレス」のように列を分ける構造は推奨されません。

**避けるべき例**

| ユーザーID | メールアドレスハッシュ1 | メールアドレスハッシュ2 | メールアドレスハッシュ3 |
| --- | --- | --- | --- |
|  | a1b2 | c3d4 |  |
|  | z9y8 |  |  |

**避けるべき理由**

* ユーザーごとの値の数を事前に予測できない
* 列数が増え続け、スキーマの保守が複雑になる

#### 避けるべき構造：1つのセルに「リスト」を自由形式のテキストとして格納

一見便利に見えますが、エラーが発生しやすい構造です。

**避けるべき例**

| ユーザーID | ハッシュ化メールアドレス（テキスト） |
| --- | --- |
|  | a1b2 · c3d4 · e5f6 |

**避けるべき理由**

* 実際の配列型ではない
* 形式やエスケープ処理の問題が起こりやすい
* わずかな表記の不整合でも取り込みに失敗する可能性がある

#### 避けるべき構造：識別子データを1ユーザーにつき複数行に分割（ユーザーの識別子テーブルを作る場合）

識別子データを1ユーザー1行で保持できる場合は、複数行に分割しないでください。

**避けるべき例**

| ユーザーID | 識別子タイプ | 識別子の値 |
| --- | --- | --- |
|  | hashed\_email | a1b2 |
|  | hashed\_email | c3d4 |

**避けるべき理由**

* ユーザー単位のデータを再構成するために追加処理が必要になる
* 重複や不整合が発生するリスクが高まる
* 大規模データでは処理効率が低い

**注意：** トランザクションテーブルでは1ユーザーにつき複数行になるのが一般的ですが、照合に使用する識別子データ（ユーザーレベルデータ）のテーブルには適していません。

</Accordion>

</Accordion>

## 追加情報

このセクションでは、関連するトピックについて、より詳しい情報を提供します。

<div id="appendix-a-transactional-data-examples" />

<Accordion title="トランザクションデータの例">

トランザクション／イベントデータでは、1ユーザーにつき複数行になる場合があります。

| トランザクションID | ユーザーID | トランザクション日 | 金額 | カテゴリ |
| --- | --- | --- | --- | --- |
| t\_001 |  | 2025-12-01 |  | 食料品 |
| t\_002 |  | 2025-12-15 |  | 薬局 |
| t\_003 |  | 2025-12-20 |  | 家電 |

**推奨**

* トランザクションデータは、元の自然な構造のまま取り込みます。
* Data Viewツールを使用して、コラボレーションに適したユーザーレベルのビューを作成します（例：過去30日間の支出額、カテゴリ嗜好、直近購入日／購入頻度のサマリー）。

</Accordion>

<div id="appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake" />

<Accordion title="コネクタ別のサンプル（AWS S3、GCS、BigQuery、Snowflake）">

### 「識別子の配列／リスト」とは？

1人のユーザーが複数のメールアドレスや電話番号を持つことがあります（個人用と仕事用のメールアドレスなど）。その場合、列を増やしたり、1つのテキストフィールドに無理に詰め込んだりするのではなく、複数の値をリストとして表現します。

| ユーザーID | ハッシュ化されたメールアドレス（リスト） |
| --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] |
| u\_0002 | [z9y8 · x7w6] |

### AWS S3／GCSコネクタ（Parquet）

**識別子データのサンプルに含める内容（スキーマ）**

| フィールド | タイプ | 備考 |
| --- | --- | --- |
| user\_id | string | 1ユーザーにつき1行 |
| hashed\_emails | 文字列の配列 | 複数値の識別子（推奨） |
| hashed\_phones | 文字列の配列 | 複数値の識別子（推奨） |
| maid | string | 任意の追加識別子 |

Parquetはリストをネイティブでサポートしているため、ユーザーが複数のメールアドレス／電話番号を持つ場合に推奨されます。

### BigQueryコネクタ（テーブルプレビューとスキーマのスクリーンショット）

**識別子データのスキーマ例（BigQuery）**

| フィールド | タイプ | モード |
| --- | --- | --- |
| user\_id | STRING | NULLABLE |
| hashed\_emails | STRING | REPEATED（ARRAY） |
| hashed\_phones | STRING | REPEATED（ARRAY） |
| maid | STRING | NULLABLE |

BigQueryでは、配列はネイティブ機能（REPEATEDフィールド）としてサポートされています。複数のメールアドレス／電話番号がある場合は、この方法を推奨します。

### Snowflakeコネクタ（テーブルプレビューとスキーマのスクリーンショット）

**識別子データのスキーマ例（Snowflake）**

| フィールド | タイプ | 備考 |
| --- | --- | --- |
| USER\_ID | VARCHAR | 1ユーザーにつき1行 |
| HASHED\_EMAILS | ARRAY | 複数値の識別子 |
| HASHED\_PHONES | ARRAY | 複数値の識別子 |
| MAID | VARCHAR | 任意 |

Snowflakeは、リスト形式のフィールド（配列）をサポートしています。 email\_1/email\_2/email\_3のように複数の列を作成するよりも、この方法を推奨します。

</Accordion>

<div id="appendix-c-why-dataviews-matter-and-recommended" />

<Accordion title="Data Viewが推奨される理由">

<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-customized-data-views">Data View</Anchor>は、元のデータセットを変更することなく、既存のデータソースから作成できるカスタマイズ済みのデータサブセットです。 Data Viewでは、データを加工・精緻化・集約する処理を行い、コラボレーションに必要な情報だけを共有できます。共有データを明確かつ目的に沿った内容に保ちながら、それ以外のデータは非公開かつ安全な状態に維持できます。コラボレーションでData Viewを使用する理由：

#### ビジネス用途に適しており、コラボレーションしやすい

* Data Viewを使用すると、ローログや複雑なトランザクションスキーマではなく、「Customer Identity View」「Eligible Audience View」「Purchase Summary View」など、整理されたビジネス向けの構造でデータを提示できます。
* また、「アクティブユーザー」「過去30日間の総支出額」などの定義を標準化できるため、双方が同じ定義とロジックに基づいてデータを利用できます。

#### 設計上、よりプライバシーを保護しやすい

* Data Viewはデータ最小化に対応しており、ローデータセット全体を公開するのではなく、コラボレーションに必要なフィールドと行だけを共有できます。
* 以下の方法でプライバシーリスクを抑えられます。
  * 不要な属性を除外
  * 粒度を制限（例：明細レベルのトランザクションではなく、集約済みの指標を共有）
  * 照合に必要な識別子だけを共有し、追加の機密列は共有しない

#### 機密性の高いビジネスデータを保護

* ロートランザクションテーブルには、詳細な購買行動、価格パターン、加盟店との関係、内部IDなど、機密性の高いビジネス情報が含まれる場合があります。
* Data Viewを使用すると、コラボレーションに必要な情報だけを共有できます。
  * 例：商品単位の詳細ではなく、カテゴリ単位の集計値を共有
  * 例：正確な明細ではなく、支出額のレンジやサマリー指標を共有
* これにより、競争上重要な情報や独自情報を意図せず開示してしまうリスクを軽減できます。

#### コスト効率とパフォーマンスを高められる

Data Viewを軽量で効率的な構造にすることで、以下を削減できる場合があります。

* スキャンするデータ量
* 処理時間
* コンピューティングコスト

コラボレーション向けのビュー（特に集約済みビュー）をあらかじめ構成しておくことで、コラボレーションをより迅速に進め、運用上の予測可能性を高められる場合があります。

</Accordion>

<div id="appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform" />

<Accordion title="プラットフォーム別：複数のID／キーのアップロードとマッチング動作">

**DCPの識別子アップロード**

| パートナー／プラットフォーム | 対応する識別子タイプ | アップロードモード | アップロード時の動作 | 識別子の優先順位（単一タイプのみ対応するパートナー） |
| --- | --- | --- | --- | --- |
| Meta | Email、Phone、IDFA、GAID、Android ID、First Name、Last Name、DOB、City、State、Zip、Country | 対応するすべてのタイプ | 対応するすべての識別子タイプをアップロード | 該当なし - すべてアップロード |
| Google | Email、Phone、IDFA、GAID、Android ID、Customer ID | 単一タイプ | オーディエンスごとに1種類の識別子タイプをアップロード | Email 2. Phone 3. Mobile IDs 4. Customer ID |
| TikTok | Email、Phone、IDFA、GAID、Android ID | 対応するすべてのタイプ | 対応するすべての識別子タイプをアップロード | 該当なし - すべてアップロード |
| Pinterest | Email、Phone、IDFA、GAID | 単一タイプ | オーディエンスごとに1種類の識別子タイプをアップロード | Email 2. Phone 3. Mobile IDs |
| Infillion | Email、Phone、IDFA、GAID、MM-UUID | 対応するすべてのタイプ | 対応するすべてのタイプを最大3ファイルに分けてアップロード | 該当なし - すべてアップロード |
| TheTradeDesk | Email、Phone | 単一タイプ | オーディエンスごとに1種類の識別子タイプをアップロード | Email 2. Phone |
| AppsFlyer Data Locker | 利用可能なすべての識別子 | すべてのタイプを統合 | すべての識別子を1つの統合ファイルで配信 | 該当なし - すべて配信 |

| プラットフォーム | 1ユーザーにつき複数のIDを送信できるか | いずれかのIDでマッチできるか | 複数のIDを組み合わせてマッチできるか | マッチングモデル（実運用） | 備考 |
| --- | --- | --- | --- | --- | --- |
| Meta | はい | はい | はい | 決定論的、いずれかのID／組み合わせ | Email、Phone、MAID、fbp/fbcをすべて評価。複数のIDのうちいずれかでマッチする仕組みが最も強力 |
| Google | はい | 限定的 | いいえ | 決定論的、優先順位あり | 1つのIDでユーザーを特定します。複数のIDを組み合わせてマッチを成立させることはありません。 |
| TikTok | はい | はい | はい | 決定論的、いずれかのID／組み合わせ | Metaと非常に近い仕組み。イベントではttclidが有効 |
| Pinterest | はい | 一部対応 | 限定的 | 決定論的、ID中心 | 主にEmailとMAIDを使用。複数IDによる補完効果は限定的 |
| The Trade Desk（TTD） | はい | IDグラフ経由 | はい（グラフ経由） | IDグラフを利用した決定論的マッチング | UID2、MAID、CookieをEUID／UID2グラフ経由で解決 |
| Infillion | はい | IDグラフ経由 | はい（グラフ経由） | パートナーのIDグラフを利用した決定論的マッチング | OmniID／パートナーのID解決機能を利用 |

**アクティベーション計画のポイント**

* **MetaとTikTok**
  * 利用可能な識別子をすべて送信
  * 複数IDのうち「いずれか」でマッチできる仕組みに対応
  * 識別子が豊富なクリーンルームアクティベーションに最も適したプラットフォーム
* **Google**
  * カバレッジを広げるために複数のIDを送信
  * 複数IDの組み合わせによる補完効果は期待しない
  * Email／Phoneが中心
* **TTDとInfillion**
  * マッチング品質は、識別子の数よりIDグラフへの参加状況に左右される
  * 生の識別子数より、UID2／OmniIDのカバレッジが重要
* **Pinterest**
  * MetaよりGoogleに近い動作
  * Email＋MAID以外のIDを追加しても得られる効果は限定的

**要点**

* 複数IDのうち「いずれか」でネイティブにマッチできるのはMetaとTikTokのみ
* Googleは決定論的ですが、1つのIDでユーザーを特定します。
* オープンWeb系プラットフォームは、生のIDではなくIDグラフを利用してマッチングします。

</Accordion>

<div id="appendix-e-hashed-data-formatting-guidelines-by-media-partner" />

<Accordion title="メディアパートナー別：ハッシュ化データの形式ガイドライン">

**共通の正規化ルール：**  
マッチ精度を確保するため、ほぼすべてのプラットフォームで、データをハッシュ化する前に以下の正規化処理が必要です。

* **テキスト：** 小文字に変換し、先頭と末尾の空白を削除します。
* **電話番号：** E.164形式に変換します（例：+15551234567）。
* **ハッシュ化：** 業界標準はSHA-256ですが、一部のプラットフォームではMD5またはSHA-1も利用できます。

| メディアパートナー | メールアドレスのガイドライン | 電話番号のガイドライン | モバイルID（MAID）のガイドライン | プラットフォーム固有の注意点とマッチングロジック | 関連リファレンス |
| --- | --- | --- | --- | --- | --- |
| Google Ads／DV360 | 形式：小文字に変換し、空白を削除。ドメインを含めます。 Gmailルール：@gmail.com／@googlemail.comでは、「@」より前のピリオド（.）と「+」以降のサフィックスを削除します。ハッシュ化：SHA-256（16進エンコード）。 | 形式：E.164（例：+16505551212）。国番号を含める必要があります。ハッシュ化：SHA-256。 | 形式：IDFA（iOS）またはGAID（Android）。ハッシュ化：行いません。 | マッチングの優先順位：決定論的かつ優先順位あり（1. Email、2. Phone、3. Mobile IDs）。複数のIDを組み合わせてマッチを成立させることはありません（単一IDで解決）。 DV360 PAIR：DV360では、パブリッシャーと広告主のデータを安全に照合するためのPAIRプロトコルにも対応しています。 | Customer Matchの利用開始（Google Ads API） |
| Meta（Facebook／Instagram） | 形式：小文字に変換し、空白を削除。ハッシュ化：SHA-256必須。<br /><br />**注意：** Metaでは、ハッシュ化前の正規化処理としてメールアドレスからピリオドを削除しません。 Meta向けには、ハッシュ化前に小文字化と空白の削除だけを行ってください。ピリオドを削除してハッシュ化したメールアドレス（DCPのソースマッピングでは「Hashed email (no dots)」）を送信すると、Meta側のハッシュ値と一致せず、該当するメールドメインのユーザーでマッチ率が低下します。この識別子バリエーションは、Google Adsなどピリオド削除が必要なパートナー向けであり、Meta／Facebookのアクティベーションには使用しないでください。 | 形式：記号、英字、先頭のゼロを削除します。国番号を含めます（例：16505551212）。ハッシュ化：SHA-256。 | 形式：IDFAまたはGAID。ハッシュ化：行いません。小文字に変換し、ハイフンは保持します。 | マッチングロジック：複数IDのうち「いずれか」でマッチする仕組みを使用し、Email、Phone、MAIDなど複数のIDを組み合わせてユーザーを特定するため、ID間で強い補完効果が得られます。<br /><br />CAPI：ブラウザでのマッチングには、ハッシュ化していないclient\_ip\_addressとclient\_user\_agentが必要です。 | Customer Information Parameters - Conversions API |
| TikTok | 形式：小文字に変換し、すべての空白を削除。ハッシュ化：SHA-256。 | 形式：E.164（+[国番号][電話番号]）。 「+」なしの形式にも対応しています。ハッシュ化：SHA-256。 | 形式：GAID（Android）またはIDFA（iOS）。大文字／小文字：すべて大文字、またはすべて小文字。ハッシュ化：SHA-256またはMD5。 | マッチングロジック：Metaと同様に、複数IDのうち「いずれか」で決定論的にマッチする方式で、1つでも有効なIDがあれば照合できます。<br /><br />オーディエンスサイズ：Custom Audienceをアクティベーションするには、マッチ済みユーザーが1,000人以上必要です。 | カスタマーファイルを使用してCustom Audienceを作成する方法 |
| The Trade Desk（UID2） | 形式：Googleと同じ「Gmailルール」（ピリオド／「+」以降を削除）。エンコード：ハッシュの生バイトをBase64でエンコードします（結果は44文字）。 | 形式：E.164。ハッシュ化：SHA-256。エンコード：生バイトをBase64でエンコードします。 | 形式：AAID（小文字）／IDFA（大文字）。ハッシュ化：SHA-256、MD5、またはSHA-1。 | マッチングロジック：IDグラフを利用した決定論的マッチング。マッチングは、生のIDのカバレッジではなくIDグラフへの参加状況に左右されます。<br /><br />重要：ハッシュの生バイトをBase64でエンコードする必要があります。 16進文字列をエンコードすると失敗します。 |  |
| Pinterest | 形式：「@」を含める必要があります。ハッシュ化：SHA-256、MD5、またはSHA-1。 | 形式：E.164。特殊文字（スペース、ハイフン）を削除します。ハッシュ化：SHA-256、MD5、またはSHA-1。 | 形式：IDFAまたはGAID。ハッシュ化：SHA-256、MD5、またはSHA-1。 | マッチングロジック：「ID中心」。主にEmailとMAIDでマッチングします。 Metaと比べて複数IDによる補完効果が弱いため、その他のIDを追加しても得られる効果は限定的です。アップロード時の動作：オーディエンスごとに1種類の識別子タイプをアップロードします。 | DCPのデータ取り込みと構造化のガイドライン |

</Accordion>

<div data-zendesk-anchors="about-dcp-ingestion-and-preparation-of-data=%E3%83%87%E3%83%BC%E3%82%BF%E6%BA%96%E5%82%99%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KFX4HVTT50TZMY2YF37B1C4R=%E3%83%87%E3%83%BC%E3%82%BF%E6%BA%96%E5%82%99%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 data-types=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BF%E3%82%A4%E3%83%97%E3%81%AE%E7%90%86%E8%A7%A3 h_01KFX4HVTTAMFEGJQEYXXWG9PT=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BF%E3%82%A4%E3%83%97%E3%81%AE%E7%90%86%E8%A7%A3 data-ingestion-recommendations=%E3%83%87%E3%83%BC%E3%82%BF%E6%A7%8B%E9%80%A0%E3%81%AE%E3%82%AC%E3%82%A4%E3%83%89%E3%83%A9%E3%82%A4%E3%83%B3 h_01KFX4HVTT2Q2EV4GAC6M8R4A2=%E3%83%87%E3%83%BC%E3%82%BF%E6%A7%8B%E9%80%A0%E3%81%AE%E3%82%AC%E3%82%A4%E3%83%89%E3%83%A9%E3%82%A4%E3%83%B3 h_01KFZJ2PK9XADZ2143VJB3YZ55=workflow-and-structuring-guidelines recommended-identifier-structures=%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E8%AD%98%E5%88%A5%E5%AD%90%E3%81%AE%E6%A7%8B%E9%80%A0 h_01KFXB0KEF59QCYET0R8XNH84D=%E6%8E%A8%E5%A5%A8%E3%81%95%E3%82%8C%E3%82%8B%E8%AD%98%E5%88%A5%E5%AD%90%E3%81%AE%E6%A7%8B%E9%80%A0 h_01KFZN8104KSPFRSS5SED7VT19=practical-checklist-for-dcp-collaborators identity-userlevel-dataset-checklist=%E8%AD%98%E5%88%A5%E5%AD%90%E3%83%87%E3%83%BC%E3%82%BF%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%83%AC%E3%83%99%E3%83%AB%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 h_01KFZNGRC0XX7YYBYT09M49YFA=%E8%AD%98%E5%88%A5%E5%AD%90%E3%83%87%E3%83%BC%E3%82%BF%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%83%AC%E3%83%99%E3%83%AB%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 transactional-events-dataset-checklist=%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 h_01KFZNJ7YKCT1YFYE400CNY6SP=%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 dataviews-checklist=data-view%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 h_01KFZNKBXJQ4S89YHCGKP8J5F4=data-view%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 h_01KFZJ2PK9TT2RZQ366Y2THS7E=supported-ingestion-cloud-services-and-formats format-guidance=%E5%BD%A2%E5%BC%8F%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%AC%E3%82%A4%E3%83%89%E3%83%A9%E3%82%A4%E3%83%B3 h_01KFX6XSNACVR9JWZWZW12F6C4=%E5%BD%A2%E5%BC%8F%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%82%AC%E3%82%A4%E3%83%89%E3%83%A9%E3%82%A4%E3%83%B3 h_01KFZJ2PK92Y5HHFC2D1H8AD9B=data-structures-that-arent-recommended avoid-multiple-columns-for-the-same-identifier-type=%E9%81%BF%E3%81%91%E3%82%8B%E3%81%B9%E3%81%8D%E6%A7%8B%E9%80%A0%E5%90%8C%E3%81%98%E8%AD%98%E5%88%A5%E5%AD%90%E3%82%BF%E3%82%A4%E3%83%97%E3%81%AB%E8%A4%87%E6%95%B0%E3%81%AE%E5%88%97%E3%82%92%E4%BD%BF%E7%94%A8 h_01KFX72MNYH1CSKWZAGZ2XETXY=%E9%81%BF%E3%81%91%E3%82%8B%E3%81%B9%E3%81%8D%E6%A7%8B%E9%80%A0%E5%90%8C%E3%81%98%E8%AD%98%E5%88%A5%E5%AD%90%E3%82%BF%E3%82%A4%E3%83%97%E3%81%AB%E8%A4%87%E6%95%B0%E3%81%AE%E5%88%97%E3%82%92%E4%BD%BF%E7%94%A8 avoid-%E2%80%9Clists-inside-a-single-cell%E2%80%9D-free-text=%E9%81%BF%E3%81%91%E3%82%8B%E3%81%B9%E3%81%8D%E6%A7%8B%E9%80%A01%E3%81%A4%E3%81%AE%E3%82%BB%E3%83%AB%E3%81%AB%E3%83%AA%E3%82%B9%E3%83%88%E3%82%92%E8%87%AA%E7%94%B1%E5%BD%A2%E5%BC%8F%E3%81%AE%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88%E3%81%A8%E3%81%97%E3%81%A6%E6%A0%BC%E7%B4%8D h_01KFX70V3BHNK93SKCRGGDVY3W=%E9%81%BF%E3%81%91%E3%82%8B%E3%81%B9%E3%81%8D%E6%A7%8B%E9%80%A01%E3%81%A4%E3%81%AE%E3%82%BB%E3%83%AB%E3%81%AB%E3%83%AA%E3%82%B9%E3%83%88%E3%82%92%E8%87%AA%E7%94%B1%E5%BD%A2%E5%BC%8F%E3%81%AE%E3%83%86%E3%82%AD%E3%82%B9%E3%83%88%E3%81%A8%E3%81%97%E3%81%A6%E6%A0%BC%E7%B4%8D avoid-multiple-rows-per-user-for-identifiers-when-your-goal-is-a-user-identity-table=%E9%81%BF%E3%81%91%E3%82%8B%E3%81%B9%E3%81%8D%E6%A7%8B%E9%80%A0%E8%AD%98%E5%88%A5%E5%AD%90%E3%83%87%E3%83%BC%E3%82%BF%E3%82%921%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%81%A4%E3%81%8D%E8%A4%87%E6%95%B0%E8%A1%8C%E3%81%AB%E5%88%86%E5%89%B2%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E8%AD%98%E5%88%A5%E5%AD%90%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB%E3%82%92%E4%BD%9C%E3%82%8B%E5%A0%B4%E5%90%88 h_01KFX70V3BJE2PR7132QE27C4V=%E9%81%BF%E3%81%91%E3%82%8B%E3%81%B9%E3%81%8D%E6%A7%8B%E9%80%A0%E8%AD%98%E5%88%A5%E5%AD%90%E3%83%87%E3%83%BC%E3%82%BF%E3%82%921%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AB%E3%81%A4%E3%81%8D%E8%A4%87%E6%95%B0%E8%A1%8C%E3%81%AB%E5%88%86%E5%89%B2%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E8%AD%98%E5%88%A5%E5%AD%90%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB%E3%82%92%E4%BD%9C%E3%82%8B%E5%A0%B4%E5%90%88 additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01KFZJ2PNKB4X962VKCKSYVFFB=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01KFX6XSJYGYFF052EM8NHNMYQ=appendix-a-transactional-data-examples h_01KFX6XSJYZNCTGD5CNSKN5KF7=appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake what-does-%E2%80%9Carraylist-of-identifiers%E2%80%9D-mean=%E8%AD%98%E5%88%A5%E5%AD%90%E3%81%AE%E9%85%8D%E5%88%97%E3%83%AA%E3%82%B9%E3%83%88%E3%81%A8%E3%81%AF h_01KFX4HVTVPHZQFNRWDH9VCEZQ=%E8%AD%98%E5%88%A5%E5%AD%90%E3%81%AE%E9%85%8D%E5%88%97%E3%83%AA%E3%82%B9%E3%83%88%E3%81%A8%E3%81%AF 1-aws-s3-and-gcs-connector-parquet=aws-s3gcs%E3%82%B3%E3%83%8D%E3%82%AF%E3%82%BFparquet h_01KFX4HVTVNQZY9A8AGEBBHF6Y=aws-s3gcs%E3%82%B3%E3%83%8D%E3%82%AF%E3%82%BFparquet 2-bigquery-connector-table-preview-and-schema-screenshot=bigquery%E3%82%B3%E3%83%8D%E3%82%AF%E3%82%BF%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB%E3%83%97%E3%83%AC%E3%83%93%E3%83%A5%E3%83%BC%E3%81%A8%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%9E%E3%81%AE%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88 h_01KFX4HVTVCMB0H1B76TCK36SF=bigquery%E3%82%B3%E3%83%8D%E3%82%AF%E3%82%BF%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB%E3%83%97%E3%83%AC%E3%83%93%E3%83%A5%E3%83%BC%E3%81%A8%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%9E%E3%81%AE%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88 3-snowflake-connector-table-preview-and-schema-screenshot=snowflake%E3%82%B3%E3%83%8D%E3%82%AF%E3%82%BF%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB%E3%83%97%E3%83%AC%E3%83%93%E3%83%A5%E3%83%BC%E3%81%A8%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%9E%E3%81%AE%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88 h_01KFX4HVTVN9MSWFB7ZRT9MVCG=snowflake%E3%82%B3%E3%83%8D%E3%82%AF%E3%82%BF%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB%E3%83%97%E3%83%AC%E3%83%93%E3%83%A5%E3%83%BC%E3%81%A8%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%9E%E3%81%AE%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88 h_01KFX6XSJYF4V3ZTX8X07J0FGS=appendix-c-why-dataviews-matter-and-recommended are-businessoriented-and-easier-to-collaborate-with=%E3%83%93%E3%82%B8%E3%83%8D%E3%82%B9%E7%94%A8%E9%80%94%E3%81%AB%E9%81%A9%E3%81%97%E3%81%A6%E3%81%8A%E3%82%8A%E3%82%B3%E3%83%A9%E3%83%9C%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%97%E3%82%84%E3%81%99%E3%81%84 h_01KFX4HVTV43QFEQARSB2N49Z5=%E3%83%93%E3%82%B8%E3%83%8D%E3%82%B9%E7%94%A8%E9%80%94%E3%81%AB%E9%81%A9%E3%81%97%E3%81%A6%E3%81%8A%E3%82%8A%E3%82%B3%E3%83%A9%E3%83%9C%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%97%E3%82%84%E3%81%99%E3%81%84 are-more-privacysafe-by-design=%E8%A8%AD%E8%A8%88%E4%B8%8A%E3%82%88%E3%82%8A%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%82%92%E4%BF%9D%E8%AD%B7%E3%81%97%E3%82%84%E3%81%99%E3%81%84 h_01KFX4HVTVJA8Q3FTQB8A94MA1=%E8%A8%AD%E8%A8%88%E4%B8%8A%E3%82%88%E3%82%8A%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%82%92%E4%BF%9D%E8%AD%B7%E3%81%97%E3%82%84%E3%81%99%E3%81%84 protect-sensitive-business-data=%E6%A9%9F%E5%AF%86%E6%80%A7%E3%81%AE%E9%AB%98%E3%81%84%E3%83%93%E3%82%B8%E3%83%8D%E3%82%B9%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E4%BF%9D%E8%AD%B7 h_01KFX4HVTVF8A0PM90FA6XA0V5=%E6%A9%9F%E5%AF%86%E6%80%A7%E3%81%AE%E9%AB%98%E3%81%84%E3%83%93%E3%82%B8%E3%83%8D%E3%82%B9%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E4%BF%9D%E8%AD%B7 can-make-your-data-more-costeffective-and-performant=%E3%82%B3%E3%82%B9%E3%83%88%E5%8A%B9%E7%8E%87%E3%81%A8%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%82%92%E9%AB%98%E3%82%81%E3%82%89%E3%82%8C%E3%82%8B h_01KFX4HVTVJ70HV606Y8KE4JD1=%E3%82%B3%E3%82%B9%E3%83%88%E5%8A%B9%E7%8E%87%E3%81%A8%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%82%92%E9%AB%98%E3%82%81%E3%82%89%E3%82%8C%E3%82%8B h_01KFX6XSJY4WGJDBP5JEQXC6E3=appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform h_01KGFDYKG8KPYR7H5VBKVTXTQS=appendix-e-hashed-data-formatting-guidelines-by-media-partner" />
