---
title: Data Clean Room—テックパートナーとの連携によるデータ拡張
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2023-03-26T08:07:17Z'
  edited_at: '2026-10-14T09:34:30Z'
  id: 14035927509137
  locale: ja
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ja/articles/14035927509137
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

ベータ機能

> **概要：** 概要： データを充実させ、連携されたテックパートナーからのデータを使用してデータクリーンルーム(DCR)レポートを強化します。

> 📘 **この新機能をお試しください！**
>
> テックパートナーとの連携機能は現在オープンベータ版です。利用可能な連携のいずれかの有効化に興味がある場合は、CSMにご連絡ください。皆様からのご意見をお待ちしております！

## 概要

コンバージョンデータとカスタムソースデータのマッチングはDCRの中心ですが、可能性はそれだけではありません。テックパートナーとの連携により、焦点を絞り、キャンペーンのパフォーマンスを向上させることができます。

> 📘 **コストに関する考慮事項**
>
> テックパートナーの連携を利用するには、主に2つのコストに関する考慮事項があります：
>
> * <span id="data-access"></span>データアクセスデータアクセス： 料金はパートナーによって異なります（詳細については以下のタブで説明します）。多くの場合、検証できるよう無料のデータアクセス試用期間を提供しています。
> * **DCRクレジット：** この機能はベータ版です。テックパートナーから利用されたデータは、レポート実行の処理された行数に追加されず 、使用済みクレジットの計算には影響しません。レポート実行ごとのクレジットは、引き続き通常どおり課金されます（無料のデータアクセス試用期間中も同様です）。

## 利用可能な連携

アクティベーションの詳細については、パートナー名をクリックしてください。

<table><thead><tr><th colspan="2">Partner</th><th>データタイプとビジネス価値</th></tr></thead><tbody><tr><td><a href="#braze">Braze</a></td><td><img alt="braze_logo.png" src="https://files.readme.io/bbe30eb298ddc9c70bd993ca88bcd100cb02f3eecf7dc4563b2ef9b5e3c394d1-14036503933841.png"/></td><td><p>Brazeを使用すると、広告主はアプリのインストール後にユーザーエンゲージメントとコンバージョンを管理および測定できます。</p><p>DCRをBrazeデータに接続すると、メール、プッシュ通知、アプリ内メッセージなどのオウンドメディアチャネルとのユーザーインタラクションに照らして、キャンペーンの成功を分析できます。</p><p>例：特定のキャンペーンで獲得したユーザーは、プッシュ通知を受け取った後、購入を続けたり、サブスクライバーになったりしているかどうか？</p><p><strong>注記：</strong>注意： <strong>プッシュ通知起動</strong>イベントをサポートするベータ版を公開しましたが、測定している他のBrazeイベントのサポートをすぐに追加できます。ご興味があればご連絡ください！</p></td></tr><tr><td><a href="#startio">Start.io</a></td><td><img alt="start.io_logo.png" src="https://files.readme.io/3aa0db6ddf43d1999bf7014648aa163aa5c535da4d289b039be35a44b97b5aef-14036504920081.png"/></td><td><p><span>Start.ioは、</span><span>ユーザーの関心に関する情報を含むユーザープロファイルの大規模なデータベース</span>を維持しています。</p><p><span>DCRをこのデータベースに接続すると、獲得したユーザーの関心に関する貴重な洞察が得られ、実行中のキャンペーンの潜在的な成功を分析できます。</span></p><p>例：カジノゲームアプリで獲得したユーザーは、通常、カジノゲームに興味を示していますか？それとも、彼らは主にロールプレイングゲームに興味を示していますか？彼らがカジノゲームのヘビーユーザーでない場合、キャンペーンのROIはあなたの期待に応えるものですか？</p><p><font>備考</font></p><ul><li>利用可能なユーザーの関心トピックの種類については、 <font>Start.ioのWebサイト</font>を確認してください。</li><li>Start.io データは、米国のユーザーのみが利用できます。</li></ul></td></tr><tr><td><a href="#techsalerator">Techsalerator</a></td><td>techsalerator</td><td><p>Techsaleratorは、人口統計プロフィール、ライフスタイル、行動など、144カ国で現地調達した消費者データの広範なデータベースを保持しています。</p><p>DCRをこのデータベースに接続することで、キャンペーンを通じて獲得したユーザーやリエンゲージメントしたユーザーに関する貴重なインサイトを得ることができます。その後、このインサイトを使用してキャンペーンを最適化することができます。</p><p>例えば、キャンペーンで獲得したユーザーやリエンゲージメントされたユーザーのほとんどは、キャンペーンのリーチ対象とは異なる年齢層に属しているのでしょうか？キャンペーンのリーチ範囲を拡大し、ターゲットとなる年齢層を広げることに関心がありますか？</p><p><span>備考</span></p><ul><li>関連する利用可能なデータフィールドについては、Techsaleratorの <span>データカタログ</span> の <span>Individual（個人）</span>タブをご覧ください。</li><li> <span></span><span>国別のデータフィールドの可用性については、 <span>国ベースのデータマーケットプレイス</span>をご覧ください。</span> </li></ul></td></tr><tr><td><a href="#evorra">Evorra</a></td><td><img alt="evorra.png" src="https://files.readme.io/4b45749fb072fef75ddccec4be35f6231a6d28fee2614d58244fe3e071aa7126-17613191508241.png"/></td><td><p>Evorraは、世界中の35を超えるプロバイダーによる10億人以上のユーザーのIDを含む、クッキーレスのデータマーケットプレイスです。すべてのデータは同意されたもので、プライバシーに準拠しています。</p><p>Evorraは、ほとんどの主要地域でハッシュ化された電子メールに基づいて高いマッチ率のリターンが可能です。人口統計、社会経済、小売、関心/意図、エンターテインメント、スポーツ、ビジネス、テクノロジー、自動車などのタイプの属性でユーザーデータを充実させることができます。<span><br/></span></p><p>次に、このユーザーデータを利用して、キャンペーンが意図したオーディエンスにリーチしているかどうかに基づいてキャンペーンを評価および最適化できます。例：例：家族旅行の航空券を購入する予定のユーザーを対象としたリターゲティングキャンペーンを実施しました。それは実際にその対象ユーザーにエンゲージしましたか?それとも、その代わりに、一人でクルーズを予約しようとしているユーザーにリーチしましたか?</p><p><span> </span>注意</p><ul><li>CSM または <a href="mailto:hello@appsflyer.com">hello@appsflyer.com</a> に連絡して <font>Evorraを通じて利用可能なユーザー属性の広範なリスト</font>の詳細をご確認ください。 </li></ul></td></tr></tbody></table>

## はじめよう

以下のタブの指示に従って、連携を有効化します：

<div id="braze" />

<Accordion title="Braze">

> 🚧 **前提条件**
>
> Braze連携は、Snowflakeを介したデータ共有を利用します。連携を利用するには、次のものが必要です：
>
> * Snowflakeとの安全なデータ共有を含むBrazeサブスクリプション
> * Braze SDKとAppsFlyer SDKの両方がアプリに実装されている必要があります。

#### 連携の有効化

**Braze連携を有効にするには：**

1. Brazeチームと調整して（Brazeのドキュメントで詳しく説明されています）、1つ以上の<Anchor target="_blank" href="https://www.braze.com/docs/partners/data_and_infrastructure_agility/data_warehouses/snowflake/#integration">Braze</Anchor>アプリグループからAppsFlyer Snowflakeアカウントにデータ共有をプロビジョニングします： `AEJUPNV.DCR_AWS_US_EAST_1_QA`AEJUPNV.DCR\_AWS\_US\_EAST\_1\_QAAEJUPNV.DCR\_AWS\_US\_EAST\_1\_QA
2. AppsFlyer SDKが各ユーザーの<Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">CUID</Anchor>を AppsFlyerに送信するように設定されていることを確認するか、 <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API</Anchor> を使用して CUID を送信します。
   * 重要！
3. 担当のCSM または [hello@appsflyer.com](mailto:hello@appsflyer.com) へ、連携有効のリクエストをご連絡ください。
   * データ共有のプロビジョニング元の Braze `app_group_id`app\_group\_idapp\_group\_id (1つ以上) を提供します。

Braze側で必要な手配を済ませると、AppsFlyer側からの追加の [データアクセス](#コストに関する考慮事項)料金は発生しません。

</Accordion>

<div id="startio" />

<Accordion title="Start.io">

#### 連携の有効化

**Start.io 連携を有効にするには、私たちへご連絡いただくだけです。**

* Start.io データを使用するレポートを最初に実行した日から 30 日間無料でアクセスできます。
* 30日が経過すると、Start.ioと直接サブスクリプションを手配しない限り、このデータを使用するレポートはすべて失敗します。

</Accordion>

<div id="techsalerator" />

<Accordion title="Techsalerator">

#### 連携の有効化

**Techsalerator連携を有効にするには、私たちへご連絡いただくだけです。**

* レポートにTechsalerator のデータを使用するには、まずTechsaleratorと直接サブスクリプションを手配する必要があります。
  * Techsaleratorのデータにアクセスするトライアル期間はありません。
* DCR内でTechsaleratorデータをアクティブ化するには時間がかかる場合がありますので、開始予定日の少なくとも1週間前に必ずご連絡ください。

</Accordion>

<div id="evorra" />

<Accordion title="Evorra">

#### 連携の有効化

**Evora連携を有効にするには、私たちへご連絡いただくだけです。**

* レポートにEvorraのデータを使用するには、まずEvorraと直接サブスクリプションを手配する必要があります。
  * Evorraのデータにアクセスするトライアル期間はありません。
* DCR内でEvorraデータをアクティブ化するには時間がかかる場合がありますので、開始予定日の少なくとも1週間前に必ずご連絡ください。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 cost-considerations=%E3%82%B3%E3%82%B9%E3%83%88%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E8%80%83%E6%85%AE%E4%BA%8B%E9%A0%85 available-integrations=%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AA%E9%80%A3%E6%90%BA getting-started=%E3%81%AF%E3%81%98%E3%82%81%E3%82%88%E3%81%86 activating-the-integration-braze=%E9%80%A3%E6%90%BA%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 activating-the-integration-startio=%E9%80%A3%E6%90%BA%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96-1 activating-the-integration-techsalerator=%E9%80%A3%E6%90%BA%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96-2" />
