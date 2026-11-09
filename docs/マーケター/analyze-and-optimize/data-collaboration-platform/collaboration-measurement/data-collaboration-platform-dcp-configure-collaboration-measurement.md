---
title: データコラボレーションプラットフォーム（DCP）- コラボレーション計測 - 概要
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2025-01-27T09:58:46Z'
  edited_at: '2026-10-14T09:39:43Z'
  id: 32147174933905
  locale: ja
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/ja/articles/32147174933905
---
**概要：** DCPを設定して、コンバージョン、エンゲージメント、キャンペーンマッピングデータに基づいてSKUレベルの帰属を行う方法を学びます。

<div id="overview" />

## 概要

<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement">コンバージョン、エンゲージメント、キャンペーンマッピング</Anchor>データを準備した後、DCPを設定してそれらを測定と帰属に使用できます。

1. [**キャンペーンタイプを定義する**](#キャンペーンタイプを選択しますオンサイトオフサイトまたは両方) – オンサイト、オフサイト、または両方を選択します。これにより、DCPがデータを処理し、必要な設定タスクを設定します。
2. [**タスクを割り当てる**](#設定タスクを割り当てる) – オーナーは、関連データにアクセスできるコラボレーターに各設定タスクを割り当てます。
3. [**タスクを設定する**](#オンサイトおよびオフサイトでのキャンペーン計測) – コラボレーターは、コンバージョン、エンゲージメント、キャンペーンマッピングを設定します。これには、すべてのデータが接続され、マッピングされ、帰属の準備が整うように、オンサイトおよびオフサイトキャンペーンを設定することが含まれます。
4. <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-run-and-manage-measurement">**測定を実行および管理する**</Anchor> - 測定をライブまたは過去のものとして実行し、それらを複製したり、再実行したり、範囲を変更したりします。

<div id="start-the-measurement-setup" />

## 測定の設定を開始します。

測定の設定を開始するには、次の手順に従います。

1. AppsFlyerのサイドメニューから、**コラボレーション** > **データクリーンルーム**に移動します。
2. **データコラボレーションプラットフォーム**ページで、設定したいコラボレーションを選択します。
3. コラボレーションページで、次の**いずれか**の手順を実行します：
   * これがコラボレーション内で最初の測定設定である場合は、<strong>測定を設定します。</strong>をクリックします。**測定を作成**ページが表示されます。
   * コラボレーション内にすでに測定セットがある場合は、測定選択パネルのプラス記号をクリックします。**測定を作成**ページが表示されます。

<Image align="center" alt="start-measurement.png" src="https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png" />

<div id="select-campaign-type-on-site-off-site-or-both" />

## キャンペーンタイプを選択します：オンサイト、オフサイト、または両方。

オンサイトとオフサイトのキャンペーンタイプは、コンバージョンが発生する場所と帰属の処理方法が異なるため、コラボレーションのオーナーはコラボレーション測定を設定する前にキャンペーンタイプを指定する必要があります。詳細については、以下を参照してください：<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaign-measurement">オンサイト対。オフサイトキャンペーン測定</Anchor>。

キャンペーンタイプを選択するには、次の手順に従ってください：

1. [測定設定を開始](#測定の設定を開始します)。
2. **測定作成**ページで、<Image alt="オンサイトアイコン.png" src="https://files.readme.io/c9ff0bb1e2c31527ee38a9403a6180e3ecd4c3ad105935fb59ed14c2474f6039-32148924980113.png" width="3.27%" /> **オンサイト, <Image alt="オフサイトアイコン.png" src="https://files.readme.io/6de5841985237de221c74d427ad06f719572000aafe8077c7cef64e53ee8caf5-32156666763921.png" width="3.3%" /> オフサイト**、または両方を選択します。次のいずれかに進んでください：**1つ**。
   * [オンサイトキャンペーンを設定](#オンサイトおよびオフサイトでのキャンペーン計測)、
   * [オフサイトキャンペーンを設定](#configure-offsite-campaign-measurement)、
   * [オンサイトとオフサイトのキャンペーンを組み合わせて設定](#configure-combined-onsite-and-offsite-campaign-measurement)。

<div id="assign-configuration-task" />

## 設定タスクを割り当てる

測定設定ページには、変換、エンゲージメント、キャンペーンマッピング、メディアパートナー、およびルックバックウィンドウ設定の5つの主要タスクが含まれています。

DCPアカウントの所有者は、データプライバシーを確保し、責任の分担を反映させるために、コラボレーターにタスクを割り当てることができます。例えば、1人のコラボレーターがエンゲージメントデータを扱い、もう1人が変換を扱うことがあります。コラボレーターは、割り当てられたタスクにのみアクセスできます。

<div id="assign-a-configuration-task-to-a-collaborator" />

<Accordion title="コラボレーターに設定タスクを割り当てる">

上記のいずれかのタスクを割り当てるには、以下の手順に従ってください：

1. [測定設定を開く](#測定の設定を開始します)。
2. 上記の4つのタスクそれぞれについて、**担当者**リストから、そのタスクを担当するコラボレーターを選択します。
   * **変換タスク：** 変換をホストするプラットフォームを持つコラボレーターに割り当てます。
   * **キャンペーンタスク：** 変換をホストするプラットフォームを持つコラボレーターに割り当てます。
   * **エンゲージメントタスク:** ユーザーエンゲージメントが発生するコラボレーターに割り当てます。
   * **メディアパートナータスク:** オフサイトキャンペーンに使用されるメディアパートナーアカウントを持つコラボレーターに割り当てます。
   * **ルックバックウィンドウタスク** – 自動的にコラボレーションオーナーに割り当てられます。他のコラボレーターを任意で割り当てることができます。

</Accordion>

<div id="remove-the-configuration-task-assignment-from-a-collaborator" />

<Accordion title="コラボレーターから構成タスクの割り当てを削除します。">

場合によっては、コラボレーターから構成タスクの割り当てを取り消す必要があるかもしれません。コラボレーションオーナーが割り当てを削除すると、次のことが発生します：

* コラボレーターは、未割り当てのタスクへのアクセスを直ちに失います。
* そのタスクのためにコラボレーターが以前に提供した構成は破棄されます。
* コラボレーションの測定が停止します。

構成タスクの割り当てを削除するには、以下の手順に従ってください：

1. コラボレーション測定に移動し、測定設定を開くを確認します。
2. 関連する構成ステップで、**割り当て先**リストから割り当てられたコラボレーターを削除します。

</Accordion>

<div id="configure-on-site-and-off-site-campaign-measurement" />

## オンサイトおよびオフサイトでのキャンペーン計測

測定設定でキャンペーン測定のセットアップを構成します。測定がオンサイト、オフサイト、またはオンサイトとオフサイトの組み合わせであるかに基づいて、以下の手順を使用します。

<div id="configure-onsite-campaign-measurement::4f9b35af" />

<Accordion title="オンサイトキャンペーン測定を構成します。">

<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-campaigns">オンサイトキャンペーン</Anchor>を設定するには、以下の手順に従ってください：

1. [測定設定を開始](#測定の設定を開始します)。
2. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-campaigns-task">キャンペーンタスクを設定する</Anchor>
3. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-conversions-task">コンバージョンタスクを設定する</Anchor>
4. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-engagements-task">エンゲージメントタスクを設定する</Anchor>
5. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-lookback-windows-task">ルックバックウィンドウタスクを設定する</Anchor>

</Accordion>

<div id="configure-offsite-campaign-measurement" />

<Accordion title="オフサイトキャンペーンの測定を設定する">

<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">オフサイトキャンペーン</Anchor>を設定するには、次の手順に従ってください：

1. [測定設定を開始](#測定の設定を開始します)。
2. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-campaigns-task">キャンペーンタスクを設定する</Anchor>
3. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-conversions-task">コンバージョンタスクを設定する</Anchor>
4. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-media-partners-task">メディアパートナータスクを設定する</Anchor>
5. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-lookback-windows-task">ルックバックウィンドウタスクを設定する</Anchor>

</Accordion>

<div id="configure-combined-onsite-and-offsite-campaign-measurement" />

<Accordion title="オンサイトとオフサイトのキャンペーン測定を統合して設定する">

<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">オンサイトとオフサイトの統合キャンペーン</Anchor>を設定するには、次の手順に従ってください：

1. [測定設定を開始](#測定の設定を開始します)。
2. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-campaigns-task">キャンペーンタスクを設定する</Anchor>
3. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-conversions-task">コンバージョンタスクを設定する</Anchor>
4. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-engagements-task">エンゲージメントタスクを設定する</Anchor>
5. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-media-partners-task">メディアパートナータスクを設定する</Anchor>
6. <Anchor target="_blank" href="/marketers/ja/docs/set-up-the-lookback-windows-task">ルックバックウィンドウタスクを設定する</Anchor>

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01K3EHANCCZ703MMMM5PTEF68B=%E6%A6%82%E8%A6%81 open-measurement-settings=%E6%B8%AC%E5%AE%9A%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%92%E9%96%8B%E5%A7%8B%E3%81%97%E3%81%BE%E3%81%99 h_01JJKK3CQ8F9Q7VM7MM9AFKNN5=%E6%B8%AC%E5%AE%9A%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%92%E9%96%8B%E5%A7%8B%E3%81%97%E3%81%BE%E3%81%99 select-campaign-type-onsite-offsite-or-both=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%82%BF%E3%82%A4%E3%83%97%E3%82%92%E9%81%B8%E6%8A%9E%E3%81%97%E3%81%BE%E3%81%99%E3%82%AA%E3%83%B3%E3%82%B5%E3%82%A4%E3%83%88%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E3%81%BE%E3%81%9F%E3%81%AF%E4%B8%A1%E6%96%B9 h_01K3EHANCCW8PQ8NWC6ZHWCMGT=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%82%BF%E3%82%A4%E3%83%97%E3%82%92%E9%81%B8%E6%8A%9E%E3%81%97%E3%81%BE%E3%81%99%E3%82%AA%E3%83%B3%E3%82%B5%E3%82%A4%E3%83%88%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E3%81%BE%E3%81%9F%E3%81%AF%E4%B8%A1%E6%96%B9 assign-configuration-task=%E8%A8%AD%E5%AE%9A%E3%82%BF%E3%82%B9%E3%82%AF%E3%82%92%E5%89%B2%E3%82%8A%E5%BD%93%E3%81%A6%E3%82%8B h_01K3EHANCCW97TV88ECVMQKF2N=%E8%A8%AD%E5%AE%9A%E3%82%BF%E3%82%B9%E3%82%AF%E3%82%92%E5%89%B2%E3%82%8A%E5%BD%93%E3%81%A6%E3%82%8B h_01K3EHANCD71R47V88DR61CTMV=assign-a-configuration-task-to-a-collaborator h_01K3EHANCDF1HMTV8X35Q1RHTS=remove-the-configuration-task-assignment-from-a-collaborator configure-onsite-campaign-measurement=%E3%82%AA%E3%83%B3%E3%82%B5%E3%82%A4%E3%83%88%E3%81%8A%E3%82%88%E3%81%B3%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E3%81%A7%E3%81%AE%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E8%A8%88%E6%B8%AC h_01K3EHANCD936QN2MKFY5QSDBZ=%E3%82%AA%E3%83%B3%E3%82%B5%E3%82%A4%E3%83%88%E3%81%8A%E3%82%88%E3%81%B3%E3%82%AA%E3%83%95%E3%82%B5%E3%82%A4%E3%83%88%E3%81%A7%E3%81%AE%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E8%A8%88%E6%B8%AC h_01KJWCMN3XRTS3361N08RT1SD6=configure-onsite-campaign-measurement::4f9b35af h_01KJWCMN3XRXW6A71P5678AHH1=configure-offsite-campaign-measurement h_01KJWCMN3XKD8YJVPQEZ53K819=configure-combined-onsite-and-offsite-campaign-measurement" />
