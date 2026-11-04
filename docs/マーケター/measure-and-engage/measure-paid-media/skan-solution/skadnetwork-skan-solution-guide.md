---
title: SKAdNetwork（SKAN）ソリューションガイド
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-07-25T21:19:42Z'
  edited_at: '2026-10-28T09:17:28Z'
  id: 360011420698
  locale: ja
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ja/articles/360011420698
---
> **概要**：SKANを使用したアプリインストールのアトリビューションについて説明します。

![5754](https://files.readme.io/a970d7b0e8da300ded2138f941bf2e891f32d396c8500292534992a4b4449d71-30757780264337.png)

## SKAN

AppleのiOSに組み込まれているSKAdNetwork（SKAN）を使用すると、広告主はユーザーのプライバシーを保護しながら、キャンペーンの成果を計測できます。 SKANは、IDFAなどの広告IDを使用せずに動作します。 SKANの動作にATTの同意は必要ありません。

<div id="tip" />

> 👍 **ヒント**
>
> * iOS15以降では、<Anchor target="_blank" href="/marketers/ja/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">SKANポストバックのコピー</Anchor>をAppsFlyerに送信することを推奨します。これにより、AppsFlyerはポストバック内のコンバージョン値が改ざんされていないことを確認できます。
> * AppsFlyerのSKANソリューションをさらに詳しく知りたい場合は、 <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/internal/view/elearning/7810/ios14-and-skadnetwork">AppsFlyer Learning Portalの短い解説コース</Anchor>をご覧ください。

**用語の定義**

* <Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">SDK</Anchor>：アプリに実装された、現行バージョンのAppsFlyer iOS SDK。
* **SKAN計測期間**：SKAN 4以降が対象です。インストール後のユーザー行動を計測する期間は、次の3つのウィンドウに分かれています。
  * ウィンドウ1：1〜2日目
  * ウィンドウ2：3〜7日目
  * ウィンドウ3：8〜35日目
* **コンバージョン値（CV）**：ユーザーの質を示す値です。SKAN 4では各計測期間の終了後、SKAN 3以前ではアクティビティ期間の終了後に、iOSが送信するポストバックで報告されます。 AppsFlyer SDKがCVを設定します。 CVを独自に設定する場合は、<Anchor target="_blank" href="/marketers/ja/docs/skan-cv-decode-map-your-cv-to-events">デコード</Anchor>を使用し、CVのマッピングファイルをアップロードしてください。
  * SKAN 4以降には、細かいコンバージョン値（fine）と粗いコンバージョン値（coarse）の両方があります。
* **Conversion Studio**：SKANの仕組みで使われるコンバージョン値（CV）とイベントを対応付けるAppsFlyerのソリューション。
* **ソリューション：** SDK、SKANの仕組み、Conversion Studio、AppsFlyerプラットフォームが連携して動作する構成。 AppsFlyerのSKANソリューションは、ダッシュボードでの分析、レポート、ポストバックを通じて、広告主とアドネットワークにLTVデータを提供します。
* **アクティビティ期間：** SKAN 3以前が対象です。アプリの初回起動から始まる、あらかじめ定めた長さの期間です。デフォルトは24時間です。 SKAN 4以降を使用していても、ユーザーのデバイスやアドネットワークがまだSKAN 4に対応していない場合は、アクティビティ期間は48時間になります。

この記事では、SKANの仕組みとAppsFlyerのソリューションについて、主な仕様を説明します。計測の設定については、<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>を参照してください。

<div id="about-apple-skan" />

<Accordion title="AppleのSKANについて">

| 項目 | 説明 |
| --- | --- |
| 前提条件 | アプリでSKANを使用するには、以下が必要です。<ul><li>広告対象のアプリ（自社アプリ）にAppsFlyer SDKを実装し、CVを設定します。代わりに、<Anchor target="_blank" href="/marketers/ja/docs/skan-cv-decode-map-your-cv-to-events">デコードモード</Anchor>を使用してCVを設定することもできます。</li><li>広告掲載元アプリ（広告を表示するアプリ）では、<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app">ソースアプリの設定</Anchor>が必要です。</li><li><Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/registering_an_ad_network">アドネットワークはAppleに登録する必要があります。</Anchor></li></ul><strong>\*注意：</strong>CVを設定する別のSDKがアプリに実装されていないことを確認してください。 |
| 対応範囲 | <ul><li>対応するSKAdNetworkのバージョンは、iOSのバージョンによって異なります。<ul><li>iOS11〜13：V1（インストールのみ。CVなし）</li><li>iOS14〜14.5：V2以降（CVあり）</li><li>iOS14.6〜16：V3（CVあり）</li><li>iOS16.1以降：V4以降（3つのウィンドウに対応するCVがあり、細かい値と粗い値の両方に対応）</li></ul></li><li>アプリ間のアトリビューション</li></ul> |
| 制限事項 | <ul><li>Apple Ads（Search Ads）は、SKANバージョン1〜3に対応しています。ビュースルーとSKAN 4への対応は保留中です。</li><li>モバイルWebには対応していません。</li><li>SKAN 4より前では、キャンペーンIDは<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skstoreproductparameteradnetworkcampaignidentifier">1〜100に制限</Anchor>されています。つまり、アドネットワークごと・アプリごとに100種類の値を使用できます。 アドネットワークが、キャンペーンIDとキャンペーン名をAppsFlyerに提供します。これらはAppsFlyerのダッシュボードとレポートに反映されます。</li><li>SKAN 4以降では、ソース識別子は1〜10,000です。</li><li>オーガニックインストール：SKANはオーガニックインストールに対応していません。</li><li>リエンゲージメント。</li></ul> |
| SKANのアトリビューション原則 | <ul><li>SKANは、以下の<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">アトリビューションモデル</Anchor>を使用します。<ul><li>ユーザーが広告をクリックし、30日以内にアプリをインストール（ダウンロード）した後、60日以内に初めて起動します。</li><li>ユーザーが広告を閲覧し、24時間以内にアプリをインストール（ダウンロード）した後、60日以内に初めて起動します。</li><li>SKAdNetwork V2.2以降では、クリックスルーアトリビューションがビュースルーアトリビューションより優先されます。 SKANのバージョンは、iOSのバージョンによって異なります。</li><li>iOSが、帰属先のアドネットワークにポストバックを送信します。 iOS15以降では、広告主はポストバックのコピーをAppsFlyerに直接送信できます。</li></ul></li></ul> |
| クラウド匿名性 | Appleは、ユーザーのプライバシーを保護するため、一部のポストバックで提供する情報を制限します。 Appleによると、プライバシー階層の制限に抵触する場合、ポストバックには細かいCVや粗いCV、ソースアプリID、完全なソース識別子は含まれません。<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">詳細はこちら</Anchor> |

</Accordion>

<div id="appsflyer-skan-solution" />

## AppsFlyerのSKANソリューション

AppsFlyerは、iOSからのSKANポストバックを使用して、iOSのアトリビューション結果を集計して提供します。これらのポストバックは、iOSからアドネットワークに送信され、その後AppsFlyerに転送されます。ポストバックには、広告主が設定したCVを含む、匿名化されたアトリビューションレコードが格納されています。 CVは、インストール直後の一定期間におけるユーザーの質を示す値です。

AppsFlyerのSKANソリューションは、広告主に以下を提供します。

* すべてのアドネットワークからのポストバックを集計し、コストなどの情報を加えたSKANデータを、ダッシュボードとレポートで確認できます。
* AppsFlyer Conversion Studioで、アプリのコードを変更せずにCVの計測内容を設定できます。 CVでは、収益、エンゲージメント、コンバージョンイベントを計測できます。  
  **注意：** CVの設定は、AppsFlyer SDKだけが行うようにしてください。 CVを設定する別のSDKがアプリに実装されていないことを確認してください。

<div id="principles-and-flow" />

<Accordion title="原則と処理の流れ">

<div id="skan-attribution-flow" />

#### **SKANアトリビューションの流れ**

![SKAN_flow_-_Affinity_diagram_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. 広告主がAppsFlyer Conversion StudioでSKAN計測を設定します。
2. ユーザーがアプリを初めて起動します。
3. 各ウィンドウで、AppsFlyerがユーザーの行動と定義済みのCVスキーマに基づいてCVを設定します。
4. ウィンドウが終了すると、iOSがアドネットワークにポストバックを送信し、そのコピーをAppsFlyerに送信します。ポストバックが届くまでには、以下の時間がかかります。
   * SKAN 4の計測ウィンドウ1：24〜48時間
   * SKAN 4の計測ウィンドウ2〜3：24〜144時間
   * SKAN 3：CVが最後に増加してから24〜48時間後。
5. iOSデバイスからAppsFlyerに直接送信されたポストバックのコピーは、広告主が指定したエンドポイントに転送されます。 <Anchor target="_blank" href="/marketers/ja/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">SKANポストバックのコピーをAppsFlyerに送信する方法</Anchor>を参照してください。
6. アドネットワークが情報を追加したポストバックをAppsFlyerに転送するか、SRNがAPI経由でポストバックデータを共有します。
7. AppsFlyerがCVを検証し、デコードします。デコードしたデータを記録・アトリビューションした後、AppsFlyerのダッシュボード、レポート、APIで提供します。

AppsFlyerのSKANソリューションは、SKAdNetworkの仕組みに伴う機能・構造上の制限を補うため、以下の表の項目に対応しています。

| 項目 | 説明 |
| --- | --- |
| データの収集 | <ul><li>広告主に代わって、複数のアドネットワークからSKAdNetworkポストバックを収集します。</li><li>広告主が、複雑で手間のかかるアドネットワークごとの個別連携を行う必要はありません。</li></ul> |
| データの検証 | <ul><li>ポストバックがAppleによって署名されていることを確認し、改ざんの可能性を低減します。</li><li>トランザクションIDのフィールドを使用し、ポストバックが重複していないことを確認します。</li></ul> |
| データの補完 | <ul><li>SKAdNetworkポストバックにほかの情報を加え、ROIを総合的に分析できるようにします。たとえば、アドネットワークが提供するキャンペーン名などが該当します。</li><li>追加されるデータには、インプレッション、クリック、コストなどがあります。</li></ul> |
| データの提供 | 情報を補完したSKAdNetworkデータは、以下で利用できます。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAdNetworkソリューションのダッシュボード</Anchor></li><li>[ダウンロード可能なレポート](/docs/skadnetwork-skan-solution-guide#reporting-options)</li></ul> |
| スムーズな導入 | <ul><li>必要な処理がソリューションに組み込まれているため、広告主はアプリ設定画面でほとんど手間をかけずに導入できます。</li><li>コーディングは不要です。アプリには最新バージョンのSDKが必要です。</li><li>AppleによるSKAdNetworkの仕組みの変更を想定した対応も含まれています。</li></ul> |
| 柔軟な変更 | 広告主は、必要に応じてダッシュボードで計測設定を変更できます。 |

</Accordion>

<div id="conversion-studio" />

<Accordion title="Conversion Studio">

AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">Conversion Studio</Anchor>は、SKANソリューションの中核となる機能です。 CVの各ビットを無駄なく活用できるよう、柔軟に設定できます。インストール後のどの行動をどのくらいの期間計測するかなど、CVに反映する計測データを細かく指定できます。 CVの設定には、複数の計測モードを使用できます。

| 種類 | 計測モード | 説明 | アクティビティ期間 |
| --- | --- | --- | --- |
| 可変 | SKAN 4.0<br /><br />［推奨］ | 設定可能な3つの計測期間で、収益、コンバージョン（アプリ内イベント）、エンゲージメントを組み合わせて計測します。 | <ul><li>ウィンドウ1：1〜2日目</li><li>ウィンドウ2：3〜7日目</li><li>ウィンドウ3：8〜35日目</li></ul> |
| 可変 | <Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#custom">カスタム</Anchor> | 設定可能なアクティビティ期間で、収益、コンバージョン（アプリ内イベント）、エンゲージメントを組み合わせて計測します。 | 12時間〜63日 |
| 固定 | 収益<br /><br />［デフォルト］<br /><br />［従来のモード］ | 以下のいずれかの範囲で収益を計測します。<ul><li>1〜630ドルを10ドル刻み</li><li>1〜63ドルを1ドル刻み</li><li>0.01〜0.63ドルを0.01ドル刻み</li></ul> | 24時間 |
| 固定 | コンバージョン<br /><br />［従来のモード］ | アプリ内イベントを1〜6個選択します。 | 24時間 |
| 固定 | エンゲージメント<br /><br />［従来のモード］ | ユーザーがイベントを実行した回数 | 24時間 |
| 可変 | <Anchor target="_blank" href="/marketers/ja/docs/skan-cv-decode-map-your-cv-to-events">デコード</Anchor> | <ul><li>CVとイベントの対応関係を独自に定義し、アプリ側でCVを設定します。 AppsFlyer SDKをアプリに実装できない場合は、このオプションを使用します。デコードを使用するには、<strong>［SKAN Conversion Studio］</strong>でオプション（⋮）をクリックし、<strong>［カスタムデコードマッピングファイルをアップロード］</strong>を選択します。</li></ul> | 12〜1,512時間（63日） |

</Accordion>

<div id="additional-skadnetwork-information" />

## SKAdNetworkの補足情報

<div id="reporting-options" />

<Accordion title="レポートの種類">

SKAdNetworkレポートには、ユーザーレベルの識別子は含まれません。

| レポート名 | 種類 | AppsFlyerによるデータ補完 | 提供方法 | プレミアム機能 |
| --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/skan-aggregated-performance-report-api">SKAN集計パフォーマンスレポート。</Anchor><br /><br />インストール、アプリ内イベント、収益の集計データ。 SKANダッシュボードと同様のデータです。 | インストール日またはポストバック到着日で集計 | はい | API | いいえ |
| <Anchor target="_blank" href="/marketers/ja/docs/skan-aggregated-postback-arrival-date-api">SKAN集計ポストバックレポート</Anchor>。<br /><br />SKANポストバックを、可能な限り細かい単位で集計したデータ。 | ポストバック到着日で集計 | いいえ | API | いいえ |
| <Anchor target="_blank" href="/marketers/ja/docs/skan-raw-data-reports#raw-data-report-types">Data Locker経由のSKANローデータ（行単位）レポート</Anchor>（例を含む）。<br /><br />利用できるレポート：<ul><li>iOSが送信し、アドネットワークパートナーが情報を追加したポストバック</li><li>インストール</li><li>再ダウンロード</li><li>アプリ内イベント</li><li>SRNの広告ディメンション</li></ul> |  | はい | Data Locker | はい。ローデータの契約が必要です。 Data Lockerの契約は不要です。 |
| Push API経由のSKANデータ |  | はい | Push API | はい |

</Accordion>

<div id="skadnetwork-solution-implementation-checklist" />

<Accordion title="SKAdNetworkソリューション導入チェックリスト">

| 番号 | 作業 | 説明 | 担当 |
| --- | --- | --- | --- |
| 1 | 準備 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">SKAdNetworkソリューションガイド</Anchor>を読む</li><li>関連資料：<Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">iOS14に向けたアプリの準備</Anchor></li></ul> | マーケター、開発者 |
| 2 | 設定 | AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>で、SKAdNetworkソリューションを設定します。 | マーケター |
| 3 | アプリの準備 | アプリをAppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">SDK V6</Anchor>に移行します。<ul><li>アプリのロジックやコードを変更する必要はありません。</li><li>AppsFlyerのSKANソリューションは、アプリ内イベントを基にCVを設定します。アプリ内イベントは通常どおり送信してください。 SKANソリューション専用のテストは不要です。</li><li>App Storeにアプリを申請します。</li><li>App StoreでSKAdNetworkの登録や手続きを行う必要はありません。</li></ul> | 開発者 |
| 4 | パートナー連携 | アドネットワークパートナーは、SKAdNetwork連携を使用してAppsFlyerと連携する必要があります。注意！ AppsFlyerのSKAdNetworkシミュレーションには、現在の連携状況にかかわらず、すべてのパートナーのデータが含まれます。一方、本番のSKAdNetworkポストバックで報告されるデータに、すべてのパートナーが含まれるとは限りません。<br /><br />キャンペーンを実施しているパートナーについて、必要に応じて以下を確認・設定してください。<br /><br />**非SRN**：<ol><li>パートナーにAppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#c-transaction-id">SKAdNetwork対応バッジ</Anchor>が付いており、パートナー側の管理画面でSKAdNetworkキャンペーンのレポートが有効になっていることを確認します。</li><li>[アプリ内イベント名が、パートナー側のアプリ内イベント名にマッピングされている](#sending-postbacks-to-integrated-partners)ことを確認します。</li></ol>**Meta広告**：<ul><li><Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-interoperation-with-meta-ads">AppsFlyerのSKAdNetworkとMeta広告の連携を設定します。</Anchor></li></ul> | マーケター |

</Accordion>

<div id="troubleshooting-guide" />

<Accordion title="トラブルシューティングガイド">

| 症状 | 説明 |
| --- | --- |
| ダッシュボードにノンオーガニックインストールが表示されない。 | <ol><li><strong>［SKAdNetwork計測］</strong>がオンになっていることを確認します。<ol><li>**［設定］**＞<strong>［SKAN Conversion Studio］</strong>に移動します。</li><li>オプション（⋮）<strong>をクリックし、</strong>SKAN計測の設定を確認します。</li></ol></li><li>SDKのバージョンが6.2.6以降であることを確認します。<ul><li>**［連携］**＞<strong>［SDK情報］＞［SDKバージョン別ユーザー数］</strong>に移動して確認できます。</li></ul></li><li>SDKプラグインを使用している場合は、AppsFlyerのSKAdNetworkに対応するバージョンを実装していることを確認します。</li><li>アドネットワークパートナーがAppsFlyerと連携しており、iOSポストバックをAppsFlyerに転送していることを確認します。</li></ol> |
| ダッシュボードにノンオーガニックインストールはあるが、アプリ内イベントがまったく表示されない。 | <ol><li>SDKのバージョンが6.2.6以降であることを確認します。<ul><li>**［連携］**＞<strong>［SDK情報］＞［SDKバージョン別ユーザー数］</strong>に移動して確認できます。</li></ul></li><li>SDKプラグインを使用している場合は、AppsFlyerのSKAdNetworkに対応するバージョンを実装していることを確認します。</li><li>S2Sでイベントを送信していますか？送信している場合は、<strong>［サーバー間APIで送信されたアプリ内イベントを記録］</strong>がオンになっていることを確認します。<ol><li>**［設定］**＞<strong>［SKAN Conversion Studio］</strong>に移動します。</li><li>**オプション（⋮）をクリックし、S2S設定がオンになっていることを確認します。** 注意：カスタムモードとデコードモードでは、この設定は常にオンで、変更できません。</li></ol></li></ol> |
| ダッシュボードにインストールと一部のアプリ内イベントが表示される。一部のアプリ内イベントが表示されない。 | <ol><li>S2Sでイベントを送信していますか？送信している場合は、<strong>［サーバー間APIで送信されたアプリ内イベントを記録］</strong>がオンになっていることを確認します。<ol><li>**［設定］**＞<strong>［SKAN Conversion Studio］</strong>に移動します。</li><li>**オプション（⋮）をクリックし、S2S設定がオンになっていることを確認します。** 注意：カスタムモードとデコードモードでは、この設定は常にオンで、変更できません。</li></ol></li><li><Anchor target="_blank" href="/marketers/ja/docs/skan-raw-data-reports#raw-data-report-types">ポストバックのローデータ</Anchor>で、すべてのイベントが報告されているか確認します。</li></ol> |
| 地域（国）の情報が実際と異なる | 地域データは、以下の情報から取得されます。<ul><li>アドネットワークがAppsFlyerに報告した、キャンペーンに紐づく国。</li><li>デバイスのIPアドレス。 iOS14.6以降では、このアドレスはプロキシのアドレスであり、ユーザーの実際の所在地を示すものではありません。</li></ul> |

</Accordion>

<div id="timing-from-app-install-until-dashboard-and-reports-update" />

<Accordion title="アプリのインストールからダッシュボード・レポートの更新までの時間">

| 記号 | 要素名 | 説明 | 例A | 例B | 例C | 例D | 例E |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | SKAN 4の計測ウィンドウ1 | <ul><li>期間中、アプリがCVを設定します。</li><li>0〜2日</li><li>Conversion Studioで、2日より前に期間を終了できます。</li></ul> | - | - | 2日 | - | - |
| B | SKAN 4の計測ウィンドウ2 | <ul><li>期間中、アプリがCVを設定します。</li><li>3〜7日</li><li>Conversion Studioで、7日より前に期間を終了できます。</li></ul> | - | - | - | 7日 | - |
| C | SKAN 4の計測ウィンドウ3 | <ul><li>期間中、アプリがCVを設定します。</li><li>8〜35日</li><li>Conversion Studioで、35日より前に期間を終了できます。</li></ul> | - | - |  | - | 35日 |
| D | SKAN 4の計測ウィンドウ1のポストバック遅延 | 24〜48時間 | - | - | 24〜48時間 | - | - |
| E | SKAN 4の計測ウィンドウ2〜3の遅延 | 24〜144時間 | - | - | - | 24〜144時間 | 24〜144時間 |
| F | アクティビティ期間<br /><br />（SKAN 4には適用されません） | <ul><li>期間中、アプリがCVを設定します。</li><li>この期間は、アプリの初回起動時に始まります。</li><li>期間は12時間〜63日です。</li></ul> | 24時間 | 72時間 | - | - | - |
| G | SKAdNetworkタイマー<br /><br />（SKAN 4には適用されません） | <ul><li>24時間のカウントダウンタイマー。</li><li>CVが増加するたびに、タイマーがリセットされます。つまり、24時間のカウントダウンが再び始まります。</li></ul> | 0〜24時間 | 0〜24時間 | - | - | - |
| H | SKAdNetworkのランダムな遅延<br /><br />（SKAN 4には適用されません） | ポストバックのランダムな遅延時間。 F+Gで定義される期間の終了時に、カウントダウンが始まります。 | 0〜24時間 | 0〜24時間 | - | - | - |
| I | AppsFlyerでの処理 | その日に受信したポストバックは、翌日の00:01（UTC）からまとめて処理されます。データは、その8時間後に利用できます。つまり、受信から処理完了まで8〜32時間かかります。平均すると、20時間の遅延が発生します。たとえば、月曜日に受信したポストバックは火曜日に処理されます。ダッシュボードは08:00（UTC）までに更新されます。 | 8〜32時間 | 8〜32時間 | 8〜32時間 | 8〜32時間 | 8〜32時間 |
| J | まとめ | 経過時間の合計 | 32〜104時間 | 80〜152時間 | 80〜128時間 | 200〜344時間 | 872〜1,016時間 |

</Accordion>

<div id="organic-metrics-in-the-context-of-skadnetwork" />

<Accordion title="SKAdNetworkにおけるオーガニック指標">

SKAdNetworkダッシュボードのオーガニック指標は、以下の仕組みで算出されます。

* **オーガニック収益**は、<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#fixed-modes">固定モード</Anchor>または従来のモードで［収益］を使用する場合にのみ利用できます。
* **オーガニックのアプリ内**イベントは、<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#fixed-modes">固定モード</Anchor>または従来のモードで［コンバージョン］を使用する場合にのみ利用できます。
* **従来のモード以外**（<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#skan-4">SKAN 4</Anchor>、カスタムエンコード、デコード）では、オーガニックデータはインストールについてのみ利用できます。
* AppleのSKAdNetworkは、メディアソースとの接触後にインストールしたユーザーについてポストバックを送信します。これがノンオーガニック指標の基になります。
* AppsFlyerのアトリビューションダッシュボードには、流入元にかかわらず、すべてのインストールの指標が含まれます。  <Anchor target="_blank" href="/marketers/ja/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side">AppsFlyerとSKANのアトリビューションを並べて表示する方法</Anchor>を参照してください。
* このデータを使用し、オーガニック指標をA−Bで算出します。
  * A＝従来のOverview dashboardに基づく、すべてのユーザーの合計
  * B＝SKAdNetworkポストバックで報告されたノンオーガニックユーザー数

**Apple Adsに関する注意点**：従来のダッシュボードでは、Apple Adsが獲得したインストールはノンオーガニックに分類されます。ただし、SKAdNetworkではオーガニック指標に含まれます。

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| アドネットワークのアクセス | アドネットワークにはポストバックが提供されます。 |
| 代理店 | 対応していません。代理店が、SKAdNetworkキャンペーンを実施するアドネットワークを有効にすることはできません。代理店の方へご自身で有効にせず、広告主にアドネットワークの有効化を依頼してください。代理店は、<Anchor target="_blank" href="/partners/ja/docs/getting-started-agency-onboarding#skadnetworkの代理店データ">SKANの代理店識別</Anchor>を実装することで、自社が獲得したユーザーであることを示せます。 |
| 運用媒体の開示設定 | N/A |
| タイムゾーン | UTC |
| 通貨 | USD |
| オーガニックデータ | SDKイベントデータに基づきます。たとえば、オーガニックインストール数は、SDKが報告した全インストール数から、SKAdNetworkが報告したノンオーガニックインストール数を差し引いて算出します。 |
| ノンオーガニックデータ | SKAdNetworkポストバックに基づきます。 |
| データの更新頻度 | 日次 |
| 過去のデータ | 最も古い日付は、iOS14の提供開始日（2020年9月16日）です。 |
| ユーザーのアクセス | アカウントユーザーには、<Anchor target="_blank" href="/marketers/ja/docs/user-management">所定の権限</Anchor>が必要です。 |
| App Clips | SKAdNetworkダッシュボードでは、App Clipsはオーガニックに帰属します。起動元のメディアソースは、Overview dashboardで確認してください。 |

</Accordion>

<div id="skan-integrated-partners" />

## SKANの連携済みパートナー

<div id="recording-ad-revenue" />

<Accordion title="広告収益の記録">

SKAdNetworkの計測期間中に発生した広告収益を、ユーザーを獲得したキャンペーンに帰属させます。現在は、SDKを介した汎用インプレッション単位の広告収益連携を実装している広告主のみが対象です。

SKANダッシュボードに広告収益を記録する手順：

* アプリに<Anchor target="_blank" href="/marketers/ja/docs/integrate-the-roi360-ad-revenue-sdk-api">汎用インプレッション単位の広告収益SDK</Anchor>を実装します。
* SKAN Conversion Studioの固定モード［従来のモード］を使用している場合は、<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#report-events-by-servertoserver-api">SKAdNetworkのサーバー間連携をオン</Anchor>にします。

**注意**：メディエーションで利用できる広告ソースについては、<Anchor target="_blank" href="/marketers/ja/docs/integrate-the-roi360-ad-revenue-sdk-api">汎用SDKコネクター</Anchor>のドキュメントを参照してください。

</Accordion>

<div id="sending-postbacks-to-integrated-partners" />

<Accordion title="連携済みパートナーへのポストバック送信">

AppsFlyerは、連携済みパートナーにSKANアトリビューションのポストバックを送信します。SKAN 4では、ウィンドウ1のポストバックのみを送信します。

利用できるオプションと要件は、以下の表で確認してください。

| 項目 | 説明 |
| --- | --- |
| トランザクションIDの共有 | **必要な対応**：連携済みパートナーに<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/verifying_an_install_validation_postback">トランザクションID</Anchor>が必要か確認し、それに応じて設定してください。<br /><br />AppsFlyerは、帰属先のアドネットワークパートナーにポストバックを送信します。これはデコード済みのポストバックであり、iOSから受信したSKAdNetworkポストバックのコピーではありません。これらのポストバックには、インストールに関するデコード済みCVデータと、アクティビティ期間中のユーザー行動に対応するアプリ内イベントデータが含まれます。<br /><br />トランザクションIDを使用するとCVをデコードできるため、広告主の許可なく共有することはありません。<br /><br />**トランザクションIDの共有**<br /><br />広告主が<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#b-advanced-privacy">トランザクションIDの共有を有効にする</Anchor>手順は次のとおりです。AppsFlyerで、**［連携］**＞**［有効な連携］**＞対象のパートナー＞**［連携］タブ**＞<strong>［データ共有］</strong>に移動します。 |
| アプリ内イベントのマッピング確認 | **必要な対応**：パートナーがポストバックを正しく記録できるよう、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#マッピング方法">アプリ内イベントを、対応するパートナー側のイベント名にマッピング</Anchor>する必要があります。<br /><br />SKAdNetworkキャンペーンを実施する各パートナーについて、アプリで選択した計測タイプに合わせて、アプリ内イベントが設定されていることを確認します。<br /><br />**パートナーへのアプリ内イベントのマッピングを確認・変更する手順**：<ol><li>AppsFlyerで、**［連携］**＞<strong>［有効な連携］</strong>に移動します。</li><li>パートナーを選択します。</li><li><strong>［連携］</strong>タブに移動します。</li><li>以下の設定を確認し、必要に応じて変更します。<ol><li><strong>［アプリ内イベントポストバック］</strong>をオンにします。</li><li>SKAdNetwork計測で設定したアプリ内イベントの**SDKイベント名**が、**パートナー側のイベント名／ID**にマッピングされていることを確認します。</li></ol></li><li><strong>［連携を保存］</strong>をクリックします。</li></ol> |

</Accordion>

<div id="see-also" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/about-att-and-skan">iOS14、ATT、SKANのクイックスタートガイドとよくある質問</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">SKAN Conversion Studioでの計測設定（SKAdNetwork設定）</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">AppsFlyerのSKANダッシュボード</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/skan-integrated-partners-list">SKANの連携済みパートナー一覧</Anchor>
> * AppsFlyerで設定が必要なSKANパートナー連携：
>   * <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-interoperation-with-meta-ads">Meta広告</Anchor>
>   * <Anchor target="_blank" href="/marketers/ja/docs/get-skan-postback-data-from-google-ads">Google広告</Anchor>
>   * <Anchor target="_blank" href="/marketers/ja/docs/skan-interoperation-with-tiktok-for-business">TikTok for Business</Anchor>
>   * <Anchor target="_blank" href="/marketers/ja/docs/skan-interoperation-with-snapchat">Snapchat</Anchor>