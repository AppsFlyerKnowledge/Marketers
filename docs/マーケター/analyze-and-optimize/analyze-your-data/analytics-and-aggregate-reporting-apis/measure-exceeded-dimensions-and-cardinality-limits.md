---
title: exceededと記載されたデータとカーディナリティ上限について
metadata:
  keywords:
    - performance reports
    - Advertisers
    - exceeded
    - reports
    - faq
    - Agencies
    - Exceeded_Events_Limit
    - Exceeded Events Limit
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
  created_at: '2017-10-08T15:20:55Z'
  edited_at: '2026-10-14T09:32:36Z'
  id: 115005099063
  locale: ja
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ja/articles/115005099063
---
> **概要：** 概要： 一部の集計データが*exceeded* と表示される理由と、それを防止する方法にするについて記載しています。

<div id="what-are-exceeded-dimensions" />

## exceeded とは何ですか？

その結果、各項目内のユニークな値の数がカーディナリティの上限を超えてしまった場合には、残りのデータは*exceeded*のグループに割り当てられます。

以下の例では、カーディナリティとそれがレポートにどのように影響するかを示しています。

<div id="example" />

> 📄 **例**
>
> 例A：Campaign IDのカーディナリティ上限は3000です。
>
> Campaign IDのカーディナリティ上限は3000です。特定の日において、計測されたCampaign IDの数が3000を超えた場合、残りのCampaign IDはすべてExceeded\_CampaignID\_Limitとしてグループ化 / 集計されます。
>
> 例B：
>
> * イベントのカーディナリティ上限が3であるとします。

* オーバービュー管理画面

* Protect360 管理画面

ローデータレポートは、カーディナリティ上限の影響は受けないのでご安心ください。

これにより、アナリティクスレポートが不正確になる可能性があります。必要に応じて、ローデータを使ってカーディナリティの上限を受けない形でグループを作成しましょう。

<table><tbody><tr><th>ディメンション</th><th>Exceeded group name</th><th>上限対象となる対象の区分</th><th>1日あたりのカーディナリティ上限  </th><th>1日あたりのProtect360におけるカーディナリティ上限</th></tr><tr><td>Ad</td><td>Exceeded_Ad_Limit</td><td>Media source</td><td>1000</td><td>-</td></tr><tr><td>Ad ID</td><td>Exceeded_AdID_Limit</td><td>Media source</td><td>1000</td><td>-</td></tr><tr><td>広告セット</td><td>Exceeded_AdSet_Limit</td><td>Media source</td><td>1000</td><td>-</td></tr><tr><td>Adset ID</td><td>Exceeded_AdSetID_Limit</td><td>Media source</td><td>1000</td><td>-</td></tr><tr><td>Campaign</td><td>Exceeded_Campaign_Limit</td><td>Media source</td><td>3000</td><td><ul><li>3000</li><li>100 </li></ul></td></tr><tr><td>Campaign ID</td><td>Exceeded_CampaignID_Limit</td><td>Media source</td><td>3000</td><td><ul><li>3000</li><li>100 </li></ul></td></tr><tr><td>Channel</td><td>Exceeded_Channels_Limit</td><td>Media source</td><td>20</td><td>20</td></tr><tr><td>Site ID</td><td>Exceeded_SiteID_Limit</td><td>Media source</td><td>2024-02-26</td><td><ul><li>2024-02-26</li></ul></td></tr><tr><td>イベント</td><td>Exceeded_Events_Limit</td><td>アプリ </td><td>300</td><td>300</td></tr><tr><td>Keywords</td><td>Exceeded_Keywords_Limit</td><td>Media source</td><td>1000</td><td>-</td></tr><tr><td>メディアソース名</td><td>Exceeded_MediaSource_Limit</td><td>アプリ</td><td>1000</td><td><ul><li>1000</li><li>100 </li></ul></td></tr><tr><td colspan="5"></td></tr></tbody></table>

<div id="cardinality-limits-per-dimension" />

## 各項目（ディメンション）毎のカーディナリティ上限

<div id="exceeded_adset_limit-and-exceeded_ad_limit" />

<Accordion title="Exceeded_AdSet_Limit と Exceeded_Ad_Limit">

* メディアソース毎に、それぞれ最大1000個のユニークなアドセット名 (af\_adset) とアド名 (af\_ad) を利用可能です。
  * 同じことが、**Exceeded\_Ad\_Limit** のメディアソースにも適用されます。

<div id="tip" />

> 👍 **ヒント**
>
> データを細分化して克服しましょう。一般的なアドセット名（理想的には最大50個まで）をいくつか定義し、これまで使っていた全てのアドセット名を代わりにアド名へ割り当ててください。
> 1.
> 2.
> 3.

</Accordion>

<div id="exceeded_adsetid_limit-and-exceeded_adid_limit" />

<Accordion title="Exceeded_AdSetID_Limit と Exceeded_AdID_Limit">

* メディアソース毎に、それぞれ最大1000個のユニークなアドセットID (af\_adset\_id) とアドID (af\_ad\_id) を利用可能です。
  * 同じことが、Exceeded\_AdID\_Limit のメディアソースにも適用されます。

</Accordion>

<div id="exceeded_campaign_limit" />

<Accordion title="Exceeded_Campaign_Limit">

**[![](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)**

* 1日あたり最大 3000 個のユニークなキャンペーン名 (c) を使用できます。
  * 特定の日において、3001個目のアドセットID以降は全てのアドセットIDのデータが **Exceeded\_Campaign\_Limit** というグループに紐づきます。

<div id="tip-1" />

> 👍 **ヒント**
>
> 一般的なキャンペーン名（理想的には最大300個まで）をいくつか定義し、これまで使っていた全てのキャンペーン名を代わりにアドセット名へ割り当ててください。AppsFlyerの計測リンクの該当パラメーターは **af\_adset** です。
> 1.
> 2.
> 3.

</Accordion>

<div id="exceeded_campaignid_limit" />

<Accordion title="Exceeded_CampaignID_Limit">

* 1日あたり最大 3000 個のユニークなキャンペーンID (af\_c\_id) を使用できます。
  * 特定の日において、3,001番目のキャンペーンからは全てのキャンペーンデータが **Exceeded\_CampaignID\_Limit** というメディアソースに紐づきます。

</Accordion>

<div id="exceeded_channels_limit" />

<Accordion title="Exceeded_Channels_Limit">

* メディアソース毎に、1日あたり最大20個のユニークなチャネル名 (af\_channel) を計測可能です。（Protect360の画面上では1000個が上限です。）
  * 特定の日において、21個目のチャネル名以降は全てのチャネル名のデータが **Exceeded\_Channel\_Limit** というグループに紐づきます。

</Accordion>

<div id="exceeded_events_limit" />

<Accordion title="Exceeded_Events_Limit">

* 1日あたり最大 300 個のユニークなイベント名を計測可能です。
  * 特定の日において、301個目のイベント名以降は全てのイベント名のデータが **Exceeded\_Events\_Limit** というグループに紐づきます。

<div id="tip-2" />

> 👍 **ヒント**
>
> **Exceeded\_Events\_Limit**が表示されないようにするには、以下のような対策を検討してください：
>
> * <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">リッチアプリ内イベント</Anchor>をご利用ください。何百もの異なるイベント名を定義せずに、少数の一般的なイベント名（理想的には最大20個）を定義してください。動的なイベント値を使用して、これらのイベントを区別しましょう。<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">アプリ内イベントのローデータ</Anchor>を使うことで、イベント値のパラメータを使った最適化や、イベント値を基にした分析が可能になります。
> * 不必要なアプリ内イベントのデータをAppsFyerのプラットフォームから除外するために、検証ルールの活用も検討してください。

<div id="example-1" />

> 📄 **例**
>
> 「com.greatapp」というアプリが、販売している靴下の色別にそれぞれ購入イベントを定義して送信するとします。イベント名の例：buy\_red\_socks、buy\_blue\_socks、buy\_white\_socksなど。イベント数が膨大になることを防ぐために、これらを「buy\_socks」という単一のイベントに統一し、購入された靴下の色を<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">イベントパラメーター</Anchor>として挿入してください。

</Accordion>

<div id="exceeded_keywords_limit" />

<Accordion title="Exceeded_Keywords_Limit">

* メディアソース毎に、1日あたり最大1000個のユニークなキーワード (af\_keywords) を計測可能です。
  * 特定の日において、1001番目のキーワード以降は全てのキーワードデータが **Exceeded\_Keywords\_Limit** というグループに紐づきます。

</Accordion>

<div id="exceeded_mediasource_limit" />

<Accordion title="Exceeded_MediaSource_Limit">

* 1日あたり最大 1000 個のユニークなメディアソース名 (pid) を使用できます。
  * 特定の日において、 1001番目のメディアソース名以降は全てのメディアソースが **Exceeded\_MediasSource\_Limit** というグループに紐づきます。

</Accordion>

<div id="exceeded_siteid_limit" />

<Accordion title="Exceeded_SiteID_Limit">

* * 特定の日において、1001番目のサイトID以降はメディアソースごとの全てのサイトIDのデータが**Exceeded\_SiteID\_Limit** という１つのグループに紐づきます。したがって、Exceeded\_SiteID\_Limit というサイトIDが表示されている場合、該当のメディアソースで使用されているサイトIDが多すぎることを意味し、このソースのトラフィックをサイトIDごとに最適化する際の精度と効率が低下してしまいます。

<div id="tip-3" />

> 👍 **ヒント**
>
> 「細分化して克服」メディアソースごとに数千個のサイトIDを使用する代わりに、計測リンクに **af\_sub\_siteid** というサブサイトIDのパラメーターを使用してください。小数の一般的なサイトID（理想的には最大50個）を定義し、以前のサイトIDを全てサブサイトIDとして一般的なサイトIDの下に割り当ててください。
> 1.
> 2.
> 3.

<div id="note" />

> 📘 **注意**
>
> リテンションレポートでは、Exceeded\_SiteID\_Limit は表示されませんが、全てのサイトIDが表示されるわけではありません。サイトIDはランダムに表示されますが、UIの制限により全てを表示することができません（上限を超えている場合）。この問題を回避するためには、リテンションデータをMaster APIから取得してください。

</Accordion>

<div id="how-to-avoid-getting-exceeded-sources" />

## Exceededという表示を防ぐ方法は？

<div id="the-long-term-solution" />

### 長期的なソリューション

通常、ほとんどの広告主は3000個を超えるキャンペーン名を手動で定義することはないので、**Exceeded**というキャンペーン名は表示されません。

ただし、**Exceeded** が表示される場合は、1つまたは複数のメディアソースにて、キャンペーン名、サイトID、広告セット、広告などに、動的に値を振り当てている可能性があります。また、アプリのコード内で動的なアプリ内イベント名を使用すると、**Exceeded\_Events\_Limit** と表示されることがあります。

<div id="tip-4" />

> 👍 **ヒント**
>
> **Exceeded** の表示を避けるためには、アプリ内イベント、キャンペーン、サイトID、広告セット、広告に静的な値のみを使用してください。
>
> また、**Exceeded**のタイプごとに特定のヒントを確認してください。

<div id="the-short-term-solution" />

### 短期的なソリューション

長期的なソリューションの実装を完了するには、数日から数週間かかることがあります。

では、今すぐにデータを確認したい場合はどうすればよいでしょう？

上記で説明した通り、**Exceeded** は、AppsFlyerが特定の日に、N+1のクリック（またはイベント）を受信した場合に発生します。その日の後半に重要なメディアソースからのデータを受信したために、それらが**Exceeded**としてまとめられてしまう可能性もあります。その場合、**Exceeded**の影響を最小限にとどめるためのシンプルな対策を以下でご紹介します。

<div id="tip-5" />

> 👍 **ヒント**
>
> 本日のデータではなく、昨日とそれ以前のデータのみを分析対象にしてください。データ集約プロセスは、毎日昨日のデータを再度計算し、過去のデータを対象に最小コホートのソースから**Exceeded**グループに割り当てていきます。これにより、クリックのオーバーフローによるデータの歪みを最小限に抑えられます。

<div data-zendesk-anchors="what-are-exceeded-dimensions=exceeded-%E3%81%A8%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B h_01J1VY82KFVMRW99RK0SXWSEZ4=exceeded-%E3%81%A8%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B h_01J1VY82KFXYA0XCA1XFVTJ2DZ=%E4%BE%8B cardinality-limits-per-dimension=%E5%90%84%E9%A0%85%E7%9B%AE%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E6%AF%8E%E3%81%AE%E3%82%AB%E3%83%BC%E3%83%87%E3%82%A3%E3%83%8A%E3%83%AA%E3%83%86%E3%82%A3%E4%B8%8A%E9%99%90 h_01J1VY82KF5WP6PJQ1MKYPP7YY=%E5%90%84%E9%A0%85%E7%9B%AE%E3%83%87%E3%82%A3%E3%83%A1%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%B3%E6%AF%8E%E3%81%AE%E3%82%AB%E3%83%BC%E3%83%87%E3%82%A3%E3%83%8A%E3%83%AA%E3%83%86%E3%82%A3%E4%B8%8A%E9%99%90 h_01J1VY82KF9XQ08EQ2BH89B6QK=exceeded_adset_limit-and-exceeded_ad_limit h_01J1VY82KFM4VAD4FG5CEKTQK6=%E3%83%92%E3%83%B3%E3%83%88 h_01J1VY82KFWMF6DN3XNFSWBFHH=exceeded_adsetid_limit-and-exceeded_adid_limit h_01J1VY82KFF7AWBCB54KRPJNS4=exceeded_campaign_limit h_01J1VY82KFBPK2PAHSSMCER6TW=%E3%83%92%E3%83%B3%E3%83%88-1 h_01J1VY82KF4TFVTGQ31RCE3QK7=exceeded_campaignid_limit h_01J1VY82KFXPX63XKKKTZ9AWN1=exceeded_channels_limit h_01J1VY82KFRDRVNEAG6S72Q1T4=exceeded_events_limit h_01J1VY82KFYXAXTJ613VAN1PXX=%E3%83%92%E3%83%B3%E3%83%88-2 h_01J1VY82KF48N1M8DZ89XQBJTD=%E4%BE%8B-1 h_01J1VY82KFAFK03F3SDJBA5ZNX=exceeded_keywords_limit h_01J1VY82KFV85460FCZB77EY1A=exceeded_mediasource_limit h_01J1VY82KFQG2ZGF91F80X2AAK=exceeded_siteid_limit h_01J1VY82KFMD2DJWDYXF8528CY=%E3%83%92%E3%83%B3%E3%83%88-3 h_01J1VY82KFQRVCAW82ZSNJ96G7=%E6%B3%A8%E6%84%8F how-to-avoid-getting-exceeded-sources=exceeded%E3%81%A8%E3%81%84%E3%81%86%E8%A1%A8%E7%A4%BA%E3%82%92%E9%98%B2%E3%81%90%E6%96%B9%E6%B3%95%E3%81%AF h_01J1VY82KFE9E2DNRNPBRQSW22=exceeded%E3%81%A8%E3%81%84%E3%81%86%E8%A1%A8%E7%A4%BA%E3%82%92%E9%98%B2%E3%81%90%E6%96%B9%E6%B3%95%E3%81%AF the-long-term-solution=%E9%95%B7%E6%9C%9F%E7%9A%84%E3%81%AA%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01J1VY82KFDBASKPRK2GJ16FDZ=%E9%95%B7%E6%9C%9F%E7%9A%84%E3%81%AA%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01J1VY82KFSWQ2Y4WSSASYDFWR=%E3%83%92%E3%83%B3%E3%83%88-4 the-short-term-solution=%E7%9F%AD%E6%9C%9F%E7%9A%84%E3%81%AA%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01J1VY82KFR7Z8422MYFK71ET8=%E7%9F%AD%E6%9C%9F%E7%9A%84%E3%81%AA%E3%82%BD%E3%83%AA%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01J1VY82KF83SADWJCESRNSJCJ=%E3%83%92%E3%83%B3%E3%83%88-5" />
