---
title: リターゲティング向けインクリメンタリティ（純増検証）概要
metadata:
  keywords:
    - Analytics
    - Audiences
    - Advertisers
    - Premium
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2020-05-29T19:29:03Z'
  edited_at: '2026-10-14T09:28:56Z'
  id: 360009360978
  locale: ja
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/ja/articles/360009360978
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** インクリメンタリティ機能で、リターゲティングキャンペーンによって生成された純増リフトを計測する方法を理解しましょう。

<div id="what-is-incrementality" />

## 「インクリメンタリティ」とは？

インクリメンタリティ（純増）を理解するには、例を挙げるのが分かりやすいでしょう。

最近、リマーケティングキャンペーンを実施したとします。わかりやすくするために、ここでは1つのアドネットワークだけで配信した場合とします。このキャンペーンのコンバージョン率は5％でした。

さて、このキャンペーンの成果を評価したいと考えており、ここで重要な（そして最も難しい）質問に答える必要があります。

* このキャンペーンのコンバージョン率の5%は良い数字でしょうか？
* そのキャンペーンが本当にコンバージョンの増加につながったことをどうやって知ることができるでしょうか？
* このキャンペーンは、配信にかかったコストに見合うものでしたか？

これらの質問に正確かつ偏りなく答えるためには、測定されたコンバージョン以上の点について考慮する必要があります。リマーケティングキャンペーンと接触しなかったとしても、自然に（オーガニック経由で）コンバージョンしていたであろうユーザーの数を考慮しなければなりません。

このコンバージョン総数と、キャンペーンの有無に関わらず発生したであろうコンバージョン数との差は、**純増（インクリメンタル）リフト**（あるいは単に**リフト**）と呼ばれ、キャンペーンの真の価値を判断する上で重要なものとなります。それを測定するのは非常に難しいことですが、AppsFlyerのIncrementalityソリューションはまさにそれを目的としています。

<div id="incrementality-experiments" />

### インクリメンタリティテスト

インクリメンタリティは、似たようなグループの行動を比較するための科学的に有効な検証を可能にすることで、純増リフトを測定するという課題を克服します。これらのグループの違いは、あるグループ（**テストグループ**）はキャンペーンと接触し、またあるグループ（**コントロールグループ**）はキャンペーンと接触していないという点だけです。

<Anchor target="_blank" href="/marketers/ja/docs/run-an-incrementality-for-remarketing-experiment">インクリメンタリティ用のテストの作成と実行についての詳細はこちら</Anchor>

<div id="calculation-methodology" />

## 計算方法

以下のセクションでは、Incrementalityダッシュボードでレポートされた数値の背後にある計算について説明します。

<div id="lift" />

<Accordion title="リフト">

AppsFlyerのインクリメンタリティでは、リフトを算出するために2つの方法を採用しています：

* Intent-to-treat（ITT解析）
* Reach-based（リーチベース）

キャンペーンのパフォーマンスを評価する目的では、実際にユーザーが広告に接触したかどうかの<strong>「リーチベース」の手法が望ましい</strong>のですが、その計算には、すべてのアドネットワークが提供しているわけではないデータポイントを測定する必要があります。 それらのネットワークについては、代わりにintent-to-treat（ITT解析）の手法が用いられます。

<div id="note" />

> 📘 **注意**
>
> 2021年12月16日以前は、intent-to-treat（ITT解析）法のみで純増を算出していました。 ただし、それ以前のデータについても、リーチベースのリフトを使用するように更新されています。 そのため、過去のテストを見直して、新しいメソッドで照らし合わせて結果を分析することができます。

<div id="itt-based-lift" />

#### ITTベースのリフト

ITT（intent-to-treat） 検証のメソッドは、医学の世界にその基礎があります。 ITTを使用して、研究者は母集団を治療を行わないコントロールグループと、研究者が治療を行う意図を持つテストグループにランダムに分割します。 研究者は、グループの結果を比較することによって、与えられた治療の有効性を測定します。 テストグループのメンバーが*実際に*治療を受けたかどうかは考慮されません。

同様に、リマーケティングでは、増分率の指標でキャンペーンの有効性を測定します。 このメソッドでは、テストグループのユーザーが *実際に* キャンペーンに接触した（治療を受けた）かどうかは加味されません ー なぜなら、純増値を計算する際に関係するのはインテンション（意図）だからです。 つまり、テストグループのメンバー全員が実際にキャンペーンに接触したものとして結果が算出されます。

**どんな時に使うのですか？**

AppsFlyerのIncrementalityは、SRN媒体にITTベースのリフト計算を採用しています。

ITTは、AppsFlyerの文脈ではリフトを測定するための好ましい方法ではありませんが、科学的に適切な実験方法であり、リーチベースの計算が不可能な場合に有効な結果を提供します。

**結果の解釈**

テストグループのメンバー全員が実際にキャンペーンに接触したという前提があるため、コンバージョン率が低くなり、その結果、リフト量も少なくなることがよくあります。

<div id="reach-based-lift" />

#### リーチベースのリフト

その名の通り、リーチベースのリフト計算は、テストグループのメンバーがコンバージョンする前に、*実際に* 広告に接触したかどうかを考慮します。 リーチベースのリフト計算は、追加データを必要とすることに加え、統計的に有効であるためには、コントロールグループに一定の数学的調整を必要とするという点で、より複雑なものとなります。 これらの調整は累積的に、"counterfactual" （反事実的条件文）コントロールグループの作成として知られています。

**どんな時に使うのですか？**

AppsFlyerのIncrementalityでは、非SRN媒体（計測リンク使用媒体）に対してリーチベースのリフト計算を行います。

リフトを計算する上で好ましい方法ですが、リーチベースの計算では、アドネットワークが以下のデータをAppsFlyerにレポートする必要があります：

* インプレッションデータ
* キャンペーンID（計測リンク経由）

このデータがレポートされていない場合、インクリメンタル測定は利用できません（インクリメンタルダッシュボードでは結果がN/Aと表示されます）。

**結果の解釈**

リーチベースのリフト計算は、キャンペーンによって実際にリーチしたテストグループのメンバーのみを考慮するため、リーチベースの純増によって測定されたネットワークは通常、結果が増幅されます（ポジティブリフトはより高くなり、ネガティブリフトはより低くなります）。

<div id="best-practices" />

#### ベストプラクティス

2つの異なるリフト計算方法によって結果が大きく異なることがあるため、解釈をより有意義なものにするために、以下のベストプラクティスを推奨します。

* 検証を行う際には、コントロールグループと1つ以上の同じタイプのネットワーク、どちらかだけに分かれたオーディエンスを選択します。
  * リーチベース計算の非SRN媒体（計測リンク使用媒体）、または
  * ITTベースのSRN
* 最初の検証では、オーディエンスを1つのネットワークとコントロールグループにのみ分割して使用することを検討してください。これにより、異なるリフト計算を行った2つ以上のネットワーク間で比較することが少なくなります。

</Accordion>

<div id="statistical-significance" />

<Accordion title="統計的有意性">

Incrementality検証の有効性を評価する場合、健全な科学的方法論では、 **統計的有意性**（リフト結果がランダムな事象や偶然によるものではないという信頼度のレベル）を考慮することが必要です。

Incrementalityダッシュボードでは、各メディアソースにおいて、有意性がパーセンテージで表示されます。

* パーセントは、キャンペーンの結果が、同じような状況でもう一度検証を行った場合に、同じ結果が繰り返される可能性を示しています。
* 統計的有意性が60％以下と判断された場合、ダッシュボードにはパーセンテージではなく、**結果：信頼性のないデータ**として表示されます。
* 有意性は、オーディエンスのサイズ、検証期間、キャンペーンのパフォーマンスに影響されます。

</Accordion>

<div id="scaled-control-group" />

<Accordion title="スケールコントロールグループ">

[テストグループレベルの指標](/docs/incrementality-for-remarketing-overview#::2c5f08ec)（[ユーザー単位の指標](/docs/incrementality-for-remarketing-overview#::6143ff4f)とは対照的）については、**スケールコントロールグループ**に基づいてリフトが計算されます。 [つまり、各メディアソースのコントロールグループの大きさに合わせて、コントロールグループの大きさを調整します。](/docs/incrementality-for-remarketing-overview#::2c5f08ec)

<div id="example" />

> 📄 **例**
>
> 次のようなシナリオを想定してください：
>
> * ネットワークAのテストグループサイズ＝100名
> * コントロールグループサイズ＝90名
> * 検証結果：
>   * ネットワークAは40件のコンバージョンが発生
>   * コントロールグループでは20件のコンバージョンが発生
> * 合計コンバージョン数は、コントロールグループの規模を100名と想定し、調整します：
>   * 想定ユーザー数 ー 実際のユーザー数 =100 - 90=11%
>      実際のユーザー数                      90
>   * 実際の純増コンバージョン数 ＋ 11％ ＝ 20 × 1.11 ＝ 22
>
> リフトは、コントロールグループの規模を100名、コンバージョンの増加を22名として計算します。

</Accordion>

<div id="incrementality-dashboard" />

## Incrementality管理画面

[![New_Incrementality_Guide_image.jpg](https://files.readme.io/a14fa7ae346177dbdd7de5fde4917d7300cbc148097a2239e29460a67eacd9a6-15317247527569.jpg)](https://files.readme.io/a14fa7ae346177dbdd7de5fde4917d7300cbc148097a2239e29460a67eacd9a6-15317247527569.jpg)

<div id="accessing-the-dashboard" />

<Accordion title="ダッシュボードにアクセスする">

インクリメンタリティはプレミアム機能です。利用をご希望の場合は、カスタマーサクセスマネージャーまたは [hello@appsflyer.com](mailto:hello@appsflyer.com) へお問い合わせください。 トライアルもしくはご契約開始後、Incrementalityダッシュボードにアクセスできるようになります。

**インクリメンタリティダッシュボードへアクセス：**

1. AppsFlyer管理画面 左メニュー **最適化** > **Incrementality: 純増検証** へ移動します。
2. 検証リストから、ダッシュボードを表示させたい検証をクリックします。

</Accordion>

<div id="a-tour-of-the-dashboard" />

<Accordion title="ダッシュボードツアー">

<Table>
  <thead>
    <tr>
      <th>

      </th>
      <th>
        要素
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ![A.png](https://files.readme.io/66b5bb0c4ea35f232f65dbc8dcbdfd6a91c12cf94915b19d33dae44834127058-31237653543313.png)
      </td>
      <td>
        フィルターバー
      </td>
      <td>
        **計測：** ダッシュボードに表示する指標を選択します：

        * **コンバージョン** **コンバージョン (UU)**  - 選択したイベントを実行したユニークユーザー数
        * **収益**  - 選択されたイベントのユーザーがコンバージョンしたことにより発生した収益
        * **イベント**  - 選択したイベントのうち、コンバージョンするユーザーによって実行された回数

        計測フィルタで選択すると、ダッシュボード全体に表示される計測基準が決定されます：

        **イベント：** データを表示したいアプリ内イベントを選択します

        **メディアソース：** 検証でテストしたメディアソースによって表示するデータをフィルターします

        **日付範囲：** 選択した日付範囲に従ってオーディエンスの純増分析をフィルターします。
      </td>
    </tr>
    <tr>
      <td>
        ![B.png](https://files.readme.io/f63914d3fefb55b627559c6e4c7d7cdef89239c0376a14c25c713a0a76dbad1b-31237653544337.png)
      </td>
      <td>
        <span id="::3b361a96"></span>検証結果の要約
      </td>
      <td>
        検証結果全体を一目でわかるように要約でまとめています。
      </td>
    </tr>
    <tr>
      <td>
        ![C.png](https://files.readme.io/b428e77b299e10fe0701b7850cea1da8942905ad38d7b30c32f99f0240b22a63-5397303804945.png)
      </td>
      <td>
        <span id="::6ba593ae"></span>有意性タイル
      </td>
      <td>
        ダッシュボードに表示されている結果の[統計的有意性](/docs/incrementality-for-remarketing-overview#statistical-significance)を表示します。
      </td>
    </tr>
    <tr>
      <td>
        ![D.png](https://files.readme.io/9d9abd09fc45ec65fc52cbc1c8011117b555629d243444d076a392b4245effdd-5397362181265.png)
      </td>
      <td>
        <span id="::4c3ffd21"></span>ヘッドライン指標タイル
      </td>
      <td>
        表示される指標は、以下のように 計測フィルター での選択によって制御されます。

        | 計測フィルターの選択 | 表示されるヘッドライン指標 |
        | --- | --- |
        | <span id="conversionsevents"></span>コンバージョン／イベント | CPiA（Cost per Incremental Action：純増アクションあたりのコスト）<br /><br />* キャンペーンコストに基づく、純増イベント毎の平均コスト |
        | <span id="revenue"></span>収益 | 広告費用対効果（iROAS）増加分<br /><br />* キャンペーンに費やした金額に対して発生した増収分の比率 |

        **注：** ヘッドラインタイルに表示される指標の計算には、コストデータが必要です。 したがって、これらの指標は **ROI360**をご契約のお客様のみが使用できます。 必要なコストおよび/または収益のデータが、この理由またはその他の理由で入手できない場合、関連する指標は **N/A** と表示されます。
      </td>
    </tr>
    <tr>
      <td>
        ![E.png](https://files.readme.io/28563cf0057cdd6ccfd8ebb5b727ae80bef81ec66697f8e11eadc698f72e7acd-5397355189777.png)
      </td>
      <td>
        <span id="::c0b74d1b"></span>ターゲットサイズとリーチタイル
      </td>
      <td>
        **ターゲットサイズ：** 検証の日付範囲内に初めてオーディエンスに加えられた、メディアソースごとのユニークユーザー数

        * 円グラフの内側のリング（濃い色）にも表示されます。

        **リーチ：** 該当メディアソースのキャンペーンから、実際に広告に接触したターゲットユーザーの%割合

        * 円グラフの外側のリング（明るい色 ）にも表示されます。
      </td>
    </tr>
    <tr>
      <td>
        ![F.png](https://files.readme.io/99f2fb8f45215ddebf9582f215e3647bc35f5a812015733b3f6e3cb8d2784bd7-5397365201809.png)
      </td>
      <td>
        <span id="::2c5f08ec"></span>テストグループレベルのリフトタイル
      </td>
      <td>
        **テストグループ**の**合計**純増指標とリフトを表示します（メディアソース別）：

        * 合計純増リフトは、 [スケールしたコントロールグループ](/docs/incrementality-for-remarketing-overview#scaled-control-group) を使用して計算されています。
        * 表示される指標は、以下のように計測フィルターでの選択によって制御されます。

        | 計測フィルターの選択 | 表示される指標 |
        | --- | --- |
        | <span id="conversions"></span>コンバージョン | コンバージョンの合計純増量 |
        | <span id="events"></span>イベント | 合計純増イベント数 |
        | <span id="revenue::3f000a8e"></span>収益 | 合計純増収益額 |
      </td>
    </tr>
    <tr>
      <td>
        ![G.png](https://files.readme.io/7301cda39a8a6bcd08d199097ff9b11d496c5f01ab34422364a4e467a752338a-5397303963409.png)
      </td>
      <td>
        <span id="::6143ff4f"></span>ユーザーごとのリフトタイル
      </td>
      <td>
        **ユーザー毎**の純増指標とリフトを表示します（メディアソース別）：

        * ユーザー毎の純増リフトは、テストグループとコントロールグループの実際のユーザー数を用いて計算されます。
        * 表示される指標は、以下のように計測フィルターでの選択によって制御されます。

        | 計測フィルターの選択 | 表示される指標 |
        | --- | --- |
        | <span id="conversions::b51393dc"></span>コンバージョン | コンバージョン率の純増 |
        | <span id="events::3b4fa416"></span>イベント | ユーザーごとのイベント純増 |
        | <span id="revenue::b432caf"></span>収益 | ユーザー1人当たりの純増収益 |
      </td>
    </tr>
    <tr>
      <td>
        ![H.png](https://files.readme.io/36085f38ba02d718acc766af3865073bf13960b2a1c755bd48302ab5415ff89a-5397355274513.png)
      </td>
      <td>
        <span id="::a6a95657"></span>トレンドチャート
      </td>
      <td>
        選択された **ユーザー毎** の純増指標 / リフトを、検証の日付範囲に渡って表示します。

        * 表示される指標は、計測フィルターの選択により制御され、**ユーザー毎のリフトタイル**で表示される指標と同じデータです。
        * 点線（チャート表示）は、レポートされた日付のデータの一部を示します（将来のイベントがまだデータに影響を与える可能性があることを意味します）。
        * **トレンドチャート表示コントロール** を使用して、さまざまな表示およびダウンロードオプションを選択します（詳細については後述します）。
      </td>
    </tr>
    <tr>
      <td><span id="::64e4f3f6"></span>
        <Image alt="I.jpg" src="https://files.readme.io/19ab5c305d3eb2609031a1a88f6f4069015b6eefe9ef4f1501613f62e5024739-15317326904465.jpg" width="29px" />
      </td>
      <td>
        トレンドチャート表示
      </td>
      <td>
        表示コントロールを使用して、 **トレンドチャート** の表示とダウンロードのオプションを選択します：

        * 累積値または日毎の値
        * チャートまたはテーブル形式

        **CSV出力**ボタンから、データをCSV形式のレポートとしてダウンロードできます。

        * ダウンロードされるデータは、表示タイプで選択したものです： **累積**または**当日**

        **レポート内の用語の説明**

        | 用語 | 説明 |
        | --- | --- |
        | ロー（生）計測 | コンバージョン / イベント / 収益の合計 インプレッションに関係なく、テストグループによって生成されます（分割設定によって各ユーザーに割り当てられたネットワークのみに基づきます）。 |
        | リーチ計測 | テストグループによって生成されたコンバージョン数、イベント数、収益数（基になるイベントをトリガーする前に選択したキャンペーンのインプレッションが発生そたユーザーのみ）。 |
        | 未リーチ計測 | ロー計測からリーチ計測ユーザーのコンバージョンデータを差し引いたデータ これは、基になるイベントをトリガーする前にインプレッションが発生しなかった（広告接触しなかった）テストグループのユーザーによって生成されたコンバージョン、イベント、収益の合計量を表します。 |
        | ユーザー毎の計測 | テストグループのリーチ / 生計測（選択したネットワークがリーチをサポートしているかどうかに基づく）を、テストグループのグループサイズ/リーチで割った数値。 |
        | コントロールグループのロー計測 | コントロールグループによって生成されたコンバージョン / イベント / 収益の合計金額。 |
        | コントロールグループのリーチ計測 | テストグループのリーチに合わせて調整された、コントロールグループグループによって生成されたコンバージョン数、イベント数、収益数（この値は反事実であり、同一条件での比較手段として機能します）。 |
        | コントロールグループの未リーチ計測 | ロー計測から反事実にリーチ計測を差し引いたもの。 これは、コントロールグループのユーザーが生成したコンバージョン/イベント/収益の合計量を示します。 |
        | コントロールグループのユーザー毎の計測 | コントロールグループの反事実 リーチ / 生の測定値（選択したネットワークがリーチをサポートしているかどうかによって異なる）を、コントロールグループのグループサイズ / 反事実リーチで割った数値。 |
        | 純増計測の合計 | テストグループの広告接触から、スケールコントロールグループを差し引いたもの。 |
        | ユーザーごとの純増計測 | ユーザー毎の計測からコントロールグループのユーザー毎の計測を引いたもの。 |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-reports" />

## ローデータレポート

Incrementalityローデータレポートを使用して、ユーザーのリマーケティングキャンペーンとのインタラクションを分析しましょう。

* **コンテンツ：** Incrementality検証に参加したユーザーレベルのローデータ
* **利用方法：**
  * <Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">Data Locker</Anchor>経由
  * データ更新頻度：UTC時間で毎日19:00 - 23:00（日本時間：毎日 4:00 - 8:00）

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012600697">Incrementalityローデータサンプルファイル</Anchor>

<div id="available-reports" />

<Accordion title="利用可能なレポート">

<table><thead><tr><th>カテゴリ</th><th>レポート名 </th><th>Data Lockerフォルダ</th></tr></thead><tbody><tr><td>First-seen</td><td>First-seen users</td><td>incrementality_first_seen_users</td></tr><tr><td rowspan="3">In-app events</td><td>Organic in-app events</td><td>incrementality_organic_inapps</td></tr><tr><td>In-app events non-organic</td><td>incrementality_inapps</td></tr><tr><td>In-app events re-attributions</td><td>incrementality_inapps_reattr</td></tr><tr><td rowspan="3"><p>Sessions</p></td><td>Organic sessions</td><td>incrementality_organic_sessions</td></tr><tr><td>Sessions non-organic</td><td>incrementality_sessions</td></tr><tr><td>Sessions re-attributions</td><td>incrementality_sessions_reattr</td></tr><tr><td>Uninstalls</td><td>Uninstalls<br/>（現在は未入力） </td><td>incrementality_uninstalls</td></tr></tbody></table>

</Accordion>

<div id="report-logic" />

<Accordion title="レポート仕様">

レポート構成の基礎となるロジックは以下の通りです：

* **テストに参加しているユーザー：First-seenレポート**
  * オーディエンス機能にて、テストに含めるユーザーを特徴付けるルールが設定されます。
  * ユーザーがルールと一致していると識別されると、そのイベントは *first\_seen* レポートに記録されます。
    * ユーザーがテスト、または *is\_control\_group*  項目で示されるコントロールグループのいずれかにランダムに割り当てられます。
    * テストグループ内のユーザーは、リターゲティング用にメディアソース（*pid\_destination*）に割り当てられます。
* **アプリ内でのユーザーエンゲージメント：** 検証中のアプリとのユーザーエンゲージメントは、コンテキスト固有のレポートに記録されます：
  * **エンゲージメントタイプ：** セッションまたはアプリ内イベント
  * ユーザーが First-seen の**ユーザー属性ステータス** ：オーガニック、非オーガニック、リアトリビューション。例えば、過去にユーザーがアプリをインストールし、オーガニックと計測されました。そのため、検証中は、アトリビューションステータスがオーガニックになります。
* **アンインストール：** 検証中にアプリをアンインストールしたユーザー。アンインストール計測が有効になっている必要があります。

</Accordion>

<div id="data-characteristics-and-fields" />

<Accordion title="データの特性と項目">

使用できる項目は、次に示すように、レポートの種類によって異なります：

<div id="fields-unique-to-incrementality-per-report-type" />

#### Incrementality固有のデータ項目（レポートタイプ別）

| 項目 | 説明 | First seen | In-app events | Sessions | Uninstalls |
| --- | --- | --- | --- | --- | --- |
| <span id="is_control_group"></span>is\_control\_group | trueの場合、ユーザーはコントロールグループに属します | Y | Y | Y | Y |
| <span id="pid_destination"></span>pid\_destination | ユーザーが割り当てられたメディアソース | Y | Y | Y | Y |
| <span id="audience_id"></span>audience\_id | 一意の識別子 | Y | Y | Y | Y |
| <span id="joined_audience_date"></span>joined\_audience\_date | ユーザーがオーディエンスに最初に参加した日 | Y | Y | Y | Y |
| <span id="audience_name"></span>audience\_name | オーディエンス名（一意ではない） | Y | Y | Y | Y |
| <span id="tm"></span>tm | 一日の時間 |  | Y | Y | Y |
| <span id="timestamp"></span>timestamp | イベントのタイムスタンプ YYYY-MM-DD HH:MM |  | Y | Y |  |
| <span id="app_ids"></span>app\_ids | オーディエンスルールに関連するアプリID | Y |  |  |  |

<div id="other-incrementality-report-fields-per-report-type" />

#### その他のIncrementalityレポート項目（レポートタイプごと）

<table><thead><tr><th>項目</th><th>表示名\*</th><th>First seen</th><th>In-app events</th><th>Sessions</th><th>Uninstalls</th></tr></thead><tbody><tr><td><span id="advertising_id"></span>advertising_id</td><td>Advertising ID (GAID)</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="android_id"></span>android_id</td><td>Android ID</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="app_id"></span>app_id</td><td>App ID</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="app_name"></span>app_name</td><td>App name</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="app_version"></span>app_version</td><td>App version</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="appsflyer_id"></span>appsflyer_id</td><td>Appsflyer ID</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="revenue_alt"></span>revenue_alt</td><td>App-specific currency</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="bundle_id"></span>bundle_id</td><td>Bundle ID</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="country"></span>country</td><td>Country code</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="currency"></span>currency</td><td>Currency code</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="customer_user_id"></span>customer_user_id</td><td>Customer user ID</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="brand"></span>brand</td><td>Device brand</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="device_category"></span>device_category</td><td>Device category</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="model"></span>model</td><td>Device model</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="device_model"></span>device_model</td><td>Device model</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="device_type"></span>device_type</td><td>Device type</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="event_name"></span>event_name</td><td>Event name</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="event_revenue"></span>event_revenue</td><td>Event revenue</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="event_revenue_currency"></span>event_revenue_currency</td><td>Event revenue currency</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="event_revenue_u_s_d"></span>event_revenue_u_s_d</td><td>Event revenue USD</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="event_time"></span>event_time</td><td>Event time</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="event_value"></span>event_value</td><td>Event value</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="idfa"></span>idfa</td><td>IDFA</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="idfv"></span>idfv</td><td>IDFV</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="imei"></span>imei</td><td>IMEI</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="is_purchase_validated"></span>is_purchase_validated</td><td>Is receipt validated</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="os_version"></span>os_version</td><td>OS version</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="platform"></span>platform</td><td>Platform</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="sdk_version"></span>sdk_version</td><td>SDK version</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td colspan="6"><span id="-according-to-raw-data-specification"></span>\* <a href="./raw-data-field-dictionary#data-fields-dictionary" target="_blank">ローデータの仕様に基づく</a> </td></tr></tbody></table>

</Accordion>

<div id="incrementality-specifications-and-limitations" />

## Incrementalityの仕様と制限

| 特性 | 備考 |
| --- | --- |
| アカウントユーザーのアクセス | アカウント権限に依存 |
| アドネットワークアクセス | 利用不可 |
| 代理店アクセス | 利用不可現状、インクリメンタリティは広告主アカウントでのみ利用可能です。 |
| 代理店の運用媒体の開示設定 | 代理店運用の媒体開示を有効（オン）に設定している代理店が実施したキャンペーンを測定できます。 |
| 通貨 | USD（米ドル） |
| データ更新頻度 | 管理画面：毎日 UTC 18:00に前日データを更新（日本時間：毎日朝4時に前々日のデータを更新）<br /><br />Data Locker（ローデータ）：毎日 UTC 19:00 - 23:00に前日分を更新（日本時間：毎日 4:00 - 8:00 に前々日のデータを更新） |
| 過去データ | N/A |
| 非オーガニックデータ | はい |
| オーガニックデータ | はい |
| S2Sイベント | Incrementalityで計測されるには、<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile#サーバー間イベントapi-for-モバイル">S2Sイベント</Anchor>のペイロードに広告IDが含まれている必要があります（iOSの場合はIDFA、Android の場合はGAID）。 |
| タイムゾーン | UTC |

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/audiences-guide">Audiencesガイド</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/blog/tips-strategy/incrementality-testing-for-marketers/">マーケターのためのインクリメンタティ検証ブログ</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/blog/topic/incrementality/">Incrementalityブログ</Anchor>

<div data-zendesk-anchors="what-is-incrementality=%E3%82%A4%E3%83%B3%E3%82%AF%E3%83%AA%E3%83%A1%E3%83%B3%E3%82%BF%E3%83%AA%E3%83%86%E3%82%A3%E3%81%A8%E3%81%AF h_01HB86QVQ0TM91XB8VSZYD42ZA=%E3%82%A4%E3%83%B3%E3%82%AF%E3%83%AA%E3%83%A1%E3%83%B3%E3%82%BF%E3%83%AA%E3%83%86%E3%82%A3%E3%81%A8%E3%81%AF incrementality-experiments=%E3%82%A4%E3%83%B3%E3%82%AF%E3%83%AA%E3%83%A1%E3%83%B3%E3%82%BF%E3%83%AA%E3%83%86%E3%82%A3%E3%83%86%E3%82%B9%E3%83%88 h_01HB86QVQ0HR436K24V3SQXVXT=%E3%82%A4%E3%83%B3%E3%82%AF%E3%83%AA%E3%83%A1%E3%83%B3%E3%82%BF%E3%83%AA%E3%83%86%E3%82%A3%E3%83%86%E3%82%B9%E3%83%88 calculation-methodology=%E8%A8%88%E7%AE%97%E6%96%B9%E6%B3%95 h_01HB86QVQ0FYTCEVATBEC91ZC1=%E8%A8%88%E7%AE%97%E6%96%B9%E6%B3%95 h_01HB86QVQ0SMJFEPJ8048NBQTN=lift h_01HB86QVQ1MREDW50YTKSY2KZJ=%E6%B3%A8%E6%84%8F ittbased-lift=itt%E3%83%99%E3%83%BC%E3%82%B9%E3%81%AE%E3%83%AA%E3%83%95%E3%83%88 h_01HB86QVQ1NGWZM604A45K03TA=itt%E3%83%99%E3%83%BC%E3%82%B9%E3%81%AE%E3%83%AA%E3%83%95%E3%83%88 reachbased-lift=%E3%83%AA%E3%83%BC%E3%83%81%E3%83%99%E3%83%BC%E3%82%B9%E3%81%AE%E3%83%AA%E3%83%95%E3%83%88 h_01HB86QVQ1N67SFWKRG1BKZE5A=%E3%83%AA%E3%83%BC%E3%83%81%E3%83%99%E3%83%BC%E3%82%B9%E3%81%AE%E3%83%AA%E3%83%95%E3%83%88 best-practices=%E3%83%99%E3%82%B9%E3%83%88%E3%83%97%E3%83%A9%E3%82%AF%E3%83%86%E3%82%A3%E3%82%B9 h_01HB86QVQ1RDMFT5FH53BYDNSV=%E3%83%99%E3%82%B9%E3%83%88%E3%83%97%E3%83%A9%E3%82%AF%E3%83%86%E3%82%A3%E3%82%B9 h_01HB86QVQ1K2SPBXTG67B5PV33=statistical-significance h_01HB86QVQ1CAZ0ZDJDKPC1B36S=scaled-control-group h_01HB86QVQ16EZVAATG4DPTDVTQ=%E4%BE%8B incrementality-dashboard=incrementality%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2 h_01HB86QVQ10C1YHC8HZ9Z8T089=incrementality%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2 h_01HB86QVQ1ECVT0BT4GYC81DH4=accessing-the-dashboard h_01HB86QVQ1JN8SPHXJGHT4NFSB=a-tour-of-the-dashboard raw-data-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HB86QVQ27FXXBRSH2V8ZK78X=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HB86QVQ24932F7CHY666730J=available-reports h_01HB86QVQ2YXRVFKEE20E787BK=report-logic h_01HB86QVQ2VK6TX3CSA4S6QSKZ=data-characteristics-and-fields fields-unique-to-incrementality-per-report-type=incrementality%E5%9B%BA%E6%9C%89%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E9%A0%85%E7%9B%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%82%BF%E3%82%A4%E3%83%97%E5%88%A5 h_01HB86QVQ2CAN02B8GWEZTTTVW=incrementality%E5%9B%BA%E6%9C%89%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E9%A0%85%E7%9B%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%82%BF%E3%82%A4%E3%83%97%E5%88%A5 other-incrementality-report-fields-per-report-type=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AEincrementality%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E9%A0%85%E7%9B%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%82%BF%E3%82%A4%E3%83%97%E3%81%94%E3%81%A8 h_01HB86QVQ221QK6WYRZQ3MJDSY=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AEincrementality%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E9%A0%85%E7%9B%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%82%BF%E3%82%A4%E3%83%97%E3%81%94%E3%81%A8 incrementality-specifications-and-limitations=incrementality%E3%81%AE%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90 h_01HB86QVQ2W6X5Z485WM371GGE=incrementality%E3%81%AE%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90 h_01HE7RBMSE1RHVSJC7B7FZG8SJ=%E5%8F%82%E7%85%A7" />
