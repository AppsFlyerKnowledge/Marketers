---
title: Avow GmbHキャンペーン設定
metadata:
  keywords:
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
  created_at: '2023-09-13T07:21:40Z'
  edited_at: '2026-10-14T09:32:05Z'
  id: 18523546870929
  locale: ja
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ja/articles/18523546870929
---
> **概要：** 概要: AVOW GmbH (avow1\_int) は、アドネットワークおよび代理店両方のアカウントを持つ連携パートナーです。これによって広告主がモバイルデバイスでユーザー獲得キャンペーンを実施できるようになります。Avow GmbHは、クリックベースのモバイルアトリビューションに加えて、広告主がAppsFlyerで記録できるビュースルーアトリビューションも提供しています。

<Image align="center" alt="avow_icon.png" src="https://files.readme.io/f6dc549357d6c7a6ddaec67752570484289529f85defaf0316ccd925868deab7-18523559800465.png" />

<div id="activate-partner" />

## パートナーの有効化

**前提条件:** **連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡して</Anchor>アカウントを開設してください。**

**連携を有効化または編集する方法：**

1. **有効にする：** AppsFlyer のサイドメニューから**共同作業** > **パートナー・マーケットプレイス**の順で選択します。  
   **編集方法：** AppsFlyer のサイドメニューから、 **共同作業** > **連携を有効にする**の順で選択します。
2. パートナーを検索し選択してください。
3. **連携設定** をクリックして、連携設定ページに移動します。
4. **連携**タブで、連携アプリを選択し、**パートナーの有効化**をオンにします。  
   **注意：** トグルは、パートナーと作業している間、オン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>にしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

<div id="setting-up-avow-gmbh" />

## Avow GmbHの設定

Avow GmbHとの連携では、クリックスルーおよびビュースルーのアトリビューションがサポートされています。構成には次のタブが含まれます。連携、計測リンク、コスト、広告収益、権限Avow GmbHの場合、利用可能なタブは、統合、計測リンク、および権限です。

<div id="note" />

> 📘 **注意**
>
> * iOSとAndroidデバイスでは設定が異なります
> * 詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携の設定</Anchor>のページをご確認ください。

<div id="integration-tab" />

<Accordion title="連携タブ">

**連携**タブには、以下で説明するセクションがあります。

<div id="activate-partner-1" />

#### 連携設定

連携を設定するには、まず**パートナーを有効にする**トグルを<Anchor target="_blank" href="/marketers/ja/docs/amazon-ads-campaign-configuration#連携設定">オン</Anchor>にする必要があります。詳細：パートナーのアクティブ化と非アクティブ化のページを参照してください。

<div id="advanced-privacy" />

#### 高プライバシーポストバック

iOSアプリのみ:ポストバックやレポートを介してパートナーと共有されるデータのコントロールは、<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">高度なプライバシー（ iOS 14.5 以降）</Anchor>**の切り替え状態**によって異なります。

| 高度なプライバシー:：オン | 高度なプライバシー:：OFF |
| --- | --- |
| そのパートナーに紐付いているイベントのみのポストバックが送付されます。 | ご自身で設定された以下の内容に沿った形でポストバックが送付されます：<ul><li>**オーガニックを含む全メディアソース**</li><li>**このパートナーのみ**</li></ul> |
| ポストバックは<Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks">高度なプライバシーテンプレート</Anchor>に従って送信されます。 |  |
| 集計された匿名データがパートナーと共有されます。つまり、ユーザーレベルのデータ（デバイスID）は共有されません。 |  |

<div id="general-settings" />

#### 一般的な設定

**Token**

AVOWスペシャリスト(AM/BDM)から提供された認証トークンを追加します。

<div id="install-attribution" />

#### インストール計測

Avow GmbH のビュースルーインストールをアトリビュートするには、ビュースルーアトリビューションのインストール をオンにします。ビュースルールックバック期間は、計測リンクタブ（下記参照）にて設定できます。

<div id="default-postbacks" />

#### デフォルトのポストバック

インストールおよび拒否されたインストールのポストバックは、このパートナーにのみ送信されます。


**<span id="in-app-event-settings"></span><span id="inapp-event-settings"></span>Token**

AVOWスペシャリスト(AM/BDM)から提供された認証トークンを追加します。

<div id="in-app-event-postbacks" />

#### アプリ内イベントポストバック

ポストバック経由で送信されるAvow GmbH イベントと一緒にアプリ内イベントのマッピングを設定します。

1. **アプリ内イベントポストバック**を有効にします。
2. **イベントを追加**をクリックして、SDK または サーバー間イベントをリストに追加してください。各項目の説明は以下を参照してください。  

| パラメーター名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>非オーガニックインストールとして計測された端末上で、そのアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>**AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントマッピングの詳細をお読みください。</Anchor></li></ul> |
| **パートナー側のイベント名** | パートナー側で定義されている各イベントの固有の名前またはID。オプションは以下の通りです：<ul><li>**テキストフィールド：** 対応するイベントIDをパートナーから取得します。</li><li>**ドロップダウンボックス：** 最適な事前定義されたAppsFlyerイベントを選択します。</li><li>**そのまま**：イベント名のマッピングなしで、イベントをそのまま送信します。</li></ul> |
| **送信オプション** | **このパートナーのみ：** アプリ内イベントのポストバックは、このパートナーに成果が紐づいているイベントに対してのみ送信されます。つまり、それを実行したユーザーはこのパートナーから来たということです。 |
| **送信データ** | <ul><li>**データなし（デフォルト）：** イベント値なしでイベント自体のみを送信します。</li><li>**イベント値と収益：** 収益値を含む全てのイベントパラメーターを送信します（イベント内にある場合）。</li><li>**収益を除いたイベント値：** 収益値以外のすべてのパラメーターを送信します。</li></ul> |

3. [オプション] イベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor>するには、<Image alt="conditional-iae-postbacks-icon.png条件を追加" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />アイコンをクリックします。
4. 必要に応じて、**アプリ内イベントのポストバック期間**を設定します。（詳細：<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間"> アプリ内イベントのポストバックウィンドウの設定</Anchor>）
5. **連携を保存**をクリックします。
6. [オプション] 連携を保存した後、設定画面に留まりつつ、ほかのアプリ / OSの設定へ進みます。
   1. 左上隅のパートナー名下にあるアプリ名をクリックし、アプリ一覧を開きます。
   2. ドロップダウンリストから別のアプリを選択してください。
   3. 選択したアプリで、連携ステップを再度実施してください。

<div id="note-1" />

> 📘 **注意**
>
> iOS アプリの場合のみ:ポストバックや<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">レポート</Anchor>を介してパートナーと共有されるデータのコントロールは、**高度なプライバシー（ iOS 14.5 以降）**<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup#高プライバシーポストバック">の切り替え状態</Anchor>によって異なります。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

計測リンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UA およびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。シングルプラットフォームリンクまたはOneLinkのいずれかを使用できます。 計測リンクの構造とパラメーターについての詳細はこちら 計測リンクを作成するには、次の手順に従ってください。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

Avow GmbH のコストデータは利用できません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

Avow GmbH の広告収益はご利用いただけません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

データにアクセスし、さまざまなアクションを実行するためにAvow GmbHに付与するアクセス許可を選択します。

<div id="note-2" />

> 📘 **注意**
>
> * 権限のトグルがオンの状態で連携が<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">無効化</Anchor>されても、権限は付与され続けます。
> * 詳細：権限の付与

</Accordion>

<div data-zendesk-anchors="activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 01H88VAJH3B5ESK12D3ATMMVZ8=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 setting-up-amazon-dsp-integration=avow-gmbh%E3%81%AE%E8%A8%AD%E5%AE%9A 01H88VAJH3VENKYVRQY5RXN63P=avow-gmbh%E3%81%AE%E8%A8%AD%E5%AE%9A 01H88VAJH3BYZSXQGGZZJQ9N0C=%E6%B3%A8%E6%84%8F 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A 01H88VAJH34GP7FK1KTJGRDPM7=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A advanced-privacy=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3G5FAR7RRNDEPNGME=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A 01H88VAJH3F2FJK5YP3M2V7RWD=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A install-attribution=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC h_01HA6PNN6RJYTNXRAS3M9EA4M4=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3WE9Z0971WMBRBJRS=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HA79D908WB6G9FFDKDJNVHEM=inapp-event-settings inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH3AS37MVF75GANWX4B=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H88VAJH36MYZ9W1YPWA92Z1Z=%E6%B3%A8%E6%84%8F-1 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%E6%B3%A8%E6%84%8F-2" />
