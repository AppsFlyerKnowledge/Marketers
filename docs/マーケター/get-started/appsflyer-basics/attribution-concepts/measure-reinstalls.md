---
title: 再インストールの計測
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2022-10-27T07:37:21Z'
  edited_at: '2026-10-28T09:07:58Z'
  id: 10164066030737
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/10164066030737
---
> **概要**：再インストールとは、ユーザーがアプリをインストールし、アンインストールした後に、再度インストールすることです。再インストールの計測結果は、ノンオーガニックの再インストール、オーガニックの再インストール、リアトリビューション（リターゲティング）のいずれかに分類されます。再インストールを区別することで、アンインストールして再度インストールしたユーザーへの重複課金を防げます。

## 再インストールとは

アプリユーザーがアプリを削除した後、<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window#リアトリビューション期間">リアトリビューション期間内</Anchor>に再度インストールすることです。

再インストールには、リターゲティングキャンペーン（リアトリビューション）、オーガニック、ノンオーガニックの流入元を経由する場合があります。

オーガニックまたはノンオーガニックの流入元を経由し、<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window#リアトリビューション期間">リアトリビューション期間内</Anchor>に行われたものを、再インストールと呼びます。

リターゲティングキャンペーン経由のものは、リアトリビューションと呼びます。

両者では、再インストールとアプリ内イベントのアトリビューション方法が異なります。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window#リアトリビューション期間">リアトリビューション期間</Anchor>外に再度インストールした場合は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window#new-install">新規インストール</Anchor>と呼びます。新規インストールはメディアソースに紐付けられ、広告接触が記録されていない場合はオーガニックとなります。また、新しいリアトリビューション期間が始まります。

再インストールの条件ごとに、AppsFlyerでどのように分類されるかを以下の表に示します。

| 再インストールの流入元 | リアトリビューション期間内か | 再インストール前にリターゲティングキャンペーンに接触したか | 再インストール前にUAキャンペーンに接触したか | AppsFlyerでの分類 |
| --- | --- | --- | --- | --- |
| リターゲティングキャンペーン経由 | はい | はい | いいえ | リアトリビューション |
| オーガニックまたはノンオーガニックの流入元経由 | はい | いいえ | はい／いいえ | 再インストール |
| オーガニックまたはノンオーガニックの流入元経由 | いいえ | いいえ | はい／いいえ | 新規インストール |

## 再インストールを正しく計測することの重要性

再インストールは、ユーザーがアプリに戻り、キャンペーンが機能していることを示す重要な指標です。また、正しく計測することで、<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window#リアトリビューション期間">リアトリビューション期間内</Anchor>にアンインストールと再インストールを行ったユーザーへの重複課金を防ぐことができます。

同様に、再インストール後のアプリ内イベントを元のメディアソース（初回インストール）に紐付けることで、ユーザーエンゲージメントの状況をより的確に把握できます。 UAキャンペーンやリターゲティング広告の効果も確認できます。詳しくは、後述の[アプリ内イベント](#再インストール後のアプリ内イベント)を参照してください。

## 再インストールの流れと計測結果

<div id="reinstall" />

<Accordion title="再インストール">

ユーザーがアプリを初めてインストールした後、アンインストールし、<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window#リアトリビューション期間">リアトリビューション期間内</Anchor>に再インストールします。再インストールには、オーガニック経由とUAキャンペーン経由があります（[例](/docs/measure-reinstalls#examples)を参照）。

この場合、以下のように処理されます。

* このインストールは、メディアソースの成果としては計上されず、ダッシュボードやデータにも表示されません。
* 再インストールのポストバックを受信できるのは、この機能に対応し、AppsFlyerから明示的に権限を付与されたパートナーのみです。広告主は、パートナーの**有効な連携**ページの*インストール*ポストバック欄で、再インストールのポストバックの送信対象を、そのパートナーのみ、またはオーガニックを含むすべてのメディアソースから選択できます。
* アプリ内イベントのアトリビューションについては、[アプリ内イベント](/docs/measure-reinstalls#再インストール後のアプリ内イベント)を参照してください。

</Accordion>

<div id="reattribution" />

<Accordion title="リアトリビューション">

ユーザーがアプリを初めてインストールした後、アンインストールし、リターゲティングキャンペーンに接触してから、<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window#リアトリビューション期間">リアトリビューション期間内</Anchor>に再インストールします。

この場合、以下のように処理されます。

* インストールはリターゲティングのメディアソースに紐付けられ、Overview dashboardのリターゲティング表示と統合表示に反映されます。
  * ユーザー獲得の表示には、リアトリビューションは含まれません。
* その後のすべてのアプリ内イベントは、リターゲティングのメディアソースに紐付けられます（詳しくは[アプリ内イベント](/docs/measure-reinstalls#再インストール後のアプリ内イベント)を参照）。
* インストールポストバックは、リターゲティングのメディアソースに送信されます。

リターゲティング計測の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">こちら</Anchor>をご覧ください。

</Accordion>

## 再インストール後のアプリ内イベント

再インストール後にユーザーが実行したアプリ内イベントは、**再インストール後のイベントのアトリビューション**の設定に応じて、オーガニック、ノンオーガニック、または元のインストールに紐付かないオーガニックとして計測されます（以下のフロー図を参照）。たとえば、アプリを再インストールしたユーザーによるアプリ内購入が、該当するアプリ内イベントです。

[![](https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg)](https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg)

<div id="postreinstall-events-attribution-state" />

<Accordion title="再インストール後のイベントのアトリビューション設定">

<table><thead><tr><th>再インストール後のイベントのアトリビューション設定</th><th>再インストール後</th><th>リアトリビューション後</th></tr></thead><tbody><tr><td><strong>オーガニックのアプリ内イベントとして計測</strong></td><td>元のインストールに紐付かないオーガニック</td><td>リターゲティング</td></tr><tr><td> <strong>初回インストールに紐付ける</strong><span>（1）</span> </td><td>初回インストールのメディアソース</td><td>リターゲティング<span>（2）</span> </td></tr><tr><td colspan="3"><p><span>（1）後述の制限事項を参照してください。</span></p><p><span>（2）主な流入元のフィールドに表示されます。初回インストールのメディアソースは、副次的な流入元のフィールドに表示されます（<span>この情報はローデータでのみ確認できます）。</span></span></p></td></tr></tbody></table>

</Accordion>

<div id="unattributed-organic-inapps" />

<Accordion title="元のインストールに紐付かないオーガニックのアプリ内イベント">

再インストール

* すべてのアプリ内イベントは、<Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison">レポートの方法</Anchor>に応じて、オーガニックとして計上されるか、完全に除外されます。
* アプリ内イベントのconversion\_typeとcampaign\_typeは、"unknown"として報告されます。
* データの集計に使用する日付は、イベントによって異なります。
  * SDK由来のほとんどのアプリ内イベントでは、再インストール日ではなく、アプリのダウンロード日を使用して集計します。
  * SDKコネクターが送信した広告収益イベント（af\_ad\_revenue）では、再インストール日を使用して集計します。

リアトリビューション

* すべてのアプリ内イベントがリターゲティングのメディアソースに紐付けられます。

</Accordion>

<div id="attributed-to-the-first-install" />

<Accordion title="初回インストールに紐付ける（初回インストールに紐付けるモード）">

> 📘 **注意**
>
> 初回インストールに紐付けるモードは、2024年7月31日以降にAppsFlyerに追加されたアプリに自動で適用されます。それ以前に追加した既存アプリについては、AppsFlyerにお問い合わせいただき、このモードへの移行を検討することを推奨します。

このモードにより、広告主はユーザーエンゲージメントをより的確に把握できます。アプリ内イベントをオーガニックではなく元の流入元に紐付けることで、UAキャンペーンやリターゲティング広告の効果を確認できます。

* **初回インストールに紐付けるモードでの再インストール：** 再インストール後に発生するすべてのアプリ内イベントが、元のインストールに紐付けられます（1）。紐付けられたアプリ内イベントのインストール時刻には、再インストール時刻ではなく、初回インストールの時刻が使用されます。たとえば、3月1日にインストールし、3月5日に再インストールした場合、「再インストール後のイベントのアトリビューション」が有効であれば、再インストール後のすべての購入が、3月1日のインストール時刻に紐付けられます。
* **初回インストールに紐付けるモードでのリアトリビューション：** すべてのアプリ内イベントが、主な流入元ではリターゲティング広告に、副次的な流入元では元のインストールに紐付けられます。 (2)

（1）[後述の制限事項を参照してください。](/docs/measure-reinstalls#limitations)

（2）この情報はローデータでのみ確認できます。

> 📘 **注意**
>
> ［**再インストール後のイベントのアトリビューション**］を［**初回インストールに紐付ける**］に設定すると、一部のデータがノンオーガニックのメディアソースに紐付けられるため、ダッシュボードのオーガニックのKPIが低下する場合があります。

#### 初回インストールに紐付けるモードでの計測例

**例1**

ユーザーがアプリをインストールし（0日目）、10ドルの購入を行った後、アンインストールします。

翌日（1日目）、アプリを再インストールして5ドルの購入を行います。

![Reinstall_1.jpg](https://files.readme.io/7e8eccb3a6873b42a1d8503c0f027386728adb2eecbe457451d2e37c0a7b6774-10225445609873.jpg)

このユーザーは再インストール前にも購入しているため、ユニークユーザー数は増えません。

| メディアソース | ユーザー数 | Af\_purchase:<br /><br />ユニークユーザー<br /><br />0日目 | Af\_purchase:<br /><br />ユニークユーザー<br /><br />1日目（累計） | 収益<br /><br />0日目 | 収益<br /><br />1日目（累計） |
| --- | --- | --- | --- | --- | --- |
| Media\_source\_A | 1 | 1 | 1 | $10 | $15 |

同じ`device_identifier`に紐付く収益が増加します。

| Appsflyer\_id | デバイス識別子 | メディアソース | イベント名 | イベント日 |
| --- | --- | --- | --- | --- |
| 111 | XXX | media\_source\_A | install | 0日目 |
| 111 | XXX | media\_source\_A | af\_purchase | 0日目 |
| 222 | XXX | organic | reinstall | 1日目 |
| 222 | XXX | media\_source\_A | af\_purchase | 1日目 |

**例2**

ユーザーがアプリをインストールし（0日目）、購入した後、アンインストールします。

翌日（1日目）、UAキャンペーン経由でアプリを再インストールして購入します。

| メディアソース | イベント名 | イベント日 | 再インストールの計測元 | アプリ内イベントの計測元 |
| --- | --- | --- | --- | --- |
| media\_source\_A | install | 0日目 | media\_source\_A |  |
| media\_source\_A | af\_purchase | 0日目 |  | media\_source\_A |
| media\_source\_B | reinstall | 1日目 | media\_source\_B |  |
| media\_source\_B | af\_purchase | 1日目 |  | media\_source\_A |

</Accordion>

<div id="confirm-inapps-are-attributed-to-the-original-install" />

<Accordion title="アプリ内イベントが元のインストールに紐付いていることの確認">

以下の手順でローデータレポートを確認すると、再インストール後のアプリ内イベントに、初回インストールに紐付けるモードが適用されているかを検証できます。

* アプリ内イベントの`install_time`フィールドを確認します。再インストールではなく、元のインストールの時刻になっていれば、初回インストールに紐付けられています。
* `device_id`（GAIDまたはIDFA）を確認します。インストール時と再インストール時で同じ値のため、イベントと元のインストールの対応を確認できます。
* アプリ内イベントの`appsflyer_id`は、元のインストールの値とは異なる点に注意してください。 AppsFlyerは、再インストールのたびに新しいAppsFlyer IDを生成します。

</Accordion>

<div id="limitations" />

<Accordion title="制限事項">

* インストール時と再インストール時の両方で、デバイス識別子（IDFAやGAIDなど）のアプリへの共有に同意したユーザーのみ、アプリ内イベントを元のインストールに紐付けられます。
  * 初回インストールと再インストールのデバイス識別子が一致する必要があります。
* 再インストールは、最後に記録されたインストールの<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#reengagement-rules-and-windows">リアトリビューション期間内</Anchor>に行われる必要があります。
* 各インストールと再インストールは、それぞれ固有の`appsflyer_id`を持ちます。
* ダッシュボードでは、インストール後と再インストール後のアプリ内イベントは区別されません。
  * ローデータでは区別できます。
* AppsFlyerのWindows SDKは、再インストールを計測しません。

</Accordion>

## AppsFlyerのダッシュボードでのデータ表示

<table><thead><tr><th colspan="2"> </th><th>ノンオーガニックの再インストール</th><th>オーガニックの再インストール </th><th>リアトリビューション</th></tr></thead><tbody><tr><td colspan="2">再インストール自体</td><td>表示されない</td><td>表示されない</td><td>リターゲティングのメディアソース\*</td></tr><tr><td rowspan="2">その後のアプリ内イベントの計測元</td><td>再インストール後のイベントを［<strong>オーガニックのアプリ内イベントとして計測</strong>］に設定 </td><td>元のインストールに紐付かないオーガニック</td><td>元のインストールに紐付かないオーガニック</td><td>リターゲティングのメディアソース</td></tr><tr><td>再インストール後のイベントを［<strong>初回インストールに紐付ける</strong>］に設定 </td><td>初回のメディアソース</td><td>初回のメディアソース</td><td>リターゲティングキャンペーン</td></tr><tr><td colspan="5">\*Overview dashboardのみ。</td></tr></tbody></table>

## 再インストールのローデータレポート

> 🚧 **前提条件**
>
> 有効化が必要です。詳しくは担当のCSMにお問い合わせください。

* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQtlerXtCVImurv-JyuG7JMPvLN6p2w79pmbMNBx6WBnLwnYq5bUqXiUuoy2l_UTzEjIr8UkDdclRxf/pub?output=csv">再インストールのレポート例（CSVファイル）</Anchor>

#### インストールとアプリ内イベントの計測元

<table><thead><tr><th colspan="2"> </th><th>ノンオーガニックの再インストール</th><th>オーガニックの再インストール </th><th>リアトリビューション</th><th>ノンオーガニックのインストール</th><th>オーガニックのインストール</th></tr></thead><tbody><tr><td colspan="2">紐付け先 </td><td>UAキャンペーン</td><td>オーガニック</td><td>リターゲティングキャンペーン</td><td>UAキャンペーン</td><td>オーガニック</td></tr><tr><td rowspan="2">その後のイベントの計測元</td><td>再インストール後のイベントを［<strong>オーガニックのアプリ内イベントとして計測</strong>］に設定 </td><td>オーガニック</td><td>オーガニック</td><td>リターゲティングキャンペーン</td><td>UAキャンペーン</td><td>オーガニック</td></tr><tr><td>再インストール後のイベントを［<strong>初回インストールに紐付ける</strong>］に設定 </td><td>初回インストール</td><td>初回インストール</td><td>リターゲティングキャンペーン</td><td>UAキャンペーン</td><td>オーガニック</td></tr></tbody></table>

### 再インストールレポートの提供方法

* 再インストールのローデータレポートは、以下の表の配信ツールで利用できます。
* レポートはインストールレポートと同じ構造で、以下のように同様の方法でデータが入力されます。
  * **メディアソース**：再インストールにつながったメディアソース、またはオーガニックが入力されます。
  * **インストール時刻**：再インストールの時刻、つまり再インストール後の最初のアプリ起動時刻を示します。
  * **イベント名：***Reinstall*

| レポートの配信方法 | ノンオーガニックの再インストール | オーガニックの再インストール |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">データのエクスポート</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/ja/docs/pull-api-aggregate-data">Pull API</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">Data Locker</Anchor> | ✓ | ✓ |
| Push API | ✓ | ✓ |

<div data-zendesk-anchors="what-is-a-reinstall=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%81%AF 01H7SZVZPGHBQ7VM8TMWRD3CE4=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%81%AF why-are-reinstalls-important=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%92%E6%AD%A3%E3%81%97%E3%81%8F%E8%A8%88%E6%B8%AC%E3%81%99%E3%82%8B%E3%81%93%E3%81%A8%E3%81%AE%E9%87%8D%E8%A6%81%E6%80%A7 01H7SZVZPG6T2AW9B3EMT29AQQ=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%92%E6%AD%A3%E3%81%97%E3%81%8F%E8%A8%88%E6%B8%AC%E3%81%99%E3%82%8B%E3%81%93%E3%81%A8%E3%81%AE%E9%87%8D%E8%A6%81%E6%80%A7 reinstall-flow-and-outcome=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E6%B5%81%E3%82%8C%E3%81%A8%E8%A8%88%E6%B8%AC%E7%B5%90%E6%9E%9C 01H7SZVZPGVQCNCQ7TCZMYM33T=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E6%B5%81%E3%82%8C%E3%81%A8%E8%A8%88%E6%B8%AC%E7%B5%90%E6%9E%9C 01H7SZVZPGCDP3GRK1BWZ04MR6=reinstall 01H7SZVZPG8WNTK30YXNZ44VTS=reattribution inapp-events=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E5%BE%8C%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 01H7SZVZPGBYRWZGAZRT36EFGH=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E5%BE%8C%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01K47GSZ90CKBGPCZFGQBD1PMK=postreinstall-events-attribution-state 01H7SZVZPH4AE1PZK8V5JG6C6X=unattributed-organic-inapps 01H7SZVZPH7KPM7T42GHZ7N69S=attributed-to-the-first-install h_01KHJV7J6H5KKMZVZN8XPW4CEZ=%E6%B3%A8%E6%84%8F 01H7SZVZPH5YGSMPGW7NPKXJAF=%E6%B3%A8%E6%84%8F-1 with-attributed-to-the-first-install-enabled=%E5%88%9D%E5%9B%9E%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AB%E7%B4%90%E4%BB%98%E3%81%91%E3%82%8B%E3%83%A2%E3%83%BC%E3%83%89%E3%81%A7%E3%81%AE%E8%A8%88%E6%B8%AC%E4%BE%8B 01H7SZVZPHH3DS9J4VRD70VTX6=%E5%88%9D%E5%9B%9E%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AB%E7%B4%90%E4%BB%98%E3%81%91%E3%82%8B%E3%83%A2%E3%83%BC%E3%83%89%E3%81%A7%E3%81%AE%E8%A8%88%E6%B8%AC%E4%BE%8B h_01K47KBXE2NXXQFMS4RPJ0RA4T=confirm-inapps-are-attributed-to-the-original-install 01H7SZVZPH8MSBQ92XWFK0HWGQ=limitations how-does-the-data-appear-in-the-appsflyer-dashboards=appsflyer%E3%81%AE%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E8%A1%A8%E7%A4%BA 01H7SZVZPHHQS4NHEDATD7ZP9V=appsflyer%E3%81%AE%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%A7%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E8%A1%A8%E7%A4%BA reinstalls-raw-data-reports=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01H7SZVZPHPWN8REBQ5CWVFNJT=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01H7SZVZPHCVDPDDYD6HHNFMMK=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 how-the-install-and-inapp-events-are-attributed=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%88%E6%B8%AC%E5%85%83 01H7SZVZPHQT8XS3ZBA4W682GB=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%88%E6%B8%AC%E5%85%83 availability-of-reinstall-reports=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E6%8F%90%E4%BE%9B%E6%96%B9%E6%B3%95 01H7SZVZPH6NY7FMG9YHDBB95R=%E5%86%8D%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E6%8F%90%E4%BE%9B%E6%96%B9%E6%B3%95" />
