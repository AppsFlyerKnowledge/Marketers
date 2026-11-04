---
title: SKAN CVのデコード｜CVとイベントのマッピング
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-26T20:31:40Z'
  edited_at: '2026-10-28T09:17:44Z'
  id: 360014696297
  locale: ja
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ja/articles/360014696297
---
> **概要：** AppsFlyerが、独自に設定されたCVをデコードしてイベントに変換します。変換されたイベントは、SKANダッシュボード、ローデータ、パートナーへのポストバックに反映されます。

![SKAdNetwork_-_Custom__1_.png](https://files.readme.io/74f0d3836ee6a73f6746afa2d6d6a468c09cba696561c5a2075149ca360b78bf-34255690318097.png)

<div id="decode-skan-conversion-value" />

## SKANコンバージョン値のデコード

広告主は、<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">Conversion Studio</Anchor>の設定オプションを使用する代わりに、CVのデコードを利用できます。デコードを使用する場合は、広告主側で、アプリのロジックに従って<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/4097267-updatepostbackconversionvalue">updatePostbackConversionValue</Anchor>を設定する必要があります。

アプリ内でCVを設定する部分を除き、処理の流れ、機能、レポートの選択肢は、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKANソリューションガイド</Anchor>の説明と同じです。つまり、広告主が管理するアクティビティ期間の終了後、iOSがアドネットワークにポストバックを送信し、アドネットワークがAppsFlyerに転送します。 AppsFlyerは、広告主が定義したマッピングに従ってCVをイベントに読み替えます。その後は、SDKが設定したCVをデコードした場合と同様に処理します。

<div id="custom-conversion-valuedecode" />

## カスタムコンバージョン値｜デコード

カスタムCVのデコードを利用するには、CVのマッピングを記載したCSVファイルを、AppsFlyerプラットフォームにアップロードする必要があります。

**デコードマッピングの原則**

* 細かいCV（1〜63）と、ウィンドウ1〜3の粗いCV（low、medium、high）に対するデコードマッピングを用意します。すべての値をマッピングする必要はありません。たとえば、1、2、10、43だけをマッピングできます。
* CV 0は、常にインストールに対応します。この対応は変更できません。
* マッピング表は、CSVファイルでAppsFlyerにアップロードします。必要に応じて、更新したマッピング表をアップロードできます。
* iOSからポストバックを受信すると、後述の例のように、CVをデコードして対応するイベントを生成します。
* インストール時刻は、ポストバック到着時刻から算出します。
* イベントには、インストール時刻と同じ時刻が設定されます。
* スキーマの作成方法については、以下のマッピング例を参照してください。
* <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムアプリ内イベント</Anchor>の名前も使用できます。
  * つまり、SDKから一度も送信したことのない、新しいイベント名も使用できます。
  * アプリ内イベントを、アドネットワーク側のアプリ内イベントにマッピングできます。
  * Meta広告との連携でも同様ですが、次のセクションに示すMeta固有のルールに従う必要があります。

<div id="decode-mapping-scenario-rules" />

<Accordion title="デコードマッピング例のルール">

以下の点に注意してください。

* 細かいCVの範囲：1〜63
* 粗いCVの値：low、medium、high
* 1つのCVを、指定した1つ以上のアプリ内イベントに対応付けます。アプリ内イベントには、任意のパラメータを設定できます。
* 以下の例では、インストール日時を2月1日08:00とします。
* 次の表は、デコードマッピング表の例です。必要なCSVファイルと同様の構成になっています。表の後には、デコード処理で生成されるイベントを示しています。
* マッピング内容にかかわらず、インストールイベントは必ず生成されます。
* 収益計測：
  * 収益の通貨はUSDです。
  * 各CVの収益範囲は、min\_revenueとmax\_revenueで定義します。
  * 集計レポートとダッシュボードでは、その範囲の平均値を収益として算出します。例：min\_revenue=4、max\_revenue=10。算出される収益は7です。
  * ローデータレポートには、算出した収益（skad\_revenue）、min\_revenue、max\_revenueが含まれます。

<div id="meta-specific-rules" />

#### **Meta固有のルール**

Meta広告と連携する場合は、以下のルールに従ってください。

* 同じCVに設定する収益の最小値と最大値は、異なる値である必要があります。つまり、同じ値にはできません。
* 次の表のconversion\_value 1、2、62のように、値は重複せず、連続した順序になっている必要があります。
* event\_counter：Meta広告では、この値は使用しません。［推奨］1を設定してください。

<div id="example-decode-mapping" />

### 例：デコードマッピング

| conversion\_  <br />value | event\_  <br />name | event\_  <br />value | min\_revenue<br /><br />（下限値を含まない） | max\_revenue（上限値を含む） | event\_  <br />counter | hours\_from\_  <br />install |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | af\_purchase | `{abc}` | 0 | 3 | 1 | 24 |
| 2 | af\_purchase | `{def}` | 3 | 10 | 3 | 36 |
| 21 | event\_a |  |  |  | 1 | 24 |
| 21 | event\_b |  |  |  | 3 | 24 |
| 21 | event\_c | `{xyz}` |  |  | 2 | 24 |
| 21 | event\_d |  |  |  | 1 | 24 |
| 21 | event\_e |  |  |  | 1 | 24 |
| 21 | event\_f |  |  |  | 1 | 24 |
| 21 | event\_g |  |  |  | 1 | 24 |
| 62 | af\_purchase | \{fgh) | 10 | 17 | 2 | 72 |
| 62 | event\_a | `{klm}` |  |  | 3 | 72 |

<div id="example-a-fine-conversion-value-1" />

### 例A：細かいCV 1

| event\_name | skad\_revenue | min\_ revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 1.5 | 0 | 3 | `{abc}` |

<div id="example-b-fine-conversion-value-2" />

### 例B：細かいCV 2

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 6.5 | 3 | 10 | `{def}` |
| af\_purchase | 6.5 | 3 | 10 | `{def}` |
| af\_purchase | 6.5 | 3 | 10 | `{def}` |

<div id="example-c-fine-conversion-value-21" />

### 例C：細かいCV 21

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| event\_a |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_c |  |  |  | `{xyz}` |
| event\_c |  |  |  | `{xyz}` |
| event\_d |  |  |  |  |
| event\_e |  |  |  |  |
| event\_f |  |  |  |  |
| event\_g |  |  |  |  |

<div id="example-d-fine-conversion-value-62" />

### 例D：細かいCV 62

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 13.5 | 10 | 17 | `{fgh}` |
| af\_purchase | 13.5 | 10 | 17 | `{fgh}` |
| event\_a |  |  |  | `{klm}` |
| event\_a |  |  |  | `{klm}` |
| event\_a |  |  |  | `{klm}` |

</Accordion>

<div id="ssot-support-for-decode-mode" />

<Accordion title="デコードモードでのSSOT（Single Source of Truth）対応">

<div id="overview" />

#### 概要

デコードモードでも、SSOTによるアトリビューションを利用できるようになりました。これにより、従来はエンコードモードに限られていた、インストールの重複除去を利用できます。エンコードモードを実装せずに、ノンオーガニックの成果をより正確に計測できます。

<div id="key-benefits" />

#### 主なメリット

* インストールがAppsFlyerでアトリビューションされたか（ノンオーガニック）、されていないか（オーガニック）を、API経由でリアルタイムに確認できます。
* CVの更新時に、SSOTのアトリビューションシグナルを反映できます。
* 専用のSSOTフラグを追加したスキーマファイルをアップロードすることで、SSOT対応のデコードスキーマを使用できます。
* SSOTダッシュボードとData Lockerレポートを利用できます。
* アドネットワークをまたぐノンオーガニックインストールの重複を除去できます。
* アトリビューションとレポートの精度を高められます。
* 開発とQAを簡素化できます。

<div id="how-to-enable-ssot-for-decode-mode" />

#### デコードモードでSSOTを有効にする手順

1. **AppsFlyer IDの取得：** <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id">インストール時にSDKからAppsFlyer IDを取得</Anchor>します。
2. **SSOT APIへの問い合わせ：** AppsFlyer IDとアプリIDを使用し、そのインストールがAppsFlyerでアトリビューションされたかどうかを確認します。
   * APIは次の値を返します。  
     `"is-non-organic-install": true/false`
3. **アトリビューションシグナルの反映：** このシグナルを使用して、CVの設定ロジックを調整します。たとえば、該当するCVのエントリに`af_attribution_flag`イベントを追加し、アトリビューション結果を反映します。
4. **更新したスキーマファイルのアップロード：** [既存のデコードスキーマを使用](/docs/skan-cv-decode-map-your-cv-to-events#decode-mapping-scenario-rules)します。 SSOTの帰属判定を反映するCVには、重複除去を示す`af_attribution_flag`イベントを追加します。
5. **レポートの確認**  
   SSOTダッシュボードとData Lockerファイルに、デコードモードのデータも含まれるようになります。

<div id="faq" />

#### よくある質問

**Q：SSOTのアトリビューションフラグを取得するために、いつAPIに問い合わせればよいですか？**  
**A：**

* インストールの直後にAPIに問い合わせてください。
* アトリビューションの遅延を考慮し、10秒おきに最大5回まで問い合わせ直します。
* または、精度を確保するため、インストールから25秒以上経過してから1回問い合わせる方法もあります。

</Accordion>

<div id="zd-decode-csv-file-specification" />

<div id="decode-csv-file-specification" />

<Accordion title="デコードCSVファイルの仕様">

CVは、1つ以上のアプリ内イベントにマッピングされます。

**ファイルのルール**

* 形式：CSVファイル
* 最大行数：640行＋ヘッダー行、合計641行。
* ヘッダー行には、ここに示す列名をすべて、表記を変えずに含める必要があります。推奨：添付のサンプルファイルをテンプレートとして使用してください。 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=0&single=true&output=csv">SKAN 3</Anchor>および<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=1187444449&single=true&output=csv">SKAN 4</Anchor>のデコードCSVサンプルを参照してください。
* 列の先頭文字に、`=`、`+`、`-`、`@`を使用しないでください（編集済み）。

### デコードCSVファイルの仕様

| 列 | 値の入力が必須 | 内容 | 詳細 |
| --- | --- | --- | --- |
| conversion\_value | 以下の場合に必須：<ul><li>SKAN 3以前</li><li>SKAN 4でpostback\_sequence\_indexが0の場合</li></ul> | 1〜63の整数 | 同じ細かいCVを複数行に記載できます。詳細は、例を参照してください。 |
| coarse\_conversion\_value | SKAN 4のみが対象 | 文字列：<ul><li>low</li><li>medium</li><li>high</li></ul> | 同じ粗いCVを複数行に記載できます。 |
| event\_name | はい | 文字列 | アプリ内イベント。 AppsFlyerに既に存在するイベントである必要はありません。<br /><br />注意！アプリ内イベント名は、大文字と小文字を区別します。<br /><br />［推奨］収益のイベント名にはaf\_skad\_revenueを使用します。 |
| event\_value | いいえ | 文字列 | 開発者が設定する文字列。広告主が自社システムでデコードするためのデータを含みます。通常はJSON形式です。 |
| min\_revenue | いいえ | 整数または浮動小数点数 | min\_revenueとmax\_revenueを使用して、USDの収益範囲を設定します。<ul><li>CVに収益を関連付けない場合は、min\_revenueとmax\_revenueを空欄にします。</li><li>min\_revenueに設定した値は、範囲に含まれません。 0の場合は、0より大きい値が対象です。たとえば、0.0001のような値です。</li><li>max\_valueに設定した値は、範囲に含まれます。</li><li>例：min\_revenueが0、max\_revenueが4の場合、範囲は0.0001〜4です。</li><li>max\_revenueは、min\_revenueより大きい値である必要があります。</li></ul>**注意！** Excelでファイルを作成する場合は、CSVに$記号が入らないよう、保存前に列の書式を通貨ではなく桁区切り形式に変更してください。 |
| max\_revenue | いいえ |  | min\_revenueを入力する場合、max\_revenueには0より大きい値が必要です。<br /><br />説明は、min\_revenueを参照してください。 |
| event\_revenue\_usd | いいえ |  | 2021年6月7日以降、廃止されています。 min\_revenueとmax\_revenueを使用してください。 |
| event\_counter | はい | 整数 | <ul><li>デコード時に、そのイベントを生成する回数。通常は、ユーザーがその操作を実行した回数を表します。</li><li>最小値は1です。</li></ul>例：ユーザーが同じイベントを5回実行した場合、5件のイベントが生成されます。<br /><br />注意点：収益を送信する場合、報告される金額（USD）には、event\_counterの値が掛けられます。つまり、min\_revenue=0、max\_revenue=3、event\_counter=4の場合、報告される総収益は1.5×4＝6です。<br /><br />例を参照してください。 |
| hours\_from\_install | はい | 整数 | <ul><li>インストール後の経過時間（時間単位）</li><li>最小値：1</li><li>最大値：1,512（63日）</li><li>同じconversion\_valueに対応する行には、すべて同じ値を設定する必要があります。 conversion\_valueが異なれば、別の値を設定できます。</li></ul>AppsFlyerは、この値を使用して、以下のようにインストール日を算出・設定します。<ul><li>SKAN V4のポストバックでは、次の式を使用します。インストール日＝ポストバック到着時刻−［累積ウィンドウ期間］−［平均ポストバック遅延時間］。<ul><li>ポストバック1：インストール日＝ポストバック到着時刻−48時間−36時間</li></ul></li><li>SKAN V3のポストバックでは、次の式を使用します。インストール日＝ポストバック到着時刻−36時間−［最終アクティブ時間帯の平均値］。<ul><li>［最終アクティブ時間帯の平均値］のデフォルトは12時間です。</li><li>CVが0の場合、最終アクティブ時間帯の平均値は0に設定されます。</li></ul></li></ul> |
| postback\_sequence\_index | 必須。ただし、SKAN 4のみが対象 | 整数：<ul><li>0</li><li>1</li><li>2</li></ul> | 細かいCVの場合、受信する値は0のみです。 |

</Accordion>

<div id="upload-conversion-value-schema-file" />

<Accordion title="CVスキーマファイルのアップロード">

**開始する前に**：

* CVスキーマのCSVファイルを用意します。
* Meta広告と連携して収益を計測する場合は、スキーマが[Metaに関するルール](/docs/skan-cv-decode-map-your-cv-to-events#meta固有のルール)に従っていることを確認します。従っていない場合、Meta広告がスキーマを読み取れません。

**デコードによるSKAN計測を有効にする手順：**

1. AppsFlyerで、**［設定］**＞<strong>［SKAN Conversion Studio］</strong>に移動します。
2. オプション（⋮）をクリックし、<strong>［デコードマッピングファイルをアップロード］</strong>を選択します。
3. まだSKAN 4にアップグレードしていない場合は、SKAN 4用か、それ以前のバージョン用かを選択してファイルをアップロードします。 SKAN 4にアップグレードすると、ほかのバージョンは選択できなくなります。
4. 以下のいずれかを行います。
   * **［ファイルをドラッグ＆ドロップ］をクリックします。**
   * **更新したマッピングファイルをアップロードします。**
5. 画面の指示に従って、ファイルをアップロードします。
6. <strong>［SKAN計測］</strong>をオンにします。
7. <strong>［変更を保存］</strong>をクリックします。   
   注意：その後48〜72時間は、ダッシュボードのデータを正しく解釈できない場合があります。 iOSタイマーの影響で、デコードに使うマッピングが、CVの設定に使ったエンコードマッピングと一致しているか判断できないためです。
8. パートナーがポストバックを正しく処理できるよう、アプリ内イベントがパートナー側のイベントにマッピングされていることを確認してください。

</Accordion>

<div id="troubleshooting-the-csv-upload-errors-file" />

## CSVアップロードのエラーファイルに関するトラブルシューティング

<div id="upload-error-messages" />

<Accordion title="アップロード時のエラーメッセージ">

ファイル内の1つ以上の値が、必要な形式と一致していません：2021年6月7日にファイル形式が変更されています。この記事の例と、ファイルの形式が一致していることを確認してください。

</Accordion>

<div id="using-excel-to-format-the-event_revenue_usd-column" />

<Accordion title="Excelでのevent_revenue_usd列の書式設定">

ExcelまたはGoogleスプレッドシートでCSVを作成する場合は、CSVとして保存する前に、event\_revenue\_usd列を正しい書式に設定する必要があります。

CSVを保存した後、内容が正しい形式になっていることを確認してください。**注意**：確認にはExcelを使用せず、[テキストエディター](/docs/skan-cv-decode-map-your-cv-to-events#visual-inspection-of-the-csv-file-without-excel)を使用してください。

<div id="formatting-event_revenue_usd-cells-in-excel" />

#### Excelでのevent\_revenue\_usdセルの書式設定

図のように、Excelでは通常、数値のセルに3桁ごとの桁区切り記号が入ります。この書式は、アップロード用CSVファイルには適していません。 $記号も削除する必要があります。

![mceclip0.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

Excelでセルの書式を変更すると、修正できます。

**支出額から桁区切りのカンマと$記号を除く手順：**

1. 書式を変更するセルを選択します。
2. 右クリックし、<strong>［セルの書式設定］</strong>を選択します。  
   ［セルの書式設定］ウィンドウが開きます。
3. <strong>［数値］</strong>を選択します。  

   <Image alt="Formatnumbers.png" src="https://files.readme.io/4c1b61d1eae9149e818d4cc9793128fbdaafed5daed9acf6cbc503571475cc0e-34255643022481.png" width="381px" />

1. **［桁区切り（,）を使用する］のチェックを外します。**
2. ［任意］**小数点以下の桁数**を設定します。デフォルトは2です。指定できる最大値は5です。
3. <strong>［OK］</strong>をクリックします。  
   セルが正しい書式になります。

</Accordion>

<div id="visual-inspection-of-the-csv-file-without-excel" />

<Accordion title="Excel以外でCSVファイルを目視確認">

CSVファイルの内容は、テキストエディターで開いて確認してください。

* Windows：メモ帳、Notepad++
* macOS: TextEdit

以下は、<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?output=csv">サンプルCSVファイル</Anchor>をテキストエディターで開いた画面です。

**エディターでの表示**

![SKCustomeEditor.png](https://files.readme.io/d8677e9967a70db32e8d04c4ee835bd477b18c1cb464a9cd0e593f72ce3f3c15-34255690323217.png)

テキストエディターでCSVファイルを確認します。特に、以下の点に注意してください。

* **空白：** フィールドを区切るカンマの前後に、余分な空白がないことを確認します。 Excelでは、@trimコマンドを使用して空白を削除します。
* **event\_revenue\_usd：** event\_revenue\_usd列の値に、カンマや$記号が含まれていないことを確認します。  

  ![mceclip1.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

</Accordion>

<div id="csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

<Accordion title="Excelで作成したCSVの区切り文字がカンマにならない">

Excelが、カンマではなくセミコロン「;」などを区切り文字にしたCSVを作成する場合があります。

* これは、コンピューターの地域設定が英語以外の言語・地域になっている場合に発生します。
* 特に、地域設定でドイツ語を選択している場合によく見られます。
* 解決方法は、OSがmacOSかWindowsかによって異なります。
* <Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor>の情報やフォーラムなどで、最新の対処方法を検索してください。検索語の例：*OS名（macOSまたはWindows）Excel CSVファイル 区切り文字 変更*。

</Accordion>

<div data-zendesk-anchors="decode-skan-conversion-value=skan%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E5%80%A4%E3%81%AE%E3%83%87%E3%82%B3%E3%83%BC%E3%83%89 h_01HAMKKCKJEGCDPN5P8J6X0E8E=skan%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E5%80%A4%E3%81%AE%E3%83%87%E3%82%B3%E3%83%BC%E3%83%89 custom-conversion-value%E2%80%94decode=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E5%80%A4%E3%83%87%E3%82%B3%E3%83%BC%E3%83%89 h_01HAMKKCKJ5K6J6NNPF394ZK61=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E5%80%A4%E3%83%87%E3%82%B3%E3%83%BC%E3%83%89 h_01HAMKKCKJT7MA03SHT4X3MH4W=decode-mapping-scenario-rules facebookspecific-rules=meta%E5%9B%BA%E6%9C%89%E3%81%AE%E3%83%AB%E3%83%BC%E3%83%AB h_01HAMKKCKJDCEKCNZFSF0V6KH8=meta%E5%9B%BA%E6%9C%89%E3%81%AE%E3%83%AB%E3%83%BC%E3%83%AB example-decode-mapping=%E4%BE%8B%E3%83%87%E3%82%B3%E3%83%BC%E3%83%89%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01HAMKKCKJ5B7W8FGK01QCKN7Y=%E4%BE%8B%E3%83%87%E3%82%B3%E3%83%BC%E3%83%89%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 example-b-conversion-value-1=%E4%BE%8Ba%E7%B4%B0%E3%81%8B%E3%81%84cv-1 h_01HAMKKCKJ1ZRH00A7Q4HZ4BBK=%E4%BE%8Ba%E7%B4%B0%E3%81%8B%E3%81%84cv-1 example-b-conversion-value-2=%E4%BE%8Bb%E7%B4%B0%E3%81%8B%E3%81%84cv-2 h_01HAMKKCKJZBASWWM1VD0VXWBX=%E4%BE%8Bb%E7%B4%B0%E3%81%8B%E3%81%84cv-2 example-c-conversion-value-21=%E4%BE%8Bc%E7%B4%B0%E3%81%8B%E3%81%84cv-21 h_01HAMKKCKJ4YHMQENKNVPMV4KC=%E4%BE%8Bc%E7%B4%B0%E3%81%8B%E3%81%84cv-21 example-d-conversion-value-62=%E4%BE%8Bd%E7%B4%B0%E3%81%8B%E3%81%84cv-62 h_01HAMKKCKJP7V7D26MGM1WVDTE=%E4%BE%8Bd%E7%B4%B0%E3%81%8B%E3%81%84cv-62 h_01JQX7MY9QRH71M4S6W9CKCQ5Z=ssot-support-for-decode-mode overview=%E6%A6%82%E8%A6%81 h_01JQX7NZD3KBYTBJMS2VEMK1MT=%E6%A6%82%E8%A6%81 key-benefits=%E4%B8%BB%E3%81%AA%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 h_01JQX7PPSRCZXNTH890PP5TD1Q=%E4%B8%BB%E3%81%AA%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 how-to-enable-ssot-for-decode-mode=%E3%83%87%E3%82%B3%E3%83%BC%E3%83%89%E3%83%A2%E3%83%BC%E3%83%89%E3%81%A7ssot%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B%E6%89%8B%E9%A0%86 h_01JQX7QKV73WT10Q8QG0DKSB4S=%E3%83%87%E3%82%B3%E3%83%BC%E3%83%89%E3%83%A2%E3%83%BC%E3%83%89%E3%81%A7ssot%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B%E6%89%8B%E9%A0%86 faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01JQX8JC023CMFSD1T6N60YHR8=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HAMKKCKKJFRTXYJNWZNGF97V=decode-csv-file-specification decode-csv-file-specification::d6a1f3f1=%E3%83%87%E3%82%B3%E3%83%BC%E3%83%89csv%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%AE%E4%BB%95%E6%A7%98 h_01HAMKKCKK7G7VP6SDEHBH6383=%E3%83%87%E3%82%B3%E3%83%BC%E3%83%89csv%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%AE%E4%BB%95%E6%A7%98 h_01HAMKKCKKN7WDP6F5E4W91HQJ=upload-conversion-value-schema-file troubleshooting-the-csv-upload-errors-file=csv%E3%82%A2%E3%83%83%E3%83%97%E3%83%AD%E3%83%BC%E3%83%89%E3%81%AE%E3%82%A8%E3%83%A9%E3%83%BC%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01HAMKKCKK0QQ8AS8FZ83MZ8FH=csv%E3%82%A2%E3%83%83%E3%83%97%E3%83%AD%E3%83%BC%E3%83%89%E3%81%AE%E3%82%A8%E3%83%A9%E3%83%BC%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01HAMKKCKK3B2T9VSTYCVE0017=upload-error-messages h_01HAMKKCKKFJAE4B88QV00HYPW=using-excel-to-format-the-event_revenue_usd-column formatting-event_revenue_usd-cells-in-excel=excel%E3%81%A7%E3%81%AEevent_revenue_usd%E3%82%BB%E3%83%AB%E3%81%AE%E6%9B%B8%E5%BC%8F%E8%A8%AD%E5%AE%9A h_01HAMKKCKKKVYCWCQCAEMSBMF7=excel%E3%81%A7%E3%81%AEevent_revenue_usd%E3%82%BB%E3%83%AB%E3%81%AE%E6%9B%B8%E5%BC%8F%E8%A8%AD%E5%AE%9A h_01HAMKKCKK39C9SP7K86ER3HZK=visual-inspection-of-the-csv-file-without-excel h_01HAMKKCKK9GEBC64JE4DSDAMQ=csv-files-generated-by-excel-dont-have-commas-as-delimiters" />
