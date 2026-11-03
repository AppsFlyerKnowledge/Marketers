---
title: オーバービュー管理画面のiOS 指標（SKANとAppsFlyer指標の並列ビュー）
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
  created_at: '2021-08-02T07:18:18Z'
  edited_at: '2026-10-14T09:29:54Z'
  id: 4404976682257
  locale: ja
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ja/articles/4404976682257
---
> **概要**：概要: オーバービュー管理画面の並列ビューを利用してSKAdNetwork（SKAN）APIとAppsFlyer両方のアトリビューション数値を並べて表示します。広告主の皆様に最適なキャンペーンパフォーマンス指標を持つフレームワークを特定し、これを活用してインサイトを得て、キャンペーンを最適化します。

**並列ビュー：オーバービューV2.0管理画面にアトリビューション指標を並べて表示**

![SBSDB.png](https://files.readme.io/550c465c329eac484d2b2e5a65c8f48831c350c3c4b967315e3b2059ab95a36d-4409263804049.png)

## 最適なiOS 14以降のキャンペーンパフォーマンス指標の発見

iOS 14以降、SKAdNetwork APIによるアトリビューションと <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">AppsFlyerによるアトリビューション</Anchor> の両方でキャンペーンのパフォーマンスを計測しています。両者はそれぞれ異なるアトリビューション方法でインストールを計測し、それぞれ異なる特性と制限があることから、両者の数値にはしばしば乖離が生じます。例えば、SKAdNetwork APIには、Appleの検索広告キャンペーンやオウンドメディア経由の数値は含まれていません。逆に、SRN（サーバー連携媒体 - Google, Facebook, Twitterなど）のAppsFlyerの指標には、ATT拒否ユーザーのインストール数値は含まれていません。さらに、SKAdNetwork APIはインストール後の最初の1～3日間のパフォーマンスを測定するのに対し、AppsFlyerはライフタイムバリュー(LTV)を測定します。

「並列ビュー」では、両方のフレームワークが計測・提供するデータを使って、キャンペーンのパフォーマンスを見ることができます。各フレームワークの評価指標を比較し、どの評価指標が実際のキャンペーンパフォーマンスを最もよく表しているかを決定します。

`</SKAdNetwork APImar経由のk>`数値がSダッシュボードにKAdNet表示されないwork場合は、テーブル設定 を更新してください。

並列ビューでは、キャンペーンの評価指標を把握することができます。キャンペーンのパフォーマンス指標を、以下の観点から評価するために使用します。

* [正確性](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-precision)：
  * キャンペーンがもたらしたインストール数は？
  * SKANとAppsFlyerの測定基準が異なるのはなぜですか？
* 効果何人のユーザーがコンバージョンしたのか、そしてROIはどうなのか。

このページでは、データをどのように解釈し、そこからどのように実用的なインサイトを得るかについて、当社の市場に関する知識と見解に基づいたガイダンスを掲載しています。アプリごとにマーケティングの状況が異なることを考慮し、あなたのアプリの状況に合わせて私たちのガイダンスを検証してください。

**用語**

* **インストール**：
  * AppsFlyer：
  * SKAN：SKAN：新規インストールと再インストール
* 実数：実数とは、すべてのデータが含まれていなくても、そのデータを最もよく表している指標を意味します。
* 許諾ユーザー：パブリッシャーと広告主アプリの両方で ATTの承認/strong> を与えた iOS 14以降のユーザー。

<div id="campaign-precision" />

<Accordion title="キャンペーンの精度">

| 質問 | キャンペーンにアトリビューションされる実際のインストール数はどのくらいですか？ |
| --- | --- |
| 症状 | インストール・メトリクスは、フレームワークによって異なります。各フレームワークはインストールの一部をカウントしており、フレームワーク間で重複や相違がある場合があります。 |
| 対処法 | <ul><li>キャンペーンレベルでフレームワークのインストール数を比較します。</li><li>最も多くのインストール数を計測・表示しているフレームワークは、最も正確な指標を持っているとみなされますが、この指標にはアトリビューション数値が100%含まれていない場合があります。</li></ul> |
| 例 | ![S2Sinstalls.png](https://files.readme.io/9599ef8ac37aa1bc0da46112c1a7d6b4c42f3ff82efda0d0e4b47b8bddc6b52a-4406110225425.png)<br /><br />この表では、最も多くのインストールが行われたフレームワークがハイライトされています。これは、キャンペーンによってもたらされた実際のインストール数です。 |
| ヒント | この表をスプレッドシートなどにインポートすることで、どちらの指標が高いかを確定するプロセスを自動化することができます。最も多くのインストール数を報告しているフレームワークを特定するには、@max 関数と条件付き書式を使用します。 |

| 質問 | SKANとAppsFlyerの測定基準が異なるのはなぜですか？ |
| --- | --- |
| 症状 | インストールメトリクスが異なります。 |
| 概要 | <ul><li>AppsFlyerのフレームワーク（計測手法）は、AppsFlyer <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">アトリビューションモデル</Anchor> に基づいてインストールを決定しますが、SKANは、アプリキャンペーンからのみのインストールを測定します。</li><li>一般的に、SRNキャンペーンのインストール数はAppsFlyerの計測値よりも多くなりますが、これはAppsFlyerがATT同意ユーザーのみを計測しているためです。</li><li>非SRNネットワーク（アドネットワークなど）の場合、フレームワークごとの評価指標の間には、より密接な関係があることが多いです。</li></ul> |

</Accordion>

<div id="campaign-effectiveness" />

<Accordion title="キャンペーンの効果">

| 質問 | 何人のユーザーがコンバージョンしたのか、そしてROIはどうなのか。 |
| --- | --- |
| 注意事項 | <ul><li>収益やコンバージョン率の指標を決定するには、ユーザーのパフォーマンスを長期的に測定する必要があります。</li><li>SKANではインストール後12～72時間に限定されていますが、AppsFlyerでは無制限に測定できます（LTV）。</li><li>AppsFlyerのアトリビューションには、ATT同意したユーザーの数値のみが含まれます。</li></ul> |
| 対処法 | AppsFlyerのアトリビューションメトリクスが、全ユーザー（SKAN経由で報告されたユーザーを含む）を正確に表しているかどうかを検討する。そうであれば、ROIやコンバージョン率のようなキャンペーン効果の指標を推定するために使用します。<br /><br />コンバージョンしたユーザーの数を計算するには：<ol><li>AppsFlyerのコンバージョン率の指標（イベントごと）を使用します。</li><li>コンバージョン率に、キャンペーンの精度の項で説明した実際のユーザー数を乗じます。</li></ol>キャンペーンの収益とROIを算出するには：<ol><li>キャンペーンの精度の項で述べたように、実際のユーザー数 (a) を導き出します。</li><li>AppsFlyerのアトリビューション表示で提供される ARPU (b) の指標を使用する。</li><li>キャンペーンの収益を計算するには、次の式を使用します： a x b</li><li>ダッシュボードに表示されているキャンペーンコストを使用します。</li><li>ROI = (キャンペーンからの収益 - 広告費) / (広告費 * 100)</li></ol> |
| 例 | **ROIの算出**<br /><br />![SBSCost.png](https://files.readme.io/052c862e0a93c4e938f84b22e04e8b088bf50acbf047b821ca6cd20f5b9eae57-4409270882577.png)<br /><br />capaign a のROI計算例：<ol><li>想定ユーザー数：2000</li><li>ダッシュボードのARPU：0.76ドル</li><li>キャンペーンからの収益＝ 2000 × 0.76ドル ＝ 1520ドル</li><li>広告費：905.88ドル</li><li>ROI=(1520ドル-905.88ドル) / (905.88ドル*100) = 68%</li></ol> |
| ヒント | BIなど分析ツールを使用して、ATT許諾ユーザーのパフォーマンスをアプリのユーザー全体と比較します。結果が異なる場合は、それを考慮して救済措置の計算を調整する必要があります。 |

</Accordion>

<div id="campaign-efficiency" />

<Accordion title="キャンペーンの効率化">

| 質問 | 実際のキャンペーンのeCPIは？ |
| --- | --- |
| 症状 | eCPIのようなキャンペーンコスト関連の指標は、正確なユーザー数に依存しているため、誤解を招く恐れがあります。 |
| 対処法 | <ol><li>キャンペーンの精度の項で述べたように、実際のユーザー数 (a) を導き出します。</li><li>次の式を用いてeCPIを算出します： eCPI = コスト / (a)</li></ol> |
| 例 | ![mceclip1.png](https://files.readme.io/98fc80d1e995ba8ef0cce267fa12f22d48a77d7e25db4add1108144c6de7136d-4406111715217.png)<ul><li>実際のインストール数は、最も多くインストールされたフレームワークで決定されます。</li><li>eCPIは、コスト➗インストール数という計算式で算出されます。</li></ul> |

</Accordion>

## 「並列ビュー」を使用する

<div id="principles" />

<Accordion title="原則">

* SKAdNetwork APIとAppsFlyer計測の両方のアトリビューション・フレームワークで計測されたインストールを表示します。
* オーバービューV2.0の統合ビューを使用することで、キャンペーンのコンテキスト内で利用可能なすべてのデータが表示され、フィルターによって不用意に隠されることはありません。
* SKANデータは、SKANダッシュボードから得られるデータと同じです。
* フレームワーク間のタイミングの違いによる不一致を減らすために、ダッシュボードで以下のように日付の範囲を設定します。
  * 期間：
  * 最新の期間：
    * 現在の日付から3-5日前この範囲は、SKAN Conversion Studioで設定されたアクティビティウィンドウによって異なります。
    * Google Adsキャンペーンを実施している場合、最も直近の日付が現在の日付から8日前である必要があります。

</Accordion>

<div id="display-skan-metrics-in-the-table" />

<Accordion title="SKAdNetworkの数値をテーブルに表示">

**SKANの数値を表に表示するには**：

1. ⚙ （テーブル設定）をクリックします。   
   メトリクス選択ウィンドウが開きます。

   ![SelectSkan.png](https://files.readme.io/6b60fa8e2d10a1b61b1bfb4b7a968adb5ee16086d80c9cc8bc097b8e8ed77b51-4408473842833.png)
2. SKAN attribution をクリック
3. SKANインストール をクリック
4. SKAN収益 をクリック
5. [オプション] アプリ内イベントを追加または削除する。
   1. アプリ内イベントを選択します。
   2. 必要なアプリ内イベントを追加または削除します。
6. 適用をクリックします。   
   選択されたメトリクスとアプリ内イベントが表示されます。

</Accordion>

<div id="timerelated-differences" />

<Accordion title="タイムゾーンと更新頻度の違い">

<table><thead><tr><th>差異</th><th>AppsFlyer</th><th>SKAN</th></tr></thead><tbody><tr><td>過去データ</td><td><p>利用可能（制限なし）</p></td><td><p>利用可能（制限なし） </p></td></tr><tr><td>タイムゾーン</td><td><p>アプリ固有のタイムゾーン</p></td><td>UTC </td></tr><tr><td>データ更新頻度 </td><td>最大60分の遅延で継続的にリアルタイム更新</td><td><p><span>毎日 8:00 UTC（日本時間17時）に更新</span></p><p>データ遅延：アクティビティ期間に依存します。デフォルトデフォルト：2-5日（Google Adsのキャンペーンの場合は最大8日）</p></td></tr><tr><td>Install date</td><td>インストールされた日付 </td><td>iOSポストバックの到着時刻から推測して算出されます2024-02-26 </td></tr><tr><td>計測期間</td><td>無制限（LTVベース）</td><td><p>12-72時間のアクティビティウィンドウの期間に限定されます。デフォルト＝24時間</p></td></tr><tr><td>アトリビューションルックバック期間</td><td><ul><li>広告主またはSRNによって決定</li><li>7日</li></ul></td><td><ul><li>Apple社が決定</li><li>Click-to-Download30日間</li><li>60日間</li></ul></td></tr><tr><td colspan="3"><p>備考</p><p>(1) Google Adsのデータは最大8日遅れで更新されます。</p></td></tr></tbody></table>

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="コスト、クリック数、インプレッション数">

アドネットワークは、コスト、クリック、インプレッションの数値をAppsFlyerに提供しており、これらは両フレームワークで共通して表示されます。これらの数値をフレームワーク（SKAN / AppsFlyer）別に分離することはありません。

コストデータの場合、以下のようになります。

* 1日6回、平均4時間ごとに更新
* AppsFlyerは、キャンペーンに紐づく最初のエンゲージメント（クリックやインプレッション）を記録し、その後、エンゲージメントに紐づくキャンペーンコストを表示します。
* SKANのインストール数は、アプリを最初に開いてから72～120時間後に報告されるため、コスト指標は、インストール数と紐づけられる数日前に表示されることになります。
* Google広告からのインストールの場合、最大で8日間の遅延が発生します。

</Accordion>

<div id="data-scope-differences" />

<Accordion title="データスコープの違い">

| 差異 | AppsFlyer | SKAN |
| --- | --- | --- |
| Platform | すべて | iOS |
| アトリビューションの種類 | <ul><li>インストール</li><li>リエンゲージメント</li><li>リアトリビューション</li></ul> | <ul><li>インストール</li><li>再インストール</li></ul> |
| 広告収益 | 利用可能 | <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">限定的：仲介媒体に依存します</Anchor> |
| Apple検索広告 | 利用可能 | SKANでは計測されません |
| オウンドメディア | 利用可能 | SKANでは計測されません |
| Web-to-app | 利用可能 |  |
| 通貨設定 | App-specific currency | USD |

</Accordion>

<div id="matching-considerations" />

<Accordion title="マッチングの考慮事項">

<table><thead><tr><th>注意事項</th><th>AppsFlyer</th><th>SKAN</th></tr></thead><tbody><tr><td>代理店の運用媒体の開示設定</td><td>サポート対象</td><td><p>インストールをもたらしたメディアソースに紐づけられます。代理店は、媒体管理画面でキャンペーン名の冒頭に <em><a href="/partners/ja/docs/getting-started-agency-onboarding" target="_blank">代理店識別子</a></em>を付けることで、その代理店経由のトラフィックであることを特定することができます。例：AgencyName_Campaign_A</p></td></tr><tr><td>キャンペーン名の変更</td><td><ul><li>サポート対象</li><li>アドネットワークによって報告された最新の名前が、特定のキャンペーンIDに関連するすべてのインストールに使用されるキャンペーン名を決定します。これには過去に記録されたインストールも含まれます。 </li></ul></td><td><ul><li>サポートされておらず、計測対象外です</li><li>ユーザーがアプリをインストールした際にレポートされたキャンペーン名が使用されます。これは時間が経っても変わりません。そのため、1つのキャンペーンIDに複数の名前が紐付けられる場合があります。 </li></ul></td></tr><tr><td>サポートされているディメンション</td><td>制限なし</td><td><p><strong>利用可能：</strong></p><p><strong>代理店：</strong></p><p>対応していないディメンションを選択した場合、SKANデータは「なし」と表示されます。</p></td></tr><tr><td>SRNインストール数値</td><td>ATT同意を得たユーザーに限定されているため、AppsFlyerでレポートされる数値は、SKANで計測される指標やSRN自体が提供する指標よりも低いことが予想されます。 </td><td>SKANに紐づくすべてのインストール通常、AppsFlyerの数値よりも多くなります。 </td></tr><tr><td>SKANの隠れたキャンペーン</td><td colspan="2"><p>ダッシュボードのテーブルには、限られた数の行が含まれています。残りの行は、 <em>others</em> と表示される行にまとめられます。</p><p>この行の内訳を表示するには、表全体をスプレッドシートにエクスポートします。 </p></td></tr></tbody></table>

</Accordion>

<div id="dimensions-available" />

<Accordion title="利用可能なディメンション">

並列ビューで確認可能なディメンションは以下のメトリクスです：

* Media source
* キャンペーン名
* Campaign ID
* 日付
* アトリビューションタイプ

</Accordion>

<div data-zendesk-anchors="finding-the-best-ios-14-campaign-performance-metrics=%E6%9C%80%E9%81%A9%E3%81%AAios-14%E4%BB%A5%E9%99%8D%E3%81%AE%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E6%8C%87%E6%A8%99%E3%81%AE%E7%99%BA%E8%A6%8B h_01HYAQAR84BP9MRRXP7BPPDJ4N=%E6%9C%80%E9%81%A9%E3%81%AAios-14%E4%BB%A5%E9%99%8D%E3%81%AE%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E6%8C%87%E6%A8%99%E3%81%AE%E7%99%BA%E8%A6%8B h_01HYAQAR856G6VARSH746SJB5Z=campaign-precision h_01HYAQAR856JT2JX28SE3QY7VZ=campaign-effectiveness h_01HYAQAR85GZN1RZYNV2MV7DAP=campaign-efficiency using-sidebyside=%E4%B8%A6%E5%88%97%E3%83%93%E3%83%A5%E3%83%BC%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B h_01HYAQAR85FY6K8R574GWFQW91=%E4%B8%A6%E5%88%97%E3%83%93%E3%83%A5%E3%83%BC%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%99%E3%82%8B h_01HYAQAR85Z09SXSE8JGTG5AMF=principles h_01HYAQAR85V6CD29T9AY9XYX0Z=display-skan-metrics-in-the-table h_01HYAQAR85QSTB8QZPGMEV6MR9=timerelated-differences h_01HYAQAR85A03KNAHC5TEAZAZK=cost-clicks-and-impressions h_01HYAQAR85SPYQKDFP3CRGW5FN=data-scope-differences h_01HYAQAR85FSAXQ25X16N6XQEW=matching-considerations h_01HYAQAR85XF7CEG6F7PC44F1C=dimensions-available" />
