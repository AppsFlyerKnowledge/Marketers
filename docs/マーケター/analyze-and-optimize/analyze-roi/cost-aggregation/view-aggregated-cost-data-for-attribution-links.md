---
title: アトリビューションリンクで送信される広告費の集計データの確認
metadata:
  keywords:
    - eCPI
    - clicks
    - ROI
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-20T10:50:58Z'
  edited_at: '2026-10-28T08:43:36Z'
  id: 360008981698
  locale: ja
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ja/articles/360008981698
---
> **概要：** アドネットワークが広告のクリックごとにアトリビューションリンクで送信する広告費を、集計データで確認する方法を説明します。

## 広告費の基本的なレポート

AppsFlyerへの広告費データの送信方法：

* ユーザーが広告をクリックするたびに、アドネットワークから送信されます。 AppsFlyerでキャンペーンの広告費を確認することで、広告主はROIを計測し、適切な予算判断を行えます。
  * 広告費は、インストール単価（CPI）モデルを使用し、<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">アトリビューションリンク</Anchor>で送信されます。
  * アトリビューションリンクをアドネットワークに渡す際は、アドネットワークが<Anchor target="_blank" href="/partners/ja/docs/cost-reporting-on-the-attribution-link-for-ad-networks">広告費送信用パラメータを追加する</Anchor>ことを確認してください。
* <Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview">広告費の集計には、さらに高度な方法</Anchor>として、APIやコストインポート（CSVファイルのアップロード）もあります。

  * これらの集計方法は、CPIに加えて、CPA、CPC、CPMなど、パートナーが使用する課金モデルにも対応しています。

<div id="viewing-ad-cost-by-click" />

<Accordion title="アトリビューションリンクで送信された広告費の確認">

アトリビューションリンクで送信された広告費は集計され、AppsFlyerのダッシュボード、パフォーマンスレポート、ローデータレポートでリアルタイムに確認できます（リンクのクリックから最大2時間かかる場合があります）。

*Overview dashboardの集計パフォーマンスレポート*には、広告費、クリック数、インプレッション数、ROI、平均eCPIのデータが含まれます。

[![CostReporting.jpg](https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg)](https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg)

パフォーマンスレポートとローデータレポートは、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ダウンロード</Anchor>することもできます。

</Accordion>

<div id="ad-networks-providing-cost-by-click-data" />

<Accordion title="アトリビューションリンクで広告費を送信するアドネットワーク">

アトリビューションリンクで広告費を送信するアドネットワークでは、リンクに含まれるディメンションに対応しています。

**アトリビューションリンクで広告費を送信するアドネットワークには、次のものがあります。**

* AdAction
* Aura from Unity
* Blind Ferret
* Chartboost
* Cross Install
* Digital Turbine
* Fyber
* HangMyAds
* ironSource
* Criteo DSP (Manage)
* Mintegral
* TikTok for Business
* Vungle
* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTMPZ9anfZoFBelK2bsBUoHG9n4YE3WxpXOayDF_wI8vyYClM6_6yXelFCZ3khwhd9Z_5Louxd4VVgx/pub?gid=0&single=true&output=csv">アトリビューションリンクでの広告費送信に対応するアドネットワークの全一覧を確認</Anchor>

</Accordion>

<div id="limitations" />

<Accordion title="制限事項">

アトリビューションリンクで送信する広告費には、次の制限があります。

* 広告費を送信できるのは、インストール単価（CPI）モデルのみです。 CPA、CPC、CPMなど、その他のモデルには対応していません。
* <Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">Self-Reporting Network</Anchor>（SRN）は、アトリビューションリンクで広告費を送信しません。
* アトリビューションリンクで送信された広告費データは変更できません。そのため、AppsFlyerに記録された後は、データの報告に誤りがあっても修正できません。

</Accordion>

<div data-zendesk-anchors="basic-cost-reporting=%E5%BA%83%E5%91%8A%E8%B2%BB%E3%81%AE%E5%9F%BA%E6%9C%AC%E7%9A%84%E3%81%AA%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HX954Y5X7ZP2VMB5W2XAMCR0=%E5%BA%83%E5%91%8A%E8%B2%BB%E3%81%AE%E5%9F%BA%E6%9C%AC%E7%9A%84%E3%81%AA%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HX954Y5XTRRQV4JHA5XX1AQ0=viewing-ad-cost-by-click h_01HX954Y5XV8M2R2VDAV34641R=ad-networks-providing-cost-by-click-data h_01HX954Y5X84BM7F8TGQRDPBTS=limitations" />
