---
title: Protect360｜不正対策ガイド
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - p360
    - p 360
    - 360protect
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2016-12-06T07:47:17Z'
  edited_at: '2026-10-28T08:58:37Z'
  id: 218254203
  locale: ja
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ja/articles/218254203
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** アトリビューション不正は、マーケティング予算を浪費させ、成果データの正確性を損ない、好調なキャンペーンを赤字に転じさせるおそれがあります。 **Protect360は、アプリ所有者にリアルタイムの不正対策と、ポストアトリビューションでの不正検知（アトリビューション後の不正検知）を提供します。**

![p360intro2.jpg](https://files.readme.io/c8476382eeff62164ca93b9bf2f3c4cdbe0609d4160047eac36a44d5f333ffdb-360014803578.jpg)

<div id="protect360-overview" />

## Protect360の概要

* アトリビューション不正から保護します。不正を検知し、不正なアトリビューションをブロックする、状況に応じて機能する各種ツールで構成されています。
* AppsFlyerの大規模なデータ、機械学習、行動分析を活用し、ボットや行動の異常を含む、既知の不正や新しい手法によるクリック／インストール不正から保護します。
* デバイス、パブリッシャー、メディアソースの各単位で、マーケターを不正から保護します。
* リアルタイムの不正ブロックと、ポストアトリビューションでの不正特定を組み合わせた、多段階の対策を行います。
* アプリのユーザー体験には影響しません。実際のユーザーが関わる不正の試みでも、アプリのインストールは通常どおり完了し、影響するのはアトリビューションの記録のみです。

<div id="realtime-blocking" />

<Accordion title="リアルタイムのブロック">

* アトリビューション前に、インストールが不正なメディアソースからのものとリアルタイムで判定され、アトリビューションがブロックされます。
* 同じユーザーによる、その後のアプリ内イベントもブロックされます。
* ブロックされたインストールとアプリ内イベントは、Protect360ダッシュボードと、ブロックされた不正のレポートに表示されます。
  * ブロックされたインストールとアプリ内イベントは、一度もアトリビューションされていないため、AppsFlyerのアトリビューションデータやダッシュボードには含まれません。
* ブロックされたインストールのポストバックは、ブロック理由とともにメディアソースへ送信され、最適化に役立てられます。

<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports">ブロックされたイベントについて</Anchor>

</Accordion>

<div id="postattribution-detection" />

<Accordion title="ポストアトリビューションでの不正検知">

* アトリビューション後に判明した不正を「ポストアトリビューション不正」と呼びます。ポストアトリビューション不正は、インストール当日から、その7日後までの計8日間に検知できます。
* 一度アトリビューションされたインストールは、削除できません。そのため、ポストアトリビューション不正は、リアルタイムで検知した不正とは異なる方法で処理されます。
* 後から不正と判明したインストールやアプリ内イベントも、実際の不正として扱い、請求対象から除外する必要があります。

アドネットワークやサイトIDなどの流入元が不正と判定されると：

* その流入元からの以後のクリックがブロックされます。
* 過去のインストール：
  * 当月の初日から現在までのインストールは、ポストアトリビューション不正としてマークされますが、**データから削除されません**。 2020年1月以降、これらのインストールに対するアトリビューション料金は、広告主への請求額から差し引かれます。
  * 当月より前のインストールは変更されません。
* アプリ内イベント：

  * インストールが不正としてマークされる**まで**に発生したイベント：不正としてマークされます。
  * インストールが不正としてマークされた**後**に発生したイベント：不正としてマークされます。

  注意：ユーザー獲得（UA）の再インストールが不正と判定された場合、Protect360はそのインストールをオーガニックに付け替え、アトリビューションを修正します。そのため、これらの再インストールに続くアプリ内イベントもオーガニックに紐づけられ、オーガニックのアプリ内イベントレポートに表示されます。

ポストアトリビューション不正の例：

* 一見正常なインストールの後、アプリ内イベントに不正の兆候が見つかる場合
* 新しい不正手法が見つかった場合
* 異常検知アルゴリズムがパブリッシャーのインストールに関する十分な統計データを収集して初めて、不正と判明するインストール

</Accordion>

<div id="common-fraud-issues-and-solutions" />

<Accordion title="主な不正と対策">

AppsFlyerが不正を特定すると、関連する**アトリビューションイベント**がブロックされます。これにより、不正行為者の利益と不正を行う動機をなくします。**注意**：アプリのインストール自体はブロックされず、実行されます。ユーザーはアプリを利用でき、広告主の収益につながる行動も行えます。

ブロックされた不正なクリック、インストール、アプリ内イベントは、<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports">Protect360不正ローデータレポート</Anchor>で確認できます。

次の表では、不正の種類とProtect360による対処方法を説明します。

| 不正の種類 | 説明 | AppsFlyerによる対策 |
| --- | --- | --- |
| <span id="device-id-reset-fraud"></span>**デバイスIDのリセットによる不正** | 不正行為者が同じ物理デバイスのデバイスIDを繰り返しリセットし、大量のインストールを発生させます。 | AppsFlyerは新規デバイスの割合の異常を検知し、それらを送信する流入元を拒否リストに登録します。 |
| <span id="install-hijacking"></span>**インストールハイジャック** | 不正行為者は、アプリのダウンロードを検知して通知するマルウェアをモバイルデバイスに仕込みます。ダウンロードの検知直後にAppsFlyerへクリックを送信し、そのインストールの成果を不正に獲得しようとします。 | CTIT（<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-to-install-time-ctit/">クリックからインストールまでの時間</Anchor>）が極端に短いクリックをブロックします。また、Google PlayのサーバーサイドAPIに基づいてブロックします。 |
| <span id="click-hijacking"></span><Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-hijacking/">**クリックハイジャック**</Anchor> | マルウェアがインストールのアトリビューションリンクへのクリックを検知し、即座に別のクリックを送信します。そのクリックに成果が紐づくと、不正行為者が成果を獲得します。 | 同じデバイス・同じアプリへの別のクリックの直後に発生し、成果が紐づけられたクリックをブロックします。 |
| <span id="click-flooding"></span><Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-flooding/">**クリック洪水**</Anchor> | インストール直前のラストクリックを獲得する目的で、大量の偽クリックを送信するモバイル広告不正です。 | コンバージョン率が低く、CTITが長いサイトIDからの、成果が紐づけられたクリックをブロックします。 |
| <span id="behavioral-anomalies"></span>**行動の異常** | 不正行為者が、インストール後に一貫性のない異常な行動を発生させるモバイル広告不正です。 | AppsFlyer独自の大規模なデータを使って、アプリ、地域、メディアソース、パブリッシャーなど、さまざまな単位でユーザー行動のパターンを追跡・把握できます。人間の行動とは考えにくいパターンをほぼリアルタイムで特定し、流入元でブロックします。 |
| <span id="ip-denylists"></span>**IP拒否リスト** | 不正行為者は通常、<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-farms/">不正クリックを大量に発生させる拠点</Anchor>から活動しており、そのIPアドレスから長期にわたって特定できる場合があります。 | <ul><li>第三者のグローバルプロバイダーである<Anchor target="_blank" href="http://www.digitalelement.com/">Digital Element</Anchor>から受け取る最新データを基に、不正が疑われるIPアドレスを日次で拒否リストに登録します。</li><li>IP拒否リストによる保護は、すべてのアプリで有効です。</li></ul> |
| <span id="sdk-authentication"></span>**SDK認証** | 不正行為者が偽のSDKメッセージを送信し、価値のあるユーザー行動が発生したように見せかけます。 | <ul><li>独自のハッシュ化プロトコルを使用してSDKとWebサービス間のメッセージを暗号化し、不正行為者によるメッセージの偽装を防ぎます。</li><li>SDK認証による保護は、すべてのアプリで有効です。</li></ul> |
| <span id="store-validations"></span>**ストアでの検証** | 不正行為者が偽のSDKメッセージを送信し、インストールやアプリ内購入が発生したように見せかけ、高額なCPA報酬を請求します。 <Anchor target="_blank" href="/marketers/ja/docs/implement-apple-app-store-itunes-install-validation">Appleストアでの検証</Anchor>。 | 不正な行動へのアトリビューションを防ぐため、実際に発生したインストールやアプリ内購入について、iTunesでの<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/install-validation/">インストール検証</Anchor>と、iTunesおよびGoogle Playでのアプリ内購入の検証を行えます。 |

**注意**：お客様を保護するため、上記の判定に使用する具体的な時間の値は公開していません。

その他のブロック理由については、<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports">ローデータの記事</Anchor>で説明しています。

</Accordion>

次の表では、不正なインストールとアプリ内イベントの種類、およびProtect360エンジンがリアルタイムでブロックした場合とポストアトリビューションで検知した場合の処理を示しています。

<table><thead><tr><th>不正の種類</th><th>検知のタイミング</th><th>インストールの処理</th><th>アプリ内イベントの処理</th></tr></thead><tbody><tr><td rowspan="2"><span>偽のインストール</span></td><td><span>リアルタイム</span></td><td><span>リアルタイムでブロック</span></td><td><span>リアルタイムでブロック</span></td></tr><tr><td><span>ポストアトリビューション</span></td><td><span>ポストアトリビューションインストールレポートに不正として表示</span></td><td><ul><li><span>不正検知前に発生したアプリ内イベントは、ポストアトリビューションアプリ内イベントレポートに不正として表示されます。</span></li><li><span>検知後：リアルタイムでブロック</span></li></ul></td></tr><tr><td rowspan="2"><span>インストールアトリビューションハイジャック</span></td><td><span>リアルタイム</span></td><td><ul><li><span>リアルタイムでブロック</span></li><li><span>最後の有効な流入元にアトリビューションを修正</span></li></ul></td><td><ul><li><span>ローデータレポートには表示されず、ダッシュボードでのみ確認可能</span></li><li><span>インストールと同じ有効な流入元に紐づけ</span></li></ul></td></tr><tr><td><span>ポストアトリビューション</span></td><td><span>ポストアトリビューションインストールレポートに不正として表示</span></td><td><ul><li><span>不正検知前に発生したアプリ内イベントは、ポストアトリビューションアプリ内イベントレポートに不正として表示されます。</span></li><li><p>不正検知後：インストールから30日後まで、ポストアトリビューションアプリ内イベントレポートに不正として表示。\*</p><p>\*インストールから30日間は、アプリ内イベントを最後の有効なメディアソースに付け替えます。 30日を過ぎて発生したイベントは修正されません。</p></li></ul></td></tr><tr><td rowspan="2"><span>不正なアプリ内イベント</span></td><td><span>リアルタイム</span></td><td>-</td><td><span>リアルタイムでブロック</span></td></tr><tr><td><span>ポストアトリビューション</span></td><td>-</td><td><span>ポストアトリビューションアプリ内イベントレポートに不正として表示</span></td></tr></tbody></table>

Protect360の不正検知と処理

<div id="using-protect360" />

## Protect360の利用方法

<div id="dashboard" />

<Accordion title="ダッシュボード">

<Anchor target="_blank" href="/marketers/ja/docs/protect360-dashboard">Protect360ダッシュボード</Anchor>には不正の集計データが表示され、不正なトラフィックの状況を把握できます。

ダッシュボードの表示：

**インストール**：リアルタイムでブロックされたものと、ポストアトリビューションで判明した不正なインストールを、<Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTVベース</Anchor>で把握できます。フィルタやグループ化を使って詳細を絞り込み、不正なイベントを詳しく調べられます。

**アプリ内イベント**：リアルタイムでブロックされたものと、ポストアトリビューションで判明した不正なアプリ内イベントを、<Anchor target="_blank" href="/marketers/ja/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">アクティビティベース</Anchor>で把握できます。フィルタやグループ化を使って詳細を絞り込み、不正なイベントを詳しく調べられます。

</Accordion>

<div id="raw-data" />

<Accordion title="ローデータ">

不正に関する<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports">ローデータ</Anchor>は、Pull API、データ出力、<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">Data Locker（プレミアム機能）</Anchor>で利用できます。

ローデータレポートは、次のように分類されます。

* ブロックされたデータのレポート：アトリビューションがブロックされ、どのメディアソースにも紐づけられなかったユーザーのインストール、クリック、アプリ内イベント。
* ポストアトリビューションレポート：
  * メディアソースに紐づけられた後に、不正と判明したインストール。
  * アプリ内イベント：
    * メディアソースに紐づけられた後に不正と判明したインストールに関連するイベント。
    * インストール自体の判定とは関係なく、不正と判定されたイベント。

* 広告主は、これらのレポートをアドネットワークとの広告費の精算、最適化、ポストアトリビューション不正を考慮したアトリビューションダッシュボードの調整に使用できます。

</Accordion>

<div id="validation-rules" />

<Accordion title="検証ルール">

<Anchor target="_blank" href="/marketers/ja/docs/implement-validation-rules-to-prevent-fraud">検証ルール</Anchor>を使うと、アプリ所有者は、特定のインストールのブロック、アトリビューションのブロック（最後の有効なメディアソースへインストールを付け替え）、アプリ内イベントのブロックを行う条件を設定できます。

</Accordion>

<div id="fraud-reconciliation-with-ad-networks" />

<Accordion title="アドネットワークとの不正分の広告費の精算">

Protect360を使うと、アドネットワーク側で不正として記録されていない可能性のあるインストールやアプリ内イベントについても、ローデータを取得できます。

不審な流入元からアドネットワークがトラフィックを送信していることが分かった場合は、アドネットワークに連絡し、その流入元からの送信を停止するよう依頼してください。インストールのローデータレポートの<strong>アトリビューション対象の広告接触時刻（Attributed Touch Time）</strong>列を使って、停止依頼後にその流入元からインストールが発生していないことを確認してください。

Protect360のデータを使ってアドネットワークと精算し、不審な流入元からの過去のトラフィックについて、全額または一部の返金を受けることもできます。

**Protect360を使ったCPI課金キャンペーンの精算手順：**

* 毎月の初めに、不正が発生した各アドネットワークのアカウント担当者へ連絡します。
* ブロックされたインストールと[ポストアトリビューションインストール](/docs/protect360-anti-fraud-guide#postattribution-detection)のレポートから、該当する不正インストールのローデータを取得します。
* 不正のローデータをアドネットワークに共有し、広告費の精算とトラフィックの最適化に活用します。
* ポストアトリビューション不正のインストールを除き、有効なインストールのみを含むローデータレポートを作成することもできます。月次の***アトリビューションされたUAインストール***レポートをダウンロードし、***ポストアトリビューションインストール***レポートに含まれるすべてのレコードを除外します。

**Protect360を使ったCPA／CPE課金キャンペーンの精算手順：**

* 毎月の初めに、不正が発生した各アドネットワークのアカウント担当者へ連絡します。
* ブロックされたアプリ内イベントと[ポストアトリビューション](/docs/protect360-anti-fraud-guide#postattribution-detection)アプリ内イベントのレポートから、該当する不正なアプリ内イベントのローデータを取得します。
* 不正のローデータをアドネットワークに共有し、広告費の精算とトラフィックの最適化に活用します。
* ポストアトリビューション不正のイベントを除き、有効なアプリ内イベントのみを含むローデータレポートを作成することもできます。月次の***アトリビューションされたUAアプリ内イベント***レポートをダウンロードし、***ポストアトリビューションアプリ内イベント***レポートに含まれるすべてのレコードを除外します。

</Accordion>

<div id="traits-and-limitations" />

## 仕様と制限事項

<div id="traits-and-limitations::a07033c3" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| 広告主のアクセス | すべてのアカウントユーザー。 |
| アドネットワークのアクセス | <ul><li>Protect360ダッシュボードとローデータへのアクセスには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#アドネットワークの権限">広告主の許可</Anchor>が必要です。</li><li>広告主が、そのアドネットワークを連携済みパートナーとして設定している必要があります。</li></ul> |
| 代理店のアクセス | Protect360ダッシュボードとローデータへのアクセスには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#アドネットワークの権限">広告主の許可</Anchor>が必要です。 |
| 運用媒体の開示設定 | 運用媒体を開示している代理店：個々のメディアソースを確認できます。<br /><br />運用媒体を開示していない代理店：個々のメディアソースを確認できません。 |
| アプリ固有のタイムゾーン | <ul><li>すべてのアプリが同じタイムゾーンに設定されている場合、ダッシュボードにはアプリ固有のタイムゾーンが適用されます。</li><li>アプリのタイムゾーンが異なる場合、ダッシュボードはUTCで表示されます。</li></ul> |
| データの更新頻度 | <ul><li>Protect360ダッシュボード：<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#eod">日次</Anchor>で更新。<br />ダッシュボードの日付範囲フィルタの下に、最新の更新時刻が表示されます。</li><li>レポート：<ul><li>ブロックされたインストールとアプリ内イベント：ほぼリアルタイムで継続的に更新。</li><li>ポストアトリビューション：UTCに基づき<Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#eod">日次</Anchor>で更新。</li></ul></li></ul> |
| 再インストール | 再インストールの不正データは、ローデータでのみ確認できます。そのため、ダッシュボードとローデータレポートの合計値に差異が生じる場合があります。 |
| リターゲティング | <ul><li>不正と判定されたインストールについて、インストール、リアトリビューション、リエンゲージメントに分けた、アトリビューション対象の広告接触の種類別の内訳が表示されます。</li><li>アプリ内イベント：<ul><li>アプリ内イベント（CPA）ダッシュボードには、UAインストールに関連する不正イベントが表示されますが、リターゲティングのイベントは表示されません。</li><li>リアトリビューションに関連する不正イベントのうち、リアルタイムで検知されたものは、ローデータレポートで確認できます。リエンゲージメントに関連する不正イベントは検知できません。</li><li>リターゲティングに関連する不正イベントは、ポストアトリビューションでは検知できません。</li></ul></li></ul> |
| 制限事項 | <ul><li>表の表示は最大20,000行です。</li><li>これを超えるデータを取得しようとすると、一部のメディアソースが除外される可能性があります。この制限を回避するには、次の方法を推奨します。<ul><li>日付範囲を短くする、アプリやメディアソースを指定するなどして、取得対象のデータを絞り込む</li><li>Protect360の<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports">ローデータレポート</Anchor>を出力する</li><li>Protect360の高度な不正検知の集計レポートを<Anchor target="_blank" href="/marketers/ja/docs/pull-api-aggregate-data">Pull APIで出力する</Anchor></li></ul></li></ul> |

仕様と制限事項

</Accordion>

<div id="faq-and-tips" />

## よくある質問とヒント

<div id="faq" />

<Accordion title="よくある質問">

| **Protect360は、カスタムアトリビューションリンクからの不正にも対応していますか？**<br /><br />はい、対応しています。 Protect360は、アドネットワークからの不正に加えて、カスタムアトリビューションリンクからの不正も検知・ブロックします。そのため、インフルエンサー、メール・SMSキャンペーン、Webサイトのバナーやランディングページ、SNSで拡散される投稿、プッシュ通知、QRコードなど、自社で管理する媒体を使ったキャンペーンも保護されます。 |
| --- |
| **Protect360 V2は、V1と比べて何が変わりましたか？**<ol><li>P360 V2.0には主に3つの変更があります。<br />ポストアトリビューション不正：ブロックされたインストールを表示するすべての箇所で、ポストアトリビューション不正のインストールも表示します。ポストアトリビューションのデータは、ローデータレポートでも利用できます。</li><li>異常の分析：「異常の分析」という新しいセクションが追加され、広告主は可視化ツールを使って異常を分析できます。旧「高度な不正検知」タブの2つのグラフに代わるものです。</li><li>不正データの集約：「高度な不正検知」タブを廃止し、すべての情報を1つのタブに集約しています。</li></ol> |
| **ポストアトリビューションのローデータが、データ出力ページで利用できないのはなぜですか？**<br /><br />広告費の精算を行いやすくするため、ポストアトリビューションレポートはアカウント単位で、メディアソース別に提供されています。**データ出力**ページはアプリ単位です。従来の利用方法との互換性を維持するため、アプリ単位のブロックされた不正データが引き続き含まれています。 |
| **ポストアトリビューションのデータは、過去にさかのぼって更新されますか？**<ul><li>**インストール**：概要ページと、Protect360ダッシュボード以外のすべてのレポートのインストールデータは、過去にさかのぼって更新されません。</li><li>**アプリ内イベント**：ポストアトリビューションの不正対策でインストールが偽と判定されると、そのインストールに紐づく以後のアプリ内イベントがブロックされます。それ以前のアプリ内イベントは、過去にさかのぼって更新されません。</li></ul> |
| **「異常の分析」で特定のアドネットワークを選択したり、選択を変えたりすると、データの見え方が変わるのはなぜですか？**<br /><br />CTITの異常を確認する際、AF\_Baselineを比較基準に選択すると、アドネットワークAの異常が表示される場合があります。そこで、例えばアドネットワークAを比較基準にすると、他のアドネットワークの異常が表示され、Aの異常は表示されなくなります。<br /><br />これは想定どおりの動作です。信頼できるAppsFlyerの基準値を使うと、CTITの割合に異常があるアドネットワークが表示されます。異常のあるアドネットワークを比較基準にすると、そのアドネットワークのインストールは異常として扱われなくなり、他のアドネットワークのインストールが、その基準に対して異常とみなされる場合があります。 |
| **異常なオーガニックトラフィックは、実際に不正なのでしょうか？**<br /><br />オーガニックトラフィックが異常に急増した場合、不正の可能性があります。 AppsFlyerに表示されるオーガニックトラフィックに、不正と思われる根拠がある場合、一般に次の3つのケースが考えられます。<ul><li>**アトリビューション不正の失敗：** 不正行為者のクリックに成果が紐づかなかった場合です。例えば、クリック洪水で最後のクリックがクリックのルックバック期間外に発生した場合などです。</li><li>**アトリビューションとは無関係な不正：** ユーザーが計測とは無関係な不正を行う場合です。例えば、戦略ゲームでアイテムを不正に獲得する場合などです。</li><li>**SDK実装の問題：** アプリ内イベントが、利用の流れに沿った適切なタイミングで、正しいイベントパラメータの値を使って送信されているかを確認してください。</li></ul> |

よくある質問

</Accordion>

<div id="benchmarks-and-tips" />

<Accordion title="判断の目安とヒント">

| <strong>新規デバイスを使った不正の検知</strong><br /><br />不正行為者は、デバイスの主要な識別子（iOSのIDFA、AndroidのGAID）を頻繁にリセットして、デバイスを偽装することがあります。<br /><br />AppsFlyerは、世界のモバイルデバイスの98%以上を識別しています。<br /><br />そのため、新規デバイスを意図的にターゲットにしている場合を除き、未識別の新規デバイスの割合が高いことは、不正クリックを大量に発生させる拠点による不正の有力な兆候です。<br /><br /><strong>新規デバイスの確認手順：</strong><ol><li>Protect360で、<strong><em>検知された不正の内訳</em></strong>の表を開きます。</li><li>右にスクロールして、<strong><em>大量の端末を使った不正の指標 - 新規デバイス</em></strong>の列を表示します。</li><li><strong><em>インストールの割合（%）</em></strong>の列名をクリックし、新規デバイスの割合が高い順に並べ替えます。</li><li>新規デバイスによる不正の兆候：</li></ol><ul><li><strong>新規</strong>デバイスの割合が高い流入元。<strong>注意</strong>：インストール数が多い場合は、割合が低くても不正の可能性があります。全体の件数が多くなるためです。<ul><li>その流入元のロイヤルユーザー率が、全体のロイヤルユーザー率よりも低い場合は、不正の有力な兆候です。</li></ul></li></ul><strong>注意</strong>：<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-factory-preinstall-using-manifest-android">プリインストールアプリ</Anchor>のキャンペーンは、新規デバイスの割合が通常、非常に高くなります。新しいデバイスを使い始めたユーザーが、最初に起動するアプリの1つになりやすいためです。そのため、プリインストールアプリでは、新規デバイスの割合が高くても、新規デバイスを使った不正の可能性は低くなります。 |
| --- |
| <strong>LATを利用した不正の検知</strong><br /><br />LAT（広告トラッキング制限）を選択したユーザーは、広告主にデバイスID（IDFAやGAID）を公開しない設定にしています。 iOSユーザーの約15%、Androidユーザーの約10%が、この設定を選択しています。<br /><br />新規デバイスの場合と同様に、LATユーザーも正常なユーザーである可能性があります。ただし、その割合が高い場合は、不正の兆候となることがあります。<br /><br /><strong>LATの確認手順：</strong><ol><li>Protect360で、<strong><em>検知された不正の内訳</em></strong>の表を開きます。</li><li>右にスクロールして、<strong><em>大量の端末を使った不正の指標 - LATデバイス</em></strong>の列を表示します。</li><li><strong><em>インストールの割合（%）</em></strong>の列名をクリックし、LATデバイスの割合が高い順に並べ替えます。</li><li>LATデバイスによる不正の兆候：</li></ol><ul><li><strong>LAT</strong>デバイスの割合が高い流入元。<strong>注意</strong>：インストール数が多い場合は、割合が低くても不正の可能性があります。全体の件数が多くなるためです。</li><li>その流入元のロイヤルユーザー率が、全体のロイヤルユーザー率よりも低い場合は、不正の有力な兆候です。</li></ul> |
| <strong>クリック洪水の不正検知</strong><ol><li>クリック洪水では、不正行為者が実際のデバイスIDを使って数百万件のクリックを送信し、実際のユーザーのラストクリックとして記録されることを狙います。この不正がある流入元は、<strong>コンバージョン率が非常に低い一方、ユーザーの質は高くなります</strong>。ユーザー自体は実在するためです。</li></ol><strong>クリック洪水の確認手順：</strong><ol><li>Protect360で、<strong><em>検知された不正の内訳</em></strong>の表を開きます。</li><li>右にスクロールして、<strong><em>クリック洪水の指標</em></strong>の列を表示します。</li><li><strong><em>コンバージョン率</em></strong>の列名をクリックし、コンバージョン率が低い順に並べ替えます。</li><li>クリック洪水の判断の目安：</li></ol><ul><li>正常な<strong><em>コンバージョン率</em></strong>は、0.5%～35%です。<br />コンバージョン率が異常に低い流入元や、<strong>アプリの平均コンバージョン率の25%以下</strong>の流入元は、不正が疑われます。このKPIは、概要ダッシュボードのパフォーマンス集計レポートの表で確認できます。</li><li>判断が難しい流入元は、<strong><em>アシストの割合（%）</em></strong>を平均アシスト率と比較します。正常なアシスト率は、概要ダッシュボードのアシストウィジェットで確認できます。<br />アシスト率がアプリの平均より<strong>50%高い</strong>流入元は、不審とみなされます。<br />アプリが利用する流入元が多いほど、貢献率も高くなる点に注意してください。</li></ul> |
| **CTITの指標を使ったクリック洪水の検知**<br /><br />クリック洪水の別の兆候として、**CTITの分布が均一になること**が挙げられます。<br />通常、正常なインストールの約70%は、広告接触から1時間以内に発生します。<br />クリック洪水では、偽の広告接触と実際のインストールに関連性がありません。そのため、CTITが1時間を超える不正インストールの割合は、30%を大きく上回ります。<br /><br />**クリック洪水のCTITの確認手順：**<ol><li>Protect360で、***検知された不正の内訳***の表を開きます。</li><li>右にスクロールして、***クリック洪水の指標*** ***- CTIT***の列を表示します。</li><li>クリック洪水のCTITの判断の目安：</li></ol><ul><li>通常、***60分超***の割合は約30%です。この指標が50%を超える流入元は、不正が疑われます。</li><li>通常、***5時間超***の割合は約20%です。この指標が40%を超える流入元は、不正が疑われます。</li></ul>CTITが不審な流入元は、***異常の分析***<Anchor target="_blank" href="/marketers/ja/docs/protect360-dashboard#anomalies-dashboard">ページ</Anchor>で詳しく調べてください。 |

判断の目安とヒント

</Accordion>

<div id="advanced-antifraud-tips" />

<Accordion title="不正対策を強化するためのヒント">

| **インストール数**<br /><br />大規模な不正の流入元を見つけるには、調査対象の流入元ごとのインストール数で絞り込むことが重要です。また、インストール数が少ないと、統計的に意味のある結果が得られない場合があります。注意：<br /><br />**注意**：インストール数が30件未満、あるいは50件未満の流入元では、結論を出すのに十分なデータがありません。日付範囲やその他の検索条件を広げて、判断に十分なデータを取得してください。 |
| --- |
| **ロイヤルユーザーの定義の変更**<br /><br />ロイヤルユーザー（継続的に利用するユーザー）のデフォルトの定義は、アプリを3回以上起動したユーザーです。これはユーザーの利用状況を把握する重要なKPIですが、多くの不正行為者もこの定義を知っており、ロイヤルユーザー率を高く見せかけて、不正を疑われないようにします。より適切で複数の条件を組み合わせたロイヤルユーザーの定義を作成・選択し、こうした偽装を防いでください。<br /><br />登録、チュートリアル完了、購入、複数回のセッションなど、ユーザーの質を示すKPIを分析します。ユーザーが一覧のすべてのKPIを満たした場合に、新しい**ロイヤルユーザー**のアプリ内イベントを送信するよう、アプリのコードに実装します。<br /><br />最初の非オーガニックの**ロイヤルユーザー**イベントが送信されたら、**アプリ設定**でそのイベントを選択し、ロイヤルユーザーの判定に使用します。全体のロイヤルユーザー率は少し下がり、不正な流入元では大幅に下がることが想定されます。 |

不正対策を強化するためのヒント

</Accordion>

<div id="tip" />

> 👍 **ヒント**
>
> 不正対策について、さらに詳しく知りたいですか？ AppsFlyerラーニングポータルの<Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7809/play/18635/mobile-app-fraud-and-protect360">短時間で学べるコース</Anchor>をご覧ください。

<div id="see-also" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports">ローデータ</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/marketers-guide-mobile-ad-fraud/">マーケター向けモバイル広告不正の入門ガイド</Anchor>

<div data-zendesk-anchors="protect360-overview=protect360%E3%81%AE%E6%A6%82%E8%A6%81 h_01HE7RSPPQ4T5J3W038EZRCTCE=protect360%E3%81%AE%E6%A6%82%E8%A6%81 h_01HE7RSPPQ5BH7HBK0R8SY1T16=realtime-blocking h_01HE7RSPPRW4CQ3GB9ZEYAA6YN=postattribution-detection h_01HE7RSPPRYMQKJH46JET2ZZ0T=common-fraud-issues-and-solutions using-protect360=protect360%E3%81%AE%E5%88%A9%E7%94%A8%E6%96%B9%E6%B3%95 h_01HE7RSPPR8Y8J1VJJXXDCAZE6=protect360%E3%81%AE%E5%88%A9%E7%94%A8%E6%96%B9%E6%B3%95 h_01HE7RSPPR04G3SCSYHSWJKQDG=dashboard h_01HE7RSPPRS6PSTZCR5RT4A5ND=raw-data h_01HE7RSPPR8C9MHRAGJXYD2VVZ=validation-rules h_01HE7RSPPR1PQ2R6NJPRQGS1K1=fraud-reconciliation-with-ad-networks traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HE7RSPPRV797PS12NFQHX1X5=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HE7RSPPRWRKR1Y25PZV2RMVV=traits-and-limitations::a07033c3 faq-and-tips=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F%E3%81%A8%E3%83%92%E3%83%B3%E3%83%88 h_01HE7RSPPSV2TT8SMK8JZXFKMC=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F%E3%81%A8%E3%83%92%E3%83%B3%E3%83%88 h_01HE7RSPPS01J796008HDS1CRW=faq h_01HE7RSPPS018W98JWZGED54W8=benchmarks-and-tips h_01HE7RSPPSEDZWRH929DBSWEWM=advanced-antifraud-tips h_01HE7RSPPSY161MSQVQW7M767F=%E3%83%92%E3%83%B3%E3%83%88 h_01HE7RX6167Q5QP5JNZDSXCCK5=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />
