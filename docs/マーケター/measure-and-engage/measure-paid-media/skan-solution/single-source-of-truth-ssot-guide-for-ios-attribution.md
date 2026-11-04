---
title: iOSアトリビューション向けSSOT（Single Source of Truth）ガイド
metadata:
  keywords:
    - iOS
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
  created_at: '2021-11-11T09:28:42Z'
  edited_at: '2026-10-28T09:17:25Z'
  id: 4410634145425
  locale: ja
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ja/articles/4410634145425
---
> **概要**：iOS14以降の環境で、AppsFlyerはIDFA、IDFV、SKAN、Apple Adsなど、複数の照合方法によるアトリビューションデータを統合します。これにより、アプリキャンペーンの成果の全体像を把握できます。どのアトリビューション方法も、単独ではアプリの成果の全体像を捉えられません。同じユーザーが2つの方法でアトリビューションされる場合があるため、重複を除いて1人としてカウントする必要があります。これを実現するのが、AppsFlyerのSSOTです。 SSOTのレポートと指標は、同じユーザーを1回だけカウントし、正確なデータを示します。

<Embed title="iOSアトリビューション向けSSOT（Single Source of Truth）ガイド" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/545isomgo1" providerUrl="https://fast.wistia.com" />

<div id="about-single-source-of-truthtrue-ios-performance-data" />

## SSOTについて｜iOSの成果を正確に把握

iOS14以降では、AppsFlyerはSKAdNetwork、ATTに同意したユーザー、確率論的モデリング、増分効果に基づくインサイト、Apple Ads専用APIなど、複数のデータソースを使用してiOSユーザーをアトリビューションします。 IDFAがない場合、各アトリビューション方法の結果を、重複を避けながら結び付けることはほぼ不可能です。

SSOTは、インストールデータの重複を除去し、誤って分類されたユーザーの帰属先も修正します。本来はノンオーガニックのメディアソースに帰属するはずが、オーガニックに分類されていたユーザーが対象です。これにより、キャンペーンに帰属するインストール数が修正され、eCPI、ROI、ROASなど、インストール数に基づくコスト・収益関連の指標も正しく算出されます。

SSOTは、別の照合方法でもアトリビューションされたSKANインストールにフラグを付けます。集計指標の算出時にこのフラグを参照することで、同じユーザーの二重カウントを防ぎます。 SKANローデータを処理する際にも、同じようにこのフラグを使用します。

データにSSOTフラグを含めるには、Conversion StudioでSSOTをオンにする必要があります。

<div id="turn-on-single-source-of-truth" />

<Accordion title="SSOTの有効化">

![SSOTControl.png](https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png)

**SSOTをオンにする手順：**

1. 設定を始める前に、AppsFlyerの<Anchor target="_blank" href="https://content.appsflyer.com/ios-hub/billing/">SSOTの課金ポリシー</Anchor>を確認してください。
2. AppsFlyerで、**［設定］**＞<strong>［SKAN Conversion Studio］</strong>に移動します。
3. <strong>［カスタム］</strong>モードを選択します。
4. <strong>［SSOT］</strong>をオンにします。
5. 必要に応じて、その他の設定を行います。

<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>を参照してください。

</Accordion>

<div id="overview-dashboard-single-source-of-truth-view" />

## Overview dashboardのSSOTビュー

![SSOTisNowOn.png](https://files.readme.io/8e21fd0c64bb85fb94af752eb037472726d68cd55bf028dc5306b0acb398d199-31247490958225.png)

Overview dashboardのSSOTビューでは、ノンオーガニックの成果指標を全体的に把握できます。このビューには、以下の特徴があります。

* インストール指標に正確な値が表示されます。
* eCPI、ARPU、ROASなど、インストール数を基に計算するコスト・収益関連の指標も、正しく算出されます。
* オーガニック指標は、誤って分類されたインストールを考慮して調整されます。

このセクションでは、SSOTビュー特有の機能や、通常のビューとの違いを説明します。ここでは、Overview dashboardの基本的な使い方を理解していることを前提に説明します。

<div id="turn-on-single-source-of-truth-view" />

<Accordion title="SSOTビューの有効化">

SSOTビューのデータは、Conversion StudioでSSOTを有効にしてから3〜5日後に利用できるようになります。

**SSOTビューを有効にする手順**：

1. 開始する前に、Conversion Studioで<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#single-source-of-truth">［SSOT］</Anchor>がオンになっていることを確認してください。
2. AppsFlyerで、**［ダッシュボード］**＞<strong>［Overview］</strong>に移動します。  
   <Image alt="SelectSavedReport.png" src="https://files.readme.io/863a9c66c37e031a1f1b2a7fb3e0c68eb9c29405283214e68a432357c35524dd-31247514684177.png" width="243px" />
3. ▼をクリックします。
4. <strong>［Lite overview］</strong>を選択します。  
   SSOTのスイッチが表示されます。  
   <Image alt="SSOTviewon.png" src="https://files.readme.io/7b0a664f0882dad46e7239b5363592717358a79d920377dde13aa9c5dfbe84c3-31247514684433.png" width="246px" />
5. SSOTをオンにします。
6. 次のいずれかの状態になります。
   * ダッシュボードに指標とグラフが表示されます。  
     利用できるデータについては、以降のセクションで説明します。表示されるデータについては、以降のセクションを参照してください。  
     SSOTビューを新しいレポートとして保存します。手順は次のとおりです。  
     1. ▼をクリックします。
     2. <strong>［+新しいレポートを保存］</strong>をクリックします。
     3. レポート名を入力します。
     4. <strong>［保存］</strong>をクリックします。
   * データが表示されません。 SSOTをオンにしてからデータが表示されるまで、3〜5日かかる場合があります。 3〜5日経過してから、もう一度ダッシュボードを確認してください。

SSOTのスイッチをオフにすると、いつでも通常のデータに切り替えられます。SSOTビューでは利用できないディメンションも表示されます。  これにより、さらに詳しく分析できます。

</Accordion>

<div id="ssot-view-considerations" />

<Accordion title="SSOTビューの注意点">

SSOTビューでは、以下の点に注意してください。

* **nullのコンバージョン値（CV）**：モデリングで補完されます。高度な機械学習と[af\_attributionフラグ](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#アトリビューションフラグのフィールド)を使用し、CVがnullのインストールについて、AppsFlyerとSKANのどちらに帰属するかを推定します。 SKANに帰属する場合、インストール後のすべてのSKAN計測結果がSSOTダッシュボードに含まれます。 <Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data">詳細はこちら</Anchor>
* **再ダウンロード**：インストール指標に含まれます。初回インストールと再ダウンロードは区別されません。
* **タイムゾーン**：AppsFlyerが報告するインストールとイベントは、UTC、または<Anchor target="_blank" href="/marketers/ja/docs/app-settings">アプリ設定画面</Anchor>で指定したアプリ固有のタイムゾーンで表示されます。 SKANが報告するインストールとイベントはUTCで表示されます。ただし、MetaとGoogleのSKANデータには、それぞれのアカウントに設定されたタイムゾーンが使用されます。
* **通貨**：USD、または<Anchor target="_blank" href="/marketers/ja/docs/app-settings">アプリ設定画面</Anchor>で指定したアプリ固有の通貨で表示されます。
* **収益指標（D2、D7）：** SKANポストバックの情報不足や欠落（CVがnullの場合）を補うため、モデリングによる推定データが含まれます。より長期のコホートデータ（D14、D21、D30）は、SSOTのData Lockerレポートからエクスポートできます。

<div id="filter-considerations" />

#### フィルターに関する注意点

以下の表に示すように、フィルターはデータの表示や指標に影響します。

| フィルター | 注意点 |
| --- | --- |
| SSOT | SSOTの指標を表示するには、スイッチがオンになっていることを確認してください。 |
| ビューの種類 | <ul><li>**ユーザー獲得：** SSOTデータの確認に推奨するビューです。</li><li>**リターゲティング**：SKANはリターゲティングに対応していません。</li><li>**統合**：インストールキャンペーンにはSSOTデータが含まれます。リターゲティングキャンペーンはSSOTの影響を受けません。</li></ul> |
| 日付 | <ul><li>［推奨］正確な結果を得るには、確認したいコホートを含む十分な長さの期間を選択してください。たとえば、D30収益には31日間が必要です。また、直近3日間は対象から除外してください。</li><li>通常、選択できる最も古い日付は、SSOTをオンにした3日後です。この日付はAppsFlyerが決定します。</li><li>適切な期間を選択する例：<ul><li>今日が2月10日で、1月29日にSSOTをオンにした場合、 2月1日〜7日を選択できます。</li></ul></li><li>収益など、一部のデータはSSOTをオンにしてから利用可能になるまで、8日かかる場合があります。</li><li>GoogleのSKANインストールは、最大45日遅れて報告される場合があります。</li></ul> |
| キャンペーンのフィルター | 以下のキャンペーン階層で絞り込めます。<ul><li>メディアソース</li><li>キャンペーン</li></ul> |
| 主要KPI | SSOTダッシュボードの主要KPIでは、以下を確認できます。<ul><li>ユーザー獲得：ノンオーガニックとオーガニックの両方</li><li>重複するSKANインストール</li><li>リターゲティング：リエンゲージメントとリアトリビューション</li><li>コスト</li><li>eCPI</li></ul>各KPIには、増減率が表示されます。この値は、表示中のKPIを直前の同じ長さの期間と比較したものです。たとえば、今週と先週、または選択した期間とその直前の同じ日数の期間を比較します。インストール数がX%増加と表示されている場合、直前の比較期間のインストール数がX%少なかったことを意味します。 |
| グラフ | **利用できるディメンション：**<ul><li>アトリビューション方法：<ul><li>AppsFlyerの従来のアトリビューション：SKANを含む複数の方法で照合されたインストール。ダッシュボードでは、同じインストールの二重カウントを避けるため、SKANのレコードを除外します。 SKANローデータでは、そのインストールのaf\_attribution\_flagがtrueに設定されます。</li><li>SKANアトリビューション：SKANでのみ照合され、ほかの方法では照合されなかったインストール。 SKANローデータでは、そのインストールのaf\_attribution\_flagがfalseに設定されます。</li></ul></li><li>アトリビューションの種類</li><li>アトリビューションに使用された接点の種類</li><li>キャンペーン</li><li>キャンペーンID</li><li>メディアソース</li><li>ソース</li><li>アプリID（一部のグラフのみ）</li><li>地域（SKANの地域情報は<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#geo">モデリングによる推定値</Anchor>です）</li><li>アプリ内イベント名（SKAN Conversion Studioで設定した個々のアプリ内イベントの名前）。</li></ul>**指標：**<br /><br />指標のセクションで説明するとおりです。 |
| 表 | **グループ化：**<ul><li>［デフォルト］メディアソースとキャンペーンでグループ化されます。</li><li>メディアソース、アトリビューションの種類、アトリビューション方法、キャンペーン、キャンペーンID、アトリビューションに使用された接点の種類、日付、ソース、地域、およびそれらの組み合わせでグループ化できます。**注意**：SKANの地域情報は<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#geo">モデリングで推定</Anchor>されます。</li><li>ノンオーガニックトラフィックにのみ適用されるディメンションでグループ化すると、オーガニックのメディアソースにはN/Aと表示されます。</li></ul>**指標：**<br /><br />指標のセクションで説明するとおりです。 |

</Accordion>

<div id="metrics" />

<Accordion title="指標">

SSOTダッシュボードで利用できる指標：

| 指標 | 説明と注意点 |
| --- | --- |
| グループ化 | <ul><li>［デフォルト］メディアソースとキャンペーンでグループ化されます。</li><li>メディアソース、アトリビューションの種類、アトリビューション方法、キャンペーン、キャンペーンID、アトリビューションに使用された接点の種類、日付、ソース、およびそれらの組み合わせでグループ化できます。</li><li>ノンオーガニックトラフィックにのみ適用されるディメンションでグループ化すると、オーガニックのメディアソースにはN/Aと表示されます。</li></ul> |
| **SSOTアトリビューション** | **選択期間中のSSOTインストール、リアトリビューション、リエンゲージメントの主要な内訳です。**<ul><li>**ノンオーガニック：ユーザーの獲得につながったキャンペーン。 SSOTにより、同じインストールは1回だけカウントされます。**</li><li>**オーガニックの指標。**</li></ul> |
| 合計 | インストール、リアトリビューション、リエンゲージメントの数。 |
| インストール | アプリをインストールしたユニークユーザー数。 UAキャンペーンでAppsFlyerがアトリビューションしたインストール数に、SKANが報告した新規インストールと再ダウンロードから重複を除いた件数を加えて算出します。 |
| リアトリビューション | リターゲティング指標は、［統合］ビューと［リターゲティング］ビューで利用できます。 SKANはリターゲティングに対応していない点に注意してください。 |
| リエンゲージメント | リターゲティング指標は、［統合］ビューと［リターゲティング］ビューで利用できます。 SKANはリターゲティングに対応していない点に注意してください。 |
| **その他の指標** | **SSOTと広告の成果に関する、その他の各種指標** |
| 重複するSKANインストール | af\_attribution\_flag=trueのSKANインストール数 |
| クリック | アドネットワークからAPI経由で報告されたクリックとインプレッションのデータ。 SSOTは接点の指標に影響しません。 |
| インプレッション | アドネットワークからAPI経由で報告されたクリックとインプレッションのデータ。 SSOTは接点の指標に影響しません。 |
| コンバージョン率 | クリックからインストールへのコンバージョン率 |
| コスト（$） | アドネットワークからAPI経由で報告された<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview">キャンペーンコスト</Anchor>のデータ。 1件以上のインストールがあるキャンペーンのデータが表示されます。 SSOTによって、報告された総コストが変わることはありません。影響するのは、インストール数を用いて算出する指標のみです。 |
| 平均eCPI（$） | 実効インストール単価は、SSOTビューのインストール数を使用して算出します。オーガニックインストールは含まれません。 |
| CPM | 1,000インプレッションあたりのコスト。計算式：（コスト÷インプレッション数）×1,000 |
| CPC | クリック単価。計算式：コスト÷クリック数 |
| クリックスルー | ユーザーが広告をクリックした後に発生したアトリビューションの数（CTA） |
| CTR | クリック率。計算式：クリック数÷インプレッション数 |
| ビュースルー | <span id="simple-tabpanel-2"></span>ユーザーが広告を閲覧した後に発生したアトリビューションの数（VTA） |
| 収益（D2） | <ul><li>SKANポストバックの情報不足や欠落（CVがnullの場合）を補うため、モデリングによる推定データが含まれます。</li></ul>最初のSKAN計測期間（D2）における、SKANとAppsFlyerの従来のアトリビューションによる収益（広告収益を含む）：<ul><li>**SKAN収益：** SKANインストール（af\_attribution\_flag=false/null）から生じた収益。 <Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#revenue-component">Conversion Studioの収益に関するCV設定</Anchor>と、計測期間に基づきます。</li><li>**従来のアトリビューションによる収益：** AppsFlyerの従来の方法でアトリビューションされたインストールについて、SKANの計測期間内にそのユーザーから生じた収益。</li><li>Conversion StudioでSKAN 4を使用している場合、インストール後2日間のデータです。 Conversion StudioでSKAN 3を使用している場合は、設定したSKANのアクティビティ期間に基づきます。期間が2日より長くても短くても、この設定が適用されます。</li><li>**例**：<ul><li>アクティビティ期間が24時間の場合。</li><li>収益イベントがインストールの翌日（X+1日目）に発生していても、24時間のアクティビティ期間内であるとします。<ul><li>インストール日と日付が異なっていても、24時間の期間内に発生しているため、SKANとAppsFlyerが報告する収益の両方にカウントされます。</li></ul></li></ul></li></ul>**ヒント**：SKAN収益の精度を高めるには、次の方法があります。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">SKAN広告収益の手順</Anchor>に従います。</li><li>収益の推奨設定を利用します。</li></ul> |
| 収益D7 | <ul><li>SKANポストバックの情報不足や欠落（CVがnullの場合）を補うため、モデリングによる推定データが含まれます。</li><li>SKANの計測期間を超え、インストール後7日目までのモデリングによる推定データが含まれます。<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#revenue-ltv">詳細はこちら</Anchor></li><li>モデリングには収益D2のデータが必要です。</li></ul> |
| ARPU D2 | ユーザー1人あたりの平均収益。<br /><br />計算式：収益÷ユニークユーザー数<br /><br />Conversion StudioでSKAN 4を使用している場合、インストール後2日間のデータです。 Conversion StudioでSKAN 3を使用している場合は、設定したSKANのアクティビティ期間に基づきます。期間が2日より長くても短くても、この設定が適用されます。 |
| ARPU D7 | SKANの計測期間を超え、インストール後7日目までのモデリングによる推定データが含まれます。<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#revenue-ltv">詳細はこちら</Anchor> |
| ROAS D2 | 広告費用対効果（%）。<br /><br />計算式：収益÷コスト×100<br /><br />Conversion StudioでSKAN 4を使用している場合、インストール後2日間のデータです。 Conversion StudioでSKAN 3を使用している場合は、設定したSKANのアクティビティ期間に基づきます。期間が2日より長くても短くても、この設定が適用されます。 |
| ROAS D7 | SKANの計測期間を超え、インストール後7日目までのモデリングによる推定データが含まれます。<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#revenue-ltv">詳細はこちら</Anchor> |
| ROI D2 | 投資収益率（%）。<br /><br />計算式：（収益−コスト）÷コスト×100<br /><br />Conversion StudioでSKAN 4を使用している場合、インストール後2日間のデータです。 Conversion StudioでSKAN 3を使用している場合は、設定したSKANのアクティビティ期間に基づきます。期間が2日より長くても短くても、この設定が適用されます。 |
| ROI D7 | SKANの計測期間を超え、インストール後7日目までのモデリングによる推定データが含まれます。<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#revenue-ltv">詳細はこちら</Anchor> |
| 粗利益D2 | 収益からキャンペーンコストを差し引いた利益。<br /><br />計算式：収益−コスト<br /><br />Conversion StudioでSKAN 4を使用している場合、インストール後2日間のデータです。 Conversion StudioでSKAN 3を使用している場合は、設定したSKANのアクティビティ期間に基づきます。期間が2日より長くても短くても、この設定が適用されます。 |
| 粗利益D7 | SKANの計測期間を超え、インストール後7日目までのモデリングによる推定データが含まれます。<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#revenue-ltv">詳細はこちら</Anchor> |
| **アプリ内イベントの指標** | **特定のアプリ内イベント（IAE）に関する指標** |
| イベントのユニークユーザー数（D2） | イベントを実行したユニークユーザー数。AppsFlyerとSKANのデータを組み合わせて計測し、CVがnullの場合の推定データも含めます。 SKAN 4では、インストール後の最初の2日間の累計データです。 SKAN 3では、設定したアクティビティ期間内の、インストール後の累計データです。 |
| イベントのユニークユーザー数（D7） | AppsFlyerとSKANのデータを組み合わせ、モデリングで推定した、イベントを実行したユニークユーザー数。 SKANの計測期間を超え、インストール後7日目までのモデリングによる推定データが含まれます。<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#inapp-event-ltv">詳細はこちら</Anchor><br /><br />注意：D7のユニークユーザー数には、D2のユニークユーザー数も含まれます。 |
| イベントeCPA（D2） | 実効アクション単価：コスト÷イベントを実行したユニークユーザー数 |
| イベントeCPA（D7） | 実効アクション単価：コスト÷イベントを実行したユニークユーザー数。 SKANの計測期間を超え、インストール後7日目までのモデリングによる推定データが含まれます。<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#inapp-event-ltv">詳細はこちら</Anchor> |
| イベントのコンバージョン率（D2） | アトリビューションされたユーザー（インストール、リエンゲージメント、リアトリビューションを行ったユーザー）のうち、イベントを実行したユニークユーザーの割合（%）。計算式：ユニークユーザー数÷アトリビューション数×100 |
| イベントのコンバージョン率（D7） | アトリビューションされたユーザー（インストール、リエンゲージメント、リアトリビューションを行ったユーザー）のうち、イベントを実行したユニークユーザーの割合（%）。計算式：ユニークユーザー数÷アトリビューション数×100。 SKANの計測期間を超え、インストール後7日目までのモデリングによる推定データが含まれます。<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#inapp-event-ltv">詳細はこちら</Anchor> |
| イベント収益（D2） | インストール後の指定日数内に、このイベントによって生じた収益 |
| イベント収益（D7） | インストール後の指定日数内に、このイベントによって生じた収益。 SKANの計測期間を超え、インストール後7日目までのモデリングによる推定データが含まれます。<Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#inapp-event-ltv">詳細はこちら</Anchor> |

</Accordion>

<div id="how-does-ssot-work" />

## SSOTの仕組み

<div id="understanding-skanaf-modeled-attribution-duplication" />

<Accordion title="SKANとAppsFlyerのモデリングでアトリビューションが重複する仕組み">

SKANとAppsFlyerのモデリングによるアトリビューションは、動作の仕組みや、仕様・制限事項が異なります。そのため、各インストールがノンオーガニックのメディアソースに帰属するかどうかは、次のパターンに分かれます。

* SKANまたはAppsFlyerのモデルの一方だけでアトリビューションされる（重複なし）。
* SKANとAppsFlyerのモデルの両方でアトリビューションされる（重複あり）。この場合、[SSOT](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#ssot-mechanism-workings)がaf\_attribution\_flag=TRUEというフラグでSKANインストールの重複を示します。 SSOTダッシュボードでは、2件ではなく1件のインストールとして表示されます。
* SKANでもAppsFlyerのモデルでもアトリビューションされない（オーガニック）。

SKANとAppsFlyerのモデルによるアトリビューションの各パターンを、以下のベン図に示します。

![skan_af_model_diagram.png](https://files.readme.io/1b305d053044f79d12b9190d0b6c24dcc7e0bd17e17ef29029ad0b1c3c7d84c0-31247514684689.png)

以下の表では、各パターンが発生する理由を説明します。

| SKANのみ | AppsFlyerのモデルのみ | SKANとAppsFlyerのモデルの両方 | どちらでもアトリビューションされない |
| --- | --- | --- | --- |
| <ul><li>メディアソースがSRNで、ユーザーのデバイスがiOS14.5以降であり、ユーザーが双方のアプリでATTに同意していない場合。</li><li>メディアソースが非SRNで、ユーザーのデバイスがiOS14.5以降であり、確率論的モデリングを利用できず、ユーザーが双方のアプリでATTに同意していない場合。</li></ul> | <ul><li>ユーザーのデバイスがiOS14.4以前の場合。</li><li>メディアソースがSKANに対応していない場合。</li><li>Webからアプリへの導線でインストールされた場合（SKANはアプリ間の導線にのみ対応）。</li><li>リターゲティングによるインストールの場合（SKANは非対応）。</li></ul> | 制限がなく、SKANとAppsFlyerのモデルの両方でインストールをアトリビューションできる場合。<br /><br />この場合、同じインストールが重複して計測されるため、SSOTで重複を除去する必要があります。 | ユーザーがオーガニックの場合。 |

</Accordion>

<div id="ssot-mechanism-workings" />

<Accordion title="SSOTの処理の流れ">

SSOTは、以下の図に示す流れで動作します。

![SingleSourceOfTruth.png](https://files.readme.io/882527d4828cf3c7156caf183652368de33463a440715c69f7ec39bfd0f655fa-31247514685329.png)

**SSOTはどのように動作するのか**

SSOTは、ユーザーデバイス上のアプリに実装されたAppsFlyer SDKと、AppsFlyerプラットフォームで、次のように動作します。

**ユーザーデバイス：**

* ユーザーがアプリを初めて起動します。 AppsFlyerプラットフォームが、ユーザーの帰属先の特定を試みます。アトリビューションできるかどうかは、キャンペーンの種類とユーザーの同意（ATT）状況によって異なります。
* アトリビューションに成功すると、SDKがコンバージョン値（CV）内のアトリビューションビットを設定します。
* 通常のSKAdNetworkの処理は、そのまま続行されます。つまり、計測期間が終了するまで、ユーザーの行動の計測とCVの設定が続きます。
* その後、iOSがポストバックを送信します。

**AppsFlyerプラットフォーム**

* AppsFlyerはiOSのポストバックを受信してCVをデコードし、アトリビューションビットの値をaf\_attribution\_flagで提供します。各値の意味は、以下の表のとおりです。

**注意点**

* 通常、AppsFlyerは再インストールをカウントしません。 SSOTでは、再インストールかどうかは考慮しません。したがって、SSOTの分析では再インストールによるSKANインストールの重複は除去されず、再インストールの状態がaf\_attributionフラグの設定に影響することもありません。

<div id="attribution-flag-field" />

#### **アトリビューションフラグのフィールド**

| コンバージョン値内のSSOTインジケーター | 意味 | af\_attribution\_flagフィールド |
| --- | --- | --- |
| オン | Conversion StudioでSSOTがオンになっており、AppsFlyerがユーザーのアトリビューションに成功した状態。 | True |
| オフ | Conversion StudioでSSOTがオンになっているものの、AppsFlyerがユーザーをアトリビューションしなかった状態。 | False |
| -- | Conversion StudioでSSOTがオフになっている状態。 | Null |

**af\_attribution\_flag（アトリビューションビット）のレポートへの反映**

* SKANダッシュボード：SKANポストバックで報告された成果のみを反映します。そのため、af\_attributionフラグは考慮されず、重複も除去されません。
* SKANの<Anchor target="_blank" href="/marketers/ja/docs/skan-aggregated-performance-report-api">集計パフォーマンスレポート</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/skan-raw-data-reports">ローデータレポート</Anchor>：これらのレポートにはaf\_attribution\_flagが含まれます。レポートの用途に応じて使用してください。 SKANデータとAppsFlyerデータを統合する場合は、このフラグを使用して重複を除去してください。これは、ローデータレポートと集計レポートの両方に当てはまります。
* Overview dashboardのSSOTビュー：SKANデータの重複を除去したうえで、SKAN、IDFA、IDFV、Apple Adsなど、すべてのアトリビューション方法のデータを1つのビューに統合します。

</Accordion>

<div id="metrics-derived-by-combining-data-from-multiple-attribution-methods" />

<Accordion title="複数のアトリビューション方法を組み合わせて算出する指標">

SKANデータとほかのアトリビューション方法によるデータを統合する場合は、af\_attribution\_flagを使用して重複を除去してください。これは、ローデータレポートと集計レポートの両方に当てはまります。

af\_attribution\_flagを使用すると、たとえば以下の指標を算出できます。

* ノンオーガニックインストール
* オーガニックインストール
* eCPI
* コホート収益

各指標の計算式：

| 指標の説明 | 記号 | 計算式 |
| --- | --- | --- |
| AppsFlyerのノンオーガニックインストール | A | AppsFlyerが報告したノンオーガニックインストール |
| SKANの重複のないインストール | B | af\_attribution\_flag=falseのSKANインストール |
| すべてのノンオーガニックインストール | C | A + B |
| オーガニックインストール | D | 総インストール数−C<br /><br />**注意**：総インストール数とは、帰属先にかかわらず、AppsFlyer SDKが記録したすべてのインストールを指します。 |
| キャンペーンeCPI | E | コスト÷C |
| コホート収益 | F | 以下を合計します。<ul><li>Aに該当するユーザーの収益。インストール直後からSKANの計測期間と同じ長さの期間に発生したイベントを含めます。</li><li>af\_attribution\_flag=falseのSKAN収益</li></ul> |
| オーガニック収益D2 | G | D2の総収益−AとBのインストールによるD2収益 |
| オーガニックIAEユニークユーザー数D2 | H | D2のIAE総ユニークユーザー数−AとBのインストールによるD2イベントユニークユーザー数 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| SSOTビュー | 過去5日間の各日に、`af_attribution_flag=true`を含むSKANポストバックが少なくとも1件ある場合にのみ、SSOTを利用できます。 |
| 総インストール数 | SSOTをオンにすると、オフの場合よりも多くのインストールが表示されることがあります。理由の1つは、CVがnullの場合のモデリングが、インストール日の算出に影響することです。そのため、同じ日付のインストールを比較しても差が生じる場合があります。また、nullのCVがモデリングされない場合は、すべてのSKANインストールが重複なしとしてカウントされ、総インストール数が過大になる場合があります。この場合、フラグは`af_attribution_flag=false`となります。 |
| 収益 | 収益と関連指標（ARPU、ROAS、ROI、粗利益）は、2022年9月1日以降のデータに対応しています。 |
| 代理店 | 代理店ユーザーは、Overview dashboardでSSOTビューを表示できます。 |
| アドネットワーク | <ul><li>アドネットワークは、Overview dashboardのSSOTビューで、自社のメディアソースに帰属するデータを確認できます。 SSOTビューを表示するには、以下の条件を満たす必要があります。<ul><li>広告主がConversion StudioでSSOTをオンにしていること。</li><li>アドネットワークがSKANキャンペーンを実施していること。</li><li>アドネットワークが、集計データへのアクセスに<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">必要な権限</Anchor>を広告主から付与されていること。</li></ul></li><li>アドネットワークは、skad\_af\_attribution\_flagフィールドのマクロを追加することで、SKANポストバック経由でSSOTのシグナルを受信できます。<Anchor target="_blank" href="/partners/ja/docs/skan-integration-guide-for-ad-networks#appsflyerからのデータ受け取り">詳細はこちら</Anchor></li></ul> |
| D7指標 | オーガニックトラフィックのD7指標は、2025年2月16日以降のデータで利用できます。<br /><br />以下の場合、D7指標が表示されないか、D2指標より小さくなることがあります。<ul><li>選択期間に、まだ8日間経過していない日付が含まれている場合。</li><li>モデリングによる推定データを利用できない場合。たとえば、14日分の収益データがない場合が該当します。 <Anchor target="_blank" href="/marketers/ja/docs/skan-modeled-data#revenue-ltv">詳細はこちら</Anchor></li><li>過去14日以内にSKAN Conversion Studioの設定を変更した場合。</li><li>特定の日付のインストール数が10件未満の場合。</li></ul> |
| SKAN Conversion Studioの設定変更 | SKAN Conversion Studioの設定を変更すると、約96時間にわたりSSOTデータが不正確になる場合があります。 AppsFlyerが直ちに新しいスキーマでポストバックのデコードを開始する一方で、以前のスキーマでCVを設定したインストールのポストバックが引き続き届くためです。 |
| AppsFlyerが報告するデータ | <ul><li>AppsFlyerが報告するデータは、AFモデルデータとも呼ばれます。SKAN以外のAppsFlyerのアトリビューション方法で帰属した、インストールやその他のイベントのデータを指します。</li><li>SSOTダッシュボードは、SKANとAppsFlyerの別の方法の両方でアトリビューションされたインストールやイベントの重複を防ぐことを目的としています。</li><li>SSOTをオンにした状態で、それ以前の期間を表示すると、SSOTダッシュボードに表示されるのはAppsFlyerが報告するデータのみです。</li></ul> |
| アプリ内イベント | ディメンションとして表示できるアプリ内イベントと、その指標の対象は、以下に限られます。<ul><li>ウィンドウ1の期間中に発生したイベント。</li></ul> |
| SKANポストバックの遅延 | SKANポストバックが大幅に遅れて届くと、D7などの後の日数のデータが、当初はD2などの前の日数のデータより小さく表示される場合があります。たとえば、Google APIからのデータは最大15日遅れることがあります。この遅延は、SSOTモデルの精度に影響する場合があります。そのため、モデルの精度を評価する際は、データがすべて揃うよう、インストール日から少なくとも15日待つことを推奨します。 |

</Accordion>

<div id="see-also" />

> 📄 **関連情報**
>
> * Overview dashboard
> * <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKANソリューションガイド</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>

<div data-zendesk-anchors="how-to-get-true-ios-14-performance-data=ssot%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6ios%E3%81%AE%E6%88%90%E6%9E%9C%E3%82%92%E6%AD%A3%E7%A2%BA%E3%81%AB%E6%8A%8A%E6%8F%A1 01H8TZV6P41Z3ZEZ8VS86DK1J9=ssot%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6ios%E3%81%AE%E6%88%90%E6%9E%9C%E3%82%92%E6%AD%A3%E7%A2%BA%E3%81%AB%E6%8A%8A%E6%8F%A1 01H8TZV6P4G5AF2MJDQB8J6W2M=turn-on-single-source-of-truth overview-dashboard-single-source-of-truth-view=overview-dashboard%E3%81%AEssot%E3%83%93%E3%83%A5%E3%83%BC 01H8TZV6P4ZBJTDH0FQ6F5D6Q9=overview-dashboard%E3%81%AEssot%E3%83%93%E3%83%A5%E3%83%BC 01H8TZV6P47ZE6PMPF7S9GCJ16=turn-on-single-source-of-truth-view 01H8TZV6P4VCC5NRKBRQNJ4NX3=ssot-view-considerations filter-considerations=%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E6%B3%A8%E6%84%8F%E7%82%B9 01H8TZV6P4QXEXYWSXKDB7B5SV=%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E6%B3%A8%E6%84%8F%E7%82%B9 01H8TZV6P4YNTFBX5RXVKK8J0F=metrics how-does-ssot-work=ssot%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF 01H8TZV6P4K8VXNKDR7JHM8PFW=ssot%E3%81%AE%E4%BB%95%E7%B5%84%E3%81%BF 01H8TZV6P4QYQJ177E2ZG676MH=understanding-skanaf-modeled-attribution-duplication 01H8TZV6P58E502Y1FDFHC3KHM=ssot-mechanism-workings attribution-flag-field=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%A9%E3%82%B0%E3%81%AE%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 01H8TZV6P5SSKDTKV4BV3TTA7D=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%A9%E3%82%B0%E3%81%AE%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89 01H8TZV6P5AHZD8VRWRS4SPBYW=metrics-derived-by-combining-data-from-multiple-attribution-methods 01H8TZV6P5KN4F24ZN33V0TK7K=traits-and-limitations h_01HE182N43SSBX051E4GK7NFQ8=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
