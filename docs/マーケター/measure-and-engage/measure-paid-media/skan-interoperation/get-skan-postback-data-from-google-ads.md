---
title: Google AdsとのSKAN連携
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-28T19:34:39Z'
  edited_at: '2026-10-29T04:33:46Z'
  id: 4403215779857
  locale: ja
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/ja/articles/4403215779857
---
> **概要：** GoogleからAppsFlyerへ、iOSアプリのSKAdNetwork（SKAN）ポストバックの内容を共有するように設定します。

## Google AdsとのSKAN連携

複数のアドネットワークパートナーと連携する場合は、AppsFlyerで設定することをおすすめします。これにより、AppsFlyer上で、すべてのアドネットワークパートナーのSKANパフォーマンス指標をコストなどの指標とあわせて確認できます。

**Google AdsのSKANレポートの対象範囲**

* Google Adsは、iOSアプリキャンペーンで受信したiOSのSKANポストバックを集計し、AppsFlyerと共有します。これらのポストバックには、ディスプレイ、YouTube、検索など、複数のチャネルからのインストールが含まれます。
* AppsFlyerはポストバックをデコードし、SKANダッシュボードとレポート（ポストバックのローデータレポートを含む）を更新します。
* <Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#ios-145-srn-attribution">iOS 14.5がSRNのレポートに与える影響</Anchor>

**考慮事項**：

GoogleはiOSのポストバックを受信すると、広告配信シグナルを使用してラストクリックの時刻を判定します。一方、AppsFlyerはこのクリック時刻をインストール時刻として扱います。このため、AppsFlyerとGoogleの管理画面でデータに差異が生じることがあります。

Googleのクリックのレポート方式と、過去のデータを日次で更新する仕組みに対応するため、AppsFlyerは過去45日分のデータを取得します。インストールは、インストール前のラストクリックの日付に紐づけて表示されます。 たとえば、7月1日のクリックが8月15日までにAppsFlyerへレポートされることがあります。AppsFlyerでは、このインストールをGoogleがレポートしたクリックの日付に紐づけて表示します。この仕組みは、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#reporting-options">レポート</Anchor>に次のように影響します。

* 集計レポートとダッシュボードでは、過去のデータが更新されます。
* <Anchor target="_blank" href="/marketers/ja/docs/skan-raw-data-reports">ローデータレポート</Anchor>では、過去のデータは更新されません。Data Lockerで提供されるデータは、GoogleからAppsFlyerにデータが提供された日付（データ受信日）に対応するフォルダに格納されます。

## 連携の設定

Google Adsとの連携を設定するには、以下の各タブの手順を行ってください。

<Accordion title="ポストバックの設定">

**ポストバックの送信を設定するには、次の手順を行います。**

| ステップ | 作業 | 詳細 |
| --- | --- | --- |
| 1 | SKAN設定の確認 | AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKANソリューション</Anchor>の設定が完了し、有効になっていることを確認します。これにより、AppsFlyer SDKからSKAN APIを呼び出し、コンバージョン値を設定できるようになります。<br /><br />**SKAN設定を確認するには、次の手順を行います。**<ol><li>AppsFlyerで、［**設定**］>［**SKAN Conversion Studio**］に移動します。</li><li>オプション（⋮）をクリックし、［**SKAN計測**］がオンになっていることを確認します。<br />![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)</li><li>使用する計測モードを選択します。<br />詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>を参照してください。</li><li>設定したイベント名を、表記を変えずに正確に控えておきます。次のステップで使用します。**注意**：イベント名では大文字と小文字が区別されます。</li></ol> |
| 2 | AppsFlyerでのアプリ内イベントのマッピング | **アプリ内イベントのマッピングを確認・設定するには、次の手順を行います。**<ol><li>AppsFlyerで、［**コラボレーション**］>［**アクティブな連携**］に移動します。</li><li>［**Google Ads**］を選択します。</li><li>［**連携**］タブで、［**パートナーを有効にする**］がオンになっていることを確認します。オフの場合は、先に<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers">Google Adsとの連携</Anchor>を完了してください。</li><li>［**アプリ内イベントポストバック**］セクションで、次の設定を行います。<ol><li>［**アプリ内イベントポストバック**］がオフの場合は、オンにします。</li><li>現在選択している計測タイプに関連するイベントをマッピングすることをおすすめします。注意：収益を計測する場合は、af\_skad\_revenueをGoogleの適切な収益イベントにマッピングします。</li></ol></li><li>ページの一番下までスクロールします。</li><li>［**連携を保存**］をクリックします。</li></ol> |

</Accordion>

<Accordion title="Google AdsからAppsFlyerへのSKANデータの共有を許可">

Google AdsにアトリビューションされたSKANインストールをAppsFlyerのSKANダッシュボードに表示するには、Google AdsからAppsFlyerへのSKANデータの共有を許可する必要があります。

**Google AdsからAppsFlyerへのSKANデータの共有を許可するには、次の手順を行います。**

1. 以下の手順は、広告主が行う必要があります。代理店を利用する場合は、代理店と広告主の両方でSKAN計測を有効にする必要があります。
2. AppsFlyerで、［**コラボレーション**］>［**アクティブな連携**］に移動します。
3. ［**Google Ads**］を検索して選択します。
4. ［**SKAN**］タブに移動します。<Image alt="mceclip0.png" src="https://files.readme.io/ba8d881ca8430bfdcf67a37e862ad3e31a9af522f2f877d3fba30bc2e13006a6-4404428381457.png" width="309px" />
5. ［**一時的に利用できません（Temporarily unavailable）**］というメッセージが表示される場合は、多くの場合、広告ブロッカーが有効になっています。その場合は、広告ブロッカーを無効にしてページを再読み込みしてください。広告ブロッカーが原因でない場合は、AppsFlyerサポートにお問い合わせください。![mceclip1.png](https://files.readme.io/e86b868f71e11ad347ff7557a793090d9d6adb8fe4df4f9010c8d770b373ac6a-4404428420497.png)
6. ［**Google Ads**に**接続**］をクリックします。
   * Google Adsアカウントの管理者権限を持つユーザーでログインする必要があります。
   * Googleアカウントに複数のアプリが紐づいている場合は、1回ログインするだけで、すべてのアプリが承認されます。アプリごとに承認する必要はありません。
   * AppsFlyerは、各アプリの［パートナーを有効にする］の設定にかかわらず、そのGoogleアカウントに紐づくAppsFlyer上のすべてのiOSアプリのデータを取得します。
7. 画面の指示に従って操作します。
8. AppsFlyerに<strong>［AdWordsキャンペーンの管理（Manage your AdWords campaigns）］権限を付与するよう求められる場合があります。</strong> その場合は、この権限を許可する必要があります。AppsFlyerがお客様のキャンペーン設定を変更することはありません。[<Image alt="GoogleManageAdWords.png" src="https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png" width="182px" />](https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png)
9. アカウントのステータスに［**同期待ち（Waiting for sync）**］と表示されることを確認します。  
   このメッセージは、AppsFlyerがGoogle Adsからデータを受信するまで表示されます（最大24時間）。
10. 翌日の02:00 UTCを過ぎてから、ステータスが［**有効（Active）**］に変わったことを確認します。  
    SKANダッシュボードのデータは、毎日08:00 UTCまでに更新されます。**注意**：「考慮事項」で説明したとおり、Googleは最大45日前までさかのぼってデータを更新することがあります。
11. [計測の差異](/docs/get-skan-postback-data-from-google-ads#measurement-and-timing-differences-between-appsflyer-and-google-ads)についても確認してください。

</Accordion>

## 補足情報

<Accordion title="SKAN連携の解除">

Google Adsとの連携を解除する際は、［**パートナーを有効にする**］をオフにするだけではSKANデータの記録は停止しません。SKANの接続も別途削除する必要があります。

**SKAN連携を解除するには、次の手順を行います。**

1. AppsFlyerで、［**コラボレーション**］>［**アクティブな連携**］に移動します。
2. Google Adsを検索して選択します。
3. ［**SKAN**］タブに移動します。
4. 接続を解除するアカウントの削除アイコンをクリックします。

</Accordion>

<Accordion title="AppsFlyerとGoogle Adsの計測方法・タイミングの違い">

| 項目 | 詳細 |
| --- | --- |
| 取得できるデータの開始日 | 連携を有効にした日付（UTC基準）以降のデータを取得できます。ただし、Googleはクリック時刻を使用するため、連携を有効にした日より前のインストールが、後から表示されることがあります。 |
| インストール日 | Googleは、インストール前のラストクリックの推定時刻をインストール時刻として設定します。このクリック時刻は、Googleが広告配信シグナルを使用して判定します。<br /><br />メディアソースのデータとAppsFlyerのダッシュボードを比較する際は、次の点に注意してください。<ul><li>AppsFlyerは、アプリのタイムゾーンもGoogle Adsの広告アカウントのタイムゾーンも考慮しません。</li><li>Googleでは、インストール日から45日後まで、そのインストールがさかのぼってレポートされることがあります。</li><li>他のメディアソースについては、AppsFlyerがポストバックの受信時刻からインストール時刻を算出します。</li></ul> |
| インストール | Google Ads API V10以降では、AppsFlyerに表示されるインストールは、did\_win=TRUEのポストバックに基づくもののみです。このため、AppsFlyerのインストール数がGoogle Adsの管理画面より少なくなることがあります。 |

</Accordion>

<Accordion title="トラブルシューティングとよくある質問">

| 項目 | 詳細 |
| --- | --- |
| Google Adsへのイベント送信 | **Q**：コンバージョン値の計測対象として選択していないイベントについても、Google Adsへ追加でポストバックを送信する意味はありますか？<br /><br />**A**：同意を得ているユーザーについては、Google Adsによる最適化の効果を最大限に引き出すため、すべてのイベントを送信してください。 |
| 複数のイベントを同じGoogle Adsイベントにマッピング | **Q**：複数のアプリ内イベントを1つのGoogle Adsイベントにマッピングできますか？<br /><br />**A**：複数のイベントを1つのGoogle Ads標準イベントにマッピングすると、Google Adsはそれらのイベントを区別できません。そのため、Google Adsが認識する1つのイベントに対して最適化が行われます。 |
| 対応しているキャンペーンタイプ | **Q：** どのタイプのGoogle Adsキャンペーンに対応していますか？<br /><br />**A**：検索や動画など、Webからアプリ、またはアプリからアプリへ誘導するiOSキャンペーンに対応しています。 |
| 取得できるデータがない場合 | **Q：** 接続ステータスに「取得できるデータがありません：Googleのデータ共有権限を確認してください」と表示されるのはなぜですか？<br /><br />**A**：SKANデータがまだ存在しないか、Google Adsアカウントの管理者権限を持つユーザーでログインする必要があります。 |

</Accordion>

<Accordion title="仕様と制限事項">

| 仕様 | 説明 |
| --- | --- |
| エンゲージビュー | エンゲージビューはクリックとしてカウントされ、他のクリックスルーアトリビューションと同様にポストバックが送信されます。 |
| データの更新タイミング | <ul><li>AppsFlyerは、毎日01:00 UTCからGoogle AdsのSKANデータを収集します。</li><li>ダッシュボードと集計データは、その7時間後に更新されます。</li><li>Google側のSKANデータ処理が遅れることがあるため、通常よりデータの到着が遅れ、SSOT（Single Source of Truth）のデータにも影響する場合があります。<ul><li>遅れていたデータがGoogleから届くと、過去のデータが更新されます。</li></ul></li></ul> |
| 利用可能なレポート | Google Adsのデータは、SKANダッシュボード、集計レポート、ローデータレポートで確認できます。<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#reporting-options">SKANレポートの種類</Anchor>を参照してください。 |
| 代理店 | 代理店が広告主のGoogle Adsアカウントの管理者権限を持っている場合は、この記事の手順を実行し、広告主に代わってGoogleとのSKAN連携を有効にできます。広告主が別途Google Adsにログインする必要はありません。広告主のアカウントには、代理店がログインしていることが表示されます。 |

</Accordion>

<Accordion title="Google AdsのSKANインストールが表示されない場合">

次のチェックリストで設定を確認し、AppsFlyerのSKANダッシュボードでデータを受信できる状態になっているかを確認してください。

**設定確認のチェックリスト**

1. 連携のステータスを確認します。
   * AppsFlyerでGoogle Adsとの連携が有効になっていることを確認します。
   * ［**SKAN**］タブで、ステータスが［**有効（Active）**］になっていることを確認します。［**一時的に利用できません（Temporarily unavailable）**］と表示される場合は、広告ブロッカーを無効にし、ページを再読み込みしてください。
2. Google Adsへの接続がまだ承認されていない場合は、承認します。
   * ［**Google Adsに接続**］をクリックします。
   * Google Adsの管理者アカウントでログインし、AdWordsキャンペーンの管理権限を求められた場合は許可します。
3. 同期が完了するまで待ちます。
   * ログイン後、ステータスは［**同期待ち（Waiting for sync）**］になります。
   * AppsFlyerがGoogleからSKANデータを受信し始めると、ステータスが［**有効（Active）**］に変わります。これには最大24時間かかる場合があります。
   * その後、SKANダッシュボードのデータは毎日08:00 UTCまでに更新されます。

**それでも表示されない場合**

上記の手順を行ってもインストールが表示されない場合は、次の点を確認してください。

* ステータスに「取得できるデータがありません：Googleのデータ共有権限を確認してください」と表示される場合は、GoogleからSKANデータがまだ共有されていないか、Google Adsアカウントの管理者権限を持つユーザーでログインする必要があります。
* Google AdsでSKAN専用キャンペーンを配信しており、管理者アカウントでログインしていることを確認します。
* Google Adsでインストール数を直接確認します。

  1. Google Adsで［**キャンペーン**］に移動します。
  2. ［**レポート（Reports）**］アイコン >［**目標とコンバージョン（Goals and conversions）**］>［**SKAdNetworkコンバージョン（SKAdNetwork conversions）**］をクリックします。
  3. 「レポートの読み込みエラー：このレポートは現在の表示フィルタと互換性がありません（Error loading report — This report is incompatible with the current view filters）」と表示される場合は、［**表示フィルタをクリア（Clear view filters）**］をクリックします。
  4. 列の検索（虫眼鏡アイコン）を使用して、［**SKAdNetwork conv. value segment**］などのSKAN専用の列を探して追加します。

  Google側でインストールが記録されていなければ、AppsFlyerにも表示されません。インストールが記録されない理由については、Googleの担当者に確認してください。

**補足事項**

* Google AdsのSKANデータは、毎日01:00 UTCから収集されます。Googleからのデータの到着に、通常より最大2日多くかかる場合があります。
* SKAN計測の対象となるのは、Webからアプリ、またはアプリからアプリへ誘導するiOSキャンペーンのみです。

</Accordion>

> 📄 **関連記事**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">AppsFlyerのSKANソリューションガイド</Anchor>

<div data-zendesk-anchors="get-skan-postback-data-from-google-ads=google-ads%E3%81%A8%E3%81%AEskan%E9%80%A3%E6%90%BA h_01HCHYGCVJA3C8WJS8JH7BG0CD=google-ads%E3%81%A8%E3%81%AEskan%E9%80%A3%E6%90%BA set-up-interoperation=%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HCHYGCVJY5KT4J6RQS0BJ90G=%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HCHYGCVJTS53PCGK21BEZB2T=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HE7RMSECNDW9VD9XY6H01H55=%E9%96%A2%E9%80%A3%E8%A8%98%E4%BA%8B" />
