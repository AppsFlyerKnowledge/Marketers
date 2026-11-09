---
title: PBA管理画面の使用
metadata:
  keywords:
    - pba
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-04-21T04:53:54Z'
  edited_at: '2026-10-14T09:27:33Z'
  id: 360007630318
  locale: ja
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ja/articles/360007630318
---
> **概要：**

<Image align="center" alt="AppsFlyer-People-Based-Attribution_us-en.png" src="https://files.readme.io/d2178dfedb2f67420e66626adbd72dd96ba9edc39fcb0be08648b01656fd2d4b-360010094118.png" />

<div id="pba-dashboards" />

## PBA管理画面

<div id="settings" />

## 設定

<div id="filtering-options" />

<Accordion title="フィルタのオプション">

(A) 日付選択、(B) メインフィルター、および (C) 追加のフィルターを使用して、PBA ダッシュボードの結果を絞り込み、分析をニーズに合わせて調整します。

<div id="filter-panel-in-pba-dashboards" />

#### PBAダッシュボードのフィルターパネル

<Image align="center" alt="PBAHeader_us-en.png" src="https://files.readme.io/aaa4040b69082c8507c604b530086404080d542b614fd20fcb0d5302221d7586-360019762657.png" />

**キー**:

(1) 日付選択

(2) デフォルトフィルター

追加フィルタ

**原則**

* フィルターパネルの設計は、すべてのPBA ダッシュボードにおいて共通です。
* ダッシュボードごとに使用できるフィルターは、次の表に示すように異なります。
* コンテキストを持つフィルター：下表に示されているように、一部のフィルターでは、コンテキストに関連付ける必要があります。たとえば、Webアシストインストールダッシュボードでは、国フィルターには Webメディアソースまたはモバイルメディアソースのいずれかのコンテキストが必要です。国フィルターを2つ設定することで、それぞれに国フィルターを設定できます。


<table><tbody><tr><th><span id="available-filter-dimensions-per-dashboard"></span><span id="filters-and-date-picker"></span>フィルター</th><th>説明／値</th><th>Webサイト計測 </th><th>Webアシストインストール</th><th>コンバージョン<br/> </th></tr><tr><td>日付選択</td><td><p>次のいずれかのPBA CVイベントが発生した日： </p><ul><li>アプリインストール</li><li>Webコンバージョン</li><li>アプリコンバージョン</li></ul></td><td><p>Y</p></td><td><p>Y</p></td><td><p>Y</p></td></tr><tr><td>地理 </td><td><p>国／地域リスト </p></td><td>Y</td><td><span>Y(1)</span></td><td><p><span>Y(2)</span></p></td></tr><tr><td>インストールタイプ</td><td>オーガニック、スマートバナー、カスタムリンク、有料</td><td>--</td><td><span>Y</span></td><td><span>--</span></td></tr><tr><td>メディアチャネル</td><td>広告、ダイレクト、メール、紹介、オーガニック検索、ソーシャル</td><td>Y</td><td><span>Y</span></td><td><span>Y(2)</span></td></tr><tr><td>モバイルプラットフォーム</td><td>Android、iOS</td><td>--</td><td><span>Y</span></td><td><span>--</span></td></tr><tr><td>Media source </td><td><p>イベントが紐づけられたメディアソース<span></span></p></td><td><p>Y</p></td><td><span>Y(1)</span></td><td>Y(1)</td></tr><tr><td><p>メディアタイプ</p></td><td><p>有料 (paid) 、<a href="./owned-media-attribution" target="_blank">オウンド</a> (owned)、獲得 (earned) を含む</p></td><td><p>Y</p></td><td>Y</td><td>Y(2)</td></tr><tr><td><p>コンバージョンイベント</p></td><td><p>コンバージョン経路のコンバージョンイベントにつながった経路を表示する</p></td><td><p>Y</p></td><td><p>--</p></td><td><p><span>Y</span></p></td></tr><tr><td><p>経路の長さ（ステップ数） </p></td><td></td><td><p>--</p></td><td><p>--</p></td><td><p>Y</p></td></tr><tr><td><p>パスの期間（日数）</p></td><td>最初のタッチポイントからのコンバージョン経路の期間</td><td>--</td><td>--</td><td>Y</td></tr><tr><td colspan="5"><p><strong>(1)</strong> Webアシストインストールダッシュボードで、フィルターを Web メディアソースまたはモバイルメディアソースに関連付けます。フィルターの複数のインスタンスを設定できます。（ケース例）</p></td></tr></tbody></table>

</Accordion>

<div id="grouping-options" />

<Accordion title="グループ化オプション">

管理画面上のデータは、例えばメディアソースやデバイス、国ごとにグループ化されます。グループを選択すると、結果テーブルにデータ列が追加されます。グループの選択順序は、データの表示方法に影響します。

* メディアソース／キャンペーン
* ドロップダウンにて、1つ以上のオプションを選択してください。

<div id="example" />

> 📄 **例**
>
> シナリオ：Net\_AとNet\_Bの両方で、同じターゲティングキャンペーンが実行されます。
>
> **ゴール：** 目的：どのメディアソースがより成功しているかを調べます。
>
> **方法**方法：*メディアソース*でグループ化し、同じターゲットオーディエンス向けのキャンペーンを確認してください。

| グループ | 説明 | Webアシストインストール | Webサイト計測 |
| --- | --- | --- | --- |
| Device type | スマートフォン、タブレット、デスクトップ、TV、その他（認識されなかったデバイス）を含む | Y | Y |
| 環境 | <ul><li>WebとモバイルのKPIを区別するために使用してください</li><li>PBA Webサイト計測の管理画面例：Android/Web、iOS/Web、Windows/Web、Linux/Web</li><li>Webアシストインストール：iOS、Android、Windows</li></ul> | Y | いいえ |
| 地理 | <ul><li>国別にトラフィックとエンゲージメント傾向を表示します</li><li>結果によって国ごとの投資決定に直接影響する可能性があります</li></ul> | Y | Y |
| メディアソース／キャンペーン | **Media source**<br /><br />コンバージョンに紐づくメディアソース<ul><li>詳細なキャンペーンデータを表示するには、キャンペーン階層をクリックしてください：キャンペーン > 広告セット > 広告</li><li>使用可能な階層レベルは、メディアソースによって異なります</li></ul>**キャンペーン名**<ul><li>URLパラメーターに基づく使用可能なキャンペーン名</li><li>キャンペーン名が利用できない場合もあります。</li></ul> | Y | Y |
| メディアチャネル | 広告、ダイレクト、メール、紹介、オーガニック検索、ソーシャル | いいえ | Y |
| メディアタイプ | 有料 (paid) 、<Anchor target="_blank" href="/marketers/ja/docs/owned-media-attribution">オウンド</Anchor> (owned)、獲得 (earned) を含む | いいえ | Y |
| Platform |  | いいえ | Y |

</Accordion>

<div id="other-settings" />

<Accordion title="その他の設定">

| 設定 | 説明 |
| --- | --- |
| ブランドバンドル | PBA管理画面には、ブランドバンドルレベルのデータがあります。バンドルは、Webサイト、1つのAndroidアプリ、1つのiOSアプリで構成されます。<ul><li>バンドルを構成するアプリを表示／編集できる<Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings#よくある質問">権限</Anchor>がある場合は、バンドルを選択できます。</li><li>バンドルを切り替えるにはセレクターを使用してください。</li><li><Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings">バンドルを作成し編集します。</Anchor></li></ul> |
| PBA設定 | <ul><li>コンバージョンイベントの設定</li><li>バンドル設定の変更</li></ul> |

</Accordion>

<div id="additional-information" />

## 追加情報

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

PBA管理画面とレポートは、UTCタイムゾーンごとで<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#eod">毎日</Anchor>更新されます。

* デイリーの処理には、前日に受信したイベントが含まれます。
* データのファイナライズ：
  * Webアシストインストールの場合、Webサイト計測およびコンバージョン経路PBAは、コンバージョン後7日間、追加の関連イベントを識別します。これにより、コンバージョンをもたらしたと特定されたメディアソースが変更される可能性があります。
  * 関連するローデータレポートでは、最初の7日間は *final\_data* の項目が fales になります。

PBAダッシュボードは現地通貨をサポートしておらず、データは米ドルで表示されます。

</Accordion>

<div data-zendesk-anchors="pba-dashboards=pba%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2 h_01HNJGN4BYRH14QXS4SWQAHR8D=pba%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2 settings=%E8%A8%AD%E5%AE%9A h_01HNJGN4BYF8NFYYWHG30RHEJH=%E8%A8%AD%E5%AE%9A h_01HNJGN4BYSHM9PFYQQ86ZR84X=filtering-options filter-panel-in-pba-dashboards=pba%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC%E3%83%91%E3%83%8D%E3%83%AB h_01HNJGN4BYVYY2MKK5G3RCS07W=pba%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC%E3%83%91%E3%83%8D%E3%83%AB h_01HNJGN4BZ2KZAK120ZGT3B23W=filters-and-date-picker h_01HNJGN4BZV94W8W2GBXCZF563=grouping-options 01EDDQYQ8RWQZZTEZY9AVT1M64=%E4%BE%8B 01EDDQYQ8R5JPZE30ETV70FJVN=other-settings additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HNJGN4BZ9BMV7BQRQCKGYSSP=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HNJGN4BZFMG73SPZ1J4Z7TT5=traits-and-limitations" />
