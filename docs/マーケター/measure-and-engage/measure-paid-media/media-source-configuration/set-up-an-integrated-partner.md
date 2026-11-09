---
title: 連携パートナーを設定する
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-08T08:02:46Z'
  edited_at: '2026-10-14T09:26:52Z'
  id: 4410395957521
  locale: ja
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ja/articles/4410395957521
---
> **概要：** AppsFlyerとのパートナー接続を設定することで、アトリビューション計測を可能にし、パートナーにポストバックを送信したり、その他の連携機能を利用できます。

<div id="overview" />

## 概要

パートナー、メディアソース、およびサードパーティプラットフォームは、APIによってAppsFlyerと連携されます。この記事では、SRN以外のアドネットワークの計測リンクの生成など、連携を有効にして設定するための一般的な手順について説明します。

* このガイドはSRNには適用されません。<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">SRNに関する別ページ</Anchor>を参照してください。
* 一部のアドネットワークには専用の連携ガイドが提供されています。
* 設定を始める前に、パートナーに連絡してアカウントを開設してください。

<div id="partner-types-in-the-ecosystem" />

<Accordion title="エコシステム内のパートナータイプ">

以下の画像には、アトリビューションエコシステムを構成するさまざまなパートナータイプが表示されています。

<Image align="center" alt="Ecosystem.jpg" src="https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg" />

**関連記事**：<Anchor target="_blank" href="https://www.appsflyer.com/performance-index/">AppsFlyerパフォーマンスインデックス</Anchor>で、カテゴリおよび地域別にモバイルメディアソースのランキングを確認できます。

| パートナータイプ | 説明 |
| --- | --- |
| アドネットワーク | あなたに代わってキャンペーンを行います。 |
| 代理店 | 代理店の専門知識を活用し、高品質なユーザーを獲得するためにあなたに代わってキャンペーンを行います。<Anchor target="_blank" href="/marketers/ja/docs/view-agency-data">エージェンシーデータ</Anchor>についてもっと知る |
| マーケティングパートナー | マーケティングパートナーは、特定のアドネットワークでの連携に特化しています。例：Metaキャンペーン管理パートナー、Apple Adsマーケティングパートナー、Xマーケティングパートナー |
| リターゲティングネットワーク | リターゲティングキャンペーンの実行に特化したアドネットワークです。 |
| サードパーティプラットフォーム | 分析やマーケティングオートメーションプラットフォームなど、ビジネスインテリジェンス関連サービスを提供します。 |
| 不正検知 | AppsFlyer Protect360の一部ではない外部サードパーティの不正防止システム。 |

</Accordion>

<div id="partners-in-the-marketplace" />

<Accordion title="パートナー統合におけるパートナー">

AppsFlyerと連携しているすべてのパートナー、メディアソース、その他のプラットフォームは、「パートナー連携」ページに掲載されています。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">アクティブなパートナーと非アクティブなパートナーの両方</Anchor>を見つけて、新しいパートナーとの接続を探すことができます。

**パートナー統合で、すべてのパートナー、メディアソース、またはその他のプラットフォームを検索およびフィルタリングするには：**

* AppsFlyerのサイドメニューから、［**連携**］＞［**パートナー連携**］を選択します。さまざまな検索フィルターを使用できます。

<div id="invite-new-partners-to-appsflyer" />

#### AppsFlyerに新しいパートナーを招待する

連携しているパートナーがまだAppsFlyerと連携していない場合は、<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#appsflyerに新規パートナーを招待する">招待を送信</Anchor>できます。

</Accordion>

<div id="your-integrated-partners" />

<Accordion title="アクティブな連携済みのパートナー">

「パートナー統合」の「アクティブ統合」タブには、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">現在統合</Anchor>されているすべてのパートナーが表示されます。このページから、パートナーに関する情報を学び、連携を管理することが可能です。

<div id="note" />

> 📘 **注意**
>
> タブに表示されるパートナーの一覧は、選択したアプリによって異なります。左上のアプリをクリックして、別のアプリを選択することで、どのパートナーが他のアプリに接続されているか確認できます。

**すべてのアクティブなパートナーを確認するには：**

* AppsFlyer のサイドメニューから、［**Collaborate**］>［**Partner Integrations**］>［**Active integrations**］ タブを選択します。

</Accordion>

<div id="about-the-integrated-partner-page" />

<Accordion title="パートナー設定画面について">

画面は以下のように構成されています：

* **ヘッダー**には以下が含まれます：
  * パートナー名
  * パートナー専用記事へのリンク。専用記事が存在しない場合はこの記事が表示されます。
  * 連携ステータス
  * 選択されたアプリ
* **設定タブ**：利用可能なタブは、パートナーの種類とサポートされている機能により異なります。
* **フッター**：
  * **リストに戻る**：以前に選択したフィルタリングオプションを使用して、連携済みパートナーリストに戻ります。
  * **ステータスメッセージ：** タブデータの現在のステータス（例えば、保存中、保存済み、エラー、未保存の変更がある場合など）。
  * **変更を破棄：** 最後の変更を保存せずに元に戻します。
  * **保存：** 現在のタブ設定のみを保存します。

<div id="applicable-settings-tabs-per-partner-type" />

#### パートナータイプごとの適用可能な設定タブ

<table><thead><tr><th> </th><th colspan="2">設定タブ</th><th> </th></tr><tr><th>パートナータイプ</th><th>連携 </th><th>権限</th><th>備考</th></tr></thead><tbody><tr><td>メディアソース</td><td>はい</td><td>はい</td><td><p><strong>利用可能な追加タブ</strong>：コスト、広告収益、計測リンク</p><p>アドネットワーク、アフィリエイトネットワーク、ダイレクトパブリッシャー、プログラマティック広告、中国国内アドネットワーク、リターゲティングネットワークが含まれます。<br/>SRNの場合、計測リンクタブは適用されません。</p></td></tr><tr><td>代理店 </td><td>いいえ</td><td>はい</td><td>アドネットワークとして機能しないスタンドアロン代理店</td></tr><tr><td>サードパーティプラットフォーム</td><td>はい</td><td>いいえ</td><td>分析またはマーケティングオートメーションプラットフォーム</td></tr><tr><td>マーケティングパートナー </td><td>はい</td><td>いいえ</td><td> </td></tr></tbody></table>

</Accordion>

<div id="set-up-a-partner-non-srn" />

## パートナーの設定（SRN以外）

<div id="important" />

> 🚧 **重要！**
>
> パートナー連携を有効にすると、個人情報（例：広告ID、IPアドレス）を含む特定のデータが、デフォルトで共有されます。このデータを共有するための適切な法的根拠と権利があることを確認してください。パートナーとのデータ共有を制限するには、<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">集約的高プライバシーフレームワーク</Anchor>および<Anchor target="_blank" href="/marketers/ja/docs/apply-privacy-preserving-sdk-methods">SDKにおけるプライバシー保護手法</Anchor>の記事に記載された指示に従ってください。

**設定にアクセスし、パートナーとのキャンペーンを構成するには：**

[パートナー連携から、パートナーを検索して選択してください。](/docs/set-up-an-integrated-partner#partners-in-the-marketplace)

<div id="note-1" />

> 📘 **注意**
>
> タブの[一般設定](#d-general-settings)ステップは、すべてのパートナー連携において必須です。SRN以外のアドネットワークの場合、**計測リンク**のタブも完了する必要があります。残りのタブはオプションです。

<div id="integration-tab" />

<Accordion title="連携タブ">

パートナー連携の要件はそれぞれ異なり、このセクションで説明されているすべての可能なオプションのサブセットを含めることができます。iOSとAndroidの設定にはいくつか違いがあります。

<Image align="center" alt="連携パートナーの設定.png" src="https://files.readme.io/441ddfcd784a000099ae75acdb234d32bfe75ab598a34a88c7f9ed651fe8f7ec-15520850610449.png" />

必要に応じて各セクションを完了してください。

<div id="integration-sections" />

#### 連携セクション

次の表には、連携画面のさまざまなセクションが含まれています。一部のセクションはすべてのユーザーが利用できますが、他は連携ごとに異なります。

<Table>
  <thead>
    <tr>
      <th>
        セクション
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="a-activate-partner"></span>
        パートナーを有効にする
      </td>
      <td>
        パートナーと計測リンクを共有する前に、**パートナーを有効にする**トグルをオンにし、連携タブの残りのセクションを完了する必要があります。

        * キャンペーンのアトリビューションを一時停止または無効にするために**パートナーをアクティブにする**を利用しないでください。
        * パートナー連携を無効にすると、**アクティブなキャンペーンに回復不可能なデータ欠損が発生する可能性があります**。
        * 詳細：<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効 / 無効設定による影響</Anchor>

        **連携パートナーを有効にするには：**

        1. AppsFlyerのサイドメニューから、［**連携**］＞［**パートナー連携**］を選択します。
        2. パートナーを検索して選択します。連携設定画面に移動します。
        3. <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">**パートナーを有効にする**</Anchor>トグルをオンにします。
        4. **連携を保存**をクリックします。
        5. オプション ：パートナーが<Anchor target="_blank" href="/marketers/ja/docs/manage-data-access-permissions">自社のキャンペーンに紐づくデータを閲覧</Anchor>できるようにするには、[権限](/docs/set-up-an-integrated-partner#permissions-tab)タブで[アドネットワークの権限](/docs/set-up-an-integrated-partner#アドネットワークの権限)をオンにしてください。
      </td>
    </tr>
    <tr>
      <td><span id="b-advanced-privacy"></span>
        高プライバシーポストバック
      </td>
      <td>
        iOSアプリのみ：  
        <strong>高プライバシー設定（iOS 14.5以降）</strong>がオンになっている場合、ポストバックとレポートを通じて、<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">パートナーと共有するデータをコントロール</Anchor>できます。これにより、パートナーとのユーザー識別子の共有を制限します。アプリ設定で<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">高プライバシー 一括設定</Anchor>トグルがオンの場合、<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">**高プライバシーポストバック（iOS 14.5以降）**</Anchor>がオンになり、ロックされます。
      </td>
    </tr>
    <tr>
      <td><span id="c-transaction-id"></span>
        トランザクションID
      </td>
      <td>
        iOSアプリのみ：  
        **SKANトランザクションIDの共有**がオンになっている場合、<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAdNetworkポストバックのトランザクションID</Anchor>をパートナーと共有することになります。それによって、パートナーはSKAdNetworkコンバージョン値をデコードできるようになります。
      </td>
    </tr>
    <tr>
      <td><span id="d-general-settings"></span>
        一般的な設定
      </td>
      <td>
        **パートナーID—認証情報**  
        一部のパートナーは、AppsFlyerが連携パートナーとの連携に認証情報を要します。パートナーはこのIDをアプリID、アカウントID、ユーザーID、またはネットワークIDと呼びます。このフィールドが表示される場合は、パートナー管理画面からIDを取得し、フィールドに入力します。
      </td>
    </tr>
    <tr>
      <td><span id="non-eu-users"></span>
        非EUユーザー
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/ja/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**Non EU users**</Anchor>トグルを有効にするか決定してください。
      </td>
    </tr>
    <tr>
      <td><span id="e-install-attribution"></span>
        インストール計測
      </td>
      <td>
        広告を表示またはクリックしたユーザーの新規インストール（初回起動）をアトリビューションするためのアトリビューション期間を設定します。アトリビューションルックバック期間とは、広告のクリックまたは表示からインストールまでの最大時間を指し、パートナーにインストールがアトリビューションされ得る期間です。

        * **インストールクリックスルールックバック期間：** アプリへのクリック後、インストールをクリックに紐づける最大時間を設定します。

        **インストールのビュースルーアトリビューション：オンにすることで、広告を見たがクリックしなかったユーザーによる新規インストールのアトリビューションを開始します。**

        * **インストールのビュースルールックバック期間：** ビューからアプリへの遷移後、インストールをそのビューに紐づける最大時間を設定します。

        参照：<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">ルックバック期間の詳細</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="e-re-engagement-attribution"></span>
        リエンゲージメントCV計測
      </td>
      <td>
        リエンゲージメントCVのルックバック期間をオンにして設定し、既存ユーザーのリエンゲージメントCVの計測を開始します。非SRNの場合、この設定は連携タブまたは[計測リンク](/docs/set-up-an-integrated-partner#リターゲティング設定)タブで利用できます。

        * **リエンゲージメントCVのクリックスルールックバック期間：** クリックからアプリ起動までの最大時間を設定し、リエンゲージメントCVとしてクリックに紐付けます。

        **リエンゲージメントCVのビュースルー計測：** オンにすることで、広告を見たがクリックしなかった既存ユーザーのリエンゲージメントCVの計測を有効にします。

        * **リエンゲージメントCV：ビュースルーのルックバック期間：** ビューからアプリへの遷移後、アプリ起動をリエンゲージメントCVとしてビューに紐づける最大時間を設定します。

        参照：<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">ルックバック期間の詳細</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="reengagement-window"></span>
        リエンゲージメント期間
      </td>
      <td>
        アプリ内イベントを、主にリエンゲージメントコンバージョンに紐付ける期間を設定します。<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#setup-reengagement-window">詳細はこちら</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="ignore-active-users"></span>
        リターゲティングCVの計測対象からアクティブユーザーを除外
      </td>
      <td>
        指定された期間内にアクティブユーザーのリターゲティングコンバージョンが記録されないように、ユーザーの休眠期間を設定します。参照：<Anchor target="_blank" href="/marketers/ja/docs/set-retargeting-inactivity-window">リターゲティング計測における休眠期間の詳細と設定</Anchor>

        **<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns">SRN</Anchor>の場合：**

        1. 連携タブから、**リエンゲージメントCV計測**をオンにします。
        2. **リターゲティングCVの計測対象からアクティブユーザーを除外**トグルをオンにします。
        3. **休眠期間**を設定します。

        **SRN以外の場合：**

        1. 計測リンクタブで、**リターゲティング設定**をオンにします。
        2. **リターゲティングCVの計測対象からアクティブユーザーを除外**トグルをオンにします。
        3. **休眠期間**を設定します。
      </td>
    </tr>
    <tr>
      <td><span id="e-cross-platform-attribution"></span>
        クロスプラットフォームのアトリビューション
      </td>
      <td>
        **クロスプラットフォームの均等なアトリビューション優先度**がオンの場合、選択した期間中のクロスプラットフォームインプレッションはアトリビューションの優先度が均等に設定されます。
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-attribution"></span>
        プリロード計測
      </td>
      <td>
        **プリロード計測**がオンの場合、<Anchor target="_blank" href="/marketers/ja/docs/measure-preload-campaigns-with-google-play-install">インストールは**プリロードキャンペーン**</Anchor>にアトリビューションされます。**プリロードルックバック期間**を設定して、デバイスがアクティブ化された後、プリロードインストールをパートナーへアトリビューションする（紐づける）期間を決定します。
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-equal-attribution-priority"></span>
        プリロード同等のアトリビューション優先度
      </td>
      <td>
        **プリロード同等のアトリビューション優先度**がオンの場合、選択されたルックバック期間中のプリロードエンゲージメントには、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#アトリビューション方法">決定論的モデリングと同じアトリビューション優先度</Anchor>が適用されます。
      </td>
    </tr>
    <tr>
      <td><span id="advanced-data-sharing"></span>
        アドバンスデータ共有
      </td>
      <td>
        **アドバンスデータ共有**がオンの場合、追加のデータが計測リンクを通じてパートナーと共有されます。  
        **注記：** この共有オプションは、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-aggregate-event-measurement-aem-for-ios#aemのデータ共有">Meta広告のAEMアドバンスデータ共有</Anchor>とは異なります。
      </td>
    </tr>
    <tr>
      <td><span id="default-postbacks"></span>
        デフォルトのポストバック
      </td>
      <td>
        パートナー連携がオンの場合、インストール、ブロック済みインストール、リエンゲージメントなど、アプリ起動前に行われたユーザーアクションに関連するデフォルトのポストバックがパートナーに送信されます。

        <div id="01H80XGTBQ4MPGGKSZW0D9GG9H" />

        > 📘 **注**
        >
        > * ブロック済みされたイベントは、<Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide">Protect360</Anchor>によってブロックされたアプリ内イベント、またはターゲット検証で非準拠と判断されたイベントです。ブロック済みイベントについては、パートナーがAppsFlyerとのブロック済みイベントの連携を有効にしているか確認してください。
        > * 技術パートナーはインストールとリエンゲージメントのデフォルトポストバックを受け取ることができます。場合によっては、アプリ内イベントのポストバックを受け取ることも可能です。

        **パートナーのデフォルトポストバックを設定**するには、ポストバックを送信するユーザーのソースを定義してください。

        * **このパートナーのみ：** イベントがこのパートナーに起因する場合、つまり、イベントを実行したユーザーがこのパートナーから来た場合にのみ、ポストバックを送信します。  
          **注記：** 次の場合、デフォルトのポストバックは常に **このパートナーのみ** として設定されます。
          * ブロック済みインストール
          * 代理店（[権限](/docs/set-up-an-integrated-partner#代理店の許可)あり）
        * **オーガニックを含むすべてのメディアソース：** あらゆるパートナーに起因するイベントやオーガニックイベント、つまり、それを行ったユーザーがどのメディアソースから来たものであっても、ポストバックを送信します。
        * オフこのパートナーにデフォルトのポストバックを送信しないでください。
      </td>
    </tr>
    <tr>
      <td><span id="g-in-app-event-postback-configuration"></span>
        <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration">アプリ内イベントポストバック</Anchor>
      </td>
      <td>
        ポストバックを介して、AppsFlyerイベントをパートナーのイベントと<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#イベントマッピング">マッピング</Anchor>します。ポストバック送信が有効な場合、これにはブロック済みアプリ内イベント（Protect360によって不正としてブロックされたイベントや、検証ルールに準拠していないと判断されたイベント）が含まれます。

        **アプリ内イベントのポストバックを設定するには：**

        1. **パートナーID**を設定します（必要な場合）。
        2. **アプリ内イベントポストバック**を有効にします。
        3. 必要に応じて、**アプリ内イベントポストバック期間**を設定してください（詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントポストバック期間の設定</Anchor>を参照してください）。
        4. **イベントを追加**をクリックし、SDKまたはサーバー間イベントをリストに追加します。
        5. <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#マッピング方法">マッピング方法</Anchor>に従って、必要なパラメーターを入力します。
        6. オプション： <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> をクリックして、特定のアプリ内イベントをパートナーに送信するための<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件</Anchor>を設定します。

        | パラメーター名 | 説明 |
        | --- | --- |
        | <span id="appsflyer-event"></span>**AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。  <br />**ヒント**：探しているイベントが見つかりませんか？<br /><br />* 必ず、非オーガニックインストールのデバイスでイベントを起動して、再確認してください。<br />* **AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントマッピングの詳細をお読みください。</Anchor> |
        | <span id="mapped-to-partner-event"></span>**パートナー側のイベント名** | パートナー側で設定された各イベントの一意の名前またはID。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#マッピング方法">可能なマッピング構成</Anchor>は次のとおりです。<br /><br />* **テキスト項目：** 対応するイベントIDをパートナーから取得します。<br />* **ドロップダウンボックス：** 最も適切な事前定義されたパートナーイベントを選択します。<br />* **そのまま**：イベント名をマッピングせずに、イベントをそのまま送信します。 |
        | <span id="for-users-from"></span>**送信オプション** | イベントの送信オプションを選択してください：<br /><br />* **このパートナーのみ：** イベントがこのパートナーに起因する場合、つまり、イベントを実行したユーザーがこのパートナーから来た場合にのみ、ポストバックを送信します。<br />* **オーガニックを含む全メディアソース**：あらゆるパートナーに起因するイベントや、オーガニックなイベント、つまり実行したユーザーがあらゆるメディアソースから来た場合にポストバックを送信します。 |
        | <span id="including"></span>**送信データ** | ポストバックでパートナーと共有する<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#ポストバックに含めるデータ">イベントデータ</Anchor>を選択します。<br /><br />* **付随データなし**：パラメーター（値または収益）なしでイベント自体のみを送信します。<br />* **イベント値のみ**：収益値**以外**のすべてのパラメーターを送信します。<br />* **イベント値と収益**：収益値を含むすべてのイベントパラメーターを送信します（イベント内に存在する場合）。 |

         備考：

        * 特定のパートナーの連携タブでマッピングされたイベントは、標準ポストバックと<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKANポストバック</Anchor>の両方に適用されます。
        * ポストバックはパートナーにリアルタイムで送信されます。
        * AppsFlyerイベント名は選択することも、入力することもできます。  
          入力された値には、イベント名の前後に下線付きのスペース（アンダースコア）を含めることができます。AppsFlyerから送信されるイベント名に同じ下線付きスペースがある場合にのみ、下線付きスペースを使用します。
        * **重要：** イベント名では大文字と小文字が区別されます。不一致を避けるため、すべてのメディアソースとアプリバージョンに正しいイベント名を使用するようにしてください。
        * **連携**タブに**アプリ内イベントポストバック**セクションが存在しない場合は、パートナーが予備設定でAppsFlyerを利用したアプリ内イベント記録をまだ設定していないことを意味します。パートナーは、<Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">パートナーアシスタントウィジェット</Anchor>を使用してAppsFlyerに連絡し、連携を完了できます。
        * 広告主が意図せずにサードパーティプラットフォームと過剰な情報を共有することを防ぐため、2019年3月より、サードパーティプラットフォームの<strong>すべてのイベントを送信（アンインストール、セッション、{"af_ad_"}収益を除く）</strong>オプションを削除しました。これより前に設定されたサードパーティプラットフォームでは、このセットアップオプションが保持されます。

        関連記事：

        * <Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration">アプリ内イベントポストバック</Anchor>の設定
        * <Anchor target="_blank" href="/marketers/ja/docs/share-ad-revenue-data-with-partners#ad-revenue-event-postbacks-for-ad-networks">広告収益イベントポストバック</Anchor>の設定
      </td>
    </tr>
    <tr>
      <td><span id="h"></span>
        連携の保存
      </td>
      <td>
        変更を加えたら、**連携を保存**をクリックします。
      </td>
    </tr>
    <tr>
      <td><span id="i-connect-more-apps-optional"></span>
        他のアプリをさらに接続（オプション）
      </td>
      <td>
        連携を保存した後、連携設定画面に留まりつつ、さらに多くのアプリをパートナーと連携できます。

        1. 左上のパートナー名の下にあるアプリ名をクリックし、アプリリストを開きます。
        2. ドロップダウンリストから別のアプリを選択してください。
        3. 選択したアプリで連携手順を繰り返します。
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

クリック（非SRN）アドネットワークのために計測リンクを生成して保存し、そのリンクを媒体へ入稿して、特定のキャンペーン、広告セット、または単一の広告をアトリビューションします。

**注：** SRNは広告主が生成した計測リンクを実装しないため、このタブはSRNキャンペーンには関連しません。

**計測リンクを生成するには：**

1. **単一プラットフォームリンクを使用する**か**OneLinkを使用する**のいずれかを選択します。

   次のいずれかに該当する場合、**単一プラットフォームリンクを使用する**を選択します。

   * アプリを開くには<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">URIスキーム</Anchor>のみを使用する予定です。
   * URLでのディープリンクが必要ない場合。

   次のいずれかに該当する場合、**OneLinkを使用する**を選択します。

   * AndroidおよびiOSアプリ両方に単一のリンクが必要な場合。
   * AndroidアプリリンクまたはiOSユニバーサルリンクを使用してアプリを開く場合。
   * ディープリンク機能が必要な場合。

   **注記**：OneLinkを選択すると、クリック計測リンクがアプリ固有から<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink URL</Anchor>に変更されます。
2. **OneLinkを使用する**を選択した場合：
   1. アプリを開くために使用するOneLinkテンプレート（およびディープリンク）を選択します。
   2. オプション： **ディープリンク価値**を入力します。
   3. オプション： **追加のディープリンク値**を入力します。
3. 必要に応じて、<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#android専用のパラメータ">Android</Anchor> および <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#ios専用のパラメータ">iOS</Anchor> のパラメーターを追加します。
4. オプション： 追加のアトリビューションパラメーターを選択します。

<div id="attribution-link-parameters" />

#### 計測リンクパラメーター

<Image align="center" alt="attribution-link-parameters-en_us.png" src="https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png" />

計測リンクにパラメーターを追加すると、詳細なドリルダウン分析を実行できます。計測リンクですでに定義されているパラメーターは、それらと新しい値をここで追加することで編集できます。計測リンクを保存すると、このタブで設定したすべてのパラメーターが保存されます。

計測リンクに追加するパラメーターを選択します。

<div id="attribution-link-parameters-1" />

#### 計測リンクパラメーター

| 名前 | 説明 | 計測リンクパラメーター |
| --- | --- | --- |
| キャンペーン | **必須パラメーター。**  <br />メディアソースで実行している様々なキャンペーンを比較します。 | c |
| 広告セット | メディアソースの特定のキャンペーン内の異なる広告セットを比較します。 | af\_adset |
| 広告名 | メディアソースの特定のキャンペーン内における特定の広告セット内で、各クリエイティブを比較します。 | af\_ad |
| サイトIDとサブサイトID | **必須パラメーター。**<br /><br />インストールを特定のパブリッシャーにアトリビューションさせるには、サイトIDを設定します。<br /><br />サイトIDは次の理由で計測リンクでAppsFlyerに渡す必要があります：<ul><li>パブリッシャーに対する明確さと透明性を提供します。</li><li>AppsFlyerは、不正なパブリッシャーや他のトラフィッククラスターを識別し排除するために使用します。</li></ul>サイトIDが欠如していても、アトリビューションには影響しないことに注意してください。参照：<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#site-id-parameter">サイトIDパラメーターの詳細</Anchor><br /><br />パブリッシャーが多い場合、<Anchor target="_blank" href="/marketers/ja/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">サイトIDの制限を超えないように</Anchor>、使用するサイトIDの数を制限し、サブサイトIDパラメーターを使用することをお勧めします。 | af\_siteid および af\_sub\_siteid |
| サブパラメーター | 5つのサブパラメーターのいずれかを利用して、有用な値を挿入します。これらのパラメーターは解析されローデータレポートに表示されるため、データの集約やフィルターに非常に便利です。 | af\_sub1 / af\_sub2 / af\_sub3 / af\_sub4 / af\_sub5 |

新しいパラメータボックスに入力することで、計測リンクに他のパラメーターを追加可能です。すべてのAppsFlyerで<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">利用可能なURLパラメーター</Anchor>を使用できます。注意：URIスキームとOneLinkパラメーターの値は、エンコードする必要があります。

<div id="retargeting-settings" />

#### リターゲティング設定

**リターゲティング計測がオンの場合：** AppsFlyerは、計測リンクに `&is_retargeting=true` パラメータを追加して、リンクをユーザー獲得ではなく、<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティング</Anchor>計測リンクとして認識します。  
**計測リンクパラメータ：** is\_retargeting

リターゲティング計測用のリンクを使用する：

1. **リターゲティング計測設定**をオンにします。
2. オプション： URIスキームを使用してアプリを開く場合は、URIスキームを入力します。  
   　**注：**
   * ユニバーサルリンクまたはアプリリンクが機能しない場合に備えて、アプリを開くためのフォールバック方法として、URIスキームが推奨されます。
   * ここでURIスキームを追加すると、OneLinkテンプレート設定内の既存のURIスキームが上書きされます。
   * URIスキームは af\_dp パラメータとしてリンクに追加されます。
3. オプション： **リターゲティングCVの計測対象からアクティブユーザーを除外** トグルをオンにします。
4. 休眠期間を設定して、どのユーザーがアクティブおよび非アクティブと見なされるかを決定します。
5. リエンゲージメント期間を設定し、リエンゲージメント後の期間中にユーザーのアプリ内イベントがリターゲティングメディアソースに紐付けられるようにします。
   * 値は、日数（1-90）、時間（最大23）、またはライフタイムで設定できます。
   * リエンゲージメント期間は af\_reengagement\_window パラメータとしてリンクに追加されます。

<div id="click-through-attribution" />

#### クリックスルー計測

この設定を利用して、**クリックからインストールまでの最大時間**を設定します。ルックバック期間内に行われたインストール（初回起動）のみがアトリビューションされます。

許可される範囲：1〜23時間または1〜30日。

**計測リンクパラメータ：** af\_click\_lookback

参照：<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">クリックルックバック期間についての詳細</Anchor>

**クリック計測リンク**

<Image align="center" alt="click-through-attribution-link_en-us.png" src="https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png" />

これは、設定したすべての情報を含む計測リンクです。計測リンクを保存するには、**計測リンクを保存**をクリックしてください。

**クリック計測リンクをコピーする手順：**

1. **計測リンクを保存**をクリックします。
2. 生成されたリンクをコピーします。

リードが対応する広告をクリックする際に使用するリンクを、パートナーに送信してください。

<div id="view-through-attribution-lookback-window" />

#### ビュースルー計測のルックバック期間

インプレッションからインストールまでの**最大時間**を設定します。このルックバック期間内で、広告インプレッション後に他の関連広告がクリックされなかった場合のみ、インストール（初回起動）がパートナーにアトリビューションされます。

この値は1～24時間でカスタマイズ可能です。

**計測リンクパラメータ：** af\_viewthrough\_lookback

参照：<Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">ビュースルーアトリビューションの詳細</Anchor>

**インプレッションの計測リンク**

<Image align="center" alt="impressions-attribution-link_en-us.png" src="https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png" />

インプレッション計測リンクは、異なるルックバック期間を除いて、クリック記録リンクと同様のアトリビューションデータを含んでいます。計測リンクを保存するには、**計測リンクを保存**をクリックしてください。

計測リンクを保存した後、生成されたリンクをコピーしてください。

**インプレッションの計測リンクをコピーする：**

1. **計測リンクを保存**をクリックします。
2. 生成されたリンクをコピーしましょう。

通常1秒以上広告が視聴された際に起動されるように、リンクをパートナーに送信します。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

* コストデータは、クリックまたはコストAPIによって連携パートナーからレポートされます。
* ベストプラクティスとして、（ROI360の契約が必要）コストAPIを実装することをお勧めします。
* コストAPIにはクリック数とインプレッション数のレポートが含まれています。サポートされているディメンション、指標、機能の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">アドネットワークコスト連携に関する表</Anchor>を参照してください。

<div id="note-2" />

> 📘 **注**
>
> 広告主が代理店運用でキャンペーンを実行する場合は、代理店が適切な広告媒体とのコスト連携設定を行います。そうでなければ、広告主と代理店が同じアプリで同じ認証情報を使ってパートナーとの連携を行うと、コストデータが重複してしまいます。

<div id="enabling-cost-data-by-api" />

#### APIによるコストデータの有効化

**コストAPI**を有効にする方法：

* <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">これらの連携手順</Anchor>に従ってください。

<div id="cost-data-sync-status" />

#### コストデータ同期ステイタス

<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiのステータス">コストAPIのステータス</Anchor>と、AppsFlyerがコスト（および広告収益）連携ステータスのダッシュボード、または個々のアドネットワークのダッシュボードのいずれかで、一致するコストデータを引き出すことができた最終時刻が表示されます。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

アプリ内で広告を表示する媒体として機能している場合、広告収益機能により、ユーザーを呼び込んだメディアソースに広告収益をアトリビューションきます。参照：<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution">広告収益のアトリビューションについて</Anchor>

<div id="enable-ad-revenue-attribution" />

#### 広告収益のアトリビューションを有効にする

1. パートナーがサポートしている方法（<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#list-of-ad-revenue-integrated-partners">集計またはユーザーレベルのアトリビューション</Anchor>）を確認してください。
2. <Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#実装">広告収益連携ガイド</Anchor>の適切な方法に従ってください。

<div id="ad-revenue-api-status-messages" />

#### 広告収益APIステータスメッセージ

| ステータス | 備考／必要なアクション |
| --- | --- |
| アクティブ | 接続が有効で、データを取得中です。 |
| 取得するデータが見つかりませんでした。 | 接続が成功しました。パートナーにはこのアプリに関連するデータがありません。 |
| パートナーAPIが応答しません。AppsFlyerサポートに連絡してください。 | パートナーのサーバーがAppsFlyerに応答していません。 |
| 資格情報が無効です。更新された資格情報を入力してください。 |  |
| 問題が発生しました。AppsFlyerサポートに連絡してください。 | 技術的な問題があります。 |
| パートナーデータがまだ準備されていません。問題が解決しない場合は、AppsFlyerサポートに連絡してください。 |  |
| データは処理中で、まもなく利用可能になります。 | 現在、パートナーから受け取ったデータを処理中です。データは管理画面とレポートで利用できるようになります。 |
| データが正常に取得されませんでした | このステータスがさらに1時間続く場合は、AppsFlyerサポートに連絡してください。 |

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

アドネットワークと代理店に、データへのアクセスやさまざまなアクションを行うための特定の権限を付与します。

* 権限を付与するために、パートナーとの連携を有効にする必要はありません。
* **代理店によって設定されたアドネットワーク：** 代理店によってパートナー設定が行われた場合、広告主はアドネットワークのアクティベーションステータスや付与された権限を表示できません。
* パートナーとの関係が代理店としてのみである場合は、**代理店権限**を使用し、**アドネットワーク権限**は利用しないでください。代理店権限のトグルをオンにすると、代理店が広告ネットワークの権限を制御できるようになります。詳細については、 <Anchor target="_blank" href="/partners/ja/docs/getting-started-agency-onboarding#マーケティング担当者からの権限を得るとはどういうことですか">「マーケティング担当者から許可を得るとはどういう意味ですか」</Anchor>の注記を参照してください。
* 現在選択されているアプリに権限が付与されます。

<div id="ad-network-permissions" />

#### アドネットワークの権限

**アドネットワークの権限**をオンにすると、アドネットワークが管理画面にアクセスできるようになり、以下の表に示すように追加の権限を付与することができます。

<div id="note-3" />

> 📘 **注**
>
> アクセス権限はアドネットワークが保有するデータに限定されます。

**アドネットワークとそのチームメンバーに権限を付与するには：**

1. **アドネットワークの権限**をオンにします。

   * アプリがアドネットワークの管理画面に表示されます。
   * アドネットワーク管理者には、<Anchor target="_blank" href="/marketers/ja/docs/manage-data-access-permissions">アプリに関する基本データを表示する</Anchor>権限があります。

   **注：** 広告ネットワークのチームメンバーは、アドネットワークによって直接管理されます。特定のチームメンバーにアクセスを与えたい場合は、アドネットワークにお問い合わせください。<Anchor target="_blank" href="/partners/ja/docs/user-management-for-ad-networks#ユーザーの作成">（詳細はこちら）</Anchor>
2. アドネットワークに付与する追加の権限を選択します：

| **権限** | **付与される機能** |
| --- | --- |
| <span id="configure-integration"></span>連携設定 | アドネットワークが、アプリ内イベントのポストバック設定を除き、連携タブでパラメーターを変更できます。 |
| <span id="configure-inapp-event-postbacks"></span>アプリ内イベントポストバックを設定 | アドネットワークはアプリ内イベントのポストバックを設定できます。これにより、ポストバック設定を作成、定義（マッピング）、変更することが可能になります。<br /><br />**注意！** この権限と連携の設定の両方が有効な場合、**アドネットワークはすべてのイベントにアクセスすることができます。これには、すべてのメディアソースからのオーガニックトラフィックと非オーガニックトラフィックが含まれます。** |
| <span id="access-retention-report"></span>リテンションとコホートレポートへのアクセス | アドネットワークは、アドネットワークによって獲得されたユーザーによって作成されたリテンション／コホートデータにのみアクセスできます。 |
| <span id="access-aggregate-loyal-users-data"></span>ロイヤルユーザーの集計データへのアクセス | <Anchor target="_blank" href="/marketers/ja/docs/about-a-loyal-user">アドネットワークは、ロイヤルユーザーの指標にアクセスできます。</Anchor> |
| <span id="access-aggregate-conversions-data"></span>集計コンバージョンデータへのアクセス | アドネットワークは、集計コンバージョンイベントの指標レポートにアクセスできます。これには、インストール、リエンゲージメント、再インストール、およびリアトリビューションが含まれます。例：<Anchor target="_blank" href="/partners/ja/docs/aggregated-campaign-performance-report-for-ad-networks">アドネットワーク向けの集計キャンペーンパフォーマンスレポート</Anchor> |
| <span id="access-aggregate-inapp-events-data"></span>アプリ内イベント集計データへのアクセス | アドネットワークは以下を行うことができます：<ul><li>アプリ内イベントデータの集計レポートにアクセスします。アクセスには、Protect360を含む選択したアプリのすべてのアプリ内イベントデータが含まれます。つまり、ポストバック設定でマッピングされたイベントに限らず、他のイベントにもアクセスできます。</li><li>広告収益化データの集計レポートにアクセスでき、これには他のメディアソースからの広告収益化イベントが含まれることがあります。</li></ul> |
| <span id="view-validation-rules"></span>検証ルールへのアクセス | <Anchor target="_blank" href="/marketers/ja/docs/implement-validation-rules-to-prevent-fraud">アドネットワークは</Anchor>検証ルールの詳細を表示できます。 |
| <span id="access-aggregate-revenue-data"></span>総収益データへのアクセス | このアドネットワークは、アプリ内データおよび広告収益データの集計レポートにアクセスできます。これらデータは、アドネットワークによってもたらされたユーザーによるものです。**注記：** この権限では、広告収益パートナーの特定は直接行われません。ただし、収益化イベント名にパートナー名を含める場合、収益化ネットワークのIDが意図せず明らかになる可能性があります。 |
| <span id="use-ad-spend-ingestion"></span>広告費用取り込みを利用する | アドネットワークは以下を行うことができます：<ul><li><Anchor target="_blank" href="/marketers/ja/docs/import-cost-data">コストインポート画面へのアクセス</Anchor>この画面では、権限を持つアプリのみが表示されます。</li><li>コストファイルを取り込み用に送信します。</li></ul> |
| <span id="access-protect360-dashboard-raw-data"></span>Protect360管理画面とローデータへのアクセス | アドネットワークは以下を行うことができます：<ul><li>Protect360管理画面（<Anchor target="_blank" href="/marketers/ja/docs/basic-fraud-detection-and-insights-with-protectlite-dashboard-and-reporting">ProtectLITE</Anchor>を含む）にアクセス</li><li>契約プランに含まれている場合、Protect360、検証ルール、ローデータへのアクセス/span>ProtectLITEにはローデータへのアクセスは含まれません。</li></ul>**注意：** Protect360の契約がある場合、アドネットワークは管理画面全体を確認できます。Protect360サブスクリプションがない場合、ライト管理画面を利用できます。 |
| <span id="access-ad-revenue-raw-data"></span>広告収益データのローデータへのアクセス | <Anchor target="_blank" href="/partners/ja/docs/ad-revenue-signals-for-ua-ad-networks">アドネットワークは</Anchor><Anchor target="_blank" href="/partners/ja/docs/ad-revenue-signals-for-ua-ad-networks">広告収益データにアクセスし、ユーザー獲得の最適化に利用できます。  <br />**注意：** この権限は、ROI360のご契約があるアプリでのみ利用可能です。</Anchor> |

<div id="agency-permissions" />

#### 代理店の許可

参照：権限付与された場合、<Anchor target="_blank" href="/partners/ja/docs/getting-started-agency-onboarding#マーケティング担当者からの権限を得るとはどういうことですか">代理店アカウントで何ができるか</Anchor>

<div id="important-1" />

> 🚧 **重要！**
>
> 代理店と連携する場合、統合パートナーをオフにしても、そのパートナーにリンクされている代理店の特定の属性情報機能が自動的に無効になるわけではありません。
>
> 代理店向けのこれらの機能を完全に無効化するには、広告主はパートナーを無効化する前に、以下の設定を手動でオフにする必要があります。
>
> 1.インストール：ビュースルーアトリビューション
> 2.クロスプラットフォームの同等アトリビューション優先度
>
> これらのトグルを無効にした後で初めて、広告主はパートナーの無効化に進むべきです。
>
> **注記：** 広告主がこれらの設定をオフにせずにパートナーを無効化した場合、代理店はこれらのアトリビューション機能を引き続き使用する可能性があります。

**注意：** この設定が無効になっている間に発生した代理店経由のインストールは、代理店の成果と計測されず、代理店アカウントの管理画面とデータには表示されません。詳細：<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation#代理店権限">代理店アカウントのアクティベーションについて</Anchor>

**代理店に権限を付与するには：**

1. **代理店の権限**をオンにします。
2. 代理店に付与する権限を選択してください：

| **権限** | **付与される機能** |
| --- | --- |
| <span id="change-advanced-privacy-configuration"></span>高プライバシー設定の変更 | 代理店アカウントでアドネットワークの<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">高プライバシーデータ共有</Anchor>を変更できます。   <br />**注：** この権限はTikTok for BusinessおよびSnapchatには適用されません。これらの連携では、広告主の設定と一致するように、高プライバシー設定がグレーアウトされます。 |
| <span id="access-retention-and-cohort-reports"></span>リテンションとコホートレポートへのアクセス | 代理店は代理店が連れてきたユーザーによって作成されたリテンション/コホートデータにのみアクセス可能です。 |
| <span id="access-aggregate-organic-data"></span>集計オーガニックデータへのアクセス | 代理店は集計されたオーガニックデータにアクセスすることができます。 |
| <span id="view-validation-rules::6872643b"></span>検証ルールを表示 | 代理店は検証ルールの詳細を確認できます。 |
| <span id="add-validation-rules"></span>検証ルールを追加 | 代理店は検証ルールを追加および編集可能です。検証ルールの**表示**がオンになっているときに利用可能です。   <br />**注記**：代理店は広告主が作成したルールを編集することはできません。 |
| <span id="access-rawdata-reports"></span>ローデータレポートへのアクセス | 代理店は代理店に起因するトラフィックのローデータレポートにアクセス可能です。広告主は代理店がレポート内で確認できるイベントを制限できません。 |
| <span id="access-protect360-dashboard-raw-data::dd9829fd"></span>Protect360管理画面とローデータへのアクセス | 代理店は次のことができます：<ul><li>Protect360集計管理画面へのアクセス</li><li>ご契約プランに含まれている場合、Protect360、検証ルール、ローデータへのアクセス</li></ul>**注記：** 広告主が代理店を通じてアドネットワークと連携する場合、アドネットワークと代理店の両方がデータにアクセスできるようにするには、広告主は AppsFlyerに代理店とアドネットワークの両方を連携し、彼らにデータへのアクセスを許可しなければなりません。仮に代理店のみが権限付与をされている場合には、アドネットワークはP360のデータへアクセスできないので注意してください。 |
| <span id="configure-inapp-event-postbacks::8743ba60"></span>アプリ内イベントポストバックを設定 | 代理店は、選択した特定のイベントのアプリ内イベントポストバックを設定できます。<ul><li>**イベントを追加：** ドロップダウンメニューから、代理店に権限を付与するイベントを選択します。</li></ul>選択したイベントに適用できるオプションは次のとおりです。<ul><li>**イベントの収益を送信：** オンにすると、代理店はイベントの金銭的価値を含めて送信する設定が可能です。</li><li>送信オプション<ul><li>**このパートナーのみ：** このオプションを選択すると、代理店は自社がもたらしたトラフィックに関連するイベントに対してのみポストバックを送信できます。</li><li>**オーガニックを含むすべてのメディアソース：** 選択すると、全てのメディアソース、代理店、及びオーガニックユーザーのイベントにポストバックを設定できます。</li></ul></li></ul> |

参照：<Anchor target="_blank" href="/partners/ja/docs/about-agency-accounts#代理店のマーケターデータへのアクセス">代理店との連携における詳細</Anchor>

</Accordion>

<div id="test-the-integration" />

## 連携テスト

パートナーとの連携を完了し、新しく追加されたパートナーとキャンペーンを実行する前に、連携のテストを行うことが重要です。セットアップ中はミスが発生しやすいです。事前にテストを行うことで、多大なリソースを費やした後にアトリビューションデータが欠落しているか誤っていることを確認するリスクを回避できます。

<div id="note-4" />

> 📘 **注**
>
> 連携をテストする前に、まず、<Anchor target="_blank" href="/marketers/ja/docs/testing-the-sdk-integration-for-marketers">オーガニックおよび非オーガニックインストールを含む基本的なSDK連携のテスト</Anchor>を行ってください。

<div id="test-the-attribution-link-for-nonsrns" />

<Accordion title="非SRNの計測リンクをテスト">

連携されたアドネットワークの99.5%に当たる非SRNアドネットワークは、AppsFlyerの計測リンクを使用します。同様に、オウンドメディアの計測も、AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLinkリンク</Anchor>を用いて行われます。

正確なアトリビューションは計測リンクのパラメーターに依存するため、非SRNアドネットワークまたはカスタム計測リンクを用いてキャンペーンを開始する前にこれらのリンクをテストしてください。

**計測リンクをテストするために：**

1. [計測リンク](/docs/set-up-an-integrated-partner#attribution-link-tab)を作成します。
2. 新しい計測リンクを、<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">登録された</Anchor>テストデバイスに送信します。（メールまたはQRコードを使用）
3. リンクをクリックし、アプリストアにリダイレクトされることを確認してください。
4. アプリをインストールします。
5. アプリを起動します。
6. インストールがパートナーのメディアソース名の下にAppsFlyer管理画面で表示されるか確認してください。管理画面にインストールが表示されるまで最大30分待つ必要があります。
7. オーバービュー画面上部の**メディアソースフィルター**でパートナーを選択して、キャンペーンレベルまでドリルダウンし、インストールが正しいキャンペーン名に表示されることを確認します。
8. 必要に応じてさらにドリルダウンし、広告セットや個々の広告レベルも確認してください。

</Accordion>

<div id="test-the-srn-integration" />

<Accordion title="SRN連携のテスト">

Meta広告、Apple Search Ads、Google AdsなどのSRNは、アトリビューションのために外部アトリビューションリンクに依存しません。代わりに、SRNはAppsFlyerからクエリを受け取り、自らアトリビューションを行い、結果を返します。よって、通常のアドネットワークのようにネットワークのシステムとは別に連携をテストすることは現実的ではありません。各SRNと連携項目を個別にテストする必要があります。

**SRN連携のテスト：**

1. <Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#srn媒体">特定のSRNセットアップガイド</Anchor>に基づき、AppsFlyerで完全なSRNセットアップを行います。
2. SRNパートナーと協力し、新しい低予算キャンペーンを実行します。
3. パートナーの管理画面で新規インストールが表示された際、AppsFlyer管理画面でそのインストールがパートナーのメディアソース名の下に表示されるか確認します。
4. オーバービュー管理画面で**メディアソースフィルター**を使いパートナーを選択して、キャンペーンレベルまでドリルダウンし、インストールが正しいキャンペーン名で表示されることを確認します。管理画面にインストールが表示されるまで最大30分待つ必要があります。
5. 必要に応じてさらにドリルダウンして、広告セットや個々の広告レベルを確認してください。

すべてが順調であれば、パートナーと共に新たな高予算キャンペーンを実行できます。SRNパートナーごとに1回の連携テストで十分です。つまり、キャンペーンごとのテストは不要です。

</Accordion>

<div id="test-the-raw-data" />

<Accordion title="ローデータのテスト">

AppsFlyerのご契約プランにローデータへのアクセスが含まれる場合、ローデータのテストをする必要があります。

**ローデータのテスト：**

1. 前述のテストを行った後で、AppsFlyer管理画面左メニュー **エクスポート** > <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">**ローデータ出力**</Anchor>に進みます。
2. テスト対象のメディアソースを選択します。
3. インストールから最大15分待ってからインストールレポートをダウンロードしてください。
4. パートナーからのインストールレコードが存在し、メディアソース、キャンペーン名、タッチ時間とタイプ、デバイスID（該当する場合）、代理店名（レポート内では「パートナー」と表記）などのパラメーターを含んでいることを確認してください。

<div id="important-2" />

> 🚧 **重要！**
>
> 一部のアドネットワークでは、ローデータをユーザーレベルで収集するために特別な操作が必要です。
>
> 管理画面に新しいインストールが表示されているが、ローデータに表示されない場合は、アドネットワークの特定のサポートガイド（例： <Anchor target="_blank" href="/marketers/ja/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies#do-you-make-twitters-raw-data-available-to-agencies">X広告</Anchor>）を参照してください。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 01H80XGTBQ6MAK3VG0X6QMAYMP=%E6%A6%82%E8%A6%81 01H80XGTBQPPZV7WR5JBHQFB0B=partner-types-in-the-ecosystem 01H80XGTBQ4CPMBRVSMM7TD4VD=partners-in-the-marketplace invite-new-partners-to-appsflyer=appsflyer%E3%81%AB%E6%96%B0%E3%81%97%E3%81%84%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%8B%9B%E5%BE%85%E3%81%99%E3%82%8B 01H80XGTBQRJ78XCGNZBTJVYEQ=appsflyer%E3%81%AB%E6%96%B0%E3%81%97%E3%81%84%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%8B%9B%E5%BE%85%E3%81%99%E3%82%8B 01H80XGTBQ8VF6V9WARZRECWVR=your-integrated-partners 01H80XGTBQJQYD3R46H95WVVM0=%E6%B3%A8%E6%84%8F 01H80XGTBQ5BE24X219BVZBMDG=about-the-integrated-partner-page applicable-settings-tabs-per-partner-type=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%BF%E3%82%A4%E3%83%97%E3%81%94%E3%81%A8%E3%81%AE%E9%81%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AA%E8%A8%AD%E5%AE%9A%E3%82%BF%E3%83%96 01H80XGTBQPP74G38YNNYVXWP2=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%BF%E3%82%A4%E3%83%97%E3%81%94%E3%81%A8%E3%81%AE%E9%81%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AA%E8%A8%AD%E5%AE%9A%E3%82%BF%E3%83%96 set-up-a-partner-nonsrn=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9Asrn%E4%BB%A5%E5%A4%96 01H80XGTBQXNQ7SFXZ5PBQGS1V=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9Asrn%E4%BB%A5%E5%A4%96 01JDM949M75Q3BAG6M65DYMHZT=%E9%87%8D%E8%A6%81 01H80XGTBQZXZARZCM61CMG0K3=%E6%B3%A8%E6%84%8F-1 01H80XGTBQB9T22GQ7CSHS2S1X=integration-tab integration-tab-sections=%E9%80%A3%E6%90%BA%E3%82%BB%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 01H80XGTBQ0531M2RS3DH7E4Z0=%E9%80%A3%E6%90%BA%E3%82%BB%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3 d-general%20settings=d-general-settings default%20postbacks=default-postbacks 01H80XGTBQ4MPGGKSZW0D9GG9H=%E6%B3%A8 01H80XGTBRT41FGP5107G96TWC=attribution-link-tab attribution-link-parameters=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC 01H80XGTBRPENCTCRK8PPYSCGX=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC attribution-link-parameters::3874dfb8=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC-1 01H80XGTBR8630SEV80K9RD6V9=%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC-1 retargeting-settings=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E8%A8%AD%E5%AE%9A 01H80XGTBRT57QMPRENYSS81Z3=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E8%A8%AD%E5%AE%9A clickthrough-attribution=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC 01H80XGTBREZTJ6B0Y08JCKN1E=%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC viewthrough-attribution-lookback-window=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 01H80XGTBRXC1YYX4FW94NDR2Z=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 01H80XGTBRERTJ9XHGDV416T7V=cost-tab 01H80XGTBR54TQ0DNY1JR36GXN=%E6%B3%A8-1 enabling-cost-data-by-api=api%E3%81%AB%E3%82%88%E3%82%8B%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 01H80XGTBRV6BHWS76HWHK933M=api%E3%81%AB%E3%82%88%E3%82%8B%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 cost-data-sync-status=%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E5%90%8C%E6%9C%9F%E3%82%B9%E3%83%86%E3%82%A4%E3%82%BF%E3%82%B9 01H80XGTBRPWREFYFXA0A6VD47=%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E5%90%8C%E6%9C%9F%E3%82%B9%E3%83%86%E3%82%A4%E3%82%BF%E3%82%B9 01H80XGTBRJ1AKX2Q7WPXFVA49=ad-revenue-tab enable-ad-revenue-attribution=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B 01H80XGTBRHE9PPRA9X46M4TGZ=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B ad-revenue-api-status-messages=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8Aapi%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8 01H80XGTBRNT4K4ZNPKVV25ESJ=%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8Aapi%E3%82%B9%E3%83%86%E3%83%BC%E3%82%BF%E3%82%B9%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8 01H80XGTBRGXS97JMG45QR4BEQ=permissions-tab ad-network-permissions=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AE%E6%A8%A9%E9%99%90 01H80XGTBRS9BTT2F8F95BCE9Z=%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AE%E6%A8%A9%E9%99%90 h_01HGFD78GRX9P2G58W21QZN4X7=%E6%B3%A8-2 agency-permissions=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%B1%E5%8F%AF 01H80XGTBRTVP407AAA77N090E=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%B1%E5%8F%AF h_01KC9MDDRPTB05PV6NCGZVFRMJ=%E9%87%8D%E8%A6%81-1 test-the-integration=%E9%80%A3%E6%90%BA%E3%83%86%E3%82%B9%E3%83%88 01H80XGTBSEWPHCPQF29XD6Y4W=%E9%80%A3%E6%90%BA%E3%83%86%E3%82%B9%E3%83%88 01H80XGTBSTHG2FC2M31F83RGK=%E6%B3%A8-3 01H80XGTBS4P06757QXHDKYAHT=test-the-attribution-link-for-nonsrns 01H80XGTBS2K9SPQ1MTAV7GP2H=test-the-srn-integration 01H80XGTBSTBV4RC3V279WNNB1=test-the-raw-data 01H80XGTBSN0VAX76XW9Y77T04=%E9%87%8D%E8%A6%81-2" />
