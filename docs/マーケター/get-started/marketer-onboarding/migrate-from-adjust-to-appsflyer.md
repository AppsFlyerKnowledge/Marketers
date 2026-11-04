---
title: AdjustからAppsFlyerへの移行
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2024-12-02T10:01:48Z'
  edited_at: '2026-10-21T09:13:50Z'
  id: 30563700129297
  locale: ja
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/ja/articles/30563700129297
---
> **概要：** AdjustからAppsFlyerへの移行計画を立てるためのガイドです。移行期間中の二重請求、データの重複、データの欠落を防ぐ方法を説明します。

<div id="about-migrating-to-appsflyer" />

## AppsFlyerへの移行について

AdjustからAppsFlyerへ移行することで、信頼性が高く、幅広い機能を備えたアトリビューション・マーケティング分析プラットフォームへ円滑に切り替えられます。 AppsFlyerは、安全性と中立性を備えたソリューションに加え、業界の変化への対応を支援するさまざまな高度なツールを提供しています。世界各地のカスタマーサポートと継続的な製品改善を通じて、企業の成長と変化への対応に必要なツールや分析結果の提供を目指しています。

<div id="compare-measurement-between-appsflyer-and-adjust" />

#### AppsFlyerとAdjustの計測結果の比較

移行を検討する際には、同じメディアソースやキャンペーンを対象に、AppsFlyerとAdjustのアトリビューションの計測結果を比較したい場合があります。ただし、すべてのメディアソースが複数のMMPによる計測に対応しているわけではありません。対応している場合でも、アトリビューションの差異を防ぐために、一定の制限や注意点が設けられていることがあります。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/measuring-attribution-with-multiple-mmps">複数のMMPによるアトリビューション計測</Anchor>をご確認ください。

<div id="tasks" />

## 移行に必要な作業

以下の表に、移行に必要な主な手順をまとめています。作業全体の詳しい内訳を確認し、進捗を記録するには、<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQqbJIkE7kD87uSm7MH7zfkPN1VLuBaeotTEHAID2pYFVWM_LuQIA2AE2-8fVnXH-DrbXUQCs2iaiDe/pub?output=xlsx">こちらのスプレッドシート</Anchor>をダウンロードしてください。

これらの作業は並行して進められます。マーケティング担当者、開発者、データエンジニアは、大半の作業をそれぞれ同時に進めることが可能です。以下の対応をおすすめします。

* AppsFlyer SDKを実装した更新版アプリを公開する前に、すべての作業を完了する。
* デバイスIDの移行前に、既存のマーケティングキャンペーンを一時停止する。

<table><thead><tr><th>手順</th><th>担当者</th><th>所要時間の目安</th><th>補足</th></tr></thead><tbody><tr><td> AppsFlyerアカウントの作成</td><td>マーケティング担当者 / AppsFlyer管理画面の利用者</td><td>2時間</td><td> </td></tr><tr><td> AppsFlyerへのアプリの追加</td><td>マーケティング担当者 / AppsFlyer管理画面の利用者</td><td>2時間</td><td> </td></tr><tr><td> SDKの実装</td><td>アプリ開発者</td><td>実装に1日、テストと修正に1週間</td><td><ul><li> <strong>推奨：</strong>公開前のテスト用アプリにAppsFlyer SDKを実装し、テストを行ってください。</li><li>本番用アプリは、ほかのすべての作業を完了してから、アプリストアで更新する必要があります。</li></ul></td></tr><tr><td> デバイスIDの移行（任意）</td><td>データエンジニア</td><td>1～2週間</td><td rowspan="2"><ul><li>移行前に既存のキャンペーンを一時停止し、アプリのバージョンを更新してから再開することを検討してください。 </li><li>移行漏れを防ぐため、最終的な移行日にデバイスIDの移行を再度実施することを検討してください。 </li></ul></td></tr><tr><td> キャンペーンの移行</td><td>マーケティング担当者 / ユーザー獲得施策の担当者</td><td>メディアソースごとに1～3日</td></tr><tr><td> レポート取得の設定</td><td>データエンジニア</td><td>3～6週間</td><td> </td></tr></tbody></table>

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="ステップ1． AppsFlyerアカウントの作成">

**AppsFlyerアカウントを作成するには**：

1. <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">AppsFlyerアカウントを作成</Anchor>します。
2. <Anchor target="_blank" href="/marketers/ja/docs/user-management">適切な権限を付与してアカウントにユーザーを追加</Anchor>します。

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="ステップ2．アプリの追加">

**AppsFlyerにアプリを追加するには**：

1. AppsFlyerに<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">アプリを追加</Anchor>します。
2. ［任意］アクティブユーザーの定義に合わせて、<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>をデフォルトの90日間から変更します。
3. AppsFlyerのアプリ登録ウィザードで、SDK実装とアプリ内イベントの対応付けに関する手順や作業内容をまとめたメールを作成し、開発者に送信します。

</Accordion>

<div id="step-3-integrate-the-sdk" />

<Accordion title="ステップ3． SDKの実装">

アプリに実装したAppsFlyer SDKは、アプリとAppsFlyerプラットフォームをつなぐ役割を果たします。アプリのインストール、起動、アプリ内イベントなどを送信します。

**AppsFlyer SDKを実装するには**：

1. マーケティング担当者から、SDK実装とアプリ内イベントの対応付けに関する手順や作業内容をまとめたメールを受け取ります。
2. メールの手順に従い、<Anchor target="_blank" href="https://dj.dev.appsflyer.com/?sourceos=android&utm_source=kb&utm_medium=sdk-int-wizard-orvw">AppsFlyer SDK実装ウィザード（設定ガイド）</Anchor>を使用して、アプリにAppsFlyer SDKを実装します。
   * ウィザードでは、SDKの導入から実装のテストが正常に完了するまでの手順を案内します。アプリ内イベントの定義と、AppsFlyerへの送信が正常に行われることを確認するテストについても案内します。 <Anchor target="_blank" href="/marketers/ja/docs/for-ios-and-android-the-sdk-integration-wizard">SDK実装ウィザードの詳細</Anchor>
   * 開発者向けの<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">Android</Anchor>および<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">iOS</Anchor>のSDK実装ガイドもご確認ください。
   * 記録するアプリ内イベントを、AppsFlyerの定義に対応付けます。  
     <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview">SDK</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>で設定できます。
3. Adjust SDKを削除します。  
   すぐに削除してAppsFlyerのみを使用することも、しばらく両方のSDKを併用することも可能です。各選択肢の詳細は、以下の表をご確認ください。

| 選択肢 | 更新版アプリの公開後の  <br />挙動 | 影響 |
| --- | --- | --- |
| Adjust SDKを削除する（推奨） | 新規インストールと、アプリを更新したユーザーを記録するのは、AppsFlyerのみになります。  <br />ユーザーがアプリを更新するまでは、そのユーザーのイベントは引き続きAdjustに表示されます。 | <ul><li>迅速に移行できます。</li><li>アトリビューションの重複が発生しません。</li></ul> |
| 移行期間中はAdjust SDKを残す | AppsFlyerとAdjustの両方が、新規インストールのアトリビューションとイベントの記録を行います。後日、Adjust SDKを削除します。 | <ul><li>データを検証できます。つまり、AppsFlyerとAdjustのデータを比較できます。</li><li>アトリビューションが重複し、アドネットワークから二重請求される可能性があります。以下の例をご確認ください。</li><li>作業負担が増えます。</li></ul> |

4. この記事に記載されたほかのすべての移行作業を完了したら、AppsFlyer SDKを実装したアプリのバージョンを公開します。新規ユーザーのアトリビューションはAppsFlyerが行います。   
   **注意**：
   * iOS、Google Play、および利用しているGoogle Play以外のAndroidアプリ配信先で、アプリを更新してください。
   * Androidアプリは、把握していない非公式のAPK配布サイトで公開されている可能性があります。確認するには、アプリのパッケージ名でWeb検索してください。 APK配布サイトで最新版に更新されるまでには時間がかかるため、AppsFlyer SDKを含まない旧バージョンをインストールするオーガニックユーザーが発生する場合があります。
   * アプリストアで更新版の配信が完全に行き渡るまで、数日かかる場合があります。この期間中にインストールしたユーザーには、旧バージョンが配信される可能性があります。

</Accordion>

<div id="step-4-migrate-devices-optional" />

<Accordion title="ステップ4．デバイスIDの移行 （ 任意）">

デバイスIDの移行とは、既存ユーザーのデバイスID（IDFA、IDFV、GAID）の一覧をAppsFlyerにアップロードする作業です。（必要なデバイスIDがすべて揃っていない場合は、担当のCSMにご相談ください。CUIDを使用した移行手順をご案内します。） AppsFlyer SDKを含む新しいバージョンのアプリを公開する前に、この作業を実施してください。デバイスIDの移行には、[流入元情報を引き継ぐ移行](/docs/migrate-from-adjust-to-appsflyer#attributed-migration)と[流入元情報を引き継がない移行](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration)の2つの方法があります。

デバイスIDの移行により、アプリをダウンロードし、Adjustでアトリビューションが行われた既存ユーザーに関するデータ上の問題を解消できます。たとえば、AdjustでSRNにアトリビュートされたユーザーがルックバック期間内にAppsFlyerでも同じSRNにアトリビュートされ、二重請求が発生する問題に対応できます。

<div id="example" />

> 📄 **例**
>
> * 新規ユーザーがFacebookアプリで広告をクリックし、6月15日に自社アプリをインストールします。
> * 6月24日に、ユーザーがAppsFlyer SDKを含むバージョンにアプリを更新し、起動します。 AppsFlyerでは、このユーザーを新規ユーザーとして扱うため、リアルタイムにアトリビューションを行う必要があります。
> * AppsFlyerは、ユーザーのデバイスIDを使用してMeta adsに照会します。ユーザーはまだMeta adsの28日間のルックバック期間内にいるため、Meta adsはこのユーザーを自社の成果として報告します。その結果、アプリ所有者は同じユーザーについて二重に請求されます。

デバイスIDの移行後、AppsFlyerではデータが以下のように反映されます。

* **インストールデータ：** <Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window#reinstall">再インストール</Anchor>と同様に、移行したデバイスにはインストールデータがありません。移行したデバイスのインストールは、AppsFlyerに表示されません。
* **アプリ内イベントとセッションのデータ：** [流入元情報を引き継がない移行](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration)では、オーガニックとして記録・表示されます。[流入元情報を引き継ぐ移行](/docs/migrate-from-adjust-to-appsflyer#attributed-migration)では、メディアソースとキャンペーンにアトリビュートされます。
* **リターゲティング：** リアトリビューションとリエンゲージメントは、通常どおり表示されます。
* **アクティビティデータ：** 通常どおり表示されます。
* **リテンションとコホートのデータ：** 移行したデバイスには、インストールの記録がありません。そのため、どのコホートにも紐づかず、コホートレポートとリテンションレポートには表示されません。

<div id="note" />

> 📘 **注意**
>
> 移行日から180日以内にアプリが起動されない場合、移行したデバイスのデータはすべて削除されます。そのため、180日を経過してからアプリが起動された場合は、新規インストールとして記録されます。

**デバイスIDを移行するには、以下の手順を実行します。**

1. 移行対象のユーザーを決定します。既存ユーザー全員を移行することも、最近アプリをインストールしたユーザーのみを移行することも可能です。前者では、AppsFlyerで正確なリアトリビューションデータを取得できなくなる可能性があります。後者では、それより前にインストールしたユーザーについて二重請求が発生する可能性があります。  
   <strong>現在設定されているリアトリビューション期間内にアクティブだったユーザーの移行をおすすめします。</strong>たとえば、アプリのリアトリビューション期間が90日間の場合は、過去90日間に1回以上のセッションがあったユーザーを移行します。
2. ［任意］マーケティング担当者 / ユーザー獲得施策の担当者に、デバイスIDの移行が完了するまで、既存のマーケティングキャンペーン（SRN、SRN以外のアドネットワーク、オウンドメディアなど）を一時停止するよう依頼します。  
   キャンペーンを一時停止しない場合は、AppsFlyer SDKを実装した更新版アプリがアプリストアで公開されたら、他社サービスに残っているデバイスIDを速やかに移行してください。
3. 移行対象のユーザーに基づいて、[流入元情報を引き継ぐ移行](/docs/migrate-from-adjust-to-appsflyer#attributed-migration)または[流入元情報を引き継がない移行](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration)の形式でCSVファイルを作成します。 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">CSVのサンプル</Anchor>
4. CSVファイルを担当のAppsFlyer CSMに送信します。  
   担当のCSMが、デバイスIDをAppsFlyerに移行します。

</Accordion>

<div id="step-5-migrate-campaigns" />

<Accordion title="ステップ5．キャンペーンの移行">

既存のマーケティングキャンペーンをAppsFlyerに切り替えることで、AppsFlyerでアトリビューションを行えるようにし、二重請求やアトリビューションデータの欠落を防ぎます。

**注意：** マーケティングキャンペーンを少しずつ移行することも可能です。その場合は、メディアソース（アドネットワークや代理店など）、地域、キャンペーンの単位で移行対象を分けられます。

以下では、SRN、SRN以外のアドネットワーク、オウンドメディア、SKANについて、それぞれAppsFlyerで計測を開始するために必要な作業を説明します。

<div id="srns" />

#### セルフレポーティングネットワーク（SRN）

SRNは、モバイル計測パートナー（MMP）から、特定のデバイスの広告接触について照会を受けると、その情報を返します。 AppsFlyerとAdjustが、同じデバイスのインストールについて同じSRNに照会すると、二重請求が発生する可能性があります。

**SRNのキャンペーンを移行するには**：

* AppsFlyerで、対象の<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#srn媒体">SRN</Anchor>を有効化し、設定します。

<div id="note-1" />

> 📘 **注意**
>
> * SRNは複数のMMPを併用できます（Meta adsとTwitterを除く）。
> * Meta adsでは、アプリ内イベントの重複を排除できません。

<div id="non-srn-ad-networks" />

#### SRN以外のアドネットワーク

アドネットワークのアトリビューションリンクは、ユーザーの広告接触を記録します。その後、その記録を使用して、実際のインストールにつながった広告接触にアトリビューションを行います。

**SRN以外のアドネットワークのキャンペーンを移行するには**：

1. AppsFlyerで、対象のアドネットワークを<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">有効化</Anchor>します。
2. 各アドネットワークの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">AppsFlyerアトリビューションリンクを生成</Anchor>します。
3. 各キャンペーンの既存のリンクを、AppsFlyerのアトリビューションリンクに置き換えます。

<div id="owned-media" />

#### オウンドメディア

ここでいうオウンドメディアとは、以下で使用するアトリビューションリンクを指します。

* コンテンツの共有
* Webからアプリへの誘導
* メール
* SMS
* SNSへの投稿
* ブログ
* オンラインコミュニティ（Quoraなど）
* その他

これらのキャンペーンでは、AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLinkリンク</Anchor>を使用します。 OneLinkリンクは、ユーザーのデバイスに応じて、適切なアプリストア、アプリ内、またはWeb URL / ランディングページにリダイレクトします。

**AdjustのリンクをAppsFlyerのOneLinkリンクに変更するには**：

* 担当のCSMにご相談ください。現在利用しているチャネルやツールに合わせて、オウンドメディアのリンクをOneLinkリンクに変更する作業を支援します。

#### SKAN

SKAdNetwork（SKAN）のアトリビューションでは、コンバージョン値を更新するSDKを1つに限定する必要があります。複数のSDKが更新すると、SKANデータが意味をなさなくなります。そのため、移行後はAppsFlyer SDKのみがSKANのコンバージョン値を更新するようにしてください。

AppsFlyerでのSKANのコンバージョン値の設定方法をご確認ください。

</Accordion>

<div id="step-6-set-up-data-reporting" />

<Accordion title="ステップ6．レポート取得の設定">

AppsFlyerでは、複数の方法で<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-apis">ローデータ</Anchor>および<Anchor target="_blank" href="/marketers/ja/docs/analytics-and-aggregate-reporting-apis">集計データ</Anchor>のレポートを取得できます。各取得方法を確認し、必要な方法を設定してください。

以下の方法でレポートを取得できます。

* ダッシュボード
* レポート出力
* Push API
* Pull API
* Data Locker

移行前のシステムでは、Adjustで設定したレポートの構成、項目、パラメータに従って、Adjustのアトリビューションデータが保存されています。 AppsFlyerのデータを正しく取り込むには、現在のレポートの構成を調整し、AppsFlyerのレポートの構成、項目、パラメータに対応付ける必要があります。

**レポートの構成を調整・対応付けするには：**

* 担当のAppsFlyer CSMにご相談ください。AdjustからAppsFlyerへ、レポートのデータ構成を迅速に調整・移行する作業を支援します。

</Accordion>

<div id="additional-information" />

## 補足情報

<div id="attributed-migration" />

<Accordion title="流入元情報を引き継ぐ移行">

この方法でAppsFlyerに移行したデバイスのアプリ内イベントとセッションは、移行前の計測サービスが報告したメディアソースに基づき、アドネットワークのデータ保持ポリシーに従って記録・表示されます。

<div id="attributed-device-migration-csv-structure" />

#### 流入元情報を引き継ぐ移行のCSV形式

| 列  <br />名 | 説明 | 必須 | 例 |
| --- | --- | --- | --- |
| &lt;0>app\_id0> | AppsFlyer管理画面に表示されるアプリID | はい | <ul><li>Android：com.great.app1</li><li>iOS：id123456789</li></ul> |
| &lt;0>platform0> | デバイスのプラットフォーム：iosまたはandroid | はい | <ul><li>ios</li><li>android</li></ul> |
| &lt;0>device\_id0> | <ul><li>Android：gaidまたはandroid\_id</li><li>iOS：IDFV（取得できる場合は推奨）またはIDFA</li><li>同じデバイスIDとアプリIDの組み合わせを、複数の行に重複して記載しないでください。重複がある場合は、ファイル内で最後に記載された行が使用されます。</li></ul> | はい | <ul><li>**gaid**（小文字）：9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**android\_id**（小文字）：f35aea8908254891</li><li>**IDFV**（大文字）：A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA**（大文字）：9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| &lt;0>id\_type0> | <ul><li>Android： advertiserId（amazon\_aidにも対応）、android\_id</li><li>iOS：idfaまたはidfv</li><li>現在、OAIDやIMEIなど、ほかの識別子には対応していません。<br />Google Play以外からインストールしたAndroidユーザーには、流入元情報を引き継がない移行を使用してください。</li></ul> | はい | <ul><li>advertiserId</li><li>android\_id</li><li>idfa</li><li>idfv</li></ul> |
| &lt;0>install\_time0> | 元のアプリのインストール日時を、<Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor>に準拠した以下のUTC形式で指定します：  <br />**yyyy-mm-ddTHH:MM:SS.SSS** | いいえ | 2018-01-22T08:45:33.412 |
| &lt;0>media\_source0> | <ul><li>以下のいずれか：<ul><li>AppsFlyerのパートナーID</li><li>独自のメディアソース（パートナーIDは使用不可）</li></ul></li><li>AppsFlyerで必要なパートナーIDの一覧を取得するには、以下の手順を実行します。<ul><li>対象となるすべての連携済みパートナーを有効化します。</li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">Get active integrations API</Anchor>を実行し、有効なすべての連携の一覧を取得します。</li><li>APIが返す**media\_source\_name**を、CSVの**media\_source**の値として使用します。</li><li>例外：<ul><li>Apple Search Adsには、**Apple Search Ads**を使用します。</li><li>Twitterには、**twitter**を使用します。</li></ul></li></ul></li><li>形式：大文字と小文字を区別</li></ul> | はい | 非オーガニック：facebook\_int、googleadwords\_int<br /><br />オーガニック：organic |
| &lt;0>integrated\_partner0> | <ul><li>メディアソースが連携済みパートナーかどうかを示します。連携済みパートナーではない場合は、オーガニックまたは独自のメディアソースを指します。</li><li>形式：大文字と小文字を区別</li></ul> | はい | <ul><li>yes</li><li>no（media\_sourceが独自のメディアソースの場合）</li></ul> |
| &lt;0>campaign0> | アトリビューションの詳細をより細かく記録するには、元のキャンペーン名を指定します。<br /><br />形式：文字列 | いいえ |  |
| &lt;0>campaign\_id0> | アトリビューションの詳細をより細かく記録するには、元のキャンペーンIDを指定します。<br /><br />形式：文字列（スペースは使用不可） | いいえ |  |

**CSVファイルの作成ルール：**

* 1つのCSVファイルに、複数のアプリのユーザーのデバイス情報を含められます。
* 同じデバイスIDとアプリIDの組み合わせを、複数の行に重複して記載しないでください。重複がある場合は、ファイル内で最後に記載された行が使用されます。
* すべての列名を含める必要があります：app\_id、platform、device\_id、id\_type、install\_time、media\_source、integrated\_partner、campaign、campaign\_id。**注意：** 項目の順序は重要なため、必ず維持してください。
* 同じデバイスのIDFVとIDFAの両方を追加できますが、別々の行に記載する必要があります。それぞれの行では、device\_id以外のすべての項目を同じ値にしてください。
* 各行には、カンマで区切った9つの項目を必ず含めてください。
* 必須ではない項目は空欄にします。
* 1ファイルに最大500万行を含められます。
* 複数のファイルがある場合は、それぞれ異なるファイル名を付けてください。
* 文字コードはUTF-8を使用してください。
* ［任意］ZIPまたはGZIPでファイルを圧縮します。

CSVのサンプル

</Accordion>

<div id="nonattributed-migration" />

<Accordion title="流入元情報を引き継がない移行">

この方法でAppsFlyerに移行したデバイスは、オーガニックユーザーとして記録されますが、表示はされません。そのデバイスのアプリ内イベントとセッションも、オーガニックとして記録・表示されます。

<div id="non-attributed-device-migration-csv-file-structure" />

#### 流入元情報を引き継がない移行のCSV形式

| 選択肢 | 列 | 使用する条件 | 例 |
| --- | --- | --- | --- |
|  | アプリID + IDFA / GAID / IDFV | <ul><li>すべてのAndroidユーザーにGAIDがある場合。</li><li>iOSユーザーのみの場合。</li></ul> |  |
|  | アプリID + デバイスID + デバイスIDの種類 | <ul><li>Androidユーザーの一部にGAIDがなく、IMEIまたはAndroid IDのみがある場合（Google Play以外のAndroidアプリ配信先、Android 4.4.2未満など）。</li><li>Android IDは、16進数形式で指定する必要があります。</li></ul>**注意**：<ul><li>**IDの種類**の列には、以下の文字列を正確に使用してください：advertiserId（amazon\_aidにも対応）、idfa、idfv、android\_id、imei。</li><li>android\_idまたはimeiを使用した後に、AppsFlyerがより適切な識別子を受信すると、新たなアトリビューションが記録される場合があります。</li></ul> |  |

**CSVファイルの作成ルール：**

* 1つのCSVファイルに、複数のアプリのユーザーのデバイス情報を含められます。
* 各行には、アプリごとに1つのデバイスIDを記載します。 **0>**
* 選択したファイル形式に応じて、以下の列を記載順どおりに指定してください。
  * 選択肢1：app\_id,device\_id
  * 選択肢2：app\_id,device\_id,id\_type
* アプリIDは小文字で指定します。
* Androidの識別子は小文字で指定します。
* IDFA / IDFVは大文字で指定します。
* 最大2,500万行を含められます。

CSVのサンプル

</Accordion>

<div data-zendesk-anchors="overview=appsflyer%E3%81%B8%E3%81%AE%E7%A7%BB%E8%A1%8C%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 01H8EDSTP8N4GZJQ5J609C3DHM=appsflyer%E3%81%B8%E3%81%AE%E7%A7%BB%E8%A1%8C%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 compare-measurement-between-appsflyer-and-adjust=appsflyer%E3%81%A8adjust%E3%81%AE%E8%A8%88%E6%B8%AC%E7%B5%90%E6%9E%9C%E3%81%AE%E6%AF%94%E8%BC%83 h_01HQJ10ZFJR43KBYMD9A07CJ99=appsflyer%E3%81%A8adjust%E3%81%AE%E8%A8%88%E6%B8%AC%E7%B5%90%E6%9E%9C%E3%81%AE%E6%AF%94%E8%BC%83 tasks=%E7%A7%BB%E8%A1%8C%E3%81%AB%E5%BF%85%E8%A6%81%E3%81%AA%E4%BD%9C%E6%A5%AD 01H8EDSTP8YGDZBPEY1976JP8C=%E7%A7%BB%E8%A1%8C%E3%81%AB%E5%BF%85%E8%A6%81%E3%81%AA%E4%BD%9C%E6%A5%AD 01JE3EC4C847ZEK769Y9G237KG=step-1-create-an-appsflyer-account 01JE3EC4C9V83D0V46EJK49JZ2=step-2-add-your-app 01JE3EC4CAKY4FQBPPZSJFP5V5=step-3-integrate-the-sdk step-4-migrate-devices%E2%80%94optional=step-4-migrate-devices-optional 01JE3EC4CPT4KAER27C8C0DHH7=step-4-migrate-devices-optional 01H8EDSTP93QJA4XZB6TDWWH1V=%E4%BE%8B 01JA2CAMW3HCHC4B9FX7517FJ6=%E6%B3%A8%E6%84%8F 01JE3EJ5DVXF1VT28ZCGR7SMF3=step-5-migrate-campaigns srns=%E3%82%BB%E3%83%AB%E3%83%95%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AFsrn 01JE3EXVNRMA2MFVPSJZ2RMR09=%E3%82%BB%E3%83%AB%E3%83%95%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AFsrn 01H8EDSTP9ZGMHSM44BWGF1FJN=%E6%B3%A8%E6%84%8F-1 nonsrn-ad-networks=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF 01JE3EXVNTWK4ZJS55WXHFKSMX=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF owned-media=%E3%82%AA%E3%82%A6%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 01JE3EXVNTS4FVXN370G1CR8Z9=%E3%82%AA%E3%82%A6%E3%83%B3%E3%83%89%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2 01JE3EXVP4TSMGSZD4B460RSQA=skan 01JE3F6VXDG9MDCVWN81RSHXVG=step-6-set-up-data-reporting additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 01JE3E5VHV2WCFWABC9FYQW3VG=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 01JE3FG6K95QT60C36R88WGDG4=attributed-migration attributed-device-migration-csv-structure=%E6%B5%81%E5%85%A5%E5%85%83%E6%83%85%E5%A0%B1%E3%82%92%E5%BC%95%E3%81%8D%E7%B6%99%E3%81%90%E7%A7%BB%E8%A1%8C%E3%81%AEcsv%E5%BD%A2%E5%BC%8F 01H8EDSTP9HABKEZJXMB84CDDE=%E6%B5%81%E5%85%A5%E5%85%83%E6%83%85%E5%A0%B1%E3%82%92%E5%BC%95%E3%81%8D%E7%B6%99%E3%81%90%E7%A7%BB%E8%A1%8C%E3%81%AEcsv%E5%BD%A2%E5%BC%8F 01JE3FG6MKNJMTHSR5B2ZMQP1K=nonattributed-migration nonattributed-device-migration-csv-file-structure=%E6%B5%81%E5%85%A5%E5%85%83%E6%83%85%E5%A0%B1%E3%82%92%E5%BC%95%E3%81%8D%E7%B6%99%E3%81%8C%E3%81%AA%E3%81%84%E7%A7%BB%E8%A1%8C%E3%81%AEcsv%E5%BD%A2%E5%BC%8F 01H8EDSTP9AFDMQS6BPQJY19ZH=%E6%B5%81%E5%85%A5%E5%85%83%E6%83%85%E5%A0%B1%E3%82%92%E5%BC%95%E3%81%8D%E7%B6%99%E3%81%8C%E3%81%AA%E3%81%84%E7%A7%BB%E8%A1%8C%E3%81%AEcsv%E5%BD%A2%E5%BC%8F" />
