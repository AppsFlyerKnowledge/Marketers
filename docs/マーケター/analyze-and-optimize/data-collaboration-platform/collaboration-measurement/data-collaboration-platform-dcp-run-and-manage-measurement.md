---
title: Data collaboration platform（DCP）｜計測の実行と管理
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2026-03-04T10:59:23Z'
  edited_at: '2026-10-14T09:23:56Z'
  id: 44427723216017
  locale: ja
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/ja/articles/44427723216017
---
> **概要：** オンサイトまたはオフサイトの計測を設定した後、ライブ計測または過去データ計測として実行できます。目的に応じて、継続的にパフォーマンスを計測するか、特定期間の結果を検証するかに応じてモードを選択します。

## 計測の実行モードについて

<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#オンサイトおよびオフサイトでのキャンペーン計測">オンサイトまたはオフサイトの計測設定が完了</Anchor>すると、次に計測の実行方法を選択します。

利用できる実行モードは以下の2つです：

* **ライブ計測**：定期的に更新される継続的な計測で、新しいデータが追加されるたびにライブダッシュボード上でパフォーマンスをモニタリングできます。
* **過去データ計測**：特定の期間に対して一度だけ実行される計測で、過去データダッシュボード上で閲覧・分析できます。

### ライブ計測と過去データ計測の違い

| 項目 | 過去データ計測 | ライブ計測 |
| --- | --- | --- |
| 実行タイミング | **オンデマンド**（手動実行） | **自動**（日次実行） |
| データソース | **過去データのアップロード**を使用 | **SDK / ETLの設定**が必要で、定義された時間間隔で実行 |
| 対応ソースタイプ | <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">追加</Anchor>および<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">上書き（スナップショット）</Anchor> | <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">追加タイプのカスタムソース</Anchor> |
| 期間設定 | **開始日と終了日**を選択（利用可能データから） | **開始日のみ選択**（有効化時に過去期間を自動算出し、その後データを蓄積） |
| 計測数 | 複数可 | 1つのみ |

### 必要な計測の選び方

以下のガイドを参考に、目的に合った計測を選択してください。

**ライブ計測を選ぶ場合**

* 新しいデータの到着に応じて継続的に更新される計測
* パフォーマンスを常時モニタリングできるダッシュボード
* 長期的かつ常時稼働の計測（単発分析ではない）

**過去データ計測を選ぶ場合**

* 特定期間に対する単発の計測を実行する
* キャンペーン終了後にパフォーマンスを分析する
* ルックバック期間を変更してアトリビューションへの影響を確認する「what-if分析」を行う

**ヒント：** 設定の検証や特定期間の確認から始めたい場合は、まず<strong>過去データ計測を利用してください。</strong>継続的なモニタリングが必要になった段階で、**ライブ計測**に切り替えると便利です。

## ライブ計測の実行

**始める前に：** <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#オンサイトおよびオフサイトでのキャンペーン計測">計測設定ページでオンサイトまたはオフサイトの計測キャンペーンを設定してください。</Anchor>

1. **計測設定**ページで、<strong>「今すぐ実行」</strong>をクリックします。

   もしも<strong>「今すぐ実行」</strong>が無効になっている場合、計測タスクが未完了の状態です。必要な設定をすべて完了してください。
2. **実行準備**のダイアログで、**ライブダッシュボード**を選択します。

   > 📘 **注意**
   >
   > * 計測に<Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">上書きタイプ</Anchor>のソースを使用している場合は、**過去データダッシュボード**のみ利用可能です。**ライブダッシュボード**には**追加型タイプのソース**（またはAppsFlyer SDKのアプリ内イベント）が必要です。
   > * 1つのコラボレーション内で**同時に実行できるライブ計測は1つのみ**です。すでに実行中のライブ計測がある状態で新しいものを開始すると、既存の計測を一時停止するよう求められます。

3. ダッシュボード名を変更するか、デフォルト名のまま使用します。
4. **計測開始日**を選択します。デフォルトは今日の日付ですが、日付ピッカーから過去の日付を選択することができます。（データソースに存在する日付のみを選択できます。）
5. <strong>「開始」</strong>をクリックしてライブ計測を開始します。コラボレーション計測ページに遷移します。
6. 自動バリデーションが完了した後、「**今すぐ実行**」をクリックします。

## 過去データ計測の実行

**始める前に：** <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#オンサイトおよびオフサイトでのキャンペーン計測">計測設定ページでオンサイトまたはオフサイトの計測キャンペーンを設定してください。</Anchor>

1. **計測設定**で、<strong>「今すぐ実行」</strong>をクリックします。  
   もしも<strong>「今すぐ実行」</strong>が無効になっている場合、計測タスクが未完了の状態です。必要な設定をすべて完了してください。
2. **実行準備**ダイアログで、**過去データダッシュボード**を選択します。
3. ダッシュボード名を変更するか、デフォルト名のまま使用します。
4. **計測日付範囲**を選択します（データソースに存在する日付のみ選択可能）：
   * **開始日**を設定
   * **終了日**を設定
5. <strong>「開始」</strong>をクリックして、過去データ計測を開始します。コラボレーション計測ページに遷移します。
6. 自動バリデーションが完了した後、「**今すぐ実行**」をクリックします。

## 計測の管理

計測の設定および実行後は、コラボレーション計測ページの計測パネルから管理できます。ライブ計測の一時停止・再開、日付の変更、過去データ計測の再実行、既存設定の複製などが可能です。

### コラボレーション計測ページ

[![](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)

<div id="pause-or-restart-live-measurement" />

<Accordion title="ライブ計測の一時停止・再開">

#### 説明

* **A** - 計測パネル
* **B** - 選択中の計測
* **C** - 共有トグル
* **D** - オプションメニュー

1. コラボレーション計測ページを開きます。
2. 計測パネルから**ライブダッシュボード**を選択します（[A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#コラボレーション計測ページ)）。
3. オプションメニュー（[D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#コラボレーション計測ページ)）を開き、**計測設定**をクリックします。
4. **計測設定**ページで、次のいずれかを行います：
   * ライブ計測を**一時停止**：　**計測を有効化**をオフにし、**確認ダイアログ**で承認
   * ライブ計測を**再開**：　**計測を有効化**をオンにする

</Accordion>

<div id="change-measurement-start-and-end-dates" />

<Accordion title="計測期間の変更">

次の期間を変更可能です：

* ライブ計測の**開始日**
* 過去データ計測の**開始日と終了日**

測定の開始日と終了日を変更するには、次の手順に従ってください:

1. コラボレーション計測ページを開きます。
2. 計測パネル ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#コラボレーション計測ページ))から対象の計測を選択します。
3. オプションメニュー（[D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#コラボレーション計測ページ)）を開き、**計測設定**をクリックします。
4. **計測設定**ページで、ペンのアイコンをクリックします。
5. 開始日または終了日をクリックします。
6. 日付ピッカーから新しい日付を選択します。

</Accordion>

<div id="rerun-a-historical-measurement" />

<Accordion title="過去データ計測の再実行">

過去データ計測を再実行すると、最新データに基づいてアトリビューションが再計算され、既存の結果は新しい結果に置き換えられます。

1. コラボレーション計測ページを開きます。
2. 計測パネル ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#コラボレーション計測ページ))から対象の計測を選択します。
3. オプションメニューを開き ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#コラボレーション計測ページ))、**再実行**をクリックします。
4. 確認メッセージで、**再実行**をクリックします。
5. 自動バリデーションが完了した後、「**今すぐ実行**」をクリックします。

</Accordion>

<div id="duplicate-a-live-or-historical-measurement" />

<Accordion title="ライブ計測・過去データ計測の複製">

複製すると、既存設定をもとに新しい計測を作成できます。設定を変更して新たな計測として実行できます。

1. コラボレーション計測ページを開きます。
2. 計測パネル ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#コラボレーション計測ページ))から対象の計測を選択します。
3. オプションメニューを開き ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#コラボレーション計測ページ))、**複製**をクリックします。
4. 複製された**計測設定**ページで、必要に応じて設定を調整します。

</Accordion>

<div id="share-a-dashboard" />

<Accordion title="ダッシュボードの共有">

**共有**トグルをオンにすることで、ダッシュボードを共同作業者と共有できます。**共有**がオンのとき、ダッシュボードおよびその計測結果は他のユーザーからも閲覧可能になります。

**共有**がオンのときに可能な操作は、ユーザーがダッシュボードに**割り当てられているかどうか**によって異なります。

* **割り当てユーザーができること：**
  * ダッシュボードの**閲覧**
  * **計測設定**を開いて、**自分に割り当てられたタスクのみ編集**

* **割り当てユーザーができないこと：**
  * **共有**トグルのオン / オフ切り替え
  * **計測の再実行**

* **未割り当てユーザー**は、共有されていてもアクセス権が制限されます（例：結果サマリーが見えない、再実行や共有ができない）。

ダッシュボードを共有する方法：

1. コラボレーション計測ページを開き、計測パネル（A）から共有したい**ダッシュボード**（[A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#コラボレーション計測ページ)）を選択します。
2. **共有**（[C](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#コラボレーション計測ページ)）をオンにします。ダッシュボードは共同作業者の計測ページから利用可能になります。
3. **共有をオフにする**ことで、共有は停止されます。オフの場合は、自分および適切な権限を持つユーザーのみがアクセス可能です。

</Accordion>

<div data-zendesk-anchors="about-the-measurement-run-modes=%E8%A8%88%E6%B8%AC%E3%81%AE%E5%AE%9F%E8%A1%8C%E3%83%A2%E3%83%BC%E3%83%89%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KJW81RSZPK2Y1PSAF9FSMXB6=%E8%A8%88%E6%B8%AC%E3%81%AE%E5%AE%9F%E8%A1%8C%E3%83%A2%E3%83%BC%E3%83%89%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 live-vs-historical-measurements=%E3%83%A9%E3%82%A4%E3%83%96%E8%A8%88%E6%B8%AC%E3%81%A8%E9%81%8E%E5%8E%BB%E3%83%87%E3%83%BC%E3%82%BF%E8%A8%88%E6%B8%AC%E3%81%AE%E9%81%95%E3%81%84 h_01KJW81RSZBG5ZC8HE9WFXE34D=%E3%83%A9%E3%82%A4%E3%83%96%E8%A8%88%E6%B8%AC%E3%81%A8%E9%81%8E%E5%8E%BB%E3%83%87%E3%83%BC%E3%82%BF%E8%A8%88%E6%B8%AC%E3%81%AE%E9%81%95%E3%81%84 choose-the-measurement-you-need=%E5%BF%85%E8%A6%81%E3%81%AA%E8%A8%88%E6%B8%AC%E3%81%AE%E9%81%B8%E3%81%B3%E6%96%B9 h_01KJW81RSZQG21Z0MRHWPMD69F=%E5%BF%85%E8%A6%81%E3%81%AA%E8%A8%88%E6%B8%AC%E3%81%AE%E9%81%B8%E3%81%B3%E6%96%B9 run-a-live-measurement=%E3%83%A9%E3%82%A4%E3%83%96%E8%A8%88%E6%B8%AC%E3%81%AE%E5%AE%9F%E8%A1%8C h_01KJW81RT0Q1RWEHZP66B5141M=%E3%83%A9%E3%82%A4%E3%83%96%E8%A8%88%E6%B8%AC%E3%81%AE%E5%AE%9F%E8%A1%8C h_01KJW81RT0N37ARE5570X7MYJF=%E6%B3%A8%E6%84%8F run-a-historical-measurement=%E9%81%8E%E5%8E%BB%E3%83%87%E3%83%BC%E3%82%BF%E8%A8%88%E6%B8%AC%E3%81%AE%E5%AE%9F%E8%A1%8C h_01KJW81RT0QECMGBTRFSETA5A8=%E9%81%8E%E5%8E%BB%E3%83%87%E3%83%BC%E3%82%BF%E8%A8%88%E6%B8%AC%E3%81%AE%E5%AE%9F%E8%A1%8C manage-measurements=%E8%A8%88%E6%B8%AC%E3%81%AE%E7%AE%A1%E7%90%86 h_01KJW81RT046RE5FVHPGEDMCC5=%E8%A8%88%E6%B8%AC%E3%81%AE%E7%AE%A1%E7%90%86 the-collaboration-measurement-page=%E3%82%B3%E3%83%A9%E3%83%9C%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%83%9A%E3%83%BC%E3%82%B8 h_01KJWNTR04PRG54W0GZVGQY72X=%E3%82%B3%E3%83%A9%E3%83%9C%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%83%9A%E3%83%BC%E3%82%B8 legend=%E8%AA%AC%E6%98%8E h_01KJWNF8NAJ9NT5T8NAVTCMZVA=%E8%AA%AC%E6%98%8E h_01KJW81RT0A148W49X0BR0V9YM=pause-or-restart-live-measurement h_01KJW81RT0GYDCZCXXV2G5EJD7=change-measurement-start-and-end-dates h_01KJW81RT054CCYMTKFN7TS1XV=rerun-a-historical-measurement h_01KJW81RT0RKQJRCTRVP36YBKV=duplicate-a-live-or-historical-measurement h_01KJW81RT0C3R95JQVPGSZ043B=share-a-dashboard" />
