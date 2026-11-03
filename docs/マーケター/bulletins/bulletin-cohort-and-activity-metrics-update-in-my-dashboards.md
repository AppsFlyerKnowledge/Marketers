---
title: お知らせ：マイダッシュボードにおけるコホート指標のアップデート
metadata:
  keywords:
    - Partners
    - Marketers
    - Marketing Analytics
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maya-kahane
    - Marketers
    - Marketing Analytics
  created_at: '2026-04-19T14:38:57Z'
  edited_at: '2026-10-14T09:22:59Z'
  id: 45887523041425
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/45887523041425
---
| **概要** | **2026年7月**より、**マイダッシュボード**のコホート指標およびアクティビティ指標は、**AI活用を前提としたデータ基盤**へ移行します。この変更は**2026年7月〜8月**にかけて段階的に適用されます。<br /><br />段階的な移行に伴い、一部の指標値、過去データの利用可能範囲、セグメンテーションオプションに変更が生じる場合があります。<br /><br />今回のアップデートでは、アクティビティデータ向けの新しいビュータイプと指標の追加、コホートデータにおけるユニークユーザー数の精度向上、さらにコホートとアクティビティの両方における過去データおよびセグメンテーション機能の拡張が行われます。 |
| --- | --- |
| **適用時期** | 2026年7月〜8月に段階的に展開 |
| **対象者** | **マイダッシュボード**でコホート指標またはアクティビティ指標を利用しているすべての広告主、代理店、パートナー |
| **必要な対応** | 対応不要。変更は自動的に適用されます |
| **ご確認いただきたい事項** | **<span id="h_activity-retargeting-and-ua-view-types"></span>アクティビティデータでリターゲティングおよび新規獲得ビューが利用可能に**<br /><br />アクティビティデータをビュータイプごとにフィルタリング・分析できるようになりました。利用可能なビュータイプには、リターゲティングと新規獲得が含まれます。<ul><li>リターゲティングデータは2025年2月以降のデータが利用可能です。</li><li>新規獲得データは2026年2月以降のデータが利用可能です。</li><li>リターゲティングおよび新規獲得ビューでは当日データは含まれません。データ反映には1日の遅延があります。</li></ul>**<span id="h_net-revenue-metrics"></span>コホートおよびアクティビティでネット収益関連の指標が利用可能に**<br /><br />ROI360を利用してネット収益を計測している、またはアプリ内イベントで`af_net_revenue`イベントパラメーターを送信しているお客様は、以下の指標を利用できるようになります。<ul><li>ネット収益</li><li>ネットROAS</li><li>ネットROI</li><li>ネットARPU</li><li>総利益</li></ul>これらの指標は、ネット収益データを送信しているお客様にのみ表示されます。<br /><br />**<span id="h_ctv-app-support"></span>CohortおよびActivityでCTVアプリをサポート**<br /><br />コホート指標およびアクティビティ指標がCTVアプリでも利用可能になりました。<br /><br />**<span id="h_new-dimensions"></span>コホートおよびアクティビティで新しいディメンションを追加**<br /><br />以下のディメンションが、コホートおよびアクティビティの両方でセグメンテーションに利用できるようになりました。<ul><li>プラットフォーム</li><li>Sub 1</li><li>エンゲージメントの遷移先</li></ul>**<span id="h_extended-historical-data"></span>コホートで利用可能な過去データ期間を拡張**<br /><br />ほとんどのコホート指標において、**2024年5月6日**以降のデータを利用できるようになりました。従来より約6か月分多くの履歴データにアクセスできます。<br /><br />ただし、日次粒度のユニークユーザー数のデータには適用されず、こちらは**2025年6月3日**以降のデータのみ利用可能です。<br /><br />**<span id="h_unique-users-updated-calculation-method"></span>Cohortの日次内訳におけるUnique Usersの計算方法を更新**<br /><br />以下の指標について、Day 1、Day 7などの日次コホート分析における計算方法が更新されました。<ul><li>アプリ内イベントのユニークユーザー</li><li>リテンション数</li><li>リテンション率</li><li>ARPU</li></ul>**<span id="h_what-changed-and-why"></span>変更内容と背景**<br /><br />ユーザーの識別単位がデバイスレベルに変更されました。これにより、同じユーザーが複数回リエンゲージメントした場合でも、リエンゲージメント回数ごとではなく1ユーザーとして1回のみカウントされます。<br /><br />この変更により、リエンゲージメントキャンペーンを実施しているアプリで発生していた過剰計上が解消されます。<br /><br />リエンゲージメントキャンペーンを実施しているアプリでは、日次のユニークユーザー数が減少して見える場合がありますが、実際のユーザー数やパフォーマンスが低下したわけではなく、計測方法の修正によるものです。<br /><br />また、新しい計算方式では確率論的モデリングを用いた集計を採用しています。そのため、通常1〜2％程度のごく小さな近似誤差が発生する可能性があります。これは想定された挙動であり、データ不具合ではありません。<br /><br />**<span id="h_unique-users-data-availability"></span>データ利用可能期間**<ul><li>日次粒度データは**2025年6月3日**以降のデータが利用可能です。</li><li>2025年6月3日以前の日次のユニークユーザーデータはマイダッシュボードでは利用できません。</li><li>週次および月次粒度には影響ありません。過去データは引き続き利用可能です。</li></ul>**<span id="h_activity-unique-users-and-active-users-historical-availability"></span>アクティビティにおけるユニークユーザー数およびアクティブユーザー数の履歴データ制限**<br /><br />**2025年6月3日**以前の期間については、アクティビティのユニークユーザー数およびアクティブユーザー数は日付単位での内訳のみ利用可能です。<br /><br />期間合計値は**2025年6月3日**以降のデータから利用可能となります。<br /><br />この制限は、ユニークユーザー数またはアクティブユーザー数をベースに計算されるすべての指標に適用されます。なお、この制限は恒久的なものです。<br /><br />**<span id="h_uninstalls-temporarily-unavailable"></span>コホートのアンインストール指標が一時的に利用不可**<br /><br />アンインストールに関する指標は現在一時的に利用できません。復旧は今後1〜2四半期以内を予定しています。<br /><br />**なお、LTVには影響ありません。**<br /><br />**<span id="h_ad-revenue-unified-in-utc"></span>すべてのダッシュボードで広告収益のタイムゾーンをUTCに統一**<br /><br />すべてのダッシュボードにおいて、広告収益関連指標は連携方法やアプリ単位のタイムゾーン設定に関わらずUTC基準で表示されるようになります。<br /><br />過去データへの影響はありません。<br /><br />**<span id="h_about-the-transition"></span>移行について**<br /><br />今回の移行の目的は、コホートおよびアクティビティデータを、よりモダンでスケーラブルな基盤へ移行することです。これにより、データの信頼性とパフォーマンスを向上させるとともに、AI活用を前提とした分析機能の実現や、AppsFlyerの集約アトリビューションデータを活用した今後のプロダクト改善を支える基盤を構築します。<br /><br />過去データを参照する必要がある場合は、引き続きコホート & リテンションのダッシュボードをご利用ください。以下のデータについては、移行期間中もコホート & リテンションのダッシュボードから確認できます。 ・**2025年6月3日**以前のCohortユニークユーザー数のデータ ・再構築中のUninstallsデータ |

<div data-zendesk-anchors="activity-retargeting-and-ua-view-types=h_activity-retargeting-and-ua-view-types net-revenue-metrics=h_net-revenue-metrics ctv-app-support=h_ctv-app-support new-dimensions=h_new-dimensions extended-historical-data=h_extended-historical-data unique-users-updated-calculation-method=h_unique-users-updated-calculation-method what-changed-and-why=h_what-changed-and-why unique-users-data-availability=h_unique-users-data-availability activity-unique-users-and-active-users-historical-availability=h_activity-unique-users-and-active-users-historical-availability uninstalls-temporarily-unavailable=h_uninstalls-temporarily-unavailable ad-revenue-unified-in-utc=h_ad-revenue-unified-in-utc about-the-transition=h_about-the-transition" />
