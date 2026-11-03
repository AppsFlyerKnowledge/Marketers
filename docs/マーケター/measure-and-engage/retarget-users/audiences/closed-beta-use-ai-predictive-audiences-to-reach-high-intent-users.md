---
title: ［Closed Beta機能］AIによるPredictive Audiences｜高意欲ユーザーへのリーチ
metadata:
  keywords:
    - Premium
    - Beta
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2026-04-15T09:20:36Z'
  edited_at: '2026-10-14T09:23:27Z'
  id: 45762246838801
  locale: ja
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ja/articles/45762246838801
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** Predictive Audiencesは、AIを活用して特定のアクション（購入など）を実行する可能性が高いユーザーのオーディエンスを作成する機能です。これにより、購買意欲の高いユーザーに効率的にアプローチし、無駄な広告費を削減しながらキャンペーン効果を最大化できます。

<Embed title="［Closed Beta機能］AIによるPredictive Audiences｜高意欲ユーザーへのリーチ" typeOfEmbed="youtube" url="https://www.youtube.com/embed/LuEJrfARo5g" providerUrl="https://www.youtube.com" />

## Predictive Audiencesについて

AppsFlyer <Anchor target="_blank" href="/marketers/ja/docs/audiences-guide">Audiences</Anchor>の機能であるPredictive Audiencesは、AIを活用して特定のアクションを実行する可能性が高いユーザーのオーディエンスを作成します。例えば、今後7日以内に購入する可能性が高いユーザーを予測し、そのユーザー層にキャンペーンを集中させることで、より効率的な広告運用を実現できます。

購入確率の範囲を調整することで、より購買意欲の高いユーザーに絞り込んだ小規模なオーディエンスを作成することも、リーチを広げた大規模なオーディエンスを作成することも可能です。。作成したオーディエンスは連携済みパートナーへ配信でき、作成後は毎日更新されるとともに、継続的かつ自動的に各パートナーへ送信されます

## Predictive Audienceを作成する

### 事前準備

Predictive Audiencesを利用するには、以下の条件を満たしている必要があります。

* **前提条件：** AppsFlyer <Anchor target="_blank" href="/marketers/ja/docs/audiences-guide">Audiences</Anchor>の有償契約が必要です。Predictive Audiencesは現在ベータ版として提供されており、アカウント単位で有効化されます。利用を希望する場合は、担当のCSMまでお問い合わせください。

<div id="step-1-define-the-goal" />

<Accordion title="ステップ１：予測目標を設定する">

このステップでは、対象アプリ、ターゲットイベント、および予測目標を選択し、Predictive Audiencesに何を予測させるかを定義します。

**予測目標を設定する方法：**

1. AppsFlyerのサイドメニューから **Engage > Audiences** をクリックします。
2. **Audiences**の画面を開いて**New predictive audience**をクリックします。
3. オーディエンス名を入力します。

   [<Image alt="Define goal (values entered).png" src="https://files.readme.io/9dd260c4552be231e2f313db451d92501b6090664e6f7010c660357f9af71efb-45796747476497.png" width="1666px" />](https://files.readme.io/9dd260c4552be231e2f313db451d92501b6090664e6f7010c660357f9af71efb-45796747476497.png)
4. アプリを選択します。
5. ターゲットイベントを選択します。
6. 予測目標を選択します。（**Likely to purchase**（購入する可能性が高いユーザー））
7. **次へ**をクリックしてください。

</Accordion>

<div id="step-2-set-the-probability-range" />

<Accordion title="ステップ２：購入確率の範囲を設定する">

このステップでは、精度とリーチのバランスを考慮しながら購入確率の範囲を設定します。最小確率のしきい値を高く設定すると、オーディエンス規模は小さくなりますが、購買意欲の高いユーザーに絞り込むことができます。一方で、しきい値を低く設定すると、パフォーマンスを維持しながらより多くのユーザーへリーチできます。

推奨プリセットを選択することも、グラフ上のマーカーをドラッグして範囲を自由に調整することも可能です。範囲を変更すると推定オーディエンスサイズがリアルタイムで更新されるため、リーチ規模とコンバージョン確率のトレードオフを確認しながら調整できます。

**購入確率の範囲を設定する方法：**

1. プリセット（**購入意向の高いユーザー層**、**バランス重視**、**リーチ最大化**）を選択すると、初期設定の範囲が適用されます。AppsFlyerでは、**バランス重視**を選択することを推奨しています。

**または**

2. 範囲をカスタマイズする場合は、グラフ上の最小値および最大値のマーカーをドラッグします。

   <Image alt="Set probability range Correct version.png" src="https://files.readme.io/8dd9b6368d86e5641e99e7fe66e137b1137adf8fdf7760d597826f7c2d5be745-45796825322385.png" width="1898px" />

   選択内容に応じて、**推定オーディエンス規模**がリアルタイムで更新されます。

#### オーディエンス比較（任意）：

オーディエンス比較は、作成するPredictive Audienceを1つまたは複数の既存オーディエンスと比較できるオプション機能です。広告費用対効果（ROAS）やコンバージョン率などの主要指標（KPI）に基づいてパフォーマンスを比較できます。比較対象には任意のオーディエンスを選択できますが、現在パフォーマンスデータを利用できるのは、Facebook、TikTok、Google、またはSnapに接続されたキャンペーンのみです。

</Accordion>

<div id="step-3-connect-to-partners" />

<Accordion title="ステップ３：パートナーに接続する">

このステップでは、Predictive Audienceをパートナーに接続し、作成時に有効化およびアップロードできるようにします。

**パートナーに接続してオーディエンスを有効化する方法：**

1. 既存のパートナー接続を選択するか、新しい接続を追加します。

   [<Image alt="Connect to partners.png" src="https://files.readme.io/3fd67bfe6d3fd760ad1569c8e0b360432f7874d152804cbef9a4925189837e0c-45796884976401.png" width="1633px" />](https://files.readme.io/3fd67bfe6d3fd760ad1569c8e0b360432f7874d152804cbef9a4925189837e0c-45796884976401.png)
2. 右側の**Summary**で設定内容を確認します。
3. **接続・完了**をクリックします。

最初のPredictive Audienceは24時間以内に作成され、パートナーとの連携が自動的に有効化されます。

作成後、新しいPredictive Audienceは**Audiences**のテーブルに表示されます。

</Accordion>

## 仕様および制限事項

| 特性 | 説明 |
| --- | --- |
| 提供状況 | ベータ機能として提供されており、アカウント単位で有効化されます。利用には明示的な申し込みが必要です。現在はECアプリのみ対応しています。 |
| 予測期間 | 今後7日以内に購入する可能性を予測します。 |
| １オーディエンスごとに１アプリ | 複数アプリを対象としたPredictive Audienceには対応していません。 |
| 対象条件に基づく選択およびデータ要件 | 一定量以上のデータを持つ対象アプリおよびイベントのみ選択リストに表示されます（例：過去30日間のアクティブユーザー数が1,000人以上）。 |
| データ保護 | AIを活用したAudiences機能を提供するため、お客様のオーディエンスデータが処理される場合があります。アカウントデータが外部に共有されることはなく、内部モデルおよび予測精度の向上のためにのみ利用されます。 |
| 毎日の更新 | オーディエンスは毎日更新され、パートナーへアップロードされます。 |

<div data-zendesk-anchors="about-predictive-audiences=predictive-audiences%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KP871KNVB69BFATSZYVK9SMM=predictive-audiences%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 create-a-predictive-audience=predictive-audience%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B h_01KP871KNVC3W8WNA9XVCFYCMA=predictive-audience%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B prerequisites=%E4%BA%8B%E5%89%8D%E6%BA%96%E5%82%99 h_01KP871KNVHD2VK8BQMGQ42QX0=%E4%BA%8B%E5%89%8D%E6%BA%96%E5%82%99 h_01KP8835A2Z5QRHGJKR7BH6H1W=step-1-define-the-goal h_01KP8835A2746F64JRHCF9CVF2=step-2-set-the-probability-range compare-audiences-optional=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E6%AF%94%E8%BC%83%E4%BB%BB%E6%84%8F h_01KPJJH00TMZ2NQKPDN07RW1B1=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E6%AF%94%E8%BC%83%E4%BB%BB%E6%84%8F h_01KP8835A203NTEVCS3VPQDB0D=step-3-connect-to-partners traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%8A%E3%82%88%E3%81%B3%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KP871KNVWVAQMXYXNT6Q0D0P=%E4%BB%95%E6%A7%98%E3%81%8A%E3%82%88%E3%81%B3%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
