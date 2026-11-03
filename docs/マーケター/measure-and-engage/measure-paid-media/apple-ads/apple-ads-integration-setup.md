---
title: Apple Ads（検索広告）統合設定
metadata:
  keywords:
    - cost
    - Advertisers
    - apple search ads
    - asa
    - apple ads
    - apple search advanced
    - apple search ads campaign group
    - apple keywords
    - apple searchads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-31T09:04:38Z'
  edited_at: '2026-10-14T09:38:50Z'
  id: 213747963
  locale: ja
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/ja/articles/213747963
---
> **概要：** AppsFlyerのSRN媒体であるApple Search Ads（ASA）は、ユーザーがキーワードを使用してApp Storeでアプリを見つけるのに役立ちます。

<Image alt="apple_search_ads.png" src="https://support.appsflyer.com/hc/article_attachments/51910174096657" width="217px" />

アプリとの関連性は、App Store上での検索クエリに応じて表示される広告があなたの広告であるかどうかを判断します。アプリ広告に対するユーザーの反応が、広告の関連性を判定する要素になります。ASAは、ユーザーの反応をシグナルとしてどの広告を最も多く表示するかを決定します。

> 📘 **注**
>
> * AppsFlyerは、Apple Search Adsのクリックベースのモバイルアトリビューション、ユーザー<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティング</Anchor>、および<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview">コスト</Anchor>データをAPI経由でサポートしています（ROI360のご契約が必要）。
> * 2025年3月27日以降、AppsFlyerはApple Search Adsのインプレッションベースのモバイルアトリビューションも対応しています。

## ASA連携の設定

<div id="get-started" />

<Accordion title="まずはじめに">

**前提条件**

* 最新バージョンのAppsFlyer iOS SDKが実装されていること

**AppsFlyerでのApple Search Ads連携の設定方法：**

設定は **連携済みパートナー**画面から行いますが、新しく連携する場合には、まず <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations">パートナーマーケットプレイス</Anchor>にアクセスする必要があります。以下の手順に従い、各タブの設定を完了してください。

> 📘 **注**
>
> 連携を設定する前に、<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>して広告運用のためのアカウントを開設してください。

</Accordion>

<div id="integration" />

<Accordion title="連携タブ">

SRN媒体であるApple Search Adsは、API経由でAppsFlyerと連携しています。そのため、ポストバック設定はありません。計測ゴールに応じて、次のセクションを完了してください。

<table><thead><tr><th>セクション </th><th>詳細</th></tr></thead><tbody><tr><td>連携の有効化</td><td><p><strong>連携を有効化または編集するには：</strong></p><ol><li> <strong>有効化するには：</strong> AppsFlyer管理画面 左メニュー <strong>連携</strong> &gt; <strong>パートナーマーケットプレイス</strong>へ移動します。<br/><strong>連携を変更するには：</strong>AppsFlyer管理画面 左メニュー <strong>連携</strong> &gt; <strong>連携済みパートナー</strong>へ移動します。</li><li>パートナーを検索し選択してください。</li><li> <strong>連携設定</strong>をクリックします。連携の設定画面に移動します。</li><li> <strong>連携</strong>タブにて連携したいアプリを選択し、 <strong>パートナーを有効にする</strong>をオンにしてください。<br/><strong>注：</strong> パートナーと作業している間、トグルはオン<a href="./partner-activation-deactivation" target="_blank">（有効）</a>のままにしておく必要があります。</li><li>以下の手順に従い、各タブの設定を完了してください。</li></ol></td></tr><tr><td>インストール：クリックスルーアトリビューション</td><td><p>クリックからインストールまでの最大時間を設定してください。これにより、AppsFlyerはASAのルックバック期間内に発生したインストール（初回起動）を計測できるようになります。</p><p>範囲：1-30日<br/><br/>ルックバック期間に関する詳細：<a href="./set-up-lookback-windows" target="_blank">ルックバック期間の説明</a></p></td></tr><tr><td>インストール：ビュースルーアトリビューション</td><td><p>ビュー（インプレッション）からインストールまでの最大時間を設定します。インプレッション経由のインストールのルックバック期間スライダーは、時間単位のみです（最大：24時間 / デフォルト：24時間）。24時間、デフォルト：24時間</p><p>範囲：1-24時間</p><p>ルックバック期間に関する詳細：<a href="./set-up-lookback-windows" target="_blank">ルックバック期間の説明</a></p></td></tr><tr><td rowspan="2">再インストール </td><td><p><strong>再インストール計測</strong></p><p><strong>再インストール</strong>計測が有効になっている場合、AppsFlyer は再インストールの成果をASAに紐づけることができます。</p><p>再インストール計測のルックバック期間の設定は、インストール計測の設定に従って設定されます。</p><p>ユーザーのインストールが <a href="./set-up-re-attribution-window" target="_blank">リアトリビューション期間</a>（初回インストール時に設定）内の場合、そのインストールは再インストールとしてASAに紐付けられます。</p><p>この再インストールのデータは、オーバービューの管理画面のリターゲティングビューで見ることができます。</p><p>また、ローデータ上では <strong>Store reinstall</strong> の項目が true で入力されます。 </p><p>注意：現在、ASAのリターゲティング計測は、「リエンゲージメントCV」の計測はサポートされていません。</p></td></tr><tr><td><p><strong>休眠期間</strong></p><p>ユーザーの<a href="./set-retargeting-inactivity-window" target="_blank">休眠期間</a>（日数）を設定して、リターゲティングキャンペーンの影響を範囲を設定してください。 </p></td></tr><tr><td>Postbacks</td><td>現在、Apple Ads統合はポストバックをサポートしていません。 </td></tr></tbody></table>

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

コスト連携では、以下の集計データを提供します：

* キャンペーン、広告セット、地域／国、キーワードに関するコストデータ。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークコスト連携に関する表</Anchor>を参照してください。  
  **注記：** コストデータの連携にはROI360機能のご契約が必要です。
* クリック、インプレッションに関するデータ、及びキーワードやキャンペーン名、広告セットなどの補足データ。

> 📘 **注意**
>
> * 複数のASAアカウントの使用もサポートしています。つまり、異なるApple Search Adsのアカウントを使って同じアプリの複数キャンペーンを実行している場合でも、全てのアカウントからデータを取得できます。
> * 「キャンペーングループ」のコストデータはASAレポートAPIではサポートされていないため、「キャンペーングループ」データはAppsFlyerでは利用できません。
> * Appleでサインインするには、ASAのアドミンレベルの権限（「アカウントの読み出しのみ」または「アカウントの読み書き」）が必要です。
> * Appledでサインインすると、以前に提供されたAPI証明書はデータの取得を停止します。
> * Appleでサインインすると、ASAキャンペーングループの認証は累積されません。新しいアプリを連携すると、以前のアプリで選択したキャンペーングループの権限は、再度選択しない限り取り消されます。
> * Appleでサインインする場合、<Anchor target="_blank" href="https://support.apple.com/en-il/guide/apple-business-manager/axmb19317543/web">連携ログイン</Anchor>は使用できません。

**コスト、クリック数、インプレッション数、より豊富なデータを有効にする方法：**

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">こちらの連携手順</Anchor>に従ってください。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータスを表示</Anchor>と一致するコストデータを引き出すことができた最後の時刻を、AppsFlyerがコスト（および広告収益）連携ステータス管理画面、または個別のアドネットワーク管理画面のいずれかで確認してください。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">アドネットワークと代理店の権限設定</Anchor>

</Accordion>

## 代理店とASAマーケティングパートナーの設定

<div id="principles" />

<Accordion title="原則">

**Apple Search Ads：マーケティングパートナー vs.代理店：**

広告主と代理店はASAマーケティングパートナーと連携することができます ASAでキャンペーンを報告および最適化するために。

代理店とマーケティングパートナーの違いは 次の表に列挙されています。

#### 代理店とマーケティングパートナー

|  | 代理店 | マーケティングパートナー |
| --- | --- | --- |
| AppsFlyerがポストバックを送信するか | いいえ | はい |
| 機能と役割 | キャンペーンを実施します。 | キャンペーンを最適化するための付加価値テクノロジーソリューションを所有 |

#### 代理店とマーケティングパートナーの設定

次のチェックリストを使用して、すべてのステップを完了してください 設定プロセスで。詳細な指示は 次のセクションのパートナータイプごとに含まれています。

#### 設定ステップのチェックリスト

| 設定担当 | 代理店との連携 | マーケティングパートナーとの連携 |
| --- | --- | --- |
| 広告主 | <ol><li>AppsFlyerのASA統合タブで、 **パートナーを有効にする** をオンにしてください。</li><li>代理店を選択し、代理店の権限で **代理店の権限**をオンにする。</li></ol> | <ol><li>ASA統合タブで、オンにします。 パートナーの有効化</li><li>ASAダッシュボードでマーケティングパートナーの キャンペーングループID</li><li>連携済みパートナー内のマーケティングパートナーの連携画面に入り、連携タブにて：<ol><li>**パートナーを有効にする** をオンにしてください。</li><li>キャンペーングループを設定してください。</li><li>アプリ内イベントポストバックを設定してください。</li></ol></li></ol> |
| 代理店 | ASA統合タブで、設定します。 **Apple Search Adsキャンペーングループ** | <ol><li>ASA統合タブで、オンにします。 パートナーの有効化</li><li>ASAダッシュボードでマーケティングパートナーの キャンペーングループID</li><li>連携済みパートナー内のマーケティングパートナーの連携画面に入り、連携タブにて：<ol><li>**パートナーを有効にする** をオンにしてください。</li><li>キャンペーングループを設定してください。</li><li>アプリ内イベントポストバックを設定してください。</li></ol></li></ol> |

</Accordion>

<div id="marketing-partner-setup" />

<Accordion title="マーケティングパートナーの設定">

**マーケティングパートナーの設定方法：**

1. （必要に応じて）**Apple Search Ads連携**を有効に設定します。
   1. AppsFlyerで、**設定**>に移動します。 **アクティブな統合パートナー** > • Apple Ads
   2. **パートナーを有効にする** をオンにしてください。
   3. **保存**をクリックしてください。
2. **Apple Search Adsのダッシュボード**： GET Apple Search AdsキャンペーングループIDパラメータに関連する マーケティングパートナー次のスクリーンショットをガイドとして使用してください。 IDを特定するために。  ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
3. **AppsFlyerでASAマーケティングパートナーを設定：**
   1. AppsFlyerのサイドメニューから、選択します。 コラボレーション 連携済みパートナー
   2. **Apple Search Ads** ***マーケティングパートナー***を検索してください。  
       マーケティングパートナーの一覧が表示されます。
   3. マーケティングパートナーを選択します。
   4. **パートナーを有効にする** をオンにしてください。
   5. パートナー名を入力 apple-search-ads-campaign-group-id.png 前のステップで取得したもの。数値（数字）のみを入力してください。 only
   6. **保存**をクリックしてください。
4. [任意] アプリ内イベントポストバックの設定：
   1. **アプリ内イベントポストバック**をオンにしてください。
   2. **イベントを追加するにはクリックします** リストに。
   3. 次のパラメーターを入力してください：
      1. **SDKイベント名：** の名前。 AppsFlyerが受け取ったイベント、アプリ内の SDK、またはサーバーから サーバーイベントに。　 / **ヒント：** もしあなたが アプリ内イベント名がリストに表示されない場合は、 デバイスでイベントを有効にすることを確認してください。 非オーガニックインストールを再確認します。
      2. **収益を送信：** のいずれかを選択します。 次の手順を実行します：値なし、収益なし、値 と収益なし、または値と収益。
5. **連携を保存**をクリックします。

</Accordion>

<div id="agency-setup" />

<Accordion title="代理店の設定">

広告主は代理店に代わってキャンペーンを実行することを許可します。 Apple Search Ads。広告主と代理店の両方が、 このセクションで説明されているようにAppsFlyerで設定アクションを実行します。

**前提条件**

AppsFlyerで代理店を設定する前に、代理店と 広告主はASAプラットフォームで次のステップを実行する必要があります。

* **代理店：**
  1. 代理店アカウント内に別々のキャンペーングループを作成します。
  2. 広告主をキャンペーングループマネージャーとして招待するか、 リンクアカウントの役割を通じてアプリストアを接続します。 アカウント接続
* **広告主：** 招待を受け取った後、 広告主はキャンペーングループをリンクする必要があります。 そのアプリストアコネクトアカウントに。

ASAのドキュメントを参照してください。 <Anchor target="_blank" href="https://searchads.apple.com/help/get-started/0012-link-app-store-connect-accounts">クライアントのアプリストアコネクトアカウントを代理店アカウントにリンクする方法</Anchor>

**Apple Search Adsキャンペーングループ**

* 代理店キャンペーンと広告主キャンペーンは、別々のApple Search Ads IDキャンペーングループである必要があります。
* グループ名には、特殊文字とスペース（空白）は使用しないでください。
* Appleでサインインすると、ASAキャンペーングループの承認は 累積されません。これは、新しいアプリを統合すると、 前のアプリのために選択されたキャンペーングループの承認が取り消されることを意味します。 再度選択しない限り。選択する必要があります。 **制限付きアクセス**と関連する各キャンペーン グループ（広告主のために接続したいアプリに関連する）。

#### **広告主側のアクション**

**前提条件：**

<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#代理店の許可">代理店に権限を付与</Anchor>します。

**Apple Search Adsの計測を有効にするには、以下を実施する必要があります：**

1. AppsFlyerのサイドメニューから、選択します。 コラボレーション 連携済みパートナー
2. **Apple Search Ads**を選択します。
3. **統合**タブに移動し、切り替えます。 パートナーの有効化
4. [オプション] アプリを再インストールしたユーザーを帰属させたい場合、 再帰属ウィンドウ中に切り替えます。 **再インストール計測**
5. **保存**をクリックしてください。

#### **代理店が行う設定**

1. **Apple Search Adsのダッシュボード**：今すぐ キャンペーングループID次のスクリーンショットをガイドとして使用してください。 IDを特定するために。数字のみを取得してください。 ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
2. AppsFlyerにてアプリを選択します。
3. サイドメニューから **コラボレーション** > を選択します。 連携済みパートナー
4. **Apple Search Ads**を選択します。
5. **Apple Search AdsキャンペーンID**パラメーターを入力します。 注意！数値のみを入力してください。
6. **保存**をクリックしてください。

> 📘 **注意**
>
> エージェンシーが Apple Search Ads マーケティングパートナーと連携する場合、 エージェンシーは両方の Apple Search Ads 設定ページとマーケティングパートナー 設定ページで同じキャンペーングループ ID を設定する必要があります。

### コスト、クリック、インプレションのデータ

コスト API を有効にすると、AppsFlyer はコスト, クリック、 および API 経由で ASA からのインプレッションデータを受信します。 詳細：アドネットワークのコスト連携表 サポートされている次元、メトリック、および機能の詳細。 　**注：** コストデータの取得にはROI360のご契約が必要です。 ROI360 がない場合、受信するのは クリックとインプレッションデータのみです。

**コストAPIを有効にするには：**

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。 Apple Search Ads にログインするように求められたときは、 **権限を選択** で、いずれかを選択してください。 次の手順を実行します：
  * **アカウントの読み取りと書き込み**
  * **アカウント読み取り専用**  
     **注：** 制限付きアクセスを選択し、 特定のキャンペーングループを選択すると、データエラーが発生する可能性があります。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIステータスの表示</Anchor> AppsFlyer がいずれかの コスト（および広告収益）統合ステータスダッシュボード、または 個別の広告ネットワークダッシュボードで一致するコストデータを取得できた最後の時点。

> 📘 **注意**
>
> Apple Search Ads のコストデータは、SKAN ダッシュボードや SKAN Pull API では利用できません。SKAN ポストバックにはキャンペーンレベルのデータが含まれていないためです。 ただし、コストデータは SSOT レポートで利用可能で、これは SKAN インストールデータと、従来の Apple Search Ads 統合を介して取得したコスト情報を組み合わせたものです。

</Accordion>

<div id="disable-agencies-and-marketing-partners" />

<Accordion title="代理店とマーケティングパートナーを無効にする">

**代理店またはマーケティングパートナーによってもたらされたApple Search Adsインストールの計測を停止する方法：**

1. AppsFlyerのサイドメニューから、選択します。 コラボレーション 連携済みパートナー
2. 代理店またはマーケティングパートナーを選択します。
3. コンテンツを削除します。 apple-search-ads-campaign-group-id.png
4. 画面右下の**連携を保存**をクリックします。

</Accordion>

## 追加情報

<div id="asa-attribution" />

<Accordion title="ASA計測手法">

Apple Search Adsは、SKAdNetworkとは独立して別で機能しており、ATTの同意に関係なく決定的モデルで全ユーザーのインストール計測が可能です。つまり、ASAに紐づくユーザーは、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">LTV計測モデル</Anchor>によって提供されるあらゆる機能および計測値を利用できます。

ASA アトリビューションは、IDFAに依存せず —アトリビューションはデバイスからのトークンを使用して行われ（決定的モデル）—ATTの同意状況によって異なります。

| **ATT同意** | **クリック/インプレッション時間の利用可能** | **クリック/インプレッションのルックバック期間** | **備考** |
| --- | --- | --- | --- |
| はい | はい | 広告主が設定 | AppsFlyerのラストクリック計測ルールが適用されます |
| いいえ | いいえ | クリック：30日間  <br />（ASAによって設定）  <br /> / インプレッション：24時間 | クリックまたはインプレッション時間は提供されていません。決定的な計測手法の計測が優先されます。 |

</Accordion>

<div id="discrepancies" />

<Accordion title="数値の乖離">

AppsFlyerとApple Search Adsは異なる計測ロジックを使用しているため、プラットフォーム間で不一致が生じます。SRNである<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#アトリビューション">Apple Search Ads</Anchor>は、API経由で新規インストールをレポートします。

**API経由でのApple Search AdsのAppsFlyerへのレポーティング**

* 各キャンペーンは地域別に集計されます。
* 以下はレポートされません：特定のキャンペーンのインプレッション数が 100 回未満の Geoのインプレッション、タップ、またはコスト。
* AppsFlyerで地域別にグループ化する場合、データが返されない地域は正しい値が表示されず、N/Aとしてひとまとめに表示されます。

### リターゲティング関連の乖離

AppsFlyerリターゲティング計測メカニズムにより、広告主はユーザー獲得キャンペーンに加えて、リターゲティングキャンペーンを測定および分析できます。

以下の図は、Apple Search Adsで実行されているリターゲティングキャンペーン（リターゲティングコントロールの設定に関係なく）に関して、発生しうる乖離を示しています。

**リターゲティングがオン**

[![ASA R Enabled2.jpg](https://files.readme.io/0d26cc4844aa97adb793a266cb2a51961a1345e71a24eec305fcc16539d86027-31197524086801.jpg)](https://files.readme.io/0d26cc4844aa97adb793a266cb2a51961a1345e71a24eec305fcc16539d86027-31197524086801.jpg)

**リターゲティングがオフ**

[![ASA_R_Disabled.png](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)

### その他の乖離の原因

次の表には、乖離の主な理由を示しています。

| 相違点 | Apple Search Ads | AppsFlyer |
| --- | --- | --- |
| <span id="differences-related-to-appsflyer-sdk-versions"></span>AppsFlyer SDKバージョンに関する違い | AppsFlyer SDKのバージョンに関係なくコンバージョンをカウントします。 | AdsServicesの場合、正しく計測するためには、SDK V6.1.3以上を実装する必要があります。 |
| <span id="limit-ad-tracking-lat-and-att"></span>広告トラッキング制限（LAT）とATT | 常にコンバージョンを計測します。<br /><br />キャンペーンが年齢や性別によって制限されている場合、LAT ユーザーはキャンペーンから除外されます。<br /><br />18歳以下のAppleユーザーは常にLATです。 | LATコンバージョンはオーガニックに紐づきます。<br /><br />AdServicesが実装され、iOS14.3以上がインストールされている場合、同意していないユーザーも正しく計測されます。 |
| <span id="counting-users"></span>ユーザー数のカウント | ダウンロードに基づいてユーザーを計測します | 初回アプリ起動に基づいてユーザーを計測します |
| <span id="reinstall-a-user-after-installing-the-app-deletes-it-clicks-on-a-search-ad-then-installs-the-app-again"></span>再インストール：アプリをインストールしたあと、削除し、サーチ広告をクリックしてアプリを再インストールしたユーザー | コンバージョン（インストール）として計測します | <ul><li>IDFA取得できた場合：AppsFlyerは再インストールを識別し、ユーザー獲得の目的にはカウントしません。ヒントリターゲティングを有効にすると、リターゲティングインストール（別名：リアトリビューション）として再インストールが記録されます。</li><li>IDFA取得できなかった場合：AppsFlyerはIDFVを使用して、これが再インストールか新規インストールかを判断できます。<ol><li>端末にベンダーの他のアプリが1つ以上インストールされている場合、AppsFlyerはASAをリアトリビューションします。</li><li>それ以外の場合（他のアプリが存在しない場合）は、AppsFlyerはASAを新規インストールとして計測します。</li></ol></li></ul> |
| <span id="click-lookback-window"></span>クリックルックバック期間 | 30日間に固定 | クリックタイムがないAdServicesからのレスポンスについては、クリックルックバック期間が30日に固定されています。 |
| <span id="impression-lookback-window"></span>インプレッションのルックバック期間 | 固定の24時間ウィンドウ | インプレッション時間がないAdServicesからの応答については、インプレッションのルックバック期間は固定の24時間ウィンドウに設定されています。 |
| <span id="winning-click"></span>成果が紐づくクリック | ユーザーが広告に触れダウンロードした場合は、常に自社の成果とします。 | 複数のネットワークにわたる可視性を持ち、ラストクリックに基づいて成果を測定します。 |
| <span id="install-time"></span>インストール時間 | アプリダウンロード時刻 | アプリ初回起動 |
| <span id="time-zone"></span>タイムゾーン | アプリストアのローカルタイムゾーン | UTCタイムゾーンまたはAppsFlyerで設定されているタイムゾーン |
| <span id="conversion-data"></span>コンバージョンデータ | Search Ads経由でのインストールがAppsFlyerにレポートされるまで5秒以上かかります。 | 5秒以内に計測され、同時にコンバージョンデータAPIが応答します。データが受信されていない場合は、オーガニックと計測されます。 |
| <span id="cost-data"></span>コストデータ | 全てのキーワードに対するコストレポート | コホート管理画面とコホートAPIでは、大文字を含むキーワードに対しては、コストデータをレポートしません。 |
| <span id="geo-locations"></span>地理的ロケーション | Apple Search Adsを使用すると、広告主は 国や地域に応じてユーザーをターゲティングできます。Apple Search Adsは、限られた数の[**国**](https://searchads.Apple.com/storefronts/)をサポートしています。 | AppsFlyerではIPアドレスに基づいてユーザーの地理的位置情報を正確に認識しますが、Apple Search Adsでは地域に関するレポートは利用できません。<br /><br />ヒントアプリストアの国と同じ国内でユーザーがアプリをインストールした場合、AppsFlyerとApple Search Adsの地域データは一致します。 |

</Accordion>

<div id="tips" />

<Accordion title="ヒント">

Apple Search Adsを使用すると、貴重なマーケティングデータを収集できます。これは、iOSアプリの全てのメディアソースでのユーザー獲得の取り組みに効果を与える可能性があります。

Apple Search Adsの利点を最大化するのに役立つヒントを参照ください：

| ヒント | 詳細 |
| --- | --- |
| <span id="get-keyword-data"></span>キーワードデータを取得する | Apple Search Adsは、AppsFlyerとキーワードデータを共有します。キーワードデータは、ローデータやピボット、リテンション、コホートなどの分析ツールで確認できます。<br /><br />**注記：**<ul><li>キーワードデータの取得は8~12時間遅れることがあり、場合によっては、キーワード用語なしでキーワードIDのみが含まれることがあります。</li><li>キーワードデータを取得するには、[コスト] トグルをオンにする必要があります。キーワードデータは、ROI360の契約を必要とせずに [コスト連携](/docs/apple-ads-integration-setup#cost-tab)設定することで取得できます。</li></ul>AppsFlyerでキーワードデータが見つからない場合は、次の原因が考えられます：<ul><li>**パッケージタイプ：** Apple Search Adsによって、キーワードデータはApple Search Adsの[Advanced](https://searchads.Apple.com/advanced/)パッケージを持つ広告主に共有されます。</li><li>**キャンペーンタイプ：** Apple Search Adsでは、さまざまなキャンペーンキーワードのマッチングタイプを設定できます。マッチタイプに基づいて、Apple Search Adsはキーワードを次のように共有します：<ul><li>完全一致：**ユーザーが検索した正確なキーワード**</li><li>**部分一致：** Appleが検索に使用したキーワード。ユーザーの検索ワードに類似しているキーワードです。</li><li>**検索マッチ：** Appleはこれらのキーワードを広告主と**共有しません**。</li></ul></li></ul>完全なキーワード データを受け取りたい場合は、**完全一致、または部分一致のみを使用**して下さい。 |
| <span id="compare-the-quality-of-users-based-on-keyword-data"></span>キーワードデータに基づいてユーザーの質を比較する | 全てのキーワードが同じであるとは限りません。たとえコストが同等の異なるキーワードでも、惹きつけられるユーザーの質は異なる可能性があります。リテンションや<Anchor target="_blank" href="/marketers/ja/docs/pivot-table-user-metrics">ピボット</Anchor>レポートを使って、ROIを最大化するキーワードを特定しましょう。 |
| <span id="analyze-keyword-cost"></span>キーワードのコストを分析する | ASAキーワード広告が[完全一致または部分一致](/docs/apple-ads-integration-setup#get-keyword-data)として設定されている場合、キーワードのコストデータが集計値で確認できます。キーワードのコストデータは以下の特徴があります：<ul><li>過去のデータは2019年10月13日以降で利用可能です。</li><li>ディメンション：<ul><li>日付</li><li>キャンペーン</li><li>広告セット</li></ul></li><li>分析ツール：<ul><li><Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard">コホート</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/pivot-table-user-metrics">ピボット</Anchor></li><li><Anchor target="_blank" href="/marketers/ja/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor></li></ul></li></ul>**制限事項**<ul><li>コストデータクエリの絞り込みやグループ化には、上記のディメンションのみを使用してください。例えば、Geo（国）別に絞り込みやグループ化はしないでください。</li></ul>**<span id="cohort-example"></span>コホートの例**<br />次の例は、コストとROI情報を表示するためのコホートの設定方法を示しています。<br /><br />**コホートの設定**<br /><br />[<Image alt="CohortRequest.png" src="https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png" width="327px" />](https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png)<br /><br />**結果として表示されるコホート表**<br /><br />次の表に、総コストとコホートROIが表示されます。<br /><br />[<Image alt="CohortTable.png" src="https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png" width="429px" />](https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png)<br /><br />**<span id="pivot-example"></span>ピボットの例**<br /><br />**ピボットの設定**<br /><br />[<Image alt="Pivot_define.png" src="https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png" width="413px" />](https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png)<br /><br />**結果として表示されるピボット表**<br /><br />[<Image alt="Pivot.png" src="https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png" width="439px" />](https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png) |
| <span id="find-the-best-performing-creative-set"></span>パフォーマンスが高いクリエイティブを見つける | ![creative_sets.png](https://files.readme.io/ef8e38d67121283742dcbd1faef11d94a8ea1c612dc258611e72cbf826d7ef8f-31197524112785.png)<br /><br />使用しているさまざまな広告クリエイティブに対してユーザーがどのように反応するかテストをしましょう。パフォーマンスが最も高いクリエイティブは、コンバージョン率が最も高くなります。さらに、最高のクリエイティブは、より高いエンゲージメントを持つユーザーを獲得します。<br /><br />これは、最終的に全てのユーザーがアプリストアに到着するため、ASA上のユーザーだけでなく、全てのiOS広告ユーザーにも影響を与えます。ただし、ASA経由のインストールについては、AppsFlyerは<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">ローデータ</Anchor>の **Ad ID**パラメータでクリエイティブセットIDを表示するため、様々なクリエイティブセットのパフォーマンスを比較できます。 |
| <span id="target-redownloaders"></span>再ダウンロードのターゲティング | 過去にインストールしたことのあるユーザーは、Apple Search Adsのターゲットとして最適なオーディエンスである可能性があります。<br /><br />アプリをアンインストールしたユーザーが、ASAリターゲティングキャンペーンの結果、再度インストールしたユーザーは、ASAではRe-Downloaderと呼ばれます。<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">リアトリビューション期間</Anchor>内に再インストールが発生した場合、AppsFlyerはこれをリアトリビューションと呼びます。それ以外の場合は全て、新規インストールとして扱われます。<br /><br />![ASACGroupID.png](https://files.readme.io/ebdc380f2abc3e9a3b134cd258d90ae32f75b3ee4d9eadde39adbc728daae523-31197514645265.png) |

</Accordion>

<div id="asa-change-log" />

<Accordion title="過去の連携仕様アップデート">

| 発効日 | 更新／変更 |
| --- | --- |
| <span id="20230207"></span>2023-02-07 | 拡張データ（パラメーター）である `Campaign name`, `Adset name`, および `Keywords` は、ご契約プランに関係なく、「コスト」タブが有効になっている場合にのみ使用できます。  <br />**つまり、ダッシュボードやローデータレポートにキャンペーン名、広告セット名、キーワードを表示するには、コストタブを有効にする必要があります。** |
| <span id="20220216"></span>2022-02-16 | コストAPIでキーワードが利用できるようになりました。Apple Search Adsの連携ページでAPIを有効にする必要があります。注意！このAPIは、ご契約プランに関わらず、全ての広告主が利用できます。 |
| <span id="20210407"></span>2021-04-07 | <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">Apple Search Adsの連携</Anchor>：ASAはSKAdNetworkとは独立して機能し、全ユーザーに対して独自の決定論的モデルを使用してアトリビューション計測を可能にしています。つまり、ASAに紐づくユーザーは、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">LTV計測モデル</Anchor>によって提供されるあらゆる機能および計測値を利用できます。 |
| <span id="20210307"></span>2021-03-07 | Apple Search Adsは、キャンペーン管理API V4.0の展開を開始しました。このAPIはコストとその他のキャンペーンデータに関連するもので、アトリビューションには影響しません。現在、更新されたAPIの導入を進めています。お客様側の作業はありません。 |
| <span id="20210215"></span>2021-02-15 | 発効日以降、ASAの[コストAPI](/docs/apple-ads-integration-setup#cost-tab)を有効にしている場合、キャンペーン名と広告セット名の項目が入力されます。このAPIは、ご契約プランに関わらず、全ての広告主様が利用できます。 |

ASAの更新と変更

</Accordion>

<div id="availability-of-apple-search-ads-campaign-parameters" />

<Accordion title="利用可能なApple Search Adsキャンペーンパラメーター">

以下の表では、ローデータレポートまたは管理画面上でご利用いただける計測パラメーターを示しています。

| ローデータレポートのパラメーター | 可用性 |
| --- | --- |
| Campaign name | このパラメーターを利用するには、Apple Search Adsの連携ページにて[コストAPI](/docs/apple-ads-integration-setup#cost-tab)を有効にする必要があります。このAPIは、ご契約プランに関わらず全ての広告主様において利用可能です。 |
| Campaign ID | 常に利用可能です。 |
| Adset name | このパラメーターを利用するには、Apple Search Adsの連携ページにて[コストAPI](/docs/apple-ads-integration-setup#cost-tab)を有効にする必要があります。このAPIは、ご契約プランに関わらず全ての広告主様において利用可能です。 |
| Adset ID | 常に利用可能です。 |
| Ad | 現在ご利用いただけません。 |
| Ad ID | このパラメーターは、次の両方の条件が満たされている場合にのみご利用いただけます。<ul><li>iOS 15.2以降を使用しているユーザー</li><li>以下の広告配置のいずれかに関連するキャンペーンで、広告が <Anchor target="_blank" href="https://developer.apple.com/app-store/product-page/">カスタムプロダクトページ</Anchor> を使用している場合：<ul><li>`Today tab`</li><li>`Search results`</li></ul></li></ul> |
| Keywords | このパラメーターを利用するには、Apple Search Adsの連携ページにて[コストAPI](/docs/apple-ads-integration-setup#cost-tab)を有効にする必要があります。このAPIは、ご契約プランに関わらず全ての広告主様において利用可能です。 |
| Keyword ID | このパラメーターはローデータレポート経由でご利用いただけます。ただし、Data Locker、Push API、データエクスポートで明示的に選択する必要があります。Pull APIの場合は、`Pull APIコール`の `&additional_fields` パラメーターに <Anchor target="_blank" href="/marketers/ja/docs/pull-api-raw-data#additional-fields">keyword\_id</Anchor> を追加してください。 |
| Keywords Match Type | 現在ご利用いただけません。 |

</Accordion>

<div id="impact-of-aggregated-advanced-privacy" />

<Accordion title="高プライバシー一括設定の影響">

iOS14以降、<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">ATTrackingManager</Anchor>（ATT）がIDFAを取得できるかどうかを制御し、ユーザーレベルでのASA経由のインストールの計測データについてはASAによって制御されます。そのため、ASA経由インストールのユーザーレベルのデータは、<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">高プライバシー一括設定</Anchor>の影響は受けません。

| **ATTの同意** | **クリック/インプレッション時間の利用可能** | **クリック/インプレッションのルックバック期間** | **備考** | **データの可用性** | **IDFAが利用可能** |
| --- | --- | --- | --- | --- | --- |
| 同意 | はい | 広告主が設定 | AppsFlyerのラストクリック計測ルールが適用されます。 | ユーザーレベルアトリビューションデータ | はい |
| 同意しない | いいえ | クリック：30日間  <br />（ASAによって設定）<br /><br />/ インプレッション：24時間 | 決定論的計測手法の計測が優先されます。 | クリック/インプレッション時間なしのユーザーレベルのアトリビューションデータ | いいえ |

</Accordion>

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">高プライバシー一括設定のフレームワーク</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">ルックバック期間について</Anchor>

<div data-zendesk-anchors="h_01J3WQNHJZSW1MX8SWXTNX8JKD=%E6%B3%A8 set-up-asa-integration=asa%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDPCGMP2CY4B37VM3AT2P114=asa%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDPCGMP35S325269JETX1EJW=get-started h_01HDPCGMP383Y223E1YXF60C8S=%E6%B3%A8-1 h_01HDPCGMP3JC93JWHM2SM8EVZA=integration h_01JP51C2KK0B7PQAT6NB8ANK3B=cost-tab h_01HDPCGMP3XGYXVZZJ8SGDK3G2=%E6%B3%A8%E6%84%8F h_01HDPCGMP3KXMKSHN0GFD6MAFG=permissions-tab set-up-agencies-and-asa-marketing-partners=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%A8asa%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDPCGMP3D96BG496G7H97YWP=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%A8asa%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDPCGMP3EBHM0CQXKP05SG9F=principles agency-vs-marketing-partner=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%A8%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC h_01HDPCGMP3YGJEA942DF2YC9P1=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%A8%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC configuring-agencies-and-marketing-partners=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%A8%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDPCGMP3NQQ76SC32SEC8TS4=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%A8%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A configuration-steps-checklist=%E8%A8%AD%E5%AE%9A%E3%82%B9%E3%83%86%E3%83%83%E3%83%97%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 h_01HDPCGMP39HE117X4MP25M77W=%E8%A8%AD%E5%AE%9A%E3%82%B9%E3%83%86%E3%83%83%E3%83%97%E3%81%AE%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 h_01HDPCGMP3BT4YJWJ2G8X76NSE=marketing-partner-setup h_01HDPCGMP3X6B4RYF289WY49P7=agency-setup advertiser-actions=%E5%BA%83%E5%91%8A%E4%B8%BB%E5%81%B4%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 h_01HDPCGMP3S3PHHH3F6KZE3SEV=%E5%BA%83%E5%91%8A%E4%B8%BB%E5%81%B4%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 agency-actions=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%8C%E8%A1%8C%E3%81%86%E8%A8%AD%E5%AE%9A h_01HDPCGMP3MK61YRMCQA2KA5X2=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%8C%E8%A1%8C%E3%81%86%E8%A8%AD%E5%AE%9A h_01HDPCGMP3E7PZB8FDG4XN79JA=%E6%B3%A8%E6%84%8F-1 cost-clicks-and-impressions-data=%E3%82%B3%E3%82%B9%E3%83%88%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF h_01HDPCGMP3AVYYK2X03RF057FN=%E3%82%B3%E3%82%B9%E3%83%88%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF h_01JYM0FHV098KXW5RAWW3N916W=%E6%B3%A8%E6%84%8F-2 h_01HDPCGMP3113BYD1GPJM7XBQH=disable-agencies-and-marketing-partners additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HDPCGMP3BXVASH2YJ9G8AS2C=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HDPCGMP31QFVN1SWBCABJ65K=asa-attribution h_01HDPCGMP4DCKH898AEWAY6N01=discrepancies retargeting-related-discrepancies=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E9%96%A2%E9%80%A3%E3%81%AE%E4%B9%96%E9%9B%A2 h_01HDPCGMP4Z9M3QR6QGRR7A8BM=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E9%96%A2%E9%80%A3%E3%81%AE%E4%B9%96%E9%9B%A2 additional-reasons-for-discrepancies=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E4%B9%96%E9%9B%A2%E3%81%AE%E5%8E%9F%E5%9B%A0 h_01HDPCGMP4QJ3HYEP7EAYMHRQQ=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E4%B9%96%E9%9B%A2%E3%81%AE%E5%8E%9F%E5%9B%A0 h_01HDPCGMP4A8NAD8SYD191YJYR=tips h_01HDPCGMP4HNS84AVWH7J8H7YA=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E4%B9%96%E9%9B%A2%E3%81%AE%E5%8E%9F%E5%9B%A0 h_01HDPCGMP4MF9FBP4WDRHVZ4BR=cohort-example h_01HDPCGMP4EFMZ4FHZ8WBWW9R2=pivot-example h_01HDPCGMP4XKB75F6R7DDWDHPB=asa-change-log h_01HDPCGMP40MW37BFT8A096PNG=availability-of-apple-search-ads-campaign-parameters h_01HDPCGMP48M04SDA4FGYW6XNQ=impact-of-aggregated-advanced-privacy h_01HDPD3C1T4ZXXZ2RE0GSXPZP3=%E5%8F%82%E7%85%A7" />
