---
title: Web訪問者をアプリへ誘導するSmart Scriptの設定
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2021-12-13T09:57:23Z'
  edited_at: '2026-10-28T09:20:05Z'
  id: 4413588932241
  locale: ja
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ja/articles/4413588932241
---
> **概要：** OneLink Smart Scriptを設定すると、流入元を問わず、モバイルWebサイトの訪問者をモバイルアプリへ誘導し、その成果を紐づけられます。

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

## 設定

OneLink Smart Scriptには、次の2つのバージョンがあります。

**OneLink Smart Script V2（推奨）**：初めてOneLink Smart Scriptを設定する場合は、このバージョンの使用をおすすめします。開発者の支援がなくても、AppsFlyerの管理画面で生成できます。何らかの理由で開発者の対応が必要な場合も、実装作業を簡単に進められます。 Googleタグマネージャーを使った設定にも対応しています。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2">開発者向けの手順を参照</Anchor>

<Anchor target="_blank" href="/marketers/ja/docs/legacy-onelink-smart-script-v1-setup">**OneLink Smart Script V1（旧版）**</Anchor>：すでにOneLink Smart Scriptを設定している場合は、このバージョンのドキュメントを参照してスクリプトを保守・編集してください。**注意**：必須ではありませんが、OneLink Smart Scriptで<Anchor target="_blank" href="https://www.appsflyer.com/glossary/view-through-attribution/">ビュースルーアトリビューション</Anchor>を正しく計測するために、V2への移行をご検討ください。

### OneLink Smart Scriptの設定

Smart Scriptは、次のいずれかの方法で設定できます。

* Webサイトにスクリプトを埋め込む。
* Googleタグマネージャーを使用する。

#### 作業範囲

**担当者**

* **広告主**：
  * 受信URLを処理するスクリプトの[引数](/docs/set-up-smart-script-to-convert-web-visitors#arguments)に基づいて、送信URLに含める情報を決めます。受信URLの情報を加工するか、使用する値を固定で指定して、送信URLに追加するアトリビューションとディープリンクのデータを決めます。
  * AppsFlyerの管理画面でSmart Scriptを生成します。
  * モバイルWebサイトへ誘導するすべてのキャンペーンについて、受信URLにスクリプトが処理できるパラメータが含まれていることを確認します。
  * <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Smart Scriptをテストします</Anchor>。
* **Web開発者**：
  * 対象のモバイルサイトやページでスクリプトが動作することを確認します。
  * 生成された値を必要に応じて使用します。たとえば、WebサイトのCTAにリンクとして設定します。
  * スクリプトを使ったQRコードの作成に、開発者の対応が必要な場合があります。
  * スクリプトに高度な引数を手動で追加する際に、開発者の対応が必要な場合があります。

**前提条件**

* 少なくとも1つのアプリが登録されたAppsFlyerアカウント。
* [OneLinkURLパラメータ](/docs/set-up-smart-script-to-convert-web-visitors#arguments)の値として使用する<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor>。

<div id="how-to-create-a-onelink-smart-script" />

<Accordion title="OneLink Smart Scriptの作成">

**OneLink Smart Scriptを作成するには：**

1. AppsFlyerのサイドメニューから、**［Engage］** > **［Web-to-app］** > <strong>［Smart Script］</strong>を選択します。
2. ***初めて利用する場合***
   1. *<strong>［はじめる］</strong>ボタンをクリックします。*
   2. *手順4以降に進みます。*
3. ページ上部の<strong>［＋新しいSmart Script］ボタン</strong>をクリックします。
4. 画面の指示に従って、Smart Scriptに名前を付けます。
5. スクリプトの基になるOneLinkテンプレートを選択します。テンプレートには、基本的なリダイレクト設定が含まれています。
6. 送信URLに含めるパラメータをマッピングします。受信URLのパラメータを基に設定します。**注意**：メディアソース（pid）パラメータは必須です。
   1. マッピング先の送信パラメータ／ディメンションを選択します。  
      通常は変更できないAppsFlyerのパラメータ名ですが、自分でパラメータ名を入力する場合もあります。
   2. 送信パラメータの値をどのように設定するかを決め、次の項目で設定します。
      * 受信URLのパラメータ：送信URLに値を引き継ぐ元となる、受信URLのパラメータ候補を1つ以上指定します。受信URLのパラメータの値が、送信URLのパラメータの値になります。
        * 例：any\_param\_name、utm\_param\_name。受信URLにutm\_param\_nameが見つかった場合、その値が、選択した送信URLのパラメータに使用されます。
        * Smart Scriptは、パラメータのリストを左から右へ順に検索し、最初に見つかったものを送信URLのパラメータにマッピングします。
        * このパラメータのリストは、開発者向けにはkeysと呼ばれます。
      * デフォルト値：受信URLのパラメータが見つからない場合、または受信URLのパラメータを指定しない場合に、送信パラメータに使用する値を入力します。
        * 例：受信URLのパラメータとしてany\_paramnameとutm\_paramnameを指定し、どちらも見つからなかった場合、送信パラメータにはデフォルト値が使用されます。
      * 値の上書き：受信URLの値と、送信URLでその代わりに使用する値を、1組以上設定します。
        * 例：campaignパラメータの値が受信URLではcampaign\_nameの場合、送信URLではnew\_campaign\_nameに変更できます。
   3. ［任意］<strong>［＋新しいパラメータ］</strong>をクリックすると、マッピングするパラメータを追加できます。使用可能な[追加の引数](/docs/set-up-smart-script-to-convert-web-visitors#arguments)（パラメータ設定）の一覧を参照してください。
7. ［任意］<strong>［Webリファラのマッピング］</strong>で<strong>［自然検索経由のインストールのメディアソース］</strong>を有効にすると、URLパラメータのマッピングでメディアソースを特定できなかった自然検索からの流入について、メディアソースを自動設定できます。[詳細はこちら](#seo-referrer-mapping)
8. WebサイトへのSmart Scriptの実装方法を選択します。
   * **Webサイトにスクリプトを埋め込む。**
   * **Googleタグマネージャーを使用する。**
9. <strong>［テスト］</strong>をクリックし、<Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Smart Scriptのテストページ</Anchor>でスクリプトをテストします。正しい送信URLが生成されることを確認します。
10. 次のいずれかをクリックします。
    1. **［保存］**：変更内容を保存します。
    2. **［保存して生成］**：保存してスクリプトを生成します。
       1. <strong>［スクリプトをダウンロード］</strong>をクリックします。
11. Webサイトへの埋め込みを選択した場合は、Web開発者にスクリプトの実装を依頼し、生成される送信URLの使用方法も伝えます。たとえば、モバイルサイトのCTAボタンに設定したり、デスクトップサイトにQRコードとして表示したりします。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#embed-the-script-in-your-website">開発者向けの手順</Anchor>
12. Googleタグマネージャーの使用を選択した場合：
    1. Googleタグマネージャーで新しいタグを作成して名前を付け、<strong>［タグの設定］</strong>をクリックし、<strong>［カスタムHTML］</strong>を選択します。
    2. HTMLの入力欄に、生成したSmart Scriptのコードを貼り付けます。
    3. <strong>［トリガー］</strong>をクリックし、新しいトリガーを作成して名前を付け、<strong>［トリガーの設定］</strong>で設定内容を選択します（すべてのページビューなど）。<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">詳細はGTMのドキュメントを参照</Anchor>
    4. <strong>［保存］</strong>をクリックします。
    5. 生成される送信URLの使用方法をWeb開発者に伝えます。たとえば、モバイルサイトのCTAボタンに設定したり、デスクトップサイトにQRコードとして表示したりします。<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#use-google-tag-manager">開発者向けの手順</Anchor>
13. 保存したスクリプトは、[ドロップダウンメニュー](/docs/set-up-smart-script-to-convert-web-visitors#how-to-edit-or-delete-a-script)で確認できます。

> 🚧 **重要**
>
> スクリプトを更新するたびに、再実装が必要です。

</Accordion>

<div id="how-to-edit-or-delete-a-script" />

<Accordion title="スクリプトの編集・削除">

**スクリプトを編集または削除するには：**

1. Smart Script名の横にあるドロップダウン矢印<Image alt="Down_arrow.jpg" src="https://files.readme.io/a82023665721be681f985548857c4c329f626435780bb1bff7a3821b32b69078-42045468433041.jpg" width="28px" />をクリックします。  
   保存したすべてのスクリプトが表示されます。  

   <Image alt="Script_steps.jpg" src="https://files.readme.io/824c042dc23acaa14b360ce8cd792cfc2e85ee3c9c95e3fa694f96badfeb1fc2-42045468432657.jpg" width="1732px" />
2. 編集するスクリプトの横にある鉛筆アイコンをクリックします。
   1. [OneLink Smart Scriptの作成手順](/docs/set-up-smart-script-to-convert-web-visitors#onelink-smart-scriptの設定)に従います。
3. ごみ箱アイコンをクリックすると、Smart Scriptを削除できます。

> 🚧 **重要**
>
> スクリプトを更新するたびに、再実装が必要です。

</Accordion>

<div id="how-to-duplicate-a-script" />

<Accordion title="スクリプトの複製">

**スクリプトを複製するには：**

1. 複製するSmart Scriptを開きます。
2. 上部のバナーにある複製ボタン<Image alt="SmartScript_duplicate.jpg" src="https://files.readme.io/ec05ea217331b588dc7033984287d46b61a37e41510546b67a0046ea281e0979-42045454920721.jpg" width="21px" />をクリックします。
3. [OneLink Smart Scriptの作成手順](/docs/set-up-smart-script-to-convert-web-visitors#onelink-smart-scriptの設定)に従います。

</Accordion>

<div id="argument-structure" />

<Accordion title="引数の構造">

OneLink Smart Scriptは、受信URLのパラメータと、スクリプト内で定義した引数に基づいて送信URLを生成します。 afParameters引数は、アトリビューションとディープリンクに使用する複数の引数（パラメータ）で構成されます。各引数は、キー、上書きする値、デフォルト値を含む構造になっています。この構造は開発者向けには設定オブジェクトと呼ばれ、各項目の内容は以下の表のとおりです。

| 引数 | 説明 | 例 |
| --- | --- | --- |
| 受信URLのパラメータ（開発者向けにはkeysと呼ばれます） | <ul><li>文字列のリスト</li><li>スクリプトが受信URL内で検索するパラメータの候補です。見つかったパラメータの値が、送信URLの値として設定されます。</li><li>スクリプトは左から右へ順に検索し、最初に一致した時点で検索を終了します。</li></ul> | <ul><li>例：['in\_channel', 'utm\_channel']</li><li>スクリプトのchannelパラメータでは、受信リンクからin\_channelを探し、その値をchannelに使用します。</li></ul> |
| デフォルト値 | <ul><li>文字列</li><li>該当するパラメータが見つからない場合に、代わりに使用する値を指定します。</li><li>keysのリストにあるパラメータが見つからない場合は、送信URLにdefaultValueの値が使用されます。</li><li>空のkeysリストを渡すと、常にデフォルト値を使用できます。</li></ul> | 例：['web\_video']<br /><br />スクリプトのchannelパラメータでは、in\_channelが見つからない場合、channelの値としてweb\_videoを使用します。 |
| 値の上書き | <ul><li>辞書型\{文字列: 文字列\}</li><li>送信リンクで値を変更する場合は、受信URLの元の値と、置き換え後の値を組み合わせて指定します。</li><li>スクリプトは、受信URLから取得したパラメータの値を、指定した値に置き換えます。</li></ul> | 例：\{'video': 'video\_new'\}<br /><br />スクリプトのchannelパラメータでは、受信した値がvideoの場合、送信リンクではvideo\_newに変更します。 |

</Accordion>

<div id="arguments" />

<Accordion title="引数（パラメータと値）">

OneLink Smart Scriptは、受信URLのパラメータと、スクリプト内で定義した引数に基づいて送信URLを生成します。

#### Smart Scriptに実装する引数（パラメータと値）

<table><thead><tr><th colspan="2">引数</th><th>説明</th><th>設定内容の記入欄（ご自身または開発者の作業用）</th></tr></thead><tbody><tr><td colspan="2">oneLinkURL（必須）</td><td><ul><li>OneLinkテンプレートのドメインとテンプレートIDを指定します。<strong>注意：</strong>OneLinkのカスタムリンクURLではありません。</li><li>例：<strong>yourbrand.onelink.me/A1b2</strong> </li><li>ブランドドメインの例：<strong>click.yourbrand.com/A1b2</strong> </li></ul></td><td> </td></tr><tr><td rowspan="9"><p>afParameters</p><p>（必須）</p></td><td><p>mediaSource</p><p>（必須）</p></td><td><ul><li>メディアソースの設定オブジェクト。</li><li>例：<ul><li>キー：['incoming_mediasource’' 'utm_source']</li><li>デフォルト値：['any_source']</li><li>値の上書き：`{twitter: 'twitter_int', orig_src: 'new_src',  seo:'false'}</li></ul></li></ul></td><td><p>キー：</p><p>デフォルト値：</p><p>値の上書き：</p></td></tr><tr><td>campaign</td><td><ul><li>キャンペーンの設定オブジェクト。</li><li>例：<ul><li>キー：['incoming_campaign', 'utm_campaign']</li><li>デフォルト値：['any_campaign_name']</li><li>値の上書き：{campaign_name: 'new_campaign_name'}</li></ul></li></ul></td><td><p>キー：</p><p>デフォルト値：</p><p>値の上書き：</p></td></tr><tr><td>channel</td><td><ul><li>チャネルの設定オブジェクト。</li><li>例：<ul><li>キー：['incoming_channel', 'utm_channel']</li><li>デフォルト値：['any_video']</li><li>値の上書き：{video: 'new_video'}</li></ul></li></ul></td><td><p>キー：</p><p>デフォルト値：</p><p>値の上書き：</p></td></tr><tr><td>ad</td><td><ul><li>広告の設定オブジェクト。</li><li>例：<ul><li>キー：['incoming_ad', 'utm_ad']</li><li>デフォルト値：['any_ad_name']</li><li>値の上書き：{ad_name: 'new_ad_name'}</li></ul></li></ul></td><td><p>キー：</p><p>デフォルト値：</p><p>値の上書き：</p></td></tr><tr><td>adSet</td><td><ul><li>広告セットの設定オブジェクト。</li><li>例：<ul><li>キー：['incoming_adset', 'utm_adset']</li><li>デフォルト値：['any_ad_name']</li><li>値の上書き：{adset_name: 'new_adset_name'}</li></ul></li></ul></td><td><p>キー：</p><p>デフォルト値：</p><p>値の上書き：</p></td></tr><tr><td>deepLinkValue</td><td><ul><li> <strong>deep_link_value</strong>の設定オブジェクト。</li><li>例：<ul><li>キー：['product_id', 'page_name']</li><li>デフォルト値：'new_offers_page'</li><li>値の上書き：{twenty_percent_off: 'thirty_percent_off'}</li></ul></li></ul></td><td><p>キー：</p><p>デフォルト値：</p><p>値の上書き：</p></td></tr><tr><td>afSub1-5</td><td> <strong>af_sub[1-5]</strong>の設定オブジェクト。</td><td><p>キー：</p><p>デフォルト値：</p><p>値の上書き：</p></td></tr><tr><td>googleClickIdKey</td><td> <a href="https://support.google.com/google-ads/answer/9744275?hl=en" target="_blank">GCLID</a>を格納するパラメータの名前を指定します。<br/><strong>注意</strong> <span>AppsFlyerのローデータレポートに表示するには、<strong>af_sub[1-5]</strong>のいずれかを使用する必要があります。</span> </td><td> </td></tr><tr><td> <span>その他のクエリパラメータ（カスタム）</span><br/> </td><td><ul><li>アトリビューションやディープリンクのためにOneLinkの送信URLに含めるその他のパラメータを、設定オブジェクトとともに指定します。</li><li>カスタムパラメータ名は、開発者が設定オブジェクト内のparamKeyに指定します。<span></span> </li><li>例：<ul><li>paramKey: 'deep_link_sub1'</li><li>キー：['page_id']</li><li>デフォルト値：'page1'</li><li>値の上書き：{page12: 'new_page12'}`</li></ul></li></ul></td><td><p>パラメータキー：</p><p>キー：</p><p>デフォルト値：</p><p>値の上書き：</p></td></tr></tbody></table>

</Accordion>

<div id="advanced-arguments" />

<Accordion title="高度な引数">

以下の表では、技術的な知識を持つマーケターや開発者がSmart Scriptに実装できる引数を説明します。

#### Smart Scriptに実装する高度な引数（パラメータと値）

<table><thead><tr><th colspan="2">引数</th><th>説明</th><th>設定内容の記入欄（ご自身または開発者の作業用）</th></tr></thead><tbody><tr><td colspan="2"> <br/>referrerSkipList</td><td><ul><li>特定のクリックのHTTPリファラで検索する文字列のリスト（TwitterやFacebookなど）です。該当する文字列が見つかった場合、Smart Scriptは<code>null</code>を返します。 X AdsやMeta adsなど、クリックがすでにレポートされるSRNで役立ちます。</li><li>この引数を実装すると、条件に一致した場合にスクリプトはOneLink URLを生成しません。</li></ul></td><td> </td></tr><tr><td colspan="2">urlSkipList</td><td><ul><li>特定のクリックのURLで検索する文字列のリスト（af_rなど）です。該当する文字列が見つかった場合、Smart Scriptは<code>null</code>を返します。 af_rを指定したAppsFlyerのアトリビューションリンクでモバイルWebサイトへリダイレクトする際に、元のクリックのデータを失わないようにしたい場合に役立ちます。</li><li>この引数を実装すると、条件に一致した場合にスクリプトはOneLink URLを生成しません。</li></ul></td><td> </td></tr><tr><td colspan="2">SEO</td><td><ul><li>有効にすると、<strong>［URLパラメータのマッピング］</strong>でメディアソースを特定できなかった場合に、WebリファラのURLに基づいて検索エンジンからの訪問かどうかを確認し、それに応じたメディアソースを設定します。（バージョン2.10.3以降で利用可能）</li></ul></td><td> </td></tr></tbody></table>

</Accordion>

## 利用ケース

以下では、よくあるキャンペーンとメディアソースの組み合わせについて、Smart Scriptの利用ケースを説明します。

<div id="utm-parameters" />

<Accordion title="UTMパラメータ">

**UTMパラメータに対応するスクリプトを設定するには：**

1. 受信URLのUTMパラメータ（**utm\_source**、**utm\_campaign**など）を一覧にし、送信URLのパラメータ（**media\_source**、**campaign**など）に対応付けます。
2. これらを[引数の一覧](/docs/set-up-smart-script-to-convert-web-visitors#arguments)に記入し、Web開発者に渡します。

**結果**：受信パラメータ（**utm\_source**、**utm\_campaign**）の値が、それぞれ送信リンクの**media\_source**と**campaign**に設定されます。

</Accordion>

<div id="google-ads-gclid" />

<Accordion title="Google広告のGCLID">

GCLIDパラメータを含むGoogle広告キャンペーンの通常のインストールアトリビューションでは、広告をクリックしたユーザーをアプリのストアページURLへリダイレクトする必要があります。

このケースではGoogle広告からWebページやランディングページへ誘導するため、スクリプトはGoogle広告のインストールキャンペーンURLからGCLIDを取得し、送信URLに設定します。 Smart Scriptバージョン2.9.0以降では、GCLID、WBRAID、GBRAIDがある場合、生成される送信URLにそのまま自動で引き継がれます。

クリックIDを他の送信パラメータ（**af\_sub[1-5]**）にマッピングすると、AppsFlyerのローデータレポートでも確認できます。

**注意**

* これはインストールキャンペーンに適用されます。 ACI以外の検索キャンペーン、つまりリエンゲージメントキャンペーンでは、Smart Scriptの出力にかかわらず、Googleがメディアソースとして紐づく場合があります。
* GCLIDが見つかった場合、スクリプトは受信パラメータのkeywordを探します。見つかった場合は、その値を送信URLのaf\_keywordsに設定します。

**前提条件**：Googleの管理画面で<Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">自動タグ設定を有効にします</Anchor>。   
自動タグ設定を有効にすると、URLに*GCLID*パラメータが含まれます。

**Google広告のGCLIDを他のパラメータにマッピングするには：**

1. 送信URLでGCLIDを格納するパラメータを選択します。  
   推奨：AppsFlyerのローデータレポートにデータを表示できるよう、**af\_sub[1-5]** のいずれかを選択してください。
2. これを[引数の一覧](/docs/set-up-smart-script-to-convert-web-visitors#arguments)に記入し、Web開発者に渡します。送信URLでは、GCLIDが**af\_sub[1-5]** のいずれかの値として設定されます。

**これらのインストールをGoogle広告に通知するには：**

**推奨：** <Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-create-web-based-campaigns">GoogleのWeb連携</Anchor>を設定します。この連携は、インストールのポストバックの自動送信に対応しています。

**この連携を利用していない場合：**

1. CSVから、またはインストールごとにPush APIでリアルタイムに、**af\_sub[1-5]** パラメータのGCLIDデータを取得します。
2. GCLIDデータを、<Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">手動</Anchor>または<Anchor target="_blank" href="https://developers.google.com/google-ads/api/docs/start">Google Ads API</Anchor>でGoogleにアップロードします。

> 📘 **注意**
>
> GCLIDを使用するこの方法は、Googleが公式にサポートまたは推奨しているものではありません。 GoogleがGCLIDパラメータを廃止した場合は、その変更に対応するようスクリプトを更新します。記事や添付スクリプトの更新通知を受け取れるよう、記事上部の<strong>［フォロー］</strong>ボタンをクリックして、この記事をフォローしてください。

</Accordion>

<div id="facebook-click-id" />

<Accordion title="Facebook FBCLID">

Meta adsのクリックIDは、FBCLIDと呼ばれます。 Smart Scriptバージョン2.8.1以降では、FBCLIDがある場合、生成される送信URLにそのまま自動で引き継がれます。クリックIDを他の送信パラメータにマッピングすると、AppsFlyerのローデータレポートでも確認できます。

**FBCLIDを他のパラメータにマッピングするには：**

1. 送信URLでFBCLIDを格納するパラメータを選択します。   
   推奨：AppsFlyerのローデータレポートにデータを表示できるよう、**af\_sub[1-5]** のいずれかを選択してください。
2. これを[引数の一覧](/docs/set-up-smart-script-to-convert-web-visitors#arguments)に記入し、Web開発者に渡します。送信URLでは、FBCLIDが**af\_sub[1-5]** のいずれかの値として設定されます。

</Accordion>

<div id="tiktok-ttclid-x-twclid-and-snapsccid" />

<Accordion title="TikTok（ttclid）、X（twclid）、Snap（ScCid）">

TikTok、X（旧Twitter）、Snapの広告キャンペーンでは、広告クリックに付与された各媒体固有のクリックIDパラメータを使って、インストールとインストール後のイベントを元の広告に紐づけます。

最初にWebページやランディングページへ誘導する場合は、正しく成果を紐づけられるよう、クリックIDを保持して次のURLへ引き継ぐ必要があります。このケースでは、Smart Scriptが受信したクリックIDパラメータを取得し、生成する送信URLに追加します。

クリックIDはインストール時に取得され、そのインストールに関連する今後のイベントにも使用されます。

Smart Scriptバージョン2.10.0以降では、以下のクリックIDパラメータがある場合、生成される送信URLにそのまま自動で引き継がれます。

* TikTok: ttclid
* X（旧Twitter）：twclid
* Snap: ScCid

これらのクリックIDは、af\_sub1～af\_sub5などの他の送信パラメータにマッピングすることで、AppsFlyerのローデータレポートでも確認できます。

関連するWeb連携の記事も参照してください。

* <Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-create-web-based-campaigns">TikTok</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/snapchat-create-web-based-campaigns">Snap</Anchor>

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="SRN、オウンドメディア、その他のメディアソースのリンク">

SnapchatやX Adsなどの<Anchor target="_blank" href="/marketers/ja/docs/self-reporting-networks-srns#srn媒体">SRN</Anchor>は、Google広告やクロスプラットフォームに対応するMeta adsとは仕組みが異なります。これらのSRNのキャンペーンでは、ユーザーをWebページやランディングページへ誘導し、その後モバイルアプリのユーザーになったかどうかにかかわらず、見込み顧客のクリックに基づいて課金されます。

これらのSRNでは、オウンドメディアやその他のメディアソースのリンクと同じ方法でスクリプトを設定します。

**スクリプトを設定するには：**

1. 受信リンクに含まれるメディアソースとキャンペーンのパラメータ名を一覧にします。
2. これらを[引数の一覧](/docs/set-up-smart-script-to-convert-web-visitors#arguments)に記入し、Web開発者に渡します。  
   受信URLでは、メディアソースの値にSRNまたはメディアソースの種類を指定します。スクリプトはその値を取得し、Webページやランディングページのダウンロードボタンで使用するOneLinkの送信URLの**media\_source**に設定します。送信URLの**media\_source**を変更する場合は、Web開発者に渡す[引数の一覧](/docs/set-up-smart-script-to-convert-web-visitors#arguments)に、受信したメディアソースの値と、上書きするmedia\_sourceの値を記入します。

**結果**：これらのSRNやメディアソースでは、受信リンクのメディアソースとキャンペーンの値が、それぞれ送信リンクの**media\_source**と**campaign**に設定されます。

> 📄 **例**
>
> **受信URL**：https://hotel.me/incoming_mediasource=twitter&incoming_campaign=big_social
>
> **送信URL**：https://hotel.onelink.me/Ac4G?pid=twitter&c=big_social

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="AppsFlyerのアトリビューションリンク">

クリックの計測に対応するアドネットワークでは、AppsFlyerのアトリビューションリンクを使用できます。 AppsFlyerでこのリンクを設定する際に、モバイルWebサイトの誘導先URLを<strong>［リダイレクト先URLのパス（af\_r）］</strong>パラメータに追加すると、Webキャンペーンからアプリへのアトリビューションに対応できます。スクリプトでOneLinkの送信URLを生成すると、元のクリックのデータが一部失われる可能性があります。そのため、送信URLを生成しないようにしたい場合があります。

**対応：urlSkipList**引数に**af\_r**パラメータを指定します。

**結果**：Smart Scriptが受信リンクに**af\_r**パラメータを検出すると、送信URLを生成しません。その場合、開発者が送信URLとして設定するリンクを決め、実装する必要があります。

> 📄 **例**
>
> **受信URL**：https://app.appsflyer.com/id123456789?pid=click_ad_network_int&c=orlando&af_r=hotel.me
>
> **送信URL**：生成されません。

</Accordion>

<div id="web-referrer-mapping" />

<Accordion title="Webリファラのマッピング">

Webリファラのマッピングでは、ユーザーがどのページ（自然検索の結果など）からWebサイトに訪問したかを確認できます。この情報を加えることで、Smart Scriptを使ったWebからアプリへの経路におけるインストールやリエンゲージメントを、より詳しく分析できます。

ランディングページまたはWebサイトのHTTPヘッダーの[`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer)フィールドから、この情報を収集するようSmart Scriptを設定できます。このフィールドには、ユーザーがリンクをクリックして自社のWebページへ移動する直前に閲覧していたページのベースURLが含まれます。

**Webリファラを収集するようにスクリプトを設定するには：**

1. <strong>［Smart Script］</strong>ページを開きます。
2. <strong>［Webリファラのマッピング］</strong>で、Webリファラの値を格納する送信URLのパラメータキーを選択します。
   * af\_channel：ダッシュボードとローデータで確認できます。
   * af\_sub1-5：ローデータの**af\_sub1-5**列と**original URL**列で確認できます。
   * カスタムパラメータ：パラメータ名と値で構成されます。ローデータの**original URL**列に表示されます。

Universal LinksとApp Linksを使用した、自然検索経由のリエンゲージメントのアトリビューションについては、<Anchor target="_blank" href="/marketers/ja/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">こちら</Anchor>を参照してください。

</Accordion>

<div id="seo-referrer-mapping" />

<Accordion title="自然検索のリファラのマッピング">

<strong>［自然検索経由のインストールのメディアソース］</strong>を有効にすると、<strong>［URLパラメータのマッピング］</strong>でメディアソースを特定できなかった自然検索からの流入について、メディアソースを自動設定できます。

* ユーザーのWebリファラが、対応する検索エンジン（google.comやbing.comなど）に一致した場合、メディアソースに対応するチャネル（google\_organic\_seoなど）が設定されます。
* 一致する検索エンジンがない場合は、URLパラメータのマッピングで設定した<strong>［デフォルト値］</strong>が使用されます。

</Accordion>

<div id="desktop" />

<Accordion title="デスクトップ">

この記事の利用ケースの多くは、モバイルデバイスからの訪問を想定しています。そのため、モバイルWebサイトからアプリストアに誘導すると、その場でアプリをダウンロードできます。

一方、デスクトップユーザーのデバイス（デスクトップPCやノートPC）ではモバイルアプリをダウンロードできないため、そのままアプリストアへ誘導すべきではありません。

**デスクトップユーザー向けにスクリプトを設定するには：**

* <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor>の<strong>［デスクトップでリンクがクリックされた場合］</strong>に、誘導先URLを設定します。専用のWebページまたはランディングページにリダイレクトするURLを指定してください。ランディングページには、ユーザーが情報を入力すると、アプリのダウンロードリンクを含むSMSまたはメールを受け取れるWebフォームを設置できます。 Webフォームは自社で作成し、そのURLをスクリプトに設定してください。

**結果**：スクリプトは、ユーザーのデバイスまたはプラットフォームを検出します。デスクトップの場合は、専用のWebページまたはランディングページへ誘導するOneLinkの送信URLを生成します。

<Anchor target="_blank" href="/marketers/ja/docs/qr-to-app-conversion">デスクトップからアプリへのコンバージョン</Anchor>も参照してください。

</Accordion>

<div id="qr-codes" />

<Accordion title="QRコード">

Smart Scriptでは、リンクを設定したボタンの代わりに、WebページにQRコードを表示できます。 

**QRコードを表示するには：**

1. Smart Scriptの設定時に、バージョン2.6以降を使用していることを確認します。
2. 開発者に、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#create-a-qr-code-with-the-smart-script-result">開発者向けの手順</Anchor>に従い、Smart Scriptの生成結果からQRコードを作成するよう依頼します。
3. ［推奨］開発者に次の対応を依頼します。
   * 中央にアプリのロゴを追加し、色を変更するなど、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#create-a-qr-code-with-the-smart-script-result">QRコードをカスタマイズします</Anchor>。
   * デスクトップではQRコードを表示し、モバイルではリンクを設定したボタンを表示します。

**結果**：スクリプトは、URLを設定したボタンの代わりにQRコードを表示します。

> 📄 **例**
>
> **受信URL**：
>
> https://hotel.me/qr_code.html?incmp=gogo&inmedia=email
>
> **送信URL**：
>
> https://hotel.onelink.me/LtRd/?af_js_web=true&af_ss_ver=2_1_0&pid=email&c=gogo
>
> **生成されるQRコード**：
>
> <Image alt="" src="https://files.readme.io/2f06149c901d8a97c2a544b8196e9afecbe3b3748ed8419a39c2dc5e3afa61ba-42045454923153.png" width="48.07%" />

</Accordion>

<div id="impressions" />

<Accordion title="インプレッション">

OneLink Smart Scriptは、Webサイトのインプレッションのカウントにも使用できます。開発者がインプレッション関数を呼び出す必要があります。そのインプレッションに、<Anchor target="_blank" href="/marketers/ja/docs/measure-view-through-engagements">ビュースルーアトリビューション</Anchor>でインストールが紐づきます。

**注意**：

* インプレッションのカウントは、通常のSmart Scriptが生成するURLによるクリックのカウントに加えて利用できます。 Smart Scriptは、クリックとインプレッションのいずれか、または両方のカウントに使用できます。
* Smart Scriptによるビュースルーアトリビューションは、モバイルデバイスでのみ機能し、デスクトップには対応していません。

**これらのインプレッションに新規インストールを紐づける（ビュースルーアトリビューション）には：**

1. Smart Scriptの設定時に、バージョン2.3以降を使用していることを確認します。
2. 開発者に、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#fire-an-impression">Smart Scriptのインプレッション関数を呼び出す</Anchor>よう依頼します。
3. <Anchor target="_blank" href="/marketers/ja/docs/measure-view-through-engagements">ビュースルーアトリビューションが有効になっている</Anchor>ことを確認します。

> 🚧 **重要**
>
> 2023年2月1日（Chrome 110の安定版リリース）以降、Googleは<Anchor target="_blank" href="https://developer.chrome.com/en/docs/privacy-sandbox/user-agent/">User-Agentのデータを削減する変更</Anchor>を行っています。 OneLink Smart Scriptで<Anchor target="_blank" href="https://www.appsflyer.com/glossary/view-through-attribution/">ビュースルーアトリビューション</Anchor>を正しく計測するには、バージョン2.3以降を使用してください。

</Accordion>

## 補足情報

<div id="faq" />

<Accordion title="よくある質問">

#### **ユーザーがWebサイト内の別のページへ移動しても、元の受信URLの情報をOneLinkの生成に使用できますか？**

はい。受信URLのパラメータはブラウジングセッション中保持され、Smart Scriptで生成するOneLinkの送信パラメータに適用されます。実装の詳細は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#preserve-incoming-url-parameters-across-pages">開発者ハブ</Anchor>を参照してください。

#### **GoogleタグマネージャーでSmart Scriptを実装するとエラーになるのはなぜですか？**

AppsFlyerで生成したSmart ScriptをGoogleタグマネージャー（GTM）に挿入すると、「JavaScript too long」エラーが表示される場合があります。その場合は、GTMのタグを削除し、新しく作成してください。

#### **一覧にないパラメータを追加できますか？**

はい。 OneLink Smart Scriptのページで<strong>［＋新しいパラメータ］</strong>をクリックし、マッピングするパラメータを追加します。

* カスタムパラメータに加え、ドロップダウンに表示されていないAppsFlyerの予約済みパラメータも追加できます。
  * 使用可能な[追加の引数](/docs/set-up-smart-script-to-convert-web-visitors#arguments)（パラメータ設定）の一覧を参照してください。
* ドロップダウンで［カスタム］を選択し、<strong>［送信URLのパラメータ］</strong>欄にパラメータを追加します。

たとえばis\_retargetingを追加する場合は、<strong>［マッピング対象］</strong>欄で［カスタムパラメータ］を選択し、<strong>［送信URLのパラメータ］</strong>欄にis\_retargetingを指定します。

![Smart_Script_Custom.jpg](https://files.readme.io/5a09d18b01ece93bbb47667b676039c98742ebc3b88c5235ad92c7e44d5316b9-small-42045454926609.jpg)

#### **Adsetなどのパラメータがドロップダウンに表示されません。**

パラメータの作成・追加時には、ブラウザーの広告ブロッカーを無効にすることをおすすめします。広告ブロッカーによって、「Ad」という文字列を含む選択肢が非表示になる場合があります。

#### **Smart Scriptはどのブラウザーで動作しますか？**

Smart ScriptはJavaScriptを使用しており、すべてのブラウザーで動作する想定です。

</Accordion>

<div id="specs-and-limitations" />

<Accordion title="仕様と制限事項">

| **仕様** | **説明** |
| --- | --- |
| URIスキーム | 既存ユーザー向けにアプリを開くURIスキームをOneLinkテンプレートに設定していても、Smart Scriptで生成するリンクには、開発者がURIスキームを指定したaf\_dpパラメータを<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#set-additional-custom-parameters">カスタムパラメータ</Anchor>として追加する必要があります。 |
| 受信URLに含まれる# | クエリパラメータ（「?」以降の部分）より前にハッシュ記号（「#」）がある受信URLは、Smart Scriptで正しく処理できません。その場合、Smart Scriptはデフォルト値を使用します。 |

</Accordion>

<div data-zendesk-anchors="setup=%E8%A8%AD%E5%AE%9A h_01H95PGMNWR12KQ2P0KT8BBGEC=%E8%A8%AD%E5%AE%9A set-up-onelink-smart-script=onelink-smart-script%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H95PGMNW6N63XQ1EQSQSHHB2=onelink-smart-script%E3%81%AE%E8%A8%AD%E5%AE%9A scope-of-work=%E4%BD%9C%E6%A5%AD%E7%AF%84%E5%9B%B2 h_01H95PGMNWPBRHSZBPMKNJ2PS6=%E4%BD%9C%E6%A5%AD%E7%AF%84%E5%9B%B2 h_01H95PGMNWWYRRNVNTK31XYRN3=how-to-create-a-onelink-smart-script h_01H95PGMNW5HA4FWBFW7AR89AV=%E9%87%8D%E8%A6%81 h_01H95PGMNXZAES8DPJ1B4E1QV8=how-to-edit-or-delete-a-script h_01H95PGMNX5ZT7DPV2WBG0CTKB=%E9%87%8D%E8%A6%81-1 h_01H95PGMNXNT9C07B0YTS1KK82=how-to-duplicate-a-script h_01H95PGMNXWJ9V5JW9JEAHF81S=argument-structure h_01H95PGMNXR2HTV1EF07QVQB6W=arguments arguments-parameters-and-values-to-implement-the-smart-script::d4f6bf94=smart-script%E3%81%AB%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E5%BC%95%E6%95%B0%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%A8%E5%80%A4 h_01H95PGMNXPMCM73XT3GTDVAXJ=smart-script%E3%81%AB%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E5%BC%95%E6%95%B0%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%A8%E5%80%A4 h_01H95PGMNX4B8W84DHJR9T4CR2=advanced-arguments arguments-parameters-and-values-to-implement-the-smart-script=smart-script%E3%81%AB%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E9%AB%98%E5%BA%A6%E3%81%AA%E5%BC%95%E6%95%B0%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%A8%E5%80%A4 h_01H95PGMNXCAHTTJATG75Y3TRN=smart-script%E3%81%AB%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E9%AB%98%E5%BA%A6%E3%81%AA%E5%BC%95%E6%95%B0%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%A8%E5%80%A4 use-cases=%E5%88%A9%E7%94%A8%E3%82%B1%E3%83%BC%E3%82%B9 h_01H95PGMNXBPFFNE44YGGECBPR=%E5%88%A9%E7%94%A8%E3%82%B1%E3%83%BC%E3%82%B9 h_01H95PGMNX3W95JW47YQGSEYQ6=utm-parameters h_01H95PGMNXGZZEMZ6PMAB4XFQQ=google-ads-gclid h_01H95PGMNXZT08G8RTMMG6BQCJ=%E6%B3%A8%E6%84%8F h_01H95PGMNXHJXGB2QXH0YTB6Z0=facebook-click-id h_01KD5EZQFF23MYGXGJF1CF6VPT=tiktok-ttclid-x-twclid-and-snapsccid h_01H95PGMNXBKXFG9M169WG89TK=srns-owned-media-and-other-media-source-links h_01H95PGMNXZPB6CT3ZKJ2KMQ1J=%E4%BE%8B h_01H95PGMNX8Q0BASSESVD06MXE=appsflyer-attribution-links h_01H95PGMNX741EJGPF9G2DS67N=%E4%BE%8B-1 h_01HAS199KS0C0V3G41WGXTK4PF=web-referrer-mapping h_01M1BK4M22YAQ6YX4RZXRKZF7C=seo-referrer-mapping h_01H95PGMNY0P2354ZFVC92TMVC=desktop h_01H95PGMNYDSFP6GJDWC9AE0J2=qr-codes h_01H95PGMNYGJ9BJ86YCP7FYH6G=%E4%BE%8B-2 h_01H95PGMNYZBGZWNFESDTE9GY9=impressions h_01H95PGMNYX1FDT1KK9PQAMX5N=%E9%87%8D%E8%A6%81-2 additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01H95PGMNYB6A8VKEAH8Z8TDPE=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01H95PGMNYKQ8TNM3KKK9EXANV=faq will-the-incoming-url-for-onelink-link-generation-work-if-the-user-browses-to-a-different-page-on-the-website=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%8Cweb%E3%82%B5%E3%82%A4%E3%83%88%E5%86%85%E3%81%AE%E5%88%A5%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%B8%E7%A7%BB%E5%8B%95%E3%81%97%E3%81%A6%E3%82%82%E5%85%83%E3%81%AE%E5%8F%97%E4%BF%A1url%E3%81%AE%E6%83%85%E5%A0%B1%E3%82%92onelink%E3%81%AE%E7%94%9F%E6%88%90%E3%81%AB%E4%BD%BF%E7%94%A8%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01H95PGMNYM5X2K9J0WZW6PZ8A=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%8Cweb%E3%82%B5%E3%82%A4%E3%83%88%E5%86%85%E3%81%AE%E5%88%A5%E3%81%AE%E3%83%9A%E3%83%BC%E3%82%B8%E3%81%B8%E7%A7%BB%E5%8B%95%E3%81%97%E3%81%A6%E3%82%82%E5%85%83%E3%81%AE%E5%8F%97%E4%BF%A1url%E3%81%AE%E6%83%85%E5%A0%B1%E3%82%92onelink%E3%81%AE%E7%94%9F%E6%88%90%E3%81%AB%E4%BD%BF%E7%94%A8%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B why-do-i-get-an-error-when-implemeting-smart-script-via-google-tag-manager=google%E3%82%BF%E3%82%B0%E3%83%9E%E3%83%8D%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%81%A7smart-script%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E3%81%A8%E3%82%A8%E3%83%A9%E3%83%BC%E3%81%AB%E3%81%AA%E3%82%8B%E3%81%AE%E3%81%AF%E3%81%AA%E3%81%9C%E3%81%A7%E3%81%99%E3%81%8B h_01H95PGMNYSQX6BJCN56D4XZZF=google%E3%82%BF%E3%82%B0%E3%83%9E%E3%83%8D%E3%83%BC%E3%82%B8%E3%83%A3%E3%83%BC%E3%81%A7smart-script%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B%E3%81%A8%E3%82%A8%E3%83%A9%E3%83%BC%E3%81%AB%E3%81%AA%E3%82%8B%E3%81%AE%E3%81%AF%E3%81%AA%E3%81%9C%E3%81%A7%E3%81%99%E3%81%8B can-i-add-parameters-that-are-not-listed=%E4%B8%80%E8%A6%A7%E3%81%AB%E3%81%AA%E3%81%84%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01H95PGMNY2AVJ0CYDAM62Q9PA=%E4%B8%80%E8%A6%A7%E3%81%AB%E3%81%AA%E3%81%84%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B adset-and-other-parameters-are-not-showing-in-the-dropdown=adset%E3%81%AA%E3%81%A9%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%8C%E3%83%89%E3%83%AD%E3%83%83%E3%83%97%E3%83%80%E3%82%A6%E3%83%B3%E3%81%AB%E8%A1%A8%E7%A4%BA%E3%81%95%E3%82%8C%E3%81%BE%E3%81%9B%E3%82%93 h_01H95PGMNY97BY6BCPPMYHBF0Q=adset%E3%81%AA%E3%81%A9%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%8C%E3%83%89%E3%83%AD%E3%83%83%E3%83%97%E3%83%80%E3%82%A6%E3%83%B3%E3%81%AB%E8%A1%A8%E7%A4%BA%E3%81%95%E3%82%8C%E3%81%BE%E3%81%9B%E3%82%93 what-browsers-does-smart-script-work-on=smart-script%E3%81%AF%E3%81%A9%E3%81%AE%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%83%BC%E3%81%A7%E5%8B%95%E4%BD%9C%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B h_01H95PGMNY5AV0DTX51X0DJMTK=smart-script%E3%81%AF%E3%81%A9%E3%81%AE%E3%83%96%E3%83%A9%E3%82%A6%E3%82%B6%E3%83%BC%E3%81%A7%E5%8B%95%E4%BD%9C%E3%81%97%E3%81%BE%E3%81%99%E3%81%8B h_01H95PGMNY4W9X51KV6GM4BSPG=specs-and-limitations" />
