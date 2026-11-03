---
title: ピボットテーブル—ユーザーメトリクス
metadata:
  keywords:
    - Pivot
    - Advertisers
    - 透视表
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2017-03-16T13:11:23Z'
  edited_at: '2026-10-14T09:26:23Z'
  id: 115001421846
  locale: ja
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ja/articles/115001421846
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要**：異なるユーザーメトリクスを表示—LTV、アクティビティ、Protect360、およびリテンション。自社BIシステムに取り込むためにCSVファイルをダウンロードできます。Pivotレポートでは、1つのクエリに複数アプリを含めることができます。Pivotは、Master APIコールを生成するために使用されます。

![Full_Funnel.gif](https://support.appsflyer.com/hc/article_attachments/51909644198929)

## ピボットレポートページについて

ピボットを使用することで、ユーザー獲得に関する指標を含むカスタマイズされたレポートを生成できます。ピボット機能には、カスタマイズしたレポートを作成するベースとして使用できる事前定義されたレポートが多数用意してあります。特定のアカウントユーザーによって作成されたレポートは全てのユーザーが利用できます。

事前に定義されたピボットレポート：

* 日付別メディアソース
* 全階層
* コスト分析

**注：** キャンペーンデータがピボットに表示されるためには、キャンペーンにインストールが必要です。

## ピボットの手順

ユーザーインタフェースで既存のピボットを作成および変更します。これを行うには、以降のセクションの手順に従ってください。

**ピボットの使用方法**：

* AppsFlyerのサイドメニューから、[**分析**] > [**イベント**] を選択します。  
  これまでに作成されたレポートの一覧が表示されます。

<div id="pivot-page-controls-and-options" />

<Accordion title="ピボットページ：操作オプション">

<Table>
  <thead>
    <tr>
      <th>
        カラム／オプション
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        名前
      </td>
      <td>
        レポート名を選択して、ピボットを表示します。
      </td>
    </tr>
    <tr>
      <td>
        カラムのクリック
      </td>
      <td>
        インタフェースに示すとおり、カラム名をクリックして並び替えられる列もあります。
      </td>
    </tr>
    <tr>
      <td>
        最終更新日
      </td>
      <td>
        レポート構成が最後に更新された日。
      </td>
    </tr>
    <tr>
      <td>
        最終更新日
      </td>
      <td>
        ピボットを変更したユーザーの名前。
      </td>
    </tr>
    <tr>
      <td>
        App name
      </td>
      <td>
        * 1つのアプリのみが含まれる場合：アプリ名が表示されます
        * 複数のアプリが含まれる場合：アプリの数が表示されます
      </td>
    </tr>
    <tr>
      <td>
        アクション
      </td>
      <td>
        | アクション | 備考 |
        | --- | --- |
        | 複製 | 既存のピボットレポートをコピーします。 |
        | 名前を編集 | レポートの名前を編集します。 |
        | 履歴ログを表示 | 誰がレポートの構成を編集し、どんな変更がいつ行われたかを確認します。 |
        | マスターAPIリンクをコピー | <Anchor target="_blank" href="/marketers/ja/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>経由でデータを取得するためのURLを生成します。 Master API を使用するには、認証ヘッダーで使用する <Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">API トークン</Anchor> (管理者権限が必要) を取得する必要があります。 |
        | 削除 | 選択したピボットを削除します。 |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="add-a-pivot-report" />

<Accordion title="ピボットレポートの追加">

**ピボットレポートを追加する方法**：

1. **ピボットを追加**をクリックします。  
   新しいピボット画面が開きます。
2. ピボット名を入力してください。
3. [**送信**]をクリックします。  
   ピボットテーブルの追加画面が開きます。
4. アプリ、ディメンション、指標を選択します。フィルタと値の表示設定を設定します。

| セクション | 説明 |
| --- | --- |
| アプリ | ピボットに含めるアプリを1つ以上選択します。 |
| ディメンション | [<Image alt="" src="https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png" width="221px" />](https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png)<br /><br />ディメンションを使用して、ピボットレポートをグループ化、構成、並べ替えることができます。<br /><br />**ディメンションを選択する方法**：<ol><li>**ディメンション**をクリックしてください。</li><li>ディメンションを選択し、追加したいセクションまでドラッグします。ディメンションは、ピボットに次の影響があります。<ul><li>5行行：行に配置されたディメンションにより、グループ化の階層が決まります。</li><li>列列：列に配置されたディメンションにより、ディメンションの値に応じて結果の列が増えます。</li></ul></li></ol> |
| KPI | [<Image alt="" src="https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png" width="294px" />](https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png)<br /><br />KPIは、次のようにタイプごとにグループ化されます。<ul><li>LTV（顧客生涯価値）</li><li><Anchor target="_blank" href="/marketers/ja/docs/activity-dashboard#仕様と制限事項">アクティビティ</Anchor></li><li>リテンション：リテンション日、リテンション率。 　**注：** 注：リテンションの選択肢までスクロールダウンし、リテンション率とProtect360を選択します（Protect360が有効なアカウントのみ）。</li><li><Anchor target="_blank" href="/marketers/ja/docs/master-api-user-acquisition-metrics-via-api#kpis">指標について。</Anchor></li></ul>ほとんどの場合、値セクションにKPIを配置します。必要に応じて、KPIはディメンションとして使用できます。<br /><br />KPIを関連するセクションにドラッグ＆ドロップします。 |
| 範囲外の値は | 各KPIとごに、演算子を選択して計算方法を設定します。<ul><li>合計</li><li>カウント</li><li>Max</li><li>Min</li><li>レート</li><li>平均</li></ul> |
| フィルタ | フィルタセクションに必要なフィルタを配置します。フィルタの設定方法を選択します。<ul><li>テキスト</li><li>Multi-select</li></ul> |

</Accordion>

<div id="view-a-pivot-report" />

<Accordion title="ピボットレポートの表示">

[![](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)

**ピボットレポートを表示する方法**：

* ピボットページで表示するレポートを選択します。
* レポートの表示オプション

| セクション | 説明 |
| --- | --- |
| (1) 選択したディメンション | 最初の列には、レポートのグループ化として選択されたディメンションが含まれています。ディメンションはピボットの編集で設定された順序に従ってグループ化されます。上記の例では、プライマリディメンションはアプリ名で、次にメディアソース、最後にインストール日と続きます。 |
| (2) 指標 | 残りの列には、ピボットの編集ページで**値**として選択されたKPIが表示されます。上記の例では、最初のKPIはインプレッションで、その次にクリック、インストール等が表示されています。 |
| (3) フィルタ | ピボットの編集ページで設定したレポートのフィルタがここに表示されます。フィルタの文字列を入力するか、ドロップダウンから複数アイテムを選択できます。<br /><br />[**![](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png)**](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png) |
| (4) 選択した日付 | 日付範囲の選択ウィンドウを使用して特定の日付を選択します。独自のカスタム日付範囲を選択するか、既定の日付範囲ボタンのいずれか1つを使用します。 |
| (5) アクション | [ピボットレポートの一覧](/docs/pivot-table-user-metrics#view-a-pivot-report)ページで利用できるアクションと同じものが、ピボットレポートごとに利用できます。 |

</Accordion>

## 特性と制限

<div id="traits-and-limitations::e6883df" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| アドネットワークのレポートへのアクセス | いいえ |
| 代理店によるデータアクセス | いいえ |
| 代理店の運用媒体の開示設定 | はい |
| アプリ固有のタイムゾーン | はい<br /><br />例外：例外：以下のすべての場合で、AppsFlyerはアプリ固有のタイムゾーンを無視し、UTC +0であるデフォルトのタイムゾーンを使用します。<ul><li>レポートに複数のアプリのデータが含まれており、それぞれのアプリのタイムゾーンが異なる場合。</li><li>全てのアプリのタイムゾーンは同じだが、コホートレポート期間中に少なくとも1つのアプリのタイムゾーンが変更された場合レポートの期間の決定において：<ul><li>開始日コンバージョン日範囲の最初の日付。</li><li>終了日。終了日：表示期間の日数をコンバージョン日付範囲の最後の日付に加算して計算されます。例：最終日：Jan 23, 2023レポート期間：1-180日終了日。Jan 23, 2023</li></ul></li></ul> |
| App-specific currency | 結果はUSDで返されます。 |
| オーガニックデータ | 含まれています |
| 非オーガニックデータ | 含まれています |
| データ更新頻度 | データ更新頻度：毎日。データの更新頻度は、<Anchor target="_blank" href="/marketers/ja/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>と同じです。 |
| アカウントユーザーのアクセス | はい |
| リターゲティング収益 | 含まれています |
| キャンペーン名の変更 | ピボットでは、キャンペーン名の広告費が、レポートされた最新のキャンペーン名と一致しません。つまり、使用される各キャンペーン名にはコストが関連付けられます。 |
| リターゲティングデータ | <ul><li>一般的に、<Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard">Cohort</Anchor>を使用してリターゲティングデータを表示します。</li><li>2025年2月1日以降のトラフィックのアクティビティKPIには、統合データ（UAとリターゲティングを合わせたもの）が含まれます。</li></ul> |
| コストデータ | AppsFlyerは、主にコストAPIを介してコストデータを取得します。データは連携済みパートナーにより提供されます。<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">連携パートナーごとのディメンションの一覧。</Anchor> |
| リテンション率 | リテンション率を取得するには、レポートにインストールを含めます。 |
| レポートあたりの最大行数 | 200K |
| 過去データ | <ul><li>LTVデータ5年</li><li>アクティビティデータ：3年</li></ul> |

</Accordion>

<div data-zendesk-anchors="pivot-reports-page=%E3%83%94%E3%83%9C%E3%83%83%E3%83%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HJR8389QPFKR9X6V52N7PHMM=%E3%83%94%E3%83%9C%E3%83%83%E3%83%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 pivot-procedures=%E3%83%94%E3%83%9C%E3%83%83%E3%83%88%E3%81%AE%E6%89%8B%E9%A0%86 h_01HJR8389QPNRX8Y26VQWN0ZXP=%E3%83%94%E3%83%9C%E3%83%83%E3%83%88%E3%81%AE%E6%89%8B%E9%A0%86 pivot-page%E2%80%94controls-and-options=pivot-page-controls-and-options h_01HJR8389QDDWR8ZKCSDZGVAGP=pivot-page-controls-and-options h_01HJR8389R2C1E42JN9NFMS4CJ=add-a-pivot-report h_01HJR8389SQ40HZ8EXQME4807S=view-a-pivot-report traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HJR8389SPJZG6AYGABB17V1N=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HJR8389S19TVMVR60ZYAJMAA=traits-and-limitations::e6883df" />
