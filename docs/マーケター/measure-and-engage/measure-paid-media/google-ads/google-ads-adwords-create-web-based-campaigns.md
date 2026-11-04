---
title: Google Ads Web｜モバイルアプリ向けWebキャンペーンの作成
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-05-16T09:12:15Z'
  edited_at: '2026-10-28T09:15:21Z'
  id: 25096718837137
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/25096718837137
---
> **At a glance:** Google AdsからWeb経由で発生したアプリのコンバージョンを計測するため、Webキャンペーンを作成します。

> 📘 **Note**
>
> この記事では、モバイルアプリを宣伝するWebキャンペーンについて説明します。 PCまたはコンソールアプリを宣伝するキャンペーンを作成する場合は、「Google Ads Web：PCおよびコンソールアプリ向けの連携」を参照してください。

<div id="overview" />

## 概要

AppsFlyerは、WebキャンペーンでのGoogle Ads（`googleads_int`）連携に対応しています。キャンペーンの計測データとコンバージョンデータは、GoogleのOffline Conversion API（OCI）を通じてGoogleに送信されます。

この記事では、Googleの広告に接触するWebユーザーを対象に、AppsFlyerとGoogle Adsでモバイルアプリ向けのWebキャンペーンを設定する方法を説明します。

このキャンペーンのユーザージャーニーは、ユーザーが広告をクリックし、ランディングページにリダイレクトされるところから始まります。このランディングページには、計測リンクを生成するAppsFlyerのSmart ScriptまたはSmart Bannersが実装されています。

ユーザーがこれらのリンクをクリックすると、アプリストアに移動してアプリをダウンロード・インストールできます。インストールとその後のアプリ内イベントはAppsFlyerで計測され、OCIを通じてGoogle Adsに送信されます。

Googleはこのデータを使用して、広告ターゲティングの最適化、パフォーマンスの計測、カスタムオーディエンスの作成を行います。

<div id="prerequisite" />

### 前提条件

Webキャンペーン向けのGoogle Ads連携を有効にする前に、以下を準備してください。

* モバイルアプリ
* AppsFlyerのアカウント
* <Anchor target="_blank" href="/marketers/ja/docs/user-management">適切なロールまたは権限を持つAppsFlyerユーザー</Anchor>と、対象アプリへのアクセス権

<div id="create-a-google-ads-web-campaign" />

### Google AdsのWebキャンペーンの作成

この記事では、AppsFlyerを使用して、モバイル、PC、コンソールアプリ向けのWebキャンペーンをGoogle Adsで設定する方法を説明します。 Google AdsとAppsFlyerの連携、およびキャンペーンの計測リンクを設定します。

* [AppsFlyerでのGoogle Ads連携の設定](#appsflyerでのgoogle-ads連携の設定)（必須）
* [Google Adsでの連携の設定](#google-adsでのwebキャンペーンの作成)（必須）

ステップ1でGoogle AdsとAppsFlyerを連携し、計測リンクを設定した後、ステップ2でランディングページを作成します。ランディングページでは、OneLink Smart ScriptまたはSmart Bannersが計測リンクを使用して、アプリストアへ誘導するCTAボタンを生成します。

* [OneLink Smart Scriptを使用したランディングページの作成](#onelink-smart-scriptを使ったランディングページの作成)（任意）
* [OneLink Smart Bannersを使用したランディングページの作成](#onelink-smart-bannersを使ったランディングページの作成)（任意）

<div id="create-a-google-ads-integration-in-appsflyer" />

## AppsFlyerでのGoogle Ads連携の設定

まず、Webキャンペーン向けのGoogle Ads連携を有効にし、AppsFlyerからOCIに送信するポストバックを設定します。

<Accordion title="1. Webキャンペーン向けGoogle Ads連携の有効化">

1. AppsFlyerのサイドメニューから、［**コラボレーション**］>［**Partner Marketplace**］に移動します。
2. **Google Ads Web**を検索して選択します。
3. ［**連携の設定**］をクリックします。［**アクティブな連携**］の設定ページが開きます。
4. ［**連携**］タブで、［**パートナーを有効にする**］をオンにします。**注意：** このパートナーとの連携中は、トグルをオン（<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">有効</Anchor>）のままにしておく必要があります。
5. iOSアプリの連携を設定する場合は、［**高プライバシー一括設定**］をオフにします。

> 📘 **Note**
>
> 後述の手順でGoogleにサインインし、AppsFlyerによるトークンの取得を許可すると、**Missing token**エラーメッセージは表示されなくなります。サインイン後もエラーが続く場合は、トークンに必要な権限が付与されていることを確認してください。

1. ［**初回起動のコンバージョンID**］に、Google Adsで設定した`First open`コンバージョンアクションのIDを入力します。 IDを確認するには、Google Adsで［**初回起動**］のコンバージョンアクションページの［**詳細**］タブを開きます。次に、ページのURLから`ctid=*`クエリパラメータの値をコピーします。たとえば、`ctid=123456789`の場合、［**初回起動のコンバージョンアクションID**］欄に`123456789`を入力します。

   ![](https://files.readme.io/0bbe655051204d8902b82f2f8d8b12f183ef40f9e84c542972db767707d75a9d-26324053660177.png)

> 👍 **Tip**
>
> Google Adsで［First open］アクションの設定がまだ完了していない場合は、設定が完了するまで仮の値を入力できます。

1. ［**お客様ID**］を入力します。このIDは、Google Adsの管理画面で取得できます。
   1. Google Adsアカウントにログインします。
   2. 右上のGoogleアカウントのアイコンをクリックし、お客様IDが表示される位置までスクロールします。
2. 同じアプリのキャンペーンを複数のGoogle Adsアカウントで配信している場合、クロスアカウントコンバージョントラッキングにはマネージャー（MCC）アカウントのお客様IDを使用する必要があります。個別アカウントのお客様IDではなく、**MCC ID**を［**お客様ID**］欄と［**MCCのお客様ID**］欄の両方に貼り付けます（両方に同じIDを入力）。   
   広告配信に使用するGoogle Adsアカウントが1つだけの場合は、そのアカウントのIDを［**お客様ID**］欄に貼り付け、［**MCCのお客様ID**］欄は空欄にします。 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">MCCアカウントの設定に関するGoogleの手順</Anchor>を参照してください。
3. ［**許可**］をクリックします。

</Accordion>

<Accordion title="2. ビュースルー計測の有効化">

AppsFlyerは、[Smart Script](#set-up-a-smart-script-crossplatform-landing-page)または[Smart Banners](#set-up-a-smart-banners-landing-page)を実装したランディングページを使用するGoogleのWebキャンペーンで、ビュースルー計測に対応しています。これにより、ユーザーが広告を直接クリックしなくても、広告表示をきっかけに発生したアプリのインストールを確率論的モデリング（PMOD）で計測できます。

ユーザーがGoogleの広告を見た後、[Smart Script](#set-up-a-smart-script-crossplatform-landing-page)または[Smart Banners](#set-up-a-smart-banners-landing-page)を実装したランディングページにアクセスすると、AppsFlyerは、その後に発生したアプリのインストールを、クロスプラットフォームの場合も含め、元のWebインプレッションの成果として計測できます。

取得できる場合は、Googleへのポストバックに`gclid`が含まれます。

**ビュースルー計測を有効にするには、次の手順を実行します。**

1. AppsFlyerのサイドメニューから、［**コラボレーション**］>［**パートナー連携>アクティブな連携**］>［**Google Ads Web**］を開きます。
2. ［**連携**］タブで、［**インストールの計測**］セクションまでスクロールします。
3. ［**インストール：ビュースルー計測**］をオンにします。
4. **［任意］**［**クロスプラットフォームの計測優先度を同等にする**］をオンにし、ルックバック期間を設定します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">クロスプラットフォームのインプレッションに同等の優先度を設定する方法</Anchor>を参照してください。
5. ［**アトリビューション**］タブを開きます。
6. ［**ビュースルー計測**］セクションまでスクロールし、［**ビュースルールックバック期間**］を設定します（最大24時間）。
7. ［**連携を保存**］をクリックして変更を適用します。

</Accordion>

<Accordion title="3. Advanced Matching Data Sharingの有効化">

Advanced Matching Data Sharingはパートナー別・アプリ別に管理されるため、Google Ads Webについても個別にオンにする必要があります。

オンにすると、送信するイベントデータにハッシュ化されたメールアドレスや電話番号が含まれている場合、それらの識別子がGoogle OCIと共有されます。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor>を参照してください。

Advanced Matching Data Sharingをオンにするには、次の手順を実行します。

1. AppsFlyerのサイドメニューから、［**コラボレーション**］>［**パートナー連携**］>［**アクティブな連携**］に移動します。
2. **Google Ads Web**を検索して選択します。
3. ［**連携**］タブで、［**Advanced Matching Data Sharing**］をオンにします。
4. ［**連携を保存**］をクリックします。

</Accordion>

<Accordion title="4. アプリ内イベントポストバックの設定">

現在、OCI APIを通じてGoogle Ads Webにデフォルトのポストバックが自動送信されるイベントは、インストールのみです。その他のイベントは、AppsFlyerイベントをGoogle AdsのコンバージョンアクションIDにマッピングして、カスタムポストバックを作成できます。「コンバージョンアクション」は、Google Adsで成果計測の対象となるイベントを指す用語です。 AppsFlyerイベントにマッピングするGoogle Ads Webのイベントは、Google Adsの管理画面で確認してください。

1. ［**アプリ内イベントポストバック**］をオンにします。
2. 必要に応じて、アプリ内イベントのポストバック期間を設定します（設定の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">こちらの記事</Anchor>を参照してください）。
3. ［**イベントを追加**］をクリックして、SDKイベントまたはサーバー間イベントをリストに追加します。
4. ［**AppsFlyerイベント**］列で、ドロップダウンからイベント名を選択します。 AppsFlyerは、アプリに実装したSDKまたはサーバー間イベントからイベント名を受信します。
5. ［**パートナー側のイベント名**］列で、AppsFlyerイベントを、対応するGoogleのコンバージョンアクションIDにマッピングします。事前にGoogle Adsで必要なコンバージョンアクションを作成しておく必要があります。 Google Adsでの設定方法は、[カスタムコンバージョンアクションの作成](#h_01J1MPPMW4KMSXAR903P534X65)を参照してください。

   **Google AdsでコンバージョンアクションIDを確認するには、次の手順を実行します。**

   1. Google Adsを開きます。
   2. マッピングするコンバージョンアクションのページを開きます。
   3. ［**詳細**］タブを開きます。
   4. ページのURLから、`ctid=*`クエリパラメータの値をコピーします。
   5. AppsFlyerに戻ります。
   6. ［**パートナー側のイベント名**］列に、その値を貼り付けます。たとえば、`ctid=123456789`の場合は、`123456789`を貼り付けます。
6. ［**送信対象ユーザー**］列で、［**このパートナーのみ**］または［**オーガニックを含むすべてのメディアソース**］を選択します。**注意：** 成果が紐づいていないイベントは、<Anchor target="_blank" href="/marketers/ja/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor>がオンで、ハッシュ化されたメールアドレスまたは電話番号が含まれている場合にのみ送信されます。
7. ［**送信するデータ**］列で、収益値（イベントに含まれる場合）を含むすべてのイベントパラメータをポストバックで送信するかどうかを選択します。
8. ［任意］［**条件を追加**］アイコンをクリックして、イベントに<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor>します。
9. ［**連携を保存**］をクリックします。
10. ［任意］連携の保存後は、同じ設定ページで、このパートナーと連携する他のアプリを設定することもできます。
    1. 左上のパートナー名の下にあるアプリ名をクリックし、アプリの一覧を開きます。
    2. ドロップダウンリストから別のアプリを選択します。
    3. 選択したアプリについて、連携の設定手順を繰り返します。

</Accordion>

<Accordion title="5. OneLinkテンプレートの設定">

Google Adsキャンペーン用のOneLink計測リンクを作成する前に、OneLinkテンプレートを設定する必要があります。その後、このテンプレートからOneLinkの計測URLを作成し、GoogleのトラッキングテンプレートURLとして使用できます。

> 📘 **Note**
>
> 以下では、Smart Scriptを使用するGoogleのWebキャンペーン向けに、OneLinkテンプレートを作成する手順を説明します。 OneLinkテンプレートの詳しい設定方法は、「OneLinkテンプレート」記事の「OneLinkテンプレートの作成方法」セクションを参照してください。

1. ［**新規テンプレート**］または［**テンプレートの編集**］ページの［**リダイレクト**］セクションで、以下を設定します。
   * ［**アプリがインストールされていない場合**］>［**リダイレクト先**］：使用する選択肢を選択します。ここで設定したリダイレクト先は、Googleのトラッキングテンプレートに追加するリダイレクトパラメータ（<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_android_url">`af_android_url`</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ios_url">`af_ios_url`</Anchor>）に設定された`{lpurl}`の値で上書きされます。[トラッキングテンプレートURLの設定](#トラッキングテンプレートurlの設定)を参照してください。
   * **アプリがインストールされている場合**：Googleは最終ページURL以外へのリダイレクトを許可しないため、アプリ起動用のユニバーサルリンク、URIスキーム、All Linksを**設定しないでください**。
   * ［**デスクトップのWebページでリンクがクリックされた場合**］>［**リダイレクト先**］：使用する選択肢を選択します。ここで設定したリダイレクト先は、Googleのトラッキングテンプレートに追加するリダイレクトパラメータ（<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_web_dp">`af_web_dp`</Anchor>）に設定された`{lpurl}`の値で上書きされます。[トラッキングテンプレートURLの設定](#トラッキングテンプレートurlの設定)を参照してください。
2. ［**テンプレートを作成**］をクリックします。

</Accordion>

<div id="create-a-web-campaign-in-google-ads" />

## Google AdsでのWebキャンペーンの作成

Google Adsで以下の手順を実行します。

<Accordion title="1. キャンペーンの種類、目的、目標の設定">

Google Adsは、ここで選択したキャンペーンの種類・目的・目標に基づいて、適切な入札戦略を設定し、キャンペーンのパフォーマンスを最適化します。

1. Google Adsにログインし、キャンペーンを作成します。
2. キャンペーンの目的を選択します。

   ![](https://files.readme.io/90063f7fe5a363ed498271148c4165969cc63c708a73ab25363d2263a79b0828-26324053661201.png)
   * モバイルアプリのキャンペーン専用の［アプリのプロモーション］を除き、すべての目的を選択できます。
   * 特定のアプリ内イベントに基づいて最適化する場合は、キャンペーンの目的を［販売促進］に設定することを推奨します。
3. コンバージョン目標を選択します。

   ![](https://files.readme.io/5ca0a0425af24d5926dc0a7a3529632e22bd140423e87c026ff1527e7a0341b3-26324096257169.png)
   * デフォルトでは、アカウントレベルで定義済みのキャンペーン目標が表示されます。そのまま使用することも、キャンペーンに関係のない目標を削除することもできます。
   * Googleに最適化させたい目標が見当たらない場合：

     <Anchor target="_blank" href="/marketers/ja/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals">カスタムコンバージョンアクションと目標を作成</Anchor>します。
   * 定義済みの目標は、［コンバージョン］ページでも編集できます。
4. キャンペーンの種類を選択します。

   ![](https://files.readme.io/14daea1c1edf92854e21d0a4c5d34372a4e062d68a4613967bb4f40d0d1e720f-26324053659281.png)
   * 商品カタログが必要で、確認済みのドメインに限定される［ショッピング］を除き、すべての種類を選択できます。

</Accordion>

<Accordion title="2. カスタムコンバージョンアクションの作成">

次に、[AppsFlyerで設定したアプリ内イベント](#h_01J1MPPMW34GG0EPDWYXA7383C)ごとに、対応するコンバージョンアクションをGoogle Adsで作成します。コンバージョンアクションの作成後、新しいアクションのIDをコピーし、AppsFlyerのアプリ内イベントにマッピングします。

Google Adsでカスタムコンバージョンアクションと目標を作成するには、次の手順を実行します。

1. Google Adsアカウントの概要ページで、サイドメニューから［**目標>コンバージョン>概要**］を選択します。
2. ［**+新しいコンバージョンアクション**］をクリックします。
3. コンバージョンアクションのデータソースとして、［**オフラインコンバージョン**］を選択します。
4. コンバージョンの種類のリストから［**インポート**］を選択し、次のいずれかを選択します。

   * ［**APIまたはアップロードによる手動インポート>クリック経由のコンバージョンを計測**］。

   または

   * ［**CRM、ファイル、その他のデータソース>クリック経由のコンバージョンを計測**］を選択し、［**データソース**］で［**このステップをスキップし、後でデータソースを設定**］を選択します。
5. ［**続行**］をクリックします。
6. ［**コンバージョン目標**］で、コンバージョンアクションのカテゴリを選択します。
7. ［**コンバージョン名を入力**］欄に、コンバージョンアクションの名前を入力します。

> ❗️ **Warning**
>
> GCLIDに加えてGBRAID／WBRAIDでもOffline Conversions APIを使用するには、コンバージョンアクションの［**カウント方法**］を［**初回のみ**］ではなく［**全件**］（デフォルト）に設定してください。

1. ［**コンバージョン名**］を入力し、［**追加**］をクリックします。**注意**：キャンペーンを1つのアクションのみで最適化する場合は、そのアクションだけをこのカテゴリに含めてください。たとえば、**初回起動**のコンバージョンアクションに基づいてキャンペーンを最適化する場合は、そのカテゴリに含まれるアクションを初回起動のみにしてください。キャンペーンの作成時に、このカテゴリをパフォーマンス最適化のコンバージョン目標として選択できるようになります。
2. データソースを設定せずに［**保存して続行**］をクリックし、［**完了**］をクリックします。作成したコンバージョンアクションは、最初は［無効］と表示される場合がありますが、実際のデータが送信されると［有効］に変わります。
3. 新しいコンバージョンアクションをAppsFlyerのポストバックイベントにマッピングするため、そのコンバージョンアクションIDを取得します。コンバージョン目標の［**概要**］ページで、作成したコンバージョンアクションをクリックし、ページのURLから`ctid=*`クエリパラメータの値をコピーします。

   ![](https://files.readme.io/0bbe655051204d8902b82f2f8d8b12f183ef40f9e84c542972db767707d75a9d-26324053660177.png)
4. AppsFlyerで、Googleに最適化させたいポストバックイベントの［**パートナー側のイベント名**］列に`ctid`の値を貼り付けます。[アプリ内イベントポストバックの設定](#h_01J1MPPMW34GG0EPDWYXA7383C)を参照してください。

</Accordion>

<Accordion title="3. キャンペーンURLの設定">

GoogleのWeb広告キャンペーンでは、広告接触ごとに最終ページURLとトラッキングテンプレートURLの2つのURLを使用します。広告がクリックされると、この2つのURLが同時に呼び出されます。Googleはこの仕組みを「並行トラッキング」と呼んでいます。並行トラッキングの詳細は、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">Googleのドキュメント</Anchor>を参照してください。

<div id="set-the-final-url" />

#### 最終ページURLの設定

Googleは<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">最終ページURL</Anchor>を、「ユーザーが広告をクリックした後にアクセスする、自社Webサイト内のページのURL」と定義しています。「ランディングページ」とも呼ばれます。

**最終ページURLを設定するには、次の手順を実行します。**

1. Google Adsで、［**キャンペーン**］>［**広告**］ページを開きます。
2. 広告の行で、編集アイコンをクリックします。

   ![](https://files.readme.io/e6b834a0e105324c5b9e4105a5ce7e1f47fa7c00fcf2aee29b6b0e96763150f1-26324098055057.png)
3. ［**最終ページURL**］に、WebランディングページのURLを入力します。

> ❗️ **Warning**
>
> 最終ページURLにAppsFlyerのURL（OneLinkまたは単一プラットフォーム向けの計測URL）を設定すると、キャンペーンが不承認になる可能性があるため、使用できません。 Webページ、Google Playストア、App Storeなど、リダイレクトが発生しない、直接アクセスできるURLのみを使用してください。

1. ユーザーを最終的に誘導したいWeb上の場所を指定する必要があります。次のいずれかを指定できます。
   * **ランディングページのURL**：Google Play、App Store、その他のアプリストアからアプリをダウンロードするよう促すCTAボタンがあるページのURL。このランディングページには、CTAボタンのURLを自動生成するSmart ScriptまたはSmart Bannersが実装されています。作成方法は、[Smart Scriptを使用したランディングページの作成](#onelink-smart-scriptを使ったランディングページの作成)または[Smart Bannersを使用したランディングページの作成](#onelink-smart-bannersを使ったランディングページの作成)を参照してください。

     最終ページURLにAppsFlyerの計測パラメータを追加し、GoogleのValueTrackパラメータにマッピングできます。例：`af_c_id={campaignid}`。 Googleの広告がクリックされてランディングページが読み込まれると、Smart ScriptまたはSmart Bannersがこれらのパラメータをランディングページの送信URLにコピーできます。使用可能なValueTrackパラメータの詳細については、[Googleのドキュメント](https://support.google.com/google-ads/answer/6305348?sjid=9660882197247124000-EU#zippy=%2Cfinal-url-tracking-template-or-custom-parameter)をご確認ください。

     例：

     ```
     https://example.com?product=1234&af_c_id={campaignid}
     ```
   * App StoreやGoogle Playなどの**ストアのURL**。

> ❗️ **Warning**
>
> 最終ページURLとしてストアのURLを使用する場合を考えます。この場合、計測情報やカスタムパラメータの情報をAppsFlyerに送信するには、トラッキングテンプレートURLにAppsFlyerのパラメータを追加してマッピングする必要があります。

*
  ```
  https://play.google.com/store/apps/details?id=.com.app.id&hl=en&gl=US&referrer={gclid}&gclid={gclid}&campaignid={campaignid}
  ```
* ユーザーをストアに誘導せず、アプリを直接ダウンロードしてもらう場合は、**アプリのAPKファイルを直接ダウンロードするリンク**を使用します。

<div id="set-the-tracking-template-url" />

#### トラッキングテンプレートURLの設定

Google Adsはデフォルトで並行トラッキングを使用するため、トラッキングテンプレートURL（この場合はAppsFlyerの計測リンク）がバックグラウンドで読み込まれ、クリックがAppsFlyerに記録されます。トラッキングテンプレートURLの使用は必須ではありません。特にSmart BannersやSmart Scriptを使用する場合は、この記事の[Smart ScriptまたはSmart BannersでのトラッキングテンプレートURLの使用](#smart-scriptまたはsmart-bannersでのトラッキングテンプレートurlの使用)を参照してください。

1. Google Adsで、［**キャンペーン**］>［**キャンペーン**］ページを開きます。キャンペーンの行にある設定アイコンをクリックします。

   ![](https://files.readme.io/ec6503cfb3ff185448f13897240e0eadd7f10fc3678ffa85b4d52d2393b01ca4-26324098054033.png)
2. ［**設定**］>［**その他の設定**］>［**キャンペーンURLオプション**］を展開します。

   ![](https://files.readme.io/4959b4129749ff282ee3818c3b5724ac2ed3b1d033d06f8557329cafa812720f-26324053658641.png)
3. ［**トラッキングテンプレート**］に、以下の形式（ベースURL＋リダイレクトパラメータ）でURLを設定します。
   * **ベースURL**：広告のクリック先に応じて、以下のいずれかを設定します。
     * 広告のクリック先がGoogle PlayまたはApp Storeの場合は、**単一プラットフォーム向けの計測リンク**を設定します（以下の例を参照）。
     * 広告のクリック先がWebページの場合は、**OneLinkの計測リンク**を設定します（以下の例を参照）。

> ❗️ **Warning**
>
> 最終ページURLがGoogle PlayまたはApp Storeを直接指している場合（ユーザーのプラットフォームが判明している場合）、トラッキングテンプレートURLには単一プラットフォーム向けの計測リンクを使用してください。この場合にOneLinkのURLを使用すると、Googleで「Tracking call unsuccessful」エラーが発生します。

* **PIDパラメータ（必須）：** パラメータ<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#pid">`pid`</Anchor>`=googleads_int`を必ず追加してください。

> 👍 **Tip**
>
> キャンペーンを分析しやすいように、campaign-name\_webなど、キャンペーン名の先頭または末尾にキャンペーンの種類（webまたはmobile）を含めてください。

* **サイトIDパラメータ：** パラメータ<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor>を必ず追加してください。手動で任意の値を割り当てることができます。
* **キャンペーン名パラメータ：** 必須の<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#c">c</Anchor>パラメータを追加し、その値を手動で割り当てます（このパラメータにはValueTrackパラメータはありません）。
* **af\_force\_transparentパラメータ**：必須パラメータ`af_force_transparent=true`を追加します。このパラメータは、リダイレクト動作のセキュリティを強化し、Googleの要件に準拠するように設計されています。必要なパラメータを追加していない場合、Googleは広告を不承認にする可能性がありますのでご注意ください。
* **OneLinkの計測リンクのリダイレクトパラメータ：** 並行トラッキングを正しく機能させるため、AppsFlyerのリダイレクトパラメータを以下のいずれかの組み合わせで設定します。
  * `af_android_url`、`af_ios_url`、`af_web_dp`の各パラメータの値に、GoogleのValueTrackパラメータ`{lpurl}`を設定します。**重要：** すべてのケースで計測リンクが動作するよう、3つのパラメータすべてに値を設定してください。  
    **または**
  * `af_r`パラメータの値に、GoogleのValueTrackパラメータ`{lpurl}`を設定します。
* **単一プラットフォーム向け計測リンクのリダイレクトパラメータ：** 並行トラッキングを正しく機能させるため、`af_r`パラメータの値にGoogleのValueTrackパラメータ`{lpurl}`を設定します。

> ❗️ **Warning**
>
> Googleの要件を満たすため、`{lpurl}`の値が、以下の条件を満たす有効なリダイレクトURLであることを確認してください。
>
> * HTTPSプロトコルを使用していること。
> * エンコードされていること。
> * URLのドメインがリダイレクト許可リストに含まれていること。

* **GoogleのValueTrackパラメータにマッピングしたAppsFlyerの計測パラメータ**。例：<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor>`={campaignid}`。使用可能なValueTrackパラメータの詳細については、[Googleのドキュメント](https://support.google.com/google-ads/answer/6305348?sjid=9660882197247124000-EU#zippy=%2Cfinal-url-tracking-template-or-custom-parameter)をご確認ください。
* 以下のパラメータは含めないでください。これらのパラメータを含むリクエストは、並行トラッキングのフローではサポートされず、拒否されます。
  * `af_dp`
  * `af_android_store_csl`
  * `af_ios_store_cpp`
  * `af_og_title`
  * `af_og_description`
  * `af_og_image`
* リダイレクトパラメータ`{lpurl}`の値を変更するパラメータは含めないでください。これには`af_base_params_forward`と`af_param_forwarding`が含まれます。

> 📘 **Note**
>
> トラッキングテンプレートURLのその他の制限は、この記事の「機能と制限事項」セクションを参照してください。

<div id="google-tracking-template-url-examples" />

#### GoogleトラッキングテンプレートURLの例

GoogleのトラッキングテンプレートURLに設定する**リンク**として、**OneLink**を使用する例：

```
https://subdomain.onelink.me/aAB1?pid=googleads_int&af_force_transparent=true&af_android_url={lpurl}&af_ios_url={lpurl}&af_web_dp={lpurl}&c=summer_sale24&af_siteid=123456&af_c_id={campaignid}&af_adset=sum24A&af_adset_id={adgroupid}&af_sub1={gclid}&af_sub2={gbraid}
```

GoogleのトラッキングテンプレートURLに**単一プラットフォーム向けリンク**を設定する例：

```
https://app.appsflyer.com/id1510557250?pid=googleads_int&af_force_transparent=true&c=examplecamp&af_siteid=123456&af_adset=exampleadset&af_adset_id={adgroupid}&af_c_id={campaignid}&af_ad_id={creative}&af_click_lookback=7d&af_r={lpurl}
```

<div id="using-the-tracking-template-url-with-smart-script-or-smart-banners" />

#### Smart ScriptまたはSmart BannersでのトラッキングテンプレートURLの使用

広告からSmart ScriptまたはSmart Bannersを実装したランディングページに誘導する場合、トラッキングテンプレートURLにAppsFlyerの計測リンクを設定する必要はありません。ユーザーがランディングページのCTAボタンをクリックすると、これらのツールが自動生成した計測リンクを通じて、クリックがAppsFlyerに記録されるためです。ただし、トラッキングテンプレートURLを空欄にするかどうかを決める際は、以下の点を考慮してください。

* トラッキングテンプレートURLに**AppsFlyerの計測リンクを設定しない場合**、ユーザーが広告をクリックした後にランディングページ内の遷移ボタンをまったくクリックしなかったときにインストールの成果が計測できないリスクがあります。ユーザーがルックバック期間内にアプリストアへ直接アクセスしてアプリをダウンロードした場合、そのインストールの成果は計測できません。
* トラッキングテンプレートURLに**計測リンクを設定した場合**、ユーザーが広告をクリックした後にランディングページのCTAボタンもクリックすると、クリックが1回ではなく2回記録され、コンバージョン率のデータに影響する場合があります。

</Accordion>

<div id="create-a-landing-page-with-onelink-smart-script" />

## OneLink Smart Scriptを使ったランディングページの作成

**ユーザージャーニー：** ユーザーがGoogleの広告をクリックし、モバイルWebサイトに誘導されます。アプリのダウンロードを促すCTAボタンがあるページにアクセスします。ユーザーがそのボタンをクリックすると、アプリストアへリダイレクトされます。

<Accordion title="データ処理の全体の流れ">

Web to App（W2A）でSmart Scriptを使用する場合、データは以下の流れで処理されます。

![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. ユーザーがGoogleの広告をクリックすると、Googleは最終ページURLに以下を自動的に追加します。
   * Androidデバイス、および同意したiOSデバイスユーザーには、`gclid`パラメータ。
   * 同意していないiOSデバイスユーザーには、`gbraid`と`wbraid`パラメータ。
   * リダイレクトパラメータを除く、広告のGoogleトラッキングテンプレートURLに設定されたすべてのクエリパラメータ。
2. 最終URLは、ユーザーをランディングページにリダイレクトします。
3. 同時に、自動追加された`gclid`、`gbraid`、`wbraid`と、`pid=googleads_int`パラメータを含む広告のGoogleトラッキングテンプレートURLがバックグラウンドで呼び出され、クリックがAppsFlyerに記録されます。
4. ランディングページが読み込まれると、Smart Scriptは受信URLのパラメータを含むインプレッションイベントをAppsFlyerに送信します。このインプレッションにより、ランディングページのビュースルー計測が可能になります。インプレッションとビュースルー計測については、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">カスタムインプレッションURLの作成</Anchor>を参照してください。
5. Smart Scriptは、`gclid`、`gbraid`、`wbraid`を含む受信URLのパラメータに基づき、ページ上のCTAボタンの送信URLを生成します。ボタンの遷移先として、以下を指定できます。
   * OneLinkの計測リンク経由でアクセスするGoogle PlayとApp Store。
   * 複数のプラットフォームのストア（CTV、Epic、Steamなど）。この場合、Smart Scriptはプラットフォームごとに単一プラットフォーム向けの計測リンクを送信URLとして生成し、そのプラットフォームのストアに誘導します。
   * ユーザーのデバイスへのAPKファイルのダウンロード。
6. ユーザーがCTAボタンをクリックすると、クリックがAppsFlyerに記録されます。
7. ユーザーはストアにリダイレクトされ、アプリをダウンロードします。
8. インストールのイベントは、ユーザーがアプリを起動したときにAppsFlyerで計測されます。
9. AppsFlyerは、確率論的モデリングに基づいてインストールの成果を計測します。[インストールリファラ](https://www.appsflyer.com/glossary/install-referrer/)が利用可能な場合は、決定論的な手法で計測します。
10. `gclid`、または`gbraid`と`wbraid`、および追加のイベントパラメータを含むポストバックが生成され、OCI API経由でGoogle Adsに送信されます。 Google Adsは`gclid`、または`gbraid`と`wbraid`を使用して対象のクリックを識別し、その他のパラメータをキャンペーンの最適化に使用します。

</Accordion>

<Accordion title="ランディングページへのSmart Scriptの設定">

GoogleのWebキャンペーン向けにSmart Scriptを設定するには、以下の手順を実行します。

1. Smart Scriptを作成します。

> 📘 **Note**
>
> 以下では、Smart Scriptを使用してGoogleのWebキャンペーンを設定するために必要な手順を説明します。 Smart Scriptキャンペーンの詳しい設定方法は、「OneLink Smart Script V2の設定」記事の「OneLink Smart Scriptの作成方法」セクションを参照してください。

1. Smart Scriptで取得する関連URLパラメータが、すべて受信URLに追加されていることを確認してください。受信URLに追加されるパラメータを確認するには、Google Adsで、最終ページURLまたはトラッキングテンプレートURLの作成時に設定したURLパラメータを確認します。[キャンペーンURLの設定](#h_01J1MPPMW44NGXN55SFD16Z4HE)を参照してください。
2. キャンペーンに必要な受信URLパラメータを、ユーザーがCTAボタンをクリックしたときにAppsFlyerに送信される送信URLパラメータにマッピングします：
   * **PID**：Smart Scriptが受信URLから`pid=googleads_int`パラメータの値を取得し、送信URLの対応するパラメータにマッピングすることを確認してください。
   * **GCLID：** アプリ内イベントのポストバックをGoogle Adsに正常に送信するには、`gclid`パラメータが必要です。送信URLのGCLIDパラメータのマッピング方法は、Smart Scriptのバージョンによって異なります。
     * バージョン2.8.1以降：受信URLに`gclid`パラメータがある場合、送信URLに自動転送されるため、手動でのマッピングは不要です。
     * バージョン2.8.0以前：［**Smart Script**］ページの［**URLパラメータのマッピング**］セクションで、`gclid`パラメータを手動でマッピングする必要があります。
       1. ［**マッピング対象**］で［**カスタムパラメータ**］を選択します。
       2. ［**送信URLパラメータ**］と［**受信URLパラメータ**］に**gclid**と入力します。
   * **GBRAID**と**WBRAID**：同意していないiOSデバイスユーザーのアプリ内イベントポストバックをGoogle Adsに正常に送信するには、`gbraid`と`wbraid`パラメータが必要です。送信URLの`gbraid`と`wbraid`パラメータのマッピング方法は、Smart Scriptのバージョンによって異なります。
     * バージョン2.9.0以降：受信URLに`wbraid`と`gbraid`パラメータがある場合、送信URLのパラメータに自動的に転送されるため、手動でマッピングする必要はありません。
     * バージョン2.8.1以前：［**Smart Script**］ページの［**URLパラメータのマッピング**］セクションで、`wbraid`と`gbraid`パラメータを手動でマッピングする必要があります。
       1. ［**マッピング対象**］で［**カスタムパラメータ**］を選択します。
       2. ［**送信URLパラメータ**］と［**受信URLパラメータ**］に**wbraid**と入力します。
       3. `wbraid`パラメータについて、上記の手順を繰り返します。

> 📘 **Note**
>
> AppsFlyerのローデータレポートに表示するには、受信URLのgclid、gbraid、wbraidを、それぞれ専用の送信URLのaf\_sub[1-5]パラメータにもマッピングする必要があります（送信URLのgclid、gbraid、wbraidパラメータへのマッピングとは別に設定します）。

</Accordion>

<Accordion title="クロスプラットフォーム向けランディングページでのSmart Scriptの設定">

クロスプラットフォーム向けではないランディングページでは、通常、マーケティング担当者がAppsFlyerのSmart ScriptページでSmart Scriptを自動生成します。ただし、クロスプラットフォーム向けのランディングページの場合、開発者がマーケティング担当者から送信されたパラメータに基づいてSmart Scriptを作成する必要があります。

GoogleのWebキャンペーン向けにSmart Scriptを設定するには、以下の手順を実行します。

1. OneLinkテンプレートでクロスプラットフォームの計測を有効にします。<Anchor target="_blank" href="/marketers/ja/docs/set-up-cross-platform-links-for-multi-device-campaigns#クロスプラットフォーム計測用のonelinkテンプレートの作成">クロスプラットフォーム計測用のOneLinkテンプレートの作成・編集</Anchor>を参照してください。
2. 関連するURLパラメータがすべてランディングページのURL（受信URL）に追加されていることを確認してください。受信URLに追加されるパラメータを確認するには、Google Adsで、最終ページURLまたはトラッキングテンプレートURLの作成時に設定したURLパラメータを確認します。[キャンペーンURLの設定](#h_01J1MPPMW44NGXN55SFD16Z4HE)を参照してください。
3. 受信パラメータごとに、マッピング先の送信パラメータを決めます。たとえば、受信URL内の`af_site_id`は送信URL内でも`af_site_id`にマッピングしてください。
4. 空欄にできない必須の送信パラメータについて、デフォルト値を決めます。
5. 開発者に以下の情報を共有します。
   * 受信パラメータと送信パラメータのマッピング。開発者は、このマッピングに基づいて、送信先のダイレクトURLを生成するスクリプトを作成します。
   * 各パラメータのデフォルト値。対応する受信URLパラメータの値がない場合、スクリプトは送信URLパラメータにデフォルト値を設定します。
   * OneLinkの計測リンクを使用する場合は、開発者にOneLinkのドメインとテンプレートIDを共有してください。開発者はこの情報を使ってOneLinkの送信URLを作成します。例：`your_brand.onelink.me/A1b2`。ブランドドメインを使用する場合の例：`click.yourbrand.com/A1b2`。
   * 以下のDev Hubのリンクを開発者に共有します。
     * モバイル以外のプラットフォーム向けの送信先ダイレクトURLを作成するための[手順とコード例](https://dev.appsflyer.com/hc/docs/create-direct-click-url)。
     * クロスプラットフォーム向けランディングページを作成するための[デモと手順](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/)。
   * Smart Scriptのバージョン2.8.1以降では、受信URLに`gclid`パラメータがあれば送信URLに自動転送されるため、手動でのマッピングは不要です。開発者は`gclid`を`af_sub`パラメータのいずれかにマッピングし、ローデータレポートで確認できるようにすることもできます。「Google Ads GCLID」を参照してください。

</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## OneLink Smart Bannersを使ったランディングページの作成

**ユーザージャーニー：** ユーザーがGoogleの広告をクリックし、モバイルWebサイトに誘導されます。アクセスしたページに、アプリストアからのダウンロードを促すCTAを備えたSmart Bannerが表示されます。

<Accordion title="データ処理の全体の流れ">

1. ユーザーがGoogleの広告をクリックすると、Googleは最終ページURLに以下を自動的に追加します。
   * Androidデバイス、および同意したiOSデバイスユーザーには、`gclid`パラメータ。
   * 同意していないiOSデバイスユーザーには、`gbraid`と`wbraid`パラメータ。
   * リダイレクトパラメータを除く、広告のGoogleトラッキングテンプレートURLに設定されたすべてのクエリパラメータ。
2. 同時に、自動追加された`gclid`パラメータと`pid=googleads_int`パラメータを含む広告のGoogleトラッキングテンプレートURLがバックグラウンドで呼び出され、クリックがAppsFlyerに記録されます。
3. ランディングページが読み込まれると、Smart Bannerは受信URLのパラメータを含む<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">インプレッション</Anchor>イベントをAppsFlyerに送信します。このインプレッションにより、ランディングページのビュースルー計測が可能になります。インプレッションとビュースルー計測については、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">カスタムインプレッションURLの作成</Anchor>を参照してください。
4. Smart Bannerは、`gclid`を含む受信URLのパラメータに基づき、バナーのCTAボタンの送信URLを生成します。なお、Smart BannerはOneLinkベースの計測リンクのみを生成できます。
5. ユーザーがSmart BannerのCTAボタンをクリックすると、クリックが発生し、AppsFlyerに記録されます。
6. ユーザーはストアにリダイレクトされ、アプリをダウンロードします。
7. インストールのイベントは、ユーザーがアプリを起動したときにAppsFlyerで計測されます。
8. AppsFlyerは、確率論的モデリングに基づいて、または[インストールリファラ](https://www.appsflyer.com/glossary/install-referrer/)が利用可能な場合は決定論的手法でインストールを計測します。
9. `gclid`とその他のイベントパラメータを含むポストバックが生成され、OCI API経由でGoogle Adsへ送信されます。 Googleは`gclid`パラメータで対象のクリックを識別し、その他のパラメータをキャンペーンの最適化に使用します。

</Accordion>

<Accordion title="ランディングページへのSmart Bannersの設定">

> 📘 **Note**
>
> 以下では、Smart Bannersを使用してGoogleのWebキャンペーンを設定するために必要な手順を説明します。 Smart Bannersキャンペーンの詳しい設定方法は、「Smart Banners：モバイルWebからアプリへ（マーケティング担当者向け）」記事の設定セクションを参照してください。

GoogleのWebキャンペーン向けにSmart Bannersを設定するには、以下の手順を実行します。

1. Smart Bannerを作成します。手順は、「<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners：モバイルWebからアプリへ（マーケティング担当者向け）</Anchor>」の記事の<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers#設定">設定セクション</Anchor>を参照してください。
2. 受信URLに以下が含まれていることを確認してください。
   * `pid=googleads_int`が受信URLに含まれていること。
   * `gclid`パラメータが受信URLに付与されていること。 Smart Bannersは、`gclid`パラメータをバナーの送信URLに自動転送します。 Google OCIにアプリ内イベントのポストバックを正常に送信するには、`gclid`パラメータが必要です。
   * 同意していないiOSデバイスユーザーのポストバックを送信する場合、受信URLに`gbraid`と`wbraid`パラメータが含まれていること。 Smart Bannersは、これらのパラメータをバナーの送信URLに自動転送します。この場合、`gbraid`と`wbraid`パラメータにより、`gclid`がなくてもGoogleはイベントの集計データを取得できます。
   * 関連するすべてのURLパラメータが受信URLに追加されていること。受信URLに追加されるパラメータを確認するには、Google Adsで、最終ページURLまたはトラッキングテンプレートURLの作成時に設定したURLパラメータを確認します。[キャンペーンURLの設定](#h_01J1MPPMW44NGXN55SFD16Z4HE)を参照してください。
3. ［任意］バナーグループの設定ページの［**動的アトリビューションパラメータ**］セクションで、最初のチェックボックスをオンにします。この設定により、受信リンクのすべてのパラメータがSmart Bannerのリンクに追加されます。

</Accordion>

<div id="view-web-to-app-attribution-data" />

## Web to Appの計測データの確認

Web経由のコンバージョンイベントは元の`googleads_int`PIDでGoogleに送信されますが、AppsFlyer管理画面とローデータレポートでは`googleadwords_int`PIDでレポートされます。これは、コンバージョンの成果イベントと、その成果をアシストしたイベントの両方に適用されます。

この統合されたレポート表示により、モバイルとWebのすべてのコストレポートを含め、Webキャンペーンとアプリキャンペーンのパフォーマンスを1か所で分析できます。

<div id="view-in-the-dashboard" />

### 管理画面での確認

GoogleのWeb to Appの計測結果はすべて、オーバービューダッシュボードとアクティビティダッシュボードで`googleadwords_int`として表示されます。これにより、プラットフォームを横断したキャンペーンの成果を1つにまとめて確認できます。標準のフィルタと内訳表示を使用して、Google Adsのデータ内でアプリとWebのトラフィックを比較できます。

<div id="view-in-raw-data-and-api-reports" />

### ローデータレポートとAPIレポートでの確認

* **ローデータのエクスポートとAPIレスポンス**では、GoogleのWeb上のアクティビティについて、`media_source`フィールドに`googleadwords_int`PIDが含まれます。 Webキャンペーンの設定詳細を確認するには、`original_url`フィールドを参照してください。Webキャンペーンの作成時に使用されたPIDとして`googleads_int`が表示されます。
* **ポストバックレポート**には、ポストバックの送信先となった元のメディアソースとして`googleads_int`が表示されます。

<div id="troubleshooting-in-app-events-postbacks" />

## アプリ内イベントのポストバックに関するトラブルシューティング

Google AdsやGoogle Analyticsにアプリ内イベントのデータが表示されない場合、またはMissing tokenエラーが表示される場合は、サポートに問い合わせる前に以下の設定を確認してください。

<Accordion title="トークンの権限の設定">

Google Adsで、アクセストークンにオフラインコンバージョンのアップロードに必要な権限があることを確認してください。

1. Google Developers Consoleにアクセスします。
2. `uploadClickConversions`に次のOAuthスコープがあることを確認してください：[`https://www.googleapis.com/auth/adwords`](https://www.googleapis.com/auth/adwords)
3. AppsFlyerの［連携］タブで、［**Googleでサインイン**］をクリックします。
4. MCCアカウントの管理者アカウントを選択します。
5. ［**許可**］をクリックします。

</Accordion>

<Accordion title="MCCのお客様ID">

同じアプリのキャンペーンを複数のGoogle Adsアカウントで配信している場合は、MCCアカウントのお客様IDを使用する必要があります。 [MCCアカウントの設定に関するGoogleの手順](https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC)を参照してください。

</Accordion>

<Accordion title="コンバージョンアクションID">

ポストバックするアプリ内イベントが、正しいコンバージョンアクションIDにマッピングされていることを確認してください。 Google AdsでのコンバージョンアクションIDの確認方法は、[Google AdsでコンバージョンアクションIDを確認する方法](#to-find-the-conversion-action-id-in-google-ads)を参照してください。

</Accordion>

<Accordion title="GCLID、GBRAID、WBRAIDパラメータ">

Google OCIへのポストバックをGoogle Adsに正しく登録するには、Smart ScriptまたはSmart Bannersの送信URLに、`gclid`、`wbraid`、`gbraid`のいずれかを含める必要があります。

</Accordion>

<div id="traits-and-limitations" />

## 機能と制限事項

| 項目 | 補足 |
| --- | --- |
| <span id="dashboard"></span>ダッシュボード | iOSのGoogleのWebキャンペーンの計測データは、AppsFlyer Classic Dashboardで表示・分析できます。通常、Web to AppキャンペーンではSKANダッシュボードを使用しません。 |
| <span id="reengagement-attribution"></span>リエンゲージメントの計測 | 同じキャンペーンによる成果でも、インストールは`googleads_int`、リエンゲージメントは`googleadwords_int`に紐づいて表示される場合があります。この動作は仕様であり、技術的な問題ではありません。   <br />  <br />通常、`googleadwords_int`のSRN連携が同時に有効になっており、同じGoogle AdsのWeb to Appキャンペーンのリエンゲージメントの成果を主張できる場合に発生します。 |
| <span id="cost-data"></span>コスト、クリック、インプレッションデータ | Google Ads Web（`googleads_int`）のコスト、クリック、インプレッションデータは、Google Ads連携（`googleadwords_int`）を通じて取得できます。<ul><li>データを取得するには、アドネットワークのアカウントをメインのPID（`googleadwords_int`）に接続してください。<ul><li>ROI360をご契約の場合：［**コスト設定**］ページで接続します。</li><li>ROI360をご契約でない場合：［**アクティブな連携**］ページの［**コスト**］タブで接続します。</li></ul></li><li>Google Ads Webキャンペーンのコスト、クリック、インプレッションデータを表示するには、計測リンクにキャンペーンID（<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>）が含まれていることを確認してください。</li><li>成果に紐づくコスト、クリック、インプレッションデータを最も細かい粒度で表示するには、計測リンクにキャンペーン階層の情報をすべて含める必要があります。</li></ul> |
| <span id="tracking-template-urls"></span>トラッキングテンプレートURL | トラッキングテンプレートURLは、以下の制限に従う必要があります。これらの制限に従わないと、リンクが正常に動作しなくなります。<ul><li>リンクには重複するパラメータを含めてはいけません。</li><li>リンクには、次のような無効なパラメータを含めてはいけません：<ul><li>値のないパラメータ、不正なパラメータ、解析できないパラメータ。値のないパラメータには、`key=`や`key`などが含まれます。例：`pid=googleads_int&key&c=campaign`、または`pid=googleads_int&key=&c=campaign`。</li><li>ValueTrackパラメータの値が欠落している場合。例：`{placement}`。値の欠落を防ぐため、Google Adsでトラッキングテンプレートを正しく設定し、各パラメータに値が設定されるようにしてください。</li></ul></li><li>Google Adsキャンペーンの［**キャンペーンURLオプション**］で設定した各パラメータの値は、トラッキングテンプレート内の値と一致する必要があります。一致しない場合は、ポリシーの更新に準拠するために、トラッキングテンプレートからそれらを削除してください。</li></ul> |
| <span id="unexpected-srn-attribution"></span>予期しないSRN計測 | Google AdsのWebキャンペーンによるインストールが、SRN（Self-Reporting Network）経由で`googleadwords_int`に紐づく場合があります。 Googleが、そのインストールを自社の成果として主張した場合に発生します。 Googleからその成果の主張を受け取ると、AppsFlyerはインストールをGoogleの成果として計測します。これは想定される動作であり、GoogleがWebキャンペーンのインストール計測のサポートを拡大するにつれて、発生頻度が増える可能性があります。 |
| <span id="agency-managed-campaigns"></span>代理店が管理するキャンペーン | Webキャンペーンを代理店のみが管理している場合、ポストバックをGoogle Adsに送信するには、広告主と代理店の両方で`googleads_int`連携を有効にする必要があります。代理店側でも、[Googleでサインイン](#h_01J1MPPMW3G9B1G116B18CRYJB)を完了し、OAuthトークンを取得する必要があります。この手順を省略するとポストバックの呼び出しが失敗し、Googleに送信されません。 |
| <span id="plan-availability"></span>利用可能なプラン | `googleads_int`連携は、GrowthプランとEnterpriseプランでのみ利用できます。 ZeroプランとWelcomeプランでは、この連携を利用できません。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01J1MPPMW38A7EG2W8TJ8F6YQ3=%E6%A6%82%E8%A6%81 prerequisite=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01J1MPPMW3GWQKZVG2HAQA9H46=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 how-to-create-a-google-ad-web-campaign=google-ads%E3%81%AEweb%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90 h_01J1MPPMW3ZYSPQHT4D2YAJ038=google-ads%E3%81%AEweb%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90 create-a-google-ad-for-web-integration-in-appsflyer=appsflyer%E3%81%A7%E3%81%AEgoogle-ads%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01J1MPPMW3WTD63M686BHZNKDX=appsflyer%E3%81%A7%E3%81%AEgoogle-ads%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A create-a-web-campaign-in-google-ads=google-ads%E3%81%A7%E3%81%AEweb%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90 h_01J1MPPMW4AQNQEKBN1VSPM4X7=google-ads%E3%81%A7%E3%81%AEweb%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E4%BD%9C%E6%88%90 set-the-final-url=%E6%9C%80%E7%B5%82%E3%83%9A%E3%83%BC%E3%82%B8url%E3%81%AE%E8%A8%AD%E5%AE%9A h_01J1MPPMW48F7X2NYEA735BG51=%E6%9C%80%E7%B5%82%E3%83%9A%E3%83%BC%E3%82%B8url%E3%81%AE%E8%A8%AD%E5%AE%9A set-the-tracking-template-url=%E3%83%88%E3%83%A9%E3%83%83%E3%82%AD%E3%83%B3%E3%82%B0%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88url%E3%81%AE%E8%A8%AD%E5%AE%9A h_01J1MPPMW44596CZVKF9MGDTMP=%E3%83%88%E3%83%A9%E3%83%83%E3%82%AD%E3%83%B3%E3%82%B0%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88url%E3%81%AE%E8%A8%AD%E5%AE%9A google-tracking-template-url-examples=google%E3%83%88%E3%83%A9%E3%83%83%E3%82%AD%E3%83%B3%E3%82%B0%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88url%E3%81%AE%E4%BE%8B 01JCZQR9RJAZF4SJVVKYZNJNPY=google%E3%83%88%E3%83%A9%E3%83%83%E3%82%AD%E3%83%B3%E3%82%B0%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88url%E3%81%AE%E4%BE%8B using-the-tracking-template-url-with-smart-script-or-smart-banners=smart-script%E3%81%BE%E3%81%9F%E3%81%AFsmart-banners%E3%81%A7%E3%81%AE%E3%83%88%E3%83%A9%E3%83%83%E3%82%AD%E3%83%B3%E3%82%B0%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88url%E3%81%AE%E4%BD%BF%E7%94%A8 01JCZQR9RMAW9YP3T3679JAX45=smart-script%E3%81%BE%E3%81%9F%E3%81%AFsmart-banners%E3%81%A7%E3%81%AE%E3%83%88%E3%83%A9%E3%83%83%E3%82%AD%E3%83%B3%E3%82%B0%E3%83%86%E3%83%B3%E3%83%97%E3%83%AC%E3%83%BC%E3%83%88url%E3%81%AE%E4%BD%BF%E7%94%A8 create-a-landing-page-with-onelink-smart-script=onelink-smart-script%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01J1MPPMW4P7Q18JN7JS9ZXR23=onelink-smart-script%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 create-a-landing-page-with-onelink-smart-banners=onelink-smart-banners%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 h_01J1MPPMW4CW8JMJK26PTEY74W=onelink-smart-banners%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%9F%E3%83%A9%E3%83%B3%E3%83%87%E3%82%A3%E3%83%B3%E3%82%B0%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%AE%E4%BD%9C%E6%88%90 google-view-web-to-app=web-to-app%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D view-webtoapp-attribution-data-from-november-2-2025=web-to-app%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D h_01K88H6ETM23EV0PTR8GS13KRN=web-to-app%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D view-in-the-dashboard=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D h_01K88H6ETMG7007CJ0ADD8VQH4=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D view-in-raw-data-and-api-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A8api%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D h_01K88H6ETM502Z2XDC63602FGD=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A8api%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D troubleshooting-inapp-events-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01J52V5G2DSF9PW9Z5GJHAD376=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 traits-and-limitations=%E6%A9%9F%E8%83%BD%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 01JDW5XHD92VFJ93671YP4JMFQ=%E6%A9%9F%E8%83%BD%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
