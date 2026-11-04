---
title: ROI360の広告費APIの設定と広告費データの計測
metadata:
  keywords:
    - ROI
    - cost
    - Advertisers
    - Agencies
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
  created_at: '2020-05-19T12:50:13Z'
  edited_at: '2026-10-28T08:43:34Z'
  id: 360008850257
  locale: ja
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ja/articles/360008850257
---
> **At a glance:** アプリ単位またはメディアソースのアカウント単位で広告費APIを利用し、広告費に関連するLTV（顧客生涯価値）ベースの成果指標を含む、マーケティング広告費の集計データを取得します。

<div id="overview" />

## 概要

ROI360は、アプリ単位とアカウント単位の両方で広告費を計測できます。アプリごとの詳細な広告費や、メディアソースのアカウント全体の広告費を分析できます。

広告費連携の管理場所は、メディアソースによって次の2つに分かれます。

* **アカウント単位の連携**は、<strong>［広告費設定］</strong>で管理します。広告アカウント単位で連携を設定します。[対応するアドネットワークの一覧](#h_01KQ7V7Q6MAEMXKKJ7TV8GC1YR)を参照してください。
* **アプリ単位の連携**は、<strong>［広告費］</strong>タブで管理します。アプリごとに個別に連携を設定します。メディアソースが<strong>［広告費設定］</strong>にない場合は、アプリ単位の<strong>［広告費］</strong>タブで連携を設定してください。

<div id="additional-steps-specific-media-sources-only" />

<div id="h_01M43Y9WQ8HK1N0GJNW5BH4MPZ" />

<div id="h_01M43Y9WQ8WCXWQ0S9ZAT59CWW" />

<div id="map-apps-to-package-names-or-bundle-ids" />

<div id="create-a-new-api-cost-integration" />

> 📘 **Note**
>
> 広告費設定へのアクセスは、ロールの権限によって制御されます。<strong>［広告費設定］</strong>を開けない場合は、<strong>［ユーザー管理］</strong>ページでロールの権限を更新するよう、管理者に依頼してください。該当する権限は<strong>［広告費連携］</strong>です。

## 広告費APIの有効化

広告費連携は、アプリ単位またはアカウント単位のいずれかの方法で有効にできます。

<Accordion title="アプリ単位での広告費連携の有効化（広告費タブ）">

特定のアプリに対してメディアソースとの広告費連携を設定するには、次の手順を実行します。

1. AppsFlyerのサイドメニューから<strong>［コラボレーション］</strong>＞**［パートナー連携］**＞<strong>［有効な連携］</strong>を選択し、パートナーを選択します。
2. <strong>［連携を管理］</strong>をクリックします。
3. 連携済みパートナーの<strong>［広告費］</strong>タブを開きます。
4. <strong>［広告費データを取得］</strong>をオンにします。パートナーとの接続に必要な項目が表示されます。
5. パートナーとの広告費連携を設定し、認証を行います。認証方法はメディアソースによって異なります。以下の[広告費の連携方法](#広告費の連携方法)を参照してください。
6. パートナーの広告費設定に<strong>［サイトIDマッピング］</strong>がある場合は、ドロップダウンから使用するサイトIDの設定を選択します。以下の[サイトIDマッピング](#サイトidマッピング)を参照してください。
7. <strong>［広告費設定を保存］</strong>をクリックします。
   * 5～6時間以内に、ダッシュボードに広告費データが表示され始めます。
   * AppsFlyerは、平均4時間に1回、1日6回パートナーからデータを取得します。
   * <strong>［広告費設定］</strong>内のメディアソースアカウントには、アプリ単位の<strong>［広告費］</strong>タブで行った変更が反映されます。

</Accordion>

<Accordion title="アカウント単位での広告費連携の有効化（広告費設定ページ）">

メディアソースのアカウントを一度接続すれば、AppsFlyerアカウント内の複数またはすべてのアプリで広告費連携を有効にできます。

アカウント単位で広告費連携を有効にするには、次の手順を実行します。

1. AppsFlyerのサイドメニューから<strong>［設定］</strong>＞**［ROI360］**＞<strong>［広告費設定］</strong>を開きます。
2. 広告費データを取得するメディアソースを選択し、<strong>［次へ］</strong>をクリックします。
3. メディアソースとの広告費連携を設定し、認証を行います。認証方法はメディアソースによって異なります。以下の[広告費の連携方法](#広告費の連携方法)を参照してください。
4. 広告費連携の名前を入力、または変更します。
5. この広告費連携の対象に含めるアプリを選択します。
6. <strong>［連携を保存］</strong>をクリックします。
   * 5～6時間以内に、ダッシュボードに広告費データが表示され始めます。
   * AppsFlyerは、平均4時間に1回、1日6回メディアソースからデータを取得します。
   * アカウント単位の<strong>［広告費設定］</strong>で行った変更は、該当するアプリとメディアソースの<strong>［有効な連携］</strong>にある<strong>［広告費］</strong>タブにも自動的に反映されます。

</Accordion>

<div id="select-which-ad-account-to-pull-cost-from" />

> 📘 **Note**
>
> 代理店にキャンペーン運用を委託している場合は、広告主ではなく代理店が対象パートナーとの連携を行うことを推奨します。同じアプリに対して、広告主と代理店の両方が同じ認証情報でメディアソースと連携すると、広告費データが重複するためです。

## 広告費の連携方法

広告費連携を有効にする方法は、メディアソースとAppsFlyerの連携方式によって異なります。次のいずれかの方法を使用します。

* <strong>ログイン</strong>：<strong>［`<media source>`にログイン］</strong>をクリックし、メディアソースのログインウィンドウを開きます。その後、メディアソースの案内に従ってログインします。
* **認証情報**：**APIキー**など、メディアソース固有のパラメータの値を入力します。
* **なし：** [上記](#広告費apiの有効化)の手順で<strong>［広告費データを取得］</strong>をオンにする以外に、接続設定は不要です。

各メディアソースの方式は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">メディアソースの広告費連携一覧</Anchor>の<strong>［連携方法］</strong>列で確認できます。

<div id="map-apps-to-site-ids" />

## サイトIDマッピング

<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">一部のメディアソースの連携</Anchor>では、広告費を報告する際に<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#attribution::e9b53459">サイトID</Anchor>フィールドに設定する値を選択できます。これにより、AppsFlyerのアトリビューションリンクに含まれる`site-id`マクロを、メディアソースが想定する値に合わせられます。

* デフォルトでは、サイトIDマッピングはアトリビューションリンク内のAppsFlyerマクロに合わせて設定されています。
* アトリビューションリンクで使用するマクロと、サイトIDマッピングで選択した値が異なると、サイトIDデータが正しく入力されません。

アプリ単位でサイトIDマッピングを設定するには：

1. 連携済みパートナーの<strong>［広告費］</strong>タブで<strong>［サイトIDマッピング］</strong>に移動し、ドロップダウンから設定を選択します。
2. <strong>［広告費設定を保存］</strong>をクリックします。変更はUTCの翌日から有効になります。

<div id="h_01M43Y9WQ8H8ANPDEGYCH0T0MF" />

<div id="view-status-in-cost-tab" />

<div id="view-status-in-cost-settings" />

<div id="h_01M43Y9WQ8ANZY2KNHKMV67YNY" />

<div id="h_01M43Y9WQ89XKB2CN2EY4TG2AD" />

<div id="h_01M43Y9WQ804YMN8TZ7HGYSQH7" />

<div id="cost-integration-and-agencies" />

<div id="view-cost-api-status" />

<div id="edit-and-delete-an-integration" />

## 広告費連携の削除

広告費連携は、アプリ単位またはアカウント単位で削除できます。削除すると、AppsFlyerはそのアカウントから広告費データを取得できなくなります。連携を削除しても、過去のデータには影響しません。

<Accordion title="アプリ単位での広告費連携の削除（広告費タブ）">

連携はいつでも削除できます。

アプリ単位で広告費連携を削除するには：

1. AppsFlyerのサイドメニューから<strong>［コラボレーション］</strong>＞**［パートナー連携］**＞<strong>［有効な連携］</strong>に移動します。
2. 連携済みパートナー（Meta広告など）を選択します。
3. <strong>［連携を管理］</strong>をクリックします。
4. <strong>［広告費］</strong>タブを開きます。接続済みアカウントの一覧が表示されます。
5. <strong>［操作］</strong>列で対象アカウントにカーソルを合わせ、<strong>［接続を削除］</strong>をクリックします。
6. 確認メッセージが表示されたら、<strong>［はい、削除します］</strong>をクリックします。

アプリ単位で設定されていた広告費連携が、アプリ単位とアカウント単位の両方から削除されます。広告費データの収集は直ちに停止します。すでに収集した過去の広告費データには影響しません。

</Accordion>

<Accordion title="アカウント単位での広告費連携の削除（広告費設定ページ）">

アカウント単位で広告費連携を削除するには：

1. AppsFlyerのサイドメニューから<strong>［設定］</strong>＞<strong>［ROI360］＞［広告費設定］</strong>を選択し、連携を削除するメディアソースを選択します。
2. メディアソースの連携一覧で、対象の連携をクリックします。
3. 確認メッセージが表示されたら、<strong>［はい、削除します］</strong>をクリックします。

アカウント単位で設定されていた広告費連携が、アプリ単位とアカウント単位の両方から削除されます。広告費データの収集は直ちに停止します。すでに収集した過去の広告費データには影響しません。

</Accordion>

## 広告費APIの無効化

広告費APIを無効にできるのは、アプリ単位のみです。

広告費APIをオフにするには：

1. <strong>［有効な連携］</strong>に移動し、メディアソースを選択します。
2. <strong>［広告費］</strong>タブを開きます。
3. <strong>［広告費データを取得］</strong>をオフにします。
4. <strong>［広告費設定を保存］</strong>をクリックします。

> 📘 **Note**
>
> 広告主が代理店との取引を終了し、アプリ単位で代理店権限をオフにしても、代理店側にそのアプリの広告費設定がある場合、広告費データの取得は継続します。取得を停止するには、広告主から代理店に、広告費連携をオフにするよう依頼する必要があります。

## 広告費APIのステータス

広告費連携の稼働状況は、以下で確認できます。

* <Anchor target="_blank" href="/marketers/ja/docs/dashboard-cost-and-ad-revenue-status">広告費・広告収益の連携状況ダッシュボード</Anchor>：アカウント内の1つ以上のアプリで広告費連携が有効になっているメディアソースを、まとめて確認できます。
* 連携済みパートナー：アプリごとの状況を確認できます。
* 広告費設定<strong>：［広告費設定］</strong>ページでは、アカウント単位とアプリ単位の両方の広告費APIステータスを確認できます。詳しくは、以下の「[メディアソース全体の広告費連携状況の確認](#h_01K3DGA6SKBPXEY18VJBCBNCJS)」を参照してください。

<Accordion title="メディアソースの広告費連携状況の確認（広告費タブ）">

メディアソースの<strong>［有効な連携］</strong>ページの<strong>［広告費］</strong>タブには、以下が表示されます（API経由の広告費取得に対応するメディアソースが対象）。

* 選択したアプリの広告費連携のステータス。
* そのアプリと一致する広告費データを、AppsFlyerが最後に正常に取得した日時。

選択したアプリのメディアソース別の広告費連携状況を確認するには：

1. AppsFlyerのサイドメニューから<strong>［コラボレーション］</strong>＞**［パートナー連携］**＞<strong>［有効な連携］</strong>に移動します。
2. メディアソースを選択します。
3. メディアソースの<strong>［有効な連携］</strong>ページで、タブバーの上にあるアプリ一覧から、広告費のステータスを確認するアプリを選択します。
4. <strong>［広告費］</strong>タブをクリックします。ステータスと最終同期日時が表示されます。

</Accordion>

<Accordion title="メディアソース全体の広告費連携状況の確認（広告費設定ページ）">

メディアソース全体の広告費連携状況を確認するには：

1. AppsFlyerのサイドメニューから<strong>［設定］</strong>＞<strong>［ROI360］＞［広告費設定］</strong>を選択します。
2. 対象のメディアソースを選択します。
3. メディアソースのページの<strong>［ステータス］</strong>列で、メディアソースアカウントのステータスを確認できます。アカウントに紐づくすべてのアプリが同じステータスであれば、そのステータスが表示されます。アプリごとにステータスが異なる場合は、<strong>［ステータス混在］</strong>と表示されます。
4. メディアソースアカウントに紐づく特定のアプリの状況を確認するには、対象アカウントの行をクリックして<strong>［広告費連携］</strong>ページを表示します。
5. メディアソースに紐づくアプリ一覧で、アプリのステータスを確認します。

</Accordion>

<Accordion title="ステータス一覧">

| ステータス | 補足／必要な対応 |
| --- | --- |
| 有効 | 連携が有効で、メディアソースに正常に接続されています。 |
| APIから一致する広告費データが返されない | 考えられる原因：  <br />• キャンペーンIDが提供されていないため、広告費をキャンペーンと照合できません。  <br />  <br />• AppsFlyerからパートナーにログインする際に、別の広告アカウント（別のMeta広告アカウントなど）を連携しました。正しいパートナーの広告アカウントを連携していることを確認してください。  <br />  <br />• パートナーの広告費連携に設定した認証情報のフィールドのいずれかに誤りがあります。例えば、バンドルIDなどです。連携の認証情報を確認し、修正してください。  <br />  <br />• キャンペーンが一時停止されており、データがありません。 |
| パートナーのAPIから応答がない | • 連携済みパートナーのサーバーがAppsFlyerに応答していません。  <br />• 6時間待ってください。同じステータスメッセージが表示され続ける場合は、AppsFlyerサポートにお問い合わせください。 |
| 認証情報が無効 | • 認証情報が無効なため、AppsFlyerがAPI経由でデータを取得できません。  <br />• 正しい認証情報で再接続してください。 |
| レポートAPIへのアクセスについて、アドネットワークの担当者にお問い合わせください。 | パートナーの担当者と連携し、パートナー側のシステムで広告費連携を有効にしてください。 |
| パートナーのAPIからデータが返されていません。連携設定を確認してください。 | 考えられる原因：  <br />• キャンペーンが一時停止されており、データがありません。 |
| パートナー側のシステムで、このアカウントによる広告費データの取得が有効になっていない | パートナーにお問い合わせください。 |
| ステータス混在 | 紐づくアプリのステータスが異なる場合にのみ、広告費設定＞**メディアソース**ページに表示されます。**メディアソース**ページから**連携**ページを開くと、アプリごとのステータスを確認できます。このステータスは、ステータスダッシュボードには表示されません。 |

</Accordion>

## アカウント単位の広告費設定に対応するメディアソース

ROI360をご利用のお客様は、<strong>［広告費設定］</strong>と<strong>［広告費］</strong>タブで、アカウント単位の広告費連携を作成・編集できます。次のメディアソースが、アカウント単位の広告費設定に対応しています。

<Accordion title="対応するメディアソース">

| 表示名 | 連携ID |
| --- | --- |
| AdAction3 | `adaction5_int` |
| Adbloom | `adbloom_int` |
| AdColony | `adcolony_int` |
| AdGate Media | `adgatemedia_int` |
| adjoe GmbH | `adjoe_int` |
| Adikteev Retargeting | `trademob_int` |
| Apple Search Ads | `iossearchads_int` |
| AppLift | `applift_int` |
| AppLovin | `applovin_int` |
| Aura | `aura_int` |
| Blind Ferret Agency | `blindferret_int` |
| Bluestacks | `bluestacks_int` |
| ByteDance | `bytedance_int` |
| Chartboost | `chartboost_int` |
| Dataseat | `dataseat_int` |
| Digital Turbine Legacy | `appia_int` |
| Digital Turbine On Device | `digitalturbine_int` |
| Domob | `domobc_int` |
| DV360 | `dv360_int` |
| GlobalWide Media | `globalwide_int` |
| Google広告 | `googleadwords_int` |
| InMobi | `inmobi_int` |
| InMobi DSP | `inmobidsp_int` |
| Liftoff Influence | `jetfuelit_int` |
| Mediaforce | `mediaforce_int` |
| Meta広告 | `facebook` |
| Mintegral | `mintegral_int` |
| Mobupps | `mobupps_int` |
| Moloco | `moloco_int` |
| MoPub Acquire | `crossinstall_int` |
| Opera Mobile | `operaevent_int` |
| Persona.ly RTB | `personalyrtb_int` |
| Pinterest | `pinterest_int` |
| Pinsight | `pinsight_int` |
| Point2Web | `point2web_int` |
| Reddit | `reddit_int` |
| Smadex | `smadex_int` |
| Snapchat | `snapchat_int` |
| Tapjoy | `tapjoy_int` |
| Taptica | `taptica_int` |
| TikTok | `tiktokglobal_int` |
| TUNE | `hasoffers_int` |
| Unity Ads | `unityads_int` |
| X (Twitter) | `twitter` |

> 📘 **Note**
>
> InCost対応アドネットワークを通じて、その他のメディアソースも利用できます。 InCost対応アドネットワークの全一覧は、担当のカスタマーサクセスマネージャー（CSM）にお問い合わせください。

</Accordion>

<div id="traits-and-limitations" />

## 仕様と制限事項

| 項目 | 説明 |
| --- | --- |
| 代理店 | 代理店は、広告費設定から複数のアプリの広告費連携を一括で設定することはできません。 |
| アカウント単位の広告費設定を、今後追加するアプリに自動適用する機能 | 現在は非対応 |
| 広告主と代理店が同じアドネットワークに接続した場合の広告費データ | **広告主と代理店の両方が同じアドネットワークアカウント（Google広告など）の広告費連携を設定した場合**、**成果が紐づいたアカウント**から広告費データを取得します。<br /><br />**例：**<ul><li>広告主が、自社の認証情報で広告費連携を設定します。</li><li>代理店が、代理店の認証情報で広告費連携を設定します。</li><li>成果は代理店アカウントに紐づいています。</li></ul>**結果：**<ul><li>ROI360は、**代理店の連携から広告費データを取得**します。</li><li>**広告主の連携**には「データなし」と表示されます。</li></ul> |
| Google広告費連携の自動切断 | <strong>［データなし］</strong>または<strong>［認証情報が無効］</strong>のステータスが365日を超えて連続した広告費連携は、自動的に切断されます。 Googleの連携にのみ適用されます。 |
| TikTokの広告主ID一覧の設定 | 広告主ID一覧は、アドネットワーク側のTikTokユーザーに紐づく広告主IDのみを使用して、アカウント単位で設定してください。<br /><br />アドネットワーク側のユーザーに紐づかない広告主IDを一覧に追加しても、そのIDの広告費データは返されません。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01K3DGA6SJ82CGNT0R422CF7RY=%E6%A6%82%E8%A6%81 enabling-cost-api=%E5%BA%83%E5%91%8A%E8%B2%BBapi%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01K3DGA6SJB0R7G9EKH1G76R8K=%E5%BA%83%E5%91%8A%E8%B2%BBapi%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 cost-integration-methods=%E5%BA%83%E5%91%8A%E8%B2%BB%E3%81%AE%E9%80%A3%E6%90%BA%E6%96%B9%E6%B3%95 h_01K3DGA6SK18MHM5FR6ZDR8Y2G=%E5%BA%83%E5%91%8A%E8%B2%BB%E3%81%AE%E9%80%A3%E6%90%BA%E6%96%B9%E6%B3%95 site-id-mapping=%E3%82%B5%E3%82%A4%E3%83%88id%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01K3DGA6SKDTTPY8Q1JBTCTY7H=%E3%82%B5%E3%82%A4%E3%83%88id%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 deleting-cost-integrations=%E5%BA%83%E5%91%8A%E8%B2%BB%E9%80%A3%E6%90%BA%E3%81%AE%E5%89%8A%E9%99%A4 h_01K3DGA6SKF8ZA5M9AW6DA0V3J=%E5%BA%83%E5%91%8A%E8%B2%BB%E9%80%A3%E6%90%BA%E3%81%AE%E5%89%8A%E9%99%A4 disabling-cost-api=%E5%BA%83%E5%91%8A%E8%B2%BBapi%E3%81%AE%E7%84%A1%E5%8A%B9%E5%8C%96 h_01K3DGA6SK93AZ8MNMS0VB87YK=%E5%BA%83%E5%91%8A%E8%B2%BBapi%E3%81%AE%E7%84%A1%E5%8A%B9%E5%8C%96 cost-api-status=%E5%BA%83%E5%91%8A%E8%B2%BBapi%E3%81%AE%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9 h_01K3DGA6SKCZYP5AX29PW7JQ1T=%E5%BA%83%E5%91%8A%E8%B2%BBapi%E3%81%AE%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9 account-level-cost-configuration-supporting-media-sources=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E5%8D%98%E4%BD%8D%E3%81%AE%E5%BA%83%E5%91%8A%E8%B2%BB%E8%A8%AD%E5%AE%9A%E3%81%AB%E5%AF%BE%E5%BF%9C%E3%81%99%E3%82%8B%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9 h_01KQ7V7Q6M2SZX4KWNEM1MQEJV=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E5%8D%98%E4%BD%8D%E3%81%AE%E5%BA%83%E5%91%8A%E8%B2%BB%E8%A8%AD%E5%AE%9A%E3%81%AB%E5%AF%BE%E5%BF%9C%E3%81%99%E3%82%8B%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9 specification-and-limitation=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01K3DGA6SKVZ347ZDY599S0Y7Y=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
