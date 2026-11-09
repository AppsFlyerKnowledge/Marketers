---
title: 広告費データのインポート
metadata:
  keywords:
    - Ad Network
    - Agency
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Xpend
    - Marketers
    - ROI360
    - Ad Networks
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
    - Ad Networks
  created_at: '2019-09-15T15:53:44Z'
  edited_at: '2026-10-28T08:43:22Z'
  id: 360002516838
  locale: ja
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ja/articles/360002516838
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** AppsFlyer ROI360のコストインポートでは、CSVファイルをアップロードまたはメールで送信することで、マーケティングにかかる広告費を漏れなく正確に把握できます。

<div id="overview" />

## 概要

コストインポートでは、次のことが可能です。

* モバイルキャンペーン、インフルエンサー施策、CTVなど、さまざまなマーケティング施策のキャンペーン広告費をAppsFlyerに取り込めます。特に、APIやアトリビューションリンク経由で広告費を送信しないメディアソースを利用する場合に役立ちます。
* 既存の広告費データをさかのぼって上書き・修正できます。

広告費は、CSVファイルをAppsFlyerにアップロードするか、メールで送信して報告します。 AppsFlyerがファイルを受信するとデータが処理され、数時間以内にダッシュボードとレポートで利用できるようになります。これにより、キャンペーンの広告費とROIの全体像を把握できます。

**注意**：

* アドネットワークは、必要な権限が付与されていれば、顧客の広告費ファイルをインポートできます。
* 代理店はデータをアップロードできません。代理店がファイルを作成し、広告主に送付してアップロードを依頼することは可能です。

<div id="procedures" />

## 手順

コストインポートで広告費データをAppsFlyerに送信するには、次の作業を行います。

1. 送信する広告費データを含む[CSVファイルを作成](/docs/import-cost-data#prepare-csv-file-with-cost-data)します。
2. 次のいずれかの方法で、ファイルをAppsFlyerに送信します。
   * AppsFlyerの管理画面から[アップロード](/docs/import-cost-data#email-file)します。
   * [メール](/docs/import-cost-data#email-file)で送信します。**注意**：CTV、PC、ゲーム機プラットフォームのアプリでは、メールでの送信のみを使用してください。

詳しい手順は、以下の各セクションを参照してください。

<div id="prepare-csv-file-with-cost-data" />

<Accordion title="広告費データを含むCSVファイルの作成">

コストインポート用のCSVファイルは、広告主、アドネットワーク、代理店が作成できます。<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv">サンプルファイルを確認</Anchor>

**CSVファイルを作成するには**：

* 以下の表に示すスキーマ、形式、ルールに従って作成します。  
  広告費データと併せて、アドネットワークが報告したクリック数とインプレッション数を含めることもできます。**注意**：ExcelまたはGoogleスプレッドシートでファイルを作成する場合は、[ExcelとGoogleスプレッドシートでの書式設定手順](/docs/import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file)に従ってください。

<div id="csv-schema" />

#### CSVスキーマ

<table><thead><tr><th><p><span>列名 </span></p><p><span>（大文字と小文字を区別）</span></p></th><th><span>形式／補足</span></th><th><span>例</span></th><th><span>必須</span></th></tr></thead><tbody><tr><td><span>date</span></td><td><ul><li><span>広告費が発生した日付</span></li><li> <span>形式：文字列</span><br/><span>推奨形式：</span><ul><li><span>YYYY-MM-DD</span></li><li><span>YYYY/MM/DD</span></li><li><span>MM-DD-YYYY</span></li><li> <span>MM/DD/YYYY </span><br/> </li></ul></li><li>未来の日付は使用できません。</li><li> <strong>推奨事項</strong>：AppsFlyerでアプリに設定したタイムゾーンと同じものを使用してください。</li><li> <strong>注意</strong>：ExcelまたはGoogleスプレッドシートでファイルを作成する場合は、<a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">こちら</a>を参照してください。 </li></ul></td><td><ul><li><span>2019-05-30</span></li><li><span>2019/05/30</span></li><li><span>5-30-2019</span></li><li>5/30/2019</li><li>05-30-2019</li><li>05/30/2019</li></ul></td><td><span>✓</span></td></tr><tr><td><span>app-id</span></td><td><ul><li><span>形式：文字列</span></li><li> <span>AppsFlyerに表示されているアプリID</span>。</li><li>1つのファイルに複数のアプリIDを含めることができます。</li><li>すべてのアプリIDが、同じ広告主アカウントに属している必要があります。</li></ul></td><td><ul><li><span>com.app.name </span></li><li><span>id12356789</span></li></ul></td><td><span>✓</span></td></tr><tr><td><span>media-source</span></td><td><ul><li><span>形式：文字列</span></li><li><span>AppsFlyerに表示されている名前と<strong>完全に一致する</strong>メディアソース名。<strong>注意：</strong>該当する場合は、末尾の_intも含めてください。</span></li><li> <span>1つのファイルに含められるメディアソースは1つのみです。</span><span></span>同じメディアソースであれば、複数のアプリを含めることができます。</li></ul></td><td><span>network_x_int</span></td><td><span>✓</span></td></tr><tr><td><span>campaign</span></td><td><ul><li> <span>形式：文字列</span><span></span> </li><li><span>キャンペーン名。アドネットワークにキャンペーン名が登録されている場合は、それと同じ名前を使用してください（大文字と小文字を区別します）。</span></li><li>複数のアプリで同じキャンペーン名を使用しないでください。</li></ul></td><td>campaign_a</td><td><p><span>✓</span></p><p><span><strong>注意</strong>：アトリビューションデータに名前とIDの両方がある場合、照合させるにはCSVにも両方を含める必要があります。</span></p></td></tr><tr><td><span>spend</span></td><td><ul><li><span>広告費の金額</span></li><li><span>小数点以下5桁まで使用可能</span></li><li><span>0も使用可能</span></li><li> <span><strong>注意</strong>： </span><ul><li>「2,874.12」のような3桁区切りのカンマは使用できません。</li><li>ExcelまたはGoogleスプレッドシートでファイルを作成する場合は、<a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">こちら</a>を参照してください。</li></ul></li></ul></td><td><p><span>2874.12345</span></p></td><td><span><span>✓</span></span></td></tr><tr><td><span>reported-clicks</span></td><td><ul><li><span>形式：整数</span></li><li><span>アドネットワークが報告したクリック数。</span></li><li><span>整数のみ。小数、桁区切りのカンマ、通貨記号、指数表記は使用できません。</span></li><li><span>0以上の値である必要があります。 0も使用できます。</span></li></ul></td><td><span>1200</span></td><td><span>いいえ</span></td></tr><tr><td><span>reported-impressions</span></td><td><ul><li><span>形式：整数</span></li><li><span>アドネットワークが報告したインプレッション数。</span></li><li><span>整数のみ。小数、桁区切りのカンマ、通貨記号、指数表記は使用できません。</span></li><li><span>0以上の値である必要があります。 0も使用できます。</span></li></ul></td><td><span>45000</span></td><td><span>いいえ</span></td></tr><tr><td><span>geo</span></td><td><ul><li><span>形式：文字列</span></li><li> <span></span><a href="https://www.iso.org/iso-3166-country-codes.html"><span>ISO 3166</span></a><span>に準拠した2文字の国コード。<strong>注意</strong>：空白を含まない2文字の値を送信してください。</span> </li><li> <span>英国にはUKを使用してください。</span><span>GBは使用しないでください。</span><br/> </li></ul></td><td><p><span>US, CN, AU</span></p></td><td><span>いいえ</span></td></tr><tr><td><span>currency</span></td><td><ul><li><span>形式：文字列</span></li><li> <a href="https://www.iso.org/iso-4217-currency-codes.html" target="_blank">ISO 4217</a>に準拠した3文字の通貨コード。 <strong>注意</strong>：先頭と末尾に空白を含まない3文字の値を送信してください。</li><li> <span>ファイル内で1つのアプリに使用できる通貨コードは1つのみです。アプリごとに</span><span>異なる通貨コードを使用することは可能です。 </span> </li></ul></td><td><span>USD, GBP, EUR, JPY</span></td><td><p><span>いいえ</span></p><p><span>空欄の場合、デフォルトでUSDになります。</span></p></td></tr><tr><td><span>campaign-id</span></td><td>形式：文字列</td><td>abc1234def</td><td rowspan="5"><p>いいえ</p><p><strong>注意</strong>：アトリビューションデータに名前とIDの両方がある場合、照合させるにはCSVにも両方を含める必要があります。</p></td></tr><tr><td><span>adset</span></td><td>形式：文字列 </td><td>my_adset_1</td></tr><tr><td><span>adset-id</span></td><td>形式：文字列</td><td>id5678ghi</td></tr><tr><td><span>ad</span></td><td>形式：文字列 </td><td>my_ad_name</td></tr><tr><td> <span>ad-</span><span>id</span> </td><td>形式：文字列 </td><td>id91011jkl</td></tr><tr><td><span>site-id</span></td><td><ul><li>形式：文字列 </li><li>広告を表示するパブリッシャーを識別する一意のID。 <a href="./about-link-structure-and-parameters#site-id-parameter" target="_blank">詳細はこちら</a> </li></ul></td><td>id1213mno</td><td>いいえ</td></tr><tr><td><span>channel</span></td><td>形式：文字列 </td><td> video</td><td>いいえ</td></tr><tr><td><span>keywords</span></td><td>形式：文字列</td><td><ul><li>better</li><li>better you app</li><li>better you online</li></ul></td><td>いいえ</td></tr><tr><td><span>agency</span></td><td><ul><li>形式：文字列</li><li>代理店名。 <code>af_prt</code>パラメータの値。</li><li>1つのファイルに含められる代理店は1社のみで、その代理店が運用するキャンペーンのみを含めることができます。</li><li>各行に代理店名が必要です。 agency列に空のセルを含めることはできません。</li><li>代理店は、ファイル内のすべてのアプリに対する権限を持っている必要があります。</li><li>ファイルをアップロードできるのは広告主のみです。代理店はデータをアップロードできません。代理店がファイルを作成し、広告主に送付してアップロードを依頼することは可能です。</li><li>同じ日付の広告費データを再送信する際に、初回の送信では含めていなかった代理店名（<code>af_prt</code>）を追加すると、広告費データが重複します。</li></ul></td><td>AgencyName</td><td>いいえ</td></tr><tr><td colspan="4"><span><strong>注意：</strong>英語以外の文字を含む名前は、UTF-8でエンコードする必要があります。</span></td></tr></tbody></table>

<div id="csv-format-and-rules" />

#### CSVの形式とルール

| ルール | 要件 |
| --- | --- |
| 使用できない文字 | 文字列形式のフィールドでは、先頭の文字に`=`、`+`、`-`、`@`を使用できません。例えば、`@example_campaign`や`=123`は使用できません。 |
| アプリ所有者 | 1つのファイルに含められる広告主（アプリ所有者）は1社のみです。同じ広告主アカウントに属する複数のアプリを含めることは可能です。 |
| ファイルの拡張子 | CSV。例：abc123.csv |
| ファイルの構造 | <ul><li>**形式**：CSV形式を使用し、各列をカンマで区切ります。</li><li>**ヘッダー行**：先頭行は、スキーマに一致するヘッダー行にします。</li><li>**データ行**：必須の列を含めます。 **注意**：データの末尾に空白がないことを確認してください。例えば、［USD ］のように**D**の後に空白がある場合は、［USD］に修正します。</li><li>**空の行**：使用不可</li><li>**同じキーを持つ重複行**：使用不可。キーは必須フィールドを組み合わせて決まります。</li><li>**空のセル：** <mark>ファイル内に空の値を含めることはできません。</mark>アップロードしないフィールドは、列ごとファイルから除外してください。</li></ul> |
| 広告の階層 | 広告費はキャンペーン単位で記録する必要があります。広告階層内のその他のディメンションは任意です。<br /><br />下位の階層のデータを一部だけアップロードしても、キャンペーン階層以下のすべてのデータが上書きされます。<br /><br />**例：** 広告セット1のキャンペーン広告費を含むファイルをインポートし、その後、同じキャンペーンの広告セット2を別のファイルでインポートすると、キャンペーンの総費用が置き換わり、広告セット2のデータのみが表示されます。キャンペーンの総費用を反映するには、インポートするファイルに広告セット1と広告セット2の両方を含める必要があります。 |

</Accordion>

<div id="upload-file" />

<Accordion title="ファイルのアップロード">

広告主とアドネットワークは、コストインポート用のCSVファイルをアップロードできます。

**前提条件**：アドネットワークは、[広告主からコストインポートの権限を付与](/docs/import-cost-data#cost-import-permissions-for-ad-networks)されている必要があります。 

**AppsFlyerの管理画面からCSVファイルをアップロードするには**：

1. AppsFlyerのサイドメニューから<strong>［設定］</strong>＞<strong>［コストインポート］</strong>を選択します。  
   コストインポートページが表示されます。
2. <strong>［＋広告費ファイルをインポート］</strong>をクリックします。  
   広告費インポートのウィンドウが開きます。
3. CSVファイルを<strong>［広告費ファイルをインポート］</strong>ウィンドウにドラッグします。  
   ファイルを処理中であることを示すメッセージが表示されます。
4. アップロード中にエラーメッセージが表示された場合は、エラーを修正し、該当する手順をやり直してください。
5. <strong>［コストインポート：ファイルの概要］</strong>ウィンドウが開きます。
6. 次のいずれかの操作を行います。
   * アップロードを中止する場合は、<strong>［インポートをキャンセル］</strong>をクリックします。
   * インポートを完了する場合は、<strong>［ファイルをインポート］</strong>をクリックします。  
     「完了しました！」というメッセージが表示されます。
   * エラーメッセージが表示された場合は、[エラーメッセージの対処方法](#error-messages-and-solutions)に従ってください。
7. <strong>［別のファイルをインポート］</strong>または<strong>［完了］</strong>をクリックします。

</Accordion>

<div id="email-file" />

<Accordion title="ファイルのメール送信">

広告主とアドネットワークは、コストインポート用のCSVファイルをメールで送信できます。

**前提条件**：

* **広告主**： 
  * 送信元メールアドレスは、AppsFlyerに登録済みのユーザーのものである必要があります。
* **アドネットワーク**：
  * 送信元メールアドレスは、AppsFlyerに登録済みのユーザーのものである必要があります。
  * [広告主からコストインポートの権限を付与](/docs/import-cost-data#cost-import-permissions-for-ad-networks)されている必要があります。

**CSVファイルをメールで送信するには**：

1. [メールインポート用トークン](/docs/import-cost-data#token-for-email-import)を取得します。
   1. AppsFlyerのサイドメニューから<strong>［設定］</strong>＞**［コストインポート］を選択します。**
   2. ページ右上の<strong>［メールインポート用トークン］</strong>をクリックします。
   3. トークンをコピーして保存します。
2. 次の内容でメールを作成します。
   * **宛先**：`adspend-upload@appsflyer.com`
   * **CC：自動返信による処理結果を共有するユーザー**
   * **件名**：メールインポート用トークンを件名に貼り付けます。
   * **添付ファイル**：データを含むCSVファイル。
3. メールを送信します。
   * ファイルの受信・処理が完了すると、処理の詳細、検出された問題やエラーをまとめたステータスメールが届きます。このメールは、ファイル送信時のメールに含まれるすべての関係者と、広告主の管理者に送信されます。エラーが見つかった場合は、[エラーメッセージの対処方法](#error-messages-and-solutions)に従ってください。
   * 送信したファイルのステータスは、[コストインポートダッシュボード](/docs/import-cost-data#error-messages-and-solutions)で確認できます。

</Accordion>

<div id="dashboard" />

## ダッシュボード

コストインポートダッシュボードでは、ファイルのアップロードと、過去にアップロードしたファイルの詳細の確認ができます。

<div id="cost-import-dashboard" />

<Accordion title="コストインポートダッシュボード">

コストインポートダッシュボードを開くには、AppsFlyerのサイドメニューから<strong>［設定］</strong>＞<strong>［コストインポート］</strong>を選択します。

インポート済みファイルについて確認できる情報を、以下の表に示します。

| 列名 | 説明 |
| --- | --- |
| CSVファイル名 | AppsFlyerにインポートした広告費ファイルの名前。 |
| アップロード日 | ファイルをインポートした日付。 |
| メディアソース | ファイルに含まれるメディアソース。 |
| 対象期間 | ファイル内で広告費が発生した最初の日付と最後の日付。 |
| 一致した行（%） | ファイル内で、広告費がアトリビューションデータと一致した行の割合。[詳細はこちら](#matched-rows)。 |
| ステータス | インポートしたファイルのステータス：<ul><li>**成功**：処理が正常に完了しました。広告費が記録され、AppsFlyerのダッシュボードとレポートで利用できます。</li><li>**検証エラー**：AppsFlyer側のシステムの問題です。 10分待ってから再試行してください。再び失敗した場合は、AppsFlyerサポートにお問い合わせください。</li><li>**権限なし**：トークンに、このアプリの処理を行う権限がありません。<ul><li>広告主：アプリIDが正しいことを確認してください。</li><li>アドネットワーク：コストインポートの権限を付与済みか、広告主に確認してください。</li></ul></li><li>**取り消し済み**：処理が正常に完了しました。ファイルのデータは、他のデータで上書き・置換されています。</li></ul> |
| 操作 | <ul><li>ファイル単位：ファイル内のすべてのアプリに対する権限がある場合、次の操作ができます。<ul><li>**［CSVファイルをダウンロード］**：インポートしたCSVファイルのコピーを取得します。</li><li><strong>［不一致レポートをダウンロード］</strong>で、ファイル内のすべてのアプリのレポートを取得できます。詳しくは、この表の「一致した行」を参照してください。</li></ul></li><li>アプリ単位：特定のファイルをクリックすると、そのアプリに対して行われたすべてのコストインポートの情報が表示されます。選択したファイルだけでなく、他のファイルからのインポートも含まれます。アプリに対する権限がある場合、次の操作ができます。<ul><li>**アプリのデータをダウンロードします。**</li><li><strong>［不一致レポートをダウンロード］</strong>で、そのアプリのレポートを取得します。</li><li>選択したアプリのコストインポートを**取り消し**ます。</li></ul></li></ul> |

</Accordion>

<div id="matched-rows" />

<Accordion title="一致した行">

行の照合とは、インポートした広告費と、AppsFlyerに記録されたアトリビューションデータを照合する処理です。メディアソース、キャンペーン、広告セット、広告など、利用可能なすべてのディメンションの名前（IDではありません）を使用して照合します。すべて一致した行には、is-matching=TRUEが設定されます。

一致したかどうかにかかわらず、広告費は記録され、AppsFlyerのダッシュボードとレポートで利用できます。

一致した行の割合は、コストインポートダッシュボードに表示されます。想定外の不一致行がある場合や、一致した行の割合（%）が想定より高い場合は、次の手順で確認します。

* 不一致レポートをダウンロードし、原因を調べます。不一致レポートには「is-matched」列があり、各行にTRUE（一致）またはFALSE（不一致）が設定されます。
* 必要に応じて、インポートを取り消します。
* 詳しくは、この表の「操作」を参照してください。

</Accordion>

<div id="additional-information" />

## 補足情報

<div id="using-excel-or-google-sheets-to-prepare-csv-file" />

<Accordion title="ExcelまたはGoogleスプレッドシートでのCSVファイルの作成">

ExcelまたはGoogleスプレッドシートでCSVファイルを作成する場合は、CSV形式で保存する前に、date列（日付）とspend列（広告費）の書式を正しく設定する必要があります。 CSVファイルを保存した後に、内容の形式が正しいことを確認してください。以下の手順に従って、次の作業を行います。

* 日付セルの書式設定。
* spendセルの書式設定。
* 内容の形式の確認。

<div id="format-date-cells" />

#### 日付セルの書式設定

**Excelで日付セルをYYYY-MM-DD形式に設定するには**：

1. 書式を設定するセルを選択します。
2. 右クリックし、<strong>［セルの書式設定］</strong>を選択します。  
   セルの書式設定ウィンドウが開きます。  
   <Image align="center" alt="Formatdate..png" src="https://files.readme.io/43d0f370f299d73b8ce93fec1c912cb7525d0071db779a64a58f5917df2a5531-360004042458.png" width="379px" />
3. <strong>［ユーザー定義］</strong>を選択します。
4. ［種類］フィールドに**YYYY-MM-DD**と入力します。
5. <strong>［OK］</strong>をクリックします。  
   日付の書式が設定されます。

<div id="formatting-spend-cells" />

#### spendセルの書式設定

Excelでは通常、以下の画像のように、数値のセルに3桁区切りのカンマが設定されます。この書式はコストインポート用ファイルには適していません。

<Image align="center" alt="mceclip1.png" src="https://files.readme.io/d54e21ddd937dfe25a33bb96193761a5a724c22a35a55bb7d71eb03a6433d7ed-360003949177.png" width="291px" />

**spendセルの3桁区切りのカンマを無効にするには**：

1. 書式を設定するセルを選択します。
2. 右クリックし、<strong>［セルの書式設定］</strong>を選択します。  
   セルの書式設定ウィンドウが開きます。
3. <strong>［数値］</strong>を選択します。  
   <Image align="center" alt="Formatnumbers.png" src="https://files.readme.io/4c1b61d1eae9149e818d4cc9793128fbdaafed5daed9acf6cbc503571475cc0e-34255643022481.png" width="381px" />
4. <strong>［桁区切り（,）を使用する］</strong>のチェックを外します。
5. 任意で、<strong>［小数点以下の桁数］</strong>を設定します。デフォルトは2桁です。最大5桁まで指定できます。
6. <strong>［OK］</strong>をクリックします。  
   セルの書式が正しく設定されます。

<div id="verify-content-format" />

#### 内容の形式の確認

**内容の形式を確認するには**：

1. エディターでファイルを開きます。
   * Windows：メモ帳、Notepad++
   * macOS：テキストエディット
2. 特に以下の点を確認してください。
   * **空白：** フィールドを区切るカンマの前後で、値の先頭や末尾に不要な空白がないことを確認してください。 Excelでは、@trimコマンドで空白を削除できます。
   * **日付：** 日付セルがYYYY-MM-DD形式になっていることを確認してください。
   * **広告費：** spendセルにカンマが含まれていないことを確認してください。
   * **区切り文字**：カンマである必要があります。セミコロンになっている場合：
     * コンピューターの地域設定が英語以外の言語・地域、特にドイツ語に設定されていると、この問題が発生することがあります。
     * 対処方法は、コンピューターのOS（macOSまたはWindows）によって異なります。
     * 解決方法は、<Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor>やその他のフォーラムで最新の案内を検索してください。検索語句の例：OS名（macOSまたはWindows）、Excel、CSVファイルの区切り文字の変更。

以下の画像は、[サンプルCSVファイル](https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv)をエディターで開いた画面です。

<Image align="center" alt="mceclip1.png" src="https://files.readme.io/1398c5e9bad7a46b697e3b21030e64d656162e33a4a63f39475c64993bbe7a72-360003996197.png" width="672px" />

</Accordion>

<div id="token-for-email-import" />

<Accordion title="メールインポート用トークン">

メールインポート用トークンは、メールの送信者にコストインポート用ファイルの送信権限があることを確認するために使用します。

広告主とアドネットワークでは、トークンが異なります。

* 広告主のトークン：
  * 同じトークンを、アカウント内のすべてのアプリに使用できます。
  * アカウント内のどのユーザーでも取得できます。
* アドネットワークのトークン：
  * すべての広告主に同じトークンを使用します。

広告主とアドネットワークの間でトークンを共有しないでください。

</Accordion>

<div id="cost-import-permissions-for-ad-networks" />

<Accordion title="アドネットワークのコストインポート権限">

アドネットワークがコストインポートを利用するには、アプリごとに広告主から権限を付与される必要があります。

**アドネットワークにコストインポートの権限を付与するには：**

1. AppsFlyerで、**広告主**がサイドメニューから<strong>［コラボレーション］</strong>＞**［有効な連携］を選択します。**   
   連携済みパートナーページが表示されます。
2. 連携済みパートナーを選択します。
3. <strong>［権限］</strong>タブを開きます。
4. <strong>［アドネットワークの権限］</strong>が有効になっていない場合は、有効にします。
5. 任意で、アカウントユーザーを追加します。
6. <strong>［コストインポートの使用］</strong>を有効にします。
7. <strong>［権限を保存］</strong>をクリックします。

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## トラブルシューティング・仕様・制限事項

<div id="error-messages-and-solutions" />

<Accordion title="エラーメッセージと対処方法">

コストインポートで表示されるエラーメッセージと対処方法を、以下の表に示します。

| エラーメッセージ | 説明 | 対処方法 |
| --- | --- | --- |
| ファイルに指定されたアプリIDが、AppsFlyerに1つも存在しません。アプリIDが正しいことを確認してください。 | アカウントにアプリIDが存在しません。 | アプリIDを変更して再送信してください。 |
| 行[line name]の列数が正しくありません。列数は[number]列である必要がありますが、[number]列が指定されています。 | ファイル内のすべての列に値が必要です。 | 設定したヘッダーに合わせて、ファイル内の値を修正してください。 |
| ファイルのヘッダーに「media-source」がありません。 | <ul><li>ファイルのヘッダーにmedia-sourceがありません。</li><li>列名は、スキーマに示す名前と完全に一致している必要があります。</li></ul> | ヘッダー名としてmedia-sourceを追加してください。 |
| ファイルに含められるメディアソースは1つのみです。ファイル内に複数のメディアソースが見つかりました：[number of media sources]。 | ファイルに複数のメディアソースが含まれています。 Excel上では見えない空の行や、形式が不正な行がCSV内にある場合も、このエラーが発生することがあります。 | Notepad++などのテキストエディターでファイルを開き、空の行や形式が不正な行を削除してください。ファイルを保存し、再度アップロードしてください。ファイルに複数のメディアソースが含まれる場合は、メディアソースごとにファイルを分けてください。 |
| [field]に指定された値[value]は、この列で使用できません。 | 列のデータ形式が正しくありません。例えば、日付がyyyy-mm-ddではなくdd-mm-yyになっています。 | 形式を修正して再送信してください。 |
| 1つのアプリに複数の通貨が指定されています。ファイル内では、アプリごとに1つの通貨を使用してください。検出された通貨数：%number of currencies%。 | 1つのアプリで使用できる通貨は1つのみです。 | 通貨を1つに揃えて再送信してください。 |
| ファイルのヘッダーに、対応していない列があります：[file headers] | ファイルのヘッダーがスキーマと一致していません。列名は、スキーマに示す名前と完全に一致している必要があります。 | 対応していない列を削除して再送信してください。 |
| ファイルのヘッダーに必須の列がありません：[file headers] | ファイルのヘッダーに必須の列がありません。 | 不足している列と値を追加して再送信してください。 |
| アプリのデータに未来の日付が含まれています：[date] | 未来の日付は使用できません。 | 日付を本日以前に修正し、再送信してください。 |
| ファイルが空です。処理するデータがありません。 | ファイルが空です。 | ファイルにデータを入力して再送信してください。 |
| 次の2行は、ディメンションが同じため競合しています。同じディメンションの組み合わせに対する広告費は、1行にまとめてください。 [conflicting rows] | キー（必須）フィールドが同じ行が複数あります。 | 重複する行を削除して再送信してください。 |
| ファイルに含められるのは、1つの広告主アカウントのデータのみです。ファイル内に異なる広告主が見つかりました：[advertiser names] | パートナーによるアップロードでは、複数の広告主のデータをまとめることはできません。 | 広告主ごとにファイルを分けてアップロードしてください。 |
| アカウントにアプリ[app ID]が存在しません。アプリIDを確認してください。 | アプリIDが存在しません。 | アプリIDを修正して再送信してください。 |
| アプリ[app ID]の地域（国）コードが見つかりませんでした。 ISO 3166の2文字のコードを使用してください。 | 地域が存在しません。 | 地域コードを修正して再送信してください。 |
| アプリ[app ID]の通貨コードが見つかりませんでした。 ISO 4217の3文字のコードを使用してください。 | 通貨が存在しません。 | 有効な通貨に変更して再送信してください。 |
| ファイル内の1つ以上のアプリに検証エラーがありました。詳しくは、ファイルの情報を確認してください。 | ファイルに複数のエラーがあります。 | ファイルをダウンロードし、エラーを確認してください。 |
| ファイルの処理中に内部エラーが発生しました。再度アップロードしてください。 | <ul><li>ファイル処理のバックエンド側で問題が発生しています。</li><li>通常は一時的な問題です。</li></ul> | 1時間待ってから、再度アップロードしてください。 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| アドネットワーク | 対応。<br /><br />例外：<ul><li>Meta広告</li><li>X広告</li><li>ASA</li></ul> |
| 代理店 | <ul><li>代理店はデータをアップロードできません。代理店がファイルを作成し、広告主に送付してアップロードを依頼することは可能です。</li><li>CSVファイルには、代理店名を記載したagency列が必要です（代理店名はaf\_prtパラメータの値です）。 [CSVスキーマを参照](/docs/import-cost-data#ad-spend-csv-schema)</li></ul> |
| 運用媒体の開示設定 | 非対応 |
| アプリ固有のタイムゾーン | 対応 |
| アプリ固有の通貨 | 対応。キャンペーンの広告費は、アプリ固有の通貨に換算されます。 |
| キャンペーン名 | 複数のアプリで同じキャンペーン名を使用すると、一方のアプリの広告費が両方に適用されるため、同じ名前は使用できません。 |
| フィールド名 | キャンペーン階層のフィールド名がアトリビューションデータの表記と一致しない場合、別々に集計されます。 <br /><br />例えば、キャンペーンIDが同じでも、キャンペーン名が一致しない場合は、異なるキャンペーンとして集計されます。 |
| ファイルサイズ | コストインポート用CSVファイルのサイズ上限は以下のとおりです。<ul><li>AppsFlyer管理画面からのアップロード：2MB</li><li>メール送信：1ファイルあたり5MB</li></ul> |
| オーガニックデータ | 対応 |
| ノンオーガニックデータ | 対応 |
| データの更新・反映 | <Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">広告費</Anchor> |
| 過去のデータ | 対応。報告済みの広告費の取り消しと、修正データの再送信は、最大90日前のデータまで可能です。 |
| リターゲティング | 非対応。 |
| アカウントユーザーのアクセス権 | 地域またはメディアソースによるアクセス制限があるユーザーは利用できません。 |

</Accordion>

<div id="see-also" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">アトリビューションリンクの構造とパラメータ</Anchor>
> * 一致した行