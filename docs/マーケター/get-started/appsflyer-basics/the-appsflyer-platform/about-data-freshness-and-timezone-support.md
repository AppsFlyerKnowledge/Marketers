---
title: データの反映タイミングとタイムゾーンへの対応
metadata:
  keywords:
    - Reports
    - Advertisers
    - Agencies
    - Ad Networks
    - timezone
    - data freshness
    - data
    - Developers
    - Gray
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2018-02-19T15:57:01Z'
  edited_at: '2026-10-21T18:45:03Z'
  id: 360000310629
  locale: ja
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/ja/articles/360000310629
---
> **At a glance:** データの反映タイミングとは、イベントが発生してからAppsFlyer上でそのデータを利用できるようになるまでの時間を指します。

**タイムゾーン**

## データの反映タイミングとアプリのタイムゾーンへの対応

### データの反映タイミング

AppsFlyerでは、日次やリアルタイムなど、さまざまな[データ更新方式](/docs/about-data-freshness-and-timezone-support#data-freshness-types)を採用しています。これらの方式でデータを更新し、表示・利用できる状態にします。方式ごとに[データの反映タイミング](/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support)が異なります。

例：イベントダッシュボードのデータの反映タイミング

* 指標のKPI：リアルタイム
* 平均値のKPI：日次

### タイムゾーン

AppsFlyerでは、1日は00:01に始まり、24:00に終了します。デフォルトのタイムゾーンはUTC（GMT）です。デフォルトのタイムゾーンは、<Anchor target="_blank" href="/marketers/ja/docs/changing-app-time-zone-settings">アプリごとのタイムゾーン設定</Anchor>で変更できます。

<Accordion title="日付とタイムゾーンの基本ルール">

UTCには夏時間・冬時間による時刻の切り替えがありません。

UTCとの時差による地域の区分

* UTCより進んだ地域：UTC+と表記されるタイムゾーンは、UTCの基準となる地域より東に位置します。
* UTCより遅れた地域：UTC−と表記されるタイムゾーンは、UTCの基準となる地域より西に位置します。

#### アプリごとのタイムゾーン設定

アプリごとにタイムゾーンを設定できます。この設定により、UTCではなく、設定したタイムゾーンの現地時刻に基づいてデータが日別に集計されます。

例：

**北京：** アプリのタイムゾーンを北京（UTC+8）に設定した場合、1日はUTC 16:01に始まり、翌日のUTC 16:00に終了します。

**ロサンゼルス**：アプリのタイムゾーンをロサンゼルス（UTC−8）に設定した場合、1日はUTC 08:01に始まり、翌日のUTC 08:00に終了します。

#### タイムゾーン設定の推奨事項

* アプリのタイムゾーンは、GoogleやMeta広告など、他のアトリビューションサービスで設定したタイムゾーンとそろえてください。
* 複数のアプリがある場合は、すべて同じタイムゾーンに設定することをお勧めします。アプリのタイムゾーンを確認するには、**設定** > **アプリ設定**に移動してください。
* ほとんどのレポートとデータ抽出ツールは、アプリごとに設定したタイムゾーンに対応しています。複数アプリのレポートも、すべてのアプリで同じタイムゾーンを設定していれば対応しています。

#### 日次処理

一部のレポートやプルダウンリストは、1日1回処理されます。これを「日次更新」または「日次処理」と呼びます。日次処理は、以下のルールに従って行われます。

* 月曜日など、特定の日付に属するデータは、*日別のデータ集計枠*にまとめられます。アプリに設定したタイムゾーンで、1日は00:01に始まり、24:00に終了します。
* 深夜0時から2時間後までに受信したデータは、その日の集計枠に含まれます。たとえば、火曜日の02:00までに受信したデータは、月曜日の集計枠に含まれます。
* 現地時刻の02:00に集計枠が締め切られ、それ以降はデータを追加できなくなります。
* 02:00以降に受信したデータは、イベントの発生日にかかわらず、次の受付中の集計枠に追加されます。
* 締め切られた集計枠の日次処理は、アプリのタイムゾーンにかかわらず、UTCの深夜0時から2時間後に開始されます。以降は説明を分かりやすくするため、処理開始時刻をUTCの深夜0時として扱います。そのため、アプリのタイムゾーンによっては、処理開始までUTCの深夜0時を待つ必要があります。

**UTCより進んだ地域およびUTCのタイムゾーン**：

* 現地時刻で1日が終了してから処理が開始されるまで、最大11時間かかる場合があります。例：
  * 北京（UTC+8）：処理開始まで8時間待つ必要があります
  * ベルリン（UTC+1）：処理開始まで1時間待つ必要があります
  * UTC：待ち時間はありません。
* レポートの種類によって、処理開始から8～20時間後にデータを利用できるようになります。たとえば、北京のデータは現地時刻の16:00以降に利用できます。ベルリンのデータは09:00以降に利用できます。

**UTCより遅れた地域：**

* 1日が終了してから処理が開始されるまで、最大23時間かかる場合があります。例：
  * ロサンゼルス（UTC−8）：処理開始まで16時間待つ必要があります
  * ニューヨーク（UTC−5）：処理開始まで19時間待つ必要があります
* レポートの種類によって、処理開始から8～20時間後にデータを利用できるようになります。たとえば、ロサンゼルスのデータは、イベント発生日の2日後の現地時刻00:01以降に利用できます。ニューヨークのデータは、イベント発生日の2日後の現地時刻03:01以降に利用できます。
* 例：
  * ロサンゼルス時間（UTC−8）の月曜日にイベントが発生した場合、日次処理はUTCの火曜日深夜0時に開始されます。これはロサンゼルス時間の火曜日16:01に相当します。
  * その8時間後、ロサンゼルス時間の水曜日00:01にデータ処理が完了します。つまり、ロサンゼルスの広告主は、水曜日の朝に業務を開始する時点で、月曜日のデータを利用できます。

</Accordion>

<Accordion title="データの更新方式">

| 更新方式 | データを利用できるタイミング | 説明 |
| --- | --- | --- |
| 継続（リアルタイム） | イベント発生から15～60分後 | データは継続的に処理されます。この用語は、日次処理などのようにデータをまとめて処理する方式と区別するために使用します。継続更新では、イベント発生から15～60分の遅延を伴ってデータが更新されます。具体的な時間は以下のとおりです。<ul><li>アトリビューション（インストール、リアトリビューション、リエンゲージメント）：15～30分。</li><li>アプリ内イベント：30～60分。</li></ul> |
| リアルタイムレポート | レポートのリクエストから数分後 | イベント発生から数分以内にデータが更新されます。 |
| 日次 | **UTCのタイムゾーン**：イベント発生日のUTC深夜0時から8時間後<br /><br />**UTCより進んだ地域**：イベント発生日のUTC深夜0時から9～20時間後<br /><br />**UTCより遅れた地域**：イベント発生日のUTC深夜0時から21～32時間後 | <ul><li>データは日次で処理されます。</li><li>データを利用できるタイミングは、アプリに設定したタイムゾーンによって異なります。</li><li>アプリごとのタイムゾーンに対応していないデータでは、UTCが使用されます。</li><li>データを利用できる時刻は日によって変動する場合があります。個別の記事に記載されている場合もあります。</li></ul> |
| 1日の終了時 | アプリに設定したタイムゾーンで、毎日の終了時 | 暦上の1日が終了した時点でデータが反映されます。具体的には、翌日の00:01です。例：月曜日に記録されたデータは、アプリに設定したタイムゾーンにかかわらず、火曜日の00:01から利用できます。 |
| 1日複数回の更新 | 平均4時間ごと | <ul><li>データは1日6回、平均4時間ごとに収集されます。</li><li>ROI360を利用していない場合、SRNのクリック・インプレッションデータは1日3回収集されます。</li><li>Cost ETLのデータは1日4回、平均6時間ごとに送信されます。</li></ul> |
| 広告収益 | 連携方式とレポートによって異なります | <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#data-freshness">詳しくは広告収益の記事をご覧ください</Anchor>。 |
| PBAの日次更新 | UTCで1日が終了してから11～12時間後にデータを利用できます。 | <ul><li>PBAのダッシュボードとレポートは、UTCを基準に[日次](/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles)で更新されます。</li><li>日次処理には、前日に受信したイベントが含まれます。</li><li>コンバージョン発生後の最初の7日間は、そのコンバージョンに関連する追加のイベントがPBAで識別される場合があります。これにより、KPIやアトリビューション先のメディアソースが遡って変更されることがあります。</li><li>7日後にはコンバージョンに至る経路が確定し、それ以降は変更されません。</li><li>ローデータレポートには、*final\_dataというフィールドが含まれます。*この値がtrueの場合、データは確定しています。</li><li>詳しい例</li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">反映までの時間</Anchor>については、ポストバックの受信からダッシュボードやレポートでデータを利用できるようになるまでの説明をご覧ください。 | その日に受信したポストバックは、UTCでその日が終了した時点で処理されます。翌日のUTC 10:00までにデータを利用できるようになります。つまり、月曜日に受信したiOSのポストバックは、火曜日の午前中（UTC）にレポートとダッシュボードに反映されます。同様に、パートナーへのポストバックも火曜日の午前中（UTC）に送信されます。<br /><br />レポートとダッシュボードのインストール日は、ポストバックの受信時刻に基づいて算出されます。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#activity-window">SKANコンバージョンスタジオの記事</Anchor>をご覧ください。 |
| Data Lockerの日次更新 | UTCで1日が終了してから8～10時間後にデータを利用できます | <ul><li>データは日次で処理されます。</li><li>データは、イベント発生日のh=23フォルダに格納されます。たとえば、月曜日のデータは、火曜日のUTC 08:00～10:00に、月曜日のh=23フォルダで利用できるようになります。</li><li>SKANデータは、少し遅れて届く場合があります（上記のSKANの説明を参照）。</li></ul> |

</Accordion>

<Accordion title="データの反映タイミングとタイムゾーン対応一覧">

<table><thead><tr><th>対象データ</th><th>表示・提供形式</th><th>データの更新方式・反映タイミング<br/>（各方式の説明は前のセクションを参照）</th><th>アプリに設定したタイムゾーンでのデータ表示</th></tr></thead><tbody><tr><td>インストール</td><td>KPI</td><td><p>継続</p><p>以下の例外に注意してください。</p><ul><li>Protect360<ul><li>毎日UTC 16:00に更新</li></ul></li></ul></td><td><span>✓</span></td></tr><tr><td>セッション、クリック、インプレッション、ロイヤルユーザー</td><td>KPI</td><td><ul><li>アトリビューションリンク：継続</li><li>SRN：1日複数回の更新</li></ul></td><td><span>✓</span></td></tr><tr><td>収益を伴うアプリ内イベント</td><td>KPI</td><td>継続</td><td><span>✓</span></td></tr><tr><td>広告収益</td><td>KPI</td><td>広告収益</td><td><span>✓</span></td></tr><tr><td>広告費（コスト）</td><td>KPI</td><td><ul><li>アトリビューションリンク：継続（クリックから最大2時間後）</li><li>API：1日複数回の更新</li><li>広告費データの取り込み：取り込みから最大4時間後</li></ul></td><td><span>✓</span></td></tr><tr><td>アンインストール</td><td>KPI</td><td>日次。 AppsFlyerは24時間ごとにアプリストアに確認リクエストを送信します。アンインストールのイベント時刻は、AppsFlyerがサイレントプッシュ通知を送信し、アプリがアンインストールされていることを検知した時刻を表します。実際にアンインストールされた時刻ではありません。</td><td><span><strong>x</strong></span></td></tr><tr><td>管理画面に表示されるアプリ内イベント</td><td>プルダウンリスト</td><td><p>プルダウンリストに表示されるアプリ内イベント名は、日次で更新されます。</p><p>イベントのデータ自体の反映タイミングには影響しません。</p><p><strong>例：</strong>Push API、ダッシュボード、Audiencesのアプリ内イベントのプルダウンリスト。</p></td><td><span>✓</span></td></tr><tr><td>オーバービューダッシュボード</td><td>ページ</td><td>継続</td><td><span>✓</span></td></tr><tr><td>Protect360ダッシュボード</td><td>ページ</td><td>日次</td><td> &lt;0&gt;&lt;1&gt;✓ 1&gt;0&gt;(1)</td></tr><tr><td>SKANダッシュボード</td><td>ページ</td><td>日次</td><td><span><strong>x</strong></span></td></tr><tr><td>アクティビティページ</td><td>ページ</td><td><ul><li>KPI：継続</li><li>平均値：アプリに設定したタイムゾーンの深夜0時</li></ul></td><td><p><span>✓</span></p><p>例外：MAU（月間アクティブユーザー）のデータはUTC</p></td></tr><tr><td>イベントページ</td><td>ページ</td><td>継続</td><td><span>✓</span></td></tr><tr><td> </td><td> </td><td>（この行は意図的に空欄にしています）</td><td> </td></tr><tr><td>リテンション</td><td>ページ</td><td><p>リテンションのKPIは、日次と週次の単位で確認できます。それぞれのデータの反映タイミングは異なります。</p><ul><li>日次リテンションKPI：日次</li><li>週次リテンションKPI：週の開始は月曜日、終了は日曜日です。リテンションは月曜日のUTC 12:00に計算されます。週次KPIはアプリごとのタイムゾーンに対応していませんが、それによって生じる差はごくわずかです。</li></ul></td><td><p>日次：<span>✓</span></p><p>週次：<span><strong>x</strong></span></p></td></tr><tr><td>コホート</td><td>ページ</td><td>継続</td><td> &lt;0&gt;&lt;1&gt;✓ 1&gt;0&gt;(2)</td></tr><tr><td>カスタムダッシュボード</td><td>ページ</td><td>継続</td><td> &lt;0&gt;&lt;1&gt;✓ 1&gt;0&gt;(3)</td></tr><tr><td>Audiences</td><td>ページ</td><td><ul><li>更新データは24時間ごとにパートナーに送信されます。</li><li>ユーザーデータは日次で更新され、最大90日分のデバイスデータを保持します。</li></ul></td><td><span>✓</span></td></tr><tr><td>SDK情報ページ</td><td>ページ</td><td>日次</td><td><span><strong>x</strong></span></td></tr><tr><td>データ出力</td><td>ページ</td><td><p>継続</p><p>以下の例外に注意してください。</p><ul><li>広告収益のローデータ：日次</li><li>Protect360：<ul><li>集計レポート：日次</li><li>ブロックされた不正のローデータ：継続</li><li>ポストアトリビューション（アトリビューション後に検知された不正）のローデータ：日次</li></ul></li><li>オーガニックのアプリ内イベント：数時間の遅延を伴って更新されます。</li></ul></td><td><span>✓</span></td></tr><tr><td>Pull API</td><td>API</td><td>Pull APIのデータの反映タイミングは、データ出力と同じです。</td><td><p><span>✓</span></p><p><span>デフォルトはUTC</span></p></td></tr><tr><td>ピボット</td><td>ページ</td><td>日次</td><td><p><span>✓</span></p><p>週次リテンションKPI：<strong>x</strong></p></td></tr><tr><td>Master API</td><td>API</td><td>日次</td><td> &lt;0&gt;&lt;1&gt;✓ 1&gt;0&gt;(3)</td></tr><tr><td>Data Locker</td><td>API</td><td>詳しくは、<a href="./data-locker-advertiser-reports#data-freshness-explanations" target="_blank">Data Lockerの記事</a>をご覧ください。</td><td><p><span><strong>x</strong></span></p><p><span><strong>UTC</strong></span></p></td></tr><tr><td>ポストバック</td><td>API</td><td>継続</td><td>対象外</td></tr><tr><td>Push API</td><td>API</td><td>継続（4）</td><td><p><span>✓</span></p><p><span><strong>両方</strong></span></p></td></tr><tr><td>サーバー間（S2S）送信によるアプリ内イベント</td><td>API</td><td>継続</td><td>対象外</td></tr><tr><td colspan="4"><p>注意：</p><p>（1）ユーザーがアクセス権限を持つすべてのアプリで、同じタイムゾーンを設定する必要があります。タイムゾーンが異なる場合は、UTCが使用されます。</p><p>（2）UTCが使用される条件については、<a href="./cohort-and-retention-dashboard#traits-and-limitations" target="_blank">コホートの仕様と制限事項</a>をご覧ください。</p><p>（3）選択したすべてのアプリで、同じタイムゾーンを設定する必要があります。タイムゾーンが異なる場合は、UTCが使用されます。</p><p>（4）SKANレポートのデータは、毎日UTC 08:00～10:00に利用できるようになります。</p></td></tr></tbody></table>

> 📘 **例外：Web、CTV、PC・コンソールアプリのマイダッシュボードにおけるコホート・アクティビティ指標**
>
> これらの指標には、上記の継続更新・リアルタイムの反映タイミングは適用されません。当日のデータは、翌日の日次処理が完了した後に利用できるようになります。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/my-dashboards#traits-and-limitations">マイダッシュボードの仕様と制限事項</Anchor>をご覧ください。

</Accordion>

<div data-zendesk-anchors="data-freshness-and-support-for-appspecific-time-zones=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%8D%E6%98%A0%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0%E3%81%A8%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E3%81%B8%E3%81%AE%E5%AF%BE%E5%BF%9C 01EDBBPAH96ADJ56FRNB34K3VB=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%8D%E6%98%A0%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0%E3%81%A8%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E3%81%B8%E3%81%AE%E5%AF%BE%E5%BF%9C data-freshness=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%8D%E6%98%A0%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0 01EDBBPAH9M5KQRXJ1TNN3RJAX=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%8D%E6%98%A0%E3%82%BF%E3%82%A4%E3%83%9F%E3%83%B3%E3%82%B0 time-zones=%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3 01EDBBPAH92JJVVGXN61N4SV89=%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3 appspecific-time-zone=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%94%E3%81%A8%E3%81%AE%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E8%A8%AD%E5%AE%9A 01EDBBPAH9WHDY875Y913PV00Z=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%94%E3%81%A8%E3%81%AE%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E8%A8%AD%E5%AE%9A timezone-guidelines=%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E8%A8%AD%E5%AE%9A%E3%81%AE%E6%8E%A8%E5%A5%A8%E4%BA%8B%E9%A0%85 01EDBBPAH9TRH8HBB0JAX2369H=%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E8%A8%AD%E5%AE%9A%E3%81%AE%E6%8E%A8%E5%A5%A8%E4%BA%8B%E9%A0%85 daily-processing=%E6%97%A5%E6%AC%A1%E5%87%A6%E7%90%86 01EDBBPAH98F0641D934W9NJD8=%E6%97%A5%E6%AC%A1%E5%87%A6%E7%90%86 h_01M2MJESA4EG1BEVM5T6N9FH0D=%E4%BE%8B%E5%A4%96webctvpc%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%9E%E3%82%A4%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E3%82%B3%E3%83%9B%E3%83%BC%E3%83%88%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%93%E3%83%86%E3%82%A3%E6%8C%87%E6%A8%99" />
