---
title: リターゲティング計測ガイド
metadata:
  keywords:
    - Attribution
    - Re-targeting
    - retargeting
    - Advertisers
    - reatribution
    - re-atribution
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-30T13:18:26Z'
  edited_at: '2026-10-14T09:35:16Z'
  id: 207033786
  locale: ja
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/ja/articles/207033786
---
> **概要：** リターゲティング（リマーケティング）キャンペーンでは、ユーザーにアプリを起動させ再度エンゲージすることを促したり、アプリをアンインストールしたユーザーに再インストールを促すことができます。

## リターゲティングの基本

リターゲティングのアトリビューションは、ユーザーが[リターゲティングの計測リンク](/docs/retargeting-attribution-guide#retargeting-attribution-links)をクリックして、または<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">ディープリンク</Anchor>でリターゲティングキャペーンと接触した際に発生します。これは、次のいずれかのアトリビューションイベントとして計測されます：

* **リエンゲージメントCV：** デバイスにアプリがインストール済みで、ユーザーにアプリ起動を促すメディアソースにリエンゲージメントCVの成果が紐づきます。
* **リアトリビューションCV：別名リターゲティングインストール：** ユーザーがアプリをアンインストールしたが、リターゲティングキャンペーンに接触してアプリを再インストールします。これが<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>中に実行された場合：リターゲティングメディアソースには「リアトリビューションCV」の成果が紐づきます。関連記事：<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#reinstalls">再インストール</Anchor>

![](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

リターゲティングキャンペーンを開始する前に、次のセクションでリエンゲージメントCVのルールと使用例を確認してください。その後、リターゲティングの手順セクションに従って、リターゲティングを設定してください。より良く理解するために、AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">計測モデル</Anchor>と関連する計測期間についてもご確認ください。

> 👍 **ヒント**
>
> リターゲティングについてもっと知りたいですか？クイックに重要なポイントを押さえた<Anchor target="_blank" href="https://elevate.appsflyer.com/pages/142/remarketing">AppsFlyerラーニングポータルコース</Anchor>をご活用ください。

<div id="reengagement-rules-and-windows" />

<Accordion title="リエンゲージメントCVのルールと期間">

* リターゲティング計測ルールは、イベントがリターゲティングイベントでありリターゲティングのメディアソースに成果が紐づくかを決定します。
* 新規インストールキャンペーンと同様に、SRN（サーバー連携媒体）のリターゲティングのリエンゲージメントCVはAPIによってレポートされ、非SRN（通常連携媒体 / アドネットワーク）の場合は計測リンクに基づいて計測されます。
* ユーザージャーニーに基づいたルールは次のように構成されます：
  * [計測期間](/docs/retargeting-attribution-guide#計測期間)：リエンゲージメントCVが発生しうる期間。
  * [除外期間](/docs/retargeting-attribution-guide#計測除外設定)：リエンゲージメントCVを計測しない期間。
* リエンゲージメントCVが計測されると、リエンゲージメント期間中に発生したアプリ内イベントは<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">重複計上</Anchor>されます。つまり、これはリターゲティングメディアソースと元のユーザー獲得メディアソース（既知の場合）の両方に成果が紐づきます。

次の図は一連のリエンゲージメントCVの計測ルールを示しています。リターゲティングキャンペーンとの接触が、リエンゲージメントCVと計測されるかどうかを判断するためにご利用ください。

**リエンゲージメントCVの計測ルール**

![](https://files.readme.io/e6643112f3e9969242c0dd394f6401406fbc837a9494cc4bb3825cff6365f36d-33563511578513.png)**参照：計測期間と除外期間**

次の表には、リターゲティング計測に関連する計測期間についての参照情報を示しています。

#### 計測期間

| 期間のタイプ | 説明 |
| --- | --- |
| ビュースルー | ユーザーが広告を閲覧してからアプリを開くまでの最大期間。<br /><br />**設定されている場合：** 計測リンク<br /><br />**期間**：<ul><li>デフォルト：1日</li><li>範囲：1-23時間 / 1-7日</li></ul> |
| クリックルックバック | ユーザーが広告をクリックしてからアプリを開くまでの最大期間。<br /><br />**設定されている場合：** 計測リンク<br /><br />**期間：**<ul><li>デフォルト：7日</li><li>範囲：1-23時間 / 1-30日</li></ul>**SRNに関する備考：** 各SRNに固有のルックバック期間におけるポリシーをご確認ください。 |
| リエンゲージメントCV | リエンゲージメント期間において、次のことを考慮してください：<ul><li>期間は、ユーザーがリターゲティングメディアソースとエンゲージメント後、アプリを初回起動した時点から開始されます。</li><li>アプリ内イベントは、リエンゲージメント期間中、リターゲティングとユーザー獲得メディアソースの両方に<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">重複計上</Anchor>されます。</li><li>期間はアプリ設定に基づき、またはSRNによって決定されます。</li><li>リエンゲージメント期間中にユーザーが別のリターゲティングキャンペーンとエンゲージし、除外期間によってブロックされていない場合、元のリエンゲージメント期間はその時点で終了し、新しいリエンゲージメント期間が開始します。</li><li>リアトリビューションCVのコンテキスト：**アトリビューション期間** 期間は無制限です （インストールと同様）。ただし、このウィンドウは、新規インストール、再インストールの場合、またはデータ保持期間の制限により終了します。</li></ul>**設定場所：** 計測リンク<ul><li>デフォルト：30日間</li><li>範囲：範囲：1&#126;23時間／1&#126;90日間／ライフタイム</li></ul>**SRNに関する備考：** SRN向けに設定可能<br /><br />期間設定を変更した場合、変更は変更後のリエンゲージメントCVのみに影響します。既存のリエンゲージメントCVには影響しません。 |

#### 計測除外設定

| 期間のタイプ | 説明 |
| --- | --- |
| リエンゲージメントコンバージョン間の期間設定 | 除外期間中は同一端末からのリエンゲージメントCVを2回以上計測しません。<br /><br />**リエンゲージメントコンバージョン間の期間設定**<ul><li>リエンゲージメントCVを計測すると、その後のアプリ内イベントをリターゲティング広告（primary: メインの紐付け先）と新規インストール広告（non-primary: メインの紐付け先ではない）の両方に紐付ける、リエンゲージメント期間というものが適用され始めます。</li><li>これにより、リターゲティング広告のパフォーマンスを計測できるようになります。</li><li>この期間中に別のネットワークまたはキャンペーンがリエンゲージメントCVをもたらした場合：<ul><li>［デフォルト］既存のリエンゲージメント期間が閉じられるとともに新しく別のリエンゲージメントが1件記録され、その後に発生したアプリ内イベントは新しい方のリエンゲージメントに紐付けられるようになります。</li><li>これを防ぐには、リエンゲージメントCV再計測までの最短時間を設定してください。この期間を設定すると、設定期間を経過したあとにのみ、新しいリエンゲージメントCVが計測されるようになります。</li></ul></li><li>ただし、この設定はリエンゲージメント期間がこちらの設定期間よりも短い場合には適用されないので注意してください。例：リエンゲージメント期間が1日、こちらの最低期間が4日でそれぞれ設定されている場合、最短期間の設定は適用されません。</li><li>この設定は、初回インストールとリエンゲージメントの間の計測期間を設定するものではありません。</li></ul>**設定場所：** アプリ設定画面<br /><br />**期間**：<ul><li>デフォルト：なし</li><li>範囲：1-23時間 / 1-30日</li></ul> |
| <Anchor target="_blank" href="/marketers/ja/docs/set-retargeting-inactivity-window">休眠期間</Anchor> | 設定された休眠期間中に一度でもアプリ起動したユーザーのリエンゲージメントCVまたはリアトリビューションCVを記録しません。<br /><br />**設定場所：** 連携済みパートナー画面<br /><br />**期間**：<ul><li>デフォルト：なし</li><li>0&#126;30日間</li></ul>**SRNに関する備考：** SRNは通常、独自の休眠期間ルールを持っていると考えてください。SRN側の管理画面設定と異なる場合は、不一致が生じる可能性があります。 |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューションCV</Anchor> | リアトリビューション期間は、リアトリビューションCV（リタゲ経由の再インストール）のみに影響し、リエンゲージメントCV（既存ユーザーがリタゲ経由でアプリを起動）には影響しません。<br /><br />リターゲティングキャンペーンと接触後、リアトリビューション期間中にリインストールしたユーザーは、リターゲティンメディアソースの成果として紐づきます。関連記事：<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#reinstalls">再インストール</Anchor><br /><br />**設定場所：** アプリ設定 |

#### **ルールが適用されるフローの例**

![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)

クリックスルーとビュースルー計測のリエンゲージメントルールのチェックリスト：

| ルール | ルール |
| --- | --- |
| A | ユーザーがリターゲティング広告として設定された広告を閲覧またはクリックすることで、リターゲティングキャンペーンとエンゲージ（接触）します。 |
| B | このエンゲージメントはクリックルックバック、またはビュースルー**期間中**に発生しました。 |
| C | このユーザーは設定された休眠期間よりも長い期間、アプリを使用（起動）していません。 |
| D | アプリ内イベントが、リエンゲージメント期間中に発生しました。 |
| E | 前回と今回のリエンゲージメント間の期間は、リエンゲージメントCV再計測までの最短時間を超えています。 |

</Accordion>

<div id="example-retargeting-scenarios" />

<Accordion title="リターゲティングシナリオの例">

| **シナリオ１：リエンゲージメント期間前、期間中、期間後の購入**<br /><br />ユーザージャーニー：<ul><li>ネットワークZの広告と接触した後、アプリをインストールし、購入 (A) を実行します。</li><li>ネットワークＹのリターゲティング広告と接触した後、アプリを起動し、購入 (B) を実行します。</li><li>購入 (C) を実行します。</li></ul>![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)<br /><br />P/S列：<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">リターゲティングイベントの重複計測</Anchor>で説明しているプライマリ (P)、またはセカンダリ (S)を示します。 |
| --- |
| **シナリオ2：リエンゲージメント期間内の複数のコンバージョン**<br /><br />ユーザージャーニー：<ul><li>ネットワークZの広告と接触した後、アプリをインストールし、購入 (A) を実行します。</li><li>ネットワークＹのリターゲティング広告と接触した後、アプリを起動し、購入 (B) を実行します。</li><li>購入 (C) を実行します。</li></ul>![](https://files.readme.io/bf57f8a9597bd56a89bb3f1be3700195e1b153b548cb11ee3d37c65d5382e711-33563474530321.png)<br /><br />P/S列：<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">リターゲティングイベントの重複計測</Anchor>で説明しているプライマリ (P)、またはセカンダリ (S)を示します。 |

</Accordion>

## リターゲティングの運用

<div id="retargeting-settings" />

<Accordion title="リターゲティング設定">

シナリオによっては、次の設定が必須です。

| コンバージョンタイプ | SRN | 非SRN |
| --- | --- | --- |
| リエンゲージメントCV | <ol><li>AppsFlyer管理画面左メニュー **設定** > **アプリ設定**へ移動します。</li><li>リエンゲージメントCV計測がオンになっていることを確認してください。</li><li>SRNごと：</li><li>AppsFlyer管理画面左メニュー **連携** > **連携済みパートナー**を選択し、SRNを選択します。</li><li>**リエンゲージメントCVの計測**トグルをオンにしてください。</li></ol> | <ol><li>AppsFlyer管理画面左メニュー **設定** > **アプリ設定**へ移動します。</li><li>リエンゲージメントCV計測がオンになっていることを確認してください。</li><li>非SRNごと：このセクションの手順に従って、リターゲティングパラメーターを計測リンクに追加してください。</li></ol> |
| リアトリビューションCV | <ol><li>AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**へ移動します。</li><li>**再インストール計測**を有効にします。</li></ol> | <ol><li>明示的な設定は必要ありません。</li><li>このセクションの手順に従って、リターゲティングパラメーターを計測リンクに追加してください。</li></ol> |

#### **SRN以外の設定**

**アドネットワーク（非SRN）のリターゲティングを設定する方法**：

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**へ移動します。
2. アドネットワークを選択します。
3. **リターゲティング設定**を**有効化**します。これにより、下のセクションにある計測リンクに `is_retargeting=true` が追加され、計測リンクがリターゲティングURLに変更されます。   

   [![](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)
4. 次のいずれかから選択します：
   * 一つのプラットフォーム（アプリ固有）のリンクは**通常の計測リンクを使用**します。
   * **OneLinkを使用**します。
     * 必要に応じて、**ディープリンクURL**を入力してください（詳細は<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">ディープリンクガイド</Anchor>を参照）。
5. 生成されたURLをコピーし、リターゲティングキャンペーンで使用するようアドネットワークに入稿します。  
   　**注：** URLはプラットフォーム上で保持されず、保存できません。

</Accordion>

<div id="retargeting-dashboard" />

<Accordion title="リターゲティングレポート">

マイダッシュボードには、新規インストールのデータだけでなく、リターゲティングのデータも含まれています。この指標はLTVベースで、リターゲティングキャンペーンに接触したユーザーに紐づいています。

**リターゲティングデータを見るには：**

1. サイドメニューから、**マイダッシュボード**へ移動します。
2. **表示タイプ**をクリックし、**リターゲティング**を選択してください。  
   リターゲティングデータが表示されます。  
   　**注：** リターゲティングデータは統合ビューでも見ることができます。ダッシュボードの表示タイプを参照してください。

</Accordion>

<div id="retargeting-attribution-links" />

<Accordion title="リターゲティング計測リンク">

* リターゲティングの計測URLは、通常のユーザー獲得のURLに似ています。
* 次の用途で作成してください：
  * リターゲティング計測をサポートしている非SRNのメディアソース
  * <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">OneLink</Anchor>を使用するオウンドメディア

リターゲティング計測リンクパラメーター

| パラメータ | 説明 | 必須 |
| --- | --- | --- |
| `is_retargeting` | 設定：`is_retargeting=true` | はい |
| Advertising ID | 可能な場合、IDFA、OAID、IDFVなどの広告IDを送信してください。<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#probabilistic-modeling">iOSアプリの確率論的モデリングの制限</Anchor> | いいえ |
| リターゲティングのクリック ルックバック期間 | <ul><li>リターゲティングの<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">クリックルックバック期間</Anchor>は、ユーザー獲得キャンペーンと同様の仕組みで機能します。</li><li>これは、ユーザーが広告をクリックしてから、ユーザーが計測されるまで経過できる最大期間を定義します。</li><li>ルックバック期間は、 `&af_click_lookback` パラメータを使用して設定されます。</li><li>デフォルト設定は7日間です。</li></ul>**<span id="01ECF12NKTFH6Q2NH4B1WKSYF9"></span>例**<br />クリックルックバック期間を14日間で設定するには、リターゲティングキャンペーンの計測URLに次のパラメータを追加してください：`&af_click_lookback=14d` | いいえ |
| リターゲティングのビュースルールックバック期間 | <ul><li>リターゲティングの<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">ビュースルーのルックバック期間</Anchor>は、ユーザー獲得キャンペーンと同様の仕組みで機能します。</li><li>これは、ユーザーが広告を閲覧してから、リターゲティングCVが計測されるまでの最大期間を定義します。</li><li>デフォルトは1日です。</li><li>ルックバック期間は次を使用して設定されます：</li></ul>`af_viewthrough_lookback={time}`<br /><br /><br /><br />**<span id="01ECF12NKTE8W4K72VATN9RM2X"></span>例**<br />ビュースルーのルックバック期間を5時間で設定するには、リターゲティングキャンペーンの計測URLに次のパラメータを追加してください：`&af_viewthrough_lookback=5h` | いいえ |
| Re-engagement window | <ul><li>**リエンゲージメント期間**は計測リンクの計測リンクで設定できます。これは、計測リンク上の **af\_reengagement\_window** パラメーターを設定します。このパラメーターは手動で追加することもできます。</li><li>デフォルトは30日です。</li><li>以下のリエンゲージメント期間の値が使用可能です：</li><li>時間：1&#126;23時間</li><li>日数：1-90日</li><li>ライフタイム：ユーザーがアプリをアンインストールするか、別のリエンゲージメントを発火するまで持続します。（例：af\_reengagement\_window=lifetime）</li></ul>例えば、 **af\_reengagement\_window=60d** は、リエンゲージメントから60日以内に発生したイベントがリターゲティング媒体の成果に紐づきます。 | いいえ |

#### リターゲティングビュースルールックバック期間

```http
https://app.appsflyer.com/id123456789?pid=remerge_int&af_dp=mydeeplink%3A%2F%2F&
clickid={clickid}&af_siteid={publisher}&idfa={device_id_raw}&sha1_idfa={device_id}
&af_sub1={creative_name}&is_retargeting=true&af_reengagement_window=60d
```

</Accordion>

<div id="retargeting-reports-and-raw-data" />

<Accordion title="リターゲティングレポートとローデータ">

* リターゲティングレポートは、新規獲得の<Anchor target="_blank" href="/marketers/ja/docs/aggregated-and-analytics-reporting-overview">集計</Anchor>データと<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ローデータ</Anchor>レポートと同様、レポーティングツールを使用して利用できます。
* リターゲティングのアプリ内イベントとセッションは、<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">重複計測</Anchor>されます。

**リターゲティングコンバージョンのレポート**

* リターゲティングコンバージョンのレポートには、リエンゲージメントCVとリアトリビューションCVのローデータが含まれています。
* 一部のリターゲティングレポートのデータ項目は、ユーザー獲得のレポートで使用されるものとは意味が異なる点に注意してください。

リターゲティングのコンテキストにおけるローデータレポートの解釈

| 項目 | **説明** |
| --- | --- |
| Event name | <ul><li>カラムの内容はレポートタイプによって異なります。</li><li>アプリ内イベントレポート：アプリ内イベント名</li><li>リターゲティングコンバージョンレポート：リエンゲージメントCVまたはリアトリビューションCV。<strong>注意！</strong>Data Lockerの場合、値は次のとおりです：<ul><li>インストールはリアトリビューションCVを指します</li><li>リターゲティングはリエンゲージメントCVを指します</li></ul></li></ul> |
| Attributed touch typ | エンゲージメントタイプ：<ul><li>Click</li><li>Impression</li></ul> |
| Attributed touch time | リターゲティング広告との接触時間 |
| Install time | リエンゲージメントCV、もしくはリアトリビューションCVが計測された時間 |
| Event time | イベントが発生した時刻 |
| AppsFlyer ID | <ul><li>リアトリビューションCV：新しいAppsFlyer IDが採番されます</li><li>Re-engagement：変更なし</li></ul> |
| Is retargeting | リターゲティングコンバージョン / イベントレポート：TRUE |
| Is primary attribution | リターゲティングコンバージョン / イベントレポート：TRUE |
| Retargeting conversion type | <ul><li>Re-engagement</li><li>Re-attribution</li></ul> |
| Conversion type | コンバージョンタイプ：<ul><li>Install</li><li>Reinstall (1)</li><li>Re-engagement</li><li>Unknown (2)</li></ul>(1) conversion\_type= reinstall で campaign\_type=retargeting である場合、retargeting\_conversion\_type=re-attribution と同等です。<br /><br />(2) メディアソースに紐づかないアプリ内イベント / セッション |
| Campaign type | ユーザーをもたらしたソース：<ul><li>UA（非オーガニックインストール）</li><li>Organic</li><li>Retargeting</li><li>Unknown</li></ul> |
| Attribution Lookback | リターゲティングのクリックルックバック期間 |
| Original URL | 次のいずれかが含まれます：<ul><li>リターゲティングの計測URL</li><li>ディープリンクデータ</li><li>SRN媒体の場合：空欄</li></ul> |
| Contributorの項目 | リエンゲージメントのデータでは利用できません。 |

</Accordion>

## 追加情報

<div id="probabilistic-modeling" />

<Accordion title="確率論的モデリング">

2021年2月17日以降、リターゲティングで確率論的モデリングがサポートされています。<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#note-for-ios-apps">iOS 14.5以降の制限事項</Anchor>が適用されます。リターゲティングの確率論的モデリングで使用されるルックバック期間は、AppsFlyerによって動的に設定され、オペレーティングシステムにより異なります。

送信されたクリックに、必要な<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#probabilistic-modeling-parameters-for-ad-networks">確率論的モデリングパラメータ</Anchor>が含まれていることを確認します。

</Accordion>

<div id="app-requirements" />

<Accordion title="アプリの要件">

リターゲティングキャンペーンを実施するには、アプリが以下の要件を必ず満たしている必要があります。

* iOS
  * 標準のAppsFlyer SDK実装に加えて、app delegate にコードを追加する必要があります。詳細は<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#onelinkによるディープリンク">SDKの実装</Anchor>（計測リンクセクション）を参照してください。
  * iOS 9の場合、ユニバーサルリンクのアプリ起動のコードを実装する必要があります。<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">iOS 9のユニバーサルリンク</Anchor>。
* Android

  * ディープリンクによる起動でメインアクティビティ以外のアクティビティ（特定画面）を開く場合は、<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#deep-linking">SDK実装ガイド</Anchor>（計測リンクのセクション）を参照してください。

</Accordion>

<div id="retargeting-limitations" />

<Accordion title="リターゲティングの制限事項">

* 2021年2月17日以降、リターゲティング計測で確率論的モデリングがサポートされています。
* リターゲティングのキャンペーンコストデータは、統合ビューのオーバービューとコホートのダッシュボードとレポートで利用可能です。

</Accordion>

<div id="faq" />

<Accordion title="よくある質問">

| **リターゲティングのクリック：**<ul><li>リターゲティングのクリックデータには、AppsFlyerの計測リンクを使用してリターゲティングされたユーザーが含まれています。</li><li>SRN媒体または<Anchor target="_blank" href="/marketers/ja/docs/measuring-push-notification-re-engagement-campaigns">プッシュ通知</Anchor>からのクリックはカウントに含まれません。</li><li>一部のクリックは新規インストールに繋がるためユーザー獲得として計測されます。このようなケースは、未インストールユーザー、または<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>の有効期間が切れた後の既存ユーザーが、リターゲティング広告経由でアプリをインストールしたときに発生します。</li></ul> |
| --- |
| **attributed touch time が install timeと同じになるのはどのような場合ですか？**<ul><li>iOSのユニバーサルリンク、またはAndroidのアプリリンクによってユーザーのディープリンクが行われると、AppsFlyerのサーバーは経由せずに直接アプリが起動されます。</li><li>アプリが起動され、SDKが新しいリエンゲージメントを計測すると、AppsFlyerはアプリ起動と同じタイムスタンプを使用してクリックデータを再現します。その結果、広告接触（エンゲージメント）と起動時間が同じになります。</li></ul> |

</Accordion>

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">AppsFlyerの計測モデル</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/audiences-guide">Audiencesガイド</Anchor>

<div data-zendesk-anchors="retargeting-fundamentals=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E5%9F%BA%E6%9C%AC h_01HCFJHC85VK0A05X5F69E2WKT=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E5%9F%BA%E6%9C%AC h_01HCFJHC851PV0VR42H07VQAXF=%E3%83%92%E3%83%B3%E3%83%88 h_01HCFJHC85EW8MBQ8MBXBVPF03=reengagement-rules-and-windows inclusion-windows=%E8%A8%88%E6%B8%AC%E6%9C%9F%E9%96%93 h_01HCFJHC85FRFJ531Y08DW03Y2=%E8%A8%88%E6%B8%AC%E6%9C%9F%E9%96%93 exclusion-windows=%E8%A8%88%E6%B8%AC%E9%99%A4%E5%A4%96%E8%A8%AD%E5%AE%9A h_01HCFJHC85ECS3PJV80D943TVY=%E8%A8%88%E6%B8%AC%E9%99%A4%E5%A4%96%E8%A8%AD%E5%AE%9A example-flow-implementing-the-rules=%E3%83%AB%E3%83%BC%E3%83%AB%E3%81%8C%E9%81%A9%E7%94%A8%E3%81%95%E3%82%8C%E3%82%8B%E3%83%95%E3%83%AD%E3%83%BC%E3%81%AE%E4%BE%8B h_01HCFJHC8529NW0ABMQ0RB3E8R=%E3%83%AB%E3%83%BC%E3%83%AB%E3%81%8C%E9%81%A9%E7%94%A8%E3%81%95%E3%82%8C%E3%82%8B%E3%83%95%E3%83%AD%E3%83%BC%E3%81%AE%E4%BE%8B h_01HCFJHC85E1SWGYN0BH603BV9=example-retargeting-scenarios retargeting-operations=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E9%81%8B%E7%94%A8 h_01HCFJHC863XPHNWRHJ60JPSRF=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AE%E9%81%8B%E7%94%A8 h_01HCFJHC86XNCT5AQP48R9ZDC4=retargeting-settings nonsrn-settings=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HCFJHC865V36R3H58D5PWXYY=srn%E4%BB%A5%E5%A4%96%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HCFJHC860BS9YJM99G437G24=retargeting-dashboard h_01HCFJHC860Y5HZN66DRNN2Q89=retargeting-attribution-links retargeting-viewthrough-lookback-period=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HCFJHC863CSP03AYBXFSNC37=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HCFJHC86MNFRGYMN776FYHJV=retargeting-reports-and-raw-data additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HCFJHC86RKKPPMBYEZV4Q3X9=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HCFJHC8690EN19DDX7P24AD0=probabilistic-modeling h_01HCFJHC862E6C46Q7645VJ6CZ=app-requirements h_01HCFJHC86SMKZ1HT5KHQNQS1N=retargeting-limitations h_01HCFJHC86BVSVRNAGJEKZFCJP=faq h_01HE7TPR7928SF2W8ZJS55Y5BG=%E5%8F%82%E7%85%A7" />
