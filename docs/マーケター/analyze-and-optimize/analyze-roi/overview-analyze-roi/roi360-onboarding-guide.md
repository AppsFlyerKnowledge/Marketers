---
title: ROI360｜導入ガイド
metadata:
  keywords:
    - ROI
    - cost
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-05-23T08:36:31Z'
  edited_at: '2026-10-28T08:47:56Z'
  id: 25301111725329
  locale: ja
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/ja/articles/25301111725329
---
> **概要**：この記事の導入手順に従って、ROI360で広告費と収益のデータを取得するための設定を行います。

<Image align="center" alt="" src="https://files.readme.io/fa3644980702d735f81d7243f91cb0f0d454bd971e83685ab9759ff7bd925e93-26137252926097.png" />

<div id="about-roi360" />

## ROI360について

ROI360は、広告費と収益のレポートに特化したツール群で、最新かつ高精度のデータを提供します。広告費と収益の両方のデータから、広告費用対効果（ROAS）と投資利益率（ROI）の全体像を把握し、それに基づく最適化と改善を行えます。

以下の導入手順に従って、ROI360で広告費、広告収益、アプリ内課金・サブスクリプション収益のレポートを利用するための設定を行います。導入を完了するには、マーケティング担当者、アプリ開発者、BIシステムの開発者による対応が必要です。

**ヒント**！スムーズに導入するには、まず1つのアプリを優先し、そのアプリでROI360を利用するためのすべての手順を完了してください。広告費、広告収益、アプリ内課金・サブスクリプション収益のいずれから着手してもかまいませんが、まずは1つのアプリの導入を完了させてください。

<div id="cost-onboarding" />

<Accordion title="広告費データの取得設定">

<Image align="center" alt="" src="https://files.readme.io/0e7102766b3b7cdba3f301ca89c51edf8e4bd2ec88e09bc912ce3c1436c43fcb-26137252929681.png" />

ROI360の広告費ソリューションでは、広告費とROIの詳細なデータを取得できます。データは1日に複数回更新されます。アドネットワーク、自社メディア、代理店のいずれを利用する場合でも、キャンペーンの広告費を効果的に管理し、メディアソース（アドネットワーク）、キャンペーン、地域ごとの予算配分を確認できます。

広告費データの取得設定を完了すると、次のことが可能になります。

* すべてのメディアソースの広告費が自動的に集約され、最新のデータでキャンペーン全体の広告費を把握できます。
* インストール後も更新される、高精度の広告費データに基づいて分析できます。
* ROI360 Advancedをご利用の場合は、詳細な広告費データを1日最大4回、BIシステムに送信できます。
* 代理店手数料を管理し、キャンペーンの総費用を正確に計測することで、費用を適切に管理し、その内訳を明確にできます。

| 作業項目 | 目的 | 必要な作業 | 担当者 |
| --- | --- | --- | --- |
| 利用するすべてのアドネットワークで、広告費API連携を設定します。 | 各メディアソースから、アトリビューションに紐づく、最も詳細な広告費データを取得します。 | AppsFlyerの管理画面で、アドネットワークごとに<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">広告費APIを有効にします</Anchor>。**注意**：連携する前に、各アドネットワークの認証情報・ログイン情報を取得する必要があります。 | マーケティング担当者 |
| コストETLレポートを設定します。 （ROI360 Advancedをご契約のお客様が利用可能） | 各メディアソースから取得できる最も詳細なキャンペーン広告費データを確認できます。データは1日最大4回更新されます。 | <Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-aws-s3">AWS S3</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-gcs">GCS</Anchor>向けのコストETLレポートを設定します。 | マーケティング担当者／BIシステム開発者 |
| コストインポートで広告費データをアップロードします。 | 次のような場合に、広告費データを取得できます。<ul><li>APIやクリック経由で広告費を送信しないアドネットワークを利用する場合。</li><li>OneLinkを使用して、インフルエンサーなどを通じて広告を配信する場合。</li><li>広告費データの修正が必要な場合。</li></ul> | <Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">コストインポート</Anchor>を使用して、広告費データのファイルをアップロードするか、メールで送信します。 | マーケティング担当者 |
| 代理店手数料を設定します。 | 代理店を利用する場合は、広告配信に対して一定の料率で請求される手数料も含めて、キャンペーンの総費用を把握できます。 | 利用する代理店ごとに、<Anchor target="_blank" href="/marketers/ja/docs/incorporate-agency-fees-into-campaign-costs">代理店手数料のルール</Anchor>を作成します。 | マーケティング担当者 |

</Accordion>

<div id="ad-revenue-onboarding" />

<Accordion title="広告収益データの取得設定">

<Image align="center" alt="" src="https://files.readme.io/877e4abddd466bbe7dfa31f7fffb2f17fe3e6419f3bf6345e9d619253126b0e6-26137252932369.png" />

ROI360の広告収益ソリューションでは、分析に役立つ詳細な広告収益データを取得できます。データは1日に複数回更新されます。

広告収益化に利用するメディエーションプラットフォームやアドネットワークとの連携、インプレッション単位の広告収益SDK APIの実装、ユーザー獲得（UA）パートナーとのデータ共有などの導入設定を完了すると、次のことが可能になります。

* AppsFlyerのすべてのダッシュボードとレポートで、正確かつ最新の広告収益データを取得できます。
* 必要な詳細度と更新頻度で、BIシステムにデータを継続的に送信できます。
* ユーザー獲得を担うアドネットワークが広告収益の指標に基づいて最適化を行うことで、キャンペーンの成果向上につなげられます。

| 作業項目 | 目的 | 必要な作業 | 担当者 |
| --- | --- | --- | --- |
| 広告収益のアトリビューションに使用する連携方式を決めます。 | 各連携方式のメリットを把握し、ビジネスの要件に最も適した方式を選択します。 | <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">広告収益の連携方式</Anchor>を確認し、いずれか1つを選択します。 | マーケティング担当者 |
| 広告収益化に利用するすべてのメディエーションプラットフォームおよびアドネットワークとの連携を設定します。 | メディエーションプラットフォームや広告収益化に利用するアドネットワークから、広告収益データを取得できます。 | AppsFlyerの管理画面で、<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">広告収益の連携を設定します</Anchor>。 | マーケティング担当者 |
| インプレッション単位の広告収益SDK APIを実装します。 | <ul><li>SDKを使用する連携方式が対象です。</li><li>ほぼリアルタイムで広告収益データを取得できます。</li></ul> | <ol><li><Anchor target="_blank" href="/marketers/ja/docs/integrate-the-roi360-ad-revenue-sdk-api">ROI360向けAppsFlyer広告収益SDK API</Anchor>を実装します。</li><li>SKANダッシュボードに広告収益データを表示するには、<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#report-events-by-servertoserver-api">SKAdNetworkのS2S連携</Anchor>をオンにします。</li></ol> | 開発者／マーケティング担当者 |
| ユーザー獲得パートナーと広告収益データを共有します。 | ユーザー獲得を担うアドネットワークは、広告収益データを使ってユーザー獲得キャンペーンを最適化できます。 | <ol><li><Anchor target="_blank" href="/marketers/ja/docs/share-ad-revenue-data-with-partners#パートナーへの広告収益データの共有について">ユーザー獲得パートナーと広告収益データを共有する2つの方法</Anchor>を確認します。</li><li>選択した<Anchor target="_blank" href="/marketers/ja/docs/share-ad-revenue-data-with-partners#手順">方法に従って実装します</Anchor>。</li></ol> | マーケティング担当者 |
| 収益ETLレポートを設定します。 （ROI360 Advancedをご契約のお客様が利用可能） | 取得できる最も詳細な広告収益データをBIシステムに送信し、確認できます。データは1日に複数回更新されます。 | <Anchor target="_blank" href="/marketers/ja/docs/revenue-etl-reports">広告収益ETLレポート</Anchor>を設定します。 | マーケティング担当者／BIシステム開発者 |

</Accordion>

<div id="revenue-onboarding" />

<Accordion title="アプリ内課金・サブスクリプション収益の取得設定">

<Image align="center" alt="" src="https://files.readme.io/811c90ec42465994455fe42be8400b4ebb94ab6d1a5703bc9a77251aba95ed3b-26137252934545.png" />

ROI360の収益ソリューションを使用すると、収益状況を把握し、計画的に管理できます。

ストア通知の設定やAndroid・iOS向けの購入SDK APIの実装など、収益データの取得設定を完了すると、次のことが可能になります。

* App StoreとGoogle Playの取引を、自動的に検証・計測できます。
* ROI360がすべてのアプリ内収益イベントを記録するため、導入後に開発者が追加対応することなく、正確な収益レポートを継続的に取得できます。
* 収益を正確に計測することで、運用するアプリ全体で、成長に向けた戦略的な取り組みを効果的に管理できます。

| 作業項目 | 目的 | 必要な作業 | 担当者 |
| --- | --- | --- | --- |
| ROI360のアプリ内課金・サブスクリプション収益ソリューションを実装します。 | App Store（iOS）またはGoogle Play（Android）で発生するアプリ内課金、自動更新サブスクリプション、および関連イベントの収益を自動的に検証・計測できます。 | <Anchor target="_blank" href="/marketers/ja/docs/purchase-and-subscription-validation-overview">こちらの手順</Anchor>に従って、以下の作業を行います。<ol><li>Google Playとの連携を設定します。</li><li>iOSのApp Storeとの連携を設定します。</li><li>AppsFlyer購入SDKコネクタを実装します。</li><li>アプリ内課金・サブスクリプション収益の計測をテストします。</li><li>SDKコネクタを実装したバージョンのアプリをリリースします。</li></ol> | 開発者／マーケティング担当者 |
| 収益ETLレポートを設定します。 （ROI360 Advancedをご契約のお客様が利用可能） | 取得できる最も詳細な収益データをBIシステムに送信し、確認できます。データは1日に複数回更新されます。 | <Anchor target="_blank" href="/marketers/ja/docs/revenue-etl-reports">収益ETLレポート</Anchor>を設定します。 | マーケティング担当者／BIシステム開発者 |

</Accordion>

<div data-zendesk-anchors="overview=roi360%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HKHGX9JJQQCKF9SDZRSCM1XJ=roi360%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HYJ8PSPTFR6QH329TBR73AXM=cost-onboarding h_01HYJ8PSPTKBZ60TF7T0EMSCXW=ad-revenue-onboarding h_01HYJ8PSPTWK4SEGVJWG5J86E2=revenue-onboarding" />
