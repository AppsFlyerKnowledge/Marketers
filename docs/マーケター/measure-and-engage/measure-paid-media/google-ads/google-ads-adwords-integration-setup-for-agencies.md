---
title: Google Ads（AdWords）｜代理店向けの連携設定
metadata:
  keywords:
    - Google
    - AdWords
    - Advertisers
    - Agencies
    - (AdWords)
    - google ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2017-07-23T11:26:20Z'
  edited_at: '2026-10-28T09:15:31Z'
  id: 115003669983
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/115003669983
---
> **概要：** 代理店としてGoogle AdsとAppsFlyerの連携を設定する方法を説明します。

広告主と代理店の双方で、各自システムを設定していただく必要があります。以下の動画では、代理店がGoogle Adsから広告主のアプリへのモバイルトラフィックを計測し、成果に紐づけられるようにするために、広告主と代理店の双方で必要な手順を紹介します。

この設定によりAppsFlyerは、AppsFlyer管理画面上で、コンバージョンを代理店の成果に紐づけることができます。

代理店がプロセスを開始する前に、まずは広告主がGoogle Adsの連携を設定する必要があります。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers">こちら</Anchor>を参照してください。

<div id="enabling-agency-attribution-of-google-ads" />

## Google Adsの代理店による成果計測の有効化

AppsFlyerでは、Google Adsの代理店設定をサポートしています。 AppsFlyerでデータの計測を正しく行うには、広告主と代理店が個別のGoogle Adsアカウントを使用していることが重要です。

<div id="setting-up-google-ads-attribution-for-agencies" />

## 代理店向けのGoogle Ads計測設定

AppsFlyerで 代理店のGoogle Ads計測を開始するには、次のステップを実行します：

<Accordion title="動画を見る">

<Embed title="Google Ads（AdWords）｜代理店向けの連携設定" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/fzihkki0qd" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="手順を読む">

<div id="advertiser-prestep-enabling-the-agency-access-to-google-ads" />

<Accordion title="広告主の事前準備：代理店へのGoogle Adsアクセス権の付与">

**前提条件：**

* AppsFlyerで、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#代理店の許可">こちら</Anchor>の手順に従って、代理店にアプリへのアクセス権を付与します。
* AppsFlyerでGoogle Adsパートナーを<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">有効化</Anchor>します。

**広告主のリンクIDを共有するには、次の手順を実行します。**

1. Google Ads管理画面を開き、***ツール***アイコンをクリックします。

![Google_Ag_1.png](https://files.readme.io/3a1188bc11e09779076c880c1b4d5e933845ee642393ff1367b2368c1199d8a2-50897694578449.png)

2. ***リンク済みアカウント*** を選択します。

![Google_Ag_2.png](https://files.readme.io/5bf0fb06df3263bc65a4e7e78539c06f2fce552b24b2913c18e155eff56f18ad-50897658813841.png)

3. ［アプリ分析プロバイダ］でAppsFlyerを探します。[オプション] を選択します。

4. ［***別のアカウントと共有***］をクリックします。

![Google_Ag_3.png](https://files.readme.io/0659fc1f193ffc668f18f13641d07e085c94a97fb9e5c6c0f35188e1c18c632b-50897694583441.png)

5. **代理店のGoogle Adsのお客様ID**を入力します。

![Google_Ag_4.png](https://files.readme.io/cce6c7aa387f354c004682c6d46b804897654c99b3346ce6c27a2bcf43259c2e-50897694584849.png)

6. [***次へ***] をクリックします。［***招待を送信**］をクリックします。*

![Google_Ag_5.png](https://files.readme.io/d3da1850913f2c2a9b9125460cebd7e61922a177178c48cf23904d5a42445972-50897658822801.png)

広告主側で、代理店に招待リクエストが送信されたことが確認できます。代理店が招待を承認すると、ステータスが［共有中］に変わります。

Google AdsのリンクIDの共有については、<Anchor target="_blank" href="https://support.google.com/adwords/answer/7365001">こちら</Anchor>を参照してください。

![Google_Ag_6.png](https://files.readme.io/b205e5b2771a128846b22d653998da09f8d600b6b60efb6ca1e90042ffba5ee7-50897694593041.png)

</Accordion>

<div id="agency-step-1-accepting-the-link-id" />

<Accordion title="代理店の手順1：リンクIDの承認">

Google Ads管理画面にて、代理店は招待を受け取り、リンクを承認する必要があります。

![Google_Ag_7.png](https://files.readme.io/f64942b5f67d9cb3ce692380626d9b87fb43a98ce825544b84e49c36162e349d-50897694593937.png)

代理店側で、リンクのステータスが［有効］になっていることを確認できます。

![Google_ag_8.png](https://files.readme.io/e44b590d4720accfde2ac95b97b18250ba2aab07f12651749592d4ad5aa8c947-50897658832017.png)

</Accordion>

<div id="agency-step-2-setting-up-google-ads-on-appsflyer" />

<Accordion title="代理店の手順2：AppsFlyerでのGoogle Adsの設定">

代理店は、必要に応じてGoogle Adsのお客様IDを複数設定できます。

1. AppsFlyerのサイドメニューから、［**コラボレーション**］>［**パートナー連携**］を選択します。
2. **Google Ads**を検索し、選択してください。

   ![gads-search.png](https://files.readme.io/97f9abe0e6bf4e07b81341f1c0a9978f6387747b412c53f7755c53a76ba0eaeb-50897694596881.png)

   広告主によって［***パートナーを有効にする***］がオンになっており、［***リンクID***］が設定されていることを確認します。代理店向けには、これらの設定はグレー表示され変更できません。

   ![gads_agency-integration-link-id.png](https://files.readme.io/6d59ccad7fb3a4a0269b9e868e30b0b87eb23a83e07e6ef1d2603815352786bf-50897658836625.png)
3. 代理店側でGoogle Adsのお客様IDを設定します。

   代理店が広告主のアプリのキャンペーンを運用しているGoogle Adsアカウント（**サブアカウント**）のGoogle Adsのお客様IDを**すべて**入力します。

   Google Adsのお客様IDは、左上の矢印をクリックしてナビゲーションパネルを開くと確認できます。

   [![](https://files.readme.io/5cc63138208e0ba55a59b4c2514dff373e45a25f50d92f9e6d8316356d078ed3-50897658839185.png)](https://files.readme.io/5cc63138208e0ba55a59b4c2514dff373e45a25f50d92f9e6d8316356d078ed3-50897658839185.png)
4. Google Adsで配信中のリターゲティングキャンペーンを計測するには、広告主に**Google Adsのリターゲティング**を有効にするよう依頼してください。有効になると、**リエンゲージメント期間**を設定できます。

   ![gads-agency-retargeting.png](https://files.readme.io/42008f063585b0a1dff553b8391b9dca48c2a3657786c263459c717cc94b5b19-50897658842385.png)
5. Google Adsの設定値に合わせ、クリックスルー計測のルックバック期間を**30日**に設定することを推奨します。

   ![gads-click-through.png](https://files.readme.io/9bf0456ecb003e4b2750e4e5c1455d4418de00b8815ae08e9e580763948e3721-50897694603025.png)
6. Google Adsの設定値に合わせ、ビュースルー計測のルックバック期間を**1日**に設定することを推奨します。スライダーで、広告が表示されてから、そのインプレッションをこのパートナーの成果として計測できる時間数または日数を設定します。

   ![gads-view-through.png](https://files.readme.io/c26b18ff2d51ade48a9e57e0bb5097e4a0671f0ba78583cfeaa17848bebf9a34-50897658845969.png)
7. ***再インストールの計測***：
   * 再インストールを計測するには、この設定をオンにします。
   * 再インストールの計測にはインストール計測の設定値が使用されるため、ビュースルー計測の有効化やルックバック期間の設定は不要です。
8. ［***保存して閉じる***］をクリックします。

</Accordion>

<div id="agency-step-3-mapping-your-inapp-events" />

<Accordion title="代理店の手順3：アプリ内イベントのマッピング">

1. ［**アプリ内イベント**］タブをクリックします。

2. Google Adsインストール経由のみのアプリ内イベントを送信するか、すべてのアプリ内イベントをGoogleに送信するかを選択します。  
[![](https://files.readme.io/c2d22406f549db47de21beb54b7f9c8f94419702d0f78f46b2dbf0785e2ba94a-50897694609297.png)](https://files.readme.io/c2d22406f549db47de21beb54b7f9c8f94419702d0f78f46b2dbf0785e2ba94a-50897694609297.png)

3. 事前に定義されているGoogle Adsイベントを使用して、Google Adsに送信したいすべてのイベントをマップします。

[![](https://files.readme.io/036b4f1cef8fa9b537b3aeaaab3f4072a099f94b3a8bbc539838d7898185a1ad-50897694610065.png)](https://files.readme.io/036b4f1cef8fa9b537b3aeaaab3f4072a099f94b3a8bbc539838d7898185a1ad-50897694610065.png)

4. ［***保存***］をクリックします。

<div id="important" />

> 🚧 **重要！**
>
> 初回起動とアプリ内アクションをGoogle Adsにインポートすると、Google AdsとAppsFlyer管理画面の両方でコンバージョンの計測を開始できます。
>
> インポートするには、アプリを起動し、マップしたアプリ内イベントを1回以上実行する必要があります。

<div id="note" />

> 📘 **注意**
>
> * 新しいコンバージョンのステータスが「No Recent Conversion」（最近のコンバージョンなし）から、「Recording Conversion」（コンバージョンの記録中）に変更するまで最大6時間かかることがあります。
> * 代理店がMCCアカウントを使用し、その配下の複数のサブアカウントでアプリの広告を配信している場合、［**Google Adsのお客様ID**］欄にすべてのサブアカウントを設定する必要があります（上の画面例を参照）。
>   この場合、MCCアカウントのお客様IDを設定する必要はありません。

</Accordion>

<div id="step-4-measure-your-app-conversions-mandatory" />

<Accordion title="代理店の手順4：アプリのコンバージョンの計測（必須）">

（**Google Adsの管理者のみ）**

<div id="important-1" />

> 🚧 **重要！**
>
> Google Adsで新しいコンバージョンを登録するには、少なくとも1回、**アプリを起動してマッピングしたアプリ内イベントを実行する**必要があります。 iOSアプリをテストする場合、イベントを確認するにはIDFAを収集する必要があります。イベントコンバージョンがキューに追加されるまでに最大6時間かかる場合があります。キューに追加されるとインポートできるようになり、新しいコンバージョンのステータスが［最近のコンバージョンなし］から［コンバージョンの記録中］に変わります。

1. Google Adsアカウントの［**概要**］ページに戻り、［**ツールと設定**］>［**測定**］>［**コンバージョン**］に移動します。  
   [![conversions_overview_en-us__1_.png](https://files.readme.io/8e4217e0fc2d9696b9aaee3e247ce38fbd5bafd70f05101b31b4ab8de524b3cb-50897694610833.png)](https://files.readme.io/8e4217e0fc2d9696b9aaee3e247ce38fbd5bafd70f05101b31b4ab8de524b3cb-50897694610833.png)
2. [ **+ 新しいコンバージョンアクション**] をクリックします。  
   [![New_conversion_action_en-us__2_.png](https://files.readme.io/e4140f9a279c53bed9f0b576cc006bccd30fe737ea791ade47cd4d42c3e2074b-50897694612113.png)](https://files.readme.io/e4140f9a279c53bed9f0b576cc006bccd30fe737ea791ade47cd4d42c3e2074b-50897694612113.png)
3. コンバージョンタイプのリストから**アプリ**を選択し、**第三者アプリ分析ツール**を選択して、**続行**をクリックします。  
   [![select_app_en-us__3_.png](https://files.readme.io/60d68af7588d5840bd478f2d6c7513f3a93fd2c409f780e13049cc5e639f2e98-50897658853137.png)](https://files.readme.io/60d68af7588d5840bd478f2d6c7513f3a93fd2c409f780e13049cc5e639f2e98-50897658853137.png)
4. すべてのアプリの**first\_open**と、インポートする各イベントの横にあるチェックボックスをオンにします。

   <div id="note-1" />

   > 📘 **注意**
   >
   > Google Adsの**パートナーイベント識別子**が変更された場合、または [カスタム] でAppsFlyerで対応するイベント名が変更された場合は、再インポートする必要があります。


   **インポートして続行**をクリックし、**完了**をクリックします。  
   [![select_events_to_import_en-us__4_.png](https://files.readme.io/efe5458d26e6085aa0c228b98f63d37ef932e672e83ebc9050437b3b1259eea1-50897658853905.png)](https://files.readme.io/efe5458d26e6085aa0c228b98f63d37ef932e672e83ebc9050437b3b1259eea1-50897658853905.png)
5. 第三者アプリ分析ツールのコンバージョンイベントは、**コンバージョン** > **概要**ページで確認できるようになりました。イベントがリストに表示されない場合、またはGoogle Adsのコンバージョンリストから削除されている場合は、［**すべてのコンバージョンアクションを表示**］をクリックします。［**ステータス**］フィルタが表示されます。   
   [![conversions_summary_en-us__5_.png](https://files.readme.io/406121cc793f06d778192f8c8b191d7db0f11f91614cc4cf411a940ea176cd95-50897694614801.png)](https://files.readme.io/406121cc793f06d778192f8c8b191d7db0f11f91614cc4cf411a940ea176cd95-50897694614801.png)
6. ［**ステータス**］をクリックして［**すべて**］を選択すると、無効化または削除されたものを含むすべてのイベントが表示されます。  
   [![conversion_action_status__6_.png](https://files.readme.io/f1294f57798cb4222775678a496be20b57238316b03a11e9a390b5362d1878c8-50897694615313.png)](https://files.readme.io/f1294f57798cb4222775678a496be20b57238316b03a11e9a390b5362d1878c8-50897694615313.png)
7. おめでとうございます！これで、AppsFlyerでGoogle Adsモバイルキャンペーンの計測ができるようになりました！

<div id="note-2" />

> 📘 **注意**
>
> 「コンバージョンに含む」設定が、Google Adsでのキャンペーン目標に合致するようにしてください。詳細はGoogleの担当者に問い合わせるか、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">こちら</Anchor>のGoogleのドキュメントを参照してください。

</Accordion>

</Accordion>

「広告主向けGoogle Ads計測の設定」の動画は、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#広告主向けのgoogle-ads計測の設定">こちら</Anchor>から視聴できます。

広告主が複数の代理店／MCCのGoogle Adsアカウントを計測する方法は、<Anchor target="_blank" href="/marketers/ja/docs/recording-multiple-agency-mcc-google-ads-accounts">こちら</Anchor>を参照してください。

<div id="agencies-collecting-cost-clicks-and-impression-data" />

## 代理店向け：コスト、クリック、インプレッションデータの取得

代理店は、クリック数とインプレッション数を含む<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#cost-tab">コストデータを取得</Anchor>できます。

コストデータは、代理店と広告主の双方の管理画面にキャンペーンレベルで表示されます。

運用媒体の開示設定が有効な場合、広告主の管理画面ではGoogle Adsのキャンペーンにコストデータが表示されます。運用媒体の開示設定が無効な場合、代理店のキャンペーンにデータが表示されます。

<div data-zendesk-anchors="enabling-agency-attribution-of-google-ads=google-ads%E3%81%AE%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AB%E3%82%88%E3%82%8B%E6%88%90%E6%9E%9C%E8%A8%88%E6%B8%AC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HKA1J5ES5T65NT5QMY5ZGXP6=google-ads%E3%81%AE%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AB%E3%82%88%E3%82%8B%E6%88%90%E6%9E%9C%E8%A8%88%E6%B8%AC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 setting-up-google-ads-attribution-for-agencies=%E4%BB%A3%E7%90%86%E5%BA%97%E5%90%91%E3%81%91%E3%81%AEgoogle-ads%E8%A8%88%E6%B8%AC%E8%A8%AD%E5%AE%9A h_01HKA1J5ESJYS902S9Z3YY5FV9=%E4%BB%A3%E7%90%86%E5%BA%97%E5%90%91%E3%81%91%E3%81%AEgoogle-ads%E8%A8%88%E6%B8%AC%E8%A8%AD%E5%AE%9A h_01HKA1J5ESF3ZK9E9PKM9AN8C8=advertiser-prestep-enabling-the-agency-access-to-google-ads h_01HKA1J5ETKV3H3KYBEYQZMSXA=agency-step-1-accepting-the-link-id h_01HKA1J5ET2BV8GHXZS5T8KCGZ=agency-step-2-setting-up-google-ads-on-appsflyer h_01HKA1J5ETH4TTVDSP0HNK6F0Q=agency-step-3-mapping-your-inapp-events h_01HKA1J5ETK5PXYFPXPBVH0HJQ=%E9%87%8D%E8%A6%81 h_01HKA1J5ETNQ1FCBMVTQED74HG=%E6%B3%A8%E6%84%8F h_01HKA1J5ETKH9GKAX3HZMA7W57=step-4-measure-your-app-conversions-mandatory h_01HKA1J5ET210B40MPFQ79PPSN=%E9%87%8D%E8%A6%81-1 h_01HKA1J5ETNTFKKDF6NC635H3W=%E6%B3%A8%E6%84%8F-1 h_01HKA1J5ETEWJN8MH9NPWTWX0F=%E6%B3%A8%E6%84%8F-2 agencies-collecting-cost-clicks-and-impression-data=%E4%BB%A3%E7%90%86%E5%BA%97%E5%90%91%E3%81%91%E3%82%B3%E3%82%B9%E3%83%88%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97 h_01HKA1J5ETPYE7B2NFPFHA05YT=%E4%BB%A3%E7%90%86%E5%BA%97%E5%90%91%E3%81%91%E3%82%B3%E3%82%B9%E3%83%88%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E5%BE%97" />
