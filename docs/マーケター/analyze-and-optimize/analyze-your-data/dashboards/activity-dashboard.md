---
title: アクティビティ管理画面
metadata:
  keywords:
    - activity report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-01-12T15:50:15Z'
  edited_at: '2026-10-14T09:30:38Z'
  id: 207602503
  locale: ja
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ja/articles/207602503
---
> **概要：** 特定の期間内に発生したアプリのアクティビティ、エンゲージメント、アプリの指標を確認できます。当日の指標はリアルタイムで更新されます。

![ActivityDB.png](https://files.readme.io/8150eafc018c83ae2b1030702129bda12419dfac60eb8664187c2acd66136df3-4420170646289.png)

## アクティビティ管理画面

* オーガニックと非オーガニックのトラフィックが含まれます。
* 日付の期間はイベントの発生日を指定しており、<Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTVベース</Anchor>ではありません。
* データ更新頻度：
  * **当日**：<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">随時</Anchor>。例：DAU、セッション、収益
  * **平均：** 毎日。例：MAU、平均 DAU、平均 MAU
* 国フィルタは、インストール時のユーザーロケーションに関連します。

> 👍 **ヒント**
>
> アクティビティダッシュボードについて詳しく知りたいですか？簡潔に重要なポイントを押さえた<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7802/play/18621/the-activity-dashboard">AppsFlyerラーニングポータルコース</Anchor>をご活用ください。

## 管理画面の機能とレイアウト

<div id="metric-definitions" />

<Accordion title="指標の定義">

<Table>
  <thead>
    <tr>
      <th>
        指標
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="dau"></span>
        DAU
      </td>
      <td>
        * 1日のアクティブユーザー数：1日に1回以上アプリを開いたユニークユーザーの数。
        * DAUはセッションに基づいて算出されます。
        * <Anchor target="_blank" href="/marketers/ja/docs/unique-users">詳細：ユニークユーザーに関して</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="average-dau"></span>
        平均DAU
      </td>
      <td>
        選択した日付期間内における一日当たりのアクティブユーザーの平均値です。

        例：平均DAUの計算

        > 📄
        >
        > |  | 日曜日 | 月曜日 | 火曜日 |
        > | --- | --- | --- | --- |
        > | <span id="daily-active-unique-users"></span>1日のアクティブユニークユーザー数 | 10 | 12 | 8 |
        >
        >
        >
        > **平均DAU** = (10+12+8)/3= 10.
      </td>
    </tr>
    <tr>
      <td><span id="mau"></span>
        MAU
      </td>
      <td>
        マンスリーアクティブユーザー：

        * **詳細：** アプリを過去31日間に少なくとも一回起動したユニークユーザー（一回のみカウント）の数。
        * **高レベル：** アプリをカレンダー月の間に少なくとも一回起動したユニークユーザー（一回のみカウント）の数。
      </td>
    </tr>
    <tr>
      <td><span id="daumau-rate"></span>
        DAU÷MAU率
      </td>
      <td>
        * この指標は再訪問ユーザーの割合を示しています。DAU÷MAU率が50%の場合、平均的なユーザーは過去31日間に15日アプリを起動したことを意味します。
        * DAU÷MAU 率は、ユーザーの定着度を示す指標であり、ユーザーリテンションを把握することができます。
      </td>
    </tr>
    <tr>
      <td><span id="revenue"></span>
        収益
      </td>
      <td>
        選択した期間に生成された収益額。収益はアプリ内購入（レポートされている場合）と広告収益で構成されています。
      </td>
    </tr>
    <tr>
      <td><span id="arpdau"></span>
        ARPDAU
      </td>
      <td>
        デイリーアクティブユーザー当たりの平均収益額。  
        数式：（[n] 日の収益額 ÷ [n] 日のDAU）の合計） ÷ 日数の合計

        > 📄 **例：ARPDAUの計算**
        >
        > | 日 | その日の収益額 ($) | DAU | デイリーユーザーの平均収益額 ($) |
        > | --- | --- | --- | --- |
        > | <span id="day-1"></span>1日目 | 10 | 5 | 2 |
        > | <span id="day-2"></span>2日目 | 16 | 4 | 4 |
        > | <span id="day-3"></span>3日目 | 30 | 5 | 6 |
        > |  |  | 合計： | 12 |
        > |  <span id="::4eb0b020"></span>|  | 日数 | 3 |
        > |  <span id="::b35cc38c"></span>|  | **ARPDAU** | 4 |
      </td>
    </tr>
    <tr>
      <td><span id="sessions"></span>
        セッション
      </td>
      <td>
        選択された期間のセッション（アプリで計測されている場合）
      </td>
    </tr>
    <tr>
      <td><span id="installs"></span>
        インストール
      </td>
      <td>
        指定期間内のインストール数
      </td>
    </tr>
    <tr>
      <td><span id="average-ecpi"></span>
        平均eCPI
      </td>
      <td>
        インストールごとの平均コスト。注：インストールしたユーザーはユーザー獲得によるインストールであり、コストは統一されています（ユーザー獲得とリターゲティング）。
      </td>
    </tr>
    <tr>
      <td><span id="conversion-rate"></span>
        コンバージョン率
      </td>
      <td>
        クリックからのインストール転換率。**注意：** インストールしたユーザーはユーザー獲得によるインストールであり、コストは統一されています（ユーザー獲得とリターゲティング）。
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="detailed-tab" />

<Accordion title="トレンドタブ">

[トレンド] タブは、主要な指標、アクティブユーザートレンド、アクティビティ概要のセクションに分かれています。 

<table><tbody><tr><td colspan="2"><h4><strong><span id="headline-metrics"></span>メインの指標</strong></h4></td></tr><tr><td> </td><td><img alt="ActivityHeadLines_us-en__1_.png" src="https://files.readme.io/a4f1a5316eeacf0f635bbeadf52d490dd0276bb8a1fe9c0e32db7008d11d044b-360012584838.png"/></td></tr><tr><td> </td><td> <strong>平均アクティブユーザー</strong><ul><li>平均DAU：選択した期間内における一日当たりのアクティブユーザーの平均値です。</li><li>平均MAU：選択した期間内における一月当たりのアクティブユーザーの平均値です。これは、選択した期間内の各日がそれぞれ過去31日間のデータを振り返る、移動平均として計算されます。注：特定の月の MAU 値（例：3月）を表示するには、日付範囲をその月の初日（例：4月1日）に設定し、平均 MAU 値を確認してください。</li></ul></td></tr><tr><td> </td><td> <strong>インストール総数：</strong>オーガニックと非オーガニックインストールに分けられたインストール数</td></tr><tr><td> </td><td> <strong>合計セッション数</strong>：オーガニックと非オーガニックユーザーに分けられたセッション数</td></tr><tr><td> </td><td> <strong>合計収益</strong>：オーガニックと非オーガニックユーザーに分けられた収益額</td></tr><tr><td colspan="2"><h4> <br/><strong><span id="activity-trends"></span>アクティビティトレンド</strong><br/> </h4></td></tr><tr><td> </td><td><p><strong>比較を伴うトレンドグラフ</strong></p><p><img alt="TrendLinWithComp_us-en.png" src="https://files.readme.io/b9edb3e409dc13bc72aebdccdc499fa2dcd9abf4549fb0170bf0cdc7036eee15-360012507997.png"/></p><ul><li>トレンドグラフはKPIまたはアプリ内イベントに関する計測データを表示します。</li><li>前日、前週、前月、前期、前年単位で、<strong>過去比較</strong>を有効にすると、オプションの比較データが確認できます。 </li><li>例えば前月を選択した場合、チャート内では、比較として先月の同日の値が表示されます。 </li></ul><p>利用可能なKPIは次のとおりです：</p><ul><li><span>DAU</span></li><li><span>MAU</span></li><li><span>収益</span></li><li><span>ARPDAU</span></li><li><span>セッション</span></li><li><span>DAU÷MAU率</span></li></ul><p><span>利用可能なアプリ内イベント測定は次のとおりです。</span></p><ul><li><span>カウント</span></li><li><span>ユニークユーザー数</span></li><li><span>収益</span></li></ul></td></tr><tr><td colspan="2"><h4> <br/><strong><span id="activity-summary-table"></span>アクティビティ概要の表</strong> </h4></td></tr><tr><td> </td><td><p>アクティビティ概要の表：</p><ul><li>インプレッション、クリック、インストールなどに関するデータを含む最大50のメディアソースを表示します。（すべてのデータを取得するには、<a href="./master-api-user-acquisition-metrics-via-api" target="_blank">Master API</a> または <a href="./pivot-table-user-metrics" target="_blank">Pivot</a>を使用してください。） </li><li>セッション数で並べ替えられて表示されます。 </li><li>キャンペーンレベルまでドリルダウンできます（これ以下の階層で確認することはできません）。</li><li>新規のDAUの数と既存のユーザーの数 (DAUからインストール数を引いたもの) を確認するのに適した方法です。</li></ul><p><span>サマリーテーブルを使用する方法：</span></p><ul><li><span>[フィルタ] と [グループ化] 機能を使ってデータを絞り込むことができます。</span></li><li><span>表の列は列のヘッダーをクリックすることで並び替えられます。</span></li><li> <strong>アプリ内イベント</strong>別に絞り込むことで、特定のアプリ内イベントに関するデータのみを表示できます。</li><li>表示タイプの切り替え：<ul><li> <strong>サマリー：</strong> 選択されたすべてのアプリ内イベントの合計</li><li> アプリ<strong>内イベント：</strong> アプリ内イベント別の内訳</li></ul></li></ul></td></tr></tbody></table>

</Accordion>

<div id="highlevel-tab-previous-twelvemonths" />

<Accordion title="月間データ タブ：過去12か月間">

![ActivityHiLevel.png](https://files.readme.io/42636f5b13dca3a2209ea295c02e784175dfc92a2523c861220b87baed859541-4420194466065.png)

このタブにはアプリのアクティビティ成果に関する12か月間の履歴概要が表示され、次のグラフを含みます：

* アクティブユーザーと収益
* 月間粗利益：収益、コスト、粗利益

</Accordion>

## 仕様と制限事項

| 仕様 | 備考 |
| --- | --- |
| データ更新頻度 | <ul><li>**指標：** リアルタイム以下の画像を参照してください。</li><li>**平均指標**：毎日。以下の画像を参照してください。**注意：** 平均指標は、不完全は日のデータが入ることで平均に歪みがでないように、リアルタイムで計算されていません。期間に現在の日付が含まれている場合、次のように計算されます：<ul><li>期間に現在の日付のみが選択されている場合、平均値は表示されません。</li><li>期間に現在の日付が含まれている一定期間が選択されている場合、現在の日付のデータを除いて平均が計算されます。</li></ul></li><li>**広告収益：** <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#data-freshness">遅れて記録され</Anchor>以下の日付でレポートされます：<ul><li>集計レベルデータ：Day 1（データが取得された日）。</li><li>ユーザーレベルデータ：Day 0（広告が表示された日）</li></ul></li></ul>[![Whats_realtime.png](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png)](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png) |
| アンインストール | サポートされておらず、計測対象外です |
| リターゲティング | 2025年2月1日より、すべてのアクティビティ指標は統合データ（ユーザー獲得とリターゲティングを合わせたもの）となります。2025年2月1日以前のデータについては、次の指標にはUAトラフィックデータのみが含まれます：<ul><li>合計セッション数</li><li>DAU</li><li>MAU</li><li>DAU（1日あたりのアクティブユーザー数）とMAU（1ヶ月あたりのアクティブユーザー数）</li><li>ARPDAU</li><li>コスト</li><li>クリック</li><li>インプレッション</li><li>コンバージョン率</li><li>eCPI</li></ul>統合ビューのみが利用可能であり、ユーザーはユーザー獲得やリターゲティングのみに切り替えることはできません。 |
| ARPDAU | アクティビティ管理画面とピボットのARPDAUの間に不一致が生じることがあります。 |
| 過去データ | <ul><li>3年</li><li>高レベルタブ：1年</li></ul> |
| 表示範囲 | <ul><li>最大2か月。それより長い期間を選択した場合、期間は2か月間に短縮され、通知メッセージが表示されます。</li></ul> |
| 国別データ | <ul><li>国別集計は、インストールした地域に基づいて行われます。</li><li>最大62の国・地域を表示します（上位のアクティビティセッション数でランク付け）。</li></ul> |
| キャンペーンごとのグループ | このグループ化は、特定のメディアソースを選択した後にのみ使用できます。 |
| ディメンション値 | メディアソース、キャンペーン名、アセット名などのディメンションの値は、大文字と小文字を区別します。例えば、"Facebook "と "facebook "は、結果をフィルタリングする際に別々のエンティティとして扱われます。大文字と小文字を区別せずに結果を見るには、<Anchor target="_blank" href="/marketers/ja/docs/pivot-table-user-metrics">ピボットテーブルを</Anchor>利用してください。 |
| 代理店 | 代理店アカウントからはアクティビティダッシュボードにアクセスできません。<Anchor target="_blank" href="/marketers/ja/docs/manage-data-access-permissions">詳細はこちら</Anchor> |

<div data-zendesk-anchors="activity-dashboard=%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%93%E3%83%86%E3%82%A3%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2 h_01HHYHP1HE8G5VA6GSAVTQDDDN=%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%93%E3%83%86%E3%82%A3%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2 h_01HHYHP1HEJHKQKCNC5R26ZE3J=%E3%83%92%E3%83%B3%E3%83%88 dashboard-features-and-layout=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AE%E6%A9%9F%E8%83%BD%E3%81%A8%E3%83%AC%E3%82%A4%E3%82%A2%E3%82%A6%E3%83%88 h_01HHYHP1HEBTACW6Q3MJ3QJJ95=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AE%E6%A9%9F%E8%83%BD%E3%81%A8%E3%83%AC%E3%82%A4%E3%82%A2%E3%82%A6%E3%83%88 h_01HHYHP1HESQBPYJWK81ZHQDVH=metric-definitions h_01HHYHP1HFZBRTWB8MJ1F6XKZS=%E4%BE%8Barpdau%E3%81%AE%E8%A8%88%E7%AE%97 h_01HHYHP1HFF92WQMQAFKWWNDJK=detailed-tab h_01HHYHP1HFNDXC2E55Q7PDE9WY=headline-metrics h_01HHYHP1HFZR9JN2H0RNAG1QTK=activity-trends h_01HHYHP1HFV8AZ2FYKJ300488A=activity-summary-table h_01HHYHP1HF6FCXPS2SHTH0RBXC=highlevel-tab-previous-twelvemonths specifications-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HHYHP1HFNJF4JJZY4CSVZ3GY=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
