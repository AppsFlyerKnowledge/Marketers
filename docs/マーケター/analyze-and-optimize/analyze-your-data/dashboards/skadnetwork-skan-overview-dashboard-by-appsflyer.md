---
title: AppsFlyerのSKAdNetwork (SKAN) オーバービュー管理画面
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
  created_at: '2020-07-25T21:27:38Z'
  edited_at: '2026-10-14T09:38:12Z'
  id: 360011307357
  locale: ja
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ja/articles/360011307357
---
> **概要：** 概要： SKAdNetwork (SKAN) ダッシュボードには、iOS SKANポストバックを介してレポートされたキャンペーン指標と、初期ユーザー測定ウィンドウ中の追加のデータポイントが表示されます。null コンバージョンを考慮したモデル化（推定）された指標も用意されています。インストールまたはポストバックの到着日を使用してデータを表示します。

![SKAdHeadling8_us-en.png](https://files.readme.io/72c2eb452741cbd77c5828197f827f238c71c5097b8703528fa180dcafe2364c-360011831017.png)

## 管理画面の原則

管理画面には、SKANキャンペーンのパフォーマンスデータが含まれており、以下の原則に基づいています。

* Appleは、 <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork">プライバシー閾値メカニズム</Anchor>により、コンバージョン値（CV）を常に提供するわけではないことを考慮してください（これを「null CV」と呼びます）。null CVの場合は、インストールのみ計測されます。
* 指標は以下のように算出されます：
  * ダッシュボードの非オーガニック数値は、AppsFlyerが受信したSKANのポストバックデータを使用して計算されています。<Anchor target="_blank" href="/marketers/ja/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">再ダウンロード、ソースアプリID、'fidelity' タイプのメトリクスなど、一部のメトリクスでは ポストバックコピーを直接AppsFlyerに送信 するようアプリ側で設定が必要です。（設定推奨）</Anchor>
  * オーガニックに関する指標は、AppsFlyerの計測データからSKANの非オーガニック計測データを差し引いて算出されます。　**注：** 注意： オーガニック指標は、常に利用できるわけではありません。[詳細はこちら](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations)を参照してください。
    * install type項目で **新規インストール** とフィルターしてください。
  * 収益やROASのように、ポストバックから得られる元の値と、null CV率を考慮したモデル値 [の両方を持つ指標もあります。](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv)
* 代理店経由のトラフィックは運用媒体を開示する仕様で扱われます。
* データ更新頻度：
  * 毎日。
  * 特定の日に受信したポストバックは、UTCで一日の終わりに処理されます。データは、翌日の08:00 UTCまでに入手可能です。つまり、月曜日に受信したポストバックは日本時間で火曜日の夕方17時にダッシュボードで利用できることを意味します。
  * <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">管理画面の更新時間</Anchor>を参照してください。

## SKAN管理画面の表示オプション

データは、[インストール日またはポストバック到着日](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#filter-options)のいずれかを用いて表示されます。

フィルタにて、表示の方法オプションを選択してください。

追加のフィルタと表示オプションについては、次のセクションで説明しています。

## 管理画面の使用

<div id="dashboard-settings" />

<Accordion title="管理画面の設定">

Dashboard 設定は、アプリケーションがレガシー <Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#fixed-modes">固定モードコンバージョン測定</Anchor> を使用してコンバージョンイベントを選択する場合に利用できます。

**コンバージョンイベントを選択する方法**：

1. 管理画面の右上にある**管理画面の設定**をクリックしてください。
2. コンバージョンイベントを選択してください。
3. 適用をクリックします。  
   コンバージョン指標はこのイベントを使用して計算されます。  
   ご注意くださいこの設定はダッシュボードでの表示に関連するもので、アプリ内のCV設定には影響しません。

</Accordion>

<div id="filter-options" />

<Accordion title="フィルターオプション">

フィルタを使って表示されるデータを絞り込みます。

| **フィルター** | **備考** |
| --- | --- |
| 表示 | <ul><li>**インストール日**：インストール日： ポストバックの到着時刻から次のように導出されます：<ul><li>ポストバックがSKAN V4の場合：インストール日 = ポストバック到着時間 - [累積ウィンドウの長さ] - [ポストバックの平均遅延時間]<ul><li>ポストバック1： インストール日 = ポストバック到着時刻 - 48h - 36h</li><li>ポストバック2： インストール日 = ポストバック到着時刻 - 168h - 84h</li><li>ポストバック3： インストール日 = ポストバック到着時刻 - 840h - 84h</li></ul></li><li>インストール日 = ポストバック到着時間 - 36時間 - [平均最終アクティブ範囲]。<ul><li>デフォルトの「平均最終アクティブ範囲」は12時間です。</li><li>コンバージョン値が 0 の場合、最後のアクティブ範囲の平均は 0 に設定されます。</li></ul></li></ul></li><li>**ポストバック到着日**：<ul><li>AppsFlyerがポストバックを受信した日</li><li>AppsFlyer SKAN管理画面の指標とアドネットワークが提供する指標を比較する場合、アドネットワークは通常、ポストバック到着日を使ってデータを公開しています。</li><li>このオプションを選択した場合、オーガニックの指標は利用できません。</li><li>Google Ads：到着日とインストール日は同じです。</li></ul></li></ul> |
| データ期間 | <ul><li>計測されたインストール日。この日付はポストバック到着時刻を使用して算出されます。</li><li>インストール数が多い場合、タイミングによる精度の低下は大きくありません。</li><li>インストールは再ダウンロードを含みます。</li><li>日付の範囲は90日に限定されています。</li></ul> |
| Media source | <ul><li>インストール成果が紐づくアドネットワーク</li><li>代理店運用のトラフィック：実際のメディアソースは、代理店の運用媒体開示設定の内容に関係なく表示されます。そのため、自社で運用したことのないメディアソース名が表示されることがあります。</li></ul> |
| キャンペーン | <ul><li>アドネットワークによって設定されたキャンペーン名とID。</li><li>AppsFlyerはポストバックのキャンペーンIDをアドネットワークのそれに変換します。</li><li>特定のキャンペーンIDに複数のキャンペーン名が紐付けられている場合は、管理画面にすべての名前が表示されます。ご注意くださいアドネットワークは、ポストバックごとにキャンペーンIDと名前を提供します。キャンペーンIDとキャンペーン名の両方が、ローデータと集計されたSKANレポートで利用できます。</li></ul> |
| Site ID | <ul><li>広告を表示しているアプリ。</li><li>最も有益なアプリを分析をするために使用します。</li></ul> |
| 地理 | <ul><li>地域や国</li><li>地域は、アドネットワークから提供されるデータまたはデバイスIPアドレスを使用して導き出されます。</li><li>[2021年6月24日更新] iOS 14.6以降、デバイスのIPアドレスはAppleのプロキシサーバーによってマスクされます。つまり、デバイス自体の位置情報ではなく、Appleサーバーの位置が反映されます。</li></ul> |
| インストールタイプ | <ul><li>インストール</li><li>再ダウンロードはアプリストアによりレポートされます。</li></ul> |
| Adset | アドネットワークがこのデータポイントを提供する場合に利用できます。 |
| Ad | アドネットワークがこのデータポイントを提供する場合に利用できます。 |
| バージョン |  |

</Accordion>

<div id="headline-metrics" />

<Accordion title="メインの指標">

| 指標 | 備考 |
| --- | --- |
| インストール | SKANは、ユーザーがインストール前に広告に関与していない場合は、インストールを報告しません。AppsFlyerは、AppsFlyerのインストール計測（LTV管理画面）を使用してオーガニック指標を計算します。<ul><li>非オーガニック：非オーガニック：有料アプリ間キャンペーンのコンテキストでメディアソースに紐づくインストールとSKANによってレポートされたインストール。</li><li>AppsFlyerによって計算されるオーガニックは、以下が含まれます。<ul><li>SKANにより計測されなかった、またはアドネットワークからポストバックを受信しなかったインストール。</li><li>App Clip</li><li>Apple Search Ads。</li></ul></li></ul> |
| タッチポイント | 広告媒体は、インプレッションとクリックをクリックまたはAPIでレポートします。 |
| Total Revenue | <ul><li>収益モードが設定されている場合に利用可能です。</li><li>USDまたは<Anchor target="_blank" href="/marketers/ja/docs/app-settings">アプリ設定ページ</Anchor>で設定されたアプリ固有の現地通貨で表示されます。</li><li>オーガニックと非オーガニックの収益の分割が表示されます</li><li>オーガニックの収益は、総収益額から非オーガニックの収益を差し引いて計算されます。</li><li>類似比較を可能にするために、オーガニックインストールと非オーガニックインストールのインストール後の期間は同じです。</li></ul>**注：** 注意： オーガニック指標は、常に利用できるわけではありません。[詳細はこちら](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations)を参照してください。 |
| コスト | <ul><li>アドネットワークから報告されるコスト。コストデータは、ROI360 / コストAPIを使用してAppsFlyerにレポートされます。コストはUSDまたは<Anchor target="_blank" href="/marketers/ja/docs/app-settings">アプリ設定ページ</Anchor>で設定されたアプリ固有の現地通貨で表示されます。</li><li>キャンペーン名が変更されると、最新のキャンペーン名を使用してコストが表示されます（複数のキャンペーン名が存在する場合）。</li><li>コスト指標は、インストールと再ダウンロードの両方を含む [インストールの種類 = すべて] フィルターでのみ使用できます。</li></ul> |
| Click-to-install率 | Click-to-install率。 |
| 直近期間のトレンド | % で示されるトレンド値は、同様の前期間と比較した現在の指標の変化を示しています。例えば、現状の期間が5月1~10日の場合、以前の期間は4月21~30日です。 |

</Accordion>

<div id="charts" />

<Accordion title="グラフ">

使用可能なグラフは、選択された計測タイプにより異なります。

<Table>
  <thead>
    <tr>
      <th>
        グラフ指標
      </th>
      <th>
        備考
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ユーザー獲得の傾向
      </td>
      <td>
        利用可能なディメンション：

        * オーガニック
        * 非オーガニック

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer2_us-en.png" src="https://files.readme.io/5c46dc05b4df07f3f60ff6015f115b4bc89106a6eb594f43d777af2100fdf460-360010368477.png" width="201px" />](https://support.appsflyer.com/hc/article_attachments/51444204175505)
      </td>
    </tr>
    <tr>
      <td>
        コンバージョンへの接触タイプ
      </td>
      <td>
        利用できる表示方法：

        * タッチポイントのディメンション：
          * インプレッション
          * クリック
        * Click-to-install率

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer3_us-en.png" src="https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png" width="223px" />](https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png)
      </td>
    </tr>
    <tr>
      <td>
        広告階層要素ごとにまとめた1日あたりのインストール数
      </td>
      <td>
        使用可能なディメンション：
      </td>
    </tr>
    <tr>
      <td>
        広告階層要素ごとの指標のブレークダウン
      </td>
      <td>
        使用可能なディメンション：

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer5_us-en.png" src="https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png" width="198px" />](https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png)
      </td>
    </tr>
    <tr>
      <td>
        トップイベント
      </td>
      <td>
        上位イベントには、オーガニックユーザーと非オーガニックユーザーが含まれています。ページ上部のメディアソースフィルタを使用して、オーガニックと非オーガニックユーザーを区別したり、メディアソースに絞り込んで確認できます。

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer6_us-en.png" src="https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png" width="245px" />](https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png)
      </td>
    </tr>
    <tr>
      <td>
        上位の国
      </td>
      <td>
        [<Image alt="mceclip1.png" src="https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png" width="181px" />](https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png)

        注： 注：この表は代理店様向けで、広告主様向けではありません。/span>
      </td>
    </tr>
    <tr>
      <td>
        ポストバックコピー
      </td>
      <td>
        このグラフは、iOS 15+ <Anchor target="_blank" href="/marketers/ja/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">ポストバックコピー</Anchor> をAppsFlyerに送信するようにアプリを設定した後に利用できます。チャートが表示されない場合：

        * アプリからのポストバックを受信していない、またはまだ受信していません。AppsFlyerエンドポイントがアプリで設定されており、App Storeにてアプリバージョンが更新されていることをアプリ開発者に確認してください。
        * 選択した日付のポストバックを受信しなかった（つまりSKANインストールが無い）、または2022年1月1日より前の日付を選択した場合。

        注：

        * ダッシュボードに表示されるその他の指標は、広告媒体からAppsFlyerに転送されるiOSのポストバック、またはSRNから直接提供されるデータから計算されています。ポストバックコピーのメトリクスと他のメトリクスとの間に不一致があることが予想されます。
        * ポストバックコピーチャートは、代理店では利用できません。

        [<Image alt="PostbackCopy.png" src="https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png" width="207px" />](https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png)

        | ディメンション | 備考 |
        | --- | --- |
        | Media source | インストールに起因するメディアソース。<br /><br />* 指標：<br />  * （SKAdNetwork V2.2+を使用したポストバックに関する測定値です。）<br />  * attributed\_touch\_type（SKAdNetwork V2.2+を使用したポストバックに関する測定値です。）<br />* 注記：注：メディアソースIDが表示される場合、現在そのIDに関連する名前はありません。媒体社にAppsFlyerのSKAdNetwork IDを更新するよう依頼してください。 |
        | ソースアプリ | 広告掲載アプリ名 - ユーザーが広告にエンゲージしたアプリの名前<br /><br />* メトリクス：<br />* 注：<br />  * Appleがプライバシーのしきい値のためにソースアプリIDを非公開にした場合、ソースアプリは *unknown* として表示されます。<br />  * アプリ名が見つからない場合は、アプリIDが表示されます |
        | ソースアプリID | 広告掲載アプリID - ユーザーが広告に接触したアプリID<br /><br />* メトリクス： |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="metrics" />

<Accordion title="指標">

* 利用できる指標を選択します。[推定数値](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) は null CV率を考慮します。
* ディメンション別にプライマリとセカンダリのグループを設定し、パフォーマンス指標をドリルダウンします。

[![SKAdNetwork_Dashboard_AppsFlyer7_us-en.png](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)

指標テーブルについて：

* この表を使用してキャンペーンとメディアソースの成果を比較します。
* デフォルトでは、インストール数の上位20のメディアソースが降順に表示されます。
* 表を並び替えるには、列のヘッダーをクリックします。再度クリックすると、並び替え順序が逆になります。
* コスト関連の指標（コスト、インプレッション、クリック）は、少なくとも1つのインストールが特定のキャンペーンに計測されている場合に利用できます。注記：
  * インストール数が0のキャンペーンは全く表示されません。
  * 一部のアドネットワークでは、コスト関連の指標を広告セットや広告レベルでレポートしていますが、インストールについてはキャンペーンレベルでレポートしています。この場合、広告セットおよび広告コスト関連の指標は、インストール指標が0の状態で表示されます。

指標について

<table><thead><tr><th>指標</th><th>計算式／備考</th></tr></thead><tbody><tr><td>インストール</td><td><ul><li>インストール総数</li><li>クリックスルー<ul><li>クリックスルー計測で獲得したユーザー</li><li>2021年12月22日以降に記録されたインストールで利用できます</li></ul></li><li>ビュースルー<ul><li>2021年12月22日以降に記録されたインストールで利用できます</li><li>SKAdNetwork V2.2以降を実装しているアドネットワークに適用されます</li></ul></li></ul>このデータはポストバックの fidelity_type の項目から算出されます</td></tr><tr><td>コンバージョン値のNull率</td><td>コンバージョン値がNULLのポストバック数 / インストール数 \* 100 </td></tr><tr><td>インプレッション</td><td> </td></tr><tr><td>クリック</td><td> </td></tr><tr><td>Click-to-install率</td><td>インストール/クリック数 \* 100</td></tr><tr><td>コンバージョンしたユーザー</td><td><p>指定した測定イベントを実行したユニークユーザー数。</p><ul><li>SKAN 4モード：常に af_skad_revenue（それ以外を選択した場合、コンバージョンしたユーザーは空のままになります）</li><li>SKAN 4モード：常に af_skad_revenue（それ以外を選択した場合、コンバージョンしたユーザーは空のままになります）</li><li>Always af_skad_revenue</li><li>SKAdNetworkの計測設定</li><li> <br/><br/> </li></ul></td></tr><tr><td>コンバージョンしたユーザー / インストール</td><td> </td></tr><tr><td>合計収益</td><td>収益（null 値のモデル化データを含む）<a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">詳細はこちら</a> </td></tr><tr><td>総収益（モデル化されていない値）</td><td>コンバージョン値によってレポートされる収益 / モデル化されたデータは含まれていません）</td></tr><tr><td>収益 D1-D2</td><td>SKAN ウィンドウ1 の収益（変更しない限り 1-2日目 / null値のモデル化データを含む）：<a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">詳細はこちら</a> </td></tr><tr><td>収益 D1-D2 (モデル化されていない値)</td><td>SKANウィンドウ1で受け取った収益（変更しない限り1-2日目 / モデル化されたデータは含まれていません）</td></tr><tr><td>収益 D3-D7</td><td></td></tr><tr><td>収益 D8-D35</td><td></td></tr><tr><td>コスト</td><td><ul><li>アドネットワークから報告されるコスト </li><li>キャンペーン名が変更されると、最新のキャンペーン名を使用してコストが表示されます（複数のキャンペーン名が存在する場合）。</li></ul></td></tr><tr><td>ARPU</td><td><ul><li>ユーザーあたりの平均収益（null値のモデル化データを含む）：<a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">詳細はこちら</a> </li><li>数式：収益（推定値）／インストール数</li></ul></td></tr><tr><td>ARPU (モデル化されていない値)</td><td>ユーザーあたりの平均収益（モデル化されたデータは含まれていません）</td></tr><tr><td>ROI</td><td><ul><li>投資収益率（null値のモデル化データを含む）<a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">詳細はこちら</a> </li><li>数式：（収益 (推定値) - コスト)／コスト \* 100</li></ul></td></tr><tr><td>ROI（モデル化されていない値）</td><td>投資収益率（モデル化データは含まれていません）</td></tr><tr><td>ROAS</td><td><ul><li>広告費用対効果（null値のモデル化データを含む）<a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">詳細はこちら</a> </li><li>数式：(収益(推定値) / コスト) \* 100</li></ul></td></tr><tr><td>ROAS（モデル化されていない値）</td><td>広告費用対効果（モデル化データは含まれていません）</td></tr><tr><td>eCPI</td><td> </td></tr><tr><td colspan="2"><strong>アプリ内イベントの指標</strong></td></tr><tr><td>アプリ内イベント名</td><td> </td></tr><tr><td>eCPA</td><td><ul><li>アクションあたりの有効コスト（null値のモデル化データを含む）<a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">詳細はこちら</a> </li><li>数式：計算式： コスト ÷ イベントを実行したユニークユーザーユーザー (推定値)</li></ul></td></tr><tr><td>eCPA（モデル化されていない値）</td><td>アクションあたりの有効コスト（モデル化されたデータは含まれていません）</td></tr><tr><td>合計イベント数</td><td>すべてのウィンドウで発生したイベントの合計（null値のモデル化データを含む）<a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">詳細はこちら</a> </td></tr><tr><td>合計イベント数（モデル化されていない値）</td><td>すべてのウィンドウにわたるイベント発生の合（モデル化されたデータは含まれません）</td></tr><tr><td>イベント数 D1-D2\*</td><td>ウィンドウ1 のイベント発生（変更しない限り 1-2日目 / null値のモデル化データを含む）<a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">詳細はこちら</a> </td></tr><tr><td>イベント数 D1-D2（モデル化されていない値）</td><td>ウィンドウ1 のイベント発生回数（変更しない限り 1-2日目 / モデル化されたデータは含まれません）</td></tr><tr><td>イベント数 D3-D7</td><td></td></tr><tr><td>イベント数 D8-D35</td><td></td></tr></tbody></table>

</Accordion>

<div id="modeled-metrics-and-null-cv" />

<Accordion title="Nullコンバージョン値の推定">

SKAdNetwork（SKAN）のレポートは、以下の理由で制限される場合があります：

* SKANは、6ビットに制限されたコンバージョン値（CV）に依存しており、64の可能な値（0〜63）が取得できます。
* Appleは、ユーザーのプライバシーを保護するために、実際のコンバージョン値をレポートしない（そしてデータを "null" として返す）ことがあります。
* データは計測ウィンドウ内からのみ利用でき、完全なライフタイム値 (LTV) は不明です。

SKANの推定データは、以下のような問題を解決します。

* null 値の代わりに推定コンバージョン値を提供します。
* 推定の収益とイベント実行回数を提供します。
* アプリとキャンペーンLTVパフォーマンスに関するより最適な全体像を把握できます。

利用できる推定値の指標には次のものが含まれています：

* 収益
* イベントカウント
* eCPA
* ARPU
* ROI
* ROAS

推定のSKANデータについて

</Accordion>

<div id="appsflyer-attribution-vs-skan-attribution" />

<Accordion title="SKANアトリビューション">

SKANの指標は、AppsFlyer計測モデルを使用して利用できる指標とは異なります。次の表は、主な原因を列挙したものです。

定義：

* 時間：デフォルトのアクティビティウィンドウを24時間（SKAN 4にアップグレードすると48時間）と仮定します。
* SDKアプリに実装されたAppsFlyer SDK
* ルール<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">AppsFlyerの計測モデル</Anchor>

#### 計測フレームワークの違い

| コンセプト | SKAN | AppsFlyer |
| --- | --- | --- |
| サポートされているアトリビューション方法 | クリックとビュースルー計測向けApple SKAN。SKANをサポートするアドネットワークとSRNのアプリ間のキャンペーンのトラフィックが含まれます。 | <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">AppsFlyer計測モデル</Anchor>は、複数の計測方法とシナリオをサポートしています。<ul><li>モバイルウェブ</li><li>ビュースルー</li><li>クリックスルー</li><li>App Clip</li><li>Webアトリビューション</li><li>Apple検索広告</li><li>オウンドメディア</li><li>SRNトラフィック（同意ユーザー）</li><li>その他</li></ul> |
| 主なデータソース | <ul><li>SKANポストバック</li><li>SDK</li></ul> | SDKおよび関連するソリューション。  例：サーバー間（S2S）イベント |
| データ更新頻度 | <Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#skan">SKANデータの更新頻度に基づく</Anchor> | ユーザーがアプリを起動して使用する場合、リアルタイムです。 |
| タイムゾーン | UTC | アプリ固有のタイムゾーン。 |
| Install time | iOSポストバックの到着時刻から派生します。 | SDKによりレポートされます。 |
| アクティビティ期間 | 固定計測ウィンドウ中のユーザーアクティビティ（初回起動から開始） | インストール日から現在までのLTVデータを含みます。<br /><br />コホート0日目、コホート1日目、または双方の測定期間を一緒に確認する場合は、コホート分析を利用してください。<br /><br />コホート0日目には、24時間以下のアクティビティが含まれていると考えてください。例えば、ある日の18:00にユーザーがインストールした場合、コホート0日目には8時間のみが含まれます。 |
| インストールのレポート手段： | <ul><li>SKANSKAN: 非オーガニックインストールと非オーガニック再ダウンロードに限定されます。</li><li>**SDK**:SDK: 全てのインストールがレポートされます。指標のために、初回インストールのみが計測されます。つまり、リアトリビューションは無視されます。</li></ul> | SDKは、ルールを使用して全てのインストールを、初回インストールとリターゲティングインストール（リアトリビューション）に分類します。 |
| 広告の粒度レベル | キャンペーン、広告セット、広告セットID、広告、広告ID。 | 全階層フル階層：キャンペーン、キャンペーンID、広告セット、広告、チャネル、パートナー等の追加パラメーター。 |
| 再ダウンロード vs. リインストール | 再ダウンロードは、あるApple IDユーザーのアクションに関連するものです。リアトリビューションとは同一のものではありません。 | リターゲティング（リエンゲージメント、リアトリビューション）はリターゲティング管理画面に反映されます。再ダウンロードと同じではありません。 |

#### 指標の違い

| 指標 | SKAN | 従来のアトリビューション |
| --- | --- | --- |
| 非オーガニックインストール | AppsFlyerが受信した有効なiOSポストバックの数。<br /><br />AppsFlyerは、SKANの連携をAppsFlyerと完了していないアドネットワークのポストバックを取得しませんのでご留意ください。<br /><br />これにより、非オーガニックインストールの数が過少になり、オーガニックインストールの数が増加する可能性があります。 | <ul><li>SDKによりレポートされます。</li><li>メディアソースに起因されます。</li><li>ルールを使用してカウントします。</li></ul> |
| オーガニックインストール | SDKインストールからSKANインストールを差し引いたものです。 | <ul><li>SDKによりレポートされます。</li><li>どのメディアソースにもアトリビューションされません。</li><li>ルールを使用してカウントします。</li></ul> |
| 収益 | 非オーガニック*<br /><br />オーガニックオーガニック：SDKによってレポートされた全てのアプリ内イベントの収益から非オーガニックの収益を差し引いたもの。　**注：** 注意： オーガニック指標は、常に利用できるわけではありません。[詳細はこちら](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations)を参照してください。 | <ul><li>SDKおよびサーバー間APIによって報告されます。</li></ul> |
| 広告収益 | <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">利用可能</Anchor> | ユーザーレベルの広告収益はIDFVに基づいて計測されます。 |
| ROI/ROAS | 測定期間の収益額。 | <ul><li>LTV（顧客生涯価値）</li><li>UAとリターゲティングキャンペーンの指標。</li></ul> |

</Accordion>

<div id="faq-skan-discrepancies" />

<Accordion title="よくある質問—SKANの乖離">

| 理由 | 乖離—QA |
| --- | --- |
| A | **Q:Q：AppsFlyer管理画面とアドネットワーク管理画面のコンバージョン数が異なるのはなぜですか？**<br /><br />**A**:差異の原因<ul><li>インストール日 vs. ポストバック到着日：<ul><li>AppsFlyerAppsFlyer: インストール日は、iOSポストバック到着時間、ウィンドウの長さ、ポストバック遅延時間を考慮した式を使用して導出されます。</li><li>**広告媒体**広告媒体：通常、iOS ポストバックの到着時刻のみをインストール日として使用し、調整は行いません。</li><li>管理画面で**ポストバック到着日で表示**するオプションを選択すると、この差異がなくなります。</li></ul></li><li>ポストバック検証：AppsFlyerは受信したiOSポストバックを検証しAppleの署名が有効であることを確認します。アドネットワークは、AppsFlyerが無視する無効なポストバックを送信することがあります。</li><li>**ポストバックの欠如**：iOSポストバックはアドネットワークからAppsFlyerに送信される必要があります。AppsFlyerはポストバックをデバイスから直接受け取りません。ポストバックが欠如している場合、AppsFlyerではこれを把握する方法がありません。</li></ul> |
| B | **Q**:Q: **<Anchor target="_blank" href="/marketers/ja/docs/skan-aggregated-performance-report-api">SKANパフォーマンスAPI</Anchor>および管理画面と、SKAN集計ポストバックAPIの違いは何ですか？**<br /><br />**A**:A：ポストバックAPIの日付範囲は、AppsFlyerがポストバックを受信した日付です。パフォーマンスAPIの日付範囲は、原因Aで説明しているインストール日の算出方法で決定されます。 |
| C | **Q:Q：全てのアドネットワークは地域をレポートしますか？**<br /><br />**A:** いいえ。 |
| D | **Q:Q：オーバービュー管理画面とSKAN管理画面で差異があるのはなぜですか？**<br /><br />**A：A：差異の理由についての概要は、次のセクションを参照してください。** |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| 推定イベント実行回数 | <ul><li>イベント推定値は、 [Nullコンバージョン値の推定](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) で説明されている式に基づいています。</li><li>数式はデータの行ごとに適用されます。これにより、特定のメディアソースのイベント推定値と、そのキャンペーンの推定されたイベント数の合計との間に不一致が生じる可能性があります。</li></ul> |
| ポストバック到着日 | 日付範囲の最終日付は、最後のインストールが記録された日に制限されます。 |
| オーガニックデータ | <ul><li>SSOTでは、SKANアトリビューションイベントと AppsFlyerアトリビューションモデルの重複排除を行うため、SSOTを使用してオーガニックデータを表示することを検討してください。</li></ul> |
| 過去データ | 2024年11月 |
| 通貨設定 | USDまたは<Anchor target="_blank" href="/marketers/ja/docs/app-settings">アプリ設定ページ</Anchor>で設定されたアプリ固有の現地通貨で表示されます。 |
| タイムゾーン | SKAN計測のデータの場合、インストールとイベントはUTCで表示されますが、 MetaとGoogle SKANのデータは例外で、タイムゾーンはMetaアカウントとGoogleアカウントで設定されたタイムゾーンに基づいています。 |
|  | <ul><li>Google</li><li>メタ</li></ul> |

</Accordion>

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">AppsFlyer SKANソリューションガイド</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/about-att-and-skan">変更点は—AppsFlyerの iOS 14に関するアップデート</Anchor>

<div data-zendesk-anchors="dashboard-principles=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AE%E5%8E%9F%E5%89%87 01H81P8JPZM24J0536GKBPNFMJ=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AE%E5%8E%9F%E5%89%87 skan-dashboard-view-options=skan%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AE%E8%A1%A8%E7%A4%BA%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 01H81P8JPZC5K0KZR64P084N4W=skan%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AE%E8%A1%A8%E7%A4%BA%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3 dashboard-use=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AE%E4%BD%BF%E7%94%A8 01H81P8JPZGSHQVMG27YEJPARH=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AE%E4%BD%BF%E7%94%A8 01H81P8JPZ93G4EQY343SV2B1Q=dashboard-settings 01H81P8JPZV5F4VCZHR537HREH=filter-options 01H81P8JQ0KRGXWCVT82YW30CS=headline-metrics 01H81P8JQ0ETB0W3SGS56CBCX8=charts 01H81P8JQ0KK1NMRGFR0GBX4EK=metrics 01H81P8JQ0ZKGTRWNW95D015Z7=modeled-metrics-and-null-cv 01H81P8JQ18NGP8Z74D02DMQ7P=appsflyer-attribution-vs-skan-attribution attribution-framework-differences=%E8%A8%88%E6%B8%AC%E3%83%95%E3%83%AC%E3%83%BC%E3%83%A0%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AE%E9%81%95%E3%81%84 01H81P8JQ1VTYX3382WDXDMVT3=%E8%A8%88%E6%B8%AC%E3%83%95%E3%83%AC%E3%83%BC%E3%83%A0%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AE%E9%81%95%E3%81%84 metric-differences=%E6%8C%87%E6%A8%99%E3%81%AE%E9%81%95%E3%81%84 01H81P8JQ1M8M9TSHF0C12Z2QE=%E6%8C%87%E6%A8%99%E3%81%AE%E9%81%95%E3%81%84 faq%E2%80%94skan-discrepancies=faq-skan-discrepancies 01H81P8JQ157YYNX9C527ES4C8=faq-skan-discrepancies 01H81P8JQ1T3DE29Y14VARKASK=traits-and-limitations h_01HE7SWGPWNWG26CEN40VSTA9J=%E5%8F%82%E7%85%A7" />
