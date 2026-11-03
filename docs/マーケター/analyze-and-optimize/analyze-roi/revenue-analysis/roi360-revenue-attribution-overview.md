---
title: ROI360｜収益のアトリビューションの概要
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2018-11-12T07:56:29Z'
  edited_at: '2026-10-28T08:49:54Z'
  id: 360001546009
  locale: ja
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ja/articles/360001546009
---
> **概要：** 収益データを使うと、ROIとROASの全体像を正確に把握できます。広告主が収益データを集計・確認するための製品や機能を紹介します。

![roi_revenue.png](https://files.readme.io/4b1013d51c3ff2c80b15ec598f7bbe02dadc0e556f5533b9a49ea320fa85be6d-33438500789905.png)

## 概要

ROIの算出には、収益と広告費の2つが必要です。収益データを正確に計測し、ユーザーを獲得したメディアソースやキャンペーンに紐づけると、次のことができます。

* ROIとROASの全体像を把握できます。インストールやエンゲージメントの件数に加え、価値の高いユーザーを獲得できているアドネットワーク、キャンペーン、広告を特定できます。
* 分析結果をもとに、広告費の配分やマーケティングキャンペーンを調整できます。

### 有料機能による収益レポート

収益の主な発生源は、次の3つです。

* **アプリ内購入**：アプリ内で商品やサービスを販売して得られる収益です。 AppsFlyerは、保留中の購入、購入、返金、キャンセル、税金、ストア手数料などを含め、アプリ内購入に関する収益を自動的に検証・計測できます。アプリ内購入について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/purchase-and-subscription-validation-overview">購入・サブスクリプションの検証</Anchor>を参照してください。
* **サブスクリプション収益**：アプリやサービスのサブスクリプションから得られる収益です。アップグレード、自動更新の停止、返金など、サブスクリプションの変更も含まれます。サブスクリプション収益について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/purchase-and-subscription-validation-overview">購入・サブスクリプションの検証</Anchor>を参照してください。
* **広告収益**：アプリ内に広告を掲載し、ユーザーに表示することで得られる収益です。例えば、自社アプリ内に他のアプリの広告を表示できます。ユーザーがその広告をクリックすると、クリックに応じた収益が発生します。広告収益について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution">「ROI360ガイド｜広告収益のアトリビューション」</Anchor>を参照してください。

### 基本的な収益レポート

AppsFlyerには、基本的な収益計測ツールもあります。高度な収益レポート機能に比べると、利用できる機能は少なく、開発者の設定作業も増えますが、有料製品の契約は不要です。

* <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#revenue-events">カスタムのアプリ内イベント</Anchor>による収益の記録。このデータは、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#ポストバックに含めるデータ">ポストバック</Anchor>でアドネットワークに共有することもできます。**注意**：返金、税金、ストア手数料なども自動的に計測する場合は、有料機能のアプリ内購入の検証をご検討ください。
* レシート検証

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 01JC364VBGSCYBHHZENZXJQ39R=%E6%A6%82%E8%A6%81 premium-revenue-reporting=%E6%9C%89%E6%96%99%E6%A9%9F%E8%83%BD%E3%81%AB%E3%82%88%E3%82%8B%E5%8F%8E%E7%9B%8A%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01JC364VBHQ4C12YVEJ0Q7X6R4=%E6%9C%89%E6%96%99%E6%A9%9F%E8%83%BD%E3%81%AB%E3%82%88%E3%82%8B%E5%8F%8E%E7%9B%8A%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 basic-revenue-reporting=%E5%9F%BA%E6%9C%AC%E7%9A%84%E3%81%AA%E5%8F%8E%E7%9B%8A%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01JC364VBK86C9ZV94P0FJGZSV=%E5%9F%BA%E6%9C%AC%E7%9A%84%E3%81%AA%E5%8F%8E%E7%9B%8A%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88" />
