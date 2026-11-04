---
title: ProtectLITEのダッシュボードとレポートによる基本的な不正検知・分析
metadata:
  keywords:
    - Advertisers
    - Protect360
    - Marketers
    - Protect360 / Fraud protection
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360 / Fraud protection
  created_at: '2021-01-25T09:47:02Z'
  edited_at: '2026-10-28T08:58:22Z'
  id: 360017223058
  locale: ja
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ja/articles/360017223058
---
> **概要：** ProtectLITEでは、無料の基本的な不正対策エンジンでブロックされた不正インストールや、検証ルールの適用によってブロックされたインストールを確認・分析できます。

## ProtectLITE

ProtectLITEは、インストールのアトリビューションに関する不正に対して、基本的な保護機能を無料で提供します。より高度な不正対策・検知機能は、<Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide">Protect360</Anchor>で利用できます。

AppsFlyerが不正を検知すると、その不正はトラフィックデータ上でブロックされます。このデータはAppsFlyerのダッシュボードとローデータレポートで確認できますが、ブロックによってエンドユーザーのアプリ利用に影響が生じることはありません。つまり、ユーザーは引き続きアプリを利用でき、広告主の収益につながる行動も可能です。

ProtectLITEダッシュボードでは、次のことができます。

* 不正インストール、成果を横取りされたインストール、または<Anchor target="_blank" href="/marketers/ja/docs/implement-validation-rules-to-prevent-fraud">検証ルール</Anchor>によってリアルタイムでブロックされたインストールについて、すべてのアプリの集計データを表示します。
* フィルターやグループ化の機能を使ってデータを絞り込み、検知されたインストールを詳しく確認できます。
* Protect360の契約が必要な追加の不正対策機能も確認できます。これには、高度なリアルタイム不正検知、ポストアトリビューションでの不正検知、アプリ内イベントの不正検知、アプリ内イベントの検証ルール、異常傾向の分析ツールが含まれます。

ProtectLITEの<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports">ローデータ</Anchor>は、次の方法で取得できます。

* ［データ出力（Export Data）］ページとPull APIから、Protect360のインストールレポートとして取得できます。

<div id="dashboard" />

## ダッシュボード

ProtectLITEダッシュボードを表示するには、AppsFlyerで<strong>［Protect360］</strong>に移動します。

ダッシュボードの各機能について、以下で説明します。

<div id="filters-and-groupings" />

<Accordion title="フィルターとグループ化">

**フィルターとグループ化の設定画面**

次のフィルターとグループ化のオプションを利用できます。

* 基本フィルター：
  * アプリ名
  * 流入の種類：非オーガニック／オーガニック（両方の選択も可能）
  * メディアソース
  * 国・地域（Geo）
  * 日付範囲（<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#protect360-dashboard">対応するタイムゾーンを参照</Anchor>）
* 追加フィルター：日付選択欄の右側にある青い矢印をクリックすると表示されます。
  * 代理店
  * チャネル
  * 集計対象グループの最小件数（Minimum cohort size）
* グループ化のオプション：不正データを集計する項目を選択して、必要な情報を確認できます。
  * **アプリ：** アプリごとの不正の総件数を比較します。
  * **メディアソース** （デフォルト）：アプリが利用する各メディアソースについて、対処した不正を比較します。
  * **メディアソース＋キャンペーン**：アプリが利用するすべてのメディアソースについて、各キャンペーンで対処した不正を比較します。
  * **メディアソース＋サイトID**：アプリが利用するすべてのメディアソースについて、各パブリッシャー（サイトID）で対処した不正を比較します。
  * **メディアソース＋サイトID＋キャンペーン**：アプリが利用するすべてのメディアソースについて、各パブリッシャー（サイトID）で対処した不正を、該当するキャンペーン名とあわせて比較します。
  * **国・地域**：各国で対処した不正を比較します。
  * **メディアソース＋国・地域** （アプリ内イベントダッシュボードで利用可能）：アプリが利用する各メディアソースについて、対処した不正を該当する国別に比較します。

</Accordion>

<div id="installs-headline-metrics" />

<Accordion title="インストール：主要指標">

主要指標では、次の項目を確認できます。

* 推定削減額
* 不正・無効と判定されたインストール
* 推定される不正の全体規模

指標は、日付フィルターで選択した期間のデータを示します。

「推定削減額」と「不正・無効と判定されたインストール」のKPIには、パーセント値が表示されます。この値は、表示されているKPIを、直前の同じ長さの期間と比較したものです。たとえば、今週と先週、または選択した期間とその直前の同じ日数の期間を比較します。推定削減額がX%増加と表示されている場合、直前の比較対象期間には不正インストールがX%少なかったことを意味します。

<div id="estimated-savings" />

#### 推定削減額

[![](https://files.readme.io/f53d6245eb8bb81fb652a05869fe71102ed50ab304d2fc8faf1cc17198794470-360019038197.jpg)](https://files.readme.io/f53d6245eb8bb81fb652a05869fe71102ed50ab304d2fc8faf1cc17198794470-360019038197.jpg)

推定削減額の指標は、次のとおりです。

* ProtectLITEと検証ルールによってリアルタイムで検知・ブロックされた不正に相当する金額を表示します。この金額をもとに、アドネットワークとの精算を調整します。
* 計算式：推定削減額＝ブロックされたインストール数×アプリの平均eCPI。
* オーガニック流入は対象外です。

金額の計算方法について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide#faq">よくある質問</Anchor>を参照してください。

<div id="identified-installs" />

#### 不正・無効と判定されたインストール

[![](https://files.readme.io/2bc38a1ee19b4a13c18ed7571d97efd0f855d27142e8a6cd9a761cac276d3bd0-360019090998.jpg)](https://files.readme.io/2bc38a1ee19b4a13c18ed7571d97efd0f855d27142e8a6cd9a761cac276d3bd0-360019090998.jpg)

この指標は、ProtectLITEと検証ルールによってリアルタイムで検知・ブロックされたインストール数を示します。

<div id="suspected-overall-fraud-threat" />

#### 推定される不正の全体規模

[![](https://files.readme.io/bb6a33cfea1dbff695d46a4b2f6547b756740cf35b750db25097d7ec772cc3d8-360019091058.jpg)](https://files.readme.io/bb6a33cfea1dbff695d46a4b2f6547b756740cf35b750db25097d7ec772cc3d8-360019091058.jpg)

推定される不正の全体規模は、次のことを示します。

* Protect360を契約した場合にブロックされると推定される不正の規模です。
* より高度な不正対策を利用するためにProtect360へアップグレードすべきか、判断する際の目安になります。

</Accordion>

<div id="installs-chart" />

<Accordion title="インストール：グラフ">

<div id="fraud-trend-over-time-chart" />

#### 不正件数の推移グラフ

日付フィルターで選択した期間について、ProtectLITEと検証ルールによってブロックされた日別のインストール数を表示します。

</Accordion>

<div id="installs-table" />

<Accordion title="インストール：表">

<div id="identified-fraud-breakdown" />

#### 検知された不正の内訳

日付フィルターで選択した期間について、ProtectLITEと検証ルールによってブロックされたインストール数を表示します。

<strong>［CSV出力（Export CSV）］</strong>をクリックすると、表をCSV形式でパソコンにダウンロードできます。

以下の画像のように、表には全体の概要が表示されます。

[![plite_fraud_table.jpg](https://files.readme.io/81246675ce8f0e1243e0c0d64e1cf347246bb403894718ad9e23c56fc594eb84-360019038257.jpg)](https://files.readme.io/81246675ce8f0e1243e0c0d64e1cf347246bb403894718ad9e23c56fc594eb84-360019038257.jpg)

表の表示内容は、次の方法で変更できます。

* 表の設定ボタンをクリックして、列を追加・削除できます。  
  変更後は［保存］ボタンをクリックしてください。設定を保存すると、次回のアクセス時にも同じ表示内容が適用されます。
* 列の設定画面で各列の項目をドラッグすると、列の順序を変更できます。

[![plite_edit_columns.jpg](https://files.readme.io/52fc1378d4c758d80ed2a89b24f5b7fa949c9ccccae7ff5edf4af307538e805a-360019038297.jpg)](https://files.readme.io/52fc1378d4c758d80ed2a89b24f5b7fa949c9ccccae7ff5edf4af307538e805a-360019038297.jpg)

<div id="content-of-the-identified-fraud-breakdown-table" />

#### 「検知された不正の内訳」表の内容

| 表の列 | 説明 |
| --- | --- |
| グループ化 | <ul><li>［デフォルト］表とダッシュボードは、メディアソース別にグループ化されます。</li><li>特定のメディアソースを選択すると、自動的にメディアソースとサイトIDの両方でグループ化されます。</li><li>キャンペーン、国・地域、チャネル、代理店、またはこれらの組み合わせでもグループ化できます。</li><li>非オーガニック流入のみに適用される項目でグループ化すると、オーガニックのメディアソースにはN/Aと表示されます。</li></ul> |
| **インストール** | **不正や検証ルールによってブロックされたインストールの主な内訳** |
| 合計（A） | <ul><li>合計インストール数＝不正インストールや検証ルールで検知されたインストールを含む、アプリのすべてのインストール。</li><li>通常のインストールは、オーバービューダッシュボードでメディアソース別（非オーガニック）に確認できます。</li></ul> |
| 不正・無効と判定されたインストール（B） | <ul><li>リアルタイムで検知・ブロックされたインストールの合計数</li><li>ブロックされたオーガニックインストールは、ダッシュボードには表示されません。ブロックされたオーガニックインストールを確認するには、ローデータレポートを利用してください。</li><li>［デフォルト］表は、このKPIの降順で並べ替えられます。</li></ul> |
| **不正・無効と判定されたインストールの割合** （B/A） | 不正・無効と判定されたインストール数／合計インストール数 |
| **ポストアトリビューションで検知されたインストール（C）** | Protect360が必要です。 |
| **ポストアトリビューションで検知されたインストールの割合（C/A）** | Protect360が必要です。 |
| **架空のインストール** | **実際のユーザーの行動を装った不正インストールです。** |
| リアルタイムブロック | リアルタイムでブロックされた架空のインストールです。 |
| ポストアトリビューションで検知されたインストール | Protect360が必要です。 |
| **成果を横取りされたインストール** | **不正なラストクリックによって、実際のユーザーによるインストールの成果が横取りされたものです。** |
| リアルタイムブロック | リアルタイムでブロックされた、成果を横取りされたインストールです。 |
| ポストアトリビューションで検知されたインストール | Protect360が必要です。 |
| **検証ルール** | **検証ルールの条件に基づいて、無効と判定されたインストールです。** |
| ブロックされたインストール | 検証ルールによってブロックされたインストールです。 |
| ブロックされたアトリビューション | 検証ルールによってアトリビューションが修正されたインストールです。 |
| **クリック** | **メディアソースからの正当なクリックです。**<br /><br />**注意：** 表にクリックデータを表示するには、フィルターバーですべてのアトリビューションタイプを選択する必要があります。選択されていない場合は、N/Aと表示されます。この条件に合わせて、フィルターの選択内容を調整してください。 |
| 合計（E） | メディアソースから受信した正当なクリックの合計数です。 |
| ブロック済み | 不正によってブロックされたクリック |
| **インプレッション** | **メディアソースからのインプレッションです。**<br /><br />**注意：** 表にインプレッションデータを表示するには、フィルターバーですべてのアトリビューションタイプを選択する必要があります。選択されていない場合は、N/Aと表示されます。この条件に合わせて、フィルターの選択内容を調整してください。 |
| 合計 | メディアソースから受信した、正当なインプレッションと不正なインプレッションの合計数 |
| ブロック済み | 不正によってブロックされたインプレッション |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| 広告主のアクセス権 | アカウントのすべてのユーザーがアクセスできます。 |
| アドネットワークのアクセス権 | <ul><li>ProtectLITEダッシュボードとローデータへのアクセスには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#アドネットワークの権限">広告主による許可</Anchor>が必要です。</li><li>広告主が、そのアドネットワークを連携済みパートナーとして利用している必要があります。</li></ul> |
| 代理店のアクセス権 | ProtectLITEダッシュボードとローデータへのアクセスには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#アドネットワークの権限">広告主による許可</Anchor>が必要です。 |
| 運用媒体の開示設定 | 運用媒体を開示している代理店：個別のメディアソースを確認できます。<br /><br />運用媒体を開示していない代理店：個別のメディアソースを確認できません。 |

</Accordion>

<div data-zendesk-anchors="01JDHEKR6W19WD6HXFFMRNXKFF=protectlite dashboard=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89 01JDHEKR6YGEKRB23M19F5ZGQ5=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89 01JDHEKR6YPNDQAK3ATDRDDZTC=filters-and-groupings installs%E2%80%94headline-metrics=installs-headline-metrics 01JDHEKR75TF5RHJTFM91XPYPY=installs-headline-metrics estimated-savings=%E6%8E%A8%E5%AE%9A%E5%89%8A%E6%B8%9B%E9%A1%8D 01JDHEKR76MMVSJSWFTZS5PRBK=%E6%8E%A8%E5%AE%9A%E5%89%8A%E6%B8%9B%E9%A1%8D identified-installs=%E4%B8%8D%E6%AD%A3%E7%84%A1%E5%8A%B9%E3%81%A8%E5%88%A4%E5%AE%9A%E3%81%95%E3%82%8C%E3%81%9F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB 01JDHEKR77VGHR1BWQFPYSWW2E=%E4%B8%8D%E6%AD%A3%E7%84%A1%E5%8A%B9%E3%81%A8%E5%88%A4%E5%AE%9A%E3%81%95%E3%82%8C%E3%81%9F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB suspected-overall-fraud-threat=%E6%8E%A8%E5%AE%9A%E3%81%95%E3%82%8C%E3%82%8B%E4%B8%8D%E6%AD%A3%E3%81%AE%E5%85%A8%E4%BD%93%E8%A6%8F%E6%A8%A1 01JDHEKR78BBFEZS98VG0VTERN=%E6%8E%A8%E5%AE%9A%E3%81%95%E3%82%8C%E3%82%8B%E4%B8%8D%E6%AD%A3%E3%81%AE%E5%85%A8%E4%BD%93%E8%A6%8F%E6%A8%A1 installs%E2%80%94chart=installs-chart 01JDHEKR795RK8KP9BZ0WECQW8=installs-chart fraud-trend-over-time-chart=%E4%B8%8D%E6%AD%A3%E4%BB%B6%E6%95%B0%E3%81%AE%E6%8E%A8%E7%A7%BB%E3%82%B0%E3%83%A9%E3%83%95 01JDHEKR79YM7VWE6NH2FJ70NS=%E4%B8%8D%E6%AD%A3%E4%BB%B6%E6%95%B0%E3%81%AE%E6%8E%A8%E7%A7%BB%E3%82%B0%E3%83%A9%E3%83%95 installs%E2%80%94table=installs-table 01JDHEKR79ZBQVSTT4GA162J94=installs-table identified-fraud-breakdown=%E6%A4%9C%E7%9F%A5%E3%81%95%E3%82%8C%E3%81%9F%E4%B8%8D%E6%AD%A3%E3%81%AE%E5%86%85%E8%A8%B3 01JDHEKR79H7PQFEJGWAY4RMJC=%E6%A4%9C%E7%9F%A5%E3%81%95%E3%82%8C%E3%81%9F%E4%B8%8D%E6%AD%A3%E3%81%AE%E5%86%85%E8%A8%B3 content-of-the-identified-fraud-breakdown-table=%E6%A4%9C%E7%9F%A5%E3%81%95%E3%82%8C%E3%81%9F%E4%B8%8D%E6%AD%A3%E3%81%AE%E5%86%85%E8%A8%B3%E8%A1%A8%E3%81%AE%E5%86%85%E5%AE%B9 01JDHEKR7BR6ESS9DX03NMHPT0=%E6%A4%9C%E7%9F%A5%E3%81%95%E3%82%8C%E3%81%9F%E4%B8%8D%E6%AD%A3%E3%81%AE%E5%86%85%E8%A8%B3%E8%A1%A8%E3%81%AE%E5%86%85%E5%AE%B9 01JDHEKR9JCAR22V33B7TFZSPV=traits-and-limitations" />
