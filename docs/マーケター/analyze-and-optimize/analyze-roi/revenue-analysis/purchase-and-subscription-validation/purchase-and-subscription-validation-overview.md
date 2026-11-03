---
title: 購入・サブスクリプションの検証｜概要
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-20T16:30:47Z'
  edited_at: '2026-10-28T08:49:28Z'
  id: 42120228484241
  locale: ja
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ja/articles/42120228484241
---
> **At a glance:** AppsFlyerが購入とサブスクリプションを検証する仕組みを説明し、レシート検証とROI360ストア収益の2つの機能を比較します。

## 購入・サブスクリプションの検証について

収益データの正確性と信頼性を確保するには、購入とサブスクリプションの検証が欠かせません。ユーザーがアプリ内で1回限りの購入やサブスクリプションの契約を行った際に、アプリストア（Apple App StoreとGoogle Play）に取引を照会し、正当で支払い済みの取引だけを計測・アトリビューションの対象にします。

AppsFlyerでは、アプリ内購入とサブスクリプションの収益を検証・計測するために、レシート検証とROI360ストア収益の2つの機能を提供しています。

アプリに適した機能を選べるよう、各機能の概要と[比較表](#レシート検証とroi360ストア収益の比較)を紹介します。

## 購入・サブスクリプションの検証に使える2つの機能

### レシート検証

レシート検証は、iOSとAndroidのアプリ内購入およびサブスクリプションを検証する、AppsFlyerの無料機能です。実際に成立した取引だけを計測します。そのために、レシートの情報をアプリストアに直接照会します。

アプリに組み込んだAppsFlyer SDKから、商品ID、購入ID、種類など、必要最小限のデータを送信します。 AppsFlyerは、ストアからの応答をもとに収益の詳細を取得します。取得する情報には、金額と通貨も含まれます。この機能では、純収益の計算、サブスクリプションのライフサイクル全体の計測、返金への対応、IAPの包括的な計測、購入の自動検出と重複排除は利用できません。

検証済みの収益データを、意思決定やキャンペーンの最適化に活用できます。

詳しくは、以下を参照してください。

* <Anchor target="_blank" href="/marketers/ja/docs/about-receipt-validation">レシート検証について</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/set-up-receipt-validation">レシート検証の設定</Anchor>

### ROI360ストア収益（有料機能）

> 🚧 **重要**
>
> ROI360ストア収益は、ROI360の有料プランをご契約のお客様のみ利用できます。契約プランの確認やアップグレードについては、担当のカスタマーサクセスマネージャー（CSM）にお問い合わせください。

ROI360ストア収益は、アプリ内購入とサブスクリプションの収益を漏れなく正確に計測するための、AppsFlyerの有料製品です。アプリストアとのサーバー間通信で取引を検証し、詳細情報を付加した検証済みの収益データを返します。

このサーバー間検証の過程で、重複を排除し、ストア手数料と税金を差し引いた純収益を計算します。また、更新、自動更新の停止、返金、アップグレードなど、サブスクリプションのライフサイクル全体を計測します。既存の契約者のイベントや、Google Playなどで支払いの確定が遅れた取引も処理できます。

収益を漏れなく正確に把握したい場合や、サブスクリプションのライフサイクルを分析したい場合、複雑なビジネスモデルに対応したい場合に適しています。

詳しくは、以下を参照してください。

* <Anchor target="_blank" href="/marketers/ja/docs/about-roi360-store-revenue">ROI360ストア収益について</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-store-revenue">ROI360ストア収益の設定</Anchor>

## レシート検証とROI360ストア収益の比較

以下の表で、用途に合った機能を確認してください。

<Accordion title="機能の比較">

| **機能** | **レシート検証** | **ROI360ストア収益**（有料機能） |
| --- | --- | --- |
| **レシート検証**  <br />アプリ内購入を検証し、不正な取引を除外します。 | ✔ | ✔ |
| **購入の自動検出と重複排除**  <br />既存の契約者の取引も含め、アプリ内購入（IAP）とサブスクリプションを自動的に検出します。重複を排除し、レポートの正確性を高めます。 | ✖ | ✔ |
| **返金への対応**  <br />返金を検出して元の購入に紐づけ、実際の収益を反映します。 | ✖ | ✔* |
| **IAPの包括的な計測**  <br />ファミリー共有に対応し、App Storeへの確認に基づいて、保留中だった購入の最終的な処理結果を報告します。 | ✖ | ✔ |
| **サブスクリプションのライフサイクル全体の計測**  <br />更新、アップグレード、コンバージョンを計測し、契約者全体がもたらす価値を把握できます。 | ✖ | ✔ |
| **純収益の計算**  <br />総収益に加え、ストア手数料と税金を自動的に差し引いた純収益も算出します。 | ✖ | ✔ |

* **アプリ内購入の**返金に対応しているのは、ROI360 Advancedプランのみです。

</Accordion>

<Accordion title="アプリ内購入イベントへの対応の比較">

| **イベント名** | **レシート検証** | **ROI360ストア収益** |
| --- | --- | --- |
| af\_purchase | ✔ | ✔ |
| af\_purchase\_refund* | ✖ | ✔ |
| af\_purchase\_pending | ✖ | ✔ |
| af\_purchase\_canceled* | ✖ | ✔ |
| af\_purchase\_free | ✖ | ✔ |
| af\_purchase\_sandbox\_sdk | ✔ | ✔ |
| af\_purchase\_sandbox\_s2s* | ✖ | ✔ |

* ROI360 Advancedプランでのみ利用できます。

</Accordion>

<Accordion title="サブスクリプション関連イベントへの対応の比較">

| **イベント名** | **レシート検証** | **ROI360ストア収益** |
| --- | --- | --- |
| af\_ars\_trial\_started | ✔ | ✔ |
| af\_ars\_trial\_canceled | ✖ | ✔ |
| af\_ars\_trial\_churned | ✖ | ✔ |
| af\_ars\_trial\_converted | ✖ | ✔ |
| af\_ars\_subscription\_started | ✔ | ✔ |
| af\_ars\_subscription\_canceled | ✖ | ✔ |
| af\_ars\_subscription\_paused | ✖ | ✔ |
| af\_ars\_subscription\_resumed | ✖ | ✔ |
| af\_ars\_subscription\_churned | ✖ | ✔ |
| af\_ars\_subscription\_refunded | ✖ | ✔ |
| af\_ars\_subscription\_billing\_grace | ✖ | ✔ |
| af\_ars\_subscription\_renewed | ✖ | ✔ |
| af\_ars\_subscription\_xgraded | ✖ | ✔ |
| af\_ars\_existing\_subscriber | ✖ | ✔ |
| af\_ars\_sandbox\_sdk | ✔ | ✔ |
| af\_ars\_sandbox\_s2s | ✖ | ✔ |

</Accordion>

<div data-zendesk-anchors="about-purchase-validation=%E8%B3%BC%E5%85%A5%E3%82%B5%E3%83%96%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E6%A4%9C%E8%A8%BC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KCY9DHB7PBM3CZS65WMHR8B5=%E8%B3%BC%E5%85%A5%E3%82%B5%E3%83%96%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E6%A4%9C%E8%A8%BC%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 appsflyer-solutions=%E8%B3%BC%E5%85%A5%E3%82%B5%E3%83%96%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E6%A4%9C%E8%A8%BC%E3%81%AB%E4%BD%BF%E3%81%88%E3%82%8B2%E3%81%A4%E3%81%AE%E6%A9%9F%E8%83%BD h_01KCY9DHB7XKWP0P8WMTSXVT4A=%E8%B3%BC%E5%85%A5%E3%82%B5%E3%83%96%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E6%A4%9C%E8%A8%BC%E3%81%AB%E4%BD%BF%E3%81%88%E3%82%8B2%E3%81%A4%E3%81%AE%E6%A9%9F%E8%83%BD receipt-validation=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC h_01KCY9DHB7DC66Q3H9W9064CZY=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC roi360-store-revenue=roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E6%9C%89%E6%96%99%E6%A9%9F%E8%83%BD h_01KCY9DHB70VN27BYR3ZG0JD86=roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E6%9C%89%E6%96%99%E6%A9%9F%E8%83%BD h_01KSAJM50XFXVQXZC59D1BE5XN=%E9%87%8D%E8%A6%81 compare-receipt-validation-and-roi360-stores-revenue=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%A8roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%AE%E6%AF%94%E8%BC%83 h_01KCY9DHB7RJ89GB5CM29T2AK5=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%A8roi360%E3%82%B9%E3%83%88%E3%82%A2%E5%8F%8E%E7%9B%8A%E3%81%AE%E6%AF%94%E8%BC%83" />
