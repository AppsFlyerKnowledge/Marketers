---
title: Google Ads Web｜PCおよびコンソールアプリ向けの連携
metadata:
  keywords:
    - google ads configuration
    - google ads
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2024-01-18T11:04:33Z'
  edited_at: '2026-10-28T09:15:39Z'
  id: 21768823915665
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/21768823915665
---
> **概要：** Google AdsのWebキャンペーンを使用して、PCやコンソール（家庭用ゲーム機）のプラットフォーム向けアプリを宣伝し、成果を計測します。 AppsFlyerは、クロスプラットフォーム向けランディングページまたはダイレクト計測リンクを使用したGoogleのWebキャンペーンに対応しています。

<div id="note" />

> 📘 **注意**
>
> この記事では、PCまたはコンソールアプリを宣伝するWebキャンペーンについて説明します。モバイルアプリを宣伝するWebキャンペーンを作成する場合は、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-create-web-based-campaigns">Google Ads（AdWords）：Webキャンペーンの作成</Anchor>を参照してください。

<div id="overview" />

## 概要

この記事では、AppsFlyerを使用して、PCおよびコンソールアプリ向けのGoogle Ads Webを設定・利用するための情報と手順を説明します。以下の内容が含まれます。

* [AppsFlyerでのパートナー連携の有効化](/docs/google-ads-web-integration-for-pc-and-console-apps#appsflyerでのパートナーの有効化)。
* [AppsFlyerでのGoogle Ads Webの設定](/docs/google-ads-web-integration-for-pc-and-console-apps#setting-up-Googleadsweb-in-appsflyer)。
* [PCおよびコンソールアプリ向けのGoogle Adsキャンペーンの設定](/docs/google-ads-web-integration-for-pc-and-console-apps#pcおよびコンソールアプリ向けのgoogle-ads-webキャンペーンの設定)。

<div id="prerequisites" />

### 前提条件

Google Ads Web連携を有効にする前に、以下を準備してください。

* PCまたはコンソールアプリ
* AppsFlyerのアカウント
* <Anchor target="_blank" href="https://developers.google.com/identity/protocols/oauth2/scopes">必要なOAuthスコープ</Anchor>を持つGoogleのアクセストークン。アクセストークンに紐づくスコープは、Google Developer Consoleで確認できます。
* <Anchor target="_blank" href="/marketers/ja/docs/user-management">適切なロール／権限を持つAppsFlyerユーザー</Anchor>と、対象アプリへのアクセス権

<div id="activate-partner-in-appsflyer" />

## AppsFlyerでのパートナーの有効化

**パートナー連携を有効にするには、次の手順を実行します。**

1. AppsFlyerのサイドメニューから、［**コラボレーション**］>［**パートナー連携>マーケットプレイス**］タブに移動します。
2. **Google Ads Web**を検索して選択するか、［**連携**］をクリックします。
3. 設定ページが開きます。
4. ［**連携**］タブで、［**パートナーを有効にする**］をオンにします。  
   **注意：** このパートナーとの連携中は、トグルをオン（<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">有効</Anchor>）のままにしておく必要があります。
5. 次のセクションの説明に従い、各タブで設定を完了します。

<div id="set-up-google-ads-web-in-appsflyer" />

## AppsFlyerでのGoogle Ads Webの設定

この設定では、Google Adsへのポストバックも設定できます。 Google Ads Web（googleads\_int）連携では、Google Adsが提供するAPIツールを使用し、広告主の**PCおよびコンソールアプリ**のデータをGoogleのサーバーに直接送信します。このデータには、モバイル以外のプラットフォーム（Webサイトやアプリ）で行われた購入、登録、その他のコンバージョンなど、ユーザーのアクションが含まれます。 Google Adsはこのデータを使用して、広告ターゲティングの最適化、広告パフォーマンスの計測、リターゲティング用のカスタムオーディエンスの作成を行います。

Google Ads Web連携で送信できるポストバックは、インストールとアプリ内イベントのみです。

<div id="integration-tab" />

<Accordion title="連携タブ">

［**連携**］タブには、以下のセクションがあります。

<div id="activate-partner" />

#### パートナーを有効にする

連携を設定するには、まず［**パートナーを有効にする**］トグルをオンにします。

<div id="general-settings" />

#### 一般設定

<div id="note-1" />

> 📘 **注意**
>
> 後述の手順でGoogleにサインインし、AppsFlyerによるトークンの取得を許可すると、**Missing token**エラーメッセージは表示されなくなります。サインイン後もエラーが続く場合は、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-create-web-based-campaigns#access-token-permissions">トークンに必要な権限が付与されていることを確認</Anchor>してください。

1. **初回起動のコンバージョンID**：Google Adsで設定した`First open`コンバージョンアクションのIDを入力します。 IDを確認するには、次の手順を実行します。
   1. Google Adsで、［**初回起動**］のコンバージョンアクションページの［**詳細**］タブを開きます。
   2. ページのURLから、`ctid=*`クエリパラメータの値をコピーします。たとえば、`ctid=123456789`の場合、［**初回起動のコンバージョンアクションID**］欄に`123456789`を入力します。
2. ［**お客様ID**］を入力します。このIDは、Google Adsの管理画面で取得できます。
   1. Google Adsアカウントにログインします。
   2. 右上のGoogleアカウントのアイコンをクリックし、お客様IDが表示されているところまでスクロールしてください。
   3. 同じアプリのキャンペーンを複数のGoogle Adsアカウントで配信している場合、クロスアカウントコンバージョントラッキングにはマネージャー（MCC）アカウントのお客様IDを使用する必要があります。個別アカウントのお客様IDではなく、**MCC ID**を［**お客様ID**］欄と［**MCCのお客様ID**］欄の両方に貼り付けます（両方に同じIDを入力）。   
      広告配信に使用するGoogle Adsアカウントが1つだけの場合は、そのアカウントのIDを［**お客様ID**］欄に貼り付け、［**MCCのお客様ID**］欄は空欄にします。 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">MCCアカウントの設定に関するGoogleの手順</Anchor>を参照してください。
3. AppsFlyerがGoogle Adsにコンバージョンをアップロードできるように、［**Googleでサインイン**］をクリックします。
4. Googleで、前の手順でお客様IDを取得したMCCアカウントの管理者アカウントを選択します。
5. **許可**をクリックします。

<div id="enable-view-through-attribution" />

#### ビュースルー計測の有効化

AppsFlyerは、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-create-web-based-campaigns#onelink-smart-scriptを使ったランディングページの作成">Smart Script</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-create-web-based-campaigns#onelink-smart-bannersを使ったランディングページの作成">Smart Banners</Anchor>を実装したランディングページを使用するGoogleのWebキャンペーンで、ビュースルー計測に対応しています。これにより、ユーザーが広告を直接クリックしなくても、広告表示をきっかけに発生したアプリのインストールを確率論的モデリング（PMOD）で計測できます。

ユーザーがGoogleの広告を見た後、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-create-web-based-campaigns#onelink-smart-scriptを使ったランディングページの作成">Smart Script</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-create-web-based-campaigns#set-up-a-smart-banners-landing-page">Smart Banners</Anchor>を実装したランディングページにアクセスすると、AppsFlyerは、その後に発生したアプリのインストールを、クロスプラットフォームの場合も含め、元のWebインプレッションの成果として計測できます。

利用可能な場合、AppsFlyerはポストバックに`gclid`を含めます。

**ビュースルー計測を有効にするには、次の手順を実行します。**

1. AppsFlyerのサイドメニューから、［**アクティブな連携**］>［**Google Ads Web**］を開きます。
2. ［**連携**］タブで、［**インストールの計測**］セクションまでスクロールします。
3. ［**インストール：ビュースルー計測**］をオンにします。
4. **［任意］**［**クロスプラットフォームの計測優先度を同等にする**］をオンにし、ルックバック期間を設定します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">クロスプラットフォームのインプレッションに同等の優先度を設定する方法</Anchor>を参照してください。
5. **アトリビューション**タブを開きます。
6. ［**ビュースルー計測**］セクションまでスクロールし、［**ビュースルールックバック期間**］を設定します（最大24時間）。
7. ［**連携を保存**］をクリックして変更を適用します。

<div id="default-postbacks" />

#### デフォルトのポストバック

インストールのポストバックは、Google Ads Webにのみ自動送信されます。

<div id="in-app-event-postbacks" />

#### アプリ内イベントポストバック

Google Ads Webに送信するアプリ内イベントポストバックのマッピングを設定します。これらのイベントはGoogle Adsの管理画面で確認できます。

1. **アプリ内イベントポストバック**をオンにします。
2. ［**イベントを追加**］をクリックして、SDKイベントまたはサーバー間イベントをリストに追加します。以下の表は、入力する項目の説明です。

| パラメータ名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | アプリに実装したSDKまたはサーバー間イベントからAppsFlyerが受信したイベント名。<ul><li>［**項目を追加**］をクリックしてイベント名を入力し、![check.png](https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png)をクリックします。</li></ul> |
| **パートナー側のイベント名** | パートナー側で定義された各イベントのコンバージョンアクションID。<ol><li><span class="af-ol-a"></span>Google Adsの［**コンバージョン目標**］ページで、作成したコンバージョンアクションをクリックします。</li><li>コンバージョンアクションの［**詳細**］ページで、URLパラメータ`ctId=`から**コンバージョンアクションID**をコピーします。</li><li>AppsFlyerに戻り、貼り付けます。たとえば、`ctid=123456789`の場合は、`123456789`を貼り付けます。</li></ol> |
| **送信対象ユーザー** | **このパートナーのみ：** このパートナーに成果が紐づくイベント、つまりこのパートナー経由で獲得したユーザーのイベントについてのみ、アプリ内イベントのポストバックを送信します。 |
| **送信するデータ** | **イベント値と収益：** 収益値（イベントに含まれる場合）を含む、すべてのイベントパラメータをポストバックで送信します。 |

3. ［任意］［**条件を追加**］<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />アイコンをクリックして、イベントに<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor>します。
4. 必要に応じて、［**アプリ内イベントのポストバック期間**］を設定します（<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントのポストバック期間の設定</Anchor>の詳細を参照）。
5. **連携を保存**をクリックします。
6. ［任意］連携設定を保存した後に、他のアプリのこのパートナーとの連携設定を編集することも可能です：
   1. 左上のパートナー名の下にあるアプリ名をクリックし、アプリリストを開きます。
   2. ドロップダウンリストから別のアプリを選択してください。
   3. 選択したアプリで、連携ステップを再度実施してください。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

現在、AppsFlyerのUIで計測リンクを生成することはできません。ただし、Smart Scriptを実装したクロスプラットフォーム向けランディングページを使用するか、アプリのダイレクト計測リンクを作成できます（以下の表を参照）。

| 選択肢 | 操作 | 担当者 |
| --- | --- | --- |
| クロスプラットフォーム向けランディングページ | **推奨**：EpicやSteamなど、複数のプラットフォームで利用できるアプリを宣伝するキャンペーンに適しています。<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">クロスプラットフォーム向けランディングページの詳細</Anchor><br /><br /><Anchor target="_blank" href="/marketers/ja/docs/cross-platform-landing-pages-with-smart-script">クロスプラットフォーム向けランディングページの設定方法</Anchor><ul><li>後でSmart Scriptが取得する、関連するすべてのURLパラメータが広告URLに追加されていることを確認してください。</li><li>スクリプトが受信URLからGCLIDを取得し、生成したリンクに追加することを確認してください。つまり、受信URLの`gclid`パラメータを、送信URLのGCLIDパラメータ`gclid`にマッピングします。**注意**！ AppsFlyerのローデータレポートに表示するには、受信URLの`gclid`パラメータを、送信URLの`af_sub[1-5]`パラメータのいずれかにもマッピングする必要があります。</li></ul> | マーケティング担当者（開発者のサポートが必要な場合があります） |
| ダイレクト計測リンク | 1つのプラットフォームに1つのアプリのみがあり、クロスプラットフォーム向けランディングページを使用しない場合は、広告に設定するダイレクト計測リンクを作成できます。<br /><br /><Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-direct-attribution-links">ダイレクト計測リンクの作成方法</Anchor><ul><li>リンクに以下のパラメータが含まれていることを確認してください。<ul><li>af\_media\_source</li><li>af\_campaign\_id</li><li>af\_r<br />**注意**：<Anchor target="_blank" href="https://support.google.com/google-ads/answer/3095550?hl=en">自動タグ設定</Anchor>を使用している場合、Google Adsはすべての送信クリックに<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">Googleクリック識別子（GCLID）</Anchor>パラメータを自動的に追加します。 Google Adsアカウントで自動タグ設定が無効になっている場合は、Google AdsのトラッキングテンプレートURLに`gclid={gclid}`を追加します。</li></ul></li><li>af\_camapign\_id、af\_adset\_id、af\_ad\_idパラメータには、Googleの[ValueTrackパラメータ](https://support.google.com/google-ads/answer/6305348)（動的URLパラメータ）のマクロを使用できます。その他のすべてのパラメータは、手動で設定してください。</li><li>af\_dpパラメータは含めないでください。</li></ul>**ほとんどのプラットフォーム（Epic、Steam、Xbox、PlayStationなど）で使用するテンプレート**：<br /><br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}? af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Steamに誘導するリンクの例**：`https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Google PCおよびMacアプリのみで使用するテンプレート**：<br /><br />`https://app.appsflyer.com/{app_id}?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Google PCに誘導するリンクの例**：`https://app.appsflyer.com/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}` | マーケティング担当者 |

> 👍 **Tip**
>
> キャンペーンを分析しやすいように、campaign-name\_webなど、キャンペーン名の先頭または末尾にキャンペーンの種類（webまたはmobile）を含めてください。

</Accordion>

<div id="set-up-campaigns-in-google-ads-web-for-pc-and-console-apps" />

## PCおよびコンソールアプリ向けのGoogle Ads Webキャンペーンの設定

新しいキャンペーンを設定する際は、ユーザーの誘導先として次のいずれかを選択できます。

* クロスプラットフォーム向けランディングページ：EpicやSteamなど、複数のプラットフォームで利用できるアプリを宣伝するキャンペーンに推奨します。
* 単一のストア：ダイレクト計測リンクを使用する方法で、1つのプラットフォームに1つのアプリのみがある場合に使用します。

それぞれの誘導先に対応するキャンペーンの設定手順は、以下のセクションで説明します。

**注意**：キャンペーンの設定時に、独自のコンバージョンアクションと目標を設定することもできます。その手順も、以下のセクションで説明します。

<div id="campaigns-that-redirect-to-a-crossplatform-landing-page" />

<Accordion title="クロスプラットフォーム向けランディングページに誘導するキャンペーン">

**クロスプラットフォーム向けランディングページにユーザーを誘導するキャンペーンを設定するには**：

1. [計測リンクのセクション](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab)の説明に従って、クロスプラットフォーム向けランディングページを設定します。
2. Google Adsにログインし、新しいキャンペーンを作成します。
3. キャンペーンの目的を選択してください。  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * アプリプロモーション（モバイルアプリのキャンペーンにのみ使用可能）以外の、すべてのキャンペーンの目的が利用可能です。
   * 特定のアプリ内イベントに基づいて最適化するには、キャンペーンの目的を［販売促進］に設定することを推奨します。
4. コンバージョン目標を選択します。  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * デフォルト設定では、事前に設定されたアカウントレベルのキャンペーン目標が表示されます。そのまま使用することも、キャンペーンに関係のない目標を削除することもできます。
   * 必要な目標が見当たらない場合は、[コンバージョンアクションとコンバージョン目標を追加](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals)します。
   * 定義済みの目標は、［コンバージョン］ページでも編集できます。
5. キャンペーンタイプを選択してください。  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * 商品カタログが必要で、確認済みのドメインに限定される「ショッピング」を除き、すべてのキャンペーンの種類を選択できます。
6. Googleの最終ページURLとして、クロスプラットフォーム向けランディングページのURLを入力します。

</Accordion>

<div id="campaigns-that-redirect-to-a-single-app-store" />

<Accordion title="単一のアプリストアに誘導するキャンペーン">

**単一のプラットフォームとアプリストアにユーザーを誘導するキャンペーンを設定するには**：

1. [計測リンクのセクション](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab)の説明に従って、ダイレクト計測リンクを設定します。
2. Google Adsにログインし、新しいキャンペーンを作成します。
3. キャンペーンの目的を選択してください。  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * アプリプロモーション（モバイルアプリのキャンペーンにのみ使用可能）以外の、すべてのキャンペーンの目的が利用可能です。
   * 特定のアプリ内イベントに基づいて最適化するには、キャンペーンの目的を［販売促進］に設定することを推奨します。
4. コンバージョン目標を選択します。  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * デフォルト設定では、事前に設定されたアカウントレベルのキャンペーン目標が表示されます。そのまま使用することも、キャンペーンに関係のない目標を削除することもできます。
   * 必要な目標が見当たらない場合は、[コンバージョンアクションとコンバージョン目標を追加](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals)します。
   * 定義済みの目標は、［コンバージョン］ページでも編集できます。
5. キャンペーンタイプを選択してください。  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * 商品カタログが必要で、確認済みのドメインに限定される「ショッピング」を除き、すべてのキャンペーンの種類を選択できます。
6. Googleの最終ページURLとして使用するリンクを入力します。
   * ユーザーを最終的に誘導したいWeb上の場所を指定する必要があります。 WebランディングページやストアのURLなど、任意のWeb URLを使用できます。例：`https://store.steampowered.com/app/{appid}/{myapp}/`。
   * 最終ページURLにAppsFlyerのURLを設定すると、キャンペーンが不承認になる可能性があるため、使用できません。リダイレクトが発生しない、直接アクセスできるWebアドレスのみを使用してください。
7. GoogleのトラッキングテンプレートURLとして、AppsFlyerのダイレクト計測リンクを入力します。
   * 並行トラッキングを正しく機能させるには、Googleの指定に従い、GoogleのトラッキングテンプレートURLのValueTrackパラメータ`{lpurl}`に最終ページURLを設定する必要があります。
   * af\_dpパラメータは含めないでください。

</Accordion>

<div id="creating-conversion-actions-and-goals" />

<Accordion title="コンバージョンアクションと目標の作成">

Google Adsでは、定義済みのコンバージョンアクションと目標を選択するか、独自に作成できます。

**重要！** AppsFlyerから「First Open」イベントのポストバックを送信するには、「First Open」という名前のコンバージョンアクションを作成する必要があります。

**独自のGoogle Adsコンバージョンアクションと目標を作成するには**：

1. Google Adsアカウントの概要ページで、サイドメニューから［**目標**］>［**コンバージョン**］>［**概要**］を選択します。
2. **+ 新しいコンバージョンアクション**をクリックしてください。
3. コンバージョンアクションのデータソースとして、［**オフラインコンバージョン**］を選択します。
4. コンバージョンの種類のリストから［**インポート**］を選択し、［**APIまたはアップロードによる手動インポート**］>［**クリック経由のコンバージョンを計測**］を選択します。

   <div id="note-2" />

   > 📘 **注意**
   >
   > ［**APIまたはアップロードによる手動インポート**］が表示されない場合：
   >
   > 1. <span class="af-ol-a"></span>［**CRM、ファイル、その他のデータソース**］>［**クリック経由のコンバージョンを計測**］を選択します。
   > 2. ［**データソース**］で、［**このステップをスキップし、後でデータソースを設定**］を選択します。

5. ［**続行**］をクリックします。  
   フォームが表示されます。
6. フォームに入力し、［**作成して続行**］をクリックしてコンバージョントラッカーの作成を完了します。
7. ［**目標とアクションの最適化**］で、コンバージョンアクションをマッピングするカテゴリを選択します。  
   **注意**：Google Adsのキャンペーン最適化は、個々のアクションではなくカテゴリ単位で行われます。キャンペーンを1つのアクションのみで最適化する場合は、そのアクションだけをこのカテゴリにマッピングしてください。たとえば、「install」アクションに基づいてキャンペーンを最適化する場合は、このアクションを「その他」などの専用のカテゴリにマッピングしてください。キャンペーンの作成時に、このカテゴリをキャンペーンの目標として選択できるようになります。
8. Google AdsからコンバージョンアクションIDをコピーし、［**パートナー側のイベント名**］欄に入力します。 アプリ内イベントポストバックの設定で、AppsFlyerのイベント名をパートナーイベントIDにマッピングする際に、**コンバージョンアクションID**をパートナーイベントIDとして使用します。 Google AdsからコンバージョンアクションIDをコピーするには、次の手順を実行します。
   1. <span class="af-ol-a"></span>Google Adsの［**コンバージョン目標**］ページで、作成したコンバージョンアクションをクリックします。
   2. コンバージョンアクションの［**詳細**］ページで、URLパラメータ`ctId=`から**コンバージョンアクションID**をコピーして貼り付けます。
9. ［**作成して続行**］をクリックします。
10. ［**完了**］をクリックします。

</Accordion>

<div id="view-web-to-app-attribution-data-from-november-2-2025" />

## Web to Appの計測データの確認（2025年11月2日以降）

Web経由のコンバージョンイベントは元の`googleads_int`PIDでGoogleに送信されますが、AppsFlyer管理画面とローデータレポートでは`googleadwords_int`PIDでレポートされます。これは、コンバージョンの主な成果イベントとコンバージョンのアシストイベントの両方に適用されます。

この統合されたレポート表示により、モバイルとWebのすべてのコストレポートを含め、Webキャンペーンとアプリキャンペーンのパフォーマンスを1か所で分析できます。

<div id="view-in-the-dashboard" />

### 管理画面での確認

GoogleのWeb to Appの計測結果はすべて、オーバービューダッシュボードとアクティビティダッシュボードで`googleadwords_int`として表示されます。これにより、プラットフォームを横断したキャンペーンの成果を1つにまとめて確認できます。標準のフィルタと内訳表示を使用して、Google Adsのデータ内でアプリとWebのトラフィックを比較できます。

<div id="view-in-raw-data-and-api-reports" />

### ローデータレポートとAPIレポートでの確認

* **ローデータのエクスポートとAPIレスポンス**では、GoogleのWeb上のアクティビティについて、`media_source`フィールドに`googleadwords_int`PIDが含まれます。 Webキャンペーンの設定詳細を確認するには、`original_url`フィールドを参照してください。Webキャンペーンの作成時に使用されたPIDとして`googleads_int`が表示されます。
* **ポストバックレポート**には、ポストバックの送信先となった元のメディアソースとして`googleads_int`が表示されます。

<div id="traits-and-limitations" />

## 機能と制限事項

| 項目 | 説明 |
| --- | --- |
| クリックとインプレッション（一時的な制限） | PCおよびコンソールアプリ向けキャンペーンのクリックとインプレッションは、現在、一時的にGoogleのSRN（`googleadwords_int`）から取得できません。 |

<div data-zendesk-anchors="h_01JP7SMGEPTQGHRYYCBWECH46X=%E6%B3%A8%E6%84%8F overview=%E6%A6%82%E8%A6%81 h_01HK4QHRJG6WTN9P6ZG83XQ6AY=%E6%A6%82%E8%A6%81 prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HFXV8HPGCRGYPEW0NPJ0NR0S=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 activate-partner=appsflyer%E3%81%A7%E3%81%AE%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HFXV8HPH3N4DBKKTQE6DK7FK=appsflyer%E3%81%A7%E3%81%AE%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 setting-up-metaweb-in-appsflyer=appsflyer%E3%81%A7%E3%81%AEgoogle-ads-web%E3%81%AE%E8%A8%AD%E5%AE%9A 01H88VAJH3VENKYVRQY5RXN63P=appsflyer%E3%81%A7%E3%81%AEgoogle-ads-web%E3%81%AE%E8%A8%AD%E5%AE%9A 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B h_01HFXV8HPH6X92YETNAGZ910AV=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E3%81%AB%E3%81%99%E3%82%8B transaction-id=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01HARQDVEDA206D0BBXBC6WEHH=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01JK8XJJWQK5MEJF7GTC5C1707=%E6%B3%A8%E6%84%8F-1 enable-viewthrough-attribution=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01ZXVWB0GZKWB53KTBWJ51RMBM=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3WE9Z0971WMBRBJRS=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3AS37MVF75GANWX4B=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab h_01K88M617Q7SVMDEKP5HTKANJM=tip setting-up-campaigns-in-meta-web-for-pc-and-console-apps=pc%E3%81%8A%E3%82%88%E3%81%B3%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E5%90%91%E3%81%91%E3%81%AEgoogle-ads-web%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HK4S03KVAN99YKXTHAKCT420=pc%E3%81%8A%E3%82%88%E3%81%B3%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E5%90%91%E3%81%91%E3%81%AEgoogle-ads-web%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HMR6HVJF4QT1EZKYZKRVTWEE=campaigns-that-redirect-to-a-crossplatform-landing-page h_01HMR6HVJFMN1V7VM58ZMQFEXF=campaigns-that-redirect-to-a-single-app-store h_01HMTXEZB3W19TKK8ZR6JK2TPG=creating-conversion-actions-and-goals h_01HV6FR2TFYT11H9EVT9Y9TZ3S=%E6%B3%A8%E6%84%8F-2 google%20view-web-to-app=web-to-app%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D2025%E5%B9%B411%E6%9C%882%E6%97%A5%E4%BB%A5%E9%99%8D view-webtoapp-attribution-data-from-november-2-2025=web-to-app%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D2025%E5%B9%B411%E6%9C%882%E6%97%A5%E4%BB%A5%E9%99%8D h_01K88H6ETM23EV0PTR8GS13KRN=web-to-app%E3%81%AE%E8%A8%88%E6%B8%AC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D2025%E5%B9%B411%E6%9C%882%E6%97%A5%E4%BB%A5%E9%99%8D view-in-the-dashboard=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D h_01K88H6ETMG7007CJ0ADD8VQH4=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D view-in-raw-data-and-api-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A8api%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D h_01K88H6ETM502Z2XDC63602FGD=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A8api%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A7%E3%81%AE%E7%A2%BA%E8%AA%8D traits-and-limitations=%E6%A9%9F%E8%83%BD%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KB5085FX7G6Y5E200KVH0ABJ=%E6%A9%9F%E8%83%BD%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />
