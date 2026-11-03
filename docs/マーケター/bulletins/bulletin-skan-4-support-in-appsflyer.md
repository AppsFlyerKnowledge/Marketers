---
title: お知らせ：SKAN 4のサポート開始
metadata:
  keywords:
    - iOS
    - Marketers
    - SKAN
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2023-01-05T12:36:02Z'
  edited_at: '2026-10-14T09:25:47Z'
  id: 11938810583825
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/11938810583825
---
| **ヘッドライン** |  |
| --- | --- |
| **発効日** | <ul><li>2025年2月1日</li><li>2023年2月以降、V6.10を実装の場合、最新バージョンのV6.12+へのアップデートを推奨します。<ul><li>変更点の一覧は<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-ios-sdk-release-notes">こちら</Anchor>で確認できます</li></ul></li><li>準備中：</li></ul> |
| **前提条件** | SKAN 4.0以降におけるiOSデータを正しく計測するには：<ul><li>AppsFlyer iOS SDKバージョン V6.12.1以降</li><li>広告媒体側での SKAdNetwork V4の広告署名（ad signature）の対応</li><li>アプリに掲載される広告：アプリOSバージョン iOS 16.1以降でのビルド</li><li>ウェブ広告：Safari 16.1 以降</li><li>広告主アプリが App Storeによる署名が付与され iOS 16.1以降を搭載した端末で実行されている</li></ul> |
| **必要なアクション** | <ul><li><Anchor target="_blank" href="/marketers/ja/docs/appsflyer-ios-sdk-release-notes">AppsFlyer iOS SDKバージョンを V6.12.1以降</Anchor>にアップデート</li><li>AppsFlyer SKAN Conversion Studioで、 <Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#skan-4">SKAN 4 計測モード</Anchor> にアップグレードし、3つのSKANウィンドウのCVを設定します（またはデフォルト設定のままにします）。</li></ul>**注： 注意： SKAN 4にアップデートすると、次のようになります：**<ul><li>SKAN 4インストール前のアクティビティタイマーは48時間です。</li><li>一度アップデートすると、以前のSKANバージョンに戻すことはできません。</li></ul> |
| **SKAN Conversion Studio**の変更点 | 3つのSKANウィンドウを設定するための新しいSKAN 4 計測モード |
| **ダッシュボード**の変更 | <ul><li>SKAN オーバービューダッシュボードには、3つのSKANウィンドウ中のイベント数と収益の新しい項目（テーブル設定で使用可能）が含まれています。<ul><li>イベント数 D0-D2</li><li>イベント数 D0-D2 （推定値）</li><li>イベント数 D3-D7</li><li>イベント数 D8-D35</li><li>収益 D0-D2 ($)</li><li>収益 D0-D2 ($)（推定値）</li><li>収益 D3-D7 ($)</li><li>収益 D8-D35 ($)</li></ul></li><li>SSOTビューには、アクティビティ期間（AW）の代わりに D2 データ項目が表示されます。SKAN 3データの場合、この項目にはウィンドウが2日より長いか短い場合でも、すべてのアクティビティ期間データが表示されます。</li></ul> |
| **レポート**の変更 | <ul><li>SKAdNetworkレポートには、SKAN 4をサポートするための次の新しい項目が含まれています：<ul><li>**skad\_postback\_sequence\_index**:SKAN 3の場合：常に0</li><li>**skad\_coarse\_conversion\_value**:値は 、 、 のいずれか。SKAN 3の場合：常に0</li><li>skad\_source\_identifierSKAN 3の場合：常に0</li><li>skad\_source\_domainSKAN 3の場合：常に0</li><li>ad\_network\_creative値はアドネットワークから取得したデータの拡充に基づいています。SKANバージョン3の場合、値は空になります。</li></ul></li><li>次のData LockerおよびPull APIレポートに変更が加わります：</li></ul><ul><li>**skad\_installs** （Data LockerおよびPush API経由）</li><li>skad\_redownloads（Data LockerおよびPush API経由）</li><li>skad\_inapps（Data LockerおよびPush API経由）</li><li>**skad\_postbacks**（Data Locker経由）</li><li>skad\_postbacks\_copy （Data Locker経由）（ad\_network\_creative項目は含まれません）</li><li>参照：サンプルレポートスキーマ</li></ul><ul><li>SKAN集計ポストバック到着日APIおよびSKAN集計パフォーマンスレポートAPIに、SKAN4の項目が含まれます。　**注：** 注意： SKAN 4 の V2 APIトークンのパスを使用する必要があります。</li></ul> |