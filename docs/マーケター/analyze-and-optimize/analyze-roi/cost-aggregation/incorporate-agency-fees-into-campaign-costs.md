---
title: キャンペーン広告費への代理店手数料の追加
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Premium
    - Xpend
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
  created_at: '2021-06-03T13:53:23Z'
  edited_at: '2026-10-28T08:43:25Z'
  id: 4402103019665
  locale: ja
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ja/articles/4402103019665
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** AppsFlyerの有料機能ROI360に含まれる代理店手数料ルールを使用すると、広告配信に対して代理店が請求する料率制の手数料を加算し、キャンペーンの総費用を確認できます。

<div id="overview" />

## 概要

AppsFlyerアカウントの管理者権限を持つ広告主が、ルール作成画面で条件を設定します。指定したアプリやメディアソースの代理店運用キャンペーンに、設定した料率の手数料を加算できます。

ROI360は、アドネットワークのAPIやアトリビューションリンクから取得した広告費に代理店手数料ルールを適用し、手数料を含む総広告費を計算します。この計算は、キャンペーンや広告セットなど、すべての集計単位に適用されます。結果は広告主のダッシュボード、レポート、コストETLに表示されます。代理店やアドネットワークのダッシュボードとレポートには表示されません。**注意**：コストETLレポートには、<Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports#file-fields">代理店手数料用の追加フィールド</Anchor>があります。

代理店手数料ルールを使用すると、広告主は次のことができます。

* 広告キャンペーンに実際にかかった費用の把握
* 広告費レポートの作成にかかる時間と手作業の削減
* 代理店の運用成果の管理
* 過去の広告費データの正確な分析

<div id="procedures" />

## 手順

ルールの確認・追加・編集・削除の手順を、以下で説明します。すべての操作にAppsFlyerの管理者権限が必要です。

<div id="view-rule-list" />

<Accordion title="ルール一覧の確認">

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)アカウント内に作成したすべての代理店手数料ルールを確認するには**：

1. AppsFlyerのサイドメニューから<strong>［設定］</strong>＞<strong>［コスト管理］</strong>を選択します。  
   コスト管理画面に、代理店手数料ルールの一覧が表示されます。ルールは、次のステータスに分類されます。
   * **有効：** 開始日が本日以前で、手数料が少なくとも1回計算されたルール。
   * **無効：** 終了日が過去（本日より前）のルール。
   * **処理待ち：** 処理を待っているデータがあります。ルールを作成した後や日付・料率を編集した後は、処理が完了するまで「処理待ち」となり、その後「有効」または「無効」に変わります。
   * **失敗：** 技術的な理由で計算に失敗しているルール。
2. ［パートナー］［アプリ］［メディアソース］のフィルターで、ルール一覧を絞り込めます。

</Accordion>

<div id="add-rule" />

<Accordion title="ルールの追加">

ルール作成画面で、項目を選択しながらルールを作成できます。 **ヒント！** この記事を詳しく読む前に、ルール作成画面を実際に操作し、使い方を確認しておくと理解しやすくなります。

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)新しいルールを追加するには**：

1. AppsFlyerのサイドメニューから<strong>［設定］</strong>＞<strong>［コスト管理］</strong>を選択します。
2. ＋<strong>［代理店手数料ルールを追加］</strong>をクリックします。  
   代理店手数料ルールの画面が表示されます。
3. パートナー（代理店）を選択します。
4. 1つ以上のアプリを選択するか、<strong>［すべてのアプリ］</strong>を選択します。<strong>［すべてのアプリ］</strong>を選択すると、今後アカウントに追加するアプリも含め、すべてのアプリにルールが適用されます。
5. 1つ以上のメディアソースを選択するか、［すべてのメディアソース］にチェックを入れます。［すべてのメディアソース］にチェックを入れると、今後追加するものも含め、すべてのメディアソースにルールが適用されます。
   * 運用媒体が非開示の代理店の場合、<strong>［すべてのメディアソース］</strong>がデフォルトで選択され、個別のメディアソースは選択できません。
   * 選択したアプリで運用媒体が非開示の場合、メディアソースのドロップダウンは無効のままです。ただし、そのアプリでMeta広告またはX広告を使用している場合は例外です。これらの媒体は常に開示されます。
6. 開始日を入力します。
7. 任意で、終了日を入力します。
8. 代理店手数料の料率（%）を入力します。－100～100の値を指定できます（代理店の割引や返金を反映する場合は、マイナスの値を使用します）。
9. <strong>［ルールを作成］</strong>をクリックします。

<div id="note" />

> 📘 **注意**
>
> 次のエラーがある場合、ルールを作成できません。
>
> * 必須フィールドが入力されていません。すべての必須フィールドが入力されていることを確認してください。
> * ルールの条件が既存のルールと競合しています。アプリまたはメディアソースを変更してください。

</Accordion>

<div id="edit-duplicate-or-delete-a-rule" />

<Accordion title="ルールの編集・複製・削除">

**確認事項：**

ルールを編集または削除すると、最大90日前までの計算済みデータが上書きされます。

* ルールを編集した場合は、更新後の代理店手数料率が総費用に反映されます。
* ルールを削除した場合は、総費用から代理店手数料が除かれます。

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)ルールを編集・複製・削除するには**：

1. [ルール一覧](/docs/incorporate-agency-fees-into-campaign-costs#view-rule-list)で、対象のルールにカーソルを合わせます。
2. 右側の**メニュー**⋮をクリックします。
3. 実行する操作を選択します。

<div id="note-1" />

> 📘 **注意**
>
> ルールの作成後は、代理店と開始日を変更できません。変更する必要がある場合は、既存の設定を削除して新しいルールを作成してください。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| 代理店とアドネットワーク | 代理店とアドネットワークは、ルールを閲覧できません。また、代理店手数料ルールを適用した総広告費は、代理店とアドネットワークのダッシュボードやレポートには表示されません。 |
| データの更新・反映 | <Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">1日に複数回更新</Anchor>。初回の計算結果が表示されるまで、最大5時間かかる場合があります。 |
| 過去のデータ | 最大90日前までのデータに適用するルールを作成できます。 |
| ルールの処理頻度 | 新しい代理店手数料ルールは、**4時間ごと**に処理されます。このため、ルールが適用されるまで最大**4時間**かかる場合があります。 |

仕様と制限事項

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HFV23CD24HQVC82NNNBDKFRH=%E6%A6%82%E8%A6%81 procedures=%E6%89%8B%E9%A0%86 h_01HFV23CD38RXRT59DNGZAADV1=%E6%89%8B%E9%A0%86 h_01HFV23CD3F5ZPT4D3X8PHJS4T=view-rule-list h_01HFV23CD3MZSZDKTH8CZAY954=add-rule h_01HFV23CD3W6J9QSPHBV9NE19S=%E6%B3%A8%E6%84%8F h_01HFV23CD3SHHR1HRK6DX4QCET=edit-duplicate-or-delete-a-rule h_01HFV23CD3QH6X0WJEAFTMXNMD=%E6%B3%A8%E6%84%8F-1 h_01HFV23CD3E486GBA5XBSN41RA=traits-and-limitations" />
