---
title: リアトリビューション期間の設定
metadata:
  keywords:
    - Retargeting
    - Re-Attribution
    - reattribution
    - Advertisers
    - Ad Networks
    - re-attribution window
    - reattribution window
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2017-05-23T08:55:35Z'
  edited_at: '2026-10-28T09:08:12Z'
  id: 115002587066
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/115002587066
---
> **概要：** 再インストールを新規インストールとして計測しない「リアトリビューション期間」について説明します。

<div id="re-attribution-window" />

## リアトリビューション期間

リアトリビューション期間は、ユーザーがアプリを初めてインストールした時点から始まり、広告主が設定した期間にわたって継続します。デフォルトは90日です。リアトリビューション期間内の再インストールは、新規インストールとして記録されません。また、**リターゲティング**キャンペーン経由の場合を除き、新たなインストールポストバックも送信されません。

<Image align="center" alt="ReAttributionWindow_us-en.png" src="https://files.readme.io/cc3c4286be2721571329a08cf13bb93acd0dc3ada4f5bc52f0ffd263eff671ca-360011750637.png" />

<div id="setting-the-re-attribution-window" />

### リアトリビューション期間の設定方法

リアトリビューション期間の設定は、以下のとおりです。

* <Anchor target="_blank" href="/marketers/ja/docs/app-settings">アプリ設定</Anchor>ページで設定します。
* デフォルト値は90日（3か月）です。
* 1～24か月の範囲で設定できます。

インストールは、そのインストールが発生した時点の設定に基づいて判定されます。そのため、設定を変更すると、変更後に発生するインストール（再インストール）の判定に適用されます。過去のインストールの判定には影響しません。

* **リアトリビューション期間を90日から30日に変更する場合**：
  * 9月1日にインストールします。
  * 9月2日にリアトリビューション期間を変更します。
  * 10月1日までの再インストールは、再インストールとして扱われます。 10月2日以降は、新規インストールとして扱われます。
* **リアトリビューション期間を30日から90日に変更する場合**：
  * 9月1日にインストールします。
  * 9月2日にリアトリビューション期間を変更します。
  * 10月15日の再インストールは、現在の設定が90日であるため、再インストールとして扱われます。
  * 12月15日の再インストールは、9月1日のインストールから90日を超えているため、新規インストールとして扱われます。

<div id="re-attribution-window-use-cases" />

## リアトリビューション期間の適用例

<div id="first-install" />

<Accordion title="初回インストール">

アプリを一度もインストールしたことがない見込みユーザーが、ユーザー獲得またはリターゲティングのキャンペーンに接触し、モバイルアプリをインストールします。

この場合、以下のように処理されます。

* 新規インストールをメディアソースに紐付け、ユーザー獲得のダッシュボードやデータに反映します。広告接触が記録されていない場合は、オーガニックとして計測します。
* 新たなリアトリビューション期間が開始します。
* ポストバックの送信が設定されている場合、インストールとアプリ内イベントのポストバックが、そのメディアソースに送信されます。
* その後のアプリ内イベントも、同じメディアソースに紐付けます。

</Accordion>

<div id="reinstall" />

<Accordion title="再インストール">

ユーザーがアプリを初めてインストールした後、リアトリビューション期間内にアンインストールし、再インストールします。

この場合、以下のように処理されます。

* このインストールは、メディアソースの成果としては計上されず、ダッシュボードやデータにも表示されません。
* どのメディアソースにも、インストールポストバックは送信されません。
* これらのユーザーによる再インストール後のアプリ内イベントは、<Anchor target="_blank" href="/marketers/ja/docs/measure-reinstalls#overview">**再インストール後のイベントのアトリビューション**</Anchor>の設定に応じて、オーガニックまたは元のインストールに紐付けられます。

</Accordion>

<div id="reattribution" />

<Accordion title="リアトリビューション">

ユーザーがアプリを初めてインストールした後、リアトリビューション期間内にアンインストールし、リターゲティングキャンペーンに接触してから再インストールします。  
これをリアトリビューションと呼びます。

この場合、以下のように処理されます。

* インストールをリターゲティングのメディアソースに紐付け、Overview dashboardのリターゲティング表示と統合表示に反映します。つまり、ユーザー獲得の表示にはリアトリビューションは含まれません。
* その後のすべてのアプリ内イベントを、リターゲティングのメディアソースに紐付けます。
* インストールポストバックは、リターゲティングのメディアソースに送信されます。

リターゲティング計測の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">こちら</Anchor>をご覧ください。

</Accordion>

<div id="new-install" />

<Accordion title="新規インストール">

ユーザーがアプリをアンインストールします。その後、リアトリビューション期間が終了してから、再インストールします。この再インストールは初回インストールとして扱われ、同様に以下のように処理されます。

* 新規インストールをメディアソースに紐付け、ユーザー獲得のダッシュボードやデータに反映します。広告接触が記録されていない場合は、オーガニックとして計測します。
* **新たなリアトリビューション期間が開始します。**
* ポストバックの送信が設定されている場合、インストールとアプリ内イベントのポストバックが、そのメディアソースに送信されます。
* その後のアプリ内イベントも、同じメディアソースに紐付けます。

</Accordion>

<div id="ios-app-restored-from-icloud-backup" />

<Accordion title="iCloudバックアップから復元したiOSアプリ">

iCloudにバックアップされたアプリを、同じデバイスまたは別のデバイスに復元した場合、リアトリビューション期間にかかわらず、AppsFlyerは新規インストールや再インストールとして集計しません。 iCloudからアプリを復元したユーザーのAppsFlyer IDとアトリビューションデータは維持されます。

</Accordion>

<div data-zendesk-anchors="reattribution-window=%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93 h_01H95B0F8XEX9RFXW8W6QBQJBY=%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93 setting-the-reattribution-window=%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 h_01H95B0F8X2YQWBB9H0WFXPK8C=%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 reattribution-window-use-cases=%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93%E3%81%AE%E9%81%A9%E7%94%A8%E4%BE%8B h_01H95B0F8Y4T13VYEN2D7T5GHR=%E3%83%AA%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E6%9C%9F%E9%96%93%E3%81%AE%E9%81%A9%E7%94%A8%E4%BE%8B h_01H95B0F8Y58QFRSJ9TV3J34EX=first-install h_01H95B0F8YBY482KHT09CZNT9E=reinstall h_01H95B0F8YCQV3H6ZSZE0DF5VV=reattribution h_01H95B0F8Y046Q80V0S8YZ1DWG=new-install h_01H95B0F8Y6M7W02ZSNYCN66PD=ios-app-restored-from-icloud-backup" />
