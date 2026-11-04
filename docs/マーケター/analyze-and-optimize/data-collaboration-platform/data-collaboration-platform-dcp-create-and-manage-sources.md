---
title: Data Collaboration Platform（DCP）｜ソースの作成と管理
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2024-05-02T13:56:27Z'
  edited_at: '2026-10-14T09:37:47Z'
  id: 24740010687249
  locale: ja
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ja/articles/24740010687249
---
> **At a glance:** ファーストパーティデータを他のコラボレーターと安全に共有するためのソースを作成・管理します。

<div id="about-dcp-sources" />

## DCPのソースについて

Data Collaboration Platform（DCP）におけるソースとは、通常、クラウドストレージからAppsFlyerへアップロードするデータセットを指します。ソースはあらゆるコラボレーションの基盤となり、コラボレーターがオーディエンスの作成やアクティベーションに利用できるデータを提供します。この記事では、ソースの作成と管理に必要な情報をまとめて説明します。主な内容は以下のとおりです。

* [ソースデータの要件](#ソースデータの要件)
* [ソースの作成](#ソースを作成する)
* [ソースの管理](#ソースを管理する)

<div id="source-data-requirements" />

## ソースデータの要件

コラボレーター間のデータ照合率を高め、コラボレーションの成果を最大化するため、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion">事前にソースデータを準備</Anchor>しておくことを推奨します。また、すべてのソースは**以下の要件を満たす必要があります**。

<Accordion title="データ形式 （すべてのソースが対象）">

ソース内のデータは、以下の要件を満たす必要があります。

* **日付**（日付のみ）： yyyy-mm-dd（例：`2023-04-18`）
* **日付と時刻：**
  * **形式：** yyyy-MMM-dd hh:mm:ss （*例*：`2023-APR-18 15:30:35`）
  * **タイムゾーン：** UTC
* **数値：** 小数点以下は最大2桁
* **文字列の長さ：** 最大256文字
* **文字の制限：**
  * **フィールド名（列ヘッダー）：** スペースや特殊文字は使用不可
  * **その他のデータ：** 制限なし（すべての文字を使用可能）

</Accordion>

<Accordion title="テーブル列 （データウェアハウス内のソースのみ対象）">

BigQueryまたはSnowflakeのソーステーブルには、処理対象として共有するデータに加え、**日付**と**バージョン**の2列を追加する必要があります。

* **日付：**
  * **列ヘッダー：** `dt`
  * **列タイプ：** date
  * **データ形式：** yyyy-mm-dd（*例*：`2023-04-18`）
  * **補足：** BigQueryテーブルでは、この列を基準に<Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/partitioned-tables">パーティション分割</Anchor>する必要があります。
* **バージョン：**
  * **列ヘッダー：** `v`
  * **列タイプ：** string
  * **データ形式：** 数値（例：`1`、`2`、`3`、`10`）
  * **重要**DCRがこの列で新しい値を検出するたびに、新しいレポートバージョンが生成されます。レポートに必要なデータが欠けないよう、この列の値を変更する際は、ソーステーブルに完全なデータセットを登録してください。

</Accordion>

<Accordion title="ファイル名と形式 （クラウドストレージバケット内のソースのみ対象）">

Amazon S3またはGCSに保存するソースファイルは、以下のファイル名と形式の要件を満たす必要があります。

* ファイル名は<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCRの命名要件</Anchor>に準拠している必要があります。
* CSVまたはGZIP形式
  * GZIPで圧縮する元ファイルはCSV形式である必要があります。
* <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-add-connections#snowflake-outbound">データフォルダ</Anchor>あたりのデータソースファイル数：
  * **CSV：** 最大1ファイル
  * **GZIP：** 単一パートのファイルは最大1ファイル。マルチパートGZIPファイルを使用する場合は、`filename_part01.csv.gz`、`filename_part02.csv.gz` のように命名します。

</Accordion>

<div id="create-a-source" />

## ソースを作成する

**前提条件：** ソースを作成する前に、AppsFlyer DCPがソースデータの取得に使用する<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">クラウドサービスを設定</Anchor>してください。接続がまだ設定されていない場合は、ソース作成の途中で設定を求められます。

**DCPでソースを作成するには、以下の手順に従います。**

<Accordion title="ステップ1：DCPの［Sources］にアクセス">

1. AppsFlyerのサイドメニューから、［**Collaborate**］>［**Data Clean Room**］の順に選択します。

   <Image alt="Click Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="644px" />
2. ［**+ New source**］をクリックします（メインページ、または［**Sources**］タブから操作できます）。

   <Image alt="sources empty state cropped.png" src="https://files.readme.io/629d8c7c68bfbce7c2307306128b0d0cc430886dc2a58200cb635bc0044d2bd7-33193030142609.png" width="482px" />
3. ［**New source**］の画面に沿って、以下の手順を進めます。

</Accordion>

<Accordion title="ステップ2：ソース名を設定">

ソース名を入力します。ソースを識別しやすい任意の一意な名前を設定できます。必要に応じて、ソースの内容が分かる説明も追加できます（例：「2025年の全購入データ」）。

<div id="requirements-and-guidelines" />

#### 要件とガイドライン

* **ソース名**は、アカウント内の他のすべてのソースと重複しないようにしてください。重複している場合、ソースを保存できません。
* クラウド連携を使用する場合、ソース名とファイル名を一致させる必要はありません。
* ソース名の要件：
  * 文字数：2-80文字
  * 使用可能な文字：
    * 英字 `(A-Z, a-z)`
    * 数字 `(0-9)`、*ただし名前の先頭には使用できません。*
    * アンダースコア `"_"`
  * 使用できない文字：
    * スペース
    * その他の記号や特殊文字

</Accordion>

<Accordion title="ステップ3：ソースの保存場所を設定">

**ソースの保存場所を指定するには：**

1. ソースを作成する、またはすでに作成している<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#overview">接続</Anchor>を選択します。
   * アカウントに接続が定義されていない場合は、［**New connection**］ダイアログが表示され、接続の作成を求められます。<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-add-connections">こちらの手順</Anchor>に従って接続を作成します。
   * 既存の接続とは別に新しい接続を使用する場合は、［**+ New connection**］をクリックし、<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-connections">こちらの手順</Anchor>に従って作成します。
2. ソースデータの保存場所に応じて、以下の該当する手順に進みます。

**注記：** 大量のデータを扱う場合のパフォーマンスを最適化するため、データの一部が別途保存されることがあります。このデータはソースの更新時に更新され、ソースを削除すると削除されます。

<div id="source-locations-in-bigquery" />

#### BigQueryのソース保存場所

**BigQueryのソースについて保存場所の指定を完了するには：**

1. ソーステーブルがあるデータセットを選択します。
2. ソースデータがあるテーブルを選択します。

各選択肢には、接続の作成時に指定したBigQueryプロジェクトで利用可能なデータセットとテーブルがそれぞれ表示されます。

<div id="source-locations-in-snowflake" />

#### Snowflakeのソース保存場所

**Snowflakeのソースについて保存場所の指定を完了するには：**

1. ソースデータを含むshareを選択します。
2. ソーステーブルがあるschemaを選択します。
3. ソースデータがあるtableを選択します。

各選択肢には、接続の作成時に指定したSnowflakeアカウントで利用可能なshare、schema、tableがそれぞれ表示されます。

<div id="source-locations-in-cloud-storage-buckets" />

#### クラウドストレージバケットのソース保存場所

Amazon S3またはGCSを使用する場合、ソースの保存場所は、接続で指定したクラウドストレージバケットと、DCRがソース更新のたびにファイルを読み込む配下のフォルダパスで構成されます。

接続を指定すると、AppsFlyerでソース作成時に必要な配下のフォルダパスを自動生成できます。

* AppsFlyerにフォルダを生成させると、設定を簡単に進められます。一方、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">こちらの手順</Anchor>に従ってフォルダを手動で作成することもできます。

AppsFlyerでフォルダを生成する場合、追加で必要なのは**ソースフォルダ**に付ける名前だけです。（新しいレポートバージョンを実行するためにソースを更新する際、この最上位フォルダにデータを配置します。）ソースフォルダを親フォルダの配下に作成するかどうかも指定できます。– 親フォルダには通常、**input** という名前を使用します。

**クラウドストレージバケット内のソース保存場所の指定を完了するには、ソースフォルダ名を入力します。**

* デフォルトでは、表示されるソースフォルダ名は以下のようになります。
  * [ソースに付けた名前](#h_01K1ZHNZEQWRP7ZBK7XJP5F9HA)をもとに設定されます。<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCRの命名要件</Anchor>を満たしていれば、用途に合わせてフォルダ名を変更できます。
  * <strong>input という名前の親フォルダの配下に生成されることが示されます。</strong>このフォルダは、DCRにアップロードするすべてのソースの親フォルダとして使用されます。
    * ［**input**］フォルダは必須ではありません。<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCRの命名要件</Anchor>を満たしていれば、削除したり別の名前に変更したりできます。
    * 必須ではありませんが、［**input**］フォルダ、または同等の用途の別名フォルダを用意することを推奨します。特に、同じクラウドストレージバケットをデータファイルのアップロード（input）とレポートの受信（output）の両方に使用する場合は、強く推奨します。

<div id="important" />

> 🚧 **重要**
>
> フォルダパスを手動で作成した場合は、［**Source location**］セクションで指定する接続とパスが、実際に作成したパスと一致していることを確認してください。


<div id="source-location-as-local-files" />

#### ローカルファイルをソースとして使用する

ローカルファイルからソースデータをアップロードすることもできます。ただし、**ソースの保存場所にはクラウドサービスを設定することを強く推奨します**。特に大規模なデータセットや自動更新を利用する場合は重要です。ローカルファイルは、主にテストやプラットフォームの機能を確認する目的で使用します。

**ローカルファイルを使用してソースデータをアップロードするには：**

ソースの保存場所を選択する際に［**Local file system**］をクリックし、［**Next**］を選択します。これにより、デバイスからローカルファイルをアップロードできるようになります。

<Image alt="Select Local file system.png" src="https://files.readme.io/08f4797196c915b73a543c7152b5090913287c61b12fefe893d3893ca76fc4d5-33193021989393.png" width="731px" />

<div id="note" />

> 📘 **注記**
>
> * 対応ファイル形式：.CSV、.GZ（最大5GB）。
> * ローカルファイルからアップロードしたデータは180日間保存されます。
> * 更新は手動で行う必要があります。

</Accordion>

<Accordion title="ステップ4：ソースの更新方法を設定">

Data Collaboration Platform（DCP）でソースを設定する際は、そのソースをどのように更新するかを選択する必要があります。DCPでは、2つの同期方法を利用できます。**Snapshot** と **Append**。それぞれ異なるユースケースやデータフローに適しています。

* **Snapshot** — ソースを更新するたびにデータセット全体をアップロードし、既存のデータセットを新しいデータで完全に置き換える方法です。アップロードするファイルに常に最新かつ完全なデータセットが含まれる場合にのみ、この方法を選択してください。
* **Append** — データセット全体ではなく、新規または変更されたデータのみをアップロードする方法です。過去のデータセットは削除・更新されません。日次・週次レポートのような定期的なアップロードに適しています。アップロード量の削減（クラウドストレージコストの削減につながる可能性があります）、アップロード処理の高速化、レコード管理の簡素化などのメリットがあります。

<Image alt="Delta Generate folders.png" src="https://files.readme.io/105f55ff555565e97b82ecf86d58cfd2cf2a0340f83d6261fd3bd1c084b13889-38096875288977.png" width="637px" />

<div id="important-1" />

> 🚧 **重要**
>
> 選択する前に、どちらの方法が適しているかを確認してください。方法を選択して［**Generate folders**］をクリックすると、選択したクラウドサービス内にファイルパスが作成され、データアップロード方法の手順が表示されます。フォルダの重複やエラーを防ぐため、最初に選択した同期方法は、その後**1回だけ変更できます**。


<div id="snapshot-upload-requirements" />

#### Snapshotアップロードの要件

ソースを更新するたびに、以前のデータセットを完全に置き換える、自己完結型の完全なファイルをアップロードする場合に使用します。

<span id="h_01K2A7MAWT05K506384QHYA0FN"></span>**対応するクラウドサービス**

* Amazon S3
* Google Cloud Storage（GCS）
* BigQuery
* Snowflake

**<span id="h_01K2A7MAWTCYF3VAWJRRRJFNN5"></span>Snapshot更新方式では、以下のガイドラインに従ってください。**

1. **ソースフォルダのパス**

   DCPでクラウドストレージのソースを登録すると、そのソースに対するルートパス（例：`input/my_source_folder/`）が定義されます。データセットを更新するたびに、現在のすべてのレコードを含む**完全なスナップショット**をこのフォルダへアップロードします。これにより、DCPは常に最新かつ完全なデータを処理できます。
2. <span id="h_01K2A7MAWTPJ621MGBBG40N8H4"></span>**完全なスナップショットファイルのアップロード**

| ガイドライン | 重要な理由 | 対応方法 |
| --- | --- | --- |
| **完全なデータセット** | DCPでは、既存の状態を完全に置き換える必要があります。 | 差分だけでなく、すべてのレコードを含むエクスポートを生成します。 |
| **日付ごとのパーティションフォルダ（**`dt=`） | 期間による絞り込みや保持期間の管理が可能になります。 | 各スナップショットを `dt=YYYY‑MM‑DD/` 配下に配置します。 |
| **バージョン用サブフォルダ（**`v=`） | 同じ日に複数のスナップショットを保存できます。 | 最初のアップロードは `v=1/`、再試行時は `v=2/`、`v=3/` のように使用します。 |
| `data/` **サブフォルダ** | ファイルを整理するためのフォルダです。 | Parquet／CSV／Avroファイルをこのフォルダに保存します。 |
| `_SUCCESS` **マーカー** | DCPに取り込み開始のタイミングを知らせます。 | すべてのデータファイルの配置が完了したら、`_SUCCESS` という名前の空ファイルを `v=` フォルダ内にアップロードします。 |
| **対応ファイル形式とサイズ** |  | <ul><li>対応ファイル形式：.csv または .gz</li><li>最大ファイルサイズ：5GB</li></ul> |

<div id="important-2" />

> 🚧 **重要**
>
> 以下のスクリーンショットにある完全なスナップショットファイル（BI-data.csv）は、次の場所に配置する必要があります。
>
> ```
> /v=1/data/
> ```
>
> データファイルのアップロード後、空の `_SUCCESS` ファイルを次の場所に配置します。
>
> ```
> /v=1/
> ```

**フォルダ構成：**

```
s3://af-dcr-xyz/abcd9876/input/source_name1/dt=2025-mm-dd/v=1/data/
└ bucket ┘ └ tenant ┘ └ingestion┘ └source┘└snapshot date┘└ver┘└files┘
```

| セグメント | 説明 | 用途 |
| --- | --- | --- |
| `af-dcr-xyz` | S3／GCSバケット | DCPのすべてのデータを格納する最上位コンテナ |
| `abcd9876/` | テナント／ワークスペースID | 各顧客のデータを分離して保持します。 |
| `input/` | 取り込み領域 | 処理前の元データをアップロードする場所 |
| `source_name1/` | ソース名 | DCPに登録される論理データセット |
| `dt=2025-mm-dd/` | スナップショット日付 | その日のデータセット全体の状態を表します。 |
| `v=1/` | バージョン（任意） | 再試行や追加のスナップショットに対応します。 |
| `data/` | ファイル | Parquet／CSV／Avro形式のスナップショットファイル |

<span id="h_01K2A7MAWTYFHBANCV9F2NKNCV"></span>**2日分のスナップショット構成例：**

```
source_name1/
  dt=2025-08-10/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
  dt=2025-08-11/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
```

2日分のソースファイルについて完全なスナップショットをアップロードした場合（日付／バージョン／dataフォルダと \_SUCCESS ファイルをプログラムで作成）、バケット／フォルダ構成は以下のようになります。

[<Image alt="Snapshot example bucket.png" src="https://files.readme.io/a96762b43bbcae3d1265aa407e725ba885e27c3a83433d017aa30d7afaf31e37-38096860329233.png" width="219px" />](https://files.readme.io/a96762b43bbcae3d1265aa407e725ba885e27c3a83433d017aa30d7afaf31e37-38096860329233.png)


<div id="append-upload-requirements" />

#### Appendアップロードの要件

前回のアップロード以降に追加・変更されたデータだけをアップロードする場合に使用します。

Appendを使用する理由

* **効率性** — アップロード量を削減
* **データの整合性** — 変更履歴をすべて保持でき、時系列分析に活用可能
* **プライバシー対応** — レコード削除や同意管理を簡素化

**対応するクラウドサービス：** AWS S3、Google Cloud Storage（GCS）  
**注記：** BigQueryとSnowflakeはAppend方式に対応していないため、Snapshot方式を使用する必要があります。

**Append更新方式では、以下のガイドラインに従ってください。**

<span id="h_01K2A7MAWT8E6AX95VG86APXBB"></span>1.**ソースフォルダの設定**

| 手順 | 説明 |
| --- | --- |
| **バケットを作成／割り当て** | 既存のS3／GCSバケットを使用するか、AppsFlyerで用意したバケットを使用します。 |
| **ルートパスを定義** | テナント単位のパス（例：`s3://af‑dcr‑xyz/abcd1234/`）を入力ディレクトリとして設定します。 |
| **セキュリティ** | サービスユーザーには、このパスへの書き込み権限のみを付与します。 |

<span id="h_01K2A7MAWT86J2S65D99BC66PQ"></span>2.**Append（差分）ファイルのアップロード**

| ガイドライン | 重要な理由 | 対応方法 |
| --- | --- | --- |
| **アップロード頻度** | 転送コストや運用負荷を抑えられます。 | 毎日アップロードするか、7日分のフォルダをまとめて週1回アップロードします。 |
| **1日につき1フォルダ** | 日付による絞り込みが可能になり、大量データのスキャンを避けられます。 | 各日の差分データを `dt=YYYY‑MM‑DD/` に配置します。 |
| **一意なファイル名** | 誤って既存ファイルを上書きするのを防ぎます。 | ファイル名は、次の形式を参考に一意になるよう設定します：`events_2025‑08‑04.parquet` `events_2025‑08‑05.parquet` |
| **必須列** | 変更履歴を追跡するために必要です。 | ファイルには以下の列を含める必要があります。<ul><li>レコードとレポート対象期間を紐づけるための日付列。<ul><li>データの改訂を追跡するためのバージョン列。</li></ul></li></ul>**注記：** これらの列がないファイルは、DCPへの読み込み時にエラーになります。 |

<span id="h_01K2A7MAWTV3FY1GZSXQFNX4JS"></span>**フォルダ構成：**

```
s3://af-dcr-xyz/abcd1234/input/source_name/dt=2025-08-10/
└ bucket ┘ └ tenant ┘ └ ingestion ┘ └ source ┘ └ day partition ┘
```

| セグメント | 用途 |
| --- | --- |
| `af-dcr-xyz` | 顧客のS3／GCSバケット |
| `abcd1234/` | テナントまたはワークスペースID |
| `input/` | 取り込み待ちの元データ |
| `source_name/` | DCP上の論理ソース（例：CRM\_Events） |
| `dt=2025-08-10/` | 日次パーティションフォルダ |

<span id="h_01K2A7MAWTRSYFTTDKG4G0TPZR"></span>**週次の差分フォルダ構成例：**

```
source_name/
  dt=2025-08-04/
  dt=2025-08-05/
  dt=2025-08-06/
  dt=2025-08-07/
  dt=2025-08-08/
  dt=2025-08-09/
  dt=2025-08-10/
```

<span id="h_01K2A7MAWT5NDJQAYD16NRZSAQ"></span>**要点一覧：**

| 要件 | 理由 | 例 |
| --- | --- | --- |
| **週次バッチ（任意）** | アップロード回数を減らしつつ、日単位の粒度を維持できます。 | 7つの `dt=` フォルダを同階層にまとめた1バッチとしてアップロードします。 |
| **日次パーティション** | クエリやUIでの絞り込みを高速化します。 | `s3://your‑bucket/source/ dt=2025‑08‑04/ ... dt=2025‑08‑10/` |

**ポイント：** 週次でアップロードする場合でも、データは必ず日付ごとの `dt=YYYY‑MM‑DD` フォルダに分けて整理してください。

</Accordion>

<Accordion title="ステップ5：ソースフィールドをマッピング">

ソースフィールドをDCPフィールドにマッピングし、テストしたうえで設定を保存します。

1. [ソースフィールドを読み込む](#1ソースフィールドを読み込む)
2. [ソースフィールドを設定する](#2ソースフィールドを設定する)
3. [EUユーザーが含まれるか確認する](#3euユーザーが含まれるか確認する)
4. [ソースデータをテストする](#4ソースデータをテストする)
5. [ソースを保存する](#5ソースを保存する)

<div id="1-load-your-source-fields" />

#### 1.ソースフィールドを読み込む

ソースフィールドは自動的に読み込まれます。手動で読み込む必要がある場合は、ソースの保存場所に応じて以下の手順に従ってください。

**データウェアハウスのソース**

データウェアハウス（BigQueryまたはSnowflake）にあるソースからフィールドを読み込むには、［**Load fields from source**］をクリックします。

<div id="important-3" />

> 🚧 **重要**
>
> 選択したソーステーブルに必須の[日付列とバージョン列](#h_01HPKB2ERPJ5PVQ2QM5XCYZE0D)が含まれていない場合、エラーが表示されます。

**クラウドストレージバケットのソース**

クラウドストレージバケット（Amazon S3またはGCS）にあるソースからフィールドを読み込むには、プロトタイプのソースファイルをアップロードする必要があります。

ソースフィールドをDCPフィールドにマッピングするため、以下のいずれかの方法でプロトタイプをアップロードします。

* ローカルファイルからソースのプロトタイプ版をアップロードできます。
  * この方法を選択すると、AppsFlyerがソースフォルダのパスを自動的に作成します。

                                                                — または —

* 接続済みのクラウドバケットから、ソースファイルのプロトタイプ版を直接アップロードできます。
  * この方法を選択した場合は、さらに以下のいずれかを選びます。
    * AppsFlyerでソースファイル用のクラウドフォルダを自動生成する、または
    * [ソースファイル用のクラウドフォルダを手動で作成する](#h_01HPKB2ERVZ88MJ35JC66YDPAB)

**プロトタイプのソースファイルをアップロードするには、以下の該当するタブの手順に従ってください。**

<Tabs>
<Tab title="ローカルファイル">

1. ［**Map source fields**］セクションで、 ［**Load fields from source**］をクリックします。
2. 表示されたウィンドウで、 ［**Upload a local file**］を選択します。
3. アップロードするCSVまたはGZIPファイルを指定し、 ［OK］をクリックします。

</Tab>

<Tab title="接続（自動作成）">

**接続済みのクラウドバケットからファイルを読み込み、AppsFlyerでソースファイル用のクラウドフォルダを生成するには：**

1. ［**Map source fields**］セクションで、 ［**Load fields from source**］をクリックします。
2. 表示されたウィンドウで、 ［**Load from cloud bucket**］を選択します。
3. ［**Generate folders**］リンクをクリックします。
   * AppsFlyerが必要な フォルダ構成とクラウド上のソースフォルダを自動生成します（ 指定した接続内に、指定したソース フォルダ名で作成されます）。
4. ソースフォルダ構成の作成が完了すると、 ソースフォルダへのリンクを含む確認メッセージが 表示されます。表示されたリンクをクリックして、 プロトタイプファイルをソースフォルダにアップロードします。
5. ファイルのアップロードが完了したら、［**OK**］をクリックします。

</Tab>

<Tab title="接続（手動作成）">

**手動で作成したフォルダ構成からソースファイルをアップロードするには：**

1. ［**Map source fields**］セクションで、 ［**Load fields from source**］をクリックします。
2. 表示されたウィンドウで、 ［**Load from cloud bucket**］を選択します。
3. **［Generate folders］はクリックしないでください。** 代わりに、ファイルを直接 [事前に作成したソースフォルダ](#h_01HPKB2ERVZ88MJ35JC66YDPAB)へアップロードします。
4. ファイルのアップロードが完了したら、［**OK**］をクリックします。

</Tab>
</Tabs>

<div id="2-configure-the-source-fields" />

#### 2.ソースフィールドを設定する

ソースフィールドを読み込むと、各ソースフィールド（列）に対応するDCPフィールドが表示されます。各ソースフィールドを確認し、横にあるドロップダウンリストから適切なDCPフィールドを選択してマッピングします。以下の点に注意してください。

<div id="note-1" />

> 📘 **注記**
>
> * 双方がソースデータを共有する場合、対応するソース間でユーザーレベルのデータを照合できるよう、**少なくとも1つのフィールドを識別子として設定する必要があります**。識別子とは、アプリユーザーを一意に識別するフィールドです（例：CUID、AppsFlyer ID、ハッシュ化メールアドレス）。
> * アップロードしたすべてのソースフィールド（列）を設定することは必須ではありませんが、分類やデータの正確な解釈、オーディエンス作成、インサイトの提案、検証を適切に行うため、できる限り設定することが重要です。

<div id="ai-assisted-field-type-detection" />

#### AIによるフィールドタイプの自動検出

DCPでは、列名をもとにAIが各ソース列に適したDCPフィールドを提案できます。

**AIによる自動検出を有効にするには：**

1. ［**Map source fields**］セクションで、以下のバナーを探します。「フィールドのマッピングをすばやく行いたいですか？［**Activate DCP AI Assistant**］」［**Activate DCP AI Assistant**］をクリックします。
2. フィールドが読み込まれたら、［**Auto detect field types**］をクリックします。DCPが各列名を評価し、対応するDCPフィールドを提案します。
3. 保存する前に、それぞれの提案内容を確認してください。提案をそのまま採用することも、他のフィールドと同様に手動でマッピングを変更することもできます。

各フィールドは、以下のいずれかの状態になります。

* **Mapped：** AIが確度の高い一致候補を1つ特定した状態です。内容を確認して採用するか、必要に応じて手動で変更します。
* **Couldn't map：** AIが対応するフィールドを特定できなかった状態です。手動でマッピングするか、未マッピングのままにします。

<div id="limitations" />

#### 制限事項

* **列数の上限：** AIによる検出は、1ソースあたり最大100列まで対応します。100列を超えるソースでは、「limit exceeded」というメッセージが表示されます。
* **フィールド名の長さ：** 列名が100文字を超える場合、AIによる検出は利用できません。

<div id="important-4" />

> 🚧 **重要**
>
> 手動で追加したフィールドと同様、AIが提案したマッピングで [List of... タイプ](#重要-5)を使用する場合、ソースファイルはParquet形式でアップロードまたは接続する必要があります。CSVおよびGZIPファイルでは、配列型の列はサポートされません。

**フィールドを削除するには：**

* 削除するフィールドの右側にカーソルを合わせ、表示されるゴミ箱アイコンをクリックします。

**フィールドを手動で追加するには：**

データソースには現在存在しないフィールドを、オーディエンスに追加する場合に使用します。

1. ［**+ New field**］をクリックします。空のフィールドが追加されます。
2. フィールド名を入力し、タイプを選択します。

<Image alt="NewField.png" src="https://files.readme.io/8dfb70dcac2cc9a2257c6e092bc2185de74a3804bd608878eaaadf09cd903331-43749881081745.png" width="760px" />

**利用できるフィールドタイプ：**

* [**Identifier**](#identifier-とlist-of-identifiers-の違い)
  * Android ID
  * AppsFlyer ID
  * CUID
  * メールアドレス
  * ハッシュ化メールアドレス
  * ハッシュ化メールアドレス（ドットなし）
  * IDFA
  * IPアドレス
  * ID5 ID
  * MediaMath ID
  * モバイル広告ID
  * 電話番号
  * ハッシュ化電話番号（+なし）
  * プラットフォームID
  * SHA256ハッシュ化ID
  * SHA256電話番号
  * ZIP+5コード
  * ZIP+4コード
  * LUID
  * Person ID
* [**List of identifiers**](#identifier-とlist-of-identifiers-の違い)
  * ハッシュ化メールアドレス（ドットなし）のリスト
  * ハッシュ化電話番号（+なし）のリスト
  * ハッシュ化メールアドレスのリスト
  * ハッシュ化電話番号のリスト
  * メールアドレスのリスト
  * 電話番号のリスト
  * ID5 IDのリスト
  * MediaMath IDのリスト
  * モバイル広告IDのリスト
  * IDFAのリスト
  * Android IDのリスト
  * IPアドレスのリスト
* Boolean
* 日付と時刻
  * 日時
  * 日付
* DMA
  * 広告パーソナライズが有効
  * 広告ユーザーデータが有効
  * EU DMAの適用対象
* 数値
  * Double
  * 数値のリスト
  * Long
  * 数値
* テキスト
  * テキスト
  * App ID
  * テキストのリスト

<div id="identifier-vs-list-of-identifiers" />

#### **Identifier とList of identifiers の違い：**

Identifierタイプでは、1行につき1つの値を保持します（例：1行に1つのメールアドレス、または1つのCUID）。List of identifiersタイプでは、1行につき複数の値を配列として保持します（例：1行に複数のハッシュ化メールアドレスやデバイスID）。1レコードにつき複数の識別子で照合する必要があるソースで使用します。

<div id="important-5" />

> 🚧 **重要**
>
> ソース内に **List of...** タイプ（List of identifiers、List of Numbers、List of Text）へマッピングしたフィールドが1つでもある場合、ソースファイルはParquet形式でアップロードまたは接続する必要があります。CSVおよびGZファイルでは配列型の列がサポートされないため、これらの形式ではリスト型フィールドが正しく取り込まれない可能性があります。

<div id="reload-source-fields" />

#### ソースフィールドを再読み込みする

データファイルの構成を変更した場合は、その変更内容を反映するためにソースファイルを更新できます。

<div id="note-2" />

> 📘 **注記**
>
> ソースを再読み込みすると、ソース内の列名は更新後のファイル名に合わせてリセットされます。これにより、一覧にあるフィールド名とそのタイプが上書きされます。

**更新したフィールドをファイルから再読み込みするには：**

1. ［**Reload fields**］をクリックします。
2. ファイルの保存場所を選択します。
   * ローカルファイルの場合：ファイルをアップロードします。
   * クラウドサービス上のファイルの場合：［**Load from cloud bucket**］をクリックし、画面の指示に従います。
3. ［**OK**］をクリックします。更新後のフィールドが表示されます。

<div id="3-verify-eu-user-inclusion" />

#### 3.EUユーザーが含まれるか確認する

* 次の質問に対して、［**Yes**］または［**No**］を選択します。「**ソースに、EU DMA規制の適用対象となる欧州のユーザーが含まれていますか？**」

EU Digital Markets Actに関するプライバシー規制の詳細を確認してください。

<div id="4-test-the-source-data" />

#### 4.ソースデータをテストする

* ［任意］［**Test**］をクリックして、ソースフィールドの形式や有効性にエラーがないか確認します。

<div id="5-save-the-source" />

#### 5.ソースを保存する

* ［**Save**］をクリックしてソースを保存します。

確認後、新しいソースが［**Sources**］タブに追加されます。

<div id="note-3" />

> 📘 **注記**
>
> ローカルファイルからソースをアップロードした場合、ソースを保存するとフォルダ構成が自動的に作成されます。表示される確認メッセージには、ソースフォルダへのリンクも含まれます。

</Accordion>

<div id="manage-your-sources" />

## ソースを管理する

作成したソースは［**Sources**］タブに表示されます。ここでは、ソース名や構成の編集、コラボレーターとの共有、削除ができます。ただし、すでにオーディエンスで使用されているソースは削除できません。

<Accordion title="ソースを編集する">

1. ［**Sources**］タブ（**Data Clean Room**）に移動します。
2. ソース一覧で編集するソースにカーソルを合わせ、行の末尾にある編集アイコン ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) をクリックします。
3. ［**Edit source**］ページで、以下の説明に従って必要な項目を編集します。
4. ［**Save**］をクリックします。

<div id="edit-the-source-name" />

#### ソース名を編集する

ソース名を編集する際は、必ず[こちらの命名要件](#要件とガイドライン)に従ってください。

<div id="edit-the-source-location" />

#### ソースの保存場所を編集する

1. ［**Edit source**］ページ > ［**Source location**］で、別のデータ接続を選択します。
2. 該当する保存場所の詳細を選択します。
3. ［任意］[ソースをテスト](#4ソースデータをテストする)します。
4. ［**Save**］をクリックします。

<div id="edit-the-field-mapping" />

#### フィールドマッピングを編集する

1. フィールドマッピングに移動し、必要な変更を行います。フィールドを変更するか、マッピング先のDCPフィールドを更新します。
2. ［**Save**］をクリックします。

<div id="important-6" />

> 🚧 **重要**
>
> ソースの構成を変更した場合、このソースを使用しているレポート側にも新しい構成を反映する必要があります。
>
> * 削除、マッピング解除、または以前のマッピングから変更されたフィールドは、そのフィールドを使用しているレポートから自動的に削除されます。
> * 新しく追加またはマッピングしたフィールドは、レポート定義を編集して追加するまで、既存のレポートには自動的に含まれません。

</Accordion>

<Accordion title="ソースを削除する">

オーディエンスで使用されていないソースは削除できます。ソースがオーディエンスで使用されている場合、そのソースを使用しているオーディエンスが通知に表示されます。ソースを削除するには、まずそのソースに紐づくオーディエンスを削除する必要があります。共有されたソースは、ソースの所有者のみが削除できます。

1. ［**Sources**］タブ（**Data Clean Room**）に移動します。
2. ソース一覧で、削除するソースの行にカーソルを合わせます。
3. 行の右側に表示される削除アイコン ![delete_button.png](https://files.readme.io/10fbd4d4f09ddb56823a2824629f8bb9362b34c95038b3d9e747ffcde7b30381-24740010666129.png) をクリックします。
4. ダイアログで［**Delete**］をクリックして確定します。

</Accordion>

<div id="sharing-permissions" />

## 共有権限

コラボレーターにソースデータの閲覧・利用権限を付与する設定は、<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-a-collaboration">コラボレーションの作成時</Anchor>に行います。<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-sharing-permissions">共有権限</Anchor>について詳しく確認してください。

<div id="additional-information" />

## 追加情報

ここでは、参考情報や補足事項を紹介します。

<Accordion title="ストレージバケットのフォルダ構成を手動で作成する（任意）">

通常は、ソース作成時に必要なフォルダ構成をAppsFlyerで自動生成する方法が最も簡単です。ただし、フォルダを手動で作成する場合は、以下の手順で行えます。

<div id="create-a-dcr-key-folder" />

#### DCRキーフォルダを作成する

セキュリティを最大限に高めるため、バケット直下のフォルダ（「DCRキーフォルダ」）には、アカウントに割り当てられた8文字の英数字の**DCR key**を名前として使用する必要があります（例：`01bcc5fb`）。*これは、AppsFlyerアカウントに関連付けられた他のパスワードやキーとは異なるものです。*

DCRキーフォルダは通常、利用するクラウドサービスの管理画面から手動で作成します。

**アカウントのDCR keyを確認するには：**

* 画面右上の3点メニュー（アクション）をクリックし、［**DCR key**］を選択します。

[<Image alt="DCR key.png" src="https://files.readme.io/b892831ad68cffb5b8084949d759f402780536c7176aa27733c867aff6560684-43750165616657.png" width="1141px" />](https://support.appsflyer.com/hc/article_attachments/50232078980881)

DCRキーフォルダを作成すると、バケット／フォルダ構成は次のようになります。

<Image alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png" width="308px" />

<div id="top-level-input-folder" />

#### 最上位のinputフォルダ

必須ではありませんが、DCRキーフォルダの直下に最上位のinputフォルダを作成することを推奨します。このフォルダは、DCRにアップロードするファイル専用として使用します。

最上位のinputフォルダは通常、利用するクラウドサービスの管理画面から手動で作成します。

* 同じバケットを、データファイルのアップロード（input）とレポートの受信（output）の両方に使用する場合は、特に推奨します。
* <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCRの命名要件</Anchor>を満たしていれば、このフォルダには任意の名前を付けられます。識別しやすいよう、通常は `input/` という名前を使用します。

最上位のinputフォルダを作成すると、バケット／フォルダ構成は次のようになります。

<Image alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png" width="308px" />

<div id="second-level-folder-for-each-data-source" />

#### データソースごとの第2階層フォルダ

DCRでは、処理対象となる複数のデータソースファイルを定期的にアップロードできます。各データソースには、それぞれ専用のフォルダ（「データソースフォルダ」）を割り当てる必要があります。

たとえば、毎日2つのファイルをDCRへアップロードして処理する場合：*BI-data.csv* と *CRM-data.gzip* には、それぞれ専用のデータソースフォルダを割り当てます。これらのフォルダには、たとえば `BI-data/`、`CRM-data/` といった名前を付けられます。

データソースフォルダは通常、利用するクラウドサービスの管理画面から手動で作成します。

2つのデータソースフォルダを作成すると、バケット／フォルダ構成は次のようになります。

<Image alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png" width="307px" />

各データソースフォルダの配下には、ソースを更新するたびに[日付とバージョンごとのサブフォルダ](#nested-subfolders-for-each-date-and-version)を作成する必要があります。

</Accordion>

<div id="privacy-regulations" />

## プライバシー規制

ここでは、現在のプライバシー規制に関する重要な情報を説明します。

<Accordion title="GoogleのEUユーザー同意ポリシーとその影響を理解する">

GoogleはDigital Markets Act（DMA）の施行に伴い、2024年3月6日付でEUユーザー同意ポリシーを更新しました。AppsFlyerはGoogle App Attribution Partnerとして、広告主がGoogle Adsのマーケティングチャネルから最大限の価値を得られるよう支援しつつ、同ポリシーの要件に対応するために必要な変更を行いました。

<div id="note-4" />

> 📘 **注記**
>
> * GoogleによるDigital Markets Act（DMA）の施行は、すべてのプラットフォームに適用されます。
> * 詳しくは、以下を参照してください。
>   * <Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">Digital Markets Actに関するインサイトとリソース</Anchor>
>   * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">GoogleのFAQ</Anchor>

<div id="adding-consent-fields" />

#### 同意フィールドを追加する

Googleでオーディエンスをアクティベーションするためのソースを設定し、［**Yes**］を選択して「**ソースに、EU DMA規制の適用対象となる欧州のユーザーが含まれていますか？**」と回答する場合は、以下の表に記載されている追加の同意フィールドをソースファイルに含めてください。これにより、アクティベーション時に必要な情報をAppsFlyerからGoogleへ送信できます。

**追加の同意フィールドとその値：**

<table><thead><tr><th>フィールド名</th><th>値</th><th>フィールドの説明</th></tr></thead><tbody><tr><td><span id="eea"></span><code>eea</code></td><td>true／false</td><td>ユーザーは、DMAの適用対象となるEEA（欧州経済領域）内に所在していますか？</td></tr><tr><td><span id="ad_personalization"></span><code>ad_personalization</code></td><td>\*true／false</td><td>ユーザーは、パーソナライズ広告へのデータ利用についてGoogleに同意していますか？</td></tr><tr><td><span id="ad_user_data"></span><code>ad_user_data</code></td><td>\*true／false</td><td>ユーザーは、自身のユーザーデータをGoogleへ送信することに同意していますか？ </td></tr><tr><td colspan="3"><span id="when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them"></span>\*「<strong>true</strong>」の場合、AppsFlyerは、同意したユーザーについて送信されたユーザー識別子を含めます。<br/>   「<strong>false</strong>」の場合：AppsFlyerには送信されていないため、これらの識別子は含まれません。</td></tr></tbody></table>

<div id="potential-impact-on-the-audience-size" />

#### オーディエンスサイズへの影響

Googleへ送信される実際のオーディエンスサイズおよび推定オーディエンスサイズは、同意するユーザーと拒否するユーザーの数によって変動する可能性があります。

</Accordion>

<div data-zendesk-anchors="introduction=dcp%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HPKB2ERNRQG73AFA0X7XEDEF=dcp%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 source-format=%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%A6%81%E4%BB%B6 h_01HPKB2ERPANE0CAXFP9RG5YEH=%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E8%A6%81%E4%BB%B6 creating-a-source=%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B h_01HPKB2ERPX2T413N3T93YBBZB=%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B requirements-and-guidelines=%E8%A6%81%E4%BB%B6%E3%81%A8%E3%82%AC%E3%82%A4%E3%83%89%E3%83%A9%E3%82%A4%E3%83%B3 h_01K1ZHNZEQ3NSN3V7NQ34G8VC8=%E8%A6%81%E4%BB%B6%E3%81%A8%E3%82%AC%E3%82%A4%E3%83%89%E3%83%A9%E3%82%A4%E3%83%B3 source-locations-in-bigquery=bigquery%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E4%BF%9D%E5%AD%98%E5%A0%B4%E6%89%80 01HX49VY7D8KG5DCB82BP69BXV=bigquery%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E4%BF%9D%E5%AD%98%E5%A0%B4%E6%89%80 source-locations-in-snowflake=snowflake%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E4%BF%9D%E5%AD%98%E5%A0%B4%E6%89%80 01HX49VY7DXH5YN8FF0NFAJBC2=snowflake%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E4%BF%9D%E5%AD%98%E5%A0%B4%E6%89%80 source-locations-in-cloud-storage-buckets=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E4%BF%9D%E5%AD%98%E5%A0%B4%E6%89%80 01HX49VY7D3CSF4SQ79Q7CZKWX=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E4%BF%9D%E5%AD%98%E5%A0%B4%E6%89%80 01HX49VY7D307DT5VTMGHPF3WA=%E9%87%8D%E8%A6%81 local-file-system=%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%AB%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%82%92%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%A8%E3%81%97%E3%81%A6%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B h_01HX4SKEGE9NVCA6VYSR77S2DK=%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%AB%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%82%92%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%A8%E3%81%97%E3%81%A6%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B h_01K1FW3AW2AW4TPDS0ZGPQCMX3=%E3%83%AD%E3%83%BC%E3%82%AB%E3%83%AB%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%82%92%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%A8%E3%81%97%E3%81%A6%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B h_01HX4T0H6SFQJEWFETKFD1CY6S=%E6%B3%A8%E8%A8%98 h_01K29ETW94GQM9YYF5A4Y6DKB6=%E9%87%8D%E8%A6%81-1 overwrite-method-specifications=snapshot%E3%82%A2%E3%83%83%E3%83%97%E3%83%AD%E3%83%BC%E3%83%89%E3%81%AE%E8%A6%81%E4%BB%B6 snapshot-upload-requirements=snapshot%E3%82%A2%E3%83%83%E3%83%97%E3%83%AD%E3%83%BC%E3%83%89%E3%81%AE%E8%A6%81%E4%BB%B6 h_01K1G33RX95KP9TJ4002DDJBCE=snapshot%E3%82%A2%E3%83%83%E3%83%97%E3%83%AD%E3%83%BC%E3%83%89%E3%81%AE%E8%A6%81%E4%BB%B6 h_01K2A7MAWS5KR16QV0Y8AE39GW=snapshot%E3%82%A2%E3%83%83%E3%83%97%E3%83%AD%E3%83%BC%E3%83%89%E3%81%AE%E8%A6%81%E4%BB%B6 h_01K2CC62XGAVTD5JH5DYXP0947=%E9%87%8D%E8%A6%81-2 data-title=append%E3%82%A2%E3%83%83%E3%83%97%E3%83%AD%E3%83%BC%E3%83%89%E3%81%AE%E8%A6%81%E4%BB%B6 append-delta-upload-requirements=append%E3%82%A2%E3%83%83%E3%83%97%E3%83%AD%E3%83%BC%E3%83%89%E3%81%AE%E8%A6%81%E4%BB%B6 h_01K2A7MAWT7CRHY1TV5J41MM0D=append%E3%82%A2%E3%83%83%E3%83%97%E3%83%AD%E3%83%BC%E3%83%89%E3%81%AE%E8%A6%81%E4%BB%B6 h_01K2C6QNJSAH9D3M48T02JHQ3R=append%E3%82%A2%E3%83%83%E3%83%97%E3%83%AD%E3%83%BC%E3%83%89%E3%81%AE%E8%A6%81%E4%BB%B6 load-the-source-fields=1%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%82%92%E8%AA%AD%E3%81%BF%E8%BE%BC%E3%82%80 h_01HPKB2ERQTJPGG68FSEBHVVJA=1%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%82%92%E8%AA%AD%E3%81%BF%E8%BE%BC%E3%82%80 h_01HPKB2ERRZNPYVVD8GHD7PBPE=%E9%87%8D%E8%A6%81-3 configure-the-source-fields=2%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01HX64YHGHMK352E3RXHBFV0B5=2%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B 01HX6HVZ6DK2WH71JVB0J9WPBF=%E6%B3%A8%E8%A8%98-1 h_01K5AI0D3TFIELDTYPEDETECT=ai%E3%81%AB%E3%82%88%E3%82%8B%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%82%BF%E3%82%A4%E3%83%97%E3%81%AE%E8%87%AA%E5%8B%95%E6%A4%9C%E5%87%BA ai-assisted-field-type-detection=ai%E3%81%AB%E3%82%88%E3%82%8B%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%82%BF%E3%82%A4%E3%83%97%E3%81%AE%E8%87%AA%E5%8B%95%E6%A4%9C%E5%87%BA h_01K5AI0D3TLIMITATIONS=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 limitations=%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01K5AI0D3TIMPORTANT=%E9%87%8D%E8%A6%81-4 identifier-vs-list-of-identifiers=identifier-%E3%81%A8list-of-identifiers-%E3%81%AE%E9%81%95%E3%81%84 h_01KYSMJKRA2E13PH2QS671BSKG=identifier-%E3%81%A8list-of-identifiers-%E3%81%AE%E9%81%95%E3%81%84 h_01KYSJNEWS5QY5Q13Z11TNJHX1=%E9%87%8D%E8%A6%81-5 reload-source-fields=%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%82%92%E5%86%8D%E8%AA%AD%E3%81%BF%E8%BE%BC%E3%81%BF%E3%81%99%E3%82%8B h_01HX6TDNEMJFQM5FA95Y3C1QHD=%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%82%92%E5%86%8D%E8%AA%AD%E3%81%BF%E8%BE%BC%E3%81%BF%E3%81%99%E3%82%8B h_01HX6WF7YC014Z7ZX359RB5ZRZ=%E6%B3%A8%E8%A8%98-2 verify-eu-user-inclusion=3eu%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%8C%E5%90%AB%E3%81%BE%E3%82%8C%E3%82%8B%E3%81%8B%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B 01HZKZ2T33TYCQ8J59YGDYN7DK=3eu%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%8C%E5%90%AB%E3%81%BE%E3%82%8C%E3%82%8B%E3%81%8B%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B test-the-source-data=4%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E3%83%86%E3%82%B9%E3%83%88%E3%81%99%E3%82%8B h_01HX6WGD421PCWEWTN5YJ7V42H=4%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E3%83%86%E3%82%B9%E3%83%88%E3%81%99%E3%82%8B save-the-source=5%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E4%BF%9D%E5%AD%98%E3%81%99%E3%82%8B h_01HYX92EXSJNM5B2PDXEAEBNFS=5%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E4%BF%9D%E5%AD%98%E3%81%99%E3%82%8B h_01HYXC06K3ZWQE867NKBT95RFH=%E6%B3%A8%E8%A8%98-3 working-with-existing-sources=%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E7%AE%A1%E7%90%86%E3%81%99%E3%82%8B h_01HPKB2ERS5PK2P2XTC4ZMPCMC=%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E7%AE%A1%E7%90%86%E3%81%99%E3%82%8B edit-the-source-name=%E3%82%BD%E3%83%BC%E3%82%B9%E5%90%8D%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B 01J1SMACQHFEVAR8ZC6W8T0BAV=%E3%82%BD%E3%83%BC%E3%82%B9%E5%90%8D%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B edit-the-source-location=%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E4%BF%9D%E5%AD%98%E5%A0%B4%E6%89%80%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B h_01J1SM789AFJBSD0NG826P98Q4=%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E4%BF%9D%E5%AD%98%E5%A0%B4%E6%89%80%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B edit-the-source-structure=%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B h_01J1SNB66WQMBV1GQE4PDQ0NW4=%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B h_01HPKB2ERTYP6BFAESN3MHZSQG=%E9%87%8D%E8%A6%81-6 permissions=%E5%85%B1%E6%9C%89%E6%A8%A9%E9%99%90 h_01HZHBDPZ8FFQCB9DZ2Q8XSC2R=%E5%85%B1%E6%9C%89%E6%A8%A9%E9%99%90 reference=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HPKB2ERV1KK3J8YX918GCF3M=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 creating-a-dcr-key-folder=dcr%E3%82%AD%E3%83%BC%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B h_01HPKB2ERV7MQJ9CK44T92GK2G=dcr%E3%82%AD%E3%83%BC%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B toplevel-input-folder=%E6%9C%80%E4%B8%8A%E4%BD%8D%E3%81%AEinput%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80 h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=%E6%9C%80%E4%B8%8A%E4%BD%8D%E3%81%AEinput%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80 secondlevel-folder-for-each-data-source=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%94%E3%81%A8%E3%81%AE%E7%AC%AC2%E9%9A%8E%E5%B1%A4%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80 h_01HPKB2ERVVFMP81RE8ATZ6SZ8=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%94%E3%81%A8%E3%81%AE%E7%AC%AC2%E9%9A%8E%E5%B1%A4%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80 privacy-regulations-eu-digital-markets-act=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E8%A6%8F%E5%88%B6 h_01HZHBF0NZDTXAA3MY1A0BPE5E=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E8%A6%8F%E5%88%B6 h_01HZM4EFRJD483NARKDPPPPXCY=%E6%B3%A8%E8%A8%98-4 adding-consent-fields=%E5%90%8C%E6%84%8F%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B h_01HZHBF0NZSDGDYG2ZWNW4KQYD=%E5%90%8C%E6%84%8F%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B -when-%E2%80%9Ctrue%E2%80%9D-appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google%C2%A0-when-%E2%80%9Cfalse%E2%80%9D-appsflyer-abstains-from-sending-them=when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them potential-impact-on-the-audience-size=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%82%B5%E3%82%A4%E3%82%BA%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF h_01HZHBF0NZJBSXNBDFZH4YKNSH=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%82%B5%E3%82%A4%E3%82%BA%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF" />
