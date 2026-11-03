---
title: Data Lockerの広告主様向けレポート
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-11-11T09:48:51Z'
  edited_at: '2026-10-14T09:39:05Z'
  id: 4410643856657
  locale: ja
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/ja/articles/4410643856657
---
> **概要：** Data Locker 経由で利用可能な集計／ローデータレポート

## 広告主向け：Data Lockerで提供されるレポート一覧

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th>データタイプ</th><th>レポートグループ</th><th>Data Lockerの有償契約が必要</th></tr></thead><tbody><tr><td>ローデータ</td><td>ユーザージャーニー／ローデータ</td><td>はい (2)</td></tr><tr><td>ローデータ</td><td>Protect360</td><td>はい</td></tr><tr><td>ローデータ</td><td>ピープルベースアトリビューション（PBA） </td><td>いいえ </td></tr><tr><td>ローデータ</td><td>Incrementality</td><td>いいえ </td></tr><tr><td>ローデータ</td><td>SKAN</td><td>いいえ (1)</td></tr><tr><td>ローデータ</td><td>収益</td><td><p>広告収益（単一バージョン）レポートは Data Locker の有償契約が必要</p><p>その他の収益レポートは、ROI360 Advanced パッケージの契約が必要</p></td></tr><tr><td>ローデータ</td><td>CTV、PC、コンソールアプリ</td><td>はい</td></tr><tr><td>集計レポート</td><td>コホート分析</td><td>いいえ (1)</td></tr><tr><td>アドバンス集計レポート</td><td>コホート分析</td><td>いいえ (3)</td></tr><tr><td>集計レポート</td><td>Creative Optimization</td><td><p>いいえ (1)</p><p>Creative Optimization Premium プランの契約が必要</p></td></tr><tr><td>集計レポート</td><td>SSOT</td><td>いいえ (1)</td></tr><tr><td colspan="3"><p>(1) Data Locker を契約していない場合、<a href="./data-locker-for-marketers#storage-options" target="_blank">お客様が所有するストレージ</a>を用意する必要あり</p><p>(2) クロスプラットフォームエンゲージメントは対象外</p><p>(3) Data Locker の契約、または Analytics API Suite で利用可能</p></td></tr></tbody></table>

<div id="data-freshness-explanations" />

<Accordion title="データ更新頻度">

Data Lockerのレポート提供タイミングは、レポートの種類によって異なります。レポートに応じて、毎時、日次、またはバージョン管理のいずれかの更新頻度でデータが提供されます。これらの更新頻度がData Lockerのフォルダ階層にどのように対応しているかについては、「<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#folder-structure">フォルダ構造</Anchor>」を参照してください。

| データの更新頻度 | 説明 | レポート例 |
| --- | --- | --- |
| 毎時 | AppsFlyerがデータを受信するたびに更新され、時間単位の`h`フォルダへ出力されるレポートです。 | <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">アプリ内イベントレポート</Anchor> |
| 日毎 | 日中に継続的に更新されるのではなく、1日1回生成されるレポートです。 | <Anchor target="_blank" href="/marketers/ja/docs/measure-uninstalls">アンインストールレポート</Anchor> |
| バージョン管理 | 同一日のデータが、より新しい、またはより完全なデータの取得に応じて複数回出力されるレポートです。最新バージョンが最も正確なデータとなります。 | <Anchor target="_blank" href="/marketers/ja/docs/revenue-etl-reports#ad-revenue-versioned">アトリビューション済み広告収益レポート</Anchor> |

</Accordion>

## ローデータレポート

<div id="user-journey" />

<Accordion title="ユーザージャーニー">

レポートタイプの説明については、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ユーザージャーニーレポート</Anchor>を参照してください。

| カテゴリ | レポートの種類 (トピック) | データ更新頻度 | オーガニック／非オーガニック | Data Locker経由のみ |
| --- | --- | --- | --- | --- |
| ユーザー獲得 | クリック | 1-3時間 | N/A | ✓ |
| リターゲティング | クリック | 1-3時間 | N/A | ✓ |
| ユーザー獲得 | インプレッション | 1-3時間 | N/A | ✓ |
| リターゲティング | インプレッション | 1-3時間 | N/A | ✓ |
| ユーザー獲得 | インストール | 1-3時間 | 両方 |  |
| ユーザー獲得 | アプリ内イベント | 1-3時間 | 両方 |  |
| ユーザー獲得 | 非オーガニックインストールに紐づくアプリ内広告収益 | Daily+1 | 非オーガニック |  |
| ユーザー獲得 | オーガニックインストールに紐づくアプリ内広告収益 | Daily+1 | オーガニック |  |
| リターゲティング | リターゲティング成果に紐づくアプリ内広告収益 | Daily+1 | 非オーガニック |  |
| リターゲティング | リエンゲージメント / リアトリビューション | 1-3時間 | 非オーガニック |  |
| リターゲティング | アプリ内イベント | 1-3時間 | 非オーガニック |  |
| リターゲティング | セッション（アプリ起動） | 1-3時間 | 両方 | ✓ |
| ユーザー獲得 | セッション（アプリ起動） | 1-3時間 | 両方 | ✓ |
| ユーザー獲得 | アンインストール | Daily - アンインストール | 非オーガニック |  |
| ユーザー獲得 | オーガニックアンインストール | Daily - アンインストール | オーガニック |  |
| 再インストール | 再インストール | 1-3時間 | 非オーガニック |  |
| 再インストール | オーガニック再インストール | 1-3時間 | オーガニック |  |
| ユーザー獲得 | クロスプラットフォームエンゲージメント（広告接触） | 毎時 | 両方 | ✓ |

</Accordion>

<div id="protect360" />

<Accordion title="Protect360">

<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports">Protect360 レポートについて</Anchor>を参照してください。

| レポートの種類 (トピック) | データ更新頻度 |
| --- | --- |
| ブロック済みインストール | 1-3時間 |
| ブロック済みアプリ内イベント | 1-3時間 |
| ブロック済みクリック | 1-3時間 |
| ポストアトリビューション判定されたインストール | 日毎<br /><br />各日のレポートには、前日に報告されたポストアトリビューション判定されたインストールデータが含まれます。 例えば、月曜日に検知されたデータのレポートは、火曜日のレポートに含まれます。 |

</Accordion>

<div id="peoplebased-attribution" />

<Accordion title="ピープルベースアトリビューション（PBA）">

**データ更新頻度**

前日（UTC）終了後、10〜12 時間後に日次で利用可能になります。例えば、月曜日に受信されたデータは、1 日の終了後に処理され、月曜日の h=23 フォルダで利用可能になります。 データは火曜日の日本時間21:00 (UTC 12:00) までに利用可能になります。

**注意事項**

* アカウント内のすべての PBA ブランドバンドルのデータは、アプリフィルターを考慮せず常に提供されます。
* アプリ単位でのデータ分割は利用できません。

| レポートの種類 (トピック) |
| --- |
| <Anchor target="_blank" href="/marketers/ja/docs/pba-raw-data-reports#website-visits-and-website-events">Webサイト訪問</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/pba-raw-data-reports#website-visits-and-website-events">Webサイトイベント</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/pba-raw-data-reports#websiteassisted-installs::7e12586d">Webサイトアシストインストール</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/pba-raw-data-reports#conversion-paths">コンバージョン経路</Anchor> |

</Accordion>

<div id="incrementality" />

<Accordion title="Incrementality">

<Anchor target="_blank" href="/marketers/ja/docs/incrementality-for-remarketing-overview#available-reports">Incrementalityレポート</Anchor>を参照してください。

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

<Anchor target="_blank" href="/marketers/ja/docs/skan-raw-data-reports">SKANローデータレポート</Anchor>について

**データ更新頻度**

* データは、AppsFlyer がポストバックを受信した日、または API 経由で AppsFlyer に報告された日の翌日に利用可能になります。
* データは、AppsFlyer がデータを受信した日の h=23 フォルダに格納されます。例：月曜日にポストバックを受信した場合、日次終了後に処理され、火曜日 UTC 12:00 までに処理が完了し、月曜日の h=23 フォルダでデータが利用可能になります。

| レポートの種類 (トピック) |
| --- |
| ポストバック |
| ポストバックコピー（iOSから直接送信されたもの） |
| インストール |
| 再ダウンロード |
| アプリ内イベント |
| SRN広告のディメンション |

</Accordion>

<div id="ad-revenue" />

<Accordion title="収益">

<Anchor target="_blank" href="/marketers/ja/docs/revenue-etl-reports">RevenueETLのData Lockerレポート</Anchor>を参照してください。

<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">広告収益のローデータ</Anchor>を参照してください。

</Accordion>

<div id="ctv" />

<Accordion title="CTV、PC、コンソールのデータ">

<Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-data-via-data-locker">Data LockerでのCTV、PC、コンソールのデータ取得</Anchor>を参照してください。

</Accordion>

## アドバンスローデータレポート（ベータ機能）

アドバンスレポートは、構造化・検証済み・**AI 対応のデータセット**を提供することを目的とした、新世代のローデータレポートです。**初回の広告接触からコンバージョン、インストール後のアクティビティまで、ユーザージャーニー全体の取り込みと分析を、3 つのレポートのみで可能にします。**  
**型定義されたフィールド**、**洗練されたフィールド名**、すべてのデータセットで一貫したスキーマにより、明確性・正確性・使いやすさを確保します。統一された構造により、データセット間の結合が容易になり、**ETL および後続処理の複雑さを軽減し**、高度な分析を支えるデータを提供するとともに、用途に応じた柔軟なデータ活用を可能にします。詳細については、「Data Lockerのアドバンスレポートについて」を参照してください。

<div id="advanced-reports" />

<Accordion title="エンゲージメントローデータレポート">

エンゲージメントローデータレポートは、モバイルおよびCTVプラットフォームにおけるユーザー獲得およびリターゲティング施策のクリックおよびインプレッションデータを統合します。ユーザーの広告との接点を統合的に可視化することで、ファネル上流のパフォーマンスを詳細に分析でき、成果につながるクリエイティブやチャネルの特定を支援します。また、エンゲージメント単位で広告費やリーチの最適化を行えるため、マーケティング施策の露出状況やトラフィック品質を評価するための基盤として活用できます。詳細については、「Data Lockerのアドバンスレポートについて」の<Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports#engagements">エンゲージメントローデータレポート</Anchor>のセクションを参照してください。

| カテゴリ | レポートの種類 (トピック) | データ更新頻度 | Data Locker経由のみ |
| --- | --- | --- | --- |
| ユーザー獲得とリターゲティング | クリック数とインプレッション数 | 1-3時間 | ✅ |

</Accordion>

<div id="conversion-report" />

<Accordion title="コンバージョンレポート">

コンバージョンレポートは、モバイルおよびコネクテッドTV（CTV）におけるオーガニックおよび非オーガニックを含む、すべてのアプリインストールを包括的に確認できるレポートです。コンバージョンデータを一元化することで、単一の簡潔なデータセットを用いた包括的な成長分析が可能になります。本レポートを使用して、マーケティングパフォーマンスを正確に計測・最適化できます。詳細については、「Data Lockerのアドバンスレポートについて」の<Anchor target="_blank" href="/marketers/ja/docs/about-data-locker-advanced-reports#conversions">コンバージョンレポート</Anchor>のセクションを参照してください。

| カテゴリ | レポートの種類 (トピック) | データ更新頻度 | Data Locker経由のみ |
| --- | --- | --- | --- |
| ユーザー獲得とリターゲティング | リエンゲージメント / リアトリビューション | 1-3時間 | ✅ |

> 📘 **注意**
>
> * 再インストールは本レポートには含まれません。
> * CTV、PC、コンソールを含む拡張プラットフォームのアプリでは、リターゲティングによるコンバージョンイベントは含まれません。

</Accordion>

<div id="h_01K9CROSSPLATFORMREPORT" />

<Accordion title="エンドユーザーイベントレポート">

エンドユーザーイベントレポートは、モバイルおよびCTVにおけるセッション、購入、登録、レベルクリアなどの詳細なアプリ内イベントを収集するレポートです。各イベントには完全なアトリビューションコンテキストが付与されており、アトリビューションの完全なトレーサビリティを確保しながら、ユーザー行動、リテンション、LTVを詳細に分析することが可能です。詳細については、「Data Lockerのアドバンスレポートについて」の[エンドユーザーイベントレポート](#enduser-events)のセクションを参照してください。

| カテゴリ | レポートの種類 (トピック) | データ更新頻度 | Data Locker経由のみ |
| --- | --- | --- | --- |
| ユーザー獲得とリターゲティング | エンドユーザーイベント | 1-3時間 | ✅ |

> 📘 **注意**
>
> CTV、PC、コンソールを含む拡張プラットフォームアプリでは、リターゲティングによるエンドユーザーイベントは含まれません。

</Accordion>

## 集計レポート

<div id="cohort-analytics" />

<Accordion title="コホート分析">

**データ更新頻度**

レポートは通常、前日分のフォルダに日本時間21:00 (UTC 12:00) までに利用可能になります。たとえば、火曜日の日本時間21:00 (UTC 12:00) までに処理が完了した場合、データは月曜日のフォルダに格納されます。

| レポートの種類 (トピック) |
| --- |
| <Anchor target="_blank" href="/marketers/ja/docs/cohort-analytics-via-data-locker">コホート - 統合</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/cohort-analytics-via-data-locker">コホート - ユーザー獲得</Anchor> |
| <Anchor target="_blank" href="/marketers/ja/docs/cohort-analytics-via-data-locker">コホート - リターゲティング</Anchor> |

</Accordion>

<div id="advanced-aggregated-reports" />

<Accordion title="アドバンス集計レポート">

Data Locker のアドバンス集計レポートには、最適なデータ更新頻度、正確性、粒度、そして無制限のデータボリュームを備えた集計データが含まれます。詳細は<Anchor target="_blank" href="/marketers/ja/docs/advanced-aggregated-reports-in-data-locker">こちらのページ</Anchor>をご覧ください。

</Accordion>

<div id="creative-optimization-etl" />

<Accordion title="Creative Optimization ETL">

Creative Optimization ETL レポートは、クリエイティブパフォーマンス分析に必要なすべての情報をデータアナリストに提供します。主要 KPI、上流および下流ファネルの KPI、アトリビューションデータ、クリエイティブアセットデータを含む、アセット単位での完全なパフォーマンスレポーティングを提供します。<Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-etl-reporting">詳細はこちらのページをご覧ください。</Anchor>

</Accordion>

<div data-zendesk-anchors="reports-available-via-data-locker-for-advertisers=%E5%BA%83%E5%91%8A%E4%B8%BB%E5%90%91%E3%81%91data-locker%E3%81%A7%E6%8F%90%E4%BE%9B%E3%81%95%E3%82%8C%E3%82%8B%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E4%B8%80%E8%A6%A7 01H7WFZN6P1S49NYX8Q0W55P0B=%E5%BA%83%E5%91%8A%E4%B8%BB%E5%90%91%E3%81%91data-locker%E3%81%A7%E6%8F%90%E4%BE%9B%E3%81%95%E3%82%8C%E3%82%8B%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E4%B8%80%E8%A6%A7 01H7WFZN6PQWASTMXM9V72QZER=data-freshness-explanations raw-data-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01H7WFZN6P94YW1V79NT3HV5G4=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01H7WFZN6PD75S557PDB5PSFFR=user-journey 01H7WFZN6QY2GV69N464EE196M=protect360 01H7WFZN6QW72FDBTMW2ZD7NZQ=peoplebased-attribution 01H7WFZN6QZ1B7BS6E59RVAF30=incrementality 01H7WFZN6Q0P99DCFA7MZQTVSX=skan 01H7WFZN6Q717F9Z1HG38JVBG3=ad-revenue 01H7WFZN6QMJGSAJR00MHYJB6Z=ctv Unified%20raw-data-reports=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%99%E3%83%BC%E3%82%BF%E6%A9%9F%E8%83%BD h_01JX9T0PGE93JNJ3S4NDP0C2YW=%E3%82%A2%E3%83%89%E3%83%90%E3%83%B3%E3%82%B9%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%83%99%E3%83%BC%E3%82%BF%E6%A9%9F%E8%83%BD h_01K85EE8DA4E8D4SVHYV2PE42E=conversion-report h_01K85EE8DAWY52B7RJQ33MJ59B=%E6%B3%A8%E6%84%8F cross-platform-end-user-events-report=h_01K9CROSSPLATFORMREPORT h_01KMD3WY9MQABBWFCTJYVWG66S=%E6%B3%A8%E6%84%8F-1 aggregated-reports=%E9%9B%86%E8%A8%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01H7WFZN6Q90AT8N0VY5PKQ407=%E9%9B%86%E8%A8%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01H7WFZN6QNKXTRM7G6VFANSZ7=cohort-analytics h_01J0K1MEKEEAQBXF1YRZTG8V0X=advanced-aggregated-reports h_01J0TQ88VNSFZJ27T3E2P3MVE6=creative-optimization-etl" />
