---
title: Awinキャンペーン設定
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-09-13T11:50:38Z'
  edited_at: '2026-10-14T09:29:19Z'
  id: 18532554968849
  locale: ja
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ja/articles/18532554968849
---
> **概要：** Awin（affiliatewindow\_int）は、広告主がUAおよびリターゲティングキャンペーンを実行できる統合パートナーです。Awinのマーケティングプラットフォームは、商人（広告主）とアフィリエイト（パブリッシャー）をつなぐのに役立ちます。

awin icon.png

<div id="activate-partner" />

## パートナーの有効化

**前提条件：** 連携を設定する前に、 <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーへ連絡</Anchor>し、アカウントを開設してください。

**連携を有効化または編集する方法：**

1. **有効化するには：** AppsFlyer管理画面 左メニュー **連携** > **Partner Marketplace**へ移動します。  
   **編集方法：** AppsFlyer管理画面左メニュー **連携** > **連携済みパートナー**を選択します。
2. パートナーを検索し選択してください。
3. **連携設定**をクリックします。連携設定ページに移動します。
4. **連携**タブにて連携したいアプリを選択し、 **パートナーを有効にする**をオンにしてください。  
   **注：** パートナーと作業している間、トグルはオン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>のままにしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

<div id="setting-up-awin" />

## Awinのセットアップ

Awinとの統合により、クリックスルーアトリビューションがサポートされます。

構成には次のタブが含まれます。連携、計測リンク、コスト、広告収益、権限Awinの場合、利用可能なタブは、統合、計測リンク、および権限です。

<div id="note" />

> 📘 **注意**
>
> * iOSとAndroidデバイスでは設定が異なります
> * 詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携の設定</Anchor>のページをご確認ください。

<div id="prerequisite" />

### 前提条件

統合を設定する前に、<Anchor target="_blank" href="https://help.awin.com/docs/appsflyer">Awin のドキュメント</Anchor>で指定されているように、SDK に必要な 「コミッション グループ」のパラメーターを実装してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

**連携**タブには、以下で説明するセクションがあります。

<div id="activate-partner-1" />

#### 連携設定

連携を設定するには、まず**パートナーを有効にする**トグルを<Anchor target="_blank" href="/marketers/ja/docs/amazon-ads-campaign-configuration#連携設定">オン</Anchor>にする必要があります。詳細：パートナー連携追加情報については、<Anchor target="_blank" href="https://developer.awin.com/docs/appsflyer">Awin統合ページ</Anchor>を参照できます。

<div id="advanced-privacy" />

#### 高プライバシーポストバック

iOS アプリの場合のみ:ポストバックや<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">レポート</Anchor>を通じてパートナーと共有するデータのコントロールは、 **高プライバシー** （iOS 14.5以降）のトグル状態によって決まります。

| 高度なプライバシー:：オン | 高度なプライバシー:：OFF |
| --- | --- |
| そのパートナーに紐付いているイベントのみのポストバックが送付されます。 | ご自身で設定された以下の内容に沿った形でポストバックが送付されます：<ul><li>**オーガニックを含む全メディアソース**</li><li>**このパートナーのみ**</li></ul> |
| ポストバックは、<Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks">高プライバシーポストバック向けに設定されたテンプレート</Anchor>を使って送信されます。 |  |
| <Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">集計された匿名データ</Anchor>がパートナーと共有されます。つまり、ユーザーレベルのデータ（デバイスID）は共有されません。 |  |

<div id="general-settings" />

#### 一般的な設定

**Awin 広告主のID**

Awin 加盟店 IDを追加します。

<div id="note-1" />

> 📘 **注意**
>
> 複数の商人IDがある場合は、メインのものを接続してください。

<div id="default-postbacks" />

#### デフォルトのポストバック

インストールポストバックは、このパートナーにのみ送信されます。

<div id="in-app-event-settings" />

#### アプリ内イベントの設定

**Awin 広告主のID**

Awin 加盟店 IDを追加します。

<div id="in-app-event-postbacks" />

#### アプリ内イベントポストバック

ポストバック経由で送信されるAwinイベントと一緒にアプリ内イベントのマッピングを設定します。

1. **アプリ内イベントポストバック**を有効にします。
2. **イベントを追加**をクリックして、SDK または サーバー間イベントをリストに追加してください。各項目の説明は以下を参照してください。

| パラメーター名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>非オーガニックインストールとして計測された端末上で、そのアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>**AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。詳細：カスタムイベントのマッピング</li></ul> |
| **パートナー側のイベント名** | パートナー側で定義されている各イベントの固有の名前またはID。オプションは以下の通りです：<ul><li>**テキストフィールド：** 対応するイベントIDをパートナーから取得します。</li><li>**ドロップダウンボックス：** 最適な事前定義されたAppsFlyerイベントを選択します。</li><li>**そのまま**：イベント名のマッピングなしで、イベントをそのまま送信します。</li></ul> |
| **送信オプション** | **このパートナーのみ：** このパートナーのみ:アプリ内イベントのポストバックは、イベントがこのパートナーに紐づいている、—つまり、イベントを実行したユーザーがこのパートナーからの場合にのみ終了できます。 |
| **送信データ** | <ul><li>**データなし（デフォルト）：** イベント値なしでイベント自体のみを送信します。</li><li>**イベント値と収益：** 収益の額を**含む**（存在する場合）、すべてのイベント値を送信します。</li><li>**収益を除いたイベント値：** 収益の額を**含まない**、すべてのイベント値を送信します。</li></ul> |

3. [オプション] イベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor>するには、**条件を追加**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />をクリックします。
4. 必要に応じて、**アプリ内イベントポストバック期間**を設定してください（詳細については、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントポストバック期間の設定</Anchor>を参照してください）。
5. **連携を保存**をクリックします。
6. [オプション] 連携を保存した後、設定画面に留まりつつ、ほかのアプリ / OSの設定へ進みます。
   1. 左上隅のパートナー名下にあるアプリ名をクリックし、アプリ一覧を開きます。
   2. ドロップダウンリストから別のアプリを選択してください。
   3. 選択したアプリに対し、<Anchor target="_blank" href="/marketers/ja/docs/amazon-ads-campaign-configuration#integration-tab">連携手順</Anchor>を再度実行します。

<div id="note-2" />

> 📘 **注意**
>
> iOS アプリの場合のみ:ポストバックや<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">レポート</Anchor>を通じてパートナーと共有するデータのコントロールは、 **<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup#高プライバシーポストバック">高プライバシー</Anchor>** （iOS 14.5以降）のトグル状態によって決まります。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

アトリビューションリンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UAおよびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。単一プラットフォームリンクまたは<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>のいずれかを使用できます。 <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">アトリビューションリンクの構造とパラメーターについての詳細は、こちらをご覧ください</Anchor>。 計測リンクを作成するには、これらの手順に従ってください。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

Awinのコストデータは利用できません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

Awinの広告収益はご利用いただけません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

データにアクセスし、さまざまなアクションを実行するためにAwinに付与するアクセス許可を選択します。

<div id="note-3" />

> 📘 **注意**
>
> * 権限トグルがオンの状態で連携が<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">非アクティブ化</Anchor>された場合でも、権限は付与されたままです。
> * 詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">権限付与</Anchor>のページを参照してください。

</Accordion>

<div id="deep-linking-and-deferred-deep-linking-using-onelink" />

## OneLinkを使用したディープリンク＆ディファードディープリンク

AWINは、プラットフォームで使用されるすべてのリンクをラップして、顧客に分析データを提供できるようにします。これは、ユーザーを最終目的地に送信する前に、リンクがAWINのサイトにリダイレクトされることを意味します。<Anchor target="_blank" href="https://www.appsflyer.com/blog/mobile-marketing/universal-links-app-links/#:~:text=%231%3A%20Link%20wrapping%20and%20Universal%20Links">詳しくは、リンクラッピングの記事をご覧ください</Anchor>。  
プラットフォームとしてのAWINはURIスキームをサポートしていますが、ディープリンクのiOSユニバーサルリンクとAndroidアプリリンクメソッドの処理 **はサポートしていません** 。これは、AWIN内で使用されるすべてのリンクに適用されます。

Awin経由のOneLinkとのディープリンク：

* <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">OneLink URLをURIスキームで設定します</Anchor>

<div id="note-4" />

> 📘 **注意**
>
> iOSアプリの場合、OneLink URLの`af_force_deeplink=true`パラメータを使用して、ディープリンク<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">URIスキーム</Anchor>をアクティブにします。

<div data-zendesk-anchors="activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 01H88VAJH3B5ESK12D3ATMMVZ8=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 setting-up-amazon-dsp-integration=awin%E3%81%AE%E3%82%BB%E3%83%83%E3%83%88%E3%82%A2%E3%83%83%E3%83%97 01H88VAJH3VENKYVRQY5RXN63P=awin%E3%81%AE%E3%82%BB%E3%83%83%E3%83%88%E3%82%A2%E3%83%83%E3%83%97 01H88VAJH3BYZSXQGGZZJQ9N0C=%E6%B3%A8%E6%84%8F prerequisite=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01HFPEEW4FXS9AFQTTEF2ZBDZW=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A 01H88VAJH34GP7FK1KTJGRDPM7=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A advanced-privacy=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3G5FAR7RRNDEPNGME=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A 01H88VAJH3F2FJK5YP3M2V7RWD=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A h_01K4VVB00RYB0XRANWQ29M6P36=%E6%B3%A8%E6%84%8F-1 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3WE9Z0971WMBRBJRS=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HA77JYAR06HA5FZGSRQJATHF=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3AS37MVF75GANWX4B=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH36MYZ9W1YPWA92Z1Z=%E6%B3%A8%E6%84%8F-2 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%E6%B3%A8%E6%84%8F-3 deep-linking-and-deferred-deep-linking-using-onelink=onelink%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF h_01HA77Q9RWZ3FRE5KEN854ZZ78=onelink%E3%82%92%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%9F%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%83%87%E3%82%A3%E3%83%95%E3%82%A1%E3%83%BC%E3%83%89%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF h_01HA78QWQVXEWHPEQE6XWBB64M=%E6%B3%A8%E6%84%8F-4" />
