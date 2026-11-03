---
title: Data Clean Room — ソースの管理
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-03-27T10:58:23Z'
  edited_at: '2026-10-14T09:32:24Z'
  id: 5041487011601
  locale: ja
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ja/articles/5041487011601
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 概要： データクリーンルーム (DCR) と共有するカスタムデータソースを設定して、アトリビューションデータとマッチングさせDCRレポートを作成します。

## はじめに

多くのDCRレポートは、 **アトリビューションデータ**と**カスタムソース**のデータを照合するよう設計されています。この記事には、次の方法を含む、カスタムソースの扱いについて知っておく必要があるすべての情報が含まれています。

* DCR内の[ソース作成](/docs/data-clean-room-working-with-sources#ソースの作成)
  * [ソースに名前を付けます](/docs/data-clean-room-working-with-sources#1-name-the-source)
  * DCR がソースデータを取得する[場所を指定](/docs/data-clean-room-working-with-sources#2-specify-the-source-location)します
  * ソースの[構造を定義](/docs/data-clean-room-working-with-sources#3-define-the-source-structure)します（フィールドを指標、ディメンション、識別子としてラベル付けします）
  * [ソースを保存します](/docs/data-clean-room-working-with-sources#4-save-the-source)
* レポート処理をトリガーするための定期的な[ソースデータ更新](/docs/data-clean-room-working-with-sources#ソースを更新してレポート処理をトリガーします)
* [既存のソースの取り扱い](/docs/data-clean-room-working-with-sources#既存のソースの取り扱い)

> 🚧 **始める前に：**
>
> カスタムソースを作成する前に、まず次のことを行う必要があります。
>
> * [必須] DCR がデータを取得する<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-setting-up-cloud-services">クラウドサービスを設定します</Anchor> 。次の 2 種類のクラウドサービスがサポートされています。
> * [任意] AppsFlyerプラットフォームで<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-connections#受信接続を作成します">受信接続を作成</Anchor>し、これらのクラウドサービスをDCRに接続します。
>   * これらの接続がこれまでに設定されていない場合は、ソース作成時に設定するよう求められます。


<span id="source-format"></span>ソースは、ソース作成およびレポート処理のエラーを防ぐために、以下の要件を満たしている必要があります。

ソース内のデータは、次の要件を満たしている必要があります：

* **日時：**
  * **フォーマット:** yyyy-MMM-dd hh:mm:ss (*例*`2023-APR-18 15:30:35`2023-APR-18 15:30:352023-APR-18>)
  * タイムゾーンUTC
* **数値：** 小数点以下 最大2桁まで
* **文字列の長さ：** 最大256 文字（半角）
* **文字の制限：**
  * **フィールド名（列ヘッダー） :** スペースや特殊文字は使用できません
  * その他すべてのデータ: 制限なし（すべての文字が有効です）


<div id="table-columns" />

<Accordion title="表の列 （データウェアハウスのソースにのみ関連）">

BigQueryまたは Snowflakeのソース表には、処理のために共有されるデータに加えて、 **日付** 用と **バージョン**用の 2 つの追加列を含める必要があります

* **日付：**
  * 列のヘッダー
  * **列タイプ:** date
  * **データ形式:** yyyy-mm-dd (*例*、 `2023-04-18`2023-04-182023-04-18)
  * **追加事項：** 追加： BigQuery テーブルは、この列で <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/partitioned-tables">分割</Anchor> する必要があります
* **バージョン：**
  * 列のヘッダー
  * **列タイプ:** 文字列
  * **データ形式**: 数値 （例: `1`11, `2`22, `3`33, `10`1010）
  * <strong>重要！</strong>DCR がこの列で新しい値を検出するたびに、新しいバージョンのレポートがトリガーされます。レポートを完全なものにするには、列の値が変更されるたびに、ソースの表に完全なデータを入力するようにしてください。

</Accordion>

<div id="file-format" />

<Accordion title="ファイル名および形式（ クラウドストレージバケットのソースにのみ関連 ）">

Amazon S3 または GCS に保存されているソースファイルは、以下のファイル名および形式の要件を満たしている必要があります。

* ファイル名は<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR名称設定要件</Anchor>に準拠している必要があります
* CSV または GZIP 形式
  * （GZIP圧縮の基になるファイルは、CSVファイルである必要があります。）
* [データフォルダ](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version)毎のデータソースファイル数
  * **CSV**
  * GZIPGZIP: 最大 1つの単一部分ファイル

</Accordion>

## ソースの作成

ソースを作成するプロセスは、 <strong>以下で説明するすべてのステップで構成されます。</strong>これらは、読みやすくするためにタブに分かれています。

**ソースを作成するには、次の手順に従います：**

<div id="1-name-the-source" />

<Accordion title="#1：ソースに名前を付けます">

1. **Data Clean Room**の **ソース** タブに移動します。
2. [ **+ 新しいソース** ] ボタンをクリックします。  
   **新しいソース** ページが開きます。
3. 左上隅にソースの名前を入力します。
   * これには、DCRプラットフォームでソースを識別するのに役立つ任意の一意の名前を指定できます。
   * <strong>重要！</strong>ソース名がアカウント内の他のすべてのソースと異なることを確認してください。そうでない場合、ソースを保存できません。
   * ソース名の要件：
     * 文字数：2-80文字
     * 利用可能な有効文字：

       * 数字`(0-9)`（0-9）(0-9) - *最初の文字には使用できません*
     * 無効な文字：
       * スペース
       * その他すべての記号または特殊文字

</Accordion>

<div id="2-specify-the-source-location" />

<Accordion title="2024-02-26#2: ソースの場所を指定します">

1. ソースが作成される（または作成された）<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-setting-up-cloud-services#概要">接続</Anchor>を選択します。
   * アカウントに接続が定義されていない場合は、 <strong>New connection（新規接続）</strong>ダイアログが開き、接続を作成するように求められます。<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-working-with-connections#接続を完了します">こちらの手順</Anchor>に従って作成してください。
   * こちらの手順に従って作成してください。
2. ソースのデータの場所に基づいて、以下の関連する手順に進みます。

#### BigQueryにおけるソースの場所

BigQueryのソースの場所の指定を完了します

1. ソースの表があるデータセットを選択します。
2. ソースデータがある表を選択します。

これらの選択を行うリストには、接続作成時に指定したBigQueryプロジェクトで使用可能なデータセットと表がそれぞれ含まれています。

#### Snowflakeのソースの場所

**Snowflakeのソースの場所の指定を完了します**

1. ソースデータを含む共有を選択します。
2. ソースの表があるスキーマを選択します。
3. ソースデータがある表を選択します。

これらの選択を行うリストには、接続の作成時に指定したSnowflakeアカウントの共有、スキーマ、およびテーブルがそれぞれ含まれています。

#### クラウドストレージバケット内のソースの場所

Amazon S3またはGCSのソースの場所は、接続によって指定されたクラウドストレージバケットと、DCRが更新されるたびにソースファイルを読み込む基となるフォルダパスで構成されます。

接続を指定すると、AppsFlyerはソース作成プロセスの一部として、必要な基礎となるフォルダパスを自動生成できるようになります。

**クラウドストレージバケット内のソースの場所の指定を完了するためにソースフォルダ名を入力します。**

* デフォルトでは、表示されるソースフォルダ名は次のようになっています。
  * [ソースに付けた名前](/docs/data-clean-room-working-with-sources#1-name-the-source)に基づいています。フォルダ名は、<Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCRの名前付け要件</Anchor>に準拠している限り、必要に応じて変更できます。
  * **input**という名前の親フォルダ内に生成されることを示します。このフォルダは、DCR にアップロードするすべてのソースの親フォルダとして利用されます。
    * この**input**フォルダは必須ではなく、 <Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR の名前付け要件</Anchor>に準拠している限り、削除したり、別の名前を付けたりすることができます。
    * このフォルダは必須ではありませんが、 inputフォルダ (または別の名前の同等のフォルダ) を持つことがベストプラクティスとされています。データファイルのアップロード（入力）とレポートの受信（出力）の両方に同じクラウドストレージバケットを使用している場合には、さらに強くお勧めします。

> 🚧 **重要！**
>
> フォルダパスを手動で作成した場合は、**ソースの場所**の項目に入力した接続とパスが、手動で作成したパスと一致していることを確認してください。

</Accordion>

<div id="3-define-the-source-structure" />

<Accordion title="3.#3: ソース構造を定義します">

処理のためにDCRと共有するすべてのソースについて、AppsFlyer は、レポート作成のために、各データフィールドをどのように使用すべきかを知っておく必要があります。ソース構造の定義は以下で構成されます：

* [ソースフィールドの読み込み](/docs/data-clean-room-working-with-sources#ソースフィールドの読み込み)
* [各フィールド](/docs/data-clean-room-working-with-sources#フィールドの分類) を次のいずれかのタイプとして分類します（列）：
  * \_識別子 識別子： アプリのユニークユーザーを識別する項目（例：CUID, AppsFlyer IDなどが含まれます）/span>
    * DCRのコンテキストにおける識別子の主な目的は、対応するユーザーレベルのデータを一致させることができるようにデータソースを結合することです。
  * ディメンション ディメンション： アプリユーザーを分類する属性（例: 地域、インストール日、キャンペーンなど）/span>
  * 指標メトリック： アプリユーザーに関して収集した数値データ（収益、アプリ起動数、LTV など）
    * メトリックとして識別されるデータ項目には、 数値のみを含めることができます。

#### ソースフィールドの読み込み

以下の関連する手順を使用してソースフィールドを読み込みます。

**データウェアハウスのソース**

> 🚧 **重要！**
>
> 選択したソースの表に必要な [日付とバージョンの列](/docs/data-clean-room-working-with-sources#table-columns)が含まれていない場合は、エラーが発生します。

**クラウドストレージバケットのソース**

クラウドストレージバケット (Amazon S3 または GCS) のソースからフィールドをロードするには、プロトタイプソースファイルをアップロードする必要があります。

ソース構造を定義するために

* ソースのプロトタイプバージョンをローカルファイルからアップロードできます。
  * このオプションを選択すると、AppsFlyerは常にソースフォルダパスを自動で作成します。

                                                                - または -

* ソースファイルのプロトタイプバージョンをその接続から直接アップロードできます。
  * このオプションを選択した場合は、以下を作成する選択肢が 1 つ追加されます。
    * AppsFlyerがソースフォルダ構造を自動作成できるようにします。または
    * ソースフォルダ構造を手動で作成します。

**プロトタイプのソースファイルをアップロードするには、以下の関連するタブの手順に従います**

<Tabs>
<Tab title="ローカルファイル">

2. 開いたウィンドウで、**[Upload a local file]（ローカルファイルのアップロード）** を選択します。
3. アップロードするCSVまたはGZIPファイルを指定し、[OK] をクリックします。

</Tab>

<Tab title="接続（自動作成）">

接続からファイルをロードし、AppsFlyerでソースフォルダ構造を作成できるようにします

2. 開いたウィンドウで、<strong>[Load from connection]（接続から読み込む）</strong>を選択します。
3. <strong>[Generate folders]（フォルダの作成）</strong>リンクをクリックします。
   * AppsFlyerは、必要なフォルダ構造とソースフォルダを自動的に作成します（指定した接続上に、指定したソースフォルダ名で作成します）。
4. ソースフォルダ構造が作成されると、ソースフォルダへのリンクを含む確認メッセージが表示されます。提供されたリンクをクリックして、プロトタイプファイルをソースフォルダにアップロードします。
5. ファイルのアップロードが完了したら、**OK**をクリックします。

</Tab>

<Tab title="接続（手動作成）">

**手動で作成した構造からソースファイルをアップロードします**

2. 開いたウィンドウで、<strong>[Load from connection]（接続から読み込む）</strong>を選択します。
3. <strong>[Generate folders]（フォルダの生成）</strong>をクリック**しないでください** 。代わりに、作成したソースフォルダにファイルを直接アップロードします。
4. ファイルのアップロードが完了したら、**OK**をクリックします。

</Tab>
</Tabs>

#### フィールドの分類

フィールド読み込み後、AppsFlyerがファイルを分析し、すべてのデータフィールド（列）のリストが <strong>[Available fields]（使用可能な項目）</strong>のリストに表示されます。

**フィールドを分類します**

1. 左側の <strong>[Available fields]（使用可能なフィールド）</strong>リストで 1 つ以上のフィールドを選択し、画面中央のボタンを使用して、 [識別子、ディメンション、またはメトリック](/docs/data-clean-room-working-with-sources#3-define-the-source-structure)として分類します。
   * 項目を分類すると、画面右側の関連カテゴリ一覧に表示されます。
   * 検索バーを使用して、リスト内の項目を検索できます。
   * 割り当てられていたカテゴリからフィールドを削除するには、関連するカテゴリリストでそのフィールドを選択し、<strong>[Remove]（削除）</strong>ボタンを使用して **[Available fields]（使用可能なフィールド）** リストに戻ります。
2. DCR レポートに含める各項目を分類するまで、このプロセスを繰り返します。
   * **使用可能な項目**リスト内のすべての項目を分類する必要はありません。ただし、後でレポートで使用するには、項目を分類する必要があります。
3. [ソースを保存する](/docs/data-clean-room-working-with-sources#4-save-the-source)前にソースを編集し、その編集したソースデータのフィールドを使用する場合は、<strong>[Available fields]（使用可能なフィールド）</strong>リストの下部にある <strong>[Reload fields]（フィールドの再読み込み）</strong>リンクをクリックします。
   * ソースを再読み込みすると、[使用可能なフィールド] リストのフィールド名が上書きされますのでご注意ください。これまでに分類したフィールドは **[Identifiers]（識別子）**、**[Dimensions]（ディメンション）** または <strong>[Metrics]（指標）</strong>リストに残ります。
   * これまでに分類されたフィールドが再読み込みしたソースデータ中見つからない場合、関連するカテゴリリストに表示されてもエラーアイコンでマークされています。

> 📘 **注意**
>
> 保存後にこのソースから追加でフィールドを使用する場合は、 [ソース構造を編集](/docs/data-clean-room-working-with-sources#editing-the-source-structure)することで使用できるようになります。

</Accordion>

<div id="4-save-the-source" />

<Accordion title="4ソースを保存します">

**ソースを保存します**

2. **保存** をクリックしてソースを保存します。

   ソースが作成され、確認メッセージが表示されます。

   * ローカルファイルからソースをアップロードした場合、ソースを保存するとフォルダ構造が自動的に作成されます。表示される確認メッセージにはソースフォルダへのリンクが含まれます。

   既存のすべてのソースのリストは、データクリーンルームの <strong>Sources（ソース）</strong>項目で確認できます。

</Accordion>

## ソースを更新してレポート処理をトリガーします

AppsFlyer でデータソースファイルを処理し、それに基づくレポートを実行したい場合、毎回、新しいバージョンのファイルを、日付とバージョン番号が分かる一連のネスト化したサブフォルダ（さらに、AppsFlyerにデータの場所を通知する追加のサブフォルダ１つ）内のソースフォルダにアップロードします。

AppsFlyerは、**現在の日付と２日前**のソースファイルの新しいバージョンを継続的にスキャンします。新しいバージョンのソースファイル（ [\_SUCCESSファイル](/docs/data-clean-room-working-with-sources#_success-files)を含みます。以下で詳しく説明します。）が見つかるたびに、新しいバージョンのレポートがトリガーされます。

<div id="nested-subfolders-for-each-date-and-version" />

<Accordion title="日付とバージョンごとにネストされたサブフォルダー">

ネスト化されたサブフォルダの構造は次のとおりです。

* ソースフォルダ内 --> 各日付ごとに1つのサブフォルダ（「日付フォルダ」）
  * 形式：
  * <strong>`dt=2022-12-15/` dt=2022-12-15/</strong>例
* 各日付フォルダ内に --> その日付の各バージョンごとに1つのサブフォルダ(「バージョンフォルダ」）が存在します
  * 形式：
  * <strong>`v=1/` v=1/</strong>例
  * **注記：** 注意： バージョンフォルダーは、ファイルを 1日に 1回だけアップロードする場合でも必要です。
* 各バージョンフォルダ内に --> データの場所を示す1つのサブフォルダ（「データフォルダ」）を格納します
  * 形式：
  * データフォルダは、ソースファイルのアップロード先です。

ほとんどの場合、API呼び出し、またはその他のプログラムによる手段を使用して、データソースファイルがアップロードされるたびに日付 / バージョン / データフォルダを自動的に作成します。詳細については、クラウドサービスのAPIリファレンス（AWS、 GCS）を参照してください。

</Accordion>

<div id="_success-files" />

<Accordion title="_SUCCESS ファイル">

ソースファイルのデータフォルダへのアップロードが完了したら、名前 `_SUCCESS`\_SUCCESS\_SUCCESS の空のファイルを**バージョン**フォルダにアップロードする必要があります。これにより、新しいファイルを処理できることが AppsFlyer にアラートされます。ほとんどの場合、APIスクリプトを使用して、このファイルを自動的に生成してアップロードします。

**重要！**\_SUCCESS ファイルは、データフォルダ外に存在する`_SUCCESS`バージョン\_SUCCESSフォルダにアップロードされます。

\_SUCCESSファイルのファイル名：

* すべて大文字にする必要があります
* 前にアンダースコアを付ける必要があります `(_)`(\_) (\_)
* ファイル拡張子は含まないでください

マルチパートGZIPファイルの場合：

* `_SUCCESS`\_SUCCESS\_SUCCESS ファイルは、すべてのファイル部分のアップロードが完了した後にのみアップロードされます。

</Accordion>

<div id="example-after-uploading-files" />

<Accordion title="例（ファイルのアップロード後）">

ソースファイルを2日間アップロードした後（および、プログラムで日付 / バージョン / データフォルダと `_SUCCESS`\_SUCCESS\_SUCCESS ファイルを作成した後)、バケット / フォルダ構造は次のようになります：

<Image alt="dcr_file_structure_after_uploads.png" src="https://files.readme.io/f6e753cdf8389c0b99cad9cbf1a06261473ef87ce6f840a21ab8d9ccea20aed4-11420299723665.png" width="308px" />

</Accordion>

## 既存のソースの取り扱い

既存のソースの取り扱い方はいくつかあります。以下のプロセスは、データクリーンルームの <strong>[Sources]（ソース）</strong>タブから開始します。

* [ソース名の編集](/docs/data-clean-room-working-with-sources#editing-the-source-name)
* [ソース構造の編集](/docs/data-clean-room-working-with-sources#editing-the-source-structure)
* [ソースの削除](/docs/data-clean-room-working-with-sources#deleting-a-source)（レポートに使用されていない場合）

<div id="editing-the-source-name" />

<Accordion title="ソース名の編集">

ソース名を編集するには：

1. **Data Clean Room**の **ソース** タブに移動します。
2. ソースのリストで、編集するソースの行にカーソルを合わせます。
4. **ソースの編集**ページで、ソースの名前を編集します。
5. **[Save]（保存）** ボタンをクリックしてソースを新しい名前で保存するか、<strong>[Cancel]（キャンセル）</strong>で元に戻します。

</Accordion>

<div id="editing-the-source-structure" />

<Accordion title="ソース構造の編集">

ソース構造を編集するには：

1. **Data Clean Room**の **ソース** タブに移動します。
2. ソースのリストで、編集するソースの行にカーソルを合わせます。
4. **[Edit source]（ソースの編集）** ページでは、これまで[識別子、ディメンション、または指標](/docs/data-clean-room-working-with-sources#3-define-the-source-structure)として分類されていたフィールドが、画面の右側にある関連するカテゴリリストに表示されます。
5. 以前に分類した項目を別のカテゴリに移動するには、ソースファイルから項目を再読み込みする必要はありません。これを行うには、次を参照してください：
   1. まず、関連するカテゴリリストから選択し、**削除**ボタンを使用して **使用可能な項目** リストに戻ります。
   2. 次に、**使用可能な項目**リストから選択し、画面中央のボタンを使用して識別子、ディメンション、またはメトリックとして分類します。
6. まだ分類されていないソースファイル内の項目を処理するには、ソースの場所またはローカルファイルから項目を再ロードする必要があります。この選択を行うには、<strong>[Available fields]（使用可能なフィールド）</strong>リストの下部にある <strong>[Reload fields]（フィールドの再読み込み）</strong>をクリックします。
7. AppsFlyerがファイルを分析し、以前に分類されていないすべてのデータ項目（列）の一覧が **使用可能な項目**リストに表示されます。
   * 以前に識別子、ディメンション、または指標として分類されていた項目は、画面の右側にある関連するカテゴリリストに表示されます。
   * 以前に分類された項目がリロードされたソースファイルで見つからない場合でも、関連するカテゴリリストに表示されますが、エラーアイコンでマークされます。
8. 左側の <strong>[Available fields]（使用可能なフィールド）</strong>リストで 1 つ以上のフィールドを選択し、画面中央のボタンを使用して、識別子、ディメンション、またはメトリックとして分類します。
9. 必要な変更をすべて行ったら、<strong>[Save]（保存）</strong>ボタンをクリックしてソースを更新された構造で保存するか、<strong>[Cancel]（キャンセル）</strong>して元に戻します。

> 🚧 **重要！**
>
> このソースが使用されているレポートで、新しいソース構造を反映した対応する変更を行うことを忘れないでください。
>
> * 削除されたフィールド、未分類、または以前のカテゴリから変更されたフィールドは、使用されているすべてのレポートから自動的に削除されます。
> * 新しく追加または分類されたフィールドは、レポート定義を編集して含めるまで、既存のレポートに自動的には含まれません。

</Accordion>

<div id="deleting-a-source" />

<Accordion title="ソースの削除">

1. **Data Clean Room**の **ソース** タブに移動します。
2. ソースのリストで、編集するソースの行にカーソルを合わせます。
4. ダイアログで、ソースを削除することを確認します。
   * レポートで使用されているソースは削除できません。この場合、ソースが使用されているレポートがメッセージにリストされます。ソースを削除するには、次のいずれかを実行します：
     * 使用されているレポートを削除します。または、
     * ソース項目は、それらが使用されているレポートの定義から除去します。

</Accordion>

## 参考

<div id="manually-creating-a-folder-structure" />

<Accordion title="ストレージバケットのフォルダ構造を手動で作成します （選択した場合にのみ関連）">

一般に最も簡単な方法は、AppsFlyerがソース作成プロセスの一部として必要なフォルダ構造を自動的に生成できるようにすることです。ただし、これらのフォルダを手動で作成する場合は、次のようにすると可能です。

#### DCR キーフォルダの作成

最大限のセキュリティを確保するには、バケットの直下のフォルダ （DCRキーフォルダ） に、アカウントに割り当てられた 8文字の英数字の **DCRキー** の名前を付ける必要があります。（例： `01bcc5fb`01bcc5fb01bcc5fb）*これは、AppsFlyerアカウントに関連付けられている他のパスワードやキーとは異なりますのでご注意ください。*

DCR キーフォルダーは、通常、選択したクラウドサービスのインターフェイスを使用して手動で作成されます。

**アカウントのDCRキーを取得するには、DCRのメインページの上部にある DCRキーボタンをクリックします。**

[![dcr_key_button.png](https://files.readme.io/8d02c129ce45b19b28523419e43ec8227a9179e3bafb2b84c0a523b247061c19-16571022734353.png)](https://files.readme.io/8d02c129ce45b19b28523419e43ec8227a9179e3bafb2b84c0a523b247061c19-16571022734353.png)

DCRキーフォルダを作成すると、バケット/フォルダ構造は次のようになります。

<Image alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png" width="308px" />

#### 最上位のインプット用フォルダ

必須ではありませんが、ベストプラクティスは、DCRキーフォルダーのすぐ下に最上位のインプット用フォルダーを作成することです。このフォルダは、DCRにアップロードするファイル専用です。

最上位のインプット用フォルダーは、通常、選択したクラウドサービスのインターフェイスを使用して手動で作成されます。

* この方法は、データファイルのアップロード (入力) とレポートの受信 (出力) の両方に同じバケットを使用している場合には、さらに強くお勧めします。
* このフォルダーには、 <Anchor target="_blank" href="/marketers/ja/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCRの名称設定要件</Anchor>に準拠している限り、任意の名前を付けることができます。識別を容易にするために、通常は input/ という名前が付けられています。

最上位のインプット用フォルダを作成した後、バケット/フォルダ構造は次のようになります：

<Image alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png" width="308px" />

#### 各データソースの第2レベルのフォルダー

処理のために、さまざまなデータソースファイルを定期的に DCRにアップロードできます。これらの各データソースには、個別のフォルダ（「データソースフォルダ」）を割り当てる必要があります。

データソースフォルダは、通常、選択したクラウドサービスのインターフェイスを使用して手動で作成されます。

2つのデータソースフォルダを作成した後、バケット/フォルダ構造は次のようになります。

<Image alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png" width="307px" />

各データソースフォルダの下には、ソースが更新されるたびに、 [日付とバージョンによるネスト化したサブフォルダ](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version) を作成する必要があります。

</Accordion>

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01HPKB2ERNRQG73AFA0X7XEDEF=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01HPKB2ERPGD2PS4JBSDGYW3MC=%E5%A7%8B%E3%82%81%E3%82%8B%E5%89%8D%E3%81%AB h_01HPKB2ERPANE0CAXFP9RG5YEH=source-format h_01HPKB2ERPJ5PVQ2QM5XCYZE0D=table-columns h_01HPKB2ERPWZFZN2DSCHWNXKXX=file-format creating-a-source=%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E4%BD%9C%E6%88%90 h_01HPKB2ERPX2T413N3T93YBBZB=%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E4%BD%9C%E6%88%90 h_01HPKB2ERPQMT0NKTE5NN40KG4=1-name-the-source h_01HPKB2ERQWDMYBEPDZY17T9PG=2-specify-the-source-location source-locations-in-bigquery=bigquery%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%A0%B4%E6%89%80 h_01HPKB2ERQ28JQ2CK16RYZ38G6=bigquery%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%A0%B4%E6%89%80 source-locations-in-snowflake=snowflake%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%A0%B4%E6%89%80 h_01HPKB2ERQWFGF8MN8ZYAXWC87=snowflake%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%A0%B4%E6%89%80 source-locations-in-cloud-storage-buckets=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%A0%B4%E6%89%80 h_01HPKB2ERQZT3Y6GNZ2WWWM0M7=%E3%82%AF%E3%83%A9%E3%82%A6%E3%83%89%E3%82%B9%E3%83%88%E3%83%AC%E3%83%BC%E3%82%B8%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E5%86%85%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%A0%B4%E6%89%80 h_01HPKB2ERQK2HFDATGKV0X7GCG=%E9%87%8D%E8%A6%81 h_01HPKB2ERQ40VTVZA5DGNR907G=3-define-the-source-structure loading-source-fields=%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%81%AE%E8%AA%AD%E3%81%BF%E8%BE%BC%E3%81%BF h_01HPKB2ERQTJPGG68FSEBHVVJA=%E3%82%BD%E3%83%BC%E3%82%B9%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%81%AE%E8%AA%AD%E3%81%BF%E8%BE%BC%E3%81%BF h_01HPKB2ERRZNPYVVD8GHD7PBPE=%E9%87%8D%E8%A6%81-1 categorize-fields=%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%81%AE%E5%88%86%E9%A1%9E h_01HPKB2ERSYCFE1EYTCK550VTK=%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%81%AE%E5%88%86%E9%A1%9E h_01HPKB2ERSNT8Y9QPN03HJKHCD=%E6%B3%A8%E6%84%8F h_01HPKB2ERS55YGWY3RMRPR02Y4=4-save-the-source uploading-source-files-to-trigger-report-processing=%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E6%9B%B4%E6%96%B0%E3%81%97%E3%81%A6%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E5%87%A6%E7%90%86%E3%82%92%E3%83%88%E3%83%AA%E3%82%AC%E3%83%BC%E3%81%97%E3%81%BE%E3%81%99 h_01HPKB2ERSCPAPB6WE3354ECW9=%E3%82%BD%E3%83%BC%E3%82%B9%E3%82%92%E6%9B%B4%E6%96%B0%E3%81%97%E3%81%A6%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E5%87%A6%E7%90%86%E3%82%92%E3%83%88%E3%83%AA%E3%82%AC%E3%83%BC%E3%81%97%E3%81%BE%E3%81%99 h_01HPKB2ERSEVBTS3DR2TB6Y1AQ=nested-subfolders-for-each-date-and-version h_01HPKB2ERSJ9KNDK6CEBRQB65C=_success-files h_01HPKB2ERSJKGVE61T6J9HXTCK=example-after-uploading-files working-with-existing-sources=%E6%97%A2%E5%AD%98%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%8F%96%E3%82%8A%E6%89%B1%E3%81%84 h_01HPKB2ERS5PK2P2XTC4ZMPCMC=%E6%97%A2%E5%AD%98%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E5%8F%96%E3%82%8A%E6%89%B1%E3%81%84 h_01HPKB2ERTC48MGS0BM5SDR6XV=editing-the-source-name h_01HPKB2ERTS6DEQX0KP0EQTGSP=editing-the-source-structure h_01HPKB2ERTYP6BFAESN3MHZSQG=%E9%87%8D%E8%A6%81-2 h_01HPKB2ERVGJYJ9KW1RGX24CGV=deleting-a-source reference=%E5%8F%82%E8%80%83 h_01HPKB2ERV1KK3J8YX918GCF3M=%E5%8F%82%E8%80%83 h_01HPKB2ERVZ88MJ35JC66YDPAB=manually-creating-a-folder-structure creating-a-dcr-key-folder=dcr-%E3%82%AD%E3%83%BC%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%81%AE%E4%BD%9C%E6%88%90 h_01HPKB2ERV7MQJ9CK44T92GK2G=dcr-%E3%82%AD%E3%83%BC%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%81%AE%E4%BD%9C%E6%88%90 toplevel-input-folder=%E6%9C%80%E4%B8%8A%E4%BD%8D%E3%81%AE%E3%82%A4%E3%83%B3%E3%83%97%E3%83%83%E3%83%88%E7%94%A8%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80 h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=%E6%9C%80%E4%B8%8A%E4%BD%8D%E3%81%AE%E3%82%A4%E3%83%B3%E3%83%97%E3%83%83%E3%83%88%E7%94%A8%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80 secondlevel-folder-for-each-data-source=%E5%90%84%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E7%AC%AC2%E3%83%AC%E3%83%99%E3%83%AB%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC h_01HPKB2ERVVFMP81RE8ATZ6SZ8=%E5%90%84%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E7%AC%AC2%E3%83%AC%E3%83%99%E3%83%AB%E3%81%AE%E3%83%95%E3%82%A9%E3%83%AB%E3%83%80%E3%83%BC" />
