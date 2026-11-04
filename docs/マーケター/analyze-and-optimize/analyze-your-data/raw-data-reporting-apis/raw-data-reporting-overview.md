---
title: ローデータレポート｜概要
metadata:
  keywords:
    - LTV
    - raw data
    - uninstalls
    - AFI
    - Advertisers
    - Agencies
    - Premium Feature
    - Gray
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2016-03-21T08:32:06Z'
  edited_at: '2026-10-14T09:34:51Z'
  id: 209680773
  locale: ja
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/ja/articles/209680773
---
> **概要：概要**：行レベルデータ（ローデータ）には、インストール、アプリ内イベント、Webサイト訪問、Protect360ブロック済みインストール、広告収益、パートナーに送信されたユーザーに関するポストバックなどのユーザーに関するイベントが記載されています。ローデータレポートは、ダウンロード、API、Data Lockerを介して取得できます。

<div id="raw-data-reportingtools-and-reports" />

## ローデータレポート｜ツールとレポート

ローデータレポートを使用すると、ユーザーの行動やジャーニーの分析、広告ネットワークのアカウントとのデータ照合、CRMやBIシステムのデータ拡充などを行うことができます。ローデータを活用することで、アプリのパフォーマンスをより詳細に分析し、最適化や改善につなげることができます。

レポートは、各種レポーティングツールを介して利用できます。それぞれのツールには異なる特性があり、用途に応じて使い分けることができます。たとえば、特定の広告ネットワークのアカウントとデータを照合する場合は、必要に応じてデータ出力のページからレポートをダウンロードできます。一方、ユーザーのパフォーマンスデータをBIシステムに取り込む場合は、Data LockerまたはPull APIを使用してプログラムからデータを取得できます。

<div id="tip" />

> 👍 **ヒント**
>
> ローデータについてさらに詳しく知りたい場合は、<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7806/play/18629/viewing-and-understanding-your-raw-data">AppsFlyer Learning Portal</Anchor>の短時間で学べるコースをご覧ください。

<div id="reporting-tools-characteristics-and-features" />

<Accordion title="レポーティングツール｜特性と機能">

このセクションでは、レポートの取得に使用できる各レポーティングツールについて説明します。

以下の点にご留意ください：

* レポートの日付範囲は、イベントが実際に発生した日付（アクティビティベース）に基づきます。これは、日付範囲が<Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTVベース</Anchor>となる集計レポートとは異なります。
* 各項目の説明については、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">データ項目の手引き</Anchor>をご覧ください。

<div id="reporting-tools" />

#### レポートツール

<table><thead><tr><th>ツール</th><th>説明</th><th>複数 / 単一アプリ（1）</th><th>データ更新（2）</th><th>スクリプトへの埋め込み</th><th>タイムゾーン</th><th>通貨</th></tr></thead><tbody><tr><td><a href="./raw-data-export-page" target="_blank">ローデータ出力ページ</a></td><td><ul><li>ユーザーインターフェースからレポートをダウンロード</li><li>形式：CSVファイル</li></ul></td><td>単一アプリ</td><td>継続的に更新</td><td><span><strong>x</strong></span></td><td>アプリ設定値</td><td>アプリ設定値</td></tr><tr><td><a href="./pull-api-raw-data" target="_blank">Pull API\*</a></td><td><ul><li>APIコールを使用してレポートをダウンロード</li><li>形式：CSVファイル</li></ul></td><td>単一アプリ</td><td>継続的に更新</td><td><span>✓</span></td><td><ul><li>選択可能</li><li>デフォルト：UTC</li></ul></td><td><ul><li>選択可能</li><li>デフォルト：USD</li></ul></td></tr><tr><td> <a href="./data-locker-for-marketers" target="_blank">Data Locker</a> <span><strong>P</strong></span> </td><td><ul><li> <a href="./data-locker-cloud-service-setup" target="_blank">クラウド上のバケット</a>にデータをストリーミング </li><li>データ量の制限なし</li><li>データ保持期間：14日間</li><li>形式：CSVまたはParquet</li></ul></td><td>複数</td><td>数時間程度の遅延を伴い継続的に更新</td><td><span>✓</span></td><td>UTC</td><td>USD </td></tr><tr><td> <a href="./push-api-streaming-raw-data" target="_blank">Push API<span></span></a> <span><strong>P</strong></span> </td><td><ul><li>ユーザージャーニーデータ（インストール、アプリ内イベント、リターゲティング、SKAN）をリアルタイムでお客様のサーバーに送信</li><li>形式：JSONまたはクエリのパラメーター</li></ul></td><td>同じエンドポイントを使用可能</td><td>AppsFlyerでイベントが記録されてから数分以内</td><td><span>✓</span></td><td>UTC + アプリ固有</td><td>USD + アプリ固有</td></tr><tr><td> <a href="./conversion-data-payloads-and-scenarios" target="_blank">SDK Conversion data</a>（3）</td><td><ul><li>アプリ内でアトリビューションのコンバージョンデータを取得</li><li>形式：JSON</li></ul></td><td>該当なし</td><td>初回アプリ起動から最長8秒以内にユーザーのアトリビューションデータを取得（AppsFlyerサーバーでの処理に最長5秒、それに加えてエンドツーエンドのネットワーク遅延）</td><td><span>✓</span></td><td>UTC</td><td>該当なし</td></tr><tr><td colspan="7"> <strong>注記および略語：</strong><br/>（1）複数アプリへの対応<br/>（2）実際のデータ更新頻度はレポートによって異なります。一部のレポートは日次で更新されます。<br/>（3）SDK Conversion dataでは、初回アプリ起動から最長8秒以内にユーザーのアトリビューションデータを取得します（AppsFlyerサーバーでの処理に最長5秒、それに加えてエンドツーエンドのネットワーク遅延）。そのため、この方法は最も精度が低くなります。<br/><span><strong>（P）</strong> </span><span>Premium機能</span><br/><a href="./report-generation-quotas-rate-limitations" target="_blank">（\*）レポート生成数の上限が適用されます。</a> </td></tr></tbody></table>

<div id="tool-limitations" />

#### ツールの制限事項

<table><thead><tr><th>制限 </th><th>Pull API（\*）</th><th>Push API</th><th>Data Locker</th><th>SDK<br/>Conversion data</th></tr></thead><tbody><tr><td>データ制限</td><td>1回のAPIコールにつき100万行</td><td>該当なし</td><td>該当なし</td><td>該当なし</td></tr><tr><td>データの選択オプション</td><td>データタイプを選択可能。項目の選択には制限あり</td><td>データタイプ、項目、アプリ内イベントを選択可能</td><td>データタイプ、項目、アプリ内イベントを選択可能</td><td>不可</td></tr><tr><td>データ取得可能期間</td><td>90日間</td><td>該当なし</td><td>14日間 </td><td>無期限（SDK内で利用可能）</td></tr><tr><td colspan="5"><a href="./report-generation-quotas-rate-limitations" target="_blank">（\*）レポート生成数の上限が適用されます。</a></td></tr></tbody></table>

<div id="integration-considerations" />

#### 実装に関する考慮事項

| 注意事項 | Pull API | Push API | Data Locker | SDK  <br />Conversion Data |
| --- | --- | --- | --- | --- |
| サーバーサイドでの開発 | 任意 | 必須 | 任意 | 任意 |
| データ処理 | 任意 | 必須 | 任意 | 任意 |
| データ損失のリスク | なし | あり（受信側サーバーがダウンしている場合） | なし | 小（広告ネットワークからのレスポンスに遅延が発生した場合） |
| クライアント・サーバー間の処理コスト | なし | 高 | 低 | なし（データをサーバーに送信する場合を除く） |
| クライアント・サーバー間のメンテナンス | なし | 高 | 低 | なし（データをサーバーに送信する場合を除く） |
| データ形式 | CSVファイル | JSONまたはクエリのパラメーター | CSVまたはParquet | JSON |

</Accordion>

特定のコンテキストで生成されたローデータレコードは、レポート単位でまとめられます。たとえば、非オーガニックインストールやオーガニックのアプリ内イベントなどです。分かりやすくするため、レポートは以下のように分類されています：

* **ユーザージャーニー：** ユーザーがアプリとどのように接触し、エンゲージしたかという一連のジャーニーを追跡するために使用します。  
  例：クリック > インストール > アプリ内イベント > アンインストール
* **機能別：** 特定のAppsFlyer機能に関連するものの、主要なユーザージャーニーには含まれないレポートです。たとえば、広告ネットワークへのポストバック、不正および検証ルールに関するレポート、ユーザー単位の広告収益レポートなどがあります。

<div id="report-fields" />

<Accordion title="レポート項目">

<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">ローデータ</Anchor>項目の手引きには、ユーザージャーニーレポートに関連する項目と、一部の機能別レポートの項目が記載されています。その原則は以下の通りです。

* **ユーザージャーニー：**
  * 共通の項目セットがあります。
  * 各項目に値が入力されるかどうかは、ジャーニーのコンテキストによって異なります。たとえば、非オーガニックレポートにはユーザー獲得に貢献したメディアソースが含まれます。 一方、オーガニックレポートにはメディアソースが存在しないため、アトリビューション関連の項目には値が入力されません。
* **機能：** 機能固有の項目セットを持つ場合と、ユーザージャーニーの項目に、その機能に関連する追加項目が含まれる場合があります。たとえば、SKAdNetworkレポートには固有の項目一覧があります。一方、ポストバックレポートにはユーザージャーニーの項目に加えて、パートナーへのポストバック送信に関連する項目が含まれます。

**ヒント：** 各レポートについて理解するには、実際のレポートを確認するのが最も効果的です。**データ出力ページ**から各種レポートをダウンロードできます。

分かりやすくするため、ユーザージャーニーの項目はコンテキストに基づいてグループ分けされています。

<div id="user-journey-raw-data-field-groups" />

#### ユーザージャーニーのローデータ項目グループ

| 項目グループ | オーガニックユーザーとの関連 | 項目の例 |
| --- | --- | --- |
| App | はい | App ID, app name, app version, SDK version, ATT |
| Attribution | なし（Install timeを除く） | Install time、Attributed touch time、Media source、Campaign、Adset、Ad、Partner、Retargeting conversion type |
| Contributors attribution | なし | Contributor partner, match type |
| Device info | はい | Advertising ID, GAID, OAID, device type, customer user ID |
| Device location | はい | IP address, city, country |
| Event | はい | アプリ内イベントレポートの場合：<br /><br />Event name、Event value、Event revenue |

</Accordion>

<div id="user-journey-reports" />

## ユーザージャーニーレポート

![Raw_data_-_User_acquisition_.png](https://files.readme.io/319da2a6a5567d6cfe4a74337279e67e0bdcdb063e62ecacde5eb4293a98a1a2-36317497158033.png)

<div id="user-journey-basics" />

<Accordion title="ユーザージャーニーの基本">

ユーザージャーニーレポートには、ユーザーのライフタイム中に発生したイベントについて収集されたデータが含まれます。データは、以下の観点に基づいて各レポートに分類されます。

* ユーザーの流入元：オーガニックまたは非オーガニック
* ジャーニーのコンテキスト：
  * アプリインストール前の広告とのエンゲージメント（インプレッションおよびクリック）
  * ユーザー獲得
  * リターゲティング

**ユーザー獲得（UA）レポートには、以下のデータが含まれます：**

* 広告にエンゲージした*潜在ユーザー*による、インストール前のインプレッションとクリック
* インストールイベント
* その後ユーザーが実行したアプリ内イベント

**リターゲティングレポートには、以下のデータが含まれます：**

* ユーザーがリターゲティングされた際に発生したインプレッションとクリック
* コンバージョンイベント：リエンゲージメントまたはリアトリビューション
* リエンゲージメントの一環として、その後ユーザーが実行したアプリ内イベント注意点：
  * リターゲティングデータは常に非オーガニックです。
  * リターゲティングのアプリ内イベントは、UAのアプリ内イベントレポートとリターゲティングのアプリ内イベントレポートの両方に含まれます。詳しくは<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">詳しくは、リターゲティングの二重アトリビューションの仕組み</Anchor>をご覧ください。

    ![Raw_data_-_Retargeting.png](https://files.readme.io/717f6e43ca3b224ead9e3e1c5f9b277d2f21dbc1fe3b4c217ebf4bdbc539bab7-36317470735249.png)

ユーザージャーニーを追跡するには、インストールやアプリ内イベントなど、確認したいジャーニーの区間に関連するレポートを組み合わせます。その後、AppsFlyer ID、イベント時刻、レポートタイプの順にレポートを並べ替えることで、特定のユーザーについて時系列に並んだイベント、つまりユーザージャーニーを確認できます。

</Accordion>

<div id="user-journey-report-availability" />

<Accordion title="ユーザージャーニーレポートの提供状況">

* レポートの利用可否は、ご利用のサブスクリプションプランによって異なります。
* レポートには、記載されている内容に応じて、オーガニックユーザー、非オーガニックユーザー、またはその両方のデータが含まれます。
* 過去のローデータレポートには、使用するレポーティングツールおよびローデータの取得元に応じてデータ保持ポリシーが適用されます。通常、過去90日間のデータを利用できます。<strong>注意！</strong>データ保持ポリシーは集計データには適用されません。

<div id="user-journey-reports-1" />

#### ユーザージャーニーレポート

<table><thead><tr><th>カテゴリ</th><th>Data Lockerのみ</th><th>レポート内容</th><th>オーガニック</th><th>非オーガニック</th></tr></thead><tbody><tr><td>ユーザー獲得</td><td><span>✓</span></td><td>クリック</td><td colspan="2">該当なし</td></tr><tr><td>リターゲティング</td><td><span>✓</span></td><td>リターゲティングキャンペーンからのクリック </td><td colspan="2">リターゲティングは常に非オーガニック</td></tr><tr><td>ユーザー獲得</td><td><span>✓</span></td><td>インプレッション</td><td colspan="2">該当なし</td></tr><tr><td>リターゲティング</td><td><span>✓</span></td><td>リターゲティングキャンペーンのインプレッション</td><td colspan="2">リターゲティングは常に非オーガニック</td></tr><tr><td>ユーザー獲得</td><td>-</td><td>インストール </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>ユーザー獲得</td><td>-</td><td>アプリ内イベント </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>ユーザー獲得</td><td>-</td><td>アトリビューション済み広告収益</td><td>-</td><td><span>✓</span></td></tr><tr><td>ユーザー獲得</td><td>-</td><td>オーガニック広告収益</td><td><span>✓</span></td><td>-</td></tr><tr><td>リターゲティング</td><td>-</td><td>リターゲティング広告収益</td><td colspan="2">リターゲティングは常に非オーガニック</td></tr><tr><td>リターゲティング</td><td>-</td><td>リターゲティングコンバージョン（リエンゲージメントとリアトリビューション）</td><td colspan="2">リターゲティングは常に非オーガニック</td></tr><tr><td>リターゲティング</td><td>-</td><td>リターゲティングアプリ内イベント（リエンゲージメントとリアトリビューション）</td><td colspan="2">リターゲティングは常に非オーガニック</td></tr><tr><td>リターゲティング</td><td><span>✓</span></td><td>リターゲティングセッション（リエンゲージメントとリアトリビューション）</td><td colspan="2">リターゲティングは常に非オーガニック</td></tr><tr><td>ユーザー獲得</td><td><span>✓</span></td><td>セッション</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>ユーザー獲得</td><td>-</td><td>非オーガニックアンインストール </td><td>-</td><td><span>✓</span></td></tr><tr><td>ユーザー獲得</td><td>-</td><td>オーガニックアンインストール</td><td><span>✓</span></td><td>-</td></tr><tr><td>ユーザー獲得</td><td><span>✓</span></td><td>クロスプラットフォームエンゲージメント</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div id="user-journey-report-descriptions" />

<Accordion title="ユーザージャーニーレポートの詳細">

<div id="clicks-and-impressions" />

#### クリックとインプレッション

| レポート | 特性 |
| --- | --- |
| コンテクスト | ユーザーがキャンペーンにエンゲージし、広告をクリックまたは閲覧した場合 |
| 特性 | ユーザーが広告をクリックまたは<Anchor target="_blank" href="/marketers/ja/docs/measure-view-through-engagements#set-impression-links">閲覧</Anchor>した際のアトリビューションリンクおよびHTTPヘッダーの記録が含まれます。 |
| ユースケース | <ul><li>アプリ起動（インストール、リアトリビューション、リエンゲージメント）につながらないキャンペーンを最適化する</li><li>別のキャンペーンを使用して、該当ユーザーをリターゲティングする</li></ul> |
| サンプルレポート | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1036692270&single=true&output=csv">クリック</Anchor> |
| 備考 | SRNのデータは利用できません。 |
| 制限対象ユーザー | プライバシールールにより、インプレッションやクリックのデータが制限される場合があります。この場合、ユーザー識別子が含まれない、またはデータ自体を利用できないことがあります。利用可否は、メディアソースおよびプラットフォームによって異なります。 |

<div id="installs-and-retargeting-conversions" />

#### インストールとリターゲティングコンバージョン

<table><thead><tr><th rowspan="2">レポート名 </th><th rowspan="2"><p>ユーザー獲得：インストール</p></th><th rowspan="2">リターゲティングデータ：コンバージョン</th></tr></thead><tbody><tr><td>コンテクスト</td><td><p>ユーザーが初めてアプリを起動したとき。</p></td><td><p>ユーザーがリターゲティング広告にエンゲージした後、アプリを起動したとき。リターゲティングコンバージョンには、リエンゲージメントまたはリアトリビューションがあります。</p><a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">リターゲティング計測ガイド</a>を参照してください。 </td></tr><tr><td>使用事例</td><td><ul><li>AppsFlyerの分析ツールでは利用できない項目を使用して、集計レポートを作成する</li><li>他のレポートと組み合わせ、高度な横断分析を行う</li><li>都市や大都市圏など、さまざまなディメンションでパフォーマンスを分析する </li><li>国、都市、言語に基づいてユーザーをセグメント化し、ターゲティングに活用する リターゲティングに使用するユーザーのデバイスIDを取得する</li><li>リターゲティングのユースケースも、基本的にはインストールの場合と同様です。</li></ul></td><td>インストールに似ています。</td></tr><tr><td>オーガニックと非オーガニック</td><td><ul><li> <strong>非オーガニック：</strong>AttributionおよびContributors attributionの項目グループに値が入力されます。</li><li> <strong>オーガニック：</strong> Media sourceの項目は、空欄、null、またはorganicになります。システムにデータを読み込む際は、この点にご留意ください。 </li></ul></td><td>適用外</td></tr><tr><td>サンプルレポート</td><td><a href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR2yvNGmZp8ataHBj89CFq856PmDixnyjKK75O8fQcS9TjT8J2jBAnJoTn3350NV-7pCSlaT0oh8ebs/pub?output=csv" target="_blank">インストール</a></td><td>リターゲティングコンバージョンレポートは、インストールレポートと同じ構造です。一部の項目には、リターゲティングのコンテキストに応じた値が入力されます。<a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">リターゲティングローデータ</a> をご覧ください。 </td></tr></tbody></table>

<div id="in-app-events" />

#### アプリ内イベント

<Table>
  <thead>
    <tr>
      <th>
        レポート
      </th>
      <th>
        特性
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-context"></span>
        レポートのコンテキスト
      </td>
      <td>
        アトリビューション（インストール、リアトリビューション、リエンゲージメント）後にユーザーが実行したアクションを時系列で表示します。
      </td>
    </tr>
    <tr>
      <td><span id="characteristics"></span>
        特性
      </td>
      <td>
        * レポートの構造と項目は、インストールレポートと類似しています。
        * イベント専用の項目には、イベント名、値、収益、時刻などの情報が含まれます。
      </td>
    </tr>
    <tr>
      <td><span id="use-case"></span>
        ユースケース
      </td>
      <td>
        このレポートは、次の目的で使用します。

        * ユーザーのライフタイム全体にわたるジャーニーを確認し、インサイトを得る
        * インストールとアプリ内イベントのローデータを組み合わせて、ユーザーのジャーニー全体を追跡する
      </td>
    </tr>
    <tr>
      <td><span id="event-values"></span>
        イベント値
      </td>
      <td>
        **イベント値の項目**

        には、イベントに関連するすべてのデータがJSON形式で格納されます。BIシステムに読み込んで、さらに詳細な分析を行うことができます。

        **ヒント：** <Anchor target="_blank" href="https://docs.microsoft.com/en-us/power-query/parse-json-xml">Microsoft ExcelのPower Query</Anchor>を使用すると、JSONテキスト文字列からイベントパラメーターを解析できます。

        ```json
        {"af_level":"10","af_user_journey":"3387","arena":"7","char_type":"paladin"}
        ```

        **収益のレポート**

        AppsFlyerの収益およびROIデータは、イベントで送信されたaf\_revenueをもとに算出されます。

        アプリ内イベントでaf\_revenueパラメーターが送信されると、AppsFlyerはその値を使用してEvent revenueの項目を入力します。この項目の値をもとに、ダッシュボードおよび集計レポートが更新されます。

        注意！af\_revenueパラメーターは、**実際に発生した収益を表すアプリ内イベントにのみ使用してください。 add\_to\_cartなど、収益に関連していても最終的な収益確定を表さないイベントでは、af\_priceなどの別のパラメーターを使用してください。**
      </td>
    </tr>
    <tr>
      <td><span id="example-report"></span>
        サンプルレポート
      </td>
      <td>
        <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQhOF-g3HeqZt3rXx7WZVQnB54p7ALW_IEpnJ9xtAkrcb9XzZwweiNCZzEmuX7q0i1g6yYMxYtuuX1c/pub?output=csv">アプリ内イベント</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="remarks"></span>
        備考
      </td>
      <td>
        * リターゲティングのアプリ内イベントは、UAとリターゲティングの両方のアプリ内イベントローデータレポートに<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">二重で記録されます。</Anchor>
        * アプリ内イベントには、起動イベント（af\_app\_opened）は含まれません。このイベントは、<Anchor target="_blank" href="/marketers/ja/docs/measure-sessions">セッション</Anchor>のローデータレポートで確認できます。
        * 位置情報は、イベント実行時のユーザーのIPアドレスをもとに判定されます。
      </td>
    </tr>
  </tbody>
</Table>

<div id="sessions" />

#### セッション

| レポート | 特性 |
| --- | --- |
| コンテクスト | ユーザーがアプリを起動すると、セッションイベントがAppsFlyerに送信されます。「<Anchor target="_blank" href="/marketers/ja/docs/measure-sessions">セッション間の最短時間</Anchor>」のしきい値を超えている場合にイベントが記録されます。 |
| 特性 | レポートの構成は、アプリ内イベントレポートと同じです。セッションイベントは非常に件数が多いため、個別のレポートとして提供されます。 |
| ユースケース | アプリに対するユーザーエンゲージメントを把握する |
| サンプルレポート | セッションレポートはアプリ内イベントレポートと類似しています。（注：ローデータでは、セッションのイベント名は*launch*です。） |

<div id="uninstalls" />

#### アンインストール

| レポート | 特性 |
| --- | --- |
| コンテクスト | ユーザーによるアプリのアンインストールを記録します。 |
| 特性 | <ul><li>他のユーザージャーニーレポートのように継続的に更新されるのではなく、このレポートは1日1回更新されます。</li><li>レポートのEvent timeは、実際にアンインストールが行われた時刻ではなく、AppsFlyerがアプリのアンインストールを判定した時刻を表します。詳しくは、アンインストール計測を参照してください。</li></ul> |
| 利用可能な項目 | <ul><li>ユーザーが非オーガニックのメディアソースから流入している場合、Media source関連の項目に値が入力されます。</li><li>アンインストールイベントは、ユーザーがアプリをアンインストールしたとAppsFlyerが判定した後、AppsFlyerサーバーによって生成されます。そのため、多くの項目には値が入力されません。</li><li>利用できるユーザー識別子は、インストール時に記録されたものです。CUIDは利用できません。</li><li>位置情報関連の項目には、ユーザーがメディアソースにエンゲージした時点（クリックまたはインプレッション）の位置情報が入力されます。エンゲージメント時の位置情報を利用できない場合は、インストールイベントに関連付けられた位置情報が使用されます。</li></ul> |
| サンプルレポート | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1558773473&single=true&output=csv">アンインストール</Anchor>：例を分かりやすくするため、サンプルレポートの2行目には、関連するデータが利用可能な場合に値が入力される項目が示されています。 |
| ユースケース | <ul><li>アンインストールイベント、デバイス、ユーザー属性を分析する</li><li>リターゲティングに使用するアンインストールユーザーのオーディエンスを作成する</li></ul> |

</Accordion>

<div id="user-journey-report-availability-per-tool" />

<Accordion title="ツール別のユーザージャーニーレポート提供状況">

<div id="ad-engagement-report-by-tool" />

#### 広告エンゲージメントレポート：ツール別

<table><thead><tr><th>レポート</th><th>データ出力</th><th>Pull API</th><th>Data Locker</th><th>Push API</th><th>SDK<br/>Conversion Data</th></tr></thead><tbody><tr><td>インプレッション (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>クリック (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td colspan="6">(1) クリックおよびインプレッションデータは非SRN媒体から提供されます。SRNではこれらのデータは提供されません。</td></tr></tbody></table>

<div id="user-acquisition-reports-by-tool" />

#### ユーザー獲得レポート：ツール別

| レポート | データ出力 | Pull API | Data Locker | Push API | SDK conversion data |
| --- | --- | --- | --- | --- | --- |
| インストール | ✓ | ✓ | ✓ | ✓ | ✓ |
| セッション | - | - | ✓ | - | - |
| アプリ内イベント | ✓ | ✓ | ✓ | ✓ | - |
| アンインストール | ✓ | ✓ | ✓ | - | - |

<div id="retargeting-raw-data-reports-by-tool" />

#### リターゲティングローデータレポート：ツール別

<table><thead><tr><th>レポート</th><th>データ出力</th><th>Pull API</th><th>Data Locker</th><th>Push API</th><th>SDK<br/>conversion Data</th></tr></thead><tbody><tr><td>クリック (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>コンバージョン（リアトリビューション＋リエンゲージメント）</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>インプレッション (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>セッション</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>アプリ内イベント</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">(1) クリックおよびインプレッションデータは非SRN媒体から提供されます。SRNではこれらのデータは提供されません。</td></tr></tbody></table>

</Accordion>

<div id="faq" />

<Accordion title="よくある質問">

| 詳細 |
| --- |
| **タイムスタンプにはどのような違いがありますか？**<br /><br />タイムスタンプはすべてのレポートで共通しているため、異なるレポート同士を組み合わせることができます。<br /><br />関連するタイムスタンプは以下のとおりです。<ul><li>**Attributed touch time**：ユーザーが広告にエンゲージした時刻</li><li>**Install** **time**：アプリが初めて起動された時刻</li><li>**Event time**：イベントが発生した時刻</li></ul>注意点：<ul><li>インストールレポートでは、Install timeとEvent timeは同じです。</li><li>アプリ内イベントレポートでは、Install timeとEvent timeは異なります。その差から、アプリの初回起動からユーザーがアプリ内でエンゲージするまでに経過した時間を確認できます。</li></ul> |
| **Contributorの項目は何のために使用されますか？**<br /><br />Contributorの項目には、コンバージョンに貢献したメディアソースが記録されます。これらは<Anchor target="_blank" href="/marketers/ja/docs/measure-assisted-installs#アシストインストールのレポート">アシストインストール</Anchor>と呼ばれることもあります。Protect360では、この項目は<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports#ハイジャックされたインストールのアトリビューション修正">ハイジャックされたインストールのアトリビューション修正</Anchor>にも使用されます。 |
| **Keywordsの項目は何を指しますか？なぜ、すべての非オーガニックインストールで利用できないのですか？**<br /><br />Google AdsまたはApple Adsにアトリビューションされたインストールには、そのインストールにつながった広告に関連するキーワードまたはKeyword IDが含まれる場合があります。 |

</Accordion>

<div id="install-report-tips" />

<Accordion title="インストールレポート活用のヒント">

**ユーザージャーニーの理解**

ユーザージャーニーとは、商品の購入や航空券の予約など、特定の目標を達成するまでにユーザーが行う一連のステップのことです。ユーザージャーニーを分析する目的は、ユーザーがアプリ内でどのような行動を取っているか、どの程度アクティブであるか、そして一定期間にどの程度の価値をもたらしているかを把握することです。

AppsFlyer IDを使用すると、ユーザージャーニーを特定して可視化できます。AppsFlyer IDは、デバイスごとのアプリインストールに対して生成されます。このIDは、インストールからアンインストールまで、ユーザーのライフサイクルを通じて変更されません。また、ユーザーがデバイスIDをリセットした場合でも、AppsFlyer IDは保持されます。

インストールレポートとアプリ内イベントレポートは同じ構造を持つため、1つのレポートに統合できます。統合したレポートでは、AppsFlyer IDおよびCustomer User ID（利用可能な場合）を使用して集計やフィルタリングを行い、ユーザージャーニーを分析できます。

> 📄 **例**
>
> #### <span id="engaged-userstrong"></span>アプリとのエンゲージメントが強いユーザー
>
> * ユーザーが8月20日9:31にアプリをインストールしました。
> * 統合レポートを見ると、8月20日10:31、8月22日15:22、8月25日16:47に購入を行っています。
> * この結果から、このユーザーはエンゲージメントの高いユーザーであると判断できます。アプリを起動してから1時間後に購入し、その後もインストール後の数日間にわたって購入を継続しています。
>
> #### <span id="engaged-userweak"></span>アプリとのエンゲージメントが弱いユーザー
>
> * ユーザーが7月30日にアプリをインストールしました。統合レポートを見ると、8月15日に商品をカートへ追加していますが、その後の購入イベントはありません。
> * このユーザーは購入をためらっている可能性があると判断し、カートに追加した商品を使用してリターゲティングすることができます。
>
> #### <span id="analyzing-the-user-journey-for-campaign-optimization"></span>キャンペーン最適化のためのユーザージャーニー分析
>
> * 旅行アプリのユーザー獲得（UA）担当者が、インストールレポートとアプリ内イベントレポートをダウンロードして統合します。
> * 次に、アプリ内のユーザージャーニーを確認するため、AppsFlyer IDを使用してデータをフィルタリングまたは集計します。
> * AppsFlyer IDで特定されたあるユーザーが、12か月前にアプリをダウンロードし、その数日後に航空券を予約していたことが分かりました。
> * その後、このユーザーはいくつかの航空券情報を閲覧したものの、予約には至っていませんでした。さらに調査を進めたところ、UA担当者は同じような行動パターンを持つユーザーが他にもいることを発見し、より詳しく分析することにしました。
> * その結果、これらのユーザーの多くが、**メディアソースC**で配信された**キャンペーンB**の**広告A**から流入していることが分かりました。この広告とキャンペーンは、特定の目的地への旅行を希望するユーザーをターゲットとしていました。
> * ユーザージャーニーを分析することで、UA担当者は、このキャンペーンのターゲティング範囲が狭すぎたこと、またユーザーがアプリに十分エンゲージしていなかった可能性があると判断できます。

</Accordion>

<div id="feature-reports" />

## 機能別レポート

プラットフォームで利用できる追加機能に関連するレポートです。

* <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">広告収益</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview#ローデータレポート">Incrementality</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/skan-raw-data-reports">SKAdNetwork</Anchor>

<div id="postbacks" />

<Accordion title="ポストバック">

ポストバックレポートでは、広告ネットワークに送信されたデータのコピーを確認できます。たとえば、データの乖離を調査する際に利用できます。これらのレポートは情報確認を目的としたものであり、広告ネットワークとの連携に必須ではありません。

* レポートには、以下のデータが含まれます。
  * アトリビューションされたメディアソースに送信されたポストバックのコピー
  * <Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">ローデータ項目</Anchor>、およびこのセクションで説明する追加項目
* 一方、ポストバックレポートに以下のデータは含まれません。
  * SRNのインストール
  * Meta Ads、X Ads、Apple Adsに関連するアプリ内イベント
  * アトリビューションされていないパートナーのポストバック詳しくは、「<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">他のパートナーまたはオーガニックに紐づいたイベント</Anchor>」をご覧ください。
  * オーガニックユーザーのデータ。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">オーガニックユーザーについて</Anchor>を参照してください。
* 2021年3月以降、各項目の値は広告ネットワークの高プライバシーポストバックの設定に応じて入力されます。つまり、高プライバシーポストバックが有効になっている場合、ユーザー識別子など一部の項目は含まれません。詳しくは、<Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks#advanced-privacy-postback-specification">アドネットワーク向け高プライバシーポストバックの仕様について</Anchor>を参照してください。
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5">ポストバックレポートはPull APIから取得することもできます。</Anchor>

<div id="postback-reports-available-via-the-export-data-page-and-pull-api" />

#### ポストバックレポート（Export DataページおよびPull APIから利用可能）

| レポート内容 | 成果が紐づくメディアソースに送信されるイベント |
| --- | --- |
| インストール | 非オーガニック (UA) インストール |
| アプリ内イベント | 非オーガニックのアプリ内イベント |
| リターゲティングコンバージョンポストバック | リターゲティング（リエンゲージメントとリアトリビューション） |
| リターゲティングアプリ内イベント | リターゲティングアプリ内イベント |

<div id="additional-fields-in-postback-reports" />

#### ポストバックレポートの追加項目

| 項目 | 備考 |
| --- | --- |
| Postback URL | 収益など、一部の値は該当する項目に表示されない場合がありますが、**Postback URL**内で確認できます。 |
| Postback method |  |
| Postback HTTP response code | 200：広告ネットワークがポストバックを受信したことを示します。 |
| Postback error message |  |

</Accordion>

<div id="protect360-fraud-and-validation-rules" />

<Accordion title="Protect360と検証ルール">

* <Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports">Protect360</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/implement-validation-rules-to-prevent-fraud#outcomes">検証ルール</Anchor>のローデータレポートを参照してください。
* 広告ネットワークおよび代理店がProtect360と検証ルールのレポートにアクセスするには、広告主から<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#access-protect360-dashboard-raw-data">権限を付与</Anchor>してもらう必要があります。

**連携済みパートナーにProtect360へのアクセス権限を付与するには、以下の手順を実行します。**

1. **連携** > **Active Integrations**に移動します。
2. 該当の媒体を選択します。
3. **権限**タブにて、**Protect360管理画面とAPIでのローデータへのアクセスを許可する**をオンにします。
4. アプリ内イベント（CPA）ダッシュボードへのアクセスも許可する場合は、**アプリ内イベントの集計データへのアクセス**も有効にします。

</Accordion>

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview">集計レポートと分析について</Anchor>

<div data-zendesk-anchors="raw-data-reporting%E2%80%94tools-and-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB%E3%81%A8%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HE7SRDXQ9TR0CRB2JC9XCQE2=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB%E3%81%A8%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HE7SRDXQQJFMV9EJKPY34D00=%E3%83%92%E3%83%B3%E3%83%88 reporting-tools%E2%80%94characteristics-and-features=reporting-tools-characteristics-and-features h_01HE7SRDXQFJGMY05K1SV4TF63=reporting-tools-characteristics-and-features reporting-tools=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB h_01HE7SRDXQ647XRQ8QVMPGH43B=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB tool-limitations=%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AE%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HE7SRDXQWQAKR0G6CNKC5AMT=%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AE%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 integration-considerations=%E5%AE%9F%E8%A3%85%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 h_01HE7SRDXQN3HSMGAPBAX9S3MB=%E5%AE%9F%E8%A3%85%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 h_01HE7SRDXQRPD8MHC8M5916HTQ=report-fields user-journey-raw-data-field-groups=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%83%8B%E3%83%BC%E3%81%AE%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E9%A0%85%E7%9B%AE%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%97 h_01HE7SRDXQMGQEG1QWGWEESQER=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%83%8B%E3%83%BC%E3%81%AE%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E9%A0%85%E7%9B%AE%E3%82%B0%E3%83%AB%E3%83%BC%E3%83%97 user-journey-reports=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%83%8B%E3%83%BC%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HE7SRDXQZ50WMKCMYHZM7D92=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%83%8B%E3%83%BC%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HE7SRDXQFN0P9QK8SKAZKVKP=user-journey-basics h_01HE7SRDXRS2B12Z67MYMH0QN9=user-journey-report-availability user-journey-reports::d286e1f5=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%83%8B%E3%83%BC%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88-1 h_01HE7SRDXR7YQGWN4FNDXMNMX8=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%83%8B%E3%83%BC%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88-1 h_01HE7SRDXRK6G27SDFK3CGDCRC=user-journey-report-descriptions clicks-and-impressions=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%81%A8%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 h_01HE7SRDXRC9YKZ0P9ED0218SJ=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%81%A8%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 installs-and-retargeting-conversions=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 h_01HE7SRDXRN60XE5BSDQY28N71=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3 inapp-events=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HE7SRDXR3ZT39EDNW4MVZZTX=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 sessions=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 h_01HE7SRDXRY05XQCMZE6YPXGWQ=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3 uninstalls=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HE7SRDXRA7ESDD4ME51WWBPR=%E3%82%A2%E3%83%B3%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HE7SRDXRZYNFGK4CNP4VPAE0=user-journey-report-availability-per-tool ad-engagement-report-by-tool=%E5%BA%83%E5%91%8A%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB%E5%88%A5 h_01HE7SRDXR171M74HMQBZJ2E8R=%E5%BA%83%E5%91%8A%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB%E5%88%A5 user-acquisition-reports-by-tool=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB%E5%88%A5 h_01HE7SRDXRMGEP5QB452ZKQ8X7=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB%E5%88%A5 retargeting-raw-data-reports-by-tool=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB%E5%88%A5 h_01HE7SRDXRXR4J3HTMYW2P233Y=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%84%E3%83%BC%E3%83%AB%E5%88%A5 h_01HE7SRDXRWW3JKNESSN2QA4DV=faq h_01HE7SRDXR61K28JGA8944D6HV=install-report-tips h_01HE7SRDXRKFR2WYGNF317CTRX=%E4%BE%8B engaged-user%E2%80%94strong=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A8%E3%81%AE%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%81%8C%E5%BC%B7%E3%81%84%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC h_01HE7SRDXRW0CWHGQV75VF66DC=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A8%E3%81%AE%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%81%8C%E5%BC%B7%E3%81%84%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC engaged-user%E2%80%94weak=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A8%E3%81%AE%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%81%8C%E5%BC%B1%E3%81%84%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC h_01HE7SRDXRNMDZEJQ32665T14F=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A8%E3%81%AE%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E3%81%8C%E5%BC%B1%E3%81%84%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC analyzing-the-user-journey-for-campaign-optimization=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E6%9C%80%E9%81%A9%E5%8C%96%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%83%8B%E3%83%BC%E5%88%86%E6%9E%90 h_01HE7SRDXRRET0YN4Q8WYMENSR=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E6%9C%80%E9%81%A9%E5%8C%96%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%83%8B%E3%83%BC%E5%88%86%E6%9E%90 feature-reports=%E6%A9%9F%E8%83%BD%E5%88%A5%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HE7SRDXSVAHKBYQK0C71K6AR=%E6%A9%9F%E8%83%BD%E5%88%A5%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HE7SRDXSFWMVY61NBYFQ4XSM=postbacks postback-reports-available-via-the-export-data-page-and-pull-api=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88export-data%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%8A%E3%82%88%E3%81%B3pull-api%E3%81%8B%E3%82%89%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD h_01HE7SRDXS6T4M4CRQN0ZTJETR=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88export-data%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%8A%E3%82%88%E3%81%B3pull-api%E3%81%8B%E3%82%89%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD additional-fields-in-postback-reports=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E8%BF%BD%E5%8A%A0%E9%A0%85%E7%9B%AE h_01HE7SRDXSYBDG0H2QEYBFWSRH=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E8%BF%BD%E5%8A%A0%E9%A0%85%E7%9B%AE h_01HE7SRDXS8K4MB76WVBCBHASQ=protect360-fraud-and-validation-rules h_01HE7ST20N8ZBFNY2QXW5G44A1=%E5%8F%82%E7%85%A7" />
