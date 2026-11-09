---
title: Bidease キャンペーンの設定
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
  created_at: '2023-11-13T13:17:18Z'
  edited_at: '2026-10-14T09:27:34Z'
  id: 20106343354129
  locale: ja
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ja/articles/20106343354129
---
> **概要：**

<Image align="center" alt="bidease.png" src="https://files.readme.io/4a3373c0fdb73190017601c374ca7634cc0feb1954b6e23fc1bd9693c60605f9-20106376017041.png" width="298px" />

<div id="setting-up-bidease" />

## Bideaseのセットアップ

Bideaseとの連携では、クリックスルーおよびビュースルーのアトリビューションがサポートされています。

構成には次のタブが含まれます。連携、計測リンク、コスト、広告収益、権限Bideaseでは、利用可能なタブは、統合、計測リンク、および権限です。

<div id="note" />

> 📘 **注意**
>
> * iOSとAndroidデバイスでは設定が異なります
> * 詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携の設定</Anchor>のページをご確認ください。

<div id="integration-tab" />

<Accordion title="連携タブ">

**連携**タブには、以下で説明するセクションがあります。

<div id="activate-partner" />

#### パートナーの有効化

**前提条件:** **連携を設定する前に、必ず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#パートナーに連絡する">パートナーに連絡して</Anchor>アカウントを開設してください。**

**連携を有効化または編集する方法：**

1. **有効にする：** AppsFlyer のサイドメニューから**共同作業** > **パートナー・マーケットプレイス**の順で選択します。  
   **編集方法：** AppsFlyer のサイドメニューから、 **共同作業** > **連携を有効にする**の順で選択します。
2. パートナーを検索し選択してください。
3. **連携設定** をクリックして、連携設定ページに移動します。
4. **連携**タブで、連携アプリを選択し、**パートナーの有効化**をオンにします。  
   **注意：** トグルは、パートナーと作業している間、オン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>にしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

<div id="advanced-privacy" />

#### 高プライバシーポストバック

iOS アプリの場合のみ:ポストバックやレポートを介してパートナーと共有されるデータのコントロールは、高度なプライバシー（ iOS 14.5 以降）<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">の切り替え状態</Anchor>によって異なります。

| 高度なプライバシー:：オン | 高度なプライバシー:：OFF |
| --- | --- |
| そのパートナーに紐付いているイベントのみのポストバックが送付されます。 | ご自身で設定された以下の内容に沿った形でポストバックが送付されます：<ul><li>**オーガニックを含む全メディアソース**</li><li>**このパートナーのみ**</li></ul> |
| ポストバックは<Anchor target="_blank" href="/partners/ja/docs/advanced-privacy-guide-postback-macros-for-ad-networks">高度なプライバシーテンプレート</Anchor>に従って送信されます。 |  |
| 集計された匿名データがパートナーと共有されます。つまり、ユーザーレベルのデータ（デバイスID）は共有されません。 |  |

<div id="transaction-id" />

#### トランザクションID

iOS アプリの場合のみ:

<div id="install-attribution" />

#### インストール計測

Bideaseからのビュースルーインストールをアトリビューションするには、 ビュースルーアトリビューションのインストールをオンにします。ビュースルー計測のルックバックスライダーは、 計測リンク タブで使うことができます。

<div id="default-postbacks" />

#### デフォルトのポストバック

アプリ起動前に発生したユーザーアクションに関連するパートナーに自動ポストバックを送信するユーザーのソースを定義します。

* **インストール**で、次のいずれかを選択します。
  * このパートナーのみ：このパートナーのみ: ポストバックを送信するのは、インストールがこのパートナーに紐づいている場合、つまり、このアプリをインストールしたユーザーはBideaseからのユーザーです。
  * オーガニックを含むすべてのメディアソース：

<div id="in-app-event-postbacks" />

#### アプリ内イベントポストバック

必要に応じて、**アプリ内イベントのポストバック期間**を設定します（アプリ内イベントのポストバック期間の設定についてお読みください）。

ポストバック経由で送信されるBideaseイベントと一緒にアプリ内イベントのマッピングを設定します。

1. **アプリ内イベントポストバック**を有効にします。
2. **イベントを追加**をクリックして、SDK または サーバー間イベントをリストに追加してください。各項目の説明は以下を参照してください。  

| パラメーター名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>非オーガニックインストールとして計測された端末上で、そのアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>**AppsFlyerイベント**に入力し、**カスタムを作成**をクリックしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントマッピングの詳細をお読みください。</Anchor></li></ul> |
| **送信オプション** | イベントの送信オプションを選択します。<ul><li>**このパートナーのみ**:このイベントがこのパートナーに起因する場合にのみポストバックを送信します。</li><li>**オーガニックを含む全メディアソース**:すべてのイベントを送信：オーガニックを含む全てパートナーに紐づくイベントに対してポストバックを送信します。</li></ul> |
| **送信データ** | <ul><li>**データなし（デフォルト）：** イベント値なしでイベント自体のみを送信します。</li><li>**イベント値と収益：** 収益値を含む全てのイベントパラメーターを送信します（イベント内にある場合）。</li><li>**収益を除いたイベント値：** 収益値以外のすべてのパラメーターを送信します。</li></ul> |

3. [オプション] イベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor>するには、<Image alt="conditional-iae-postbacks-icon.png条件を追加" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />アイコンをクリックします。
4. **連携を保存**をクリックします。
5. ［オプション］連携設定を保存したあとに、他のご自身のアプリのこのパートナーとの連携設定を編集することも可能です：
   1. 左上のパートナー名の下にある、アプリ名をクリックしてアプリ一覧を開いてください。
   2. ドロップダウンリストから別のアプリを選択してください。
   3. 選択したアプリで、<Anchor target="_blank" href="/marketers/ja/docs/amazon-ads-campaign-configuration#integration-tab">連携ステップ</Anchor>を再度実施してください。

<div id="note-1" />

> 📘 **注意**
>
> **iOS アプリの場合のみ:** ポストバックや<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">レポート</Anchor>を介してパートナーと共有されるデータのコントロールは、**高度なプライバシー（ iOS 14.5 以降）**<Anchor target="_blank" href="/marketers/ja/docs/tiktok-for-business-advanced-srn-integration-setup#高プライバシーポストバック">の切り替え状態</Anchor>によって異なります。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

計測リンクを生成して保存し、特定のキャンペーン、広告セット、または単一の広告（UA およびリターゲティングキャンペーンの両方）のためにパートナーに送信できます。シングルプラットフォームリンクまたはOneLinkのいずれかを使用できます。 計測リンクの構造とパラメーターについての詳細はこちら

**計測リンクを作成**するにはこれらの手順に従ってください<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">。</Anchor>

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-cost-and-revenue-data">コストデータ</Anchor> はBidease では利用できません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution">広告収益</Anchor> は Bidease ではご利用いただけません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

データにアクセスしてさまざまなアクションを実行するために Bidease に <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">付与する権限</Anchor> を選択します。

<div id="note-2" />

> 📘 **注意**
>
> 権限のトグルがオンの状態で連携が<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">無効化</Anchor>されても、権限は付与され続けます。

</Accordion>

<div data-zendesk-anchors="setting-up-bidease=bidease%E3%81%AE%E3%82%BB%E3%83%83%E3%83%88%E3%82%A2%E3%83%83%E3%83%97 h_01HF4ED4B5QHY92B03426260QY=bidease%E3%81%AE%E3%82%BB%E3%83%83%E3%83%88%E3%82%A2%E3%83%83%E3%83%97 h_01HF4DWFAP55JRXTR8Z65YAR68=%E6%B3%A8%E6%84%8F h_01HF4DWFAP4S45241VR1PJ3RFC=integration-tab activate-partner::b746d215=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HF4DWFAP9BS1G612WS5HNQ6S=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 advanced-privacy=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HF4DWFAQHEJATJG6DRVMKA34=%E9%AB%98%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF transaction-id=%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3id h_01HF4DWFAQ1Y1AVQ0EV63H5YJ1=%E3%83%88%E3%83%A9%E3%83%B3%E3%82%B6%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3id install-attribution=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC h_01HF4DWFAQQRR8XH5S7NW2NCB6=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HF4DWFAQG4YEEH3HMD61GEWE=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HF4DWFAQQCM4TK3JJNMSM6RD=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HF4DWFAQQ3C7GBA4Q4SA6G0Y=%E6%B3%A8%E6%84%8F-1 h_01HF4DWFAQ9D9BV6PG4BEYX788=attribution-link-tab h_01HF4DWFAQT2PD4863N6EB7HHH=cost-tab h_01HF4DWFAQXMNDHWT0Y4C0M6EN=ad-revenue-tab h_01HF4DWFAQJWNFMFDEZ8XT0DM5=permissions-tab h_01HF4DWFAQJ9HRMD1FE717F1WK=%E6%B3%A8%E6%84%8F-2" />
