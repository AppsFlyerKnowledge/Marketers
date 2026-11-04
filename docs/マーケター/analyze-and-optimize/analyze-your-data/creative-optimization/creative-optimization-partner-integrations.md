---
title: Creative Optimization｜パートナー連携
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-09-14T13:52:36Z'
  edited_at: '2026-10-28T08:56:10Z'
  id: 18565403047569
  locale: ja
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/ja/articles/18565403047569
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** パートナー連携を設定し、すべてのクリエイティブデータをCreative Optimizationへ自動的に取り込みます。

![Creative integrations New.jpg](https://files.readme.io/2bfead93dbaac902956ea4379e3f360120d59e7454be354c567b2f182382ab2d-20130430776337.jpg)

<div id="about-partner-integrations" />

## パートナー連携について

パートナー連携では、そのパートナー経由で配信するキャンペーンのクリエイティブを、<Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-guide">Creative Optimization</Anchor>へスムーズかつ継続的に取り込みます。

<div id="data-availability" />

### データの利用開始と更新

パートナー連携を追加すると、以下の処理が行われます。

* 過去90日間のクリエイティブデータとAppsFlyerのパフォーマンスデータを遡って取得します。通常、24時間以内にCreative Optimizationでデータを確認できるようになります。
* その後も、連携済みパートナーから毎日2回、継続的にクリエイティブデータを取得します。取得したデータを取り込み、アトリビューション、広告費、クリック、インプレッション、収益などのAppsFlyerのパフォーマンスデータと照合します（AppsFlyerのパフォーマンスデータは1時間ごとに更新されます）。 **Creative Optimizationダッシュボードは、上記のすべての処理で得られたデータをまとめて表示し、1日1回更新されます（UTC＋10）**（過去90日間のすべてのクリエイティブデータが更新されます）。

<div id="note" />

> 📘 **注意**
>
> AppsFlyerのコストデータ（ROASなど）を見るには、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview">ROI360のご契約</Anchor>が必要です。

<div id="media-partner-integrations" />

## メディアパートナーとの連携

本セクションでは、各パートナー連携の設定方法について説明します。

<div id="adikteev" />

<Accordion title="Adikteev">

**前提条件：**

* 連携に必要な認証情報：
  * メールアドレス（Adikteevのユーザー名）
  * Adikteevのパスワード
  * **注意：** Adikteevの管理画面にアクセスする際と同じ認証情報を使用する必要があります。
* Adikteevからすべてのコストデータを取得するには、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview">ROI360</Anchor>の連携を設定したユーザーが、Creative Optimizationの連携も設定する必要があります。

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の  ⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Adikteev**を選択します。
4. プロモーション対象のアプリを選択します。
5. メールアドレスとパスワードを入力します。
6. **保存**をクリックします。

**注意：** Adikteevは、Trademob（trademob\_int）という名称でも知られています。

</Accordion>

<div id="adjoe" />

<Accordion title="Adjoe">

**前提条件：**

* 連携に必要な認証情報：
  * トークン  
    Adjoeのアカウントマネージャーに連絡して、トークンを入手してください。参照：<Anchor target="_blank" href="https://drive.google.com/file/d/16zMpKbRLmTLU-plnodELGAHZVe0CuC_F/view">Adjoeのドキュメント</Anchor>

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Adjoe GmbH**を選択します。
4. プロモーション対象のアプリを選択します。
5. トークンを入力します。
6. **保存**をクリックします。

</Accordion>

<div id="applovin" />

<Accordion title="AppLovin">

**前提条件：**

* 連携対象アプリの広告アカウントへのアクセス権限。**注意**：AppLovinの認証は、アカウント管理者が行う必要があります。
* AppLovinの**アカウントID**、**キャンペーン管理APIキー**、**レポートAPIキー**が必要です。これらはAppLovin Axonの管理画面で取得できます（右上のアカウントをクリックし、キーを選択します）。

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。

   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。

   ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **＋新規連携**をクリックします。
3. **パートナー**リストで、**AppLovin**を選択します。
4. プロモーション対象のアプリを選択します。
5. AppLovinの**アカウントID**、**キャンペーン管理APIキー**、**レポートAPIキーを入力します。**
6. 続いて**保存**をクリックします。

<div id="note-1" />

> 📘 **注意**
>
> AppLovinのアセット単位のレポートAPIが返すのは、前日分のデータのみです。過去に遡ったデータの取得には対応していません。このため、連携を有効にすると、AppsFlyerは有効化した日以降のアセット単位のデータ収集を開始します。データの対象範囲は徐々に広がり、通常は有効化から30日以内に全体をカバーするようになります。

</Accordion>

<div id="google-ads" />

<Accordion title="Google Ads">

**前提条件：**

* 連携対象アプリの広告アカウントに対する管理者権限。
* Googleからすべてのクリエイティブデータを取得するには、<Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview">ROI360</Anchor>の連携を設定したユーザーが、Creative Optimizationの連携も設定する必要があります。 ROI360のご契約がない場合は、Google AdWordsにおけるすべての関連アプリと広告アカウントの管理者権限が必要です。

**注意：**

* Google Adsとの連携はユーザー単位のため、複数のユーザーが同時にそれぞれの連携を有効にできます。

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **＋新規連携**をクリックします。
3. **パートナー**リストをクリックし、<strong>Google Ads（AdWords）</strong>を選択します。
4. プロモーション対象のアプリを選択します。
5. **Googleにログイン**をクリックします。 **Googleでログインのウィンドウ**が開きます。
6. Googleへのログインを完了し、権限を付与します。 AppsFlyerがすべてのデータを取得できるよう、必要な権限をすべて付与することをお勧めします。
7. **保存**をクリックします。

**注意：** 対応しているのは、UACキャンペーン（ACi、ACe、ACpre）の広告タイプのみです。非対応の広告タイプのデータは、Creative Optimizationでは広告単位でのみ利用できます（クリエイティブ単位では利用できません）。

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

**前提条件：**

* 連携に必要なironSourceの認証情報：
  * シークレットキー
  * リフレッシュトークン
  * <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/ios/authentication/#step-1">認証情報の取得方法</Anchor>を確認してください。
* ironSourceのAdministrator（管理者）またはContributor（コントリビューター）のユーザーロール。詳細：<Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/air/user-management/#step-1">ユーザー権限の設定方法について</Anchor>

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**ironSource**を選択します。
4. プロモーション対象のアプリを選択します。
5. シークレットキーとリフレッシュトークンを入力します。
6. **保存**をクリックします。

**注意：** 一部の広告タイプは非対応のため、そのデータはCreative Optimizationでは広告単位でのみ利用できます（クリエイティブ単位では利用できません）。サポートされていない広告タイプには、オファーウォール広告が含まれます。

</Accordion>

<div id="liftoff" />

<Accordion title="Liftoff">

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Liftoff**を選択します。
4. プロモーション対象のアプリを選択します。
5. Liftoffの担当者へ連絡して、LiftoffレポートAPIのユーザー名とパスワードを入手します。
6. **保存**をクリックします。

</Accordion>

<div id="facebook-ads" />

<Accordion title="Meta Ads">

**前提条件：**

* 連携対象アプリの広告アカウントへのアクセス権限。**注意**：Meta Adsとの連携はユーザー単位のため、複数のユーザーが同時にそれぞれの連携を有効にできます。
* 自社または外部のFacebookページに表示されるクリエイティブを取得するには、Facebookビジネスセンターの管理者が、Creative Optimizationとの連携を設定するユーザーに必要な権限を付与していることを確認してください。

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Meta Ads**を選択します。
4. プロモーション対象のアプリを選択します。
5. **Meta Adsでログイン**をクリックします。
6. ログインを完了し、権限を付与します。**注意**：AppsFlyerがすべてのデータを取得できるよう、必要な権限をすべて付与することをお勧めします。
7. **保存**をクリックします。

**注意：**

* Metaのフレキシブル広告はレポート用に1つのアセットのみを提供するため、広告内で最もパフォーマンスが高いアセットに関連するデータのみが表示されます。
* 一部の広告タイプは非対応のため、そのデータはCreative Optimizationでは広告単位でのみ利用できます（クリエイティブ単位では利用できません）。サポートされていない広告タイプ：カタログ/ DPA

</Accordion>

<div id="mintegral" />

<Accordion title="Mintegral">

**前提条件：**

* Mintegral連携に必要な認証情報：
  * APIキー
  * アクセスキー
  * <Anchor target="_blank" href="https://adv-new.mintegral.com/doc/en/guide/introduction/register.html">認証情報の取得方法</Anchor>を確認してください。

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Mintegral**を選択します。
4. プロモーション対象のアプリを選択します。
5. **APIキー**と**シークレットキーを入力します。**
6. **保存**をクリックします。

</Accordion>

<div id="moloco" />

<Accordion title="Moloco">

**前提条件：**

* クリエイティブを取得するには、Molocoの<Anchor target="_blank" href="https://help.moloco.com/hc/en-us/articles/360050566173-Invite-and-manage-users">Workplace OwnerまたはAd Account Owner</Anchor>のロールが必要です。
* MolocoのAPIキーを取得できること。

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Moloco**を選択します。
4. プロモーション対象のアプリを選択します。
5. Moloco APIキーを入力してください。
6. **保存**をクリックします。

**注意：**

* 一部の広告タイプは非対応のため、そのデータはCreative Optimizationでは広告単位でのみ利用できます（クリエイティブ単位では利用できません）。サポートされていない広告タイプには、CTV広告が含まれます。

</Accordion>

<div id="personaly" />

<Accordion title="Persona.ly">

**前提条件：**

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Persona.ly**を選択します。
4. プロモーション対象のアプリを選択します。
5. Persona.lyの**APIキー**を入力します（Persona.lyアカウントから取得できます）。
6. **保存**をクリックします。

</Accordion>

<div id="reddit" />

<Accordion title="Reddit">

**前提条件：**

* クリエイティブを取得するには、RedditのCreator（クリエイター）またはAdmin（管理者）のロールが必要です。

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Reddit**を選択します。
4. プロモーション対象のアプリを選択します。
5. **Redditにログイン**をクリックします。
6. ログインを完了し、権限を付与します。**注意**：AppsFlyerがすべてのデータを取得できるよう、必要な権限をすべて付与することをお勧めします。
7. **保存**をクリックします。

</Accordion>

<div id="remerge" />

<Accordion title="Remerge">

**前提条件：**

* 連携に必要な認証情報（**注意**：Remergeの管理画面にアクセスする際と同じ認証情報です。 <Anchor target="_blank" href="https://help.remerge.io/hc/en-us/articles/115003440434-Remerge-Reporting-API">Remergeのドキュメントを参照してください</Anchor>）：
  * メールアドレス
  * パスワード

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Remerge**を選択します。
4. プロモーション対象のアプリを選択します。
5. メールアドレスとパスワードを入力します。
6. **保存**をクリックします。

</Accordion>

<div id="revx" />

<Accordion title="RevX">

**前提条件：**

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**RevX**を選択します。
4. プロモーション対象のアプリを選択します。
5. RevXの**APIキー**を入力します（APIキーの取得については、RevXのアカウントマネージャーに直接お問い合わせください）。
6. **保存**をクリックします。

</Accordion>

<div id="smadex" />

<Accordion title="Smadex">

**前提条件：**

* 連携に必要なSmadexの認証情報（**注意：** これらは、Smadexダッシュボードにアクセスするために使用されるアカウント情報と同一の認証情報です）：
  * メールアドレス
  * パスワード

**連携を追加するには：**

1. **Creative Optimizationにログイン**し、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Smadex**を選択します。
4. プロモーション対象のアプリを選択します。
5. 必要な認証情報を入力します。
6. **保存**をクリックします。

</Accordion>

<div id="snap" />

<Accordion title="Snapchat">

**前提条件：** 連携させたい関連アプリの広告アカウントの権限が必要となります。**注意**：Snapchatとの連携はユーザー単位のため、複数のユーザーが同時にそれぞれの連携を有効にできます。

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Snapchat**を選択します。
4. プロモーション対象のアプリを選択します。
5. **Snapchatでログイン**をクリックします。**ウィンドウ**が開きます。
6. ログインを完了し、権限を付与します。 AppsFlyerがすべてのデータを取得できるよう、必要な権限をすべて付与することをお勧めします。
7. **保存**をクリックします。

**注意：** 一部の広告タイプは非対応のため、そのデータはCreative Optimizationでは広告単位でのみ利用できます（クリエイティブ単位では利用できません）。サポートされていない広告タイプには、コレクション広告が含まれます。

</Accordion>

<div id="tiktok" />

<Accordion title="TikTok">

**前提条件：**

* 連携対象アプリの広告アカウントへのアクセス権限。**注意**：TikTokとの連携はユーザー単位のため、複数のユーザーが同時にそれぞれの連携を有効にできます。
* Spark Adsのクリエイティブデータを取得するには、TikTok Business Centerの管理者が、Creative Optimizationとの連携を設定するユーザーに必要な権限を付与していることを確認してください。

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**TikTok**を選択します。
4. プロモーション対象のアプリを選択します。
5. **TikTokでログイン**をクリックします。**ウィンドウ**が開きます。
6. ログインを完了し、権限を付与します。 AppsFlyerがすべてのデータを取得できるよう、必要な権限をすべて付与することをお勧めします。
7. **保存**をクリックします。

<div id="notes" />

> 📘 **注意**
>
> * 2023年1月30日に、新しい**TikTok for Business—アドバンスSRN**連携`tiktokglobal_int`が追加されました。一方、**［旧］TikTok for Business**連携`bytedanceglobal_int`は段階的に縮小され、2024年3月までに廃止される予定です。詳細：<Anchor target="_blank" href="/marketers/ja/docs/bulletin-tiktok-for-business-advanced-srn">TikTokアドバンスSRN連携に関するお知らせ</Anchor>
>   * 新しい連携（tiktokglobal\_int）が連携された後も従来のレガシー連携（bytedanceglobal\_int）がまだアクティブな場合、Creative Optimizationではパフォーマンスデータが両方のネットワークから取得されるため、重複が生じます。
>   * AIが実際のアセットを識別するため、クリエイティブが重複することはありません。
>   * 旧連携を削除しても、製品内の過去のデータは削除されません。
>   * 必要なデータをすべて連携するには、TikTok SRNの接続ユーザーが関連する権限を持っている必要があります（広告アカウントの管理者を推奨）。
> * 一部の広告タイプは非対応のため、そのデータはCreative Optimizationでは広告単位でのみ利用できます（クリエイティブ単位では利用できません）。サポートされていない広告タイプには、コレクション広告、ショッピング広告などがあります。

</Accordion>

<div id="unity-ads" />

<Accordion title="Unity Ads">

**前提条件：**

* 連携に必要なUnityサービスアカウント認証情報：
  * キーID
  * シークレットキー
  * 組織コアID

[認証情報の取得手順を参照してください。](/docs/creative-optimization-partner-integrations#認証情報の取得方法)

* Unityで以下のサービスアカウント（組織）ロールが選択されていること。
  * クリエイティブを取得するには、**Advertise API Admin**ロールが必要です。
  * クリエイティブに加えてUnityの指標を取得するには、**Advertisers API Stats Viewer** ロールが必要です。<Anchor target="_blank" href="https://services.docs.unity.com/statistics/#section/Migrating-from-the-previous-version-of-the-API/Query-parameters">詳細はこちら</Anchor>

**注意：** これらのロールを利用できない場合は、Unity Adsのカスタマーサクセスマネージャーにお問い合わせください。

<div id="instructions-for-retrieving-the-credentials" />

#### 認証情報の取得方法

**キーIDとシークレットキーを取得するには：**

1. Unity Adsにログインします。
2. メインのメニューサイドパネルで、**Administration** > **Service Accounts**をクリックします。
3. 対象のサービスアカウントをクリックします。
4. **＋Add key**をクリックします。  
   キーIDとシークレットキーが表示されます。
5. **キーID**と**シークレットキー**をコピーします。  
   ![Unity get Key ID & Secret key image.jpg](https://files.readme.io/9c4d1b1e0e476546b8f8be3a7375c610c48db6f94344a3dbe48277a6d115f52e-20344146224401.jpg)

**組織コアIDの**<Anchor target="_blank" href="https://services.docs.unity.com/advertise/v1/index.html#section/General-Information/Resource-IDs-Used-in-the-API-Calls">**取得方法：**</Anchor>

1. Unity Ads画面で、サイドメニューの**Products**をクリックします。
2. **Grow**をクリックします。  
   ![Unity Org ID step 1 cropped.jpg](https://files.readme.io/5e8d2f54f5999c58b2e2b3591ae889f5051cae4073aa6c5ef17e16da6a60131f-22859368875153.jpg)
3. **Unity Ads User Acquisition**をクリックします。  
   <Image alt="Unity Org ID step 2 cropped.jpg" src="https://files.readme.io/07a1c8e878a9ed7b6832012b3261866477b825d3b23e4973b8c5dadd675973e2-22859368883473.jpg" width="347px" />
4. **Settings**をクリックします。  
   ![Get Organization core ID instructions 2 arrows.jpg](https://files.readme.io/aff97bcb1c255771fc46483d8d94a2f13c7ef26c45a7fc884b1c03c83da91ae5-20344868139153.jpg)
5. **組織コアID**をコピーします。

<div id="to-select-a-service-account-organization-role" />

#### **サービスアカウント（組織）ロールの選択方法：**

1. Unityの管理画面で、**Administration**をクリックします。  
   **<Image alt="Org roles step 1.jpg" src="https://files.readme.io/b9a9258cf324cdf0c73ab9be8d1646c43d2211d23cebafa3624582e6e964851f-20347001525777.jpg" width="372px" />**
2. **Service accounts**をクリックします。
3. 対象のサービスアカウントをクリックし、**+ Manage organization roles**をクリックします。  
   **![Org roles step 2.jpg](https://files.readme.io/f72334c392a89084c22fc6c6d97cedb051b4a53de9bad1eb3722c2e0f31852de-20347023191697.jpg)**
4. **Growth**ドロップダウンメニューで、以下のサービスアカウントの組織ロールを選択します。
   * Unityの指標を取得するための**Advertisers API Stats Viewer**。
   * クリエイティブを取得するため、以下のいずれかのロールも選択します。
     * Advertise API Admin
     * Advertise API Viewer
     * &lt;0>Advertise API Creative Packs Editor0>  
       <Image alt="Org roles step 3 without role names.jpg" src="https://files.readme.io/7b46417e6389f7c3675cc6f72b33e9b2833d5c561ef1d79122ed24605533b265-20347535827217.jpg" width="471px" />
5. **保存**をクリックします。

**注意：** これらのロールにアクセスできない場合は、Unityのカスタマーサクセスマネージャーに問い合わせるか、[unityads-support@unity3d.com](mailto:unityads-support@unity3d.com)までメールを送り、必要な権限を申請してください。

<div id="to-add-a-unity-integration-to-the-creative-dashboard" />

#### **Creative OptimizationダッシュボードにUnity連携を追加するには：**

1. **Creative Optimization**ダッシュボードで、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**Unity Ads**を選択します。
4. プロモーション対象のアプリを選択します。
5. キーID、シークレットキー、組織コアIDを入力します。
6. （オプション）<Anchor target="_blank" href="/marketers/ja/docs/creative-optimization-guide#partner-metrics::e592ecd3">パートナー指標</Anchor>情報を入力して、Unity Adsによってレポートされた指標も取得します。
7. **保存**をクリックします。

</Accordion>

<div id="x-ads" />

<Accordion title="X Ads（旧Twitter Ads）">

**前提条件：**

* クリエイティブを取得するには、X AdsのAccount admin（アカウント管理者）またはAd manager（広告マネージャー）のロールが必要です。

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**X Ads**を選択します。
4. プロモーション対象のアプリを選択します。
5. **X Adsでログイン**をクリックしてください。
6. ログインを完了し、権限を付与します。**注意**：AppsFlyerがすべてのデータを取得できるよう、必要な権限をすべて付与することをお勧めします。
7. **保存**をクリックします。

</Accordion>

<div id="youappi" />

<Accordion title="YouAppi">

**前提条件：**

連携に必要なYouAppi認証情報：

* トークン  
  　**注意：** トークンを取得するには、YouAppiのアカウントマネージャーに連絡してください。詳細は、<Anchor target="_blank" href="https://support.youappi.com/knowledgebase/reporting-api-for-re-engagement/">YouAppiのドキュメント</Anchor>を参照してください。

**連携を追加するには：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮ アイコンをクリックし、**クリエイティブ連携**に移動します。  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+新規連携**をクリックします。
3. **パートナー**リストで、**YouAppi**を選択します。
4. プロモーション対象のアプリを選択します。
5. トークンを入力します。
6. **保存**をクリックします。

</Accordion>

<div id="additional-information" />

## 追加情報

<div id="creative-integrations-dashboard" />

<Accordion title="クリエイティブ連携画面">

クリエイティブ連携画面では、新しいメディアパートナー連携を追加できます。新しい連携を追加するには、[パートナーごとの具体的な手順](/docs/creative-optimization-partner-integrations#データの利用開始と更新)に従って設定します。

連携を追加すると、現在のすべての連携のステータスが、以下の列とともに表示されます。

| 列 | 説明 |
| --- | --- |
| パートナー | 連携しているパートナー名（例：Meta Ads / ironsource\_int）。パートナー列を展開すると、パートナーのさまざまな接続がすべて表示されます。たとえば、各ユーザーが独自の接続を持っている場合があります。 |
| アプリ | 連携パートナーと特定のユーザー接続ごとのアプリのリスト。 |
| 連携更新 | パートナー連携設定が最後に更新された日付。 |
| カバー率ステータス | Creative Optimizationのダッシュボードやレポートで利用できる、パートナー連携から取得したクリエイティブのパフォーマンスデータのカバー状況を示します。<ul><li>**低**：この連携に含まれるすべてのアプリでデータが不足しています。</li><li>**一部**：この連携に含まれる一部のアプリでデータが不足しています。</li><li>**高**：この連携に含まれるすべてのアプリにデータがあります。</li><li>**処理中**：ステータスの更新まで最大24時間お待ちください。</li><li>**データなし**：過去30日間、このパートナーのデータがありません。</li></ul>ステータスをクリックすると、アプリごとのカバー率ステータスの内訳が表示されます。アプリごとのステータスは、ROI360をご契約かどうかによって意味が異なります。<br /><br />**ROI360の契約がない場合：**<ul><li>**高：** 該当アプリに大量のデータが存在します。取得したクリエイティブが、過去30日間のアプリの総インストール数（AppsFlyerで計測）の85％超をカバーしていることを意味します。</li><li>**低**：アプリのデータが不足しています。取得したクリエイティブが、過去30日間のアプリの総インストール数（AppsFlyerで計測）の85％未満しかカバーしていないことを意味します。</li></ul>**ROI360の契約がある場合：**<ul><li>**高**：取得したクリエイティブが、過去30日間にAppsFlyerのROI360で計測されたコストの85％超をカバーしています。</li><li>**低**：取得したクリエイティブが、過去30日間にAppsFlyerのROI360で計測されたコストの85％未満しかカバーしていません。<br />**例**：<ul><li>AppsFlyerは、総広告費が100ドルのメディアソース「ネットワークA」のデータを取得します。</li><li>クリエイティブ1の広告費は85ドル、クリエイティブ2の広告費は15ドルでした。</li><li>AppsFlyerがクリエイティブ1のデータを取得した場合、コストの85％をカバーするため、カバー率は「高」となります。</li><li>AppsFlyerがクリエイティブ2のデータのみを取得した場合、コストの15％しかカバーしないため、カバー率は「低」となります。</li></ul></li></ul>**ROI360の契約に関係なく：**<ul><li>**処理中**：ステータスの更新まで最大24時間お待ちください。</li><li>**データ不足**：[パートナーごとの手順](/docs/creative-optimization-partner-integrations#データの利用開始と更新)に従って、連携が正しく設定されていることを確認してください。</li><li>**データなし**：過去30日間、このアプリのデータがありません。<ul><li>AppsFlyerの一般的な設定が完了し、正常に機能していることを確認してください（クリエイティブ連携以外の部分も含む）。</li><li>アプリがアクティブで、トラフィックがあることを確認してください。<br />代理店が連携を管理している場合は、[代理店向けの手順](/docs/creative-optimization-partner-integrations#agencies)に従って、連携が正しく設定されていることを確認してください。</li></ul></li></ul> |

</Accordion>

<div id="agencies" />

<Accordion title="代理店との連携">

<div id="add-an-agency-integration" />

#### 代理店連携の追加

クリエイティブダッシュボードに代理店パートナーのデータを取り込むことができます。

**代理店連携の追加：**

1. **Creative Optimization**にログインし、以下のいずれかの操作を行います。
   * 既存のパートナー連携設定がない場合は、+ **新規連携を追加**をクリックします。
   * それ以外の場合は、ダッシュボード右上の⋮アイコンをクリックし、**クリエイティブ連携**に移動します。  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. ＋新**規連携**をクリックします。
3. パートナー連携ウィンドウでパートナーとアプリを選択したら、**詳細設定：代理店**ドロップダウンをクリックし、対象の代理店を選択します。  

   <Image alt="Creative agencies.png" src="https://files.readme.io/74f0dc492bc530278687becdd0061e9c06081653b69ed525f237b97a9568e413-38395601553169.png" width="288px" />
4. **保存**をクリックします。  
   代理店連携が追加されます。

**注意：**

* ダッシュボードにクリエイティブデータを表示したい代理店ごとに、「代理店」チェックボックスを選択した個別のパートナー連携を作成する必要があります。
* 運用媒体の開示設定が有効な代理店のデータのみ利用できます。<Anchor target="_blank" href="/marketers/ja/docs/view-agency-data">詳細はこちら</Anchor>
* この連携で取得するクリエイティブデータは、対象の代理店のデータのみです。つまり、上記の例のようにパートナーとしてGoogle Adsを選択した場合でも、Google Adsで直接キャンペーンを実施している場合は、Google Ads用に追加のパートナー連携を作成する必要があります。

<div id="grant-dashboard-access-to-an-agency" />

#### 代理店へのダッシュボードのアクセス権付与

代理店がAppsFlyerの<Anchor target="_blank" href="/partners/ja/docs/about-agency-accounts">代理店アカウント</Anchor>を所持している場合、Creative Optimizationダッシュボードで自分のクリエイティブパフォーマンスデータを表示するアクセスを付与できます。これは透明性とコラボレーションを高めるのに役立つ可能性があります。

**アクセスを有効にする：**

1. AppsFlyerのサイドメニューで、**連携** > **パートナーマーケットプレイス**をクリックします。  

   **<Image alt="From Collaborate click Partner Marketplace.png" src="https://files.readme.io/96485cefae79412a680915810c16b23619f73d9109212bfc45d1c0d42c2e529a-39258887136785.png" width="33.9%" />**
2. ページ上部の検索バーから関連するパートナー代理店を検索し、パートナーをクリックします。

   <Image alt="Search bar.png" src="https://files.readme.io/f1ff34a547af45eec73e7abd41105bbab9ff12d4a2636ed4b99634985ec58044-39258887138449.png" width="1210px" />
3. パートナーページで**権限**タブに移動し、**代理店権限**を有効にします。

   <Image alt="Agency permissions.png" src="https://files.readme.io/b307601f9b41800a146c664bdd9f6d24a5398be9022801505419aebb0741162c-39258856594705.png" width="71.31%" />
4. 続いて、**Creative Optimizationダッシュボードへのアクセス**を有効にします。  

   これで、代理店は自身のダッシュボードで、共有されたクリエイティブを閲覧できるようになります。まだAppsFlyer代理店アカウントを設定していない代理店は、<Anchor target="_blank" href="/partners/ja/docs/getting-started-agency-onboarding">こちらで詳細</Anchor>を確認してください。

</Accordion>

<div id="update-credentials" />

<Accordion title="認証情報の更新">

一部のパートナー連携では、設定後にアカウント単位の認証情報を変更できません（Meta Ads、Google Ads、TikTok、AppLovinはこの制限の対象外です）。パートナーの認証情報を更新する必要がある場合：

1. **クリエイティブ連携**ページで、パートナー名の左にある展開ボタンをクリックし、そのパートナーの接続一覧を開きます。
2. 接続の右側にある<Image alt="3 dots icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="7px" />メニューアイコンをクリックし、**連携を削除**をクリックします。 ![partner-integration-side-menu.png](https://files.readme.io/43ba588af05ffb8dafa165cf5d760010d36bd8b6409f6f9f4ef131d695989ed2-18565371542033.png)
3. 更新された認証情報を使用してパートナー用の新しい連携を設定します。

</Accordion>

<div data-zendesk-anchors="about-creative-partner-integrations=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E9%80%A3%E6%90%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HAP6JQEFKAFK96WDBN0MERB6=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E9%80%A3%E6%90%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 media-partner-integrations=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8%E9%96%8B%E5%A7%8B%E3%81%A8%E6%9B%B4%E6%96%B0 h_01HEQ2QR21MZB57S6MQ5ZWZ7ZQ=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8%E9%96%8B%E5%A7%8B%E3%81%A8%E6%9B%B4%E6%96%B0 h_01K4M4JF53A3J1R5VACNVN4X8A=%E6%B3%A8%E6%84%8F h_01HC7W736NDRRAJ95Z28JS2J46=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA h_01HBAZ8724YYFVQWYV5F8F4F5S=adikteev 01H7SZ8RA055S4M11TTX1J0E55=adjoe 01H7SZ8RA0A52YQEMYX0GV44AB=applovin h_01KY4CAH2MKX650JS1R0N8X6B4=%E6%B3%A8%E6%84%8F-1 01H7SZ8RA0980TH09EP2ED9WSF=google-ads 01H7SZ8RA0DRWC76119ED96KHP=ironsource 01H7SZ8RA0428ZPRYD99GWRMK0=liftoff 01H7SZ8RA06V5BR4ABV0ZVK82Z=facebook-ads h_01JXCRAESXDAHGGJ71EB32NAPD=mintegral 01H7SZ8RA06G1W04NSEHSPSV2D=moloco h_01KRGPVZH0Z0DHEEJNP4ST5CD9=personaly 01J9V2ZJR6KYJERPR2Y2XNCREP=reddit 01H7SZ8RA0CDR1M5V2F177TG84=remerge h_01KRGPVZH00WKJ4VJN8QHAW3YS=revx h_01HZEP4F6M2W5HC76WVFP5Z5C0=smadex 01H7SZ8RA1H0Q47N1W3NST4PZW=snap 01H7SZ8RA1E221TK8VRWEF1FA4=tiktok 01H8VVCC8GW5AZ3M475XFZY9JW=%E6%B3%A8%E6%84%8F-2 01H7SZ8RA1YTA3MGVJMXVTP78Y=unity-ads instructions-for-retrieving-the-credentials=%E8%AA%8D%E8%A8%BC%E6%83%85%E5%A0%B1%E3%81%AE%E5%8F%96%E5%BE%97%E6%96%B9%E6%B3%95 h_01GT6Z998RCBQWKDC9YGPJQGN6=%E8%AA%8D%E8%A8%BC%E6%83%85%E5%A0%B1%E3%81%AE%E5%8F%96%E5%BE%97%E6%96%B9%E6%B3%95 to-select-a-service-account-organization-role=%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E7%B5%84%E7%B9%94%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%AE%E9%81%B8%E6%8A%9E%E6%96%B9%E6%B3%95 h_01GT6ZFTGKMR18DTNVX706DH1R=%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E7%B5%84%E7%B9%94%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%AE%E9%81%B8%E6%8A%9E%E6%96%B9%E6%B3%95 to-add-a-unity-connection-to-the-creative-dashboard=creative-optimization%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%ABunity%E9%80%A3%E6%90%BA%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF h_01GT6ZS52ZWY47BCT2NJVCFFEP=creative-optimization%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%ABunity%E9%80%A3%E6%90%BA%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF 01J9V2ZJSKN37WSGKA6D12MYBH=x-ads 01H7SZ8RA1E37649AAH1DNRXA9=youappi agency-integrations=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HC7WCZ143S29PGTVNFEX962Y=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 01J9WK9A78RP6BKX6860MAABFM=creative-integrations-dashboard h_01HC7WCE9EJK3NDJQE88RZ3T0Z=agencies add-an-agency-integration=%E4%BB%A3%E7%90%86%E5%BA%97%E9%80%A3%E6%90%BA%E3%81%AE%E8%BF%BD%E5%8A%A0 h_01K5PE1K1G75KEF9HXMAW9YP2F=%E4%BB%A3%E7%90%86%E5%BA%97%E9%80%A3%E6%90%BA%E3%81%AE%E8%BF%BD%E5%8A%A0 grant-dashboard-access=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%B8%E3%81%AE%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%A8%A9%E4%BB%98%E4%B8%8E h_01K5PE1WK5AE2MX235B8FA4YJ0=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%B8%E3%81%AE%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%A8%A9%E4%BB%98%E4%B8%8E 01J9WKGYM1D04ZT14EPZ13VE4P=update-credentials" />
